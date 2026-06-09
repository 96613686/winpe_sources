# CReportManager::AddReportToQueue(ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18001f718`
- end: `0x18001fcec`
- name: `?AddReportToQueue@CReportManager@@AEAAJKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1492`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, service_task`

## callers

- `0x18001f458`

## callees

- `0x180004c64`
- `0x18000753c`
- `0x180009074`
- `0x18000a6c0`
- `0x18000ad98`
- `0x18000cf50`
- `0x18000db80`
- `0x18001f718`
- `0x18001fd44`
- `0x18001fe88`
- `0x180020680`
- `0x180023698`
- `0x180027f28`
- `0x18002d124`
- `0x1800334f8`
- `0x1800335e0`
- `0x180037710`
- `0x1800406a4`
- `0x180043804`
- `0x18004d2d4`
- `0x18004df60`
- `0x18004e384`
- `0x18004e764`
- `0x18004f8b8`
- `0x180053300`
- `0x180074490`
- `0x180075e38`
- `0x18007cc74`
- `0x18007d0a0`
- `0x18007e840`
- `0x1800808ec`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fca8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fca8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001faea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fb0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fbd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001faea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fb0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fbd5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001fb20`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001fbe6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001fb20`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001fbe6`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001faf9`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001faf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001fa46`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001fa46`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CReportManager::AddReportToQueue(__int64 a1)
{
  wchar_t *v2; // rcx
  __int64 v3; // rax
  int started; // edi
  __int64 v5; // rdx
  int IsSecondLevelDataThrottled; // r14d
  int v7; // r15d
  int inited; // eax
  wchar_t *v9; // rcx
  __int64 v10; // rdx
  unsigned int DwordData; // eax
  CReport *v12; // rcx
  int v13; // eax
  int v14; // eax
  HANDLE CurrentThread; // rax
  int ThreadPriority; // edi
  HANDLE v17; // rax
  CReport *v18; // rcx
  HANDLE v19; // rax
  CReportQueue *v20; // rcx
  int v21; // eax
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  union _ULARGE_INTEGER v24; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID lpMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  char v26; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  _BYTE v29[32]; // [rsp+68h] [rbp-98h] BYREF
  int v30; // [rsp+88h] [rbp-78h]
  _QWORD v31[650]; // [rsp+90h] [rbp-70h] BYREF

  CReportStore::CReportStore((CReportStore *)v31);
  v31[0] = &CReportQueue::`vftable';
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v29);
  v27 = 0;
  v28 = 0;
  v30 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  v24.QuadPart = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = *(_QWORD *)(a1 + 8);
  if ( !v3 )
  {
    started = -2147024809;
    if ( v2 != (wchar_t *)&WPP_GLOBAL_Control && (v2[14] & 1) != 0 )
    {
      v5 = 237;
LABEL_8:
      WPP_SF_(*((_QWORD *)v2 + 2), v5, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
      goto LABEL_83;
    }
    goto LABEL_83;
  }
  if ( *(char *)(v3 + 6616) < 0 )
  {
    if ( v2 != (wchar_t *)&WPP_GLOBAL_Control && (v2[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)v2 + 2), 238, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
    started = 1769477;
    goto LABEL_83;
  }
  started = CReportManager::StartReporting((CReportManager *)a1);
  if ( started < 0 )
    goto LABEL_83;
  if ( (unsigned int)CReport::IsSecondaryDataEnabled(*(CReport **)(a1 + 8)) )
  {
    IsSecondLevelDataThrottled = 0;
    CReportManager::AddPreConfiguredSecondLevelData((CReportManager *)a1);
  }
  else
  {
    IsSecondLevelDataThrottled = 1;
  }
  v23 = 0;
  v7 = CReportManager::ExternalCallbackBeforeQueue((CReportManager *)a1, &v23, IsSecondLevelDataThrottled);
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 5960LL) |= 0x400000u;
    started = -2145681407;
    goto LABEL_83;
  }
  if ( (unsigned int)CReport::IsThrottled(*(CReport **)(a1 + 8)) )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 5960LL) |= 0x2000u;
    started = 1769483;
    goto LABEL_83;
  }
  if ( !IsSecondLevelDataThrottled )
  {
    IsSecondLevelDataThrottled = CReport::IsSecondLevelDataThrottled(*(CReport **)(a1 + 8), 1);
    if ( IsSecondLevelDataThrottled )
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 5960LL) |= 0x1000u;
  }
  inited = CReportQueue::InitMachineStore((CReportQueue *)v31);
  started = inited;
  if ( inited < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_83;
    v10 = 240;
    goto LABEL_32;
  }
  if ( !IsSecondLevelDataThrottled )
  {
    if ( (int)CReportStore::GetFreeDiskSpace((CReportStore *)v31, &v24) < 0 )
      goto LABEL_47;
    DwordData = CRegSetting::GetDwordData((CRegSetting *)(*(_QWORD *)(a1 + 96) + 2808LL));
    if ( v24.QuadPart >= (unsigned __int64)DwordData << 20 )
      goto LABEL_47;
    IsSecondLevelDataThrottled = 1;
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 5960LL) |= 0x200000u;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
  }
  v12 = *(CReport **)(a1 + 8);
  if ( *((_DWORD *)v12 + 1468) != 4 )
  {
    v13 = CReport::RemoveAllFiles(v12);
    if ( v13 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 243, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        242,
        WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
        (unsigned int)v13);
    }
  }
LABEL_47:
  if ( v7 || IsSecondLevelDataThrottled )
  {
LABEL_73:
    CReportManager::AddTracingFile((CReportManager *)a1);
    if ( (int)CReportManager::AddReportToQueueAsZip(a1, lpMem) >= 0
      || (inited = CReportStore::AddReportToStore(v31, IsSecondLevelDataThrottled == 0, *(_QWORD *)(a1 + 8), lpMem),
          started = inited,
          inited >= 0) )
    {
      CReport::ReleaseReportLock(*(CReport **)(a1 + 8));
      v21 = CReportQueue::TriggerUploadTask(v20);
      if ( v21 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          247,
          WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
          (unsigned int)v21);
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 5960LL) |= 4u;
      started = 0;
      goto LABEL_83;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_83;
    v10 = 246;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, (unsigned int)inited);
    goto LABEL_83;
  }
  GetTickCount();
  started = CDataCollection::Initialize(
              (CDataCollection *)&v27,
              *(struct CReport **)(a1 + 8),
              *(struct CReportHandleInstance **)a1,
              *(void **)(a1 + 264));
  if ( started >= 0 )
  {
    v14 = CDataCollection::AddReportMetadata((CDataCollection *)&v27);
    if ( v14 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        245,
        WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
        (unsigned int)v14);
    goto LABEL_58;
  }
  if ( !(unsigned int)CReport::DumpsRequested(*(CReport **)(a1 + 8)) )
  {
LABEL_58:
    if ( (unsigned int)CReport::DumpsRequested(*(CReport **)(a1 + 8)) )
    {
      CurrentThread = GetCurrentThread();
      ThreadPriority = GetThreadPriority(CurrentThread);
      if ( ThreadPriority != 0x7FFFFFFF )
      {
        v17 = GetCurrentThread();
        SetThreadPriority(v17, -1);
      }
      if ( *(_DWORD *)(a1 + 200) )
      {
        v18 = *(CReport **)(a1 + 8);
        if ( (*((_DWORD *)v18 + 1468) == 3 || (*((_DWORD *)v18 + 1654) & 0x80000) != 0)
          && (!*(_DWORD *)CReport::GetProcessDumpObject(v18, WerDumpTypeTriageDump)
           || (*((_BYTE *)CReport::GetProcessDumpObject(*(CReport **)(a1 + 8), WerDumpTypeTriageDump) + 176) & 1) == 0)
          && (!*(_DWORD *)CReport::GetProcessDumpObject(*(CReport **)(a1 + 8), WerDumpTypeMiniDump)
           || (*((_BYTE *)CReport::GetProcessDumpObject(*(CReport **)(a1 + 8), WerDumpTypeMiniDump) + 176) & 1) == 0) )
        {
          CReportManager::AddDesktopHeapDataForReport((CReportManager *)a1);
        }
      }
      CDataCollection::AddQueueDumps((CDataCollection *)&v27, *(_DWORD *)(a1 + 216));
      if ( CReportManager::IsNativeDumpEnabled((CReportManager *)a1) )
        CReportManager::ExternalCallbackDataRequestEnd(a1, 0);
      if ( ThreadPriority != -1 )
      {
        v19 = GetCurrentThread();
        SetThreadPriority(v19, ThreadPriority);
      }
    }
    goto LABEL_73;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v5 = 244;
    goto LABEL_8;
  }
LABEL_83:
  if ( lpMem[0] != &v26 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v29);
  CReportStore::~CReportStore((CReportStore *)v31);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18001f718  push    rbp
0x18001f71a  push    rbx
0x18001f71b  push    rdi
0x18001f71c  push    r13
0x18001f71e  push    r14
0x18001f720  push    r15
0x18001f722  lea     rbp, [rsp-13F8h]
0x18001f72a  mov     eax, 14F8h
0x18001f72f  call    _alloca_probe
0x18001f734  sub     rsp, rax
0x18001f737  mov     rax, cs:__security_cookie
0x18001f73e  xor     rax, rsp
0x18001f741  mov     [rbp+1420h+var_40], rax
0x18001f748  mov     rbx, rcx
0x18001f74b  lea     rcx, [rbp+1420h+var_1490]; this
0x18001f74f  call    ??0CReportStore@@QEAA@XZ; CReportStore::CReportStore(void)
0x18001f754  lea     rax, ??_7CReportQueue@@6B@; const CReportQueue::`vftable'
0x18001f75b  mov     [rbp+1420h+var_1490], rax
0x18001f75f  lea     rcx, [rsp+1520h+var_14B8]; void *
0x18001f764  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001f769  xorps   xmm0, xmm0
0x18001f76c  movdqa  [rsp+1520h+var_14D0], xmm0
0x18001f772  mov     [rsp+1520h+var_14C0], 0
0x18001f77b  mov     [rbp+1420h+var_1498], 0
0x18001f782  lea     rcx, [rsp+1520h+lpMem]; void *
0x18001f787  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001f78c  nop
0x18001f78d  mov     qword ptr [rsp+1520h+var_14F8], 0
0x18001f796  lea     r13, WPP_GLOBAL_Control
0x18001f79d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7a4  cmp     rcx, r13
0x18001f7a7  jz      short loc_18001F7CB
0x18001f7a9  test    byte ptr [rcx+1Ch], 4
0x18001f7ad  jz      short loc_18001F7CB
0x18001f7af  mov     edx, 0ECh
0x18001f7b4  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18001f7bb  mov     rcx, [rcx+10h]
0x18001f7bf  call    WPP_SF_
0x18001f7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7cb  mov     rax, [rbx+8]
0x18001f7cf  test    rax, rax
0x18001f7d2  jnz     short loc_18001F806
0x18001f7d4  mov     edi, 80070057h
0x18001f7d9  cmp     rcx, r13
0x18001f7dc  jz      loc_18001FC90
0x18001f7e2  test    byte ptr [rcx+1Ch], 1
0x18001f7e6  jz      loc_18001FC90
0x18001f7ec  mov     edx, 0EDh
0x18001f7f1  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18001f7f8  mov     rcx, [rcx+10h]
0x18001f7fc  call    WPP_SF_
0x18001f801  jmp     loc_18001FC90
0x18001f806  test    byte ptr [rax+19D8h], 80h
0x18001f80d  jz      short loc_18001F839
0x18001f80f  cmp     rcx, r13
0x18001f812  jz      short loc_18001F82F
0x18001f814  test    byte ptr [rcx+1Ch], 4
0x18001f818  jz      short loc_18001F82F
0x18001f81a  mov     edx, 0EEh
0x18001f81f  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18001f826  mov     rcx, [rcx+10h]
0x18001f82a  call    WPP_SF_
0x18001f82f  mov     edi, 1B0005h
0x18001f834  jmp     loc_18001FC90
0x18001f839  mov     rcx, rbx; this
0x18001f83c  call    ?StartReporting@CReportManager@@AEAAJXZ; CReportManager::StartReporting(void)
0x18001f841  mov     edi, eax
0x18001f843  test    eax, eax
0x18001f845  js      loc_18001FC90
0x18001f84b  mov     rcx, [rbx+8]; this
0x18001f84f  call    ?IsSecondaryDataEnabled@CReport@@QEBAHXZ; CReport::IsSecondaryDataEnabled(void)
0x18001f854  test    eax, eax
0x18001f856  jnz     short loc_18001F85E
0x18001f858  lea     r14d, [rax+1]
0x18001f85c  jmp     short loc_18001F869
0x18001f85e  xor     r14d, r14d
0x18001f861  mov     rcx, rbx; this
0x18001f864  call    ?AddPreConfiguredSecondLevelData@CReportManager@@AEAAJXZ; CReportManager::AddPreConfiguredSecondLevelData(void)
0x18001f869  mov     [rsp+1520h+var_1500], 0
0x18001f871  mov     r8d, r14d; int
0x18001f874  lea     rdx, [rsp+1520h+var_1500]; int *
0x18001f879  mov     rcx, rbx; this
0x18001f87c  call    ?ExternalCallbackBeforeQueue@CReportManager@@QEAAHPEAHH@Z; CReportManager::ExternalCallbackBeforeQueue(int *,int)
0x18001f881  mov     r15d, eax
0x18001f884  cmp     [rsp+1520h+var_1500], 0
0x18001f889  jz      short loc_18001F8C8
0x18001f88b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f892  cmp     rcx, r13
0x18001f895  jz      short loc_18001F8B2
0x18001f897  test    byte ptr [rcx+1Ch], 4
0x18001f89b  jz      short loc_18001F8B2
0x18001f89d  mov     edx, 0EFh
0x18001f8a2  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18001f8a9  mov     rcx, [rcx+10h]
0x18001f8ad  call    WPP_SF_
0x18001f8b2  mov     rax, [rbx+8]
0x18001f8b6  bts     dword ptr [rax+1748h], 16h
0x18001f8be  mov     edi, 801B8001h
0x18001f8c3  jmp     loc_18001FC90
0x18001f8c8  mov     rcx, [rbx+8]; this
0x18001f8cc  call    ?IsThrottled@CReport@@QEAAHXZ; CReport::IsThrottled(void)
0x18001f8d1  test    eax, eax
0x18001f8d3  jz      short loc_18001F8EB
0x18001f8d5  mov     rax, [rbx+8]
0x18001f8d9  bts     dword ptr [rax+1748h], 0Dh
0x18001f8e1  mov     edi, 1B000Bh
0x18001f8e6  jmp     loc_18001FC90
0x18001f8eb  test    r14d, r14d
0x18001f8ee  jnz     short loc_18001F910
0x18001f8f0  lea     edx, [r14+1]; int
0x18001f8f4  mov     rcx, [rbx+8]; this
0x18001f8f8  call    ?IsSecondLevelDataThrottled@CReport@@QEAAHH@Z; CReport::IsSecondLevelDataThrottled(int)
0x18001f8fd  mov     r14d, eax
0x18001f900  test    eax, eax
0x18001f902  jz      short loc_18001F910
0x18001f904  mov     rcx, [rbx+8]
0x18001f908  bts     dword ptr [rcx+1748h], 0Ch
0x18001f910  lea     rcx, [rbp+1420h+var_1490]; this
0x18001f914  call    ?InitMachineStore@CReportQueue@@UEAAJXZ; CReportQueue::InitMachineStore(void)
0x18001f919  mov     edi, eax
0x18001f91b  test    eax, eax
0x18001f91d  jns     short loc_18001F956
0x18001f91f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f926  cmp     rcx, r13
0x18001f929  jz      loc_18001FC90
0x18001f92f  test    byte ptr [rcx+1Ch], 1
0x18001f933  jz      loc_18001FC90
0x18001f939  mov     edx, 0F0h
0x18001f93e  mov     r9d, eax
0x18001f941  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18001f948  mov     rcx, [rcx+10h]
0x18001f94c  call    WPP_SF_d
0x18001f951  jmp     loc_18001FC90
0x18001f956  test    r14d, r14d
0x18001f959  jnz     short loc_18001F9CB
0x18001f95b  lea     rdx, [rsp+1520h+var_14F8]; union _ULARGE_INTEGER *
0x18001f960  lea     rcx, [rbp+1420h+var_1490]; this
0x18001f964  call    ?GetFreeDiskSpace@CReportStore@@QEAAJPEAT_ULARGE_INTEGER@@@Z; CReportStore::GetFreeDiskSpace(_ULARGE_INTEGER *)
0x18001f969  test    eax, eax
0x18001f96b  js      loc_18001FA34
0x18001f971  mov     rcx, [rbx+60h]
0x18001f975  add     rcx, 0AF8h; this
0x18001f97c  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18001f981  mov     ecx, eax
0x18001f983  shl     rcx, 14h
0x18001f987  cmp     qword ptr [rsp+1520h+var_14F8], rcx
0x18001f98c  jnb     loc_18001FA34
0x18001f992  mov     r14d, 1
0x18001f998  mov     rax, [rbx+8]
0x18001f99c  bts     dword ptr [rax+1748h], 15h
0x18001f9a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9ab  cmp     rcx, r13
0x18001f9ae  jz      short loc_18001F9CB
0x18001f9b0  test    byte ptr [rcx+1Ch], 4
0x18001f9b4  jz      short loc_18001F9CB
0x18001f9b6  mov     edx, 0F1h
0x18001f9bb  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18001f9c2  mov     rcx, [rcx+10h]
0x18001f9c6  call    WPP_SF_
0x18001f9cb  mov     rcx, [rbx+8]; this
0x18001f9cf  cmp     dword ptr [rcx+16F0h], 4
0x18001f9d6  jz      short loc_18001FA34
0x18001f9d8  call    ?RemoveAllFiles@CReport@@QEAAJXZ; CReport::RemoveAllFiles(void)
0x18001f9dd  test    eax, eax
0x18001f9df  jns     short loc_18001FA0D
0x18001f9e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9e8  cmp     rcx, r13
0x18001f9eb  jz      short loc_18001FA34
0x18001f9ed  test    byte ptr [rcx+1Ch], 1
0x18001f9f1  jz      short loc_18001FA34
0x18001f9f3  mov     edx, 0F2h
0x18001f9f8  mov     r9d, eax
0x18001f9fb  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18001fa02  mov     rcx, [rcx+10h]
0x18001fa06  call    WPP_SF_d
0x18001fa0b  jmp     short loc_18001FA34
0x18001fa0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa14  cmp     rcx, r13
0x18001fa17  jz      short loc_18001FA34
0x18001fa19  test    byte ptr [rcx+1Ch], 4
0x18001fa1d  jz      short loc_18001FA34
0x18001fa1f  mov     edx, 0F3h
0x18001fa24  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18001fa2b  mov     rcx, [rcx+10h]
0x18001fa2f  call    WPP_SF_
0x18001fa34  test    r15d, r15d
0x18001fa37  jnz     loc_18001FBF2
0x18001fa3d  test    r14d, r14d
0x18001fa40  jnz     loc_18001FBF2
0x18001fa46  call    cs:__imp_GetTickCount
0x18001fa4d  nop     dword ptr [rax+rax+00h]
0x18001fa52  mov     r9, [rbx+108h]; void *
0x18001fa59  mov     r8, [rbx]; struct CReportHandleInstance *
0x18001fa5c  mov     rdx, [rbx+8]; struct CReport *
0x18001fa60  lea     rcx, [rsp+1520h+var_14D0]; this
0x18001fa65  call    ?Initialize@CDataCollection@@QEAAJPEAVCReport@@PEAVCReportHandleInstance@@PEAX@Z; CDataCollection::Initialize(CReport *,CReportHandleInstance *,void *)
0x18001fa6a  mov     edi, eax
0x18001fa6c  test    eax, eax
0x18001fa6e  jns     short loc_18001FAA1
0x18001fa70  mov     rcx, [rbx+8]; this
0x18001fa74  call    ?DumpsRequested@CReport@@QEAAHXZ; CReport::DumpsRequested(void)
0x18001fa79  test    eax, eax
0x18001fa7b  jz      short loc_18001FAD9
0x18001fa7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa84  cmp     rcx, r13
0x18001fa87  jz      loc_18001FC90
0x18001fa8d  test    byte ptr [rcx+1Ch], 1
0x18001fa91  jz      loc_18001FC90
0x18001fa97  mov     edx, 0F4h
0x18001fa9c  jmp     loc_18001F7F1
0x18001faa1  lea     rcx, [rsp+1520h+var_14D0]; this
0x18001faa6  call    ?AddReportMetadata@CDataCollection@@QEAAJXZ; CDataCollection::AddReportMetadata(void)
0x18001faab  test    eax, eax
0x18001faad  jns     short loc_18001FAD9
0x18001faaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fab6  cmp     rcx, r13
0x18001fab9  jz      short loc_18001FAD9
0x18001fabb  test    byte ptr [rcx+1Ch], 2
0x18001fabf  jz      short loc_18001FAD9
0x18001fac1  mov     edx, 0F5h
0x18001fac6  mov     r9d, eax
0x18001fac9  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18001fad0  mov     rcx, [rcx+10h]
0x18001fad4  call    WPP_SF_d
0x18001fad9  mov     rcx, [rbx+8]; this
0x18001fadd  call    ?DumpsRequested@CReport@@QEAAHXZ; CReport::DumpsRequested(void)
0x18001fae2  test    eax, eax
0x18001fae4  jz      loc_18001FBF2
0x18001faea  call    cs:__imp_GetCurrentThread
0x18001faf1  nop     dword ptr [rax+rax+00h]
0x18001faf6  mov     rcx, rax; hThread
0x18001faf9  call    cs:__imp_GetThreadPriority
0x18001fb00  nop     dword ptr [rax+rax+00h]
0x18001fb05  mov     edi, eax
0x18001fb07  cmp     eax, 7FFFFFFFh
0x18001fb0c  jz      short loc_18001FB2C
0x18001fb0e  call    cs:__imp_GetCurrentThread
0x18001fb15  nop     dword ptr [rax+rax+00h]
0x18001fb1a  mov     rcx, rax; hThread
0x18001fb1d  or      edx, 0FFFFFFFFh; nPriority
0x18001fb20  call    cs:__imp_SetThreadPriority
0x18001fb27  nop     dword ptr [rax+rax+00h]
0x18001fb2c  cmp     dword ptr [rbx+0C8h], 0
0x18001fb33  jz      short loc_18001FBAA
0x18001fb35  mov     rcx, [rbx+8]; this
0x18001fb39  cmp     dword ptr [rcx+16F0h], 3
0x18001fb40  jz      short loc_18001FB4E
0x18001fb42  test    dword ptr [rcx+19D8h], 80000h
0x18001fb4c  jz      short loc_18001FBAA
0x18001fb4e  mov     r15d, 4
0x18001fb54  mov     edx, r15d; enum _WER_DUMP_TYPE
0x18001fb57  call    ?GetProcessDumpObject@CReport@@QEAAPEAVCProcessDump@@W4_WER_DUMP_TYPE@@@Z; CReport::GetProcessDumpObject(_WER_DUMP_TYPE)
0x18001fb5c  cmp     dword ptr [rax], 0
0x18001fb5f  jz      short loc_18001FB76
0x18001fb61  mov     edx, r15d; enum _WER_DUMP_TYPE
0x18001fb64  mov     rcx, [rbx+8]; this
0x18001fb68  call    ?GetProcessDumpObject@CReport@@QEAAPEAVCProcessDump@@W4_WER_DUMP_TYPE@@@Z; CReport::GetProcessDumpObject(_WER_DUMP_TYPE)
0x18001fb6d  test    byte ptr [rax+0B0h], 1
0x18001fb74  jnz     short loc_18001FBAA
0x18001fb76  mov     r15d, 2
0x18001fb7c  mov     edx, r15d; enum _WER_DUMP_TYPE
0x18001fb7f  mov     rcx, [rbx+8]; this
0x18001fb83  call    ?GetProcessDumpObject@CReport@@QEAAPEAVCProcessDump@@W4_WER_DUMP_TYPE@@@Z; CReport::GetProcessDumpObject(_WER_DUMP_TYPE)
0x18001fb88  cmp     dword ptr [rax], 0
0x18001fb8b  jz      short loc_18001FBA2
0x18001fb8d  mov     edx, r15d; enum _WER_DUMP_TYPE
0x18001fb90  mov     rcx, [rbx+8]; this
0x18001fb94  call    ?GetProcessDumpObject@CReport@@QEAAPEAVCProcessDump@@W4_WER_DUMP_TYPE@@@Z; CReport::GetProcessDumpObject(_WER_DUMP_TYPE)
0x18001fb99  test    byte ptr [rax+0B0h], 1
0x18001fba0  jnz     short loc_18001FBAA
0x18001fba2  mov     rcx, rbx; this
0x18001fba5  call    ?AddDesktopHeapDataForReport@CReportManager@@AEAAJXZ; CReportManager::AddDesktopHeapDataForReport(void)
0x18001fbaa  mov     edx, [rbx+0D8h]; unsigned int
0x18001fbb0  lea     rcx, [rsp+1520h+var_14D0]; this
0x18001fbb5  call    ?AddQueueDumps@CDataCollection@@QEAAJK@Z; CDataCollection::AddQueueDumps(ulong)
0x18001fbba  mov     rcx, rbx; this
0x18001fbbd  call    ?IsNativeDumpEnabled@CReportManager@@AEBA_NXZ; CReportManager::IsNativeDumpEnabled(void)
0x18001fbc2  test    al, al
0x18001fbc4  jz      short loc_18001FBD0
0x18001fbc6  xor     edx, edx
0x18001fbc8  mov     rcx, rbx
0x18001fbcb  call    ?ExternalCallbackDataRequestEnd@CReportManager@@AEAAHPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::ExternalCallbackDataRequestEnd(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001fbd0  cmp     edi, 0FFFFFFFFh
0x18001fbd3  jz      short loc_18001FBF2
0x18001fbd5  call    cs:__imp_GetCurrentThread
0x18001fbdc  nop     dword ptr [rax+rax+00h]
0x18001fbe1  mov     rcx, rax; hThread
0x18001fbe4  mov     edx, edi; nPriority
0x18001fbe6  call    cs:__imp_SetThreadPriority
0x18001fbed  nop     dword ptr [rax+rax+00h]
0x18001fbf2  mov     rcx, rbx; this
0x18001fbf5  call    ?AddTracingFile@CReportManager@@AEAAJXZ; CReportManager::AddTracingFile(void)
0x18001fbfa  lea     rdx, [rsp+1520h+lpMem]
0x18001fbff  mov     rcx, rbx
0x18001fc02  call    ?AddReportToQueueAsZip@CReportManager@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::AddReportToQueueAsZip(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001fc07  test    eax, eax
0x18001fc09  jns     short loc_18001FC47
0x18001fc0b  xor     edx, edx
0x18001fc0d  test    r14d, r14d
0x18001fc10  setz    dl
  ... truncated ...
```
