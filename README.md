# novolis-template-dotnet

Canonical GitHub **repository template** for new Novolis package, tool, analyzer, app, and template repos.

Use **[Use this template](https://github.com/Novolis-Platform/novolis-template-dotnet/generate)** on GitHub to create a new repository, then rename and add projects.

Supports: library, CLI tool, analyzer, game/app, and template repos without over-specializing.

## What you get

| Item | Purpose |
|------|---------|
| `Directory.Build.props` / `.targets` | `net10.0`, packable defaults, artifacts layout |
| `Directory.Packages.props` | Central package management (optional baseline) |
| `build/version.json` + `version.props` | CalVer versioning |
| `build/Novolis.Documentation.props` | README + XML doc policy for packable projects |
| `nuget.config` | nuget.org + GitHub Packages (`Novolis.*` at `2026.1.*`) |
| `.github/workflows/` | PR, merge, and release CI |
| `docs/getting-started.md` | Documentation defaults checklist |

## Quick start

```powershell
# After generating your repo from the template:
dotnet restore
dotnet build
```

Add your first project:

```powershell
dotnet new classlib -n Acme.Widgets.Core -o src/Acme.Widgets.Core
dotnet sln add src/Acme.Widgets.Core/Acme.Widgets.Core.csproj
```

## Documentation defaults

New packable projects should:

1. Import `build/Novolis.Documentation.props` (included via root `Directory.Build.props`).
2. Add `README.md` next to each packable `.csproj` with Install/API sections.
3. Document public API with XML comments before removing transitional `CS1591` suppressions.

See [documentation-policy.md](https://github.com/Novolis-Platform/novolis-governance/blob/main/docs/documentation-policy.md).

## Package sources

**Only** nuget.org and GitHub Packages. No local folder feeds. Cross-repo iteration on platform libraries: open **`Novolis.Platform.slnx`** (ProjectReference mode) — see [platform-project-ref-mode](https://github.com/Novolis-Platform/novolis-governance/blob/main/docs/platform-project-ref-mode.md).

## Related templates

For `dotnet new` scaffolds (microservice, Avalonia, MonoGame), use the **[novolis-templates](https://github.com/Novolis-Platform/novolis-templates)** package instead.

## More documentation

- [Getting started](docs/getting-started.md)
- [Design](docs/design.md)
- [Release](docs/release.md)
