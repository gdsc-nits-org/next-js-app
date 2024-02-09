# CONTRIBUTING.md

**Tools and Tech Stack: NextJS pages router, scss, mdx, pnpm, eslint, prettier, git**

**Project Structure**

- All React Components should be defined inside `components`.
- All Pages should be defined inside `pages`.
- Create a single directory for each component. For example, Button component should be inside `components/Button/Button.jsx`. All the styles related to that component should be declared as a [css module](https://medium.com/@ralph1786/using-css-modules-in-react-app-c2079eadbb87) inside the same directory. For example, styles related to Button component should be declared in `components/Button/Button.module.scss`.
- `components` has an `index.jsx` file. After creating your component, import and export your component from `index.jsx`. This simplifies importing Components in pages. For example, without an `index.jsx`, importing Button component would look like:
    
```jsx
import Button  from “./Components/Button/Button”
```

With the `index.jsx` file, it would be much cleaner:

```jsx    
import { Button }  from “./Components”
```

- Follow a similar pattern for Pages as well.
- Context Providers should go in `global/`

**Linting**

- **Install ESLint and Prettier extensions in VSCode**.
- Project uses ESLint. ***Do not try to bypass eslint errors**.
- See all the rules in `eslintrc.json`
- General rules to follow:
    - All Js files should be named in [camelCase](https://en.wikipedia.org/wiki/Camel_case)
    - All Jsx files should be named in PascalCase
        - camelCase (capitalize first letter from second word onwards)
        - PascalCase (capitalize first letter of all the words)
    - All directories inside src should be named in PascalCase.
    - React Components/Pages must be defined as [Javascript arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions).
- Not following any of the above rules will throw an error when committing your changes.
- Optional: After writing your code, you can use Prettier to format it.
    
    Ctrl/Cmd + Shift + p -> Format Document with… -> Prettier
    
    This step is done automatically by the pre-commit hook so it is not compulsory to do this step manually.
    

**Git Commits and Branches**

- Write proper git commit messages. Max 50 character title with a brief description below it.
- Try to use tags in commit titles. For example “[bugfix]” for a commit that fixes a bug, “[feat]” for a commit that adds a feature and so on…
- Keep the message brief and crisp.
- Example of good commit messages:
    
    ![](https://lh7-us.googleusercontent.com/bs7K3fwJOvkg3jLo-P1GFGwO1XNzwUpycMk8ucBjqj5GDvQDfSZDBEluhRmW0mCtOn16hrrgp952PFgqQu_3khV8vc4NDTMrhpIypBg806yTFsjjK3fCDFeerSCb6hWnwJdSX7NaK6KyJ1_C83NqwdY)
    
- Before working on something(features/bugs etc), general rule:
    - Pull from origin/main (git pull origin main)
    - Create a branch from the main branch.
- Branch names should be small but descriptive of what the branch is doing. For example, if you are creating the landing page, give a branch name like `landing-page`.

**Miscellaneous**

- Write clean and maintainable code. Use comments if necessary; for example, the structure in which a component takes props.
- If facing problems(like long stalling/failure to authenticate) with git network commands(clone/pull/push/fetch etc).
    
    Fix(use any one):
    
    - Use *Github Pull Request and Issues* Vscode extension, and then authenticate with your Github account through browser. This will make those commands work only through your Vscode terminal.
    - Install [Git Credential Manager](https://github.com/GitCredentialManager/git-credential-manager). Authenticate to your Github account through the browser/popup. This will make the commands work from any terminal.
    

### Working on components

- Create a separate branch for your component in git. Push to github and put a PR to the `home` branch. This branch will be used for integration.
- Initially put a pr with a `don't-merge` tag. After the feature is complete remove the tag and/or replace with other available appropriate tags then (like pls-merge).
- **Only work on your assigned feature. If any help is needed first google, rtfm (google its meaning), talk with the team members, and then contact seniors.**
- Do not touch the main branch. Push your changes only to your own branch. Those changes will be first merged in the home branch, and then the home branch will be merged to the dev branch, and then once the whole site is finished, does the dev branch get merged into the main branch.
- The branch names for pages should be of the form {pageName}-page, eg home-page, resource-page.
- Name the PR after the feature you are working on.

![](https://lh7-us.googleusercontent.com/s7SiKfGfPGniCoxET87XvGMi9rj2NxoMnm-WYp1MtJTRks0V8zaMtOZ-SyupTnwtlLW6uedOCJUh6x4REhMfL05k1xofXcMiRNyJoLaQRkfGz_orNnPmBFHySn25S7SIk1psuZLWt4O0TFtbaijMiZs)
*Pushing your branch*

![](https://lh7-us.googleusercontent.com/ZFHXqewq3AGbT-vZOmsNymj268fRTgKsOG6FNz3szZQZR08jkg5AQe39-Z1hpI8RJGiJevmxOJR2CnkX83WA1QS1vGboI42-ghhrYU8vQgg6wVBvkwKDvTh7JxMJc59t8b93507Z2iN1bRJfPk4RNGw)
*PR to home*

![](https://lh7-us.googleusercontent.com/phUWVK1ZrJd9Q39Hn5keS6GUenCRB40c4XR8cp4hqj1-W4wVsp2yQcqE3SXnyH6Z_0GGxsl-8oU29GIWLVIw8i7gqPxQ7NLgqGKlh09NvyTrHlgJRMrJ-HONXWBXK0UwkhrFG1NG-bLxwb-3j5E6lTA)
*Putting `dont-merge` tag`*

### Using css vars

- Define css variables for commonly used colours in global.css.
- So instead of copying and pasting the same hex codes over and over again, we can just use the vars.
- If any colour is changed due to some design change, we just have to make a change in the var, instead of everywhere.
- Reference code:

![](https://lh7-us.googleusercontent.com/mZKbOflU5Sj9jn2REIlKOpQ8fD-S2P5MwS5TJheL3NytUgc_ETMMSW4OnkkkUTdALqp8rbIWSGbYZVu18G_MwgxDBCUfX28Fw7ER7cz7z4BnyaIA9wxnVE5-ivKZd70hpQS9hTFOvStZTjZ0oswFaNs)

Further reading:

1. [A Complete Guide To CSS Variables [With Examples] | LambdaTest](https://www.lambdatest.com/blog/guide-to-css-variables-with-examples/)
2. [Using CSS custom properties (variables) - CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)

### Use iconify for icons

- Use [Iconify](https://iconify.design/) for icons. It is used by the designers as well, so the same specific icon can be used. (Package will be included in the repo, use it for icons).
- It supports tree shaking i.e. only used icons are built, and discarding the rest, keeping the build size to whatever you actually use.
