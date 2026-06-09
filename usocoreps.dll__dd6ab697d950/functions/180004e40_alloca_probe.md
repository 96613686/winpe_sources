# _alloca_probe

- ea: `0x180004e40`
- end: `0x180004e8e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000271c`
- `0x1800037e8`
- `0x180003b5c`
- `0x18000430c`

## callees

- `0x180004e40`

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
0x180004e40  sub     rsp, 10h
0x180004e44  mov     [rsp+10h+var_10], r10
0x180004e48  mov     [rsp+10h+var_8], r11
0x180004e4d  xor     r11, r11
0x180004e50  lea     r10, [rsp+10h+arg_0]
0x180004e55  sub     r10, rax
0x180004e58  cmovb   r10, r11
0x180004e5c  mov     r11, gs:10h
0x180004e65  cmp     r10, r11
0x180004e68  jnb     short cs20
0x180004e6a  and     r10w, 0F000h
0x180004e70  lea     r11, [r11-1000h]
0x180004e77  mov     byte ptr [r11], 0
0x180004e7b  cmp     r10, r11
0x180004e7e  jnz     short cs10
0x180004e80  mov     r10, [rsp+10h+var_10]
0x180004e84  mov     r11, [rsp+10h+var_8]
0x180004e89  add     rsp, 10h
0x180004e8d  retn
```
