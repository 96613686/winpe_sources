# DriverEntry

- ea: `0x14001a078`
- end: `0x14001a5c9`
- name: `DriverEntry`
- size: `1361`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x14001a010`

## callees

- `0x1400024d0`
- `0x140002b6c`
- `0x140003960`
- `0x1400045a4`
- `0x1400050b0`
- `0x1400171b4`
- `0x14001727c`
- `0x14001785c`
- `0x140017a4c`
- `0x140017af0`
- `0x140018024`
- `0x14001a078`
- `0x14001a5d0`
- `0x14001a85c`
- `0x14001aa04`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001a40f`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14001a40f`
- `ntoskrnl!ZwClose` at `0x14001a22d`
- `ntoskrnl!ZwClose` at `0x14001a22d`
- `ntoskrnl!KeReleaseMutex` at `0x14001a3f4`
- `ntoskrnl!KeReleaseMutex` at `0x14001a448`
- `ntoskrnl!KeReleaseMutex` at `0x14001a4fb`
- `ntoskrnl!KeReleaseMutex` at `0x14001a3f4`
- `ntoskrnl!KeReleaseMutex` at `0x14001a448`
- `ntoskrnl!KeReleaseMutex` at `0x14001a4fb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001a134`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001a134`
- `ntoskrnl!IoDeleteDevice` at `0x14001a52b`
- `ntoskrnl!IoDeleteDevice` at `0x14001a543`
- `ntoskrnl!IoDeleteDevice` at `0x14001a52b`
- `ntoskrnl!IoDeleteDevice` at `0x14001a543`
- `ntoskrnl!KeInitializeMutex` at `0x14001a0de`
- `ntoskrnl!KeInitializeMutex` at `0x14001a0de`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001a15f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001a15f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a3bb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a4b5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a3bb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a4b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a17f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a17f`
- `ntoskrnl!ExAllocatePool2` at `0x14001a103`
- `ntoskrnl!ExAllocatePool2` at `0x14001a103`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a14b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a260`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a277`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a14b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a260`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a277`
- `NETIO!NetioUnInitializeNetBufferListLibrary` at `0x14001a4de`
- `NETIO!NetioUnInitializeNetBufferListLibrary` at `0x14001a4de`
- `NETIO!NetioRegisterProcessorAddCallback` at `0x14001a3d8`
- `NETIO!NetioRegisterProcessorAddCallback` at `0x14001a3d8`
- `NETIO!NetioInitializeNetBufferListLibrary` at `0x14001a421`
- `NETIO!NetioInitializeNetBufferListLibrary` at `0x14001a421`
- `NETIO!NmrRegisterClient` at `0x14001a48a`
- `NETIO!NmrRegisterClient` at `0x14001a48a`
- `NETIO!NetioUnRegisterProcessorAddCallback` at `0x14001a513`
- `NETIO!NetioUnRegisterProcessorAddCallback` at `0x14001a513`

## string_xrefs

- `0x14001a1c3`: `EnableLinkDownAtStop`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  unsigned __int16 v4; // r15
  wchar_t *Pool2; // rax
  wchar_t *v6; // r14
  int v7; // edi
  char v8; // bl
  int v9; // edi
  ULONG v10; // edx
  ULONG v11; // r9d
  ULONG v12; // edx
  ULONG v13; // r9d
  ULONG Timeout; // [rsp+20h] [rbp-79h]
  ULONG Timeouta; // [rsp+20h] [rbp-79h]
  BOOLEAN v17; // [rsp+28h] [rbp-71h]
  BOOLEAN v18; // [rsp+28h] [rbp-71h]
  HANDLE Handle; // [rsp+58h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING v22; // [rsp+80h] [rbp-19h] BYREF
  UNICODE_STRING Source; // [rsp+90h] [rbp-9h] BYREF
  GUID DeviceClassGuid; // [rsp+A0h] [rbp+7h] BYREF

  DeviceClassGuid = GUID_DEVCLASS_NETTRANS;
  Handle = 0;
  DestinationString = 0;
  Source = 0;
  wil_InitializeFeatureStaging();
  KeInitializeMutex(&Mutex, 0);
  v4 = RegistryPath->Length + 26;
  Pool2 = (wchar_t *)ExAllocatePool2(64, v4, 1936749143);
  v6 = Pool2;
  if ( !Pool2 )
  {
    v7 = -1073741670;
LABEL_47:
    wil_UninitializeFeatureStaging();
    return v7;
  }
  DestinationString.MaximumLength = v4;
  DestinationString.Buffer = Pool2;
  v8 = 0;
  RtlCopyUnicodeString(&DestinationString, RegistryPath);
  RtlInitUnicodeString(&Source, L"\\Parameters");
  RtlAppendUnicodeStringToString(&DestinationString, &Source);
  v9 = OpenRegKey(&Handle, &DestinationString);
  ExFreePoolWithTag(v6, 0);
  if ( !v9 )
  {
    if ( !(unsigned int)GetRegDWORDValue(Handle) )
      g_bDisableSpoofingProtection = 0;
    if ( !(unsigned int)GetRegDWORDValue(Handle) )
      g_bEnableLinkDownAtStop = 0;
    if ( !(unsigned int)GetRegDWORDValue(Handle) )
      g_SetInterfaceTagforRouter = 1;
    if ( !(unsigned int)GetRegDWORDValue(Handle) )
      g_SetInterfaceTagForVpnServer = 0;
    ZwClose(Handle);
  }
  dword_140009A80 = 0;
  Increment = 0;
  DeviceName = 0;
  v22 = 0;
  RtlInitUnicodeString(&DeviceName, L"\\Device\\WANARP");
  RtlInitUnicodeString(&v22, L"\\Device\\WANARPV6");
  v7 = WdmlibIoCreateDeviceSecure(
         DriverObject,
         v10,
         &DeviceName,
         v11,
         Timeout,
         v17,
         &SDDL_SYS_ALL_ADM_ALL,
         &DeviceClassGuid,
         &DeviceObject);
  if ( v7 >= 0 )
  {
    v7 = WanpSetDeviceObjectDacl(DeviceObject);
    if ( v7 >= 0 )
    {
      v7 = WdmlibIoCreateDeviceSecure(
             DriverObject,
             v12,
             &v22,
             v13,
             Timeouta,
             v18,
             &SDDL_SYS_ALL_ADM_ALL,
             &DeviceClassGuid,
             &qword_140009B98);
      if ( v7 >= 0 )
      {
        v7 = WanpSetDeviceObjectDacl(qword_140009B98);
        if ( v7 >= 0 )
        {
          v7 = WanpSetupExternalName(&DeviceName);
          if ( v7 >= 0 )
          {
            v8 = 1;
            v7 = WanpSetupExternalName(&v22);
            if ( v7 >= 0 )
            {
              DriverObject->FastIoDispatch = 0;
              DriverObject->DriverUnload = (PDRIVER_UNLOAD)WanUnload;
              memset64(DriverObject->MajorFunction, (unsigned __int64)WanDispatch, 0x1Cu);
              if ( !(unsigned __int8)WanpInitializeDriverStructures() )
              {
                v8 = 3;
                v7 = -1073741670;
LABEL_35:
                if ( DeviceObject )
                  IoDeleteDevice(DeviceObject);
                if ( qword_140009B98 )
                  IoDeleteDevice(qword_140009B98);
                if ( (v8 & 1) != 0 )
                  WanpSetupExternalName(0);
                if ( (v8 & 2) != 0 )
                  WanpSetupExternalName(0);
                if ( (v8 & 8) != 0 )
                  WanpFreeDriverStructures();
                if ( (v8 & 4) != 0 )
                  WanpReleaseResource(&g_wrBindMutex);
                goto LABEL_47;
              }
              WanpAcquireResource(&g_wrBindMutex);
              byte_140009AEC = 1;
              byte_140009C0C = 1;
              KeWaitForSingleObject(&Mutex, Executive, 0, 0, 0);
              v7 = NetioRegisterProcessorAddCallback(qword_1400098C8, WanpProcessorAddCallback, 0);
              if ( v7 < 0 )
              {
                v8 = 15;
                KeReleaseMutex(&Mutex, 0);
                goto LABEL_35;
              }
              v8 = 47;
              dword_1400098C0 = KeQueryActiveProcessorCountEx(0xFFFFu);
              v7 = NetioInitializeNetBufferListLibrary();
              if ( v7 >= 0 )
              {
                v8 = 111;
                v7 = WanNmrpRegisterProviders();
                if ( v7 >= 0 )
                {
                  KeReleaseMutex(&Mutex, 0);
                  byte_140009AEC = 0;
                  byte_140009C0C = 0;
                  WanpReleaseResource(&g_wrBindMutex);
                  v8 = 123;
                  HIDWORD(qword_140009948) = 1;
                  v7 = NmrRegisterClient(&FlNaClientNotify, 0, &NmrClientHandle);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v7 )
  {
    if ( (v8 & 0x10) != 0 )
    {
      KeWaitForSingleObject(&Mutex, Executive, 0, 0, 0);
      WanNmrpCleanupProviderState(&WanNmrV4ProviderState);
      WanNmrpCleanupProviderState(&WanNmrV6ProviderState);
    }
    if ( (v8 & 0x40) != 0 )
      NetioUnInitializeNetBufferListLibrary();
    if ( (v8 & 0x70) != 0 )
    {
      byte_1400098D8 = 1;
      KeReleaseMutex(&Mutex, 0);
    }
    if ( (v8 & 0x20) != 0 )
      NetioUnRegisterProcessorAddCallback(qword_1400098C8);
    goto LABEL_35;
  }
  return 0;
}

```

## disassembly

```asm
0x14001a078  mov     [rsp-8+arg_10], rbx
0x14001a07d  push    rbp
0x14001a07e  push    rsi
0x14001a07f  push    rdi
0x14001a080  push    r12
0x14001a082  push    r13
0x14001a084  push    r14
0x14001a086  push    r15
0x14001a088  lea     rbp, [rsp-27h]
0x14001a08d  sub     rsp, 0C0h
0x14001a094  mov     rax, cs:__security_cookie
0x14001a09b  xor     rax, rsp
0x14001a09e  mov     [rbp+57h+var_40], rax
0x14001a0a2  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_NETTRANS.Data1
0x14001a0a9  xor     r12d, r12d
0x14001a0ac  mov     rdi, rdx
0x14001a0af  xorps   xmm1, xmm1
0x14001a0b2  mov     [rbp+57h+var_A0], r12d
0x14001a0b6  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x14001a0bb  mov     [rbp+57h+Handle], r12
0x14001a0bf  mov     rsi, rcx
0x14001a0c2  xorps   xmm0, xmm0
0x14001a0c5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001a0c9  movups  xmmword ptr [rbp+57h+Source.Length], xmm1
0x14001a0cd  call    wil_InitializeFeatureStaging
0x14001a0d2  lea     r13, Mutex
0x14001a0d9  xor     edx, edx; Level
0x14001a0db  mov     rcx, r13; Mutex
0x14001a0de  call    cs:__imp_KeInitializeMutex
0x14001a0e5  nop     dword ptr [rax+rax+00h]
0x14001a0ea  movzx   eax, word ptr [rdi]
0x14001a0ed  lea     ecx, [r12+40h]
0x14001a0f2  add     ax, 1Ah
0x14001a0f6  mov     r8d, 73707257h
0x14001a0fc  movzx   r15d, ax
0x14001a100  mov     edx, r15d
0x14001a103  call    cs:__imp_ExAllocatePool2
0x14001a10a  nop     dword ptr [rax+rax+00h]
0x14001a10f  mov     r14, rax
0x14001a112  test    rax, rax
0x14001a115  jnz     short loc_14001A121
0x14001a117  mov     edi, 0C000009Ah
0x14001a11c  jmp     loc_14001A596
0x14001a121  mov     rdx, rdi; SourceString
0x14001a124  mov     [rbp+57h+DestinationString.MaximumLength], r15w
0x14001a129  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001a12d  mov     [rbp+57h+DestinationString.Buffer], r14
0x14001a131  mov     ebx, r12d
0x14001a134  call    cs:__imp_RtlCopyUnicodeString
0x14001a13b  nop     dword ptr [rax+rax+00h]
0x14001a140  lea     rdx, aParameters; "\\Parameters"
0x14001a147  lea     rcx, [rbp+57h+Source]; DestinationString
0x14001a14b  call    cs:__imp_RtlInitUnicodeString
0x14001a152  nop     dword ptr [rax+rax+00h]
0x14001a157  lea     rdx, [rbp+57h+Source]; Source
0x14001a15b  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14001a15f  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001a166  nop     dword ptr [rax+rax+00h]
0x14001a16b  lea     rdx, [rbp+57h+DestinationString]
0x14001a16f  lea     rcx, [rbp+57h+Handle]
0x14001a173  call    OpenRegKey
0x14001a178  xor     edx, edx; Tag
0x14001a17a  mov     rcx, r14; P
0x14001a17d  mov     edi, eax
0x14001a17f  call    cs:__imp_ExFreePoolWithTag
0x14001a186  nop     dword ptr [rax+rax+00h]
0x14001a18b  test    edi, edi
0x14001a18d  jnz     loc_14001A239
0x14001a193  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001a197  lea     r8, [rbp+57h+var_A0]
0x14001a19b  lea     rdx, aDisablespoofin; "DisableSpoofingProtection"
0x14001a1a2  call    GetRegDWORDValue
0x14001a1a7  test    eax, eax
0x14001a1a9  jnz     short loc_14001A1BB
0x14001a1ab  cmp     [rbp+57h+var_A0], r12d
0x14001a1af  mov     eax, r12d
0x14001a1b2  setnz   al
0x14001a1b5  mov     cs:g_bDisableSpoofingProtection, eax
0x14001a1bb  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001a1bf  lea     r8, [rbp+57h+var_A0]
0x14001a1c3  lea     rdx, aEnablelinkdown; "EnableLinkDownAtStop"
0x14001a1ca  call    GetRegDWORDValue
0x14001a1cf  test    eax, eax
0x14001a1d1  jnz     short loc_14001A1E3
0x14001a1d3  cmp     [rbp+57h+var_A0], r12d
0x14001a1d7  mov     eax, r12d
0x14001a1da  setnz   al
0x14001a1dd  mov     cs:g_bEnableLinkDownAtStop, eax
0x14001a1e3  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001a1e7  lea     r8, [rbp+57h+var_A0]
0x14001a1eb  lea     rdx, aDisablenatons2; "DisableNATOnS2SExternalInterface"
0x14001a1f2  call    GetRegDWORDValue
0x14001a1f7  test    eax, eax
0x14001a1f9  jnz     short loc_14001A206
0x14001a1fb  cmp     [rbp+57h+var_A0], r12d
0x14001a1ff  setz    cs:g_SetInterfaceTagforRouter
0x14001a206  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001a20a  lea     r8, [rbp+57h+var_A0]
0x14001a20e  lea     rdx, aEnablenatondia; "EnableNATOnDialInInterface"
0x14001a215  call    GetRegDWORDValue
0x14001a21a  test    eax, eax
0x14001a21c  jnz     short loc_14001A229
0x14001a21e  cmp     [rbp+57h+var_A0], r12d
0x14001a222  setnz   cs:g_SetInterfaceTagForVpnServer
0x14001a229  mov     rcx, [rbp+57h+Handle]; Handle
0x14001a22d  call    cs:__imp_ZwClose
0x14001a234  nop     dword ptr [rax+rax+00h]
0x14001a239  xorps   xmm0, xmm0
0x14001a23c  mov     cs:dword_140009A80, r12d
0x14001a243  xorps   xmm1, xmm1
0x14001a246  mov     cs:Increment, r12d
0x14001a24d  lea     rdx, aDeviceWanarp; "\\Device\\WANARP"
0x14001a254  lea     rcx, [rbp+57h+DeviceName]; DestinationString
0x14001a258  movups  xmmword ptr [rbp+57h+DeviceName.Length], xmm0
0x14001a25c  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x14001a260  call    cs:__imp_RtlInitUnicodeString
0x14001a267  nop     dword ptr [rax+rax+00h]
0x14001a26c  lea     rdx, aDeviceWanarpv6; "\\Device\\WANARPV6"
0x14001a273  lea     rcx, [rbp+57h+var_70]; DestinationString
0x14001a277  call    cs:__imp_RtlInitUnicodeString
0x14001a27e  nop     dword ptr [rax+rax+00h]
0x14001a283  lea     rax, DeviceObject
0x14001a28a  mov     rcx, rsi; DriverObject
0x14001a28d  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x14001a292  lea     r15, SDDL_SYS_ALL_ADM_ALL
0x14001a299  lea     rax, [rbp+57h+var_50]
0x14001a29d  mov     [rsp+0F0h+DeviceClassGuid], rax; DeviceClassGuid
0x14001a2a2  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x14001a2a6  mov     [rsp+0F0h+DefaultSDDLString], r15; DefaultSDDLString
0x14001a2ab  call    WdmlibIoCreateDeviceSecure
0x14001a2b0  mov     edi, eax
0x14001a2b2  mov     r14d, 1
0x14001a2b8  test    eax, eax
0x14001a2ba  js      loc_14001A498
0x14001a2c0  mov     rcx, cs:DeviceObject
0x14001a2c7  call    WanpSetDeviceObjectDacl
0x14001a2cc  mov     edi, eax
0x14001a2ce  test    eax, eax
0x14001a2d0  js      loc_14001A498
0x14001a2d6  lea     rax, qword_140009B98
0x14001a2dd  mov     rcx, rsi; DriverObject
0x14001a2e0  mov     [rsp+0F0h+DeviceObject], rax; DeviceObject
0x14001a2e5  lea     r8, [rbp+57h+var_70]; DeviceName
0x14001a2e9  lea     rax, [rbp+57h+var_50]
0x14001a2ed  mov     [rsp+0F0h+DeviceClassGuid], rax; DeviceClassGuid
0x14001a2f2  mov     [rsp+0F0h+DefaultSDDLString], r15; DefaultSDDLString
0x14001a2f7  call    WdmlibIoCreateDeviceSecure
0x14001a2fc  mov     edi, eax
0x14001a2fe  test    eax, eax
0x14001a300  js      loc_14001A498
0x14001a306  mov     rcx, cs:qword_140009B98
0x14001a30d  call    WanpSetDeviceObjectDacl
0x14001a312  mov     edi, eax
0x14001a314  test    eax, eax
0x14001a316  js      loc_14001A498
0x14001a31c  mov     r8b, r14b
0x14001a31f  lea     rdx, aDosdevicesWana_0; "\\DosDevices\\WanArp"
0x14001a326  lea     rcx, [rbp+57h+DeviceName]; DeviceName
0x14001a32a  call    WanpSetupExternalName
0x14001a32f  mov     edi, eax
0x14001a331  test    eax, eax
0x14001a333  js      loc_14001A498
0x14001a339  mov     r8b, r14b
0x14001a33c  lea     rdx, aDosdevicesWana; "\\DosDevices\\WanArpV6"
0x14001a343  lea     rcx, [rbp+57h+var_70]; DeviceName
0x14001a347  mov     ebx, r14d
0x14001a34a  call    WanpSetupExternalName
0x14001a34f  mov     edi, eax
0x14001a351  test    eax, eax
0x14001a353  js      loc_14001A498
0x14001a359  lea     rax, WanUnload
0x14001a360  mov     [rsi+50h], r12
0x14001a364  mov     [rsi+68h], rax
0x14001a368  lea     rdi, [rsi+70h]
0x14001a36c  lea     rax, WanDispatch
0x14001a373  lea     ecx, [r14+1Bh]
0x14001a377  rep stosq
0x14001a37a  call    WanpInitializeDriverStructures
0x14001a37f  test    al, al
0x14001a381  jnz     short loc_14001A391
0x14001a383  lea     ebx, [r14+2]
0x14001a387  mov     edi, 0C000009Ah
0x14001a38c  jmp     loc_14001A51F
0x14001a391  lea     rcx, g_wrBindMutex
0x14001a398  call    WanpAcquireResource
0x14001a39d  xor     r9d, r9d; Alertable
0x14001a3a0  mov     cs:byte_140009AEC, r14b
0x14001a3a7  xor     r8d, r8d; WaitMode
0x14001a3aa  mov     cs:byte_140009C0C, r14b
0x14001a3b1  xor     edx, edx; WaitReason
0x14001a3b3  mov     [rsp+0F0h+Timeout], r12; Timeout
0x14001a3b8  mov     rcx, r13; Object
0x14001a3bb  call    cs:__imp_KeWaitForSingleObject
0x14001a3c2  nop     dword ptr [rax+rax+00h]
0x14001a3c7  xor     r8d, r8d
0x14001a3ca  lea     rdx, WanpProcessorAddCallback
0x14001a3d1  lea     rcx, qword_1400098C8
0x14001a3d8  call    cs:__imp_NetioRegisterProcessorAddCallback
0x14001a3df  nop     dword ptr [rax+rax+00h]
0x14001a3e4  mov     edi, eax
0x14001a3e6  test    eax, eax
0x14001a3e8  jns     short loc_14001A405
0x14001a3ea  xor     edx, edx; Wait
0x14001a3ec  mov     rcx, r13; Mutex
0x14001a3ef  mov     ebx, 0Fh
0x14001a3f4  call    cs:__imp_KeReleaseMutex
0x14001a3fb  nop     dword ptr [rax+rax+00h]
0x14001a400  jmp     loc_14001A51F
0x14001a405  mov     ecx, 0FFFFh; GroupNumber
0x14001a40a  mov     ebx, 2Fh ; '/'
0x14001a40f  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14001a416  nop     dword ptr [rax+rax+00h]
0x14001a41b  mov     cs:dword_1400098C0, eax
0x14001a421  call    cs:__imp_NetioInitializeNetBufferListLibrary
0x14001a428  nop     dword ptr [rax+rax+00h]
0x14001a42d  mov     edi, eax
0x14001a42f  test    eax, eax
0x14001a431  js      short loc_14001A498
0x14001a433  mov     ebx, 6Fh ; 'o'
0x14001a438  call    WanNmrpRegisterProviders
0x14001a43d  mov     edi, eax
0x14001a43f  test    eax, eax
0x14001a441  js      short loc_14001A498
0x14001a443  xor     edx, edx; Wait
0x14001a445  mov     rcx, r13; Mutex
0x14001a448  call    cs:__imp_KeReleaseMutex
0x14001a44f  nop     dword ptr [rax+rax+00h]
0x14001a454  lea     rcx, g_wrBindMutex
0x14001a45b  mov     cs:byte_140009AEC, r12b
0x14001a462  mov     cs:byte_140009C0C, r12b
0x14001a469  call    WanpReleaseResource
0x14001a46e  mov     ebx, 7Bh ; '{'
0x14001a473  mov     dword ptr cs:qword_140009948+4, r14d
0x14001a47a  lea     r8, NmrClientHandle; NmrClientHandle
0x14001a481  xor     edx, edx; ClientContext
0x14001a483  lea     rcx, FlNaClientNotify; ClientCharacteristics
0x14001a48a  call    cs:__imp_NmrRegisterClient
0x14001a491  nop     dword ptr [rax+rax+00h]
0x14001a496  mov     edi, eax
0x14001a498  test    edi, edi
0x14001a49a  jz      loc_14001A59F
0x14001a4a0  test    bl, 10h
0x14001a4a3  jz      short loc_14001A4D9
0x14001a4a5  xor     r9d, r9d; Alertable
0x14001a4a8  mov     [rsp+0F0h+Timeout], r12; Timeout
0x14001a4ad  xor     r8d, r8d; WaitMode
0x14001a4b0  xor     edx, edx; WaitReason
0x14001a4b2  mov     rcx, r13; Object
0x14001a4b5  call    cs:__imp_KeWaitForSingleObject
0x14001a4bc  nop     dword ptr [rax+rax+00h]
0x14001a4c1  lea     rcx, WanNmrV4ProviderState
0x14001a4c8  call    WanNmrpCleanupProviderState
0x14001a4cd  lea     rcx, WanNmrV6ProviderState
0x14001a4d4  call    WanNmrpCleanupProviderState
0x14001a4d9  test    bl, 40h
0x14001a4dc  jz      short loc_14001A4EA
0x14001a4de  call    cs:__imp_NetioUnInitializeNetBufferListLibrary
0x14001a4e5  nop     dword ptr [rax+rax+00h]
0x14001a4ea  test    bl, 70h
0x14001a4ed  jz      short loc_14001A507
0x14001a4ef  xor     edx, edx; Wait
0x14001a4f1  mov     cs:byte_1400098D8, r14b
0x14001a4f8  mov     rcx, r13; Mutex
0x14001a4fb  call    cs:__imp_KeReleaseMutex
0x14001a502  nop     dword ptr [rax+rax+00h]
0x14001a507  test    bl, 20h
0x14001a50a  jz      short loc_14001A51F
0x14001a50c  lea     rcx, qword_1400098C8
0x14001a513  call    cs:__imp_NetioUnRegisterProcessorAddCallback
0x14001a51a  nop     dword ptr [rax+rax+00h]
0x14001a51f  mov     rcx, cs:DeviceObject; DeviceObject
0x14001a526  test    rcx, rcx
0x14001a529  jz      short loc_14001A537
0x14001a52b  call    cs:__imp_IoDeleteDevice
0x14001a532  nop     dword ptr [rax+rax+00h]
0x14001a537  mov     rcx, cs:qword_140009B98; DeviceObject
0x14001a53e  test    rcx, rcx
0x14001a541  jz      short loc_14001A54F
0x14001a543  call    cs:__imp_IoDeleteDevice
0x14001a54a  nop     dword ptr [rax+rax+00h]
0x14001a54f  test    r14b, bl
0x14001a552  jz      short loc_14001A565
0x14001a554  xor     r8d, r8d
0x14001a557  lea     rdx, aDosdevicesWana_0; "\\DosDevices\\WanArp"
0x14001a55e  xor     ecx, ecx; DeviceName
0x14001a560  call    WanpSetupExternalName
0x14001a565  test    bl, 2
0x14001a568  jz      short loc_14001A57B
0x14001a56a  xor     r8d, r8d
0x14001a56d  lea     rdx, aDosdevicesWana; "\\DosDevices\\WanArpV6"
0x14001a574  xor     ecx, ecx; DeviceName
0x14001a576  call    WanpSetupExternalName
0x14001a57b  test    bl, 8
0x14001a57e  jz      short loc_14001A585
0x14001a580  call    WanpFreeDriverStructures
0x14001a585  test    bl, 4
0x14001a588  jz      short loc_14001A596
0x14001a58a  lea     rcx, g_wrBindMutex
0x14001a591  call    WanpReleaseResource
0x14001a596  call    wil_UninitializeFeatureStaging
  ... truncated ...
```
