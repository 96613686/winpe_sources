# CWinSATTaskMangerTask::DoRunWinSAT(ulong &)

- ea: `0x180020428`
- end: `0x18002077c`
- name: `?DoRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEAK@Z`
- size: `852`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this, LPDWORD lpExitCode)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020dcc`

## callees

- `0x180005394`
- `0x1800071d0`
- `0x18000e6ac`
- `0x18000e864`
- `0x1800151bb`
- `0x18001c414`
- `0x18001cb1c`
- `0x180020428`
- `0x1800215b8`
- `0x180021904`
- `0x18002bed4`
- `0x180031010`

## import_xrefs

- `msvcrt!_time64` at `0x18002061d`
- `msvcrt!_time64` at `0x18002061d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020696`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020696`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800206ea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800206ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020708`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180020583`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180020583`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800206fa`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800206fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002073e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002073e`

## string_xrefs

- `0x18002048c`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x1800204f5`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x1800205bb`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x1800206da`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020480`: `cannot get system directory`
- `0x1800204e9`: `WinSAT command line = '%S'`
- `0x18002066e`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x18002065f`: `Cannot write %s to the registry`

## pseudocode

```c
__int64 __fastcall CWinSATTaskMangerTask::DoRunWinSAT(CWinSATTaskMangerTask *this, LPDWORD lpExitCode)
{
  int SystemDirectoryInMString; // ebx
  __int64 result; // rax
  __int64 v6; // rcx
  struct _STARTUPINFOW *p_StartupInfo; // rax
  unsigned int v8; // ebx
  void (__fastcall *v9)(__int64 *, __int64, _QWORD); // rax
  __int64 LastError; // r8
  void (__fastcall *v11)(__int64 *, __int64, __int64); // rax
  __time64_t v12; // rbx
  __int64 v13; // rcx
  DWORD v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // r8
  void (__fastcall *v17)(__int64 *, __int64, __int64); // rax
  __int64 v18; // [rsp+50h] [rbp-B8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+70h] [rbp-98h]
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v23; // [rsp+120h] [rbp+18h] BYREF
  __int64 v24; // [rsp+128h] [rbp+20h] BYREF

  v20 = -2;
  try
  {
    ((void (*)(void))mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>)();
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v24,
      260);
    SystemDirectoryInMString = GetSystemDirectoryInMString(&v18);
    if ( SystemDirectoryInMString < 0 )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 201, "cannot get system directory");
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v18);
      return (unsigned int)SystemDirectoryInMString;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      &v24,
      L"%s\\winsat.exe formal -log -cancelevent %s",
      *(_QWORD *)(v18 + 24),
      *(_QWORD *)(*((_QWORD *)this + 15) + 24LL));
    Log_Text_F(
      "base\\winsat\\api-dll\\winsattaskmangertask.cpp",
      209,
      "WinSAT command line = '%S'",
      *(const wchar_t **)(v24 + 24));
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    v6 = 104;
    p_StartupInfo = &StartupInfo;
    do
    {
      LOBYTE(p_StartupInfo->cb) = 0;
      p_StartupInfo = (struct _STARTUPINFOW *)((char *)p_StartupInfo + 1);
      --v6;
    }
    while ( v6 );
    StartupInfo.cb = 104;
    v8 = CreateProcessW(0, *(LPWSTR *)(v24 + 24), 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation);
    v9 = (void (__fastcall *)(__int64 *, __int64, _QWORD))*((_QWORD *)this + 17);
    if ( v9 )
      v9(qword_1800487B0, 10267, v8);
    if ( !v8 )
    {
      Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 231, "cannot start winsat process");
      LastError = GetLastError();
      v11 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
      if ( v11 )
        v11(qword_1800487B0, 10269, LastError);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v18);
      return 2147500037LL;
    }
    v23 = 0;
    v12 = _time64(0);
    if ( CWinSATTaskMangerTask::IncrimentWinSATIdleRunCount(this, &v23) )
    {
      if ( v23 == 1 && (unsigned int)RegHelper::WriteQWORDValue(v13, L"FirstIdleRunTimeDate", v12) )
        Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)L"FirstIdleRunTimeDate");
      CWinSATTaskMangerTask::SQMLogWinSATRun(this, v23, v12);
    }
    v14 = WaitForSingleObject(ProcessInformation.hProcess, 0xDE2B0u);
    v15 = -2147467259;
    switch ( v14 )
    {
      case 0xFFFFFFFF:
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 259, "cannot wait for WinSAT, wait failed");
        break;
      case 0x80u:
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 263, "WinSAT process abandoned while waiting");
        break;
      case 0x102u:
        Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 267, "waiting for WinSAT to finish timed out");
        break;
      default:
        if ( GetExitCodeProcess(ProcessInformation.hProcess, lpExitCode) )
        {
          v15 = 0;
        }
        else
        {
          v16 = GetLastError();
          v17 = (void (__fastcall *)(__int64 *, __int64, __int64))*((_QWORD *)this + 17);
          if ( v17 )
            v17(qword_1800487B0, 10269, v16);
        }
        goto LABEL_28;
    }
    SetEvent(*((HANDLE *)this + 14));
LABEL_28:
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v18);
    result = v15;
  }
  catch ( std::bad_alloc )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 291, "out of memory exception caught");
    if ( *((_QWORD *)this + 17) )
      (*((void (__fastcall **)(__int64 *, __int64, __int64))this + 17))(qword_1800487B0, 10269, 8);
    return 2147500037LL;
  }
  catch ( ... )
  {
    Log_Text_F("base\\winsat\\api-dll\\winsattaskmangertask.cpp", 295, "unknown exception caught");
    if ( *((_QWORD *)this + 17) )
      (*((void (__fastcall **)(__int64 *, __int64, __int64))this + 17))(qword_1800487B0, 10269, 574);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180020428  mov     rax, rsp
0x18002042b  mov     [rax+8], rcx
0x18002042f  push    rdi
0x180020430  push    r12
0x180020432  push    r14
0x180020434  sub     rsp, 0F0h
0x18002043b  mov     [rsp+108h+var_98], 0FFFFFFFFFFFFFFFEh
0x180020444  mov     [rax+10h], rbx
0x180020448  mov     r14, rdx
0x18002044b  mov     rdi, rcx
0x18002044e  mov     ebx, 104h
0x180020453  mov     edx, ebx
0x180020455  lea     rcx, [rsp+108h+var_B8]
0x18002045a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18002045f  nop
0x180020460  mov     edx, ebx
0x180020462  lea     rcx, [rsp+108h+arg_18]
0x18002046a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18002046f  nop
0x180020470  lea     rcx, [rsp+108h+var_B8]
0x180020475  call    ?GetSystemDirectoryInMString@@YAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; GetSystemDirectoryInMString(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x18002047a  mov     ebx, eax
0x18002047c  test    eax, eax
0x18002047e  jns     short loc_1800204B8
0x180020480  lea     r8, aCannotGetSyste; "cannot get system directory"
0x180020487  mov     edx, 0C9h
0x18002048c  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020493  call    Log_Text_F
0x180020498  nop
0x180020499  lea     rcx, [rsp+108h+arg_18]
0x1800204a1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800204a6  nop
0x1800204a7  lea     rcx, [rsp+108h+var_B8]
0x1800204ac  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800204b1  mov     eax, ebx
0x1800204b3  jmp     loc_180020766
0x1800204b8  mov     r9, [rdi+78h]
0x1800204bc  mov     r9, [r9+18h]
0x1800204c0  mov     r8, [rsp+108h+var_B8]
0x1800204c5  mov     r8, [r8+18h]
0x1800204c9  lea     rdx, aSWinsatExeForm; "%s\\winsat.exe formal -log -cancelevent"...
0x1800204d0  lea     rcx, [rsp+108h+arg_18]
0x1800204d8  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x1800204dd  mov     r9, [rsp+108h+arg_18]
0x1800204e5  mov     r9, [r9+18h]
0x1800204e9  lea     r8, aWinsatCommandL; "WinSAT command line = '%S'"
0x1800204f0  mov     edx, 0D1h
0x1800204f5  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800204fc  call    Log_Text_F
0x180020501  mov     ebx, 68h ; 'h'
0x180020506  mov     r8d, ebx; Size
0x180020509  xor     edx, edx; Val
0x18002050b  lea     rcx, [rsp+108h+StartupInfo]; void *
0x180020513  call    memset_0
0x180020518  xorps   xmm0, xmm0
0x18002051b  xor     eax, eax
0x18002051d  movups  xmmword ptr [rsp+108h+ProcessInformation.hProcess], xmm0
0x180020522  mov     qword ptr [rsp+108h+ProcessInformation.dwProcessId], rax
0x180020527  mov     ecx, ebx
0x180020529  lea     rax, [rsp+108h+StartupInfo]
0x180020531  mov     byte ptr [rax], 0
0x180020534  inc     rax
0x180020537  sub     rcx, 1; lpApplicationName
0x18002053b  jnz     short loc_180020531
0x18002053d  mov     [rsp+108h+StartupInfo.cb], ebx
0x180020544  lea     rax, [rsp+108h+ProcessInformation]
0x180020549  mov     [rsp+108h+lpProcessInformation], rax; lpProcessInformation
0x18002054e  lea     rax, [rsp+108h+StartupInfo]
0x180020556  mov     [rsp+108h+lpStartupInfo], rax; lpStartupInfo
0x18002055b  mov     [rsp+108h+lpCurrentDirectory], rcx; lpCurrentDirectory
0x180020560  mov     [rsp+108h+lpEnvironment], rcx; lpEnvironment
0x180020565  mov     [rsp+108h+dwCreationFlags], 8000000h; dwCreationFlags
0x18002056d  mov     [rsp+108h+bInheritHandles], ecx; bInheritHandles
0x180020571  xor     r9d, r9d; lpThreadAttributes
0x180020574  xor     r8d, r8d; lpProcessAttributes
0x180020577  mov     rdx, [rsp+108h+arg_18]
0x18002057f  mov     rdx, [rdx+18h]; lpCommandLine
0x180020583  call    cs:__imp_CreateProcessW
0x180020589  mov     ebx, eax
0x18002058b  mov     rax, [rdi+88h]
0x180020592  test    rax, rax
0x180020595  jz      short loc_1800205AB
0x180020597  mov     r8d, ebx
0x18002059a  mov     edx, 281Bh
0x18002059f  lea     rcx, qword_1800487B0
0x1800205a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205ab  test    ebx, ebx
0x1800205ad  jnz     short loc_180020610
0x1800205af  lea     r8, aCannotStartWin; "cannot start winsat process"
0x1800205b6  mov     edx, 0E7h
0x1800205bb  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800205c2  call    Log_Text_F
0x1800205c7  call    cs:__imp_GetLastError
0x1800205cd  mov     r8d, eax
0x1800205d0  mov     rax, [rdi+88h]
0x1800205d7  test    rax, rax
0x1800205da  jz      short loc_1800205EE
0x1800205dc  mov     edx, 281Dh
0x1800205e1  lea     rcx, qword_1800487B0
0x1800205e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205ed  nop
0x1800205ee  lea     rcx, [rsp+108h+arg_18]
0x1800205f6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800205fb  nop
0x1800205fc  lea     rcx, [rsp+108h+var_B8]
0x180020601  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180020606  mov     eax, 80004005h
0x18002060b  jmp     loc_180020766
0x180020610  mov     [rsp+108h+arg_10], 0
0x18002061b  xor     ecx, ecx; Time
0x18002061d  call    cs:__imp__time64
0x180020623  mov     rbx, rax
0x180020626  lea     rdx, [rsp+108h+arg_10]; unsigned int *
0x18002062e  mov     rcx, rdi; this
0x180020631  call    ?IncrimentWinSATIdleRunCount@CWinSATTaskMangerTask@@AEAA_NAEAK@Z; CWinSATTaskMangerTask::IncrimentWinSATIdleRunCount(ulong &)
0x180020636  test    al, al
0x180020638  jz      short loc_18002068C
0x18002063a  cmp     [rsp+108h+arg_10], 1
0x180020642  jnz     short loc_18002067A
0x180020644  mov     r8, rbx
0x180020647  lea     r12, aFirstidlerunti; "FirstIdleRunTimeDate"
0x18002064e  mov     rdx, r12
0x180020651  call    ?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z; RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)
0x180020656  test    eax, eax
0x180020658  jz      short loc_18002067A
0x18002065a  mov     qword ptr [rsp+108h+bInheritHandles], r12; char
0x18002065f  lea     r9, aCannotWriteSTo; "Cannot write %s to the registry"
0x180020666  mov     r8d, eax
0x180020669  mov     edx, 13Ch
0x18002066e  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020675  call    Record_Win32Error_w
0x18002067a  mov     r8, rbx; unsigned __int64
0x18002067d  mov     edx, [rsp+108h+arg_10]; unsigned int
0x180020684  mov     rcx, rdi; this
0x180020687  call    ?SQMLogWinSATRun@CWinSATTaskMangerTask@@AEAAXK_K@Z; CWinSATTaskMangerTask::SQMLogWinSATRun(ulong,unsigned __int64)
0x18002068c  mov     edx, 0DE2B0h; dwMilliseconds
0x180020691  mov     rcx, [rsp+108h+ProcessInformation.hProcess]; hHandle
0x180020696  call    cs:__imp_WaitForSingleObject
0x18002069c  mov     ebx, 80004005h
0x1800206a1  cmp     eax, 0FFFFFFFFh
0x1800206a4  jnz     short loc_1800206B4
0x1800206a6  lea     r8, aCannotWaitForW; "cannot wait for WinSAT, wait failed"
0x1800206ad  mov     edx, 103h
0x1800206b2  jmp     short loc_1800206DA
0x1800206b4  cmp     eax, 80h
0x1800206b9  jnz     short loc_1800206C9
0x1800206bb  lea     r8, aWinsatProcessA; "WinSAT process abandoned while waiting"
0x1800206c2  mov     edx, 107h
0x1800206c7  jmp     short loc_1800206DA
0x1800206c9  cmp     eax, 102h
0x1800206ce  jnz     short loc_1800206F2
0x1800206d0  lea     r8, aWaitingForWins; "waiting for WinSAT to finish timed out"
0x1800206d7  lea     edx, [rax+9]
0x1800206da  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800206e1  call    Log_Text_F
0x1800206e6  mov     rcx, [rdi+70h]; hEvent
0x1800206ea  call    cs:__imp_SetEvent
0x1800206f0  jmp     short loc_18002072E
0x1800206f2  mov     rdx, r14; lpExitCode
0x1800206f5  mov     rcx, [rsp+108h+ProcessInformation.hProcess]; hProcess
0x1800206fa  call    cs:__imp_GetExitCodeProcess
0x180020700  test    eax, eax
0x180020702  jz      short loc_180020708
0x180020704  xor     ebx, ebx
0x180020706  jmp     short loc_18002072E
0x180020708  call    cs:__imp_GetLastError
0x18002070e  mov     r8d, eax
0x180020711  mov     rax, [rdi+88h]
0x180020718  test    rax, rax
0x18002071b  jz      short loc_18002072E
0x18002071d  mov     edx, 281Dh
0x180020722  lea     rcx, qword_1800487B0
0x180020729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002072e  mov     rcx, [rsp+108h+ProcessInformation.hProcess]; hObject
0x180020733  call    cs:__imp_CloseHandle
0x180020739  mov     rcx, [rsp+108h+ProcessInformation.hThread]; hObject
0x18002073e  call    cs:__imp_CloseHandle
0x180020744  nop
0x180020745  lea     rcx, [rsp+108h+arg_18]
0x18002074d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180020752  nop
0x180020753  lea     rcx, [rsp+108h+var_B8]
0x180020758  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18002075d  mov     eax, ebx
0x18002075f  jmp     short loc_180020766
0x180020761  mov     eax, 80004005h
0x180020766  mov     rbx, [rsp+108h+arg_8]
0x18002076e  add     rsp, 0F0h
0x180020775  pop     r14
0x180020777  pop     r12
0x180020779  pop     rdi
0x18002077a  retn
```
