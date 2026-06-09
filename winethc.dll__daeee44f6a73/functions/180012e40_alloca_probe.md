# _alloca_probe

- ea: `0x180012e40`
- end: `0x180012e8d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022e8`
- `0x180002568`
- `0x180002818`
- `0x180003b40`
- `0x18000b374`
- `0x18000b6fc`
- `0x18000c82c`
- `0x18000e2a4`

## callees

- `0x180012e40`

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
0x180012e40  sub     rsp, 10h
0x180012e44  mov     [rsp+10h+var_10], r10
0x180012e48  mov     [rsp+10h+var_8], r11
0x180012e4d  xor     r11, r11
0x180012e50  lea     r10, [rsp+10h+arg_0]
0x180012e55  sub     r10, rax
0x180012e58  cmovb   r10, r11
0x180012e5c  mov     r11, gs:10h
0x180012e65  cmp     r10, r11
0x180012e68  jnb     short loc_180012E7F
0x180012e6a  and     r10w, 0F000h
0x180012e70  lea     r11, [r11-1000h]
0x180012e77  test    [r11], r11b
0x180012e7a  cmp     r10, r11
0x180012e7d  jb      short loc_180012E70
0x180012e7f  mov     r10, [rsp+10h+var_10]
0x180012e83  mov     r11, [rsp+10h+var_8]
0x180012e88  add     rsp, 10h
0x180012e8c  retn
```
