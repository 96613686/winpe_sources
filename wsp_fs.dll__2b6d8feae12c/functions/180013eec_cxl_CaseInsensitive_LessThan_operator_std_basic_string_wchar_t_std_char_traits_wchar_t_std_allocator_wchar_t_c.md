# cxl::CaseInsensitive_LessThan::operator()(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180013eec`
- end: `0x180013fae`
- name: `??RCaseInsensitive_LessThan@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `194`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001f0c8`
- `0x18001f22c`
- `0x18001f308`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d33c`
- `0x18000dd74`
- `0x180013eec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f59`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013f3b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013f3b`

## string_xrefs

- `0x180013f45`: `CompareStringW`

## pseudocode

```c
bool __fastcall cxl::CaseInsensitive_LessThan::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  const WCHAR *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  PCNZWCH lpString2; // rdx
  int v8; // eax
  __int64 v9; // rbx
  _DWORD v11[2]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v12[40]; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+60h] [rbp-88h] BYREF

  std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v3);
  v8 = CompareStringW(0x400u, 1u, v4, *(_DWORD *)(v6 + 16), lpString2, *(_DWORD *)(v5 + 16));
  if ( !v8 )
  {
    v9 = std::wstring::wstring(v12, L"CompareStringW");
    v11[0] = GetLastError();
    v11[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v11, v9);
    throw (cxl::Exception *)pExceptionObject;
  }
  return v8 == 1;
}

```

## disassembly

```asm
0x180013eec  push    rbx
0x180013eee  sub     rsp, 0E0h
0x180013ef5  mov     rax, cs:__security_cookie
0x180013efc  xor     rax, rsp
0x180013eff  mov     [rsp+0E8h+var_18], rax
0x180013f07  mov     r9, rdx
0x180013f0a  mov     rcx, r8
0x180013f0d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013f12  mov     rdx, rax
0x180013f15  mov     rcx, r9
0x180013f18  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013f1d  mov     ecx, [r8+10h]
0x180013f21  mov     [rsp+0E8h+cchCount2], ecx; cchCount2
0x180013f25  mov     [rsp+0E8h+lpString2], rdx; lpString2
0x180013f2a  mov     r9d, [r9+10h]; cchCount1
0x180013f2e  mov     r8, rax; lpString1
0x180013f31  mov     edx, 1; dwCmpFlags
0x180013f36  mov     ecx, 400h; Locale
0x180013f3b  call    cs:__imp_CompareStringW
0x180013f41  test    eax, eax
0x180013f43  jnz     short loc_180013F8F
0x180013f45  lea     rdx, aComparestringw; "CompareStringW"
0x180013f4c  lea     rcx, [rsp+0E8h+var_B0]
0x180013f51  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180013f56  mov     rbx, rax
0x180013f59  call    cs:__imp_GetLastError
0x180013f5f  mov     [rsp+0E8h+var_B8], eax
0x180013f63  mov     [rsp+0E8h+var_B4], 0
0x180013f6b  mov     r8, rbx
0x180013f6e  lea     rdx, [rsp+0E8h+var_B8]
0x180013f73  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180013f78  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180013f7d  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180013f84  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180013f89  call    _CxxThrowException_0
0x180013f8f  cmp     eax, 1
0x180013f92  setz    al
0x180013f95  mov     rcx, [rsp+0E8h+var_18]
0x180013f9d  xor     rcx, rsp; StackCookie
0x180013fa0  call    __security_check_cookie
0x180013fa5  add     rsp, 0E0h
0x180013fac  pop     rbx
0x180013fad  retn
```
