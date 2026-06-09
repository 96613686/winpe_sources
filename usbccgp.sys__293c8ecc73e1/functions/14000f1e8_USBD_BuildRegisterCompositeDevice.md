# USBD_BuildRegisterCompositeDevice

- ea: `0x14000f1e8`
- end: `0x14000f210`
- name: `USBD_BuildRegisterCompositeDevice`
- size: `40`
- prototype: `void __stdcall(USBD_HANDLE USBDHandle, COMPOSITE_DEVICE_CAPABILITIES CapabilityFlags, ULONG FunctionCount, PREGISTER_COMPOSITE_DEVICE RegisterCompositeDevice)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140023414`

## pseudocode

```c
void __stdcall USBD_BuildRegisterCompositeDevice(
        USBD_HANDLE USBDHandle,
        COMPOSITE_DEVICE_CAPABILITIES CapabilityFlags,
        ULONG FunctionCount,
        PREGISTER_COMPOSITE_DEVICE RegisterCompositeDevice)
{
  *(_QWORD *)(&RegisterCompositeDevice->Size + 1) = 0;
  HIDWORD(RegisterCompositeDevice->Reserved) = 0;
  *(_DWORD *)&RegisterCompositeDevice->Version = 1573120;
  RegisterCompositeDevice->CapabilityFlags = CapabilityFlags;
  RegisterCompositeDevice->FunctionCount = FunctionCount;
  RegisterCompositeDevice->Reserved = (USBDI_HANDLE)*((_QWORD *)USBDHandle + 6);
}

```

## disassembly

```asm
0x14000f1e8  mov     qword ptr [r9+4], 0
0x14000f1f0  mov     dword ptr [r9+0Ch], 0
0x14000f1f8  mov     dword ptr [r9], 180100h
0x14000f1ff  mov     [r9+10h], edx
0x14000f203  mov     [r9+14h], r8d
0x14000f207  mov     rax, [rcx+30h]
0x14000f20b  mov     [r9+8], rax
0x14000f20f  retn
```
