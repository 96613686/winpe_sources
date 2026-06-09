# HTTP2ChannelPointer::SetChannel(HTTP2Channel *)

- ea: `0x180019278`
- end: `0x1800192de`
- name: `?SetChannel@HTTP2ChannelPointer@@QEAAXPEAVHTTP2Channel@@@Z`
- size: `102`
- prototype: `void __fastcall(HTTP2ChannelPointer *__hidden this, struct HTTP2Channel *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013920`
- `0x180014850`
- `0x1800193d0`
- `0x18001941c`
- `0x18001977c`
- `0x1800197dc`

## callees

- `0x180019278`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x1800192ab`
- `RPCRT4!I_RpcLogEvent` at `0x1800192ab`

## pseudocode

```c
void __fastcall HTTP2ChannelPointer::SetChannel(HTTP2ChannelPointer *this, struct HTTP2Channel *a2)
{
  struct HTTP2Channel *v2; // rdi
  int v4; // ett
  signed __int32 v5[8]; // [rsp+0h] [rbp-48h] BYREF

  v2 = a2;
  _InterlockedOr(v5, 0);
  LOBYTE(a2) = 115;
  I_RpcLogEvent(50, a2, this, *((_QWORD *)this + 1), *(_DWORD *)this, 1, 1);
  _InterlockedOr(v5, 0);
  if ( *(int *)this < 0 )
  {
    *((_QWORD *)this + 1) = v2;
    _m_prefetchw(this);
    do
    {
      _InterlockedOr(v5, 0);
      v4 = *(_DWORD *)this;
    }
    while ( v4 != _InterlockedCompareExchange((volatile signed __int32 *)this, *(_DWORD *)this + 101, *(_DWORD *)this) );
  }
}

```

## disassembly

```asm
0x180019278  mov     [rsp+arg_8], rbx
0x18001927d  push    rdi
0x18001927e  sub     rsp, 40h
0x180019282  mov     rdi, rdx
0x180019285  mov     rbx, rcx
0x180019288  lock or [rsp+48h+var_48], 0
0x18001928d  mov     eax, [rcx]
0x18001928f  mov     r8, rbx
0x180019292  mov     r9, [rbx+8]
0x180019296  mov     ecx, 1
0x18001929b  mov     [rsp+48h+var_18], ecx
0x18001929f  mov     dl, 73h ; 's'
0x1800192a1  mov     [rsp+48h+var_20], ecx
0x1800192a5  mov     cl, 32h ; '2'
0x1800192a7  mov     [rsp+48h+var_28], eax
0x1800192ab  call    cs:__imp_I_RpcLogEvent
0x1800192b1  lock or [rsp+48h+var_48], 0
0x1800192b6  mov     eax, [rbx]
0x1800192b8  test    eax, eax
0x1800192ba  jns     short loc_1800192D3
0x1800192bc  mov     [rbx+8], rdi
0x1800192c0  prefetchw byte ptr [rbx]
0x1800192c3  lock or [rsp+48h+var_48], 0
0x1800192c8  mov     eax, [rbx]
0x1800192ca  lea     ecx, [rax+65h]
0x1800192cd  lock cmpxchg [rbx], ecx
0x1800192d1  jnz     short loc_1800192C3
0x1800192d3  mov     rbx, [rsp+48h+arg_8]
0x1800192d8  add     rsp, 40h
0x1800192dc  pop     rdi
0x1800192dd  retn
```
