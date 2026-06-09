# _mi::MiApplication::CreateSession_0__::_1_::dtor$2

- ea: `0x18002be52`
- end: `0x18002be6f`
- name: `_mi::MiApplication::CreateSession_0__::_1_::dtor$2`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180002510`

## pseudocode

```c
void __fastcall mi::MiApplication::CreateSession_0__::_1_::dtor_2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x18002be52  push    rbp
0x18002be54  sub     rsp, 20h
0x18002be58  mov     rbp, rdx
0x18002be5b  mov     edx, 138h; unsigned __int64
0x18002be60  mov     rcx, [rbp+28h]; void *
0x18002be64  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002be69  add     rsp, 20h
0x18002be6d  pop     rbp
0x18002be6e  retn
```
