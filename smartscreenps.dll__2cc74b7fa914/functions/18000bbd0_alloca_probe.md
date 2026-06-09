# _alloca_probe

- ea: `0x18000bbd0`
- end: `0x18000bc1e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ebc`
- `0x180006f6c`
- `0x180007200`
- `0x180009c50`
- `0x18000a058`

## callees

- `0x18000bbd0`

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
0x18000bbd0  sub     rsp, 10h
0x18000bbd4  mov     [rsp+10h+var_10], r10
0x18000bbd8  mov     [rsp+10h+var_8], r11
0x18000bbdd  xor     r11, r11
0x18000bbe0  lea     r10, [rsp+10h+arg_0]
0x18000bbe5  sub     r10, rax
0x18000bbe8  cmovb   r10, r11
0x18000bbec  mov     r11, gs:10h
0x18000bbf5  cmp     r10, r11
0x18000bbf8  jnb     short cs20
0x18000bbfa  and     r10w, 0F000h
0x18000bc00  lea     r11, [r11-1000h]
0x18000bc07  mov     byte ptr [r11], 0
0x18000bc0b  cmp     r10, r11
0x18000bc0e  jnz     short cs10
0x18000bc10  mov     r10, [rsp+10h+var_10]
0x18000bc14  mov     r11, [rsp+10h+var_8]
0x18000bc19  add     rsp, 10h
0x18000bc1d  retn
```
