# _alloca_probe

- ea: `0x1400154e0`
- end: `0x14001552e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e54`
- `0x1400030bc`
- `0x140003358`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000b058`
- `0x14000c42c`
- `0x140014c34`

## callees

- `0x1400154e0`

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
0x1400154e0  sub     rsp, 10h
0x1400154e4  mov     [rsp+10h+var_10], r10
0x1400154e8  mov     [rsp+10h+var_8], r11
0x1400154ed  xor     r11, r11
0x1400154f0  lea     r10, [rsp+10h+arg_0]
0x1400154f5  sub     r10, rax
0x1400154f8  cmovb   r10, r11
0x1400154fc  mov     r11, gs:10h
0x140015505  cmp     r10, r11
0x140015508  jnb     short loc_140015520
0x14001550a  and     r10w, 0F000h
0x140015510  lea     r11, [r11-1000h]
0x140015517  mov     byte ptr [r11], 0
0x14001551b  cmp     r10, r11
0x14001551e  jnz     short loc_140015510
0x140015520  mov     r10, [rsp+10h+var_10]
0x140015524  mov     r11, [rsp+10h+var_8]
0x140015529  add     rsp, 10h
0x14001552d  retn
```
