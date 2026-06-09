# WcRelativeStreamOpen

- ea: `0x14001fc48`
- end: `0x14001fe38`
- name: `WcRelativeStreamOpen`
- size: `496`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _FILE_OBJECT *, struct _UNICODE_STRING *, void **, PFILE_OBJECT *FileObject)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140017f64`
- `0x14001ef50`

## callees

- `0x1400048a4`
- `0x14001fc48`
- `0x140020434`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14001fcf5`
- `ntoskrnl!IoGetSilo` at `0x14001fcf5`
- `ntoskrnl!ObfDereferenceObject` at `0x14001fe0d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001fe0d`
- `FLTMGR!FltCreateFileEx2` at `0x14001fd88`
- `FLTMGR!FltCreateFileEx2` at `0x14001fd88`
- `FLTMGR!FltClose` at `0x14001fdf8`
- `FLTMGR!FltClose` at `0x14001fdf8`

## pseudocode

```c
__int64 __fastcall WcRelativeStreamOpen(
        PFLT_INSTANCE Instance,
        struct _FILE_OBJECT *a2,
        struct _UNICODE_STRING *a3,
        void **a4,
        PFILE_OBJECT *FileObject)
{
  NTSTATUS v9; // ebx
  PFILE_OBJECT *v10; // rcx
  int v11; // edx
  PVOID Object; // [rsp+80h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-39h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-29h] BYREF
  __int64 Silo; // [rsp+B8h] [rbp-9h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-1h] BYREF
  HANDLE FileHandle; // [rsp+130h] [rbp+6Fh] BYREF

  LOWORD(Silo) = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  Object = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&DriverContext, 0, sizeof(DriverContext));
  v9 = WcReopenFile(Instance, a2, &FileHandle, (PFILE_OBJECT *)&Object);
  if ( a3->Length )
  {
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    Silo = 1;
    Silo = IoGetSilo(a2);
    ObjectAttributes.RootDirectory = FileHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = a3;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = FltCreateFileEx2(
           Globals,
           Instance,
           a4,
           FileObject,
           0x80000000,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0,
           7u,
           1u,
           0x202028u,
           0,
           0,
           0,
           &DriverContext);
    if ( v9 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_sDZd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v11,
        10,
        107,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        133,
        (__int64)a3,
        v9);
    }
    if ( FileHandle )
      FltClose(FileHandle);
  }
  else
  {
    v10 = FileObject;
    *a4 = FileHandle;
    FileHandle = 0;
    if ( v10 )
    {
      *v10 = (PFILE_OBJECT)Object;
      return (unsigned int)v9;
    }
  }
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001fc48  mov     [rsp-8+arg_0], rbx
0x14001fc4d  mov     [rsp-8+arg_8], rsi
0x14001fc52  push    rbp
0x14001fc53  push    rdi
0x14001fc54  push    r12
0x14001fc56  push    r14
0x14001fc58  push    r15
0x14001fc5a  lea     rbp, [rsp-2Fh]
0x14001fc5f  sub     rsp, 0F0h
0x14001fc66  xorps   xmm0, xmm0
0x14001fc69  mov     rsi, r9
0x14001fc6c  mov     rdi, r8
0x14001fc6f  lea     r9, [rbp+4Fh+Object]; PFILE_OBJECT *
0x14001fc73  xor     eax, eax
0x14001fc75  lea     r8, [rbp+4Fh+FileHandle]; FileHandle
0x14001fc79  xor     r12d, r12d
0x14001fc7c  mov     word ptr [rbp+4Fh+var_58], ax
0x14001fc80  movups  xmmword ptr [rbp+4Fh+var_50.ObjectName], xmm0
0x14001fc84  mov     r14, rdx
0x14001fc87  mov     r15, rcx
0x14001fc8a  movups  xmmword ptr [rbp+4Fh+var_50+1Ch], xmm0
0x14001fc8e  mov     [rbp+4Fh+FileHandle], r12
0x14001fc92  movups  xmmword ptr [rbp+4Fh+var_88], xmm0
0x14001fc96  mov     [rbp+4Fh+Object], r12
0x14001fc9a  movups  xmmword ptr [rbp+4Fh+var_50.Length], xmm0
0x14001fc9e  movups  xmmword ptr [rbp+4Fh+var_78.Size], xmm0
0x14001fca2  movups  xmmword ptr [rbp+4Fh+var_78.DeviceObjectHint], xmm0
0x14001fca6  call    WcReopenFile
0x14001fcab  mov     ebx, eax
0x14001fcad  cmp     [rdi], r12w
0x14001fcb1  jnz     short loc_14001FCD7
0x14001fcb3  mov     rax, [rbp+4Fh+FileHandle]
0x14001fcb7  mov     rcx, [rbp+4Fh+FileObject]
0x14001fcbb  mov     [rsi], rax
0x14001fcbe  mov     [rbp+4Fh+FileHandle], r12
0x14001fcc2  test    rcx, rcx
0x14001fcc5  jz      loc_14001FE04
0x14001fccb  mov     rax, [rbp+4Fh+Object]
0x14001fccf  mov     [rcx], rax
0x14001fcd2  jmp     loc_14001FE19
0x14001fcd7  mov     eax, 28h ; '('
0x14001fcdc  xorps   xmm0, xmm0
0x14001fcdf  movups  xmmword ptr [rbp+4Fh+var_78.Size], xmm0
0x14001fce3  mov     rcx, r14
0x14001fce6  mov     [rbp+4Fh+var_78.Size], ax
0x14001fcea  movups  xmmword ptr [rbp+4Fh+var_78.DeviceObjectHint], xmm0
0x14001fcee  lea     ebx, [rax-27h]
0x14001fcf1  mov     [rbp+4Fh+var_58], rbx
0x14001fcf5  call    cs:__imp_IoGetSilo
0x14001fcfc  nop     dword ptr [rax+rax+00h]
0x14001fd01  mov     r9, [rbp+4Fh+FileObject]; FileObject
0x14001fd05  xorps   xmm0, xmm0
0x14001fd08  mov     rcx, cs:Globals; Filter
0x14001fd0f  mov     r8, rsi; FileHandle
0x14001fd12  mov     [rbp+4Fh+var_58], rax
0x14001fd16  mov     rdx, r15; Instance
0x14001fd19  mov     rax, [rbp+4Fh+FileHandle]
0x14001fd1d  mov     [rbp+4Fh+var_50.RootDirectory], rax
0x14001fd21  lea     rax, [rbp+4Fh+var_78]
0x14001fd25  mov     [rsp+110h+DriverContext], rax; DriverContext
0x14001fd2a  lea     rax, [rbp+4Fh+var_88]
0x14001fd2e  mov     [rsp+110h+Flags], r12d; Flags
0x14001fd33  mov     [rsp+110h+EaLength], r12d; EaLength
0x14001fd38  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x14001fd3d  mov     [rsp+110h+CreateOptions], 202028h; CreateOptions
0x14001fd45  mov     [rsp+110h+CreateDisposition], ebx; CreateDisposition
0x14001fd49  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x14001fd51  mov     [rsp+110h+FileAttributes], r12d; FileAttributes
0x14001fd56  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x14001fd5b  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14001fd60  lea     rax, [rbp+4Fh+var_50]
0x14001fd64  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x14001fd69  mov     [rsp+110h+DesiredAccess], 80000000h; DesiredAccess
0x14001fd71  mov     [rbp+4Fh+var_50.Length], 30h ; '0'
0x14001fd78  mov     [rbp+4Fh+var_50.Attributes], 200h
0x14001fd7f  mov     [rbp+4Fh+var_50.ObjectName], rdi
0x14001fd83  movdqu  xmmword ptr [rbp+4Fh+var_50.SecurityDescriptor], xmm0
0x14001fd88  call    cs:__imp_FltCreateFileEx2
0x14001fd8f  nop     dword ptr [rax+rax+00h]
0x14001fd94  mov     ebx, eax
0x14001fd96  test    eax, eax
0x14001fd98  jns     short loc_14001FDEF
0x14001fd9a  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fda1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fda8  jz      short loc_14001FDEF
0x14001fdaa  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001fdb1  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001fdb8  mov     [rsp+110h+FileAttributes], ebx
0x14001fdbc  mov     r9d, 6Bh ; 'k'
0x14001fdc2  mov     [rsp+110h+AllocationSize], rdi
0x14001fdc7  mov     dl, 2
0x14001fdc9  mov     dword ptr [rsp+110h+IoStatusBlock], 0C85h
0x14001fdd1  mov     rcx, [rcx+40h]
0x14001fdd5  mov     [rsp+110h+ObjectAttributes], rax
0x14001fdda  lea     r8d, [r9-61h]
0x14001fdde  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001fde5  mov     qword ptr [rsp+110h+DesiredAccess], rax
0x14001fdea  call    WPP_RECORDER_SF_sDZd
0x14001fdef  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14001fdf3  test    rcx, rcx
0x14001fdf6  jz      short loc_14001FE04
0x14001fdf8  call    cs:__imp_FltClose
0x14001fdff  nop     dword ptr [rax+rax+00h]
0x14001fe04  mov     rcx, [rbp+4Fh+Object]; Object
0x14001fe08  test    rcx, rcx
0x14001fe0b  jz      short loc_14001FE19
0x14001fe0d  call    cs:__imp_ObfDereferenceObject
0x14001fe14  nop     dword ptr [rax+rax+00h]
0x14001fe19  lea     r11, [rsp+110h+var_20]
0x14001fe21  mov     eax, ebx
0x14001fe23  mov     rbx, [r11+30h]
0x14001fe27  mov     rsi, [r11+38h]
0x14001fe2b  mov     rsp, r11
0x14001fe2e  pop     r15
0x14001fe30  pop     r14
0x14001fe32  pop     r12
0x14001fe34  pop     rdi
0x14001fe35  pop     rbp
0x14001fe36  retn
```
