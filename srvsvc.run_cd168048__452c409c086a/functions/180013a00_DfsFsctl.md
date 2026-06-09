# DfsFsctl

- ea: `0x180013a00`
- end: `0x180013b36`
- name: `DfsFsctl`
- size: `310`
- prototype: `__int64 __fastcall(ULONG FsControlCode, PVOID InputBuffer, ULONG InputBufferLength)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015500`
- `0x1800216f0`

## callees

- `0x180013a00`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180013abd`
- `ntdll!NtCreateFile` at `0x180013abd`
- `ntdll!NtFsControlFile` at `0x180013b0c`
- `ntdll!NtFsControlFile` at `0x180013b0c`
- `ntdll!NtClose` at `0x180013b1e`
- `ntdll!NtClose` at `0x180013b1e`
- `RPCRT4!RpcImpersonateClient` at `0x180013a6f`
- `RPCRT4!RpcImpersonateClient` at `0x180013a6f`
- `RPCRT4!RpcRevertToSelf` at `0x180013ace`
- `RPCRT4!RpcRevertToSelf` at `0x180013ace`

## pseudocode

```c
RPC_STATUS __fastcall DfsFsctl(ULONG FsControlCode, PVOID InputBuffer, ULONG InputBufferLength)
{
  RPC_STATUS result; // eax
  NTSTATUS Status; // ebx
  _QWORD v8[2]; // [rsp+60h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-11h] BYREF
  void *FileHandle; // [rsp+108h] [rbp+77h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v8[1] = L"\\DfsServer";
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v8;
  FileHandle = 0;
  v8[0] = 1441812;
  IoStatusBlock = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( !dword_18005CE2C || (result = RpcImpersonateClient(0)) == 0 )
  {
    Status = NtCreateFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 3u, 0xA0u, 0, 0);
    if ( dword_18005CE2C )
      RpcRevertToSelf();
    if ( Status >= 0 )
    {
      Status = IoStatusBlock.Status;
      if ( IoStatusBlock.Status >= 0 )
      {
        Status = NtFsControlFile(
                   FileHandle,
                   0,
                   0,
                   0,
                   &IoStatusBlock,
                   FsControlCode,
                   InputBuffer,
                   InputBufferLength,
                   0,
                   0);
        if ( Status >= 0 )
          Status = IoStatusBlock.Status;
        NtClose(FileHandle);
      }
    }
    return Status;
  }
  return result;
}

```

## disassembly

```asm
0x180013a00  mov     [rsp-8+FileHandle], r9
0x180013a05  push    rbp
0x180013a06  push    rbx
0x180013a07  push    rsi
0x180013a08  push    rdi
0x180013a09  push    r14
0x180013a0b  push    r15
0x180013a0d  lea     rbp, [rsp-27h]
0x180013a12  sub     rsp, 0B8h
0x180013a19  xor     r15d, r15d
0x180013a1c  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180013a24  cmp     cs:dword_18005CE2C, r15d
0x180013a2b  lea     rax, aDfsserver; "\\DfsServer"
0x180013a32  xorps   xmm0, xmm0
0x180013a35  mov     [rbp+4Fh+var_78], rax
0x180013a39  lea     rax, [rbp+4Fh+var_80]
0x180013a3d  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180013a45  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x180013a49  mov     edi, r8d
0x180013a4c  mov     rsi, rdx
0x180013a4f  mov     [rbp+4Fh+FileHandle], r15
0x180013a53  mov     r14d, ecx
0x180013a56  mov     [rbp+4Fh+var_80], 160014h
0x180013a5e  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x180013a62  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r15
0x180013a66  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180013a6b  jz      short loc_180013A7D
0x180013a6d  xor     ecx, ecx; BindingHandle
0x180013a6f  call    cs:__imp_RpcImpersonateClient
0x180013a75  test    eax, eax
0x180013a77  jnz     loc_180013B26
0x180013a7d  mov     [rsp+0E0h+EaLength], r15d; EaLength
0x180013a82  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180013a86  mov     [rsp+0E0h+EaBuffer], r15; EaBuffer
0x180013a8b  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180013a8f  mov     [rsp+0E0h+CreateOptions], 0A0h; CreateOptions
0x180013a97  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180013a9b  mov     [rsp+0E0h+CreateDisposition], 3; CreateDisposition
0x180013aa3  mov     edx, 100002h; DesiredAccess
0x180013aa8  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180013ab0  mov     [rsp+0E0h+FileAttributes], 80h; FileAttributes
0x180013ab8  mov     [rsp+0E0h+AllocationSize], r15; AllocationSize
0x180013abd  call    cs:__imp_NtCreateFile
0x180013ac3  cmp     cs:dword_18005CE2C, r15d
0x180013aca  mov     ebx, eax
0x180013acc  jz      short loc_180013AD4
0x180013ace  call    cs:__imp_RpcRevertToSelf
0x180013ad4  test    ebx, ebx
0x180013ad6  js      short loc_180013B24
0x180013ad8  mov     ebx, dword ptr [rbp+4Fh+IoStatusBlock]
0x180013adb  test    ebx, ebx
0x180013add  js      short loc_180013B24
0x180013adf  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180013ae3  lea     rax, [rbp+4Fh+IoStatusBlock]
0x180013ae7  mov     dword ptr [rsp+0E0h+EaBuffer], r15d; OutputBufferLength
0x180013aec  xor     r9d, r9d; ApcContext
0x180013aef  mov     qword ptr [rsp+0E0h+CreateOptions], r15; OutputBuffer
0x180013af4  xor     r8d, r8d; ApcRoutine
0x180013af7  mov     [rsp+0E0h+CreateDisposition], edi; InputBufferLength
0x180013afb  xor     edx, edx; Event
0x180013afd  mov     qword ptr [rsp+0E0h+ShareAccess], rsi; InputBuffer
0x180013b02  mov     [rsp+0E0h+FileAttributes], r14d; FsControlCode
0x180013b07  mov     [rsp+0E0h+AllocationSize], rax; IoStatusBlock
0x180013b0c  call    cs:__imp_NtFsControlFile
0x180013b12  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180013b16  test    eax, eax
0x180013b18  mov     ebx, eax
0x180013b1a  cmovns  ebx, dword ptr [rbp+4Fh+IoStatusBlock]
0x180013b1e  call    cs:__imp_NtClose
0x180013b24  mov     eax, ebx
0x180013b26  add     rsp, 0B8h
0x180013b2d  pop     r15
0x180013b2f  pop     r14
0x180013b31  pop     rdi
0x180013b32  pop     rsi
0x180013b33  pop     rbx
0x180013b34  pop     rbp
0x180013b35  retn
```
