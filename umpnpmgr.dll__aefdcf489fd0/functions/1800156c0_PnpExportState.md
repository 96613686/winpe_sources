# PnpExportState

- ea: `0x1800156c0`
- end: `0x180015f6e`
- name: `PnpExportState`
- size: `2222`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015550`

## callees

- `0x1800010e0`
- `0x180001110`
- `0x180001ec0`
- `0x1800024d0`
- `0x1800040f0`
- `0x180005540`
- `0x18000e810`
- `0x1800117d4`
- `0x180011964`
- `0x180013590`
- `0x180013cd0`
- `0x1800156c0`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001582f`
- `msvcrt!wcsrchr` at `0x18001582f`
- `ntdll!RtlFreeHeap` at `0x180015eee`
- `ntdll!RtlFreeHeap` at `0x180015f06`
- `ntdll!RtlFreeHeap` at `0x180015eee`
- `ntdll!RtlFreeHeap` at `0x180015f06`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015c07`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001587d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001587d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015bf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ed2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015bf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ed2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180015dd6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180015dd6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180015b9d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180015b9d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180015c64`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180015c64`
- `DEVRTL!DevRtlWriteTextLog` at `0x18001579b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800157c6`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800157fc`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015b2f`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015c56`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015d04`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015dc4`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015e6f`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015ebc`
- `DEVRTL!DevRtlWriteTextLog` at `0x18001579b`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800157c6`
- `DEVRTL!DevRtlWriteTextLog` at `0x1800157fc`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015b2f`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015c56`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015d04`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015dc4`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015e6f`
- `DEVRTL!DevRtlWriteTextLog` at `0x180015ebc`

## string_xrefs

- `0x18001577e`: `Failed to export PnP state for system path '%ws'. Error = 0x%08X`
- `0x1800157e2`: `Failed to get device installer filename. Error = 0x%08X`
- `0x18001581a`: `Failed to create temporary file. Error = 0x%08X`
- `0x180015c47`: `Wait for process completed.`

## pseudocode

```c
__int64 __fastcall PnpExportState(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  __int64 v8; // rcx
  DWORD LastError; // eax
  const char *v10; // r9
  wchar_t *v11; // rax
  wchar_t *v12; // r12
  __int64 v13; // rbx
  void *v14; // rax
  wchar_t *v15; // r15
  __int64 v16; // rbx
  __int64 v17; // rax
  WCHAR *v18; // rdi
  int v19; // r9d
  int v20; // r9d
  int v21; // r9d
  int v22; // r9d
  int v23; // r9d
  int v24; // r9d
  int v25; // r9d
  int v26; // r9d
  int v27; // r9d
  int v28; // r9d
  int v29; // r9d
  int v30; // r9d
  DWORD v31; // eax
  HANDLE hProcess; // r12
  DWORD v33; // eax
  DWORD v34; // r15d
  DWORD v35; // eax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  __int64 v39; // rcx
  __int64 v40; // r8
  int v41; // eax
  __int64 v42; // rbx
  DWORD v43; // eax
  DWORD v44; // eax
  BOOL bInheritHandles[2]; // [rsp+20h] [rbp-E0h]
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
  BOOL bInheritHandlesl[2]; // [rsp+20h] [rbp-E0h]
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v60; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v61; // [rsp+60h] [rbp-A0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h]
  PVOID P; // [rsp+88h] [rbp-78h]
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v66[48]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t Src[264]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t Str[264]; // [rsp+340h] [rbp+240h] BYREF

  v61 = a3;
  v63 = a2;
  ExitCode = 0;
  v60 = 0;
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids);
  if ( !a2 )
  {
    ExitCode = 87;
    goto LABEL_94;
  }
  if ( a1 )
  {
    ExitCode = 50;
    DevRtlWriteTextLog(a4, 0x2000000, 1, "Failed to export PnP state for system path '%ws'. Error = 0x%08X", a1, 50);
    goto LABEL_94;
  }
  DevRtlWriteTextLog(a4, 0x2000000, 6, "Export Flags: 0x%08X", a5);
  if ( !GetDeviceInstallerFilename(Str) )
  {
    LastError = GetLastError();
    v10 = "Failed to get device installer filename. Error = 0x%08X";
LABEL_10:
    bInheritHandles[0] = LastError;
    ExitCode = LastError;
    DevRtlWriteTextLog(a4, 0x2000000, 1, v10, *(_QWORD *)bInheritHandles);
    goto LABEL_94;
  }
  if ( !CreateTempFilename(v8, (__int64)Src) )
  {
    LastError = GetLastError();
    v10 = "Failed to create temporary file. Error = 0x%08X";
    goto LABEL_10;
  }
  v11 = wcsrchr(Str, 0x5Cu);
  if ( !v11 || (v12 = v11 + 1, (int)RtlUnalignedStringCchLengthW(v11 + 1, 0x7FFF, &v60) < 0) )
  {
    ExitCode = 13;
    goto LABEL_94;
  }
  v13 = v60;
  v60 = 0;
  v14 = StringSearchAndReplace(Src);
  P = v14;
  if ( v14 )
  {
    v15 = (wchar_t *)v14;
  }
  else
  {
    ExitCode = GetLastError();
    if ( ExitCode )
      goto LABEL_94;
    v15 = Src;
  }
  if ( (int)RtlUnalignedStringCchLengthW(v15, 260, &v60) < 0 )
  {
    ExitCode = 13;
    goto LABEL_91;
  }
  v16 = v60 + 45 + v13;
  v17 = PnpHeapAlloc(2 * v16);
  v18 = (WCHAR *)v17;
  if ( !v17 )
  {
    ExitCode = 8;
    goto LABEL_91;
  }
  if ( (int)RtlStringCchCopyW(v17, v16, v12) >= 0 )
  {
    if ( (int)RtlStringCchPrintfW(v66, 17, L"%lx") < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)L" \"", v19, bInheritHandles[0], 2048) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)v66, v20, bInheritHandlesa, 2048) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)L"\"", v21, bInheritHandlesb, 2048) < 0
      || (int)RtlStringCchPrintfW(v66, 17, L"%I64x", a4) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)L" \"", v22, bInheritHandlesc, 2048) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)v66, v23, bInheritHandlesd, 2304) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)L"\"", v24, bInheritHandlese, 2048) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)L" \"", v25, bInheritHandlesf, 2048) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (_DWORD)v15, v26, bInheritHandlesg, 2304) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)L"\"", v27, bInheritHandlesh, 2048) < 0
      || (int)RtlStringCchPrintfW(v66, 17, L"%hx", a5) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)L" \"", v28, bInheritHandlesi, 2048) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)v66, v29, bInheritHandlesj, 2048) < 0
      || (int)RtlStringCchCatExW((_DWORD)v18, v16, (unsigned int)L"\"", v30, bInheritHandlesk, 2048) < 0 )
    {
      ExitCode = 13;
      goto LABEL_90;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids, v18);
    DevRtlWriteTextLog(a4, 0x2000000, 65542, "Creating Export Process");
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.lpDesktop = (LPWSTR)&qword_18001C3B0;
    if ( !CreateProcessW(Str, v18, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v31 = GetLastError();
      ExitCode = v31;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids, v31);
      goto LABEL_90;
    }
    CloseHandle(ProcessInformation.hThread);
    hProcess = ProcessInformation.hProcess;
    v33 = WaitForSingleObjectEx(ProcessInformation.hProcess, 0x927C0u, 0);
    v34 = v33;
    if ( v33 )
    {
      if ( v33 != 258 )
      {
        if ( v33 == -1 )
        {
          v44 = GetLastError();
          ExitCode = v44;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids, v44);
            v44 = ExitCode;
          }
          DevRtlWriteTextLog(a4, 0x2000000, 1, "Wait for export process failed. Error = 0x%08x", v44);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids, v33);
          }
          DevRtlWriteTextLog(a4, 0x2000000, 1, "Wait for process was not satisfied (WaitStatus = %d)", v34);
          ExitCode = 13;
        }
        goto LABEL_87;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids, v33);
      DevRtlWriteTextLog(a4, 0x2000000, 1, "Wait for export process timed out (WaitStatus = %d)", 258);
      ExitCode = 1460;
      if ( !TerminateProcess(hProcess, 0x5B4u)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      {
        v42 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v43 = GetLastError();
        v37 = 19;
        v39 = v42;
        v38 = v43;
        goto LABEL_56;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids);
      DevRtlWriteTextLog(a4, 0x2000000, 65542, "Wait for process completed.");
      if ( GetExitCodeProcess(hProcess, &ExitCode) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids, ExitCode);
        }
        if ( ExitCode )
        {
          bInheritHandlesl[0] = ExitCode;
          v40 = 1;
        }
        else
        {
          bInheritHandlesl[0] = 0;
          v40 = 65542;
        }
        DevRtlWriteTextLog(a4, 0x2000000, v40, "Export process exited with code 0x%08x", *(_QWORD *)bInheritHandlesl);
        v41 = RtlStringCchCopyW(v63, v61, Src);
        if ( v41 == -2147483643 )
        {
          ExitCode = 122;
        }
        else if ( v41 == -1073741811 )
        {
          ExitCode = 87;
        }
        else
        {
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          {
            v38 = ExitCode;
            v37 = 22;
            goto LABEL_55;
          }
        }
      }
      else
      {
        v35 = GetLastError();
        ExitCode = v35;
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        {
          v37 = 16;
          v38 = v35;
LABEL_55:
          v39 = v36[2];
LABEL_56:
          WPP_SF_d(v39, v37, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids, v38);
        }
      }
    }
LABEL_87:
    if ( hProcess )
      CloseHandle(hProcess);
    goto LABEL_90;
  }
  ExitCode = 123;
LABEL_90:
  RtlFreeHeap(PnpHeapHandle, 0, v18);
LABEL_91:
  if ( P )
    RtlFreeHeap(PnpHeapHandle, 0, P);
LABEL_94:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids);
  return ExitCode;
}

```

## disassembly

```asm
0x1800156c0  push    rbp
0x1800156c2  push    rbx
0x1800156c3  push    rsi
0x1800156c4  push    rdi
0x1800156c5  push    r12
0x1800156c7  push    r13
0x1800156c9  push    r14
0x1800156cb  push    r15
0x1800156cd  lea     rbp, [rsp-468h]
0x1800156d5  sub     rsp, 568h
0x1800156dc  mov     rax, cs:__security_cookie
0x1800156e3  xor     rax, rsp
0x1800156e6  mov     [rbp+4A0h+var_50], rax
0x1800156ed  xor     r15d, r15d
0x1800156f0  mov     [rsp+5A0h+var_540], r8d
0x1800156f5  mov     rdi, rdx
0x1800156f8  mov     [rbp+4A0h+var_520], rdx
0x1800156fc  mov     rbx, rcx
0x1800156ff  mov     [rsp+5A0h+ExitCode], r15d
0x180015704  xor     eax, eax
0x180015706  mov     [rsp+5A0h+var_548], r15
0x18001570b  lea     r8d, [r15+64h]; Size
0x18001570f  mov     dword ptr [rbp+4A0h+StartupInfo+4], eax
0x180015712  xor     edx, edx; Val
0x180015714  lea     rcx, [rbp+4A0h+StartupInfo]; void *
0x180015718  mov     r14, r9
0x18001571b  call    memset_0
0x180015720  xorps   xmm0, xmm0
0x180015723  xor     eax, eax
0x180015725  movups  xmmword ptr [rsp+5A0h+ProcessInformation.hProcess], xmm0
0x18001572a  mov     qword ptr [rsp+5A0h+ProcessInformation.dwProcessId], rax
0x18001572f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015736  lea     rax, WPP_GLOBAL_Control
0x18001573d  cmp     rcx, rax
0x180015740  jz      short loc_18001575F
0x180015742  test    dword ptr [rcx+1Ch], 10000000h
0x180015749  jz      short loc_18001575F
0x18001574b  mov     rcx, [rcx+10h]
0x18001574f  lea     edx, [r15+0Ch]
0x180015753  lea     r8, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids
0x18001575a  call    WPP_SF_
0x18001575f  test    rdi, rdi
0x180015762  jnz     short loc_180015771
0x180015764  mov     [rsp+5A0h+ExitCode], 57h ; 'W'
0x18001576c  jmp     loc_180015F16
0x180015771  mov     rcx, r14
0x180015774  test    rbx, rbx
0x180015777  jz      short loc_1800157A6
0x180015779  mov     eax, 32h ; '2'
0x18001577e  lea     r9, aFailedToExport; "Failed to export PnP state for system p"...
0x180015785  mov     [rsp+5A0h+dwCreationFlags], eax
0x180015789  mov     edx, 2000000h
0x18001578e  mov     [rsp+5A0h+ExitCode], eax
0x180015792  mov     qword ptr [rsp+5A0h+bInheritHandles], rbx
0x180015797  lea     r8d, [rax-31h]
0x18001579b  call    cs:__imp_DevRtlWriteTextLog
0x1800157a1  jmp     loc_180015F16
0x1800157a6  mov     r13d, [rbp+4A0h+arg_20]
0x1800157ad  lea     r9, aExportFlags0x0; "Export Flags: 0x%08X"
0x1800157b4  mov     esi, 2000000h
0x1800157b9  mov     [rsp+5A0h+bInheritHandles], r13d
0x1800157be  mov     edx, esi
0x1800157c0  mov     r8d, 6
0x1800157c6  call    cs:__imp_DevRtlWriteTextLog
0x1800157cc  lea     rcx, [rbp+4A0h+Str]
0x1800157d3  call    GetDeviceInstallerFilename
0x1800157d8  test    eax, eax
0x1800157da  jnz     short loc_180015807
0x1800157dc  call    cs:__imp_GetLastError
0x1800157e2  lea     r9, aFailedToGetDev; "Failed to get device installer filename"...
0x1800157e9  mov     r8d, 1
0x1800157ef  mov     [rsp+5A0h+bInheritHandles], eax
0x1800157f3  mov     edx, esi
0x1800157f5  mov     [rsp+5A0h+ExitCode], eax
0x1800157f9  mov     rcx, r14
0x1800157fc  call    cs:__imp_DevRtlWriteTextLog
0x180015802  jmp     loc_180015F16
0x180015807  lea     rdx, [rbp+4A0h+Src]
0x18001580b  call    CreateTempFilename
0x180015810  test    eax, eax
0x180015812  jnz     short loc_180015823
0x180015814  call    cs:__imp_GetLastError
0x18001581a  lea     r9, aFailedToCreate; "Failed to create temporary file. Error "...
0x180015821  jmp     short loc_1800157E9
0x180015823  mov     edx, 5Ch ; '\'; Ch
0x180015828  lea     rcx, [rbp+4A0h+Str]; Str
0x18001582f  call    cs:__imp_wcsrchr
0x180015835  test    rax, rax
0x180015838  jz      loc_180015F0E
0x18001583e  lea     r12, [rax+2]
0x180015842  mov     edx, 7FFFh
0x180015847  mov     rcx, r12
0x18001584a  lea     r8, [rsp+5A0h+var_548]
0x18001584f  call    RtlUnalignedStringCchLengthW
0x180015854  test    eax, eax
0x180015856  js      loc_180015F0E
0x18001585c  mov     rbx, [rsp+5A0h+var_548]
0x180015861  lea     rcx, [rbp+4A0h+Src]; Src
0x180015865  mov     [rsp+5A0h+var_548], r15
0x18001586a  call    StringSearchAndReplace
0x18001586f  mov     [rbp+4A0h+P], rax
0x180015873  test    rax, rax
0x180015876  jz      short loc_18001587D
0x180015878  mov     r15, rax
0x18001587b  jmp     short loc_180015893
0x18001587d  call    cs:__imp_GetLastError
0x180015883  mov     [rsp+5A0h+ExitCode], eax
0x180015887  test    eax, eax
0x180015889  jnz     loc_180015F16
0x18001588f  lea     r15, [rbp+4A0h+Src]
0x180015893  lea     r8, [rsp+5A0h+var_548]
0x180015898  mov     edx, 104h
0x18001589d  mov     rcx, r15
0x1800158a0  call    RtlUnalignedStringCchLengthW
0x1800158a5  test    eax, eax
0x1800158a7  jns     short loc_1800158B6
0x1800158a9  mov     [rsp+5A0h+ExitCode], 0Dh
0x1800158b1  jmp     loc_180015EF4
0x1800158b6  mov     rax, [rsp+5A0h+var_548]
0x1800158bb  add     rax, 2Dh ; '-'
0x1800158bf  add     rbx, rax
0x1800158c2  lea     rcx, [rbx+rbx]
0x1800158c6  call    PnpHeapAlloc
0x1800158cb  mov     rdi, rax
0x1800158ce  test    rax, rax
0x1800158d1  jnz     short loc_1800158E0
0x1800158d3  mov     [rsp+5A0h+ExitCode], 8
0x1800158db  jmp     loc_180015EF4
0x1800158e0  mov     r8, r12
0x1800158e3  mov     rdx, rbx
0x1800158e6  mov     rcx, rdi
0x1800158e9  call    RtlStringCchCopyW
0x1800158ee  xor     r12d, r12d
0x1800158f1  test    eax, eax
0x1800158f3  jns     short loc_180015902
0x1800158f5  mov     [rsp+5A0h+ExitCode], 7Bh ; '{'
0x1800158fd  jmp     loc_180015EE2
0x180015902  mov     r9d, 0Ah
0x180015908  lea     r8, aLx; "%lx"
0x18001590f  lea     rcx, [rbp+4A0h+var_4A0]
0x180015913  lea     edx, [r9+7]
0x180015917  call    RtlStringCchPrintfW
0x18001591c  test    eax, eax
0x18001591e  js      loc_180015EDA
0x180015924  lea     r8, asc_18001C3A8; " \""
0x18001592b  mov     [rsp+5A0h+dwCreationFlags], 800h
0x180015933  mov     rdx, rbx
0x180015936  mov     rcx, rdi
0x180015939  call    RtlStringCchCatExW
0x18001593e  test    eax, eax
0x180015940  js      loc_180015EDA
0x180015946  lea     r8, [rbp+4A0h+var_4A0]
0x18001594a  mov     [rsp+5A0h+dwCreationFlags], 800h
0x180015952  mov     rdx, rbx
0x180015955  mov     rcx, rdi
0x180015958  call    RtlStringCchCatExW
0x18001595d  test    eax, eax
0x18001595f  js      loc_180015EDA
0x180015965  lea     r8, SubStr; "\""
0x18001596c  mov     [rsp+5A0h+dwCreationFlags], 800h
0x180015974  mov     rdx, rbx
0x180015977  mov     rcx, rdi
0x18001597a  call    RtlStringCchCatExW
0x18001597f  test    eax, eax
0x180015981  js      loc_180015EDA
0x180015987  mov     r9, r14
0x18001598a  lea     r8, aI64x; "%I64x"
0x180015991  mov     edx, 11h
0x180015996  lea     rcx, [rbp+4A0h+var_4A0]
0x18001599a  call    RtlStringCchPrintfW
0x18001599f  test    eax, eax
0x1800159a1  js      loc_180015EDA
0x1800159a7  lea     r8, asc_18001C3A8; " \""
0x1800159ae  mov     [rsp+5A0h+dwCreationFlags], 800h
0x1800159b6  mov     rdx, rbx
0x1800159b9  mov     rcx, rdi
0x1800159bc  call    RtlStringCchCatExW
0x1800159c1  test    eax, eax
0x1800159c3  js      loc_180015EDA
0x1800159c9  lea     r8, [rbp+4A0h+var_4A0]
0x1800159cd  mov     [rsp+5A0h+dwCreationFlags], 900h
0x1800159d5  mov     rdx, rbx
0x1800159d8  mov     rcx, rdi
0x1800159db  call    RtlStringCchCatExW
0x1800159e0  test    eax, eax
0x1800159e2  js      loc_180015EDA
0x1800159e8  lea     r8, SubStr; "\""
0x1800159ef  mov     [rsp+5A0h+dwCreationFlags], 800h
0x1800159f7  mov     rdx, rbx
0x1800159fa  mov     rcx, rdi
0x1800159fd  call    RtlStringCchCatExW
0x180015a02  test    eax, eax
0x180015a04  js      loc_180015EDA
0x180015a0a  lea     r8, asc_18001C3A8; " \""
0x180015a11  mov     [rsp+5A0h+dwCreationFlags], 800h
0x180015a19  mov     rdx, rbx
0x180015a1c  mov     rcx, rdi
0x180015a1f  call    RtlStringCchCatExW
0x180015a24  test    eax, eax
0x180015a26  js      loc_180015EDA
0x180015a2c  mov     r8, r15
0x180015a2f  mov     [rsp+5A0h+dwCreationFlags], 900h
0x180015a37  mov     rdx, rbx
0x180015a3a  mov     rcx, rdi
0x180015a3d  call    RtlStringCchCatExW
0x180015a42  test    eax, eax
0x180015a44  js      loc_180015EDA
0x180015a4a  mov     r15d, 800h
0x180015a50  lea     r8, SubStr; "\""
0x180015a57  mov     rdx, rbx
0x180015a5a  mov     [rsp+5A0h+dwCreationFlags], r15d
0x180015a5f  mov     rcx, rdi
0x180015a62  call    RtlStringCchCatExW
0x180015a67  test    eax, eax
0x180015a69  js      loc_180015EDA
0x180015a6f  mov     r9d, r13d
0x180015a72  lea     r8, aHx; "%hx"
0x180015a79  mov     edx, 11h
0x180015a7e  lea     rcx, [rbp+4A0h+var_4A0]
0x180015a82  call    RtlStringCchPrintfW
0x180015a87  test    eax, eax
0x180015a89  js      loc_180015EDA
0x180015a8f  lea     r8, asc_18001C3A8; " \""
0x180015a96  mov     [rsp+5A0h+dwCreationFlags], r15d
0x180015a9b  mov     rdx, rbx
0x180015a9e  mov     rcx, rdi
0x180015aa1  call    RtlStringCchCatExW
0x180015aa6  test    eax, eax
0x180015aa8  js      loc_180015EDA
0x180015aae  lea     r8, [rbp+4A0h+var_4A0]
0x180015ab2  mov     [rsp+5A0h+dwCreationFlags], r15d
0x180015ab7  mov     rdx, rbx
0x180015aba  mov     rcx, rdi
0x180015abd  call    RtlStringCchCatExW
0x180015ac2  test    eax, eax
0x180015ac4  js      loc_180015EDA
0x180015aca  lea     r8, SubStr; "\""
0x180015ad1  mov     [rsp+5A0h+dwCreationFlags], r15d
0x180015ad6  mov     rdx, rbx
0x180015ad9  mov     rcx, rdi
0x180015adc  call    RtlStringCchCatExW
0x180015ae1  test    eax, eax
0x180015ae3  js      loc_180015EDA
0x180015ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x180015af0  lea     r13, WPP_GLOBAL_Control
0x180015af7  cmp     rcx, r13
0x180015afa  jz      short loc_180015B1D
0x180015afc  test    dword ptr [rcx+1Ch], 80000h
0x180015b03  jz      short loc_180015B1D
0x180015b05  mov     rcx, [rcx+10h]
0x180015b09  lea     r8, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids
0x180015b10  mov     edx, 0Dh
0x180015b15  mov     r9, rdi
0x180015b18  call    WPP_SF_S
0x180015b1d  lea     r9, aCreatingExport; "Creating Export Process"
0x180015b24  mov     r8d, 10006h
0x180015b2a  mov     edx, esi
0x180015b2c  mov     rcx, r14
0x180015b2f  call    cs:__imp_DevRtlWriteTextLog
0x180015b35  xor     eax, eax
0x180015b37  lea     rcx, [rbp+4A0h+StartupInfo]; void *
0x180015b3b  xorps   xmm0, xmm0
0x180015b3e  mov     qword ptr [rsp+5A0h+ProcessInformation.dwProcessId], rax
0x180015b43  xor     edx, edx; Val
0x180015b45  movups  xmmword ptr [rsp+5A0h+ProcessInformation.hProcess], xmm0
0x180015b4a  lea     ebx, [rax+68h]
0x180015b4d  mov     r8d, ebx; Size
0x180015b50  call    memset_0
0x180015b55  lea     rax, qword_18001C3B0
0x180015b5c  mov     [rbp+4A0h+StartupInfo.cb], ebx
0x180015b5f  mov     [rbp+4A0h+StartupInfo.lpDesktop], rax
0x180015b63  lea     rcx, [rbp+4A0h+Str]; lpApplicationName
0x180015b6a  lea     rax, [rsp+5A0h+ProcessInformation]
0x180015b6f  xor     r9d, r9d; lpThreadAttributes
0x180015b72  mov     [rsp+5A0h+lpProcessInformation], rax; lpProcessInformation
0x180015b77  xor     r8d, r8d; lpProcessAttributes
0x180015b7a  lea     rax, [rbp+4A0h+StartupInfo]
0x180015b7e  mov     rdx, rdi; lpCommandLine
0x180015b81  mov     [rsp+5A0h+lpStartupInfo], rax; lpStartupInfo
0x180015b86  mov     [rsp+5A0h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180015b8b  mov     [rsp+5A0h+lpEnvironment], r12; lpEnvironment
0x180015b90  mov     [rsp+5A0h+dwCreationFlags], 8; dwCreationFlags
0x180015b98  mov     [rsp+5A0h+bInheritHandles], r12d; bInheritHandles
0x180015b9d  call    cs:__imp_CreateProcessW
0x180015ba3  test    eax, eax
0x180015ba5  jnz     short loc_180015BEC
0x180015ba7  call    cs:__imp_GetLastError
0x180015bad  mov     [rsp+5A0h+ExitCode], eax
0x180015bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bb8  cmp     rcx, r13
0x180015bbb  jz      loc_180015EE2
0x180015bc1  mov     ebx, 10000h
0x180015bc6  test    [rcx+1Ch], ebx
0x180015bc9  jz      loc_180015EE2
0x180015bcf  mov     rcx, [rcx+10h]
0x180015bd3  lea     r8, WPP_e8d02699756f3b086e4657f0935e50be_Traceguids
0x180015bda  mov     edx, 0Eh
0x180015bdf  mov     r9d, eax
0x180015be2  call    WPP_SF_d
0x180015be7  jmp     loc_180015EE2
  ... truncated ...
```
