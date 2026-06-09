# UbpmpTaskHostDead

- ea: `0x180004860`
- end: `0x1800049ad`
- name: `UbpmpTaskHostDead`
- size: `333`
- prototype: `__int64 __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180004860`
- `0x1800057b0`
- `0x180009750`
- `0x180032e38`
- `0x18003cbc0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800048de`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800048de`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000489e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000489e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004888`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800048a8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004888`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800048a8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800048d4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004918`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800048d4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004918`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000488e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000488e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048ae`
- `RPCRT4!RpcAsyncAbortCall` at `0x180004935`
- `RPCRT4!RpcAsyncAbortCall` at `0x180004935`

## pseudocode

```c
unsigned int __fastcall UbpmpTaskHostDead(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1)
{
  unsigned int result; // eax
  int v3; // [rsp+50h] [rbp+8h] BYREF
  PRPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp+18h] BYREF
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a1;
  pAsync = 0;
  v3 = 1;
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_18004CF18 = GetCurrentThreadId();
  RtlAcquireSRWLockShared((char *)a1 + 80);
  RtlAcquireSRWLockExclusive((char *)a1 + 64);
  *((_DWORD *)a1 + 18) = GetCurrentThreadId();
  UbpmpTaskHostCleanup(a1, &pAsync, &v3);
  *((_DWORD *)a1 + 18) = 0;
  RtlReleaseSRWLockExclusive((char *)a1 + 64);
  RtlReleaseSRWLockShared((char *)a1 + 80);
  if ( (*((_BYTE *)a1 + 320) & 1) != 0 )
  {
    --g_cDummyHosts;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 92);
  }
  if ( v3 )
    UbpmpDecrementRefAndDelete((__int64 *)&v5, 0);
  dword_18004CF18 = 0;
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
0x180004860  push    rbx
0x180004862  push    rsi
0x180004863  push    rdi
0x180004864  sub     rsp, 30h
0x180004868  mov     rsi, rcx
0x18000486b  mov     [rsp+48h+arg_18], rcx
0x180004870  lea     rcx, g_TaskHostContextListLock
0x180004877  mov     [rsp+48h+pAsync], 0
0x180004880  mov     [rsp+48h+arg_0], 1
0x180004888  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000488e  call    cs:__imp_GetCurrentThreadId
0x180004894  lea     rcx, [rsi+50h]
0x180004898  mov     cs:dword_18004CF18, eax
0x18000489e  call    cs:__imp_RtlAcquireSRWLockShared
0x1800048a4  lea     rcx, [rsi+40h]
0x1800048a8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800048ae  call    cs:__imp_GetCurrentThreadId
0x1800048b4  lea     r8, [rsp+48h+arg_0]; int *
0x1800048b9  mov     rcx, rsi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x1800048bc  lea     rdx, [rsp+48h+pAsync]; struct _RPC_ASYNC_STATE **
0x1800048c1  mov     [rsi+48h], eax
0x1800048c4  call    ?UbpmpTaskHostCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_RPC_ASYNC_STATE@@PEAH@Z; UbpmpTaskHostCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,_RPC_ASYNC_STATE * *,int *)
0x1800048c9  lea     rcx, [rsi+40h]
0x1800048cd  mov     dword ptr [rsi+48h], 0
0x1800048d4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800048da  lea     rcx, [rsi+50h]
0x1800048de  call    cs:__imp_RtlReleaseSRWLockShared
0x1800048e4  test    byte ptr [rsi+140h], 1
0x1800048eb  lea     rbx, WPP_GLOBAL_Control
0x1800048f2  jnz     short loc_18000496B
0x1800048f4  cmp     [rsp+48h+arg_0], 0
0x1800048f9  jz      short loc_180004907
0x1800048fb  xor     edx, edx
0x1800048fd  lea     rcx, [rsp+48h+arg_18]
0x180004902  call    UbpmpDecrementRefAndDelete
0x180004907  lea     rcx, g_TaskHostContextListLock
0x18000490e  mov     cs:dword_18004CF18, 0
0x180004918  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000491e  mov     rcx, [rsp+48h+pAsync]; pAsync
0x180004923  test    rcx, rcx
0x180004926  jnz     short loc_180004930
0x180004928  add     rsp, 30h
0x18000492c  pop     rdi
0x18000492d  pop     rsi
0x18000492e  pop     rbx
0x18000492f  retn
0x180004930  mov     edx, 42Bh; ExceptionCode
0x180004935  call    cs:__imp_RpcAsyncAbortCall
0x18000493b  test    eax, eax
0x18000493d  jz      short loc_180004928
0x18000493f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004946  cmp     rcx, rbx
0x180004949  jz      short loc_180004928
0x18000494b  test    byte ptr [rcx+1Ch], 1
0x18000494f  jz      short loc_180004928
0x180004951  mov     rcx, [rcx+10h]
0x180004955  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000495c  mov     edx, 5Dh ; ']'
0x180004961  mov     r9d, eax
0x180004964  call    WPP_SF_d
0x180004969  jmp     short loc_180004928
0x18000496b  mov     eax, cs:?g_cDummyHosts@@3KA; ulong g_cDummyHosts
0x180004971  dec     eax
0x180004973  mov     cs:?g_cDummyHosts@@3KA, eax; ulong g_cDummyHosts
0x180004979  mov     rcx, cs:WPP_GLOBAL_Control
0x180004980  cmp     rcx, rbx
0x180004983  jz      loc_1800048F4
0x180004989  test    byte ptr [rcx+1Ch], 80h
0x18000498d  jz      loc_1800048F4
0x180004993  mov     rcx, [rcx+10h]
0x180004997  mov     edx, 5Ch ; '\'
0x18000499c  mov     r9, rsi
0x18000499f  mov     [rsp+48h+var_28], eax
0x1800049a3  call    WPP_SF_qd
0x1800049a8  jmp     loc_1800048F4
```
