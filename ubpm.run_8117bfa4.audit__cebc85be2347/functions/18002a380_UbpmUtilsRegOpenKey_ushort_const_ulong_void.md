# UbpmUtilsRegOpenKey(ushort const *,ulong,void * *)

- ea: `0x18002a380`
- end: `0x18002a41a`
- name: `?UbpmUtilsRegOpenKey@@YAKPEBGKPEAPEAX@Z`
- size: `154`
- prototype: `unsigned int __fastcall(PCWSTR SourceString, ACCESS_MASK DesiredAccess, PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029de0`
- `0x180036484`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002a3b4`
- `ntdll!RtlInitUnicodeString` at `0x18002a3b4`
- `ntdll!NtOpenKey` at `0x18002a3ef`
- `ntdll!NtOpenKey` at `0x18002a3ef`
- `ntdll!RtlNtStatusToDosError` at `0x18002a3fd`
- `ntdll!RtlNtStatusToDosError` at `0x18002a3fd`

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
0x18002a380  mov     [rsp-8+arg_0], rbx
0x18002a385  mov     [rsp-8+arg_8], rdi
0x18002a38a  push    rbp
0x18002a38b  mov     rbp, rsp
0x18002a38e  sub     rsp, 60h
0x18002a392  xorps   xmm1, xmm1
0x18002a395  mov     ebx, edx
0x18002a397  mov     rdx, rcx; SourceString
0x18002a39a  xorps   xmm0, xmm0
0x18002a39d  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002a3a1  mov     rdi, r8
0x18002a3a4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002a3a8  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x18002a3ac  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x18002a3b0  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x18002a3b4  call    cs:__imp_RtlInitUnicodeString
0x18002a3bb  nop     dword ptr [rax+rax+00h]
0x18002a3c0  lea     rax, [rbp+DestinationString]
0x18002a3c4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002a3cb  xorps   xmm0, xmm0
0x18002a3ce  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002a3d2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002a3d6  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18002a3de  mov     edx, ebx; DesiredAccess
0x18002a3e0  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002a3e7  mov     rcx, rdi; KeyHandle
0x18002a3ea  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002a3ef  call    cs:__imp_NtOpenKey
0x18002a3f6  nop     dword ptr [rax+rax+00h]
0x18002a3fb  mov     ecx, eax; Status
0x18002a3fd  call    cs:__imp_RtlNtStatusToDosError
0x18002a404  nop     dword ptr [rax+rax+00h]
0x18002a409  mov     rbx, [rsp+60h+arg_0]
0x18002a40e  mov     rdi, [rsp+60h+arg_8]
0x18002a413  add     rsp, 60h
0x18002a417  pop     rbp
0x18002a418  retn
```
