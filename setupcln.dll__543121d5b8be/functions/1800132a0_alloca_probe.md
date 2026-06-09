# _alloca_probe

- ea: `0x1800132a0`
- end: `0x1800132ed`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cc2c`
- `0x18000ce94`
- `0x18000d130`
- `0x180010840`
- `0x180012820`
- `0x180012a08`

## callees

- `0x1800132a0`

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
0x1800132a0  sub     rsp, 10h
0x1800132a4  mov     [rsp+10h+var_10], r10
0x1800132a8  mov     [rsp+10h+var_8], r11
0x1800132ad  xor     r11, r11
0x1800132b0  lea     r10, [rsp+10h+arg_0]
0x1800132b5  sub     r10, rax
0x1800132b8  cmovb   r10, r11
0x1800132bc  mov     r11, gs:10h
0x1800132c5  cmp     r10, r11
0x1800132c8  jnb     short loc_1800132DF
0x1800132ca  and     r10w, 0F000h
0x1800132d0  lea     r11, [r11-1000h]
0x1800132d7  test    [r11], r11b
0x1800132da  cmp     r10, r11
0x1800132dd  jb      short loc_1800132D0
0x1800132df  mov     r10, [rsp+10h+var_10]
0x1800132e3  mov     r11, [rsp+10h+var_8]
0x1800132e8  add     rsp, 10h
0x1800132ec  retn
```
