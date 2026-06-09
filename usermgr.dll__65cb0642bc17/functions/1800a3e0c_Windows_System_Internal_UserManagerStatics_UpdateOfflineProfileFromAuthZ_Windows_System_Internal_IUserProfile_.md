# Windows::System::Internal::UserManagerStatics::UpdateOfflineProfileFromAuthZ(Windows::System::Internal::IUserProfile *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x1800a3e0c`
- end: `0x1800a4491`
- name: `?UpdateOfflineProfileFromAuthZ@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUIUserProfile@234@PEAUIPropertySet@Collections@Foundation@4@@Z`
- size: `1669`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this, struct Windows::System::Internal::IUserProfile *, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18008d234`
- `0x18009ac9c`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x1800181f0`
- `0x180024828`
- `0x18003329c`
- `0x180041bb0`
- `0x18004ba28`
- `0x18004fc2c`
- `0x180050c38`
- `0x1800610f8`
- `0x1800a3e0c`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3f4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3fec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4198`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a424d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a43d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a43e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a43f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a441f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a442d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3f4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3fec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4198`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a424d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a43d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a43e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a43f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a441f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a442d`

## string_xrefs

- `0x1800a3ec8`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::System::Internal::UserManagerStatics::UpdateOfflineProfileFromAuthZ(
        Windows::System::Internal::UserManagerStatics *this,
        struct Windows::System::Internal::IUserProfile *a2,
        struct Windows::Foundation::Collections::IPropertySet *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(struct Windows::System::Internal::IUserProfile *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  HSTRING v10; // rbx
  HSTRING v11; // rbx
  HSTRING v12; // rbx
  HSTRING v13; // rbx
  HSTRING v14; // rbx
  HSTRING v15; // rbx
  HSTRING v16; // rbx
  int v18; // [rsp+20h] [rbp-89h] BYREF
  __int64 v19; // [rsp+28h] [rbp-81h] BYREF
  __int64 v20; // [rsp+30h] [rbp-79h] BYREF
  HSTRING v21; // [rsp+38h] [rbp-71h] BYREF
  HSTRING v22; // [rsp+40h] [rbp-69h] BYREF
  HSTRING v23; // [rsp+48h] [rbp-61h] BYREF
  HSTRING newString; // [rsp+50h] [rbp-59h] BYREF
  HSTRING v25; // [rsp+58h] [rbp-51h] BYREF
  HSTRING v26; // [rsp+60h] [rbp-49h] BYREF
  HSTRING string; // [rsp+68h] [rbp-41h] BYREF
  unsigned int v28; // [rsp+70h] [rbp-39h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp-31h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64); // [rsp+80h] [rbp-29h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // [rsp+88h] [rbp-21h] BYREF
  HSTRING v32; // [rsp+90h] [rbp-19h] BYREF
  __int64 v33; // [rsp+98h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v35; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v31 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v31);
  v30 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v30);
  v33 = 0;
  v29 = 0;
  v20 = 0;
  v19 = 0;
  string = 0;
  v21 = 0;
  newString = 0;
  v23 = 0;
  v22 = 0;
  v26 = 0;
  v25 = 0;
  LOBYTE(v18) = 0;
  v28 = 0;
  if ( !a3 )
    goto LABEL_46;
  v6 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
         &v30,
         (__int64)&v20);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::Implementation::IUserProfileInternal>(
           &v31,
           (__int64)&v33);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4194;
      goto LABEL_6;
    }
    v6 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::IUserProfile *, unsigned int *))(*(_QWORD *)a2 + 48LL))(
           a2,
           &v28);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4196;
      goto LABEL_6;
    }
    v9 = *(__int64 (__fastcall **)(struct Windows::System::Internal::IUserProfile *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)a2 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    v6 = v9(a2, &v29);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4197;
      goto LABEL_6;
    }
    v6 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v29,
           (__int64)&v19);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4199;
      goto LABEL_6;
    }
    WindowsDeleteString(string);
    string = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
    v6 = Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(v20, v35, (__int64)&string);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4201;
      goto LABEL_6;
    }
    WindowsDeleteString(v21);
    v21 = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
    v6 = Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(v20, v35, (__int64)&v21);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4202;
      goto LABEL_6;
    }
    WindowsDeleteString(v26);
    v26 = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
    v6 = Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(v20, v35, (__int64)&v26);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4203;
      goto LABEL_6;
    }
    WindowsDeleteString(v25);
    v25 = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserData", 9u, 8u);
    v6 = Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(v20, v35, (__int64)&v25);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4204;
      goto LABEL_6;
    }
    v10 = string;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
    v6 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
           v19,
           v35,
           (__int64)v10,
           (__int64)&v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4205;
      goto LABEL_6;
    }
    v11 = v21;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
    v6 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
           v19,
           v35,
           (__int64)v11,
           (__int64)&v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4206;
      goto LABEL_6;
    }
    v12 = v26;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
    v6 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
           v19,
           v35,
           (__int64)v12,
           (__int64)&v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4207;
      goto LABEL_6;
    }
    v13 = v25;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserData", 9u, 8u);
    v6 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
           v19,
           v35,
           (__int64)v13,
           (__int64)&v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4208;
      goto LABEL_6;
    }
    WindowsDeleteString(newString);
    newString = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertag", 0xFu, 0xEu);
    if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
                v20,
                v35,
                (__int64)&newString) < 0 )
    {
      v32 = v21;
      v6 = Microsoft::WRL::Wrappers::HString::Set(&newString, &v32);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 4213;
        goto LABEL_6;
      }
    }
    v14 = newString;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertag", 0xFu, 0xEu);
    v6 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
           v19,
           v35,
           (__int64)v14,
           (__int64)&v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4215;
      goto LABEL_6;
    }
    WindowsDeleteString(v22);
    v22 = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UniqueModernGamertag", 0x15u, 0x14u);
    if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(v20, v35, (__int64)&v22) < 0 )
    {
      v32 = v21;
      v6 = Microsoft::WRL::Wrappers::HString::Set(&v22, &v32);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 4219;
        goto LABEL_6;
      }
    }
    v15 = v22;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UniqueModernGamertag", 0x15u, 0x14u);
    v6 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
           v19,
           v35,
           (__int64)v15,
           (__int64)&v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4221;
      goto LABEL_6;
    }
    WindowsDeleteString(v23);
    v23 = 0;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertagSuffix", 0x15u, 0x14u);
    if ( (int)Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(v20, v35, (__int64)&v23) < 0 )
    {
      v6 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v23, &cchOriginalDestLength, 0);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 4226;
        goto LABEL_6;
      }
    }
    v16 = v23;
    v35 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertagSuffix", 0x15u, 0x14u);
    v6 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
           v19,
           v35,
           (__int64)v16,
           (__int64)&v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4228;
      goto LABEL_6;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 67) + 112LL))(
           *((_QWORD *)this + 67),
           v28,
           v29);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 4230;
      goto LABEL_6;
    }
LABEL_46:
    v7 = 0;
    goto LABEL_47;
  }
  v8 = 4193;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
    (const char *)(unsigned int)v6,
    v18);
LABEL_47:
  WindowsDeleteString(v25);
  v25 = 0;
  WindowsDeleteString(v26);
  v26 = 0;
  WindowsDeleteString(v22);
  v22 = 0;
  WindowsDeleteString(v23);
  v23 = 0;
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(v21);
  v21 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  return v7;
}

```

## disassembly

```asm
0x1800a3e0c  push    rbp
0x1800a3e0e  push    rbx
0x1800a3e0f  push    rsi
0x1800a3e10  push    rdi
0x1800a3e11  push    r14
0x1800a3e13  push    r15
0x1800a3e15  lea     rbp, [rsp-2Fh]
0x1800a3e1a  sub     rsp, 0D8h
0x1800a3e21  mov     rax, cs:__security_cookie
0x1800a3e28  xor     rax, rsp
0x1800a3e2b  mov     [rbp+57h+var_40], rax
0x1800a3e2f  mov     rbx, r8
0x1800a3e32  mov     rdi, rdx
0x1800a3e35  mov     rsi, rcx
0x1800a3e38  mov     [rbp+57h+var_78], rdx
0x1800a3e3c  lea     rcx, [rbp+57h+var_78]
0x1800a3e40  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800a3e45  nop
0x1800a3e46  mov     [rbp+57h+var_80], rbx
0x1800a3e4a  lea     rcx, [rbp+57h+var_80]
0x1800a3e4e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800a3e53  nop
0x1800a3e54  xor     r14d, r14d
0x1800a3e57  mov     [rbp+57h+var_68], r14
0x1800a3e5b  mov     [rbp+57h+var_88], r14
0x1800a3e5f  mov     [rbp+57h+var_D0], r14
0x1800a3e63  mov     [rsp+100h+var_D8], r14
0x1800a3e68  mov     [rbp+57h+string], r14
0x1800a3e6c  mov     [rbp+57h+var_C8], r14
0x1800a3e70  mov     [rbp+57h+newString], r14
0x1800a3e74  mov     [rbp+57h+var_B8], r14
0x1800a3e78  mov     [rbp+57h+var_C0], r14
0x1800a3e7c  mov     [rbp+57h+var_A0], r14
0x1800a3e80  mov     [rbp+57h+var_A8], r14
0x1800a3e84  mov     byte ptr [rsp+100h+var_E0], r14b; int
0x1800a3e89  mov     [rbp+57h+var_90], r14d
0x1800a3e8d  test    rbx, rbx
0x1800a3e90  jz      loc_1800A43D2
0x1800a3e96  lea     rdx, [rbp+57h+var_D0]
0x1800a3e9a  lea     rcx, [rbp+57h+var_80]
0x1800a3e9e  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800a3ea3  mov     ebx, eax
0x1800a3ea5  test    eax, eax
0x1800a3ea7  jns     short loc_1800A3EB0
0x1800a3ea9  mov     edx, 1061h
0x1800a3eae  jmp     short loc_1800A3EC8
0x1800a3eb0  lea     rdx, [rbp+57h+var_68]
0x1800a3eb4  lea     rcx, [rbp+57h+var_78]
0x1800a3eb8  call    ??$As@UIUserProfileInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserProfileInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::Implementation::IUserProfileInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserProfileInternal>>)
0x1800a3ebd  mov     ebx, eax
0x1800a3ebf  test    eax, eax
0x1800a3ec1  jns     short loc_1800A3EE0
0x1800a3ec3  mov     edx, 1062h; void *
0x1800a3ec8  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800a3ecf  mov     r9d, eax; char *
0x1800a3ed2  mov     rcx, [rbp+5Fh]; this
0x1800a3ed6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3edb  jmp     loc_1800A43D5
0x1800a3ee0  mov     rax, [rdi]
0x1800a3ee3  lea     rdx, [rbp+57h+var_90]
0x1800a3ee7  mov     rcx, rdi
0x1800a3eea  mov     rax, [rax+30h]
0x1800a3eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ef3  mov     ebx, eax
0x1800a3ef5  test    eax, eax
0x1800a3ef7  jns     short loc_1800A3F00
0x1800a3ef9  mov     edx, 1064h
0x1800a3efe  jmp     short loc_1800A3EC8
0x1800a3f00  mov     rax, [rdi]
0x1800a3f03  mov     rbx, [rax+58h]
0x1800a3f07  lea     rcx, [rbp+57h+var_88]
0x1800a3f0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a3f10  lea     rdx, [rbp+57h+var_88]
0x1800a3f14  mov     rcx, rdi
0x1800a3f17  mov     rax, rbx
0x1800a3f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f1f  mov     ebx, eax
0x1800a3f21  test    eax, eax
0x1800a3f23  jns     short loc_1800A3F2C
0x1800a3f25  mov     edx, 1065h
0x1800a3f2a  jmp     short loc_1800A3EC8
0x1800a3f2c  lea     rdx, [rsp+100h+var_D8]
0x1800a3f31  lea     rcx, [rbp+57h+var_88]
0x1800a3f35  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800a3f3a  mov     ebx, eax
0x1800a3f3c  test    eax, eax
0x1800a3f3e  jns     short loc_1800A3F47
0x1800a3f40  mov     edx, 1067h
0x1800a3f45  jmp     short loc_1800A3EC8
0x1800a3f47  mov     rcx, [rbp+57h+string]; string
0x1800a3f4b  call    cs:__imp_WindowsDeleteString
0x1800a3f51  mov     [rbp+57h+string], r14
0x1800a3f55  mov     [rbp+57h+var_48], r14
0x1800a3f59  mov     r9d, 0Ah; unsigned int
0x1800a3f5f  lea     r8d, [r9+1]; unsigned int
0x1800a3f63  lea     rdx, aXboxuserid_0; "XboxUserId"
0x1800a3f6a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a3f6e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a3f73  nop
0x1800a3f74  lea     r8, [rbp+57h+string]
0x1800a3f78  mov     rdx, [rbp+57h+var_48]
0x1800a3f7c  mov     rcx, [rbp+57h+var_D0]
0x1800a3f80  call    ??$FromPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@PEAPEAU8@@Z; Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *)
0x1800a3f85  mov     ebx, eax
0x1800a3f87  test    eax, eax
0x1800a3f89  jns     short loc_1800A3F95
0x1800a3f8b  mov     edx, 1069h
0x1800a3f90  jmp     loc_1800A3EC8
0x1800a3f95  mov     rcx, [rbp+57h+var_C8]; string
0x1800a3f99  call    cs:__imp_WindowsDeleteString
0x1800a3f9f  mov     [rbp+57h+var_C8], r14
0x1800a3fa3  mov     [rbp+57h+var_48], r14
0x1800a3fa7  mov     edi, 8
0x1800a3fac  mov     r9d, edi; unsigned int
0x1800a3faf  lea     r15d, [rdi+1]
0x1800a3fb3  mov     r8d, r15d; unsigned int
0x1800a3fb6  lea     rdx, aGamertag; "Gamertag"
0x1800a3fbd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a3fc1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a3fc6  nop
0x1800a3fc7  lea     r8, [rbp+57h+var_C8]
0x1800a3fcb  mov     rdx, [rbp+57h+var_48]
0x1800a3fcf  mov     rcx, [rbp+57h+var_D0]
0x1800a3fd3  call    ??$FromPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@PEAPEAU8@@Z; Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *)
0x1800a3fd8  mov     ebx, eax
0x1800a3fda  test    eax, eax
0x1800a3fdc  jns     short loc_1800A3FE8
0x1800a3fde  mov     edx, 106Ah
0x1800a3fe3  jmp     loc_1800A3EC8
0x1800a3fe8  mov     rcx, [rbp+57h+var_A0]; string
0x1800a3fec  call    cs:__imp_WindowsDeleteString
0x1800a3ff2  mov     [rbp+57h+var_A0], r14
0x1800a3ff6  mov     [rbp+57h+var_48], r14
0x1800a3ffa  mov     r9d, edi; unsigned int
0x1800a3ffd  mov     r8d, r15d; unsigned int
0x1800a4000  lea     rdx, aAgegroup_0; "AgeGroup"
0x1800a4007  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a400b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a4010  nop
0x1800a4011  lea     r8, [rbp+57h+var_A0]
0x1800a4015  mov     rdx, [rbp+57h+var_48]
0x1800a4019  mov     rcx, [rbp+57h+var_D0]
0x1800a401d  call    ??$FromPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@PEAPEAU8@@Z; Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *)
0x1800a4022  mov     ebx, eax
0x1800a4024  test    eax, eax
0x1800a4026  jns     short loc_1800A4032
0x1800a4028  mov     edx, 106Bh
0x1800a402d  jmp     loc_1800A3EC8
0x1800a4032  mov     rcx, [rbp+57h+var_A8]; string
0x1800a4036  call    cs:__imp_WindowsDeleteString
0x1800a403c  mov     [rbp+57h+var_A8], r14
0x1800a4040  mov     [rbp+57h+var_48], r14
0x1800a4044  mov     r9d, edi; unsigned int
0x1800a4047  mov     r8d, r15d; unsigned int
0x1800a404a  lea     rdx, aUserdata_0; "UserData"
0x1800a4051  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a4055  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a405a  nop
0x1800a405b  lea     r8, [rbp+57h+var_A8]
0x1800a405f  mov     rdx, [rbp+57h+var_48]
0x1800a4063  mov     rcx, [rbp+57h+var_D0]
0x1800a4067  call    ??$FromPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@PEAPEAU8@@Z; Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *)
0x1800a406c  mov     ebx, eax
0x1800a406e  test    eax, eax
0x1800a4070  jns     short loc_1800A407C
0x1800a4072  mov     edx, 106Ch
0x1800a4077  jmp     loc_1800A3EC8
0x1800a407c  mov     rbx, [rbp+57h+string]
0x1800a4080  mov     [rbp+57h+var_48], r14
0x1800a4084  mov     r9d, 0Ah; unsigned int
0x1800a408a  lea     r8d, [r9+1]; unsigned int
0x1800a408e  lea     rdx, aXboxuserid_0; "XboxUserId"
0x1800a4095  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a4099  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a409e  nop
0x1800a409f  lea     r9, [rsp+100h+var_E0]
0x1800a40a4  mov     r8, rbx
0x1800a40a7  mov     rdx, [rbp+57h+var_48]
0x1800a40ab  mov     rcx, [rsp+100h+var_D8]
0x1800a40b0  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x1800a40b5  mov     ebx, eax
0x1800a40b7  test    eax, eax
0x1800a40b9  jns     short loc_1800A40C5
0x1800a40bb  mov     edx, 106Dh
0x1800a40c0  jmp     loc_1800A3EC8
0x1800a40c5  mov     rbx, [rbp+57h+var_C8]
0x1800a40c9  mov     [rbp+57h+var_48], r14
0x1800a40cd  mov     r9d, edi; unsigned int
0x1800a40d0  mov     r8d, r15d; unsigned int
0x1800a40d3  lea     rdx, aGamertag; "Gamertag"
0x1800a40da  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a40de  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a40e3  nop
0x1800a40e4  lea     r9, [rsp+100h+var_E0]
0x1800a40e9  mov     r8, rbx
0x1800a40ec  mov     rdx, [rbp+57h+var_48]
0x1800a40f0  mov     rcx, [rsp+100h+var_D8]
0x1800a40f5  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x1800a40fa  mov     ebx, eax
0x1800a40fc  test    eax, eax
0x1800a40fe  jns     short loc_1800A410A
0x1800a4100  mov     edx, 106Eh
0x1800a4105  jmp     loc_1800A3EC8
0x1800a410a  mov     rbx, [rbp+57h+var_A0]
0x1800a410e  mov     [rbp+57h+var_48], r14
0x1800a4112  mov     r9d, edi; unsigned int
0x1800a4115  mov     r8d, r15d; unsigned int
0x1800a4118  lea     rdx, aAgegroup_0; "AgeGroup"
0x1800a411f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a4123  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a4128  nop
0x1800a4129  lea     r9, [rsp+100h+var_E0]
0x1800a412e  mov     r8, rbx
0x1800a4131  mov     rdx, [rbp+57h+var_48]
0x1800a4135  mov     rcx, [rsp+100h+var_D8]
0x1800a413a  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x1800a413f  mov     ebx, eax
0x1800a4141  test    eax, eax
0x1800a4143  jns     short loc_1800A414F
0x1800a4145  mov     edx, 106Fh
0x1800a414a  jmp     loc_1800A3EC8
0x1800a414f  mov     rbx, [rbp+57h+var_A8]
0x1800a4153  mov     [rbp+57h+var_48], r14
0x1800a4157  mov     r9d, edi; unsigned int
0x1800a415a  mov     r8d, r15d; unsigned int
0x1800a415d  lea     rdx, aUserdata_0; "UserData"
0x1800a4164  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a4168  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a416d  nop
0x1800a416e  lea     r9, [rsp+100h+var_E0]
0x1800a4173  mov     r8, rbx
0x1800a4176  mov     rdx, [rbp+57h+var_48]
0x1800a417a  mov     rcx, [rsp+100h+var_D8]
0x1800a417f  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x1800a4184  mov     ebx, eax
0x1800a4186  test    eax, eax
0x1800a4188  jns     short loc_1800A4194
0x1800a418a  mov     edx, 1070h
0x1800a418f  jmp     loc_1800A3EC8
0x1800a4194  mov     rcx, [rbp+57h+newString]; string
0x1800a4198  call    cs:__imp_WindowsDeleteString
0x1800a419e  mov     [rbp+57h+newString], r14
0x1800a41a2  mov     [rbp+57h+var_48], r14
0x1800a41a6  mov     edi, 0Eh
0x1800a41ab  mov     r9d, edi; unsigned int
0x1800a41ae  lea     r15d, [rdi+1]
0x1800a41b2  mov     r8d, r15d; unsigned int
0x1800a41b5  lea     rdx, aModerngamertag; "ModernGamertag"
0x1800a41bc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a41c0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a41c5  nop
0x1800a41c6  lea     r8, [rbp+57h+newString]
0x1800a41ca  mov     rdx, [rbp+57h+var_48]
0x1800a41ce  mov     rcx, [rbp+57h+var_D0]
0x1800a41d2  call    ??$FromPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@PEAPEAU8@@Z; Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *)
0x1800a41d7  nop
0x1800a41d8  shr     eax, 1Fh
0x1800a41db  test    al, al
0x1800a41dd  jz      short loc_1800A4204
0x1800a41df  mov     rax, [rbp+57h+var_C8]
0x1800a41e3  mov     [rbp+57h+var_70], rax
0x1800a41e7  lea     rdx, [rbp+57h+var_70]; HSTRING *
0x1800a41eb  lea     rcx, [rbp+57h+newString]; newString
0x1800a41ef  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800a41f4  mov     ebx, eax
0x1800a41f6  test    eax, eax
0x1800a41f8  jns     short loc_1800A4204
0x1800a41fa  mov     edx, 1075h
0x1800a41ff  jmp     loc_1800A3EC8
0x1800a4204  mov     rbx, [rbp+57h+newString]
0x1800a4208  mov     [rbp+57h+var_48], r14
0x1800a420c  mov     r9d, edi; unsigned int
0x1800a420f  mov     r8d, r15d; unsigned int
0x1800a4212  lea     rdx, aModerngamertag; "ModernGamertag"
0x1800a4219  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a421d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a4222  nop
0x1800a4223  lea     r9, [rsp+100h+var_E0]
0x1800a4228  mov     r8, rbx
0x1800a422b  mov     rdx, [rbp+57h+var_48]
0x1800a422f  mov     rcx, [rsp+100h+var_D8]
0x1800a4234  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x1800a4239  mov     ebx, eax
0x1800a423b  test    eax, eax
0x1800a423d  jns     short loc_1800A4249
0x1800a423f  mov     edx, 1077h
0x1800a4244  jmp     loc_1800A3EC8
0x1800a4249  mov     rcx, [rbp+57h+var_C0]; string
0x1800a424d  call    cs:__imp_WindowsDeleteString
0x1800a4253  mov     [rbp+57h+var_C0], r14
0x1800a4257  mov     [rbp+57h+var_48], r14
0x1800a425b  mov     edi, 14h
0x1800a4260  mov     r9d, edi; unsigned int
0x1800a4263  lea     r15d, [rdi+1]
0x1800a4267  mov     r8d, r15d; unsigned int
0x1800a426a  lea     rdx, aUniquemodernga; "UniqueModernGamertag"
0x1800a4271  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a4275  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a427a  nop
0x1800a427b  lea     r8, [rbp+57h+var_C0]
  ... truncated ...
```
