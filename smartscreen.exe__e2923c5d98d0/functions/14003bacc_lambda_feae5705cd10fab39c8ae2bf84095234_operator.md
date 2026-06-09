# _lambda_feae5705cd10fab39c8ae2bf84095234_::operator()

- ea: `0x14003bacc`
- end: `0x14003bbaf`
- name: `_lambda_feae5705cd10fab39c8ae2bf84095234_::operator()`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14003a6f8`

## callees

- `0x140004190`
- `0x140014bb8`
- `0x1400212e0`
- `0x140025aa0`
- `0x14003af4c`
- `0x14003bacc`
- `0x14003d5c4`
- `0x140040514`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003bb66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003bb66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003bb4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003bb4b`

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
0x14003bacc  mov     [rsp-8+arg_8], rbx
0x14003bad1  mov     [rsp-8+arg_10], rdi
0x14003bad6  push    rbp
0x14003bad7  lea     rbp, [rsp-57h]
0x14003badc  sub     rsp, 0A0h
0x14003bae3  mov     rax, cs:__security_cookie
0x14003baea  xor     rax, rsp
0x14003baed  mov     [rbp+57h+var_8], rax
0x14003baf1  mov     rdi, rcx
0x14003baf4  xor     ebx, ebx
0x14003baf6  mov     [rbp+57h+var_80], ebx
0x14003baf9  mov     rcx, [rcx]
0x14003bafc  add     rcx, 68h ; 'h'
0x14003bb00  lea     rdx, [rbp+57h+var_30]
0x14003bb04  call    ?GetElementsJson@NotificationBody@ux@os_smartscreen@@QEBA?AV?$optional@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@XZ; os_smartscreen::ux::NotificationBody::GetElementsJson(void)
0x14003bb09  nop
0x14003bb0a  cmp     [rbp+57h+var_10], bl
0x14003bb0d  jz      short loc_14003BB55
0x14003bb0f  lea     rdx, [rbp+57h+var_30]
0x14003bb13  lea     rcx, [rbp+57h+var_70]
0x14003bb17  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x14003bb1c  mov     rdx, rax
0x14003bb1f  lea     rcx, [rbp+57h+var_50]
0x14003bb23  call    _anonymous_namespace___StringUtil__ToWString
0x14003bb28  nop
0x14003bb29  mov     [rbp+57h+var_80], 1
0x14003bb30  mov     rdx, rax
0x14003bb33  lea     rcx, [rbp+57h+string]
0x14003bb37  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003bb3c  mov     ebx, 3
0x14003bb41  mov     rdx, [rdi+8]
0x14003bb45  mov     rdx, [rdx]; newString
0x14003bb48  mov     rcx, [rax]; string
0x14003bb4b  call    cs:__imp_WindowsDuplicateString
0x14003bb51  mov     edi, eax
0x14003bb53  jmp     short loc_14003BB5A
0x14003bb55  mov     edi, 80004005h
0x14003bb5a  test    bl, 2
0x14003bb5d  jz      short loc_14003BB74
0x14003bb5f  and     ebx, 0FFFFFFFDh
0x14003bb62  mov     rcx, [rbp+57h+string]; string
0x14003bb66  call    cs:__imp_WindowsDeleteString
0x14003bb6c  mov     [rbp+57h+string], 0
0x14003bb74  test    bl, 1
0x14003bb77  jz      short loc_14003BB83
0x14003bb79  lea     rcx, [rbp+57h+var_50]; this
0x14003bb7d  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003bb82  nop
0x14003bb83  lea     rcx, [rbp+57h+var_30]
0x14003bb87  call    ??1?$_Optional_destruct_base@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::string,0>::~_Optional_destruct_base<std::string,0>(void)
0x14003bb8c  mov     eax, edi
0x14003bb8e  mov     rcx, [rbp+57h+var_8]
0x14003bb92  xor     rcx, rsp; StackCookie
0x14003bb95  call    __security_check_cookie
0x14003bb9a  lea     r11, [rsp+0A0h+var_s0]
0x14003bba2  mov     rbx, [r11+18h]
0x14003bba6  mov     rdi, [r11+20h]
0x14003bbaa  mov     rsp, r11
0x14003bbad  pop     rbp
0x14003bbae  retn
```
