# LambdaWrapper__lambda_3f888ffeeb51c4c77808cd545df17201_

- ea: `0x180007900`
- end: `0x18000792e`
- name: `LambdaWrapper__lambda_3f888ffeeb51c4c77808cd545df17201___`
- size: `46`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002190`
- `0x180007900`
- `0x1800079cc`

## pseudocode

```c
__int64 __fastcall LambdaWrapper__lambda_3f888ffeeb51c4c77808cd545df17201_(LPVOID lpThreadParameter)
{
  lambda_3f888ffeeb51c4c77808cd545df17201_::operator()();
  if ( lpThreadParameter )
    operator delete(lpThreadParameter, (const struct std::nothrow_t *)0x28);
  return 0;
}

```

## disassembly

```asm
0x180007900  push    rbx
0x180007902  sub     rsp, 20h
0x180007906  mov     rbx, rcx
0x180007909  mov     [rsp+28h+arg_0], rcx
0x18000790e  call    _lambda_3f888ffeeb51c4c77808cd545df17201___operator__
0x180007913  nop
0x180007914  test    rbx, rbx
0x180007917  jz      short loc_180007926
0x180007919  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18000791e  mov     rcx, rbx; void *
0x180007921  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007926  xor     eax, eax
0x180007928  add     rsp, 20h
0x18000792c  pop     rbx
0x18000792d  retn
```
