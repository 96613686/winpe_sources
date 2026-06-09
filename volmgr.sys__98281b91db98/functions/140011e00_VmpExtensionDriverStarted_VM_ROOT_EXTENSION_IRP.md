# VmpExtensionDriverStarted(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140011e00`
- end: `0x140012034`
- name: `?VmpExtensionDriverStarted@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002ea0`

## callees

- `0x1400029e0`
- `0x140002a30`
- `0x140011e00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140011e4f`
- `ntoskrnl!ExAllocatePool2` at `0x140011e4f`

## pseudocode

```c
__int64 __fastcall VmpExtensionDriverStarted(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IRP *MasterIrp; // rbx
  __int64 Pool2; // rax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Create.Options < 0xF8 || CurrentStackLocation->Parameters.Read.Length < 0xA0 )
    return 3221225485LL;
  VmpAcquireAll(a1);
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  Pool2 = ExAllocatePool2(66, 248, 538987862);
  *((_QWORD *)a1 + 49) = Pool2;
  if ( Pool2 )
  {
    *(_OWORD *)Pool2 = *(_OWORD *)&MasterIrp->Type;
    *(_OWORD *)(Pool2 + 16) = *(_OWORD *)&MasterIrp->Flags;
    *(LIST_ENTRY *)(Pool2 + 32) = MasterIrp->ThreadListEntry;
    *(_OWORD *)(Pool2 + 48) = *(_OWORD *)&MasterIrp->IoStatus.Status;
    *(_OWORD *)(Pool2 + 64) = *(_OWORD *)&MasterIrp->RequestorMode;
    *(_OWORD *)(Pool2 + 80) = *(_OWORD *)&MasterIrp->UserEvent;
    *(union _IRP::$6B96A96ED958C92F2CB4B83EAB343043 *)(Pool2 + 96) = *(union _IRP::$6B96A96ED958C92F2CB4B83EAB343043 *)((char *)&MasterIrp->Overlay + 8);
    *(_OWORD *)(Pool2 + 112) = *(_OWORD *)&MasterIrp->UserBuffer;
    *(_OWORD *)(Pool2 + 128) = *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 1);
    *(_OWORD *)(Pool2 + 144) = *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 3);
    *(_OWORD *)(Pool2 + 160) = *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 5);
    *(_OWORD *)(Pool2 + 176) = *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 7);
    *(_OWORD *)(Pool2 + 192) = *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 9);
    *(_OWORD *)(Pool2 + 208) = *(_OWORD *)&MasterIrp[1].Type;
    *(_OWORD *)(Pool2 + 224) = *(_OWORD *)&MasterIrp[1].Flags;
    *(_QWORD *)(Pool2 + 240) = MasterIrp[1].ThreadListEntry.Flink;
    MasterIrp->MdlAddress = (PMDL)VmLogError;
    *(_QWORD *)&MasterIrp->Type = a1;
    *(_QWORD *)&MasterIrp->Flags = VmAcquireDevices;
    MasterIrp->AssociatedIrp.MasterIrp = (struct _IRP *)VmReleaseDevices;
    MasterIrp->ThreadListEntry.Flink = (struct _LIST_ENTRY *)VmAcquireAll;
    MasterIrp->ThreadListEntry.Blink = (struct _LIST_ENTRY *)VmReleaseAll;
    MasterIrp->IoStatus.Pointer = VmLoadExtensionDriver;
    MasterIrp->IoStatus.Information = (ULONG_PTR)VmUnloadExtensionDriver;
    *(_QWORD *)&MasterIrp->RequestorMode = VmVolumeRequestCompletionRoutine;
    MasterIrp->UserIosb = (PIO_STATUS_BLOCK)VmQueryBasicExtension;
    MasterIrp->UserEvent = (PKEVENT)VmQueryDynamicExtension;
    MasterIrp->Overlay.AllocationSize.QuadPart = (LONGLONG)VmFindNextDynamicExtension;
    MasterIrp->Overlay.AsynchronousParameters.UserApcContext = VmCreatePendingDynamicDevice;
    MasterIrp->CancelRoutine = (PDRIVER_CANCEL)VmDeletePendingDynamicDevice;
    MasterIrp->UserBuffer = VmCommitDevices;
    MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)VmQueryDeviceName;
    MasterIrp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)VmQueryUniqueIdBuffer;
    MasterIrp->Tail.Overlay.DriverContext[2] = VmFreezeBasicDeviceCreation;
    MasterIrp->Tail.Overlay.DriverContext[3] = VmSetDevicePowerState;
    MasterIrp->Tail.Overlay.Thread = (PETHREAD)VmQueryBootInformation;
    a2->IoStatus.Information = 160;
    VmpReleaseAll(a1);
    return 0;
  }
  else
  {
    VmpReleaseAll(a1);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140011e00  mov     [rsp+arg_0], rbx
0x140011e05  mov     [rsp+arg_8], rsi
0x140011e0a  push    rdi
0x140011e0b  sub     rsp, 20h
0x140011e0f  mov     rax, [rdx+0B8h]
0x140011e16  mov     rsi, rdx
0x140011e19  mov     rdi, rcx
0x140011e1c  cmp     dword ptr [rax+10h], 0F8h
0x140011e23  jb      loc_14001201E
0x140011e29  cmp     dword ptr [rax+8], 0A0h
0x140011e30  jb      loc_14001201E
0x140011e36  call    ?VmpAcquireAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireAll(VM_ROOT_EXTENSION *)
0x140011e3b  mov     rbx, [rsi+18h]
0x140011e3f  mov     edx, 0F8h
0x140011e44  mov     ecx, 42h ; 'B'
0x140011e49  mov     r8d, 20204D56h
0x140011e4f  call    cs:__imp_ExAllocatePool2
0x140011e56  nop     dword ptr [rax+rax+00h]
0x140011e5b  mov     [rdi+188h], rax
0x140011e62  mov     rcx, rax
0x140011e65  test    rax, rax
0x140011e68  jnz     short loc_140011E7C
0x140011e6a  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x140011e6d  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x140011e72  mov     eax, 0C000009Ah
0x140011e77  jmp     loc_140012023
0x140011e7c  movups  xmm0, xmmword ptr [rbx]
0x140011e7f  movups  xmmword ptr [rax], xmm0
0x140011e82  movups  xmm1, xmmword ptr [rbx+10h]
0x140011e86  movups  xmmword ptr [rax+10h], xmm1
0x140011e8a  movups  xmm0, xmmword ptr [rbx+20h]
0x140011e8e  movups  xmmword ptr [rax+20h], xmm0
0x140011e92  movups  xmm1, xmmword ptr [rbx+30h]
0x140011e96  movups  xmmword ptr [rax+30h], xmm1
0x140011e9a  movups  xmm0, xmmword ptr [rbx+40h]
0x140011e9e  movups  xmmword ptr [rax+40h], xmm0
0x140011ea2  movups  xmm1, xmmword ptr [rbx+50h]
0x140011ea6  movups  xmmword ptr [rax+50h], xmm1
0x140011eaa  movups  xmm0, xmmword ptr [rbx+60h]
0x140011eae  movups  xmmword ptr [rax+60h], xmm0
0x140011eb2  movups  xmm1, xmmword ptr [rbx+70h]
0x140011eb6  movups  xmmword ptr [rax+70h], xmm1
0x140011eba  movups  xmm0, xmmword ptr [rbx+80h]
0x140011ec1  movups  xmmword ptr [rax+80h], xmm0
0x140011ec8  movups  xmm1, xmmword ptr [rbx+90h]
0x140011ecf  movups  xmmword ptr [rax+90h], xmm1
0x140011ed6  movups  xmm0, xmmword ptr [rbx+0A0h]
0x140011edd  movups  xmmword ptr [rax+0A0h], xmm0
0x140011ee4  movups  xmm1, xmmword ptr [rbx+0B0h]
0x140011eeb  movups  xmmword ptr [rax+0B0h], xmm1
0x140011ef2  movups  xmm0, xmmword ptr [rbx+0C0h]
0x140011ef9  movups  xmmword ptr [rax+0C0h], xmm0
0x140011f00  movups  xmm1, xmmword ptr [rbx+0D0h]
0x140011f07  movups  xmmword ptr [rax+0D0h], xmm1
0x140011f0e  movups  xmm0, xmmword ptr [rbx+0E0h]
0x140011f15  movups  xmmword ptr [rax+0E0h], xmm0
0x140011f1c  mov     rax, [rbx+0F0h]
0x140011f23  mov     [rcx+0F0h], rax
0x140011f2a  lea     rax, VmLogError
0x140011f31  mov     [rbx+8], rax
0x140011f35  mov     rcx, rdi; struct VM_ROOT_EXTENSION *
0x140011f38  lea     rax, ?VmAcquireDevices@@YAXPEAX@Z; VmAcquireDevices(void *)
0x140011f3f  mov     [rbx], rdi
0x140011f42  mov     [rbx+10h], rax
0x140011f46  lea     rax, ?VmReleaseDevices@@YAXPEAX@Z; VmReleaseDevices(void *)
0x140011f4d  mov     [rbx+18h], rax
0x140011f51  lea     rax, ?VmAcquireAll@@YAXPEAX@Z; VmAcquireAll(void *)
0x140011f58  mov     [rbx+20h], rax
0x140011f5c  lea     rax, ?VmReleaseAll@@YAXPEAX@Z; VmReleaseAll(void *)
0x140011f63  mov     [rbx+28h], rax
0x140011f67  lea     rax, ?VmLoadExtensionDriver@@YAXPEAX@Z; VmLoadExtensionDriver(void *)
0x140011f6e  mov     [rbx+30h], rax
0x140011f72  lea     rax, ?VmUnloadExtensionDriver@@YAXPEAX@Z; VmUnloadExtensionDriver(void *)
0x140011f79  mov     [rbx+38h], rax
0x140011f7d  lea     rax, ?VmVolumeRequestCompletionRoutine@@YAXPEAU_IRP@@@Z; VmVolumeRequestCompletionRoutine(_IRP *)
0x140011f84  mov     [rbx+40h], rax
0x140011f88  lea     rax, ?VmQueryBasicExtension@@YAPEAXPEAXK_K1PEAPEAU_DEVICE_OBJECT@@@Z; VmQueryBasicExtension(void *,ulong,unsigned __int64,unsigned __int64,_DEVICE_OBJECT * *)
0x140011f8f  mov     [rbx+48h], rax
0x140011f93  lea     rax, ?VmQueryDynamicExtension@@YAPEAXPEAX0@Z; VmQueryDynamicExtension(void *,void *)
0x140011f9a  mov     [rbx+50h], rax
0x140011f9e  lea     rax, ?VmFindNextDynamicExtension@@YAPEAXPEAX0PEAPEAX@Z; VmFindNextDynamicExtension(void *,void *,void * *)
0x140011fa5  mov     [rbx+58h], rax
0x140011fa9  lea     rax, ?VmCreatePendingDynamicDevice@@YAJPEAX0@Z; VmCreatePendingDynamicDevice(void *,void *)
0x140011fb0  mov     [rbx+60h], rax
0x140011fb4  lea     rax, ?VmDeletePendingDynamicDevice@@YAXPEAX0@Z; VmDeletePendingDynamicDevice(void *,void *)
0x140011fbb  mov     [rbx+68h], rax
0x140011fbf  lea     rax, ?VmCommitDevices@@YAXPEAXKPEAU_VM_DEVICE_CHANGE@@@Z; VmCommitDevices(void *,ulong,_VM_DEVICE_CHANGE *)
0x140011fc6  mov     [rbx+70h], rax
0x140011fca  lea     rax, ?VmQueryDeviceName@@YAXPEAXPEAGK@Z; VmQueryDeviceName(void *,ushort *,ulong)
0x140011fd1  mov     [rbx+78h], rax
0x140011fd5  lea     rax, ?VmQueryUniqueIdBuffer@@YAJPEAXPEAGPEAE@Z; VmQueryUniqueIdBuffer(void *,ushort *,uchar *)
0x140011fdc  mov     [rbx+80h], rax
0x140011fe3  lea     rax, ?VmFreezeBasicDeviceCreation@@YAXPEAXPEAU_DEVICE_OBJECT@@@Z; VmFreezeBasicDeviceCreation(void *,_DEVICE_OBJECT *)
0x140011fea  mov     [rbx+88h], rax
0x140011ff1  lea     rax, ?VmSetDevicePowerState@@YAXPEAXW4_DEVICE_POWER_STATE@@@Z; VmSetDevicePowerState(void *,_DEVICE_POWER_STATE)
0x140011ff8  mov     [rbx+90h], rax
0x140011fff  lea     rax, ?VmQueryBootInformation@@YAXPEAXPEAPEAU_BOOTDISK_INFORMATION_LITE@@@Z; VmQueryBootInformation(void *,_BOOTDISK_INFORMATION_LITE * *)
0x140012006  mov     [rbx+98h], rax
0x14001200d  mov     qword ptr [rsi+38h], 0A0h
0x140012015  call    ?VmpReleaseAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseAll(VM_ROOT_EXTENSION *)
0x14001201a  xor     eax, eax
0x14001201c  jmp     short loc_140012023
0x14001201e  mov     eax, 0C000000Dh
0x140012023  mov     rbx, [rsp+28h+arg_0]
0x140012028  mov     rsi, [rsp+28h+arg_8]
0x14001202d  add     rsp, 20h
0x140012031  pop     rdi
0x140012032  retn
```
