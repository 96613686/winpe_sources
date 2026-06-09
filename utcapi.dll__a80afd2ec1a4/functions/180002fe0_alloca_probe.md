# _alloca_probe

- ea: `0x180002fe0`
- end: `0x18000302e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d9c`

## callees

- `0x180002fe0`

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
    {
      StackLimit -= 4096;
      *StackLimit = 0;
    }
    while ( v1 != StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x180002fe0  sub     rsp, 10h
0x180002fe4  mov     [rsp+10h+var_10], r10
0x180002fe8  mov     [rsp+10h+var_8], r11
0x180002fed  xor     r11, r11
0x180002ff0  lea     r10, [rsp+10h+arg_0]
0x180002ff5  sub     r10, rax
0x180002ff8  cmovb   r10, r11
0x180002ffc  mov     r11, gs:10h
0x180003005  cmp     r10, r11
0x180003008  jnb     short cs20
0x18000300a  and     r10w, 0F000h
0x180003010  lea     r11, [r11-1000h]
0x180003017  mov     byte ptr [r11], 0
0x18000301b  cmp     r10, r11
0x18000301e  jnz     short cs10
0x180003020  mov     r10, [rsp+10h+var_10]
0x180003024  mov     r11, [rsp+10h+var_8]
0x180003029  add     rsp, 10h
0x18000302d  retn
```
