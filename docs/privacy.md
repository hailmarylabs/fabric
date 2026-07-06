# Privacy

Fabric does not upload your repo to HailMary.

Fabric writes local state under `.fabric/`. The proxy binds to `127.0.0.1`, starts for the Fabric-launched Claude Code session, and stops when that session exits.

Selected context still goes to your configured Claude provider during Claude Code sessions. Fabric narrows context; it does not hide selected files from the model provider.

Run `claude` directly to bypass Fabric.
