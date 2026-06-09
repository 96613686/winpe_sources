# _alloca_probe

- ea: `0x180029980`
- end: `0x1800299cd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180008750`
- `0x1800089b8`
- `0x180008c54`
- `0x18000f534`
- `0x180012d80`
- `0x180012e90`

## callees

- `0x180029980`

## pseudocode

```c
unsigned __int64 __fastcall alloca_probe()
{
  unsigned __int64 result; // rax
  char *v1; // r10
  char *StackLimit; // r11
  char v3; // [rsp+18h] [rbp+8h] BYREF

  v1 = &v3 - result;
  if ( (unsigned __int64)&v3 < result )
    v1 = 0;
  StackLimit = (char *)NtCurrentTeb()->NtTib.StackLimit;
  if ( v1 < StackLimit )
  {
    LOWORD(v1) = (unsigned __int16)v1 & 0xF000;
    do
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x180029980  sub     rsp, 10h
0x180029984  mov     [rsp+10h+var_10], r10
0x180029988  mov     [rsp+10h+var_8], r11
0x18002998d  xor     r11, r11
0x180029990  lea     r10, [rsp+10h+arg_0]
0x180029995  sub     r10, rax
0x180029998  cmovb   r10, r11
0x18002999c  mov     r11, gs:10h
0x1800299a5  cmp     r10, r11
0x1800299a8  jnb     short loc_1800299BF
0x1800299aa  and     r10w, 0F000h
0x1800299b0  lea     r11, [r11-1000h]
0x1800299b7  test    [r11], r11b
0x1800299ba  cmp     r10, r11
0x1800299bd  jb      short loc_1800299B0
0x1800299bf  mov     r10, [rsp+10h+var_10]
0x1800299c3  mov     r11, [rsp+10h+var_8]
0x1800299c8  add     rsp, 10h
0x1800299cc  retn
```
