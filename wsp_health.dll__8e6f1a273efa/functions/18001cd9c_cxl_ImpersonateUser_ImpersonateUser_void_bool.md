# cxl::ImpersonateUser::ImpersonateUser(void *,bool)

- ea: `0x18001cd9c`
- end: `0x18001ce47`
- name: `??0ImpersonateUser@cxl@@QEAA@PEAX_N@Z`
- size: `171`
- prototype: `_QWORD(cxl::ImpersonateUser *__hidden this, void *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c578`
- `0x18007d22c`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x18001cd9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdee`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001cdca`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001cdca`

## string_xrefs

- `0x18001cdda`: `::ImpersonateLoggedOnUser( token )`

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
0x18001cd9c  push    rbx
0x18001cd9e  sub     rsp, 0D0h
0x18001cda5  mov     rax, cs:__security_cookie
0x18001cdac  xor     rax, rsp
0x18001cdaf  mov     [rsp+0D8h+var_18], rax
0x18001cdb7  mov     rbx, rcx
0x18001cdba  mov     [rsp+0D8h+var_B0], rcx
0x18001cdbf  mov     qword ptr [rcx+8], 0
0x18001cdc7  mov     rcx, rdx; hToken
0x18001cdca  call    cs:__imp_ImpersonateLoggedOnUser
0x18001cdd1  nop     dword ptr [rax+rax+00h]
0x18001cdd6  test    eax, eax
0x18001cdd8  jnz     short loc_18001CE2A
0x18001cdda  lea     rdx, aImpersonatelog; "::ImpersonateLoggedOnUser( token )"
0x18001cde1  lea     rcx, [rsp+0D8h+var_A8]
0x18001cde6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001cdeb  mov     rbx, rax
0x18001cdee  call    cs:__imp_GetLastError
0x18001cdf5  nop     dword ptr [rax+rax+00h]
0x18001cdfa  mov     [rsp+0D8h+var_B8], eax
0x18001cdfe  mov     [rsp+0D8h+var_B4], 0
0x18001ce06  mov     r8, rbx
0x18001ce09  lea     rdx, [rsp+0D8h+var_B8]
0x18001ce0e  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18001ce13  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001ce18  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001ce1f  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001ce24  call    _CxxThrowException_0
0x18001ce2a  mov     rax, rbx
0x18001ce2d  mov     rcx, [rsp+0D8h+var_18]
0x18001ce35  xor     rcx, rsp; StackCookie
0x18001ce38  call    __security_check_cookie
0x18001ce3d  add     rsp, 0D0h
0x18001ce44  pop     rbx
0x18001ce45  retn
```
