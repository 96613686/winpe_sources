# Launcher::_GetBrokeredLauncher<Windows::System::ILauncherStatics4>(Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics4> &,Windows::System::IUser *,bool)

- ea: `0x180069898`
- end: `0x180069a4f`
- name: `??$_GetBrokeredLauncher@UILauncherStatics4@System@Windows@@@Launcher@@CAJAEAV?$ComPtr@UILauncherStatics4@System@Windows@@@WRL@Microsoft@@PEAUIUser@System@Windows@@_N@Z`
- size: `439`
- prototype: `__int64 __fastcall(LauncherMiscHelpers *, __int64, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a1c0`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18001d590`
- `0x180039730`
- `0x180041bf8`
- `0x180069898`
- `0x180069a58`
- `0x18006c510`
- `0x18008a030`

## import_xrefs

- `combase!__imp_CoAllowSetForegroundWindow` at `0x180069a28`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x180069a28`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800699e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800699e5`
- `ntdll!RtlIsMultiSessionSku` at `0x18006993d`
- `ntdll!RtlIsMultiSessionSku` at `0x18006993d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180069906`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180069906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800699cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800699cf`

## string_xrefs

- `0x1800699c8`: `Windows.System.BrokeredLauncher`

## pseudocode

```c

```
