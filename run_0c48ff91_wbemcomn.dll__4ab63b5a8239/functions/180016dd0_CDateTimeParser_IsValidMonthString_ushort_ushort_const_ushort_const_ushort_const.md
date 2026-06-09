# CDateTimeParser::IsValidMonthString(ushort *,ushort const *,ushort * * const,ushort * * const)

- ea: `0x180016dd0`
- end: `0x180016ea4`
- name: `?IsValidMonthString@CDateTimeParser@@IEAAHPEAGPEBGQEAPEAG2@Z`
- size: `212`
- prototype: `int(CDateTimeParser *__hidden this, unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **const, unsigned __int16 **const)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016c90`
- `0x180016eb0`
- `0x180017270`
- `0x1800177c0`
- `0x180017940`
- `0x180017b30`
- `0x180018d10`
- `0x180019430`

## callees

- `0x180016dd0`
- `0x18002ea8c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016e3d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016e64`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016e3d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016e64`

## pseudocode

```c
__int64 __fastcall CDateTimeParser::IsValidMonthString(
        CDateTimeParser *this,
        unsigned __int16 *a2,
        wchar_t *a3,
        unsigned __int16 **const a4,
        unsigned __int16 **const a5)
{
  wchar_t *v7; // rax
  int v8; // ebx
  const WCHAR *lpString2; // rdi
  WCHAR i; // ax

  v7 = wcstok_mvcrt_legacy_two_parameter_form(a2, a3, (wchar_t **)a3);
  v8 = 0;
  lpString2 = v7;
  if ( !v7 )
    return 2;
  for ( i = *v7; i == 32; i = *lpString2 )
    ++lpString2;
  if ( !i )
    return 2;
  while ( v8 < 12 )
  {
    if ( CompareStringW(0x7Fu, 1u, a5[v8], -1, lpString2, -1) == 2
      || CompareStringW(0x7Fu, 1u, a4[v8], -1, lpString2, -1) == 2 )
    {
      *((_BYTE *)this + 229) = v8 + 1;
      return 0;
    }
    ++v8;
  }
  return 1;
}

```

## disassembly

```asm
0x180016dd0  push    rbx
0x180016dd2  push    rbp
0x180016dd3  push    rsi
0x180016dd4  push    rdi
0x180016dd5  push    r14
0x180016dd7  push    r15
0x180016dd9  sub     rsp, 38h
0x180016ddd  mov     rax, rdx
0x180016de0  mov     rbp, rcx
0x180016de3  mov     rcx, rax; String
0x180016de6  mov     rdx, r8; Delimiter
0x180016de9  mov     r15, r9
0x180016dec  call    wcstok_mvcrt_legacy_two_parameter_form
0x180016df1  xor     ebx, ebx
0x180016df3  mov     rdi, rax
0x180016df6  test    rax, rax
0x180016df9  jz      loc_180016E8A
0x180016dff  movzx   eax, word ptr [rax]
0x180016e02  cmp     ax, 20h ; ' '
0x180016e06  jz      loc_180016E91
0x180016e0c  test    ax, ax
0x180016e0f  jz      short loc_180016E8A
0x180016e11  mov     r14, [rsp+68h+arg_20]
0x180016e19  cmp     ebx, 0Ch
0x180016e1c  jge     short loc_180016E9D
0x180016e1e  or      r9d, 0FFFFFFFFh; cchCount1
0x180016e22  movsxd  rsi, ebx
0x180016e25  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180016e2d  mov     [rsp+68h+lpString2], rdi; lpString2
0x180016e32  mov     r8, [r14+rsi*8]; lpString1
0x180016e36  lea     edx, [r9+2]; dwCmpFlags
0x180016e3a  lea     ecx, [rdx+7Eh]; Locale
0x180016e3d  call    cs:__imp_CompareStringW
0x180016e43  cmp     eax, 2
0x180016e46  jz      short loc_180016E73
0x180016e48  mov     r8, [r15+rsi*8]; lpString1
0x180016e4c  or      r9d, 0FFFFFFFFh; cchCount1
0x180016e50  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180016e58  mov     [rsp+68h+lpString2], rdi; lpString2
0x180016e5d  lea     edx, [r9+2]; dwCmpFlags
0x180016e61  lea     ecx, [rdx+7Eh]; Locale
0x180016e64  call    cs:__imp_CompareStringW
0x180016e6a  cmp     eax, 2
0x180016e6d  jz      short loc_180016E73
0x180016e6f  inc     ebx
0x180016e71  jmp     short loc_180016E19
0x180016e73  inc     bl
0x180016e75  mov     [rbp+0E5h], bl
0x180016e7b  xor     eax, eax
0x180016e7d  add     rsp, 38h
0x180016e81  pop     r15
0x180016e83  pop     r14
0x180016e85  pop     rdi
0x180016e86  pop     rsi
0x180016e87  pop     rbp
0x180016e88  pop     rbx
0x180016e89  retn
0x180016e8a  mov     eax, 2
0x180016e8f  jmp     short loc_180016E7D
0x180016e91  add     rdi, 2
0x180016e95  movzx   eax, word ptr [rdi]
0x180016e98  jmp     loc_180016E02
0x180016e9d  mov     eax, 1
0x180016ea2  jmp     short loc_180016E7D
```
