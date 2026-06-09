# __alloca_probe

- ea: `0x1800196e0`
- end: `0x18001972e`
- name: `__alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180017a20`
- `0x180019bf8`
- `0x180019cd4`
- `0x180019f78`
- `0x18001d380`
- `0x180020044`
- `0x1800218a0`
- `0x1800228c8`
- `0x180022998`
- `0x180023058`
- `0x1800243cc`
- `0x18002448c`
- `0x180024904`

## callees

- `0x1800196e0`

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
0x1800196e0  sub     rsp, 10h
0x1800196e4  mov     [rsp+10h+var_10], r10
0x1800196e8  mov     [rsp+10h+var_8], r11
0x1800196ed  xor     r11, r11
0x1800196f0  lea     r10, [rsp+10h+arg_0]
0x1800196f5  sub     r10, rax
0x1800196f8  cmovb   r10, r11
0x1800196fc  mov     r11, gs:10h
0x180019705  cmp     r10, r11
0x180019708  jnb     short cs20
0x18001970a  and     r10w, 0F000h
0x180019710  lea     r11, [r11-1000h]
0x180019717  mov     byte ptr [r11], 0
0x18001971b  cmp     r10, r11
0x18001971e  jnz     short cs10
0x180019720  mov     r10, [rsp+10h+var_10]
0x180019724  mov     r11, [rsp+10h+var_8]
0x180019729  add     rsp, 10h
0x18001972d  retn
```
