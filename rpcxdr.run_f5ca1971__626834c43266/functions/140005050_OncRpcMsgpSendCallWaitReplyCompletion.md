# OncRpcMsgpSendCallWaitReplyCompletion

- ea: `0x140005050`
- end: `0x140005075`
- name: `OncRpcMsgpSendCallWaitReplyCompletion`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140005063`
- `ntoskrnl!KeSetEvent` at `0x140005063`

## pseudocode

```c
LONG __fastcall OncRpcMsgpSendCallWaitReplyCompletion(struct _LIST_ENTRY *a1, struct _KEVENT *a2)
{
  a2[1].Header.WaitListHead.Flink = a1;
  return KeSetEvent(a2, 0, 0);
}

```

## disassembly

```asm
0x140005050  sub     rsp, 28h
0x140005054  mov     rax, rdx
0x140005057  mov     [rdx+20h], rcx
0x14000505b  mov     rcx, rax; Event
0x14000505e  xor     r8d, r8d; Wait
0x140005061  xor     edx, edx; Increment
0x140005063  call    cs:__imp_KeSetEvent
0x14000506a  nop     dword ptr [rax+rax+00h]
0x14000506f  add     rsp, 28h
0x140005073  retn
```
