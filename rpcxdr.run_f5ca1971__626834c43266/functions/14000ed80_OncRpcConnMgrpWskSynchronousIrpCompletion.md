# OncRpcConnMgrpWskSynchronousIrpCompletion

- ea: `0x14000ed80`
- end: `0x14000edae`
- name: `OncRpcConnMgrpWskSynchronousIrpCompletion`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000ed80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000ed97`
- `ntoskrnl!KeSetEvent` at `0x14000ed97`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpWskSynchronousIrpCompletion(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  if ( *(_BYTE *)(a2 + 65) )
    KeSetEvent(a3, 2, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000ed80  sub     rsp, 28h
0x14000ed84  cmp     byte ptr [rdx+41h], 0
0x14000ed88  mov     rax, r8
0x14000ed8b  jz      short loc_14000EDA3
0x14000ed8d  xor     r8d, r8d; Wait
0x14000ed90  mov     rcx, rax; Event
0x14000ed93  lea     edx, [r8+2]; Increment
0x14000ed97  call    cs:__imp_KeSetEvent
0x14000ed9e  nop     dword ptr [rax+rax+00h]
0x14000eda3  mov     eax, 0C0000016h
0x14000eda8  add     rsp, 28h
0x14000edac  retn
```
