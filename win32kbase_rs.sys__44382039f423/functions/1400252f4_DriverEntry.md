# DriverEntry

- ea: `0x1400252f4`
- end: `0x140025322`
- name: `DriverEntry`
- size: `46`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140025330`

## callees

- `0x140025008`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400252fd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400252fd`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  KeGetCurrentIrql();
  wil_InitializeFeatureStaging();
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)DriverUnload;
  return 0;
}

```

## disassembly

```asm
0x1400252f4  push    rbx
0x1400252f6  sub     rsp, 20h
0x1400252fa  mov     rbx, rcx
0x1400252fd  call    cs:__imp_KeGetCurrentIrql
0x140025304  nop     dword ptr [rax+rax+00h]
0x140025309  call    wil_InitializeFeatureStaging
0x14002530e  lea     rax, ?DriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; DriverUnload(_DRIVER_OBJECT *)
0x140025315  mov     [rbx+68h], rax
0x140025319  xor     eax, eax
0x14002531b  add     rsp, 20h
0x14002531f  pop     rbx
0x140025320  retn
```
