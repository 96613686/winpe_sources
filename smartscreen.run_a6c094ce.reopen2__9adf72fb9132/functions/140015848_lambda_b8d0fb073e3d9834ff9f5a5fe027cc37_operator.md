# _lambda_b8d0fb073e3d9834ff9f5a5fe027cc37_::operator()

- ea: `0x140015848`
- end: `0x14001599e`
- name: `_lambda_b8d0fb073e3d9834ff9f5a5fe027cc37_::operator()`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003bc2c`

## callees

- `0x140004370`
- `0x1400055ac`
- `0x140015724`
- `0x140015848`
- `0x1400159a4`
- `0x1400159c4`
- `0x140015b14`
- `0x140015d14`
- `0x1400184f0`
- `0x140026c20`
- `0x140040818`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14001591b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14001591b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400158f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001595e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400158f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001595e`

## string_xrefs

- `0x14001588e`: `onecore\amcore\smartscreen\src\client\urlrep\src\com_api.cpp`

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
0x140015848  mov     [rsp-8+arg_8], rbx
0x14001584d  push    rbp
0x14001584e  lea     rbp, [rsp-57h]
0x140015853  sub     rsp, 0D0h
0x14001585a  mov     rax, cs:__security_cookie
0x140015861  xor     rax, rsp
0x140015864  mov     [rbp+57h+var_10], rax
0x140015868  mov     rbx, rcx
0x14001586b  mov     rcx, [rcx]
0x14001586e  add     rcx, 40h ; '@'
0x140015872  lea     rdx, [rbp+57h+var_48]
0x140015876  call    ?ToJson@UrlRepExperience@ux@os_smartscreen@@QEBA?AV?$optional@Vjbuilder@ux@os_smartscreen@@@std@@XZ; os_smartscreen::ux::UrlRepExperience::ToJson(void)
0x14001587b  nop
0x14001587c  cmp     [rbp+57h+var_18], 0
0x140015880  jnz     short loc_1400158B0
0x140015882  mov     rcx, [rbp+5Fh]; this
0x140015886  mov     ebx, 80004005h
0x14001588b  mov     r9d, ebx; char *
0x14001588e  lea     r8, aOnecoreAmcoreS_11; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140015895  mov     edx, 208h; void *
0x14001589a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001589f  nop
0x1400158a0  lea     rcx, [rbp+57h+var_48]
0x1400158a4  call    ??1?$_Optional_destruct_base@Vjbuilder@ux@os_smartscreen@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>::~_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>(void)
0x1400158a9  mov     eax, ebx
0x1400158ab  jmp     loc_140015980
0x1400158b0  lea     rcx, [rbp+57h+var_48]
0x1400158b4  call    ?value@?$optional@Vjbuilder@ux@os_smartscreen@@@std@@QEGAAAEAVjbuilder@ux@os_smartscreen@@XZ; std::optional<os_smartscreen::ux::jbuilder>::value(void)
0x1400158b9  lea     rdx, [rbp+57h+var_A8]
0x1400158bd  mov     rcx, rax
0x1400158c0  call    ?to_string@jbuilder@ux@os_smartscreen@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; os_smartscreen::ux::jbuilder::to_string(void)
0x1400158c5  mov     rdx, rax
0x1400158c8  lea     rcx, [rbp+57h+var_88]
0x1400158cc  call    _anonymous_namespace___StringUtil__ToWString
0x1400158d1  nop
0x1400158d2  mov     rdx, rax
0x1400158d5  lea     rcx, [rbp+57h+sourceString]
0x1400158d9  call    ?Encrypt@data_protection@crypto@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; crypto::data_protection::Encrypt(std::wstring const &)
0x1400158de  nop
0x1400158df  lea     rcx, [rbp+57h+var_88]; this
0x1400158e3  call    ??1path@@QEAA@XZ; path::~path(void)
0x1400158e8  mov     [rbp+57h+string], 0
0x1400158f0  xor     ecx, ecx; string
0x1400158f2  call    cs:__imp_WindowsDeleteString
0x1400158f9  nop     dword ptr [rax+rax+00h]
0x1400158fe  mov     [rbp+57h+string], 0
0x140015906  lea     rcx, [rbp+57h+sourceString]
0x14001590a  cmp     [rbp+57h+var_50], 7
0x14001590f  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x140015914  lea     r8, [rbp+57h+string]; string
0x140015918  mov     edx, [rbp+57h+length]; length
0x14001591b  call    cs:__imp_WindowsCreateString
0x140015922  nop     dword ptr [rax+rax+00h]
0x140015927  mov     rcx, [rbp+5Fh]; this
0x14001592b  test    eax, eax
0x14001592d  jns     short loc_140015944
0x14001592f  mov     r9d, eax; char *
0x140015932  lea     r8, aOnecoreAmcoreS_6; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140015939  mov     edx, 12h; void *
0x14001593e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140015944  mov     rdx, [rbp+57h+string]
0x140015948  mov     [rbp+57h+string], 0
0x140015950  mov     rax, [rbx+8]
0x140015954  mov     rcx, [rax]
0x140015957  mov     [rcx], rdx
0x14001595a  mov     rcx, [rbp+57h+string]; string
0x14001595e  call    cs:__imp_WindowsDeleteString
0x140015965  nop     dword ptr [rax+rax+00h]
0x14001596a  nop
0x14001596b  lea     rcx, [rbp+57h+sourceString]; this
0x14001596f  call    ??1path@@QEAA@XZ; path::~path(void)
0x140015974  nop
0x140015975  lea     rcx, [rbp+57h+var_48]
0x140015979  call    ??1?$_Optional_destruct_base@Vjbuilder@ux@os_smartscreen@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>::~_Optional_destruct_base<os_smartscreen::ux::jbuilder,0>(void)
0x14001597e  xor     eax, eax
0x140015980  mov     rcx, [rbp+57h+var_10]
0x140015984  xor     rcx, rsp; StackCookie
0x140015987  call    __security_check_cookie
0x14001598c  mov     rbx, [rsp+0D0h+arg_8]
0x140015994  add     rsp, 0D0h
0x14001599b  pop     rbp
0x14001599c  retn
```
