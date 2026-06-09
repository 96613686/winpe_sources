# SmpGetControlDeviceHandle

- ea: `0x14000dfc0`
- end: `0x14000e06c`
- name: `SmpGetControlDeviceHandle`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000df30`

## callees

- `0x14000dfc0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000dffb`
- `ntdll!RtlInitUnicodeString` at `0x14000dffb`
- `ntdll!NtOpenFile` at `0x14000e048`
- `ntdll!NtOpenFile` at `0x14000e048`

## pseudocode

```c
NTSTATUS __fastcall SmpGetControlDeviceHandle(void **a1)
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp+20h] BYREF

  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\RdyBoost");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( result >= 0 )
  {
    *a1 = FileHandle;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000dfc0  mov     [rsp-8+arg_0], rbx
0x14000dfc5  push    rbp
0x14000dfc6  mov     rbp, rsp
0x14000dfc9  sub     rsp, 80h
0x14000dfd0  xorps   xmm0, xmm0
0x14000dfd3  lea     rdx, aDeviceRdyboost; "\\Device\\RdyBoost"
0x14000dfda  mov     rbx, rcx
0x14000dfdd  xor     eax, eax
0x14000dfdf  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000dfe3  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000dfe7  mov     [rbp+FileHandle], rax
0x14000dfeb  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000dfef  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000dff3  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000dff7  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14000dffb  call    cs:__imp_RtlInitUnicodeString
0x14000e001  lea     rax, [rbp+DestinationString]
0x14000e005  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x14000e00d  xorps   xmm0, xmm0
0x14000e010  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000e014  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14000e018  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000e01f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000e023  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000e02b  mov     edx, 12019Fh; DesiredAccess
0x14000e030  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14000e037  lea     rcx, [rbp+FileHandle]; FileHandle
0x14000e03b  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x14000e043  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e048  call    cs:__imp_NtOpenFile
0x14000e04e  test    eax, eax
0x14000e050  js      short loc_14000E05B
0x14000e052  mov     rax, [rbp+FileHandle]
0x14000e056  mov     [rbx], rax
0x14000e059  xor     eax, eax
0x14000e05b  mov     rbx, [rsp+80h+arg_0]
0x14000e063  add     rsp, 80h
0x14000e06a  pop     rbp
0x14000e06b  retn
```
