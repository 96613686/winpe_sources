# CPackagedComCatalog::CPackagedComProgIdIterator::Next(HSTRING__ * *,_GUID *)

- ea: `0x1800ead10`
- end: `0x1800eafbd`
- name: `?Next@CPackagedComProgIdIterator@CPackagedComCatalog@@UEAAJPEAPEAUHSTRING__@@PEAU_GUID@@@Z`
- size: `685`
- prototype: `__int64 __fastcall(CPackagedComCatalog::CPackagedComProgIdIterator *__hidden this, HSTRING *, struct _GUID *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800065a4`
- `0x1800210f8`
- `0x1800a9c84`
- `0x1800b7ac0`
- `0x1800dd8cc`
- `0x1800ead10`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ead78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eae20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eae7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eae8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaea2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaeb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaeed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaf01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaf34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaf48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaf80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ead78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eae20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eae7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eae8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaea2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaeb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaeed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaf01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaf34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaf48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eaf80`

## string_xrefs

- `0x1800eaf68`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::CPackagedComProgIdIterator::Next(
        CPackagedComCatalog::CPackagedComProgIdIterator *this,
        HSTRING *a2,
        struct _GUID *a3)
{
  HSTRING v6; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64, _BYTE *); // rbx
  __int64 v9; // r8
  int v10; // eax
  unsigned int v11; // ebx
  char IsEnabled; // al
  char v13; // di
  __int64 v14; // r12
  HSTRING v15; // rbx
  int v16; // r8d
  HSTRING v17; // rcx
  int v19; // r8d
  HSTRING v20; // rcx
  int v21; // [rsp+30h] [rbp-79h]
  _BYTE v22[8]; // [rsp+50h] [rbp-59h] BYREF
  HSTRING string; // [rsp+58h] [rbp-51h] BYREF
  HSTRING i; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v25[4]; // [rsp+70h] [rbp-39h] BYREF
  struct _GUID v26; // [rsp+74h] [rbp-35h]
  int v27; // [rsp+84h] [rbp-25h]
  char v28; // [rsp+88h] [rbp-21h]
  HSTRING v29; // [rsp+90h] [rbp-19h]
  int v30; // [rsp+98h] [rbp-11h]
  char v31; // [rsp+9Ch] [rbp-Dh]
  int v32; // [rsp+A0h] [rbp-9h]
  char v33; // [rsp+A4h] [rbp-5h]
  int v34; // [rsp+A8h] [rbp-1h]
  char v35; // [rsp+ACh] [rbp+3h]
  __int64 v36; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *a2 = 0;
  *a3 = GUID_NULL;
  if ( !*((_QWORD *)this + 3) )
    return 2147942659LL;
  v6 = 0;
  v22[0] = 0;
  for ( i = 0; ; v6 = i )
  {
    v7 = *((_QWORD *)this + 2);
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v7 + 392LL);
    WindowsDeleteString(v6);
    v9 = *((unsigned int *)this + 8);
    i = 0;
    *((_DWORD *)this + 8) = v9 + 1;
    v10 = v8(v7, *((_QWORD *)this + 3), v9, v22);
    v11 = v10;
    if ( v10 < 0 )
      break;
    if ( !v22[0] )
    {
      v11 = -2147024637;
      goto LABEL_15;
    }
    v25[0] = 0;
    v28 = 0;
    v26 = 0;
    v27 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    string = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v13 = *((_BYTE *)this + 36);
    v14 = *((_QWORD *)this + 2);
    v15 = i;
    if ( IsEnabled )
    {
      WindowsDeleteString(string);
      string = 0;
      if ( (int)CPackagedComCatalog::EntryLookup::ResolveAndReadEntry<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &)>(
                  (unsigned int)v25,
                  (unsigned int)&string,
                  v16,
                  v14,
                  (__int64)v15,
                  v13,
                  v21) >= 0
        && v25[0] )
      {
        v17 = string;
        *a2 = i;
        *a3 = v26;
        i = 0;
        WindowsDeleteString(v17);
        string = 0;
        WindowsDeleteString(v29);
        v29 = 0;
        WindowsDeleteString(i);
        return 0;
      }
    }
    else
    {
      WindowsDeleteString(string);
      string = 0;
      if ( (int)CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(
                  (unsigned int)v25,
                  (unsigned int)&string,
                  v19,
                  v14,
                  (__int64)v15,
                  v13) >= 0
        && v25[0] )
      {
        v20 = string;
        *a2 = i;
        *a3 = v26;
        i = 0;
        WindowsDeleteString(v20);
        string = 0;
        WindowsDeleteString(v29);
        v29 = 0;
        v11 = 0;
        goto LABEL_15;
      }
    }
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v29);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x698,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)v10,
    (int)&i);
LABEL_15:
  WindowsDeleteString(i);
  return v11;
}

```

## disassembly

```asm
0x1800ead10  mov     [rsp-8+arg_18], rbx
0x1800ead15  push    rbp
0x1800ead16  push    rsi
0x1800ead17  push    rdi
0x1800ead18  push    r12
0x1800ead1a  push    r13
0x1800ead1c  push    r14
0x1800ead1e  push    r15
0x1800ead20  lea     rbp, [rsp-27h]
0x1800ead25  sub     rsp, 0D0h
0x1800ead2c  mov     rax, cs:__security_cookie
0x1800ead33  xor     rax, rsp
0x1800ead36  mov     [rbp+57h+var_40], rax
0x1800ead3a  xor     r13d, r13d
0x1800ead3d  mov     rsi, r8
0x1800ead40  mov     [rdx], r13
0x1800ead43  mov     r15, rdx
0x1800ead46  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800ead4d  mov     r14, rcx
0x1800ead50  movdqu  xmmword ptr [r8], xmm0
0x1800ead55  cmp     [rcx+18h], r13
0x1800ead59  jz      loc_1800EAF90
0x1800ead5f  mov     ecx, r13d; string
0x1800ead62  mov     [rbp+57h+var_B0], r13b
0x1800ead66  mov     [rbp+57h+var_A0], rcx
0x1800ead6a  mov     rdi, [r14+10h]
0x1800ead6e  mov     rax, [rdi]
0x1800ead71  mov     rbx, [rax+188h]
0x1800ead78  call    cs:__imp_WindowsDeleteString
0x1800ead7f  nop     dword ptr [rax+rax+00h]
0x1800ead84  mov     r8d, [r14+20h]
0x1800ead88  lea     rax, [rbp+57h+var_A0]
0x1800ead8c  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1800ead91  lea     r9, [rbp+57h+var_B0]
0x1800ead95  mov     rcx, rdi
0x1800ead98  mov     [rbp+57h+var_A0], r13
0x1800ead9c  mov     rax, rbx
0x1800ead9f  lea     edx, [r8+1]
0x1800eada3  mov     [r14+20h], edx
0x1800eada7  mov     rdx, [r14+18h]
0x1800eadab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eadb0  mov     ebx, eax
0x1800eadb2  test    eax, eax
0x1800eadb4  js      loc_1800EAF64
0x1800eadba  cmp     [rbp+57h+var_B0], r13b
0x1800eadbe  jz      loc_1800EAF5D
0x1800eadc4  xorps   xmm0, xmm0
0x1800eadc7  mov     [rbp+57h+var_90], r13b
0x1800eadcb  xor     eax, eax
0x1800eadcd  mov     [rbp+57h+var_78], r13b
0x1800eadd1  movups  [rbp+57h+var_8C], xmm0
0x1800eadd5  mov     [rbp+57h+var_7C], eax
0x1800eadd8  mov     [rbp+57h+var_70], r13
0x1800eaddc  mov     [rbp+57h+var_68], r13d
0x1800eade0  mov     [rbp+57h+var_64], r13b
0x1800eade4  mov     [rbp+57h+var_60], r13d
0x1800eade8  mov     [rbp+57h+var_5C], r13b
0x1800eadec  mov     [rbp+57h+var_58], r13d
0x1800eadf0  mov     [rbp+57h+var_54], r13b
0x1800eadf4  mov     [rbp+57h+var_50], r13
0x1800eadf8  mov     [rbp+57h+string], r13
0x1800eadfc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800eae03  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800eae08  mov     dil, [r14+24h]
0x1800eae0c  mov     r12, [r14+10h]
0x1800eae10  mov     rbx, [rbp+57h+var_A0]
0x1800eae14  mov     rcx, [rbp+57h+string]; string
0x1800eae18  test    al, al
0x1800eae1a  jz      loc_1800EAEB5
0x1800eae20  call    cs:__imp_WindowsDeleteString
0x1800eae27  nop     dword ptr [rax+rax+00h]
0x1800eae2c  mov     r9, r12
0x1800eae2f  mov     [rsp+100h+var_D8], dil
0x1800eae34  lea     rdx, [rbp+57h+string]
0x1800eae38  mov     [rbp+57h+string], r13
0x1800eae3c  lea     rcx, [rbp+57h+var_90]
0x1800eae40  mov     qword ptr [rsp+100h+var_E0], rbx
0x1800eae45  call    ??$ResolveAndReadEntry@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU3@_NW4ComRegistrationVisibility@@PEBVPackageFilter@@PEAVMainPackageFamilyNameFilter@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@Z@Z; CPackagedComCatalog::EntryLookup::ResolveAndReadEntry<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,ComRegistrationVisibility,PackageFilter const *,MainPackageFamilyNameFilter *,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &))
0x1800eae4a  test    eax, eax
0x1800eae4c  js      loc_1800EAEE9
0x1800eae52  cmp     [rbp+57h+var_90], r13b
0x1800eae56  jz      loc_1800EAEE9
0x1800eae5c  mov     rax, [rbp+57h+var_A0]
0x1800eae60  mov     rcx, [rbp+57h+string]; string
0x1800eae64  mov     [r15], rax
0x1800eae67  mov     rax, qword ptr [rbp+57h+var_8C]
0x1800eae6b  mov     [rsi], rax
0x1800eae6e  mov     rax, qword ptr [rbp+57h+var_8C+8]
0x1800eae72  mov     [rsi+8], rax
0x1800eae76  mov     [rbp+57h+var_A0], r13
0x1800eae7a  call    cs:__imp_WindowsDeleteString
0x1800eae81  nop     dword ptr [rax+rax+00h]
0x1800eae86  mov     rcx, [rbp+57h+var_70]; string
0x1800eae8a  mov     [rbp+57h+string], r13
0x1800eae8e  call    cs:__imp_WindowsDeleteString
0x1800eae95  nop     dword ptr [rax+rax+00h]
0x1800eae9a  mov     rcx, [rbp+57h+var_A0]; string
0x1800eae9e  mov     [rbp+57h+var_70], r13
0x1800eaea2  call    cs:__imp_WindowsDeleteString
0x1800eaea9  nop     dword ptr [rax+rax+00h]
0x1800eaeae  xor     eax, eax
0x1800eaeb0  jmp     loc_1800EAF95
0x1800eaeb5  call    cs:__imp_WindowsDeleteString
0x1800eaebc  nop     dword ptr [rax+rax+00h]
0x1800eaec1  mov     r9, r12
0x1800eaec4  mov     [rsp+100h+var_D8], dil
0x1800eaec9  lea     rdx, [rbp+57h+string]
0x1800eaecd  mov     [rbp+57h+string], r13
0x1800eaed1  lea     rcx, [rbp+57h+var_90]
0x1800eaed5  mov     qword ptr [rsp+100h+var_E0], rbx
0x1800eaeda  call    ??$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU2@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))
0x1800eaedf  test    eax, eax
0x1800eaee1  js      short loc_1800EAEE9
0x1800eaee3  cmp     [rbp+57h+var_90], r13b
0x1800eaee7  jnz     short loc_1800EAF16
0x1800eaee9  mov     rcx, [rbp+57h+string]; string
0x1800eaeed  call    cs:__imp_WindowsDeleteString
0x1800eaef4  nop     dword ptr [rax+rax+00h]
0x1800eaef9  mov     rcx, [rbp+57h+var_70]; string
0x1800eaefd  mov     [rbp+57h+string], r13
0x1800eaf01  call    cs:__imp_WindowsDeleteString
0x1800eaf08  nop     dword ptr [rax+rax+00h]
0x1800eaf0d  mov     rcx, [rbp+57h+var_A0]
0x1800eaf11  jmp     loc_1800EAD6A
0x1800eaf16  mov     rax, [rbp+57h+var_A0]
0x1800eaf1a  mov     rcx, [rbp+57h+string]; string
0x1800eaf1e  mov     [r15], rax
0x1800eaf21  mov     rax, qword ptr [rbp+57h+var_8C]
0x1800eaf25  mov     [rsi], rax
0x1800eaf28  mov     rax, qword ptr [rbp+57h+var_8C+8]
0x1800eaf2c  mov     [rsi+8], rax
0x1800eaf30  mov     [rbp+57h+var_A0], r13
0x1800eaf34  call    cs:__imp_WindowsDeleteString
0x1800eaf3b  nop     dword ptr [rax+rax+00h]
0x1800eaf40  mov     rcx, [rbp+57h+var_70]; string
0x1800eaf44  mov     [rbp+57h+string], r13
0x1800eaf48  call    cs:__imp_WindowsDeleteString
0x1800eaf4f  nop     dword ptr [rax+rax+00h]
0x1800eaf54  mov     [rbp+57h+var_70], r13
0x1800eaf58  mov     ebx, r13d
0x1800eaf5b  jmp     short loc_1800EAF7C
0x1800eaf5d  mov     ebx, 80070103h
0x1800eaf62  jmp     short loc_1800EAF7C
0x1800eaf64  mov     rcx, [rbp+5Fh]; this
0x1800eaf68  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800eaf6f  mov     r9d, eax; char *
0x1800eaf72  mov     edx, 698h; void *
0x1800eaf77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eaf7c  mov     rcx, [rbp+57h+var_A0]; string
0x1800eaf80  call    cs:__imp_WindowsDeleteString
0x1800eaf87  nop     dword ptr [rax+rax+00h]
0x1800eaf8c  mov     eax, ebx
0x1800eaf8e  jmp     short loc_1800EAF95
0x1800eaf90  mov     eax, 80070103h
0x1800eaf95  mov     rcx, [rbp+57h+var_40]
0x1800eaf99  xor     rcx, rsp; StackCookie
0x1800eaf9c  call    __security_check_cookie
0x1800eafa1  mov     rbx, [rsp+100h+arg_18]
0x1800eafa9  add     rsp, 0D0h
0x1800eafb0  pop     r15
0x1800eafb2  pop     r14
0x1800eafb4  pop     r13
0x1800eafb6  pop     r12
0x1800eafb8  pop     rdi
0x1800eafb9  pop     rsi
0x1800eafba  pop     rbp
0x1800eafbb  retn
```
