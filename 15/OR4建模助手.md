### GPT名称：OR4建模助手
[访问链接](https://chat.openai.com/g/g-ghT8oVfIC)
## 简介：以清晰的步骤逐步解释PDF示例
![头像](../imgs/g-ghT8oVfIC.png)
```text

1. OPERATIONS RESEARCH MODELING APPLICATIONS

2. Lecture 4: Multi-Objective Modeling

3. Sonya Javadi

4. Işık University-Fall 2023

5. Outline

6. 1. Multi-Objective Modeling
    • Multi-Objective Problems
    • Goal Programming

7. 2. Transforming Infeasible Solutions to Satisfactory Solutions

8. 3. Single to Multiple Objectives

9. Multi-Objective Problems

10. Multi-Objective Problems

11. • Nowadays having only one objective or goal to achieve is not enough to survive in a continuously changing business environment.

12. • There are usually many simultaneous however conflicting goals.

13. • It is difficult to obtain explicit statements for goals.

14. Example: For a profit making firm in addition to making money the company wants to:
    • grow
    • develop its products and its employees
    • provide job security for its workers
    • serve the community.

15. 2 / 31

16. Multi-Objective Problems

17. Example: For a logistics company in addition to meet customer demand the company wants to:
    • reduce costs
    • achieve a sustainable competitive advantage
    • increase service effectiveness.

18. 3 / 31

19. Multi-Objective Problems

20. Example: A Production Planning Problem

21. A manufacturing facility has received a production order of 300 units that must be supplied within a week.

22. Two production lines are available each for 25 hours per week.
    • Production line A can produce 5 units per hour.
    • Using production line B it takes 15 min to produce each unit.

23. Line A costs $8 and line B costs $11 per unit to process.

24. Overtime is available;
    • up to 30 h for line A at $10 per unit to process.
    • up to 30 h for line B at $12 per unit to process.

25. 4 / 31

26. Multi-Objective Problems

27. Example: A Production Planning Problem (cont’d)

28. The provided information is summarized in the following table.

29. The company wants to develop a production plan by minimizing the overall production cost and at the same time by maximizing the utilization of the regular working hours. For this problem we are going to start by defining sets.

30. 5 / 31

31. Multi-Objective Problems

32. Example: A Production Planning Problem (cont’d)

33. Sets:
    • Lines (i): A and B.
    • Production levels (j): Regular (R) overtime (O).

34. Decision Variables:
    • Xij: Number of units produced in line i in production level j.
    • i ∈ {A B} j ∈ {R O}

35. 6 / 31

36. Multi-Objective Problems

37. Example: A Production Planning Problem (cont’d)

38. • Decision Variables:
    • XAR: Number of units produced in line A during regular hours.
    • XAO: Number of units produced in line A during overtime hours.
    • XBR: Number of units produced in line B during regular hours.
    • XB0: Number of units produced in line B during overtime hours.

39. • Objective Functions:
    • Objective Function 1: Minimization of the total cost.

40. min Z1 = 8XAR + 10XAO + 11XBR + 12XBO

41. 7 / 31

42. Multi-Objective Problems

43. • Objective Function 2: Maximizing the utilization (the total usage) of regular working hours.

44. 1 1 max Z2 = 5 XAR + 4 XBR

45. 8 / 31

46. Multi-Objective Problems

47. Example: A Production Planning Problem (cont’d)

48. • Constraints:
    • Production requirement: Exactly 300 units must be produced.

49. XAR + XAO + XBR + XBO = 300

50. • Hour limitations:
    • Line A regular: 1 5 XAR ≤ 25
    • Line B overtime: 1 4 XBR ≤ 25
    • Line A regular: 1 5 XAO ≤ 30
    • Line B overtime: 1 4 XBO ≤ 30
    • Non-negativity: XAR XA0 XBR XBO ≥ 0

51. 9 / 31

52. Multi-Objective Problems

53. Example: A Production Planning Problem (cont’d)

54. The overall mathematical model is an LP model with two objectives.

55. min max s.t. Z1 = 8XAR + 10XAO + 11XBR + 12XBO Z2 = 1 5 XAR + 1 4 XBR XAR + XA0 + XBR + XBO = 300 1 5 XAR ≤ 25 1 4 XBR ≤ 25 1 5 XAO ≤ 30 1 4 XBO ≤ 30 XAR XA0 XBR XBO ≥ 0

56. The above model can be reformulated through goal programming.

57. 10 / 31

58. Multi-Objective Problems

59. Objective vs. Goal

60. In mathematical modeling an objective is represented by a function which is to be either maximized or minimized.
    • Maximization of total profit max Z = 3X1 + 5X2

61. However a goal indicates a target value for a function.
    • We define a target profit and try to make 3X1 + 5X2 as close to the target as possible while still satisfying all constraints.

62. Goals are introduced to the model as goal constraints.
    • Goal constraints can be violated with certain penalties set by the decision makers.
    • Goal constraints are also known as soft constraints.

63. 11 / 31

64. Multi-Objective Problems

65. Goal Programming

66. • The components of any goal programming (GP) model are:
    • Decision variables
    • Deviational goal variables
    • System constraints: Hard constraints. No violation is allowed.
    • Goal constraints: Soft constraints violation is allowed with penalty.
    • Objective function: The weighted sum of the undesirable violations in soft constraints.
    • A goal programming model can be either a linear integer or non-linear model.
    • In a single model there may be multiple goals.

67. A specific numeric goal is established for each goal function (constraint). We seek a solution that minimizes the weighted sum of deviations of these goal functions from their respective goals.

68. 12 / 31

69. Multi-Objective Problems

70. Types of Goals

71. There are three types of goals in goal programming:
    • A lower one-sided goal sets a lower limit that we do not want to fall under (but exceeding the limit is fine).
    • An upper one-sided goal sets an upper limit that we do not want to exceed (but falling under the limit is fine).
    • A two-sided goal sets a specific target range that we do not want to fall outside.

72. 13 / 31

73. Multi-Objective Problems

74. Example: A Production Planning Problem

75. Consider the previous production planning problem.

76. Suppose the company has set:
    • a maximal target of $ 3000 for the overall production cost
    • a minimal target of 37.5 hours for the utilization of the regular working hours total in both lines.

77. 14 / 31

78. Multi-Objective Problems

79. Although the company expects to achieve the target values some deviations may be allowed under certain conditions.
    • Sets: Same as before.
    • Decision Variables: Same as before.
    • System Constraints: Same as before.

80. 15 / 31

81. Multi-Objective Problems

82. Example: A Production Planning Problem (cont’d)

83. Deviational Variables:
    • d+1: Overachievement deviation of production cost target.
    • d−1: Underachievement deviation of production cost target.
    • d+2: Overachievement deviation of regular working hours target.
    • d−2 Underachievement deviation of regular working hours target.

84. Goal Constraints:
    • The production cost goal is an upper one-sided goal that the company does not want to exceed.

85. 8XAR + 10XAO + 11XBR + 12XBO − d−1 + d−1 = 3000

86. 16 / 31

87. Multi-Objective Problems

88. • Similarly the regular production hour target is a lower one-sided goal that the company does not want to fall below.

89. 1 5 XAR + 1 4 XBR − d−2 + d−1 = 37.5

90. 17 / 31

91. Multi-Objective Problems

92. Example: A Production Planning Problem (cont’d)

93. Objective Function: The objective function of a GP model is always to minimize the weighted sum of the undesirable deviations.
    • In the production cost goal constraint the over achievement deviation (d+1) is undesirable.
    • In the regular production hour goal constraint the underachievement deviation (d−2) is undesirable.

94. We want to minimize the weighted sum of these two variables.
    • Weights can introduce the importance of one deviation as compared to the other.
    • Both weights should be non-negative.

95. 18 / 31

96. Multi-Objective Problems

97. Say these weights are w1 and w2 respectively. The objective function becomes:

98. min Z = w1d+1 + w2d+2

99. 19 / 31

100. Multi-Objective Problems

101. Example: A Production Planning Problem (cont’d)

102. The overall GP model becomes.

103. 20 / 31

104. Transforming Infeasible Solutions to Satisfactory Solutions

105. Transforming Infeasible Solutions to Satisfactory Solutions

106. A mathematical programming model can be infeasible for many reasons:
    • wrong formulation
    • wrong data
    • inconsistent/infeasible constraints.
    However if the problem is infeasible by its nature it is impossible to obtain a feasible solution to the problem.

107. In that case we can transform this model into a GP model to obtain satisfactory solutions.

108. 21 / 31

109. Transforming Infeasible Solutions to Satisfactory Solutions

110. Example: A Product-Mix Problem

111. Consider the following LP problem that maximizes the profit generated from producing four products.

112. There are three technological constraints along with available cash and working capital constraints.

113. The optimal solution of the above problem is:

114. x∗ = (21.44 28.55 0 150)′ Z∗ = 20948

115. 22 / 31

116. Transforming Infeasible Solutions to Satisfactory Solutions

117. Example: A Product-Mix Problem (cont’d)

118. Later it is realized that the available cash requirement should have been increased from $67000 to $72000.
    • The new constraint is 168x1 + 288x2 + 288x3 + 391x4 ≥ 72000.
    • Now there is no feasible solution for this LP model.
    • The RHS of this constraint should be reduced.

119. Instead we will develop a negotiated production plan through goal programming to meet the financial plan.
    • Technological constraints will be considered as hard constraints.
    • Cash constraints will be considered as soft constraints.
    • Objective profit will also be a soft constraint. The profit goal will be 23000 slightly higher than the previous optimal objective value.

120. 23 / 31

121. Transforming Infeasible Solutions to Satisfactory Solutions

122. Example: A Product-Mix Problem (cont’d)

123. Deviational Variables: All deviational variables are measured in dollars.
    • d+1: Overachievement deviation of available cash target.
    • d−1: Underachievement deviation of available cash target.
    • d+2: Overachievement deviation of working capital target.
    • d−2 Underachievement deviation of working capital target.
    • d+3: Overachievement deviation of profit target.
    • d−3: Overachievement deviation of profit target.

124. 24 / 31

125. Transforming Infeasible Solutions to Satisfactory Solutions

126. Example: A Product-Mix Problem (cont’d)

127. Goal Constraints:
    The available cash goal is a lower one-sided goal that the company does not want to fall below.

128. 168x1 + 288x2 + 288x3 + 391x4 − d+1 + d−1 = 72000

129. The working capital goal is also a lower one-sided goal that the company does not want to fall below.

130. 150x1 + 80x2 + 86x3 + 70x4 − d+2 + d−2 = 16000

131. The profit goal is also a lower one-sided goal that the company does not want to fall below.

132. 112x1 + 162x2 + 192x3 + 89x4 − d+3 + d−3 = 23000

133. 25 / 31

134. Transforming Infeasible Solutions to Satisfactory Solutions

135. Objective Function: Undesirable deviations are d−1 d−2 and d−3.

136. min Z = w1d−1 + w2d−2 + w3d−3

137. 26 / 31

138. Transforming Infeasible Solutions to Satisfactory Solutions

139. Example: A Product-Mix Problem (cont’d)

140. The overall GP model becomes:

141. 27 / 31

142. Single to Multiple Objectives

143. Single to Multiple Objectives

144. Goal programming forms a single objective optimization model where the objective is to minimize the weighted sum of all undesirable deviations.
    • In the product-mix example a negotiated production plan was perceived in order to meet the financial plan that meant a compromise between profit available cash and working capital.
    In other words the objective was to indirectly maximize the profit available cash and working capital.
    • There are three objectives here.

145. 28 / 31

146. Single to Multiple
```