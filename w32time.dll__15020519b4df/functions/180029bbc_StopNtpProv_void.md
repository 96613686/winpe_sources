# StopNtpProv(void)

- ea: `0x180029bbc`
- end: `0x180029eab`
- name: `?StopNtpProv@@YAJXZ`
- size: `751`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180030090`
- `0x1800301f8`
- `0x180032f00`

## callees

- `0x1800151a0`
- `0x180015370`
- `0x180018138`
- `0x18001d9a0`
- `0x180029bbc`
- `0x180029eb4`
- `0x180029ef0`
- `0x18002a940`
- `0x180030fec`
- `0x18003d2d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029bf2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029bf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029c47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029c47`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029ddc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029dff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029e22`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029ddc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029dff`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029e22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029c15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029c15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029cbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029db9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029cbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029db9`

## pseudocode

```c
__int64 StopNtpProv(void)
{
  int v0; // edi
  void *v1; // r8
  _NtpProvState *v2; // rbx
  void *v3; // rcx
  int v4; // eax
  int v5; // eax
  struct _RTL_CRITICAL_SECTION *v6; // rdx
  struct _RTL_CRITICAL_SECTION *v7; // rdx
  void *v8; // rcx
  void *v9; // rcx
  __int64 i; // rsi
  struct NicSocket *v11; // rcx
  signed int v12; // eax
  _QWORD *j; // rsi
  _QWORD *v14; // rax
  _QWORD *v15; // rdx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx

  v0 = 0;
  if ( (unsigned __int8)FileLogAllowEntry(59) )
    FileLogAdd(L"StopNtpProv\n");
  v2 = g_pnpstate;
  v3 = (void *)*((_QWORD *)g_pnpstate + 11);
  *(_BYTE *)g_pnpstate = 0;
  if ( v3 )
  {
    SetEvent(v3);
    v2 = g_pnpstate;
  }
  if ( *((_BYTE *)v2 + 284) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 288));
    v4 = StopPeerPollingThread();
    if ( v4 < 0 )
      v0 = v4;
    v5 = StopListeningThread();
    if ( v5 < 0 && v0 >= 0 )
      v0 = v5;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 288));
    v2 = g_pnpstate;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v2 + 17);
  if ( v6 )
  {
    myDeleteTimerQueueTimer(v3, v6, v1);
    v2 = g_pnpstate;
  }
  v7 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v2 + 61);
  if ( v7 && *((_BYTE *)v2 + 524) )
  {
    myDeleteTimerQueueTimer(v3, v7, v1);
    v2 = g_pnpstate;
    *((_BYTE *)g_pnpstate + 524) = 0;
  }
  v8 = (void *)*((_QWORD *)v2 + 11);
  if ( v8 )
  {
    CloseHandle(v8);
    v2 = g_pnpstate;
  }
  v9 = (void *)*((_QWORD *)v2 + 12);
  if ( v9 )
  {
    CloseHandle(v9);
    v2 = g_pnpstate;
  }
  if ( *((_QWORD *)v2 + 8) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)v2 + 18); i = (unsigned int)(i + 1) )
    {
      v11 = *(struct NicSocket **)(*((_QWORD *)v2 + 8) + 8 * i);
      if ( v11 )
      {
        FinalizeNicSocket(v11);
        LocalFree(*(HLOCAL *)(*((_QWORD *)g_pnpstate + 8) + 8 * i));
        v2 = g_pnpstate;
        *(_QWORD *)(*((_QWORD *)g_pnpstate + 8) + 8 * i) = 0;
      }
    }
    LocalFree(*((HLOCAL *)v2 + 8));
    v2 = g_pnpstate;
  }
  if ( *((_BYTE *)v2 + 56) == 1 )
  {
    v12 = CloseSocketLayer();
    v2 = g_pnpstate;
    v0 = v12;
  }
  for ( j = (_QWORD *)*((_QWORD *)v2 + 66); j != (_QWORD *)((char *)v2 + 528); --*((_DWORD *)g_pnpstate + 136) )
  {
    v14 = (_QWORD *)*j;
    if ( *(_QWORD **)(*j + 8LL) != j || (v15 = (_QWORD *)j[1], (_QWORD *)*v15 != j) )
      __fastfail(3u);
    v16 = j;
    *v15 = v14;
    j = v14;
    v14[1] = v15;
    LocalFree(v16);
    v2 = g_pnpstate;
  }
  v17 = (void *)*((_QWORD *)v2 + 58);
  if ( v17 )
  {
    CloseHandle(v17);
    v2 = g_pnpstate;
  }
  if ( *((_BYTE *)v2 + 285) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 328));
    v2 = g_pnpstate;
  }
  if ( *((_BYTE *)v2 + 284) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 288));
    v2 = g_pnpstate;
  }
  if ( *((_BYTE *)v2 + 286) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 368));
    v2 = g_pnpstate;
  }
  v18 = (void *)*((_QWORD *)v2 + 20);
  if ( v18 )
  {
    LocalFree(v18);
    v2 = g_pnpstate;
  }
  v19 = (void *)*((_QWORD *)v2 + 19);
  if ( v19 )
  {
    LocalFree(v19);
    v2 = g_pnpstate;
  }
  if ( v2 )
  {
    _NtpProvState::~_NtpProvState(v2);
    operator delete(v2);
  }
  g_pnpstate = 0;
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180029bbc  push    rbx
0x180029bbe  push    rbp
0x180029bbf  push    rsi
0x180029bc0  push    rdi
0x180029bc1  sub     rsp, 28h
0x180029bc5  xor     edi, edi
0x180029bc7  lea     ecx, [rdi+3Bh]
0x180029bca  call    FileLogAllowEntry
0x180029bcf  test    al, al
0x180029bd1  jz      short loc_180029BDF
0x180029bd3  lea     rcx, aStopntpprov; "StopNtpProv\n"
0x180029bda  call    FileLogAdd
0x180029bdf  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029be6  mov     rcx, [rbx+58h]; hEvent
0x180029bea  mov     [rbx], dil
0x180029bed  test    rcx, rcx
0x180029bf0  jz      short loc_180029C05
0x180029bf2  call    cs:__imp_SetEvent
0x180029bf9  nop     dword ptr [rax+rax+00h]
0x180029bfe  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029c05  cmp     [rbx+11Ch], dil
0x180029c0c  jz      short loc_180029C5A
0x180029c0e  lea     rcx, [rbx+120h]; lpCriticalSection
0x180029c15  call    cs:__imp_EnterCriticalSection
0x180029c1c  nop     dword ptr [rax+rax+00h]
0x180029c21  call    ?StopPeerPollingThread@@YAJXZ; StopPeerPollingThread(void)
0x180029c26  test    eax, eax
0x180029c28  cmovs   edi, eax
0x180029c2b  call    ?StopListeningThread@@YAJXZ; StopListeningThread(void)
0x180029c30  test    eax, eax
0x180029c32  jns     short loc_180029C39
0x180029c34  test    edi, edi
0x180029c36  cmovns  edi, eax
0x180029c39  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029c40  add     rcx, 120h; lpCriticalSection
0x180029c47  call    cs:__imp_LeaveCriticalSection
0x180029c4e  nop     dword ptr [rax+rax+00h]
0x180029c53  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029c5a  mov     rdx, [rbx+88h]; void *
0x180029c61  test    rdx, rdx
0x180029c64  jz      short loc_180029C72
0x180029c66  call    ?myDeleteTimerQueueTimer@@YAXPEAX00@Z; myDeleteTimerQueueTimer(void *,void *,void *)
0x180029c6b  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029c72  mov     rdx, [rbx+1E8h]; void *
0x180029c79  test    rdx, rdx
0x180029c7c  jz      short loc_180029C9A
0x180029c7e  cmp     byte ptr [rbx+20Ch], 0
0x180029c85  jz      short loc_180029C9A
0x180029c87  call    ?myDeleteTimerQueueTimer@@YAXPEAX00@Z; myDeleteTimerQueueTimer(void *,void *,void *)
0x180029c8c  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029c93  mov     byte ptr [rbx+20Ch], 0
0x180029c9a  mov     rcx, [rbx+58h]; hObject
0x180029c9e  test    rcx, rcx
0x180029ca1  jz      short loc_180029CB6
0x180029ca3  call    cs:__imp_CloseHandle
0x180029caa  nop     dword ptr [rax+rax+00h]
0x180029caf  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029cb6  mov     rcx, [rbx+60h]; hObject
0x180029cba  test    rcx, rcx
0x180029cbd  jz      short loc_180029CD2
0x180029cbf  call    cs:__imp_CloseHandle
0x180029cc6  nop     dword ptr [rax+rax+00h]
0x180029ccb  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029cd2  cmp     qword ptr [rbx+40h], 0
0x180029cd7  jz      short loc_180029D3E
0x180029cd9  xor     esi, esi
0x180029cdb  cmp     [rbx+48h], esi
0x180029cde  jbe     short loc_180029D27
0x180029ce0  mov     rax, [rbx+40h]
0x180029ce4  mov     rcx, [rax+rsi*8]; struct NicSocket *
0x180029ce8  test    rcx, rcx
0x180029ceb  jz      short loc_180029D20
0x180029ced  call    ?FinalizeNicSocket@@YAXPEAUNicSocket@@@Z; FinalizeNicSocket(NicSocket *)
0x180029cf2  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029cf9  mov     rcx, [rax+40h]
0x180029cfd  mov     rcx, [rcx+rsi*8]; hMem
0x180029d01  call    cs:__imp_LocalFree
0x180029d08  nop     dword ptr [rax+rax+00h]
0x180029d0d  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029d14  mov     rax, [rbx+40h]
0x180029d18  mov     qword ptr [rax+rsi*8], 0
0x180029d20  inc     esi
0x180029d22  cmp     esi, [rbx+48h]
0x180029d25  jb      short loc_180029CE0
0x180029d27  mov     rcx, [rbx+40h]; hMem
0x180029d2b  call    cs:__imp_LocalFree
0x180029d32  nop     dword ptr [rax+rax+00h]
0x180029d37  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029d3e  cmp     byte ptr [rbx+38h], 1
0x180029d42  jnz     short loc_180029D52
0x180029d44  call    ?CloseSocketLayer@@YAJXZ; CloseSocketLayer(void)
0x180029d49  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029d50  mov     edi, eax
0x180029d52  lea     rcx, [rbx+210h]
0x180029d59  mov     rsi, [rcx]
0x180029d5c  cmp     rsi, rcx
0x180029d5f  jz      short loc_180029DAD
0x180029d61  mov     rax, [rsi]
0x180029d64  cmp     [rax+8], rsi
0x180029d68  jnz     loc_180029EA4
0x180029d6e  mov     rdx, [rsi+8]
0x180029d72  cmp     [rdx], rsi
0x180029d75  jnz     loc_180029EA4
0x180029d7b  mov     rcx, rsi; hMem
0x180029d7e  mov     [rdx], rax
0x180029d81  mov     rsi, rax
0x180029d84  mov     [rax+8], rdx
0x180029d88  call    cs:__imp_LocalFree
0x180029d8f  nop     dword ptr [rax+rax+00h]
0x180029d94  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029d9b  dec     dword ptr [rbx+220h]
0x180029da1  lea     rax, [rbx+210h]
0x180029da8  cmp     rsi, rax
0x180029dab  jnz     short loc_180029D61
0x180029dad  mov     rcx, [rbx+1D0h]; hObject
0x180029db4  test    rcx, rcx
0x180029db7  jz      short loc_180029DCC
0x180029db9  call    cs:__imp_CloseHandle
0x180029dc0  nop     dword ptr [rax+rax+00h]
0x180029dc5  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029dcc  cmp     byte ptr [rbx+11Dh], 0
0x180029dd3  jz      short loc_180029DEF
0x180029dd5  lea     rcx, [rbx+148h]; lpCriticalSection
0x180029ddc  call    cs:__imp_DeleteCriticalSection
0x180029de3  nop     dword ptr [rax+rax+00h]
0x180029de8  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029def  cmp     byte ptr [rbx+11Ch], 0
0x180029df6  jz      short loc_180029E12
0x180029df8  lea     rcx, [rbx+120h]; lpCriticalSection
0x180029dff  call    cs:__imp_DeleteCriticalSection
0x180029e06  nop     dword ptr [rax+rax+00h]
0x180029e0b  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029e12  cmp     byte ptr [rbx+11Eh], 0
0x180029e19  jz      short loc_180029E35
0x180029e1b  lea     rcx, [rbx+170h]; lpCriticalSection
0x180029e22  call    cs:__imp_DeleteCriticalSection
0x180029e29  nop     dword ptr [rax+rax+00h]
0x180029e2e  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029e35  mov     rcx, [rbx+0A0h]; hMem
0x180029e3c  test    rcx, rcx
0x180029e3f  jz      short loc_180029E54
0x180029e41  call    cs:__imp_LocalFree
0x180029e48  nop     dword ptr [rax+rax+00h]
0x180029e4d  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029e54  mov     rcx, [rbx+98h]; hMem
0x180029e5b  test    rcx, rcx
0x180029e5e  jz      short loc_180029E73
0x180029e60  call    cs:__imp_LocalFree
0x180029e67  nop     dword ptr [rax+rax+00h]
0x180029e6c  mov     rbx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180029e73  test    rbx, rbx
0x180029e76  jz      short loc_180029E8D
0x180029e78  mov     rcx, rbx; this
0x180029e7b  call    ??1_NtpProvState@@QEAA@XZ; _NtpProvState::~_NtpProvState(void)
0x180029e80  mov     edx, 488h; unsigned __int64
0x180029e85  mov     rcx, rbx; void *
0x180029e88  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029e8d  mov     cs:?g_pnpstate@@3PEAU_NtpProvState@@EA, 0; _NtpProvState * g_pnpstate
0x180029e98  mov     eax, edi
0x180029e9a  add     rsp, 28h
0x180029e9e  pop     rdi
0x180029e9f  pop     rsi
0x180029ea0  pop     rbp
0x180029ea1  pop     rbx
0x180029ea2  retn
0x180029ea4  mov     ecx, 3
0x180029ea9  int     29h; Win8: RtlFailFast(ecx)
```
