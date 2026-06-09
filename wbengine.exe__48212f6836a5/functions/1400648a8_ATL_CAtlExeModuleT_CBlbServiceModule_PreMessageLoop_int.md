# ATL::CAtlExeModuleT<CBlbServiceModule>::PreMessageLoop(int)

- ea: `0x1400648a8`
- end: `0x140064a34`
- name: `?PreMessageLoop@?$CAtlExeModuleT@VCBlbServiceModule@@@ATL@@QEAAJH@Z`
- size: `396`
- prototype: `int __fastcall(LPVOID lpParameter, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140066080`

## callees

- `0x140006ca8`
- `0x14005f44c`
- `0x140060588`
- `0x1400648a8`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14006492b`
- `KERNEL32!CreateThread` at `0x14006492b`
- `KERNEL32!WaitForSingleObject` at `0x14006498a`
- `KERNEL32!WaitForSingleObject` at `0x14006498a`
- `KERNEL32!SetEvent` at `0x14006497c`
- `KERNEL32!SetEvent` at `0x14006497c`
- `KERNEL32!CloseHandle` at `0x14006493d`
- `KERNEL32!CloseHandle` at `0x14006493d`
- `KERNEL32!CreateEventW` at `0x1400648ed`
- `KERNEL32!CreateEventW` at `0x1400648ed`
- `ole32!CoResumeClassObjects` at `0x140064954`
- `ole32!CoResumeClassObjects` at `0x1400649a4`
- `ole32!CoResumeClassObjects` at `0x140064954`
- `ole32!CoResumeClassObjects` at `0x1400649a4`
- `ole32!CoRevokeClassObject` at `0x1400649ee`
- `ole32!CoRevokeClassObject` at `0x1400649ee`

## pseudocode

```c

```
