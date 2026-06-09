# _alloca_probe

- ea: `0x18001bd80`
- end: `0x18001bdcd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ee0`
- `0x1800021f0`
- `0x1800033b0`
- `0x1800045b0`
- `0x18000a620`
- `0x18001699c`
- `0x180016c04`
- `0x180016ea0`
- `0x180019f4c`
- `0x18001b6a4`

## callees

- `0x18001bd80`

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
0x18001bd80  sub     rsp, 10h
0x18001bd84  mov     [rsp+10h+var_10], r10
0x18001bd88  mov     [rsp+10h+var_8], r11
0x18001bd8d  xor     r11, r11
0x18001bd90  lea     r10, [rsp+10h+arg_0]
0x18001bd95  sub     r10, rax
0x18001bd98  cmovb   r10, r11
0x18001bd9c  mov     r11, gs:10h
0x18001bda5  cmp     r10, r11
0x18001bda8  jnb     short loc_18001BDBF
0x18001bdaa  and     r10w, 0F000h
0x18001bdb0  lea     r11, [r11-1000h]
0x18001bdb7  test    [r11], r11b
0x18001bdba  cmp     r10, r11
0x18001bdbd  jb      short loc_18001BDB0
0x18001bdbf  mov     r10, [rsp+10h+var_10]
0x18001bdc3  mov     r11, [rsp+10h+var_8]
0x18001bdc8  add     rsp, 10h
0x18001bdcc  retn
```
