# HTTP2VirtualConnection::AbortChannels(long)

- ea: `0x180004058`
- end: `0x18000412a`
- name: `?AbortChannels@HTTP2VirtualConnection@@QEAAXJ@Z`
- size: `210`
- prototype: `void __fastcall(HTTP2VirtualConnection *__hidden this, int)`
- caller_count: `14`
- callee_count: `4`
- tags: ``

## callers

- `0x180003ce0`
- `0x180003d50`
- `0x180003f94`
- `0x180003ffc`
- `0x180004130`
- `0x1800041d0`
- `0x18000dfe8`
- `0x180013920`
- `0x180014850`
- `0x1800158e0`
- `0x180018930`
- `0x18001a170`
- `0x18001a540`
- `0x18001b22c`

## callees

- `0x180004058`
- `0x18000f2bc`
- `0x18001ac1c`
- `0x180025010`

## pseudocode

```c
void __fastcall HTTP2VirtualConnection::AbortChannels(HTTP2VirtualConnection *this, __int64 a2)
{
  unsigned int v2; // esi
  __int64 v4; // rdi
  char *v5; // rcx
  __int64 v6; // rdi
  struct HTTP2Channel *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 i; // rbx
  struct HTTP2Channel *v11; // rax
  __int64 v12; // rdx
  signed __int32 v13[8]; // [rsp+0h] [rbp-48h] BYREF
  HTTP2ChannelPointer *v14[5]; // [rsp+20h] [rbp-28h]

  v2 = a2;
  _InterlockedOr(v13, 0);
  if ( *((int *)this + 13) <= 0 )
  {
    v4 = *((int *)this + 68);
    v14[0] = (HTTP2VirtualConnection *)((char *)this + 120);
    v14[1] = (HTTP2VirtualConnection *)((char *)this + 136);
    v14[2] = (HTTP2VirtualConnection *)((char *)this + 200);
    v5 = (char *)this + 200;
    v6 = 16 * v4;
    v14[3] = (HTTP2ChannelPointer *)(v5 + 16);
    v7 = HTTP2ChannelPointer::LockChannelPointer((HTTP2ChannelPointer *)&v5[v6], a2);
    if ( v7 )
    {
      (*(void (__fastcall **)(struct HTTP2Channel *, char *, char *))(*(_QWORD *)v7 + 72LL))(
        v7,
        (char *)this + 40,
        (char *)this + 48);
      HTTP2ChannelPointer::UnlockChannelPointer((HTTP2VirtualConnection *)((char *)this + v6 + 200), v9);
    }
    for ( i = 0; i != 4; ++i )
    {
      v11 = HTTP2ChannelPointer::LockChannelPointer(v14[i], v8);
      if ( v11 )
      {
        (*(void (__fastcall **)(struct HTTP2Channel *, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, v2);
        HTTP2ChannelPointer::UnlockChannelPointer(v14[i], v12);
      }
    }
  }
}

```

## disassembly

```asm
0x180004058  mov     r11, rsp
0x18000405b  mov     [r11+8], rbx
0x18000405f  mov     [r11+10h], rsi
0x180004063  push    rdi
0x180004064  sub     rsp, 40h
0x180004068  mov     esi, edx
0x18000406a  mov     rbx, rcx
0x18000406d  lock or [rsp+48h+var_48], 0
0x180004072  mov     eax, [rcx+34h]
0x180004075  test    eax, eax
0x180004077  jg      loc_18000411A
0x18000407d  movsxd  rdi, dword ptr [rcx+110h]
0x180004084  lea     rax, [rcx+78h]
0x180004088  mov     [r11-28h], rax
0x18000408c  add     rax, 10h
0x180004090  mov     [r11-20h], rax
0x180004094  lea     rax, [rcx+0C8h]
0x18000409b  mov     [r11-18h], rax
0x18000409f  add     rcx, 0C8h
0x1800040a6  add     rax, 10h
0x1800040aa  shl     rdi, 4
0x1800040ae  add     rcx, rdi; this
0x1800040b1  mov     [r11-10h], rax
0x1800040b5  call    ?LockChannelPointer@HTTP2ChannelPointer@@QEAAPEAVHTTP2Channel@@XZ; HTTP2ChannelPointer::LockChannelPointer(void)
0x1800040ba  test    rax, rax
0x1800040bd  jz      short loc_1800040E5
0x1800040bf  mov     r9, [rax]
0x1800040c2  lea     r8, [rbx+30h]
0x1800040c6  mov     rcx, rax
0x1800040c9  lea     rdx, [rbx+28h]
0x1800040cd  mov     rax, [r9+48h]
0x1800040d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040d6  lea     rcx, [rbx+0C8h]
0x1800040dd  add     rcx, rdi; this
0x1800040e0  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x1800040e5  xor     ebx, ebx
0x1800040e7  mov     rcx, [rsp+rbx*8+48h+var_28]; this
0x1800040ec  call    ?LockChannelPointer@HTTP2ChannelPointer@@QEAAPEAVHTTP2Channel@@XZ; HTTP2ChannelPointer::LockChannelPointer(void)
0x1800040f1  mov     rcx, rax
0x1800040f4  test    rax, rax
0x1800040f7  jz      short loc_180004111
0x1800040f9  mov     rdx, [rax]
0x1800040fc  mov     rax, [rdx+28h]
0x180004100  mov     edx, esi
0x180004102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004107  mov     rcx, [rsp+rbx*8+48h+var_28]; this
0x18000410c  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x180004111  inc     rbx
0x180004114  cmp     rbx, 4
0x180004118  jnz     short loc_1800040E7
0x18000411a  mov     rbx, [rsp+48h+arg_0]
0x18000411f  mov     rsi, [rsp+48h+arg_8]
0x180004124  add     rsp, 40h
0x180004128  pop     rdi
0x180004129  retn
```
