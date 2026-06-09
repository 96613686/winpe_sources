# _alloca_probe

- ea: `0x180006680`
- end: `0x1800066ce`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003560`
- `0x1800039c0`
- `0x180003c30`
- `0x180003ecc`

## callees

- `0x180006680`

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
0x180006680  sub     rsp, 10h
0x180006684  mov     [rsp+10h+var_10], r10
0x180006688  mov     [rsp+10h+var_8], r11
0x18000668d  xor     r11, r11
0x180006690  lea     r10, [rsp+10h+arg_0]
0x180006695  sub     r10, rax
0x180006698  cmovb   r10, r11
0x18000669c  mov     r11, gs:10h
0x1800066a5  cmp     r10, r11
0x1800066a8  jnb     short cs20
0x1800066aa  and     r10w, 0F000h
0x1800066b0  lea     r11, [r11-1000h]
0x1800066b7  mov     byte ptr [r11], 0
0x1800066bb  cmp     r10, r11
0x1800066be  jnz     short cs10
0x1800066c0  mov     r10, [rsp+10h+var_10]
0x1800066c4  mov     r11, [rsp+10h+var_8]
0x1800066c9  add     rsp, 10h
0x1800066cd  retn
```
