# _alloca_probe

- ea: `0x18001b840`
- end: `0x18001b88d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aa34`
- `0x18000ac9c`
- `0x18000af30`
- `0x18000e75c`
- `0x18001005c`

## callees

- `0x18001b840`

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
0x18001b840  sub     rsp, 10h
0x18001b844  mov     [rsp+10h+var_10], r10
0x18001b848  mov     [rsp+10h+var_8], r11
0x18001b84d  xor     r11, r11
0x18001b850  lea     r10, [rsp+10h+arg_0]
0x18001b855  sub     r10, rax
0x18001b858  cmovb   r10, r11
0x18001b85c  mov     r11, gs:10h
0x18001b865  cmp     r10, r11
0x18001b868  jnb     short loc_18001B87F
0x18001b86a  and     r10w, 0F000h
0x18001b870  lea     r11, [r11-1000h]
0x18001b877  test    [r11], r11b
0x18001b87a  cmp     r10, r11
0x18001b87d  jb      short loc_18001B870
0x18001b87f  mov     r10, [rsp+10h+var_10]
0x18001b883  mov     r11, [rsp+10h+var_8]
0x18001b888  add     rsp, 10h
0x18001b88c  retn
```
