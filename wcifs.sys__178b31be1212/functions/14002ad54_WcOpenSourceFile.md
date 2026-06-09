# WcOpenSourceFile

- ea: `0x14002ad54`
- end: `0x14002b68f`
- name: `WcOpenSourceFile`
- size: `2363`
- prototype: `__int64 __fastcall(__int64, __int64, struct _FLT_INSTANCE *, void *, UNICODE_STRING *Source, ULONG CreateOptions, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140029504`
- `0x14002a664`

## callees

- `0x1400020c4`
- `0x1400048a4`
- `0x140007c60`
- `0x14002ad54`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14002b20a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002b20a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002adeb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002adeb`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b66a`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b66a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b21d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b21d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b62a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b67e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b62a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b67e`
- `ntoskrnl!ExAllocatePool2` at `0x14002aec7`
- `ntoskrnl!ExAllocatePool2` at `0x14002b1e1`
- `ntoskrnl!ExAllocatePool2` at `0x14002aec7`
- `ntoskrnl!ExAllocatePool2` at `0x14002b1e1`
- `FLTMGR!FltAttachVolume` at `0x14002b397`
- `FLTMGR!FltAttachVolume` at `0x14002b397`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x14002b181`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x14002b181`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14002afdc`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14002afdc`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14002b1be`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14002b1be`
- `FLTMGR!FltPrepareToReuseEcp` at `0x14002b43c`
- `FLTMGR!FltPrepareToReuseEcp` at `0x14002b43c`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002b600`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002b600`
- `FLTMGR!FltCreateFileEx2` at `0x14002af6f`
- `FLTMGR!FltCreateFileEx2` at `0x14002b0f5`
- `FLTMGR!FltCreateFileEx2` at `0x14002b4ec`
- `FLTMGR!FltCreateFileEx2` at `0x14002af6f`
- `FLTMGR!FltCreateFileEx2` at `0x14002b0f5`
- `FLTMGR!FltCreateFileEx2` at `0x14002b4ec`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002af98`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002af98`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002b025`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002b025`
- `FLTMGR!FltClose` at `0x14002b655`
- `FLTMGR!FltClose` at `0x14002b655`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002b5e4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002b614`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002b5e4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002b614`
- `FLTMGR!FltObjectDereference` at `0x14002b3e8`
- `FLTMGR!FltObjectDereference` at `0x14002b40b`
- `FLTMGR!FltObjectDereference` at `0x14002b5ba`
- `FLTMGR!FltObjectDereference` at `0x14002b5cf`
- `FLTMGR!FltObjectDereference` at `0x14002b63b`
- `FLTMGR!FltObjectDereference` at `0x14002b3e8`
- `FLTMGR!FltObjectDereference` at `0x14002b40b`
- `FLTMGR!FltObjectDereference` at `0x14002b5ba`
- `FLTMGR!FltObjectDereference` at `0x14002b5cf`
- `FLTMGR!FltObjectDereference` at `0x14002b63b`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b119`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b14f`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b2f6`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b119`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b14f`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b2f6`
- `FLTMGR!FltQueryInformationFile` at `0x14002b27c`
- `FLTMGR!FltQueryInformationFile` at `0x14002b27c`

## pseudocode

```c
__int64 __fastcall WcOpenSourceFile(
        __int64 a1,
        __int64 a2,
        struct _FLT_INSTANCE *a3,
        void *a4,
        UNICODE_STRING *Source,
        ULONG CreateOptions,
        _QWORD *a7)
{
  struct _FLT_FILE_NAME_INFORMATION *v10; // r14
  unsigned __int16 v11; // ax
  char *v12; // rdi
  unsigned __int16 v13; // cx
  NTSTATUS appended; // ebx
  __int64 Pool2; // rax
  int v17; // edx
  PFILE_OBJECT *v18; // r13
  NTSTATUS v19; // eax
  _QWORD *v20; // rdx
  void *v21; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v22; // rcx
  NTSTATUS InformationFile; // eax
  int v24; // edx
  int v25; // r9d
  PVOID *v26; // rax
  void *v27; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v28; // rbx
  int v29; // r9d
  void *v30; // rcx
  void *v31; // rcx
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char IoStatusBlocka; // [rsp+30h] [rbp-D0h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-C8h]
  struct _UNICODE_STRING *AllocationSizea; // [rsp+38h] [rbp-C8h]
  char FileAttributes; // [rsp+40h] [rbp-C0h]
  PVOID EcpContext; // [rsp+80h] [rbp-80h] BYREF
  struct _FLT_FILE_NAME_INFORMATION *v38; // [rsp+88h] [rbp-78h]
  PECP_LIST EcpList; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  ULONG ShareAccess; // [rsp+A8h] [rbp-58h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  PFLT_INSTANCE RetInstance; // [rsp+110h] [rbp+10h] BYREF
  __int64 v47; // [rsp+118h] [rbp+18h]
  _QWORD *v48; // [rsp+120h] [rbp+20h]
  struct _IO_STATUS_BLOCK v49; // [rsp+128h] [rbp+28h] BYREF
  _OWORD FileInformation[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v51; // [rsp+158h] [rbp+58h]

  v48 = a7;
  v47 = a2;
  v45 = a1;
  LOWORD(v44) = 0;
  v51 = 0;
  EcpList = 0;
  DestinationString = 0;
  EcpContext = 0;
  v10 = 0;
  memset(&ObjectAttributes, 0, 44);
  RetInstance = 0;
  v38 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v49 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  RtlInitUnicodeString(&DestinationString, 0);
  if ( a4 )
  {
    ObjectAttributes.RootDirectory = a4;
    ObjectAttributes.ObjectName = Source;
    goto LABEL_16;
  }
  v11 = *(_WORD *)(a2 + 24);
  v12 = 0;
  v13 = Source->Length + v11;
  if ( v13 < v11 )
  {
    appended = -1073741675;
    DestinationString.MaximumLength = -1;
    goto LABEL_4;
  }
  DestinationString.MaximumLength = Source->Length + v11;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v13, 1852195671);
  if ( !DestinationString.Buffer )
  {
    appended = -1073741670;
    goto LABEL_4;
  }
  DestinationString.Length = 0;
  RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a2 + 24));
  appended = RtlAppendUnicodeStringToString(&DestinationString, Source);
  if ( appended >= 0 )
  {
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    a3 = *(struct _FLT_INSTANCE **)(v47 + 40);
LABEL_16:
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Pool2 = ExAllocatePool2(256, 40, 1936933719);
    v12 = (char *)Pool2;
    if ( !Pool2 )
    {
      appended = -1073741670;
      goto LABEL_45;
    }
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    ShareAccess = 2 * ((CreateOptions & 1) == 0) + 3;
    v44 = v45;
    appended = FltCreateFileEx2(
                 Globals,
                 a3,
                 (PHANDLE)(Pool2 + 8),
                 (PFILE_OBJECT *)(Pool2 + 16),
                 0x80000000,
                 &ObjectAttributes,
                 &v49,
                 0,
                 0,
                 ShareAccess,
                 1u,
                 CreateOptions,
                 0,
                 0,
                 0,
                 &DriverContext);
    if ( (unsigned int)(appended + 1073740952) > 1 )
    {
      v18 = (PFILE_OBJECT *)(v12 + 16);
    }
    else
    {
      appended = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
      if ( appended < 0 )
        goto LABEL_45;
      appended = FltAllocateExtraCreateParameter(
                   Globals,
                   &GUID_ECP_FLT_CREATEFILE_TARGET,
                   0x20u,
                   0,
                   0,
                   0x63744357u,
                   &EcpContext);
      if ( appended < 0 )
        goto LABEL_45;
      *((_WORD *)EcpContext + 12) = 1;
      *(_QWORD *)EcpContext = 0;
      *((_QWORD *)EcpContext + 1) = 0;
      *((_QWORD *)EcpContext + 2) = 0;
      appended = FltInsertExtraCreateParameter(Globals, EcpList, EcpContext);
      if ( appended < 0 )
        goto LABEL_45;
      DriverContext.Size = 40;
      v44 = v45;
      DriverContext.ExtraCreateParameter = EcpList;
      *(_DWORD *)(&DriverContext.Size + 1) = 0;
      *(&DriverContext.Size + 3) = 0;
      *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( DestinationString.Length )
      {
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = &DestinationString;
      }
      else
      {
        ObjectAttributes.RootDirectory = a4;
        ObjectAttributes.ObjectName = Source;
      }
      v18 = (PFILE_OBJECT *)(v12 + 16);
      v19 = FltCreateFileEx2(
              Globals,
              a3,
              (PHANDLE)v12 + 1,
              (PFILE_OBJECT *)v12 + 2,
              0x80000000,
              &ObjectAttributes,
              &v49,
              0,
              0,
              ShareAccess,
              1u,
              CreateOptions,
              0,
              0,
              0,
              &DriverContext);
      appended = v19;
      if ( v19 >= 0 )
      {
        if ( FltIsEcpAcknowledged(Globals, EcpContext) && *(_QWORD *)EcpContext )
          a3 = *(struct _FLT_INSTANCE **)EcpContext;
        goto LABEL_40;
      }
      if ( (unsigned int)(v19 + 1073740952) > 1 )
      {
LABEL_61:
        if ( DestinationString.Length )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            || !LOWORD(wil_details_featureDescriptors_a->DeviceType) )
          {
            goto LABEL_69;
          }
          FileAttributes = appended;
          AllocationSizea = &DestinationString;
          v29 = 97;
          IoStatusBlocka = 124;
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            || !LOWORD(wil_details_featureDescriptors_a->DeviceType) )
          {
            goto LABEL_69;
          }
          FileAttributes = appended;
          v29 = 98;
          AllocationSizea = Source;
          IoStatusBlocka = -125;
        }
        LOBYTE(v17) = 5;
        WPP_RECORDER_SF_sDZd(
          WcVerboseRecorder,
          v17,
          5,
          v29,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          IoStatusBlocka,
          (__int64)AllocationSizea,
          FileAttributes);
LABEL_69:
        v10 = v38;
        goto LABEL_4;
      }
      if ( !FltIsEcpAcknowledged(Globals, EcpContext) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && LOWORD(wil_details_featureDescriptors_a->DeviceType) )
        {
          LODWORD(AllocationSize) = appended;
          v25 = 95;
          IoStatusBlock = 42;
LABEL_51:
          LOBYTE(v24) = 5;
          WPP_RECORDER_SF_sDd(
            WcVerboseRecorder,
            v24,
            5,
            v25,
            (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
            IoStatusBlock,
            AllocationSize);
          goto LABEL_69;
        }
        goto LABEL_45;
      }
      appended = FltAttachVolume(Globals, *((PFLT_VOLUME *)EcpContext + 1), &stru_14000A5F0, &RetInstance);
      if ( appended < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && LOWORD(wil_details_featureDescriptors_a->DeviceType) )
        {
          LODWORD(AllocationSize) = appended;
          v25 = 96;
          IoStatusBlock = 65;
          goto LABEL_51;
        }
LABEL_45:
        v10 = 0;
        goto LABEL_4;
      }
      v26 = (PVOID *)EcpContext;
      a3 = RetInstance;
      v27 = (void *)*((_QWORD *)EcpContext + 1);
      if ( v27 )
      {
        FltObjectDereference(v27);
        *((_QWORD *)EcpContext + 1) = 0;
        v26 = (PVOID *)EcpContext;
      }
      if ( *v26 )
      {
        FltObjectDereference(*v26);
        *(_QWORD *)EcpContext = 0;
        v26 = (PVOID *)EcpContext;
      }
      v28 = (struct _FLT_FILE_NAME_INFORMATION *)v26[2];
      v26[2] = 0;
      v38 = v28;
      FltPrepareToReuseEcp(Globals, EcpContext);
      ObjectAttributes.Length = 48;
      *(_DWORD *)(&DriverContext.Size + 1) = 0;
      *(&DriverContext.Size + 3) = 0;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      DriverContext.Size = 40;
      v44 = v45;
      DriverContext.ExtraCreateParameter = EcpList;
      ObjectAttributes.ObjectName = &v28->Name;
      *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      appended = FltCreateFileEx2(
                   Globals,
                   a3,
                   (PHANDLE)v12 + 1,
                   (PFILE_OBJECT *)v12 + 2,
                   0x80000000,
                   &ObjectAttributes,
                   &v49,
                   0,
                   0,
                   ShareAccess,
                   1u,
                   CreateOptions,
                   0,
                   0,
                   0,
                   &DriverContext);
    }
    if ( appended >= 0 )
    {
LABEL_40:
      InformationFile = FltQueryInformationFile(a3, *v18, FileInformation, 0x28u, FileBasicInformation, 0);
      v10 = v38;
      appended = InformationFile;
      if ( InformationFile >= 0 )
      {
        *((_QWORD *)v12 + 4) = v47;
        *(_QWORD *)v12 = a3;
        *((_DWORD *)v12 + 6) = v51;
        *v48 = v12;
        v12 = 0;
      }
      goto LABEL_4;
    }
    goto LABEL_61;
  }
LABEL_4:
  if ( EcpContext && FltIsEcpAcknowledged(Globals, EcpContext) )
  {
    FltRemoveExtraCreateParameter(Globals, EcpList, &GUID_ECP_FLT_CREATEFILE_TARGET, &EcpContext, 0);
    v20 = EcpContext;
    if ( *(_QWORD *)EcpContext )
    {
      FltObjectDereference(*(PVOID *)EcpContext);
      v20 = EcpContext;
    }
    v21 = (void *)v20[1];
    if ( v21 )
    {
      FltObjectDereference(v21);
      v20 = EcpContext;
    }
    v22 = (struct _FLT_FILE_NAME_INFORMATION *)v20[2];
    if ( v22 )
    {
      FltReleaseFileNameInformation(v22);
      v20 = EcpContext;
    }
    FltFreeExtraCreateParameter(Globals, v20);
  }
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  if ( v10 )
    FltReleaseFileNameInformation(v10);
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664357u);
  if ( RetInstance )
    FltObjectDereference(RetInstance);
  if ( v12 )
  {
    v30 = (void *)*((_QWORD *)v12 + 1);
    if ( v30 )
      FltClose(v30);
    v31 = (void *)*((_QWORD *)v12 + 2);
    if ( v31 )
      ObfDereferenceObject(v31);
    ExFreePoolWithTag(v12, 0x73734357u);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14002ad54  push    rbp
0x14002ad56  push    rbx
0x14002ad57  push    rsi
0x14002ad58  push    rdi
0x14002ad59  push    r12
0x14002ad5b  push    r13
0x14002ad5d  push    r14
0x14002ad5f  push    r15
0x14002ad61  lea     rbp, [rsp-78h]
0x14002ad66  sub     rsp, 178h
0x14002ad6d  mov     rax, cs:__security_cookie
0x14002ad74  xor     rax, rsp
0x14002ad77  mov     [rbp+0B0h+var_50], rax
0x14002ad7b  mov     rax, [rbp+0B0h+arg_30]
0x14002ad82  xorps   xmm0, xmm0
0x14002ad85  mov     r12, [rbp+0B0h+Source]
0x14002ad8c  xor     r15d, r15d
0x14002ad8f  mov     [rbp+0B0h+var_90], rax
0x14002ad93  mov     rbx, rdx
0x14002ad96  xor     eax, eax
0x14002ad98  mov     [rbp+0B0h+var_98], rdx
0x14002ad9c  mov     [rbp+0B0h+var_A8], rcx
0x14002ada0  xor     edx, edx; SourceString
0x14002ada2  movups  xmmword ptr [rbp+0B0h+var_100.ObjectName], xmm0
0x14002ada6  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14002adaa  mov     word ptr [rbp+0B0h+var_B0], ax
0x14002adae  mov     [rbp+0B0h+var_58], rax
0x14002adb2  mov     r13, r9
0x14002adb5  mov     rsi, r8
0x14002adb8  mov     [rbp+0B0h+EcpList], r15
0x14002adbc  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x14002adc0  mov     [rbp+0B0h+EcpContext], r15
0x14002adc4  mov     r14d, r15d
0x14002adc7  movups  xmmword ptr [rbp+0B0h+var_100.Length], xmm0
0x14002adcb  mov     [rbp+0B0h+RetInstance], r15
0x14002adcf  movups  xmmword ptr [rbp+0B0h+var_100+1Ch], xmm0
0x14002add3  mov     [rbp+0B0h+var_128], r15
0x14002add7  movups  xmmword ptr [rbp+0B0h+var_D0.Size], xmm0
0x14002addb  movups  xmmword ptr [rbp+0B0h+var_D0.DeviceObjectHint], xmm0
0x14002addf  movups  xmmword ptr [rbp+0B0h+var_88], xmm0
0x14002ade3  movups  [rbp+0B0h+FileInformation], xmm0
0x14002ade7  movups  [rbp+0B0h+var_68], xmm0
0x14002adeb  call    cs:__imp_RtlInitUnicodeString
0x14002adf2  nop     dword ptr [rax+rax+00h]
0x14002adf7  xor     r10d, r10d
0x14002adfa  test    r13, r13
0x14002adfd  jnz     loc_14002AE92
0x14002ae03  movzx   eax, word ptr [rbx+18h]
0x14002ae07  mov     edi, r10d
0x14002ae0a  movzx   ecx, ax
0x14002ae0d  add     cx, [r12]
0x14002ae12  cmp     cx, ax
0x14002ae15  jnb     loc_14002B1CF
0x14002ae1b  mov     eax, 0FFFFh
0x14002ae20  mov     ebx, 0C0000095h
0x14002ae25  mov     [rbp+0B0h+DestinationString.MaximumLength], ax
0x14002ae29  mov     rdx, [rbp+0B0h+EcpContext]; EcpContext
0x14002ae2d  test    rdx, rdx
0x14002ae30  jnz     loc_14002B148
0x14002ae36  mov     rdx, [rbp+0B0h+EcpList]; EcpList
0x14002ae3a  test    rdx, rdx
0x14002ae3d  jnz     loc_14002B5F9
0x14002ae43  test    r14, r14
0x14002ae46  jnz     loc_14002B611
0x14002ae4c  mov     rcx, [rbp+0B0h+DestinationString.Buffer]; P
0x14002ae50  test    rcx, rcx
0x14002ae53  jnz     loc_14002B625
0x14002ae59  mov     rcx, [rbp+0B0h+RetInstance]; FltObject
0x14002ae5d  test    rcx, rcx
0x14002ae60  jnz     loc_14002B63B
0x14002ae66  test    rdi, rdi
0x14002ae69  jnz     loc_14002B64C
0x14002ae6f  mov     eax, ebx
0x14002ae71  mov     rcx, [rbp+0B0h+var_50]
0x14002ae75  xor     rcx, rsp; StackCookie
0x14002ae78  call    __security_check_cookie
0x14002ae7d  add     rsp, 178h
0x14002ae84  pop     r15
0x14002ae86  pop     r14
0x14002ae88  pop     r13
0x14002ae8a  pop     r12
0x14002ae8c  pop     rdi
0x14002ae8d  pop     rsi
0x14002ae8e  pop     rbx
0x14002ae8f  pop     rbp
0x14002ae90  retn
0x14002ae92  mov     [rbp+0B0h+var_100.RootDirectory], r13
0x14002ae96  mov     [rbp+0B0h+var_100.ObjectName], r12
0x14002ae9a  mov     r14d, 30h ; '0'
0x14002aea0  xorps   xmm0, xmm0
0x14002aea3  mov     r15d, 240h
0x14002aea9  mov     [rbp+0B0h+var_100.Length], r14d
0x14002aead  mov     r8d, 73734357h
0x14002aeb3  mov     [rbp+0B0h+var_100.Attributes], r15d
0x14002aeb7  mov     ecx, 100h
0x14002aebc  lea     ebx, [r14-8]
0x14002aec0  mov     edx, ebx
0x14002aec2  movdqu  xmmword ptr [rbp+0B0h+var_100.SecurityDescriptor], xmm0
0x14002aec7  call    cs:__imp_ExAllocatePool2
0x14002aece  nop     dword ptr [rax+rax+00h]
0x14002aed3  xor     r10d, r10d
0x14002aed6  mov     rdi, rax
0x14002aed9  test    rax, rax
0x14002aedc  jz      loc_14002B2D0
0x14002aee2  mov     ecx, [rbp+0B0h+arg_28]
0x14002aee8  lea     r11d, [r14-2Fh]
0x14002aeec  mov     eax, ecx
0x14002aeee  lea     r9, [rbp+0B0h+var_D0]
0x14002aef2  mov     [rsp+1B0h+DriverContext], r9; DriverContext
0x14002aef7  lea     r8, [rdi+8]; FileHandle
0x14002aefb  mov     [rsp+1B0h+Flags], r10d; Flags
0x14002af00  lea     r9, [rdi+10h]; FileObject
0x14002af04  mov     [rsp+1B0h+EaLength], r10d; EaLength
0x14002af09  not     eax
0x14002af0b  mov     [rsp+1B0h+EaBuffer], r10; EaBuffer
0x14002af10  and     eax, r11d
0x14002af13  mov     [rsp+1B0h+CreateOptions], ecx; CreateOptions
0x14002af17  xorps   xmm0, xmm0
0x14002af1a  mov     [rsp+1B0h+CreateDisposition], r11d; CreateDisposition
0x14002af1f  lea     rcx, [rbp+0B0h+var_88]
0x14002af23  movups  xmmword ptr [rbp+0B0h+var_D0.Size], xmm0
0x14002af27  lea     edx, ds:3[rax*2]
0x14002af2e  mov     [rbp+0B0h+var_D0.Size], bx
0x14002af32  mov     rax, [rbp+0B0h+var_A8]
0x14002af36  mov     [rsp+1B0h+ShareAccess], edx; ShareAccess
0x14002af3a  mov     dword ptr [rsp+1B0h+FileAttributes], r10d; FileAttributes
0x14002af3f  mov     [rsp+1B0h+AllocationSize], r10; AllocationSize
0x14002af44  mov     [rsp+1B0h+IoStatusBlock], rcx; IoStatusBlock
0x14002af49  lea     rcx, [rbp+0B0h+var_100]
0x14002af4d  mov     [rsp+1B0h+ObjectAttributes], rcx; ObjectAttributes
0x14002af52  mov     rcx, cs:Globals; Filter
0x14002af59  mov     [rbp+0B0h+var_108], edx
0x14002af5c  mov     rdx, rsi; Instance
0x14002af5f  movups  xmmword ptr [rbp+0B0h+var_D0.DeviceObjectHint], xmm0
0x14002af63  mov     [rbp+0B0h+var_B0], rax
0x14002af67  mov     [rsp+1B0h+DesiredAccess], 80000000h; DesiredAccess
0x14002af6f  call    cs:__imp_FltCreateFileEx2
0x14002af76  nop     dword ptr [rax+rax+00h]
0x14002af7b  mov     ebx, eax
0x14002af7d  add     eax, 3FFFFC98h
0x14002af82  cmp     eax, 1
0x14002af85  ja      loc_14002B24F
0x14002af8b  mov     rcx, cs:Globals; Filter
0x14002af92  lea     r8, [rbp+0B0h+EcpList]; EcpList
0x14002af96  xor     edx, edx; Flags
0x14002af98  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14002af9f  nop     dword ptr [rax+rax+00h]
0x14002afa4  xor     r10d, r10d
0x14002afa7  mov     ebx, eax
0x14002afa9  test    eax, eax
0x14002afab  js      loc_14002B2D5
0x14002afb1  mov     rcx, cs:Globals; Filter
0x14002afb8  lea     rax, [rbp+0B0h+EcpContext]
0x14002afbc  mov     [rsp+1B0h+IoStatusBlock], rax; EcpContext
0x14002afc1  lea     r8d, [r14-10h]; SizeOfContext
0x14002afc5  mov     dword ptr [rsp+1B0h+ObjectAttributes], 63744357h; PoolTag
0x14002afcd  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14002afd4  xor     r9d, r9d; Flags
0x14002afd7  mov     qword ptr [rsp+1B0h+DesiredAccess], r10; CleanupCallback
0x14002afdc  call    cs:__imp_FltAllocateExtraCreateParameter
0x14002afe3  nop     dword ptr [rax+rax+00h]
0x14002afe8  xor     r10d, r10d
0x14002afeb  mov     ebx, eax
0x14002afed  test    eax, eax
0x14002afef  js      loc_14002B2D5
0x14002aff5  mov     rax, [rbp+0B0h+EcpContext]
0x14002aff9  mov     word ptr [rax+18h], 1
0x14002afff  mov     rax, [rbp+0B0h+EcpContext]
0x14002b003  mov     [rax], r10
0x14002b006  mov     rax, [rbp+0B0h+EcpContext]
0x14002b00a  mov     [rax+8], r10
0x14002b00e  mov     rax, [rbp+0B0h+EcpContext]
0x14002b012  mov     [rax+10h], r10
0x14002b016  mov     r8, [rbp+0B0h+EcpContext]; EcpContext
0x14002b01a  mov     rdx, [rbp+0B0h+EcpList]; EcpList
0x14002b01e  mov     rcx, cs:Globals; Filter
0x14002b025  call    cs:__imp_FltInsertExtraCreateParameter
0x14002b02c  nop     dword ptr [rax+rax+00h]
0x14002b031  xor     r10d, r10d
0x14002b034  mov     ebx, eax
0x14002b036  test    eax, eax
0x14002b038  js      loc_14002B2D5
0x14002b03e  lea     eax, [r14-8]
0x14002b042  xorps   xmm0, xmm0
0x14002b045  mov     [rbp+0B0h+var_D0.Size], ax
0x14002b049  mov     rax, [rbp+0B0h+var_A8]
0x14002b04d  mov     [rbp+0B0h+var_B0], rax
0x14002b051  mov     rax, [rbp+0B0h+EcpList]
0x14002b055  mov     [rbp+0B0h+var_D0.ExtraCreateParameter], rax
0x14002b059  mov     dword ptr [rbp+0B0h+var_D0+2], r10d
0x14002b05d  mov     word ptr [rbp+0B0h+var_D0+6], r10w
0x14002b062  movdqu  xmmword ptr [rbp+0B0h+var_D0.DeviceObjectHint], xmm0
0x14002b067  mov     [rbp+0B0h+var_100.Length], r14d
0x14002b06b  mov     [rbp+0B0h+var_100.Attributes], r15d
0x14002b06f  movdqu  xmmword ptr [rbp+0B0h+var_100.SecurityDescriptor], xmm0
0x14002b074  cmp     [rbp+0B0h+DestinationString.Length], r10w
0x14002b079  jbe     loc_14002B2B9
0x14002b07f  lea     rax, [rbp+0B0h+DestinationString]
0x14002b083  mov     [rbp+0B0h+var_100.RootDirectory], r10
0x14002b087  mov     [rbp+0B0h+var_100.ObjectName], rax
0x14002b08b  mov     rcx, cs:Globals; Filter
0x14002b092  lea     rax, [rbp+0B0h+var_D0]
0x14002b096  mov     [rsp+1B0h+DriverContext], rax; DriverContext
0x14002b09b  lea     r13, [rdi+10h]
0x14002b09f  mov     eax, [rbp+0B0h+arg_28]
0x14002b0a5  lea     r8, [rdi+8]; FileHandle
0x14002b0a9  mov     [rsp+1B0h+Flags], r10d; Flags
0x14002b0ae  mov     r9, r13; FileObject
0x14002b0b1  mov     [rsp+1B0h+EaLength], r10d; EaLength
0x14002b0b6  mov     rdx, rsi; Instance
0x14002b0b9  mov     [rsp+1B0h+EaBuffer], r10; EaBuffer
0x14002b0be  mov     [rsp+1B0h+CreateOptions], eax; CreateOptions
0x14002b0c2  mov     eax, [rbp+0B0h+var_108]
0x14002b0c5  mov     [rsp+1B0h+CreateDisposition], 1; CreateDisposition
0x14002b0cd  mov     [rsp+1B0h+ShareAccess], eax; ShareAccess
0x14002b0d1  lea     rax, [rbp+0B0h+var_88]
0x14002b0d5  mov     dword ptr [rsp+1B0h+FileAttributes], r10d; FileAttributes
0x14002b0da  mov     [rsp+1B0h+AllocationSize], r10; AllocationSize
0x14002b0df  mov     [rsp+1B0h+IoStatusBlock], rax; IoStatusBlock
0x14002b0e4  lea     rax, [rbp+0B0h+var_100]
0x14002b0e8  mov     [rsp+1B0h+ObjectAttributes], rax; ObjectAttributes
0x14002b0ed  mov     [rsp+1B0h+DesiredAccess], 80000000h; DesiredAccess
0x14002b0f5  call    cs:__imp_FltCreateFileEx2
0x14002b0fc  nop     dword ptr [rax+rax+00h]
0x14002b101  xor     r10d, r10d
0x14002b104  mov     ebx, eax
0x14002b106  test    eax, eax
0x14002b108  js      loc_14002B2DD
0x14002b10e  mov     rdx, [rbp+0B0h+EcpContext]; EcpContext
0x14002b112  mov     rcx, cs:Globals; Filter
0x14002b119  call    cs:__imp_FltIsEcpAcknowledged
0x14002b120  nop     dword ptr [rax+rax+00h]
0x14002b125  xor     r10d, r10d
0x14002b128  test    al, al
0x14002b12a  jz      loc_14002B25E
0x14002b130  mov     rax, [rbp+0B0h+EcpContext]
0x14002b134  mov     rcx, [rax]
0x14002b137  test    rcx, rcx
0x14002b13a  jz      loc_14002B25E
0x14002b140  mov     rsi, rcx
0x14002b143  jmp     loc_14002B25E
0x14002b148  mov     rcx, cs:Globals; Filter
0x14002b14f  call    cs:__imp_FltIsEcpAcknowledged
0x14002b156  nop     dword ptr [rax+rax+00h]
0x14002b15b  xor     r10d, r10d
0x14002b15e  test    al, al
0x14002b160  jz      loc_14002AE36
0x14002b166  mov     rdx, [rbp+0B0h+EcpList]; EcpList
0x14002b16a  lea     r9, [rbp+0B0h+EcpContext]; EcpContext
0x14002b16e  mov     rcx, cs:Globals; Filter
0x14002b175  lea     r8, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14002b17c  mov     qword ptr [rsp+1B0h+DesiredAccess], r10; EcpContextSize
0x14002b181  call    cs:__imp_FltRemoveExtraCreateParameter
0x14002b188  nop     dword ptr [rax+rax+00h]
0x14002b18d  mov     rdx, [rbp+0B0h+EcpContext]; EcpContext
0x14002b191  mov     rcx, [rdx]; FltObject
0x14002b194  test    rcx, rcx
0x14002b197  jnz     loc_14002B5BA
0x14002b19d  mov     rcx, [rdx+8]; FltObject
0x14002b1a1  test    rcx, rcx
0x14002b1a4  jnz     loc_14002B5CF
0x14002b1aa  mov     rcx, [rdx+10h]; FileNameInformation
0x14002b1ae  test    rcx, rcx
0x14002b1b1  jnz     loc_14002B5E4
0x14002b1b7  mov     rcx, cs:Globals; Filter
0x14002b1be  call    cs:__imp_FltFreeExtraCreateParameter
0x14002b1c5  nop     dword ptr [rax+rax+00h]
0x14002b1ca  jmp     loc_14002AE36
0x14002b1cf  mov     [rbp+0B0h+DestinationString.MaximumLength], cx
0x14002b1d3  mov     r8d, 6E664357h
0x14002b1d9  movzx   edx, cx
0x14002b1dc  mov     ecx, 100h
0x14002b1e1  call    cs:__imp_ExAllocatePool2
0x14002b1e8  nop     dword ptr [rax+rax+00h]
0x14002b1ed  xor     r10d, r10d
0x14002b1f0  mov     [rbp+0B0h+DestinationString.Buffer], rax
0x14002b1f4  test    rax, rax
0x14002b1f7  jz      loc_14002B2C6
0x14002b1fd  lea     rdx, [rbx+18h]; SourceString
0x14002b201  mov     [rbp+0B0h+DestinationString.Length], r10w
0x14002b206  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14002b20a  call    cs:__imp_RtlCopyUnicodeString
0x14002b211  nop     dword ptr [rax+rax+00h]
0x14002b216  mov     rdx, r12; Source
0x14002b219  lea     rcx, [rbp+0B0h+DestinationString]; Destination
0x14002b21d  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002b224  nop     dword ptr [rax+rax+00h]
0x14002b229  xor     r10d, r10d
0x14002b22c  mov     ebx, eax
0x14002b22e  test    eax, eax
0x14002b230  js      loc_14002AE29
0x14002b236  mov     rsi, [rbp+0B0h+var_98]
0x14002b23a  lea     rax, [rbp+0B0h+DestinationString]
0x14002b23e  mov     [rbp+0B0h+var_100.RootDirectory], r10
0x14002b242  mov     [rbp+0B0h+var_100.ObjectName], rax
0x14002b246  mov     rsi, [rsi+28h]
0x14002b24a  jmp     loc_14002AE9A
0x14002b24f  lea     r13, [rdi+10h]
0x14002b253  xor     r10d, r10d
0x14002b256  test    ebx, ebx
  ... truncated ...
```
