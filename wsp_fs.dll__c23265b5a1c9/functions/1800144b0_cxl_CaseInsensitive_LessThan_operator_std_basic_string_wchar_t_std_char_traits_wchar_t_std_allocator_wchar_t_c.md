# cxl::CaseInsensitive_LessThan::operator()(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800144b0`
- end: `0x18001457f`
- name: `??RCaseInsensitive_LessThan@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `207`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001fcf0`
- `0x18001fe54`
- `0x18001ff30`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d6a4`
- `0x18000e14c`
- `0x1800144b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014523`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800144ff`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800144ff`

## string_xrefs

- `0x18001450f`: `CompareStringW`

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
0x1800144b0  push    rbx
0x1800144b2  sub     rsp, 0E0h
0x1800144b9  mov     rax, cs:__security_cookie
0x1800144c0  xor     rax, rsp
0x1800144c3  mov     [rsp+0E8h+var_18], rax
0x1800144cb  mov     r9, rdx
0x1800144ce  mov     rcx, r8
0x1800144d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800144d6  mov     rdx, rax
0x1800144d9  mov     rcx, r9
0x1800144dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800144e1  mov     ecx, [r8+10h]
0x1800144e5  mov     [rsp+0E8h+cchCount2], ecx; cchCount2
0x1800144e9  mov     [rsp+0E8h+lpString2], rdx; lpString2
0x1800144ee  mov     r9d, [r9+10h]; cchCount1
0x1800144f2  mov     r8, rax; lpString1
0x1800144f5  mov     edx, 1; dwCmpFlags
0x1800144fa  mov     ecx, 400h; Locale
0x1800144ff  call    cs:__imp_CompareStringW
0x180014506  nop     dword ptr [rax+rax+00h]
0x18001450b  test    eax, eax
0x18001450d  jnz     short loc_18001455F
0x18001450f  lea     rdx, aComparestringw; "CompareStringW"
0x180014516  lea     rcx, [rsp+0E8h+var_B0]
0x18001451b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180014520  mov     rbx, rax
0x180014523  call    cs:__imp_GetLastError
0x18001452a  nop     dword ptr [rax+rax+00h]
0x18001452f  mov     [rsp+0E8h+var_B8], eax
0x180014533  mov     [rsp+0E8h+var_B4], 0
0x18001453b  mov     r8, rbx
0x18001453e  lea     rdx, [rsp+0E8h+var_B8]
0x180014543  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180014548  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001454d  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180014554  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180014559  call    _CxxThrowException_0
0x18001455f  cmp     eax, 1
0x180014562  setz    al
0x180014565  mov     rcx, [rsp+0E8h+var_18]
0x18001456d  xor     rcx, rsp; StackCookie
0x180014570  call    __security_check_cookie
0x180014575  add     rsp, 0E0h
0x18001457c  pop     rbx
0x18001457d  retn
```
