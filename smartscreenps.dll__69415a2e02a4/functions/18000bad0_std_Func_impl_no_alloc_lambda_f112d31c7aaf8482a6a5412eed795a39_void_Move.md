# std::_Func_impl_no_alloc__lambda_f112d31c7aaf8482a6a5412eed795a39__void_::_Move

- ea: `0x18000bad0`
- end: `0x18000bade`
- name: `std::_Func_impl_no_alloc__lambda_f112d31c7aaf8482a6a5412eed795a39__void_::_Move`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc__lambda_f112d31c7aaf8482a6a5412eed795a39__void_::_Move(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = off_18000F160;
  return a2;
}

```

## disassembly

```asm
0x18000bad0  lea     rax, off_18000F160
0x18000bad7  mov     [rdx], rax
0x18000bada  mov     rax, rdx
0x18000badd  retn
```
