# _alloca_probe

- ea: `0x140007570`
- end: `0x1400075be`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400028bc`
- `0x140003e1c`
- `0x140004190`
- `0x1400049f8`

## callees

- `0x140007570`

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
0x140007570  sub     rsp, 10h
0x140007574  mov     [rsp+10h+var_10], r10
0x140007578  mov     [rsp+10h+var_8], r11
0x14000757d  xor     r11, r11
0x140007580  lea     r10, [rsp+10h+arg_0]
0x140007585  sub     r10, rax
0x140007588  cmovb   r10, r11
0x14000758c  mov     r11, gs:10h
0x140007595  cmp     r10, r11
0x140007598  jnb     short loc_1400075B0
0x14000759a  and     r10w, 0F000h
0x1400075a0  lea     r11, [r11-1000h]
0x1400075a7  mov     byte ptr [r11], 0
0x1400075ab  cmp     r10, r11
0x1400075ae  jnz     short loc_1400075A0
0x1400075b0  mov     r10, [rsp+10h+var_10]
0x1400075b4  mov     r11, [rsp+10h+var_8]
0x1400075b9  add     rsp, 10h
0x1400075bd  retn
```
