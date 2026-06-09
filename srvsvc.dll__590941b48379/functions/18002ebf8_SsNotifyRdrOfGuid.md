# SsNotifyRdrOfGuid

- ea: `0x18002ebf8`
- end: `0x18002ecec`
- name: `SsNotifyRdrOfGuid`
- size: `244`
- prototype: `__int64 __fastcall(PVOID InputBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001764`

## callees

- `0x18002ebf8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18002ec86`
- `ntdll!NtOpenFile` at `0x18002ec86`
- `ntdll!NtFsControlFile` at `0x18002eccb`
- `ntdll!NtFsControlFile` at `0x18002eccb`
- `ntdll!RtlInitUnicodeString` at `0x18002ec39`
- `ntdll!RtlInitUnicodeString` at `0x18002ec39`
- `ntdll!NtClose` at `0x18002ecd5`
- `ntdll!NtClose` at `0x18002ecd5`

## pseudocode

```c
int __fastcall SsNotifyRdrOfGuid(PVOID InputBuffer)
{
  int result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+6Fh] BYREF

  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\LanmanRedirector");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenFile(&FileHandle, 0x1F01FFu, &ObjectAttributes, &IoStatusBlock, 0, 0x20u);
  if ( result >= 0 )
  {
    NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x1401E4u, InputBuffer, 0x10u, 0, 0);
    return NtClose(FileHandle);
  }
  return result;
}

```

## disassembly

```asm
0x18002ebf8  mov     [rsp-8+arg_0], rbx
0x18002ebfd  push    rbp
0x18002ebfe  lea     rbp, [rsp-57h]
0x18002ec03  sub     rsp, 0A0h
0x18002ec0a  xorps   xmm0, xmm0
0x18002ec0d  mov     [rbp+57h+FileHandle], 0
0x18002ec15  mov     rbx, rcx
0x18002ec18  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x18002ec1f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002ec23  xor     eax, eax
0x18002ec25  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002ec29  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002ec2d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002ec31  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002ec35  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002ec39  call    cs:__imp_RtlInitUnicodeString
0x18002ec3f  lea     rax, [rbp+57h+DestinationString]
0x18002ec43  mov     [rsp+0A0h+OpenOptions], 20h ; ' '; OpenOptions
0x18002ec4b  xorps   xmm0, xmm0
0x18002ec4e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002ec52  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002ec56  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002ec5d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002ec61  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002ec69  mov     edx, 1F01FFh; DesiredAccess
0x18002ec6e  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002ec75  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002ec79  mov     [rsp+0A0h+ShareAccess], 0; ShareAccess
0x18002ec81  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ec86  call    cs:__imp_NtOpenFile
0x18002ec8c  test    eax, eax
0x18002ec8e  js      short loc_18002ECDB
0x18002ec90  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002ec94  lea     rax, [rbp+57h+IoStatusBlock]
0x18002ec98  mov     [rsp+0A0h+OutputBufferLength], 0; OutputBufferLength
0x18002eca0  xor     r9d, r9d; ApcContext
0x18002eca3  mov     [rsp+0A0h+OutputBuffer], 0; OutputBuffer
0x18002ecac  xor     r8d, r8d; ApcRoutine
0x18002ecaf  mov     [rsp+0A0h+InputBufferLength], 10h; InputBufferLength
0x18002ecb7  xor     edx, edx; Event
0x18002ecb9  mov     [rsp+0A0h+InputBuffer], rbx; InputBuffer
0x18002ecbe  mov     [rsp+0A0h+OpenOptions], 1401E4h; FsControlCode
0x18002ecc6  mov     qword ptr [rsp+0A0h+ShareAccess], rax; IoStatusBlock
0x18002eccb  call    cs:__imp_NtFsControlFile
0x18002ecd1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18002ecd5  call    cs:__imp_NtClose
0x18002ecdb  mov     rbx, [rsp+0A0h+arg_0]
0x18002ece3  add     rsp, 0A0h
0x18002ecea  pop     rbp
0x18002eceb  retn
```
