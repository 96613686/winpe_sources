# _alloca_probe

- ea: `0x14000ac20`
- end: `0x14000ac6e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f78`
- `0x1400031e8`
- `0x14000347c`
- `0x140006380`
- `0x140006a7c`
- `0x140006aec`
- `0x14000983c`

## callees

- `0x14000ac20`

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
0x14000ac20  sub     rsp, 10h
0x14000ac24  mov     [rsp+10h+var_10], r10
0x14000ac28  mov     [rsp+10h+var_8], r11
0x14000ac2d  xor     r11, r11
0x14000ac30  lea     r10, [rsp+10h+arg_0]
0x14000ac35  sub     r10, rax
0x14000ac38  cmovb   r10, r11
0x14000ac3c  mov     r11, gs:10h
0x14000ac45  cmp     r10, r11
0x14000ac48  jnb     short loc_14000AC60
0x14000ac4a  and     r10w, 0F000h
0x14000ac50  lea     r11, [r11-1000h]
0x14000ac57  mov     byte ptr [r11], 0
0x14000ac5b  cmp     r10, r11
0x14000ac5e  jnz     short loc_14000AC50
0x14000ac60  mov     r10, [rsp+10h+var_10]
0x14000ac64  mov     r11, [rsp+10h+var_8]
0x14000ac69  add     rsp, 10h
0x14000ac6d  retn
```
