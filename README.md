# FRINX javascript style guide

We follow [Airbnb javascript styleguide](https://github.com/airbnb/javascript). This guide extends and/or overrides it, so it takes precedence.

Packages also follow the airbnb naming convention:

- @frinx/eslint-config-frinx-typescript
  - TBA
- @frinx/eslint-config-frinx-typescript-base
  - TBA

## Booleans

If a property or variable is a boolean, or function returns boolean, use is, has, can or should prefix. (Accessors - Booleans)

```typescript
// bad
if (dragon.age()) {
  return false;
}
let good = false;
let sign = false;
let closeDocument = true;

// good
if (dragon.hasAge()) {
  return false;
}
let isGood = false;
let canSign = false;
let shouldCloseDocument = true;
```

## Common variable names

To consistently write certain variable names, we use these rules:

- if the name is an acronym, like `URL` comes from `Uniform Resource Locator`, we write it lowercase when it is alone, and all uppercase when part of a longer name
- if the name is an abbreviation of a longer word, like `id` (from `identifier`) or `src` (from `source`), we write it lowercase when it is alone, and camel case when part of a longer name

### Examples:

```typescript
const url = "x";
const imageURL = "x";
const id = "x";
const imageId = "x";
const src = "x";
const imgSrc = "x";
```

## Images in React components

Images are in a /img subfolder, has size suffix in its name, and imported into React component as a constant with image type suffix (Png, Svg, Jpg, ...).

```typescript
// bad
import organization from "./organization.png";
import phone from "../../common/phone.svg";

// good
import organizationPng from "./img/organization-24x24.png";
import phoneSvg from "./img/phone.svg";
```

## React event handler naming

The handler functions should be named of the form handle*, for example handleClick or handleStart. When sent as props to a component, the property-keys should be named of the form on*, for example onClick or onStart. example:

```typescript
const Activator: FC<ActivatorProps> = (props) => {
  return <button onClick={this.props.onActivation}>Activate</button>;
};

const Thing: FC<ThingProps> = (props) => {
  const [isActive, setActive] = useState(false);

  function handleActivation() {
    setActive(true);
  }

  return (
    <div>
      Thing is {isActive ? "Active" : "Inactive"}
      <Activator onActivation={handleActivation} />
    </div>
  );
};
```

## Files and folders naming conventions

Project structure is driven by [LIFT Principle](https://github.com/johnpapa/angular-styleguide/tree/master/a1#application-structure-lift-principle). Folder structure is organized with approach “folders-by-feature”, not “folders-by-type”

```
/save-file-dialog
|-- save-file-dialog.helpers.ts
|-- save-file-dialog.helpers.spec.ts
|-- save-file-dialog.tsx
```

Test file has the same name, as the tested unit, with “.spec.ts” suffix. Test file is in the same folder as the tested code.

```
/save-file-dialog
|-- save-file-dialog.helpers.ts
|-- save-file-dialog.helpers.spec.ts
```

Images are in the /img sub-folder of the component, in folder.

```
/button
|-- /img
|   |-- icon-24x24.png
|
|-- button.tsx
```

## Renaming/moving files

NEVER EVER rename a file, by just changing capitalization. Seriously, NEVER !

$ # BAD - NEVER DO THIS
$ mv my-Source-Code-File.js my-source-code-file.js
If you desperately need to do it, you have to do it in 3 steps:

```bash
# STEP 1 - rename file by adding postfix

$ mv my-Source-Code-File.js my-source-code-file-ex.js

# STEP 2 - wait until change spreads into all open branches - this may take several weeks

# STEP 3 - rename file by removing postfix

$ mv my-source-code-file-ex.js my-source-code-file.js
```

## GIT Renaming and/or moving files

To help git track changed files, never rename a file and change its content in one commit.

```bash
# BAD
$ mv my-file.ts my-changed-name.ts
# change content of my-changed-name.ts file
$ git commit
```

```bash
# GOOD
$ mv my-file.ts my-changed-name.ts
$ git commit
# change content of my-changed-name.ts file
$ git commit
```
