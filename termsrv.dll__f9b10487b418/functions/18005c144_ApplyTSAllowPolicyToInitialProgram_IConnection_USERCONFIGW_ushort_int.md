# ApplyTSAllowPolicyToInitialProgram(IConnection *,_USERCONFIGW *,ushort * *,int *)

- ea: `0x18005c144`
- end: `0x18005c3e7`
- name: `?ApplyTSAllowPolicyToInitialProgram@@YAJPEAVIConnection@@PEAU_USERCONFIGW@@PEAPEAGPEAH@Z`
- size: `675`
- prototype: `__int64 __fastcall(struct IConnection *, struct _USERCONFIGW *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005df80`

## callees

- `0x18000a210`
- `0x180013e38`
- `0x180016234`
- `0x1800321f0`
- `0x18003269c`
- `0x180032700`
- `0x18004d884`
- `0x18005c144`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c386`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c386`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c2fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c2fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c36b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c36b`

## string_xrefs

- `0x18005c350`: `StringCchCopy failed: 0x%x in %s`
- `0x18005c394`: `Protocol failed VERIFY_TYPE_PUBLISHED_APPLICATION failed: 0x%x in %s`

## pseudocode

```c

```
