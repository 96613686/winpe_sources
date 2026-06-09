# VmpReleaseConfig(VM_ROOT_EXTENSION *)

- ea: `0x1400039c0`
- end: `0x1400039dc`
- name: `?VmpReleaseConfig@@YAXPEAVVM_ROOT_EXTENSION@@@Z`
- size: `28`
- prototype: `void __fastcall(struct VM_ROOT_EXTENSION *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, loader_planting`

## callers

- `0x140012b3c`
- `0x14001462c`
- `0x140014838`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400039ca`
- `ntoskrnl!KeReleaseMutex` at `0x1400039ca`

## pseudocode

```c
void __fastcall VmpReleaseConfig(struct _KMUTANT *a1)
{
  KeReleaseMutex(a1 + 1, 0);
}

```

## disassembly

```asm
0x1400039c0  sub     rsp, 28h
0x1400039c4  add     rcx, 38h ; '8'; Mutex
0x1400039c8  xor     edx, edx; Wait
0x1400039ca  call    cs:__imp_KeReleaseMutex
0x1400039d1  nop     dword ptr [rax+rax+00h]
0x1400039d6  add     rsp, 28h
0x1400039da  retn
```
