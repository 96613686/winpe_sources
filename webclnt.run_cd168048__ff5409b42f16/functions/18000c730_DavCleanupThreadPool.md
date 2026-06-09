# DavCleanupThreadPool

- ea: `0x18000c730`
- end: `0x18000c79c`
- name: `DavCleanupThreadPool`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180025bf8`
- `0x180025f10`

## callees

- `0x18000c730`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000c784`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000c784`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000c767`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000c767`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000c75a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000c75a`

## pseudocode

```c
__int64 DavCleanupThreadPool()
{
  if ( g_DavCallbackEnvironInitialized )
    g_DavCallbackEnvironInitialized = 0;
  if ( DavCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(DavCleanupGroup, 1, 0);
    CloseThreadpoolCleanupGroup(DavCleanupGroup);
    DavCleanupGroup = 0;
  }
  if ( DavThreadPool )
  {
    CloseThreadpool(DavThreadPool);
    DavThreadPool = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c730  sub     rsp, 28h
0x18000c734  cmp     cs:g_DavCallbackEnvironInitialized, 0
0x18000c73b  jz      short loc_18000C747
0x18000c73d  mov     cs:g_DavCallbackEnvironInitialized, 0
0x18000c747  mov     rcx, cs:DavCleanupGroup; ptpcg
0x18000c74e  test    rcx, rcx
0x18000c751  jz      short loc_18000C778
0x18000c753  xor     r8d, r8d; pvCleanupContext
0x18000c756  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18000c75a  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000c760  mov     rcx, cs:DavCleanupGroup; ptpcg
0x18000c767  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000c76d  mov     cs:DavCleanupGroup, 0
0x18000c778  mov     rcx, cs:DavThreadPool; ptpp
0x18000c77f  test    rcx, rcx
0x18000c782  jz      short loc_18000C795
0x18000c784  call    cs:__imp_CloseThreadpool
0x18000c78a  mov     cs:DavThreadPool, 0
0x18000c795  xor     eax, eax
0x18000c797  add     rsp, 28h
0x18000c79b  retn
```
