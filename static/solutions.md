

## Exercise 1

```
(p9.ggplot(water_quality,
           p9.aes(x="depth_cm",
                  y="dissolved_oxygen_mg_l"))
     + p9.geom_point()
)
```

## Exercise 2

```
(p9.ggplot(water_quality,
           p9.aes(x="temperature_C",
                  y="dissolved_oxygen_mg_l",
                  color="month"))
     + p9.geom_point()
)
```

## Exercise 3

Different options are available, for example:

```
(p9.ggplot(water_quality,
           p9.aes(x="factor(location)",
                  y="dissolved_oxygen_mg_l"))
    + p9.geom_violin()
    + p9.geom_jitter()
)
```

```
(p9.ggplot(water_quality,
           p9.aes(x="factor(location)",
                  y="temperature_C"))
    + p9.geom_violin()
    + p9.geom_jitter()
)
```

## Exercise 4

```
(p9.ggplot(water_quality,
           p9.aes(x="dissolved_oxygen_mg_l",
                  y="temperature_C",
                  color="factor(location)"))
    + p9.geom_point()
    + p9.geom_smooth(method="lowess")
    + p9.facet_wrap("month")
)
```

## Exercise 5

```
(p9.ggplot(water_quality,
           p9.aes(x="dissolved_oxygen_mg_l",
                  y="depth_cm",
                  color="factor(location)"))
     + p9.geom_point()
     + p9.scale_y_reverse()

     + p9.theme_light()
     + p9.scale_color_brewer(type="qual", palette=6)
     + p9.labs(x="Dissolved oxygen (mg/l)",
               y="Depth (cm)",
               color="Location")
)
```

## Exercise 6

```
(p9.ggplot(water_quality,
           p9.aes(x='dissolved_oxygen_mg_l',
                  y='depth_cm',
                  color="month"))
    + p9.geom_path(size=1.5)
    + p9.geom_point(size=2)
    + p9.facet_wrap(facets='location')
    + p9.scale_y_reverse()

    + p9.theme_light()
    + p9.labs(x="dissolved oxygen (mg/l)",
              y="depth (m)",
              color="Month (2016)")
    + p9.theme(figure_size=(8, 8),
               text=p9.element_text(size=14),
               legend_position="top",
               legend_direction='horizontal',
               legend_title=p9.element_blank(),
               legend_key=p9.element_rect(fill='white',
                                          color='white'))
)
```


## Exercise 7

```
(p9.ggplot(water_quality,
           p9.aes(x='factor(location)',
                  y="dissolved_oxygen_mg_l",
                  fill="month"))
    + p9.stat_summary(fun_y=np.mean, geom='col', position='dodge')

    + p9.theme_light()
)
```