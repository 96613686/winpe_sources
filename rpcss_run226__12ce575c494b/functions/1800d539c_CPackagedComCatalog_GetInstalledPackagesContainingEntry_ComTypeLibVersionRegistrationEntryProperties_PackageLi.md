# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTypeLibVersionRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)

- ea: `0x1800d539c`
- end: `0x1800d5808`
- name: `??$GetInstalledPackagesContainingEntry@UComTypeLibVersionRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z`
- size: `1132`
- prototype: `__int64 __usercall@<rax>(PackageListBuffer *this@<rcx>, char, PackageFilter *)`
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a8ad4`
- `0x1800a97ac`
- `0x1800e40ac`

## callees

- `0x180005c40`
- `0x18002ba28`
- `0x18002effc`
- `0x1800414d0`
- `0x180043850`
- `0x180047f88`
- `0x18004844c`
- `0x18004853c`
- `0x18006d90c`
- `0x18006df38`
- `0x18008e98c`
- `0x1800a167c`
- `0x1800d539c`
- `0x1800d99b8`
- `0x1800d99d0`
- `0x1800dd864`
- `0x1800de7e4`
- `0x1800de834`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d54d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d56f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d57a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d57d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d54d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d56f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d57a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d57d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d54b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5752`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d54b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5752`

## string_xrefs

- `0x1800d541a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d55ed`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d56e2`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d5767`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d57c5`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d5778`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x1800d5786`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

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
  __int64 i; // r14
  int ComPackageInstallOrder; // eax
  unsigned int v24; // edi
  __int64 j; // rdi
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
  int v36; // [rsp+20h] [rbp-60h]
  char *v37; // [rsp+28h] [rbp-58h]
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v39; // [rsp+48h] [rbp-38h]
  int v40; // [rsp+4Ch] [rbp-34h]
  unsigned int v41; // [rsp+50h] [rbp-30h]
  int v42; // [rsp+54h] [rbp-2Ch]
  unsigned int v43; // [rsp+58h] [rbp-28h]
  int v44; // [rsp+5Ch] [rbp-24h]
  __int64 v45; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v46[2]; // [rsp+68h] [rbp-18h] BYREF
  char v47; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  HSTRING v49; // [rsp+C8h] [rbp+48h] BYREF
  GUID *rguid; // [rsp+D8h] [rbp+58h]

  rguid = a4;
  v49 = a2;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
  v10 = a6;
  if ( IsEnabled && a6 && !PackageFilter::GetPackageCount(a6) )
    return 0;
  v45 = 0;
  v12 =  IPackagedComCatalogContext::`vcall'{320,{flat}}(a3, a4, &v45);
  v13 = 0;
  v14 = v12;
  if ( v12 >= 0 )
  {
    v15 = BYTE3(v49);
    v46[1] = &v45;
    v16 = 0;
    v46[0] = a3;
    v47 = 1;
    while ( 1 )
    {
      LOBYTE(v49) = 0;
      string = 0;
      WindowsDeleteString(0);
      p_string = &string;
      string = 0;
      v14 =  IPackagedComCatalogContext::`vcall'{328,{flat}}(a3, v45, v16, &v49);
      if ( v14 < 0 )
      {
        v19 = 3953;
        goto LABEL_57;
      }
      if ( !(_BYTE)v49 )
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
      *(_WORD *)((char *)&v39 + 1) = *(_WORD *)((char *)&v49 + 1);
      *(_WORD *)((char *)&v41 + 1) = *(_WORD *)((char *)&v49 + 1);
      HIBYTE(v41) = BYTE3(v49);
      *(_WORD *)((char *)&v43 + 1) = *(_WORD *)((char *)&v49 + 1);
      HIBYTE(v43) = BYTE3(v49);
      LOBYTE(v39) = 0;
      HIBYTE(v39) = v15;
      v40 = 0;
      LOBYTE(v41) = 0;
      v42 = 0;
      LOBYTE(v43) = 0;
      v44 = 0;
      v14 = PackageListBuffer::AddPackage((__int64)this, &string, (HSTRING)v43, (HSTRING)v41, (HSTRING)v39);
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
        wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v46);
        return (unsigned int)v14;
      }
      WindowsDeleteString(string);
LABEL_18:
      ++v16;
    }
    WindowsDeleteString(string);
    wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v46);
    v20 = 0;
    v49 = 0;
    if ( *((_DWORD *)this + 34) )
    {
      OpaqueString::operator=(&v49, *((_QWORD *)this + 16));
      v20 = v49;
    }
    v21 = a5;
    if ( a5 )
    {
      for ( i = *((_QWORD *)this + 16); i != *((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34); i += 32 )
      {
        ComPackageInstallOrder = CPackagedComCatalog::TryGetComPackageInstallOrder(
                                   a3,
                                   *(HSTRING *)i,
                                   0,
                                   1u,
                                   (_BYTE *)(i + 8));
        v24 = ComPackageInstallOrder;
        if ( ComPackageInstallOrder < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFBA,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)ComPackageInstallOrder,
            v35);
LABEL_46:
          WindowsDeleteString(v20);
          wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v46);
          return v24;
        }
      }
      for ( j = *((_QWORD *)this + 16); j != *((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34); j += 32 )
      {
        v26 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *(HSTRING *)j, 0, 2u, (_BYTE *)(j + 24));
        if ( v26 < 0 )
        {
          v27 = 4041;
LABEL_45:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v26,
            v36);
          v24 = v26;
          goto LABEL_46;
        }
      }
    }
    v28 = (struct PackageIdAndInstallOrders *)*((_QWORD *)this + 16);
    while ( v28 != (struct PackageIdAndInstallOrders *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34)) )
    {
      v26 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *(HSTRING *)v28, 0, 0, (_BYTE *)v28 + 16);
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
      v49 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v49,
        0);
      if ( (int)GetIdString(rguid, &v49) >= 0 )
      {
        v30 = WindowsGetStringRawBuffer(v20, 0);
        v37 = (char *)WindowsGetStringRawBuffer(v49, 0);
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
          v37,
          v30);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v49);
    }
    WindowsDeleteString(v20);
    wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v46);
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
0x1800d539c  mov     [rsp-38h+arg_0], rbx
0x1800d53a1  mov     [rsp-38h+rguid], r9
0x1800d53a6  mov     [rsp-38h+arg_8], rdx
0x1800d53ab  push    rbp
0x1800d53ac  push    rsi
0x1800d53ad  push    rdi
0x1800d53ae  push    r12
0x1800d53b0  push    r13
0x1800d53b2  push    r14
0x1800d53b4  push    r15
0x1800d53b6  mov     rbp, rsp
0x1800d53b9  sub     rsp, 80h
0x1800d53c0  mov     r14, r9
0x1800d53c3  mov     r12, r8
0x1800d53c6  mov     rsi, rcx
0x1800d53c9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800d53d0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800d53d5  mov     rdi, [rbp+arg_28]
0x1800d53d9  test    al, al
0x1800d53db  jz      short loc_1800D53F6
0x1800d53dd  test    rdi, rdi
0x1800d53e0  jz      short loc_1800D53F6
0x1800d53e2  mov     rcx, rdi; this
0x1800d53e5  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800d53ea  test    rax, rax
0x1800d53ed  jnz     short loc_1800D53F6
0x1800d53ef  xor     eax, eax
0x1800d53f1  jmp     loc_1800D57ED
0x1800d53f6  lea     r8, [rbp+var_20]
0x1800d53fa  mov     [rbp+var_20], 0
0x1800d5402  mov     rdx, r14
0x1800d5405  mov     rcx, r12
0x1800d5408  call    ??_9IPackagedComCatalogContext@@$BBEA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{320,{flat}}
0x1800d540d  xor     r14d, r14d
0x1800d5410  mov     ebx, eax
0x1800d5412  test    eax, eax
0x1800d5414  jns     short loc_1800D5433
0x1800d5416  mov     rcx, [rbp+38h]; this
0x1800d541a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d5421  mov     r9d, eax; char *
0x1800d5424  mov     edx, 0F65h; void *
0x1800d5429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d542e  jmp     loc_1800D57EB
0x1800d5433  mov     r13b, byte ptr [rbp+arg_8+3]
0x1800d5437  lea     rax, [rbp+var_20]
0x1800d543b  mov     [rbp+var_10], rax
0x1800d543f  mov     r15d, r14d
0x1800d5442  mov     [rbp+var_18], r12
0x1800d5446  mov     [rbp+var_8], 1
0x1800d544a  xor     ecx, ecx; string
0x1800d544c  mov     byte ptr [rbp+arg_8], r14b
0x1800d5450  mov     [rbp+string], r14
0x1800d5454  call    cs:__imp_WindowsDeleteString
0x1800d545a  mov     rdx, [rbp+var_20]
0x1800d545e  lea     rax, [rbp+string]
0x1800d5462  lea     r9, [rbp+arg_8]
0x1800d5466  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800d546b  mov     r8d, r15d
0x1800d546e  mov     [rbp+string], r14
0x1800d5472  mov     rcx, r12
0x1800d5475  call    ??_9IPackagedComCatalogContext@@$BBEI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{328,{flat}}
0x1800d547a  mov     ebx, eax
0x1800d547c  test    eax, eax
0x1800d547e  js      loc_1800D57BC
0x1800d5484  cmp     byte ptr [rbp+arg_8], r14b
0x1800d5488  jz      loc_1800D555F
0x1800d548e  test    rdi, rdi
0x1800d5491  jz      short loc_1800D54E0
0x1800d5493  mov     rcx, rdi; this
0x1800d5496  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800d549b  cmp     r14, rax
0x1800d549e  jnb     short loc_1800D54CE
0x1800d54a0  mov     rdx, r14; unsigned __int64
0x1800d54a3  mov     rcx, rdi; this
0x1800d54a6  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x1800d54ab  mov     rcx, [rbp+string]; string
0x1800d54af  xor     edx, edx; length
0x1800d54b1  mov     rbx, rax
0x1800d54b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d54ba  mov     rcx, rax; unsigned __int16 *
0x1800d54bd  mov     rdx, rbx; unsigned __int16 *
0x1800d54c0  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x1800d54c5  test    al, al
0x1800d54c7  jnz     short loc_1800D54DD
0x1800d54c9  inc     r14
0x1800d54cc  jmp     short loc_1800D5493
0x1800d54ce  mov     rcx, [rbp+string]; string
0x1800d54d2  call    cs:__imp_WindowsDeleteString
0x1800d54d8  xor     r14d, r14d
0x1800d54db  jmp     short loc_1800D554D
0x1800d54dd  xor     r14d, r14d
0x1800d54e0  movzx   eax, word ptr [rbp+arg_8+1]
0x1800d54e4  lea     rdx, [rbp+string]
0x1800d54e8  mov     word ptr [rbp+var_38+1], ax
0x1800d54ec  mov     rcx, rsi
0x1800d54ef  movzx   eax, word ptr [rbp+arg_8+1]
0x1800d54f3  mov     word ptr [rbp+var_30+1], ax
0x1800d54f7  mov     al, byte ptr [rbp+arg_8+3]
0x1800d54fa  mov     byte ptr [rbp+var_30+3], al
0x1800d54fd  movzx   eax, word ptr [rbp+arg_8+1]
0x1800d5501  mov     word ptr [rbp+var_28+1], ax
0x1800d5505  mov     al, byte ptr [rbp+arg_8+3]
0x1800d5508  mov     byte ptr [rbp+var_28+3], al
0x1800d550b  mov     byte ptr [rbp+var_38], r14b
0x1800d550f  mov     byte ptr [rbp+var_38+3], r13b
0x1800d5513  mov     dword ptr [rbp+var_38+4], r14d
0x1800d5517  mov     rax, [rbp+var_38]
0x1800d551b  mov     byte ptr [rbp+var_30], r14b
0x1800d551f  mov     dword ptr [rbp+var_30+4], r14d
0x1800d5523  mov     r9, [rbp+var_30]
0x1800d5527  mov     byte ptr [rbp+var_28], r14b
0x1800d552b  mov     dword ptr [rbp+var_28+4], r14d
0x1800d552f  mov     r8, [rbp+var_28]
0x1800d5533  mov     qword ptr [rsp+80h+var_60], rax
0x1800d5538  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x1800d553d  mov     ebx, eax
0x1800d553f  test    eax, eax
0x1800d5541  js      short loc_1800D5555
0x1800d5543  mov     rcx, [rbp+string]; string
0x1800d5547  call    cs:__imp_WindowsDeleteString
0x1800d554d  inc     r15d
0x1800d5550  jmp     loc_1800D544A
0x1800d5555  mov     edx, 0F8Ah
0x1800d555a  jmp     loc_1800D57C1
0x1800d555f  mov     rcx, [rbp+string]; string
0x1800d5563  call    cs:__imp_WindowsDeleteString
0x1800d5569  lea     rcx, [rbp+var_18]
0x1800d556d  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800d5572  mov     rbx, r14
0x1800d5575  mov     [rbp+arg_8], rbx
0x1800d5579  cmp     [rsi+88h], r14d
0x1800d5580  jz      short loc_1800D5596
0x1800d5582  mov     rdx, [rsi+80h]
0x1800d5589  lea     rcx, [rbp+arg_8]
0x1800d558d  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800d5592  mov     rbx, [rbp+arg_8]
0x1800d5596  mov     r13b, [rbp+arg_20]
0x1800d559a  test    r13b, r13b
0x1800d559d  jz      loc_1800D565A
0x1800d55a3  mov     r14, [rsi+80h]
0x1800d55aa  mov     eax, [rsi+88h]
0x1800d55b0  shl     rax, 5
0x1800d55b4  add     rax, [rsi+80h]
0x1800d55bb  cmp     r14, rax
0x1800d55be  jz      short loc_1800D5606
0x1800d55c0  mov     rdx, [r14]
0x1800d55c3  lea     rax, [r14+8]
0x1800d55c7  mov     r9d, 1
0x1800d55cd  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800d55d2  xor     r8d, r8d
0x1800d55d5  mov     rcx, r12
0x1800d55d8  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800d55dd  mov     edi, eax
0x1800d55df  test    eax, eax
0x1800d55e1  js      short loc_1800D55E9
0x1800d55e3  add     r14, 20h ; ' '
0x1800d55e7  jmp     short loc_1800D55AA
0x1800d55e9  mov     rcx, [rbp+38h]; this
0x1800d55ed  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d55f4  mov     r9d, eax; char *
0x1800d55f7  mov     edx, 0FBAh; void *
0x1800d55fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d5601  jmp     loc_1800D56F4
0x1800d5606  mov     rdi, [rsi+80h]
0x1800d560d  mov     eax, [rsi+88h]
0x1800d5613  shl     rax, 5
0x1800d5617  add     rax, [rsi+80h]
0x1800d561e  cmp     rdi, rax
0x1800d5621  jz      short loc_1800D5657
0x1800d5623  mov     rdx, [rdi]
0x1800d5626  lea     rax, [rdi+18h]
0x1800d562a  mov     r9d, 2
0x1800d5630  mov     qword ptr [rsp+80h+var_60], rax
0x1800d5635  xor     r8d, r8d
0x1800d5638  mov     rcx, r12
0x1800d563b  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800d5640  mov     r14d, eax
0x1800d5643  test    eax, eax
0x1800d5645  js      short loc_1800D564D
0x1800d5647  add     rdi, 20h ; ' '
0x1800d564b  jmp     short loc_1800D560D
0x1800d564d  mov     edx, 0FC9h
0x1800d5652  jmp     loc_1800D56DE
0x1800d5657  xor     r14d, r14d
0x1800d565a  mov     rdi, [rsi+80h]
0x1800d5661  mov     ecx, [rsi+88h]
0x1800d5667  mov     eax, ecx
0x1800d5669  shl     rax, 5
0x1800d566d  add     rax, [rsi+80h]
0x1800d5674  cmp     rdi, rax
0x1800d5677  jz      loc_1800D570D
0x1800d567d  mov     rdx, [rdi]
0x1800d5680  lea     r15, [rdi+10h]
0x1800d5684  xor     r9d, r9d
0x1800d5687  mov     qword ptr [rsp+80h+var_60], r15; int
0x1800d568c  xor     r8d, r8d
0x1800d568f  mov     rcx, r12
0x1800d5692  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800d5697  mov     r14d, eax
0x1800d569a  test    eax, eax
0x1800d569c  js      short loc_1800D56D9
0x1800d569e  xor     r14d, r14d
0x1800d56a1  cmp     [rdi+8], r14b
0x1800d56a5  jz      short loc_1800D56B2
0x1800d56a7  cmp     [rdi+18h], r14b
0x1800d56ab  jz      short loc_1800D56B2
0x1800d56ad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d56b2  cmp     [r15], r14b
0x1800d56b5  jnz     short loc_1800D56D3
0x1800d56b7  cmp     [rdi+8], r14b
0x1800d56bb  jnz     short loc_1800D56D3
0x1800d56bd  cmp     [rdi+18h], r14b
0x1800d56c1  jnz     short loc_1800D56D3
0x1800d56c3  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x1800d56c6  mov     rcx, rsi; this
0x1800d56c9  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x1800d56ce  mov     rdi, rax
0x1800d56d1  jmp     short loc_1800D5661
0x1800d56d3  add     rdi, 20h ; ' '
0x1800d56d7  jmp     short loc_1800D5661
0x1800d56d9  mov     edx, 0FD4h; void *
0x1800d56de  mov     rcx, [rbp+38h]; this
0x1800d56e2  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d56e9  mov     r9d, r14d; char *
0x1800d56ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d56f1  mov     edi, r14d
0x1800d56f4  mov     rcx, rbx; string
0x1800d56f7  call    cs:__imp_WindowsDeleteString
0x1800d56fd  lea     rcx, [rbp+var_18]
0x1800d5701  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800d5706  mov     eax, edi
0x1800d5708  jmp     loc_1800D57ED
0x1800d570d  test    rbx, rbx
0x1800d5710  jz      loc_1800D57A5
0x1800d5716  test    ecx, ecx
0x1800d5718  jnz     loc_1800D57A5
0x1800d571e  xor     edx, edx
0x1800d5720  mov     [rbp+arg_8], r14
0x1800d5724  lea     rcx, [rbp+arg_8]
0x1800d5728  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800d572d  mov     rcx, [rbp+rguid]; rguid
0x1800d5731  lea     rdx, [rbp+arg_8]; string
0x1800d5735  call    ?GetIdString@@YAJAEBU_GUID@@PEAPEAUHSTRING__@@@Z; GetIdString(_GUID const &,HSTRING__ * *)
0x1800d573a  test    eax, eax
0x1800d573c  js      short loc_1800D579C
0x1800d573e  xor     edx, edx; length
0x1800d5740  mov     rcx, rbx; string
0x1800d5743  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5749  mov     rcx, [rbp+arg_8]; string
0x1800d574d  xor     edx, edx; length
0x1800d574f  mov     rdi, rax
0x1800d5752  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5758  mov     rcx, [rbp+38h]; this
0x1800d575c  mov     r9d, 8002801Dh; char *
0x1800d5762  mov     [rsp+80h+var_50], rdi
0x1800d5767  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d576e  mov     [rsp+80h+var_58], rax; char *
0x1800d5773  test    r13b, r13b
0x1800d5776  jz      short loc_1800D5786
0x1800d5778  lea     rax, aWarningPackage_0; "Warning: PackagedCom entry for %ls in p"...
0x1800d577f  mov     edx, 0FF6h
0x1800d5784  jmp     short loc_1800D5792
0x1800d5786  lea     rax, aWarningPackage; "Warning: PackagedCom entry for %ls in p"...
0x1800d578d  mov     edx, 0FFCh; void *
0x1800d5792  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800d5797  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800d579c  lea     rcx, [rbp+arg_8]
0x1800d57a0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800d57a5  mov     rcx, rbx; string
0x1800d57a8  call    cs:__imp_WindowsDeleteString
0x1800d57ae  lea     rcx, [rbp+var_18]
0x1800d57b2  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800d57b7  jmp     loc_1800D53EF
0x1800d57bc  mov     edx, 0F71h; void *
0x1800d57c1  mov     rcx, [rbp+38h]; this
0x1800d57c5  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d57cc  mov     r9d, ebx; char *
0x1800d57cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d57d4  mov     rcx, [rbp+string]; string
0x1800d57d8  call    cs:__imp_WindowsDeleteString
0x1800d57de  lea     rcx, [rbp+var_18]
0x1800d57e2  mov     [rbp+string], r14
0x1800d57e6  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800d57eb  mov     eax, ebx
0x1800d57ed  mov     rbx, [rsp+80h+arg_0]
0x1800d57f5  add     rsp, 80h
0x1800d57fc  pop     r15
0x1800d57fe  pop     r14
0x1800d5800  pop     r13
0x1800d5802  pop     r12
0x1800d5804  pop     rdi
0x1800d5805  pop     rsi
0x1800d5806  pop     rbp
0x1800d5807  retn
```
