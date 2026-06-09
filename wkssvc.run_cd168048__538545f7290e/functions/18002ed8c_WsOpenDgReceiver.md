# WsOpenDgReceiver

- ea: `0x18002ed8c`
- end: `0x18002ee5d`
- name: `WsOpenDgReceiver`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006e0c`

## callees

- `0x1800081b0`
- `0x18002ed8c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18002ee20`
- `ntdll!NtOpenFile` at `0x18002ee20`
- `ntdll!RtlInitUnicodeString` at `0x18002edc5`
- `ntdll!RtlInitUnicodeString` at `0x18002edc5`

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
0x18002ed8c  mov     [rsp-8+arg_0], rbx
0x18002ed91  push    rbp
0x18002ed92  mov     rbp, rsp
0x18002ed95  sub     rsp, 80h
0x18002ed9c  xorps   xmm0, xmm0
0x18002ed9f  lea     rdx, aDeviceLanmanda; "\\Device\\LanmanDatagramReceiver"
0x18002eda6  xorps   xmm1, xmm1
0x18002eda9  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002edad  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002edb1  xor     eax, eax
0x18002edb3  xor     ebx, ebx
0x18002edb5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18002edb9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002edbd  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x18002edc1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002edc5  call    cs:__imp_RtlInitUnicodeString
0x18002edcc  nop     dword ptr [rax+rax+00h]
0x18002edd1  cmp     cs:WsDgReceiverDeviceHandle, rbx
0x18002edd8  lea     rax, [rbp+DestinationString]
0x18002eddc  xorps   xmm0, xmm0
0x18002eddf  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002ede3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ede8  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002edef  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18002edf3  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002edfa  jnz     short loc_18002EE44
0x18002edfc  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x18002ee04  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18002ee08  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002ee0c  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x18002ee14  mov     edx, 100000h; DesiredAccess
0x18002ee19  lea     rcx, WsDgReceiverDeviceHandle; FileHandle
0x18002ee20  call    cs:__imp_NtOpenFile
0x18002ee27  nop     dword ptr [rax+rax+00h]
0x18002ee2c  mov     ebx, eax
0x18002ee2e  test    eax, eax
0x18002ee30  js      short loc_18002EE39
0x18002ee32  mov     ebx, dword ptr [rbp+IoStatusBlock]
0x18002ee35  test    ebx, ebx
0x18002ee37  jns     short loc_18002EE44
0x18002ee39  mov     cs:WsDgReceiverDeviceHandle, 0
0x18002ee44  mov     ecx, ebx; Status
0x18002ee46  call    NetpNtStatusToApiStatus
0x18002ee4b  mov     rbx, [rsp+80h+arg_0]
0x18002ee53  add     rsp, 80h
0x18002ee5a  pop     rbp
0x18002ee5b  retn
```
