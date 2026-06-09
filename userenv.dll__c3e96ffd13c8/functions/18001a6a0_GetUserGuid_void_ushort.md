# GetUserGuid(void *,ushort * *)

- ea: `0x18001a6a0`
- end: `0x18001a90b`
- name: `?GetUserGuid@@YAJPEAXPEAPEAG@Z`
- size: `619`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a540`

## callees

- `0x1800056a0`
- `0x1800064a8`
- `0x18000cd2c`
- `0x18000cea0`
- `0x18000cfc4`
- `0x18000d9b0`
- `0x1800104fc`
- `0x1800106b8`
- `0x180018b04`
- `0x18001992c`
- `0x18001a524`
- `0x18001a6a0`
- `0x18001a914`
- `0x18001aa28`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a7be`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a7be`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001a73f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001a73f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a6f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a6f7`

## string_xrefs

- `0x18001a74d`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001a78c`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001a7e0`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001a87a`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001a8b7`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001a7cc`: `User SID matches local system, returning Invalid Arg.`

## pseudocode

```c
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
        (int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        (const char *)(unsigned int)UserNameAlloc);
  }
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&v14);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
  return 0;
}

```

## disassembly

```asm
0x18001a6a0  mov     [rsp-8+arg_10], rbx
0x18001a6a5  mov     [rsp-8+arg_18], rsi
0x18001a6aa  push    rbp
0x18001a6ab  push    rdi
0x18001a6ac  push    r14
0x18001a6ae  lea     rbp, [rsp-47h]
0x18001a6b3  sub     rsp, 90h
0x18001a6ba  mov     rax, cs:__security_cookie
0x18001a6c1  xor     rax, rsp
0x18001a6c4  mov     [rbp+57h+var_18], rax
0x18001a6c8  mov     rsi, rdx
0x18001a6cb  mov     rdi, rcx
0x18001a6ce  xor     r14d, r14d
0x18001a6d1  mov     [rdx], r14
0x18001a6d4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18001a6d8  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001a6de  mov     [rbp+57h+hMem], r14
0x18001a6e2  mov     rbx, [rbp+57h+hMem]
0x18001a6e6  test    rbx, rbx
0x18001a6e9  jz      short loc_18001A707
0x18001a6eb  lea     rcx, [rbp+57h+pSid1]; this
0x18001a6ef  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a6f4  mov     rcx, rbx; hMem
0x18001a6f7  call    cs:__imp_LocalFree
0x18001a6fd  lea     rcx, [rbp+57h+pSid1]; this
0x18001a701  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a706  nop
0x18001a707  mov     [rbp+57h+hMem], r14
0x18001a70b  lea     rax, [rbp+57h+hMem]
0x18001a70f  mov     [rsp+0A0h+pSid], rax; pSid
0x18001a714  mov     [rsp+0A0h+nSubAuthority7], r14d; nSubAuthority7
0x18001a719  mov     [rsp+0A0h+nSubAuthority6], r14d; nSubAuthority6
0x18001a71e  mov     [rsp+0A0h+nSubAuthority5], r14d; nSubAuthority5
0x18001a723  mov     [rsp+0A0h+nSubAuthority4], r14d; nSubAuthority4
0x18001a728  mov     dword ptr [rsp+0A0h+nSubAuthority3], r14d; char *
0x18001a72d  mov     [rsp+0A0h+nSubAuthority2], r14d; int
0x18001a732  xor     r9d, r9d; nSubAuthority1
0x18001a735  lea     r8d, [r9+12h]; nSubAuthority0
0x18001a739  mov     dl, 1; nSubAuthorityCount
0x18001a73b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001a73f  call    cs:__imp_AllocateAndInitializeSid
0x18001a745  test    eax, eax
0x18001a747  jnz     short loc_18001A76F
0x18001a749  mov     rcx, [rbp+5Fh]; this
0x18001a74d  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a754  mov     edx, 99h; void *
0x18001a759  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a75e  mov     ebx, eax
0x18001a760  lea     rcx, [rbp+57h+hMem]
0x18001a764  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a769  nop
0x18001a76a  jmp     loc_18001A8E5
0x18001a76f  mov     [rbp+57h+pSid1], r14
0x18001a773  lea     rdx, [rbp+57h+pSid1]; void **
0x18001a777  mov     rcx, rdi; TokenHandle
0x18001a77a  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x18001a77f  mov     ebx, eax
0x18001a781  test    eax, eax
0x18001a783  jns     short loc_18001A7B6
0x18001a785  mov     rcx, [rbp+5Fh]; this
0x18001a789  mov     r9d, eax; char *
0x18001a78c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a793  mov     edx, 9Ch; void *
0x18001a798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a79d  lea     rcx, [rbp+57h+pSid1]
0x18001a7a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a7a6  nop
0x18001a7a7  lea     rcx, [rbp+57h+hMem]
0x18001a7ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a7b0  nop
0x18001a7b1  jmp     loc_18001A8E5
0x18001a7b6  mov     rdx, [rbp+57h+hMem]; pSid2
0x18001a7ba  mov     rcx, [rbp+57h+pSid1]; pSid1
0x18001a7be  call    cs:__imp_EqualSid
0x18001a7c4  test    eax, eax
0x18001a7c6  jz      short loc_18001A80A
0x18001a7c8  mov     rcx, [rbp+5Fh]; this
0x18001a7cc  lea     rax, aUserSidMatches; "User SID matches local system, returnin"...
0x18001a7d3  mov     qword ptr [rsp+0A0h+nSubAuthority2], rax; int
0x18001a7d8  mov     ebx, 80070057h
0x18001a7dd  mov     r9d, ebx; char *
0x18001a7e0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a7e7  mov     edx, 9Eh; void *
0x18001a7ec  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a7f1  lea     rcx, [rbp+57h+pSid1]
0x18001a7f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a7fa  nop
0x18001a7fb  lea     rcx, [rbp+57h+hMem]
0x18001a7ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a804  nop
0x18001a805  jmp     loc_18001A8E5
0x18001a80a  mov     [rbp+57h+var_30], r14
0x18001a80e  mov     [rbp+57h+var_28], r14b
0x18001a812  mov     ebx, 80004005h
0x18001a817  test    rdi, rdi
0x18001a81a  jz      loc_18001A8B0
0x18001a820  lea     rcx, [rbp+57h+var_30]; this
0x18001a824  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001a829  lea     rdx, [rbp+57h+var_30]; void **
0x18001a82d  mov     rcx, rdi; hToken
0x18001a830  call    ?ImpersonateUser@@YAJPEAXPEAPEAX@Z; ImpersonateUser(void *,void * *)
0x18001a835  mov     ebx, eax
0x18001a837  test    eax, eax
0x18001a839  js      short loc_18001A8AC
0x18001a83b  mov     [rbp+57h+var_28], 1
0x18001a83f  mov     rdx, rsi; unsigned __int16 **
0x18001a842  mov     ecx, 6; NameFormat
0x18001a847  call    ?GetUserNameAlloc@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG@Z; GetUserNameAlloc(EXTENDED_NAME_FORMAT,ushort * *)
0x18001a84c  lea     ecx, [rax+7FF8FACCh]
0x18001a852  cmp     ecx, 17h
0x18001a855  ja      short loc_18001A861
0x18001a857  mov     edx, 880001h
0x18001a85c  bt      edx, ecx
0x18001a85f  jb      short loc_18001A88B
0x18001a861  cmp     eax, 80070032h
0x18001a866  jz      short loc_18001A88B
0x18001a868  cmp     eax, 800704BCh
0x18001a86d  jz      short loc_18001A88B
0x18001a86f  mov     rcx, [rbp+5Fh]; this
0x18001a873  test    eax, eax
0x18001a875  jns     short loc_18001A88B
0x18001a877  mov     r9d, eax; char *
0x18001a87a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a881  mov     edx, 0AFh; void *
0x18001a886  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a88b  lea     rcx, [rbp+57h+var_30]; this
0x18001a88f  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001a894  lea     rcx, [rbp+57h+pSid1]
0x18001a898  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a89d  nop
0x18001a89e  lea     rcx, [rbp+57h+hMem]
0x18001a8a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a8a7  nop
0x18001a8a8  xor     eax, eax
0x18001a8aa  jmp     short loc_18001A8E7
0x18001a8ac  mov     [rbp+57h+var_28], r14b
0x18001a8b0  mov     rcx, [rbp+5Fh]; this
0x18001a8b4  mov     r9d, ebx; char *
0x18001a8b7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a8be  mov     edx, 0A5h; void *
0x18001a8c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a8c8  lea     rcx, [rbp+57h+var_30]; this
0x18001a8cc  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001a8d1  lea     rcx, [rbp+57h+pSid1]
0x18001a8d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a8da  nop
0x18001a8db  lea     rcx, [rbp+57h+hMem]
0x18001a8df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a8e4  nop
0x18001a8e5  mov     eax, ebx
0x18001a8e7  mov     rcx, [rbp+57h+var_18]
0x18001a8eb  xor     rcx, rsp; StackCookie
0x18001a8ee  call    __security_check_cookie
0x18001a8f3  lea     r11, [rsp+0A0h+var_10]
0x18001a8fb  mov     rbx, [r11+30h]
0x18001a8ff  mov     rsi, [r11+38h]
0x18001a903  mov     rsp, r11
0x18001a906  pop     r14
0x18001a908  pop     rdi
0x18001a909  pop     rbp
0x18001a90a  retn
```
