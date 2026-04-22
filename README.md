# Aquarium frontend static bundle

## API proxy routing

To prevent CORS failures (including infinite loading during login), API requests are routed through:

- Proxy: `https://masmovil.icu/`
- Upstream target: `https://billetterie.aquarium-larochelle.com/`

The shared API request builder now rewrites API request URLs to this format:

`https://masmovil.icu/https://billetterie.aquarium-larochelle.com/<api-path-and-query>`

This routing is centralized in the shared API runtime chunk so all generated API client calls follow the same behavior.
