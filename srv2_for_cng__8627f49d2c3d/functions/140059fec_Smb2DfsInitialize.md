# Smb2DfsInitialize

- ea: `0x140059fec`
- end: `0x14005a1fd`
- name: `Smb2DfsInitialize`
- size: `529`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140059540`
- `0x140061f44`

## callees

- `0x1400224b8`
- `0x140059fec`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14005a037`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005a037`
- `ntoskrnl!ZwClose` at `0x14005a1a4`
- `ntoskrnl!ZwClose` at `0x14005a1a4`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a142`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a142`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005a0e8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005a0e8`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005a101`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005a101`
- `ntoskrnl!ZwCreateFile` at `0x14005a0b0`
- `ntoskrnl!ZwCreateFile` at `0x14005a0b0`

## pseudocode

```c
__int64 Smb2DfsInitialize()
{
  __int64 result; // rax
  NTSTATUS v1; // eax
  NTSTATUS v2; // ebx
  __int64 v3; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp+67h] BYREF

  FileHandle = 0;
  result = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !Smb2DfsFileObject )
  {
    RtlInitUnicodeString(&DestinationString, L"\\DfsServer");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v1 = ZwCreateFile(&FileHandle, 3u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
    if ( v1 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_f2fe7b9906d9373ee732fbbfda7ee132_Traceguids,
          (unsigned int)v1);
      }
      return 0;
    }
    else
    {
      v2 = ObReferenceObjectByHandle(FileHandle, 0, 0, 0, &Smb2DfsFileObject, 0);
      if ( v2 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            WPP_f2fe7b9906d9373ee732fbbfda7ee132_Traceguids,
            (unsigned int)v2);
        }
        v2 = 0;
      }
      else
      {
        Smb2DfsDeviceObject = (__int64)IoGetRelatedDeviceObject((PFILE_OBJECT)Smb2DfsFileObject);
        v3 = *(_QWORD *)(*(_QWORD *)(Smb2DfsDeviceObject + 8) + 80LL);
        if ( v3 && *(_DWORD *)v3 > 0x50u )
          Smb2DfsFastIoDeviceControl = *(_QWORD *)(v3 + 80);
        if ( !Smb2DfsFastIoDeviceControl )
        {
          ObfDereferenceObject(Smb2DfsFileObject);
          Smb2DfsFileObject = 0;
          Smb2DfsDeviceObject = 0;
        }
      }
      ZwClose(FileHandle);
    }
    return (unsigned int)v2;
  }
  return result;
}

```

## disassembly

```asm
0x140059fec  mov     [rsp-8+arg_8], rbx
0x140059ff1  push    rbp
0x140059ff2  lea     rbp, [rsp-57h]
0x140059ff7  sub     rsp, 0B0h
0x140059ffe  xorps   xmm0, xmm0
0x14005a001  mov     [rbp+57h+FileHandle], 0
0x14005a009  xor     eax, eax
0x14005a00b  cmp     cs:Smb2DfsFileObject, rax
0x14005a012  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14005a016  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14005a01a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14005a01e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14005a022  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14005a026  jnz     loc_14005A1EB
0x14005a02c  lea     rdx, aDfsserver; "\\DfsServer"
0x14005a033  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005a037  call    cs:__imp_RtlInitUnicodeString
0x14005a03e  nop     dword ptr [rax+rax+00h]
0x14005a043  mov     [rsp+0B0h+EaLength], 0; EaLength
0x14005a04b  lea     rax, [rbp+57h+DestinationString]
0x14005a04f  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x14005a058  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14005a05c  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x14005a064  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005a068  mov     [rsp+0B0h+CreateDisposition], 1; CreateDisposition
0x14005a070  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14005a074  mov     edx, 3; DesiredAccess
0x14005a079  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14005a080  mov     [rsp+0B0h+ShareAccess], edx; ShareAccess
0x14005a084  xorps   xmm0, xmm0
0x14005a087  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x14005a08f  mov     [rsp+0B0h+AllocationSize], 0; AllocationSize
0x14005a098  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14005a0a0  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14005a0a7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14005a0ab  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005a0b0  call    cs:__imp_ZwCreateFile
0x14005a0b7  nop     dword ptr [rax+rax+00h]
0x14005a0bc  mov     r9d, eax
0x14005a0bf  test    eax, eax
0x14005a0c1  js      loc_14005A1B2
0x14005a0c7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14005a0cb  lea     rax, Smb2DfsFileObject
0x14005a0d2  mov     qword ptr [rsp+0B0h+FileAttributes], 0; HandleInformation
0x14005a0db  xor     r9d, r9d; AccessMode
0x14005a0de  xor     r8d, r8d; ObjectType
0x14005a0e1  mov     [rsp+0B0h+AllocationSize], rax; Object
0x14005a0e6  xor     edx, edx; DesiredAccess
0x14005a0e8  call    cs:__imp_ObReferenceObjectByHandle
0x14005a0ef  nop     dword ptr [rax+rax+00h]
0x14005a0f4  mov     ebx, eax
0x14005a0f6  test    eax, eax
0x14005a0f8  js      short loc_14005A166
0x14005a0fa  mov     rcx, cs:Smb2DfsFileObject; FileObject
0x14005a101  call    cs:__imp_IoGetRelatedDeviceObject
0x14005a108  nop     dword ptr [rax+rax+00h]
0x14005a10d  mov     cs:Smb2DfsDeviceObject, rax
0x14005a114  mov     rcx, [rax+8]
0x14005a118  mov     rax, [rcx+50h]
0x14005a11c  test    rax, rax
0x14005a11f  jz      short loc_14005A131
0x14005a121  cmp     dword ptr [rax], 50h ; 'P'
0x14005a124  jbe     short loc_14005A131
0x14005a126  mov     rax, [rax+50h]
0x14005a12a  mov     cs:Smb2DfsFastIoDeviceControl, rax
0x14005a131  cmp     cs:Smb2DfsFastIoDeviceControl, 0
0x14005a139  jnz     short loc_14005A1A0
0x14005a13b  mov     rcx, cs:Smb2DfsFileObject; Object
0x14005a142  call    cs:__imp_ObfDereferenceObject
0x14005a149  nop     dword ptr [rax+rax+00h]
0x14005a14e  mov     cs:Smb2DfsFileObject, 0
0x14005a159  mov     cs:Smb2DfsDeviceObject, 0
0x14005a164  jmp     short loc_14005A1A0
0x14005a166  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005a16d  lea     rax, WPP_GLOBAL_Control
0x14005a174  cmp     rcx, rax
0x14005a177  jz      short loc_14005A19E
0x14005a179  mov     eax, [rcx+2Ch]
0x14005a17c  test    al, 1
0x14005a17e  jz      short loc_14005A19E
0x14005a180  cmp     byte ptr [rcx+29h], 1
0x14005a184  jb      short loc_14005A19E
0x14005a186  mov     rcx, [rcx+18h]
0x14005a18a  lea     r8, WPP_f2fe7b9906d9373ee732fbbfda7ee132_Traceguids
0x14005a191  mov     edx, 0Ah
0x14005a196  mov     r9d, ebx
0x14005a199  call    WPP_SF_d
0x14005a19e  xor     ebx, ebx
0x14005a1a0  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14005a1a4  call    cs:__imp_ZwClose
0x14005a1ab  nop     dword ptr [rax+rax+00h]
0x14005a1b0  jmp     short loc_14005A1E9
0x14005a1b2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005a1b9  lea     rax, WPP_GLOBAL_Control
0x14005a1c0  cmp     rcx, rax
0x14005a1c3  jz      short loc_14005A1E7
0x14005a1c5  mov     eax, [rcx+2Ch]
0x14005a1c8  test    al, 1
0x14005a1ca  jz      short loc_14005A1E7
0x14005a1cc  cmp     byte ptr [rcx+29h], 1
0x14005a1d0  jb      short loc_14005A1E7
0x14005a1d2  mov     rcx, [rcx+18h]
0x14005a1d6  lea     r8, WPP_f2fe7b9906d9373ee732fbbfda7ee132_Traceguids
0x14005a1dd  mov     edx, 0Bh
0x14005a1e2  call    WPP_SF_d
0x14005a1e7  xor     ebx, ebx
0x14005a1e9  mov     eax, ebx
0x14005a1eb  mov     rbx, [rsp+0B0h+arg_8]
0x14005a1f3  add     rsp, 0B0h
0x14005a1fa  pop     rbp
0x14005a1fb  retn
```
