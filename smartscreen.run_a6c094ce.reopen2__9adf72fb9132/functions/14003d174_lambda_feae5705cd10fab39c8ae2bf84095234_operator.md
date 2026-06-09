# _lambda_feae5705cd10fab39c8ae2bf84095234_::operator()

- ea: `0x14003d174`
- end: `0x14003d264`
- name: `_lambda_feae5705cd10fab39c8ae2bf84095234_::operator()`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14003bd4c`

## callees

- `0x140004370`
- `0x140015724`
- `0x140022448`
- `0x140026c20`
- `0x14003c5c4`
- `0x14003d174`
- `0x14003ec8c`
- `0x140041c5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003d214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003d214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003d1f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003d1f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_feae5705cd10fab39c8ae2bf84095234_::operator()(__int64 a1)
{
  char v2; // bl
  __int64 v3; // rax
  __int64 v4; // rax
  HSTRING *v5; // rax
  unsigned int v6; // edi
  HSTRING string; // [rsp+28h] [rbp-21h] BYREF
  _BYTE v9[32]; // [rsp+30h] [rbp-19h] BYREF
  _BYTE v10[32]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v11[40]; // [rsp+70h] [rbp+27h] BYREF

  v2 = 0;
  os_smartscreen::ux::NotificationBody::GetElementsJson(*(_QWORD *)a1 + 104LL, v11);
  if ( v11[32] )
  {
    v3 = std::string::string(v9, v11);
    v4 = anonymous_namespace_::StringUtil::ToWString(v10, v3);
    v5 = (HSTRING *)windows::rt::create_hstring(&string, v4);
    v2 = 3;
    v6 = WindowsDuplicateString(*v5, **(HSTRING ***)(a1 + 8));
  }
  else
  {
    v6 = -2147467259;
  }
  if ( (v2 & 2) != 0 )
  {
    v2 &= ~2u;
    WindowsDeleteString(string);
    string = 0;
  }
  if ( (v2 & 1) != 0 )
    path::~path((path *)v10);
  std::_Optional_destruct_base<std::string,0>::~_Optional_destruct_base<std::string,0>(v11);
  return v6;
}

```

## disassembly

```asm
0x14003d174  mov     [rsp-8+arg_8], rbx
0x14003d179  mov     [rsp-8+arg_10], rdi
0x14003d17e  push    rbp
0x14003d17f  lea     rbp, [rsp-57h]
0x14003d184  sub     rsp, 0A0h
0x14003d18b  mov     rax, cs:__security_cookie
0x14003d192  xor     rax, rsp
0x14003d195  mov     [rbp+57h+var_8], rax
0x14003d199  mov     rdi, rcx
0x14003d19c  xor     ebx, ebx
0x14003d19e  mov     [rbp+57h+var_80], ebx
0x14003d1a1  mov     rcx, [rcx]
0x14003d1a4  add     rcx, 68h ; 'h'
0x14003d1a8  lea     rdx, [rbp+57h+var_30]
0x14003d1ac  call    ?GetElementsJson@NotificationBody@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@XZ; os_smartscreen::ux::NotificationBody::GetElementsJson(void)
0x14003d1b1  nop
0x14003d1b2  cmp     [rbp+57h+var_10], bl
0x14003d1b5  jz      short loc_14003D203
0x14003d1b7  lea     rdx, [rbp+57h+var_30]
0x14003d1bb  lea     rcx, [rbp+57h+var_70]
0x14003d1bf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x14003d1c4  mov     rdx, rax
0x14003d1c7  lea     rcx, [rbp+57h+var_50]
0x14003d1cb  call    _anonymous_namespace___StringUtil__ToWString
0x14003d1d0  nop
0x14003d1d1  mov     [rbp+57h+var_80], 1
0x14003d1d8  mov     rdx, rax
0x14003d1db  lea     rcx, [rbp+57h+string]
0x14003d1df  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003d1e4  mov     ebx, 3
0x14003d1e9  mov     rdx, [rdi+8]
0x14003d1ed  mov     rdx, [rdx]; newString
0x14003d1f0  mov     rcx, [rax]; string
0x14003d1f3  call    cs:__imp_WindowsDuplicateString
0x14003d1fa  nop     dword ptr [rax+rax+00h]
0x14003d1ff  mov     edi, eax
0x14003d201  jmp     short loc_14003D208
0x14003d203  mov     edi, 80004005h
0x14003d208  test    bl, 2
0x14003d20b  jz      short loc_14003D228
0x14003d20d  and     ebx, 0FFFFFFFDh
0x14003d210  mov     rcx, [rbp+57h+string]; string
0x14003d214  call    cs:__imp_WindowsDeleteString
0x14003d21b  nop     dword ptr [rax+rax+00h]
0x14003d220  mov     [rbp+57h+string], 0
0x14003d228  test    bl, 1
0x14003d22b  jz      short loc_14003D237
0x14003d22d  lea     rcx, [rbp+57h+var_50]; this
0x14003d231  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003d236  nop
0x14003d237  lea     rcx, [rbp+57h+var_30]
0x14003d23b  call    ??1?$_Optional_destruct_base@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::string,0>::~_Optional_destruct_base<std::string,0>(void)
0x14003d240  mov     eax, edi
0x14003d242  mov     rcx, [rbp+57h+var_8]
0x14003d246  xor     rcx, rsp; StackCookie
0x14003d249  call    __security_check_cookie
0x14003d24e  lea     r11, [rsp+0A0h+var_s0]
0x14003d256  mov     rbx, [r11+18h]
0x14003d25a  mov     rdi, [r11+20h]
0x14003d25e  mov     rsp, r11
0x14003d261  pop     rbp
0x14003d262  retn
```
