# WcOpenAsReparsePoint

- ea: `0x14002cb38`
- end: `0x14002d640`
- name: `WcOpenAsReparsePoint`
- size: `2824`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *, __int64, struct _FLT_INSTANCE *, ACCESS_MASK DesiredAccess, int, void **, PFILE_OBJECT *, bool *, bool *, bool *, char *, bool *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001a62c`
- `0x14001c688`
- `0x14001ecb8`
- `0x14002bf4c`
- `0x140030da4`

## callees

- `0x1400020c4`
- `0x1400048a4`
- `0x14002cb38`
- `0x14002d7e0`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14002cc1d`
- `ntoskrnl!IoGetSilo` at `0x14002d342`
- `ntoskrnl!IoGetSilo` at `0x14002cc1d`
- `ntoskrnl!IoGetSilo` at `0x14002d342`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002d56a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002d585`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002d5a0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002d5bb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002d56a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002d585`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002d5a0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002d5bb`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002d011`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002d0dd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002d181`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002d225`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002d011`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002d0dd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002d181`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002d225`
- `ntoskrnl!ObfDereferenceObject` at `0x14002ced8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d5e5`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d60f`
- `ntoskrnl!ObfDereferenceObject` at `0x14002ced8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d5e5`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d60f`
- `FLTMGR!FltCreateFileEx2` at `0x14002ccba`
- `FLTMGR!FltCreateFileEx2` at `0x14002ceae`
- `FLTMGR!FltCreateFileEx2` at `0x14002d3de`
- `FLTMGR!FltCreateFileEx2` at `0x14002ccba`
- `FLTMGR!FltCreateFileEx2` at `0x14002ceae`
- `FLTMGR!FltCreateFileEx2` at `0x14002d3de`
- `FLTMGR!FltClose` at `0x14002cec8`
- `FLTMGR!FltClose` at `0x14002d5d0`
- `FLTMGR!FltClose` at `0x14002d5fa`
- `FLTMGR!FltClose` at `0x14002cec8`
- `FLTMGR!FltClose` at `0x14002d5d0`
- `FLTMGR!FltClose` at `0x14002d5fa`
- `FLTMGR!FltQueryInformationFile` at `0x14002cd34`
- `FLTMGR!FltQueryInformationFile` at `0x14002cd34`
- `FLTMGR!FltReleaseContext` at `0x14002d54f`
- `FLTMGR!FltReleaseContext` at `0x14002d54f`
- `FLTMGR!FltGetInstanceContext` at `0x14002cbd5`
- `FLTMGR!FltGetInstanceContext` at `0x14002cbd5`

## pseudocode

```c
__int64 __fastcall WcOpenAsReparsePoint(
        struct _UNICODE_STRING *a1,
        void *a2,
        __int64 a3,
        struct _FLT_INSTANCE *a4,
        ACCESS_MASK DesiredAccess,
        int a6,
        void **a7,
        PFILE_OBJECT *a8,
        bool *a9,
        bool *a10,
        bool *a11,
        char *a12,
        bool *a13)
{
  __int64 **v15; // rsi
  __int64 **v16; // r14
  __int64 **v17; // r15
  __int64 **v18; // r12
  int v19; // ecx
  NTSTATUS v20; // eax
  int v21; // edx
  unsigned int v22; // ebx
  int v23; // r9d
  NTSTATUS v24; // eax
  bool v25; // r10
  bool v26; // r11
  bool *v27; // r8
  bool *v28; // r9
  bool *v29; // rdx
  bool v30; // di
  bool *v31; // rcx
  bool v32; // r13
  NTSTATUS v33; // eax
  void *v34; // rax
  PFILE_OBJECT v35; // rax
  char *v36; // rax
  int v37; // edx
  int v38; // r9d
  __int64 ***v39; // rax
  char *v40; // rax
  __int64 ***v41; // rax
  char *v42; // rax
  __int64 ***v43; // rax
  char *v44; // rax
  __int64 ***v45; // rax
  int v46; // eax
  NTSTATUS v47; // eax
  void *v48; // rax
  char v49; // dl
  PFILE_OBJECT v50; // rax
  char IoStatusBlock; // [rsp+38h] [rbp-D0h]
  char IoStatusBlocka; // [rsp+38h] [rbp-D0h]
  PLARGE_INTEGER AllocationSize; // [rsp+40h] [rbp-C8h]
  char FileAttributes; // [rsp+48h] [rbp-C0h]
  char v56; // [rsp+8Ah] [rbp-7Eh]
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-78h] BYREF
  __int64 v58[2]; // [rsp+98h] [rbp-70h] BYREF
  void *FileHandle; // [rsp+A8h] [rbp-60h] BYREF
  HANDLE v60; // [rsp+B0h] [rbp-58h] BYREF
  PFILE_OBJECT v61; // [rsp+B8h] [rbp-50h] BYREF
  __int64 FileInformation; // [rsp+C0h] [rbp-48h] BYREF
  PFLT_CONTEXT Context; // [rsp+C8h] [rbp-40h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+D0h] [rbp-38h] BYREF
  __int64 Silo; // [rsp+F0h] [rbp-18h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-10h] BYREF
  struct _IO_STATUS_BLOCK v67; // [rsp+128h] [rbp+20h] BYREF

  Context = 0;
  FileHandle = 0;
  FileObject = 0;
  v60 = 0;
  *(_OWORD *)v58 = 0;
  v61 = 0;
  memset(&ObjectAttributes, 0, 44);
  FileInformation = 0;
  LOWORD(Silo) = 0;
  v67 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  if ( !a8 || !a7 )
    return 3221225485LL;
  v15 = 0;
  v56 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  FltGetInstanceContext(a4, &Context);
  v19 = *((_DWORD *)Context + 2);
  if ( v19 == 2 || v19 == 28 )
  {
    v58[1] = (__int64)v58;
    v58[0] = (__int64)v58;
    if ( a9 )
    {
      v36 = (char *)ExAllocateFromPagedLookasideList(&stru_14000E380);
      v15 = (__int64 **)v36;
      if ( !v36 )
      {
        v22 = -1073741670;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_98;
        v38 = 137;
        IoStatusBlocka = -26;
LABEL_50:
        LOBYTE(v37) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v37,
          10,
          v38,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          IoStatusBlocka,
          154);
        goto LABEL_98;
      }
      *((_QWORD *)v36 + 1) = v36;
      *(_QWORD *)v36 = v36;
      *(_OWORD *)(v36 + 24) = 0;
      *((_DWORD *)v36 + 4) = a6;
      *((_DWORD *)v36 + 5) = -2147483644;
      *((_DWORD *)v36 + 10) = 48;
      v39 = (__int64 ***)v58[1];
      if ( *(__int64 **)v58[1] != v58 )
LABEL_70:
        __fastfail(3u);
      v15[1] = (__int64 *)v58[1];
      *v15 = v58;
      *v39 = v15;
      v58[1] = (__int64)v15;
    }
    if ( a10 )
    {
      v40 = (char *)ExAllocateFromPagedLookasideList(&stru_14000E380);
      v16 = (__int64 **)v40;
      if ( !v40 )
      {
        v22 = -1073741670;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_98;
        v38 = 138;
        IoStatusBlocka = -11;
        goto LABEL_50;
      }
      *((_QWORD *)v40 + 1) = v40;
      *(_QWORD *)v40 = v40;
      *(_OWORD *)(v40 + 24) = 0;
      *((_DWORD *)v40 + 4) = -1610612724;
      *((_DWORD *)v40 + 5) = -2147483644;
      *((_WORD *)v40 + 20) = 48;
      *((_WORD *)v40 + 21) = 0;
      v41 = (__int64 ***)v58[1];
      if ( *(__int64 **)v58[1] != v58 )
        goto LABEL_70;
      v16[1] = (__int64 *)v58[1];
      *v16 = v58;
      *v41 = v16;
      v58[1] = (__int64)v16;
    }
    if ( a11 )
    {
      v42 = (char *)ExAllocateFromPagedLookasideList(&stru_14000E380);
      v17 = (__int64 **)v42;
      if ( !v42 )
      {
        v22 = -1073741670;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_98;
        v38 = 139;
        IoStatusBlocka = 4;
        goto LABEL_50;
      }
      *((_QWORD *)v42 + 1) = v42;
      *(_QWORD *)v42 = v42;
      *(_OWORD *)(v42 + 24) = 0;
      *((_DWORD *)v42 + 4) = -1610612733;
      *((_DWORD *)v42 + 5) = -2147483644;
      *((_WORD *)v42 + 20) = 48;
      *((_WORD *)v42 + 21) = 0;
      v43 = (__int64 ***)v58[1];
      if ( *(__int64 **)v58[1] != v58 )
        goto LABEL_70;
      v17[1] = (__int64 *)v58[1];
      *v17 = v58;
      *v43 = v17;
      v58[1] = (__int64)v17;
    }
    if ( a13 )
    {
      v44 = (char *)ExAllocateFromPagedLookasideList(&stru_14000E380);
      v18 = (__int64 **)v44;
      if ( !v44 )
      {
        v22 = -1073741670;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_98;
        v38 = 140;
        IoStatusBlocka = 19;
        goto LABEL_50;
      }
      *((_QWORD *)v44 + 1) = v44;
      *(_QWORD *)v44 = v44;
      *(_OWORD *)(v44 + 24) = 0;
      *((_DWORD *)v44 + 4) = -1610612705;
      *((_DWORD *)v44 + 5) = -2147483644;
      *((_WORD *)v44 + 20) = 48;
      *((_WORD *)v44 + 21) = 0;
      v45 = (__int64 ***)v58[1];
      if ( *(__int64 **)v58[1] != v58 )
        goto LABEL_70;
      v18[1] = (__int64 *)v58[1];
      *v18 = v58;
      *v45 = v18;
      v58[1] = (__int64)v18;
    }
    v46 = WcOpenReparsePoint(a4, DesiredAccess, 0x28u, 3u, (__int64)v58, a7, a8);
    v22 = v46;
    if ( v46 == -1073741191 )
    {
      Silo = 1;
      memset(&DriverContext, 0, sizeof(DriverContext));
      DriverContext.Size = 40;
      if ( a3 )
        Silo = IoGetSilo(a3);
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = a2;
      ObjectAttributes.ObjectName = a1;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v47 = FltCreateFileEx2(
              Globals,
              a4,
              &FileHandle,
              &FileObject,
              DesiredAccess,
              &ObjectAttributes,
              &v67,
              0,
              0,
              3u,
              1u,
              0x200028u,
              0,
              0,
              0x800u,
              &DriverContext);
      v22 = v47;
      if ( v47 < 0 )
      {
        if ( v47 == -1073741772
          || v47 == -1073741766
          || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          goto LABEL_98;
        }
        FileAttributes = v47;
        v23 = 141;
        AllocationSize = (PLARGE_INTEGER)a1;
        IoStatusBlock = 97;
        goto LABEL_80;
      }
      v48 = FileHandle;
      v49 = 1;
      FileHandle = 0;
      *a7 = v48;
      v50 = FileObject;
      FileObject = 0;
      *a8 = v50;
    }
    else
    {
      if ( v46 < 0 )
      {
        if ( v46 == -1073741772
          || v46 == -1073741766
          || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          goto LABEL_98;
        }
        FileAttributes = v46;
        v23 = 142;
        AllocationSize = (PLARGE_INTEGER)a1;
        IoStatusBlock = 118;
        goto LABEL_80;
      }
      v49 = 0;
    }
    if ( a9 )
      *a9 = *((_BYTE *)v15 + 20) & 1;
    if ( a10 )
      *a10 = *((_BYTE *)v16 + 20) & 1;
    if ( a11 )
      *a11 = *((_BYTE *)v17 + 20) & 1;
    if ( a12 )
      *a12 = v49;
    if ( a13 )
      *a13 = *((_BYTE *)v18 + 20) & 1;
    goto LABEL_98;
  }
  Silo = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  if ( a3 )
    Silo = IoGetSilo(a3);
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v20 = FltCreateFileEx2(
          Globals,
          a4,
          &FileHandle,
          &FileObject,
          DesiredAccess,
          &ObjectAttributes,
          &v67,
          0,
          0,
          3u,
          1u,
          0x200028u,
          0,
          0,
          0x800u,
          &DriverContext);
  v22 = v20;
  if ( v20 < 0 )
  {
    if ( v20 == -1073741772 || v20 == -1073741766 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_98;
    FileAttributes = v20;
    v23 = 143;
    AllocationSize = (PLARGE_INTEGER)a1;
    IoStatusBlock = -45;
    goto LABEL_80;
  }
  v24 = FltQueryInformationFile(a4, FileObject, &FileInformation, 8u, FileAttributeTagInformation, 0);
  v22 = v24;
  if ( v24 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      FileAttributes = v24;
      v23 = 144;
      AllocationSize = (PLARGE_INTEGER)a1;
      IoStatusBlock = -27;
LABEL_80:
      LOBYTE(v21) = 2;
      WPP_RECORDER_SF_sDZd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v21,
        10,
        v23,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        IoStatusBlock,
        (__int64)AllocationSize,
        FileAttributes);
      goto LABEL_98;
    }
    goto LABEL_98;
  }
  v25 = 0;
  v26 = 0;
  if ( (FileInformation & 0x400) == 0 )
    goto LABEL_26;
  if ( HIDWORD(FileInformation) == a6 )
  {
    v27 = a9;
    v25 = a9 != 0;
LABEL_27:
    v28 = a10;
    goto LABEL_28;
  }
  switch ( HIDWORD(FileInformation) )
  {
    case 0xA000000C:
      v28 = a10;
      v27 = a9;
      v26 = a10 != 0;
LABEL_28:
      v29 = a11;
      v30 = 0;
      goto LABEL_29;
    case 0xA0000003:
      v29 = a11;
      v27 = a9;
      v28 = a10;
      v30 = a11 != 0;
LABEL_29:
      v32 = 0;
LABEL_30:
      v31 = a13;
      goto LABEL_31;
    case 0xA000001F:
      v31 = a13;
      v30 = 0;
      v29 = a11;
      v27 = a9;
      v28 = a10;
      v32 = a13 != 0;
LABEL_31:
      if ( a12 )
      {
        *a12 = v56;
        v31 = a13;
      }
      if ( v27 )
        *v27 = v25;
      if ( v28 )
        *v28 = v26;
      if ( v29 )
        *v29 = v30;
      if ( v31 )
        *v31 = v32;
      v34 = FileHandle;
      FileHandle = 0;
      *a7 = v34;
      v35 = FileObject;
      FileObject = 0;
      *a8 = v35;
      goto LABEL_98;
  }
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v33 = FltCreateFileEx2(
          Globals,
          a4,
          &v60,
          &v61,
          DesiredAccess,
          &ObjectAttributes,
          &v67,
          0,
          0,
          3u,
          1u,
          0x28u,
          0,
          0,
          0x800u,
          &DriverContext);
  v22 = v33;
  if ( v33 >= 0 )
  {
    FltClose(FileHandle);
    ObfDereferenceObject(FileObject);
    v25 = 0;
    FileHandle = v60;
    v26 = 0;
    FileObject = v61;
    v60 = 0;
    v61 = 0;
LABEL_26:
    v27 = a9;
    goto LABEL_27;
  }
  if ( v33 == -1073741191 )
  {
    v29 = a11;
    v22 = 0;
    v27 = a9;
    v25 = 0;
    v28 = a10;
    v26 = 0;
    v56 = 1;
    v32 = 0;
    v30 = 0;
    goto LABEL_30;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    FileAttributes = v33;
    v23 = 145;
    AllocationSize = (PLARGE_INTEGER)a1;
    IoStatusBlock = 64;
    goto LABEL_80;
  }
LABEL_98:
  if ( Context )
    FltReleaseContext(Context);
  if ( v15 )
    ExFreeToPagedLookasideList(&stru_14000E380, v15);
  if ( v16 )
    ExFreeToPagedLookasideList(&stru_14000E380, v16);
  if ( v17 )
    ExFreeToPagedLookasideList(&stru_14000E380, v17);
  if ( v18 )
    ExFreeToPagedLookasideList(&stru_14000E380, v18);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v60 )
    FltClose(v60);
  if ( v61 )
    ObfDereferenceObject(v61);
  return v22;
}

```

## disassembly

```asm
0x14002cb38  mov     rax, rsp
0x14002cb3b  mov     [rax+8], rbx
0x14002cb3f  mov     [rax+20h], r9
0x14002cb43  mov     [rax+18h], r8
0x14002cb47  mov     [rax+10h], rdx
0x14002cb4b  push    rbp
0x14002cb4c  push    rsi
0x14002cb4d  push    rdi
0x14002cb4e  push    r12
0x14002cb50  push    r13
0x14002cb52  push    r14
0x14002cb54  push    r15
0x14002cb56  lea     rbp, [rax-68h]
0x14002cb5a  sub     rsp, 130h
0x14002cb61  xor     edx, edx
0x14002cb63  xorps   xmm0, xmm0
0x14002cb66  mov     r13, rcx
0x14002cb69  mov     [rbp+60h+Context], rdx
0x14002cb6d  xor     ecx, ecx
0x14002cb6f  mov     [rbp+60h+FileHandle], rdx
0x14002cb73  mov     rbx, r8
0x14002cb76  mov     [rbp+60h+FileObject], rdx
0x14002cb7a  movups  xmmword ptr [rbp+60h+var_70.ObjectName], xmm0
0x14002cb7e  mov     [rbp+60h+var_B8], rdx
0x14002cb82  movups  xmmword ptr [rbp+60h+var_D0], xmm0
0x14002cb86  mov     [rbp+60h+var_B0], rdx
0x14002cb8a  movups  xmmword ptr [rbp+60h+var_70.Length], xmm0
0x14002cb8e  mov     [rbp+60h+FileInformation], rdx
0x14002cb92  movups  xmmword ptr [rbp+60h+var_70+1Ch], xmm0
0x14002cb96  mov     word ptr [rbp+60h+var_78], cx
0x14002cb9a  movups  xmmword ptr [rbp+60h+var_40], xmm0
0x14002cb9e  movups  xmmword ptr [rbp+60h+DriverContext.Size], xmm0
0x14002cba2  movups  xmmword ptr [rbp+60h+DriverContext.DeviceObjectHint], xmm0
0x14002cba6  cmp     [rbp+60h+arg_38], rdx
0x14002cbad  jz      loc_14002D61F
0x14002cbb3  cmp     [rbp+60h+arg_30], rdx
0x14002cbba  jz      loc_14002D61F
0x14002cbc0  mov     esi, edx
0x14002cbc2  mov     [rbp+60h+var_DE], dl
0x14002cbc5  mov     r14d, edx
0x14002cbc8  mov     r15d, edx
0x14002cbcb  mov     r12d, edx
0x14002cbce  mov     rcx, r9; Instance
0x14002cbd1  lea     rdx, [rbp+60h+Context]; Context
0x14002cbd5  call    cs:__imp_FltGetInstanceContext
0x14002cbdc  nop     dword ptr [rax+rax+00h]
0x14002cbe1  mov     rax, [rbp+60h+Context]
0x14002cbe5  mov     ecx, [rax+8]
0x14002cbe8  cmp     ecx, 2
0x14002cbeb  jz      loc_14002CFE8
0x14002cbf1  cmp     ecx, 1Ch
0x14002cbf4  jz      loc_14002CFE8
0x14002cbfa  lea     eax, [r12+28h]
0x14002cbff  xorps   xmm0, xmm0
0x14002cc02  lea     edi, [rax-27h]
0x14002cc05  mov     [rbp+60h+var_78], rdi
0x14002cc09  movups  xmmword ptr [rbp+60h+DriverContext.Size], xmm0
0x14002cc0d  mov     [rbp+60h+DriverContext.Size], ax
0x14002cc11  movups  xmmword ptr [rbp+60h+DriverContext.DeviceObjectHint], xmm0
0x14002cc15  test    rbx, rbx
0x14002cc18  jz      short loc_14002CC2D
0x14002cc1a  mov     rcx, rbx
0x14002cc1d  call    cs:__imp_IoGetSilo
0x14002cc24  nop     dword ptr [rax+rax+00h]
0x14002cc29  mov     [rbp+60h+var_78], rax
0x14002cc2d  mov     rax, [rbp+60h+arg_8]
0x14002cc31  lea     r9, [rbp+60h+FileObject]; FileObject
0x14002cc35  mov     rdx, [rbp+60h+Instance]; Instance
0x14002cc3c  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x14002cc40  mov     rcx, cs:Globals; Filter
0x14002cc47  xorps   xmm0, xmm0
0x14002cc4a  mov     [rbp+60h+var_70.RootDirectory], rax
0x14002cc4e  lea     rax, [rbp+60h+DriverContext]
0x14002cc52  mov     [rsp+78h], rax; DriverContext
0x14002cc57  xor     eax, eax
0x14002cc59  mov     [rsp+160h+Flags], 800h; Flags
0x14002cc61  mov     [rsp+160h+EaLength], eax; EaLength
0x14002cc65  mov     [rsp+160h+EaBuffer], rax; EaBuffer
0x14002cc6a  mov     [rsp+160h+CreateOptions], 200028h; CreateOptions
0x14002cc72  mov     [rsp+160h+CreateDisposition], edi; CreateDisposition
0x14002cc76  mov     [rsp+160h+ShareAccess], 3; ShareAccess
0x14002cc7e  mov     [rsp+160h+FileAttributes], eax; FileAttributes
0x14002cc82  mov     [rsp+160h+AllocationSize], rax; AllocationSize
0x14002cc87  lea     rax, [rbp+60h+var_40]
0x14002cc8b  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14002cc90  lea     rax, [rbp+60h+var_70]
0x14002cc94  mov     [rsp+160h+ObjectAttributes], rax; ObjectAttributes
0x14002cc99  mov     eax, [rbp+60h+arg_20]
0x14002cc9f  mov     [rsp+160h+DesiredAccess], eax; DesiredAccess
0x14002cca3  mov     [rbp+60h+var_70.Length], 30h ; '0'
0x14002ccaa  mov     [rbp+60h+var_70.Attributes], 240h
0x14002ccb1  mov     [rbp+60h+var_70.ObjectName], r13
0x14002ccb5  movdqu  xmmword ptr [rbp+60h+var_70.SecurityDescriptor], xmm0
0x14002ccba  call    cs:__imp_FltCreateFileEx2
0x14002ccc1  nop     dword ptr [rax+rax+00h]
0x14002ccc6  mov     ebx, eax
0x14002ccc8  test    eax, eax
0x14002ccca  jns     short loc_14002CD12
0x14002cccc  cmp     eax, 0C0000034h
0x14002ccd1  jz      loc_14002D546
0x14002ccd7  cmp     eax, 0C000003Ah
0x14002ccdc  jz      loc_14002D546
0x14002cce2  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002cce9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002ccf0  jz      loc_14002D546
0x14002ccf6  mov     [rsp+160h+FileAttributes], eax
0x14002ccfa  mov     r9d, 8Fh
0x14002cd00  mov     [rsp+160h+AllocationSize], r13
0x14002cd05  mov     dword ptr [rsp+160h+IoStatusBlock], 13D3h
0x14002cd0d  jmp     loc_14002D431
0x14002cd12  mov     rdx, [rbp+60h+FileObject]; FileObject
0x14002cd16  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x14002cd1a  mov     rcx, [rbp+60h+Instance]; Instance
0x14002cd21  mov     r9d, 8; Length
0x14002cd27  mov     [rsp+160h+ObjectAttributes], rsi; LengthReturned
0x14002cd2c  mov     [rsp+160h+DesiredAccess], 23h ; '#'; FileInformationClass
0x14002cd34  call    cs:__imp_FltQueryInformationFile
0x14002cd3b  nop     dword ptr [rax+rax+00h]
0x14002cd40  mov     ebx, eax
0x14002cd42  test    eax, eax
0x14002cd44  jns     short loc_14002CD76
0x14002cd46  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002cd4d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cd54  jz      loc_14002D546
0x14002cd5a  mov     [rsp+160h+FileAttributes], eax
0x14002cd5e  mov     r9d, 90h
0x14002cd64  mov     [rsp+160h+AllocationSize], r13
0x14002cd69  mov     dword ptr [rsp+160h+IoStatusBlock], 13E5h
0x14002cd71  jmp     loc_14002D431
0x14002cd76  xor     r10b, r10b
0x14002cd79  xor     r11b, r11b
0x14002cd7c  test    dword ptr [rbp+60h+FileInformation], 400h
0x14002cd83  jz      loc_14002CF02
0x14002cd89  mov     eax, dword ptr [rbp+60h+FileInformation+4]
0x14002cd8c  cmp     eax, [rbp+60h+arg_28]
0x14002cd92  jnz     short loc_14002CDA7
0x14002cd94  mov     r8, [rbp+60h+arg_40]
0x14002cd9b  test    r8, r8
0x14002cd9e  setnz   r10b
0x14002cda2  jmp     loc_14002CF09
0x14002cda7  cmp     eax, 0A000000Ch
0x14002cdac  jnz     short loc_14002CDC8
0x14002cdae  mov     r9, [rbp+60h+arg_48]
0x14002cdb5  mov     r8, [rbp+60h+arg_40]
0x14002cdbc  test    r9, r9
0x14002cdbf  setnz   r11b
0x14002cdc3  jmp     loc_14002CF10
0x14002cdc8  cmp     eax, 0A0000003h
0x14002cdcd  jnz     short loc_14002CDF0
0x14002cdcf  mov     rdx, [rbp+60h+arg_50]
0x14002cdd6  mov     r8, [rbp+60h+arg_40]
0x14002cddd  test    rdx, rdx
0x14002cde0  mov     r9, [rbp+60h+arg_48]
0x14002cde7  setnz   dil
0x14002cdeb  jmp     loc_14002CF1A
0x14002cdf0  cmp     eax, 0A000001Fh
0x14002cdf5  jnz     short loc_14002CE22
0x14002cdf7  mov     rcx, [rbp+60h+arg_60]
0x14002cdfe  mov     dil, sil
0x14002ce01  mov     rdx, [rbp+60h+arg_50]
0x14002ce08  test    rcx, rcx
0x14002ce0b  mov     r8, [rbp+60h+arg_40]
0x14002ce12  mov     r9, [rbp+60h+arg_48]
0x14002ce19  setnz   r13b
0x14002ce1d  jmp     loc_14002CF24
0x14002ce22  mov     rdx, [rbp+60h+Instance]; Instance
0x14002ce29  lea     r9, [rbp+60h+var_B0]; FileObject
0x14002ce2d  mov     rcx, cs:Globals; Filter
0x14002ce34  lea     r8, [rbp+60h+var_B8]; FileHandle
0x14002ce38  mov     eax, 30h ; '0'
0x14002ce3d  mov     [rbp+60h+var_70.Attributes], 240h
0x14002ce44  mov     [rbp+60h+var_70.Length], eax
0x14002ce47  xorps   xmm0, xmm0
0x14002ce4a  mov     rax, [rbp+60h+arg_8]
0x14002ce4e  mov     [rbp+60h+var_70.RootDirectory], rax
0x14002ce52  lea     rax, [rbp+60h+DriverContext]
0x14002ce56  mov     [rsp+78h], rax; DriverContext
0x14002ce5b  lea     rax, [rbp+60h+var_40]
0x14002ce5f  mov     [rsp+160h+Flags], 800h; Flags
0x14002ce67  mov     [rsp+160h+EaLength], esi; EaLength
0x14002ce6b  mov     [rsp+160h+EaBuffer], rsi; EaBuffer
0x14002ce70  mov     [rsp+160h+CreateOptions], 28h ; '('; CreateOptions
0x14002ce78  mov     [rsp+160h+CreateDisposition], edi; CreateDisposition
0x14002ce7c  mov     [rsp+160h+ShareAccess], 3; ShareAccess
0x14002ce84  mov     [rsp+160h+FileAttributes], esi; FileAttributes
0x14002ce88  mov     [rsp+160h+AllocationSize], rsi; AllocationSize
0x14002ce8d  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x14002ce92  lea     rax, [rbp+60h+var_70]
0x14002ce96  mov     [rsp+160h+ObjectAttributes], rax; ObjectAttributes
0x14002ce9b  mov     eax, [rbp+60h+arg_20]
0x14002cea1  mov     [rsp+160h+DesiredAccess], eax; DesiredAccess
0x14002cea5  mov     [rbp+60h+var_70.ObjectName], r13
0x14002cea9  movdqu  xmmword ptr [rbp+60h+var_70.SecurityDescriptor], xmm0
0x14002ceae  call    cs:__imp_FltCreateFileEx2
0x14002ceb5  nop     dword ptr [rax+rax+00h]
0x14002ceba  mov     ebx, eax
0x14002cebc  test    eax, eax
0x14002cebe  js      loc_14002CF85
0x14002cec4  mov     rcx, [rbp+60h+FileHandle]; FileHandle
0x14002cec8  call    cs:__imp_FltClose
0x14002cecf  nop     dword ptr [rax+rax+00h]
0x14002ced4  mov     rcx, [rbp+60h+FileObject]; Object
0x14002ced8  call    cs:__imp_ObfDereferenceObject
0x14002cedf  nop     dword ptr [rax+rax+00h]
0x14002cee4  mov     rax, [rbp+60h+var_B8]
0x14002cee8  mov     r10b, sil
0x14002ceeb  mov     [rbp+60h+FileHandle], rax
0x14002ceef  mov     r11b, sil
0x14002cef2  mov     rax, [rbp+60h+var_B0]
0x14002cef6  mov     [rbp+60h+FileObject], rax
0x14002cefa  mov     [rbp+60h+var_B8], rsi
0x14002cefe  mov     [rbp+60h+var_B0], rsi
0x14002cf02  mov     r8, [rbp+60h+arg_40]
0x14002cf09  mov     r9, [rbp+60h+arg_48]
0x14002cf10  mov     rdx, [rbp+60h+arg_50]
0x14002cf17  mov     dil, sil
0x14002cf1a  mov     r13b, sil
0x14002cf1d  mov     rcx, [rbp+60h+arg_60]
0x14002cf24  mov     rax, [rbp+60h+arg_58]
0x14002cf2b  test    rax, rax
0x14002cf2e  jz      short loc_14002CF3C
0x14002cf30  mov     cl, [rbp+60h+var_DE]
0x14002cf33  mov     [rax], cl
0x14002cf35  mov     rcx, [rbp+60h+arg_60]
0x14002cf3c  test    r8, r8
0x14002cf3f  jz      short loc_14002CF44
0x14002cf41  mov     [r8], r10b
0x14002cf44  test    r9, r9
0x14002cf47  jz      short loc_14002CF4C
0x14002cf49  mov     [r9], r11b
0x14002cf4c  test    rdx, rdx
0x14002cf4f  jz      short loc_14002CF54
0x14002cf51  mov     [rdx], dil
0x14002cf54  test    rcx, rcx
0x14002cf57  jz      short loc_14002CF5C
0x14002cf59  mov     [rcx], r13b
0x14002cf5c  mov     rax, [rbp+60h+FileHandle]
0x14002cf60  mov     rcx, [rbp+60h+arg_30]
0x14002cf67  mov     [rbp+60h+FileHandle], rsi
0x14002cf6b  mov     [rcx], rax
0x14002cf6e  mov     rax, [rbp+60h+FileObject]
0x14002cf72  mov     rcx, [rbp+60h+arg_38]
0x14002cf79  mov     [rbp+60h+FileObject], rsi
0x14002cf7d  mov     [rcx], rax
0x14002cf80  jmp     loc_14002D546
0x14002cf85  cmp     eax, 0C0000279h
0x14002cf8a  jnz     short loc_14002CFB8
0x14002cf8c  mov     rdx, [rbp+60h+arg_50]
0x14002cf93  xor     ebx, ebx
0x14002cf95  mov     r8, [rbp+60h+arg_40]
0x14002cf9c  mov     r10b, bl
0x14002cf9f  mov     r9, [rbp+60h+arg_48]
0x14002cfa6  mov     r11b, bl
0x14002cfa9  mov     [rbp+60h+var_DE], dil
0x14002cfad  mov     r13b, bl
0x14002cfb0  mov     dil, bl
0x14002cfb3  jmp     loc_14002CF1D
0x14002cfb8  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002cfbf  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cfc6  jz      loc_14002D546
0x14002cfcc  mov     [rsp+160h+FileAttributes], eax
0x14002cfd0  mov     r9d, 91h
0x14002cfd6  mov     [rsp+160h+AllocationSize], r13
0x14002cfdb  mov     dword ptr [rsp+160h+IoStatusBlock], 1440h
0x14002cfe3  jmp     loc_14002D431
0x14002cfe8  lea     rax, [rbp+60h+var_D0]
0x14002cfec  mov     edi, 30h ; '0'
0x14002cff1  mov     [rbp+60h+var_D0+8], rax
0x14002cff5  lea     rax, [rbp+60h+var_D0]
0x14002cff9  mov     [rbp+60h+var_D0], rax
0x14002cffd  cmp     [rbp+60h+arg_40], rsi
0x14002d004  jz      loc_14002D0C9
0x14002d00a  lea     rcx, stru_14000E380; Lookaside
0x14002d011  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14002d018  nop     dword ptr [rax+rax+00h]
0x14002d01d  mov     rsi, rax
0x14002d020  test    rax, rax
0x14002d023  jnz     short loc_14002D085
0x14002d025  mov     eax, 0C000009Ah
0x14002d02a  mov     ebx, eax
0x14002d02c  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d033  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d03a  jz      loc_14002D546
0x14002d040  mov     dword ptr [rsp+160h+AllocationSize], eax
0x14002d044  lea     r9d, [rdi+59h]
0x14002d048  mov     dword ptr [rsp+160h+IoStatusBlock], 12E6h
0x14002d050  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002d057  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002d05e  mov     [rsp+160h+ObjectAttributes], rax
0x14002d063  mov     r8d, 0Ah
0x14002d069  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002d070  mov     dl, 2
0x14002d072  mov     qword ptr [rsp+160h+DesiredAccess], rax
0x14002d077  mov     rcx, [rcx+40h]
0x14002d07b  call    WPP_RECORDER_SF_sDd
0x14002d080  jmp     loc_14002D546
0x14002d085  mov     [rax+8], rsi
0x14002d089  lea     rcx, [rbp+60h+var_D0]
0x14002d08d  mov     [rax], rsi
0x14002d090  xorps   xmm0, xmm0
  ... truncated ...
```
