# _lambda_acf6ddb890cc9453d47af966f956de06_::operator()

- ea: `0x1801c7354`
- end: `0x1801c77dc`
- name: `_lambda_acf6ddb890cc9453d47af966f956de06_::operator()`
- size: `1160`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1801cab84`

## callees

- `0x180021944`
- `0x180026508`
- `0x1801c7354`
- `0x1801cc204`
- `0x1801cc340`
- `0x1801cd5c4`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c74f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c753e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7687`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c77bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c74f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c753e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7687`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c7755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801c77bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c77a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801c77a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall lambda_acf6ddb890cc9453d47af966f956de06_::operator()(__int64 **a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 *v4; // rdi
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  int v10; // eax
  HSTRING v11; // rdi
  __int64 (__fastcall *v12)(HSTRING, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rdi
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  HSTRING v20; // rdi
  __int64 (__fastcall *v21)(HSTRING, HSTRING *); // rbx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  int AuthenticationToken; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING *); // rbx
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // rdx
  int v34; // eax
  HSTRING v35; // rdi
  __int64 (__fastcall *v36)(HSTRING, HSTRING *); // rbx
  int v37; // eax
  Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *v38; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-20h] BYREF
  __int64 v41; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v42[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HSTRING v44; // [rsp+70h] [rbp+30h] BYREF
  HSTRING v45; // [rsp+78h] [rbp+38h] BYREF
  HSTRING string; // [rsp+80h] [rbp+40h] BYREF
  __int64 v47; // [rsp+88h] [rbp+48h] BYREF

  v2 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)**a1 + 56LL))(**a1, a1[1]);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)v2,
      (int)v40);
    return v3;
  }
  v4 = *a1;
  if ( *(_DWORD *)a1[1] )
  {
    string = 0;
    v29 = *v4;
    v30 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    v31 = v30(v29, &string);
    v3 = v31;
    if ( v31 >= 0 )
    {
      if ( string )
      {
        LODWORD(v44) = 0;
        v34 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 48LL))(string, &v44);
        v3 = v34;
        if ( v34 >= 0 )
        {
          v45 = 0;
          v35 = string;
          v36 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 56LL);
          WindowsDeleteString(0);
          v45 = 0;
          v37 = v36(v35, &v45);
          v3 = v37;
          if ( v37 >= 0 )
          {
            Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::ParseWebTokenRequestError(
              (Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *)a1[3],
              (unsigned int)v44);
            v38 = (Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession *)a1[3];
            StringRawBuffer = WindowsGetStringRawBuffer(v45, 0);
            Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::ParseWebTokenRequestErrorInfo(
              v38,
              StringRawBuffer);
            v3 = (unsigned int)v44;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D6,
              (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
              (const char *)(unsigned int)v37,
              (int)v40);
          }
          WindowsDeleteString(v45);
          v45 = 0;
          goto LABEL_43;
        }
        v32 = (unsigned int)v34;
        v33 = 467;
      }
      else
      {
        v3 = -2147418113;
        v32 = 2147549183LL;
        v33 = 464;
      }
    }
    else
    {
      v32 = (unsigned int)v31;
      v33 = 463;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)v32,
      (int)v40);
LABEL_43:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    return v3;
  }
  v42[0] = 0;
  v5 = *v4;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v5 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
  v7 = v6(v5, v42);
  v3 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)v7,
      (int)v40);
LABEL_28:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
    return v3;
  }
  v45 = 0;
  v8 = v42[0];
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v42[0] + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  v10 = v9(v8, 0, &v45);
  v3 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)v10,
      (int)v40);
LABEL_27:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    goto LABEL_28;
  }
  v40 = 0;
  v11 = v45;
  v12 = *(__int64 (__fastcall **)(HSTRING, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v45 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  v13 = v12(v11, &v40);
  v3 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)v13,
      (int)v40);
LABEL_26:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    goto LABEL_27;
  }
  v47 = 0;
  v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
  v15 = **v40;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  v16 = v15(v14, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v47);
  v3 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)v16,
      (int)v40);
LABEL_25:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    goto LABEL_26;
  }
  v44 = 0;
  v17 = v47;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v47 + 48LL);
  WindowsDeleteString(0);
  v44 = 0;
  v19 = v18(v17, &v44);
  v3 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)v19,
      (int)v40);
LABEL_24:
    WindowsDeleteString(v44);
    v44 = 0;
    goto LABEL_25;
  }
  string = 0;
  v20 = v45;
  v21 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v45 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v22 = v21(v20, &string);
  v3 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)v22,
      (int)v40);
LABEL_23:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_24;
  }
  v41 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 56LL))(v47, &v41);
  v3 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)v23,
      (int)v40);
    v24 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    goto LABEL_23;
  }
  AuthenticationToken = Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::SetLastAuthenticationToken(
                          (Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication *)a1[2],
                          string);
  v3 = AuthenticationToken;
  if ( AuthenticationToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\userauthentication.cpp",
      (const char *)(unsigned int)AuthenticationToken,
      (int)v40);
    v26 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    goto LABEL_23;
  }
  v27 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v44);
  v44 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
  return 0;
}

```

## disassembly

```asm
0x1801c7354  push    rbp
0x1801c7356  push    rbx
0x1801c7357  push    rsi
0x1801c7358  push    rdi
0x1801c7359  push    r14
0x1801c735b  mov     rbp, rsp
0x1801c735e  sub     rsp, 40h
0x1801c7362  mov     rsi, rcx
0x1801c7365  mov     rax, [rcx]
0x1801c7368  mov     rcx, [rax]
0x1801c736b  mov     rax, [rcx]
0x1801c736e  mov     rdx, [rsi+8]
0x1801c7372  mov     rax, [rax+38h]
0x1801c7376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c737b  mov     ebx, eax
0x1801c737d  xor     r14d, r14d
0x1801c7380  test    eax, eax
0x1801c7382  jns     short loc_1801C73A1
0x1801c7384  mov     rcx, [rbp+28h]; this
0x1801c7388  mov     r9d, eax; char *
0x1801c738b  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c7392  mov     edx, 1B1h; void *
0x1801c7397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c739c  jmp     loc_1801C77CF
0x1801c73a1  mov     rdi, [rsi]
0x1801c73a4  mov     rax, [rsi+8]
0x1801c73a8  cmp     [rax], r14d
0x1801c73ab  jnz     loc_1801C76BF
0x1801c73b1  mov     [rbp+var_10], r14
0x1801c73b5  mov     rdi, [rdi]
0x1801c73b8  mov     rax, [rdi]
0x1801c73bb  mov     rbx, [rax+30h]
0x1801c73bf  lea     rcx, [rbp+var_10]
0x1801c73c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c73c8  lea     rdx, [rbp+var_10]
0x1801c73cc  mov     rcx, rdi
0x1801c73cf  mov     rax, rbx
0x1801c73d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c73d7  mov     ebx, eax
0x1801c73d9  test    eax, eax
0x1801c73db  jns     short loc_1801C73FA
0x1801c73dd  mov     rcx, [rbp+28h]; this
0x1801c73e1  mov     r9d, eax; char *
0x1801c73e4  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c73eb  mov     edx, 1B5h; void *
0x1801c73f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c73f5  jmp     loc_1801C764D
0x1801c73fa  mov     [rbp+arg_8], r14
0x1801c73fe  mov     rdi, [rbp+var_10]
0x1801c7402  mov     rax, [rdi]
0x1801c7405  mov     rbx, [rax+30h]
0x1801c7409  lea     rcx, [rbp+arg_8]
0x1801c740d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c7412  lea     r8, [rbp+arg_8]
0x1801c7416  xor     edx, edx
0x1801c7418  mov     rcx, rdi
0x1801c741b  mov     rax, rbx
0x1801c741e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7423  mov     ebx, eax
0x1801c7425  test    eax, eax
0x1801c7427  jns     short loc_1801C7446
0x1801c7429  mov     rcx, [rbp+28h]; this
0x1801c742d  mov     r9d, eax; char *
0x1801c7430  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c7437  mov     edx, 1B8h; void *
0x1801c743c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c7441  jmp     loc_1801C7643
0x1801c7446  mov     [rbp+var_20], r14
0x1801c744a  mov     rdi, [rbp+arg_8]
0x1801c744e  mov     rax, [rdi]
0x1801c7451  mov     rbx, [rax+40h]
0x1801c7455  lea     rcx, [rbp+var_20]
0x1801c7459  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c745e  lea     rdx, [rbp+var_20]
0x1801c7462  mov     rcx, rdi
0x1801c7465  mov     rax, rbx
0x1801c7468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c746d  mov     ebx, eax
0x1801c746f  test    eax, eax
0x1801c7471  jns     short loc_1801C7490
0x1801c7473  mov     rcx, [rbp+28h]; this
0x1801c7477  mov     r9d, eax; char *
0x1801c747a  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c7481  mov     edx, 1BBh; void *
0x1801c7486  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c748b  jmp     loc_1801C7639
0x1801c7490  mov     [rbp+arg_18], r14
0x1801c7494  mov     rbx, [rbp+var_20]
0x1801c7498  mov     rax, [rbx]
0x1801c749b  mov     rdi, [rax]
0x1801c749e  lea     rcx, [rbp+arg_18]
0x1801c74a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c74a7  lea     r8, [rbp+arg_18]
0x1801c74ab  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x1801c74b2  mov     rcx, rbx
0x1801c74b5  mov     rax, rdi
0x1801c74b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c74bd  mov     ebx, eax
0x1801c74bf  test    eax, eax
0x1801c74c1  jns     short loc_1801C74E0
0x1801c74c3  mov     rcx, [rbp+28h]; this
0x1801c74c7  mov     r9d, eax; char *
0x1801c74ca  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c74d1  mov     edx, 1BEh; void *
0x1801c74d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c74db  jmp     loc_1801C762F
0x1801c74e0  mov     [rbp+arg_0], r14
0x1801c74e4  mov     rdi, [rbp+arg_18]
0x1801c74e8  mov     rax, [rdi]
0x1801c74eb  mov     rbx, [rax+30h]
0x1801c74ef  xor     ecx, ecx; string
0x1801c74f1  call    cs:__imp_WindowsDeleteString
0x1801c74f7  mov     [rbp+arg_0], r14
0x1801c74fb  lea     rdx, [rbp+arg_0]
0x1801c74ff  mov     rcx, rdi
0x1801c7502  mov     rax, rbx
0x1801c7505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c750a  mov     ebx, eax
0x1801c750c  test    eax, eax
0x1801c750e  jns     short loc_1801C752D
0x1801c7510  mov     rcx, [rbp+28h]; this
0x1801c7514  mov     r9d, eax; char *
0x1801c7517  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c751e  mov     edx, 1C1h; void *
0x1801c7523  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c7528  jmp     loc_1801C7621
0x1801c752d  mov     [rbp+string], r14
0x1801c7531  mov     rdi, [rbp+arg_8]
0x1801c7535  mov     rax, [rdi]
0x1801c7538  mov     rbx, [rax+30h]
0x1801c753c  xor     ecx, ecx; string
0x1801c753e  call    cs:__imp_WindowsDeleteString
0x1801c7544  mov     [rbp+string], r14
0x1801c7548  lea     rdx, [rbp+string]
0x1801c754c  mov     rcx, rdi
0x1801c754f  mov     rax, rbx
0x1801c7552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7557  mov     ebx, eax
0x1801c7559  test    eax, eax
0x1801c755b  jns     short loc_1801C757A
0x1801c755d  mov     rcx, [rbp+28h]; this
0x1801c7561  mov     r9d, eax; char *
0x1801c7564  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c756b  mov     edx, 1C4h; void *
0x1801c7570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c7575  jmp     loc_1801C7613
0x1801c757a  mov     [rbp+var_18], r14
0x1801c757e  mov     rcx, [rbp+arg_18]
0x1801c7582  mov     rax, [rcx]
0x1801c7585  lea     rdx, [rbp+var_18]
0x1801c7589  mov     rax, [rax+38h]
0x1801c758d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7592  mov     ebx, eax
0x1801c7594  test    eax, eax
0x1801c7596  jns     short loc_1801C75CD
0x1801c7598  mov     rcx, [rbp+28h]; this
0x1801c759c  mov     r9d, eax; char *
0x1801c759f  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c75a6  mov     edx, 1C7h; void *
0x1801c75ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c75b0  nop
0x1801c75b1  mov     rcx, [rbp+var_18]
0x1801c75b5  test    rcx, rcx
0x1801c75b8  jz      short loc_1801C75CB
0x1801c75ba  mov     [rbp+var_18], r14
0x1801c75be  mov     rax, [rcx]
0x1801c75c1  mov     rax, [rax+10h]
0x1801c75c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c75ca  nop
0x1801c75cb  jmp     short loc_1801C7613
0x1801c75cd  mov     rdx, [rbp+string]; HSTRING
0x1801c75d1  mov     rcx, [rsi+10h]; this
0x1801c75d5  call    ?SetLastAuthenticationToken@UserAuthentication@Authentication@Client@LanguageUnderstanding@Bing@Microsoft@@AEAAJPEAUHSTRING__@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::Authentication::UserAuthentication::SetLastAuthenticationToken(HSTRING__ *)
0x1801c75da  mov     ebx, eax
0x1801c75dc  test    eax, eax
0x1801c75de  jns     short loc_1801C765B
0x1801c75e0  mov     rcx, [rbp+28h]; this
0x1801c75e4  mov     r9d, eax; char *
0x1801c75e7  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c75ee  mov     edx, 1CAh; void *
0x1801c75f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c75f8  nop
0x1801c75f9  mov     rcx, [rbp+var_18]
0x1801c75fd  test    rcx, rcx
0x1801c7600  jz      short loc_1801C7613
0x1801c7602  mov     [rbp+var_18], r14
0x1801c7606  mov     rax, [rcx]
0x1801c7609  mov     rax, [rax+10h]
0x1801c760d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7612  nop
0x1801c7613  mov     rcx, [rbp+string]; string
0x1801c7617  call    cs:__imp_WindowsDeleteString
0x1801c761d  mov     [rbp+string], r14
0x1801c7621  mov     rcx, [rbp+arg_0]; string
0x1801c7625  call    cs:__imp_WindowsDeleteString
0x1801c762b  mov     [rbp+arg_0], r14
0x1801c762f  lea     rcx, [rbp+arg_18]
0x1801c7633  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c7638  nop
0x1801c7639  lea     rcx, [rbp+var_20]
0x1801c763d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c7642  nop
0x1801c7643  lea     rcx, [rbp+arg_8]
0x1801c7647  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c764c  nop
0x1801c764d  lea     rcx, [rbp+var_10]
0x1801c7651  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c7656  jmp     loc_1801C77CF
0x1801c765b  mov     rcx, [rbp+var_18]
0x1801c765f  test    rcx, rcx
0x1801c7662  jz      short loc_1801C7675
0x1801c7664  mov     [rbp+var_18], r14
0x1801c7668  mov     rax, [rcx]
0x1801c766b  mov     rax, [rax+10h]
0x1801c766f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7674  nop
0x1801c7675  mov     rcx, [rbp+string]; string
0x1801c7679  call    cs:__imp_WindowsDeleteString
0x1801c767f  mov     [rbp+string], r14
0x1801c7683  mov     rcx, [rbp+arg_0]; string
0x1801c7687  call    cs:__imp_WindowsDeleteString
0x1801c768d  mov     [rbp+arg_0], r14
0x1801c7691  lea     rcx, [rbp+arg_18]
0x1801c7695  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c769a  nop
0x1801c769b  lea     rcx, [rbp+var_20]
0x1801c769f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c76a4  nop
0x1801c76a5  lea     rcx, [rbp+arg_8]
0x1801c76a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c76ae  nop
0x1801c76af  lea     rcx, [rbp+var_10]
0x1801c76b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c76b8  xor     eax, eax
0x1801c76ba  jmp     loc_1801C77D1
0x1801c76bf  mov     [rbp+string], r14
0x1801c76c3  mov     rdi, [rdi]
0x1801c76c6  mov     rax, [rdi]
0x1801c76c9  mov     rbx, [rax+40h]
0x1801c76cd  lea     rcx, [rbp+string]
0x1801c76d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c76d6  lea     rdx, [rbp+string]
0x1801c76da  mov     rcx, rdi
0x1801c76dd  mov     rax, rbx
0x1801c76e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c76e5  mov     ebx, eax
0x1801c76e7  test    eax, eax
0x1801c76e9  jns     short loc_1801C76F5
0x1801c76eb  mov     r9d, eax
0x1801c76ee  mov     edx, 1CFh
0x1801c76f3  jmp     short loc_1801C770B
0x1801c76f5  mov     rcx, [rbp+string]
0x1801c76f9  test    rcx, rcx
0x1801c76fc  jnz     short loc_1801C7720
0x1801c76fe  mov     ebx, 8000FFFFh
0x1801c7703  mov     r9d, ebx; char *
0x1801c7706  mov     edx, 1D0h; void *
0x1801c770b  mov     rcx, [rbp+28h]; this
0x1801c770f  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c7716  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c771b  jmp     loc_1801C77C6
0x1801c7720  mov     dword ptr [rbp+arg_0], r14d
0x1801c7724  mov     rax, [rcx]
0x1801c7727  lea     rdx, [rbp+arg_0]
0x1801c772b  mov     rax, [rax+30h]
0x1801c772f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7734  mov     ebx, eax
0x1801c7736  test    eax, eax
0x1801c7738  jns     short loc_1801C7744
0x1801c773a  mov     r9d, eax
0x1801c773d  mov     edx, 1D3h
0x1801c7742  jmp     short loc_1801C770B
0x1801c7744  mov     [rbp+arg_8], r14
0x1801c7748  mov     rdi, [rbp+string]
0x1801c774c  mov     rax, [rdi]
0x1801c774f  mov     rbx, [rax+38h]
0x1801c7753  xor     ecx, ecx; string
0x1801c7755  call    cs:__imp_WindowsDeleteString
0x1801c775b  mov     [rbp+arg_8], r14
0x1801c775f  lea     rdx, [rbp+arg_8]
0x1801c7763  mov     rcx, rdi
0x1801c7766  mov     rax, rbx
0x1801c7769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c776e  mov     ebx, eax
0x1801c7770  test    eax, eax
0x1801c7772  jns     short loc_1801C778E
0x1801c7774  mov     rcx, [rbp+28h]; this
0x1801c7778  mov     r9d, eax; char *
0x1801c777b  lea     r8, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801c7782  mov     edx, 1D6h; void *
0x1801c7787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c778c  jmp     short loc_1801C77B8
0x1801c778e  mov     edx, dword ptr [rbp+arg_0]; unsigned int
0x1801c7791  mov     rcx, [rsi+18h]; this
0x1801c7795  call    ?ParseWebTokenRequestError@UserAuthenticationSession@RemoteNaturalLanguageTelemetry@Internal@Speech@Media@Windows@@QEAAXK@Z; Windows::Media::Speech::Internal::RemoteNaturalLanguageTelemetry::UserAuthenticationSession::ParseWebTokenRequestError(ulong)
0x1801c779a  mov     rbx, [rsi+18h]
0x1801c779e  xor     edx, edx; length
0x1801c77a0  mov     rcx, [rbp+arg_8]; string
0x1801c77a4  call    cs:__imp_WindowsGetStringRawBuffer
0x1801c77aa  mov     rdx, rax; unsigned __int16 *
  ... truncated ...
```
