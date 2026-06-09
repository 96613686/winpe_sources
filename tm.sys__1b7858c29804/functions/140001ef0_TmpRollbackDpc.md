# TmpRollbackDpc

- ea: `0x140001ef0`
- end: `0x140001f28`
- name: `TmpRollbackDpc`
- size: `56`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x140001f16`
- `ntoskrnl!ExQueueWorkItem` at `0x140001f16`

## pseudocode

```c
void __fastcall TmpRollbackDpc(struct _KDPC *Dpc, char *DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)
{
  *((_QWORD *)DeferredContext + 44) = DeferredContext;
  *((_QWORD *)DeferredContext + 43) = TmpRollbackWorkItem;
  *((_QWORD *)DeferredContext + 41) = 0;
  ExQueueWorkItem((PWORK_QUEUE_ITEM)(DeferredContext + 328), DelayedWorkQueue);
}

```

## disassembly

```asm
0x140001ef0  sub     rsp, 28h
0x140001ef4  lea     rcx, [rdx+148h]; WorkItem
0x140001efb  mov     [rcx+18h], rdx
0x140001eff  lea     rax, TmpRollbackWorkItem
0x140001f06  mov     edx, 1; QueueType
0x140001f0b  mov     [rcx+10h], rax
0x140001f0f  mov     qword ptr [rcx], 0
0x140001f16  call    cs:__imp_ExQueueWorkItem
0x140001f1d  nop     dword ptr [rax+rax+00h]
0x140001f22  add     rsp, 28h
0x140001f26  retn
```
