# GetWICFactory(void)

- ea: `0x18002aec8`
- end: `0x18002aeeb`
- name: `?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ`
- size: `35`
- prototype: `struct IWICComponentFactory *(void)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028fb0`
- `0x1800297c0`
- `0x18002ac90`
- `0x18002adc0`
- `0x18002be10`
- `0x1800314f0`
- `0x1800321c0`
- `0x1800322d0`
- `0x180035010`
- `0x1800354b0`
- `0x180038270`
- `0x180039170`
- `0x180039770`
- `0x18003a470`
- `0x18003a8c0`
- `0x18003aa30`
- `0x18003ac50`

## callees

- `0x18002aec8`
- `0x18002f018`

## pseudocode

```c
struct IWICComponentFactory *GetWICFactory(void)
{
  struct IWICComponentFactory *result; // rax

  result = (struct IWICComponentFactory *)qword_1800503B0;
  if ( !qword_1800503B0 )
  {
    InitWICFactory();
    return (struct IWICComponentFactory *)qword_1800503B0;
  }
  return result;
}

```

## disassembly

```asm
0x18002aec8  sub     rsp, 28h
0x18002aecc  mov     rax, cs:qword_1800503B0
0x18002aed3  test    rax, rax
0x18002aed6  jz      short loc_18002AEDD
0x18002aed8  add     rsp, 28h
0x18002aedc  retn
0x18002aedd  call    ?InitWICFactory@@YAJXZ; InitWICFactory(void)
0x18002aee2  mov     rax, cs:qword_1800503B0
0x18002aee9  jmp     short loc_18002AED8
```
