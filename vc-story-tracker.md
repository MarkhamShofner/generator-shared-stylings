**As a user (developer) I can download and use a scaffolding tool so that I can generate a hub-ready app, in terms of shared styling**

### Concept
The idea is to create an extended 'app template' that streamlines the app creation process for developers. The user will be able to run some sort of scaffolding tool (e.g. yeoman), some sort of build tool (e.g. Grunt or Gulp), and some sort of package manager (e.g. Bower and npm) to quickly generate and integrate a child 'app template' that consumes and applies the shared styling concepts of a parent app. The application will also be served to a locally hosted location (for the meantime).

Providing a scaffolding mechanism to users (specifically developers) will decrease the requisite start-up time to create an app. Moving from zero to a hub-ready will take less time, require less research, and likely increase the quantity and quality of applications for users to interact with.

##### Clarification on Hub-Ready apps
See https://github.com/ArcGIS/Hub and https://github.com/ArcGIS/Hub/blob/master/specification.md.
For now, this story aims to facilitate the incorporation of the "shared style" portion of hub-ready apps. Other major components of hub-ready apps (that can be addressed down the line in other stories) include:
- Schema matching
- Link apps to data
- Category Ontology
- Item Listing
- Structured License
- etc...

##### User Flow
![scaffolding draft - hub-ready apps 2](https://cloud.githubusercontent.com/assets/14302394/15297270/20f37a0c-1b67-11e6-8f6d-409221f26e9f.png)

### Acceptance Criteria

- User can download the scaffolding tool (either a zip file from a site, or through npm)
- User can then run a command (e.g. 'yo hub-app'), which creates a series of files and actions
- These files and actions work in concert to generate a website that is served to a local address
- The website is viewable in a browser locally, and page components mirror the (to be determined) requirements for the shared styling of a hub-ready app
  - Specifically, shared styling between the parent and child sites can be validated (i.e. specific components of the page mirror styling)

### Design

- [ ] Determine eventual path for users to be able to discover and download the tool
  - Potential options - zip file link on parent site, npm install (the shortcut to be used in this story)
  - For the sake of this story, implementing the discovery-mechanism is out of scope

### Technical

Description of the general things that need to be done.

- [ ] Research potential scaffolding tools, and determine which one to use
- [ ] Build draft scaffolding
  - [ ] Boilerplate page(s) in html. Header, footer, nav info, and maybe some other DOM elements
  - [ ] Package.json and dependencies (Calcite bootstrap, node, general info, etc...)
  - [ ] Consume API and extract shared styling
  - [ ] Apply style information to the app user interface
- [ ] Publishing to npm


___

#### Comments Section, to be addressed
- Andrew -  ```Where will this capability code be served? GitHub or in our infrastructure or ?```
  - Markham - Currently I think it makes sense to run something similar to what Dave has done here (https://github.com/dbouwman/generator-demo-map) and have it live on GitHub for now. Public facing, similar to Dave's, makes sense as well.
- Brooks - ```This may be out of scope for this story, what's the overall criteria for "hub ready"?```
  - Markham - Here is a specification file written by Andrew that does a good job formalizing the idea. https://github.com/ArcGIS/Hub/blob/master/specification.md.
- Brooks - ```Is creating a hub ready app open to anyone or is it restricted to Orgs or some other type of account?```
  - Markham - I don't have enough contextual knowledge to make this call. Think either could make sense. I prefer anyone being able to make the apps, and then orgs could decide to include specific apps on their site if they want to.
- Brooks - ```What's in the package.json?```
  - Markham - file should contain information like dependencies, keywords, license, etc...
- Brooks - ```Can the page consume other APIs?```
  - Markham - Not sure what this one means. It's grabbing an API already, does it need to grab others? I assume we could build it to consumer multiple APIs, but for this story we just need one it seems.
