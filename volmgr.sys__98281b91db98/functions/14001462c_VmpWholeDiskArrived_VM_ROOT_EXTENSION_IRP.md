# VmpWholeDiskArrived(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x14001462c`
- end: `0x1400147d4`
- name: `?VmpWholeDiskArrived@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x140002ea0`

## callees

- `0x140003170`
- `0x140003990`
- `0x1400039c0`
- `0x140003e70`
- `0x140003ef0`
- `0x140003f50`
- `0x1400047f0`
- `0x140005090`
- `0x14000e300`
- `0x14001462c`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x14001471b`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001471b`
- `ntoskrnl!ObfReferenceObject` at `0x140014703`
- `ntoskrnl!ObfReferenceObject` at `0x140014703`
- `ntoskrnl!IoFreeWorkItem` at `0x140014762`
- `ntoskrnl!IoFreeWorkItem` at `0x140014762`
- `ntoskrnl!IoQueueWorkItem` at `0x14001479f`
- `ntoskrnl!IoQueueWorkItem` at `0x14001479f`

## pseudocode

```c
__int64 __fastcall VmpWholeDiskArrived(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PVOID *MasterIrp; // rsi
  unsigned __int64 v6; // rcx
  struct _IO_WORKITEM *WorkItem; // rdi
  char v8; // al
  bool v9; // zf
  _OWORD *v10; // rax
  struct VM_ROOT_EXTENSION **v11; // rdx
  char v12; // [rsp+38h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v12 = 0;
  if ( CurrentStackLocation->Parameters.Create.Options < 8 )
    return 3221225485LL;
  MasterIrp = (PVOID *)a2->AssociatedIrp.MasterIrp;
  VmpAcquireDevices(a1);
  WorkItem = (struct _IO_WORKITEM *)*MasterIrp;
  v8 = 0;
  v9 = *((_QWORD *)a1 + 49) == 0;
  v12 = 0;
  if ( !v9 )
  {
    VmpRestoreExtensionDriver((__int64)a1);
    LODWORD(WorkItem) = (**((__int64 (__fastcall ***)(struct _IO_WORKITEM *, char *))a1 + 49))(WorkItem, &v12);
    VmpPageExtensionDriver((__int64)a1);
    if ( (int)WorkItem < 0 )
    {
LABEL_21:
      VmpReleaseDevices((struct _KMUTANT *)a1);
      return (unsigned int)WorkItem;
    }
    v8 = v12;
  }
  WorkItem = 0;
  if ( !v8 )
    goto LABEL_21;
  v10 = VM_ALLOCATED_OBJECT::operator new(v6);
  if ( v10 )
  {
    *v10 = 0;
    v10[1] = 0;
    *((_QWORD *)v10 + 4) = 0;
    *((_DWORD *)v10 + 4) = 0;
    *((_QWORD *)v10 + 3) = *MasterIrp;
    v11 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)a1 + 24);
    if ( *v11 != (struct VM_ROOT_EXTENSION *)((char *)a1 + 184) )
      __fastfail(3u);
    *(_QWORD *)v10 = (char *)a1 + 184;
    *((_QWORD *)v10 + 1) = v11;
    *v11 = (struct VM_ROOT_EXTENSION *)v10;
    *((_QWORD *)a1 + 24) = v10;
    ObfReferenceObject(*MasterIrp);
    if ( !*((_BYTE *)a1 + 200) )
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

```

## disassembly

```asm
0x14001462c  mov     [rsp+arg_0], rbx
0x140014631  mov     [rsp+arg_10], rsi
0x140014636  push    rdi
0x140014637  sub     rsp, 20h
0x14001463b  mov     rax, [rdx+0B8h]
0x140014642  mov     rbx, rcx
0x140014645  mov     [rsp+28h+arg_8], 0
0x14001464a  cmp     dword ptr [rax+10h], 8
0x14001464e  jnb     short loc_14001465A
0x140014650  mov     eax, 0C000000Dh
0x140014655  jmp     loc_1400147C3
0x14001465a  mov     rsi, [rdx+18h]
0x14001465e  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x140014663  mov     rdi, [rsi]
0x140014666  xor     al, al
0x140014668  cmp     qword ptr [rbx+188h], 0
0x140014670  mov     [rsp+28h+arg_8], al
0x140014674  jz      short loc_1400146AB
0x140014676  mov     rcx, rbx
0x140014679  call    VmpRestoreExtensionDriver
0x14001467e  mov     rax, [rbx+188h]
0x140014685  lea     rdx, [rsp+28h+arg_8]
0x14001468a  mov     rcx, rdi
0x14001468d  mov     rax, [rax]
0x140014690  call    _guard_dispatch_icall
0x140014695  mov     rcx, rbx
0x140014698  mov     edi, eax
0x14001469a  call    VmpPageExtensionDriver
0x14001469f  test    edi, edi
0x1400146a1  js      loc_1400147B9
0x1400146a7  mov     al, [rsp+28h+arg_8]
0x1400146ab  xor     edi, edi
0x1400146ad  test    al, al
0x1400146af  jz      loc_1400147B9
0x1400146b5  call    ??2VM_ALLOCATED_OBJECT@@SAPEAX_K@Z; VM_ALLOCATED_OBJECT::operator new(unsigned __int64)
0x1400146ba  test    rax, rax
0x1400146bd  jz      loc_1400147AD
0x1400146c3  xor     ecx, ecx
0x1400146c5  xorps   xmm0, xmm0
0x1400146c8  movups  xmmword ptr [rax], xmm0
0x1400146cb  movups  xmmword ptr [rax+10h], xmm0
0x1400146cf  mov     [rax+20h], rcx
0x1400146d3  mov     [rax+10h], ecx
0x1400146d6  mov     rcx, [rsi]
0x1400146d9  mov     [rax+18h], rcx
0x1400146dd  lea     rcx, [rbx+0B8h]
0x1400146e4  mov     rdx, [rcx+8]
0x1400146e8  cmp     [rdx], rcx
0x1400146eb  jz      short loc_1400146F2
0x1400146ed  lea     ecx, [rdi+3]
0x1400146f0  int     29h; Win8: RtlFailFast(ecx)
0x1400146f2  mov     [rax], rcx
0x1400146f5  mov     [rax+8], rdx
0x1400146f9  mov     [rdx], rax
0x1400146fc  mov     [rcx+8], rax
0x140014700  mov     rcx, [rsi]; Object
0x140014703  call    cs:__imp_ObfReferenceObject
0x14001470a  nop     dword ptr [rax+rax+00h]
0x14001470f  cmp     [rbx+0C8h], dil
0x140014716  jnz     short loc_140014736
0x140014718  mov     rcx, [rbx]; DeviceObject
0x14001471b  call    cs:__imp_IoAllocateWorkItem
0x140014722  nop     dword ptr [rax+rax+00h]
0x140014727  mov     rdi, rax
0x14001472a  test    rax, rax
0x14001472d  jz      short loc_140014736
0x14001472f  mov     byte ptr [rbx+0C8h], 1
0x140014736  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140014739  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x14001473e  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140014741  call    ?VmpTestAcquireConfig@@YAEPEAVVM_ROOT_EXTENSION@@@Z; VmpTestAcquireConfig(VM_ROOT_EXTENSION *)
0x140014746  test    al, al
0x140014748  jz      short loc_140014787
0x14001474a  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x14001474d  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x140014752  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140014755  call    ?VmpProcessDiskNotifications@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpProcessDiskNotifications(VM_ROOT_EXTENSION *)
0x14001475a  test    rdi, rdi
0x14001475d  jz      short loc_140014775
0x14001475f  mov     rcx, rdi; IoWorkItem
0x140014762  call    cs:__imp_IoFreeWorkItem
0x140014769  nop     dword ptr [rax+rax+00h]
0x14001476e  mov     byte ptr [rbx+0C8h], 0
0x140014775  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140014778  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x14001477d  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140014780  call    ?VmpReleaseConfig@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseConfig(VM_ROOT_EXTENSION *)
0x140014785  jmp     short loc_1400147B5
0x140014787  test    rdi, rdi
0x14001478a  jz      short loc_1400147B5
0x14001478c  mov     r9, rdi; Context
0x14001478f  lea     rdx, VmpProcessDiskNotificationsWorkRoutine; WorkerRoutine
0x140014796  mov     r8d, 1; QueueType
0x14001479c  mov     rcx, rdi; IoWorkItem
0x14001479f  call    cs:__imp_IoQueueWorkItem
0x1400147a6  nop     dword ptr [rax+rax+00h]
0x1400147ab  jmp     short loc_1400147B5
0x1400147ad  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x1400147b0  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x1400147b5  xor     eax, eax
0x1400147b7  jmp     short loc_1400147C3
0x1400147b9  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x1400147bc  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x1400147c1  mov     eax, edi
0x1400147c3  mov     rbx, [rsp+28h+arg_0]
0x1400147c8  mov     rsi, [rsp+28h+arg_10]
0x1400147cd  add     rsp, 20h
0x1400147d1  pop     rdi
0x1400147d2  retn
```
