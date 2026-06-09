# _tsrpcUnInitialize(int)

- ea: `0x180003494`
- end: `0x180003500`
- name: `?_tsrpcUnInitialize@@YAHH@Z`
- size: `108`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800031d8`

## callees

- `0x180003494`
- `0x180003508`
- `0x180003560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034a4`

## pseudocode

```c
__int64 __fastcall _tsrpcUnInitialize()
{
  __int64 result; // rax

  if ( g_ReadyEventHandle )
  {
    CloseHandle(g_ReadyEventHandle);
    g_ReadyEventHandle = 0;
  }
  DestroyNotification();
  if ( gbWinstaCritInitialized )
  {
    DeleteCriticalSection(&gWinstaCrit);
    gbWinstaCritInitialized = 0;
  }
  CPublicBinding::DeleteLocalSids();
  DeleteCriticalSection(&CPublicBinding::m_CritSec);
  result = 1;
  CPublicBinding::bCritSecInitialized = 0;
  return result;
}

```

## disassembly

```asm
0x180003494  sub     rsp, 28h
0x180003498  mov     rcx, cs:?g_ReadyEventHandle@@3PEAXEA; hObject
0x18000349f  test    rcx, rcx
0x1800034a2  jz      short loc_1800034B5
0x1800034a4  call    cs:__imp_CloseHandle
0x1800034aa  mov     cs:?g_ReadyEventHandle@@3PEAXEA, 0; void * g_ReadyEventHandle
0x1800034b5  call    ?DestroyNotification@@YAJXZ; DestroyNotification(void)
0x1800034ba  cmp     cs:?gbWinstaCritInitialized@@3HA, 0; int gbWinstaCritInitialized
0x1800034c1  jz      short loc_1800034DA
0x1800034c3  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800034ca  call    cs:__imp_DeleteCriticalSection
0x1800034d0  mov     cs:?gbWinstaCritInitialized@@3HA, 0; int gbWinstaCritInitialized
0x1800034da  call    ?DeleteLocalSids@CPublicBinding@@SAXXZ; CPublicBinding::DeleteLocalSids(void)
0x1800034df  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800034e6  call    cs:__imp_DeleteCriticalSection
0x1800034ec  mov     eax, 1
0x1800034f1  mov     cs:?bCritSecInitialized@CPublicBinding@@1HA, 0; int CPublicBinding::bCritSecInitialized
0x1800034fb  add     rsp, 28h
0x1800034ff  retn
```
