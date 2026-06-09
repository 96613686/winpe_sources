# cxl::ImpersonateUser::ImpersonateUser(void *,bool)

- ea: `0x18001f440`
- end: `0x18001f54f`
- name: `??0ImpersonateUser@cxl@@QEAA@PEAX_N@Z`
- size: `271`
- prototype: `__int64 __fastcall(cxl::ImpersonateUser *__hidden this, HANDLE hToken, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ec28`
- `0x18005ba54`
- `0x18005f610`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d33c`
- `0x180015b9c`
- `0x18001f440`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f479`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f479`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001f4df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001f4df`

## string_xrefs

- `0x18001f4a0`: `userToken_.TryOpenThreadToken( TOKEN_QUERY | TOKEN_IMPERSONATE, TRUE )`
- `0x18001f4e9`: `::ImpersonateLoggedOnUser( token )`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
cxl::ImpersonateUser *__fastcall cxl::ImpersonateUser::ImpersonateUser(
        cxl::ImpersonateUser *this,
        HANDLE hToken,
        char a3)
{
  HANDLE CurrentThread; // rax
  unsigned int v6; // eax
  DWORD v7; // edi
  __int64 v8; // rax
  __int64 v9; // rbx
  DWORD LastError; // [rsp+20h] [rbp-69h] BYREF
  int v12; // [rsp+24h] [rbp-65h]
  cxl::ImpersonateUser *v13; // [rsp+28h] [rbp-61h]
  _BYTE v14[32]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-39h] BYREF

  v13 = this;
  *((_QWORD *)this + 1) = 0;
  if ( a3 )
  {
    CurrentThread = GetCurrentThread();
    v6 = cxl::Token::TryOpenThreadToken(this, 0xCu, 1, CurrentThread);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 != 1008 )
      {
        v8 = std::wstring::wstring(v14, L"userToken_.TryOpenThreadToken( TOKEN_QUERY | TOKEN_IMPERSONATE, TRUE )");
        LastError = v7;
        v12 = 0;
        cxl::Exception::Exception(pExceptionObject, &LastError, v8);
        throw (cxl::Exception *)pExceptionObject;
      }
    }
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v9 = std::wstring::wstring(v14, L"::ImpersonateLoggedOnUser( token )");
    LastError = GetLastError();
    v12 = 0;
    cxl::Exception::Exception(pExceptionObject, &LastError, v9);
    throw (cxl::Exception *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18001f440  mov     [rsp-8+arg_10], rbx
0x18001f445  push    rbp
0x18001f446  push    rsi
0x18001f447  push    rdi
0x18001f448  lea     rbp, [rsp-47h]
0x18001f44d  sub     rsp, 0D0h
0x18001f454  mov     rax, cs:__security_cookie
0x18001f45b  xor     rax, rsp
0x18001f45e  mov     [rbp+57h+var_20], rax
0x18001f462  mov     rsi, rdx
0x18001f465  mov     rbx, rcx
0x18001f468  mov     [rbp+57h+var_B8], rcx
0x18001f46c  mov     qword ptr [rcx+8], 0
0x18001f474  test    r8b, r8b
0x18001f477  jz      short loc_18001F4DC
0x18001f479  call    cs:__imp_GetCurrentThread
0x18001f47f  mov     r9, rax; void *
0x18001f482  mov     edx, 0Ch; unsigned int
0x18001f487  lea     r8d, [rdx-0Bh]; int
0x18001f48b  mov     rcx, rbx; this
0x18001f48e  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x18001f493  mov     edi, eax
0x18001f495  test    eax, eax
0x18001f497  jz      short loc_18001F4DC
0x18001f499  cmp     eax, 3F0h
0x18001f49e  jz      short loc_18001F4DC
0x18001f4a0  lea     rdx, aUsertokenTryop; "userToken_.TryOpenThreadToken( TOKEN_QU"...
0x18001f4a7  lea     rcx, [rbp+57h+var_B0]
0x18001f4ab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f4b0  nop
0x18001f4b1  mov     [rbp+57h+var_C0], edi
0x18001f4b4  mov     [rbp+57h+var_BC], 0
0x18001f4bb  mov     r8, rax
0x18001f4be  lea     rdx, [rbp+57h+var_C0]
0x18001f4c2  lea     rcx, [rbp+57h+pExceptionObject]
0x18001f4c6  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001f4cb  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001f4d2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001f4d6  call    _CxxThrowException_0
0x18001f4dc  mov     rcx, rsi; hToken
0x18001f4df  call    cs:__imp_ImpersonateLoggedOnUser
0x18001f4e5  test    eax, eax
0x18001f4e7  jnz     short loc_18001F52D
0x18001f4e9  lea     rdx, aImpersonatelog; "::ImpersonateLoggedOnUser( token )"
0x18001f4f0  lea     rcx, [rbp+57h+var_B0]
0x18001f4f4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f4f9  mov     rbx, rax
0x18001f4fc  call    cs:__imp_GetLastError
0x18001f502  mov     [rbp+57h+var_C0], eax
0x18001f505  mov     [rbp+57h+var_BC], 0
0x18001f50c  mov     r8, rbx
0x18001f50f  lea     rdx, [rbp+57h+var_C0]
0x18001f513  lea     rcx, [rbp+57h+pExceptionObject]
0x18001f517  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001f51c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001f523  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001f527  call    _CxxThrowException_0
0x18001f52d  mov     rax, rbx
0x18001f530  mov     rcx, [rbp+57h+var_20]
0x18001f534  xor     rcx, rsp; StackCookie
0x18001f537  call    __security_check_cookie
0x18001f53c  mov     rbx, [rsp+0E0h+arg_10]
0x18001f544  add     rsp, 0D0h
0x18001f54b  pop     rdi
0x18001f54c  pop     rsi
0x18001f54d  pop     rbp
0x18001f54e  retn
```
