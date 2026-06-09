# GenerateRandomData

- ea: `0x180014da0`
- end: `0x180014eb3`
- name: `GenerateRandomData`
- size: `275`
- prototype: `_BOOL8 __fastcall(PVOID OutputBuffer, ULONG OutputBufferLength)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001848`
- `0x18000f22c`
- `0x180014c48`

## callees

- `0x180014da0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180014df1`
- `ntdll!RtlInitUnicodeString` at `0x180014df1`
- `ntdll!NtClose` at `0x180014e8b`
- `ntdll!NtClose` at `0x180014e8b`
- `ntdll!NtOpenFile` at `0x180014e3e`
- `ntdll!NtOpenFile` at `0x180014e3e`
- `ntdll!NtDeviceIoControlFile` at `0x180014e7f`
- `ntdll!NtDeviceIoControlFile` at `0x180014e7f`

## pseudocode

```c
_BOOL8 __fastcall GenerateRandomData(PVOID OutputBuffer, ULONG OutputBufferLength)
{
  _BOOL8 result; // rax
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp+67h] BYREF

  FileHandle = 0;
  result = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( OutputBuffer )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\KsecDD");
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = 0;
    if ( NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x10u) >= 0 )
    {
      v5 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x390008u, 0, 0, OutputBuffer, OutputBufferLength);
      NtClose(FileHandle);
      if ( v5 >= 0 )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014da0  mov     [rsp-8+arg_8], rbx
0x180014da5  mov     [rsp-8+arg_10], rdi
0x180014daa  push    rbp
0x180014dab  lea     rbp, [rsp-57h]
0x180014db0  sub     rsp, 0A0h
0x180014db7  xorps   xmm0, xmm0
0x180014dba  mov     [rbp+57h+FileHandle], 0
0x180014dc2  xor     eax, eax
0x180014dc4  mov     edi, edx
0x180014dc6  mov     rbx, rcx
0x180014dc9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180014dcd  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180014dd1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180014dd5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180014dd9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180014ddd  test    rcx, rcx
0x180014de0  jz      loc_180014E9E
0x180014de6  lea     rdx, aDeviceKsecdd; "\\Device\\KsecDD"
0x180014ded  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180014df1  call    cs:__imp_RtlInitUnicodeString
0x180014df7  lea     rax, [rbp+57h+DestinationString]
0x180014dfb  mov     [rsp+0A0h+OpenOptions], 10h; OpenOptions
0x180014e03  xorps   xmm0, xmm0
0x180014e06  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180014e0a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180014e0e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180014e15  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180014e19  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180014e21  mov     edx, 100001h; DesiredAccess
0x180014e26  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180014e2d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180014e31  mov     [rsp+0A0h+ShareAccess], 7; ShareAccess
0x180014e39  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014e3e  call    cs:__imp_NtOpenFile
0x180014e44  test    eax, eax
0x180014e46  js      short loc_180014E9C
0x180014e48  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180014e4c  lea     rax, [rbp+57h+IoStatusBlock]
0x180014e50  mov     [rsp+0A0h+OutputBufferLength], edi; OutputBufferLength
0x180014e54  xor     r9d, r9d; ApcContext
0x180014e57  mov     [rsp+0A0h+OutputBuffer], rbx; OutputBuffer
0x180014e5c  xor     r8d, r8d; ApcRoutine
0x180014e5f  mov     [rsp+0A0h+InputBufferLength], 0; InputBufferLength
0x180014e67  xor     edx, edx; Event
0x180014e69  mov     [rsp+0A0h+InputBuffer], 0; InputBuffer
0x180014e72  mov     [rsp+0A0h+OpenOptions], 390008h; IoControlCode
0x180014e7a  mov     qword ptr [rsp+0A0h+ShareAccess], rax; IoStatusBlock
0x180014e7f  call    cs:__imp_NtDeviceIoControlFile
0x180014e85  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180014e89  mov     ebx, eax
0x180014e8b  call    cs:__imp_NtClose
0x180014e91  test    ebx, ebx
0x180014e93  js      short loc_180014E9C
0x180014e95  mov     eax, 1
0x180014e9a  jmp     short loc_180014E9E
0x180014e9c  xor     eax, eax
0x180014e9e  lea     r11, [rsp+0A0h+var_s0]
0x180014ea6  mov     rbx, [r11+18h]
0x180014eaa  mov     rdi, [r11+20h]
0x180014eae  mov     rsp, r11
0x180014eb1  pop     rbp
0x180014eb2  retn
```
