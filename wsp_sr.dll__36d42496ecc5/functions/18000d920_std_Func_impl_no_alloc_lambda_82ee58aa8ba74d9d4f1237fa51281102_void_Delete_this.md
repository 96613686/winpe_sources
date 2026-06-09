# std::_Func_impl_no_alloc__lambda_82ee58aa8ba74d9d4f1237fa51281102__void_::_Delete_this

- ea: `0x18000d920`
- end: `0x18000d937`
- name: `std::_Func_impl_no_alloc__lambda_82ee58aa8ba74d9d4f1237fa51281102__void_::_Delete_this`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000570c`
- `0x18000d920`

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
0x18000d920  sub     rsp, 28h
0x18000d924  test    dl, dl
0x18000d926  jz      short loc_18000D932
0x18000d928  mov     edx, 20h ; ' '
0x18000d92d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d932  add     rsp, 28h
0x18000d936  retn
```
