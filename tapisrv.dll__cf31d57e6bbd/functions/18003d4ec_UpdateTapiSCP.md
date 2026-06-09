# UpdateTapiSCP

- ea: `0x18003d4ec`
- end: `0x18003d7e7`
- name: `UpdateTapiSCP`
- size: `763`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002b8f0`
- `0x18002d6d0`

## callees

- `0x180001600`
- `0x18001c8a4`
- `0x18003bcc8`
- `0x18003ca9c`
- `0x18003d4ec`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d574`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d574`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d5cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d658`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d5cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d658`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003d6b5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003d6b5`
- `KERNEL32!FileTimeToSystemTime` at `0x18003d6d7`
- `KERNEL32!FileTimeToSystemTime` at `0x18003d6d7`
- `KERNEL32!LeaveCriticalSection` at `0x18003d7bb`
- `KERNEL32!LeaveCriticalSection` at `0x18003d7bb`
- `KERNEL32!EnterCriticalSection` at `0x18003d54d`
- `KERNEL32!EnterCriticalSection` at `0x18003d54d`

## string_xrefs

- `0x18003d583`: `RegOpenKeyEx failed, error 0x%x`
- `0x18003d5eb`: `UpdateTapiSCP: RegQueryValueEx TapisrvSCPGuid failed, error 0x%x`
- `0x18003d53a`: `UpdateTapiSCP: enter, bActive: %d`
- `0x18003d683`: `UpdateTapiSCP: Telephony server is not enabled`
- `0x18003d610`: `UpdateTapiSCP: CreateTapiSCP failed`
- `0x18003d66d`: `UpdateTapiSCP: CreateTapiSCP succeeded but cannot read the guid`

## pseudocode

```c
__int64 __fastcall UpdateTapiSCP(int a1)
{
  LSTATUS v2; // eax
  LSTATUS v3; // ebx
  int TapiSCP; // ebx
  HRESULT v5; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  _WORD v14[40]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v15[40]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t pszDest[64]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v17[128]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Data[259]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int16 v19; // [rsp+4A6h] [rbp+3A6h]

  Type = 0;
  cbData = 0;
  hKey = 0;
  TRACELogPrint(524290, "UpdateTapiSCP: enter, bActive: %d", a1);
  EnterCriticalSection(&gSCPCritSec);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony", 0, 1u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    TRACELogPrint(65538, "RegOpenKeyEx failed, error 0x%x", v2);
LABEL_3:
    TapiSCP = v3 | 0x10000000;
    goto LABEL_18;
  }
  cbData = 520;
  v3 = RegQueryValueExW(hKey, L"TAPISRVSCPGUID", 0, &Type, (LPBYTE)Data, &cbData);
  v19 = 0;
  if ( v3 )
  {
    TRACELogPrint(65538, "UpdateTapiSCP: RegQueryValueEx TapisrvSCPGuid failed, error 0x%x", v3);
    if ( (dword_180051900 & 2) == 0 )
    {
      TRACELogPrint(524290, "UpdateTapiSCP: Telephony server is not enabled");
      goto LABEL_3;
    }
    TapiSCP = CreateTapiSCP();
    if ( TapiSCP < 0 )
    {
      TRACELogPrint(65538, "UpdateTapiSCP: CreateTapiSCP failed");
      goto LABEL_18;
    }
    cbData = 520;
    v3 = RegQueryValueExW(hKey, L"TAPISRVSCPGUID", 0, &Type, (LPBYTE)Data, &cbData);
    v19 = 0;
    if ( v3 )
    {
      TRACELogPrint(65538, "UpdateTapiSCP: CreateTapiSCP succeeded but cannot read the guid");
      goto LABEL_3;
    }
  }
  v15[0] = 0;
  v14[0] = 0;
  if ( a1 )
  {
    SystemTimeAsFileTime = 0;
    SystemTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(_QWORD *)&SystemTimeAsFileTime += 600000000LL * *(unsigned int *)&gdwTapiSCPTTL;
    FileTimeToSystemTime(&SystemTimeAsFileTime, &SystemTime);
    LODWORD(lpcbData) = SystemTime.wDay;
    LODWORD(phkResult) = SystemTime.wMonth;
    TapiSCP = StringCbPrintfW(
                pszDest,
                0x80u,
                L"%05d%02d%02d%02d%02d%02d%03d",
                SystemTime.wYear,
                phkResult,
                lpcbData,
                SystemTime.wHour,
                SystemTime.wMinute,
                SystemTime.wSecond,
                SystemTime.wMilliseconds);
    if ( TapiSCP < 0 )
      goto LABEL_18;
    v5 = StringCbPrintfW(
           v17,
           0x100u,
           L"E{\\pipe\\tapsrv}P{ncacn_np}C{%s}A{%s}S{%s}TTL{%s}",
           v15,
           v14,
           L"Active",
           pszDest);
  }
  else
  {
    v5 = StringCbPrintfW(
           v17,
           0x100u,
           L"E{\\pipe\\tapsrv}P{ncacn_np}C{%s}A{%s}S{%s}TTL{%s}",
           v15,
           v14,
           L"Inactive",
           &Format);
  }
  TapiSCP = v5;
  if ( v5 >= 0 )
    TapiSCP = UpdateSCP(Data, v17);
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  LeaveCriticalSection(&gSCPCritSec);
  return (unsigned int)TapiSCP;
}

```

## disassembly

```asm
0x18003d4ec  mov     [rsp-8+arg_8], rbx
0x18003d4f1  mov     [rsp-8+arg_10], rsi
0x18003d4f6  push    rbp
0x18003d4f7  lea     rbp, [rsp-3C0h]
0x18003d4ff  sub     rsp, 4C0h
0x18003d506  mov     rax, cs:__security_cookie
0x18003d50d  xor     rax, rsp
0x18003d510  mov     [rbp+3C0h+var_10], rax
0x18003d517  mov     esi, ecx
0x18003d519  mov     [rsp+4C0h+Type], 0
0x18003d521  mov     r8d, ecx
0x18003d524  mov     [rsp+4C0h+cbData], 0
0x18003d52c  mov     ecx, 80002h
0x18003d531  mov     [rsp+4C0h+hKey], 0
0x18003d53a  lea     rdx, aUpdatetapiscpE; "UpdateTapiSCP: enter, bActive: %d"
0x18003d541  call    TRACELogPrint
0x18003d546  lea     rcx, gSCPCritSec; lpCriticalSection
0x18003d54d  call    cs:__imp_EnterCriticalSection
0x18003d553  lea     rax, [rsp+4C0h+hKey]
0x18003d558  mov     r9d, 1; samDesired
0x18003d55e  xor     r8d, r8d; ulOptions
0x18003d561  mov     [rsp+4C0h+phkResult], rax; phkResult
0x18003d566  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003d56d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d574  call    cs:__imp_RegOpenKeyExW
0x18003d57a  mov     ebx, eax
0x18003d57c  test    eax, eax
0x18003d57e  jz      short loc_18003D59D
0x18003d580  mov     r8d, eax
0x18003d583  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed, error 0x%x"
0x18003d58a  mov     ecx, 10002h
0x18003d58f  call    TRACELogPrint
0x18003d594  bts     ebx, 1Ch
0x18003d598  jmp     loc_18003D7A4
0x18003d59d  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18003d5a2  lea     rax, [rsp+4C0h+cbData]
0x18003d5a7  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x18003d5ac  lea     r9, [rsp+4C0h+Type]; lpType
0x18003d5b1  lea     rax, [rbp+3C0h+Data]
0x18003d5b8  mov     [rsp+4C0h+cbData], 208h
0x18003d5c0  xor     r8d, r8d; lpReserved
0x18003d5c3  mov     [rsp+4C0h+phkResult], rax; lpData
0x18003d5c8  lea     rdx, gszRegTapisrvSCPGuid; "TAPISRVSCPGUID"
0x18003d5cf  call    cs:__imp_RegQueryValueExW
0x18003d5d5  mov     ebx, eax
0x18003d5d7  xor     eax, eax
0x18003d5d9  mov     [rbp+3C0h+var_1A], ax
0x18003d5e0  test    ebx, ebx
0x18003d5e2  jz      loc_18003D691
0x18003d5e8  mov     r8d, ebx
0x18003d5eb  lea     rdx, aUpdatetapiscpR; "UpdateTapiSCP: RegQueryValueEx TapisrvS"...
0x18003d5f2  mov     ecx, 10002h
0x18003d5f7  call    TRACELogPrint
0x18003d5fc  test    byte ptr cs:dword_180051900, 2
0x18003d603  jz      short loc_18003D683
0x18003d605  call    CreateTapiSCP
0x18003d60a  mov     ebx, eax
0x18003d60c  test    eax, eax
0x18003d60e  jns     short loc_18003D626
0x18003d610  lea     rdx, aUpdatetapiscpC_0; "UpdateTapiSCP: CreateTapiSCP failed"
0x18003d617  mov     ecx, 10002h
0x18003d61c  call    TRACELogPrint
0x18003d621  jmp     loc_18003D7A4
0x18003d626  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18003d62b  lea     rax, [rsp+4C0h+cbData]
0x18003d630  mov     [rsp+4C0h+lpcbData], rax; lpcbData
0x18003d635  lea     r9, [rsp+4C0h+Type]; lpType
0x18003d63a  lea     rax, [rbp+3C0h+Data]
0x18003d641  mov     [rsp+4C0h+cbData], 208h
0x18003d649  xor     r8d, r8d; lpReserved
0x18003d64c  mov     [rsp+4C0h+phkResult], rax; lpData
0x18003d651  lea     rdx, gszRegTapisrvSCPGuid; "TAPISRVSCPGUID"
0x18003d658  call    cs:__imp_RegQueryValueExW
0x18003d65e  mov     ebx, eax
0x18003d660  xor     eax, eax
0x18003d662  mov     [rbp+3C0h+var_1A], ax
0x18003d669  test    ebx, ebx
0x18003d66b  jz      short loc_18003D691
0x18003d66d  lea     rdx, aUpdatetapiscpC; "UpdateTapiSCP: CreateTapiSCP succeeded "...
0x18003d674  mov     ecx, 10002h
0x18003d679  call    TRACELogPrint
0x18003d67e  jmp     loc_18003D594
0x18003d683  lea     rdx, aUpdatetapiscpT; "UpdateTapiSCP: Telephony server is not "...
0x18003d68a  mov     ecx, 80002h
0x18003d68f  jmp     short loc_18003D679
0x18003d691  xor     eax, eax
0x18003d693  mov     [rbp+3C0h+var_3F0], ax
0x18003d697  mov     [rbp+3C0h+var_440], ax
0x18003d69b  test    esi, esi
0x18003d69d  jz      loc_18003D74C
0x18003d6a3  xorps   xmm0, xmm0
0x18003d6a6  mov     qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003d6ab  lea     rcx, [rsp+4C0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003d6b0  movups  xmmword ptr [rsp+4C0h+SystemTime.wYear], xmm0
0x18003d6b5  call    cs:__imp_GetSystemTimeAsFileTime
0x18003d6bb  mov     eax, cs:gdwTapiSCPTTL
0x18003d6c1  lea     rdx, [rsp+4C0h+SystemTime]; lpSystemTime
0x18003d6c6  imul    rcx, rax, 23C34600h
0x18003d6cd  add     qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18003d6d2  lea     rcx, [rsp+4C0h+SystemTimeAsFileTime]; lpFileTime
0x18003d6d7  call    cs:__imp_FileTimeToSystemTime
0x18003d6dd  movzx   ecx, [rsp+4C0h+SystemTime.wSecond]
0x18003d6e2  movzx   edx, [rsp+4C0h+SystemTime.wMinute]
0x18003d6e7  movzx   r8d, [rsp+4C0h+SystemTime.wHour]
0x18003d6ed  movzx   eax, [rsp+4C0h+SystemTime.wMilliseconds]
0x18003d6f2  movzx   r10d, [rsp+4C0h+SystemTime.wDay]
0x18003d6f8  movzx   r11d, [rsp+4C0h+SystemTime.wMonth]
0x18003d6fe  movzx   r9d, [rsp+4C0h+SystemTime.wYear]
0x18003d704  mov     [rsp+4C0h+var_478], eax
0x18003d708  mov     [rsp+4C0h+var_480], ecx
0x18003d70c  lea     rcx, [rbp+3C0h+pszDest]; pszDest
0x18003d710  mov     [rsp+4C0h+var_488], edx
0x18003d714  mov     edx, 80h; cbDest
0x18003d719  mov     dword ptr [rsp+4C0h+var_490], r8d
0x18003d71e  lea     r8, a05d02d02d02d02; "%05d%02d%02d%02d%02d%02d%03d"
0x18003d725  mov     dword ptr [rsp+4C0h+lpcbData], r10d
0x18003d72a  mov     dword ptr [rsp+4C0h+phkResult], r11d
0x18003d72f  call    StringCbPrintfW
0x18003d734  mov     ebx, eax
0x18003d736  test    eax, eax
0x18003d738  js      short loc_18003D7A4
0x18003d73a  lea     rax, [rbp+3C0h+pszDest]
0x18003d73e  mov     [rsp+4C0h+var_490], rax
0x18003d743  lea     rax, aActive; "Active"
0x18003d74a  jmp     short loc_18003D75F
0x18003d74c  lea     rax, Format
0x18003d753  mov     [rsp+4C0h+var_490], rax
0x18003d758  lea     rax, aInactive; "Inactive"
0x18003d75f  mov     [rsp+4C0h+lpcbData], rax
0x18003d764  lea     r9, [rbp+3C0h+var_3F0]
0x18003d768  lea     rax, [rbp+3C0h+var_440]
0x18003d76c  mov     edx, 100h; cbDest
0x18003d771  lea     r8, aEPipeTapsrvPNc; "E{\\pipe\\tapsrv}P{ncacn_np}C{%s}A{%s}S"...
0x18003d778  mov     [rsp+4C0h+phkResult], rax
0x18003d77d  lea     rcx, [rbp+3C0h+var_320]; pszDest
0x18003d784  call    StringCbPrintfW
0x18003d789  mov     ebx, eax
0x18003d78b  test    eax, eax
0x18003d78d  js      short loc_18003D7A4
0x18003d78f  lea     rdx, [rbp+3C0h+var_320]; unsigned __int16 *
0x18003d796  lea     rcx, [rbp+3C0h+Data]; lpszPathName
0x18003d79d  call    ?UpdateSCP@@YAJPEBGPEAG@Z; UpdateSCP(ushort const *,ushort *)
0x18003d7a2  mov     ebx, eax
0x18003d7a4  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18003d7a9  test    rcx, rcx
0x18003d7ac  jz      short loc_18003D7B4
0x18003d7ae  call    cs:__imp_RegCloseKey
0x18003d7b4  lea     rcx, gSCPCritSec; lpCriticalSection
0x18003d7bb  call    cs:__imp_LeaveCriticalSection
0x18003d7c1  mov     eax, ebx
0x18003d7c3  mov     rcx, [rbp+3C0h+var_10]
0x18003d7ca  xor     rcx, rsp; StackCookie
0x18003d7cd  call    __security_check_cookie
0x18003d7d2  lea     r11, [rsp+4C0h+var_s0]
0x18003d7da  mov     rbx, [r11+18h]
0x18003d7de  mov     rsi, [r11+20h]
0x18003d7e2  mov     rsp, r11
0x18003d7e5  pop     rbp
0x18003d7e6  retn
```
