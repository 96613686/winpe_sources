# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTreatAsClassRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)

- ea: `0x18006da34`
- end: `0x18006df2f`
- name: `??$GetInstalledPackagesContainingEntry@UComTreatAsClassRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z`
- size: `1275`
- prototype: `__int64 __usercall@<rax>(PackageListBuffer *this@<rcx>, char, PackageFilter *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008f084`
- `0x1800de220`

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
- `0x18006da34`
- `0x18006df38`
- `0x18008e98c`
- `0x1800a167c`
- `0x1800d9a18`
- `0x1800d9a30`
- `0x1800dd864`
- `0x1800de7e4`
- `0x1800de834`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dae4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006db62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dbd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dbf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dc9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006de2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dedf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006df06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dae4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006db62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dbd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dbf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dc9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006de2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dedf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006df06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006db44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006de79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006de88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006db44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006de79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006de88`

## string_xrefs

- `0x18006daae`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18006dc70`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18006dcf4`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18006de1a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18006de8e`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18006def3`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18006deaf`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x18006debd`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTreatAsClassRegistrationEntryProperties>(
        PackageListBuffer *this,
        struct IUserToken *a2,
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
  __int64 i; // r15
  int ComPackageInstallOrder; // eax
  __int64 j; // rdi
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
  int v35; // [rsp+20h] [rbp-69h]
  char *v36; // [rsp+28h] [rbp-61h]
  _BYTE v37[8]; // [rsp+40h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v39; // [rsp+50h] [rbp-39h] BYREF
  __int64 v40; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v41; // [rsp+60h] [rbp-29h]
  int v42; // [rsp+64h] [rbp-25h]
  unsigned int v43; // [rsp+68h] [rbp-21h]
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
  v11 =  IPackagedComCatalogContext::`vcall'{352,{flat}}(a3, a4, &v40);
  v12 = 0;
  v13 = v11;
  if ( v11 >= 0 )
  {
    v45[0] = a3;
    v45[1] = &v40;
    v14 = 0;
    v46 = 1;
    while ( 1 )
    {
      v37[0] = 0;
      string = 0;
      WindowsDeleteString(0);
      p_string = &string;
      string = 0;
      v13 =  IPackagedComCatalogContext::`vcall'{360,{flat}}(a3, v40, v14, v37);
      if ( v13 < 0 )
      {
        v17 = 3953;
        goto LABEL_66;
      }
      if ( !v37[0] )
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
      v13 = PackageListBuffer::AddPackage(
              (__int64)this,
              &string,
              (HSTRING)(unsigned int)v39,
              (HSTRING)v43,
              (HSTRING)v41);
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
        wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v45);
        return (unsigned int)v13;
      }
      WindowsDeleteString(string);
LABEL_18:
      ++v14;
    }
    WindowsDeleteString(string);
    v18 = *a3;
    v46 = 0;
    (*(void (__fastcall **)(__int64 *, __int64))(v18 + 32))(a3, v40);
    v19 = 0;
    v40 = 0;
    v39 = 0;
    if ( *((_DWORD *)this + 34) )
    {
      OpaqueString::operator=(&v39, *((_QWORD *)this + 16));
      v19 = v39;
    }
    if ( a5 )
    {
      LODWORD(string) = 0;
      if ( a2 )
      {
        v20 = (*(__int64 (__fastcall **)(struct IUserToken *, __int64, HSTRING *))(*(_QWORD *)a2 + 96LL))(
                a2,
                1,
                &string);
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
            (*(void (__fastcall **)(struct IUserToken *))(*(_QWORD *)a2 + 104LL))(a2);
          WindowsDeleteString(v19);
          return v21;
        }
      }
      for ( i = *((_QWORD *)this + 16); i != *((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34); i += 32 )
      {
        ComPackageInstallOrder = CPackagedComCatalog::TryGetComPackageInstallOrder(
                                   (__int64)a3,
                                   *(HSTRING *)i,
                                   a2,
                                   1u,
                                   (_BYTE *)(i + 8));
        v21 = ComPackageInstallOrder;
        if ( ComPackageInstallOrder < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFBA,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)ComPackageInstallOrder,
            v34);
          if ( (_DWORD)string )
            (*(void (__fastcall **)(struct IUserToken *))(*(_QWORD *)a2 + 104LL))(a2);
LABEL_55:
          WindowsDeleteString(v19);
          wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v45);
          return v21;
        }
      }
      if ( (_DWORD)string )
        (*(void (__fastcall **)(struct IUserToken *))(*(_QWORD *)a2 + 104LL))(a2);
      for ( j = *((_QWORD *)this + 16); j != *((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34); j += 32 )
      {
        v25 = CPackagedComCatalog::TryGetComPackageInstallOrder((__int64)a3, *(HSTRING *)j, a2, 2u, (_BYTE *)(j + 24));
        if ( v25 < 0 )
        {
          v26 = 4041;
LABEL_54:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v26,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v25,
            v35);
          v21 = v25;
          goto LABEL_55;
        }
      }
    }
    v27 = (struct PackageIdAndInstallOrders *)*((_QWORD *)this + 16);
    while ( v27 != (struct PackageIdAndInstallOrders *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34)) )
    {
      v25 = CPackagedComCatalog::TryGetComPackageInstallOrder((__int64)a3, *(HSTRING *)v27, a2, 0, (_BYTE *)v27 + 16);
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
        v36 = (char *)WindowsGetStringRawBuffer(string, 0);
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
          v36,
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
0x18006da34  mov     [rsp-8+rguid], r9
0x18006da39  push    rbp
0x18006da3a  push    rbx
0x18006da3b  push    rsi
0x18006da3c  push    rdi
0x18006da3d  push    r12
0x18006da3f  push    r13
0x18006da41  push    r14
0x18006da43  push    r15
0x18006da45  lea     rbp, [rsp-0Fh]
0x18006da4a  sub     rsp, 98h
0x18006da51  mov     r15, r9
0x18006da54  mov     r12, r8
0x18006da57  mov     r14, rdx
0x18006da5a  mov     rsi, rcx
0x18006da5d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18006da64  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18006da69  mov     rdi, [rbp+47h+arg_28]
0x18006da6d  test    al, al
0x18006da6f  jz      short loc_18006DA8A
0x18006da71  test    rdi, rdi
0x18006da74  jz      short loc_18006DA8A
0x18006da76  mov     rcx, rdi; this
0x18006da79  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x18006da7e  test    rax, rax
0x18006da81  jnz     short loc_18006DA8A
0x18006da83  xor     eax, eax
0x18006da85  jmp     loc_18006DF1B
0x18006da8a  lea     r8, [rbp+47h+var_78]
0x18006da8e  mov     [rbp+47h+var_78], 0
0x18006da96  mov     rdx, r15
0x18006da99  mov     rcx, r12
0x18006da9c  call    ??_9IPackagedComCatalogContext@@$BBGA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{352,{flat}}
0x18006daa1  xor     r15d, r15d
0x18006daa4  mov     ebx, eax
0x18006daa6  test    eax, eax
0x18006daa8  jns     short loc_18006DAC7
0x18006daaa  mov     rcx, [rbp+4Fh]; this
0x18006daae  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18006dab5  mov     r9d, eax; char *
0x18006dab8  mov     edx, 0F65h; void *
0x18006dabd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006dac2  jmp     loc_18006DF19
0x18006dac7  lea     rax, [rbp+47h+var_78]
0x18006dacb  mov     [rbp+47h+var_60], r12
0x18006dacf  mov     [rbp+47h+var_58], rax
0x18006dad3  mov     r13d, r15d
0x18006dad6  mov     [rbp+47h+var_50], 1
0x18006dada  xor     ecx, ecx; string
0x18006dadc  mov     [rbp+47h+var_90], r15b
0x18006dae0  mov     [rbp+47h+string], r15
0x18006dae4  call    cs:__imp_WindowsDeleteString
0x18006daea  mov     rdx, [rbp+47h+var_78]
0x18006daee  lea     rax, [rbp+47h+string]
0x18006daf2  lea     r9, [rbp+47h+var_90]
0x18006daf6  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18006dafb  mov     r8d, r13d
0x18006dafe  mov     [rbp+47h+string], r15
0x18006db02  mov     rcx, r12
0x18006db05  call    ??_9IPackagedComCatalogContext@@$BBGI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{360,{flat}}
0x18006db0a  mov     ebx, eax
0x18006db0c  test    eax, eax
0x18006db0e  js      loc_18006DEEA
0x18006db14  cmp     [rbp+47h+var_90], r15b
0x18006db18  jz      loc_18006DBF1
0x18006db1e  test    rdi, rdi
0x18006db21  jz      short loc_18006DB70
0x18006db23  mov     rcx, rdi; this
0x18006db26  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x18006db2b  cmp     r15, rax
0x18006db2e  jnb     short loc_18006DB5E
0x18006db30  mov     rdx, r15; unsigned __int64
0x18006db33  mov     rcx, rdi; this
0x18006db36  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x18006db3b  mov     rcx, [rbp+47h+string]; string
0x18006db3f  xor     edx, edx; length
0x18006db41  mov     rbx, rax
0x18006db44  call    cs:__imp_WindowsGetStringRawBuffer
0x18006db4a  mov     rcx, rax; unsigned __int16 *
0x18006db4d  mov     rdx, rbx; unsigned __int16 *
0x18006db50  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x18006db55  test    al, al
0x18006db57  jnz     short loc_18006DB6D
0x18006db59  inc     r15
0x18006db5c  jmp     short loc_18006DB23
0x18006db5e  mov     rcx, [rbp+47h+string]; string
0x18006db62  call    cs:__imp_WindowsDeleteString
0x18006db68  xor     r15d, r15d
0x18006db6b  jmp     short loc_18006DBDF
0x18006db6d  xor     r15d, r15d
0x18006db70  movzx   eax, word ptr [rbp+47h+var_80+1]
0x18006db74  lea     rdx, [rbp+47h+string]
0x18006db78  mov     word ptr [rbp+47h+var_70+1], ax
0x18006db7c  mov     rcx, rsi
0x18006db7f  mov     al, byte ptr [rbp+47h+var_80+3]
0x18006db82  mov     byte ptr [rbp+47h+var_70+3], al
0x18006db85  movzx   eax, word ptr [rbp+47h+var_80+1]
0x18006db89  mov     word ptr [rbp+47h+var_68+1], ax
0x18006db8d  mov     al, byte ptr [rbp+47h+var_80+3]
0x18006db90  mov     byte ptr [rbp+47h+var_68+3], al
0x18006db93  movzx   eax, word ptr [rbp+47h+var_80+1]
0x18006db97  mov     word ptr [rbp+47h+var_80+1], ax
0x18006db9b  mov     al, byte ptr [rbp+47h+var_80+3]
0x18006db9e  mov     byte ptr [rbp+47h+var_80+3], al
0x18006dba1  mov     byte ptr [rbp+47h+var_70], r15b
0x18006dba5  mov     dword ptr [rbp+47h+var_70+4], r15d
0x18006dba9  mov     rax, [rbp+47h+var_70]
0x18006dbad  mov     byte ptr [rbp+47h+var_68], r15b
0x18006dbb1  mov     dword ptr [rbp+47h+var_68+4], r15d
0x18006dbb5  mov     r9, [rbp+47h+var_68]
0x18006dbb9  mov     byte ptr [rbp+47h+var_80], r15b
0x18006dbbd  mov     dword ptr [rbp+47h+var_80+4], r15d
0x18006dbc1  mov     r8, [rbp+47h+var_80]
0x18006dbc5  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18006dbca  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x18006dbcf  mov     ebx, eax
0x18006dbd1  test    eax, eax
0x18006dbd3  js      short loc_18006DBE7
0x18006dbd5  mov     rcx, [rbp+47h+string]; string
0x18006dbd9  call    cs:__imp_WindowsDeleteString
0x18006dbdf  inc     r13d
0x18006dbe2  jmp     loc_18006DADA
0x18006dbe7  mov     edx, 0F8Ah
0x18006dbec  jmp     loc_18006DEEF
0x18006dbf1  mov     rcx, [rbp+47h+string]; string
0x18006dbf5  call    cs:__imp_WindowsDeleteString
0x18006dbfb  mov     rax, [r12]
0x18006dbff  mov     rcx, r12
0x18006dc02  mov     rdx, [rbp+47h+var_78]
0x18006dc06  mov     [rbp+47h+var_50], r15b
0x18006dc0a  mov     rax, [rax+20h]
0x18006dc0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc13  mov     rbx, r15
0x18006dc16  mov     [rbp+47h+var_78], r15
0x18006dc1a  mov     [rbp+47h+var_80], rbx
0x18006dc1e  cmp     [rsi+88h], r15d
0x18006dc25  jz      short loc_18006DC3B
0x18006dc27  mov     rdx, [rsi+80h]
0x18006dc2e  lea     rcx, [rbp+47h+var_80]
0x18006dc32  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x18006dc37  mov     rbx, [rbp+47h+var_80]
0x18006dc3b  cmp     [rbp+47h+arg_20], r15b
0x18006dc3f  jz      loc_18006DD91
0x18006dc45  mov     dword ptr [rbp+47h+string], r15d
0x18006dc49  test    r14, r14
0x18006dc4c  jz      short loc_18006DCAA
0x18006dc4e  mov     rax, [r14]
0x18006dc51  lea     r8, [rbp+47h+string]
0x18006dc55  mov     edx, 1
0x18006dc5a  mov     rcx, r14
0x18006dc5d  mov     rax, [rax+60h]
0x18006dc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc66  mov     edi, eax
0x18006dc68  test    eax, eax
0x18006dc6a  jns     short loc_18006DCAA
0x18006dc6c  mov     rcx, [rbp+4Fh]; this
0x18006dc70  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18006dc77  mov     r9d, eax; char *
0x18006dc7a  mov     edx, 0FB4h; void *
0x18006dc7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006dc84  mov     edx, dword ptr [rbp+47h+string]
0x18006dc87  test    edx, edx
0x18006dc89  jz      short loc_18006DC9A
0x18006dc8b  mov     rcx, [r14]
0x18006dc8e  mov     rax, [rcx+68h]
0x18006dc92  mov     rcx, r14
0x18006dc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc9a  mov     rcx, rbx; string
0x18006dc9d  call    cs:__imp_WindowsDeleteString
0x18006dca3  mov     eax, edi
0x18006dca5  jmp     loc_18006DF1B
0x18006dcaa  mov     r15, [rsi+80h]
0x18006dcb1  mov     eax, [rsi+88h]
0x18006dcb7  shl     rax, 5
0x18006dcbb  add     rax, [rsi+80h]
0x18006dcc2  cmp     r15, rax
0x18006dcc5  jz      short loc_18006DD27
0x18006dcc7  mov     rdx, [r15]
0x18006dcca  lea     rax, [r15+8]
0x18006dcce  mov     r9d, 1
0x18006dcd4  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18006dcd9  mov     r8, r14
0x18006dcdc  mov     rcx, r12
0x18006dcdf  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x18006dce4  mov     edi, eax
0x18006dce6  test    eax, eax
0x18006dce8  js      short loc_18006DCF0
0x18006dcea  add     r15, 20h ; ' '
0x18006dcee  jmp     short loc_18006DCB1
0x18006dcf0  mov     rcx, [rbp+4Fh]; this
0x18006dcf4  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18006dcfb  mov     r9d, eax; char *
0x18006dcfe  mov     edx, 0FBAh; void *
0x18006dd03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006dd08  mov     edx, dword ptr [rbp+47h+string]
0x18006dd0b  test    edx, edx
0x18006dd0d  jz      loc_18006DE2C
0x18006dd13  mov     rax, [r14]
0x18006dd16  mov     rcx, r14
0x18006dd19  mov     rax, [rax+68h]
0x18006dd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd22  jmp     loc_18006DE2C
0x18006dd27  mov     edx, dword ptr [rbp+47h+string]
0x18006dd2a  test    edx, edx
0x18006dd2c  jz      short loc_18006DD3D
0x18006dd2e  mov     rax, [r14]
0x18006dd31  mov     rcx, r14
0x18006dd34  mov     rax, [rax+68h]
0x18006dd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd3d  mov     rdi, [rsi+80h]
0x18006dd44  mov     eax, [rsi+88h]
0x18006dd4a  shl     rax, 5
0x18006dd4e  add     rax, [rsi+80h]
0x18006dd55  cmp     rdi, rax
0x18006dd58  jz      short loc_18006DD8E
0x18006dd5a  mov     rdx, [rdi]
0x18006dd5d  lea     rax, [rdi+18h]
0x18006dd61  mov     r9d, 2
0x18006dd67  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18006dd6c  mov     r8, r14
0x18006dd6f  mov     rcx, r12
0x18006dd72  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x18006dd77  mov     r15d, eax
0x18006dd7a  test    eax, eax
0x18006dd7c  js      short loc_18006DD84
0x18006dd7e  add     rdi, 20h ; ' '
0x18006dd82  jmp     short loc_18006DD44
0x18006dd84  mov     edx, 0FC9h
0x18006dd89  jmp     loc_18006DE16
0x18006dd8e  xor     r15d, r15d
0x18006dd91  mov     rdi, [rsi+80h]
0x18006dd98  mov     ecx, [rsi+88h]
0x18006dd9e  mov     eax, ecx
0x18006dda0  shl     rax, 5
0x18006dda4  add     rax, [rsi+80h]
0x18006ddab  cmp     rdi, rax
0x18006ddae  jz      loc_18006DE43
0x18006ddb4  mov     rdx, [rdi]
0x18006ddb7  lea     r13, [rdi+10h]
0x18006ddbb  xor     r9d, r9d
0x18006ddbe  mov     qword ptr [rsp+0D0h+var_B0], r13; int
0x18006ddc3  mov     r8, r14
0x18006ddc6  mov     rcx, r12
0x18006ddc9  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x18006ddce  mov     r15d, eax
0x18006ddd1  test    eax, eax
0x18006ddd3  js      short loc_18006DE11
0x18006ddd5  xor     r15d, r15d
0x18006ddd8  cmp     [rdi+8], r15b
0x18006dddc  jz      short loc_18006DDE9
0x18006ddde  cmp     [rdi+18h], r15b
0x18006dde2  jz      short loc_18006DDE9
0x18006dde4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006dde9  cmp     [r13+0], r15b
0x18006dded  jnz     short loc_18006DE0B
0x18006ddef  cmp     [rdi+8], r15b
0x18006ddf3  jnz     short loc_18006DE0B
0x18006ddf5  cmp     [rdi+18h], r15b
0x18006ddf9  jnz     short loc_18006DE0B
0x18006ddfb  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x18006ddfe  mov     rcx, rsi; this
0x18006de01  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x18006de06  mov     rdi, rax
0x18006de09  jmp     short loc_18006DD98
0x18006de0b  add     rdi, 20h ; ' '
0x18006de0f  jmp     short loc_18006DD98
0x18006de11  mov     edx, 0FD4h; void *
0x18006de16  mov     rcx, [rbp+4Fh]; this
0x18006de1a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18006de21  mov     r9d, r15d; char *
0x18006de24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006de29  mov     edi, r15d
0x18006de2c  mov     rcx, rbx; string
0x18006de2f  call    cs:__imp_WindowsDeleteString
0x18006de35  lea     rcx, [rbp+47h+var_60]
0x18006de39  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x18006de3e  jmp     loc_18006DCA3
0x18006de43  test    rbx, rbx
0x18006de46  jz      loc_18006DEDC
0x18006de4c  test    ecx, ecx
0x18006de4e  jnz     loc_18006DEDC
0x18006de54  xor     edx, edx
0x18006de56  mov     [rbp+47h+string], r15
0x18006de5a  lea     rcx, [rbp+47h+string]
0x18006de5e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18006de63  mov     rcx, [rbp+47h+rguid]; rguid
0x18006de67  lea     rdx, [rbp+47h+string]; string
0x18006de6b  call    ?GetIdString@@YAJAEBU_GUID@@PEAPEAUHSTRING__@@@Z; GetIdString(_GUID const &,HSTRING__ * *)
0x18006de70  test    eax, eax
0x18006de72  js      short loc_18006DED3
0x18006de74  xor     edx, edx; length
0x18006de76  mov     rcx, rbx; string
0x18006de79  call    cs:__imp_WindowsGetStringRawBuffer
0x18006de7f  mov     rcx, [rbp+47h+string]; string
0x18006de83  xor     edx, edx; length
0x18006de85  mov     rdi, rax
0x18006de88  call    cs:__imp_WindowsGetStringRawBuffer
0x18006de8e  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18006de95  mov     rcx, [rbp+4Fh]; this
0x18006de99  mov     r9d, 80040154h; char *
  ... truncated ...
```
