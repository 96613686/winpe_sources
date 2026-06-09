# VmpWholeDiskRemoved(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140014838`
- end: `0x1400149e1`
- name: `?VmpWholeDiskRemoved@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `425`
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
- `0x140014838`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140014928`
- `ntoskrnl!IoAllocateWorkItem` at `0x140014928`
- `ntoskrnl!ObfReferenceObject` at `0x140014910`
- `ntoskrnl!ObfReferenceObject` at `0x140014910`
- `ntoskrnl!IoFreeWorkItem` at `0x14001496f`
- `ntoskrnl!IoFreeWorkItem` at `0x14001496f`
- `ntoskrnl!IoQueueWorkItem` at `0x1400149ac`
- `ntoskrnl!IoQueueWorkItem` at `0x1400149ac`

## pseudocode

```c
__int64 __fastcall VmpWholeDiskRemoved(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PVOID *MasterIrp; // rsi
  unsigned __int64 v6; // rcx
  struct _IO_WORKITEM *WorkItem; // rdi
  char v8; // al
  bool v9; // zf
  _OWORD *v10; // rax
  struct VM_ROOT_EXTENSION **v11; // r8
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
    LODWORD(WorkItem) = (*(__int64 (__fastcall **)(struct _IO_WORKITEM *, char *))(*((_QWORD *)a1 + 49) + 48LL))(
                          WorkItem,
                          &v12);
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
    *((_DWORD *)v10 + 4) = 3;
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
0x140014838  mov     [rsp+arg_0], rbx
0x14001483d  mov     [rsp+arg_10], rsi
0x140014842  push    rdi
0x140014843  sub     rsp, 20h
0x140014847  mov     rax, [rdx+0B8h]
0x14001484e  mov     rbx, rcx
0x140014851  mov     [rsp+28h+arg_8], 0
0x140014856  cmp     dword ptr [rax+10h], 8
0x14001485a  jnb     short loc_140014866
0x14001485c  mov     eax, 0C000000Dh
0x140014861  jmp     loc_1400149D0
0x140014866  mov     rsi, [rdx+18h]
0x14001486a  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x14001486f  mov     rdi, [rsi]
0x140014872  xor     al, al
0x140014874  cmp     qword ptr [rbx+188h], 0
0x14001487c  mov     [rsp+28h+arg_8], al
0x140014880  jz      short loc_1400148B8
0x140014882  mov     rcx, rbx
0x140014885  call    VmpRestoreExtensionDriver
0x14001488a  mov     rax, [rbx+188h]
0x140014891  lea     rdx, [rsp+28h+arg_8]
0x140014896  mov     rcx, rdi
0x140014899  mov     rax, [rax+30h]
0x14001489d  call    _guard_dispatch_icall
0x1400148a2  mov     rcx, rbx
0x1400148a5  mov     edi, eax
0x1400148a7  call    VmpPageExtensionDriver
0x1400148ac  test    edi, edi
0x1400148ae  js      loc_1400149C6
0x1400148b4  mov     al, [rsp+28h+arg_8]
0x1400148b8  xor     edi, edi
0x1400148ba  test    al, al
0x1400148bc  jz      loc_1400149C6
0x1400148c2  call    ??2VM_ALLOCATED_OBJECT@@SAPEAX_K@Z; VM_ALLOCATED_OBJECT::operator new(unsigned __int64)
0x1400148c7  test    rax, rax
0x1400148ca  jz      loc_1400149BA
0x1400148d0  xor     ecx, ecx
0x1400148d2  xorps   xmm0, xmm0
0x1400148d5  movups  xmmword ptr [rax], xmm0
0x1400148d8  movups  xmmword ptr [rax+10h], xmm0
0x1400148dc  mov     [rax+20h], rcx
0x1400148e0  lea     ecx, [rdi+3]
0x1400148e3  mov     [rax+10h], ecx
0x1400148e6  mov     rdx, [rsi]
0x1400148e9  mov     [rax+18h], rdx
0x1400148ed  lea     rdx, [rbx+0B8h]
0x1400148f4  mov     r8, [rdx+8]
0x1400148f8  cmp     [r8], rdx
0x1400148fb  jz      short loc_1400148FF
0x1400148fd  int     29h; Win8: RtlFailFast(ecx)
0x1400148ff  mov     [rax], rdx
0x140014902  mov     [rax+8], r8
0x140014906  mov     [r8], rax
0x140014909  mov     [rdx+8], rax
0x14001490d  mov     rcx, [rsi]; Object
0x140014910  call    cs:__imp_ObfReferenceObject
0x140014917  nop     dword ptr [rax+rax+00h]
0x14001491c  cmp     [rbx+0C8h], dil
0x140014923  jnz     short loc_140014943
0x140014925  mov     rcx, [rbx]; DeviceObject
0x140014928  call    cs:__imp_IoAllocateWorkItem
0x14001492f  nop     dword ptr [rax+rax+00h]
0x140014934  mov     rdi, rax
0x140014937  test    rax, rax
0x14001493a  jz      short loc_140014943
0x14001493c  mov     byte ptr [rbx+0C8h], 1
0x140014943  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140014946  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x14001494b  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x14001494e  call    ?VmpTestAcquireConfig@@YAEPEAVVM_ROOT_EXTENSION@@@Z; VmpTestAcquireConfig(VM_ROOT_EXTENSION *)
0x140014953  test    al, al
0x140014955  jz      short loc_140014994
0x140014957  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x14001495a  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x14001495f  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140014962  call    ?VmpProcessDiskNotifications@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpProcessDiskNotifications(VM_ROOT_EXTENSION *)
0x140014967  test    rdi, rdi
0x14001496a  jz      short loc_140014982
0x14001496c  mov     rcx, rdi; IoWorkItem
0x14001496f  call    cs:__imp_IoFreeWorkItem
0x140014976  nop     dword ptr [rax+rax+00h]
0x14001497b  mov     byte ptr [rbx+0C8h], 0
0x140014982  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140014985  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x14001498a  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x14001498d  call    ?VmpReleaseConfig@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseConfig(VM_ROOT_EXTENSION *)
0x140014992  jmp     short loc_1400149C2
0x140014994  test    rdi, rdi
0x140014997  jz      short loc_1400149C2
0x140014999  mov     r9, rdi; Context
0x14001499c  lea     rdx, VmpProcessDiskNotificationsWorkRoutine; WorkerRoutine
0x1400149a3  mov     r8d, 1; QueueType
0x1400149a9  mov     rcx, rdi; IoWorkItem
0x1400149ac  call    cs:__imp_IoQueueWorkItem
0x1400149b3  nop     dword ptr [rax+rax+00h]
0x1400149b8  jmp     short loc_1400149C2
0x1400149ba  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x1400149bd  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x1400149c2  xor     eax, eax
0x1400149c4  jmp     short loc_1400149D0
0x1400149c6  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x1400149c9  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x1400149ce  mov     eax, edi
0x1400149d0  mov     rbx, [rsp+28h+arg_0]
0x1400149d5  mov     rsi, [rsp+28h+arg_10]
0x1400149da  add     rsp, 20h
0x1400149de  pop     rdi
0x1400149df  retn
```
