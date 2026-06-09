# SystemMetricsAll_Get(SYSTEMMETRICSALL *)

- ea: `0x180015700`
- end: `0x1800159da`
- name: `?SystemMetricsAll_Get@@YAJPEAUSYSTEMMETRICSALL@@@Z`
- size: `730`
- prototype: `__int64 __fastcall(struct SYSTEMMETRICSALL *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000eeb0`
- `0x180010b20`
- `0x18003c510`

## callees

- `0x180015700`
- `0x1800358c0`

## import_xrefs

- `SHLWAPI!StrToIntW` at `0x18001597f`
- `SHLWAPI!StrToIntW` at `0x180015994`
- `SHLWAPI!StrToIntW` at `0x18001597f`
- `SHLWAPI!StrToIntW` at `0x180015994`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015837`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001595e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015837`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001595e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800157ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800158bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800157ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800158bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800157ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015825`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015900`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015944`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800157ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015825`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015900`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015944`
- `USER32!GetSysColor` at `0x180015882`
- `USER32!GetSysColor` at `0x180015882`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180015760`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180015848`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180015867`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180015760`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180015848`
- `UxTheme!__imp_ClassicGetSystemMetrics` at `0x180015867`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001573b`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180015755`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180015788`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x18001573b`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180015755`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180015788`

## pseudocode

```c
__int64 __fastcall SystemMetricsAll_Get(struct SYSTEMMETRICSALL *a1)
{
  int SystemMetrics; // eax
  int v3; // ebx
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  int i; // ebx
  DWORD SysColor; // eax
  __int64 v9; // rdx
  LSTATUS v10; // eax
  bool v11; // sf
  LSTATUS v12; // eax
  bool v13; // sf
  LSTATUS v14; // eax
  bool v15; // sf
  DWORD cbData; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-38h] BYREF
  WCHAR Data[16]; // [rsp+48h] [rbp-30h] BYREF

  *((_DWORD *)a1 + 2) = 504;
  hKey = 0;
  ClassicSystemParametersInfoW(41, 504, (char *)a1 + 8, 0);
  ClassicSystemParametersInfoW(31, 92, (char *)a1 + 512, 0);
  SystemMetrics = ClassicGetSystemMetrics(11);
  *((_DWORD *)a1 + 184) = SystemMetrics;
  *((_DWORD *)a1 + 185) = SystemMetrics / 2;
  ClassicSystemParametersInfoW(4130, 0, (char *)a1 + 748, 0);
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Desktop\\WindowMetrics", 0, 0x20019u, &hKey) )
  {
    cbData = 16;
    *(_OWORD *)Data = 0;
    if ( !RegQueryValueExW(hKey, L"Shell Icon Size", 0, 0, (LPBYTE)Data, &cbData) )
      *((_DWORD *)a1 + 184) = StrToIntW(Data);
    cbData = 16;
    if ( !RegQueryValueExW(hKey, L"Shell Small Icon Size", 0, 0, (LPBYTE)Data, &cbData) )
      *((_DWORD *)a1 + 185) = StrToIntW(Data);
    RegCloseKey(hKey);
  }
  v3 = *((_DWORD *)a1 + 184);
  v4 = ClassicGetSystemMetrics(38) - v3;
  *((_DWORD *)a1 + 182) = v4;
  if ( v4 < 0 )
    *((_DWORD *)a1 + 182) = 0;
  v5 = *((_DWORD *)a1 + 184);
  v6 = ClassicGetSystemMetrics(39) - v5;
  *((_DWORD *)a1 + 183) = v6;
  if ( v6 < 0 )
    *((_DWORD *)a1 + 183) = 0;
  for ( i = 0; i < 31; ++i )
  {
    SysColor = GetSysColor(i);
    v9 = (unsigned int)i;
    *((_DWORD *)a1 + v9 + 151) = SysColor;
  }
  phkResult = 0;
  v10 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Colors", 0, 0x20019u, &phkResult);
  v11 = v10 < 0;
  if ( v10 > 0 )
    v11 = 1;
  if ( !v11 )
  {
    cbData = 30;
    v12 = RegQueryValueExW(phkResult, L"MenuHilight", 0, 0, (LPBYTE)Data, &cbData);
    v13 = v12 < 0;
    if ( v12 > 0 )
      v13 = 1;
    if ( v13 )
      *((_DWORD *)a1 + 180) = *((_DWORD *)a1 + 164);
    cbData = 30;
    v14 = RegQueryValueExW(phkResult, L"MenuBar", 0, 0, (LPBYTE)Data, &cbData);
    v15 = v14 < 0;
    if ( v14 > 0 )
      v15 = 1;
    if ( v15 )
      *((_DWORD *)a1 + 181) = *((_DWORD *)a1 + 155);
    RegCloseKey(phkResult);
  }
  return 0;
}

```

## disassembly

```asm
0x180015700  push    rbp
0x180015702  push    rbx
0x180015703  push    rsi
0x180015704  push    rdi
0x180015705  mov     rbp, rsp
0x180015708  sub     rsp, 78h
0x18001570c  mov     rax, cs:__security_cookie
0x180015713  xor     rax, rsp
0x180015716  mov     [rbp+var_10], rax
0x18001571a  lea     r8, [rcx+8]
0x18001571e  mov     rdi, rcx
0x180015721  xor     esi, esi
0x180015723  mov     dword ptr [r8], 1F8h
0x18001572a  mov     ecx, 29h ; ')'
0x18001572f  mov     [rbp+hKey], rsi
0x180015733  xor     r9d, r9d
0x180015736  mov     edx, 1F8h
0x18001573b  call    cs:__imp_ClassicSystemParametersInfoW
0x180015741  lea     r8, [rdi+200h]
0x180015748  xor     r9d, r9d
0x18001574b  mov     edx, 5Ch ; '\'
0x180015750  mov     ecx, 1Fh
0x180015755  call    cs:__imp_ClassicSystemParametersInfoW
0x18001575b  mov     ecx, 0Bh
0x180015760  call    cs:__imp_ClassicGetSystemMetrics
0x180015766  mov     [rdi+2E0h], eax
0x18001576c  lea     r8, [rdi+2ECh]
0x180015773  cdq
0x180015774  xor     r9d, r9d
0x180015777  sub     eax, edx
0x180015779  mov     ecx, 1022h
0x18001577e  sar     eax, 1
0x180015780  xor     edx, edx
0x180015782  mov     [rdi+2E4h], eax
0x180015788  call    cs:__imp_ClassicSystemParametersInfoW
0x18001578e  lea     rax, [rbp+hKey]
0x180015792  mov     r9d, 20019h; samDesired
0x180015798  xor     r8d, r8d; ulOptions
0x18001579b  mov     [rsp+78h+phkResult], rax; phkResult
0x1800157a0  lea     rdx, pszSubKey; "Control Panel\\Desktop\\WindowMetrics"
0x1800157a7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800157ae  call    cs:__imp_RegOpenKeyExW
0x1800157b4  test    eax, eax
0x1800157b6  jnz     loc_18001583D
0x1800157bc  mov     rcx, [rbp+hKey]; hKey
0x1800157c0  lea     rax, [rbp+cbData]
0x1800157c4  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800157c9  lea     rdx, pszValue; "Shell Icon Size"
0x1800157d0  lea     rax, [rbp+Data]
0x1800157d4  mov     [rbp+cbData], 10h
0x1800157db  xorps   xmm0, xmm0
0x1800157de  mov     [rsp+78h+phkResult], rax; lpData
0x1800157e3  xor     r9d, r9d; lpType
0x1800157e6  xor     r8d, r8d; lpReserved
0x1800157e9  movups  xmmword ptr [rbp+Data], xmm0
0x1800157ed  call    cs:__imp_RegQueryValueExW
0x1800157f3  test    eax, eax
0x1800157f5  jz      loc_18001597B
0x1800157fb  mov     rcx, [rbp+hKey]; hKey
0x1800157ff  lea     rax, [rbp+cbData]
0x180015803  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180015808  lea     rdx, aShellSmallIcon; "Shell Small Icon Size"
0x18001580f  lea     rax, [rbp+Data]
0x180015813  mov     [rbp+cbData], 10h
0x18001581a  xor     r9d, r9d; lpType
0x18001581d  mov     [rsp+78h+phkResult], rax; lpData
0x180015822  xor     r8d, r8d; lpReserved
0x180015825  call    cs:__imp_RegQueryValueExW
0x18001582b  test    eax, eax
0x18001582d  jz      loc_180015990
0x180015833  mov     rcx, [rbp+hKey]; hKey
0x180015837  call    cs:__imp_RegCloseKey
0x18001583d  mov     ebx, [rdi+2E0h]
0x180015843  mov     ecx, 26h ; '&'
0x180015848  call    cs:__imp_ClassicGetSystemMetrics
0x18001584e  sub     eax, ebx
0x180015850  mov     [rdi+2D8h], eax
0x180015856  js      loc_1800159A5
0x18001585c  mov     ebx, [rdi+2E0h]
0x180015862  mov     ecx, 27h ; '''
0x180015867  call    cs:__imp_ClassicGetSystemMetrics
0x18001586d  sub     eax, ebx
0x18001586f  mov     [rdi+2DCh], eax
0x180015875  js      loc_1800159B0
0x18001587b  mov     ebx, esi
0x18001587d  nop     dword ptr [rax]
0x180015880  mov     ecx, ebx; nIndex
0x180015882  call    cs:__imp_GetSysColor
0x180015888  mov     edx, ebx
0x18001588a  inc     ebx
0x18001588c  mov     [rdi+rdx*4+25Ch], eax
0x180015893  cmp     ebx, 1Fh
0x180015896  jl      short loc_180015880
0x180015898  lea     rax, [rbp+var_38]
0x18001589c  mov     [rbp+var_38], rsi
0x1800158a0  mov     r9d, 20019h; samDesired
0x1800158a6  mov     [rsp+78h+phkResult], rax; phkResult
0x1800158ab  xor     r8d, r8d; ulOptions
0x1800158ae  lea     rdx, aControlPanelCo; "Control Panel\\Colors"
0x1800158b5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800158bc  call    cs:__imp_RegOpenKeyExW
0x1800158c2  test    eax, eax
0x1800158c4  jle     short loc_1800158D0
0x1800158c6  movzx   eax, ax
0x1800158c9  or      eax, 80070000h
0x1800158ce  test    eax, eax
0x1800158d0  js      loc_180015964
0x1800158d6  mov     rdx, cs:lpValueName; lpValueName
0x1800158dd  lea     rax, [rbp+cbData]
0x1800158e1  mov     rcx, [rbp+var_38]; hKey
0x1800158e5  xor     r9d, r9d; lpType
0x1800158e8  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800158ed  xor     r8d, r8d; lpReserved
0x1800158f0  lea     rax, [rbp+Data]
0x1800158f4  mov     [rbp+cbData], 1Eh
0x1800158fb  mov     [rsp+78h+phkResult], rax; lpData
0x180015900  call    cs:__imp_RegQueryValueExW
0x180015906  test    eax, eax
0x180015908  jle     short loc_180015914
0x18001590a  movzx   eax, ax
0x18001590d  or      eax, 80070000h
0x180015912  test    eax, eax
0x180015914  js      loc_1800159BB
0x18001591a  mov     rdx, cs:off_18006E6F0; lpValueName
0x180015921  lea     rax, [rbp+cbData]
0x180015925  mov     rcx, [rbp+var_38]; hKey
0x180015929  xor     r9d, r9d; lpType
0x18001592c  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180015931  xor     r8d, r8d; lpReserved
0x180015934  lea     rax, [rbp+Data]
0x180015938  mov     [rbp+cbData], 1Eh
0x18001593f  mov     [rsp+78h+phkResult], rax; lpData
0x180015944  call    cs:__imp_RegQueryValueExW
0x18001594a  test    eax, eax
0x18001594c  jle     short loc_180015958
0x18001594e  movzx   eax, ax
0x180015951  or      eax, 80070000h
0x180015956  test    eax, eax
0x180015958  js      short loc_1800159CC
0x18001595a  mov     rcx, [rbp+var_38]; hKey
0x18001595e  call    cs:__imp_RegCloseKey
0x180015964  xor     eax, eax
0x180015966  mov     rcx, [rbp+var_10]
0x18001596a  xor     rcx, rsp; StackCookie
0x18001596d  call    __security_check_cookie
0x180015972  add     rsp, 78h
0x180015976  pop     rdi
0x180015977  pop     rsi
0x180015978  pop     rbx
0x180015979  pop     rbp
0x18001597a  retn
0x18001597b  lea     rcx, [rbp+Data]; pszSrc
0x18001597f  call    cs:__imp_StrToIntW
0x180015985  mov     [rdi+2E0h], eax
0x18001598b  jmp     loc_1800157FB
0x180015990  lea     rcx, [rbp+Data]; pszSrc
0x180015994  call    cs:__imp_StrToIntW
0x18001599a  mov     [rdi+2E4h], eax
0x1800159a0  jmp     loc_180015833
0x1800159a5  mov     [rdi+2D8h], esi
0x1800159ab  jmp     loc_18001585C
0x1800159b0  mov     [rdi+2DCh], esi
0x1800159b6  jmp     loc_18001587B
0x1800159bb  mov     eax, [rdi+290h]
0x1800159c1  mov     [rdi+2D0h], eax
0x1800159c7  jmp     loc_18001591A
0x1800159cc  mov     eax, [rdi+26Ch]
0x1800159d2  mov     [rdi+2D4h], eax
0x1800159d8  jmp     short loc_18001595A
```
