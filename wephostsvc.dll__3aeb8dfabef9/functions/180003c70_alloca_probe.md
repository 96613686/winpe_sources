# _alloca_probe

- ea: `0x180003c70`
- end: `0x180003cbd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022c0`

## callees

- `0x180003c70`

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
0x180003c70  sub     rsp, 10h
0x180003c74  mov     [rsp+10h+var_10], r10
0x180003c78  mov     [rsp+10h+var_8], r11
0x180003c7d  xor     r11, r11
0x180003c80  lea     r10, [rsp+10h+arg_0]
0x180003c85  sub     r10, rax
0x180003c88  cmovb   r10, r11
0x180003c8c  mov     r11, gs:10h
0x180003c95  cmp     r10, r11
0x180003c98  jnb     short loc_180003CAF
0x180003c9a  and     r10w, 0F000h
0x180003ca0  lea     r11, [r11-1000h]
0x180003ca7  test    [r11], r11b
0x180003caa  cmp     r10, r11
0x180003cad  jb      short loc_180003CA0
0x180003caf  mov     r10, [rsp+10h+var_10]
0x180003cb3  mov     r11, [rsp+10h+var_8]
0x180003cb8  add     rsp, 10h
0x180003cbc  retn
```
