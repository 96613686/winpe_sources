# VmpReleaseRundown(VM_VOLUME_EXTENSION *)

- ea: `0x140016fc0`
- end: `0x140016fdc`
- name: `?VmpReleaseRundown@@YAXPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `28`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140004b40`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140016fca`
- `ntoskrnl!KeReleaseMutex` at `0x140016fca`

## pseudocode

```c
void __fastcall VmpReleaseRundown(struct _KMUTANT *a1)
{
  KeReleaseMutex(a1 + 1, 0);
}

```

## disassembly

```asm
0x140016fc0  sub     rsp, 28h
0x140016fc4  add     rcx, 38h ; '8'; Mutex
0x140016fc8  xor     edx, edx; Wait
0x140016fca  call    cs:__imp_KeReleaseMutex
0x140016fd1  nop     dword ptr [rax+rax+00h]
0x140016fd6  add     rsp, 28h
0x140016fda  retn
```
