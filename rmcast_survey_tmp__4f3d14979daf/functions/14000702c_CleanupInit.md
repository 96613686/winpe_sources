# CleanupInit

- ea: `0x14000702c`
- end: `0x140007385`
- name: `CleanupInit`
- size: `857`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400361a0`
- `0x14003770c`
- `0x14003a078`

## callees

- `0x140002550`
- `0x140005068`
- `0x1400052e4`
- `0x14000702c`
- `0x14001ce30`
- `0x1400366fc`
- `0x140037dd0`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400070b1`
- `ntoskrnl!KeClearEvent` at `0x1400070b1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007105`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007105`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140007304`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140007304`
- `ntoskrnl!ObfDereferenceObject` at `0x140007338`
- `ntoskrnl!ObfDereferenceObject` at `0x140007338`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007160`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400071c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007160`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400071c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400070c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007114`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400070c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007114`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400071b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007249`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000725c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007289`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400072a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007319`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000735d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400071b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007249`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000725c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007289`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400072a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007319`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000735d`
- `TDI!TdiDeregisterPnPHandlers` at `0x1400071dc`
- `TDI!TdiDeregisterPnPHandlers` at `0x1400071dc`

## pseudocode

```c
__int64 __fastcall CleanupInit(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  PDEVICE_OBJECT v5; // rcx
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  KIRQL v12; // dl
  struct _SINGLE_LIST_ENTRY *Next; // rbx
  struct _SINGLE_LIST_ENTRY *v14; // r8
  struct _SINGLE_LIST_ENTRY *v15; // rcx
  struct _SINGLE_LIST_ENTRY *v16; // rdi
  _QWORD **v17; // rbx
  __int64 v18; // rax
  _QWORD **v19; // rdi
  _QWORD *v20; // rcx
  _QWORD *v21; // rax
  PVOID v22; // rcx
  void *v23; // rcx
  __int64 v24; // rax

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xEu,
      (__int64)WPP_a24bb4c2db3a31577af78786167edc49_Traceguids,
      a1);
  v6 = a1 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( !v7 )
      goto LABEL_37;
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( v11 != 1 )
              goto LABEL_44;
            KeClearEvent(&Event);
            v12 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
            if ( !HIDWORD(WPP_MAIN_CB.Dpc.SystemArgument2) )
              goto LABEL_14;
            KeReleaseSpinLock(&SpinLock, v12);
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
            while ( 1 )
            {
              v12 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
LABEL_14:
              Next = WPP_MAIN_CB.Dpc.DpcListEntry.Next;
              if ( WPP_MAIN_CB.Dpc.DpcListEntry.Next == &WPP_MAIN_CB.Dpc.DpcListEntry )
                break;
              v14 = WPP_MAIN_CB.Dpc.DpcListEntry.Next->Next;
              if ( WPP_MAIN_CB.Dpc.DpcListEntry.Next->Next[1].Next != WPP_MAIN_CB.Dpc.DpcListEntry.Next
                || (v15 = WPP_MAIN_CB.Dpc.DpcListEntry.Next[1].Next, v15->Next != WPP_MAIN_CB.Dpc.DpcListEntry.Next) )
              {
LABEL_41:
                __fastfail(3u);
              }
              v15->Next = v14;
              v14[1].Next = v15;
              KeReleaseSpinLock(&SpinLock, v12);
              v16 = Next[2].Next;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
              {
                WPP_SF_q(
                  WPP_GLOBAL_Control->AttachedDevice,
                  15,
                  WPP_a24bb4c2db3a31577af78786167edc49_Traceguids,
                  Next[2].Next);
              }
              ((void (__fastcall *)(struct _SINGLE_LIST_ENTRY *, struct _SINGLE_LIST_ENTRY *, struct _SINGLE_LIST_ENTRY *))v16)(
                Next[3].Next,
                Next[4].Next,
                Next[5].Next);
              ExFreePoolWithTag(&Next[-4], 0);
            }
            KeReleaseSpinLock(&SpinLock, v12);
          }
          TdiDeregisterPnPHandlers(TdiClientHandle);
          while ( 1 )
          {
            v17 = (_QWORD **)WPP_MAIN_CB.DeviceQueue.1;
            if ( (BOOLEAN *)WPP_MAIN_CB.DeviceQueue.32 == &WPP_MAIN_CB.DeviceQueue.Busy )
              break;
            if ( *(struct _DEVICE_OBJECT **)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 + 8LL) != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
              goto LABEL_41;
            v18 = **(_QWORD **)&WPP_MAIN_CB.DeviceQueue.32;
            if ( *(_QWORD *)(**(_QWORD **)&WPP_MAIN_CB.DeviceQueue.32 + 8LL) != *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 )
              goto LABEL_41;
            WPP_MAIN_CB.DeviceQueue.1 = **(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **)&WPP_MAIN_CB.DeviceQueue.32;
            v19 = v17 + 2;
            *(_QWORD *)(v18 + 8) = &WPP_MAIN_CB.DeviceQueue.1;
            while ( 1 )
            {
              v20 = *v19;
              if ( *v19 == v19 )
                break;
              if ( (_QWORD **)v20[1] != v19 )
                goto LABEL_41;
              v21 = (_QWORD *)*v20;
              if ( *(_QWORD **)(*v20 + 8LL) != v20 )
                goto LABEL_41;
              *v19 = v21;
              v21[1] = v19;
              ExFreePoolWithTag(v20, 0);
            }
            ExFreePoolWithTag(v17, 0);
          }
        }
        PgmDereferenceDevice((__int64)v5, a2, a3, a4);
      }
    }
    v22 = pPgmRegistryConfig;
    if ( pPgmRegistryConfig )
    {
      if ( *((_QWORD *)pPgmRegistryConfig + 2) )
      {
        ExFreePoolWithTag(*((PVOID *)pPgmRegistryConfig + 2), 0);
        v22 = pPgmRegistryConfig;
        *((_QWORD *)pPgmRegistryConfig + 2) = 0;
      }
      ExFreePoolWithTag(v22, 0);
      pPgmRegistryConfig = 0;
    }
LABEL_37:
    while ( 1 )
    {
      v23 = *(void **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
      if ( *(struct _DEVICE_OBJECT **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
        break;
      if ( *(struct _DEVICE_OBJECT **)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL) != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
        goto LABEL_41;
      v24 = **(_QWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
      if ( *(_QWORD *)(**(_QWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL) != *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
        goto LABEL_41;
      *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = **(_QWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
      *(_QWORD *)(v24 + 8) = &WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
      PgmDestroyAddress(v23);
    }
  }
  ExDeleteNPagedLookasideList(&Lookaside);
  ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( Object )
  {
    byte_140021D68 = 0;
    ObfDereferenceObject(Object);
    Object = 0;
  }
LABEL_44:
  if ( PgmSecurityDescriptor )
  {
    ExFreePoolWithTag(PgmSecurityDescriptor, 0);
    PgmSecurityDescriptor = 0;
  }
  return wil_UninitializeFeatureStaging();
}

```

## disassembly

```asm
0x14000702c  push    rbx
0x14000702e  push    rdi
0x14000702f  push    r14
0x140007031  push    r15
0x140007033  sub     rsp, 38h
0x140007037  mov     ebx, ecx
0x140007039  mov     rcx, cs:WPP_GLOBAL_Control
0x140007040  lea     r15, WPP_GLOBAL_Control
0x140007047  cmp     rcx, r15
0x14000704a  jz      short loc_14000706B
0x14000704c  mov     eax, [rcx+2Ch]
0x14000704f  test    al, 10h
0x140007051  jz      short loc_14000706B
0x140007053  mov     rcx, [rcx+18h]
0x140007057  lea     r8, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids
0x14000705e  mov     edx, 0Eh
0x140007063  mov     r9d, ebx
0x140007066  call    WPP_SF_d
0x14000706b  sub     ebx, 1
0x14000706e  jz      loc_1400072FD
0x140007074  sub     ebx, 1
0x140007077  jz      loc_1400072BD
0x14000707d  sub     ebx, 1
0x140007080  jz      loc_14000726F
0x140007086  sub     ebx, 1
0x140007089  jz      loc_14000726F
0x14000708f  sub     ebx, 1
0x140007092  jz      loc_14000726A
0x140007098  sub     ebx, 1
0x14000709b  jz      loc_1400071D5
0x1400070a1  cmp     ebx, 1
0x1400070a4  jnz     loc_14000734F
0x1400070aa  lea     rcx, Event; Event
0x1400070b1  call    cs:__imp_KeClearEvent
0x1400070b8  nop     dword ptr [rax+rax+00h]
0x1400070bd  lea     r14, SpinLock
0x1400070c4  mov     rcx, r14; SpinLock
0x1400070c7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400070ce  nop     dword ptr [rax+rax+00h]
0x1400070d3  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2+4, 0
0x1400070da  mov     dl, al; NewIrql
0x1400070dc  jz      short loc_140007122
0x1400070de  mov     rcx, r14; SpinLock
0x1400070e1  call    cs:__imp_KeReleaseSpinLock
0x1400070e8  nop     dword ptr [rax+rax+00h]
0x1400070ed  xor     r9d, r9d; Alertable
0x1400070f0  mov     [rsp+58h+Timeout], 0; Timeout
0x1400070f9  xor     r8d, r8d; WaitMode
0x1400070fc  lea     rcx, Event; Object
0x140007103  xor     edx, edx; WaitReason
0x140007105  call    cs:__imp_KeWaitForSingleObject
0x14000710c  nop     dword ptr [rax+rax+00h]
0x140007111  mov     rcx, r14; SpinLock
0x140007114  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000711b  nop     dword ptr [rax+rax+00h]
0x140007120  mov     dl, al; NewIrql
0x140007122  mov     rbx, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x140007129  lea     rax, WPP_MAIN_CB.Dpc.DpcListEntry
0x140007130  cmp     rbx, rax
0x140007133  jz      loc_1400071C6
0x140007139  mov     r8, [rbx]
0x14000713c  mov     rax, rbx
0x14000713f  cmp     [r8+8], rbx
0x140007143  jnz     loc_1400072F6
0x140007149  mov     rcx, [rbx+8]
0x14000714d  cmp     [rcx], rax
0x140007150  jnz     loc_1400072F6
0x140007156  mov     [rcx], r8
0x140007159  mov     [r8+8], rcx
0x14000715d  mov     rcx, r14; SpinLock
0x140007160  call    cs:__imp_KeReleaseSpinLock
0x140007167  nop     dword ptr [rax+rax+00h]
0x14000716c  mov     rdi, [rbx+10h]
0x140007170  mov     rcx, cs:WPP_GLOBAL_Control
0x140007177  cmp     rcx, r15
0x14000717a  jz      short loc_14000719B
0x14000717c  mov     eax, [rcx+2Ch]
0x14000717f  test    al, 10h
0x140007181  jz      short loc_14000719B
0x140007183  mov     rcx, [rcx+18h]
0x140007187  lea     r8, WPP_a24bb4c2db3a31577af78786167edc49_Traceguids
0x14000718e  mov     edx, 0Fh
0x140007193  mov     r9, rdi
0x140007196  call    WPP_SF_q
0x14000719b  mov     r8, [rbx+28h]
0x14000719f  mov     rax, rdi
0x1400071a2  mov     rdx, [rbx+20h]
0x1400071a6  mov     rcx, [rbx+18h]
0x1400071aa  call    _guard_dispatch_icall
0x1400071af  xor     edx, edx; Tag
0x1400071b1  lea     rcx, [rbx-20h]; P
0x1400071b5  call    cs:__imp_ExFreePoolWithTag
0x1400071bc  nop     dword ptr [rax+rax+00h]
0x1400071c1  jmp     loc_140007111
0x1400071c6  mov     rcx, r14; SpinLock
0x1400071c9  call    cs:__imp_KeReleaseSpinLock
0x1400071d0  nop     dword ptr [rax+rax+00h]
0x1400071d5  mov     rcx, cs:TdiClientHandle; BindingHandle
0x1400071dc  call    cs:__imp_TdiDeregisterPnPHandlers
0x1400071e3  nop     dword ptr [rax+rax+00h]
0x1400071e8  lea     r14, WPP_MAIN_CB.DeviceQueue.20h
0x1400071ef  mov     rbx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x1400071f6  cmp     rbx, r14
0x1400071f9  jz      short loc_14000726A
0x1400071fb  cmp     [rbx+8], r14
0x1400071ff  jnz     loc_1400072F6
0x140007205  mov     rax, [rbx]
0x140007208  cmp     [rax+8], rbx
0x14000720c  jnz     loc_1400072F6
0x140007212  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rax
0x140007219  lea     rdi, [rbx+10h]
0x14000721d  mov     [rax+8], r14
0x140007221  mov     rcx, [rdi]; P
0x140007224  cmp     rcx, rdi
0x140007227  jz      short loc_140007257
0x140007229  cmp     [rcx+8], rdi
0x14000722d  jnz     loc_1400072F6
0x140007233  mov     rax, [rcx]
0x140007236  cmp     [rax+8], rcx
0x14000723a  jnz     loc_1400072F6
0x140007240  mov     [rdi], rax
0x140007243  xor     edx, edx; Tag
0x140007245  mov     [rax+8], rdi
0x140007249  call    cs:__imp_ExFreePoolWithTag
0x140007250  nop     dword ptr [rax+rax+00h]
0x140007255  jmp     short loc_140007221
0x140007257  xor     edx, edx; Tag
0x140007259  mov     rcx, rbx; P
0x14000725c  call    cs:__imp_ExFreePoolWithTag
0x140007263  nop     dword ptr [rax+rax+00h]
0x140007268  jmp     short loc_1400071EF
0x14000726a  call    PgmDereferenceDevice
0x14000726f  mov     rcx, cs:pPgmRegistryConfig
0x140007276  test    rcx, rcx
0x140007279  jz      short loc_1400072BD
0x14000727b  mov     rax, [rcx+10h]
0x14000727f  test    rax, rax
0x140007282  jz      short loc_1400072A4
0x140007284  xor     edx, edx; Tag
0x140007286  mov     rcx, rax; P
0x140007289  call    cs:__imp_ExFreePoolWithTag
0x140007290  nop     dword ptr [rax+rax+00h]
0x140007295  mov     rcx, cs:pPgmRegistryConfig; P
0x14000729c  mov     qword ptr [rcx+10h], 0
0x1400072a4  xor     edx, edx; Tag
0x1400072a6  call    cs:__imp_ExFreePoolWithTag
0x1400072ad  nop     dword ptr [rax+rax+00h]
0x1400072b2  mov     cs:pPgmRegistryConfig, 0
0x1400072bd  lea     rbx, WPP_MAIN_CB.Queue+10h
0x1400072c4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h; P
0x1400072cb  cmp     rcx, rbx
0x1400072ce  jz      short loc_1400072FD
0x1400072d0  cmp     [rcx+8], rbx
0x1400072d4  jnz     short loc_1400072F6
0x1400072d6  mov     rax, [rcx]
0x1400072d9  cmp     [rax+8], rcx
0x1400072dd  jnz     short loc_1400072F6
0x1400072df  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x1400072e6  xor     r8d, r8d
0x1400072e9  xor     edx, edx
0x1400072eb  mov     [rax+8], rbx
0x1400072ef  call    PgmDestroyAddress
0x1400072f4  jmp     short loc_1400072C4
0x1400072f6  mov     ecx, 3
0x1400072fb  int     29h; Win8: RtlFailFast(ecx)
0x1400072fd  lea     rcx, Lookaside; Lookaside
0x140007304  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000730b  nop     dword ptr [rax+rax+00h]
0x140007310  mov     rcx, cs:DestinationString.Buffer; P
0x140007317  xor     edx, edx; Tag
0x140007319  call    cs:__imp_ExFreePoolWithTag
0x140007320  nop     dword ptr [rax+rax+00h]
0x140007325  mov     rcx, cs:Object; Object
0x14000732c  test    rcx, rcx
0x14000732f  jz      short loc_14000734F
0x140007331  mov     cs:byte_140021D68, 0
0x140007338  call    cs:__imp_ObfDereferenceObject
0x14000733f  nop     dword ptr [rax+rax+00h]
0x140007344  mov     cs:Object, 0
0x14000734f  mov     rcx, cs:PgmSecurityDescriptor; P
0x140007356  test    rcx, rcx
0x140007359  jz      short loc_140007374
0x14000735b  xor     edx, edx; Tag
0x14000735d  call    cs:__imp_ExFreePoolWithTag
0x140007364  nop     dword ptr [rax+rax+00h]
0x140007369  mov     cs:PgmSecurityDescriptor, 0
0x140007374  call    wil_UninitializeFeatureStaging
0x140007379  add     rsp, 38h
0x14000737d  pop     r15
0x14000737f  pop     r14
0x140007381  pop     rdi
0x140007382  pop     rbx
0x140007383  retn
```
