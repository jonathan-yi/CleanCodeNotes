# Meaningful Names - Chapter 2

### Use Intention-Revealing Names
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
  public getThem(): number[] {
    let list1: number[] = [];
    for(let i: number = 0; i < theList.length; i++) {
      list1.push(i);
    };
    return list1;
  }
  ```
  - DO:
  ```typescript
  public getFlaggedCell(): Cell[] {
    let flaggedCells: Array<Cell> = [];
    for(let cell: number = 0; cell < gameBoard.length; cell++) {
      if(cell.isFlagged()) {
        flaggedCells.push(cell);
      };
    };
    return flaggedCell;
  }
  ```

### Avoid Disinformation
- Avoid leaving false clues that obscure meaning of code.
  - DONT:
    - Referring a grouping of accounts as an AccountArray when the grouping isn't actually an array
  - DO:
    - Refer to them as accountGroup, bunchOfAccounts, or accounts
- Beware of names which vary in small ways.
  - Ex:
    - XYZControllerForEfficientHandlingOfStrings
    - XYZControllerForEfficientStorageOfStrings

### Make Meaningful Distinctions
- Number-series naming (a1, a2, ... aN) are noninformative, provide no clue to author's intentions and should be avoided
  - DONT:
  ```typescript
  public static copyChar(a1: string[], a2: string[]): void {
    for(let i: number = 0; i < a1.length; i++) {
      a2[i] = a1[i];
    };
  }
  ```
  - DO:
  ```typescript
  public static copyChar(source: string[], destination: string[]): void {
    for(let i: number = 0; i < source.length; i++) {
      destination[i] = source[i];
    };
  }
  ```
- Avoid noise words if they don't make meaningful distinction
  - DONT:
    - ProductInfo or ProductData
  - DO:
    - Product
- Avoid redundant noise words
  - DONT:
    - NameString
  - DO:
    - Name
- Distinguish names so readers know what the difference offers

### Use Pronounceable Names
- Pronounable Names
  - DONT:
  ```typescript
  public class DtaRcrd102 {
    private genymdhms: Date;
    private modymdhms: Date;
    private readonly pszqint: string = "102";
  }
  ```
  - DO:
  ```typescript
  public class Customer {
    private generationTimestamp: Date;
    private modificationTimestamp: Date;
    private readonly recordId: string = "102";
  }
  ```

### Use Searchable Names
- Single-letter names should ONLY be used as local variables inside short methods
- Variables or constants used in multiple places should be given a search-friendly name
- DONT:
```typescript
for (let j = 0; j < 34; j++) {
  s += (t[j]*4)/5;
};
```
-DO:
```typescript
const realDaysPerIdealDay: number = 4;
const WORK_DAYS_PER_WEEK: number = 5;
let sum: number = 0;
for (let j: number = 0; j < NUMBER_OF_TASKS; j++) {
  const realTaskDays: number = taskEstimate[j] * realDaysPerIdealDay;
  const realTaskWeeks: number = (realTaskDays / WORK_DAYS_PER_WEEK);
  sum += realTaskWeeks; 
};
```

### Avoid Encodings
- Encoding types or scope information into names adds extra burden of deciphering

### Member Prefixes
- Don't prefix member variables with m_ anymore. Unseen clutter and marker of older code
- DONT:
```typescript
public class Part {
  private m_dsc: string;
  private static setName(name: string): void {
    m_dsc = name;
  }
}
```
- DO:
```typescript
public class Part {
  private description: string;
  private static setName(description: string): void {
    this.description = description;
  }
}
```