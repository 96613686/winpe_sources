# OncRpcWiMgrpThreadPoolRundown

- ea: `0x1400202f8`
- end: `0x14002039c`
- name: `OncRpcWiMgrpThreadPoolRundown`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400201dc`

## callees

- `0x14000f130`
- `0x14000f1d0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140020350`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020374`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020350`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020374`
- `ntoskrnl!KeRundownQueue` at `0x140020384`
- `ntoskrnl!KeRundownQueue` at `0x140020384`

## pseudocode

```c
PLIST_ENTRY __fastcall OncRpcWiMgrpThreadPoolRundown(__int64 a1)
{
  struct _LIST_ENTRY *v1; // rbx

  *(_DWORD *)(a1 + 216) |= 1u;
  v1 = (struct _LIST_ENTRY *)(a1 + 136);
  OncRpcWiMgrWorkQueueItemInit(a1 + 136, a1, (unsigned int)OncRpcWiMgrpWorkerThreadTerminate, a1, 4);
  OncRpcWiMgrWorkQueueItemPost(v1);
  KeWaitForSingleObject((PVOID)(a1 + 184), Executive, 0, 0, 0);
  KeWaitForSingleObject(*(PVOID *)(a1 + 208), Executive, 0, 0, 0);
  return KeRundownQueue((PRKQUEUE)(a1 + 32));
}

```

## disassembly

```asm
0x1400202f8  mov     [rsp+arg_0], rbx
0x1400202fd  push    rdi
0x1400202fe  sub     rsp, 30h
0x140020302  or      dword ptr [rcx+0D8h], 1
0x140020309  lea     rbx, [rcx+88h]
0x140020310  mov     rdi, rcx
0x140020313  mov     dword ptr [rsp+38h+Timeout], 4
0x14002031b  mov     r9, rcx
0x14002031e  lea     r8, OncRpcWiMgrpWorkerThreadTerminate
0x140020325  mov     rdx, rcx
0x140020328  mov     rcx, rbx
0x14002032b  call    OncRpcWiMgrWorkQueueItemInit
0x140020330  mov     rcx, rbx; Entry
0x140020333  call    OncRpcWiMgrWorkQueueItemPost
0x140020338  lea     rcx, [rdi+0B8h]; Object
0x14002033f  mov     [rsp+38h+Timeout], 0; Timeout
0x140020348  xor     r9d, r9d; Alertable
0x14002034b  xor     r8d, r8d; WaitMode
0x14002034e  xor     edx, edx; WaitReason
0x140020350  call    cs:__imp_KeWaitForSingleObject
0x140020357  nop     dword ptr [rax+rax+00h]
0x14002035c  mov     rcx, [rdi+0D0h]; Object
0x140020363  xor     r9d, r9d; Alertable
0x140020366  xor     r8d, r8d; WaitMode
0x140020369  mov     [rsp+38h+Timeout], 0; Timeout
0x140020372  xor     edx, edx; WaitReason
0x140020374  call    cs:__imp_KeWaitForSingleObject
0x14002037b  nop     dword ptr [rax+rax+00h]
0x140020380  lea     rcx, [rdi+20h]; Queue
0x140020384  call    cs:__imp_KeRundownQueue
0x14002038b  nop     dword ptr [rax+rax+00h]
0x140020390  mov     rbx, [rsp+38h+arg_0]
0x140020395  add     rsp, 30h
0x140020399  pop     rdi
0x14002039a  retn
```
