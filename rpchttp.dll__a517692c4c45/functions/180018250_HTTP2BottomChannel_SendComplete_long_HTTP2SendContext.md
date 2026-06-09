# HTTP2BottomChannel::SendComplete(long,HTTP2SendContext *)

- ea: `0x180018250`
- end: `0x1800182e2`
- name: `?SendComplete@HTTP2BottomChannel@@UEAAJJPEAVHTTP2SendContext@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(HTTP2BottomChannel *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180018980`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180018286`
- `RPCRT4!I_RpcLogEvent` at `0x1800182bc`
- `RPCRT4!I_RpcLogEvent` at `0x180018286`
- `RPCRT4!I_RpcLogEvent` at `0x1800182bc`

## pseudocode

```c
__int64 __fastcall HTTP2BottomChannel::SendComplete(HTTP2BottomChannel *this, __int64 a2, struct HTTP2SendContext *a3)
{
  unsigned int v4; // edi
  HTTP2TransportChannel *v5; // rsi
  HTTP2BottomChannel *v6; // r8
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // [rsp+20h] [rbp-28h]

  v4 = a2;
  v11 = a2;
  v5 = this;
  v6 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v6, 17104900, v11, 0, 0);
  v7 = HTTP2TransportChannel::SendComplete(v5, v4, a3);
  LOBYTE(v8) = 111;
  LOBYTE(v9) = 50;
  LODWORD(a3) = v7;
  I_RpcLogEvent(v9, v8, v5, 327684, v7, 0, 0);
  return (*(__int64 (__fastcall **)(HTTP2TransportChannel *, _QWORD))(*(_QWORD *)v5 + 80LL))(v5, (unsigned int)a3);
}

```

## disassembly

```asm
0x180018250  mov     rax, rsp
0x180018253  mov     [rax+8], rbx
0x180018257  mov     [rax+10h], rsi
0x18001825b  push    rdi
0x18001825c  sub     rsp, 40h
0x180018260  mov     dword ptr [rax-18h], 0
0x180018267  mov     rbx, r8
0x18001826a  mov     dword ptr [rax-20h], 0
0x180018271  mov     edi, edx
0x180018273  mov     [rax-28h], edx
0x180018276  mov     rsi, rcx
0x180018279  mov     r8, rcx
0x18001827c  mov     dl, 6Fh ; 'o'
0x18001827e  mov     r9d, 1050004h
0x180018284  mov     cl, 32h ; '2'
0x180018286  call    cs:__imp_I_RpcLogEvent
0x18001828c  mov     r8, rbx; struct HTTP2SendContext *
0x18001828f  mov     edx, edi; int
0x180018291  mov     rcx, rsi; this
0x180018294  call    ?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)
0x180018299  mov     [rsp+48h+var_18], 0
0x1800182a1  mov     r9d, 50004h
0x1800182a7  mov     [rsp+48h+var_20], 0
0x1800182af  mov     r8, rsi
0x1800182b2  mov     dl, 6Fh ; 'o'
0x1800182b4  mov     [rsp+48h+var_28], eax
0x1800182b8  mov     cl, 32h ; '2'
0x1800182ba  mov     ebx, eax
0x1800182bc  call    cs:__imp_I_RpcLogEvent
0x1800182c2  mov     rcx, [rsi]
0x1800182c5  mov     edx, ebx
0x1800182c7  mov     rax, [rcx+50h]
0x1800182cb  mov     rcx, rsi
0x1800182ce  mov     rbx, [rsp+48h+arg_0]
0x1800182d3  mov     rsi, [rsp+48h+arg_8]
0x1800182d8  add     rsp, 40h
0x1800182dc  pop     rdi
0x1800182dd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
