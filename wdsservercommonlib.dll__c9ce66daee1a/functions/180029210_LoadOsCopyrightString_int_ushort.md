# LoadOsCopyrightString(int,ushort * *)

- ea: `0x180029210`
- end: `0x180029312`
- name: `?LoadOsCopyrightString@@YAKHPEAPEAG@Z`
- size: `258`
- prototype: `unsigned int __fastcall(int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180014b10`
- `0x180029210`
- `0x18002f3ba`
- `0x18002f3e0`
- `0x18002f4a0`

## import_xrefs

- `WINBRAND!BrandingLoadString` at `0x180029273`
- `WINBRAND!BrandingLoadString` at `0x180029273`
- `KERNEL32!GetLastError` at `0x180029304`
- `KERNEL32!GetLastError` at `0x180029304`

## string_xrefs

- `0x180029287`: `Copyright (c) Microsoft Corporation. All rights reserved.`

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
0x180029210  mov     [rsp+arg_0], rbx
0x180029215  mov     [rsp+arg_10], rbp
0x18002921a  mov     [rsp+arg_18], rsi
0x18002921f  push    rdi
0x180029220  mov     eax, 2030h
0x180029225  call    _alloca_probe
0x18002922a  sub     rsp, rax
0x18002922d  mov     rax, cs:__security_cookie
0x180029234  xor     rax, rsp
0x180029237  mov     [rsp+2038h+var_18], rax
0x18002923f  mov     rsi, rdx
0x180029242  mov     edi, ecx
0x180029244  xor     ebp, ebp
0x180029246  lea     rcx, [rsp+2038h+var_2014]; void *
0x18002924b  xor     edx, edx; Val
0x18002924d  mov     dword ptr [rsp+2038h+var_2018], ebp
0x180029251  mov     r8d, 1FFCh; Size
0x180029257  call    memset_0
0x18002925c  mov     ebx, 1000h
0x180029261  lea     r8, [rsp+2038h+var_2018]
0x180029266  mov     r9d, ebx
0x180029269  lea     edx, [rbp+0Eh]
0x18002926c  lea     rcx, aBasebrd; "Basebrd"
0x180029273  call    cs:__imp_BrandingLoadString
0x18002927a  nop     dword ptr [rax+rax+00h]
0x18002927f  test    eax, eax
0x180029281  jnz     short loc_1800292CB
0x180029283  test    edi, edi
0x180029285  jz      short loc_180029304
0x180029287  lea     rdx, aCopyrightCMicr; "Copyright (c) Microsoft Corporation. Al"...
0x18002928e  lea     rax, [rsp+2038h+var_2018]
0x180029293  sub     rdx, rax
0x180029296  lea     rcx, [rsp+2038h+var_2018]
0x18002929b  lea     rax, [rbx+7FFFEFFEh]
0x1800292a2  test    rax, rax
0x1800292a5  jz      short loc_1800292BD
0x1800292a7  movzx   eax, word ptr [rdx+rcx]
0x1800292ab  test    ax, ax
0x1800292ae  jz      short loc_1800292BD
0x1800292b0  mov     [rcx], ax
0x1800292b3  add     rcx, 2
0x1800292b7  sub     rbx, 1
0x1800292bb  jnz     short loc_18002929B
0x1800292bd  test    rbx, rbx
0x1800292c0  lea     rax, [rcx-2]
0x1800292c4  cmovnz  rax, rcx
0x1800292c8  mov     [rax], bp
0x1800292cb  mov     r8, rsi; unsigned __int16 **
0x1800292ce  lea     rcx, [rsp+2038h+var_2018]; unsigned __int16 *
0x1800292d3  xor     edx, edx; int
0x1800292d5  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x1800292da  mov     rcx, [rsp+2038h+var_18]
0x1800292e2  xor     rcx, rsp; StackCookie
0x1800292e5  call    __security_check_cookie
0x1800292ea  lea     r11, [rsp+2038h+var_8]
0x1800292f2  mov     rbx, [r11+10h]
0x1800292f6  mov     rbp, [r11+20h]
0x1800292fa  mov     rsi, [r11+28h]
0x1800292fe  mov     rsp, r11
0x180029301  pop     rdi
0x180029302  retn
0x180029304  call    cs:__imp_GetLastError
0x18002930b  nop     dword ptr [rax+rax+00h]
0x180029310  jmp     short loc_1800292DA
```
