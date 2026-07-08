# Cleaning Log

Overall, the data provided by `titanic.csv` was well conditioned, requiring minimal cleaning beyond category classification, as described in `notebook.ipynb` as well as below.

## Removed Features

The `PassengerId` and `Name` columns were removed for being too idiosyncratic, and therefore poor for model training. Similarly, the `Ticket`, `Fare`, and `Cabin` features were all dropped for nearly perfectly mirroring the `Pclass` feature in meaning; ticket numbers all reference class number, as does the relative magnitude of each fare, while only first-class passengers were assigned cabins. All other features were kept, with some modifications.

## Modified

The `Sex` feature was trivially converted into a Boolean expression, while the `Pclass`, `SibSp`, and `Parch` fields were kept as-is. The `Age` and `Embarked` fields were encoded, with the former being divided into children (aged < 18), adults, elderly (aged >= 55), and unknown, and the latter admitting a complete mapping, including unknown values. The final fields are as follows:

| Field | Meaning (what it represents) |
|---|---|
| Survived | Whether the person survived (0 = No, 1 = Yes) |
| Pclass | Passenger class (1 = 1st, 2 = 2nd, 3 = 3rd) |
| Sex | Passenger sex (0 = male, 1 = female) |
| Age | Age category (0 = unknown, 1 = child, 2 = adult, 3 = senior) |
| SibSp | Number of siblings/spouses aboard |
| Parch | Number of parents/children aboard |
| Embarked | Port of embarkation (0 = unknown, 1 = Southampton, England, 2 = Cherbourg, France, 3 = Queenstown, Ireland) |
