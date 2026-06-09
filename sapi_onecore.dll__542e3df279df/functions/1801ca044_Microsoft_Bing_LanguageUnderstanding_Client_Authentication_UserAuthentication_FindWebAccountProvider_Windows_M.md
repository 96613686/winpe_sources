# Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::FindWebAccountProvider(Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession &,Windows::Security::Credentials::IWebAccountProvider * *,Windows::System::IUser *)

- ea: `0x1801ca044`
- end: `0x1801ca3be`
- name: `?FindWebAccountProvider@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAVUserAuthenticationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@PEAPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAUIUser@System@Windows@@@Z`
- size: `890`
- prototype: `__int64 __fastcall(Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *__hidden this, struct Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *, struct Windows::Security::Credentials::IWebAccountProvider **, struct Windows::System::IUser *)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801c6fa4`
- `0x1801cab84`

## callees

- `0x18001ce70`
- `0x180021944`
- `0x180026508`
- `0x18004b1a8`
- `0x18006a378`
- `0x18006b414`
- `0x180079e30`
- `0x1800be48c`
- `0x1801c4638`
- `0x1801c5590`
- `0x1801c55cc`
- `0x1801c90a8`
- `0x1801c969c`
- `0x1801ca044`
- `0x1801cd614`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ca0f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ca190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ca1d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ca0f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ca190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ca1d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca0d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca13c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca1af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca0d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca13c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca1af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca388`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ca108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ca201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ca23c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ca108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ca201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ca23c`

## string_xrefs

- `0x1801ca08b`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::FindWebAccountProvider(
        Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *this,
        struct Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *a2,
        struct Windows::Security::Credentials::IWebAccountProvider **a3,
        struct Windows::System::IUser *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // rax
  int LastConsumerAuthority; // eax
  __int64 v12; // rdx
  bool v13; // al
  const unsigned __int16 *v14; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, _QWORD, HSTRING, struct Windows::System::IUser *); // rdi
  HSTRING v20; // rbx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, _QWORD, HSTRING, __int64 *); // rdi
  HSTRING v26; // rbx
  __int64 v27; // rax
  __int64 *v29; // [rsp+20h] [rbp-60h]
  bool v30; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  __int64 v32; // [rsp+40h] [rbp-40h] BYREF
  __int64 v33; // [rsp+48h] [rbp-38h] BYREF
  __int64 v34; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v36; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  *a3 = 0;
  v34 = 0;
  v36 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
         v36,
         &v34);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v30 = 0;
    WindowsDeleteString(0);
    string = 0;
    if ( (int)Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetIdentityPropertyValue(
                this,
                2,
                &string) < 0
      || WindowsIsStringEmpty(string) )
    {
      LastConsumerAuthority = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetLastConsumerAuthority(
                                this,
                                (struct Microsoft::WRL::Wrappers::HString *)&string);
      v9 = LastConsumerAuthority;
      if ( LastConsumerAuthority < 0 )
      {
        v12 = 320;
        goto LABEL_7;
      }
      if ( !WindowsIsStringEmpty(string) || *((_BYTE *)this + 189) )
      {
LABEL_24:
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::ConsumerAuthority(
          a2,
          StringRawBuffer);
        v32 = 0;
        if ( a4 )
        {
          v33 = 0;
          v16 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>::As<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics2>(
                  &v34,
                  &v33);
          v9 = v16;
          if ( v16 < 0 )
          {
            v17 = 342;
LABEL_27:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v17,
              (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
              (const char *)(unsigned int)v16,
              (int)v29);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
LABEL_28:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
            goto LABEL_8;
          }
          v18 = v33;
          v19 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, struct Windows::System::IUser *))(*(_QWORD *)v33 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          v20 = string;
          v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_18029FB10);
          v29 = &v32;
          v16 = v19(v18, *(_QWORD *)(v21 + 24), v20, a4);
          v9 = v16;
          if ( v16 < 0 )
          {
            v17 = 348;
            goto LABEL_27;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        }
        else
        {
          v24 = v34;
          v25 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v34 + 96LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          v26 = string;
          v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_18029FB10);
          v22 = v25(v24, *(_QWORD *)(v27 + 24), v26, &v32);
          v9 = v22;
          if ( v22 < 0 )
          {
            v23 = 355;
LABEL_36:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v23,
              (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
              (const char *)(unsigned int)v22,
              (int)v29);
            goto LABEL_28;
          }
        }
        v22 = BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>,Windows::Security::Credentials::IWebAccountProvider *>(
                v32,
                a3);
        v9 = v22;
        if ( v22 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          WindowsDeleteString(string);
          v9 = 0;
          goto LABEL_38;
        }
        v23 = 358;
        goto LABEL_36;
      }
      WindowsDeleteString(string);
      string = 0;
      if ( Microsoft::Authentication::Validation::FindAuthorityForUser(a4, &v30, &string) < 0
        || WindowsIsStringEmpty(string) )
      {
        LastConsumerAuthority = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)&string);
        v9 = LastConsumerAuthority;
        if ( LastConsumerAuthority < 0 )
        {
          v12 = 328;
          goto LABEL_7;
        }
      }
      v14 = WindowsGetStringRawBuffer(string, 0);
      LastConsumerAuthority = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::SetLastConsumerAuthority(
                                this,
                                v14);
      v9 = LastConsumerAuthority;
      if ( LastConsumerAuthority < 0 )
      {
        v12 = 330;
        goto LABEL_7;
      }
      v13 = !v30;
    }
    else
    {
      v10 = WindowsGetStringRawBuffer(string, 0);
      LastConsumerAuthority = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::SetLastConsumerAuthority(
                                this,
                                v10);
      v9 = LastConsumerAuthority;
      if ( LastConsumerAuthority < 0 )
      {
        v12 = 308;
LABEL_7:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
          (const char *)(unsigned int)LastConsumerAuthority,
          (int)v29);
LABEL_8:
        WindowsDeleteString(string);
LABEL_38:
        string = 0;
        goto LABEL_39;
      }
      if ( *((_BYTE *)this + 189)
        || (Microsoft::Authentication::Validation::FindAuthorityForUser(a4, &v30, 0), v13 = 0, !v30) )
      {
        v13 = 1;
      }
    }
    *((_BYTE *)this + 188) = v13;
    *((_BYTE *)this + 189) = 1;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12B,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
    (const char *)(unsigned int)v8,
    (int)v29);
LABEL_39:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  return v9;
}

```

## disassembly

```asm
0x1801ca044  push    rbp
0x1801ca046  push    rbx
0x1801ca047  push    rsi
0x1801ca048  push    rdi
0x1801ca049  push    r12
0x1801ca04b  push    r14
0x1801ca04d  push    r15
0x1801ca04f  mov     rbp, rsp
0x1801ca052  sub     rsp, 80h
0x1801ca059  mov     rax, cs:__security_cookie
0x1801ca060  xor     rax, rsp
0x1801ca063  mov     [rbp+var_8], rax
0x1801ca067  mov     r14, r9
0x1801ca06a  mov     r15, r8
0x1801ca06d  mov     rsi, rdx
0x1801ca070  mov     rdi, rcx
0x1801ca073  xor     r12d, r12d
0x1801ca076  mov     [r8], r12
0x1801ca079  mov     [rbp+var_30], r12
0x1801ca07d  mov     [rbp+var_10], r12
0x1801ca081  lea     r9d, [r12+45h]; unsigned int
0x1801ca086  lea     r8d, [r12+46h]; unsigned int
0x1801ca08b  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1801ca092  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801ca096  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801ca09b  lea     rdx, [rbp+var_30]
0x1801ca09f  mov     rcx, [rbp+var_10]
0x1801ca0a3  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x1801ca0a8  mov     ebx, eax
0x1801ca0aa  test    eax, eax
0x1801ca0ac  jns     short loc_1801CA0CB
0x1801ca0ae  mov     rcx, [rbp+38h]; this
0x1801ca0b2  mov     r9d, eax; char *
0x1801ca0b5  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801ca0bc  mov     edx, 12Bh; void *
0x1801ca0c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ca0c6  jmp     loc_1801CA395
0x1801ca0cb  mov     [rbp+string], r12
0x1801ca0cf  mov     [rbp+var_50], r12b
0x1801ca0d3  xor     ecx, ecx; string
0x1801ca0d5  call    cs:__imp_WindowsDeleteString
0x1801ca0db  mov     [rbp+string], r12
0x1801ca0df  lea     r8, [rbp+string]
0x1801ca0e3  mov     edx, 2
0x1801ca0e8  mov     rcx, rdi
0x1801ca0eb  call    ?GetIdentityPropertyValue@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@QEAAJW4IdentityProp@23456@PEAPEAUHSTRING__@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetIdentityPropertyValue(Microsoft::Bing::LanguageUnderstanding::Client::Authentication::IdentityProp,HSTRING__ * *)
0x1801ca0f0  test    eax, eax
0x1801ca0f2  js      short loc_1801CA173
0x1801ca0f4  mov     rcx, [rbp+string]; string
0x1801ca0f8  call    cs:__imp_WindowsIsStringEmpty
0x1801ca0fe  test    eax, eax
0x1801ca100  jnz     short loc_1801CA173
0x1801ca102  xor     edx, edx; length
0x1801ca104  mov     rcx, [rbp+string]; string
0x1801ca108  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ca10e  mov     rdx, rax; unsigned __int16 *
0x1801ca111  mov     rcx, rdi; this
0x1801ca114  call    ?SetLastConsumerAuthority@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJPEBG@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::SetLastConsumerAuthority(ushort const *)
0x1801ca119  mov     ebx, eax
0x1801ca11b  test    eax, eax
0x1801ca11d  jns     short loc_1801CA147
0x1801ca11f  mov     edx, 134h; void *
0x1801ca124  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801ca12b  mov     r9d, eax; char *
0x1801ca12e  mov     rcx, [rbp+38h]; this
0x1801ca132  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ca137  nop
0x1801ca138  mov     rcx, [rbp+string]; string
0x1801ca13c  call    cs:__imp_WindowsDeleteString
0x1801ca142  jmp     loc_1801CA391
0x1801ca147  cmp     [rdi+0BDh], r12b
0x1801ca14e  jnz     short loc_1801CA16C
0x1801ca150  xor     r8d, r8d; HSTRING *
0x1801ca153  lea     rdx, [rbp+var_50]; bool *
0x1801ca157  mov     rcx, r14; struct Windows::System::IUser *
0x1801ca15a  call    ?FindAuthorityForUser@Validation@Authentication@Microsoft@@SAJPEAUIUser@System@Windows@@PEA_NPEAPEAUHSTRING__@@@Z; Microsoft::Authentication::Validation::FindAuthorityForUser(Windows::System::IUser *,bool *,HSTRING__ * *)
0x1801ca15f  cmp     [rbp+var_50], r12b
0x1801ca163  mov     al, r12b
0x1801ca166  jnz     loc_1801CA229
0x1801ca16c  mov     al, 1
0x1801ca16e  jmp     loc_1801CA229
0x1801ca173  lea     rdx, [rbp+string]; struct Microsoft::WRL::Wrappers::HString *
0x1801ca177  mov     rcx, rdi; this
0x1801ca17a  call    ?GetLastConsumerAuthority@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJAEAVHString@Wrappers@WRL@6@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::GetLastConsumerAuthority(Microsoft::WRL::Wrappers::HString &)
0x1801ca17f  mov     ebx, eax
0x1801ca181  test    eax, eax
0x1801ca183  jns     short loc_1801CA18C
0x1801ca185  mov     edx, 140h
0x1801ca18a  jmp     short loc_1801CA124
0x1801ca18c  mov     rcx, [rbp+string]; string
0x1801ca190  call    cs:__imp_WindowsIsStringEmpty
0x1801ca196  test    eax, eax
0x1801ca198  jz      loc_1801CA236
0x1801ca19e  cmp     [rdi+0BDh], r12b
0x1801ca1a5  jnz     loc_1801CA236
0x1801ca1ab  mov     rcx, [rbp+string]; string
0x1801ca1af  call    cs:__imp_WindowsDeleteString
0x1801ca1b5  mov     [rbp+string], r12
0x1801ca1b9  lea     r8, [rbp+string]; HSTRING *
0x1801ca1bd  lea     rdx, [rbp+var_50]; bool *
0x1801ca1c1  mov     rcx, r14; struct Windows::System::IUser *
0x1801ca1c4  call    ?FindAuthorityForUser@Validation@Authentication@Microsoft@@SAJPEAUIUser@System@Windows@@PEA_NPEAPEAUHSTRING__@@@Z; Microsoft::Authentication::Validation::FindAuthorityForUser(Windows::System::IUser *,bool *,HSTRING__ * *)
0x1801ca1c9  test    eax, eax
0x1801ca1cb  js      short loc_1801CA1DB
0x1801ca1cd  mov     rcx, [rbp+string]; string
0x1801ca1d1  call    cs:__imp_WindowsIsStringEmpty
0x1801ca1d7  test    eax, eax
0x1801ca1d9  jz      short loc_1801CA1FB
0x1801ca1db  lea     rdx, off_18029FB18; "consumers"
0x1801ca1e2  lea     rcx, [rbp+string]; this
0x1801ca1e6  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1801ca1eb  mov     ebx, eax
0x1801ca1ed  test    eax, eax
0x1801ca1ef  jns     short loc_1801CA1FB
0x1801ca1f1  mov     edx, 148h
0x1801ca1f6  jmp     loc_1801CA124
0x1801ca1fb  xor     edx, edx; length
0x1801ca1fd  mov     rcx, [rbp+string]; string
0x1801ca201  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ca207  mov     rdx, rax; unsigned __int16 *
0x1801ca20a  mov     rcx, rdi; this
0x1801ca20d  call    ?SetLastConsumerAuthority@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJPEBG@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::SetLastConsumerAuthority(ushort const *)
0x1801ca212  mov     ebx, eax
0x1801ca214  test    eax, eax
0x1801ca216  jns     short loc_1801CA222
0x1801ca218  mov     edx, 14Ah
0x1801ca21d  jmp     loc_1801CA124
0x1801ca222  cmp     [rbp+var_50], r12b
0x1801ca226  setz    al
0x1801ca229  mov     [rdi+0BCh], al
0x1801ca22f  mov     byte ptr [rdi+0BDh], 1
0x1801ca236  xor     edx, edx; length
0x1801ca238  mov     rcx, [rbp+string]; string
0x1801ca23c  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ca242  mov     rdx, rax; unsigned __int16 *
0x1801ca245  mov     rcx, rsi; this
0x1801ca248  call    ?ConsumerAuthority@UserAuthenticationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@QEAAXPEBG@Z; Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::ConsumerAuthority(ushort const *)
0x1801ca24d  mov     [rbp+var_40], r12
0x1801ca251  test    r14, r14
0x1801ca254  jz      loc_1801CA318
0x1801ca25a  mov     [rbp+var_38], r12
0x1801ca25e  lea     rdx, [rbp+var_38]
0x1801ca262  lea     rcx, [rbp+var_30]
0x1801ca266  call    ??$As@UIWebAuthenticationCoreManagerStatics2@Core@Web@Authentication@Security@Windows@@@?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics2@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>::As<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics2>>)
0x1801ca26b  mov     ebx, eax
0x1801ca26d  test    eax, eax
0x1801ca26f  jns     short loc_1801CA2A2
0x1801ca271  mov     edx, 156h; void *
0x1801ca276  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801ca27d  mov     r9d, eax; char *
0x1801ca280  mov     rcx, [rbp+38h]; this
0x1801ca284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ca289  nop
0x1801ca28a  lea     rcx, [rbp+var_38]
0x1801ca28e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ca293  nop
0x1801ca294  lea     rcx, [rbp+var_40]
0x1801ca298  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ca29d  jmp     loc_1801CA138
0x1801ca2a2  mov     rsi, [rbp+var_38]
0x1801ca2a6  mov     rax, [rsi]
0x1801ca2a9  mov     rdi, [rax+30h]
0x1801ca2ad  lea     rcx, [rbp+var_40]
0x1801ca2b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ca2b6  mov     rbx, [rbp+string]
0x1801ca2ba  lea     rdx, off_18029FB10; "https://login.microsoft.com"
0x1801ca2c1  lea     rcx, [rbp+hstringHeader]
0x1801ca2c5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801ca2ca  nop
0x1801ca2cb  lea     rcx, [rbp+var_40]
0x1801ca2cf  mov     [rsp+80h+var_60], rcx
0x1801ca2d4  mov     r9, r14
0x1801ca2d7  mov     r8, rbx
0x1801ca2da  mov     rdx, [rax+18h]
0x1801ca2de  mov     rcx, rsi
0x1801ca2e1  mov     rax, rdi
0x1801ca2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ca2e9  mov     ebx, eax
0x1801ca2eb  test    eax, eax
0x1801ca2ed  jns     short loc_1801CA2F6
0x1801ca2ef  mov     edx, 15Ch
0x1801ca2f4  jmp     short loc_1801CA276
0x1801ca2f6  lea     rcx, [rbp+var_38]
0x1801ca2fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ca2ff  mov     rdx, r15
0x1801ca302  mov     rcx, [rbp+var_40]
0x1801ca306  call    ??$BlockOnCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@PEAUIWebAccountProvider@Credentials@Security@3@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@PEAPEAUIWebAccountProvider@Credentials@Security@2@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>,Windows::Security::Credentials::IWebAccountProvider *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Windows::Security::Credentials::IWebAccountProvider * *,tagCOWAIT_FLAGS,void *)
0x1801ca30b  mov     ebx, eax
0x1801ca30d  test    eax, eax
0x1801ca30f  jns     short loc_1801CA37A
0x1801ca311  mov     edx, 166h
0x1801ca316  jmp     short loc_1801CA362
0x1801ca318  mov     rsi, [rbp+var_30]
0x1801ca31c  mov     rax, [rsi]
0x1801ca31f  mov     rdi, [rax+60h]
0x1801ca323  lea     rcx, [rbp+var_40]
0x1801ca327  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ca32c  mov     rbx, [rbp+string]
0x1801ca330  lea     rdx, off_18029FB10; "https://login.microsoft.com"
0x1801ca337  lea     rcx, [rbp+hstringHeader]
0x1801ca33b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801ca340  nop
0x1801ca341  lea     r9, [rbp+var_40]
0x1801ca345  mov     r8, rbx
0x1801ca348  mov     rdx, [rax+18h]
0x1801ca34c  mov     rcx, rsi
0x1801ca34f  mov     rax, rdi
0x1801ca352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ca357  mov     ebx, eax
0x1801ca359  test    eax, eax
0x1801ca35b  jns     short loc_1801CA2FF
0x1801ca35d  mov     edx, 163h; void *
0x1801ca362  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801ca369  mov     r9d, eax; char *
0x1801ca36c  mov     rcx, [rbp+38h]; this
0x1801ca370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ca375  jmp     loc_1801CA294
0x1801ca37a  lea     rcx, [rbp+var_40]
0x1801ca37e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ca383  nop
0x1801ca384  mov     rcx, [rbp+string]; string
0x1801ca388  call    cs:__imp_WindowsDeleteString
0x1801ca38e  mov     ebx, r12d
0x1801ca391  mov     [rbp+string], r12
0x1801ca395  lea     rcx, [rbp+var_30]
0x1801ca399  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ca39e  mov     eax, ebx
0x1801ca3a0  mov     rcx, [rbp+var_8]
0x1801ca3a4  xor     rcx, rsp; StackCookie
0x1801ca3a7  call    __security_check_cookie
0x1801ca3ac  add     rsp, 80h
0x1801ca3b3  pop     r15
0x1801ca3b5  pop     r14
0x1801ca3b7  pop     r12
0x1801ca3b9  pop     rdi
0x1801ca3ba  pop     rsi
0x1801ca3bb  pop     rbx
0x1801ca3bc  pop     rbp
0x1801ca3bd  retn
```
