# CreateNetworkReadyEvent

- ea: `0x18002c3c4`
- end: `0x18002c497`
- name: `CreateNetworkReadyEvent`
- size: `211`
- prototype: `__int64 __fastcall(PHANDLE EventHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c750`

## callees

- `0x18002c3c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c47b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c47b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c467`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c467`
- `ntdll!NtCreateEvent` at `0x18002c45b`
- `ntdll!NtCreateEvent` at `0x18002c45b`
- `ntdll!RtlNtStatusToDosError` at `0x18002c473`
- `ntdll!RtlNtStatusToDosError` at `0x18002c473`
- `ntdll!RtlInitUnicodeString` at `0x18002c41e`
- `ntdll!RtlInitUnicodeString` at `0x18002c41e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c407`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c407`

## pseudocode

```c
__int64 __fastcall CreateNetworkReadyEvent(PHANDLE EventHandle)
{
  unsigned int v2; // ebx
  int v3; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+18h] BYREF

  SecurityDescriptor = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:(A;;0x100003;;;SY)",
          1u,
          &SecurityDescriptor,
          0) )
    return GetLastError();
  v2 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\BaseNamedObjects\\LanmanServerNetworkInitialized");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.SecurityQualityOfService = 0;
  v3 = NtCreateEvent(EventHandle, 2u, &ObjectAttributes, NotificationEvent, 0);
  LocalFree(SecurityDescriptor);
  if ( v3 < 0 )
    return RtlNtStatusToDosError(v3);
  return v2;
}

```

## disassembly

```asm
0x18002c3c4  mov     [rsp-8+arg_0], rbx
0x18002c3c9  mov     [rsp-8+arg_10], rdi
0x18002c3ce  push    rbp
0x18002c3cf  mov     rbp, rsp
0x18002c3d2  sub     rsp, 70h
0x18002c3d6  xorps   xmm0, xmm0
0x18002c3d9  mov     [rbp+SecurityDescriptor], 0
0x18002c3e1  xor     eax, eax
0x18002c3e3  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002c3e7  mov     rdi, rcx
0x18002c3ea  xor     r9d, r9d; SecurityDescriptorSize
0x18002c3ed  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002c3f1  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;0x100003;;;SY)"
0x18002c3f8  lea     edx, [rax+1]; StringSDRevision
0x18002c3fb  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002c3ff  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18002c403  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002c407  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002c40d  test    eax, eax
0x18002c40f  jz      short loc_18002C47B
0x18002c411  lea     rdx, aBasenamedobjec_0; "\\BaseNamedObjects\\LanmanServerNetwork"...
0x18002c418  xor     ebx, ebx
0x18002c41a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002c41e  call    cs:__imp_RtlInitUnicodeString
0x18002c424  lea     rax, [rbp+DestinationString]
0x18002c428  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002c42f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002c433  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002c437  mov     rax, [rbp+SecurityDescriptor]
0x18002c43b  lea     edx, [rbx+2]; DesiredAccess
0x18002c43e  xor     r9d, r9d; EventType
0x18002c441  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x18002c445  mov     rcx, rdi; EventHandle
0x18002c448  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18002c44c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002c453  mov     [rbp+ObjectAttributes.SecurityQualityOfService], rbx
0x18002c457  mov     [rsp+70h+InitialState], bl; InitialState
0x18002c45b  call    cs:__imp_NtCreateEvent
0x18002c461  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18002c465  mov     edi, eax
0x18002c467  call    cs:__imp_LocalFree
0x18002c46d  test    edi, edi
0x18002c46f  jns     short loc_18002C483
0x18002c471  mov     ecx, edi; Status
0x18002c473  call    cs:__imp_RtlNtStatusToDosError
0x18002c479  jmp     short loc_18002C481
0x18002c47b  call    cs:__imp_GetLastError
0x18002c481  mov     ebx, eax
0x18002c483  lea     r11, [rsp+70h+var_s0]
0x18002c488  mov     eax, ebx
0x18002c48a  mov     rbx, [r11+10h]
0x18002c48e  mov     rdi, [r11+20h]
0x18002c492  mov     rsp, r11
0x18002c495  pop     rbp
0x18002c496  retn
```
