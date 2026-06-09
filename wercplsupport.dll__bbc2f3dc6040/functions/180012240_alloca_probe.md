# _alloca_probe

- ea: `0x180012240`
- end: `0x18001228d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800088fc`
- `0x180008b5c`
- `0x180008df4`
- `0x18000d28c`
- `0x180011c1c`

## callees

- `0x180012240`

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
0x180012240  sub     rsp, 10h
0x180012244  mov     [rsp+10h+var_10], r10
0x180012248  mov     [rsp+10h+var_8], r11
0x18001224d  xor     r11, r11
0x180012250  lea     r10, [rsp+10h+arg_0]
0x180012255  sub     r10, rax
0x180012258  cmovb   r10, r11
0x18001225c  mov     r11, gs:10h
0x180012265  cmp     r10, r11
0x180012268  jnb     short loc_18001227F
0x18001226a  and     r10w, 0F000h
0x180012270  lea     r11, [r11-1000h]
0x180012277  test    [r11], r11b
0x18001227a  cmp     r10, r11
0x18001227d  jb      short loc_180012270
0x18001227f  mov     r10, [rsp+10h+var_10]
0x180012283  mov     r11, [rsp+10h+var_8]
0x180012288  add     rsp, 10h
0x18001228c  retn
```
