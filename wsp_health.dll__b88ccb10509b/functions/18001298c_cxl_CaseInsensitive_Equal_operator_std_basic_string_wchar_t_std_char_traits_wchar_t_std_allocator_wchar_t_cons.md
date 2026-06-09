# cxl::CaseInsensitive_Equal::operator()(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18001298c`
- end: `0x180012a4e`
- name: `??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `194`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005f0cc`
- `0x18006bcd0`
- `0x18006e180`
- `0x1800763fc`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x18000d618`
- `0x18001298c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800129db`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800129db`

## string_xrefs

- `0x1800129e5`: `CompareStringW`

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
0x18001298c  push    rbx
0x18001298e  sub     rsp, 0E0h
0x180012995  mov     rax, cs:__security_cookie
0x18001299c  xor     rax, rsp
0x18001299f  mov     [rsp+0E8h+var_18], rax
0x1800129a7  mov     r9, rdx
0x1800129aa  mov     rcx, r8
0x1800129ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800129b2  mov     rdx, rax
0x1800129b5  mov     rcx, r9
0x1800129b8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800129bd  mov     ecx, [r8+10h]
0x1800129c1  mov     [rsp+0E8h+cchCount2], ecx; cchCount2
0x1800129c5  mov     [rsp+0E8h+lpString2], rdx; lpString2
0x1800129ca  mov     r9d, [r9+10h]; cchCount1
0x1800129ce  mov     r8, rax; lpString1
0x1800129d1  mov     edx, 1; dwCmpFlags
0x1800129d6  mov     ecx, 400h; Locale
0x1800129db  call    cs:__imp_CompareStringW
0x1800129e1  test    eax, eax
0x1800129e3  jnz     short loc_180012A2F
0x1800129e5  lea     rdx, aComparestringw; "CompareStringW"
0x1800129ec  lea     rcx, [rsp+0E8h+var_B0]
0x1800129f1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800129f6  mov     rbx, rax
0x1800129f9  call    cs:__imp_GetLastError
0x1800129ff  mov     [rsp+0E8h+var_B8], eax
0x180012a03  mov     [rsp+0E8h+var_B4], 0
0x180012a0b  mov     r8, rbx
0x180012a0e  lea     rdx, [rsp+0E8h+var_B8]
0x180012a13  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180012a18  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180012a1d  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180012a24  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180012a29  call    _CxxThrowException_0
0x180012a2f  cmp     eax, 2
0x180012a32  setz    al
0x180012a35  mov     rcx, [rsp+0E8h+var_18]
0x180012a3d  xor     rcx, rsp; StackCookie
0x180012a40  call    __security_check_cookie
0x180012a45  add     rsp, 0E0h
0x180012a4c  pop     rbx
0x180012a4d  retn
```
