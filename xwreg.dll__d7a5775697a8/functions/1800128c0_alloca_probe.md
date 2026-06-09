# _alloca_probe

- ea: `0x1800128c0`
- end: `0x18001290d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033ac`
- `0x18000527c`
- `0x1800055a0`
- `0x180005e5c`

## callees

- `0x1800128c0`

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
0x1800128c0  sub     rsp, 10h
0x1800128c4  mov     [rsp+10h+var_10], r10
0x1800128c8  mov     [rsp+10h+var_8], r11
0x1800128cd  xor     r11, r11
0x1800128d0  lea     r10, [rsp+10h+arg_0]
0x1800128d5  sub     r10, rax
0x1800128d8  cmovb   r10, r11
0x1800128dc  mov     r11, gs:10h
0x1800128e5  cmp     r10, r11
0x1800128e8  jnb     short loc_1800128FF
0x1800128ea  and     r10w, 0F000h
0x1800128f0  lea     r11, [r11-1000h]
0x1800128f7  test    [r11], r11b
0x1800128fa  cmp     r10, r11
0x1800128fd  jb      short loc_1800128F0
0x1800128ff  mov     r10, [rsp+10h+var_10]
0x180012903  mov     r11, [rsp+10h+var_8]
0x180012908  add     rsp, 10h
0x18001290c  retn
```
