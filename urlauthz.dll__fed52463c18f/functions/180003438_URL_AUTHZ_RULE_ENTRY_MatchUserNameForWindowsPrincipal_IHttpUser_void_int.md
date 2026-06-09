# URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal(IHttpUser *,void *,int *)

- ea: `0x180003438`
- end: `0x18000364b`
- name: `?MatchUserNameForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVIHttpUser@@PEAXPEAH@Z`
- size: `531`
- prototype: `__int64 __fastcall(struct IHttpUser *, void *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b88`

## callees

- `0x180003438`
- `0x180003bb2`
- `0x180003be0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000350c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000354c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000359f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000350c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000354c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000359f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800034f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003595`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800034f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003595`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800035fb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800035fb`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003542`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003542`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800034bd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800034bd`
- `iisutil!PuDbgPrintError` at `0x1800035e8`
- `iisutil!PuDbgPrintError` at `0x1800035e8`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003615`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003620`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003615`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003620`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000360a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000360a`

## string_xrefs

- `0x1800035dd`: `servercommon\inetsrv\iis\iisrearc\iis70\urlauthorization\url_authz_rule_list.cxx`
- `0x1800035ca`: `Failed to call GetTokenInformation() to retrieve SIDfor the user context\n`

## pseudocode

```c
__int64 __fastcall URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal(struct IHttpUser *a1, void *a2, int *a3)
{
  void *v6; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  __int64 v9; // r8
  signed int v10; // eax
  DWORD v11; // ebx
  void *v12; // rdi
  void *v13; // rax
  signed int v14; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[32]; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID TokenInformation; // [rsp+58h] [rbp-A8h]
  DWORD TokenInformationLength; // [rsp+60h] [rbp-A0h]
  __int16 v20; // [rsp+64h] [rbp-9Ch]
  _QWORD v21[5]; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+90h] [rbp-70h]
  __int16 v23; // [rsp+94h] [rbp-6Ch]
  _BYTE v24[56]; // [rsp+98h] [rbp-68h] BYREF
  char v25; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v26[127]; // [rsp+D1h] [rbp-2Fh] BYREF

  memset_0(v26, 0, sizeof(v26));
  v25 = 0;
  TokenInformation = &v25;
  TokenInformationLength = 128;
  v21[4] = v21;
  v20 = 256;
  ReturnLength = 0;
  v21[0] = 0;
  v22 = 32;
  v23 = 256;
  STRU::STRU((STRU *)v24);
  v6 = (void *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a1 + 32LL))(a1);
  if ( GetTokenInformation(v6, TokenUser, &v25, 0x80u, &ReturnLength) )
    goto LABEL_17;
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v9 = 653;
LABEL_16:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\urlauthorization\\url_authz_rule_list.cxx",
        v9,
        "URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal",
        v8,
        "Failed to call GetTokenInformation() to retrieve SIDfor the user context\n");
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  if ( !BUFFER::Resize((BUFFER *)v17, ReturnLength) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v8 = v10;
    goto LABEL_18;
  }
  v11 = TokenInformationLength;
  v12 = TokenInformation;
  v13 = (void *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a1 + 32LL))(a1);
  if ( GetTokenInformation(v13, TokenUser, v12, v11, &ReturnLength) )
  {
LABEL_17:
    *a3 = EqualSid(*(PSID *)TokenInformation, a2);
    v8 = 0;
    goto LABEL_18;
  }
  v14 = GetLastError();
  v8 = v14;
  if ( v14 > 0 )
    v8 = (unsigned __int16)v14 | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v9 = 679;
    goto LABEL_16;
  }
LABEL_18:
  STRU::~STRU((STRU *)v24);
  BUFFER::~BUFFER((BUFFER *)v21);
  BUFFER::~BUFFER((BUFFER *)v17);
  return v8;
}

```

## disassembly

```asm
0x180003438  mov     [rsp-8+arg_18], rbx
0x18000343d  push    rbp
0x18000343e  push    rsi
0x18000343f  push    rdi
0x180003440  push    r14
0x180003442  push    r15
0x180003444  lea     rbp, [rsp-60h]
0x180003449  sub     rsp, 160h
0x180003450  mov     rax, cs:__security_cookie
0x180003457  xor     rax, rsp
0x18000345a  mov     [rbp+80h+var_30], rax
0x18000345e  mov     r14, rdx
0x180003461  mov     r15, r8
0x180003464  xor     edx, edx; Val
0x180003466  mov     rsi, rcx
0x180003469  lea     rcx, [rbp+80h+var_AF]; void *
0x18000346d  lea     r8d, [rdx+7Fh]; Size
0x180003471  call    memset_0
0x180003476  lea     rax, [rbp+80h+var_B0]
0x18000347a  mov     [rbp+80h+var_B0], 0
0x18000347e  mov     [rsp+180h+TokenInformation], rax
0x180003483  lea     rcx, [rbp+80h+var_E8]
0x180003487  lea     rax, [rsp+180h+var_118]
0x18000348c  mov     [rsp+180h+TokenInformationLength], 80h
0x180003494  mov     [rbp+80h+var_F8], rax
0x180003498  mov     [rsp+180h+var_11C], 100h
0x18000349f  mov     [rsp+180h+var_150], 0
0x1800034a7  mov     [rsp+180h+var_118], 0
0x1800034b0  mov     [rbp+80h+var_F0], 20h ; ' '
0x1800034b7  mov     [rbp+80h+var_EC], 100h
0x1800034bd  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800034c3  mov     rax, [rsi]
0x1800034c6  mov     rcx, rsi
0x1800034c9  mov     ebx, [rsp+180h+TokenInformationLength]
0x1800034cd  mov     rdi, [rsp+180h+TokenInformation]
0x1800034d2  mov     rax, [rax+20h]
0x1800034d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034db  lea     rcx, [rsp+180h+var_150]
0x1800034e0  mov     r9d, ebx; TokenInformationLength
0x1800034e3  mov     [rsp+180h+ReturnLength], rcx; ReturnLength
0x1800034e8  mov     r8, rdi; TokenInformation
0x1800034eb  mov     rcx, rax; TokenHandle
0x1800034ee  mov     edx, 1; TokenInformationClass
0x1800034f3  call    cs:__imp_GetTokenInformation
0x1800034f9  test    eax, eax
0x1800034fb  jnz     loc_1800035F0
0x180003501  call    cs:__imp_GetLastError
0x180003507  cmp     eax, 7Ah ; 'z'
0x18000350a  jz      short loc_180003539
0x18000350c  call    cs:__imp_GetLastError
0x180003512  mov     ebx, eax
0x180003514  test    eax, eax
0x180003516  jle     short loc_180003521
0x180003518  movzx   ebx, ax
0x18000351b  or      ebx, 80070000h
0x180003521  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003528  jz      loc_180003606
0x18000352e  mov     r8d, 28Dh
0x180003534  jmp     loc_1800035C3
0x180003539  mov     edx, [rsp+180h+var_150]
0x18000353d  lea     rcx, [rsp+180h+var_148]
0x180003542  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003548  test    al, al
0x18000354a  jnz     short loc_180003565
0x18000354c  call    cs:__imp_GetLastError
0x180003552  test    eax, eax
0x180003554  jle     short loc_18000355E
0x180003556  movzx   eax, ax
0x180003559  or      eax, 80070000h
0x18000355e  mov     ebx, eax
0x180003560  jmp     loc_180003606
0x180003565  mov     rax, [rsi]
0x180003568  mov     rcx, rsi
0x18000356b  mov     ebx, [rsp+180h+TokenInformationLength]
0x18000356f  mov     rdi, [rsp+180h+TokenInformation]
0x180003574  mov     rax, [rax+20h]
0x180003578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000357d  lea     rcx, [rsp+180h+var_150]
0x180003582  mov     r9d, ebx; TokenInformationLength
0x180003585  mov     [rsp+180h+ReturnLength], rcx; ReturnLength
0x18000358a  mov     r8, rdi; TokenInformation
0x18000358d  mov     rcx, rax; TokenHandle
0x180003590  mov     edx, 1; TokenInformationClass
0x180003595  call    cs:__imp_GetTokenInformation
0x18000359b  test    eax, eax
0x18000359d  jnz     short loc_1800035F0
0x18000359f  call    cs:__imp_GetLastError
0x1800035a5  mov     ebx, eax
0x1800035a7  test    eax, eax
0x1800035a9  jle     short loc_1800035B4
0x1800035ab  movzx   ebx, ax
0x1800035ae  or      ebx, 80070000h
0x1800035b4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800035bb  jz      short loc_180003606
0x1800035bd  mov     r8d, 2A7h
0x1800035c3  mov     rcx, cs:g_pDebug
0x1800035ca  lea     rax, aFailedToCallGe; "Failed to call GetTokenInformation() to"...
0x1800035d1  mov     [rsp+180h+var_158], rax
0x1800035d6  lea     r9, aUrlAuthzRuleEn; "URL_AUTHZ_RULE_ENTRY::MatchUserNameForW"...
0x1800035dd  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800035e4  mov     dword ptr [rsp+180h+ReturnLength], ebx
0x1800035e8  call    cs:__imp_PuDbgPrintError
0x1800035ee  jmp     short loc_180003606
0x1800035f0  mov     rcx, [rsp+180h+TokenInformation]
0x1800035f5  mov     rdx, r14; pSid2
0x1800035f8  mov     rcx, [rcx]; pSid1
0x1800035fb  call    cs:__imp_EqualSid
0x180003601  mov     [r15], eax
0x180003604  xor     ebx, ebx
0x180003606  lea     rcx, [rbp+80h+var_E8]
0x18000360a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003610  lea     rcx, [rsp+180h+var_118]
0x180003615  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000361b  lea     rcx, [rsp+180h+var_148]
0x180003620  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003626  mov     eax, ebx
0x180003628  mov     rcx, [rbp+80h+var_30]
0x18000362c  xor     rcx, rsp; StackCookie
0x18000362f  call    __security_check_cookie
0x180003634  mov     rbx, [rsp+180h+arg_18]
0x18000363c  add     rsp, 160h
0x180003643  pop     r15
0x180003645  pop     r14
0x180003647  pop     rdi
0x180003648  pop     rsi
0x180003649  pop     rbp
0x18000364a  retn
```
