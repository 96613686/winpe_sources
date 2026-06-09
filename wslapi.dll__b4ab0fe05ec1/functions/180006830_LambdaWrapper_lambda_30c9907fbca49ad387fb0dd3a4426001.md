# LambdaWrapper__lambda_30c9907fbca49ad387fb0dd3a4426001_

- ea: `0x180006830`
- end: `0x18000685e`
- name: `LambdaWrapper__lambda_30c9907fbca49ad387fb0dd3a4426001___`
- size: `46`
- prototype: `__int64 __fastcall(int **lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002190`
- `0x180006830`
- `0x1800069e4`

## pseudocode

```c
__int64 __fastcall LambdaWrapper__lambda_30c9907fbca49ad387fb0dd3a4426001_(int **lpThreadParameter)
{
  lambda_30c9907fbca49ad387fb0dd3a4426001_::operator()(lpThreadParameter);
  if ( lpThreadParameter )
    operator delete(lpThreadParameter, (const struct std::nothrow_t *)0x20);
  return 0;
}

```

## disassembly

```asm
0x180006830  push    rbx
0x180006832  sub     rsp, 20h
0x180006836  mov     rbx, rcx
0x180006839  mov     [rsp+28h+arg_0], rcx
0x18000683e  call    _lambda_30c9907fbca49ad387fb0dd3a4426001___operator__
0x180006843  nop
0x180006844  test    rbx, rbx
0x180006847  jz      short loc_180006856
0x180006849  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18000684e  mov     rcx, rbx; void *
0x180006851  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006856  xor     eax, eax
0x180006858  add     rsp, 20h
0x18000685c  pop     rbx
0x18000685d  retn
```
