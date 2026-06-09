# cxl::CaseInsensitive_LessThan::operator()(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180013084`
- end: `0x180013153`
- name: `??RCaseInsensitive_LessThan@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `207`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ca20`
- `0x18001cb84`
- `0x18001cc60`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x18000da34`
- `0x180013084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130f7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800130d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800130d3`

## string_xrefs

- `0x1800130e3`: `CompareStringW`

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
0x180013084  push    rbx
0x180013086  sub     rsp, 0E0h
0x18001308d  mov     rax, cs:__security_cookie
0x180013094  xor     rax, rsp
0x180013097  mov     [rsp+0E8h+var_18], rax
0x18001309f  mov     r9, rdx
0x1800130a2  mov     rcx, r8
0x1800130a5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800130aa  mov     rdx, rax
0x1800130ad  mov     rcx, r9
0x1800130b0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800130b5  mov     ecx, [r8+10h]
0x1800130b9  mov     [rsp+0E8h+cchCount2], ecx; cchCount2
0x1800130bd  mov     [rsp+0E8h+lpString2], rdx; lpString2
0x1800130c2  mov     r9d, [r9+10h]; cchCount1
0x1800130c6  mov     r8, rax; lpString1
0x1800130c9  mov     edx, 1; dwCmpFlags
0x1800130ce  mov     ecx, 400h; Locale
0x1800130d3  call    cs:__imp_CompareStringW
0x1800130da  nop     dword ptr [rax+rax+00h]
0x1800130df  test    eax, eax
0x1800130e1  jnz     short loc_180013133
0x1800130e3  lea     rdx, aComparestringw; "CompareStringW"
0x1800130ea  lea     rcx, [rsp+0E8h+var_B0]
0x1800130ef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800130f4  mov     rbx, rax
0x1800130f7  call    cs:__imp_GetLastError
0x1800130fe  nop     dword ptr [rax+rax+00h]
0x180013103  mov     [rsp+0E8h+var_B8], eax
0x180013107  mov     [rsp+0E8h+var_B4], 0
0x18001310f  mov     r8, rbx
0x180013112  lea     rdx, [rsp+0E8h+var_B8]
0x180013117  lea     rcx, [rsp+0E8h+pExceptionObject]
0x18001311c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180013121  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180013128  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18001312d  call    _CxxThrowException_0
0x180013133  cmp     eax, 1
0x180013136  setz    al
0x180013139  mov     rcx, [rsp+0E8h+var_18]
0x180013141  xor     rcx, rsp; StackCookie
0x180013144  call    __security_check_cookie
0x180013149  add     rsp, 0E0h
0x180013150  pop     rbx
0x180013151  retn
```
