# CToken::GetTokenIntegrityLevel(_TOKEN_MANDATORY_LABEL * *)

- ea: `0x18002fcb0`
- end: `0x18002fe42`
- name: `?GetTokenIntegrityLevel@CToken@@UEAAJPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(CToken *__hidden this, struct _TOKEN_MANDATORY_LABEL **)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c454`
- `0x18002fb7c`
- `0x18002fc10`
- `0x180073020`
- `0x1800771c8`
- `0x18007ab08`
- `0x1800a3e30`

## callees

- `0x18002fcb0`
- `0x180034260`
- `0x1800a7388`
- `0x1800b7ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fdd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fdd1`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002fd3f`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002fd3f`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002fcfb`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002fcfb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002fd65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002fd65`
- `KERNELBASE!LocalAlloc` at `0x18002fd12`
- `KERNELBASE!LocalAlloc` at `0x18002fd12`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002fdef`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002fe0e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002fdef`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002fe0e`

## string_xrefs

- `0x18002fdc0`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18002fdb2`: `GetTokenIntegrityLevel`

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
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+34h] [rbp-34h] BYREF

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
0x18002fcb0  mov     [rsp+arg_10], rbx
0x18002fcb5  push    rsi
0x18002fcb6  push    rdi
0x18002fcb7  push    r14
0x18002fcb9  sub     rsp, 50h
0x18002fcbd  mov     rax, cs:__security_cookie
0x18002fcc4  xor     rax, rsp
0x18002fcc7  mov     [rsp+68h+var_28], rax
0x18002fccc  xor     ebx, ebx
0x18002fcce  mov     r14, rdx
0x18002fcd1  mov     rsi, rcx
0x18002fcd4  cmp     [rcx+78h], rbx
0x18002fcd8  jnz     loc_18002FE1A
0x18002fcde  mov     rbx, [rcx+48h]
0x18002fce2  mov     cl, 1; nSubAuthorityCount
0x18002fce4  mov     [rsp+68h+TokenInformationLength], 0
0x18002fcec  mov     dword ptr [rsp+68h+pIdentifierAuthority.Value], 0
0x18002fcf4  mov     word ptr [rsp+68h+pIdentifierAuthority.Value+4], 1000h
0x18002fcfb  call    cs:__imp_GetSidLengthRequired
0x18002fd02  nop     dword ptr [rax+rax+00h]
0x18002fd07  add     eax, 10h
0x18002fd0a  xor     ecx, ecx; uFlags
0x18002fd0c  mov     edx, eax; uBytes
0x18002fd0e  mov     [rsp+68h+TokenInformationLength], eax
0x18002fd12  call    cs:__imp_LocalAlloc
0x18002fd19  nop     dword ptr [rax+rax+00h]
0x18002fd1e  mov     rdi, rax
0x18002fd21  test    rax, rax
0x18002fd24  jnz     short loc_18002FD30
0x18002fd26  mov     ebx, 8007000Eh
0x18002fd2b  jmp     loc_18002FE1A
0x18002fd30  lea     rcx, [rax+10h]; Sid
0x18002fd34  mov     r8b, 1; nSubAuthorityCount
0x18002fd37  lea     rdx, [rsp+68h+pIdentifierAuthority]; pIdentifierAuthority
0x18002fd3c  mov     [rax], rcx
0x18002fd3f  call    cs:__imp_InitializeSid
0x18002fd46  nop     dword ptr [rax+rax+00h]
0x18002fd4b  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18002fd50  lea     rax, [rsp+68h+TokenInformationLength]
0x18002fd55  mov     r8, rdi; TokenInformation
0x18002fd58  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18002fd5d  mov     edx, 19h; TokenInformationClass
0x18002fd62  mov     rcx, rbx; TokenHandle
0x18002fd65  call    cs:__imp_GetTokenInformation
0x18002fd6c  nop     dword ptr [rax+rax+00h]
0x18002fd71  test    eax, eax
0x18002fd73  jz      short loc_18002FD7C
0x18002fd75  xor     ebx, ebx
0x18002fd77  jmp     loc_18002FE01
0x18002fd7c  mov     eax, cs:dword_1801574B8
0x18002fd82  test    eax, eax
0x18002fd84  jnz     short loc_18002FD99
0x18002fd86  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18002fd8c  jz      short loc_18002FDD1
0x18002fd8e  xor     ecx, ecx
0x18002fd90  call    IsWppLevelEnabled
0x18002fd95  test    al, al
0x18002fd97  jz      short loc_18002FDD1
0x18002fd99  call    cs:__imp_GetLastError
0x18002fda0  nop     dword ptr [rax+rax+00h]
0x18002fda5  mov     [rsp+68h+var_40], eax
0x18002fda9  xor     r9d, r9d
0x18002fdac  mov     r8d, 5E6h
0x18002fdb2  lea     rdx, aGettokenintegr; "GetTokenIntegrityLevel"
0x18002fdb9  lea     rax, aWinerror; "%!WINERROR!"
0x18002fdc0  lea     rcx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18002fdc7  mov     [rsp+68h+ReturnLength], rax
0x18002fdcc  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x18002fdd1  call    cs:__imp_GetLastError
0x18002fdd8  nop     dword ptr [rax+rax+00h]
0x18002fddd  mov     ebx, eax
0x18002fddf  test    eax, eax
0x18002fde1  jle     short loc_18002FDEC
0x18002fde3  movzx   ebx, ax
0x18002fde6  or      ebx, 80070000h
0x18002fdec  mov     rcx, rdi; hMem
0x18002fdef  call    cs:__imp_LocalFree
0x18002fdf6  nop     dword ptr [rax+rax+00h]
0x18002fdfb  xor     edi, edi
0x18002fdfd  test    ebx, ebx
0x18002fdff  js      short loc_18002FE1A
0x18002fe01  xor     eax, eax
0x18002fe03  lock cmpxchg [rsi+78h], rdi
0x18002fe09  jz      short loc_18002FE1A
0x18002fe0b  mov     rcx, rdi; hMem
0x18002fe0e  call    cs:__imp_LocalFree
0x18002fe15  nop     dword ptr [rax+rax+00h]
0x18002fe1a  mov     rcx, [rsi+78h]
0x18002fe1e  mov     eax, ebx
0x18002fe20  mov     [r14], rcx
0x18002fe23  mov     rcx, [rsp+68h+var_28]
0x18002fe28  xor     rcx, rsp; StackCookie
0x18002fe2b  call    __security_check_cookie
0x18002fe30  mov     rbx, [rsp+68h+arg_10]
0x18002fe38  add     rsp, 50h
0x18002fe3c  pop     r14
0x18002fe3e  pop     rdi
0x18002fe3f  pop     rsi
0x18002fe40  retn
```
