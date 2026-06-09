# NtUnmapViewOfSection_0

- ea: `0x18000666c`
- end: `0x180006672`
- name: `NtUnmapViewOfSection_0`
- size: `6`
- prototype: `NTSTATUS __stdcall(HANDLE ProcessHandle, PVOID BaseAddress)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001e00`
- `0x180003310`
- `0x180004660`
- `0x180005fd0`

## import_xrefs

- `ntdll!NtUnmapViewOfSection` at `0x18000666c`

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
0x18000666c  jmp     cs:__imp_NtUnmapViewOfSection
```
