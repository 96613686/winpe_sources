# CReceiveData::~CReceiveData(void)

- ea: `0x1800183b0`
- end: `0x180018690`
- name: `??1CReceiveData@@AEAA@XZ`
- size: `736`
- prototype: `void __fastcall(CReceiveData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018380`

## callees

- `0x18000df80`
- `0x1800183b0`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800183d2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018491`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018602`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800183d2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018491`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018602`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018429`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018429`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018475`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001857f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001857f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018666`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800184f1`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800184f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185f0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800185d5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800185d5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800185a0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800185a0`
- `WS2_32!__imp_closesocket` at `0x18001860f`
- `WS2_32!__imp_closesocket` at `0x18001860f`

## pseudocode

```c
void __fastcall CReceiveData::~CReceiveData(CReceiveData *this)
{
  void *v2; // rcx
  __int64 v3; // rdi
  unsigned int v4; // r12d
  __int64 v5; // rbp
  struct _SSDPNetwork *v6; // rbx
  HANDLE *v7; // r14
  struct _SSDPNetwork *v8; // rsi
  struct _SSDPNetwork *v9; // r15
  __int64 v10; // r9
  __int64 v12; // rbx
  DWORD v13; // edi
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  HANDLE EventA; // rax
  DWORD LastError; // eax
  __int64 v19; // rax
  void *v20; // rcx
  void *v21; // rcx
  DWORD v22; // eax

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    free(v2);
  v3 = *((_QWORD *)this + 2);
  v4 = 0;
  v5 = 0;
  EnterCriticalSection(&stru_180042200);
  v6 = Block;
  if ( Block != (struct _SSDPNetwork *)&Block )
  {
    do
    {
      if ( v3 == *((_QWORD *)v6 + 20) && (*((_DWORD *)v6 + 43))-- == 1 )
        ++v4;
      v6 = *(struct _SSDPNetwork **)v6;
    }
    while ( v6 != (struct _SSDPNetwork *)&Block );
    v6 = Block;
  }
  v7 = (HANDLE *)malloc(8LL * v4);
  while ( v6 != (struct _SSDPNetwork *)&Block )
  {
    v8 = v6;
    v9 = v6;
    v6 = *(struct _SSDPNetwork **)v6;
    v10 = *((_QWORD *)v8 + 20);
    if ( v3 == v10 && !*((_DWORD *)v8 + 43) )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, v10);
      v14 = (_QWORD *)*((_QWORD *)v9 + 1);
      v15 = *(_QWORD *)v9;
      *v14 = *(_QWORD *)v9;
      *(_QWORD *)(v15 + 8) = v14;
      v16 = *((_QWORD *)v8 + 22);
      if ( v16 && *(_QWORD *)(v16 + 24) )
      {
        if ( v7 && (unsigned int)v5 < v4 && (EventA = CreateEventA(0, 0, 0, 0), (v7[v5] = EventA) != 0) )
        {
          if ( UnregisterWaitEx(*(HANDLE *)(*((_QWORD *)v8 + 22) + 24LL), EventA)
            || (LastError = GetLastError()) == 0
            || LastError == 997 )
          {
            v5 = (unsigned int)(v5 + 1);
          }
          else
          {
            CloseHandle(v7[v5]);
          }
        }
        else
        {
          UnregisterWait(*(HANDLE *)(*((_QWORD *)v8 + 22) + 24LL));
        }
      }
      v19 = *((_QWORD *)v8 + 22);
      if ( v19 )
      {
        v20 = *(void **)(v19 + 16);
        if ( v20 )
          CloseHandle(v20);
      }
      v21 = (void *)*((_QWORD *)v8 + 22);
      if ( v21 )
        free(v21);
      closesocket(*((_QWORD *)v8 + 20));
      FreeSSDPNetwork(v8);
    }
  }
  LeaveCriticalSection(&stru_180042200);
  if ( v7 )
  {
    if ( (_DWORD)v5 )
    {
      LODWORD(v12) = v5;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids,
          (unsigned int)v5);
      do
      {
        v13 = v12;
        if ( (unsigned int)v12 > 0x40 )
          v13 = 64;
        if ( WaitForMultipleObjects(v13, &v7[(unsigned int)(v5 - v12)], 1, 0xFFFFFFFF) == -1
          && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0 )
        {
          v22 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, v22);
        }
        v12 = (unsigned int)v12 - v13;
      }
      while ( (_DWORD)v12 );
      do
      {
        CloseHandle(v7[v12]);
        v12 = (unsigned int)(v12 + 1);
      }
      while ( (unsigned int)v12 < (unsigned int)v5 );
    }
    free(v7);
  }
}

```

## disassembly

```asm
0x1800183b0  push    rbx
0x1800183b2  push    rbp
0x1800183b3  push    rdi
0x1800183b4  push    r14
0x1800183b6  push    r15
0x1800183b8  sub     rsp, 20h
0x1800183bc  mov     rdi, rcx
0x1800183bf  mov     [rsp+48h+arg_10], r12
0x1800183c4  mov     rcx, [rcx+8]; Block
0x1800183c8  mov     [rsp+48h+arg_18], r13
0x1800183cd  test    rcx, rcx
0x1800183d0  jz      short loc_1800183D8
0x1800183d2  call    cs:__imp_free
0x1800183d8  mov     rdi, [rdi+10h]
0x1800183dc  lea     rcx, stru_180042200; lpCriticalSection
0x1800183e3  xor     r12d, r12d
0x1800183e6  xor     ebp, ebp
0x1800183e8  call    cs:__imp_EnterCriticalSection
0x1800183ee  mov     rbx, cs:Block
0x1800183f5  lea     r13, Block
0x1800183fc  cmp     rbx, r13
0x1800183ff  jz      short loc_18001841D
0x180018401  cmp     rdi, [rbx+0A0h]
0x180018408  jz      loc_1800184A8
0x18001840e  mov     rbx, [rbx]
0x180018411  cmp     rbx, r13
0x180018414  jnz     short loc_180018401
0x180018416  mov     rbx, cs:Block
0x18001841d  mov     ecx, r12d
0x180018420  shl     rcx, 3; Size
0x180018424  mov     [rsp+48h+arg_8], rsi
0x180018429  call    cs:__imp_malloc
0x18001842f  lea     r15, WPP_GLOBAL_Control
0x180018436  mov     r14, rax
0x180018439  cmp     rbx, r13
0x18001843c  jz      short loc_18001846E
0x18001843e  xchg    ax, ax
0x180018440  mov     rsi, rbx
0x180018443  mov     r15, rbx
0x180018446  mov     rbx, [rbx]
0x180018449  mov     r9, [rsi+0A0h]
0x180018450  cmp     rdi, r9
0x180018453  jnz     short loc_180018462
0x180018455  cmp     dword ptr [rsi+0ACh], 0
0x18001845c  jz      loc_180018519
0x180018462  cmp     rbx, r13
0x180018465  jnz     short loc_180018440
0x180018467  lea     r15, WPP_GLOBAL_Control
0x18001846e  lea     rcx, stru_180042200; lpCriticalSection
0x180018475  call    cs:__imp_LeaveCriticalSection
0x18001847b  mov     r13, [rsp+48h+arg_18]
0x180018480  mov     r12, [rsp+48h+arg_10]
0x180018485  test    r14, r14
0x180018488  jz      short loc_180018497
0x18001848a  test    ebp, ebp
0x18001848c  jnz     short loc_1800184BD
0x18001848e  mov     rcx, r14; Block
0x180018491  call    cs:__imp_free
0x180018497  mov     rsi, [rsp+48h+arg_8]
0x18001849c  add     rsp, 20h
0x1800184a0  pop     r15
0x1800184a2  pop     r14
0x1800184a4  pop     rdi
0x1800184a5  pop     rbp
0x1800184a6  pop     rbx
0x1800184a7  retn
0x1800184a8  sub     dword ptr [rbx+0ACh], 1
0x1800184af  jnz     loc_18001840E
0x1800184b5  inc     r12d
0x1800184b8  jmp     loc_18001840E
0x1800184bd  mov     ebx, ebp
0x1800184bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184c6  cmp     rcx, r15
0x1800184c9  jnz     loc_180018622
0x1800184cf  mov     esi, 40h ; '@'
0x1800184d4  mov     eax, ebp
0x1800184d6  cmp     ebx, esi
0x1800184d8  mov     edi, ebx
0x1800184da  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x1800184e0  cmova   edi, esi
0x1800184e3  mov     r8d, 1; bWaitAll
0x1800184e9  sub     eax, ebx
0x1800184eb  mov     ecx, edi; nCount
0x1800184ed  lea     rdx, [r14+rax*8]; lpHandles
0x1800184f1  call    cs:__imp_WaitForMultipleObjects
0x1800184f7  cmp     eax, 0FFFFFFFFh
0x1800184fa  jz      loc_18001864C
0x180018500  sub     ebx, edi
0x180018502  jnz     short loc_1800184D4
0x180018504  mov     rcx, [r14+rbx*8]; hObject
0x180018508  call    cs:__imp_CloseHandle
0x18001850e  inc     ebx
0x180018510  cmp     ebx, ebp
0x180018512  jb      short loc_180018504
0x180018514  jmp     loc_18001848E
0x180018519  mov     rcx, cs:WPP_GLOBAL_Control
0x180018520  lea     rax, WPP_GLOBAL_Control
0x180018527  cmp     rcx, rax
0x18001852a  jz      short loc_18001854A
0x18001852c  test    dword ptr [rcx+1Ch], 200h
0x180018533  jz      short loc_18001854A
0x180018535  mov     rcx, [rcx+10h]
0x180018539  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180018540  mov     edx, 25h ; '%'
0x180018545  call    WPP_SF_d
0x18001854a  mov     rax, [r15+8]
0x18001854e  mov     rcx, [r15]
0x180018551  mov     [rax], rcx
0x180018554  mov     [rcx+8], rax
0x180018558  mov     rax, [rsi+0B0h]
0x18001855f  test    rax, rax
0x180018562  jz      short loc_1800185DB
0x180018564  cmp     qword ptr [rax+18h], 0
0x180018569  jz      short loc_1800185DB
0x18001856b  test    r14, r14
0x18001856e  jz      short loc_1800185CA
0x180018570  cmp     ebp, r12d
0x180018573  jnb     short loc_1800185CA
0x180018575  xor     r9d, r9d; lpName
0x180018578  xor     r8d, r8d; bInitialState
0x18001857b  xor     edx, edx; bManualReset
0x18001857d  xor     ecx, ecx; lpEventAttributes
0x18001857f  call    cs:__imp_CreateEventA
0x180018585  mov     [r14+rbp*8], rax
0x180018589  lea     r15, [r14+rbp*8]
0x18001858d  test    rax, rax
0x180018590  jz      short loc_1800185CA
0x180018592  mov     rcx, [rsi+0B0h]
0x180018599  mov     rdx, rax; CompletionEvent
0x18001859c  mov     rcx, [rcx+18h]; WaitHandle
0x1800185a0  call    cs:__imp_UnregisterWaitEx
0x1800185a6  test    eax, eax
0x1800185a8  jnz     short loc_1800185C6
0x1800185aa  call    cs:__imp_GetLastError
0x1800185b0  test    eax, eax
0x1800185b2  jz      short loc_1800185C6
0x1800185b4  cmp     eax, 3E5h
0x1800185b9  jz      short loc_1800185C6
0x1800185bb  mov     rcx, [r15]; hObject
0x1800185be  call    cs:__imp_CloseHandle
0x1800185c4  jmp     short loc_1800185DB
0x1800185c6  inc     ebp
0x1800185c8  jmp     short loc_1800185DB
0x1800185ca  mov     rcx, [rsi+0B0h]
0x1800185d1  mov     rcx, [rcx+18h]; WaitHandle
0x1800185d5  call    cs:__imp_UnregisterWait
0x1800185db  mov     rax, [rsi+0B0h]
0x1800185e2  test    rax, rax
0x1800185e5  jz      short loc_1800185F6
0x1800185e7  mov     rcx, [rax+10h]; hObject
0x1800185eb  test    rcx, rcx
0x1800185ee  jz      short loc_1800185F6
0x1800185f0  call    cs:__imp_CloseHandle
0x1800185f6  mov     rcx, [rsi+0B0h]; Block
0x1800185fd  test    rcx, rcx
0x180018600  jz      short loc_180018608
0x180018602  call    cs:__imp_free
0x180018608  mov     rcx, [rsi+0A0h]; s
0x18001860f  call    cs:__imp_closesocket
0x180018615  mov     rcx, rsi; struct _SSDPNetwork *
0x180018618  call    ?FreeSSDPNetwork@@YAXPEAU_SSDPNetwork@@@Z; FreeSSDPNetwork(_SSDPNetwork *)
0x18001861d  jmp     loc_180018462
0x180018622  test    dword ptr [rcx+1Ch], 200h
0x180018629  jz      loc_1800184CF
0x18001862f  mov     rcx, [rcx+10h]
0x180018633  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18001863a  mov     edx, 1Bh
0x18001863f  mov     r9d, ebp
0x180018642  call    WPP_SF_d
0x180018647  jmp     loc_1800184CF
0x18001864c  mov     rax, cs:WPP_GLOBAL_Control
0x180018653  cmp     rax, r15
0x180018656  jz      loc_180018500
0x18001865c  test    byte ptr [rax+1Ch], 1
0x180018660  jz      loc_180018500
0x180018666  call    cs:__imp_GetLastError
0x18001866c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018673  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18001867a  mov     edx, 1Ch
0x18001867f  mov     r9d, eax
0x180018682  mov     rcx, [rcx+10h]
0x180018686  call    WPP_SF_d
0x18001868b  jmp     loc_180018500
```
