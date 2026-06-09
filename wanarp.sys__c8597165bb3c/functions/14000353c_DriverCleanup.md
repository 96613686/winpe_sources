# DriverCleanup

- ea: `0x14000353c`
- end: `0x1400035b3`
- name: `DriverCleanup`
- size: `119`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140017550`

## callees

- `0x14000353c`
- `0x140003960`
- `0x140017a4c`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000354c`
- `ntoskrnl!IoDeleteDevice` at `0x14000356f`
- `ntoskrnl!IoDeleteDevice` at `0x14000354c`
- `ntoskrnl!IoDeleteDevice` at `0x14000356f`

## pseudocode

```c
__int64 DriverCleanup()
{
  if ( DeviceObject )
  {
    IoDeleteDevice(DeviceObject);
    DeviceObject = 0;
  }
  if ( qword_140009B98 )
  {
    IoDeleteDevice(qword_140009B98);
    qword_140009B98 = 0;
  }
  WanpSetupExternalName(0, L"\\DosDevices\\WanArp", 0);
  WanpSetupExternalName(0, L"\\DosDevices\\WanArpV6", 0);
  return WanpFreeDriverStructures();
}

```

## disassembly

```asm
0x14000353c  sub     rsp, 28h
0x140003540  mov     rcx, cs:DeviceObject; DeviceObject
0x140003547  test    rcx, rcx
0x14000354a  jz      short loc_140003563
0x14000354c  call    cs:__imp_IoDeleteDevice
0x140003553  nop     dword ptr [rax+rax+00h]
0x140003558  mov     cs:DeviceObject, 0
0x140003563  mov     rcx, cs:qword_140009B98; DeviceObject
0x14000356a  test    rcx, rcx
0x14000356d  jz      short loc_140003586
0x14000356f  call    cs:__imp_IoDeleteDevice
0x140003576  nop     dword ptr [rax+rax+00h]
0x14000357b  mov     cs:qword_140009B98, 0
0x140003586  xor     r8d, r8d
0x140003589  lea     rdx, aDosdevicesWana_0; "\\DosDevices\\WanArp"
0x140003590  xor     ecx, ecx; DeviceName
0x140003592  call    WanpSetupExternalName
0x140003597  xor     r8d, r8d
0x14000359a  lea     rdx, aDosdevicesWana; "\\DosDevices\\WanArpV6"
0x1400035a1  xor     ecx, ecx; DeviceName
0x1400035a3  call    WanpSetupExternalName
0x1400035a8  call    WanpFreeDriverStructures
0x1400035ad  add     rsp, 28h
0x1400035b1  retn
```
