# CToken::GetIntegritySID(uchar * *,ushort *)

- ea: `0x180054f10`
- end: `0x18005507b`
- name: `?GetIntegritySID@CToken@@UEAAJPEAPEAEPEAG@Z`
- size: `363`
- prototype: `__int64 __fastcall(CToken *__hidden this, unsigned __int8 **, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180034540`
- `0x180054f10`
- `0x1800a1e98`
- `0x1800b27e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055012`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180054f95`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180054f95`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180054f5d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180054f5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180054fb5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180054fb5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180055050`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180055050`
- `KERNELBASE!LocalAlloc` at `0x180054f6e`
- `KERNELBASE!LocalAlloc` at `0x180054f6e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005502a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180055043`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005502a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180055043`

## string_xrefs

- `0x180055001`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180054ff3`: `GetTokenIntegrityLevel`

## pseudocode

```c
__int64 __fastcall CToken::GetIntegritySID(CToken *this, PSID *a2, unsigned __int16 *a3)
{
  unsigned int v3; // edi
  void *v7; // rdi
  _QWORD *v8; // rax
  void *v9; // rbx
  signed int v10; // eax
  PSID *v11; // rbx
  DWORD LastError; // [rsp+28h] [rbp-50h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-48h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+34h] [rbp-44h] BYREF

  v3 = 0;
  if ( *((_QWORD *)this + 15) )
  {
LABEL_15:
    v11 = (PSID *)*((_QWORD *)this + 15);
    *a3 = GetLengthSid(*v11);
    *a2 = *v11;
    return v3;
  }
  v7 = (void *)*((_QWORD *)this + 9);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  TokenInformationLength = GetSidLengthRequired(1u) + 16;
  v8 = LocalAlloc(0, TokenInformationLength);
  v9 = v8;
  if ( !v8 )
    return (unsigned int)-2147024882;
  *v8 = v8 + 2;
  InitializeSid(v8 + 2, &pIdentifierAuthority, 1u);
  if ( GetTokenInformation(v7, TokenIntegrityLevel, v9, TokenInformationLength, &TokenInformationLength) )
  {
    v3 = 0;
LABEL_13:
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 15, (signed __int64)v9, 0) )
      LocalFree(v9);
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
  v10 = GetLastError();
  v3 = v10;
  if ( v10 > 0 )
    v3 = (unsigned __int16)v10 | 0x80070000;
  LocalFree(v9);
  v9 = 0;
  if ( (v3 & 0x80000000) == 0 )
    goto LABEL_13;
  return v3;
}

```

## disassembly

```asm
0x180054f10  push    rbx
0x180054f12  push    rsi
0x180054f13  push    rdi
0x180054f14  push    r14
0x180054f16  push    r15
0x180054f18  sub     rsp, 50h
0x180054f1c  mov     rax, cs:__security_cookie
0x180054f23  xor     rax, rsp
0x180054f26  mov     [rsp+78h+var_38], rax
0x180054f2b  xor     edi, edi
0x180054f2d  mov     r15, r8
0x180054f30  mov     r14, rdx
0x180054f33  mov     rsi, rcx
0x180054f36  cmp     [rcx+78h], rdi
0x180054f3a  jnz     loc_180055049
0x180054f40  mov     rdi, [rcx+48h]
0x180054f44  mov     cl, 1; nSubAuthorityCount
0x180054f46  mov     [rsp+78h+TokenInformationLength], 0
0x180054f4e  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], 0
0x180054f56  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 1000h
0x180054f5d  call    cs:__imp_GetSidLengthRequired
0x180054f63  add     eax, 10h
0x180054f66  xor     ecx, ecx; uFlags
0x180054f68  mov     edx, eax; uBytes
0x180054f6a  mov     [rsp+78h+TokenInformationLength], eax
0x180054f6e  call    cs:__imp_LocalAlloc
0x180054f74  mov     rbx, rax
0x180054f77  test    rax, rax
0x180054f7a  jnz     short loc_180054F86
0x180054f7c  mov     edi, 8007000Eh
0x180054f81  jmp     loc_180055060
0x180054f86  lea     rcx, [rax+10h]; Sid
0x180054f8a  mov     r8b, 1; nSubAuthorityCount
0x180054f8d  lea     rdx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x180054f92  mov     [rax], rcx
0x180054f95  call    cs:__imp_InitializeSid
0x180054f9b  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x180054fa0  lea     rax, [rsp+78h+TokenInformationLength]
0x180054fa5  mov     r8, rbx; TokenInformation
0x180054fa8  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180054fad  mov     edx, 19h; TokenInformationClass
0x180054fb2  mov     rcx, rdi; TokenHandle
0x180054fb5  call    cs:__imp_GetTokenInformation
0x180054fbb  test    eax, eax
0x180054fbd  jz      short loc_180054FC3
0x180054fbf  xor     edi, edi
0x180054fc1  jmp     short loc_180055036
0x180054fc3  mov     eax, cs:dword_18014E4B8
0x180054fc9  test    eax, eax
0x180054fcb  jnz     short loc_180054FE0
0x180054fcd  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180054fd3  jz      short loc_180055012
0x180054fd5  xor     ecx, ecx
0x180054fd7  call    IsWppLevelEnabled
0x180054fdc  test    al, al
0x180054fde  jz      short loc_180055012
0x180054fe0  call    cs:__imp_GetLastError
0x180054fe6  mov     [rsp+78h+var_50], eax
0x180054fea  xor     r9d, r9d
0x180054fed  mov     r8d, 5E6h
0x180054ff3  lea     rdx, aGettokenintegr; "GetTokenIntegrityLevel"
0x180054ffa  lea     rax, aWinerror; "%!WINERROR!"
0x180055001  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180055008  mov     [rsp+78h+ReturnLength], rax
0x18005500d  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180055012  call    cs:__imp_GetLastError
0x180055018  mov     edi, eax
0x18005501a  test    eax, eax
0x18005501c  jle     short loc_180055027
0x18005501e  movzx   edi, ax
0x180055021  or      edi, 80070000h
0x180055027  mov     rcx, rbx; hMem
0x18005502a  call    cs:__imp_LocalFree
0x180055030  xor     ebx, ebx
0x180055032  test    edi, edi
0x180055034  js      short loc_180055060
0x180055036  xor     eax, eax
0x180055038  lock cmpxchg [rsi+78h], rbx
0x18005503e  jz      short loc_180055049
0x180055040  mov     rcx, rbx; hMem
0x180055043  call    cs:__imp_LocalFree
0x180055049  mov     rbx, [rsi+78h]
0x18005504d  mov     rcx, [rbx]; pSid
0x180055050  call    cs:__imp_GetLengthSid
0x180055056  mov     [r15], ax
0x18005505a  mov     rcx, [rbx]
0x18005505d  mov     [r14], rcx
0x180055060  mov     eax, edi
0x180055062  mov     rcx, [rsp+78h+var_38]
0x180055067  xor     rcx, rsp; StackCookie
0x18005506a  call    __security_check_cookie
0x18005506f  add     rsp, 50h
0x180055073  pop     r15
0x180055075  pop     r14
0x180055077  pop     rdi
0x180055078  pop     rsi
0x180055079  pop     rbx
0x18005507a  retn
```
