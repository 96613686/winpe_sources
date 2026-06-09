# __alloca_probe

- ea: `0x180093220`
- end: `0x18009326e`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ad70`
- `0x18002b2a0`
- `0x18002b800`
- `0x18002bd80`
- `0x18002c2f0`
- `0x18002c840`
- `0x18002cdb0`
- `0x18002d300`
- `0x18002d870`
- `0x18002ddb0`
- `0x180078800`

## callees

- `0x180093220`

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
0x180093220  sub     rsp, 10h
0x180093224  mov     [rsp+10h+var_10], r10
0x180093228  mov     [rsp+10h+var_8], r11
0x18009322d  xor     r11, r11
0x180093230  lea     r10, [rsp+10h+arg_0]
0x180093235  sub     r10, rax
0x180093238  cmovb   r10, r11
0x18009323c  mov     r11, gs:10h
0x180093245  cmp     r10, r11
0x180093248  jnb     short loc_180093260
0x18009324a  and     r10w, 0F000h
0x180093250  lea     r11, [r11-1000h]
0x180093257  mov     byte ptr [r11], 0
0x18009325b  cmp     r10, r11
0x18009325e  jnz     short loc_180093250
0x180093260  mov     r10, [rsp+10h+var_10]
0x180093264  mov     r11, [rsp+10h+var_8]
0x180093269  add     rsp, 10h
0x18009326d  retn
```
