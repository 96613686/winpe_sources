# SampUnicodeToOemString(_STRING *,_UNICODE_STRING *)

- ea: `0x1800adde8`
- end: `0x1800adf48`
- name: `?SampUnicodeToOemString@@YAJPEAU_STRING@@PEAU_UNICODE_STRING@@@Z`
- size: `352`
- prototype: `int(struct _STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180051e60`
- `0x180051f10`

## callees

- `0x180027e24`
- `0x1800adde8`

## import_xrefs

- `ntdll!RtlUnicodeToOemN` at `0x1800adeb2`
- `ntdll!RtlUnicodeToOemN` at `0x1800adeb2`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x1800ade0f`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x1800ade0f`
- `ntdll!RtlInitString` at `0x1800adf04`
- `ntdll!RtlInitString` at `0x1800adf04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ade6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ade6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800adec2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800adec2`

## pseudocode

```c

```
