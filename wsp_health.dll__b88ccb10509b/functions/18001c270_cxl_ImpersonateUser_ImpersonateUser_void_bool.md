# cxl::ImpersonateUser::ImpersonateUser(void *,bool)

- ea: `0x18001c270`
- end: `0x18001c30e`
- name: `??0ImpersonateUser@cxl@@QEAA@PEAX_N@Z`
- size: `158`
- prototype: `_QWORD(cxl::ImpersonateUser *__hidden this, void *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ba54`
- `0x18007b094`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x18001c270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2bc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001c29e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001c29e`

## string_xrefs

- `0x18001c2a8`: `::ImpersonateLoggedOnUser( token )`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
cxl::ImpersonateUser *__fastcall cxl::ImpersonateUser::ImpersonateUser(cxl::ImpersonateUser *this, void *a2)
{
  __int64 v3; // rbx
  _DWORD v5[2]; // [rsp+20h] [rbp-B8h] BYREF
  cxl::ImpersonateUser *v6; // [rsp+28h] [rbp-B0h]
  _BYTE v7[32]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-88h] BYREF

  v6 = this;
  *((_QWORD *)this + 1) = 0;
  if ( !ImpersonateLoggedOnUser(a2) )
  {
    v3 = std::wstring::wstring(v7, L"::ImpersonateLoggedOnUser( token )");
    v5[0] = GetLastError();
    v5[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v5, v3);
    throw (cxl::Exception *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18001c270  push    rbx
0x18001c272  sub     rsp, 0D0h
0x18001c279  mov     rax, cs:__security_cookie
0x18001c280  xor     rax, rsp
0x18001c283  mov     [rsp+0D8h+var_18], rax
0x18001c28b  mov     rbx, rcx
0x18001c28e  mov     [rsp+0D8h+var_B0], rcx
0x18001c293  mov     qword ptr [rcx+8], 0
0x18001c29b  mov     rcx, rdx; hToken
0x18001c29e  call    cs:__imp_ImpersonateLoggedOnUser
0x18001c2a4  test    eax, eax
0x18001c2a6  jnz     short loc_18001C2F2
0x18001c2a8  lea     rdx, aImpersonatelog; "::ImpersonateLoggedOnUser( token )"
0x18001c2af  lea     rcx, [rsp+0D8h+var_A8]
0x18001c2b4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001c2b9  mov     rbx, rax
0x18001c2bc  call    cs:__imp_GetLastError
0x18001c2c2  mov     [rsp+0D8h+var_B8], eax
0x18001c2c6  mov     [rsp+0D8h+var_B4], 0
0x18001c2ce  mov     r8, rbx
0x18001c2d1  lea     rdx, [rsp+0D8h+var_B8]
0x18001c2d6  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001c2db  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001c2e0  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001c2e7  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001c2ec  call    _CxxThrowException_0
0x18001c2f2  mov     rax, rbx
0x18001c2f5  mov     rcx, [rsp+0D8h+var_18]
0x18001c2fd  xor     rcx, rsp; StackCookie
0x18001c300  call    __security_check_cookie
0x18001c305  add     rsp, 0D0h
0x18001c30c  pop     rbx
0x18001c30d  retn
```
