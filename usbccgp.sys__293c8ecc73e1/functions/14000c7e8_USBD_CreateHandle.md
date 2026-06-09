# USBD_CreateHandle

- ea: `0x14000c7e8`
- end: `0x14000cc01`
- name: `USBD_CreateHandle`
- size: `1049`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT TargetDeviceObject, ULONG USBDClientContractVersion, ULONG PoolTag, USBD_HANDLE *USBDHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14002a2e0`

## callees

- `0x14000c7e8`
- `0x14000cc08`
- `0x14000cd78`
- `0x140014d10`
- `0x140014d50`
- `0x140015100`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbed`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c825`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c825`
- `ntoskrnl!DbgPrintEx` at `0x14000c84d`
- `ntoskrnl!DbgPrintEx` at `0x14000c8fc`
- `ntoskrnl!DbgPrintEx` at `0x14000c935`
- `ntoskrnl!DbgPrintEx` at `0x14000c983`
- `ntoskrnl!DbgPrintEx` at `0x14000ca3a`
- `ntoskrnl!DbgPrintEx` at `0x14000caab`
- `ntoskrnl!DbgPrintEx` at `0x14000cb13`
- `ntoskrnl!DbgPrintEx` at `0x14000cb7f`
- `ntoskrnl!DbgPrintEx` at `0x14000c84d`
- `ntoskrnl!DbgPrintEx` at `0x14000c8fc`
- `ntoskrnl!DbgPrintEx` at `0x14000c935`
- `ntoskrnl!DbgPrintEx` at `0x14000c983`
- `ntoskrnl!DbgPrintEx` at `0x14000ca3a`
- `ntoskrnl!DbgPrintEx` at `0x14000caab`
- `ntoskrnl!DbgPrintEx` at `0x14000cb13`
- `ntoskrnl!DbgPrintEx` at `0x14000cb7f`
- `ntoskrnl!RtlGetVersion` at `0x14000c88f`
- `ntoskrnl!RtlGetVersion` at `0x14000c88f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c95a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c95a`

## string_xrefs

- `0x14000ca2d`: `USBD_CreateHandle Successful: usbdHandleInfo 0x%p\n`

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
  if ( byte_14001C3F0
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
    v8 = NonPagedPoolNx;
    PoolType = NonPagedPoolNx;
  }
  byte_14001C3F0 = 1;
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
    PoolWithTag = (USBD_HANDLE)ExAllocatePoolWithTag(v8, 0xE8u, 0x43627355u);
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
    *((_DWORD *)v10 + 16) = 1130525525;
    *((_QWORD *)v10 + 9) = v10;
    *((_QWORD *)v10 + 26) = TargetDeviceObject;
    *((_DWORD *)v10 + 55) = 1;
    InterfaceSynchronously = USBDInternal_BuildAndSendQueryInterfaceSynchronously(
                               DeviceObject,
                               TargetDeviceObject,
                               (unsigned __int64)&GUID_USBD_INTERFACE,
                               (unsigned __int16 *)v10 + 4);
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
              (unsigned __int64)&GUID_USBD_INTERFACE,
              (unsigned __int16 *)v10 + 4);
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
                  (unsigned __int64)&USB_BUS_INTERFACE_USBDI_GUID,
                  (unsigned __int16 *)v19);
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
          ExFreePoolWithTag(v10, 0x43627355u);
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
0x14000c7e8  mov     [rsp-8+arg_10], rbx
0x14000c7ed  push    rbp
0x14000c7ee  push    rsi
0x14000c7ef  push    rdi
0x14000c7f0  push    r12
0x14000c7f2  push    r13
0x14000c7f4  push    r14
0x14000c7f6  push    r15
0x14000c7f8  lea     rbp, [rsp-0B0h]
0x14000c800  sub     rsp, 1B0h
0x14000c807  mov     rax, cs:__security_cookie
0x14000c80e  xor     rax, rsp
0x14000c811  mov     [rbp+0E0h+var_40], rax
0x14000c818  mov     r14, [rbp+0E0h+USBDHandle]
0x14000c81f  mov     rsi, rdx
0x14000c822  mov     r12, rcx
0x14000c825  call    cs:__imp_KeGetCurrentIrql
0x14000c82c  nop     dword ptr [rax+rax+00h]
0x14000c831  xor     r13d, r13d
0x14000c834  test    al, al
0x14000c836  jz      short loc_14000C863
0x14000c838  cmp     cs:g_EnableDbgPrints, r13b
0x14000c83f  jz      short loc_14000C859
0x14000c841  xor     edx, edx; Level
0x14000c843  lea     r8, aIrqlTooHigh; "Irql Too High\n"
0x14000c84a  lea     ecx, [rdx+4Dh]; ComponentId
0x14000c84d  call    cs:__imp_DbgPrintEx
0x14000c854  nop     dword ptr [rax+rax+00h]
0x14000c859  mov     ebx, 0C0000148h
0x14000c85e  jmp     loc_14000C90D
0x14000c863  cmp     cs:byte_14001C3F0, r13b
0x14000c86a  jnz     short loc_14000C8BA
0x14000c86c  xor     edx, edx; Val
0x14000c86e  mov     cs:PoolType, r13d
0x14000c875  mov     r8d, 118h; Size
0x14000c87b  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x14000c87f  call    memset
0x14000c884  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x14000c888  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14000c88f  call    cs:__imp_RtlGetVersion
0x14000c896  nop     dword ptr [rax+rax+00h]
0x14000c89b  test    eax, eax
0x14000c89d  js      short loc_14000C8BA
0x14000c89f  cmp     [rbp+0E0h+VersionInformation.dwMajorVersion], 6
0x14000c8a3  ja      short loc_14000C8AD
0x14000c8a5  jnz     short loc_14000C8BA
0x14000c8a7  cmp     [rbp+0E0h+VersionInformation.dwMinorVersion], 2
0x14000c8ab  jb      short loc_14000C8BA
0x14000c8ad  mov     ecx, 200h
0x14000c8b2  mov     cs:PoolType, ecx
0x14000c8b8  jmp     short loc_14000C8C0
0x14000c8ba  mov     ecx, cs:PoolType; PoolType
0x14000c8c0  mov     ebx, 1
0x14000c8c5  mov     cs:byte_14001C3F0, bl
0x14000c8cb  test    r12, r12
0x14000c8ce  jnz     short loc_14000C8E2
0x14000c8d0  cmp     cs:g_EnableDbgPrints, r13b
0x14000c8d7  jz      short loc_14000C908
0x14000c8d9  lea     r8, aDeviceobjectCa; "DeviceObject cannot be NULL\n"
0x14000c8e0  jmp     short loc_14000C8F7
0x14000c8e2  test    rsi, rsi
0x14000c8e5  jnz     short loc_14000C91B
0x14000c8e7  cmp     cs:g_EnableDbgPrints, r13b
0x14000c8ee  jz      short loc_14000C908
0x14000c8f0  lea     r8, aTargetdeviceob; "TargetDeviceObject cannot be NULL\n"
0x14000c8f7  xor     edx, edx; Level
0x14000c8f9  lea     ecx, [rdx+4Dh]; ComponentId
0x14000c8fc  call    cs:__imp_DbgPrintEx
0x14000c903  nop     dword ptr [rax+rax+00h]
0x14000c908  mov     ebx, 0C000000Dh
0x14000c90d  test    r14, r14
0x14000c910  jnz     loc_14000CBF9
0x14000c916  jmp     loc_14000CAC7
0x14000c91b  test    r14, r14
0x14000c91e  jnz     short loc_14000C94B
0x14000c920  cmp     cs:g_EnableDbgPrints, r13b
0x14000c927  jz      short loc_14000C941
0x14000c929  xor     edx, edx; Level
0x14000c92b  lea     r8, aUsbdhandleCann; "USBDHandle cannot be NULL\n"
0x14000c932  lea     ecx, [rdx+4Dh]; ComponentId
0x14000c935  call    cs:__imp_DbgPrintEx
0x14000c93c  nop     dword ptr [rax+rax+00h]
0x14000c941  mov     ebx, 0C000000Dh
0x14000c946  jmp     loc_14000CAC7
0x14000c94b  mov     r15d, 0E8h
0x14000c951  mov     r8d, 43627355h; Tag
0x14000c957  mov     edx, r15d; NumberOfBytes
0x14000c95a  call    cs:__imp_ExAllocatePoolWithTag
0x14000c961  nop     dword ptr [rax+rax+00h]
0x14000c966  mov     rdi, rax
0x14000c969  test    rax, rax
0x14000c96c  jnz     short loc_14000C999
0x14000c96e  cmp     cs:g_EnableDbgPrints, r13b
0x14000c975  jz      short loc_14000C98F
0x14000c977  lea     r8, aAllocationFail; "Allocation Failed\n"
0x14000c97e  xor     edx, edx; Level
0x14000c980  lea     ecx, [rax+4Dh]; ComponentId
0x14000c983  call    cs:__imp_DbgPrintEx
0x14000c98a  nop     dword ptr [rax+rax+00h]
0x14000c98f  mov     ebx, 0C000009Ah
0x14000c994  jmp     loc_14000CBF9
0x14000c999  mov     r8, r15; Size
0x14000c99c  xor     edx, edx; Val
0x14000c99e  mov     rcx, rdi; void *
0x14000c9a1  call    memset
0x14000c9a6  lea     r15, [rdi+8]
0x14000c9aa  mov     rcx, r12
0x14000c9ad  mov     rdx, r15
0x14000c9b0  call    USBDInternal_QueryUsbVerifierSettings
0x14000c9b5  mov     eax, 603h
0x14000c9ba  mov     dword ptr [rdi], 44425355h
0x14000c9c0  mov     r9, r15
0x14000c9c3  mov     [rdi+0Ah], ax
0x14000c9c7  lea     r8, GUID_USBD_INTERFACE
0x14000c9ce  mov     [rdi+0D8h], eax
0x14000c9d4  mov     rdx, rsi; PDEVICE_OBJECT
0x14000c9d7  mov     word ptr [r15], 0C8h
0x14000c9dd  mov     rcx, r12; DeviceObject
0x14000c9e0  mov     dword ptr [rdi+28h], 602h
0x14000c9e7  mov     [rdi+38h], r12
0x14000c9eb  mov     dword ptr [rdi+40h], 43627355h
0x14000c9f2  mov     [rdi+48h], rdi
0x14000c9f6  mov     [rdi+0D0h], rsi
0x14000c9fd  mov     [rdi+0DCh], ebx
0x14000ca03  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14000ca08  mov     ebx, eax
0x14000ca0a  test    eax, eax
0x14000ca0c  js      loc_14000CAF4
0x14000ca12  movzx   eax, word ptr [rdi+0Ah]
0x14000ca16  mov     [rdi+0D8h], eax
0x14000ca1c  mov     r15b, 1
0x14000ca1f  cmp     cs:g_EnableDbgPrints, r13b
0x14000ca26  jz      short loc_14000CA46
0x14000ca28  mov     edx, 3; Level
0x14000ca2d  lea     r8, aUsbdCreatehand; "USBD_CreateHandle Successful: usbdHandl"...
0x14000ca34  mov     r9, rdi
0x14000ca37  lea     ecx, [rdx+4Ah]; ComponentId
0x14000ca3a  call    cs:__imp_DbgPrintEx
0x14000ca41  nop     dword ptr [rax+rax+00h]
0x14000ca46  cmp     dword ptr [rdi+0D8h], 600h
0x14000ca50  jnz     loc_14000CBC6
0x14000ca56  xor     edx, edx; Val
0x14000ca58  lea     rcx, [rsp+1E0h+var_1B0]; void *
0x14000ca5d  lea     r8d, [rdx+48h]; Size
0x14000ca61  call    memset
0x14000ca66  lea     r9, [rsp+1E0h+var_1B0]
0x14000ca6b  mov     [rsp+1E0h+var_1B0], 10048h
0x14000ca73  lea     r8, USB_BUS_INTERFACE_USBDI_GUID
0x14000ca7a  mov     rdx, rsi; PDEVICE_OBJECT
0x14000ca7d  mov     rcx, r12; DeviceObject
0x14000ca80  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14000ca85  mov     ebx, eax
0x14000ca87  test    eax, eax
0x14000ca89  jns     loc_14000CB93
0x14000ca8f  cmp     cs:g_EnableDbgPrints, r13b
0x14000ca96  jz      short loc_14000CAB7
0x14000ca98  xor     edx, edx; Level
0x14000ca9a  mov     [rsp+1E0h+var_1C0], eax
0x14000ca9e  mov     r9, rsi
0x14000caa1  lea     r8, aCoreStackTarge_0; "Core stack (TargetDevieObject 0x%p) fai"...
0x14000caa8  lea     ecx, [rdx+4Dh]; ComponentId
0x14000caab  call    cs:__imp_DbgPrintEx
0x14000cab2  nop     dword ptr [rax+rax+00h]
0x14000cab7  mov     dword ptr [rdi+0D8h], 0FFFFFFFFh
0x14000cac1  mov     ebx, r13d
0x14000cac4  mov     [r14], rdi
0x14000cac7  mov     eax, ebx
0x14000cac9  mov     rcx, [rbp+0E0h+var_40]
0x14000cad0  xor     rcx, rsp; StackCookie
0x14000cad3  call    __security_check_cookie
0x14000cad8  mov     rbx, [rsp+1E0h+arg_10]
0x14000cae0  add     rsp, 1B0h
0x14000cae7  pop     r15
0x14000cae9  pop     r14
0x14000caeb  pop     r13
0x14000caed  pop     r12
0x14000caef  pop     rdi
0x14000caf0  pop     rsi
0x14000caf1  pop     rbp
0x14000caf2  retn
0x14000caf4  cmp     cs:g_EnableDbgPrints, r13b
0x14000cafb  jz      short loc_14000CB1F
0x14000cafd  mov     edx, 3; Level
0x14000cb02  mov     [rsp+1E0h+var_1C0], eax
0x14000cb06  mov     r9, rsi
0x14000cb09  lea     r8, aCoreStackTarge_1; "Core stack (TargetDevieObject 0x%p) fai"...
0x14000cb10  lea     ecx, [rdx+4Ah]; ComponentId
0x14000cb13  call    cs:__imp_DbgPrintEx
0x14000cb1a  nop     dword ptr [rax+rax+00h]
0x14000cb1f  mov     eax, 602h
0x14000cb24  mov     word ptr [r15], 98h
0x14000cb2a  mov     r9, r15
0x14000cb2d  mov     [rdi+0Ah], ax
0x14000cb31  lea     r8, GUID_USBD_INTERFACE
0x14000cb38  mov     [rdi+0D8h], eax
0x14000cb3e  mov     rdx, rsi; PDEVICE_OBJECT
0x14000cb41  mov     rcx, r12; DeviceObject
0x14000cb44  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14000cb49  mov     ebx, eax
0x14000cb4b  test    eax, eax
0x14000cb4d  jns     loc_14000CA1C
0x14000cb53  cmp     cs:g_EnableDbgPrints, r13b
0x14000cb5a  mov     r15b, r13b
0x14000cb5d  mov     dword ptr [rdi+0D8h], 600h
0x14000cb67  jz      short loc_14000CB8B
0x14000cb69  mov     edx, 3; Level
0x14000cb6e  mov     [rsp+1E0h+var_1C0], eax
0x14000cb72  mov     r9, rsi
0x14000cb75  lea     r8, aCoreStackTarge; "Core stack (TargetDevieObject 0x%p) fai"...
0x14000cb7c  lea     ecx, [rdx+4Ah]; ComponentId
0x14000cb7f  call    cs:__imp_DbgPrintEx
0x14000cb86  nop     dword ptr [rax+rax+00h]
0x14000cb8b  mov     ebx, r13d
0x14000cb8e  jmp     loc_14000CA1F
0x14000cb93  mov     rax, [rsp+1E0h+var_170]
0x14000cb98  test    rax, rax
0x14000cb9b  jz      short loc_14000CBA9
0x14000cb9d  mov     rcx, [rsp+1E0h+var_1A8]
0x14000cba2  call    _guard_dispatch_icall
0x14000cba7  jmp     short loc_14000CBAC
0x14000cba9  mov     al, r13b
0x14000cbac  mov     [rdi+0E0h], al
0x14000cbb2  mov     rcx, [rsp+1E0h+var_1A8]
0x14000cbb7  mov     rax, [rsp+1E0h+var_198]
0x14000cbbc  call    _guard_dispatch_icall
0x14000cbc1  jmp     loc_14000CAC4
0x14000cbc6  test    ebx, ebx
0x14000cbc8  jns     loc_14000CAC4
0x14000cbce  test    r15b, r15b
0x14000cbd1  jz      short loc_14000CBE5
0x14000cbd3  mov     rax, [rdi+70h]
0x14000cbd7  test    rax, rax
0x14000cbda  jz      short loc_14000CBE5
0x14000cbdc  mov     rcx, [rdi+30h]
0x14000cbe0  call    _guard_dispatch_icall
0x14000cbe5  mov     edx, 43627355h; Tag
0x14000cbea  mov     rcx, rdi; P
0x14000cbed  call    cs:__imp_ExFreePoolWithTag
0x14000cbf4  nop     dword ptr [rax+rax+00h]
0x14000cbf9  mov     [r14], r13
0x14000cbfc  jmp     loc_14000CAC7
```
