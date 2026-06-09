# Microsoft::CommonDatapoints::UpdateStaticCommonDatapointsInRegistry(void)

- ea: `0x1800d77d4`
- end: `0x1800d7d53`
- name: `?UpdateStaticCommonDatapointsInRegistry@CommonDatapoints@Microsoft@@SAJXZ`
- size: `1407`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801817c4`

## callees

- `0x18008b3c8`
- `0x180098d5c`
- `0x1800d77d4`
- `0x180105fcc`
- `0x18012de40`
- `0x18012eb08`
- `0x18012edcc`
- `0x180161064`
- `0x18017aafc`
- `0x18017e1f4`
- `0x180184f18`
- `0x1801850c8`
- `0x1801851b4`
- `0x180185290`
- `0x1801879d4`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d7be9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d7be9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d7bbf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d7bbf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d78d6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d78d6`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800d793a`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800d793a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d7883`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d7883`
- `ntdll!NtPowerInformation` at `0x1800d7a9a`
- `ntdll!NtPowerInformation` at `0x1800d7a9a`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x1800d7ae4`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x1800d7ae4`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x1800d79c8`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x1800d79c8`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x1800d78fc`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x1800d78fc`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1800d7a0e`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1800d7a0e`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x1800d7a4f`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x1800d7a4f`

## string_xrefs

- `0x1800d78c8`: `Software\Microsoft\SQMClient\Windows\CommonDatapoints`
- `0x1800d7bb8`: `ReAgent.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Microsoft::CommonDatapoints::UpdateStaticCommonDatapointsInRegistry(void)
{
  const wchar_t *v0; // rdx
  HKEY v1; // rcx
  const wchar_t *v2; // r8
  const wchar_t *v3; // rdx
  HKEY v4; // rcx
  struct _SECURITY_ATTRIBUTES *v5; // r8
  const wchar_t *v6; // r9
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  signed int v9; // ebx
  bool v10; // cc
  DWORDLONG ullTotalPhys; // rcx
  int v12; // eax
  HMODULE Library; // rax
  const wchar_t *v14; // rdx
  HMODULE v15; // rcx
  FARPROC ProcAddress; // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  char OutputBuffer; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v21[3]; // [rsp+55h] [rbp-ABh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 v23[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v24[4]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 v25[4]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 v26[4]; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int8 v27[8]; // [rsp+70h] [rbp-90h] BYREF
  HMODULE hModule; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v31; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v32; // [rsp+98h] [rbp-68h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v34; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v35[124]; // [rsp+E2h] [rbp-1Eh] BYREF
  __int16 v36; // [rsp+15Eh] [rbp+5Eh]
  wchar_t v37; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v38[126]; // [rsp+162h] [rbp+62h] BYREF

  memset_0(&Buffer, 0, sizeof(Buffer));
  v34 = 0;
  memset_0(v35, 0, 0x7Eu);
  *(_DWORD *)v19 = 0;
  *(_DWORD *)v23 = 0;
  hKey = 0;
  OutputBuffer = 0;
  v21[0] = 0;
  TotalMemoryInKilobytes = 0;
  *(_DWORD *)v24 = 0;
  *(_DWORD *)v25 = 0;
  v37 = 0;
  memset_0(v38, 0, sizeof(v38));
  *(_DWORD *)v26 = 0;
  *(_DWORD *)v27 = 0;
  hModule = 0;
  v32 = 0;
  SystemTimeAsFileTime = 0;
  if ( Microsoft::CommonDatapoints::RegGetDWord64Value(v1, v0, v2, &v32) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    Microsoft::CommonDatapoints::RegSetDWord64Value(v4, v3, v5, v6, SystemTimeAsFileTime.dwLowDateTime);
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
          0,
          0,
          0,
          0xF003Fu,
          0,
          phkResult,
          0);
  v9 = Key;
  v10 = Key <= 0;
  if ( Key )
  {
LABEL_43:
    if ( !v10 )
      v9 = (unsigned __int16)Key | 0x80070000;
    goto LABEL_45;
  }
  if ( hKey )
  {
    *(_DWORD *)v23 = GetActiveProcessorCount(0xFFFFu);
    v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x1Fu, 4u, v23, 4u);
    if ( v9 >= 0 )
    {
      Buffer.dwLength = 64;
      if ( !GlobalMemoryStatusEx(&Buffer) )
        goto LABEL_48;
      ullTotalPhys = 1;
      v12 = 0;
      while ( ullTotalPhys < Buffer.ullTotalPhys )
      {
        ullTotalPhys *= 2LL;
        if ( (unsigned int)++v12 >= 0x40 )
        {
          if ( ullTotalPhys < Buffer.ullTotalPhys )
          {
            ullTotalPhys = Buffer.ullTotalPhys;
            goto LABEL_16;
          }
          break;
        }
      }
      if ( ullTotalPhys - Buffer.ullTotalPhys > 0x1000000 )
      {
        ullTotalPhys >>= 1;
        if ( ullTotalPhys < Buffer.ullTotalPhys && Buffer.ullTotalPhys - ullTotalPhys > 0x1000000 )
          ullTotalPhys = Buffer.ullTotalPhys;
      }
LABEL_16:
      *(_DWORD *)v19 = ullTotalPhys >> 20;
      v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x23u, 4u, v19, 4u);
      if ( v9 >= 0 )
      {
LABEL_48:
        if ( !GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes)
          || (*(_DWORD *)v19 = TotalMemoryInKilobytes >> 10,
              v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x28C1u, 4u, v19, 4u),
              v9 >= 0) )
        {
          *(_DWORD *)v19 = IsOS(0x1Cu);
          v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x260u, 4u, v19, 4u);
          if ( v9 >= 0 )
          {
            *(_DWORD *)v19 = PowerDeterminePlatformRoleEx(2);
            Key = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x1F89u, 4u, v19, 4u);
            v9 = Key;
            v10 = Key <= 0;
            if ( !Key )
            {
              *(_DWORD *)v19 = 0;
              if ( NtPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, &OutputBuffer, 1u) >= 0 && OutputBuffer )
                *(_DWORD *)v19 = 1;
              v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x244Au, 4u, v19, 4u);
              if ( v9 >= 0 )
              {
                *(_DWORD *)v19 = 0;
                if ( (int)RtlCheckPortableOperatingSystem(v21) < 0 )
                  goto LABEL_29;
                if ( v21[0] )
                  *(_DWORD *)v19 = 1;
                v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x23EDu, 4u, v19, 4u);
                if ( v9 >= 0 )
                {
LABEL_29:
                  *(_DWORD *)v19 = Microsoft::CommonDatapoints::DetermineInstallType();
                  v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x244Cu, 4u, v19, 4u);
                  if ( v9 >= 0 )
                  {
                    if ( (int)Microsoft::CommonDatapoints::GetDiskGeometry((unsigned int *)v24, (unsigned int *)v25) < 0
                      || (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31B8u, 4u, v24, 4u),
                          v9 >= 0)
                      && (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31B9u, 4u, v25, 4u),
                          v9 >= 0) )
                    {
                      Library = LoadLibraryExW(L"ReAgent.dll", 0, 0x800u);
                      tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::reset(
                        &hModule,
                        Library);
                      v15 = hModule;
                      if ( !hModule
                        || (ProcAddress = GetProcAddress(hModule, "WinReIsWimBootEnabled")) == 0
                        || (*(_DWORD *)v19 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0) != 0,
                            v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31BAu, 4u, v19, 4u),
                            v9 >= 0) )
                      {
                        v34 = 0;
                        v31 = 0;
                        if ( Microsoft::CommonDatapoints::RegGetStringValue(
                               (HKEY)v15,
                               v14,
                               L"BuildLabEx",
                               &v34,
                               dwOptions)
                          || (v36 = 0, swscanf_s(&v34, L"%*d.%*d.%*[^.].%[^.].%d-%d", &v37, 64, v26, v27) != 3)
                          || (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31C0u, 4u, v26, 4u),
                              v9 >= 0)
                          && (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31C1u, 4u, v27, 4u),
                              v9 >= 0)
                          && (v9 = StringCchLengthW(&v37, 0x40u, &v31), v9 >= 0)
                          && (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(
                                     hKey,
                                     0x31C2u,
                                     1u,
                                     (unsigned __int8 *)&v37,
                                     2 * (int)v31 + 2),
                              v9 >= 0) )
                        {
                          v9 = 0;
                        }
                      }
                    }
                  }
                }
              }
              goto LABEL_45;
            }
            goto LABEL_43;
          }
        }
      }
    }
  }
LABEL_45:
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hModule);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800d77d4  push    rbp
0x1800d77d6  push    rbx
0x1800d77d7  push    rsi
0x1800d77d8  push    rdi
0x1800d77d9  push    r14
0x1800d77db  push    r15
0x1800d77dd  lea     rbp, [rsp-0F8h]
0x1800d77e5  sub     rsp, 1F8h
0x1800d77ec  mov     rax, cs:__security_cookie
0x1800d77f3  xor     rax, rsp
0x1800d77f6  mov     [rbp+120h+var_40], rax
0x1800d77fd  mov     r15d, 40h ; '@'
0x1800d7803  mov     r8d, r15d; Size
0x1800d7806  xor     edx, edx; Val
0x1800d7808  lea     rcx, [rbp+120h+Buffer]; void *
0x1800d780c  call    memset_0
0x1800d7811  xor     edi, edi
0x1800d7813  mov     [rbp+120h+var_140], di
0x1800d7817  lea     ebx, [rdi+7Eh]
0x1800d781a  mov     r8d, ebx; Size
0x1800d781d  xor     edx, edx; Val
0x1800d781f  lea     rcx, [rbp+120h+var_13E]; void *
0x1800d7823  call    memset_0
0x1800d7828  mov     dword ptr [rsp+220h+var_1D0], edi
0x1800d782c  mov     dword ptr [rsp+220h+var_1C0], edi
0x1800d7830  mov     [rsp+220h+hKey], rdi
0x1800d7835  mov     [rsp+220h+OutputBuffer], dil
0x1800d783a  mov     [rsp+220h+var_1CB], dil
0x1800d783f  mov     [rbp+120h+TotalMemoryInKilobytes], rdi
0x1800d7843  mov     dword ptr [rsp+220h+var_1BC], edi
0x1800d7847  mov     dword ptr [rsp+220h+var_1B8], edi
0x1800d784b  mov     [rbp+120h+var_C0], di
0x1800d784f  mov     r8d, ebx; Size
0x1800d7852  xor     edx, edx; Val
0x1800d7854  lea     rcx, [rbp+120h+var_BE]; void *
0x1800d7858  call    memset_0
0x1800d785d  mov     dword ptr [rsp+220h+var_1B4], edi
0x1800d7861  mov     dword ptr [rsp+220h+var_1B0], edi
0x1800d7865  mov     [rsp+220h+hModule], rdi
0x1800d786a  mov     [rbp+120h+var_188], rdi
0x1800d786e  mov     qword ptr [rbp+120h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800d7872  lea     r9, [rbp+120h+var_188]; unsigned __int64 *
0x1800d7876  call    ?RegGetDWord64Value@CommonDatapoints@Microsoft@@CAKPEAUHKEY__@@PEB_W1PEA_K@Z; Microsoft::CommonDatapoints::RegGetDWord64Value(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64 *)
0x1800d787b  test    eax, eax
0x1800d787d  jz      short loc_1800D789D
0x1800d787f  lea     rcx, [rbp+120h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800d7883  call    cs:__imp_GetSystemTimeAsFileTime
0x1800d788a  nop     dword ptr [rax+rax+00h]
0x1800d788f  mov     rax, qword ptr [rbp+120h+SystemTimeAsFileTime.dwLowDateTime]
0x1800d7893  mov     qword ptr [rsp+220h+dwOptions], rax; Data
0x1800d7898  call    ?RegSetDWord64Value@CommonDatapoints@Microsoft@@CAKPEAUHKEY__@@PEB_WPEAU_SECURITY_ATTRIBUTES@@1_K@Z; Microsoft::CommonDatapoints::RegSetDWord64Value(HKEY__ *,wchar_t const *,_SECURITY_ATTRIBUTES *,wchar_t const *,unsigned __int64)
0x1800d789d  lea     rcx, [rsp+220h+hKey]
0x1800d78a2  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800d78a7  mov     [rsp+220h+lpdwDisposition], rdi; lpdwDisposition
0x1800d78ac  mov     [rsp+220h+phkResult], rax; phkResult
0x1800d78b1  mov     [rsp+220h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800d78b6  mov     [rsp+220h+samDesired], 0F003Fh; samDesired
0x1800d78be  mov     [rsp+220h+dwOptions], edi; dwOptions
0x1800d78c2  xor     r9d, r9d; lpClass
0x1800d78c5  xor     r8d, r8d; Reserved
0x1800d78c8  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\SQMClient\\Windows"...
0x1800d78cf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d78d6  call    cs:__imp_RegCreateKeyExW
0x1800d78dd  nop     dword ptr [rax+rax+00h]
0x1800d78e2  mov     ebx, eax
0x1800d78e4  test    eax, eax
0x1800d78e6  jnz     loc_1800D7D11
0x1800d78ec  cmp     [rsp+220h+hKey], rdi
0x1800d78f1  jz      loc_1800D7D1C
0x1800d78f7  mov     ecx, 0FFFFh; GroupNumber
0x1800d78fc  call    cs:__imp_GetActiveProcessorCount
0x1800d7903  nop     dword ptr [rax+rax+00h]
0x1800d7908  mov     dword ptr [rsp+220h+var_1C0], eax
0x1800d790c  lea     esi, [rbx+4]
0x1800d790f  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7913  lea     r9, [rsp+220h+var_1C0]; unsigned __int8 *
0x1800d7918  mov     r8d, esi; unsigned int
0x1800d791b  lea     edx, [rbx+1Fh]; unsigned int
0x1800d791e  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d7923  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d7928  mov     ebx, eax
0x1800d792a  test    eax, eax
0x1800d792c  js      loc_1800D7D1C
0x1800d7932  mov     [rbp+120h+Buffer.dwLength], r15d
0x1800d7936  lea     rcx, [rbp+120h+Buffer]; lpBuffer
0x1800d793a  call    cs:__imp_GlobalMemoryStatusEx
0x1800d7941  nop     dword ptr [rax+rax+00h]
0x1800d7946  lea     r14d, [rsi-3]
0x1800d794a  test    eax, eax
0x1800d794c  jz      short loc_1800D79C4
0x1800d794e  mov     rdx, [rbp+120h+Buffer.ullTotalPhys]
0x1800d7952  mov     ecx, r14d
0x1800d7955  mov     eax, edi
0x1800d7957  cmp     rcx, rdx
0x1800d795a  jnb     short loc_1800D7971
0x1800d795c  add     rcx, rcx
0x1800d795f  add     eax, r14d
0x1800d7962  cmp     eax, r15d
0x1800d7965  jb      short loc_1800D7957
0x1800d7967  cmp     rcx, rdx
0x1800d796a  jnb     short loc_1800D7971
0x1800d796c  mov     rcx, rdx
0x1800d796f  jmp     short loc_1800D7997
0x1800d7971  mov     rax, rcx
0x1800d7974  sub     rax, rdx
0x1800d7977  mov     r8d, 1000000h
0x1800d797d  cmp     rax, r8
0x1800d7980  jbe     short loc_1800D7997
0x1800d7982  shr     rcx, 1
0x1800d7985  cmp     rcx, rdx
0x1800d7988  jnb     short loc_1800D7997
0x1800d798a  mov     rax, rdx
0x1800d798d  sub     rax, rcx
0x1800d7990  cmp     rax, r8
0x1800d7993  cmova   rcx, rdx
0x1800d7997  shr     rcx, 14h
0x1800d799b  mov     dword ptr [rsp+220h+var_1D0], ecx
0x1800d799f  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d79a3  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800d79a8  mov     r8d, esi; unsigned int
0x1800d79ab  mov     edx, 23h ; '#'; unsigned int
0x1800d79b0  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d79b5  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d79ba  mov     ebx, eax
0x1800d79bc  test    eax, eax
0x1800d79be  js      loc_1800D7D1C
0x1800d79c4  lea     rcx, [rbp+120h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x1800d79c8  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x1800d79cf  nop     dword ptr [rax+rax+00h]
0x1800d79d4  test    eax, eax
0x1800d79d6  jz      short loc_1800D7A09
0x1800d79d8  mov     rax, [rbp+120h+TotalMemoryInKilobytes]
0x1800d79dc  shr     rax, 0Ah
0x1800d79e0  mov     dword ptr [rsp+220h+var_1D0], eax
0x1800d79e4  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d79e8  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800d79ed  mov     r8d, esi; unsigned int
0x1800d79f0  mov     edx, 28C1h; unsigned int
0x1800d79f5  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d79fa  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d79ff  mov     ebx, eax
0x1800d7a01  test    eax, eax
0x1800d7a03  js      loc_1800D7D1C
0x1800d7a09  mov     ecx, 1Ch; dwOS
0x1800d7a0e  call    cs:__imp_IsOS
0x1800d7a15  nop     dword ptr [rax+rax+00h]
0x1800d7a1a  mov     ecx, edi
0x1800d7a1c  test    eax, eax
0x1800d7a1e  setnz   cl
0x1800d7a21  mov     dword ptr [rsp+220h+var_1D0], ecx
0x1800d7a25  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7a29  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800d7a2e  mov     r8d, esi; unsigned int
0x1800d7a31  mov     edx, 260h; unsigned int
0x1800d7a36  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d7a3b  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d7a40  mov     ebx, eax
0x1800d7a42  test    eax, eax
0x1800d7a44  js      loc_1800D7D1C
0x1800d7a4a  mov     ecx, 2
0x1800d7a4f  call    cs:__imp_PowerDeterminePlatformRoleEx
0x1800d7a56  nop     dword ptr [rax+rax+00h]
0x1800d7a5b  mov     dword ptr [rsp+220h+var_1D0], eax
0x1800d7a5f  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7a63  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800d7a68  mov     r8d, esi; unsigned int
0x1800d7a6b  mov     edx, 1F89h; unsigned int
0x1800d7a70  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d7a75  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d7a7a  mov     ebx, eax
0x1800d7a7c  test    eax, eax
0x1800d7a7e  jnz     loc_1800D7D11
0x1800d7a84  mov     dword ptr [rsp+220h+var_1D0], edi
0x1800d7a88  mov     [rsp+220h+dwOptions], r14d; OutputBufferLength
0x1800d7a8d  lea     r9, [rsp+220h+OutputBuffer]; OutputBuffer
0x1800d7a92  xor     r8d, r8d; InputBufferLength
0x1800d7a95  xor     edx, edx; InputBuffer
0x1800d7a97  lea     ecx, [rax+42h]; PowerInformationLevel
0x1800d7a9a  call    cs:__imp_NtPowerInformation
0x1800d7aa1  nop     dword ptr [rax+rax+00h]
0x1800d7aa6  test    eax, eax
0x1800d7aa8  js      short loc_1800D7AB6
0x1800d7aaa  cmp     [rsp+220h+OutputBuffer], dil
0x1800d7aaf  jz      short loc_1800D7AB6
0x1800d7ab1  mov     dword ptr [rsp+220h+var_1D0], r14d
0x1800d7ab6  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7aba  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800d7abf  mov     r8d, esi; unsigned int
0x1800d7ac2  mov     edx, 244Ah; unsigned int
0x1800d7ac7  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d7acc  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d7ad1  mov     ebx, eax
0x1800d7ad3  test    eax, eax
0x1800d7ad5  js      loc_1800D7D1C
0x1800d7adb  mov     dword ptr [rsp+220h+var_1D0], edi
0x1800d7adf  lea     rcx, [rsp+220h+var_1CB]
0x1800d7ae4  call    cs:__imp_RtlCheckPortableOperatingSystem
0x1800d7aeb  nop     dword ptr [rax+rax+00h]
0x1800d7af0  test    eax, eax
0x1800d7af2  js      short loc_1800D7B25
0x1800d7af4  cmp     [rsp+220h+var_1CB], dil
0x1800d7af9  jz      short loc_1800D7B00
0x1800d7afb  mov     dword ptr [rsp+220h+var_1D0], r14d
0x1800d7b00  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7b04  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800d7b09  mov     r8d, esi; unsigned int
0x1800d7b0c  mov     edx, 23EDh; unsigned int
0x1800d7b11  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d7b16  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d7b1b  mov     ebx, eax
0x1800d7b1d  test    eax, eax
0x1800d7b1f  js      loc_1800D7D1C
0x1800d7b25  call    ?DetermineInstallType@CommonDatapoints@Microsoft@@CAKXZ; Microsoft::CommonDatapoints::DetermineInstallType(void)
0x1800d7b2a  mov     dword ptr [rsp+220h+var_1D0], eax
0x1800d7b2e  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7b32  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800d7b37  mov     r8d, esi; unsigned int
0x1800d7b3a  mov     edx, 244Ch; unsigned int
0x1800d7b3f  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d7b44  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d7b49  mov     ebx, eax
0x1800d7b4b  test    eax, eax
0x1800d7b4d  js      loc_1800D7D1C
0x1800d7b53  lea     rdx, [rsp+220h+var_1B8]; unsigned int *
0x1800d7b58  lea     rcx, [rsp+220h+var_1BC]; unsigned int *
0x1800d7b5d  call    ?GetDiskGeometry@CommonDatapoints@Microsoft@@CAJPEAK0@Z; Microsoft::CommonDatapoints::GetDiskGeometry(ulong *,ulong *)
0x1800d7b62  test    eax, eax
0x1800d7b64  js      short loc_1800D7BB0
0x1800d7b66  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7b6a  lea     r9, [rsp+220h+var_1BC]; unsigned __int8 *
0x1800d7b6f  mov     r8d, esi; unsigned int
0x1800d7b72  mov     edx, 31B8h; unsigned int
0x1800d7b77  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d7b7c  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d7b81  mov     ebx, eax
0x1800d7b83  test    eax, eax
0x1800d7b85  js      loc_1800D7D1C
0x1800d7b8b  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7b8f  lea     r9, [rsp+220h+var_1B8]; unsigned __int8 *
0x1800d7b94  mov     r8d, esi; unsigned int
0x1800d7b97  mov     edx, 31B9h; unsigned int
0x1800d7b9c  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d7ba1  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d7ba6  mov     ebx, eax
0x1800d7ba8  test    eax, eax
0x1800d7baa  js      loc_1800D7D1C
0x1800d7bb0  xor     edx, edx; hFile
0x1800d7bb2  mov     r8d, 800h; dwFlags
0x1800d7bb8  lea     rcx, aReagentDll; "ReAgent.dll"
0x1800d7bbf  call    cs:__imp_LoadLibraryExW
0x1800d7bc6  nop     dword ptr [rax+rax+00h]
0x1800d7bcb  mov     rdx, rax
0x1800d7bce  lea     rcx, [rsp+220h+hModule]
0x1800d7bd3  call    ?reset@?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAAXPEAUHINSTANCE__@@@Z; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::reset(HINSTANCE__ *)
0x1800d7bd8  mov     rcx, [rsp+220h+hModule]; hModule
0x1800d7bdd  test    rcx, rcx
0x1800d7be0  jz      short loc_1800D7C33
0x1800d7be2  lea     rdx, aWinreiswimboot; "WinReIsWimBootEnabled"
0x1800d7be9  call    cs:__imp_GetProcAddress
0x1800d7bf0  nop     dword ptr [rax+rax+00h]
0x1800d7bf5  test    rax, rax
0x1800d7bf8  jz      short loc_1800D7C33
0x1800d7bfa  mov     dword ptr [rsp+220h+var_1D0], edi
0x1800d7bfe  xor     ecx, ecx
0x1800d7c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7c05  test    eax, eax
0x1800d7c07  jz      short loc_1800D7C0E
0x1800d7c09  mov     dword ptr [rsp+220h+var_1D0], r14d
0x1800d7c0e  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7c12  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800d7c17  mov     r8d, esi; unsigned int
0x1800d7c1a  mov     edx, 31BAh; unsigned int
0x1800d7c1f  mov     rcx, [rsp+220h+hKey]; hKey
0x1800d7c24  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800d7c29  mov     ebx, eax
0x1800d7c2b  test    eax, eax
0x1800d7c2d  js      loc_1800D7D1C
0x1800d7c33  mov     [rbp+120h+var_140], di
0x1800d7c37  mov     [rbp+120h+var_190], rdi
0x1800d7c3b  lea     r9, [rbp+120h+var_140]; wchar_t *
0x1800d7c3f  lea     r8, aBuildlabex; "BuildLabEx"
0x1800d7c46  call    ?RegGetStringValue@CommonDatapoints@Microsoft@@CAKPEAUHKEY__@@PEB_W1PEA_WK@Z; Microsoft::CommonDatapoints::RegGetStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong)
0x1800d7c4b  test    eax, eax
0x1800d7c4d  jnz     loc_1800D7D0D
0x1800d7c53  mov     [rbp+120h+var_C2], di
0x1800d7c57  lea     rax, [rsp+220h+var_1B0]
0x1800d7c5c  mov     qword ptr [rsp+220h+samDesired], rax
0x1800d7c61  lea     rax, [rsp+220h+var_1B4]
0x1800d7c66  mov     qword ptr [rsp+220h+dwOptions], rax
0x1800d7c6b  mov     r9d, r15d
0x1800d7c6e  lea     r8, [rbp+120h+var_C0]
0x1800d7c72  lea     rdx, aDDDD; "%*d.%*d.%*[^.].%[^.].%d-%d"
0x1800d7c79  lea     rcx, [rbp+120h+var_140]; Buffer
0x1800d7c7d  call    swscanf_s
0x1800d7c82  cmp     eax, 3
0x1800d7c85  jnz     loc_1800D7D0D
0x1800d7c8b  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800d7c8f  lea     r9, [rsp+220h+var_1B4]; unsigned __int8 *
0x1800d7c94  mov     r8d, esi; unsigned int
0x1800d7c97  mov     edx, 31C0h; unsigned int
  ... truncated ...
```
