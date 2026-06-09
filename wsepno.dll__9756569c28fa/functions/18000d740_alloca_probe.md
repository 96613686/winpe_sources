# _alloca_probe

- ea: `0x18000d740`
- end: `0x18000d78e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003900`
- `0x1800043b8`
- `0x180004638`
- `0x1800048e4`
- `0x180009a0c`
- `0x18000b824`

## callees

- `0x18000d740`

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
0x18000d740  sub     rsp, 10h
0x18000d744  mov     [rsp+10h+var_10], r10
0x18000d748  mov     [rsp+10h+var_8], r11
0x18000d74d  xor     r11, r11
0x18000d750  lea     r10, [rsp+10h+arg_0]
0x18000d755  sub     r10, rax
0x18000d758  cmovb   r10, r11
0x18000d75c  mov     r11, gs:10h
0x18000d765  cmp     r10, r11
0x18000d768  jnb     short cs20
0x18000d76a  and     r10w, 0F000h
0x18000d770  lea     r11, [r11-1000h]
0x18000d777  mov     byte ptr [r11], 0
0x18000d77b  cmp     r10, r11
0x18000d77e  jnz     short cs10
0x18000d780  mov     r10, [rsp+10h+var_10]
0x18000d784  mov     r11, [rsp+10h+var_8]
0x18000d789  add     rsp, 10h
0x18000d78d  retn
```
