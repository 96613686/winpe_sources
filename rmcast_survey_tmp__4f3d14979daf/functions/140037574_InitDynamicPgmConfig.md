# InitDynamicPgmConfig

- ea: `0x140037574`
- end: `0x140037703`
- name: `InitDynamicPgmConfig`
- size: `399`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003770c`

## callees

- `0x140005038`
- `0x14001c878`
- `0x14001d300`
- `0x140037574`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400376bf`
- `ntoskrnl!KeInitializeEvent` at `0x1400376bf`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400376a7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400376a7`

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
  GetRandomData((__int64)&WPP_MAIN_CB.Dpc.DpcData + 6, 2u);
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
0x140037574  push    rbx
0x140037576  sub     rsp, 20h
0x14003757a  lea     rbx, WPP_MAIN_CB.DeviceExtension
0x140037581  xor     edx, edx; Val
0x140037583  mov     rcx, rbx; void *
0x140037586  mov     r8d, 170h; Size
0x14003758c  call    memset
0x140037591  lea     rax, WPP_MAIN_CB.Queue
0x140037598  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rbx
0x14003759f  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x1400375a6  lea     rcx, WPP_MAIN_CB.Dpc.DpcData+6
0x1400375ad  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x1400375b4  mov     edx, 2
0x1400375b9  lea     rax, WPP_MAIN_CB.Queue+10h
0x1400375c0  mov     cs:WPP_MAIN_CB.DeviceExtension, rbx
0x1400375c7  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, rax
0x1400375ce  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x1400375d5  lea     rax, WPP_MAIN_CB.Queue+20h
0x1400375dc  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x1400375e3  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rax
0x1400375ea  lea     rax, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x1400375f1  mov     cs:WPP_MAIN_CB.DeviceQueue.Lock, rax
0x1400375f8  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, rax
0x1400375ff  lea     rax, WPP_MAIN_CB.Queue+30h
0x140037606  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, rax
0x14003760d  mov     qword ptr cs:WPP_MAIN_CB.Queue+30h, rax
0x140037614  lea     rax, WPP_MAIN_CB.Queue+40h
0x14003761b  mov     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, rax
0x140037622  mov     qword ptr cs:WPP_MAIN_CB.Queue+40h, rax
0x140037629  lea     rax, WPP_MAIN_CB.DeviceQueue
0x140037630  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, rax
0x140037637  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rax
0x14003763e  lea     rax, WPP_MAIN_CB.DeviceQueue.20h
0x140037645  mov     qword ptr cs:WPP_MAIN_CB.Dpc, rax
0x14003764c  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rax
0x140037653  lea     rax, WPP_MAIN_CB.Dpc.DpcListEntry
0x14003765a  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rax
0x140037661  mov     cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, rax
0x140037668  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x140037673  call    GetRandomData
0x140037678  movzx   ecx, word ptr cs:WPP_MAIN_CB.Dpc.DpcData+6
0x14003767f  mov     eax, 7480813Fh
0x140037684  mul     ecx
0x140037686  shr     edx, 0Dh
0x140037689  imul    eax, edx, 4651h
0x14003768f  sub     ecx, eax
0x140037691  mov     eax, 7D0h
0x140037696  add     cx, ax
0x140037699  mov     word ptr cs:WPP_MAIN_CB.Dpc.DpcData+6, cx
0x1400376a0  lea     rcx, SpinLock; SpinLock
0x1400376a7  call    cs:__imp_KeInitializeSpinLock
0x1400376ae  nop     dword ptr [rax+rax+00h]
0x1400376b3  mov     r8b, 1; State
0x1400376b6  lea     rcx, Event; Event
0x1400376bd  xor     edx, edx; Type
0x1400376bf  call    cs:__imp_KeInitializeEvent
0x1400376c6  nop     dword ptr [rax+rax+00h]
0x1400376cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400376d2  lea     rax, WPP_GLOBAL_Control
0x1400376d9  cmp     rcx, rax
0x1400376dc  jz      short loc_1400376FA
0x1400376de  mov     eax, [rcx+2Ch]
0x1400376e1  mov     edx, 10h
0x1400376e6  test    dl, al
0x1400376e8  jz      short loc_1400376FA
0x1400376ea  mov     rcx, [rcx+18h]
0x1400376ee  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x1400376f5  call    WPP_SF_
0x1400376fa  xor     eax, eax
0x1400376fc  add     rsp, 20h
0x140037700  pop     rbx
0x140037701  retn
```
