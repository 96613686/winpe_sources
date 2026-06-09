# std::_Func_impl_no_alloc__lambda_2d7393df8955c25088fcf63b6303fefa__bool_wvr::MSFT_WvrReplicationGroup_const_&_::_Delete_this

- ea: `0x180017190`
- end: `0x1800171c4`
- name: `std::_Func_impl_no_alloc__lambda_2d7393df8955c25088fcf63b6303fefa__bool_wvr::MSFT_WvrReplicationGroup_const_&_::_Delete_this`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000570c`
- `0x180015d58`
- `0x180017190`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_2d7393df8955c25088fcf63b6303fefa__bool_wvr::MSFT_WvrReplicationGroup_const___::_Delete_this(
        char *a1,
        char a2)
{
  lambda_2d7393df8955c25088fcf63b6303fefa_::__lambda_2d7393df8955c25088fcf63b6303fefa_(a1 + 8);
  if ( a2 )
    std::_Deallocate<16>(a1, 0x68u);
}

```

## disassembly

```asm
0x180017190  mov     [rsp+arg_0], rbx
0x180017195  push    rdi
0x180017196  sub     rsp, 20h
0x18001719a  mov     rdi, rcx
0x18001719d  mov     bl, dl
0x18001719f  add     rcx, 8
0x1800171a3  call    _lambda_2d7393df8955c25088fcf63b6303fefa_____lambda_2d7393df8955c25088fcf63b6303fefa_
0x1800171a8  test    bl, bl
0x1800171aa  jz      short loc_1800171B9
0x1800171ac  mov     edx, 68h ; 'h'
0x1800171b1  mov     rcx, rdi
0x1800171b4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800171b9  mov     rbx, [rsp+28h+arg_0]
0x1800171be  add     rsp, 20h
0x1800171c2  pop     rdi
0x1800171c3  retn
```
