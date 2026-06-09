# _alloca_probe

- ea: `0x180015990`
- end: `0x1800159de`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d90`
- `0x180004580`
- `0x180004a38`
- `0x180004b60`
- `0x18000a2b0`
- `0x18000a4a4`
- `0x18000a53c`
- `0x18000a6c8`

## callees

- `0x180015990`

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
0x180015990  sub     rsp, 10h
0x180015994  mov     [rsp+10h+var_10], r10
0x180015998  mov     [rsp+10h+var_8], r11
0x18001599d  xor     r11, r11
0x1800159a0  lea     r10, [rsp+10h+arg_0]
0x1800159a5  sub     r10, rax
0x1800159a8  cmovb   r10, r11
0x1800159ac  mov     r11, gs:10h
0x1800159b5  cmp     r10, r11
0x1800159b8  jnb     short cs20
0x1800159ba  and     r10w, 0F000h
0x1800159c0  lea     r11, [r11-1000h]
0x1800159c7  mov     byte ptr [r11], 0
0x1800159cb  cmp     r10, r11
0x1800159ce  jnz     short cs10
0x1800159d0  mov     r10, [rsp+10h+var_10]
0x1800159d4  mov     r11, [rsp+10h+var_8]
0x1800159d9  add     rsp, 10h
0x1800159dd  retn
```
