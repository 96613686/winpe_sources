# UdfInitializeGlobalData

- ea: `0x14005d4f4`
- end: `0x14005da10`
- name: `UdfInitializeGlobalData`
- size: `1308`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14005d078`

## callees

- `0x1400041e0`
- `0x14001bc30`
- `0x14001c080`
- `0x140038a68`
- `0x14005d350`
- `0x14005d4f4`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14005d6a4`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005d6a4`
- `ntoskrnl!KeInitializeEvent` at `0x14005d73c`
- `ntoskrnl!KeInitializeEvent` at `0x14005d73c`
- `ntoskrnl!FsRtlMdlReadCompleteDev` at `0x14005d63a`
- `ntoskrnl!FsRtlMdlWriteCompleteDev` at `0x14005d656`
- `ntoskrnl!MmQuerySystemSize` at `0x14005d796`
- `ntoskrnl!MmQuerySystemSize` at `0x14005d796`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005d81c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005d84f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005d87e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005d81c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005d84f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14005d87e`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d8b4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d8e3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d916`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d949`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d97c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d8b4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d8e3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d916`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d949`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14005d97c`
- `ntoskrnl!RtlGetVersion` at `0x14005d9c3`
- `ntoskrnl!RtlGetVersion` at `0x14005d9c3`

## pseudocode

```c
char __fastcall UdfInitializeGlobalData(
        struct _DRIVER_OBJECT *a1,
        struct _DEVICE_OBJECT *a2,
        struct _DEVICE_OBJECT *a3)
{
  MM_SYSTEMSIZE SystemSize; // eax
  __int64 v7; // rcx
  char result; // al
  __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+48h] [rbp-B8h]
  _BYTE VersionInformation[284]; // [rsp+50h] [rbp-B0h] BYREF

  memset(VersionInformation, 0, sizeof(VersionInformation));
  memset(&WPP_MAIN_CB.DeviceExtension, 0, 0xE0u);
  LODWORD(WPP_MAIN_CB.DeviceExtension) = 224;
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = UdfFastIoCheckIfPossible;
  *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement = 0;
  WPP_MAIN_CB.Queue.ListEntry.Flink = (struct _LIST_ENTRY *)UdfPrepareMdlWrite;
  WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)UdfPrepareMdlWrite;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = UdfFastQueryBasicInfo;
  WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = (PDRIVER_CONTROL)UdfFastQueryStdInfo;
  WPP_MAIN_CB.Queue.Wcb.DeviceContext = UdfFastLock;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = UdfFastUnlockSingle;
  WPP_MAIN_CB.Queue.Wcb.DeviceObject = UdfFastUnlockAll;
  WPP_MAIN_CB.Queue.Wcb.CurrentIrp = UdfFastUnlockAllByKey;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink = (struct _LIST_ENTRY *)UdfFastQueryNetworkInfo;
  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = UdfReleaseForCreateSection;
  WPP_MAIN_CB.DeviceQueue.Lock = (KSPIN_LOCK)UdfAcquireForModWrite;
  WPP_MAIN_CB.SecurityDescriptor = UdfAcquireForCcFlush;
  *(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock = UdfReleaseForCcFlush;
  WPP_MAIN_CB.DeviceQueue.1 = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)UdfPrepareMdlWrite;
  *(_QWORD *)&WPP_MAIN_CB.Dpc.TargetInfoAsUlong = FsRtlMdlReadCompleteDev;
  WPP_MAIN_CB.Dpc.DpcListEntry.Next = (struct _SINGLE_LIST_ENTRY *)UdfPrepareMdlWrite;
  WPP_MAIN_CB.Dpc.ProcessorHistory = (KAFFINITY)FsRtlMdlWriteCompleteDev;
  memset(&UdfData, 0, 0x180u);
  UdfData = 25168177;
  qword_140025B28 = (__int64)&qword_140025B20;
  qword_140025B20 = (__int64)&qword_140025B20;
  DriverObject = a1;
  qword_140025B10 = a2;
  DeviceObject = a3;
  ExInitializeResourceLite(&Resource);
  FastMutex.Owner = 0;
  Callbacks.AcquireForLazyWrite = (PACQUIRE_FOR_LAZY_WRITE)&UdfAcquireForCacheWrite;
  qword_140025C40 = (__int64)UdfNoopAcquire;
  Callbacks.ReleaseFromLazyWrite = (PRELEASE_FROM_LAZY_WRITE)UdfReleaseFromCacheWrite;
  qword_140025C50 = (__int64)UdfNoopAcquire;
  Callbacks.AcquireForReadAhead = (PACQUIRE_FOR_READ_AHEAD)&UdfAcquireForCache;
  Callbacks.ReleaseFromReadAhead = (PRELEASE_FROM_READ_AHEAD)UdfReleaseFromCache;
  qword_140025C48 = (__int64)UdfNoopRelease;
  qword_140025C58 = (__int64)UdfNoopRelease;
  FastMutex.Count = 1;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  WorkItem.Parameter = 0;
  qword_140025B48 = (__int64)&qword_140025B40;
  qword_140025B40 = (__int64)&qword_140025B40;
  qword_140025B60 = (__int64)&qword_140025B58;
  qword_140025B58 = (__int64)&qword_140025B58;
  WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)UdfFspClose;
  WorkItem.List.Flink = 0;
  SystemSize = MmQuerySystemSize();
  if ( SystemSize )
  {
    if ( SystemSize == MmLargeSystem )
    {
      dword_140025B6C = 72;
      dword_140025B70 = 18;
    }
    else
    {
      dword_140025B6C = 32;
      dword_140025B70 = 8;
    }
  }
  else
  {
    dword_140025B6C = 10;
    dword_140025B70 = 2;
  }
  ExInitializeNPagedLookasideList(&UdfIrpContextLookasideList, 0, 0, 0x210u, 0x68u, 0x63666455u, 0);
  ExInitializeNPagedLookasideList(&UdfFcbNonPagedLookasideList, 0, 0, 0x210u, 0x148u, 0x46666455u, 0);
  ExInitializeNPagedLookasideList(&UdfScbNonPagedLookasideList, 0, 0, 0x210u, 0x20u, 0x6E666455u, 0);
  ExInitializePagedLookasideList(&UdfCcbLookasideList, 0, 0, 0x10u, 0x40u, 0x78666455u, 0);
  ExInitializePagedLookasideList(&UdfFcbLookasideList, 0, 0, 0x10u, 0x68u, 0x66666455u, 0);
  ExInitializePagedLookasideList(&UdfScbIndexLookasideList, 0, 0, 0x10u, 0x230u, 0x69666455u, 0);
  ExInitializePagedLookasideList(&UdfScbDataLookasideList, 0, 0, 0x10u, 0x200u, 0x64666455u, 0);
  ExInitializePagedLookasideList(&UdfLcbLookasideList, 0, 0, 0x10u, 0x158u, 0x6C666455u, 0);
  UdfInitializeCrc16();
  UdfGetFileSystemControlValue();
  v9 = 0x190707B60000LL;
  v10 = 0;
  UdfConvertUdfTimeToNtTime(v7, &v9, &UdfCorruptFileTime);
  *(_DWORD *)VersionInformation = 284;
  RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation);
  BYTE12(xmmword_140025350) = VersionInformation[4];
  BYTE13(xmmword_140025350) = VersionInformation[8];
  BYTE14(xmmword_140025350) = VersionInformation[276];
  result = VersionInformation[278];
  HIBYTE(xmmword_140025350) = VersionInformation[278];
  return result;
}

```

## disassembly

```asm
0x14005d4f4  push    rbp
0x14005d4f6  push    rbx
0x14005d4f7  push    rsi
0x14005d4f8  push    rdi
0x14005d4f9  push    r14
0x14005d4fb  lea     rbp, [rsp-80h]
0x14005d500  sub     rsp, 180h
0x14005d507  mov     rax, cs:__security_cookie
0x14005d50e  xor     rax, rsp
0x14005d511  mov     [rbp+0A0h+var_30], rax
0x14005d515  mov     rsi, r8
0x14005d518  mov     rdi, rdx
0x14005d51b  mov     rbx, rcx
0x14005d51e  xor     edx, edx; Val
0x14005d520  mov     r8d, 11Ch; Size
0x14005d526  lea     rcx, [rsp+1A0h+VersionInformation]; void *
0x14005d52b  call    memset
0x14005d530  mov     r14d, 0E0h
0x14005d536  lea     rcx, WPP_MAIN_CB.DeviceExtension; void *
0x14005d53d  mov     r8d, r14d; Size
0x14005d540  xor     edx, edx; Val
0x14005d542  call    memset
0x14005d547  lea     rax, UdfFastIoCheckIfPossible
0x14005d54e  mov     dword ptr cs:WPP_MAIN_CB.DeviceExtension, r14d
0x14005d555  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x14005d55c  lea     rcx, UdfData; void *
0x14005d563  lea     rax, UdfPrepareMdlWrite
0x14005d56a  mov     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, 0
0x14005d575  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x14005d57c  xor     edx, edx; Val
0x14005d57e  lea     rax, UdfPrepareMdlWrite
0x14005d585  mov     r8d, 180h; Size
0x14005d58b  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x14005d592  lea     rax, UdfFastQueryBasicInfo
0x14005d599  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x14005d5a0  lea     rax, UdfFastQueryStdInfo
0x14005d5a7  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, rax
0x14005d5ae  lea     rax, UdfFastLock
0x14005d5b5  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rax
0x14005d5bc  lea     rax, UdfFastUnlockSingle
0x14005d5c3  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x14005d5ca  lea     rax, UdfFastUnlockAll
0x14005d5d1  mov     qword ptr cs:WPP_MAIN_CB.Queue+30h, rax
0x14005d5d8  lea     rax, UdfFastUnlockAllByKey
0x14005d5df  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, rax
0x14005d5e6  lea     rax, UdfFastQueryNetworkInfo
0x14005d5ed  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, rax
0x14005d5f4  lea     rax, UdfReleaseForCreateSection
0x14005d5fb  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rax
0x14005d602  lea     rax, UdfAcquireForModWrite
0x14005d609  mov     cs:WPP_MAIN_CB.DeviceQueue.Lock, rax
0x14005d610  lea     rax, UdfAcquireForCcFlush
0x14005d617  mov     cs:WPP_MAIN_CB.SecurityDescriptor, rax
0x14005d61e  lea     rax, UdfReleaseForCcFlush
0x14005d625  mov     qword ptr cs:WPP_MAIN_CB.DeviceLock.Header, rax
0x14005d62c  lea     rax, UdfPrepareMdlWrite
0x14005d633  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rax
0x14005d63a  mov     rax, cs:__imp_FsRtlMdlReadCompleteDev
0x14005d641  mov     qword ptr cs:WPP_MAIN_CB.Dpc, rax
0x14005d648  lea     rax, UdfPrepareMdlWrite
0x14005d64f  mov     cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, rax
0x14005d656  mov     rax, cs:__imp_FsRtlMdlWriteCompleteDev
0x14005d65d  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rax
0x14005d664  call    memset
0x14005d669  lea     rax, qword_140025B20
0x14005d670  mov     cs:UdfData, 1800931h
0x14005d67a  lea     rcx, Resource; Resource
0x14005d681  mov     cs:qword_140025B28, rax
0x14005d688  mov     cs:qword_140025B20, rax
0x14005d68f  mov     cs:DriverObject, rbx
0x14005d696  mov     cs:qword_140025B10, rdi
0x14005d69d  mov     cs:DeviceObject, rsi
0x14005d6a4  call    cs:__imp_ExInitializeResourceLite
0x14005d6ab  nop     dword ptr [rax+rax+00h]
0x14005d6b0  lea     rax, UdfAcquireForCacheWrite
0x14005d6b7  mov     cs:FastMutex.Owner, 0
0x14005d6c2  mov     cs:Callbacks.AcquireForLazyWrite, rax
0x14005d6c9  lea     rcx, UdfNoopAcquire
0x14005d6d0  lea     rax, UdfReleaseFromCacheWrite
0x14005d6d7  mov     cs:qword_140025C40, rcx
0x14005d6de  mov     cs:Callbacks.ReleaseFromLazyWrite, rax
0x14005d6e5  mov     edx, 1; Type
0x14005d6ea  lea     rax, UdfAcquireForCache
0x14005d6f1  mov     cs:qword_140025C50, rcx
0x14005d6f8  mov     cs:Callbacks.AcquireForReadAhead, rax
0x14005d6ff  lea     rax, UdfReleaseFromCache
0x14005d706  mov     cs:Callbacks.ReleaseFromReadAhead, rax
0x14005d70d  lea     rax, UdfNoopRelease
0x14005d714  mov     cs:qword_140025C48, rax
0x14005d71b  mov     cs:qword_140025C58, rax
0x14005d722  mov     cs:FastMutex.Count, edx
0x14005d728  mov     cs:FastMutex.Contention, 0
0x14005d732  xor     r8d, r8d; State
0x14005d735  lea     rcx, FastMutex.Event; Event
0x14005d73c  call    cs:__imp_KeInitializeEvent
0x14005d743  nop     dword ptr [rax+rax+00h]
0x14005d748  lea     rax, qword_140025B40
0x14005d74f  mov     cs:WorkItem.Parameter, 0
0x14005d75a  mov     cs:qword_140025B48, rax
0x14005d761  mov     cs:qword_140025B40, rax
0x14005d768  lea     rax, qword_140025B58
0x14005d76f  mov     cs:qword_140025B60, rax
0x14005d776  mov     cs:qword_140025B58, rax
0x14005d77d  lea     rax, UdfFspClose
0x14005d784  mov     cs:WorkItem.WorkerRoutine, rax
0x14005d78b  mov     cs:WorkItem.List.Flink, 0
0x14005d796  call    cs:__imp_MmQuerySystemSize
0x14005d79d  nop     dword ptr [rax+rax+00h]
0x14005d7a2  mov     esi, 20h ; ' '
0x14005d7a7  test    eax, eax
0x14005d7a9  jz      short loc_14005D7DD
0x14005d7ab  sub     eax, 1
0x14005d7ae  jz      short loc_14005D7CB
0x14005d7b0  cmp     eax, 1
0x14005d7b3  jnz     short loc_14005D7CB
0x14005d7b5  mov     cs:dword_140025B6C, 48h ; 'H'
0x14005d7bf  mov     cs:dword_140025B70, 12h
0x14005d7c9  jmp     short loc_14005D7F1
0x14005d7cb  mov     cs:dword_140025B6C, esi
0x14005d7d1  mov     cs:dword_140025B70, 8
0x14005d7db  jmp     short loc_14005D7F1
0x14005d7dd  mov     cs:dword_140025B6C, 0Ah
0x14005d7e7  mov     cs:dword_140025B70, 2
0x14005d7f1  xor     eax, eax
0x14005d7f3  lea     rcx, UdfIrpContextLookasideList; Lookaside
0x14005d7fa  mov     [rsp+1A0h+Depth], ax; Depth
0x14005d7ff  mov     ebx, 210h
0x14005d804  mov     [rsp+1A0h+Tag], 63666455h; Tag
0x14005d80c  mov     r9d, ebx; Flags
0x14005d80f  xor     r8d, r8d; Free
0x14005d812  xor     edx, edx; Allocate
0x14005d814  lea     edi, [rax+68h]
0x14005d817  mov     [rsp+1A0h+Size], rdi; Size
0x14005d81c  call    cs:__imp_ExInitializeNPagedLookasideList
0x14005d823  nop     dword ptr [rax+rax+00h]
0x14005d828  xor     eax, eax
0x14005d82a  lea     rcx, UdfFcbNonPagedLookasideList; Lookaside
0x14005d831  mov     [rsp+1A0h+Depth], ax; Depth
0x14005d836  mov     r9d, ebx; Flags
0x14005d839  mov     [rsp+1A0h+Tag], 46666455h; Tag
0x14005d841  xor     r8d, r8d; Free
0x14005d844  xor     edx, edx; Allocate
0x14005d846  mov     [rsp+1A0h+Size], 148h; Size
0x14005d84f  call    cs:__imp_ExInitializeNPagedLookasideList
0x14005d856  nop     dword ptr [rax+rax+00h]
0x14005d85b  xor     eax, eax
0x14005d85d  lea     rcx, UdfScbNonPagedLookasideList; Lookaside
0x14005d864  mov     [rsp+1A0h+Depth], ax; Depth
0x14005d869  mov     r9d, ebx; Flags
0x14005d86c  mov     [rsp+1A0h+Tag], 6E666455h; Tag
0x14005d874  xor     r8d, r8d; Free
0x14005d877  xor     edx, edx; Allocate
0x14005d879  mov     [rsp+1A0h+Size], rsi; Size
0x14005d87e  call    cs:__imp_ExInitializeNPagedLookasideList
0x14005d885  nop     dword ptr [rax+rax+00h]
0x14005d88a  xor     eax, eax
0x14005d88c  lea     ebx, [rdi-58h]
0x14005d88f  mov     [rsp+1A0h+Depth], ax; Depth
0x14005d894  lea     rcx, UdfCcbLookasideList; Lookaside
0x14005d89b  mov     [rsp+1A0h+Tag], 78666455h; Tag
0x14005d8a3  mov     r9d, ebx; Flags
0x14005d8a6  xor     r8d, r8d; Free
0x14005d8a9  mov     [rsp+1A0h+Size], 40h ; '@'; Size
0x14005d8b2  xor     edx, edx; Allocate
0x14005d8b4  call    cs:__imp_ExInitializePagedLookasideList
0x14005d8bb  nop     dword ptr [rax+rax+00h]
0x14005d8c0  xor     eax, eax
0x14005d8c2  lea     rcx, UdfFcbLookasideList; Lookaside
0x14005d8c9  mov     [rsp+1A0h+Depth], ax; Depth
0x14005d8ce  mov     r9d, ebx; Flags
0x14005d8d1  mov     [rsp+1A0h+Tag], 66666455h; Tag
0x14005d8d9  xor     r8d, r8d; Free
0x14005d8dc  xor     edx, edx; Allocate
0x14005d8de  mov     [rsp+1A0h+Size], rdi; Size
0x14005d8e3  call    cs:__imp_ExInitializePagedLookasideList
0x14005d8ea  nop     dword ptr [rax+rax+00h]
0x14005d8ef  xor     eax, eax
0x14005d8f1  lea     rcx, UdfScbIndexLookasideList; Lookaside
0x14005d8f8  mov     [rsp+1A0h+Depth], ax; Depth
0x14005d8fd  mov     r9d, ebx; Flags
0x14005d900  mov     [rsp+1A0h+Tag], 69666455h; Tag
0x14005d908  xor     r8d, r8d; Free
0x14005d90b  xor     edx, edx; Allocate
0x14005d90d  mov     [rsp+1A0h+Size], 230h; Size
0x14005d916  call    cs:__imp_ExInitializePagedLookasideList
0x14005d91d  nop     dword ptr [rax+rax+00h]
0x14005d922  xor     eax, eax
0x14005d924  lea     rcx, UdfScbDataLookasideList; Lookaside
0x14005d92b  mov     [rsp+1A0h+Depth], ax; Depth
0x14005d930  mov     r9d, ebx; Flags
0x14005d933  mov     [rsp+1A0h+Tag], 64666455h; Tag
0x14005d93b  xor     r8d, r8d; Free
0x14005d93e  xor     edx, edx; Allocate
0x14005d940  mov     [rsp+1A0h+Size], 200h; Size
0x14005d949  call    cs:__imp_ExInitializePagedLookasideList
0x14005d950  nop     dword ptr [rax+rax+00h]
0x14005d955  xor     eax, eax
0x14005d957  lea     rcx, UdfLcbLookasideList; Lookaside
0x14005d95e  mov     [rsp+1A0h+Depth], ax; Depth
0x14005d963  mov     r9d, ebx; Flags
0x14005d966  mov     [rsp+1A0h+Tag], 6C666455h; Tag
0x14005d96e  xor     r8d, r8d; Free
0x14005d971  xor     edx, edx; Allocate
0x14005d973  mov     [rsp+1A0h+Size], 158h; Size
0x14005d97c  call    cs:__imp_ExInitializePagedLookasideList
0x14005d983  nop     dword ptr [rax+rax+00h]
0x14005d988  call    UdfInitializeCrc16
0x14005d98d  call    UdfGetFileSystemControlValue
0x14005d992  xor     eax, eax
0x14005d994  mov     [rsp+1A0h+var_160], rax
0x14005d999  mov     dword ptr [rsp+1A0h+var_160+2], 190707B6h
0x14005d9a1  mov     [rsp+1A0h+var_158], eax
0x14005d9a5  lea     r8, UdfCorruptFileTime
0x14005d9ac  lea     rdx, [rsp+1A0h+var_160]
0x14005d9b1  call    UdfConvertUdfTimeToNtTime
0x14005d9b6  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x14005d9bb  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14005d9c3  call    cs:__imp_RtlGetVersion
0x14005d9ca  nop     dword ptr [rax+rax+00h]
0x14005d9cf  mov     al, byte ptr [rsp+1A0h+VersionInformation.dwMajorVersion]
0x14005d9d3  mov     byte ptr cs:xmmword_140025350+0Ch, al
0x14005d9d9  mov     al, byte ptr [rsp+1A0h+VersionInformation.dwMinorVersion]
0x14005d9dd  mov     byte ptr cs:xmmword_140025350+0Dh, al
0x14005d9e3  mov     al, [rbp+0A0h+var_3C]
0x14005d9e6  mov     byte ptr cs:xmmword_140025350+0Eh, al
0x14005d9ec  mov     al, [rbp+0A0h+var_3A]
0x14005d9ef  mov     byte ptr cs:xmmword_140025350+0Fh, al
0x14005d9f5  mov     rcx, [rbp+0A0h+var_30]
0x14005d9f9  xor     rcx, rsp; StackCookie
0x14005d9fc  call    __security_check_cookie
0x14005da01  add     rsp, 180h
0x14005da08  pop     r14
0x14005da0a  pop     rdi
0x14005da0b  pop     rsi
0x14005da0c  pop     rbx
0x14005da0d  pop     rbp
0x14005da0e  retn
```
