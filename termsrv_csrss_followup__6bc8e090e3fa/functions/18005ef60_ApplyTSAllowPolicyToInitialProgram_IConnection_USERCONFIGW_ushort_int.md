# ApplyTSAllowPolicyToInitialProgram(IConnection *,_USERCONFIGW *,ushort * *,int *)

- ea: `0x18005ef60`
- end: `0x18005f216`
- name: `?ApplyTSAllowPolicyToInitialProgram@@YAJPEAVIConnection@@PEAU_USERCONFIGW@@PEAPEAGPEAH@Z`
- size: `694`
- prototype: `__int64 __fastcall(struct IConnection *, struct _USERCONFIGW *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060ee0`

## callees

- `0x180009940`
- `0x180014808`
- `0x180016d6c`
- `0x180033f60`
- `0x18003440c`
- `0x180034470`
- `0x18004fecc`
- `0x18005ef60`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f1ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f1ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f11a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f11a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f18d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f18d`

## string_xrefs

- `0x18005f172`: `StringCchCopy failed: 0x%x in %s`
- `0x18005f1c2`: `Protocol failed VERIFY_TYPE_PUBLISHED_APPLICATION failed: 0x%x in %s`

## pseudocode

```c

```
