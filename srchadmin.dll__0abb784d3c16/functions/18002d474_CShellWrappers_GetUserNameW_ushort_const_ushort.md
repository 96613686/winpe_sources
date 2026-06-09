# CShellWrappers::GetUserNameW(ushort const *,ushort *)

- ea: `0x18002d474`
- end: `0x18002d69a`
- name: `?GetUserNameW@CShellWrappers@@SAJPEBGPEAG@Z`
- size: `550`
- prototype: `__int64 __fastcall(PCWSTR pszFirst, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001681c`
- `0x180020704`
- `0x180024de8`
- `0x18002cda8`

## callees

- `0x1800094f0`
- `0x18000957c`
- `0x18000d4dc`
- `0x18001a7fc`
- `0x18001a828`
- `0x1800273a4`
- `0x18002d474`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x18002d49f`
- `SHLWAPI!StrStrW` at `0x18002d4be`
- `SHLWAPI!StrStrW` at `0x18002d49f`
- `SHLWAPI!StrStrW` at `0x18002d4be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d67b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d67b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d523`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002d523`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002d562`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002d620`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002d562`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002d620`

## pseudocode

```c
__int64 __fastcall CShellWrappers::GetUserNameW(PCWSTR pszFirst, unsigned __int16 *a2)
{
  int Error; // ebx
  PWSTR v5; // rsi
  PWSTR v6; // rax
  const unsigned __int16 *v7; // rsi
  unsigned __int64 v8; // rbx
  unsigned __int16 *v9; // rax
  PSID v10; // rcx
  LPCWSTR v11; // r11
  DWORD LastError; // eax
  void *v13; // rdi
  void *v14; // rsi
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-10h] BYREF
  PSID Sid; // [rsp+38h] [rbp-8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+80h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+88h] [rbp+48h] BYREF

  Error = 1;
  v5 = StrStrW(pszFirst, L"://{");
  if ( v5 )
  {
    v6 = StrStrW(pszFirst, L"}");
    if ( v6 )
    {
      v7 = v5 + 4;
      v8 = v6 - v7 + 1;
      v9 = (unsigned __int16 *)operator new(saturated_mul(v8, 2u));
      v10 = 0;
      Sid = 0;
      if ( v9 )
      {
        StringCchCopyW(v9, v8, v7);
        Error = 0;
        if ( !ConvertStringSidToSidW(v11, &Sid) )
          Error = -2147024809;
        v10 = Sid;
      }
      else
      {
        Error = -2147024882;
      }
      peUse = 0;
      cchName = 0;
      cchReferencedDomainName = 0;
      if ( Error >= 0 )
      {
        LookupAccountSidLocalW(v10, 0, &cchName, 0, &cchReferencedDomainName, &peUse);
        LastError = GetLastError();
        if ( LastError == 1332 )
        {
          Error = -2147024883;
          v13 = 0;
LABEL_11:
          v14 = 0;
LABEL_24:
          operator delete(v14);
          operator delete(v13);
          LocalFree(Sid);
          return (unsigned int)Error;
        }
        if ( LastError == 122 )
        {
          Error = 0;
LABEL_16:
          v13 = operator new(saturated_mul(cchName, 2u));
          if ( !v13 )
          {
            Error = -2147024882;
            goto LABEL_11;
          }
LABEL_18:
          v14 = 0;
          if ( Error >= 0 )
          {
            v14 = operator new(saturated_mul(cchReferencedDomainName, 2u));
            if ( v14 )
            {
              if ( LookupAccountSidLocalW(Sid, (LPWSTR)v13, &cchName, (LPWSTR)v14, &cchReferencedDomainName, &peUse) )
              {
                StringCchCopyW(a2, 0x104u, (const unsigned __int16 *)v14);
                StringCchCatW(a2, 0x104u, L"\\");
                StringCchCatW(a2, 0x104u, (const unsigned __int16 *)v13);
              }
              else
              {
                Error = ResultFromKnownLastError();
              }
            }
            else
            {
              Error = -2147024882;
            }
          }
          goto LABEL_24;
        }
        Error = ResultFromKnownError(LastError);
      }
      v13 = 0;
      if ( Error < 0 )
        goto LABEL_18;
      goto LABEL_16;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002d474  mov     [rsp-28h+arg_0], rbx
0x18002d479  mov     [rsp-28h+arg_8], rsi
0x18002d47e  push    rbp
0x18002d47f  push    rdi
0x18002d480  push    r13
0x18002d482  push    r14
0x18002d484  push    r15
0x18002d486  mov     rbp, rsp
0x18002d489  sub     rsp, 40h
0x18002d48d  mov     r14, rdx
0x18002d490  mov     rdi, rcx
0x18002d493  lea     rdx, asc_180038620; "://{"
0x18002d49a  mov     ebx, 1
0x18002d49f  call    cs:__imp_StrStrW
0x18002d4a5  xor     r15d, r15d
0x18002d4a8  mov     rsi, rax
0x18002d4ab  test    rax, rax
0x18002d4ae  jz      loc_18002D681
0x18002d4b4  lea     rdx, asc_1800383D8; "}"
0x18002d4bb  mov     rcx, rdi; pszFirst
0x18002d4be  call    cs:__imp_StrStrW
0x18002d4c4  test    rax, rax
0x18002d4c7  jz      loc_18002D681
0x18002d4cd  add     rsi, 8
0x18002d4d1  lea     rcx, [r15-1]
0x18002d4d5  sub     rax, rsi
0x18002d4d8  lea     r13d, [r15+2]
0x18002d4dc  sar     rax, 1
0x18002d4df  lea     rbx, [rax+1]
0x18002d4e3  mov     eax, r13d
0x18002d4e6  mul     rbx
0x18002d4e9  cmovb   rax, rcx
0x18002d4ed  mov     rcx, rax; unsigned __int64
0x18002d4f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d4f5  mov     ecx, r15d
0x18002d4f8  mov     r11, rax
0x18002d4fb  mov     [rbp+Sid], rcx
0x18002d4ff  test    rax, rax
0x18002d502  jnz     short loc_18002D50B
0x18002d504  mov     ebx, 8007000Eh
0x18002d509  jmp     short loc_18002D537
0x18002d50b  mov     r8, rsi; unsigned __int16 *
0x18002d50e  mov     rdx, rbx; unsigned __int64
0x18002d511  mov     rcx, r11; unsigned __int16 *
0x18002d514  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d519  lea     rdx, [rbp+Sid]; Sid
0x18002d51d  mov     rcx, r11; StringSid
0x18002d520  mov     ebx, r15d
0x18002d523  call    cs:__imp_ConvertStringSidToSidW
0x18002d529  mov     ecx, 80070057h
0x18002d52e  test    eax, eax
0x18002d530  cmovz   ebx, ecx
0x18002d533  mov     rcx, [rbp+Sid]; Sid
0x18002d537  mov     [rbp+var_10], r15d
0x18002d53b  mov     [rbp+cchName], r15d
0x18002d53f  mov     [rbp+arg_10], r15d
0x18002d543  test    ebx, ebx
0x18002d545  js      short loc_18002D598
0x18002d547  lea     rax, [rbp+var_10]
0x18002d54b  xor     r9d, r9d; ReferencedDomainName
0x18002d54e  mov     [rsp+40h+peUse], rax; peUse
0x18002d553  lea     r8, [rbp+cchName]; cchName
0x18002d557  lea     rax, [rbp+arg_10]
0x18002d55b  xor     edx, edx; Name
0x18002d55d  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002d562  call    cs:__imp_LookupAccountSidLocalW
0x18002d568  call    cs:__imp_GetLastError
0x18002d56e  cmp     eax, 534h
0x18002d573  jnz     short loc_18002D585
0x18002d575  mov     ebx, 8007000Dh
0x18002d57a  mov     rdi, r15
0x18002d57d  mov     rsi, r15
0x18002d580  jmp     loc_18002D667
0x18002d585  cmp     eax, 7Ah ; 'z'
0x18002d588  jnz     short loc_18002D58F
0x18002d58a  mov     ebx, r15d
0x18002d58d  jmp     short loc_18002D59F
0x18002d58f  mov     ecx, eax; unsigned int
0x18002d591  call    ?ResultFromKnownError@@YAJK@Z; ResultFromKnownError(ulong)
0x18002d596  mov     ebx, eax
0x18002d598  mov     rdi, r15
0x18002d59b  test    ebx, ebx
0x18002d59d  js      short loc_18002D5CA
0x18002d59f  mov     ecx, [rbp+cchName]
0x18002d5a2  mov     rax, r13
0x18002d5a5  mul     rcx
0x18002d5a8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d5af  cmovb   rax, rcx
0x18002d5b3  mov     rcx, rax; unsigned __int64
0x18002d5b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d5bb  mov     rdi, rax
0x18002d5be  test    rax, rax
0x18002d5c1  jnz     short loc_18002D5CA
0x18002d5c3  mov     ebx, 8007000Eh
0x18002d5c8  jmp     short loc_18002D57D
0x18002d5ca  mov     rsi, r15
0x18002d5cd  test    ebx, ebx
0x18002d5cf  js      loc_18002D667
0x18002d5d5  mov     ecx, [rbp+arg_10]
0x18002d5d8  mov     rax, r13
0x18002d5db  mul     rcx
0x18002d5de  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d5e5  cmovb   rax, rcx
0x18002d5e9  mov     rcx, rax; unsigned __int64
0x18002d5ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d5f1  mov     rsi, rax
0x18002d5f4  test    rax, rax
0x18002d5f7  jnz     short loc_18002D600
0x18002d5f9  mov     ebx, 8007000Eh
0x18002d5fe  jmp     short loc_18002D667
0x18002d600  mov     rcx, [rbp+Sid]; Sid
0x18002d604  lea     rax, [rbp+var_10]
0x18002d608  mov     [rsp+40h+peUse], rax; peUse
0x18002d60d  lea     r8, [rbp+cchName]; cchName
0x18002d611  lea     rax, [rbp+arg_10]
0x18002d615  mov     r9, rsi; ReferencedDomainName
0x18002d618  mov     rdx, rdi; Name
0x18002d61b  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002d620  call    cs:__imp_LookupAccountSidLocalW
0x18002d626  test    eax, eax
0x18002d628  jz      short loc_18002D660
0x18002d62a  mov     r15d, 104h
0x18002d630  mov     r8, rsi; unsigned __int16 *
0x18002d633  mov     edx, r15d; unsigned __int64
0x18002d636  mov     rcx, r14; unsigned __int16 *
0x18002d639  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d63e  lea     r8, SubStr; "\\"
0x18002d645  mov     edx, r15d; unsigned __int64
0x18002d648  mov     rcx, r14; unsigned __int16 *
0x18002d64b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d650  mov     r8, rdi; unsigned __int16 *
0x18002d653  mov     edx, r15d; unsigned __int64
0x18002d656  mov     rcx, r14; unsigned __int16 *
0x18002d659  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d65e  jmp     short loc_18002D667
0x18002d660  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d665  mov     ebx, eax
0x18002d667  mov     rcx, rsi; lpMem
0x18002d66a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d66f  mov     rcx, rdi; lpMem
0x18002d672  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d677  mov     rcx, [rbp+Sid]; hMem
0x18002d67b  call    cs:__imp_LocalFree
0x18002d681  mov     rsi, [rsp+40h+arg_8]
0x18002d686  mov     eax, ebx
0x18002d688  mov     rbx, [rsp+40h+arg_0]
0x18002d68d  add     rsp, 40h
0x18002d691  pop     r15
0x18002d693  pop     r14
0x18002d695  pop     r13
0x18002d697  pop     rdi
0x18002d698  pop     rbp
0x18002d699  retn
```
