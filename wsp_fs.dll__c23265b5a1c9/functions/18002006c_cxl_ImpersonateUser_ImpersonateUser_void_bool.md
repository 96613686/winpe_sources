# cxl::ImpersonateUser::ImpersonateUser(void *,bool)

- ea: `0x18002006c`
- end: `0x18002018e`
- name: `??0ImpersonateUser@cxl@@QEAA@PEAX_N@Z`
- size: `290`
- prototype: `__int64 __fastcall(cxl::ImpersonateUser *__hidden this, HANDLE hToken, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f84c`
- `0x18005cb90`
- `0x180060828`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d6a4`
- `0x180016300`
- `0x18002006c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020134`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800200a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800200a5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020111`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020111`

## string_xrefs

- `0x1800200d2`: `userToken_.TryOpenThreadToken( TOKEN_QUERY | TOKEN_IMPERSONATE, TRUE )`
- `0x180020121`: `::ImpersonateLoggedOnUser( token )`

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
0x18002006c  mov     [rsp-8+arg_10], rbx
0x180020071  push    rbp
0x180020072  push    rsi
0x180020073  push    rdi
0x180020074  lea     rbp, [rsp-47h]
0x180020079  sub     rsp, 0D0h
0x180020080  mov     rax, cs:__security_cookie
0x180020087  xor     rax, rsp
0x18002008a  mov     [rbp+57h+var_20], rax
0x18002008e  mov     rsi, rdx
0x180020091  mov     rbx, rcx
0x180020094  mov     [rbp+57h+var_B8], rcx
0x180020098  mov     qword ptr [rcx+8], 0
0x1800200a0  test    r8b, r8b
0x1800200a3  jz      short loc_18002010E
0x1800200a5  call    cs:__imp_GetCurrentThread
0x1800200ac  nop     dword ptr [rax+rax+00h]
0x1800200b1  mov     r9, rax; void *
0x1800200b4  mov     edx, 0Ch; unsigned int
0x1800200b9  lea     r8d, [rdx-0Bh]; int
0x1800200bd  mov     rcx, rbx; this
0x1800200c0  call    ?TryOpenThreadToken@Token@cxl@@QEAAKKHPEAX@Z; cxl::Token::TryOpenThreadToken(ulong,int,void *)
0x1800200c5  mov     edi, eax
0x1800200c7  test    eax, eax
0x1800200c9  jz      short loc_18002010E
0x1800200cb  cmp     eax, 3F0h
0x1800200d0  jz      short loc_18002010E
0x1800200d2  lea     rdx, aUsertokenTryop; "userToken_.TryOpenThreadToken( TOKEN_QU"...
0x1800200d9  lea     rcx, [rbp+57h+var_B0]
0x1800200dd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800200e2  nop
0x1800200e3  mov     [rbp+57h+var_C0], edi
0x1800200e6  mov     [rbp+57h+var_BC], 0
0x1800200ed  mov     r8, rax
0x1800200f0  lea     rdx, [rbp+57h+var_C0]
0x1800200f4  lea     rcx, [rbp+57h+pExceptionObject]
0x1800200f8  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800200fd  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180020104  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180020108  call    _CxxThrowException_0
0x18002010e  mov     rcx, rsi; hToken
0x180020111  call    cs:__imp_ImpersonateLoggedOnUser
0x180020118  nop     dword ptr [rax+rax+00h]
0x18002011d  test    eax, eax
0x18002011f  jnz     short loc_18002016B
0x180020121  lea     rdx, aImpersonatelog; "::ImpersonateLoggedOnUser( token )"
0x180020128  lea     rcx, [rbp+57h+var_B0]
0x18002012c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180020131  mov     rbx, rax
0x180020134  call    cs:__imp_GetLastError
0x18002013b  nop     dword ptr [rax+rax+00h]
0x180020140  mov     [rbp+57h+var_C0], eax
0x180020143  mov     [rbp+57h+var_BC], 0
0x18002014a  mov     r8, rbx
0x18002014d  lea     rdx, [rbp+57h+var_C0]
0x180020151  lea     rcx, [rbp+57h+pExceptionObject]
0x180020155  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18002015a  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180020161  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180020165  call    _CxxThrowException_0
0x18002016b  mov     rax, rbx
0x18002016e  mov     rcx, [rbp+57h+var_20]
0x180020172  xor     rcx, rsp; StackCookie
0x180020175  call    __security_check_cookie
0x18002017a  mov     rbx, [rsp+0E0h+arg_10]
0x180020182  add     rsp, 0D0h
0x180020189  pop     rdi
0x18002018a  pop     rsi
0x18002018b  pop     rbp
0x18002018c  retn
```
