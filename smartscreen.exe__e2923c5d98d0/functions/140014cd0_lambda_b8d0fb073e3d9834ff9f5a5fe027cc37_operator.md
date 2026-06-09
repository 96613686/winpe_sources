# _lambda_b8d0fb073e3d9834ff9f5a5fe027cc37_::operator()

- ea: `0x140014cd0`
- end: `0x140014e13`
- name: `_lambda_b8d0fb073e3d9834ff9f5a5fe027cc37_::operator()`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003a5e8`

## callees

- `0x140004190`
- `0x140005260`
- `0x140014bb8`
- `0x140014cd0`
- `0x140014e1c`
- `0x140014e3c`
- `0x140014f80`
- `0x14001516c`
- `0x140016ce4`
- `0x140025aa0`
- `0x14003f0f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140014d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140014d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140014d7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140014dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140014d7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140014dda`

## string_xrefs

- `0x140014d16`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_b8d0fb073e3d9834ff9f5a5fe027cc37_::operator()(__int64 a1)
{
  __int64 v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rcx
  HRESULT v6; // eax
  HSTRING v7; // rdx
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  _BYTE v9[32]; // [rsp+28h] [rbp-51h] BYREF
  _BYTE v10[32]; // [rsp+48h] [rbp-31h] BYREF
  PCNZWCH sourceString[2]; // [rsp+68h] [rbp-11h] BYREF
  UINT32 length; // [rsp+78h] [rbp-1h]
  unsigned __int64 v13; // [rsp+80h] [rbp+7h]
  _BYTE v14[56]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  os_smartscreen::ux::UrlRepExperience::ToJson(*(_QWORD *)a1 + 64LL, v14);
  if ( v14[48] )
  {
    v3 = std::optional<os_smartscreen::ux::jbuilder>::value(v14);
    v4 = os_smartscreen::ux::jbuilder::to_string(v3, v9);
    anonymous_namespace_::StringUtil::ToWString(v10, v4);
    crypto::data_protection::Encrypt((LPWSTR)sourceString);
    path::~path((path *)v10);
    WindowsDeleteString(0);
    string = 0;
    v5 = (const WCHAR *)sourceString;
    if ( v13 > 7 )
      v5 = sourceString[0];
    v6 = WindowsCreateString(v5, length, &string);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\rt.h",
        (const char *)(unsigned int)v6,
        (int)string);
    v7 = string;
    string = 0;
    ***(_QWORD ***)(a1 + 8) = v7;
    WindowsDeleteString(string);
    path::~path((path *)sourceString);
    std::_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>::~_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>(v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\com_api.cpp",
      (const char *)0x80004005LL,
      (int)string);
    std::_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>::~_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>(v14);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x140014cd0  mov     [rsp-8+arg_8], rbx
0x140014cd5  push    rbp
0x140014cd6  lea     rbp, [rsp-57h]
0x140014cdb  sub     rsp, 0D0h
0x140014ce2  mov     rax, cs:__security_cookie
0x140014ce9  xor     rax, rsp
0x140014cec  mov     [rbp+57h+var_10], rax
0x140014cf0  mov     rbx, rcx
0x140014cf3  mov     rcx, [rcx]
0x140014cf6  add     rcx, 40h ; '@'
0x140014cfa  lea     rdx, [rbp+57h+var_48]
0x140014cfe  call    ?ToJson@UrlRepExperience@ux@os_smartscreen@@QEBA?AV?$optional@Vjbuilder@ux@os_smartscreen@@@std@@XZ; os_smartscreen::ux::UrlRepExperience::ToJson(void)
0x140014d03  nop
0x140014d04  cmp     [rbp+57h+var_18], 0
0x140014d08  jnz     short loc_140014D38
0x140014d0a  mov     rcx, [rbp+5Fh]; this
0x140014d0e  mov     ebx, 80004005h
0x140014d13  mov     r9d, ebx; char *
0x140014d16  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140014d1d  mov     edx, 208h; void *
0x140014d22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014d27  nop
0x140014d28  lea     rcx, [rbp+57h+var_48]
0x140014d2c  call    ??1?$_Optional_destruct_base@Vjbuilder@ux@os_smartscreen@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>::~_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>(void)
0x140014d31  mov     eax, ebx
0x140014d33  jmp     loc_140014DF6
0x140014d38  lea     rcx, [rbp+57h+var_48]
0x140014d3c  call    ?value@?$optional@Vjbuilder@ux@os_smartscreen@@@std@@QEGAAAEAVjbuilder@ux@os_smartscreen@@XZ; std::optional<os_smartscreen::ux::jbuilder>::value(void)
0x140014d41  lea     rdx, [rbp+57h+var_A8]
0x140014d45  mov     rcx, rax
0x140014d48  call    ?to_string@jbuilder@ux@os_smartscreen@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; os_smartscreen::ux::jbuilder::to_string(void)
0x140014d4d  mov     rdx, rax
0x140014d50  lea     rcx, [rbp+57h+var_88]
0x140014d54  call    _anonymous_namespace___StringUtil__ToWString
0x140014d59  nop
0x140014d5a  mov     rdx, rax
0x140014d5d  lea     rcx, [rbp+57h+sourceString]
0x140014d61  call    ?Encrypt@data_protection@crypto@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; crypto::data_protection::Encrypt(std::wstring const &)
0x140014d66  nop
0x140014d67  lea     rcx, [rbp+57h+var_88]; this
0x140014d6b  call    ??1path@@QEAA@XZ; path::~path(void)
0x140014d70  mov     [rbp+57h+string], 0
0x140014d78  xor     ecx, ecx; string
0x140014d7a  call    cs:__imp_WindowsDeleteString
0x140014d80  mov     [rbp+57h+string], 0
0x140014d88  lea     rcx, [rbp+57h+sourceString]
0x140014d8c  cmp     [rbp+57h+var_50], 7
0x140014d91  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x140014d96  lea     r8, [rbp+57h+string]; string
0x140014d9a  mov     edx, [rbp+57h+length]; length
0x140014d9d  call    cs:__imp_WindowsCreateString
0x140014da3  mov     rcx, [rbp+5Fh]; this
0x140014da7  test    eax, eax
0x140014da9  jns     short loc_140014DC0
0x140014dab  mov     r9d, eax; char *
0x140014dae  lea     r8, aOnecoreAmcoreS_6; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140014db5  mov     edx, 12h; void *
0x140014dba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140014dc0  mov     rdx, [rbp+57h+string]
0x140014dc4  mov     [rbp+57h+string], 0
0x140014dcc  mov     rax, [rbx+8]
0x140014dd0  mov     rcx, [rax]
0x140014dd3  mov     [rcx], rdx
0x140014dd6  mov     rcx, [rbp+57h+string]; string
0x140014dda  call    cs:__imp_WindowsDeleteString
0x140014de0  nop
0x140014de1  lea     rcx, [rbp+57h+sourceString]; this
0x140014de5  call    ??1path@@QEAA@XZ; path::~path(void)
0x140014dea  nop
0x140014deb  lea     rcx, [rbp+57h+var_48]
0x140014def  call    ??1?$_Optional_destruct_base@Vjbuilder@ux@os_smartscreen@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>::~_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>(void)
0x140014df4  xor     eax, eax
0x140014df6  mov     rcx, [rbp+57h+var_10]
0x140014dfa  xor     rcx, rsp; StackCookie
0x140014dfd  call    __security_check_cookie
0x140014e02  mov     rbx, [rsp+0D0h+arg_8]
0x140014e0a  add     rsp, 0D0h
0x140014e11  pop     rbp
0x140014e12  retn
```
