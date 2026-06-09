# TmpRollbackWorkItem

- ea: `0x140011740`
- end: `0x140011766`
- name: `TmpRollbackWorkItem`
- size: `38`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140010c70`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140011753`
- `ntoskrnl!ObfDereferenceObject` at `0x140011753`

## pseudocode

```c
LONG_PTR __fastcall TmpRollbackWorkItem(struct _KTRANSACTION *Object)
{
  TmRollbackTransactionExt(Object, 0);
  return ObfDereferenceObject(Object);
}

```

## disassembly

```asm
0x140011740  push    rbx
0x140011742  sub     rsp, 20h
0x140011746  xor     edx, edx; Wait
0x140011748  mov     rbx, rcx
0x14001174b  call    TmRollbackTransactionExt
0x140011750  mov     rcx, rbx; Object
0x140011753  call    cs:__imp_ObfDereferenceObject
0x14001175a  nop     dword ptr [rax+rax+00h]
0x14001175f  add     rsp, 20h
0x140011763  pop     rbx
0x140011764  retn
```
