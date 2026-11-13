# MosaicEarth-Connector-WebODM

Native WebODM & OpenDroneMap WebUI plugins for verified chunked synchronization of tasks, source photos, orthomosaics, DSMs, meshes & point clouds with MosaicEarth.

## Releases & Ready-to-Install Downloads (`v0.2.2`)

- [`MosaicEarth-webodm-0.2.2.zip`](https://github.com/nsicart/MosaicEarth-Connector-WebODM/releases/download/v0.2.2/MosaicEarth-webodm-0.2.2.zip)
- [`MosaicEarth-webui-0.2.2.zip`](https://github.com/nsicart/MosaicEarth-Connector-WebODM/releases/download/v0.2.2/MosaicEarth-webui-0.2.2.zip)
- Also available directly from [MosaicEarth Desktop & Connectors (`app.mosaicearth.app/en/Desktop`)](https://app.mosaicearth.app/en/Desktop).

## Cloud & Local Workstation Endpoints

Every MosaicEarth connector speaks the open **MosaicEarth Synchronization Protocol v1** (chunked `4 MiB` resumable uploads + end-to-end `SHA-256` verification) and can connect to:

- **MosaicEarth Cloud** (default): `https://app.mosaicearth.app`
- **MosaicEarth Desktop (Local Workstation)**: `http://127.0.0.1:19771` (set `MOSAICEARTH_URL=http://127.0.0.1:19771` or select the endpoint in the connector UI).

## Usage & Setup

Download the matching `MosaicEarth-webodm-0.2.2.zip` or `MosaicEarth-webui-0.2.2.zip`. Install it through the host's Administration → Plugins screen, enable it and restart the host web and worker services if requested. WebODM requires 2.9.4 or later; OpenDroneMap WebUI requires 3.2.5 or later. The two ZIPs have different native manifests and must not be interchanged.

Open **MosaicEarth** in the main menu and sign in. Select a local completed task and synchronize. The existing host worker transfers original photos, finished assets and task options without launching a new reconstruction. Cloud viewer layers are prepared separately. Browse the cloud, select a saved revision or latest cloud project, choose a destination host project and download. The plugin restores all files into a new private task and asks the host to prepare its native viewers. Original downloads remain in the resumable staging directory; native viewers may produce additional derivatives.

Host project permissions apply to both upload and restore. Pause stops transfers between chunks; repeat the same action to resume. A native WebODM/WebUI snapshot restores the task structure. A project from another application retains every file and maps compatible orthophotos, elevation models and point clouds into host viewers; unsupported formats remain downloadable attachments. Gaussian splats remain intact but need MosaicEarth's Gaussian viewer.

## License

Released under **GNU Affero General Public License v3.0 or later (`AGPL-3.0-or-later`)** — see [`LICENSE`](./LICENSE).
