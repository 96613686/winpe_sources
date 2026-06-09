# HUBMISC_LogDescriptorValidationErrorForDevice

- ea: `0x1400302d0`
- end: `0x140030366`
- name: `HUBMISC_LogDescriptorValidationErrorForDevice`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14001f3e0`
- `0x140024db0`
- `0x14002cf60`

## callees

- `0x14001c674`
- `0x1400302d0`
- `0x140033530`

## import_xrefs

- `ntoskrnl!RtlSetBit` at `0x14003034e`
- `ntoskrnl!RtlSetBit` at `0x14003034e`

## string_xrefs

- `0x140030339`: `DeviceHwVerifierDescriptorValidationFailure`

## pseudocode

```c
void __fastcall HUBMISC_LogDescriptorValidationErrorForDevice(__int64 a1, ULONG a2, __int64 a3, __int64 a4)
{
  if ( a1 )
  {
    if ( (byte_14006ED41 & 1) != 0 )
      McTemplateK0ppqq_EtwWriteTransfer(
        a1,
        (unsigned int)USBHUB3_ETW_EVENT_DESCRIPTOR_VALIDATION_FAILURE,
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
0x1400302d0  mov     [rsp+arg_0], rbx
0x1400302d5  push    rdi
0x1400302d6  sub     rsp, 40h
0x1400302da  mov     edi, edx
0x1400302dc  mov     rbx, rcx
0x1400302df  test    rcx, rcx
0x1400302e2  jz      short loc_14003035A
0x1400302e4  test    cs:byte_14006ED41, 1
0x1400302eb  jz      short loc_140030328
0x1400302ed  mov     rax, [rcx+8]
0x1400302f1  lea     r8, [rcx+5F4h]
0x1400302f8  mov     r9, [rcx]
0x1400302fb  mov     [rsp+48h+var_18], edx
0x1400302ff  lea     rdx, USBHUB3_ETW_EVENT_DESCRIPTOR_VALIDATION_FAILURE
0x140030306  movzx   r10d, word ptr [rax+0C8h]
0x14003030e  mov     rax, [rcx+18h]
0x140030312  mov     r9, [r9+0F8h]
0x140030319  mov     [rsp+48h+var_20], r10d
0x14003031e  mov     [rsp+48h+var_28], rax
0x140030323  call    McTemplateK0ppqq_EtwWriteTransfer
0x140030328  mov     eax, [rbx+98Ch]
0x14003032e  test    al, 2
0x140030330  jz      short loc_140030345
0x140030332  lea     rdx, [rbx+200h]
0x140030339  lea     rcx, aDevicehwverifi_1; "DeviceHwVerifierDescriptorValidationFai"...
0x140030340  call    HUBMISC_VerifierDbgBreak
0x140030345  lea     rcx, [rbx+0A28h]; BitMapHeader
0x14003034c  mov     edx, edi; BitNumber
0x14003034e  call    cs:__imp_RtlSetBit
0x140030355  nop     dword ptr [rax+rax+00h]
0x14003035a  mov     rbx, [rsp+48h+arg_0]
0x14003035f  add     rsp, 40h
0x140030363  pop     rdi
0x140030364  retn
```
