# DriverEntry

- ea: `0x14000c078`
- end: `0x14000c2c7`
- name: `DriverEntry`
- size: `591`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000c010`

## callees

- `0x140002c90`
- `0x14000a230`
- `0x14000b900`
- `0x14000c078`
- `0x14000c2d0`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14000c14b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000c14b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c0cf`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c0cf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c1f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c1f1`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14000c18f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14000c18f`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14000c299`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x14000c299`
- `FLTMGR!FltStartFiltering` at `0x14000c282`
- `FLTMGR!FltStartFiltering` at `0x14000c282`
- `FLTMGR!FltCreateCommunicationPort` at `0x14000c269`
- `FLTMGR!FltCreateCommunicationPort` at `0x14000c269`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x14000c1d0`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x14000c1d0`
- `FLTMGR!FltRegisterFilter` at `0x14000c1ac`
- `FLTMGR!FltRegisterFilter` at `0x14000c1ac`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int (__fastcall *SystemRoutineAddress)(__int64, char *, __int64, _QWORD); // rax
  int started; // ebx
  struct _UNICODE_STRING SystemRoutineName; // [rsp+40h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  char v9; // [rsp+C0h] [rbp+77h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C8h] [rbp+7Fh] BYREF

  SecurityDescriptor = 0;
  v9 = 0;
  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  SystemRoutineName.Buffer = L"NtQuerySystemInformation";
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SystemRoutineAddress = (int (__fastcall *)(__int64, char *, __int64, _QWORD))MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress && SystemRoutineAddress(227, &v9, 1, 0) >= 0 && v9 )
    ExPoolZeroingNativelySupported = 1;
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  started = wil_InitializeFeatureStaging();
  byte_140006198 = started >= 0;
  if ( (int)(started + 0x80000000) < 0 || started == -1073741511 )
  {
    started = ExInitializeResourceLite(&Resource);
    if ( started >= 0 )
    {
      byte_140006199 = 1;
      ExInitializePagedLookasideList(&Lookaside, 0, 0, 0, 0x40u, 0x50466372u, 0);
      started = FltRegisterFilter(DriverObject, &FilterRegistration, &gFilterHandle);
      if ( started >= 0 )
      {
        WMCommListCreate();
        started = FltBuildDefaultSecurityDescriptor(&SecurityDescriptor, 0x1F0001u);
        if ( started >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, L"\\PFPort");
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 576;
          ObjectAttributes.SecurityQualityOfService = 0;
          started = FltCreateCommunicationPort(
                      gFilterHandle,
                      &ServerPort,
                      &ObjectAttributes,
                      0,
                      PFPortConnect,
                      PFPortDisconnect,
                      PFReceiveMessage,
                      256);
          if ( started >= 0 )
            started = FltStartFiltering(gFilterHandle);
        }
      }
    }
  }
  if ( SecurityDescriptor )
    FltFreeSecurityDescriptor(SecurityDescriptor);
  if ( started < 0 )
    Unload();
  return started;
}

```

## disassembly

```asm
0x14000c078  mov     [rsp-8+arg_0], rbx
0x14000c07d  push    rbp
0x14000c07e  push    rdi
0x14000c07f  push    r14
0x14000c081  lea     rbp, [rsp-47h]
0x14000c086  sub     rsp, 90h
0x14000c08d  xorps   xmm1, xmm1
0x14000c090  mov     [rbp+57h+SecurityDescriptor], 0
0x14000c098  mov     rdi, rcx
0x14000c09b  mov     [rbp+57h+arg_10], 0
0x14000c09f  xorps   xmm0, xmm0
0x14000c0a2  mov     qword ptr [rbp+57h+SystemRoutineName.Length], 320030h
0x14000c0aa  lea     rax, aNtquerysystemi; "NtQuerySystemInformation"
0x14000c0b1  mov     r14d, 30h ; '0'
0x14000c0b7  lea     rcx, [rbp+57h+SystemRoutineName]; SystemRoutineName
0x14000c0bb  mov     [rbp+57h+SystemRoutineName.Buffer], rax
0x14000c0bf  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000c0c3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x14000c0c7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14000c0cb  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x14000c0cf  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c0d6  nop     dword ptr [rax+rax+00h]
0x14000c0db  test    rax, rax
0x14000c0de  jz      short loc_14000C106
0x14000c0e0  xor     r9d, r9d
0x14000c0e3  lea     r8d, [r14-2Fh]
0x14000c0e7  lea     rdx, [rbp+57h+arg_10]
0x14000c0eb  mov     ecx, 0E3h
0x14000c0f0  call    _guard_dispatch_icall
0x14000c0f5  test    eax, eax
0x14000c0f7  js      short loc_14000C106
0x14000c0f9  cmp     [rbp+57h+arg_10], 0
0x14000c0fd  jz      short loc_14000C106
0x14000c0ff  mov     cs:ExPoolZeroingNativelySupported, 1
0x14000c106  mov     cs:ExDefaultNonPagedPoolType, 200h
0x14000c110  mov     cs:ExDefaultMdlProtection, 40000000h
0x14000c11a  call    wil_InitializeFeatureStaging
0x14000c11f  mov     ebx, eax
0x14000c121  mov     ecx, 80000000h
0x14000c126  shr     eax, 1Fh
0x14000c129  xor     al, 1
0x14000c12b  mov     cs:byte_140006198, al
0x14000c131  lea     eax, [rbx+rcx]
0x14000c134  test    ecx, eax
0x14000c136  jnz     short loc_14000C144
0x14000c138  cmp     ebx, 0C0000139h
0x14000c13e  jnz     loc_14000C290
0x14000c144  lea     rcx, Resource; Resource
0x14000c14b  call    cs:__imp_ExInitializeResourceLite
0x14000c152  nop     dword ptr [rax+rax+00h]
0x14000c157  mov     ebx, eax
0x14000c159  test    eax, eax
0x14000c15b  js      loc_14000C290
0x14000c161  xor     eax, eax
0x14000c163  mov     cs:byte_140006199, 1
0x14000c16a  mov     [rsp+0A0h+Depth], ax; Depth
0x14000c16f  lea     rcx, Lookaside; Lookaside
0x14000c176  mov     [rsp+0A0h+Tag], 50466372h; Tag
0x14000c17e  xor     r9d, r9d; Flags
0x14000c181  xor     r8d, r8d; Free
0x14000c184  mov     [rsp+0A0h+Size], 40h ; '@'; Size
0x14000c18d  xor     edx, edx; Allocate
0x14000c18f  call    cs:__imp_ExInitializePagedLookasideList
0x14000c196  nop     dword ptr [rax+rax+00h]
0x14000c19b  lea     r8, gFilterHandle; RetFilter
0x14000c1a2  mov     rcx, rdi; Driver
0x14000c1a5  lea     rdx, FilterRegistration; Registration
0x14000c1ac  call    cs:__imp_FltRegisterFilter
0x14000c1b3  nop     dword ptr [rax+rax+00h]
0x14000c1b8  mov     ebx, eax
0x14000c1ba  test    eax, eax
0x14000c1bc  js      loc_14000C290
0x14000c1c2  call    WMCommListCreate
0x14000c1c7  mov     edx, 1F0001h; DesiredAccess
0x14000c1cc  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14000c1d0  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x14000c1d7  nop     dword ptr [rax+rax+00h]
0x14000c1dc  mov     ebx, eax
0x14000c1de  test    eax, eax
0x14000c1e0  js      loc_14000C290
0x14000c1e6  lea     rdx, SourceString; "\\PFPort"
0x14000c1ed  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000c1f1  call    cs:__imp_RtlInitUnicodeString
0x14000c1f8  nop     dword ptr [rax+rax+00h]
0x14000c1fd  mov     rcx, cs:gFilterHandle; Filter
0x14000c204  lea     rax, [rbp+57h+DestinationString]
0x14000c208  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000c20c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000c210  mov     rax, [rbp+57h+SecurityDescriptor]
0x14000c214  lea     rdx, ServerPort; ServerPort
0x14000c21b  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x14000c21f  xor     r9d, r9d; ServerPortCookie
0x14000c222  mov     [rsp+0A0h+MaxConnections], 100h; MaxConnections
0x14000c22a  lea     rax, PFReceiveMessage
0x14000c231  mov     qword ptr [rsp+0A0h+Depth], rax; MessageNotifyCallback
0x14000c236  lea     rax, PFPortDisconnect
0x14000c23d  mov     qword ptr [rsp+0A0h+Tag], rax; DisconnectNotifyCallback
0x14000c242  lea     rax, PFPortConnect
0x14000c249  mov     [rsp+0A0h+Size], rax; ConnectNotifyCallback
0x14000c24e  mov     [rbp+57h+ObjectAttributes.Length], r14d
0x14000c252  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000c25a  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000c261  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x14000c269  call    cs:__imp_FltCreateCommunicationPort
0x14000c270  nop     dword ptr [rax+rax+00h]
0x14000c275  mov     ebx, eax
0x14000c277  test    eax, eax
0x14000c279  js      short loc_14000C290
0x14000c27b  mov     rcx, cs:gFilterHandle; Filter
0x14000c282  call    cs:__imp_FltStartFiltering
0x14000c289  nop     dword ptr [rax+rax+00h]
0x14000c28e  mov     ebx, eax
0x14000c290  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14000c294  test    rcx, rcx
0x14000c297  jz      short loc_14000C2A5
0x14000c299  call    cs:__imp_FltFreeSecurityDescriptor
0x14000c2a0  nop     dword ptr [rax+rax+00h]
0x14000c2a5  test    ebx, ebx
0x14000c2a7  jns     short loc_14000C2B0
0x14000c2a9  xor     ecx, ecx
0x14000c2ab  call    Unload
0x14000c2b0  mov     eax, ebx
0x14000c2b2  mov     rbx, [rsp+0A0h+arg_0]
0x14000c2ba  add     rsp, 90h
0x14000c2c1  pop     r14
0x14000c2c3  pop     rdi
0x14000c2c4  pop     rbp
0x14000c2c5  retn
```
