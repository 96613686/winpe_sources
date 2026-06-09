# SmpQuerySameVolume

- ea: `0x140012320`
- end: `0x1400124b2`
- name: `SmpQuerySameVolume`
- size: `402`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011d24`
- `0x1400127a8`

## callees

- `0x140012320`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1400123f3`
- `ntdll!NtOpenFile` at `0x1400123f3`
- `ntdll!NtClose` at `0x140012481`
- `ntdll!NtClose` at `0x140012481`
- `ntdll!NtQueryVolumeInformationFile` at `0x14001239b`
- `ntdll!NtQueryVolumeInformationFile` at `0x140012474`
- `ntdll!NtQueryVolumeInformationFile` at `0x14001239b`
- `ntdll!NtQueryVolumeInformationFile` at `0x140012474`
- `ntdll!NtCreateFile` at `0x14001244e`
- `ntdll!NtCreateFile` at `0x14001244e`

## pseudocode

```c
NTSTATUS __fastcall SmpQuerySameVolume(HANDLE FileHandle, struct _UNICODE_STRING *a2, bool *a3)
{
  NTSTATUS result; // eax
  int v7; // edi
  NTSTATUS v8; // ebx
  void *FileHandlea; // [rsp+60h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  _BYTE FsInformation[8]; // [rsp+B0h] [rbp-50h] BYREF
  int v13; // [rsp+B8h] [rbp-48h]

  FileHandlea = 0;
  memset_0(FsInformation, 0, 0xE0u);
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  result = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0xE0u, FileFsVolumeInformation);
  if ( result >= 0 )
  {
    v7 = v13;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.ObjectName = a2;
    result = NtOpenFile(&FileHandlea, 0x100000u, &ObjectAttributes, &IoStatusBlock, 3u, 0x60u);
    if ( result == -1073741772 )
      result = NtCreateFile(&FileHandlea, 0x110000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 2u, 0x1060u, 0, 0);
    if ( result >= 0 )
    {
      v8 = NtQueryVolumeInformationFile(FileHandlea, &IoStatusBlock, FsInformation, 0xE0u, FileFsVolumeInformation);
      NtClose(FileHandlea);
      if ( v8 >= 0 )
        *a3 = v7 == v13;
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012320  push    rbp
0x140012322  push    rbx
0x140012323  push    rsi
0x140012324  push    rdi
0x140012325  push    r14
0x140012327  lea     rbp, [rsp-0A0h]
0x14001232f  sub     rsp, 1A0h
0x140012336  mov     rax, cs:__security_cookie
0x14001233d  xor     rax, rsp
0x140012340  mov     [rbp+0C0h+var_30], rax
0x140012347  mov     rsi, r8
0x14001234a  mov     [rsp+1C0h+FileHandle], 0
0x140012353  mov     r14, rdx
0x140012356  mov     rbx, rcx
0x140012359  xor     edx, edx; Val
0x14001235b  lea     rcx, [rbp+0C0h+FsInformation]; void *
0x14001235f  mov     r8d, 0E0h; Size
0x140012365  call    memset_0
0x14001236a  xorps   xmm0, xmm0
0x14001236d  mov     [rsp+1C0h+FsInformationClass], 1; FsInformationClass
0x140012375  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x140012379  xor     eax, eax
0x14001237b  lea     r8, [rbp+0C0h+FsInformation]; FsInformation
0x14001237f  mov     r9d, 0E0h; Length
0x140012385  lea     rdx, [rsp+1C0h+IoStatusBlock]; IoStatusBlock
0x14001238a  mov     rcx, rbx; FileHandle
0x14001238d  movups  xmmword ptr [rbp+0C0h+ObjectAttributes+1Ch], xmm0
0x140012391  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.Length], xmm0
0x140012396  movups  xmmword ptr [rsp+1C0h+IoStatusBlock], xmm0
0x14001239b  call    cs:__imp_NtQueryVolumeInformationFile
0x1400123a1  test    eax, eax
0x1400123a3  js      loc_140012495
0x1400123a9  mov     edi, [rbp+0C0h+var_108]
0x1400123ac  lea     r9, [rsp+1C0h+IoStatusBlock]; IoStatusBlock
0x1400123b1  xorps   xmm0, xmm0
0x1400123b4  mov     [rsp+1C0h+OpenOptions], 60h ; '`'; OpenOptions
0x1400123bc  lea     r8, [rsp+1C0h+ObjectAttributes]; ObjectAttributes
0x1400123c1  mov     [rsp+1C0h+ObjectAttributes.Length], 30h ; '0'
0x1400123c9  mov     edx, 100000h; DesiredAccess
0x1400123ce  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], 0
0x1400123d6  lea     rcx, [rsp+1C0h+FileHandle]; FileHandle
0x1400123db  mov     [rbp+0C0h+ObjectAttributes.Attributes], 40h ; '@'
0x1400123e2  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400123e7  mov     [rbp+0C0h+ObjectAttributes.ObjectName], r14
0x1400123eb  mov     [rsp+1C0h+FsInformationClass], 3; ShareAccess
0x1400123f3  call    cs:__imp_NtOpenFile
0x1400123f9  cmp     eax, 0C0000034h
0x1400123fe  jnz     short loc_140012454
0x140012400  mov     [rsp+1C0h+EaLength], 0; EaLength
0x140012408  lea     r9, [rsp+1C0h+IoStatusBlock]; IoStatusBlock
0x14001240d  mov     [rsp+1C0h+EaBuffer], 0; EaBuffer
0x140012416  lea     r8, [rsp+1C0h+ObjectAttributes]; ObjectAttributes
0x14001241b  mov     [rsp+1C0h+CreateOptions], 1060h; CreateOptions
0x140012423  lea     rcx, [rsp+1C0h+FileHandle]; FileHandle
0x140012428  mov     [rsp+1C0h+CreateDisposition], 2; CreateDisposition
0x140012430  mov     edx, 110000h; DesiredAccess
0x140012435  mov     [rsp+1C0h+ShareAccess], 0; ShareAccess
0x14001243d  mov     [rsp+1C0h+OpenOptions], 80h; FileAttributes
0x140012445  mov     qword ptr [rsp+1C0h+FsInformationClass], 0; AllocationSize
0x14001244e  call    cs:__imp_NtCreateFile
0x140012454  test    eax, eax
0x140012456  js      short loc_140012495
0x140012458  mov     rcx, [rsp+1C0h+FileHandle]; FileHandle
0x14001245d  lea     r8, [rbp+0C0h+FsInformation]; FsInformation
0x140012461  mov     r9d, 0E0h; Length
0x140012467  mov     [rsp+1C0h+FsInformationClass], 1; FsInformationClass
0x14001246f  lea     rdx, [rsp+1C0h+IoStatusBlock]; IoStatusBlock
0x140012474  call    cs:__imp_NtQueryVolumeInformationFile
0x14001247a  mov     rcx, [rsp+1C0h+FileHandle]; Handle
0x14001247f  mov     ebx, eax
0x140012481  call    cs:__imp_NtClose
0x140012487  test    ebx, ebx
0x140012489  js      short loc_140012493
0x14001248b  cmp     edi, [rbp+0C0h+var_108]
0x14001248e  setz    al
0x140012491  mov     [rsi], al
0x140012493  mov     eax, ebx
0x140012495  mov     rcx, [rbp+0C0h+var_30]
0x14001249c  xor     rcx, rsp; StackCookie
0x14001249f  call    __security_check_cookie
0x1400124a4  add     rsp, 1A0h
0x1400124ab  pop     r14
0x1400124ad  pop     rdi
0x1400124ae  pop     rsi
0x1400124af  pop     rbx
0x1400124b0  pop     rbp
0x1400124b1  retn
```
