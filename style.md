This style guide outlines the conventions and best practices for writing and maintaining code in every TypeScript project of the code base.
1. Code Formatting
1.1 Prettier
Consistent Formatting: This project uses https://prettier.io/ for code formatting. Ensure that your code adheres to the Prettier configuration specified in the project.
Automatic Formatting: Set up your IDE/editor to format code automatically on save using Prettier to maintain consistent code style.
2. Naming Conventions
Everything should have a name that clearly describes their contents or purpose
2.1 File and Folder Names
camelCase: All file and folder names should be in camelCase. This applies to both TypeScript files and any other resources in the project.
  # Examples
  components/
  userProfile.ts

2.2 Variables, Functions, and Classes
camelCase for variables and functions: Use camelCase for naming variables and functions.
  let userName: string;
  function getUserInfo() { /* ... */ }

PascalCase for classes and interfaces: Use PascalCase for naming classes and interfaces.
  class UserProfile { /* ... */ }
  interface User { /* ... */ }


2.3 Comments on the code
Code should be clear enough to doesn't need any comment to understand it 
You can still add comments to give some insights
Comments should always be in English
Comments are recommended to leave a note on the code, for exemple:
// TODO @Valentin: check the code here

2.4 Best practice on Functions and files
Functions should do exactly one thing
Exported functions should be at the bottoms of the files
One file should have functions of only one scope (ex: snapshots handling should not be in the pickup file)
Lines length should not exceed 100 characters
3. TypeScript-Specific Guidelines
3.1 Type Annotations
Explicit Types: While adding return types to functions is not mandatory, it’s encouraged for public functions, APIs, and critical parts of the codebase.
  // Optional but encouraged
  function calculateTotal(price: number, tax: number): number {
      return price + tax;
  }

3.2 Avoid any
Type Safety: Avoid using the any type whenever possible. Prefer more specific types to maintain type safety and clarity.
  // Avoid
  let data: any;

  // Prefer
  let data: string | number;

3.3 Null and Undefined
Explicitly Handle null and undefined: Avoid assuming values will never be null or undefined. Handle these cases explicitly.
  function getUserName(user?: User): string {
      return user?.name ?? 'Guest';
  }

3.4 Optional Chaining and Nullish Coalescing
Use Modern JavaScript: Use optional chaining (`?.`) and nullish coalescing (`??`) operators where appropriate to simplify code.
  const userName = user?.name ?? 'Guest';


3.5 Looping and Iteration
Avoid .forEach: Do not use .forEach for iterating over arrays. Instead, prefer using for loops, .map(), or .reduce() for better performance and readability.
  // Avoid
  users.forEach(user => processUser(user));

  // Prefer
  for (const user of users) {
      processUser(user);
  }
  
  // Or when transforming data:
  const processedUsers = users.map(user => processUser(user));
  
  // Or when accumulating a result:
  const total = users.reduce((sum, user) => sum + user.score, 0);


3.6 Alternative Patterns
For Loops: Use for...of loops when simple iteration is needed.
.map(): Use .map() when transforming elements of an array into a new array.
.reduce(): Use .reduce() for accumulating or aggregating values from an array.

3.7 Function Documentation
Function Headers: All public functions, as well as complex private functions, should include a header comment. This comment should use JSDoc format to describe the function’s purpose, its parameters, and its return value.
  /**
   * Calculates the total price including tax.
   * 
   * @param price - The base price of the item.
   * @param tax - The tax amount to be added to the price.
   * @returns The total price including tax.
   */
  function calculateTotal(price: number, tax: number): number {
      return price + tax;
  }

/**
 * Retrieves an hotel based on its slug.
 
 * @param slug - The slug of the hotel.
 * @returns A promise that resolves to the hotel.
 * @throws {NotFoundError} if the hotel with the given slug doesn't exist.
 */
export async function getHotel(slug: string) {
    const result = await db.collection('hotels').findOne<Hotel>({ slug });
    
    if (!result) throw new NotFoundError(`hotel with slug: "${slug}" doesn't exists`);

    return result;
}

Further Reading: For more details on supported JSDoc types in TypeScript, refer to the https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html.

4. Commit Message Norms
4.1 Verb Prefixes
Structured Commit Messages: Use the following verb prefixes in square brackets at the beginning of commit messages to clearly indicate the nature of the change:
[ADD] for adding new features or files.
[CHG] for changes to existing functionality.
[FIX] for bug fixes.
[DEL] for deletions of code or files.
  # Examples
  [ADD] Implement user authentication
  [CHG] Update user profile UI
  [FIX] Resolve crash on login screen
  [DEL] Remove deprecated API endpoint


