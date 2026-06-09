# GetDisplayNameFromPackageFamilyNameAndPraid

- ea: `0x180040d98`
- end: `0x18004108c`
- name: `GetDisplayNameFromPackageFamilyNameAndPraid`
- size: `756`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004075c`
- `0x1800dbe0c`
- `0x1800eaee8`
- `0x1801170dc`

## callees

- `0x180004658`
- `0x180040d98`
- `0x180041be4`
- `0x180042428`
- `0x180042d18`
- `0x180064880`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `UserDataTypeHelperUtil!SafeStrDup` at `0x180041005`
- `UserDataTypeHelperUtil!SafeStrDup` at `0x180041005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040fc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040fe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041015`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040fc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040fe8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041015`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040ff6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040ff6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040e45`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040f31`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040e45`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040f31`

## pseudocode

```c
__int64 __fastcall GetDisplayNameFromPackageFamilyNameAndPraid(const WCHAR *a1, const WCHAR *a2, __int64 a3)
{
  __int64 result; // rax
  int PackageFromPackageFamilyName; // ebx
  void (*v6)(void); // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, struct Windows::Internal::StateRepository::IPackage *, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v11; // rax
  struct Windows::Internal::StateRepository::IPackage *v12; // rsi
  __int64 v13; // rcx
  void (*v14)(void); // rax
  __int64 v15; // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, __int64 *); // rbx
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  HSTRING v22; // rcx
  PCWSTR StringRawBuffer; // rax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  __int64 v28; // [rsp+40h] [rbp-19h] BYREF
  __int64 v29; // [rsp+48h] [rbp-11h] BYREF
  __int64 v30; // [rsp+50h] [rbp-9h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v31; // [rsp+58h] [rbp-1h] BYREF
  const WCHAR *v32; // [rsp+60h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v34; // [rsp+80h] [rbp+27h]

  v32 = a2;
  if ( !a2 )
  {
    result = GetAppDisplayName(a1, a3);
    if ( (int)result < 0 )
      return result;
    return 0;
  }
  v31 = 0;
  PackageFromPackageFamilyName = GetPackageFromPackageFamilyName(a1, &v31, 0);
  if ( PackageFromPackageFamilyName < 0 )
  {
    if ( !v31 )
      return (unsigned int)PackageFromPackageFamilyName;
    v6 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
LABEL_7:
    v6();
    return (unsigned int)PackageFromPackageFamilyName;
  }
  v26 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  PackageFromPackageFamilyName = RoGetActivationFactory(v34, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v26);
  if ( PackageFromPackageFamilyName < 0 )
  {
    v7 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    if ( !v31 )
      return (unsigned int)PackageFromPackageFamilyName;
    v8 = *(_QWORD *)v31;
LABEL_14:
    v6 = *(void (**)(void))(v8 + 16);
    goto LABEL_7;
  }
  v9 = v26;
  v28 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IPackage *, PVOID, __int64 *))(*(_QWORD *)v26 + 104LL);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v32);
  v12 = v31;
  PackageFromPackageFamilyName = v10(v9, v31, v11[1].Reserved.Reserved1, &v28);
  if ( PackageFromPackageFamilyName < 0 )
    goto LABEL_16;
  v29 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.ApplicationResourceResolver",
    0x3Du,
    0x3Cu);
  v15 = v34;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v29);
  PackageFromPackageFamilyName = RoGetActivationFactory(v15, &GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9, &v29);
  if ( PackageFromPackageFamilyName < 0 )
  {
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v29);
LABEL_16:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
    v13 = v26;
    if ( !v26 )
    {
LABEL_19:
      if ( !v12 )
        return (unsigned int)PackageFromPackageFamilyName;
      v8 = *(_QWORD *)v12;
      goto LABEL_14;
    }
    v26 = 0;
    v14 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
LABEL_18:
    v14();
    goto LABEL_19;
  }
  v16 = v29;
  v30 = 0;
  v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v29 + 48LL);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v30);
  PackageFromPackageFamilyName = v17(v16, v28, &v30);
  if ( PackageFromPackageFamilyName < 0 )
  {
LABEL_24:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
    v18 = v26;
    if ( !v26 )
      goto LABEL_19;
    v26 = 0;
    v14 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
    goto LABEL_18;
  }
  v19 = v30;
  string = 0;
  v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v21 = v20(v19, &string);
  v22 = string;
  PackageFromPackageFamilyName = v21;
  if ( v21 < 0
    || (StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
        v24 = SafeStrDup(StringRawBuffer, 0xFFFFFFFFLL, a3),
        v22 = string,
        PackageFromPackageFamilyName = v24,
        v24 < 0) )
  {
    WindowsDeleteString(v22);
    string = 0;
    goto LABEL_24;
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v28);
  v25 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  if ( v12 )
    (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v12 + 16LL))(v12);
  return 0;
}

```

## disassembly

```asm
0x180040d98  mov     [rsp-8+arg_18], rbx
0x180040d9d  push    rbp
0x180040d9e  push    rsi
0x180040d9f  push    rdi
0x180040da0  push    r14
0x180040da2  push    r15
0x180040da4  lea     rbp, [rsp-37h]
0x180040da9  sub     rsp, 90h
0x180040db0  mov     rax, cs:__security_cookie
0x180040db7  xor     rax, rsp
0x180040dba  mov     [rbp+57h+var_28], rax
0x180040dbe  xor     r15d, r15d
0x180040dc1  mov     [rbp+57h+var_50], rdx
0x180040dc5  mov     r14, r8
0x180040dc8  test    rdx, rdx
0x180040dcb  jnz     short loc_180040DE2
0x180040dcd  mov     rdx, r8
0x180040dd0  call    GetAppDisplayName
0x180040dd5  test    eax, eax
0x180040dd7  js      loc_180041069
0x180040ddd  jmp     loc_180041067
0x180040de2  xor     r8d, r8d; struct Windows::Internal::StateRepository::IPackageUser **
0x180040de5  mov     [rbp+57h+var_58], r15
0x180040de9  lea     rdx, [rbp+57h+var_58]; struct Windows::Internal::StateRepository::IPackage **
0x180040ded  call    ?GetPackageFromPackageFamilyName@@YAJPEBGPEAPEAUIPackage@StateRepository@Internal@Windows@@PEAPEAUIPackageUser@234@@Z; GetPackageFromPackageFamilyName(ushort const *,Windows::Internal::StateRepository::IPackage * *,Windows::Internal::StateRepository::IPackageUser * *)
0x180040df2  mov     ebx, eax
0x180040df4  test    eax, eax
0x180040df6  jns     short loc_180040E14
0x180040df8  mov     rcx, [rbp+57h+var_58]
0x180040dfc  test    rcx, rcx
0x180040dff  jz      short loc_180040E0D
0x180040e01  mov     rdx, [rcx]
0x180040e04  mov     rax, [rdx+10h]
0x180040e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e0d  mov     eax, ebx
0x180040e0f  jmp     loc_180041069
0x180040e14  mov     r9d, 2Ch ; ','; unsigned int
0x180040e1a  mov     [rbp+57h+var_80], r15
0x180040e1e  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180040e25  mov     [rbp+57h+var_30], r15
0x180040e29  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180040e2d  lea     r8d, [r9+1]; unsigned int
0x180040e31  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180040e36  mov     rcx, [rbp+57h+var_30]
0x180040e3a  lea     r8, [rbp+57h+var_80]
0x180040e3e  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180040e45  call    cs:__imp_RoGetActivationFactory
0x180040e4b  mov     ebx, eax
0x180040e4d  test    eax, eax
0x180040e4f  jns     short loc_180040E7C
0x180040e51  mov     rcx, [rbp+57h+var_80]
0x180040e55  test    rcx, rcx
0x180040e58  jz      short loc_180040E6A
0x180040e5a  mov     [rbp+57h+var_80], r15
0x180040e5e  mov     rdx, [rcx]
0x180040e61  mov     rax, [rdx+10h]
0x180040e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e6a  mov     rcx, [rbp+57h+var_58]
0x180040e6e  test    rcx, rcx
0x180040e71  jz      short loc_180040E0D
0x180040e73  mov     rax, [rcx]
0x180040e76  mov     rax, [rax+10h]
0x180040e7a  jmp     short loc_180040E08
0x180040e7c  mov     rdi, [rbp+57h+var_80]
0x180040e80  lea     rcx, [rbp+57h+var_70]
0x180040e84  mov     [rbp+57h+var_70], r15
0x180040e88  mov     rax, [rdi]
0x180040e8b  mov     rbx, [rax+68h]
0x180040e8f  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180040e94  lea     rdx, [rbp+57h+var_50]
0x180040e98  lea     rcx, [rbp+57h+hstringHeader]
0x180040e9c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180040ea1  mov     rsi, [rbp+57h+var_58]
0x180040ea5  lea     r9, [rbp+57h+var_70]
0x180040ea9  mov     rdx, rsi
0x180040eac  mov     rcx, rdi
0x180040eaf  mov     r8, [rax+18h]
0x180040eb3  mov     rax, rbx
0x180040eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ebb  mov     ebx, eax
0x180040ebd  test    eax, eax
0x180040ebf  jns     short loc_180040EF4
0x180040ec1  lea     rcx, [rbp+57h+var_70]
0x180040ec5  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180040eca  mov     rcx, [rbp+57h+var_80]
0x180040ece  test    rcx, rcx
0x180040ed1  jz      short loc_180040EE3
0x180040ed3  mov     [rbp+57h+var_80], r15
0x180040ed7  mov     rdx, [rcx]
0x180040eda  mov     rax, [rdx+10h]
0x180040ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ee3  test    rsi, rsi
0x180040ee6  jz      loc_180040E0D
0x180040eec  mov     rax, [rsi]
0x180040eef  mov     rcx, rsi
0x180040ef2  jmp     short loc_180040E76
0x180040ef4  mov     r9d, 3Ch ; '<'; unsigned int
0x180040efa  mov     [rbp+57h+var_68], r15
0x180040efe  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180040f05  mov     [rbp+57h+var_30], r15
0x180040f09  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180040f0d  lea     r8d, [r9+1]; unsigned int
0x180040f11  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180040f16  mov     rbx, [rbp+57h+var_30]
0x180040f1a  lea     rcx, [rbp+57h+var_68]
0x180040f1e  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180040f23  lea     r8, [rbp+57h+var_68]
0x180040f27  mov     rcx, rbx
0x180040f2a  lea     rdx, _GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9
0x180040f31  call    cs:__imp_RoGetActivationFactory
0x180040f37  mov     ebx, eax
0x180040f39  test    eax, eax
0x180040f3b  jns     short loc_180040F4B
0x180040f3d  lea     rcx, [rbp+57h+var_68]
0x180040f41  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180040f46  jmp     loc_180040EC1
0x180040f4b  mov     rdi, [rbp+57h+var_68]
0x180040f4f  lea     rcx, [rbp+57h+var_60]
0x180040f53  mov     [rbp+57h+var_60], r15
0x180040f57  mov     rax, [rdi]
0x180040f5a  mov     rbx, [rax+30h]
0x180040f5e  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180040f63  mov     rdx, [rbp+57h+var_70]
0x180040f67  lea     r8, [rbp+57h+var_60]
0x180040f6b  mov     rcx, rdi
0x180040f6e  mov     rax, rbx
0x180040f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f76  mov     ebx, eax
0x180040f78  test    eax, eax
0x180040f7a  jns     short loc_180040FB4
0x180040f7c  lea     rcx, [rbp+57h+var_60]
0x180040f80  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180040f85  lea     rcx, [rbp+57h+var_68]
0x180040f89  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180040f8e  lea     rcx, [rbp+57h+var_70]
0x180040f92  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180040f97  mov     rcx, [rbp+57h+var_80]
0x180040f9b  test    rcx, rcx
0x180040f9e  jz      loc_180040EE3
0x180040fa4  mov     [rbp+57h+var_80], r15
0x180040fa8  mov     rax, [rcx]
0x180040fab  mov     rax, [rax+10h]
0x180040faf  jmp     loc_180040EDE
0x180040fb4  mov     rdi, [rbp+57h+var_60]
0x180040fb8  xor     ecx, ecx; string
0x180040fba  mov     [rbp+57h+string], r15
0x180040fbe  mov     rax, [rdi]
0x180040fc1  mov     rbx, [rax+30h]
0x180040fc5  call    cs:__imp_WindowsDeleteString
0x180040fcb  lea     rdx, [rbp+57h+string]
0x180040fcf  mov     [rbp+57h+string], r15
0x180040fd3  mov     rcx, rdi
0x180040fd6  mov     rax, rbx
0x180040fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fde  mov     rcx, [rbp+57h+string]; string
0x180040fe2  mov     ebx, eax
0x180040fe4  test    eax, eax
0x180040fe6  jns     short loc_180040FF4
0x180040fe8  call    cs:__imp_WindowsDeleteString
0x180040fee  mov     [rbp+57h+string], r15
0x180040ff2  jmp     short loc_180040F7C
0x180040ff4  xor     edx, edx; length
0x180040ff6  call    cs:__imp_WindowsGetStringRawBuffer
0x180040ffc  mov     r8, r14
0x180040fff  or      edx, 0FFFFFFFFh
0x180041002  mov     rcx, rax
0x180041005  call    cs:__imp_SafeStrDup
0x18004100b  mov     rcx, [rbp+57h+string]; string
0x18004100f  mov     ebx, eax
0x180041011  test    eax, eax
0x180041013  js      short loc_180040FE8
0x180041015  call    cs:__imp_WindowsDeleteString
0x18004101b  lea     rcx, [rbp+57h+var_60]
0x18004101f  mov     [rbp+57h+string], r15
0x180041023  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180041028  lea     rcx, [rbp+57h+var_68]
0x18004102c  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180041031  lea     rcx, [rbp+57h+var_70]
0x180041035  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18004103a  mov     rcx, [rbp+57h+var_80]
0x18004103e  test    rcx, rcx
0x180041041  jz      short loc_180041053
0x180041043  mov     [rbp+57h+var_80], r15
0x180041047  mov     rax, [rcx]
0x18004104a  mov     rax, [rax+10h]
0x18004104e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041053  test    rsi, rsi
0x180041056  jz      short loc_180041067
0x180041058  mov     rax, [rsi]
0x18004105b  mov     rcx, rsi
0x18004105e  mov     rax, [rax+10h]
0x180041062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041067  xor     eax, eax
0x180041069  mov     rcx, [rbp+57h+var_28]
0x18004106d  xor     rcx, rsp; StackCookie
0x180041070  call    __security_check_cookie
0x180041075  mov     rbx, [rsp+0B0h+arg_18]
0x18004107d  add     rsp, 90h
0x180041084  pop     r15
0x180041086  pop     r14
0x180041088  pop     rdi
0x180041089  pop     rsi
0x18004108a  pop     rbp
0x18004108b  retn
```
