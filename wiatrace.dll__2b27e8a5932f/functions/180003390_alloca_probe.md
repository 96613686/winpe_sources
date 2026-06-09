# _alloca_probe

- ea: `0x180003390`
- end: `0x1800033de`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001300`

## callees

- `0x180003390`

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
0x180003390  sub     rsp, 10h
0x180003394  mov     [rsp+10h+var_10], r10
0x180003398  mov     [rsp+10h+var_8], r11
0x18000339d  xor     r11, r11
0x1800033a0  lea     r10, [rsp+10h+arg_0]
0x1800033a5  sub     r10, rax
0x1800033a8  cmovb   r10, r11
0x1800033ac  mov     r11, gs:10h
0x1800033b5  cmp     r10, r11
0x1800033b8  jnb     short cs20
0x1800033ba  and     r10w, 0F000h
0x1800033c0  lea     r11, [r11-1000h]
0x1800033c7  mov     byte ptr [r11], 0
0x1800033cb  cmp     r10, r11
0x1800033ce  jnz     short cs10
0x1800033d0  mov     r10, [rsp+10h+var_10]
0x1800033d4  mov     r11, [rsp+10h+var_8]
0x1800033d9  add     rsp, 10h
0x1800033dd  retn
```
