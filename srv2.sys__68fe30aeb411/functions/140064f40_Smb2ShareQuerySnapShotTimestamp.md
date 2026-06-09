# Smb2ShareQuerySnapShotTimestamp

- ea: `0x140064f40`
- end: `0x140065025`
- name: `Smb2ShareQuerySnapShotTimestamp`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400644a4`

## callees

- `0x140038490`
- `0x140064f40`
- `0x1400654f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140064ff5`
- `ntoskrnl!ZwClose` at `0x140064ff5`
- `ntoskrnl!NtOpenFile` at `0x140064fbe`
- `ntoskrnl!NtOpenFile` at `0x140064fbe`

## pseudocode

```c
NTSTATUS __fastcall Smb2ShareQuerySnapShotTimestamp(struct _UNICODE_STRING *a1, _QWORD *a2)
{
  NTSTATUS result; // eax
  int v4; // ebx
  ULONG v5; // [rsp+30h] [rbp-19h] BYREF
  void *FileHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+27h] BYREF
  __int128 v9; // [rsp+80h] [rbp+37h] BYREF

  ObjectAttributes.ObjectName = a1;
  FileHandle = 0;
  v5 = 16;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  v9 = 0;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenFile(&FileHandle, 0, &ObjectAttributes, &IoStatusBlock, 7u, 0);
  if ( result >= 0 )
  {
    v4 = Smb2SnapIssueIoctl(FileHandle, 0x530194u, (struct _IRP *)&v9, &v5);
    if ( v4 >= 0 )
      *a2 = *((_QWORD *)&v9 + 1);
    ZwClose(FileHandle);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x140064f40  mov     [rsp-8+arg_10], rbx
0x140064f45  mov     [rsp-8+arg_18], rdi
0x140064f4a  push    rbp
0x140064f4b  lea     rbp, [rsp-57h]
0x140064f50  sub     rsp, 0A0h
0x140064f57  mov     rax, cs:__security_cookie
0x140064f5e  xor     rax, rsp
0x140064f61  mov     [rbp+57h+var_10], rax
0x140064f65  xor     eax, eax
0x140064f67  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x140064f6b  xorps   xmm0, xmm0
0x140064f6e  mov     [rsp+0A0h+OpenOptions], eax; OpenOptions
0x140064f72  mov     rdi, rdx
0x140064f75  mov     [rsp+0A0h+ShareAccess], 7; ShareAccess
0x140064f7d  xorps   xmm1, xmm1
0x140064f80  mov     [rbp+57h+FileHandle], 0
0x140064f88  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140064f8c  mov     [rbp+57h+var_70], 10h
0x140064f93  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140064f97  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140064f9f  xor     edx, edx; DesiredAccess
0x140064fa1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140064fa9  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140064fad  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140064fb1  movups  [rbp+57h+var_20], xmm0
0x140064fb5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x140064fb9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140064fbe  call    cs:__imp_NtOpenFile
0x140064fc5  nop     dword ptr [rax+rax+00h]
0x140064fca  test    eax, eax
0x140064fcc  js      short loc_140065003
0x140064fce  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140064fd2  lea     r9, [rbp+57h+var_70]
0x140064fd6  lea     r8, [rbp+57h+var_20]
0x140064fda  mov     edx, 530194h
0x140064fdf  call    Smb2SnapIssueIoctl
0x140064fe4  mov     ebx, eax
0x140064fe6  test    eax, eax
0x140064fe8  js      short loc_140064FF1
0x140064fea  mov     rcx, qword ptr [rbp+57h+var_20+8]
0x140064fee  mov     [rdi], rcx
0x140064ff1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140064ff5  call    cs:__imp_ZwClose
0x140064ffc  nop     dword ptr [rax+rax+00h]
0x140065001  mov     eax, ebx
0x140065003  mov     rcx, [rbp+57h+var_10]
0x140065007  xor     rcx, rsp; StackCookie
0x14006500a  call    __security_check_cookie
0x14006500f  lea     r11, [rsp+0A0h+var_s0]
0x140065017  mov     rbx, [r11+20h]
0x14006501b  mov     rdi, [r11+28h]
0x14006501f  mov     rsp, r11
0x140065022  pop     rbp
0x140065023  retn
```
