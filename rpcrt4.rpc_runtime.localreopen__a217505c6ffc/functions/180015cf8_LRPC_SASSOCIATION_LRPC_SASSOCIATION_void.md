# LRPC_SASSOCIATION::~LRPC_SASSOCIATION(void)

- ea: `0x180015cf8`
- end: `0x180015e99`
- name: `??1LRPC_SASSOCIATION@@UEAA@XZ`
- size: `417`
- prototype: `void __fastcall(LRPC_SASSOCIATION *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180015910`
- `0x1800aafb8`

## callees

- `0x180015cf8`
- `0x1800160dc`
- `0x180016100`
- `0x180016128`
- `0x1800161f4`
- `0x1800162a8`
- `0x1800164b4`
- `0x1800165d0`
- `0x180016e1c`
- `0x180023a40`
- `0x180028670`
- `0x1800d7010`

## import_xrefs

- `KERNELBASE!Sleep` at `0x180015e70`
- `KERNELBASE!Sleep` at `0x180015e70`
- `ntdll!NtClose` at `0x180015d59`
- `ntdll!NtClose` at `0x180015d59`
- `ntdll!RtlDeleteCriticalSection` at `0x180015e05`
- `ntdll!RtlDeleteCriticalSection` at `0x180015e05`

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
  ContextCollection *v14; // rdi

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
    if ( dword_1800FE624 )
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
    v14 = (ContextCollection *)*((_QWORD *)this + 4);
    DestroyContextHandlesForGuard(v14, 1, 0);
    if ( v14 )
      FreeWrapper(v14);
  }
  *((_DWORD *)this + 2) = -1713459815;
}

```

## disassembly

```asm
0x180015cf8  push    rbx
0x180015cfa  push    rsi
0x180015cfb  push    rdi
0x180015cfc  push    r14
0x180015cfe  sub     rsp, 38h
0x180015d02  cmp     dword ptr [rcx+28h], 0FFFFFFFFh
0x180015d06  lea     rax, ??_7LRPC_SASSOCIATION@@6B@; const LRPC_SASSOCIATION::`vftable'
0x180015d0d  mov     [rcx], rax
0x180015d10  mov     rbx, rcx
0x180015d13  jz      short loc_180015D1A
0x180015d15  call    ?RemoveFromAddressDictionary@LRPC_SASSOCIATION@@QEAAXXZ; LRPC_SASSOCIATION::RemoveFromAddressDictionary(void)
0x180015d1a  mov     rax, [rbx+38h]
0x180015d1e  mov     rcx, [rax+98h]; this
0x180015d25  test    rcx, rcx
0x180015d28  jnz     loc_180015E61
0x180015d2e  mov     r8, [rbx+30h]; __int64
0x180015d32  test    r8, r8
0x180015d35  jz      short loc_180015D6D
0x180015d37  cmp     cs:dword_1800FE624, 0
0x180015d3e  jz      short loc_180015D55
0x180015d40  xor     r9d, r9d; __int64
0x180015d43  mov     [rsp+58h+var_38], 0; __int64
0x180015d4c  mov     dl, 64h ; 'd'; unsigned __int8
0x180015d4e  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180015d50  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x180015d55  mov     rcx, [rbx+30h]; Handle
0x180015d59  call    cs:__imp_NtClose
0x180015d60  nop     dword ptr [rax+rax+00h]
0x180015d65  mov     qword ptr [rbx+30h], 0
0x180015d6d  mov     eax, [rbx+1B0h]
0x180015d73  test    al, 1
0x180015d75  jz      short loc_180015D83
0x180015d77  lock dec cs:?EnableIdleLrpcSContextsCleanupCount@@3KA; ulong EnableIdleLrpcSContextsCleanupCount
0x180015d7e  call    ?DecrementPeriodicGarbageCollectItems@@YAXXZ; DecrementPeriodicGarbageCollectItems(void)
0x180015d83  xor     eax, eax
0x180015d85  cmp     eax, [rbx+48h]
0x180015d88  jnb     short loc_180015DA7
0x180015d8a  mov     ecx, eax
0x180015d8c  lea     edi, [rax+1]
0x180015d8f  mov     rax, [rbx+40h]
0x180015d93  mov     rcx, [rax+rcx*8]; lpMem
0x180015d97  test    rcx, rcx
0x180015d9a  jnz     short loc_180015DA0
0x180015d9c  mov     eax, edi
0x180015d9e  jmp     short loc_180015D85
0x180015da0  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180015da5  jmp     short loc_180015D9C
0x180015da7  xor     eax, eax
0x180015da9  lea     rsi, [rbx+98h]
0x180015db0  cmp     eax, [rsi+8]
0x180015db3  jnb     short loc_180015DD1
0x180015db5  mov     ecx, eax
0x180015db7  lea     edi, [rax+1]
0x180015dba  mov     rax, [rsi]
0x180015dbd  mov     rcx, [rax+rcx*8]; this
0x180015dc1  test    rcx, rcx
0x180015dc4  jnz     short loc_180015DCA
0x180015dc6  mov     eax, edi
0x180015dc8  jmp     short loc_180015DB0
0x180015dca  call    ??_GLRPC_SCONTEXT@@QEAAPEAXI@Z; LRPC_SCONTEXT::`scalar deleting destructor'(uint)
0x180015dcf  jmp     short loc_180015DC6
0x180015dd1  mov     rcx, [rbx+1B8h]; lpMem
0x180015dd8  test    rcx, rcx
0x180015ddb  jnz     loc_180015E84
0x180015de1  mov     rcx, rbx; this
0x180015de4  call    ?FreeAllCausalFlows@LRPC_SASSOCIATION@@AEAAXXZ; LRPC_SASSOCIATION::FreeAllCausalFlows(void)
0x180015de9  mov     rcx, [rbx+38h]
0x180015ded  mov     rax, [rcx]
0x180015df0  mov     rax, [rax+20h]
0x180015df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df9  mov     rcx, rsi; this
0x180015dfc  call    ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
0x180015e01  lea     rcx, [rbx+70h]; CriticalSection
0x180015e05  call    cs:__imp_RtlDeleteCriticalSection
0x180015e0c  nop     dword ptr [rax+rax+00h]
0x180015e11  lea     rcx, [rbx+40h]; this
0x180015e15  call    ??1QUEUE@@QEAA@XZ; QUEUE::~QUEUE(void)
0x180015e1a  cmp     qword ptr [rbx+20h], 0
0x180015e1f  jz      short loc_180015E4F
0x180015e21  mov     edi, 14h
0x180015e26  call    ?RpcpCreateThreadIfThreadPoolIsRunning@@YAJXZ; RpcpCreateThreadIfThreadPoolIsRunning(void)
0x180015e2b  test    eax, eax
0x180015e2d  jnz     short loc_180015E6B
0x180015e2f  mov     rdi, [rbx+20h]
0x180015e33  xor     r8d, r8d; void *
0x180015e36  mov     rcx, rdi; this
0x180015e39  lea     edx, [r8+1]; int
0x180015e3d  call    ?DestroyContextHandlesForGuard@@YAXPEAXH0@Z; DestroyContextHandlesForGuard(void *,int,void *)
0x180015e42  test    rdi, rdi
0x180015e45  jz      short loc_180015E4F
0x180015e47  mov     rcx, rdi; lpMem
0x180015e4a  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180015e4f  mov     dword ptr [rbx+8], 99DEAD99h
0x180015e56  add     rsp, 38h
0x180015e5a  pop     r14
0x180015e5c  pop     rdi
0x180015e5d  pop     rsi
0x180015e5e  pop     rbx
0x180015e5f  retn
0x180015e61  call    ?EndActivity@RPCP_INTERFACE_GROUP@@QEAAXXZ; RPCP_INTERFACE_GROUP::EndActivity(void)
0x180015e66  jmp     loc_180015D2E
0x180015e6b  mov     ecx, 0Ah; dwMilliseconds
0x180015e70  call    cs:__imp_Sleep
0x180015e77  nop     dword ptr [rax+rax+00h]
0x180015e7c  dec     edi
0x180015e7e  test    edi, edi
0x180015e80  jle     short loc_180015E2F
0x180015e82  jmp     short loc_180015E26
0x180015e84  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180015e89  mov     qword ptr [rbx+1B8h], 0
0x180015e94  jmp     loc_180015DE1
```
