# _WslSession::s_Create_::_1_::dtor$1

- ea: `0x18000c14f`
- end: `0x18000c16e`
- name: `_WslSession::s_Create_::_1_::dtor$1`
- size: `31`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180002190`

## pseudocode

```c
void __fastcall WslSession::s_Create_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32), (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x18000c14f  push    rbp
0x18000c151  sub     rsp, 20h
0x18000c155  mov     rbp, rdx
0x18000c158  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c15f  mov     rcx, [rbp+20h]; void *
0x18000c163  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c168  add     rsp, 20h
0x18000c16c  pop     rbp
0x18000c16d  retn
```
