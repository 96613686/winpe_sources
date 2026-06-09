# Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation::ValidateProviderAndAccountsMatch(void)

- ea: `0x180104f84`
- end: `0x1801052df`
- name: `?ValidateProviderAndAccountsMatch@CWebTokenRequestResultOperation@Core@Web@Authentication@Security@Windows@@AEAAJXZ`
- size: `859`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180100fb8`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180030a78`
- `0x18004e750`
- `0x18004fdbc`
- `0x180063ff0`
- `0x18007ef3c`
- `0x1801026d0`
- `0x180104f84`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180105092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801050fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801051c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801051f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180105242`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801052d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180105092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801050fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801051c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801051f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180105242`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801052d1`

## string_xrefs

- `0x180105039`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180105073`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x1801050ca`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180105228`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180105265`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x180105289`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x1801052ad`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation::ValidateProviderAndAccountsMatch(
        Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation *this)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int PluginPFN; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // esi
  HSTRING v12; // rcx
  unsigned int v13; // r15d
  HSTRING v14; // rbx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rdi
  int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rdi
  int v21; // eax
  int v22; // eax
  HSTRING v23; // rdi
  HSTRING v24; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v25; // [rsp+20h] [rbp-18h] BYREF
  HSTRING v26; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  unsigned int v28; // [rsp+70h] [rbp+38h] BYREF
  __int64 v29; // [rsp+78h] [rbp+40h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v30; // [rsp+80h] [rbp+48h] BYREF
  HSTRING string; // [rsp+88h] [rbp+50h] BYREF

  if ( *((_QWORD *)this + 1) )
    return 0;
  v25 = 0;
  v3 = *((_QWORD *)this + 2);
  v4 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v3 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  v5 = v4(v3, &v25);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 779;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)v5,
      (int)v25);
    goto LABEL_36;
  }
  if ( !v25 )
  {
    v6 = -2147024809;
    goto LABEL_36;
  }
  if ( Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsSystemProvider(v25) )
  {
    if ( (unsigned int)dword_180175000 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180175000,
        word_1801567B2,
        0,
        0);
LABEL_23:
    v6 = 0;
    goto LABEL_36;
  }
  v5 = Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation::InitializeTokenBrokerInternal(this);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 796;
    goto LABEL_12;
  }
  string = 0;
  PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(
                (__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v25,
                &string);
  v6 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x321,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)PluginPFN,
      (int)v25);
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_36;
  }
  v28 = 0;
  v9 = *((_QWORD *)this + 3);
  if ( !v9 )
    goto LABEL_21;
  v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 56LL))(v9, &v28);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)v10,
      (int)v25);
    v12 = string;
    if ( string )
      goto LABEL_34;
    goto LABEL_35;
  }
  if ( !v28 )
  {
LABEL_21:
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_23;
  }
  v13 = 0;
  v14 = string;
  while ( 1 )
  {
    v29 = 0;
    v15 = *((_QWORD *)this + 3);
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v17 = v16(v15, v13, &v29);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33A,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v17,
        (int)v25);
      goto LABEL_45;
    }
    v30 = 0;
    v19 = v29;
    v20 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v29 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    v21 = v20(v19, &v30);
    v18 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33D,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v21,
        (int)v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
LABEL_45:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      if ( v14 )
        WindowsDeleteString(v14);
      v6 = v18;
      goto LABEL_36;
    }
    v26 = 0;
    v22 = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(
            (__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v30,
            &v26);
    v11 = v22;
    if ( v22 < 0 )
      break;
    v23 = v26;
    if ( !ComparePfns(v14, v26) )
    {
      v11 = -2147024809;
      TryOriginateError(-2147024809, 0x3F4u);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x348,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)0x80070057LL,
        (int)v25);
      if ( v23 )
      {
        v24 = v23;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    if ( v23 )
      WindowsDeleteString(v23);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    if ( ++v13 >= v28 )
      goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x342,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
    (const char *)(unsigned int)v22,
    (int)v25);
  v24 = v26;
  if ( v26 )
LABEL_39:
    WindowsDeleteString(v24);
LABEL_40:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
LABEL_32:
  if ( !v14 )
    goto LABEL_35;
  v12 = v14;
LABEL_34:
  WindowsDeleteString(v12);
LABEL_35:
  v6 = v11;
LABEL_36:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  return v6;
}

```

## disassembly

```asm
0x180104f84  push    rbp
0x180104f86  push    rbx
0x180104f87  push    rsi
0x180104f88  push    rdi
0x180104f89  push    r14
0x180104f8b  push    r15
0x180104f8d  mov     rbp, rsp
0x180104f90  sub     rsp, 38h
0x180104f94  mov     r14, rcx
0x180104f97  cmp     qword ptr [rcx+8], 0
0x180104f9c  jz      short loc_180104FA5
0x180104f9e  xor     eax, eax
0x180104fa0  jmp     loc_180105203
0x180104fa5  mov     [rbp+var_18], 0
0x180104fad  mov     rdi, [rcx+10h]
0x180104fb1  mov     rax, [rdi]
0x180104fb4  mov     rbx, [rax+30h]
0x180104fb8  lea     rcx, [rbp+var_18]
0x180104fbc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180104fc1  lea     rdx, [rbp+var_18]
0x180104fc5  mov     rcx, rdi
0x180104fc8  mov     rax, rbx
0x180104fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104fd0  mov     ebx, eax
0x180104fd2  test    eax, eax
0x180104fd4  jns     short loc_180104FDD
0x180104fd6  mov     edx, 30Bh
0x180104fdb  jmp     short loc_180105039
0x180104fdd  mov     rcx, [rbp+var_18]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180104fe1  test    rcx, rcx
0x180104fe4  jnz     short loc_180104FF0
0x180104fe6  mov     ebx, 80070057h
0x180104feb  jmp     loc_1801051F8
0x180104ff0  call    ?IsSystemProvider@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SA_NPEAUIWebAccountProvider@Credentials@46@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsSystemProvider(Windows::Security::Credentials::IWebAccountProvider *)
0x180104ff5  test    al, al
0x180104ff7  jz      short loc_180105026
0x180104ff9  mov     eax, cs:dword_180175000
0x180104fff  cmp     eax, 5
0x180105002  jbe     loc_180105104
0x180105008  xor     r9d, r9d
0x18010500b  xor     r8d, r8d
0x18010500e  lea     rdx, word_1801567B2
0x180105015  lea     rcx, dword_180175000
0x18010501c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180105021  jmp     loc_180105104
0x180105026  mov     rcx, r14; this
0x180105029  call    ?InitializeTokenBrokerInternal@CWebTokenRequestResultOperation@Core@Web@Authentication@Security@Windows@@AEAAJXZ; Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation::InitializeTokenBrokerInternal(void)
0x18010502e  mov     ebx, eax
0x180105030  test    eax, eax
0x180105032  jns     short loc_180105051
0x180105034  mov     edx, 31Ch; void *
0x180105039  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180105040  mov     r9d, eax; char *
0x180105043  mov     rcx, [rbp+30h]; this
0x180105047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010504c  jmp     loc_1801051F8
0x180105051  mov     [rbp+string], 0
0x180105059  lea     rdx, [rbp+string]; HSTRING *
0x18010505d  mov     rcx, [rbp+var_18]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180105061  call    ?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x180105066  mov     ebx, eax
0x180105068  test    eax, eax
0x18010506a  jns     short loc_18010509D
0x18010506c  mov     rcx, [rbp+30h]; this
0x180105070  mov     r9d, eax; char *
0x180105073  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x18010507a  mov     edx, 321h; void *
0x18010507f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105084  nop
0x180105085  mov     rcx, [rbp+string]; string
0x180105089  test    rcx, rcx
0x18010508c  jz      loc_1801051F8
0x180105092  call    cs:__imp_WindowsDeleteString
0x180105098  jmp     loc_1801051F8
0x18010509d  mov     [rbp+arg_0], 0
0x1801050a4  mov     rcx, [r14+18h]
0x1801050a8  test    rcx, rcx
0x1801050ab  jz      short loc_1801050F5
0x1801050ad  mov     rax, [rcx]
0x1801050b0  lea     rdx, [rbp+arg_0]
0x1801050b4  mov     rax, [rax+38h]
0x1801050b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801050bd  mov     esi, eax
0x1801050bf  test    eax, eax
0x1801050c1  jns     short loc_1801050EE
0x1801050c3  mov     rcx, [rbp+30h]; this
0x1801050c7  mov     r9d, eax; char *
0x1801050ca  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x1801050d1  mov     edx, 32Dh; void *
0x1801050d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801050db  nop
0x1801050dc  mov     rcx, [rbp+string]
0x1801050e0  test    rcx, rcx
0x1801050e3  jz      loc_1801051F6
0x1801050e9  jmp     loc_1801051F0
0x1801050ee  mov     eax, [rbp+arg_0]
0x1801050f1  test    eax, eax
0x1801050f3  jnz     short loc_18010510B
0x1801050f5  mov     rcx, [rbp+string]; string
0x1801050f9  test    rcx, rcx
0x1801050fc  jz      short loc_180105104
0x1801050fe  call    cs:__imp_WindowsDeleteString
0x180105104  xor     ebx, ebx
0x180105106  jmp     loc_1801051F8
0x18010510b  xor     r15d, r15d
0x18010510e  mov     rbx, [rbp+string]
0x180105112  test    eax, eax
0x180105114  jz      loc_1801051E8
0x18010511a  mov     [rbp+arg_8], 0
0x180105122  mov     rsi, [r14+18h]
0x180105126  mov     rax, [rsi]
0x180105129  mov     rdi, [rax+30h]
0x18010512d  lea     rcx, [rbp+arg_8]
0x180105131  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105136  lea     r8, [rbp+arg_8]
0x18010513a  mov     edx, r15d
0x18010513d  mov     rcx, rsi
0x180105140  mov     rax, rdi
0x180105143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105148  mov     edi, eax
0x18010514a  test    eax, eax
0x18010514c  js      loc_1801052A6
0x180105152  mov     [rbp+arg_10], 0
0x18010515a  mov     rsi, [rbp+arg_8]
0x18010515e  mov     rax, [rsi]
0x180105161  mov     rdi, [rax+30h]
0x180105165  lea     rcx, [rbp+arg_10]
0x180105169  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010516e  lea     rdx, [rbp+arg_10]
0x180105172  mov     rcx, rsi
0x180105175  mov     rax, rdi
0x180105178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010517d  mov     edi, eax
0x18010517f  test    eax, eax
0x180105181  js      loc_180105282
0x180105187  mov     [rbp+var_10], 0
0x18010518f  lea     rdx, [rbp+var_10]; HSTRING *
0x180105193  mov     rcx, [rbp+arg_10]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180105197  call    ?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x18010519c  mov     esi, eax
0x18010519e  test    eax, eax
0x1801051a0  js      loc_18010525E
0x1801051a6  mov     rdi, [rbp+var_10]
0x1801051aa  mov     rdx, rdi; HSTRING
0x1801051ad  mov     rcx, rbx; string
0x1801051b0  call    ?ComparePfns@@YA_NPEAUHSTRING__@@0@Z; ComparePfns(HSTRING__ *,HSTRING__ *)
0x1801051b5  test    al, al
0x1801051b7  jz      short loc_180105210
0x1801051b9  test    rdi, rdi
0x1801051bc  jz      short loc_1801051C8
0x1801051be  mov     rcx, rdi; string
0x1801051c1  call    cs:__imp_WindowsDeleteString
0x1801051c7  nop
0x1801051c8  lea     rcx, [rbp+arg_10]
0x1801051cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801051d1  nop
0x1801051d2  lea     rcx, [rbp+arg_8]
0x1801051d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801051db  inc     r15d
0x1801051de  cmp     r15d, [rbp+arg_0]
0x1801051e2  jb      loc_18010511A
0x1801051e8  test    rbx, rbx
0x1801051eb  jz      short loc_1801051F6
0x1801051ed  mov     rcx, rbx; string
0x1801051f0  call    cs:__imp_WindowsDeleteString
0x1801051f6  mov     ebx, esi
0x1801051f8  lea     rcx, [rbp+var_18]
0x1801051fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105201  mov     eax, ebx
0x180105203  add     rsp, 38h
0x180105207  pop     r15
0x180105209  pop     r14
0x18010520b  pop     rdi
0x18010520c  pop     rsi
0x18010520d  pop     rbx
0x18010520e  pop     rbp
0x18010520f  retn
0x180105210  mov     edx, 3F4h; unsigned __int16
0x180105215  mov     esi, 80070057h
0x18010521a  mov     ecx, esi; int
0x18010521c  call    ?TryOriginateError@@YAXJG@Z; TryOriginateError(long,ushort)
0x180105221  mov     rcx, [rbp+30h]; this
0x180105225  mov     r9d, esi; char *
0x180105228  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x18010522f  mov     edx, 348h; void *
0x180105234  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105239  nop
0x18010523a  test    rdi, rdi
0x18010523d  jz      short loc_180105249
0x18010523f  mov     rcx, rdi; string
0x180105242  call    cs:__imp_WindowsDeleteString
0x180105248  nop
0x180105249  lea     rcx, [rbp+arg_10]
0x18010524d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105252  nop
0x180105253  lea     rcx, [rbp+arg_8]
0x180105257  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010525c  jmp     short loc_1801051E8
0x18010525e  mov     rcx, [rbp+30h]; this
0x180105262  mov     r9d, esi; char *
0x180105265  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x18010526c  mov     edx, 342h; void *
0x180105271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105276  nop
0x180105277  mov     rcx, [rbp+var_10]
0x18010527b  test    rcx, rcx
0x18010527e  jz      short loc_180105249
0x180105280  jmp     short loc_180105242
0x180105282  mov     rcx, [rbp+30h]; this
0x180105286  mov     r9d, edi; char *
0x180105289  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180105290  mov     edx, 33Dh; void *
0x180105295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010529a  nop
0x18010529b  lea     rcx, [rbp+arg_10]
0x18010529f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801052a4  jmp     short loc_1801052BF
0x1801052a6  mov     rcx, [rbp+30h]; this
0x1801052aa  mov     r9d, edi; char *
0x1801052ad  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x1801052b4  mov     edx, 33Ah; void *
0x1801052b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801052be  nop
0x1801052bf  lea     rcx, [rbp+arg_8]
0x1801052c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801052c8  nop
0x1801052c9  test    rbx, rbx
0x1801052cc  jz      short loc_1801052D7
0x1801052ce  mov     rcx, rbx; string
0x1801052d1  call    cs:__imp_WindowsDeleteString
0x1801052d7  mov     ebx, edi
0x1801052d9  jmp     loc_1801051F8
```
