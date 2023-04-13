# pollenprognose-card-ottes

A fork of the great work of [leahoswald's](https://github.com/leahoswald/) work on a card, but not publishing it to HACS. This is the finetuning and publishing, if he adopts this work some day, i will deprecate my work.

```
A Lovelace custom card for https://github.com/mampfes/hacs_dwd_pollenflug in Home Assistant based on the great work of https://github.com/isabellaalstrom/, https://github.com/isabellaalstrom/lovelace-pollenprognos-card and https://github.com/TekniskSupport.
```

## Installation

<b>Warning:</b> Remove other integrations, that use the same name pollenprognose-card, like leahoswald's one


The easiest way to install it is through HACS (Home Assistant Community Store), search for `Pollenprognose OttesFork` in the Frontend section and select `Pollenprogose Card OttesFork`.

If you are not using HACS, you may download pollenprognose-card.js plus the images folder and put it into homeassistant_config_dir/www/community/lovelace-dwd-pollenprognose-card-ottesfork/ directory.

## Example usage
Pick the allergens you want to display.

For ui-mode:
```yaml
type: custom:pollenprognose-card
region_desc: Nordhessen und hess. Mittelgebirge
region_id: 91
allergens:
  - Birke
  - Erle
  - Hasel
  - Esche
  - Graeser
  - Roggen
  - Beifuss
  - Ambrosia
```

For yaml-mode:
```yaml
- type: custom:pollenprognose-card
  region_desc: Oberrhein und unteres Neckartal
  region_id: 111
  allergens:
    - Birke
    - Erle
    - Hasel
    - Esche
    - Graeser
    - Roggen
    - Beifuss
    - Ambrosia
```

## Options

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | `custom:pollenprognose-card`
| region_desc | string | **Required** | Name of the region, is only used for display in header.
| region_id | string | **Required** | The region id as [defined by DWD](https://opendata.dwd.de/climate_environment/health/alerts/Beschreibung_pollen_s31fg.pdf) (find Name from DWD Component and enter ID of it here)
| allergens | list | **Required** | List of allergens for which you have sensors, defined at [hacs_dwd_pollenflug](https://github.com/mampfes/hacs_dwd_pollenflug)
| title | boolean | **Optional** | Set to `false` to remove the heading from the card
| show_state | boolean | **Optional** | Set to `false` if you don't want to show the state text under the images.
| forecast | boolean | **Optional** | Set to `true` to see the forecast for tomorrow indicated with an additional smaller leaf.
| filter_unknown | boolean | **Optional** | Set to `true` to only see actually active pollen.

### Example of the card with all allergens presented
![Screenshot2022-02-13_17-16-48](https://user-images.githubusercontent.com/1292551/153762269-214888ae-d2bb-445b-a90a-f4336cd303e1.png)
