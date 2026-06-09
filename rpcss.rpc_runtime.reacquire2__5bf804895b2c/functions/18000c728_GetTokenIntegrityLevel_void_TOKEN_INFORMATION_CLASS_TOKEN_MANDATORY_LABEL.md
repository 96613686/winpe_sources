# GetTokenIntegrityLevel(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_MANDATORY_LABEL * *)

- ea: `0x18000c728`
- end: `0x18000c88c`
- name: `?GetTokenIntegrityLevel@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, struct _TOKEN_MANDATORY_LABEL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c454`

## callees

- `0x18000c728`
- `0x180034260`
- `0x1800a7388`
- `0x1800b7ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c80a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c80a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c842`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18000c7b0`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18000c7b0`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18000c76c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18000c76c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c7d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c7d6`
- `KERNELBASE!LocalAlloc` at `0x18000c783`
- `KERNELBASE!LocalAlloc` at `0x18000c783`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000c860`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000c860`

## string_xrefs

- `0x18000c831`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18000c823`: `GetTokenIntegrityLevel`

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
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+34h] [rbp-24h] BYREF

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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x18000c728  mov     [rsp+arg_8], rbx
0x18000c72d  mov     [rsp+arg_18], rsi
0x18000c732  push    rdi
0x18000c733  sub     rsp, 50h
0x18000c737  mov     rax, cs:__security_cookie
0x18000c73e  xor     rax, rsp
0x18000c741  mov     [rsp+58h+var_18], rax
0x18000c746  mov     rbx, rcx
0x18000c749  mov     [rsp+58h+TokenInformationLength], 0
0x18000c751  mov     cl, 1; nSubAuthorityCount
0x18000c753  mov     dword ptr [rsp+58h+pIdentifierAuthority.Value], 0
0x18000c75b  mov     rsi, r8
0x18000c75e  mov     word ptr [rsp+58h+pIdentifierAuthority.Value+4], 1000h
0x18000c765  mov     qword ptr [r8], 0
0x18000c76c  call    cs:__imp_GetSidLengthRequired
0x18000c773  nop     dword ptr [rax+rax+00h]
0x18000c778  add     eax, 10h
0x18000c77b  xor     ecx, ecx; uFlags
0x18000c77d  mov     edx, eax; uBytes
0x18000c77f  mov     [rsp+58h+TokenInformationLength], eax
0x18000c783  call    cs:__imp_LocalAlloc
0x18000c78a  nop     dword ptr [rax+rax+00h]
0x18000c78f  mov     rdi, rax
0x18000c792  test    rax, rax
0x18000c795  jnz     short loc_18000C7A1
0x18000c797  mov     eax, 8007000Eh
0x18000c79c  jmp     loc_18000C86E
0x18000c7a1  lea     rcx, [rax+10h]; Sid
0x18000c7a5  mov     r8b, 1; nSubAuthorityCount
0x18000c7a8  lea     rdx, [rsp+58h+pIdentifierAuthority]; pIdentifierAuthority
0x18000c7ad  mov     [rax], rcx
0x18000c7b0  call    cs:__imp_InitializeSid
0x18000c7b7  nop     dword ptr [rax+rax+00h]
0x18000c7bc  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000c7c1  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c7c6  mov     r8, rdi; TokenInformation
0x18000c7c9  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c7ce  mov     edx, 19h; TokenInformationClass
0x18000c7d3  mov     rcx, rbx; TokenHandle
0x18000c7d6  call    cs:__imp_GetTokenInformation
0x18000c7dd  nop     dword ptr [rax+rax+00h]
0x18000c7e2  test    eax, eax
0x18000c7e4  jz      short loc_18000C7ED
0x18000c7e6  xor     ebx, ebx
0x18000c7e8  mov     [rsi], rdi
0x18000c7eb  jmp     short loc_18000C86C
0x18000c7ed  mov     eax, cs:dword_1801574B8
0x18000c7f3  test    eax, eax
0x18000c7f5  jnz     short loc_18000C80A
0x18000c7f7  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18000c7fd  jz      short loc_18000C842
0x18000c7ff  xor     ecx, ecx
0x18000c801  call    IsWppLevelEnabled
0x18000c806  test    al, al
0x18000c808  jz      short loc_18000C842
0x18000c80a  call    cs:__imp_GetLastError
0x18000c811  nop     dword ptr [rax+rax+00h]
0x18000c816  mov     [rsp+58h+var_30], eax
0x18000c81a  xor     r9d, r9d
0x18000c81d  mov     r8d, 5E6h
0x18000c823  lea     rdx, aGettokenintegr; "GetTokenIntegrityLevel"
0x18000c82a  lea     rax, aWinerror; "%!WINERROR!"
0x18000c831  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18000c838  mov     [rsp+58h+ReturnLength], rax
0x18000c83d  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18000c842  call    cs:__imp_GetLastError
0x18000c849  nop     dword ptr [rax+rax+00h]
0x18000c84e  mov     ebx, eax
0x18000c850  test    eax, eax
0x18000c852  jle     short loc_18000C85D
0x18000c854  movzx   ebx, ax
0x18000c857  or      ebx, 80070000h
0x18000c85d  mov     rcx, rdi; hMem
0x18000c860  call    cs:__imp_LocalFree
0x18000c867  nop     dword ptr [rax+rax+00h]
0x18000c86c  mov     eax, ebx
0x18000c86e  mov     rcx, [rsp+58h+var_18]
0x18000c873  xor     rcx, rsp; StackCookie
0x18000c876  call    __security_check_cookie
0x18000c87b  mov     rbx, [rsp+58h+arg_8]
0x18000c880  mov     rsi, [rsp+58h+arg_18]
0x18000c885  add     rsp, 50h
0x18000c889  pop     rdi
0x18000c88a  retn
```
