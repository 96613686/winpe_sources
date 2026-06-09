# GetUserGuid(void *,ushort * *)

- ea: `0x18001c16c`
- end: `0x18001c3ea`
- name: `?GetUserGuid@@YAJPEAXPEAPEAG@Z`
- size: `638`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c00c`

## callees

- `0x180005e10`
- `0x180006a98`
- `0x18000da0c`
- `0x18000db08`
- `0x18000dc30`
- `0x18000e640`
- `0x18001136c`
- `0x1800114c4`
- `0x18001a4b8`
- `0x18001b3b4`
- `0x18001bfec`
- `0x18001c16c`
- `0x18001c3f0`
- `0x18001c51c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001c296`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001c296`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c211`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c211`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c1c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c1c3`

## string_xrefs

- `0x18001c225`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001c264`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001c2be`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001c358`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001c395`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001c2aa`: `User SID matches local system, returning Invalid Arg.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUserGuid(HANDLE TokenHandle, unsigned __int16 **a2)
{
  const char *v4; // r9
  unsigned int LastError; // ebx
  int UserSid; // eax
  int UserNameAlloc; // eax
  int v8; // edx
  int nSubAuthority2; // [rsp+20h] [rbp-29h]
  const char *nSubAuthority3; // [rsp+28h] [rbp-21h]
  HLOCAL hMem; // [rsp+60h] [rbp+17h] BYREF
  PSID pSid1; // [rsp+68h] [rbp+1Fh] BYREF
  void *v14; // [rsp+70h] [rbp+27h] BYREF
  char v15; // [rsp+78h] [rbp+2Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a2 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  hMem = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &hMem) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x99,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
                  v4);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  pSid1 = 0;
  UserSid = GetUserSid(TokenHandle, &pSid1);
  LastError = UserSid;
  if ( UserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)UserSid,
      nSubAuthority2);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  if ( EqualSid(pSid1, hMem) )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)0x80070057LL,
      (int)"User SID matches local system, returning Invalid Arg.",
      nSubAuthority3);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  v14 = 0;
  v15 = 0;
  LastError = -2147467259;
  if ( !TokenHandle )
  {
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)LastError,
      nSubAuthority2);
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v14);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v14);
  LastError = ImpersonateUser(TokenHandle, &v14);
  if ( (LastError & 0x80000000) != 0 )
  {
    v15 = 0;
    goto LABEL_17;
  }
  v15 = 1;
  UserNameAlloc = GetUserNameAlloc(NameUniqueId, a2);
  if ( (unsigned int)(UserNameAlloc + 2147023564) > 0x17 || (v8 = 8912897, !_bittest(&v8, UserNameAlloc + 2147023564)) )
  {
    if ( UserNameAlloc != -2147024846 && UserNameAlloc != -2147023684 && UserNameAlloc < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        (const char *)(unsigned int)UserNameAlloc,
        nSubAuthority2);
  }
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v14);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
  return 0;
}

```

## disassembly

```asm
0x18001c16c  mov     [rsp-8+arg_10], rbx
0x18001c171  mov     [rsp-8+arg_18], rsi
0x18001c176  push    rbp
0x18001c177  push    rdi
0x18001c178  push    r14
0x18001c17a  lea     rbp, [rsp-47h]
0x18001c17f  sub     rsp, 90h
0x18001c186  mov     rax, cs:__security_cookie
0x18001c18d  xor     rax, rsp
0x18001c190  mov     [rbp+57h+var_18], rax
0x18001c194  mov     rsi, rdx
0x18001c197  mov     rdi, rcx
0x18001c19a  xor     r14d, r14d
0x18001c19d  mov     [rdx], r14
0x18001c1a0  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18001c1a4  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001c1aa  mov     [rbp+57h+hMem], r14
0x18001c1ae  mov     rbx, [rbp+57h+hMem]
0x18001c1b2  test    rbx, rbx
0x18001c1b5  jz      short loc_18001C1D9
0x18001c1b7  lea     rcx, [rbp+57h+pSid1]; this
0x18001c1bb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001c1c0  mov     rcx, rbx; hMem
0x18001c1c3  call    cs:__imp_LocalFree
0x18001c1ca  nop     dword ptr [rax+rax+00h]
0x18001c1cf  lea     rcx, [rbp+57h+pSid1]; this
0x18001c1d3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001c1d8  nop
0x18001c1d9  mov     [rbp+57h+hMem], r14
0x18001c1dd  lea     rax, [rbp+57h+hMem]
0x18001c1e1  mov     [rsp+0A0h+pSid], rax; pSid
0x18001c1e6  mov     [rsp+0A0h+nSubAuthority7], r14d; nSubAuthority7
0x18001c1eb  mov     [rsp+0A0h+nSubAuthority6], r14d; nSubAuthority6
0x18001c1f0  mov     [rsp+0A0h+nSubAuthority5], r14d; nSubAuthority5
0x18001c1f5  mov     [rsp+0A0h+nSubAuthority4], r14d; nSubAuthority4
0x18001c1fa  mov     dword ptr [rsp+0A0h+nSubAuthority3], r14d; char *
0x18001c1ff  mov     [rsp+0A0h+nSubAuthority2], r14d; int
0x18001c204  xor     r9d, r9d; nSubAuthority1
0x18001c207  lea     r8d, [r9+12h]; nSubAuthority0
0x18001c20b  mov     dl, 1; nSubAuthorityCount
0x18001c20d  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001c211  call    cs:__imp_AllocateAndInitializeSid
0x18001c218  nop     dword ptr [rax+rax+00h]
0x18001c21d  test    eax, eax
0x18001c21f  jnz     short loc_18001C247
0x18001c221  mov     rcx, [rbp+5Fh]; this
0x18001c225  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c22c  mov     edx, 99h; void *
0x18001c231  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c236  mov     ebx, eax
0x18001c238  lea     rcx, [rbp+57h+hMem]
0x18001c23c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c241  nop
0x18001c242  jmp     loc_18001C3C3
0x18001c247  mov     [rbp+57h+pSid1], r14
0x18001c24b  lea     rdx, [rbp+57h+pSid1]; void **
0x18001c24f  mov     rcx, rdi; TokenHandle
0x18001c252  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x18001c257  mov     ebx, eax
0x18001c259  test    eax, eax
0x18001c25b  jns     short loc_18001C28E
0x18001c25d  mov     rcx, [rbp+5Fh]; this
0x18001c261  mov     r9d, eax; char *
0x18001c264  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c26b  mov     edx, 9Ch; void *
0x18001c270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c275  lea     rcx, [rbp+57h+pSid1]
0x18001c279  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c27e  nop
0x18001c27f  lea     rcx, [rbp+57h+hMem]
0x18001c283  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c288  nop
0x18001c289  jmp     loc_18001C3C3
0x18001c28e  mov     rdx, [rbp+57h+hMem]; pSid2
0x18001c292  mov     rcx, [rbp+57h+pSid1]; pSid1
0x18001c296  call    cs:__imp_EqualSid
0x18001c29d  nop     dword ptr [rax+rax+00h]
0x18001c2a2  test    eax, eax
0x18001c2a4  jz      short loc_18001C2E8
0x18001c2a6  mov     rcx, [rbp+5Fh]; this
0x18001c2aa  lea     rax, aUserSidMatches; "User SID matches local system, returnin"...
0x18001c2b1  mov     qword ptr [rsp+0A0h+nSubAuthority2], rax; int
0x18001c2b6  mov     ebx, 80070057h
0x18001c2bb  mov     r9d, ebx; char *
0x18001c2be  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c2c5  mov     edx, 9Eh; void *
0x18001c2ca  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001c2cf  lea     rcx, [rbp+57h+pSid1]
0x18001c2d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c2d8  nop
0x18001c2d9  lea     rcx, [rbp+57h+hMem]
0x18001c2dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c2e2  nop
0x18001c2e3  jmp     loc_18001C3C3
0x18001c2e8  mov     [rbp+57h+var_30], r14
0x18001c2ec  mov     [rbp+57h+var_28], r14b
0x18001c2f0  mov     ebx, 80004005h
0x18001c2f5  test    rdi, rdi
0x18001c2f8  jz      loc_18001C38E
0x18001c2fe  lea     rcx, [rbp+57h+var_30]; this
0x18001c302  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001c307  lea     rdx, [rbp+57h+var_30]; void **
0x18001c30b  mov     rcx, rdi; hToken
0x18001c30e  call    ?ImpersonateUser@@YAJPEAXPEAPEAX@Z; ImpersonateUser(void *,void * *)
0x18001c313  mov     ebx, eax
0x18001c315  test    eax, eax
0x18001c317  js      short loc_18001C38A
0x18001c319  mov     [rbp+57h+var_28], 1
0x18001c31d  mov     rdx, rsi; unsigned __int16 **
0x18001c320  mov     ecx, 6; NameFormat
0x18001c325  call    ?GetUserNameAlloc@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG@Z; GetUserNameAlloc(EXTENDED_NAME_FORMAT,ushort * *)
0x18001c32a  lea     ecx, [rax+7FF8FACCh]
0x18001c330  cmp     ecx, 17h
0x18001c333  ja      short loc_18001C33F
0x18001c335  mov     edx, 880001h
0x18001c33a  bt      edx, ecx
0x18001c33d  jb      short loc_18001C369
0x18001c33f  cmp     eax, 80070032h
0x18001c344  jz      short loc_18001C369
0x18001c346  cmp     eax, 800704BCh
0x18001c34b  jz      short loc_18001C369
0x18001c34d  mov     rcx, [rbp+5Fh]; this
0x18001c351  test    eax, eax
0x18001c353  jns     short loc_18001C369
0x18001c355  mov     r9d, eax; char *
0x18001c358  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c35f  mov     edx, 0AFh; void *
0x18001c364  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c369  lea     rcx, [rbp+57h+var_30]; this
0x18001c36d  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001c372  lea     rcx, [rbp+57h+pSid1]
0x18001c376  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c37b  nop
0x18001c37c  lea     rcx, [rbp+57h+hMem]
0x18001c380  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c385  nop
0x18001c386  xor     eax, eax
0x18001c388  jmp     short loc_18001C3C5
0x18001c38a  mov     [rbp+57h+var_28], r14b
0x18001c38e  mov     rcx, [rbp+5Fh]; this
0x18001c392  mov     r9d, ebx; char *
0x18001c395  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c39c  mov     edx, 0A5h; void *
0x18001c3a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c3a6  lea     rcx, [rbp+57h+var_30]; this
0x18001c3aa  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001c3af  lea     rcx, [rbp+57h+pSid1]
0x18001c3b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c3b8  nop
0x18001c3b9  lea     rcx, [rbp+57h+hMem]
0x18001c3bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c3c2  nop
0x18001c3c3  mov     eax, ebx
0x18001c3c5  mov     rcx, [rbp+57h+var_18]
0x18001c3c9  xor     rcx, rsp; StackCookie
0x18001c3cc  call    __security_check_cookie
0x18001c3d1  lea     r11, [rsp+0A0h+var_10]
0x18001c3d9  mov     rbx, [r11+30h]
0x18001c3dd  mov     rsi, [r11+38h]
0x18001c3e1  mov     rsp, r11
0x18001c3e4  pop     r14
0x18001c3e6  pop     rdi
0x18001c3e7  pop     rbp
0x18001c3e8  retn
```
