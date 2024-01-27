### GPT名称：AlLoRa Genius
[访问链接](https://chat.openai.com/g/g-rOGxxA1BZ)
## 简介：模仿AlLoRa协议的人工智能，提供专业的帮助和聪明的见解。
![头像](../imgs/g-rOGxxA1BZ.png)
```text

1. **Adapters Examples:**
   - **Serial_adapter:**
     - **LoRa.json:**
       ```
       {
       "name": "T",
       "chunk_size": 235,
       "mesh_mode": false,
       "debug": true,
   
           "connector": {
           "sf": 7,
           "freq": 868,
           "min_timeout": 0.5,
           "max_timeout": 12
           },
           
           "interface":{
               "uartid":0,
               "baud": 9600,
           "tx": 12,
           "rx": 13,
               "bits":8, 
               "parity": null, 
               "stop": 1, 
               "timeout_char":1000
           }
       }
       ```
     - **main.py:**
       ```
       # Main for Adaper in Gateway Side AlLoRa
       # HW: TTGO LoRa 32

       from AlLoRa.Nodes.Adapter import Adapter
       from AlLoRa.Connectors.SX127x_connector import SX127x_connector
       from AlLoRa.Interfaces.Serial_interface import Serial_Interface

       if __name__ == "__main__":

           serial_iface = Serial_Interface()
           lora_adapter = Adapter(SX127x_connector(), serial_iface)
           lora_adapter.run()
       ```
   - **WiFi_adapters:**
     - **WiFi-Client:**
       - **LoRa.json:**
         ```
         {
             "name": "G",
             "chunk_size": 235,
             "mesh_mode": false,
             "debug": true,

             "connector": {
                 "sf": 7,
                 "freq": 868,
                 "min_timeout": 0.5,
                 "max_timeout": 12
                 },

             "interface": {
                 "ssid": "AlLoRa_wifi",
                 "psw": "AlLoRa_psw",
                 "host": "192.168.4.1",
                 "port": 80,
                 "ip" : "192.168.0.16",
                 "subnet_mask" : "255.255.255.0",
                 "gateway" : "192.168.1.10",
                 "DNS_server" : "8.8.8.8"
                 }
             }
         ```
       - **main.py:**
         ```
         from AlLoRa.Nodes.Adapter import Adapter
         from AlLoRa.Connectors.LoPy4_connector import LoPy4_connector
         from AlLoRa.Interfaces.Wifi_client import WiFi_Client_Interface

         if __name__ == "__main__":
             lora_adapter = Adapter(LoPy4_connector(), WiFi_Client_Interface())
             lora_adapter.run()
         ```
     - **WiFi-Hotspot:**
       - **LoRa.json:**
         ```
         {
             "name": "G",
             "chunk_size": 235,
             "mesh_mode": false,
             "debug": true,

             "connector": {
                 "sf": 7,
                 "freq": 868,
                 "min_timeout": 0.5,
                 "max_timeout": 12
                 },

             "interface": {
                 "ssid": "AlLoRa",
                 "psw": "AlLoRa_psw",
                 "host": "192.168.4.1",
                 "port": 80
                 }
             }
         ```
       - **main.py:**
         ```
         from AlLoRa.Nodes.Adapter import Adapter
         from AlLoRa.Connectors.LoPy4_connector import LoPy4_connector
         from AlLoRa.Interfaces.Wifi_hotspot import WiFi_Hotspot_Interface

         if __name__ == "__main__":
             lora_adapter = Adapter(LoPy4_connector(), WiFi_Hotspot_Interface())
             lora_adapter.run()
         ```

2. **ESP32 Examples:**
   - **LoRa.json:**
     ```
     {
         "name": "T",
         "chunk_size": 235,
         "mesh_mode": false,
         "debug": true,
     
         "connector": {
         "sf": 7,
         "freq": 868,
         "min_timeout": 0.5,
         "max_timeout": 12
         }
     }
     ```
   - **main_Heltec.py:**
     ```
     from AlLoRa.Nodes.Source import Source
     from AlLoRa.Connectors.SX127x_connector import SX127x_connector
     from AlLoRa.File import CTP_File

     from time import sleep
     import micropython
     import gc

     gc.enable()

     # For testing
     sizes = [1, 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024]	#, 1024
     file_counter = 0

     def clean_timing_file():
         test_log = open('log.txt', "wb")
         test_log.write("")
         test_log.close()

     if __name__ == "__main__":
         # First, we set the connector (basyc LoRa-LoPy connection to access to the LoPy's LoRa libraries)
         connector = SX127x_connector()

         # Then, we set up out Sender Node, giving it the connector and the path for the configuration file
         lora_node = Source(connector, config_file = "LoRa.json")

         chunk_size = lora_node.get_chunk_size()		# We use it to create the files to be sent...

         try:
             clean_timing_file()
             #show_in_screen(screen, "Waiting", '-')
             backup = lora_node.establish_connection()
             #print("Connected!")
             #show_in_screen(screen, "Connected!", '-')

             # This is how to handle a backup file if needed (not implemented in this example...)
             if backup:
                 print("Asking backup")
                 #file = Datasource.get_backup()
                 #lora_node.restore_file(file)

             # with an established connection, we start sending data periodically
             while True:
                 if not lora_node.got_file():
                     gc.collect()
                     n = file_counter % len(sizes)
                     file_counter += 1
                     size = sizes[n]
                     print("Setting file")

                     file = CTP_File(name = '{}.json'.format(size),
                                     content = bytearray('{}'.format(n%10)*(1024 * size)),
                                     chunk_size=chunk_size)
                     lora_node.set_file(file)

                     print("New file set, ", file.get_name())
                     #show_in_screen(screen, file.get_name(), file.get_length())

                 lora_node.send_file()

         except KeyboardInterrupt as e:
             print("THREAD_EXIT")
     ```

3. **RaspberryGateway:**
   - **Serial_Gateway:**
     - **LoRa.json:**
       ```
       {
           "name": "G",
           "debug": false,
           "mesh_mode": false,
           "chunk_size": 235,
           "connector":{
           "freq": 868,
           "sf": 7,
           "min_timeout": 0.5,
           "max_timeout": 12}
       }
       ```
     - **Nodes.json:**
       ```
       [ 
           {
           "name": "A",
           "mac_address": "9a76ba3f",
           "sleep_mesh" : false,
           "active": false
           },
           {
           "name": "B",
           "mac_address": "93a5bb9c",
           "sleep_mesh" : true,
           "active": false
           },
           {
           "name": "CAM",
           "mac_address": "bd462e74",
           "sleep_mesh" : true,
           "active": true
           }
       
       ]
       ```
     - **main.py:**
       ```
       # Main for Gateway Side AlLoRa
       # HW: Raspberry Pi + TTGO Adapter

       import  sys, gc
       from AlLoRa.Nodes.Gateway import Gateway
       from AlLoRa.Connectors.Serial_connector import Serial_connector


       if __name__ == "__main__":
           connector = Serial_connector(serial_port = '/dev/ttyACM0', baud= '115200', timeout=1)
           allora_gateway = Gateway(connector, config_file= "LoRa.json", debug_hops= False, TIME_PER_ENDPOINT=10)

           # Listen to the digital_endpoints and print and save the files as they come in
           allora_gateway.check_digital_endpoints(print_file_content = True, save_files = True)
       ```
```