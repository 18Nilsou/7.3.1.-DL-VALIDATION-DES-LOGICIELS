# Exercise 2 (Repo 1): Cyclomatic Complexity on a Key Method



**Class:** BankAccount  
**Method analyzed:** `withdrawMoney(double withdrawAmount)`

- **Cyclomatic Complexity (CC) from CK Metrics plugin:** 5
- **Weighted Methods per Class (WMC):** 20

### Decision Points in `withdrawMoney`

```java
public boolean withdrawMoney(double withdrawAmount) {
    if ( // Decision point : IF avec 4 condition
        withdrawAmount >= 0
        && balance >= withdrawAmount
        && withdrawAmount < withdrawLimit 
        && withdrawAmount + amountWithdrawn <= withdrawLimit
    ) { 
        balance = balance - withdrawAmount;
        success = true;
        amountWithdrawn += withdrawAmount;
    } else { 
        success = false;
    }
    return success;
}
```

### Refactoring Proposal

The main source of complexity is the compound condition in the `if` statement. To reduce complexity and improve readability/testability, extract this condition into a helper method.  
**Suggested helper name:** `isWithdrawMoneyAllowed(double withdrawAmount)`

This helper will encapsulate all the checks, making the main method easier to read and test.

### Refactored Code

```java
public boolean withdrawMoney(double withdrawAmount) {
    if (isWithdrawMoneyAllowed(withdrawAmount)) { 
        balance = balance - withdrawAmount;
        success = true;
        amountWithdrawn += withdrawAmount;
    } else { 
        success = false;
    }
    return success;
}

private boolean isWithdrawMoneyAllowed(double withdrawAmount) {
    return withdrawAmount >= 0
        && balance >= withdrawAmount
        && withdrawAmount + amountWithdrawn <= withdrawLimit;
}
```

**After refactoring:**  
- Cyclomatic Complexity for `withdrawMoney`: 2  
- Cyclomatic Complexity for `isWithdrawMoneyAllowed`: 4  
- The main method is now simpler and easier to test.
