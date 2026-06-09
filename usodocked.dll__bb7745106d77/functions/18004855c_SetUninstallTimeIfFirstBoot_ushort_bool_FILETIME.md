# SetUninstallTimeIfFirstBoot(ushort *,bool &,_FILETIME &)

- ea: `0x18004855c`
- end: `0x180048858`
- name: `?SetUninstallTimeIfFirstBoot@@YAJPEAGAEA_NAEAU_FILETIME@@@Z`
- size: `764`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, bool *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800476dc`
- `0x1800478e8`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x18004855c`
- `0x180048860`
- `0x180048a7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048694`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800485cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800485cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004864b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800487e8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004864b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800487e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048608`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004882d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048608`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004882d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004867d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004867d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004868a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004868a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180048746`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180048792`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180048746`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180048792`

## string_xrefs

- `0x1800485ae`: `SOFTWARE\MICROSOFT\WINDOWS\CURRENTVERSION\WINDOWSUPDATE\WINREUNINSTALLLIST`
- `0x180048731`: `UninstallTime`
- `0x1800487bf`: `UninstallTime`

## pseudocode

```c
__int64 __fastcall SetUninstallTimeIfFirstBoot(LPCWSTR lpSubKey, bool *a2, struct _FILETIME *a3)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  __int64 v8; // rdx
  LSTATUS ValueW; // eax
  signed int LastError; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  int phkResult; // [rsp+20h] [rbp-69h]
  LPDWORD pcbData; // [rsp+30h] [rbp-59h]
  int wMonth; // [rsp+38h] [rbp-51h]
  int wDay; // [rsp+40h] [rbp-49h]
  int wHour; // [rsp+48h] [rbp-41h]
  int wMinute; // [rsp+50h] [rbp-39h]
  int wSecond; // [rsp+58h] [rbp-31h]
  HKEY hKey; // [rsp+60h] [rbp-29h] BYREF
  int pvData; // [rsp+68h] [rbp-21h] BYREF
  DWORD v24; // [rsp+6Ch] [rbp-1Dh] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int16 Data[24]; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *a2 = 0;
  hKey = 0;
  v24 = 0;
  pvData = 0;
  SystemTime = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\MICROSOFT\\WINDOWS\\CURRENTVERSION\\WINDOWSUPDATE\\WINREUNINSTALLLIST",
         0,
         0xF003Fu,
         &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = 299;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\enduser\\srtlib\\srt.cpp",
      (const char *)(unsigned int)v7,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v7;
  }
  v24 = 4;
  ValueW = RegGetValueW(hKey, lpSubKey, L"IsFirstBoot", 0x10u, 0, &pvData, &v24);
  v7 = ValueW;
  if ( ValueW > 0 )
    v7 = (unsigned __int16)ValueW | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = 308;
    goto LABEL_5;
  }
  if ( pvData )
    *a2 = 1;
  if ( *a2 )
  {
    GetSystemTimeAsFileTime(a3);
    if ( !FileTimeToSystemTime(a3, &SystemTime) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 < 0 )
      {
        v8 = 321;
        goto LABEL_5;
      }
    }
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wDay = SystemTime.wDay;
    wMonth = SystemTime.wMonth;
    LODWORD(pcbData) = SystemTime.wYear;
    v7 = StringCchPrintfExW(
           Data,
           0x15u,
           0,
           0,
           0x100u,
           L"%04u-%02u-%02uT%02u:%02u:%02uZ",
           pcbData,
           wMonth,
           wDay,
           wHour,
           wMinute,
           wSecond);
    if ( v7 < 0 )
    {
      v8 = 331;
      goto LABEL_5;
    }
    v12 = RegSetKeyValueW(hKey, lpSubKey, L"UninstallTime", 1u, Data, 0x2Au);
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = 338;
      goto LABEL_5;
    }
    pvData = 0;
    v13 = RegSetKeyValueW(hKey, lpSubKey, L"IsFirstBoot", 4u, &pvData, 4u);
    v7 = v13;
    if ( v13 > 0 )
      v7 = (unsigned __int16)v13 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = 346;
      goto LABEL_5;
    }
  }
  else
  {
    v24 = 42;
    v14 = RegGetValueW(hKey, lpSubKey, L"UninstallTime", 2u, 0, Data, &v24);
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = 358;
      goto LABEL_5;
    }
    v7 = StringToFileTime(Data, a3);
    if ( v7 < 0 )
    {
      v8 = 360;
      goto LABEL_5;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18004855c  mov     [rsp-8+arg_18], rbx
0x180048561  push    rbp
0x180048562  push    rsi
0x180048563  push    rdi
0x180048564  push    r12
0x180048566  push    r14
0x180048568  lea     rbp, [rsp-37h]
0x18004856d  sub     rsp, 0C0h
0x180048574  mov     rax, cs:__security_cookie
0x18004857b  xor     rax, rsp
0x18004857e  mov     [rbp+57h+var_30], rax
0x180048582  mov     rsi, r8
0x180048585  mov     byte ptr [rdx], 0
0x180048588  mov     rdi, rdx
0x18004858b  mov     [rbp+57h+hKey], 0
0x180048593  mov     r14, rcx
0x180048596  mov     [rbp+57h+var_74], 0
0x18004859d  xorps   xmm0, xmm0
0x1800485a0  mov     [rbp+57h+var_78], 0
0x1800485a7  lea     rax, [rbp+57h+hKey]
0x1800485ab  xor     r8d, r8d; ulOptions
0x1800485ae  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\MICROSOFT\\WINDOWS\\CURRENTVE"...
0x1800485b5  mov     [rsp+0E0h+phkResult], rax; int
0x1800485ba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800485c1  mov     r9d, 0F003Fh; samDesired
0x1800485c7  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800485cb  call    cs:__imp_RegOpenKeyExW
0x1800485d1  mov     ebx, eax
0x1800485d3  mov     r12d, 80070000h
0x1800485d9  test    eax, eax
0x1800485db  jle     short loc_1800485E3
0x1800485dd  movzx   ebx, ax
0x1800485e0  or      ebx, r12d
0x1800485e3  test    ebx, ebx
0x1800485e5  jns     short loc_180048615
0x1800485e7  mov     edx, 12Bh; void *
0x1800485ec  mov     rcx, [rbp+5Fh]; this
0x1800485f0  lea     r8, aOnecoreEnduser_29; "onecore\\enduser\\srtlib\\srt.cpp"
0x1800485f7  mov     r9d, ebx; char *
0x1800485fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800485ff  mov     rcx, [rbp+57h+hKey]; hKey
0x180048603  test    rcx, rcx
0x180048606  jz      short loc_18004860E
0x180048608  call    cs:__imp_RegCloseKey
0x18004860e  mov     eax, ebx
0x180048610  jmp     loc_180048835
0x180048615  mov     rcx, [rbp+57h+hKey]; hkey
0x180048619  lea     rax, [rbp+57h+var_74]
0x18004861d  mov     [rsp+0E0h+pcbData], rax; pcbData
0x180048622  lea     r8, aIsfirstboot; "IsFirstBoot"
0x180048629  lea     rax, [rbp+57h+var_78]
0x18004862d  mov     [rbp+57h+var_74], 4
0x180048634  mov     [rsp+0E0h+pvData], rax; pvData
0x180048639  mov     r9d, 10h; dwFlags
0x18004863f  mov     rdx, r14; lpSubKey
0x180048642  mov     [rsp+0E0h+phkResult], 0; pdwType
0x18004864b  call    cs:__imp_RegGetValueW
0x180048651  mov     ebx, eax
0x180048653  test    eax, eax
0x180048655  jle     short loc_18004865D
0x180048657  movzx   ebx, ax
0x18004865a  or      ebx, r12d
0x18004865d  test    ebx, ebx
0x18004865f  jns     short loc_180048668
0x180048661  mov     edx, 134h
0x180048666  jmp     short loc_1800485EC
0x180048668  cmp     [rbp+57h+var_78], 0
0x18004866c  jz      short loc_180048671
0x18004866e  mov     byte ptr [rdi], 1
0x180048671  cmp     byte ptr [rdi], 0
0x180048674  jz      loc_1800487B2
0x18004867a  mov     rcx, rsi; lpSystemTimeAsFileTime
0x18004867d  call    cs:__imp_GetSystemTimeAsFileTime
0x180048683  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180048687  mov     rcx, rsi; lpFileTime
0x18004868a  call    cs:__imp_FileTimeToSystemTime
0x180048690  test    eax, eax
0x180048692  jnz     short loc_1800486B4
0x180048694  call    cs:__imp_GetLastError
0x18004869a  mov     ebx, eax
0x18004869c  test    eax, eax
0x18004869e  jle     short loc_1800486A6
0x1800486a0  movzx   ebx, ax
0x1800486a3  or      ebx, r12d
0x1800486a6  test    ebx, ebx
0x1800486a8  jns     short loc_1800486B4
0x1800486aa  mov     edx, 141h
0x1800486af  jmp     loc_1800485EC
0x1800486b4  movzx   eax, [rbp+57h+SystemTime.wSecond]
0x1800486b8  movzx   ecx, [rbp+57h+SystemTime.wMinute]
0x1800486bc  movzx   edx, [rbp+57h+SystemTime.wHour]
0x1800486c0  movzx   r8d, [rbp+57h+SystemTime.wDay]
0x1800486c5  movzx   r9d, [rbp+57h+SystemTime.wMonth]
0x1800486ca  movzx   r10d, [rbp+57h+SystemTime.wYear]
0x1800486cf  mov     [rsp+0E0h+var_88], eax
0x1800486d3  lea     rax, a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02uZ"
0x1800486da  mov     [rsp+0E0h+var_90], ecx
0x1800486de  lea     rcx, [rbp+57h+Data]; unsigned __int16 *
0x1800486e2  mov     [rsp+0E0h+var_98], edx
0x1800486e6  mov     [rsp+0E0h+var_A0], r8d
0x1800486eb  xor     r8d, r8d; unsigned __int16 **
0x1800486ee  mov     [rsp+0E0h+var_A8], r9d
0x1800486f3  xor     r9d, r9d; unsigned __int64 *
0x1800486f6  mov     dword ptr [rsp+0E0h+pcbData], r10d
0x1800486fb  mov     [rsp+0E0h+pvData], rax; unsigned __int16 *
0x180048700  mov     dword ptr [rsp+0E0h+phkResult], 100h; unsigned int
0x180048708  lea     edx, [r9+15h]; unsigned __int64
0x18004870c  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180048711  mov     ebx, eax
0x180048713  test    eax, eax
0x180048715  jns     short loc_180048721
0x180048717  mov     edx, 14Bh
0x18004871c  jmp     loc_1800485EC
0x180048721  mov     rcx, [rbp+57h+hKey]; hKey
0x180048725  lea     rax, [rbp+57h+Data]
0x180048729  mov     dword ptr [rsp+0E0h+pvData], 2Ah ; '*'; cbData
0x180048731  lea     r8, aUninstalltime; "UninstallTime"
0x180048738  mov     r9d, 1; dwType
0x18004873e  mov     [rsp+0E0h+phkResult], rax; lpData
0x180048743  mov     rdx, r14; lpSubKey
0x180048746  call    cs:__imp_RegSetKeyValueW
0x18004874c  mov     ebx, eax
0x18004874e  test    eax, eax
0x180048750  jle     short loc_180048758
0x180048752  movzx   ebx, ax
0x180048755  or      ebx, r12d
0x180048758  test    ebx, ebx
0x18004875a  jns     short loc_180048766
0x18004875c  mov     edx, 152h
0x180048761  jmp     loc_1800485EC
0x180048766  mov     rcx, [rbp+57h+hKey]; hKey
0x18004876a  lea     rax, [rbp+57h+var_78]
0x18004876e  mov     dword ptr [rsp+0E0h+pvData], 4; cbData
0x180048776  lea     r8, aIsfirstboot; "IsFirstBoot"
0x18004877d  mov     r9d, 4; dwType
0x180048783  mov     [rsp+0E0h+phkResult], rax; lpData
0x180048788  mov     rdx, r14; lpSubKey
0x18004878b  mov     [rbp+57h+var_78], 0
0x180048792  call    cs:__imp_RegSetKeyValueW
0x180048798  mov     ebx, eax
0x18004879a  test    eax, eax
0x18004879c  jle     short loc_1800487A4
0x18004879e  movzx   ebx, ax
0x1800487a1  or      ebx, r12d
0x1800487a4  test    ebx, ebx
0x1800487a6  jns     short loc_180048824
0x1800487a8  mov     edx, 15Ah
0x1800487ad  jmp     loc_1800485EC
0x1800487b2  mov     rcx, [rbp+57h+hKey]; hkey
0x1800487b6  lea     rax, [rbp+57h+var_74]
0x1800487ba  mov     [rsp+0E0h+pcbData], rax; pcbData
0x1800487bf  lea     r8, aUninstalltime; "UninstallTime"
0x1800487c6  lea     rax, [rbp+57h+Data]
0x1800487ca  mov     [rbp+57h+var_74], 2Ah ; '*'
0x1800487d1  mov     [rsp+0E0h+pvData], rax; pvData
0x1800487d6  mov     r9d, 2; dwFlags
0x1800487dc  mov     rdx, r14; lpSubKey
0x1800487df  mov     [rsp+0E0h+phkResult], 0; pdwType
0x1800487e8  call    cs:__imp_RegGetValueW
0x1800487ee  mov     ebx, eax
0x1800487f0  test    eax, eax
0x1800487f2  jle     short loc_1800487FA
0x1800487f4  movzx   ebx, ax
0x1800487f7  or      ebx, r12d
0x1800487fa  test    ebx, ebx
0x1800487fc  jns     short loc_180048808
0x1800487fe  mov     edx, 166h
0x180048803  jmp     loc_1800485EC
0x180048808  mov     rdx, rsi; struct _FILETIME *
0x18004880b  lea     rcx, [rbp+57h+Data]; unsigned __int16 *
0x18004880f  call    ?StringToFileTime@@YAJPEBGPEAU_FILETIME@@@Z; StringToFileTime(ushort const *,_FILETIME *)
0x180048814  mov     ebx, eax
0x180048816  test    eax, eax
0x180048818  jns     short loc_180048824
0x18004881a  mov     edx, 168h
0x18004881f  jmp     loc_1800485EC
0x180048824  mov     rcx, [rbp+57h+hKey]; hKey
0x180048828  test    rcx, rcx
0x18004882b  jz      short loc_180048833
0x18004882d  call    cs:__imp_RegCloseKey
0x180048833  xor     eax, eax
0x180048835  mov     rcx, [rbp+57h+var_30]
0x180048839  xor     rcx, rsp; StackCookie
0x18004883c  call    __security_check_cookie
0x180048841  mov     rbx, [rsp+0E0h+arg_18]
0x180048849  add     rsp, 0C0h
0x180048850  pop     r14
0x180048852  pop     r12
0x180048854  pop     rdi
0x180048855  pop     rsi
0x180048856  pop     rbp
0x180048857  retn
```
