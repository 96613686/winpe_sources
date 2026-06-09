# FilterCreateQueue_CompleteIrp

- ea: `0x140013f40`
- end: `0x140013fe2`
- name: `FilterCreateQueue_CompleteIrp`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400199e8`
- `0x14003a7a0`

## callees

- `0x140013f40`
- `0x14001977c`
- `0x14001b15c`
- `0x14001b218`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140013f4d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013f4d`
- `ntoskrnl!IoAllocateWorkItem` at `0x140013f68`
- `ntoskrnl!IoAllocateWorkItem` at `0x140013f68`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140013fd4`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140013fd4`

## pseudocode

```c
void __fastcall FilterCreateQueue_CompleteIrp(__int64 a1, IRP *a2, NTSTATUS a3)
{
  struct _IO_WORKITEM *WorkItem; // rax
  int v5; // edx
  int v6; // r8d

  a2->IoStatus.Status = a3;
  if ( !KeGetCurrentIrql() )
  {
LABEL_6:
    FreeResourcesObjectBag_IfCreateFailure(a2);
    CompleteCreateIrp(a2, v5, v6);
    return;
  }
  WorkItem = IoAllocateWorkItem(a2->Tail.Overlay.CurrentStackLocation->DeviceObject);
  if ( !WorkItem )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, a2);
    goto LABEL_6;
  }
  IoQueueWorkItemEx(WorkItem, FilterCreateQueue_CompleteIrpWorker, DelayedWorkQueue, a2);
}

```

## disassembly

```asm
0x140013f40  push    rbx
0x140013f42  sub     rsp, 20h
0x140013f46  mov     rbx, rdx
0x140013f49  mov     [rdx+30h], r8d
0x140013f4d  call    cs:__imp_KeGetCurrentIrql
0x140013f54  nop     dword ptr [rax+rax+00h]
0x140013f59  test    al, al
0x140013f5b  jz      short loc_140013FAA
0x140013f5d  mov     rcx, [rbx+0B8h]
0x140013f64  mov     rcx, [rcx+28h]; DeviceObject
0x140013f68  call    cs:__imp_IoAllocateWorkItem
0x140013f6f  nop     dword ptr [rax+rax+00h]
0x140013f74  test    rax, rax
0x140013f77  jnz     short loc_140013FC1
0x140013f79  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f80  lea     rax, WPP_GLOBAL_Control
0x140013f87  cmp     rcx, rax
0x140013f8a  jz      short loc_140013FAA
0x140013f8c  cmp     byte ptr [rcx+29h], 5
0x140013f90  jb      short loc_140013FAA
0x140013f92  mov     rcx, [rcx+18h]
0x140013f96  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x140013f9d  mov     edx, 2Dh ; '-'
0x140013fa2  mov     r9, rbx
0x140013fa5  call    WPP_SF_q
0x140013faa  mov     rcx, rbx; Irp
0x140013fad  call    FreeResourcesObjectBag_IfCreateFailure
0x140013fb2  mov     rcx, rbx; Irp
0x140013fb5  call    CompleteCreateIrp
0x140013fba  add     rsp, 20h
0x140013fbe  pop     rbx
0x140013fbf  retn
0x140013fc1  mov     r9, rbx; Context
0x140013fc4  lea     rdx, FilterCreateQueue_CompleteIrpWorker; WorkerRoutine
0x140013fcb  mov     r8d, 1; QueueType
0x140013fd1  mov     rcx, rax; IoWorkItem
0x140013fd4  call    cs:__imp_IoQueueWorkItemEx
0x140013fdb  nop     dword ptr [rax+rax+00h]
0x140013fe0  jmp     short loc_140013FBA
```
