# WimFSFOpenWimFile

- ea: `0x14002da2c`
- end: `0x14002dcb0`
- name: `WimFSFOpenWimFile`
- size: `644`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, PVOID Buffer)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400263f0`
- `0x14002d940`
- `0x14002dcc0`

## callees

- `0x14000d3b8`
- `0x14000ed74`
- `0x14000fc08`
- `0x14002da2c`
- `0x14002dfb8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002dc70`
- `ntoskrnl!ObfDereferenceObject` at `0x14002dc70`
- `FLTMGR!FltReadFile` at `0x14002dbe4`
- `FLTMGR!FltReadFile` at `0x14002dbe4`
- `FLTMGR!FltCreateFileEx` at `0x14002daeb`
- `FLTMGR!FltCreateFileEx` at `0x14002daeb`
- `FLTMGR!FltClose` at `0x14002dc85`
- `FLTMGR!FltClose` at `0x14002dc85`

## pseudocode

```c
__int64 __fastcall WimFSFOpenWimFile(
        int a1,
        __int64 a2,
        __int64 a3,
        struct _UNICODE_STRING *a4,
        __int64 a5,
        _QWORD *a6,
        PFILE_OBJECT *a7,
        PVOID Buffer)
{
  int v9; // esi
  struct _FLT_INSTANCE *v11; // rdx
  struct _FLT_FILTER *v13; // rcx
  NTSTATUS v14; // ebx
  struct _FILE_OBJECT *v15; // rdx
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  int v17; // eax
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  PVOID v21; // rsi
  struct _FLT_INSTANCE *v22; // rcx
  PFILE_OBJECT v23; // rax
  void *v24; // rcx
  void *FileHandle; // [rsp+80h] [rbp-39h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+88h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-19h] BYREF
  ULONG BytesRead; // [rsp+110h] [rbp+57h] BYREF
  PFILE_OBJECT FileObject; // [rsp+118h] [rbp+5Fh] BYREF

  ObjectAttributes.ObjectName = a4;
  v9 = (int)a4;
  v11 = *(struct _FLT_INSTANCE **)(a3 + 120);
  v13 = *(struct _FLT_FILTER **)(a3 + 104);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  IoStatusBlock = 0;
  FileHandle = 0;
  FileObject = 0;
  BytesRead = 0;
  ByteOffset.QuadPart = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v14 = FltCreateFileEx(
          v13,
          v11,
          &FileHandle,
          &FileObject,
          0x120089u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0,
          1u,
          1u,
          0x40u,
          0,
          0,
          1u);
  if ( v14 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_ZZd(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        (unsigned int)WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids,
        v9,
        a2 + 64,
        v14);
    return (unsigned int)v14;
  }
  v15 = FileObject;
  SectionObjectPointer = FileObject->SectionObjectPointer;
  if ( SectionObjectPointer && SectionObjectPointer->DataSectionObject )
  {
    v17 = WofFlushFile(a1, *(_QWORD *)(a3 + 120), (_DWORD)FileObject, 0, 1);
    v14 = v17;
    if ( v17 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_23;
      v19 = 13;
      v20 = (unsigned int)v17;
      goto LABEL_11;
    }
    v15 = FileObject;
  }
  v21 = Buffer;
  v22 = *(struct _FLT_INSTANCE **)(a3 + 120);
  ByteOffset.QuadPart = 0;
  v14 = FltReadFile(v22, v15, &ByteOffset, 0xD0u, Buffer, 0, &BytesRead, 0, 0);
  if ( v14 >= 0 )
  {
    v14 = WimFSFValidateWim(*(_QWORD *)(a3 + 120), FileObject, v21, a5);
    if ( v14 >= 0 )
    {
      v23 = FileObject;
      FileObject = 0;
      *a7 = v23;
      v24 = FileHandle;
      FileHandle = 0;
      *a6 = v24;
      goto LABEL_23;
    }
    v18 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_23;
    v19 = 15;
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_23;
    v19 = 14;
  }
  v20 = (unsigned int)v14;
LABEL_11:
  WPP_SF_d(v18->AttachedDevice, v19, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids, v20);
LABEL_23:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14002da2c  mov     [rsp-8+arg_0], rbx
0x14002da31  mov     [rsp-8+arg_8], rsi
0x14002da36  push    rbp
0x14002da37  push    rdi
0x14002da38  push    r12
0x14002da3a  push    r14
0x14002da3c  push    r15
0x14002da3e  lea     rbp, [rsp-17h]
0x14002da43  sub     rsp, 0D0h
0x14002da4a  mov     [rsp+0F0h+Flags], 1; Flags
0x14002da52  lea     rax, [rbp+37h+var_60]
0x14002da56  xor     r12d, r12d
0x14002da59  mov     [rbp+37h+var_50.ObjectName], r9
0x14002da5d  mov     [rsp+0F0h+EaLength], r12d; EaLength
0x14002da62  mov     rdi, r8
0x14002da65  mov     [rsp+0F0h+EaBuffer], r12; EaBuffer
0x14002da6a  lea     r8, [rbp+37h+FileHandle]; FileHandle
0x14002da6e  mov     [rsp+0F0h+CreateOptions], 40h ; '@'; CreateOptions
0x14002da76  xorps   xmm0, xmm0
0x14002da79  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x14002da81  mov     rsi, r9
0x14002da84  mov     [rsp+0F0h+ShareAccess], 1; ShareAccess
0x14002da8c  lea     r9, [rbp+37h+FileObject]; FileObject
0x14002da90  mov     [rsp+0F0h+FileAttributes], r12d; FileAttributes
0x14002da95  mov     r14, rdx
0x14002da98  mov     rdx, [rdi+78h]; Instance
0x14002da9c  mov     r15, rcx
0x14002da9f  mov     rcx, [rdi+68h]; Filter
0x14002daa3  mov     [rsp+0F0h+AllocationSize], r12; AllocationSize
0x14002daa8  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x14002daad  lea     rax, [rbp+37h+var_50]
0x14002dab1  mov     [rsp+0F0h+ObjectAttributes], rax; ObjectAttributes
0x14002dab6  mov     [rsp+0F0h+DesiredAccess], 120089h; DesiredAccess
0x14002dabe  mov     qword ptr [rbp+37h+var_50.Length], 30h ; '0'
0x14002dac6  mov     qword ptr [rbp+37h+var_50.Attributes], 240h
0x14002dace  movups  xmmword ptr [rbp+37h+var_60], xmm0
0x14002dad2  mov     [rbp+37h+FileHandle], r12
0x14002dad6  mov     [rbp+37h+FileObject], r12
0x14002dada  mov     [rbp+37h+BytesRead], r12d
0x14002dade  mov     qword ptr [rbp+37h+ByteOffset], r12
0x14002dae2  mov     [rbp+37h+var_50.RootDirectory], r12
0x14002dae6  movdqu  xmmword ptr [rbp+37h+var_50.SecurityDescriptor], xmm0
0x14002daeb  call    cs:__imp_FltCreateFileEx
0x14002daf2  nop     dword ptr [rax+rax+00h]
0x14002daf7  mov     ebx, eax
0x14002daf9  test    eax, eax
0x14002dafb  jns     short loc_14002DB44
0x14002dafd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002db04  mov     edx, [rcx+2Ch]
0x14002db07  test    dl, 8
0x14002db0a  jz      loc_14002DC91
0x14002db10  cmp     byte ptr [rcx+29h], 2
0x14002db14  jb      loc_14002DC91
0x14002db1a  mov     rcx, [rcx+18h]
0x14002db1e  lea     rax, [r14+40h]
0x14002db22  lea     edx, [r12+0Ch]
0x14002db27  mov     dword ptr [rsp+0F0h+ObjectAttributes], ebx
0x14002db2b  mov     r9, rsi
0x14002db2e  mov     qword ptr [rsp+0F0h+DesiredAccess], rax
0x14002db33  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002db3a  call    WPP_SF_ZZd
0x14002db3f  jmp     loc_14002DC91
0x14002db44  mov     rdx, [rbp+37h+FileObject]
0x14002db48  mov     rax, [rdx+28h]
0x14002db4c  test    rax, rax
0x14002db4f  jz      short loc_14002DBB1
0x14002db51  cmp     [rax], r12
0x14002db54  jz      short loc_14002DBB1
0x14002db56  mov     r8, rdx
0x14002db59  mov     byte ptr [rsp+0F0h+DesiredAccess], 1
0x14002db5e  mov     rdx, [rdi+78h]
0x14002db62  xor     r9d, r9d
0x14002db65  mov     rcx, r15
0x14002db68  call    WofFlushFile
0x14002db6d  mov     ebx, eax
0x14002db6f  test    eax, eax
0x14002db71  jns     short loc_14002DBAD
0x14002db73  mov     rcx, cs:WPP_GLOBAL_Control
0x14002db7a  mov     edx, [rcx+2Ch]
0x14002db7d  test    dl, 8
0x14002db80  jz      loc_14002DC67
0x14002db86  cmp     byte ptr [rcx+29h], 2
0x14002db8a  jb      loc_14002DC67
0x14002db90  mov     edx, 0Dh
0x14002db95  mov     r9d, eax
0x14002db98  mov     rcx, [rcx+18h]
0x14002db9c  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002dba3  call    WPP_SF_d
0x14002dba8  jmp     loc_14002DC67
0x14002dbad  mov     rdx, [rbp+37h+FileObject]; FileObject
0x14002dbb1  mov     rsi, [rbp+37h+Buffer]
0x14002dbb5  lea     rax, [rbp+37h+BytesRead]
0x14002dbb9  mov     rcx, [rdi+78h]; InitiatingInstance
0x14002dbbd  lea     r8, [rbp+37h+ByteOffset]; ByteOffset
0x14002dbc1  mov     qword ptr [rsp+0F0h+FileAttributes], r12; CallbackContext
0x14002dbc6  mov     r9d, 0D0h; Length
0x14002dbcc  mov     [rsp+0F0h+AllocationSize], r12; CallbackRoutine
0x14002dbd1  mov     [rsp+0F0h+IoStatusBlock], rax; BytesRead
0x14002dbd6  mov     dword ptr [rsp+0F0h+ObjectAttributes], r12d; Flags
0x14002dbdb  mov     qword ptr [rsp+0F0h+DesiredAccess], rsi; Buffer
0x14002dbe0  mov     qword ptr [rbp+37h+ByteOffset], r12
0x14002dbe4  call    cs:__imp_FltReadFile
0x14002dbeb  nop     dword ptr [rax+rax+00h]
0x14002dbf0  mov     ebx, eax
0x14002dbf2  test    eax, eax
0x14002dbf4  jns     short loc_14002DC14
0x14002dbf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dbfd  mov     eax, [rcx+2Ch]
0x14002dc00  test    al, 8
0x14002dc02  jz      short loc_14002DC67
0x14002dc04  cmp     byte ptr [rcx+29h], 2
0x14002dc08  jb      short loc_14002DC67
0x14002dc0a  mov     edx, 0Eh
0x14002dc0f  mov     r9d, ebx
0x14002dc12  jmp     short loc_14002DB98
0x14002dc14  mov     r9, [rbp+37h+arg_20]
0x14002dc18  mov     r8, rsi
0x14002dc1b  mov     rdx, [rbp+37h+FileObject]
0x14002dc1f  mov     rcx, [rdi+78h]
0x14002dc23  call    WimFSFValidateWim
0x14002dc28  mov     ebx, eax
0x14002dc2a  test    eax, eax
0x14002dc2c  jns     short loc_14002DC49
0x14002dc2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dc35  mov     eax, [rcx+2Ch]
0x14002dc38  test    al, 8
0x14002dc3a  jz      short loc_14002DC67
0x14002dc3c  cmp     byte ptr [rcx+29h], 2
0x14002dc40  jb      short loc_14002DC67
0x14002dc42  mov     edx, 0Fh
0x14002dc47  jmp     short loc_14002DC0F
0x14002dc49  mov     rax, [rbp+37h+FileObject]
0x14002dc4d  mov     rcx, [rbp+37h+arg_30]
0x14002dc51  mov     [rbp+37h+FileObject], r12
0x14002dc55  mov     [rcx], rax
0x14002dc58  mov     rcx, [rbp+37h+FileHandle]
0x14002dc5c  mov     rax, [rbp+37h+arg_28]
0x14002dc60  mov     [rbp+37h+FileHandle], r12
0x14002dc64  mov     [rax], rcx
0x14002dc67  mov     rcx, [rbp+37h+FileObject]; Object
0x14002dc6b  test    rcx, rcx
0x14002dc6e  jz      short loc_14002DC7C
0x14002dc70  call    cs:__imp_ObfDereferenceObject
0x14002dc77  nop     dword ptr [rax+rax+00h]
0x14002dc7c  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x14002dc80  test    rcx, rcx
0x14002dc83  jz      short loc_14002DC91
0x14002dc85  call    cs:__imp_FltClose
0x14002dc8c  nop     dword ptr [rax+rax+00h]
0x14002dc91  lea     r11, [rsp+0F0h+var_20]
0x14002dc99  mov     eax, ebx
0x14002dc9b  mov     rbx, [r11+30h]
0x14002dc9f  mov     rsi, [r11+38h]
0x14002dca3  mov     rsp, r11
0x14002dca6  pop     r15
0x14002dca8  pop     r14
0x14002dcaa  pop     r12
0x14002dcac  pop     rdi
0x14002dcad  pop     rbp
0x14002dcae  retn
```
