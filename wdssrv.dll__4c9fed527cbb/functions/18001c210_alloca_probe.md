# _alloca_probe

- ea: `0x18001c210`
- end: `0x18001c25d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800068d0`
- `0x180006b48`
- `0x180006df8`
- `0x18000c004`
- `0x18000eee8`

## callees

- `0x18001c210`

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
0x18001c210  sub     rsp, 10h
0x18001c214  mov     [rsp+10h+var_10], r10
0x18001c218  mov     [rsp+10h+var_8], r11
0x18001c21d  xor     r11, r11
0x18001c220  lea     r10, [rsp+10h+arg_0]
0x18001c225  sub     r10, rax
0x18001c228  cmovb   r10, r11
0x18001c22c  mov     r11, gs:10h
0x18001c235  cmp     r10, r11
0x18001c238  jnb     short loc_18001C24F
0x18001c23a  and     r10w, 0F000h
0x18001c240  lea     r11, [r11-1000h]
0x18001c247  test    [r11], r11b
0x18001c24a  cmp     r10, r11
0x18001c24d  jb      short loc_18001C240
0x18001c24f  mov     r10, [rsp+10h+var_10]
0x18001c253  mov     r11, [rsp+10h+var_8]
0x18001c258  add     rsp, 10h
0x18001c25c  retn
```
