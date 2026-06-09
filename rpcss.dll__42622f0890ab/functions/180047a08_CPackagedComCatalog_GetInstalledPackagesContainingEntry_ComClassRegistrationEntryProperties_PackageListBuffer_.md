# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComClassRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)

- ea: `0x180047a08`
- end: `0x180047f80`
- name: `??$GetInstalledPackagesContainingEntry@UComClassRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z`
- size: `1400`
- prototype: `__int64 __fastcall(PackageListBuffer *this, __int64, __int64 *, GUID *, char, PackageFilter *)`
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008df18`
- `0x1800a83ac`
- `0x1800de0d0`
- `0x1800e30e0`

## callees

- `0x180005c40`
- `0x18002ba28`
- `0x18002effc`
- `0x1800414d0`
- `0x180043850`
- `0x180047a08`
- `0x180047f88`
- `0x18004844c`
- `0x18004853c`
- `0x18006d90c`
- `0x18006df38`
- `0x18008e98c`
- `0x1800a167c`
- `0x1800d9958`
- `0x1800d9970`
- `0x1800dd864`
- `0x1800de7e4`
- `0x1800de834`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047a8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047b75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047c1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047f66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047a8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047b75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047c1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047f66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047de9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047ef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047de9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047ef1`

## string_xrefs

- `0x180047c02`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180047c9e`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180047cd5`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180047daf`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180047e87`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180047ef7`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180047f53`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180047f18`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x180047f26`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

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
  unsigned int v18; // r15d
  _QWORD *i; // rdi
  _QWORD *j; // rdi
  int v22; // eax
  int v23; // r15d
  unsigned int v24; // edi
  int ComPackageInstallOrder; // eax
  int v26; // eax
  const unsigned __int16 *PackageFullName; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v29; // rdx
  PCWSTR v30; // rdi
  const char *v31; // rax
  __int64 v32; // rdx
  int v33; // [rsp+20h] [rbp-69h]
  HSTRING *p_string; // [rsp+20h] [rbp-69h]
  char *v35; // [rsp+28h] [rbp-61h]
  _BYTE v36[8]; // [rsp+40h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v38; // [rsp+50h] [rbp-39h] BYREF
  __int64 v39; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-29h]
  int v41; // [rsp+64h] [rbp-25h]
  int v42; // [rsp+68h] [rbp-21h]
  int v43; // [rsp+6Ch] [rbp-1Dh]
  _QWORD v44[2]; // [rsp+70h] [rbp-19h] BYREF
  char v45; // [rsp+80h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
    && a6
    && !PackageFilter::GetPackageCount(a6) )
  {
    return 0;
  }
  v39 = 0;
  v10 =  IPackagedComCatalogContext::`vcall'{288,{flat}}(a3, a4, &v39);
  v11 = 0;
  v12 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF65,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v10,
      v33);
    return (unsigned int)v12;
  }
  else
  {
    v44[0] = a3;
    v44[1] = &v39;
    v13 = 0;
    v45 = 1;
    while ( 1 )
    {
      v36[0] = 0;
      string = 0;
      WindowsDeleteString(0);
      p_string = &string;
      string = 0;
      v12 =  IPackagedComCatalogContext::`vcall'{296,{flat}}(a3, v39, v13, v36);
      if ( v12 < 0 )
      {
        v29 = 3953;
        goto LABEL_66;
      }
      if ( !v36[0] )
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
      *(_WORD *)((char *)&v40 + 1) = *(_WORD *)((char *)&v38 + 1);
      HIBYTE(v40) = BYTE3(v38);
      *(_WORD *)((char *)&v42 + 1) = *(_WORD *)((char *)&v38 + 1);
      HIBYTE(v42) = BYTE3(v38);
      LOBYTE(v40) = 0;
      v41 = 0;
      LOBYTE(v42) = 0;
      v43 = 0;
      LOBYTE(v38) = 0;
      HIDWORD(v38) = 0;
      v12 = PackageListBuffer::AddPackage((_DWORD)this, (unsigned int)&string, (_DWORD)v38, v42, v40);
      if ( v12 < 0 )
      {
        v29 = 3978;
LABEL_66:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v12,
          (int)p_string);
        WindowsDeleteString(string);
        string = 0;
        wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v44);
        return (unsigned int)v12;
      }
      WindowsDeleteString(string);
LABEL_40:
      ++v13;
    }
    WindowsDeleteString(string);
    v14 = *a3;
    v45 = 0;
    (*(void (__fastcall **)(__int64 *, __int64))(v14 + 32))(a3, v39);
    v15 = 0;
    v39 = 0;
    v38 = 0;
    if ( *((_DWORD *)this + 34) )
    {
      OpaqueString::operator=(&v38, *((_QWORD *)this + 16));
      v15 = v38;
    }
    if ( !a5 )
      goto LABEL_9;
    LODWORD(string) = 0;
    if ( !a2
      || (v26 = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)a2 + 96LL))(a2, 1, &string),
          v24 = v26,
          v26 >= 0) )
    {
      for ( i = (_QWORD *)*((_QWORD *)this + 16);
            i != (_QWORD *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34));
            i += 4 )
      {
        ComPackageInstallOrder = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *i, a2, 1);
        v23 = ComPackageInstallOrder;
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
          v24 = v23;
          goto LABEL_27;
        }
      }
      if ( (_DWORD)string )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
      for ( j = (_QWORD *)*((_QWORD *)this + 16);
            j != (_QWORD *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34));
            j += 4 )
      {
        v22 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *j, a2, 2);
        v23 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFC9,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v22,
            (_DWORD)j + 24);
          goto LABEL_26;
        }
      }
LABEL_9:
      v16 = (struct PackageIdAndInstallOrders *)*((_QWORD *)this + 16);
      while ( v16 != (struct PackageIdAndInstallOrders *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34)) )
      {
        v17 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *(_QWORD *)v16, a2, 0);
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFD4,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v17,
            (_DWORD)v16 + 16);
          WindowsDeleteString(v15);
          wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v44);
          return v18;
        }
        if ( *((_BYTE *)v16 + 8) && *((_BYTE *)v16 + 24) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
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
          v30 = WindowsGetStringRawBuffer(v15, 0);
          v35 = (char *)WindowsGetStringRawBuffer(string, 0);
          if ( a5 )
          {
            v31 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to t"
                  "he caller. Package may not be installed for user.";
            v32 = 4086;
          }
          else
          {
            v31 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to t"
                  "he caller. Lookup was performed without per-user state, which may indicate that the caller was elevate"
                  "d, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).";
            v32 = 4092;
          }
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)v32,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)0x80040154LL,
            (int)v31,
            v35,
            v30);
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
      (const char *)(unsigned int)v26,
      (int)&string);
    if ( (_DWORD)string )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
LABEL_27:
    WindowsDeleteString(v15);
    return v24;
  }
}

```

## disassembly

```asm
0x180047a08  mov     [rsp-8+rguid], r9
0x180047a0d  push    rbp
0x180047a0e  push    rbx
0x180047a0f  push    rsi
0x180047a10  push    rdi
0x180047a11  push    r12
0x180047a13  push    r13
0x180047a15  push    r14
0x180047a17  push    r15
0x180047a19  lea     rbp, [rsp-0Fh]
0x180047a1e  sub     rsp, 98h
0x180047a25  mov     r15, r9
0x180047a28  mov     r12, r8
0x180047a2b  mov     r14, rdx
0x180047a2e  mov     rsi, rcx
0x180047a31  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180047a38  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180047a3d  mov     rdi, [rbp+47h+arg_28]
0x180047a41  test    al, al
0x180047a43  jnz     loc_180047D8C
0x180047a49  lea     r8, [rbp+47h+var_78]
0x180047a4d  mov     [rbp+47h+var_78], 0
0x180047a55  mov     rdx, r15
0x180047a58  mov     rcx, r12
0x180047a5b  call    ??_9IPackagedComCatalogContext@@$BBCA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{288,{flat}}
0x180047a60  xor     r15d, r15d
0x180047a63  mov     ebx, eax
0x180047a65  test    eax, eax
0x180047a67  js      loc_180047DAB
0x180047a6d  lea     rax, [rbp+47h+var_78]
0x180047a71  mov     [rbp+47h+var_60], r12
0x180047a75  mov     [rbp+47h+var_58], rax
0x180047a79  mov     r13d, r15d
0x180047a7c  mov     [rbp+47h+var_50], 1
0x180047a80  xor     ecx, ecx; string
0x180047a82  mov     [rbp+47h+var_90], r15b
0x180047a86  mov     [rbp+47h+string], r15
0x180047a8a  call    cs:__imp_WindowsDeleteString
0x180047a90  mov     rdx, [rbp+47h+var_78]
0x180047a94  lea     rax, [rbp+47h+string]
0x180047a98  lea     r9, [rbp+47h+var_90]
0x180047a9c  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180047aa1  mov     r8d, r13d
0x180047aa4  mov     [rbp+47h+string], r15
0x180047aa8  mov     rcx, r12
0x180047aab  call    ??_9IPackagedComCatalogContext@@$BBCI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{296,{flat}}
0x180047ab0  mov     ebx, eax
0x180047ab2  test    eax, eax
0x180047ab4  js      loc_180047F4A
0x180047aba  cmp     [rbp+47h+var_90], r15b
0x180047abe  jnz     loc_180047D08
0x180047ac4  mov     rcx, [rbp+47h+string]; string
0x180047ac8  call    cs:__imp_WindowsDeleteString
0x180047ace  mov     rax, [r12]
0x180047ad2  mov     rcx, r12
0x180047ad5  mov     rdx, [rbp+47h+var_78]
0x180047ad9  mov     [rbp+47h+var_50], r15b
0x180047add  mov     rax, [rax+20h]
0x180047ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ae6  mov     rbx, r15
0x180047ae9  mov     [rbp+47h+var_78], r15
0x180047aed  mov     [rbp+47h+var_80], rbx
0x180047af1  cmp     [rsi+88h], r15d
0x180047af8  jnz     loc_180047E27
0x180047afe  cmp     [rbp+47h+arg_20], r15b
0x180047b02  jnz     loc_180047C6B
0x180047b08  mov     rdi, [rsi+80h]
0x180047b0f  mov     ecx, [rsi+88h]
0x180047b15  mov     eax, ecx
0x180047b17  shl     rax, 5
0x180047b1b  add     rax, [rsi+80h]
0x180047b22  cmp     rdi, rax
0x180047b25  jz      short loc_180047B69
0x180047b27  mov     rdx, [rdi]
0x180047b2a  lea     r13, [rdi+10h]
0x180047b2e  xor     r9d, r9d
0x180047b31  mov     qword ptr [rsp+0D0h+var_B0], r13; int
0x180047b36  mov     r8, r14
0x180047b39  mov     rcx, r12
0x180047b3c  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x180047b41  mov     r15d, eax
0x180047b44  test    eax, eax
0x180047b46  js      loc_180047E83
0x180047b4c  xor     r15d, r15d
0x180047b4f  cmp     [rdi+8], r15b
0x180047b53  jnz     loc_180047E48
0x180047b59  cmp     [r13+0], r15b
0x180047b5d  jz      loc_180047E5C
0x180047b63  add     rdi, 20h ; ' '
0x180047b67  jmp     short loc_180047B0F
0x180047b69  test    rbx, rbx
0x180047b6c  jnz     loc_180047EB5
0x180047b72  mov     rcx, rbx; string
0x180047b75  call    cs:__imp_WindowsDeleteString
0x180047b7b  xor     eax, eax
0x180047b7d  jmp     loc_180047C24
0x180047b82  mov     rdi, [rsi+80h]
0x180047b89  mov     eax, [rsi+88h]
0x180047b8f  shl     rax, 5
0x180047b93  add     rax, [rsi+80h]
0x180047b9a  cmp     rdi, rax
0x180047b9d  jnz     loc_180047C3E
0x180047ba3  mov     edx, dword ptr [rbp+47h+string]
0x180047ba6  test    edx, edx
0x180047ba8  jz      short loc_180047BB9
0x180047baa  mov     rax, [r14]
0x180047bad  mov     rcx, r14
0x180047bb0  mov     rax, [rax+68h]
0x180047bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047bb9  mov     rdi, [rsi+80h]
0x180047bc0  mov     eax, [rsi+88h]
0x180047bc6  shl     rax, 5
0x180047bca  add     rax, [rsi+80h]
0x180047bd1  cmp     rdi, rax
0x180047bd4  jz      loc_180047E40
0x180047bda  mov     rdx, [rdi]
0x180047bdd  lea     rax, [rdi+18h]
0x180047be1  mov     r9d, 2
0x180047be7  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180047bec  mov     r8, r14
0x180047bef  mov     rcx, r12
0x180047bf2  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x180047bf7  mov     r15d, eax
0x180047bfa  test    eax, eax
0x180047bfc  jns     short loc_180047C38
0x180047bfe  mov     rcx, [rbp+4Fh]; this
0x180047c02  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180047c09  mov     r9d, eax; char *
0x180047c0c  mov     edx, 0FC9h; void *
0x180047c11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047c16  mov     edi, r15d
0x180047c19  mov     rcx, rbx; string
0x180047c1c  call    cs:__imp_WindowsDeleteString
0x180047c22  mov     eax, edi
0x180047c24  add     rsp, 98h
0x180047c2b  pop     r15
0x180047c2d  pop     r14
0x180047c2f  pop     r13
0x180047c31  pop     r12
0x180047c33  pop     rdi
0x180047c34  pop     rsi
0x180047c35  pop     rbx
0x180047c36  pop     rbp
0x180047c37  retn
0x180047c38  add     rdi, 20h ; ' '
0x180047c3c  jmp     short loc_180047BC0
0x180047c3e  mov     rdx, [rdi]
0x180047c41  lea     rax, [rdi+8]
0x180047c45  mov     r9d, 1
0x180047c4b  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180047c50  mov     r8, r14
0x180047c53  mov     rcx, r12
0x180047c56  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x180047c5b  mov     r15d, eax
0x180047c5e  test    eax, eax
0x180047c60  js      short loc_180047CD1
0x180047c62  add     rdi, 20h ; ' '
0x180047c66  jmp     loc_180047B89
0x180047c6b  mov     dword ptr [rbp+47h+string], r15d
0x180047c6f  test    r14, r14
0x180047c72  jz      loc_180047B82
0x180047c78  mov     rax, [r14]
0x180047c7b  lea     r8, [rbp+47h+string]
0x180047c7f  mov     edx, 1
0x180047c84  mov     rcx, r14
0x180047c87  mov     rax, [rax+60h]
0x180047c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c90  mov     edi, eax
0x180047c92  test    eax, eax
0x180047c94  jns     loc_180047B82
0x180047c9a  mov     rcx, [rbp+4Fh]; this
0x180047c9e  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180047ca5  mov     r9d, eax; char *
0x180047ca8  mov     edx, 0FB4h; void *
0x180047cad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047cb2  mov     edx, dword ptr [rbp+47h+string]
0x180047cb5  test    edx, edx
0x180047cb7  jz      loc_180047C19
0x180047cbd  mov     rcx, [r14]
0x180047cc0  mov     rax, [rcx+68h]
0x180047cc4  mov     rcx, r14
0x180047cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ccc  jmp     loc_180047C19
0x180047cd1  mov     rcx, [rbp+4Fh]; this
0x180047cd5  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180047cdc  mov     r9d, r15d; char *
0x180047cdf  mov     edx, 0FBAh; void *
0x180047ce4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047ce9  mov     edx, dword ptr [rbp+47h+string]
0x180047cec  test    edx, edx
0x180047cee  jz      loc_180047C16
0x180047cf4  mov     rax, [r14]
0x180047cf7  mov     rcx, r14
0x180047cfa  mov     rax, [rax+68h]
0x180047cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d03  jmp     loc_180047C16
0x180047d08  test    rdi, rdi
0x180047d0b  jnz     loc_180047DC8
0x180047d11  movzx   eax, word ptr [rbp+47h+var_80+1]
0x180047d15  lea     rdx, [rbp+47h+string]
0x180047d19  mov     word ptr [rbp+47h+var_70+1], ax
0x180047d1d  mov     rcx, rsi
0x180047d20  mov     al, byte ptr [rbp+47h+var_80+3]
0x180047d23  mov     byte ptr [rbp+47h+var_70+3], al
0x180047d26  movzx   eax, word ptr [rbp+47h+var_80+1]
0x180047d2a  mov     word ptr [rbp+47h+var_68+1], ax
0x180047d2e  mov     al, byte ptr [rbp+47h+var_80+3]
0x180047d31  mov     byte ptr [rbp+47h+var_68+3], al
0x180047d34  movzx   eax, word ptr [rbp+47h+var_80+1]
0x180047d38  mov     word ptr [rbp+47h+var_80+1], ax
0x180047d3c  mov     al, byte ptr [rbp+47h+var_80+3]
0x180047d3f  mov     byte ptr [rbp+47h+var_80+3], al
0x180047d42  mov     byte ptr [rbp+47h+var_70], r15b
0x180047d46  mov     dword ptr [rbp+47h+var_70+4], r15d
0x180047d4a  mov     rax, [rbp+47h+var_70]
0x180047d4e  mov     byte ptr [rbp+47h+var_68], r15b
0x180047d52  mov     dword ptr [rbp+47h+var_68+4], r15d
0x180047d56  mov     r9, [rbp+47h+var_68]
0x180047d5a  mov     byte ptr [rbp+47h+var_80], r15b
0x180047d5e  mov     dword ptr [rbp+47h+var_80+4], r15d
0x180047d62  mov     r8, [rbp+47h+var_80]
0x180047d66  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180047d6b  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x180047d70  mov     ebx, eax
0x180047d72  test    eax, eax
0x180047d74  js      loc_180047E1D
0x180047d7a  mov     rcx, [rbp+47h+string]; string
0x180047d7e  call    cs:__imp_WindowsDeleteString
0x180047d84  inc     r13d
0x180047d87  jmp     loc_180047A80
0x180047d8c  test    rdi, rdi
0x180047d8f  jz      loc_180047A49
0x180047d95  mov     rcx, rdi; this
0x180047d98  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x180047d9d  test    rax, rax
0x180047da0  jnz     loc_180047A49
0x180047da6  jmp     loc_180047B7B
0x180047dab  mov     rcx, [rbp+4Fh]; this
0x180047daf  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180047db6  mov     r9d, ebx; char *
0x180047db9  mov     edx, 0F65h; void *
0x180047dbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047dc3  jmp     loc_180047F79
0x180047dc8  mov     rcx, rdi; this
0x180047dcb  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x180047dd0  cmp     r15, rax
0x180047dd3  jnb     short loc_180047E03
0x180047dd5  mov     rdx, r15; unsigned __int64
0x180047dd8  mov     rcx, rdi; this
0x180047ddb  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x180047de0  mov     rcx, [rbp+47h+string]; string
0x180047de4  xor     edx, edx; length
0x180047de6  mov     rbx, rax
0x180047de9  call    cs:__imp_WindowsGetStringRawBuffer
0x180047def  mov     rcx, rax; unsigned __int16 *
0x180047df2  mov     rdx, rbx; unsigned __int16 *
0x180047df5  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x180047dfa  test    al, al
0x180047dfc  jnz     short loc_180047E15
0x180047dfe  inc     r15
0x180047e01  jmp     short loc_180047DC8
0x180047e03  mov     rcx, [rbp+47h+string]; string
0x180047e07  call    cs:__imp_WindowsDeleteString
0x180047e0d  xor     r15d, r15d
0x180047e10  jmp     loc_180047D84
0x180047e15  xor     r15d, r15d
0x180047e18  jmp     loc_180047D11
0x180047e1d  mov     edx, 0F8Ah
0x180047e22  jmp     loc_180047F4F
0x180047e27  mov     rdx, [rsi+80h]
0x180047e2e  lea     rcx, [rbp+47h+var_80]
0x180047e32  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x180047e37  mov     rbx, [rbp+47h+var_80]
0x180047e3b  jmp     loc_180047AFE
0x180047e40  xor     r15d, r15d
0x180047e43  jmp     loc_180047B08
0x180047e48  cmp     [rdi+18h], r15b
0x180047e4c  jz      loc_180047B59
0x180047e52  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180047e57  jmp     loc_180047B59
0x180047e5c  cmp     [rdi+8], r15b
0x180047e60  jnz     loc_180047B63
0x180047e66  cmp     [rdi+18h], r15b
0x180047e6a  jnz     loc_180047B63
0x180047e70  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x180047e73  mov     rcx, rsi; this
0x180047e76  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x180047e7b  mov     rdi, rax
0x180047e7e  jmp     loc_180047B0F
0x180047e83  mov     rcx, [rbp+4Fh]; this
0x180047e87  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180047e8e  mov     r9d, r15d; char *
0x180047e91  mov     edx, 0FD4h; void *
0x180047e96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047e9b  mov     rcx, rbx; string
0x180047e9e  call    cs:__imp_WindowsDeleteString
0x180047ea4  lea     rcx, [rbp+47h+var_60]
0x180047ea8  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x180047ead  mov     eax, r15d
0x180047eb0  jmp     loc_180047C24
  ... truncated ...
```
