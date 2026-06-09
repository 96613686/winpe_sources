# USBD_CreateHandle

- ea: `0x1400430c0`
- end: `0x1400434d9`
- name: `USBD_CreateHandle`
- size: `1049`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT TargetDeviceObject, ULONG USBDClientContractVersion, ULONG PoolTag, USBD_HANDLE *USBDHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000ed20`

## callees

- `0x1400428a8`
- `0x140042d48`
- `0x1400430c0`
- `0x140045530`
- `0x140045570`
- `0x140045940`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400430fd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400430fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400434c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400434c5`
- `ntoskrnl!DbgPrintEx` at `0x140043125`
- `ntoskrnl!DbgPrintEx` at `0x1400431d4`
- `ntoskrnl!DbgPrintEx` at `0x14004320d`
- `ntoskrnl!DbgPrintEx` at `0x14004325b`
- `ntoskrnl!DbgPrintEx` at `0x140043312`
- `ntoskrnl!DbgPrintEx` at `0x140043383`
- `ntoskrnl!DbgPrintEx` at `0x1400433eb`
- `ntoskrnl!DbgPrintEx` at `0x140043457`
- `ntoskrnl!DbgPrintEx` at `0x140043125`
- `ntoskrnl!DbgPrintEx` at `0x1400431d4`
- `ntoskrnl!DbgPrintEx` at `0x14004320d`
- `ntoskrnl!DbgPrintEx` at `0x14004325b`
- `ntoskrnl!DbgPrintEx` at `0x140043312`
- `ntoskrnl!DbgPrintEx` at `0x140043383`
- `ntoskrnl!DbgPrintEx` at `0x1400433eb`
- `ntoskrnl!DbgPrintEx` at `0x140043457`
- `ntoskrnl!RtlGetVersion` at `0x140043167`
- `ntoskrnl!RtlGetVersion` at `0x140043167`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043232`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043232`

## string_xrefs

- `0x140043305`: `USBD_CreateHandle Successful: usbdHandleInfo 0x%p\n`

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

  if ( !KeGetCurrentIrql() )
  {
    if ( byte_14006ECE5
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
    byte_14006ECE5 = 1;
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
    if ( !USBDHandle )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "USBDHandle cannot be NULL\n");
      return -1073741811;
    }
    PoolWithTag = (USBD_HANDLE)ExAllocatePoolWithTag(v8, 0xE8u, 0x68334855u);
    v10 = PoolWithTag;
    if ( !PoolWithTag )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Allocation Failed\n");
      v7 = -1073741670;
      goto LABEL_56;
    }
    memset(PoolWithTag, 0, 0xE8u);
    USBDInternal_QueryUsbVerifierSettings((__int64)DeviceObject, (__int64)(v10 + 2));
    *(_DWORD *)v10 = 1145197397;
    *((_WORD *)v10 + 5) = 1539;
    *((_DWORD *)v10 + 54) = 1539;
    *((_WORD *)v10 + 4) = 200;
    *((_DWORD *)v10 + 10) = 1538;
    *((_QWORD *)v10 + 7) = DeviceObject;
    *((_DWORD *)v10 + 16) = 1748191317;
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
        goto LABEL_32;
      }
    }
    else
    {
      *((_DWORD *)v10 + 54) = *((unsigned __int16 *)v10 + 5);
    }
    v12 = 1;
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
      ExFreePoolWithTag(v10, 0x68334855u);
      goto LABEL_56;
    }
    *USBDHandle = v10;
    return v7;
  }
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 0, "Irql Too High\n");
  v7 = -1073741496;
LABEL_19:
  if ( USBDHandle )
LABEL_56:
    *USBDHandle = 0;
  return v7;
}

```

## disassembly

```asm
0x1400430c0  mov     [rsp-8+arg_10], rbx
0x1400430c5  push    rbp
0x1400430c6  push    rsi
0x1400430c7  push    rdi
0x1400430c8  push    r12
0x1400430ca  push    r13
0x1400430cc  push    r14
0x1400430ce  push    r15
0x1400430d0  lea     rbp, [rsp-0B0h]
0x1400430d8  sub     rsp, 1B0h
0x1400430df  mov     rax, cs:__security_cookie
0x1400430e6  xor     rax, rsp
0x1400430e9  mov     [rbp+0E0h+var_40], rax
0x1400430f0  mov     r14, [rbp+0E0h+USBDHandle]
0x1400430f7  mov     rsi, rdx
0x1400430fa  mov     r12, rcx
0x1400430fd  call    cs:__imp_KeGetCurrentIrql
0x140043104  nop     dword ptr [rax+rax+00h]
0x140043109  xor     r13d, r13d
0x14004310c  test    al, al
0x14004310e  jz      short loc_14004313B
0x140043110  cmp     cs:g_EnableDbgPrints, r13b
0x140043117  jz      short loc_140043131
0x140043119  xor     edx, edx; Level
0x14004311b  lea     r8, aIrqlTooHigh; "Irql Too High\n"
0x140043122  lea     ecx, [rdx+4Dh]; ComponentId
0x140043125  call    cs:__imp_DbgPrintEx
0x14004312c  nop     dword ptr [rax+rax+00h]
0x140043131  mov     ebx, 0C0000148h
0x140043136  jmp     loc_1400431E5
0x14004313b  cmp     cs:byte_14006ECE5, r13b
0x140043142  jnz     short loc_140043192
0x140043144  xor     edx, edx; Val
0x140043146  mov     cs:PoolType, r13d
0x14004314d  mov     r8d, 118h; Size
0x140043153  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x140043157  call    memset
0x14004315c  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x140043160  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140043167  call    cs:__imp_RtlGetVersion
0x14004316e  nop     dword ptr [rax+rax+00h]
0x140043173  test    eax, eax
0x140043175  js      short loc_140043192
0x140043177  cmp     [rbp+0E0h+VersionInformation.dwMajorVersion], 6
0x14004317b  ja      short loc_140043185
0x14004317d  jnz     short loc_140043192
0x14004317f  cmp     [rbp+0E0h+VersionInformation.dwMinorVersion], 2
0x140043183  jb      short loc_140043192
0x140043185  mov     ecx, 200h
0x14004318a  mov     cs:PoolType, ecx
0x140043190  jmp     short loc_140043198
0x140043192  mov     ecx, cs:PoolType; PoolType
0x140043198  mov     ebx, 1
0x14004319d  mov     cs:byte_14006ECE5, bl
0x1400431a3  test    r12, r12
0x1400431a6  jnz     short loc_1400431BA
0x1400431a8  cmp     cs:g_EnableDbgPrints, r13b
0x1400431af  jz      short loc_1400431E0
0x1400431b1  lea     r8, aDeviceobjectCa; "DeviceObject cannot be NULL\n"
0x1400431b8  jmp     short loc_1400431CF
0x1400431ba  test    rsi, rsi
0x1400431bd  jnz     short loc_1400431F3
0x1400431bf  cmp     cs:g_EnableDbgPrints, r13b
0x1400431c6  jz      short loc_1400431E0
0x1400431c8  lea     r8, aTargetdeviceob; "TargetDeviceObject cannot be NULL\n"
0x1400431cf  xor     edx, edx; Level
0x1400431d1  lea     ecx, [rdx+4Dh]; ComponentId
0x1400431d4  call    cs:__imp_DbgPrintEx
0x1400431db  nop     dword ptr [rax+rax+00h]
0x1400431e0  mov     ebx, 0C000000Dh
0x1400431e5  test    r14, r14
0x1400431e8  jz      loc_14004339F
0x1400431ee  jmp     loc_1400434D1
0x1400431f3  test    r14, r14
0x1400431f6  jnz     short loc_140043223
0x1400431f8  cmp     cs:g_EnableDbgPrints, r13b
0x1400431ff  jz      short loc_140043219
0x140043201  xor     edx, edx; Level
0x140043203  lea     r8, aUsbdhandleCann; "USBDHandle cannot be NULL\n"
0x14004320a  lea     ecx, [rdx+4Dh]; ComponentId
0x14004320d  call    cs:__imp_DbgPrintEx
0x140043214  nop     dword ptr [rax+rax+00h]
0x140043219  mov     ebx, 0C000000Dh
0x14004321e  jmp     loc_14004339F
0x140043223  mov     r15d, 0E8h
0x140043229  mov     r8d, 68334855h; Tag
0x14004322f  mov     edx, r15d; NumberOfBytes
0x140043232  call    cs:__imp_ExAllocatePoolWithTag
0x140043239  nop     dword ptr [rax+rax+00h]
0x14004323e  mov     rdi, rax
0x140043241  test    rax, rax
0x140043244  jnz     short loc_140043271
0x140043246  cmp     cs:g_EnableDbgPrints, r13b
0x14004324d  jz      short loc_140043267
0x14004324f  lea     r8, aAllocationFail; "Allocation Failed\n"
0x140043256  xor     edx, edx; Level
0x140043258  lea     ecx, [rax+4Dh]; ComponentId
0x14004325b  call    cs:__imp_DbgPrintEx
0x140043262  nop     dword ptr [rax+rax+00h]
0x140043267  mov     ebx, 0C000009Ah
0x14004326c  jmp     loc_1400434D1
0x140043271  mov     r8, r15; Size
0x140043274  xor     edx, edx; Val
0x140043276  mov     rcx, rdi; void *
0x140043279  call    memset
0x14004327e  lea     r15, [rdi+8]
0x140043282  mov     rcx, r12
0x140043285  mov     rdx, r15
0x140043288  call    USBDInternal_QueryUsbVerifierSettings
0x14004328d  mov     eax, 603h
0x140043292  mov     dword ptr [rdi], 44425355h
0x140043298  mov     r9, r15
0x14004329b  mov     [rdi+0Ah], ax
0x14004329f  lea     r8, GUID_USBD_INTERFACE
0x1400432a6  mov     [rdi+0D8h], eax
0x1400432ac  mov     rdx, rsi; PDEVICE_OBJECT
0x1400432af  mov     word ptr [r15], 0C8h
0x1400432b5  mov     rcx, r12; DeviceObject
0x1400432b8  mov     dword ptr [rdi+28h], 602h
0x1400432bf  mov     [rdi+38h], r12
0x1400432c3  mov     dword ptr [rdi+40h], 68334855h
0x1400432ca  mov     [rdi+48h], rdi
0x1400432ce  mov     [rdi+0D0h], rsi
0x1400432d5  mov     [rdi+0DCh], ebx
0x1400432db  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x1400432e0  mov     ebx, eax
0x1400432e2  test    eax, eax
0x1400432e4  js      loc_1400433CC
0x1400432ea  movzx   eax, word ptr [rdi+0Ah]
0x1400432ee  mov     [rdi+0D8h], eax
0x1400432f4  mov     r15b, 1
0x1400432f7  cmp     cs:g_EnableDbgPrints, r13b
0x1400432fe  jz      short loc_14004331E
0x140043300  mov     edx, 3; Level
0x140043305  lea     r8, aUsbdCreatehand; "USBD_CreateHandle Successful: usbdHandl"...
0x14004330c  mov     r9, rdi
0x14004330f  lea     ecx, [rdx+4Ah]; ComponentId
0x140043312  call    cs:__imp_DbgPrintEx
0x140043319  nop     dword ptr [rax+rax+00h]
0x14004331e  cmp     dword ptr [rdi+0D8h], 600h
0x140043328  jnz     loc_14004349E
0x14004332e  xor     edx, edx; Val
0x140043330  lea     rcx, [rsp+1E0h+var_1B0]; void *
0x140043335  lea     r8d, [rdx+48h]; Size
0x140043339  call    memset
0x14004333e  lea     r9, [rsp+1E0h+var_1B0]
0x140043343  mov     [rsp+1E0h+var_1B0], 10048h
0x14004334b  lea     r8, USB_BUS_INTERFACE_USBDI_GUID
0x140043352  mov     rdx, rsi; PDEVICE_OBJECT
0x140043355  mov     rcx, r12; DeviceObject
0x140043358  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14004335d  mov     ebx, eax
0x14004335f  test    eax, eax
0x140043361  jns     loc_14004346B
0x140043367  cmp     cs:g_EnableDbgPrints, r13b
0x14004336e  jz      short loc_14004338F
0x140043370  xor     edx, edx; Level
0x140043372  mov     [rsp+1E0h+var_1C0], eax
0x140043376  mov     r9, rsi
0x140043379  lea     r8, aCoreStackTarge_0; "Core stack (TargetDevieObject 0x%p) fai"...
0x140043380  lea     ecx, [rdx+4Dh]; ComponentId
0x140043383  call    cs:__imp_DbgPrintEx
0x14004338a  nop     dword ptr [rax+rax+00h]
0x14004338f  mov     dword ptr [rdi+0D8h], 0FFFFFFFFh
0x140043399  mov     ebx, r13d
0x14004339c  mov     [r14], rdi
0x14004339f  mov     eax, ebx
0x1400433a1  mov     rcx, [rbp+0E0h+var_40]
0x1400433a8  xor     rcx, rsp; StackCookie
0x1400433ab  call    __security_check_cookie
0x1400433b0  mov     rbx, [rsp+1E0h+arg_10]
0x1400433b8  add     rsp, 1B0h
0x1400433bf  pop     r15
0x1400433c1  pop     r14
0x1400433c3  pop     r13
0x1400433c5  pop     r12
0x1400433c7  pop     rdi
0x1400433c8  pop     rsi
0x1400433c9  pop     rbp
0x1400433ca  retn
0x1400433cc  cmp     cs:g_EnableDbgPrints, r13b
0x1400433d3  jz      short loc_1400433F7
0x1400433d5  mov     edx, 3; Level
0x1400433da  mov     [rsp+1E0h+var_1C0], eax
0x1400433de  mov     r9, rsi
0x1400433e1  lea     r8, aCoreStackTarge_1; "Core stack (TargetDevieObject 0x%p) fai"...
0x1400433e8  lea     ecx, [rdx+4Ah]; ComponentId
0x1400433eb  call    cs:__imp_DbgPrintEx
0x1400433f2  nop     dword ptr [rax+rax+00h]
0x1400433f7  mov     eax, 602h
0x1400433fc  mov     word ptr [r15], 98h
0x140043402  mov     r9, r15
0x140043405  mov     [rdi+0Ah], ax
0x140043409  lea     r8, GUID_USBD_INTERFACE
0x140043410  mov     [rdi+0D8h], eax
0x140043416  mov     rdx, rsi; PDEVICE_OBJECT
0x140043419  mov     rcx, r12; DeviceObject
0x14004341c  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x140043421  mov     ebx, eax
0x140043423  test    eax, eax
0x140043425  jns     loc_1400432F4
0x14004342b  cmp     cs:g_EnableDbgPrints, r13b
0x140043432  mov     r15b, r13b
0x140043435  mov     dword ptr [rdi+0D8h], 600h
0x14004343f  jz      short loc_140043463
0x140043441  mov     edx, 3; Level
0x140043446  mov     [rsp+1E0h+var_1C0], eax
0x14004344a  mov     r9, rsi
0x14004344d  lea     r8, aCoreStackTarge; "Core stack (TargetDevieObject 0x%p) fai"...
0x140043454  lea     ecx, [rdx+4Ah]; ComponentId
0x140043457  call    cs:__imp_DbgPrintEx
0x14004345e  nop     dword ptr [rax+rax+00h]
0x140043463  mov     ebx, r13d
0x140043466  jmp     loc_1400432F7
0x14004346b  mov     rax, [rsp+1E0h+var_170]
0x140043470  test    rax, rax
0x140043473  jz      short loc_140043481
0x140043475  mov     rcx, [rsp+1E0h+var_1A8]
0x14004347a  call    _guard_dispatch_icall
0x14004347f  jmp     short loc_140043484
0x140043481  mov     al, r13b
0x140043484  mov     [rdi+0E0h], al
0x14004348a  mov     rcx, [rsp+1E0h+var_1A8]
0x14004348f  mov     rax, [rsp+1E0h+var_198]
0x140043494  call    _guard_dispatch_icall
0x140043499  jmp     loc_14004339C
0x14004349e  test    ebx, ebx
0x1400434a0  jns     loc_14004339C
0x1400434a6  test    r15b, r15b
0x1400434a9  jz      short loc_1400434BD
0x1400434ab  mov     rax, [rdi+70h]
0x1400434af  test    rax, rax
0x1400434b2  jz      short loc_1400434BD
0x1400434b4  mov     rcx, [rdi+30h]
0x1400434b8  call    _guard_dispatch_icall
0x1400434bd  mov     edx, 68334855h; Tag
0x1400434c2  mov     rcx, rdi; P
0x1400434c5  call    cs:__imp_ExFreePoolWithTag
0x1400434cc  nop     dword ptr [rax+rax+00h]
0x1400434d1  mov     [r14], r13
0x1400434d4  jmp     loc_14004339F
```
