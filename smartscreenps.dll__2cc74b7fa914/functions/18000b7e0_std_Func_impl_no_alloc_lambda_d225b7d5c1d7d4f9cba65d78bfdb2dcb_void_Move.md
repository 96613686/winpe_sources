# std::_Func_impl_no_alloc__lambda_d225b7d5c1d7d4f9cba65d78bfdb2dcb__void_::_Move

- ea: `0x18000b7e0`
- end: `0x18000b7ee`
- name: `std::_Func_impl_no_alloc__lambda_d225b7d5c1d7d4f9cba65d78bfdb2dcb__void_::_Move`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc__lambda_d225b7d5c1d7d4f9cba65d78bfdb2dcb__void_::_Move(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = off_18000F130;
  return a2;
}

```

## disassembly

```asm
0x18000b7e0  lea     rax, off_18000F130
0x18000b7e7  mov     [rdx], rax
0x18000b7ea  mov     rax, rdx
0x18000b7ed  retn
```
