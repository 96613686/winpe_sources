# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTreatAsClassRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)

- ea: `0x1800720e0`
- end: `0x18007261e`
- name: `??$GetInstalledPackagesContainingEntry@UComTreatAsClassRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z`
- size: `1342`
- prototype: `__int64 __usercall@<rax>(PackageListBuffer *this@<rcx>, char, PackageFilter *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18009633c`
- `0x1800e5260`

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
- `0x1800720e0`
- `0x180072624`
- `0x180095c0c`
- `0x1800a6b6c`
- `0x1800e0780`
- `0x1800e0798`
- `0x1800e482c`
- `0x1800e5844`
- `0x1800e5898`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007221a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800722b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072367`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800724ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800725c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800725ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007221a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800722b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072367`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800724ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800725c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800725ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800721f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007254f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072564`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800721f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007254f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072564`

## string_xrefs

- `0x18007215a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18007233a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800723c4`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800724ea`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180072570`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800725db`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180072591`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x18007259f`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTreatAsClassRegistrationEntryProperties>(
        PackageListBuffer *this,
        __int64 a2,
        __int64 *a3,
        GUID *a4,
        char a5,
        PackageFilter *a6)
{
  int v11; // eax
  unsigned __int64 v12; // r15
  int v13; // ebx
  unsigned int v14; // r13d
  const unsigned __int16 *PackageFullName; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  HSTRING v19; // rbx
  int v20; // eax
  unsigned int v21; // edi
  _QWORD *i; // r15
  int ComPackageInstallOrder; // eax
  _QWORD *j; // rdi
  int v25; // r15d
  __int64 v26; // rdx
  struct PackageIdAndInstallOrders *v27; // rdi
  __int64 v28; // rcx
  PCWSTR v29; // rdi
  const char *v30; // rax
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-69h]
  HSTRING *p_string; // [rsp+20h] [rbp-69h]
  int v34; // [rsp+20h] [rbp-69h]
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
  v11 =  IPackagedComCatalogContext::`vcall'{352,{flat}}(a3, a4, &v39);
  v12 = 0;
  v13 = v11;
  if ( v11 >= 0 )
  {
    v44[0] = a3;
    v44[1] = &v39;
    v14 = 0;
    v45 = 1;
    while ( 1 )
    {
      v36[0] = 0;
      string = 0;
      WindowsDeleteString(0);
      p_string = &string;
      string = 0;
      v13 =  IPackagedComCatalogContext::`vcall'{360,{flat}}(a3, v39, v14, v36);
      if ( v13 < 0 )
      {
        v17 = 3953;
        goto LABEL_66;
      }
      if ( !v36[0] )
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
      v13 = PackageListBuffer::AddPackage((_DWORD)this, (unsigned int)&string, (_DWORD)v38, v42, v40);
      if ( v13 < 0 )
      {
        v17 = 3978;
LABEL_66:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v13,
          (int)p_string);
        WindowsDeleteString(string);
        string = 0;
        wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v44);
        return (unsigned int)v13;
      }
      WindowsDeleteString(string);
LABEL_18:
      ++v14;
    }
    WindowsDeleteString(string);
    v18 = *a3;
    v45 = 0;
    (*(void (__fastcall **)(__int64 *, __int64))(v18 + 32))(a3, v39);
    v19 = 0;
    v39 = 0;
    v38 = 0;
    if ( *((_DWORD *)this + 34) )
    {
      OpaqueString::operator=(&v38, *((_QWORD *)this + 16));
      v19 = v38;
    }
    if ( a5 )
    {
      LODWORD(string) = 0;
      if ( a2 )
      {
        v20 = (*(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)a2 + 96LL))(a2, 1, &string);
        v21 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFB4,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v20,
            (int)&string);
          if ( (_DWORD)string )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
          WindowsDeleteString(v19);
          return v21;
        }
      }
      for ( i = (_QWORD *)*((_QWORD *)this + 16);
            i != (_QWORD *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34));
            i += 4 )
      {
        ComPackageInstallOrder = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *i, a2, 1);
        v21 = ComPackageInstallOrder;
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
LABEL_55:
          WindowsDeleteString(v19);
          wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v44);
          return v21;
        }
      }
      if ( (_DWORD)string )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
      for ( j = (_QWORD *)*((_QWORD *)this + 16);
            j != (_QWORD *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34));
            j += 4 )
      {
        v34 = (_DWORD)j + 24;
        v25 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *j, a2, 2);
        if ( v25 < 0 )
        {
          v26 = 4041;
LABEL_54:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v26,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v25,
            v34);
          v21 = v25;
          goto LABEL_55;
        }
      }
    }
    v27 = (struct PackageIdAndInstallOrders *)*((_QWORD *)this + 16);
    while ( v27 != (struct PackageIdAndInstallOrders *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34)) )
    {
      v34 = (_DWORD)v27 + 16;
      v25 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *(_QWORD *)v27, a2, 0);
      if ( v25 < 0 )
      {
        v26 = 4052;
        goto LABEL_54;
      }
      if ( *((_BYTE *)v27 + 8) && *((_BYTE *)v27 + 24) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v28);
      if ( *((_BYTE *)v27 + 16) || *((_BYTE *)v27 + 8) || *((_BYTE *)v27 + 24) )
        v27 = (struct PackageIdAndInstallOrders *)((char *)v27 + 32);
      else
        v27 = PackageListBuffer::RemoveAt(this, v27);
    }
    if ( v19 && !*((_DWORD *)this + 34) )
    {
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      if ( (int)GetIdString(a4, &string) >= 0 )
      {
        v29 = WindowsGetStringRawBuffer(v19, 0);
        v35 = (char *)WindowsGetStringRawBuffer(string, 0);
        if ( a5 )
        {
          v30 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the"
                " caller. Package may not be installed for user.";
          v31 = 4086;
        }
        else
        {
          v30 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the"
                " caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, n"
                "on-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).";
          v31 = 4092;
        }
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)0x80040154LL,
          (int)v30,
          v35,
          v29);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
    }
    WindowsDeleteString(v19);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF65,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)v11,
    v32);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800720e0  mov     [rsp-8+rguid], r9
0x1800720e5  push    rbp
0x1800720e6  push    rbx
0x1800720e7  push    rsi
0x1800720e8  push    rdi
0x1800720e9  push    r12
0x1800720eb  push    r13
0x1800720ed  push    r14
0x1800720ef  push    r15
0x1800720f1  lea     rbp, [rsp-0Fh]
0x1800720f6  sub     rsp, 98h
0x1800720fd  mov     r15, r9
0x180072100  mov     r12, r8
0x180072103  mov     r14, rdx
0x180072106  mov     rsi, rcx
0x180072109  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180072110  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180072115  mov     rdi, [rbp+47h+arg_28]
0x180072119  test    al, al
0x18007211b  jz      short loc_180072136
0x18007211d  test    rdi, rdi
0x180072120  jz      short loc_180072136
0x180072122  mov     rcx, rdi; this
0x180072125  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x18007212a  test    rax, rax
0x18007212d  jnz     short loc_180072136
0x18007212f  xor     eax, eax
0x180072131  jmp     loc_180072609
0x180072136  lea     r8, [rbp+47h+var_78]
0x18007213a  mov     [rbp+47h+var_78], 0
0x180072142  mov     rdx, r15
0x180072145  mov     rcx, r12
0x180072148  call    ??_9IPackagedComCatalogContext@@$BBGA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{352,{flat}}
0x18007214d  xor     r15d, r15d
0x180072150  mov     ebx, eax
0x180072152  test    eax, eax
0x180072154  jns     short loc_180072173
0x180072156  mov     rcx, [rbp+4Fh]; this
0x18007215a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180072161  mov     r9d, eax; char *
0x180072164  mov     edx, 0F65h; void *
0x180072169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007216e  jmp     loc_180072607
0x180072173  lea     rax, [rbp+47h+var_78]
0x180072177  mov     [rbp+47h+var_60], r12
0x18007217b  mov     [rbp+47h+var_58], rax
0x18007217f  mov     r13d, r15d
0x180072182  mov     [rbp+47h+var_50], 1
0x180072186  xor     ecx, ecx; string
0x180072188  mov     [rbp+47h+var_90], r15b
0x18007218c  mov     [rbp+47h+string], r15
0x180072190  call    cs:__imp_WindowsDeleteString
0x180072197  nop     dword ptr [rax+rax+00h]
0x18007219c  mov     rdx, [rbp+47h+var_78]
0x1800721a0  lea     rax, [rbp+47h+string]
0x1800721a4  lea     r9, [rbp+47h+var_90]
0x1800721a8  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800721ad  mov     r8d, r13d
0x1800721b0  mov     [rbp+47h+string], r15
0x1800721b4  mov     rcx, r12
0x1800721b7  call    ??_9IPackagedComCatalogContext@@$BBGI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{360,{flat}}
0x1800721bc  mov     ebx, eax
0x1800721be  test    eax, eax
0x1800721c0  js      loc_1800725D2
0x1800721c6  cmp     [rbp+47h+var_90], r15b
0x1800721ca  jz      loc_1800722B5
0x1800721d0  test    rdi, rdi
0x1800721d3  jz      short loc_18007222E
0x1800721d5  mov     rcx, rdi; this
0x1800721d8  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800721dd  cmp     r15, rax
0x1800721e0  jnb     short loc_180072216
0x1800721e2  mov     rdx, r15; unsigned __int64
0x1800721e5  mov     rcx, rdi; this
0x1800721e8  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x1800721ed  mov     rcx, [rbp+47h+string]; string
0x1800721f1  xor     edx, edx; length
0x1800721f3  mov     rbx, rax
0x1800721f6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800721fd  nop     dword ptr [rax+rax+00h]
0x180072202  mov     rcx, rax; unsigned __int16 *
0x180072205  mov     rdx, rbx; unsigned __int16 *
0x180072208  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x18007220d  test    al, al
0x18007220f  jnz     short loc_18007222B
0x180072211  inc     r15
0x180072214  jmp     short loc_1800721D5
0x180072216  mov     rcx, [rbp+47h+string]; string
0x18007221a  call    cs:__imp_WindowsDeleteString
0x180072221  nop     dword ptr [rax+rax+00h]
0x180072226  xor     r15d, r15d
0x180072229  jmp     short loc_1800722A3
0x18007222b  xor     r15d, r15d
0x18007222e  movzx   eax, word ptr [rbp+47h+var_80+1]
0x180072232  lea     rdx, [rbp+47h+string]
0x180072236  mov     word ptr [rbp+47h+var_70+1], ax
0x18007223a  mov     rcx, rsi
0x18007223d  mov     al, byte ptr [rbp+47h+var_80+3]
0x180072240  mov     byte ptr [rbp+47h+var_70+3], al
0x180072243  movzx   eax, word ptr [rbp+47h+var_80+1]
0x180072247  mov     word ptr [rbp+47h+var_68+1], ax
0x18007224b  mov     al, byte ptr [rbp+47h+var_80+3]
0x18007224e  mov     byte ptr [rbp+47h+var_68+3], al
0x180072251  movzx   eax, word ptr [rbp+47h+var_80+1]
0x180072255  mov     word ptr [rbp+47h+var_80+1], ax
0x180072259  mov     al, byte ptr [rbp+47h+var_80+3]
0x18007225c  mov     byte ptr [rbp+47h+var_80+3], al
0x18007225f  mov     byte ptr [rbp+47h+var_70], r15b
0x180072263  mov     dword ptr [rbp+47h+var_70+4], r15d
0x180072267  mov     rax, [rbp+47h+var_70]
0x18007226b  mov     byte ptr [rbp+47h+var_68], r15b
0x18007226f  mov     dword ptr [rbp+47h+var_68+4], r15d
0x180072273  mov     r9, [rbp+47h+var_68]
0x180072277  mov     byte ptr [rbp+47h+var_80], r15b
0x18007227b  mov     dword ptr [rbp+47h+var_80+4], r15d
0x18007227f  mov     r8, [rbp+47h+var_80]
0x180072283  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180072288  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x18007228d  mov     ebx, eax
0x18007228f  test    eax, eax
0x180072291  js      short loc_1800722AB
0x180072293  mov     rcx, [rbp+47h+string]; string
0x180072297  call    cs:__imp_WindowsDeleteString
0x18007229e  nop     dword ptr [rax+rax+00h]
0x1800722a3  inc     r13d
0x1800722a6  jmp     loc_180072186
0x1800722ab  mov     edx, 0F8Ah
0x1800722b0  jmp     loc_1800725D7
0x1800722b5  mov     rcx, [rbp+47h+string]; string
0x1800722b9  call    cs:__imp_WindowsDeleteString
0x1800722c0  nop     dword ptr [rax+rax+00h]
0x1800722c5  mov     rax, [r12]
0x1800722c9  mov     rcx, r12
0x1800722cc  mov     rdx, [rbp+47h+var_78]
0x1800722d0  mov     [rbp+47h+var_50], r15b
0x1800722d4  mov     rax, [rax+20h]
0x1800722d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800722dd  mov     rbx, r15
0x1800722e0  mov     [rbp+47h+var_78], r15
0x1800722e4  mov     [rbp+47h+var_80], rbx
0x1800722e8  cmp     [rsi+88h], r15d
0x1800722ef  jz      short loc_180072305
0x1800722f1  mov     rdx, [rsi+80h]
0x1800722f8  lea     rcx, [rbp+47h+var_80]
0x1800722fc  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x180072301  mov     rbx, [rbp+47h+var_80]
0x180072305  cmp     [rbp+47h+arg_20], r15b
0x180072309  jz      loc_180072461
0x18007230f  mov     dword ptr [rbp+47h+string], r15d
0x180072313  test    r14, r14
0x180072316  jz      short loc_18007237A
0x180072318  mov     rax, [r14]
0x18007231b  lea     r8, [rbp+47h+string]
0x18007231f  mov     edx, 1
0x180072324  mov     rcx, r14
0x180072327  mov     rax, [rax+60h]
0x18007232b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072330  mov     edi, eax
0x180072332  test    eax, eax
0x180072334  jns     short loc_18007237A
0x180072336  mov     rcx, [rbp+4Fh]; this
0x18007233a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180072341  mov     r9d, eax; char *
0x180072344  mov     edx, 0FB4h; void *
0x180072349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007234e  mov     edx, dword ptr [rbp+47h+string]
0x180072351  test    edx, edx
0x180072353  jz      short loc_180072364
0x180072355  mov     rcx, [r14]
0x180072358  mov     rax, [rcx+68h]
0x18007235c  mov     rcx, r14
0x18007235f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072364  mov     rcx, rbx; string
0x180072367  call    cs:__imp_WindowsDeleteString
0x18007236e  nop     dword ptr [rax+rax+00h]
0x180072373  mov     eax, edi
0x180072375  jmp     loc_180072609
0x18007237a  mov     r15, [rsi+80h]
0x180072381  mov     eax, [rsi+88h]
0x180072387  shl     rax, 5
0x18007238b  add     rax, [rsi+80h]
0x180072392  cmp     r15, rax
0x180072395  jz      short loc_1800723F7
0x180072397  mov     rdx, [r15]
0x18007239a  lea     rax, [r15+8]
0x18007239e  mov     r9d, 1
0x1800723a4  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800723a9  mov     r8, r14
0x1800723ac  mov     rcx, r12
0x1800723af  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800723b4  mov     edi, eax
0x1800723b6  test    eax, eax
0x1800723b8  js      short loc_1800723C0
0x1800723ba  add     r15, 20h ; ' '
0x1800723be  jmp     short loc_180072381
0x1800723c0  mov     rcx, [rbp+4Fh]; this
0x1800723c4  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800723cb  mov     r9d, eax; char *
0x1800723ce  mov     edx, 0FBAh; void *
0x1800723d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800723d8  mov     edx, dword ptr [rbp+47h+string]
0x1800723db  test    edx, edx
0x1800723dd  jz      loc_1800724FC
0x1800723e3  mov     rax, [r14]
0x1800723e6  mov     rcx, r14
0x1800723e9  mov     rax, [rax+68h]
0x1800723ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800723f2  jmp     loc_1800724FC
0x1800723f7  mov     edx, dword ptr [rbp+47h+string]
0x1800723fa  test    edx, edx
0x1800723fc  jz      short loc_18007240D
0x1800723fe  mov     rax, [r14]
0x180072401  mov     rcx, r14
0x180072404  mov     rax, [rax+68h]
0x180072408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007240d  mov     rdi, [rsi+80h]
0x180072414  mov     eax, [rsi+88h]
0x18007241a  shl     rax, 5
0x18007241e  add     rax, [rsi+80h]
0x180072425  cmp     rdi, rax
0x180072428  jz      short loc_18007245E
0x18007242a  mov     rdx, [rdi]
0x18007242d  lea     rax, [rdi+18h]
0x180072431  mov     r9d, 2
0x180072437  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18007243c  mov     r8, r14
0x18007243f  mov     rcx, r12
0x180072442  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x180072447  mov     r15d, eax
0x18007244a  test    eax, eax
0x18007244c  js      short loc_180072454
0x18007244e  add     rdi, 20h ; ' '
0x180072452  jmp     short loc_180072414
0x180072454  mov     edx, 0FC9h
0x180072459  jmp     loc_1800724E6
0x18007245e  xor     r15d, r15d
0x180072461  mov     rdi, [rsi+80h]
0x180072468  mov     ecx, [rsi+88h]
0x18007246e  mov     eax, ecx
0x180072470  shl     rax, 5
0x180072474  add     rax, [rsi+80h]
0x18007247b  cmp     rdi, rax
0x18007247e  jz      loc_180072519
0x180072484  mov     rdx, [rdi]
0x180072487  lea     r13, [rdi+10h]
0x18007248b  xor     r9d, r9d
0x18007248e  mov     qword ptr [rsp+0D0h+var_B0], r13; int
0x180072493  mov     r8, r14
0x180072496  mov     rcx, r12
0x180072499  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x18007249e  mov     r15d, eax
0x1800724a1  test    eax, eax
0x1800724a3  js      short loc_1800724E1
0x1800724a5  xor     r15d, r15d
0x1800724a8  cmp     [rdi+8], r15b
0x1800724ac  jz      short loc_1800724B9
0x1800724ae  cmp     [rdi+18h], r15b
0x1800724b2  jz      short loc_1800724B9
0x1800724b4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800724b9  cmp     [r13+0], r15b
0x1800724bd  jnz     short loc_1800724DB
0x1800724bf  cmp     [rdi+8], r15b
0x1800724c3  jnz     short loc_1800724DB
0x1800724c5  cmp     [rdi+18h], r15b
0x1800724c9  jnz     short loc_1800724DB
0x1800724cb  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x1800724ce  mov     rcx, rsi; this
0x1800724d1  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x1800724d6  mov     rdi, rax
0x1800724d9  jmp     short loc_180072468
0x1800724db  add     rdi, 20h ; ' '
0x1800724df  jmp     short loc_180072468
0x1800724e1  mov     edx, 0FD4h; void *
0x1800724e6  mov     rcx, [rbp+4Fh]; this
0x1800724ea  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800724f1  mov     r9d, r15d; char *
0x1800724f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800724f9  mov     edi, r15d
0x1800724fc  mov     rcx, rbx; string
0x1800724ff  call    cs:__imp_WindowsDeleteString
0x180072506  nop     dword ptr [rax+rax+00h]
0x18007250b  lea     rcx, [rbp+47h+var_60]
0x18007250f  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x180072514  jmp     loc_180072373
0x180072519  test    rbx, rbx
0x18007251c  jz      loc_1800725BE
0x180072522  test    ecx, ecx
0x180072524  jnz     loc_1800725BE
0x18007252a  xor     edx, edx
0x18007252c  mov     [rbp+47h+string], r15
0x180072530  lea     rcx, [rbp+47h+string]
0x180072534  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180072539  mov     rcx, [rbp+47h+rguid]; rguid
0x18007253d  lea     rdx, [rbp+47h+string]; string
0x180072541  call    ?GetIdString@@YAJAEBU_GUID@@PEAPEAUHSTRING__@@@Z; GetIdString(_GUID const &,HSTRING__ * *)
0x180072546  test    eax, eax
0x180072548  js      short loc_1800725B5
0x18007254a  xor     edx, edx; length
0x18007254c  mov     rcx, rbx; string
0x18007254f  call    cs:__imp_WindowsGetStringRawBuffer
  ... truncated ...
```
