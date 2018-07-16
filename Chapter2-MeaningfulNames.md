Use Intention-Revealing Names
  - Name of variable, function, or class should tell you why it exists, what it does, and how it is used.
    - DONT:
    ```typescript
      let d: number; // elapsed time in days 
    ```
    - DO:
    ```typescript
      let elapsedTimeInDays: number;
      let daysSinceCreation: number;
    ```
  - Be more explicit
    - DONT:
    ```typescript
      public getThem(): Array<number> {
        let list1: number[] = [];
        for(let i = 0; i < theList.length; i++) {
          list1.push(i);
        };
        return list1;
      }
    ```
    - DO:
      ```typescript
      public getFlaggedCell(): Array<Cell> {
        let flaggedCells: Array<Cell> = [];
        for(let cell = 0; cell < gameBoard.length; cell++) {
          if(cell.isFlagged()) {
            flaggedCells.push(cell);
          }
        }
        return flaggedCell;
      }
      ```

Avoid Disinformation
  - Avoid leaving false clues that obscure meaning of code.
    - DONT:
      Referring a grouping of accounts as an AccountArray when the grouping isn't actually an array
    - DO:
      Refer to them as accountGroup, bunchOfAccounts, or accounts
  - Beware of names which vary in small ways.
    - Ex:
      XYZControllerForEfficientHandlingOfStrings
      XYZControllerForEfficientStorageOfStrings

Make Meaningful Distinctions
  - Number-series naming (a1, a2, ... aN) are noninformative, provide no clue to author's intentions and should be avoided
    - DONT:
    ```typescript
      public static 
    ```


    
  