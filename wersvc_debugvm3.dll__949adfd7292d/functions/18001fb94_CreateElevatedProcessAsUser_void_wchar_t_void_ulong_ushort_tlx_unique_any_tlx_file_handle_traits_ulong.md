# CreateElevatedProcessAsUser(void *,wchar_t *,void * *,ulong,ushort,tlx::unique_any<tlx::file_handle_traits> *,ulong)

- ea: `0x18001fb94`
- end: `0x18002045f`
- name: `?CreateElevatedProcessAsUser@@YAJPEAXPEA_WPEAPEAXKGPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@K@Z`
- size: `2251`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020468`
- `0x180021b88`
- `0x180021fc0`
- `0x180023d0c`

## callees

- `0x1800029f4`
- `0x180002a24`
- `0x1800035e8`
- `0x180004a44`
- `0x180006a80`
- `0x18000facc`
- `0x180011ef8`
- `0x180013df4`
- `0x18001fb94`
- `0x18002060c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001ff98`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180020052`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001ff98`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180020052`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180020313`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180020313`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18002039d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18002039d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800200ce`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002016f`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800200ce`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18002016f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002005c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002031b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002005c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002031b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002024c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002024c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002033a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002033a`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18001fe10`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18001fe10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fcd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020382`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020424`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020443`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fcd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020382`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020424`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020443`
- `profapi!__imp_CreateEnvBlock` at `0x1800201de`
- `profapi!__imp_CreateEnvBlock` at `0x1800201de`
- `profapi!__imp_DestroyEnvBlock` at `0x1800203b0`
- `profapi!__imp_DestroyEnvBlock` at `0x1800203b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CreateElevatedProcessAsUser(
        void *a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        __int16 a5,
        void **a6,
        unsigned __int16 a7)
{
  const struct std::nothrow_t *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  struct _PROC_THREAD_ATTRIBUTE_LIST *v13; // r12
  char v14; // di
  signed int ProcessToken; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  void **v18; // rsi
  void *v19; // rcx
  __int64 v20; // r8
  const wchar_t *v21; // rax
  int v22; // eax
  __int16 v23; // r13
  int v24; // r13d
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  const wchar_t *v27; // r14
  DWORD v28; // r14d
  __int64 v29; // rbx
  signed int LastError; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v31; // rax
  signed int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  signed int v37; // eax
  __int64 v38; // r8
  __int64 v39; // r9
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  signed int v42; // eax
  __int64 v43; // rdx
  BOOL v44; // edi
  signed int v45; // eax
  _QWORD *hProcess; // rax
  LPVOID lpEnvironment; // [rsp+70h] [rbp-98h] BYREF
  __int64 v49; // [rsp+78h] [rbp-90h]
  ULONG_PTR Size; // [rsp+80h] [rbp-88h] BYREF
  struct _PROCESS_INFORMATION hObject; // [rsp+88h] [rbp-80h] BYREF
  LPCWSTR lpCurrentDirectory; // [rsp+A0h] [rbp-68h] BYREF
  const WCHAR *v53; // [rsp+A8h] [rbp-60h]
  _WORD v54[8]; // [rsp+B0h] [rbp-58h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+C0h] [rbp-48h] BYREF
  _WORD v56[8]; // [rsp+D0h] [rbp-38h] BYREF
  LPCWSTR lpApplicationName[2]; // [rsp+E0h] [rbp-28h] BYREF
  _WORD v58[8]; // [rsp+F0h] [rbp-18h] BYREF
  const wchar_t *v59; // [rsp+100h] [rbp-8h]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v60; // [rsp+108h] [rbp+0h]
  struct _STARTUPINFOW StartupInfo; // [rsp+118h] [rbp+10h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v62; // [rsp+180h] [rbp+78h]
  HANDLE Value; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v64; // [rsp+1E0h] [rbp+D8h]
  PVOID lpValue; // [rsp+1E8h] [rbp+E0h]
  unsigned int v66; // [rsp+1F0h] [rbp+E8h]

  v66 = a4;
  lpValue = a3;
  v64 = a2;
  Value = a1;
  lpEnvironment = 0;
  memset(&hObject, 0, sizeof(hObject));
  memset_0(&StartupInfo, 0, 0x70u);
  Size = 0;
  v13 = 0;
  v60 = 0;
  lpCurrentDirectory = v54;
  v53 = v54;
  v54[0] = 0;
  lpApplicationName[0] = v58;
  lpApplicationName[1] = v58;
  v58[0] = 0;
  lpCommandLine[0] = v56;
  lpCommandLine[1] = v56;
  v56[0] = 0;
  v14 = a7;
  LODWORD(v49) = a7 & 0x40;
  if ( (a7 & 0x40) != 0 )
  {
    if ( a4 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
    if ( (v14 & 0x20) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
    if ( (v14 & 4) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
    if ( (v14 & 8) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
  }
  if ( !a2 )
  {
    ProcessToken = -2147024809;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 18;
LABEL_14:
      WPP_SF_(v16[2], v17, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids);
      goto LABEL_127;
    }
    goto LABEL_127;
  }
  v18 = a6;
  if ( a6 )
  {
    v19 = *a6;
    *a6 = 0;
    if ( (unsigned __int64)v19 + 1 > 1 )
      CloseHandle(v19);
  }
  v20 = v14 & 1;
  v9 = (const struct std::nothrow_t *)L"WerFault.exe";
  v21 = L"WerMgr.exe";
  if ( (v14 & 2) == 0 )
    v21 = (const wchar_t *)((unsigned __int64)L"WerFault.exe" & -(__int64)((v14 & 1) != 0));
  v59 = v21;
  v22 = v20 + 1;
  if ( (v14 & 2) == 0 )
    v22 = v14 & 1;
  if ( v22 == 1 )
  {
    v23 = a5;
    if ( (v14 & 0x30) != 0 && a5 )
    {
      ProcessToken = -2147024809;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 20;
        goto LABEL_14;
      }
      goto LABEL_127;
    }
    ProcessToken = -2147467259;
    if ( Value )
    {
      ProcessToken = GetCreateProcessToken(Value);
      if ( ProcessToken < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
            (unsigned int)ProcessToken);
        goto LABEL_127;
      }
      if ( (v14 & 0x30) != 0 )
      {
        a7 = 0;
        if ( (unsigned int)IsWow64Process2(Value, &a7, 0) )
        {
          v9 = (const struct std::nothrow_t *)a7;
          if ( a7 == v23 )
          {
            LOBYTE(v20) = 1;
            ProcessToken = UtilGetSystemDirectory2(&lpCurrentDirectory, a7, v20);
            if ( ProcessToken < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  22,
                  WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
                  (unsigned int)ProcessToken);
              goto LABEL_127;
            }
          }
        }
      }
    }
    if ( lpCurrentDirectory == v53 )
    {
      LOBYTE(v20) = 1;
      ProcessToken = UtilGetSystemDirectory2(&lpCurrentDirectory, 0, v20);
    }
    v24 = 0;
    if ( ProcessToken < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_127;
      v26 = 23;
      goto LABEL_50;
    }
    v27 = v59;
    ProcessToken = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                     lpApplicationName,
                     L"%s\\%s",
                     lpCurrentDirectory,
                     v59);
    if ( ProcessToken < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_127;
      v26 = 24;
      goto LABEL_50;
    }
    ProcessToken = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                     lpCommandLine,
                     L"\"%s\\%s\" %s",
                     lpCurrentDirectory,
                     v27,
                     v64);
    if ( ProcessToken < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_127;
      v26 = 25;
      goto LABEL_50;
    }
    v28 = 1024;
    v29 = v66;
    if ( v66 - 1 <= 0xE )
    {
      if ( !InitializeProcThreadAttributeList(0, 2u, 0, &Size) && GetLastError() != 122 )
      {
        LastError = GetLastError();
        ProcessToken = LastError;
        if ( LastError > 0 )
          ProcessToken = (unsigned __int16)LastError | 0x80070000;
        if ( ProcessToken >= 0 )
          ProcessToken = -2147467259;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_127;
        v26 = 26;
        goto LABEL_50;
      }
      v31 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)operator new[](Size, (const struct std::nothrow_t *)&std::nothrow);
      v13 = v31;
      v60 = v31;
      if ( !v31 )
      {
        ProcessToken = -2147024882;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_127;
        v26 = 27;
        goto LABEL_50;
      }
      if ( !InitializeProcThreadAttributeList(v31, 2u, 0, &Size) )
      {
        v32 = GetLastError();
        ProcessToken = v32;
        if ( v32 > 0 )
          ProcessToken = (unsigned __int16)v32 | 0x80070000;
        if ( ProcessToken >= 0 )
          ProcessToken = -2147467259;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_127;
        v26 = 28;
LABEL_50:
        WPP_SF_d(v25[2], v26, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)ProcessToken);
        goto LABEL_127;
      }
      if ( !UpdateProcThreadAttribute(v13, 0, 0x20002u, lpValue, 8 * v29, 0, 0) )
      {
        v37 = GetLastError();
        ProcessToken = v37;
        if ( v37 > 0 )
          ProcessToken = (unsigned __int16)v37 | 0x80070000;
        if ( ProcessToken >= 0 )
          ProcessToken = -2147467259;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_124;
        v41 = 29;
LABEL_89:
        WPP_SF_d(v40[2], v41, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)ProcessToken);
LABEL_124:
        if ( !v13 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v40, v9, v38, v39);
        DeleteProcThreadAttributeList(v13);
        goto LABEL_127;
      }
      if ( v14 >= 0 )
      {
        if ( (_DWORD)v49 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v34, v33, v35, v36);
        if ( !UpdateProcThreadAttribute(v13, 0, 0x20000u, &Value, 8u, 0, 0) )
        {
          v42 = GetLastError();
          ProcessToken = v42;
          if ( v42 > 0 )
            ProcessToken = (unsigned __int16)v42 | 0x80070000;
          if ( ProcessToken >= 0 )
            ProcessToken = -2147467259;
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_124;
          v41 = 30;
          goto LABEL_89;
        }
      }
      v24 = 1;
      v62 = v13;
      v28 = 525312;
    }
    ProcessToken = CreateEnvBlock(&lpEnvironment, 0, 0);
    if ( ProcessToken >= 0 )
    {
      StartupInfo.cb = 112;
      StartupInfo.lpDesktop = (LPWSTR)&dword_180039414;
      StartupInfo.dwFlags |= 0x10000u;
      if ( hObject.hProcess )
        CloseHandle(hObject.hProcess);
      if ( hObject.hThread )
        CloseHandle(hObject.hThread);
      memset(&hObject, 0, sizeof(hObject));
      v44 = CreateProcessAsUserW(
              0,
              lpApplicationName[0],
              lpCommandLine[0],
              0,
              0,
              1,
              v28,
              lpEnvironment,
              lpCurrentDirectory,
              &StartupInfo,
              &hObject);
      v45 = GetLastError();
      ProcessToken = v45;
      if ( v45 > 0 )
        ProcessToken = (unsigned __int16)v45 | 0x80070000;
      if ( ProcessToken >= 0 )
        ProcessToken = -2147467259;
      RevertToSelf();
      if ( v44 )
      {
        if ( v18 )
        {
          hProcess = hObject.hProcess;
          hObject.hProcess = 0;
          v40 = *v18;
          *v18 = hProcess;
          if ( (unsigned __int64)v40 + 1 > 1 )
            CloseHandle(v40);
        }
        ProcessToken = 0;
      }
      else
      {
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v43 = 33;
          goto LABEL_106;
        }
      }
    }
    else
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v43 = 31;
LABEL_106:
        WPP_SF_d(v40[2], v43, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)ProcessToken);
      }
    }
    if ( !v24 )
      goto LABEL_127;
    goto LABEL_124;
  }
  ProcessToken = -2147024809;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = 19;
    goto LABEL_14;
  }
LABEL_127:
  if ( lpEnvironment )
  {
    DestroyEnvBlock();
    lpEnvironment = 0;
  }
  if ( lpCommandLine[0] != v56 )
    operator delete(lpCommandLine[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpApplicationName[0] != v58 )
    operator delete((void *)lpApplicationName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpCurrentDirectory != v54 )
    operator delete((void *)lpCurrentDirectory, (const struct std::nothrow_t *)&std::nothrow);
  if ( v13 )
    operator delete(v13, v9);
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  return (unsigned int)ProcessToken;
}

```

## disassembly

```asm
0x18001fb94  mov     rax, rsp
0x18001fb97  mov     [rax+20h], r9d
0x18001fb9b  mov     [rax+18h], r8
0x18001fb9f  mov     [rax+10h], rdx
0x18001fba3  mov     [rax+8], rcx
0x18001fba7  push    rbp
0x18001fba8  push    rbx
0x18001fba9  push    rsi
0x18001fbaa  push    rdi
0x18001fbab  push    r12
0x18001fbad  push    r13
0x18001fbaf  push    r14
0x18001fbb1  push    r15
0x18001fbb3  lea     rbp, [rax-0C8h]
0x18001fbba  sub     rsp, 188h
0x18001fbc1  mov     ebx, r9d
0x18001fbc4  mov     rsi, rdx
0x18001fbc7  xor     r14d, r14d
0x18001fbca  mov     [rsp+1C0h+var_158], r14
0x18001fbcf  xorps   xmm0, xmm0
0x18001fbd2  xor     eax, eax
0x18001fbd4  movups  xmmword ptr [rbp+0C0h+hObject], xmm0
0x18001fbd8  mov     [rbp+0C0h+var_130], rax
0x18001fbdc  mov     r15d, r14d
0x18001fbdf  mov     [rsp+1C0h+var_160], r14
0x18001fbe4  xor     edx, edx; Val
0x18001fbe6  lea     r8d, [r14+70h]; Size
0x18001fbea  lea     rcx, [rbp+0C0h+StartupInfo]; void *
0x18001fbee  call    memset_0
0x18001fbf3  mov     [rsp+1C0h+Size], r14
0x18001fbf8  mov     r12d, r14d
0x18001fbfb  mov     [rbp+0C0h+var_C0], r14
0x18001fbff  lea     rax, [rbp+0C0h+var_118]
0x18001fc03  mov     [rbp+0C0h+var_128], rax
0x18001fc07  lea     rax, [rbp+0C0h+var_118]
0x18001fc0b  mov     [rbp+0C0h+var_120], rax
0x18001fc0f  mov     [rbp+0C0h+var_118], r14w
0x18001fc14  lea     rax, [rbp+0C0h+var_D8]
0x18001fc18  mov     [rbp+0C0h+lpApplicationName], rax
0x18001fc1c  lea     rax, [rbp+0C0h+var_D8]
0x18001fc20  mov     [rbp+0C0h+var_E0], rax
0x18001fc24  mov     [rbp+0C0h+var_D8], r14w
0x18001fc29  lea     rax, [rbp+0C0h+var_F8]
0x18001fc2d  mov     [rbp+0C0h+lpCommandLine], rax
0x18001fc31  lea     rax, [rbp+0C0h+var_F8]
0x18001fc35  mov     [rbp+0C0h+var_100], rax
0x18001fc39  mov     [rbp+0C0h+var_F8], r14w
0x18001fc3e  mov     edi, [rbp+0C0h+arg_30]
0x18001fc44  mov     eax, edi
0x18001fc46  and     eax, 40h
0x18001fc49  mov     dword ptr [rsp+1C0h+var_150], eax
0x18001fc4d  jz      short loc_18001FC79
0x18001fc4f  test    ebx, ebx
0x18001fc51  jz      short loc_18001FC58
0x18001fc53  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001fc58  test    dil, 20h
0x18001fc5c  jz      short loc_18001FC63
0x18001fc5e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001fc63  test    dil, 4
0x18001fc67  jz      short loc_18001FC6E
0x18001fc69  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001fc6e  test    dil, 8
0x18001fc72  jz      short loc_18001FC79
0x18001fc74  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001fc79  test    rsi, rsi
0x18001fc7c  jnz     short loc_18001FCBC
0x18001fc7e  mov     ebx, 80070057h
0x18001fc83  lea     rax, WPP_GLOBAL_Control
0x18001fc8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc91  cmp     rcx, rax
0x18001fc94  jz      loc_1800203A3
0x18001fc9a  test    byte ptr [rcx+1Ch], 1
0x18001fc9e  jz      loc_1800203A3
0x18001fca4  lea     edx, [rsi+12h]
0x18001fca7  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18001fcae  mov     rcx, [rcx+10h]
0x18001fcb2  call    WPP_SF_
0x18001fcb7  jmp     loc_1800203A3
0x18001fcbc  mov     rsi, [rbp+0C0h+arg_28]
0x18001fcc3  test    rsi, rsi
0x18001fcc6  jz      short loc_18001FCDE
0x18001fcc8  mov     rcx, [rsi]; hObject
0x18001fccb  mov     [rsi], r14
0x18001fcce  lea     rax, [rcx+1]
0x18001fcd2  cmp     rax, 1
0x18001fcd6  jbe     short loc_18001FCDE
0x18001fcd8  call    cs:__imp_CloseHandle
0x18001fcde  mov     r8d, edi
0x18001fce1  and     r8d, 1
0x18001fce5  mov     eax, r8d
0x18001fce8  lea     rdx, aWerfaultExe_0; "WerFault.exe"
0x18001fcef  neg     eax
0x18001fcf1  sbb     rcx, rcx
0x18001fcf4  and     rcx, rdx
0x18001fcf7  bt      edi, 1
0x18001fcfb  lea     rax, aWermgrExe; "WerMgr.exe"
0x18001fd02  cmovnb  rax, rcx
0x18001fd06  mov     [rbp+0C0h+var_C8], rax
0x18001fd0a  lea     eax, [r8+1]
0x18001fd0e  cmovnb  eax, r8d
0x18001fd12  cmp     eax, 1
0x18001fd15  jz      short loc_18001FD47
0x18001fd17  mov     ebx, 80070057h
0x18001fd1c  lea     rax, WPP_GLOBAL_Control
0x18001fd23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd2a  cmp     rcx, rax
0x18001fd2d  jz      loc_1800203A3
0x18001fd33  test    byte ptr [rcx+1Ch], 1
0x18001fd37  jz      loc_1800203A3
0x18001fd3d  mov     edx, 13h
0x18001fd42  jmp     loc_18001FCA7
0x18001fd47  mov     r14d, edi
0x18001fd4a  movzx   r13d, [rbp+0C0h+arg_20]
0x18001fd52  and     r14d, 30h
0x18001fd56  jz      short loc_18001FD8E
0x18001fd58  test    r13w, r13w
0x18001fd5c  jz      short loc_18001FD8E
0x18001fd5e  mov     ebx, 80070057h
0x18001fd63  lea     rax, WPP_GLOBAL_Control
0x18001fd6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd71  cmp     rcx, rax
0x18001fd74  jz      loc_1800203A3
0x18001fd7a  test    byte ptr [rcx+1Ch], 1
0x18001fd7e  jz      loc_1800203A3
0x18001fd84  mov     edx, 14h
0x18001fd89  jmp     loc_18001FCA7
0x18001fd8e  mov     ebx, 80004005h
0x18001fd93  mov     rcx, [rbp+0C0h+Value]; ProcessHandle
0x18001fd9a  test    rcx, rcx
0x18001fd9d  jz      loc_18001FE74
0x18001fda3  lea     r8, [rsp+1C0h+var_160]
0x18001fda8  mov     edx, edi
0x18001fdaa  call    ?GetCreateProcessToken@@YAJPEAXKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; GetCreateProcessToken(void *,ulong,tlx::unique_any<tlx::file_handle_traits> *)
0x18001fdaf  mov     ebx, eax
0x18001fdb1  xor     r15d, r15d
0x18001fdb4  test    eax, eax
0x18001fdb6  jns     short loc_18001FDF2
0x18001fdb8  lea     rax, WPP_GLOBAL_Control
0x18001fdbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdc6  cmp     rcx, rax
0x18001fdc9  jz      short loc_18001FDE8
0x18001fdcb  test    byte ptr [rcx+1Ch], 1
0x18001fdcf  jz      short loc_18001FDE8
0x18001fdd1  lea     edx, [r15+15h]
0x18001fdd5  mov     r9d, ebx
0x18001fdd8  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18001fddf  mov     rcx, [rcx+10h]
0x18001fde3  call    WPP_SF_d
0x18001fde8  mov     r15, [rsp+1C0h+var_160]
0x18001fded  jmp     loc_1800203A3
0x18001fdf2  test    r14d, r14d
0x18001fdf5  jz      short loc_18001FE6F
0x18001fdf7  mov     word ptr [rbp+0C0h+arg_30], r15w
0x18001fdff  xor     r8d, r8d
0x18001fe02  lea     rdx, [rbp+0C0h+arg_30]
0x18001fe09  mov     rcx, [rbp+0C0h+Value]
0x18001fe10  call    cs:__imp_IsWow64Process2
0x18001fe16  test    eax, eax
0x18001fe18  jz      short loc_18001FE6F
0x18001fe1a  movzx   edx, word ptr [rbp+0C0h+arg_30]
0x18001fe21  cmp     dx, r13w
0x18001fe25  jnz     short loc_18001FE6F
0x18001fe27  mov     r8b, 1
0x18001fe2a  lea     rcx, [rbp+0C0h+var_128]
0x18001fe2e  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x18001fe33  mov     ebx, eax
0x18001fe35  test    eax, eax
0x18001fe37  jns     short loc_18001FE6F
0x18001fe39  lea     rax, WPP_GLOBAL_Control
0x18001fe40  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe47  cmp     rcx, rax
0x18001fe4a  jz      short loc_18001FDE8
0x18001fe4c  test    byte ptr [rcx+1Ch], 1
0x18001fe50  jz      short loc_18001FDE8
0x18001fe52  mov     edx, 16h
0x18001fe57  mov     r9d, ebx
0x18001fe5a  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18001fe61  mov     rcx, [rcx+10h]
0x18001fe65  call    WPP_SF_d
0x18001fe6a  jmp     loc_18001FDE8
0x18001fe6f  mov     r15, [rsp+1C0h+var_160]
0x18001fe74  mov     rax, [rbp+0C0h+var_120]
0x18001fe78  cmp     [rbp+0C0h+var_128], rax
0x18001fe7c  jnz     short loc_18001FE8E
0x18001fe7e  xor     edx, edx
0x18001fe80  mov     r8b, 1
0x18001fe83  lea     rcx, [rbp+0C0h+var_128]
0x18001fe87  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x18001fe8c  mov     ebx, eax
0x18001fe8e  xor     r13d, r13d
0x18001fe91  test    ebx, ebx
0x18001fe93  jns     short loc_18001FED2
0x18001fe95  lea     rax, WPP_GLOBAL_Control
0x18001fe9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fea3  cmp     rcx, rax
0x18001fea6  jz      loc_1800203A3
0x18001feac  test    byte ptr [rcx+1Ch], 1
0x18001feb0  jz      loc_1800203A3
0x18001feb6  lea     edx, [r13+17h]
0x18001feba  mov     r9d, ebx
0x18001febd  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18001fec4  mov     rcx, [rcx+10h]
0x18001fec8  call    WPP_SF_d
0x18001fecd  jmp     loc_1800203A3
0x18001fed2  mov     r14, [rbp+0C0h+var_C8]
0x18001fed6  mov     r9, r14
0x18001fed9  mov     r8, [rbp+0C0h+var_128]
0x18001fedd  lea     rdx, aSS; "%s\\%s"
0x18001fee4  lea     rcx, [rbp+0C0h+lpApplicationName]
0x18001fee8  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18001feed  mov     ebx, eax
0x18001feef  test    eax, eax
0x18001fef1  jns     short loc_18001FF1B
0x18001fef3  lea     rax, WPP_GLOBAL_Control
0x18001fefa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff01  cmp     rcx, rax
0x18001ff04  jz      loc_1800203A3
0x18001ff0a  test    byte ptr [rcx+1Ch], 1
0x18001ff0e  jz      loc_1800203A3
0x18001ff14  mov     edx, 18h
0x18001ff19  jmp     short loc_18001FEBA
0x18001ff1b  mov     rax, [rbp+0C0h+arg_8]
0x18001ff22  mov     [rsp+1C0h+cbSize], rax
0x18001ff27  mov     r9, r14
0x18001ff2a  mov     r8, [rbp+0C0h+var_128]
0x18001ff2e  lea     rdx, aSSS; "\"%s\\%s\" %s"
0x18001ff35  lea     rcx, [rbp+0C0h+lpCommandLine]
0x18001ff39  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18001ff3e  mov     ebx, eax
0x18001ff40  test    eax, eax
0x18001ff42  jns     short loc_18001FF6F
0x18001ff44  lea     rax, WPP_GLOBAL_Control
0x18001ff4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff52  cmp     rcx, rax
0x18001ff55  jz      loc_1800203A3
0x18001ff5b  test    byte ptr [rcx+1Ch], 1
0x18001ff5f  jz      loc_1800203A3
0x18001ff65  mov     edx, 19h
0x18001ff6a  jmp     loc_18001FEBA
0x18001ff6f  mov     r14d, 400h
0x18001ff75  mov     ebx, [rbp+0C0h+arg_18]
0x18001ff7b  lea     eax, [rbx-1]
0x18001ff7e  cmp     eax, 0Eh
0x18001ff81  ja      loc_1800201D3
0x18001ff87  lea     r9, [rsp+1C0h+Size]; lpSize
0x18001ff8c  xor     r8d, r8d; dwFlags
0x18001ff8f  lea     r14d, [r8+2]
0x18001ff93  mov     edx, r14d; dwAttributeCount
0x18001ff96  xor     ecx, ecx; lpAttributeList
0x18001ff98  call    cs:__imp_InitializeProcThreadAttributeList
0x18001ff9e  test    eax, eax
0x18001ffa0  jnz     short loc_18001FFF7
0x18001ffa2  call    cs:__imp_GetLastError
0x18001ffa8  cmp     eax, 7Ah ; 'z'
0x18001ffab  jz      short loc_18001FFF7
0x18001ffad  call    cs:__imp_GetLastError
0x18001ffb3  mov     ebx, eax
0x18001ffb5  test    eax, eax
0x18001ffb7  jle     short loc_18001FFC2
0x18001ffb9  movzx   ebx, ax
0x18001ffbc  or      ebx, 80070000h
0x18001ffc2  test    ebx, ebx
0x18001ffc4  mov     eax, 80004005h
0x18001ffc9  cmovns  ebx, eax
0x18001ffcc  lea     rax, WPP_GLOBAL_Control
0x18001ffd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffda  cmp     rcx, rax
0x18001ffdd  jz      loc_1800203A3
0x18001ffe3  test    byte ptr [rcx+1Ch], 1
0x18001ffe7  jz      loc_1800203A3
0x18001ffed  mov     edx, 1Ah
0x18001fff2  jmp     loc_18001FEBA
0x18001fff7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fffe  mov     rcx, [rsp+1C0h+Size]; unsigned __int64
0x180020003  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020008  mov     r12, rax
0x18002000b  mov     [rbp+0C0h+var_C0], rax
0x18002000f  test    rax, rax
0x180020012  jnz     short loc_180020044
0x180020014  mov     ebx, 8007000Eh
0x180020019  lea     rax, WPP_GLOBAL_Control
0x180020020  mov     rcx, cs:WPP_GLOBAL_Control
0x180020027  cmp     rcx, rax
0x18002002a  jz      loc_1800203A3
0x180020030  test    byte ptr [rcx+1Ch], 1
0x180020034  jz      loc_1800203A3
0x18002003a  lea     edx, [r12+1Bh]
0x18002003f  jmp     loc_18001FEBA
0x180020044  lea     r9, [rsp+1C0h+Size]; lpSize
0x180020049  xor     r8d, r8d; dwFlags
0x18002004c  mov     edx, r14d; dwAttributeCount
0x18002004f  mov     rcx, r12; lpAttributeList
0x180020052  call    cs:__imp_InitializeProcThreadAttributeList
0x180020058  test    eax, eax
0x18002005a  jnz     short loc_1800200A6
0x18002005c  call    cs:__imp_GetLastError
0x180020062  mov     ebx, eax
0x180020064  test    eax, eax
0x180020066  jle     short loc_180020071
0x180020068  movzx   ebx, ax
  ... truncated ...
```
