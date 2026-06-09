# CToken::GetIntegritySID(uchar * *,ushort *)

- ea: `0x18005b0f0`
- end: `0x18005b295`
- name: `?GetIntegritySID@CToken@@UEAAJPEAPEAEPEAG@Z`
- size: `421`
- prototype: `__int64 __fastcall(CToken *__hidden this, unsigned __int8 **, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180034260`
- `0x18005b0f0`
- `0x1800a7388`
- `0x1800b7ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b1db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b1db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b213`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005b181`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18005b181`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005b13d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005b13d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005b1a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005b1a7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005b263`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005b263`
- `KERNELBASE!LocalAlloc` at `0x18005b154`
- `KERNELBASE!LocalAlloc` at `0x18005b154`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005b231`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005b250`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005b231`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005b250`

## string_xrefs

- `0x18005b202`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18005b1f4`: `GetTokenIntegrityLevel`

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
0x18005b0f0  push    rbx
0x18005b0f2  push    rsi
0x18005b0f3  push    rdi
0x18005b0f4  push    r14
0x18005b0f6  push    r15
0x18005b0f8  sub     rsp, 50h
0x18005b0fc  mov     rax, cs:__security_cookie
0x18005b103  xor     rax, rsp
0x18005b106  mov     [rsp+78h+var_38], rax
0x18005b10b  xor     edi, edi
0x18005b10d  mov     r15, r8
0x18005b110  mov     r14, rdx
0x18005b113  mov     rsi, rcx
0x18005b116  cmp     [rcx+78h], rdi
0x18005b11a  jnz     loc_18005B25C
0x18005b120  mov     rdi, [rcx+48h]
0x18005b124  mov     cl, 1; nSubAuthorityCount
0x18005b126  mov     [rsp+78h+TokenInformationLength], 0
0x18005b12e  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], 0
0x18005b136  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 1000h
0x18005b13d  call    cs:__imp_GetSidLengthRequired
0x18005b144  nop     dword ptr [rax+rax+00h]
0x18005b149  add     eax, 10h
0x18005b14c  xor     ecx, ecx; uFlags
0x18005b14e  mov     edx, eax; uBytes
0x18005b150  mov     [rsp+78h+TokenInformationLength], eax
0x18005b154  call    cs:__imp_LocalAlloc
0x18005b15b  nop     dword ptr [rax+rax+00h]
0x18005b160  mov     rbx, rax
0x18005b163  test    rax, rax
0x18005b166  jnz     short loc_18005B172
0x18005b168  mov     edi, 8007000Eh
0x18005b16d  jmp     loc_18005B279
0x18005b172  lea     rcx, [rax+10h]; Sid
0x18005b176  mov     r8b, 1; nSubAuthorityCount
0x18005b179  lea     rdx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x18005b17e  mov     [rax], rcx
0x18005b181  call    cs:__imp_InitializeSid
0x18005b188  nop     dword ptr [rax+rax+00h]
0x18005b18d  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x18005b192  lea     rax, [rsp+78h+TokenInformationLength]
0x18005b197  mov     r8, rbx; TokenInformation
0x18005b19a  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18005b19f  mov     edx, 19h; TokenInformationClass
0x18005b1a4  mov     rcx, rdi; TokenHandle
0x18005b1a7  call    cs:__imp_GetTokenInformation
0x18005b1ae  nop     dword ptr [rax+rax+00h]
0x18005b1b3  test    eax, eax
0x18005b1b5  jz      short loc_18005B1BE
0x18005b1b7  xor     edi, edi
0x18005b1b9  jmp     loc_18005B243
0x18005b1be  mov     eax, cs:dword_1801574B8
0x18005b1c4  test    eax, eax
0x18005b1c6  jnz     short loc_18005B1DB
0x18005b1c8  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18005b1ce  jz      short loc_18005B213
0x18005b1d0  xor     ecx, ecx
0x18005b1d2  call    IsWppLevelEnabled
0x18005b1d7  test    al, al
0x18005b1d9  jz      short loc_18005B213
0x18005b1db  call    cs:__imp_GetLastError
0x18005b1e2  nop     dword ptr [rax+rax+00h]
0x18005b1e7  mov     [rsp+78h+var_50], eax
0x18005b1eb  xor     r9d, r9d
0x18005b1ee  mov     r8d, 5E6h
0x18005b1f4  lea     rdx, aGettokenintegr; "GetTokenIntegrityLevel"
0x18005b1fb  lea     rax, aWinerror; "%!WINERROR!"
0x18005b202  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18005b209  mov     [rsp+78h+ReturnLength], rax
0x18005b20e  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18005b213  call    cs:__imp_GetLastError
0x18005b21a  nop     dword ptr [rax+rax+00h]
0x18005b21f  mov     edi, eax
0x18005b221  test    eax, eax
0x18005b223  jle     short loc_18005B22E
0x18005b225  movzx   edi, ax
0x18005b228  or      edi, 80070000h
0x18005b22e  mov     rcx, rbx; hMem
0x18005b231  call    cs:__imp_LocalFree
0x18005b238  nop     dword ptr [rax+rax+00h]
0x18005b23d  xor     ebx, ebx
0x18005b23f  test    edi, edi
0x18005b241  js      short loc_18005B279
0x18005b243  xor     eax, eax
0x18005b245  lock cmpxchg [rsi+78h], rbx
0x18005b24b  jz      short loc_18005B25C
0x18005b24d  mov     rcx, rbx; hMem
0x18005b250  call    cs:__imp_LocalFree
0x18005b257  nop     dword ptr [rax+rax+00h]
0x18005b25c  mov     rbx, [rsi+78h]
0x18005b260  mov     rcx, [rbx]; pSid
0x18005b263  call    cs:__imp_GetLengthSid
0x18005b26a  nop     dword ptr [rax+rax+00h]
0x18005b26f  mov     [r15], ax
0x18005b273  mov     rcx, [rbx]
0x18005b276  mov     [r14], rcx
0x18005b279  mov     eax, edi
0x18005b27b  mov     rcx, [rsp+78h+var_38]
0x18005b280  xor     rcx, rsp; StackCookie
0x18005b283  call    __security_check_cookie
0x18005b288  add     rsp, 50h
0x18005b28c  pop     r15
0x18005b28e  pop     r14
0x18005b290  pop     rdi
0x18005b291  pop     rsi
0x18005b292  pop     rbx
0x18005b293  retn
```
