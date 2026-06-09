# QueryVolumeId(ushort const *,CVolumeId *)

- ea: `0x1800031e8`
- end: `0x180003314`
- name: `?QueryVolumeId@@YAJPEBGPEAUCVolumeId@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CVolumeId *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002488`

## callees

- `0x1800031e8`
- `0x18000331c`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800032ab`
- `ntdll!NtCreateFile` at `0x1800032ab`
- `ntdll!RtlFreeHeap` at `0x1800032ce`
- `ntdll!RtlFreeHeap` at `0x1800032ce`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180003228`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180003228`
- `ntdll!NtClose` at `0x1800032ef`
- `ntdll!NtClose` at `0x1800032ef`

## pseudocode

```c
__int64 __fastcall QueryVolumeId(const unsigned __int16 *a1, struct CVolumeId *a2)
{
  PWSTR Buffer; // rdi
  NTSTATUS VolumeId; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+77h] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  NtPathName = 0;
  if ( RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    Buffer = NtPathName.Buffer;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &NtPathName;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    VolumeId = NtCreateFile(
                 &FileHandle,
                 0x100080u,
                 &ObjectAttributes,
                 &IoStatusBlock,
                 0,
                 0x80u,
                 7u,
                 1u,
                 0x400020u,
                 0,
                 0);
    if ( VolumeId < 0 )
      FileHandle = 0;
    if ( Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( VolumeId >= 0 )
    {
      VolumeId = QueryVolumeId(FileHandle, a2);
      if ( FileHandle )
        NtClose(FileHandle);
    }
  }
  else
  {
    return (unsigned int)-1073741773;
  }
  return (unsigned int)VolumeId;
}

```

## disassembly

```asm
0x1800031e8  push    rbp
0x1800031ea  push    rbx
0x1800031eb  push    rsi
0x1800031ec  push    rdi
0x1800031ed  lea     rbp, [rsp-3Fh]
0x1800031f2  sub     rsp, 0B8h
0x1800031f9  xorps   xmm0, xmm0
0x1800031fc  mov     [rbp+57h+FileHandle], 0
0x180003204  mov     rsi, rdx
0x180003207  xorps   xmm1, xmm1
0x18000320a  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18000320e  xor     r9d, r9d; DirectoryInfo
0x180003211  xor     r8d, r8d; NtFileNamePart
0x180003214  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180003218  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000321c  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003220  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180003224  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm1
0x180003228  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000322e  test    al, al
0x180003230  jz      loc_18000330D
0x180003236  mov     rdi, [rbp+57h+NtPathName.Buffer]
0x18000323a  lea     rax, [rbp+57h+NtPathName]
0x18000323e  mov     [rsp+0D0h+EaLength], 0; EaLength
0x180003246  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000324a  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x180003253  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180003257  mov     [rsp+0D0h+CreateOptions], 400020h; CreateOptions
0x18000325f  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180003263  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x18000326b  xorps   xmm0, xmm0
0x18000326e  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x180003276  mov     edx, 100080h; DesiredAccess
0x18000327b  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x180003283  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x18000328c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180003293  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000329b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800032a2  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800032a6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800032ab  call    cs:__imp_NtCreateFile
0x1800032b1  mov     ebx, eax
0x1800032b3  test    eax, eax
0x1800032b5  js      short loc_180003303
0x1800032b7  test    rdi, rdi
0x1800032ba  jz      short loc_1800032D4
0x1800032bc  mov     rcx, gs:60h
0x1800032c5  mov     r8, rdi; P
0x1800032c8  xor     edx, edx; Flags
0x1800032ca  mov     rcx, [rcx+30h]; HeapHandle
0x1800032ce  call    cs:__imp_RtlFreeHeap
0x1800032d4  test    ebx, ebx
0x1800032d6  js      short loc_1800032F5
0x1800032d8  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800032dc  mov     rdx, rsi; struct CVolumeId *
0x1800032df  call    ?QueryVolumeId@@YAJQEAXPEAUCVolumeId@@@Z; QueryVolumeId(void * const,CVolumeId *)
0x1800032e4  mov     ebx, eax
0x1800032e6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800032ea  test    rcx, rcx
0x1800032ed  jz      short loc_1800032F5
0x1800032ef  call    cs:__imp_NtClose
0x1800032f5  mov     eax, ebx
0x1800032f7  add     rsp, 0B8h
0x1800032fe  pop     rdi
0x1800032ff  pop     rsi
0x180003300  pop     rbx
0x180003301  pop     rbp
0x180003302  retn
0x180003303  mov     [rbp+57h+FileHandle], 0
0x18000330b  jmp     short loc_1800032B7
0x18000330d  mov     ebx, 0C0000033h
0x180003312  jmp     short loc_1800032F5
```
