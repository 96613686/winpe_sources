# USBD_QueryUsbCapability

- ea: `0x14003be34`
- end: `0x14003bffa`
- name: `USBD_QueryUsbCapability`
- size: `454`
- prototype: `NTSTATUS __stdcall(USBD_HANDLE USBDHandle, const GUID *CapabilityType, ULONG OutputBufferLength, PUCHAR OutputBuffer, PULONG ResultLength)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400156a0`

## callees

- `0x140013dc8`
- `0x14003be34`
- `0x140040a30`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003bf24`
- `ntoskrnl!RtlCompareMemory` at `0x14003bf78`
- `ntoskrnl!RtlCompareMemory` at `0x14003bf24`
- `ntoskrnl!RtlCompareMemory` at `0x14003bf78`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003be6b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003be6b`
- `ntoskrnl!DbgPrintEx` at `0x14003be90`
- `ntoskrnl!DbgPrintEx` at `0x14003bef3`
- `ntoskrnl!DbgPrintEx` at `0x14003bf55`
- `ntoskrnl!DbgPrintEx` at `0x14003be90`
- `ntoskrnl!DbgPrintEx` at `0x14003bef3`
- `ntoskrnl!DbgPrintEx` at `0x14003bf55`

## pseudocode

```c
NTSTATUS __stdcall USBD_QueryUsbCapability(
        USBD_HANDLE USBDHandle,
        const GUID *CapabilityType,
        ULONG OutputBufferLength,
        PUCHAR OutputBuffer,
        PULONG ResultLength)
{
  int v8; // eax

  if ( KeGetCurrentIrql() )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "PASSIVE_LEVEL required\n");
    return -1073741811;
  }
  if ( !USBDHandle )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "USBDHandle cant be NULL\n");
    return -1073741811;
  }
  if ( !CapabilityType )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "CapabilityType cant be NULL\n");
    return -1073741811;
  }
  v8 = *((_DWORD *)USBDHandle + 54);
  if ( v8 == -1 )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(
        0x4Du,
        0,
        "Could not exchange an interface with the Underlying USB core stack, querrying for capability is not possible\n");
    return -1073741822;
  }
  if ( v8 != 1536 )
    return USBDInternal_BuildandSendIoctlSynchronously(
             *((PDEVICE_OBJECT *)USBDHandle + 7),
             *((PDEVICE_OBJECT *)USBDHandle + 26));
  if ( RtlCompareMemory(CapabilityType, &GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE, 0x10u) != 16 )
  {
    if ( RtlCompareMemory(CapabilityType, &GUID_USB_CAPABILITY_SELECTIVE_SUSPEND, 0x10u) != 16 )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "QueryUsbCapability not supported/implemented by core stack\n");
      return -1073741822;
    }
    return 0;
  }
  if ( *((_BYTE *)USBDHandle + 224) )
    return 0;
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 3u, "Device is not High Speed\n");
  return -1073741637;
}

```

## disassembly

```asm
0x14003be34  mov     [rsp-8+arg_10], rbx
0x14003be39  mov     [rsp-8+arg_18], rdi
0x14003be3e  push    rbp
0x14003be3f  mov     rbp, rsp
0x14003be42  sub     rsp, 60h
0x14003be46  mov     rax, cs:__security_cookie
0x14003be4d  xor     rax, rsp
0x14003be50  mov     [rbp+var_8], rax
0x14003be54  xorps   xmm0, xmm0
0x14003be57  xor     eax, eax
0x14003be59  movups  [rbp+var_30], xmm0
0x14003be5d  mov     [rbp+var_10], rax
0x14003be61  mov     rdi, rdx
0x14003be64  movups  [rbp+var_20], xmm0
0x14003be68  mov     rbx, rcx
0x14003be6b  call    cs:__imp_KeGetCurrentIrql
0x14003be72  nop     dword ptr [rax+rax+00h]
0x14003be77  test    al, al
0x14003be79  jz      short loc_14003BEA6
0x14003be7b  cmp     cs:g_EnableDbgPrints, 0
0x14003be82  jz      short loc_14003BE9C
0x14003be84  lea     r8, aPassiveLevelRe; "PASSIVE_LEVEL required\n"
0x14003be8b  xor     edx, edx; Level
0x14003be8d  lea     ecx, [rdx+4Dh]; ComponentId
0x14003be90  call    cs:__imp_DbgPrintEx
0x14003be97  nop     dword ptr [rax+rax+00h]
0x14003be9c  mov     eax, 0C000000Dh
0x14003bea1  jmp     loc_14003BFDB
0x14003bea6  test    rbx, rbx
0x14003bea9  jnz     short loc_14003BEBC
0x14003beab  cmp     cs:g_EnableDbgPrints, bl
0x14003beb1  jz      short loc_14003BE9C
0x14003beb3  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14003beba  jmp     short loc_14003BE8B
0x14003bebc  test    rdi, rdi
0x14003bebf  jnz     short loc_14003BED3
0x14003bec1  cmp     cs:g_EnableDbgPrints, dil
0x14003bec8  jz      short loc_14003BE9C
0x14003beca  lea     r8, aCapabilitytype; "CapabilityType cant be NULL\n"
0x14003bed1  jmp     short loc_14003BE8B
0x14003bed3  mov     eax, [rbx+0D8h]
0x14003bed9  cmp     eax, 0FFFFFFFFh
0x14003bedc  jnz     short loc_14003BF09
0x14003bede  cmp     cs:g_EnableDbgPrints, 0
0x14003bee5  jz      short loc_14003BEFF
0x14003bee7  lea     r8, aCouldNotExchan; "Could not exchange an interface with th"...
0x14003beee  xor     edx, edx; Level
0x14003bef0  lea     ecx, [rdx+4Dh]; ComponentId
0x14003bef3  call    cs:__imp_DbgPrintEx
0x14003befa  nop     dword ptr [rax+rax+00h]
0x14003beff  mov     eax, 0C0000002h
0x14003bf04  jmp     loc_14003BFDB
0x14003bf09  cmp     eax, 600h
0x14003bf0e  jnz     loc_14003BFA7
0x14003bf14  mov     r8d, 10h; Length
0x14003bf1a  lea     rdx, GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE; Source2
0x14003bf21  mov     rcx, rdi; Source1
0x14003bf24  call    cs:__imp_RtlCompareMemory
0x14003bf2b  nop     dword ptr [rax+rax+00h]
0x14003bf30  cmp     rax, 10h
0x14003bf34  jnz     short loc_14003BF68
0x14003bf36  cmp     byte ptr [rbx+0E0h], 0
0x14003bf3d  jnz     short loc_14003BF8A
0x14003bf3f  cmp     cs:g_EnableDbgPrints, 0
0x14003bf46  jz      short loc_14003BF61
0x14003bf48  lea     r8, aDeviceIsNotHig; "Device is not High Speed\n"
0x14003bf4f  lea     edx, [rax-0Dh]; Level
0x14003bf52  lea     ecx, [rax+3Dh]; ComponentId
0x14003bf55  call    cs:__imp_DbgPrintEx
0x14003bf5c  nop     dword ptr [rax+rax+00h]
0x14003bf61  mov     eax, 0C00000BBh
0x14003bf66  jmp     short loc_14003BFDB
0x14003bf68  mov     r8d, 10h; Length
0x14003bf6e  lea     rdx, GUID_USB_CAPABILITY_SELECTIVE_SUSPEND; Source2
0x14003bf75  mov     rcx, rdi; Source1
0x14003bf78  call    cs:__imp_RtlCompareMemory
0x14003bf7f  nop     dword ptr [rax+rax+00h]
0x14003bf84  cmp     rax, 10h
0x14003bf88  jnz     short loc_14003BF8E
0x14003bf8a  xor     eax, eax
0x14003bf8c  jmp     short loc_14003BFDB
0x14003bf8e  cmp     cs:g_EnableDbgPrints, 0
0x14003bf95  jz      loc_14003BEFF
0x14003bf9b  lea     r8, aQueryusbcapabi; "QueryUsbCapability not supported/implem"...
0x14003bfa2  jmp     loc_14003BEEE
0x14003bfa7  movups  xmm0, xmmword ptr [rdi]
0x14003bfaa  mov     rax, [rbx+30h]
0x14003bfae  lea     r9, [rbp+var_30]
0x14003bfb2  mov     rdx, [rbx+0D0h]; PDEVICE_OBJECT
0x14003bfb9  mov     rcx, [rbx+38h]; DeviceObject
0x14003bfbd  movdqu  [rbp+var_20], xmm0
0x14003bfc2  mov     qword ptr [rbp+var_30], 280001h
0x14003bfca  mov     [rbp+var_10], 0
0x14003bfd2  mov     qword ptr [rbp+var_30+8], rax
0x14003bfd6  call    USBDInternal_BuildandSendIoctlSynchronously
0x14003bfdb  mov     rcx, [rbp+var_8]
0x14003bfdf  xor     rcx, rsp; StackCookie
0x14003bfe2  call    __security_check_cookie
0x14003bfe7  lea     r11, [rsp+60h+var_s0]
0x14003bfec  mov     rbx, [r11+20h]
0x14003bff0  mov     rdi, [r11+28h]
0x14003bff4  mov     rsp, r11
0x14003bff7  pop     rbp
0x14003bff8  retn
```
