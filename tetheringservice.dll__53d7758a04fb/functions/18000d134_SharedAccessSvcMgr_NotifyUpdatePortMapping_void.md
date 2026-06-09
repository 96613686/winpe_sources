# SharedAccessSvcMgr::NotifyUpdatePortMapping(void)

- ea: `0x18000d134`
- end: `0x18000d272`
- name: `?NotifyUpdatePortMapping@SharedAccessSvcMgr@@AEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(SharedAccessSvcMgr *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000d584`

## callees

- `0x180002590`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d134`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d221`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d221`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d1ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d1ab`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000d1d3`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18000d1d3`

## string_xrefs

- `0x18000d19d`: `SYSTEM\CurrentControlSet\services\SharedAccess\Setup\StaticPortMapping`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SharedAccessSvcMgr::NotifyUpdatePortMapping(SharedAccessSvcMgr *this)
{
  unsigned int v2; // ebx
  SC_HANDLE v3; // rcx
  DWORD LastError; // eax
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids);
  }
  v2 = 0;
  hKey = 0;
  RegOpenKeyExW(
    HKEY_LOCAL_MACHINE,
    L"SYSTEM\\CurrentControlSet\\services\\SharedAccess\\Setup\\StaticPortMapping",
    0,
    0x20019u,
    &hKey);
  if ( hKey )
  {
    v3 = (SC_HANDLE)*((_QWORD *)this + 1);
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !ControlService(v3, 0x87u, &ServiceStatus) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, LastError);
      }
      if ( (int)v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
    }
    RegCloseKey(hKey);
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d134  mov     [rsp+arg_8], rbx
0x18000d139  mov     [rsp+arg_10], rsi
0x18000d13e  push    rdi
0x18000d13f  sub     rsp, 60h
0x18000d143  mov     rax, cs:__security_cookie
0x18000d14a  xor     rax, rsp
0x18000d14d  mov     [rsp+68h+var_10], rax
0x18000d152  mov     rdi, rcx
0x18000d155  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d15c  lea     rsi, WPP_GLOBAL_Control
0x18000d163  cmp     rcx, rsi
0x18000d166  jz      short loc_18000D183
0x18000d168  test    byte ptr [rcx+1Ch], 8
0x18000d16c  jz      short loc_18000D183
0x18000d16e  mov     rcx, [rcx+10h]
0x18000d172  lea     r8, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x18000d179  mov     edx, 1Eh
0x18000d17e  call    WPP_SF_
0x18000d183  lea     rax, [rsp+68h+hKey]
0x18000d188  xor     ebx, ebx
0x18000d18a  mov     r9d, 20019h; samDesired
0x18000d190  mov     [rsp+68h+hKey], rbx
0x18000d195  xor     r8d, r8d; ulOptions
0x18000d198  mov     [rsp+68h+phkResult], rax; phkResult
0x18000d19d  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\services\\Sh"...
0x18000d1a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d1ab  call    cs:__imp_RegOpenKeyExW
0x18000d1b1  cmp     [rsp+68h+hKey], rbx
0x18000d1b6  jz      short loc_18000D227
0x18000d1b8  mov     rcx, [rdi+8]; hService
0x18000d1bc  lea     r8, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18000d1c1  xorps   xmm0, xmm0
0x18000d1c4  mov     edx, 87h; dwControl
0x18000d1c9  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18000d1ce  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000d1d3  call    cs:__imp_ControlService
0x18000d1d9  test    eax, eax
0x18000d1db  jnz     short loc_18000D21C
0x18000d1dd  call    cs:__imp_GetLastError
0x18000d1e3  mov     ebx, eax
0x18000d1e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1ec  cmp     rcx, rsi
0x18000d1ef  jz      short loc_18000D20F
0x18000d1f1  test    byte ptr [rcx+1Ch], 1
0x18000d1f5  jz      short loc_18000D20F
0x18000d1f7  mov     rcx, [rcx+10h]
0x18000d1fb  lea     r8, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x18000d202  mov     edx, 1Fh
0x18000d207  mov     r9d, eax
0x18000d20a  call    WPP_SF_d
0x18000d20f  test    ebx, ebx
0x18000d211  jle     short loc_18000D21C
0x18000d213  movzx   ebx, bx
0x18000d216  or      ebx, 80070000h
0x18000d21c  mov     rcx, [rsp+68h+hKey]; hKey
0x18000d221  call    cs:__imp_RegCloseKey
0x18000d227  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d22e  cmp     rcx, rsi
0x18000d231  jz      short loc_18000D251
0x18000d233  test    byte ptr [rcx+1Ch], 8
0x18000d237  jz      short loc_18000D251
0x18000d239  mov     rcx, [rcx+10h]
0x18000d23d  lea     r8, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x18000d244  mov     edx, 20h ; ' '
0x18000d249  mov     r9d, ebx
0x18000d24c  call    WPP_SF_d
0x18000d251  mov     eax, ebx
0x18000d253  mov     rcx, [rsp+68h+var_10]
0x18000d258  xor     rcx, rsp; StackCookie
0x18000d25b  call    __security_check_cookie
0x18000d260  lea     r11, [rsp+68h+var_8]
0x18000d265  mov     rbx, [r11+18h]
0x18000d269  mov     rsi, [r11+20h]
0x18000d26d  mov     rsp, r11
0x18000d270  pop     rdi
0x18000d271  retn
```
