# WofOpenVolumeHandle

- ea: `0x14000f148`
- end: `0x14000f25a`
- name: `WofOpenVolumeHandle`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002eaa0`

## callees

- `0x14000f148`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000f236`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f236`
- `FLTMGR!FltCreateFileEx` at `0x14000f206`
- `FLTMGR!FltCreateFileEx` at `0x14000f206`
- `FLTMGR!FltClose` at `0x14000f21c`
- `FLTMGR!FltClose` at `0x14000f21c`

## pseudocode

```c
__int64 __fastcall WofOpenVolumeHandle(struct _UNICODE_STRING *a1, struct _FILE_OBJECT *a2, PFILE_OBJECT *a3)
{
  struct _FLT_INSTANCE *Buffer; // rdx
  NTSTATUS v5; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+D8h] [rbp+67h] BYREF
  PFILE_OBJECT FileObject; // [rsp+E0h] [rbp+6Fh] BYREF

  FileObject = a2;
  Buffer = (struct _FLT_INSTANCE *)a1[7].Buffer;
  FileHandle = 0;
  FileObject = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a1 + 4;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = FltCreateFileEx(
         WofGlobal,
         Buffer,
         &FileHandle,
         &FileObject,
         0x180u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0,
         7u,
         1u,
         0x20u,
         0,
         0,
         0);
  if ( v5 >= 0 )
  {
    FltClose(FileHandle);
    if ( a3 )
      *a3 = FileObject;
    else
      ObfDereferenceObject(FileObject);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000f148  mov     r11, rsp
0x14000f14b  mov     [r11+18h], rbx
0x14000f14f  mov     [r11+20h], rdi
0x14000f153  mov     [r11+10h], rdx
0x14000f157  push    rbp
0x14000f158  lea     rbp, [r11-5Fh]
0x14000f15c  sub     rsp, 0C0h
0x14000f163  mov     rdx, [rcx+78h]; Instance
0x14000f167  lea     r9, [rbp+57h+FileObject]; FileObject
0x14000f16b  mov     [rsp+0C0h+Flags], 0; Flags
0x14000f173  xor     eax, eax
0x14000f175  mov     [rsp+0C0h+EaLength], 0; EaLength
0x14000f17d  xorps   xmm0, xmm0
0x14000f180  mov     qword ptr [r11-68h], 0
0x14000f188  mov     rbx, r8
0x14000f18b  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x14000f193  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x14000f197  mov     [rsp+0C0h+CreateDisposition], 1; CreateDisposition
0x14000f19f  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x14000f1a7  mov     [rbp+57h+FileHandle], rax
0x14000f1ab  mov     [rbp+57h+FileObject], rax
0x14000f1af  mov     [rbp+57h+var_30.RootDirectory], rax
0x14000f1b3  lea     rax, [rcx+40h]
0x14000f1b7  mov     rcx, cs:WofGlobal; Filter
0x14000f1be  mov     [rsp+0C0h+FileAttributes], 0; FileAttributes
0x14000f1c6  mov     [rbp+57h+var_30.ObjectName], rax
0x14000f1ca  lea     rax, [rbp+57h+var_40]
0x14000f1ce  mov     [rsp+0C0h+AllocationSize], 0; AllocationSize
0x14000f1d7  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x14000f1dc  lea     rax, [rbp+57h+var_30]
0x14000f1e0  mov     [rsp+0C0h+ObjectAttributes], rax; ObjectAttributes
0x14000f1e5  mov     [rsp+0C0h+DesiredAccess], 180h; DesiredAccess
0x14000f1ed  mov     qword ptr [rbp+57h+var_30.Length], 30h ; '0'
0x14000f1f5  mov     qword ptr [rbp+57h+var_30.Attributes], 240h
0x14000f1fd  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x14000f201  movdqu  xmmword ptr [rbp+57h+var_30.SecurityDescriptor], xmm0
0x14000f206  call    cs:__imp_FltCreateFileEx
0x14000f20d  nop     dword ptr [rax+rax+00h]
0x14000f212  mov     edi, eax
0x14000f214  test    eax, eax
0x14000f216  js      short loc_14000F242
0x14000f218  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000f21c  call    cs:__imp_FltClose
0x14000f223  nop     dword ptr [rax+rax+00h]
0x14000f228  mov     rcx, [rbp+57h+FileObject]; Object
0x14000f22c  test    rbx, rbx
0x14000f22f  jz      short loc_14000F236
0x14000f231  mov     [rbx], rcx
0x14000f234  jmp     short loc_14000F242
0x14000f236  call    cs:__imp_ObfDereferenceObject
0x14000f23d  nop     dword ptr [rax+rax+00h]
0x14000f242  lea     r11, [rsp+0C0h+var_s0]
0x14000f24a  mov     eax, edi
0x14000f24c  mov     rbx, [r11+20h]
0x14000f250  mov     rdi, [r11+28h]
0x14000f254  mov     rsp, r11
0x14000f257  pop     rbp
0x14000f258  retn
```
