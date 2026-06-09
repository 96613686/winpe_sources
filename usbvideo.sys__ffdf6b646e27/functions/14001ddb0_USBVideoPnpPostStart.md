# USBVideoPnpPostStart

- ea: `0x14001ddb0`
- end: `0x14001dea8`
- name: `USBVideoPnpPostStart`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001d0cc`
- `0x14001ddb0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14001de71`
- `ntoskrnl!IoQueueWorkItem` at `0x14001de71`
- `ntoskrnl!IoFreeWorkItem` at `0x14001de7f`
- `ntoskrnl!IoFreeWorkItem` at `0x14001de7f`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001de04`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001de04`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001de3b`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001de3b`

## pseudocode

```c
__int64 __fastcall USBVideoPnpPostStart(__int64 a1)
{
  __int64 v1; // rbx
  struct _IO_WORKITEM *WorkItem; // rdi
  NTSTATUS v3; // esi

  v1 = *(_QWORD *)(a1 + 16);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, v1, a1);
  WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(*(_QWORD *)(v1 + 24) + 24LL));
  if ( WorkItem )
  {
    v3 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v1 + 768), IdleDetectWorkItem, File, 1u, 0x20u);
    if ( v3 < 0 )
    {
      IoFreeWorkItem(WorkItem);
    }
    else
    {
      *(_QWORD *)(v1 + 240) = WorkItem;
      *(_DWORD *)(v1 + 224) = 1;
      IoQueueWorkItem(WorkItem, (PIO_WORKITEM_ROUTINE)IdleDetectWorkItem, DelayedWorkQueue, (PVOID)v1);
    }
  }
  else
  {
    v3 = 0;
    *(_DWORD *)(v1 + 224) = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001ddb0  mov     [rsp+arg_0], rbx
0x14001ddb5  mov     [rsp+arg_8], rsi
0x14001ddba  push    rdi
0x14001ddbb  sub     rsp, 30h
0x14001ddbf  mov     rbx, [rcx+10h]
0x14001ddc3  mov     rax, rcx
0x14001ddc6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ddcd  lea     rdx, WPP_GLOBAL_Control
0x14001ddd4  cmp     rcx, rdx
0x14001ddd7  jz      short loc_14001DDFC
0x14001ddd9  cmp     byte ptr [rcx+29h], 4
0x14001dddd  jb      short loc_14001DDFC
0x14001dddf  mov     rcx, [rcx+18h]
0x14001dde3  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14001ddea  mov     edx, 29h ; ')'
0x14001ddef  mov     qword ptr [rsp+38h+RemlockSize], rax
0x14001ddf4  mov     r9, rbx
0x14001ddf7  call    WPP_SF_qq
0x14001ddfc  mov     rcx, [rbx+18h]
0x14001de00  mov     rcx, [rcx+18h]; DeviceObject
0x14001de04  call    cs:__imp_IoAllocateWorkItem
0x14001de0b  nop     dword ptr [rax+rax+00h]
0x14001de10  mov     rdi, rax
0x14001de13  test    rax, rax
0x14001de16  jz      short loc_14001DE8D
0x14001de18  lea     rcx, [rbx+300h]; RemoveLock
0x14001de1f  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x14001de27  mov     r9d, 1; Line
0x14001de2d  lea     r8, File; File
0x14001de34  lea     rdx, IdleDetectWorkItem; Tag
0x14001de3b  call    cs:__imp_IoAcquireRemoveLockEx
0x14001de42  nop     dword ptr [rax+rax+00h]
0x14001de47  mov     esi, eax
0x14001de49  mov     rcx, rdi; IoWorkItem
0x14001de4c  test    eax, eax
0x14001de4e  js      short loc_14001DE7F
0x14001de50  mov     r9, rbx; Context
0x14001de53  mov     [rbx+0F0h], rdi
0x14001de5a  mov     r8d, 1; QueueType
0x14001de60  mov     dword ptr [rbx+0E0h], 1
0x14001de6a  lea     rdx, IdleDetectWorkItem; WorkerRoutine
0x14001de71  call    cs:__imp_IoQueueWorkItem
0x14001de78  nop     dword ptr [rax+rax+00h]
0x14001de7d  jmp     short loc_14001DE95
0x14001de7f  call    cs:__imp_IoFreeWorkItem
0x14001de86  nop     dword ptr [rax+rax+00h]
0x14001de8b  jmp     short loc_14001DE95
0x14001de8d  xor     esi, esi
0x14001de8f  mov     [rbx+0E0h], esi
0x14001de95  mov     rbx, [rsp+38h+arg_0]
0x14001de9a  mov     eax, esi
0x14001de9c  mov     rsi, [rsp+38h+arg_8]
0x14001dea1  add     rsp, 30h
0x14001dea5  pop     rdi
0x14001dea6  retn
```
