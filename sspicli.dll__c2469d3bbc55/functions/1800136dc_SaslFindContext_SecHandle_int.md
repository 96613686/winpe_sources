# SaslFindContext(_SecHandle *,int)

- ea: `0x1800136dc`
- end: `0x18001378f`
- name: `?SaslFindContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@H@Z`
- size: `179`
- prototype: `struct _SASL_CONTEXT *__fastcall(struct _SecHandle *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800199c0`
- `0x180019c20`
- `0x180019eb0`
- `0x18001a060`
- `0x18001a210`

## callees

- `0x1800136dc`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001376f`
- `ntdll!RtlLeaveCriticalSection` at `0x18001376f`
- `ntdll!RtlEnterCriticalSection` at `0x1800136fe`
- `ntdll!RtlEnterCriticalSection` at `0x1800136fe`

## pseudocode

```c

```
