# Throttle(ulong,ulong,ulong,ulong,ulong)

- ea: `0x18000fac0`
- end: `0x18000ff4c`
- name: `?Throttle@@YAJKKKKK@Z`
- size: `1164`
- prototype: `int(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000fa30`
- `0x18000fac0`
- `0x18001016c`
- `0x1800101cc`
- `0x18002a110`
- `0x18002f6b4`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000fe6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000fe6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fcac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fcac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAdjustment` at `0x18000ff17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAdjustment` at `0x18000ff17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe1a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fbd0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fc7b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fbd0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fc7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fee7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fee7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fed2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fed2`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetLastInputInfo` at `0x18000fc9e`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetLastInputInfo` at `0x18000fc9e`

## string_xrefs

- `0x18000fecb`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Throttle(int a1, int a2, __int64 a3, DWORD a4, unsigned int a5)
{
  int v6; // r15d
  __int64 v9; // rbx
  unsigned int v10; // edi
  DWORD v11; // r13d
  unsigned int v12; // edx
  int v13; // r15d
  unsigned int v14; // eax
  __int64 v15; // r14
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  DWORD TickCount; // eax
  __int64 v20; // r13
  int v21; // eax
  HMODULE ModuleHandleW; // rax
  int v23; // [rsp+40h] [rbp-C0h]
  DWORD TimeAdjustment; // [rsp+44h] [rbp-BCh] BYREF
  WINBOOL TimeAdjustmentDisabled; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-B0h]
  tagLASTINPUTINFO plii; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v32; // [rsp+70h] [rbp-90h]
  unsigned int v33; // [rsp+74h] [rbp-8Ch]
  unsigned int v34; // [rsp+78h] [rbp-88h]
  __int64 v35; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[752]; // [rsp+C0h] [rbp-40h] BYREF

  v6 = a3;
  v33 = a3;
  if ( !MyNtQuerySystemInformation )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    if ( !ModuleHandleW )
      return 2147749889LL;
    MyNtQuerySystemInformation = (int (*)(enum _SYSTEM_INFORMATION_CLASS, void *, unsigned int, unsigned int *))GetProcAddress(ModuleHandleW, "NtQuerySystemInformation");
    if ( !MyNtQuerySystemInformation )
      return 2147749889LL;
  }
  if ( !TimeIncrement )
  {
    TimeAdjustmentDisabled = 0;
    TimeAdjustment = 0;
    if ( !GetSystemTimeAdjustment(&TimeAdjustment, &TimeIncrement, &TimeAdjustmentDisabled) )
      return 2147749889LL;
  }
  if ( !dword_180070024 )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    dword_180070024 = SystemInfo.dwPageSize;
  }
  if ( (a1 & 0xFFFFFFFC) != 0 || !a4 )
    return 2147749896LL;
  plii.dwTime = 0;
  plii.cbSize = 8;
  v35 = 0;
  v31 = 0;
  v30 = 4;
  v26 = 0;
  if ( DLRegOpenKeyExW(-2147483646, (__int64)L"Software\\Microsoft\\WBEM\\CIMOM", a3, 0x20019u, (__int64)&v35) )
    return 2147749889LL;
  LODWORD(v29) = 0;
  v9 = v35;
  v36 = v35;
  v10 = 2;
  v11 = a1 & 2;
  TimeAdjustment = v11;
  if ( (a1 & 2) == 0 )
    goto LABEL_11;
  if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _BYTE *, __int64, _QWORD))MyNtQuerySystemInformation)(
                        2,
                        v38,
                        376,
                        0) )
  {
    LODWORD(v29) = 1;
    Sleep(0x96u);
LABEL_11:
    v12 = a5 / a4;
    v34 = a5 / a4;
    v32 = 10000 * a2;
    v27 = v6 + 1;
    v13 = 0;
    v23 = 0;
    v14 = 0;
    while ( 1 )
    {
      TimeAdjustmentDisabled = v14;
      if ( v14 >= v12 )
      {
        if ( v9 )
          DLRegCloseKey(v9);
        return 1;
      }
      v15 = v35;
      ProcAddress = (FARPROC)qword_1800703F0;
      if ( qword_1800703F0 )
        goto LABEL_14;
      if ( (unsigned int)DLpLoadRegistryDll() )
        goto LABEL_16;
      ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegQueryValueExW");
      qword_1800703F0 = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_14:
        LastError = ((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, int *, int *, int *))ProcAddress)(
                      v15,
                      L"ThrottleDrege",
                      0,
                      &v31,
                      &v26,
                      &v30);
      else
        LastError = GetLastError();
      if ( !LastError && !v26 )
      {
        if ( v9 )
          DLRegCloseKey(v9);
        return 8;
      }
LABEL_16:
      if ( (a1 & 1) == 0 || !(unsigned __int8)IsGetLastInputInfoPresent() )
        goto LABEL_17;
      if ( !GetLastInputInfo(&plii) )
        break;
      TickCount = GetTickCount();
      if ( TickCount >= plii.dwTime )
      {
        if ( TimeIncrement * (TickCount - plii.dwTime) >= v32 )
        {
          if ( (a1 & 0xFFFFFFFE) == 0 )
            goto LABEL_61;
          v13 = 1;
        }
LABEL_17:
        if ( (a1 & 3) == 3 && !v13 )
        {
LABEL_19:
          Sleep(a4);
          goto LABEL_20;
        }
        if ( v11 )
        {
          v20 = 376LL * (unsigned int)v29;
          if ( (unsigned int)((__int64 (__fastcall *)(__int64, _BYTE *, __int64, _QWORD))MyNtQuerySystemInformation)(
                               2,
                               &v38[v20],
                               376,
                               0) )
          {
            if ( v9 )
              DLRegCloseKey(v9);
            return 2147749889LL;
          }
          v27 = (v27
               + 1000
               * (*(_DWORD *)&v38[v20 + 24]
                + *(_DWORD *)&v38[v20 + 16]
                + *(_DWORD *)&v38[v20 + 8]
                + dword_180070024
                * (*(_DWORD *)&v38[v20 + 80]
                 + *(_DWORD *)&v38[v20 + 88]
                 + *(_DWORD *)&v38[v20 + 96]
                 + *(_DWORD *)&v38[v20 + 104]
                 - *(_DWORD *)&v38[376 * (((_BYTE)v29 - 1) & 1) + 104]
                 - *(_DWORD *)&v38[376 * (((_BYTE)v29 - 1) & 1) + 96]
                 - *(_DWORD *)&v38[376 * (((_BYTE)v29 - 1) & 1) + 88]
                 - *(_DWORD *)&v38[376 * (((_BYTE)v29 - 1) & 1) + 80])
                - *(_DWORD *)&v38[376 * (((_BYTE)v29 - 1) & 1) + 8]
                - *(_DWORD *)&v38[376 * (((_BYTE)v29 - 1) & 1) + 16]
                - *(_DWORD *)&v38[376 * (((_BYTE)v29 - 1) & 1) + 24])
               / a4) >> 1;
          v29 = ((_BYTE)v29 - 1) & 1;
          if ( v27 >= v33 )
          {
            v11 = TimeAdjustment;
            goto LABEL_35;
          }
          if ( (a1 & 0xFFFFFFFD) == 0 )
          {
            v10 = 4;
            goto LABEL_61;
          }
          v21 = 1;
          v23 = 1;
          v11 = TimeAdjustment;
        }
        else
        {
LABEL_35:
          v21 = v23;
        }
        if ( (a1 & 3) != 0 )
        {
          if ( v13 && v21 )
          {
            if ( v9 )
              DLRegCloseKey(v9);
            return 6;
          }
          v13 = 0;
          v23 = 0;
        }
        goto LABEL_19;
      }
LABEL_20:
      v14 = TimeAdjustmentDisabled + 1;
      v12 = v34;
    }
  }
  v10 = -2147217407;
LABEL_61:
  CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v36);
  return v10;
}

```

## disassembly

```asm
0x18000fac0  push    rbp
0x18000fac2  push    rbx
0x18000fac3  push    rsi
0x18000fac4  push    rdi
0x18000fac5  push    r12
0x18000fac7  push    r13
0x18000fac9  push    r14
0x18000facb  push    r15
0x18000facd  lea     rbp, [rsp-2C8h]
0x18000fad5  sub     rsp, 3C8h
0x18000fadc  mov     rax, cs:__security_cookie
0x18000fae3  xor     rax, rsp
0x18000fae6  mov     [rbp+300h+var_50], rax
0x18000faed  mov     r12d, r9d
0x18000faf0  mov     r15d, r8d
0x18000faf3  mov     [rsp+400h+var_38C], r8d
0x18000faf8  mov     r14d, edx
0x18000fafb  mov     esi, ecx
0x18000fafd  xor     ebx, ebx
0x18000faff  cmp     cs:?MyNtQuerySystemInformation@@3P6AJW4_SYSTEM_INFORMATION_CLASS@@PEAXKPEAK@ZEA, rbx; long (*MyNtQuerySystemInformation)(_SYSTEM_INFORMATION_CLASS,void *,ulong,ulong *)
0x18000fb06  jz      loc_18000FECB
0x18000fb0c  cmp     cs:TimeIncrement, ebx
0x18000fb12  jz      loc_18000FEFE
0x18000fb18  cmp     cs:dword_180070024, ebx
0x18000fb1e  jz      loc_18000FE5A
0x18000fb24  test    esi, 0FFFFFFFCh
0x18000fb2a  jnz     loc_18000FF42
0x18000fb30  test    r12d, r12d
0x18000fb33  jz      loc_18000FF42
0x18000fb39  mov     qword ptr [rsp+400h+plii.cbSize], rbx
0x18000fb3e  mov     [rsp+400h+plii.cbSize], 8
0x18000fb46  mov     [rbp+300h+var_380], rbx
0x18000fb4a  mov     [rsp+400h+var_394], ebx
0x18000fb4e  mov     [rsp+400h+var_398], 4
0x18000fb56  mov     [rsp+400h+var_3B4], ebx
0x18000fb5a  lea     rax, [rbp+300h+var_380]
0x18000fb5e  mov     [rsp+400h+var_3E0], rax
0x18000fb63  mov     r9d, 20019h
0x18000fb69  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WBEM\\CIMOM"
0x18000fb70  mov     rcx, 0FFFFFFFF80000002h
0x18000fb77  call    DLRegOpenKeyExW
0x18000fb7c  test    eax, eax
0x18000fb7e  jnz     loc_18000FEC1
0x18000fb84  mov     dword ptr [rsp+400h+var_3A0], ebx
0x18000fb88  mov     rbx, [rbp+300h+var_380]
0x18000fb8c  mov     [rbp+300h+var_378], rbx
0x18000fb90  mov     r13d, esi
0x18000fb93  lea     edi, [rax+2]
0x18000fb96  and     r13d, edi
0x18000fb99  mov     [rsp+400h+TimeAdjustment], r13d
0x18000fb9e  jz      short loc_18000FBD6
0x18000fba0  xor     r9d, r9d
0x18000fba3  mov     r8d, 178h
0x18000fba9  lea     rdx, [rbp+300h+var_340]
0x18000fbad  mov     ecx, edi
0x18000fbaf  mov     rax, cs:?MyNtQuerySystemInformation@@3P6AJW4_SYSTEM_INFORMATION_CLASS@@PEAXKPEAK@ZEA; long (*MyNtQuerySystemInformation)(_SYSTEM_INFORMATION_CLASS,void *,ulong,ulong *)
0x18000fbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbbb  test    eax, eax
0x18000fbbd  jnz     loc_18000FF26
0x18000fbc3  mov     dword ptr [rsp+400h+var_3A0], 1
0x18000fbcb  mov     ecx, 96h; dwMilliseconds
0x18000fbd0  call    cs:__imp_Sleep
0x18000fbd6  xor     edx, edx
0x18000fbd8  mov     eax, [rbp+300h+arg_20]
0x18000fbde  div     r12d
0x18000fbe1  mov     edx, eax
0x18000fbe3  mov     [rsp+400h+var_388], eax
0x18000fbe7  imul    eax, r14d, 2710h
0x18000fbee  mov     [rsp+400h+var_390], eax
0x18000fbf2  lea     eax, [r15+1]
0x18000fbf6  mov     [rsp+400h+var_3B0], eax
0x18000fbfa  xor     r15d, r15d
0x18000fbfd  xor     ecx, ecx
0x18000fbff  mov     [rsp+400h+var_3C0], ecx
0x18000fc03  xor     eax, eax
0x18000fc05  mov     [rsp+400h+TimeAdjustmentDisabled], eax
0x18000fc09  cmp     eax, edx
0x18000fc0b  jnb     loc_18000FE25
0x18000fc11  mov     r14, [rbp+300h+var_380]
0x18000fc15  mov     rax, cs:qword_1800703F0
0x18000fc1c  test    rax, rax
0x18000fc1f  jz      loc_18000FDE9
0x18000fc25  lea     rcx, [rsp+400h+var_398]
0x18000fc2a  mov     [rsp+400h+var_3D8], rcx
0x18000fc2f  lea     rcx, [rsp+400h+var_3B4]
0x18000fc34  mov     [rsp+400h+var_3E0], rcx
0x18000fc39  lea     r9, [rsp+400h+var_394]
0x18000fc3e  xor     r8d, r8d
0x18000fc41  lea     rdx, aThrottledrege; "ThrottleDrege"
0x18000fc48  mov     rcx, r14
0x18000fc4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc50  test    eax, eax
0x18000fc52  jz      loc_18000FCDD
0x18000fc58  test    sil, 1
0x18000fc5c  jnz     short loc_18000FC90
0x18000fc5e  mov     r14d, esi
0x18000fc61  and     r14d, 3
0x18000fc65  cmp     r14d, 3
0x18000fc69  jnz     loc_18000FCFF
0x18000fc6f  test    r15d, r15d
0x18000fc72  jnz     loc_18000FCFF
0x18000fc78  mov     ecx, r12d; dwMilliseconds
0x18000fc7b  call    cs:__imp_Sleep
0x18000fc81  mov     eax, [rsp+400h+TimeAdjustmentDisabled]
0x18000fc85  inc     eax
0x18000fc87  mov     edx, [rsp+400h+var_388]
0x18000fc8b  jmp     loc_18000FC05
0x18000fc90  call    IsGetLastInputInfoPresent
0x18000fc95  test    al, al
0x18000fc97  jz      short loc_18000FC5E
0x18000fc99  lea     rcx, [rsp+400h+plii]; plii
0x18000fc9e  call    cs:__imp_GetLastInputInfo
0x18000fca4  test    eax, eax
0x18000fca6  jz      loc_18000FF26
0x18000fcac  call    cs:__imp_GetTickCount
0x18000fcb2  cmp     eax, [rsp+400h+plii.dwTime]
0x18000fcb6  jb      short loc_18000FC81
0x18000fcb8  sub     eax, [rsp+400h+plii.dwTime]
0x18000fcbc  imul    eax, cs:TimeIncrement
0x18000fcc3  cmp     eax, [rsp+400h+var_390]
0x18000fcc7  jb      short loc_18000FC5E
0x18000fcc9  test    esi, 0FFFFFFFEh
0x18000fccf  jz      loc_18000FF32
0x18000fcd5  mov     r15d, 1
0x18000fcdb  jmp     short loc_18000FC5E
0x18000fcdd  cmp     [rsp+400h+var_3B4], 0
0x18000fce2  jnz     loc_18000FC58
0x18000fce8  test    rbx, rbx
0x18000fceb  jz      short loc_18000FCF5
0x18000fced  mov     rcx, rbx
0x18000fcf0  call    DLRegCloseKey
0x18000fcf5  mov     eax, 8
0x18000fcfa  jmp     loc_18000FE37
0x18000fcff  test    r13d, r13d
0x18000fd02  jz      loc_18000FDC1
0x18000fd08  mov     ecx, dword ptr [rsp+400h+var_3A0]
0x18000fd0c  imul    r13, rcx, 178h
0x18000fd13  lea     rdx, [rbp+300h+var_340]
0x18000fd17  add     rdx, r13
0x18000fd1a  xor     r9d, r9d
0x18000fd1d  mov     r8d, 178h
0x18000fd23  mov     ecx, edi
0x18000fd25  mov     rax, cs:?MyNtQuerySystemInformation@@3P6AJW4_SYSTEM_INFORMATION_CLASS@@PEAXKPEAK@ZEA; long (*MyNtQuerySystemInformation)(_SYSTEM_INFORMATION_CLASS,void *,ulong,ulong *)
0x18000fd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd31  test    eax, eax
0x18000fd33  jnz     loc_18000FEB4
0x18000fd39  mov     r8, [rsp+400h+var_3A0]
0x18000fd3e  dec     r8d
0x18000fd41  mov     eax, r8d
0x18000fd44  and     eax, 1
0x18000fd47  imul    rcx, rax, 178h
0x18000fd4e  mov     eax, [rbp+r13+300h+var_2D8]
0x18000fd53  sub     eax, [rbp+rcx+300h+var_2D8]
0x18000fd57  sub     eax, [rbp+rcx+300h+var_2E0]
0x18000fd5b  sub     eax, [rbp+rcx+300h+var_2E8]
0x18000fd5f  sub     eax, [rbp+rcx+300h+var_2F0]
0x18000fd63  add     eax, [rbp+r13+300h+var_2E0]
0x18000fd68  add     eax, [rbp+r13+300h+var_2E8]
0x18000fd6d  add     eax, [rbp+r13+300h+var_2F0]
0x18000fd72  imul    eax, cs:dword_180070024
0x18000fd79  sub     eax, [rbp+rcx+300h+var_338]
0x18000fd7d  sub     eax, [rbp+rcx+300h+var_330]
0x18000fd81  sub     eax, [rbp+rcx+300h+var_328]
0x18000fd85  add     eax, [rbp+r13+300h+var_338]
0x18000fd8a  add     eax, [rbp+r13+300h+var_330]
0x18000fd8f  add     eax, [rbp+r13+300h+var_328]
0x18000fd94  imul    eax, 3E8h
0x18000fd9a  xor     edx, edx
0x18000fd9c  div     r12d
0x18000fd9f  add     eax, [rsp+400h+var_3B0]
0x18000fda3  shr     eax, 1
0x18000fda5  mov     [rsp+400h+var_3B0], eax
0x18000fda9  and     r8d, 1
0x18000fdad  mov     [rsp+400h+var_3A0], r8
0x18000fdb2  cmp     eax, [rsp+400h+var_38C]
0x18000fdb6  jb      loc_18000FE81
0x18000fdbc  mov     r13d, [rsp+400h+TimeAdjustment]
0x18000fdc1  mov     eax, [rsp+400h+var_3C0]
0x18000fdc5  test    r14d, r14d
0x18000fdc8  jz      loc_18000FC78
0x18000fdce  test    r15d, r15d
0x18000fdd1  jz      short loc_18000FDDB
0x18000fdd3  test    eax, eax
0x18000fdd5  jnz     loc_18000FEA0
0x18000fddb  xor     r15d, r15d
0x18000fdde  xor     ecx, ecx
0x18000fde0  mov     [rsp+400h+var_3C0], ecx
0x18000fde4  jmp     loc_18000FC78
0x18000fde9  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18000fdee  test    eax, eax
0x18000fdf0  jnz     loc_18000FC58
0x18000fdf6  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18000fdfd  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18000fe04  call    cs:__imp_GetProcAddress
0x18000fe0a  mov     cs:qword_1800703F0, rax
0x18000fe11  test    rax, rax
0x18000fe14  jnz     loc_18000FC25
0x18000fe1a  call    cs:__imp_GetLastError
0x18000fe20  jmp     loc_18000FC50
0x18000fe25  test    rbx, rbx
0x18000fe28  jz      short loc_18000FE32
0x18000fe2a  mov     rcx, rbx
0x18000fe2d  call    DLRegCloseKey
0x18000fe32  mov     eax, 1
0x18000fe37  mov     rcx, [rbp+300h+var_50]
0x18000fe3e  xor     rcx, rsp; StackCookie
0x18000fe41  call    __security_check_cookie
0x18000fe46  add     rsp, 3C8h
0x18000fe4d  pop     r15
0x18000fe4f  pop     r14
0x18000fe51  pop     r13
0x18000fe53  pop     r12
0x18000fe55  pop     rdi
0x18000fe56  pop     rsi
0x18000fe57  pop     rbx
0x18000fe58  pop     rbp
0x18000fe59  retn
0x18000fe5a  xorps   xmm0, xmm0
0x18000fe5d  movups  xmmword ptr [rbp+300h+SystemInfo], xmm0
0x18000fe61  movups  xmmword ptr [rbp+300h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000fe65  movups  xmmword ptr [rbp+300h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000fe69  lea     rcx, [rbp+300h+SystemInfo]; lpSystemInfo
0x18000fe6d  call    cs:__imp_GetSystemInfo
0x18000fe73  mov     eax, [rbp+300h+SystemInfo.dwPageSize]
0x18000fe76  mov     cs:dword_180070024, eax
0x18000fe7c  jmp     loc_18000FB24
0x18000fe81  test    esi, 0FFFFFFFDh
0x18000fe87  jz      loc_18000FF2D
0x18000fe8d  mov     eax, 1
0x18000fe92  mov     [rsp+400h+var_3C0], eax
0x18000fe96  mov     r13d, [rsp+400h+TimeAdjustment]
0x18000fe9b  jmp     loc_18000FDC5
0x18000fea0  test    rbx, rbx
0x18000fea3  jz      short loc_18000FEAD
0x18000fea5  mov     rcx, rbx
0x18000fea8  call    DLRegCloseKey
0x18000fead  mov     eax, 6
0x18000feb2  jmp     short loc_18000FE37
0x18000feb4  test    rbx, rbx
0x18000feb7  jz      short loc_18000FEC1
0x18000feb9  mov     rcx, rbx
0x18000febc  call    DLRegCloseKey
0x18000fec1  mov     eax, 80041001h
0x18000fec6  jmp     loc_18000FE37
0x18000fecb  lea     rcx, ModuleName; "ntdll.dll"
0x18000fed2  call    cs:__imp_GetModuleHandleW
0x18000fed8  test    rax, rax
0x18000fedb  jz      short loc_18000FEC1
0x18000fedd  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x18000fee4  mov     rcx, rax; hModule
0x18000fee7  call    cs:__imp_GetProcAddress
0x18000feed  mov     cs:?MyNtQuerySystemInformation@@3P6AJW4_SYSTEM_INFORMATION_CLASS@@PEAXKPEAK@ZEA, rax; long (*MyNtQuerySystemInformation)(_SYSTEM_INFORMATION_CLASS,void *,ulong,ulong *)
0x18000fef4  test    rax, rax
0x18000fef7  jz      short loc_18000FEC1
0x18000fef9  jmp     loc_18000FB0C
0x18000fefe  mov     [rsp+400h+TimeAdjustmentDisabled], ebx
0x18000ff02  mov     [rsp+400h+TimeAdjustment], ebx
0x18000ff06  lea     r8, [rsp+400h+TimeAdjustmentDisabled]; lpTimeAdjustmentDisabled
0x18000ff0b  lea     rdx, TimeIncrement; lpTimeIncrement
0x18000ff12  lea     rcx, [rsp+400h+TimeAdjustment]; lpTimeAdjustment
0x18000ff17  call    cs:__imp_GetSystemTimeAdjustment
0x18000ff1d  test    eax, eax
0x18000ff1f  jz      short loc_18000FEC1
0x18000ff21  jmp     loc_18000FB18
0x18000ff26  mov     edi, 80041001h
0x18000ff2b  jmp     short loc_18000FF32
0x18000ff2d  mov     edi, 4
0x18000ff32  lea     rcx, [rbp+300h+var_378]; this
0x18000ff36  call    ??1CRegCloseMe@@QEAA@XZ; CRegCloseMe::~CRegCloseMe(void)
0x18000ff3b  mov     eax, edi
0x18000ff3d  jmp     loc_18000FE37
0x18000ff42  mov     eax, 80041008h
0x18000ff47  jmp     loc_18000FE37
```
