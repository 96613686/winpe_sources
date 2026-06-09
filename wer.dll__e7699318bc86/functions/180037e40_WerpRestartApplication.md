# WerpRestartApplication

- ea: `0x180037e40`
- end: `0x18003865f`
- name: `WerpRestartApplication`
- size: `2079`
- prototype: `__int64 __fastcall(HANDLE hProcess, __int64, const size_t *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007a8ac`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007e10`
- `0x180009bb4`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x180013730`
- `0x180015c40`
- `0x18001c5ec`
- `0x18001c650`
- `0x18001fe24`
- `0x180021634`
- `0x18002bed4`
- `0x180037e40`
- `0x180038f78`
- `0x180049a90`
- `0x180049f04`
- `0x1800517cc`
- `0x180061e84`
- `0x180061efc`
- `0x18006201c`
- `0x180065510`
- `0x1800a3f64`
- `0x1800a473c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037fd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037fd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037f72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037f72`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800384fb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800384fb`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003816c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003821b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003816c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003821b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180038146`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800381f8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180038146`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800381f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003809b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003809b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180038440`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180038507`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180038538`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180038440`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180038507`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180038538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800380ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003857d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800380ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003857d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037fe6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800381e9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037fe6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800381e9`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180037f4b`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180037fbb`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180037f4b`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180037fbb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003852d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003852d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800383b9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800383b9`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180038452`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180038513`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180038544`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180038452`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180038513`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x180038544`
- `USERENV!DestroyEnvironmentBlock` at `0x18003834f`
- `USERENV!DestroyEnvironmentBlock` at `0x18003834f`
- `USERENV!CreateEnvironmentBlock` at `0x180038360`
- `USERENV!CreateEnvironmentBlock` at `0x180038360`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WerpRestartApplication(HANDLE hProcess, __int64 a2, const size_t *a3, _DWORD *a4, _DWORD *a5)
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
  WCHAR *v31; // r8
  WCHAR v32; // r9
  void *v33; // r9
  void *v34; // rcx
  HANDLE v35; // rbx
  wchar_t *v36; // rcx
  UINT v37; // ebx
  DWORD v38; // eax
  int v39; // eax
  unsigned int v41; // [rsp+60h] [rbp-A0h] BYREF
  DWORD nLengthNeeded; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD OldMode; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hToken; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpEnvironment; // [rsp+78h] [rbp-88h] BYREF
  void *v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  const size_t *v48; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpCurrentDirectory[4]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v51; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v52; // [rsp+D0h] [rbp-30h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+D8h] [rbp-28h] BYREF
  LPWSTR lpCommandLine[4]; // [rsp+F0h] [rbp-10h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+110h] [rbp+10h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v48 = 0;
  v41 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpCommandLine);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpCurrentDirectory);
  hToken = 0;
  lpEnvironment = 0;
  OldMode = 0;
  v7 = 0;
  v46 = 0;
  v52 = 0;
  nLengthNeeded = 0;
  v51 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !(unsigned int)UtilCheckProcessExecutionTimeForRestart(hProcess) )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
    v8 = -2147467259;
    goto LABEL_107;
  }
  v9 = 0;
  if ( !GetKernelObjectSecurity(hProcess, 4u, 0, 0, &nLengthNeeded) && GetLastError() == 122 )
  {
    v10 = HeapAlloc(g_hWerheap, 0, nLengthNeeded);
    v46 = 0;
    v11 = v10;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v46);
    v47 = 0;
    v7 = v11;
    v46 = v11;
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v47);
    if ( v11 )
    {
      if ( !GetKernelObjectSecurity(hProcess, 4u, v11, nLengthNeeded, &nLengthNeeded) )
      {
        v46 = 0;
        v7 = 0;
        HeapFree(g_hWerheap, 0, v11);
      }
    }
  }
  StartupInfo.cb = 104;
  if ( WaitForSingleObject(hProcess, 0) )
  {
    RestartCommandLine = WerpGetRestartCommandLine(hProcess, 0, &v41, 0);
    if ( (!RestartCommandLine || RestartCommandLine == -2147024774) && (v13 = v41) != 0 )
    {
      unique_for = utl::make_unique_for_overwrite<wchar_t [0],0>(&v47, v41);
      utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&v48, unique_for);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v47);
      v15 = v48;
      if ( v48 )
      {
        *(_WORD *)v48 = 0;
        v21 = WerpGetRestartCommandLine(hProcess, v15, &v41, 0);
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
              WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids,
              (unsigned int)v21);
          *(_WORD *)v15 = 0;
        }
      }
      else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, 2 * v13);
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
    WPP_SF_(*((_QWORD *)v18 + 2), v19, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
LABEL_28:
    LastError = GetLastError();
    v8 = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_107;
  }
  v41 = 0;
  v47 = 0;
  v50 = 0;
  Policy_Internal = AppModelPolicy_GetPolicy_Internal(hToken, v17, &v41, &v50, &v47);
  v8 = Policy_Internal | 0x10000000;
  if ( Policy_Internal < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_107;
    v25 = 148;
    v26 = v8;
LABEL_41:
    WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, v26);
    goto LABEL_107;
  }
  v27 = v41;
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
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(lpCurrentDirectory) )
    {
      v8 = -2147024882;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
      goto LABEL_107;
    }
    if ( !UtilPathTail(lpCurrentDirectory[0]) )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
        v31 = (WCHAR *)lpCurrentDirectory[0];
        v32 = 0;
      }
      lpCurrentDirectory[1] = v31;
      *v31 = v32;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(lpCurrentDirectory);
LABEL_65:
    v34 = lpEnvironment;
    v35 = hToken;
    lpEnvironment = v33;
    if ( v34 )
      DestroyEnvironmentBlock(v34);
    if ( !CreateEnvironmentBlock(&lpEnvironment, v35, 0) )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_75;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_72:
        if ( v36 != (wchar_t *)&WPP_GLOBAL_Control && (v36[14] & 4) != 0 )
          WPP_SF_S(*((_QWORD *)v36 + 2), 155, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
LABEL_75:
        if ( !ImpersonateLoggedOnUser(hToken) )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_28;
          v19 = 156;
          goto LABEL_27;
        }
        v37 = SetErrorMode(1u);
        SetThreadErrorMode(1u, &OldMode);
        if ( a5 )
          *a5 = UtilWaitForSingleObject(L"Process", hProcess, 0xBB8u) == 0;
        if ( v7 )
        {
          LODWORD(v52) = 0;
          *((_QWORD *)&v51 + 1) = v7;
          LODWORD(v51) = 24;
        }
        wer::ProcessInformation::Clear((wer::ProcessInformation *)&ProcessInformation);
        if ( CreateProcessAsUserW(
               hToken,
               0,
               lpCommandLine[0],
               (LPSECURITY_ATTRIBUTES)((unsigned __int64)&v51 & -(__int64)(v7 != 0)),
               0,
               0,
               0x400u,
               lpEnvironment,
               lpCurrentDirectory[0],
               &StartupInfo,
               &ProcessInformation) )
        {
          SetErrorMode(v37);
          SetThreadErrorMode(OldMode, 0);
        }
        else
        {
          SetErrorMode(v37);
          SetThreadErrorMode(OldMode, 0);
          if ( v27 != 786433 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
            v38 = GetLastError();
            v8 = ERROR_HR_FROM_WIN32(v38);
            goto LABEL_93;
          }
          v39 = WerpLaunchPackagedCWA(hProcess, v9);
          v8 = v39;
          if ( v39 < 0 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                158,
                WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids,
                (unsigned int)v39);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
    }
    v36 = WPP_GLOBAL_Control;
    goto LABEL_72;
  }
  if ( v27 == 786433 )
  {
    PackagedCWALauncherCommandLine = WerpGeneratePackagedCWALauncherCommandLine(hProcess, a2, v9, lpCommandLine);
    v33 = 0;
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, v27);
  v8 = -2147418113;
LABEL_107:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v46);
  tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&int DestroyEnvironmentBlock(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&int DestroyEnvironmentBlock(void *),0>>(&lpEnvironment);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hToken);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpCurrentDirectory);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpCommandLine);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v48);
  wer::ProcessInformation::Clear((wer::ProcessInformation *)&ProcessInformation);
  return v8;
}

```

## disassembly

```asm
0x180037e40  mov     rax, rsp
0x180037e43  mov     [rax+8], rbx
0x180037e47  mov     [rax+20h], r9
0x180037e4b  mov     [rax+18h], r8
0x180037e4f  mov     [rax+10h], rdx
0x180037e53  push    rbp
0x180037e54  push    rsi
0x180037e55  push    rdi
0x180037e56  push    r12
0x180037e58  push    r13
0x180037e5a  push    r14
0x180037e5c  push    r15
0x180037e5e  lea     rbp, [rsp-80h]
0x180037e63  sub     rsp, 180h
0x180037e6a  mov     r15, rcx
0x180037e6d  mov     esi, 68h ; 'h'
0x180037e72  mov     r8d, esi; Size
0x180037e75  lea     rcx, [rbp+0B0h+StartupInfo]; void *
0x180037e79  xor     edx, edx; Val
0x180037e7b  mov     rbx, r9
0x180037e7e  call    memset_0
0x180037e83  xorps   xmm0, xmm0
0x180037e86  lea     rcx, [rbp+0B0h+lpCommandLine]; void *
0x180037e8a  xor     eax, eax
0x180037e8c  xor     r12d, r12d
0x180037e8f  movups  xmmword ptr [rbp+0B0h+ProcessInformation.hProcess], xmm0
0x180037e93  mov     qword ptr [rbp+0B0h+ProcessInformation.dwProcessId], rax
0x180037e97  mov     [rbp+0B0h+var_120], r12
0x180037e9b  mov     [rsp+1B0h+var_150], r12d
0x180037ea0  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180037ea5  lea     rcx, [rbp+0B0h+var_118]; void *
0x180037ea9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180037eae  xor     eax, eax
0x180037eb0  mov     [rsp+1B0h+hToken], r12
0x180037eb5  mov     [rsp+1B0h+lpEnvironment], r12
0x180037eba  xorps   xmm0, xmm0
0x180037ebd  mov     [rsp+1B0h+OldMode], r12d
0x180037ec2  mov     edi, r12d
0x180037ec5  mov     [rbp+0B0h+var_130], r12
0x180037ec9  mov     [rbp+0B0h+var_E0], rax
0x180037ecd  mov     [rsp+1B0h+nLengthNeeded], r12d
0x180037ed2  movups  [rbp+0B0h+var_F0], xmm0
0x180037ed6  test    rbx, rbx
0x180037ed9  jz      short loc_180037EDE
0x180037edb  mov     [rbx], r12d
0x180037ede  mov     rax, [rbp+0B0h+arg_20]
0x180037ee5  test    rax, rax
0x180037ee8  jz      short loc_180037EED
0x180037eea  mov     [rax], r12d
0x180037eed  mov     rcx, r15; hProcess
0x180037ef0  call    ?UtilCheckProcessExecutionTimeForRestart@@YAHPEAX@Z; UtilCheckProcessExecutionTimeForRestart(void *)
0x180037ef5  test    eax, eax
0x180037ef7  jnz     short loc_180037F31
0x180037ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f00  lea     rsi, WPP_GLOBAL_Control
0x180037f07  cmp     rcx, rsi
0x180037f0a  jz      short loc_180037F27
0x180037f0c  test    byte ptr [rcx+1Ch], 4
0x180037f10  jz      short loc_180037F27
0x180037f12  mov     rcx, [rcx+10h]
0x180037f16  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180037f1d  mov     edx, 90h
0x180037f22  call    WPP_SF_
0x180037f27  mov     ebx, 80004005h
0x180037f2c  jmp     loc_180038601
0x180037f31  xor     r9d, r9d; nLength
0x180037f34  lea     rax, [rsp+1B0h+nLengthNeeded]
0x180037f39  xor     r8d, r8d; pSecurityDescriptor
0x180037f3c  mov     [rsp+1B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180037f41  mov     rcx, r15; Handle
0x180037f44  mov     r13, r12
0x180037f47  lea     edx, [r9+4]; RequestedInformation
0x180037f4b  call    cs:__imp_GetKernelObjectSecurity
0x180037f51  test    eax, eax
0x180037f53  jnz     loc_180037FDE
0x180037f59  call    cs:__imp_GetLastError
0x180037f5f  cmp     eax, 7Ah ; 'z'
0x180037f62  jnz     short loc_180037FDE
0x180037f64  mov     r8d, [rsp+1B0h+nLengthNeeded]; dwBytes
0x180037f69  xor     edx, edx; dwFlags
0x180037f6b  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180037f72  call    cs:__imp_HeapAlloc
0x180037f78  lea     rcx, [rbp+0B0h+var_130]; void *
0x180037f7c  mov     [rbp+0B0h+var_130], r12
0x180037f80  mov     rbx, rax
0x180037f83  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180037f88  lea     rcx, [rbp+0B0h+var_128]; void *
0x180037f8c  mov     [rbp+0B0h+var_128], r12
0x180037f90  mov     rdi, rbx
0x180037f93  mov     [rbp+0B0h+var_130], rbx
0x180037f97  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180037f9c  test    rbx, rbx
0x180037f9f  jz      short loc_180037FDE
0x180037fa1  mov     r9d, [rsp+1B0h+nLengthNeeded]; nLength
0x180037fa6  lea     rax, [rsp+1B0h+nLengthNeeded]
0x180037fab  mov     r8, rbx; pSecurityDescriptor
0x180037fae  mov     [rsp+1B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180037fb3  mov     edx, 4; RequestedInformation
0x180037fb8  mov     rcx, r15; Handle
0x180037fbb  call    cs:__imp_GetKernelObjectSecurity
0x180037fc1  test    eax, eax
0x180037fc3  jnz     short loc_180037FDE
0x180037fc5  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180037fcc  mov     r8, rbx; lpMem
0x180037fcf  xor     edx, edx; dwFlags
0x180037fd1  mov     [rbp+0B0h+var_130], r12
0x180037fd5  mov     rdi, r12
0x180037fd8  call    cs:__imp_HeapFree
0x180037fde  xor     edx, edx; dwMilliseconds
0x180037fe0  mov     [rbp+0B0h+StartupInfo.cb], esi
0x180037fe3  mov     rcx, r15; hHandle
0x180037fe6  call    cs:__imp_WaitForSingleObject
0x180037fec  lea     rsi, WPP_GLOBAL_Control
0x180037ff3  lea     r14, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180037ffa  test    eax, eax
0x180037ffc  jz      loc_180038086
0x180038002  xor     r9d, r9d
0x180038005  lea     r8, [rsp+1B0h+var_150]
0x18003800a  xor     edx, edx
0x18003800c  mov     rcx, r15
0x18003800f  call    WerpGetRestartCommandLine
0x180038014  test    eax, eax
0x180038016  jz      short loc_180038023
0x180038018  cmp     eax, 8007007Ah
0x18003801d  jnz     loc_18003813A
0x180038023  mov     r12d, [rsp+1B0h+var_150]
0x180038028  test    r12d, r12d
0x18003802b  jz      loc_180038137
0x180038031  mov     edx, r12d
0x180038034  lea     rcx, [rbp+0B0h+var_128]
0x180038038  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18003803d  mov     rdx, rax
0x180038040  lea     rcx, [rbp+0B0h+var_120]
0x180038044  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x180038049  lea     rcx, [rbp+0B0h+var_128]; void *
0x18003804d  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180038052  mov     rbx, [rbp+0B0h+var_120]
0x180038056  test    rbx, rbx
0x180038059  jnz     loc_1800380E2
0x18003805f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038066  cmp     rcx, rsi
0x180038069  jz      short loc_180038086
0x18003806b  test    byte ptr [rcx+1Ch], 1
0x18003806f  jz      short loc_180038086
0x180038071  mov     rcx, [rcx+10h]
0x180038075  lea     r9d, [r12+r12]
0x180038079  mov     edx, 91h
0x18003807e  mov     r8, r14
0x180038081  call    WPP_SF_d
0x180038086  lea     rcx, [rsp+1B0h+hToken]
0x18003808b  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180038090  mov     r8, rax; TokenHandle
0x180038093  mov     edx, 0Bh; DesiredAccess
0x180038098  mov     rcx, r15; ProcessHandle
0x18003809b  call    cs:__imp_OpenProcessToken
0x1800380a1  xor     ecx, ecx
0x1800380a3  test    eax, eax
0x1800380a5  jnz     loc_18003817A
0x1800380ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380b2  cmp     rcx, rsi
0x1800380b5  jz      short loc_1800380CE
0x1800380b7  test    byte ptr [rcx+1Ch], 1
0x1800380bb  jz      short loc_1800380CE
0x1800380bd  mov     edx, 93h
0x1800380c2  mov     rcx, [rcx+10h]
0x1800380c6  mov     r8, r14
0x1800380c9  call    WPP_SF_
0x1800380ce  call    cs:__imp_GetLastError
0x1800380d4  mov     ecx, eax; unsigned int
0x1800380d6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800380db  mov     ebx, eax
0x1800380dd  jmp     loc_180038601
0x1800380e2  xor     r12d, r12d
0x1800380e5  lea     r8, [rsp+1B0h+var_150]
0x1800380ea  xor     r9d, r9d
0x1800380ed  mov     [rbx], r12w
0x1800380f1  mov     rdx, rbx
0x1800380f4  mov     rcx, r15
0x1800380f7  call    WerpGetRestartCommandLine
0x1800380fc  test    eax, eax
0x1800380fe  jns     short loc_18003812F
0x180038100  mov     rcx, cs:WPP_GLOBAL_Control
0x180038107  cmp     rcx, rsi
0x18003810a  jz      short loc_180038126
0x18003810c  test    byte ptr [rcx+1Ch], 1
0x180038110  jz      short loc_180038126
0x180038112  mov     rcx, [rcx+10h]
0x180038116  mov     edx, 92h
0x18003811b  mov     r9d, eax
0x18003811e  mov     r8, r14
0x180038121  call    WPP_SF_d
0x180038126  mov     [rbx], r12w
0x18003812a  jmp     loc_180038086
0x18003812f  mov     r13, rbx
0x180038132  jmp     loc_180038086
0x180038137  xor     r12d, r12d
0x18003813a  cmp     eax, 1
0x18003813d  jnz     loc_180038086
0x180038143  mov     rcx, r15; Process
0x180038146  call    cs:__imp_GetProcessId
0x18003814c  mov     r9d, 1
0x180038152  lea     r8, aWerrec; "WerRec"
0x180038159  mov     ecx, eax
0x18003815b  lea     edx, [r9+2]
0x18003815f  call    WerpAddTerminationReason
0x180038164  mov     edx, 0FFh; uExitCode
0x180038169  mov     rcx, r15; hProcess
0x18003816c  call    cs:__imp_TerminateProcess
0x180038172  mov     ebx, r12d
0x180038175  jmp     loc_180038601
0x18003817a  mov     [rsp+1B0h+var_150], ecx
0x18003817e  lea     rax, [rbp+0B0h+var_128]
0x180038182  mov     [rbp+0B0h+var_128], rcx
0x180038186  lea     r9, [rbp+0B0h+var_F8]
0x18003818a  mov     [rbp+0B0h+var_F8], rcx
0x18003818e  lea     r8, [rsp+1B0h+var_150]
0x180038193  mov     rcx, [rsp+1B0h+hToken]
0x180038198  mov     [rsp+1B0h+lpnLengthNeeded], rax
0x18003819d  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x1800381a2  mov     ebx, eax
0x1800381a4  or      ebx, 10000000h
0x1800381aa  jge     short loc_1800381DF
0x1800381ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381b3  cmp     rcx, rsi
0x1800381b6  jz      loc_180038601
0x1800381bc  test    byte ptr [rcx+1Ch], 1
0x1800381c0  jz      loc_180038601
0x1800381c6  mov     edx, 94h
0x1800381cb  mov     r9d, ebx
0x1800381ce  mov     rcx, [rcx+10h]
0x1800381d2  mov     r8, r14
0x1800381d5  call    WPP_SF_d
0x1800381da  jmp     loc_180038601
0x1800381df  mov     r12d, [rsp+1B0h+var_150]
0x1800381e4  xor     edx, edx; dwMilliseconds
0x1800381e6  mov     rcx, r15; hHandle
0x1800381e9  call    cs:__imp_WaitForSingleObject
0x1800381ef  xor     ebx, ebx
0x1800381f1  test    eax, eax
0x1800381f3  jz      short loc_180038221
0x1800381f5  mov     rcx, r15; Process
0x1800381f8  call    cs:__imp_GetProcessId
0x1800381fe  mov     ecx, eax
0x180038200  lea     r9d, [rbx+1]
0x180038204  lea     r8, aWerrec; "WerRec"
0x18003820b  lea     edx, [rbx+3]
0x18003820e  call    WerpAddTerminationReason
0x180038213  mov     edx, 0FFh; uExitCode
0x180038218  mov     rcx, r15; hProcess
0x18003821b  call    cs:__imp_TerminateProcess
0x180038221  test    r13, r13
0x180038224  jz      short loc_18003822D
0x180038226  cmp     [r13+0], bx
0x18003822b  jnz     short loc_180038234
0x18003822d  mov     r13, [rbp+0B0h+arg_10]
0x180038234  cmp     r12d, 0C0000h
0x18003823b  jnz     loc_1800383E7
0x180038241  mov     r8, [rbp+0B0h+arg_8]
0x180038248  lea     r9, Src
0x18003824f  test    r13, r13
0x180038252  lea     rdx, aSS_2; "\"%s\" %s"
0x180038259  lea     rcx, [rbp+0B0h+lpCommandLine]
0x18003825d  cmovnz  r9, r13
0x180038261  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180038266  mov     ebx, eax
0x180038268  test    eax, eax
0x18003826a  jns     short loc_180038293
0x18003826c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038273  cmp     rcx, rsi
0x180038276  jz      loc_180038601
0x18003827c  test    byte ptr [rcx+1Ch], 1
0x180038280  jz      loc_180038601
0x180038286  mov     edx, 95h
0x18003828b  mov     r9d, eax
0x18003828e  jmp     loc_1800381CE
0x180038293  mov     rdx, [rbp+0B0h+arg_8]
0x18003829a  lea     rcx, [rbp+0B0h+var_118]
0x18003829e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800382a3  xor     r9d, r9d
0x1800382a6  test    al, al
0x1800382a8  jnz     short loc_1800382DF
0x1800382aa  mov     ebx, 8007000Eh
0x1800382af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382b6  cmp     rcx, rsi
0x1800382b9  jz      loc_180038601
0x1800382bf  test    byte ptr [rcx+1Ch], 1
0x1800382c3  jz      loc_180038601
0x1800382c9  mov     rcx, [rcx+10h]
0x1800382cd  mov     edx, 96h
0x1800382d2  mov     r8, r14
0x1800382d5  call    WPP_SF_
0x1800382da  jmp     loc_180038601
0x1800382df  mov     r8, [rbp+0B0h+var_118]
0x1800382e3  mov     rcx, r8; wchar_t *
0x1800382e6  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x1800382eb  mov     rbx, rax
0x1800382ee  test    rax, rax
0x1800382f1  jnz     short loc_180038329
0x1800382f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382fa  cmp     rcx, rsi
  ... truncated ...
```
