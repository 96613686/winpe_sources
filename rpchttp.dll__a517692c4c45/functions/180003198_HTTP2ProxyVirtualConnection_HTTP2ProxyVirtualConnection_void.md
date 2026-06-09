# HTTP2ProxyVirtualConnection::~HTTP2ProxyVirtualConnection(void)

- ea: `0x180003198`
- end: `0x180003210`
- name: `??1HTTP2ProxyVirtualConnection@@UEAA@XZ`
- size: `120`
- prototype: `void __fastcall(HTTP2ProxyVirtualConnection *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000308c`
- `0x180003610`

## callees

- `0x180003198`
- `0x180003250`
- `0x1800213e0`
- `0x180025010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800031fd`
- `ntdll!RtlDeleteCriticalSection` at `0x1800031fd`
- `RPCRT4!I_RpcFree` at `0x1800031ad`
- `RPCRT4!I_RpcFree` at `0x1800031ad`

## pseudocode

```c
void __fastcall HTTP2ProxyVirtualConnection::~HTTP2ProxyVirtualConnection(HTTP2ProxyVirtualConnection *this)
{
  void *v2; // rcx
  LBSVirtualChannelState *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 49);
  if ( v2 )
  {
    I_RpcFree(v2);
    *((_QWORD *)this + 49) = 0;
  }
  v3 = (LBSVirtualChannelState *)*((_QWORD *)this + 48);
  if ( v3 )
  {
    *((_QWORD *)this + 48) = 0;
    LBSVirtualChannelState::RundownSession(v3);
  }
  if ( *((_QWORD *)this + 47) )
    (*(void (**)(void))(*((_QWORD *)this + 46) + 32LL))();
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 312));
  HTTP2VirtualConnection::~HTTP2VirtualConnection(this);
}

```

## disassembly

```asm
0x180003198  push    rbx
0x18000319a  sub     rsp, 20h
0x18000319e  mov     rbx, rcx
0x1800031a1  mov     rcx, [rcx+188h]; Object
0x1800031a8  test    rcx, rcx
0x1800031ab  jz      short loc_1800031BE
0x1800031ad  call    cs:__imp_I_RpcFree
0x1800031b3  mov     qword ptr [rbx+188h], 0
0x1800031be  mov     rcx, [rbx+180h]; this
0x1800031c5  test    rcx, rcx
0x1800031c8  jz      short loc_1800031DA
0x1800031ca  mov     qword ptr [rbx+180h], 0
0x1800031d5  call    ?RundownSession@LBSVirtualChannelState@@QEAAXXZ; LBSVirtualChannelState::RundownSession(void)
0x1800031da  mov     rcx, [rbx+178h]
0x1800031e1  test    rcx, rcx
0x1800031e4  jz      short loc_1800031F6
0x1800031e6  mov     rax, [rbx+170h]
0x1800031ed  mov     rax, [rax+20h]
0x1800031f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f6  lea     rcx, [rbx+138h]; CriticalSection
0x1800031fd  call    cs:__imp_RtlDeleteCriticalSection
0x180003203  mov     rcx, rbx; this
0x180003206  add     rsp, 20h
0x18000320a  pop     rbx
0x18000320b  jmp     ??1HTTP2VirtualConnection@@UEAA@XZ; HTTP2VirtualConnection::~HTTP2VirtualConnection(void)
```
