# GetLatestPackageFullNameForLogging(IUserTokenInternal *,ushort const *,uint,ushort *)

- ea: `0x1800aa224`
- end: `0x1800aa425`
- name: `?GetLatestPackageFullNameForLogging@@YAXPEAUIUserTokenInternal@@PEBGIPEAG@Z`
- size: `513`
- prototype: `void __fastcall(struct IUserTokenInternal *, PCWSTR packageFullName, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18004ffe8`

## callees

- `0x180005c40`
- `0x18000b310`
- `0x18002ba28`
- `0x18008e98c`
- `0x18009818c`
- `0x1800aa224`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800cdda8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa2a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa343`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa3ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa2a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa343`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa3ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aa338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aa338`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x1800aa272`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x1800aa272`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800aa305`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800aa31e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800aa305`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800aa31e`

## string_xrefs

- `0x1800aa38f`: `onecore\com\combase\catalog\services.cxx`
- `0x1800aa2e0`: `onecore\com\combase\Catalog\services.hxx`
- `0x1800aa3b8`: `MultipleInstalledPackagesInFamily`
- `0x1800aa3aa`: `PackageNotInstalled`

## pseudocode

```c
void __fastcall GetLatestPackageFullNameForLogging(
        struct IUserTokenInternal *a1,
        PCWSTR packageFullName,
        __int64 a3,
        unsigned __int16 *a4)
{
  int InstalledPackageFullNameFromMainOrRelatedSetPackageFamilyName; // eax
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v12; // rcx
  int InstalledPackageFullNameFromPackageFamilyNameOld; // eax
  int v14; // [rsp+20h] [rbp-89h]
  int v15; // [rsp+20h] [rbp-89h]
  HSTRING string; // [rsp+30h] [rbp-79h] BYREF
  int v17; // [rsp+38h] [rbp-71h] BYREF
  __int64 v18; // [rsp+40h] [rbp-69h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+48h] [rbp-61h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+50h] [rbp-59h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  memset_0(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength = 65;
  if ( PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName) )
  {
    StringCchCopyW(a4, 0x80u, L"InvalidPackageName");
    return;
  }
  v17 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    WindowsDeleteString(0);
    string = 0;
    v18 = 0;
    InstalledPackageFullNameFromMainOrRelatedSetPackageFamilyName = GetInstalledPackageFullNameFromMainOrRelatedSetPackageFamilyName(
                                                                      (struct StateRepository::Cache::Manager_NoThrow *)&v18,
                                                                      a1,
                                                                      packageFamilyName,
                                                                      &string,
                                                                      (enum PackageFamilyErrorDetails *)&v17);
    v8 = InstalledPackageFullNameFromMainOrRelatedSetPackageFamilyName;
    if ( InstalledPackageFullNameFromMainOrRelatedSetPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecore\\com\\combase\\Catalog\\services.hxx",
        (const char *)(unsigned int)InstalledPackageFullNameFromMainOrRelatedSetPackageFamilyName,
        v14);
      v9 = v18;
      v18 = 0;
      if ( v9 )
        SRCacheManager_Close(v9);
      goto LABEL_9;
    }
    v10 = v18;
    v18 = 0;
    if ( v10 )
      SRCacheManager_Close(v10);
    goto LABEL_8;
  }
  WindowsDeleteString(0);
  string = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12);
  InstalledPackageFullNameFromPackageFamilyNameOld = GetInstalledPackageFullNameFromPackageFamilyNameOld(
                                                       a1,
                                                       packageFamilyName,
                                                       0x40010u,
                                                       &string,
                                                       (enum PackageFamilyErrorDetails *)&v17);
  v8 = InstalledPackageFullNameFromPackageFamilyNameOld;
  if ( InstalledPackageFullNameFromPackageFamilyNameOld >= 0 )
  {
LABEL_8:
    v8 = 0;
    goto LABEL_9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x972,
    (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
    (const char *)(unsigned int)InstalledPackageFullNameFromPackageFamilyNameOld,
    v15);
LABEL_9:
  if ( v8 >= 0 && v17 == 1 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  }
  else if ( v17 == 2 )
  {
    StringRawBuffer = L"PackageNotInstalled";
  }
  else if ( v17 == 3 )
  {
    StringRawBuffer = L"MultipleInstalledPackagesInFamily";
  }
  else
  {
    StringRawBuffer = L"InvalidPackageName";
    if ( v17 != 4 )
      StringRawBuffer = L"UnknownError";
  }
  StringCchCopyW(a4, 0x80u, StringRawBuffer);
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x1800aa224  mov     [rsp-8+arg_10], rbx
0x1800aa229  push    rbp
0x1800aa22a  push    rsi
0x1800aa22b  push    rdi
0x1800aa22c  lea     rbp, [rsp-47h]
0x1800aa231  sub     rsp, 0F0h
0x1800aa238  mov     rax, cs:__security_cookie
0x1800aa23f  xor     rax, rsp
0x1800aa242  mov     [rbp+57h+var_20], rax
0x1800aa246  mov     rbx, rdx
0x1800aa249  mov     rdi, rcx
0x1800aa24c  xor     edx, edx; Val
0x1800aa24e  lea     rcx, [rbp+57h+packageFamilyName]; void *
0x1800aa252  mov     r8d, 82h; Size
0x1800aa258  mov     rsi, r9
0x1800aa25b  call    memset_0
0x1800aa260  lea     r8, [rbp+57h+packageFamilyName]; packageFamilyName
0x1800aa264  mov     [rbp+57h+packageFamilyNameLength], 41h ; 'A'
0x1800aa26b  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x1800aa26f  mov     rcx, rbx; packageFullName
0x1800aa272  call    cs:__imp_PackageFamilyNameFromFullName
0x1800aa278  test    eax, eax
0x1800aa27a  jnz     loc_1800AA3F2
0x1800aa280  mov     [rbp+57h+string], 0
0x1800aa288  mov     [rbp+57h+var_C8], eax
0x1800aa28b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800aa292  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800aa297  mov     rcx, [rbp+57h+string]; string
0x1800aa29b  test    al, al
0x1800aa29d  jz      loc_1800AA343
0x1800aa2a3  call    cs:__imp_WindowsDeleteString
0x1800aa2a9  lea     rax, [rbp+57h+var_C8]
0x1800aa2ad  mov     [rbp+57h+string], 0
0x1800aa2b5  lea     r9, [rbp+57h+string]; HSTRING *
0x1800aa2b9  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1800aa2be  lea     r8, [rbp+57h+packageFamilyName]; unsigned __int16 *
0x1800aa2c2  mov     [rbp+57h+var_C0], 0
0x1800aa2ca  mov     rdx, rdi; struct IUserTokenInternal *
0x1800aa2cd  lea     rcx, [rbp+57h+var_C0]; struct StateRepository::Cache::Manager_NoThrow *
0x1800aa2d1  call    ?GetInstalledPackageFullNameFromMainOrRelatedSetPackageFamilyName@@YAJAEAVManager_NoThrow@Cache@StateRepository@@PEAUIUserTokenInternal@@PEBGPEAPEAUHSTRING__@@PEAW4PackageFamilyErrorDetails@@@Z; GetInstalledPackageFullNameFromMainOrRelatedSetPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,IUserTokenInternal *,ushort const *,HSTRING__ * *,PackageFamilyErrorDetails *)
0x1800aa2d6  mov     ebx, eax
0x1800aa2d8  test    eax, eax
0x1800aa2da  jns     short loc_1800AA30D
0x1800aa2dc  mov     rcx, [rbp+5Fh]; this
0x1800aa2e0  lea     r8, aOnecoreComComb_43; "onecore\\com\\combase\\Catalog\\service"...
0x1800aa2e7  mov     r9d, eax; char *
0x1800aa2ea  mov     edx, 0D0h; void *
0x1800aa2ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa2f4  mov     rcx, [rbp+57h+var_C0]
0x1800aa2f8  mov     [rbp+57h+var_C0], 0
0x1800aa300  test    rcx, rcx
0x1800aa303  jz      short loc_1800AA326
0x1800aa305  call    cs:__imp_SRCacheManager_Close
0x1800aa30b  jmp     short loc_1800AA326
0x1800aa30d  mov     rcx, [rbp+57h+var_C0]
0x1800aa311  mov     [rbp+57h+var_C0], 0
0x1800aa319  test    rcx, rcx
0x1800aa31c  jz      short loc_1800AA324
0x1800aa31e  call    cs:__imp_SRCacheManager_Close
0x1800aa324  xor     ebx, ebx
0x1800aa326  mov     ecx, [rbp+57h+var_C8]
0x1800aa329  test    ebx, ebx
0x1800aa32b  js      short loc_1800AA3A5
0x1800aa32d  cmp     ecx, 1
0x1800aa330  jnz     short loc_1800AA3A5
0x1800aa332  mov     rcx, [rbp+57h+string]; string
0x1800aa336  xor     edx, edx; length
0x1800aa338  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aa33e  jmp     loc_1800AA3D6
0x1800aa343  call    cs:__imp_WindowsDeleteString
0x1800aa349  mov     [rbp+57h+string], 0
0x1800aa351  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800aa358  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800aa35d  test    al, al
0x1800aa35f  jz      short loc_1800AA366
0x1800aa361  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800aa366  lea     rax, [rbp+57h+var_C8]
0x1800aa36a  mov     r8d, 40010h; unsigned int
0x1800aa370  lea     r9, [rbp+57h+string]; HSTRING *
0x1800aa374  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1800aa379  lea     rdx, [rbp+57h+packageFamilyName]; unsigned __int16 *
0x1800aa37d  mov     rcx, rdi; struct IUserTokenInternal *
0x1800aa380  call    ?GetInstalledPackageFullNameFromPackageFamilyNameOld@@YAJPEAUIUserTokenInternal@@PEBGIPEAPEAUHSTRING__@@PEAW4PackageFamilyErrorDetails@@@Z; GetInstalledPackageFullNameFromPackageFamilyNameOld(IUserTokenInternal *,ushort const *,uint,HSTRING__ * *,PackageFamilyErrorDetails *)
0x1800aa385  mov     ebx, eax
0x1800aa387  test    eax, eax
0x1800aa389  jns     short loc_1800AA324
0x1800aa38b  mov     rcx, [rbp+5Fh]; this
0x1800aa38f  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x1800aa396  mov     r9d, eax; char *
0x1800aa399  mov     edx, 972h; void *
0x1800aa39e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa3a3  jmp     short loc_1800AA326
0x1800aa3a5  cmp     ecx, 2
0x1800aa3a8  jnz     short loc_1800AA3B3
0x1800aa3aa  lea     rax, aPackagenotinst; "PackageNotInstalled"
0x1800aa3b1  jmp     short loc_1800AA3D6
0x1800aa3b3  cmp     ecx, 3
0x1800aa3b6  jnz     short loc_1800AA3C1
0x1800aa3b8  lea     rax, aMultipleinstal; "MultipleInstalledPackagesInFamily"
0x1800aa3bf  jmp     short loc_1800AA3D6
0x1800aa3c1  cmp     ecx, 4
0x1800aa3c4  lea     rax, aInvalidpackage; "InvalidPackageName"
0x1800aa3cb  lea     rdx, aUnknownerror; "UnknownError"
0x1800aa3d2  cmovnz  rax, rdx
0x1800aa3d6  mov     r8, rax; unsigned __int16 *
0x1800aa3d9  mov     edx, 80h; unsigned __int64
0x1800aa3de  mov     rcx, rsi; unsigned __int16 *
0x1800aa3e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800aa3e6  mov     rcx, [rbp+57h+string]; string
0x1800aa3ea  call    cs:__imp_WindowsDeleteString
0x1800aa3f0  jmp     short loc_1800AA406
0x1800aa3f2  lea     r8, aInvalidpackage; "InvalidPackageName"
0x1800aa3f9  mov     edx, 80h; unsigned __int64
0x1800aa3fe  mov     rcx, rsi; unsigned __int16 *
0x1800aa401  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800aa406  mov     rcx, [rbp+57h+var_20]
0x1800aa40a  xor     rcx, rsp; StackCookie
0x1800aa40d  call    __security_check_cookie
0x1800aa412  mov     rbx, [rsp+100h+arg_10]
0x1800aa41a  add     rsp, 0F0h
0x1800aa421  pop     rdi
0x1800aa422  pop     rsi
0x1800aa423  pop     rbp
0x1800aa424  retn
```
