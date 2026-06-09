# VhdmpiDeleteControlDevice(_DEVICE_OBJECT *)

- ea: `0x1400b7658`
- end: `0x1400b76a8`
- name: `?VhdmpiDeleteControlDevice@@YAXPEAU_DEVICE_OBJECT@@@Z`
- size: `80`
- prototype: `void __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path`

## callers

- `0x140026800`
- `0x1400b71a0`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400b7686`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400b7686`
- `ntoskrnl!IoDeleteDevice` at `0x1400b7695`
- `ntoskrnl!IoDeleteDevice` at `0x1400b7695`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b7675`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b7675`

## pseudocode

```c
void __fastcall VhdmpiDeleteControlDevice(PDEVICE_OBJECT DeviceObject)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\VHDMP");
  IoDeleteSymbolicLink(&DestinationString);
  IoDeleteDevice(DeviceObject);
}

```

## disassembly

```asm
0x1400b7658  push    rbx
0x1400b765a  sub     rsp, 30h
0x1400b765e  mov     rbx, rcx
0x1400b7661  lea     rdx, aDosdevicesVhdm; "\\DosDevices\\VHDMP"
0x1400b7668  xorps   xmm0, xmm0
0x1400b766b  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400b7670  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400b7675  call    cs:__imp_RtlInitUnicodeString
0x1400b767c  nop     dword ptr [rax+rax+00h]
0x1400b7681  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x1400b7686  call    cs:__imp_IoDeleteSymbolicLink
0x1400b768d  nop     dword ptr [rax+rax+00h]
0x1400b7692  mov     rcx, rbx; DeviceObject
0x1400b7695  call    cs:__imp_IoDeleteDevice
0x1400b769c  nop     dword ptr [rax+rax+00h]
0x1400b76a1  add     rsp, 30h
0x1400b76a5  pop     rbx
0x1400b76a6  retn
```
