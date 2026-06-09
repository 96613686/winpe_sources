# URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal(STRU *,BUFFER *)

- ea: `0x180003910`
- end: `0x180003b04`
- name: `?ResolveUserNameToSidForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVSTRU@@PEAVBUFFER@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(struct STRU *, struct BUFFER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b88`

## callees

- `0x180003910`
- `0x180003bb2`
- `0x180003be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a70`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800039b4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180003a66`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800039b4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180003a66`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003a01`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003a2f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003a01`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003a2f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000396f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000396f`
- `iisutil!PuDbgPrintError` at `0x180003ac2`
- `iisutil!PuDbgPrintError` at `0x180003ac2`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003adb`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003adb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003ad1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003ad1`

## string_xrefs

- `0x180003a98`: `URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal`
- `0x180003aa6`: `servercommon\inetsrv\iis\iisrearc\iis70\urlauthorization\url_authz_rule_list.cxx`

## pseudocode

```c
__int64 __fastcall URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal(struct STRU *a1, struct BUFFER *a2)
{
  void *v4; // r8
  const WCHAR *v5; // rdx
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // r8
  signed int v9; // eax
  signed int v10; // eax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+70h] [rbp-90h]
  unsigned int v17; // [rsp+78h] [rbp-88h]
  _BYTE v18[32]; // [rsp+88h] [rbp-78h] BYREF
  char *v19; // [rsp+A8h] [rbp-58h]
  int v20; // [rsp+B0h] [rbp-50h]
  __int16 v21; // [rsp+B4h] [rbp-4Ch]
  char v22; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v23[127]; // [rsp+C1h] [rbp-3Fh] BYREF

  memset_0(v23, 0, sizeof(v23));
  v22 = 0;
  v19 = &v22;
  cbSid = *((_DWORD *)a2 + 10);
  v20 = 128;
  v21 = 256;
  STRU::STRU((STRU *)v15);
  v4 = (void *)*((_QWORD *)a2 + 4);
  v5 = (const WCHAR *)*((_QWORD *)a1 + 4);
  cchReferencedDomainName = v17 >> 1;
  peUse = 0;
  if ( LookupAccountNameW(0, v5, v4, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    goto LABEL_18;
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v8 = 541;
LABEL_17:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\urlauthorization\\url_authz_rule_list.cxx",
        v8,
        "URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal",
        v7,
        "Failed to Lookup account %S (LookupAccountNameW() failed)\n",
        *((const wchar_t **)a1 + 4));
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  if ( !BUFFER::Resize(a2, cbSid) || !BUFFER::Resize((BUFFER *)v15, 2 * cchReferencedDomainName) )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v7 = v9;
    goto LABEL_19;
  }
  if ( LookupAccountNameW(
         0,
         *((LPCWSTR *)a1 + 4),
         *((PSID *)a2 + 4),
         &cbSid,
         ReferencedDomainName,
         &cchReferencedDomainName,
         &peUse) )
  {
LABEL_18:
    v7 = 0;
    goto LABEL_19;
  }
  v10 = GetLastError();
  v7 = v10;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v8 = 579;
    goto LABEL_17;
  }
LABEL_19:
  STRU::~STRU((STRU *)v15);
  BUFFER::~BUFFER((BUFFER *)v18);
  return v7;
}

```

## disassembly

```asm
0x180003910  mov     [rsp-8+arg_10], rbx
0x180003915  mov     [rsp-8+arg_18], rdi
0x18000391a  push    rbp
0x18000391b  lea     rbp, [rsp-50h]
0x180003920  sub     rsp, 150h
0x180003927  mov     rax, cs:__security_cookie
0x18000392e  xor     rax, rsp
0x180003931  mov     [rbp+50h+var_10], rax
0x180003935  mov     rbx, rdx
0x180003938  mov     rdi, rcx
0x18000393b  xor     edx, edx; Val
0x18000393d  lea     rcx, [rbp+50h+var_8F]; void *
0x180003941  lea     r8d, [rdx+7Fh]; Size
0x180003945  call    memset_0
0x18000394a  lea     rax, [rbp+50h+var_90]
0x18000394e  mov     [rbp+50h+var_90], 0
0x180003952  mov     [rbp+50h+var_A8], rax
0x180003956  lea     rcx, [rsp+150h+var_100]
0x18000395b  mov     eax, [rbx+28h]
0x18000395e  mov     [rsp+150h+cbSid], eax
0x180003962  mov     [rbp+50h+var_A0], 80h
0x180003969  mov     [rbp+50h+var_9C], 100h
0x18000396f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003975  mov     eax, [rsp+150h+var_D8]
0x180003979  lea     rcx, [rsp+150h+var_108]
0x18000397e  mov     r8, [rbx+20h]; Sid
0x180003982  lea     r9, [rsp+150h+cbSid]; cbSid
0x180003987  mov     rdx, [rdi+20h]; lpAccountName
0x18000398b  mov     [rsp+150h+peUse], rcx; peUse
0x180003990  lea     rcx, [rsp+150h+var_110]
0x180003995  shr     eax, 1
0x180003997  mov     [rsp+150h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18000399c  xor     ecx, ecx; lpSystemName
0x18000399e  mov     [rsp+150h+var_110], eax
0x1800039a2  mov     rax, [rsp+150h+var_E0]
0x1800039a7  mov     [rsp+150h+ReferencedDomainName], rax; ReferencedDomainName
0x1800039ac  mov     [rsp+150h+var_108], 0
0x1800039b4  call    cs:__imp_LookupAccountNameW
0x1800039ba  test    eax, eax
0x1800039bc  jnz     loc_180003ACA
0x1800039c2  call    cs:__imp_GetLastError
0x1800039c8  cmp     eax, 7Ah ; 'z'
0x1800039cb  jz      short loc_1800039FA
0x1800039cd  call    cs:__imp_GetLastError
0x1800039d3  mov     ebx, eax
0x1800039d5  test    eax, eax
0x1800039d7  jle     short loc_1800039E2
0x1800039d9  movzx   ebx, ax
0x1800039dc  or      ebx, 80070000h
0x1800039e2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800039e9  jz      loc_180003ACC
0x1800039ef  mov     r8d, 21Dh
0x1800039f5  jmp     loc_180003A94
0x1800039fa  mov     edx, [rsp+150h+cbSid]
0x1800039fe  mov     rcx, rbx
0x180003a01  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003a07  test    al, al
0x180003a09  jnz     short loc_180003A24
0x180003a0b  call    cs:__imp_GetLastError
0x180003a11  test    eax, eax
0x180003a13  jle     short loc_180003A1D
0x180003a15  movzx   eax, ax
0x180003a18  or      eax, 80070000h
0x180003a1d  mov     ebx, eax
0x180003a1f  jmp     loc_180003ACC
0x180003a24  mov     edx, [rsp+150h+var_110]
0x180003a28  lea     rcx, [rsp+150h+var_100]
0x180003a2d  add     edx, edx
0x180003a2f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003a35  test    al, al
0x180003a37  jz      short loc_180003A0B
0x180003a39  mov     rax, [rsp+150h+var_E0]
0x180003a3e  lea     rcx, [rsp+150h+var_108]
0x180003a43  mov     r8, [rbx+20h]; Sid
0x180003a47  lea     r9, [rsp+150h+cbSid]; cbSid
0x180003a4c  mov     rdx, [rdi+20h]; lpAccountName
0x180003a50  mov     [rsp+150h+peUse], rcx; peUse
0x180003a55  lea     rcx, [rsp+150h+var_110]
0x180003a5a  mov     [rsp+150h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180003a5f  xor     ecx, ecx; lpSystemName
0x180003a61  mov     [rsp+150h+ReferencedDomainName], rax; ReferencedDomainName
0x180003a66  call    cs:__imp_LookupAccountNameW
0x180003a6c  test    eax, eax
0x180003a6e  jnz     short loc_180003ACA
0x180003a70  call    cs:__imp_GetLastError
0x180003a76  mov     ebx, eax
0x180003a78  test    eax, eax
0x180003a7a  jle     short loc_180003A85
0x180003a7c  movzx   ebx, ax
0x180003a7f  or      ebx, 80070000h
0x180003a85  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003a8c  jz      short loc_180003ACC
0x180003a8e  mov     r8d, 243h
0x180003a94  mov     rax, [rdi+20h]
0x180003a98  lea     r9, aUrlAuthzRuleEn_0; "URL_AUTHZ_RULE_ENTRY::ResolveUserNameTo"...
0x180003a9f  mov     rcx, cs:g_pDebug
0x180003aa6  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003aad  mov     [rsp+150h+peUse], rax
0x180003ab2  lea     rax, aFailedToLookup; "Failed to Lookup account %S (LookupAcco"...
0x180003ab9  mov     [rsp+150h+cchReferencedDomainName], rax
0x180003abe  mov     dword ptr [rsp+150h+ReferencedDomainName], ebx
0x180003ac2  call    cs:__imp_PuDbgPrintError
0x180003ac8  jmp     short loc_180003ACC
0x180003aca  xor     ebx, ebx
0x180003acc  lea     rcx, [rsp+150h+var_100]
0x180003ad1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003ad7  lea     rcx, [rbp+50h+var_C8]
0x180003adb  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003ae1  mov     eax, ebx
0x180003ae3  mov     rcx, [rbp+50h+var_10]
0x180003ae7  xor     rcx, rsp; StackCookie
0x180003aea  call    __security_check_cookie
0x180003aef  lea     r11, [rsp+150h+var_s0]
0x180003af7  mov     rbx, [r11+20h]
0x180003afb  mov     rdi, [r11+28h]
0x180003aff  mov     rsp, r11
0x180003b02  pop     rbp
0x180003b03  retn
```
