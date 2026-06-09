# HUBMISC_QueryAndCacheRegistryValuesForDevice

- ea: `0x140084d2c`
- end: `0x140084e1f`
- name: `HUBMISC_QueryAndCacheRegistryValuesForDevice`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140022f10`

## callees

- `0x140001f94`
- `0x14002e4a8`
- `0x140045530`
- `0x140084d2c`
- `0x140088178`
- `0x140088744`

## pseudocode

```c
__int64 __fastcall HUBMISC_QueryAndCacheRegistryValuesForDevice(__int64 a1)
{
  int v1; // ebx
  int UsbflagsValuesForDevice; // edi
  __int64 v4; // rcx
  __int64 v6; // [rsp+20h] [rbp-48h]
  _BYTE v7[8]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v8[8]; // [rsp+48h] [rbp-20h] BYREF
  _BYTE v9[8]; // [rsp+50h] [rbp-18h] BYREF

  v1 = a1 + 1996;
  HUBMISC_ConvertUsbDeviceIdsToString(a1 + 1996, v9, v8, v7);
  UsbflagsValuesForDevice = HUBREG_QueryUsbflagsValuesForDevice(a1, v9, v8, v7);
  HUBREG_QueryUsbHardwareVerifierValue(
    v1,
    (unsigned int)v9,
    (unsigned int)v8,
    (unsigned int)v7,
    (__int64)&g_HwVerifierDeviceName,
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
    a1 + 2444);
  if ( UsbflagsValuesForDevice < 0 )
  {
    *(_DWORD *)(a1 + 2440) = 1073807366;
    if ( Microsoft_Windows_USB_USBHUB3EnableBits < 0 )
    {
      LODWORD(v6) = UsbflagsValuesForDevice;
      McTemplateK0pq_EtwWriteTransfer(
        v4,
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_REGISTRY_FAILURE,
        (const GUID *)(a1 + 1524),
        *(_QWORD *)(a1 + 24),
        v6);
    }
  }
  return ((UsbflagsValuesForDevice >> 31) & 0xFFFFFFF4) + 4077;
}

```

## disassembly

```asm
0x140084d2c  mov     r11, rsp
0x140084d2f  mov     [r11+10h], rbx
0x140084d33  mov     [r11+18h], rsi
0x140084d37  push    rdi
0x140084d38  sub     rsp, 60h
0x140084d3c  mov     rax, cs:__security_cookie
0x140084d43  xor     rax, rsp
0x140084d46  mov     [rsp+68h+var_10], rax
0x140084d4b  lea     rbx, [rcx+7CCh]
0x140084d52  mov     rsi, rcx
0x140084d55  mov     rcx, rbx
0x140084d58  lea     r9, [r11-28h]
0x140084d5c  lea     r8, [r11-20h]
0x140084d60  lea     rdx, [r11-18h]
0x140084d64  call    HUBMISC_ConvertUsbDeviceIdsToString
0x140084d69  lea     r9, [rsp+68h+var_28]
0x140084d6e  mov     rcx, rsi
0x140084d71  lea     r8, [rsp+68h+var_20]
0x140084d76  lea     rdx, [rsp+68h+var_18]
0x140084d7b  call    HUBREG_QueryUsbflagsValuesForDevice
0x140084d80  mov     rdx, [rsi+8]
0x140084d84  lea     r9, [rsp+68h+var_28]
0x140084d89  mov     edi, eax
0x140084d8b  lea     r8, [rsp+68h+var_20]
0x140084d90  lea     rax, [rsi+98Ch]
0x140084d97  mov     rcx, rbx
0x140084d9a  mov     [rsp+68h+var_38], rax
0x140084d9f  mov     rax, [rdx+598h]
0x140084da6  lea     rdx, [rsp+68h+var_18]
0x140084dab  mov     [rsp+68h+var_40], rax
0x140084db0  lea     rax, g_HwVerifierDeviceName
0x140084db7  mov     [rsp+68h+var_48], rax
0x140084dbc  call    HUBREG_QueryUsbHardwareVerifierValue
0x140084dc1  test    edi, edi
0x140084dc3  jns     short loc_140084DF3
0x140084dc5  mov     dword ptr [rsi+988h], 40010006h
0x140084dcf  cmp     cs:Microsoft_Windows_USB_USBHUB3EnableBits, 0
0x140084dd6  jge     short loc_140084DF3
0x140084dd8  mov     r9, [rsi+18h]
0x140084ddc  lea     r8, [rsi+5F4h]
0x140084de3  lea     rdx, USBHUB3_ETW_EVENT_REGISTRY_FAILURE
0x140084dea  mov     dword ptr [rsp+68h+var_48], edi
0x140084dee  call    McTemplateK0pq_EtwWriteTransfer
0x140084df3  sar     edi, 1Fh
0x140084df6  and     edi, 0FFFFFFF4h
0x140084df9  lea     eax, [rdi+0FEDh]
0x140084dff  mov     rcx, [rsp+68h+var_10]
0x140084e04  xor     rcx, rsp; StackCookie
0x140084e07  call    __security_check_cookie
0x140084e0c  lea     r11, [rsp+68h+var_8]
0x140084e11  mov     rbx, [r11+18h]
0x140084e15  mov     rsi, [r11+20h]
0x140084e19  mov     rsp, r11
0x140084e1c  pop     rdi
0x140084e1d  retn
```
