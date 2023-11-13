# Dapple

Dapple is an attempt at providing a unified workflow for three DPL projects:

- [Design system](https://github.com/danskernesdigitalebibliotek/dpl-design-system)
- [React components](https://github.com/danskernesdigitalebibliotek/dpl-react)
- [CMS]((https://github.com/danskernesdigitalebibliotek/dpl-cms))

These projects recide in separate repositories but are used by one another to 
provide a complete application. While there is an established workflow for
implementing changes which span multiple repositories, some processes may
result in much back and forth between the individual parts. This can become
both slow and complex.

Dapple tries to achieve the following goals:

1. Make changes in one project propagate to the others automatically
2. Propagate changes quickly
3. Do not change the current structure of the projects

Dapple attempts to solve this by creating a working environment containing all
three projects with direct links between each of them.

## Prerequisites

- [Docker Compose](https://docs.docker.com/compose/install/)
- [Task](https://taskfile.dev/#/installation)
- Prerequisites required by the individual projects.

## Installation

1. Clone this repository
2. Run `task init` to initialize the working environment

## Example usage

### React component development

1. Run `task dev:react --watch` to start the development environment
2. See that Storybook for the React components are opened in a browser
3. Make a change in the local `design-system` project
4. See that the change triggers a build of the design system
5. See the change is reflected in the Storybook browser window

### CMS development

1. Run `task dev:cms-react --watch` to start the development environment
2. Open a browser to see the CMS installation
3. Make a change in the local `design-system` project
4. See that the change triggers a build of the design system
5. See that the change causes the CMS cache to be cleared
6. Reload the browser to see the change reflected in the CMS
7. Make a change in the local `react` project
8. See that the change triggers a build of the React components
9. See that the change causes the CMS cache to be cleared
10. Reload the browser to see the change reflected in the CMS