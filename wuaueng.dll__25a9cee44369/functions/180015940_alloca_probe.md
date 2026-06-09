# _alloca_probe

- ea: `0x180015940`
- end: `0x18001598e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d90`
- `0x180004580`
- `0x180004a38`
- `0x180004b60`
- `0x1800084e4`
- `0x180008a10`
- `0x180008c38`
- `0x180009af8`

## callees

- `0x180015940`

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
0x180015940  sub     rsp, 10h
0x180015944  mov     [rsp+10h+var_10], r10
0x180015948  mov     [rsp+10h+var_8], r11
0x18001594d  xor     r11, r11
0x180015950  lea     r10, [rsp+10h+arg_0]
0x180015955  sub     r10, rax
0x180015958  cmovb   r10, r11
0x18001595c  mov     r11, gs:10h
0x180015965  cmp     r10, r11
0x180015968  jnb     short cs20
0x18001596a  and     r10w, 0F000h
0x180015970  lea     r11, [r11-1000h]
0x180015977  mov     byte ptr [r11], 0
0x18001597b  cmp     r10, r11
0x18001597e  jnz     short cs10
0x180015980  mov     r10, [rsp+10h+var_10]
0x180015984  mov     r11, [rsp+10h+var_8]
0x180015989  add     rsp, 10h
0x18001598d  retn
```
