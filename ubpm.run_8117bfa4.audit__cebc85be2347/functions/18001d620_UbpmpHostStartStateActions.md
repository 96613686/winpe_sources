# UbpmpHostStartStateActions

- ea: `0x18001d620`
- end: `0x18001d819`
- name: `UbpmpHostStartStateActions`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18001da20`

## callees

- `0x18001d620`
- `0x180032f78`
- `0x1800351ec`
- `0x18003f3d8`
- `0x18003f5b4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d638`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001d638`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d6ac`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001d6ac`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001d68f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001d68f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001d723`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001d723`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d644`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d644`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d6f1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d757`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d6f1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d745`
- `RPCRT4!RpcAsyncAbortCall` at `0x18001d7ce`
- `RPCRT4!RpcAsyncAbortCall` at `0x18001d7ce`

## pseudocode

```c
unsigned int __fastcall UbpmpHostStartStateActions(__int64 a1, int a2)
{
  struct _RPC_ASYNC_STATE *v4; // rsi
  __int64 v5; // r8
  char v6; // cl
  PVOID *v7; // rcx
  unsigned int result; // eax
  void *v9; // rcx
  __int64 v10; // rbx
  DWORD ProcessId; // eax
  __int64 v12; // r8
  DWORD v13; // eax

  v4 = 0;
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_180050018 = GetCurrentThreadId();
  if ( (*(_BYTE *)(a1 + 104) & 0x30) != 0x30 )
    goto LABEL_8;
  v6 = *(_BYTE *)(a1 + 104) & 0xDF;
  *(_BYTE *)(a1 + 104) = v6;
  if ( a2 )
    goto LABEL_3;
  *(_BYTE *)(a1 + 104) = v6 | 0x40;
  v9 = *(void **)(a1 + 24);
  if ( !v9 )
    goto LABEL_3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v10 = *(_QWORD *)(a1 + 56);
    ProcessId = GetProcessId(v9);
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, v12, ProcessId, v10);
  }
  if ( TerminateProcess(*(HANDLE *)(a1 + 24), 0x42Bu) )
    goto LABEL_18;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    GetLastError();
    v13 = GetProcessId(*(HANDLE *)(a1 + 24));
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v13);
LABEL_18:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)(a1 + 56) )
  {
    v4 = *(struct _RPC_ASYNC_STATE **)(a1 + 56);
    *(_QWORD *)(a1 + 56) = 0;
LABEL_3:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && *((char *)v7 + 28) < 0 )
    WPP_SF_qd(v7[2], 184, v5, a1, *(unsigned __int8 *)(a1 + 104));
  WakeAllConditionVariable(&g_cvHostStartedup);
LABEL_8:
  dword_180050018 = 0;
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
0x18001d620  push    rbx
0x18001d622  push    rsi
0x18001d623  push    rdi
0x18001d624  push    r14
0x18001d626  sub     rsp, 38h
0x18001d62a  mov     rdi, rcx
0x18001d62d  mov     ebx, edx
0x18001d62f  lea     rcx, g_TaskHostContextListLock
0x18001d636  xor     esi, esi
0x18001d638  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001d63f  nop     dword ptr [rax+rax+00h]
0x18001d644  call    cs:__imp_GetCurrentThreadId
0x18001d64b  nop     dword ptr [rax+rax+00h]
0x18001d650  mov     cs:dword_180050018, eax
0x18001d656  lea     r14, WPP_GLOBAL_Control
0x18001d65d  mov     cl, [rdi+68h]
0x18001d660  mov     al, cl
0x18001d662  and     al, 30h
0x18001d664  cmp     al, 30h ; '0'
0x18001d666  jnz     short loc_18001D69B
0x18001d668  and     cl, 0DFh
0x18001d66b  mov     [rdi+68h], cl
0x18001d66e  test    ebx, ebx
0x18001d670  jz      short loc_18001D6CC
0x18001d672  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d679  cmp     rcx, r14
0x18001d67c  jz      short loc_18001D688
0x18001d67e  test    byte ptr [rcx+1Ch], 80h
0x18001d682  jnz     loc_18001D7A8
0x18001d688  lea     rcx, ?g_cvHostStartedup@@3U_RTL_CONDITION_VARIABLE@@A; ConditionVariable
0x18001d68f  call    cs:__imp_WakeAllConditionVariable
0x18001d696  nop     dword ptr [rax+rax+00h]
0x18001d69b  lea     rcx, g_TaskHostContextListLock
0x18001d6a2  mov     cs:dword_180050018, 0
0x18001d6ac  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001d6b3  nop     dword ptr [rax+rax+00h]
0x18001d6b8  test    rsi, rsi
0x18001d6bb  jnz     loc_18001D7C6
0x18001d6c1  add     rsp, 38h
0x18001d6c5  pop     r14
0x18001d6c7  pop     rdi
0x18001d6c8  pop     rsi
0x18001d6c9  pop     rbx
0x18001d6ca  retn
0x18001d6cc  or      cl, 40h
0x18001d6cf  mov     [rdi+68h], cl
0x18001d6d2  mov     rcx, [rdi+18h]; Process
0x18001d6d6  test    rcx, rcx
0x18001d6d9  jz      short loc_18001D672
0x18001d6db  mov     rax, cs:WPP_GLOBAL_Control
0x18001d6e2  cmp     rax, r14
0x18001d6e5  jz      short loc_18001D71A
0x18001d6e7  test    byte ptr [rax+1Ch], 80h
0x18001d6eb  jz      short loc_18001D71A
0x18001d6ed  mov     rbx, [rdi+38h]
0x18001d6f1  call    cs:__imp_GetProcessId
0x18001d6f8  nop     dword ptr [rax+rax+00h]
0x18001d6fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d704  mov     edx, 0B6h
0x18001d709  mov     r9d, eax
0x18001d70c  mov     [rsp+58h+var_38], rbx
0x18001d711  mov     rcx, [rcx+10h]
0x18001d715  call    WPP_SF_dq
0x18001d71a  mov     rcx, [rdi+18h]; hProcess
0x18001d71e  mov     edx, 42Bh; uExitCode
0x18001d723  call    cs:__imp_TerminateProcess
0x18001d72a  nop     dword ptr [rax+rax+00h]
0x18001d72f  test    eax, eax
0x18001d731  jnz     short loc_18001D786
0x18001d733  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d73a  cmp     rcx, r14
0x18001d73d  jz      short loc_18001D78D
0x18001d73f  test    byte ptr [rcx+1Ch], 1
0x18001d743  jz      short loc_18001D78D
0x18001d745  call    cs:__imp_GetLastError
0x18001d74c  nop     dword ptr [rax+rax+00h]
0x18001d751  mov     rcx, [rdi+18h]; Process
0x18001d755  mov     ebx, eax
0x18001d757  call    cs:__imp_GetProcessId
0x18001d75e  nop     dword ptr [rax+rax+00h]
0x18001d763  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d76a  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001d771  mov     edx, 0B7h
0x18001d776  mov     dword ptr [rsp+58h+var_38], ebx
0x18001d77a  mov     r9d, eax
0x18001d77d  mov     rcx, [rcx+10h]
0x18001d781  call    WPP_SF_dd
0x18001d786  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d78d  cmp     [rdi+38h], rsi
0x18001d791  jz      loc_18001D679
0x18001d797  mov     rsi, [rdi+38h]
0x18001d79b  mov     qword ptr [rdi+38h], 0
0x18001d7a3  jmp     loc_18001D672
0x18001d7a8  movzx   eax, byte ptr [rdi+68h]
0x18001d7ac  mov     edx, 0B8h
0x18001d7b1  mov     rcx, [rcx+10h]
0x18001d7b5  mov     r9, rdi
0x18001d7b8  mov     dword ptr [rsp+58h+var_38], eax
0x18001d7bc  call    WPP_SF_qd
0x18001d7c1  jmp     loc_18001D688
0x18001d7c6  mov     edx, 42Bh; ExceptionCode
0x18001d7cb  mov     rcx, rsi; pAsync
0x18001d7ce  call    cs:__imp_RpcAsyncAbortCall
0x18001d7d5  nop     dword ptr [rax+rax+00h]
0x18001d7da  test    eax, eax
0x18001d7dc  jz      loc_18001D6C1
0x18001d7e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7e9  cmp     rcx, r14
0x18001d7ec  jz      loc_18001D6C1
0x18001d7f2  test    byte ptr [rcx+1Ch], 1
0x18001d7f6  jz      loc_18001D6C1
0x18001d7fc  mov     rcx, [rcx+10h]
0x18001d800  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001d807  mov     edx, 0B9h
0x18001d80c  mov     r9d, eax
0x18001d80f  call    WPP_SF_d
0x18001d814  jmp     loc_18001D6C1
```
