# UnreferenceSocket(unsigned __int64)

- ea: `0x180003a60`
- end: `0x180003db0`
- name: `?UnreferenceSocket@@YAX_K@Z`
- size: `848`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001580`
- `0x1800025f0`
- `0x180002b9c`
- `0x180003770`
- `0x1800040e0`
- `0x18000bc1c`

## callees

- `0x180003a60`
- `0x18000f350`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003b57`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003d10`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003b57`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003d10`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003ad8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003ad8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a85`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180003c69`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180003c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d80`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180003bbe`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180003bbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003be4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003be4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180003cd7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180003cd7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180003c90`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180003c90`
- `WS2_32!__imp_closesocket` at `0x180003d23`
- `WS2_32!__imp_closesocket` at `0x180003d23`

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
  EnterCriticalSection(&stru_1800452F8);
  v4 = qword_1800452E8;
  if ( qword_1800452E8 != (struct _SSDPNetwork *)&qword_1800452E8 )
  {
    do
    {
      if ( a1 == *((_QWORD *)v4 + 20) && (*((_DWORD *)v4 + 43))-- == 1 )
        ++v2;
      v4 = *(struct _SSDPNetwork **)v4;
    }
    while ( v4 != (struct _SSDPNetwork *)&qword_1800452E8 );
    v4 = qword_1800452E8;
  }
  v5 = (HANDLE *)malloc(8LL * v2);
  while ( v4 != (struct _SSDPNetwork *)&qword_1800452E8 )
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
  LeaveCriticalSection(&stru_1800452F8);
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
0x180003a60  push    rbx
0x180003a62  push    rbp
0x180003a63  push    rdi
0x180003a64  push    r14
0x180003a66  push    r15
0x180003a68  sub     rsp, 20h
0x180003a6c  mov     rdi, rcx
0x180003a6f  mov     [rsp+48h+arg_10], r12
0x180003a74  lea     rcx, stru_1800452F8; lpCriticalSection
0x180003a7b  mov     [rsp+48h+arg_18], r13
0x180003a80  xor     r12d, r12d
0x180003a83  xor     ebp, ebp
0x180003a85  call    cs:__imp_EnterCriticalSection
0x180003a8c  nop     dword ptr [rax+rax+00h]
0x180003a91  mov     rbx, cs:qword_1800452E8
0x180003a98  lea     r13, qword_1800452E8
0x180003a9f  cmp     rbx, r13
0x180003aa2  jz      short loc_180003ACC
0x180003aa4  nop     dword ptr [rax+00h]
0x180003aa8  nop     dword ptr [rax+rax+00000000h]
0x180003ab0  cmp     rdi, [rbx+0A0h]
0x180003ab7  jz      loc_180003B75
0x180003abd  mov     rbx, [rbx]
0x180003ac0  cmp     rbx, r13
0x180003ac3  jnz     short loc_180003AB0
0x180003ac5  mov     rbx, cs:qword_1800452E8
0x180003acc  mov     ecx, r12d
0x180003acf  shl     rcx, 3; Size
0x180003ad3  mov     [rsp+48h+arg_0], rsi
0x180003ad8  call    cs:__imp_malloc
0x180003adf  nop     dword ptr [rax+rax+00h]
0x180003ae4  lea     r15, WPP_GLOBAL_Control
0x180003aeb  mov     r14, rax
0x180003aee  cmp     rbx, r13
0x180003af1  jz      short loc_180003B2E
0x180003af3  nop     dword ptr [rax+00h]
0x180003af7  nop     word ptr [rax+rax+00000000h]
0x180003b00  mov     rsi, rbx
0x180003b03  mov     r15, rbx
0x180003b06  mov     rbx, [rbx]
0x180003b09  mov     r9, [rsi+0A0h]
0x180003b10  cmp     rdi, r9
0x180003b13  jnz     short loc_180003B22
0x180003b15  cmp     dword ptr [rsi+0ACh], 0
0x180003b1c  jz      loc_180003BFB
0x180003b22  cmp     rbx, r13
0x180003b25  jnz     short loc_180003B00
0x180003b27  lea     r15, WPP_GLOBAL_Control
0x180003b2e  lea     rcx, stru_1800452F8; lpCriticalSection
0x180003b35  call    cs:__imp_LeaveCriticalSection
0x180003b3c  nop     dword ptr [rax+rax+00h]
0x180003b41  mov     r13, [rsp+48h+arg_18]
0x180003b46  mov     r12, [rsp+48h+arg_10]
0x180003b4b  test    r14, r14
0x180003b4e  jz      short loc_180003B63
0x180003b50  test    ebp, ebp
0x180003b52  jnz     short loc_180003B8A
0x180003b54  mov     rcx, r14; Block
0x180003b57  call    cs:__imp_free
0x180003b5e  nop     dword ptr [rax+rax+00h]
0x180003b63  mov     rsi, [rsp+48h+arg_0]
0x180003b68  add     rsp, 20h
0x180003b6c  pop     r15
0x180003b6e  pop     r14
0x180003b70  pop     rdi
0x180003b71  pop     rbp
0x180003b72  pop     rbx
0x180003b73  retn
0x180003b75  sub     dword ptr [rbx+0ACh], 1
0x180003b7c  jnz     loc_180003ABD
0x180003b82  inc     r12d
0x180003b85  jmp     loc_180003ABD
0x180003b8a  mov     ebx, ebp
0x180003b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b93  cmp     rcx, r15
0x180003b96  jnz     loc_180003D3C
0x180003b9c  mov     esi, 40h ; '@'
0x180003ba1  mov     eax, ebp
0x180003ba3  cmp     ebx, esi
0x180003ba5  mov     edi, ebx
0x180003ba7  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180003bad  cmova   edi, esi
0x180003bb0  mov     r8d, 1; bWaitAll
0x180003bb6  sub     eax, ebx
0x180003bb8  mov     ecx, edi; nCount
0x180003bba  lea     rdx, [r14+rax*8]; lpHandles
0x180003bbe  call    cs:__imp_WaitForMultipleObjects
0x180003bc5  nop     dword ptr [rax+rax+00h]
0x180003bca  cmp     eax, 0FFFFFFFFh
0x180003bcd  jz      loc_180003D66
0x180003bd3  sub     ebx, edi
0x180003bd5  jnz     short loc_180003BA1
0x180003bd7  nop     word ptr [rax+rax+00000000h]
0x180003be0  mov     rcx, [r14+rbx*8]; hObject
0x180003be4  call    cs:__imp_CloseHandle
0x180003beb  nop     dword ptr [rax+rax+00h]
0x180003bf0  inc     ebx
0x180003bf2  cmp     ebx, ebp
0x180003bf4  jb      short loc_180003BE0
0x180003bf6  jmp     loc_180003B54
0x180003bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c02  lea     rax, WPP_GLOBAL_Control
0x180003c09  cmp     rcx, rax
0x180003c0c  jz      short loc_180003C2C
0x180003c0e  test    dword ptr [rcx+1Ch], 200h
0x180003c15  jz      short loc_180003C2C
0x180003c17  mov     rcx, [rcx+10h]
0x180003c1b  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180003c22  mov     edx, 25h ; '%'
0x180003c27  call    WPP_SF_d
0x180003c2c  mov     rax, [r15+8]
0x180003c30  mov     rcx, [r15]
0x180003c33  mov     [rax], rcx
0x180003c36  mov     [rcx+8], rax
0x180003c3a  mov     rax, [rsi+0B0h]
0x180003c41  test    rax, rax
0x180003c44  jz      loc_180003CE3
0x180003c4a  cmp     qword ptr [rax+18h], 0
0x180003c4f  jz      loc_180003CE3
0x180003c55  test    r14, r14
0x180003c58  jz      short loc_180003CCC
0x180003c5a  cmp     ebp, r12d
0x180003c5d  jnb     short loc_180003CCC
0x180003c5f  xor     r9d, r9d; lpName
0x180003c62  xor     r8d, r8d; bInitialState
0x180003c65  xor     edx, edx; bManualReset
0x180003c67  xor     ecx, ecx; lpEventAttributes
0x180003c69  call    cs:__imp_CreateEventA
0x180003c70  nop     dword ptr [rax+rax+00h]
0x180003c75  mov     [r14+rbp*8], rax
0x180003c79  lea     r15, [r14+rbp*8]
0x180003c7d  test    rax, rax
0x180003c80  jz      short loc_180003CCC
0x180003c82  mov     rcx, [rsi+0B0h]
0x180003c89  mov     rdx, rax; CompletionEvent
0x180003c8c  mov     rcx, [rcx+18h]; WaitHandle
0x180003c90  call    cs:__imp_UnregisterWaitEx
0x180003c97  nop     dword ptr [rax+rax+00h]
0x180003c9c  test    eax, eax
0x180003c9e  jnz     short loc_180003CC8
0x180003ca0  call    cs:__imp_GetLastError
0x180003ca7  nop     dword ptr [rax+rax+00h]
0x180003cac  test    eax, eax
0x180003cae  jz      short loc_180003CC8
0x180003cb0  cmp     eax, 3E5h
0x180003cb5  jz      short loc_180003CC8
0x180003cb7  mov     rcx, [r15]; hObject
0x180003cba  call    cs:__imp_CloseHandle
0x180003cc1  nop     dword ptr [rax+rax+00h]
0x180003cc6  jmp     short loc_180003CE3
0x180003cc8  inc     ebp
0x180003cca  jmp     short loc_180003CE3
0x180003ccc  mov     rcx, [rsi+0B0h]
0x180003cd3  mov     rcx, [rcx+18h]; WaitHandle
0x180003cd7  call    cs:__imp_UnregisterWait
0x180003cde  nop     dword ptr [rax+rax+00h]
0x180003ce3  mov     rax, [rsi+0B0h]
0x180003cea  test    rax, rax
0x180003ced  jz      short loc_180003D04
0x180003cef  mov     rcx, [rax+10h]; hObject
0x180003cf3  test    rcx, rcx
0x180003cf6  jz      short loc_180003D04
0x180003cf8  call    cs:__imp_CloseHandle
0x180003cff  nop     dword ptr [rax+rax+00h]
0x180003d04  mov     rcx, [rsi+0B0h]; Block
0x180003d0b  test    rcx, rcx
0x180003d0e  jz      short loc_180003D1C
0x180003d10  call    cs:__imp_free
0x180003d17  nop     dword ptr [rax+rax+00h]
0x180003d1c  mov     rcx, [rsi+0A0h]; s
0x180003d23  call    cs:__imp_closesocket
0x180003d2a  nop     dword ptr [rax+rax+00h]
0x180003d2f  mov     rcx, rsi; struct _SSDPNetwork *
0x180003d32  call    ?FreeSSDPNetwork@@YAXPEAU_SSDPNetwork@@@Z; FreeSSDPNetwork(_SSDPNetwork *)
0x180003d37  jmp     loc_180003B22
0x180003d3c  test    dword ptr [rcx+1Ch], 200h
0x180003d43  jz      loc_180003B9C
0x180003d49  mov     rcx, [rcx+10h]
0x180003d4d  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180003d54  mov     edx, 1Bh
0x180003d59  mov     r9d, ebp
0x180003d5c  call    WPP_SF_d
0x180003d61  jmp     loc_180003B9C
0x180003d66  mov     rax, cs:WPP_GLOBAL_Control
0x180003d6d  cmp     rax, r15
0x180003d70  jz      loc_180003BD3
0x180003d76  test    byte ptr [rax+1Ch], 1
0x180003d7a  jz      loc_180003BD3
0x180003d80  call    cs:__imp_GetLastError
0x180003d87  nop     dword ptr [rax+rax+00h]
0x180003d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d93  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x180003d9a  mov     edx, 1Ch
0x180003d9f  mov     r9d, eax
0x180003da2  mov     rcx, [rcx+10h]
0x180003da6  call    WPP_SF_d
0x180003dab  jmp     loc_180003BD3
```
