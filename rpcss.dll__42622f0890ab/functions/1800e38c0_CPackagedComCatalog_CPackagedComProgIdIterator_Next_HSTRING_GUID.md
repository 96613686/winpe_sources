# CPackagedComCatalog::CPackagedComProgIdIterator::Next(HSTRING__ * *,_GUID *)

- ea: `0x1800e38c0`
- end: `0x1800e3b1e`
- name: `?Next@CPackagedComProgIdIterator@CPackagedComCatalog@@UEAAJPEAPEAUHSTRING__@@PEAU_GUID@@@Z`
- size: `606`
- prototype: `__int64 __fastcall(CPackagedComCatalog::CPackagedComProgIdIterator *__hidden this, HSTRING *, struct _GUID *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005c40`
- `0x18002ba28`
- `0x1800a4cc4`
- `0x1800b27e0`
- `0x1800d6ca4`
- `0x1800e38c0`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e39c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3ab6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3ae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e39c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3ab6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3ae8`

## string_xrefs

- `0x1800e3ad0`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

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
  __int64 v16; // r8
  HSTRING v17; // rcx
  __int64 v19; // r8
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
                  (__int64)v25,
                  (__int64)&string,
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
                  (int)v25,
                  (int)&string,
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
0x1800e38c0  mov     [rsp-8+arg_18], rbx
0x1800e38c5  push    rbp
0x1800e38c6  push    rsi
0x1800e38c7  push    rdi
0x1800e38c8  push    r12
0x1800e38ca  push    r13
0x1800e38cc  push    r14
0x1800e38ce  push    r15
0x1800e38d0  lea     rbp, [rsp-27h]
0x1800e38d5  sub     rsp, 0D0h
0x1800e38dc  mov     rax, cs:__security_cookie
0x1800e38e3  xor     rax, rsp
0x1800e38e6  mov     [rbp+57h+var_40], rax
0x1800e38ea  xor     r13d, r13d
0x1800e38ed  mov     rsi, r8
0x1800e38f0  mov     [rdx], r13
0x1800e38f3  mov     r15, rdx
0x1800e38f6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800e38fd  mov     r14, rcx
0x1800e3900  movdqu  xmmword ptr [r8], xmm0
0x1800e3905  cmp     [rcx+18h], r13
0x1800e3909  jz      loc_1800E3AF2
0x1800e390f  mov     ecx, r13d; string
0x1800e3912  mov     [rbp+57h+var_B0], r13b
0x1800e3916  mov     [rbp+57h+var_A0], rcx
0x1800e391a  mov     rdi, [r14+10h]
0x1800e391e  mov     rax, [rdi]
0x1800e3921  mov     rbx, [rax+188h]
0x1800e3928  call    cs:__imp_WindowsDeleteString
0x1800e392e  mov     r8d, [r14+20h]
0x1800e3932  lea     rax, [rbp+57h+var_A0]
0x1800e3936  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1800e393b  lea     r9, [rbp+57h+var_B0]
0x1800e393f  mov     rcx, rdi
0x1800e3942  mov     [rbp+57h+var_A0], r13
0x1800e3946  mov     rax, rbx
0x1800e3949  lea     edx, [r8+1]
0x1800e394d  mov     [r14+20h], edx
0x1800e3951  mov     rdx, [r14+18h]
0x1800e3955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e395a  mov     ebx, eax
0x1800e395c  test    eax, eax
0x1800e395e  js      loc_1800E3ACC
0x1800e3964  cmp     [rbp+57h+var_B0], r13b
0x1800e3968  jz      loc_1800E3AC5
0x1800e396e  xorps   xmm0, xmm0
0x1800e3971  mov     [rbp+57h+var_90], r13b
0x1800e3975  xor     eax, eax
0x1800e3977  mov     [rbp+57h+var_78], r13b
0x1800e397b  movups  [rbp+57h+var_8C], xmm0
0x1800e397f  mov     [rbp+57h+var_7C], eax
0x1800e3982  mov     [rbp+57h+var_70], r13
0x1800e3986  mov     [rbp+57h+var_68], r13d
0x1800e398a  mov     [rbp+57h+var_64], r13b
0x1800e398e  mov     [rbp+57h+var_60], r13d
0x1800e3992  mov     [rbp+57h+var_5C], r13b
0x1800e3996  mov     [rbp+57h+var_58], r13d
0x1800e399a  mov     [rbp+57h+var_54], r13b
0x1800e399e  mov     [rbp+57h+var_50], r13
0x1800e39a2  mov     [rbp+57h+string], r13
0x1800e39a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800e39ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800e39b2  mov     dil, [r14+24h]
0x1800e39b6  mov     r12, [r14+10h]
0x1800e39ba  mov     rbx, [rbp+57h+var_A0]
0x1800e39be  mov     rcx, [rbp+57h+string]; string
0x1800e39c2  test    al, al
0x1800e39c4  jz      short loc_1800E3A3B
0x1800e39c6  call    cs:__imp_WindowsDeleteString
0x1800e39cc  mov     r9, r12
0x1800e39cf  mov     [rsp+100h+var_D8], dil
0x1800e39d4  lea     rdx, [rbp+57h+string]
0x1800e39d8  mov     [rbp+57h+string], r13
0x1800e39dc  lea     rcx, [rbp+57h+var_90]
0x1800e39e0  mov     qword ptr [rsp+100h+var_E0], rbx
0x1800e39e5  call    ??$ResolveAndReadEntry@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU3@_NW4ComRegistrationVisibility@@PEBVPackageFilter@@PEAVMainPackageFamilyNameFilter@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@Z@Z; CPackagedComCatalog::EntryLookup::ResolveAndReadEntry<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,ComRegistrationVisibility,PackageFilter const *,MainPackageFamilyNameFilter *,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &))
0x1800e39ea  test    eax, eax
0x1800e39ec  js      short loc_1800E3A69
0x1800e39ee  cmp     [rbp+57h+var_90], r13b
0x1800e39f2  jz      short loc_1800E3A69
0x1800e39f4  mov     rax, [rbp+57h+var_A0]
0x1800e39f8  mov     rcx, [rbp+57h+string]; string
0x1800e39fc  mov     [r15], rax
0x1800e39ff  mov     rax, qword ptr [rbp+57h+var_8C]
0x1800e3a03  mov     [rsi], rax
0x1800e3a06  mov     rax, qword ptr [rbp+57h+var_8C+8]
0x1800e3a0a  mov     [rsi+8], rax
0x1800e3a0e  mov     [rbp+57h+var_A0], r13
0x1800e3a12  call    cs:__imp_WindowsDeleteString
0x1800e3a18  mov     rcx, [rbp+57h+var_70]; string
0x1800e3a1c  mov     [rbp+57h+string], r13
0x1800e3a20  call    cs:__imp_WindowsDeleteString
0x1800e3a26  mov     rcx, [rbp+57h+var_A0]; string
0x1800e3a2a  mov     [rbp+57h+var_70], r13
0x1800e3a2e  call    cs:__imp_WindowsDeleteString
0x1800e3a34  xor     eax, eax
0x1800e3a36  jmp     loc_1800E3AF7
0x1800e3a3b  call    cs:__imp_WindowsDeleteString
0x1800e3a41  mov     r9, r12
0x1800e3a44  mov     [rsp+100h+var_D8], dil
0x1800e3a49  lea     rdx, [rbp+57h+string]
0x1800e3a4d  mov     [rbp+57h+string], r13
0x1800e3a51  lea     rcx, [rbp+57h+var_90]
0x1800e3a55  mov     qword ptr [rsp+100h+var_E0], rbx
0x1800e3a5a  call    ??$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU2@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))
0x1800e3a5f  test    eax, eax
0x1800e3a61  js      short loc_1800E3A69
0x1800e3a63  cmp     [rbp+57h+var_90], r13b
0x1800e3a67  jnz     short loc_1800E3A8A
0x1800e3a69  mov     rcx, [rbp+57h+string]; string
0x1800e3a6d  call    cs:__imp_WindowsDeleteString
0x1800e3a73  mov     rcx, [rbp+57h+var_70]; string
0x1800e3a77  mov     [rbp+57h+string], r13
0x1800e3a7b  call    cs:__imp_WindowsDeleteString
0x1800e3a81  mov     rcx, [rbp+57h+var_A0]
0x1800e3a85  jmp     loc_1800E391A
0x1800e3a8a  mov     rax, [rbp+57h+var_A0]
0x1800e3a8e  mov     rcx, [rbp+57h+string]; string
0x1800e3a92  mov     [r15], rax
0x1800e3a95  mov     rax, qword ptr [rbp+57h+var_8C]
0x1800e3a99  mov     [rsi], rax
0x1800e3a9c  mov     rax, qword ptr [rbp+57h+var_8C+8]
0x1800e3aa0  mov     [rsi+8], rax
0x1800e3aa4  mov     [rbp+57h+var_A0], r13
0x1800e3aa8  call    cs:__imp_WindowsDeleteString
0x1800e3aae  mov     rcx, [rbp+57h+var_70]; string
0x1800e3ab2  mov     [rbp+57h+string], r13
0x1800e3ab6  call    cs:__imp_WindowsDeleteString
0x1800e3abc  mov     [rbp+57h+var_70], r13
0x1800e3ac0  mov     ebx, r13d
0x1800e3ac3  jmp     short loc_1800E3AE4
0x1800e3ac5  mov     ebx, 80070103h
0x1800e3aca  jmp     short loc_1800E3AE4
0x1800e3acc  mov     rcx, [rbp+5Fh]; this
0x1800e3ad0  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e3ad7  mov     r9d, eax; char *
0x1800e3ada  mov     edx, 698h; void *
0x1800e3adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3ae4  mov     rcx, [rbp+57h+var_A0]; string
0x1800e3ae8  call    cs:__imp_WindowsDeleteString
0x1800e3aee  mov     eax, ebx
0x1800e3af0  jmp     short loc_1800E3AF7
0x1800e3af2  mov     eax, 80070103h
0x1800e3af7  mov     rcx, [rbp+57h+var_40]
0x1800e3afb  xor     rcx, rsp; StackCookie
0x1800e3afe  call    __security_check_cookie
0x1800e3b03  mov     rbx, [rsp+100h+arg_18]
0x1800e3b0b  add     rsp, 0D0h
0x1800e3b12  pop     r15
0x1800e3b14  pop     r14
0x1800e3b16  pop     r13
0x1800e3b18  pop     r12
0x1800e3b1a  pop     rdi
0x1800e3b1b  pop     rsi
0x1800e3b1c  pop     rbp
0x1800e3b1d  retn
```
