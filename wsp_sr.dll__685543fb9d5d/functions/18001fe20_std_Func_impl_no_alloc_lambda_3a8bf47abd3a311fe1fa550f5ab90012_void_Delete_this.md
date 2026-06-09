# std::_Func_impl_no_alloc__lambda_3a8bf47abd3a311fe1fa550f5ab90012__void_::_Delete_this

- ea: `0x18001fe20`
- end: `0x18001fe38`
- name: `std::_Func_impl_no_alloc__lambda_3a8bf47abd3a311fe1fa550f5ab90012__void_::_Delete_this`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000573c`
- `0x18001fe20`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_3a8bf47abd3a311fe1fa550f5ab90012__void_::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    std::_Deallocate<16>(a1, 0x18u);
}

```

## disassembly

```asm
0x18001fe20  sub     rsp, 28h
0x18001fe24  test    dl, dl
0x18001fe26  jz      short loc_18001FE32
0x18001fe28  mov     edx, 18h
0x18001fe2d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001fe32  add     rsp, 28h
0x18001fe36  retn
```
