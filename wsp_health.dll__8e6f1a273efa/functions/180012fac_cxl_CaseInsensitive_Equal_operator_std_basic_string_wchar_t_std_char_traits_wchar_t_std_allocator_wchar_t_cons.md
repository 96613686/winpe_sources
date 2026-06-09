# cxl::CaseInsensitive_Equal::operator()(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180012fac`
- end: `0x18001307b`
- name: `??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `207`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006089c`
- `0x18006d518`
- `0x18006fa00`
- `0x18007825c`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x18000da34`
- `0x180012fac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001301f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001301f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012ffb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012ffb`

## string_xrefs

- `0x18001300b`: `CompareStringW`

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
0x180012fac  push    rbx
0x180012fae  sub     rsp, 0E0h
0x180012fb5  mov     rax, cs:__security_cookie
0x180012fbc  xor     rax, rsp
0x180012fbf  mov     [rsp+0E8h+var_18], rax
0x180012fc7  mov     r9, rdx
0x180012fca  mov     rcx, r8
0x180012fcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180012fd2  mov     rdx, rax
0x180012fd5  mov     rcx, r9
0x180012fd8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180012fdd  mov     ecx, [r8+10h]
0x180012fe1  mov     [rsp+0E8h+cchCount2], ecx; cchCount2
0x180012fe5  mov     [rsp+0E8h+lpString2], rdx; lpString2
0x180012fea  mov     r9d, [r9+10h]; cchCount1
0x180012fee  mov     r8, rax; lpString1
0x180012ff1  mov     edx, 1; dwCmpFlags
0x180012ff6  mov     ecx, 400h; Locale
0x180012ffb  call    cs:__imp_CompareStringW
0x180013002  nop     dword ptr [rax+rax+00h]
0x180013007  test    eax, eax
0x180013009  jnz     short loc_18001305B
0x18001300b  lea     rdx, aComparestringw; "CompareStringW"
0x180013012  lea     rcx, [rsp+0E8h+var_B0]
0x180013017  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001301c  mov     rbx, rax
0x18001301f  call    cs:__imp_GetLastError
0x180013026  nop     dword ptr [rax+rax+00h]
0x18001302b  mov     [rsp+0E8h+var_B8], eax
0x18001302f  mov     [rsp+0E8h+var_B4], 0
0x180013037  mov     r8, rbx
0x18001303a  lea     rdx, [rsp+0E8h+var_B8]
0x18001303f  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180013044  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180013049  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180013050  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180013055  call    _CxxThrowException_0
0x18001305b  cmp     eax, 2
0x18001305e  setz    al
0x180013061  mov     rcx, [rsp+0E8h+var_18]
0x180013069  xor     rcx, rsp; StackCookie
0x18001306c  call    __security_check_cookie
0x180013071  add     rsp, 0E0h
0x180013078  pop     rbx
0x180013079  retn
```
