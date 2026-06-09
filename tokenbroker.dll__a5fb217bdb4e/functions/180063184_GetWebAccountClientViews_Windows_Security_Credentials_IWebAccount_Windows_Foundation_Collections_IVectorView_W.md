# GetWebAccountClientViews(Windows::Security::Credentials::IWebAccount *,Windows::Foundation::Collections::IVectorView<Windows::Security::Authentication::Web::Provider::WebAccountClientView *> * *)

- ea: `0x180063184`
- end: `0x18006347c`
- name: `?GetWebAccountClientViews@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAPEAU?$IVectorView@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@@Collections@Foundation@4@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180063170`
- `0x1800e3000`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180030d30`
- `0x180031088`
- `0x180035880`
- `0x1800372d0`
- `0x180040c94`
- `0x18004c98c`
- `0x18004fdbc`
- `0x180051dd0`
- `0x180052f30`
- `0x180053718`
- `0x18005817c`
- `0x180063184`
- `0x1800729e0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800632fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800633af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800633d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800632fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800633af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800633d3`

## string_xrefs

- `0x1800631e9`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180063222`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180063395`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x1800633f8`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180063412`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18006342c`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetWebAccountClientViews(struct Windows::Security::Credentials::IWebAccount *a1, __int64 a2)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  HSTRING v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  HSTRING *v10; // rdi
  int v11; // eax
  int Uri; // eax
  int v13; // eax
  int StringUri; // eax
  __int64 v15; // rdx
  struct Windows::Foundation::IUriRuntimeClass *v17; // [rsp+20h] [rbp-69h] BYREF
  __int64 v18; // [rsp+28h] [rbp-61h] BYREF
  HSTRING string; // [rsp+30h] [rbp-59h] BYREF
  __int64 v20; // [rsp+38h] [rbp-51h] BYREF
  HSTRING *v21; // [rsp+40h] [rbp-49h] BYREF
  std::_Ref_count_base *v22; // [rsp+48h] [rbp-41h]
  __int64 i; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v24; // [rsp+58h] [rbp-31h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v25; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v26[24]; // [rsp+70h] [rbp-19h] BYREF
  __int64 *v27; // [rsp+88h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  BOOL v29; // [rsp+100h] [rbp+77h] BYREF
  HSTRING v30; // [rsp+108h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      byte_180157FD1,
      0,
      0);
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,0>>(
         v4,
         &v20);
  v6 = v5;
  if ( v5 >= 0 )
  {
    AccountSystemOnlyInfo::AccountSystemOnlyInfo((AccountSystemOnlyInfo *)v26);
    v8 = AccountSystemOnlyInfo::InitializeFromAccount((AccountSystemOnlyInfo *)v26, a1, v7);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v9 = *v27;
      for ( i = *v27; ; v9 = i )
      {
        if ( *(_BYTE *)(v9 + 25) )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 64LL))(v20, a2);
          goto LABEL_35;
        }
        std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(
          &v21,
          v9 + 64);
        v30 = 0;
        v10 = v21;
        v11 = Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::InitializeFromPfn(
                (Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri *)&v30,
                *v21);
        v6 = v11;
        if ( v11 < 0 )
          break;
        v17 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        Uri = Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::GetUri(
                (Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri *)&v30,
                &v17);
        v6 = Uri;
        if ( Uri < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD3F,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
            (const char *)(unsigned int)Uri,
            (int)v17);
          goto LABEL_25;
        }
        v18 = 0;
        v24 = v10[2];
        v25 = v17;
        v29 = *((_DWORD *)v10 + 2) == 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
        v13 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::Provider::CWebAccountClientView,Windows::Security::Authentication::Web::Provider::CWebAccountClientView,enum Windows::Security::Authentication::Web::Provider::WebAccountClientViewType,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *>(
                &v18,
                &v29,
                &v25,
                &v24);
        v6 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD49,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
            (const char *)(unsigned int)v13,
            (int)v17);
          goto LABEL_24;
        }
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        StringUri = Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::GetStringUri(
                      (Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri *)&v30,
                      &string);
        v6 = StringUri;
        if ( StringUri < 0 )
        {
          v15 = 3404;
          goto LABEL_22;
        }
        StringUri = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 104LL))(v20, v18);
        v6 = StringUri;
        if ( StringUri < 0 )
        {
          v15 = 3406;
LABEL_22:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
            (const char *)(unsigned int)StringUri,
            (int)v17);
          if ( string )
            WindowsDeleteString(string);
LABEL_24:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
LABEL_25:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
          goto LABEL_26;
        }
        if ( string )
          WindowsDeleteString(string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        if ( v30 )
          WindowsDeleteString(v30);
        if ( v22 )
          std::_Ref_count_base::_Decref(v22);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>>>,std::_Iterator_base0>::operator++(&i);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD3D,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v11,
        (int)v17);
LABEL_26:
      if ( v30 )
        WindowsDeleteString(v30);
      if ( v22 )
        std::_Ref_count_base::_Decref(v22);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD33,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v8,
        (int)v17);
    }
LABEL_35:
    AccountSystemOnlyInfo::~AccountSystemOnlyInfo((AccountSystemOnlyInfo *)v26);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD30,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v5,
      (int)v17);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return v6;
}

```

## disassembly

```asm
0x180063184  mov     [rsp-8+arg_0], rbx
0x180063189  push    rbp
0x18006318a  push    rsi
0x18006318b  push    rdi
0x18006318c  lea     rbp, [rsp-47h]
0x180063191  sub     rsp, 0D0h
0x180063198  mov     rsi, rdx
0x18006319b  mov     rdi, rcx
0x18006319e  mov     eax, cs:dword_180175000
0x1800631a4  cmp     eax, 4
0x1800631a7  jbe     short loc_1800631C2
0x1800631a9  xor     r9d, r9d
0x1800631ac  xor     r8d, r8d
0x1800631af  lea     rdx, byte_180157FD1
0x1800631b6  lea     rcx, dword_180175000
0x1800631bd  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800631c2  mov     [rbp+57h+var_A8], 0
0x1800631ca  lea     rcx, [rbp+57h+var_A8]
0x1800631ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800631d3  lea     rdx, [rbp+57h+var_A8]
0x1800631d7  call    ??$CreateExternalObjectVector@VWebAccountClientView@Provider@Web@Authentication@Security@Windows@@V?$AgileVector@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@@89Foundation@6@$0A@@Internal@Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@@89Foundation@6@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,0> * *)
0x1800631dc  mov     ebx, eax
0x1800631de  test    eax, eax
0x1800631e0  jns     short loc_1800631FF
0x1800631e2  mov     rcx, [rbp+5Fh]; this
0x1800631e6  mov     r9d, eax; char *
0x1800631e9  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800631f0  mov     edx, 0D30h; void *
0x1800631f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800631fa  jmp     loc_18006345E
0x1800631ff  lea     rcx, [rbp+57h+var_70]; this
0x180063203  call    ??0AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::AccountSystemOnlyInfo(void)
0x180063208  nop
0x180063209  mov     rdx, rdi; struct Windows::Security::Credentials::IWebAccount *
0x18006320c  lea     rcx, [rbp+57h+var_70]; this
0x180063210  call    ?InitializeFromAccount@AccountSystemOnlyInfo@@QEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEAUHSTRING__@@@Z; AccountSystemOnlyInfo::InitializeFromAccount(Windows::Security::Credentials::IWebAccount *,HSTRING__ *)
0x180063215  mov     ebx, eax
0x180063217  test    eax, eax
0x180063219  jns     short loc_180063238
0x18006321b  mov     rcx, [rbp+5Fh]; this
0x18006321f  mov     r9d, eax; char *
0x180063222  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180063229  mov     edx, 0D33h; void *
0x18006322e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063233  jmp     loc_180063454
0x180063238  mov     rdx, [rbp+57h+var_58]
0x18006323c  mov     rdx, [rdx]
0x18006323f  mov     [rbp+57h+var_90], rdx
0x180063243  cmp     byte ptr [rdx+19h], 0
0x180063247  jnz     loc_18006343F
0x18006324d  add     rdx, 40h ; '@'
0x180063251  lea     rcx, [rbp+57h+var_A0]
0x180063255  call    ??0?$shared_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext> const &)
0x18006325a  nop
0x18006325b  mov     [rbp+57h+arg_18], 0
0x180063263  mov     rdi, [rbp+57h+var_A0]
0x180063267  mov     rdx, [rdi]; HSTRING
0x18006326a  lea     rcx, [rbp+57h+arg_18]; this
0x18006326e  call    ?InitializeFromPfn@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::InitializeFromPfn(HSTRING__ *)
0x180063273  mov     ebx, eax
0x180063275  test    eax, eax
0x180063277  js      loc_180063425
0x18006327d  mov     [rbp+57h+var_C0], 0
0x180063285  lea     rcx, [rbp+57h+var_C0]
0x180063289  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006328e  lea     rdx, [rbp+57h+var_C0]; struct Windows::Foundation::IUriRuntimeClass **
0x180063292  lea     rcx, [rbp+57h+arg_18]; this
0x180063296  call    ?GetUri@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@QEBAJPEAPEAUIUriRuntimeClass@Foundation@6@@Z; Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::GetUri(Windows::Foundation::IUriRuntimeClass * *)
0x18006329b  mov     ebx, eax
0x18006329d  test    eax, eax
0x18006329f  js      loc_18006340B
0x1800632a5  mov     [rbp+57h+var_B8], 0
0x1800632ad  mov     rax, [rdi+10h]
0x1800632b1  mov     [rbp+57h+var_88], rax
0x1800632b5  mov     rax, [rbp+57h+var_C0]
0x1800632b9  mov     [rbp+57h+var_80], rax
0x1800632bd  xor     eax, eax
0x1800632bf  cmp     [rdi+8], eax
0x1800632c2  setz    al
0x1800632c5  mov     [rbp+57h+arg_10], eax
0x1800632c8  lea     rcx, [rbp+57h+var_B8]
0x1800632cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800632d1  lea     r9, [rbp+57h+var_88]
0x1800632d5  lea     r8, [rbp+57h+var_80]
0x1800632d9  lea     rdx, [rbp+57h+arg_10]
0x1800632dd  lea     rcx, [rbp+57h+var_B8]
0x1800632e1  call    ??$MakeAndInitialize@VCWebAccountClientView@Provider@Web@Authentication@Security@Windows@@V123456@W4WebAccountClientViewType@23456@PEAUIUriRuntimeClass@Foundation@6@PEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAVCWebAccountClientView@Provider@Web@Authentication@Security@Windows@@$$QEAW4WebAccountClientViewType@45678@$$QEAPEAUIUriRuntimeClass@Foundation@8@$$QEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::Provider::CWebAccountClientView,Windows::Security::Authentication::Web::Provider::CWebAccountClientView,Windows::Security::Authentication::Web::Provider::WebAccountClientViewType,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *>(Windows::Security::Authentication::Web::Provider::CWebAccountClientView * *,Windows::Security::Authentication::Web::Provider::WebAccountClientViewType &&,Windows::Foundation::IUriRuntimeClass * &&,HSTRING__ * &&)
0x1800632e6  mov     ebx, eax
0x1800632e8  test    eax, eax
0x1800632ea  js      loc_1800633F1
0x1800632f0  mov     [rbp+57h+string], 0
0x1800632f8  xor     ecx, ecx; string
0x1800632fa  call    cs:__imp_WindowsDeleteString
0x180063300  mov     [rbp+57h+string], 0
0x180063308  lea     rdx, [rbp+57h+string]; HSTRING *
0x18006330c  lea     rcx, [rbp+57h+arg_18]; this
0x180063310  call    ?GetStringUri@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@QEBAJPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::GetStringUri(HSTRING__ * *)
0x180063315  mov     ebx, eax
0x180063317  test    eax, eax
0x180063319  js      loc_1800633EA
0x18006331f  mov     rcx, [rbp+57h+var_A8]
0x180063323  mov     rax, [rcx]
0x180063326  mov     rdx, [rbp+57h+var_B8]
0x18006332a  mov     rax, [rax+68h]
0x18006332e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063333  mov     ebx, eax
0x180063335  test    eax, eax
0x180063337  js      short loc_18006338D
0x180063339  mov     rcx, [rbp+57h+string]; string
0x18006333d  test    rcx, rcx
0x180063340  jz      short loc_180063349
0x180063342  call    cs:__imp_WindowsDeleteString
0x180063348  nop
0x180063349  lea     rcx, [rbp+57h+var_B8]
0x18006334d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063352  nop
0x180063353  lea     rcx, [rbp+57h+var_C0]
0x180063357  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006335c  nop
0x18006335d  mov     rcx, [rbp+57h+arg_18]; string
0x180063361  test    rcx, rcx
0x180063364  jz      short loc_18006336D
0x180063366  call    cs:__imp_WindowsDeleteString
0x18006336c  nop
0x18006336d  mov     rcx, [rbp+57h+var_98]; this
0x180063371  test    rcx, rcx
0x180063374  jz      short loc_18006337B
0x180063376  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006337b  lea     rcx, [rbp+57h+var_90]
0x18006337f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPerAppAccountData@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<PerAppAccountData>>>>,std::_Iterator_base0>::operator++(void)
0x180063384  mov     rdx, [rbp+57h+var_90]
0x180063388  jmp     loc_180063243
0x18006338d  mov     edx, 0D4Eh; void *
0x180063392  mov     r9d, eax; char *
0x180063395  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18006339c  mov     rcx, [rbp+5Fh]; this
0x1800633a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800633a5  nop
0x1800633a6  mov     rcx, [rbp+57h+string]; string
0x1800633aa  test    rcx, rcx
0x1800633ad  jz      short loc_1800633B6
0x1800633af  call    cs:__imp_WindowsDeleteString
0x1800633b5  nop
0x1800633b6  lea     rcx, [rbp+57h+var_B8]
0x1800633ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800633bf  nop
0x1800633c0  lea     rcx, [rbp+57h+var_C0]
0x1800633c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800633c9  nop
0x1800633ca  mov     rcx, [rbp+57h+arg_18]; string
0x1800633ce  test    rcx, rcx
0x1800633d1  jz      short loc_1800633DA
0x1800633d3  call    cs:__imp_WindowsDeleteString
0x1800633d9  nop
0x1800633da  mov     rcx, [rbp+57h+var_98]; this
0x1800633de  test    rcx, rcx
0x1800633e1  jz      short loc_180063454
0x1800633e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800633e8  jmp     short loc_180063454
0x1800633ea  mov     edx, 0D4Ch
0x1800633ef  jmp     short loc_180063392
0x1800633f1  mov     rcx, [rbp+5Fh]; this
0x1800633f5  mov     r9d, eax; char *
0x1800633f8  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800633ff  mov     edx, 0D49h; void *
0x180063404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063409  jmp     short loc_1800633B6
0x18006340b  mov     rcx, [rbp+5Fh]; this
0x18006340f  mov     r9d, eax; char *
0x180063412  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180063419  mov     edx, 0D3Fh; void *
0x18006341e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063423  jmp     short loc_1800633C0
0x180063425  mov     rcx, [rbp+5Fh]; this
0x180063429  mov     r9d, eax; char *
0x18006342c  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180063433  mov     edx, 0D3Dh; void *
0x180063438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006343d  jmp     short loc_1800633CA
0x18006343f  mov     rcx, [rbp+57h+var_A8]
0x180063443  mov     rax, [rcx]
0x180063446  mov     rdx, rsi
0x180063449  mov     rax, [rax+40h]
0x18006344d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063452  mov     ebx, eax
0x180063454  lea     rcx, [rbp+57h+var_70]; this
0x180063458  call    ??1AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::~AccountSystemOnlyInfo(void)
0x18006345d  nop
0x18006345e  lea     rcx, [rbp+57h+var_A8]
0x180063462  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063467  mov     eax, ebx
0x180063469  mov     rbx, [rsp+0E0h+arg_0]
0x180063471  add     rsp, 0D0h
0x180063478  pop     rdi
0x180063479  pop     rsi
0x18006347a  pop     rbp
0x18006347b  retn
```
