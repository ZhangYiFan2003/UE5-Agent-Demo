# Interview notes

## 30-second explanation

“This is a lightweight Unreal Engine Agent integration demo based on an open-source UE LLM connector. I focused on understanding and adapting how Agent decisions map to deterministic runtime actions. User instructions go to an LLM, which returns structured JSON such as `move` / `character` / `forward#3`. Unreal parses the response, checks whether a registered handler can execute the command, and performs the action. The model produces high-level decisions; Unreal owns execution.”

Build, LLM request, and character movement verification are still pending. Present this as the intended flow until the local smoke test succeeds.

## Architecture

User → UE5 → LLM API → structured command → Command Handler → gameplay action

## If asked what I changed

- Forked and adapted the existing project for an Agent integration demo.
- Made the plugin self-contained inside the test project.
- Removed credential-bearing prebuilt artifacts and hardcoded credential values from current files.
- Moved API credentials to process environment configuration.
- Fixed the async error callback mismatch.
- Added generated-file exclusions and explicit plugin enablement.
- Preserved the existing movement example instead of rebuilding gameplay.

The original MIT license, attribution, and upstream history are preserved.

## If asked whether the whole project was written from scratch

“No. The underlying LLM Connector is an open-source project. I used it as a UE integration base and focused on understanding and adapting the Agent → structured command → game runtime execution path.”

For the local build and movement smoke test, follow the [README setup instructions](../README.md#phase-1-setup-windows).
