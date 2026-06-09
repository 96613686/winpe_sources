# CngRsa32Compat_rc4

- ea: `0x180007d1c`
- end: `0x180007d7f`
- name: `CngRsa32Compat_rc4`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007e00`
- `0x180009a34`
- `0x180009fe8`

## callees

- `0x180007d1c`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x180007d69`
- `bcrypt!BCryptEncrypt` at `0x180007d69`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_rc4(void **a1, ULONG a2, UCHAR *a3)
{
  void *v3; // rcx
  NTSTATUS result; // eax
  ULONG v5; // [rsp+68h] [rbp+10h] BYREF

  v5 = a2;
  v3 = *a1;
  v5 = 0;
  result = BCryptEncrypt(v3, a3, 0x204u, 0, 0, 0, a3, 0x204u, &v5, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x180007d1c  mov     [rsp+arg_8], edx
0x180007d20  mov     r11, rsp
0x180007d23  sub     rsp, 58h
0x180007d27  mov     rcx, [rcx]; hKey
0x180007d2a  lea     rdx, [r11+10h]
0x180007d2e  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180007d36  mov     rax, r8
0x180007d39  mov     [r11-18h], rdx
0x180007d3d  mov     r8d, 204h; cbInput
0x180007d43  mov     [r11-20h], r8d
0x180007d47  xor     r9d, r9d; pPaddingInfo
0x180007d4a  mov     [r11-28h], rax
0x180007d4e  mov     rdx, rax; pbInput
0x180007d51  mov     [rsp+58h+cbIV], 0; cbIV
0x180007d59  mov     qword ptr [r11-38h], 0
0x180007d61  mov     [rsp+58h+arg_8], 0
0x180007d69  call    cs:__imp_BCryptEncrypt
0x180007d6f  test    eax, eax
0x180007d71  jns     short loc_180007D7A
0x180007d73  mov     ecx, 7
0x180007d78  int     29h; Win8: RtlFailFast(ecx)
0x180007d7a  add     rsp, 58h
0x180007d7e  retn
```
