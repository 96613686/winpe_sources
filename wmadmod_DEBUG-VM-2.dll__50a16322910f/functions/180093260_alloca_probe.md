# __alloca_probe

- ea: `0x180093260`
- end: `0x1800932ae`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18002adb0`
- `0x18002b2e0`
- `0x18002b840`
- `0x18002bdc0`
- `0x18002c330`
- `0x18002c880`
- `0x18002cdf0`
- `0x18002d340`
- `0x18002d8b0`
- `0x18002ddf0`
- `0x180078840`

## callees

- `0x180093260`

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
0x180093260  sub     rsp, 10h
0x180093264  mov     [rsp+10h+var_10], r10
0x180093268  mov     [rsp+10h+var_8], r11
0x18009326d  xor     r11, r11
0x180093270  lea     r10, [rsp+10h+arg_0]
0x180093275  sub     r10, rax
0x180093278  cmovb   r10, r11
0x18009327c  mov     r11, gs:10h
0x180093285  cmp     r10, r11
0x180093288  jnb     short loc_1800932A0
0x18009328a  and     r10w, 0F000h
0x180093290  lea     r11, [r11-1000h]
0x180093297  mov     byte ptr [r11], 0
0x18009329b  cmp     r10, r11
0x18009329e  jnz     short loc_180093290
0x1800932a0  mov     r10, [rsp+10h+var_10]
0x1800932a4  mov     r11, [rsp+10h+var_8]
0x1800932a9  add     rsp, 10h
0x1800932ad  retn
```
