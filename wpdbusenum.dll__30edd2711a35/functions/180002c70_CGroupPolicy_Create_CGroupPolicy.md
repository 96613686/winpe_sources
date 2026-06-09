# CGroupPolicy::Create(CGroupPolicy * *)

- ea: `0x180002c70`
- end: `0x180002f8b`
- name: `?Create@CGroupPolicy@@SAJPEAPEAV1@@Z`
- size: `795`
- prototype: `__int64 __fastcall(struct CGroupPolicy **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x1800018c0`

## callees

- `0x180001210`
- `0x180001730`
- `0x180002c70`
- `0x180002fa0`
- `0x180005bb0`
- `0x18000704c`
- `0x180007160`
- `0x180007f28`
- `0x180009394`
- `0x1800097d0`
- `0x18000a192`
- `0x18000e204`
- `0x18000ea84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e9f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180002e90`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180002e90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e3d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180002e32`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180002e32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002e1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180002d21`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180002d21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f5e`

## string_xrefs

- `0x180002d78`: `RegCacheState`
- `0x180002dc0`: `RegCacheUpdated`
- `0x180002e55`: `RegCacheUpdated`

## pseudocode

```c
__int64 __fastcall CGroupPolicy::Create(struct CGroupPolicy **a1)
{
  BYTE *v1; // rdi
  BYTE *v2; // rax
  BYTE *v3; // rsi
  signed int v4; // eax
  unsigned int v5; // edx
  signed int v6; // ebx
  CPnPNotification *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  DWORD v14; // [rsp+40h] [rbp-368h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-360h] BYREF
  BYTE *v16[2]; // [rsp+50h] [rbp-358h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-348h] BYREF
  char v18; // [rsp+178h] [rbp-230h]
  unsigned __int16 v19[264]; // [rsp+180h] [rbp-228h] BYREF

  memset_0(&VersionInformation, 0, 0x11Cu);
  memset_0(v19, 0, 0x208u);
  hKey = 0;
  v1 = 0;
  v14 = 0;
  v16[0] = 0;
  g_GroupPolicy = 0;
  v2 = (BYTE *)operator new(0x38u);
  v16[1] = v2;
  v3 = v2;
  if ( !v2 )
  {
    v6 = -2147024882;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids, "pGroupPolicy");
    goto LABEL_29;
  }
  *(_DWORD *)v2 = 0;
  *((_QWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 3) = 0;
  *((_DWORD *)v2 + 8) = 1;
  *((_QWORD *)v2 + 5) = 0;
  *((_DWORD *)v2 + 12) = -1;
  GPEnableLogToFile();
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( (v18 & 0x10) == 0 )
      *((_DWORD *)v3 + 8) = 0;
    v6 = StringCchPrintfW(v19, 0x104u, L"%ws\\%ws", L"SYSTEM\\CurrentControlSet\\Control\\Storage", L"RegCacheState");
    if ( v6 >= 0 )
    {
      v14 = 4;
      WPDLibGetRegistryValue(0, v9, v19, L"RegCacheUpdated", 4, v16, &v14);
      v1 = v16[0];
      if ( !v16[0] || !*(_DWORD *)v16[0] )
      {
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Storage", 0, 0x2001Fu, &hKey) )
        {
          RegDeleteTreeW(hKey, L"EnabledDenyGP");
          RegCloseKey(hKey);
        }
        v14 = 1;
        WPDLibSetRegistryValue(0, v10, v19, L"RegCacheUpdated", 4, &v14, 4);
      }
    }
    CGroupPolicy::RetrieveEnabledDenyGP((CGroupPolicy *)v3);
    ThreadpoolWork = CreateThreadpoolWork(CGroupPolicy::ProcessGPSettingsWork, v3, 0);
    *((_QWORD *)v3 + 5) = ThreadpoolWork;
    if ( !ThreadpoolWork )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v8 = 12;
        goto LABEL_22;
      }
    }
  }
  else
  {
    v4 = GetLastError();
    v6 = v4;
    if ( v4 > 0 )
      v6 = (unsigned __int16)v4 | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 11;
LABEL_22:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids, (unsigned int)v6);
    }
  }
  if ( v6 < 0 )
  {
    CGroupPolicy::`scalar deleting destructor'((CGroupPolicy *)v3, v5);
LABEL_29:
    GPDebugPrintX(8u, "GP object initialized failed.  hr = 0x%08x\n", v6);
    goto LABEL_30;
  }
  g_GroupPolicy = (CGroupPolicy *)v3;
  GPDebugPrintX(8u, "GP object initialized successfully\n");
LABEL_30:
  LocalFree(v1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002c70  mov     [rsp+arg_0], rbx
0x180002c75  mov     [rsp+arg_8], rsi
0x180002c7a  push    rdi
0x180002c7b  sub     rsp, 3A0h
0x180002c82  mov     rax, cs:__security_cookie
0x180002c89  xor     rax, rsp
0x180002c8c  mov     [rsp+3A8h+var_18], rax
0x180002c94  xor     edx, edx; Val
0x180002c96  lea     rcx, [rsp+3A8h+VersionInformation]; void *
0x180002c9b  mov     r8d, 11Ch; Size
0x180002ca1  call    memset_0
0x180002ca6  xor     edx, edx; Val
0x180002ca8  lea     rcx, [rsp+3A8h+var_228]; void *
0x180002cb0  mov     r8d, 208h; Size
0x180002cb6  call    memset_0
0x180002cbb  xor     ebx, ebx
0x180002cbd  mov     ecx, 38h ; '8'; Size
0x180002cc2  mov     [rsp+3A8h+hKey], rbx
0x180002cc7  mov     edi, ebx
0x180002cc9  mov     [rsp+3A8h+var_368], ebx
0x180002ccd  mov     [rsp+3A8h+var_358], rbx
0x180002cd2  mov     cs:?g_GroupPolicy@@3PEAVCGroupPolicy@@EA, rbx; CGroupPolicy * g_GroupPolicy
0x180002cd9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002cde  mov     [rsp+3A8h+var_350], rax
0x180002ce3  mov     rsi, rax
0x180002ce6  test    rax, rax
0x180002ce9  jz      loc_180002F0D
0x180002cef  mov     [rax], ebx
0x180002cf1  mov     [rax+8], rbx
0x180002cf5  mov     [rax+10h], rbx
0x180002cf9  mov     [rax+18h], rbx
0x180002cfd  mov     dword ptr [rax+20h], 1
0x180002d04  mov     [rax+28h], rbx
0x180002d08  mov     dword ptr [rax+30h], 0FFFFFFFFh
0x180002d0f  call    ?GPEnableLogToFile@@YAKXZ; GPEnableLogToFile(void)
0x180002d14  lea     rcx, [rsp+3A8h+VersionInformation]; lpVersionInformation
0x180002d19  mov     [rsp+3A8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180002d21  call    cs:__imp_GetVersionExW
0x180002d27  test    eax, eax
0x180002d29  jnz     short loc_180002D6B
0x180002d2b  call    cs:__imp_GetLastError
0x180002d31  mov     ebx, eax
0x180002d33  test    eax, eax
0x180002d35  jle     short loc_180002D40
0x180002d37  movzx   ebx, ax
0x180002d3a  or      ebx, 80070000h
0x180002d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d47  lea     rax, WPP_GLOBAL_Control
0x180002d4e  cmp     rcx, rax
0x180002d51  jz      loc_180002EE5
0x180002d57  test    byte ptr [rcx+1Ch], 2
0x180002d5b  jz      loc_180002EE5
0x180002d61  mov     edx, 0Bh
0x180002d66  jmp     loc_180002ED2
0x180002d6b  test    [rsp+3A8h+var_230], 10h
0x180002d73  jnz     short loc_180002D78
0x180002d75  mov     [rsi+20h], ebx
0x180002d78  lea     rax, aRegcachestate; "RegCacheState"
0x180002d7f  mov     edx, 104h; unsigned __int64
0x180002d84  lea     r9, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x180002d8b  mov     [rsp+3A8h+phkResult], rax
0x180002d90  lea     r8, aWsWs; "%ws\\%ws"
0x180002d97  lea     rcx, [rsp+3A8h+var_228]; unsigned __int16 *
0x180002d9f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002da4  mov     ebx, eax
0x180002da6  test    eax, eax
0x180002da8  js      loc_180002E7B
0x180002dae  lea     rax, [rsp+3A8h+var_368]
0x180002db3  mov     [rsp+3A8h+var_368], 4
0x180002dbb  mov     [rsp+3A8h+var_378], rax
0x180002dc0  lea     r9, aRegcacheupdate; "RegCacheUpdated"
0x180002dc7  lea     rax, [rsp+3A8h+var_358]
0x180002dcc  xor     ecx, ecx
0x180002dce  mov     [rsp+3A8h+var_380], rax
0x180002dd3  lea     r8, [rsp+3A8h+var_228]
0x180002ddb  mov     dword ptr [rsp+3A8h+phkResult], 4
0x180002de3  call    WPDLibGetRegistryValue
0x180002de8  mov     rdi, [rsp+3A8h+var_358]
0x180002ded  test    rdi, rdi
0x180002df0  jz      short loc_180002DFB
0x180002df2  cmp     dword ptr [rdi], 0
0x180002df5  jnz     loc_180002E7B
0x180002dfb  lea     rax, [rsp+3A8h+hKey]
0x180002e00  mov     r9d, 2001Fh; samDesired
0x180002e06  xor     r8d, r8d; ulOptions
0x180002e09  mov     [rsp+3A8h+phkResult], rax; phkResult
0x180002e0e  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x180002e15  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002e1c  call    cs:__imp_RegOpenKeyExW
0x180002e22  test    eax, eax
0x180002e24  jnz     short loc_180002E43
0x180002e26  mov     rcx, [rsp+3A8h+hKey]; hKey
0x180002e2b  lea     rdx, aEnableddenygp; "EnabledDenyGP"
0x180002e32  call    cs:__imp_RegDeleteTreeW
0x180002e38  mov     rcx, [rsp+3A8h+hKey]; hKey
0x180002e3d  call    cs:__imp_RegCloseKey
0x180002e43  lea     rax, [rsp+3A8h+var_368]
0x180002e48  mov     dword ptr [rsp+3A8h+var_378], 4
0x180002e50  mov     [rsp+3A8h+var_380], rax
0x180002e55  lea     r9, aRegcacheupdate; "RegCacheUpdated"
0x180002e5c  lea     r8, [rsp+3A8h+var_228]
0x180002e64  mov     dword ptr [rsp+3A8h+phkResult], 4
0x180002e6c  xor     ecx, ecx
0x180002e6e  mov     [rsp+3A8h+var_368], 1
0x180002e76  call    WPDLibSetRegistryValue
0x180002e7b  mov     rcx, rsi; this
0x180002e7e  call    ?RetrieveEnabledDenyGP@CGroupPolicy@@IEAAXXZ; CGroupPolicy::RetrieveEnabledDenyGP(void)
0x180002e83  xor     r8d, r8d; pcbe
0x180002e86  lea     rcx, ?ProcessGPSettingsWork@CGroupPolicy@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180002e8d  mov     rdx, rsi; pv
0x180002e90  call    cs:__imp_CreateThreadpoolWork
0x180002e96  mov     [rsi+28h], rax
0x180002e9a  test    rax, rax
0x180002e9d  jnz     short loc_180002EE5
0x180002e9f  call    cs:__imp_GetLastError
0x180002ea5  mov     ebx, eax
0x180002ea7  test    eax, eax
0x180002ea9  jle     short loc_180002EB4
0x180002eab  movzx   ebx, ax
0x180002eae  or      ebx, 80070000h
0x180002eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ebb  lea     rax, WPP_GLOBAL_Control
0x180002ec2  cmp     rcx, rax
0x180002ec5  jz      short loc_180002EE5
0x180002ec7  test    byte ptr [rcx+1Ch], 2
0x180002ecb  jz      short loc_180002EE5
0x180002ecd  mov     edx, 0Ch
0x180002ed2  mov     rcx, [rcx+10h]
0x180002ed6  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180002edd  mov     r9d, ebx
0x180002ee0  call    WPP_SF_d
0x180002ee5  test    ebx, ebx
0x180002ee7  js      short loc_180002F03
0x180002ee9  lea     rdx, aGpObjectInitia_0; "GP object initialized successfully\n"
0x180002ef0  mov     cs:?g_GroupPolicy@@3PEAVCGroupPolicy@@EA, rsi; CGroupPolicy * g_GroupPolicy
0x180002ef7  mov     ecx, 8; unsigned int
0x180002efc  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180002f01  jmp     short loc_180002F5B
0x180002f03  mov     rcx, rsi; this
0x180002f06  call    ??_GCGroupPolicy@@QEAAPEAXI@Z; CGroupPolicy::`scalar deleting destructor'(uint)
0x180002f0b  jmp     short loc_180002F47
0x180002f0d  mov     ebx, 8007000Eh
0x180002f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f19  lea     rax, WPP_GLOBAL_Control
0x180002f20  cmp     rcx, rax
0x180002f23  jz      short loc_180002F47
0x180002f25  test    byte ptr [rcx+1Ch], 2
0x180002f29  jz      short loc_180002F47
0x180002f2b  mov     rcx, [rcx+10h]
0x180002f2f  lea     r9, aPgrouppolicy; "pGroupPolicy"
0x180002f36  mov     edx, 0Ah
0x180002f3b  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180002f42  call    WPP_SF_s
0x180002f47  mov     r8d, ebx
0x180002f4a  lea     rdx, aGpObjectInitia; "GP object initialized failed.  hr = 0x%"...
0x180002f51  mov     ecx, 8; unsigned int
0x180002f56  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180002f5b  mov     rcx, rdi; hMem
0x180002f5e  call    cs:__imp_LocalFree
0x180002f64  mov     eax, ebx
0x180002f66  mov     rcx, [rsp+3A8h+var_18]
0x180002f6e  xor     rcx, rsp; StackCookie
0x180002f71  call    __security_check_cookie
0x180002f76  lea     r11, [rsp+3A8h+var_8]
0x180002f7e  mov     rbx, [r11+10h]
0x180002f82  mov     rsi, [r11+18h]
0x180002f86  mov     rsp, r11
0x180002f89  pop     rdi
0x180002f8a  retn
```
