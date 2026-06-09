# CWLIDCCHelper::HasClockChanged(IExecutionContextLite *,ulong &)

- ea: `0x180050d58`
- end: `0x180050fed`
- name: `?HasClockChanged@CWLIDCCHelper@@SA_NPEAVIExecutionContextLite@@AEAK@Z`
- size: `661`
- prototype: `bool __fastcall(struct IExecutionContextLite *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180014004`

## callees

- `0x18000535c`
- `0x1800061a8`
- `0x180009630`
- `0x180009e00`
- `0x18000a400`
- `0x180050d58`
- `0x18005100c`
- `0x1800521f0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180050f06`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180050f06`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180050f13`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180050f13`

## string_xrefs

- `0x180050eb7`: `hr = registryHelper.ReadQwordFromRegistry(volatileKey, nullptr, WLID_REG_TICKCOUNT, &regTickCount)`
- `0x180050eef`: `hr = registryHelper.ReadQwordFromRegistry(volatileKey, nullptr, WLID_REG_CLOCKTIME_SEC, &regClockTimeSeconds)`

## pseudocode

```c

```
