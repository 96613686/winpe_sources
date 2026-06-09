# _alloca_probe

- ea: `0x14000d280`
- end: `0x14000d2cd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400046f0`
- `0x140004958`
- `0x140004bf4`
- `0x140008338`
- `0x14000a178`

## callees

- `0x14000d280`

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
0x14000d280  sub     rsp, 10h
0x14000d284  mov     [rsp+10h+var_10], r10
0x14000d288  mov     [rsp+10h+var_8], r11
0x14000d28d  xor     r11, r11
0x14000d290  lea     r10, [rsp+10h+arg_0]
0x14000d295  sub     r10, rax
0x14000d298  cmovb   r10, r11
0x14000d29c  mov     r11, gs:10h
0x14000d2a5  cmp     r10, r11
0x14000d2a8  jnb     short loc_14000D2BF
0x14000d2aa  and     r10w, 0F000h
0x14000d2b0  lea     r11, [r11-1000h]
0x14000d2b7  test    [r11], r11b
0x14000d2ba  cmp     r10, r11
0x14000d2bd  jb      short loc_14000D2B0
0x14000d2bf  mov     r10, [rsp+10h+var_10]
0x14000d2c3  mov     r11, [rsp+10h+var_8]
0x14000d2c8  add     rsp, 10h
0x14000d2cc  retn
```
