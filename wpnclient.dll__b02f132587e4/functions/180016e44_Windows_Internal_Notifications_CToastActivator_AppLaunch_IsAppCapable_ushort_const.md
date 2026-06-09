# Windows::Internal::Notifications::CToastActivator_AppLaunch::IsAppCapable(ushort const *)

- ea: `0x180016e44`
- end: `0x180016fcb`
- name: `?IsAppCapable@CToastActivator_AppLaunch@Notifications@Internal@Windows@@AEAA_NPEBG@Z`
- size: `391`
- prototype: `bool(Windows::Internal::Notifications::CToastActivator_AppLaunch *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800138f0`
- `0x180013f50`

## callees

- `0x1800064c0`
- `0x180016e44`
- `0x180016fd4`
- `0x18001b848`
- `0x18001ff00`
- `0x180025aa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180016e6e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180016e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016f9c`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180016f36`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180016f36`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Windows::Internal::Notifications::CToastActivator_AppLaunch::IsAppCapable(
        Windows::Internal::Notifications::CToastActivator_AppLaunch *this,
        const unsigned __int16 *a2)
{
  wchar_t *v3; // rax
  int v4; // eax
  WCHAR *v5; // rbx
  unsigned int PackagesByPackageFamily; // eax
  char v7; // di
  const char *v8; // r9
  char result; // al
  int bufferLength; // [rsp+20h] [rbp-168h]
  unsigned int bufferLengtha; // [rsp+20h] [rbp-168h]
  UINT32 count; // [rsp+40h] [rbp-148h] BYREF
  UINT32 v13; // [rsp+44h] [rbp-144h] BYREF
  PWSTR packageFullNames; // [rsp+48h] [rbp-140h] BYREF
  PCWSTR packageFamilyName[4]; // [rsp+50h] [rbp-138h] BYREF
  WCHAR buffer[128]; // [rsp+70h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v3 = wcschr(a2, 0x21u);
  try
  {
    if ( !v3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_applaunch.cpp",
        (const char *)0x80070490LL,
        bufferLength);
    memset(packageFamilyName, 0, 24);
    v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           (__int64)packageFamilyName,
           (unsigned __int64)a2,
           v3 - a2);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_applaunch.cpp",
        (const char *)(unsigned int)v4,
        bufferLength);
    packageFullNames = 0;
    v13 = 128;
    count = 1;
    v5 = (WCHAR *)packageFamilyName[0];
    PackagesByPackageFamily = FindPackagesByPackageFamily(
                                packageFamilyName[0],
                                0x10u,
                                &count,
                                &packageFullNames,
                                &v13,
                                buffer,
                                0);
    if ( PackagesByPackageFamily )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_applaunch.cpp",
        (const char *)PackagesByPackageFamily,
        bufferLengtha);
    if ( count != 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_applaunch.cpp",
        (const char *)0x8000FFFFLL,
        bufferLengtha);
    v7 = AppLaunchEnforcer::VerifyAppLaunchAllowed(retaddr, packageFullNames);
    if ( v5 )
      CoTaskMemFree(v5);
    result = v7;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_applaunch.cpp",
      v8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180016e44  mov     [rsp+arg_0], rbx
0x180016e49  push    rdi
0x180016e4a  sub     rsp, 180h
0x180016e51  mov     rax, cs:__security_cookie
0x180016e58  xor     rax, rsp
0x180016e5b  mov     [rsp+188h+var_18], rax
0x180016e63  mov     rbx, rdx
0x180016e66  mov     edx, 21h ; '!'; Ch
0x180016e6b  mov     rcx, rbx; Str
0x180016e6e  call    cs:__imp_wcschr
0x180016e74  mov     rcx, [rsp+188h]; this
0x180016e7c  test    rax, rax
0x180016e7f  jnz     short loc_180016E98
0x180016e81  mov     r9d, 80070490h; char *
0x180016e87  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180016e8e  mov     edx, 8Ch; void *
0x180016e93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016e98  mov     [rsp+188h+packageFamilyName], 0
0x180016ea1  mov     [rsp+188h+var_130], 0
0x180016eaa  mov     [rsp+188h+var_128], 0
0x180016eb3  sub     rax, rbx
0x180016eb6  sar     rax, 1
0x180016eb9  mov     r8, rax
0x180016ebc  mov     rdx, rbx
0x180016ebf  lea     rcx, [rsp+188h+packageFamilyName]
0x180016ec4  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180016ec9  mov     rcx, [rsp+188h]; this
0x180016ed1  test    eax, eax
0x180016ed3  jns     short loc_180016EE9
0x180016ed5  mov     r9d, eax; char *
0x180016ed8  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180016edf  mov     edx, 8Fh; void *
0x180016ee4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016ee9  mov     [rsp+188h+packageFullNames], 0
0x180016ef2  mov     [rsp+188h+var_144], 80h
0x180016efa  mov     [rsp+188h+count], 1
0x180016f02  mov     [rsp+188h+packageProperties], 0; packageProperties
0x180016f0b  lea     rax, [rsp+188h+var_118]
0x180016f10  mov     [rsp+188h+buffer], rax; buffer
0x180016f15  lea     rax, [rsp+188h+var_144]
0x180016f1a  mov     [rsp+188h+bufferLength], rax; int
0x180016f1f  lea     r9, [rsp+188h+packageFullNames]; packageFullNames
0x180016f24  lea     r8, [rsp+188h+count]; count
0x180016f29  mov     edx, 10h; packageFilters
0x180016f2e  mov     rbx, [rsp+188h+packageFamilyName]
0x180016f33  mov     rcx, rbx; packageFamilyName
0x180016f36  call    cs:__imp_FindPackagesByPackageFamily
0x180016f3c  mov     rcx, [rsp+188h]; this
0x180016f44  test    eax, eax
0x180016f46  jz      short loc_180016F5C
0x180016f48  mov     r9d, eax; char *
0x180016f4b  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180016f52  mov     edx, 9Dh; void *
0x180016f57  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180016f5c  cmp     [rsp+188h+count], 1
0x180016f61  setz    al
0x180016f64  mov     rcx, [rsp+188h]; this
0x180016f6c  test    al, al
0x180016f6e  jnz     short loc_180016F87
0x180016f70  mov     r9d, 8000FFFFh; char *
0x180016f76  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180016f7d  mov     edx, 9Fh; void *
0x180016f82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016f87  mov     rdx, [rsp+188h+packageFullNames]; unsigned __int16 *
0x180016f8c  call    ?VerifyAppLaunchAllowed@AppLaunchEnforcer@@QEAA_NPEBG@Z; AppLaunchEnforcer::VerifyAppLaunchAllowed(ushort const *)
0x180016f91  mov     dil, al
0x180016f94  test    rbx, rbx
0x180016f97  jz      short loc_180016FA2
0x180016f99  mov     rcx, rbx; pv
0x180016f9c  call    cs:__imp_CoTaskMemFree
0x180016fa2  mov     al, dil
0x180016fa5  jmp     short loc_180016FA9
0x180016fa7  xor     al, al
0x180016fa9  mov     rcx, [rsp+188h+var_18]
0x180016fb1  xor     rcx, rsp; StackCookie
0x180016fb4  call    __security_check_cookie
0x180016fb9  mov     rbx, [rsp+188h+arg_0]
0x180016fc1  add     rsp, 180h
0x180016fc8  pop     rdi
0x180016fc9  retn
```
