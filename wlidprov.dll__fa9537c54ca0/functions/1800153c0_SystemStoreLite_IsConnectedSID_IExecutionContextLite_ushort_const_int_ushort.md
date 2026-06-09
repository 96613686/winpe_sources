# SystemStoreLite::IsConnectedSID(IExecutionContextLite *,ushort const *,int *,ushort * *)

- ea: `0x1800153c0`
- end: `0x180015542`
- name: `?IsConnectedSID@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEBGPEAHPEAPEAG@Z`
- size: `386`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, const unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800058b8`
- `0x18004cc80`

## callees

- `0x180004824`
- `0x180004910`
- `0x180004b2c`
- `0x180005a60`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x1800153c0`

## import_xrefs

- `ntdll!wcsstr` at `0x1800154c6`
- `ntdll!wcsstr` at `0x1800154c6`

## string_xrefs

- `0x180015400`: `SystemStoreLite::IsConnectedSID`
- `0x1800154e3`: `pContext != nullptr && pIsConnected != nullptr && pCurrentUserSidString != nullptr`

## pseudocode

```c

```
