# ReadIconGuts(_FILEINFO *,ulong *,tagNEWHEADER *,int,ushort * *,int,int,ulong)

- ea: `0x1800028a0`
- end: `0x180002bf7`
- name: `?ReadIconGuts@@YAPEAUtagCURSORRESOURCE@@PEAU_FILEINFO@@PEAKPEAUtagNEWHEADER@@HPEAPEAGHHK@Z`
- size: `855`
- prototype: `struct tagCURSORRESOURCE *__usercall@<rax>(struct _FILEINFO *@<rcx>, unsigned int *@<rdx>, struct tagNEWHEADER *@<r8>, int@<r9d>, unsigned __int16 **, int, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800013dc`
- `0x180002264`

## callees

- `0x180002824`
- `0x1800028a0`
- `0x180008634`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002b90`
- `ntdll!RtlFreeHeap` at `0x180002bcf`
- `ntdll!RtlFreeHeap` at `0x180002be1`
- `ntdll!RtlFreeHeap` at `0x180002b90`
- `ntdll!RtlFreeHeap` at `0x180002bcf`
- `ntdll!RtlFreeHeap` at `0x180002be1`
- `ntdll!RtlAllocateHeap` at `0x180002917`
- `ntdll!RtlAllocateHeap` at `0x180002adf`
- `ntdll!RtlAllocateHeap` at `0x180002917`
- `ntdll!RtlAllocateHeap` at `0x180002adf`

## pseudocode

```c

```
