# CVssMachineInformation::GetMinDiffAreaForSystem(void)

- ea: `0x180038fa8`
- end: `0x18003938e`
- name: `?GetMinDiffAreaForSystem@CVssMachineInformation@@SA_JXZ`
- size: `998`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180018544`
- `0x18001f47c`
- `0x180021bc4`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x1800377c4`
- `0x180038fa8`
- `0x180039394`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390da`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180039184`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180039184`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180039064`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180039064`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180039212`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180039212`

## string_xrefs

- `0x180038fcf`: `base\stor\vss\modules\registry\registry.cxx`
- `0x1800392d2`: `base\stor\vss\modules\registry\registry.cxx`
- `0x1800390c1`: `GetSystemWindowsDirectoryW(%s, %u): %u`
- `0x18003913b`: `GetSystemWindowsDirectoryW(%s, %u): %u [0x%08lx]`
- `0x1800391e3`: `GetVolumePathNameW(%s, %p, %u)`
- `0x180039260`: `GetVolumeNameForVolumeMountPointW( '%s', STRING_CCH_PARAM(wszSysVolumeName))`

## pseudocode

```c
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
}

```

## disassembly

```asm
0x180038fa8  mov     r11, rsp
0x180038fab  push    rbx
0x180038fac  push    rsi
0x180038fad  push    rdi
0x180038fae  push    r12
0x180038fb0  push    r13
0x180038fb2  push    r14
0x180038fb4  push    r15
0x180038fb6  sub     rsp, 660h
0x180038fbd  mov     rax, cs:__security_cookie
0x180038fc4  xor     rax, rsp
0x180038fc7  mov     [rsp+698h+var_48], rax
0x180038fcf  lea     rsi, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x180038fd6  mov     [r11-518h], rsi
0x180038fdd  lea     r14, aCvssmachineinf_0; "CVssMachineInformation::GetMinDiffAreaF"...
0x180038fe4  mov     [r11-510h], r14
0x180038feb  lea     r15, aRegregsc; "REGREGSC"
0x180038ff2  mov     [r11-508h], r15
0x180038ff9  mov     [rsp+698h+var_500], 6C7h
0x180039004  mov     r12d, 0Bh
0x18003900a  mov     [r11-4FCh], r12d
0x180039011  mov     r13d, 0FFh
0x180039017  mov     [r11-4F8h], r13d
0x18003901e  xor     edi, edi
0x180039020  mov     [rsp+698h+var_478], 1000000h
0x18003902b  lea     ebx, [rdi+78h]
0x18003902e  mov     r8d, ebx; Size
0x180039031  xor     edx, edx; Val
0x180039033  lea     rcx, [r11-4F0h]; void *
0x18003903a  call    memset_0
0x18003903f  xor     r8d, r8d
0x180039042  lea     rdx, [rsp+698h+szVolumeName]
0x18003904a  lea     rcx, [rsp+698h+var_598]
0x180039052  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180039057  nop
0x180039058  lea     edx, [r13+6]; uSize
0x18003905c  lea     rcx, [rsp+698h+Buffer]; lpBuffer
0x180039064  call    cs:__imp_GetSystemWindowsDirectoryW
0x18003906a  mov     [rsp+698h+var_650], eax
0x18003906e  test    eax, eax
0x180039070  jnz     short loc_1800390DA
0x180039072  mov     [rsp+698h+var_648], rsi
0x180039077  mov     [rsp+698h+var_640], r14
0x18003907c  mov     [rsp+698h+var_638], r15
0x180039081  mov     [rsp+698h+var_630], 6D0h
0x180039089  mov     [rsp+698h+var_62C], r12d
0x18003908e  mov     [rsp+698h+var_628], r13d
0x180039093  mov     [rsp+698h+var_5A8], 1000000h
0x18003909e  mov     r8d, ebx; Size
0x1800390a1  xor     edx, edx; Val
0x1800390a3  lea     rcx, [rsp+698h+var_620]; void *
0x1800390a8  call    memset_0
0x1800390ad  mov     dword ptr [rsp+698h+var_670], edi
0x1800390b1  mov     dword ptr [rsp+698h+var_678], 105h
0x1800390b9  lea     r9, [rsp+698h+Buffer]
0x1800390c1  lea     r8, aGetsystemwindo_0; "GetSystemWindowsDirectoryW(%s, %u): %u"
0x1800390c8  lea     rdx, [rsp+698h+var_648]
0x1800390cd  lea     rcx, [rsp+698h+var_598]
0x1800390d5  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1800390da  call    cs:__imp_GetLastError
0x1800390e0  mov     ebx, eax
0x1800390e2  mov     [rsp+698h+var_648], rsi
0x1800390e7  mov     [rsp+698h+var_640], r14
0x1800390ec  mov     [rsp+698h+var_638], r15
0x1800390f1  mov     [rsp+698h+var_630], 6D2h
0x1800390f9  mov     [rsp+698h+var_62C], r12d
0x1800390fe  mov     [rsp+698h+var_628], r13d
0x180039103  mov     [rsp+698h+var_5A8], 1000000h
0x18003910e  xor     edx, edx; Val
0x180039110  lea     r8d, [rdx+78h]; Size
0x180039114  lea     rcx, [rsp+698h+var_620]; void *
0x180039119  call    memset_0
0x18003911e  mov     [rsp+698h+var_668], ebx
0x180039122  mov     eax, [rsp+698h+var_650]
0x180039126  mov     dword ptr [rsp+698h+var_670], eax
0x18003912a  mov     ebx, 105h
0x18003912f  mov     dword ptr [rsp+698h+var_678], ebx
0x180039133  lea     r9, [rsp+698h+Buffer]
0x18003913b  lea     r8, aGetsystemwindo; "GetSystemWindowsDirectoryW(%s, %u): %u "...
0x180039142  lea     rdx, [rsp+698h+var_648]
0x180039147  lea     rcx, [rsp+698h+var_598]
0x18003914f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180039154  mov     [rsp+698h+szVolumePathName], di
0x18003915c  xor     edx, edx; Val
0x18003915e  mov     r8d, 208h; Size
0x180039164  lea     rcx, [rsp+698h+var_466]; void *
0x18003916c  call    memset_0
0x180039171  mov     r8d, ebx; cchBufferLength
0x180039174  lea     rdx, [rsp+698h+szVolumePathName]; lpszVolumePathName
0x18003917c  lea     rcx, [rsp+698h+Buffer]; lpszFileName
0x180039184  call    cs:__imp_GetVolumePathNameW
0x18003918a  test    eax, eax
0x18003918c  jnz     short loc_1800391FC
0x18003918e  mov     [rsp+698h+var_648], rsi
0x180039193  mov     [rsp+698h+var_640], r14
0x180039198  mov     [rsp+698h+var_638], r15
0x18003919d  mov     [rsp+698h+var_630], 6DBh
0x1800391a5  mov     [rsp+698h+var_62C], r12d
0x1800391aa  mov     [rsp+698h+var_628], r13d
0x1800391af  mov     [rsp+698h+var_5A8], 1000000h
0x1800391ba  xor     edx, edx; Val
0x1800391bc  lea     r8d, [rax+78h]; Size
0x1800391c0  lea     rcx, [rsp+698h+var_620]; void *
0x1800391c5  call    memset_0
0x1800391ca  mov     dword ptr [rsp+698h+var_670], ebx
0x1800391ce  lea     rax, [rsp+698h+szVolumePathName]
0x1800391d6  mov     [rsp+698h+var_678], rax
0x1800391db  lea     r9, [rsp+698h+Buffer]
0x1800391e3  lea     r8, aGetvolumepathn_1; "GetVolumePathNameW(%s, %p, %u)"
0x1800391ea  lea     rdx, [rsp+698h+var_648]
0x1800391ef  lea     rcx, [rsp+698h+var_598]
0x1800391f7  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1800391fc  mov     r8d, 32h ; '2'; cchBufferLength
0x180039202  lea     rdx, [rsp+698h+szVolumeName]; lpszVolumeName
0x18003920a  lea     rcx, [rsp+698h+szVolumePathName]; lpszVolumeMountPoint
0x180039212  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180039218  mov     [rsp+698h+var_648], rsi
0x18003921d  mov     [rsp+698h+var_640], r14
0x180039222  mov     [rsp+698h+var_638], r15
0x180039227  mov     [rsp+698h+var_62C], r12d
0x18003922c  mov     [rsp+698h+var_628], r13d
0x180039231  mov     [rsp+698h+var_5A8], 1000000h
0x18003923c  xor     edx, edx; Val
0x18003923e  lea     r8d, [rdx+78h]; Size
0x180039242  lea     rcx, [rsp+698h+var_620]; void *
0x180039247  test    eax, eax
0x180039249  jnz     short loc_180039279
0x18003924b  mov     [rsp+698h+var_630], 6E1h
0x180039253  call    memset_0
0x180039258  lea     r9, [rsp+698h+szVolumePathName]
0x180039260  lea     r8, aGetvolumenamef_5; "GetVolumeNameForVolumeMountPointW( '%s'"...
0x180039267  lea     rdx, [rsp+698h+var_648]
0x18003926c  lea     rcx, [rsp+698h+var_598]
0x180039274  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x180039279  mov     [rsp+698h+var_630], 6E3h
0x180039281  call    memset_0
0x180039286  lea     r9, [rsp+698h+szVolumeName]
0x18003928e  lea     r8, aSystemVolumeNa; "System volume name: %s"
0x180039295  lea     rdx, [rsp+698h+var_648]
0x18003929a  lea     rcx, [rsp+698h+var_598]
0x1800392a2  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800392a7  lea     rcx, [rsp+698h+szVolumeName]; unsigned __int16 *
0x1800392af  call    ?GetMinDiffAreaOnVolume@CVssMachineInformation@@SA_JPEBG@Z; CVssMachineInformation::GetMinDiffAreaOnVolume(ushort const *)
0x1800392b4  mov     rbx, rax
0x1800392b7  lea     rcx, [rsp+698h+var_598]; this
0x1800392bf  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800392c4  mov     rax, rbx
0x1800392c7  jmp     loc_18003936B
0x1800392cc  jmp     short loc_1800392D2
0x1800392ce  jmp     short loc_1800392D2
0x1800392d0  jmp     short $+2
0x1800392d2  lea     rsi, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x1800392d9  mov     [rsp+698h+var_648], rsi
0x1800392de  lea     r14, aCvssmachineinf_0; "CVssMachineInformation::GetMinDiffAreaF"...
0x1800392e5  mov     [rsp+698h+var_640], r14
0x1800392ea  lea     r15, aRegregsc; "REGREGSC"
0x1800392f1  mov     [rsp+698h+var_638], r15
0x1800392f6  mov     [rsp+698h+var_630], 6E9h
0x1800392fe  mov     r12d, 0Bh
0x180039304  mov     [rsp+698h+var_62C], r12d
0x180039309  mov     r13d, 0FFh
0x18003930f  mov     [rsp+698h+var_628], r13d
0x180039314  mov     [rsp+698h+var_5A8], 1000000h
0x18003931f  xor     edx, edx; Val
0x180039321  lea     r8d, [r12+6Dh]; Size
0x180039326  lea     rcx, [rsp+698h+var_620]; void *
0x18003932b  call    memset_0
0x180039330  mov     ebx, 14000000h
0x180039335  mov     [rsp+698h+var_678], rbx
0x18003933a  mov     r9d, [rsp+698h+var_590]
0x180039342  lea     r8, aCannotRetrieve; "Cannot retrieve system default minimum "...
0x180039349  lea     rdx, [rsp+698h+var_648]
0x18003934e  lea     rcx, [rsp+698h+var_598]
0x180039356  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003935b  nop
0x18003935c  lea     rcx, [rsp+698h+var_598]; this
0x180039364  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180039369  mov     eax, ebx
0x18003936b  mov     rcx, [rsp+698h+var_48]
0x180039373  xor     rcx, rsp; StackCookie
0x180039376  call    __security_check_cookie
0x18003937b  add     rsp, 660h
0x180039382  pop     r15
0x180039384  pop     r14
0x180039386  pop     r13
0x180039388  pop     r12
0x18003938a  pop     rdi
0x18003938b  pop     rsi
0x18003938c  pop     rbx
0x18003938d  retn
```
