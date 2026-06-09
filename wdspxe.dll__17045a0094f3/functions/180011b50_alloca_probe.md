# _alloca_probe

- ea: `0x180011b50`
- end: `0x180011b9d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009408`
- `0x180009680`
- `0x180009930`
- `0x18000dcdc`
- `0x180010d98`

## callees

- `0x180011b50`

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
0x180011b50  sub     rsp, 10h
0x180011b54  mov     [rsp+10h+var_10], r10
0x180011b58  mov     [rsp+10h+var_8], r11
0x180011b5d  xor     r11, r11
0x180011b60  lea     r10, [rsp+10h+arg_0]
0x180011b65  sub     r10, rax
0x180011b68  cmovb   r10, r11
0x180011b6c  mov     r11, gs:10h
0x180011b75  cmp     r10, r11
0x180011b78  jnb     short loc_180011B8F
0x180011b7a  and     r10w, 0F000h
0x180011b80  lea     r11, [r11-1000h]
0x180011b87  test    [r11], r11b
0x180011b8a  cmp     r10, r11
0x180011b8d  jb      short loc_180011B80
0x180011b8f  mov     r10, [rsp+10h+var_10]
0x180011b93  mov     r11, [rsp+10h+var_8]
0x180011b98  add     rsp, 10h
0x180011b9c  retn
```
