# _alloca_probe

- ea: `0x180016d10`
- end: `0x180016d5d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800059b0`
- `0x18000b334`
- `0x1800113fc`
- `0x180014dc4`
- `0x180014e78`
- `0x180015114`

## callees

- `0x180016d10`

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
0x180016d10  sub     rsp, 10h
0x180016d14  mov     [rsp+10h+var_10], r10
0x180016d18  mov     [rsp+10h+var_8], r11
0x180016d1d  xor     r11, r11
0x180016d20  lea     r10, [rsp+10h+arg_0]
0x180016d25  sub     r10, rax
0x180016d28  cmovb   r10, r11
0x180016d2c  mov     r11, gs:10h
0x180016d35  cmp     r10, r11
0x180016d38  jnb     short loc_180016D4F
0x180016d3a  and     r10w, 0F000h
0x180016d40  lea     r11, [r11-1000h]
0x180016d47  test    [r11], r11b
0x180016d4a  cmp     r10, r11
0x180016d4d  jb      short loc_180016D40
0x180016d4f  mov     r10, [rsp+10h+var_10]
0x180016d53  mov     r11, [rsp+10h+var_8]
0x180016d58  add     rsp, 10h
0x180016d5c  retn
```
