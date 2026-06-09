# VmpAcquireRundown(VM_VOLUME_EXTENSION *)

- ea: `0x140016a20`
- end: `0x140016a4b`
- name: `?VmpAcquireRundown@@YAXPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `43`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140004b40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140016a39`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016a39`

## pseudocode

```c
void __fastcall VmpAcquireRundown(struct VM_VOLUME_EXTENSION *a1)
{
  KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x140016a20  sub     rsp, 38h
0x140016a24  add     rcx, 38h ; '8'; Object
0x140016a28  mov     [rsp+38h+Timeout], 0; Timeout
0x140016a31  xor     r9d, r9d; Alertable
0x140016a34  xor     r8d, r8d; WaitMode
0x140016a37  xor     edx, edx; WaitReason
0x140016a39  call    cs:__imp_KeWaitForSingleObject
0x140016a40  nop     dword ptr [rax+rax+00h]
0x140016a45  add     rsp, 38h
0x140016a49  retn
```
