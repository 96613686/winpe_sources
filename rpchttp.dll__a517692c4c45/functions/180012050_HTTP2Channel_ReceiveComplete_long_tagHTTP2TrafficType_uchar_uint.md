# HTTP2Channel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)

- ea: `0x180012050`
- end: `0x180012103`
- name: `?ReceiveComplete@HTTP2Channel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a3b4`
- `0x180012050`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180012087`
- `RPCRT4!I_RpcLogEvent` at `0x1800120f0`
- `RPCRT4!I_RpcLogEvent` at `0x180012087`
- `RPCRT4!I_RpcLogEvent` at `0x1800120f0`

## pseudocode

```c
__int64 __fastcall HTTP2Channel::ReceiveComplete(
        HTTP2Channel *a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  unsigned int v7; // esi
  HTTP2Channel *v8; // rdi
  HTTP2Channel *v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // ebx
  int v14; // [rsp+20h] [rbp-48h]

  v14 = a2;
  v7 = a2;
  v8 = a1;
  v9 = a1;
  LOBYTE(a2) = 111;
  LOBYTE(a1) = 50;
  I_RpcLogEvent(a1, a2, v9, 17039363, v14, 0, 0);
  v12 = (*(__int64 (__fastcall **)(HTTP2Channel *, _QWORD, _QWORD, unsigned __int8 *, unsigned int))(*(_QWORD *)v8 + 152LL))(
          v8,
          v7,
          a3,
          a4,
          a5);
  if ( v12 != -1073606615 )
    v12 = HTTP2Channel::ForwardUpReceiveComplete(v8, v7, a4, a5);
  LOBYTE(v10) = 111;
  LOBYTE(v11) = 50;
  I_RpcLogEvent(v11, v10, v8, 262147, v12, 0, 0);
  return v12;
}

```

## disassembly

```asm
0x180012050  push    rbx
0x180012052  push    rbp
0x180012053  push    rsi
0x180012054  push    rdi
0x180012055  push    r14
0x180012057  sub     rsp, 40h
0x18001205b  mov     [rsp+68h+var_38], 0
0x180012063  mov     ebx, r8d
0x180012066  mov     rbp, r9
0x180012069  mov     [rsp+68h+var_40], 0
0x180012071  mov     [rsp+68h+var_48], edx
0x180012075  mov     esi, edx
0x180012077  mov     rdi, rcx
0x18001207a  mov     r8, rcx
0x18001207d  mov     dl, 6Fh ; 'o'
0x18001207f  mov     r9d, 1040003h
0x180012085  mov     cl, 32h ; '2'
0x180012087  call    cs:__imp_I_RpcLogEvent
0x18001208d  mov     rax, [rdi]
0x180012090  mov     r9, rbp
0x180012093  mov     r14d, [rsp+68h+arg_20]
0x18001209b  mov     r8d, ebx
0x18001209e  mov     edx, esi
0x1800120a0  mov     [rsp+68h+var_48], r14d
0x1800120a5  mov     rcx, rdi
0x1800120a8  mov     rax, [rax+98h]
0x1800120af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120b4  mov     ebx, eax
0x1800120b6  cmp     eax, 0C0021029h
0x1800120bb  jz      short loc_1800120CF
0x1800120bd  mov     r9d, r14d; unsigned int
0x1800120c0  mov     r8, rbp; unsigned __int8 *
0x1800120c3  mov     edx, esi; int
0x1800120c5  mov     rcx, rdi; this
0x1800120c8  call    ?ForwardUpReceiveComplete@HTTP2Channel@@IEAAJJPEAEI@Z; HTTP2Channel::ForwardUpReceiveComplete(long,uchar *,uint)
0x1800120cd  mov     ebx, eax
0x1800120cf  mov     [rsp+68h+var_38], 0
0x1800120d7  mov     r9d, 40003h
0x1800120dd  mov     [rsp+68h+var_40], 0
0x1800120e5  mov     r8, rdi
0x1800120e8  mov     dl, 6Fh ; 'o'
0x1800120ea  mov     [rsp+68h+var_48], ebx
0x1800120ee  mov     cl, 32h ; '2'
0x1800120f0  call    cs:__imp_I_RpcLogEvent
0x1800120f6  mov     eax, ebx
0x1800120f8  add     rsp, 40h
0x1800120fc  pop     r14
0x1800120fe  pop     rdi
0x1800120ff  pop     rsi
0x180012100  pop     rbp
0x180012101  pop     rbx
0x180012102  retn
```
