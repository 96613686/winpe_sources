# RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)

- ea: `0x18001e7b4`
- end: `0x18001e915`
- name: `?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ`
- size: `353`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001964c`
- `0x18001e91c`

## callees

- `0x18001e7b4`
- `0x180024640`

## import_xrefs

- `ntdll!TpSetPoolStackInformation` at `0x18001e8a6`
- `ntdll!TpSetPoolStackInformation` at `0x18001e8a6`
- `ntdll!TpDisablePoolCallbackChecks` at `0x18001e880`
- `ntdll!TpDisablePoolCallbackChecks` at `0x18001e880`
- `ntdll!RtlNtStatusToDosError` at `0x18001e8ae`
- `ntdll!RtlNtStatusToDosError` at `0x18001e8ae`
- `KERNEL32!CloseThreadpool` at `0x18001e8de`
- `KERNEL32!CloseThreadpool` at `0x18001e8de`
- `KERNEL32!CreateThreadpool` at `0x18001e86a`
- `KERNEL32!CreateThreadpool` at `0x18001e86a`
- `RPCRT4!I_RpcFree` at `0x18001e8ec`
- `RPCRT4!I_RpcFree` at `0x18001e8ec`
- `RPCRT4!I_RpcAllocate` at `0x18001e80f`
- `RPCRT4!I_RpcAllocate` at `0x18001e80f`

## pseudocode

```c
__int64 RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
{
  int v0; // esi
  _QWORD *v1; // rax
  _QWORD *v2; // rbx
  unsigned int v3; // edi
  PTP_POOL Threadpool; // rax
  struct _TP_POOL *v5; // rsi
  NTSTATUS v6; // eax
  unsigned __int128 v8; // [rsp+20h] [rbp-28h] BYREF

  v8 = 0;
  if ( !RPC_THREAD_POOL::PoolStarted )
    RPC_THREAD_POOL::PoolStarted = 1;
  if ( RPC_THREAD_POOL::CallbackEnvironment || !RPC_THREAD_POOL::PrivatePool )
    return 0;
  v0 = (_DWORD)RPC_THREAD_POOL::CallbackEnvironment + 72;
  v1 = I_RpcAllocate((int)RPC_THREAD_POOL::CallbackEnvironment + 72);
  v2 = v1;
  if ( v1 )
  {
    *(_DWORD *)v1 = 3;
    v1[1] = 0;
    v1[2] = 0;
    v1[3] = 0;
    v1[4] = 0;
    v1[5] = 0;
    v1[6] = 0;
    *((_DWORD *)v1 + 14) = 0;
    *((_DWORD *)v1 + 15) = 1;
    *((_DWORD *)v1 + 16) = v0;
    Threadpool = CreateThreadpool(0);
    v5 = Threadpool;
    if ( !Threadpool )
    {
      v3 = 14;
      goto LABEL_16;
    }
    TpDisablePoolCallbackChecks(Threadpool);
    v8 = __PAIR128__(RPC_THREAD_POOL::CommitStackSize, RPC_THREAD_POOL::ReserveStackSize);
    v6 = TpSetPoolStackInformation(v5, &v8);
    if ( RtlNtStatusToDosError(v6) )
    {
      v3 = 14;
    }
    else
    {
      v2[1] = v5;
      if ( !_InterlockedCompareExchange64(
              (volatile signed __int64 *)&RPC_THREAD_POOL::CallbackEnvironment,
              (signed __int64)v2,
              0) )
      {
        v5 = 0;
        v2 = 0;
      }
      v3 = 0;
      if ( !v5 )
      {
LABEL_15:
        if ( !v2 )
          return v3;
LABEL_16:
        I_RpcFree(v2);
        return v3;
      }
    }
    CloseThreadpool(v5);
    goto LABEL_15;
  }
  return (unsigned int)(v0 - 58);
}

```

## disassembly

```asm
0x18001e7b4  mov     [rsp+arg_0], rbx
0x18001e7b9  mov     [rsp+arg_8], rsi
0x18001e7be  push    rdi
0x18001e7bf  sub     rsp, 40h
0x18001e7c3  mov     rax, cs:__security_cookie
0x18001e7ca  xor     rax, rsp
0x18001e7cd  mov     [rsp+48h+var_18], rax
0x18001e7d2  cmp     cs:?PoolStarted@RPC_THREAD_POOL@@0HA, 0; int RPC_THREAD_POOL::PoolStarted
0x18001e7d9  xorps   xmm0, xmm0
0x18001e7dc  movups  [rsp+48h+var_28], xmm0
0x18001e7e1  mov     edi, 1
0x18001e7e6  jnz     short loc_18001E7EE
0x18001e7e8  mov     cs:?PoolStarted@RPC_THREAD_POOL@@0HA, edi; int RPC_THREAD_POOL::PoolStarted
0x18001e7ee  mov     rax, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; _TP_CALLBACK_ENVIRON_V3 * RPC_THREAD_POOL::CallbackEnvironment
0x18001e7f5  test    rax, rax
0x18001e7f8  jnz     loc_18001E8F4
0x18001e7fe  cmp     cs:?PrivatePool@RPC_THREAD_POOL@@0HA, eax; int RPC_THREAD_POOL::PrivatePool
0x18001e804  jz      loc_18001E8F4
0x18001e80a  lea     esi, [rax+48h]
0x18001e80d  mov     ecx, esi; Size
0x18001e80f  call    cs:__imp_I_RpcAllocate
0x18001e815  mov     rbx, rax
0x18001e818  test    rax, rax
0x18001e81b  jnz     short loc_18001E825
0x18001e81d  lea     edi, [rsi-3Ah]
0x18001e820  jmp     loc_18001E8F6
0x18001e825  xor     ecx, ecx; reserved
0x18001e827  mov     dword ptr [rax], 3
0x18001e82d  mov     qword ptr [rax+8], 0
0x18001e835  mov     qword ptr [rax+10h], 0
0x18001e83d  mov     qword ptr [rax+18h], 0
0x18001e845  mov     qword ptr [rax+20h], 0
0x18001e84d  mov     qword ptr [rax+28h], 0
0x18001e855  mov     qword ptr [rax+30h], 0
0x18001e85d  mov     dword ptr [rax+38h], 0
0x18001e864  mov     [rax+3Ch], edi
0x18001e867  mov     [rax+40h], esi
0x18001e86a  call    cs:__imp_CreateThreadpool
0x18001e870  mov     rsi, rax
0x18001e873  test    rax, rax
0x18001e876  jnz     short loc_18001E87D
0x18001e878  lea     edi, [rax+0Eh]
0x18001e87b  jmp     short loc_18001E8E9
0x18001e87d  mov     rcx, rsi
0x18001e880  call    cs:__imp_TpDisablePoolCallbackChecks
0x18001e886  mov     rax, cs:?ReserveStackSize@RPC_THREAD_POOL@@0_KA; unsigned __int64 RPC_THREAD_POOL::ReserveStackSize
0x18001e88d  lea     rdx, [rsp+48h+var_28]
0x18001e892  mov     qword ptr [rsp+48h+var_28], rax
0x18001e897  mov     rcx, rsi
0x18001e89a  mov     rax, cs:?CommitStackSize@RPC_THREAD_POOL@@0_KA; unsigned __int64 RPC_THREAD_POOL::CommitStackSize
0x18001e8a1  mov     qword ptr [rsp+48h+var_28+8], rax
0x18001e8a6  call    cs:__imp_TpSetPoolStackInformation
0x18001e8ac  mov     ecx, eax; Status
0x18001e8ae  call    cs:__imp_RtlNtStatusToDosError
0x18001e8b4  test    eax, eax
0x18001e8b6  jz      short loc_18001E8BF
0x18001e8b8  mov     edi, 0Eh
0x18001e8bd  jmp     short loc_18001E8DB
0x18001e8bf  mov     [rbx+8], rsi
0x18001e8c3  xor     eax, eax
0x18001e8c5  lock cmpxchg cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA, rbx; _TP_CALLBACK_ENVIRON_V3 * RPC_THREAD_POOL::CallbackEnvironment
0x18001e8ce  jnz     short loc_18001E8D4
0x18001e8d0  xor     esi, esi
0x18001e8d2  xor     ebx, ebx
0x18001e8d4  xor     edi, edi
0x18001e8d6  test    rsi, rsi
0x18001e8d9  jz      short loc_18001E8E4
0x18001e8db  mov     rcx, rsi; ptpp
0x18001e8de  call    cs:__imp_CloseThreadpool
0x18001e8e4  test    rbx, rbx
0x18001e8e7  jz      short loc_18001E8F6
0x18001e8e9  mov     rcx, rbx; Object
0x18001e8ec  call    cs:__imp_I_RpcFree
0x18001e8f2  jmp     short loc_18001E8F6
0x18001e8f4  xor     edi, edi
0x18001e8f6  mov     eax, edi
0x18001e8f8  mov     rcx, [rsp+48h+var_18]
0x18001e8fd  xor     rcx, rsp; StackCookie
0x18001e900  call    __security_check_cookie
0x18001e905  mov     rbx, [rsp+48h+arg_0]
0x18001e90a  mov     rsi, [rsp+48h+arg_8]
0x18001e90f  add     rsp, 40h
0x18001e913  pop     rdi
0x18001e914  retn
```
