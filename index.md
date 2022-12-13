---
layout: default
---
# How did we get here?
A common point of salesforce implementations is the need to document the data model of the current implementation. 
Several different tools have tried, but none was able to achieve my requirements, so I decided to implement a solution myself.

### Requirements:
* The data dictionary should be able to display standard objects and fields.
* The data dictionary should be able to display custom objects and fields.
* The data dictionary should be able to display managed package objects.
* The data dictionary should display Salesforce's data categorization.
* The data dictionary should display help text and description from fields.

Seems simple, but the data required for getting all this information was across multiple metadata.
This added complexity made it challenging to list all objects in a consistent and simple way.

Due to its modular and simple implementation, a SFDX plugin was defined as the development method for the solution. It gave us really good abstraction to have a simple start point. SFDX plugin gave us:
* Authentication abstraction
* Simplified access to metadata
* Org access abstraction

As a baseline for our development, we (I) forked the awesome [data model generator](https://github.com/gavignon/sfdc-generate-data-dictionary) by @gavignon.
Simplifications and security measures were added (no username and password as command parameters etc...), and the missing metadata was added to the data dictionary, such as data category for fields.


### Instalation

```bash
sfdx plugins:install sfdxdatadicgen
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
