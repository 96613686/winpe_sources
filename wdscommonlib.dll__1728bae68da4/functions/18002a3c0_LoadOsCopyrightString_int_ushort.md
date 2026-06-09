# LoadOsCopyrightString(int,ushort * *)

- ea: `0x18002a3c0`
- end: `0x18002a4c2`
- name: `?LoadOsCopyrightString@@YAKHPEAPEAG@Z`
- size: `258`
- prototype: `unsigned int __fastcall(int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180015830`
- `0x18002a3c0`
- `0x180030362`
- `0x180030390`
- `0x180030450`

## import_xrefs

- `WINBRAND!BrandingLoadString` at `0x18002a423`
- `WINBRAND!BrandingLoadString` at `0x18002a423`
- `KERNEL32!GetLastError` at `0x18002a4b4`
- `KERNEL32!GetLastError` at `0x18002a4b4`

## string_xrefs

- `0x18002a437`: `Copyright (c) Microsoft Corporation. All rights reserved.`

## pseudocode

```c
DWORD __fastcall LoadOsCopyrightString(int a1, unsigned __int16 **a2)
{
  __int64 v4; // rbx
  unsigned __int16 *v5; // rcx
  unsigned __int16 v6; // ax
  unsigned __int16 *v7; // rax
  unsigned __int16 v9[2]; // [rsp+20h] [rbp-2018h] BYREF
  _BYTE v10[8188]; // [rsp+24h] [rbp-2014h] BYREF

  *(_DWORD *)v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  v4 = 4096;
  if ( (unsigned int)((__int64 (__fastcall *)(const wchar_t *, __int64, unsigned __int16 *, __int64))BrandingLoadString)(
                       L"Basebrd",
                       14,
                       v9,
                       4096) )
    return DuplicateStringWBom(v9, 0, a2);
  if ( a1 )
  {
    v5 = v9;
    do
    {
      if ( v4 == -2147479550 )
        break;
      v6 = *(unsigned __int16 *)((char *)v5
                               + (char *)L"Copyright (c) Microsoft Corporation. All rights reserved."
                               - (char *)v9);
      if ( !v6 )
        break;
      *v5++ = v6;
      --v4;
    }
    while ( v4 );
    v7 = v5 - 1;
    if ( v4 )
      v7 = v5;
    *v7 = 0;
    return DuplicateStringWBom(v9, 0, a2);
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18002a3c0  mov     [rsp+arg_0], rbx
0x18002a3c5  mov     [rsp+arg_10], rbp
0x18002a3ca  mov     [rsp+arg_18], rsi
0x18002a3cf  push    rdi
0x18002a3d0  mov     eax, 2030h
0x18002a3d5  call    _alloca_probe
0x18002a3da  sub     rsp, rax
0x18002a3dd  mov     rax, cs:__security_cookie
0x18002a3e4  xor     rax, rsp
0x18002a3e7  mov     [rsp+2038h+var_18], rax
0x18002a3ef  mov     rsi, rdx
0x18002a3f2  mov     edi, ecx
0x18002a3f4  xor     ebp, ebp
0x18002a3f6  lea     rcx, [rsp+2038h+var_2014]; void *
0x18002a3fb  xor     edx, edx; Val
0x18002a3fd  mov     dword ptr [rsp+2038h+var_2018], ebp
0x18002a401  mov     r8d, 1FFCh; Size
0x18002a407  call    memset_0
0x18002a40c  mov     ebx, 1000h
0x18002a411  lea     r8, [rsp+2038h+var_2018]
0x18002a416  mov     r9d, ebx
0x18002a419  lea     edx, [rbp+0Eh]
0x18002a41c  lea     rcx, aBasebrd; "Basebrd"
0x18002a423  call    cs:__imp_BrandingLoadString
0x18002a42a  nop     dword ptr [rax+rax+00h]
0x18002a42f  test    eax, eax
0x18002a431  jnz     short loc_18002A47B
0x18002a433  test    edi, edi
0x18002a435  jz      short loc_18002A4B4
0x18002a437  lea     rdx, aCopyrightCMicr; "Copyright (c) Microsoft Corporation. Al"...
0x18002a43e  lea     rax, [rsp+2038h+var_2018]
0x18002a443  sub     rdx, rax
0x18002a446  lea     rcx, [rsp+2038h+var_2018]
0x18002a44b  lea     rax, [rbx+7FFFEFFEh]
0x18002a452  test    rax, rax
0x18002a455  jz      short loc_18002A46D
0x18002a457  movzx   eax, word ptr [rdx+rcx]
0x18002a45b  test    ax, ax
0x18002a45e  jz      short loc_18002A46D
0x18002a460  mov     [rcx], ax
0x18002a463  add     rcx, 2
0x18002a467  sub     rbx, 1
0x18002a46b  jnz     short loc_18002A44B
0x18002a46d  test    rbx, rbx
0x18002a470  lea     rax, [rcx-2]
0x18002a474  cmovnz  rax, rcx
0x18002a478  mov     [rax], bp
0x18002a47b  mov     r8, rsi; unsigned __int16 **
0x18002a47e  lea     rcx, [rsp+2038h+var_2018]; unsigned __int16 *
0x18002a483  xor     edx, edx; int
0x18002a485  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x18002a48a  mov     rcx, [rsp+2038h+var_18]
0x18002a492  xor     rcx, rsp; StackCookie
0x18002a495  call    __security_check_cookie
0x18002a49a  lea     r11, [rsp+2038h+var_8]
0x18002a4a2  mov     rbx, [r11+10h]
0x18002a4a6  mov     rbp, [r11+20h]
0x18002a4aa  mov     rsi, [r11+28h]
0x18002a4ae  mov     rsp, r11
0x18002a4b1  pop     rdi
0x18002a4b2  retn
0x18002a4b4  call    cs:__imp_GetLastError
0x18002a4bb  nop     dword ptr [rax+rax+00h]
0x18002a4c0  jmp     short loc_18002A48A
```
