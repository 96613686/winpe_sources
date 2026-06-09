# std::_Func_impl_no_alloc__lambda_f112d31c7aaf8482a6a5412eed795a39__void_::_Delete_this

- ea: `0x18000b820`
- end: `0x18000b837`
- name: `std::_Func_impl_no_alloc__lambda_f112d31c7aaf8482a6a5412eed795a39__void_::_Delete_this`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001960`
- `0x18000b820`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_f112d31c7aaf8482a6a5412eed795a39__void_::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x18000b820  sub     rsp, 28h
0x18000b824  test    dl, dl
0x18000b826  jz      short loc_18000B832
0x18000b828  mov     edx, 10h; unsigned __int64
0x18000b82d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b832  add     rsp, 28h
0x18000b836  retn
```
