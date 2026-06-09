# _lambda_51cbdb607f8f513cee7d74b44e200b85_::operator()

- ea: `0x18002e844`
- end: `0x18002ea28`
- name: `_lambda_51cbdb607f8f513cee7d74b44e200b85_::operator()`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e520`

## callees

- `0x180003110`
- `0x180005f50`
- `0x18000e5ac`
- `0x180010278`
- `0x180014928`
- `0x180021208`
- `0x1800212e4`
- `0x18002e844`
- `0x18002ea30`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e888`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e9f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e888`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e9f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e8dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e8dc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e909`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e909`

## string_xrefs

- `0x18002e8b4`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingsclientjson.cpp`
- `0x18002e9b4`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingsclientjson.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_51cbdb607f8f513cee7d74b44e200b85_::operator()(__int64 **a1, __int64 a2)
{
  char v4; // r14
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v9; // rbx
  const unsigned __int16 *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  bool v14; // bl
  __int64 (__fastcall *v15)(__int64, struct Windows::Data::Json::IJsonValue **); // rbx
  int v16; // eax
  const char *v17; // r9
  BOOL bIgnoreCase; // [rsp+20h] [rbp-88h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-88h]
  UINT32 length; // [rsp+30h] [rbp-78h] BYREF
  struct Windows::Data::Json::IJsonValue *v22; // [rsp+38h] [rbp-70h] BYREF
  HSTRING string; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v24[24]; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v25[32]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v4 = 0;
  length = 0;
  string = 0;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a2, &string);
  v7 = v6;
  if ( v6 >= 0 )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v9 = StringRawBuffer;
    if ( length > 9 && CompareStringOrdinal(L"ENDPOINT.", 9, StringRawBuffer, 9, 1) == 2 )
    {
      v10 = v9 + 9;
      v11 = **a1;
      v14 = 0;
      if ( v11 )
      {
        std::wstring::wstring((__int64)v25, (__int64)v10);
        v4 = 1;
        v12 = std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Find_lower_bound<std::wstring>(
                v11,
                v24,
                v25);
        if ( (unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
                                v13,
                                *(_QWORD *)(v12 + 16),
                                v25) )
          v14 = 1;
      }
      if ( (v4 & 1) != 0 )
        std::wstring::_Tidy_deallocate(v25);
      if ( !v14 )
      {
        v22 = 0;
        v15 = *(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)a2 + 56LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
        v16 = v15(a2, &v22);
        v7 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9F,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingsclientjson.cpp",
            (const char *)(unsigned int)v16,
            bIgnoreCasea);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
          goto LABEL_16;
        }
        try
        {
          OneSettingsClientJson::AddClient((OneSettingsClientJson *)a1[1], v10, v22);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0xA9,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingsclientjson.cpp",
            v17);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      }
    }
    v7 = 0;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x82,
    (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingsclientjson.cpp",
    (const char *)(unsigned int)v6,
    bIgnoreCase);
LABEL_16:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x18002e844  mov     [rsp+arg_10], rbx
0x18002e849  mov     [rsp+arg_18], rsi
0x18002e84e  push    rdi
0x18002e84f  push    r14
0x18002e851  push    r15
0x18002e853  sub     rsp, 90h
0x18002e85a  mov     rax, cs:__security_cookie
0x18002e861  xor     rax, rsp
0x18002e864  mov     [rsp+0A8h+var_28], rax
0x18002e86c  mov     r15, rdx
0x18002e86f  mov     rsi, rcx
0x18002e872  xor     r14d, r14d
0x18002e875  mov     [rsp+0A8h+length], r14d
0x18002e87a  mov     [rsp+0A8h+string], r14
0x18002e87f  mov     rax, [rdx]
0x18002e882  mov     rbx, [rax+30h]
0x18002e886  xor     ecx, ecx; string
0x18002e888  call    cs:__imp_WindowsDeleteString
0x18002e88e  mov     [rsp+0A8h+string], r14
0x18002e893  lea     rdx, [rsp+0A8h+string]
0x18002e898  mov     rcx, r15
0x18002e89b  mov     rax, rbx
0x18002e89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8a3  mov     ebx, eax
0x18002e8a5  test    eax, eax
0x18002e8a7  jns     short loc_18002E8CA
0x18002e8a9  mov     rcx, [rsp+0A8h]; this
0x18002e8b1  mov     r9d, eax; char *
0x18002e8b4  lea     r8, aOnecoreBaseFli_8; "onecore\\base\\flighting\\onesettings\\"...
0x18002e8bb  mov     edx, 82h; void *
0x18002e8c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e8c5  jmp     loc_18002E9F2
0x18002e8ca  mov     [rsp+0A8h+length], 0
0x18002e8d2  lea     rdx, [rsp+0A8h+length]; length
0x18002e8d7  mov     rcx, [rsp+0A8h+string]; string
0x18002e8dc  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e8e2  mov     rbx, rax
0x18002e8e5  mov     edx, 9; cchCount1
0x18002e8ea  cmp     [rsp+0A8h+length], edx
0x18002e8ee  jbe     loc_18002E9F0
0x18002e8f4  mov     [rsp+0A8h+bIgnoreCase], 1; int
0x18002e8fc  mov     r9d, edx; cchCount2
0x18002e8ff  mov     r8, rax; lpString2
0x18002e902  lea     rcx, ?s_tagEndpoint@OneSettingsClientJson@@0QBGB; "ENDPOINT."
0x18002e909  call    cs:__imp_CompareStringOrdinal
0x18002e90f  cmp     eax, 2
0x18002e912  jnz     loc_18002E9F0
0x18002e918  lea     rdi, [rbx+12h]
0x18002e91c  mov     rax, [rsi]
0x18002e91f  mov     rbx, [rax]
0x18002e922  test    rbx, rbx
0x18002e925  jz      short loc_18002E963
0x18002e927  mov     rdx, rdi
0x18002e92a  lea     rcx, [rsp+0A8h+var_48]
0x18002e92f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e934  mov     r14d, 1
0x18002e93a  lea     r8, [rsp+0A8h+var_48]
0x18002e93f  lea     rdx, [rsp+0A8h+var_60]
0x18002e944  mov     rcx, rbx
0x18002e947  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18002e94c  lea     r8, [rsp+0A8h+var_48]
0x18002e951  mov     rdx, [rax+10h]
0x18002e955  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x18002e95a  test    al, al
0x18002e95c  jz      short loc_18002E963
0x18002e95e  mov     bl, r14b
0x18002e961  jmp     short loc_18002E965
0x18002e963  xor     bl, bl
0x18002e965  test    r14b, 1
0x18002e969  jz      short loc_18002E975
0x18002e96b  lea     rcx, [rsp+0A8h+var_48]
0x18002e970  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e975  test    bl, bl
0x18002e977  jnz     short loc_18002E9F0
0x18002e979  mov     [rsp+0A8h+var_70], 0
0x18002e982  mov     rax, [r15]
0x18002e985  mov     rbx, [rax+38h]
0x18002e989  lea     rcx, [rsp+0A8h+var_70]
0x18002e98e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e993  lea     rdx, [rsp+0A8h+var_70]
0x18002e998  mov     rcx, r15
0x18002e99b  mov     rax, rbx
0x18002e99e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9a3  mov     ebx, eax
0x18002e9a5  test    eax, eax
0x18002e9a7  jns     short loc_18002E9D2
0x18002e9a9  mov     rcx, [rsp+0A8h]; this
0x18002e9b1  mov     r9d, eax; char *
0x18002e9b4  lea     r8, aOnecoreBaseFli_8; "onecore\\base\\flighting\\onesettings\\"...
0x18002e9bb  mov     edx, 9Fh; void *
0x18002e9c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e9c5  nop
0x18002e9c6  lea     rcx, [rsp+0A8h+var_70]
0x18002e9cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e9d0  jmp     short loc_18002E9F2
0x18002e9d2  mov     r8, [rsp+0A8h+var_70]; struct Windows::Data::Json::IJsonValue *
0x18002e9d7  mov     rdx, rdi; unsigned __int16 *
0x18002e9da  mov     rcx, [rsi+8]; this
0x18002e9de  call    ?AddClient@OneSettingsClientJson@@AEAAXPEBGPEAUIJsonValue@Json@Data@Windows@@@Z; OneSettingsClientJson::AddClient(ushort const *,Windows::Data::Json::IJsonValue *)
0x18002e9e3  nop
0x18002e9e4  jmp     short $+2
0x18002e9e6  lea     rcx, [rsp+0A8h+var_70]
0x18002e9eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e9f0  xor     ebx, ebx
0x18002e9f2  mov     rcx, [rsp+0A8h+string]; string
0x18002e9f7  call    cs:__imp_WindowsDeleteString
0x18002e9fd  mov     eax, ebx
0x18002e9ff  mov     rcx, [rsp+0A8h+var_28]
0x18002ea07  xor     rcx, rsp; StackCookie
0x18002ea0a  call    __security_check_cookie
0x18002ea0f  lea     r11, [rsp+0A8h+var_18]
0x18002ea17  mov     rbx, [r11+30h]
0x18002ea1b  mov     rsi, [r11+38h]
0x18002ea1f  mov     rsp, r11
0x18002ea22  pop     r15
0x18002ea24  pop     r14
0x18002ea26  pop     rdi
0x18002ea27  retn
```
