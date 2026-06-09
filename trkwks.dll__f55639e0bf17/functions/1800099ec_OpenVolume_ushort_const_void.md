# OpenVolume(ushort const *,void * *)

- ea: `0x1800099ec`
- end: `0x180009b9d`
- name: `?OpenVolume@@YAJPEBGPEAPEAX@Z`
- size: `433`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000756c`
- `0x180009364`
- `0x1800098bc`

## callees

- `0x1800099ec`
- `0x180009ba4`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180009ac7`
- `ntdll!NtCreateFile` at `0x180009ac7`
- `ntdll!RtlFreeHeap` at `0x180009aee`
- `ntdll!RtlFreeHeap` at `0x180009aee`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180009a44`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180009a44`
- `ntdll!NtQueryVolumeInformationFile` at `0x180009b12`
- `ntdll!NtQueryVolumeInformationFile` at `0x180009b12`
- `ntdll!NtClose` at `0x180009b1e`
- `ntdll!NtClose` at `0x180009b1e`

## pseudocode

```c
__int64 __fastcall OpenVolume(const unsigned __int16 *a1, void **a2)
{
  PWSTR Buffer; // rdi
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK v9; // [rsp+80h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+17h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+77h] BYREF
  __int64 FsInformation; // [rsp+F8h] [rbp+7Fh] BYREF

  FsInformation = 0;
  FileHandle = 0;
  v9 = 0;
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
    v5 = NtCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x20u, 0, 0);
    if ( v5 < 0 )
      FileHandle = 0;
    if ( Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( v5 >= 0 )
    {
      v5 = NtQueryVolumeInformationFile(FileHandle, &v9, &FsInformation, 8u, FileFsDeviceInformation);
      NtClose(FileHandle);
      if ( v5 >= 0 )
      {
        if ( (FsInformation & 0x2000000000LL) != 0 )
          return (unsigned int)TrkCreateFile(a1, 0x180u, 0x80u, 7u, 1u, 0x20u, 0, a2);
        else
          return (unsigned int)-1073741202;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741773;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800099ec  mov     [rsp-8+arg_0], rbx
0x1800099f1  mov     [rsp-8+arg_8], rsi
0x1800099f6  push    rbp
0x1800099f7  push    rdi
0x1800099f8  push    r14
0x1800099fa  lea     rbp, [rsp-47h]
0x1800099ff  sub     rsp, 0C0h
0x180009a06  xorps   xmm1, xmm1
0x180009a09  mov     [rbp+57h+FsInformation], 0
0x180009a11  xorps   xmm0, xmm0
0x180009a14  mov     [rbp+57h+FileHandle], 0
0x180009a1c  mov     r14, rdx
0x180009a1f  xor     r9d, r9d; DirectoryInfo
0x180009a22  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180009a26  xor     r8d, r8d; NtFileNamePart
0x180009a29  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180009a2d  mov     rsi, rcx
0x180009a30  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180009a34  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x180009a38  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180009a3c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180009a40  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm1
0x180009a44  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180009a4a  test    al, al
0x180009a4c  jz      loc_180009B8F
0x180009a52  mov     rdi, [rbp+57h+NtPathName.Buffer]
0x180009a56  lea     rax, [rbp+57h+NtPathName]
0x180009a5a  mov     [rsp+0D0h+EaLength], 0; EaLength
0x180009a62  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180009a66  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x180009a6f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180009a73  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x180009a7b  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180009a7f  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x180009a87  xorps   xmm0, xmm0
0x180009a8a  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x180009a92  mov     edx, 100080h; DesiredAccess
0x180009a97  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x180009a9f  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x180009aa8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180009aaf  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180009ab7  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180009abe  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180009ac2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180009ac7  call    cs:__imp_NtCreateFile
0x180009acd  mov     ebx, eax
0x180009acf  test    eax, eax
0x180009ad1  js      loc_180009B82
0x180009ad7  test    rdi, rdi
0x180009ada  jz      short loc_180009AF4
0x180009adc  mov     rcx, gs:60h
0x180009ae5  mov     r8, rdi; P
0x180009ae8  xor     edx, edx; Flags
0x180009aea  mov     rcx, [rcx+30h]; HeapHandle
0x180009aee  call    cs:__imp_RtlFreeHeap
0x180009af4  test    ebx, ebx
0x180009af6  js      short loc_180009B68
0x180009af8  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180009afc  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x180009b00  mov     r9d, 8; Length
0x180009b06  mov     dword ptr [rsp+0D0h+AllocationSize], 4; FsInformationClass
0x180009b0e  lea     rdx, [rbp+57h+var_50]; IoStatusBlock
0x180009b12  call    cs:__imp_NtQueryVolumeInformationFile
0x180009b18  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180009b1c  mov     ebx, eax
0x180009b1e  call    cs:__imp_NtClose
0x180009b24  test    ebx, ebx
0x180009b26  js      short loc_180009B68
0x180009b28  test    byte ptr [rbp+57h+FsInformation+4], 20h
0x180009b2f  jz      short loc_180009B96
0x180009b31  mov     qword ptr [rsp+0D0h+CreateDisposition], r14; void **
0x180009b36  mov     r9d, 7; unsigned int
0x180009b3c  mov     qword ptr [rsp+0D0h+ShareAccess], 0; struct _SECURITY_ATTRIBUTES *
0x180009b45  mov     edx, 180h; unsigned int
0x180009b4a  mov     [rsp+0D0h+FileAttributes], 20h ; ' '; unsigned int
0x180009b52  mov     rcx, rsi; unsigned __int16 *
0x180009b55  mov     dword ptr [rsp+0D0h+AllocationSize], 1; unsigned int
0x180009b5d  lea     r8d, [r9+79h]; unsigned int
0x180009b61  call    ?TrkCreateFile@@YAJPEBGKKKKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAX@Z; TrkCreateFile(ushort const *,ulong,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *)
0x180009b66  mov     ebx, eax
0x180009b68  lea     r11, [rsp+0D0h+var_10]
0x180009b70  mov     eax, ebx
0x180009b72  mov     rbx, [r11+20h]
0x180009b76  mov     rsi, [r11+28h]
0x180009b7a  mov     rsp, r11
0x180009b7d  pop     r14
0x180009b7f  pop     rdi
0x180009b80  pop     rbp
0x180009b81  retn
0x180009b82  mov     [rbp+57h+FileHandle], 0
0x180009b8a  jmp     loc_180009AD7
0x180009b8f  mov     ebx, 0C0000033h
0x180009b94  jmp     short loc_180009B68
0x180009b96  mov     ebx, 0C000026Eh
0x180009b9b  jmp     short loc_180009B68
```
