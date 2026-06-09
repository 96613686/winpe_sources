# _alloca_probe

- ea: `0x140006640`
- end: `0x14000668e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002424`
- `0x1400043a8`
- `0x140004954`
- `0x1400051e0`

## callees

- `0x140006640`

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
0x140006640  sub     rsp, 10h
0x140006644  mov     [rsp+10h+var_10], r10
0x140006648  mov     [rsp+10h+var_8], r11
0x14000664d  xor     r11, r11
0x140006650  lea     r10, [rsp+10h+arg_0]
0x140006655  sub     r10, rax
0x140006658  cmovb   r10, r11
0x14000665c  mov     r11, gs:10h
0x140006665  cmp     r10, r11
0x140006668  jnb     short loc_140006680
0x14000666a  and     r10w, 0F000h
0x140006670  lea     r11, [r11-1000h]
0x140006677  mov     byte ptr [r11], 0
0x14000667b  cmp     r10, r11
0x14000667e  jnz     short loc_140006670
0x140006680  mov     r10, [rsp+10h+var_10]
0x140006684  mov     r11, [rsp+10h+var_8]
0x140006689  add     rsp, 10h
0x14000668d  retn
```
