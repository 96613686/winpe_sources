# _alloca_probe

- ea: `0x180043de0`
- end: `0x180043e2e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003050`
- `0x18000ef30`
- `0x18000f3b4`
- `0x18000ffc0`

## callees

- `0x180043de0`

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
0x180043de0  sub     rsp, 10h
0x180043de4  mov     [rsp+10h+var_10], r10
0x180043de8  mov     [rsp+10h+var_8], r11
0x180043ded  xor     r11, r11
0x180043df0  lea     r10, [rsp+10h+arg_0]
0x180043df5  sub     r10, rax
0x180043df8  cmovb   r10, r11
0x180043dfc  mov     r11, gs:10h
0x180043e05  cmp     r10, r11
0x180043e08  jnb     short cs20
0x180043e0a  and     r10w, 0F000h
0x180043e10  lea     r11, [r11-1000h]
0x180043e17  mov     byte ptr [r11], 0
0x180043e1b  cmp     r10, r11
0x180043e1e  jnz     short cs10
0x180043e20  mov     r10, [rsp+10h+var_10]
0x180043e24  mov     r11, [rsp+10h+var_8]
0x180043e29  add     rsp, 10h
0x180043e2d  retn
```
