# CPackagedComCatalog::GetTreatAsClassWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID *,HSTRING__ * *,ComRegistrationVisibility,bool *,ComRegistrationVisibility *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)

- ea: `0x18008d6f0`
- end: `0x18008dd31`
- name: `?GetTreatAsClassWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@3PEAU5@PEAPEAUHSTRING__@@W4ComRegistrationVisibility@@PEA_NPEAW47@PEBGIQEBQEAU6@IQEBQEAU6@@Z`
- size: `1601`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18008d028`
- `0x1800dfe40`

## callees

- `0x180005c40`
- `0x180016160`
- `0x180018344`
- `0x18002ba28`
- `0x180034540`
- `0x18007cbf8`
- `0x180081894`
- `0x18008d6f0`
- `0x18008e98c`
- `0x18008eff4`
- `0x18008f084`
- `0x18008f610`
- `0x180092e8c`
- `0x1800933b0`
- `0x180093538`
- `0x1800a1fd4`
- `0x1800b27e0`
- `0x1800d42f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008dbb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008dbb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d9b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008da3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008da5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008daa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008db7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dbbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dc45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dc51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dce6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d9b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008da3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008da5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008daa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008db7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dbbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dc45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dc51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dce6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008d7a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008d7a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d945`

## string_xrefs

- `0x18008db8f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008dc18`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008dd1f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008dc0c`: `CPackagedComCatalog::GetTreatAsClassWorker`
- `0x18008dc1f`: `While resolving CLSID %ws, exceeded maximum TreatAs hops %d`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetTreatAsClassWorker(
        struct IUserTokenInternal *a1,
        __int64 a2,
        HSTRING *a3,
        char a4,
        struct _GUID *a5,
        char a6,
        struct _GUID *a7,
        HSTRING *a8,
        int a9,
        char *a10,
        _DWORD *a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16)
{
  char v16; // r14
  HSTRING v18; // rbx
  int v19; // esi
  int v20; // r15d
  int v21; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int MainAndRelatedSetOptionalPackagesForMainPackage; // eax
  int v24; // ebx
  unsigned __int64 v25; // rbx
  const char *v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rcx
  CGuidStr *v29; // rax
  int v30; // edx
  int v31; // r8d
  int v32; // r9d
  int *v34; // [rsp+20h] [rbp-100h]
  char v36; // [rsp+A1h] [rbp-7Fh]
  HSTRING newString; // [rsp+A8h] [rbp-78h] BYREF
  int v38; // [rsp+B0h] [rbp-70h] BYREF
  int v39; // [rsp+B4h] [rbp-6Ch]
  __int64 v40; // [rsp+B8h] [rbp-68h]
  LPVOID lpMem; // [rsp+C0h] [rbp-60h] BYREF
  unsigned __int64 v42; // [rsp+C8h] [rbp-58h] BYREF
  void **v43; // [rsp+D0h] [rbp-50h] BYREF
  struct _GUID *v44; // [rsp+D8h] [rbp-48h]
  _QWORD v45[4]; // [rsp+E0h] [rbp-40h] BYREF
  void **v46; // [rsp+100h] [rbp-20h] BYREF
  struct _GUID *v47; // [rsp+108h] [rbp-18h]
  char *v48; // [rsp+110h] [rbp-10h]
  _DWORD *v49; // [rsp+118h] [rbp-8h]
  void **v50; // [rsp+120h] [rbp+0h]
  _QWORD *v51; // [rsp+128h] [rbp+8h]
  void ***v52; // [rsp+130h] [rbp+10h]
  struct _GUID *v53; // [rsp+138h] [rbp+18h]
  struct _GUID v54; // [rsp+140h] [rbp+20h] BYREF
  int v55[4]; // [rsp+150h] [rbp+30h] BYREF
  char v56; // [rsp+160h] [rbp+40h]
  HSTRING v57; // [rsp+168h] [rbp+48h]
  char v58; // [rsp+170h] [rbp+50h]
  __int128 v59; // [rsp+174h] [rbp+54h]
  __int16 v60; // [rsp+184h] [rbp+64h]
  char v61; // [rsp+188h] [rbp+68h]
  int v62; // [rsp+18Ch] [rbp+6Ch]
  char v63; // [rsp+190h] [rbp+70h]
  int v64; // [rsp+194h] [rbp+74h]
  char v65; // [rsp+198h] [rbp+78h]
  int v66; // [rsp+19Ch] [rbp+7Ch]
  HSTRING string; // [rsp+1A0h] [rbp+80h] BYREF
  _QWORD v68[2]; // [rsp+1A8h] [rbp+88h] BYREF
  __int128 v69[3]; // [rsp+1B8h] [rbp+98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+118h]

  v16 = 0;
  v47 = a7;
  v48 = a10;
  v49 = a11;
  v45[3] = a12;
  v45[2] = a14;
  v45[1] = a16;
  v40 = a2;
  v44 = a5;
  if ( a8 )
    *a8 = 0;
  v18 = *a3;
  WindowsDeleteString(0);
  newString = 0;
  WindowsDuplicateString(v18, &newString);
  v36 = 0;
  v19 = 0;
  v54 = *a5;
  v39 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    v19 = a9;
    v16 = a6;
    v39 = a9;
    v36 = a6;
  }
  v20 = 0;
  while ( 1 )
  {
    v56 = 0;
    v60 = 0;
    v59 = 0;
    v57 = 0;
    v58 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      WindowsDeleteString(newString);
      newString = 0;
      v45[0] = CPackagedComCatalog::AlwaysApplicable<ComProgIdRegistrationEntryProperties>;
      v38 = 0;
      v43 = &CPackagedComCatalog::EntryLookup::EntryType<ComTreatAsClassRegistrationEntryProperties>::`vftable';
      v46 = &CPackagedComCatalog::EntryLookup::RankingType<int>::`vftable';
      v50 = &CPackagedComCatalog::EntryLookup::CheckApplicabilityCallbackFromCheckIfApplicableCallback<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComInterfaceRegistrationEntryProperties const &,bool &)>::`vftable';
      v51 = v45;
      v52 = &v43;
      v53 = &v54;
      v34 = &v38;
      v21 = CPackagedComCatalog::EntryLookup::DoPackageAwareLookupWithCustomRanking(&v43, &v46, v55, &newString);
      v16 = v36;
      v19 = v39;
LABEL_20:
      v24 = v21;
      goto LABEL_21;
    }
    if ( !newString )
    {
      WindowsDeleteString(0);
      newString = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v28);
      v38 = 0;
      v21 = Z::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
              (int)v55,
              (int)&newString,
              (int)&v38,
              (int)a1,
              v40,
              (__int64)&v54,
              a6,
              0,
              (char)CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>);
      goto LABEL_20;
    }
    if ( !a4 )
    {
      PackageFilter::PackageFilter((PackageFilter *)&string, (const struct OpaqueString *)&newString);
      WindowsDeleteString(newString);
      newString = 0;
      v24 = CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
              (unsigned int)v55,
              (unsigned int)&newString,
              (_DWORD)a1,
              v40,
              (__int64)&v54,
              a6,
              (PackageFilter *)&string);
      PackageFilter::~PackageFilter((PackageFilter *)&string);
      goto LABEL_21;
    }
    lpMem = 0;
    v42 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(newString, 0);
    MainAndRelatedSetOptionalPackagesForMainPackage = GetMainAndRelatedSetOptionalPackagesForMainPackage(
                                                        a1,
                                                        StringRawBuffer,
                                                        &v42,
                                                        (struct PACKAGE_INFO **)&lpMem);
    v24 = MainAndRelatedSetOptionalPackagesForMainPackage;
    if ( MainAndRelatedSetOptionalPackagesForMainPackage < 0 )
      break;
    v25 = v42;
    v68[0] = lpMem;
    v68[1] = v42;
    v69[0] = 0;
    string = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && !v25 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        v26);
    }
    WindowsDeleteString(newString);
    newString = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v27);
    v38 = 0;
    v24 = Z::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
            (int)v55,
            (int)&newString,
            (int)&v38,
            (int)a1,
            v40,
            (__int64)&v54,
            a6,
            (PackageFilter *)&string,
            (char)CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>);
    wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(v69);
    wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(v68);
    WindowsDeleteString(string);
LABEL_21:
    if ( v24 < 0 )
    {
      WindowsDeleteString(v57);
      if ( v24 == -2147024894 )
      {
        if ( v20 <= 0 )
        {
          v24 = -2147221164;
        }
        else
        {
          v24 = 0;
          *v47 = v54;
        }
      }
      else if ( v24 == -2147024883 )
      {
        v24 = -2147221165;
      }
      goto LABEL_41;
    }
    ++v20;
    a4 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) != 0
       ? a4
       : 0;
    if ( v20 > 50 )
    {
      v24 = -2147221164;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        CGuidStr::CGuidStr((CGuidStr *)&string, v44);
        ComTraceMessage(
          0xFFFFFFFFLL,
          "onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          "CPackagedComCatalog::GetTreatAsClassWorker",
          7850);
      }
      WindowsDeleteString(v57);
LABEL_41:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
      {
        if ( v24 >= 0 )
        {
          if ( a8 )
          {
            *a8 = newString;
            newString = 0;
          }
          if ( v48 )
            *v48 = v16;
          if ( v49 )
            *v49 = v19;
        }
      }
      else if ( v24 >= 0 && a8 )
      {
        *a8 = newString;
        newString = 0;
      }
      goto LABEL_52;
    }
    if ( gfEnableTracing )
    {
      if ( (unsigned __int8)IsWppLevelEnabled(3) )
      {
        v29 = CGuidStr::CGuidStr((CGuidStr *)&string, &v54);
        ComTraceMessageT<_GUID const *,unsigned short *,_GUID *>(
          (unsigned int)v55,
          v30,
          v31,
          v32,
          (_DWORD)v34,
          (__int64)v44,
          (__int64)v29,
          (__int64)v55);
      }
    }
    v54 = *(struct _GUID *)v55;
    WindowsDeleteString(v57);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E7F,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)MainAndRelatedSetOptionalPackagesForMainPackage,
    (int)v34);
  if ( lpMem )
    HeapFree(g_hHeap, 0, lpMem);
  WindowsDeleteString(v57);
  v57 = 0;
LABEL_52:
  WindowsDeleteString(newString);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18008d6f0  mov     [rsp-8+arg_18], rbx
0x18008d6f5  push    rbp
0x18008d6f6  push    rsi
0x18008d6f7  push    rdi
0x18008d6f8  push    r12
0x18008d6fa  push    r13
0x18008d6fc  push    r14
0x18008d6fe  push    r15
0x18008d700  lea     rbp, [rsp-0E0h]
0x18008d708  sub     rsp, 200h
0x18008d70f  mov     rax, cs:__security_cookie
0x18008d716  xor     rax, rsp
0x18008d719  mov     [rbp+110h+var_40], rax
0x18008d720  mov     rax, [rbp+110h+arg_30]
0x18008d727  xor     r14d, r14d
0x18008d72a  mov     rdi, [rbp+110h+arg_38]
0x18008d731  mov     r13, rcx
0x18008d734  mov     rsi, [rbp+110h+arg_20]
0x18008d73b  mov     [rbp+110h+var_128], rax
0x18008d73f  mov     rax, [rbp+110h+arg_48]
0x18008d746  mov     [rbp+110h+var_120], rax
0x18008d74a  mov     rax, [rbp+110h+arg_50]
0x18008d751  mov     [rbp+110h+var_118], rax
0x18008d755  mov     rax, [rbp+110h+arg_58]
0x18008d75c  mov     [rbp+110h+var_138], rax
0x18008d760  mov     rax, [rbp+110h+arg_68]
0x18008d767  mov     [rbp+110h+var_140], rax
0x18008d76b  mov     rax, [rbp+110h+arg_78]
0x18008d772  mov     [rbp+110h+var_148], rax
0x18008d776  mov     [rbp+110h+var_190], r9b
0x18008d77a  mov     [rbp+110h+var_178], rdx
0x18008d77e  mov     [rbp+110h+var_158], rsi
0x18008d782  test    rdi, rdi
0x18008d785  jz      short loc_18008D78A
0x18008d787  mov     [rdi], r14
0x18008d78a  mov     rbx, [r8]
0x18008d78d  xor     ecx, ecx; string
0x18008d78f  mov     [rbp+110h+newString], r14
0x18008d793  call    cs:__imp_WindowsDeleteString
0x18008d799  lea     rdx, [rbp+110h+newString]; newString
0x18008d79d  mov     [rbp+110h+newString], r14
0x18008d7a1  mov     rcx, rbx; string
0x18008d7a4  call    cs:__imp_WindowsDuplicateString
0x18008d7aa  movups  xmm0, xmmword ptr [rsi]
0x18008d7ad  xor     ebx, ebx
0x18008d7af  mov     [rbp+110h+var_18F], bl
0x18008d7b2  mov     esi, ebx
0x18008d7b4  movdqu  xmmword ptr [rbp+110h+var_F0.Data1], xmm0
0x18008d7b9  mov     [rbp+110h+var_17C], ebx
0x18008d7bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008d7c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008d7c8  mov     r12b, [rbp+110h+arg_28]
0x18008d7cf  test    al, al
0x18008d7d1  jz      short loc_18008D7E3
0x18008d7d3  mov     esi, [rbp+110h+arg_40]
0x18008d7d9  mov     r14b, r12b
0x18008d7dc  mov     [rbp+110h+var_17C], esi
0x18008d7df  mov     [rbp+110h+var_18F], r12b
0x18008d7e3  mov     r15d, ebx
0x18008d7e6  xor     eax, eax
0x18008d7e8  mov     [rbp+110h+var_D0], bl
0x18008d7eb  xorps   xmm0, xmm0
0x18008d7ee  mov     [rbp+110h+var_AC], ax
0x18008d7f2  movups  [rbp+110h+var_BC], xmm0
0x18008d7f6  mov     [rbp+110h+var_C8], rbx
0x18008d7fa  mov     [rbp+110h+var_C0], bl
0x18008d7fd  mov     [rbp+110h+var_A8], bl
0x18008d800  mov     [rbp+110h+var_A4], ebx
0x18008d803  mov     [rbp+110h+var_A0], bl
0x18008d806  mov     [rbp+110h+var_9C], ebx
0x18008d809  mov     [rbp+110h+var_98], bl
0x18008d80c  mov     [rbp+110h+var_94], ebx
0x18008d80f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008d816  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008d81b  mov     rcx, [rbp+110h+newString]; string
0x18008d81f  test    al, al
0x18008d821  jz      loc_18008D928
0x18008d827  call    cs:__imp_WindowsDeleteString
0x18008d82d  lea     rax, ??$AlwaysApplicable@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBUComProgIdRegistrationEntryProperties@@AEA_N@Z; CPackagedComCatalog::AlwaysApplicable<ComProgIdRegistrationEntryProperties>(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &)
0x18008d834  mov     [rbp+110h+newString], rbx
0x18008d838  mov     [rbp+110h+var_150], rax
0x18008d83c  lea     r9, [rbp+110h+newString]
0x18008d840  lea     rax, ??_7?$EntryType@UComTreatAsClassRegistrationEntryProperties@@@EntryLookup@CPackagedComCatalog@@6B@; const CPackagedComCatalog::EntryLookup::EntryType<ComTreatAsClassRegistrationEntryProperties>::`vftable'
0x18008d847  mov     [rbp+110h+var_180], ebx
0x18008d84a  mov     [rbp+110h+var_160], rax
0x18008d84e  lea     r8, [rbp+110h+var_E0]
0x18008d852  lea     rax, ??_7?$RankingType@H@EntryLookup@CPackagedComCatalog@@6B@; const CPackagedComCatalog::EntryLookup::RankingType<int>::`vftable'
0x18008d859  mov     [rbp+110h+var_130], rax
0x18008d85d  lea     rdx, [rbp+110h+var_130]
0x18008d861  lea     rax, ??_7?$CheckApplicabilityCallbackFromCheckIfApplicableCallback@UComInterfaceRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@6B@; const CPackagedComCatalog::EntryLookup::CheckApplicabilityCallbackFromCheckIfApplicableCallback<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComInterfaceRegistrationEntryProperties const &,bool &)>::`vftable'
0x18008d868  mov     [rbp+110h+var_110], rax
0x18008d86c  lea     rcx, [rbp+110h+var_160]
0x18008d870  lea     rax, [rbp+110h+var_150]
0x18008d874  mov     [rbp+110h+var_108], rax
0x18008d878  lea     rax, [rbp+110h+var_160]
0x18008d87c  mov     [rbp+110h+var_100], rax
0x18008d880  lea     rax, [rbp+110h+var_F0]
0x18008d884  mov     [rbp+110h+var_F8], rax
0x18008d888  mov     rax, [rbp+110h+var_148]
0x18008d88c  mov     [rsp+230h+var_198], rax
0x18008d894  mov     eax, [rbp+110h+arg_70]
0x18008d89a  mov     [rsp+230h+var_1A0], eax
0x18008d8a1  mov     rax, [rbp+110h+var_140]
0x18008d8a5  mov     [rsp+230h+var_1A8], rax
0x18008d8ad  mov     eax, [rbp+110h+arg_60]
0x18008d8b3  mov     [rsp+230h+var_1B0], eax
0x18008d8ba  mov     rax, [rbp+110h+var_138]
0x18008d8be  mov     [rsp+230h+var_1B8], rax
0x18008d8c3  lea     rax, [rbp+110h+var_110]
0x18008d8c7  mov     [rsp+230h+var_1C0], rax
0x18008d8cc  mov     al, [rbp+110h+var_190]
0x18008d8cf  mov     [rsp+230h+var_1C8], esi
0x18008d8d3  mov     [rsp+230h+var_1D0], r14b
0x18008d8d8  mov     [rsp+230h+var_1D8], al
0x18008d8dc  lea     rax, [rbp+110h+newString]
0x18008d8e0  mov     [rsp+230h+var_1E0], rax
0x18008d8e5  lea     rax, [rbp+110h+var_100]
0x18008d8e9  mov     [rsp+230h+var_1E8], rax
0x18008d8ee  mov     rax, [rbp+110h+var_178]
0x18008d8f2  mov     qword ptr [rsp+230h+var_1F0], rax
0x18008d8f7  lea     rax, [rbp+110h+var_17C]
0x18008d8fb  mov     [rsp+230h+var_1F8], r13
0x18008d900  mov     qword ptr [rsp+230h+var_200], rax
0x18008d905  lea     rax, [rbp+110h+var_18F]
0x18008d909  mov     [rsp+230h+var_208], rax
0x18008d90e  lea     rax, [rbp+110h+var_180]
0x18008d912  mov     [rsp+230h+var_210], rax
0x18008d917  call    ?DoPackageAwareLookupWithCustomRanking@EntryLookup@CPackagedComCatalog@@CAJAEAUIEntryTypeGeneric@12@AEAUIRankingTypeGeneric@12@UEntryPropertiesPointerGeneric@12@PEAPEAUHSTRING__@@URankingPointerGeneric@12@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@UEntryIdGeneric@12@AEBVOpaqueString@@_N_NW48@AEAUICheckApplicabilityCallbackGeneric@12@PEBGIQEBQEAU6@IQEBQEAU6@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookupWithCustomRanking(CPackagedComCatalog::EntryLookup::IEntryTypeGeneric &,CPackagedComCatalog::EntryLookup::IRankingTypeGeneric &,CPackagedComCatalog::EntryLookup::EntryPropertiesPointerGeneric,HSTRING__ * *,CPackagedComCatalog::EntryLookup::RankingPointerGeneric,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,CPackagedComCatalog::EntryLookup::EntryIdGeneric,OpaqueString const &,bool,bool,ComRegistrationVisibility,CPackagedComCatalog::EntryLookup::ICheckApplicabilityCallbackGeneric &,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x18008d91c  mov     r14b, [rbp+110h+var_18F]
0x18008d920  mov     esi, [rbp+110h+var_17C]
0x18008d923  jmp     loc_18008DB04
0x18008d928  test    rcx, rcx
0x18008d92b  jz      loc_18008DAA6
0x18008d931  cmp     [rbp+110h+var_190], 0
0x18008d935  jz      loc_18008DA4A
0x18008d93b  xor     edx, edx; length
0x18008d93d  mov     [rbp+110h+lpMem], rbx
0x18008d941  mov     [rbp+110h+var_168], rbx
0x18008d945  call    cs:__imp_WindowsGetStringRawBuffer
0x18008d94b  lea     r9, [rbp+110h+lpMem]; struct PACKAGE_INFO **
0x18008d94f  mov     rcx, r13; struct IUserTokenInternal *
0x18008d952  mov     rdx, rax; unsigned __int16 *
0x18008d955  lea     r8, [rbp+110h+var_168]; unsigned __int64 *
0x18008d959  call    ?GetMainAndRelatedSetOptionalPackagesForMainPackage@@YAJPEAUIUserTokenInternal@@PEBGPEA_KPEAPEAUPACKAGE_INFO@@@Z; GetMainAndRelatedSetOptionalPackagesForMainPackage(IUserTokenInternal *,ushort const *,unsigned __int64 *,PACKAGE_INFO * *)
0x18008d95e  mov     ebx, eax
0x18008d960  test    eax, eax
0x18008d962  js      loc_18008DB88
0x18008d968  mov     rax, [rbp+110h+lpMem]
0x18008d96c  xorps   xmm0, xmm0
0x18008d96f  mov     rbx, [rbp+110h+var_168]
0x18008d973  mov     [rbp+110h+var_88], rax
0x18008d97a  mov     [rbp+110h+var_80], rbx
0x18008d981  movdqu  [rbp+110h+var_78], xmm0
0x18008d989  mov     [rbp+110h+string], 0
0x18008d994  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008d99b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008d9a0  test    al, al
0x18008d9a2  jnz     short loc_18008D9AD
0x18008d9a4  test    rbx, rbx
0x18008d9a7  jz      loc_18008DD18
0x18008d9ad  mov     rcx, [rbp+110h+newString]; string
0x18008d9b1  call    cs:__imp_WindowsDeleteString
0x18008d9b7  mov     [rbp+110h+newString], 0
0x18008d9bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008d9c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008d9cb  test    al, al
0x18008d9cd  jz      short loc_18008D9D4
0x18008d9cf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008d9d4  lea     rax, ??$AlwaysApplicableOld@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComProgIdRegistrationEntryProperties@@PEA_N@Z; CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)
0x18008d9db  mov     [rbp+110h+var_180], 0
0x18008d9e2  mov     qword ptr [rsp+230h+var_1F0], rax; char
0x18008d9e7  lea     r8, [rbp+110h+var_180]; int
0x18008d9eb  lea     rax, [rbp+110h+string]
0x18008d9f2  mov     r9, r13; int
0x18008d9f5  mov     [rsp+230h+var_1F8], rax; PackageFilter *
0x18008d9fa  lea     rdx, [rbp+110h+newString]; int
0x18008d9fe  lea     rax, [rbp+110h+var_F0]
0x18008da02  mov     [rsp+230h+var_200], r12b; char
0x18008da07  mov     [rsp+230h+var_208], rax; __int64
0x18008da0c  lea     rcx, [rbp+110h+var_E0]; int
0x18008da10  mov     rax, [rbp+110h+var_178]
0x18008da14  mov     [rsp+230h+var_210], rax; __int64
0x18008da19  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComTreatAsClassRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)
0x18008da1e  lea     rcx, [rbp+110h+var_78]
0x18008da25  mov     ebx, eax
0x18008da27  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x18008da2c  lea     rcx, [rbp+110h+var_88]
0x18008da33  call    ?reset@?$unique_any_array_ptr@UPACKAGE_INFO@@UPrivMemDeleter@@Uempty_deleter@wil@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(void)
0x18008da38  mov     rcx, [rbp+110h+string]; string
0x18008da3f  call    cs:__imp_WindowsDeleteString
0x18008da45  jmp     loc_18008DB06
0x18008da4a  lea     rdx, [rbp+110h+newString]; struct OpaqueString *
0x18008da4e  lea     rcx, [rbp+110h+string]; this
0x18008da55  call    ??0PackageFilter@@QEAA@AEBVOpaqueString@@@Z; PackageFilter::PackageFilter(OpaqueString const &)
0x18008da5a  mov     rcx, [rbp+110h+newString]; string
0x18008da5e  call    cs:__imp_WindowsDeleteString
0x18008da64  mov     r9, [rbp+110h+var_178]
0x18008da68  lea     rax, [rbp+110h+string]
0x18008da6f  mov     qword ptr [rsp+230h+var_200], rax
0x18008da74  lea     rdx, [rbp+110h+newString]
0x18008da78  lea     rax, [rbp+110h+var_F0]
0x18008da7c  mov     byte ptr [rsp+230h+var_208], r12b
0x18008da81  mov     r8, r13
0x18008da84  mov     [rsp+230h+var_210], rax
0x18008da89  lea     rcx, [rbp+110h+var_E0]
0x18008da8d  mov     [rbp+110h+newString], rbx
0x18008da91  call    ??$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))
0x18008da96  lea     rcx, [rbp+110h+string]; this
0x18008da9d  mov     ebx, eax
0x18008da9f  call    ??1PackageFilter@@QEAA@XZ; PackageFilter::~PackageFilter(void)
0x18008daa4  jmp     short loc_18008DB06
0x18008daa6  call    cs:__imp_WindowsDeleteString
0x18008daac  mov     [rbp+110h+newString], rbx
0x18008dab0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008dab7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008dabc  test    al, al
0x18008dabe  jz      short loc_18008DAC5
0x18008dac0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008dac5  lea     rax, ??$AlwaysApplicableOld@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComProgIdRegistrationEntryProperties@@PEA_N@Z; CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)
0x18008dacc  mov     [rbp+110h+var_180], ebx
0x18008dacf  mov     qword ptr [rsp+230h+var_1F0], rax; char
0x18008dad4  lea     r8, [rbp+110h+var_180]; int
0x18008dad8  mov     [rsp+230h+var_1F8], rbx; PackageFilter *
0x18008dadd  lea     rax, [rbp+110h+var_F0]
0x18008dae1  mov     [rsp+230h+var_200], r12b; char
0x18008dae6  lea     rdx, [rbp+110h+newString]; int
0x18008daea  mov     [rsp+230h+var_208], rax; __int64
0x18008daef  lea     rcx, [rbp+110h+var_E0]; int
0x18008daf3  mov     rax, [rbp+110h+var_178]
0x18008daf7  mov     r9, r13; int
0x18008dafa  mov     [rsp+230h+var_210], rax; __int64
0x18008daff  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComTreatAsClassRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)
0x18008db04  mov     ebx, eax
0x18008db06  test    ebx, ebx
0x18008db08  js      loc_18008DC4D
0x18008db0e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008db15  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008db1a  neg     al
0x18008db1c  sbb     cl, cl
0x18008db1e  inc     r15d
0x18008db21  and     [rbp+110h+var_190], cl
0x18008db24  cmp     r15d, 32h ; '2'
0x18008db28  jg      loc_18008DBD2
0x18008db2e  xor     ebx, ebx
0x18008db30  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18008db36  jz      short loc_18008DB70
0x18008db38  lea     ecx, [rbx+3]
0x18008db3b  call    IsWppLevelEnabled
0x18008db40  test    al, al
0x18008db42  jz      short loc_18008DB70
0x18008db44  lea     rdx, [rbp+110h+var_F0]; struct _GUID *
0x18008db48  lea     rcx, [rbp+110h+string]; this
0x18008db4f  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18008db54  lea     rcx, [rbp+110h+var_E0]
0x18008db58  mov     [rsp+230h+var_1F8], rcx
0x18008db5d  mov     qword ptr [rsp+230h+var_200], rax
0x18008db62  mov     rax, [rbp+110h+var_158]
0x18008db66  mov     [rsp+230h+var_208], rax
0x18008db6b  call    ??$ComTraceMessageT@PEBU_GUID@@PEAGPEAU1@@@YAXPEBD0HW4TraceLevel@@PEBGPEBU_GUID@@PEAGPEAU1@@Z; ComTraceMessageT<_GUID const *,ushort *,_GUID *>(char const *,char const *,int,TraceLevel,ushort const *,_GUID const *,ushort *,_GUID *)
0x18008db70  movaps  xmm0, xmmword ptr [rbp+110h+var_E0]
0x18008db74  mov     rcx, [rbp+110h+var_C8]; string
0x18008db78  movdqu  xmmword ptr [rbp+110h+var_F0.Data1], xmm0
0x18008db7d  call    cs:__imp_WindowsDeleteString
0x18008db83  jmp     loc_18008D7E6
0x18008db88  mov     rcx, [rbp+118h]; this
0x18008db8f  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008db96  mov     r9d, eax; char *
0x18008db99  mov     edx, 1E7Fh; void *
0x18008db9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dba3  mov     r8, [rbp+110h+lpMem]; lpMem
0x18008dba7  test    r8, r8
0x18008dbaa  jz      short loc_18008DBBB
0x18008dbac  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18008dbb3  xor     edx, edx; dwFlags
0x18008dbb5  call    cs:__imp_HeapFree
0x18008dbbb  mov     rcx, [rbp+110h+var_C8]; string
0x18008dbbf  call    cs:__imp_WindowsDeleteString
0x18008dbc5  mov     [rbp+110h+var_C8], 0
0x18008dbcd  jmp     loc_18008DCE2
0x18008dbd2  mov     eax, cs:dword_18014E4B8
0x18008dbd8  mov     ebx, 80040154h
0x18008dbdd  test    eax, eax
0x18008dbdf  jnz     short loc_18008DBF4
0x18008dbe1  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18008dbe7  jz      short loc_18008DC41
0x18008dbe9  xor     ecx, ecx
0x18008dbeb  call    IsWppLevelEnabled
0x18008dbf0  test    al, al
0x18008dbf2  jz      short loc_18008DC41
0x18008dbf4  mov     rdx, [rbp+110h+var_158]; struct _GUID *
0x18008dbf8  lea     rcx, [rbp+110h+string]; this
0x18008dbff  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18008dc04  mov     dword ptr [rsp+230h+var_1F8], 32h ; '2'
0x18008dc0c  lea     r8, aCpackagedcomca_10; "CPackagedComCatalog::GetTreatAsClassWor"...
0x18008dc13  mov     qword ptr [rsp+230h+var_200], rax
0x18008dc18  lea     rdx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008dc1f  lea     rax, aWhileResolving_2; "While resolving CLSID %ws, exceeded max"...
0x18008dc26  mov     r9d, 1EAAh
0x18008dc2c  mov     [rsp+230h+var_208], rax
0x18008dc31  or      ecx, 0FFFFFFFFh
  ... truncated ...
```
