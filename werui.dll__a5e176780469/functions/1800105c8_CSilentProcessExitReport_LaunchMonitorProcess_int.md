# CSilentProcessExitReport::LaunchMonitorProcess(int *)

- ea: `0x1800105c8`
- end: `0x18001092f`
- name: `?LaunchMonitorProcess@CSilentProcessExitReport@@AEAAJPEAH@Z`
- size: `871`
- prototype: `__int64 __fastcall(CSilentProcessExitReport *__hidden this, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010234`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x180005c80`
- `0x1800091b0`
- `0x180009580`
- `0x1800105c8`
- `0x180010ccc`
- `0x180012718`
- `0x180013b38`
- `0x180013ba0`
- `0x180013e3c`
- `0x180016c1e`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180010704`
- `msvcrt!_wcsnicmp` at `0x18001071c`
- `msvcrt!_wcsnicmp` at `0x180010704`
- `msvcrt!_wcsnicmp` at `0x18001071c`
- `msvcrt!wcschr` at `0x1800106d6`
- `msvcrt!wcschr` at `0x1800106d6`
- `KERNEL32!CreateProcessW` at `0x1800107d7`
- `KERNEL32!CreateProcessW` at `0x1800107d7`
- `KERNEL32!GetLastError` at `0x1800107e1`
- `KERNEL32!GetLastError` at `0x180010888`
- `KERNEL32!GetLastError` at `0x1800107e1`
- `KERNEL32!GetLastError` at `0x180010888`
- `KERNEL32!GetProcessId` at `0x180010818`
- `KERNEL32!GetProcessId` at `0x180010818`
- `KERNEL32!CloseHandle` at `0x1800108eb`
- `KERNEL32!CloseHandle` at `0x1800108fe`
- `KERNEL32!CloseHandle` at `0x1800108eb`
- `KERNEL32!CloseHandle` at `0x1800108fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSilentProcessExitReport::LaunchMonitorProcess(CSilentProcessExitReport *this, int *a2)
{
  unsigned int v4; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // r8
  const wchar_t *v7; // r14
  wchar_t *v8; // rax
  size_t v9; // rbx
  int v10; // eax
  __int64 v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD LastError; // eax
  unsigned int v15; // eax
  DWORD v16; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-79h] BYREF
  LPWSTR lpCommandLine[5]; // [rsp+68h] [rbp-61h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-39h] BYREF
  DWORD ProcessId; // [rsp+138h] [rbp+6Fh] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpCommandLine);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  ProcessId = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_0b9f8713f655331c3edd713292668335_Traceguids);
    goto LABEL_37;
  }
  v5 = UtilPathTail(*(const unsigned __int16 **)((char *)this
                                               + (-(__int64)(*((_BYTE *)this + 216) != 0) & 0xFFFFFFFFFFFFFFA8uLL)
                                               + 312));
  v7 = v5;
  if ( !v5 )
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LOBYTE(v6) = -(char)v6;
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        v6,
        *(_QWORD *)((char *)this + (-(__int64)((_BYTE)v6 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 312));
    }
    goto LABEL_37;
  }
  v8 = wcschr(v5, 0x20u);
  if ( v8 )
  {
    v9 = v8 - v7;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( v7[v9] );
  }
  if ( _wcsnicmp(v7, *((const wchar_t **)this + 13), v9) && _wcsnicmp(v7, *((const wchar_t **)this + 12), v9) )
  {
    v10 = CSilentProcessExitReport::PrepareCmdLineForMonitorProcess(this, lpCommandLine);
    v4 = v10;
    if ( v10 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v13 = 20;
      goto LABEL_20;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v11, lpCommandLine[0]);
    if ( !CreateProcessW(0, lpCommandLine[0], 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      LastError = GetLastError();
      v10 = ERROR_HR_FROM_WIN32(LastError);
      v4 = v10;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v13 = 22;
LABEL_20:
      WPP_SF_d(v12[2], v13, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, (unsigned int)v10);
      goto LABEL_37;
    }
    ProcessId = GetProcessId(ProcessInformation.hProcess);
    CSilentProcessExitTestAutomation::WriteTestHookToRegistry(
      (CSilentProcessExitReport *)((char *)this + 872),
      L"MonitorProcessPID",
      (unsigned __int8 *)&ProcessId,
      4u,
      4u);
    v15 = UtilWaitForSingleObject(L"Monitor Process Exit", ProcessInformation.hProcess, 0xFFFFFFFF);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, v15);
      v16 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v16);
    }
    else
    {
      *a2 = 0;
      v4 = 0;
    }
  }
  else
  {
    *a2 = 1;
    v4 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), *((_QWORD *)this + 12), *((_QWORD *)this + 13));
  }
LABEL_37:
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = 0;
  }
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = 0;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpCommandLine);
  return v4;
}

```

## disassembly

```asm
0x1800105c8  mov     [rsp-8+arg_0], rbx
0x1800105cd  mov     [rsp-8+arg_10], rsi
0x1800105d2  push    rbp
0x1800105d3  push    rdi
0x1800105d4  push    r12
0x1800105d6  push    r14
0x1800105d8  push    r15
0x1800105da  lea     rbp, [rsp-37h]
0x1800105df  sub     rsp, 100h
0x1800105e6  mov     rsi, rcx
0x1800105e9  mov     r15, rdx
0x1800105ec  lea     rcx, [rbp+57h+lpCommandLine]; void *
0x1800105f0  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800105f5  xor     eax, eax
0x1800105f7  lea     rcx, [rbp+57h+StartupInfo]; void *
0x1800105fb  xorps   xmm0, xmm0
0x1800105fe  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180010602  xor     edx, edx; Val
0x180010604  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180010608  lea     r8d, [rax+68h]; Size
0x18001060c  call    memset_0
0x180010611  xor     r12d, r12d
0x180010614  mov     [rbp+57h+arg_8], r12d
0x180010618  test    r15, r15
0x18001061b  jnz     short loc_18001065D
0x18001061d  mov     ebx, 80070057h
0x180010622  mov     rcx, cs:WPP_GLOBAL_Control
0x180010629  lea     rdi, WPP_GLOBAL_Control
0x180010630  cmp     rcx, rdi
0x180010633  jz      loc_1800108E2
0x180010639  test    byte ptr [rcx+1Ch], 1
0x18001063d  jz      loc_1800108E2
0x180010643  mov     rcx, [rcx+10h]
0x180010647  lea     edx, [r12+11h]
0x18001064c  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x180010653  call    WPP_SF_
0x180010658  jmp     loc_1800108E2
0x18001065d  mov     r8b, [rsi+0D8h]
0x180010664  mov     al, r8b
0x180010667  neg     al
0x180010669  sbb     rcx, rcx
0x18001066c  and     rcx, 0FFFFFFFFFFFFFFA8h
0x180010670  mov     rcx, [rcx+rsi+138h]; unsigned __int16 *
0x180010678  call    ?UtilPathTail@@YAPEBGPEBG@Z; UtilPathTail(ushort const *)
0x18001067d  mov     r14, rax
0x180010680  test    rax, rax
0x180010683  jnz     short loc_1800106CE
0x180010685  mov     ebx, 80070057h
0x18001068a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010691  lea     rdi, WPP_GLOBAL_Control
0x180010698  cmp     rcx, rdi
0x18001069b  jz      loc_1800108E2
0x1800106a1  test    byte ptr [rcx+1Ch], 1
0x1800106a5  jz      loc_1800108E2
0x1800106ab  mov     rcx, [rcx+10h]
0x1800106af  lea     edx, [rax+12h]
0x1800106b2  neg     r8b
0x1800106b5  sbb     r9, r9
0x1800106b8  and     r9, 0FFFFFFFFFFFFFFA8h
0x1800106bc  mov     r9, [r9+rsi+138h]
0x1800106c4  call    WPP_SF_S
0x1800106c9  jmp     loc_1800108E2
0x1800106ce  mov     edx, 20h ; ' '; Ch
0x1800106d3  mov     rcx, r14; Str
0x1800106d6  call    cs:__imp_wcschr
0x1800106dc  mov     rbx, rax
0x1800106df  test    rax, rax
0x1800106e2  jnz     short loc_1800106F4
0x1800106e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800106e8  inc     rbx
0x1800106eb  cmp     [r14+rbx*2], r12w
0x1800106f0  jnz     short loc_1800106E8
0x1800106f2  jmp     short loc_1800106FA
0x1800106f4  sub     rbx, r14
0x1800106f7  sar     rbx, 1
0x1800106fa  mov     rdx, [rsi+68h]; String2
0x1800106fe  mov     r8, rbx; MaxCount
0x180010701  mov     rcx, r14; String1
0x180010704  call    cs:__imp__wcsnicmp
0x18001070a  test    eax, eax
0x18001070c  jz      loc_1800108A1
0x180010712  mov     rdx, [rsi+60h]; String2
0x180010716  mov     r8, rbx; MaxCount
0x180010719  mov     rcx, r14; String1
0x18001071c  call    cs:__imp__wcsnicmp
0x180010722  test    eax, eax
0x180010724  jz      loc_1800108A1
0x18001072a  lea     rdx, [rbp+57h+lpCommandLine]
0x18001072e  mov     rcx, rsi
0x180010731  call    ?PrepareCmdLineForMonitorProcess@CSilentProcessExitReport@@AEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CSilentProcessExitReport::PrepareCmdLineForMonitorProcess(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180010736  mov     ebx, eax
0x180010738  test    eax, eax
0x18001073a  jns     short loc_18001077A
0x18001073c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010743  lea     rdi, WPP_GLOBAL_Control
0x18001074a  cmp     rcx, rdi
0x18001074d  jz      loc_1800108E2
0x180010753  test    byte ptr [rcx+1Ch], 1
0x180010757  jz      loc_1800108E2
0x18001075d  mov     edx, 14h
0x180010762  mov     rcx, [rcx+10h]
0x180010766  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x18001076d  mov     r9d, eax
0x180010770  call    WPP_SF_d
0x180010775  jmp     loc_1800108E2
0x18001077a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010781  lea     rdi, WPP_GLOBAL_Control
0x180010788  cmp     rcx, rdi
0x18001078b  jz      short loc_1800107A5
0x18001078d  test    byte ptr [rcx+1Ch], 4
0x180010791  jz      short loc_1800107A5
0x180010793  mov     r9, [rbp+57h+lpCommandLine]
0x180010797  mov     edx, 15h
0x18001079c  mov     rcx, [rcx+10h]
0x1800107a0  call    WPP_SF_S
0x1800107a5  mov     rdx, [rbp+57h+lpCommandLine]; lpCommandLine
0x1800107a9  lea     rax, [rbp+57h+ProcessInformation]
0x1800107ad  mov     [rsp+120h+lpProcessInformation], rax; lpProcessInformation
0x1800107b2  xor     r9d, r9d; lpThreadAttributes
0x1800107b5  lea     rax, [rbp+57h+StartupInfo]
0x1800107b9  xor     r8d, r8d; lpProcessAttributes
0x1800107bc  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x1800107c1  xor     ecx, ecx; lpApplicationName
0x1800107c3  mov     [rsp+120h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1800107c8  mov     [rsp+120h+lpEnvironment], r12; lpEnvironment
0x1800107cd  mov     [rsp+120h+dwCreationFlags], r12d; dwCreationFlags
0x1800107d2  mov     [rsp+120h+bInheritHandles], r12d; bInheritHandles
0x1800107d7  call    cs:__imp_CreateProcessW
0x1800107dd  test    eax, eax
0x1800107df  jnz     short loc_180010814
0x1800107e1  call    cs:__imp_GetLastError
0x1800107e7  mov     ecx, eax; unsigned int
0x1800107e9  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800107ee  mov     ebx, eax
0x1800107f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107f7  cmp     rcx, rdi
0x1800107fa  jz      loc_1800108E2
0x180010800  test    byte ptr [rcx+1Ch], 1
0x180010804  jz      loc_1800108E2
0x18001080a  mov     edx, 16h
0x18001080f  jmp     loc_180010762
0x180010814  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; Process
0x180010818  call    cs:__imp_GetProcessId
0x18001081e  lea     rcx, [rsi+368h]; this
0x180010825  mov     [rsp+120h+bInheritHandles], 4; unsigned int
0x18001082d  mov     r9d, 4; unsigned int
0x180010833  mov     [rbp+57h+arg_8], eax
0x180010836  lea     r8, [rbp+57h+arg_8]; unsigned __int8 *
0x18001083a  lea     rdx, aMonitorprocess_0; "MonitorProcessPID"
0x180010841  call    ?WriteTestHookToRegistry@CSilentProcessExitTestAutomation@@QEAAXPEBGPEAEKK@Z; CSilentProcessExitTestAutomation::WriteTestHookToRegistry(ushort const *,uchar *,ulong,ulong)
0x180010846  mov     rdx, [rbp+57h+ProcessInformation.hProcess]; void *
0x18001084a  lea     rcx, aMonitorProcess; "Monitor Process Exit"
0x180010851  or      r8d, 0FFFFFFFFh; unsigned int
0x180010855  call    ?UtilWaitForSingleObject@@YAKPEBGPEAXK@Z; UtilWaitForSingleObject(ushort const *,void *,ulong)
0x18001085a  test    eax, eax
0x18001085c  jz      short loc_180010899
0x18001085e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010865  cmp     rcx, rdi
0x180010868  jz      short loc_180010888
0x18001086a  test    byte ptr [rcx+1Ch], 1
0x18001086e  jz      short loc_180010888
0x180010870  mov     rcx, [rcx+10h]
0x180010874  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x18001087b  mov     edx, 17h
0x180010880  mov     r9d, eax
0x180010883  call    WPP_SF_d
0x180010888  call    cs:__imp_GetLastError
0x18001088e  mov     ecx, eax; unsigned int
0x180010890  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180010895  mov     ebx, eax
0x180010897  jmp     short loc_1800108E2
0x180010899  mov     [r15], r12d
0x18001089c  mov     ebx, r12d
0x18001089f  jmp     short loc_1800108E2
0x1800108a1  mov     dword ptr [r15], 1
0x1800108a8  mov     ebx, r12d
0x1800108ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108b2  lea     rdi, WPP_GLOBAL_Control
0x1800108b9  cmp     rcx, rdi
0x1800108bc  jz      short loc_1800108E2
0x1800108be  test    byte ptr [rcx+1Ch], 4
0x1800108c2  jz      short loc_1800108E2
0x1800108c4  mov     rax, [rsi+68h]
0x1800108c8  mov     r9, r14
0x1800108cb  mov     rcx, [rcx+10h]; LoggerHandle
0x1800108cf  mov     qword ptr [rsp+120h+dwCreationFlags], rax; __int64
0x1800108d4  mov     rax, [rsi+60h]
0x1800108d8  mov     qword ptr [rsp+120h+bInheritHandles], rax; __int64
0x1800108dd  call    WPP_SF_SSS
0x1800108e2  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x1800108e6  test    rcx, rcx
0x1800108e9  jz      short loc_1800108F5
0x1800108eb  call    cs:__imp_CloseHandle
0x1800108f1  mov     [rbp+57h+ProcessInformation.hThread], r12
0x1800108f5  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x1800108f9  test    rcx, rcx
0x1800108fc  jz      short loc_180010908
0x1800108fe  call    cs:__imp_CloseHandle
0x180010904  mov     [rbp+57h+ProcessInformation.hProcess], r12
0x180010908  lea     rcx, [rbp+57h+lpCommandLine]
0x18001090c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180010911  lea     r11, [rsp+120h+var_20]
0x180010919  mov     eax, ebx
0x18001091b  mov     rbx, [r11+30h]
0x18001091f  mov     rsi, [r11+40h]
0x180010923  mov     rsp, r11
0x180010926  pop     r15
0x180010928  pop     r14
0x18001092a  pop     r12
0x18001092c  pop     rdi
0x18001092d  pop     rbp
0x18001092e  retn
```
