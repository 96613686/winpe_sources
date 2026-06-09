# NtUnmapViewOfSection_0

- ea: `0x180006598`
- end: `0x18000659e`
- name: `NtUnmapViewOfSection_0`
- size: `6`
- prototype: `NTSTATUS __stdcall(HANDLE ProcessHandle, PVOID BaseAddress)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001d80`
- `0x180003170`
- `0x1800044b0`
- `0x180005f10`

## import_xrefs

- `ntdll!NtUnmapViewOfSection` at `0x180006598`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtUnmapViewOfSection_0(HANDLE ProcessHandle, PVOID BaseAddress)
{
  return NtUnmapViewOfSection(ProcessHandle, BaseAddress);
}

```

## disassembly

```asm
0x180006598  jmp     cs:__imp_NtUnmapViewOfSection
```
