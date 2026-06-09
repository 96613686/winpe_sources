# CRpcWatchDog::ReportException(void *,unsigned __int64)

- ea: `0x1800c7678`
- end: `0x1800c77a3`
- name: `?ReportException@CRpcWatchDog@@AEAAXPEAX_K@Z`
- size: `299`
- prototype: `void __fastcall(CRpcWatchDog *__hidden this, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18009f154`

## callees

- `0x1800a1d10`
- `0x1800a2660`
- `0x1800c7678`
- `0x1800db758`
- `0x1800dd2e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c7730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c7730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c7727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c7727`
- `ntdll!RtlReportExceptionEx` at `0x1800c7751`
- `ntdll!RtlReportExceptionEx` at `0x1800c7751`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800c7702`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800c7702`

## pseudocode

```c

```
