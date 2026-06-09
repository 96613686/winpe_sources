# PnpUninstallDriver

- ea: `0x180014a84`
- end: `0x180015492`
- name: `PnpUninstallDriver`
- size: `2574`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, __int64, const wchar_t *, const wchar_t *Src, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800148a0`

## callees

- `0x1800010e0`
- `0x180001110`
- `0x180001ec0`
- `0x1800024d0`
- `0x1800040f0`
- `0x180005540`
- `0x18000b160`
- `0x18000e810`
- `0x18000fc1c`
- `0x1800117d4`
- `0x180011964`
- `0x180013590`
- `0x180014a84`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180014bc5`
- `msvcrt!wcsrchr` at `0x180014bc5`
- `ntdll!RtlFreeHeap` at `0x18001541d`
- `ntdll!RtlFreeHeap` at `0x180015434`
- `ntdll!RtlFreeHeap` at `0x18001541d`
- `ntdll!RtlFreeHeap` at `0x180015434`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015184`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001511f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001534b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001511f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001534b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001516e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001516e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015406`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180015309`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180015309`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180015115`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180015115`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800151ca`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800151ca`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x180014b93`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x180014b93`
- `DEVRTL!DevRtlWriteTextLog` at `0x180014b6b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800150ac`
- `DEVRTL!DevRtlWriteTextLog` at `0x18001528f`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800153f8`
- `DEVRTL!DevRtlWriteTextLog` at `0x180014b6b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800150ac`
- `DEVRTL!DevRtlWriteTextLog` at `0x18001528f`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800153f8`

## string_xrefs

- `0x180015276`: `Server install process exited with code 0x%08x`
- `0x180014b4d`: `{Plug and Play Service: Driver Uninstall for %ws}`
- `0x180014b7b`: `Driver Uninstall`
- `0x180015092`: `Creating Uninstall Process: %ws`
- `0x1800153e2`: `{Plug and Play Service: Driver Uninstall exit(%08x)}`

## pseudocode

```c
__int64 __fastcall PnpUninstallDriver(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *Src,
        unsigned int a6,
        _DWORD *a7)
{
  WCHAR *v8; // rdi
  HANDLE hProcess; // r15
  const wchar_t *v10; // r12
  wchar_t *v11; // rbx
  __int64 v12; // rdx
  int v13; // eax
  DWORD LastError; // eax
  wchar_t *v15; // rax
  __int64 v16; // rbx
  const wchar_t *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  void *v20; // r15
  __int64 v21; // rbx
  __int64 v22; // rax
  wchar_t *v23; // r14
  int v24; // r9d
  int v25; // r9d
  int v26; // r9d
  int v27; // r9d
  int v28; // r9d
  int v29; // r9d
  int v30; // r9d
  int v31; // r9d
  int v32; // r9d
  int v33; // r9d
  int v34; // r9d
  int v35; // r9d
  int v36; // r9d
  int v37; // r9d
  int v38; // r9d
  int v39; // r9d
  int v40; // r9d
  int v41; // r9d
  int v42; // r9d
  int v43; // r9d
  int v44; // r9d
  DWORD v45; // eax
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  _QWORD *v49; // rcx
  __int64 v50; // rbx
  char bInheritHandles; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesb; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesc; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesd; // [rsp+20h] [rbp-E0h]
  char bInheritHandlese; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesf; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesg; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesh; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesi; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesj; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesk; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesl; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesm; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesn; // [rsp+20h] [rbp-E0h]
  char bInheritHandleso; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesp; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesq; // [rsp+20h] [rbp-E0h]
  char bInheritHandlesr; // [rsp+20h] [rbp-E0h]
  char bInheritHandless; // [rsp+20h] [rbp-E0h]
  char bInheritHandlest; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v74; // [rsp+58h] [rbp-A8h] BYREF
  void *v75; // [rsp+60h] [rbp-A0h]
  __int64 v76; // [rsp+68h] [rbp-98h] BYREF
  int v77; // [rsp+70h] [rbp-90h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v79; // [rsp+90h] [rbp-70h]
  __int64 v80; // [rsp+98h] [rbp-68h]
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v82[48]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t Str[264]; // [rsp+140h] [rbp+40h] BYREF

  v80 = a1;
  v8 = 0;
  hProcess = 0;
  v74 = a4;
  ExitCode = 0;
  v76 = 0;
  v75 = 0;
  v10 = a4;
  *(&StartupInfo.cb + 1) = 0;
  v11 = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  if ( a7 )
    *a7 = 0;
  if ( v10 )
  {
    v77 = 0;
    bInheritHandles = (char)a2;
    DevRtlWriteTextLog(v10, 0x2000000, 131076, "{Plug and Play Service: Driver Uninstall for %ws}");
  }
  else
  {
    v13 = pSetupCreateTextLogSectionW(a2, v12, L"Driver Uninstall", &v74);
    v10 = v74;
    v77 = v13;
  }
  DevRtlSetThreadLogToken(v10);
  if ( !GetDeviceInstallerFilename(Str) )
  {
    LastError = GetLastError();
LABEL_11:
    ExitCode = LastError;
    goto LABEL_21;
  }
  v15 = wcsrchr(Str, 0x5Cu);
  if ( !v15 || (v79 = v15 + 1, (int)RtlUnalignedStringCchLengthW(v15 + 1, 0x7FFF, &v76) < 0) )
  {
    LastError = 13;
    goto LABEL_11;
  }
  v16 = v76;
  v76 = 0;
  v17 = (const wchar_t *)StringSearchAndReplace(a2);
  v74 = v17;
  if ( v17 )
  {
    a2 = v17;
  }
  else
  {
    LastError = GetLastError();
    ExitCode = LastError;
    if ( LastError )
      goto LABEL_20;
  }
  if ( (int)RtlUnalignedStringCchLengthW(a2, 260, &v76) < 0 )
  {
    LastError = 13;
    ExitCode = 13;
    goto LABEL_20;
  }
  v18 = v76 + 22;
  v76 = 0;
  v19 = v18 + v16;
  v20 = StringSearchAndReplace(Src);
  if ( !v20 )
  {
    LastError = GetLastError();
    ExitCode = LastError;
    if ( LastError )
    {
LABEL_28:
      hProcess = 0;
      goto LABEL_20;
    }
    v20 = (void *)Src;
  }
  if ( (int)RtlUnalignedStringCchLengthW(v20, 522, &v76) < 0 )
  {
    LastError = 13;
    ExitCode = 13;
    goto LABEL_28;
  }
  v21 = v76 + 52 + v19;
  v22 = PnpHeapAlloc(2 * v21);
  v8 = (WCHAR *)v22;
  if ( !v22 )
  {
    LastError = 8;
LABEL_31:
    hProcess = v75;
    ExitCode = LastError;
    goto LABEL_20;
  }
  v23 = v79;
  if ( (int)RtlStringCchCopyW(v22, v21, v79) < 0 )
  {
    LastError = 123;
    goto LABEL_31;
  }
  if ( (int)RtlStringCchPrintfW(v82, 17, L"%lx") < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L" \"", v24, bInheritHandles, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)v82, v25, bInheritHandlesa, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L"\"", v26, bInheritHandlesb, 2048) < 0
    || (int)RtlStringCchPrintfW(v82, 17, L"%lx", a6) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L" \"", v27, bInheritHandlesc, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)v82, v28, bInheritHandlesd, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L"\"", v29, bInheritHandlese, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L" \"", v30, bInheritHandlesf, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (_DWORD)a2, v31, bInheritHandlesg, 2304) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L"\"", v32, bInheritHandlesh, 2048) < 0 )
  {
    LastError = 13;
    goto LABEL_31;
  }
  if ( (int)RtlStringCchPrintfW(v82, 17, L"%hx", 0) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L" \"", v33, bInheritHandlesi, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)v82, v34, bInheritHandlesj, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L"\"", v35, bInheritHandlesk, 2048) < 0
    || (int)RtlStringCchPrintfW(v82, 17, L"%I64x", v10) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L" \"", v36, bInheritHandlesl, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)v82, v37, bInheritHandlesm, 2304) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L"\"", v38, bInheritHandlesn, 2048) < 0
    || (int)RtlStringCchPrintfW(v82, 17, L"%p", v80) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L" \"", v39, bInheritHandleso, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)v82, v40, bInheritHandlesp, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L"\"", v41, bInheritHandlesq, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L" \"", v42, bInheritHandlesr, 2048) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (_DWORD)v20, v43, bInheritHandless, 2304) < 0
    || (int)RtlStringCchCatExW((_DWORD)v8, v21, (unsigned int)L"\"", v44, bInheritHandlest, 2048) < 0 )
  {
    LastError = 13;
    hProcess = 0;
    ExitCode = 13;
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, v8);
  DevRtlWriteTextLog(v10, 0x2000000, 65542, "Creating Uninstall Process: %ws", v23);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = (LPWSTR)&qword_18001C3B0;
  if ( !CreateProcessW(Str, v8, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    ExitCode = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, LastError);
      LastError = ExitCode;
    }
    hProcess = 0;
    goto LABEL_20;
  }
  CloseHandle(ProcessInformation.hThread);
  hProcess = ProcessInformation.hProcess;
  v45 = WaitForSingleObjectEx(ProcessInformation.hProcess, 0xFFFFFFFF, 0);
  if ( v45 )
  {
    if ( v45 == 258 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, 258);
      ExitCode = 1460;
      if ( TerminateProcess(hProcess, 0x5B4u)
        || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) == 0 )
      {
        goto LABEL_78;
      }
      v50 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      v47 = 59;
      v48 = v50;
LABEL_77:
      WPP_SF_d(v48, v47, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, LastError);
LABEL_78:
      LastError = ExitCode;
      goto LABEL_20;
    }
    if ( v45 != -1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, v45);
      LastError = 13;
      ExitCode = 13;
      goto LABEL_20;
    }
    LastError = GetLastError();
    ExitCode = LastError;
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      v47 = 60;
      goto LABEL_76;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
    if ( GetExitCodeProcess(hProcess, &ExitCode) )
    {
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, ExitCode);
          v49 = WPP_GLOBAL_Control;
        }
        if ( v49 != &WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x40000) != 0 )
          WPP_SF_d(v49[2], 62, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids, ExitCode);
      }
      DevRtlWriteTextLog(v10, 0x2000000, 65542, "Server install process exited with code 0x%08x", ExitCode);
      LastError = ExitCode;
      if ( ExitCode == 3010 )
      {
        LastError = 0;
        ExitCode = 0;
        if ( a7 )
          *a7 = 1;
      }
      goto LABEL_20;
    }
    LastError = GetLastError();
    ExitCode = LastError;
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      v47 = 56;
LABEL_76:
      v48 = v46[2];
      goto LABEL_77;
    }
  }
LABEL_20:
  v11 = (wchar_t *)v74;
LABEL_21:
  if ( v77 )
    pSetupCloseTextLogSection(v10, LastError);
  else
    DevRtlWriteTextLog(v10, 0x2000000, 262148, "{Plug and Play Service: Driver Uninstall exit(%08x)}", LastError);
  if ( hProcess )
    CloseHandle(hProcess);
  if ( v8 )
    RtlFreeHeap(PnpHeapHandle, 0, v8);
  if ( v11 )
    RtlFreeHeap(PnpHeapHandle, 0, v11);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids);
  return ExitCode;
}

```

## disassembly

```asm
0x180014a84  mov     [rsp-8+arg_10], rbx
0x180014a89  push    rbp
0x180014a8a  push    rsi
0x180014a8b  push    rdi
0x180014a8c  push    r12
0x180014a8e  push    r13
0x180014a90  push    r14
0x180014a92  push    r15
0x180014a94  lea     rbp, [rsp-260h]
0x180014a9c  sub     rsp, 360h
0x180014aa3  mov     rax, cs:__security_cookie
0x180014aaa  xor     rax, rsp
0x180014aad  mov     [rbp+290h+var_40], rax
0x180014ab4  mov     r14, [rbp+290h+Src]
0x180014abb  mov     rsi, rdx
0x180014abe  mov     r13, [rbp+290h+arg_30]
0x180014ac5  xor     eax, eax
0x180014ac7  mov     [rbp+290h+var_2F8], rcx
0x180014acb  xor     edi, edi
0x180014acd  xor     r15d, r15d
0x180014ad0  mov     [rsp+390h+var_338], r9
0x180014ad5  xor     edx, edx; Val
0x180014ad7  mov     [rsp+390h+ExitCode], 0
0x180014adf  lea     rcx, [rbp+290h+StartupInfo]; void *
0x180014ae3  mov     [rsp+390h+var_328], 0
0x180014aec  lea     r8d, [rdi+64h]; Size
0x180014af0  mov     [rsp+390h+var_330], r15
0x180014af5  mov     r12, r9
0x180014af8  mov     dword ptr [rbp+290h+StartupInfo+4], eax
0x180014afb  xor     ebx, ebx
0x180014afd  call    memset_0
0x180014b02  xorps   xmm0, xmm0
0x180014b05  xor     eax, eax
0x180014b07  movups  xmmword ptr [rsp+390h+ProcessInformation.hProcess], xmm0
0x180014b0c  mov     qword ptr [rbp+290h+ProcessInformation.dwProcessId], rax
0x180014b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b17  lea     rax, WPP_GLOBAL_Control
0x180014b1e  cmp     rcx, rax
0x180014b21  jz      short loc_180014B3F
0x180014b23  test    dword ptr [rcx+1Ch], 10000000h
0x180014b2a  jz      short loc_180014B3F
0x180014b2c  mov     rcx, [rcx+10h]
0x180014b30  lea     edx, [rdi+34h]
0x180014b33  lea     r8, WPP_62776862b79f37ec5ad8eff833594fa0_Traceguids
0x180014b3a  call    WPP_SF_
0x180014b3f  test    r13, r13
0x180014b42  jz      short loc_180014B48
0x180014b44  mov     [r13+0], ebx
0x180014b48  test    r12, r12
0x180014b4b  jz      short loc_180014B73
0x180014b4d  lea     r9, aPlugAndPlaySer; "{Plug and Play Service: Driver Uninstal"...
0x180014b54  mov     [rsp+390h+var_320], ebx
0x180014b58  mov     edx, 2000000h
0x180014b5d  mov     qword ptr [rsp+390h+bInheritHandles], rsi
0x180014b62  mov     r8d, 20004h
0x180014b68  mov     rcx, r12
0x180014b6b  call    cs:__imp_DevRtlWriteTextLog
0x180014b71  jmp     short loc_180014B90
0x180014b73  lea     r9, [rsp+390h+var_338]
0x180014b78  mov     rcx, rsi
0x180014b7b  lea     r8, aDriverUninstal; "Driver Uninstall"
0x180014b82  call    pSetupCreateTextLogSectionW
0x180014b87  mov     r12, [rsp+390h+var_338]
0x180014b8c  mov     [rsp+390h+var_320], eax
0x180014b90  mov     rcx, r12
0x180014b93  call    cs:__imp_DevRtlSetThreadLogToken
0x180014b99  lea     rcx, [rbp+290h+Str]
0x180014b9d  call    GetDeviceInstallerFilename
0x180014ba2  test    eax, eax
0x180014ba4  jnz     short loc_180014BBC
0x180014ba6  call    cs:__imp_GetLastError
0x180014bac  mov     [rsp+390h+ExitCode], eax
0x180014bb0  lea     r14, WPP_GLOBAL_Control
0x180014bb7  jmp     loc_180014C4F
0x180014bbc  mov     edx, 5Ch ; '\'; Ch
0x180014bc1  lea     rcx, [rbp+290h+Str]; Str
0x180014bc5  call    cs:__imp_wcsrchr
0x180014bcb  test    rax, rax
0x180014bce  jnz     short loc_180014BD7
0x180014bd0  mov     eax, 0Dh
0x180014bd5  jmp     short loc_180014BAC
0x180014bd7  add     rax, 2
0x180014bdb  lea     r8, [rsp+390h+var_328]
0x180014be0  mov     rcx, rax
0x180014be3  mov     [rbp+290h+var_300], rax
0x180014be7  mov     edx, 7FFFh
0x180014bec  call    RtlUnalignedStringCchLengthW
0x180014bf1  test    eax, eax
0x180014bf3  js      short loc_180014BD0
0x180014bf5  mov     rbx, [rsp+390h+var_328]
0x180014bfa  mov     rcx, rsi; Src
0x180014bfd  mov     [rsp+390h+var_328], rdi
0x180014c02  call    StringSearchAndReplace
0x180014c07  mov     [rsp+390h+var_338], rax
0x180014c0c  test    rax, rax
0x180014c0f  jz      short loc_180014C16
0x180014c11  mov     rsi, rax
0x180014c14  jmp     short loc_180014C24
0x180014c16  call    cs:__imp_GetLastError
0x180014c1c  mov     [rsp+390h+ExitCode], eax
0x180014c20  test    eax, eax
0x180014c22  jnz     short loc_180014C43
0x180014c24  lea     r8, [rsp+390h+var_328]
0x180014c29  mov     edx, 104h
0x180014c2e  mov     rcx, rsi
0x180014c31  call    RtlUnalignedStringCchLengthW
0x180014c36  test    eax, eax
0x180014c38  jns     short loc_180014C69
0x180014c3a  mov     eax, 0Dh
0x180014c3f  mov     [rsp+390h+ExitCode], eax
0x180014c43  lea     r14, WPP_GLOBAL_Control
0x180014c4a  mov     rbx, [rsp+390h+var_338]
0x180014c4f  cmp     [rsp+390h+var_320], 0
0x180014c54  mov     rcx, r12
0x180014c57  jz      loc_1800153E2
0x180014c5d  mov     edx, eax
0x180014c5f  call    pSetupCloseTextLogSection
0x180014c64  jmp     loc_1800153FE
0x180014c69  mov     rax, [rsp+390h+var_328]
0x180014c6e  mov     rcx, r14; Src
0x180014c71  add     rax, 16h
0x180014c75  mov     [rsp+390h+var_328], rdi
0x180014c7a  add     rbx, rax
0x180014c7d  call    StringSearchAndReplace
0x180014c82  mov     r15, rax
0x180014c85  test    rax, rax
0x180014c88  jnz     short loc_180014C9B
0x180014c8a  call    cs:__imp_GetLastError
0x180014c90  mov     [rsp+390h+ExitCode], eax
0x180014c94  test    eax, eax
0x180014c96  jnz     short loc_180014CBA
0x180014c98  mov     r15, r14
0x180014c9b  lea     r8, [rsp+390h+var_328]
0x180014ca0  mov     edx, 20Ah
0x180014ca5  mov     rcx, r15
0x180014ca8  call    RtlUnalignedStringCchLengthW
0x180014cad  test    eax, eax
0x180014caf  jns     short loc_180014CBF
0x180014cb1  mov     eax, 0Dh
0x180014cb6  mov     [rsp+390h+ExitCode], eax
0x180014cba  mov     r15, rdi
0x180014cbd  jmp     short loc_180014C43
0x180014cbf  mov     rax, [rsp+390h+var_328]
0x180014cc4  add     rax, 34h ; '4'
0x180014cc8  add     rbx, rax
0x180014ccb  lea     rcx, [rbx+rbx]
0x180014ccf  call    PnpHeapAlloc
0x180014cd4  mov     rdi, rax
0x180014cd7  test    rax, rax
0x180014cda  jnz     short loc_180014CED
0x180014cdc  lea     eax, [rdi+8]
0x180014cdf  mov     r15, [rsp+390h+var_330]
0x180014ce4  mov     [rsp+390h+ExitCode], eax
0x180014ce8  jmp     loc_180014C43
0x180014ced  mov     r14, [rbp+290h+var_300]
0x180014cf1  mov     rdx, rbx
0x180014cf4  mov     r8, r14
0x180014cf7  mov     rcx, rdi
0x180014cfa  call    RtlStringCchCopyW
0x180014cff  test    eax, eax
0x180014d01  jns     short loc_180014D0A
0x180014d03  mov     eax, 7Bh ; '{'
0x180014d08  jmp     short loc_180014CDF
0x180014d0a  mov     r9d, 9
0x180014d10  lea     r8, aLx; "%lx"
0x180014d17  lea     rcx, [rbp+290h+var_280]
0x180014d1b  lea     edx, [r9+8]
0x180014d1f  call    RtlStringCchPrintfW
0x180014d24  test    eax, eax
0x180014d26  js      loc_1800153D8
0x180014d2c  lea     r8, asc_18001C3A8; " \""
0x180014d33  mov     [rsp+390h+dwCreationFlags], 800h
0x180014d3b  mov     rdx, rbx
0x180014d3e  mov     rcx, rdi
0x180014d41  call    RtlStringCchCatExW
0x180014d46  test    eax, eax
0x180014d48  js      loc_1800153D8
0x180014d4e  lea     r8, [rbp+290h+var_280]
0x180014d52  mov     [rsp+390h+dwCreationFlags], 800h
0x180014d5a  mov     rdx, rbx
0x180014d5d  mov     rcx, rdi
0x180014d60  call    RtlStringCchCatExW
0x180014d65  test    eax, eax
0x180014d67  js      loc_1800153D8
0x180014d6d  lea     r8, SubStr; "\""
0x180014d74  mov     [rsp+390h+dwCreationFlags], 800h
0x180014d7c  mov     rdx, rbx
0x180014d7f  mov     rcx, rdi
0x180014d82  call    RtlStringCchCatExW
0x180014d87  test    eax, eax
0x180014d89  js      loc_1800153D8
0x180014d8f  mov     r9d, [rbp+290h+arg_28]
0x180014d96  lea     r8, aLx; "%lx"
0x180014d9d  mov     edx, 11h
0x180014da2  lea     rcx, [rbp+290h+var_280]
0x180014da6  call    RtlStringCchPrintfW
0x180014dab  test    eax, eax
0x180014dad  js      loc_1800153D8
0x180014db3  lea     r8, asc_18001C3A8; " \""
0x180014dba  mov     [rsp+390h+dwCreationFlags], 800h
0x180014dc2  mov     rdx, rbx
0x180014dc5  mov     rcx, rdi
0x180014dc8  call    RtlStringCchCatExW
0x180014dcd  test    eax, eax
0x180014dcf  js      loc_1800153D8
0x180014dd5  lea     r8, [rbp+290h+var_280]
0x180014dd9  mov     [rsp+390h+dwCreationFlags], 800h
0x180014de1  mov     rdx, rbx
0x180014de4  mov     rcx, rdi
0x180014de7  call    RtlStringCchCatExW
0x180014dec  test    eax, eax
0x180014dee  js      loc_1800153D8
0x180014df4  lea     r8, SubStr; "\""
0x180014dfb  mov     [rsp+390h+dwCreationFlags], 800h
0x180014e03  mov     rdx, rbx
0x180014e06  mov     rcx, rdi
0x180014e09  call    RtlStringCchCatExW
0x180014e0e  test    eax, eax
0x180014e10  js      loc_1800153D8
0x180014e16  lea     r8, asc_18001C3A8; " \""
0x180014e1d  mov     [rsp+390h+dwCreationFlags], 800h
0x180014e25  mov     rdx, rbx
0x180014e28  mov     rcx, rdi
0x180014e2b  call    RtlStringCchCatExW
0x180014e30  test    eax, eax
0x180014e32  js      loc_1800153D8
0x180014e38  mov     r8, rsi
0x180014e3b  mov     [rsp+390h+dwCreationFlags], 900h
0x180014e43  mov     rdx, rbx
0x180014e46  mov     rcx, rdi
0x180014e49  call    RtlStringCchCatExW
0x180014e4e  xor     esi, esi
0x180014e50  test    eax, eax
0x180014e52  js      loc_1800153D8
0x180014e58  lea     r8, SubStr; "\""
0x180014e5f  mov     [rsp+390h+dwCreationFlags], 800h
0x180014e67  mov     rdx, rbx
0x180014e6a  mov     rcx, rdi
0x180014e6d  call    RtlStringCchCatExW
0x180014e72  test    eax, eax
0x180014e74  js      loc_1800153D8
0x180014e7a  xor     r9d, r9d
0x180014e7d  lea     r8, aHx; "%hx"
0x180014e84  lea     edx, [rsi+11h]
0x180014e87  lea     rcx, [rbp+290h+var_280]
0x180014e8b  call    RtlStringCchPrintfW
0x180014e90  test    eax, eax
0x180014e92  js      loc_1800153C7
0x180014e98  lea     r8, asc_18001C3A8; " \""
0x180014e9f  mov     [rsp+390h+dwCreationFlags], 800h
0x180014ea7  mov     rdx, rbx
0x180014eaa  mov     rcx, rdi
0x180014ead  call    RtlStringCchCatExW
0x180014eb2  test    eax, eax
0x180014eb4  js      loc_1800153C7
0x180014eba  lea     r8, [rbp+290h+var_280]
0x180014ebe  mov     [rsp+390h+dwCreationFlags], 800h
0x180014ec6  mov     rdx, rbx
0x180014ec9  mov     rcx, rdi
0x180014ecc  call    RtlStringCchCatExW
0x180014ed1  test    eax, eax
0x180014ed3  js      loc_1800153C7
0x180014ed9  lea     r8, SubStr; "\""
0x180014ee0  mov     [rsp+390h+dwCreationFlags], 800h
0x180014ee8  mov     rdx, rbx
0x180014eeb  mov     rcx, rdi
0x180014eee  call    RtlStringCchCatExW
0x180014ef3  test    eax, eax
0x180014ef5  js      loc_1800153C7
0x180014efb  mov     r9, r12
0x180014efe  lea     r8, aI64x; "%I64x"
0x180014f05  lea     edx, [rsi+11h]
0x180014f08  lea     rcx, [rbp+290h+var_280]
0x180014f0c  call    RtlStringCchPrintfW
0x180014f11  test    eax, eax
0x180014f13  js      loc_1800153C7
0x180014f19  lea     r8, asc_18001C3A8; " \""
0x180014f20  mov     [rsp+390h+dwCreationFlags], 800h
0x180014f28  mov     rdx, rbx
0x180014f2b  mov     rcx, rdi
0x180014f2e  call    RtlStringCchCatExW
0x180014f33  test    eax, eax
0x180014f35  js      loc_1800153C7
0x180014f3b  lea     r8, [rbp+290h+var_280]
0x180014f3f  mov     [rsp+390h+dwCreationFlags], 900h
0x180014f47  mov     rdx, rbx
0x180014f4a  mov     rcx, rdi
0x180014f4d  call    RtlStringCchCatExW
0x180014f52  test    eax, eax
0x180014f54  js      loc_1800153C7
0x180014f5a  lea     r8, SubStr; "\""
0x180014f61  mov     [rsp+390h+dwCreationFlags], 800h
0x180014f69  mov     rdx, rbx
0x180014f6c  mov     rcx, rdi
0x180014f6f  call    RtlStringCchCatExW
0x180014f74  test    eax, eax
0x180014f76  js      loc_1800153C7
0x180014f7c  mov     r9, [rbp+290h+var_2F8]
0x180014f80  lea     r8, aP; "%p"
0x180014f87  lea     edx, [rsi+11h]
  ... truncated ...
```
