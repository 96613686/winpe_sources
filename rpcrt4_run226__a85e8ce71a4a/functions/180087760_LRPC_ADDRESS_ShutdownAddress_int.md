# LRPC_ADDRESS::ShutdownAddress(int)

- ea: `0x180087760`
- end: `0x18008793d`
- name: `?ShutdownAddress@LRPC_ADDRESS@@AEAAXH@Z`
- size: `477`
- prototype: `void __fastcall(LRPC_ADDRESS *__hidden this, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180086e00`
- `0x180086e10`

## callees

- `0x180021ce0`
- `0x18004c2b4`
- `0x18004c8d8`
- `0x180087760`
- `0x180087944`
- `0x1800879a0`
- `0x180087cbc`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtClose` at `0x1800878d6`
- `ntdll!NtClose` at `0x1800878d6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800877fb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800877fb`
- `ntdll!RtlEnterCriticalSection` at `0x18008778f`
- `ntdll!RtlEnterCriticalSection` at `0x18008778f`
- `ntdll!TpWaitForAlpcCompletion` at `0x180087839`
- `ntdll!TpWaitForAlpcCompletion` at `0x180087839`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180087810`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180087810`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18008791d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18008791d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180087932`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180087932`

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
0x180087760  mov     [rsp+arg_0], rbx
0x180087765  mov     [rsp+arg_10], rbp
0x18008776a  push    rsi
0x18008776b  push    rdi
0x18008776c  push    r14
0x18008776e  sub     rsp, 40h
0x180087772  mov     [rsp+58h+arg_8], 0
0x18008777a  mov     rdi, rcx
0x18008777d  test    edx, edx
0x18008777f  jz      loc_180087916
0x180087785  lea     rbp, [rdi+0A0h]
0x18008778c  mov     rcx, rbp; CriticalSection
0x18008778f  call    cs:__imp_RtlEnterCriticalSection
0x180087795  xor     r14d, r14d
0x180087798  xor     eax, eax
0x18008779a  cmp     eax, [rdi+0E0h]
0x1800877a0  jnb     short loc_1800877E0
0x1800877a2  mov     ecx, eax
0x1800877a4  lea     esi, [rax+1]
0x1800877a7  mov     rax, [rdi+0D8h]
0x1800877ae  mov     rbx, [rax+rcx*8]
0x1800877b2  test    rbx, rbx
0x1800877b5  jnz     short loc_1800877BB
0x1800877b7  mov     eax, esi
0x1800877b9  jmp     short loc_18008779A
0x1800877bb  mov     rcx, rbx; this
0x1800877be  call    ?FreeAllCausalFlows@LRPC_SASSOCIATION@@AEAAXXZ; LRPC_SASSOCIATION::FreeAllCausalFlows(void)
0x1800877c3  mov     rcx, rbx; this
0x1800877c6  call    ?NotifyAllActiveCalls@LRPC_SASSOCIATION@@AEAAXXZ; LRPC_SASSOCIATION::NotifyAllActiveCalls(void)
0x1800877cb  mov     rdx, [rbx+30h]; void *
0x1800877cf  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x1800877d4  call    ?DisconnectAlpcPort@LRPC_ADDRESS@@AEAAXPEAXPEAK@Z; LRPC_ADDRESS::DisconnectAlpcPort(void *,ulong *)
0x1800877d9  add     r14d, [rsp+58h+arg_8]
0x1800877de  jmp     short loc_1800877B7
0x1800877e0  mov     rdx, [rdi+0D0h]; void *
0x1800877e7  lea     r8, [rsp+58h+arg_8]; unsigned int *
0x1800877ec  call    ?DisconnectAlpcPort@LRPC_ADDRESS@@AEAAXPEAXPEAK@Z; LRPC_ADDRESS::DisconnectAlpcPort(void *,ulong *)
0x1800877f1  mov     ebx, [rsp+58h+arg_8]
0x1800877f5  mov     rcx, rbp; CriticalSection
0x1800877f8  add     ebx, r14d
0x1800877fb  call    cs:__imp_RtlLeaveCriticalSection
0x180087801  mov     eax, ebx
0x180087803  lea     rcx, [rdi+1A8h]
0x18008780a  xchg    eax, [rdi+194h]
0x180087810  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180087816  xor     ecx, ecx
0x180087818  xor     eax, eax
0x18008781a  lock cmpxchg [rdi+190h], ecx
0x180087822  cmp     ebx, eax
0x180087824  ja      loc_180087928
0x18008782a  mov     rcx, [rdi+110h]
0x180087831  test    rcx, rcx
0x180087834  jz      short loc_18008785A
0x180087836  mov     rcx, [rcx]
0x180087839  call    cs:__imp_TpWaitForAlpcCompletion
0x18008783f  mov     rcx, [rdi+110h]; this
0x180087846  test    rcx, rcx
0x180087849  jnz     loc_18008790C
0x18008784f  mov     qword ptr [rdi+110h], 0
0x18008785a  xor     eax, eax
0x18008785c  cmp     eax, [rdi+0E0h]
0x180087862  jnb     short loc_1800878A9
0x180087864  mov     ecx, eax
0x180087866  lea     ebx, [rax+1]
0x180087869  mov     rax, [rdi+0D8h]
0x180087870  mov     rcx, [rax+rcx*8]
0x180087874  test    rcx, rcx
0x180087877  jnz     short loc_18008787D
0x180087879  mov     eax, ebx
0x18008787b  jmp     short loc_18008785C
0x18008787d  xor     edx, edx
0x18008787f  xor     eax, eax
0x180087881  lock cmpxchg [rcx+0CCh], edx
0x180087889  mov     r8d, eax
0x18008788c  xor     eax, eax
0x18008788e  lock cmpxchg [rcx+0D0h], edx
0x180087896  cmp     r8d, eax
0x180087899  jnb     short loc_180087879
0x18008789b  mov     rax, [rcx]
0x18008789e  mov     rax, [rax+20h]
0x1800878a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800878a7  jmp     short loc_180087879
0x1800878a9  mov     rbx, [rdi+0D0h]
0x1800878b0  xor     r9d, r9d; void *
0x1800878b3  mov     r8, rbx; void *
0x1800878b6  mov     qword ptr [rdi+0D0h], 0
0x1800878c1  mov     dl, 64h ; 'd'; unsigned __int8
0x1800878c3  mov     [rsp+58h+var_38], 0; unsigned __int64
0x1800878cc  mov     cl, 4Ch ; 'L'; unsigned __int8
0x1800878ce  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800878d3  mov     rcx, rbx; Handle
0x1800878d6  call    cs:__imp_NtClose
0x1800878dc  mov     rcx, cs:?GlobalRpcServer@@3PEAVRPC_SERVER@@EA; this
0x1800878e3  mov     rdx, rdi; struct RPC_ADDRESS *
0x1800878e6  call    ?DeleteAddressIfNecessary@RPC_SERVER@@QEAAXPEAVRPC_ADDRESS@@@Z; RPC_SERVER::DeleteAddressIfNecessary(RPC_ADDRESS *)
0x1800878eb  mov     rax, [rdi]
0x1800878ee  mov     rcx, rdi
0x1800878f1  mov     rax, [rax+20h]
0x1800878f5  mov     rbx, [rsp+58h+arg_0]
0x1800878fa  mov     rbp, [rsp+58h+arg_10]
0x1800878ff  add     rsp, 40h
0x180087903  pop     r14
0x180087905  pop     rdi
0x180087906  pop     rsi
0x180087907  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18008790c  call    ??_GRPC_THREAD_POOL_ALPC@@QEAAPEAXI@Z; RPC_THREAD_POOL_ALPC::`scalar deleting destructor'(uint)
0x180087911  jmp     loc_18008784F
0x180087916  add     rcx, 1A8h
0x18008791d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180087923  jmp     loc_180087785
0x180087928  mov     rcx, [rdi+198h]; hHandle
0x18008792f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180087932  call    cs:__imp_WaitForSingleObject
0x180087938  jmp     loc_18008782A
```
