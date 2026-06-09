# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComInterfaceRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)

- ea: `0x1800db3c0`
- end: `0x1800db8ea`
- name: `??$GetInstalledPackagesContainingEntry@UComInterfaceRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z`
- size: `1322`
- prototype: `__int64 __usercall@<rax>(PackageListBuffer *this@<rcx>, char, PackageFilter *)`
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800aa358`
- `0x1800aad5c`
- `0x1800b3564`
- `0x1800e5190`

## callees

- `0x1800065a4`
- `0x1800210f8`
- `0x180024fd0`
- `0x18003bf10`
- `0x18003c3f4`
- `0x18003c4f8`
- `0x18004b0f0`
- `0x1800535d0`
- `0x180071404`
- `0x180072624`
- `0x180095c0c`
- `0x1800a6b6c`
- `0x1800db3c0`
- `0x1800e06f0`
- `0x1800e0708`
- `0x1800e482c`
- `0x1800e5844`
- `0x1800e5898`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db470`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db4fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db7c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db8ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db470`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db4fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db7c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db8ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db4d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db4d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db827`

## string_xrefs

- `0x1800db43a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800db607`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800db685`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800db7ab`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800db833`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800db8a7`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800db854`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x1800db862`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComInterfaceRegistrationEntryProperties>(
        PackageListBuffer *this,
        __int64 a2,
        __int64 a3,
        GUID *a4,
        char a5,
        PackageFilter *a6)
{
  int v11; // eax
  unsigned __int64 v12; // r15
  int v13; // ebx
  unsigned int v14; // r12d
  const unsigned __int16 *PackageFullName; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v17; // rdx
  HSTRING v18; // rbx
  int v19; // eax
  unsigned int v20; // edi
  _QWORD *i; // rdi
  int ComPackageInstallOrder; // eax
  int v23; // r15d
  _QWORD *j; // rdi
  __int64 v25; // rdx
  struct PackageIdAndInstallOrders *v26; // rdi
  __int64 v27; // rcx
  PCWSTR v28; // rdi
  const char *v29; // rax
  __int64 v30; // rdx
  int v31; // [rsp+20h] [rbp-69h]
  HSTRING *p_string; // [rsp+20h] [rbp-69h]
  int v33; // [rsp+20h] [rbp-69h]
  char *v34; // [rsp+28h] [rbp-61h]
  _BYTE v35[8]; // [rsp+40h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-41h] BYREF
  __int64 v37; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v38; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v39; // [rsp+60h] [rbp-29h]
  int v40; // [rsp+64h] [rbp-25h]
  int v41; // [rsp+68h] [rbp-21h]
  int v42; // [rsp+6Ch] [rbp-1Dh]
  _QWORD v43[2]; // [rsp+70h] [rbp-19h] BYREF
  char v44; // [rsp+80h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
    && a6
    && !PackageFilter::GetPackageCount(a6) )
  {
    return 0;
  }
  v37 = 0;
  v11 =  IPackagedComCatalogContext::`vcall'{304,{flat}}(a3, a4, &v37);
  v12 = 0;
  v13 = v11;
  if ( v11 >= 0 )
  {
    v43[0] = a3;
    v43[1] = &v37;
    v14 = 0;
    v44 = 1;
    while ( 1 )
    {
      v35[0] = 0;
      string = 0;
      WindowsDeleteString(0);
      p_string = &string;
      string = 0;
      v13 =  IPackagedComCatalogContext::`vcall'{312,{flat}}(a3, v37, v14, v35);
      if ( v13 < 0 )
      {
        v17 = 3953;
        goto LABEL_65;
      }
      if ( !v35[0] )
        break;
      if ( a6 )
      {
        while ( 1 )
        {
          if ( v12 >= PackageFilter::GetPackageCount(a6) )
          {
            WindowsDeleteString(string);
            v12 = 0;
            goto LABEL_18;
          }
          PackageFullName = PackageFilter::GetPackageFullName(a6, v12);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( PackageNamesMatch(StringRawBuffer, PackageFullName) )
            break;
          ++v12;
        }
        v12 = 0;
      }
      *(_WORD *)((char *)&v39 + 1) = *(_WORD *)((char *)&v37 + 1);
      HIBYTE(v39) = BYTE3(v37);
      *(_WORD *)((char *)&v41 + 1) = *(_WORD *)((char *)&v37 + 1);
      HIBYTE(v41) = BYTE3(v37);
      *(_WORD *)((char *)&v38 + 1) = *(_WORD *)((char *)&v37 + 1);
      BYTE3(v38) = BYTE3(v37);
      LOBYTE(v39) = 0;
      v40 = 0;
      LOBYTE(v41) = 0;
      v42 = 0;
      LOBYTE(v38) = 0;
      HIDWORD(v38) = 0;
      v13 = PackageListBuffer::AddPackage((_DWORD)this, (unsigned int)&string, (_DWORD)v38, v41, v39);
      if ( v13 < 0 )
      {
        v17 = 3978;
LABEL_65:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v13,
          (int)p_string);
        WindowsDeleteString(string);
        string = 0;
        wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v43);
        return (unsigned int)v13;
      }
      WindowsDeleteString(string);
LABEL_18:
      ++v14;
    }
    WindowsDeleteString(string);
    wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v43);
    v18 = 0;
    v38 = 0;
    if ( *((_DWORD *)this + 34) )
    {
      OpaqueString::operator=(&v38, *((_QWORD *)this + 16));
      v18 = v38;
    }
    if ( a5 )
    {
      LODWORD(string) = 0;
      if ( a2 )
      {
        v19 = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)a2 + 96LL))(a2, 1, &string);
        v20 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFB4,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v19,
            (int)&string);
          if ( (_DWORD)string )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
LABEL_54:
          WindowsDeleteString(v18);
          wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v43);
          return v20;
        }
      }
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
LABEL_53:
          v20 = v23;
          goto LABEL_54;
        }
      }
      if ( (_DWORD)string )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
      for ( j = (_QWORD *)*((_QWORD *)this + 16);
            j != (_QWORD *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34));
            j += 4 )
      {
        v33 = (_DWORD)j + 24;
        v23 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *j, a2, 2);
        if ( v23 < 0 )
        {
          v25 = 4041;
LABEL_52:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v25,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v23,
            v33);
          goto LABEL_53;
        }
      }
    }
    v26 = (struct PackageIdAndInstallOrders *)*((_QWORD *)this + 16);
    while ( v26 != (struct PackageIdAndInstallOrders *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34)) )
    {
      v33 = (_DWORD)v26 + 16;
      v23 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *(_QWORD *)v26, a2, 0);
      if ( v23 < 0 )
      {
        v25 = 4052;
        goto LABEL_52;
      }
      if ( *((_BYTE *)v26 + 8) && *((_BYTE *)v26 + 24) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v27);
      if ( *((_BYTE *)v26 + 16) || *((_BYTE *)v26 + 8) || *((_BYTE *)v26 + 24) )
        v26 = (struct PackageIdAndInstallOrders *)((char *)v26 + 32);
      else
        v26 = PackageListBuffer::RemoveAt(this, v26);
    }
    if ( v18 && !*((_DWORD *)this + 34) )
    {
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      if ( (int)GetIdString(a4, &string) >= 0 )
      {
        v28 = WindowsGetStringRawBuffer(v18, 0);
        v34 = (char *)WindowsGetStringRawBuffer(string, 0);
        if ( a5 )
        {
          v29 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the"
                " caller. Package may not be installed for user.";
          v30 = 4086;
        }
        else
        {
          v29 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the"
                " caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, n"
                "on-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).";
          v30 = 4092;
        }
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)v30,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)0x80040155LL,
          (int)v29,
          v34,
          v28);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
    }
    WindowsDeleteString(v18);
    wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v43);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF65,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)v11,
    v31);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800db3c0  mov     [rsp-8+rguid], r9
0x1800db3c5  push    rbp
0x1800db3c6  push    rbx
0x1800db3c7  push    rsi
0x1800db3c8  push    rdi
0x1800db3c9  push    r12
0x1800db3cb  push    r13
0x1800db3cd  push    r14
0x1800db3cf  push    r15
0x1800db3d1  lea     rbp, [rsp-0Fh]
0x1800db3d6  sub     rsp, 98h
0x1800db3dd  mov     r15, r9
0x1800db3e0  mov     r13, r8
0x1800db3e3  mov     r14, rdx
0x1800db3e6  mov     rsi, rcx
0x1800db3e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800db3f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800db3f5  mov     rdi, [rbp+47h+arg_28]
0x1800db3f9  test    al, al
0x1800db3fb  jz      short loc_1800DB416
0x1800db3fd  test    rdi, rdi
0x1800db400  jz      short loc_1800DB416
0x1800db402  mov     rcx, rdi; this
0x1800db405  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800db40a  test    rax, rax
0x1800db40d  jnz     short loc_1800DB416
0x1800db40f  xor     eax, eax
0x1800db411  jmp     loc_1800DB8D5
0x1800db416  lea     r8, [rbp+47h+var_80]
0x1800db41a  mov     [rbp+47h+var_80], 0
0x1800db422  mov     rdx, r15
0x1800db425  mov     rcx, r13
0x1800db428  call    ??_9IPackagedComCatalogContext@@$BBDA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{304,{flat}}
0x1800db42d  xor     r15d, r15d
0x1800db430  mov     ebx, eax
0x1800db432  test    eax, eax
0x1800db434  jns     short loc_1800DB453
0x1800db436  mov     rcx, [rbp+4Fh]; this
0x1800db43a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800db441  mov     r9d, eax; char *
0x1800db444  mov     edx, 0F65h; void *
0x1800db449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db44e  jmp     loc_1800DB8D3
0x1800db453  lea     rax, [rbp+47h+var_80]
0x1800db457  mov     [rbp+47h+var_60], r13
0x1800db45b  mov     [rbp+47h+var_58], rax
0x1800db45f  mov     r12d, r15d
0x1800db462  mov     [rbp+47h+var_50], 1
0x1800db466  xor     ecx, ecx; string
0x1800db468  mov     [rbp+47h+var_90], r15b
0x1800db46c  mov     [rbp+47h+string], r15
0x1800db470  call    cs:__imp_WindowsDeleteString
0x1800db477  nop     dword ptr [rax+rax+00h]
0x1800db47c  mov     rdx, [rbp+47h+var_80]
0x1800db480  lea     rax, [rbp+47h+string]
0x1800db484  lea     r9, [rbp+47h+var_90]
0x1800db488  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800db48d  mov     r8d, r12d
0x1800db490  mov     [rbp+47h+string], r15
0x1800db494  mov     rcx, r13
0x1800db497  call    ??_9IPackagedComCatalogContext@@$BBDI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{312,{flat}}
0x1800db49c  mov     ebx, eax
0x1800db49e  test    eax, eax
0x1800db4a0  js      loc_1800DB89E
0x1800db4a6  cmp     [rbp+47h+var_90], r15b
0x1800db4aa  jz      loc_1800DB595
0x1800db4b0  test    rdi, rdi
0x1800db4b3  jz      short loc_1800DB50E
0x1800db4b5  mov     rcx, rdi; this
0x1800db4b8  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800db4bd  cmp     r15, rax
0x1800db4c0  jnb     short loc_1800DB4F6
0x1800db4c2  mov     rdx, r15; unsigned __int64
0x1800db4c5  mov     rcx, rdi; this
0x1800db4c8  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x1800db4cd  mov     rcx, [rbp+47h+string]; string
0x1800db4d1  xor     edx, edx; length
0x1800db4d3  mov     rbx, rax
0x1800db4d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db4dd  nop     dword ptr [rax+rax+00h]
0x1800db4e2  mov     rcx, rax; unsigned __int16 *
0x1800db4e5  mov     rdx, rbx; unsigned __int16 *
0x1800db4e8  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x1800db4ed  test    al, al
0x1800db4ef  jnz     short loc_1800DB50B
0x1800db4f1  inc     r15
0x1800db4f4  jmp     short loc_1800DB4B5
0x1800db4f6  mov     rcx, [rbp+47h+string]; string
0x1800db4fa  call    cs:__imp_WindowsDeleteString
0x1800db501  nop     dword ptr [rax+rax+00h]
0x1800db506  xor     r15d, r15d
0x1800db509  jmp     short loc_1800DB583
0x1800db50b  xor     r15d, r15d
0x1800db50e  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800db512  lea     rdx, [rbp+47h+string]
0x1800db516  mov     word ptr [rbp+47h+var_70+1], ax
0x1800db51a  mov     rcx, rsi
0x1800db51d  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800db520  mov     byte ptr [rbp+47h+var_70+3], al
0x1800db523  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800db527  mov     word ptr [rbp+47h+var_68+1], ax
0x1800db52b  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800db52e  mov     byte ptr [rbp+47h+var_68+3], al
0x1800db531  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800db535  mov     word ptr [rbp+47h+var_78+1], ax
0x1800db539  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800db53c  mov     byte ptr [rbp+47h+var_78+3], al
0x1800db53f  mov     byte ptr [rbp+47h+var_70], r15b
0x1800db543  mov     dword ptr [rbp+47h+var_70+4], r15d
0x1800db547  mov     rax, [rbp+47h+var_70]
0x1800db54b  mov     byte ptr [rbp+47h+var_68], r15b
0x1800db54f  mov     dword ptr [rbp+47h+var_68+4], r15d
0x1800db553  mov     r9, [rbp+47h+var_68]
0x1800db557  mov     byte ptr [rbp+47h+var_78], r15b
0x1800db55b  mov     dword ptr [rbp+47h+var_78+4], r15d
0x1800db55f  mov     r8, [rbp+47h+var_78]
0x1800db563  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800db568  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x1800db56d  mov     ebx, eax
0x1800db56f  test    eax, eax
0x1800db571  js      short loc_1800DB58B
0x1800db573  mov     rcx, [rbp+47h+string]; string
0x1800db577  call    cs:__imp_WindowsDeleteString
0x1800db57e  nop     dword ptr [rax+rax+00h]
0x1800db583  inc     r12d
0x1800db586  jmp     loc_1800DB466
0x1800db58b  mov     edx, 0F8Ah
0x1800db590  jmp     loc_1800DB8A3
0x1800db595  mov     rcx, [rbp+47h+string]; string
0x1800db599  call    cs:__imp_WindowsDeleteString
0x1800db5a0  nop     dword ptr [rax+rax+00h]
0x1800db5a5  lea     rcx, [rbp+47h+var_60]
0x1800db5a9  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800db5ae  mov     rbx, r15
0x1800db5b1  mov     [rbp+47h+var_78], rbx
0x1800db5b5  cmp     [rsi+88h], r15d
0x1800db5bc  jz      short loc_1800DB5D2
0x1800db5be  mov     rdx, [rsi+80h]
0x1800db5c5  lea     rcx, [rbp+47h+var_78]
0x1800db5c9  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800db5ce  mov     rbx, [rbp+47h+var_78]
0x1800db5d2  cmp     [rbp+47h+arg_20], r15b
0x1800db5d6  jz      loc_1800DB722
0x1800db5dc  mov     dword ptr [rbp+47h+string], r15d
0x1800db5e0  test    r14, r14
0x1800db5e3  jz      short loc_1800DB63A
0x1800db5e5  mov     rax, [r14]
0x1800db5e8  lea     r8, [rbp+47h+string]
0x1800db5ec  mov     edx, 1
0x1800db5f1  mov     rcx, r14
0x1800db5f4  mov     rax, [rax+60h]
0x1800db5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db5fd  mov     edi, eax
0x1800db5ff  test    eax, eax
0x1800db601  jns     short loc_1800DB63A
0x1800db603  mov     rcx, [rbp+4Fh]; this
0x1800db607  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800db60e  mov     r9d, eax; char *
0x1800db611  mov     edx, 0FB4h; void *
0x1800db616  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db61b  mov     edx, dword ptr [rbp+47h+string]
0x1800db61e  test    edx, edx
0x1800db620  jz      loc_1800DB7BD
0x1800db626  mov     rcx, [r14]
0x1800db629  mov     rax, [rcx+68h]
0x1800db62d  mov     rcx, r14
0x1800db630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db635  jmp     loc_1800DB7BD
0x1800db63a  mov     rdi, [rsi+80h]
0x1800db641  mov     eax, [rsi+88h]
0x1800db647  shl     rax, 5
0x1800db64b  add     rax, [rsi+80h]
0x1800db652  cmp     rdi, rax
0x1800db655  jz      short loc_1800DB6B8
0x1800db657  mov     rdx, [rdi]
0x1800db65a  lea     rax, [rdi+8]
0x1800db65e  mov     r9d, 1
0x1800db664  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800db669  mov     r8, r14
0x1800db66c  mov     rcx, r13
0x1800db66f  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800db674  mov     r15d, eax
0x1800db677  test    eax, eax
0x1800db679  js      short loc_1800DB681
0x1800db67b  add     rdi, 20h ; ' '
0x1800db67f  jmp     short loc_1800DB641
0x1800db681  mov     rcx, [rbp+4Fh]; this
0x1800db685  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800db68c  mov     r9d, r15d; char *
0x1800db68f  mov     edx, 0FBAh; void *
0x1800db694  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db699  mov     edx, dword ptr [rbp+47h+string]
0x1800db69c  test    edx, edx
0x1800db69e  jz      loc_1800DB7BA
0x1800db6a4  mov     rax, [r14]
0x1800db6a7  mov     rcx, r14
0x1800db6aa  mov     rax, [rax+68h]
0x1800db6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db6b3  jmp     loc_1800DB7BA
0x1800db6b8  mov     edx, dword ptr [rbp+47h+string]
0x1800db6bb  test    edx, edx
0x1800db6bd  jz      short loc_1800DB6CE
0x1800db6bf  mov     rax, [r14]
0x1800db6c2  mov     rcx, r14
0x1800db6c5  mov     rax, [rax+68h]
0x1800db6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db6ce  mov     rdi, [rsi+80h]
0x1800db6d5  mov     eax, [rsi+88h]
0x1800db6db  shl     rax, 5
0x1800db6df  add     rax, [rsi+80h]
0x1800db6e6  cmp     rdi, rax
0x1800db6e9  jz      short loc_1800DB71F
0x1800db6eb  mov     rdx, [rdi]
0x1800db6ee  lea     rax, [rdi+18h]
0x1800db6f2  mov     r9d, 2
0x1800db6f8  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800db6fd  mov     r8, r14
0x1800db700  mov     rcx, r13
0x1800db703  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800db708  mov     r15d, eax
0x1800db70b  test    eax, eax
0x1800db70d  js      short loc_1800DB715
0x1800db70f  add     rdi, 20h ; ' '
0x1800db713  jmp     short loc_1800DB6D5
0x1800db715  mov     edx, 0FC9h
0x1800db71a  jmp     loc_1800DB7A7
0x1800db71f  xor     r15d, r15d
0x1800db722  mov     rdi, [rsi+80h]
0x1800db729  mov     ecx, [rsi+88h]
0x1800db72f  mov     eax, ecx
0x1800db731  shl     rax, 5
0x1800db735  add     rax, [rsi+80h]
0x1800db73c  cmp     rdi, rax
0x1800db73f  jz      loc_1800DB7DC
0x1800db745  mov     rdx, [rdi]
0x1800db748  lea     r12, [rdi+10h]
0x1800db74c  xor     r9d, r9d
0x1800db74f  mov     qword ptr [rsp+0D0h+var_B0], r12; int
0x1800db754  mov     r8, r14
0x1800db757  mov     rcx, r13
0x1800db75a  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800db75f  mov     r15d, eax
0x1800db762  test    eax, eax
0x1800db764  js      short loc_1800DB7A2
0x1800db766  xor     r15d, r15d
0x1800db769  cmp     [rdi+8], r15b
0x1800db76d  jz      short loc_1800DB77A
0x1800db76f  cmp     [rdi+18h], r15b
0x1800db773  jz      short loc_1800DB77A
0x1800db775  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800db77a  cmp     [r12], r15b
0x1800db77e  jnz     short loc_1800DB79C
0x1800db780  cmp     [rdi+8], r15b
0x1800db784  jnz     short loc_1800DB79C
0x1800db786  cmp     [rdi+18h], r15b
0x1800db78a  jnz     short loc_1800DB79C
0x1800db78c  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x1800db78f  mov     rcx, rsi; this
0x1800db792  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x1800db797  mov     rdi, rax
0x1800db79a  jmp     short loc_1800DB729
0x1800db79c  add     rdi, 20h ; ' '
0x1800db7a0  jmp     short loc_1800DB729
0x1800db7a2  mov     edx, 0FD4h; void *
0x1800db7a7  mov     rcx, [rbp+4Fh]; this
0x1800db7ab  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800db7b2  mov     r9d, r15d; char *
0x1800db7b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db7ba  mov     edi, r15d
0x1800db7bd  mov     rcx, rbx; string
0x1800db7c0  call    cs:__imp_WindowsDeleteString
0x1800db7c7  nop     dword ptr [rax+rax+00h]
0x1800db7cc  lea     rcx, [rbp+47h+var_60]
0x1800db7d0  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800db7d5  mov     eax, edi
0x1800db7d7  jmp     loc_1800DB8D5
0x1800db7dc  test    rbx, rbx
0x1800db7df  jz      loc_1800DB881
0x1800db7e5  test    ecx, ecx
0x1800db7e7  jnz     loc_1800DB881
0x1800db7ed  xor     edx, edx
0x1800db7ef  mov     [rbp+47h+string], r15
0x1800db7f3  lea     rcx, [rbp+47h+string]
0x1800db7f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800db7fc  mov     rcx, [rbp+47h+rguid]; rguid
0x1800db800  lea     rdx, [rbp+47h+string]; string
0x1800db804  call    ?GetIdString@@YAJAEBU_GUID@@PEAPEAUHSTRING__@@@Z; GetIdString(_GUID const &,HSTRING__ * *)
0x1800db809  test    eax, eax
0x1800db80b  js      short loc_1800DB878
0x1800db80d  xor     edx, edx; length
0x1800db80f  mov     rcx, rbx; string
0x1800db812  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db819  nop     dword ptr [rax+rax+00h]
0x1800db81e  mov     rcx, [rbp+47h+string]; string
0x1800db822  xor     edx, edx; length
0x1800db824  mov     rdi, rax
0x1800db827  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db82e  nop     dword ptr [rax+rax+00h]
0x1800db833  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800db83a  mov     rcx, [rbp+4Fh]; this
  ... truncated ...
```
