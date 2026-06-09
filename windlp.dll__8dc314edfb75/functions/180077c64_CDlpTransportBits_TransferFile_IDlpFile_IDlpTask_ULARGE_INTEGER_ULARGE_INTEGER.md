# CDlpTransportBits::TransferFile(IDlpFile *,IDlpTask *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x180077c64`
- end: `0x18007804e`
- name: `?TransferFile@CDlpTransportBits@@AEAAJPEAVIDlpFile@@PEAVIDlpTask@@PEAT_ULARGE_INTEGER@@2@Z`
- size: `1002`
- prototype: `__int64 __usercall@<rax>(CDlpTransportBits *__hidden this@<rcx>, struct IDlpFile *@<rdx>, struct IDlpTask *@<r8>, union _ULARGE_INTEGER *@<r9>, union _ULARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180079800`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180077c64`
- `0x180079890`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180077e2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180077ebd`
- `OLEAUT32!__imp_SysFreeString` at `0x18007801e`
- `OLEAUT32!__imp_SysFreeString` at `0x180078035`
- `OLEAUT32!__imp_SysFreeString` at `0x180077e2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180077ebd`
- `OLEAUT32!__imp_SysFreeString` at `0x18007801e`
- `OLEAUT32!__imp_SysFreeString` at `0x180078035`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077f04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077f04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077f2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077f2b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180077e57`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180077e57`

## string_xrefs

- `0x180077eef`: `TransferFile: Not updating remote source path.`
- `0x180077e94`: `TransferFile: Updating remote source path: [%s] => [%s]`

## pseudocode

```c

```
