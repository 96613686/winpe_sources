# CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComProgIdRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *)

- ea: `0x1800d4e8c`
- end: `0x1800d5394`
- name: `??$GetInstalledPackagesContainingEntry@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAUHSTRING__@@_NPEBVPackageFilter@@@Z`
- size: `1288`
- prototype: `__int64 __usercall@<rax>(PackageListBuffer *this@<rcx>, char, PackageFilter *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a4d50`
- `0x1800de1d0`

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
- `0x1800d4e8c`
- `0x1800d99e8`
- `0x1800d9a00`
- `0x1800de7e4`
- `0x1800de834`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4f3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4fba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5031`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d504d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d526e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d533b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d536b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4f3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4fba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5031`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d504d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d526e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d533b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d536b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d52ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d52ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4f9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d4f9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52e4`

## string_xrefs

- `0x1800d4f06`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d50b5`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d5133`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d5259`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d52ba`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d52ea`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d5358`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800d530b`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Package may not be installed for user.`
- `0x1800d5319`: `Warning: PackagedCom entry for %ls in package %ls (and possibly others) exists but is not visible to the caller. Lookup was performed without per-user state, which may indicate that the caller was elevated, non-user, or otherwise blocks per-user registrations (e.g. UWP and some OS processes).`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComProgIdRegistrationEntryProperties>(
        PackageListBuffer *this,
        struct IUserToken *a2,
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
  __int64 i; // rdi
  int ComPackageInstallOrder; // eax
  int v23; // r15d
  __int64 j; // rdi
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
  unsigned int v41; // [rsp+68h] [rbp-21h]
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
      v13 = PackageListBuffer::AddPackage(
              (__int64)this,
              &string,
              (HSTRING)(unsigned int)v38,
              (HSTRING)v41,
              (HSTRING)v39);
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
          wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(v43);
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
            (int)p_string);
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
            (int)p_string);
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
0x1800d4e8c  mov     [rsp-8+arg_18], r9
0x1800d4e91  push    rbp
0x1800d4e92  push    rbx
0x1800d4e93  push    rsi
0x1800d4e94  push    rdi
0x1800d4e95  push    r12
0x1800d4e97  push    r13
0x1800d4e99  push    r14
0x1800d4e9b  push    r15
0x1800d4e9d  lea     rbp, [rsp-0Fh]
0x1800d4ea2  sub     rsp, 98h
0x1800d4ea9  mov     r15, r9
0x1800d4eac  mov     r13, r8
0x1800d4eaf  mov     r14, rdx
0x1800d4eb2  mov     rsi, rcx
0x1800d4eb5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800d4ebc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800d4ec1  mov     rdi, [rbp+47h+arg_28]
0x1800d4ec5  test    al, al
0x1800d4ec7  jz      short loc_1800D4EE2
0x1800d4ec9  test    rdi, rdi
0x1800d4ecc  jz      short loc_1800D4EE2
0x1800d4ece  mov     rcx, rdi; this
0x1800d4ed1  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800d4ed6  test    rax, rax
0x1800d4ed9  jnz     short loc_1800D4EE2
0x1800d4edb  xor     eax, eax
0x1800d4edd  jmp     loc_1800D5380
0x1800d4ee2  lea     r8, [rbp+47h+var_80]
0x1800d4ee6  mov     [rbp+47h+var_80], 0
0x1800d4eee  mov     rdx, r15
0x1800d4ef1  mov     rcx, r13
0x1800d4ef4  call    ??_9IPackagedComCatalogContext@@$BBFA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{336,{flat}}
0x1800d4ef9  xor     r15d, r15d
0x1800d4efc  mov     ebx, eax
0x1800d4efe  test    eax, eax
0x1800d4f00  jns     short loc_1800D4F1F
0x1800d4f02  mov     rcx, [rbp+4Fh]; this
0x1800d4f06  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d4f0d  mov     r9d, eax; char *
0x1800d4f10  mov     edx, 0F65h; void *
0x1800d4f15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4f1a  jmp     loc_1800D537E
0x1800d4f1f  lea     rax, [rbp+47h+var_80]
0x1800d4f23  mov     [rbp+47h+var_60], r13
0x1800d4f27  mov     [rbp+47h+var_58], rax
0x1800d4f2b  mov     r12d, r15d
0x1800d4f2e  mov     [rbp+47h+var_50], 1
0x1800d4f32  xor     ecx, ecx; string
0x1800d4f34  mov     [rbp+47h+var_90], r15b
0x1800d4f38  mov     [rbp+47h+string], r15
0x1800d4f3c  call    cs:__imp_WindowsDeleteString
0x1800d4f42  mov     rdx, [rbp+47h+var_80]
0x1800d4f46  lea     rax, [rbp+47h+string]
0x1800d4f4a  lea     r9, [rbp+47h+var_90]
0x1800d4f4e  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800d4f53  mov     r8d, r12d
0x1800d4f56  mov     [rbp+47h+string], r15
0x1800d4f5a  mov     rcx, r13
0x1800d4f5d  call    ??_9IPackagedComCatalogContext@@$BBFI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{344,{flat}}
0x1800d4f62  mov     ebx, eax
0x1800d4f64  test    eax, eax
0x1800d4f66  js      loc_1800D534F
0x1800d4f6c  cmp     [rbp+47h+var_90], r15b
0x1800d4f70  jz      loc_1800D5049
0x1800d4f76  test    rdi, rdi
0x1800d4f79  jz      short loc_1800D4FC8
0x1800d4f7b  mov     rcx, rdi; this
0x1800d4f7e  call    ?GetPackageCount@PackageFilter@@QEBA_KXZ; PackageFilter::GetPackageCount(void)
0x1800d4f83  cmp     r15, rax
0x1800d4f86  jnb     short loc_1800D4FB6
0x1800d4f88  mov     rdx, r15; unsigned __int64
0x1800d4f8b  mov     rcx, rdi; this
0x1800d4f8e  call    ?GetPackageFullName@PackageFilter@@QEBAPEBG_K@Z; PackageFilter::GetPackageFullName(unsigned __int64)
0x1800d4f93  mov     rcx, [rbp+47h+string]; string
0x1800d4f97  xor     edx, edx; length
0x1800d4f99  mov     rbx, rax
0x1800d4f9c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d4fa2  mov     rcx, rax; unsigned __int16 *
0x1800d4fa5  mov     rdx, rbx; unsigned __int16 *
0x1800d4fa8  call    ?PackageNamesMatch@@YA_NPEBG0@Z; PackageNamesMatch(ushort const *,ushort const *)
0x1800d4fad  test    al, al
0x1800d4faf  jnz     short loc_1800D4FC5
0x1800d4fb1  inc     r15
0x1800d4fb4  jmp     short loc_1800D4F7B
0x1800d4fb6  mov     rcx, [rbp+47h+string]; string
0x1800d4fba  call    cs:__imp_WindowsDeleteString
0x1800d4fc0  xor     r15d, r15d
0x1800d4fc3  jmp     short loc_1800D5037
0x1800d4fc5  xor     r15d, r15d
0x1800d4fc8  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800d4fcc  lea     rdx, [rbp+47h+string]
0x1800d4fd0  mov     word ptr [rbp+47h+var_70+1], ax
0x1800d4fd4  mov     rcx, rsi
0x1800d4fd7  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800d4fda  mov     byte ptr [rbp+47h+var_70+3], al
0x1800d4fdd  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800d4fe1  mov     word ptr [rbp+47h+var_68+1], ax
0x1800d4fe5  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800d4fe8  mov     byte ptr [rbp+47h+var_68+3], al
0x1800d4feb  movzx   eax, word ptr [rbp+47h+var_80+1]
0x1800d4fef  mov     word ptr [rbp+47h+var_78+1], ax
0x1800d4ff3  mov     al, byte ptr [rbp+47h+var_80+3]
0x1800d4ff6  mov     byte ptr [rbp+47h+var_78+3], al
0x1800d4ff9  mov     byte ptr [rbp+47h+var_70], r15b
0x1800d4ffd  mov     dword ptr [rbp+47h+var_70+4], r15d
0x1800d5001  mov     rax, [rbp+47h+var_70]
0x1800d5005  mov     byte ptr [rbp+47h+var_68], r15b
0x1800d5009  mov     dword ptr [rbp+47h+var_68+4], r15d
0x1800d500d  mov     r9, [rbp+47h+var_68]
0x1800d5011  mov     byte ptr [rbp+47h+var_78], r15b
0x1800d5015  mov     dword ptr [rbp+47h+var_78+4], r15d
0x1800d5019  mov     r8, [rbp+47h+var_78]
0x1800d501d  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800d5022  call    ?AddPackage@PackageListBuffer@@QEAAJAEBVOpaqueString@@U?$Optional@I@@11@Z; PackageListBuffer::AddPackage(OpaqueString const &,Optional<uint>,Optional<uint>,Optional<uint>)
0x1800d5027  mov     ebx, eax
0x1800d5029  test    eax, eax
0x1800d502b  js      short loc_1800D503F
0x1800d502d  mov     rcx, [rbp+47h+string]; string
0x1800d5031  call    cs:__imp_WindowsDeleteString
0x1800d5037  inc     r12d
0x1800d503a  jmp     loc_1800D4F32
0x1800d503f  mov     edx, 0F8Ah
0x1800d5044  jmp     loc_1800D5354
0x1800d5049  mov     rcx, [rbp+47h+string]; string
0x1800d504d  call    cs:__imp_WindowsDeleteString
0x1800d5053  lea     rcx, [rbp+47h+var_60]
0x1800d5057  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800d505c  mov     rbx, r15
0x1800d505f  mov     [rbp+47h+var_78], rbx
0x1800d5063  cmp     [rsi+88h], r15d
0x1800d506a  jz      short loc_1800D5080
0x1800d506c  mov     rdx, [rsi+80h]
0x1800d5073  lea     rcx, [rbp+47h+var_78]
0x1800d5077  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800d507c  mov     rbx, [rbp+47h+var_78]
0x1800d5080  cmp     [rbp+47h+arg_20], r15b
0x1800d5084  jz      loc_1800D51D0
0x1800d508a  mov     dword ptr [rbp+47h+string], r15d
0x1800d508e  test    r14, r14
0x1800d5091  jz      short loc_1800D50E8
0x1800d5093  mov     rax, [r14]
0x1800d5096  lea     r8, [rbp+47h+string]
0x1800d509a  mov     edx, 1
0x1800d509f  mov     rcx, r14
0x1800d50a2  mov     rax, [rax+60h]
0x1800d50a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d50ab  mov     edi, eax
0x1800d50ad  test    eax, eax
0x1800d50af  jns     short loc_1800D50E8
0x1800d50b1  mov     rcx, [rbp+4Fh]; this
0x1800d50b5  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d50bc  mov     r9d, eax; char *
0x1800d50bf  mov     edx, 0FB4h; void *
0x1800d50c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d50c9  mov     edx, dword ptr [rbp+47h+string]
0x1800d50cc  test    edx, edx
0x1800d50ce  jz      loc_1800D526B
0x1800d50d4  mov     rcx, [r14]
0x1800d50d7  mov     rax, [rcx+68h]
0x1800d50db  mov     rcx, r14
0x1800d50de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d50e3  jmp     loc_1800D526B
0x1800d50e8  mov     rdi, [rsi+80h]
0x1800d50ef  mov     eax, [rsi+88h]
0x1800d50f5  shl     rax, 5
0x1800d50f9  add     rax, [rsi+80h]
0x1800d5100  cmp     rdi, rax
0x1800d5103  jz      short loc_1800D5166
0x1800d5105  mov     rdx, [rdi]
0x1800d5108  lea     rax, [rdi+8]
0x1800d510c  mov     r9d, 1
0x1800d5112  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800d5117  mov     r8, r14
0x1800d511a  mov     rcx, r13
0x1800d511d  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800d5122  mov     r15d, eax
0x1800d5125  test    eax, eax
0x1800d5127  js      short loc_1800D512F
0x1800d5129  add     rdi, 20h ; ' '
0x1800d512d  jmp     short loc_1800D50EF
0x1800d512f  mov     rcx, [rbp+4Fh]; this
0x1800d5133  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d513a  mov     r9d, r15d; char *
0x1800d513d  mov     edx, 0FBAh; void *
0x1800d5142  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d5147  mov     edx, dword ptr [rbp+47h+string]
0x1800d514a  test    edx, edx
0x1800d514c  jz      loc_1800D5268
0x1800d5152  mov     rax, [r14]
0x1800d5155  mov     rcx, r14
0x1800d5158  mov     rax, [rax+68h]
0x1800d515c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5161  jmp     loc_1800D5268
0x1800d5166  mov     edx, dword ptr [rbp+47h+string]
0x1800d5169  test    edx, edx
0x1800d516b  jz      short loc_1800D517C
0x1800d516d  mov     rax, [r14]
0x1800d5170  mov     rcx, r14
0x1800d5173  mov     rax, [rax+68h]
0x1800d5177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d517c  mov     rdi, [rsi+80h]
0x1800d5183  mov     eax, [rsi+88h]
0x1800d5189  shl     rax, 5
0x1800d518d  add     rax, [rsi+80h]
0x1800d5194  cmp     rdi, rax
0x1800d5197  jz      short loc_1800D51CD
0x1800d5199  mov     rdx, [rdi]
0x1800d519c  lea     rax, [rdi+18h]
0x1800d51a0  mov     r9d, 2
0x1800d51a6  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800d51ab  mov     r8, r14
0x1800d51ae  mov     rcx, r13
0x1800d51b1  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800d51b6  mov     r15d, eax
0x1800d51b9  test    eax, eax
0x1800d51bb  js      short loc_1800D51C3
0x1800d51bd  add     rdi, 20h ; ' '
0x1800d51c1  jmp     short loc_1800D5183
0x1800d51c3  mov     edx, 0FC9h
0x1800d51c8  jmp     loc_1800D5255
0x1800d51cd  xor     r15d, r15d
0x1800d51d0  mov     rdi, [rsi+80h]
0x1800d51d7  mov     ecx, [rsi+88h]
0x1800d51dd  mov     eax, ecx
0x1800d51df  shl     rax, 5
0x1800d51e3  add     rax, [rsi+80h]
0x1800d51ea  cmp     rdi, rax
0x1800d51ed  jz      loc_1800D5284
0x1800d51f3  mov     rdx, [rdi]
0x1800d51f6  lea     r12, [rdi+10h]
0x1800d51fa  xor     r9d, r9d
0x1800d51fd  mov     qword ptr [rsp+0D0h+var_B0], r12; int
0x1800d5202  mov     r8, r14
0x1800d5205  mov     rcx, r13
0x1800d5208  call    ?TryGetComPackageInstallOrder@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEAUHSTRING__@@PEAUIUserToken@@W4InstallScope@RegistrationStoreContext@@AEAU?$Optional@I@@@Z; CPackagedComCatalog::TryGetComPackageInstallOrder(IPackagedComCatalogContext *,HSTRING__ *,IUserToken *,RegistrationStoreContext::InstallScope,Optional<uint> &)
0x1800d520d  mov     r15d, eax
0x1800d5210  test    eax, eax
0x1800d5212  js      short loc_1800D5250
0x1800d5214  xor     r15d, r15d
0x1800d5217  cmp     [rdi+8], r15b
0x1800d521b  jz      short loc_1800D5228
0x1800d521d  cmp     [rdi+18h], r15b
0x1800d5221  jz      short loc_1800D5228
0x1800d5223  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d5228  cmp     [r12], r15b
0x1800d522c  jnz     short loc_1800D524A
0x1800d522e  cmp     [rdi+8], r15b
0x1800d5232  jnz     short loc_1800D524A
0x1800d5234  cmp     [rdi+18h], r15b
0x1800d5238  jnz     short loc_1800D524A
0x1800d523a  mov     rdx, rdi; struct PackageIdAndInstallOrders *
0x1800d523d  mov     rcx, rsi; this
0x1800d5240  call    ?RemoveAt@PackageListBuffer@@QEAAPEAUPackageIdAndInstallOrders@@PEAU2@@Z; PackageListBuffer::RemoveAt(PackageIdAndInstallOrders *)
0x1800d5245  mov     rdi, rax
0x1800d5248  jmp     short loc_1800D51D7
0x1800d524a  add     rdi, 20h ; ' '
0x1800d524e  jmp     short loc_1800D51D7
0x1800d5250  mov     edx, 0FD4h; void *
0x1800d5255  mov     rcx, [rbp+4Fh]; this
0x1800d5259  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d5260  mov     r9d, r15d; char *
0x1800d5263  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d5268  mov     edi, r15d
0x1800d526b  mov     rcx, rbx; string
0x1800d526e  call    cs:__imp_WindowsDeleteString
0x1800d5274  lea     rcx, [rbp+47h+var_60]
0x1800d5278  call    ?reset@?$lambda_call@V_lambda_fdd1f03cf39401802144a19ea53258dc_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_fdd1f03cf39401802144a19ea53258dc_>::reset(void)
0x1800d527d  mov     eax, edi
0x1800d527f  jmp     loc_1800D5380
0x1800d5284  test    rbx, rbx
0x1800d5287  jz      loc_1800D5338
0x1800d528d  test    ecx, ecx
0x1800d528f  jnz     loc_1800D5338
0x1800d5295  xor     edx, edx
0x1800d5297  mov     [rbp+47h+string], r15
0x1800d529b  lea     rcx, [rbp+47h+string]
0x1800d529f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800d52a4  mov     rcx, [rbp+47h+arg_18]; string
0x1800d52a8  lea     rdx, [rbp+47h+string]; newString
0x1800d52ac  call    cs:__imp_WindowsDuplicateString
0x1800d52b2  test    eax, eax
0x1800d52b4  jns     short loc_1800D52D0
0x1800d52b6  mov     rcx, [rbp+4Fh]; this
0x1800d52ba  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d52c1  mov     r9d, eax; char *
0x1800d52c4  mov     edx, 14Bh; void *
0x1800d52c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d52ce  jmp     short loc_1800D532F
0x1800d52d0  xor     edx, edx; length
0x1800d52d2  mov     rcx, rbx; string
0x1800d52d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d52db  mov     rcx, [rbp+47h+string]; string
0x1800d52df  xor     edx, edx; length
0x1800d52e1  mov     rdi, rax
0x1800d52e4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d52ea  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800d52f1  mov     rcx, [rbp+4Fh]; this
0x1800d52f5  mov     r9d, 80040154h; char *
0x1800d52fb  mov     [rsp+0D0h+var_A0], rdi
  ... truncated ...
```
