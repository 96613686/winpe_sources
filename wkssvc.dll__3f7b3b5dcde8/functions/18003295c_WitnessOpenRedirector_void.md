# WitnessOpenRedirector(void * *)

- ea: `0x18003295c`
- end: `0x180032a24`
- name: `?WitnessOpenRedirector@@YAKPEAPEAX@Z`
- size: `200`
- prototype: `ULONG __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c308`

## callees

- `0x18003295c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800329e9`
- `ntdll!NtOpenFile` at `0x1800329e9`
- `ntdll!RtlNtStatusToDosError` at `0x180032a0d`
- `ntdll!RtlNtStatusToDosError` at `0x180032a0d`
- `ntdll!RtlInitUnicodeString` at `0x18003299c`
- `ntdll!RtlInitUnicodeString` at `0x18003299c`

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
0x18003295c  mov     [rsp-8+arg_0], rbx
0x180032961  push    rbp
0x180032962  mov     rbp, rsp
0x180032965  sub     rsp, 80h
0x18003296c  xorps   xmm0, xmm0
0x18003296f  mov     [rbp+FileHandle], 0
0x180032977  mov     rbx, rcx
0x18003297a  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x180032981  xorps   xmm1, xmm1
0x180032984  lea     rcx, [rbp+DestinationString]; DestinationString
0x180032988  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003298c  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180032990  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180032994  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180032998  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003299c  call    cs:__imp_RtlInitUnicodeString
0x1800329a2  lea     rax, [rbp+DestinationString]
0x1800329a6  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x1800329ae  xorps   xmm0, xmm0
0x1800329b1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800329b5  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800329b9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800329c0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800329c4  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800329cc  mov     edx, 100000h; DesiredAccess
0x1800329d1  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800329d8  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800329dc  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x1800329e4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800329e9  call    cs:__imp_NtOpenFile
0x1800329ef  mov     ecx, eax; Status
0x1800329f1  test    eax, eax
0x1800329f3  js      short loc_180032A05
0x1800329f5  mov     ecx, dword ptr [rbp+IoStatusBlock]
0x1800329f8  test    ecx, ecx
0x1800329fa  js      short loc_180032A05
0x1800329fc  mov     rax, [rbp+FileHandle]
0x180032a00  mov     [rbx], rax
0x180032a03  jmp     short loc_180032A0D
0x180032a05  mov     [rbp+FileHandle], 0
0x180032a0d  call    cs:__imp_RtlNtStatusToDosError
0x180032a13  mov     rbx, [rsp+80h+arg_0]
0x180032a1b  add     rsp, 80h
0x180032a22  pop     rbp
0x180032a23  retn
```
