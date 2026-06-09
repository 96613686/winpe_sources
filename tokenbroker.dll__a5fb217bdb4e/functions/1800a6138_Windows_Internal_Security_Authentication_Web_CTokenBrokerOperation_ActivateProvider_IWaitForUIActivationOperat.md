# Windows::Internal::Security::Authentication::Web::CTokenBrokerOperation::ActivateProvider(IWaitForUIActivationOperation * *)

- ea: `0x1800a6138`
- end: `0x1800a6724`
- name: `?ActivateProvider@CTokenBrokerOperation@Web@Authentication@Security@Internal@Windows@@AEAAJPEAPEAUIWaitForUIActivationOperation@@@Z`
- size: `1516`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::Web::CTokenBrokerOperation *__hidden this, struct IWaitForUIActivationOperation **)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ac658`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18002fbf0`
- `0x1800412e0`
- `0x18004f560`
- `0x18004fdbc`
- `0x180081df0`
- `0x180083a54`
- `0x18008e690`
- `0x18008fccc`
- `0x18009b954`
- `0x1800a2cb4`
- `0x1800a2d04`
- `0x1800a2df4`
- `0x1800a2e44`
- `0x1800a3864`
- `0x1800a3e98`
- `0x1800a6138`
- `0x1800ad188`
- `0x1800b3c18`
- `0x1800e3f2c`
- `0x1800ef38c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a63e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a66ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a63e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a66ab`
- `ext-ms-win-webtokenrequest-win32-l1-1-0!InvokePluginAsWin32` at `0x1800a64fd`
- `ext-ms-win-webtokenrequest-win32-l1-1-0!InvokePluginAsWin32` at `0x1800a6557`
- `ext-ms-win-webtokenrequest-win32-l1-1-0!InvokePluginAsWin32` at `0x1800a64fd`
- `ext-ms-win-webtokenrequest-win32-l1-1-0!InvokePluginAsWin32` at `0x1800a6557`

## string_xrefs

- `0x1800a61d6`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a623b`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a627d`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a62b8`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6331`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a636f`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a63ce`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a643b`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a649a`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6515`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a658c`: `Windows.Internal.PlatformExtensions.TokenBrokerExperience`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerOperation::ActivateProvider(
        Windows::Internal::Security::Authentication::Web::CallerContext **this,
        struct IWaitForUIActivationOperation **a2)
{
  bool IsCallerAppContainer; // bl
  HSTRING CallerPackageFamilyName; // rax
  int v6; // eax
  unsigned int ExtensionForProvider; // ebx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  int v15; // eax
  struct Windows::Internal::String *v16; // r8
  int AumId; // eax
  HSTRING v18; // rcx
  char v19; // si
  __int64 WindowSizeForWebAccountProviderOperation; // rax
  int v21; // eax
  char v22; // al
  HSTRING v23; // rdi
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  unsigned int v27; // ebx
  Windows::Internal::Security::Authentication::Web::CallerContext *v28; // r12
  __int64 v29; // rax
  int v30; // ebx
  bool v31; // zf
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(Windows::Internal::Security::Authentication::Web::CallerContext *, __int64, HSTRING, __int64); // r14
  __int64 (__fastcall *v34)(Windows::Internal::Security::Authentication::Web::CallerContext *, __int64, HSTRING, __int64); // r14
  struct IWaitForUIActivationOperation *v35; // rax
  int v37; // [rsp+28h] [rbp-A9h]
  int v38; // [rsp+28h] [rbp-A9h]
  __int64 v39; // [rsp+48h] [rbp-89h] BYREF
  __int64 v40; // [rsp+50h] [rbp-81h] BYREF
  __int64 v41; // [rsp+58h] [rbp-79h] BYREF
  __int64 v42; // [rsp+60h] [rbp-71h] BYREF
  struct IWaitForUIActivationOperation *v43; // [rsp+68h] [rbp-69h] BYREF
  __int64 v44; // [rsp+70h] [rbp-61h] BYREF
  __int64 v45; // [rsp+78h] [rbp-59h] BYREF
  HSTRING string; // [rsp+80h] [rbp-51h] BYREF
  __int64 v47; // [rsp+88h] [rbp-49h] BYREF
  int v48[2]; // [rsp+90h] [rbp-41h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  *a2 = 0;
  v47 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  IsCallerAppContainer = Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(this[5]);
  CallerPackageFamilyName = Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(
                              this[5],
                              0);
  LOBYTE(v37) = IsCallerAppContainer;
  v6 = Windows::Internal::Security::Authentication::TokenBroker::ConstructWebProviderTokenRequest(
         this[2],
         this[3],
         CallerPackageFamilyName);
  ExtensionForProvider = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v6,
      v37);
    goto LABEL_56;
  }
  v39 = 0;
  *(_QWORD *)v48 = 0;
  string = 0;
  v49 = v47;
  LODWORD(v44) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  v8 = Windows::Internal::ComTaskPool::MakeAndInitializeOnSharedSTAThread<Windows::Security::Authentication::Web::Provider::CWebAccountProviderActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,enum Windows::Security::Authentication::Web::Provider::WebAccountProviderOperationKind,Windows::Security::Authentication::Web::Provider::IWebProviderTokenRequest *,std::nullptr_t,std::nullptr_t>(
         (unsigned int)&v39,
         (unsigned int)&v44,
         (unsigned int)&v49,
         (unsigned int)&string,
         (__int64)v48);
  ExtensionForProvider = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x645,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v8,
      v38);
LABEL_5:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    goto LABEL_56;
  }
  v40 = 0;
  v9 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IWebAccountProviderActivatedEventArgs>(
         &v39,
         &v40);
  ExtensionForProvider = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v9,
      v38);
LABEL_8:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    goto LABEL_5;
  }
  v41 = 0;
  v10 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>(
          &v39,
          &v41);
  ExtensionForProvider = v10;
  if ( v10 < 0 )
  {
    v11 = 1611;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v10,
      v38);
LABEL_12:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    goto LABEL_8;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 56LL))(v41, *((_QWORD *)this[5] + 1));
  ExtensionForProvider = v10;
  if ( v10 < 0 )
  {
    v11 = 1612;
    goto LABEL_11;
  }
  v42 = 0;
  v12 = v40;
  v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v14 = v13(v12, &v42);
  ExtensionForProvider = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v14,
      v38);
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    goto LABEL_12;
  }
  v43 = 0;
  v15 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation>::As<IWaitForUIActivationOperation>(
          &v42,
          &v43);
  ExtensionForProvider = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x652,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v15,
      v38);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    goto LABEL_17;
  }
  if ( (unsigned int)dword_180175000 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &word_1801497A6,
      0,
      0);
  string = 0;
  AumId = Windows::Internal::Security::Authentication::Web::GetAumId(
            this[4],
            (struct Windows::Security::Credentials::IWebAccountProvider *)&string,
            v16);
  ExtensionForProvider = AumId;
  if ( AumId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x659,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)AumId,
      v38);
    goto LABEL_25;
  }
  v44 = 0;
  v48[0] = v47;
  LOBYTE(v48[1]) = 0;
  *(_WORD *)((char *)&v48[1] + 1) = *(_WORD *)((char *)&v47 + 5);
  HIBYTE(v48[1]) = HIBYTE(v47);
  ExtensionForProvider = Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionForProvider(
                           (__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))this[4],
                           (__int64)&v44,
                           *(__int64 *)v48);
  if ( (int)(ExtensionForProvider + 0x80000000) >= 0 && ExtensionForProvider != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x660,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)ExtensionForProvider,
      v38);
LABEL_30:
    std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(&v44);
LABEL_25:
    v18 = string;
    if ( !string )
      goto LABEL_20;
LABEL_26:
    WindowsDeleteString(v18);
    goto LABEL_20;
  }
  v19 = 0;
  if ( v44 )
  {
    WindowSizeForWebAccountProviderOperation = Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::GetWindowSizeForWebAccountProviderOperation(
                                                 v44,
                                                 v48,
                                                 0);
    v49 = *(_QWORD *)WindowSizeForWebAccountProviderOperation;
    v19 = *(_BYTE *)(WindowSizeForWebAccountProviderOperation + 8);
  }
  v45 = 0;
  v21 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<IInspectable>(&v39, &v45);
  ExtensionForProvider = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x668,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v21,
      v38);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    goto LABEL_30;
  }
  LogInvalidCallerWindow((HWND)*((unsigned int *)this + 12), this[5]);
  v22 = IsInvokePluginAsWin32Present();
  v23 = string;
  if ( v22 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::GetImpl'::`2'::impl) )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 8);
      v24 = InvokePluginAsWin32(v23, v45, *((int *)this + 12), this + 8);
      ExtensionForProvider = v24;
      if ( v24 < 0 )
      {
        v25 = 1654;
LABEL_39:
        v26 = (unsigned int)v24;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)v26,
          v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(&v44);
        if ( !v23 )
          goto LABEL_20;
        v18 = v23;
        goto LABEL_26;
      }
    }
    else
    {
      v24 = InvokePluginAsWin32(0, v45, 0, 0);
      ExtensionForProvider = v24;
      if ( v24 < 0 )
      {
        v25 = 1658;
        goto LABEL_39;
      }
    }
  }
  else
  {
    v27 = *((_DWORD *)this + 12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 8);
    v51 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.PlatformExtensions.TokenBrokerExperience",
      0x3Au,
      0x39u);
    v24 = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract>(
            v51,
            this + 8,
            v27);
    ExtensionForProvider = v24;
    if ( v24 < 0 )
    {
      v25 = 1666;
      goto LABEL_39;
    }
    v28 = this[8];
    if ( !v28 )
    {
      ExtensionForProvider = -2147467263;
      v26 = 2147500033LL;
      v25 = 1667;
      goto LABEL_40;
    }
    v29 = *(_QWORD *)v28;
    v30 = *((_DWORD *)this + 12);
    v51 = 0;
    v31 = v19 == 0;
    v32 = v45;
    if ( v31 )
    {
      v34 = *(__int64 (__fastcall **)(Windows::Internal::Security::Authentication::Web::CallerContext *, __int64, HSTRING, __int64))(v29 + 48);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.WebAccountProvider",
        0x1Bu,
        0x1Au);
      v38 = v30;
      v24 = v34(v28, v51, v23, v32);
      ExtensionForProvider = v24;
      if ( v24 < 0 )
      {
        v25 = 1677;
        goto LABEL_39;
      }
    }
    else
    {
      v33 = *(__int64 (__fastcall **)(Windows::Internal::Security::Authentication::Web::CallerContext *, __int64, HSTRING, __int64))(v29 + 56);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.WebAccountProvider",
        0x1Bu,
        0x1Au);
      v38 = v30;
      v24 = v33(v28, v51, v23, v32);
      ExtensionForProvider = v24;
      if ( v24 < 0 )
      {
        v25 = 1672;
        goto LABEL_39;
      }
    }
  }
  v35 = v43;
  v43 = 0;
  *a2 = v35;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(&v44);
  if ( v23 )
    WindowsDeleteString(v23);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  ExtensionForProvider = 0;
LABEL_56:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  return ExtensionForProvider;
}

```

## disassembly

```asm
0x1800a6138  mov     rax, rsp
0x1800a613b  mov     [rax+18h], rbx
0x1800a613f  push    rbp
0x1800a6140  push    rsi
0x1800a6141  push    rdi
0x1800a6142  push    r12
0x1800a6144  push    r13
0x1800a6146  push    r14
0x1800a6148  push    r15
0x1800a614a  lea     rbp, [rax-5Fh]
0x1800a614e  sub     rsp, 0F0h
0x1800a6155  movaps  xmmword ptr [rax-48h], xmm6
0x1800a6159  movaps  xmmword ptr [rax-58h], xmm7
0x1800a615d  mov     rax, cs:__security_cookie
0x1800a6164  xor     rax, rsp
0x1800a6167  mov     [rbp+57h+var_58], rax
0x1800a616b  mov     r13, rdx
0x1800a616e  mov     r15, rcx
0x1800a6171  xor     r14d, r14d
0x1800a6174  mov     [rdx], r14
0x1800a6177  mov     [rbp+57h+var_A0], r14
0x1800a617b  lea     rcx, [rbp+57h+var_A0]
0x1800a617f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6184  mov     rcx, [r15+28h]; this
0x1800a6188  mov     rdi, [rcx+38h]
0x1800a618c  mov     rsi, [r15+38h]
0x1800a6190  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x1800a6195  mov     bl, al
0x1800a6197  xor     edx, edx; bool
0x1800a6199  mov     rcx, [r15+28h]; this
0x1800a619d  call    ?GetCallerPackageFamilyName@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAPEAUHSTRING__@@_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(bool)
0x1800a61a2  lea     rcx, [rbp+57h+var_A0]
0x1800a61a6  mov     [rsp+120h+var_E8], rcx
0x1800a61ab  mov     [rsp+120h+var_F0], rdi
0x1800a61b0  mov     [rsp+120h+var_F8], rsi
0x1800a61b5  mov     byte ptr [rsp+120h+var_100], bl; int
0x1800a61b9  mov     r8, rax
0x1800a61bc  mov     rdx, [r15+18h]
0x1800a61c0  mov     rcx, [r15+10h]
0x1800a61c4  call    ?ConstructWebProviderTokenRequest@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebTokenRequest@Core@Web@235@PEAU?$IVector@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@PEAUHSTRING__@@_N3_K2PEAPEAUIWebProviderTokenRequest@Provider@8235@@Z; Windows::Internal::Security::Authentication::TokenBroker::ConstructWebProviderTokenRequest(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVector<Windows::Security::Credentials::WebAccount *> *,HSTRING__ *,bool,bool,unsigned __int64,HSTRING__ *,Windows::Security::Authentication::Web::Provider::IWebProviderTokenRequest * *)
0x1800a61c9  mov     ebx, eax
0x1800a61cb  test    eax, eax
0x1800a61cd  jns     short loc_1800A61EC
0x1800a61cf  mov     rcx, [rbp+5Fh]; this
0x1800a61d3  mov     r9d, eax; char *
0x1800a61d6  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a61dd  mov     edx, 63Dh; void *
0x1800a61e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a61e7  jmp     loc_1800A66E8
0x1800a61ec  mov     [rsp+120h+var_E0], r14
0x1800a61f1  mov     qword ptr [rbp+57h+var_98], r14
0x1800a61f5  mov     [rbp+57h+string], r14
0x1800a61f9  mov     rax, [rbp+57h+var_A0]
0x1800a61fd  mov     [rbp+57h+var_88], rax
0x1800a6201  mov     dword ptr [rbp+57h+var_B8], r14d
0x1800a6205  lea     rcx, [rsp+120h+var_E0]
0x1800a620a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a620f  lea     rax, [rbp+57h+var_98]
0x1800a6213  mov     qword ptr [rsp+120h+var_100], rax; int
0x1800a6218  lea     r9, [rbp+57h+string]
0x1800a621c  lea     r8, [rbp+57h+var_88]
0x1800a6220  lea     rdx, [rbp+57h+var_B8]
0x1800a6224  lea     rcx, [rsp+120h+var_E0]
0x1800a6229  call    ??$MakeAndInitializeOnSharedSTAThread@VCWebAccountProviderActivatedEventArgs@Provider@Web@Authentication@Security@Windows@@UIActivatedEventArgs@Activation@ApplicationModel@6@W4WebAccountProviderOperationKind@23456@PEAUIWebProviderTokenRequest@23456@$$T$$T@ComTaskPool@Internal@Windows@@SAJPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@$$QEAW4WebAccountProviderOperationKind@Provider@Web@Authentication@Security@2@$$QEAPEAUIWebProviderTokenRequest@789Security@2@$$QEA$$T3@Z
0x1800a622e  mov     ebx, eax
0x1800a6230  test    eax, eax
0x1800a6232  jns     short loc_1800A625C
0x1800a6234  mov     rcx, [rbp+5Fh]; this
0x1800a6238  mov     r9d, eax; char *
0x1800a623b  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6242  mov     edx, 645h; void *
0x1800a6247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a624c  nop
0x1800a624d  lea     rcx, [rsp+120h+var_E0]
0x1800a6252  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6257  jmp     loc_1800A66E8
0x1800a625c  mov     [rsp+120h+var_D8], r14
0x1800a6261  lea     rdx, [rsp+120h+var_D8]
0x1800a6266  lea     rcx, [rsp+120h+var_E0]
0x1800a626b  call    ??$As@UIWebAccountProviderActivatedEventArgs@Activation@ApplicationModel@Windows@@@?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProviderActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IWebAccountProviderActivatedEventArgs>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IWebAccountProviderActivatedEventArgs>>)
0x1800a6270  mov     ebx, eax
0x1800a6272  test    eax, eax
0x1800a6274  jns     short loc_1800A629B
0x1800a6276  mov     rcx, [rbp+5Fh]; this
0x1800a627a  mov     r9d, eax; char *
0x1800a627d  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6284  mov     edx, 648h; void *
0x1800a6289  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a628e  nop
0x1800a628f  lea     rcx, [rsp+120h+var_D8]
0x1800a6294  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6299  jmp     short loc_1800A624D
0x1800a629b  mov     [rbp+57h+var_D0], r14
0x1800a629f  lea     rdx, [rbp+57h+var_D0]
0x1800a62a3  lea     rcx, [rsp+120h+var_E0]
0x1800a62a8  call    ??$As@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>>)
0x1800a62ad  mov     ebx, eax
0x1800a62af  test    eax, eax
0x1800a62b1  jns     short loc_1800A62D7
0x1800a62b3  mov     edx, 64Bh; void *
0x1800a62b8  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a62bf  mov     r9d, eax; char *
0x1800a62c2  mov     rcx, [rbp+5Fh]; this
0x1800a62c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a62cb  nop
0x1800a62cc  lea     rcx, [rbp+57h+var_D0]
0x1800a62d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a62d5  jmp     short loc_1800A628F
0x1800a62d7  mov     rcx, [rbp+57h+var_D0]
0x1800a62db  mov     rax, [rcx]
0x1800a62de  mov     rdx, [r15+28h]
0x1800a62e2  mov     rdx, [rdx+8]
0x1800a62e6  mov     rax, [rax+38h]
0x1800a62ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a62ef  mov     ebx, eax
0x1800a62f1  test    eax, eax
0x1800a62f3  jns     short loc_1800A62FC
0x1800a62f5  mov     edx, 64Ch
0x1800a62fa  jmp     short loc_1800A62B8
0x1800a62fc  mov     [rbp+57h+var_C8], r14
0x1800a6300  mov     rdi, [rsp+120h+var_D8]
0x1800a6305  mov     rax, [rdi]
0x1800a6308  mov     rbx, [rax+30h]
0x1800a630c  lea     rcx, [rbp+57h+var_C8]
0x1800a6310  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6315  lea     rdx, [rbp+57h+var_C8]
0x1800a6319  mov     rcx, rdi
0x1800a631c  mov     rax, rbx
0x1800a631f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6324  mov     ebx, eax
0x1800a6326  test    eax, eax
0x1800a6328  jns     short loc_1800A6351
0x1800a632a  mov     rcx, [rbp+5Fh]; this
0x1800a632e  mov     r9d, eax; char *
0x1800a6331  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6338  mov     edx, 64Fh; void *
0x1800a633d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6342  nop
0x1800a6343  lea     rcx, [rbp+57h+var_C8]
0x1800a6347  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a634c  jmp     loc_1800A62CC
0x1800a6351  mov     [rbp+57h+var_C0], r14
0x1800a6355  lea     rdx, [rbp+57h+var_C0]
0x1800a6359  lea     rcx, [rbp+57h+var_C8]
0x1800a635d  call    ??$As@UIWaitForUIActivationOperation@@@?$ComPtr@UIWebAccountProviderOperation@Provider@Web@Authentication@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWaitForUIActivationOperation@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Provider::IWebAccountProviderOperation>::As<IWaitForUIActivationOperation>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWaitForUIActivationOperation>>)
0x1800a6362  mov     ebx, eax
0x1800a6364  test    eax, eax
0x1800a6366  jns     short loc_1800A638C
0x1800a6368  mov     rcx, [rbp+5Fh]; this
0x1800a636c  mov     r9d, eax; char *
0x1800a636f  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6376  mov     edx, 652h; void *
0x1800a637b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6380  nop
0x1800a6381  lea     rcx, [rbp+57h+var_C0]
0x1800a6385  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a638a  jmp     short loc_1800A6343
0x1800a638c  mov     eax, cs:dword_180175000
0x1800a6392  cmp     eax, 5
0x1800a6395  jbe     short loc_1800A63B0
0x1800a6397  xor     r9d, r9d
0x1800a639a  xor     r8d, r8d
0x1800a639d  lea     rdx, word_1801497A6
0x1800a63a4  lea     rcx, dword_180175000
0x1800a63ab  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800a63b0  mov     [rbp+57h+string], r14
0x1800a63b4  lea     rdx, [rbp+57h+string]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800a63b8  mov     rcx, [r15+20h]; this
0x1800a63bc  call    ?GetAumId@Web@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@35@AEAVString@45@@Z; Windows::Internal::Security::Authentication::Web::GetAumId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &)
0x1800a63c1  mov     ebx, eax
0x1800a63c3  test    eax, eax
0x1800a63c5  jns     short loc_1800A63F1
0x1800a63c7  mov     rcx, [rbp+5Fh]; this
0x1800a63cb  mov     r9d, eax; char *
0x1800a63ce  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a63d5  mov     edx, 659h; void *
0x1800a63da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a63df  nop
0x1800a63e0  mov     rcx, [rbp+57h+string]; string
0x1800a63e4  test    rcx, rcx
0x1800a63e7  jz      short loc_1800A6381
0x1800a63e9  call    cs:__imp_WindowsDeleteString
0x1800a63ef  jmp     short loc_1800A6381
0x1800a63f1  mov     [rbp+57h+var_B8], r14
0x1800a63f5  mov     eax, dword ptr [rbp+57h+var_A0]
0x1800a63f8  mov     [rbp+57h+var_98], eax
0x1800a63fb  mov     byte ptr [rbp+57h+var_98+4], r14b
0x1800a63ff  movzx   eax, word ptr [rbp+57h+var_A0+5]
0x1800a6403  mov     word ptr [rbp+57h+var_98+5], ax
0x1800a6407  mov     al, byte ptr [rbp+57h+var_A0+7]
0x1800a640a  mov     byte ptr [rbp+57h+var_98+7], al
0x1800a640d  mov     r8, qword ptr [rbp+57h+var_98]
0x1800a6411  lea     rdx, [rbp+57h+var_B8]
0x1800a6415  mov     rcx, [r15+20h]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800a6419  call    ?FindExtensionForProvider@SystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAV?$unique_ptr@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@V?$optional@W4ExtensionType@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@Z; Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionForProvider(Windows::Security::Credentials::IWebAccountProvider *,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension> &,std::optional<Windows::Internal::Security::Authentication::TokenBroker::ExtensionType>)
0x1800a641e  mov     ebx, eax
0x1800a6420  mov     eax, 80000000h
0x1800a6425  lea     ecx, [rbx+rax]
0x1800a6428  test    eax, ecx
0x1800a642a  jnz     short loc_1800A6458
0x1800a642c  cmp     ebx, 80070002h
0x1800a6432  jz      short loc_1800A6458
0x1800a6434  mov     rcx, [rbp+5Fh]; this
0x1800a6438  mov     r9d, ebx; char *
0x1800a643b  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6442  mov     edx, 660h; void *
0x1800a6447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a644c  nop
0x1800a644d  lea     rcx, [rbp+57h+var_B8]
0x1800a6451  call    ??1?$unique_ptr@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(void)
0x1800a6456  jmp     short loc_1800A63E0
0x1800a6458  mov     sil, r14b
0x1800a645b  mov     rcx, [rbp+57h+var_B8]
0x1800a645f  test    rcx, rcx
0x1800a6462  jz      short loc_1800A647B
0x1800a6464  xor     r8d, r8d
0x1800a6467  lea     rdx, [rbp+57h+var_98]
0x1800a646b  call    ?GetWindowSizeForWebAccountProviderOperation@SystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@QEAA?AV?$optional@USize@Foundation@Windows@@@std@@W4WebAccountProviderOperationKind@Provider@Web@346@@Z; Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::GetWindowSizeForWebAccountProviderOperation(Windows::Security::Authentication::Web::Provider::WebAccountProviderOperationKind)
0x1800a6470  mov     rcx, [rax]
0x1800a6473  mov     [rbp+57h+var_88], rcx
0x1800a6477  mov     sil, [rax+8]
0x1800a647b  mov     [rbp+57h+var_B0], r14
0x1800a647f  lea     rdx, [rbp+57h+var_B0]
0x1800a6483  lea     rcx, [rsp+120h+var_E0]
0x1800a6488  call    ??$As@UIInspectable@@@?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<IInspectable>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>)
0x1800a648d  mov     ebx, eax
0x1800a648f  test    eax, eax
0x1800a6491  jns     short loc_1800A64B7
0x1800a6493  mov     rcx, [rbp+5Fh]; this
0x1800a6497  mov     r9d, eax; char *
0x1800a649a  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a64a1  mov     edx, 668h; void *
0x1800a64a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a64ab  nop
0x1800a64ac  lea     rcx, [rbp+57h+var_B0]
0x1800a64b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a64b5  jmp     short loc_1800A644D
0x1800a64b7  mov     ecx, [r15+30h]; hWnd
0x1800a64bb  mov     rdx, [r15+28h]; this
0x1800a64bf  call    ?LogInvalidCallerWindow@@YAXPEAUHWND__@@PEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; LogInvalidCallerWindow(HWND__ *,Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800a64c4  call    IsInvokePluginAsWin32Present
0x1800a64c9  mov     rdi, [rbp+57h+string]
0x1800a64cd  test    al, al
0x1800a64cf  jz      loc_1800A656E
0x1800a64d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WAMPluginWin32Activation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WAMPluginWin32Activation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WAMPluginWin32Activation> `wil::Feature<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::GetImpl(void)'::`2'::impl
0x1800a64dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WAMPluginWin32Activation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::__private_IsEnabled(void)
0x1800a64e1  test    al, al
0x1800a64e3  jz      short loc_1800A654B
0x1800a64e5  lea     rcx, [r15+40h]
0x1800a64e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a64ee  movsxd  r8, dword ptr [r15+30h]
0x1800a64f2  lea     r9, [r15+40h]
0x1800a64f6  mov     rdx, [rbp+57h+var_B0]
0x1800a64fa  mov     rcx, rdi
0x1800a64fd  call    cs:__imp_InvokePluginAsWin32
0x1800a6503  mov     ebx, eax
0x1800a6505  test    eax, eax
0x1800a6507  jns     loc_1800A6683
0x1800a650d  mov     edx, 676h; void *
0x1800a6512  mov     r9d, eax; char *
0x1800a6515  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a651c  mov     rcx, [rbp+5Fh]; this
0x1800a6520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6525  nop
0x1800a6526  lea     rcx, [rbp+57h+var_B0]
0x1800a652a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a652f  nop
0x1800a6530  lea     rcx, [rbp+57h+var_B8]
0x1800a6534  call    ??1?$unique_ptr@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(void)
0x1800a6539  nop
0x1800a653a  test    rdi, rdi
0x1800a653d  jz      loc_1800A6381
0x1800a6543  mov     rcx, rdi
0x1800a6546  jmp     loc_1800A63E9
0x1800a654b  xor     r9d, r9d
0x1800a654e  xor     r8d, r8d
0x1800a6551  mov     rdx, [rbp+57h+var_B0]
0x1800a6555  xor     ecx, ecx
0x1800a6557  call    cs:__imp_InvokePluginAsWin32
0x1800a655d  mov     ebx, eax
0x1800a655f  test    eax, eax
0x1800a6561  jns     loc_1800A6683
0x1800a6567  mov     edx, 67Ah
0x1800a656c  jmp     short loc_1800A6512
0x1800a656e  mov     ebx, [r15+30h]
0x1800a6572  lea     r12, [r15+40h]
0x1800a6576  mov     rcx, r12
0x1800a6579  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a657e  mov     [rbp+57h+var_60], r14
0x1800a6582  mov     r9d, 39h ; '9'; unsigned int
0x1800a6588  lea     r8d, [r9+1]; unsigned int
0x1800a658c  lea     rdx, aWindowsInterna_36; "Windows.Internal.PlatformExtensions.Tok"...
0x1800a6593  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a6597  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a659c  mov     r8d, ebx
0x1800a659f  mov     rdx, r12
0x1800a65a2  mov     rcx, [rbp+57h+var_60]
0x1800a65a6  call    ??$TryActivateContractExtension@UITokenBrokerExperienceContract@PlatformExtensions@Internal@Windows@@@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAPEAUITokenBrokerExperienceContract@012@UWindowId@WindowManagement@ApplicationModel@12@@Z; Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract>(HSTRING__ *,Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x1800a65ab  mov     ebx, eax
0x1800a65ad  test    eax, eax
  ... truncated ...
```
