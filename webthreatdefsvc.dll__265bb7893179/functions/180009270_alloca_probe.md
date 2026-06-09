# __alloca_probe

- ea: `0x180009270`
- end: `0x1800092be`
- name: `__alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180009704`
- `0x1800097e0`
- `0x180009a84`
- `0x18000ce50`
- `0x18000fbe4`
- `0x180011430`
- `0x18001247c`
- `0x180012530`
- `0x180012c18`
- `0x180016918`
- `0x180019258`

## callees

- `0x180009270`

## pseudocode

```c
unsigned __int64 __fastcall _alloca_probe()
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
0x180009270  sub     rsp, 10h
0x180009274  mov     [rsp+10h+var_10], r10
0x180009278  mov     [rsp+10h+var_8], r11
0x18000927d  xor     r11, r11
0x180009280  lea     r10, [rsp+10h+arg_0]
0x180009285  sub     r10, rax
0x180009288  cmovb   r10, r11
0x18000928c  mov     r11, gs:10h
0x180009295  cmp     r10, r11
0x180009298  jnb     short cs20
0x18000929a  and     r10w, 0F000h
0x1800092a0  lea     r11, [r11-1000h]
0x1800092a7  mov     byte ptr [r11], 0
0x1800092ab  cmp     r10, r11
0x1800092ae  jnz     short cs10
0x1800092b0  mov     r10, [rsp+10h+var_10]
0x1800092b4  mov     r11, [rsp+10h+var_8]
0x1800092b9  add     rsp, 10h
0x1800092bd  retn
```
