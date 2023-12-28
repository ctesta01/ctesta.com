---
title: "Scale (Zoom) Dependent Maps with Leaflet in R"
author: "Christian Testa"
categories: [geography, mapping, R, programming, data-science]
date: "2023-06-10"
filters:
   - lightbox
lightbox: auto
format:
  html:
   include-in-header:
     - text: |
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/htmlwidgets-1.6.1/htmlwidgets.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/jquery-1.12.4/jquery.min.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/leaflet-1.3.1/leaflet.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/leaflet-1.3.1/leaflet.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/leafletfix-1.0.0/leafletfix.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/proj4-2.6.2/proj4.min.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/Proj4Leaflet-1.0.1/proj4leaflet.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/rstudio_leaflet-1.3.1/rstudio_leaflet.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/leaflet-binding-2.1.1/leaflet.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/leaflet-providers-1.9.0/leaflet-providers_1.9.0.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/leaflet-providers-plugin-2.1.1/leaflet-providers-plugin.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/lfx-fullscreen-1.0.2/lfx-fullscreen-prod.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_age_map_files/lfx-fullscreen-1.0.2/lfx-fullscreen-prod.js'></script>
        
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/htmlwidgets-1.6.1/htmlwidgets.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/jquery-1.12.4/jquery.min.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/leaflet-1.3.1/leaflet.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/leaflet-1.3.1/leaflet.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/leafletfix-1.0.0/leafletfix.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/proj4-2.6.2/proj4.min.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/Proj4Leaflet-1.0.1/proj4leaflet.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/rstudio_leaflet-1.3.1/rstudio_leaflet.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/leaflet-binding-2.1.1/leaflet.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/leaflet-providers-1.9.0/leaflet-providers_1.9.0.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/leaflet-providers-plugin-2.1.1/leaflet-providers-plugin.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/lfx-fullscreen-1.0.2/lfx-fullscreen-prod.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_poverty_map_files/lfx-fullscreen-1.0.2/lfx-fullscreen-prod.js'></script>

        <script src='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/htmlwidgets-1.6.1/htmlwidgets.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/jquery-1.12.4/jquery.min.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/leaflet-1.3.1/leaflet.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/leaflet-1.3.1/leaflet.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/leafletfix-1.0.0/leafletfix.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/proj4-2.6.2/proj4.min.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/Proj4Leaflet-1.0.1/proj4leaflet.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/rstudio_leaflet-1.3.1/rstudio_leaflet.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/leaflet-binding-2.1.1/leaflet.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/leaflet-providers-1.9.0/leaflet-providers_1.9.0.js'></script>
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/leaflet-providers-plugin-2.1.1/leaflet-providers-plugin.js'></script>
        <link href='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/lfx-fullscreen-1.0.2/lfx-fullscreen-prod.css' rel='stylesheet' />
        <script src='/assets/2023-06-10-scale-dependent-maps/ma_income_map_files/lfx-fullscreen-1.0.2/lfx-fullscreen-prod.js'></script>
---

![](/assets/img/2023-06-10/interactive_map_scaling.gif)

Something I’ve wanted to accomplish for a while is producing interactive
maps in R that provide a higher level of resolution as the user zooms
in.

I’ve finally sat down and accomplished that, and I’m quite happy to be
sharing the R code here.

Since I live in the Boston area and have family in the New York area, I
thought those were great examples to start with, but the code should be
easily adaptable to any US state or locale that has data collected in
the American Community Survey.

``` r
# dependencies
require(leaflet)
require(sf)
library(tidycensus)
library(tidyverse)
library(tidyr)
library(magrittr)
library(leafpop)
library(htmlwidgets)
library(leaflet.extras)

options(tigris_use_cache = TRUE)
```

``` r
# median income, age, and pct in poverty in Boston Area ---------------------------------------------------

# download county data
ma_counties <- get_acs(
  geography = "county",
  state = "MA",
  variables = c(
    median_income = "B19013_001",
    median_age = "B01002_001",
    total_for_poverty = "B17101_001",
    in_poverty = "B17101_002"
  ), 
  year = 2021,
  geometry = FALSE
)

# download tract data
ma_tracts <- get_acs(
  geography = "tract",
  state = "MA",
  variables = c(
    median_income = "B19013_001",
    median_age = "B01002_001",
    total_for_poverty = "B17101_001",
    in_poverty = "B17101_002"
  ), 
  year = 2021,
  geometry = FALSE
)

# download block group data
ma_block_groups <- get_acs(
  geography = "block group",
  state = "MA",
  variables = c(
    median_income = "B19013_001",
    median_age = "B01002_001",
    total_for_poverty = "B17101_001",
    in_poverty = "B17101_002"
  ), 
  year = 2021,
  geometry = FALSE
)

# put the data together in a list
ma_geographic_dfs <- list(
  counties = ma_counties,
  tracts = ma_tracts,
  block_groups = ma_block_groups
)


# pivot the data wider
ma_geographic_dfs %<>% purrr::map( ~ tidyr::pivot_wider(
  .,
  id_cols = c('GEOID', 'NAME'),
  names_from = 'variable',
  values_from = 'estimate'
))

# calculate the pct in poverty from last 12 months of household income poverty threshold data
ma_geographic_dfs %<>% purrr::map( ~ mutate(., pct_in_poverty = in_poverty / total_for_poverty * 100))

# add geography data to each: 
# we held off on doing this in the `tidycensus::get_acs` calls because sf objects 
# often interact poorly with `tidyr::pivot_wider`
ma_geographic_dfs$counties <-
  left_join(
    tigris::counties(
      cb = TRUE,
      resolution = '20m',
      state = 'MA'
    ),
    ma_geographic_dfs$counties,
    by = c('GEOID' = 'GEOID')
  )

ma_geographic_dfs$tracts <-
  left_join(
    tigris::tracts(cb = TRUE, state = 'MA'),
    ma_geographic_dfs$tracts,
    by = c('GEOID' = 'GEOID')
  )

ma_geographic_dfs$block_groups <-
  left_join(
    tigris::block_groups(cb = TRUE, state = 'MA'),
    ma_geographic_dfs$block_groups,
    by = c('GEOID' = 'GEOID')
  )


# this formatter is so that the data we show in the `leafpop::popupTable` renders nicely 
custom_formatter <- function(df) {
  
  # use the scales::*_format functions to provide nice formatting
  df$median_income %<>% scales::dollar_format()()
  df$median_age %<>% scales::number_format()()
  df$pct_in_poverty %<>% scales::percent_format(scale = 1, accuracy = .1)()

  # we don't want to be sending lists of boundary coordinates into the popupTable
  df %<>% sf::st_drop_geometry()
  
  # some quick renaming & selection of only important variables
  df %<>% select(
    GEOID,
    NAME = NAME.y,
    `Median Age` = median_age,
    `Median Income` = median_income,
    `Poverty` = pct_in_poverty
  )

  return(df)
}

# we'll use Blues for the income level
income_pal <- colorNumeric("Blues", domain = ma_geographic_dfs$block_groups$median_income, na.color = NA)

leaflet() %>%
  addProviderTiles(providers$CartoDB.Voyager) %>%
  addPolygons(
    data = ma_geographic_dfs$counties,
    fillColor = ~income_pal(median_income),
    weight = 0,
    color = "white",
    fillOpacity = 0.7,
    group = 'counties',
    popup = leafpop::popupTable(custom_formatter(ma_geographic_dfs$counties), row.numbers = F)) %>%
  addPolygons(
    data = ma_geographic_dfs$tracts,
    fillColor = ~income_pal(median_income),
    weight = 0,
    color = "white",
    fillOpacity = 0.7,
    group = 'tracts',
    popup = leafpop::popupTable(custom_formatter(ma_geographic_dfs$tracts), row.numbers = F)) %>%
  addPolygons(
    data = ma_geographic_dfs$block_groups,
    fillColor = ~income_pal(median_income),
    weight = 0,
    color = "white",
    fillOpacity = 0.7,
    group = 'block groups',
    popup = leafpop::popupTable(custom_formatter(ma_geographic_dfs$block_groups), row.numbers = F)) %>%
  addLegend(
    data = ma_geographic_dfs$block_groups,
    pal = income_pal,
    values = ~median_income,
    opacity = 0.7,
    title = "Median Income $",
    labFormat = labelFormat(prefix="$"),
    position = "bottomright"
  ) %>%
  addFullscreenControl() %>% 
  groupOptions("block groups", zoomLevels = 13:20) %>% # this is where the magic (scale/zoom dependent rendering happens)
  groupOptions("tracts", zoomLevels = 10:12) %>%
  groupOptions("counties", zoomLevels = 1:9) ->
  ma_income_map

htmlwidgets::saveWidget(ma_income_map, file = "ma_income_map.html", selfcontained = FALSE)
```

<iframe src="/assets/2023-06-10-scale-dependent-maps/ma_income_map.html" width='100%' height = '350px'> </iframe>

``` r
poverty_pal <- colorNumeric("Reds", domain = ma_geographic_dfs$block_groups$pct_in_poverty, na.color = NA)

leaflet() %>%
  addProviderTiles(providers$CartoDB.Voyager) %>%
  addPolygons(
    data = ma_geographic_dfs$counties,
    fillColor = ~poverty_pal(pct_in_poverty),
    weight = 0,
    color = "white",
    fillOpacity = 0.7,
    group = 'counties',
    popup = leafpop::popupTable(custom_formatter(ma_geographic_dfs$counties), row.numbers = F)) %>%
  addPolygons(
    data = ma_geographic_dfs$tracts,
    fillColor = ~poverty_pal(pct_in_poverty),
    weight = 0,
    color = "white",
    fillOpacity = 0.7,
    group = 'tracts',
    popup = leafpop::popupTable(custom_formatter(ma_geographic_dfs$tracts), row.numbers = F)) %>%
  addPolygons(
    data = ma_geographic_dfs$block_groups,
    fillColor = ~poverty_pal(pct_in_poverty),
    weight = 0,
    color = "white",
    fillOpacity = 0.7,
    group = 'block groups',
    popup = leafpop::popupTable(custom_formatter(ma_geographic_dfs$block_groups), row.numbers = F)) %>%
  addLegend(
    data = ma_geographic_dfs$block_groups,
    pal = poverty_pal,
    values = ~pct_in_poverty,
    opacity = 0.7,
    title = "% in Poverty",
    labFormat = labelFormat(suffix="%"),
    position = "bottomright"
  ) %>%
  addFullscreenControl() %>% 
  groupOptions("block groups", zoomLevels = 13:20) %>%
  groupOptions("tracts", zoomLevels = 10:12) %>%
  groupOptions("counties", zoomLevels = 1:9) ->
  ma_poverty_map

htmlwidgets::saveWidget(ma_poverty_map, file = "ma_poverty_map.html", selfcontained = FALSE)
```


<iframe src="/assets/2023-06-10-scale-dependent-maps/ma_poverty_map.html" width='100%' height = '350px'> </iframe>

``` r
age_pal <- colorNumeric("magma", domain = ma_geographic_dfs$block_groups$median_age, na.color = NA, reverse = TRUE)

leaflet() %>%
  addProviderTiles(providers$CartoDB.Voyager) %>%
  addPolygons(
    data = ma_geographic_dfs$counties,
    fillColor = ~age_pal(median_age),
    weight = 0,
    color = "white",
    fillOpacity = 0.7,
    group = 'counties',
    popup = leafpop::popupTable(custom_formatter(ma_geographic_dfs$counties), row.numbers = F)) %>%
  addPolygons(
    data = ma_geographic_dfs$tracts,
    fillColor = ~age_pal(median_age),
    weight = 0,
    color = "white",
    fillOpacity = 0.7,
    group = 'tracts',
    popup = leafpop::popupTable(custom_formatter(ma_geographic_dfs$tracts), row.numbers = F)) %>%
  addPolygons(
    data = ma_geographic_dfs$block_groups,
    fillColor = ~age_pal(median_age),
    weight = 0,
    color = "white",
    fillOpacity = 0.7,
    group = 'block groups',
    popup = leafpop::popupTable(custom_formatter(ma_geographic_dfs$block_groups), row.numbers = F)) %>%
  addLegend(
    data = ma_geographic_dfs$block_groups,
    pal = age_pal,
    values = ~median_age,
    opacity = 0.7,
    title = "Median Age",
    position = "bottomright"
  ) %>%
  addFullscreenControl() %>% 
  groupOptions("block groups", zoomLevels = 13:20) %>%
  groupOptions("tracts", zoomLevels = 10:12) %>%
  groupOptions("counties", zoomLevels = 1:9)  ->
  ma_age_map

htmlwidgets::saveWidget(ma_age_map, file = "ma_age_map.html", selfcontained = FALSE)
```

<iframe src="/assets/2023-06-10-scale-dependent-maps/ma_age_map.html" width='100%' height = '350px'> </iframe>

