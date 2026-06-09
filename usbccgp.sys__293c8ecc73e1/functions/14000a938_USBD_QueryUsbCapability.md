# USBD_QueryUsbCapability

- ea: `0x14000a938`
- end: `0x14000abf2`
- name: `USBD_QueryUsbCapability`
- size: `698`
- prototype: `NTSTATUS __stdcall(USBD_HANDLE USBDHandle, const GUID *CapabilityType, ULONG OutputBufferLength, PUCHAR OutputBuffer, PULONG ResultLength)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a7bc`

## callees

- `0x14000a938`
- `0x14000abf8`
- `0x140014d10`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000a98c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a98c`
- `ntoskrnl!RtlCompareMemory` at `0x14000ab19`
- `ntoskrnl!RtlCompareMemory` at `0x14000abab`
- `ntoskrnl!RtlCompareMemory` at `0x14000ab19`
- `ntoskrnl!RtlCompareMemory` at `0x14000abab`
- `ntoskrnl!DbgPrintEx` at `0x14000aa75`
- `ntoskrnl!DbgPrintEx` at `0x14000aaf1`
- `ntoskrnl!DbgPrintEx` at `0x14000ab56`
- `ntoskrnl!DbgPrintEx` at `0x14000ab88`
- `ntoskrnl!DbgPrintEx` at `0x14000aa75`
- `ntoskrnl!DbgPrintEx` at `0x14000aaf1`
- `ntoskrnl!DbgPrintEx` at `0x14000ab56`
- `ntoskrnl!DbgPrintEx` at `0x14000ab88`

## string_xrefs

- `0x14000ab41`: `OutputBuffer must be NULL for GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE\n`

## pseudocode

```c
NTSTATUS __stdcall USBD_QueryUsbCapability(
        USBD_HANDLE USBDHandle,
        const GUID *CapabilityType,
        ULONG OutputBufferLength,
        PUCHAR OutputBuffer,
        PULONG ResultLength)
{
  int v9; // eax
  NTSTATUS v10; // ebx

  if ( ResultLength )
    *ResultLength = 0;
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
  if ( !OutputBufferLength )
  {
    if ( !OutputBuffer )
      goto LABEL_8;
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "OutputBuffer must be NULL if OutputBufferLength is zero\n");
    return -1073741811;
  }
  if ( !OutputBuffer )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "OutputBuffer cant be NULL if OutputBufferLength is not zero\n");
    return -1073741811;
  }
LABEL_8:
  v9 = *((_DWORD *)USBDHandle + 54);
  if ( v9 == -1 )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(
        0x4Du,
        0,
        "Could not exchange an interface with the Underlying USB core stack, querrying for capability is not possible\n");
    return -1073741822;
  }
  if ( v9 != 1536 )
  {
    v10 = USBDInternal_BuildandSendIoctlSynchronously(
            *((PDEVICE_OBJECT *)USBDHandle + 7),
            *((PDEVICE_OBJECT *)USBDHandle + 26));
    if ( v10 >= 0 && ResultLength )
      *ResultLength = 0;
    return v10;
  }
  if ( RtlCompareMemory(CapabilityType, &GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE, 0x10u) == 16 )
  {
    if ( OutputBuffer )
    {
      v10 = -1073741811;
      if ( g_EnableDbgPrints )
        DbgPrintEx(
          0x4Du,
          0,
          "OutputBuffer must be NULL for GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE\n");
      return v10;
    }
    if ( !*((_BYTE *)USBDHandle + 224) )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 3u, "Device is not High Speed\n");
      return -1073741637;
    }
    return 0;
  }
  if ( RtlCompareMemory(CapabilityType, &GUID_USB_CAPABILITY_SELECTIVE_SUSPEND, 0x10u) != 16 )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "QueryUsbCapability not supported/implemented by core stack\n");
    return -1073741822;
  }
  if ( !OutputBuffer )
    return 0;
  v10 = -1073741811;
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 0, "OutputBuffer must be NULL for GUID_USB_CAPABILITY_SELECTIVE_SUSPEND\n");
  return v10;
}

```

## disassembly

```asm
0x14000a938  mov     [rsp-28h+arg_10], rbx
0x14000a93d  mov     [rsp-28h+arg_18], rsi
0x14000a942  push    rbp
0x14000a943  push    rdi
0x14000a944  push    r12
0x14000a946  push    r14
0x14000a948  push    r15
0x14000a94a  mov     rbp, rsp
0x14000a94d  sub     rsp, 60h
0x14000a951  mov     rax, cs:__security_cookie
0x14000a958  xor     rax, rsp
0x14000a95b  mov     [rbp+var_8], rax
0x14000a95f  mov     rsi, [rbp+ResultLength]
0x14000a963  xor     eax, eax
0x14000a965  xorps   xmm0, xmm0
0x14000a968  mov     [rbp+var_10], rax
0x14000a96c  xor     r12d, r12d
0x14000a96f  mov     rbx, r9
0x14000a972  mov     r15d, r8d
0x14000a975  mov     r14, rdx
0x14000a978  mov     rdi, rcx
0x14000a97b  movups  [rbp+var_30], xmm0
0x14000a97f  movups  [rbp+var_20], xmm0
0x14000a983  test    rsi, rsi
0x14000a986  jnz     loc_14000AA83
0x14000a98c  call    cs:__imp_KeGetCurrentIrql
0x14000a993  nop     dword ptr [rax+rax+00h]
0x14000a998  test    al, al
0x14000a99a  jnz     loc_14000AA44
0x14000a9a0  test    rdi, rdi
0x14000a9a3  jz      loc_14000AA94
0x14000a9a9  test    r14, r14
0x14000a9ac  jz      loc_14000AAA6
0x14000a9b2  test    r15d, r15d
0x14000a9b5  jnz     loc_14000AAB8
0x14000a9bb  test    rbx, rbx
0x14000a9be  jnz     loc_14000AA60
0x14000a9c4  mov     eax, [rdi+0D8h]
0x14000a9ca  cmp     eax, 0FFFFFFFFh
0x14000a9cd  jz      loc_14000AAD3
0x14000a9d3  cmp     eax, 600h
0x14000a9d8  jz      loc_14000AB07
0x14000a9de  movups  xmm0, xmmword ptr [r14]
0x14000a9e2  mov     rax, [rdi+30h]
0x14000a9e6  lea     r9, [rbp+var_30]
0x14000a9ea  mov     rdx, [rdi+0D0h]; PDEVICE_OBJECT
0x14000a9f1  mov     r8, rbx
0x14000a9f4  mov     rcx, [rdi+38h]; DeviceObject
0x14000a9f8  movdqu  [rbp+var_20], xmm0
0x14000a9fd  mov     qword ptr [rbp+var_30], 280001h
0x14000aa05  mov     dword ptr [rbp+var_10+4], r12d
0x14000aa09  mov     qword ptr [rbp+var_30+8], rax
0x14000aa0d  mov     dword ptr [rbp+var_10], r15d
0x14000aa11  call    USBDInternal_BuildandSendIoctlSynchronously
0x14000aa16  mov     ebx, eax
0x14000aa18  test    eax, eax
0x14000aa1a  jns     short loc_14000AA54
0x14000aa1c  mov     eax, ebx
0x14000aa1e  mov     rcx, [rbp+var_8]
0x14000aa22  xor     rcx, rsp; StackCookie
0x14000aa25  call    __security_check_cookie
0x14000aa2a  lea     r11, [rsp+60h+var_s0]
0x14000aa2f  mov     rbx, [r11+40h]
0x14000aa33  mov     rsi, [r11+48h]
0x14000aa37  mov     rsp, r11
0x14000aa3a  pop     r15
0x14000aa3c  pop     r14
0x14000aa3e  pop     r12
0x14000aa40  pop     rdi
0x14000aa41  pop     rbp
0x14000aa42  retn
0x14000aa44  cmp     cs:g_EnableDbgPrints, r12b
0x14000aa4b  jnz     short loc_14000AA8B
0x14000aa4d  mov     ebx, 0C000000Dh
0x14000aa52  jmp     short loc_14000AA1C
0x14000aa54  test    rsi, rsi
0x14000aa57  jz      short loc_14000AA1C
0x14000aa59  mov     ecx, dword ptr [rbp+var_10+4]
0x14000aa5c  mov     [rsi], ecx
0x14000aa5e  jmp     short loc_14000AA1C
0x14000aa60  cmp     cs:g_EnableDbgPrints, r12b
0x14000aa67  jz      short loc_14000AA4D
0x14000aa69  lea     r8, aOutputbufferMu_1; "OutputBuffer must be NULL if OutputBuff"...
0x14000aa70  xor     edx, edx; Level
0x14000aa72  lea     ecx, [rdx+4Dh]; ComponentId
0x14000aa75  call    cs:__imp_DbgPrintEx
0x14000aa7c  nop     dword ptr [rax+rax+00h]
0x14000aa81  jmp     short loc_14000AA4D
0x14000aa83  mov     [rsi], r12d
0x14000aa86  jmp     loc_14000A98C
0x14000aa8b  lea     r8, aPassiveLevelRe; "PASSIVE_LEVEL required\n"
0x14000aa92  jmp     short loc_14000AA70
0x14000aa94  cmp     cs:g_EnableDbgPrints, r12b
0x14000aa9b  jz      short loc_14000AA4D
0x14000aa9d  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14000aaa4  jmp     short loc_14000AA70
0x14000aaa6  cmp     cs:g_EnableDbgPrints, r12b
0x14000aaad  jz      short loc_14000AA4D
0x14000aaaf  lea     r8, aCapabilitytype; "CapabilityType cant be NULL\n"
0x14000aab6  jmp     short loc_14000AA70
0x14000aab8  test    rbx, rbx
0x14000aabb  jnz     loc_14000A9C4
0x14000aac1  cmp     cs:g_EnableDbgPrints, r12b
0x14000aac8  jz      short loc_14000AA4D
0x14000aaca  lea     r8, aOutputbufferCa; "OutputBuffer cant be NULL if OutputBuff"...
0x14000aad1  jmp     short loc_14000AA70
0x14000aad3  cmp     cs:g_EnableDbgPrints, r12b
0x14000aada  jz      short loc_14000AAFD
0x14000aadc  lea     r8, aCouldNotExchan; "Could not exchange an interface with th"...
0x14000aae3  jmp     short loc_14000AAEC
0x14000aae5  lea     r8, aQueryusbcapabi; "QueryUsbCapability not supported/implem"...
0x14000aaec  xor     edx, edx; Level
0x14000aaee  lea     ecx, [rdx+4Dh]; ComponentId
0x14000aaf1  call    cs:__imp_DbgPrintEx
0x14000aaf8  nop     dword ptr [rax+rax+00h]
0x14000aafd  mov     ebx, 0C0000002h
0x14000ab02  jmp     loc_14000AA1C
0x14000ab07  mov     esi, 10h
0x14000ab0c  lea     rdx, GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE; Source2
0x14000ab13  mov     r8d, esi; Length
0x14000ab16  mov     rcx, r14; Source1
0x14000ab19  call    cs:__imp_RtlCompareMemory
0x14000ab20  nop     dword ptr [rax+rax+00h]
0x14000ab25  cmp     rax, rsi
0x14000ab28  jnz     short loc_14000AB9E
0x14000ab2a  test    rbx, rbx
0x14000ab2d  jz      short loc_14000AB67
0x14000ab2f  cmp     cs:g_EnableDbgPrints, r12b
0x14000ab36  mov     ebx, 0C000000Dh
0x14000ab3b  jz      loc_14000AA1C
0x14000ab41  lea     r8, aOutputbufferMu_0; "OutputBuffer must be NULL for GUID_USB_"...
0x14000ab48  jmp     short loc_14000AB51
0x14000ab4a  lea     r8, aOutputbufferMu; "OutputBuffer must be NULL for GUID_USB_"...
0x14000ab51  xor     edx, edx; Level
0x14000ab53  lea     ecx, [rdx+4Dh]; ComponentId
0x14000ab56  call    cs:__imp_DbgPrintEx
0x14000ab5d  nop     dword ptr [rax+rax+00h]
0x14000ab62  jmp     loc_14000AA1C
0x14000ab67  cmp     [rdi+0E0h], r12b
0x14000ab6e  jnz     short loc_14000ABD8
0x14000ab70  cmp     cs:g_EnableDbgPrints, r12b
0x14000ab77  jz      short loc_14000AB94
0x14000ab79  mov     edx, 3; Level
0x14000ab7e  lea     r8, aDeviceIsNotHig; "Device is not High Speed\n"
0x14000ab85  lea     ecx, [rdx+4Ah]; ComponentId
0x14000ab88  call    cs:__imp_DbgPrintEx
0x14000ab8f  nop     dword ptr [rax+rax+00h]
0x14000ab94  mov     ebx, 0C00000BBh
0x14000ab99  jmp     loc_14000AA1C
0x14000ab9e  mov     r8, rsi; Length
0x14000aba1  lea     rdx, GUID_USB_CAPABILITY_SELECTIVE_SUSPEND; Source2
0x14000aba8  mov     rcx, r14; Source1
0x14000abab  call    cs:__imp_RtlCompareMemory
0x14000abb2  nop     dword ptr [rax+rax+00h]
0x14000abb7  cmp     rax, rsi
0x14000abba  jnz     short loc_14000ABE0
0x14000abbc  test    rbx, rbx
0x14000abbf  jz      short loc_14000ABD8
0x14000abc1  cmp     cs:g_EnableDbgPrints, r12b
0x14000abc8  mov     ebx, 0C000000Dh
0x14000abcd  jz      loc_14000AA1C
0x14000abd3  jmp     loc_14000AB4A
0x14000abd8  mov     ebx, r12d
0x14000abdb  jmp     loc_14000AA1C
0x14000abe0  cmp     cs:g_EnableDbgPrints, r12b
0x14000abe7  jz      loc_14000AAFD
0x14000abed  jmp     loc_14000AAE5
```
