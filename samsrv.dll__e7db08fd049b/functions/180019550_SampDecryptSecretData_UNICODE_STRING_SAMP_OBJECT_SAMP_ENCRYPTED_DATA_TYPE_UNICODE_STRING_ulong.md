# SampDecryptSecretData(_UNICODE_STRING *,_SAMP_OBJECT *,_SAMP_ENCRYPTED_DATA_TYPE,_UNICODE_STRING *,ulong)

- ea: `0x180019550`
- end: `0x18001988e`
- name: `?SampDecryptSecretData@@YAJPEAU_UNICODE_STRING@@PEAU_SAMP_OBJECT@@W4_SAMP_ENCRYPTED_DATA_TYPE@@0K@Z`
- size: `830`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _SAMP_OBJECT *, unsigned int, struct _UNICODE_STRING *, int)`
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180028370`
- `0x18003bd2c`
- `0x18004f7a0`
- `0x18009cd40`
- `0x18009fd08`

## callees

- `0x180018f10`
- `0x180019550`
- `0x18001a8e0`
- `0x180027250`
- `0x180027e24`
- `0x1800281e4`
- `0x18002820c`
- `0x180028270`
- `0x1800282b8`
- `0x18002832c`
- `0x18002cd80`
- `0x18006ae40`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180019809`
- `ntdll!RtlCopyUnicodeString` at `0x180019809`
- `ntdll!RtlInitUnicodeString` at `0x180019816`
- `ntdll!RtlInitUnicodeString` at `0x180019816`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019666`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800197c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019666`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800197c7`
- `bcrypt!BCryptDestroyKey` at `0x180019755`
- `bcrypt!BCryptDestroyKey` at `0x180019755`

## pseudocode

```c

```
