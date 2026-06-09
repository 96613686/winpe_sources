# GetWebAccountMapForPerApp(Windows::Security::Credentials::IWebAccount *,Windows::Security::Credentials::IWebAccount * *,HSTRING__ *)

- ea: `0x18010f754`
- end: `0x18010fa0a`
- name: `?GetWebAccountMapForPerApp@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAPEAU1234@PEAUHSTRING__@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccount **, HSTRING)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800586a8`
- `0x1800e3080`
- `0x1800e3100`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180028e44`
- `0x180040cc0`
- `0x18004fdbc`
- `0x180063ff0`
- `0x18010f754`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f84a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f940`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f9d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f9ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f84a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f940`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f9d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010f9ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010f859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18010f859`

## string_xrefs

- `0x18010f7d6`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010f82b`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010f8d2`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010f923`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetWebAccountMapForPerApp(
        struct Windows::Security::Credentials::IWebAccount *a1,
        struct Windows::Security::Credentials::IWebAccount **a2,
        HSTRING a3)
{
  __int64 (__fastcall *v6)(struct Windows::Security::Credentials::IWebAccount *, GUID *, _QWORD *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 (__fastcall *v12)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v13; // eax
  int PluginPFN; // eax
  __int64 v15; // rdx
  HSTRING v16; // rbx
  unsigned int v17; // edi
  struct Windows::Security::Credentials::IWebAccount *v18; // rcx
  int v20; // [rsp+20h] [rbp-28h]
  struct Windows::Security::Credentials::IWebAccount *v21; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  HSTRING string; // [rsp+80h] [rbp+38h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v25; // [rsp+88h] [rbp+40h] BYREF
  HSTRING v26; // [rsp+90h] [rbp+48h] BYREF
  HSTRING v27; // [rsp+98h] [rbp+50h] BYREF

  v26 = a3;
  *a2 = 0;
  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &dword_180157F7C,
      0,
      0);
  v22[0] = 0;
  v6 = **(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccount *, GUID *, _QWORD *))a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v22);
  v7 = v6(a1, &GUID_40285a2b_65d5_41f5_b904_76c860d86e26, v22);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE05,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v7,
      v20);
    goto LABEL_34;
  }
  string = 0;
  v9 = v22[0];
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22[0] + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v11 = v10(v9, &string);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE07,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v11,
      v20);
    goto LABEL_7;
  }
  if ( WindowsIsStringEmpty(string) )
  {
    if ( (unsigned int)dword_180175000 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180175000,
        byte_180157F49,
        0,
        0);
    if ( string )
      WindowsDeleteString(string);
    v8 = 0;
    goto LABEL_34;
  }
  v25 = 0;
  v12 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  v13 = v12(a1, &v25);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE16,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v13,
      v20);
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
LABEL_7:
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_34;
  }
  v27 = 0;
  if ( a3 )
  {
    PluginPFN = Windows::Internal::String::Initialize((Windows::Internal::String *)&v27, &v26);
    v8 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      v15 = 3614;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)PluginPFN,
        v20);
      if ( v27 )
        WindowsDeleteString(v27);
      goto LABEL_17;
    }
  }
  else
  {
    WindowsDeleteString(0);
    v27 = 0;
    PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(v25, &v27);
    v8 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      v15 = 3610;
      goto LABEL_21;
    }
  }
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v16 = v27;
  v17 = InitializeAccountFromDataStoreWithDefaultProvider(string, v27, 7u, 0, v25, &v21);
  if ( v17 )
  {
    if ( v17 == -2147024894 )
      v17 = 0;
  }
  else
  {
    v18 = v21;
    v21 = 0;
    *a2 = v18;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  if ( v16 )
    WindowsDeleteString(v16);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  if ( string )
    WindowsDeleteString(string);
  v8 = v17;
LABEL_34:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v22);
  return v8;
}

```

## disassembly

```asm
0x18010f754  mov     [rsp-30h+arg_10], r8
0x18010f759  push    rbp
0x18010f75a  push    rbx
0x18010f75b  push    rsi
0x18010f75c  push    rdi
0x18010f75d  push    r14
0x18010f75f  push    r15
0x18010f761  mov     rbp, rsp
0x18010f764  sub     rsp, 48h
0x18010f768  mov     rsi, r8
0x18010f76b  mov     r15, rdx
0x18010f76e  mov     r14, rcx
0x18010f771  mov     qword ptr [rdx], 0
0x18010f778  mov     eax, cs:dword_180175000
0x18010f77e  cmp     eax, 4
0x18010f781  jbe     short loc_18010F79C
0x18010f783  xor     r9d, r9d
0x18010f786  xor     r8d, r8d
0x18010f789  lea     rdx, dword_180157F7C
0x18010f790  lea     rcx, dword_180175000
0x18010f797  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010f79c  mov     [rbp+var_10], 0
0x18010f7a4  mov     rax, [r14]
0x18010f7a7  mov     rbx, [rax]
0x18010f7aa  lea     rcx, [rbp+var_10]
0x18010f7ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010f7b3  lea     r8, [rbp+var_10]
0x18010f7b7  lea     rdx, _GUID_40285a2b_65d5_41f5_b904_76c860d86e26
0x18010f7be  mov     rcx, r14
0x18010f7c1  mov     rax, rbx
0x18010f7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f7c9  mov     ebx, eax
0x18010f7cb  test    eax, eax
0x18010f7cd  jns     short loc_18010F7EC
0x18010f7cf  mov     rcx, [rbp+30h]; this
0x18010f7d3  mov     r9d, eax; char *
0x18010f7d6  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010f7dd  mov     edx, 0E05h; void *
0x18010f7e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f7e7  jmp     loc_18010F9F2
0x18010f7ec  mov     [rbp+string], 0
0x18010f7f4  mov     rdi, [rbp+var_10]
0x18010f7f8  mov     rax, [rdi]
0x18010f7fb  mov     rbx, [rax+40h]
0x18010f7ff  xor     ecx, ecx; string
0x18010f801  call    cs:__imp_WindowsDeleteString
0x18010f807  mov     [rbp+string], 0
0x18010f80f  lea     rdx, [rbp+string]
0x18010f813  mov     rcx, rdi
0x18010f816  mov     rax, rbx
0x18010f819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f81e  mov     ebx, eax
0x18010f820  test    eax, eax
0x18010f822  jns     short loc_18010F855
0x18010f824  mov     rcx, [rbp+30h]; this
0x18010f828  mov     r9d, eax; char *
0x18010f82b  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010f832  mov     edx, 0E07h; void *
0x18010f837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f83c  nop
0x18010f83d  mov     rcx, [rbp+string]; string
0x18010f841  test    rcx, rcx
0x18010f844  jz      loc_18010F9F2
0x18010f84a  call    cs:__imp_WindowsDeleteString
0x18010f850  jmp     loc_18010F9F2
0x18010f855  mov     rcx, [rbp+string]; string
0x18010f859  call    cs:__imp_WindowsIsStringEmpty
0x18010f85f  test    eax, eax
0x18010f861  jz      short loc_18010F89E
0x18010f863  mov     eax, cs:dword_180175000
0x18010f869  cmp     eax, 4
0x18010f86c  jbe     short loc_18010F888
0x18010f86e  xor     r9d, r9d
0x18010f871  xor     r8d, r8d
0x18010f874  lea     rdx, byte_180157F49
0x18010f87b  lea     rcx, dword_180175000
0x18010f882  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010f887  nop
0x18010f888  mov     rcx, [rbp+string]; string
0x18010f88c  test    rcx, rcx
0x18010f88f  jz      short loc_18010F897
0x18010f891  call    cs:__imp_WindowsDeleteString
0x18010f897  xor     ebx, ebx
0x18010f899  jmp     loc_18010F9F2
0x18010f89e  mov     [rbp+arg_8], 0
0x18010f8a6  mov     rax, [r14]
0x18010f8a9  mov     rbx, [rax+30h]
0x18010f8ad  lea     rcx, [rbp+arg_8]
0x18010f8b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010f8b6  lea     rdx, [rbp+arg_8]
0x18010f8ba  mov     rcx, r14
0x18010f8bd  mov     rax, rbx
0x18010f8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f8c5  mov     ebx, eax
0x18010f8c7  test    eax, eax
0x18010f8c9  jns     short loc_18010F8F2
0x18010f8cb  mov     rcx, [rbp+30h]; this
0x18010f8cf  mov     r9d, eax; char *
0x18010f8d2  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010f8d9  mov     edx, 0E16h; void *
0x18010f8de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f8e3  nop
0x18010f8e4  lea     rcx, [rbp+arg_8]
0x18010f8e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010f8ed  jmp     loc_18010F83D
0x18010f8f2  mov     [rbp+arg_18], 0
0x18010f8fa  test    rsi, rsi
0x18010f8fd  jnz     short loc_18010F948
0x18010f8ff  xor     ecx, ecx; string
0x18010f901  call    cs:__imp_WindowsDeleteString
0x18010f907  mov     [rbp+arg_18], rsi
0x18010f90b  lea     rdx, [rbp+arg_18]; HSTRING *
0x18010f90f  mov     rcx, [rbp+arg_8]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18010f913  call    ?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x18010f918  mov     ebx, eax
0x18010f91a  test    eax, eax
0x18010f91c  jns     short loc_18010F962
0x18010f91e  mov     edx, 0E1Ah; void *
0x18010f923  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010f92a  mov     r9d, eax; char *
0x18010f92d  mov     rcx, [rbp+30h]; this
0x18010f931  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f936  nop
0x18010f937  mov     rcx, [rbp+arg_18]; string
0x18010f93b  test    rcx, rcx
0x18010f93e  jz      short loc_18010F8E4
0x18010f940  call    cs:__imp_WindowsDeleteString
0x18010f946  jmp     short loc_18010F8E4
0x18010f948  lea     rdx, [rbp+arg_10]; HSTRING *
0x18010f94c  lea     rcx, [rbp+arg_18]; this
0x18010f950  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18010f955  mov     ebx, eax
0x18010f957  test    eax, eax
0x18010f959  jns     short loc_18010F962
0x18010f95b  mov     edx, 0E1Eh
0x18010f960  jmp     short loc_18010F923
0x18010f962  mov     [rbp+var_18], 0
0x18010f96a  lea     rcx, [rbp+var_18]
0x18010f96e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010f973  mov     rax, [rbp+arg_8]
0x18010f977  lea     rcx, [rbp+var_18]
0x18010f97b  mov     [rsp+48h+var_20], rcx; struct Windows::Security::Credentials::IWebAccount **
0x18010f980  mov     [rsp+48h+var_28], rax; struct Windows::Security::Credentials::IWebAccountProvider *
0x18010f985  xor     r9d, r9d; HSTRING
0x18010f988  lea     r8d, [r9+7]; unsigned int
0x18010f98c  mov     rbx, [rbp+arg_18]
0x18010f990  mov     rdx, rbx; HSTRING
0x18010f993  mov     rcx, [rbp+string]; HSTRING
0x18010f997  call    ?InitializeAccountFromDataStoreWithDefaultProvider@@YAJQEAUHSTRING__@@0K0PEAUIWebAccountProvider@Credentials@Security@Windows@@PEAPEAUIWebAccount@345@@Z; InitializeAccountFromDataStoreWithDefaultProvider(HSTRING__ * const,HSTRING__ * const,ulong,HSTRING__ * const,Windows::Security::Credentials::IWebAccountProvider *,Windows::Security::Credentials::IWebAccount * *)
0x18010f99c  mov     edi, eax
0x18010f99e  test    eax, eax
0x18010f9a0  jnz     short loc_18010F9B3
0x18010f9a2  mov     rcx, [rbp+var_18]
0x18010f9a6  mov     [rbp+var_18], 0
0x18010f9ae  mov     [r15], rcx
0x18010f9b1  jmp     short loc_18010F9BE
0x18010f9b3  xor     eax, eax
0x18010f9b5  cmp     edi, 80070002h
0x18010f9bb  cmovz   edi, eax
0x18010f9be  lea     rcx, [rbp+var_18]
0x18010f9c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010f9c7  nop
0x18010f9c8  test    rbx, rbx
0x18010f9cb  jz      short loc_18010F9D7
0x18010f9cd  mov     rcx, rbx; string
0x18010f9d0  call    cs:__imp_WindowsDeleteString
0x18010f9d6  nop
0x18010f9d7  lea     rcx, [rbp+arg_8]
0x18010f9db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010f9e0  nop
0x18010f9e1  mov     rcx, [rbp+string]; string
0x18010f9e5  test    rcx, rcx
0x18010f9e8  jz      short loc_18010F9F0
0x18010f9ea  call    cs:__imp_WindowsDeleteString
0x18010f9f0  mov     ebx, edi
0x18010f9f2  lea     rcx, [rbp+var_10]
0x18010f9f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010f9fb  mov     eax, ebx
0x18010f9fd  add     rsp, 48h
0x18010fa01  pop     r15
0x18010fa03  pop     r14
0x18010fa05  pop     rdi
0x18010fa06  pop     rsi
0x18010fa07  pop     rbx
0x18010fa08  pop     rbp
0x18010fa09  retn
```
