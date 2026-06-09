# WerpRestartApplication

- ea: `0x180039f30`
- end: `0x18003a7ea`
- name: `WerpRestartApplication`
- size: `2234`
- prototype: `__int64 __usercall@<rax>(HANDLE hProcess@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007df2c`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x18000ae48`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x18000e31c`
- `0x1800170b0`
- `0x1800195f0`
- `0x18001c368`
- `0x18001e0d0`
- `0x18001f3a0`
- `0x180020680`
- `0x18002219c`
- `0x18002d930`
- `0x180039f30`
- `0x18003b180`
- `0x18004bcc0`
- `0x18004c158`
- `0x180053d3c`
- `0x1800647ac`
- `0x180064828`
- `0x180064950`
- `0x180068558`
- `0x1800a8c2c`
- `0x1800a9464`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a0e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a0e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a072`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a072`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18003a65b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18003a65b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003a296`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003a357`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003a296`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003a357`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003a26a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003a32e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003a26a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18003a32e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a1b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a1b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a594`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a66d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a6b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a594`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a66d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a6b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a04f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a04f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a701`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a0f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a319`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a0f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a319`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18003a03b`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18003a0c1`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18003a03b`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18003a0c1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003a69f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003a69f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a507`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a507`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a5ac`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a67f`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a6c2`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a5ac`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a67f`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a6c2`
- `USERENV!DestroyEnvironmentBlock` at `0x18003a491`
- `USERENV!DestroyEnvironmentBlock` at `0x18003a491`
- `USERENV!CreateEnvironmentBlock` at `0x18003a4a8`
- `USERENV!CreateEnvironmentBlock` at `0x18003a4a8`

## pseudocode

```c
__int64 __fastcall WerpRestartApplication(HANDLE hProcess, void *a2, const size_t *a3, _DWORD *a4, _DWORD *a5)
{
  void *v7; // rdi
  unsigned int v8; // ebx
  const size_t *v9; // r13
  LPVOID v10; // rax
  void *v11; // rbx
  int RestartCommandLine; // eax
  unsigned int v13; // r12d
  __int64 unique_for; // rax
  const size_t *v15; // rbx
  void **v16; // rax
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  __int64 v19; // rdx
  DWORD LastError; // eax
  int v21; // eax
  DWORD ProcessId; // eax
  int Policy_Internal; // eax
  wchar_t *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  unsigned int v27; // r12d
  DWORD v28; // eax
  const size_t *v29; // r9
  int PackagedCWALauncherCommandLine; // eax
  const wchar_t *v31; // rbx
  WCHAR *v32; // r8
  WCHAR v33; // r9
  void *v34; // r9
  void *v35; // rcx
  HANDLE v36; // rbx
  wchar_t *v37; // rcx
  UINT v38; // ebx
  DWORD v39; // eax
  int v40; // eax
  unsigned int v42; // [rsp+60h] [rbp-A0h] BYREF
  DWORD nLengthNeeded; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD OldMode; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hToken; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpEnvironment; // [rsp+78h] [rbp-88h] BYREF
  void *v47; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+88h] [rbp-78h] BYREF
  const size_t *v49; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpCurrentDirectory[4]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v52; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v53; // [rsp+D0h] [rbp-30h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+D8h] [rbp-28h] BYREF
  LPWSTR lpCommandLine[4]; // [rsp+F0h] [rbp-10h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+110h] [rbp+10h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v49 = 0;
  v42 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpCommandLine);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpCurrentDirectory);
  hToken = 0;
  lpEnvironment = 0;
  OldMode = 0;
  v7 = 0;
  v47 = 0;
  v53 = 0;
  nLengthNeeded = 0;
  v52 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !(unsigned int)UtilCheckProcessExecutionTimeForRestart(hProcess) )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
    v8 = -2147467259;
    goto LABEL_107;
  }
  v9 = 0;
  if ( !GetKernelObjectSecurity(hProcess, 4u, 0, 0, &nLengthNeeded) && GetLastError() == 122 )
  {
    v10 = HeapAlloc(g_hWerheap, 0, nLengthNeeded);
    v47 = 0;
    v11 = v10;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v47);
    v48 = 0;
    v7 = v11;
    v47 = v11;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v48);
    if ( v11 )
    {
      if ( !GetKernelObjectSecurity(hProcess, 4u, v11, nLengthNeeded, &nLengthNeeded) )
      {
        v47 = 0;
        v7 = 0;
        HeapFree(g_hWerheap, 0, v11);
      }
    }
  }
  StartupInfo.cb = 104;
  if ( WaitForSingleObject(hProcess, 0) )
  {
    RestartCommandLine = WerpGetRestartCommandLine(hProcess, 0, &v42, 0);
    if ( (!RestartCommandLine || RestartCommandLine == -2147024774) && (v13 = v42) != 0 )
    {
      unique_for = utl::make_unique_for_overwrite<wchar_t [0],0>(&v48, v42);
      utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&v49, unique_for);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v48);
      v15 = v49;
      if ( v49 )
      {
        *(_WORD *)v49 = 0;
        v21 = WerpGetRestartCommandLine(hProcess, v15, &v42, 0);
        if ( v21 >= 0 )
        {
          v9 = v15;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              146,
              WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids,
              (unsigned int)v21);
          *(_WORD *)v15 = 0;
        }
      }
      else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, 2 * v13);
      }
    }
    else if ( RestartCommandLine == 1 )
    {
      ProcessId = GetProcessId(hProcess);
      WerpAddTerminationReason(ProcessId, 3, L"WerRec");
      TerminateProcess(hProcess, 0xFFu);
      v8 = 0;
      goto LABEL_107;
    }
  }
  v16 = (void **)tlx::replace<tlx::file_handle_traits>(&hToken);
  if ( !OpenProcessToken(hProcess, 0xBu, v16) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_28;
    v19 = 147;
LABEL_27:
    WPP_SF_(*((_QWORD *)v18 + 2), v19, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
LABEL_28:
    LastError = GetLastError();
    v8 = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_107;
  }
  v42 = 0;
  v48 = 0;
  v51 = 0;
  Policy_Internal = AppModelPolicy_GetPolicy_Internal(hToken, v17, &v42, &v51, &v48);
  v8 = Policy_Internal | 0x10000000;
  if ( Policy_Internal < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_107;
    v25 = 148;
    v26 = v8;
LABEL_41:
    WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, v26);
    goto LABEL_107;
  }
  v27 = v42;
  if ( WaitForSingleObject(hProcess, 0) )
  {
    v28 = GetProcessId(hProcess);
    WerpAddTerminationReason(v28, 3, L"WerRec");
    TerminateProcess(hProcess, 0xFFu);
  }
  if ( !v9 || !*(_WORD *)v9 )
    v9 = a3;
  if ( v27 == 786432 )
  {
    v29 = &Src;
    if ( v9 )
      v29 = v9;
    PackagedCWALauncherCommandLine = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                                       lpCommandLine,
                                       L"\"%s\" %s",
                                       a2,
                                       v29);
    v8 = PackagedCWALauncherCommandLine;
    if ( PackagedCWALauncherCommandLine < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_107;
      v25 = 149;
LABEL_54:
      v26 = (unsigned int)PackagedCWALauncherCommandLine;
      goto LABEL_41;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             lpCurrentDirectory,
                             a2) )
    {
      v8 = -2147024882;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
      goto LABEL_107;
    }
    v31 = UtilPathTail(lpCurrentDirectory[0]);
    if ( !v31 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
        v32 = (WCHAR *)lpCurrentDirectory[0];
        v33 = 0;
      }
      lpCurrentDirectory[1] = v32;
      *v32 = v33;
      v32 = (WCHAR *)lpCurrentDirectory[0];
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(lpCurrentDirectory, v31 - v32);
LABEL_65:
    v35 = lpEnvironment;
    v36 = hToken;
    lpEnvironment = v34;
    if ( v35 )
      DestroyEnvironmentBlock(v35);
    if ( !CreateEnvironmentBlock(&lpEnvironment, v36, 0) )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_75;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_72:
        if ( v37 != (wchar_t *)&WPP_GLOBAL_Control && (v37[14] & 4) != 0 )
          WPP_SF_S(*((_QWORD *)v37 + 2), 155, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, lpCommandLine[0]);
LABEL_75:
        if ( !ImpersonateLoggedOnUser(hToken) )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_28;
          v19 = 156;
          goto LABEL_27;
        }
        v38 = SetErrorMode(1u);
        SetThreadErrorMode(1u, &OldMode);
        if ( a5 )
          *a5 = UtilWaitForSingleObject(L"Process", hProcess, 0xBB8u) == 0;
        if ( v7 )
        {
          LODWORD(v53) = 0;
          *((_QWORD *)&v52 + 1) = v7;
          LODWORD(v52) = 24;
        }
        wer::ProcessInformation::Clear((wer::ProcessInformation *)&ProcessInformation);
        if ( CreateProcessAsUserW(
               hToken,
               0,
               lpCommandLine[0],
               (LPSECURITY_ATTRIBUTES)((unsigned __int64)&v52 & -(__int64)(v7 != 0)),
               0,
               0,
               0x400u,
               lpEnvironment,
               lpCurrentDirectory[0],
               &StartupInfo,
               &ProcessInformation) )
        {
          SetErrorMode(v38);
          SetThreadErrorMode(OldMode, 0);
        }
        else
        {
          SetErrorMode(v38);
          SetThreadErrorMode(OldMode, 0);
          if ( v27 != 786433 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, a2);
            v39 = GetLastError();
            v8 = ERROR_HR_FROM_WIN32(v39);
            goto LABEL_93;
          }
          v40 = WerpLaunchPackagedCWA(hProcess, v9);
          v8 = v40;
          if ( v40 < 0 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                158,
                WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids,
                (unsigned int)v40);
            goto LABEL_93;
          }
        }
        if ( a4 )
          *a4 = 1;
        v8 = 0;
LABEL_93:
        RevertToSelf();
        goto LABEL_107;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
    }
    v37 = WPP_GLOBAL_Control;
    goto LABEL_72;
  }
  if ( v27 == 786433 )
  {
    PackagedCWALauncherCommandLine = WerpGeneratePackagedCWALauncherCommandLine(hProcess, a2, v9, lpCommandLine);
    v34 = 0;
    v8 = PackagedCWALauncherCommandLine;
    if ( PackagedCWALauncherCommandLine < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_107;
      v25 = 152;
      goto LABEL_54;
    }
    goto LABEL_65;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, v27);
  v8 = -2147418113;
LABEL_107:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v47);
  tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&int DestroyEnvironmentBlock(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&int DestroyEnvironmentBlock(void *),0>>(&lpEnvironment);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hToken);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpCurrentDirectory);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpCommandLine);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v49);
  wer::ProcessInformation::Clear((wer::ProcessInformation *)&ProcessInformation);
  return v8;
}

```

## disassembly

```asm
0x180039f30  mov     rax, rsp
0x180039f33  mov     [rax+8], rbx
0x180039f37  mov     [rax+20h], r9
0x180039f3b  mov     [rax+18h], r8
0x180039f3f  mov     [rax+10h], rdx
0x180039f43  push    rbp
0x180039f44  push    rsi
0x180039f45  push    rdi
0x180039f46  push    r12
0x180039f48  push    r13
0x180039f4a  push    r14
0x180039f4c  push    r15
0x180039f4e  lea     rbp, [rsp-80h]
0x180039f53  sub     rsp, 180h
0x180039f5a  mov     r15, rcx
0x180039f5d  mov     esi, 68h ; 'h'
0x180039f62  mov     r8d, esi; Size
0x180039f65  lea     rcx, [rbp+0B0h+StartupInfo]; void *
0x180039f69  xor     edx, edx; Val
0x180039f6b  mov     rbx, r9
0x180039f6e  call    memset_0
0x180039f73  xorps   xmm0, xmm0
0x180039f76  lea     rcx, [rbp+0B0h+lpCommandLine]; void *
0x180039f7a  xor     eax, eax
0x180039f7c  xor     r12d, r12d
0x180039f7f  movups  xmmword ptr [rbp+0B0h+ProcessInformation.hProcess], xmm0
0x180039f83  mov     qword ptr [rbp+0B0h+ProcessInformation.dwProcessId], rax
0x180039f87  mov     [rbp+0B0h+var_120], r12
0x180039f8b  mov     [rsp+1B0h+var_150], r12d
0x180039f90  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180039f95  lea     rcx, [rbp+0B0h+var_118]; void *
0x180039f99  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180039f9e  xor     eax, eax
0x180039fa0  mov     [rsp+1B0h+hToken], r12
0x180039fa5  mov     [rsp+1B0h+lpEnvironment], r12
0x180039faa  xorps   xmm0, xmm0
0x180039fad  mov     [rsp+1B0h+OldMode], r12d
0x180039fb2  mov     edi, r12d
0x180039fb5  mov     [rbp+0B0h+var_130], r12
0x180039fb9  mov     [rbp+0B0h+var_E0], rax
0x180039fbd  mov     [rsp+1B0h+nLengthNeeded], r12d
0x180039fc2  movups  [rbp+0B0h+var_F0], xmm0
0x180039fc6  test    rbx, rbx
0x180039fc9  jz      short loc_180039FCE
0x180039fcb  mov     [rbx], r12d
0x180039fce  mov     rax, [rbp+0B0h+arg_20]
0x180039fd5  test    rax, rax
0x180039fd8  jz      short loc_180039FDD
0x180039fda  mov     [rax], r12d
0x180039fdd  mov     rcx, r15; hProcess
0x180039fe0  call    ?UtilCheckProcessExecutionTimeForRestart@@YAHPEAX@Z; UtilCheckProcessExecutionTimeForRestart(void *)
0x180039fe5  test    eax, eax
0x180039fe7  jnz     short loc_18003A021
0x180039fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ff0  lea     rsi, WPP_GLOBAL_Control
0x180039ff7  cmp     rcx, rsi
0x180039ffa  jz      short loc_18003A017
0x180039ffc  test    byte ptr [rcx+1Ch], 4
0x18003a000  jz      short loc_18003A017
0x18003a002  mov     rcx, [rcx+10h]
0x18003a006  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18003a00d  mov     edx, 90h
0x18003a012  call    WPP_SF_
0x18003a017  mov     ebx, 80004005h
0x18003a01c  jmp     loc_18003A78B
0x18003a021  xor     r9d, r9d; nLength
0x18003a024  lea     rax, [rsp+1B0h+nLengthNeeded]
0x18003a029  xor     r8d, r8d; pSecurityDescriptor
0x18003a02c  mov     [rsp+1B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18003a031  mov     rcx, r15; Handle
0x18003a034  mov     r13, r12
0x18003a037  lea     edx, [r9+4]; RequestedInformation
0x18003a03b  call    cs:__imp_GetKernelObjectSecurity
0x18003a042  nop     dword ptr [rax+rax+00h]
0x18003a047  test    eax, eax
0x18003a049  jnz     loc_18003A0F0
0x18003a04f  call    cs:__imp_GetLastError
0x18003a056  nop     dword ptr [rax+rax+00h]
0x18003a05b  cmp     eax, 7Ah ; 'z'
0x18003a05e  jnz     loc_18003A0F0
0x18003a064  mov     r8d, [rsp+1B0h+nLengthNeeded]; dwBytes
0x18003a069  xor     edx, edx; dwFlags
0x18003a06b  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18003a072  call    cs:__imp_HeapAlloc
0x18003a079  nop     dword ptr [rax+rax+00h]
0x18003a07e  lea     rcx, [rbp+0B0h+var_130]; void *
0x18003a082  mov     [rbp+0B0h+var_130], r12
0x18003a086  mov     rbx, rax
0x18003a089  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18003a08e  lea     rcx, [rbp+0B0h+var_128]; void *
0x18003a092  mov     [rbp+0B0h+var_128], r12
0x18003a096  mov     rdi, rbx
0x18003a099  mov     [rbp+0B0h+var_130], rbx
0x18003a09d  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18003a0a2  test    rbx, rbx
0x18003a0a5  jz      short loc_18003A0F0
0x18003a0a7  mov     r9d, [rsp+1B0h+nLengthNeeded]; nLength
0x18003a0ac  lea     rax, [rsp+1B0h+nLengthNeeded]
0x18003a0b1  mov     r8, rbx; pSecurityDescriptor
0x18003a0b4  mov     [rsp+1B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18003a0b9  mov     edx, 4; RequestedInformation
0x18003a0be  mov     rcx, r15; Handle
0x18003a0c1  call    cs:__imp_GetKernelObjectSecurity
0x18003a0c8  nop     dword ptr [rax+rax+00h]
0x18003a0cd  test    eax, eax
0x18003a0cf  jnz     short loc_18003A0F0
0x18003a0d1  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18003a0d8  mov     r8, rbx; lpMem
0x18003a0db  xor     edx, edx; dwFlags
0x18003a0dd  mov     [rbp+0B0h+var_130], r12
0x18003a0e1  mov     rdi, r12
0x18003a0e4  call    cs:__imp_HeapFree
0x18003a0eb  nop     dword ptr [rax+rax+00h]
0x18003a0f0  xor     edx, edx; dwMilliseconds
0x18003a0f2  mov     [rbp+0B0h+StartupInfo.cb], esi
0x18003a0f5  mov     rcx, r15; hHandle
0x18003a0f8  call    cs:__imp_WaitForSingleObject
0x18003a0ff  nop     dword ptr [rax+rax+00h]
0x18003a104  lea     rsi, WPP_GLOBAL_Control
0x18003a10b  lea     r14, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18003a112  test    eax, eax
0x18003a114  jz      loc_18003A19E
0x18003a11a  xor     r9d, r9d
0x18003a11d  lea     r8, [rsp+1B0h+var_150]
0x18003a122  xor     edx, edx
0x18003a124  mov     rcx, r15
0x18003a127  call    WerpGetRestartCommandLine
0x18003a12c  test    eax, eax
0x18003a12e  jz      short loc_18003A13B
0x18003a130  cmp     eax, 8007007Ah
0x18003a135  jnz     loc_18003A25E
0x18003a13b  mov     r12d, [rsp+1B0h+var_150]
0x18003a140  test    r12d, r12d
0x18003a143  jz      loc_18003A25B
0x18003a149  mov     edx, r12d
0x18003a14c  lea     rcx, [rbp+0B0h+var_128]
0x18003a150  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18003a155  mov     rdx, rax
0x18003a158  lea     rcx, [rbp+0B0h+var_120]
0x18003a15c  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x18003a161  lea     rcx, [rbp+0B0h+var_128]; void *
0x18003a165  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18003a16a  mov     rbx, [rbp+0B0h+var_120]
0x18003a16e  test    rbx, rbx
0x18003a171  jnz     loc_18003A206
0x18003a177  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a17e  cmp     rcx, rsi
0x18003a181  jz      short loc_18003A19E
0x18003a183  test    byte ptr [rcx+1Ch], 1
0x18003a187  jz      short loc_18003A19E
0x18003a189  mov     rcx, [rcx+10h]
0x18003a18d  lea     r9d, [r12+r12]
0x18003a191  mov     edx, 91h
0x18003a196  mov     r8, r14
0x18003a199  call    WPP_SF_d
0x18003a19e  lea     rcx, [rsp+1B0h+hToken]
0x18003a1a3  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18003a1a8  mov     r8, rax; TokenHandle
0x18003a1ab  mov     edx, 0Bh; DesiredAccess
0x18003a1b0  mov     rcx, r15; ProcessHandle
0x18003a1b3  call    cs:__imp_OpenProcessToken
0x18003a1ba  nop     dword ptr [rax+rax+00h]
0x18003a1bf  xor     ecx, ecx
0x18003a1c1  test    eax, eax
0x18003a1c3  jnz     loc_18003A2AA
0x18003a1c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1d0  cmp     rcx, rsi
0x18003a1d3  jz      short loc_18003A1EC
0x18003a1d5  test    byte ptr [rcx+1Ch], 1
0x18003a1d9  jz      short loc_18003A1EC
0x18003a1db  mov     edx, 93h
0x18003a1e0  mov     rcx, [rcx+10h]
0x18003a1e4  mov     r8, r14
0x18003a1e7  call    WPP_SF_
0x18003a1ec  call    cs:__imp_GetLastError
0x18003a1f3  nop     dword ptr [rax+rax+00h]
0x18003a1f8  mov     ecx, eax; unsigned int
0x18003a1fa  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18003a1ff  mov     ebx, eax
0x18003a201  jmp     loc_18003A78B
0x18003a206  xor     r12d, r12d
0x18003a209  lea     r8, [rsp+1B0h+var_150]
0x18003a20e  xor     r9d, r9d
0x18003a211  mov     [rbx], r12w
0x18003a215  mov     rdx, rbx
0x18003a218  mov     rcx, r15
0x18003a21b  call    WerpGetRestartCommandLine
0x18003a220  test    eax, eax
0x18003a222  jns     short loc_18003A253
0x18003a224  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a22b  cmp     rcx, rsi
0x18003a22e  jz      short loc_18003A24A
0x18003a230  test    byte ptr [rcx+1Ch], 1
0x18003a234  jz      short loc_18003A24A
0x18003a236  mov     rcx, [rcx+10h]
0x18003a23a  mov     edx, 92h
0x18003a23f  mov     r9d, eax
0x18003a242  mov     r8, r14
0x18003a245  call    WPP_SF_d
0x18003a24a  mov     [rbx], r12w
0x18003a24e  jmp     loc_18003A19E
0x18003a253  mov     r13, rbx
0x18003a256  jmp     loc_18003A19E
0x18003a25b  xor     r12d, r12d
0x18003a25e  cmp     eax, 1
0x18003a261  jnz     loc_18003A19E
0x18003a267  mov     rcx, r15; Process
0x18003a26a  call    cs:__imp_GetProcessId
0x18003a271  nop     dword ptr [rax+rax+00h]
0x18003a276  mov     r9d, 1
0x18003a27c  lea     r8, aWerrec; "WerRec"
0x18003a283  mov     ecx, eax
0x18003a285  lea     edx, [r9+2]
0x18003a289  call    WerpAddTerminationReason
0x18003a28e  mov     edx, 0FFh; uExitCode
0x18003a293  mov     rcx, r15; hProcess
0x18003a296  call    cs:__imp_TerminateProcess
0x18003a29d  nop     dword ptr [rax+rax+00h]
0x18003a2a2  mov     ebx, r12d
0x18003a2a5  jmp     loc_18003A78B
0x18003a2aa  mov     [rsp+1B0h+var_150], ecx
0x18003a2ae  lea     rax, [rbp+0B0h+var_128]
0x18003a2b2  mov     [rbp+0B0h+var_128], rcx
0x18003a2b6  lea     r9, [rbp+0B0h+var_F8]
0x18003a2ba  mov     [rbp+0B0h+var_F8], rcx
0x18003a2be  lea     r8, [rsp+1B0h+var_150]
0x18003a2c3  mov     rcx, [rsp+1B0h+hToken]
0x18003a2c8  mov     [rsp+1B0h+lpnLengthNeeded], rax
0x18003a2cd  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x18003a2d2  mov     ebx, eax
0x18003a2d4  or      ebx, 10000000h
0x18003a2da  jge     short loc_18003A30F
0x18003a2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a2e3  cmp     rcx, rsi
0x18003a2e6  jz      loc_18003A78B
0x18003a2ec  test    byte ptr [rcx+1Ch], 1
0x18003a2f0  jz      loc_18003A78B
0x18003a2f6  mov     edx, 94h
0x18003a2fb  mov     r9d, ebx
0x18003a2fe  mov     rcx, [rcx+10h]
0x18003a302  mov     r8, r14
0x18003a305  call    WPP_SF_d
0x18003a30a  jmp     loc_18003A78B
0x18003a30f  mov     r12d, [rsp+1B0h+var_150]
0x18003a314  xor     edx, edx; dwMilliseconds
0x18003a316  mov     rcx, r15; hHandle
0x18003a319  call    cs:__imp_WaitForSingleObject
0x18003a320  nop     dword ptr [rax+rax+00h]
0x18003a325  xor     ebx, ebx
0x18003a327  test    eax, eax
0x18003a329  jz      short loc_18003A363
0x18003a32b  mov     rcx, r15; Process
0x18003a32e  call    cs:__imp_GetProcessId
0x18003a335  nop     dword ptr [rax+rax+00h]
0x18003a33a  mov     ecx, eax
0x18003a33c  lea     r9d, [rbx+1]
0x18003a340  lea     r8, aWerrec; "WerRec"
0x18003a347  lea     edx, [rbx+3]
0x18003a34a  call    WerpAddTerminationReason
0x18003a34f  mov     edx, 0FFh; uExitCode
0x18003a354  mov     rcx, r15; hProcess
0x18003a357  call    cs:__imp_TerminateProcess
0x18003a35e  nop     dword ptr [rax+rax+00h]
0x18003a363  test    r13, r13
0x18003a366  jz      short loc_18003A36F
0x18003a368  cmp     [r13+0], bx
0x18003a36d  jnz     short loc_18003A376
0x18003a36f  mov     r13, [rbp+0B0h+arg_10]
0x18003a376  cmp     r12d, 0C0000h
0x18003a37d  jnz     loc_18003A53B
0x18003a383  mov     r8, [rbp+0B0h+arg_8]
0x18003a38a  lea     r9, Src
0x18003a391  test    r13, r13
0x18003a394  lea     rdx, aSS_2; "\"%s\" %s"
0x18003a39b  lea     rcx, [rbp+0B0h+lpCommandLine]
0x18003a39f  cmovnz  r9, r13
0x18003a3a3  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003a3a8  mov     ebx, eax
0x18003a3aa  test    eax, eax
0x18003a3ac  jns     short loc_18003A3D5
0x18003a3ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3b5  cmp     rcx, rsi
0x18003a3b8  jz      loc_18003A78B
0x18003a3be  test    byte ptr [rcx+1Ch], 1
0x18003a3c2  jz      loc_18003A78B
0x18003a3c8  mov     edx, 95h
0x18003a3cd  mov     r9d, eax
0x18003a3d0  jmp     loc_18003A2FE
0x18003a3d5  mov     rdx, [rbp+0B0h+arg_8]
0x18003a3dc  lea     rcx, [rbp+0B0h+var_118]
0x18003a3e0  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18003a3e5  xor     r9d, r9d
0x18003a3e8  test    al, al
0x18003a3ea  jnz     short loc_18003A421
0x18003a3ec  mov     ebx, 8007000Eh
0x18003a3f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3f8  cmp     rcx, rsi
0x18003a3fb  jz      loc_18003A78B
0x18003a401  test    byte ptr [rcx+1Ch], 1
0x18003a405  jz      loc_18003A78B
  ... truncated ...
```
