# std::_Func_impl_std::_Callable_obj__lambda_312e65f4f93bbe839a71a78ad9276a5e__0__std::allocator_std::_Func_class_void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this

- ea: `0x18000c6c0`
- end: `0x18000c6f5`
- name: `std::_Func_impl_std::_Callable_obj__lambda_312e65f4f93bbe839a71a78ad9276a5e__0__std::allocator_std::_Func_class_void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000c6c0`
- `0x180010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c6e4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c6e4`

## pseudocode

```c
void __fastcall std::_Func_impl_std::_Callable_obj__lambda_312e65f4f93bbe839a71a78ad9276a5e__0__std::allocator_std::_Func_class_void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil____void_unsigned_long_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_std::_Nil_::_Delete_this(
        void *a1,
        char a2)
{
  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0);
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x18000c6c0  mov     [rsp+arg_0], rbx
0x18000c6c5  push    rdi
0x18000c6c6  sub     rsp, 20h
0x18000c6ca  mov     rax, [rcx]
0x18000c6cd  mov     bl, dl
0x18000c6cf  xor     edx, edx
0x18000c6d1  mov     rdi, rcx
0x18000c6d4  mov     rax, [rax+28h]
0x18000c6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6dd  test    bl, bl
0x18000c6df  jz      short loc_18000C6EA
0x18000c6e1  mov     rcx, rdi
0x18000c6e4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c6ea  mov     rbx, [rsp+28h+arg_0]
0x18000c6ef  add     rsp, 20h
0x18000c6f3  pop     rdi
0x18000c6f4  retn
```
