# WdsCreateExtendedPath

- ea: `0x18001bef0`
- end: `0x18001c056`
- name: `WdsCreateExtendedPath`
- size: `358`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001a0f8`
- `0x18001c060`
- `0x18001c660`
- `0x18001c6f0`

## callees

- `0x180017330`
- `0x18001a880`
- `0x18001b0cc`
- `0x18001bef0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001bf91`
- `msvcrt!_wcsnicmp` at `0x18001bf91`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c035`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c035`

## pseudocode

```c
__int64 __fastcall WdsCreateExtendedPath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rcx
  unsigned __int16 *v5; // rax
  __int64 v6; // rcx
  signed int v7; // ebx
  unsigned __int64 v8; // rbp
  wchar_t *v9; // r14
  signed int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int16 *v14; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  v14 = 0;
  if ( !a1 || !a2 )
  {
    v7 = -2147024809;
LABEL_26:
    if ( v3 )
      operator delete(v3);
    return (unsigned int)v7;
  }
  v5 = a1;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = v6 == 0 ? 0x80070057 : 0;
  v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( v6 )
  {
    if ( v8 < 2 )
      return (unsigned int)-2147024735;
    v9 = (wchar_t *)L"\\\\?\\";
    if ( v8 >= 4 && !_wcsnicmp(a1, L"\\\\?\\", 4u) )
    {
      if ( v8 == 4 )
        return (unsigned int)-2147024735;
      v7 = WcsDupHr(a1, &v14);
      if ( v7 >= 0 )
      {
LABEL_13:
        *a2 = v14;
        return (unsigned int)v7;
      }
LABEL_24:
      v3 = v14;
      goto LABEL_26;
    }
    if ( *a1 == 92 )
    {
      if ( a1[1] != 92 )
        return (unsigned int)-2147024809;
      v9 = (wchar_t *)L"\\\\?\\UNC";
      a1 += 2;
    }
    else if ( a1[1] != 58 )
    {
      return (unsigned int)-2147024809;
    }
    v10 = ConcatenatePaths(v9, (__int64)a1, &v14);
    if ( !(unsigned int)ElValidateWin32_8(v10, v11, v12, 0xDA7u) )
      goto LABEL_13;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    else
      v7 = v10;
    if ( v7 < 0 )
      goto LABEL_24;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001bef0  mov     [rsp+arg_8], rbx
0x18001bef5  push    rbp
0x18001bef6  push    rdi
0x18001bef7  push    r12
0x18001bef9  push    r14
0x18001befb  push    r15
0x18001befd  sub     rsp, 20h
0x18001bf01  xor     r12d, r12d
0x18001bf04  mov     rdi, rcx
0x18001bf07  mov     ecx, r12d
0x18001bf0a  mov     r15, rdx
0x18001bf0d  mov     [rsp+48h+arg_10], rcx
0x18001bf12  test    rdi, rdi
0x18001bf15  jz      loc_18001C02B
0x18001bf1b  test    rdx, rdx
0x18001bf1e  jz      loc_18001C02B
0x18001bf24  mov     r8d, 7FFFFFFFh
0x18001bf2a  mov     rax, rdi
0x18001bf2d  mov     ecx, r8d
0x18001bf30  cmp     [rax], r12w
0x18001bf34  jz      short loc_18001BF40
0x18001bf36  add     rax, 2
0x18001bf3a  sub     rcx, 1
0x18001bf3e  jnz     short loc_18001BF30
0x18001bf40  mov     rax, rcx
0x18001bf43  neg     rax
0x18001bf46  mov     rax, rcx
0x18001bf49  sbb     ebx, ebx
0x18001bf4b  sub     r8, rcx
0x18001bf4e  not     ebx
0x18001bf50  and     ebx, 80070057h
0x18001bf56  neg     rax
0x18001bf59  sbb     rbp, rbp
0x18001bf5c  and     rbp, r8
0x18001bf5f  test    rcx, rcx
0x18001bf62  jz      loc_18001C041
0x18001bf68  cmp     rbp, 2
0x18001bf6c  jnb     short loc_18001BF78
0x18001bf6e  mov     ebx, 800700A1h
0x18001bf73  jmp     loc_18001C041
0x18001bf78  lea     r14, asc_180036A98; "\\\\?\\"
0x18001bf7f  cmp     rbp, 4
0x18001bf83  jb      short loc_18001BFC4
0x18001bf85  mov     r8d, 4; MaxCount
0x18001bf8b  mov     rdx, r14; String2
0x18001bf8e  mov     rcx, rdi; String1
0x18001bf91  call    cs:__imp__wcsnicmp
0x18001bf98  nop     dword ptr [rax+rax+00h]
0x18001bf9d  test    eax, eax
0x18001bf9f  jnz     short loc_18001BFC4
0x18001bfa1  cmp     rbp, 4
0x18001bfa5  jz      short loc_18001BF6E
0x18001bfa7  lea     rdx, [rsp+48h+arg_10]; unsigned __int16 **
0x18001bfac  mov     rcx, rdi; unsigned __int16 *
0x18001bfaf  call    ?WcsDupHr@@YAJPEBGPEAPEAG@Z; WcsDupHr(ushort const *,ushort * *)
0x18001bfb4  mov     ebx, eax
0x18001bfb6  test    eax, eax
0x18001bfb8  js      short loc_18001C024
0x18001bfba  mov     rax, [rsp+48h+arg_10]
0x18001bfbf  mov     [r15], rax
0x18001bfc2  jmp     short loc_18001C041
0x18001bfc4  cmp     word ptr [rdi], 5Ch ; '\'
0x18001bfc8  jnz     short loc_18001BFE5
0x18001bfca  cmp     word ptr [rdi+2], 5Ch ; '\'
0x18001bfcf  jz      short loc_18001BFD8
0x18001bfd1  mov     ebx, 80070057h
0x18001bfd6  jmp     short loc_18001C041
0x18001bfd8  lea     r14, aUnc; "\\\\?\\UNC"
0x18001bfdf  add     rdi, 4
0x18001bfe3  jmp     short loc_18001BFEC
0x18001bfe5  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001bfea  jnz     short loc_18001BFD1
0x18001bfec  lea     r8, [rsp+48h+arg_10]
0x18001bff1  mov     rdx, rdi
0x18001bff4  mov     rcx, r14
0x18001bff7  call    ConcatenatePaths
0x18001bffc  mov     r9d, 0DA7h
0x18001c002  mov     ecx, eax
0x18001c004  mov     edi, eax
0x18001c006  call    ElValidateWin32_8
0x18001c00b  test    eax, eax
0x18001c00d  jz      short loc_18001BFBA
0x18001c00f  test    edi, edi
0x18001c011  jg      short loc_18001C017
0x18001c013  mov     ebx, edi
0x18001c015  jmp     short loc_18001C020
0x18001c017  movzx   ebx, di
0x18001c01a  or      ebx, 80070000h
0x18001c020  test    ebx, ebx
0x18001c022  jns     short loc_18001C041
0x18001c024  mov     rcx, [rsp+48h+arg_10]
0x18001c029  jmp     short loc_18001C030
0x18001c02b  mov     ebx, 80070057h
0x18001c030  test    rcx, rcx
0x18001c033  jz      short loc_18001C041
0x18001c035  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c03c  nop     dword ptr [rax+rax+00h]
0x18001c041  mov     eax, ebx
0x18001c043  mov     rbx, [rsp+48h+arg_8]
0x18001c048  add     rsp, 20h
0x18001c04c  pop     r15
0x18001c04e  pop     r14
0x18001c050  pop     r12
0x18001c052  pop     rdi
0x18001c053  pop     rbp
0x18001c054  retn
```
