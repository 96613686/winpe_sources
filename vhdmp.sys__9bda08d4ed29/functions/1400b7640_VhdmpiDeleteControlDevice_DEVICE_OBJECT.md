# VhdmpiDeleteControlDevice(_DEVICE_OBJECT *)

- ea: `0x1400b7640`
- end: `0x1400b7690`
- name: `?VhdmpiDeleteControlDevice@@YAXPEAU_DEVICE_OBJECT@@@Z`
- size: `80`
- prototype: `void __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path`

## callers

- `0x140026c20`
- `0x1400b7188`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400b766e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400b766e`
- `ntoskrnl!IoDeleteDevice` at `0x1400b767d`
- `ntoskrnl!IoDeleteDevice` at `0x1400b767d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b765d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b765d`

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
0x1400b7640  push    rbx
0x1400b7642  sub     rsp, 30h
0x1400b7646  mov     rbx, rcx
0x1400b7649  lea     rdx, aDosdevicesVhdm; "\\DosDevices\\VHDMP"
0x1400b7650  xorps   xmm0, xmm0
0x1400b7653  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400b7658  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400b765d  call    cs:__imp_RtlInitUnicodeString
0x1400b7664  nop     dword ptr [rax+rax+00h]
0x1400b7669  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x1400b766e  call    cs:__imp_IoDeleteSymbolicLink
0x1400b7675  nop     dword ptr [rax+rax+00h]
0x1400b767a  mov     rcx, rbx; DeviceObject
0x1400b767d  call    cs:__imp_IoDeleteDevice
0x1400b7684  nop     dword ptr [rax+rax+00h]
0x1400b7689  add     rsp, 30h
0x1400b768d  pop     rbx
0x1400b768e  retn
```
