# Windows::System::Internal::Implementation::UserProfileManager::ReadUserFromRegistryAndAddToMap(ushort const *)

- ea: `0x1800c2ae0`
- end: `0x1800c2d10`
- name: `?ReadUserFromRegistryAndAddToMap@UserProfileManager@Implementation@Internal@System@Windows@@AEAAXPEBG@Z`
- size: `560`
- prototype: `void(Windows::System::Internal::Implementation::UserProfileManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c2d18`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180012890`
- `0x180018d14`
- `0x18002799c`
- `0x18003d38c`
- `0x18004e75c`
- `0x1800624bc`
- `0x1800632e8`
- `0x18006371c`
- `0x180063748`
- `0x1800c2ae0`
- `0x1800ec010`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800c2c53`
- `msvcrt!wcsstr` at `0x1800c2c53`
- `msvcrt!_wtol` at `0x1800c2afe`
- `msvcrt!_wtol` at `0x1800c2c62`
- `msvcrt!_wtol` at `0x1800c2afe`
- `msvcrt!_wtol` at `0x1800c2c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2c43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2c43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2c07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2c07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2c7e`

## string_xrefs

- `0x1800c2ce9`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c2cfe`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::System::Internal::Implementation::UserProfileManager::ReadUserFromRegistryAndAddToMap(
        Windows::System::Internal::Implementation::UserProfileManager *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // eax
  _DWORD *v7; // rax
  __int64 (*v8)(void); // rbx
  __int64 (*v9)(void); // rax
  int v10; // eax
  const wchar_t *StringRawBuffer; // rax
  wchar_t *v12; // rax
  unsigned int v13; // ecx
  unsigned int v14; // eax
  const struct _tlgProvider_t *v15; // rax
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // eax
  int v19; // [rsp+20h] [rbp-48h]
  int v20; // [rsp+20h] [rbp-48h]
  __int64 v21; // [rsp+30h] [rbp-38h] BYREF
  HKEY v22; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-28h] BYREF
  int v24; // [rsp+50h] [rbp-18h] BYREF
  _BYTE v25[16]; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int v27; // [rsp+80h] [rbp+18h] BYREF
  HSTRING string; // [rsp+88h] [rbp+20h]

  v22 = 0;
  v3 = _wtol(a2);
  v27 = v3;
  if ( v3 - 16 > 0xFFFEF )
  {
    v15 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v15 > 3u )
    {
      v27 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)byte_18012C455,
        v16,
        v17,
        (__int64)&v27);
    }
  }
  else
  {
    v21 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v22,
      0);
    Windows::System::Internal::Implementation::UserProfileManager::CreateUserKey(v3, &v22);
    v23[0] = v22;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v4 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::UserProfile,Windows::System::Internal::IUserProfile,unsigned int &,HKEY__ *>(
           &v21,
           &v27,
           v23);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)(unsigned int)v4,
        v20);
    try
    {
      if ( (v3 & 0xFF000) != 0 )
      {
        v6 = *((_DWORD *)this + 32);
        if ( v6 >= v3 - 1 )
          v6 = v3 - 1;
        *((_DWORD *)this + 32) = v6;
      }
      else
      {
        v5 = *((unsigned int *)this + 30);
        if ( (unsigned int)v5 <= v3 + 1 )
          v5 = v3 + 1;
        *((_DWORD *)this + 30) = v5;
        if ( (unsigned int)(v5 - 16) > 0xFFFEF )
          MicrosoftTelemetryAssertTriggeredNoArgs(v5);
      }
      v23[0] = v21;
      v7 = std::pair<unsigned int const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>::pair<unsigned int const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>(
             &v24,
             &v27,
             v23);
      std::_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>>,0>>::insert(
        (char *)this + 104,
        v23,
        v7);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
      string = 0;
      v8 = *(__int64 (**)(void))(*(_QWORD *)v21 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v9 = v8;
    }
    catch ( std::bad_alloc )
    {
      v18 = wil::verify_hresult<long>(2147942414LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B2,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)v18,
        v19);
    }
    v10 = v9();
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)(unsigned int)v10,
        v20);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v12 = wcsstr(StringRawBuffer, L"UserMgr");
    if ( v12 )
    {
      v13 = _wtol(v12 + 7) + 1;
      v14 = *((_DWORD *)this + 31);
      if ( v14 <= v13 )
        v14 = v13;
      *((_DWORD *)this + 31) = v14;
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
}

```

## disassembly

```asm
0x1800c2ae0  mov     [rsp+arg_0], rbx
0x1800c2ae5  mov     [rsp+arg_8], rsi
0x1800c2aea  push    rdi
0x1800c2aeb  sub     rsp, 60h
0x1800c2aef  mov     rsi, rcx
0x1800c2af2  mov     [rsp+68h+var_30], 0
0x1800c2afb  mov     rcx, rdx; String
0x1800c2afe  call    cs:__imp__wtol
0x1800c2b04  mov     ebx, eax
0x1800c2b06  mov     [rsp+68h+arg_10], eax
0x1800c2b0d  add     eax, 0FFFFFFF0h
0x1800c2b10  mov     edi, 0FFFEFh
0x1800c2b15  cmp     eax, edi
0x1800c2b17  ja      loc_1800C2C9C
0x1800c2b1d  mov     [rsp+68h+var_38], 0
0x1800c2b26  xor     edx, edx
0x1800c2b28  lea     rcx, [rsp+68h+var_30]
0x1800c2b2d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800c2b32  lea     rdx, [rsp+68h+var_30]; HKEY *
0x1800c2b37  mov     ecx, ebx; Value
0x1800c2b39  call    ?CreateUserKey@UserProfileManager@Implementation@Internal@System@Windows@@SAJIPEAPEAUHKEY__@@@Z; Windows::System::Internal::Implementation::UserProfileManager::CreateUserKey(uint,HKEY__ * *)
0x1800c2b3e  mov     rax, [rsp+68h+var_30]
0x1800c2b43  mov     [rsp+68h+var_28], rax
0x1800c2b48  lea     rcx, [rsp+68h+var_38]
0x1800c2b4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2b52  lea     r8, [rsp+68h+var_28]
0x1800c2b57  lea     rdx, [rsp+68h+arg_10]
0x1800c2b5f  lea     rcx, [rsp+68h+var_38]
0x1800c2b64  call    ??$MakeAndInitialize@VUserProfile@Internal@System@Windows@@UIUserProfile@234@AEAIPEAUHKEY__@@@Details@WRL@Microsoft@@YAJPEAPEAUIUserProfile@Internal@System@Windows@@AEAI$$QEAPEAUHKEY__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::UserProfile,Windows::System::Internal::IUserProfile,uint &,HKEY__ *>(Windows::System::Internal::IUserProfile * *,uint &,HKEY__ * &&)
0x1800c2b69  mov     rcx, [rsp+68h]; this
0x1800c2b6e  test    eax, eax
0x1800c2b70  js      loc_1800C2CE6
0x1800c2b76  test    ebx, 0FF000h
0x1800c2b7c  jnz     short loc_1800C2B9A
0x1800c2b7e  lea     eax, [rbx+1]
0x1800c2b81  mov     ecx, [rsi+78h]
0x1800c2b84  cmp     ecx, eax
0x1800c2b86  cmovbe  ecx, eax
0x1800c2b89  mov     [rsi+78h], ecx
0x1800c2b8c  lea     eax, [rcx-10h]
0x1800c2b8f  cmp     eax, edi
0x1800c2b91  jbe     short loc_1800C2BAE
0x1800c2b93  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800c2b98  jmp     short loc_1800C2BAE
0x1800c2b9a  lea     ecx, [rbx-1]
0x1800c2b9d  mov     eax, [rsi+80h]
0x1800c2ba3  cmp     eax, ecx
0x1800c2ba5  cmovnb  eax, ecx
0x1800c2ba8  mov     [rsi+80h], eax
0x1800c2bae  mov     rax, [rsp+68h+var_38]
0x1800c2bb3  mov     [rsp+68h+var_28], rax
0x1800c2bb8  lea     r8, [rsp+68h+var_28]
0x1800c2bbd  lea     rdx, [rsp+68h+arg_10]
0x1800c2bc5  lea     rcx, [rsp+68h+var_18]
0x1800c2bca  call    ??$?0AEAIPEAUIUserProfile@Internal@System@Windows@@@?$pair@$$CBIV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@@std@@QEAA@AEAI$$QEAPEAUIUserProfile@Internal@System@Windows@@PEAPEAX@Z; std::pair<uint const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>::pair<uint const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>(uint &,Windows::System::Internal::IUserProfile * &&,void * *)
0x1800c2bcf  nop
0x1800c2bd0  lea     rcx, [rsi+68h]
0x1800c2bd4  mov     r8, rax
0x1800c2bd7  lea     rdx, [rsp+68h+var_28]
0x1800c2bdc  call    ?insert@?$_Tree@V?$_Tmap_traits@IV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBIV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@@2@@Z; std::_Tree<std::_Tmap_traits<uint,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>>>,0>>::insert(std::pair<uint const,Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>> &&)
0x1800c2be1  nop
0x1800c2be2  lea     rcx, [rsp+68h+var_10]
0x1800c2be7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2bec  nop
0x1800c2bed  mov     [rsp+68h+string], 0
0x1800c2bf9  mov     rdi, [rsp+68h+var_38]
0x1800c2bfe  mov     rax, [rdi]
0x1800c2c01  mov     rbx, [rax+38h]
0x1800c2c05  xor     ecx, ecx; string
0x1800c2c07  call    cs:__imp_WindowsDeleteString
0x1800c2c0d  mov     [rsp+68h+string], 0
0x1800c2c19  lea     rdx, [rsp+68h+string]
0x1800c2c21  mov     rcx, rdi
0x1800c2c24  mov     rax, rbx
0x1800c2c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2c2c  mov     rcx, [rsp+68h]; this
0x1800c2c31  test    eax, eax
0x1800c2c33  js      loc_1800C2CFB
0x1800c2c39  xor     edx, edx; length
0x1800c2c3b  mov     rcx, [rsp+68h+string]; string
0x1800c2c43  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2c49  lea     rdx, aUsermgr; "UserMgr"
0x1800c2c50  mov     rcx, rax; Str
0x1800c2c53  call    cs:__imp_wcsstr
0x1800c2c59  test    rax, rax
0x1800c2c5c  jz      short loc_1800C2C76
0x1800c2c5e  lea     rcx, [rax+0Eh]; String
0x1800c2c62  call    cs:__imp__wtol
0x1800c2c68  lea     ecx, [rax+1]
0x1800c2c6b  mov     eax, [rsi+7Ch]
0x1800c2c6e  cmp     eax, ecx
0x1800c2c70  cmovbe  eax, ecx
0x1800c2c73  mov     [rsi+7Ch], eax
0x1800c2c76  mov     rcx, [rsp+68h+string]; string
0x1800c2c7e  call    cs:__imp_WindowsDeleteString
0x1800c2c84  mov     [rsp+68h+string], 0
0x1800c2c90  lea     rcx, [rsp+68h+var_38]
0x1800c2c95  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2c9a  jmp     short loc_1800C2CCC
0x1800c2c9c  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800c2ca1  mov     ecx, [rax]
0x1800c2ca3  cmp     ecx, 3
0x1800c2ca6  jbe     short loc_1800C2CCC
0x1800c2ca8  mov     [rsp+68h+arg_10], ebx
0x1800c2caf  lea     rcx, [rsp+68h+arg_10]
0x1800c2cb7  mov     qword ptr [rsp+68h+var_48], rcx
0x1800c2cbc  lea     rdx, byte_18012C455
0x1800c2cc3  mov     rcx, rax
0x1800c2cc6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800c2ccb  nop
0x1800c2ccc  lea     rcx, [rsp+68h+var_30]
0x1800c2cd1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c2cd6  mov     rbx, [rsp+68h+arg_0]
0x1800c2cdb  mov     rsi, [rsp+68h+arg_8]
0x1800c2ce0  add     rsp, 60h
0x1800c2ce4  pop     rdi
0x1800c2ce5  retn
0x1800c2ce6  mov     r9d, eax; char *
0x1800c2ce9  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c2cf0  mov     edx, 2A1h; void *
0x1800c2cf5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c2cfb  mov     r9d, eax; char *
0x1800c2cfe  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x1800c2d05  mov     edx, 2B6h; void *
0x1800c2d0a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
