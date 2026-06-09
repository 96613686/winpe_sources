# cxl::CaseInsensitive_Equal::operator()(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800143d8`
- end: `0x1800144a7`
- name: `??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `207`
- prototype: ``
- caller_count: `11`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004d548`
- `0x18004db10`
- `0x18004e7e0`
- `0x180053138`
- `0x1800595a0`
- `0x1800596d8`
- `0x18005efa0`
- `0x18005f940`
- `0x180065de8`
- `0x180066300`
- `0x18009be38`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d6a4`
- `0x18000e14c`
- `0x1800143d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001444b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001444b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014427`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014427`

## string_xrefs

- `0x180014437`: `CompareStringW`

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
0x1800143d8  push    rbx
0x1800143da  sub     rsp, 0E0h
0x1800143e1  mov     rax, cs:__security_cookie
0x1800143e8  xor     rax, rsp
0x1800143eb  mov     [rsp+0E8h+var_18], rax
0x1800143f3  mov     r9, rdx
0x1800143f6  mov     rcx, r8
0x1800143f9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800143fe  mov     rdx, rax
0x180014401  mov     rcx, r9
0x180014404  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180014409  mov     ecx, [r8+10h]
0x18001440d  mov     [rsp+0E8h+cchCount2], ecx; cchCount2
0x180014411  mov     [rsp+0E8h+lpString2], rdx; lpString2
0x180014416  mov     r9d, [r9+10h]; cchCount1
0x18001441a  mov     r8, rax; lpString1
0x18001441d  mov     edx, 1; dwCmpFlags
0x180014422  mov     ecx, 400h; Locale
0x180014427  call    cs:__imp_CompareStringW
0x18001442e  nop     dword ptr [rax+rax+00h]
0x180014433  test    eax, eax
0x180014435  jnz     short loc_180014487
0x180014437  lea     rdx, aComparestringw; "CompareStringW"
0x18001443e  lea     rcx, [rsp+0E8h+var_B0]
0x180014443  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180014448  mov     rbx, rax
0x18001444b  call    cs:__imp_GetLastError
0x180014452  nop     dword ptr [rax+rax+00h]
0x180014457  mov     [rsp+0E8h+var_B8], eax
0x18001445b  mov     [rsp+0E8h+var_B4], 0
0x180014463  mov     r8, rbx
0x180014466  lea     rdx, [rsp+0E8h+var_B8]
0x18001446b  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180014470  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180014475  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001447c  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180014481  call    _CxxThrowException_0
0x180014487  cmp     eax, 2
0x18001448a  setz    al
0x18001448d  mov     rcx, [rsp+0E8h+var_18]
0x180014495  xor     rcx, rsp; StackCookie
0x180014498  call    __security_check_cookie
0x18001449d  add     rsp, 0E0h
0x1800144a4  pop     rbx
0x1800144a5  retn
```
