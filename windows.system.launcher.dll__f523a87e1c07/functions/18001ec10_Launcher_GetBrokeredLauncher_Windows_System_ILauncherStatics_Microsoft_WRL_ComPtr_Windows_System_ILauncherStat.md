# Launcher::_GetBrokeredLauncher<Windows::System::ILauncherStatics>(Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics> &,Windows::System::IUser *,bool)

- ea: `0x18001ec10`
- end: `0x18001edc7`
- name: `??$_GetBrokeredLauncher@UILauncherStatics@System@Windows@@@Launcher@@CAJAEAV?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@PEAUIUser@System@Windows@@_N@Z`
- size: `439`
- prototype: `__int64 __fastcall(LauncherMiscHelpers *, __int64, char)`
- caller_count: `5`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d790`
- `0x18001e350`
- `0x1800285d0`
- `0x18009aea0`
- `0x18009b640`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x18001d544`
- `0x18001d590`
- `0x18001ec10`
- `0x180039730`
- `0x180041bf8`
- `0x18006c510`
- `0x18008a030`

## import_xrefs

- `combase!__imp_CoAllowSetForegroundWindow` at `0x18001eda0`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x18001eda0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ed5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001ed5d`
- `ntdll!RtlIsMultiSessionSku` at `0x18001ecb5`
- `ntdll!RtlIsMultiSessionSku` at `0x18001ecb5`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001ec7e`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001ec7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ed47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ed47`

## string_xrefs

- `0x18001ed40`: `Windows.System.BrokeredLauncher`

## pseudocode

```c

```
