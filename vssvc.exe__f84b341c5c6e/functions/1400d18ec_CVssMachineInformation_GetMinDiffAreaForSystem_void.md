# CVssMachineInformation::GetMinDiffAreaForSystem(void)

- ea: `0x1400d18ec`
- end: `0x1400d1cd2`
- name: `?GetMinDiffAreaForSystem@CVssMachineInformation@@SA_JXZ`
- size: `998`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1400a7280`

## callees

- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140028b48`
- `0x140091560`
- `0x1400921dc`
- `0x1400d18ec`
- `0x1400d1cd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d1a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d1a1e`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400d1ac8`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400d1ac8`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400d1b56`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400d1b56`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400d19a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400d19a8`

## string_xrefs

- `0x1400d1913`: `base\stor\vss\modules\registry\registry.cxx`
- `0x1400d1c16`: `base\stor\vss\modules\registry\registry.cxx`
- `0x1400d1a7f`: `GetSystemWindowsDirectoryW(%s, %u): %u [0x%08lx]`
- `0x1400d1a05`: `GetSystemWindowsDirectoryW(%s, %u): %u`
- `0x1400d1ba4`: `GetVolumeNameForVolumeMountPointW( '%s', STRING_CCH_PARAM(wszSysVolumeName))`
- `0x1400d1b27`: `GetVolumePathNameW(%s, %p, %u)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CVssMachineInformation::GetMinDiffAreaForSystem(void)
{
  UINT SystemWindowsDirectoryW; // eax
  DWORD LastError; // ebx
  BOOL VolumeNameForVolumeMountPointW; // eax
  __int64 MinDiffAreaOnVolume; // rbx
  __int64 v5; // [rsp+28h] [rbp-670h]
  UINT v6; // [rsp+48h] [rbp-650h]
  const unsigned __int16 *v7; // [rsp+50h] [rbp-648h] BYREF
  const unsigned __int16 *v8; // [rsp+58h] [rbp-640h]
  const unsigned __int16 *v9; // [rsp+60h] [rbp-638h]
  int v10; // [rsp+68h] [rbp-630h]
  int v11; // [rsp+6Ch] [rbp-62Ch]
  int v12; // [rsp+70h] [rbp-628h]
  _BYTE v13[120]; // [rsp+78h] [rbp-620h] BYREF
  int v14; // [rsp+F0h] [rbp-5A8h]
  int v15; // [rsp+F8h] [rbp-5A0h] BYREF
  LPVOID v16; // [rsp+100h] [rbp-598h] BYREF
  unsigned int v17; // [rsp+108h] [rbp-590h]
  unsigned int v18; // [rsp+124h] [rbp-574h]
  _com_error *v19; // [rsp+170h] [rbp-528h] BYREF
  const std::exception *v20; // [rsp+178h] [rbp-520h] BYREF
  _QWORD szVolumeName[3]; // [rsp+180h] [rbp-518h] BYREF
  int v22; // [rsp+198h] [rbp-500h]
  int v23; // [rsp+19Ch] [rbp-4FCh]
  int v24; // [rsp+1A0h] [rbp-4F8h]
  _DWORD v25[34]; // [rsp+1A8h] [rbp-4F0h] BYREF
  WCHAR szVolumePathName; // [rsp+230h] [rbp-468h] BYREF
  _BYTE v27[526]; // [rsp+232h] [rbp-466h] BYREF
  WCHAR Buffer[264]; // [rsp+440h] [rbp-258h] BYREF

  szVolumeName[0] = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  szVolumeName[1] = L"CVssMachineInformation::GetMinDiffAreaForSystem";
  szVolumeName[2] = L"REGREGSC";
  v22 = 1735;
  v23 = 11;
  v24 = 255;
  v25[30] = 0x1000000;
  memset_0(v25, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v16, (__int64)szVolumeName, 0);
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x105u);
  try
  {
    v6 = SystemWindowsDirectoryW;
    if ( !SystemWindowsDirectoryW )
    {
      v7 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v8 = L"CVssMachineInformation::GetMinDiffAreaForSystem";
      v9 = L"REGREGSC";
      v10 = 1744;
      v11 = 11;
      v12 = 255;
      v14 = 0x1000000;
      memset_0(v13, 0, sizeof(v13));
      CVssFunctionTracer::TranslateWin32Error(&v16, &v7, L"GetSystemWindowsDirectoryW(%s, %u): %u", Buffer, 261, 0);
    }
    LastError = GetLastError();
    v7 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v8 = L"CVssMachineInformation::GetMinDiffAreaForSystem";
    v9 = L"REGREGSC";
    v10 = 1746;
    v11 = 11;
    v12 = 255;
    v14 = 0x1000000;
    memset_0(v13, 0, sizeof(v13));
    CVssFunctionTracer::Trace(
      &v16,
      &v7,
      L"GetSystemWindowsDirectoryW(%s, %u): %u [0x%08lx]",
      Buffer,
      261,
      v6,
      LastError);
    szVolumePathName = 0;
    memset_0(v27, 0, 0x208u);
    if ( !GetVolumePathNameW(Buffer, &szVolumePathName, 0x105u) )
    {
      v7 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v8 = L"CVssMachineInformation::GetMinDiffAreaForSystem";
      v9 = L"REGREGSC";
      v10 = 1755;
      v11 = 11;
      v12 = 255;
      v14 = 0x1000000;
      memset_0(v13, 0, sizeof(v13));
      LODWORD(v5) = 261;
      CVssFunctionTracer::TranslateWin32Error(
        &v16,
        &v7,
        L"GetVolumePathNameW(%s, %p, %u)",
        Buffer,
        &szVolumePathName,
        v5);
    }
    VolumeNameForVolumeMountPointW = GetVolumeNameForVolumeMountPointW(&szVolumePathName, (LPWSTR)szVolumeName, 0x32u);
    v7 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v8 = L"CVssMachineInformation::GetMinDiffAreaForSystem";
    v9 = L"REGREGSC";
    v11 = 11;
    v12 = 255;
    v14 = 0x1000000;
    if ( !VolumeNameForVolumeMountPointW )
    {
      v10 = 1761;
      memset_0(v13, 0, sizeof(v13));
      CVssFunctionTracer::TranslateWin32Error(
        &v16,
        &v7,
        L"GetVolumeNameForVolumeMountPointW( '%s', STRING_CCH_PARAM(wszSysVolumeName))",
        &szVolumePathName);
    }
    v10 = 1763;
    memset_0(v13, 0, sizeof(v13));
    CVssFunctionTracer::Trace(&v16, &v7, L"System volume name: %s", szVolumeName);
    MinDiffAreaOnVolume = CVssMachineInformation::GetMinDiffAreaOnVolume((const unsigned __int16 *)szVolumeName);
  }
  catch ( long v15 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v16,
      v15,
      L"base\\stor\\vss\\modules\\registry\\registry.cxx",
      L"REGREGSC",
      L"CVssMachineInformation::GetMinDiffAreaForSystem",
      0x6E7u,
      v18);
    goto LABEL_10;
  }
  catch ( _com_error *v19 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v16,
      v19,
      L"base\\stor\\vss\\modules\\registry\\registry.cxx",
      L"REGREGSC",
      L"CVssMachineInformation::GetMinDiffAreaForSystem",
      0x6E7u,
      v18);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v16,
      L"base\\stor\\vss\\modules\\registry\\registry.cxx",
      L"REGREGSC",
      L"CVssMachineInformation::GetMinDiffAreaForSystem",
      0x6E7u,
      v18);
LABEL_10:
    v7 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v8 = L"CVssMachineInformation::GetMinDiffAreaForSystem";
    v9 = L"REGREGSC";
    v10 = 1769;
    v11 = 11;
    v12 = 255;
    v14 = 0x1000000;
    memset_0(v13, 0, sizeof(v13));
    CVssFunctionTracer::Trace(
      &v16,
      &v7,
      L"Cannot retrieve system default minimum diff area [0x%08lx]. Using the default value %I64d",
      v17,
      335544320);
    CVssFunctionTracer::~CVssFunctionTracer(&v16);
    return 335544320;
  }
  catch ( const std::exception *v20 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v16,
      v20,
      L"base\\stor\\vss\\modules\\registry\\registry.cxx",
      L"REGREGSC",
      L"CVssMachineInformation::GetMinDiffAreaForSystem",
      0x6E7u,
      v18);
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v16);
  return MinDiffAreaOnVolume;
}

```

## disassembly

```asm
0x1400d18ec  mov     r11, rsp
0x1400d18ef  push    rbx
0x1400d18f0  push    rsi
0x1400d18f1  push    rdi
0x1400d18f2  push    r12
0x1400d18f4  push    r13
0x1400d18f6  push    r14
0x1400d18f8  push    r15
0x1400d18fa  sub     rsp, 660h
0x1400d1901  mov     rax, cs:__security_cookie
0x1400d1908  xor     rax, rsp
0x1400d190b  mov     [rsp+698h+var_48], rax
0x1400d1913  lea     rsi, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x1400d191a  mov     [r11-518h], rsi
0x1400d1921  lea     r14, aCvssmachineinf_0; "CVssMachineInformation::GetMinDiffAreaF"...
0x1400d1928  mov     [r11-510h], r14
0x1400d192f  lea     r15, aRegregsc; "REGREGSC"
0x1400d1936  mov     [r11-508h], r15
0x1400d193d  mov     [rsp+698h+var_500], 6C7h
0x1400d1948  mov     r12d, 0Bh
0x1400d194e  mov     [r11-4FCh], r12d
0x1400d1955  mov     r13d, 0FFh
0x1400d195b  mov     [r11-4F8h], r13d
0x1400d1962  xor     edi, edi
0x1400d1964  mov     [rsp+698h+var_478], 1000000h
0x1400d196f  lea     ebx, [rdi+78h]
0x1400d1972  mov     r8d, ebx; Size
0x1400d1975  xor     edx, edx; Val
0x1400d1977  lea     rcx, [r11-4F0h]; void *
0x1400d197e  call    memset_0
0x1400d1983  xor     r8d, r8d
0x1400d1986  lea     rdx, [rsp+698h+szVolumeName]
0x1400d198e  lea     rcx, [rsp+698h+var_598]
0x1400d1996  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400d199b  nop
0x1400d199c  lea     edx, [r13+6]; uSize
0x1400d19a0  lea     rcx, [rsp+698h+Buffer]; lpBuffer
0x1400d19a8  call    cs:__imp_GetSystemWindowsDirectoryW
0x1400d19ae  mov     [rsp+698h+var_650], eax
0x1400d19b2  test    eax, eax
0x1400d19b4  jnz     short loc_1400D1A1E
0x1400d19b6  mov     [rsp+698h+var_648], rsi
0x1400d19bb  mov     [rsp+698h+var_640], r14
0x1400d19c0  mov     [rsp+698h+var_638], r15
0x1400d19c5  mov     [rsp+698h+var_630], 6D0h
0x1400d19cd  mov     [rsp+698h+var_62C], r12d
0x1400d19d2  mov     [rsp+698h+var_628], r13d
0x1400d19d7  mov     [rsp+698h+var_5A8], 1000000h
0x1400d19e2  mov     r8d, ebx; Size
0x1400d19e5  xor     edx, edx; Val
0x1400d19e7  lea     rcx, [rsp+698h+var_620]; void *
0x1400d19ec  call    memset_0
0x1400d19f1  mov     dword ptr [rsp+698h+var_670], edi
0x1400d19f5  mov     dword ptr [rsp+698h+var_678], 105h
0x1400d19fd  lea     r9, [rsp+698h+Buffer]
0x1400d1a05  lea     r8, aGetsystemwindo_0; "GetSystemWindowsDirectoryW(%s, %u): %u"
0x1400d1a0c  lea     rdx, [rsp+698h+var_648]
0x1400d1a11  lea     rcx, [rsp+698h+var_598]
0x1400d1a19  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400d1a1e  call    cs:__imp_GetLastError
0x1400d1a24  mov     ebx, eax
0x1400d1a26  mov     [rsp+698h+var_648], rsi
0x1400d1a2b  mov     [rsp+698h+var_640], r14
0x1400d1a30  mov     [rsp+698h+var_638], r15
0x1400d1a35  mov     [rsp+698h+var_630], 6D2h
0x1400d1a3d  mov     [rsp+698h+var_62C], r12d
0x1400d1a42  mov     [rsp+698h+var_628], r13d
0x1400d1a47  mov     [rsp+698h+var_5A8], 1000000h
0x1400d1a52  xor     edx, edx; Val
0x1400d1a54  lea     r8d, [rdx+78h]; Size
0x1400d1a58  lea     rcx, [rsp+698h+var_620]; void *
0x1400d1a5d  call    memset_0
0x1400d1a62  mov     [rsp+698h+var_668], ebx
0x1400d1a66  mov     eax, [rsp+698h+var_650]
0x1400d1a6a  mov     dword ptr [rsp+698h+var_670], eax
0x1400d1a6e  mov     ebx, 105h
0x1400d1a73  mov     dword ptr [rsp+698h+var_678], ebx
0x1400d1a77  lea     r9, [rsp+698h+Buffer]
0x1400d1a7f  lea     r8, aGetsystemwindo; "GetSystemWindowsDirectoryW(%s, %u): %u "...
0x1400d1a86  lea     rdx, [rsp+698h+var_648]
0x1400d1a8b  lea     rcx, [rsp+698h+var_598]
0x1400d1a93  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400d1a98  mov     [rsp+698h+szVolumePathName], di
0x1400d1aa0  xor     edx, edx; Val
0x1400d1aa2  mov     r8d, 208h; Size
0x1400d1aa8  lea     rcx, [rsp+698h+var_466]; void *
0x1400d1ab0  call    memset_0
0x1400d1ab5  mov     r8d, ebx; cchBufferLength
0x1400d1ab8  lea     rdx, [rsp+698h+szVolumePathName]; lpszVolumePathName
0x1400d1ac0  lea     rcx, [rsp+698h+Buffer]; lpszFileName
0x1400d1ac8  call    cs:__imp_GetVolumePathNameW
0x1400d1ace  test    eax, eax
0x1400d1ad0  jnz     short loc_1400D1B40
0x1400d1ad2  mov     [rsp+698h+var_648], rsi
0x1400d1ad7  mov     [rsp+698h+var_640], r14
0x1400d1adc  mov     [rsp+698h+var_638], r15
0x1400d1ae1  mov     [rsp+698h+var_630], 6DBh
0x1400d1ae9  mov     [rsp+698h+var_62C], r12d
0x1400d1aee  mov     [rsp+698h+var_628], r13d
0x1400d1af3  mov     [rsp+698h+var_5A8], 1000000h
0x1400d1afe  xor     edx, edx; Val
0x1400d1b00  lea     r8d, [rax+78h]; Size
0x1400d1b04  lea     rcx, [rsp+698h+var_620]; void *
0x1400d1b09  call    memset_0
0x1400d1b0e  mov     dword ptr [rsp+698h+var_670], ebx
0x1400d1b12  lea     rax, [rsp+698h+szVolumePathName]
0x1400d1b1a  mov     [rsp+698h+var_678], rax
0x1400d1b1f  lea     r9, [rsp+698h+Buffer]
0x1400d1b27  lea     r8, aGetvolumepathn_5; "GetVolumePathNameW(%s, %p, %u)"
0x1400d1b2e  lea     rdx, [rsp+698h+var_648]
0x1400d1b33  lea     rcx, [rsp+698h+var_598]
0x1400d1b3b  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400d1b40  mov     r8d, 32h ; '2'; cchBufferLength
0x1400d1b46  lea     rdx, [rsp+698h+szVolumeName]; lpszVolumeName
0x1400d1b4e  lea     rcx, [rsp+698h+szVolumePathName]; lpszVolumeMountPoint
0x1400d1b56  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1400d1b5c  mov     [rsp+698h+var_648], rsi
0x1400d1b61  mov     [rsp+698h+var_640], r14
0x1400d1b66  mov     [rsp+698h+var_638], r15
0x1400d1b6b  mov     [rsp+698h+var_62C], r12d
0x1400d1b70  mov     [rsp+698h+var_628], r13d
0x1400d1b75  mov     [rsp+698h+var_5A8], 1000000h
0x1400d1b80  xor     edx, edx; Val
0x1400d1b82  lea     r8d, [rdx+78h]; Size
0x1400d1b86  lea     rcx, [rsp+698h+var_620]; void *
0x1400d1b8b  test    eax, eax
0x1400d1b8d  jnz     short loc_1400D1BBD
0x1400d1b8f  mov     [rsp+698h+var_630], 6E1h
0x1400d1b97  call    memset_0
0x1400d1b9c  lea     r9, [rsp+698h+szVolumePathName]
0x1400d1ba4  lea     r8, aGetvolumenamef_15; "GetVolumeNameForVolumeMountPointW( '%s'"...
0x1400d1bab  lea     rdx, [rsp+698h+var_648]
0x1400d1bb0  lea     rcx, [rsp+698h+var_598]
0x1400d1bb8  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400d1bbd  mov     [rsp+698h+var_630], 6E3h
0x1400d1bc5  call    memset_0
0x1400d1bca  lea     r9, [rsp+698h+szVolumeName]
0x1400d1bd2  lea     r8, aSystemVolumeNa; "System volume name: %s"
0x1400d1bd9  lea     rdx, [rsp+698h+var_648]
0x1400d1bde  lea     rcx, [rsp+698h+var_598]
0x1400d1be6  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400d1beb  lea     rcx, [rsp+698h+szVolumeName]; unsigned __int16 *
0x1400d1bf3  call    ?GetMinDiffAreaOnVolume@CVssMachineInformation@@SA_JPEBG@Z; CVssMachineInformation::GetMinDiffAreaOnVolume(ushort const *)
0x1400d1bf8  mov     rbx, rax
0x1400d1bfb  lea     rcx, [rsp+698h+var_598]; this
0x1400d1c03  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400d1c08  mov     rax, rbx
0x1400d1c0b  jmp     loc_1400D1CAF
0x1400d1c10  jmp     short loc_1400D1C16
0x1400d1c12  jmp     short loc_1400D1C16
0x1400d1c14  jmp     short $+2
0x1400d1c16  lea     rsi, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x1400d1c1d  mov     [rsp+698h+var_648], rsi
0x1400d1c22  lea     r14, aCvssmachineinf_0; "CVssMachineInformation::GetMinDiffAreaF"...
0x1400d1c29  mov     [rsp+698h+var_640], r14
0x1400d1c2e  lea     r15, aRegregsc; "REGREGSC"
0x1400d1c35  mov     [rsp+698h+var_638], r15
0x1400d1c3a  mov     [rsp+698h+var_630], 6E9h
0x1400d1c42  mov     r12d, 0Bh
0x1400d1c48  mov     [rsp+698h+var_62C], r12d
0x1400d1c4d  mov     r13d, 0FFh
0x1400d1c53  mov     [rsp+698h+var_628], r13d
0x1400d1c58  mov     [rsp+698h+var_5A8], 1000000h
0x1400d1c63  xor     edx, edx; Val
0x1400d1c65  lea     r8d, [r12+6Dh]; Size
0x1400d1c6a  lea     rcx, [rsp+698h+var_620]; void *
0x1400d1c6f  call    memset_0
0x1400d1c74  mov     ebx, 14000000h
0x1400d1c79  mov     [rsp+698h+var_678], rbx
0x1400d1c7e  mov     r9d, [rsp+698h+var_590]
0x1400d1c86  lea     r8, aCannotRetrieve; "Cannot retrieve system default minimum "...
0x1400d1c8d  lea     rdx, [rsp+698h+var_648]
0x1400d1c92  lea     rcx, [rsp+698h+var_598]
0x1400d1c9a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400d1c9f  nop
0x1400d1ca0  lea     rcx, [rsp+698h+var_598]; this
0x1400d1ca8  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400d1cad  mov     eax, ebx
0x1400d1caf  mov     rcx, [rsp+698h+var_48]
0x1400d1cb7  xor     rcx, rsp; StackCookie
0x1400d1cba  call    __security_check_cookie
0x1400d1cbf  add     rsp, 660h
0x1400d1cc6  pop     r15
0x1400d1cc8  pop     r14
0x1400d1cca  pop     r13
0x1400d1ccc  pop     r12
0x1400d1cce  pop     rdi
0x1400d1ccf  pop     rsi
0x1400d1cd0  pop     rbx
0x1400d1cd1  retn
```
