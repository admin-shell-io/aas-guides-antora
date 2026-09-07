# Asset Administration Shell Guides

## How to add new guide document

### Step 1 **antora-playbook** 
In https://github.com/admin-shell-io/aas-guides-antora

**antora-playbook.yml** section **content:**: add new document with branches

Example:

```     
       - url: https://github.com/admin-shell-io/aas-guides
           branches:
           - main
             start_paths:
                 - HowToCreateSMT/docs
                 - HowToCreateSMT/*/docs
``` 

It is possible to use wildcards to include all versions of the document.

### Step 2 **update navigation** 
In https://github.com/admin-shell-io/aas-guides-antora

- `modules\ROOT\nav.adoc`, update `nav.adoc`

Example:

```   
* xref:HowToCreateSMT:ROOT:imprint.adoc[How-To create SMT]
```

The name in square brackets will be used in the menue top left.

### Step 3 **update overview page**
In https://github.com/admin-shell-io/aas-guides-antora 

- `modules\ROOT\pages`, update `index.adoc`


### Step A
in https://github.com/admin-shell-io/aas-guides

**antora.yml** of new document, must be in folder of the start paths as defined in antora-playbook (see Step 1)

``` 
name: HowTo_SMT
title: 'How-To Create a SMT'
version: '1.1'
display_version: '1.1 - in work'
start_page: ROOT:imprint.adoc
nav:
  - modules/ROOT/nav.adoc
``` 

The *title* will be used as text in the menue (bottom left) with all the verions of the document.

The *display_version* will be used in the menue (bottom left) as the name of the version.

The *version* will be used in the URL.

The *name* of all versions of the same document must be identical.
 
