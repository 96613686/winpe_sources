# VmVolumeRequestCompletionRoutine(_IRP *)

- ea: `0x140003150`
- end: `0x140003168`
- name: `?VmVolumeRequestCompletionRoutine@@YAXPEAU_IRP@@@Z`
- size: `24`
- prototype: `void __fastcall(struct _IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003156`
- `ntoskrnl!IofCompleteRequest` at `0x140003156`

## pseudocode

```c
void __fastcall VmVolumeRequestCompletionRoutine(struct _IRP *a1)
{
  IofCompleteRequest(a1, 1);
}

```

## disassembly

```asm
0x140003150  sub     rsp, 28h
0x140003154  mov     dl, 1; PriorityBoost
0x140003156  call    cs:__imp_IofCompleteRequest
0x14000315d  nop     dword ptr [rax+rax+00h]
0x140003162  add     rsp, 28h
0x140003166  retn
```
