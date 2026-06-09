# VmpPartitionRemoved(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140012b3c`
- end: `0x140012ceb`
- name: `?VmpPartitionRemoved@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x140002ea0`

## callees

- `0x140003170`
- `0x140003990`
- `0x1400039c0`
- `0x140003f50`
- `0x1400047f0`
- `0x14000e300`
- `0x14000e888`
- `0x140012b3c`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140012c2e`
- `ntoskrnl!IoAllocateWorkItem` at `0x140012c2e`
- `ntoskrnl!ObfReferenceObject` at `0x140012c07`
- `ntoskrnl!ObfReferenceObject` at `0x140012c16`
- `ntoskrnl!ObfReferenceObject` at `0x140012c07`
- `ntoskrnl!ObfReferenceObject` at `0x140012c16`
- `ntoskrnl!IoFreeWorkItem` at `0x140012c79`
- `ntoskrnl!IoFreeWorkItem` at `0x140012c79`
- `ntoskrnl!IoQueueWorkItem` at `0x140012cb6`
- `ntoskrnl!IoQueueWorkItem` at `0x140012cb6`

## pseudocode

```c
__int64 __fastcall VmpPartitionRemoved(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IRP *MasterIrp; // rdi
  unsigned __int64 v6; // rcx
  int v7; // esi
  _OWORD *v8; // rax
  struct VM_ROOT_EXTENSION **v9; // rdx
  PMDL MdlAddress; // rcx
  struct _IO_WORKITEM *WorkItem; // rdi
  unsigned __int8 v12; // [rsp+48h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v12 = 0;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x18 )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  VmpAcquireDevices(a1);
  v7 = VmpPartitionRemovedImmediate(
         a1,
         (struct _DEVICE_OBJECT *)MasterIrp->MdlAddress,
         *(struct _DEVICE_OBJECT **)&MasterIrp->Type,
         *(struct _PARTITION_INFORMATION_EX **)&MasterIrp->Flags,
         &v12);
  if ( v7 >= 0 && v12 )
  {
    v8 = VM_ALLOCATED_OBJECT::operator new(v6);
    if ( v8 )
    {
      *v8 = 0;
      v8[1] = 0;
      *((_QWORD *)v8 + 4) = 0;
      *((_DWORD *)v8 + 4) = 2;
      *((_QWORD *)v8 + 3) = MasterIrp->MdlAddress;
      *((_QWORD *)v8 + 4) = *(_QWORD *)&MasterIrp->Type;
      v9 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)a1 + 24);
      if ( *v9 != (struct VM_ROOT_EXTENSION *)((char *)a1 + 184) )
        __fastfail(3u);
      *(_QWORD *)v8 = (char *)a1 + 184;
      *((_QWORD *)v8 + 1) = v9;
      *v9 = (struct VM_ROOT_EXTENSION *)v8;
      *((_QWORD *)a1 + 24) = v8;
      MdlAddress = MasterIrp->MdlAddress;
      if ( MdlAddress )
        ObfReferenceObject(MdlAddress);
      ObfReferenceObject(*(PVOID *)&MasterIrp->Type);
      if ( *((_BYTE *)a1 + 200) )
      {
        WorkItem = 0;
      }
      else
      {
        WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)a1);
        if ( WorkItem )
          *((_BYTE *)a1 + 200) = 1;
      }
      VmpReleaseDevices((struct _KMUTANT *)a1);
      if ( VmpTestAcquireConfig(a1) )
      {
        VmpAcquireDevices(a1);
        VmpProcessDiskNotifications(a1);
        if ( WorkItem )
        {
          IoFreeWorkItem(WorkItem);
          *((_BYTE *)a1 + 200) = 0;
        }
        VmpReleaseDevices((struct _KMUTANT *)a1);
        VmpReleaseConfig(a1);
      }
      else if ( WorkItem )
      {
        IoQueueWorkItem(WorkItem, VmpProcessDiskNotificationsWorkRoutine, DelayedWorkQueue, WorkItem);
      }
    }
    else
    {
      VmpReleaseDevices((struct _KMUTANT *)a1);
    }
    return 0;
  }
  else
  {
    VmpReleaseDevices((struct _KMUTANT *)a1);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x140012b3c  mov     [rsp+arg_0], rbx
0x140012b41  mov     [rsp+arg_10], rsi
0x140012b46  push    rdi
0x140012b47  sub     rsp, 30h
0x140012b4b  mov     rax, [rdx+0B8h]
0x140012b52  mov     rbx, rcx
0x140012b55  mov     [rsp+38h+arg_8], 0
0x140012b5a  cmp     dword ptr [rax+10h], 18h
0x140012b5e  jnb     short loc_140012B6A
0x140012b60  mov     eax, 0C000000Dh
0x140012b65  jmp     loc_140012CDA
0x140012b6a  mov     rdi, [rdx+18h]
0x140012b6e  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x140012b73  mov     r9, [rdi+10h]; struct _PARTITION_INFORMATION_EX *
0x140012b77  lea     rax, [rsp+38h+arg_8]
0x140012b7c  mov     r8, [rdi]; struct _DEVICE_OBJECT *
0x140012b7f  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012b82  mov     rdx, [rdi+8]; struct _DEVICE_OBJECT *
0x140012b86  mov     [rsp+38h+var_18], rax; unsigned __int8 *
0x140012b8b  call    ?VmpPartitionRemovedImmediate@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@1PEAU_PARTITION_INFORMATION_EX@@PEAE@Z; VmpPartitionRemovedImmediate(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_PARTITION_INFORMATION_EX *,uchar *)
0x140012b90  mov     esi, eax
0x140012b92  test    eax, eax
0x140012b94  js      loc_140012CD0
0x140012b9a  cmp     [rsp+38h+arg_8], 0
0x140012b9f  jz      loc_140012CD0
0x140012ba5  call    ??2VM_ALLOCATED_OBJECT@@SAPEAX_K@Z; VM_ALLOCATED_OBJECT::operator new(unsigned __int64)
0x140012baa  test    rax, rax
0x140012bad  jz      loc_140012CC4
0x140012bb3  xor     ecx, ecx
0x140012bb5  xorps   xmm0, xmm0
0x140012bb8  movups  xmmword ptr [rax], xmm0
0x140012bbb  movups  xmmword ptr [rax+10h], xmm0
0x140012bbf  mov     [rax+20h], rcx
0x140012bc3  mov     dword ptr [rax+10h], 2
0x140012bca  mov     rcx, [rdi+8]
0x140012bce  mov     [rax+18h], rcx
0x140012bd2  mov     rcx, [rdi]
0x140012bd5  mov     [rax+20h], rcx
0x140012bd9  lea     rcx, [rbx+0B8h]
0x140012be0  mov     rdx, [rcx+8]
0x140012be4  cmp     [rdx], rcx
0x140012be7  jz      short loc_140012BF0
0x140012be9  mov     ecx, 3
0x140012bee  int     29h; Win8: RtlFailFast(ecx)
0x140012bf0  mov     [rax], rcx
0x140012bf3  mov     [rax+8], rdx
0x140012bf7  mov     [rdx], rax
0x140012bfa  mov     [rcx+8], rax
0x140012bfe  mov     rcx, [rdi+8]; Object
0x140012c02  test    rcx, rcx
0x140012c05  jz      short loc_140012C13
0x140012c07  call    cs:__imp_ObfReferenceObject
0x140012c0e  nop     dword ptr [rax+rax+00h]
0x140012c13  mov     rcx, [rdi]; Object
0x140012c16  call    cs:__imp_ObfReferenceObject
0x140012c1d  nop     dword ptr [rax+rax+00h]
0x140012c22  cmp     byte ptr [rbx+0C8h], 0
0x140012c29  jnz     short loc_140012C4B
0x140012c2b  mov     rcx, [rbx]; DeviceObject
0x140012c2e  call    cs:__imp_IoAllocateWorkItem
0x140012c35  nop     dword ptr [rax+rax+00h]
0x140012c3a  mov     rdi, rax
0x140012c3d  test    rax, rax
0x140012c40  jz      short loc_140012C4D
0x140012c42  mov     byte ptr [rbx+0C8h], 1
0x140012c49  jmp     short loc_140012C4D
0x140012c4b  xor     edi, edi
0x140012c4d  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012c50  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140012c55  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012c58  call    ?VmpTestAcquireConfig@@YAEPEAVVM_ROOT_EXTENSION@@@Z; VmpTestAcquireConfig(VM_ROOT_EXTENSION *)
0x140012c5d  test    al, al
0x140012c5f  jz      short loc_140012C9E
0x140012c61  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012c64  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x140012c69  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012c6c  call    ?VmpProcessDiskNotifications@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpProcessDiskNotifications(VM_ROOT_EXTENSION *)
0x140012c71  test    rdi, rdi
0x140012c74  jz      short loc_140012C8C
0x140012c76  mov     rcx, rdi; IoWorkItem
0x140012c79  call    cs:__imp_IoFreeWorkItem
0x140012c80  nop     dword ptr [rax+rax+00h]
0x140012c85  mov     byte ptr [rbx+0C8h], 0
0x140012c8c  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012c8f  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140012c94  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012c97  call    ?VmpReleaseConfig@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseConfig(VM_ROOT_EXTENSION *)
0x140012c9c  jmp     short loc_140012CCC
0x140012c9e  test    rdi, rdi
0x140012ca1  jz      short loc_140012CCC
0x140012ca3  mov     r9, rdi; Context
0x140012ca6  lea     rdx, VmpProcessDiskNotificationsWorkRoutine; WorkerRoutine
0x140012cad  mov     r8d, 1; QueueType
0x140012cb3  mov     rcx, rdi; IoWorkItem
0x140012cb6  call    cs:__imp_IoQueueWorkItem
0x140012cbd  nop     dword ptr [rax+rax+00h]
0x140012cc2  jmp     short loc_140012CCC
0x140012cc4  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012cc7  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140012ccc  xor     eax, eax
0x140012cce  jmp     short loc_140012CDA
0x140012cd0  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140012cd3  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140012cd8  mov     eax, esi
0x140012cda  mov     rbx, [rsp+38h+arg_0]
0x140012cdf  mov     rsi, [rsp+38h+arg_10]
0x140012ce4  add     rsp, 30h
0x140012ce8  pop     rdi
0x140012ce9  retn
```
