# _alloca_probe

- ea: `0x180003cc0`
- end: `0x180003d0d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c70`

## callees

- `0x180003cc0`

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
0x180003cc0  sub     rsp, 10h
0x180003cc4  mov     [rsp+10h+var_10], r10
0x180003cc8  mov     [rsp+10h+var_8], r11
0x180003ccd  xor     r11, r11
0x180003cd0  lea     r10, [rsp+10h+arg_0]
0x180003cd5  sub     r10, rax
0x180003cd8  cmovb   r10, r11
0x180003cdc  mov     r11, gs:10h
0x180003ce5  cmp     r10, r11
0x180003ce8  jnb     short loc_180003CFF
0x180003cea  and     r10w, 0F000h
0x180003cf0  lea     r11, [r11-1000h]
0x180003cf7  test    [r11], r11b
0x180003cfa  cmp     r10, r11
0x180003cfd  jb      short loc_180003CF0
0x180003cff  mov     r10, [rsp+10h+var_10]
0x180003d03  mov     r11, [rsp+10h+var_8]
0x180003d08  add     rsp, 10h
0x180003d0c  retn
```
