# _tsrpcUnInitialize(int)

- ea: `0x18000b254`
- end: `0x18000b2d3`
- name: `?_tsrpcUnInitialize@@YAHH@Z`
- size: `127`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000af64`

## callees

- `0x18000b254`
- `0x18000b2dc`
- `0x18000b34c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b290`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b290`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b264`

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
0x18000b254  sub     rsp, 28h
0x18000b258  mov     rcx, cs:?g_ReadyEventHandle@@3PEAXEA; hObject
0x18000b25f  test    rcx, rcx
0x18000b262  jz      short loc_18000B27B
0x18000b264  call    cs:__imp_CloseHandle
0x18000b26b  nop     dword ptr [rax+rax+00h]
0x18000b270  mov     cs:?g_ReadyEventHandle@@3PEAXEA, 0; void * g_ReadyEventHandle
0x18000b27b  call    ?DestroyNotification@@YAJXZ; DestroyNotification(void)
0x18000b280  cmp     cs:?gbWinstaCritInitialized@@3HA, 0; int gbWinstaCritInitialized
0x18000b287  jz      short loc_18000B2A6
0x18000b289  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b290  call    cs:__imp_DeleteCriticalSection
0x18000b297  nop     dword ptr [rax+rax+00h]
0x18000b29c  mov     cs:?gbWinstaCritInitialized@@3HA, 0; int gbWinstaCritInitialized
0x18000b2a6  call    ?DeleteLocalSids@CPublicBinding@@SAXXZ; CPublicBinding::DeleteLocalSids(void)
0x18000b2ab  lea     rcx, ?m_CritSec@CPublicBinding@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000b2b2  call    cs:__imp_DeleteCriticalSection
0x18000b2b9  nop     dword ptr [rax+rax+00h]
0x18000b2be  mov     eax, 1
0x18000b2c3  mov     cs:?bCritSecInitialized@CPublicBinding@@1HA, 0; int CPublicBinding::bCritSecInitialized
0x18000b2cd  add     rsp, 28h
0x18000b2d1  retn
```
