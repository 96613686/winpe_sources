# _alloca_probe

- ea: `0x180004ee0`
- end: `0x180004f2e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002164`
- `0x180003688`
- `0x180004730`

## callees

- `0x180004ee0`

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
0x180004ee0  sub     rsp, 10h
0x180004ee4  mov     [rsp+10h+var_10], r10
0x180004ee8  mov     [rsp+10h+var_8], r11
0x180004eed  xor     r11, r11
0x180004ef0  lea     r10, [rsp+10h+arg_0]
0x180004ef5  sub     r10, rax
0x180004ef8  cmovb   r10, r11
0x180004efc  mov     r11, gs:10h
0x180004f05  cmp     r10, r11
0x180004f08  jnb     short cs20
0x180004f0a  and     r10w, 0F000h
0x180004f10  lea     r11, [r11-1000h]
0x180004f17  mov     byte ptr [r11], 0
0x180004f1b  cmp     r10, r11
0x180004f1e  jnz     short cs10
0x180004f20  mov     r10, [rsp+10h+var_10]
0x180004f24  mov     r11, [rsp+10h+var_8]
0x180004f29  add     rsp, 10h
0x180004f2d  retn
```
