# OpenBrowser

- ea: `0x180006f00`
- end: `0x180006fa3`
- name: `OpenBrowser`
- size: `163`
- prototype: `__int64 __fastcall(PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006fb0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180006f86`
- `ntdll!NtOpenFile` at `0x180006f86`
- `ntdll!RtlInitUnicodeString` at `0x180006f3a`
- `ntdll!RtlInitUnicodeString` at `0x180006f3a`

## pseudocode

```c
int __fastcall OpenBrowser(PHANDLE FileHandle)
{
  int result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\Device\\LanmanDatagramReceiver");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenFile(FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( result >= 0 )
    return IoStatusBlock.Status;
  return result;
}

```

## disassembly

```asm
0x180006f00  mov     [rsp-8+arg_0], rbx
0x180006f05  push    rbp
0x180006f06  mov     rbp, rsp
0x180006f09  sub     rsp, 80h
0x180006f10  xorps   xmm0, xmm0
0x180006f13  lea     rdx, aDeviceLanmanda; "\\Device\\LanmanDatagramReceiver"
0x180006f1a  mov     rbx, rcx
0x180006f1d  xorps   xmm1, xmm1
0x180006f20  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180006f24  xor     eax, eax
0x180006f26  lea     rcx, [rbp+DestinationString]; DestinationString
0x180006f2a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180006f2e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180006f32  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180006f36  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180006f3a  call    cs:__imp_RtlInitUnicodeString
0x180006f40  lea     rax, [rbp+DestinationString]
0x180006f44  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x180006f4c  xorps   xmm0, xmm0
0x180006f4f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180006f53  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180006f57  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180006f5e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180006f62  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180006f6a  mov     edx, 0C0100000h; DesiredAccess
0x180006f6f  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180006f76  mov     rcx, rbx; FileHandle
0x180006f79  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x180006f81  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180006f86  call    cs:__imp_NtOpenFile
0x180006f8c  mov     rbx, [rsp+80h+arg_0]
0x180006f94  test    eax, eax
0x180006f96  cmovns  eax, dword ptr [rbp+IoStatusBlock]
0x180006f9a  add     rsp, 80h
0x180006fa1  pop     rbp
0x180006fa2  retn
```
