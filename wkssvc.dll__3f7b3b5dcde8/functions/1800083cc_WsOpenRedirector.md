# WsOpenRedirector

- ea: `0x1800083cc`
- end: `0x18000847b`
- name: `WsOpenRedirector`
- size: `175`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800068d0`

## callees

- `0x180007c80`
- `0x1800083cc`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000844f`
- `ntdll!NtOpenFile` at `0x18000844f`
- `ntdll!RtlInitUnicodeString` at `0x1800083ff`
- `ntdll!RtlInitUnicodeString` at `0x1800083ff`

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
0x1800083cc  push    rbp
0x1800083ce  mov     rbp, rsp
0x1800083d1  sub     rsp, 80h
0x1800083d8  xorps   xmm0, xmm0
0x1800083db  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x1800083e2  xorps   xmm1, xmm1
0x1800083e5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800083e9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800083ed  xor     eax, eax
0x1800083ef  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800083f3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800083f7  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x1800083fb  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800083ff  call    cs:__imp_RtlInitUnicodeString
0x180008405  lea     rax, [rbp+DestinationString]
0x180008409  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x180008411  xorps   xmm0, xmm0
0x180008414  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180008418  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18000841c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180008423  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180008427  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18000842f  mov     edx, 100000h; DesiredAccess
0x180008434  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000843b  lea     rcx, WsRedirDeviceHandle; FileHandle
0x180008442  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x18000844a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000844f  call    cs:__imp_NtOpenFile
0x180008455  test    eax, eax
0x180008457  js      short loc_180008460
0x180008459  mov     eax, dword ptr [rbp+IoStatusBlock]
0x18000845c  test    eax, eax
0x18000845e  jns     short loc_18000846B
0x180008460  mov     cs:WsRedirDeviceHandle, 0
0x18000846b  mov     ecx, eax; Status
0x18000846d  call    NetpNtStatusToApiStatus
0x180008472  add     rsp, 80h
0x180008479  pop     rbp
0x18000847a  retn
```
