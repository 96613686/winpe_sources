# CreateSetupLaunchClaimEvent

- ea: `0x140099714`
- end: `0x1400997cf`
- name: `CreateSetupLaunchClaimEvent`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400877f0`
- `0x14009965c`

## callees

- `0x140099714`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x1400997a8`
- `ntdll!NtCreateEvent` at `0x1400997a8`
- `ntdll!NtOpenEvent` at `0x140099786`
- `ntdll!NtOpenEvent` at `0x140099786`
- `ntdll!RtlInitUnicodeString` at `0x140099749`
- `ntdll!RtlInitUnicodeString` at `0x140099749`
- `ntdll!NtClose` at `0x140099796`
- `ntdll!NtClose` at `0x140099796`

## pseudocode

```c
__int64 __fastcall CreateSetupLaunchClaimEvent(int a1)
{
  NTSTATUS v2; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+88h] [rbp+18h] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SETUP_LAUNCH_CLAIMED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 32;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a1 )
  {
    v2 = NtOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes);
    if ( v2 >= 0 )
      NtClose(EventHandle);
  }
  else
  {
    v2 = NtCreateEvent(&EventHandle, 0, &ObjectAttributes, NotificationEvent, 0);
    if ( v2 >= 0 )
      qword_1400D33E0 = (__int64)EventHandle;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140099714  mov     [rsp-8+arg_0], rbx
0x140099719  push    rbp
0x14009971a  mov     rbp, rsp
0x14009971d  sub     rsp, 70h
0x140099721  xorps   xmm0, xmm0
0x140099724  mov     [rbp+EventHandle], 0
0x14009972c  mov     ebx, ecx
0x14009972e  lea     rdx, aSetupLaunchCla; "\\SETUP_LAUNCH_CLAIMED"
0x140099735  lea     rcx, [rbp+DestinationString]; DestinationString
0x140099739  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14009973d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140099741  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140099745  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140099749  call    cs:__imp_RtlInitUnicodeString
0x14009974f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140099756  lea     rax, [rbp+DestinationString]
0x14009975a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14009975e  xorps   xmm0, xmm0
0x140099761  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140099769  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14009976d  mov     [rbp+ObjectAttributes.Attributes], 20h ; ' '
0x140099774  lea     rcx, [rbp+EventHandle]; EventHandle
0x140099778  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14009977d  test    ebx, ebx
0x14009977f  jz      short loc_14009979E
0x140099781  mov     edx, 100000h; DesiredAccess
0x140099786  call    cs:__imp_NtOpenEvent
0x14009978c  mov     ebx, eax
0x14009978e  test    eax, eax
0x140099790  js      short loc_1400997BF
0x140099792  mov     rcx, [rbp+EventHandle]; Handle
0x140099796  call    cs:__imp_NtClose
0x14009979c  jmp     short loc_1400997BF
0x14009979e  xor     r9d, r9d; EventType
0x1400997a1  mov     [rsp+70h+InitialState], 0; InitialState
0x1400997a6  xor     edx, edx; DesiredAccess
0x1400997a8  call    cs:__imp_NtCreateEvent
0x1400997ae  mov     ebx, eax
0x1400997b0  test    eax, eax
0x1400997b2  js      short loc_1400997BF
0x1400997b4  mov     rax, [rbp+EventHandle]
0x1400997b8  mov     cs:qword_1400D33E0, rax
0x1400997bf  mov     eax, ebx
0x1400997c1  mov     rbx, [rsp+70h+arg_0]
0x1400997c9  add     rsp, 70h
0x1400997cd  pop     rbp
0x1400997ce  retn
```
