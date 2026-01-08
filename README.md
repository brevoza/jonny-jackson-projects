This will store my portfolio project data.

Each project has a title, description, coverImage, and body (markdown).


Brevoza will search this git repo for a `brevoza.config.yml` file, then see what collections are defined. In this case, it's just the `projects` collection, who's config file is located at `projects-config.yml`.

```
collections:
  projects:
    config: projects-config.yml
```


Then, brevoza will find the collection's config file to see it's schema.  
**projects-config.yml**:
```
collection: projects
description: >
  Jonny Jacksons portfolio projects

storage:
  path: projects/
  format: json
  idField: id

schema:
  type: object
  required:
    - id
    - title

  properties:
    id:
      type: string
      description: Unique slug identifier

    title:
      type: string

    description:
      type: string

    coverImage:
      type: image

    body:
      type: markdown
```

As you can see, each project has a title (string), description (string), coverImage (image), and body (markdown).  
And because of this:
```
storage:
  path: projects/
  format: json
```

We know that each project is stored as a **json** file in the `projects/` directory.