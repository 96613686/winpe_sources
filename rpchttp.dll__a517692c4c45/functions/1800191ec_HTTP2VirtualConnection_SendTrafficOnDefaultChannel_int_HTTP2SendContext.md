# HTTP2VirtualConnection::SendTrafficOnDefaultChannel(int,HTTP2SendContext *)

- ea: `0x1800191ec`
- end: `0x180019259`
- name: `?SendTrafficOnDefaultChannel@HTTP2VirtualConnection@@QEAAJHPEAVHTTP2SendContext@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(HTTP2VirtualConnection *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a094`
- `0x18000dfe8`
- `0x180010864`
- `0x1800111a4`
- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`
- `0x180016ac0`
- `0x180018bec`
- `0x180018e20`
- `0x180018eb0`

## callees

- `0x18000f334`
- `0x1800191ec`
- `0x18001ac1c`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2VirtualConnection::SendTrafficOnDefaultChannel(
        HTTP2VirtualConnection *this,
        int a2,
        struct HTTP2SendContext *a3)
{
  struct HTTP2ChannelPointer *v4; // r8
  volatile int *v5; // rdx
  struct HTTP2Channel *v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  HTTP2ChannelPointer *v10; // [rsp+48h] [rbp+20h] BYREF

  v10 = 0;
  if ( a2 )
  {
    v4 = (HTTP2VirtualConnection *)((char *)this + 120);
    v5 = (volatile int *)((char *)this + 192);
  }
  else
  {
    v4 = (HTTP2VirtualConnection *)((char *)this + 200);
    v5 = (volatile int *)((char *)this + 272);
  }
  v6 = HTTP2VirtualConnection::LockDefaultChannel(this, v5, v4, &v10);
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(struct HTTP2Channel *, struct HTTP2SendContext *))(*(_QWORD *)v6 + 8LL))(v6, a3);
    HTTP2ChannelPointer::UnlockChannelPointer(v10, v8);
  }
  else
  {
    return (unsigned int)-1073606648;
  }
  return v7;
}

```

## disassembly

```asm
0x1800191ec  push    rbx
0x1800191ee  sub     rsp, 20h
0x1800191f2  mov     [rsp+28h+arg_18], 0
0x1800191fb  mov     rbx, r8
0x1800191fe  lea     r9, [rsp+28h+arg_18]; struct HTTP2ChannelPointer **
0x180019203  test    edx, edx
0x180019205  jz      short loc_180019214
0x180019207  lea     r8, [rcx+78h]
0x18001920b  lea     rdx, [rcx+0C0h]
0x180019212  jmp     short loc_180019222
0x180019214  lea     r8, [rcx+0C8h]; struct HTTP2ChannelPointer *
0x18001921b  lea     rdx, [rcx+110h]; volatile int *
0x180019222  call    ?LockDefaultChannel@HTTP2VirtualConnection@@AEAAPEAVHTTP2Channel@@PECHQEAVHTTP2ChannelPointer@@PEAPEAV3@@Z; HTTP2VirtualConnection::LockDefaultChannel(int volatile *,HTTP2ChannelPointer * const,HTTP2ChannelPointer * *)
0x180019227  mov     rcx, rax
0x18001922a  test    rax, rax
0x18001922d  jz      short loc_18001924C
0x18001922f  mov     rax, [rax]
0x180019232  mov     rdx, rbx
0x180019235  mov     rax, [rax+8]
0x180019239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001923e  mov     rcx, [rsp+28h+arg_18]; this
0x180019243  mov     ebx, eax
0x180019245  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x18001924a  jmp     short loc_180019251
0x18001924c  mov     ebx, 0C0021008h
0x180019251  mov     eax, ebx
0x180019253  add     rsp, 20h
0x180019257  pop     rbx
0x180019258  retn
```
