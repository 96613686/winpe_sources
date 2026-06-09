# USBD_QueryUsbCapability

- ea: `0x1400434e0`
- end: `0x140043744`
- name: `USBD_QueryUsbCapability`
- size: `612`
- prototype: `NTSTATUS __stdcall(USBD_HANDLE USBDHandle, const GUID *CapabilityType, ULONG OutputBufferLength, PUCHAR OutputBuffer, PULONG ResultLength)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ed20`

## callees

- `0x140042bfc`
- `0x1400434e0`
- `0x140045530`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004351e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004351e`
- `ntoskrnl!RtlCompareMemory` at `0x140043611`
- `ntoskrnl!RtlCompareMemory` at `0x14004369a`
- `ntoskrnl!RtlCompareMemory` at `0x140043611`
- `ntoskrnl!RtlCompareMemory` at `0x14004369a`
- `ntoskrnl!DbgPrintEx` at `0x140043546`
- `ntoskrnl!DbgPrintEx` at `0x1400435dd`
- `ntoskrnl!DbgPrintEx` at `0x140043645`
- `ntoskrnl!DbgPrintEx` at `0x140043677`
- `ntoskrnl!DbgPrintEx` at `0x140043546`
- `ntoskrnl!DbgPrintEx` at `0x1400435dd`
- `ntoskrnl!DbgPrintEx` at `0x140043645`
- `ntoskrnl!DbgPrintEx` at `0x140043677`

## string_xrefs

- `0x140043639`: `OutputBuffer must be NULL for GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE\n`

## pseudocode

```c
NTSTATUS __stdcall USBD_QueryUsbCapability(
        USBD_HANDLE USBDHandle,
        const GUID *CapabilityType,
        ULONG OutputBufferLength,
        PUCHAR OutputBuffer,
        PULONG ResultLength)
{
  NTSTATUS v9; // ebx
  int v10; // eax
  __int64 v11; // rax
  struct _DEVICE_OBJECT *v12; // rdx
  struct _DEVICE_OBJECT *v13; // rcx
  __int128 v15; // [rsp+30h] [rbp-30h] BYREF
  GUID v16; // [rsp+40h] [rbp-20h]
  __int64 v17; // [rsp+50h] [rbp-10h]

  v15 = 0;
  v17 = 0;
  v16 = 0;
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
  if ( OutputBufferLength )
  {
    if ( !OutputBuffer )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "OutputBuffer cant be NULL if OutputBufferLength is not zero\n");
      return -1073741811;
    }
  }
  else if ( OutputBuffer )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "OutputBuffer must be NULL if OutputBufferLength is zero\n");
    return -1073741811;
  }
  v10 = *((_DWORD *)USBDHandle + 54);
  if ( v10 == -1 )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(
        0x4Du,
        0,
        "Could not exchange an interface with the Underlying USB core stack, querrying for capability is not possible\n");
    return -1073741822;
  }
  if ( v10 != 1536 )
  {
    v11 = *((_QWORD *)USBDHandle + 6);
    v12 = (struct _DEVICE_OBJECT *)*((_QWORD *)USBDHandle + 26);
    v13 = (struct _DEVICE_OBJECT *)*((_QWORD *)USBDHandle + 7);
    v16 = *CapabilityType;
    *(_QWORD *)&v15 = 2621441;
    *((_QWORD *)&v15 + 1) = v11;
    v17 = OutputBufferLength;
    return USBDInternal_BuildandSendIoctlSynchronously(v13, v12, (_IRP *)OutputBuffer, (unsigned __int64)&v15);
  }
  if ( RtlCompareMemory(CapabilityType, &GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE, 0x10u) == 16 )
  {
    if ( OutputBuffer )
    {
      v9 = -1073741811;
      if ( g_EnableDbgPrints )
        DbgPrintEx(
          0x4Du,
          0,
          "OutputBuffer must be NULL for GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE\n");
      return v9;
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
  v9 = -1073741811;
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 0, "OutputBuffer must be NULL for GUID_USB_CAPABILITY_SELECTIVE_SUSPEND\n");
  return v9;
}

```

## disassembly

```asm
0x1400434e0  mov     [rsp-28h+arg_10], rbx
0x1400434e5  push    rbp
0x1400434e6  push    rsi
0x1400434e7  push    rdi
0x1400434e8  push    r14
0x1400434ea  push    r15
0x1400434ec  mov     rbp, rsp
0x1400434ef  sub     rsp, 60h
0x1400434f3  mov     rax, cs:__security_cookie
0x1400434fa  xor     rax, rsp
0x1400434fd  mov     [rbp+var_8], rax
0x140043501  xorps   xmm0, xmm0
0x140043504  xor     eax, eax
0x140043506  movups  [rbp+var_30], xmm0
0x14004350a  mov     [rbp+var_10], rax
0x14004350e  mov     rbx, r9
0x140043511  movups  [rbp+var_20], xmm0
0x140043515  mov     r14d, r8d
0x140043518  mov     rsi, rdx
0x14004351b  mov     rdi, rcx
0x14004351e  call    cs:__imp_KeGetCurrentIrql
0x140043525  nop     dword ptr [rax+rax+00h]
0x14004352a  xor     r15d, r15d
0x14004352d  test    al, al
0x14004352f  jz      short loc_14004355C
0x140043531  cmp     cs:g_EnableDbgPrints, r15b
0x140043538  jz      short loc_140043552
0x14004353a  lea     r8, aPassiveLevelRe; "PASSIVE_LEVEL required\n"
0x140043541  xor     edx, edx; Level
0x140043543  lea     ecx, [rdx+4Dh]; ComponentId
0x140043546  call    cs:__imp_DbgPrintEx
0x14004354d  nop     dword ptr [rax+rax+00h]
0x140043552  mov     ebx, 0C000000Dh
0x140043557  jmp     loc_140043721
0x14004355c  test    rdi, rdi
0x14004355f  jnz     short loc_140043573
0x140043561  cmp     cs:g_EnableDbgPrints, r15b
0x140043568  jz      short loc_140043552
0x14004356a  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x140043571  jmp     short loc_140043541
0x140043573  test    rsi, rsi
0x140043576  jnz     short loc_14004358A
0x140043578  cmp     cs:g_EnableDbgPrints, r15b
0x14004357f  jz      short loc_140043552
0x140043581  lea     r8, aCapabilitytype; "CapabilityType cant be NULL\n"
0x140043588  jmp     short loc_140043541
0x14004358a  test    r14d, r14d
0x14004358d  jz      short loc_1400435A6
0x14004358f  test    rbx, rbx
0x140043592  jnz     short loc_1400435BD
0x140043594  cmp     cs:g_EnableDbgPrints, r15b
0x14004359b  jz      short loc_140043552
0x14004359d  lea     r8, aOutputbufferCa; "OutputBuffer cant be NULL if OutputBuff"...
0x1400435a4  jmp     short loc_140043541
0x1400435a6  test    rbx, rbx
0x1400435a9  jz      short loc_1400435BD
0x1400435ab  cmp     cs:g_EnableDbgPrints, r15b
0x1400435b2  jz      short loc_140043552
0x1400435b4  lea     r8, aOutputbufferMu_1; "OutputBuffer must be NULL if OutputBuff"...
0x1400435bb  jmp     short loc_140043541
0x1400435bd  mov     eax, [rdi+0D8h]
0x1400435c3  cmp     eax, 0FFFFFFFFh
0x1400435c6  jnz     short loc_1400435F3
0x1400435c8  cmp     cs:g_EnableDbgPrints, r15b
0x1400435cf  jz      short loc_1400435E9
0x1400435d1  lea     r8, aCouldNotExchan; "Could not exchange an interface with th"...
0x1400435d8  xor     edx, edx; Level
0x1400435da  lea     ecx, [rdx+4Dh]; ComponentId
0x1400435dd  call    cs:__imp_DbgPrintEx
0x1400435e4  nop     dword ptr [rax+rax+00h]
0x1400435e9  mov     ebx, 0C0000002h
0x1400435ee  jmp     loc_140043721
0x1400435f3  cmp     eax, 600h
0x1400435f8  jnz     loc_1400436E8
0x1400435fe  mov     r14d, 10h
0x140043604  lea     rdx, GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE; Source2
0x14004360b  mov     r8d, r14d; Length
0x14004360e  mov     rcx, rsi; Source1
0x140043611  call    cs:__imp_RtlCompareMemory
0x140043618  nop     dword ptr [rax+rax+00h]
0x14004361d  cmp     rax, r14
0x140043620  jnz     short loc_14004368D
0x140043622  test    rbx, rbx
0x140043625  jz      short loc_140043656
0x140043627  cmp     cs:g_EnableDbgPrints, r15b
0x14004362e  mov     ebx, 0C000000Dh
0x140043633  jz      loc_140043721
0x140043639  lea     r8, aOutputbufferMu_0; "OutputBuffer must be NULL for GUID_USB_"...
0x140043640  xor     edx, edx; Level
0x140043642  lea     ecx, [rdx+4Dh]; ComponentId
0x140043645  call    cs:__imp_DbgPrintEx
0x14004364c  nop     dword ptr [rax+rax+00h]
0x140043651  jmp     loc_140043721
0x140043656  cmp     [rdi+0E0h], r15b
0x14004365d  jnz     short loc_1400436CA
0x14004365f  cmp     cs:g_EnableDbgPrints, r15b
0x140043666  jz      short loc_140043683
0x140043668  mov     edx, 3; Level
0x14004366d  lea     r8, aDeviceIsNotHig; "Device is not High Speed\n"
0x140043674  lea     ecx, [rdx+4Ah]; ComponentId
0x140043677  call    cs:__imp_DbgPrintEx
0x14004367e  nop     dword ptr [rax+rax+00h]
0x140043683  mov     ebx, 0C00000BBh
0x140043688  jmp     loc_140043721
0x14004368d  mov     r8, r14; Length
0x140043690  lea     rdx, GUID_USB_CAPABILITY_SELECTIVE_SUSPEND; Source2
0x140043697  mov     rcx, rsi; Source1
0x14004369a  call    cs:__imp_RtlCompareMemory
0x1400436a1  nop     dword ptr [rax+rax+00h]
0x1400436a6  cmp     rax, r14
0x1400436a9  jnz     short loc_1400436CF
0x1400436ab  test    rbx, rbx
0x1400436ae  jz      short loc_1400436CA
0x1400436b0  cmp     cs:g_EnableDbgPrints, r15b
0x1400436b7  mov     ebx, 0C000000Dh
0x1400436bc  jz      short loc_140043721
0x1400436be  lea     r8, aOutputbufferMu; "OutputBuffer must be NULL for GUID_USB_"...
0x1400436c5  jmp     loc_140043640
0x1400436ca  mov     ebx, r15d
0x1400436cd  jmp     short loc_140043721
0x1400436cf  cmp     cs:g_EnableDbgPrints, r15b
0x1400436d6  jz      loc_1400435E9
0x1400436dc  lea     r8, aQueryusbcapabi; "QueryUsbCapability not supported/implem"...
0x1400436e3  jmp     loc_1400435D8
0x1400436e8  movups  xmm0, xmmword ptr [rsi]
0x1400436eb  mov     rax, [rdi+30h]
0x1400436ef  lea     r9, [rbp+var_30]
0x1400436f3  mov     rdx, [rdi+0D0h]; PDEVICE_OBJECT
0x1400436fa  mov     r8, rbx
0x1400436fd  mov     rcx, [rdi+38h]; DeviceObject
0x140043701  movdqu  [rbp+var_20], xmm0
0x140043706  mov     qword ptr [rbp+var_30], 280001h
0x14004370e  mov     dword ptr [rbp+var_10+4], r15d
0x140043712  mov     qword ptr [rbp+var_30+8], rax
0x140043716  mov     dword ptr [rbp+var_10], r14d
0x14004371a  call    USBDInternal_BuildandSendIoctlSynchronously
0x14004371f  mov     ebx, eax
0x140043721  mov     eax, ebx
0x140043723  mov     rcx, [rbp+var_8]
0x140043727  xor     rcx, rsp; StackCookie
0x14004372a  call    __security_check_cookie
0x14004372f  mov     rbx, [rsp+60h+arg_10]
0x140043737  add     rsp, 60h
0x14004373b  pop     r15
0x14004373d  pop     r14
0x14004373f  pop     rdi
0x140043740  pop     rsi
0x140043741  pop     rbp
0x140043742  retn
```
