# UnreferenceSocket(unsigned __int64)

- ea: `0x1800023d0`
- end: `0x1800026a0`
- name: `?UnreferenceSocket@@YAX_K@Z`
- size: `720`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180001530`
- `0x180002100`
- `0x1800029b0`
- `0x18000a498`
- `0x180017470`

## callees

- `0x1800023d0`
- `0x18000df80`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800024a1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002612`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800024a1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002612`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180002438`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180002438`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002485`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002485`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000258f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000258f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002676`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180002501`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180002501`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002518`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002600`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002518`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002600`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800025e5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800025e5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800025b0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800025b0`
- `WS2_32!__imp_closesocket` at `0x18000261f`
- `WS2_32!__imp_closesocket` at `0x18000261f`

## pseudocode

```c
void __fastcall UnreferenceSocket(__int64 a1)
{
  unsigned int v2; // r12d
  __int64 v3; // rbp
  struct _SSDPNetwork *v4; // rbx
  HANDLE *v5; // r14
  struct _SSDPNetwork *v6; // rsi
  struct _SSDPNetwork *v7; // r15
  __int64 v8; // r9
  __int64 v10; // rbx
  DWORD v11; // edi
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  HANDLE EventA; // rax
  DWORD LastError; // eax
  __int64 v17; // rax
  void *v18; // rcx
  void *v19; // rcx
  DWORD v20; // eax

  v2 = 0;
  v3 = 0;
  EnterCriticalSection(&stru_180042200);
  v4 = Block;
  if ( Block != (struct _SSDPNetwork *)&Block )
  {
    do
    {
      if ( a1 == *((_QWORD *)v4 + 20) && (*((_DWORD *)v4 + 43))-- == 1 )
        ++v2;
      v4 = *(struct _SSDPNetwork **)v4;
    }
    while ( v4 != (struct _SSDPNetwork *)&Block );
    v4 = Block;
  }
  v5 = (HANDLE *)malloc(8LL * v2);
  while ( v4 != (struct _SSDPNetwork *)&Block )
  {
    v6 = v4;
    v7 = v4;
    v4 = *(struct _SSDPNetwork **)v4;
    v8 = *((_QWORD *)v6 + 20);
    if ( a1 == v8 && !*((_DWORD *)v6 + 43) )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, v8);
      v12 = (_QWORD *)*((_QWORD *)v7 + 1);
      v13 = *(_QWORD *)v7;
      *v12 = *(_QWORD *)v7;
      *(_QWORD *)(v13 + 8) = v12;
      v14 = *((_QWORD *)v6 + 22);
      if ( v14 && *(_QWORD *)(v14 + 24) )
      {
        if ( v5 && (unsigned int)v3 < v2 && (EventA = CreateEventA(0, 0, 0, 0), (v5[v3] = EventA) != 0) )
        {
          if ( UnregisterWaitEx(*(HANDLE *)(*((_QWORD *)v6 + 22) + 24LL), EventA)
            || (LastError = GetLastError()) == 0
            || LastError == 997 )
          {
            v3 = (unsigned int)(v3 + 1);
          }
          else
          {
            CloseHandle(v5[v3]);
          }
        }
        else
        {
          UnregisterWait(*(HANDLE *)(*((_QWORD *)v6 + 22) + 24LL));
        }
      }
      v17 = *((_QWORD *)v6 + 22);
      if ( v17 )
      {
        v18 = *(void **)(v17 + 16);
        if ( v18 )
          CloseHandle(v18);
      }
      v19 = (void *)*((_QWORD *)v6 + 22);
      if ( v19 )
        free(v19);
      closesocket(*((_QWORD *)v6 + 20));
      FreeSSDPNetwork(v6);
    }
  }
  LeaveCriticalSection(&stru_180042200);
  if ( v5 )
  {
    if ( (_DWORD)v3 )
    {
      LODWORD(v10) = v3;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids,
          (unsigned int)v3);
      do
      {
        v11 = v10;
        if ( (unsigned int)v10 > 0x40 )
          v11 = 64;
        if ( WaitForMultipleObjects(v11, &v5[(unsigned int)(v3 - v10)], 1, 0xFFFFFFFF) == -1
          && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0 )
        {
          v20 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, v20);
        }
        v10 = (unsigned int)v10 - v11;
      }
      while ( (_DWORD)v10 );
      do
      {
        CloseHandle(v5[v10]);
        v10 = (unsigned int)(v10 + 1);
      }
      while ( (unsigned int)v10 < (unsigned int)v3 );
    }
    free(v5);
  }
}

```

## disassembly

```asm
0x1800023d0  push    rbx
0x1800023d2  push    rbp
0x1800023d3  push    rdi
0x1800023d4  push    r14
0x1800023d6  push    r15
0x1800023d8  sub     rsp, 20h
0x1800023dc  mov     rdi, rcx
0x1800023df  mov     [rsp+48h+arg_10], r12
0x1800023e4  lea     rcx, stru_180042200; lpCriticalSection
0x1800023eb  mov     [rsp+48h+arg_18], r13
0x1800023f0  xor     r12d, r12d
0x1800023f3  xor     ebp, ebp
0x1800023f5  call    cs:__imp_EnterCriticalSection
0x1800023fb  mov     rbx, cs:Block
0x180002402  lea     r13, Block
0x180002409  cmp     rbx, r13
0x18000240c  jz      short loc_18000242C
0x18000240e  xchg    ax, ax
0x180002410  cmp     rdi, [rbx+0A0h]
0x180002417  jz      loc_1800024B8
0x18000241d  mov     rbx, [rbx]
0x180002420  cmp     rbx, r13
0x180002423  jnz     short loc_180002410
0x180002425  mov     rbx, cs:Block
0x18000242c  mov     ecx, r12d
0x18000242f  shl     rcx, 3; Size
0x180002433  mov     [rsp+48h+arg_0], rsi
0x180002438  call    cs:__imp_malloc
0x18000243e  lea     r15, WPP_GLOBAL_Control
0x180002445  mov     r14, rax
0x180002448  cmp     rbx, r13
0x18000244b  jz      short loc_18000247E
0x18000244d  nop     dword ptr [rax]
0x180002450  mov     rsi, rbx
0x180002453  mov     r15, rbx
0x180002456  mov     rbx, [rbx]
0x180002459  mov     r9, [rsi+0A0h]
0x180002460  cmp     rdi, r9
0x180002463  jnz     short loc_180002472
0x180002465  cmp     dword ptr [rsi+0ACh], 0
0x18000246c  jz      loc_180002529
0x180002472  cmp     rbx, r13
0x180002475  jnz     short loc_180002450
0x180002477  lea     r15, WPP_GLOBAL_Control
0x18000247e  lea     rcx, stru_180042200; lpCriticalSection
0x180002485  call    cs:__imp_LeaveCriticalSection
0x18000248b  mov     r13, [rsp+48h+arg_18]
0x180002490  mov     r12, [rsp+48h+arg_10]
0x180002495  test    r14, r14
0x180002498  jz      short loc_1800024A7
0x18000249a  test    ebp, ebp
0x18000249c  jnz     short loc_1800024CD
0x18000249e  mov     rcx, r14; Block
0x1800024a1  call    cs:__imp_free
0x1800024a7  mov     rsi, [rsp+48h+arg_0]
0x1800024ac  add     rsp, 20h
0x1800024b0  pop     r15
0x1800024b2  pop     r14
0x1800024b4  pop     rdi
0x1800024b5  pop     rbp
0x1800024b6  pop     rbx
0x1800024b7  retn
0x1800024b8  sub     dword ptr [rbx+0ACh], 1
0x1800024bf  jnz     loc_18000241D
0x1800024c5  inc     r12d
0x1800024c8  jmp     loc_18000241D
0x1800024cd  mov     ebx, ebp
0x1800024cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024d6  cmp     rcx, r15
0x1800024d9  jnz     loc_180002632
0x1800024df  mov     esi, 40h ; '@'
0x1800024e4  mov     eax, ebp
0x1800024e6  cmp     ebx, esi
0x1800024e8  mov     edi, ebx
0x1800024ea  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x1800024f0  cmova   edi, esi
0x1800024f3  mov     r8d, 1; bWaitAll
0x1800024f9  sub     eax, ebx
0x1800024fb  mov     ecx, edi; nCount
0x1800024fd  lea     rdx, [r14+rax*8]; lpHandles
0x180002501  call    cs:__imp_WaitForMultipleObjects
0x180002507  cmp     eax, 0FFFFFFFFh
0x18000250a  jz      loc_18000265C
0x180002510  sub     ebx, edi
0x180002512  jnz     short loc_1800024E4
0x180002514  mov     rcx, [r14+rbx*8]; hObject
0x180002518  call    cs:__imp_CloseHandle
0x18000251e  inc     ebx
0x180002520  cmp     ebx, ebp
0x180002522  jb      short loc_180002514
0x180002524  jmp     loc_18000249E
0x180002529  mov     rcx, cs:WPP_GLOBAL_Control
0x180002530  lea     rax, WPP_GLOBAL_Control
0x180002537  cmp     rcx, rax
0x18000253a  jz      short loc_18000255A
0x18000253c  test    dword ptr [rcx+1Ch], 200h
0x180002543  jz      short loc_18000255A
0x180002545  mov     rcx, [rcx+10h]
0x180002549  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180002550  mov     edx, 25h ; '%'
0x180002555  call    WPP_SF_d
0x18000255a  mov     rax, [r15+8]
0x18000255e  mov     rcx, [r15]
0x180002561  mov     [rax], rcx
0x180002564  mov     [rcx+8], rax
0x180002568  mov     rax, [rsi+0B0h]
0x18000256f  test    rax, rax
0x180002572  jz      short loc_1800025EB
0x180002574  cmp     qword ptr [rax+18h], 0
0x180002579  jz      short loc_1800025EB
0x18000257b  test    r14, r14
0x18000257e  jz      short loc_1800025DA
0x180002580  cmp     ebp, r12d
0x180002583  jnb     short loc_1800025DA
0x180002585  xor     r9d, r9d; lpName
0x180002588  xor     r8d, r8d; bInitialState
0x18000258b  xor     edx, edx; bManualReset
0x18000258d  xor     ecx, ecx; lpEventAttributes
0x18000258f  call    cs:__imp_CreateEventA
0x180002595  mov     [r14+rbp*8], rax
0x180002599  lea     r15, [r14+rbp*8]
0x18000259d  test    rax, rax
0x1800025a0  jz      short loc_1800025DA
0x1800025a2  mov     rcx, [rsi+0B0h]
0x1800025a9  mov     rdx, rax; CompletionEvent
0x1800025ac  mov     rcx, [rcx+18h]; WaitHandle
0x1800025b0  call    cs:__imp_UnregisterWaitEx
0x1800025b6  test    eax, eax
0x1800025b8  jnz     short loc_1800025D6
0x1800025ba  call    cs:__imp_GetLastError
0x1800025c0  test    eax, eax
0x1800025c2  jz      short loc_1800025D6
0x1800025c4  cmp     eax, 3E5h
0x1800025c9  jz      short loc_1800025D6
0x1800025cb  mov     rcx, [r15]; hObject
0x1800025ce  call    cs:__imp_CloseHandle
0x1800025d4  jmp     short loc_1800025EB
0x1800025d6  inc     ebp
0x1800025d8  jmp     short loc_1800025EB
0x1800025da  mov     rcx, [rsi+0B0h]
0x1800025e1  mov     rcx, [rcx+18h]; WaitHandle
0x1800025e5  call    cs:__imp_UnregisterWait
0x1800025eb  mov     rax, [rsi+0B0h]
0x1800025f2  test    rax, rax
0x1800025f5  jz      short loc_180002606
0x1800025f7  mov     rcx, [rax+10h]; hObject
0x1800025fb  test    rcx, rcx
0x1800025fe  jz      short loc_180002606
0x180002600  call    cs:__imp_CloseHandle
0x180002606  mov     rcx, [rsi+0B0h]; Block
0x18000260d  test    rcx, rcx
0x180002610  jz      short loc_180002618
0x180002612  call    cs:__imp_free
0x180002618  mov     rcx, [rsi+0A0h]; s
0x18000261f  call    cs:__imp_closesocket
0x180002625  mov     rcx, rsi; struct _SSDPNetwork *
0x180002628  call    ?FreeSSDPNetwork@@YAXPEAU_SSDPNetwork@@@Z; FreeSSDPNetwork(_SSDPNetwork *)
0x18000262d  jmp     loc_180002472
0x180002632  test    dword ptr [rcx+1Ch], 200h
0x180002639  jz      loc_1800024DF
0x18000263f  mov     rcx, [rcx+10h]
0x180002643  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000264a  mov     edx, 1Bh
0x18000264f  mov     r9d, ebp
0x180002652  call    WPP_SF_d
0x180002657  jmp     loc_1800024DF
0x18000265c  mov     rax, cs:WPP_GLOBAL_Control
0x180002663  cmp     rax, r15
0x180002666  jz      loc_180002510
0x18000266c  test    byte ptr [rax+1Ch], 1
0x180002670  jz      loc_180002510
0x180002676  call    cs:__imp_GetLastError
0x18000267c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002683  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000268a  mov     edx, 1Ch
0x18000268f  mov     r9d, eax
0x180002692  mov     rcx, [rcx+10h]
0x180002696  call    WPP_SF_d
0x18000269b  jmp     loc_180002510
```
