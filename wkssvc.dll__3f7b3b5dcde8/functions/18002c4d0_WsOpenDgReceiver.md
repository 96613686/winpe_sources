# WsOpenDgReceiver

- ea: `0x18002c4d0`
- end: `0x18002c594`
- name: `WsOpenDgReceiver`
- size: `196`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800068d0`

## callees

- `0x180007c80`
- `0x18002c4d0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18002c55e`
- `ntdll!NtOpenFile` at `0x18002c55e`
- `ntdll!RtlInitUnicodeString` at `0x18002c509`
- `ntdll!RtlInitUnicodeString` at `0x18002c509`

## pseudocode

```c
__int64 WsOpenDgReceiver()
{
  int Status; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  Status = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\Device\\LanmanDatagramReceiver");
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  if ( !WsDgReceiverDeviceHandle )
  {
    Status = NtOpenFile(&WsDgReceiverDeviceHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
    if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
      WsDgReceiverDeviceHandle = 0;
  }
  return NetpNtStatusToApiStatus(Status);
}

```

## disassembly

```asm
0x18002c4d0  mov     [rsp-8+arg_0], rbx
0x18002c4d5  push    rbp
0x18002c4d6  mov     rbp, rsp
0x18002c4d9  sub     rsp, 80h
0x18002c4e0  xorps   xmm0, xmm0
0x18002c4e3  lea     rdx, aDeviceLanmanda; "\\Device\\LanmanDatagramReceiver"
0x18002c4ea  xorps   xmm1, xmm1
0x18002c4ed  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002c4f1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002c4f5  xor     eax, eax
0x18002c4f7  xor     ebx, ebx
0x18002c4f9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18002c4fd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002c501  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x18002c505  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002c509  call    cs:__imp_RtlInitUnicodeString
0x18002c50f  cmp     cs:WsDgReceiverDeviceHandle, rbx
0x18002c516  lea     rax, [rbp+DestinationString]
0x18002c51a  xorps   xmm0, xmm0
0x18002c51d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002c521  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c526  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002c52d  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18002c531  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002c538  jnz     short loc_18002C57C
0x18002c53a  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x18002c542  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18002c546  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002c54a  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x18002c552  mov     edx, 100000h; DesiredAccess
0x18002c557  lea     rcx, WsDgReceiverDeviceHandle; FileHandle
0x18002c55e  call    cs:__imp_NtOpenFile
0x18002c564  mov     ebx, eax
0x18002c566  test    eax, eax
0x18002c568  js      short loc_18002C571
0x18002c56a  mov     ebx, dword ptr [rbp+IoStatusBlock]
0x18002c56d  test    ebx, ebx
0x18002c56f  jns     short loc_18002C57C
0x18002c571  mov     cs:WsDgReceiverDeviceHandle, 0
0x18002c57c  mov     ecx, ebx; Status
0x18002c57e  call    NetpNtStatusToApiStatus
0x18002c583  mov     rbx, [rsp+80h+arg_0]
0x18002c58b  add     rsp, 80h
0x18002c592  pop     rbp
0x18002c593  retn
```
