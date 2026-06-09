# _alloca_probe

- ea: `0x180019850`
- end: `0x18001989e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003114`
- `0x180003394`
- `0x180003648`
- `0x1800038f4`
- `0x180008e2c`
- `0x18000ca70`
- `0x18000cb98`

## callees

- `0x180019850`

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
0x180019850  sub     rsp, 10h
0x180019854  mov     [rsp+10h+var_10], r10
0x180019858  mov     [rsp+10h+var_8], r11
0x18001985d  xor     r11, r11
0x180019860  lea     r10, [rsp+10h+arg_0]
0x180019865  sub     r10, rax
0x180019868  cmovb   r10, r11
0x18001986c  mov     r11, gs:10h
0x180019875  cmp     r10, r11
0x180019878  jnb     short cs20
0x18001987a  and     r10w, 0F000h
0x180019880  lea     r11, [r11-1000h]
0x180019887  mov     byte ptr [r11], 0
0x18001988b  cmp     r10, r11
0x18001988e  jnz     short cs10
0x180019890  mov     r10, [rsp+10h+var_10]
0x180019894  mov     r11, [rsp+10h+var_8]
0x180019899  add     rsp, 10h
0x18001989d  retn
```
