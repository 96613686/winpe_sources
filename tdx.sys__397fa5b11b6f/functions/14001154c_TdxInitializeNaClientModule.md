# TdxInitializeNaClientModule

- ea: `0x14001154c`
- end: `0x140011816`
- name: `TdxInitializeNaClientModule`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140014184`

## callees

- `0x14001154c`
- `0x140012b5c`
- `0x140012fd0`
- `0x140014c84`
- `0x140015038`
- `0x140018218`
- `0x1400182b4`
- `0x140018900`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x1400115ca`
- `ntoskrnl!KeInitializeMutex` at `0x1400115ca`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400115e0`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400115e0`
- `ntoskrnl!KeInitializeTimer` at `0x140011640`
- `ntoskrnl!KeInitializeTimer` at `0x140011640`
- `ntoskrnl!KeSetTimer` at `0x14001167e`
- `ntoskrnl!KeSetTimer` at `0x14001167e`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400116a6`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011796`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400116a6`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011796`
- `ntoskrnl!KeInitializeDpc` at `0x14001165d`
- `ntoskrnl!KeInitializeDpc` at `0x14001165d`
- `NETIO!NmrRegisterClient` at `0x1400117b2`
- `NETIO!NmrRegisterClient` at `0x1400117b2`
- `NETIO!NmrDeregisterClient` at `0x1400117d9`
- `NETIO!NmrDeregisterClient` at `0x1400117d9`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400117ec`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400117ec`

## string_xrefs

- `0x14001157e`: `TdxInitializeNaClientModule`

## pseudocode

```c
__int64 __fastcall TdxInitializeNaClientModule(_BYTE *a1)
{
  NTSTATUS v3; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
  {
    WPP_SF_s(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
      "TdxInitializeNaClientModule");
  }
  *(_OWORD *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0u;
  WPP_MAIN_CB.ActiveThreadCount = 1;
  qword_14001E508 = 0;
  KeInitializeMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
  *a1 = 0;
  qword_14001E500 = IoAllocateWorkItem(TdxDeviceObject);
  if ( qword_14001E500 )
  {
    _InterlockedExchange((_DWORD *)&qword_14001E508 + 1, 3);
    KeInitializeTimer(&TdxProviderReadyContext);
    KeInitializeDpc(&Dpc, TdxProviderReadyTimeoutRoutine, 0);
    KeSetTimer(&TdxProviderReadyContext, (LARGE_INTEGER)-600000000LL, &Dpc);
    WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink = (struct _LIST_ENTRY *)&WPP_MAIN_CB.DeviceQueue;
    *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = &WPP_MAIN_CB.DeviceQueue;
    KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
    *(_QWORD *)&WPP_MAIN_CB.Dpc.TargetInfoAsUlong = &WPP_MAIN_CB.DeviceQueue.1;
    WPP_MAIN_CB.DeviceQueue.1 = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)&WPP_MAIN_CB.DeviceQueue.1;
    memset(&WPP_MAIN_CB.DeviceLock.Header.WaitListHead, 0, 0x90u);
    v3 = NetioInitializeWorkQueue(&WPP_MAIN_CB.Reserved + 1, TdxProcessAddressChangeRoutine);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids);
      }
    }
    else
    {
      v3 = NetioInitializeWorkQueue(&Context, TdxProcessInterfaceChangeRoutine);
      if ( v3 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids);
        }
        NetioShutdownWorkQueue(&WPP_MAIN_CB.Reserved + 1);
      }
      else
      {
        byte_14001E468 = 1;
        KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
        v3 = NmrRegisterClient(&TdxNaClientNotify, 0, &WPP_MAIN_CB.Queue.Wcb.DeviceContext);
        if ( v3 >= 0 )
        {
          v3 = TdxNaRegisterChangeHandler(a1);
          if ( v3 >= 0 )
            return (unsigned int)v3;
          NmrDeregisterClient(WPP_MAIN_CB.Queue.Wcb.DeviceContext);
          NmrWaitForClientDeregisterComplete(WPP_MAIN_CB.Queue.Wcb.DeviceContext);
          WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
        }
      }
    }
    TdxShutdownNaClientModule();
    return (unsigned int)v3;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 9u) )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids);
  }
  return 3221225495LL;
}

```

## disassembly

```asm
0x14001154c  push    rbx
0x14001154e  push    rdi
0x14001154f  push    r14
0x140011551  push    r15
0x140011553  sub     rsp, 28h
0x140011557  mov     rdi, rcx
0x14001155a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011561  lea     r15, WPP_GLOBAL_Control
0x140011568  cmp     rcx, r15
0x14001156b  jz      short loc_140011596
0x14001156d  cmp     byte ptr [rcx+29h], 3
0x140011571  jb      short loc_140011596
0x140011573  bt      dword ptr [rcx+2Ch], 9
0x140011578  jnb     short loc_140011596
0x14001157a  mov     rcx, [rcx+18h]
0x14001157e  lea     r9, aTdxinitializen; "TdxInitializeNaClientModule"
0x140011585  mov     edx, 0Dh
0x14001158a  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x140011591  call    WPP_SF_s
0x140011596  xor     edx, edx; Level
0x140011598  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x1400115a3  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x1400115aa  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, 0
0x1400115b5  mov     cs:WPP_MAIN_CB.ActiveThreadCount, 1
0x1400115bf  mov     cs:qword_14001E508, 0
0x1400115ca  call    cs:__imp_KeInitializeMutex
0x1400115d1  nop     dword ptr [rax+rax+00h]
0x1400115d6  mov     byte ptr [rdi], 0
0x1400115d9  mov     rcx, cs:TdxDeviceObject; DeviceObject
0x1400115e0  call    cs:__imp_IoAllocateWorkItem
0x1400115e7  nop     dword ptr [rax+rax+00h]
0x1400115ec  mov     cs:qword_14001E500, rax
0x1400115f3  test    rax, rax
0x1400115f6  jnz     short loc_14001162E
0x1400115f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400115ff  cmp     rcx, r15
0x140011602  jz      short loc_140011624
0x140011604  cmp     byte ptr [rcx+29h], 3
0x140011608  jb      short loc_140011624
0x14001160a  bt      dword ptr [rcx+2Ch], 9
0x14001160f  jnb     short loc_140011624
0x140011611  mov     rcx, [rcx+18h]
0x140011615  lea     edx, [rax+0Eh]
0x140011618  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14001161f  call    WPP_SF_
0x140011624  mov     eax, 0C0000017h
0x140011629  jmp     loc_14001180A
0x14001162e  mov     eax, 3
0x140011633  lea     rcx, TdxProviderReadyContext; Timer
0x14001163a  xchg    eax, dword ptr cs:qword_14001E508+4
0x140011640  call    cs:__imp_KeInitializeTimer
0x140011647  nop     dword ptr [rax+rax+00h]
0x14001164c  xor     r8d, r8d; DeferredContext
0x14001164f  lea     rdx, TdxProviderReadyTimeoutRoutine; DeferredRoutine
0x140011656  lea     rcx, Dpc; Dpc
0x14001165d  call    cs:__imp_KeInitializeDpc
0x140011664  nop     dword ptr [rax+rax+00h]
0x140011669  lea     r8, Dpc; Dpc
0x140011670  mov     rdx, 0FFFFFFFFDC3CBA00h; DueTime
0x140011677  lea     rcx, TdxProviderReadyContext; Timer
0x14001167e  call    cs:__imp_KeSetTimer
0x140011685  nop     dword ptr [rax+rax+00h]
0x14001168a  lea     rax, WPP_MAIN_CB.DeviceQueue
0x140011691  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x140011698  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, rax
0x14001169f  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rax
0x1400116a6  call    cs:__imp_KeInitializeSpinLock
0x1400116ad  nop     dword ptr [rax+rax+00h]
0x1400116b2  lea     rax, WPP_MAIN_CB.DeviceQueue.20h
0x1400116b9  xor     edx, edx; Val
0x1400116bb  mov     r8d, 90h; Size
0x1400116c1  mov     qword ptr cs:WPP_MAIN_CB.Dpc, rax
0x1400116c8  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; void *
0x1400116cf  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rax
0x1400116d6  call    memset
0x1400116db  lea     rdx, TdxProcessAddressChangeRoutine
0x1400116e2  lea     rcx, WPP_MAIN_CB+148h
0x1400116e9  call    NetioInitializeWorkQueue
0x1400116ee  mov     ebx, eax
0x1400116f0  test    eax, eax
0x1400116f2  jz      short loc_140011733
0x1400116f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116fb  cmp     rcx, r15
0x1400116fe  jz      loc_140011803
0x140011704  cmp     byte ptr [rcx+29h], 3
0x140011708  jb      loc_140011803
0x14001170e  bt      dword ptr [rcx+2Ch], 9
0x140011713  jnb     loc_140011803
0x140011719  mov     rcx, [rcx+18h]
0x14001171d  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x140011724  mov     edx, 0Fh
0x140011729  call    WPP_SF_
0x14001172e  jmp     loc_140011803
0x140011733  lea     rdx, TdxProcessInterfaceChangeRoutine
0x14001173a  lea     rcx, Context
0x140011741  call    NetioInitializeWorkQueue
0x140011746  mov     ebx, eax
0x140011748  test    eax, eax
0x14001174a  jz      short loc_140011788
0x14001174c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011753  cmp     rcx, r15
0x140011756  jz      short loc_14001177A
0x140011758  cmp     byte ptr [rcx+29h], 3
0x14001175c  jb      short loc_14001177A
0x14001175e  bt      dword ptr [rcx+2Ch], 9
0x140011763  jnb     short loc_14001177A
0x140011765  mov     rcx, [rcx+18h]
0x140011769  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x140011770  mov     edx, 10h
0x140011775  call    WPP_SF_
0x14001177a  lea     rcx, WPP_MAIN_CB+148h
0x140011781  call    NetioShutdownWorkQueue
0x140011786  jmp     short loc_140011803
0x140011788  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x14001178f  mov     cs:byte_14001E468, 1
0x140011796  call    cs:__imp_KeInitializeSpinLock
0x14001179d  nop     dword ptr [rax+rax+00h]
0x1400117a2  lea     r8, WPP_MAIN_CB.Queue+20h; NmrClientHandle
0x1400117a9  xor     edx, edx; ClientContext
0x1400117ab  lea     rcx, TdxNaClientNotify; ClientCharacteristics
0x1400117b2  call    cs:__imp_NmrRegisterClient
0x1400117b9  nop     dword ptr [rax+rax+00h]
0x1400117be  mov     ebx, eax
0x1400117c0  test    eax, eax
0x1400117c2  js      short loc_140011803
0x1400117c4  mov     rcx, rdi
0x1400117c7  call    TdxNaRegisterChangeHandler
0x1400117cc  mov     ebx, eax
0x1400117ce  test    eax, eax
0x1400117d0  jns     short loc_140011808
0x1400117d2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; NmrClientHandle
0x1400117d9  call    cs:__imp_NmrDeregisterClient
0x1400117e0  nop     dword ptr [rax+rax+00h]
0x1400117e5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; NmrClientHandle
0x1400117ec  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x1400117f3  nop     dword ptr [rax+rax+00h]
0x1400117f8  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140011803  call    TdxShutdownNaClientModule
0x140011808  mov     eax, ebx
0x14001180a  add     rsp, 28h
0x14001180e  pop     r15
0x140011810  pop     r14
0x140011812  pop     rdi
0x140011813  pop     rbx
0x140011814  retn
```
