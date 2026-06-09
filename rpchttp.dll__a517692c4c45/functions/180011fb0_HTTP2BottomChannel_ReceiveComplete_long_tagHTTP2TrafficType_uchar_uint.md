# HTTP2BottomChannel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)

- ea: `0x180011fb0`
- end: `0x18001204a`
- name: `?ReceiveComplete@HTTP2BottomChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800167d0`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180011fe6`
- `RPCRT4!I_RpcLogEvent` at `0x18001202a`
- `RPCRT4!I_RpcLogEvent` at `0x180011fe6`
- `RPCRT4!I_RpcLogEvent` at `0x18001202a`

## pseudocode

```c
__int64 __fastcall HTTP2BottomChannel::ReceiveComplete(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 v3; // r8
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-48h]

  v9 = a2;
  v2 = a1;
  v3 = a1;
  LOBYTE(a2) = 111;
  LOBYTE(a1) = 50;
  I_RpcLogEvent(a1, a2, v3, 17039364, v9, 0, 0);
  v4 = HTTP2TransportChannel::ReceiveComplete(v2);
  LOBYTE(v5) = 111;
  LOBYTE(v6) = 50;
  v7 = v4;
  I_RpcLogEvent(v6, v5, v2, 262148, v4, 0, 0);
  return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 80LL))(v2, v7);
}

```

## disassembly

```asm
0x180011fb0  push    rbx
0x180011fb2  push    rsi
0x180011fb3  push    rdi
0x180011fb4  push    r14
0x180011fb6  sub     rsp, 48h
0x180011fba  mov     [rsp+68h+var_38], 0
0x180011fc2  mov     edi, r8d
0x180011fc5  mov     rbx, r9
0x180011fc8  mov     [rsp+68h+var_40], 0
0x180011fd0  mov     [rsp+68h+var_48], edx
0x180011fd4  mov     esi, edx
0x180011fd6  mov     r14, rcx
0x180011fd9  mov     r8, rcx
0x180011fdc  mov     dl, 6Fh ; 'o'
0x180011fde  mov     r9d, 1040004h
0x180011fe4  mov     cl, 32h ; '2'
0x180011fe6  call    cs:__imp_I_RpcLogEvent
0x180011fec  mov     eax, [rsp+68h+arg_20]
0x180011ff3  mov     r9, rbx
0x180011ff6  mov     r8d, edi
0x180011ff9  mov     [rsp+68h+var_48], eax
0x180011ffd  mov     edx, esi
0x180011fff  mov     rcx, r14
0x180012002  call    ?ReceiveComplete@HTTP2TransportChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z; HTTP2TransportChannel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)
0x180012007  mov     [rsp+68h+var_38], 0
0x18001200f  mov     r9d, 40004h
0x180012015  mov     [rsp+68h+var_40], 0
0x18001201d  mov     r8, r14
0x180012020  mov     dl, 6Fh ; 'o'
0x180012022  mov     [rsp+68h+var_48], eax
0x180012026  mov     cl, 32h ; '2'
0x180012028  mov     ebx, eax
0x18001202a  call    cs:__imp_I_RpcLogEvent
0x180012030  mov     rcx, [r14]
0x180012033  mov     edx, ebx
0x180012035  mov     rax, [rcx+50h]
0x180012039  mov     rcx, r14
0x18001203c  add     rsp, 48h
0x180012040  pop     r14
0x180012042  pop     rdi
0x180012043  pop     rsi
0x180012044  pop     rbx
0x180012045  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
