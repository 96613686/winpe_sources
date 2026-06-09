# DriverEntry

- ea: `0x140024b80`
- end: `0x14002512a`
- name: `DriverEntry`
- size: `1450`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, registry_config, loader_planting, installer_update`

## callers

- `0x140024010`

## callees

- `0x140001520`
- `0x1400020c0`
- `0x1400038c8`
- `0x140005830`
- `0x14000a2d0`
- `0x1400107d0`
- `0x140010da8`
- `0x140013618`
- `0x140013b78`
- `0x140015b40`
- `0x140020640`
- `0x1400208dc`
- `0x140020970`
- `0x140020de8`
- `0x140024078`
- `0x140024514`
- `0x140024b80`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140024d75`
- `ntoskrnl!KeInitializeEvent` at `0x140024d94`
- `ntoskrnl!KeInitializeEvent` at `0x140024ede`
- `ntoskrnl!KeInitializeEvent` at `0x140024d75`
- `ntoskrnl!KeInitializeEvent` at `0x140024d94`
- `ntoskrnl!KeInitializeEvent` at `0x140024ede`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f6c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f6c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140024d28`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140024d28`
- `ntoskrnl!PsCreateSystemThread` at `0x140024f19`
- `ntoskrnl!PsCreateSystemThread` at `0x140024f19`
- `ntoskrnl!EtwRegister` at `0x140024bfa`
- `ntoskrnl!EtwRegister` at `0x140024bfa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024c06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024c06`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140024e77`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140024e77`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002510e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002510e`
- `NETIO!WskRegister` at `0x140025014`
- `NETIO!WskRegister` at `0x140025014`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int Length; // esi
  ULONG v3; // esi
  PUNICODE_STRING v6; // r8
  ULONG v7; // r9d
  NTSTATUS v8; // eax
  NTSTATUS appended; // ebx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  struct _UNICODE_STRING *v13; // rbx
  __int64 v14; // rax
  NTSTATUS v15; // eax
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  char *v18; // rdx
  _QWORD *v19; // rdx
  ULONG ClientId; // [rsp+20h] [rbp-78h]
  BOOLEAN StartRoutine; // [rsp+28h] [rbp-70h]
  const UNICODE_STRING *StartContext; // [rsp+30h] [rbp-68h]
  const GUID *v24; // [rsp+38h] [rbp-60h]
  _WSK_CLIENT_NPI WskClientNpi; // [rsp+50h] [rbp-48h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+A8h] [rbp+10h] BYREF

  Length = RegistryPath->Length;
  DeviceObject = 0;
  v3 = Length + 264;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_OncRpcXdrGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  EtwRegister(&NFS_ONCRPC_EVENT_PROVIDER, 0, 0, &RegHandle);
  KeEnterCriticalRegion();
  v8 = WdmlibIoCreateDeviceSecure(DriverObject, v3, v6, v7, ClientId, StartRoutine, StartContext, v24, &DeviceObject);
  appended = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_61;
    v11 = 10;
    v12 = (unsigned int)v8;
    goto LABEL_60;
  }
  DeviceExtension = DeviceObject->DeviceExtension;
  v13 = (struct _UNICODE_STRING *)DeviceExtension;
  memset(DeviceExtension, 0, v3);
  *(_QWORD *)&v13[1].Length = 0;
  *(_DWORD *)&v13->Length = 1482048594;
  *(_DWORD *)(&v13->MaximumLength + 1) = 0;
  LOWORD(v13->Buffer) = 0;
  v13[1].Buffer = (wchar_t *)DeviceObject;
  v13[2].Length = RegistryPath->Length;
  v13[2].MaximumLength = RegistryPath->Length;
  v13[2].Buffer = &v13[15].Length;
  v13[3].Length = 0;
  v14 = (unsigned __int16)(RegistryPath->Length + 24);
  v13[3].Buffer = &v13[15].Length;
  v13[3].MaximumLength = v14;
  v15 = RtlUnicodeStringCopy(v13 + 3, RegistryPath);
  if ( v15 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids, (unsigned int)v15);
  }
  appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)DeviceExtension + 3, &RegistryPathSubdirParameters);
  if ( appended < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids,
      (unsigned int)appended);
  }
  KeInitializeEvent((PRKEVENT)((char *)DeviceExtension + 160), NotificationEvent, 0);
  KeInitializeEvent((PRKEVENT)((char *)DeviceExtension + 184), NotificationEvent, 0);
  if ( appended < 0 )
    goto LABEL_61;
  appended = NfsResMgrStartup((PCUNICODE_STRING)DeviceExtension + 3);
  if ( appended < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_61;
    v17 = 13;
    goto LABEL_22;
  }
  appended = NfsCfgMgrpReadRegistryParameters((char *)NfsResMgrpRoot + 168);
  if ( appended < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_61;
    v17 = 14;
LABEL_22:
    WPP_SF_Dd(
      v16->AttachedDevice,
      v17,
      WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids,
      (unsigned int)appended,
      appended);
LABEL_61:
    RpcXdrDriverUnload(DriverObject);
    goto LABEL_62;
  }
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)RpcXdrDriverUnload;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&RpcXdrDispatchCreate;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&RpcXdrDispatchCreate;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&RpcXdrDispatchDeviceControl;
  appended = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
  if ( appended < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids,
      (unsigned int)appended);
  }
  v18 = (char *)DeviceExtension;
  *((_DWORD *)DeviceExtension + 17) = *((_DWORD *)DeviceExtension + 17) & 0xFFFFFFFE | (appended >= 0);
  if ( appended < 0 )
    goto LABEL_61;
  KeInitializeEvent((PRKEVENT)(v18 + 136), NotificationEvent, 0);
  appended = PsCreateSystemThread(
               (PHANDLE)DeviceExtension + 16,
               0x1FFFFFu,
               0,
               0,
               0,
               OncRpcGenericWorkerThread,
               DeviceExtension);
  if ( appended < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_61;
    v11 = 16;
    goto LABEL_59;
  }
  appended = KeWaitForSingleObject((char *)DeviceExtension + 136, Executive, 0, 0, 0);
  if ( appended < 0 )
    goto LABEL_61;
  appended = OncRpcBufMgrStartup();
  if ( appended < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_61;
    v11 = 17;
    goto LABEL_59;
  }
  appended = OncRpcMsgStartup();
  if ( appended < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_61;
    v11 = 18;
    goto LABEL_59;
  }
  appended = OncRpcSeStartup();
  if ( appended < 0 )
    goto LABEL_61;
  WskClientNpi.ClientContext = 0;
  WskClientNpi.Dispatch = (const WSK_CLIENT_DISPATCH *)WskClientDispatch;
  appended = WskRegister(&WskClientNpi, (PWSK_REGISTRATION)DeviceExtension + 3);
  if ( appended < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids,
      (unsigned int)appended);
  }
  v19 = DeviceExtension;
  *((_DWORD *)DeviceExtension + 17) = *((_DWORD *)DeviceExtension + 17) & 0xFFFFFFFB
                                    | ~((unsigned int)appended >> 29) & 4;
  if ( appended < 0 )
    goto LABEL_61;
  appended = OncRpcConnMgrStartup(v19 + 28);
  if ( appended < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_61;
    v11 = 20;
    goto LABEL_59;
  }
  appended = OncRpcWiMgrStartup((char *)DeviceExtension + 232);
  if ( appended < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_61;
    v11 = 21;
    goto LABEL_59;
  }
  appended = OncRpcDrcStartup();
  if ( appended < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_61;
    v11 = 22;
LABEL_59:
    v12 = (unsigned int)appended;
LABEL_60:
    WPP_SF_d(v10->AttachedDevice, v11, WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids, v12);
    goto LABEL_61;
  }
LABEL_62:
  KeLeaveCriticalRegion();
  return appended;
}

```

## disassembly

```asm
0x140024b80  mov     rax, rsp
0x140024b83  push    rbx
0x140024b84  push    rbp
0x140024b85  push    rsi
0x140024b86  push    rdi
0x140024b87  push    r14
0x140024b89  push    r15
0x140024b8b  sub     rsp, 68h
0x140024b8f  movzx   esi, word ptr [rdx]
0x140024b92  xor     r14d, r14d
0x140024b95  mov     [rax+10h], r14
0x140024b99  add     esi, 108h
0x140024b9f  lea     rax, WPP_ThisDir_CTLGUID_OncRpcXdrGuid
0x140024ba6  mov     qword ptr cs:WPP_MAIN_CB.Type, r14
0x140024bad  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140024bb4  mov     rdi, rdx
0x140024bb7  mov     rbp, rcx
0x140024bba  mov     cs:WPP_MAIN_CB.NextDevice, r14
0x140024bc1  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x140024bc8  mov     r15b, 1
0x140024bcb  mov     cs:WPP_MAIN_CB.Timer, 1
0x140024bd6  call    WppLoadTracingSupport
0x140024bdb  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x140024be2  call    WppInitKm
0x140024be7  lea     r9, RegHandle; RegHandle
0x140024bee  xor     r8d, r8d; CallbackContext
0x140024bf1  xor     edx, edx; EnableCallback
0x140024bf3  lea     rcx, NFS_ONCRPC_EVENT_PROVIDER; ProviderId
0x140024bfa  call    cs:__imp_EtwRegister
0x140024c01  nop     dword ptr [rax+rax+00h]
0x140024c06  call    cs:__imp_KeEnterCriticalRegion
0x140024c0d  nop     dword ptr [rax+rax+00h]
0x140024c12  lea     rax, [rsp+98h+arg_8]
0x140024c1a  mov     edx, esi; DeviceExtensionSize
0x140024c1c  mov     rcx, rbp; DriverObject
0x140024c1f  mov     [rsp+98h+DeviceObject], rax; DeviceObject
0x140024c24  call    WdmlibIoCreateDeviceSecure
0x140024c29  mov     ebx, eax
0x140024c2b  test    eax, eax
0x140024c2d  jns     short loc_140024C65
0x140024c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140024c36  lea     rdi, WPP_GLOBAL_Control
0x140024c3d  cmp     rcx, rdi
0x140024c40  jz      loc_140025106
0x140024c46  mov     edx, [rcx+2Ch]
0x140024c49  test    r15b, dl
0x140024c4c  jz      loc_140025106
0x140024c52  lea     edx, [r14+0Ah]
0x140024c56  mov     r9d, eax
0x140024c59  lea     r8, WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids
0x140024c60  jmp     loc_1400250FD
0x140024c65  mov     rax, [rsp+98h+arg_8]
0x140024c6d  xor     edx, edx; Val
0x140024c6f  mov     r8d, esi; Size
0x140024c72  mov     rbx, [rax+40h]
0x140024c76  mov     rcx, rbx; void *
0x140024c79  mov     cs:DeviceExtension, rbx
0x140024c80  call    memset
0x140024c85  mov     [rbx+10h], r14
0x140024c89  lea     rdx, [rbx+0F0h]
0x140024c90  mov     dword ptr [rbx], 58564452h
0x140024c96  lea     rcx, [rbx+30h]; DestinationString
0x140024c9a  mov     [rbx+4], r14d
0x140024c9e  mov     [rbx+8], r14w
0x140024ca3  mov     rax, [rsp+98h+arg_8]
0x140024cab  mov     [rbx+18h], rax
0x140024caf  movzx   eax, word ptr [rdi]
0x140024cb2  mov     [rbx+20h], ax
0x140024cb6  movzx   eax, word ptr [rdi]
0x140024cb9  mov     [rbx+22h], ax
0x140024cbd  mov     [rbx+28h], rdx
0x140024cc1  mov     [rcx], r14w
0x140024cc5  movzx   eax, word ptr [rdi]
0x140024cc8  add     ax, 18h
0x140024ccc  mov     [rbx+38h], rdx
0x140024cd0  mov     rdx, rdi; SourceString
0x140024cd3  mov     [rbx+32h], ax
0x140024cd7  call    RtlUnicodeStringCopy
0x140024cdc  lea     rsi, WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids
0x140024ce3  lea     rdi, WPP_GLOBAL_Control
0x140024cea  test    eax, eax
0x140024cec  jns     short loc_140024D16
0x140024cee  mov     rcx, cs:WPP_GLOBAL_Control
0x140024cf5  cmp     rcx, rdi
0x140024cf8  jz      short loc_140024D16
0x140024cfa  mov     edx, [rcx+2Ch]
0x140024cfd  test    r15b, dl
0x140024d00  jz      short loc_140024D16
0x140024d02  mov     rcx, [rcx+18h]
0x140024d06  mov     edx, 0Bh
0x140024d0b  mov     r9d, eax
0x140024d0e  mov     r8, rsi
0x140024d11  call    WPP_SF_d
0x140024d16  mov     rcx, cs:DeviceExtension
0x140024d1d  lea     rdx, RegistryPathSubdirParameters; Source
0x140024d24  add     rcx, 30h ; '0'; Destination
0x140024d28  call    cs:__imp_RtlAppendUnicodeStringToString
0x140024d2f  nop     dword ptr [rax+rax+00h]
0x140024d34  mov     ebx, eax
0x140024d36  test    eax, eax
0x140024d38  jns     short loc_140024D62
0x140024d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d41  cmp     rcx, rdi
0x140024d44  jz      short loc_140024D62
0x140024d46  mov     eax, [rcx+2Ch]
0x140024d49  test    r15b, al
0x140024d4c  jz      short loc_140024D62
0x140024d4e  mov     rcx, [rcx+18h]
0x140024d52  mov     edx, 0Ch
0x140024d57  mov     r9d, ebx
0x140024d5a  mov     r8, rsi
0x140024d5d  call    WPP_SF_d
0x140024d62  mov     rcx, cs:DeviceExtension
0x140024d69  xor     r8d, r8d; State
0x140024d6c  add     rcx, 0A0h; Event
0x140024d73  xor     edx, edx; Type
0x140024d75  call    cs:__imp_KeInitializeEvent
0x140024d7c  nop     dword ptr [rax+rax+00h]
0x140024d81  mov     rcx, cs:DeviceExtension
0x140024d88  xor     r8d, r8d; State
0x140024d8b  add     rcx, 0B8h; Event
0x140024d92  xor     edx, edx; Type
0x140024d94  call    cs:__imp_KeInitializeEvent
0x140024d9b  nop     dword ptr [rax+rax+00h]
0x140024da0  test    ebx, ebx
0x140024da2  js      loc_140025106
0x140024da8  mov     rcx, cs:DeviceExtension
0x140024daf  lea     rdx, [rcx+68h]
0x140024db3  add     rcx, 30h ; '0'; SourceString
0x140024db7  call    NfsResMgrStartup
0x140024dbc  mov     ebx, eax
0x140024dbe  test    eax, eax
0x140024dc0  jns     short loc_140024DE5
0x140024dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140024dc9  cmp     rcx, rdi
0x140024dcc  jz      loc_140025106
0x140024dd2  mov     eax, [rcx+2Ch]
0x140024dd5  test    r15b, al
0x140024dd8  jz      loc_140025106
0x140024dde  mov     edx, 0Dh
0x140024de3  jmp     short loc_140024E1F
0x140024de5  mov     rcx, cs:NfsResMgrpRoot
0x140024dec  add     rcx, 0A8h
0x140024df3  call    NfsCfgMgrpReadRegistryParameters
0x140024df8  mov     ebx, eax
0x140024dfa  test    eax, eax
0x140024dfc  jns     short loc_140024E37
0x140024dfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e05  cmp     rcx, rdi
0x140024e08  jz      loc_140025106
0x140024e0e  mov     eax, [rcx+2Ch]
0x140024e11  test    r15b, al
0x140024e14  jz      loc_140025106
0x140024e1a  mov     edx, 0Eh
0x140024e1f  mov     rcx, [rcx+18h]
0x140024e23  mov     r9d, ebx
0x140024e26  mov     r8, rsi
0x140024e29  mov     dword ptr [rsp+98h+ClientId], ebx
0x140024e2d  call    WPP_SF_Dd
0x140024e32  jmp     loc_140025106
0x140024e37  lea     rax, RpcXdrDriverUnload
0x140024e3e  mov     [rbp+68h], rax
0x140024e42  lea     rdx, DeviceName; DeviceName
0x140024e49  lea     rax, RpcXdrDispatchCreate
0x140024e50  mov     [rbp+70h], rax
0x140024e54  lea     rcx, SymbolicLinkName; SymbolicLinkName
0x140024e5b  lea     rax, RpcXdrDispatchCreate
0x140024e62  mov     [rbp+80h], rax
0x140024e69  lea     rax, RpcXdrDispatchDeviceControl
0x140024e70  mov     [rbp+0E0h], rax
0x140024e77  call    cs:__imp_IoCreateSymbolicLink
0x140024e7e  nop     dword ptr [rax+rax+00h]
0x140024e83  mov     ebx, eax
0x140024e85  test    eax, eax
0x140024e87  jns     short loc_140024EB1
0x140024e89  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e90  cmp     rcx, rdi
0x140024e93  jz      short loc_140024EB1
0x140024e95  mov     eax, [rcx+2Ch]
0x140024e98  test    r15b, al
0x140024e9b  jz      short loc_140024EB1
0x140024e9d  mov     rcx, [rcx+18h]
0x140024ea1  mov     edx, 0Fh
0x140024ea6  mov     r9d, ebx
0x140024ea9  mov     r8, rsi
0x140024eac  call    WPP_SF_d
0x140024eb1  mov     rdx, cs:DeviceExtension
0x140024eb8  mov     ecx, ebx
0x140024eba  not     ecx
0x140024ebc  shr     ecx, 1Fh
0x140024ebf  mov     eax, [rdx+44h]
0x140024ec2  and     eax, 0FFFFFFFEh
0x140024ec5  or      ecx, eax
0x140024ec7  mov     [rdx+44h], ecx
0x140024eca  test    ebx, ebx
0x140024ecc  js      loc_140025106
0x140024ed2  lea     rcx, [rdx+88h]; Event
0x140024ed9  xor     r8d, r8d; State
0x140024edc  xor     edx, edx; Type
0x140024ede  call    cs:__imp_KeInitializeEvent
0x140024ee5  nop     dword ptr [rax+rax+00h]
0x140024eea  mov     rax, cs:DeviceExtension
0x140024ef1  xor     r9d, r9d; ProcessHandle
0x140024ef4  mov     [rsp+98h+StartContext], rax; StartContext
0x140024ef9  xor     r8d, r8d; ObjectAttributes
0x140024efc  mov     edx, 1FFFFFh; DesiredAccess
0x140024f01  lea     rcx, [rax+80h]; ThreadHandle
0x140024f08  lea     rax, OncRpcGenericWorkerThread
0x140024f0f  mov     [rsp+98h+StartRoutine], rax; StartRoutine
0x140024f14  mov     [rsp+98h+ClientId], r14; ClientId
0x140024f19  call    cs:__imp_PsCreateSystemThread
0x140024f20  nop     dword ptr [rax+rax+00h]
0x140024f25  mov     ebx, eax
0x140024f27  test    eax, eax
0x140024f29  jns     short loc_140024F51
0x140024f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024f32  cmp     rcx, rdi
0x140024f35  jz      loc_140025106
0x140024f3b  mov     eax, [rcx+2Ch]
0x140024f3e  test    r15b, al
0x140024f41  jz      loc_140025106
0x140024f47  mov     edx, 10h
0x140024f4c  jmp     loc_1400250F7
0x140024f51  mov     rcx, cs:DeviceExtension
0x140024f58  xor     r9d, r9d; Alertable
0x140024f5b  add     rcx, 88h; Object
0x140024f62  mov     [rsp+98h+ClientId], r14; Timeout
0x140024f67  xor     r8d, r8d; WaitMode
0x140024f6a  xor     edx, edx; WaitReason
0x140024f6c  call    cs:__imp_KeWaitForSingleObject
0x140024f73  nop     dword ptr [rax+rax+00h]
0x140024f78  mov     ebx, eax
0x140024f7a  test    eax, eax
0x140024f7c  js      loc_140025106
0x140024f82  call    OncRpcBufMgrStartup
0x140024f87  mov     ebx, eax
0x140024f89  test    eax, eax
0x140024f8b  jns     short loc_140024FB3
0x140024f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140024f94  cmp     rcx, rdi
0x140024f97  jz      loc_140025106
0x140024f9d  mov     eax, [rcx+2Ch]
0x140024fa0  test    r15b, al
0x140024fa3  jz      loc_140025106
0x140024fa9  mov     edx, 11h
0x140024fae  jmp     loc_1400250F7
0x140024fb3  call    OncRpcMsgStartup
0x140024fb8  mov     ebx, eax
0x140024fba  test    eax, eax
0x140024fbc  jns     short loc_140024FE4
0x140024fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140024fc5  cmp     rcx, rdi
0x140024fc8  jz      loc_140025106
0x140024fce  mov     eax, [rcx+2Ch]
0x140024fd1  test    r15b, al
0x140024fd4  jz      loc_140025106
0x140024fda  mov     edx, 12h
0x140024fdf  jmp     loc_1400250F7
0x140024fe4  call    OncRpcSeStartup
0x140024fe9  mov     ebx, eax
0x140024feb  test    eax, eax
0x140024fed  js      loc_140025106
0x140024ff3  mov     rdx, cs:DeviceExtension
0x140024ffa  lea     rax, WskClientDispatch
0x140025001  add     rdx, 48h ; 'H'; WskRegistration
0x140025005  mov     [rsp+98h+WskClientNpi.ClientContext], r14
0x14002500a  lea     rcx, [rsp+98h+WskClientNpi]; WskClientNpi
0x14002500f  mov     [rsp+98h+WskClientNpi.Dispatch], rax
0x140025014  call    cs:__imp_WskRegister
0x14002501b  nop     dword ptr [rax+rax+00h]
0x140025020  mov     ebx, eax
0x140025022  test    eax, eax
0x140025024  jns     short loc_14002504E
0x140025026  mov     rcx, cs:WPP_GLOBAL_Control
0x14002502d  cmp     rcx, rdi
0x140025030  jz      short loc_14002504E
0x140025032  mov     eax, [rcx+2Ch]
0x140025035  test    r15b, al
0x140025038  jz      short loc_14002504E
0x14002503a  mov     rcx, [rcx+18h]
0x14002503e  mov     edx, 13h
0x140025043  mov     r9d, ebx
0x140025046  mov     r8, rsi
0x140025049  call    WPP_SF_d
0x14002504e  mov     rdx, cs:DeviceExtension
0x140025055  mov     ecx, ebx
0x140025057  shr     ecx, 1Dh
0x14002505a  not     ecx
0x14002505c  and     ecx, 4
0x14002505f  mov     eax, [rdx+44h]
0x140025062  and     eax, 0FFFFFFFBh
0x140025065  or      ecx, eax
0x140025067  mov     [rdx+44h], ecx
0x14002506a  test    ebx, ebx
0x14002506c  js      loc_140025106
0x140025072  lea     rcx, [rdx+0E0h]
0x140025079  call    OncRpcConnMgrStartup
0x14002507e  mov     ebx, eax
0x140025080  test    eax, eax
0x140025082  jns     short loc_14002509F
  ... truncated ...
```
