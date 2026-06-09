# SampQuickEncodeClaimsBlob(void *,_SAM_CLAIMS_SET *,_SAM_CLAIMS_BLOB *)

- ea: `0x18004cb10`
- end: `0x18004cde0`
- name: `?SampQuickEncodeClaimsBlob@@YAJPEAXPEAU_SAM_CLAIMS_SET@@PEAU_SAM_CLAIMS_BLOB@@@Z`
- size: `720`
- prototype: `int(void *, struct _SAM_CLAIMS_SET *, struct _SAM_CLAIMS_BLOB *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004d390`

## callees

- `0x180027e24`
- `0x18004beb4`
- `0x18004ca1c`
- `0x18004cb10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cc70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004cc70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cd2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cd4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cd2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cd4d`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bb923`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bb93f`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bb923`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800bb93f`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18004cc23`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18004cc23`
- `RPCRT4!NdrMesTypeEncode3` at `0x18004ccf7`
- `RPCRT4!NdrMesTypeEncode3` at `0x18004ccf7`
- `RPCRT4!MesBufferHandleReset` at `0x18004ccb8`
- `RPCRT4!MesBufferHandleReset` at `0x18004ccb8`
- `RPCRT4!MesHandleFree` at `0x18004cd3d`
- `RPCRT4!MesHandleFree` at `0x18004cd3d`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18004cbbc`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18004cbbc`

## pseudocode

```c

```
