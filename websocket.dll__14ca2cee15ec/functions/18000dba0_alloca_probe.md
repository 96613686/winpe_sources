# _alloca_probe

- ea: `0x18000dba0`
- end: `0x18000dbee`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f14`
- `0x18000317c`
- `0x180003418`
- `0x1800074e8`
- `0x180008e74`

## callees

- `0x18000dba0`

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
0x18000dba0  sub     rsp, 10h
0x18000dba4  mov     [rsp+10h+var_10], r10
0x18000dba8  mov     [rsp+10h+var_8], r11
0x18000dbad  xor     r11, r11
0x18000dbb0  lea     r10, [rsp+10h+arg_0]
0x18000dbb5  sub     r10, rax
0x18000dbb8  cmovb   r10, r11
0x18000dbbc  mov     r11, gs:10h
0x18000dbc5  cmp     r10, r11
0x18000dbc8  jnb     short cs20
0x18000dbca  and     r10w, 0F000h
0x18000dbd0  lea     r11, [r11-1000h]
0x18000dbd7  mov     byte ptr [r11], 0
0x18000dbdb  cmp     r10, r11
0x18000dbde  jnz     short cs10
0x18000dbe0  mov     r10, [rsp+10h+var_10]
0x18000dbe4  mov     r11, [rsp+10h+var_8]
0x18000dbe9  add     rsp, 10h
0x18000dbed  retn
```
