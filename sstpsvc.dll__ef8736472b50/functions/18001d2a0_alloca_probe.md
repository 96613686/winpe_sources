# _alloca_probe

- ea: `0x18001d2a0`
- end: `0x18001d2ed`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fe0`
- `0x180002320`
- `0x180003620`
- `0x180004950`
- `0x18000afb0`
- `0x180017be4`
- `0x180017e5c`
- `0x18001810c`
- `0x18001b450`
- `0x18001cb7c`

## callees

- `0x18001d2a0`

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
0x18001d2a0  sub     rsp, 10h
0x18001d2a4  mov     [rsp+10h+var_10], r10
0x18001d2a8  mov     [rsp+10h+var_8], r11
0x18001d2ad  xor     r11, r11
0x18001d2b0  lea     r10, [rsp+10h+arg_0]
0x18001d2b5  sub     r10, rax
0x18001d2b8  cmovb   r10, r11
0x18001d2bc  mov     r11, gs:10h
0x18001d2c5  cmp     r10, r11
0x18001d2c8  jnb     short loc_18001D2DF
0x18001d2ca  and     r10w, 0F000h
0x18001d2d0  lea     r11, [r11-1000h]
0x18001d2d7  test    [r11], r11b
0x18001d2da  cmp     r10, r11
0x18001d2dd  jb      short loc_18001D2D0
0x18001d2df  mov     r10, [rsp+10h+var_10]
0x18001d2e3  mov     r11, [rsp+10h+var_8]
0x18001d2e8  add     rsp, 10h
0x18001d2ec  retn
```
