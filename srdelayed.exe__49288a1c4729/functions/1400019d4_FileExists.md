# FileExists

- ea: `0x1400019d4`
- end: `0x140001aad`
- name: `FileExists`
- size: `217`
- prototype: `bool __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400020dc`

## callees

- `0x1400019d4`
- `0x140003770`

## import_xrefs

- `ntdll!NtClose` at `0x140001a82`
- `ntdll!NtClose` at `0x140001a82`
- `ntdll!NtQueryInformationFile` at `0x140001a71`
- `ntdll!NtQueryInformationFile` at `0x140001a71`
- `ntdll!NtOpenFile` at `0x140001a4b`
- `ntdll!NtOpenFile` at `0x140001a4b`

## pseudocode

```c
bool __fastcall FileExists(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // ebx
  void *FileHandle; // [rsp+30h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-11h] BYREF
  _OWORD FileInformation[2]; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v7; // [rsp+98h] [rbp+3Fh]

  ObjectAttributes.ObjectName = a1;
  v7 = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(FileInformation, 0, sizeof(FileInformation));
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
  if ( v1 >= 0 )
    v1 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
  if ( FileHandle )
    NtClose(FileHandle);
  return v1 >= 0;
}

```

## disassembly

```asm
0x1400019d4  mov     [rsp-8+arg_8], rbx
0x1400019d9  push    rbp
0x1400019da  lea     rbp, [rsp-57h]
0x1400019df  sub     rsp, 0B0h
0x1400019e6  mov     rax, cs:__security_cookie
0x1400019ed  xor     rax, rsp
0x1400019f0  mov     [rbp+57h+var_10], rax
0x1400019f4  xorps   xmm0, xmm0
0x1400019f7  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x1400019fb  xor     eax, eax
0x1400019fd  mov     [rsp+0B0h+OpenOptions], 204020h; OpenOptions
0x140001a05  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140001a09  mov     [rbp+57h+var_18], rax
0x140001a0d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140001a11  mov     [rbp+57h+FileHandle], rax
0x140001a15  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140001a19  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140001a1d  mov     edx, 100080h; DesiredAccess
0x140001a22  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140001a2a  movups  [rbp+57h+FileInformation], xmm0
0x140001a2e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140001a36  movups  [rbp+57h+var_28], xmm0
0x140001a3a  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x140001a42  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140001a46  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140001a4b  call    cs:__imp_NtOpenFile
0x140001a51  mov     ebx, eax
0x140001a53  test    eax, eax
0x140001a55  js      short loc_140001A79
0x140001a57  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140001a5b  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140001a5f  mov     r9d, 28h ; '('; Length
0x140001a65  mov     [rsp+0B0h+ShareAccess], 4; FileInformationClass
0x140001a6d  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140001a71  call    cs:__imp_NtQueryInformationFile
0x140001a77  mov     ebx, eax
0x140001a79  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140001a7d  test    rcx, rcx
0x140001a80  jz      short loc_140001A88
0x140001a82  call    cs:__imp_NtClose
0x140001a88  shr     ebx, 1Fh
0x140001a8b  xor     bl, 1
0x140001a8e  mov     al, bl
0x140001a90  mov     rcx, [rbp+57h+var_10]
0x140001a94  xor     rcx, rsp; StackCookie
0x140001a97  call    __security_check_cookie
0x140001a9c  mov     rbx, [rsp+0B0h+arg_8]
0x140001aa4  add     rsp, 0B0h
0x140001aab  pop     rbp
0x140001aac  retn
```
