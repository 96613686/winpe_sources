# HTTP2VirtualConnection::StartChannelRecyclingIfNecessary(long,int)

- ea: `0x1800199cc`
- end: `0x1800199f3`
- name: `?StartChannelRecyclingIfNecessary@HTTP2VirtualConnection@@QEAAJJH@Z`
- size: `39`
- prototype: `__int64 __fastcall(HTTP2VirtualConnection *__hidden this, int, int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dfe8`
- `0x180012110`
- `0x1800158e0`
- `0x180017db0`
- `0x18001a840`

## callees

- `0x1800199cc`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2VirtualConnection::StartChannelRecyclingIfNecessary(
        HTTP2VirtualConnection *this,
        unsigned int a2,
        unsigned int a3)
{
  if ( a2 == -1073606614 )
    return (*(unsigned int (__fastcall **)(HTTP2VirtualConnection *, _QWORD))(*(_QWORD *)this + 128LL))(this, a3);
  return a2;
}

```

## disassembly

```asm
0x1800199cc  sub     rsp, 28h
0x1800199d0  cmp     edx, 0C002102Ah
0x1800199d6  jnz     short loc_1800199EC
0x1800199d8  mov     rax, [rcx]
0x1800199db  mov     edx, r8d
0x1800199de  mov     rax, [rax+80h]
0x1800199e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199ea  mov     edx, eax
0x1800199ec  mov     eax, edx
0x1800199ee  add     rsp, 28h
0x1800199f2  retn
```
