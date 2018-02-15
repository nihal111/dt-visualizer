# dt-visualizer

## Decision Tree Visualizer

A visualizer to convert a tree in json format to a graphical representation of a tree using D3.js.

Open the website- [https://nihal111.github.io/dt-visualizer/](https://nihal111.github.io/dt-visualizer/).

## Usage

A sample json file can be found [here](/json_tree.json).
Each node forms a json object having fields-
- attribute: For all parent nodes. Contains children with 
- children: json array of all children nodes
- condition: For every child node, value of attribute of parent node.
- divide: For features having continuous distribution. Divide marks the point of division for binary classification.  
	Child nodes having `condition=1` will have values greater than divide.  
	Child nodes having `condition=0` will have values lesser than divide.
- answer: For all leaf nodes, final classification answer.

Here is a tree with `depth` = 2
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

**Courtesy:** Forked from [Mike Bostock](https://bl.ocks.org/mbostock/4339083) with a few modifications.