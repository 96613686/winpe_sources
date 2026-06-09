# GetApplicationByPackageAndCategory

- ea: `0x180116d00`
- end: `0x180116ffb`
- name: `GetApplicationByPackageAndCategory`
- size: `763`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007d620`

## callees

- `0x180004658`
- `0x180042428`
- `0x180042d18`
- `0x180116668`
- `0x180116d00`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `UserDataTypeHelperUtil!SafeStrDup` at `0x180116f51`
- `UserDataTypeHelperUtil!SafeStrDup` at `0x180116f51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180116f12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180116f61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180116f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180116f12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180116f61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180116f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180116f40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180116f40`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180116d92`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180116e61`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180116d92`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180116e61`

## string_xrefs

- `0x180116e3a`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
__int64 __fastcall GetApplicationByPackageAndCategory(const WCHAR *a1, __int64 a2, _QWORD *a3)
{
  int PackageFromPackageFamilyName; // ebx
  void (*v5)(void); // rax
  int ActivationFactory; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  struct Windows::Internal::StateRepository::IPackage *v10; // rsi
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rcx
  void (*v12)(void); // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  void (*v15)(void); // rax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall **v18)(_QWORD, GUID *, struct Windows::Internal::StateRepository::IPackage **); // rax
  __int64 (__fastcall *v19)(_QWORD, GUID *, struct Windows::Internal::StateRepository::IPackage **); // rbx
  HSTRING v20; // rcx
  __int64 v21; // rcx
  PCWSTR StringRawBuffer; // rax
  int v23; // eax
  __int64 v24; // rcx
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-50h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // [rsp+28h] [rbp-48h] BYREF
  __int64 v29; // [rsp+30h] [rbp-40h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v30; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v33; // [rsp+60h] [rbp-10h]
  __int64 v34; // [rsp+A8h] [rbp+38h] BYREF

  v34 = a2;
  *a3 = 0;
  v30 = 0;
  PackageFromPackageFamilyName = GetPackageFromPackageFamilyName(a1, &v30, 0);
  if ( PackageFromPackageFamilyName < 0 )
  {
    if ( !v30 )
      return (unsigned int)PackageFromPackageFamilyName;
    v5 = *(void (**)(void))(*(_QWORD *)v30 + 16LL);
LABEL_4:
    v5();
    return (unsigned int)PackageFromPackageFamilyName;
  }
  v27 = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  ActivationFactory = RoGetActivationFactory(v33, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v27);
  v8 = v27;
  PackageFromPackageFamilyName = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    if ( !v30 )
      return (unsigned int)PackageFromPackageFamilyName;
    v9 = *(_QWORD *)v30;
    goto LABEL_11;
  }
  v10 = v30;
  v28 = 0;
  PackageFromPackageFamilyName = (*(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IPackage *, _QWORD))(*(_QWORD *)v27 + 144LL))(
                                   v27,
                                   v30,
                                   &v28);
  if ( PackageFromPackageFamilyName < 0 )
  {
    v11 = v28;
    if ( !v28 )
    {
LABEL_16:
      v13 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      if ( !v10 )
        return (unsigned int)PackageFromPackageFamilyName;
      v9 = *(_QWORD *)v10;
LABEL_11:
      v5 = *(void (**)(void))(v9 + 16);
      goto LABEL_4;
    }
    v28 = 0;
    v12 = (void (*)(void))(*v11)[2];
LABEL_15:
    v12();
    goto LABEL_16;
  }
  v29 = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.ApplicationExtension",
    0x36u,
    0x35u);
  PackageFromPackageFamilyName = RoGetActivationFactory(v33, &GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12, &v29);
  if ( PackageFromPackageFamilyName < 0 )
    goto LABEL_21;
  v17 = v28;
  hstringHeader.Reserved.Reserved1 = &v29;
  string = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v34;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &string;
  v18 = (__int64 (__fastcall **)(_QWORD, GUID *, struct Windows::Internal::StateRepository::IPackage **))*v28;
  v30 = 0;
  v19 = *v18;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v30);
  PackageFromPackageFamilyName = v19(v17, &GUID_52384ae4_02b2_581d_b976_80c8813cef40, &v30);
  if ( PackageFromPackageFamilyName >= 0 )
    PackageFromPackageFamilyName = ForEach_Windows::Internal::StateRepository::Application____lambda_2573b764da6dbdf55ac29daa8dabcbea___(
                                     v30,
                                     &hstringHeader);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v30);
  v20 = string;
  if ( PackageFromPackageFamilyName < 0 )
  {
    WindowsDeleteString(string);
    v21 = v29;
    string = 0;
    if ( !v29 )
      goto LABEL_24;
    v29 = 0;
    v15 = *(void (**)(void))(*(_QWORD *)v21 + 16LL);
    goto LABEL_23;
  }
  if ( string )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v23 = SafeStrDup(StringRawBuffer, 131, a3);
    v20 = string;
    PackageFromPackageFamilyName = v23;
    if ( v23 < 0 )
    {
      WindowsDeleteString(string);
      string = 0;
LABEL_21:
      v14 = v29;
      if ( !v29 )
      {
LABEL_24:
        v16 = v28;
        if ( !v28 )
          goto LABEL_16;
        v28 = 0;
        v12 = (void (*)(void))(*v16)[2];
        goto LABEL_15;
      }
      v29 = 0;
      v15 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
LABEL_23:
      v15();
      goto LABEL_24;
    }
  }
  WindowsDeleteString(v20);
  v24 = v29;
  string = 0;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v28;
  if ( v28 )
  {
    v28 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v25)[2])(v25);
  }
  v26 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  if ( v10 )
    (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v10 + 16LL))(v10);
  return 0;
}

```

## disassembly

```asm
0x180116d00  mov     [rsp-28h+arg_18], rbx
0x180116d05  mov     [rsp-28h+arg_8], rdx
0x180116d0a  push    rbp
0x180116d0b  push    rsi
0x180116d0c  push    rdi
0x180116d0d  push    r14
0x180116d0f  push    r15
0x180116d11  mov     rbp, rsp
0x180116d14  sub     rsp, 70h
0x180116d18  mov     rax, cs:__security_cookie
0x180116d1f  xor     rax, rsp
0x180116d22  mov     [rbp+var_8], rax
0x180116d26  xor     r15d, r15d
0x180116d29  lea     rdx, [rbp+var_38]; struct Windows::Internal::StateRepository::IPackage **
0x180116d2d  mov     [r8], r15
0x180116d30  mov     r14, r8
0x180116d33  xor     r8d, r8d; struct Windows::Internal::StateRepository::IPackageUser **
0x180116d36  mov     [rbp+var_38], r15
0x180116d3a  call    ?GetPackageFromPackageFamilyName@@YAJPEBGPEAPEAUIPackage@StateRepository@Internal@Windows@@PEAPEAUIPackageUser@234@@Z; GetPackageFromPackageFamilyName(ushort const *,Windows::Internal::StateRepository::IPackage * *,Windows::Internal::StateRepository::IPackageUser * *)
0x180116d3f  mov     ebx, eax
0x180116d41  test    eax, eax
0x180116d43  jns     short loc_180116D61
0x180116d45  mov     rcx, [rbp+var_38]
0x180116d49  test    rcx, rcx
0x180116d4c  jz      short loc_180116D5A
0x180116d4e  mov     rdx, [rcx]
0x180116d51  mov     rax, [rdx+10h]
0x180116d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116d5a  mov     eax, ebx
0x180116d5c  jmp     loc_180116FDB
0x180116d61  mov     r9d, 2Ch ; ','; unsigned int
0x180116d67  mov     [rbp+var_50], r15
0x180116d6b  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180116d72  mov     [rbp+var_10], r15
0x180116d76  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180116d7a  lea     r8d, [r9+1]; unsigned int
0x180116d7e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180116d83  mov     rcx, [rbp+var_10]
0x180116d87  lea     r8, [rbp+var_50]
0x180116d8b  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180116d92  call    cs:__imp_RoGetActivationFactory
0x180116d98  mov     rcx, [rbp+var_50]
0x180116d9c  mov     ebx, eax
0x180116d9e  test    eax, eax
0x180116da0  jns     short loc_180116DC9
0x180116da2  test    rcx, rcx
0x180116da5  jz      short loc_180116DB7
0x180116da7  mov     [rbp+var_50], r15
0x180116dab  mov     rdx, [rcx]
0x180116dae  mov     rax, [rdx+10h]
0x180116db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116db7  mov     rcx, [rbp+var_38]
0x180116dbb  test    rcx, rcx
0x180116dbe  jz      short loc_180116D5A
0x180116dc0  mov     rax, [rcx]
0x180116dc3  mov     rax, [rax+10h]
0x180116dc7  jmp     short loc_180116D55
0x180116dc9  mov     rsi, [rbp+var_38]
0x180116dcd  lea     r8, [rbp+var_48]
0x180116dd1  mov     [rbp+var_48], r15
0x180116dd5  mov     rdx, rsi
0x180116dd8  mov     rax, [rcx]
0x180116ddb  mov     rax, [rax+90h]
0x180116de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116de7  mov     ebx, eax
0x180116de9  test    eax, eax
0x180116deb  jns     short loc_180116E30
0x180116ded  mov     rcx, [rbp+var_48]
0x180116df1  test    rcx, rcx
0x180116df4  jz      short loc_180116E06
0x180116df6  mov     [rbp+var_48], r15
0x180116dfa  mov     rdx, [rcx]
0x180116dfd  mov     rax, [rdx+10h]
0x180116e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116e06  mov     rcx, [rbp+var_50]
0x180116e0a  test    rcx, rcx
0x180116e0d  jz      short loc_180116E1F
0x180116e0f  mov     [rbp+var_50], r15
0x180116e13  mov     rax, [rcx]
0x180116e16  mov     rax, [rax+10h]
0x180116e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116e1f  test    rsi, rsi
0x180116e22  jz      loc_180116D5A
0x180116e28  mov     rax, [rsi]
0x180116e2b  mov     rcx, rsi
0x180116e2e  jmp     short loc_180116DC3
0x180116e30  mov     r9d, 35h ; '5'; unsigned int
0x180116e36  mov     [rbp+var_40], r15
0x180116e3a  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180116e41  mov     [rbp+var_10], r15
0x180116e45  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180116e49  lea     r8d, [r9+1]; unsigned int
0x180116e4d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180116e52  mov     rcx, [rbp+var_10]
0x180116e56  lea     r8, [rbp+var_40]
0x180116e5a  lea     rdx, _GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12
0x180116e61  call    cs:__imp_RoGetActivationFactory
0x180116e67  mov     ebx, eax
0x180116e69  test    eax, eax
0x180116e6b  jns     short loc_180116EA3
0x180116e6d  mov     rcx, [rbp+var_40]
0x180116e71  test    rcx, rcx
0x180116e74  jz      short loc_180116E86
0x180116e76  mov     [rbp+var_40], r15
0x180116e7a  mov     rdx, [rcx]
0x180116e7d  mov     rax, [rdx+10h]
0x180116e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116e86  mov     rcx, [rbp+var_48]
0x180116e8a  test    rcx, rcx
0x180116e8d  jz      loc_180116E06
0x180116e93  mov     [rbp+var_48], r15
0x180116e97  mov     rax, [rcx]
0x180116e9a  mov     rax, [rax+10h]
0x180116e9e  jmp     loc_180116E01
0x180116ea3  mov     rdi, [rbp+var_48]
0x180116ea7  lea     rax, [rbp+var_40]
0x180116eab  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x180116eaf  lea     rcx, [rbp+var_38]
0x180116eb3  lea     rax, [rbp+arg_8]
0x180116eb7  mov     [rbp+string], r15
0x180116ebb  mov     qword ptr [rbp+hstringHeader.Reserved+8], rax
0x180116ebf  lea     rax, [rbp+string]
0x180116ec3  mov     qword ptr [rbp+hstringHeader.Reserved+10h], rax
0x180116ec7  mov     rax, [rdi]
0x180116eca  mov     [rbp+var_38], r15
0x180116ece  mov     rbx, [rax]
0x180116ed1  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180116ed6  lea     r8, [rbp+var_38]
0x180116eda  mov     rcx, rdi
0x180116edd  lea     rdx, _GUID_52384ae4_02b2_581d_b976_80c8813cef40
0x180116ee4  mov     rax, rbx
0x180116ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116eec  mov     ebx, eax
0x180116eee  test    eax, eax
0x180116ef0  js      short loc_180116F01
0x180116ef2  mov     rcx, [rbp+var_38]
0x180116ef6  lea     rdx, [rbp+hstringHeader]
0x180116efa  call    ForEach_Windows__Internal__StateRepository__Application____lambda_2573b764da6dbdf55ac29daa8dabcbea___
0x180116eff  mov     ebx, eax
0x180116f01  lea     rcx, [rbp+var_38]
0x180116f05  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180116f0a  mov     rcx, [rbp+string]; string
0x180116f0e  test    ebx, ebx
0x180116f10  jns     short loc_180116F39
0x180116f12  call    cs:__imp_WindowsDeleteString
0x180116f18  mov     rcx, [rbp+var_40]
0x180116f1c  mov     [rbp+string], r15
0x180116f20  test    rcx, rcx
0x180116f23  jz      loc_180116E86
0x180116f29  mov     [rbp+var_40], r15
0x180116f2d  mov     rax, [rcx]
0x180116f30  mov     rax, [rax+10h]
0x180116f34  jmp     loc_180116E81
0x180116f39  test    rcx, rcx
0x180116f3c  jz      short loc_180116F70
0x180116f3e  xor     edx, edx; length
0x180116f40  call    cs:__imp_WindowsGetStringRawBuffer
0x180116f46  mov     r8, r14
0x180116f49  mov     edx, 83h
0x180116f4e  mov     rcx, rax
0x180116f51  call    cs:__imp_SafeStrDup
0x180116f57  mov     rcx, [rbp+string]; string
0x180116f5b  mov     ebx, eax
0x180116f5d  test    eax, eax
0x180116f5f  jns     short loc_180116F70
0x180116f61  call    cs:__imp_WindowsDeleteString
0x180116f67  mov     [rbp+string], r15
0x180116f6b  jmp     loc_180116E6D
0x180116f70  call    cs:__imp_WindowsDeleteString
0x180116f76  mov     rcx, [rbp+var_40]
0x180116f7a  mov     [rbp+string], r15
0x180116f7e  test    rcx, rcx
0x180116f81  jz      short loc_180116F93
0x180116f83  mov     [rbp+var_40], r15
0x180116f87  mov     rax, [rcx]
0x180116f8a  mov     rax, [rax+10h]
0x180116f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116f93  mov     rcx, [rbp+var_48]
0x180116f97  test    rcx, rcx
0x180116f9a  jz      short loc_180116FAC
0x180116f9c  mov     [rbp+var_48], r15
0x180116fa0  mov     rax, [rcx]
0x180116fa3  mov     rax, [rax+10h]
0x180116fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116fac  mov     rcx, [rbp+var_50]
0x180116fb0  test    rcx, rcx
0x180116fb3  jz      short loc_180116FC5
0x180116fb5  mov     [rbp+var_50], r15
0x180116fb9  mov     rax, [rcx]
0x180116fbc  mov     rax, [rax+10h]
0x180116fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116fc5  test    rsi, rsi
0x180116fc8  jz      short loc_180116FD9
0x180116fca  mov     rax, [rsi]
0x180116fcd  mov     rcx, rsi
0x180116fd0  mov     rax, [rax+10h]
0x180116fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116fd9  xor     eax, eax
0x180116fdb  mov     rcx, [rbp+var_8]
0x180116fdf  xor     rcx, rsp; StackCookie
0x180116fe2  call    __security_check_cookie
0x180116fe7  mov     rbx, [rsp+70h+arg_18]
0x180116fef  add     rsp, 70h
0x180116ff3  pop     r15
0x180116ff5  pop     r14
0x180116ff7  pop     rdi
0x180116ff8  pop     rsi
0x180116ff9  pop     rbp
0x180116ffa  retn
```
