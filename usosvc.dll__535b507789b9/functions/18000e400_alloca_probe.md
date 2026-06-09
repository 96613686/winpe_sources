# _alloca_probe

- ea: `0x18000e400`
- end: `0x18000e44e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034dc`
- `0x180003744`
- `0x1800039d8`
- `0x180006970`
- `0x180007008`
- `0x180007078`
- `0x180009a7c`
- `0x18000cf7c`
- `0x18000e09c`

## callees

- `0x18000e400`

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
0x18000e400  sub     rsp, 10h
0x18000e404  mov     [rsp+10h+var_10], r10
0x18000e408  mov     [rsp+10h+var_8], r11
0x18000e40d  xor     r11, r11
0x18000e410  lea     r10, [rsp+10h+arg_0]
0x18000e415  sub     r10, rax
0x18000e418  cmovb   r10, r11
0x18000e41c  mov     r11, gs:10h
0x18000e425  cmp     r10, r11
0x18000e428  jnb     short cs20
0x18000e42a  and     r10w, 0F000h
0x18000e430  lea     r11, [r11-1000h]
0x18000e437  mov     byte ptr [r11], 0
0x18000e43b  cmp     r10, r11
0x18000e43e  jnz     short cs10
0x18000e440  mov     r10, [rsp+10h+var_10]
0x18000e444  mov     r11, [rsp+10h+var_8]
0x18000e449  add     rsp, 10h
0x18000e44d  retn
```
