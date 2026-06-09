# HTTP2VirtualConnection::LockDefaultChannel(int volatile *,HTTP2ChannelPointer * const,HTTP2ChannelPointer * *)

- ea: `0x18000f334`
- end: `0x18000f3ab`
- name: `?LockDefaultChannel@HTTP2VirtualConnection@@AEAAPEAVHTTP2Channel@@PECHQEAVHTTP2ChannelPointer@@PEAPEAV3@@Z`
- size: `119`
- prototype: `struct HTTP2Channel *__fastcall(HTTP2VirtualConnection *__hidden this, volatile int *, struct HTTP2ChannelPointer *const, struct HTTP2ChannelPointer **)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x180007dcc`
- `0x180007e74`
- `0x180007ef0`
- `0x180009b40`
- `0x180009b90`
- `0x18000a340`
- `0x18000ad60`
- `0x18000ad90`
- `0x18000dfe8`
- `0x18000f3c0`
- `0x18000f3e0`
- `0x180010bbc`
- `0x180011450`
- `0x180012110`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`
- `0x180018c70`
- `0x180018d50`
- `0x1800191ec`
- `0x180019a00`
- `0x180019a90`
- `0x180019e10`
- `0x18001adac`

## callees

- `0x18000f2bc`
- `0x18000f334`
- `0x18001ac1c`

## pseudocode

```c
struct HTTP2Channel *__fastcall HTTP2VirtualConnection::LockDefaultChannel(
        HTTP2VirtualConnection *this,
        volatile int *a2,
        struct HTTP2ChannelPointer *const a3,
        struct HTTP2ChannelPointer **a4)
{
  int v4; // ebx
  __int64 v8; // rdx
  struct HTTP2Channel *i; // r8

  v4 = *a2;
  for ( i = HTTP2ChannelPointer::LockChannelPointer(
              (struct HTTP2ChannelPointer *const)((char *)a3 + 16 * *(int *)a2),
              (__int64)a2);
        v4 != *a2;
        i = HTTP2ChannelPointer::LockChannelPointer(
              (struct HTTP2ChannelPointer *const)((char *)a3 + 16 * *(int *)a2),
              v8) )
  {
    if ( i )
      HTTP2ChannelPointer::UnlockChannelPointer((struct HTTP2ChannelPointer *const)((char *)a3 + 16 * v4), v8);
    v4 = *a2;
  }
  *a4 = (struct HTTP2ChannelPointer *const)((char *)a3 + 16 * v4);
  return i;
}

```

## disassembly

```asm
0x18000f334  push    rbx
0x18000f336  push    rsi
0x18000f337  push    rdi
0x18000f338  push    r14
0x18000f33a  sub     rsp, 28h
0x18000f33e  movsxd  rbx, dword ptr [rdx]
0x18000f341  mov     r14, r9
0x18000f344  mov     rcx, rbx
0x18000f347  mov     rdi, r8
0x18000f34a  shl     rcx, 4
0x18000f34e  mov     rsi, rdx
0x18000f351  add     rcx, r8; this
0x18000f354  call    ?LockChannelPointer@HTTP2ChannelPointer@@QEAAPEAVHTTP2Channel@@XZ; HTTP2ChannelPointer::LockChannelPointer(void)
0x18000f359  mov     ecx, [rsi]
0x18000f35b  mov     r8, rax
0x18000f35e  cmp     ebx, ecx
0x18000f360  jz      short loc_18000F391
0x18000f362  test    r8, r8
0x18000f365  jz      short loc_18000F376
0x18000f367  movsxd  rcx, ebx
0x18000f36a  shl     rcx, 4
0x18000f36e  add     rcx, rdi; this
0x18000f371  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x18000f376  movsxd  rbx, dword ptr [rsi]
0x18000f379  mov     rcx, rbx
0x18000f37c  shl     rcx, 4
0x18000f380  add     rcx, rdi; this
0x18000f383  call    ?LockChannelPointer@HTTP2ChannelPointer@@QEAAPEAVHTTP2Channel@@XZ; HTTP2ChannelPointer::LockChannelPointer(void)
0x18000f388  mov     r8, rax
0x18000f38b  mov     eax, [rsi]
0x18000f38d  cmp     ebx, eax
0x18000f38f  jnz     short loc_18000F362
0x18000f391  movsxd  rax, ebx
0x18000f394  shl     rax, 4
0x18000f398  add     rax, rdi
0x18000f39b  mov     [r14], rax
0x18000f39e  mov     rax, r8
0x18000f3a1  add     rsp, 28h
0x18000f3a5  pop     r14
0x18000f3a7  pop     rdi
0x18000f3a8  pop     rsi
0x18000f3a9  pop     rbx
0x18000f3aa  retn
```
