# HTTP2IISSenderTransportChannel::SendComplete(long,HTTP2SendContext *)

- ea: `0x180018580`
- end: `0x180018632`
- name: `?SendComplete@HTTP2IISSenderTransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(HTTP2IISSenderTransportChannel *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180018580`
- `0x180018980`
- `0x1800190d0`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x1800185b2`
- `RPCRT4!I_RpcLogEvent` at `0x180018613`
- `RPCRT4!I_RpcLogEvent` at `0x1800185b2`
- `RPCRT4!I_RpcLogEvent` at `0x180018613`

## pseudocode

```c
__int64 __fastcall HTTP2IISSenderTransportChannel::SendComplete(
        HTTP2IISSenderTransportChannel *this,
        __int64 a2,
        struct HTTP2SendContext *a3)
{
  unsigned int v4; // edi
  HTTP2IISSenderTransportChannel *v5; // rsi
  HTTP2IISSenderTransportChannel *v6; // r8
  signed __int32 v7; // ebp
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-48h]

  v4 = a2;
  v13 = a2;
  v5 = this;
  v6 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v6, 17104904, v13, 0, 0);
  *((_QWORD *)v5 + 10) = 0;
  v7 = _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 30, 0xFFFFFFFF);
  v8 = HTTP2TransportChannel::SendComplete(v5, v4, a3);
  v11 = v8;
  if ( !v8 || v8 == -1073606615 )
    v11 = HTTP2IISSenderTransportChannel::SendQueuedContextIfNecessary(v5, v7 - 1, v8);
  LOBYTE(v9) = 111;
  LOBYTE(v10) = 50;
  I_RpcLogEvent(v10, v9, v5, 327688, v11, 0, 0);
  return (*(__int64 (__fastcall **)(HTTP2IISSenderTransportChannel *, _QWORD))(*(_QWORD *)v5 + 80LL))(v5, v11);
}

```

## disassembly

```asm
0x180018580  push    rbx
0x180018582  push    rbp
0x180018583  push    rsi
0x180018584  push    rdi
0x180018585  sub     rsp, 48h
0x180018589  mov     [rsp+68h+var_38], 0
0x180018591  mov     rbx, r8
0x180018594  mov     edi, edx
0x180018596  mov     [rsp+68h+var_40], 0
0x18001859e  mov     [rsp+68h+var_48], edx
0x1800185a2  mov     rsi, rcx
0x1800185a5  mov     r8, rcx
0x1800185a8  mov     dl, 6Fh ; 'o'
0x1800185aa  mov     r9d, 1050008h
0x1800185b0  mov     cl, 32h ; '2'
0x1800185b2  call    cs:__imp_I_RpcLogEvent
0x1800185b8  or      ebp, 0FFFFFFFFh
0x1800185bb  mov     qword ptr [rsi+50h], 0
0x1800185c3  lock xadd [rsi+78h], ebp
0x1800185c8  mov     r8, rbx; struct HTTP2SendContext *
0x1800185cb  mov     edx, edi; int
0x1800185cd  mov     rcx, rsi; this
0x1800185d0  call    ?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)
0x1800185d5  mov     ebx, eax
0x1800185d7  test    eax, eax
0x1800185d9  jz      short loc_1800185E2
0x1800185db  cmp     eax, 0C0021029h
0x1800185e0  jnz     short loc_1800185F2
0x1800185e2  mov     r8d, eax; int
0x1800185e5  lea     edx, [rbp-1]; unsigned int
0x1800185e8  mov     rcx, rsi; this
0x1800185eb  call    ?SendQueuedContextIfNecessary@HTTP2IISSenderTransportChannel@@AEAAJKJ@Z; HTTP2IISSenderTransportChannel::SendQueuedContextIfNecessary(ulong,long)
0x1800185f0  mov     ebx, eax
0x1800185f2  mov     [rsp+68h+var_38], 0
0x1800185fa  mov     r9d, 50008h
0x180018600  mov     [rsp+68h+var_40], 0
0x180018608  mov     r8, rsi
0x18001860b  mov     dl, 6Fh ; 'o'
0x18001860d  mov     [rsp+68h+var_48], ebx
0x180018611  mov     cl, 32h ; '2'
0x180018613  call    cs:__imp_I_RpcLogEvent
0x180018619  mov     rax, [rsi]
0x18001861c  mov     edx, ebx
0x18001861e  mov     rcx, rsi
0x180018621  mov     rax, [rax+50h]
0x180018625  add     rsp, 48h
0x180018629  pop     rdi
0x18001862a  pop     rsi
0x18001862b  pop     rbp
0x18001862c  pop     rbx
0x18001862d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
