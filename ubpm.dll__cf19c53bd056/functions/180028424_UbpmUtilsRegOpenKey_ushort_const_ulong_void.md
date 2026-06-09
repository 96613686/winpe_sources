# UbpmUtilsRegOpenKey(ushort const *,ulong,void * *)

- ea: `0x180028424`
- end: `0x1800284ab`
- name: `?UbpmUtilsRegOpenKey@@YAKPEBGKPEAPEAX@Z`
- size: `135`
- prototype: `unsigned int __fastcall(PCWSTR SourceString, ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027eb4`
- `0x180034034`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180028458`
- `ntdll!RtlInitUnicodeString` at `0x180028458`
- `ntdll!NtOpenKey` at `0x18002848d`
- `ntdll!NtOpenKey` at `0x18002848d`
- `ntdll!RtlNtStatusToDosError` at `0x180028495`
- `ntdll!RtlNtStatusToDosError` at `0x180028495`

## pseudocode

```c
ULONG __fastcall UbpmUtilsRegOpenKey(PCWSTR SourceString, ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)
{
  NTSTATUS v5; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = NtOpenKey(KeyHandle, DesiredAccess, &ObjectAttributes);
  return RtlNtStatusToDosError(v5);
}

```

## disassembly

```asm
0x180028424  mov     [rsp-8+arg_0], rbx
0x180028429  mov     [rsp-8+arg_8], rdi
0x18002842e  push    rbp
0x18002842f  mov     rbp, rsp
0x180028432  sub     rsp, 60h
0x180028436  xorps   xmm1, xmm1
0x180028439  mov     ebx, edx
0x18002843b  mov     rdx, rcx; SourceString
0x18002843e  xorps   xmm0, xmm0
0x180028441  lea     rcx, [rbp+DestinationString]; DestinationString
0x180028445  mov     rdi, r8
0x180028448  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002844c  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x180028450  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x180028454  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x180028458  call    cs:__imp_RtlInitUnicodeString
0x18002845e  lea     rax, [rbp+DestinationString]
0x180028462  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180028469  xorps   xmm0, xmm0
0x18002846c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180028470  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180028474  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18002847c  mov     edx, ebx; DesiredAccess
0x18002847e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180028485  mov     rcx, rdi; KeyHandle
0x180028488  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002848d  call    cs:__imp_NtOpenKey
0x180028493  mov     ecx, eax; Status
0x180028495  call    cs:__imp_RtlNtStatusToDosError
0x18002849b  mov     rbx, [rsp+60h+arg_0]
0x1800284a0  mov     rdi, [rsp+60h+arg_8]
0x1800284a5  add     rsp, 60h
0x1800284a9  pop     rbp
0x1800284aa  retn
```
