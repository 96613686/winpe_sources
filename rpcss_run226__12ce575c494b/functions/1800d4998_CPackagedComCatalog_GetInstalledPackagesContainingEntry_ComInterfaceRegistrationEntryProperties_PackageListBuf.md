# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComInterfaceRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)

- ea: `0x1800d4998`
- end: `0x1800d4e85`
- name: `??$GetInstalledPackagesContainingEntry@UComInterfaceRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z`
- size: `1261`
- prototype: `__int64 __usercall@<rax>(PackageListBuffer *this@<rcx>, char, PackageFilter *)`
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a5354`
- `0x1800a5cfc`
- `0x1800ae2f4`
- `0x1800de150`

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
- `0x1800d4998`
- `0x1800d9988`
- `0x1800d99a0`
- `0x1800dd864`
- `0x1800de7e4`
- `0x1800de834`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4a48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4ac6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4b3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4b59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4d7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4e2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4e5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4a48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4ac6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4b3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4b59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4d7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4e2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4e5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4dd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4dd5`

## string_xrefs

- `0x1800d4a12`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d4bc1`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d4c3f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d4d65`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d4ddb`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d4e49`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d4dfc`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x1800d4e0a`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComInterfaceRegistrationEntryProperties>(
        PackageListBuffer *this,
        struct IUserToken *a2,
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
  __int64 i; // rdi
  int ComPackageInstallOrder; // eax
  int v23; // r15d
  __int64 j; // rdi
  __int64 v25; // rdx
  struct PackageIdAndInstallOrders *v26; // rdi
  __int64 v27; // rcx
  PCWSTR v28; // rdi
  const char *v29; // rax
  __int64 v30; // rdx
  int v31; // [rsp+20h] [rbp-69h]
  HSTRING *p_string; // [rsp+20h] [rbp-69h]
  int v33; // [rsp+20h] [rbp-69h]
  int v34; // [rsp+20h] [rbp-69h]
  char *v35; // [rsp+28h] [rbp-61h]
  _BYTE v36[8]; // [rsp+40h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-41h] BYREF
  __int64 v38; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v39; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-29h]
  int v41; // [rsp+64h] [rbp-25h]
  unsigned int v42; // [rsp+68h] [rbp-21h]
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
  v38 = 0;
  v11 =  IPackagedComCatalogContext::`vcall'{304,{flat}}(a3, a4, &v38);
  v12 = 0;
  v13 = v11;
  if ( v11 >= 0 )
  {
    v44[0] = a3;
    v44[1] = &v38;
    v14 = 0;
    v45 = 1;
    while ( 1 )
    {
      v36[0] = 0;
      string = 0;
      WindowsDeleteString(0);
      p_string = &string;
      string = 0;
      v13 =  IPackagedComCatalogContext::`vcall'{312,{flat}}(a3, v38, v14, v36);
      if ( v13 < 0 )
      {
        v17 = 3953;
        goto LABEL_65;
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
      *(_WORD *)((char *)&v39 + 1) = *(_WORD *)((char *)&v38 + 1);
      BYTE3(v39) = BYTE3(v38);
      LOBYTE(v40) = 0;
      v41 = 0;
      LOBYTE(v42) = 0;
      v43 = 0;
      LOBYTE(v39) = 0;
      HIDWORD(v39) = 0;
      v13 = PackageListBuffer::AddPackage(
              (__int64)this,
              &string,
              (HSTRING)(unsigned int)v39,
              (HSTRING)v42,
              (HSTRING)v40);
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
        wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v44);
        return (unsigned int)v13;
      }
      WindowsDeleteString(string);
LABEL_18:
      ++v14;
    }
    WindowsDeleteString(string);
    wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v44);
    v18 = 0;
    v39 = 0;
    if ( *((_DWORD *)this + 34) )
    {
      OpaqueString::operator=(&v39, *((_QWORD *)this + 16));
      v18 = v39;
    }
    if ( a5 )
    {
      LODWORD(string) = 0;
      if ( a2 )
      {
        v19 = (*(__int64 (__fastcall **)(struct IUserToken *, __int64, HSTRING *))(*(_QWORD *)a2 + 96LL))(
                a2,
                1,
                &string);
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
            (*(void (__fastcall **)(struct IUserToken *))(*(_QWORD *)a2 + 104LL))(a2);
LABEL_54:
          WindowsDeleteString(v18);
          wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v44);
          return v20;
        }
      }
      for ( i = *((_QWORD *)this + 16); i != *((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34); i += 32 )
      {
        ComPackageInstallOrder = CPackagedComCatalog::TryGetComPackageInstallOrder(
                                   a3,
                                   *(HSTRING *)i,
                                   a2,
                                   1u,
                                   (_BYTE *)(i + 8));
        v23 = ComPackageInstallOrder;
        if ( ComPackageInstallOrder < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFBA,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)ComPackageInstallOrder,
            v33);
          if ( (_DWORD)string )
            (*(void (__fastcall **)(struct IUserToken *))(*(_QWORD *)a2 + 104LL))(a2);
LABEL_53:
          v20 = v23;
          goto LABEL_54;
        }
      }
      if ( (_DWORD)string )
        (*(void (__fastcall **)(struct IUserToken *))(*(_QWORD *)a2 + 104LL))(a2);
      for ( j = *((_QWORD *)this + 16); j != *((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34); j += 32 )
      {
        v23 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *(HSTRING *)j, a2, 2u, (_BYTE *)(j + 24));
        if ( v23 < 0 )
        {
          v25 = 4041;
LABEL_52:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v25,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v23,
            v34);
          goto LABEL_53;
        }
      }
    }
    v26 = (struct PackageIdAndInstallOrders *)*((_QWORD *)this + 16);
    while ( v26 != (struct PackageIdAndInstallOrders *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34)) )
    {
      v23 = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *(HSTRING *)v26, a2, 0, (_BYTE *)v26 + 16);
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
        v35 = (char *)WindowsGetStringRawBuffer(string, 0);
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
          v35,
          v28);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
    }
    WindowsDeleteString(v18);
    wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v44);
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
0x1800d4998  mov     [rsp-8+rguid], r9
0x1800d499d  push    rbp
0x1800d499e  push    rbx
0x1800d499f  push    rsi
0x1800d49a0  push    rdi
0x1800d49a1  push    r12
0x1800d49a3  push    r13
0x1800d49a5  push    r14
0x1800d49a7  push    r15
0x1800d49a9  lea     rbp, [rsp-0Fh]
0x1800d49ae  sub     rsp, 98h
0x1800d49b5  mov     r15, r9
0x1800d49b8  mov     r13, r8
0x1800d49bb  mov     r14, rdx
0x1800d49be  mov     rsi, rcx
0x1800d49c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800d49c8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800d49cd  mov     rdi, [rbp+47h+arg_28]
0x1800d49d1  test    al, al
0x1800d49d3  jz      short loc_1800D49EE
0x1800d49d5  test    rdi, rdi
0x1800d49d8  jz      short loc_1800D49EE
0x1800d49da  mov     rcx, rdi; this
0x1800d49dd  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800d49e2  test    rax, rax
0x1800d49e5  jnz     short loc_1800D49EE
0x1800d49e7  xor     eax, eax
0x1800d49e9  jmp     loc_1800D4E71
0x1800d49ee  lea     r8, [rbp+47h+var_80]
0x1800d49f2  mov     [rbp+47h+var_80], 0
0x1800d49fa  mov     rdx, r15
0x1800d49fd  mov     rcx, r13
0x1800d4a00  call    ??_9IPackagedComCatalogContext@@$BBDA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{304,{flat}}
0x1800d4a05  xor     r15d, r15d
0x1800d4a08  mov     ebx, eax
0x1800d4a0a  test    eax, eax
0x1800d4a0c  jns     short loc_1800D4A2B
0x1800d4a0e  mov     rcx, [rbp+4Fh]; this
0x1800d4a12  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d4a19  mov     r9d, eax; char *
0x1800d4a1c  mov     edx, 0F65h; void *
0x1800d4a21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4a26  jmp     loc_1800D4E6F
0x1800d4a2b  lea     rax, [rbp+47h+var_80]
0x1800d4a2f  mov     [rbp+47h+var_60], r13
0x1800d4a33  mov     [rbp+47h+var_58], rax
0x1800d4a37  mov     r12d, r15d
0x1800d4a3a  mov     [rbp+47h+var_50], 1
0x1800d4a3e  xor     ecx, ecx; string
0x1800d4a40  mov     [rbp+47h+var_90], r15b
0x1800d4a44  mov     [rbp+47h+string], r15
0x1800d4a48  call    cs:__imp_WindowsDeleteString
0x1800d4a4e  mov     rdx, [rbp+47h+var_80]
0x1800d4a52  lea     rax, [rbp+47h+string]
0x1800d4a56  lea     r9, [rbp+47h+var_90]
0x1800d4a5a  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800d4a5f  mov     r8d, r12d
0x1800d4a62  mov     [rbp+47h+string], r15
0x1800d4a66  mov     rcx, r13
0x1800d4a69  call    ??_9IPackagedComCatalogContext@@$BBDI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{312,{flat}}
0x1800d4a6e  mov     ebx, eax
0x1800d4a70  test    eax, eax
0x1800d4a72  js      loc_1800D4E40
0x1800d4a78  cmp     [rbp+47h+var_90], r15b
0x1800d4a7c  jz      loc_1800D4B55
0x1800d4a82  test    rdi, rdi
0x1800d4a85  jz      short loc_1800D4AD4
0x1800d4a87  mov     rcx, rdi; this
0x1800d4a8a  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800d4a8f  cmp     r15, rax
0x1800d4a92  jnb     short loc_1800D4AC2
0x1800d4a94  mov     rdx, r15; unsigned __int64
0x1800d4a97  mov     rcx, rdi; this
0x1800d4a9a  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x1800d4a9f  mov     rcx, [rbp+47h+string]; string
0x1800d4aa3  xor     edx, edx; length
0x1800d4aa5  mov     rbx, rax
0x1800d4aa8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d4aae  mov     rcx, rax; unsigned __int16 *
0x1800d4ab1  mov     rdx, rbx; unsigned __int16 *
0x1800d4ab4  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x1800d4ab9  test    al, al
0x1800d4abb  jnz     short loc_1800D4AD1
0x1800d4abd  inc     r15
0x1800d4ac0  jmp     short loc_1800D4A87
0x1800d4ac2  mov     rcx, [rbp+47h+string]; string
0x1800d4ac6  call    cs:__imp_WindowsDeleteString
0x1800d4acc  xor     r15d, r15d
0x1800d4acf  jmp     short loc_1800D4B43
0x1800d4ad1  xor     r15d, r15d
0x1800d4ad4  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800d4ad8  lea     rdx, [rbp+47h+string]
0x1800d4adc  mov     word ptr [rbp+47h+var_70+1], ax
0x1800d4ae0  mov     rcx, rsi
0x1800d4ae3  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800d4ae6  mov     byte ptr [rbp+47h+var_70+3], al
0x1800d4ae9  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800d4aed  mov     word ptr [rbp+47h+var_68+1], ax
0x1800d4af1  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800d4af4  mov     byte ptr [rbp+47h+var_68+3], al
0x1800d4af7  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800d4afb  mov     word ptr [rbp+47h+var_78+1], ax
0x1800d4aff  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800d4b02  mov     byte ptr [rbp+47h+var_78+3], al
0x1800d4b05  mov     byte ptr [rbp+47h+var_70], r15b
0x1800d4b09  mov     dword ptr [rbp+47h+var_70+4], r15d
0x1800d4b0d  mov     rax, [rbp+47h+var_70]
0x1800d4b11  mov     byte ptr [rbp+47h+var_68], r15b
0x1800d4b15  mov     dword ptr [rbp+47h+var_68+4], r15d
0x1800d4b19  mov     r9, [rbp+47h+var_68]
0x1800d4b1d  mov     byte ptr [rbp+47h+var_78], r15b
0x1800d4b21  mov     dword ptr [rbp+47h+var_78+4], r15d
0x1800d4b25  mov     r8, [rbp+47h+var_78]
0x1800d4b29  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800d4b2e  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x1800d4b33  mov     ebx, eax
0x1800d4b35  test    eax, eax
0x1800d4b37  js      short loc_1800D4B4B
0x1800d4b39  mov     rcx, [rbp+47h+string]; string
0x1800d4b3d  call    cs:__imp_WindowsDeleteString
0x1800d4b43  inc     r12d
0x1800d4b46  jmp     loc_1800D4A3E
0x1800d4b4b  mov     edx, 0F8Ah
0x1800d4b50  jmp     loc_1800D4E45
0x1800d4b55  mov     rcx, [rbp+47h+string]; string
0x1800d4b59  call    cs:__imp_WindowsDeleteString
0x1800d4b5f  lea     rcx, [rbp+47h+var_60]
0x1800d4b63  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800d4b68  mov     rbx, r15
0x1800d4b6b  mov     [rbp+47h+var_78], rbx
0x1800d4b6f  cmp     [rsi+88h], r15d
0x1800d4b76  jz      short loc_1800D4B8C
0x1800d4b78  mov     rdx, [rsi+80h]
0x1800d4b7f  lea     rcx, [rbp+47h+var_78]
0x1800d4b83  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800d4b88  mov     rbx, [rbp+47h+var_78]
0x1800d4b8c  cmp     [rbp+47h+arg_20], r15b
0x1800d4b90  jz      loc_1800D4CDC
0x1800d4b96  mov     dword ptr [rbp+47h+string], r15d
0x1800d4b9a  test    r14, r14
0x1800d4b9d  jz      short loc_1800D4BF4
0x1800d4b9f  mov     rax, [r14]
0x1800d4ba2  lea     r8, [rbp+47h+string]
0x1800d4ba6  mov     edx, 1
0x1800d4bab  mov     rcx, r14
0x1800d4bae  mov     rax, [rax+60h]
0x1800d4bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4bb7  mov     edi, eax
0x1800d4bb9  test    eax, eax
0x1800d4bbb  jns     short loc_1800D4BF4
0x1800d4bbd  mov     rcx, [rbp+4Fh]; this
0x1800d4bc1  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d4bc8  mov     r9d, eax; char *
0x1800d4bcb  mov     edx, 0FB4h; void *
0x1800d4bd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4bd5  mov     edx, dword ptr [rbp+47h+string]
0x1800d4bd8  test    edx, edx
0x1800d4bda  jz      loc_1800D4D77
0x1800d4be0  mov     rcx, [r14]
0x1800d4be3  mov     rax, [rcx+68h]
0x1800d4be7  mov     rcx, r14
0x1800d4bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4bef  jmp     loc_1800D4D77
0x1800d4bf4  mov     rdi, [rsi+80h]
0x1800d4bfb  mov     eax, [rsi+88h]
0x1800d4c01  shl     rax, 5
0x1800d4c05  add     rax, [rsi+80h]
0x1800d4c0c  cmp     rdi, rax
0x1800d4c0f  jz      short loc_1800D4C72
0x1800d4c11  mov     rdx, [rdi]
0x1800d4c14  lea     rax, [rdi+8]
0x1800d4c18  mov     r9d, 1
0x1800d4c1e  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800d4c23  mov     r8, r14
0x1800d4c26  mov     rcx, r13
0x1800d4c29  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800d4c2e  mov     r15d, eax
0x1800d4c31  test    eax, eax
0x1800d4c33  js      short loc_1800D4C3B
0x1800d4c35  add     rdi, 20h ; ' '
0x1800d4c39  jmp     short loc_1800D4BFB
0x1800d4c3b  mov     rcx, [rbp+4Fh]; this
0x1800d4c3f  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d4c46  mov     r9d, r15d; char *
0x1800d4c49  mov     edx, 0FBAh; void *
0x1800d4c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4c53  mov     edx, dword ptr [rbp+47h+string]
0x1800d4c56  test    edx, edx
0x1800d4c58  jz      loc_1800D4D74
0x1800d4c5e  mov     rax, [r14]
0x1800d4c61  mov     rcx, r14
0x1800d4c64  mov     rax, [rax+68h]
0x1800d4c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4c6d  jmp     loc_1800D4D74
0x1800d4c72  mov     edx, dword ptr [rbp+47h+string]
0x1800d4c75  test    edx, edx
0x1800d4c77  jz      short loc_1800D4C88
0x1800d4c79  mov     rax, [r14]
0x1800d4c7c  mov     rcx, r14
0x1800d4c7f  mov     rax, [rax+68h]
0x1800d4c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4c88  mov     rdi, [rsi+80h]
0x1800d4c8f  mov     eax, [rsi+88h]
0x1800d4c95  shl     rax, 5
0x1800d4c99  add     rax, [rsi+80h]
0x1800d4ca0  cmp     rdi, rax
0x1800d4ca3  jz      short loc_1800D4CD9
0x1800d4ca5  mov     rdx, [rdi]
0x1800d4ca8  lea     rax, [rdi+18h]
0x1800d4cac  mov     r9d, 2
0x1800d4cb2  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800d4cb7  mov     r8, r14
0x1800d4cba  mov     rcx, r13
0x1800d4cbd  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800d4cc2  mov     r15d, eax
0x1800d4cc5  test    eax, eax
0x1800d4cc7  js      short loc_1800D4CCF
0x1800d4cc9  add     rdi, 20h ; ' '
0x1800d4ccd  jmp     short loc_1800D4C8F
0x1800d4ccf  mov     edx, 0FC9h
0x1800d4cd4  jmp     loc_1800D4D61
0x1800d4cd9  xor     r15d, r15d
0x1800d4cdc  mov     rdi, [rsi+80h]
0x1800d4ce3  mov     ecx, [rsi+88h]
0x1800d4ce9  mov     eax, ecx
0x1800d4ceb  shl     rax, 5
0x1800d4cef  add     rax, [rsi+80h]
0x1800d4cf6  cmp     rdi, rax
0x1800d4cf9  jz      loc_1800D4D90
0x1800d4cff  mov     rdx, [rdi]
0x1800d4d02  lea     r12, [rdi+10h]
0x1800d4d06  xor     r9d, r9d
0x1800d4d09  mov     qword ptr [rsp+0D0h+var_B0], r12; int
0x1800d4d0e  mov     r8, r14
0x1800d4d11  mov     rcx, r13
0x1800d4d14  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800d4d19  mov     r15d, eax
0x1800d4d1c  test    eax, eax
0x1800d4d1e  js      short loc_1800D4D5C
0x1800d4d20  xor     r15d, r15d
0x1800d4d23  cmp     [rdi+8], r15b
0x1800d4d27  jz      short loc_1800D4D34
0x1800d4d29  cmp     [rdi+18h], r15b
0x1800d4d2d  jz      short loc_1800D4D34
0x1800d4d2f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d4d34  cmp     [r12], r15b
0x1800d4d38  jnz     short loc_1800D4D56
0x1800d4d3a  cmp     [rdi+8], r15b
0x1800d4d3e  jnz     short loc_1800D4D56
0x1800d4d40  cmp     [rdi+18h], r15b
0x1800d4d44  jnz     short loc_1800D4D56
0x1800d4d46  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x1800d4d49  mov     rcx, rsi; this
0x1800d4d4c  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x1800d4d51  mov     rdi, rax
0x1800d4d54  jmp     short loc_1800D4CE3
0x1800d4d56  add     rdi, 20h ; ' '
0x1800d4d5a  jmp     short loc_1800D4CE3
0x1800d4d5c  mov     edx, 0FD4h; void *
0x1800d4d61  mov     rcx, [rbp+4Fh]; this
0x1800d4d65  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d4d6c  mov     r9d, r15d; char *
0x1800d4d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4d74  mov     edi, r15d
0x1800d4d77  mov     rcx, rbx; string
0x1800d4d7a  call    cs:__imp_WindowsDeleteString
0x1800d4d80  lea     rcx, [rbp+47h+var_60]
0x1800d4d84  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800d4d89  mov     eax, edi
0x1800d4d8b  jmp     loc_1800D4E71
0x1800d4d90  test    rbx, rbx
0x1800d4d93  jz      loc_1800D4E29
0x1800d4d99  test    ecx, ecx
0x1800d4d9b  jnz     loc_1800D4E29
0x1800d4da1  xor     edx, edx
0x1800d4da3  mov     [rbp+47h+string], r15
0x1800d4da7  lea     rcx, [rbp+47h+string]
0x1800d4dab  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800d4db0  mov     rcx, [rbp+47h+rguid]; rguid
0x1800d4db4  lea     rdx, [rbp+47h+string]; string
0x1800d4db8  call    ?GetIdString@@YAJAEBU_GUID@@PEAPEAUHSTRING__@@@Z; GetIdString(_GUID const &,HSTRING__ * *)
0x1800d4dbd  test    eax, eax
0x1800d4dbf  js      short loc_1800D4E20
0x1800d4dc1  xor     edx, edx; length
0x1800d4dc3  mov     rcx, rbx; string
0x1800d4dc6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d4dcc  mov     rcx, [rbp+47h+string]; string
0x1800d4dd0  xor     edx, edx; length
0x1800d4dd2  mov     rdi, rax
0x1800d4dd5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d4ddb  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d4de2  mov     rcx, [rbp+4Fh]; this
0x1800d4de6  mov     r9d, 80040155h; char *
0x1800d4dec  mov     [rsp+0D0h+var_A0], rdi
0x1800d4df1  mov     [rsp+0D0h+var_A8], rax; char *
0x1800d4df6  cmp     [rbp+47h+arg_20], r15b
0x1800d4dfa  jz      short loc_1800D4E0A
0x1800d4dfc  lea     rax, aWarningPackage_0; "Warning: PackagedCom entry for %ls in p"...
0x1800d4e03  mov     edx, 0FF6h
0x1800d4e08  jmp     short loc_1800D4E16
  ... truncated ...
```
