# OpenDevice

- ea: `0x18001ab48`
- end: `0x18001abc8`
- name: `OpenDevice`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a860`

## callees

- `0x18001ab48`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18001aba2`
- `ntdll!NtOpenFile` at `0x18001aba2`
- `ntdll!RtlNtStatusToDosError` at `0x18001abb8`
- `ntdll!RtlNtStatusToDosError` at `0x18001abb8`
- `KERNEL32!SetLastError` at `0x18001abc0`
- `KERNEL32!SetLastError` at `0x18001abc0`

## pseudocode

```c
void *__fastcall OpenDevice(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  ULONG v3; // eax
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
    v3 = RtlNtStatusToDosError(v1);
    SetLastError(v3);
  }
  return FileHandle;
}

```

## disassembly

```asm
0x18001ab48  push    rbp
0x18001ab4a  mov     rbp, rsp
0x18001ab4d  sub     rsp, 70h
0x18001ab51  xorps   xmm0, xmm0
0x18001ab54  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x18001ab58  lea     rcx, [rbp+FileHandle]; FileHandle
0x18001ab5c  mov     [rsp+70h+OpenOptions], 20h ; ' '; OpenOptions
0x18001ab64  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18001ab68  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001ab70  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001ab74  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001ab7c  mov     edx, 12019Fh; DesiredAccess
0x18001ab81  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001ab89  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001ab8e  mov     [rbp+FileHandle], 0
0x18001ab96  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18001ab9a  mov     [rsp+70h+ShareAccess], 7; ShareAccess
0x18001aba2  call    cs:__imp_NtOpenFile
0x18001aba8  test    eax, eax
0x18001abaa  jnz     short loc_18001ABB6
0x18001abac  mov     rax, [rbp+FileHandle]
0x18001abb0  add     rsp, 70h
0x18001abb4  pop     rbp
0x18001abb5  retn
0x18001abb6  mov     ecx, eax; Status
0x18001abb8  call    cs:__imp_RtlNtStatusToDosError
0x18001abbe  mov     ecx, eax; dwErrCode
0x18001abc0  call    cs:__imp_SetLastError
0x18001abc6  jmp     short loc_18001ABAC
```
