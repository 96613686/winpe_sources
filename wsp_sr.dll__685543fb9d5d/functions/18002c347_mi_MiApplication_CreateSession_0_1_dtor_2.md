# _mi::MiApplication::CreateSession_0__::_1_::dtor$2

- ea: `0x18002c347`
- end: `0x18002c365`
- name: `_mi::MiApplication::CreateSession_0__::_1_::dtor$2`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180002540`

## pseudocode

```c
void __fastcall mi::MiApplication::CreateSession_0__::_1_::dtor_2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 40));
}

```

## disassembly

```asm
0x18002c347  push    rbp
0x18002c349  sub     rsp, 20h
0x18002c34d  mov     rbp, rdx
0x18002c350  mov     edx, 138h; unsigned __int64
0x18002c355  mov     rcx, [rbp+28h]; void *
0x18002c359  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002c35e  add     rsp, 20h
0x18002c362  pop     rbp
0x18002c363  retn
```
