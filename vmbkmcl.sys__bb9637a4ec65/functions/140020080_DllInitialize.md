# DllInitialize

- ea: `0x140020080`
- end: `0x1400202a1`
- name: `DllInitialize`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x140006e60`
- `0x1400103b4`
- `0x140010ab8`
- `0x1400115cc`
- `0x140011ed0`
- `0x14001d780`
- `0x14001d814`
- `0x140020080`
- `0x1400202b8`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x14002022c`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14002022c`
- `ntoskrnl!KeInitializeEvent` at `0x140020170`
- `ntoskrnl!KeInitializeEvent` at `0x1400201b0`
- `ntoskrnl!KeInitializeEvent` at `0x1400201f4`
- `ntoskrnl!KeInitializeEvent` at `0x140020262`
- `ntoskrnl!KeInitializeEvent` at `0x140020170`
- `ntoskrnl!KeInitializeEvent` at `0x1400201b0`
- `ntoskrnl!KeInitializeEvent` at `0x1400201f4`
- `ntoskrnl!KeInitializeEvent` at `0x140020262`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020108`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020108`
- `HAL!KeQueryPerformanceCounter` at `0x140020204`
- `HAL!KeQueryPerformanceCounter` at `0x140020204`

## pseudocode

```c
__int64 __fastcall DllInitialize(const void **a1)
{
  int (__fastcall *SystemRoutineAddress)(__int64, union _LARGE_INTEGER *, __int64, _QWORD); // rax
  ULONG TimeIncrement; // eax
  struct _UNICODE_STRING SystemRoutineName; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING v6; // [rsp+40h] [rbp-10h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+78h] [rbp+28h] BYREF
  int v8; // [rsp+80h] [rbp+30h] BYREF

  *(_QWORD *)&v6.Length = 4194366;
  v6.Buffer = L"ForceNonIsolatedBounceBuffering";
  v8 = 0;
  wil_InitializeFeatureStaging();
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_VMBKmclDriverTraceGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  LOBYTE(PerformanceFrequency.LowPart) = 0;
  SystemRoutineName.Buffer = L"ZwQuerySystemInformation";
  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  SystemRoutineAddress = (int (__fastcall *)(__int64, union _LARGE_INTEGER *, __int64, _QWORD))MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress
    && SystemRoutineAddress(227, &PerformanceFrequency, 1, 0) >= 0
    && LOBYTE(PerformanceFrequency.LowPart) )
  {
    ExPoolZeroingNativelySupported = 1;
  }
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  KmclChannelListLock.Count = 1;
  KmclChannelListLock.Owner = 0;
  KmclChannelListLock.Contention = 0;
  KeInitializeEvent(&KmclChannelListLock.Event, SynchronizationEvent, 0);
  KmclProfilerListLock.Count = 1;
  qword_1400162A8 = (__int64)&KmclChannelList;
  KmclChannelList = (__int64)&KmclChannelList;
  KmclProfilerListLock.Owner = 0;
  KmclProfilerListLock.Contention = 0;
  KeInitializeEvent(&KmclProfilerListLock.Event, SynchronizationEvent, 0);
  PerformanceFrequency.QuadPart = 0;
  qword_140016248 = (__int64)&KmclProfilerList;
  KmclProfilerList = (__int64)&KmclProfilerList;
  KmclPerformanceCounterLock.Count = 1;
  KmclPerformanceCounterLock.Owner = 0;
  KmclPerformanceCounterLock.Contention = 0;
  KeInitializeEvent(&KmclPerformanceCounterLock.Event, SynchronizationEvent, 0);
  KeQueryPerformanceCounter(&PerformanceFrequency);
  KmclPerformanceCounterFrequency = PerformanceFrequency.QuadPart;
  InitializeTelemetryAssertsKM(a1);
  if ( !WPP_MAIN_CB.Queue.ListEntry.Blink )
  {
    TimeIncrement = KeQueryTimeIncrement();
    WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)(KmclCalibrateTsc(TimeIncrement, 0x989680 % TimeIncrement)
                                                             / (unsigned __int64)(0x989680 / TimeIncrement));
  }
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.DeviceExtension, NotificationEvent, 0);
  McGenEventRegister_EtwRegister();
  if ( (int)DvReadRegistryValueUINT32((struct _UNICODE_STRING *)a1, &v6, &v8) >= 0 )
    KmclForceNonIsolatedBounceBuffering = v8 != 0;
  return 0;
}

```

## disassembly

```asm
0x140020080  mov     [rsp-18h+arg_0], rbx
0x140020085  push    rbp
0x140020086  push    rsi
0x140020087  push    rdi
0x140020088  mov     rbp, rsp
0x14002008b  sub     rsp, 50h
0x14002008f  lea     rax, aForcenonisolat; "ForceNonIsolatedBounceBuffering"
0x140020096  mov     [rbp+var_10], 40003Eh
0x14002009e  xor     esi, esi
0x1400200a0  mov     [rbp+var_8], rax
0x1400200a4  mov     [rbp+arg_10], esi
0x1400200a7  mov     rdi, rcx
0x1400200aa  call    wil_InitializeFeatureStaging
0x1400200af  lea     rax, WPP_ThisDir_CTLGUID_VMBKmclDriverTraceGuid
0x1400200b6  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x1400200bd  lea     ebx, [rsi+1]
0x1400200c0  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400200c7  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x1400200ce  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x1400200d5  mov     cs:WPP_MAIN_CB.Timer, rbx
0x1400200dc  call    WppLoadTracingSupport
0x1400200e1  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x1400200e8  call    WppInitKm
0x1400200ed  lea     rax, aZwquerysystemi; "ZwQuerySystemInformation"
0x1400200f4  mov     byte ptr [rbp+PerformanceFrequency], sil
0x1400200f8  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x1400200fc  mov     [rbp+SystemRoutineName.Buffer], rax
0x140020100  mov     qword ptr [rbp+SystemRoutineName.Length], 320030h
0x140020108  call    cs:__imp_MmGetSystemRoutineAddress
0x14002010f  nop     dword ptr [rax+rax+00h]
0x140020114  test    rax, rax
0x140020117  jz      short loc_14002013D
0x140020119  xor     r9d, r9d
0x14002011c  lea     rdx, [rbp+PerformanceFrequency]
0x140020120  mov     r8d, ebx
0x140020123  mov     ecx, 0E3h
0x140020128  call    _guard_dispatch_icall
0x14002012d  test    eax, eax
0x14002012f  js      short loc_14002013D
0x140020131  cmp     byte ptr [rbp+PerformanceFrequency], sil
0x140020135  jz      short loc_14002013D
0x140020137  mov     cs:ExPoolZeroingNativelySupported, bl
0x14002013d  xor     r8d, r8d; State
0x140020140  mov     cs:ExDefaultNonPagedPoolType, 200h
0x14002014a  mov     edx, ebx; Type
0x14002014c  mov     cs:ExDefaultMdlProtection, 40000000h
0x140020156  lea     rcx, KmclChannelListLock.Event; Event
0x14002015d  mov     cs:KmclChannelListLock.Count, ebx
0x140020163  mov     cs:KmclChannelListLock.Owner, rsi
0x14002016a  mov     cs:KmclChannelListLock.Contention, esi
0x140020170  call    cs:__imp_KeInitializeEvent
0x140020177  nop     dword ptr [rax+rax+00h]
0x14002017c  lea     rax, KmclChannelList
0x140020183  mov     cs:KmclProfilerListLock.Count, ebx
0x140020189  xor     r8d, r8d; State
0x14002018c  mov     cs:qword_1400162A8, rax
0x140020193  mov     edx, ebx; Type
0x140020195  mov     cs:KmclChannelList, rax
0x14002019c  lea     rcx, KmclProfilerListLock.Event; Event
0x1400201a3  mov     cs:KmclProfilerListLock.Owner, rsi
0x1400201aa  mov     cs:KmclProfilerListLock.Contention, esi
0x1400201b0  call    cs:__imp_KeInitializeEvent
0x1400201b7  nop     dword ptr [rax+rax+00h]
0x1400201bc  lea     rax, KmclProfilerList
0x1400201c3  mov     qword ptr [rbp+PerformanceFrequency], rsi
0x1400201c7  xor     r8d, r8d; State
0x1400201ca  mov     cs:qword_140016248, rax
0x1400201d1  mov     edx, ebx; Type
0x1400201d3  mov     cs:KmclProfilerList, rax
0x1400201da  lea     rcx, KmclPerformanceCounterLock.Event; Event
0x1400201e1  mov     cs:KmclPerformanceCounterLock.Count, ebx
0x1400201e7  mov     cs:KmclPerformanceCounterLock.Owner, rsi
0x1400201ee  mov     cs:KmclPerformanceCounterLock.Contention, esi
0x1400201f4  call    cs:__imp_KeInitializeEvent
0x1400201fb  nop     dword ptr [rax+rax+00h]
0x140020200  lea     rcx, [rbp+PerformanceFrequency]; PerformanceFrequency
0x140020204  call    cs:__imp_KeQueryPerformanceCounter
0x14002020b  nop     dword ptr [rax+rax+00h]
0x140020210  mov     rax, qword ptr [rbp+PerformanceFrequency]
0x140020214  mov     rcx, rdi
0x140020217  mov     cs:KmclPerformanceCounterFrequency, rax
0x14002021e  call    InitializeTelemetryAssertsKM
0x140020223  cmp     qword ptr cs:WPP_MAIN_CB.Queue+8, rsi
0x14002022a  jnz     short loc_140020256
0x14002022c  call    cs:__imp_KeQueryTimeIncrement
0x140020233  nop     dword ptr [rax+rax+00h]
0x140020238  mov     ecx, eax
0x14002023a  xor     edx, edx
0x14002023c  mov     eax, 989680h
0x140020241  div     ecx
0x140020243  mov     ebx, eax
0x140020245  call    KmclCalibrateTsc
0x14002024a  xor     edx, edx
0x14002024c  div     rbx
0x14002024f  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x140020256  xor     r8d, r8d; State
0x140020259  lea     rcx, WPP_MAIN_CB.DeviceExtension; Event
0x140020260  xor     edx, edx; Type
0x140020262  call    cs:__imp_KeInitializeEvent
0x140020269  nop     dword ptr [rax+rax+00h]
0x14002026e  call    McGenEventRegister_EtwRegister
0x140020273  lea     r8, [rbp+arg_10]
0x140020277  mov     rcx, rdi
0x14002027a  lea     rdx, [rbp+var_10]
0x14002027e  call    DvReadRegistryValueUINT32
0x140020283  test    eax, eax
0x140020285  js      short loc_140020291
0x140020287  cmp     [rbp+arg_10], esi
0x14002028a  setnz   cs:KmclForceNonIsolatedBounceBuffering
0x140020291  mov     rbx, [rsp+50h+arg_0]
0x140020296  xor     eax, eax
0x140020298  add     rsp, 50h
0x14002029c  pop     rdi
0x14002029d  pop     rsi
0x14002029e  pop     rbp
0x14002029f  retn
```
