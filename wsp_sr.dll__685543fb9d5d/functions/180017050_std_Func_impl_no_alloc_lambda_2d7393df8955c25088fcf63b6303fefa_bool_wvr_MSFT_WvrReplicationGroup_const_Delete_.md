# std::_Func_impl_no_alloc__lambda_2d7393df8955c25088fcf63b6303fefa__bool_wvr::MSFT_WvrReplicationGroup_const_&_::_Delete_this

- ea: `0x180017050`
- end: `0x180017085`
- name: `std::_Func_impl_no_alloc__lambda_2d7393df8955c25088fcf63b6303fefa__bool_wvr::MSFT_WvrReplicationGroup_const_&_::_Delete_this`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000573c`
- `0x180015c0c`
- `0x180017050`

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
0x180017050  mov     [rsp+arg_0], rbx
0x180017055  push    rdi
0x180017056  sub     rsp, 20h
0x18001705a  mov     rdi, rcx
0x18001705d  mov     bl, dl
0x18001705f  add     rcx, 8
0x180017063  call    _lambda_2d7393df8955c25088fcf63b6303fefa_____lambda_2d7393df8955c25088fcf63b6303fefa_
0x180017068  test    bl, bl
0x18001706a  jz      short loc_180017079
0x18001706c  mov     edx, 68h ; 'h'
0x180017071  mov     rcx, rdi
0x180017074  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017079  mov     rbx, [rsp+28h+arg_0]
0x18001707e  add     rsp, 20h
0x180017082  pop     rdi
0x180017083  retn
```
