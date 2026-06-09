# UlAtqWaitForDisconnect(unsigned __int64,int,void *)

- ea: `0x1800129e0`
- end: `0x180012aee`
- name: `?UlAtqWaitForDisconnect@@YAJ_KHPEAX@Z`
- size: `270`
- prototype: `__int64 __fastcall(HTTP_CONNECTION_ID ConnectionId, int, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180012050`
- `0x1800129e0`
- `0x180015ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012ad7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012ad7`
- `HTTPAPI!HttpWaitForDisconnectEx` at `0x180012ac3`
- `HTTPAPI!HttpWaitForDisconnectEx` at `0x180012ac3`
- `HTTPAPI!HttpWaitForDisconnect` at `0x180012aad`
- `HTTPAPI!HttpWaitForDisconnect` at `0x180012aad`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180012a19`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180012a19`

## pseudocode

```c
__int64 __fastcall UlAtqWaitForDisconnect(HTTP_CONNECTION_ID ConnectionId, int a2, void *a3)
{
  char *v7; // rax
  UL_DISCONNECT_CONTEXT *v8; // rdi
  int v9; // ebx
  void *v10; // rax
  unsigned __int64 v11; // rcx
  ULONG v12; // eax
  PSRWLOCK SRWLock; // [rsp+68h] [rbp+20h] BYREF

  SRWLock = 0;
  if ( !g_pwpContext )
    return 2147942450LL;
  v7 = (char *)ALLOC_CACHE_HANDLER::Alloc(UL_DISCONNECT_CONTEXT::sm_pachDisconnects);
  v8 = (UL_DISCONNECT_CONTEXT *)v7;
  if ( !v7 )
    return 2147942408LL;
  *(_OWORD *)(v7 + 8) = 0;
  *(_OWORD *)(v7 + 24) = 0;
  *((_QWORD *)v7 + 6) = a3;
  *(_QWORD *)v7 = &UL_DISCONNECT_CONTEXT::`vftable';
  *((_DWORD *)v7 + 10) = 1933855829;
  *((_DWORD *)v7 + 11) = 1;
  _InterlockedIncrement(&UL_DISCONNECT_CONTEXT::sm_cOutstanding);
  v10 = UL_APP_POOL::QueryAndLockHandle((WP_CONTEXT *)((char *)g_pwpContext + 760), &SRWLock);
  if ( v10 )
  {
    v11 = (unsigned __int64)v8 + 8;
    if ( g_fLegacyDisconnectNotification )
      v12 = HttpWaitForDisconnect(v10, ConnectionId, (LPOVERLAPPED)(v11 & -(__int64)(a2 != 0)));
    else
      v12 = HttpWaitForDisconnectEx(v10, ConnectionId, 0, (LPOVERLAPPED)(v11 & -(__int64)(a2 != 0)));
    v9 = v12;
  }
  else
  {
    v9 = 6;
  }
  ReleaseSRWLockShared(SRWLock);
  if ( v9 == 997 )
    return (unsigned __int16)v9 | 0x80070000;
  UL_DISCONNECT_CONTEXT::DereferenceUlDisconnectContext(v8);
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800129e0  push    rbx
0x1800129e2  push    rbp
0x1800129e3  push    rsi
0x1800129e4  push    rdi
0x1800129e5  sub     rsp, 28h
0x1800129e9  cmp     cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA, 0; WP_CONTEXT * g_pwpContext
0x1800129f1  mov     rbp, r8
0x1800129f4  mov     ebx, edx
0x1800129f6  mov     [rsp+48h+SRWLock], 0
0x1800129ff  mov     rsi, rcx
0x180012a02  jnz     short loc_180012A12
0x180012a04  mov     eax, 80070032h
0x180012a09  add     rsp, 28h
0x180012a0d  pop     rdi
0x180012a0e  pop     rsi
0x180012a0f  pop     rbp
0x180012a10  pop     rbx
0x180012a11  retn
0x180012a12  mov     rcx, cs:?sm_pachDisconnects@UL_DISCONNECT_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_DISCONNECT_CONTEXT::sm_pachDisconnects
0x180012a19  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180012a1f  mov     rdi, rax
0x180012a22  test    rax, rax
0x180012a25  jnz     short loc_180012A47
0x180012a27  mov     eax, 80070008h
0x180012a2c  jmp     short loc_180012A09
0x180012a2e  mov     rcx, rdi; this
0x180012a31  call    ?DereferenceUlDisconnectContext@UL_DISCONNECT_CONTEXT@@QEAAXXZ; UL_DISCONNECT_CONTEXT::DereferenceUlDisconnectContext(void)
0x180012a36  test    ebx, ebx
0x180012a38  jle     short loc_180012A43
0x180012a3a  movzx   ebx, bx
0x180012a3d  or      ebx, 80070000h
0x180012a43  mov     eax, ebx
0x180012a45  jmp     short loc_180012A09
0x180012a47  xorps   xmm0, xmm0
0x180012a4a  movups  xmmword ptr [rax+8], xmm0
0x180012a4e  movups  xmmword ptr [rax+18h], xmm0
0x180012a52  lea     rax, ??_7UL_DISCONNECT_CONTEXT@@6B@; const UL_DISCONNECT_CONTEXT::`vftable'
0x180012a59  mov     [rdi+30h], rbp
0x180012a5d  mov     [rdi], rax
0x180012a60  mov     dword ptr [rdi+28h], 73444C55h
0x180012a67  mov     dword ptr [rdi+2Ch], 1
0x180012a6e  lock inc cs:?sm_cOutstanding@UL_DISCONNECT_CONTEXT@@0JA; long UL_DISCONNECT_CONTEXT::sm_cOutstanding
0x180012a75  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x180012a7c  lea     rdx, [rsp+48h+SRWLock]; void **
0x180012a81  add     rcx, 2F8h; this
0x180012a88  call    ?QueryAndLockHandle@UL_APP_POOL@@QEAAPEAXPEAPEAX@Z; UL_APP_POOL::QueryAndLockHandle(void * *)
0x180012a8d  test    rax, rax
0x180012a90  jz      short loc_180012ACD
0x180012a92  cmp     cs:?g_fLegacyDisconnectNotification@@3HA, 0; int g_fLegacyDisconnectNotification
0x180012a99  lea     rcx, [rdi+8]
0x180012a9d  mov     rdx, rsi; ConnectionId
0x180012aa0  jz      short loc_180012AB5
0x180012aa2  neg     ebx
0x180012aa4  sbb     r8, r8
0x180012aa7  and     r8, rcx; Overlapped
0x180012aaa  mov     rcx, rax; RequestQueueHandle
0x180012aad  call    cs:__imp_HttpWaitForDisconnect
0x180012ab3  jmp     short loc_180012AC9
0x180012ab5  neg     ebx
0x180012ab7  sbb     r9, r9
0x180012aba  xor     r8d, r8d; Reserved
0x180012abd  and     r9, rcx; Overlapped
0x180012ac0  mov     rcx, rax; RequestQueueHandle
0x180012ac3  call    cs:__imp_HttpWaitForDisconnectEx
0x180012ac9  mov     ebx, eax
0x180012acb  jmp     short loc_180012AD2
0x180012acd  mov     ebx, 6
0x180012ad2  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x180012ad7  call    cs:__imp_ReleaseSRWLockShared
0x180012add  cmp     ebx, 3E5h
0x180012ae3  jz      loc_180012A3A
0x180012ae9  jmp     loc_180012A2E
```
