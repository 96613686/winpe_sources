# OpenDevice

- ea: `0x180052f80`
- end: `0x180052ffe`
- name: `OpenDevice`
- size: `126`
- prototype: `void *__fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180052e04`

## callees

- `0x180052f80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052fee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052fee`
- `ntdll!RtlNtStatusToDosError` at `0x180052fe6`
- `ntdll!RtlNtStatusToDosError` at `0x180052fe6`
- `ntdll!NtOpenFile` at `0x180052fda`
- `ntdll!NtOpenFile` at `0x180052fda`

## pseudocode

```c
void *__fastcall OpenDevice(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  DWORD v2; // eax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+80h] [rbp+10h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  v1 = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v1 )
  {
    v2 = RtlNtStatusToDosError(v1);
    SetLastError(v2);
  }
  return FileHandle;
}

```

## disassembly

```asm
0x180052f80  push    rbp
0x180052f82  mov     rbp, rsp
0x180052f85  sub     rsp, 70h
0x180052f89  xorps   xmm0, xmm0
0x180052f8c  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x180052f90  lea     rcx, [rbp+FileHandle]; FileHandle
0x180052f94  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x180052f9c  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180052fa0  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180052fa8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180052fac  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180052fb4  mov     edx, 12019Fh; DesiredAccess
0x180052fb9  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180052fc1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180052fc6  mov     [rbp+FileHandle], 0
0x180052fce  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180052fd2  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x180052fda  call    cs:__imp_NtOpenFile
0x180052fe0  test    eax, eax
0x180052fe2  jz      short loc_180052FF4
0x180052fe4  mov     ecx, eax; Status
0x180052fe6  call    cs:__imp_RtlNtStatusToDosError
0x180052fec  mov     ecx, eax; dwErrCode
0x180052fee  call    cs:__imp_SetLastError
0x180052ff4  mov     rax, [rbp+FileHandle]
0x180052ff8  add     rsp, 70h
0x180052ffc  pop     rbp
0x180052ffd  retn
```
