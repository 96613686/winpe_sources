# BioTrustlet::IsSecureBioAvailable(ushort &)

- ea: `0x180051030`
- end: `0x18005127e`
- name: `?IsSecureBioAvailable@BioTrustlet@@SAJAEAG@Z`
- size: `590`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045044`
- `0x180056378`
- `0x180071de8`

## callees

- `0x18003f2dc`
- `0x180050b4c`
- `0x180051030`
- `0x180068f60`
- `0x18006e4c4`
- `0x180072d34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800511fc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800511fc`
- `ntdll!NtQuerySystemInformation` at `0x1800510b8`
- `ntdll!NtQuerySystemInformation` at `0x1800510b8`
- `tbs!Tbsi_GetDeviceInfo` at `0x180051071`
- `tbs!Tbsi_GetDeviceInfo` at `0x180051071`

## string_xrefs

- `0x180051085`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x1800510c8`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`
- `0x180051228`: `onecore\ds\security\biometrics\service\trustlet\lib\trustletcontrol.cpp`

## pseudocode

```c

```
