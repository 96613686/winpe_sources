# VmpPartitionArrived(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x1400127f0`
- end: `0x14001295c`
- name: `?VmpPartitionArrived@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140002ea0`

## callees

- `0x140003170`
- `0x140003990`
- `0x140003f50`
- `0x14000e54c`
- `0x1400127f0`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x1400128f0`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400128f0`
- `ntoskrnl!ObfReferenceObject` at `0x1400128c9`
- `ntoskrnl!ObfReferenceObject` at `0x1400128d8`
- `ntoskrnl!ObfReferenceObject` at `0x1400128c9`
- `ntoskrnl!ObfReferenceObject` at `0x1400128d8`
- `ntoskrnl!IoQueueWorkItem` at `0x14001291b`
- `ntoskrnl!IoQueueWorkItem` at `0x14001291b`

## pseudocode

```c
__int64 __fastcall VmpPartitionArrived(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IRP *MasterIrp; // rdi
  unsigned __int64 v6; // rcx
  int v7; // esi
  _OWORD *v8; // rax
  struct VM_ROOT_EXTENSION **v9; // rdx
  struct _IO_WORKITEM *WorkItem; // rax
  unsigned __int8 v12; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 v13; // [rsp+60h] [rbp+18h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v12 = 0;
  v13 = 0;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x18 || !CurrentStackLocation->Parameters.Read.Length )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  VmpAcquireDevices(a1);
  v7 = VmpPartitionArrivedImmediate(
         a1,
         (struct _DEVICE_OBJECT *)MasterIrp->MdlAddress,
         *(struct _DEVICE_OBJECT **)&MasterIrp->Type,
         *(struct _PARTITION_INFORMATION_EX **)&MasterIrp->Flags,
         &v12,
         &v13);
  if ( v7 >= 0 && v12 )
  {
    v8 = VM_ALLOCATED_OBJECT::operator new(v6);
    if ( v8 )
    {
      *v8 = 0;
      v8[1] = 0;
      *((_QWORD *)v8 + 4) = 0;
      *((_DWORD *)v8 + 4) = 1;
      *((_QWORD *)v8 + 3) = MasterIrp->MdlAddress;
      *((_QWORD *)v8 + 4) = *(_QWORD *)&MasterIrp->Type;
      v9 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)a1 + 24);
      if ( *v9 != (struct VM_ROOT_EXTENSION *)((char *)a1 + 184) )
        __fastfail(3u);
      *(_QWORD *)v8 = (char *)a1 + 184;
      *((_QWORD *)v8 + 1) = v9;
      *v9 = (struct VM_ROOT_EXTENSION *)v8;
      *((_QWORD *)a1 + 24) = v8;
      ObfReferenceObject(MasterIrp->MdlAddress);
      ObfReferenceObject(*(PVOID *)&MasterIrp->Type);
      if ( !*((_BYTE *)a1 + 200) )
      {
        WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)a1);
        if ( WorkItem )
        {
          *((_BYTE *)a1 + 200) = 1;
          IoQueueWorkItem(WorkItem, VmpProcessDiskNotificationsWorkRoutine, DelayedWorkQueue, WorkItem);
        }
      }
    }
    else
    {
      v7 = 0;
    }
  }
  VmpReleaseDevices((struct _KMUTANT *)a1);
  if ( v7 >= 0 )
  {
    LOBYTE(MasterIrp->Type) = v13;
    a2->IoStatus.Information = 1;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400127f0  mov     [rsp+arg_0], rbx
0x1400127f5  push    rbp
0x1400127f6  push    rsi
0x1400127f7  push    rdi
0x1400127f8  sub     rsp, 30h
0x1400127fc  mov     rax, [rdx+0B8h]
0x140012803  mov     rbp, rdx
0x140012806  mov     [rsp+48h+arg_8], 0
0x14001280b  mov     rbx, rcx
0x14001280e  mov     [rsp+48h+arg_10], 0
0x140012813  cmp     dword ptr [rax+10h], 18h
0x140012817  jb      loc_140012949
0x14001281d  cmp     dword ptr [rax+8], 1
0x140012821  jb      loc_140012949
0x140012827  mov     rdi, [rdx+18h]
0x14001282b  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x140012830  mov     r9, [rdi+10h]; struct _PARTITION_INFORMATION_EX *
0x140012834  lea     rax, [rsp+48h+arg_10]
0x140012839  mov     r8, [rdi]; struct _DEVICE_OBJECT *
0x14001283c  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x14001283f  mov     rdx, [rdi+8]; struct _DEVICE_OBJECT *
0x140012843  mov     [rsp+48h+var_20], rax; unsigned __int8 *
0x140012848  lea     rax, [rsp+48h+arg_8]
0x14001284d  mov     [rsp+48h+var_28], rax; unsigned __int8 *
0x140012852  call    ?VmpPartitionArrivedImmediate@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@1PEAU_PARTITION_INFORMATION_EX@@PEAE3@Z; VmpPartitionArrivedImmediate(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_PARTITION_INFORMATION_EX *,uchar *,uchar *)
0x140012857  mov     esi, eax
0x140012859  test    eax, eax
0x14001285b  js      loc_14001292B
0x140012861  cmp     [rsp+48h+arg_8], 0
0x140012866  jz      loc_14001292B
0x14001286c  call    ??2VM_ALLOCATED_OBJECT@@SAPEAX_K@Z; VM_ALLOCATED_OBJECT::operator new(unsigned __int64)
0x140012871  test    rax, rax
0x140012874  jz      loc_140012929
0x14001287a  xor     ecx, ecx
0x14001287c  xorps   xmm0, xmm0
0x14001287f  movups  xmmword ptr [rax], xmm0
0x140012882  movups  xmmword ptr [rax+10h], xmm0
0x140012886  mov     [rax+20h], rcx
0x14001288a  mov     dword ptr [rax+10h], 1
0x140012891  mov     rcx, [rdi+8]
0x140012895  mov     [rax+18h], rcx
0x140012899  mov     rcx, [rdi]
0x14001289c  mov     [rax+20h], rcx
0x1400128a0  lea     rcx, [rbx+0B8h]
0x1400128a7  mov     rdx, [rcx+8]
0x1400128ab  cmp     [rdx], rcx
0x1400128ae  jz      short loc_1400128B7
0x1400128b0  mov     ecx, 3
0x1400128b5  int     29h; Win8: RtlFailFast(ecx)
0x1400128b7  mov     [rax], rcx
0x1400128ba  mov     [rax+8], rdx
0x1400128be  mov     [rdx], rax
0x1400128c1  mov     [rcx+8], rax
0x1400128c5  mov     rcx, [rdi+8]; Object
0x1400128c9  call    cs:__imp_ObfReferenceObject
0x1400128d0  nop     dword ptr [rax+rax+00h]
0x1400128d5  mov     rcx, [rdi]; Object
0x1400128d8  call    cs:__imp_ObfReferenceObject
0x1400128df  nop     dword ptr [rax+rax+00h]
0x1400128e4  cmp     byte ptr [rbx+0C8h], 0
0x1400128eb  jnz     short loc_14001292B
0x1400128ed  mov     rcx, [rbx]; DeviceObject
0x1400128f0  call    cs:__imp_IoAllocateWorkItem
0x1400128f7  nop     dword ptr [rax+rax+00h]
0x1400128fc  test    rax, rax
0x1400128ff  jz      short loc_14001292B
0x140012901  mov     r9, rax; Context
0x140012904  mov     byte ptr [rbx+0C8h], 1
0x14001290b  mov     r8d, 1; QueueType
0x140012911  lea     rdx, VmpProcessDiskNotificationsWorkRoutine; WorkerRoutine
0x140012918  mov     rcx, rax; IoWorkItem
0x14001291b  call    cs:__imp_IoQueueWorkItem
0x140012922  nop     dword ptr [rax+rax+00h]
0x140012927  jmp     short loc_14001292B
0x140012929  xor     esi, esi
0x14001292b  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x14001292e  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140012933  test    esi, esi
0x140012935  js      short loc_140012945
0x140012937  mov     al, [rsp+48h+arg_10]
0x14001293b  mov     [rdi], al
0x14001293d  mov     qword ptr [rbp+38h], 1
0x140012945  mov     eax, esi
0x140012947  jmp     short loc_14001294E
0x140012949  mov     eax, 0C000000Dh
0x14001294e  mov     rbx, [rsp+48h+arg_0]
0x140012953  add     rsp, 30h
0x140012957  pop     rdi
0x140012958  pop     rsi
0x140012959  pop     rbp
0x14001295a  retn
```
