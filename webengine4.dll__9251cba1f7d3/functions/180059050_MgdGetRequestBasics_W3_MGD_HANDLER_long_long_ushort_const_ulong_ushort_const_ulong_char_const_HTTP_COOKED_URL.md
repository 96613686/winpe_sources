# MgdGetRequestBasics(W3_MGD_HANDLER *,long *,long *,ushort const * *,ulong *,ushort const * *,ulong *,char const * *,_HTTP_COOKED_URL * *)

- ea: `0x180059050`
- end: `0x1800592ac`
- name: `?MgdGetRequestBasics@@YAJPEAVW3_MGD_HANDLER@@PEAJ1PEAPEBGPEAK23PEAPEBDPEAPEAU_HTTP_COOKED_URL@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(struct W3_MGD_HANDLER *, int *, unsigned int *, const unsigned __int16 **, unsigned int *, const unsigned __int16 **, unsigned int *, const char **, struct _HTTP_COOKED_URL **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180059050`
- `0x180065b60`

## import_xrefs

- `ucrtbase_clr0400!strtoul` at `0x180059144`
- `ucrtbase_clr0400!strtoul` at `0x180059144`
- `ucrtbase_clr0400!_errno` at `0x180059132`
- `ucrtbase_clr0400!_errno` at `0x180059157`
- `ucrtbase_clr0400!_errno` at `0x180059132`
- `ucrtbase_clr0400!_errno` at `0x180059157`
- `ucrtbase_clr0400!_strnicmp` at `0x1800591ec`
- `ucrtbase_clr0400!_strnicmp` at `0x1800591ec`
- `ucrtbase_clr0400!_stricmp` at `0x1800591cb`
- `ucrtbase_clr0400!_stricmp` at `0x1800591cb`

## string_xrefs

- `0x180059231`: `CACHE_URL`

## pseudocode

```c

```
