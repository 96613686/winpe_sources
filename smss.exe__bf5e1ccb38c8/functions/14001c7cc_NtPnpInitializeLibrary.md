# NtPnpInitializeLibrary

- ea: `0x14001c7cc`
- end: `0x14001c89c`
- name: `NtPnpInitializeLibrary`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140016190`

## callees

- `0x14001c7cc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001c813`
- `ntdll!RtlInitUnicodeString` at `0x14001c813`
- `ntdll!NtCreateFile` at `0x14001c88d`
- `ntdll!NtCreateFile` at `0x14001c88d`

## pseudocode

```c
NTSTATUS NtPnpInitializeLibrary()
{
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( NtPnpDeviceApiDriverHandle )
    return -1073740528;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\DeviceApi\\CMApi");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return NtCreateFile(&NtPnpDeviceApiDriverHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 1u, 0, 0, 0);
}

```

## disassembly

```asm
0x14001c7cc  push    rbp
0x14001c7ce  lea     rbp, [rsp-57h]
0x14001c7d3  sub     rsp, 0B0h
0x14001c7da  cmp     cs:NtPnpDeviceApiDriverHandle, 0
0x14001c7e2  xorps   xmm1, xmm1
0x14001c7e5  xorps   xmm0, xmm0
0x14001c7e8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001c7ec  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x14001c7f0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14001c7f4  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x14001c7f8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14001c7fc  jz      short loc_14001C808
0x14001c7fe  mov     eax, 0C0000510h
0x14001c803  jmp     loc_14001C893
0x14001c808  lea     rdx, aDeviceDeviceap; "\\Device\\DeviceApi\\CMApi"
0x14001c80f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001c813  call    cs:__imp_RtlInitUnicodeString
0x14001c819  mov     [rsp+0B0h+EaLength], 0; EaLength
0x14001c821  lea     rax, [rbp+57h+DestinationString]
0x14001c825  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x14001c82e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14001c832  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x14001c83a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001c83e  mov     [rsp+0B0h+CreateDisposition], 1; CreateDisposition
0x14001c846  lea     rcx, NtPnpDeviceApiDriverHandle; FileHandle
0x14001c84d  mov     [rsp+0B0h+ShareAccess], 0; ShareAccess
0x14001c855  xorps   xmm0, xmm0
0x14001c858  mov     [rsp+0B0h+FileAttributes], 0; FileAttributes
0x14001c860  mov     edx, 80000000h; DesiredAccess
0x14001c865  mov     [rsp+0B0h+AllocationSize], 0; AllocationSize
0x14001c86e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001c875  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14001c87d  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x14001c884  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001c888  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001c88d  call    cs:__imp_NtCreateFile
0x14001c893  add     rsp, 0B0h
0x14001c89a  pop     rbp
0x14001c89b  retn
```
