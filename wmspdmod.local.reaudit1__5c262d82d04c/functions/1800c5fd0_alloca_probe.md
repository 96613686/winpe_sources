# __alloca_probe

- ea: `0x1800c5fd0`
- end: `0x1800c601e`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x1800797c0`
- `0x180079c48`
- `0x18007a0dc`
- `0x18007a524`
- `0x18007a9a4`
- `0x18007ae14`
- `0x18007b2b4`
- `0x18007b73c`
- `0x18007bbe8`
- `0x18007c07c`
- `0x180085f44`
- `0x18009eaa4`
- `0x1800a6f70`
- `0x1800adb14`
- `0x1800aea24`
- `0x1800af038`
- `0x1800b90e8`

## callees

- `0x1800c5fd0`

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
0x1800c5fd0  sub     rsp, 10h
0x1800c5fd4  mov     [rsp+10h+var_10], r10
0x1800c5fd8  mov     [rsp+10h+var_8], r11
0x1800c5fdd  xor     r11, r11
0x1800c5fe0  lea     r10, [rsp+10h+arg_0]
0x1800c5fe5  sub     r10, rax
0x1800c5fe8  cmovb   r10, r11
0x1800c5fec  mov     r11, gs:10h
0x1800c5ff5  cmp     r10, r11
0x1800c5ff8  jnb     short loc_1800C6010
0x1800c5ffa  and     r10w, 0F000h
0x1800c6000  lea     r11, [r11-1000h]
0x1800c6007  mov     byte ptr [r11], 0
0x1800c600b  cmp     r10, r11
0x1800c600e  jnz     short loc_1800C6000
0x1800c6010  mov     r10, [rsp+10h+var_10]
0x1800c6014  mov     r11, [rsp+10h+var_8]
0x1800c6019  add     rsp, 10h
0x1800c601d  retn
```
