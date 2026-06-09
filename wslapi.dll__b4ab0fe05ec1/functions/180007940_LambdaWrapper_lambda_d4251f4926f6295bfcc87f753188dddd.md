# LambdaWrapper__lambda_d4251f4926f6295bfcc87f753188dddd_

- ea: `0x180007940`
- end: `0x18000796e`
- name: `LambdaWrapper__lambda_d4251f4926f6295bfcc87f753188dddd___`
- size: `46`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002190`
- `0x180007940`
- `0x180007a80`

## pseudocode

```c
__int64 __fastcall LambdaWrapper__lambda_d4251f4926f6295bfcc87f753188dddd_(LPVOID lpThreadParameter)
{
  lambda_d4251f4926f6295bfcc87f753188dddd_::operator()();
  if ( lpThreadParameter )
    operator delete(lpThreadParameter, (const struct std::nothrow_t *)0x40);
  return 0;
}

```

## disassembly

```asm
0x180007940  push    rbx
0x180007942  sub     rsp, 20h
0x180007946  mov     rbx, rcx
0x180007949  mov     [rsp+28h+arg_0], rcx
0x18000794e  call    _lambda_d4251f4926f6295bfcc87f753188dddd___operator__
0x180007953  nop
0x180007954  test    rbx, rbx
0x180007957  jz      short loc_180007966
0x180007959  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18000795e  mov     rcx, rbx; void *
0x180007961  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007966  xor     eax, eax
0x180007968  add     rsp, 20h
0x18000796c  pop     rbx
0x18000796d  retn
```
