# ApplicationIdentityInfo::GetManifestedExecutable(void)

- ea: `0x180024c0c`
- end: `0x180024eb4`
- name: `?GetManifestedExecutable@ApplicationIdentityInfo@@QEBA?AVHString@Wrappers@WRL@Microsoft@@XZ`
- size: `680`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ce0`

## callees

- `0x180003d24`
- `0x1800083f0`
- `0x180008470`
- `0x1800195e0`
- `0x180024c0c`
- `0x180024ebc`
- `0x180024ef8`
- `0x180024f90`
- `0x18002b1b0`
- `0x180033d5c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024e0f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024d7a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024d7a`

## string_xrefs

- `0x180024c4d`: `GetManifestedExecutable`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall ApplicationIdentityInfo::GetManifestedExecutable(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rbx
  int ActivationFactory; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, _QWORD, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD *); // rbx
  int v15; // eax
  const struct wil::FailureInfo *v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h]
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h]
  _QWORD v26[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v23[1] = a2;
  v22 = 0;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v26,
    "GetManifestedExecutable");
  v26[0] = &DesktopAppXProvider::GetManifestedExecutable::`vftable';
  DesktopAppXProvider::GetManifestedExecutable::StartActivity((DesktopAppXProvider::GetManifestedExecutable *)v26);
  v23[0] = 0;
  v21 = 0;
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Package",
    0x29u,
    0x28u);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         v25,
         v23);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v4,
      v18);
  v5 = v23[0];
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23[0] + 176LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v7 = v6(v5, *(_QWORD *)(a1 + 112), &v21);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v7,
      v18);
  v20 = 0;
  v19 = 0;
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  v8 = v25;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v20);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v18);
  v10 = v20;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v12 = v11(v10, v21, *(_QWORD *)(a1 + 96), &v19);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v12,
      v18);
  *a2 = 0;
  v22 = 1;
  v13 = v19;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v19 + 392LL);
  WindowsDeleteString(0);
  *a2 = 0;
  v15 = v14(v13, a2);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)(unsigned int)v15,
      v18);
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v26, v16);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v23);
  DesktopAppXProvider::GetManifestedExecutable::~GetManifestedExecutable((DesktopAppXProvider::GetManifestedExecutable *)v26);
  return a2;
}

```

## disassembly

```asm
0x180024c0c  mov     [rsp-8+arg_10], rbx
0x180024c11  mov     [rsp-8+arg_18], rsi
0x180024c16  push    rbp
0x180024c17  push    rdi
0x180024c18  push    r14
0x180024c1a  lea     rbp, [rsp-0E0h]
0x180024c22  sub     rsp, 1E0h
0x180024c29  mov     rax, cs:__security_cookie
0x180024c30  xor     rax, rsp
0x180024c33  mov     [rbp+0F0h+var_20], rax
0x180024c3a  mov     rsi, rdx
0x180024c3d  mov     r14, rcx
0x180024c40  mov     [rsp+1F0h+var_198], rdx
0x180024c45  mov     [rsp+1F0h+var_1A8], 0
0x180024c4d  lea     rdx, aGetmanifestede; "GetManifestedExecutable"
0x180024c54  lea     rcx, [rbp+0F0h+var_170]
0x180024c58  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180024c5d  lea     rax, ??_7GetManifestedExecutable@DesktopAppXProvider@@6B@; const DesktopAppXProvider::GetManifestedExecutable::`vftable'
0x180024c64  mov     [rbp+0F0h+var_170], rax
0x180024c68  lea     rcx, [rbp+0F0h+var_170]; this
0x180024c6c  call    ?StartActivity@GetManifestedExecutable@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::GetManifestedExecutable::StartActivity(void)
0x180024c71  nop
0x180024c72  mov     [rsp+1F0h+var_1A0], 0
0x180024c7b  mov     [rsp+1F0h+var_1B0], 0
0x180024c84  mov     [rsp+1F0h+var_178], 0
0x180024c8d  mov     r9d, 28h ; '('; unsigned int
0x180024c93  lea     r8d, [r9+1]; unsigned int
0x180024c97  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180024c9e  lea     rcx, [rsp+1F0h+hstringHeader]; hstringHeader
0x180024ca3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180024ca8  nop
0x180024ca9  lea     rdx, [rsp+1F0h+var_1A0]
0x180024cae  mov     rcx, [rsp+1F0h+var_178]
0x180024cb3  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x180024cb8  mov     rcx, [rbp+0F8h]; this
0x180024cbf  test    eax, eax
0x180024cc1  jns     short loc_180024CD8
0x180024cc3  mov     r9d, eax; char *
0x180024cc6  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180024ccd  mov     edx, 0B2h; void *
0x180024cd2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024cd8  mov     rdi, [rsp+1F0h+var_1A0]
0x180024cdd  mov     rax, [rdi]
0x180024ce0  mov     rbx, [rax+0B0h]
0x180024ce7  lea     rcx, [rsp+1F0h+var_1B0]
0x180024cec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024cf1  lea     r8, [rsp+1F0h+var_1B0]
0x180024cf6  mov     rdx, [r14+70h]
0x180024cfa  mov     rcx, rdi
0x180024cfd  mov     rax, rbx
0x180024d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d05  mov     rcx, [rbp+0F8h]; this
0x180024d0c  test    eax, eax
0x180024d0e  jns     short loc_180024D25
0x180024d10  mov     r9d, eax; char *
0x180024d13  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180024d1a  mov     edx, 0B3h; void *
0x180024d1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024d25  mov     [rsp+1F0h+var_1B8], 0
0x180024d2e  mov     [rsp+1F0h+var_1C0], 0
0x180024d37  mov     [rsp+1F0h+var_178], 0
0x180024d40  mov     r9d, 2Ch ; ','; unsigned int
0x180024d46  lea     r8d, [r9+1]; unsigned int
0x180024d4a  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180024d51  lea     rcx, [rsp+1F0h+hstringHeader]; hstringHeader
0x180024d56  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180024d5b  nop
0x180024d5c  mov     rbx, [rsp+1F0h+var_178]
0x180024d61  lea     rcx, [rsp+1F0h+var_1B8]
0x180024d66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024d6b  lea     r8, [rsp+1F0h+var_1B8]
0x180024d70  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180024d77  mov     rcx, rbx
0x180024d7a  call    cs:__imp_RoGetActivationFactory
0x180024d80  mov     rcx, [rbp+0F8h]; this
0x180024d87  test    eax, eax
0x180024d89  jns     short loc_180024DA0
0x180024d8b  mov     r9d, eax; char *
0x180024d8e  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180024d95  mov     edx, 0B7h; void *
0x180024d9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024da0  mov     rdi, [rsp+1F0h+var_1B8]
0x180024da5  mov     rax, [rdi]
0x180024da8  mov     rbx, [rax+68h]
0x180024dac  lea     rcx, [rsp+1F0h+var_1C0]
0x180024db1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024db6  lea     r9, [rsp+1F0h+var_1C0]
0x180024dbb  mov     r8, [r14+60h]
0x180024dbf  mov     rdx, [rsp+1F0h+var_1B0]
0x180024dc4  mov     rcx, rdi
0x180024dc7  mov     rax, rbx
0x180024dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dcf  mov     rcx, [rbp+0F8h]; this
0x180024dd6  test    eax, eax
0x180024dd8  jns     short loc_180024DEF
0x180024dda  mov     r9d, eax; char *
0x180024ddd  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180024de4  mov     edx, 0B8h; void *
0x180024de9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024def  mov     qword ptr [rsi], 0
0x180024df6  mov     [rsp+1F0h+var_1A8], 1
0x180024dfe  mov     rdi, [rsp+1F0h+var_1C0]
0x180024e03  mov     rax, [rdi]
0x180024e06  mov     rbx, [rax+188h]
0x180024e0d  xor     ecx, ecx; string
0x180024e0f  call    cs:__imp_WindowsDeleteString
0x180024e15  mov     qword ptr [rsi], 0
0x180024e1c  mov     rdx, rsi
0x180024e1f  mov     rcx, rdi
0x180024e22  mov     rax, rbx
0x180024e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e2a  mov     rcx, [rbp+0F8h]; this
0x180024e31  test    eax, eax
0x180024e33  jns     short loc_180024E4A
0x180024e35  mov     r9d, eax; char *
0x180024e38  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180024e3f  mov     edx, 0BBh; void *
0x180024e44  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024e4a  lea     rcx, [rbp+0F0h+var_170]
0x180024e4e  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180024e53  nop
0x180024e54  lea     rcx, [rsp+1F0h+var_1C0]
0x180024e59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024e5e  nop
0x180024e5f  lea     rcx, [rsp+1F0h+var_1B8]
0x180024e64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024e69  nop
0x180024e6a  lea     rcx, [rsp+1F0h+var_1B0]
0x180024e6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024e74  nop
0x180024e75  lea     rcx, [rsp+1F0h+var_1A0]
0x180024e7a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024e7f  nop
0x180024e80  lea     rcx, [rbp+0F0h+var_170]; this
0x180024e84  call    ??1GetManifestedExecutable@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::GetManifestedExecutable::~GetManifestedExecutable(void)
0x180024e89  mov     rax, rsi
0x180024e8c  mov     rcx, [rbp+0F0h+var_20]
0x180024e93  xor     rcx, rsp; StackCookie
0x180024e96  call    __security_check_cookie
0x180024e9b  lea     r11, [rsp+1F0h+var_10]
0x180024ea3  mov     rbx, [r11+30h]
0x180024ea7  mov     rsi, [r11+38h]
0x180024eab  mov     rsp, r11
0x180024eae  pop     r14
0x180024eb0  pop     rdi
0x180024eb1  pop     rbp
0x180024eb2  retn
```
