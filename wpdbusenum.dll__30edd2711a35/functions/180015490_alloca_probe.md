# _alloca_probe

- ea: `0x180015490`
- end: `0x1800154de`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b248`
- `0x18000b2fc`
- `0x18000b3f0`
- `0x18000daa0`

## callees

- `0x180015490`

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
0x180015490  sub     rsp, 10h
0x180015494  mov     [rsp+10h+var_10], r10
0x180015498  mov     [rsp+10h+var_8], r11
0x18001549d  xor     r11, r11
0x1800154a0  lea     r10, [rsp+10h+arg_0]
0x1800154a5  sub     r10, rax
0x1800154a8  cmovb   r10, r11
0x1800154ac  mov     r11, gs:10h
0x1800154b5  cmp     r10, r11
0x1800154b8  jnb     short cs20
0x1800154ba  and     r10w, 0F000h
0x1800154c0  lea     r11, [r11-1000h]
0x1800154c7  mov     byte ptr [r11], 0
0x1800154cb  cmp     r10, r11
0x1800154ce  jnz     short cs10
0x1800154d0  mov     r10, [rsp+10h+var_10]
0x1800154d4  mov     r11, [rsp+10h+var_8]
0x1800154d9  add     rsp, 10h
0x1800154dd  retn
```
