# _alloca_probe

- ea: `0x1800102e0`
- end: `0x18001032d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x1800011a0`
- `0x1800023e0`
- `0x1800032e0`
- `0x180003750`
- `0x180003af0`
- `0x180003dbc`
- `0x180005adc`
- `0x180007690`
- `0x180007c00`
- `0x180008600`
- `0x1800087c0`
- `0x180008930`
- `0x180008ef4`
- `0x180009cf0`
- `0x18000a820`
- `0x18000a900`
- `0x18000a9e0`
- `0x18000ac70`
- `0x18000ada0`
- `0x18000ae90`
- `0x18000afb0`
- `0x18000cc80`
- `0x18000d940`
- `0x18000dcc0`
- `0x18000f0a0`
- `0x18000f178`
- `0x18000f2cc`

## callees

- `0x1800102e0`

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
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x1800102e0  sub     rsp, 10h
0x1800102e4  mov     [rsp+10h+var_10], r10
0x1800102e8  mov     [rsp+10h+var_8], r11
0x1800102ed  xor     r11, r11
0x1800102f0  lea     r10, [rsp+10h+arg_0]
0x1800102f5  sub     r10, rax
0x1800102f8  cmovb   r10, r11
0x1800102fc  mov     r11, gs:10h
0x180010305  cmp     r10, r11
0x180010308  jnb     short loc_18001031F
0x18001030a  and     r10w, 0F000h
0x180010310  lea     r11, [r11-1000h]
0x180010317  test    [r11], r11b
0x18001031a  cmp     r10, r11
0x18001031d  jb      short loc_180010310
0x18001031f  mov     r10, [rsp+10h+var_10]
0x180010323  mov     r11, [rsp+10h+var_8]
0x180010328  add     rsp, 10h
0x18001032c  retn
```
