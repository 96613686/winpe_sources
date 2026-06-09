# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComClassRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)

- ea: `0x18003b94c`
- end: `0x18003bf0a`
- name: `??$GetInstalledPackagesContainingEntry@UComClassRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z`
- size: `1470`
- prototype: `__int64 __usercall@<rax>(PackageListBuffer *this@<rcx>, char, PackageFilter *)`
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18009515c`
- `0x1800ad46c`
- `0x1800e5110`
- `0x1800ea530`

## callees

- `0x1800065a4`
- `0x1800210f8`
- `0x180024fd0`
- `0x18003b94c`
- `0x18003bf10`
- `0x18003c3f4`
- `0x18003c4f8`
- `0x18004b0f0`
- `0x1800535d0`
- `0x180071404`
- `0x180072624`
- `0x180095c0c`
- `0x1800a6b6c`
- `0x1800e06c0`
- `0x1800e06d8`
- `0x1800e482c`
- `0x1800e5844`
- `0x1800e5898`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bcde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003be10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003beea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bcde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003be10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003beea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bd4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003be5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003be6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bd4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003be5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003be6f`

## string_xrefs

- `0x18003bb58`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18003bbfe`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18003bc35`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18003bd15`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18003bdf9`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18003be7b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18003bed7`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18003be9c`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x18003beaa`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComClassRegistrationEntryProperties>(
        PackageListBuffer *this,
        __int64 a2,
        __int64 *a3,
        GUID *a4,
        char a5,
        PackageFilter *a6)
{
  int v10; // eax
  unsigned __int64 v11; // r15
  int v12; // ebx
  unsigned int v13; // r13d
  __int64 v14; // rax
  HSTRING v15; // rbx
  struct PackageIdAndInstallOrders *v16; // rdi
  int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // r15d
  _QWORD *i; // rdi
  _QWORD *j; // rdi
  int v23; // eax
  int v24; // r15d
  unsigned int v25; // edi
  int ComPackageInstallOrder; // eax
  int v27; // eax
  const unsigned __int16 *PackageFullName; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v30; // rdx
  PCWSTR v31; // rdi
  const char *v32; // rax
  __int64 v33; // rdx
  int v34; // [rsp+20h] [rbp-69h]
  HSTRING *p_string; // [rsp+20h] [rbp-69h]
  char *v36; // [rsp+28h] [rbp-61h]
  _BYTE v37[8]; // [rsp+40h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v39; // [rsp+50h] [rbp-39h] BYREF
  __int64 v40; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v41; // [rsp+60h] [rbp-29h]
  int v42; // [rsp+64h] [rbp-25h]
  int v43; // [rsp+68h] [rbp-21h]
  int v44; // [rsp+6Ch] [rbp-1Dh]
  _QWORD v45[2]; // [rsp+70h] [rbp-19h] BYREF
  char v46; // [rsp+80h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
    && a6
    && !PackageFilter::GetPackageCount(a6) )
  {
    return 0;
  }
  v40 = 0;
  v10 =  IPackagedComCatalogContext::`vcall'{288,{flat}}(a3, a4, &v40);
  v11 = 0;
  v12 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF65,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v10,
      v34);
    return (unsigned int)v12;
  }
  else
  {
    v45[0] = a3;
    v45[1] = &v40;
    v13 = 0;
    v46 = 1;
    while ( 1 )
    {
      v37[0] = 0;
      string = 0;
      WindowsDeleteString(0);
      p_string = &string;
      string = 0;
      v12 =  IPackagedComCatalogContext::`vcall'{296,{flat}}(a3, v40, v13, v37);
      if ( v12 < 0 )
      {
        v30 = 3953;
        goto LABEL_66;
      }
      if ( !v37[0] )
        break;
      if ( a6 )
      {
        while ( 1 )
        {
          if ( v11 >= PackageFilter::GetPackageCount(a6) )
          {
            WindowsDeleteString(string);
            v11 = 0;
            goto LABEL_40;
          }
          PackageFullName = PackageFilter::GetPackageFullName(a6, v11);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( PackageNamesMatch(StringRawBuffer, PackageFullName) )
            break;
          ++v11;
        }
        v11 = 0;
      }
      *(_WORD *)((char *)&v41 + 1) = *(_WORD *)((char *)&v39 + 1);
      HIBYTE(v41) = BYTE3(v39);
      *(_WORD *)((char *)&v43 + 1) = *(_WORD *)((char *)&v39 + 1);
      HIBYTE(v43) = BYTE3(v39);
      LOBYTE(v41) = 0;
      v42 = 0;
      LOBYTE(v43) = 0;
      v44 = 0;
      LOBYTE(v39) = 0;
      HIDWORD(v39) = 0;
      v12 = PackageListBuffer::AddPackage((_DWORD)this, (unsigned int)&string, (_DWORD)v39, v43, v41);
      if ( v12 < 0 )
      {
        v30 = 3978;
LABEL_66:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v12,
          (int)p_string);
        WindowsDeleteString(string);
        string = 0;
        wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v45);
        return (unsigned int)v12;
      }
      WindowsDeleteString(string);
LABEL_40:
      ++v13;
    }
    WindowsDeleteString(string);
    v14 = *a3;
    v46 = 0;
    (*(void (__fastcall **)(__int64 *, __int64))(v14 + 32))(a3, v40);
    v15 = 0;
    v40 = 0;
    v39 = 0;
    if ( *((_DWORD *)this + 34) )
    {
      OpaqueString::operator=(&v39, *((_QWORD *)this + 16));
      v15 = v39;
    }
    if ( !a5 )
      goto LABEL_9;
    LODWORD(string) = 0;
    if ( !a2
      || (v27 = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)a2 + 96LL))(a2, 1, &string),
          v25 = v27,
          v27 >= 0) )
    {
      for ( i = (_QWORD *)*((_QWORD *)this + 16);
            i != (_QWORD *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34));
            i += 4 )
      {
        ComPackageInstallOrder = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *i, a2, 1);
        v24 = ComPackageInstallOrder;
        if ( ComPackageInstallOrder < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFBA,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)ComPackageInstallOrder,
            (_DWORD)i + 8);
          if ( (_DWORD)string )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
LABEL_26:
          v25 = v24;
          goto LABEL_27;
        }
      }
      if ( (_DWORD)string )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
      for ( j = (_QWORD *)*((_QWORD *)this + 16);
            j != (_QWORD *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34));
            j += 4 )
      {
        v23 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *j, a2, 2);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFC9,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v23,
            (_DWORD)j + 24);
          goto LABEL_26;
        }
      }
LABEL_9:
      v16 = (struct PackageIdAndInstallOrders *)*((_QWORD *)this + 16);
      while ( v16 != (struct PackageIdAndInstallOrders *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34)) )
      {
        v17 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *(_QWORD *)v16, a2, 0);
        v19 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFD4,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v17,
            (_DWORD)v16 + 16);
          WindowsDeleteString(v15);
          wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v45);
          return v19;
        }
        if ( *((_BYTE *)v16 + 8) && *((_BYTE *)v16 + 24) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v18);
        if ( *((_BYTE *)v16 + 16) || *((_BYTE *)v16 + 8) || *((_BYTE *)v16 + 24) )
          v16 = (struct PackageIdAndInstallOrders *)((char *)v16 + 32);
        else
          v16 = PackageListBuffer::RemoveAt(this, v16);
      }
      if ( v15 && !*((_DWORD *)this + 34) )
      {
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &string,
          0);
        if ( (int)GetIdString(a4, &string) >= 0 )
        {
          v31 = WindowsGetStringRawBuffer(v15, 0);
          v36 = (char *)WindowsGetStringRawBuffer(string, 0);
          if ( a5 )
          {
            v32 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to t"
                  "he caller. Package may not be installed for user.";
            v33 = 4086;
          }
          else
          {
            v32 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to t"
                  "he caller. Lookup was performed without per-user state, which may indicate that the caller was elevate"
                  "d, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).";
            v33 = 4092;
          }
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)v33,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)0x80040154LL,
            (int)v32,
            v36,
            v31);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
      }
      WindowsDeleteString(v15);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB4,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v27,
      (int)&string);
    if ( (_DWORD)string )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
LABEL_27:
    WindowsDeleteString(v15);
    return v25;
  }
}

```

## disassembly

```asm
0x18003b94c  mov     [rsp-8+rguid], r9
0x18003b951  push    rbp
0x18003b952  push    rbx
0x18003b953  push    rsi
0x18003b954  push    rdi
0x18003b955  push    r12
0x18003b957  push    r13
0x18003b959  push    r14
0x18003b95b  push    r15
0x18003b95d  lea     rbp, [rsp-0Fh]
0x18003b962  sub     rsp, 98h
0x18003b969  mov     r15, r9
0x18003b96c  mov     r12, r8
0x18003b96f  mov     r14, rdx
0x18003b972  mov     rsi, rcx
0x18003b975  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18003b97c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18003b981  mov     rdi, [rbp+47h+arg_28]
0x18003b985  test    al, al
0x18003b987  jnz     loc_18003BCF2
0x18003b98d  lea     r8, [rbp+47h+var_78]
0x18003b991  mov     [rbp+47h+var_78], 0
0x18003b999  mov     rdx, r15
0x18003b99c  mov     rcx, r12
0x18003b99f  call    ??_9IPackagedComCatalogContext@@$BBCA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{288,{flat}}
0x18003b9a4  xor     r15d, r15d
0x18003b9a7  mov     ebx, eax
0x18003b9a9  test    eax, eax
0x18003b9ab  js      loc_18003BD11
0x18003b9b1  lea     rax, [rbp+47h+var_78]
0x18003b9b5  mov     [rbp+47h+var_60], r12
0x18003b9b9  mov     [rbp+47h+var_58], rax
0x18003b9bd  mov     r13d, r15d
0x18003b9c0  mov     [rbp+47h+var_50], 1
0x18003b9c4  xor     ecx, ecx; string
0x18003b9c6  mov     [rbp+47h+var_90], r15b
0x18003b9ca  mov     [rbp+47h+string], r15
0x18003b9ce  call    cs:__imp_WindowsDeleteString
0x18003b9d5  nop     dword ptr [rax+rax+00h]
0x18003b9da  mov     rdx, [rbp+47h+var_78]
0x18003b9de  lea     rax, [rbp+47h+string]
0x18003b9e2  lea     r9, [rbp+47h+var_90]
0x18003b9e6  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003b9eb  mov     r8d, r13d
0x18003b9ee  mov     [rbp+47h+string], r15
0x18003b9f2  mov     rcx, r12
0x18003b9f5  call    ??_9IPackagedComCatalogContext@@$BBCI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{296,{flat}}
0x18003b9fa  mov     ebx, eax
0x18003b9fc  test    eax, eax
0x18003b9fe  js      loc_18003BECE
0x18003ba04  cmp     [rbp+47h+var_90], r15b
0x18003ba08  jnz     loc_18003BC68
0x18003ba0e  mov     rcx, [rbp+47h+string]; string
0x18003ba12  call    cs:__imp_WindowsDeleteString
0x18003ba19  nop     dword ptr [rax+rax+00h]
0x18003ba1e  mov     rax, [r12]
0x18003ba22  mov     rcx, r12
0x18003ba25  mov     rdx, [rbp+47h+var_78]
0x18003ba29  mov     [rbp+47h+var_50], r15b
0x18003ba2d  mov     rax, [rax+20h]
0x18003ba31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba36  mov     rbx, r15
0x18003ba39  mov     [rbp+47h+var_78], r15
0x18003ba3d  mov     [rbp+47h+var_80], rbx
0x18003ba41  cmp     [rsi+88h], r15d
0x18003ba48  jnz     loc_18003BD99
0x18003ba4e  cmp     [rbp+47h+arg_20], r15b
0x18003ba52  jnz     loc_18003BBCB
0x18003ba58  mov     rdi, [rsi+80h]
0x18003ba5f  mov     ecx, [rsi+88h]
0x18003ba65  mov     eax, ecx
0x18003ba67  shl     rax, 5
0x18003ba6b  add     rax, [rsi+80h]
0x18003ba72  cmp     rdi, rax
0x18003ba75  jz      short loc_18003BAB9
0x18003ba77  mov     rdx, [rdi]
0x18003ba7a  lea     r13, [rdi+10h]
0x18003ba7e  xor     r9d, r9d
0x18003ba81  mov     qword ptr [rsp+0D0h+var_B0], r13; int
0x18003ba86  mov     r8, r14
0x18003ba89  mov     rcx, r12
0x18003ba8c  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x18003ba91  mov     r15d, eax
0x18003ba94  test    eax, eax
0x18003ba96  js      loc_18003BDF5
0x18003ba9c  xor     r15d, r15d
0x18003ba9f  cmp     [rdi+8], r15b
0x18003baa3  jnz     loc_18003BDBA
0x18003baa9  cmp     [r13+0], r15b
0x18003baad  jz      loc_18003BDCE
0x18003bab3  add     rdi, 20h ; ' '
0x18003bab7  jmp     short loc_18003BA5F
0x18003bab9  test    rbx, rbx
0x18003babc  jnz     loc_18003BE2D
0x18003bac2  mov     rcx, rbx; string
0x18003bac5  call    cs:__imp_WindowsDeleteString
0x18003bacc  nop     dword ptr [rax+rax+00h]
0x18003bad1  xor     eax, eax
0x18003bad3  jmp     loc_18003BB80
0x18003bad8  mov     rdi, [rsi+80h]
0x18003badf  mov     eax, [rsi+88h]
0x18003bae5  shl     rax, 5
0x18003bae9  add     rax, [rsi+80h]
0x18003baf0  cmp     rdi, rax
0x18003baf3  jnz     loc_18003BB9E
0x18003baf9  mov     edx, dword ptr [rbp+47h+string]
0x18003bafc  test    edx, edx
0x18003bafe  jz      short loc_18003BB0F
0x18003bb00  mov     rax, [r14]
0x18003bb03  mov     rcx, r14
0x18003bb06  mov     rax, [rax+68h]
0x18003bb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb0f  mov     rdi, [rsi+80h]
0x18003bb16  mov     eax, [rsi+88h]
0x18003bb1c  shl     rax, 5
0x18003bb20  add     rax, [rsi+80h]
0x18003bb27  cmp     rdi, rax
0x18003bb2a  jz      loc_18003BDB2
0x18003bb30  mov     rdx, [rdi]
0x18003bb33  lea     rax, [rdi+18h]
0x18003bb37  mov     r9d, 2
0x18003bb3d  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003bb42  mov     r8, r14
0x18003bb45  mov     rcx, r12
0x18003bb48  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x18003bb4d  mov     r15d, eax
0x18003bb50  test    eax, eax
0x18003bb52  jns     short loc_18003BB95
0x18003bb54  mov     rcx, [rbp+4Fh]; this
0x18003bb58  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18003bb5f  mov     r9d, eax; char *
0x18003bb62  mov     edx, 0FC9h; void *
0x18003bb67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bb6c  mov     edi, r15d
0x18003bb6f  mov     rcx, rbx; string
0x18003bb72  call    cs:__imp_WindowsDeleteString
0x18003bb79  nop     dword ptr [rax+rax+00h]
0x18003bb7e  mov     eax, edi
0x18003bb80  add     rsp, 98h
0x18003bb87  pop     r15
0x18003bb89  pop     r14
0x18003bb8b  pop     r13
0x18003bb8d  pop     r12
0x18003bb8f  pop     rdi
0x18003bb90  pop     rsi
0x18003bb91  pop     rbx
0x18003bb92  pop     rbp
0x18003bb93  retn
0x18003bb95  add     rdi, 20h ; ' '
0x18003bb99  jmp     loc_18003BB16
0x18003bb9e  mov     rdx, [rdi]
0x18003bba1  lea     rax, [rdi+8]
0x18003bba5  mov     r9d, 1
0x18003bbab  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003bbb0  mov     r8, r14
0x18003bbb3  mov     rcx, r12
0x18003bbb6  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x18003bbbb  mov     r15d, eax
0x18003bbbe  test    eax, eax
0x18003bbc0  js      short loc_18003BC31
0x18003bbc2  add     rdi, 20h ; ' '
0x18003bbc6  jmp     loc_18003BADF
0x18003bbcb  mov     dword ptr [rbp+47h+string], r15d
0x18003bbcf  test    r14, r14
0x18003bbd2  jz      loc_18003BAD8
0x18003bbd8  mov     rax, [r14]
0x18003bbdb  lea     r8, [rbp+47h+string]
0x18003bbdf  mov     edx, 1
0x18003bbe4  mov     rcx, r14
0x18003bbe7  mov     rax, [rax+60h]
0x18003bbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbf0  mov     edi, eax
0x18003bbf2  test    eax, eax
0x18003bbf4  jns     loc_18003BAD8
0x18003bbfa  mov     rcx, [rbp+4Fh]; this
0x18003bbfe  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18003bc05  mov     r9d, eax; char *
0x18003bc08  mov     edx, 0FB4h; void *
0x18003bc0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc12  mov     edx, dword ptr [rbp+47h+string]
0x18003bc15  test    edx, edx
0x18003bc17  jz      loc_18003BB6F
0x18003bc1d  mov     rcx, [r14]
0x18003bc20  mov     rax, [rcx+68h]
0x18003bc24  mov     rcx, r14
0x18003bc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc2c  jmp     loc_18003BB6F
0x18003bc31  mov     rcx, [rbp+4Fh]; this
0x18003bc35  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18003bc3c  mov     r9d, r15d; char *
0x18003bc3f  mov     edx, 0FBAh; void *
0x18003bc44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc49  mov     edx, dword ptr [rbp+47h+string]
0x18003bc4c  test    edx, edx
0x18003bc4e  jz      loc_18003BB6C
0x18003bc54  mov     rax, [r14]
0x18003bc57  mov     rcx, r14
0x18003bc5a  mov     rax, [rax+68h]
0x18003bc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc63  jmp     loc_18003BB6C
0x18003bc68  test    rdi, rdi
0x18003bc6b  jnz     loc_18003BD2E
0x18003bc71  movzx   eax, word ptr [rbp+47h+var_80+1]
0x18003bc75  lea     rdx, [rbp+47h+string]
0x18003bc79  mov     word ptr [rbp+47h+var_70+1], ax
0x18003bc7d  mov     rcx, rsi
0x18003bc80  mov     al, byte ptr [rbp+47h+var_80+3]
0x18003bc83  mov     byte ptr [rbp+47h+var_70+3], al
0x18003bc86  movzx   eax, word ptr [rbp+47h+var_80+1]
0x18003bc8a  mov     word ptr [rbp+47h+var_68+1], ax
0x18003bc8e  mov     al, byte ptr [rbp+47h+var_80+3]
0x18003bc91  mov     byte ptr [rbp+47h+var_68+3], al
0x18003bc94  movzx   eax, word ptr [rbp+47h+var_80+1]
0x18003bc98  mov     word ptr [rbp+47h+var_80+1], ax
0x18003bc9c  mov     al, byte ptr [rbp+47h+var_80+3]
0x18003bc9f  mov     byte ptr [rbp+47h+var_80+3], al
0x18003bca2  mov     byte ptr [rbp+47h+var_70], r15b
0x18003bca6  mov     dword ptr [rbp+47h+var_70+4], r15d
0x18003bcaa  mov     rax, [rbp+47h+var_70]
0x18003bcae  mov     byte ptr [rbp+47h+var_68], r15b
0x18003bcb2  mov     dword ptr [rbp+47h+var_68+4], r15d
0x18003bcb6  mov     r9, [rbp+47h+var_68]
0x18003bcba  mov     byte ptr [rbp+47h+var_80], r15b
0x18003bcbe  mov     dword ptr [rbp+47h+var_80+4], r15d
0x18003bcc2  mov     r8, [rbp+47h+var_80]
0x18003bcc6  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18003bccb  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x18003bcd0  mov     ebx, eax
0x18003bcd2  test    eax, eax
0x18003bcd4  js      loc_18003BD8F
0x18003bcda  mov     rcx, [rbp+47h+string]; string
0x18003bcde  call    cs:__imp_WindowsDeleteString
0x18003bce5  nop     dword ptr [rax+rax+00h]
0x18003bcea  inc     r13d
0x18003bced  jmp     loc_18003B9C4
0x18003bcf2  test    rdi, rdi
0x18003bcf5  jz      loc_18003B98D
0x18003bcfb  mov     rcx, rdi; this
0x18003bcfe  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x18003bd03  test    rax, rax
0x18003bd06  jnz     loc_18003B98D
0x18003bd0c  jmp     loc_18003BAD1
0x18003bd11  mov     rcx, [rbp+4Fh]; this
0x18003bd15  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18003bd1c  mov     r9d, ebx; char *
0x18003bd1f  mov     edx, 0F65h; void *
0x18003bd24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bd29  jmp     loc_18003BF03
0x18003bd2e  mov     rcx, rdi; this
0x18003bd31  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x18003bd36  cmp     r15, rax
0x18003bd39  jnb     short loc_18003BD6F
0x18003bd3b  mov     rdx, r15; unsigned __int64
0x18003bd3e  mov     rcx, rdi; this
0x18003bd41  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x18003bd46  mov     rcx, [rbp+47h+string]; string
0x18003bd4a  xor     edx, edx; length
0x18003bd4c  mov     rbx, rax
0x18003bd4f  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bd56  nop     dword ptr [rax+rax+00h]
0x18003bd5b  mov     rcx, rax; unsigned __int16 *
0x18003bd5e  mov     rdx, rbx; unsigned __int16 *
0x18003bd61  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x18003bd66  test    al, al
0x18003bd68  jnz     short loc_18003BD87
0x18003bd6a  inc     r15
0x18003bd6d  jmp     short loc_18003BD2E
0x18003bd6f  mov     rcx, [rbp+47h+string]; string
0x18003bd73  call    cs:__imp_WindowsDeleteString
0x18003bd7a  nop     dword ptr [rax+rax+00h]
0x18003bd7f  xor     r15d, r15d
0x18003bd82  jmp     loc_18003BCEA
0x18003bd87  xor     r15d, r15d
0x18003bd8a  jmp     loc_18003BC71
0x18003bd8f  mov     edx, 0F8Ah
0x18003bd94  jmp     loc_18003BED3
0x18003bd99  mov     rdx, [rsi+80h]
0x18003bda0  lea     rcx, [rbp+47h+var_80]
0x18003bda4  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x18003bda9  mov     rbx, [rbp+47h+var_80]
0x18003bdad  jmp     loc_18003BA4E
0x18003bdb2  xor     r15d, r15d
0x18003bdb5  jmp     loc_18003BA58
0x18003bdba  cmp     [rdi+18h], r15b
0x18003bdbe  jz      loc_18003BAA9
0x18003bdc4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003bdc9  jmp     loc_18003BAA9
0x18003bdce  cmp     [rdi+8], r15b
0x18003bdd2  jnz     loc_18003BAB3
0x18003bdd8  cmp     [rdi+18h], r15b
0x18003bddc  jnz     loc_18003BAB3
0x18003bde2  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x18003bde5  mov     rcx, rsi; this
0x18003bde8  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x18003bded  mov     rdi, rax
0x18003bdf0  jmp     loc_18003BA5F
0x18003bdf5  mov     rcx, [rbp+4Fh]; this
0x18003bdf9  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18003be00  mov     r9d, r15d; char *
0x18003be03  mov     edx, 0FD4h; void *
  ... truncated ...
```
