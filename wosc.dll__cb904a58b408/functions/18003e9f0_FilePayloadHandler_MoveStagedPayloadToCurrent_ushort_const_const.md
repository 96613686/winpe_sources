# FilePayloadHandler::MoveStagedPayloadToCurrent(ushort const * const)

- ea: `0x18003e9f0`
- end: `0x18003eb14`
- name: `?MoveStagedPayloadToCurrent@FilePayloadHandler@@UEAAXQEBG@Z`
- size: `292`
- prototype: `void __fastcall(FilePayloadHandler *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180003110`
- `0x1800101e0`
- `0x180010278`
- `0x180013340`
- `0x180019e68`
- `0x18003c690`
- `0x18003e104`
- `0x18003e9f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18003eaba`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18003eaba`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003ea89`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003ea89`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall FilePayloadHandler::MoveStagedPayloadToCurrent(FilePayloadHandler *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  const WCHAR *v6; // rax
  LPCWSTR v7; // rdx
  const char *v8; // r9
  const WCHAR *v9; // rax
  const char *v10; // r9
  _BYTE v11[32]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v13[32]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = std::operator+<unsigned short>(v13, (char *)this + 8, L"\\Staged\\");
  std::operator+<unsigned short>(v11, v4, a2);
  std::wstring::_Tidy_deallocate(v13);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40);
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
  FilePayloadHandler::CreateFullPath(v12, v5);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 72);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  if ( !MoveFileExW(v6, v7, 1u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
      v8);
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
  if ( !RemoveDirectoryW(v9) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
      v10);
  std::wstring::_Tidy_deallocate(v12);
  std::wstring::_Tidy_deallocate(v11);
}

```

## disassembly

```asm
0x18003e9f0  mov     [rsp+arg_10], rbx
0x18003e9f5  push    rdi
0x18003e9f6  sub     rsp, 90h
0x18003e9fd  mov     rax, cs:__security_cookie
0x18003ea04  xor     rax, rsp
0x18003ea07  mov     [rsp+98h+var_18], rax
0x18003ea0f  mov     rbx, rdx
0x18003ea12  mov     rdi, rcx
0x18003ea15  lea     rdx, [rcx+8]
0x18003ea19  lea     r8, aStaged; "\\Staged\\"
0x18003ea20  lea     rcx, [rsp+98h+var_38]
0x18003ea25  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003ea2a  nop
0x18003ea2b  mov     r8, rbx
0x18003ea2e  mov     rdx, rax
0x18003ea31  lea     rcx, [rsp+98h+var_78]
0x18003ea36  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003ea3b  nop
0x18003ea3c  lea     rcx, [rsp+98h+var_38]
0x18003ea41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ea46  lea     rcx, [rdi+28h]
0x18003ea4a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ea4f  mov     r8, rax
0x18003ea52  lea     rcx, [rsp+98h+var_78]
0x18003ea57  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ea5c  mov     rdx, rax
0x18003ea5f  lea     rcx, [rsp+98h+var_58]
0x18003ea64  call    ?CreateFullPath@FilePayloadHandler@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; FilePayloadHandler::CreateFullPath(ushort const *,ushort const *)
0x18003ea69  nop
0x18003ea6a  lea     rcx, [rdi+48h]
0x18003ea6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ea73  mov     rdx, rax
0x18003ea76  lea     rcx, [rsp+98h+var_58]
0x18003ea7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ea80  mov     rcx, rax; lpExistingFileName
0x18003ea83  mov     r8d, 1; dwFlags
0x18003ea89  call    cs:__imp_MoveFileExW
0x18003ea8f  mov     rcx, [rsp+98h]; this
0x18003ea97  test    eax, eax
0x18003ea99  jnz     short loc_18003EAAD
0x18003ea9b  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003eaa2  mov     edx, 93h; void *
0x18003eaa7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003eaad  lea     rcx, [rsp+98h+var_78]
0x18003eab2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003eab7  mov     rcx, rax; lpPathName
0x18003eaba  call    cs:__imp_RemoveDirectoryW
0x18003eac0  mov     rcx, [rsp+98h]; this
0x18003eac8  test    eax, eax
0x18003eaca  jnz     short loc_18003EADE
0x18003eacc  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003ead3  mov     edx, 94h; void *
0x18003ead8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003eade  lea     rcx, [rsp+98h+var_58]
0x18003eae3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003eae8  nop
0x18003eae9  lea     rcx, [rsp+98h+var_78]
0x18003eaee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003eaf3  mov     rcx, [rsp+98h+var_18]
0x18003eafb  xor     rcx, rsp; StackCookie
0x18003eafe  call    __security_check_cookie
0x18003eb03  mov     rbx, [rsp+98h+arg_10]
0x18003eb0b  add     rsp, 90h
0x18003eb12  pop     rdi
0x18003eb13  retn
```
