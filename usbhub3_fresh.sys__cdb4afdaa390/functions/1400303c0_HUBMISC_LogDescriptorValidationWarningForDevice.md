# HUBMISC_LogDescriptorValidationWarningForDevice

- ea: `0x1400303c0`
- end: `0x140030456`
- name: `HUBMISC_LogDescriptorValidationWarningForDevice`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14001c674`
- `0x1400303c0`
- `0x140033530`

## import_xrefs

- `ntoskrnl!RtlSetBit` at `0x14003043e`
- `ntoskrnl!RtlSetBit` at `0x14003043e`

## string_xrefs

- `0x140030429`: `DeviceHwVerifierDescriptorValidationFailure`

## pseudocode

```c
void __fastcall HUBMISC_LogDescriptorValidationWarningForDevice(__int64 a1, ULONG a2, __int64 a3, __int64 a4)
{
  if ( a1 )
  {
    if ( byte_14006ED42 < 0 )
      McTemplateK0ppqq_EtwWriteTransfer(
        a1,
        (unsigned int)USBHUB3_ETW_EVENT_DESCRIPTOR_VALIDATION_WARNING,
        a1 + 1524,
        *(_QWORD *)(*(_QWORD *)a1 + 248LL),
        *(_QWORD *)(a1 + 24),
        *(_WORD *)(*(_QWORD *)(a1 + 8) + 200LL),
        a2);
    if ( (*(_DWORD *)(a1 + 2444) & 2) != 0 )
      HUBMISC_VerifierDbgBreak("DeviceHwVerifierDescriptorValidationFailure", a1 + 512, a3, a4);
    RtlSetBit((PRTL_BITMAP)(a1 + 2600), a2);
  }
}

```

## disassembly

```asm
0x1400303c0  mov     [rsp+arg_0], rbx
0x1400303c5  push    rdi
0x1400303c6  sub     rsp, 40h
0x1400303ca  mov     edi, edx
0x1400303cc  mov     rbx, rcx
0x1400303cf  test    rcx, rcx
0x1400303d2  jz      short loc_14003044A
0x1400303d4  cmp     cs:byte_14006ED42, 0
0x1400303db  jge     short loc_140030418
0x1400303dd  mov     rax, [rcx+8]
0x1400303e1  lea     r8, [rcx+5F4h]
0x1400303e8  mov     r9, [rcx]
0x1400303eb  mov     [rsp+48h+var_18], edx
0x1400303ef  lea     rdx, USBHUB3_ETW_EVENT_DESCRIPTOR_VALIDATION_WARNING
0x1400303f6  movzx   r10d, word ptr [rax+0C8h]
0x1400303fe  mov     rax, [rcx+18h]
0x140030402  mov     r9, [r9+0F8h]
0x140030409  mov     [rsp+48h+var_20], r10d
0x14003040e  mov     [rsp+48h+var_28], rax
0x140030413  call    McTemplateK0ppqq_EtwWriteTransfer
0x140030418  mov     eax, [rbx+98Ch]
0x14003041e  test    al, 2
0x140030420  jz      short loc_140030435
0x140030422  lea     rdx, [rbx+200h]
0x140030429  lea     rcx, aDevicehwverifi_1; "DeviceHwVerifierDescriptorValidationFai"...
0x140030430  call    HUBMISC_VerifierDbgBreak
0x140030435  lea     rcx, [rbx+0A28h]; BitMapHeader
0x14003043c  mov     edx, edi; BitNumber
0x14003043e  call    cs:__imp_RtlSetBit
0x140030445  nop     dword ptr [rax+rax+00h]
0x14003044a  mov     rbx, [rsp+48h+arg_0]
0x14003044f  add     rsp, 40h
0x140030453  pop     rdi
0x140030454  retn
```
