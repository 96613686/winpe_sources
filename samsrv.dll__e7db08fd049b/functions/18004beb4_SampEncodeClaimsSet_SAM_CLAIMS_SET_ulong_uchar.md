# SampEncodeClaimsSet(_SAM_CLAIMS_SET *,ulong *,uchar * *)

- ea: `0x18004beb4`
- end: `0x18004c129`
- name: `?SampEncodeClaimsSet@@YAJPEAU_SAM_CLAIMS_SET@@PEAKPEAPEAE@Z`
- size: `629`
- prototype: `__int64 __fastcall(struct _SAM_CLAIMS_SET *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004cb10`

## callees

- `0x180027e24`
- `0x18004beb4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004bfe3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004bfe3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c0a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c0a3`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18004bf8e`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18004bf8e`
- `RPCRT4!NdrMesTypeEncode3` at `0x18004c063`
- `RPCRT4!NdrMesTypeEncode3` at `0x18004c063`
- `RPCRT4!MesBufferHandleReset` at `0x18004c028`
- `RPCRT4!MesBufferHandleReset` at `0x18004c028`
- `RPCRT4!MesHandleFree` at `0x18004c0ae`
- `RPCRT4!MesHandleFree` at `0x18004c0ae`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18004bf27`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18004bf27`

## pseudocode

```c

```
