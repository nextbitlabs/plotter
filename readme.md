Plotter
-------

## Schema

The schema is inspired by D3 and it is designed with the following goals in mind:

* The data model should describe a list of one or more of states.
* Each state describes one or more visual elements, like lines and points. Elements are useful to draw one or more mathematical functions, possibly with included (or excluded) points and labels.
* Elements are identified by ids, so that we can recognize the same element on different states and trigger transitions if needed. We may use the enter/update/exit pattern.

```
// a list of states
[
	{...},
	...
]
```

Each `state` has the following structure:

```
{
	id: "state1", // State id, optional
	description: "" // State description, optional
	xInterval: [0, 1],
	yInterval: [0, 1],
	elements: [ // The order of elements determines the stack.
		{
			id: "e1" // Element id
			type: "line", // Element type
			data: [
				{
					x: 0.1,
					y: 0.3
				},
				...
			],
		},
		{
			id: "e2"
			type: "points",
			data: [
				{
					x: 0.2,
					y: 0.4,
					label: "a label", // Optional
					included: false // Optional, defaults to true
				},
				...
			]
		},
		...
	]
}
```