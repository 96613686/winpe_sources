# PfSvWsSwapAssessmentTask(HWND__ *,HINSTANCE__ *,ushort const *,uint)

- ea: `0x18007abe0`
- end: `0x18007ae78`
- name: `?PfSvWsSwapAssessmentTask@@YAKPEAUHWND__@@PEAUHINSTANCE__@@PEBGI@Z`
- size: `664`
- prototype: `__int64 __fastcall(HWND, HINSTANCE, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800382e0`
- `0x1800383e8`
- `0x180039f94`
- `0x18005ec74`
- `0x18007abe0`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ad26`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ad26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ae18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ae18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ad71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ad71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ac5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ac5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ae28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ae38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ae28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ae38`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18007ac53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18007ac53`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18007ad10`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18007ad10`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18007ad36`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18007ad36`

## string_xrefs

- `0x18007ae4e`: `WsSwapAssessmentTask`

## pseudocode

```c
__int64 __fastcall PfSvWsSwapAssessmentTask(HWND a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  int v3; // edi
  UINT SystemDirectoryW; // eax
  DWORD LastError; // ebx
  int v7; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ExitCode; // [rsp+54h] [rbp-ACh] BYREF
  int v9; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  int v11; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t pszDest[520]; // [rsp+310h] [rbp+210h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  ExitCode = 0;
  v9 = 0;
  v7 = 0;
  phkResult = 0;
  v3 = 1;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x103u);
  if ( !SystemDirectoryW )
    goto LABEL_2;
  if ( SystemDirectoryW >= 0x103
    || (Buffer[259] = 0, StringCbPrintfW(pszDest, 0x410u, L"\"%s\\%s\" %s", Buffer, L"winsat.exe", L"disk -wsswap") < 0) )
  {
    LastError = 122;
    goto LABEL_17;
  }
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  if ( !CreateProcessW(0, pszDest, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation)
    || (WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF),
        !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode)) )
  {
LABEL_2:
    LastError = GetLastError();
    goto LABEL_17;
  }
  LastError = ExitCode;
  if ( !ExitCode )
  {
    LastError = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winsat",
                  0,
                  0x2001Fu,
                  &phkResult);
    if ( !LastError )
    {
      LastError = PfsRegQueryValue((_DWORD)phkResult, (unsigned int)L"WsSwapInterference", 4, 4, (__int64)&v7);
      if ( !LastError )
      {
        if ( (unsigned __int16)v7 >= 0x32u || HIWORD(v7) >= 0x32u )
          goto LABEL_16;
        LastError = PfsRegQueryValue((_DWORD)phkResult, (unsigned int)L"WsSwapResult", 4, 4, (__int64)&v9);
        if ( !LastError )
        {
          LastError = PfsRegSetValue(phkResult, L"WsSwapThroughput", 4, 4, &v9);
          if ( !LastError )
          {
            v3 = 0;
LABEL_16:
            LastError = 0;
          }
        }
      }
    }
  }
LABEL_17:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  v11 = v3;
  PfTaskUpdateTaskSettings(L"WsSwapAssessmentTask", PfSvcUpdateWsSwapAssessmentCallback, &v11);
  return LastError;
}

```

## disassembly

```asm
0x18007abe0  push    rbp
0x18007abe2  push    rbx
0x18007abe3  push    rdi
0x18007abe4  push    r14
0x18007abe6  lea     rbp, [rsp-638h]
0x18007abee  sub     rsp, 738h
0x18007abf5  mov     rax, cs:__security_cookie
0x18007abfc  xor     rax, rsp
0x18007abff  mov     [rbp+650h+var_30], rax
0x18007ac06  mov     r14d, 68h ; 'h'
0x18007ac0c  lea     rcx, [rbp+650h+StartupInfo]; void *
0x18007ac10  mov     r8d, r14d; Size
0x18007ac13  xor     edx, edx; Val
0x18007ac15  call    memset_0
0x18007ac1a  xor     eax, eax
0x18007ac1c  mov     [rsp+750h+ExitCode], 0
0x18007ac24  xorps   xmm0, xmm0
0x18007ac27  mov     [rsp+750h+var_6F8], 0
0x18007ac2f  mov     ebx, 103h
0x18007ac34  mov     [rsp+750h+var_700], 0
0x18007ac3c  mov     edx, ebx; uSize
0x18007ac3e  mov     qword ptr [rbp+650h+ProcessInformation.dwProcessId], rax
0x18007ac42  lea     rcx, [rbp+650h+Buffer]; lpBuffer
0x18007ac46  mov     [rsp+750h+phkResult], rax
0x18007ac4b  lea     edi, [rax+1]
0x18007ac4e  movups  xmmword ptr [rsp+750h+ProcessInformation.hProcess], xmm0
0x18007ac53  call    cs:__imp_GetSystemDirectoryW
0x18007ac59  test    eax, eax
0x18007ac5b  jnz     short loc_18007AC6A
0x18007ac5d  call    cs:__imp_GetLastError
0x18007ac63  mov     ebx, eax
0x18007ac65  jmp     loc_18007AE0E
0x18007ac6a  cmp     eax, ebx
0x18007ac6c  jb      short loc_18007AC78
0x18007ac6e  mov     ebx, 7Ah ; 'z'
0x18007ac73  jmp     loc_18007AE0E
0x18007ac78  xor     eax, eax
0x18007ac7a  lea     r9, [rbp+650h+Buffer]
0x18007ac7e  mov     [rbp+650h+var_44A], ax
0x18007ac85  lea     r8, aSSS; "\"%s\\%s\" %s"
0x18007ac8c  lea     rax, aDiskWsswap; "disk -wsswap"
0x18007ac93  mov     edx, 410h; cbDest
0x18007ac98  mov     qword ptr [rsp+750h+dwCreationFlags], rax
0x18007ac9d  lea     rcx, [rbp+650h+pszDest]; pszDest
0x18007aca4  lea     rax, aWinsatExe; "winsat.exe"
0x18007acab  mov     qword ptr [rsp+750h+bInheritHandles], rax
0x18007acb0  call    StringCbPrintfW
0x18007acb5  test    eax, eax
0x18007acb7  js      short loc_18007AC6E
0x18007acb9  xor     edx, edx; Val
0x18007acbb  lea     rcx, [rbp+650h+StartupInfo+4]; void *
0x18007acbf  lea     r8d, [rdx+64h]; Size
0x18007acc3  call    memset_0
0x18007acc8  lea     rax, [rsp+750h+ProcessInformation]
0x18007accd  mov     [rbp+650h+StartupInfo.cb], r14d
0x18007acd1  mov     [rsp+750h+lpProcessInformation], rax; lpProcessInformation
0x18007acd6  lea     rdx, [rbp+650h+pszDest]; lpCommandLine
0x18007acdd  lea     rax, [rbp+650h+StartupInfo]
0x18007ace1  xor     r9d, r9d; lpThreadAttributes
0x18007ace4  mov     [rsp+750h+lpStartupInfo], rax; lpStartupInfo
0x18007ace9  xor     r8d, r8d; lpProcessAttributes
0x18007acec  mov     [rsp+750h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18007acf5  xor     ecx, ecx; lpApplicationName
0x18007acf7  mov     [rsp+750h+lpEnvironment], 0; lpEnvironment
0x18007ad00  mov     [rsp+750h+dwCreationFlags], 8000000h; dwCreationFlags
0x18007ad08  mov     [rsp+750h+bInheritHandles], 0; bInheritHandles
0x18007ad10  call    cs:__imp_CreateProcessW
0x18007ad16  test    eax, eax
0x18007ad18  jz      loc_18007AC5D
0x18007ad1e  mov     rcx, [rsp+750h+ProcessInformation.hProcess]; hHandle
0x18007ad23  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007ad26  call    cs:__imp_WaitForSingleObject
0x18007ad2c  mov     rcx, [rsp+750h+ProcessInformation.hProcess]; hProcess
0x18007ad31  lea     rdx, [rsp+750h+ExitCode]; lpExitCode
0x18007ad36  call    cs:__imp_GetExitCodeProcess
0x18007ad3c  test    eax, eax
0x18007ad3e  jz      loc_18007AC5D
0x18007ad44  mov     ebx, [rsp+750h+ExitCode]
0x18007ad48  test    ebx, ebx
0x18007ad4a  jnz     loc_18007AE0E
0x18007ad50  lea     rax, [rsp+750h+phkResult]
0x18007ad55  mov     r9d, 2001Fh; samDesired
0x18007ad5b  xor     r8d, r8d; ulOptions
0x18007ad5e  mov     qword ptr [rsp+750h+bInheritHandles], rax; phkResult
0x18007ad63  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18007ad6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007ad71  call    cs:__imp_RegOpenKeyExW
0x18007ad77  mov     ebx, eax
0x18007ad79  test    eax, eax
0x18007ad7b  jnz     loc_18007AE0E
0x18007ad81  mov     rcx, [rsp+750h+phkResult]
0x18007ad86  lea     r14d, [rbx+4]
0x18007ad8a  lea     rax, [rsp+750h+var_700]
0x18007ad8f  mov     r9d, r14d
0x18007ad92  mov     r8d, r14d
0x18007ad95  mov     qword ptr [rsp+750h+bInheritHandles], rax
0x18007ad9a  lea     rdx, aWsswapinterfer; "WsSwapInterference"
0x18007ada1  call    PfsRegQueryValue
0x18007ada6  mov     ebx, eax
0x18007ada8  test    eax, eax
0x18007adaa  jnz     short loc_18007AE0E
0x18007adac  cmp     word ptr [rsp+750h+var_700], 32h ; '2'
0x18007adb2  jnb     short loc_18007AE0C
0x18007adb4  cmp     word ptr [rsp+750h+var_700+2], 32h ; '2'
0x18007adba  jnb     short loc_18007AE0C
0x18007adbc  mov     rcx, [rsp+750h+phkResult]
0x18007adc1  lea     rax, [rsp+750h+var_6F8]
0x18007adc6  mov     r9d, r14d
0x18007adc9  mov     qword ptr [rsp+750h+bInheritHandles], rax
0x18007adce  mov     r8d, r14d
0x18007add1  lea     rdx, aWsswapresult; "WsSwapResult"
0x18007add8  call    PfsRegQueryValue
0x18007addd  mov     ebx, eax
0x18007addf  test    eax, eax
0x18007ade1  jnz     short loc_18007AE0E
0x18007ade3  mov     rcx, [rsp+750h+phkResult]
0x18007ade8  lea     rax, [rsp+750h+var_6F8]
0x18007aded  mov     r9d, r14d
0x18007adf0  mov     qword ptr [rsp+750h+bInheritHandles], rax
0x18007adf5  mov     r8d, r14d
0x18007adf8  lea     rdx, aWsswapthroughp; "WsSwapThroughput"
0x18007adff  call    PfsRegSetValue
0x18007ae04  mov     ebx, eax
0x18007ae06  test    eax, eax
0x18007ae08  jnz     short loc_18007AE0E
0x18007ae0a  xor     edi, edi
0x18007ae0c  xor     ebx, ebx
0x18007ae0e  mov     rcx, [rsp+750h+phkResult]; hKey
0x18007ae13  test    rcx, rcx
0x18007ae16  jz      short loc_18007AE1E
0x18007ae18  call    cs:__imp_RegCloseKey
0x18007ae1e  mov     rcx, [rsp+750h+ProcessInformation.hThread]; hObject
0x18007ae23  test    rcx, rcx
0x18007ae26  jz      short loc_18007AE2E
0x18007ae28  call    cs:__imp_CloseHandle
0x18007ae2e  mov     rcx, [rsp+750h+ProcessInformation.hProcess]; hObject
0x18007ae33  test    rcx, rcx
0x18007ae36  jz      short loc_18007AE3E
0x18007ae38  call    cs:__imp_CloseHandle
0x18007ae3e  lea     r8, [rsp+750h+var_6E8]
0x18007ae43  mov     [rsp+750h+var_6E8], edi
0x18007ae47  lea     rdx, ?PfSvcUpdateWsSwapAssessmentCallback@@YAJPEAUITaskSettings3@@PEAUIMaintenanceSettings@@PEAKPEAX@Z; PfSvcUpdateWsSwapAssessmentCallback(ITaskSettings3 *,IMaintenanceSettings *,ulong *,void *)
0x18007ae4e  lea     rcx, aWsswapassessme; "WsSwapAssessmentTask"
0x18007ae55  call    PfTaskUpdateTaskSettings
0x18007ae5a  mov     eax, ebx
0x18007ae5c  mov     rcx, [rbp+650h+var_30]
0x18007ae63  xor     rcx, rsp; StackCookie
0x18007ae66  call    __security_check_cookie
0x18007ae6b  add     rsp, 738h
0x18007ae72  pop     r14
0x18007ae74  pop     rdi
0x18007ae75  pop     rbx
0x18007ae76  pop     rbp
0x18007ae77  retn
```
