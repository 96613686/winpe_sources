# UsbcDbgBreak

- ea: `0x140013cac`
- end: `0x140013d46`
- name: `UsbcDbgBreak`
- size: `154`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *DriverObject)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002630`

## callees

- `0x14000dfac`
- `0x140013cac`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140013d0a`
- `ntoskrnl!DbgPrint` at `0x140013d0a`
- `ntoskrnl!MmIsDriverVerifying` at `0x140013d19`
- `ntoskrnl!MmIsDriverVerifying` at `0x140013d19`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140013d29`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140013d29`

## string_xrefs

- `0x140013cc9`: `Client driver sent IOCTL_INTERNAL_USB_CYCLE_PORT, not supported by CCGP in boot path`

## pseudocode

```c
char __fastcall UsbcDbgBreak(struct _DRIVER_OBJECT *DriverObject)
{
  LOGICAL IsDriverVerifying; // eax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qs(
      g_RecorderLog,
      2,
      1,
      65,
      (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
      (char)DriverObject,
      (__int64)"Client driver sent IOCTL_INTERNAL_USB_CYCLE_PORT, not supported by CCGP in boot path");
  DbgPrint(
    "0x%p UsbcDbgBreak called due to %s. For more details run: !rcdrlogdump usbccgp\n",
    DriverObject,
    "Client driver sent IOCTL_INTERNAL_USB_CYCLE_PORT, not supported by CCGP in boot path");
  IsDriverVerifying = MmIsDriverVerifying(DriverObject);
  if ( IsDriverVerifying )
  {
    LOBYTE(IsDriverVerifying) = KdRefreshDebuggerNotPresent();
    if ( !(_BYTE)IsDriverVerifying )
      __debugbreak();
  }
  return IsDriverVerifying;
}

```

## disassembly

```asm
0x140013cac  mov     r11, rsp
0x140013caf  mov     [r11+8], rbx
0x140013cb3  push    rdi
0x140013cb4  sub     rsp, 40h
0x140013cb8  mov     rbx, rcx
0x140013cbb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140013cc2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013cc9  lea     rdi, aClientDriverSe; "Client driver sent IOCTL_INTERNAL_USB_C"...
0x140013cd0  jz      short loc_140013CFD
0x140013cd2  mov     [r11-18h], rdi
0x140013cd6  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140013cdd  mov     [r11-20h], rcx
0x140013ce1  mov     r9d, 41h ; 'A'
0x140013ce7  mov     rcx, cs:g_RecorderLog
0x140013cee  mov     dl, 2
0x140013cf0  mov     [r11-28h], rax
0x140013cf4  lea     r8d, [r9-40h]
0x140013cf8  call    WPP_RECORDER_SF_qs
0x140013cfd  mov     r8, rdi
0x140013d00  lea     rcx, a0xPUsbcdbgbrea; "0x%p UsbcDbgBreak called due to %s. For"...
0x140013d07  mov     rdx, rbx
0x140013d0a  call    cs:__imp_DbgPrint
0x140013d11  nop     dword ptr [rax+rax+00h]
0x140013d16  mov     rcx, rbx; DriverObject
0x140013d19  call    cs:__imp_MmIsDriverVerifying
0x140013d20  nop     dword ptr [rax+rax+00h]
0x140013d25  test    eax, eax
0x140013d27  jz      short loc_140013D3A
0x140013d29  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140013d30  nop     dword ptr [rax+rax+00h]
0x140013d35  test    al, al
0x140013d37  jnz     short loc_140013D3A
0x140013d39  int     3; Trap to Debugger
0x140013d3a  mov     rbx, [rsp+48h+arg_0]
0x140013d3f  add     rsp, 40h
0x140013d43  pop     rdi
0x140013d44  retn
```
