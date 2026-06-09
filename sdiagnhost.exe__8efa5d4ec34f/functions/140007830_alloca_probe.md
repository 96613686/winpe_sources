# _alloca_probe

- ea: `0x140007830`
- end: `0x14000787d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400030e8`
- `0x140003368`
- `0x140003610`
- `0x1400074e0`

## callees

- `0x140007830`

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
0x140007830  sub     rsp, 10h
0x140007834  mov     [rsp+10h+var_10], r10
0x140007838  mov     [rsp+10h+var_8], r11
0x14000783d  xor     r11, r11
0x140007840  lea     r10, [rsp+10h+arg_0]
0x140007845  sub     r10, rax
0x140007848  cmovb   r10, r11
0x14000784c  mov     r11, gs:10h
0x140007855  cmp     r10, r11
0x140007858  jnb     short loc_14000786F
0x14000785a  and     r10w, 0F000h
0x140007860  lea     r11, [r11-1000h]
0x140007867  test    [r11], r11b
0x14000786a  cmp     r10, r11
0x14000786d  jb      short loc_140007860
0x14000786f  mov     r10, [rsp+10h+var_10]
0x140007873  mov     r11, [rsp+10h+var_8]
0x140007878  add     rsp, 10h
0x14000787c  retn
```
