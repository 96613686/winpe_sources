# RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)

- ea: `0x18006e4c0`
- end: `0x18006e644`
- name: `?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ`
- size: `388`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006e110`
- `0x18006e2dc`
- `0x18006e39c`
- `0x18006e470`
- `0x18006f0d8`
- `0x18009fe30`

## callees

- `0x180023020`
- `0x180023a40`
- `0x18006e4c0`
- `0x1800ceda0`

## import_xrefs

- `ntdll!TpDisablePoolCallbackChecks` at `0x18006e58d`
- `ntdll!TpDisablePoolCallbackChecks` at `0x18006e58d`
- `ntdll!TpSetPoolStackInformation` at `0x18006e5b9`
- `ntdll!TpSetPoolStackInformation` at `0x18006e5b9`
- `ntdll!RtlNtStatusToDosError` at `0x18006e5c7`
- `ntdll!RtlNtStatusToDosError` at `0x18006e5c7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18006e572`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18006e572`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18006e636`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18006e636`

## pseudocode

```c
__int64 RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
{
  unsigned int v0; // edi
  _QWORD *v1; // rax
  _QWORD *v2; // rbx
  PTP_POOL Threadpool; // rax
  struct _TP_POOL *v4; // rsi
  NTSTATUS v5; // eax
  unsigned __int128 v7; // [rsp+20h] [rbp-28h] BYREF

  v7 = 0;
  if ( !RPC_THREAD_POOL::PoolStarted )
    RPC_THREAD_POOL::PoolStarted = 1;
  if ( !RPC_THREAD_POOL::CallbackEnvironment && RPC_THREAD_POOL::PrivatePool )
  {
    v1 = AllocWrapper(0x48u);
    v2 = v1;
    if ( !v1 )
      return 14;
    *(_DWORD *)v1 = 3;
    v1[1] = 0;
    v1[2] = 0;
    v1[3] = 0;
    v1[4] = 0;
    v1[5] = 0;
    v1[6] = 0;
    *((_DWORD *)v1 + 14) = 0;
    *((_DWORD *)v1 + 15) = 1;
    *((_DWORD *)v1 + 16) = 72;
    Threadpool = CreateThreadpool(0);
    v4 = Threadpool;
    if ( !Threadpool )
    {
      v0 = 14;
      goto LABEL_16;
    }
    TpDisablePoolCallbackChecks(Threadpool);
    v7 = __PAIR128__(RPC_THREAD_POOL::CommitStackSize, RPC_THREAD_POOL::ReserveStackSize);
    v5 = TpSetPoolStackInformation(v4, &v7);
    if ( RtlNtStatusToDosError(v5) )
    {
      v0 = 14;
    }
    else
    {
      v2[1] = v4;
      if ( !_InterlockedCompareExchange64(
              (volatile signed __int64 *)&RPC_THREAD_POOL::CallbackEnvironment,
              (signed __int64)v2,
              0) )
      {
        v4 = 0;
        v2 = 0;
      }
      v0 = 0;
      if ( !v4 )
      {
LABEL_12:
        if ( !v2 )
          return v0;
LABEL_16:
        FreeWrapper(v2);
        return v0;
      }
    }
    CloseThreadpool(v4);
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x18006e4c0  mov     [rsp+arg_0], rbx
0x18006e4c5  mov     [rsp+arg_8], rsi
0x18006e4ca  push    rdi
0x18006e4cb  sub     rsp, 40h
0x18006e4cf  mov     rax, cs:__security_cookie
0x18006e4d6  xor     rax, rsp
0x18006e4d9  mov     [rsp+48h+var_18], rax
0x18006e4de  cmp     cs:?PoolStarted@RPC_THREAD_POOL@@0HA, 0; int RPC_THREAD_POOL::PoolStarted
0x18006e4e5  xorps   xmm0, xmm0
0x18006e4e8  movups  [rsp+48h+var_28], xmm0
0x18006e4ed  mov     edi, 1
0x18006e4f2  jnz     short loc_18006E4FA
0x18006e4f4  mov     cs:?PoolStarted@RPC_THREAD_POOL@@0HA, edi; int RPC_THREAD_POOL::PoolStarted
0x18006e4fa  mov     rax, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; _TP_CALLBACK_ENVIRON_V3 * RPC_THREAD_POOL::CallbackEnvironment
0x18006e501  test    rax, rax
0x18006e504  jnz     short loc_18006E50E
0x18006e506  cmp     cs:?PrivatePool@RPC_THREAD_POOL@@0HA, eax; int RPC_THREAD_POOL::PrivatePool
0x18006e50c  jnz     short loc_18006E515
0x18006e50e  xor     edi, edi
0x18006e510  jmp     loc_18006E5F8
0x18006e515  mov     esi, 48h ; 'H'
0x18006e51a  mov     ecx, esi; dwBytes
0x18006e51c  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18006e521  mov     rbx, rax
0x18006e524  test    rax, rax
0x18006e527  jz      loc_18006E618
0x18006e52d  xor     ecx, ecx; reserved
0x18006e52f  mov     dword ptr [rax], 3
0x18006e535  mov     qword ptr [rax+8], 0
0x18006e53d  mov     qword ptr [rax+10h], 0
0x18006e545  mov     qword ptr [rax+18h], 0
0x18006e54d  mov     qword ptr [rax+20h], 0
0x18006e555  mov     qword ptr [rax+28h], 0
0x18006e55d  mov     qword ptr [rax+30h], 0
0x18006e565  mov     dword ptr [rax+38h], 0
0x18006e56c  mov     [rax+3Ch], edi
0x18006e56f  mov     [rax+40h], esi
0x18006e572  call    cs:__imp_CreateThreadpool
0x18006e579  nop     dword ptr [rax+rax+00h]
0x18006e57e  mov     rsi, rax
0x18006e581  test    rax, rax
0x18006e584  jz      loc_18006E61F
0x18006e58a  mov     rcx, rax
0x18006e58d  call    cs:__imp_TpDisablePoolCallbackChecks
0x18006e594  nop     dword ptr [rax+rax+00h]
0x18006e599  mov     rax, cs:?ReserveStackSize@RPC_THREAD_POOL@@0_KA; unsigned __int64 RPC_THREAD_POOL::ReserveStackSize
0x18006e5a0  lea     rdx, [rsp+48h+var_28]
0x18006e5a5  mov     qword ptr [rsp+48h+var_28], rax
0x18006e5aa  mov     rcx, rsi
0x18006e5ad  mov     rax, cs:?CommitStackSize@RPC_THREAD_POOL@@0_KA; unsigned __int64 RPC_THREAD_POOL::CommitStackSize
0x18006e5b4  mov     qword ptr [rsp+48h+var_28+8], rax
0x18006e5b9  call    cs:__imp_TpSetPoolStackInformation
0x18006e5c0  nop     dword ptr [rax+rax+00h]
0x18006e5c5  mov     ecx, eax; Status
0x18006e5c7  call    cs:__imp_RtlNtStatusToDosError
0x18006e5ce  nop     dword ptr [rax+rax+00h]
0x18006e5d3  test    eax, eax
0x18006e5d5  jnz     short loc_18006E62E
0x18006e5d7  mov     [rbx+8], rsi
0x18006e5db  xor     eax, eax
0x18006e5dd  lock cmpxchg cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA, rbx; _TP_CALLBACK_ENVIRON_V3 * RPC_THREAD_POOL::CallbackEnvironment
0x18006e5e6  jnz     short loc_18006E5EC
0x18006e5e8  xor     esi, esi
0x18006e5ea  xor     ebx, ebx
0x18006e5ec  xor     edi, edi
0x18006e5ee  test    rsi, rsi
0x18006e5f1  jnz     short loc_18006E633
0x18006e5f3  test    rbx, rbx
0x18006e5f6  jnz     short loc_18006E624
0x18006e5f8  mov     eax, edi
0x18006e5fa  mov     rcx, [rsp+48h+var_18]
0x18006e5ff  xor     rcx, rsp; StackCookie
0x18006e602  call    __security_check_cookie
0x18006e607  mov     rbx, [rsp+48h+arg_0]
0x18006e60c  mov     rsi, [rsp+48h+arg_8]
0x18006e611  add     rsp, 40h
0x18006e615  pop     rdi
0x18006e616  retn
0x18006e618  mov     edi, 0Eh
0x18006e61d  jmp     short loc_18006E5F8
0x18006e61f  mov     edi, 0Eh
0x18006e624  mov     rcx, rbx; lpMem
0x18006e627  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18006e62c  jmp     short loc_18006E5F8
0x18006e62e  mov     edi, 0Eh
0x18006e633  mov     rcx, rsi; ptpp
0x18006e636  call    cs:__imp_CloseThreadpool
0x18006e63d  nop     dword ptr [rax+rax+00h]
0x18006e642  jmp     short loc_18006E5F3
```
