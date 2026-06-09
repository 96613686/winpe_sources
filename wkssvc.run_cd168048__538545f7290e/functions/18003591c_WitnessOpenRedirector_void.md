# WitnessOpenRedirector(void * *)

- ea: `0x18003591c`
- end: `0x1800359f7`
- name: `?WitnessOpenRedirector@@YAKPEAPEAX@Z`
- size: `219`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ce14`

## callees

- `0x18003591c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800359af`
- `ntdll!NtOpenFile` at `0x1800359af`
- `ntdll!RtlNtStatusToDosError` at `0x1800359d9`
- `ntdll!RtlNtStatusToDosError` at `0x1800359d9`
- `ntdll!RtlInitUnicodeString` at `0x18003595c`
- `ntdll!RtlInitUnicodeString` at `0x18003595c`

## pseudocode

```c
ULONG __fastcall WitnessOpenRedirector(void **a1)
{
  int Status; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+98h] [rbp+18h] BYREF

  FileHandle = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\Device\\LanmanRedirector");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
    FileHandle = 0;
  else
    *a1 = FileHandle;
  return RtlNtStatusToDosError(Status);
}

```

## disassembly

```asm
0x18003591c  mov     [rsp-8+arg_0], rbx
0x180035921  push    rbp
0x180035922  mov     rbp, rsp
0x180035925  sub     rsp, 80h
0x18003592c  xorps   xmm0, xmm0
0x18003592f  mov     [rbp+FileHandle], 0
0x180035937  mov     rbx, rcx
0x18003593a  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x180035941  xorps   xmm1, xmm1
0x180035944  lea     rcx, [rbp+DestinationString]; DestinationString
0x180035948  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003594c  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180035950  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180035954  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180035958  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003595c  call    cs:__imp_RtlInitUnicodeString
0x180035963  nop     dword ptr [rax+rax+00h]
0x180035968  lea     rax, [rbp+DestinationString]
0x18003596c  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x180035974  xorps   xmm0, xmm0
0x180035977  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18003597b  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18003597f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180035986  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003598a  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180035992  mov     edx, 100000h; DesiredAccess
0x180035997  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18003599e  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800359a2  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x1800359aa  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800359af  call    cs:__imp_NtOpenFile
0x1800359b6  nop     dword ptr [rax+rax+00h]
0x1800359bb  mov     ecx, eax; Status
0x1800359bd  test    eax, eax
0x1800359bf  js      short loc_1800359D1
0x1800359c1  mov     ecx, dword ptr [rbp+IoStatusBlock]
0x1800359c4  test    ecx, ecx
0x1800359c6  js      short loc_1800359D1
0x1800359c8  mov     rax, [rbp+FileHandle]
0x1800359cc  mov     [rbx], rax
0x1800359cf  jmp     short loc_1800359D9
0x1800359d1  mov     [rbp+FileHandle], 0
0x1800359d9  call    cs:__imp_RtlNtStatusToDosError
0x1800359e0  nop     dword ptr [rax+rax+00h]
0x1800359e5  mov     rbx, [rsp+80h+arg_0]
0x1800359ed  add     rsp, 80h
0x1800359f4  pop     rbp
0x1800359f5  retn
```
