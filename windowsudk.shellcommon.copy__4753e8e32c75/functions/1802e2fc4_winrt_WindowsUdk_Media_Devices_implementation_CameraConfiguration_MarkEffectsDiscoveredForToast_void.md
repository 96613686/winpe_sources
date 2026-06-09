# winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::MarkEffectsDiscoveredForToast(void)

- ea: `0x1802e2fc4`
- end: `0x1802e3318`
- name: `?MarkEffectsDiscoveredForToast@CameraConfiguration@implementation@Devices@Media@WindowsUdk@winrt@@SAXXZ`
- size: `852`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802e2fa0`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x1800795e4`
- `0x18008fc6c`
- `0x1800a8430`
- `0x1800d9dc8`
- `0x1801588c4`
- `0x1802e2fc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802e3187`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802e3187`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1802e2fe4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1802e2fe4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1802e324e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1802e324e`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1802e30cb`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1802e3137`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1802e30cb`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1802e3137`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802e3097`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802e320e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802e3097`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1802e320e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802e30ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802e30ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1802e3171`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1802e3171`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1802e3022`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1802e3022`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1802e31bb`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1802e31bb`

## string_xrefs

- `0x1802e328c`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e32a0`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e32b5`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e32ca`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e32dc`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e32f1`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3305`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::MarkEffectsDiscoveredForToast(void)
{
  bool v0; // di
  BOOL v1; // eax
  const char *v2; // r9
  HKEY *phkResult; // rax
  unsigned int v4; // eax
  HLOCAL v5; // rax
  const char *v6; // r9
  unsigned int KeySecurity; // eax
  unsigned int v8; // eax
  HKEY *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // eax
  const char *v12; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-78h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-78h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-78h]
  LPWSTR StringSecurityDescriptor; // [rsp+50h] [rbp-48h] BYREF
  struct _FILETIME v17; // [rsp+58h] [rbp-40h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-38h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  DWORD cbSecurityDescriptor; // [rsp+A0h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+B0h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B8h] [rbp+20h] BYREF

  hKey = 0;
  v17 = 0;
  *(_QWORD *)Data = 0;
  GetSystemTimeAsFileTime(&v17);
  *(struct _FILETIME *)Data = v17;
  SecurityDescriptor = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &SecurityDescriptor,
    0);
  v0 = 1;
  v1 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;KA;;;SY)(A;;KA;;;BA)(A;;KA;;;OW)(A;;KR;;;LS)(A;;KR;;;WD)",
         1u,
         &SecurityDescriptor,
         0);
  try
  {
    if ( !v1 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x174,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        v2);
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v4 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows Media Foundation\\UserCameraEffects",
           0,
           0,
           0,
           0x2001Fu,
           &SecurityAttributes,
           phkResult,
           0);
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x17D,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        (const char *)v4,
        dwOptions);
    cbSecurityDescriptor = 0;
    if ( RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor) != 122 )
      goto LABEL_12;
    pSecurityDescriptor = 0;
    do
    {
      v5 = LocalAlloc(0x40u, cbSecurityDescriptor);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &pSecurityDescriptor,
        v5);
      if ( !pSecurityDescriptor )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x18A,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
          v6);
      KeySecurity = RegGetKeySecurity(hKey, 4u, pSecurityDescriptor, &cbSecurityDescriptor);
    }
    while ( KeySecurity == 122 );
    if ( KeySecurity )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x18D,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        (const char *)KeySecurity,
        dwOptions);
    StringSecurityDescriptor = 0;
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(pSecurityDescriptor, 1u, 4u, &StringSecurityDescriptor, 0) )
      v0 = (unsigned int)_o__wcsicmp(
                           StringSecurityDescriptor,
                           L"D:(A;;KA;;;SY)(A;;KA;;;BA)(A;;KA;;;OW)(A;;KR;;;LS)(A;;KR;;;WD)") != 0;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&StringSecurityDescriptor);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pSecurityDescriptor);
    if ( v0 )
    {
LABEL_12:
      v8 = RegDeleteKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Media Foundation\\UserCameraEffects");
      if ( v8 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x19B,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
          (const char *)v8,
          dwOptions);
      v9 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
      v10 = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows Media Foundation\\UserCameraEffects",
              0,
              0,
              0,
              0x2001Fu,
              &SecurityAttributes,
              v9,
              0);
      if ( v10 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x19C,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
          (const char *)v10,
          dwOptionsa);
    }
    v11 = RegSetValueExW(hKey, L"EffectsDiscoveredToastTime", 0, 3u, Data, 8u);
    if ( v11 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x19F,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        (const char *)v11,
        dwOptionsb);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      v12);
  }
}

```

## disassembly

```asm
0x1802e2fc4  mov     rax, rsp
0x1802e2fc7  push    rsi
0x1802e2fc8  push    rdi
0x1802e2fc9  push    r12
0x1802e2fcb  sub     rsp, 80h
0x1802e2fd2  xor     esi, esi
0x1802e2fd4  mov     [rax+10h], rsi
0x1802e2fd8  mov     [rax-40h], rsi
0x1802e2fdc  mov     [rax-38h], rsi
0x1802e2fe0  lea     rcx, [rax-40h]; lpSystemTimeAsFileTime
0x1802e2fe4  call    cs:__imp_GetSystemTimeAsFileTime
0x1802e2fea  mov     rax, [rsp+98h+var_40]
0x1802e2fef  mov     qword ptr [rsp+98h+Data], rax
0x1802e2ff4  mov     [rsp+98h+SecurityDescriptor], rsi
0x1802e2ffc  xor     edx, edx
0x1802e2ffe  lea     rcx, [rsp+98h+SecurityDescriptor]
0x1802e3006  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1802e300b  xor     r9d, r9d; SecurityDescriptorSize
0x1802e300e  lea     r8, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x1802e3016  lea     edi, [rsi+1]
0x1802e3019  mov     edx, edi; StringSDRevision
0x1802e301b  lea     rcx, aDAKaSyAKaBaAKa; "D:(A;;KA;;;SY)(A;;KA;;;BA)(A;;KA;;;OW)("...
0x1802e3022  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1802e3028  mov     rcx, [rsp+98h]; this
0x1802e3030  test    eax, eax
0x1802e3032  jz      loc_1802E328C
0x1802e3038  mov     qword ptr [rsp+98h+SecurityAttributes.nLength], 18h
0x1802e3041  mov     rax, [rsp+98h+SecurityDescriptor]
0x1802e3049  mov     [rsp+98h+SecurityAttributes.lpSecurityDescriptor], rax
0x1802e304e  mov     qword ptr [rsp+98h+SecurityAttributes.bInheritHandle], rsi
0x1802e3053  lea     rcx, [rsp+98h+hKey]
0x1802e305b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1802e3060  mov     [rsp+98h+lpdwDisposition], rsi; lpdwDisposition
0x1802e3065  mov     [rsp+98h+phkResult], rax; phkResult
0x1802e306a  lea     rax, [rsp+98h+SecurityAttributes]
0x1802e306f  mov     [rsp+98h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1802e3074  mov     [rsp+98h+samDesired], 2001Fh; samDesired
0x1802e307c  mov     [rsp+98h+dwOptions], esi; unsigned int
0x1802e3080  xor     r9d, r9d; lpClass
0x1802e3083  xor     r8d, r8d; Reserved
0x1802e3086  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows Media Foun"...
0x1802e308d  mov     r12, 0FFFFFFFF80000001h
0x1802e3094  mov     rcx, r12; hKey
0x1802e3097  call    cs:__imp_RegCreateKeyExW
0x1802e309d  mov     rcx, [rsp+98h]; this
0x1802e30a5  test    eax, eax
0x1802e30a7  jnz     loc_1802E329D
0x1802e30ad  mov     [rsp+98h+cbSecurityDescriptor], esi
0x1802e30b4  lea     r9, [rsp+98h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1802e30bc  xor     r8d, r8d; pSecurityDescriptor
0x1802e30bf  lea     edx, [r8+4]; SecurityInformation
0x1802e30c3  mov     rcx, [rsp+98h+hKey]; hKey
0x1802e30cb  call    cs:__imp_RegGetKeySecurity
0x1802e30d1  cmp     eax, 7Ah ; 'z'
0x1802e30d4  jnz     loc_1802E31B1
0x1802e30da  mov     [rsp+98h+pSecurityDescriptor], rsi
0x1802e30e2  mov     edx, [rsp+98h+cbSecurityDescriptor]; uBytes
0x1802e30e9  mov     ecx, 40h ; '@'; uFlags
0x1802e30ee  call    cs:__imp_LocalAlloc
0x1802e30f4  mov     rdx, rax
0x1802e30f7  lea     rcx, [rsp+98h+pSecurityDescriptor]
0x1802e30ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1802e3104  mov     rcx, [rsp+98h]; this
0x1802e310c  cmp     [rsp+98h+pSecurityDescriptor], rsi
0x1802e3114  jz      loc_1802E32DC
0x1802e311a  lea     r9, [rsp+98h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1802e3122  mov     r8, [rsp+98h+pSecurityDescriptor]; pSecurityDescriptor
0x1802e312a  mov     edx, 4; SecurityInformation
0x1802e312f  mov     rcx, [rsp+98h+hKey]; hKey
0x1802e3137  call    cs:__imp_RegGetKeySecurity
0x1802e313d  cmp     eax, 7Ah ; 'z'
0x1802e3140  jz      short loc_1802E30E2
0x1802e3142  mov     rcx, [rsp+98h]; this
0x1802e314a  test    eax, eax
0x1802e314c  jnz     loc_1802E32B2
0x1802e3152  mov     [rsp+98h+StringSecurityDescriptor], rsi
0x1802e3157  mov     qword ptr [rsp+98h+dwOptions], rsi; unsigned int
0x1802e315c  lea     r9, [rsp+98h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1802e3161  mov     r8d, 4; SecurityInformation
0x1802e3167  mov     edx, edi; RequestedStringSDRevision
0x1802e3169  mov     rcx, [rsp+98h+pSecurityDescriptor]; SecurityDescriptor
0x1802e3171  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1802e3177  test    eax, eax
0x1802e3179  jz      short loc_1802E3194
0x1802e317b  lea     rdx, aDAKaSyAKaBaAKa; "D:(A;;KA;;;SY)(A;;KA;;;BA)(A;;KA;;;OW)("...
0x1802e3182  mov     rcx, [rsp+98h+StringSecurityDescriptor]
0x1802e3187  call    cs:__imp__o__wcsicmp
0x1802e318d  neg     eax
0x1802e318f  sbb     cl, cl
0x1802e3191  and     dil, cl
0x1802e3194  lea     rcx, [rsp+98h+StringSecurityDescriptor]
0x1802e3199  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e319e  nop
0x1802e319f  lea     rcx, [rsp+98h+pSecurityDescriptor]
0x1802e31a7  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e31ac  test    dil, dil
0x1802e31af  jz      short loc_1802E3224
0x1802e31b1  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows Media Foun"...
0x1802e31b8  mov     rcx, r12; hKey
0x1802e31bb  call    cs:__imp_RegDeleteKeyW
0x1802e31c1  mov     rcx, [rsp+98h]; this
0x1802e31c9  test    eax, eax
0x1802e31cb  jnz     loc_1802E32C7
0x1802e31d1  lea     rcx, [rsp+98h+hKey]
0x1802e31d9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1802e31de  mov     [rsp+98h+lpdwDisposition], rsi; lpdwDisposition
0x1802e31e3  mov     [rsp+98h+phkResult], rax; phkResult
0x1802e31e8  lea     rax, [rsp+98h+SecurityAttributes]
0x1802e31ed  mov     [rsp+98h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1802e31f2  mov     [rsp+98h+samDesired], 2001Fh; samDesired
0x1802e31fa  mov     [rsp+98h+dwOptions], esi; unsigned int
0x1802e31fe  xor     r9d, r9d; lpClass
0x1802e3201  xor     r8d, r8d; Reserved
0x1802e3204  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows Media Foun"...
0x1802e320b  mov     rcx, r12; hKey
0x1802e320e  call    cs:__imp_RegCreateKeyExW
0x1802e3214  mov     rcx, [rsp+98h]; this
0x1802e321c  test    eax, eax
0x1802e321e  jnz     loc_1802E32EE
0x1802e3224  mov     [rsp+98h+samDesired], 8; cbData
0x1802e322c  lea     rax, [rsp+98h+Data]
0x1802e3231  mov     qword ptr [rsp+98h+dwOptions], rax; unsigned int
0x1802e3236  mov     r9d, 3; dwType
0x1802e323c  xor     r8d, r8d; Reserved
0x1802e323f  lea     rdx, aEffectsdiscove; "EffectsDiscoveredToastTime"
0x1802e3246  mov     rcx, [rsp+98h+hKey]; hKey
0x1802e324e  call    cs:__imp_RegSetValueExW
0x1802e3254  mov     rcx, [rsp+98h]; this
0x1802e325c  test    eax, eax
0x1802e325e  jnz     loc_1802E3302
0x1802e3264  lea     rcx, [rsp+98h+SecurityDescriptor]
0x1802e326c  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1802e3271  nop
0x1802e3272  lea     rcx, [rsp+98h+hKey]
0x1802e327a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1802e327f  nop
0x1802e3280  add     rsp, 80h
0x1802e3287  pop     r12
0x1802e3289  pop     rdi
0x1802e328a  pop     rsi
0x1802e328b  retn
0x1802e328c  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3293  mov     edx, 174h; void *
0x1802e3298  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802e329d  mov     r9d, eax; char *
0x1802e32a0  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e32a7  mov     edx, 17Dh; void *
0x1802e32ac  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1802e32b2  mov     r9d, eax; char *
0x1802e32b5  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e32bc  mov     edx, 18Dh; void *
0x1802e32c1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1802e32c7  mov     r9d, eax; char *
0x1802e32ca  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e32d1  mov     edx, 19Bh; void *
0x1802e32d6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1802e32dc  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e32e3  mov     edx, 18Ah; void *
0x1802e32e8  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1802e32ee  mov     r9d, eax; char *
0x1802e32f1  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e32f8  mov     edx, 19Ch; void *
0x1802e32fd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1802e3302  mov     r9d, eax; char *
0x1802e3305  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e330c  mov     edx, 19Fh; void *
0x1802e3311  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
