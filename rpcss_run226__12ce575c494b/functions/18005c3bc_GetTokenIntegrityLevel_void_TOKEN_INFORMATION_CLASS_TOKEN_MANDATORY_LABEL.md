# GetTokenIntegrityLevel(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_MANDATORY_LABEL * *)

- ea: `0x18005c3bc`
- end: `0x18005c4f5`
- name: `?GetTokenIntegrityLevel@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, struct _TOKEN_MANDATORY_LABEL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005c14c`

## callees

- `0x180034540`
- `0x18005c3bc`
- `0x1800a1e98`
- `0x1800b27e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c4b8`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005c438`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005c438`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005c400`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005c400`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c458`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c458`
- `KERNELBASE!LocalAlloc` at `0x18005c411`
- `KERNELBASE!LocalAlloc` at `0x18005c411`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c4d0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c4d0`

## string_xrefs

- `0x18005c4a7`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18005c499`: `GetTokenIntegrityLevel`

## pseudocode

```c
__int64 __fastcall GetTokenIntegrityLevel(
        HANDLE TokenHandle,
        enum _TOKEN_INFORMATION_CLASS a2,
        struct _TOKEN_MANDATORY_LABEL **a3)
{
  struct _TOKEN_MANDATORY_LABEL *v5; // rax
  struct _TOKEN_MANDATORY_LABEL *v6; // rdi
  unsigned int v8; // ebx
  signed int v9; // eax
  DWORD LastError; // [rsp+28h] [rbp-30h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+34h] [rbp-24h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  *a3 = 0;
  TokenInformationLength = GetSidLengthRequired(1u) + 16;
  v5 = (struct _TOKEN_MANDATORY_LABEL *)LocalAlloc(0, TokenInformationLength);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v5->Label.Sid = &v5[1];
  InitializeSid(&v5[1], &pIdentifierAuthority, 1u);
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v6, TokenInformationLength, &TokenInformationLength) )
  {
    v8 = 0;
    *a3 = v6;
  }
  else
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      LastError = GetLastError();
      ComTraceMessageT<int>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
        (unsigned int)"GetTokenIntegrityLevel",
        1510,
        0,
        (__int64)L"%!WINERROR!",
        LastError);
    }
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    LocalFree(v6);
  }
  return v8;
}

```

## disassembly

```asm
0x18005c3bc  mov     [rsp+arg_8], rbx
0x18005c3c1  mov     [rsp+arg_18], rsi
0x18005c3c6  push    rdi
0x18005c3c7  sub     rsp, 50h
0x18005c3cb  mov     rax, cs:__security_cookie
0x18005c3d2  xor     rax, rsp
0x18005c3d5  mov     [rsp+58h+var_18], rax
0x18005c3da  mov     rbx, rcx
0x18005c3dd  mov     [rsp+58h+TokenInformationLength], 0
0x18005c3e5  mov     cl, 1; nSubAuthorityCount
0x18005c3e7  mov     dword ptr [rsp+58h+pIdentifierAuthority.Value], 0
0x18005c3ef  mov     rsi, r8
0x18005c3f2  mov     word ptr [rsp+58h+pIdentifierAuthority.Value+4], 1000h
0x18005c3f9  mov     qword ptr [r8], 0
0x18005c400  call    cs:__imp_GetSidLengthRequired
0x18005c406  add     eax, 10h
0x18005c409  xor     ecx, ecx; uFlags
0x18005c40b  mov     edx, eax; uBytes
0x18005c40d  mov     [rsp+58h+TokenInformationLength], eax
0x18005c411  call    cs:__imp_LocalAlloc
0x18005c417  mov     rdi, rax
0x18005c41a  test    rax, rax
0x18005c41d  jnz     short loc_18005C429
0x18005c41f  mov     eax, 8007000Eh
0x18005c424  jmp     loc_18005C4D8
0x18005c429  lea     rcx, [rax+10h]; Sid
0x18005c42d  mov     r8b, 1; nSubAuthorityCount
0x18005c430  lea     rdx, [rsp+58h+pIdentifierAuthority]; pIdentifierAuthority
0x18005c435  mov     [rax], rcx
0x18005c438  call    cs:__imp_InitializeSid
0x18005c43e  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18005c443  lea     rax, [rsp+58h+TokenInformationLength]
0x18005c448  mov     r8, rdi; TokenInformation
0x18005c44b  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18005c450  mov     edx, 19h; TokenInformationClass
0x18005c455  mov     rcx, rbx; TokenHandle
0x18005c458  call    cs:__imp_GetTokenInformation
0x18005c45e  test    eax, eax
0x18005c460  jz      short loc_18005C469
0x18005c462  xor     ebx, ebx
0x18005c464  mov     [rsi], rdi
0x18005c467  jmp     short loc_18005C4D6
0x18005c469  mov     eax, cs:dword_18014E4B8
0x18005c46f  test    eax, eax
0x18005c471  jnz     short loc_18005C486
0x18005c473  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18005c479  jz      short loc_18005C4B8
0x18005c47b  xor     ecx, ecx
0x18005c47d  call    IsWppLevelEnabled
0x18005c482  test    al, al
0x18005c484  jz      short loc_18005C4B8
0x18005c486  call    cs:__imp_GetLastError
0x18005c48c  mov     [rsp+58h+var_30], eax
0x18005c490  xor     r9d, r9d
0x18005c493  mov     r8d, 5E6h
0x18005c499  lea     rdx, aGettokenintegr; "GetTokenIntegrityLevel"
0x18005c4a0  lea     rax, aWinerror; "%!WINERROR!"
0x18005c4a7  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18005c4ae  mov     [rsp+58h+ReturnLength], rax
0x18005c4b3  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18005c4b8  call    cs:__imp_GetLastError
0x18005c4be  mov     ebx, eax
0x18005c4c0  test    eax, eax
0x18005c4c2  jle     short loc_18005C4CD
0x18005c4c4  movzx   ebx, ax
0x18005c4c7  or      ebx, 80070000h
0x18005c4cd  mov     rcx, rdi; hMem
0x18005c4d0  call    cs:__imp_LocalFree
0x18005c4d6  mov     eax, ebx
0x18005c4d8  mov     rcx, [rsp+58h+var_18]
0x18005c4dd  xor     rcx, rsp; StackCookie
0x18005c4e0  call    __security_check_cookie
0x18005c4e5  mov     rbx, [rsp+58h+arg_8]
0x18005c4ea  mov     rsi, [rsp+58h+arg_18]
0x18005c4ef  add     rsp, 50h
0x18005c4f3  pop     rdi
0x18005c4f4  retn
```
