# _alloca_probe

- ea: `0x1800096d0`
- end: `0x18000971e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000344c`
- `0x1800036bc`
- `0x180003958`

## callees

- `0x1800096d0`

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
0x1800096d0  sub     rsp, 10h
0x1800096d4  mov     [rsp+10h+var_10], r10
0x1800096d8  mov     [rsp+10h+var_8], r11
0x1800096dd  xor     r11, r11
0x1800096e0  lea     r10, [rsp+10h+arg_0]
0x1800096e5  sub     r10, rax
0x1800096e8  cmovb   r10, r11
0x1800096ec  mov     r11, gs:10h
0x1800096f5  cmp     r10, r11
0x1800096f8  jnb     short cs20
0x1800096fa  and     r10w, 0F000h
0x180009700  lea     r11, [r11-1000h]
0x180009707  mov     byte ptr [r11], 0
0x18000970b  cmp     r10, r11
0x18000970e  jnz     short cs10
0x180009710  mov     r10, [rsp+10h+var_10]
0x180009714  mov     r11, [rsp+10h+var_8]
0x180009719  add     rsp, 10h
0x18000971d  retn
```
