# _alloca_probe

- ea: `0x18000c920`
- end: `0x18000c96d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000892c`
- `0x180008bb0`
- `0x180008e60`
- `0x18000c610`

## callees

- `0x18000c920`

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
0x18000c920  sub     rsp, 10h
0x18000c924  mov     [rsp+10h+var_10], r10
0x18000c928  mov     [rsp+10h+var_8], r11
0x18000c92d  xor     r11, r11
0x18000c930  lea     r10, [rsp+10h+arg_0]
0x18000c935  sub     r10, rax
0x18000c938  cmovb   r10, r11
0x18000c93c  mov     r11, gs:10h
0x18000c945  cmp     r10, r11
0x18000c948  jnb     short loc_18000C95F
0x18000c94a  and     r10w, 0F000h
0x18000c950  lea     r11, [r11-1000h]
0x18000c957  test    [r11], r11b
0x18000c95a  cmp     r10, r11
0x18000c95d  jb      short loc_18000C950
0x18000c95f  mov     r10, [rsp+10h+var_10]
0x18000c963  mov     r11, [rsp+10h+var_8]
0x18000c968  add     rsp, 10h
0x18000c96c  retn
```
