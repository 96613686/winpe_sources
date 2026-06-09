# std::_Func_impl_no_alloc__lambda_39b72e51ee27a575a6b13922db0de152__void_::_Delete_this

- ea: `0x180015a90`
- end: `0x180015aa8`
- name: `std::_Func_impl_no_alloc__lambda_39b72e51ee27a575a6b13922db0de152__void_::_Delete_this`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000573c`
- `0x180015a90`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_39b72e51ee27a575a6b13922db0de152__void_::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    std::_Deallocate<16>(a1, 0x28u);
}

```

## disassembly

```asm
0x180015a90  sub     rsp, 28h
0x180015a94  test    dl, dl
0x180015a96  jz      short loc_180015AA2
0x180015a98  mov     edx, 28h ; '('
0x180015a9d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015aa2  add     rsp, 28h
0x180015aa6  retn
```
