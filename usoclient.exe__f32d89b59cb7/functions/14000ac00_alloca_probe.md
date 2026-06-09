# _alloca_probe

- ea: `0x14000ac00`
- end: `0x14000ac4e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f98`
- `0x140003208`
- `0x14000349c`
- `0x1400063a0`
- `0x140006a9c`
- `0x140006b0c`
- `0x14000980c`

## callees

- `0x14000ac00`

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
0x14000ac00  sub     rsp, 10h
0x14000ac04  mov     [rsp+10h+var_10], r10
0x14000ac08  mov     [rsp+10h+var_8], r11
0x14000ac0d  xor     r11, r11
0x14000ac10  lea     r10, [rsp+10h+arg_0]
0x14000ac15  sub     r10, rax
0x14000ac18  cmovb   r10, r11
0x14000ac1c  mov     r11, gs:10h
0x14000ac25  cmp     r10, r11
0x14000ac28  jnb     short loc_14000AC40
0x14000ac2a  and     r10w, 0F000h
0x14000ac30  lea     r11, [r11-1000h]
0x14000ac37  mov     byte ptr [r11], 0
0x14000ac3b  cmp     r10, r11
0x14000ac3e  jnz     short loc_14000AC30
0x14000ac40  mov     r10, [rsp+10h+var_10]
0x14000ac44  mov     r11, [rsp+10h+var_8]
0x14000ac49  add     rsp, 10h
0x14000ac4d  retn
```
