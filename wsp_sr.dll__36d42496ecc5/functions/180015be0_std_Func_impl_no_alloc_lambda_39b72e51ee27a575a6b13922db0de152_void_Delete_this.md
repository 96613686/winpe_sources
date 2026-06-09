# std::_Func_impl_no_alloc__lambda_39b72e51ee27a575a6b13922db0de152__void_::_Delete_this

- ea: `0x180015be0`
- end: `0x180015bf7`
- name: `std::_Func_impl_no_alloc__lambda_39b72e51ee27a575a6b13922db0de152__void_::_Delete_this`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000570c`
- `0x180015be0`

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
0x180015be0  sub     rsp, 28h
0x180015be4  test    dl, dl
0x180015be6  jz      short loc_180015BF2
0x180015be8  mov     edx, 28h ; '('
0x180015bed  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015bf2  add     rsp, 28h
0x180015bf6  retn
```
