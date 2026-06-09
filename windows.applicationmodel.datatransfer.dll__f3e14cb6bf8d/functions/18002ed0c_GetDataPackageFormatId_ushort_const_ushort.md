# GetDataPackageFormatId(ushort const *,ushort *)

- ea: `0x18002ed0c`
- end: `0x18002ee11`
- name: `?GetDataPackageFormatId@@YAJPEBGPEAG@Z`
- size: `261`
- prototype: `__int64 __fastcall(LPCWSTR lpszFormat, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fb3c`
- `0x18000fc84`
- `0x18002f4e0`
- `0x180051c68`

## callees

- `0x18002ed0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ed7d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002edb4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ed7d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002edb4`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x18002edd2`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x18002edd2`

## pseudocode

```c
signed int __fastcall GetDataPackageFormatId(LPCWSTR lpszFormat, unsigned __int16 *a2)
{
  LPCWSTR v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rbp
  __int64 *v7; // rdi
  unsigned __int16 v8; // ax
  signed int result; // eax

  *a2 = 0;
  if ( lpszFormat )
  {
    v4 = lpszFormat;
    v5 = 0x7FFFFFFF;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v7 = &qword_18008D3D0;
      while ( CompareStringOrdinal((LPCWCH)v7[1], -1, lpszFormat, v6, 1) != 2 )
      {
        v7 += 2;
        if ( v7 == (__int64 *)&`SafeHtmlValidatorHelper::IsUriSchemeSafe'::`2'::s_crgUnsafeList )
        {
          v7 = &qword_18008D380;
          while ( CompareStringOrdinal((LPCWCH)v7[1], -1, lpszFormat, v6, 1) != 2 )
          {
            v7 += 2;
            if ( v7 == &qword_18008D3D0 )
            {
              v8 = RegisterClipboardFormatW(lpszFormat);
              goto LABEL_14;
            }
          }
          break;
        }
      }
      v8 = *(_WORD *)v7;
LABEL_14:
      *a2 = v8;
      if ( v8 )
        return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x18002ed0c  push    rbx
0x18002ed0e  push    rbp
0x18002ed0f  push    rsi
0x18002ed10  push    rdi
0x18002ed11  push    r14
0x18002ed13  sub     rsp, 30h
0x18002ed17  xor     r14d, r14d
0x18002ed1a  mov     rbx, rdx
0x18002ed1d  mov     [rdx], r14w
0x18002ed21  mov     rsi, rcx
0x18002ed24  test    rcx, rcx
0x18002ed27  jz      loc_18002EDEA
0x18002ed2d  mov     r8d, 7FFFFFFFh
0x18002ed33  mov     rax, rcx
0x18002ed36  mov     edx, r8d
0x18002ed39  cmp     [rax], r14w
0x18002ed3d  jz      short loc_18002ED49
0x18002ed3f  add     rax, 2
0x18002ed43  sub     rdx, 1
0x18002ed47  jnz     short loc_18002ED39
0x18002ed49  sub     r8, rdx
0x18002ed4c  mov     rax, rdx
0x18002ed4f  neg     rax
0x18002ed52  sbb     rbp, rbp
0x18002ed55  and     rbp, r8
0x18002ed58  test    rdx, rdx
0x18002ed5b  jz      loc_18002EDEA
0x18002ed61  lea     rdi, qword_18008D3D0
0x18002ed68  mov     rcx, [rdi+8]; lpString1
0x18002ed6c  mov     r9d, ebp; cchCount2
0x18002ed6f  mov     r8, rsi; lpString2
0x18002ed72  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18002ed7a  or      edx, 0FFFFFFFFh; cchCount1
0x18002ed7d  call    cs:__imp_CompareStringOrdinal
0x18002ed83  cmp     eax, 2
0x18002ed86  jz      short loc_18002EDDA
0x18002ed88  add     rdi, 10h
0x18002ed8c  lea     rax, ?s_crgUnsafeList@?1??IsUriSchemeSafe@SafeHtmlValidatorHelper@@YA_NPEBG_K_NHHPEAPEAG@Z@4QBUUriSchemeEntry@2@B; SafeHtmlValidatorHelper::UriSchemeEntry const near * const `SafeHtmlValidatorHelper::IsUriSchemeSafe(ushort const *,unsigned __int64,bool,int,int,ushort * *)'::`2'::s_crgUnsafeList
0x18002ed93  cmp     rdi, rax
0x18002ed96  jnz     short loc_18002ED68
0x18002ed98  lea     rdi, qword_18008D380
0x18002ed9f  mov     rcx, [rdi+8]; lpString1
0x18002eda3  mov     r9d, ebp; cchCount2
0x18002eda6  mov     r8, rsi; lpString2
0x18002eda9  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18002edb1  or      edx, 0FFFFFFFFh; cchCount1
0x18002edb4  call    cs:__imp_CompareStringOrdinal
0x18002edba  cmp     eax, 2
0x18002edbd  jz      short loc_18002EDDA
0x18002edbf  add     rdi, 10h
0x18002edc3  lea     rax, qword_18008D3D0
0x18002edca  cmp     rdi, rax
0x18002edcd  jnz     short loc_18002ED9F
0x18002edcf  mov     rcx, rsi; lpszFormat
0x18002edd2  call    cs:__imp_RegisterClipboardFormatW
0x18002edd8  jmp     short loc_18002EDDD
0x18002edda  movzx   eax, word ptr [rdi]
0x18002eddd  mov     [rbx], ax
0x18002ede0  test    ax, ax
0x18002ede3  jz      short loc_18002EDEA
0x18002ede5  mov     eax, r14d
0x18002ede8  jmp     short loc_18002EE06
0x18002edea  call    cs:__imp_GetLastError
0x18002edf0  test    eax, eax
0x18002edf2  jle     short loc_18002EDFC
0x18002edf4  movzx   eax, ax
0x18002edf7  or      eax, 80070000h
0x18002edfc  test    eax, eax
0x18002edfe  mov     ecx, 80004005h
0x18002ee03  cmovns  eax, ecx
0x18002ee06  add     rsp, 30h
0x18002ee0a  pop     r14
0x18002ee0c  pop     rdi
0x18002ee0d  pop     rsi
0x18002ee0e  pop     rbp
0x18002ee0f  pop     rbx
0x18002ee10  retn
```
