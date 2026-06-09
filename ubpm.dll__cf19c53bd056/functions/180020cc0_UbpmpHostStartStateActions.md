# UbpmpHostStartStateActions

- ea: `0x180020cc0`
- end: `0x180020e82`
- name: `UbpmpHostStartStateActions`
- size: `450`
- prototype: `unsigned int __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180021060`

## callees

- `0x180020cc0`
- `0x180030cec`
- `0x180032e38`
- `0x18003ca00`
- `0x18003cbc0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180020cd8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180020cd8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180020d3a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180020d3a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180020d23`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180020d23`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180020da4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180020da4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020cde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020cde`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020d78`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020dcc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020d78`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180020dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020dc0`
- `RPCRT4!RpcAsyncAbortCall` at `0x180020e3d`
- `RPCRT4!RpcAsyncAbortCall` at `0x180020e3d`

## pseudocode

```c
unsigned int __fastcall UbpmpHostStartStateActions(__int64 a1, int a2)
{
  struct _RPC_ASYNC_STATE *v4; // rsi
  char v5; // cl
  PVOID *v6; // rcx
  unsigned int result; // eax
  void *v8; // rcx
  __int64 v9; // rbx
  DWORD ProcessId; // eax
  __int64 v11; // r8
  DWORD LastError; // ebx
  DWORD v13; // eax

  v4 = 0;
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_18004CF18 = GetCurrentThreadId();
  if ( (*(_BYTE *)(a1 + 104) & 0x30) != 0x30 )
    goto LABEL_8;
  v5 = *(_BYTE *)(a1 + 104) & 0xDF;
  *(_BYTE *)(a1 + 104) = v5;
  if ( a2 )
    goto LABEL_3;
  *(_BYTE *)(a1 + 104) = v5 | 0x40;
  v8 = *(void **)(a1 + 24);
  if ( !v8 )
    goto LABEL_3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v9 = *(_QWORD *)(a1 + 56);
    ProcessId = GetProcessId(v8);
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, v11, ProcessId, v9);
  }
  if ( TerminateProcess(*(HANDLE *)(a1 + 24), 0x42Bu) )
    goto LABEL_18;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    v13 = GetProcessId(*(HANDLE *)(a1 + 24));
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v13, LastError);
LABEL_18:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)(a1 + 56) )
  {
    v4 = *(struct _RPC_ASYNC_STATE **)(a1 + 56);
    *(_QWORD *)(a1 + 56) = 0;
LABEL_3:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 )
    WPP_SF_qd(v6[2], 184);
  WakeAllConditionVariable(&g_cvHostStartedup);
LABEL_8:
  dword_18004CF18 = 0;
  result = RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  if ( v4 )
  {
    result = RpcAsyncAbortCall(v4, 0x42Bu);
    if ( result )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 185,
                 WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                 result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180020cc0  push    rbx
0x180020cc2  push    rsi
0x180020cc3  push    rdi
0x180020cc4  push    r14
0x180020cc6  sub     rsp, 38h
0x180020cca  mov     rdi, rcx
0x180020ccd  mov     ebx, edx
0x180020ccf  lea     rcx, g_TaskHostContextListLock
0x180020cd6  xor     esi, esi
0x180020cd8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180020cde  call    cs:__imp_GetCurrentThreadId
0x180020ce4  mov     cs:dword_18004CF18, eax
0x180020cea  lea     r14, WPP_GLOBAL_Control
0x180020cf1  mov     cl, [rdi+68h]
0x180020cf4  mov     al, cl
0x180020cf6  and     al, 30h
0x180020cf8  cmp     al, 30h ; '0'
0x180020cfa  jnz     short loc_180020D29
0x180020cfc  and     cl, 0DFh
0x180020cff  mov     [rdi+68h], cl
0x180020d02  test    ebx, ebx
0x180020d04  jz      short loc_180020D53
0x180020d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d0d  cmp     rcx, r14
0x180020d10  jz      short loc_180020D1C
0x180020d12  test    byte ptr [rcx+1Ch], 80h
0x180020d16  jnz     loc_180020E17
0x180020d1c  lea     rcx, ?g_cvHostStartedup@@3U_RTL_CONDITION_VARIABLE@@A; ConditionVariable
0x180020d23  call    cs:__imp_WakeAllConditionVariable
0x180020d29  lea     rcx, g_TaskHostContextListLock
0x180020d30  mov     cs:dword_18004CF18, 0
0x180020d3a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180020d40  test    rsi, rsi
0x180020d43  jnz     loc_180020E35
0x180020d49  add     rsp, 38h
0x180020d4d  pop     r14
0x180020d4f  pop     rdi
0x180020d50  pop     rsi
0x180020d51  pop     rbx
0x180020d52  retn
0x180020d53  or      cl, 40h
0x180020d56  mov     [rdi+68h], cl
0x180020d59  mov     rcx, [rdi+18h]; Process
0x180020d5d  test    rcx, rcx
0x180020d60  jz      short loc_180020D06
0x180020d62  mov     rax, cs:WPP_GLOBAL_Control
0x180020d69  cmp     rax, r14
0x180020d6c  jz      short loc_180020D9B
0x180020d6e  test    byte ptr [rax+1Ch], 80h
0x180020d72  jz      short loc_180020D9B
0x180020d74  mov     rbx, [rdi+38h]
0x180020d78  call    cs:__imp_GetProcessId
0x180020d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d85  mov     edx, 0B6h
0x180020d8a  mov     r9d, eax
0x180020d8d  mov     [rsp+58h+var_38], rbx
0x180020d92  mov     rcx, [rcx+10h]
0x180020d96  call    WPP_SF_dq
0x180020d9b  mov     rcx, [rdi+18h]; hProcess
0x180020d9f  mov     edx, 42Bh; uExitCode
0x180020da4  call    cs:__imp_TerminateProcess
0x180020daa  test    eax, eax
0x180020dac  jnz     short loc_180020DF5
0x180020dae  mov     rcx, cs:WPP_GLOBAL_Control
0x180020db5  cmp     rcx, r14
0x180020db8  jz      short loc_180020DFC
0x180020dba  test    byte ptr [rcx+1Ch], 1
0x180020dbe  jz      short loc_180020DFC
0x180020dc0  call    cs:__imp_GetLastError
0x180020dc6  mov     rcx, [rdi+18h]; Process
0x180020dca  mov     ebx, eax
0x180020dcc  call    cs:__imp_GetProcessId
0x180020dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dd9  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180020de0  mov     edx, 0B7h
0x180020de5  mov     dword ptr [rsp+58h+var_38], ebx
0x180020de9  mov     r9d, eax
0x180020dec  mov     rcx, [rcx+10h]
0x180020df0  call    WPP_SF_dd
0x180020df5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dfc  cmp     [rdi+38h], rsi
0x180020e00  jz      loc_180020D0D
0x180020e06  mov     rsi, [rdi+38h]
0x180020e0a  mov     qword ptr [rdi+38h], 0
0x180020e12  jmp     loc_180020D06
0x180020e17  movzx   eax, byte ptr [rdi+68h]
0x180020e1b  mov     edx, 0B8h
0x180020e20  mov     rcx, [rcx+10h]
0x180020e24  mov     r9, rdi
0x180020e27  mov     dword ptr [rsp+58h+var_38], eax
0x180020e2b  call    WPP_SF_qd
0x180020e30  jmp     loc_180020D1C
0x180020e35  mov     edx, 42Bh; ExceptionCode
0x180020e3a  mov     rcx, rsi; pAsync
0x180020e3d  call    cs:__imp_RpcAsyncAbortCall
0x180020e43  test    eax, eax
0x180020e45  jz      loc_180020D49
0x180020e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e52  cmp     rcx, r14
0x180020e55  jz      loc_180020D49
0x180020e5b  test    byte ptr [rcx+1Ch], 1
0x180020e5f  jz      loc_180020D49
0x180020e65  mov     rcx, [rcx+10h]
0x180020e69  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180020e70  mov     edx, 0B9h
0x180020e75  mov     r9d, eax
0x180020e78  call    WPP_SF_d
0x180020e7d  jmp     loc_180020D49
```
