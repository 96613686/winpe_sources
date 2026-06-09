# CleanupListNetworkForReset(void * * *)

- ea: `0x18000dfb0`
- end: `0x18000e2b3`
- name: `?CleanupListNetworkForReset@@YAKPEAPEAPEAX@Z`
- size: `771`
- prototype: `__int64 __fastcall(void ***)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000eb10`
- `0x180030130`

## callees

- `0x18000dfb0`
- `0x1800255a8`
- `0x180028000`
- `0x18002efd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0e6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e2a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0e6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e0ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e2a8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e024`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e024`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e116`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e116`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dfe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dfe8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000e1b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000e1b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e26b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e26b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e287`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e287`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000e29d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000e29d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000e1dd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000e1dd`
- `WS2_32!__imp_closesocket` at `0x18000e0d4`
- `WS2_32!__imp_closesocket` at `0x18000e0d4`

## pseudocode

```c
__int64 __fastcall CleanupListNetworkForReset(void ***a1)
{
  unsigned int v1; // r15d
  __int64 v3; // rbp
  struct _SSDPNetwork *v4; // rbx
  void **v5; // r14
  struct _SSDPNetwork *v6; // rsi
  struct _SSDPNetwork *v7; // rdi
  LPCSTR v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  void *v13; // rcx
  void *v14; // rcx
  __int64 result; // rax
  void *v16; // rcx
  HANDLE EventA; // rax
  DWORD LastError; // eax

  v1 = 0;
  v3 = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids);
  EnterCriticalSection(&stru_180042200);
  v4 = Block;
  if ( Block != (struct _SSDPNetwork *)&Block )
  {
    do
    {
      if ( *((_DWORD *)v4 + 38) != 1 && (*((_DWORD *)v4 + 43))-- == 1 )
        ++v1;
      v4 = *(struct _SSDPNetwork **)v4;
    }
    while ( v4 != (struct _SSDPNetwork *)&Block );
    v4 = Block;
  }
  v5 = (void **)malloc(8LL * v1);
  while ( v4 != (struct _SSDPNetwork *)&Block )
  {
    v6 = v4;
    v7 = v4;
    v4 = *(struct _SSDPNetwork **)v4;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_Ddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids,
        *((unsigned int *)v7 + 40),
        *((_DWORD *)v7 + 43) + 1,
        *((_DWORD *)v7 + 43));
      v8 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)v7 + 38) == 1 || *((_DWORD *)v7 + 43) )
    {
      *((_DWORD *)v7 + 38) = 1;
    }
    else
    {
      if ( v8 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)v8 + 2), 31, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids, *((unsigned int *)v7 + 40));
      v9 = (_QWORD *)*((_QWORD *)v6 + 1);
      v10 = *(_QWORD *)v6;
      *v9 = *(_QWORD *)v6;
      *(_QWORD *)(v10 + 8) = v9;
      v11 = *((_QWORD *)v7 + 22);
      if ( v11 && *(_QWORD *)(v11 + 24) )
      {
        if ( v5 && (unsigned int)v3 < v1 && (EventA = CreateEventA(0, 0, 0, 0), (v5[v3] = EventA) != 0) )
        {
          if ( UnregisterWaitEx(*(HANDLE *)(*((_QWORD *)v7 + 22) + 24LL), EventA)
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
          UnregisterWait(*(HANDLE *)(*((_QWORD *)v7 + 22) + 24LL));
        }
      }
      v12 = *((_QWORD *)v7 + 22);
      if ( v12 )
      {
        v16 = *(void **)(v12 + 16);
        if ( v16 )
          CloseHandle(v16);
      }
      v13 = (void *)*((_QWORD *)v7 + 22);
      if ( v13 )
        free(v13);
      closesocket(*((_QWORD *)v7 + 20));
      v14 = (void *)*((_QWORD *)v7 + 28);
      if ( v14 )
        free(v14);
      free(v7);
    }
  }
  LeaveCriticalSection(&stru_180042200);
  result = (unsigned int)v3;
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x18000dfb0  mov     [rsp+arg_18], rbx
0x18000dfb5  push    rbp
0x18000dfb6  push    r12
0x18000dfb8  push    r13
0x18000dfba  push    r14
0x18000dfbc  push    r15
0x18000dfbe  sub     rsp, 30h
0x18000dfc2  xor     r15d, r15d
0x18000dfc5  mov     r12, rcx
0x18000dfc8  xor     ebp, ebp
0x18000dfca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfd1  lea     rax, WPP_GLOBAL_Control
0x18000dfd8  cmp     rcx, rax
0x18000dfdb  jnz     loc_18000E201
0x18000dfe1  lea     rcx, stru_180042200; lpCriticalSection
0x18000dfe8  call    cs:__imp_EnterCriticalSection
0x18000dfee  mov     rbx, cs:Block
0x18000dff5  lea     r13, Block
0x18000dffc  cmp     rbx, r13
0x18000dfff  jz      short loc_18000E01D
0x18000e001  cmp     dword ptr [rbx+98h], 1
0x18000e008  jnz     loc_18000E228
0x18000e00e  mov     rbx, [rbx]
0x18000e011  cmp     rbx, r13
0x18000e014  jnz     short loc_18000E001
0x18000e016  mov     rbx, cs:Block
0x18000e01d  mov     ecx, r15d
0x18000e020  shl     rcx, 3; Size
0x18000e024  call    cs:__imp_malloc
0x18000e02a  mov     r14, rax
0x18000e02d  cmp     rbx, r13
0x18000e030  jz      loc_18000E10F
0x18000e036  mov     [rsp+58h+arg_8], rsi
0x18000e03b  lea     rax, WPP_GLOBAL_Control
0x18000e042  mov     [rsp+58h+arg_10], rdi
0x18000e047  nop     word ptr [rax+rax+00000000h]
0x18000e050  mov     rsi, rbx
0x18000e053  mov     rdi, rbx
0x18000e056  mov     rbx, [rbx]
0x18000e059  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e060  cmp     rcx, rax
0x18000e063  jnz     loc_18000E14D
0x18000e069  cmp     dword ptr [rdi+98h], 1
0x18000e070  jz      loc_18000E1F2
0x18000e076  cmp     dword ptr [rdi+0ACh], 0
0x18000e07d  jnz     loc_18000E1F2
0x18000e083  cmp     rcx, rax
0x18000e086  jnz     loc_18000E23D
0x18000e08c  mov     rax, [rsi+8]
0x18000e090  mov     rcx, [rsi]
0x18000e093  mov     [rax], rcx
0x18000e096  mov     [rcx+8], rax
0x18000e09a  mov     rax, [rdi+0B0h]
0x18000e0a1  test    rax, rax
0x18000e0a4  jz      short loc_18000E0B1
0x18000e0a6  cmp     qword ptr [rax+18h], 0
0x18000e0ab  jnz     loc_18000E19C
0x18000e0b1  mov     rax, [rdi+0B0h]
0x18000e0b8  test    rax, rax
0x18000e0bb  jnz     short loc_18000E135
0x18000e0bd  mov     rcx, [rdi+0B0h]; Block
0x18000e0c4  test    rcx, rcx
0x18000e0c7  jnz     loc_18000E2A8
0x18000e0cd  mov     rcx, [rdi+0A0h]; s
0x18000e0d4  call    cs:__imp_closesocket
0x18000e0da  mov     rcx, [rdi+0E0h]; Block
0x18000e0e1  test    rcx, rcx
0x18000e0e4  jz      short loc_18000E0EC
0x18000e0e6  call    cs:__imp_free
0x18000e0ec  mov     rcx, rdi; Block
0x18000e0ef  call    cs:__imp_free
0x18000e0f5  lea     rax, WPP_GLOBAL_Control
0x18000e0fc  cmp     rbx, r13
0x18000e0ff  jnz     loc_18000E050
0x18000e105  mov     rdi, [rsp+58h+arg_10]
0x18000e10a  mov     rsi, [rsp+58h+arg_8]
0x18000e10f  lea     rcx, stru_180042200; lpCriticalSection
0x18000e116  call    cs:__imp_LeaveCriticalSection
0x18000e11c  mov     rbx, [rsp+58h+arg_18]
0x18000e121  mov     eax, ebp
0x18000e123  mov     [r12], r14
0x18000e127  add     rsp, 30h
0x18000e12b  pop     r15
0x18000e12d  pop     r14
0x18000e12f  pop     r13
0x18000e131  pop     r12
0x18000e133  pop     rbp
0x18000e134  retn
0x18000e135  mov     rcx, [rax+10h]; hObject
0x18000e139  test    rcx, rcx
0x18000e13c  jz      loc_18000E0BD
0x18000e142  call    cs:__imp_CloseHandle
0x18000e148  jmp     loc_18000E0BD
0x18000e14d  test    dword ptr [rcx+1Ch], 200h
0x18000e154  jz      loc_18000E069
0x18000e15a  mov     eax, [rdi+0ACh]
0x18000e160  mov     edx, 1Eh
0x18000e165  mov     r9d, [rdi+0A0h]
0x18000e16c  mov     rcx, [rcx+10h]
0x18000e170  mov     [rsp+58h+var_30], eax
0x18000e174  lea     r8d, [rax+1]
0x18000e178  mov     [rsp+58h+var_38], r8d
0x18000e17d  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000e184  call    WPP_SF_Ddd
0x18000e189  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e190  lea     rax, WPP_GLOBAL_Control
0x18000e197  jmp     loc_18000E069
0x18000e19c  test    r14, r14
0x18000e19f  jz      loc_18000E292
0x18000e1a5  cmp     ebp, r15d
0x18000e1a8  jnb     loc_18000E292
0x18000e1ae  xor     r9d, r9d; lpName
0x18000e1b1  xor     r8d, r8d; bInitialState
0x18000e1b4  xor     edx, edx; bManualReset
0x18000e1b6  xor     ecx, ecx; lpEventAttributes
0x18000e1b8  call    cs:__imp_CreateEventA
0x18000e1be  mov     [r14+rbp*8], rax
0x18000e1c2  lea     rsi, [r14+rbp*8]
0x18000e1c6  mov     rdx, rax; CompletionEvent
0x18000e1c9  test    rax, rax
0x18000e1cc  jz      loc_18000E292
0x18000e1d2  mov     rcx, [rdi+0B0h]
0x18000e1d9  mov     rcx, [rcx+18h]; WaitHandle
0x18000e1dd  call    cs:__imp_UnregisterWaitEx
0x18000e1e3  test    eax, eax
0x18000e1e5  jz      loc_18000E26B
0x18000e1eb  inc     ebp
0x18000e1ed  jmp     loc_18000E0B1
0x18000e1f2  mov     dword ptr [rdi+98h], 1
0x18000e1fc  jmp     loc_18000E0FC
0x18000e201  test    dword ptr [rcx+1Ch], 200h
0x18000e208  jz      loc_18000DFE1
0x18000e20e  mov     rcx, [rcx+10h]
0x18000e212  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000e219  mov     edx, 1Dh
0x18000e21e  call    WPP_SF_
0x18000e223  jmp     loc_18000DFE1
0x18000e228  sub     dword ptr [rbx+0ACh], 1
0x18000e22f  jnz     loc_18000E00E
0x18000e235  inc     r15d
0x18000e238  jmp     loc_18000E00E
0x18000e23d  test    dword ptr [rcx+1Ch], 200h
0x18000e244  jz      loc_18000E08C
0x18000e24a  mov     r9d, [rdi+0A0h]
0x18000e251  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000e258  mov     rcx, [rcx+10h]
0x18000e25c  mov     edx, 1Fh
0x18000e261  call    WPP_SF_d
0x18000e266  jmp     loc_18000E08C
0x18000e26b  call    cs:__imp_GetLastError
0x18000e271  test    eax, eax
0x18000e273  jz      loc_18000E1EB
0x18000e279  cmp     eax, 3E5h
0x18000e27e  jz      loc_18000E1EB
0x18000e284  mov     rcx, [rsi]; hObject
0x18000e287  call    cs:__imp_CloseHandle
0x18000e28d  jmp     loc_18000E0B1
0x18000e292  mov     rcx, [rdi+0B0h]
0x18000e299  mov     rcx, [rcx+18h]; WaitHandle
0x18000e29d  call    cs:__imp_UnregisterWait
0x18000e2a3  jmp     loc_18000E0B1
0x18000e2a8  call    cs:__imp_free
0x18000e2ae  jmp     loc_18000E0CD
```
