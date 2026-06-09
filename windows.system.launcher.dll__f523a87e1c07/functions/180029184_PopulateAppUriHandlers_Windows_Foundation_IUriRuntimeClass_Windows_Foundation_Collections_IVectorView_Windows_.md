# PopulateAppUriHandlers(Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *> *,HSTRING__ *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *> * *)

- ea: `0x180029184`
- end: `0x1800295b2`
- name: `?PopulateAppUriHandlers@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAU?$IVectorView@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@Collections@23@PEAUHSTRING__@@PEAPEAU?$IVectorView@PEAUHSTRING__@@@523@PEAPEAU4523@@Z`
- size: `1070`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028e3c`
- `0x1800d3280`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180021a88`
- `0x180029184`
- `0x1800295b8`
- `0x180064e14`
- `0x180072f14`
- `0x18007da9c`
- `0x1800d7608`
- `0x180111010`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x180029321`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x180029321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800292e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029459`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800292e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029459`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294b7`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x180029237`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x180029237`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 PopulateAppUriHandlers(struct Windows::Foundation::IUriRuntimeClass *a1, __int64 a2, HSTRING a3, ...)
{
  __int64 v6; // r12
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, _QWORD *); // rbx
  int v18; // eax
  int v19; // esi
  int v20; // r14d
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  PCWSTR StringRawBuffer; // rax
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rcx
  HSTRING v35; // [rsp+20h] [rbp-51h] BYREF
  HSTRING string; // [rsp+28h] [rbp-49h] BYREF
  __int64 v37; // [rsp+30h] [rbp-41h] BYREF
  __int64 v38; // [rsp+38h] [rbp-39h] BYREF
  int v39; // [rsp+40h] [rbp-31h] BYREF
  int v40; // [rsp+44h] [rbp-2Dh] BYREF
  int v41; // [rsp+48h] [rbp-29h] BYREF
  __int64 v42; // [rsp+50h] [rbp-21h] BYREF
  int v43; // [rsp+58h] [rbp-19h] BYREF
  int *v44; // [rsp+60h] [rbp-11h]
  int v45; // [rsp+68h] [rbp-9h]
  _QWORD v46[10]; // [rsp+70h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]
  __int64 v48; // [rsp+E8h] [rbp+77h] BYREF
  va_list va; // [rsp+E8h] [rbp+77h]
  __int64 v50; // [rsp+F0h] [rbp+7Fh] BYREF
  va_list va1; // [rsp+F0h] [rbp+7Fh]
  va_list va2; // [rsp+F8h] [rbp+87h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v48 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v50 = va_arg(va2, _QWORD);
  v6 = v50;
  *(_QWORD *)v50 = 0;
  v37 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v8 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,0>>(
         v7,
         &v37);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v8,
      (int)v35);
    v10 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v9;
  }
  v38 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  v13 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
          v12,
          &v38);
  v9 = v13;
  if ( v13 < 0 )
  {
    v14 = 829;
    goto LABEL_45;
  }
  v39 = 0;
  v13 = IsDeveloperModeEnabled(&v39);
  v9 = v13;
  if ( v13 < 0 )
  {
    v14 = 833;
LABEL_45:
    v32 = (unsigned int)v13;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)v32,
      (int)v35);
LABEL_47:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    return v9;
  }
  v41 = 0;
  v42 = a2;
  v44 = &v41;
  v45 = 0;
  v46[0] = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 56LL))(a2, &v43);
  *v44 = v15;
  if ( v15 >= 0 && v43 )
  {
    v16 = v42;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v42 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v46);
    v18 = v17(v16, 0, v46);
    *v44 = v18;
  }
  v19 = 0;
  v20 = v43;
  while ( v19 != v20 && *v44 >= 0 )
  {
    string = 0;
    v21 = v46[0];
    v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v46[0] + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v23 = v22(v21, &string);
    v9 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x349,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v23,
        (int)v35);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v46);
      v30 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v31 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      return v9;
    }
    LODWORD(v50) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    GetEffectivePackageStatusForUser(0, StringRawBuffer, (__int64 *)va1);
    if ( (v50 & 0x98) == 0 )
    {
      v40 = 0;
      v25 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v46[0] + 128LL))(v46[0], &v40);
      v9 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x351,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
          (const char *)(unsigned int)v25,
          (int)v35);
        goto LABEL_35;
      }
      v35 = 0;
      v26 = v46[0];
      v27 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v46[0] + 104LL);
      WindowsDeleteString(0);
      v35 = 0;
      v28 = v27(v26, &v35);
      v9 = v28;
      if ( v28 < 0 )
      {
        v29 = 852;
LABEL_33:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
          (const char *)(unsigned int)v28,
          (int)v35);
        WindowsDeleteString(v35);
        v35 = 0;
LABEL_35:
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v46);
        goto LABEL_47;
      }
      if ( !ShouldExcludePackageFamilyNameForBrowserReplacment(v35, 0) )
      {
        LOBYTE(v48) = 1;
        if ( !a1
          || v39 && (((v40 - 2) & 0xFFFFFFFA) != 0 || v40 == 7) && !DoesAppUriHandlerRequireForcedPathValidation(v35) )
        {
          goto LABEL_27;
        }
        v28 = IsFullUriValidForRegisteredApp(v35, a1, a3, (bool *)va);
        v9 = v28;
        if ( v28 < 0 )
        {
          v29 = 873;
          goto LABEL_33;
        }
        if ( (_BYTE)v48 )
        {
LABEL_27:
          v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 104LL))(v37, v46[0]);
          v9 = v28;
          if ( v28 < 0 )
          {
            v29 = 879;
            goto LABEL_33;
          }
        }
      }
      WindowsDeleteString(v35);
      v35 = 0;
    }
    WindowsDeleteString(string);
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(
      &v42,
      (unsigned int)++v19);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v46);
  v9 = v41;
  if ( v41 < 0 )
  {
    v32 = (unsigned int)v41;
    v14 = 891;
    goto LABEL_46;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 64LL))(v37, v6);
  v9 = v13;
  if ( v13 < 0 )
  {
    v14 = 892;
    goto LABEL_45;
  }
  v33 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x180029184  mov     [rsp-8+arg_18], r9
0x180029189  push    rbp
0x18002918a  push    rbx
0x18002918b  push    rsi
0x18002918c  push    rdi
0x18002918d  push    r12
0x18002918f  push    r13
0x180029191  push    r14
0x180029193  push    r15
0x180029195  lea     rbp, [rsp-17h]
0x18002919a  sub     rsp, 88h
0x1800291a1  mov     r13, r8
0x1800291a4  mov     rdi, rdx
0x1800291a7  mov     r15, rcx
0x1800291aa  xor     esi, esi
0x1800291ac  mov     r12, [rbp+4Fh+arg_20]
0x1800291b0  mov     [r12], rsi
0x1800291b4  mov     [rbp+4Fh+var_90], rsi
0x1800291b8  lea     rcx, [rbp+4Fh+var_90]
0x1800291bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800291c1  lea     rdx, [rbp+4Fh+var_90]
0x1800291c5  call    ??$CreateExternalObjectVector@VAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@V?$AgileVector@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,0> * *)
0x1800291ca  mov     ebx, eax
0x1800291cc  test    eax, eax
0x1800291ce  jns     short loc_18002920A
0x1800291d0  mov     rcx, [rbp+57h]; this
0x1800291d4  mov     r9d, eax; char *
0x1800291d7  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800291de  mov     edx, 33Bh; void *
0x1800291e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800291e8  nop
0x1800291e9  mov     rcx, [rbp+4Fh+var_90]
0x1800291ed  test    rcx, rcx
0x1800291f0  jz      short loc_180029203
0x1800291f2  mov     [rbp+4Fh+var_90], rsi
0x1800291f6  mov     rax, [rcx]
0x1800291f9  mov     rax, [rax+10h]
0x1800291fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029202  nop
0x180029203  mov     eax, ebx
0x180029205  jmp     loc_18002959E
0x18002920a  mov     [rbp+4Fh+var_88], rsi
0x18002920e  lea     rcx, [rbp+4Fh+var_88]
0x180029212  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029217  lea     rdx, [rbp+4Fh+var_88]
0x18002921b  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x180029220  mov     ebx, eax
0x180029222  test    eax, eax
0x180029224  jns     short loc_180029230
0x180029226  mov     edx, 33Dh
0x18002922b  jmp     loc_18002953C
0x180029230  mov     [rbp+4Fh+var_80], esi
0x180029233  lea     rcx, [rbp+4Fh+var_80]
0x180029237  call    cs:__imp_IsDeveloperModeEnabled
0x18002923d  mov     ebx, eax
0x18002923f  test    eax, eax
0x180029241  jns     short loc_18002924D
0x180029243  mov     edx, 341h
0x180029248  jmp     loc_18002953C
0x18002924d  mov     [rbp+4Fh+var_78], esi
0x180029250  mov     [rbp+4Fh+var_70], rdi
0x180029254  lea     rax, [rbp+4Fh+var_78]
0x180029258  mov     [rbp+4Fh+var_60], rax
0x18002925c  mov     [rbp+4Fh+var_58], esi
0x18002925f  mov     [rbp+4Fh+var_50], rsi
0x180029263  mov     rax, [rdi]
0x180029266  lea     rdx, [rbp+4Fh+var_68]
0x18002926a  mov     rcx, rdi
0x18002926d  mov     rax, [rax+38h]
0x180029271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029276  mov     rcx, [rbp+4Fh+var_60]
0x18002927a  mov     [rcx], eax
0x18002927c  xor     edi, edi
0x18002927e  test    eax, eax
0x180029280  js      short loc_1800292B4
0x180029282  cmp     [rbp+4Fh+var_68], edi
0x180029285  jbe     short loc_1800292B4
0x180029287  mov     rdi, [rbp+4Fh+var_70]
0x18002928b  mov     rax, [rdi]
0x18002928e  mov     rbx, [rax+30h]
0x180029292  lea     rcx, [rbp+4Fh+var_50]
0x180029296  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002929b  lea     r8, [rbp+4Fh+var_50]
0x18002929f  xor     edx, edx
0x1800292a1  mov     rcx, rdi
0x1800292a4  mov     rax, rbx
0x1800292a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292ac  mov     rcx, [rbp+4Fh+var_60]
0x1800292b0  mov     [rcx], eax
0x1800292b2  xor     edi, edi
0x1800292b4  mov     esi, edi
0x1800292b6  mov     r14d, [rbp+4Fh+var_68]
0x1800292ba  mov     rax, [rbp+4Fh+var_60]
0x1800292be  cmp     esi, r14d
0x1800292c1  jz      loc_180029504
0x1800292c7  cmp     [rax], edi
0x1800292c9  jl      loc_180029504
0x1800292cf  mov     [rbp+4Fh+string], rdi
0x1800292d3  mov     rdi, [rbp+4Fh+var_50]
0x1800292d7  mov     rax, [rdi]
0x1800292da  mov     rbx, [rax+70h]
0x1800292de  xor     ecx, ecx; string
0x1800292e0  call    cs:__imp_WindowsDeleteString
0x1800292e6  mov     [rbp+4Fh+string], 0
0x1800292ee  lea     rdx, [rbp+4Fh+string]
0x1800292f2  mov     rcx, rdi
0x1800292f5  mov     rax, rbx
0x1800292f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292fd  mov     ebx, eax
0x1800292ff  xor     edi, edi
0x180029301  test    eax, eax
0x180029303  js      loc_18002949A
0x180029309  mov     dword ptr [rbp+4Fh+arg_20], edi
0x18002930c  xor     edx, edx; length
0x18002930e  mov     rcx, [rbp+4Fh+string]; string
0x180029312  call    cs:__imp_WindowsGetStringRawBuffer
0x180029318  lea     r8, [rbp+4Fh+arg_20]
0x18002931c  mov     rdx, rax
0x18002931f  xor     ecx, ecx
0x180029321  call    cs:__imp_GetEffectivePackageStatusForUser
0x180029327  test    byte ptr [rbp+4Fh+arg_20], 98h
0x18002932b  jnz     loc_180029412
0x180029331  mov     [rbp+4Fh+var_7C], edi
0x180029334  mov     rcx, [rbp+4Fh+var_50]
0x180029338  mov     rax, [rcx]
0x18002933b  lea     rdx, [rbp+4Fh+var_7C]
0x18002933f  mov     rax, [rax+80h]
0x180029346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002934b  mov     ebx, eax
0x18002934d  test    eax, eax
0x18002934f  js      loc_180029465
0x180029355  mov     [rbp+4Fh+var_A0], rdi
0x180029359  mov     rdi, [rbp+4Fh+var_50]
0x18002935d  mov     rax, [rdi]
0x180029360  mov     rbx, [rax+68h]
0x180029364  xor     ecx, ecx; string
0x180029366  call    cs:__imp_WindowsDeleteString
0x18002936c  mov     [rbp+4Fh+var_A0], 0
0x180029374  lea     rdx, [rbp+4Fh+var_A0]
0x180029378  mov     rcx, rdi
0x18002937b  mov     rax, rbx
0x18002937e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029383  mov     ebx, eax
0x180029385  xor     edi, edi
0x180029387  test    eax, eax
0x180029389  js      loc_18002943C
0x18002938f  xor     edx, edx; bool
0x180029391  mov     rcx, [rbp+4Fh+var_A0]; HSTRING
0x180029395  call    ?ShouldExcludePackageFamilyNameForBrowserReplacment@@YA_NPEAUHSTRING__@@_N@Z; ShouldExcludePackageFamilyNameForBrowserReplacment(HSTRING__ *,bool)
0x18002939a  test    al, al
0x18002939c  jnz     short loc_180029404
0x18002939e  mov     byte ptr [rbp+4Fh+arg_18], 1
0x1800293a2  test    r15, r15
0x1800293a5  jz      short loc_1800293EA
0x1800293a7  cmp     [rbp+4Fh+var_80], edi
0x1800293aa  jz      short loc_1800293CB
0x1800293ac  mov     ecx, [rbp+4Fh+var_7C]
0x1800293af  lea     eax, [rcx-2]
0x1800293b2  test    eax, 0FFFFFFFAh
0x1800293b7  jnz     short loc_1800293BE
0x1800293b9  cmp     ecx, 7
0x1800293bc  jnz     short loc_1800293CB
0x1800293be  mov     rcx, [rbp+4Fh+var_A0]; HSTRING
0x1800293c2  call    ?DoesAppUriHandlerRequireForcedPathValidation@@YA_NPEAUHSTRING__@@@Z; DoesAppUriHandlerRequireForcedPathValidation(HSTRING__ *)
0x1800293c7  test    al, al
0x1800293c9  jz      short loc_1800293EA
0x1800293cb  lea     r9, [rbp+4Fh+arg_18]; bool *
0x1800293cf  mov     r8, r13; HSTRING
0x1800293d2  mov     rdx, r15; struct Windows::Foundation::IUriRuntimeClass *
0x1800293d5  mov     rcx, [rbp+4Fh+var_A0]; HSTRING
0x1800293d9  call    ?IsFullUriValidForRegisteredApp@@YAJPEAUHSTRING__@@PEAUIUriRuntimeClass@Foundation@Windows@@0PEA_N@Z; IsFullUriValidForRegisteredApp(HSTRING__ *,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,bool *)
0x1800293de  mov     ebx, eax
0x1800293e0  test    eax, eax
0x1800293e2  js      short loc_18002942E
0x1800293e4  cmp     byte ptr [rbp+4Fh+arg_18], dil
0x1800293e8  jz      short loc_180029404
0x1800293ea  mov     rcx, [rbp+4Fh+var_90]
0x1800293ee  mov     rax, [rcx]
0x1800293f1  mov     rdx, [rbp+4Fh+var_50]
0x1800293f5  mov     rax, [rax+68h]
0x1800293f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293fe  mov     ebx, eax
0x180029400  test    eax, eax
0x180029402  js      short loc_180029435
0x180029404  mov     rcx, [rbp+4Fh+var_A0]; string
0x180029408  call    cs:__imp_WindowsDeleteString
0x18002940e  mov     [rbp+4Fh+var_A0], rdi
0x180029412  mov     rcx, [rbp+4Fh+string]; string
0x180029416  call    cs:__imp_WindowsDeleteString
0x18002941c  inc     esi
0x18002941e  mov     edx, esi
0x180029420  lea     rcx, [rbp+4Fh+var_70]
0x180029424  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVAppUriHandlerGroup@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(uint)
0x180029429  jmp     loc_1800292BA
0x18002942e  mov     edx, 369h
0x180029433  jmp     short loc_180029441
0x180029435  mov     edx, 36Fh
0x18002943a  jmp     short loc_180029441
0x18002943c  mov     edx, 354h; void *
0x180029441  mov     rcx, [rbp+57h]; this
0x180029445  mov     r9d, eax; char *
0x180029448  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002944f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029454  nop
0x180029455  mov     rcx, [rbp+4Fh+var_A0]; string
0x180029459  call    cs:__imp_WindowsDeleteString
0x18002945f  mov     [rbp+4Fh+var_A0], rdi
0x180029463  jmp     short loc_18002947E
0x180029465  mov     rcx, [rbp+57h]; this
0x180029469  mov     r9d, eax; char *
0x18002946c  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180029473  mov     edx, 351h; void *
0x180029478  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002947d  nop
0x18002947e  mov     rcx, [rbp+4Fh+string]; string
0x180029482  call    cs:__imp_WindowsDeleteString
0x180029488  mov     [rbp+4Fh+string], rdi
0x18002948c  lea     rcx, [rbp+4Fh+var_50]
0x180029490  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029495  jmp     loc_180029550
0x18002949a  mov     rcx, [rbp+57h]; this
0x18002949e  mov     r9d, ebx; char *
0x1800294a1  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800294a8  mov     edx, 349h; void *
0x1800294ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800294b2  nop
0x1800294b3  mov     rcx, [rbp+4Fh+string]; string
0x1800294b7  call    cs:__imp_WindowsDeleteString
0x1800294bd  mov     [rbp+4Fh+string], rdi
0x1800294c1  lea     rcx, [rbp+4Fh+var_50]
0x1800294c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800294ca  nop
0x1800294cb  mov     rcx, [rbp+4Fh+var_88]
0x1800294cf  test    rcx, rcx
0x1800294d2  jz      short loc_1800294E5
0x1800294d4  mov     [rbp+4Fh+var_88], rdi
0x1800294d8  mov     rax, [rcx]
0x1800294db  mov     rax, [rax+10h]
0x1800294df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294e4  nop
0x1800294e5  mov     rcx, [rbp+4Fh+var_90]
0x1800294e9  test    rcx, rcx
0x1800294ec  jz      short loc_1800294FF
0x1800294ee  mov     [rbp+4Fh+var_90], rdi
0x1800294f2  mov     rax, [rcx]
0x1800294f5  mov     rax, [rax+10h]
0x1800294f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294fe  nop
0x1800294ff  jmp     loc_180029203
0x180029504  lea     rcx, [rbp+4Fh+var_50]
0x180029508  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002950d  mov     ebx, [rbp+4Fh+var_78]
0x180029510  test    ebx, ebx
0x180029512  jns     short loc_18002951E
0x180029514  mov     r9d, ebx
0x180029517  mov     edx, 37Bh
0x18002951c  jmp     short loc_18002953F
0x18002951e  mov     rcx, [rbp+4Fh+var_90]
0x180029522  mov     rax, [rcx]
0x180029525  mov     rdx, r12
0x180029528  mov     rax, [rax+40h]
0x18002952c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029531  mov     ebx, eax
0x180029533  test    eax, eax
0x180029535  jns     short loc_180029568
0x180029537  mov     edx, 37Ch; void *
0x18002953c  mov     r9d, eax; char *
0x18002953f  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180029546  mov     rcx, [rbp+57h]; this
0x18002954a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002954f  nop
0x180029550  lea     rcx, [rbp+4Fh+var_88]
0x180029554  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029559  nop
0x18002955a  lea     rcx, [rbp+4Fh+var_90]
0x18002955e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029563  jmp     loc_180029203
0x180029568  mov     rcx, [rbp+4Fh+var_88]
0x18002956c  test    rcx, rcx
0x18002956f  jz      short loc_180029582
0x180029571  mov     [rbp+4Fh+var_88], rdi
0x180029575  mov     rax, [rcx]
0x180029578  mov     rax, [rax+10h]
0x18002957c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029581  nop
0x180029582  mov     rcx, [rbp+4Fh+var_90]
0x180029586  test    rcx, rcx
0x180029589  jz      short loc_18002959C
0x18002958b  mov     [rbp+4Fh+var_90], rdi
0x18002958f  mov     rax, [rcx]
0x180029592  mov     rax, [rax+10h]
0x180029596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002959b  nop
0x18002959c  xor     eax, eax
0x18002959e  add     rsp, 88h
0x1800295a5  pop     r15
0x1800295a7  pop     r14
0x1800295a9  pop     r13
0x1800295ab  pop     r12
0x1800295ad  pop     rdi
  ... truncated ...
```
