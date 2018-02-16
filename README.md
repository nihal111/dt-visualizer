# dt-visualizer

## Decision Tree Visualizer

A visualizer to convert a tree in json format to a graphical representation of a tree using D3.js.

Open the website- [https://nihal111.github.io/dt-visualizer/](https://nihal111.github.io/dt-visualizer/).

## Usage

### See how it works
To simply see how it works, pull up [this website](https://nihal111.github.io/dt-visualizer/), leave the text areas empty and hit the "Load Sample" button.

### Use your JSON
To use it, open the [website](https://nihal111.github.io/dt-visualizer/) and enter your JSON in the larger text area. In the smaller text area, enter the keys/fields of the JSON you are interested in printing at your nodes. This should be a comma separated list, like- `condition, attribute, divide, answer`.

## My JSON schema
A sample json file can be found [here](/json_tree.json).
Each node forms a json object having fields-
- **attribute**: For all parent nodes. Contains children with 
- **children**: json array of all children nodes
- **condition**: For every child node, value of attribute of parent node.
- **divide**: For features having continuous distribution. Divide marks the point of division for binary classification.  
	Child nodes having `condition=1` will have values greater than divide.  
	Child nodes having `condition=0` will have values lesser than divide.
- **answer**: For all leaf nodes, final classification answer.

Here is a tree with `depth` = 2.

#### JSON
```
{
  "attribute": "floors", 
  "children": [
    {
      "attribute": "view", 
      "children": [
        {
          "answer": 1, 
          "condition": 0
        }, 
        {
          "answer": 2, 
          "condition": 1
        }, 
        {
          "answer": 2, 
          "condition": 2
        }, 
        {
          "answer": 2, 
          "condition": 3
        }, 
        {
          "answer": 2, 
          "condition": 4
        }, 
        {
          "answer": 1
        }
      ], 
      "condition": 1
    },
    {
      "answer": 1
    }
  ]
}
```

#### Fields
`condition, attribute, divide, answer`

---
This was created during a CS-419M (Introduction to Machine Learning) assignment.  
**Courtesy:** Forked from [Mike Bostock](https://bl.ocks.org/mbostock/4339083) with a few modifications.