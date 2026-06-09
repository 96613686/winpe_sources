# InitDynamicPgmConfig

- ea: `0x1400375c4`
- end: `0x140037753`
- name: `InitDynamicPgmConfig`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003775c`

## callees

- `0x140005038`
- `0x14001c878`
- `0x14001d300`
- `0x1400375c4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14003770f`
- `ntoskrnl!KeInitializeEvent` at `0x14003770f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400376f7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400376f7`

## pseudocode

```c
__int64 InitDynamicPgmConfig()
{
  memset(&WPP_MAIN_CB.DeviceExtension, 0, 0x170u);
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = &WPP_MAIN_CB.DeviceExtension;
  WPP_MAIN_CB.Queue.ListEntry.Blink = &WPP_MAIN_CB.Queue.ListEntry;
  WPP_MAIN_CB.Queue.ListEntry.Flink = &WPP_MAIN_CB.Queue.ListEntry;
  WPP_MAIN_CB.DeviceExtension = &WPP_MAIN_CB.DeviceExtension;
  WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = (PDRIVER_CONTROL)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = &WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = &WPP_MAIN_CB.Queue.Wcb.DeviceContext;
  WPP_MAIN_CB.Queue.Wcb.DeviceContext = &WPP_MAIN_CB.Queue.Wcb.DeviceContext;
  WPP_MAIN_CB.DeviceQueue.Lock = (KSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink = (struct _LIST_ENTRY *)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink;
  WPP_MAIN_CB.Queue.Wcb.CurrentIrp = &WPP_MAIN_CB.Queue.Wcb.DeviceObject;
  WPP_MAIN_CB.Queue.Wcb.DeviceObject = &WPP_MAIN_CB.Queue.Wcb.DeviceObject;
  *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement = &WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
  WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc = (PKDPC)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink = (struct _LIST_ENTRY *)&WPP_MAIN_CB.DeviceQueue;
  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = &WPP_MAIN_CB.DeviceQueue;
  *(_QWORD *)&WPP_MAIN_CB.Dpc.TargetInfoAsUlong = &WPP_MAIN_CB.DeviceQueue.1;
  WPP_MAIN_CB.DeviceQueue.1 = (struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C)&WPP_MAIN_CB.DeviceQueue.1;
  WPP_MAIN_CB.Dpc.ProcessorHistory = (KAFFINITY)&WPP_MAIN_CB.Dpc.DpcListEntry;
  WPP_MAIN_CB.Dpc.DpcListEntry.Next = &WPP_MAIN_CB.Dpc.DpcListEntry;
  WPP_MAIN_CB.Dpc.SystemArgument1 = (PVOID)1;
  GetRandomData((char *)&WPP_MAIN_CB.Dpc.DpcData + 6, 2);
  HIWORD(WPP_MAIN_CB.Dpc.DpcData) = HIWORD(WPP_MAIN_CB.Dpc.DpcData) % 0x4651u + 2000;
  KeInitializeSpinLock(&SpinLock);
  KeInitializeEvent(&Event, NotificationEvent, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400375c4  push    rbx
0x1400375c6  sub     rsp, 20h
0x1400375ca  lea     rbx, WPP_MAIN_CB.DeviceExtension
0x1400375d1  xor     edx, edx; Val
0x1400375d3  mov     rcx, rbx; void *
0x1400375d6  mov     r8d, 170h; Size
0x1400375dc  call    memset
0x1400375e1  lea     rax, WPP_MAIN_CB.Queue
0x1400375e8  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rbx
0x1400375ef  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x1400375f6  lea     rcx, WPP_MAIN_CB.Dpc.DpcData+6
0x1400375fd  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x140037604  mov     edx, 2
0x140037609  lea     rax, WPP_MAIN_CB.Queue+10h
0x140037610  mov     cs:WPP_MAIN_CB.DeviceExtension, rbx
0x140037617  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, rax
0x14003761e  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x140037625  lea     rax, WPP_MAIN_CB.Queue+20h
0x14003762c  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x140037633  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rax
0x14003763a  lea     rax, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x140037641  mov     cs:WPP_MAIN_CB.DeviceQueue.Lock, rax
0x140037648  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, rax
0x14003764f  lea     rax, WPP_MAIN_CB.Queue+30h
0x140037656  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, rax
0x14003765d  mov     qword ptr cs:WPP_MAIN_CB.Queue+30h, rax
0x140037664  lea     rax, WPP_MAIN_CB.Queue+40h
0x14003766b  mov     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, rax
0x140037672  mov     qword ptr cs:WPP_MAIN_CB.Queue+40h, rax
0x140037679  lea     rax, WPP_MAIN_CB.DeviceQueue
0x140037680  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, rax
0x140037687  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rax
0x14003768e  lea     rax, WPP_MAIN_CB.DeviceQueue.20h
0x140037695  mov     qword ptr cs:WPP_MAIN_CB.Dpc, rax
0x14003769c  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rax
0x1400376a3  lea     rax, WPP_MAIN_CB.Dpc.DpcListEntry
0x1400376aa  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rax
0x1400376b1  mov     cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, rax
0x1400376b8  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x1400376c3  call    GetRandomData
0x1400376c8  movzx   ecx, word ptr cs:WPP_MAIN_CB.Dpc.DpcData+6
0x1400376cf  mov     eax, 7480813Fh
0x1400376d4  mul     ecx
0x1400376d6  shr     edx, 0Dh
0x1400376d9  imul    eax, edx, 4651h
0x1400376df  sub     ecx, eax
0x1400376e1  mov     eax, 7D0h
0x1400376e6  add     cx, ax
0x1400376e9  mov     word ptr cs:WPP_MAIN_CB.Dpc.DpcData+6, cx
0x1400376f0  lea     rcx, SpinLock; SpinLock
0x1400376f7  call    cs:__imp_KeInitializeSpinLock
0x1400376fe  nop     dword ptr [rax+rax+00h]
0x140037703  mov     r8b, 1; State
0x140037706  lea     rcx, Event; Event
0x14003770d  xor     edx, edx; Type
0x14003770f  call    cs:__imp_KeInitializeEvent
0x140037716  nop     dword ptr [rax+rax+00h]
0x14003771b  mov     rcx, cs:WPP_GLOBAL_Control
0x140037722  lea     rax, WPP_GLOBAL_Control
0x140037729  cmp     rcx, rax
0x14003772c  jz      short loc_14003774A
0x14003772e  mov     eax, [rcx+2Ch]
0x140037731  mov     edx, 10h
0x140037736  test    dl, al
0x140037738  jz      short loc_14003774A
0x14003773a  mov     rcx, [rcx+18h]
0x14003773e  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037745  call    WPP_SF_
0x14003774a  xor     eax, eax
0x14003774c  add     rsp, 20h
0x140037750  pop     rbx
0x140037751  retn
```
