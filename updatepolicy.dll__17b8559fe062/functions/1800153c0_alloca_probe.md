# _alloca_probe

- ea: `0x1800153c0`
- end: `0x18001540e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b8c`
- `0x180005e40`
- `0x180005ed8`
- `0x1800061d0`
- `0x180006560`
- `0x1800068b4`
- `0x1800072b0`
- `0x1800086a0`

## callees

- `0x1800153c0`

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
0x1800153c0  sub     rsp, 10h
0x1800153c4  mov     [rsp+10h+var_10], r10
0x1800153c8  mov     [rsp+10h+var_8], r11
0x1800153cd  xor     r11, r11
0x1800153d0  lea     r10, [rsp+10h+arg_0]
0x1800153d5  sub     r10, rax
0x1800153d8  cmovb   r10, r11
0x1800153dc  mov     r11, gs:10h
0x1800153e5  cmp     r10, r11
0x1800153e8  jnb     short cs20
0x1800153ea  and     r10w, 0F000h
0x1800153f0  lea     r11, [r11-1000h]
0x1800153f7  mov     byte ptr [r11], 0
0x1800153fb  cmp     r10, r11
0x1800153fe  jnz     short cs10
0x180015400  mov     r10, [rsp+10h+var_10]
0x180015404  mov     r11, [rsp+10h+var_8]
0x180015409  add     rsp, 10h
0x18001540d  retn
```
