# PFOpenReparseTarget

- ea: `0x1400098a8`
- end: `0x140009a9a`
- name: `PFOpenReparseTarget`
- size: `498`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140009aa0`
- `0x14000a0d0`

## callees

- `0x1400014a0`
- `0x1400098a8`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009a13`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009a13`
- `ntoskrnl!IoFileObjectType` at `0x1400099eb`
- `ntoskrnl!ObfDereferenceObject` at `0x140009a66`
- `ntoskrnl!ObfDereferenceObject` at `0x140009a66`
- `FLTMGR!FltClose` at `0x140009a51`
- `FLTMGR!FltClose` at `0x140009a51`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140009a7b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140009a7b`
- `FLTMGR!FltGetFileNameInformation` at `0x140009904`
- `FLTMGR!FltGetFileNameInformation` at `0x140009904`
- `FLTMGR!FltCreateFile` at `0x1400099d9`
- `FLTMGR!FltCreateFile` at `0x1400099d9`

## pseudocode

```c
__int64 __fastcall PFOpenReparseTarget(
        struct _FLT_CALLBACK_DATA *a1,
        __int64 a2,
        PFLT_FILE_NAME_INFORMATION *a3,
        PVOID *a4)
{
  NTSTATUS v8; // ebx
  struct _FLT_TAG_DATA_BUFFER *TagData; // rcx
  struct _FLT_INSTANCE *v10; // rdx
  struct _FLT_FILTER *v11; // rcx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+70h] [rbp-49h] BYREF
  PVOID Object; // [rsp+78h] [rbp-41h] BYREF
  void *FileHandle; // [rsp+80h] [rbp-39h] BYREF
  __m128i Name; // [rsp+88h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-11h] BYREF

  FileHandle = 0;
  FileNameInformation = 0;
  Object = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  Name = 0;
  v8 = FltGetFileNameInformation(a1, 0x4000102u, &FileNameInformation);
  if ( v8 >= 0 )
  {
    TagData = a1->TagData;
    Name = (__m128i)FileNameInformation->Name;
    Name.m128i_i16[0] = _mm_cvtsi128_si32(Name) - TagData->UnparsedNameLength;
    if ( PFPathIsUnderTempDir((__int64)&Name) )
    {
      v8 = -1073741790;
    }
    else
    {
      v10 = *(struct _FLT_INSTANCE **)(a2 + 24);
      v11 = *(struct _FLT_FILTER **)(a2 + 8);
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&Name;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = FltCreateFile(
             v11,
             v10,
             &FileHandle,
             0x80100110,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0x80u,
             7u,
             3u,
             0x204020u,
             0,
             0,
             0x800u);
      if ( v8 >= 0 )
      {
        v8 = ObReferenceObjectByHandle(FileHandle, 0xF0000u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
        if ( v8 >= 0 )
        {
          *a4 = Object;
          Object = 0;
          if ( a3 )
          {
            *a3 = FileNameInformation;
            FileNameInformation = 0;
          }
        }
      }
    }
  }
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400098a8  push    rbp
0x1400098aa  push    rbx
0x1400098ab  push    rsi
0x1400098ac  push    rdi
0x1400098ad  push    r14
0x1400098af  push    r15
0x1400098b1  lea     rbp, [rsp-2Fh]
0x1400098b6  sub     rsp, 0E8h
0x1400098bd  xorps   xmm0, xmm0
0x1400098c0  mov     [rbp+57h+FileHandle], 0
0x1400098c8  mov     rdi, r8
0x1400098cb  mov     [rbp+57h+FileNameInformation], 0
0x1400098d3  mov     r14, rdx
0x1400098d6  mov     [rbp+57h+Object], 0
0x1400098de  xorps   xmm1, xmm1
0x1400098e1  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400098e5  mov     edx, 4000102h; NameOptions
0x1400098ea  mov     rsi, r9
0x1400098ed  movups  xmmword ptr [rbp+57h+var_68.Length], xmm0
0x1400098f1  mov     r15, rcx
0x1400098f4  movups  xmmword ptr [rbp+57h+var_68.ObjectName], xmm0
0x1400098f8  movups  xmmword ptr [rbp+57h+var_68.SecurityDescriptor], xmm0
0x1400098fc  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140009900  movups  [rbp+57h+var_88], xmm1
0x140009904  call    cs:__imp_FltGetFileNameInformation
0x14000990b  nop     dword ptr [rax+rax+00h]
0x140009910  mov     ebx, eax
0x140009912  test    eax, eax
0x140009914  js      loc_140009A48
0x14000991a  mov     rax, [rbp+57h+FileNameInformation]
0x14000991e  mov     rcx, [r15+28h]
0x140009922  movups  xmm0, xmmword ptr [rax+8]
0x140009926  movups  [rbp+57h+var_88], xmm0
0x14000992a  movd    eax, xmm0
0x14000992e  sub     ax, [rcx+6]
0x140009932  lea     rcx, [rbp+57h+var_88]
0x140009936  mov     word ptr [rbp+57h+var_88], ax
0x14000993a  call    PFPathIsUnderTempDir
0x14000993f  test    al, al
0x140009941  jz      short loc_14000994D
0x140009943  mov     ebx, 0C0000022h
0x140009948  jmp     loc_140009A48
0x14000994d  mov     rdx, [r14+18h]; Instance
0x140009951  lea     rax, [rbp+57h+var_88]
0x140009955  mov     rcx, [r14+8]; Filter
0x140009959  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x14000995d  mov     [rsp+110h+Flags], 800h; Flags
0x140009965  xorps   xmm0, xmm0
0x140009968  mov     [rsp+110h+EaLength], 0; EaLength
0x140009970  mov     r9d, 80100110h; DesiredAccess
0x140009976  mov     [rsp+110h+EaBuffer], 0; EaBuffer
0x14000997f  mov     [rsp+110h+CreateOptions], 204020h; CreateOptions
0x140009987  mov     [rsp+110h+CreateDisposition], 3; CreateDisposition
0x14000998f  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140009997  mov     [rbp+57h+var_68.ObjectName], rax
0x14000999b  lea     rax, [rbp+57h+var_78]
0x14000999f  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x1400099a7  mov     [rsp+110h+AllocationSize], 0; AllocationSize
0x1400099b0  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x1400099b5  lea     rax, [rbp+57h+var_68]
0x1400099b9  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x1400099be  mov     [rbp+57h+var_68.Length], 30h ; '0'
0x1400099c5  mov     [rbp+57h+var_68.RootDirectory], 0
0x1400099cd  mov     [rbp+57h+var_68.Attributes], 240h
0x1400099d4  movdqu  xmmword ptr [rbp+57h+var_68.SecurityDescriptor], xmm0
0x1400099d9  call    cs:__imp_FltCreateFile
0x1400099e0  nop     dword ptr [rax+rax+00h]
0x1400099e5  mov     ebx, eax
0x1400099e7  test    eax, eax
0x1400099e9  js      short loc_140009A48
0x1400099eb  mov     r8, cs:__imp_IoFileObjectType
0x1400099f2  lea     rax, [rbp+57h+Object]
0x1400099f6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400099fa  xor     r9d, r9d; AccessMode
0x1400099fd  mov     [rsp+110h+IoStatusBlock], 0; HandleInformation
0x140009a06  mov     edx, 0F0000h; DesiredAccess
0x140009a0b  mov     [rsp+110h+ObjectAttributes], rax; Object
0x140009a10  mov     r8, [r8]; ObjectType
0x140009a13  call    cs:__imp_ObReferenceObjectByHandle
0x140009a1a  nop     dword ptr [rax+rax+00h]
0x140009a1f  mov     ebx, eax
0x140009a21  test    eax, eax
0x140009a23  js      short loc_140009A48
0x140009a25  mov     rax, [rbp+57h+Object]
0x140009a29  mov     [rsi], rax
0x140009a2c  mov     [rbp+57h+Object], 0
0x140009a34  test    rdi, rdi
0x140009a37  jz      short loc_140009A48
0x140009a39  mov     rax, [rbp+57h+FileNameInformation]
0x140009a3d  mov     [rdi], rax
0x140009a40  mov     [rbp+57h+FileNameInformation], 0
0x140009a48  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140009a4c  test    rcx, rcx
0x140009a4f  jz      short loc_140009A5D
0x140009a51  call    cs:__imp_FltClose
0x140009a58  nop     dword ptr [rax+rax+00h]
0x140009a5d  mov     rcx, [rbp+57h+Object]; Object
0x140009a61  test    rcx, rcx
0x140009a64  jz      short loc_140009A72
0x140009a66  call    cs:__imp_ObfDereferenceObject
0x140009a6d  nop     dword ptr [rax+rax+00h]
0x140009a72  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140009a76  test    rcx, rcx
0x140009a79  jz      short loc_140009A87
0x140009a7b  call    cs:__imp_FltReleaseFileNameInformation
0x140009a82  nop     dword ptr [rax+rax+00h]
0x140009a87  mov     eax, ebx
0x140009a89  add     rsp, 0E8h
0x140009a90  pop     r15
0x140009a92  pop     r14
0x140009a94  pop     rdi
0x140009a95  pop     rsi
0x140009a96  pop     rbx
0x140009a97  pop     rbp
0x140009a98  retn
```
