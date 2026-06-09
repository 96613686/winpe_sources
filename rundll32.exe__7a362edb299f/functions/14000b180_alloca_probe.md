# _alloca_probe

- ea: `0x14000b180`
- end: `0x14000b1ce`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031dc`
- `0x140003444`
- `0x1400036e0`
- `0x140009d94`
- `0x14000abe4`

## callees

- `0x14000b180`

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
0x14000b180  sub     rsp, 10h
0x14000b184  mov     [rsp+10h+var_10], r10
0x14000b188  mov     [rsp+10h+var_8], r11
0x14000b18d  xor     r11, r11
0x14000b190  lea     r10, [rsp+10h+arg_0]
0x14000b195  sub     r10, rax
0x14000b198  cmovb   r10, r11
0x14000b19c  mov     r11, gs:10h
0x14000b1a5  cmp     r10, r11
0x14000b1a8  jnb     short loc_14000B1C0
0x14000b1aa  and     r10w, 0F000h
0x14000b1b0  lea     r11, [r11-1000h]
0x14000b1b7  mov     byte ptr [r11], 0
0x14000b1bb  cmp     r10, r11
0x14000b1be  jnz     short loc_14000B1B0
0x14000b1c0  mov     r10, [rsp+10h+var_10]
0x14000b1c4  mov     r11, [rsp+10h+var_8]
0x14000b1c9  add     rsp, 10h
0x14000b1cd  retn
```
