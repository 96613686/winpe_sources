# Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetIdentityPropertyValue(Microsoft::Bing::LanguageUnderstanding::Client::Authentication::IdentityProp,HSTRING__ * *)

- ea: `0x18004b1a8`
- end: `0x18004b64e`
- name: `?GetIdentityPropertyValue@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@QEAAJW4IdentityProp@23456@PEAPEAUHSTRING__@@@Z`
- size: `1190`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800394d0`
- `0x1801c98bc`
- `0x1801ca044`

## callees

- `0x180021944`
- `0x180026508`
- `0x18002895c`
- `0x18003151c`
- `0x18004b1a8`
- `0x18004b654`
- `0x18004d094`
- `0x1800be48c`
- `0x1801c5608`
- `0x1801caad8`
- `0x1801cb138`
- `0x1801cb2f4`
- `0x1801cd68c`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b397`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b4bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b5bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b5ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b5bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b5ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b625`

## string_xrefs

- `0x18004b227`: `CortanaServiceTarget`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetIdentityPropertyValue(
        Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *a1,
        int a2,
        HSTRING *a3)
{
  int v5; // edx
  int v6; // edx
  unsigned int AuthenticationToken; // ebx
  __int64 v8; // rdx
  int ActiveUserKeyFilter; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  std::_Ref_count_base *v13; // rcx
  Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *v14; // rax
  __int64 v15; // rax
  int v16; // eax
  Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *v17; // rax
  __int64 v18; // rax
  int v19; // eax
  Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *v20; // rax
  HSTRING v21; // rcx
  HRESULT LastAuthenticationToken; // eax
  __int64 v23; // rdx
  int *v25; // [rsp+20h] [rbp-40h]
  Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *v26; // [rsp+30h] [rbp-30h] BYREF
  int v27[2]; // [rsp+38h] [rbp-28h] BYREF
  std::_Ref_count_base *v28[2]; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v29[8]; // [rsp+50h] [rbp-10h] BYREF
  std::_Ref_count_base *v30; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v32; // [rsp+88h] [rbp+28h] BYREF
  HSTRING string; // [rsp+98h] [rbp+38h] BYREF

  if ( a2 )
  {
    v5 = a2 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 != 1 )
        {
          AuthenticationToken = -2147023728;
          v8 = 589;
LABEL_57:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v8,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
            (const char *)AuthenticationToken,
            (int)v25);
          return AuthenticationToken;
        }
        v26 = 0;
        *(_QWORD *)v27 = 0;
        *(_OWORD *)v28 = 0;
        string = 0;
        ActiveUserKeyFilter = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveUserKeyFilter(a1);
        AuthenticationToken = ActiveUserKeyFilter;
        if ( ActiveUserKeyFilter < 0 )
        {
          v10 = 578;
LABEL_23:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
            (const char *)(unsigned int)ActiveUserKeyFilter,
            (int)v25);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          goto LABEL_45;
        }
        v25 = v27;
        ActiveUserKeyFilter = (*(__int64 (__fastcall **)(HSTRING, __int64, const wchar_t *, const wchar_t *))(*(_QWORD *)string + 48LL))(
                                string,
                                -2147483647,
                                L"Software\\Microsoft\\Windows\\CurrentVersion\\Search",
                                L"CortanaServiceTarget");
        AuthenticationToken = ActiveUserKeyFilter;
        if ( ActiveUserKeyFilter < 0 )
        {
          v10 = 579;
          goto LABEL_23;
        }
        v11 = std::shared_ptr<unsigned short>::shared_ptr<unsigned short>(v29, *(_QWORD *)v27, CoTaskMemFree);
        std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(v28, v11);
        if ( v30 )
          std::_Ref_count_base::_Decref(v30);
        v12 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)&v26);
        AuthenticationToken = v12;
        if ( v12 >= 0 )
        {
          v14 = v26;
          v26 = 0;
          *a3 = (HSTRING)v14;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          if ( v28[1] )
            std::_Ref_count_base::_Decref(v28[1]);
          AuthenticationToken = 0;
          goto LABEL_45;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x245,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
          (const char *)(unsigned int)v12,
          (int)v27);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        v13 = v28[1];
        if ( v28[1] )
LABEL_28:
          std::_Ref_count_base::_Decref(v13);
      }
      else
      {
        v26 = 0;
        *(_QWORD *)v27 = 0;
        *(_OWORD *)v28 = 0;
        string = 0;
        ActiveUserKeyFilter = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveUserKeyFilter(a1);
        AuthenticationToken = ActiveUserKeyFilter;
        if ( ActiveUserKeyFilter < 0 )
        {
          v10 = 563;
          goto LABEL_23;
        }
        v25 = v27;
        ActiveUserKeyFilter = (*(__int64 (__fastcall **)(HSTRING, __int64, const wchar_t *, const wchar_t *))(*(_QWORD *)string + 48LL))(
                                string,
                                -2147483647,
                                L"Software\\Microsoft\\Windows\\CurrentVersion\\Search",
                                L"CortanaUserAuthority");
        AuthenticationToken = ActiveUserKeyFilter;
        if ( ActiveUserKeyFilter < 0 )
        {
          v10 = 564;
          goto LABEL_23;
        }
        v15 = std::shared_ptr<unsigned short>::shared_ptr<unsigned short>(v29, *(_QWORD *)v27, CoTaskMemFree);
        std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(v28, v15);
        if ( v30 )
          std::_Ref_count_base::_Decref(v30);
        v16 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)&v26);
        AuthenticationToken = v16;
        if ( v16 >= 0 )
        {
          v17 = v26;
          v26 = 0;
          *a3 = (HSTRING)v17;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          if ( v28[1] )
            std::_Ref_count_base::_Decref(v28[1]);
          AuthenticationToken = 0;
          goto LABEL_45;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x236,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
          (const char *)(unsigned int)v16,
          (int)v27);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        v13 = v28[1];
        if ( v28[1] )
          goto LABEL_28;
      }
    }
    else
    {
      v26 = 0;
      *(_QWORD *)v27 = 0;
      *(_OWORD *)v28 = 0;
      string = 0;
      ActiveUserKeyFilter = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveUserKeyFilter(a1);
      AuthenticationToken = ActiveUserKeyFilter;
      if ( ActiveUserKeyFilter < 0 )
      {
        v10 = 548;
        goto LABEL_23;
      }
      v25 = v27;
      ActiveUserKeyFilter = (*(__int64 (__fastcall **)(HSTRING, __int64, const wchar_t *, const wchar_t *))(*(_QWORD *)string + 48LL))(
                              string,
                              -2147483647,
                              L"Software\\Microsoft\\Windows\\CurrentVersion\\Search",
                              L"CortanaUserId");
      AuthenticationToken = ActiveUserKeyFilter;
      if ( ActiveUserKeyFilter < 0 )
      {
        v10 = 549;
        goto LABEL_23;
      }
      v18 = std::shared_ptr<unsigned short>::shared_ptr<unsigned short>(v29, *(_QWORD *)v27, CoTaskMemFree);
      std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(v28, v18);
      if ( v30 )
        std::_Ref_count_base::_Decref(v30);
      v19 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)&v26);
      AuthenticationToken = v19;
      if ( v19 >= 0 )
      {
        v20 = v26;
        v26 = 0;
        *a3 = (HSTRING)v20;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        if ( v28[1] )
          std::_Ref_count_base::_Decref(v28[1]);
        AuthenticationToken = 0;
        goto LABEL_45;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x227,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
        (const char *)(unsigned int)v19,
        (int)v27);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      v13 = v28[1];
      if ( v28[1] )
        goto LABEL_28;
    }
LABEL_45:
    v21 = (HSTRING)v26;
LABEL_52:
    WindowsDeleteString(v21);
    return AuthenticationToken;
  }
  if ( Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::ShouldCacheToken(a1) )
  {
    Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::PreFetchAuthenticationTokenAsync(a1);
    string = 0;
    LastAuthenticationToken = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetLastAuthenticationToken(
                                a1,
                                (struct Microsoft::WRL::Wrappers::HString *)&string);
    AuthenticationToken = LastAuthenticationToken;
    if ( LastAuthenticationToken < 0 )
    {
      v23 = 530;
LABEL_51:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
        (const char *)(unsigned int)LastAuthenticationToken,
        (int)v25);
      v21 = string;
      goto LABEL_52;
    }
    LastAuthenticationToken = WindowsDuplicateString(string, a3);
    AuthenticationToken = LastAuthenticationToken;
    if ( LastAuthenticationToken < 0 )
    {
      v23 = 531;
      goto LABEL_51;
    }
    v32 = 1;
    *(_QWORD *)v27 = WindowsGetStringRawBuffer(string, 0);
    Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::GetIdentityPropertyValue<unsigned short const *,int>(
      v27,
      &v32);
    WindowsDeleteString(string);
  }
  else
  {
    AuthenticationToken = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetAuthenticationToken(
                            a1,
                            a3);
    if ( (AuthenticationToken & 0x80000000) != 0 )
    {
      v8 = 536;
      goto LABEL_57;
    }
    v32 = 0;
    string = (HSTRING)WindowsGetStringRawBuffer(*a3, 0);
    Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::GetIdentityPropertyValue<unsigned short const *,int>(
      &string,
      &v32);
  }
  return 0;
}

```

## disassembly

```asm
0x18004b1a8  mov     [rsp-18h+arg_0], rbx
0x18004b1ad  push    rbp
0x18004b1ae  push    rsi
0x18004b1af  push    rdi
0x18004b1b0  mov     rbp, rsp
0x18004b1b3  sub     rsp, 60h
0x18004b1b7  mov     rdi, r8
0x18004b1ba  mov     rbx, rcx
0x18004b1bd  xor     esi, esi
0x18004b1bf  test    edx, edx
0x18004b1c1  jz      loc_18004B55A
0x18004b1c7  sub     edx, 1
0x18004b1ca  jz      loc_18004B435
0x18004b1d0  sub     edx, 1
0x18004b1d3  jz      loc_18004B311
0x18004b1d9  cmp     edx, 1
0x18004b1dc  jz      short loc_18004B1ED
0x18004b1de  mov     ebx, 80070490h
0x18004b1e3  mov     edx, 24Dh
0x18004b1e8  jmp     loc_18004B608
0x18004b1ed  mov     [rbp+var_30], rsi
0x18004b1f1  mov     qword ptr [rbp+var_28], rsi
0x18004b1f5  xorps   xmm0, xmm0
0x18004b1f8  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18004b1fd  mov     [rbp+string], rsi
0x18004b201  lea     rdx, [rbp+string]
0x18004b205  call    ?GetActiveUserKeyFilter@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAV?$ComPtr@UISpAudioOrchestratorPolicyKeyFilter@@@WRL@6@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveUserKeyFilter(Microsoft::WRL::ComPtr<ISpAudioOrchestratorPolicyKeyFilter> &)
0x18004b20a  mov     ebx, eax
0x18004b20c  test    eax, eax
0x18004b20e  jns     short loc_18004B217
0x18004b210  mov     edx, 242h
0x18004b215  jmp     short loc_18004B250
0x18004b217  mov     rcx, [rbp+string]
0x18004b21b  mov     rax, [rcx]
0x18004b21e  lea     rdx, [rbp+var_28]
0x18004b222  mov     qword ptr [rsp+60h+var_40], rdx; int
0x18004b227  lea     r9, aCortanaservice; "CortanaServiceTarget"
0x18004b22e  lea     r8, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004b235  mov     rdx, 0FFFFFFFF80000001h
0x18004b23c  mov     rax, [rax+30h]
0x18004b240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b245  mov     ebx, eax
0x18004b247  test    eax, eax
0x18004b249  jns     short loc_18004B273
0x18004b24b  mov     edx, 243h; void *
0x18004b250  mov     r9d, eax; char *
0x18004b253  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004b25a  mov     rcx, [rbp+18h]; this
0x18004b25e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b263  nop
0x18004b264  lea     rcx, [rbp+string]
0x18004b268  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b26d  nop
0x18004b26e  jmp     loc_18004B30C
0x18004b273  mov     r8, cs:__imp_CoTaskMemFree
0x18004b27a  mov     rdx, qword ptr [rbp+var_28]
0x18004b27e  lea     rcx, [rbp+var_10]
0x18004b282  call    ??$?0GP6AXPEAX@Z$0A@@?$shared_ptr@G@std@@QEAA@PEAGP6AXPEAX@Z@Z; std::shared_ptr<ushort>::shared_ptr<ushort>(ushort *,void (*)(void *))
0x18004b287  mov     rdx, rax
0x18004b28a  lea     rcx, [rbp+var_20]
0x18004b28e  call    ??4?$shared_ptr@VCloudConnectionCookie@Halsey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(std::shared_ptr<Halsey::CloudConnectionCookie> &&)
0x18004b293  mov     rcx, [rbp+var_8]; this
0x18004b297  test    rcx, rcx
0x18004b29a  jz      short loc_18004B2A1
0x18004b29c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b2a1  lea     rdx, [rbp+var_28]
0x18004b2a5  lea     rcx, [rbp+var_30]; this
0x18004b2a9  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004b2ae  mov     ebx, eax
0x18004b2b0  test    eax, eax
0x18004b2b2  jns     short loc_18004B2E7
0x18004b2b4  mov     rcx, [rbp+18h]; this
0x18004b2b8  mov     r9d, eax; char *
0x18004b2bb  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004b2c2  mov     edx, 245h; void *
0x18004b2c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b2cc  nop
0x18004b2cd  lea     rcx, [rbp+string]
0x18004b2d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b2d6  nop
0x18004b2d7  mov     rcx, [rbp+var_20+8]; this
0x18004b2db  test    rcx, rcx
0x18004b2de  jz      short loc_18004B30C
0x18004b2e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b2e5  jmp     short loc_18004B30C
0x18004b2e7  mov     rax, [rbp+var_30]
0x18004b2eb  mov     [rbp+var_30], rsi
0x18004b2ef  mov     [rdi], rax
0x18004b2f2  lea     rcx, [rbp+string]
0x18004b2f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b2fb  nop
0x18004b2fc  mov     rcx, [rbp+var_20+8]; this
0x18004b300  test    rcx, rcx
0x18004b303  jz      short loc_18004B30A
0x18004b305  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b30a  mov     ebx, esi
0x18004b30c  jmp     loc_18004B554
0x18004b311  mov     [rbp+var_30], rsi
0x18004b315  mov     qword ptr [rbp+var_28], rsi
0x18004b319  xorps   xmm0, xmm0
0x18004b31c  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18004b321  mov     [rbp+string], rsi
0x18004b325  lea     rdx, [rbp+string]
0x18004b329  call    ?GetActiveUserKeyFilter@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAV?$ComPtr@UISpAudioOrchestratorPolicyKeyFilter@@@WRL@6@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveUserKeyFilter(Microsoft::WRL::ComPtr<ISpAudioOrchestratorPolicyKeyFilter> &)
0x18004b32e  mov     ebx, eax
0x18004b330  test    eax, eax
0x18004b332  jns     short loc_18004B33B
0x18004b334  mov     edx, 233h
0x18004b339  jmp     short loc_18004B374
0x18004b33b  mov     rcx, [rbp+string]
0x18004b33f  mov     rax, [rcx]
0x18004b342  lea     rdx, [rbp+var_28]
0x18004b346  mov     qword ptr [rsp+60h+var_40], rdx; int
0x18004b34b  lea     r9, aCortanauseraut; "CortanaUserAuthority"
0x18004b352  lea     r8, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004b359  mov     rdx, 0FFFFFFFF80000001h
0x18004b360  mov     rax, [rax+30h]
0x18004b364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b369  mov     ebx, eax
0x18004b36b  test    eax, eax
0x18004b36d  jns     short loc_18004B397
0x18004b36f  mov     edx, 234h; void *
0x18004b374  mov     r9d, eax; char *
0x18004b377  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004b37e  mov     rcx, [rbp+18h]; this
0x18004b382  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b387  nop
0x18004b388  lea     rcx, [rbp+string]
0x18004b38c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b391  nop
0x18004b392  jmp     loc_18004B430
0x18004b397  mov     r8, cs:__imp_CoTaskMemFree
0x18004b39e  mov     rdx, qword ptr [rbp+var_28]
0x18004b3a2  lea     rcx, [rbp+var_10]
0x18004b3a6  call    ??$?0GP6AXPEAX@Z$0A@@?$shared_ptr@G@std@@QEAA@PEAGP6AXPEAX@Z@Z; std::shared_ptr<ushort>::shared_ptr<ushort>(ushort *,void (*)(void *))
0x18004b3ab  mov     rdx, rax
0x18004b3ae  lea     rcx, [rbp+var_20]
0x18004b3b2  call    ??4?$shared_ptr@VCloudConnectionCookie@Halsey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(std::shared_ptr<Halsey::CloudConnectionCookie> &&)
0x18004b3b7  mov     rcx, [rbp+var_8]; this
0x18004b3bb  test    rcx, rcx
0x18004b3be  jz      short loc_18004B3C5
0x18004b3c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b3c5  lea     rdx, [rbp+var_28]
0x18004b3c9  lea     rcx, [rbp+var_30]; this
0x18004b3cd  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004b3d2  mov     ebx, eax
0x18004b3d4  test    eax, eax
0x18004b3d6  jns     short loc_18004B40B
0x18004b3d8  mov     rcx, [rbp+18h]; this
0x18004b3dc  mov     r9d, eax; char *
0x18004b3df  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004b3e6  mov     edx, 236h; void *
0x18004b3eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b3f0  nop
0x18004b3f1  lea     rcx, [rbp+string]
0x18004b3f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b3fa  nop
0x18004b3fb  mov     rcx, [rbp+var_20+8]; this
0x18004b3ff  test    rcx, rcx
0x18004b402  jz      short loc_18004B430
0x18004b404  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b409  jmp     short loc_18004B430
0x18004b40b  mov     rax, [rbp+var_30]
0x18004b40f  mov     [rbp+var_30], rsi
0x18004b413  mov     [rdi], rax
0x18004b416  lea     rcx, [rbp+string]
0x18004b41a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b41f  nop
0x18004b420  mov     rcx, [rbp+var_20+8]; this
0x18004b424  test    rcx, rcx
0x18004b427  jz      short loc_18004B42E
0x18004b429  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b42e  mov     ebx, esi
0x18004b430  jmp     loc_18004B554
0x18004b435  mov     [rbp+var_30], rsi
0x18004b439  mov     qword ptr [rbp+var_28], rsi
0x18004b43d  xorps   xmm0, xmm0
0x18004b440  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18004b445  mov     [rbp+string], rsi
0x18004b449  lea     rdx, [rbp+string]
0x18004b44d  call    ?GetActiveUserKeyFilter@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAV?$ComPtr@UISpAudioOrchestratorPolicyKeyFilter@@@WRL@6@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveUserKeyFilter(Microsoft::WRL::ComPtr<ISpAudioOrchestratorPolicyKeyFilter> &)
0x18004b452  mov     ebx, eax
0x18004b454  test    eax, eax
0x18004b456  jns     short loc_18004B45F
0x18004b458  mov     edx, 224h
0x18004b45d  jmp     short loc_18004B498
0x18004b45f  mov     rcx, [rbp+string]
0x18004b463  mov     rax, [rcx]
0x18004b466  lea     rdx, [rbp+var_28]
0x18004b46a  mov     qword ptr [rsp+60h+var_40], rdx; int
0x18004b46f  lea     r9, aCortanauserid; "CortanaUserId"
0x18004b476  lea     r8, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004b47d  mov     rdx, 0FFFFFFFF80000001h
0x18004b484  mov     rax, [rax+30h]
0x18004b488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b48d  mov     ebx, eax
0x18004b48f  test    eax, eax
0x18004b491  jns     short loc_18004B4BB
0x18004b493  mov     edx, 225h; void *
0x18004b498  mov     r9d, eax; char *
0x18004b49b  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004b4a2  mov     rcx, [rbp+18h]; this
0x18004b4a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b4ab  nop
0x18004b4ac  lea     rcx, [rbp+string]
0x18004b4b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b4b5  nop
0x18004b4b6  jmp     loc_18004B554
0x18004b4bb  mov     r8, cs:__imp_CoTaskMemFree
0x18004b4c2  mov     rdx, qword ptr [rbp+var_28]
0x18004b4c6  lea     rcx, [rbp+var_10]
0x18004b4ca  call    ??$?0GP6AXPEAX@Z$0A@@?$shared_ptr@G@std@@QEAA@PEAGP6AXPEAX@Z@Z; std::shared_ptr<ushort>::shared_ptr<ushort>(ushort *,void (*)(void *))
0x18004b4cf  mov     rdx, rax
0x18004b4d2  lea     rcx, [rbp+var_20]
0x18004b4d6  call    ??4?$shared_ptr@VCloudConnectionCookie@Halsey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(std::shared_ptr<Halsey::CloudConnectionCookie> &&)
0x18004b4db  mov     rcx, [rbp+var_8]; this
0x18004b4df  test    rcx, rcx
0x18004b4e2  jz      short loc_18004B4E9
0x18004b4e4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b4e9  lea     rdx, [rbp+var_28]
0x18004b4ed  lea     rcx, [rbp+var_30]; this
0x18004b4f1  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004b4f6  mov     ebx, eax
0x18004b4f8  test    eax, eax
0x18004b4fa  jns     short loc_18004B52F
0x18004b4fc  mov     rcx, [rbp+18h]; this
0x18004b500  mov     r9d, eax; char *
0x18004b503  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004b50a  mov     edx, 227h; void *
0x18004b50f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b514  nop
0x18004b515  lea     rcx, [rbp+string]
0x18004b519  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b51e  nop
0x18004b51f  mov     rcx, [rbp+var_20+8]; this
0x18004b523  test    rcx, rcx
0x18004b526  jz      short loc_18004B554
0x18004b528  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b52d  jmp     short loc_18004B554
0x18004b52f  mov     rax, [rbp+var_30]
0x18004b533  mov     [rbp+var_30], rsi
0x18004b537  mov     [rdi], rax
0x18004b53a  lea     rcx, [rbp+string]
0x18004b53e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b543  nop
0x18004b544  mov     rcx, [rbp+var_20+8]; this
0x18004b548  test    rcx, rcx
0x18004b54b  jz      short loc_18004B552
0x18004b54d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b552  mov     ebx, esi
0x18004b554  mov     rcx, [rbp+var_30]; this
0x18004b558  jmp     short loc_18004B5BB
0x18004b55a  call    ?ShouldCacheToken@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAA_NXZ; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::ShouldCacheToken(void)
0x18004b55f  mov     rcx, rbx; this
0x18004b562  test    al, al
0x18004b564  jz      loc_18004B5F5
0x18004b56a  call    ?PreFetchAuthenticationTokenAsync@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@QEAAJXZ; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::PreFetchAuthenticationTokenAsync(void)
0x18004b56f  mov     [rbp+string], rsi
0x18004b573  lea     rdx, [rbp+string]; struct Microsoft::WRL::Wrappers::HString *
0x18004b577  mov     rcx, rbx; this
0x18004b57a  call    ?GetLastAuthenticationToken@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAVHString@Wrappers@WRL@6@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetLastAuthenticationToken(Microsoft::WRL::Wrappers::HString &)
0x18004b57f  mov     ebx, eax
0x18004b581  test    eax, eax
0x18004b583  jns     short loc_18004B58C
0x18004b585  mov     edx, 212h
0x18004b58a  jmp     short loc_18004B5A4
0x18004b58c  mov     rdx, rdi; newString
0x18004b58f  mov     rcx, [rbp+string]; string
0x18004b593  call    cs:__imp_WindowsDuplicateString
0x18004b599  mov     ebx, eax
0x18004b59b  test    eax, eax
0x18004b59d  jns     short loc_18004B5C5
0x18004b59f  mov     edx, 213h; void *
0x18004b5a4  mov     r9d, eax; char *
0x18004b5a7  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004b5ae  mov     rcx, [rbp+18h]; this
0x18004b5b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b5b7  mov     rcx, [rbp+string]; string
0x18004b5bb  call    cs:__imp_WindowsDeleteString
0x18004b5c1  mov     eax, ebx
0x18004b5c3  jmp     short loc_18004B63E
0x18004b5c5  mov     [rbp+arg_8], 1
0x18004b5cc  xor     edx, edx; length
0x18004b5ce  mov     rcx, [rbp+string]; string
0x18004b5d2  call    cs:__imp_WindowsGetStringRawBuffer
0x18004b5d8  mov     qword ptr [rbp+var_28], rax
0x18004b5dc  lea     rdx, [rbp+arg_8]
0x18004b5e0  lea     rcx, [rbp+var_28]
0x18004b5e4  call    ??$GetIdentityPropertyValue@PEBGH@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@SAX$$QEAPEBG$$QEAH@Z; Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::GetIdentityPropertyValue<ushort const *,int>(ushort const * &&,int &&)
0x18004b5e9  mov     rcx, [rbp+string]; string
0x18004b5ed  call    cs:__imp_WindowsDeleteString
0x18004b5f3  jmp     short loc_18004B63C
0x18004b5f5  mov     rdx, rdi; HSTRING *
0x18004b5f8  call    ?GetAuthenticationToken@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@QEAAJPEAPEAUHSTRING__@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetAuthenticationToken(HSTRING__ * *)
0x18004b5fd  mov     ebx, eax
0x18004b5ff  test    eax, eax
0x18004b601  jns     short loc_18004B61D
0x18004b603  mov     edx, 218h; void *
0x18004b608  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18004b60f  mov     r9d, ebx; char *
  ... truncated ...
```
