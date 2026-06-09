# WsOpenRedirector

- ea: `0x18000888c`
- end: `0x180008948`
- name: `WsOpenRedirector`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006e0c`

## callees

- `0x1800081b0`
- `0x18000888c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180008915`
- `ntdll!NtOpenFile` at `0x180008915`
- `ntdll!RtlInitUnicodeString` at `0x1800088bf`
- `ntdll!RtlInitUnicodeString` at `0x1800088bf`

## pseudocode

```c
__int64 WsOpenRedirector()
{
  int Status; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\Device\\LanmanRedirector");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = NtOpenFile(&WsRedirDeviceHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
    WsRedirDeviceHandle = 0;
  return NetpNtStatusToApiStatus(Status);
}

```

## disassembly

```asm
0x18000888c  push    rbp
0x18000888e  mov     rbp, rsp
0x180008891  sub     rsp, 80h
0x180008898  xorps   xmm0, xmm0
0x18000889b  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x1800088a2  xorps   xmm1, xmm1
0x1800088a5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800088a9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800088ad  xor     eax, eax
0x1800088af  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800088b3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800088b7  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x1800088bb  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800088bf  call    cs:__imp_RtlInitUnicodeString
0x1800088c6  nop     dword ptr [rax+rax+00h]
0x1800088cb  lea     rax, [rbp+DestinationString]
0x1800088cf  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x1800088d7  xorps   xmm0, xmm0
0x1800088da  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800088de  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800088e2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800088e9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800088ed  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800088f5  mov     edx, 100000h; DesiredAccess
0x1800088fa  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180008901  lea     rcx, WsRedirDeviceHandle; FileHandle
0x180008908  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x180008910  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180008915  call    cs:__imp_NtOpenFile
0x18000891c  nop     dword ptr [rax+rax+00h]
0x180008921  test    eax, eax
0x180008923  js      short loc_18000892C
0x180008925  mov     eax, dword ptr [rbp+IoStatusBlock]
0x180008928  test    eax, eax
0x18000892a  jns     short loc_180008937
0x18000892c  mov     cs:WsRedirDeviceHandle, 0
0x180008937  mov     ecx, eax; Status
0x180008939  call    NetpNtStatusToApiStatus
0x18000893e  add     rsp, 80h
0x180008945  pop     rbp
0x180008946  retn
```
