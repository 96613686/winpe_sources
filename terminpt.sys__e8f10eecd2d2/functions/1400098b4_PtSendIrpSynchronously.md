# PtSendIrpSynchronously

- ea: `0x1400098b4`
- end: `0x1400099e2`
- name: `PtSendIrpSynchronously`
- size: `302`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400092f0`

## callees

- `0x14000173c`
- `0x140001a80`
- `0x1400098b4`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000996d`
- `ntoskrnl!IofCallDriver` at `0x14000996d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009998`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009998`
- `ntoskrnl!KeInitializeEvent` at `0x140009910`
- `ntoskrnl!KeInitializeEvent` at `0x140009910`

## pseudocode

```c
__int64 __fastcall PtSendIrpSynchronously(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v6; // rax
  int v7; // edx
  unsigned int Status; // ebx
  int v9; // r8d
  __int64 v11; // [rsp+28h] [rbp-60h]
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      (__int64)Irp,
      a3,
      0x10u,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v6 = Irp->Tail.Overlay.CurrentStackLocation;
  v6[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)PtPnPComplete;
  v6[-1].Context = &Event;
  v6[-1].Control = -32;
  Status = IofCallDriver(DeviceObject, Irp);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = Irp->IoStatus.Status;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v9,
      0x11u,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids,
      v11);
  return Status;
}

```

## disassembly

```asm
0x1400098b4  push    rbx
0x1400098b6  push    rbp
0x1400098b7  push    rsi
0x1400098b8  push    rdi
0x1400098b9  push    r14
0x1400098bb  sub     rsp, 60h
0x1400098bf  xorps   xmm0, xmm0
0x1400098c2  xor     eax, eax
0x1400098c4  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x1400098c9  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x1400098ce  mov     rdi, rdx
0x1400098d1  mov     rsi, rcx
0x1400098d4  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400098db  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400098e2  lea     r14, WPP_75fd79d40e58354b8c24f648881272a9_Traceguids
0x1400098e9  jz      short loc_140009904
0x1400098eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400098f2  lea     r9d, [rax+10h]
0x1400098f6  mov     [rsp+88h+Timeout], r14
0x1400098fb  mov     rcx, [rcx+40h]
0x1400098ff  call    WPP_RECORDER_SF_s
0x140009904  xor     r8d, r8d; State
0x140009907  lea     rcx, [rsp+88h+Event]; Event
0x14000990c  lea     edx, [r8+1]; Type
0x140009910  call    cs:__imp_KeInitializeEvent
0x140009917  nop     dword ptr [rax+rax+00h]
0x14000991c  mov     rax, [rdi+0B8h]
0x140009923  lea     rcx, PtPnPComplete
0x14000992a  mov     rdx, rdi; Irp
0x14000992d  movups  xmm0, xmmword ptr [rax]
0x140009930  movups  xmmword ptr [rax-48h], xmm0
0x140009934  movups  xmm1, xmmword ptr [rax+10h]
0x140009938  movups  xmmword ptr [rax-38h], xmm1
0x14000993c  movups  xmm0, xmmword ptr [rax+20h]
0x140009940  movups  xmmword ptr [rax-28h], xmm0
0x140009944  movsd   xmm1, qword ptr [rax+30h]
0x140009949  movsd   qword ptr [rax-18h], xmm1
0x14000994e  mov     byte ptr [rax-45h], 0
0x140009952  mov     rax, [rdi+0B8h]
0x140009959  mov     [rax-10h], rcx
0x14000995d  lea     rcx, [rsp+88h+Event]
0x140009962  mov     [rax-8], rcx
0x140009966  mov     rcx, rsi; DeviceObject
0x140009969  mov     byte ptr [rax-45h], 0E0h
0x14000996d  call    cs:__imp_IofCallDriver
0x140009974  nop     dword ptr [rax+rax+00h]
0x140009979  mov     ebx, eax
0x14000997b  cmp     eax, 103h
0x140009980  jnz     short loc_1400099A7
0x140009982  xor     r9d, r9d; Alertable
0x140009985  mov     [rsp+88h+Timeout], 0; Timeout
0x14000998e  xor     r8d, r8d; WaitMode
0x140009991  lea     rcx, [rsp+88h+Event]; Object
0x140009996  xor     edx, edx; WaitReason
0x140009998  call    cs:__imp_KeWaitForSingleObject
0x14000999f  nop     dword ptr [rax+rax+00h]
0x1400099a4  mov     ebx, [rdi+30h]
0x1400099a7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400099ae  jz      short loc_1400099D4
0x1400099b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400099b7  mov     r9d, 11h
0x1400099bd  mov     [rsp+88h+var_50], ebx
0x1400099c1  mov     [rsp+88h+var_58], rsi
0x1400099c6  mov     [rsp+88h+Timeout], r14
0x1400099cb  mov     rcx, [rcx+40h]
0x1400099cf  call    WPP_RECORDER_SF_sqd
0x1400099d4  mov     eax, ebx
0x1400099d6  add     rsp, 60h
0x1400099da  pop     r14
0x1400099dc  pop     rdi
0x1400099dd  pop     rsi
0x1400099de  pop     rbp
0x1400099df  pop     rbx
0x1400099e0  retn
```
