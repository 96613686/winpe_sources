# _alloca_probe

- ea: `0x180015880`
- end: `0x1800158cd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180007534`
- `0x180008ce8`
- `0x18000902c`
- `0x1800098b4`
- `0x18000fa50`
- `0x18000fcb8`
- `0x18000ff54`
- `0x180013468`
- `0x180014ae0`

## callees

- `0x180015880`

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
0x180015880  sub     rsp, 10h
0x180015884  mov     [rsp+10h+var_10], r10
0x180015888  mov     [rsp+10h+var_8], r11
0x18001588d  xor     r11, r11
0x180015890  lea     r10, [rsp+10h+arg_0]
0x180015895  sub     r10, rax
0x180015898  cmovb   r10, r11
0x18001589c  mov     r11, gs:10h
0x1800158a5  cmp     r10, r11
0x1800158a8  jnb     short loc_1800158BF
0x1800158aa  and     r10w, 0F000h
0x1800158b0  lea     r11, [r11-1000h]
0x1800158b7  test    [r11], r11b
0x1800158ba  cmp     r10, r11
0x1800158bd  jb      short loc_1800158B0
0x1800158bf  mov     r10, [rsp+10h+var_10]
0x1800158c3  mov     r11, [rsp+10h+var_8]
0x1800158c8  add     rsp, 10h
0x1800158cc  retn
```
