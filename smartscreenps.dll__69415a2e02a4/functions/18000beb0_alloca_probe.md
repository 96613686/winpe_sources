# _alloca_probe

- ea: `0x18000beb0`
- end: `0x18000befe`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ecc`
- `0x180006f7c`
- `0x180007224`
- `0x180009e50`
- `0x18000a298`

## callees

- `0x18000beb0`

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
0x18000beb0  sub     rsp, 10h
0x18000beb4  mov     [rsp+10h+var_10], r10
0x18000beb8  mov     [rsp+10h+var_8], r11
0x18000bebd  xor     r11, r11
0x18000bec0  lea     r10, [rsp+10h+arg_0]
0x18000bec5  sub     r10, rax
0x18000bec8  cmovb   r10, r11
0x18000becc  mov     r11, gs:10h
0x18000bed5  cmp     r10, r11
0x18000bed8  jnb     short cs20
0x18000beda  and     r10w, 0F000h
0x18000bee0  lea     r11, [r11-1000h]
0x18000bee7  mov     byte ptr [r11], 0
0x18000beeb  cmp     r10, r11
0x18000beee  jnz     short cs10
0x18000bef0  mov     r10, [rsp+10h+var_10]
0x18000bef4  mov     r11, [rsp+10h+var_8]
0x18000bef9  add     rsp, 10h
0x18000befd  retn
```
