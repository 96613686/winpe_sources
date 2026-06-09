# CleanupListNetworkForReset(void * * *)

- ea: `0x18000f390`
- end: `0x18000f6ea`
- name: `?CleanupListNetworkForReset@@YAKPEAPEAPEAX@Z`
- size: `858`
- prototype: `unsigned int __fastcall(void ***)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ffa0`
- `0x180032480`

## callees

- `0x18000f390`
- `0x1800271fc`
- `0x180029df0`
- `0x180031218`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f4e0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f4ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f6d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f4e0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f4ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f6d9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f413`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000f413`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f51c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f51c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f3c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f3c8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000f5cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000f5cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f68a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f54f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f6ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f54f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f6ac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000f6c8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000f6c8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000f5f6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000f5f6`
- `WS2_32!__imp_closesocket` at `0x18000f4c8`
- `WS2_32!__imp_closesocket` at `0x18000f4c8`

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
  EnterCriticalSection(&stru_1800452F8);
  v4 = qword_1800452E8;
  if ( qword_1800452E8 != (struct _SSDPNetwork *)&qword_1800452E8 )
  {
    do
    {
      if ( *((_DWORD *)v4 + 38) != 1 && (*((_DWORD *)v4 + 43))-- == 1 )
        ++v1;
      v4 = *(struct _SSDPNetwork **)v4;
    }
    while ( v4 != (struct _SSDPNetwork *)&qword_1800452E8 );
    v4 = qword_1800452E8;
  }
  v5 = (void **)malloc(8LL * v1);
  while ( v4 != (struct _SSDPNetwork *)&qword_1800452E8 )
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
  LeaveCriticalSection(&stru_1800452F8);
  result = (unsigned int)v3;
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x18000f390  mov     [rsp+arg_18], rbx
0x18000f395  push    rbp
0x18000f396  push    r12
0x18000f398  push    r13
0x18000f39a  push    r14
0x18000f39c  push    r15
0x18000f39e  sub     rsp, 30h
0x18000f3a2  xor     r15d, r15d
0x18000f3a5  mov     r12, rcx
0x18000f3a8  xor     ebp, ebp
0x18000f3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3b1  lea     rax, WPP_GLOBAL_Control
0x18000f3b8  cmp     rcx, rax
0x18000f3bb  jnz     loc_18000F620
0x18000f3c1  lea     rcx, stru_1800452F8; lpCriticalSection
0x18000f3c8  call    cs:__imp_EnterCriticalSection
0x18000f3cf  nop     dword ptr [rax+rax+00h]
0x18000f3d4  mov     rbx, cs:qword_1800452E8
0x18000f3db  lea     r13, qword_1800452E8
0x18000f3e2  cmp     rbx, r13
0x18000f3e5  jz      short loc_18000F40C
0x18000f3e7  nop     word ptr [rax+rax+00000000h]
0x18000f3f0  cmp     dword ptr [rbx+98h], 1
0x18000f3f7  jnz     loc_18000F647
0x18000f3fd  mov     rbx, [rbx]
0x18000f400  cmp     rbx, r13
0x18000f403  jnz     short loc_18000F3F0
0x18000f405  mov     rbx, cs:qword_1800452E8
0x18000f40c  mov     ecx, r15d
0x18000f40f  shl     rcx, 3; Size
0x18000f413  call    cs:__imp_malloc
0x18000f41a  nop     dword ptr [rax+rax+00h]
0x18000f41f  mov     r14, rax
0x18000f422  cmp     rbx, r13
0x18000f425  jz      loc_18000F515
0x18000f42b  mov     [rsp+58h+arg_8], rsi
0x18000f430  lea     rax, WPP_GLOBAL_Control
0x18000f437  mov     [rsp+58h+arg_10], rdi
0x18000f43c  nop     dword ptr [rax+00h]
0x18000f440  mov     rsi, rbx
0x18000f443  mov     rdi, rbx
0x18000f446  mov     rbx, [rbx]
0x18000f449  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f450  cmp     rcx, rax
0x18000f453  jnz     loc_18000F560
0x18000f459  cmp     dword ptr [rdi+98h], 1
0x18000f460  jz      loc_18000F611
0x18000f466  cmp     dword ptr [rdi+0ACh], 0
0x18000f46d  jnz     loc_18000F611
0x18000f473  cmp     rcx, rax
0x18000f476  jnz     loc_18000F65C
0x18000f47c  mov     rax, [rsi+8]
0x18000f480  mov     rcx, [rsi]
0x18000f483  mov     [rax], rcx
0x18000f486  mov     [rcx+8], rax
0x18000f48a  mov     rax, [rdi+0B0h]
0x18000f491  test    rax, rax
0x18000f494  jz      short loc_18000F4A1
0x18000f496  cmp     qword ptr [rax+18h], 0
0x18000f49b  jnz     loc_18000F5AF
0x18000f4a1  mov     rax, [rdi+0B0h]
0x18000f4a8  test    rax, rax
0x18000f4ab  jnz     loc_18000F542
0x18000f4b1  mov     rcx, [rdi+0B0h]; Block
0x18000f4b8  test    rcx, rcx
0x18000f4bb  jnz     loc_18000F6D9
0x18000f4c1  mov     rcx, [rdi+0A0h]; s
0x18000f4c8  call    cs:__imp_closesocket
0x18000f4cf  nop     dword ptr [rax+rax+00h]
0x18000f4d4  mov     rcx, [rdi+0E0h]; Block
0x18000f4db  test    rcx, rcx
0x18000f4de  jz      short loc_18000F4EC
0x18000f4e0  call    cs:__imp_free
0x18000f4e7  nop     dword ptr [rax+rax+00h]
0x18000f4ec  mov     rcx, rdi; Block
0x18000f4ef  call    cs:__imp_free
0x18000f4f6  nop     dword ptr [rax+rax+00h]
0x18000f4fb  lea     rax, WPP_GLOBAL_Control
0x18000f502  cmp     rbx, r13
0x18000f505  jnz     loc_18000F440
0x18000f50b  mov     rdi, [rsp+58h+arg_10]
0x18000f510  mov     rsi, [rsp+58h+arg_8]
0x18000f515  lea     rcx, stru_1800452F8; lpCriticalSection
0x18000f51c  call    cs:__imp_LeaveCriticalSection
0x18000f523  nop     dword ptr [rax+rax+00h]
0x18000f528  mov     rbx, [rsp+58h+arg_18]
0x18000f52d  mov     eax, ebp
0x18000f52f  mov     [r12], r14
0x18000f533  add     rsp, 30h
0x18000f537  pop     r15
0x18000f539  pop     r14
0x18000f53b  pop     r13
0x18000f53d  pop     r12
0x18000f53f  pop     rbp
0x18000f540  retn
0x18000f542  mov     rcx, [rax+10h]; hObject
0x18000f546  test    rcx, rcx
0x18000f549  jz      loc_18000F4B1
0x18000f54f  call    cs:__imp_CloseHandle
0x18000f556  nop     dword ptr [rax+rax+00h]
0x18000f55b  jmp     loc_18000F4B1
0x18000f560  test    dword ptr [rcx+1Ch], 200h
0x18000f567  jz      loc_18000F459
0x18000f56d  mov     eax, [rdi+0ACh]
0x18000f573  mov     edx, 1Eh
0x18000f578  mov     r9d, [rdi+0A0h]
0x18000f57f  mov     rcx, [rcx+10h]
0x18000f583  mov     [rsp+58h+var_30], eax
0x18000f587  lea     r8d, [rax+1]
0x18000f58b  mov     [rsp+58h+var_38], r8d
0x18000f590  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000f597  call    WPP_SF_Ddd
0x18000f59c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5a3  lea     rax, WPP_GLOBAL_Control
0x18000f5aa  jmp     loc_18000F459
0x18000f5af  test    r14, r14
0x18000f5b2  jz      loc_18000F6BD
0x18000f5b8  cmp     ebp, r15d
0x18000f5bb  jnb     loc_18000F6BD
0x18000f5c1  xor     r9d, r9d; lpName
0x18000f5c4  xor     r8d, r8d; bInitialState
0x18000f5c7  xor     edx, edx; bManualReset
0x18000f5c9  xor     ecx, ecx; lpEventAttributes
0x18000f5cb  call    cs:__imp_CreateEventA
0x18000f5d2  nop     dword ptr [rax+rax+00h]
0x18000f5d7  mov     [r14+rbp*8], rax
0x18000f5db  lea     rsi, [r14+rbp*8]
0x18000f5df  mov     rdx, rax; CompletionEvent
0x18000f5e2  test    rax, rax
0x18000f5e5  jz      loc_18000F6BD
0x18000f5eb  mov     rcx, [rdi+0B0h]
0x18000f5f2  mov     rcx, [rcx+18h]; WaitHandle
0x18000f5f6  call    cs:__imp_UnregisterWaitEx
0x18000f5fd  nop     dword ptr [rax+rax+00h]
0x18000f602  test    eax, eax
0x18000f604  jz      loc_18000F68A
0x18000f60a  inc     ebp
0x18000f60c  jmp     loc_18000F4A1
0x18000f611  mov     dword ptr [rdi+98h], 1
0x18000f61b  jmp     loc_18000F502
0x18000f620  test    dword ptr [rcx+1Ch], 200h
0x18000f627  jz      loc_18000F3C1
0x18000f62d  mov     rcx, [rcx+10h]
0x18000f631  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000f638  mov     edx, 1Dh
0x18000f63d  call    WPP_SF_
0x18000f642  jmp     loc_18000F3C1
0x18000f647  sub     dword ptr [rbx+0ACh], 1
0x18000f64e  jnz     loc_18000F3FD
0x18000f654  inc     r15d
0x18000f657  jmp     loc_18000F3FD
0x18000f65c  test    dword ptr [rcx+1Ch], 200h
0x18000f663  jz      loc_18000F47C
0x18000f669  mov     r9d, [rdi+0A0h]
0x18000f670  lea     r8, WPP_fc0fb0ad4541302a90d7371a236586c8_Traceguids
0x18000f677  mov     rcx, [rcx+10h]
0x18000f67b  mov     edx, 1Fh
0x18000f680  call    WPP_SF_d
0x18000f685  jmp     loc_18000F47C
0x18000f68a  call    cs:__imp_GetLastError
0x18000f691  nop     dword ptr [rax+rax+00h]
0x18000f696  test    eax, eax
0x18000f698  jz      loc_18000F60A
0x18000f69e  cmp     eax, 3E5h
0x18000f6a3  jz      loc_18000F60A
0x18000f6a9  mov     rcx, [rsi]; hObject
0x18000f6ac  call    cs:__imp_CloseHandle
0x18000f6b3  nop     dword ptr [rax+rax+00h]
0x18000f6b8  jmp     loc_18000F4A1
0x18000f6bd  mov     rcx, [rdi+0B0h]
0x18000f6c4  mov     rcx, [rcx+18h]; WaitHandle
0x18000f6c8  call    cs:__imp_UnregisterWait
0x18000f6cf  nop     dword ptr [rax+rax+00h]
0x18000f6d4  jmp     loc_18000F4A1
0x18000f6d9  call    cs:__imp_free
0x18000f6e0  nop     dword ptr [rax+rax+00h]
0x18000f6e5  jmp     loc_18000F4C1
```
