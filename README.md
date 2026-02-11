# KiloCenter Blueprint Registry

The community-driven repository of device blueprints for the [KiloCenter](https://github.com/timkrav3/kitest) MIOTY Service Center.

Blueprints define how KiloCenter communicates with MIOTY endpoints — encoding formats, payload decoders, default configuration, and operational parameters. A shared registry means less duplicate work and faster device onboarding for everyone.

## What is a Blueprint?

A blueprint is a JSON document that captures everything KiloCenter needs to manage a specific device model:

- **Device identity** — manufacturer, model, hardware/firmware revision
- **Payload codec** — how to decode uplink data and encode downlink commands
- **Default parameters** — reporting intervals, power settings, bidirectional capability
- **Operational metadata** — expected battery life, supported frequency plans

When a new endpoint is provisioned, KiloCenter matches it to a blueprint and applies the correct configuration automatically.

## Repository Structure

```
blueprints/
  {uuid}.json          # One file per blueprint version
```

Each blueprint is submitted via pull request and identified by a unique ID. The flat structure keeps things simple and avoids naming collisions.

## Contributing

### Via KiloCenter UI (Recommended)

1. Open KiloCenter and navigate to **Blueprints**
2. Select a manufacturer, model, and blueprint version
3. Click **Submit to Registry**
4. Fill in your contributor name and email
5. A pull request is created automatically — no git knowledge required

### Via Pull Request

1. Fork this repository
2. Add your blueprint JSON file to `blueprints/`
3. Open a pull request with a description of the device and any testing notes

### Submission Guidelines

- One blueprint per file, one file per device model/version combination
- Use the JSON structure produced by KiloCenter's export — don't hand-craft files
- Include accurate manufacturer and model identifiers
- Test the blueprint against a real device before submitting if possible

## Using Blueprints

Blueprints from this registry can be imported directly into any KiloCenter deployment. As the registry grows, KiloCenter will support automatic discovery and synchronization.

## Why Contribute?

Every blueprint you submit saves time for the next operator deploying the same device. MIOTY is a growing ecosystem, and a comprehensive blueprint library lowers the barrier for new deployments. Whether you manage one gateway or a thousand, sharing your device definitions helps the entire community.

## License

Blueprints in this repository are contributed under the [MIT License](LICENSE). By submitting a blueprint, you agree that your contribution may be freely used by any KiloCenter deployment.
