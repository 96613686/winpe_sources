# CToken::GetTokenIntegrityLevel(_TOKEN_MANDATORY_LABEL * *)

- ea: `0x180025910`
- end: `0x180025a6e`
- name: `?GetTokenIntegrityLevel@CToken@@UEAAJPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(CToken *__hidden this, struct _TOKEN_MANDATORY_LABEL **)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800257f8`
- `0x180025884`
- `0x18005c14c`
- `0x18006e800`
- `0x180072b5c`
- `0x180076450`
- `0x1800a0184`
- `0x1800a1ad4`

## callees

- `0x180025910`
- `0x180034540`
- `0x1800a1e98`
- `0x1800b27e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a10`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180025993`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180025993`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002595b`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002595b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800259b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800259b3`
- `KERNELBASE!LocalAlloc` at `0x18002596c`
- `KERNELBASE!LocalAlloc` at `0x18002596c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180025a28`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180025a41`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180025a28`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180025a41`

## string_xrefs

- `0x1800259ff`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800259f1`: `GetTokenIntegrityLevel`

## pseudocode

```c
__int64 __fastcall CToken::GetTokenIntegrityLevel(CToken *this, struct _TOKEN_MANDATORY_LABEL **a2)
{
  signed int v2; // ebx
  void *v5; // rbx
  _QWORD *v6; // rax
  void *v7; // rdi
  signed int v8; // eax
  __int64 result; // rax
  DWORD LastError; // [rsp+28h] [rbp-40h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-38h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+34h] [rbp-34h] BYREF

  v2 = 0;
  if ( *((_QWORD *)this + 15) )
    goto LABEL_15;
  v5 = (void *)*((_QWORD *)this + 9);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  TokenInformationLength = GetSidLengthRequired(1u) + 16;
  v6 = LocalAlloc(0, TokenInformationLength);
  v7 = v6;
  if ( !v6 )
  {
    v2 = -2147024882;
    goto LABEL_15;
  }
  *v6 = v6 + 2;
  InitializeSid(v6 + 2, &pIdentifierAuthority, 1u);
  if ( GetTokenInformation(v5, TokenIntegrityLevel, v7, TokenInformationLength, &TokenInformationLength) )
  {
    v2 = 0;
LABEL_13:
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 15, (signed __int64)v7, 0) )
      LocalFree(v7);
    goto LABEL_15;
  }
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    LastError = GetLastError();
    ComTraceMessageT<int>(
      (__int64)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
      (__int64)"GetTokenIntegrityLevel",
      0x5E6u,
      0,
      (__int64)L"%!WINERROR!",
      LastError);
  }
  v8 = GetLastError();
  v2 = v8;
  if ( v8 > 0 )
    v2 = (unsigned __int16)v8 | 0x80070000;
  LocalFree(v7);
  v7 = 0;
  if ( v2 >= 0 )
    goto LABEL_13;
LABEL_15:
  result = (unsigned int)v2;
  *a2 = (struct _TOKEN_MANDATORY_LABEL *)*((_QWORD *)this + 15);
  return result;
}

```

## disassembly

```asm
0x180025910  mov     [rsp+arg_10], rbx
0x180025915  push    rsi
0x180025916  push    rdi
0x180025917  push    r14
0x180025919  sub     rsp, 50h
0x18002591d  mov     rax, cs:__security_cookie
0x180025924  xor     rax, rsp
0x180025927  mov     [rsp+68h+var_28], rax
0x18002592c  xor     ebx, ebx
0x18002592e  mov     r14, rdx
0x180025931  mov     rsi, rcx
0x180025934  cmp     [rcx+78h], rbx
0x180025938  jnz     loc_180025A47
0x18002593e  mov     rbx, [rcx+48h]
0x180025942  mov     cl, 1; nSubAuthorityCount
0x180025944  mov     [rsp+68h+TokenInformationLength], 0
0x18002594c  mov     dword ptr [rsp+68h+pIdentifierAuthority.Value], 0
0x180025954  mov     word ptr [rsp+68h+pIdentifierAuthority.Value+4], 1000h
0x18002595b  call    cs:__imp_GetSidLengthRequired
0x180025961  add     eax, 10h
0x180025964  xor     ecx, ecx; uFlags
0x180025966  mov     edx, eax; uBytes
0x180025968  mov     [rsp+68h+TokenInformationLength], eax
0x18002596c  call    cs:__imp_LocalAlloc
0x180025972  mov     rdi, rax
0x180025975  test    rax, rax
0x180025978  jnz     short loc_180025984
0x18002597a  mov     ebx, 8007000Eh
0x18002597f  jmp     loc_180025A47
0x180025984  lea     rcx, [rax+10h]; Sid
0x180025988  mov     r8b, 1; nSubAuthorityCount
0x18002598b  lea     rdx, [rsp+68h+pIdentifierAuthority]; pIdentifierAuthority
0x180025990  mov     [rax], rcx
0x180025993  call    cs:__imp_InitializeSid
0x180025999  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18002599e  lea     rax, [rsp+68h+TokenInformationLength]
0x1800259a3  mov     r8, rdi; TokenInformation
0x1800259a6  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800259ab  mov     edx, 19h; TokenInformationClass
0x1800259b0  mov     rcx, rbx; TokenHandle
0x1800259b3  call    cs:__imp_GetTokenInformation
0x1800259b9  test    eax, eax
0x1800259bb  jz      short loc_1800259C1
0x1800259bd  xor     ebx, ebx
0x1800259bf  jmp     short loc_180025A34
0x1800259c1  mov     eax, cs:dword_18014E4B8
0x1800259c7  test    eax, eax
0x1800259c9  jnz     short loc_1800259DE
0x1800259cb  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800259d1  jz      short loc_180025A10
0x1800259d3  xor     ecx, ecx
0x1800259d5  call    IsWppLevelEnabled
0x1800259da  test    al, al
0x1800259dc  jz      short loc_180025A10
0x1800259de  call    cs:__imp_GetLastError
0x1800259e4  mov     [rsp+68h+var_40], eax
0x1800259e8  xor     r9d, r9d
0x1800259eb  mov     r8d, 5E6h
0x1800259f1  lea     rdx, aGettokenintegr; "GetTokenIntegrityLevel"
0x1800259f8  lea     rax, aWinerror; "%!WINERROR!"
0x1800259ff  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180025a06  mov     [rsp+68h+ReturnLength], rax
0x180025a0b  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180025a10  call    cs:__imp_GetLastError
0x180025a16  mov     ebx, eax
0x180025a18  test    eax, eax
0x180025a1a  jle     short loc_180025A25
0x180025a1c  movzx   ebx, ax
0x180025a1f  or      ebx, 80070000h
0x180025a25  mov     rcx, rdi; hMem
0x180025a28  call    cs:__imp_LocalFree
0x180025a2e  xor     edi, edi
0x180025a30  test    ebx, ebx
0x180025a32  js      short loc_180025A47
0x180025a34  xor     eax, eax
0x180025a36  lock cmpxchg [rsi+78h], rdi
0x180025a3c  jz      short loc_180025A47
0x180025a3e  mov     rcx, rdi; hMem
0x180025a41  call    cs:__imp_LocalFree
0x180025a47  mov     rcx, [rsi+78h]
0x180025a4b  mov     eax, ebx
0x180025a4d  mov     [r14], rcx
0x180025a50  mov     rcx, [rsp+68h+var_28]
0x180025a55  xor     rcx, rsp; StackCookie
0x180025a58  call    __security_check_cookie
0x180025a5d  mov     rbx, [rsp+68h+arg_10]
0x180025a65  add     rsp, 50h
0x180025a69  pop     r14
0x180025a6b  pop     rdi
0x180025a6c  pop     rsi
0x180025a6d  retn
```
