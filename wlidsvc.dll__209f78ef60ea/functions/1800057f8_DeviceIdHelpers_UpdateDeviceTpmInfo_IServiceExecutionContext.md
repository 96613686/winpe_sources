# DeviceIdHelpers::UpdateDeviceTpmInfo(IServiceExecutionContext *)

- ea: `0x1800057f8`
- end: `0x180005edb`
- name: `?UpdateDeviceTpmInfo@DeviceIdHelpers@@SAJPEAVIServiceExecutionContext@@@Z`
- size: `1763`
- prototype: `__int64 __fastcall(struct IServiceExecutionContext *)`
- caller_count: `3`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180029980`
- `0x1800563d0`
- `0x1800bb090`

## callees

- `0x1800057f8`
- `0x180006ac0`
- `0x180006b44`
- `0x18000a354`
- `0x18000fd04`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18002c6c8`
- `0x18002d36c`
- `0x180044d88`
- `0x180055f18`
- `0x180087c44`
- `0x1800888a0`
- `0x1800e09a8`
- `0x1800e9b34`
- `0x1800e9b54`
- `0x1800e9b80`
- `0x1800e9b98`
- `0x1800e9c90`
- `0x1800e9cb0`
- `0x1800ec0d4`
- `0x1800edf40`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005d54`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005d54`
- `ntdll!RtlPublishWnfStateData` at `0x180005990`
- `ntdll!RtlPublishWnfStateData` at `0x180005a1a`
- `ntdll!RtlPublishWnfStateData` at `0x180005990`
- `ntdll!RtlPublishWnfStateData` at `0x180005a1a`
- `ntdll!RtlNtStatusToDosError` at `0x1800059a1`
- `ntdll!RtlNtStatusToDosError` at `0x180005a2a`
- `ntdll!RtlNtStatusToDosError` at `0x1800059a1`
- `ntdll!RtlNtStatusToDosError` at `0x180005a2a`
- `AutoPilot!AutoPilotGetOobeSettingsOverride` at `0x180005afc`
- `AutoPilot!AutoPilotGetOobeSettingsOverride` at `0x180005afc`

## string_xrefs

- `0x18000584d`: `DeviceIdHelpers::UpdateDeviceTpmInfo`
- `0x180005872`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers2.cpp`
- `0x180005b4a`: `ShouldUpdateTpmInLongTermAttestationFailure - AIK: 0x%x - %d, AutoPilot TPM state: 0x%x - %d, TPM Update required: %d`
- `0x1800059e9`: `UpdateDeviceTpmInfo determined client is bound to Software TPM so hardware attestation will not work`

## pseudocode

```c

```
