# UbpmpTaskHostDead

- ea: `0x180005190`
- end: `0x180005318`
- name: `UbpmpTaskHostDead`
- size: `392`
- prototype: `__int64 __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180004c30`
- `0x180005190`
- `0x1800060d0`
- `0x1800351ec`
- `0x18003f5b4`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180005232`
- `ntdll!RtlReleaseSRWLockShared` at `0x180005232`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800051da`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800051da`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800051b8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800051ea`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800051b8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800051ea`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005222`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005276`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005222`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005276`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051f6`
- `RPCRT4!RpcAsyncAbortCall` at `0x18000529a`
- `RPCRT4!RpcAsyncAbortCall` at `0x18000529a`

## pseudocode

```c
unsigned int __fastcall UbpmpTaskHostDead(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1)
{
  __int64 v2; // r8
  __int64 v3; // r9
  unsigned int result; // eax
  unsigned int v5; // eax
  int v6; // [rsp+50h] [rbp+8h] BYREF
  PRPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp+18h] BYREF
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = a1;
  pAsync = 0;
  v6 = 1;
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_180050018 = GetCurrentThreadId();
  RtlAcquireSRWLockShared((char *)a1 + 80);
  RtlAcquireSRWLockExclusive((char *)a1 + 64);
  *((_DWORD *)a1 + 18) = GetCurrentThreadId();
  UbpmpTaskHostCleanup(a1, &pAsync, &v6);
  *((_DWORD *)a1 + 18) = 0;
  RtlReleaseSRWLockExclusive((char *)a1 + 64);
  RtlReleaseSRWLockShared((char *)a1 + 80);
  if ( (*((_BYTE *)a1 + 320) & 1) != 0 )
  {
    v5 = --g_cDummyHosts;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, v2, a1, v5);
  }
  if ( v6 )
    UbpmpDecrementRefAndDelete((__int64 *)&v8, 0, v2, v3);
  dword_180050018 = 0;
  result = RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  if ( pAsync )
  {
    result = RpcAsyncAbortCall(pAsync, 0x42Bu);
    if ( result )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 93,
                 WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                 result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005190  push    rbx
0x180005192  push    rsi
0x180005193  push    rdi
0x180005194  sub     rsp, 30h
0x180005198  mov     rsi, rcx
0x18000519b  mov     [rsp+48h+arg_18], rcx
0x1800051a0  lea     rcx, g_TaskHostContextListLock
0x1800051a7  mov     [rsp+48h+pAsync], 0
0x1800051b0  mov     [rsp+48h+arg_0], 1
0x1800051b8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800051bf  nop     dword ptr [rax+rax+00h]
0x1800051c4  call    cs:__imp_GetCurrentThreadId
0x1800051cb  nop     dword ptr [rax+rax+00h]
0x1800051d0  lea     rcx, [rsi+50h]
0x1800051d4  mov     cs:dword_180050018, eax
0x1800051da  call    cs:__imp_RtlAcquireSRWLockShared
0x1800051e1  nop     dword ptr [rax+rax+00h]
0x1800051e6  lea     rcx, [rsi+40h]
0x1800051ea  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800051f1  nop     dword ptr [rax+rax+00h]
0x1800051f6  call    cs:__imp_GetCurrentThreadId
0x1800051fd  nop     dword ptr [rax+rax+00h]
0x180005202  lea     r8, [rsp+48h+arg_0]; int *
0x180005207  mov     rcx, rsi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x18000520a  lea     rdx, [rsp+48h+pAsync]; struct _RPC_ASYNC_STATE **
0x18000520f  mov     [rsi+48h], eax
0x180005212  call    ?UbpmpTaskHostCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_RPC_ASYNC_STATE@@PEAH@Z; UbpmpTaskHostCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,_RPC_ASYNC_STATE * *,int *)
0x180005217  lea     rcx, [rsi+40h]
0x18000521b  mov     dword ptr [rsi+48h], 0
0x180005222  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180005229  nop     dword ptr [rax+rax+00h]
0x18000522e  lea     rcx, [rsi+50h]
0x180005232  call    cs:__imp_RtlReleaseSRWLockShared
0x180005239  nop     dword ptr [rax+rax+00h]
0x18000523e  test    byte ptr [rsi+140h], 1
0x180005245  lea     rbx, WPP_GLOBAL_Control
0x18000524c  jnz     loc_1800052D6
0x180005252  cmp     [rsp+48h+arg_0], 0
0x180005257  jz      short loc_180005265
0x180005259  xor     edx, edx
0x18000525b  lea     rcx, [rsp+48h+arg_18]
0x180005260  call    UbpmpDecrementRefAndDelete
0x180005265  lea     rcx, g_TaskHostContextListLock
0x18000526c  mov     cs:dword_180050018, 0
0x180005276  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000527d  nop     dword ptr [rax+rax+00h]
0x180005282  mov     rcx, [rsp+48h+pAsync]; pAsync
0x180005287  test    rcx, rcx
0x18000528a  jnz     short loc_180005295
0x18000528c  add     rsp, 30h
0x180005290  pop     rdi
0x180005291  pop     rsi
0x180005292  pop     rbx
0x180005293  retn
0x180005295  mov     edx, 42Bh; ExceptionCode
0x18000529a  call    cs:__imp_RpcAsyncAbortCall
0x1800052a1  nop     dword ptr [rax+rax+00h]
0x1800052a6  test    eax, eax
0x1800052a8  jz      short loc_18000528C
0x1800052aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052b1  cmp     rcx, rbx
0x1800052b4  jz      short loc_18000528C
0x1800052b6  test    byte ptr [rcx+1Ch], 1
0x1800052ba  jz      short loc_18000528C
0x1800052bc  mov     rcx, [rcx+10h]
0x1800052c0  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800052c7  mov     edx, 5Dh ; ']'
0x1800052cc  mov     r9d, eax
0x1800052cf  call    WPP_SF_d
0x1800052d4  jmp     short loc_18000528C
0x1800052d6  mov     eax, cs:?g_cDummyHosts@@3KA; ulong g_cDummyHosts
0x1800052dc  dec     eax
0x1800052de  mov     cs:?g_cDummyHosts@@3KA, eax; ulong g_cDummyHosts
0x1800052e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052eb  cmp     rcx, rbx
0x1800052ee  jz      loc_180005252
0x1800052f4  test    byte ptr [rcx+1Ch], 80h
0x1800052f8  jz      loc_180005252
0x1800052fe  mov     rcx, [rcx+10h]
0x180005302  mov     edx, 5Ch ; '\'
0x180005307  mov     r9, rsi
0x18000530a  mov     [rsp+48h+var_28], eax
0x18000530e  call    WPP_SF_qd
0x180005313  jmp     loc_180005252
```
