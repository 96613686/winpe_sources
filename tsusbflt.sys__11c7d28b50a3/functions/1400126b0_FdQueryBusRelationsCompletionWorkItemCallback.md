# FdQueryBusRelationsCompletionWorkItemCallback

- ea: `0x1400126b0`
- end: `0x140012714`
- name: `FdQueryBusRelationsCompletionWorkItemCallback`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003258`
- `0x14000aa30`

## pseudocode

```c
void __fastcall FdQueryBusRelationsCompletionWorkItemCallback(__int64 a1)
{
  __int64 v1; // rbx
  CUsbFilterControl **v2; // rax

  v1 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a1,
         off_14000F0E0);
  v2 = (CUsbFilterControl **)((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                               WPP_MAIN_CB.Queue.ListEntry.Blink,
                               *(_QWORD *)(v1 + 8),
                               off_14000F1A0);
  CUsbBusFilter::EvtQueryBusRelationsCompletionWorkItemCallback(v2, *(struct _IRP **)v1);
}

```

## disassembly

```asm
0x1400126b0  push    rbx
0x1400126b2  sub     rsp, 20h
0x1400126b6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400126bd  mov     rdx, rcx
0x1400126c0  mov     r8, cs:off_14000F0E0
0x1400126c7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400126ce  mov     rax, [rax+650h]
0x1400126d5  call    _guard_dispatch_icall
0x1400126da  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x1400126e1  mov     rbx, rax
0x1400126e4  mov     r8, cs:off_14000F1A0
0x1400126eb  mov     rax, [rcx+650h]
0x1400126f2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400126f9  mov     rdx, [rbx+8]
0x1400126fd  call    _guard_dispatch_icall
0x140012702  mov     rdx, [rbx]; struct _IRP *
0x140012705  mov     rcx, rax; this
0x140012708  call    ?EvtQueryBusRelationsCompletionWorkItemCallback@CUsbBusFilter@@QEAAXPEAU_IRP@@@Z; CUsbBusFilter::EvtQueryBusRelationsCompletionWorkItemCallback(_IRP *)
0x14001270d  add     rsp, 20h
0x140012711  pop     rbx
0x140012712  retn
```
