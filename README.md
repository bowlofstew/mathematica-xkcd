# XKCD Charting Library

## Examples

### Standard Plot

```
f1[x_] := 5 + 50 (1 + Erf[x - 5]);
f2[x_] := 20 + 30 (1 - Erf[x - 5]);
xkcdConvert[Plot[{f1[x], f2[x]}, {x, 0, 10},
  Epilog -> 
   xkcdLabel /@ {{"Label 1", {1, f1[1]}, {1, 30}}, {"Label 2", {8, f2[8]}, {0, 30}}},
  Ticks -> {{{3.5, "1st Event"}, {7, "2nd Event"}}, Automatic}]]
```

### Bar Chart

```
xkcdConvert[BarChart[{10, 1}, ChartLabels -> {"XKCD", "Others"},
  PlotLabel -> "Popularity of questions on MMA.SE",
  Ticks -> {None, {{1, "Min"}, {10, "Max"}}}]]
```

### Bar Chart with Labels

```
xkcdConvert[BarChart[{1, 10}, ChartLegends -> {"Others", "XKCD"},
  PlotLabel -> "Popularity of questions on MMA.SE",
  ChartStyle -> {Red, Green}]]
```

### Pie Chart

```
xkcdConvert[PieChart[{9, 1}, ChartLabels -> {"XKCD", "Others"},
  PlotLabel -> "Popularity of questions on MMA.SE"]]
```

### List Plot

```
xkcdConvert[
 ListLinePlot[RandomInteger[10, 15], PlotMarkers -> Automatic]]
```

### 3-D Plots

```
xkcdConvert[BarChart3D[{3, 2, 1}, ChartStyle -> Red, FaceGrids -> None,
  Method -> {"Canvas" -> None}, ViewPoint -> {-2, -4, 1},
  PlotLabel -> "This is just silly"]]
```

```
xkcdConvert[
 Plot3D[Exp[-10 (x^2 + y^2)^4], {x, -1, 1}, {y, -1, 1}, 
  MeshStyle -> Thick,
  Boxed -> False, Lighting -> {{"Ambient", White}},
  PlotLabel -> Framed@"This plot is not\nparticularly useful"]]
```

## References

1. [xkcd-style Plots](https://mathematica.stackexchange.com/questions/11350/xkcd-style-plots)

## Author(s)

Stewart Henderson
