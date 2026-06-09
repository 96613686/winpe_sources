# ComputeService::Vmwp::CreateVmGroupSidMapping(void)

- ea: `0x1400bed64`
- end: `0x1400bef77`
- name: `?CreateVmGroupSidMapping@Vmwp@ComputeService@@YAXXZ`
- size: `531`
- prototype: `void __fastcall(ComputeService::Vmwp *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400bd0b8`

## callees

- `0x140017040`
- `0x14001d490`
- `0x140064c5c`
- `0x1400660b4`
- `0x1400bdc70`
- `0x1400be354`
- `0x1400bed64`
- `0x1401057e8`
- `0x14010b2f4`
- `0x1401332f0`
- `0x140134048`
- `0x140142dac`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400bede4`
- `ntdll!RtlInitUnicodeString` at `0x1400bee51`
- `ntdll!RtlInitUnicodeString` at `0x1400bee72`
- `ntdll!RtlInitUnicodeString` at `0x1400bede4`
- `ntdll!RtlInitUnicodeString` at `0x1400bee51`
- `ntdll!RtlInitUnicodeString` at `0x1400bee72`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x1400beeda`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x1400beeda`

## string_xrefs

- `0x1400bef0f`: `onecore\vm\compute\shared\vmwp\lib\vmsid.cpp`

## pseudocode

```c

```
