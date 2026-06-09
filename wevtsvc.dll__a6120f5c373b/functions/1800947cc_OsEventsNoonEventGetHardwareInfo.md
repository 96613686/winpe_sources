# OsEventsNoonEventGetHardwareInfo

- ea: `0x1800947cc`
- end: `0x1800949db`
- name: `OsEventsNoonEventGetHardwareInfo`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800945d0`

## callees

- `0x180006770`
- `0x180017b98`
- `0x180092008`
- `0x1800947cc`
- `0x18009aee0`
- `0x18009bb88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800948fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009493f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800948fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009493f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800948c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800948c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009483a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009483a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180094877`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180094877`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18009480e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18009480e`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180094979`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180094979`

## string_xrefs

- `0x1800948b6`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\OemInfo`

## pseudocode

```c
__int64 __fastcall OsEventsNoonEventGetHardwareInfo(__int64 a1)
{
  _WORD *v1; // rdi
  DWORD LastError; // eax
  _WORD *v4; // rdi
  HKEY *phkResult; // rax
  DWORDLONG v6; // rax
  bool v7; // zf
  DWORD nSize; // [rsp+30h] [rbp-39h] BYREF
  DWORD Type; // [rsp+34h] [rbp-35h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-31h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-29h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+70h] [rbp+7h] BYREF

  v1 = (_WORD *)(a1 + 1316);
  nSize = 260;
  if ( !GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, (LPWSTR)(a1 + 1316), &nSize) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, LastError);
    }
    *v1 = 0;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  *(_DWORD *)(a1 + 1304) = SystemInfo.dwNumberOfProcessors;
  v4 = (_WORD *)(a1 + 788);
  *(_DWORD *)(a1 + 1300) = SystemInfo.wProcessorArchitecture;
  hKey = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\OemInfo",
         0,
         0x20019u,
         phkResult) )
  {
    *(_WORD *)(a1 + 1044) = 0;
LABEL_15:
    *v4 = 0;
    goto LABEL_16;
  }
  Type = 0;
  nSize = 256;
  if ( RegQueryValueExW(hKey, L"WbemOem", 0, &Type, (LPBYTE)(a1 + 788), &nSize) || Type != 1 )
    *v4 = 0;
  v4 = (_WORD *)(a1 + 1044);
  nSize = 256;
  if ( RegQueryValueExW(hKey, L"WbemProduct", 0, &Type, (LPBYTE)(a1 + 1044), &nSize) || Type != 1 )
    goto LABEL_15;
LABEL_16:
  memset_0(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  if ( GlobalMemoryStatusEx(&Buffer) )
  {
    v6 = Buffer.ullTotalPhys >> 20;
    v7 = (Buffer.ullTotalPhys & 0xFFFFF) == 0;
    *(_DWORD *)(a1 + 1308) = Buffer.ullTotalPhys >> 20;
    if ( !v7 )
      *(_DWORD *)(a1 + 1308) = v6 + 1;
  }
  else
  {
    *(_DWORD *)(a1 + 1308) = 0;
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1800947cc  mov     [rsp-8+arg_8], rbx
0x1800947d1  mov     [rsp-8+arg_10], rdi
0x1800947d6  push    rbp
0x1800947d7  lea     rbp, [rsp-57h]
0x1800947dc  sub     rsp, 0C0h
0x1800947e3  mov     rax, cs:__security_cookie
0x1800947ea  xor     rax, rsp
0x1800947ed  mov     [rbp+57h+var_10], rax
0x1800947f1  lea     rdi, [rcx+524h]
0x1800947f8  mov     [rbp+57h+nSize], 104h
0x1800947ff  mov     rbx, rcx
0x180094802  lea     r8, [rbp+57h+nSize]; nSize
0x180094806  mov     rdx, rdi; lpBuffer
0x180094809  mov     ecx, 7; NameType
0x18009480e  call    cs:__imp_GetComputerNameExW
0x180094814  test    eax, eax
0x180094816  jnz     short loc_180094864
0x180094818  mov     rax, cs:WPP_GLOBAL_Control
0x18009481f  lea     rcx, WPP_GLOBAL_Control
0x180094826  cmp     rax, rcx
0x180094829  jz      short loc_18009485F
0x18009482b  test    dword ptr [rax+1Ch], 4000h
0x180094832  jz      short loc_18009485F
0x180094834  cmp     byte ptr [rax+19h], 2
0x180094838  jb      short loc_18009485F
0x18009483a  call    cs:__imp_GetLastError
0x180094840  mov     rcx, cs:WPP_GLOBAL_Control
0x180094847  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18009484e  mov     edx, 2Fh ; '/'
0x180094853  mov     r9d, eax
0x180094856  mov     rcx, [rcx+10h]
0x18009485a  call    WPP_SF_d
0x18009485f  xor     eax, eax
0x180094861  mov     [rdi], ax
0x180094864  xorps   xmm0, xmm0
0x180094867  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x18009486b  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x18009486f  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180094873  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x180094877  call    cs:__imp_GetSystemInfo
0x18009487d  mov     eax, [rbp+57h+SystemInfo.dwNumberOfProcessors]
0x180094880  lea     rcx, [rbp+57h+hKey]
0x180094884  mov     [rbx+518h], eax
0x18009488a  lea     rdi, [rbx+314h]
0x180094891  movzx   eax, word ptr [rbp+57h+SystemInfo]
0x180094895  mov     [rbx+514h], eax
0x18009489b  mov     [rbp+57h+hKey], 0
0x1800948a3  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800948a8  mov     r9d, 20019h; samDesired
0x1800948ae  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800948b3  xor     r8d, r8d; ulOptions
0x1800948b6  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800948bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800948c4  call    cs:__imp_RegOpenKeyExW
0x1800948ca  test    eax, eax
0x1800948cc  jnz     loc_180094953
0x1800948d2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800948d6  lea     r9, [rbp+57h+Type]; lpType
0x1800948da  mov     [rbp+57h+Type], eax
0x1800948dd  lea     rdx, aWbemoem; "WbemOem"
0x1800948e4  lea     rax, [rbp+57h+nSize]
0x1800948e8  mov     [rbp+57h+nSize], 100h
0x1800948ef  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x1800948f4  xor     r8d, r8d; lpReserved
0x1800948f7  mov     [rsp+0C0h+phkResult], rdi; lpData
0x1800948fc  call    cs:__imp_RegQueryValueExW
0x180094902  test    eax, eax
0x180094904  jnz     short loc_18009490C
0x180094906  cmp     [rbp+57h+Type], 1
0x18009490a  jz      short loc_180094911
0x18009490c  xor     eax, eax
0x18009490e  mov     [rdi], ax
0x180094911  mov     rcx, [rbp+57h+hKey]; hKey
0x180094915  lea     rax, [rbp+57h+nSize]
0x180094919  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18009491e  lea     rdi, [rbx+414h]
0x180094925  lea     r9, [rbp+57h+Type]; lpType
0x180094929  mov     [rsp+0C0h+phkResult], rdi; lpData
0x18009492e  xor     r8d, r8d; lpReserved
0x180094931  mov     [rbp+57h+nSize], 100h
0x180094938  lea     rdx, aWbemproduct; "WbemProduct"
0x18009493f  call    cs:__imp_RegQueryValueExW
0x180094945  test    eax, eax
0x180094947  jnz     short loc_18009494F
0x180094949  cmp     [rbp+57h+Type], 1
0x18009494d  jz      short loc_18009495F
0x18009494f  xor     eax, eax
0x180094951  jmp     short loc_18009495C
0x180094953  xor     eax, eax
0x180094955  mov     [rbx+414h], ax
0x18009495c  mov     [rdi], ax
0x18009495f  mov     edi, 40h ; '@'
0x180094964  lea     rcx, [rbp+57h+Buffer]; void *
0x180094968  mov     r8d, edi; Size
0x18009496b  xor     edx, edx; Val
0x18009496d  call    memset_0
0x180094972  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x180094976  mov     [rbp+57h+Buffer.dwLength], edi
0x180094979  call    cs:__imp_GlobalMemoryStatusEx
0x18009497f  test    eax, eax
0x180094981  jz      short loc_1800949A5
0x180094983  mov     rax, [rbp+57h+Buffer.ullTotalPhys]
0x180094987  shr     rax, 14h
0x18009498b  test    [rbp+57h+Buffer.ullTotalPhys], 0FFFFFh
0x180094993  mov     [rbx+51Ch], eax
0x180094999  jz      short loc_1800949AF
0x18009499b  inc     eax
0x18009499d  mov     [rbx+51Ch], eax
0x1800949a3  jmp     short loc_1800949AF
0x1800949a5  mov     dword ptr [rbx+51Ch], 0
0x1800949af  lea     rcx, [rbp+57h+hKey]
0x1800949b3  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800949b8  xor     eax, eax
0x1800949ba  mov     rcx, [rbp+57h+var_10]
0x1800949be  xor     rcx, rsp; StackCookie
0x1800949c1  call    __security_check_cookie
0x1800949c6  lea     r11, [rsp+0C0h+var_s0]
0x1800949ce  mov     rbx, [r11+18h]
0x1800949d2  mov     rdi, [r11+20h]
0x1800949d6  mov     rsp, r11
0x1800949d9  pop     rbp
0x1800949da  retn
```
