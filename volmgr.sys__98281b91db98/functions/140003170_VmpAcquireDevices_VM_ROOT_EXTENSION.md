# VmpAcquireDevices(VM_ROOT_EXTENSION *)

- ea: `0x140003170`
- end: `0x14000319b`
- name: `?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z`
- size: `43`
- prototype: `void __fastcall(struct VM_ROOT_EXTENSION *)`
- caller_count: `15`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14000e010`
- `0x14000f930`
- `0x1400127f0`
- `0x1400129d0`
- `0x140012b3c`
- `0x140012fa0`
- `0x1400132f8`
- `0x140013594`
- `0x1400136b8`
- `0x1400139b4`
- `0x14001462c`
- `0x140014838`
- `0x140016130`
- `0x140016540`
- `0x140016aa0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140003189`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003189`

## pseudocode

```c
void __fastcall VmpAcquireDevices(struct VM_ROOT_EXTENSION *a1)
{
  KeWaitForSingleObject((char *)a1 + 112, Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x140003170  sub     rsp, 38h
0x140003174  add     rcx, 70h ; 'p'; Object
0x140003178  mov     [rsp+38h+Timeout], 0; Timeout
0x140003181  xor     r9d, r9d; Alertable
0x140003184  xor     r8d, r8d; WaitMode
0x140003187  xor     edx, edx; WaitReason
0x140003189  call    cs:__imp_KeWaitForSingleObject
0x140003190  nop     dword ptr [rax+rax+00h]
0x140003195  add     rsp, 38h
0x140003199  retn
```
