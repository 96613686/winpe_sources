# WcCopyDataStreamByName

- ea: `0x14001d5b0`
- end: `0x14001d8d6`
- name: `WcCopyDataStreamByName`
- size: `806`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *, __int64, struct _FLT_INSTANCE *, struct _UNICODE_STRING *, void *, __int64, PFLT_INSTANCE Instance, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002fb70`

## callees

- `0x1400048a4`
- `0x140017b48`
- `0x14001d5b0`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14001d615`
- `ntoskrnl!IoGetSilo` at `0x14001d733`
- `ntoskrnl!IoGetSilo` at `0x14001d615`
- `ntoskrnl!IoGetSilo` at `0x14001d733`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d886`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d8b0`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d886`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d8b0`
- `FLTMGR!FltSetInformationFile` at `0x14001d834`
- `FLTMGR!FltSetInformationFile` at `0x14001d834`
- `FLTMGR!FltCreateFileEx2` at `0x14001d6a7`
- `FLTMGR!FltCreateFileEx2` at `0x14001d7d5`
- `FLTMGR!FltCreateFileEx2` at `0x14001d6a7`
- `FLTMGR!FltCreateFileEx2` at `0x14001d7d5`
- `FLTMGR!FltClose` at `0x14001d871`
- `FLTMGR!FltClose` at `0x14001d89b`
- `FLTMGR!FltClose` at `0x14001d871`
- `FLTMGR!FltClose` at `0x14001d89b`

## pseudocode

```c
__int64 __fastcall WcCopyDataStreamByName(
        struct _UNICODE_STRING *a1,
        void *a2,
        __int64 a3,
        struct _FLT_INSTANCE *a4,
        struct _UNICODE_STRING *a5,
        void *a6,
        __int64 a7,
        PFLT_INSTANCE Instance,
        __int64 a9)
{
  int v12; // edx
  NTSTATUS v13; // ebx
  int v14; // r9d
  struct _FLT_INSTANCE *v15; // rsi
  __int64 v16; // rdi
  int ObjectAttributes; // [rsp+28h] [rbp-C9h]
  char IoStatusBlock; // [rsp+30h] [rbp-C1h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-B9h]
  char FileAttributes; // [rsp+40h] [rbp-B1h]
  __int64 FileInformation; // [rsp+80h] [rbp-71h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-69h] BYREF
  HANDLE v24; // [rsp+90h] [rbp-61h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-59h] BYREF
  __int64 Silo; // [rsp+B8h] [rbp-39h]
  struct _OBJECT_ATTRIBUTES v27; // [rsp+C0h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK v28; // [rsp+F0h] [rbp-1h] BYREF
  PFILE_OBJECT v29; // [rsp+130h] [rbp+3Fh] BYREF
  PFILE_OBJECT FileObject; // [rsp+138h] [rbp+47h] BYREF

  v24 = 0;
  FileHandle = 0;
  FileObject = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v28 = 0;
  v29 = 0;
  *(&v27.Length + 1) = 0;
  FileInformation = 0;
  memset(&v27.Attributes + 1, 0, 20);
  DriverContext.Size = 40;
  Silo = IoGetSilo(a3);
  v27.Length = 48;
  v27.RootDirectory = a2;
  v27.Attributes = 576;
  v27.ObjectName = a1;
  v13 = FltCreateFileEx2(
          Globals,
          a4,
          &FileHandle,
          &FileObject,
          0x120089u,
          &v27,
          &v28,
          0,
          0x80u,
          1u,
          1u,
          0x200020u,
          0,
          0,
          0x100u,
          &DriverContext);
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_10;
    FileAttributes = v13;
    v14 = 111;
    AllocationSize = (PLARGE_INTEGER)a1;
    IoStatusBlock = 62;
    goto LABEL_4;
  }
  Silo = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  Silo = IoGetSilo(a7);
  v27.RootDirectory = a6;
  v27.ObjectName = a5;
  v15 = Instance;
  v27.Length = 48;
  v27.Attributes = 576;
  *(_OWORD *)&v27.SecurityDescriptor = 0;
  v13 = FltCreateFileEx2(
          Globals,
          Instance,
          &v24,
          &v29,
          0xC0000000,
          &v27,
          &v28,
          0,
          0x80u,
          1u,
          2u,
          0x200028u,
          0,
          0,
          0x100u,
          &DriverContext);
  if ( v13 >= 0 )
  {
    v16 = a9;
    FileInformation = a9;
    v13 = FltSetInformationFile(v15, v29, &FileInformation, 8u, FileEndOfFileInformation);
    if ( v13 >= 0 )
    {
      LOBYTE(ObjectAttributes) = 0;
      v13 = WcCopyStreamData(a4, FileObject, v16, v15, v29, ObjectAttributes);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    FileAttributes = v13;
    v14 = 112;
    AllocationSize = (PLARGE_INTEGER)a1;
    IoStatusBlock = 106;
LABEL_4:
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_sDZd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v12,
      10,
      v14,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      IoStatusBlock,
      (__int64)AllocationSize,
      FileAttributes);
  }
LABEL_10:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v24 )
    FltClose(v24);
  if ( v29 )
    ObfDereferenceObject(v29);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14001d5b0  mov     [rsp-8+arg_10], rbx
0x14001d5b5  push    rbp
0x14001d5b6  push    rsi
0x14001d5b7  push    rdi
0x14001d5b8  push    r14
0x14001d5ba  push    r15
0x14001d5bc  lea     rbp, [rsp-0Fh]
0x14001d5c1  sub     rsp, 100h
0x14001d5c8  xorps   xmm0, xmm0
0x14001d5cb  xor     r15d, r15d
0x14001d5ce  mov     rdi, rcx
0x14001d5d1  mov     [rbp+2Fh+var_90], r15
0x14001d5d5  movups  xmmword ptr [rbp+2Fh+var_60.ObjectName], xmm0
0x14001d5d9  mov     rcx, r8
0x14001d5dc  mov     r14, r9
0x14001d5df  lea     eax, [r15+28h]
0x14001d5e3  mov     [rbp+2Fh+FileHandle], r15
0x14001d5e7  lea     esi, [rax-27h]
0x14001d5ea  mov     [rbp+2Fh+FileObject], r15
0x14001d5ee  movups  xmmword ptr [rbp+2Fh+var_88.Size], xmm0
0x14001d5f2  mov     [rbp+2Fh+var_68], rsi
0x14001d5f6  mov     rbx, rdx
0x14001d5f9  movups  xmmword ptr [rbp+2Fh+var_30], xmm0
0x14001d5fd  mov     [rbp+2Fh+arg_0], r15
0x14001d601  movups  xmmword ptr [rbp+2Fh+var_60.Length], xmm0
0x14001d605  mov     [rbp+2Fh+FileInformation], r15
0x14001d609  movups  xmmword ptr [rbp+2Fh+var_60+1Ch], xmm0
0x14001d60d  mov     [rbp+2Fh+var_88.Size], ax
0x14001d611  movups  xmmword ptr [rbp+2Fh+var_88.DeviceObjectHint], xmm0
0x14001d615  call    cs:__imp_IoGetSilo
0x14001d61c  nop     dword ptr [rax+rax+00h]
0x14001d621  mov     rcx, cs:Globals; Filter
0x14001d628  lea     r9, [rbp+2Fh+FileObject]; FileObject
0x14001d62c  mov     [rbp+2Fh+var_68], rax
0x14001d630  lea     r8, [rbp+2Fh+FileHandle]; FileHandle
0x14001d634  lea     rax, [rbp+2Fh+var_88]
0x14001d638  mov     [rbp+2Fh+var_60.Length], 30h ; '0'
0x14001d63f  mov     [rsp+120h+DriverContext], rax; DriverContext
0x14001d644  xorps   xmm0, xmm0
0x14001d647  mov     [rsp+120h+Flags], 100h; Flags
0x14001d64f  lea     rax, [rbp+2Fh+var_30]
0x14001d653  mov     [rsp+120h+EaLength], r15d; EaLength
0x14001d658  mov     rdx, r14; Instance
0x14001d65b  mov     [rsp+120h+EaBuffer], r15; EaBuffer
0x14001d660  mov     [rsp+120h+CreateOptions], 200020h; CreateOptions
0x14001d668  mov     [rsp+120h+CreateDisposition], esi; CreateDisposition
0x14001d66c  mov     [rsp+120h+ShareAccess], esi; ShareAccess
0x14001d670  mov     dword ptr [rsp+120h+FileAttributes], 80h; FileAttributes
0x14001d678  mov     [rsp+120h+AllocationSize], r15; AllocationSize
0x14001d67d  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14001d682  lea     rax, [rbp+2Fh+var_60]
0x14001d686  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14001d68b  mov     [rsp+120h+DesiredAccess], 120089h; DesiredAccess
0x14001d693  mov     [rbp+2Fh+var_60.RootDirectory], rbx
0x14001d697  mov     [rbp+2Fh+var_60.Attributes], 240h
0x14001d69e  mov     [rbp+2Fh+var_60.ObjectName], rdi
0x14001d6a2  movdqu  xmmword ptr [rbp+2Fh+var_60.SecurityDescriptor], xmm0
0x14001d6a7  call    cs:__imp_FltCreateFileEx2
0x14001d6ae  nop     dword ptr [rax+rax+00h]
0x14001d6b3  mov     ebx, eax
0x14001d6b5  test    eax, eax
0x14001d6b7  jns     short loc_14001D717
0x14001d6b9  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d6c0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d6c7  jz      loc_14001D868
0x14001d6cd  mov     dword ptr [rsp+120h+FileAttributes], ebx
0x14001d6d1  lea     r9d, [r15+6Fh]
0x14001d6d5  mov     [rsp+120h+AllocationSize], rdi
0x14001d6da  mov     dword ptr [rsp+120h+IoStatusBlock], 0E3Eh
0x14001d6e2  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001d6e9  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001d6f0  mov     [rsp+120h+ObjectAttributes], rax
0x14001d6f5  mov     r8d, 0Ah
0x14001d6fb  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001d702  mov     dl, 2
0x14001d704  mov     qword ptr [rsp+120h+DesiredAccess], rax
0x14001d709  mov     rcx, [rcx+40h]
0x14001d70d  call    WPP_RECORDER_SF_sDZd
0x14001d712  jmp     loc_14001D868
0x14001d717  mov     rcx, [rbp+2Fh+arg_30]
0x14001d71b  xorps   xmm0, xmm0
0x14001d71e  mov     eax, 28h ; '('
0x14001d723  mov     [rbp+2Fh+var_68], rsi
0x14001d727  movups  xmmword ptr [rbp+2Fh+var_88.Size], xmm0
0x14001d72b  mov     [rbp+2Fh+var_88.Size], ax
0x14001d72f  movups  xmmword ptr [rbp+2Fh+var_88.DeviceObjectHint], xmm0
0x14001d733  call    cs:__imp_IoGetSilo
0x14001d73a  nop     dword ptr [rax+rax+00h]
0x14001d73f  mov     rcx, cs:Globals; Filter
0x14001d746  lea     r9, [rbp+2Fh+arg_0]; FileObject
0x14001d74a  mov     [rbp+2Fh+var_68], rax
0x14001d74e  lea     r8, [rbp+2Fh+var_90]; FileHandle
0x14001d752  mov     rax, [rbp+2Fh+arg_28]
0x14001d756  xorps   xmm0, xmm0
0x14001d759  mov     [rbp+2Fh+var_60.RootDirectory], rax
0x14001d75d  mov     rax, [rbp+2Fh+arg_20]
0x14001d761  mov     [rbp+2Fh+var_60.ObjectName], rax
0x14001d765  lea     rax, [rbp+2Fh+var_88]
0x14001d769  mov     [rsp+120h+DriverContext], rax; DriverContext
0x14001d76e  lea     rax, [rbp+2Fh+var_30]
0x14001d772  mov     [rsp+120h+Flags], 100h; Flags
0x14001d77a  mov     [rsp+120h+EaLength], r15d; EaLength
0x14001d77f  mov     [rsp+120h+EaBuffer], r15; EaBuffer
0x14001d784  mov     [rsp+120h+CreateOptions], 200028h; CreateOptions
0x14001d78c  mov     [rsp+120h+CreateDisposition], 2; CreateDisposition
0x14001d794  mov     [rsp+120h+ShareAccess], esi; ShareAccess
0x14001d798  mov     rsi, [rbp+2Fh+Instance]
0x14001d79c  mov     dword ptr [rsp+120h+FileAttributes], 80h; FileAttributes
0x14001d7a4  mov     rdx, rsi; Instance
0x14001d7a7  mov     [rsp+120h+AllocationSize], r15; AllocationSize
0x14001d7ac  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14001d7b1  lea     rax, [rbp+2Fh+var_60]
0x14001d7b5  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14001d7ba  mov     [rsp+120h+DesiredAccess], 0C0000000h; DesiredAccess
0x14001d7c2  mov     [rbp+2Fh+var_60.Length], 30h ; '0'
0x14001d7c9  mov     [rbp+2Fh+var_60.Attributes], 240h
0x14001d7d0  movdqu  xmmword ptr [rbp+2Fh+var_60.SecurityDescriptor], xmm0
0x14001d7d5  call    cs:__imp_FltCreateFileEx2
0x14001d7dc  nop     dword ptr [rax+rax+00h]
0x14001d7e1  mov     ebx, eax
0x14001d7e3  test    eax, eax
0x14001d7e5  jns     short loc_14001D813
0x14001d7e7  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d7ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d7f5  jz      short loc_14001D868
0x14001d7f7  mov     dword ptr [rsp+120h+FileAttributes], ebx
0x14001d7fb  mov     r9d, 70h ; 'p'
0x14001d801  mov     [rsp+120h+AllocationSize], rdi
0x14001d806  mov     dword ptr [rsp+120h+IoStatusBlock], 0E6Ah
0x14001d80e  jmp     loc_14001D6E2
0x14001d813  mov     rdi, [rbp+2Fh+arg_40]
0x14001d817  lea     r8, [rbp+2Fh+FileInformation]; FileInformation
0x14001d81b  mov     rdx, [rbp+2Fh+arg_0]; FileObject
0x14001d81f  mov     r9d, 8; Length
0x14001d825  mov     rcx, rsi; Instance
0x14001d828  mov     [rbp+2Fh+FileInformation], rdi
0x14001d82c  mov     [rsp+120h+DesiredAccess], 14h; FileInformationClass
0x14001d834  call    cs:__imp_FltSetInformationFile
0x14001d83b  nop     dword ptr [rax+rax+00h]
0x14001d840  mov     ebx, eax
0x14001d842  test    eax, eax
0x14001d844  js      short loc_14001D868
0x14001d846  mov     rax, [rbp+2Fh+arg_0]
0x14001d84a  mov     r9, rsi
0x14001d84d  mov     rdx, [rbp+2Fh+FileObject]
0x14001d851  mov     r8, rdi
0x14001d854  mov     byte ptr [rsp+120h+ObjectAttributes], r15b
0x14001d859  mov     rcx, r14
0x14001d85c  mov     qword ptr [rsp+120h+DesiredAccess], rax
0x14001d861  call    WcCopyStreamData
0x14001d866  mov     ebx, eax
0x14001d868  mov     rcx, [rbp+2Fh+FileHandle]; FileHandle
0x14001d86c  test    rcx, rcx
0x14001d86f  jz      short loc_14001D87D
0x14001d871  call    cs:__imp_FltClose
0x14001d878  nop     dword ptr [rax+rax+00h]
0x14001d87d  mov     rcx, [rbp+2Fh+FileObject]; Object
0x14001d881  test    rcx, rcx
0x14001d884  jz      short loc_14001D892
0x14001d886  call    cs:__imp_ObfDereferenceObject
0x14001d88d  nop     dword ptr [rax+rax+00h]
0x14001d892  mov     rcx, [rbp+2Fh+var_90]; FileHandle
0x14001d896  test    rcx, rcx
0x14001d899  jz      short loc_14001D8A7
0x14001d89b  call    cs:__imp_FltClose
0x14001d8a2  nop     dword ptr [rax+rax+00h]
0x14001d8a7  mov     rcx, [rbp+2Fh+arg_0]; Object
0x14001d8ab  test    rcx, rcx
0x14001d8ae  jz      short loc_14001D8BC
0x14001d8b0  call    cs:__imp_ObfDereferenceObject
0x14001d8b7  nop     dword ptr [rax+rax+00h]
0x14001d8bc  mov     eax, ebx
0x14001d8be  mov     rbx, [rsp+120h+arg_10]
0x14001d8c6  add     rsp, 100h
0x14001d8cd  pop     r15
0x14001d8cf  pop     r14
0x14001d8d1  pop     rdi
0x14001d8d2  pop     rsi
0x14001d8d3  pop     rbp
0x14001d8d4  retn
```
