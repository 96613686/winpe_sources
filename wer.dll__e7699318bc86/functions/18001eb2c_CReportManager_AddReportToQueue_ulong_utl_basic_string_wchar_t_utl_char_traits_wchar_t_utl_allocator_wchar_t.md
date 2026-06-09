# CReportManager::AddReportToQueue(ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18001eb2c`
- end: `0x18001f0cf`
- name: `?AddReportToQueue@CReportManager@@AEAAJKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1443`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, service_task`

## callers

- `0x18001e870`

## callees

- `0x180004bb4`
- `0x180006c34`
- `0x180009590`
- `0x180009ad4`
- `0x18000bc10`
- `0x18000dad0`
- `0x18001b280`
- `0x18001eb2c`
- `0x18001f128`
- `0x18001f274`
- `0x18001fe24`
- `0x180026ac8`
- `0x180026ea8`
- `0x18002b748`
- `0x180031b84`
- `0x180031bfc`
- `0x180035738`
- `0x18003e704`
- `0x180041aac`
- `0x18004a780`
- `0x18004afd4`
- `0x18004bf7c`
- `0x18004c3a8`
- `0x18004d478`
- `0x180050db0`
- `0x180071160`
- `0x180072a98`
- `0x18007969c`
- `0x180079abc`
- `0x18007b104`
- `0x18007d028`
- `0x1800aa000`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f092`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f092`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eef8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ef10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001efcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eef8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ef10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001efcb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001ef1c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001efd6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001ef1c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001efd6`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001ef01`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001ef01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ee5a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ee5a`

## pseudocode

```c
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
  _QWORD v29[4]; // [rsp+68h] [rbp-98h] BYREF
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
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
      WPP_SF_(*((_QWORD *)v2 + 2), v5, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
      goto LABEL_83;
    }
    goto LABEL_83;
  }
  if ( *(char *)(v3 + 6616) < 0 )
  {
    if ( v2 != (wchar_t *)&WPP_GLOBAL_Control && (v2[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)v2 + 2), 238, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
    started = 1769477;
    goto LABEL_83;
  }
  started = CReportManager::StartReporting((CReportManager *)a1);
  if ( started < 0 )
    goto LABEL_83;
  if ( (unsigned int)CReport::IsSecondaryDataEnabled(*(CReport **)(a1 + 8)) )
  {
    IsSecondLevelDataThrottled = 0;
    CReportManager::AddPreConfiguredSecondLevelData((CSettings **)a1);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
  }
  v12 = *(CReport **)(a1 + 8);
  if ( *((_DWORD *)v12 + 1468) != 4 )
  {
    v13 = CReport::RemoveAllFiles(v12);
    if ( v13 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 243, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        242,
        WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
        (unsigned int)v13);
    }
  }
LABEL_47:
  if ( v7 || IsSecondLevelDataThrottled )
  {
LABEL_73:
    CReportManager::AddTracingFile((CReportManager *)a1);
    if ( (int)CReportManager::AddReportToQueueAsZip(a1, (__int64)lpMem) >= 0
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
          WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
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
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, (unsigned int)inited);
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
        WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
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
      CDataCollection::AddQueueDumps((CReport **)&v27, *(_DWORD *)(a1 + 216));
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
0x18001eb2c  push    rbp
0x18001eb2e  push    rbx
0x18001eb2f  push    rdi
0x18001eb30  push    r13
0x18001eb32  push    r14
0x18001eb34  push    r15
0x18001eb36  lea     rbp, [rsp-13F8h]
0x18001eb3e  mov     eax, 14F8h
0x18001eb43  call    _alloca_probe
0x18001eb48  sub     rsp, rax
0x18001eb4b  mov     rax, cs:__security_cookie
0x18001eb52  xor     rax, rsp
0x18001eb55  mov     [rbp+1420h+var_40], rax
0x18001eb5c  mov     rbx, rcx
0x18001eb5f  lea     rcx, [rbp+1420h+var_1490]; this
0x18001eb63  call    ??0CReportStore@@QEAA@XZ; CReportStore::CReportStore(void)
0x18001eb68  lea     rax, ??_7CReportQueue@@6B@; const CReportQueue::`vftable'
0x18001eb6f  mov     [rbp+1420h+var_1490], rax
0x18001eb73  lea     rcx, [rsp+1520h+var_14B8]; void *
0x18001eb78  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001eb7d  xorps   xmm0, xmm0
0x18001eb80  movdqa  [rsp+1520h+var_14D0], xmm0
0x18001eb86  mov     [rsp+1520h+var_14C0], 0
0x18001eb8f  mov     [rbp+1420h+var_1498], 0
0x18001eb96  lea     rcx, [rsp+1520h+lpMem]; void *
0x18001eb9b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001eba0  nop
0x18001eba1  mov     qword ptr [rsp+1520h+var_14F8], 0
0x18001ebaa  lea     r13, WPP_GLOBAL_Control
0x18001ebb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebb8  cmp     rcx, r13
0x18001ebbb  jz      short loc_18001EBDF
0x18001ebbd  test    byte ptr [rcx+1Ch], 4
0x18001ebc1  jz      short loc_18001EBDF
0x18001ebc3  mov     edx, 0ECh
0x18001ebc8  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18001ebcf  mov     rcx, [rcx+10h]
0x18001ebd3  call    WPP_SF_
0x18001ebd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebdf  mov     rax, [rbx+8]
0x18001ebe3  test    rax, rax
0x18001ebe6  jnz     short loc_18001EC1A
0x18001ebe8  mov     edi, 80070057h
0x18001ebed  cmp     rcx, r13
0x18001ebf0  jz      loc_18001F07A
0x18001ebf6  test    byte ptr [rcx+1Ch], 1
0x18001ebfa  jz      loc_18001F07A
0x18001ec00  mov     edx, 0EDh
0x18001ec05  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18001ec0c  mov     rcx, [rcx+10h]
0x18001ec10  call    WPP_SF_
0x18001ec15  jmp     loc_18001F07A
0x18001ec1a  test    byte ptr [rax+19D8h], 80h
0x18001ec21  jz      short loc_18001EC4D
0x18001ec23  cmp     rcx, r13
0x18001ec26  jz      short loc_18001EC43
0x18001ec28  test    byte ptr [rcx+1Ch], 4
0x18001ec2c  jz      short loc_18001EC43
0x18001ec2e  mov     edx, 0EEh
0x18001ec33  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18001ec3a  mov     rcx, [rcx+10h]
0x18001ec3e  call    WPP_SF_
0x18001ec43  mov     edi, 1B0005h
0x18001ec48  jmp     loc_18001F07A
0x18001ec4d  mov     rcx, rbx; this
0x18001ec50  call    ?StartReporting@CReportManager@@AEAAJXZ; CReportManager::StartReporting(void)
0x18001ec55  mov     edi, eax
0x18001ec57  test    eax, eax
0x18001ec59  js      loc_18001F07A
0x18001ec5f  mov     rcx, [rbx+8]; this
0x18001ec63  call    ?IsSecondaryDataEnabled@CReport@@QEBAHXZ; CReport::IsSecondaryDataEnabled(void)
0x18001ec68  test    eax, eax
0x18001ec6a  jnz     short loc_18001EC72
0x18001ec6c  lea     r14d, [rax+1]
0x18001ec70  jmp     short loc_18001EC7D
0x18001ec72  xor     r14d, r14d
0x18001ec75  mov     rcx, rbx; this
0x18001ec78  call    ?AddPreConfiguredSecondLevelData@CReportManager@@AEAAJXZ; CReportManager::AddPreConfiguredSecondLevelData(void)
0x18001ec7d  mov     [rsp+1520h+var_1500], 0
0x18001ec85  mov     r8d, r14d; int
0x18001ec88  lea     rdx, [rsp+1520h+var_1500]; int *
0x18001ec8d  mov     rcx, rbx; this
0x18001ec90  call    ?ExternalCallbackBeforeQueue@CReportManager@@QEAAHPEAHH@Z; CReportManager::ExternalCallbackBeforeQueue(int *,int)
0x18001ec95  mov     r15d, eax
0x18001ec98  cmp     [rsp+1520h+var_1500], 0
0x18001ec9d  jz      short loc_18001ECDC
0x18001ec9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eca6  cmp     rcx, r13
0x18001eca9  jz      short loc_18001ECC6
0x18001ecab  test    byte ptr [rcx+1Ch], 4
0x18001ecaf  jz      short loc_18001ECC6
0x18001ecb1  mov     edx, 0EFh
0x18001ecb6  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18001ecbd  mov     rcx, [rcx+10h]
0x18001ecc1  call    WPP_SF_
0x18001ecc6  mov     rax, [rbx+8]
0x18001ecca  bts     dword ptr [rax+1748h], 16h
0x18001ecd2  mov     edi, 801B8001h
0x18001ecd7  jmp     loc_18001F07A
0x18001ecdc  mov     rcx, [rbx+8]; this
0x18001ece0  call    ?IsThrottled@CReport@@QEAAHXZ; CReport::IsThrottled(void)
0x18001ece5  test    eax, eax
0x18001ece7  jz      short loc_18001ECFF
0x18001ece9  mov     rax, [rbx+8]
0x18001eced  bts     dword ptr [rax+1748h], 0Dh
0x18001ecf5  mov     edi, 1B000Bh
0x18001ecfa  jmp     loc_18001F07A
0x18001ecff  test    r14d, r14d
0x18001ed02  jnz     short loc_18001ED24
0x18001ed04  lea     edx, [r14+1]; int
0x18001ed08  mov     rcx, [rbx+8]; this
0x18001ed0c  call    ?IsSecondLevelDataThrottled@CReport@@QEAAHH@Z; CReport::IsSecondLevelDataThrottled(int)
0x18001ed11  mov     r14d, eax
0x18001ed14  test    eax, eax
0x18001ed16  jz      short loc_18001ED24
0x18001ed18  mov     rcx, [rbx+8]
0x18001ed1c  bts     dword ptr [rcx+1748h], 0Ch
0x18001ed24  lea     rcx, [rbp+1420h+var_1490]; this
0x18001ed28  call    ?InitMachineStore@CReportQueue@@UEAAJXZ; CReportQueue::InitMachineStore(void)
0x18001ed2d  mov     edi, eax
0x18001ed2f  test    eax, eax
0x18001ed31  jns     short loc_18001ED6A
0x18001ed33  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed3a  cmp     rcx, r13
0x18001ed3d  jz      loc_18001F07A
0x18001ed43  test    byte ptr [rcx+1Ch], 1
0x18001ed47  jz      loc_18001F07A
0x18001ed4d  mov     edx, 0F0h
0x18001ed52  mov     r9d, eax
0x18001ed55  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18001ed5c  mov     rcx, [rcx+10h]
0x18001ed60  call    WPP_SF_d
0x18001ed65  jmp     loc_18001F07A
0x18001ed6a  test    r14d, r14d
0x18001ed6d  jnz     short loc_18001EDDF
0x18001ed6f  lea     rdx, [rsp+1520h+var_14F8]; union _ULARGE_INTEGER *
0x18001ed74  lea     rcx, [rbp+1420h+var_1490]; this
0x18001ed78  call    ?GetFreeDiskSpace@CReportStore@@QEAAJPEAT_ULARGE_INTEGER@@@Z; CReportStore::GetFreeDiskSpace(_ULARGE_INTEGER *)
0x18001ed7d  test    eax, eax
0x18001ed7f  js      loc_18001EE48
0x18001ed85  mov     rcx, [rbx+60h]
0x18001ed89  add     rcx, 0AF8h; this
0x18001ed90  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18001ed95  mov     ecx, eax
0x18001ed97  shl     rcx, 14h
0x18001ed9b  cmp     qword ptr [rsp+1520h+var_14F8], rcx
0x18001eda0  jnb     loc_18001EE48
0x18001eda6  mov     r14d, 1
0x18001edac  mov     rax, [rbx+8]
0x18001edb0  bts     dword ptr [rax+1748h], 15h
0x18001edb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edbf  cmp     rcx, r13
0x18001edc2  jz      short loc_18001EDDF
0x18001edc4  test    byte ptr [rcx+1Ch], 4
0x18001edc8  jz      short loc_18001EDDF
0x18001edca  mov     edx, 0F1h
0x18001edcf  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18001edd6  mov     rcx, [rcx+10h]
0x18001edda  call    WPP_SF_
0x18001eddf  mov     rcx, [rbx+8]; this
0x18001ede3  cmp     dword ptr [rcx+16F0h], 4
0x18001edea  jz      short loc_18001EE48
0x18001edec  call    ?RemoveAllFiles@CReport@@QEAAJXZ; CReport::RemoveAllFiles(void)
0x18001edf1  test    eax, eax
0x18001edf3  jns     short loc_18001EE21
0x18001edf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edfc  cmp     rcx, r13
0x18001edff  jz      short loc_18001EE48
0x18001ee01  test    byte ptr [rcx+1Ch], 1
0x18001ee05  jz      short loc_18001EE48
0x18001ee07  mov     edx, 0F2h
0x18001ee0c  mov     r9d, eax
0x18001ee0f  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18001ee16  mov     rcx, [rcx+10h]
0x18001ee1a  call    WPP_SF_d
0x18001ee1f  jmp     short loc_18001EE48
0x18001ee21  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee28  cmp     rcx, r13
0x18001ee2b  jz      short loc_18001EE48
0x18001ee2d  test    byte ptr [rcx+1Ch], 4
0x18001ee31  jz      short loc_18001EE48
0x18001ee33  mov     edx, 0F3h
0x18001ee38  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18001ee3f  mov     rcx, [rcx+10h]
0x18001ee43  call    WPP_SF_
0x18001ee48  test    r15d, r15d
0x18001ee4b  jnz     loc_18001EFDC
0x18001ee51  test    r14d, r14d
0x18001ee54  jnz     loc_18001EFDC
0x18001ee5a  call    cs:__imp_GetTickCount
0x18001ee60  mov     r9, [rbx+108h]; void *
0x18001ee67  mov     r8, [rbx]; struct CReportHandleInstance *
0x18001ee6a  mov     rdx, [rbx+8]; struct CReport *
0x18001ee6e  lea     rcx, [rsp+1520h+var_14D0]; this
0x18001ee73  call    ?Initialize@CDataCollection@@QEAAJPEAVCReport@@PEAVCReportHandleInstance@@PEAX@Z; CDataCollection::Initialize(CReport *,CReportHandleInstance *,void *)
0x18001ee78  mov     edi, eax
0x18001ee7a  test    eax, eax
0x18001ee7c  jns     short loc_18001EEAF
0x18001ee7e  mov     rcx, [rbx+8]; this
0x18001ee82  call    ?DumpsRequested@CReport@@QEAAHXZ; CReport::DumpsRequested(void)
0x18001ee87  test    eax, eax
0x18001ee89  jz      short loc_18001EEE7
0x18001ee8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee92  cmp     rcx, r13
0x18001ee95  jz      loc_18001F07A
0x18001ee9b  test    byte ptr [rcx+1Ch], 1
0x18001ee9f  jz      loc_18001F07A
0x18001eea5  mov     edx, 0F4h
0x18001eeaa  jmp     loc_18001EC05
0x18001eeaf  lea     rcx, [rsp+1520h+var_14D0]; this
0x18001eeb4  call    ?AddReportMetadata@CDataCollection@@QEAAJXZ; CDataCollection::AddReportMetadata(void)
0x18001eeb9  test    eax, eax
0x18001eebb  jns     short loc_18001EEE7
0x18001eebd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eec4  cmp     rcx, r13
0x18001eec7  jz      short loc_18001EEE7
0x18001eec9  test    byte ptr [rcx+1Ch], 2
0x18001eecd  jz      short loc_18001EEE7
0x18001eecf  mov     edx, 0F5h
0x18001eed4  mov     r9d, eax
0x18001eed7  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18001eede  mov     rcx, [rcx+10h]
0x18001eee2  call    WPP_SF_d
0x18001eee7  mov     rcx, [rbx+8]; this
0x18001eeeb  call    ?DumpsRequested@CReport@@QEAAHXZ; CReport::DumpsRequested(void)
0x18001eef0  test    eax, eax
0x18001eef2  jz      loc_18001EFDC
0x18001eef8  call    cs:__imp_GetCurrentThread
0x18001eefe  mov     rcx, rax; hThread
0x18001ef01  call    cs:__imp_GetThreadPriority
0x18001ef07  mov     edi, eax
0x18001ef09  cmp     eax, 7FFFFFFFh
0x18001ef0e  jz      short loc_18001EF22
0x18001ef10  call    cs:__imp_GetCurrentThread
0x18001ef16  mov     rcx, rax; hThread
0x18001ef19  or      edx, 0FFFFFFFFh; nPriority
0x18001ef1c  call    cs:__imp_SetThreadPriority
0x18001ef22  cmp     dword ptr [rbx+0C8h], 0
0x18001ef29  jz      short loc_18001EFA0
0x18001ef2b  mov     rcx, [rbx+8]; this
0x18001ef2f  cmp     dword ptr [rcx+16F0h], 3
0x18001ef36  jz      short loc_18001EF44
0x18001ef38  test    dword ptr [rcx+19D8h], 80000h
0x18001ef42  jz      short loc_18001EFA0
0x18001ef44  mov     r15d, 4
0x18001ef4a  mov     edx, r15d; enum _WER_DUMP_TYPE
0x18001ef4d  call    ?GetProcessDumpObject@CReport@@QEAAPEAVCProcessDump@@W4_WER_DUMP_TYPE@@@Z; CReport::GetProcessDumpObject(_WER_DUMP_TYPE)
0x18001ef52  cmp     dword ptr [rax], 0
0x18001ef55  jz      short loc_18001EF6C
0x18001ef57  mov     edx, r15d; enum _WER_DUMP_TYPE
0x18001ef5a  mov     rcx, [rbx+8]; this
0x18001ef5e  call    ?GetProcessDumpObject@CReport@@QEAAPEAVCProcessDump@@W4_WER_DUMP_TYPE@@@Z; CReport::GetProcessDumpObject(_WER_DUMP_TYPE)
0x18001ef63  test    byte ptr [rax+0B0h], 1
0x18001ef6a  jnz     short loc_18001EFA0
0x18001ef6c  mov     r15d, 2
0x18001ef72  mov     edx, r15d; enum _WER_DUMP_TYPE
0x18001ef75  mov     rcx, [rbx+8]; this
0x18001ef79  call    ?GetProcessDumpObject@CReport@@QEAAPEAVCProcessDump@@W4_WER_DUMP_TYPE@@@Z; CReport::GetProcessDumpObject(_WER_DUMP_TYPE)
0x18001ef7e  cmp     dword ptr [rax], 0
0x18001ef81  jz      short loc_18001EF98
0x18001ef83  mov     edx, r15d; enum _WER_DUMP_TYPE
0x18001ef86  mov     rcx, [rbx+8]; this
0x18001ef8a  call    ?GetProcessDumpObject@CReport@@QEAAPEAVCProcessDump@@W4_WER_DUMP_TYPE@@@Z; CReport::GetProcessDumpObject(_WER_DUMP_TYPE)
0x18001ef8f  test    byte ptr [rax+0B0h], 1
0x18001ef96  jnz     short loc_18001EFA0
0x18001ef98  mov     rcx, rbx; this
0x18001ef9b  call    ?AddDesktopHeapDataForReport@CReportManager@@AEAAJXZ; CReportManager::AddDesktopHeapDataForReport(void)
0x18001efa0  mov     edx, [rbx+0D8h]; unsigned int
0x18001efa6  lea     rcx, [rsp+1520h+var_14D0]; this
0x18001efab  call    ?AddQueueDumps@CDataCollection@@QEAAJK@Z; CDataCollection::AddQueueDumps(ulong)
0x18001efb0  mov     rcx, rbx; this
0x18001efb3  call    ?IsNativeDumpEnabled@CReportManager@@AEBA_NXZ; CReportManager::IsNativeDumpEnabled(void)
0x18001efb8  test    al, al
0x18001efba  jz      short loc_18001EFC6
0x18001efbc  xor     edx, edx
0x18001efbe  mov     rcx, rbx
0x18001efc1  call    ?ExternalCallbackDataRequestEnd@CReportManager@@AEAAHPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::ExternalCallbackDataRequestEnd(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001efc6  cmp     edi, 0FFFFFFFFh
0x18001efc9  jz      short loc_18001EFDC
0x18001efcb  call    cs:__imp_GetCurrentThread
0x18001efd1  mov     rcx, rax; hThread
0x18001efd4  mov     edx, edi; nPriority
0x18001efd6  call    cs:__imp_SetThreadPriority
0x18001efdc  mov     rcx, rbx; this
0x18001efdf  call    ?AddTracingFile@CReportManager@@AEAAJXZ; CReportManager::AddTracingFile(void)
0x18001efe4  lea     rdx, [rsp+1520h+lpMem]
0x18001efe9  mov     rcx, rbx
0x18001efec  call    ?AddReportToQueueAsZip@CReportManager@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::AddReportToQueueAsZip(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001eff1  test    eax, eax
0x18001eff3  jns     short loc_18001F031
0x18001eff5  xor     edx, edx
0x18001eff7  test    r14d, r14d
0x18001effa  setz    dl
0x18001effd  lea     r9, [rsp+1520h+lpMem]
0x18001f002  mov     r8, [rbx+8]
0x18001f006  lea     rcx, [rbp+1420h+var_1490]
0x18001f00a  call    ?AddReportToStore@CReportStore@@QEAAJHPEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::AddReportToStore(int,CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001f00f  mov     edi, eax
0x18001f011  test    eax, eax
0x18001f013  jns     short loc_18001F031
  ... truncated ...
```
