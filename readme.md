Plotter
-------

## Schema

The following schema describes the data ingested by the web component. The keys `domain` and `range` define the x and y intervals visible on the chart. Key `functions` instead has an array of objects as value, each object describes a function. The function has a `name`, multiple functions may share the same `name` if they can be considered as an unique function definition. The function has also a `cssClass`, which is useful for adding style. Keys `line` and `point` both have an array of objects with a `coordinates` key describing the data. Data in `lines` will be visualized as a line; data in `points` will be visualized as a series of points (small circles), which may be empty or not depending on key `empty`.

```
{
  domain: [0, 1],
  range: [0, 1],
  functions: [
    {
      name: 'f1'
      line: [
        {
          coordinates: [0.5, 0,23]
        },
        {
          coordinates: [0.7, 0,33]
        },
        ...
      ],
      points: [
        {
          coordinates: [0.5, 0,23],
          empty: false
        },
        ...
      ]
    },
    ...
  ]
}
```