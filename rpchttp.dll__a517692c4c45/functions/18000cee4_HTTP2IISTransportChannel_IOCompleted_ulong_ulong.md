# HTTP2IISTransportChannel::IOCompleted(ulong,ulong)

- ea: `0x18000cee4`
- end: `0x18000cfb5`
- name: `?IOCompleted@HTTP2IISTransportChannel@@QEAAXKK@Z`
- size: `209`
- prototype: `void __fastcall(HTTP2IISTransportChannel *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011230`

## callees

- `0x18000cee4`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x18000cf20`
- `RPCRT4!I_RpcLogEvent` at `0x18000cfa4`
- `RPCRT4!I_RpcLogEvent` at `0x18000cf20`
- `RPCRT4!I_RpcLogEvent` at `0x18000cfa4`

## pseudocode

```c
void __fastcall HTTP2IISTransportChannel::IOCompleted(HTTP2IISTransportChannel *this, __int64 a2, int a3)
{
  HTTP2IISTransportChannel *v4; // rbx
  HTTP2IISTransportChannel *v5; // r8
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx

  v4 = this;
  v5 = this;
  LOBYTE(this) = 50;
  LOBYTE(a2) = 111;
  I_RpcLogEvent(this, a2, v5, 17301509, a3, 0, 0);
  v6 = *(_QWORD *)v4;
  if ( *((_DWORD *)v4 + 15) == 1 )
    (*(void (__fastcall **)(HTTP2IISTransportChannel *, _QWORD, __int64))(v6 + 112))(v4, a3 != 0 ? 0xC0021009 : 0, 4);
  else
    (*(void (__fastcall **)(HTTP2IISTransportChannel *, _QWORD, _QWORD))(v6 + 24))(
      v4,
      a3 != 0 ? 0xC002100A : 0,
      *((_QWORD *)v4 + 10));
  LOBYTE(v7) = 111;
  LOBYTE(v8) = 50;
  I_RpcLogEvent(v8, v7, v4, 524293, 0, 0, 0);
}

```

## disassembly

```asm
0x18000cee4  mov     rax, rsp
0x18000cee7  mov     [rax+18h], rbx
0x18000ceeb  mov     [rax+10h], edx
0x18000ceee  push    rdi
0x18000ceef  sub     rsp, 40h
0x18000cef3  mov     dword ptr [rax-18h], 0
0x18000cefa  mov     edi, r8d
0x18000cefd  mov     dword ptr [rax-20h], 0
0x18000cf04  mov     rbx, rcx
0x18000cf07  mov     [rax-28h], r8d
0x18000cf0b  mov     r9d, 1080005h
0x18000cf11  mov     r8, rcx
0x18000cf14  mov     qword ptr [rax+8], 0
0x18000cf1c  mov     cl, 32h ; '2'
0x18000cf1e  mov     dl, 6Fh ; 'o'
0x18000cf20  call    cs:__imp_I_RpcLogEvent
0x18000cf26  mov     rax, [rbx]
0x18000cf29  mov     r9d, 1
0x18000cf2f  cmp     [rbx+3Ch], r9d
0x18000cf33  jnz     short loc_18000CF65
0x18000cf35  mov     rax, [rax+70h]
0x18000cf39  lea     rcx, [rsp+48h+arg_8]
0x18000cf3e  mov     [rsp+48h+var_20], rcx
0x18000cf43  lea     r8d, [r9+3]
0x18000cf47  neg     edi
0x18000cf49  lea     rcx, [rsp+48h+arg_0]
0x18000cf4e  mov     [rsp+48h+var_28], rcx
0x18000cf53  mov     rcx, rbx
0x18000cf56  sbb     edx, edx
0x18000cf58  and     edx, 0C0021009h
0x18000cf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf63  jmp     short loc_18000CF7F
0x18000cf65  mov     r8, [rbx+50h]
0x18000cf69  neg     edi
0x18000cf6b  mov     rax, [rax+18h]
0x18000cf6f  mov     rcx, rbx
0x18000cf72  sbb     edx, edx
0x18000cf74  and     edx, 0C002100Ah
0x18000cf7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf7f  mov     [rsp+48h+var_18], 0
0x18000cf87  mov     r9d, 80005h
0x18000cf8d  mov     dword ptr [rsp+48h+var_20], 0
0x18000cf95  mov     r8, rbx
0x18000cf98  mov     dl, 6Fh ; 'o'
0x18000cf9a  mov     dword ptr [rsp+48h+var_28], 0
0x18000cfa2  mov     cl, 32h ; '2'
0x18000cfa4  call    cs:__imp_I_RpcLogEvent
0x18000cfaa  mov     rbx, [rsp+48h+arg_10]
0x18000cfaf  add     rsp, 40h
0x18000cfb3  pop     rdi
0x18000cfb4  retn
```
