# std::_Func_impl_no_alloc__lambda_82ee58aa8ba74d9d4f1237fa51281102__void_::_Delete_this

- ea: `0x18000d7b0`
- end: `0x18000d7c8`
- name: `std::_Func_impl_no_alloc__lambda_82ee58aa8ba74d9d4f1237fa51281102__void_::_Delete_this`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000573c`
- `0x18000d7b0`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_82ee58aa8ba74d9d4f1237fa51281102__void_::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    std::_Deallocate<16>(a1, 0x20u);
}

```

## disassembly

```asm
0x18000d7b0  sub     rsp, 28h
0x18000d7b4  test    dl, dl
0x18000d7b6  jz      short loc_18000D7C2
0x18000d7b8  mov     edx, 20h ; ' '
0x18000d7bd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d7c2  add     rsp, 28h
0x18000d7c6  retn
```
