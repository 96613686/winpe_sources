# SmpDeletePagingFile

- ea: `0x1400107e8`
- end: `0x1400108c3`
- name: `SmpDeletePagingFile`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140009100`
- `0x14000f3ec`
- `0x14000f6f4`

## callees

- `0x14000d4c0`
- `0x1400107e8`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140010844`
- `ntdll!NtOpenFile` at `0x140010844`
- `ntdll!NtClose` at `0x1400108ad`
- `ntdll!NtClose` at `0x1400108ad`
- `ntdll!NtSetInformationFile` at `0x140010884`
- `ntdll!NtSetInformationFile` at `0x140010884`

## string_xrefs

- `0x140010853`: `SmpDeletePagingFile`
- `0x14001088c`: `SmpDeletePagingFile`

## pseudocode

```c
__int64 __fastcall SmpDeletePagingFile(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  NTSTATUS v2; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  char FileInformation; // [rsp+80h] [rbp+10h] BYREF
  void *FileHandle; // [rsp+88h] [rbp+18h] BYREF

  ObjectAttributes.ObjectName = a1;
  FileHandle = 0;
  FileInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = NtOpenFile(&FileHandle, 0x10000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x40u);
  v2 = v1;
  if ( v1 >= 0 )
  {
    FileInformation = 1;
    v2 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 1u, FileDispositionInformation);
    SmpLogFailure("SmpDeletePagingFile", ((v2 >> 31) & 4u) + 4017, (unsigned int)v2);
    NtClose(FileHandle);
  }
  else
  {
    SmpLogFailure("SmpDeletePagingFile", 4002, (unsigned int)v1);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400107e8  mov     [rsp-8+arg_10], rbx
0x1400107ed  push    rbp
0x1400107ee  mov     rbp, rsp
0x1400107f1  sub     rsp, 70h
0x1400107f5  xor     eax, eax
0x1400107f7  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x1400107fb  xorps   xmm0, xmm0
0x1400107fe  mov     [rbp+FileHandle], rax
0x140010802  mov     [rbp+FileInformation], al
0x140010805  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140010809  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14001080d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140010811  mov     eax, 40h ; '@'
0x140010816  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001081e  mov     [rsp+70h+OpenOptions], eax; OpenOptions
0x140010822  lea     rcx, [rbp+FileHandle]; FileHandle
0x140010826  mov     edx, 10000h; DesiredAccess
0x14001082b  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x140010833  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14001083b  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14001083f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140010844  call    cs:__imp_NtOpenFile
0x14001084a  mov     ebx, eax
0x14001084c  test    eax, eax
0x14001084e  jns     short loc_140010866
0x140010850  mov     r8d, eax
0x140010853  lea     rcx, aSmpdeletepagin; "SmpDeletePagingFile"
0x14001085a  mov     edx, 0FA2h
0x14001085f  call    SmpLogFailure
0x140010864  jmp     short loc_1400108B3
0x140010866  mov     rcx, [rbp+FileHandle]; FileHandle
0x14001086a  lea     r8, [rbp+FileInformation]; FileInformation
0x14001086e  mov     r9d, 1; Length
0x140010874  mov     [rbp+FileInformation], 1
0x140010878  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x14001087c  mov     [rsp+70h+ShareAccess], 0Dh; FileInformationClass
0x140010884  call    cs:__imp_NtSetInformationFile
0x14001088a  mov     edx, eax
0x14001088c  lea     rcx, aSmpdeletepagin; "SmpDeletePagingFile"
0x140010893  sar     edx, 1Fh
0x140010896  mov     r8d, eax
0x140010899  and     edx, 4
0x14001089c  mov     ebx, eax
0x14001089e  add     edx, 0FB1h
0x1400108a4  call    SmpLogFailure
0x1400108a9  mov     rcx, [rbp+FileHandle]; Handle
0x1400108ad  call    cs:__imp_NtClose
0x1400108b3  mov     eax, ebx
0x1400108b5  mov     rbx, [rsp+70h+arg_10]
0x1400108bd  add     rsp, 70h
0x1400108c1  pop     rbp
0x1400108c2  retn
```
