# cxl::CaseInsensitive_LessThan::operator()(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180012a54`
- end: `0x180012b16`
- name: `??RCaseInsensitive_LessThan@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `194`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001bef8`
- `0x18001c05c`
- `0x18001c138`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x18000d618`
- `0x180012a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ac1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012aa3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012aa3`

## string_xrefs

- `0x180012aad`: `CompareStringW`

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
0x180012a54  push    rbx
0x180012a56  sub     rsp, 0E0h
0x180012a5d  mov     rax, cs:__security_cookie
0x180012a64  xor     rax, rsp
0x180012a67  mov     [rsp+0E8h+var_18], rax
0x180012a6f  mov     r9, rdx
0x180012a72  mov     rcx, r8
0x180012a75  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180012a7a  mov     rdx, rax
0x180012a7d  mov     rcx, r9
0x180012a80  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180012a85  mov     ecx, [r8+10h]
0x180012a89  mov     [rsp+0E8h+cchCount2], ecx; cchCount2
0x180012a8d  mov     [rsp+0E8h+lpString2], rdx; lpString2
0x180012a92  mov     r9d, [r9+10h]; cchCount1
0x180012a96  mov     r8, rax; lpString1
0x180012a99  mov     edx, 1; dwCmpFlags
0x180012a9e  mov     ecx, 400h; Locale
0x180012aa3  call    cs:__imp_CompareStringW
0x180012aa9  test    eax, eax
0x180012aab  jnz     short loc_180012AF7
0x180012aad  lea     rdx, aComparestringw; "CompareStringW"
0x180012ab4  lea     rcx, [rsp+0E8h+var_B0]
0x180012ab9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180012abe  mov     rbx, rax
0x180012ac1  call    cs:__imp_GetLastError
0x180012ac7  mov     [rsp+0E8h+var_B8], eax
0x180012acb  mov     [rsp+0E8h+var_B4], 0
0x180012ad3  mov     r8, rbx
0x180012ad6  lea     rdx, [rsp+0E8h+var_B8]
0x180012adb  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180012ae0  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180012ae5  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180012aec  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180012af1  call    _CxxThrowException_0
0x180012af7  cmp     eax, 1
0x180012afa  setz    al
0x180012afd  mov     rcx, [rsp+0E8h+var_18]
0x180012b05  xor     rcx, rsp; StackCookie
0x180012b08  call    __security_check_cookie
0x180012b0d  add     rsp, 0E0h
0x180012b14  pop     rbx
0x180012b15  retn
```
