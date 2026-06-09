# PnpInstallPendingDriverUpdates

- ea: `0x1800126cc`
- end: `0x180012da5`
- name: `PnpInstallPendingDriverUpdates`
- size: `1753`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ea20`

## callees

- `0x1800010e0`
- `0x180001110`
- `0x180001ec0`
- `0x1800040f0`
- `0x180005540`
- `0x18000b160`
- `0x18000e810`
- `0x18000fc1c`
- `0x1800117d4`
- `0x180011964`
- `0x1800126cc`
- `0x180013590`
- `0x180013744`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800127a7`
- `msvcrt!wcsrchr` at `0x1800127a7`
- `ntdll!RtlFreeHeap` at `0x180012d0f`
- `ntdll!RtlFreeHeap` at `0x180012d0f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800127db`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001281e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800127db`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001281e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012d56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001278f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001278f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ce8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ce8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012cf6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180012aea`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180012aea`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180012b8d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180012b8d`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x18001277c`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x18001277c`
- `DEVRTL!DevRtlWriteTextLog` at `0x180012a77`
- `DEVRTL!DevRtlWriteTextLog` at `0x180012c65`
- `DEVRTL!DevRtlWriteTextLog` at `0x180012a77`
- `DEVRTL!DevRtlWriteTextLog` at `0x180012c65`

## string_xrefs

- `0x180012a60`: `Creating Install Process: %ws`
- `0x180012c4a`: `Server install process exited with code 0x%08x`
- `0x180012764`: `Device Install (Pending driver updates)`

## pseudocode

```c
_BOOL8 PnpInstallPendingDriverUpdates()
{
  __int64 v0; // rdx
  int v1; // r12d
  DWORD LastError; // eax
  wchar_t *v3; // rax
  wchar_t *v4; // rsi
  NTSTATUS v5; // eax
  __int64 v6; // rbx
  WCHAR *v7; // rax
  WCHAR *v8; // rdi
  NTSTATUS v9; // eax
  int v10; // r9d
  int v11; // r9d
  int v12; // r9d
  int v13; // r9d
  int v14; // r9d
  int v15; // r9d
  int v16; // r9d
  int v17; // r9d
  int v18; // r9d
  int v19; // r9d
  int v20; // r9d
  int v21; // r9d
  DWORD v22; // eax
  HANDLE hProcess; // rsi
  HANDLE hThread; // r14
  unsigned int v25; // eax
  DWORD v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  _QWORD *v29; // rcx
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[48]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t Str[264]; // [rsp+120h] [rbp+20h] BYREF

  ExitCode = 0;
  v33 = 0;
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v32 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  v1 = pSetupCreateTextLogSectionW(0, v0, L"Device Install (Pending driver updates)", &v32);
  if ( v1 )
    DevRtlSetThreadLogToken(v32);
  if ( !GetDeviceInstallerFilename(Str) )
  {
    LastError = GetLastError();
LABEL_8:
    ExitCode = LastError;
    goto LABEL_69;
  }
  v3 = wcsrchr(Str, 0x5Cu);
  if ( !v3 )
  {
    ExitCode = 13;
    goto LABEL_69;
  }
  v4 = v3 + 1;
  v5 = RtlUnalignedStringCchLengthW(v3 + 1, 0x7FFF, &v33);
  if ( v5 < 0 )
  {
    LastError = RtlNtStatusToDosErrorNoTeb(v5);
    goto LABEL_8;
  }
  v6 = v33 + 61;
  v7 = (WCHAR *)PnpHeapAlloc(2 * (v33 + 61));
  v8 = v7;
  if ( !v7 )
  {
    ExitCode = 8;
    goto LABEL_69;
  }
  v9 = RtlStringCchCopyW(v7, v6, v4);
  if ( v9 >= 0 )
  {
    if ( (int)RtlStringCchPrintfW(v36, 17, L"%lx") < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)L" \"", v10) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)v36, v11) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)L"\"", v12) < 0 )
    {
      ExitCode = 13;
      goto LABEL_68;
    }
    if ( (int)RtlStringCchPrintfW(v36, 17, L"%lx", 1024) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)L" \"", v13) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)v36, v14) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)L"\"", v15) < 0
      || (int)RtlStringCchPrintfW(v36, 17, L"%I64x", v32) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)L" \"", v16) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)v36, v17) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)L"\"", v18) < 0
      || (int)RtlStringCchPrintfW(v36, 17, L"%p") < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)L" \"", v19) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)v36, v20) < 0
      || (int)RtlStringCchCatExW((_DWORD)v8, v6, (unsigned int)L"\"", v21) < 0 )
    {
      ExitCode = 13;
      goto LABEL_68;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v8);
    DevRtlWriteTextLog(v32, 0x2000000, 65542, "Creating Install Process: %ws", v4, 2048);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.lpDesktop = 0;
    if ( !CreateProcessW(Str, v8, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v22 = GetLastError();
      ExitCode = v22;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v22);
      goto LABEL_68;
    }
    hProcess = ProcessInformation.hProcess;
    hThread = ProcessInformation.hThread;
    v25 = WaitForPendingDriverUpdates(ProcessInformation.hProcess);
    if ( v25 )
    {
      if ( v25 != -1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v25);
        }
        ExitCode = 13;
        goto LABEL_64;
      }
      v26 = GetLastError();
      ExitCode = v26;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      {
        v28 = 73;
        goto LABEL_48;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
      if ( GetExitCodeProcess(hProcess, &ExitCode) )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, ExitCode);
            v29 = WPP_GLOBAL_Control;
          }
          if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x40000) != 0 )
            WPP_SF_d(v29[2], 75, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, ExitCode);
        }
        DevRtlWriteTextLog(v32, 0x2000000, 65542, "Server install process exited with code 0x%08x", ExitCode);
        goto LABEL_64;
      }
      v26 = GetLastError();
      ExitCode = v26;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      {
        v28 = 71;
LABEL_48:
        WPP_SF_d(v27[2], v28, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v26);
      }
    }
LABEL_64:
    if ( hThread )
      CloseHandle(hThread);
    if ( hProcess )
      CloseHandle(hProcess);
    goto LABEL_68;
  }
  ExitCode = RtlNtStatusToDosErrorNoTeb(v9);
LABEL_68:
  RtlFreeHeap(PnpHeapHandle, 0, v8);
LABEL_69:
  if ( v1 )
    pSetupCloseTextLogSection(v32, ExitCode);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  SetLastError(ExitCode);
  return ExitCode == 0;
}

```

## disassembly

```asm
0x1800126cc  push    rbp
0x1800126ce  push    rbx
0x1800126cf  push    rsi
0x1800126d0  push    rdi
0x1800126d1  push    r12
0x1800126d3  push    r14
0x1800126d5  lea     rbp, [rsp-248h]
0x1800126dd  sub     rsp, 348h
0x1800126e4  mov     rax, cs:__security_cookie
0x1800126eb  xor     rax, rsp
0x1800126ee  mov     [rbp+270h+var_40], rax
0x1800126f5  xor     eax, eax
0x1800126f7  mov     [rsp+370h+ExitCode], 0
0x1800126ff  xor     edx, edx; Val
0x180012701  mov     [rsp+370h+var_310], 0
0x18001270a  lea     rcx, [rbp+270h+StartupInfo]; void *
0x18001270e  mov     dword ptr [rbp+270h+StartupInfo+4], eax
0x180012711  lea     r8d, [rax+64h]; Size
0x180012715  call    memset_0
0x18001271a  xor     eax, eax
0x18001271c  xorps   xmm0, xmm0
0x18001271f  movups  xmmword ptr [rsp+370h+ProcessInformation.hProcess], xmm0
0x180012724  mov     qword ptr [rsp+370h+ProcessInformation.dwProcessId], rax
0x180012729  mov     [rsp+370h+var_318], rax
0x18001272e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012735  lea     r14, WPP_GLOBAL_Control
0x18001273c  cmp     rcx, r14
0x18001273f  jz      short loc_18001275D
0x180012741  test    dword ptr [rcx+1Ch], 10000000h
0x180012748  jz      short loc_18001275D
0x18001274a  mov     rcx, [rcx+10h]
0x18001274e  lea     edx, [rax+43h]
0x180012751  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180012758  call    WPP_SF_
0x18001275d  lea     r9, [rsp+370h+var_318]
0x180012762  xor     ecx, ecx
0x180012764  lea     r8, aDeviceInstallP; "Device Install (Pending driver updates)"
0x18001276b  call    pSetupCreateTextLogSectionW
0x180012770  mov     r12d, eax
0x180012773  test    eax, eax
0x180012775  jz      short loc_180012782
0x180012777  mov     rcx, [rsp+370h+var_318]
0x18001277c  call    cs:__imp_DevRtlSetThreadLogToken
0x180012782  lea     rcx, [rbp+270h+Str]
0x180012786  call    GetDeviceInstallerFilename
0x18001278b  test    eax, eax
0x18001278d  jnz     short loc_18001279E
0x18001278f  call    cs:__imp_GetLastError
0x180012795  mov     [rsp+370h+ExitCode], eax
0x180012799  jmp     loc_180012D15
0x18001279e  mov     edx, 5Ch ; '\'; Ch
0x1800127a3  lea     rcx, [rbp+270h+Str]; Str
0x1800127a7  call    cs:__imp_wcsrchr
0x1800127ad  test    rax, rax
0x1800127b0  jnz     short loc_1800127BF
0x1800127b2  mov     [rsp+370h+ExitCode], 0Dh
0x1800127ba  jmp     loc_180012D15
0x1800127bf  lea     rsi, [rax+2]
0x1800127c3  mov     edx, 7FFFh
0x1800127c8  mov     rcx, rsi
0x1800127cb  lea     r8, [rsp+370h+var_310]
0x1800127d0  call    RtlUnalignedStringCchLengthW
0x1800127d5  test    eax, eax
0x1800127d7  jns     short loc_1800127E3
0x1800127d9  mov     ecx, eax; Status
0x1800127db  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800127e1  jmp     short loc_180012795
0x1800127e3  mov     rbx, [rsp+370h+var_310]
0x1800127e8  add     rbx, 3Dh ; '='
0x1800127ec  lea     rcx, [rbx+rbx]
0x1800127f0  call    PnpHeapAlloc
0x1800127f5  mov     rdi, rax
0x1800127f8  test    rax, rax
0x1800127fb  jnz     short loc_18001280A
0x1800127fd  mov     [rsp+370h+ExitCode], 8
0x180012805  jmp     loc_180012D15
0x18001280a  mov     r8, rsi
0x18001280d  mov     rdx, rbx
0x180012810  mov     rcx, rdi
0x180012813  call    RtlStringCchCopyW
0x180012818  test    eax, eax
0x18001281a  jns     short loc_18001282D
0x18001281c  mov     ecx, eax; Status
0x18001281e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180012824  mov     [rsp+370h+ExitCode], eax
0x180012828  jmp     loc_180012D03
0x18001282d  mov     r9d, 7
0x180012833  lea     r8, aLx; "%lx"
0x18001283a  lea     rcx, [rbp+270h+var_280]
0x18001283e  lea     edx, [r9+0Ah]
0x180012842  call    RtlStringCchPrintfW
0x180012847  test    eax, eax
0x180012849  js      loc_180012D98
0x18001284f  mov     r14d, 800h
0x180012855  lea     r8, asc_18001C3A8; " \""
0x18001285c  mov     rdx, rbx
0x18001285f  mov     [rsp+370h+dwCreationFlags], r14d
0x180012864  mov     rcx, rdi
0x180012867  call    RtlStringCchCatExW
0x18001286c  test    eax, eax
0x18001286e  js      loc_180012D91
0x180012874  lea     r8, [rbp+270h+var_280]
0x180012878  mov     [rsp+370h+dwCreationFlags], r14d
0x18001287d  mov     rdx, rbx
0x180012880  mov     rcx, rdi
0x180012883  call    RtlStringCchCatExW
0x180012888  test    eax, eax
0x18001288a  js      loc_180012D91
0x180012890  lea     r8, SubStr; "\""
0x180012897  mov     [rsp+370h+dwCreationFlags], r14d
0x18001289c  mov     rdx, rbx
0x18001289f  mov     rcx, rdi
0x1800128a2  call    RtlStringCchCatExW
0x1800128a7  test    eax, eax
0x1800128a9  js      loc_180012D91
0x1800128af  mov     r9d, 400h
0x1800128b5  lea     r8, aLx; "%lx"
0x1800128bc  mov     edx, 11h
0x1800128c1  lea     rcx, [rbp+270h+var_280]
0x1800128c5  call    RtlStringCchPrintfW
0x1800128ca  test    eax, eax
0x1800128cc  js      loc_180012D84
0x1800128d2  lea     r8, asc_18001C3A8; " \""
0x1800128d9  mov     [rsp+370h+dwCreationFlags], r14d
0x1800128de  mov     rdx, rbx
0x1800128e1  mov     rcx, rdi
0x1800128e4  call    RtlStringCchCatExW
0x1800128e9  test    eax, eax
0x1800128eb  js      loc_180012D84
0x1800128f1  lea     r8, [rbp+270h+var_280]
0x1800128f5  mov     [rsp+370h+dwCreationFlags], r14d
0x1800128fa  mov     rdx, rbx
0x1800128fd  mov     rcx, rdi
0x180012900  call    RtlStringCchCatExW
0x180012905  test    eax, eax
0x180012907  js      loc_180012D84
0x18001290d  lea     r8, SubStr; "\""
0x180012914  mov     [rsp+370h+dwCreationFlags], r14d
0x180012919  mov     rdx, rbx
0x18001291c  mov     rcx, rdi
0x18001291f  call    RtlStringCchCatExW
0x180012924  test    eax, eax
0x180012926  js      loc_180012D84
0x18001292c  mov     r9, [rsp+370h+var_318]
0x180012931  lea     r8, aI64x; "%I64x"
0x180012938  mov     edx, 11h
0x18001293d  lea     rcx, [rbp+270h+var_280]
0x180012941  call    RtlStringCchPrintfW
0x180012946  test    eax, eax
0x180012948  js      loc_180012D84
0x18001294e  lea     r8, asc_18001C3A8; " \""
0x180012955  mov     [rsp+370h+dwCreationFlags], r14d
0x18001295a  mov     rdx, rbx
0x18001295d  mov     rcx, rdi
0x180012960  call    RtlStringCchCatExW
0x180012965  test    eax, eax
0x180012967  js      loc_180012D84
0x18001296d  lea     r8, [rbp+270h+var_280]
0x180012971  mov     [rsp+370h+dwCreationFlags], 900h
0x180012979  mov     rdx, rbx
0x18001297c  mov     rcx, rdi
0x18001297f  call    RtlStringCchCatExW
0x180012984  test    eax, eax
0x180012986  js      loc_180012D84
0x18001298c  lea     r8, SubStr; "\""
0x180012993  mov     [rsp+370h+dwCreationFlags], r14d
0x180012998  mov     rdx, rbx
0x18001299b  mov     rcx, rdi
0x18001299e  call    RtlStringCchCatExW
0x1800129a3  test    eax, eax
0x1800129a5  js      loc_180012D84
0x1800129ab  xor     r9d, r9d
0x1800129ae  lea     r8, aP; "%p"
0x1800129b5  lea     rcx, [rbp+270h+var_280]
0x1800129b9  lea     edx, [r9+11h]
0x1800129bd  call    RtlStringCchPrintfW
0x1800129c2  test    eax, eax
0x1800129c4  js      loc_180012D84
0x1800129ca  lea     r8, asc_18001C3A8; " \""
0x1800129d1  mov     [rsp+370h+dwCreationFlags], r14d
0x1800129d6  mov     rdx, rbx
0x1800129d9  mov     rcx, rdi
0x1800129dc  call    RtlStringCchCatExW
0x1800129e1  test    eax, eax
0x1800129e3  js      loc_180012D84
0x1800129e9  lea     r8, [rbp+270h+var_280]
0x1800129ed  mov     [rsp+370h+dwCreationFlags], 900h
0x1800129f5  mov     rdx, rbx
0x1800129f8  mov     rcx, rdi
0x1800129fb  call    RtlStringCchCatExW
0x180012a00  test    eax, eax
0x180012a02  js      loc_180012D84
0x180012a08  lea     r8, SubStr; "\""
0x180012a0f  mov     [rsp+370h+dwCreationFlags], r14d
0x180012a14  mov     rdx, rbx
0x180012a17  mov     rcx, rdi
0x180012a1a  call    RtlStringCchCatExW
0x180012a1f  test    eax, eax
0x180012a21  js      loc_180012D84
0x180012a27  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a2e  lea     r14, WPP_GLOBAL_Control
0x180012a35  cmp     rcx, r14
0x180012a38  jz      short loc_180012A5B
0x180012a3a  test    dword ptr [rcx+1Ch], 80000h
0x180012a41  jz      short loc_180012A5B
0x180012a43  mov     rcx, [rcx+10h]
0x180012a47  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180012a4e  mov     edx, 44h ; 'D'
0x180012a53  mov     r9, rdi
0x180012a56  call    WPP_SF_S
0x180012a5b  mov     rcx, [rsp+370h+var_318]
0x180012a60  lea     r9, aCreatingInstal; "Creating Install Process: %ws"
0x180012a67  mov     edx, 2000000h
0x180012a6c  mov     qword ptr [rsp+370h+bInheritHandles], rsi
0x180012a71  mov     r8d, 10006h
0x180012a77  call    cs:__imp_DevRtlWriteTextLog
0x180012a7d  xor     eax, eax
0x180012a7f  lea     rcx, [rbp+270h+StartupInfo]; void *
0x180012a83  xorps   xmm0, xmm0
0x180012a86  mov     qword ptr [rsp+370h+ProcessInformation.dwProcessId], rax
0x180012a8b  xor     edx, edx; Val
0x180012a8d  movups  xmmword ptr [rsp+370h+ProcessInformation.hProcess], xmm0
0x180012a92  lea     ebx, [rax+68h]
0x180012a95  mov     r8d, ebx; Size
0x180012a98  call    memset_0
0x180012a9d  lea     rax, [rsp+370h+ProcessInformation]
0x180012aa2  mov     [rbp+270h+StartupInfo.cb], ebx
0x180012aa5  mov     [rsp+370h+lpProcessInformation], rax; lpProcessInformation
0x180012aaa  lea     rcx, [rbp+270h+Str]; lpApplicationName
0x180012aae  lea     rax, [rbp+270h+StartupInfo]
0x180012ab2  mov     [rbp+270h+StartupInfo.lpDesktop], 0
0x180012aba  mov     [rsp+370h+lpStartupInfo], rax; lpStartupInfo
0x180012abf  xor     r9d, r9d; lpThreadAttributes
0x180012ac2  mov     [rsp+370h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180012acb  xor     r8d, r8d; lpProcessAttributes
0x180012ace  mov     [rsp+370h+lpEnvironment], 0; lpEnvironment
0x180012ad7  mov     rdx, rdi; lpCommandLine
0x180012ada  mov     [rsp+370h+dwCreationFlags], 8; dwCreationFlags
0x180012ae2  mov     [rsp+370h+bInheritHandles], 0; bInheritHandles
0x180012aea  call    cs:__imp_CreateProcessW
0x180012af0  test    eax, eax
0x180012af2  jnz     short loc_180012B39
0x180012af4  call    cs:__imp_GetLastError
0x180012afa  mov     [rsp+370h+ExitCode], eax
0x180012afe  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b05  cmp     rcx, r14
0x180012b08  jz      loc_180012D03
0x180012b0e  mov     ebx, 10000h
0x180012b13  test    [rcx+1Ch], ebx
0x180012b16  jz      loc_180012D03
0x180012b1c  mov     rcx, [rcx+10h]
0x180012b20  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180012b27  mov     edx, 45h ; 'E'
0x180012b2c  mov     r9d, eax
0x180012b2f  call    WPP_SF_d
0x180012b34  jmp     loc_180012D03
0x180012b39  mov     rsi, [rsp+370h+ProcessInformation.hProcess]
0x180012b3e  mov     r14, [rsp+370h+ProcessInformation.hThread]
0x180012b43  mov     rcx, rsi
0x180012b46  call    WaitForPendingDriverUpdates
0x180012b4b  test    eax, eax
0x180012b4d  jnz     loc_180012C6D
0x180012b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b5a  lea     rax, WPP_GLOBAL_Control
0x180012b61  mov     ebx, 10000h
0x180012b66  cmp     rcx, rax
0x180012b69  jz      short loc_180012B85
0x180012b6b  test    [rcx+1Ch], ebx
0x180012b6e  jz      short loc_180012B85
0x180012b70  mov     rcx, [rcx+10h]
0x180012b74  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180012b7b  mov     edx, 46h ; 'F'
0x180012b80  call    WPP_SF_
0x180012b85  lea     rdx, [rsp+370h+ExitCode]; lpExitCode
0x180012b8a  mov     rcx, rsi; hProcess
0x180012b8d  call    cs:__imp_GetExitCodeProcess
0x180012b93  test    eax, eax
0x180012b95  jnz     short loc_180012BDE
0x180012b97  call    cs:__imp_GetLastError
0x180012b9d  mov     [rsp+370h+ExitCode], eax
0x180012ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ba8  lea     rdx, WPP_GLOBAL_Control
0x180012baf  cmp     rcx, rdx
0x180012bb2  jz      loc_180012CE0
0x180012bb8  test    [rcx+1Ch], ebx
0x180012bbb  jz      loc_180012CE0
0x180012bc1  mov     edx, 47h ; 'G'
0x180012bc6  mov     rcx, [rcx+10h]
0x180012bca  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180012bd1  mov     r9d, eax
0x180012bd4  call    WPP_SF_d
0x180012bd9  jmp     loc_180012CE0
0x180012bde  mov     rcx, cs:WPP_GLOBAL_Control
0x180012be5  lea     rax, WPP_GLOBAL_Control
0x180012bec  cmp     rcx, rax
0x180012bef  jz      short loc_180012C46
0x180012bf1  test    [rcx+1Ch], ebx
0x180012bf4  jz      short loc_180012C1E
0x180012bf6  mov     r9d, [rsp+370h+ExitCode]
0x180012bfb  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
  ... truncated ...
```
