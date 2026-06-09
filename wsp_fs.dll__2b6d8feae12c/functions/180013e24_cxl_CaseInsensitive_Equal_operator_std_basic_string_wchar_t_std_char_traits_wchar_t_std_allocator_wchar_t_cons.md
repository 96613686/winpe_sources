# cxl::CaseInsensitive_Equal::operator()(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180013e24`
- end: `0x180013ee6`
- name: `??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004c374`
- `0x18004c940`
- `0x18004d6a0`
- `0x180052148`
- `0x1800584b0`
- `0x1800585e8`
- `0x18005de0c`
- `0x18005e780`
- `0x180064b28`
- `0x180065030`
- `0x1800999b8`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d33c`
- `0x18000dd74`
- `0x180013e24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e91`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013e73`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013e73`

## string_xrefs

- `0x180013e7d`: `CompareStringW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall cxl::CaseInsensitive_Equal::operator()(__int64 a1, __int64 a2, __int64 a3)
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
  return v8 == 2;
}

```

## disassembly

```asm
0x180013e24  push    rbx
0x180013e26  sub     rsp, 0E0h
0x180013e2d  mov     rax, cs:__security_cookie
0x180013e34  xor     rax, rsp
0x180013e37  mov     [rsp+0E8h+var_18], rax
0x180013e3f  mov     r9, rdx
0x180013e42  mov     rcx, r8
0x180013e45  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013e4a  mov     rdx, rax
0x180013e4d  mov     rcx, r9
0x180013e50  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013e55  mov     ecx, [r8+10h]
0x180013e59  mov     [rsp+0E8h+cchCount2], ecx; cchCount2
0x180013e5d  mov     [rsp+0E8h+lpString2], rdx; lpString2
0x180013e62  mov     r9d, [r9+10h]; cchCount1
0x180013e66  mov     r8, rax; lpString1
0x180013e69  mov     edx, 1; dwCmpFlags
0x180013e6e  mov     ecx, 400h; Locale
0x180013e73  call    cs:__imp_CompareStringW
0x180013e79  test    eax, eax
0x180013e7b  jnz     short loc_180013EC7
0x180013e7d  lea     rdx, aComparestringw; "CompareStringW"
0x180013e84  lea     rcx, [rsp+0E8h+var_B0]
0x180013e89  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180013e8e  mov     rbx, rax
0x180013e91  call    cs:__imp_GetLastError
0x180013e97  mov     [rsp+0E8h+var_B8], eax
0x180013e9b  mov     [rsp+0E8h+var_B4], 0
0x180013ea3  mov     r8, rbx
0x180013ea6  lea     rdx, [rsp+0E8h+var_B8]
0x180013eab  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180013eb0  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180013eb5  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180013ebc  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180013ec1  call    _CxxThrowException_0
0x180013ec7  cmp     eax, 2
0x180013eca  setz    al
0x180013ecd  mov     rcx, [rsp+0E8h+var_18]
0x180013ed5  xor     rcx, rsp; StackCookie
0x180013ed8  call    __security_check_cookie
0x180013edd  add     rsp, 0E0h
0x180013ee4  pop     rbx
0x180013ee5  retn
```
