# UserTokenUtility::GetVirtualAccountTokenFromProcessToken(void *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x1800307b0`
- end: `0x1800309bd`
- name: `?GetVirtualAccountTokenFromProcessToken@UserTokenUtility@@SAJPEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180027460`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180007c48`
- `0x180007cf8`
- `0x1800307b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030952`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003081b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003081b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003086a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800308fa`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18003086a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800308fa`
- `SspiCli!LogonUserExExW` at `0x180030948`
- `SspiCli!LogonUserExExW` at `0x180030948`

## pseudocode

```c
__int64 __fastcall UserTokenUtility::GetVirtualAccountTokenFromProcessToken(void *a1, __int64 a2)
{
  signed int LastError; // eax
  unsigned int v4; // esi
  PSID v5; // r15
  WCHAR **unique_for; // rax
  const struct std::nothrow_t *v7; // rdx
  WCHAR *v8; // rbx
  WCHAR **v9; // rax
  const struct std::nothrow_t *v10; // rdx
  WCHAR *v11; // rdi
  __int64 v12; // rax
  const struct std::nothrow_t *v13; // rdx
  signed int v14; // eax
  DWORD cchReferencedDomainName; // [rsp+60h] [rbp-59h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-55h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+68h] [rbp-51h] BYREF
  DWORD ReturnLength; // [rsp+6Ch] [rbp-4Dh] BYREF
  void *v20[2]; // [rsp+70h] [rbp-49h] BYREF
  PSID TokenInformation[12]; // [rsp+80h] [rbp-39h] BYREF

  ReturnLength = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  if ( !GetTokenInformation(a1, TokenUser, TokenInformation, 0x54u, &ReturnLength) )
  {
    LastError = GetLastError();
    v4 = LastError;
LABEL_5:
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v4;
  }
  v5 = TokenInformation[0];
  if ( LookupAccountSidW(0, TokenInformation[0], 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
    return (unsigned int)-2147418113;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 122 )
    goto LABEL_5;
  unique_for = (WCHAR **)utl::make_unique_for_overwrite<wchar_t [0],0>(v20, cchName);
  v8 = *unique_for;
  *unique_for = 0;
  if ( v20[0] )
    operator delete(v20[0], v7);
  if ( v8 )
  {
    v9 = (WCHAR **)utl::make_unique_for_overwrite<wchar_t [0],0>(v20, cchReferencedDomainName);
    v11 = *v9;
    *v9 = 0;
    if ( v20[0] )
      operator delete(v20[0], v10);
    if ( v11 )
    {
      if ( !LookupAccountSidW(0, v5, v8, &cchName, v11, &cchReferencedDomainName, &peUse)
        || (v4 = 0,
            v12 = tlx::replace<tlx::file_handle_traits>(a2),
            !(unsigned int)LogonUserExExW(v8, v11, &dword_180039414, 2, 4, 0, v12, 0, 0, 0, 0)) )
      {
        v14 = GetLastError();
        v4 = v14;
        if ( v14 > 0 )
          v4 = (unsigned __int16)v14 | 0x80070000;
      }
      operator delete(v11, v13);
    }
    else
    {
      v4 = -2147024882;
    }
    operator delete(v8, v10);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v4;
}

```

## disassembly

```asm
0x1800307b0  mov     [rsp-8+arg_10], rbx
0x1800307b5  mov     [rsp-8+arg_18], rsi
0x1800307ba  push    rbp
0x1800307bb  push    rdi
0x1800307bc  push    r12
0x1800307be  push    r14
0x1800307c0  push    r15
0x1800307c2  lea     rbp, [rsp-37h]
0x1800307c7  sub     rsp, 0F0h
0x1800307ce  mov     rax, cs:__security_cookie
0x1800307d5  xor     rax, rsp
0x1800307d8  mov     [rbp+57h+var_30], rax
0x1800307dc  xor     r12d, r12d
0x1800307df  mov     r14, rdx
0x1800307e2  mov     [rbp+57h+var_A4], r12d
0x1800307e6  mov     [rbp+57h+cchName], r12d
0x1800307ea  mov     [rbp+57h+var_B0], r12d
0x1800307ee  mov     [rbp+57h+var_A8], r12d
0x1800307f2  test    rcx, rcx
0x1800307f5  jz      loc_18003098E
0x1800307fb  test    rdx, rdx
0x1800307fe  jz      loc_18003098E
0x180030804  lea     rax, [rbp+57h+var_A4]
0x180030808  lea     r9d, [r12+54h]; TokenInformationLength
0x18003080d  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x180030812  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180030816  lea     edx, [r12+1]; TokenInformationClass
0x18003081b  call    cs:__imp_GetTokenInformation
0x180030821  test    eax, eax
0x180030823  jnz     short loc_180030843
0x180030825  call    cs:__imp_GetLastError
0x18003082b  mov     esi, eax
0x18003082d  test    eax, eax
0x18003082f  jle     loc_180030993
0x180030835  movzx   esi, ax
0x180030838  or      esi, 80070000h
0x18003083e  jmp     loc_180030993
0x180030843  mov     r15, [rbp+57h+TokenInformation]
0x180030847  lea     rax, [rbp+57h+var_A8]
0x18003084b  mov     [rsp+110h+peUse], rax; peUse
0x180030850  lea     r9, [rbp+57h+cchName]; cchName
0x180030854  lea     rax, [rbp+57h+var_B0]
0x180030858  xor     r8d, r8d; Name
0x18003085b  mov     [rsp+110h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180030860  mov     rdx, r15; Sid
0x180030863  xor     ecx, ecx; lpSystemName
0x180030865  mov     [rsp+110h+ReturnLength], r12; ReferencedDomainName
0x18003086a  call    cs:__imp_LookupAccountSidW
0x180030870  test    eax, eax
0x180030872  jnz     loc_180030987
0x180030878  call    cs:__imp_GetLastError
0x18003087e  mov     esi, eax
0x180030880  cmp     eax, 7Ah ; 'z'
0x180030883  jnz     short loc_18003082D
0x180030885  mov     edx, [rbp+57h+cchName]
0x180030888  lea     rcx, [rbp+57h+var_A0]
0x18003088c  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180030891  mov     rbx, [rax]
0x180030894  mov     [rax], r12
0x180030897  mov     rcx, [rbp+57h+var_A0]; void *
0x18003089b  test    rcx, rcx
0x18003089e  jz      short loc_1800308A5
0x1800308a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800308a5  test    rbx, rbx
0x1800308a8  jz      loc_180030980
0x1800308ae  mov     edx, [rbp+57h+var_B0]
0x1800308b1  lea     rcx, [rbp+57h+var_A0]
0x1800308b5  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800308ba  mov     rdi, [rax]
0x1800308bd  mov     [rax], r12
0x1800308c0  mov     rcx, [rbp+57h+var_A0]; void *
0x1800308c4  test    rcx, rcx
0x1800308c7  jz      short loc_1800308CE
0x1800308c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800308ce  test    rdi, rdi
0x1800308d1  jz      loc_180030971
0x1800308d7  lea     rax, [rbp+57h+var_A8]
0x1800308db  mov     r8, rbx; Name
0x1800308de  mov     [rsp+110h+peUse], rax; peUse
0x1800308e3  lea     r9, [rbp+57h+cchName]; cchName
0x1800308e7  lea     rax, [rbp+57h+var_B0]
0x1800308eb  mov     rdx, r15; Sid
0x1800308ee  mov     [rsp+110h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800308f3  xor     ecx, ecx; lpSystemName
0x1800308f5  mov     [rsp+110h+ReturnLength], rdi; ReferencedDomainName
0x1800308fa  call    cs:__imp_LookupAccountSidW
0x180030900  test    eax, eax
0x180030902  jz      short loc_180030952
0x180030904  mov     rcx, r14
0x180030907  mov     esi, r12d
0x18003090a  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18003090f  mov     [rsp+110h+var_C0], r12
0x180030914  lea     r8, dword_180039414
0x18003091b  mov     [rsp+110h+var_C8], r12
0x180030920  mov     r9d, 2
0x180030926  mov     [rsp+110h+var_D0], r12
0x18003092b  mov     rdx, rdi
0x18003092e  mov     [rsp+110h+var_D8], r12
0x180030933  mov     rcx, rbx
0x180030936  mov     [rsp+110h+peUse], rax
0x18003093b  mov     [rsp+110h+cchReferencedDomainName], r12
0x180030940  mov     dword ptr [rsp+110h+ReturnLength], 4
0x180030948  call    cs:__imp_LogonUserExExW
0x18003094e  test    eax, eax
0x180030950  jnz     short loc_180030967
0x180030952  call    cs:__imp_GetLastError
0x180030958  mov     esi, eax
0x18003095a  test    eax, eax
0x18003095c  jle     short loc_180030967
0x18003095e  movzx   esi, ax
0x180030961  or      esi, 80070000h
0x180030967  mov     rcx, rdi; void *
0x18003096a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003096f  jmp     short loc_180030976
0x180030971  mov     esi, 8007000Eh
0x180030976  mov     rcx, rbx; void *
0x180030979  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003097e  jmp     short loc_180030993
0x180030980  mov     esi, 8007000Eh
0x180030985  jmp     short loc_180030993
0x180030987  mov     esi, 8000FFFFh
0x18003098c  jmp     short loc_180030993
0x18003098e  mov     esi, 80070057h
0x180030993  mov     eax, esi
0x180030995  mov     rcx, [rbp+57h+var_30]
0x180030999  xor     rcx, rsp; StackCookie
0x18003099c  call    __security_check_cookie
0x1800309a1  lea     r11, [rsp+110h+var_20]
0x1800309a9  mov     rbx, [r11+40h]
0x1800309ad  mov     rsi, [r11+48h]
0x1800309b1  mov     rsp, r11
0x1800309b4  pop     r15
0x1800309b6  pop     r14
0x1800309b8  pop     r12
0x1800309ba  pop     rdi
0x1800309bb  pop     rbp
0x1800309bc  retn
```
