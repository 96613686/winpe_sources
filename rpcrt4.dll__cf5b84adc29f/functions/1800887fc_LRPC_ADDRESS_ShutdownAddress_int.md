# LRPC_ADDRESS::ShutdownAddress(int)

- ea: `0x1800887fc`
- end: `0x180088a03`
- name: `?ShutdownAddress@LRPC_ADDRESS@@AEAAXH@Z`
- size: `519`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180087e30`
- `0x180087e40`

## callees

- `0x180015aa0`
- `0x180016128`
- `0x180022e80`
- `0x1800887fc`
- `0x180088a0c`
- `0x180088a74`
- `0x180088d9c`
- `0x1800d7010`

## import_xrefs

- `ntdll!NtClose` at `0x18008898a`
- `ntdll!NtClose` at `0x18008898a`
- `ntdll!RtlLeaveCriticalSection` at `0x18008889d`
- `ntdll!RtlLeaveCriticalSection` at `0x18008889d`
- `ntdll!RtlEnterCriticalSection` at `0x18008882b`
- `ntdll!RtlEnterCriticalSection` at `0x18008882b`
- `ntdll!TpWaitForAlpcCompletion` at `0x1800888e7`
- `ntdll!TpWaitForAlpcCompletion` at `0x1800888e7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800888b8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800888b8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800889d7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800889d7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800889f2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800889f2`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::ShutdownAddress(LRPC_ADDRESS *this, int a2)
{
  LRPC_ADDRESS *v3; // rcx
  int v4; // r14d
  unsigned int i; // eax
  unsigned int v6; // esi
  __int64 v7; // rax
  void **v8; // rbx
  LRPC_ADDRESS *v9; // rcx
  unsigned __int32 v10; // ebx
  _QWORD *v11; // rcx
  unsigned int v12; // edx
  RPC_THREAD_POOL_ALPC *v13; // rcx
  unsigned int j; // eax
  unsigned int v15; // ebx
  volatile signed __int32 *v16; // rcx
  unsigned int v17; // r8d
  void *v18; // rbx
  int v19; // [rsp+28h] [rbp-30h]
  int v20; // [rsp+30h] [rbp-28h]
  unsigned int v21; // [rsp+68h] [rbp+10h] BYREF

  v21 = 0;
  if ( !a2 )
    RtlAcquireSRWLockExclusive((char *)this + 424);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)this + 4);
  v4 = 0;
  for ( i = 0; i < *((_DWORD *)this + 56); i = v6 )
  {
    v3 = (LRPC_ADDRESS *)i;
    v6 = i + 1;
    v7 = *((_QWORD *)this + 27);
    v8 = *(void ***)(v7 + 8LL * (_QWORD)v3);
    if ( v8 )
    {
      LRPC_SASSOCIATION::FreeAllCausalFlows(*(LRPC_SASSOCIATION **)(v7 + 8LL * (_QWORD)v3));
      LRPC_SASSOCIATION::NotifyAllActiveCalls((LRPC_SASSOCIATION *)v8);
      LRPC_ADDRESS::DisconnectAlpcPort(v9, v8[6], &v21);
      v4 += v21;
    }
  }
  LRPC_ADDRESS::DisconnectAlpcPort(v3, *((void **)this + 26), &v21);
  v10 = v4 + v21;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)this + 4);
  _InterlockedExchange((volatile __int32 *)this + 101, v10);
  RtlReleaseSRWLockExclusive((char *)this + 424);
  if ( v10 > _InterlockedCompareExchange((volatile signed __int32 *)this + 100, 0, 0) )
    WaitForSingleObject(*((HANDLE *)this + 51), 0xFFFFFFFF);
  v11 = (_QWORD *)*((_QWORD *)this + 34);
  if ( v11 )
  {
    TpWaitForAlpcCompletion(*v11);
    v13 = (RPC_THREAD_POOL_ALPC *)*((_QWORD *)this + 34);
    if ( v13 )
      RPC_THREAD_POOL_ALPC::`scalar deleting destructor'(v13, v12);
    *((_QWORD *)this + 34) = 0;
  }
  for ( j = 0; j < *((_DWORD *)this + 56); j = v15 )
  {
    v15 = j + 1;
    v16 = *(volatile signed __int32 **)(*((_QWORD *)this + 27) + 8LL * j);
    if ( v16 )
    {
      v17 = _InterlockedCompareExchange(v16 + 51, 0, 0);
      if ( v17 < _InterlockedCompareExchange(v16 + 52, 0, 0) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 32LL))(v16);
    }
  }
  v18 = (void *)*((_QWORD *)this + 26);
  *((_QWORD *)this + 26) = 0;
  LogEvent(0x4Cu, 0x64u, v18, 0, 0, v19, v20);
  NtClose(v18);
  RPC_SERVER::DeleteAddressIfNecessary((RPC_SERVER *)GlobalRpcServer, this);
  (*(void (__fastcall **)(LRPC_ADDRESS *))(*(_QWORD *)this + 32LL))(this);
}

```

## disassembly

```asm
0x1800887fc  mov     [rsp+arg_0], rbx
0x180088801  mov     [rsp+arg_10], rbp
0x180088806  push    rsi
0x180088807  push    rdi
0x180088808  push    r14
0x18008880a  sub     rsp, 40h
0x18008880e  mov     [rsp+58h+arg_8], 0
0x180088816  mov     rdi, rcx
0x180088819  test    edx, edx
0x18008881b  jz      loc_1800889D0
0x180088821  lea     rbp, [rdi+0A0h]
0x180088828  mov     rcx, rbp; CriticalSection
0x18008882b  call    cs:__imp_RtlEnterCriticalSection
0x180088832  nop     dword ptr [rax+rax+00h]
0x180088837  xor     r14d, r14d
0x18008883a  xor     eax, eax
0x18008883c  cmp     eax, [rdi+0E0h]
0x180088842  jnb     short loc_180088882
0x180088844  mov     ecx, eax
0x180088846  lea     esi, [rax+1]
0x180088849  mov     rax, [rdi+0D8h]
0x180088850  mov     rbx, [rax+rcx*8]
0x180088854  test    rbx, rbx
0x180088857  jnz     short loc_18008885D
0x180088859  mov     eax, esi
0x18008885b  jmp     short loc_18008883C
0x18008885d  mov     rcx, rbx; this
0x180088860  call    ?FreeAllCausalFlows@LRPC_SASSOCIATION@@AEAAXXZ; LRPC_SASSOCIATION::FreeAllCausalFlows(void)
0x180088865  mov     rcx, rbx; this
0x180088868  call    ?NotifyAllActiveCalls@LRPC_SASSOCIATION@@AEAAXXZ; LRPC_SASSOCIATION::NotifyAllActiveCalls(void)
0x18008886d  mov     rdx, [rbx+30h]; void *
0x180088871  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x180088876  call    ?DisconnectAlpcPort@LRPC_ADDRESS@@AEAAXPEAXPEAK@Z; LRPC_ADDRESS::DisconnectAlpcPort(void *,ulong *)
0x18008887b  add     r14d, [rsp+58h+arg_8]
0x180088880  jmp     short loc_180088859
0x180088882  mov     rdx, [rdi+0D0h]; void *
0x180088889  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x18008888e  call    ?DisconnectAlpcPort@LRPC_ADDRESS@@AEAAXPEAXPEAK@Z; LRPC_ADDRESS::DisconnectAlpcPort(void *,ulong *)
0x180088893  mov     ebx, [rsp+58h+arg_8]
0x180088897  mov     rcx, rbp; CriticalSection
0x18008889a  add     ebx, r14d
0x18008889d  call    cs:__imp_RtlLeaveCriticalSection
0x1800888a4  nop     dword ptr [rax+rax+00h]
0x1800888a9  mov     eax, ebx
0x1800888ab  lea     rcx, [rdi+1A8h]
0x1800888b2  xchg    eax, [rdi+194h]
0x1800888b8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800888bf  nop     dword ptr [rax+rax+00h]
0x1800888c4  xor     ecx, ecx
0x1800888c6  xor     eax, eax
0x1800888c8  lock cmpxchg [rdi+190h], ecx
0x1800888d0  cmp     ebx, eax
0x1800888d2  ja      loc_1800889E8
0x1800888d8  mov     rcx, [rdi+110h]
0x1800888df  test    rcx, rcx
0x1800888e2  jz      short loc_18008890E
0x1800888e4  mov     rcx, [rcx]
0x1800888e7  call    cs:__imp_TpWaitForAlpcCompletion
0x1800888ee  nop     dword ptr [rax+rax+00h]
0x1800888f3  mov     rcx, [rdi+110h]; this
0x1800888fa  test    rcx, rcx
0x1800888fd  jnz     loc_1800889C6
0x180088903  mov     qword ptr [rdi+110h], 0
0x18008890e  xor     eax, eax
0x180088910  cmp     eax, [rdi+0E0h]
0x180088916  jnb     short loc_18008895D
0x180088918  mov     ecx, eax
0x18008891a  lea     ebx, [rax+1]
0x18008891d  mov     rax, [rdi+0D8h]
0x180088924  mov     rcx, [rax+rcx*8]
0x180088928  test    rcx, rcx
0x18008892b  jnz     short loc_180088931
0x18008892d  mov     eax, ebx
0x18008892f  jmp     short loc_180088910
0x180088931  xor     edx, edx
0x180088933  xor     eax, eax
0x180088935  lock cmpxchg [rcx+0CCh], edx
0x18008893d  mov     r8d, eax
0x180088940  xor     eax, eax
0x180088942  lock cmpxchg [rcx+0D0h], edx
0x18008894a  cmp     r8d, eax
0x18008894d  jnb     short loc_18008892D
0x18008894f  mov     rax, [rcx]
0x180088952  mov     rax, [rax+20h]
0x180088956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008895b  jmp     short loc_18008892D
0x18008895d  mov     rbx, [rdi+0D0h]
0x180088964  xor     r9d, r9d; void *
0x180088967  mov     r8, rbx; void *
0x18008896a  mov     qword ptr [rdi+0D0h], 0
0x180088975  mov     dl, 64h ; 'd'; unsigned __int8
0x180088977  mov     [rsp+58h+var_38], 0; unsigned __int64
0x180088980  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180088982  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180088987  mov     rcx, rbx; Handle
0x18008898a  call    cs:__imp_NtClose
0x180088991  nop     dword ptr [rax+rax+00h]
0x180088996  mov     rcx, cs:?GlobalRpcServer@@3PEAVRPC_SERVER@@EA; this
0x18008899d  mov     rdx, rdi; struct RPC_ADDRESS *
0x1800889a0  call    ?DeleteAddressIfNecessary@RPC_SERVER@@QEAAXPEAVRPC_ADDRESS@@@Z; RPC_SERVER::DeleteAddressIfNecessary(RPC_ADDRESS *)
0x1800889a5  mov     rax, [rdi]
0x1800889a8  mov     rcx, rdi
0x1800889ab  mov     rax, [rax+20h]
0x1800889af  mov     rbx, [rsp+58h+arg_0]
0x1800889b4  mov     rbp, [rsp+58h+arg_10]
0x1800889b9  add     rsp, 40h
0x1800889bd  pop     r14
0x1800889bf  pop     rdi
0x1800889c0  pop     rsi
0x1800889c1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800889c6  call    ??_GRPC_THREAD_POOL_ALPC@@QEAAPEAXI@Z; RPC_THREAD_POOL_ALPC::`scalar deleting destructor'(uint)
0x1800889cb  jmp     loc_180088903
0x1800889d0  add     rcx, 1A8h
0x1800889d7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800889de  nop     dword ptr [rax+rax+00h]
0x1800889e3  jmp     loc_180088821
0x1800889e8  mov     rcx, [rdi+198h]; hHandle
0x1800889ef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800889f2  call    cs:__imp_WaitForSingleObject
0x1800889f9  nop     dword ptr [rax+rax+00h]
0x1800889fe  jmp     loc_1800888D8
```
