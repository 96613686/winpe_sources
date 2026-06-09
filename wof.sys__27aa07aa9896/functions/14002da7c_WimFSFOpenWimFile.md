# WimFSFOpenWimFile

- ea: `0x14002da7c`
- end: `0x14002dd00`
- name: `WimFSFOpenWimFile`
- size: `644`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, PVOID Buffer)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140026440`
- `0x14002d990`
- `0x14002dd10`

## callees

- `0x14000d3b8`
- `0x14000ed74`
- `0x14000fc08`
- `0x14002da7c`
- `0x14002e008`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002dcc0`
- `ntoskrnl!ObfDereferenceObject` at `0x14002dcc0`
- `FLTMGR!FltReadFile` at `0x14002dc34`
- `FLTMGR!FltReadFile` at `0x14002dc34`
- `FLTMGR!FltCreateFileEx` at `0x14002db3b`
- `FLTMGR!FltCreateFileEx` at `0x14002db3b`
- `FLTMGR!FltClose` at `0x14002dcd5`
- `FLTMGR!FltClose` at `0x14002dcd5`

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
0x14002da7c  mov     [rsp-8+arg_0], rbx
0x14002da81  mov     [rsp-8+arg_8], rsi
0x14002da86  push    rbp
0x14002da87  push    rdi
0x14002da88  push    r12
0x14002da8a  push    r14
0x14002da8c  push    r15
0x14002da8e  lea     rbp, [rsp-17h]
0x14002da93  sub     rsp, 0D0h
0x14002da9a  mov     [rsp+0F0h+Flags], 1; Flags
0x14002daa2  lea     rax, [rbp+37h+var_60]
0x14002daa6  xor     r12d, r12d
0x14002daa9  mov     [rbp+37h+var_50.ObjectName], r9
0x14002daad  mov     [rsp+0F0h+EaLength], r12d; EaLength
0x14002dab2  mov     rdi, r8
0x14002dab5  mov     [rsp+0F0h+EaBuffer], r12; EaBuffer
0x14002daba  lea     r8, [rbp+37h+FileHandle]; FileHandle
0x14002dabe  mov     [rsp+0F0h+CreateOptions], 40h ; '@'; CreateOptions
0x14002dac6  xorps   xmm0, xmm0
0x14002dac9  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x14002dad1  mov     rsi, r9
0x14002dad4  mov     [rsp+0F0h+ShareAccess], 1; ShareAccess
0x14002dadc  lea     r9, [rbp+37h+FileObject]; FileObject
0x14002dae0  mov     [rsp+0F0h+FileAttributes], r12d; FileAttributes
0x14002dae5  mov     r14, rdx
0x14002dae8  mov     rdx, [rdi+78h]; Instance
0x14002daec  mov     r15, rcx
0x14002daef  mov     rcx, [rdi+68h]; Filter
0x14002daf3  mov     [rsp+0F0h+AllocationSize], r12; AllocationSize
0x14002daf8  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x14002dafd  lea     rax, [rbp+37h+var_50]
0x14002db01  mov     [rsp+0F0h+ObjectAttributes], rax; ObjectAttributes
0x14002db06  mov     [rsp+0F0h+DesiredAccess], 120089h; DesiredAccess
0x14002db0e  mov     qword ptr [rbp+37h+var_50.Length], 30h ; '0'
0x14002db16  mov     qword ptr [rbp+37h+var_50.Attributes], 240h
0x14002db1e  movups  xmmword ptr [rbp+37h+var_60], xmm0
0x14002db22  mov     [rbp+37h+FileHandle], r12
0x14002db26  mov     [rbp+37h+FileObject], r12
0x14002db2a  mov     [rbp+37h+BytesRead], r12d
0x14002db2e  mov     qword ptr [rbp+37h+ByteOffset], r12
0x14002db32  mov     [rbp+37h+var_50.RootDirectory], r12
0x14002db36  movdqu  xmmword ptr [rbp+37h+var_50.SecurityDescriptor], xmm0
0x14002db3b  call    cs:__imp_FltCreateFileEx
0x14002db42  nop     dword ptr [rax+rax+00h]
0x14002db47  mov     ebx, eax
0x14002db49  test    eax, eax
0x14002db4b  jns     short loc_14002DB94
0x14002db4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002db54  mov     edx, [rcx+2Ch]
0x14002db57  test    dl, 8
0x14002db5a  jz      loc_14002DCE1
0x14002db60  cmp     byte ptr [rcx+29h], 2
0x14002db64  jb      loc_14002DCE1
0x14002db6a  mov     rcx, [rcx+18h]
0x14002db6e  lea     rax, [r14+40h]
0x14002db72  lea     edx, [r12+0Ch]
0x14002db77  mov     dword ptr [rsp+0F0h+ObjectAttributes], ebx
0x14002db7b  mov     r9, rsi
0x14002db7e  mov     qword ptr [rsp+0F0h+DesiredAccess], rax
0x14002db83  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002db8a  call    WPP_SF_ZZd
0x14002db8f  jmp     loc_14002DCE1
0x14002db94  mov     rdx, [rbp+37h+FileObject]
0x14002db98  mov     rax, [rdx+28h]
0x14002db9c  test    rax, rax
0x14002db9f  jz      short loc_14002DC01
0x14002dba1  cmp     [rax], r12
0x14002dba4  jz      short loc_14002DC01
0x14002dba6  mov     r8, rdx
0x14002dba9  mov     byte ptr [rsp+0F0h+DesiredAccess], 1
0x14002dbae  mov     rdx, [rdi+78h]
0x14002dbb2  xor     r9d, r9d
0x14002dbb5  mov     rcx, r15
0x14002dbb8  call    WofFlushFile
0x14002dbbd  mov     ebx, eax
0x14002dbbf  test    eax, eax
0x14002dbc1  jns     short loc_14002DBFD
0x14002dbc3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dbca  mov     edx, [rcx+2Ch]
0x14002dbcd  test    dl, 8
0x14002dbd0  jz      loc_14002DCB7
0x14002dbd6  cmp     byte ptr [rcx+29h], 2
0x14002dbda  jb      loc_14002DCB7
0x14002dbe0  mov     edx, 0Dh
0x14002dbe5  mov     r9d, eax
0x14002dbe8  mov     rcx, [rcx+18h]
0x14002dbec  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002dbf3  call    WPP_SF_d
0x14002dbf8  jmp     loc_14002DCB7
0x14002dbfd  mov     rdx, [rbp+37h+FileObject]; FileObject
0x14002dc01  mov     rsi, [rbp+37h+Buffer]
0x14002dc05  lea     rax, [rbp+37h+BytesRead]
0x14002dc09  mov     rcx, [rdi+78h]; InitiatingInstance
0x14002dc0d  lea     r8, [rbp+37h+ByteOffset]; ByteOffset
0x14002dc11  mov     qword ptr [rsp+0F0h+FileAttributes], r12; CallbackContext
0x14002dc16  mov     r9d, 0D0h; Length
0x14002dc1c  mov     [rsp+0F0h+AllocationSize], r12; CallbackRoutine
0x14002dc21  mov     [rsp+0F0h+IoStatusBlock], rax; BytesRead
0x14002dc26  mov     dword ptr [rsp+0F0h+ObjectAttributes], r12d; Flags
0x14002dc2b  mov     qword ptr [rsp+0F0h+DesiredAccess], rsi; Buffer
0x14002dc30  mov     qword ptr [rbp+37h+ByteOffset], r12
0x14002dc34  call    cs:__imp_FltReadFile
0x14002dc3b  nop     dword ptr [rax+rax+00h]
0x14002dc40  mov     ebx, eax
0x14002dc42  test    eax, eax
0x14002dc44  jns     short loc_14002DC64
0x14002dc46  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dc4d  mov     eax, [rcx+2Ch]
0x14002dc50  test    al, 8
0x14002dc52  jz      short loc_14002DCB7
0x14002dc54  cmp     byte ptr [rcx+29h], 2
0x14002dc58  jb      short loc_14002DCB7
0x14002dc5a  mov     edx, 0Eh
0x14002dc5f  mov     r9d, ebx
0x14002dc62  jmp     short loc_14002DBE8
0x14002dc64  mov     r9, [rbp+37h+arg_20]
0x14002dc68  mov     r8, rsi
0x14002dc6b  mov     rdx, [rbp+37h+FileObject]
0x14002dc6f  mov     rcx, [rdi+78h]
0x14002dc73  call    WimFSFValidateWim
0x14002dc78  mov     ebx, eax
0x14002dc7a  test    eax, eax
0x14002dc7c  jns     short loc_14002DC99
0x14002dc7e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dc85  mov     eax, [rcx+2Ch]
0x14002dc88  test    al, 8
0x14002dc8a  jz      short loc_14002DCB7
0x14002dc8c  cmp     byte ptr [rcx+29h], 2
0x14002dc90  jb      short loc_14002DCB7
0x14002dc92  mov     edx, 0Fh
0x14002dc97  jmp     short loc_14002DC5F
0x14002dc99  mov     rax, [rbp+37h+FileObject]
0x14002dc9d  mov     rcx, [rbp+37h+arg_30]
0x14002dca1  mov     [rbp+37h+FileObject], r12
0x14002dca5  mov     [rcx], rax
0x14002dca8  mov     rcx, [rbp+37h+FileHandle]
0x14002dcac  mov     rax, [rbp+37h+arg_28]
0x14002dcb0  mov     [rbp+37h+FileHandle], r12
0x14002dcb4  mov     [rax], rcx
0x14002dcb7  mov     rcx, [rbp+37h+FileObject]; Object
0x14002dcbb  test    rcx, rcx
0x14002dcbe  jz      short loc_14002DCCC
0x14002dcc0  call    cs:__imp_ObfDereferenceObject
0x14002dcc7  nop     dword ptr [rax+rax+00h]
0x14002dccc  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x14002dcd0  test    rcx, rcx
0x14002dcd3  jz      short loc_14002DCE1
0x14002dcd5  call    cs:__imp_FltClose
0x14002dcdc  nop     dword ptr [rax+rax+00h]
0x14002dce1  lea     r11, [rsp+0F0h+var_20]
0x14002dce9  mov     eax, ebx
0x14002dceb  mov     rbx, [r11+30h]
0x14002dcef  mov     rsi, [r11+38h]
0x14002dcf3  mov     rsp, r11
0x14002dcf6  pop     r15
0x14002dcf8  pop     r14
0x14002dcfa  pop     r12
0x14002dcfc  pop     rdi
0x14002dcfd  pop     rbp
0x14002dcfe  retn
```
