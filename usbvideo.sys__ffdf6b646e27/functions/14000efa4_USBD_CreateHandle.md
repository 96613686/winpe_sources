# USBD_CreateHandle

- ea: `0x14000efa4`
- end: `0x14000f3bd`
- name: `USBD_CreateHandle`
- size: `1049`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT TargetDeviceObject, ULONG USBDClientContractVersion, ULONG PoolTag, USBD_HANDLE *USBDHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400156a0`

## callees

- `0x14000efa4`
- `0x14000f3c4`
- `0x14000f528`
- `0x140040a30`
- `0x140040a70`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000efe1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000efe1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f3a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f3a9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f116`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f116`
- `ntoskrnl!DbgPrintEx` at `0x14000f009`
- `ntoskrnl!DbgPrintEx` at `0x14000f0b8`
- `ntoskrnl!DbgPrintEx` at `0x14000f0f1`
- `ntoskrnl!DbgPrintEx` at `0x14000f13f`
- `ntoskrnl!DbgPrintEx` at `0x14000f1f6`
- `ntoskrnl!DbgPrintEx` at `0x14000f267`
- `ntoskrnl!DbgPrintEx` at `0x14000f2cf`
- `ntoskrnl!DbgPrintEx` at `0x14000f33b`
- `ntoskrnl!DbgPrintEx` at `0x14000f009`
- `ntoskrnl!DbgPrintEx` at `0x14000f0b8`
- `ntoskrnl!DbgPrintEx` at `0x14000f0f1`
- `ntoskrnl!DbgPrintEx` at `0x14000f13f`
- `ntoskrnl!DbgPrintEx` at `0x14000f1f6`
- `ntoskrnl!DbgPrintEx` at `0x14000f267`
- `ntoskrnl!DbgPrintEx` at `0x14000f2cf`
- `ntoskrnl!DbgPrintEx` at `0x14000f33b`
- `ntoskrnl!RtlGetVersion` at `0x14000f04b`
- `ntoskrnl!RtlGetVersion` at `0x14000f04b`

## string_xrefs

- `0x14000f1e9`: `USBD_CreateHandle Successful: usbdHandleInfo 0x%p\n`

## pseudocode

```c
NTSTATUS __stdcall USBD_CreateHandle(
        PDEVICE_OBJECT DeviceObject,
        PDEVICE_OBJECT TargetDeviceObject,
        ULONG USBDClientContractVersion,
        ULONG PoolTag,
        USBD_HANDLE *USBDHandle)
{
  NTSTATUS v7; // ebx
  POOL_TYPE v8; // ecx
  USBD_HANDLE PoolWithTag; // rax
  USBD_HANDLE v10; // rdi
  int InterfaceSynchronously; // eax
  char v12; // r15
  int v13; // eax
  int v15; // eax
  bool v16; // zf
  char v17; // al
  void (__fastcall *v18)(_QWORD); // rax
  _QWORD v19[10]; // [rsp+30h] [rbp-D0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF

  if ( KeGetCurrentIrql() )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Irql Too High\n");
    v7 = -1073741496;
LABEL_19:
    if ( !USBDHandle )
      return v7;
    goto LABEL_56;
  }
  if ( byte_14004C79D
    || (PoolType = NonPagedPool,
        memset(&VersionInformation.dwMajorVersion, 0, 0x118u),
        VersionInformation.dwOSVersionInfoSize = 284,
        RtlGetVersion(&VersionInformation) < 0)
    || VersionInformation.dwMajorVersion <= 6
    && (VersionInformation.dwMajorVersion != 6 || VersionInformation.dwMinorVersion < 2) )
  {
    v8 = PoolType;
  }
  else
  {
    v8 = 512;
    PoolType = 512;
  }
  byte_14004C79D = 1;
  if ( !DeviceObject )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "DeviceObject cannot be NULL\n");
LABEL_18:
    v7 = -1073741811;
    goto LABEL_19;
  }
  if ( !TargetDeviceObject )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "TargetDeviceObject cannot be NULL\n");
    goto LABEL_18;
  }
  if ( USBDHandle )
  {
    PoolWithTag = (USBD_HANDLE)ExAllocatePoolWithTag(v8, 0xE8u, 0x56425355u);
    v10 = PoolWithTag;
    if ( !PoolWithTag )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Allocation Failed\n");
      v7 = -1073741670;
LABEL_56:
      *USBDHandle = 0;
      return v7;
    }
    memset(PoolWithTag, 0, 0xE8u);
    USBDInternal_QueryUsbVerifierSettings((__int64)DeviceObject, (__int64)(v10 + 2));
    *(_DWORD *)v10 = 1145197397;
    *((_WORD *)v10 + 5) = 1539;
    *((_DWORD *)v10 + 54) = 1539;
    *((_WORD *)v10 + 4) = 200;
    *((_DWORD *)v10 + 10) = 1538;
    *((_QWORD *)v10 + 7) = DeviceObject;
    *((_DWORD *)v10 + 16) = 1447187285;
    *((_QWORD *)v10 + 9) = v10;
    *((_QWORD *)v10 + 26) = TargetDeviceObject;
    *((_DWORD *)v10 + 55) = 1;
    InterfaceSynchronously = USBDInternal_BuildAndSendQueryInterfaceSynchronously(
                               DeviceObject,
                               TargetDeviceObject,
                               (ULONG_PTR)&GUID_USBD_INTERFACE,
                               (USHORT *)v10 + 4);
    v7 = InterfaceSynchronously;
    if ( InterfaceSynchronously < 0 )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(
          0x4Du,
          3u,
          "Core stack (TargetDevieObject 0x%p) failed USBD_INTERFACE_VERSION_603, 0x%x\n",
          TargetDeviceObject,
          InterfaceSynchronously);
      *((_WORD *)v10 + 4) = 152;
      *((_WORD *)v10 + 5) = 1538;
      *((_DWORD *)v10 + 54) = 1538;
      v15 = USBDInternal_BuildAndSendQueryInterfaceSynchronously(
              DeviceObject,
              TargetDeviceObject,
              (ULONG_PTR)&GUID_USBD_INTERFACE,
              (USHORT *)v10 + 4);
      v7 = v15;
      if ( v15 < 0 )
      {
        v16 = g_EnableDbgPrints == 0;
        v12 = 0;
        *((_DWORD *)v10 + 54) = 1536;
        if ( !v16 )
          DbgPrintEx(
            0x4Du,
            3u,
            "Core stack (TargetDevieObject 0x%p) failed USBD_INTERFACE_VERSION_602, 0x%x\n",
            TargetDeviceObject,
            v15);
        v7 = 0;
LABEL_32:
        if ( g_EnableDbgPrints )
          DbgPrintEx(0x4Du, 3u, "USBD_CreateHandle Successful: usbdHandleInfo 0x%p\n", v10);
        if ( *((_DWORD *)v10 + 54) == 1536 )
        {
          memset(v19, 0, 0x48u);
          LODWORD(v19[0]) = 65608;
          v13 = USBDInternal_BuildAndSendQueryInterfaceSynchronously(
                  DeviceObject,
                  TargetDeviceObject,
                  (ULONG_PTR)&USB_BUS_INTERFACE_USBDI_GUID,
                  (USHORT *)v19);
          v7 = v13;
          if ( v13 >= 0 )
          {
            if ( v19[8] )
              v17 = ((__int64 (__fastcall *)(_QWORD))v19[8])(v19[1]);
            else
              v17 = 0;
            *((_BYTE *)v10 + 224) = v17;
            ((void (__fastcall *)(_QWORD))v19[3])(v19[1]);
          }
          else
          {
            if ( g_EnableDbgPrints )
              DbgPrintEx(
                0x4Du,
                0,
                "Core stack (TargetDevieObject 0x%p) failed query to USB_BUS_INTERFACE_USBDI_GUID : USB_BUSIF_USBDI_VERSION_1, 0x%x\n",
                TargetDeviceObject,
                v13);
            *((_DWORD *)v10 + 54) = -1;
            v7 = 0;
          }
        }
        else if ( v7 < 0 )
        {
          if ( v12 )
          {
            v18 = (void (__fastcall *)(_QWORD))*((_QWORD *)v10 + 14);
            if ( v18 )
              v18(*((_QWORD *)v10 + 6));
          }
          ExFreePoolWithTag(v10, 0x56425355u);
          goto LABEL_56;
        }
        *USBDHandle = v10;
        return v7;
      }
    }
    else
    {
      *((_DWORD *)v10 + 54) = *((unsigned __int16 *)v10 + 5);
    }
    v12 = 1;
    goto LABEL_32;
  }
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 0, "USBDHandle cannot be NULL\n");
  return -1073741811;
}

```

## disassembly

```asm
0x14000efa4  mov     [rsp-8+arg_10], rbx
0x14000efa9  push    rbp
0x14000efaa  push    rsi
0x14000efab  push    rdi
0x14000efac  push    r12
0x14000efae  push    r13
0x14000efb0  push    r14
0x14000efb2  push    r15
0x14000efb4  lea     rbp, [rsp-0B0h]
0x14000efbc  sub     rsp, 1B0h
0x14000efc3  mov     rax, cs:__security_cookie
0x14000efca  xor     rax, rsp
0x14000efcd  mov     [rbp+0E0h+var_40], rax
0x14000efd4  mov     r14, [rbp+0E0h+USBDHandle]
0x14000efdb  mov     rsi, rdx
0x14000efde  mov     r12, rcx
0x14000efe1  call    cs:__imp_KeGetCurrentIrql
0x14000efe8  nop     dword ptr [rax+rax+00h]
0x14000efed  xor     r13d, r13d
0x14000eff0  test    al, al
0x14000eff2  jz      short loc_14000F01F
0x14000eff4  cmp     cs:g_EnableDbgPrints, r13b
0x14000effb  jz      short loc_14000F015
0x14000effd  xor     edx, edx; Level
0x14000efff  lea     r8, Format; "Irql Too High\n"
0x14000f006  lea     ecx, [rdx+4Dh]; ComponentId
0x14000f009  call    cs:__imp_DbgPrintEx
0x14000f010  nop     dword ptr [rax+rax+00h]
0x14000f015  mov     ebx, 0C0000148h
0x14000f01a  jmp     loc_14000F0C9
0x14000f01f  cmp     cs:byte_14004C79D, r13b
0x14000f026  jnz     short loc_14000F076
0x14000f028  xor     edx, edx; Val
0x14000f02a  mov     cs:PoolType, r13d
0x14000f031  mov     r8d, 118h; Size
0x14000f037  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x14000f03b  call    memset
0x14000f040  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x14000f044  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14000f04b  call    cs:__imp_RtlGetVersion
0x14000f052  nop     dword ptr [rax+rax+00h]
0x14000f057  test    eax, eax
0x14000f059  js      short loc_14000F076
0x14000f05b  cmp     [rbp+0E0h+VersionInformation.dwMajorVersion], 6
0x14000f05f  ja      short loc_14000F069
0x14000f061  jnz     short loc_14000F076
0x14000f063  cmp     [rbp+0E0h+VersionInformation.dwMinorVersion], 2
0x14000f067  jb      short loc_14000F076
0x14000f069  mov     ecx, 200h
0x14000f06e  mov     cs:PoolType, ecx
0x14000f074  jmp     short loc_14000F07C
0x14000f076  mov     ecx, cs:PoolType; PoolType
0x14000f07c  mov     ebx, 1
0x14000f081  mov     cs:byte_14004C79D, bl
0x14000f087  test    r12, r12
0x14000f08a  jnz     short loc_14000F09E
0x14000f08c  cmp     cs:g_EnableDbgPrints, r13b
0x14000f093  jz      short loc_14000F0C4
0x14000f095  lea     r8, aDeviceobjectCa; "DeviceObject cannot be NULL\n"
0x14000f09c  jmp     short loc_14000F0B3
0x14000f09e  test    rsi, rsi
0x14000f0a1  jnz     short loc_14000F0D7
0x14000f0a3  cmp     cs:g_EnableDbgPrints, r13b
0x14000f0aa  jz      short loc_14000F0C4
0x14000f0ac  lea     r8, aTargetdeviceob; "TargetDeviceObject cannot be NULL\n"
0x14000f0b3  xor     edx, edx; Level
0x14000f0b5  lea     ecx, [rdx+4Dh]; ComponentId
0x14000f0b8  call    cs:__imp_DbgPrintEx
0x14000f0bf  nop     dword ptr [rax+rax+00h]
0x14000f0c4  mov     ebx, 0C000000Dh
0x14000f0c9  test    r14, r14
0x14000f0cc  jnz     loc_14000F3B5
0x14000f0d2  jmp     loc_14000F283
0x14000f0d7  test    r14, r14
0x14000f0da  jnz     short loc_14000F107
0x14000f0dc  cmp     cs:g_EnableDbgPrints, r13b
0x14000f0e3  jz      short loc_14000F0FD
0x14000f0e5  xor     edx, edx; Level
0x14000f0e7  lea     r8, aUsbdhandleCann; "USBDHandle cannot be NULL\n"
0x14000f0ee  lea     ecx, [rdx+4Dh]; ComponentId
0x14000f0f1  call    cs:__imp_DbgPrintEx
0x14000f0f8  nop     dword ptr [rax+rax+00h]
0x14000f0fd  mov     ebx, 0C000000Dh
0x14000f102  jmp     loc_14000F283
0x14000f107  mov     r15d, 0E8h
0x14000f10d  mov     r8d, 56425355h; Tag
0x14000f113  mov     edx, r15d; NumberOfBytes
0x14000f116  call    cs:__imp_ExAllocatePoolWithTag
0x14000f11d  nop     dword ptr [rax+rax+00h]
0x14000f122  mov     rdi, rax
0x14000f125  test    rax, rax
0x14000f128  jnz     short loc_14000F155
0x14000f12a  cmp     cs:g_EnableDbgPrints, r13b
0x14000f131  jz      short loc_14000F14B
0x14000f133  lea     r8, aAllocationFail; "Allocation Failed\n"
0x14000f13a  xor     edx, edx; Level
0x14000f13c  lea     ecx, [rax+4Dh]; ComponentId
0x14000f13f  call    cs:__imp_DbgPrintEx
0x14000f146  nop     dword ptr [rax+rax+00h]
0x14000f14b  mov     ebx, 0C000009Ah
0x14000f150  jmp     loc_14000F3B5
0x14000f155  mov     r8, r15; Size
0x14000f158  xor     edx, edx; Val
0x14000f15a  mov     rcx, rdi; void *
0x14000f15d  call    memset
0x14000f162  lea     r15, [rdi+8]
0x14000f166  mov     rcx, r12
0x14000f169  mov     rdx, r15
0x14000f16c  call    USBDInternal_QueryUsbVerifierSettings
0x14000f171  mov     eax, 603h
0x14000f176  mov     dword ptr [rdi], 44425355h
0x14000f17c  mov     r9, r15
0x14000f17f  mov     [rdi+0Ah], ax
0x14000f183  lea     r8, GUID_USBD_INTERFACE
0x14000f18a  mov     [rdi+0D8h], eax
0x14000f190  mov     rdx, rsi; PDEVICE_OBJECT
0x14000f193  mov     word ptr [r15], 0C8h
0x14000f199  mov     rcx, r12; DeviceObject
0x14000f19c  mov     dword ptr [rdi+28h], 602h
0x14000f1a3  mov     [rdi+38h], r12
0x14000f1a7  mov     dword ptr [rdi+40h], 56425355h
0x14000f1ae  mov     [rdi+48h], rdi
0x14000f1b2  mov     [rdi+0D0h], rsi
0x14000f1b9  mov     [rdi+0DCh], ebx
0x14000f1bf  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14000f1c4  mov     ebx, eax
0x14000f1c6  test    eax, eax
0x14000f1c8  js      loc_14000F2B0
0x14000f1ce  movzx   eax, word ptr [rdi+0Ah]
0x14000f1d2  mov     [rdi+0D8h], eax
0x14000f1d8  mov     r15b, 1
0x14000f1db  cmp     cs:g_EnableDbgPrints, r13b
0x14000f1e2  jz      short loc_14000F202
0x14000f1e4  mov     edx, 3; Level
0x14000f1e9  lea     r8, aUsbdCreatehand; "USBD_CreateHandle Successful: usbdHandl"...
0x14000f1f0  mov     r9, rdi
0x14000f1f3  lea     ecx, [rdx+4Ah]; ComponentId
0x14000f1f6  call    cs:__imp_DbgPrintEx
0x14000f1fd  nop     dword ptr [rax+rax+00h]
0x14000f202  cmp     dword ptr [rdi+0D8h], 600h
0x14000f20c  jnz     loc_14000F382
0x14000f212  xor     edx, edx; Val
0x14000f214  lea     rcx, [rsp+1E0h+var_1B0]; void *
0x14000f219  lea     r8d, [rdx+48h]; Size
0x14000f21d  call    memset
0x14000f222  lea     r9, [rsp+1E0h+var_1B0]
0x14000f227  mov     [rsp+1E0h+var_1B0], 10048h
0x14000f22f  lea     r8, USB_BUS_INTERFACE_USBDI_GUID
0x14000f236  mov     rdx, rsi; PDEVICE_OBJECT
0x14000f239  mov     rcx, r12; DeviceObject
0x14000f23c  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14000f241  mov     ebx, eax
0x14000f243  test    eax, eax
0x14000f245  jns     loc_14000F34F
0x14000f24b  cmp     cs:g_EnableDbgPrints, r13b
0x14000f252  jz      short loc_14000F273
0x14000f254  xor     edx, edx; Level
0x14000f256  mov     [rsp+1E0h+var_1C0], eax
0x14000f25a  mov     r9, rsi
0x14000f25d  lea     r8, aCoreStackTarge_0; "Core stack (TargetDevieObject 0x%p) fai"...
0x14000f264  lea     ecx, [rdx+4Dh]; ComponentId
0x14000f267  call    cs:__imp_DbgPrintEx
0x14000f26e  nop     dword ptr [rax+rax+00h]
0x14000f273  mov     dword ptr [rdi+0D8h], 0FFFFFFFFh
0x14000f27d  mov     ebx, r13d
0x14000f280  mov     [r14], rdi
0x14000f283  mov     eax, ebx
0x14000f285  mov     rcx, [rbp+0E0h+var_40]
0x14000f28c  xor     rcx, rsp; StackCookie
0x14000f28f  call    __security_check_cookie
0x14000f294  mov     rbx, [rsp+1E0h+arg_10]
0x14000f29c  add     rsp, 1B0h
0x14000f2a3  pop     r15
0x14000f2a5  pop     r14
0x14000f2a7  pop     r13
0x14000f2a9  pop     r12
0x14000f2ab  pop     rdi
0x14000f2ac  pop     rsi
0x14000f2ad  pop     rbp
0x14000f2ae  retn
0x14000f2b0  cmp     cs:g_EnableDbgPrints, r13b
0x14000f2b7  jz      short loc_14000F2DB
0x14000f2b9  mov     edx, 3; Level
0x14000f2be  mov     [rsp+1E0h+var_1C0], eax
0x14000f2c2  mov     r9, rsi
0x14000f2c5  lea     r8, aCoreStackTarge_1; "Core stack (TargetDevieObject 0x%p) fai"...
0x14000f2cc  lea     ecx, [rdx+4Ah]; ComponentId
0x14000f2cf  call    cs:__imp_DbgPrintEx
0x14000f2d6  nop     dword ptr [rax+rax+00h]
0x14000f2db  mov     eax, 602h
0x14000f2e0  mov     word ptr [r15], 98h
0x14000f2e6  mov     r9, r15
0x14000f2e9  mov     [rdi+0Ah], ax
0x14000f2ed  lea     r8, GUID_USBD_INTERFACE
0x14000f2f4  mov     [rdi+0D8h], eax
0x14000f2fa  mov     rdx, rsi; PDEVICE_OBJECT
0x14000f2fd  mov     rcx, r12; DeviceObject
0x14000f300  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14000f305  mov     ebx, eax
0x14000f307  test    eax, eax
0x14000f309  jns     loc_14000F1D8
0x14000f30f  cmp     cs:g_EnableDbgPrints, r13b
0x14000f316  mov     r15b, r13b
0x14000f319  mov     dword ptr [rdi+0D8h], 600h
0x14000f323  jz      short loc_14000F347
0x14000f325  mov     edx, 3; Level
0x14000f32a  mov     [rsp+1E0h+var_1C0], eax
0x14000f32e  mov     r9, rsi
0x14000f331  lea     r8, aCoreStackTarge; "Core stack (TargetDevieObject 0x%p) fai"...
0x14000f338  lea     ecx, [rdx+4Ah]; ComponentId
0x14000f33b  call    cs:__imp_DbgPrintEx
0x14000f342  nop     dword ptr [rax+rax+00h]
0x14000f347  mov     ebx, r13d
0x14000f34a  jmp     loc_14000F1DB
0x14000f34f  mov     rax, [rsp+1E0h+var_170]
0x14000f354  test    rax, rax
0x14000f357  jz      short loc_14000F365
0x14000f359  mov     rcx, [rsp+1E0h+var_1A8]
0x14000f35e  call    _guard_dispatch_icall
0x14000f363  jmp     short loc_14000F368
0x14000f365  mov     al, r13b
0x14000f368  mov     [rdi+0E0h], al
0x14000f36e  mov     rcx, [rsp+1E0h+var_1A8]
0x14000f373  mov     rax, [rsp+1E0h+var_198]
0x14000f378  call    _guard_dispatch_icall
0x14000f37d  jmp     loc_14000F280
0x14000f382  test    ebx, ebx
0x14000f384  jns     loc_14000F280
0x14000f38a  test    r15b, r15b
0x14000f38d  jz      short loc_14000F3A1
0x14000f38f  mov     rax, [rdi+70h]
0x14000f393  test    rax, rax
0x14000f396  jz      short loc_14000F3A1
0x14000f398  mov     rcx, [rdi+30h]
0x14000f39c  call    _guard_dispatch_icall
0x14000f3a1  mov     edx, 56425355h; Tag
0x14000f3a6  mov     rcx, rdi; P
0x14000f3a9  call    cs:__imp_ExFreePoolWithTag
0x14000f3b0  nop     dword ptr [rax+rax+00h]
0x14000f3b5  mov     [r14], r13
0x14000f3b8  jmp     loc_14000F283
```
