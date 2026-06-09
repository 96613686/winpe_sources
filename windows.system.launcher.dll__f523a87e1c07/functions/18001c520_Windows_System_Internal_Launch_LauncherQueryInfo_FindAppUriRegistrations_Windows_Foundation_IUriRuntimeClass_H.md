# Windows::System::Internal::Launch::LauncherQueryInfo::FindAppUriRegistrations(Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,Windows::Foundation::Collections::IVectorView<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo> * *)

- ea: `0x18001c520`
- end: `0x18001c9e3`
- name: `?FindAppUriRegistrations@LauncherQueryInfo@Launch@Internal@System@Windows@@EEAAJPEAUIUriRuntimeClass@Foundation@5@PEAUHSTRING__@@PEAPEAU?$IVectorView@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@@Collections@75@@Z`
- size: `1219`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800056d0`
- `0x18000f194`
- `0x18001b8d0`
- `0x18001c264`
- `0x18001c520`
- `0x18001c9f0`
- `0x18001caa4`
- `0x18001d4c0`
- `0x1800692bc`
- `0x180072f3c`
- `0x18007da9c`
- `0x18008a030`
- `0x18008a9d8`
- `0x18008dee8`
- `0x1800aae88`
- `0x1800ac844`
- `0x1800d0b6c`
- `0x1800d2b98`
- `0x1800d7608`
- `0x180111010`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18001c6e4`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18001c6e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c69a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c6aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c69a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c6aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c658`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c988`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c658`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c988`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c998`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001c847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001c895`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001c847`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001c895`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18001c723`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18001c723`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x18001c566`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x18001c566`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Windows::System::Internal::Launch::LauncherQueryInfo::FindAppUriRegistrations(
        __int64 a1,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        HSTRING a3,
        _QWORD *a4)
{
  int v7; // esi
  int v8; // eax
  void *v9; // rax
  __int64 v10; // rax
  __int64 v11; // r9
  HSTRING v12; // rcx
  __int64 (__fastcall *v13)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v14; // eax
  __int64 (__fastcall *v15)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v16; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v18; // rax
  SRCacheAppUriHandlerRegistration *v19; // rbx
  SRCacheAppUriHandlerRegistration *v20; // r14
  unsigned int v21; // eax
  int v22; // ecx
  __int64 v23; // rax
  bool v24; // zf
  char v25; // al
  __int64 v26; // rax
  int v27; // eax
  HSTRING_HEADER *v28; // rax
  HRESULT v29; // eax
  HSTRING_HEADER *v30; // rax
  HRESULT v31; // eax
  __int64 v32; // r9
  int v33; // eax
  int View; // eax
  bool v36[4]; // [rsp+20h] [rbp-178h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+24h] [rbp-174h] BYREF
  __int64 v38; // [rsp+28h] [rbp-170h] BYREF
  HSTRING string; // [rsp+30h] [rbp-168h] BYREF
  int v40; // [rsp+38h] [rbp-160h] BYREF
  int v41; // [rsp+3Ch] [rbp-15Ch] BYREF
  HSTRING v42[2]; // [rsp+40h] [rbp-158h] BYREF
  __int128 v43; // [rsp+50h] [rbp-148h] BYREF
  SRCacheAppUriHandlerRegistration *v44[2]; // [rsp+60h] [rbp-138h] BYREF
  __int64 v45; // [rsp+70h] [rbp-128h]
  HSTRING newString[4]; // [rsp+80h] [rbp-118h] BYREF
  HSTRING_HEADER v47; // [rsp+A0h] [rbp-F8h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+C0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v7 = 0;
  packageFamilyNameLength = 0;
  *a4 = 0;
  v41 = 0;
  v8 = IsDeveloperModeEnabled(&v41);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x637,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v8,
      *(int *)v36);
  v38 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::System::Internal::Launch::AppServiceExtensionInfo,Windows::System::Internal::Launch::AppServiceExtensionInfoEqualityPredicate,Windows::System::Internal::Launch::AppServiceExtensionInfoLifetimeTraits,0>>::InternalRelease(&v38);
  v38 = 0;
  v9 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9
    && (v10 = Windows::Foundation::Collections::Internal::Vector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,0,1,0>>::Vector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,0,1,0>>(v9)) != 0 )
  {
    v11 = 0;
    v38 = v10;
  }
  else
  {
    v11 = 2147942414LL;
  }
  if ( (int)v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63A,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)v11,
      *(int *)v36);
  v42[0] = 0;
  v12 = 0;
  string = 0;
  if ( a2 )
  {
    v13 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 88LL);
    WindowsDeleteString(0);
    v42[0] = 0;
    v14 = v13(a2, v42);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x640,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v14,
        *(int *)v36);
    v15 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 104LL);
    WindowsDeleteString(string);
    string = 0;
    v16 = v15(a2, &string);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x641,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v16,
        *(int *)v36);
    v12 = string;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v12, 0);
  v18 = WindowsGetStringRawBuffer(v42[0], 0);
  GetAppUriHandlerRegistrationsFromSRCache(v44, v18, StringRawBuffer);
  v19 = v44[0];
  v20 = v44[1];
  while ( v19 != v20 )
  {
    v40 = 0;
    GetEffectivePackageStatusForUser(0, *((_QWORD *)v19 + 3), &v40);
    if ( (v40 & 0x98) == 0 )
    {
      memset_0(packageFamilyName, 0, 0x82u);
      packageFamilyNameLength = 65;
      v21 = PackageFamilyNameFromFullName(*((PCWSTR *)v19 + 3), &packageFamilyNameLength, packageFamilyName);
      if ( v21 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x654,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
          (const char *)v21,
          *(unsigned int *)v36);
      if ( !ShouldExcludePackageFamilyNameForBrowserReplacment(packageFamilyName, 0) )
      {
        v36[0] = 1;
        if ( !a2 )
          goto LABEL_33;
        if ( !v41
          || (v22 = *((_DWORD *)v19 + 8), ((v22 - 2) & 0xFFFFFFFA) == 0) && v22 != 7
          || (v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      (HSTRING_HEADER *)newString,
                      packageFamilyName),
              v7 |= 1u,
              v24 = !DoesAppUriHandlerRequireForcedPathValidation(*(HSTRING *)(v23 + 24)),
              v25 = 0,
              !v24) )
        {
          v25 = 1;
        }
        if ( (v7 & 1) != 0 )
          v7 &= ~1u;
        if ( !v25 )
          goto LABEL_33;
        v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                (HSTRING_HEADER *)newString,
                packageFamilyName);
        v27 = IsFullUriValidForRegisteredApp(*(HSTRING *)(v26 + 24), a2, a3, v36);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x669,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
            (const char *)(unsigned int)v27,
            *(int *)v36);
        if ( v36[0] )
        {
LABEL_33:
          *(_OWORD *)newString = 0;
          *(_QWORD *)&v43 = *((_QWORD *)v19 + 2);
          v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v47, (const WCHAR **)&v43);
          v29 = WindowsDuplicateString((HSTRING)v28[1].Reserved.Reserved1, &newString[1]);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x670,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
              (const char *)(unsigned int)v29,
              *(int *)v36);
          *(_QWORD *)&v43 = *(_QWORD *)v19;
          v30 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v47, (const WCHAR **)&v43);
          v31 = WindowsDuplicateString((HSTRING)v30[1].Reserved.Reserved1, newString);
          if ( v31 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x671,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
              (const char *)(unsigned int)v31,
              *(int *)v36);
          v43 = *(_OWORD *)newString;
          LOBYTE(v32) = 1;
          v33 = Windows::Foundation::Collections::Internal::Vector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,0,1,0>>::InsertAtInternal(
                  v38,
                  0,
                  &v43,
                  v32);
          if ( v33 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x672,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
              (const char *)(unsigned int)v33,
              *(int *)v36);
        }
      }
    }
    v19 = (SRCacheAppUriHandlerRegistration *)((char *)v19 + 40);
  }
  View = Windows::Foundation::Collections::Internal::Vector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,0,1,0>>::GetView(
           v38,
           a4);
  if ( View < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x677,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)View,
      *(int *)v36);
  if ( v44[0] )
  {
    std::_Destroy_range<std::allocator<SRCacheAppUriHandlerRegistration>>(v44[0], v44[1]);
    std::_Deallocate<16>(
      (_QWORD *)v44[0],
      (const struct std::nothrow_t *)(8 * ((signed __int64)(v45 - (unsigned __int64)v44[0]) >> 3)));
    *(_OWORD *)v44 = 0;
    v45 = 0;
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v42[0]);
  v42[0] = 0;
  if ( v38 )
  {
    v38 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo>,Windows::Foundation::Collections::IIterable<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release();
  }
  return 0;
}

```

## disassembly

```asm
0x18001c520  push    rbx
0x18001c522  push    rsi
0x18001c523  push    rdi
0x18001c524  push    r12
0x18001c526  push    r13
0x18001c528  push    r14
0x18001c52a  push    r15
0x18001c52c  sub     rsp, 160h
0x18001c533  mov     rax, cs:__security_cookie
0x18001c53a  xor     rax, rsp
0x18001c53d  mov     [rsp+198h+var_48], rax
0x18001c545  mov     r15, r9
0x18001c548  mov     r12, r8
0x18001c54b  mov     rdi, rdx
0x18001c54e  xor     r13d, r13d
0x18001c551  mov     esi, r13d
0x18001c554  mov     [rsp+198h+packageFamilyNameLength], r13d
0x18001c559  mov     [r9], r13
0x18001c55c  mov     [rsp+198h+var_15C], r13d
0x18001c561  lea     rcx, [rsp+198h+var_15C]
0x18001c566  call    cs:__imp_IsDeveloperModeEnabled
0x18001c56c  mov     rcx, [rsp+198h]; this
0x18001c574  test    eax, eax
0x18001c576  jns     short loc_18001C58C
0x18001c578  mov     r9d, eax; char *
0x18001c57b  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c582  mov     edx, 637h; void *
0x18001c587  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c58c  mov     [rsp+198h+var_170], r13
0x18001c591  lea     rcx, [rsp+198h+var_170]
0x18001c596  call    ?InternalRelease@?$ComPtr@V?$AgileVector@UAppServiceExtensionInfo@Launch@Internal@System@Windows@@UAppServiceExtensionInfoEqualityPredicate@2345@UAppServiceExtensionInfoLifetimeTraits@2345@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::System::Internal::Launch::AppServiceExtensionInfo,Windows::System::Internal::Launch::AppServiceExtensionInfoEqualityPredicate,Windows::System::Internal::Launch::AppServiceExtensionInfoLifetimeTraits,0>>::InternalRelease(void)
0x18001c59b  mov     [rsp+198h+var_170], r13
0x18001c5a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c5a7  mov     ecx, 90h; unsigned __int64
0x18001c5ac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c5b1  test    rax, rax
0x18001c5b4  jz      short loc_18001C5CE
0x18001c5b6  mov     rcx, rax
0x18001c5b9  call    ??0?$Vector@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@UAppUriHandlerRegistrationInfoEqualityPredicate@2345@UAppUriHandlerRegistrationInfoLifetimeTraits@2345@U?$VectorOptions@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@$0A@$00$0A@@3Collections@Foundation@5@@Internal@Collections@Foundation@Windows@@QEAA@AEBUAppUriHandlerRegistrationInfoEqualityPredicate@Launch@1System@4@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,0,1,0>>::Vector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,0,1,0>>(Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate const &,Windows::Foundation::Collections::Internal::Vector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,0,1,0>>::permission)
0x18001c5be  nop
0x18001c5bf  test    rax, rax
0x18001c5c2  jz      short loc_18001C5CE
0x18001c5c4  mov     r9d, r13d
0x18001c5c7  mov     [rsp+198h+var_170], rax
0x18001c5cc  jmp     short loc_18001C5D4
0x18001c5ce  mov     r9d, 8007000Eh; char *
0x18001c5d4  mov     rcx, [rsp+198h]; this
0x18001c5dc  test    r9d, r9d
0x18001c5df  jns     short loc_18001C5F2
0x18001c5e1  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c5e8  mov     edx, 63Ah; void *
0x18001c5ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c5f2  mov     [rsp+198h+var_158], r13
0x18001c5f7  mov     rcx, r13
0x18001c5fa  mov     [rsp+198h+string], rcx
0x18001c5ff  test    rdi, rdi
0x18001c602  jz      loc_18001C698
0x18001c608  mov     rax, [rdi]
0x18001c60b  mov     rbx, [rax+58h]
0x18001c60f  xor     ecx, ecx; string
0x18001c611  call    cs:__imp_WindowsDeleteString
0x18001c617  mov     [rsp+198h+var_158], r13
0x18001c61c  lea     rdx, [rsp+198h+var_158]
0x18001c621  mov     rcx, rdi
0x18001c624  mov     rax, rbx
0x18001c627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c62c  mov     rcx, [rsp+198h]; this
0x18001c634  test    eax, eax
0x18001c636  jns     short loc_18001C64C
0x18001c638  mov     r9d, eax; char *
0x18001c63b  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c642  mov     edx, 640h; void *
0x18001c647  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c64c  mov     rax, [rdi]
0x18001c64f  mov     rbx, [rax+68h]
0x18001c653  mov     rcx, [rsp+198h+string]; string
0x18001c658  call    cs:__imp_WindowsDeleteString
0x18001c65e  mov     [rsp+198h+string], r13
0x18001c663  lea     rdx, [rsp+198h+string]
0x18001c668  mov     rcx, rdi
0x18001c66b  mov     rax, rbx
0x18001c66e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c673  mov     rcx, [rsp+198h]; this
0x18001c67b  test    eax, eax
0x18001c67d  jns     short loc_18001C693
0x18001c67f  mov     r9d, eax; char *
0x18001c682  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c689  mov     edx, 641h; void *
0x18001c68e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c693  mov     rcx, [rsp+198h+string]; string
0x18001c698  xor     edx, edx; length
0x18001c69a  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c6a0  mov     rbx, rax
0x18001c6a3  xor     edx, edx; length
0x18001c6a5  mov     rcx, [rsp+198h+var_158]; string
0x18001c6aa  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c6b0  mov     r8, rbx
0x18001c6b3  mov     rdx, rax
0x18001c6b6  lea     rcx, [rsp+198h+var_138]
0x18001c6bb  call    ?GetAppUriHandlerRegistrationsFromSRCache@@YA?AV?$vector@USRCacheAppUriHandlerRegistration@@V?$allocator@USRCacheAppUriHandlerRegistration@@@std@@@std@@PEBG0@Z; GetAppUriHandlerRegistrationsFromSRCache(ushort const *,ushort const *)
0x18001c6c0  nop
0x18001c6c1  mov     rbx, [rsp+198h+var_138]
0x18001c6c6  mov     r14, [rsp+198h+var_138+8]
0x18001c6cb  cmp     rbx, r14
0x18001c6ce  jz      loc_18001C907
0x18001c6d4  mov     [rsp+198h+var_160], r13d
0x18001c6d9  lea     r8, [rsp+198h+var_160]
0x18001c6de  mov     rdx, [rbx+18h]
0x18001c6e2  xor     ecx, ecx
0x18001c6e4  call    cs:__imp_GetEffectivePackageStatusForUser
0x18001c6ea  test    byte ptr [rsp+198h+var_160], 98h
0x18001c6ef  jnz     loc_18001C8FE
0x18001c6f5  xor     edx, edx; Val
0x18001c6f7  mov     r8d, 82h; Size
0x18001c6fd  lea     rcx, [rsp+198h+packageFamilyName]; void *
0x18001c705  call    memset_0
0x18001c70a  mov     [rsp+198h+packageFamilyNameLength], 41h ; 'A'
0x18001c712  lea     r8, [rsp+198h+packageFamilyName]; packageFamilyName
0x18001c71a  lea     rdx, [rsp+198h+packageFamilyNameLength]; packageFamilyNameLength
0x18001c71f  mov     rcx, [rbx+18h]; packageFullName
0x18001c723  call    cs:__imp_PackageFamilyNameFromFullName
0x18001c729  mov     rcx, [rsp+198h]; this
0x18001c731  test    eax, eax
0x18001c733  jz      short loc_18001C749
0x18001c735  mov     r9d, eax; char *
0x18001c738  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c73f  mov     edx, 654h; void *
0x18001c744  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001c749  xor     edx, edx; bool
0x18001c74b  lea     rcx, [rsp+198h+packageFamilyName]; lpString2
0x18001c753  call    ?ShouldExcludePackageFamilyNameForBrowserReplacment@@YA_NPEBG_N@Z; ShouldExcludePackageFamilyNameForBrowserReplacment(ushort const *,bool)
0x18001c758  test    al, al
0x18001c75a  jnz     loc_18001C8FE
0x18001c760  mov     [rsp+198h+var_178], 1; int
0x18001c765  test    rdi, rdi
0x18001c768  jz      loc_18001C814
0x18001c76e  cmp     [rsp+198h+var_15C], r13d
0x18001c773  jz      short loc_18001C7AF
0x18001c775  mov     ecx, [rbx+20h]
0x18001c778  lea     eax, [rcx-2]
0x18001c77b  test    eax, 0FFFFFFFAh
0x18001c780  jnz     short loc_18001C787
0x18001c782  cmp     ecx, 7
0x18001c785  jnz     short loc_18001C7AF
0x18001c787  lea     rdx, [rsp+198h+packageFamilyName]; sourceString
0x18001c78f  lea     rcx, [rsp+198h+newString]; hstringHeader
0x18001c797  call    ??$?0$0BAA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[256])
0x18001c79c  or      esi, 1
0x18001c79f  mov     rcx, [rax+18h]; HSTRING
0x18001c7a3  call    ?DoesAppUriHandlerRequireForcedPathValidation@@YA_NPEAUHSTRING__@@@Z; DoesAppUriHandlerRequireForcedPathValidation(HSTRING__ *)
0x18001c7a8  test    al, al
0x18001c7aa  mov     al, r13b
0x18001c7ad  jz      short loc_18001C7B1
0x18001c7af  mov     al, 1
0x18001c7b1  test    sil, 1
0x18001c7b5  jz      short loc_18001C7BA
0x18001c7b7  and     esi, 0FFFFFFFEh
0x18001c7ba  test    al, al
0x18001c7bc  jz      short loc_18001C814
0x18001c7be  lea     rdx, [rsp+198h+packageFamilyName]; sourceString
0x18001c7c6  lea     rcx, [rsp+198h+newString]; hstringHeader
0x18001c7ce  call    ??$?0$0BAA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[256])
0x18001c7d3  nop
0x18001c7d4  lea     r9, [rsp+198h+var_178]; bool *
0x18001c7d9  mov     r8, r12; HSTRING
0x18001c7dc  mov     rdx, rdi; struct Windows::Foundation::IUriRuntimeClass *
0x18001c7df  mov     rcx, [rax+18h]; HSTRING
0x18001c7e3  call    ?IsFullUriValidForRegisteredApp@@YAJPEAUHSTRING__@@PEAUIUriRuntimeClass@Foundation@Windows@@0PEA_N@Z; IsFullUriValidForRegisteredApp(HSTRING__ *,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,bool *)
0x18001c7e8  mov     rcx, [rsp+198h]; this
0x18001c7f0  test    eax, eax
0x18001c7f2  jns     short loc_18001C809
0x18001c7f4  mov     r9d, eax; char *
0x18001c7f7  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c7fe  mov     edx, 669h; void *
0x18001c803  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c809  cmp     [rsp+198h+var_178], r13b
0x18001c80e  jz      loc_18001C8FE
0x18001c814  xorps   xmm0, xmm0
0x18001c817  movups  xmmword ptr [rsp+198h+newString], xmm0
0x18001c81f  mov     rax, [rbx+10h]
0x18001c823  mov     qword ptr [rsp+198h+var_148], rax
0x18001c828  lea     rdx, [rsp+198h+var_148]
0x18001c82d  lea     rcx, [rsp+198h+var_F8]
0x18001c835  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18001c83a  nop
0x18001c83b  lea     rdx, [rsp+198h+newString+8]; newString
0x18001c843  mov     rcx, [rax+18h]; string
0x18001c847  call    cs:__imp_WindowsDuplicateString
0x18001c84d  mov     rcx, [rsp+198h]; this
0x18001c855  test    eax, eax
0x18001c857  jns     short loc_18001C86E
0x18001c859  mov     r9d, eax; char *
0x18001c85c  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c863  mov     edx, 670h; void *
0x18001c868  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c86e  mov     rax, [rbx]
0x18001c871  mov     qword ptr [rsp+198h+var_148], rax
0x18001c876  lea     rdx, [rsp+198h+var_148]
0x18001c87b  lea     rcx, [rsp+198h+var_F8]
0x18001c883  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18001c888  nop
0x18001c889  lea     rdx, [rsp+198h+newString]; newString
0x18001c891  mov     rcx, [rax+18h]; string
0x18001c895  call    cs:__imp_WindowsDuplicateString
0x18001c89b  mov     rcx, [rsp+198h]; this
0x18001c8a3  test    eax, eax
0x18001c8a5  jns     short loc_18001C8BC
0x18001c8a7  mov     r9d, eax; char *
0x18001c8aa  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c8b1  mov     edx, 671h; void *
0x18001c8b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c8bc  movaps  xmm0, xmmword ptr [rsp+198h+newString]
0x18001c8c4  movdqa  [rsp+198h+var_148], xmm0
0x18001c8ca  mov     r9b, 1
0x18001c8cd  lea     r8, [rsp+198h+var_148]
0x18001c8d2  xor     edx, edx
0x18001c8d4  mov     rcx, [rsp+198h+var_170]
0x18001c8d9  call    ?InsertAtInternal@?$Vector@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@UAppUriHandlerRegistrationInfoEqualityPredicate@2345@UAppUriHandlerRegistrationInfoLifetimeTraits@2345@U?$VectorOptions@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@$0A@$00$0A@@3Collections@Foundation@5@@Internal@Collections@Foundation@Windows@@AEAAJIUAppUriHandlerRegistrationInfo@Launch@2System@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,0,1,0>>::InsertAtInternal(uint,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,bool)
0x18001c8de  mov     rcx, [rsp+198h]; this
0x18001c8e6  test    eax, eax
0x18001c8e8  jns     short loc_18001C8FE
0x18001c8ea  mov     r9d, eax; char *
0x18001c8ed  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c8f4  mov     edx, 672h; void *
0x18001c8f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c8fe  add     rbx, 28h ; '('
0x18001c902  jmp     loc_18001C6CB
0x18001c907  mov     rdx, r15
0x18001c90a  mov     rcx, [rsp+198h+var_170]
0x18001c90f  call    ?GetView@?$Vector@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@UAppUriHandlerRegistrationInfoEqualityPredicate@2345@UAppUriHandlerRegistrationInfoLifetimeTraits@2345@U?$VectorOptions@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@$0A@$00$0A@@3Collections@Foundation@5@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IVectorView@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoEqualityPredicate,Windows::System::Internal::Launch::AppUriHandlerRegistrationInfoLifetimeTraits,Windows::Foundation::Collections::Internal::VectorOptions<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo,0,1,0>>::GetView(Windows::Foundation::Collections::IVectorView<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo> * *)
0x18001c914  mov     rcx, [rsp+198h]; this
0x18001c91c  test    eax, eax
0x18001c91e  jns     short loc_18001C935
0x18001c920  mov     r9d, eax; char *
0x18001c923  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18001c92a  mov     edx, 677h; void *
0x18001c92f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c935  mov     rcx, [rsp+198h+var_138]; this
0x18001c93a  test    rcx, rcx
0x18001c93d  jz      short loc_18001C983
0x18001c93f  mov     rdx, [rsp+198h+var_138+8]
0x18001c944  call    ??$_Destroy_range@V?$allocator@USRCacheAppUriHandlerRegistration@@@std@@@std@@YAXPEAUSRCacheAppUriHandlerRegistration@@QEAU1@AEAV?$allocator@USRCacheAppUriHandlerRegistration@@@0@@Z; std::_Destroy_range<std::allocator<SRCacheAppUriHandlerRegistration>>(SRCacheAppUriHandlerRegistration *,SRCacheAppUriHandlerRegistration * const,std::allocator<SRCacheAppUriHandlerRegistration> &)
0x18001c949  mov     rcx, [rsp+198h+var_138]
0x18001c94e  mov     rax, [rsp+198h+var_128]
0x18001c953  sub     rax, rcx
0x18001c956  sar     rax, 3
0x18001c95a  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18001c964  imul    rax, rdx
0x18001c968  lea     rdx, [rax+rax*4]
0x18001c96c  shl     rdx, 3
0x18001c970  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c975  xorps   xmm0, xmm0
0x18001c978  movdqu  xmmword ptr [rsp+198h+var_138], xmm0
0x18001c97e  mov     [rsp+198h+var_128], r13
0x18001c983  mov     rcx, [rsp+198h+string]; string
0x18001c988  call    cs:__imp_WindowsDeleteString
0x18001c98e  mov     [rsp+198h+string], r13
0x18001c993  mov     rcx, [rsp+198h+var_158]; string
0x18001c998  call    cs:__imp_WindowsDeleteString
0x18001c99e  mov     [rsp+198h+var_158], r13
0x18001c9a3  mov     rcx, [rsp+198h+var_170]
0x18001c9a8  test    rcx, rcx
0x18001c9ab  jz      short loc_18001C9B7
0x18001c9ad  mov     [rsp+198h+var_170], r13
0x18001c9b2  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IVector@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@@Collections@Foundation@Windows@@U?$IIterable@UAppUriHandlerRegistrationInfo@Launch@Internal@System@Windows@@@567@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::Collections::IVector<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo>,Windows::Foundation::Collections::IIterable<Windows::System::Internal::Launch::AppUriHandlerRegistrationInfo>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::Release(void)
0x18001c9b7  xor     eax, eax
0x18001c9b9  jmp     short loc_18001C9BF
0x18001c9bb  mov     eax, [rsp+198h+packageFamilyNameLength]
0x18001c9bf  mov     rcx, [rsp+198h+var_48]
0x18001c9c7  xor     rcx, rsp; StackCookie
0x18001c9ca  call    __security_check_cookie
0x18001c9cf  add     rsp, 160h
0x18001c9d6  pop     r15
0x18001c9d8  pop     r14
0x18001c9da  pop     r13
0x18001c9dc  pop     r12
0x18001c9de  pop     rdi
0x18001c9df  pop     rsi
0x18001c9e0  pop     rbx
0x18001c9e1  retn
```
