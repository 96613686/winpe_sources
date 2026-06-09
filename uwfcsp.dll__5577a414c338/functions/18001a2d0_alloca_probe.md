# _alloca_probe

- ea: `0x18001a2d0`
- end: `0x18001a31d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180004724`
- `0x180004994`
- `0x180004c28`
- `0x180008624`
- `0x18000a1b8`
- `0x18000a50c`
- `0x18000b568`

## callees

- `0x18001a2d0`

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
0x18001a2d0  sub     rsp, 10h
0x18001a2d4  mov     [rsp+10h+var_10], r10
0x18001a2d8  mov     [rsp+10h+var_8], r11
0x18001a2dd  xor     r11, r11
0x18001a2e0  lea     r10, [rsp+10h+arg_0]
0x18001a2e5  sub     r10, rax
0x18001a2e8  cmovb   r10, r11
0x18001a2ec  mov     r11, gs:10h
0x18001a2f5  cmp     r10, r11
0x18001a2f8  jnb     short loc_18001A30F
0x18001a2fa  and     r10w, 0F000h
0x18001a300  lea     r11, [r11-1000h]
0x18001a307  test    [r11], r11b
0x18001a30a  cmp     r10, r11
0x18001a30d  jb      short loc_18001A300
0x18001a30f  mov     r10, [rsp+10h+var_10]
0x18001a313  mov     r11, [rsp+10h+var_8]
0x18001a318  add     rsp, 10h
0x18001a31c  retn
```
