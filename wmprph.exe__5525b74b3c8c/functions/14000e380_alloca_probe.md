# _alloca_probe

- ea: `0x14000e380`
- end: `0x14000e3ce`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b10`
- `0x140009ec8`
- `0x14000b9a0`
- `0x14000ca78`

## callees

- `0x14000e380`

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
0x14000e380  sub     rsp, 10h
0x14000e384  mov     [rsp+10h+var_10], r10
0x14000e388  mov     [rsp+10h+var_8], r11
0x14000e38d  xor     r11, r11
0x14000e390  lea     r10, [rsp+10h+arg_0]
0x14000e395  sub     r10, rax
0x14000e398  cmovb   r10, r11
0x14000e39c  mov     r11, gs:10h
0x14000e3a5  cmp     r10, r11
0x14000e3a8  jnb     short loc_14000E3C0
0x14000e3aa  and     r10w, 0F000h
0x14000e3b0  lea     r11, [r11-1000h]
0x14000e3b7  mov     byte ptr [r11], 0
0x14000e3bb  cmp     r10, r11
0x14000e3be  jnz     short loc_14000E3B0
0x14000e3c0  mov     r10, [rsp+10h+var_10]
0x14000e3c4  mov     r11, [rsp+10h+var_8]
0x14000e3c9  add     rsp, 10h
0x14000e3cd  retn
```
