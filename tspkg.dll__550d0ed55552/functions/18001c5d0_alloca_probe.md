# _alloca_probe

- ea: `0x18001c5d0`
- end: `0x18001c61e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cd24`
- `0x18000cdd4`
- `0x18000d070`
- `0x18000f5f8`
- `0x180010c7c`
- `0x180014e90`
- `0x180019460`
- `0x18001be38`

## callees

- `0x18001c5d0`

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
0x18001c5d0  sub     rsp, 10h
0x18001c5d4  mov     [rsp+10h+var_10], r10
0x18001c5d8  mov     [rsp+10h+var_8], r11
0x18001c5dd  xor     r11, r11
0x18001c5e0  lea     r10, [rsp+10h+arg_0]
0x18001c5e5  sub     r10, rax
0x18001c5e8  cmovb   r10, r11
0x18001c5ec  mov     r11, gs:10h
0x18001c5f5  cmp     r10, r11
0x18001c5f8  jnb     short cs20
0x18001c5fa  and     r10w, 0F000h
0x18001c600  lea     r11, [r11-1000h]
0x18001c607  mov     byte ptr [r11], 0
0x18001c60b  cmp     r10, r11
0x18001c60e  jnz     short cs10
0x18001c610  mov     r10, [rsp+10h+var_10]
0x18001c614  mov     r11, [rsp+10h+var_8]
0x18001c619  add     rsp, 10h
0x18001c61d  retn
```
