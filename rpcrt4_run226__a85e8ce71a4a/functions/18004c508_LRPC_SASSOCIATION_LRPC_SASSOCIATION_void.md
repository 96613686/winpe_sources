# LRPC_SASSOCIATION::~LRPC_SASSOCIATION(void)

- ea: `0x18004c508`
- end: `0x18004c67b`
- name: `??1LRPC_SASSOCIATION@@UEAA@XZ`
- size: `371`
- prototype: `void __fastcall(LRPC_SASSOCIATION *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18004c140`
- `0x1800a76d8`

## callees

- `0x180022870`
- `0x1800274e0`
- `0x18004a8c8`
- `0x18004c508`
- `0x18004c8b0`
- `0x18004c8d8`
- `0x18004c990`
- `0x18004ca30`
- `0x18004cafc`
- `0x18004cbe0`
- `0x18004d1d8`
- `0x1800d2010`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18004c658`
- `KERNELBASE!Sleep` at `0x18004c658`
- `ntdll!NtClose` at `0x18004c569`
- `ntdll!NtClose` at `0x18004c569`
- `ntdll!RtlDeleteCriticalSection` at `0x18004c60b`
- `ntdll!RtlDeleteCriticalSection` at `0x18004c60b`

## pseudocode

```c
void __fastcall LRPC_SASSOCIATION::~LRPC_SASSOCIATION(LRPC_SASSOCIATION *this, unsigned int a2)
{
  bool v2; // zf
  RPCP_INTERFACE_GROUP *v4; // rcx
  __int64 v5; // r8
  unsigned int i; // eax
  unsigned int v7; // edi
  void *v8; // rcx
  unsigned int j; // eax
  unsigned int v10; // edi
  LRPC_SCONTEXT *v11; // rcx
  void *v12; // rcx
  int k; // edi

  v2 = *((_DWORD *)this + 10) == -1;
  *(_QWORD *)this = &LRPC_SASSOCIATION::`vftable';
  if ( !v2 )
    LRPC_SASSOCIATION::RemoveFromAddressDictionary(this);
  v4 = *(RPCP_INTERFACE_GROUP **)(*((_QWORD *)this + 7) + 152LL);
  if ( v4 )
    RPCP_INTERFACE_GROUP::EndActivity(v4);
  v5 = *((_QWORD *)this + 6);
  if ( v5 )
  {
    if ( dword_1800F9624 )
      LogEventToEtw(0x4Cu, 0x64u, v5, 0, 0);
    NtClose(*((HANDLE *)this + 6));
    *((_QWORD *)this + 6) = 0;
  }
  if ( (*((_DWORD *)this + 108) & 1) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)&EnableIdleLrpcSContextsCleanupCount);
    DecrementPeriodicGarbageCollectItems();
  }
  for ( i = 0; i < *((_DWORD *)this + 18); i = v7 )
  {
    v7 = i + 1;
    v8 = *(void **)(*((_QWORD *)this + 8) + 8LL * i);
    if ( v8 )
      FreeWrapper(v8);
  }
  for ( j = 0; j < *((_DWORD *)this + 40); j = v10 )
  {
    v10 = j + 1;
    v11 = *(LRPC_SCONTEXT **)(*((_QWORD *)this + 19) + 8LL * j);
    if ( v11 )
      LRPC_SCONTEXT::`scalar deleting destructor'(v11, a2);
  }
  v12 = (void *)*((_QWORD *)this + 55);
  if ( v12 )
  {
    FreeWrapper(v12);
    *((_QWORD *)this + 55) = 0;
  }
  LRPC_SASSOCIATION::FreeAllCausalFlows(this);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7));
  QUEUE::~QUEUE((LRPC_SASSOCIATION *)((char *)this + 152));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 112));
  QUEUE::~QUEUE((LRPC_SASSOCIATION *)((char *)this + 64));
  if ( *((_QWORD *)this + 4) )
  {
    for ( k = 20; k > 0; --k )
    {
      if ( !(unsigned int)RpcpCreateThreadIfThreadPoolIsRunning() )
        break;
      Sleep(0xAu);
    }
    DestroyContextCollection(*((struct ContextCollection **)this + 4));
  }
  *((_DWORD *)this + 2) = -1713459815;
}

```

## disassembly

```asm
0x18004c508  push    rbx
0x18004c50a  push    rsi
0x18004c50b  push    rdi
0x18004c50c  push    r14
0x18004c50e  sub     rsp, 38h
0x18004c512  cmp     dword ptr [rcx+28h], 0FFFFFFFFh
0x18004c516  lea     rax, ??_7LRPC_SASSOCIATION@@6B@; const LRPC_SASSOCIATION::`vftable'
0x18004c51d  mov     [rcx], rax
0x18004c520  mov     rbx, rcx
0x18004c523  jz      short loc_18004C52A
0x18004c525  call    ?RemoveFromAddressDictionary@LRPC_SASSOCIATION@@QEAAXXZ; LRPC_SASSOCIATION::RemoveFromAddressDictionary(void)
0x18004c52a  mov     rax, [rbx+38h]
0x18004c52e  mov     rcx, [rax+98h]; this
0x18004c535  test    rcx, rcx
0x18004c538  jnz     loc_18004C649
0x18004c53e  mov     r8, [rbx+30h]; __int64
0x18004c542  test    r8, r8
0x18004c545  jz      short loc_18004C577
0x18004c547  cmp     cs:dword_1800F9624, 0
0x18004c54e  jz      short loc_18004C565
0x18004c550  xor     r9d, r9d; __int64
0x18004c553  mov     [rsp+58h+var_38], 0; __int64
0x18004c55c  mov     dl, 64h ; 'd'; unsigned __int8
0x18004c55e  mov     cl, 4Ch ; 'L'; unsigned __int8
0x18004c560  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x18004c565  mov     rcx, [rbx+30h]; Handle
0x18004c569  call    cs:__imp_NtClose
0x18004c56f  mov     qword ptr [rbx+30h], 0
0x18004c577  mov     eax, [rbx+1B0h]
0x18004c57d  test    al, 1
0x18004c57f  jz      short loc_18004C58D
0x18004c581  lock dec cs:?EnableIdleLrpcSContextsCleanupCount@@3KA; ulong EnableIdleLrpcSContextsCleanupCount
0x18004c588  call    ?DecrementPeriodicGarbageCollectItems@@YAXXZ; DecrementPeriodicGarbageCollectItems(void)
0x18004c58d  xor     eax, eax
0x18004c58f  cmp     eax, [rbx+48h]
0x18004c592  jnb     short loc_18004C5B1
0x18004c594  mov     ecx, eax
0x18004c596  lea     edi, [rax+1]
0x18004c599  mov     rax, [rbx+40h]
0x18004c59d  mov     rcx, [rax+rcx*8]; lpMem
0x18004c5a1  test    rcx, rcx
0x18004c5a4  jnz     short loc_18004C5AA
0x18004c5a6  mov     eax, edi
0x18004c5a8  jmp     short loc_18004C58F
0x18004c5aa  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004c5af  jmp     short loc_18004C5A6
0x18004c5b1  xor     eax, eax
0x18004c5b3  lea     rsi, [rbx+98h]
0x18004c5ba  cmp     eax, [rsi+8]
0x18004c5bd  jnb     short loc_18004C5DB
0x18004c5bf  mov     ecx, eax
0x18004c5c1  lea     edi, [rax+1]
0x18004c5c4  mov     rax, [rsi]
0x18004c5c7  mov     rcx, [rax+rcx*8]; this
0x18004c5cb  test    rcx, rcx
0x18004c5ce  jnz     short loc_18004C5D4
0x18004c5d0  mov     eax, edi
0x18004c5d2  jmp     short loc_18004C5BA
0x18004c5d4  call    ??_GLRPC_SCONTEXT@@QEAAPEAXI@Z; LRPC_SCONTEXT::`scalar deleting destructor'(uint)
0x18004c5d9  jmp     short loc_18004C5D0
0x18004c5db  mov     rcx, [rbx+1B8h]; lpMem
0x18004c5e2  test    rcx, rcx
0x18004c5e5  jnz     short loc_18004C666
0x18004c5e7  mov     rcx, rbx; this
0x18004c5ea  call    ?FreeAllCausalFlows@LRPC_SASSOCIATION@@AEAAXXZ; LRPC_SASSOCIATION::FreeAllCausalFlows(void)
0x18004c5ef  mov     rcx, [rbx+38h]
0x18004c5f3  mov     rax, [rcx]
0x18004c5f6  mov     rax, [rax+20h]
0x18004c5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5ff  mov     rcx, rsi; this
0x18004c602  call    ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
0x18004c607  lea     rcx, [rbx+70h]; CriticalSection
0x18004c60b  call    cs:__imp_RtlDeleteCriticalSection
0x18004c611  lea     rcx, [rbx+40h]; this
0x18004c615  call    ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
0x18004c61a  cmp     qword ptr [rbx+20h], 0
0x18004c61f  jz      short loc_18004C638
0x18004c621  mov     edi, 14h
0x18004c626  call    ?RpcpCreateThreadIfThreadPoolIsRunning@@YAJXZ; RpcpCreateThreadIfThreadPoolIsRunning(void)
0x18004c62b  test    eax, eax
0x18004c62d  jnz     short loc_18004C653
0x18004c62f  mov     rcx, [rbx+20h]; lpMem
0x18004c633  call    ?DestroyContextCollection@@YAXPEAVContextCollection@@@Z; DestroyContextCollection(ContextCollection *)
0x18004c638  mov     dword ptr [rbx+8], 99DEAD99h
0x18004c63f  add     rsp, 38h
0x18004c643  pop     r14
0x18004c645  pop     rdi
0x18004c646  pop     rsi
0x18004c647  pop     rbx
0x18004c648  retn
0x18004c649  call    ?EndActivity@RPCP_INTERFACE_GROUP@@QEAAXXZ; RPCP_INTERFACE_GROUP::EndActivity(void)
0x18004c64e  jmp     loc_18004C53E
0x18004c653  mov     ecx, 0Ah; dwMilliseconds
0x18004c658  call    cs:__imp_Sleep
0x18004c65e  dec     edi
0x18004c660  test    edi, edi
0x18004c662  jle     short loc_18004C62F
0x18004c664  jmp     short loc_18004C626
0x18004c666  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004c66b  mov     qword ptr [rbx+1B8h], 0
0x18004c676  jmp     loc_18004C5E7
```
