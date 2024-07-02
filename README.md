# Code Challenge

## 1) Introduction
The aim of this challenge is for the customer to write a constraint that will be embedded into a given template. The customer will engage with a chatbot to ask questions and add constraints, and the LLM model should respond quickly to create an accurate response.
#### Code Template
```python
from pyomo.environ import *

model = ConcreteModel()
model.x = Var(domain=NonNegativeReals)
model.y = Var(domain=NonNegativeReals)
model.obj = Objective(expr=2 * model.x + 3 * model.y, sense=maximize)

# Define constraints
model.constraint1 = Constraint(expr=model.x + 2 * model.y <= 8)
model.constraint2 = Constraint(expr=3 * model.x + 2 * model.y <= 12)

# Solve the model
solver = SolverFactory('glpk')
result = solver.solve(model)
```

### Input
We would like the user to provide a request in the following format:
"add a constraint of 2X + 6Y > 30 in our model."

### Output
The resulting code should be:
``` python
from pyomo.environ import *

model = ConcreteModel()
model.x = Var(domain=NonNegativeReals)
model.y = Var(domain=NonNegativeReals)
model.obj = Objective(expr=2 * model.x + 3 * model.y, sense=maximize)

# Define constraints
model.constraint1 = Constraint(expr=model.x + 2 * model.y <= 8)
model.constraint2 = Constraint(expr=3 * model.x + 2 * model.y <= 12)
model.constraint3 = Constraint(expr=2 * model.x + 6 * model.y > 30)

# Solve the model
solver = SolverFactory('glpk')
result = solver.solve(model)
```
## 2) Description
We need a report for the model selection, fine-tuning implementation, RAG or lang-chain model implementation, etc.


#### A) Details
if you go after fine-tuning, 
Fine-tune models using two methods: 
- PEFT (Parameter-Efficient Fine-Tuning) and prefix fine-tuning.
- Assess and document the performance of each fine-tuning technique on the chosen models.

if you go after RAG and lang-chain, 
- Share the database of RAGs and flowchart of lang-chain with us.

## Evaluation Metrics
- Evaluate the models using common evaluation metrics, ensuring a thorough and fair comparison.
  

### B) Deliverables for the Code Challenge

- Detailed Report: Provide a comprehensive report covering model selection, fine-tuning processes, evaluation metrics, and results.
- Code and Documentation: Include all code and documentation necessary to reproduce the experiments and results.
- Insights and Recommendations: Offer insights and recommendations on the best approach for generating Pyomo code based on your findings.

### C) Submission
- Please submit a GitHub link with your work and fork the repository for collaboration.
