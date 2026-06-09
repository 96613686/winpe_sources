# _alloca_probe

- ea: `0x18000d080`
- end: `0x18000d0cd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000701c`
- `0x180007284`
- `0x180007520`
- `0x18000a9a0`
- `0x18000c154`

## callees

- `0x18000d080`

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
0x18000d080  sub     rsp, 10h
0x18000d084  mov     [rsp+10h+var_10], r10
0x18000d088  mov     [rsp+10h+var_8], r11
0x18000d08d  xor     r11, r11
0x18000d090  lea     r10, [rsp+10h+arg_0]
0x18000d095  sub     r10, rax
0x18000d098  cmovb   r10, r11
0x18000d09c  mov     r11, gs:10h
0x18000d0a5  cmp     r10, r11
0x18000d0a8  jnb     short loc_18000D0BF
0x18000d0aa  and     r10w, 0F000h
0x18000d0b0  lea     r11, [r11-1000h]
0x18000d0b7  test    [r11], r11b
0x18000d0ba  cmp     r10, r11
0x18000d0bd  jb      short loc_18000D0B0
0x18000d0bf  mov     r10, [rsp+10h+var_10]
0x18000d0c3  mov     r11, [rsp+10h+var_8]
0x18000d0c8  add     rsp, 10h
0x18000d0cc  retn
```
