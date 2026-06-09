# URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal(IHttpUser *,STRU *,int *)

- ea: `0x180002ed8`
- end: `0x180003151`
- name: `?CheckTokenMembershipForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVIHttpUser@@PEAVSTRU@@PEAH@Z`
- size: `633`
- prototype: `__int64 __fastcall(struct IHttpUser *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b88`

## callees

- `0x180002ed8`
- `0x180003bb2`
- `0x180003be0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030db`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180002f99`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18000304c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180002f99`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18000304c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800030d1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800030d1`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002fe8`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003015`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002fe8`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003015`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002f55`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002f55`
- `iisutil!PuDbgPrintError` at `0x1800030ac`
- `iisutil!PuDbgPrintError` at `0x1800030ac`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003125`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000312f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003125`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000312f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000311a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000311a`

## string_xrefs

- `0x1800030a1`: `servercommon\inetsrv\iis\iisrearc\iis70\urlauthorization\url_authz_rule_list.cxx`
- `0x180003095`: `URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal`
- `0x180003108`: `Failed to call CheckTokenMembership() for %S \n`

## pseudocode

```c
__int64 __fastcall URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal(
        struct IHttpUser *a1,
        struct STRU *a2,
        int *a3)
{
  const WCHAR *v6; // rdx
  signed int LastError; // eax
  unsigned int v8; // ebx
  __int64 v9; // r8
  signed int v10; // eax
  signed int v11; // eax
  PSID v12; // rbx
  void *v13; // rax
  signed int v14; // eax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+78h] [rbp-88h]
  __int16 v22; // [rsp+7Ch] [rbp-84h]
  _BYTE v23[32]; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+A0h] [rbp-60h]
  unsigned int v25; // [rsp+A8h] [rbp-58h]
  _BYTE v26[32]; // [rsp+B8h] [rbp-48h] BYREF
  char *v27; // [rsp+D8h] [rbp-28h]
  int v28; // [rsp+E0h] [rbp-20h]
  __int16 v29; // [rsp+E4h] [rbp-1Ch]
  char v30; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v31[127]; // [rsp+F1h] [rbp-Fh] BYREF

  memset_0(v31, 0, sizeof(v31));
  v30 = 0;
  v27 = &v30;
  v28 = 128;
  Sid = v19;
  v21 = 32;
  cbSid = 32;
  v29 = 256;
  v19[0] = 0;
  v22 = 256;
  STRU::STRU((STRU *)v23);
  v6 = (const WCHAR *)*((_QWORD *)a2 + 4);
  cchReferencedDomainName = v25 >> 1;
  peUse = 0;
  if ( LookupAccountNameW(0, v6, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    goto LABEL_19;
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v9 = 761;
LABEL_17:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\urlauthorization\\url_authz_rule_list.cxx",
        v9,
        "URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal",
        v8,
        "Failed to Lookup account %S (LookupAccountNameW() failed)\n",
        *((_QWORD *)a2 + 4));
      goto LABEL_25;
    }
    goto LABEL_25;
  }
  if ( !BUFFER::Resize((BUFFER *)v19, cbSid) || !BUFFER::Resize((BUFFER *)v23, 2 * cchReferencedDomainName) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v8 = v10;
    goto LABEL_25;
  }
  if ( LookupAccountNameW(0, *((LPCWSTR *)a2 + 4), Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
LABEL_19:
    v12 = Sid;
    v13 = (void *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a1 + 32LL))(a1);
    if ( CheckTokenMembership(v13, v12, a3) )
    {
      v8 = 0;
    }
    else
    {
      v14 = GetLastError();
      v8 = v14;
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\urlauthorization\\url_authz_rule_list.cxx",
          819,
          "URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal",
          v8,
          "Failed to call CheckTokenMembership() for %S \n",
          *((_QWORD *)a2 + 4));
    }
    goto LABEL_25;
  }
  v11 = GetLastError();
  v8 = v11;
  if ( v11 > 0 )
    v8 = (unsigned __int16)v11 | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v9 = 798;
    goto LABEL_17;
  }
LABEL_25:
  STRU::~STRU((STRU *)v23);
  BUFFER::~BUFFER((BUFFER *)v19);
  BUFFER::~BUFFER((BUFFER *)v26);
  return v8;
}

```

## disassembly

```asm
0x180002ed8  push    rbp
0x180002eda  push    rbx
0x180002edb  push    rsi
0x180002edc  push    rdi
0x180002edd  push    r14
0x180002edf  lea     rbp, [rsp-80h]
0x180002ee4  sub     rsp, 180h
0x180002eeb  mov     rax, cs:__security_cookie
0x180002ef2  xor     rax, rsp
0x180002ef5  mov     [rbp+0A0h+var_30], rax
0x180002ef9  mov     rdi, rdx
0x180002efc  mov     r14, r8
0x180002eff  xor     edx, edx; Val
0x180002f01  mov     rsi, rcx
0x180002f04  lea     rcx, [rbp+0A0h+var_AF]; void *
0x180002f08  lea     r8d, [rdx+7Fh]; Size
0x180002f0c  call    memset_0
0x180002f11  lea     rax, [rbp+0A0h+var_B0]
0x180002f15  mov     [rbp+0A0h+var_B0], 0
0x180002f19  mov     [rbp+0A0h+var_C8], rax
0x180002f1d  lea     rcx, [rbp+0A0h+var_120]
0x180002f21  lea     rax, [rsp+1A0h+var_150]
0x180002f26  mov     [rbp+0A0h+var_C0], 80h
0x180002f2d  mov     [rsp+1A0h+Sid], rax
0x180002f32  mov     eax, 20h ; ' '
0x180002f37  mov     [rsp+1A0h+var_128], eax
0x180002f3b  mov     [rsp+1A0h+cbSid], eax
0x180002f3f  mov     [rbp+0A0h+var_BC], 100h
0x180002f45  mov     [rsp+1A0h+var_150], 0
0x180002f4e  mov     [rsp+1A0h+var_124], 100h
0x180002f55  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002f5b  mov     eax, [rbp+0A0h+var_F8]
0x180002f5e  lea     rcx, [rsp+1A0h+var_158]
0x180002f63  mov     r8, [rsp+1A0h+Sid]; Sid
0x180002f68  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x180002f6d  mov     rdx, [rdi+20h]; lpAccountName
0x180002f71  mov     [rsp+1A0h+peUse], rcx; peUse
0x180002f76  lea     rcx, [rsp+1A0h+var_160]
0x180002f7b  shr     eax, 1
0x180002f7d  mov     [rsp+1A0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180002f82  xor     ecx, ecx; lpSystemName
0x180002f84  mov     [rsp+1A0h+var_160], eax
0x180002f88  mov     rax, [rbp+0A0h+var_100]
0x180002f8c  mov     [rsp+1A0h+ReferencedDomainName], rax; ReferencedDomainName
0x180002f91  mov     [rsp+1A0h+var_158], 0
0x180002f99  call    cs:__imp_LookupAccountNameW
0x180002f9f  test    eax, eax
0x180002fa1  jnz     loc_1800030B4
0x180002fa7  call    cs:__imp_GetLastError
0x180002fad  cmp     eax, 7Ah ; 'z'
0x180002fb0  jz      short loc_180002FDF
0x180002fb2  call    cs:__imp_GetLastError
0x180002fb8  mov     ebx, eax
0x180002fba  test    eax, eax
0x180002fbc  jle     short loc_180002FC7
0x180002fbe  movzx   ebx, ax
0x180002fc1  or      ebx, 80070000h
0x180002fc7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002fce  jz      loc_180003116
0x180002fd4  mov     r8d, 2F9h
0x180002fda  jmp     loc_18000307E
0x180002fdf  mov     edx, [rsp+1A0h+cbSid]
0x180002fe3  lea     rcx, [rsp+1A0h+var_150]
0x180002fe8  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180002fee  test    al, al
0x180002ff0  jnz     short loc_18000300B
0x180002ff2  call    cs:__imp_GetLastError
0x180002ff8  test    eax, eax
0x180002ffa  jle     short loc_180003004
0x180002ffc  movzx   eax, ax
0x180002fff  or      eax, 80070000h
0x180003004  mov     ebx, eax
0x180003006  jmp     loc_180003116
0x18000300b  mov     edx, [rsp+1A0h+var_160]
0x18000300f  lea     rcx, [rbp+0A0h+var_120]
0x180003013  add     edx, edx
0x180003015  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000301b  test    al, al
0x18000301d  jz      short loc_180002FF2
0x18000301f  mov     rax, [rbp+0A0h+var_100]
0x180003023  lea     rcx, [rsp+1A0h+var_158]
0x180003028  mov     r8, [rsp+1A0h+Sid]; Sid
0x18000302d  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x180003032  mov     rdx, [rdi+20h]; lpAccountName
0x180003036  mov     [rsp+1A0h+peUse], rcx; peUse
0x18000303b  lea     rcx, [rsp+1A0h+var_160]
0x180003040  mov     [rsp+1A0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180003045  xor     ecx, ecx; lpSystemName
0x180003047  mov     [rsp+1A0h+ReferencedDomainName], rax; ReferencedDomainName
0x18000304c  call    cs:__imp_LookupAccountNameW
0x180003052  test    eax, eax
0x180003054  jnz     short loc_1800030B4
0x180003056  call    cs:__imp_GetLastError
0x18000305c  mov     ebx, eax
0x18000305e  test    eax, eax
0x180003060  jle     short loc_18000306B
0x180003062  movzx   ebx, ax
0x180003065  or      ebx, 80070000h
0x18000306b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003072  jz      loc_180003116
0x180003078  mov     r8d, 31Eh
0x18000307e  mov     rax, [rdi+20h]
0x180003082  mov     [rsp+1A0h+peUse], rax
0x180003087  lea     rax, aFailedToLookup; "Failed to Lookup account %S (LookupAcco"...
0x18000308e  mov     rcx, cs:g_pDebug
0x180003095  lea     r9, aUrlAuthzRuleEn_1; "URL_AUTHZ_RULE_ENTRY::CheckTokenMembers"...
0x18000309c  mov     [rsp+1A0h+cchReferencedDomainName], rax
0x1800030a1  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800030a8  mov     dword ptr [rsp+1A0h+ReferencedDomainName], ebx
0x1800030ac  call    cs:__imp_PuDbgPrintError
0x1800030b2  jmp     short loc_180003116
0x1800030b4  mov     rax, [rsi]
0x1800030b7  mov     rcx, rsi
0x1800030ba  mov     rbx, [rsp+1A0h+Sid]
0x1800030bf  mov     rax, [rax+20h]
0x1800030c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c8  mov     r8, r14; IsMember
0x1800030cb  mov     rdx, rbx; SidToCheck
0x1800030ce  mov     rcx, rax; TokenHandle
0x1800030d1  call    cs:__imp_CheckTokenMembership
0x1800030d7  test    eax, eax
0x1800030d9  jnz     short loc_180003114
0x1800030db  call    cs:__imp_GetLastError
0x1800030e1  mov     ebx, eax
0x1800030e3  test    eax, eax
0x1800030e5  jle     short loc_1800030F0
0x1800030e7  movzx   ebx, ax
0x1800030ea  or      ebx, 80070000h
0x1800030f0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800030f7  jz      short loc_180003116
0x1800030f9  mov     rax, [rdi+20h]
0x1800030fd  mov     r8d, 333h
0x180003103  mov     [rsp+1A0h+peUse], rax
0x180003108  lea     rax, aFailedToCallCh; "Failed to call CheckTokenMembership() f"...
0x18000310f  jmp     loc_18000308E
0x180003114  xor     ebx, ebx
0x180003116  lea     rcx, [rbp+0A0h+var_120]
0x18000311a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003120  lea     rcx, [rsp+1A0h+var_150]
0x180003125  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000312b  lea     rcx, [rbp+0A0h+var_E8]
0x18000312f  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003135  mov     eax, ebx
0x180003137  mov     rcx, [rbp+0A0h+var_30]
0x18000313b  xor     rcx, rsp; StackCookie
0x18000313e  call    __security_check_cookie
0x180003143  add     rsp, 180h
0x18000314a  pop     r14
0x18000314c  pop     rdi
0x18000314d  pop     rsi
0x18000314e  pop     rbx
0x18000314f  pop     rbp
0x180003150  retn
```
