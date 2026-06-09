# InitThreadPool(int,int)

- ea: `0x180049058`
- end: `0x1800492e2`
- name: `?InitThreadPool@@YAJHH@Z`
- size: `650`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016c88`

## callees

- `0x180015050`
- `0x180020cdc`
- `0x180048e44`
- `0x180049058`
- `0x180049370`
- `0x1800494bc`
- `0x18004d350`
- `0x18004d854`
- `0x18004db70`
- `0x18004df40`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800490ca`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800490ca`
- `KERNEL32!GetSystemInfo` at `0x1800490a1`
- `KERNEL32!GetSystemInfo` at `0x1800490a1`
- `KERNEL32!CreateIoCompletionPort` at `0x180049162`
- `KERNEL32!CreateIoCompletionPort` at `0x180049162`
- `ole32!CoUninitialize` at `0x1800492c5`
- `ole32!CoUninitialize` at `0x1800492c5`

## pseudocode

```c
__int64 __fastcall InitThreadPool(int a1, int a2)
{
  DWORD dwNumberOfProcessors; // ecx
  int v5; // ecx
  unsigned int v6; // ebx
  unsigned int LastWin32Error; // eax
  int Instance; // eax
  unsigned int CurrentProcessCpuCount; // ebx
  void **v11; // [rsp+28h] [rbp-48h]
  int v12; // [rsp+30h] [rbp-40h] BYREF
  struct IUnknown *v13; // [rsp+38h] [rbp-38h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v16; // [rsp+A8h] [rbp+38h] BYREF

  v13 = 0;
  v12 = 0;
  if ( (unsigned int)RunningOnInetinfo() && (unsigned int)ProcessModelIsEnabled() )
  {
    g_fUsingCorThreadPool = 0;
    GetSystemInfo(&SystemInfo);
    dwNumberOfProcessors = 1;
    if ( SystemInfo.dwNumberOfProcessors )
      dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
    THREADPOOL::g_NumProcessors = dwNumberOfProcessors;
    THREADPOOL::g_MaxFreeThreads = THREADPOOL::g_MaxFreeThreadsPerCPU * dwNumberOfProcessors;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v5 = THREADPOOL::g_NumProcessors * THREADPOOL::g_MinThreadsPerCPU;
    THREADPOOL::g_CpuUtilization = 0;
    THREADPOOL::g_NumThreads = 0;
    THREADPOOL::g_NumFreeThreads = 0;
    THREADPOOL::g_LastThreadExitTime = *(__int64 *)&SystemTimeAsFileTime / 10000;
    THREADPOOL::g_NumCurrentCalls = 0;
    THREADPOOL::g_NumThreadsLimitMax = THREADPOOL::g_NumProcessors * THREADPOOL::g_DefaultMaxThreadsPerCPU;
    if ( THREADPOOL::g_NumProcessors * THREADPOOL::g_MinThreadsPerCPU > THREADPOOL::g_NumProcessors
                                                                      * THREADPOOL::g_DefaultMaxThreadsPerCPU )
      v5 = THREADPOOL::g_NumProcessors * THREADPOOL::g_DefaultMaxThreadsPerCPU;
    THREADPOOL::g_NumThreadsLimitMin = v5;
    THREADPOOL::g_NumThreadsLimit = v5;
    v6 = LaunchOneThread((LPTHREAD_START_ROUTINE)ThreadGateThreadProc);
    if ( !v6 )
    {
      THREADPOOL::g_CompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
      if ( !THREADPOOL::g_CompletionPort )
      {
        LastWin32Error = GetLastWin32Error();
LABEL_24:
        v6 = LastWin32Error;
        goto LABEL_28;
      }
      _InterlockedIncrement(&THREADPOOL::g_NumThreads);
      v6 = LaunchOneThread((LPTHREAD_START_ROUTINE)ThreadPoolThreadProc);
      if ( v6 )
        _InterlockedDecrement(&THREADPOOL::g_NumThreads);
    }
  }
  else
  {
    g_fUsingCorThreadPool = 1;
    v6 = EnsureCoInitialized(&v12);
    if ( !v6 )
    {
      v6 = SelectRuntimeFlavor(&v13, 0);
      if ( !v6 )
      {
        if ( v13 )
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, LPVOID *))v13->lpVtbl->QueryInterface)(
                       v13,
                       &IID_ICorThreadpool,
                       &g_pCorThreadpool);
        else
          Instance = LegacyActivationShim::ClrCoCreateInstance(
                       &CLSID_CorRuntimeHost,
                       0,
                       1u,
                       &IID_ICorThreadpool,
                       &g_pCorThreadpool,
                       v11);
        v6 = Instance;
        if ( !Instance && g_pCorThreadpool )
        {
          if ( !a1 )
            goto LABEL_28;
          CurrentProcessCpuCount = GetCurrentProcessCpuCount();
          if ( a2 )
          {
            SystemTimeAsFileTime.dwLowDateTime = 0;
            v16 = 0;
            if ( (*(int (__fastcall **)(LPVOID, struct _FILETIME *, unsigned int *))(*(_QWORD *)g_pCorThreadpool + 96LL))(
                   g_pCorThreadpool,
                   &SystemTimeAsFileTime,
                   &v16) >= 0 )
            {
              g_dwMaxWorkerThreadsOriginal = SystemTimeAsFileTime.dwLowDateTime;
              g_dwMaxIoThreadsOriginal = v16;
            }
          }
          LastWin32Error = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)g_pCorThreadpool + 88LL))(
                             g_pCorThreadpool,
                             2 * CurrentProcessCpuCount,
                             2 * CurrentProcessCpuCount);
          goto LABEL_24;
        }
        g_fUsingCorThreadPool = 0;
        g_pCorThreadpool = 0;
        if ( !Instance )
          Instance = -2147467259;
        g_hrThreadPoolInitFailed = Instance;
      }
    }
  }
LABEL_28:
  ReleaseInterface(v13);
  if ( v12 )
    CoUninitialize();
  return v6;
}

```

## disassembly

```asm
0x180049058  mov     [rsp-18h+arg_0], rbx
0x18004905d  mov     [rsp-18h+arg_8], rsi
0x180049062  push    rbp
0x180049063  push    rdi
0x180049064  push    r14
0x180049066  mov     rbp, rsp
0x180049069  sub     rsp, 70h
0x18004906d  xor     r14d, r14d
0x180049070  mov     esi, edx
0x180049072  mov     [rbp+var_38], r14
0x180049076  mov     edi, ecx
0x180049078  mov     [rbp+var_40], r14d
0x18004907c  call    ?RunningOnInetinfo@@YAHXZ; RunningOnInetinfo(void)
0x180049081  test    eax, eax
0x180049083  jz      loc_1800491A7
0x180049089  call    ?ProcessModelIsEnabled@@YAHXZ; ProcessModelIsEnabled(void)
0x18004908e  test    eax, eax
0x180049090  jz      loc_1800491A7
0x180049096  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18004909a  mov     cs:?g_fUsingCorThreadPool@@3HA, r14d; int g_fUsingCorThreadPool
0x1800490a1  call    cs:__imp_GetSystemInfo
0x1800490a7  mov     eax, [rbp+SystemInfo.dwNumberOfProcessors]
0x1800490aa  lea     ecx, [r14+1]
0x1800490ae  test    eax, eax
0x1800490b0  cmovnz  ecx, eax
0x1800490b3  mov     cs:?g_NumProcessors@THREADPOOL@@3JA, ecx; long THREADPOOL::g_NumProcessors
0x1800490b9  imul    ecx, cs:?g_MaxFreeThreadsPerCPU@THREADPOOL@@3JA; long THREADPOOL::g_MaxFreeThreadsPerCPU
0x1800490c0  mov     cs:?g_MaxFreeThreads@THREADPOOL@@3JA, ecx; long THREADPOOL::g_MaxFreeThreads
0x1800490c6  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800490ca  call    cs:__imp_GetSystemTimeAsFileTime
0x1800490d0  mov     ecx, cs:?g_MinThreadsPerCPU@THREADPOOL@@3JA; long THREADPOOL::g_MinThreadsPerCPU
0x1800490d6  mov     rax, 346DC5D63886594Bh
0x1800490e0  imul    qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800490e4  imul    ecx, cs:?g_NumProcessors@THREADPOOL@@3JA; long THREADPOOL::g_NumProcessors
0x1800490eb  mov     cs:?g_CpuUtilization@THREADPOOL@@3JA, r14d; long THREADPOOL::g_CpuUtilization
0x1800490f2  sar     rdx, 0Bh
0x1800490f6  mov     rax, rdx
0x1800490f9  mov     cs:?g_NumThreads@THREADPOOL@@3JA, r14d; long THREADPOOL::g_NumThreads
0x180049100  shr     rax, 3Fh
0x180049104  add     rdx, rax
0x180049107  mov     cs:?g_NumFreeThreads@THREADPOOL@@3JA, r14d; long THREADPOOL::g_NumFreeThreads
0x18004910e  mov     cs:?g_LastThreadExitTime@THREADPOOL@@3_JA, rdx; __int64 THREADPOOL::g_LastThreadExitTime
0x180049115  mov     edx, cs:?g_DefaultMaxThreadsPerCPU@THREADPOOL@@3JA; long THREADPOOL::g_DefaultMaxThreadsPerCPU
0x18004911b  imul    edx, cs:?g_NumProcessors@THREADPOOL@@3JA; long THREADPOOL::g_NumProcessors
0x180049122  mov     cs:?g_NumCurrentCalls@THREADPOOL@@3JA, r14d; long THREADPOOL::g_NumCurrentCalls
0x180049129  cmp     ecx, edx
0x18004912b  mov     cs:?g_NumThreadsLimitMax@THREADPOOL@@3JA, edx; long THREADPOOL::g_NumThreadsLimitMax
0x180049131  cmovg   ecx, edx
0x180049134  mov     cs:?g_NumThreadsLimitMin@THREADPOOL@@3JA, ecx; long THREADPOOL::g_NumThreadsLimitMin
0x18004913a  mov     cs:?g_NumThreadsLimit@THREADPOOL@@3JA, ecx; long THREADPOOL::g_NumThreadsLimit
0x180049140  lea     rcx, ?ThreadGateThreadProc@@YAKPEAX@Z; lpStartAddress
0x180049147  call    ?LaunchOneThread@@YAJP6AKPEAX@Z@Z; LaunchOneThread(ulong (*)(void *))
0x18004914c  mov     ebx, eax
0x18004914e  test    eax, eax
0x180049150  jnz     loc_1800492B6
0x180049156  xor     r9d, r9d; NumberOfConcurrentThreads
0x180049159  xor     r8d, r8d; CompletionKey
0x18004915c  xor     edx, edx; ExistingCompletionPort
0x18004915e  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180049162  call    cs:__imp_CreateIoCompletionPort
0x180049168  mov     cs:?g_CompletionPort@THREADPOOL@@3PEAXEA, rax; void * THREADPOOL::g_CompletionPort
0x18004916f  test    rax, rax
0x180049172  jnz     short loc_18004917E
0x180049174  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180049179  jmp     loc_180049292
0x18004917e  lock inc cs:?g_NumThreads@THREADPOOL@@3JA; long THREADPOOL::g_NumThreads
0x180049185  lea     rcx, ?ThreadPoolThreadProc@@YAKPEAX@Z; lpStartAddress
0x18004918c  call    ?LaunchOneThread@@YAJP6AKPEAX@Z@Z; LaunchOneThread(ulong (*)(void *))
0x180049191  mov     ebx, eax
0x180049193  test    eax, eax
0x180049195  jz      loc_1800492B6
0x18004919b  lock dec cs:?g_NumThreads@THREADPOOL@@3JA; long THREADPOOL::g_NumThreads
0x1800491a2  jmp     loc_1800492B6
0x1800491a7  lea     rcx, [rbp+var_40]; int *
0x1800491ab  mov     cs:?g_fUsingCorThreadPool@@3HA, 1; int g_fUsingCorThreadPool
0x1800491b5  call    ?EnsureCoInitialized@@YAJPEAH@Z; EnsureCoInitialized(int *)
0x1800491ba  mov     ebx, eax
0x1800491bc  test    eax, eax
0x1800491be  jnz     loc_1800492B6
0x1800491c4  xor     edx, edx; unsigned __int16 *
0x1800491c6  lea     rcx, [rbp+var_38]; struct IUnknown **
0x1800491ca  call    ?SelectRuntimeFlavor@@YAJPEAPEAUIUnknown@@PEBG@Z; SelectRuntimeFlavor(IUnknown * *,ushort const *)
0x1800491cf  mov     ebx, eax
0x1800491d1  test    eax, eax
0x1800491d3  jnz     loc_1800492B6
0x1800491d9  mov     rcx, [rbp+var_38]
0x1800491dd  lea     r8, ?g_pCorThreadpool@@3PEAUICorThreadpool@@EA; ICorThreadpool * g_pCorThreadpool
0x1800491e4  test    rcx, rcx
0x1800491e7  jnz     short loc_180049209
0x1800491e9  mov     [rsp+70h+var_50], r8; LPVOID *
0x1800491ee  lea     r9, IID_ICorThreadpool; riid
0x1800491f5  lea     r8d, [rax+1]; dwClsContext
0x1800491f9  xor     edx, edx; pUnkOuter
0x1800491fb  lea     rcx, CLSID_CorRuntimeHost; rclsid
0x180049202  call    ?ClrCoCreateInstance@LegacyActivationShim@@YAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z; LegacyActivationShim::ClrCoCreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180049207  jmp     short loc_18004921C
0x180049209  mov     rax, [rcx]
0x18004920c  lea     rdx, IID_ICorThreadpool
0x180049213  mov     rax, [rax]
0x180049216  call    cs:__guard_dispatch_icall_fptr
0x18004921c  mov     ebx, eax
0x18004921e  test    eax, eax
0x180049220  jnz     short loc_180049296
0x180049222  cmp     cs:?g_pCorThreadpool@@3PEAUICorThreadpool@@EA, r14; ICorThreadpool * g_pCorThreadpool
0x180049229  jz      short loc_180049296
0x18004922b  test    edi, edi
0x18004922d  jz      loc_1800492B6
0x180049233  call    ?GetCurrentProcessCpuCount@@YAKXZ; GetCurrentProcessCpuCount(void)
0x180049238  mov     ebx, eax
0x18004923a  test    esi, esi
0x18004923c  jz      short loc_180049278
0x18004923e  mov     rcx, cs:?g_pCorThreadpool@@3PEAUICorThreadpool@@EA; ICorThreadpool * g_pCorThreadpool
0x180049245  lea     r8, [rbp+arg_18]
0x180049249  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], r14d
0x18004924d  mov     [rbp+arg_18], r14d
0x180049251  mov     rdx, [rcx]
0x180049254  mov     rax, [rdx+60h]
0x180049258  lea     rdx, [rbp+SystemTimeAsFileTime]
0x18004925c  call    cs:__guard_dispatch_icall_fptr
0x180049262  test    eax, eax
0x180049264  js      short loc_180049278
0x180049266  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180049269  mov     cs:?g_dwMaxWorkerThreadsOriginal@@3KA, eax; ulong g_dwMaxWorkerThreadsOriginal
0x18004926f  mov     eax, [rbp+arg_18]
0x180049272  mov     cs:?g_dwMaxIoThreadsOriginal@@3KA, eax; ulong g_dwMaxIoThreadsOriginal
0x180049278  mov     rcx, cs:?g_pCorThreadpool@@3PEAUICorThreadpool@@EA; ICorThreadpool * g_pCorThreadpool
0x18004927f  lea     edx, [rbx+rbx]
0x180049282  mov     r8d, edx
0x180049285  mov     rax, [rcx]
0x180049288  mov     rax, [rax+58h]
0x18004928c  call    cs:__guard_dispatch_icall_fptr
0x180049292  mov     ebx, eax
0x180049294  jmp     short loc_1800492B6
0x180049296  test    ebx, ebx
0x180049298  mov     cs:?g_fUsingCorThreadPool@@3HA, r14d; int g_fUsingCorThreadPool
0x18004929f  mov     eax, ebx
0x1800492a1  mov     cs:?g_pCorThreadpool@@3PEAUICorThreadpool@@EA, r14; ICorThreadpool * g_pCorThreadpool
0x1800492a8  mov     ecx, 80004005h
0x1800492ad  cmovz   eax, ecx
0x1800492b0  mov     cs:?g_hrThreadPoolInitFailed@@3JA, eax; long g_hrThreadPoolInitFailed
0x1800492b6  mov     rcx, [rbp+var_38]; struct IUnknown *
0x1800492ba  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1800492bf  cmp     [rbp+var_40], r14d
0x1800492c3  jz      short loc_1800492CB
0x1800492c5  call    cs:__imp_CoUninitialize
0x1800492cb  lea     r11, [rsp+70h+var_s0]
0x1800492d0  mov     eax, ebx
0x1800492d2  mov     rbx, [r11+20h]
0x1800492d6  mov     rsi, [r11+28h]
0x1800492da  mov     rsp, r11
0x1800492dd  pop     r14
0x1800492df  pop     rdi
0x1800492e0  pop     rbp
0x1800492e1  retn
```
