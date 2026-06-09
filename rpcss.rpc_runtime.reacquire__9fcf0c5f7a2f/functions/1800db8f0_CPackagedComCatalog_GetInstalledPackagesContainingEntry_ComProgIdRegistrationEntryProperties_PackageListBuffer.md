# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComProgIdRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *)

- ea: `0x1800db8f0`
- end: `0x1800dbe3b`
- name: `??$GetInstalledPackagesContainingEntry@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAUHSTRING__@@_NPEBVPackageFilter@@@Z`
- size: `1355`
- prototype: `__int64 __usercall@<rax>(PackageListBuffer *this@<rcx>, char, PackageFilter *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a9d10`
- `0x1800e5210`

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
- `0x1800db8f0`
- `0x1800e0750`
- `0x1800e0768`
- `0x1800e5844`
- `0x1800e5898`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db9a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dba2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbaa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbac9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbcf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbdd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbe0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db9a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dba2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbaa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbac9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbcf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbdd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbe0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800dbd34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800dbd34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dba06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbd63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbd78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dba06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbd63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dbd78`

## string_xrefs

- `0x1800db96a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dbb37`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dbbb5`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dbcdb`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dbd48`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dbd84`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dbdf8`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dbda5`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x1800dbdb3`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComProgIdRegistrationEntryProperties>(
        PackageListBuffer *this,
        __int64 a2,
        __int64 a3,
        HSTRING a4,
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
  HRESULT v28; // eax
  PCWSTR v29; // rdi
  const char *v30; // rax
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-69h]
  HSTRING *p_string; // [rsp+20h] [rbp-69h]
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
  v11 =  IPackagedComCatalogContext::`vcall'{336,{flat}}(a3, a4, &v37);
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
      v13 =  IPackagedComCatalogContext::`vcall'{344,{flat}}(a3, v37, v14, v35);
      if ( v13 < 0 )
      {
        v17 = 3953;
        goto LABEL_66;
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
LABEL_66:
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
        LODWORD(p_string) = (_DWORD)i + 8;
        ComPackageInstallOrder = CPackagedComCatalog::TryGetComPackageInstallOrder(a3, *i, a2, 1);
        v23 = ComPackageInstallOrder;
        if ( ComPackageInstallOrder < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFBA,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)ComPackageInstallOrder,
            (int)p_string);
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
        LODWORD(p_string) = (_DWORD)j + 24;
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
            (int)p_string);
          goto LABEL_53;
        }
      }
    }
    v26 = (struct PackageIdAndInstallOrders *)*((_QWORD *)this + 16);
    while ( v26 != (struct PackageIdAndInstallOrders *)(*((_QWORD *)this + 16) + 32LL * *((unsigned int *)this + 34)) )
    {
      LODWORD(p_string) = (_DWORD)v26 + 16;
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
      v28 = WindowsDuplicateString(a4, &string);
      if ( v28 >= 0 )
      {
        v29 = WindowsGetStringRawBuffer(v18, 0);
        v34 = (char *)WindowsGetStringRawBuffer(string, 0);
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
          v34,
          v29);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14B,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v28,
          (int)p_string);
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
    v32);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800db8f0  mov     [rsp-8+arg_18], r9
0x1800db8f5  push    rbp
0x1800db8f6  push    rbx
0x1800db8f7  push    rsi
0x1800db8f8  push    rdi
0x1800db8f9  push    r12
0x1800db8fb  push    r13
0x1800db8fd  push    r14
0x1800db8ff  push    r15
0x1800db901  lea     rbp, [rsp-0Fh]
0x1800db906  sub     rsp, 98h
0x1800db90d  mov     r15, r9
0x1800db910  mov     r13, r8
0x1800db913  mov     r14, rdx
0x1800db916  mov     rsi, rcx
0x1800db919  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800db920  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800db925  mov     rdi, [rbp+47h+arg_28]
0x1800db929  test    al, al
0x1800db92b  jz      short loc_1800DB946
0x1800db92d  test    rdi, rdi
0x1800db930  jz      short loc_1800DB946
0x1800db932  mov     rcx, rdi; this
0x1800db935  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800db93a  test    rax, rax
0x1800db93d  jnz     short loc_1800DB946
0x1800db93f  xor     eax, eax
0x1800db941  jmp     loc_1800DBE26
0x1800db946  lea     r8, [rbp+47h+var_80]
0x1800db94a  mov     [rbp+47h+var_80], 0
0x1800db952  mov     rdx, r15
0x1800db955  mov     rcx, r13
0x1800db958  call    ??_9IPackagedComCatalogContext@@$BBFA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{336,{flat}}
0x1800db95d  xor     r15d, r15d
0x1800db960  mov     ebx, eax
0x1800db962  test    eax, eax
0x1800db964  jns     short loc_1800DB983
0x1800db966  mov     rcx, [rbp+4Fh]; this
0x1800db96a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800db971  mov     r9d, eax; char *
0x1800db974  mov     edx, 0F65h; void *
0x1800db979  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800db97e  jmp     loc_1800DBE24
0x1800db983  lea     rax, [rbp+47h+var_80]
0x1800db987  mov     [rbp+47h+var_60], r13
0x1800db98b  mov     [rbp+47h+var_58], rax
0x1800db98f  mov     r12d, r15d
0x1800db992  mov     [rbp+47h+var_50], 1
0x1800db996  xor     ecx, ecx; string
0x1800db998  mov     [rbp+47h+var_90], r15b
0x1800db99c  mov     [rbp+47h+string], r15
0x1800db9a0  call    cs:__imp_WindowsDeleteString
0x1800db9a7  nop     dword ptr [rax+rax+00h]
0x1800db9ac  mov     rdx, [rbp+47h+var_80]
0x1800db9b0  lea     rax, [rbp+47h+string]
0x1800db9b4  lea     r9, [rbp+47h+var_90]
0x1800db9b8  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800db9bd  mov     r8d, r12d
0x1800db9c0  mov     [rbp+47h+string], r15
0x1800db9c4  mov     rcx, r13
0x1800db9c7  call    ??_9IPackagedComCatalogContext@@$BBFI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{344,{flat}}
0x1800db9cc  mov     ebx, eax
0x1800db9ce  test    eax, eax
0x1800db9d0  js      loc_1800DBDEF
0x1800db9d6  cmp     [rbp+47h+var_90], r15b
0x1800db9da  jz      loc_1800DBAC5
0x1800db9e0  test    rdi, rdi
0x1800db9e3  jz      short loc_1800DBA3E
0x1800db9e5  mov     rcx, rdi; this
0x1800db9e8  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800db9ed  cmp     r15, rax
0x1800db9f0  jnb     short loc_1800DBA26
0x1800db9f2  mov     rdx, r15; unsigned __int64
0x1800db9f5  mov     rcx, rdi; this
0x1800db9f8  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x1800db9fd  mov     rcx, [rbp+47h+string]; string
0x1800dba01  xor     edx, edx; length
0x1800dba03  mov     rbx, rax
0x1800dba06  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dba0d  nop     dword ptr [rax+rax+00h]
0x1800dba12  mov     rcx, rax; unsigned __int16 *
0x1800dba15  mov     rdx, rbx; unsigned __int16 *
0x1800dba18  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x1800dba1d  test    al, al
0x1800dba1f  jnz     short loc_1800DBA3B
0x1800dba21  inc     r15
0x1800dba24  jmp     short loc_1800DB9E5
0x1800dba26  mov     rcx, [rbp+47h+string]; string
0x1800dba2a  call    cs:__imp_WindowsDeleteString
0x1800dba31  nop     dword ptr [rax+rax+00h]
0x1800dba36  xor     r15d, r15d
0x1800dba39  jmp     short loc_1800DBAB3
0x1800dba3b  xor     r15d, r15d
0x1800dba3e  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800dba42  lea     rdx, [rbp+47h+string]
0x1800dba46  mov     word ptr [rbp+47h+var_70+1], ax
0x1800dba4a  mov     rcx, rsi
0x1800dba4d  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800dba50  mov     byte ptr [rbp+47h+var_70+3], al
0x1800dba53  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800dba57  mov     word ptr [rbp+47h+var_68+1], ax
0x1800dba5b  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800dba5e  mov     byte ptr [rbp+47h+var_68+3], al
0x1800dba61  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800dba65  mov     word ptr [rbp+47h+var_78+1], ax
0x1800dba69  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800dba6c  mov     byte ptr [rbp+47h+var_78+3], al
0x1800dba6f  mov     byte ptr [rbp+47h+var_70], r15b
0x1800dba73  mov     dword ptr [rbp+47h+var_70+4], r15d
0x1800dba77  mov     rax, [rbp+47h+var_70]
0x1800dba7b  mov     byte ptr [rbp+47h+var_68], r15b
0x1800dba7f  mov     dword ptr [rbp+47h+var_68+4], r15d
0x1800dba83  mov     r9, [rbp+47h+var_68]
0x1800dba87  mov     byte ptr [rbp+47h+var_78], r15b
0x1800dba8b  mov     dword ptr [rbp+47h+var_78+4], r15d
0x1800dba8f  mov     r8, [rbp+47h+var_78]
0x1800dba93  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800dba98  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x1800dba9d  mov     ebx, eax
0x1800dba9f  test    eax, eax
0x1800dbaa1  js      short loc_1800DBABB
0x1800dbaa3  mov     rcx, [rbp+47h+string]; string
0x1800dbaa7  call    cs:__imp_WindowsDeleteString
0x1800dbaae  nop     dword ptr [rax+rax+00h]
0x1800dbab3  inc     r12d
0x1800dbab6  jmp     loc_1800DB996
0x1800dbabb  mov     edx, 0F8Ah
0x1800dbac0  jmp     loc_1800DBDF4
0x1800dbac5  mov     rcx, [rbp+47h+string]; string
0x1800dbac9  call    cs:__imp_WindowsDeleteString
0x1800dbad0  nop     dword ptr [rax+rax+00h]
0x1800dbad5  lea     rcx, [rbp+47h+var_60]
0x1800dbad9  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800dbade  mov     rbx, r15
0x1800dbae1  mov     [rbp+47h+var_78], rbx
0x1800dbae5  cmp     [rsi+88h], r15d
0x1800dbaec  jz      short loc_1800DBB02
0x1800dbaee  mov     rdx, [rsi+80h]
0x1800dbaf5  lea     rcx, [rbp+47h+var_78]
0x1800dbaf9  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800dbafe  mov     rbx, [rbp+47h+var_78]
0x1800dbb02  cmp     [rbp+47h+arg_20], r15b
0x1800dbb06  jz      loc_1800DBC52
0x1800dbb0c  mov     dword ptr [rbp+47h+string], r15d
0x1800dbb10  test    r14, r14
0x1800dbb13  jz      short loc_1800DBB6A
0x1800dbb15  mov     rax, [r14]
0x1800dbb18  lea     r8, [rbp+47h+string]
0x1800dbb1c  mov     edx, 1
0x1800dbb21  mov     rcx, r14
0x1800dbb24  mov     rax, [rax+60h]
0x1800dbb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbb2d  mov     edi, eax
0x1800dbb2f  test    eax, eax
0x1800dbb31  jns     short loc_1800DBB6A
0x1800dbb33  mov     rcx, [rbp+4Fh]; this
0x1800dbb37  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dbb3e  mov     r9d, eax; char *
0x1800dbb41  mov     edx, 0FB4h; void *
0x1800dbb46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbb4b  mov     edx, dword ptr [rbp+47h+string]
0x1800dbb4e  test    edx, edx
0x1800dbb50  jz      loc_1800DBCED
0x1800dbb56  mov     rcx, [r14]
0x1800dbb59  mov     rax, [rcx+68h]
0x1800dbb5d  mov     rcx, r14
0x1800dbb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbb65  jmp     loc_1800DBCED
0x1800dbb6a  mov     rdi, [rsi+80h]
0x1800dbb71  mov     eax, [rsi+88h]
0x1800dbb77  shl     rax, 5
0x1800dbb7b  add     rax, [rsi+80h]
0x1800dbb82  cmp     rdi, rax
0x1800dbb85  jz      short loc_1800DBBE8
0x1800dbb87  mov     rdx, [rdi]
0x1800dbb8a  lea     rax, [rdi+8]
0x1800dbb8e  mov     r9d, 1
0x1800dbb94  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800dbb99  mov     r8, r14
0x1800dbb9c  mov     rcx, r13
0x1800dbb9f  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800dbba4  mov     r15d, eax
0x1800dbba7  test    eax, eax
0x1800dbba9  js      short loc_1800DBBB1
0x1800dbbab  add     rdi, 20h ; ' '
0x1800dbbaf  jmp     short loc_1800DBB71
0x1800dbbb1  mov     rcx, [rbp+4Fh]; this
0x1800dbbb5  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dbbbc  mov     r9d, r15d; char *
0x1800dbbbf  mov     edx, 0FBAh; void *
0x1800dbbc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbbc9  mov     edx, dword ptr [rbp+47h+string]
0x1800dbbcc  test    edx, edx
0x1800dbbce  jz      loc_1800DBCEA
0x1800dbbd4  mov     rax, [r14]
0x1800dbbd7  mov     rcx, r14
0x1800dbbda  mov     rax, [rax+68h]
0x1800dbbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbbe3  jmp     loc_1800DBCEA
0x1800dbbe8  mov     edx, dword ptr [rbp+47h+string]
0x1800dbbeb  test    edx, edx
0x1800dbbed  jz      short loc_1800DBBFE
0x1800dbbef  mov     rax, [r14]
0x1800dbbf2  mov     rcx, r14
0x1800dbbf5  mov     rax, [rax+68h]
0x1800dbbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbbfe  mov     rdi, [rsi+80h]
0x1800dbc05  mov     eax, [rsi+88h]
0x1800dbc0b  shl     rax, 5
0x1800dbc0f  add     rax, [rsi+80h]
0x1800dbc16  cmp     rdi, rax
0x1800dbc19  jz      short loc_1800DBC4F
0x1800dbc1b  mov     rdx, [rdi]
0x1800dbc1e  lea     rax, [rdi+18h]
0x1800dbc22  mov     r9d, 2
0x1800dbc28  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800dbc2d  mov     r8, r14
0x1800dbc30  mov     rcx, r13
0x1800dbc33  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800dbc38  mov     r15d, eax
0x1800dbc3b  test    eax, eax
0x1800dbc3d  js      short loc_1800DBC45
0x1800dbc3f  add     rdi, 20h ; ' '
0x1800dbc43  jmp     short loc_1800DBC05
0x1800dbc45  mov     edx, 0FC9h
0x1800dbc4a  jmp     loc_1800DBCD7
0x1800dbc4f  xor     r15d, r15d
0x1800dbc52  mov     rdi, [rsi+80h]
0x1800dbc59  mov     ecx, [rsi+88h]
0x1800dbc5f  mov     eax, ecx
0x1800dbc61  shl     rax, 5
0x1800dbc65  add     rax, [rsi+80h]
0x1800dbc6c  cmp     rdi, rax
0x1800dbc6f  jz      loc_1800DBD0C
0x1800dbc75  mov     rdx, [rdi]
0x1800dbc78  lea     r12, [rdi+10h]
0x1800dbc7c  xor     r9d, r9d
0x1800dbc7f  mov     qword ptr [rsp+0D0h+var_B0], r12; int
0x1800dbc84  mov     r8, r14
0x1800dbc87  mov     rcx, r13
0x1800dbc8a  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800dbc8f  mov     r15d, eax
0x1800dbc92  test    eax, eax
0x1800dbc94  js      short loc_1800DBCD2
0x1800dbc96  xor     r15d, r15d
0x1800dbc99  cmp     [rdi+8], r15b
0x1800dbc9d  jz      short loc_1800DBCAA
0x1800dbc9f  cmp     [rdi+18h], r15b
0x1800dbca3  jz      short loc_1800DBCAA
0x1800dbca5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800dbcaa  cmp     [r12], r15b
0x1800dbcae  jnz     short loc_1800DBCCC
0x1800dbcb0  cmp     [rdi+8], r15b
0x1800dbcb4  jnz     short loc_1800DBCCC
0x1800dbcb6  cmp     [rdi+18h], r15b
0x1800dbcba  jnz     short loc_1800DBCCC
0x1800dbcbc  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x1800dbcbf  mov     rcx, rsi; this
0x1800dbcc2  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x1800dbcc7  mov     rdi, rax
0x1800dbcca  jmp     short loc_1800DBC59
0x1800dbccc  add     rdi, 20h ; ' '
0x1800dbcd0  jmp     short loc_1800DBC59
0x1800dbcd2  mov     edx, 0FD4h; void *
0x1800dbcd7  mov     rcx, [rbp+4Fh]; this
0x1800dbcdb  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dbce2  mov     r9d, r15d; char *
0x1800dbce5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbcea  mov     edi, r15d
0x1800dbced  mov     rcx, rbx; string
0x1800dbcf0  call    cs:__imp_WindowsDeleteString
0x1800dbcf7  nop     dword ptr [rax+rax+00h]
0x1800dbcfc  lea     rcx, [rbp+47h+var_60]
0x1800dbd00  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800dbd05  mov     eax, edi
0x1800dbd07  jmp     loc_1800DBE26
0x1800dbd0c  test    rbx, rbx
0x1800dbd0f  jz      loc_1800DBDD2
0x1800dbd15  test    ecx, ecx
0x1800dbd17  jnz     loc_1800DBDD2
0x1800dbd1d  xor     edx, edx
0x1800dbd1f  mov     [rbp+47h+string], r15
0x1800dbd23  lea     rcx, [rbp+47h+string]
0x1800dbd27  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800dbd2c  mov     rcx, [rbp+47h+arg_18]; string
0x1800dbd30  lea     rdx, [rbp+47h+string]; newString
0x1800dbd34  call    cs:__imp_WindowsDuplicateString
0x1800dbd3b  nop     dword ptr [rax+rax+00h]
0x1800dbd40  test    eax, eax
0x1800dbd42  jns     short loc_1800DBD5E
0x1800dbd44  mov     rcx, [rbp+4Fh]; this
0x1800dbd48  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dbd4f  mov     r9d, eax; char *
0x1800dbd52  mov     edx, 14Bh; void *
0x1800dbd57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbd5c  jmp     short loc_1800DBDC9
0x1800dbd5e  xor     edx, edx; length
0x1800dbd60  mov     rcx, rbx; string
0x1800dbd63  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dbd6a  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
