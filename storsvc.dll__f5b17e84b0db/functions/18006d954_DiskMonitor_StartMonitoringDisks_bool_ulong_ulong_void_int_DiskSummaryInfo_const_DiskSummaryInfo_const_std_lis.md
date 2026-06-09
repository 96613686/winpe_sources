# DiskMonitor::StartMonitoringDisks(bool,ulong,ulong,void (*)(int,DiskSummaryInfo const &,DiskSummaryInfo const &,std::list<DiskAnalysisResult,std::allocator<DiskAnalysisResult>> const &),void (*)(DiskAnalysisResult),void (*)(void),void (*)(void))

- ea: `0x18006d954`
- end: `0x18006db5f`
- name: `?StartMonitoringDisks@DiskMonitor@@QEAAX_NKKP6AXHAEBUDiskSummaryInfo@@1AEBV?$list@UDiskAnalysisResult@@V?$allocator@UDiskAnalysisResult@@@std@@@std@@@ZP6AXUDiskAnalysisResult@@@ZP6AXXZ6@Z`
- size: `523`
- prototype: `__int64 __fastcall(DiskMonitor *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180020140`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x18006c494`
- `0x18006caf8`
- `0x18006ccd0`
- `0x18006d954`
- `0x18006e040`
- `0x18006e0dc`
- `0x18006e11c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006dad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18006dad2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006da94`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006da94`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006dae5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006dae5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006db35`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006db35`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006daf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006daf9`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18006da6a`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18006da6a`

## pseudocode

```c
void __fastcall DiskMonitor::StartMonitoringDisks(DiskMonitor *this)
{
  __int128 v2; // xmm1
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  unsigned int v9; // eax
  unsigned int v10; // r8d
  __int64 v11; // r8
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v13; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v17[4]; // [rsp+B4h] [rbp-4Ch] BYREF
  int v18; // [rsp+B8h] [rbp-48h]
  GUID v19; // [rsp+C0h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  SystemTimeAsFileTime = 0;
  LODWORD(v15[0]) = 0;
  memset_0((char *)v15 + 4, 0, 0x7Cu);
  v2 = v15[1];
  *((_OWORD *)this + 7) = v15[0];
  *((_QWORD *)this + 10) = StorageService::DiskMonitoringPeriodicCallback;
  v3 = v15[2];
  *((_OWORD *)this + 8) = v2;
  *((_QWORD *)this + 13) = &StorageService::UsbDiskArrivalCallback;
  v4 = v15[3];
  *((_OWORD *)this + 9) = v3;
  *((_QWORD *)this + 11) = StorageService::StorageReserveMonitoringPeriodicCallback;
  v5 = v15[4];
  *((_OWORD *)this + 10) = v4;
  *((_BYTE *)this + 48) = 0;
  v6 = v15[5];
  *((_OWORD *)this + 11) = v5;
  *((_QWORD *)this + 12) = StorageService::StorageGrovelerCallback;
  v7 = v15[6];
  *((_OWORD *)this + 12) = v6;
  v16 = 416;
  v8 = v15[7];
  *((_OWORD *)this + 13) = v7;
  *((_OWORD *)this + 14) = v8;
  memset_0(v17, 0, 0x19Cu);
  v18 = 0;
  v19 = GUID_DEVINTERFACE_DISK;
  v9 = CM_Register_Notification(&v16, this, &DiskMonitor::DeviceNotifyCallback, (char *)this + 56);
  if ( v9 )
  {
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x6B, v10, (const char *)v9, SystemTimeAsFileTime.dwLowDateTime);
  }
  else
  {
    WaitForSingleObject(*((HANDLE *)this + 5), 0xFFFFFFFF);
    std::_Tree<std::_Tmap_traits<std::wstring,DiskInfo *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DiskInfo *>>,0>>::clear((char *)this + 24);
    std::_Tree<std::_Tmap_traits<int,DiskInfo *,std::less<int>,std::allocator<std::pair<int const,DiskInfo *>>,0>>::clear((char *)this + 8);
    DiskMonitor::EnumerateExistingDisks(this);
    DiskMonitor::EnumerateVolumes(this);
    LOBYTE(v11) = 1;
    DiskMonitor::AccumulateDiskStatistics(this, (char *)this + 112, v11, 0);
    ReleaseMutex(*((HANDLE *)this + 5));
    ThreadpoolTimer = CreateThreadpoolTimer(DiskMonitor::PeriodicCallback, this, 0);
    *((_QWORD *)this + 9) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v13 = *(_QWORD *)&SystemTimeAsFileTime + 36000000000LL;
      SystemTimeAsFileTime.dwLowDateTime += 1640261632;
      SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v13);
      SetThreadpoolTimer(*((PTP_TIMER *)this + 9), &SystemTimeAsFileTime, 0x5265C00u, 0xEA60u);
    }
  }
}

```

## disassembly

```asm
0x18006d954  mov     [rsp-8+arg_8], rbx
0x18006d959  mov     [rsp-8+arg_10], rdi
0x18006d95e  push    rbp
0x18006d95f  lea     rbp, [rsp-160h]
0x18006d967  sub     rsp, 260h
0x18006d96e  mov     rax, cs:__security_cookie
0x18006d975  xor     rax, rsp
0x18006d978  mov     [rbp+160h+var_10], rax
0x18006d97f  xor     edx, edx; Val
0x18006d981  mov     qword ptr [rsp+260h+SystemTimeAsFileTime.dwLowDateTime], 0; unsigned int
0x18006d98a  mov     rbx, rcx
0x18006d98d  mov     dword ptr [rsp+260h+var_230], 0
0x18006d995  lea     rcx, [rsp+260h+var_230+4]; void *
0x18006d99a  lea     r8d, [rdx+7Ch]; Size
0x18006d99e  call    memset_0
0x18006d9a3  movaps  xmm0, [rsp+260h+var_230]
0x18006d9a8  lea     rax, ?DiskMonitoringPeriodicCallback@StorageService@@KAXHAEBUDiskSummaryInfo@@0AEBV?$list@UDiskAnalysisResult@@V?$allocator@UDiskAnalysisResult@@@std@@@std@@@Z; StorageService::DiskMonitoringPeriodicCallback(int,DiskSummaryInfo const &,DiskSummaryInfo const &,std::list<DiskAnalysisResult> const &)
0x18006d9af  movaps  xmm1, [rsp+260h+var_220]
0x18006d9b4  lea     rcx, [rbp+160h+var_1AC]; void *
0x18006d9b8  movups  xmmword ptr [rbx+70h], xmm0
0x18006d9bc  xor     edx, edx; Val
0x18006d9be  mov     [rbx+50h], rax
0x18006d9c2  movaps  xmm0, [rsp+260h+var_210]
0x18006d9c7  lea     rax, ?UsbDiskArrivalCallback@StorageService@@KAXUDiskAnalysisResult@@@Z; StorageService::UsbDiskArrivalCallback(DiskAnalysisResult)
0x18006d9ce  movups  xmmword ptr [rbx+80h], xmm1
0x18006d9d5  mov     r8d, 19Ch; Size
0x18006d9db  mov     [rbx+68h], rax
0x18006d9df  movaps  xmm1, [rsp+260h+var_200]
0x18006d9e4  lea     rax, ?StorageReserveMonitoringPeriodicCallback@StorageService@@KAXXZ; StorageService::StorageReserveMonitoringPeriodicCallback(void)
0x18006d9eb  movups  xmmword ptr [rbx+90h], xmm0
0x18006d9f2  mov     [rbx+58h], rax
0x18006d9f6  lea     rax, ?StorageGrovelerCallback@StorageService@@KAXXZ; StorageService::StorageGrovelerCallback(void)
0x18006d9fd  movaps  xmm0, [rsp+260h+var_1F0]
0x18006da02  movups  xmmword ptr [rbx+0A0h], xmm1
0x18006da09  mov     byte ptr [rbx+30h], 0
0x18006da0d  movaps  xmm1, [rbp+160h+var_1E0]
0x18006da11  movups  xmmword ptr [rbx+0B0h], xmm0
0x18006da18  mov     [rbx+60h], rax
0x18006da1c  movaps  xmm0, [rbp+160h+var_1D0]
0x18006da20  movups  xmmword ptr [rbx+0C0h], xmm1
0x18006da27  mov     [rbp+160h+var_1B0], 1A0h
0x18006da2e  movaps  xmm1, [rbp+160h+var_1C0]
0x18006da32  movups  xmmword ptr [rbx+0D0h], xmm0
0x18006da39  movups  xmmword ptr [rbx+0E0h], xmm1
0x18006da40  call    memset_0
0x18006da45  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_DISK.Data1
0x18006da4c  lea     r9, [rbx+38h]
0x18006da50  mov     [rbp+160h+var_1A8], 0
0x18006da57  lea     r8, ?DeviceNotifyCallback@DiskMonitor@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; DiskMonitor::DeviceNotifyCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18006da5e  mov     rdx, rbx
0x18006da61  lea     rcx, [rbp+160h+var_1B0]
0x18006da65  movdqu  [rbp+160h+var_1A0], xmm0
0x18006da6a  call    cs:__imp_CM_Register_Notification
0x18006da70  test    eax, eax
0x18006da72  jz      short loc_18006DA8D
0x18006da74  mov     rcx, [rbp+168h]; this
0x18006da7b  mov     r9d, eax; char *
0x18006da7e  mov     edx, 6Bh ; 'k'; void *
0x18006da83  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18006da88  jmp     loc_18006DB3B
0x18006da8d  mov     rcx, [rbx+28h]; hHandle
0x18006da91  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006da94  call    cs:__imp_WaitForSingleObject
0x18006da9a  lea     rcx, [rbx+18h]
0x18006da9e  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVDiskInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVDiskInfo@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,DiskInfo *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DiskInfo *>>,0>>::clear(void)
0x18006daa3  lea     rcx, [rbx+8]
0x18006daa7  call    ?clear@?$_Tree@V?$_Tmap_traits@HPEAVDiskInfo@@U?$less@H@std@@V?$allocator@U?$pair@$$CBHPEAVDiskInfo@@@std@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<int,DiskInfo *,std::less<int>,std::allocator<std::pair<int const,DiskInfo *>>,0>>::clear(void)
0x18006daac  mov     rcx, rbx; this
0x18006daaf  call    ?EnumerateExistingDisks@DiskMonitor@@QEAAXXZ; DiskMonitor::EnumerateExistingDisks(void)
0x18006dab4  mov     rcx, rbx; this
0x18006dab7  call    ?EnumerateVolumes@DiskMonitor@@QEAAXXZ; DiskMonitor::EnumerateVolumes(void)
0x18006dabc  xor     r9d, r9d
0x18006dabf  lea     rdx, [rbx+70h]
0x18006dac3  mov     r8b, 1
0x18006dac6  mov     rcx, rbx
0x18006dac9  call    ?AccumulateDiskStatistics@DiskMonitor@@AEAAXAEAUDiskSummaryInfo@@_NPEAV?$list@UDiskAnalysisResult@@V?$allocator@UDiskAnalysisResult@@@std@@@std@@@Z; DiskMonitor::AccumulateDiskStatistics(DiskSummaryInfo &,bool,std::list<DiskAnalysisResult> *)
0x18006dace  mov     rcx, [rbx+28h]; hMutex
0x18006dad2  call    cs:__imp_ReleaseMutex
0x18006dad8  xor     r8d, r8d; pcbe
0x18006dadb  lea     rcx, ?PeriodicCallback@DiskMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006dae2  mov     rdx, rbx; pv
0x18006dae5  call    cs:__imp_CreateThreadpoolTimer
0x18006daeb  mov     [rbx+48h], rax
0x18006daef  test    rax, rax
0x18006daf2  jz      short loc_18006DB3B
0x18006daf4  lea     rcx, [rsp+260h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006daf9  call    cs:__imp_GetSystemTimeAsFileTime
0x18006daff  mov     rax, qword ptr [rsp+260h+SystemTimeAsFileTime.dwLowDateTime]
0x18006db04  lea     rdx, [rsp+260h+SystemTimeAsFileTime]; pftDueTime
0x18006db09  mov     rcx, 861C46800h
0x18006db13  mov     r9d, 0EA60h; msWindowLength
0x18006db19  add     rax, rcx
0x18006db1c  mov     r8d, 5265C00h; msPeriod
0x18006db22  mov     rcx, rax
0x18006db25  mov     [rsp+260h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18006db29  shr     rcx, 20h
0x18006db2d  mov     [rsp+260h+SystemTimeAsFileTime.dwHighDateTime], ecx
0x18006db31  mov     rcx, [rbx+48h]; pti
0x18006db35  call    cs:__imp_SetThreadpoolTimer
0x18006db3b  mov     rcx, [rbp+160h+var_10]
0x18006db42  xor     rcx, rsp; StackCookie
0x18006db45  call    __security_check_cookie
0x18006db4a  lea     r11, [rsp+260h+var_s0]
0x18006db52  mov     rbx, [r11+18h]
0x18006db56  mov     rdi, [r11+20h]
0x18006db5a  mov     rsp, r11
0x18006db5d  pop     rbp
0x18006db5e  retn
```
