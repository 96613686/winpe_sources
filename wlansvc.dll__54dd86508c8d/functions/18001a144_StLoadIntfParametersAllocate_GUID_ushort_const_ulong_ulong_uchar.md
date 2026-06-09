# StLoadIntfParametersAllocate(_GUID *,ushort const *,ulong,ulong *,uchar * *)

- ea: `0x18001a144`
- end: `0x18001a611`
- name: `?StLoadIntfParametersAllocate@@YAKPEAU_GUID@@PEBGKPEAKPEAPEAE@Z`
- size: `1229`
- prototype: `unsigned int(struct _GUID *, const unsigned __int16 *, unsigned int, unsigned int *, unsigned __int8 **)`
- caller_count: `5`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008eaa0`
- `0x1800ad0f8`
- `0x1800f2280`
- `0x18011dcf8`
- `0x18011e7c8`

## callees

- `0x18000a994`
- `0x18000aa0c`
- `0x180019820`
- `0x180019bd0`
- `0x180019c60`
- `0x18001a144`
- `0x18001c9cc`
- `0x1800843d0`
- `0x1800843f4`
- `0x1800b2a88`
- `0x180104ba8`
- `0x180106340`
- `0x180107330`
- `0x180108234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001a1b9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001a1b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a285`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a43f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a586`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a285`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a43f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a586`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a47f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a47f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a2c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a2c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001a1d3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001a2fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001a316`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001a32e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001a1d3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001a2fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001a316`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001a32e`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x18001a4f2`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x18001a4f2`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001a1fc`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001a1fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StLoadIntfParametersAllocate(
        struct _GUID *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  char CustomWfdSettingsRegPathPresent; // al
  unsigned int v9; // ebx
  unsigned int RegKeyPath; // eax
  unsigned int v11; // ebx
  wil *v12; // rcx
  __int64 result; // rax
  int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  LSTATUS v18; // ebx
  wil *v19; // rcx
  wil *v20; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-4B8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-4B8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-4B8h]
  BYTE Data[4]; // [rsp+40h] [rbp-498h] BYREF
  HKEY v25; // [rsp+48h] [rbp-490h] BYREF
  HKEY *p_hKey; // [rsp+50h] [rbp-488h] BYREF
  HKEY v27; // [rsp+58h] [rbp-480h] BYREF
  char v28; // [rsp+60h] [rbp-478h]
  HKEY hKey; // [rsp+68h] [rbp-470h] BYREF
  struct _GUID *v30; // [rsp+70h] [rbp-468h]
  WCHAR SubKey[264]; // [rsp+80h] [rbp-458h] BYREF
  WCHAR v32[264]; // [rsp+290h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+0h]

  v30 = a1;
  memset_0(SubKey, 0, 0x208u);
  CustomWfdSettingsRegPathPresent = IsGetCustomWfdSettingsRegPathPresent();
  try
  {
    if ( (!CustomWfdSettingsRegPathPresent || (int)GetCustomRegRootPath(SubKey, 260, L"Software\\Microsoft\\Wlansvc") < 0)
      && (v9 = _o_wcscpy_s(SubKey, 260, L"Software\\Microsoft\\Wlansvc")) != 0 )
    {
      v12 = (wil *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v9);
      }
      result = v9;
    }
    else
    {
      if ( !lstrcmpW(a2, L"Scan Interval")
        || !lstrcmpW(a2, L"NloFastScanPeriod")
        || !lstrcmpW(a2, L"NloFastScanIterations")
        || !lstrcmpW(a2, L"NloSlowScanPeriod") )
      {
        *(_DWORD *)Data = 0;
        if ( (int)PolicyManager_GetPolicyInt(L"WiFi", L"WLANScanMode", Data) >= 0 && *(int *)Data > 0 )
        {
          memset_0(v32, 0, 0x208u);
          v14 = StringCchPrintfW(v32, 0x104u, L"%ws\\%ws\\%d", SubKey);
          if ( v14 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x83E,
              (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\storage\\src\\storage.cpp",
              (const char *)(unsigned int)v14,
              (int)L"Parameters\\CustomScanParameters");
          v25 = 0;
          p_hKey = &v25;
          v27 = 0;
          v28 = 1;
          v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v32, 0, 1u, &v27);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
          if ( !v18 && !StpQueryRegValueAllocate(v25, a2, a3, a4, a5) )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &v25,
              0);
            v15 = StringCchPrintfW(v32, 0x104u, L"%ws\\%ws", SubKey);
            if ( v15 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x852,
                (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\storage\\src\\storage.cpp",
                (const char *)(unsigned int)v15,
                (int)L"Parameters\\CustomScanParameters");
            p_hKey = &v25;
            v27 = 0;
            v28 = 1;
            v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v32, 0, 2u, &v27);
            if ( v16 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x856,
                (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\storage\\src\\storage.cpp",
                (const char *)v16,
                phkResulta);
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
            v17 = RegSetValueExW(v25, L"WlanScanMode", 0, 4u, Data, 4u);
            if ( v17 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x859,
                (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\storage\\src\\storage.cpp",
                (const char *)v17,
                phkResultb);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
            return 0;
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
        }
      }
      RegKeyPath = StpGetRegKeyPath(v30, 0, 0, 0, 0, SubKey, 0x104u);
      if ( RegKeyPath )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x896,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\storage\\src\\storage.cpp",
          (const char *)RegKeyPath,
          phkResult);
      hKey = 0;
      p_hKey = &hKey;
      v27 = 0;
      v28 = 1;
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &v27);
      if ( v28 )
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          p_hKey,
          v27);
      if ( v11 )
      {
        if ( details::TryToReadDefaultNloScanParameters(a2, SubKey, a3, a4, a5) )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return 0;
        }
      }
      else
      {
        v11 = StpQueryRegValueAllocate(hKey, a2, a3, a4, a5);
      }
      v12 = (wil *)hKey;
      if ( hKey )
        RegCloseKey(hKey);
      result = v11;
    }
  }
  catch ( ... )
  {
    if ( (int)wil::ResultFromCaughtException(v12) < 0 )
    {
      if ( (wil::ResultFromCaughtException(v19) & 0x1FFF0000) == 0x70000 )
        *(_DWORD *)Data = (unsigned __int16)wil::ResultFromCaughtException(v20);
      else
        *(_DWORD *)Data = wil::ResultFromCaughtException(v20);
    }
    else
    {
      *(_DWORD *)Data = 0;
    }
    return *(unsigned int *)Data;
  }
  return result;
}

```

## disassembly

```asm
0x18001a144  mov     [rsp+arg_10], rbx
0x18001a149  push    rsi
0x18001a14a  push    rdi
0x18001a14b  push    r12
0x18001a14d  push    r13
0x18001a14f  push    r15
0x18001a151  sub     rsp, 4B0h
0x18001a158  mov     rax, cs:__security_cookie
0x18001a15f  xor     rax, rsp
0x18001a162  mov     [rsp+4D8h+var_38], rax
0x18001a16a  mov     r12, r9
0x18001a16d  mov     r15d, r8d
0x18001a170  mov     rdi, rdx
0x18001a173  mov     [rsp+4D8h+var_468], rcx
0x18001a178  mov     r13, [rsp+4D8h+arg_20]
0x18001a180  xor     edx, edx; Val
0x18001a182  mov     r8d, 208h; Size
0x18001a188  lea     rcx, [rsp+4D8h+SubKey]; void *
0x18001a190  call    memset_0
0x18001a195  call    IsGetCustomWfdSettingsRegPathPresent
0x18001a19a  mov     esi, 104h
0x18001a19f  test    al, al
0x18001a1a1  jnz     loc_18001A4E0
0x18001a1a7  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Wlansvc"
0x18001a1ae  mov     rdx, rsi
0x18001a1b1  lea     rcx, [rsp+4D8h+SubKey]
0x18001a1b9  call    cs:__imp__o_wcscpy_s
0x18001a1bf  mov     ebx, eax
0x18001a1c1  test    eax, eax
0x18001a1c3  jnz     loc_18001A505
0x18001a1c9  lea     rdx, aScanInterval; "Scan Interval"
0x18001a1d0  mov     rcx, rdi; lpString1
0x18001a1d3  call    cs:__imp_lstrcmpW
0x18001a1d9  test    eax, eax
0x18001a1db  jnz     loc_18001A2F4
0x18001a1e1  mov     dword ptr [rsp+4D8h+Data], 0
0x18001a1e9  lea     r8, [rsp+4D8h+Data]
0x18001a1ee  lea     rdx, aWlanscanmode_0; "WLANScanMode"
0x18001a1f5  lea     rcx, aWifi_0; "WiFi"
0x18001a1fc  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001a202  test    eax, eax
0x18001a204  js      short loc_18001A212
0x18001a206  mov     ebx, dword ptr [rsp+4D8h+Data]
0x18001a20a  test    ebx, ebx
0x18001a20c  jg      loc_18001A355
0x18001a212  mov     [rsp+4D8h+var_4A8], rsi; unsigned __int64
0x18001a217  lea     rax, [rsp+4D8h+SubKey]
0x18001a21f  mov     qword ptr [rsp+4D8h+cbData], rax; unsigned __int16 *
0x18001a224  xor     esi, esi
0x18001a226  mov     dword ptr [rsp+4D8h+phkResult], esi; unsigned int
0x18001a22a  xor     r9d, r9d; int
0x18001a22d  xor     r8d, r8d; struct _GUID *
0x18001a230  xor     edx, edx; int
0x18001a232  mov     rcx, [rsp+4D8h+var_468]; struct _GUID *
0x18001a237  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@HPEAU1@HHPEAG_K@Z; StpGetRegKeyPath(_GUID const *,int,_GUID *,int,int,ushort *,unsigned __int64)
0x18001a23c  mov     rcx, [rsp+4D8h]; this
0x18001a244  test    eax, eax
0x18001a246  jnz     loc_18001A341
0x18001a24c  mov     [rsp+4D8h+hKey], rsi
0x18001a251  lea     rax, [rsp+4D8h+hKey]
0x18001a256  mov     [rsp+4D8h+var_488], rax
0x18001a25b  mov     [rsp+4D8h+var_480], rsi
0x18001a260  mov     [rsp+4D8h+var_478], 1
0x18001a265  lea     rax, [rsp+4D8h+var_480]
0x18001a26a  mov     [rsp+4D8h+phkResult], rax; phkResult
0x18001a26f  lea     r9d, [rsi+1]; samDesired
0x18001a273  xor     r8d, r8d; ulOptions
0x18001a276  lea     rdx, [rsp+4D8h+SubKey]; lpSubKey
0x18001a27e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a285  call    cs:__imp_RegOpenKeyExW
0x18001a28b  mov     ebx, eax
0x18001a28d  cmp     [rsp+4D8h+var_478], sil
0x18001a292  jnz     loc_18001A5CB
0x18001a298  mov     [rsp+4D8h+phkResult], r13; unsigned __int8 **
0x18001a29d  mov     r9, r12; unsigned int *
0x18001a2a0  mov     r8d, r15d; unsigned int
0x18001a2a3  test    ebx, ebx
0x18001a2a5  jnz     loc_18001A5DF
0x18001a2ab  mov     rdx, rdi; lpValueName
0x18001a2ae  mov     rcx, [rsp+4D8h+hKey]; hKey
0x18001a2b3  call    ?StpQueryRegValueAllocate@@YAKPEAUHKEY__@@PEBGKPEAKPEAPEAE@Z; StpQueryRegValueAllocate(HKEY__ *,ushort const *,ulong,ulong *,uchar * *)
0x18001a2b8  mov     ebx, eax
0x18001a2ba  mov     rcx, [rsp+4D8h+hKey]; hKey
0x18001a2bf  test    rcx, rcx
0x18001a2c2  jz      short loc_18001A2CA
0x18001a2c4  call    cs:__imp_RegCloseKey
0x18001a2ca  mov     eax, ebx
0x18001a2cc  mov     rcx, [rsp+4D8h+var_38]
0x18001a2d4  xor     rcx, rsp; StackCookie
0x18001a2d7  call    __security_check_cookie
0x18001a2dc  mov     rbx, [rsp+4D8h+arg_10]
0x18001a2e4  add     rsp, 4B0h
0x18001a2eb  pop     r15
0x18001a2ed  pop     r13
0x18001a2ef  pop     r12
0x18001a2f1  pop     rdi
0x18001a2f2  pop     rsi
0x18001a2f3  retn
0x18001a2f4  lea     rdx, aNlofastscanper; "NloFastScanPeriod"
0x18001a2fb  mov     rcx, rdi; lpString1
0x18001a2fe  call    cs:__imp_lstrcmpW
0x18001a304  test    eax, eax
0x18001a306  jz      loc_18001A1E1
0x18001a30c  lea     rdx, aNlofastscanite; "NloFastScanIterations"
0x18001a313  mov     rcx, rdi; lpString1
0x18001a316  call    cs:__imp_lstrcmpW
0x18001a31c  test    eax, eax
0x18001a31e  jz      loc_18001A1E1
0x18001a324  lea     rdx, aNloslowscanper; "NloSlowScanPeriod"
0x18001a32b  mov     rcx, rdi; lpString1
0x18001a32e  call    cs:__imp_lstrcmpW
0x18001a334  test    eax, eax
0x18001a336  jnz     loc_18001A212
0x18001a33c  jmp     loc_18001A1E1
0x18001a341  mov     r9d, eax; char *
0x18001a344  lea     r8, aOnecoreuapNetW_68; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18001a34b  mov     edx, 896h; void *
0x18001a350  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001a355  xor     edx, edx; Val
0x18001a357  mov     r8d, 208h; Size
0x18001a35d  lea     rcx, [rsp+4D8h+var_248]; void *
0x18001a365  call    memset_0
0x18001a36a  mov     [rsp+4D8h+cbData], ebx
0x18001a36e  lea     rax, aParametersCust; "Parameters\\CustomScanParameters"
0x18001a375  mov     [rsp+4D8h+phkResult], rax; int
0x18001a37a  lea     r9, [rsp+4D8h+SubKey]
0x18001a382  lea     r8, aWsWsD; "%ws\\%ws\\%d"
0x18001a389  mov     rdx, rsi; unsigned __int64
0x18001a38c  lea     rcx, [rsp+4D8h+var_248]; unsigned __int16 *
0x18001a394  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a399  mov     rcx, [rsp+4D8h]; this
0x18001a3a1  test    eax, eax
0x18001a3a3  jns     loc_18001A543
0x18001a3a9  mov     r9d, eax; char *
0x18001a3ac  lea     r8, aOnecoreuapNetW_68; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18001a3b3  mov     edx, 83Eh; void *
0x18001a3b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a3be  xor     edx, edx
0x18001a3c0  lea     rcx, [rsp+4D8h+var_490]
0x18001a3c5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001a3ca  lea     rax, aParametersCust; "Parameters\\CustomScanParameters"
0x18001a3d1  mov     [rsp+4D8h+phkResult], rax; int
0x18001a3d6  lea     r9, [rsp+4D8h+SubKey]
0x18001a3de  lea     r8, aWsWs_0; "%ws\\%ws"
0x18001a3e5  mov     rdx, rsi; unsigned __int64
0x18001a3e8  lea     rcx, [rsp+4D8h+var_248]; unsigned __int16 *
0x18001a3f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a3f5  mov     rcx, [rsp+4D8h]; this
0x18001a3fd  test    eax, eax
0x18001a3ff  js      loc_18001A4A5
0x18001a405  lea     rax, [rsp+4D8h+var_490]
0x18001a40a  mov     [rsp+4D8h+var_488], rax
0x18001a40f  mov     [rsp+4D8h+var_480], 0
0x18001a418  mov     [rsp+4D8h+var_478], 1
0x18001a41d  lea     rax, [rsp+4D8h+var_480]
0x18001a422  mov     [rsp+4D8h+phkResult], rax; unsigned int
0x18001a427  mov     r9d, 2; samDesired
0x18001a42d  xor     r8d, r8d; ulOptions
0x18001a430  lea     rdx, [rsp+4D8h+var_248]; lpSubKey
0x18001a438  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a43f  call    cs:__imp_RegOpenKeyExW
0x18001a445  mov     rcx, [rsp+4D8h]; this
0x18001a44d  test    eax, eax
0x18001a44f  jnz     short loc_18001A4BA
0x18001a451  lea     rcx, [rsp+4D8h+var_488]
0x18001a456  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001a45b  mov     r9d, 4; dwType
0x18001a461  mov     [rsp+4D8h+cbData], r9d; cbData
0x18001a466  lea     rax, [rsp+4D8h+Data]
0x18001a46b  mov     [rsp+4D8h+phkResult], rax; unsigned int
0x18001a470  xor     r8d, r8d; Reserved
0x18001a473  lea     rdx, aWlanscanmode; "WlanScanMode"
0x18001a47a  mov     rcx, [rsp+4D8h+var_490]; hKey
0x18001a47f  call    cs:__imp_RegSetValueExW
0x18001a485  mov     rcx, [rsp+4D8h]; this
0x18001a48d  test    eax, eax
0x18001a48f  jz      short loc_18001A4CF
0x18001a491  mov     r9d, eax; char *
0x18001a494  lea     r8, aOnecoreuapNetW_68; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18001a49b  mov     edx, 859h; void *
0x18001a4a0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001a4a5  mov     r9d, eax; char *
0x18001a4a8  lea     r8, aOnecoreuapNetW_68; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18001a4af  mov     edx, 852h; void *
0x18001a4b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a4ba  mov     r9d, eax; char *
0x18001a4bd  lea     r8, aOnecoreuapNetW_68; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18001a4c4  mov     edx, 856h; void *
0x18001a4c9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001a4cf  lea     rcx, [rsp+4D8h+var_490]
0x18001a4d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001a4d9  xor     eax, eax
0x18001a4db  jmp     loc_18001A2CC
0x18001a4e0  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Wlansvc"
0x18001a4e7  mov     rdx, rsi
0x18001a4ea  lea     rcx, [rsp+4D8h+SubKey]
0x18001a4f2  call    cs:__imp_GetCustomRegRootPath
0x18001a4f8  test    eax, eax
0x18001a4fa  jns     loc_18001A1C9
0x18001a500  jmp     loc_18001A1A7
0x18001a505  lea     rax, WPP_GLOBAL_Control
0x18001a50c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a513  cmp     rcx, rax
0x18001a516  jz      short loc_18001A53C
0x18001a518  cmp     byte ptr [rcx+69h], 1
0x18001a51c  jb      short loc_18001A53C
0x18001a51e  test    byte ptr [rcx+6Ch], 1
0x18001a522  jz      short loc_18001A53C
0x18001a524  mov     edx, 0Ah
0x18001a529  mov     r9d, ebx
0x18001a52c  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x18001a533  mov     rcx, [rcx+60h]
0x18001a537  call    WPP_SF_d
0x18001a53c  mov     eax, ebx
0x18001a53e  jmp     loc_18001A2CC
0x18001a543  mov     [rsp+4D8h+var_490], 0
0x18001a54c  lea     rax, [rsp+4D8h+var_490]
0x18001a551  mov     [rsp+4D8h+var_488], rax
0x18001a556  mov     [rsp+4D8h+var_480], 0
0x18001a55f  mov     [rsp+4D8h+var_478], 1
0x18001a564  lea     rax, [rsp+4D8h+var_480]
0x18001a569  mov     [rsp+4D8h+phkResult], rax; phkResult
0x18001a56e  mov     r9d, 1; samDesired
0x18001a574  xor     r8d, r8d; ulOptions
0x18001a577  lea     rdx, [rsp+4D8h+var_248]; lpSubKey
0x18001a57f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a586  call    cs:__imp_RegOpenKeyExW
0x18001a58c  mov     ebx, eax
0x18001a58e  lea     rcx, [rsp+4D8h+var_488]
0x18001a593  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001a598  test    ebx, ebx
0x18001a59a  jnz     short loc_18001A5BC
0x18001a59c  mov     [rsp+4D8h+phkResult], r13; unsigned __int8 **
0x18001a5a1  mov     r9, r12; unsigned int *
0x18001a5a4  mov     r8d, r15d; unsigned int
0x18001a5a7  mov     rdx, rdi; lpValueName
0x18001a5aa  mov     rcx, [rsp+4D8h+var_490]; hKey
0x18001a5af  call    ?StpQueryRegValueAllocate@@YAKPEAUHKEY__@@PEBGKPEAKPEAPEAE@Z; StpQueryRegValueAllocate(HKEY__ *,ushort const *,ulong,ulong *,uchar * *)
0x18001a5b4  test    eax, eax
0x18001a5b6  jz      loc_18001A3BE
0x18001a5bc  lea     rcx, [rsp+4D8h+var_490]
0x18001a5c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001a5c6  jmp     loc_18001A212
0x18001a5cb  mov     rdx, [rsp+4D8h+var_480]
0x18001a5d0  mov     rcx, [rsp+4D8h+var_488]
0x18001a5d5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001a5da  jmp     loc_18001A298
0x18001a5df  lea     rdx, [rsp+4D8h+SubKey]; unsigned __int16 *
0x18001a5e7  mov     rcx, rdi; lpValueName
0x18001a5ea  call    ?TryToReadDefaultNloScanParameters@details@@YA_NPEBG0KPEAKPEAPEAE@Z; details::TryToReadDefaultNloScanParameters(ushort const *,ushort const *,ulong,ulong *,uchar * *)
0x18001a5ef  test    al, al
0x18001a5f1  jz      loc_18001A2BA
0x18001a5f7  lea     rcx, [rsp+4D8h+hKey]
0x18001a5fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001a601  xor     eax, eax
0x18001a603  jmp     loc_18001A2CC
0x18001a608  mov     eax, dword ptr [rsp+4D8h+Data]
0x18001a60c  jmp     loc_18001A2CC
```
