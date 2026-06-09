# Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetAuthenticationToken(bool,Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession &,HSTRING__ * *)

- ea: `0x1801cab84`
- end: `0x1801cb130`
- name: `?GetAuthenticationToken@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJ_NAEAVUserAuthenticationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `1452`
- prototype: `__int64 __fastcall(Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *__hidden this, bool, struct Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *, HSTRING *)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1801c6df0`

## callees

- `0x18001ce70`
- `0x180021944`
- `0x180026508`
- `0x180079e30`
- `0x1801c5548`
- `0x1801c55cc`
- `0x1801c7354`
- `0x1801c89b0`
- `0x1801c92c0`
- `0x1801c98bc`
- `0x1801ca044`
- `0x1801ca9c0`
- `0x1801cab84`
- `0x1801cb2f4`
- `0x1801cbba4`
- `0x1801cc464`
- `0x1801cd190`
- `0x1801cd4b8`
- `0x1801cd5c4`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801caca7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cad15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801caca7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801cad15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801caccc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cad31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801caccc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cad31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801cabe5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801cabe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801caff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801caff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cac4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cac8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cacf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cad1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cb03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cb07b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cb0b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cb0f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cac4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cac8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cacf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cad1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cb03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cb07b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cb0b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cb0f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801cabcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801cabcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cb025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cb025`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801cabf7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801cb00c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801cabf7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801cb00c`

## string_xrefs

- `0x1801cae2a`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetAuthenticationToken(
        Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *this,
        bool a2,
        struct Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *a3,
        HSTRING *a4)
{
  DWORD TickCount; // r13d
  int ActiveSystemUser; // eax
  unsigned int v10; // ebx
  struct Windows::System::IUser *v11; // rbx
  int WebAccountProvider; // eax
  int v13; // eax
  int ConnectedAccount; // eax
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *, struct Windows::Security::Credentials::IWebAccount *, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  HSTRING *v20; // rcx
  HSTRING *v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *, HSTRING *); // rbx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  HRESULT LastAuthenticationToken; // eax
  unsigned __int64 v28; // r9
  DWORD v29; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v32; // [rsp+20h] [rbp-79h]
  int v33; // [rsp+20h] [rbp-79h]
  HSTRING v34; // [rsp+30h] [rbp-69h]
  struct Windows::Security::Credentials::IWebAccountProvider *v35; // [rsp+38h] [rbp-61h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *v36; // [rsp+40h] [rbp-59h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v37; // [rsp+48h] [rbp-51h] BYREF
  HSTRING v38; // [rsp+50h] [rbp-49h] BYREF
  __int64 v39; // [rsp+58h] [rbp-41h] BYREF
  __int64 v40; // [rsp+60h] [rbp-39h] BYREF
  HSTRING v41; // [rsp+68h] [rbp-31h] BYREF
  __int64 v42; // [rsp+70h] [rbp-29h] BYREF
  struct Windows::System::IUser *v43; // [rsp+78h] [rbp-21h] BYREF
  unsigned int v44; // [rsp+80h] [rbp-19h] BYREF
  __int64 v45; // [rsp+88h] [rbp-11h] BYREF
  HSTRING string; // [rsp+90h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( WindowsCreateStringReference(&cchOriginalDestLength, 0, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::SetLastAuthenticationToken(
    this,
    string);
  TickCount = GetTickCount();
  v43 = 0;
  ActiveSystemUser = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveSystemUser(this);
  v10 = ActiveSystemUser;
  if ( ActiveSystemUser >= 0 )
  {
    v34 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    WindowsDeleteString(*((HSTRING *)this + 15));
    *((_QWORD *)this + 15) = 0;
    if ( this != (Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *)-24LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v35 = 0;
    v11 = v43;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    WebAccountProvider = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::FindWebAccountProvider(
                           this,
                           a3,
                           &v35,
                           v11);
    v10 = WebAccountProvider;
    if ( WebAccountProvider < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
        (const char *)(unsigned int)WebAccountProvider,
        v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      WindowsDeleteString(v34);
      v34 = 0;
      goto LABEL_45;
    }
    v36 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    v13 = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::CreateWebTokenRequest(
            this,
            a2,
            v35,
            a3,
            &v36);
    v10 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
        (const char *)(unsigned int)v13,
        v33);
LABEL_44:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      WindowsDeleteString(v34);
      v34 = 0;
      goto LABEL_45;
    }
    v37 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    ConnectedAccount = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::FindConnectedAccount(
                         this,
                         v35,
                         a3,
                         &v37);
    v10 = ConnectedAccount;
    if ( ConnectedAccount < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
        (const char *)(unsigned int)ConnectedAccount,
        v33);
LABEL_43:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      goto LABEL_44;
    }
    v39 = 0;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&string,
      L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
      0x46u,
      0x45u);
    v15 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
            &v39);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
        (const char *)(unsigned int)v15,
        v33);
LABEL_42:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      goto LABEL_43;
    }
    v40 = 0;
    if ( v37 )
    {
      v42 = 0;
      v16 = v39;
      v17 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *, struct Windows::Security::Credentials::IWebAccount *, __int64 *))(*(_QWORD *)v39 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v18 = v17(v16, v36, v37, &v42);
      v10 = v18;
      if ( v18 < 0 )
      {
        v19 = 243;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
          (const char *)(unsigned int)v18,
          v33);
        v20 = (HSTRING *)&v42;
LABEL_19:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v20);
LABEL_41:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        goto LABEL_42;
      }
      v18 = BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
              v42,
              &v40);
      v10 = v18;
      if ( v18 < 0 )
      {
        v19 = 244;
        goto LABEL_18;
      }
      v21 = (HSTRING *)&v42;
LABEL_29:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
      v38 = 0;
      if ( v40 )
      {
        v45 = v40;
        v44 = 0;
        string = (HSTRING)&v45;
        hstringHeader.Reserved.Reserved1 = &v44;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = this;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = a3;
        v10 = lambda_acf6ddb890cc9453d47af966f956de06_::operator()(&string);
        Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::ParseWebTokenRequestResult(
          a3,
          v44,
          v10);
        if ( (v10 & 0x80000000) == 0 )
        {
          LastAuthenticationToken = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetLastAuthenticationToken(
                                      this,
                                      (struct Microsoft::WRL::Wrappers::HString *)&v38);
          v10 = LastAuthenticationToken;
          if ( LastAuthenticationToken >= 0 )
          {
            LastAuthenticationToken = WindowsDuplicateString(v38, a4);
            v10 = LastAuthenticationToken;
            if ( LastAuthenticationToken >= 0 )
            {
              v29 = GetTickCount();
              Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::AuthTokenLatency(
                a3,
                v29 - TickCount);
              StringRawBuffer = WindowsGetStringRawBuffer(v38, 0);
              Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::RpsToken(
                a3,
                StringRawBuffer);
              WindowsDeleteString(v38);
              v38 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
              WindowsDeleteString(v34);
              v34 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
              return 0;
            }
            v26 = 260;
          }
          else
          {
            v26 = 259;
          }
          v28 = (unsigned int)LastAuthenticationToken;
          goto LABEL_40;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E2,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
          (const char *)v10,
          v33);
        v26 = 258;
      }
      else
      {
        v10 = -2147023652;
        v26 = 265;
      }
      v28 = v10;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
        (const char *)v28,
        v33);
      WindowsDeleteString(v38);
      v38 = 0;
      goto LABEL_41;
    }
    v41 = 0;
    v22 = v39;
    v23 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *, HSTRING *))(*(_QWORD *)v39 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    v24 = v23(v22, v36, &v41);
    v10 = v24;
    if ( v24 >= 0 )
    {
      v24 = BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
              v41,
              &v40);
      v10 = v24;
      if ( v24 >= 0 )
      {
        v21 = &v41;
        goto LABEL_29;
      }
      v25 = 251;
    }
    else
    {
      v25 = 250;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)v24,
      v33);
    v20 = &v41;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD3,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
    (const char *)(unsigned int)ActiveSystemUser,
    v32);
LABEL_45:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  return v10;
}

```

## disassembly

```asm
0x1801cab84  mov     [rsp-8+arg_8], rbx
0x1801cab89  push    rbp
0x1801cab8a  push    rsi
0x1801cab8b  push    rdi
0x1801cab8c  push    r12
0x1801cab8e  push    r13
0x1801cab90  push    r14
0x1801cab92  push    r15
0x1801cab94  lea     rbp, [rsp-27h]
0x1801cab99  sub     rsp, 0C0h
0x1801caba0  mov     rax, cs:__security_cookie
0x1801caba7  xor     rax, rsp
0x1801cabaa  mov     [rbp+57h+var_40], rax
0x1801cabae  mov     r12, r9
0x1801cabb1  mov     r14, r8
0x1801cabb4  mov     r15b, dl
0x1801cabb7  mov     rsi, rcx
0x1801cabba  lea     r9, [rbp+57h+string]; string
0x1801cabbe  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1801cabc2  xor     edx, edx; length
0x1801cabc4  lea     rcx, cchOriginalDestLength; sourceString
0x1801cabcb  call    cs:__imp_WindowsCreateStringReference
0x1801cabd1  xor     edi, edi
0x1801cabd3  test    eax, eax
0x1801cabd5  jns     short loc_1801CABEB
0x1801cabd7  xor     r9d, r9d; lpArguments
0x1801cabda  xor     r8d, r8d; nNumberOfArguments
0x1801cabdd  lea     edx, [rdi+1]; dwExceptionFlags
0x1801cabe0  mov     ecx, 0C000000Dh; dwExceptionCode
0x1801cabe5  call    cs:__imp_RaiseException
0x1801cabeb  mov     rdx, [rbp+57h+string]; HSTRING
0x1801cabef  mov     rcx, rsi; this
0x1801cabf2  call    ?SetLastAuthenticationToken@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJPEAUHSTRING__@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::SetLastAuthenticationToken(HSTRING__ *)
0x1801cabf7  call    cs:__imp_GetTickCount
0x1801cabfd  mov     r13d, eax
0x1801cac00  mov     [rbp+57h+var_78], rdi
0x1801cac04  lea     rdx, [rbp+57h+var_78]
0x1801cac08  mov     rcx, rsi
0x1801cac0b  call    ?GetActiveSystemUser@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAV?$ComPtr@UIUser@System@Windows@@@WRL@6@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetActiveSystemUser(Microsoft::WRL::ComPtr<Windows::System::IUser> &)
0x1801cac10  mov     ebx, eax
0x1801cac12  test    eax, eax
0x1801cac14  jns     short loc_1801CAC33
0x1801cac16  mov     rcx, [rbp+5Fh]; this
0x1801cac1a  mov     r9d, eax; char *
0x1801cac1d  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801cac24  mov     edx, 0D3h; void *
0x1801cac29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cac2e  jmp     loc_1801CB0FE
0x1801cac33  mov     [rbp+57h+var_C0], rdi
0x1801cac37  mov     rbx, [rbp+57h+var_78]
0x1801cac3b  test    rbx, rbx
0x1801cac3e  jz      loc_1801CAD0E
0x1801cac44  mov     rax, [rbx]
0x1801cac47  mov     rdi, [rax+30h]
0x1801cac4b  xor     ecx, ecx; string
0x1801cac4d  call    cs:__imp_WindowsDeleteString
0x1801cac53  mov     [rbp+57h+var_C0], 0
0x1801cac5b  lea     rdx, [rbp+57h+var_C0]
0x1801cac5f  mov     rcx, rbx
0x1801cac62  mov     rax, rdi
0x1801cac65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cac6a  mov     ebx, eax
0x1801cac6c  test    eax, eax
0x1801cac6e  jns     short loc_1801CACA0
0x1801cac70  mov     rcx, [rbp+5Fh]; this
0x1801cac74  mov     r9d, eax; char *
0x1801cac77  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801cac7e  mov     edx, 0D9h; void *
0x1801cac83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cac88  nop
0x1801cac89  mov     rcx, [rbp+57h+var_C0]; string
0x1801cac8d  call    cs:__imp_WindowsDeleteString
0x1801cac93  mov     [rbp+57h+var_C0], 0
0x1801cac9b  jmp     loc_1801CB0FE
0x1801caca0  lea     rdi, [rsi+18h]
0x1801caca4  mov     rcx, rdi; lpCriticalSection
0x1801caca7  call    cs:__imp_EnterCriticalSection
0x1801cacad  mov     rax, [rbp+57h+var_C0]
0x1801cacb1  mov     [rbp+57h+var_88], rax
0x1801cacb5  lea     rcx, [rsi+78h]; newString
0x1801cacb9  lea     rdx, [rbp+57h+var_88]; HSTRING *
0x1801cacbd  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1801cacc2  mov     ebx, eax
0x1801cacc4  test    rdi, rdi
0x1801cacc7  jz      short loc_1801CACD2
0x1801cacc9  mov     rcx, rdi; lpCriticalSection
0x1801caccc  call    cs:__imp_LeaveCriticalSection
0x1801cacd2  xor     edi, edi
0x1801cacd4  test    ebx, ebx
0x1801cacd6  jns     short loc_1801CAD04
0x1801cacd8  mov     rcx, [rbp+5Fh]; this
0x1801cacdc  mov     r9d, ebx; char *
0x1801cacdf  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801cace6  mov     edx, 0DAh; void *
0x1801caceb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cacf0  nop
0x1801cacf1  mov     rcx, [rbp+57h+var_C0]; string
0x1801cacf5  call    cs:__imp_WindowsDeleteString
0x1801cacfb  mov     [rbp+57h+var_C0], rdi
0x1801cacff  jmp     loc_1801CB0FE
0x1801cad04  mov     rcx, r14; this
0x1801cad07  call    ?IsASUDetected@UserAuthenticationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@QEAAXXZ; Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::IsASUDetected(void)
0x1801cad0c  jmp     short loc_1801CAD37
0x1801cad0e  lea     rbx, [rsi+18h]
0x1801cad12  mov     rcx, rbx; lpCriticalSection
0x1801cad15  call    cs:__imp_EnterCriticalSection
0x1801cad1b  mov     rcx, [rsi+78h]; string
0x1801cad1f  call    cs:__imp_WindowsDeleteString
0x1801cad25  mov     [rsi+78h], rdi
0x1801cad29  test    rbx, rbx
0x1801cad2c  jz      short loc_1801CAD37
0x1801cad2e  mov     rcx, rbx; lpCriticalSection
0x1801cad31  call    cs:__imp_LeaveCriticalSection
0x1801cad37  mov     [rbp+57h+var_B8], rdi
0x1801cad3b  mov     rbx, [rbp+57h+var_78]
0x1801cad3f  lea     rcx, [rbp+57h+var_B8]
0x1801cad43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801cad48  mov     r9, rbx; struct Windows::System::IUser *
0x1801cad4b  lea     r8, [rbp+57h+var_B8]; struct Windows::Security::Credentials::IWebAccountProvider **
0x1801cad4f  mov     rdx, r14; struct Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *
0x1801cad52  mov     rcx, rsi; this
0x1801cad55  call    ?FindWebAccountProvider@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAVUserAuthenticationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@PEAPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAUIUser@System@Windows@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::FindWebAccountProvider(Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession &,Windows::Security::Credentials::IWebAccountProvider * *,Windows::System::IUser *)
0x1801cad5a  mov     ebx, eax
0x1801cad5c  test    eax, eax
0x1801cad5e  jns     short loc_1801CAD87
0x1801cad60  mov     rcx, [rbp+5Fh]; this
0x1801cad64  mov     r9d, eax; char *
0x1801cad67  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801cad6e  mov     edx, 0E3h; void *
0x1801cad73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cad78  nop
0x1801cad79  lea     rcx, [rbp+57h+var_B8]
0x1801cad7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801cad82  jmp     loc_1801CACF1
0x1801cad87  mov     [rbp+57h+var_B0], rdi
0x1801cad8b  lea     rcx, [rbp+57h+var_B0]
0x1801cad8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801cad94  lea     rax, [rbp+57h+var_B0]
0x1801cad98  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1801cad9d  mov     r9, r14; struct Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *
0x1801cada0  mov     r8, [rbp+57h+var_B8]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1801cada4  mov     dl, r15b; bool
0x1801cada7  mov     rcx, rsi; this
0x1801cadaa  call    ?CreateWebTokenRequest@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJ_NPEAUIWebAccountProvider@Credentials@Security@Windows@@AEAVUserAuthenticationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@PEAPEAUIWebTokenRequest@Core@Web@29Windows@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::CreateWebTokenRequest(bool,Windows::Security::Credentials::IWebAccountProvider *,Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession &,Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)
0x1801cadaf  mov     ebx, eax
0x1801cadb1  xor     r15d, r15d
0x1801cadb4  test    eax, eax
0x1801cadb6  jns     short loc_1801CADD5
0x1801cadb8  mov     rcx, [rbp+5Fh]; this
0x1801cadbc  mov     r9d, eax; char *
0x1801cadbf  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801cadc6  mov     edx, 0E6h; void *
0x1801cadcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cadd0  jmp     loc_1801CB0DC
0x1801cadd5  mov     [rbp+57h+var_A8], r15
0x1801cadd9  lea     rcx, [rbp+57h+var_A8]
0x1801caddd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801cade2  lea     r9, [rbp+57h+var_A8]; struct Windows::Security::Credentials::IWebAccount **
0x1801cade6  mov     r8, r14; struct Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *
0x1801cade9  mov     rdx, [rbp+57h+var_B8]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1801caded  mov     rcx, rsi; this
0x1801cadf0  call    ?FindConnectedAccount@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJPEAUIWebAccountProvider@Credentials@Security@Windows@@AEAVUserAuthenticationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@PEAPEAUIWebAccount@89Windows@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::FindConnectedAccount(Windows::Security::Credentials::IWebAccountProvider *,Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession &,Windows::Security::Credentials::IWebAccount * *)
0x1801cadf5  mov     ebx, eax
0x1801cadf7  test    eax, eax
0x1801cadf9  jns     short loc_1801CAE18
0x1801cadfb  mov     rcx, [rbp+5Fh]; this
0x1801cadff  mov     r9d, eax; char *
0x1801cae02  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801cae09  mov     edx, 0E9h; void *
0x1801cae0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cae13  jmp     loc_1801CB0D2
0x1801cae18  mov     [rbp+57h+var_98], r15
0x1801cae1c  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r15
0x1801cae20  mov     r9d, 45h ; 'E'; unsigned int
0x1801cae26  lea     r8d, [r9+1]; unsigned int
0x1801cae2a  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1801cae31  lea     rcx, [rbp+57h+string]; hstringHeader
0x1801cae35  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801cae3a  lea     rdx, [rbp+57h+var_98]
0x1801cae3e  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x1801cae42  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x1801cae47  mov     ebx, eax
0x1801cae49  test    eax, eax
0x1801cae4b  jns     short loc_1801CAE6A
0x1801cae4d  mov     rcx, [rbp+5Fh]; this
0x1801cae51  mov     r9d, eax; char *
0x1801cae54  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801cae5b  mov     edx, 0ECh; void *
0x1801cae60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cae65  jmp     loc_1801CB0C8
0x1801cae6a  mov     [rbp+57h+var_90], r15
0x1801cae6e  cmp     [rbp+57h+var_A8], r15
0x1801cae72  jz      short loc_1801CAEF0
0x1801cae74  mov     [rbp+57h+var_80], r15
0x1801cae78  mov     rdi, [rbp+57h+var_98]
0x1801cae7c  mov     rax, [rdi]
0x1801cae7f  mov     rbx, [rax+38h]
0x1801cae83  lea     rcx, [rbp+57h+var_80]
0x1801cae87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801cae8c  lea     r9, [rbp+57h+var_80]
0x1801cae90  mov     r8, [rbp+57h+var_A8]
0x1801cae94  mov     rdx, [rbp+57h+var_B0]
0x1801cae98  mov     rcx, rdi
0x1801cae9b  mov     rax, rbx
0x1801cae9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801caea3  mov     ebx, eax
0x1801caea5  test    eax, eax
0x1801caea7  jns     short loc_1801CAED0
0x1801caea9  mov     edx, 0F3h; void *
0x1801caeae  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801caeb5  mov     r9d, eax; char *
0x1801caeb8  mov     rcx, [rbp+5Fh]; this
0x1801caebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801caec1  nop
0x1801caec2  lea     rcx, [rbp+57h+var_80]
0x1801caec6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801caecb  jmp     loc_1801CB0BE
0x1801caed0  lea     rdx, [rbp+57h+var_90]
0x1801caed4  mov     rcx, [rbp+57h+var_80]
0x1801caed8  call    ??$BlockOnCompletionAndGetResults@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@UIWebTokenRequestResult@23456@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>>,tagCOWAIT_FLAGS,void *)
0x1801caedd  mov     ebx, eax
0x1801caedf  test    eax, eax
0x1801caee1  jns     short loc_1801CAEEA
0x1801caee3  mov     edx, 0F4h
0x1801caee8  jmp     short loc_1801CAEAE
0x1801caeea  lea     rcx, [rbp+57h+var_80]
0x1801caeee  jmp     short loc_1801CAF5E
0x1801caef0  mov     [rbp+57h+var_88], r15
0x1801caef4  mov     rdi, [rbp+57h+var_98]
0x1801caef8  mov     rax, [rdi]
0x1801caefb  mov     rbx, [rax+30h]
0x1801caeff  lea     rcx, [rbp+57h+var_88]
0x1801caf03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801caf08  lea     r8, [rbp+57h+var_88]
0x1801caf0c  mov     rdx, [rbp+57h+var_B0]
0x1801caf10  mov     rcx, rdi
0x1801caf13  mov     rax, rbx
0x1801caf16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801caf1b  mov     ebx, eax
0x1801caf1d  test    eax, eax
0x1801caf1f  jns     short loc_1801CAF40
0x1801caf21  mov     edx, 0FAh; void *
0x1801caf26  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801caf2d  mov     r9d, eax; char *
0x1801caf30  mov     rcx, [rbp+5Fh]; this
0x1801caf34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801caf39  nop
0x1801caf3a  lea     rcx, [rbp+57h+var_88]
0x1801caf3e  jmp     short loc_1801CAEC6
0x1801caf40  lea     rdx, [rbp+57h+var_90]
0x1801caf44  mov     rcx, [rbp+57h+var_88]
0x1801caf48  call    ??$BlockOnCompletionAndGetResults@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@UIWebTokenRequestResult@23456@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>>,tagCOWAIT_FLAGS,void *)
0x1801caf4d  mov     ebx, eax
0x1801caf4f  test    eax, eax
0x1801caf51  jns     short loc_1801CAF5A
0x1801caf53  mov     edx, 0FBh
0x1801caf58  jmp     short loc_1801CAF26
0x1801caf5a  lea     rcx, [rbp+57h+var_88]
0x1801caf5e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801caf63  mov     [rbp+57h+var_A0], r15
0x1801caf67  mov     rax, [rbp+57h+var_90]
0x1801caf6b  test    rax, rax
0x1801caf6e  jz      loc_1801CB092
0x1801caf74  mov     [rbp+57h+var_68], rax
0x1801caf78  mov     [rbp+57h+var_70], r15d
0x1801caf7c  lea     rax, [rbp+57h+var_68]
0x1801caf80  mov     [rbp+57h+string], rax
0x1801caf84  lea     rax, [rbp+57h+var_70]
0x1801caf88  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1801caf8c  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rsi
0x1801caf90  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r14
0x1801caf94  lea     rcx, [rbp+57h+string]
0x1801caf98  call    _lambda_acf6ddb890cc9453d47af966f956de06___operator__
0x1801caf9d  mov     ebx, eax
0x1801caf9f  mov     r8d, eax; int
0x1801cafa2  mov     edx, [rbp+57h+var_70]; unsigned int
0x1801cafa5  mov     rcx, r14; this
0x1801cafa8  call    ?ParseWebTokenRequestResult@UserAuthenticationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@QEAAXKJ@Z; Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::ParseWebTokenRequestResult(ulong,long)
0x1801cafad  test    ebx, ebx
0x1801cafaf  jns     short loc_1801CAFD3
0x1801cafb1  mov     rcx, [rbp+5Fh]; this
0x1801cafb5  mov     r9d, ebx; char *
0x1801cafb8  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801cafbf  mov     edx, 1E2h; void *
0x1801cafc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cafc9  mov     edx, 102h
0x1801cafce  jmp     loc_1801CB09C
0x1801cafd3  lea     rdx, [rbp+57h+var_A0]; struct Microsoft::WRL::Wrappers::HString *
0x1801cafd7  mov     rcx, rsi; this
0x1801cafda  call    ?GetLastAuthenticationToken@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAVHString@Wrappers@WRL@6@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetLastAuthenticationToken(Microsoft::WRL::Wrappers::HString &)
0x1801cafdf  mov     ebx, eax
0x1801cafe1  test    eax, eax
0x1801cafe3  jns     short loc_1801CAFEC
0x1801cafe5  mov     edx, 103h
0x1801cafea  jmp     short loc_1801CB004
0x1801cafec  mov     rdx, r12; newString
0x1801cafef  mov     rcx, [rbp+57h+var_A0]; string
0x1801caff3  call    cs:__imp_WindowsDuplicateString
0x1801caff9  mov     ebx, eax
0x1801caffb  test    eax, eax
  ... truncated ...
```
