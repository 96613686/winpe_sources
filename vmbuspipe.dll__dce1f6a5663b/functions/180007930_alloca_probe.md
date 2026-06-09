# _alloca_probe

- ea: `0x180007930`
- end: `0x18000797e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003484`
- `0x180003524`
- `0x1800035d4`
- `0x180003880`
- `0x180003a90`
- `0x180005b68`
- `0x180006f60`

## callees

- `0x180007930`

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
0x180007930  sub     rsp, 10h
0x180007934  mov     [rsp+10h+var_10], r10
0x180007938  mov     [rsp+10h+var_8], r11
0x18000793d  xor     r11, r11
0x180007940  lea     r10, [rsp+10h+arg_0]
0x180007945  sub     r10, rax
0x180007948  cmovb   r10, r11
0x18000794c  mov     r11, gs:10h
0x180007955  cmp     r10, r11
0x180007958  jnb     short cs20
0x18000795a  and     r10w, 0F000h
0x180007960  lea     r11, [r11-1000h]
0x180007967  mov     byte ptr [r11], 0
0x18000796b  cmp     r10, r11
0x18000796e  jnz     short cs10
0x180007970  mov     r10, [rsp+10h+var_10]
0x180007974  mov     r11, [rsp+10h+var_8]
0x180007979  add     rsp, 10h
0x18000797d  retn
```
