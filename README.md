# hl-leaflet

A [Leaflet](http://leafletjs.com/) plugin for `htmx` and `hypermedia` inspired
by [hyperleaflet](https://github.com/cemrehancavdar/hyperleaflet).

## Usage

When including the script, the library will automatically search for
all root `.hl-map` elements and configure and render them on document load.

Maps generated by the library cannot survive a full `htmx` `hx-swap`,
so it is advisable to put your `data-hl-render` target outside, and ensure it is
tagged with `hx-preserve`.

```html

<script src="https://unpkg.com/hl-leaflet@0.0.1/dist/hl-leaflet.js"></script>
```

When triggering `hx-swap`, you should take care to not re-render the map.

```html

<div id="map-render" hx-preserve/>
<div
        id=map-config"
        class="hl-map"
        data-hl-render="#map-render"
        data-hl-center="[39.73, 39.99]"
        data-hl-zoom="5"
>
    <div
            class="hl-marker"
            data-hl-center="[-33.8650, 151.2094]"
            data-hl-popup="Sydney"
    ></div>
</div>
```

## Tested With

- [Leaflet](http://leafletjs.com/) 1.4.4
- [htmx](https://htmx.org/) 1.9.9

## Development

```shell
npm install
npm run dev # Watches for changes and rebuilds dist
npm run build # Builds final dist
npm run test # Runs tests
```

## Publishing

```shell
npm login
```

## Advanced htmx usage

See the [tests](https://github.com/IodeSystems/hl-leaflet/blob/main/src/hl-leaflet.test.ts) for advanced `hx-on`
and `hx-swap` usage.
