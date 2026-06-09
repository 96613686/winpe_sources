# VhdmpiIsOnClusterStorage(_UNICODE_STRING *)

- ea: `0x140047408`
- end: `0x140047631`
- name: `?VhdmpiIsOnClusterStorage@@YAHPEAU_UNICODE_STRING@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001a608`

## callees

- `0x140020c94`
- `0x140023980`
- `0x140036284`
- `0x140047408`
- `0x14009e1c0`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x1400474fd`
- `ntoskrnl!ZwCreateFile` at `0x1400474fd`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400475a2`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400475a2`
- `ntoskrnl!ZwClose` at `0x140047608`
- `ntoskrnl!ZwClose` at `0x140047608`

## string_xrefs

- `0x140047480`: `VhdmpiIsOnClusterStorage: CreateNtFilePath failed -invalid path (0x%08x)`
- `0x140047535`: `VhdmpiIsOnClusterStorage: ZwCreateFile failed with status (0x%08x)`

## pseudocode

```c
__int64 __fastcall VhdmpiIsOnClusterStorage(struct _UNICODE_STRING *a1)
{
  int v1; // r8d
  unsigned __int16 v2; // dx
  char *v3; // rax
  unsigned int v4; // edi
  int v5; // r8d
  __int64 FileAttributes; // [rsp+28h] [rbp-31h]
  struct _UNICODE_STRING v8; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  unsigned int OutputBuffer; // [rsp+C8h] [rbp+6Fh] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+77h] BYREF

  FileHandle = 0;
  OutputBuffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  v8 = 0;
  if ( VhdmpiCreateNtFilePath(a1, &v8) < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
      goto LABEL_10;
    v2 = 11926;
    v3 = "VhdmpiIsOnClusterStorage: CreateNtFilePath failed -invalid path (0x%08x)";
LABEL_9:
    LODWORD(FileAttributes) = v1;
    TraceEvents("VhdmpiIsOnClusterStorage", v2, 2u, 4u, v3, FileAttributes);
LABEL_10:
    v4 = 0;
    goto LABEL_17;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &v8;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x20u, 0, 0) < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
      goto LABEL_10;
    v2 = 11958;
    v3 = "VhdmpiIsOnClusterStorage: ZwCreateFile failed with status (0x%08x)";
    goto LABEL_9;
  }
  if ( ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x560060u, 0, 0, &OutputBuffer, 4u) < 0 )
  {
    v4 = 0;
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
      TraceEvents(
        "VhdmpiIsOnClusterStorage",
        0x2ECFu,
        2u,
        4u,
        "VhdmpiIsOnClusterStorage: IOCTL_VOLUME_IS_CSV failed with status (0x%08x)",
        v5);
  }
  else
  {
    v4 = OutputBuffer;
  }
  ZwClose(FileHandle);
LABEL_17:
  VhdmpiFreeFilePath(&v8);
  return v4;
}

```

## disassembly

```asm
0x140047408  mov     [rsp-8+arg_0], rdi
0x14004740d  push    rbp
0x14004740e  lea     rbp, [rsp-57h]
0x140047413  sub     rsp, 0B0h
0x14004741a  xorps   xmm0, xmm0
0x14004741d  mov     [rbp+57h+FileHandle], 0
0x140047425  xorps   xmm1, xmm1
0x140047428  mov     [rbp+57h+OutputBuffer], 0
0x14004742f  lea     rdx, [rbp+57h+var_50]; struct _UNICODE_STRING *
0x140047433  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140047437  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004743b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004743f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140047443  movups  xmmword ptr [rbp+57h+var_50.Length], xmm1
0x140047447  call    VhdmpiCreateNtFilePath
0x14004744c  mov     r8d, eax
0x14004744f  test    eax, eax
0x140047451  jns     short loc_14004748C
0x140047453  mov     ecx, cs:dword_1400876D0
0x140047459  cmp     ecx, 2
0x14004745c  jbe     loc_14004755C
0x140047462  mov     edx, 4
0x140047467  lea     rcx, dword_1400876D0
0x14004746e  call    _tlgKeywordOn
0x140047473  test    al, al
0x140047475  jz      loc_14004755C
0x14004747b  mov     edx, 2E96h
0x140047480  lea     rax, aVhdmpiisonclus_0; "VhdmpiIsOnClusterStorage: CreateNtFileP"...
0x140047487  jmp     loc_14004753C
0x14004748c  mov     [rsp+0B0h+EaLength], 0; EaLength
0x140047494  lea     rax, [rbp+57h+var_50]
0x140047498  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x1400474a1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400474a5  mov     [rsp+0B0h+CreateOptions], 20h ; ' '; CreateOptions
0x1400474ad  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400474b1  mov     [rsp+0B0h+CreateDisposition], 1; CreateDisposition
0x1400474b9  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400474bd  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x1400474c5  xorps   xmm0, xmm0
0x1400474c8  mov     dword ptr [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x1400474d0  mov     edx, 100080h; DesiredAccess
0x1400474d5  mov     [rsp+0B0h+AllocationSize], 0; AllocationSize
0x1400474de  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400474e5  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400474ed  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400474f4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400474f8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400474fd  call    cs:__imp_ZwCreateFile
0x140047504  nop     dword ptr [rax+rax+00h]
0x140047509  mov     r8d, eax
0x14004750c  test    eax, eax
0x14004750e  jns     short loc_140047563
0x140047510  mov     ecx, cs:dword_1400876D0
0x140047516  cmp     ecx, 2
0x140047519  jbe     short loc_14004755C
0x14004751b  mov     edx, 4
0x140047520  lea     rcx, dword_1400876D0
0x140047527  call    _tlgKeywordOn
0x14004752c  test    al, al
0x14004752e  jz      short loc_14004755C
0x140047530  mov     edx, 2EB6h; int
0x140047535  lea     rax, aVhdmpiisonclus_1; "VhdmpiIsOnClusterStorage: ZwCreateFile "...
0x14004753c  mov     dword ptr [rsp+0B0h+FileAttributes], r8d; char
0x140047541  lea     rcx, aVhdmpiisonclus; "VhdmpiIsOnClusterStorage"
0x140047548  mov     r9d, 4; int
0x14004754e  mov     [rsp+0B0h+AllocationSize], rax; char *
0x140047553  lea     r8d, [r9-2]; int
0x140047557  call    TraceEvents
0x14004755c  xor     edi, edi
0x14004755e  jmp     loc_140047614
0x140047563  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140047567  lea     rax, [rbp+57h+OutputBuffer]
0x14004756b  mov     dword ptr [rsp+0B0h+EaBuffer], 4; OutputBufferLength
0x140047573  xor     r9d, r9d; ApcContext
0x140047576  mov     qword ptr [rsp+0B0h+CreateOptions], rax; OutputBuffer
0x14004757b  xor     r8d, r8d; ApcRoutine
0x14004757e  mov     [rsp+0B0h+CreateDisposition], 0; InputBufferLength
0x140047586  lea     rax, [rbp+57h+IoStatusBlock]
0x14004758a  mov     qword ptr [rsp+0B0h+ShareAccess], 0; InputBuffer
0x140047593  xor     edx, edx; Event
0x140047595  mov     dword ptr [rsp+0B0h+FileAttributes], 560060h; IoControlCode
0x14004759d  mov     [rsp+0B0h+AllocationSize], rax; IoStatusBlock
0x1400475a2  call    cs:__imp_ZwDeviceIoControlFile
0x1400475a9  nop     dword ptr [rax+rax+00h]
0x1400475ae  mov     r8d, eax
0x1400475b1  test    eax, eax
0x1400475b3  js      short loc_1400475BA
0x1400475b5  mov     edi, [rbp+57h+OutputBuffer]
0x1400475b8  jmp     short loc_140047604
0x1400475ba  mov     eax, cs:dword_1400876D0
0x1400475c0  xor     edi, edi
0x1400475c2  cmp     eax, 2
0x1400475c5  jbe     short loc_140047604
0x1400475c7  lea     edx, [rdi+4]
0x1400475ca  lea     rcx, dword_1400876D0
0x1400475d1  call    _tlgKeywordOn
0x1400475d6  test    al, al
0x1400475d8  jz      short loc_140047604
0x1400475da  mov     dword ptr [rsp+0B0h+FileAttributes], r8d; char
0x1400475df  lea     rax, aVhdmpiisonclus_2; "VhdmpiIsOnClusterStorage: IOCTL_VOLUME_"...
0x1400475e6  lea     r8d, [rdi+2]; int
0x1400475ea  mov     [rsp+0B0h+AllocationSize], rax; char *
0x1400475ef  mov     edx, 2ECFh; int
0x1400475f4  lea     r9d, [rdi+4]; int
0x1400475f8  lea     rcx, aVhdmpiisonclus; "VhdmpiIsOnClusterStorage"
0x1400475ff  call    TraceEvents
0x140047604  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140047608  call    cs:__imp_ZwClose
0x14004760f  nop     dword ptr [rax+rax+00h]
0x140047614  lea     rcx, [rbp+57h+var_50]
0x140047618  call    VhdmpiFreeFilePath
0x14004761d  mov     eax, edi
0x14004761f  mov     rdi, [rsp+0B0h+arg_0]
0x140047627  add     rsp, 0B0h
0x14004762e  pop     rbp
0x14004762f  retn
```
