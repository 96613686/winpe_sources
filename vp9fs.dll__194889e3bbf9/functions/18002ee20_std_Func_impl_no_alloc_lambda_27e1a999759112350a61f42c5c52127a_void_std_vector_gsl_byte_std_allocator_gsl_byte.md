# std::_Func_impl_no_alloc<_lambda_27e1a999759112350a61f42c5c52127a_,void,std::vector<gsl::byte,std::allocator<gsl::byte>> const &>::_Do_call(std::vector<gsl::byte,std::allocator<gsl::byte>> const &)

- ea: `0x18002ee20`
- end: `0x18002ee7b`
- name: `?_Do_call@?$_Func_impl_no_alloc@V_lambda_27e1a999759112350a61f42c5c52127a_@@XAEBV?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@@std@@EEAAXAEBV?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@2@@Z`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002ee20`

## import_xrefs

- `vmvirtio!VirtioMemoryStreamWrite` at `0x18002ee45`
- `vmvirtio!VirtioMemoryStreamWrite` at `0x18002ee45`
- `vmvirtio!VirtioCompleteWorkCallbackAsync` at `0x18002ee74`

## pseudocode

```c
__int64 __fastcall std::_Func_impl_no_alloc<_lambda_27e1a999759112350a61f42c5c52127a_,void,std::vector<enum gsl::byte> const &>::_Do_call(
        __int64 a1,
        _QWORD *a2)
{
  if ( a2[1] != *a2 )
    VirtioMemoryStreamWrite(*(_QWORD *)(a1 + 24), *a2);
  return VirtioCompleteWorkCallbackAsync(
           *(_QWORD *)(*(_QWORD *)(a1 + 8) + 136LL),
           *(unsigned __int16 *)(a1 + 16),
           a1 + 24,
           (unsigned int)(*((_DWORD *)a2 + 2) - *(_DWORD *)a2));
}

```

## disassembly

```asm
0x18002ee20  mov     [rsp+arg_0], rbx
0x18002ee25  mov     [rsp+arg_8], rsi
0x18002ee2a  push    rdi
0x18002ee2b  sub     rsp, 20h
0x18002ee2f  mov     r8, [rdx+8]
0x18002ee33  mov     rbx, rdx
0x18002ee36  mov     rdi, rcx
0x18002ee39  sub     r8, [rdx]
0x18002ee3c  jz      short loc_18002EE4B
0x18002ee3e  mov     rdx, [rdx]
0x18002ee41  mov     rcx, [rcx+18h]
0x18002ee45  call    cs:__imp_VirtioMemoryStreamWrite
0x18002ee4b  mov     rcx, [rdi+8]
0x18002ee4f  lea     r8, [rdi+18h]
0x18002ee53  mov     r9d, [rbx+8]
0x18002ee57  sub     r9d, [rbx]
0x18002ee5a  movzx   edx, word ptr [rdi+10h]
0x18002ee5e  mov     rcx, [rcx+88h]
0x18002ee65  mov     rbx, [rsp+28h+arg_0]
0x18002ee6a  mov     rsi, [rsp+28h+arg_8]
0x18002ee6f  add     rsp, 20h
0x18002ee73  pop     rdi
0x18002ee74  jmp     cs:__imp_VirtioCompleteWorkCallbackAsync
```
