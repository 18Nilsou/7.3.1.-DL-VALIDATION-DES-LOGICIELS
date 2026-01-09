# Exercise 3 (Repo 1): CK Metrics Across Classes: Who Looks “Smelly”?

| Classe                | WMC | CBO | LCOM |
|-----------------------|:---:|:---:|:----:|
| `Bank`                | 14  | 3   | 0    |
| `BankAccount`         | 21  | 2   | 46   |
| `Person`              | 23  | 0   | 79   |

Which class has the highest WMC?
> It is `Person`.

Which class has the highest CBO?
> It is `Bank`.

Looking at WMC + CBO + LCOM together. Which class would you worry about most for future maintenance, and why?
> It is `Person` because it has the highest WMC, which indicates a high level of complexity. It also has the highest LCOM, which means its methods are too numerous and/or have poor organization.