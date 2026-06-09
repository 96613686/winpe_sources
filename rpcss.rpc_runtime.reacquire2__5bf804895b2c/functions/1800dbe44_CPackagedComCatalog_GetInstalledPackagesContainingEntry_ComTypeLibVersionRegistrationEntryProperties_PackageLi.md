# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTypeLibVersionRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)

- ea: `0x1800dbe44`
- end: `0x1800dc2ed`
- name: `??$GetInstalledPackagesContainingEntry@UComTypeLibVersionRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z`
- size: `1193`
- prototype: `__int64 __usercall@<rax>(PackageListBuffer *this@<rcx>, char, PackageFilter *)`
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800adba8`
- `0x1800ae8d4`
- `0x1800eb578`

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
- `0x1800dbe44`
- `0x1800e0720`
- `0x1800e0738`
- `0x1800e482c`
- `0x1800e5844`
- `0x1800e5898`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbefc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbf86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc001`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc1bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc280`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc2b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbefc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbf86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc001`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc1bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc280`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc2b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbf62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbf62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc224`

## string_xrefs

- `0x1800dbec2`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dc0b3`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dc1a8`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dc23f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dc2a3`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dc250`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x1800dc25e`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTypeLibVersionRegistrationEntryProperties>(
        PackageListBuffer *this,
        HSTRING a2,
        __int64 a3,
        GUID *a4,
        char a5,
        PackageFilter *a6)
{
  char IsEnabled; // al
  PackageFilter *v10; // rdi
  int v12; // eax
  unsigned __int64 v13; // r14
  int v14; // ebx
  char v15; // r13
  unsigned int v16; // r15d
  const unsigned __int16 *PackageFullName; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v19; // rdx
  HSTRING v20; // rbx
  char v21; // r13
  _QWORD *i; // r14
  int ComPackageInstallOrder; // eax
  unsigned int v24; // edi
  _QWORD *j; // rdi
  int v26; // r14d
  __int64 v27; // rdx
  struct PackageIdAndInstallOrders *v28; // rdi
  __int64 v29; // rcx
  PCWSTR v30; // rdi
  const char *v31; // rax
  __int64 v32; // rdx
  int v33; // [rsp+20h] [rbp-60h]
  HSTRING *p_string; // [rsp+20h] [rbp-60h]
  int v35; // [rsp+20h] [rbp-60h]
  char *v36; // [rsp+28h] [rbp-58h]
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v38; // [rsp+48h] [rbp-38h]
  int v39; // [rsp+4Ch] [rbp-34h]
  int v40; // [rsp+50h] [rbp-30h]
  int v41; // [rsp+54h] [rbp-2Ch]
  int v42; // [rsp+58h] [rbp-28h]
  int v43; // [rsp+5Ch] [rbp-24h]
  __int64 v44; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v45[2]; // [rsp+68h] [rbp-18h] BYREF
  char v46; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  HSTRING v48; // [rsp+C8h] [rbp+48h] BYREF
  GUID *rguid; // [rsp+D8h] [rbp+58h]

  rguid = a4;
  v48 = a2;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
  v10 = a6;
  if ( IsEnabled && a6 && !PackageFilter::GetPackageCount(a6) )
    return 0;
  v44 = 0;
  v12 =  IPackagedComCatalogContext::`vcall'{320,{flat}}(a3, a4, &v44);
  v13 = 0;
  v14 = v12;
  if ( v12 >= 0 )
  {
    v15 = BYTE3(v48);
    v45[1] = &v44;
    v16 = 0;
    v45[0] = a3;
    v46 = 1;
    while ( 1 )
    {
      LOBYTE(v48) = 0;
      string = 0;
      WindowsDeleteString(0);
      p_string = &string;
      string = 0;
      v14 =  IPackagedComCatalogContext::`vcall'{328,{flat}}(a3, v44, v16, &v48);
      if ( v14 < 0 )
      {
        v19 = 3953;
        goto LABEL_57;
      }
      if ( !(_BYTE)v48 )
        break;
      if ( v10 )
      {
        while ( 1 )
        {
          if ( v13 >= PackageFilter::GetPackageCount(v10) )
          {
            WindowsDeleteString(string);
            v13 = 0;
            goto LABEL_18;
          }
          PackageFullName = PackageFilter::GetPackageFullName(v10, v13);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( PackageNamesMatch(StringRawBuffer, PackageFullName) )
            break;
          ++v13;
        }
        v13 = 0;
      }
      *(_WORD *)((char *)&v38 + 1) = *(_WORD *)((char *)&v48 + 1);
      *(_WORD *)((char *)&v40 + 1) = *(_WORD *)((char *)&v48 + 1);
      HIBYTE(v40) = BYTE3(v48);
      *(_WORD *)((char *)&v42 + 1) = *(_WORD *)((char *)&v48 + 1);
      HIBYTE(v42) = BYTE3(v48);
      LOBYTE(v38) = 0;
      HIBYTE(v38) = v15;
      v39 = 0;
      LOBYTE(v40) = 0;
      v41 = 0;
      LOBYTE(v42) = 0;
      v43 = 0;
      v14 = PackageListBuffer::AddPackage((_DWORD)this, (unsigned int)&string, v42, v40, v38);
      if ( v14 < 0 )
      {
        v19 = 3978;
LABEL_57:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v14,
          (int)p_string);
        WindowsDeleteString(string);
        string = 0;
        wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v45);
        return (unsigned int)v14;
      }
      WindowsDeleteString(string);
LABEL_18:
      ++v16;
    }
    WindowsDeleteString(string);
    wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v45);
    v20 = 0;
    v48 = 0;
    if ( *((_DWORD *)this + 34) )
    {
      OpaqueString::operator=(&v48, *((_QWORD *)this + 16));
      v20 = v48;
    }
    v21 = a5;
    if ( a5 )
    {
      for ( i = (_QWORD *)*((_QWORD *)this + 16);
            i != (_QWORD *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34));
            i += 4 )
      {
        ComPackageInstallOrder = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *i, 0, 1);
        v24 = ComPackageInstallOrder;
        if ( ComPackageInstallOrder < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFBA,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)ComPackageInstallOrder,
            (_DWORD)i + 8);
LABEL_46:
          WindowsDeleteString(v20);
          wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v45);
          return v24;
        }
      }
      for ( j = (_QWORD *)*((_QWORD *)this + 16);
            j != (_QWORD *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34));
            j += 4 )
      {
        v35 = (_DWORD)j + 24;
        v26 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *j, 0, 2);
        if ( v26 < 0 )
        {
          v27 = 4041;
LABEL_45:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v26,
            v35);
          v24 = v26;
          goto LABEL_46;
        }
      }
    }
    v28 = (struct PackageIdAndInstallOrders *)*((_QWORD *)this + 16);
    while ( v28 != (struct PackageIdAndInstallOrders *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34)) )
    {
      v35 = (_DWORD)v28 + 16;
      v26 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *(_QWORD *)v28, 0, 0);
      if ( v26 < 0 )
      {
        v27 = 4052;
        goto LABEL_45;
      }
      if ( *((_BYTE *)v28 + 8) && *((_BYTE *)v28 + 24) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v29);
      if ( *((_BYTE *)v28 + 16) || *((_BYTE *)v28 + 8) || *((_BYTE *)v28 + 24) )
        v28 = (struct PackageIdAndInstallOrders *)((char *)v28 + 32);
      else
        v28 = PackageListBuffer::RemoveAt(this, v28);
    }
    if ( v20 && !*((_DWORD *)this + 34) )
    {
      v48 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v48,
        0);
      if ( (int)GetIdString(rguid, &v48) >= 0 )
      {
        v30 = WindowsGetStringRawBuffer(v20, 0);
        v36 = (char *)WindowsGetStringRawBuffer(v48, 0);
        if ( v21 )
        {
          v31 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the"
                " caller. Package may not be installed for user.";
          v32 = 4086;
        }
        else
        {
          v31 = "Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the"
                " caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, n"
                "on-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).";
          v32 = 4092;
        }
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)v32,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)0x8002801DLL,
          (int)v31,
          v36,
          v30);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v48);
    }
    WindowsDeleteString(v20);
    wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v45);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF65,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)v12,
    v33);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800dbe44  mov     [rsp-38h+arg_0], rbx
0x1800dbe49  mov     [rsp-38h+rguid], r9
0x1800dbe4e  mov     [rsp-38h+arg_8], rdx
0x1800dbe53  push    rbp
0x1800dbe54  push    rsi
0x1800dbe55  push    rdi
0x1800dbe56  push    r12
0x1800dbe58  push    r13
0x1800dbe5a  push    r14
0x1800dbe5c  push    r15
0x1800dbe5e  mov     rbp, rsp
0x1800dbe61  sub     rsp, 80h
0x1800dbe68  mov     r14, r9
0x1800dbe6b  mov     r12, r8
0x1800dbe6e  mov     rsi, rcx
0x1800dbe71  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800dbe78  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800dbe7d  mov     rdi, [rbp+arg_28]
0x1800dbe81  test    al, al
0x1800dbe83  jz      short loc_1800DBE9E
0x1800dbe85  test    rdi, rdi
0x1800dbe88  jz      short loc_1800DBE9E
0x1800dbe8a  mov     rcx, rdi; this
0x1800dbe8d  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800dbe92  test    rax, rax
0x1800dbe95  jnz     short loc_1800DBE9E
0x1800dbe97  xor     eax, eax
0x1800dbe99  jmp     loc_1800DC2D1
0x1800dbe9e  lea     r8, [rbp+var_20]
0x1800dbea2  mov     [rbp+var_20], 0
0x1800dbeaa  mov     rdx, r14
0x1800dbead  mov     rcx, r12
0x1800dbeb0  call    ??_9IPackagedComCatalogContext@@$BBEA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{320,{flat}}
0x1800dbeb5  xor     r14d, r14d
0x1800dbeb8  mov     ebx, eax
0x1800dbeba  test    eax, eax
0x1800dbebc  jns     short loc_1800DBEDB
0x1800dbebe  mov     rcx, [rbp+38h]; this
0x1800dbec2  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dbec9  mov     r9d, eax; char *
0x1800dbecc  mov     edx, 0F65h; void *
0x1800dbed1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbed6  jmp     loc_1800DC2CF
0x1800dbedb  mov     r13b, byte ptr [rbp+arg_8+3]
0x1800dbedf  lea     rax, [rbp+var_20]
0x1800dbee3  mov     [rbp+var_10], rax
0x1800dbee7  mov     r15d, r14d
0x1800dbeea  mov     [rbp+var_18], r12
0x1800dbeee  mov     [rbp+var_8], 1
0x1800dbef2  xor     ecx, ecx; string
0x1800dbef4  mov     byte ptr [rbp+arg_8], r14b
0x1800dbef8  mov     [rbp+string], r14
0x1800dbefc  call    cs:__imp_WindowsDeleteString
0x1800dbf03  nop     dword ptr [rax+rax+00h]
0x1800dbf08  mov     rdx, [rbp+var_20]
0x1800dbf0c  lea     rax, [rbp+string]
0x1800dbf10  lea     r9, [rbp+arg_8]
0x1800dbf14  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800dbf19  mov     r8d, r15d
0x1800dbf1c  mov     [rbp+string], r14
0x1800dbf20  mov     rcx, r12
0x1800dbf23  call    ??_9IPackagedComCatalogContext@@$BBEI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{328,{flat}}
0x1800dbf28  mov     ebx, eax
0x1800dbf2a  test    eax, eax
0x1800dbf2c  js      loc_1800DC29A
0x1800dbf32  cmp     byte ptr [rbp+arg_8], r14b
0x1800dbf36  jz      loc_1800DC01F
0x1800dbf3c  test    rdi, rdi
0x1800dbf3f  jz      short loc_1800DBF9A
0x1800dbf41  mov     rcx, rdi; this
0x1800dbf44  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800dbf49  cmp     r14, rax
0x1800dbf4c  jnb     short loc_1800DBF82
0x1800dbf4e  mov     rdx, r14; unsigned __int64
0x1800dbf51  mov     rcx, rdi; this
0x1800dbf54  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x1800dbf59  mov     rcx, [rbp+string]; string
0x1800dbf5d  xor     edx, edx; length
0x1800dbf5f  mov     rbx, rax
0x1800dbf62  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dbf69  nop     dword ptr [rax+rax+00h]
0x1800dbf6e  mov     rcx, rax; unsigned __int16 *
0x1800dbf71  mov     rdx, rbx; unsigned __int16 *
0x1800dbf74  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x1800dbf79  test    al, al
0x1800dbf7b  jnz     short loc_1800DBF97
0x1800dbf7d  inc     r14
0x1800dbf80  jmp     short loc_1800DBF41
0x1800dbf82  mov     rcx, [rbp+string]; string
0x1800dbf86  call    cs:__imp_WindowsDeleteString
0x1800dbf8d  nop     dword ptr [rax+rax+00h]
0x1800dbf92  xor     r14d, r14d
0x1800dbf95  jmp     short loc_1800DC00D
0x1800dbf97  xor     r14d, r14d
0x1800dbf9a  movzx   eax, word ptr [rbp+arg_8+1]
0x1800dbf9e  lea     rdx, [rbp+string]
0x1800dbfa2  mov     word ptr [rbp+var_38+1], ax
0x1800dbfa6  mov     rcx, rsi
0x1800dbfa9  movzx   eax, word ptr [rbp+arg_8+1]
0x1800dbfad  mov     word ptr [rbp+var_30+1], ax
0x1800dbfb1  mov     al, byte ptr [rbp+arg_8+3]
0x1800dbfb4  mov     byte ptr [rbp+var_30+3], al
0x1800dbfb7  movzx   eax, word ptr [rbp+arg_8+1]
0x1800dbfbb  mov     word ptr [rbp+var_28+1], ax
0x1800dbfbf  mov     al, byte ptr [rbp+arg_8+3]
0x1800dbfc2  mov     byte ptr [rbp+var_28+3], al
0x1800dbfc5  mov     byte ptr [rbp+var_38], r14b
0x1800dbfc9  mov     byte ptr [rbp+var_38+3], r13b
0x1800dbfcd  mov     dword ptr [rbp+var_38+4], r14d
0x1800dbfd1  mov     rax, [rbp+var_38]
0x1800dbfd5  mov     byte ptr [rbp+var_30], r14b
0x1800dbfd9  mov     dword ptr [rbp+var_30+4], r14d
0x1800dbfdd  mov     r9, [rbp+var_30]
0x1800dbfe1  mov     byte ptr [rbp+var_28], r14b
0x1800dbfe5  mov     dword ptr [rbp+var_28+4], r14d
0x1800dbfe9  mov     r8, [rbp+var_28]
0x1800dbfed  mov     qword ptr [rsp+80h+var_60], rax
0x1800dbff2  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x1800dbff7  mov     ebx, eax
0x1800dbff9  test    eax, eax
0x1800dbffb  js      short loc_1800DC015
0x1800dbffd  mov     rcx, [rbp+string]; string
0x1800dc001  call    cs:__imp_WindowsDeleteString
0x1800dc008  nop     dword ptr [rax+rax+00h]
0x1800dc00d  inc     r15d
0x1800dc010  jmp     loc_1800DBEF2
0x1800dc015  mov     edx, 0F8Ah
0x1800dc01a  jmp     loc_1800DC29F
0x1800dc01f  mov     rcx, [rbp+string]; string
0x1800dc023  call    cs:__imp_WindowsDeleteString
0x1800dc02a  nop     dword ptr [rax+rax+00h]
0x1800dc02f  lea     rcx, [rbp+var_18]
0x1800dc033  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800dc038  mov     rbx, r14
0x1800dc03b  mov     [rbp+arg_8], rbx
0x1800dc03f  cmp     [rsi+88h], r14d
0x1800dc046  jz      short loc_1800DC05C
0x1800dc048  mov     rdx, [rsi+80h]
0x1800dc04f  lea     rcx, [rbp+arg_8]
0x1800dc053  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800dc058  mov     rbx, [rbp+arg_8]
0x1800dc05c  mov     r13b, [rbp+arg_20]
0x1800dc060  test    r13b, r13b
0x1800dc063  jz      loc_1800DC120
0x1800dc069  mov     r14, [rsi+80h]
0x1800dc070  mov     eax, [rsi+88h]
0x1800dc076  shl     rax, 5
0x1800dc07a  add     rax, [rsi+80h]
0x1800dc081  cmp     r14, rax
0x1800dc084  jz      short loc_1800DC0CC
0x1800dc086  mov     rdx, [r14]
0x1800dc089  lea     rax, [r14+8]
0x1800dc08d  mov     r9d, 1
0x1800dc093  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800dc098  xor     r8d, r8d
0x1800dc09b  mov     rcx, r12
0x1800dc09e  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800dc0a3  mov     edi, eax
0x1800dc0a5  test    eax, eax
0x1800dc0a7  js      short loc_1800DC0AF
0x1800dc0a9  add     r14, 20h ; ' '
0x1800dc0ad  jmp     short loc_1800DC070
0x1800dc0af  mov     rcx, [rbp+38h]; this
0x1800dc0b3  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dc0ba  mov     r9d, eax; char *
0x1800dc0bd  mov     edx, 0FBAh; void *
0x1800dc0c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dc0c7  jmp     loc_1800DC1BA
0x1800dc0cc  mov     rdi, [rsi+80h]
0x1800dc0d3  mov     eax, [rsi+88h]
0x1800dc0d9  shl     rax, 5
0x1800dc0dd  add     rax, [rsi+80h]
0x1800dc0e4  cmp     rdi, rax
0x1800dc0e7  jz      short loc_1800DC11D
0x1800dc0e9  mov     rdx, [rdi]
0x1800dc0ec  lea     rax, [rdi+18h]
0x1800dc0f0  mov     r9d, 2
0x1800dc0f6  mov     qword ptr [rsp+80h+var_60], rax
0x1800dc0fb  xor     r8d, r8d
0x1800dc0fe  mov     rcx, r12
0x1800dc101  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800dc106  mov     r14d, eax
0x1800dc109  test    eax, eax
0x1800dc10b  js      short loc_1800DC113
0x1800dc10d  add     rdi, 20h ; ' '
0x1800dc111  jmp     short loc_1800DC0D3
0x1800dc113  mov     edx, 0FC9h
0x1800dc118  jmp     loc_1800DC1A4
0x1800dc11d  xor     r14d, r14d
0x1800dc120  mov     rdi, [rsi+80h]
0x1800dc127  mov     ecx, [rsi+88h]
0x1800dc12d  mov     eax, ecx
0x1800dc12f  shl     rax, 5
0x1800dc133  add     rax, [rsi+80h]
0x1800dc13a  cmp     rdi, rax
0x1800dc13d  jz      loc_1800DC1D9
0x1800dc143  mov     rdx, [rdi]
0x1800dc146  lea     r15, [rdi+10h]
0x1800dc14a  xor     r9d, r9d
0x1800dc14d  mov     qword ptr [rsp+80h+var_60], r15; int
0x1800dc152  xor     r8d, r8d
0x1800dc155  mov     rcx, r12
0x1800dc158  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800dc15d  mov     r14d, eax
0x1800dc160  test    eax, eax
0x1800dc162  js      short loc_1800DC19F
0x1800dc164  xor     r14d, r14d
0x1800dc167  cmp     [rdi+8], r14b
0x1800dc16b  jz      short loc_1800DC178
0x1800dc16d  cmp     [rdi+18h], r14b
0x1800dc171  jz      short loc_1800DC178
0x1800dc173  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800dc178  cmp     [r15], r14b
0x1800dc17b  jnz     short loc_1800DC199
0x1800dc17d  cmp     [rdi+8], r14b
0x1800dc181  jnz     short loc_1800DC199
0x1800dc183  cmp     [rdi+18h], r14b
0x1800dc187  jnz     short loc_1800DC199
0x1800dc189  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x1800dc18c  mov     rcx, rsi; this
0x1800dc18f  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x1800dc194  mov     rdi, rax
0x1800dc197  jmp     short loc_1800DC127
0x1800dc199  add     rdi, 20h ; ' '
0x1800dc19d  jmp     short loc_1800DC127
0x1800dc19f  mov     edx, 0FD4h; void *
0x1800dc1a4  mov     rcx, [rbp+38h]; this
0x1800dc1a8  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dc1af  mov     r9d, r14d; char *
0x1800dc1b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dc1b7  mov     edi, r14d
0x1800dc1ba  mov     rcx, rbx; string
0x1800dc1bd  call    cs:__imp_WindowsDeleteString
0x1800dc1c4  nop     dword ptr [rax+rax+00h]
0x1800dc1c9  lea     rcx, [rbp+var_18]
0x1800dc1cd  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800dc1d2  mov     eax, edi
0x1800dc1d4  jmp     loc_1800DC2D1
0x1800dc1d9  test    rbx, rbx
0x1800dc1dc  jz      loc_1800DC27D
0x1800dc1e2  test    ecx, ecx
0x1800dc1e4  jnz     loc_1800DC27D
0x1800dc1ea  xor     edx, edx
0x1800dc1ec  mov     [rbp+arg_8], r14
0x1800dc1f0  lea     rcx, [rbp+arg_8]
0x1800dc1f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800dc1f9  mov     rcx, [rbp+rguid]; rguid
0x1800dc1fd  lea     rdx, [rbp+arg_8]; string
0x1800dc201  call    ?GetIdString@@YAJAEBU_GUID@@PEAPEAUHSTRING__@@@Z; GetIdString(_GUID const &,HSTRING__ * *)
0x1800dc206  test    eax, eax
0x1800dc208  js      short loc_1800DC274
0x1800dc20a  xor     edx, edx; length
0x1800dc20c  mov     rcx, rbx; string
0x1800dc20f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc216  nop     dword ptr [rax+rax+00h]
0x1800dc21b  mov     rcx, [rbp+arg_8]; string
0x1800dc21f  xor     edx, edx; length
0x1800dc221  mov     rdi, rax
0x1800dc224  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc22b  nop     dword ptr [rax+rax+00h]
0x1800dc230  mov     rcx, [rbp+38h]; this
0x1800dc234  mov     r9d, 8002801Dh; char *
0x1800dc23a  mov     [rsp+80h+var_50], rdi
0x1800dc23f  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dc246  mov     [rsp+80h+var_58], rax; char *
0x1800dc24b  test    r13b, r13b
0x1800dc24e  jz      short loc_1800DC25E
0x1800dc250  lea     rax, aWarningPackage_0; "Warning: PackagedCom entry for %ls in p"...
0x1800dc257  mov     edx, 0FF6h
0x1800dc25c  jmp     short loc_1800DC26A
0x1800dc25e  lea     rax, aWarningPackage; "Warning: PackagedCom entry for %ls in p"...
0x1800dc265  mov     edx, 0FFCh; void *
0x1800dc26a  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800dc26f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800dc274  lea     rcx, [rbp+arg_8]
0x1800dc278  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800dc27d  mov     rcx, rbx; string
0x1800dc280  call    cs:__imp_WindowsDeleteString
0x1800dc287  nop     dword ptr [rax+rax+00h]
0x1800dc28c  lea     rcx, [rbp+var_18]
0x1800dc290  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800dc295  jmp     loc_1800DBE97
0x1800dc29a  mov     edx, 0F71h; void *
0x1800dc29f  mov     rcx, [rbp+38h]; this
0x1800dc2a3  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dc2aa  mov     r9d, ebx; char *
0x1800dc2ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dc2b2  mov     rcx, [rbp+string]; string
0x1800dc2b6  call    cs:__imp_WindowsDeleteString
0x1800dc2bd  nop     dword ptr [rax+rax+00h]
0x1800dc2c2  lea     rcx, [rbp+var_18]
0x1800dc2c6  mov     [rbp+string], r14
0x1800dc2ca  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800dc2cf  mov     eax, ebx
0x1800dc2d1  mov     rbx, [rsp+80h+arg_0]
0x1800dc2d9  add     rsp, 80h
0x1800dc2e0  pop     r15
0x1800dc2e2  pop     r14
0x1800dc2e4  pop     r13
0x1800dc2e6  pop     r12
  ... truncated ...
```
