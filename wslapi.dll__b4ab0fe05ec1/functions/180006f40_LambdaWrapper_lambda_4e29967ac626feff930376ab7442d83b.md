# LambdaWrapper__lambda_4e29967ac626feff930376ab7442d83b_

- ea: `0x180006f40`
- end: `0x180006f6e`
- name: `LambdaWrapper__lambda_4e29967ac626feff930376ab7442d83b___`
- size: `46`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002190`
- `0x180006f40`
- `0x18000710c`

## pseudocode

```c
__int64 __fastcall LambdaWrapper__lambda_4e29967ac626feff930376ab7442d83b_(LPVOID lpThreadParameter)
{
  lambda_4e29967ac626feff930376ab7442d83b_::operator()();
  if ( lpThreadParameter )
    operator delete(lpThreadParameter, (const struct std::nothrow_t *)0x18);
  return 0;
}

```

## disassembly

```asm
0x180006f40  push    rbx
0x180006f42  sub     rsp, 20h
0x180006f46  mov     rbx, rcx
0x180006f49  mov     [rsp+28h+arg_0], rcx
0x180006f4e  call    _lambda_4e29967ac626feff930376ab7442d83b___operator__
0x180006f53  nop
0x180006f54  test    rbx, rbx
0x180006f57  jz      short loc_180006F66
0x180006f59  mov     edx, 18h; struct std::nothrow_t *
0x180006f5e  mov     rcx, rbx; void *
0x180006f61  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006f66  xor     eax, eax
0x180006f68  add     rsp, 20h
0x180006f6c  pop     rbx
0x180006f6d  retn
```
