# VhdmpiIsOnClusterStorage(_UNICODE_STRING *)

- ea: `0x140047018`
- end: `0x140047241`
- name: `?VhdmpiIsOnClusterStorage@@YAHPEAU_UNICODE_STRING@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001a1e8`

## callees

- `0x140020874`
- `0x140023560`
- `0x140035e94`
- `0x140047018`
- `0x14009e1c0`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x14004710d`
- `ntoskrnl!ZwCreateFile` at `0x14004710d`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400471b2`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400471b2`
- `ntoskrnl!ZwClose` at `0x140047218`
- `ntoskrnl!ZwClose` at `0x140047218`

## string_xrefs

- `0x140047145`: `VhdmpiIsOnClusterStorage: ZwCreateFile failed with status (0x%08x)`
- `0x140047090`: `VhdmpiIsOnClusterStorage: CreateNtFilePath failed -invalid path (0x%08x)`

## pseudocode

```c
__int64 __fastcall VhdmpiIsOnClusterStorage(struct _UNICODE_STRING *a1)
{
  int v1; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  unsigned __int16 v4; // dx
  char *v5; // rax
  NTSTATUS v6; // eax
  unsigned int v7; // edi
  int v8; // r8d
  __int64 FileAttributes; // [rsp+28h] [rbp-31h]
  struct _UNICODE_STRING v11; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  unsigned int OutputBuffer; // [rsp+C8h] [rbp+6Fh] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+77h] BYREF

  FileHandle = 0;
  OutputBuffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  v11 = 0;
  v1 = VhdmpiCreateNtFilePath(a1, &v11);
  v3 = (unsigned int)v1;
  if ( v1 < 0 )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      goto LABEL_10;
    v4 = 11926;
    v5 = "VhdmpiIsOnClusterStorage: CreateNtFilePath failed -invalid path (0x%08x)";
LABEL_9:
    LODWORD(FileAttributes) = v3;
    TraceEvents("VhdmpiIsOnClusterStorage", v4, 2u, 4u, v5, FileAttributes);
LABEL_10:
    v7 = 0;
    goto LABEL_17;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &v11;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x20u, 0, 0);
  v3 = (unsigned int)v6;
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      goto LABEL_10;
    v4 = 11958;
    v5 = "VhdmpiIsOnClusterStorage: ZwCreateFile failed with status (0x%08x)";
    goto LABEL_9;
  }
  if ( ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x560060u, 0, 0, &OutputBuffer, 4u) < 0 )
  {
    v7 = 0;
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
      TraceEvents(
        "VhdmpiIsOnClusterStorage",
        0x2ECFu,
        2u,
        4u,
        "VhdmpiIsOnClusterStorage: IOCTL_VOLUME_IS_CSV failed with status (0x%08x)",
        v8);
  }
  else
  {
    v7 = OutputBuffer;
  }
  ZwClose(FileHandle);
LABEL_17:
  VhdmpiFreeFilePath(&v11, v2, v3);
  return v7;
}

```

## disassembly

```asm
0x140047018  mov     [rsp-8+arg_0], rdi
0x14004701d  push    rbp
0x14004701e  lea     rbp, [rsp-57h]
0x140047023  sub     rsp, 0B0h
0x14004702a  xorps   xmm0, xmm0
0x14004702d  mov     [rbp+57h+FileHandle], 0
0x140047035  xorps   xmm1, xmm1
0x140047038  mov     [rbp+57h+OutputBuffer], 0
0x14004703f  lea     rdx, [rbp+57h+var_50]; struct _UNICODE_STRING *
0x140047043  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140047047  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004704b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004704f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140047053  movups  xmmword ptr [rbp+57h+var_50.Length], xmm1
0x140047057  call    VhdmpiCreateNtFilePath
0x14004705c  mov     r8d, eax
0x14004705f  test    eax, eax
0x140047061  jns     short loc_14004709C
0x140047063  mov     ecx, cs:dword_140087708
0x140047069  cmp     ecx, 2
0x14004706c  jbe     loc_14004716C
0x140047072  mov     edx, 4
0x140047077  lea     rcx, dword_140087708
0x14004707e  call    _tlgKeywordOn
0x140047083  test    al, al
0x140047085  jz      loc_14004716C
0x14004708b  mov     edx, 2E96h
0x140047090  lea     rax, aVhdmpiisonclus_0; "VhdmpiIsOnClusterStorage: CreateNtFileP"...
0x140047097  jmp     loc_14004714C
0x14004709c  mov     [rsp+0B0h+EaLength], 0; EaLength
0x1400470a4  lea     rax, [rbp+57h+var_50]
0x1400470a8  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x1400470b1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400470b5  mov     [rsp+0B0h+CreateOptions], 20h ; ' '; CreateOptions
0x1400470bd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400470c1  mov     [rsp+0B0h+CreateDisposition], 1; CreateDisposition
0x1400470c9  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400470cd  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x1400470d5  xorps   xmm0, xmm0
0x1400470d8  mov     dword ptr [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x1400470e0  mov     edx, 100080h; DesiredAccess
0x1400470e5  mov     [rsp+0B0h+AllocationSize], 0; AllocationSize
0x1400470ee  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400470f5  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400470fd  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140047104  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140047108  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004710d  call    cs:__imp_ZwCreateFile
0x140047114  nop     dword ptr [rax+rax+00h]
0x140047119  mov     r8d, eax
0x14004711c  test    eax, eax
0x14004711e  jns     short loc_140047173
0x140047120  mov     ecx, cs:dword_140087708
0x140047126  cmp     ecx, 2
0x140047129  jbe     short loc_14004716C
0x14004712b  mov     edx, 4
0x140047130  lea     rcx, dword_140087708
0x140047137  call    _tlgKeywordOn
0x14004713c  test    al, al
0x14004713e  jz      short loc_14004716C
0x140047140  mov     edx, 2EB6h; int
0x140047145  lea     rax, aVhdmpiisonclus_1; "VhdmpiIsOnClusterStorage: ZwCreateFile "...
0x14004714c  mov     dword ptr [rsp+0B0h+FileAttributes], r8d; char
0x140047151  lea     rcx, aVhdmpiisonclus; "VhdmpiIsOnClusterStorage"
0x140047158  mov     r9d, 4; int
0x14004715e  mov     [rsp+0B0h+AllocationSize], rax; char *
0x140047163  lea     r8d, [r9-2]; int
0x140047167  call    TraceEvents
0x14004716c  xor     edi, edi
0x14004716e  jmp     loc_140047224
0x140047173  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140047177  lea     rax, [rbp+57h+OutputBuffer]
0x14004717b  mov     dword ptr [rsp+0B0h+EaBuffer], 4; OutputBufferLength
0x140047183  xor     r9d, r9d; ApcContext
0x140047186  mov     qword ptr [rsp+0B0h+CreateOptions], rax; OutputBuffer
0x14004718b  xor     r8d, r8d; ApcRoutine
0x14004718e  mov     [rsp+0B0h+CreateDisposition], 0; InputBufferLength
0x140047196  lea     rax, [rbp+57h+IoStatusBlock]
0x14004719a  mov     qword ptr [rsp+0B0h+ShareAccess], 0; InputBuffer
0x1400471a3  xor     edx, edx; Event
0x1400471a5  mov     dword ptr [rsp+0B0h+FileAttributes], 560060h; IoControlCode
0x1400471ad  mov     [rsp+0B0h+AllocationSize], rax; IoStatusBlock
0x1400471b2  call    cs:__imp_ZwDeviceIoControlFile
0x1400471b9  nop     dword ptr [rax+rax+00h]
0x1400471be  mov     r8d, eax
0x1400471c1  test    eax, eax
0x1400471c3  js      short loc_1400471CA
0x1400471c5  mov     edi, [rbp+57h+OutputBuffer]
0x1400471c8  jmp     short loc_140047214
0x1400471ca  mov     eax, cs:dword_140087708
0x1400471d0  xor     edi, edi
0x1400471d2  cmp     eax, 2
0x1400471d5  jbe     short loc_140047214
0x1400471d7  lea     edx, [rdi+4]
0x1400471da  lea     rcx, dword_140087708
0x1400471e1  call    _tlgKeywordOn
0x1400471e6  test    al, al
0x1400471e8  jz      short loc_140047214
0x1400471ea  mov     dword ptr [rsp+0B0h+FileAttributes], r8d; char
0x1400471ef  lea     rax, aVhdmpiisonclus_2; "VhdmpiIsOnClusterStorage: IOCTL_VOLUME_"...
0x1400471f6  lea     r8d, [rdi+2]; int
0x1400471fa  mov     [rsp+0B0h+AllocationSize], rax; char *
0x1400471ff  mov     edx, 2ECFh; int
0x140047204  lea     r9d, [rdi+4]; int
0x140047208  lea     rcx, aVhdmpiisonclus; "VhdmpiIsOnClusterStorage"
0x14004720f  call    TraceEvents
0x140047214  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140047218  call    cs:__imp_ZwClose
0x14004721f  nop     dword ptr [rax+rax+00h]
0x140047224  lea     rcx, [rbp+57h+var_50]
0x140047228  call    VhdmpiFreeFilePath
0x14004722d  mov     eax, edi
0x14004722f  mov     rdi, [rsp+0B0h+arg_0]
0x140047237  add     rsp, 0B0h
0x14004723e  pop     rbp
0x14004723f  retn
```
