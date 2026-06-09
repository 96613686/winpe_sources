# Windows::Internal::Security::Authentication::Web::FindAllSystemAccountsOperation(Windows::Internal::Security::Authentication::Web::CallerContext *,long (*)(Windows::Security::Credentials::IWebAccount *,bool &),Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> * *)

- ea: `0x18006e74c`
- end: `0x18006eda2`
- name: `?FindAllSystemAccountsOperation@Web@Authentication@Security@Internal@Windows@@YAJPEAVCallerContext@12345@P6AJPEAUIWebAccount@Credentials@35@AEA_N@ZPEAPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@@Z`
- size: `1622`
- prototype: `__int64 __fastcall(struct Windows::Internal::Security::Authentication::Web::CallerContext *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b5e0c`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000e2b0`
- `0x1800200b4`
- `0x180024544`
- `0x1800262f0`
- `0x1800269f4`
- `0x180040980`
- `0x180045a04`
- `0x18004e850`
- `0x18004fdbc`
- `0x18006e064`
- `0x18006e74c`
- `0x18008fb0c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e9b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ea97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e9b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ea97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006eb48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ebf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ec54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006eb48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ebf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ec54`
- `ntdll!RtlIsMultiSessionSku` at `0x18006e7a0`
- `ntdll!RtlIsMultiSessionSku` at `0x18006e7a0`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x18006e7e1`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x18006e7e1`

## string_xrefs

- `0x18006e833`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006e879`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006e8b4`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006eb84`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006ebb9`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006ebdc`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006ec39`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006ec8a`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006ecbc`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006ed34`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x18006ed67`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::Security::Authentication::Web::FindAllSystemAccountsOperation(
        struct Windows::Internal::Security::Authentication::Web::CallerContext *a1,
        int a2,
        __int64 a3)
{
  __int64 v3; // r12
  unsigned __int64 *v4; // rsi
  unsigned int v5; // r13d
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rdx
  int AllPlugins; // eax
  int v11; // eax
  int v12; // r9d
  int v13; // edi
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *AccountManagerInstance; // r14
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v15; // r15
  unsigned int v16; // r12d
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v19; // eax
  int PluginPFN; // eax
  HSTRING v21; // rbx
  int v22; // r9d
  int IsPluginMultiUserAware; // eax
  __int64 (__fastcall *v24)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, HSTRING, struct Windows::Security::Credentials::IWebAccountProvider *, __int64 *); // rdi
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v25; // rcx
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64 *); // rdi
  unsigned __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  void (__fastcall *v35)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64); // rax
  int v36; // eax
  int v38; // [rsp+28h] [rbp-49h]
  __int64 v39; // [rsp+38h] [rbp-39h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v40; // [rsp+40h] [rbp-31h] BYREF
  __int64 v41; // [rsp+48h] [rbp-29h] BYREF
  unsigned int v42; // [rsp+50h] [rbp-21h] BYREF
  unsigned int v43; // [rsp+54h] [rbp-1Dh] BYREF
  __int64 v44; // [rsp+58h] [rbp-19h] BYREF
  __int64 v45; // [rsp+60h] [rbp-11h] BYREF
  int v46; // [rsp+68h] [rbp-9h] BYREF
  int v47; // [rsp+6Ch] [rbp-5h] BYREF
  HSTRING string; // [rsp+70h] [rbp-1h] BYREF
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v49; // [rsp+78h] [rbp+7h]
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v50; // [rsp+80h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  PCWSTR StringRawBuffer; // [rsp+F0h] [rbp+7Fh] BYREF

  v3 = a3;
  v4 = (unsigned __int64 *)a1;
  v5 = 0;
  v44 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(
         v6,
         &v44);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 38;
    goto LABEL_13;
  }
  if ( (unsigned __int8)RtlIsMultiSessionSku()
    || (Windows::Internal::Security::Authentication::Web::detail::RunningAsWellKnownSid(&StringRawBuffer, 0),
        !BYTE4(StringRawBuffer))
    || (_DWORD)StringRawBuffer != 110
    || (v46 = 0, (unsigned __int8)IsIsEmbeddedModeAllowedPresent()) && (int)IsEmbeddedModeAllowed(&v46) >= 0 && v46 )
  {
    v39 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    AllPlugins = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetAllPlugins((struct Windows::Internal::Security::Authentication::Web::CallerContext *)v4);
    v8 = AllPlugins;
    if ( AllPlugins < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
        (const char *)(unsigned int)AllPlugins,
        v38);
LABEL_77:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      goto LABEL_78;
    }
    v43 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 56LL))(v39, &v43);
    v13 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
        (const char *)(unsigned int)v11,
        v38);
LABEL_19:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      v8 = v13;
      goto LABEL_78;
    }
    if ( (unsigned int)dword_180175000 > 5 )
    {
      LODWORD(StringRawBuffer) = v43;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180175000,
        (unsigned int)byte_180151A11,
        0,
        v12,
        (__int64)&StringRawBuffer);
    }
    v49 = 0;
    AccountManagerInstance = Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(
                               0,
                               0);
    v49 = AccountManagerInstance;
    if ( !AccountManagerInstance )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
        (const char *)0x8007000ELL,
        v38);
      goto LABEL_77;
    }
    v50 = 0;
    v15 = Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(
            1,
            v4[2]);
    v50 = v15;
    if ( !v15 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
        (const char *)0x8007000ELL,
        v38);
      goto LABEL_75;
    }
    v40 = 0;
    if ( v43 )
    {
      v16 = 0;
      while ( 1 )
      {
        v17 = v39;
        v18 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v39 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        v19 = v18(v17, v5, &v40);
        v8 = v19;
        if ( v19 < 0 )
        {
          v31 = (unsigned int)v19;
          v32 = 88;
          goto LABEL_70;
        }
        string = 0;
        PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(
                      (struct Windows::Internal::Security::Authentication::Web::CallerContext *)v4,
                      (__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v40,
                      &string);
        v8 = PluginPFN;
        if ( PluginPFN < 0 )
          break;
        v21 = string;
        if ( (unsigned int)dword_180175000 > 5 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_180175000,
            (unsigned int)byte_1801519C3,
            0,
            v22,
            (__int64)&StringRawBuffer);
        }
        LOBYTE(StringRawBuffer) = 0;
        IsPluginMultiUserAware = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(
                                   (struct Windows::Internal::Security::Authentication::Web::CallerContext *)v4,
                                   v21,
                                   (bool *)&StringRawBuffer);
        v13 = IsPluginMultiUserAware;
        if ( IsPluginMultiUserAware < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x64,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
            (const char *)(unsigned int)IsPluginMultiUserAware,
            v38);
          goto LABEL_62;
        }
        v41 = 0;
        if ( (_BYTE)StringRawBuffer )
        {
          v24 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, HSTRING, struct Windows::Security::Credentials::IWebAccountProvider *, __int64 *))(*(_QWORD *)v15 + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
          v25 = v15;
        }
        else
        {
          v24 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, HSTRING, struct Windows::Security::Credentials::IWebAccountProvider *, __int64 *))(*(_QWORD *)AccountManagerInstance + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
          v25 = AccountManagerInstance;
        }
        v38 = a2;
        v13 = v24(v25, v21, v40, &v41);
        if ( v13 == -2147024894 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
        }
        else
        {
          if ( v13 < 0 )
          {
            v34 = 125;
            goto LABEL_59;
          }
          v42 = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 56LL))(v41, &v42);
          if ( v13 < 0 )
          {
            v34 = 128;
LABEL_59:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v34,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
              (const char *)(unsigned int)v13,
              a2);
LABEL_56:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_62:
            if ( v21 )
              WindowsDeleteString(v21);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
            (**(void (__fastcall ***)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64))v15)(
              v15,
              1);
            (**(void (__fastcall ***)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64))AccountManagerInstance)(
              AccountManagerInstance,
              1);
            goto LABEL_19;
          }
          if ( (unsigned int)dword_180175000 > 5 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v21, 0);
            v47 = v42;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v26,
              (unsigned int)&word_1801518D6,
              v27,
              v28,
              (__int64)&v47,
              (__int64)&StringRawBuffer);
          }
          if ( v42 )
          {
            while ( 1 )
            {
              v45 = 0;
              v29 = v41;
              v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              v13 = v30(v29, v16, &v45);
              if ( v13 < 0 )
                break;
              v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 104LL))(v44, v45);
              if ( v13 < 0 )
              {
                v33 = 140;
                goto LABEL_55;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              if ( ++v16 >= v42 )
              {
                v4 = (unsigned __int64 *)a1;
                goto LABEL_45;
              }
            }
            v33 = 139;
LABEL_55:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v33,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
              (const char *)(unsigned int)v13,
              v38);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
            goto LABEL_56;
          }
LABEL_45:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
          v16 = 0;
        }
        if ( v21 )
          WindowsDeleteString(v21);
        if ( ++v5 >= v43 )
        {
          v3 = a3;
          goto LABEL_50;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
        (const char *)(unsigned int)PluginPFN,
        v38);
      if ( string )
        WindowsDeleteString(string);
    }
    else
    {
LABEL_50:
      v8 = 0;
      if ( v13 != -2147024894 )
        v8 = v13;
      if ( v8 >= 0 )
      {
        v36 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 64LL))(v44, v3);
        v8 = v36;
        if ( v36 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
          (**(void (__fastcall ***)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64))v15)(
            v15,
            1);
          (**(void (__fastcall ***)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64))AccountManagerInstance)(
            AccountManagerInstance,
            1);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x94,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
          (const char *)(unsigned int)v36,
          v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        v35 = **(void (__fastcall ***)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64))v15;
        goto LABEL_68;
      }
      v31 = (unsigned int)v8;
      v32 = 146;
LABEL_70:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
        (const char *)v31,
        v38);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    v35 = **(void (__fastcall ***)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64))v15;
LABEL_68:
    v35(v15, 1);
LABEL_75:
    (**(void (__fastcall ***)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64))AccountManagerInstance)(
      AccountManagerInstance,
      1);
    goto LABEL_77;
  }
  if ( (unsigned int)dword_180175000 > 3 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      qword_180151988,
      0,
      0);
  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 64LL))(v44, v3);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v8 = 0;
    goto LABEL_78;
  }
  v9 = 54;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
    (const char *)(unsigned int)v7,
    v38);
LABEL_78:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006e74c  mov     rax, rsp
0x18006e74f  mov     [rax+18h], r8
0x18006e753  mov     [rax+10h], rdx
0x18006e757  mov     [rax+8], rcx
0x18006e75b  push    rbp
0x18006e75c  push    rbx
0x18006e75d  push    rsi
0x18006e75e  push    rdi
0x18006e75f  push    r12
0x18006e761  push    r13
0x18006e763  push    r14
0x18006e765  push    r15
0x18006e767  lea     rbp, [rax-5Fh]
0x18006e76b  sub     rsp, 88h
0x18006e772  mov     r12, r8
0x18006e775  mov     rsi, rcx
0x18006e778  xor     r13d, r13d
0x18006e77b  mov     [rbp+57h+var_70], r13
0x18006e77f  lea     rcx, [rbp+57h+var_70]
0x18006e783  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e788  lea     rdx, [rbp+57h+var_70]
0x18006e78c  call    ??$CreateExternalObjectVector@VWebAccount@Credentials@Security@Windows@@V?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0> * *)
0x18006e791  mov     ebx, eax
0x18006e793  test    eax, eax
0x18006e795  jns     short loc_18006E7A0
0x18006e797  lea     edx, [r13+26h]
0x18006e79b  jmp     loc_18006E833
0x18006e7a0  call    cs:__imp_RtlIsMultiSessionSku
0x18006e7a6  test    al, al
0x18006e7a8  jnz     loc_18006E853
0x18006e7ae  xor     edx, edx
0x18006e7b0  lea     rcx, [rbp+57h+arg_18]
0x18006e7b4  call    ?RunningAsWellKnownSid@detail@Web@Authentication@Security@Internal@Windows@@YA?AV?$optional@W4WELL_KNOWN_SID_TYPE@@@std@@PEAX@Z; Windows::Internal::Security::Authentication::Web::detail::RunningAsWellKnownSid(void *)
0x18006e7b9  cmp     byte ptr [rbp+57h+arg_18+4], r13b
0x18006e7c0  jz      loc_18006E853
0x18006e7c6  cmp     dword ptr [rbp+57h+arg_18], 6Eh ; 'n'
0x18006e7ca  jnz     loc_18006E853
0x18006e7d0  mov     [rbp+57h+var_60], r13d
0x18006e7d4  call    IsIsEmbeddedModeAllowedPresent
0x18006e7d9  test    al, al
0x18006e7db  jz      short loc_18006E7F1
0x18006e7dd  lea     rcx, [rbp+57h+var_60]
0x18006e7e1  call    cs:__imp_IsEmbeddedModeAllowed
0x18006e7e7  test    eax, eax
0x18006e7e9  js      short loc_18006E7F1
0x18006e7eb  cmp     [rbp+57h+var_60], r13d
0x18006e7ef  jnz     short loc_18006E853
0x18006e7f1  mov     eax, cs:dword_180175000
0x18006e7f7  cmp     eax, 3
0x18006e7fa  jbe     short loc_18006E815
0x18006e7fc  xor     r9d, r9d
0x18006e7ff  xor     r8d, r8d
0x18006e802  lea     rdx, qword_180151988
0x18006e809  lea     rcx, dword_180175000
0x18006e810  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006e815  mov     rcx, [rbp+57h+var_70]
0x18006e819  mov     rax, [rcx]
0x18006e81c  mov     rdx, r12
0x18006e81f  mov     rax, [rax+40h]
0x18006e823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e828  mov     ebx, eax
0x18006e82a  test    eax, eax
0x18006e82c  jns     short loc_18006E84B
0x18006e82e  mov     edx, 36h ; '6'; void *
0x18006e833  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006e83a  mov     r9d, eax; char *
0x18006e83d  mov     rcx, [rbp+5Fh]; this
0x18006e841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e846  jmp     loc_18006ED83
0x18006e84b  mov     ebx, r13d
0x18006e84e  jmp     loc_18006ED83
0x18006e853  mov     [rbp+57h+var_90], r13
0x18006e857  lea     rcx, [rbp+57h+var_90]
0x18006e85b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e860  lea     rdx, [rbp+57h+var_90]
0x18006e864  mov     rcx, rsi; struct Windows::Internal::Security::Authentication::Web::CallerContext *
0x18006e867  call    ?GetAllPlugins@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAPEAU?$IVectorView@PEAVWebAccountProvider@Credentials@Security@Windows@@@Collections@Foundation@6@_N@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetAllPlugins(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccountProvider *> * *,bool)
0x18006e86c  mov     ebx, eax
0x18006e86e  test    eax, eax
0x18006e870  jns     short loc_18006E88F
0x18006e872  mov     rcx, [rbp+5Fh]; this
0x18006e876  mov     r9d, eax; char *
0x18006e879  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006e880  mov     edx, 40h ; '@'; void *
0x18006e885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e88a  jmp     loc_18006ED79
0x18006e88f  mov     [rbp+57h+var_74], r13d
0x18006e893  mov     rcx, [rbp+57h+var_90]
0x18006e897  mov     rax, [rcx]
0x18006e89a  lea     rdx, [rbp+57h+var_74]
0x18006e89e  mov     rax, [rax+38h]
0x18006e8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8a7  mov     edi, eax
0x18006e8a9  test    eax, eax
0x18006e8ab  jns     short loc_18006E8D6
0x18006e8ad  mov     rcx, [rbp+5Fh]; this
0x18006e8b1  mov     r9d, eax; char *
0x18006e8b4  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006e8bb  mov     edx, 46h ; 'F'; void *
0x18006e8c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e8c5  nop
0x18006e8c6  lea     rcx, [rbp+57h+var_90]
0x18006e8ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e8cf  mov     ebx, edi
0x18006e8d1  jmp     loc_18006ED83
0x18006e8d6  mov     eax, cs:dword_180175000
0x18006e8dc  cmp     eax, 5
0x18006e8df  jbe     short loc_18006E906
0x18006e8e1  mov     eax, [rbp+57h+var_74]
0x18006e8e4  mov     dword ptr [rbp+57h+arg_18], eax
0x18006e8e7  lea     rax, [rbp+57h+arg_18]
0x18006e8eb  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18006e8f0  xor     r8d, r8d
0x18006e8f3  lea     rdx, byte_180151A11
0x18006e8fa  lea     rcx, dword_180175000
0x18006e901  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006e906  mov     [rbp+57h+var_50], r13
0x18006e90a  xor     edx, edx; unsigned __int64
0x18006e90c  xor     ecx, ecx; bool
0x18006e90e  call    ?GetAccountManagerInstance@CAccountManagerFactory@TokenBroker@Authentication@Security@Internal@Windows@@SAPEAVIAccountManager@23456@_N_K@Z; Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(bool,unsigned __int64)
0x18006e913  mov     r14, rax
0x18006e916  mov     [rbp+57h+var_50], rax
0x18006e91a  test    rax, rax
0x18006e91d  jz      loc_18006ED5B
0x18006e923  mov     [rbp+57h+var_48], r13
0x18006e927  mov     rdx, [rsi+10h]; unsigned __int64
0x18006e92b  mov     cl, 1; bool
0x18006e92d  call    ?GetAccountManagerInstance@CAccountManagerFactory@TokenBroker@Authentication@Security@Internal@Windows@@SAPEAVIAccountManager@23456@_N_K@Z; Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(bool,unsigned __int64)
0x18006e932  mov     r15, rax
0x18006e935  mov     [rbp+57h+var_48], rax
0x18006e939  test    rax, rax
0x18006e93c  jz      loc_18006ED28
0x18006e942  mov     [rbp+57h+var_88], r13
0x18006e946  cmp     [rbp+57h+var_74], 0
0x18006e94a  jbe     loc_18006EB5F
0x18006e950  xor     r12d, r12d
0x18006e953  mov     rdi, [rbp+57h+var_90]
0x18006e957  mov     rax, [rdi]
0x18006e95a  mov     rbx, [rax+30h]
0x18006e95e  lea     rcx, [rbp+57h+var_88]
0x18006e962  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e967  lea     r8, [rbp+57h+var_88]
0x18006e96b  mov     edx, r13d
0x18006e96e  mov     rcx, rdi
0x18006e971  mov     rax, rbx
0x18006e974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e979  mov     ebx, eax
0x18006e97b  test    eax, eax
0x18006e97d  js      loc_18006EC82
0x18006e983  mov     [rbp+57h+string], r12
0x18006e987  lea     r8, [rbp+57h+string]; HSTRING *
0x18006e98b  mov     rdx, [rbp+57h+var_88]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18006e98f  mov     rcx, rsi; this
0x18006e992  call    ?GetPluginPFN@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x18006e997  mov     ebx, eax
0x18006e999  test    eax, eax
0x18006e99b  js      loc_18006EC32
0x18006e9a1  mov     eax, cs:dword_180175000
0x18006e9a7  mov     rbx, [rbp+57h+string]
0x18006e9ab  cmp     eax, 5
0x18006e9ae  jbe     short loc_18006E9DE
0x18006e9b0  xor     edx, edx; length
0x18006e9b2  mov     rcx, rbx; string
0x18006e9b5  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e9bb  mov     [rbp+57h+arg_18], rax
0x18006e9bf  lea     rax, [rbp+57h+arg_18]
0x18006e9c3  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18006e9c8  xor     r8d, r8d
0x18006e9cb  lea     rdx, byte_1801519C3
0x18006e9d2  lea     rcx, dword_180175000
0x18006e9d9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18006e9de  mov     byte ptr [rbp+57h+arg_18], r12b
0x18006e9e2  lea     r8, [rbp+57h+arg_18]; bool *
0x18006e9e6  mov     rdx, rbx; HSTRING
0x18006e9e9  mov     rcx, rsi; struct Windows::Internal::Security::Authentication::Web::CallerContext *
0x18006e9ec  call    ?IsPluginMultiUserAware@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@QEAUHSTRING__@@PEA_N@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(Windows::Internal::Security::Authentication::Web::CallerContext *,HSTRING__ * const,bool *)
0x18006e9f1  mov     edi, eax
0x18006e9f3  test    eax, eax
0x18006e9f5  js      loc_18006EBD5
0x18006e9fb  mov     [rbp+57h+var_80], r12
0x18006e9ff  lea     rcx, [rbp+57h+var_80]
0x18006ea03  cmp     byte ptr [rbp+57h+arg_18], r12b
0x18006ea07  jz      short loc_18006EA1A
0x18006ea09  mov     rax, [r15]
0x18006ea0c  mov     rdi, [rax+18h]
0x18006ea10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ea15  mov     rcx, r15
0x18006ea18  jmp     short loc_18006EA29
0x18006ea1a  mov     rax, [r14]
0x18006ea1d  mov     rdi, [rax+18h]
0x18006ea21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ea26  mov     rcx, r14
0x18006ea29  mov     rax, qword ptr [rbp+57h+arg_8]
0x18006ea2d  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18006ea32  lea     r9, [rbp+57h+var_80]
0x18006ea36  mov     r8, [rbp+57h+var_88]
0x18006ea3a  mov     rdx, rbx
0x18006ea3d  mov     rax, rdi
0x18006ea40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ea45  mov     edi, eax
0x18006ea47  cmp     eax, 80070002h
0x18006ea4c  jnz     short loc_18006EA5D
0x18006ea4e  lea     rcx, [rbp+57h+var_80]
0x18006ea52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ea57  nop
0x18006ea58  jmp     loc_18006EB40
0x18006ea5d  test    edi, edi
0x18006ea5f  js      loc_18006EBCE
0x18006ea65  mov     [rbp+57h+var_78], r12d
0x18006ea69  mov     rcx, [rbp+57h+var_80]
0x18006ea6d  mov     rax, [rcx]
0x18006ea70  lea     rdx, [rbp+57h+var_78]
0x18006ea74  mov     rax, [rax+38h]
0x18006ea78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ea7d  mov     edi, eax
0x18006ea7f  test    eax, eax
0x18006ea81  js      loc_18006EBB4
0x18006ea87  mov     eax, cs:dword_180175000
0x18006ea8d  cmp     eax, 5
0x18006ea90  jbe     short loc_18006EAC5
0x18006ea92  xor     edx, edx; length
0x18006ea94  mov     rcx, rbx; string
0x18006ea97  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ea9d  mov     [rbp+57h+arg_18], rax
0x18006eaa1  mov     eax, [rbp+57h+var_78]
0x18006eaa4  mov     [rbp+57h+var_5C], eax
0x18006eaa7  lea     rax, [rbp+57h+arg_18]
0x18006eaab  mov     qword ptr [rsp+0C0h+var_A0+8], rax
0x18006eab0  lea     rax, [rbp+57h+var_5C]
0x18006eab4  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18006eab9  lea     rdx, word_1801518D6
0x18006eac0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18006eac5  cmp     [rbp+57h+var_78], 0
0x18006eac9  jbe     short loc_18006EB33
0x18006eacb  mov     [rbp+57h+var_68], 0
0x18006ead3  mov     rsi, [rbp+57h+var_80]
0x18006ead7  mov     rax, [rsi]
0x18006eada  mov     rdi, [rax+30h]
0x18006eade  lea     rcx, [rbp+57h+var_68]
0x18006eae2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006eae7  lea     r8, [rbp+57h+var_68]
0x18006eaeb  mov     edx, r12d
0x18006eaee  mov     rcx, rsi
0x18006eaf1  mov     rax, rdi
0x18006eaf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eaf9  mov     edi, eax
0x18006eafb  test    eax, eax
0x18006eafd  js      loc_18006EBAD
0x18006eb03  mov     rcx, [rbp+57h+var_70]
0x18006eb07  mov     rax, [rcx]
0x18006eb0a  mov     rdx, [rbp+57h+var_68]
0x18006eb0e  mov     rax, [rax+68h]
0x18006eb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb17  mov     edi, eax
0x18006eb19  test    eax, eax
0x18006eb1b  js      short loc_18006EB7F
0x18006eb1d  lea     rcx, [rbp+57h+var_68]
0x18006eb21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006eb26  inc     r12d
0x18006eb29  cmp     r12d, [rbp+57h+var_78]
0x18006eb2d  jb      short loc_18006EACB
0x18006eb2f  mov     rsi, [rbp+57h+arg_0]
0x18006eb33  lea     rcx, [rbp+57h+var_80]
0x18006eb37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006eb3c  nop
0x18006eb3d  xor     r12d, r12d
0x18006eb40  test    rbx, rbx
0x18006eb43  jz      short loc_18006EB4E
0x18006eb45  mov     rcx, rbx; string
0x18006eb48  call    cs:__imp_WindowsDeleteString
0x18006eb4e  inc     r13d
0x18006eb51  cmp     r13d, [rbp+57h+var_74]
0x18006eb55  jb      loc_18006E953
0x18006eb5b  mov     r12, [rbp+57h+arg_10]
0x18006eb5f  xor     ebx, ebx
0x18006eb61  cmp     edi, 80070002h
0x18006eb67  cmovnz  ebx, edi
0x18006eb6a  test    ebx, ebx
0x18006eb6c  jns     loc_18006EC9C
0x18006eb72  mov     r9d, ebx
0x18006eb75  mov     edx, 92h
0x18006eb7a  jmp     loc_18006EC8A
0x18006eb7f  mov     edx, 8Ch; void *
0x18006eb84  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006eb8b  mov     r9d, edi; char *
0x18006eb8e  mov     rcx, [rbp+5Fh]; this
0x18006eb92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006eb97  nop
0x18006eb98  lea     rcx, [rbp+57h+var_68]
0x18006eb9c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006eba1  nop
0x18006eba2  lea     rcx, [rbp+57h+var_80]
0x18006eba6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ebab  jmp     short loc_18006EBEE
0x18006ebad  mov     edx, 8Bh
0x18006ebb2  jmp     short loc_18006EB84
0x18006ebb4  mov     edx, 80h; void *
0x18006ebb9  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006ebc0  mov     r9d, edi; char *
0x18006ebc3  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
