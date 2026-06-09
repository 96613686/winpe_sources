# WcOpenSourceFile

- ea: `0x14002ad04`
- end: `0x14002b63f`
- name: `WcOpenSourceFile`
- size: `2363`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400294b4`
- `0x14002a614`

## callees

- `0x1400020c4`
- `0x1400048a4`
- `0x140007c60`
- `0x14002ad04`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14002b1ba`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002b1ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002ad9b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002ad9b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b61a`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b61a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b1cd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b1cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b5da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b62e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b5da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b62e`
- `ntoskrnl!ExAllocatePool2` at `0x14002ae77`
- `ntoskrnl!ExAllocatePool2` at `0x14002b191`
- `ntoskrnl!ExAllocatePool2` at `0x14002ae77`
- `ntoskrnl!ExAllocatePool2` at `0x14002b191`
- `FLTMGR!FltAttachVolume` at `0x14002b347`
- `FLTMGR!FltAttachVolume` at `0x14002b347`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x14002b131`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x14002b131`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14002af8c`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14002af8c`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14002b16e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14002b16e`
- `FLTMGR!FltPrepareToReuseEcp` at `0x14002b3ec`
- `FLTMGR!FltPrepareToReuseEcp` at `0x14002b3ec`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002b5b0`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002b5b0`
- `FLTMGR!FltCreateFileEx2` at `0x14002af1f`
- `FLTMGR!FltCreateFileEx2` at `0x14002b0a5`
- `FLTMGR!FltCreateFileEx2` at `0x14002b49c`
- `FLTMGR!FltCreateFileEx2` at `0x14002af1f`
- `FLTMGR!FltCreateFileEx2` at `0x14002b0a5`
- `FLTMGR!FltCreateFileEx2` at `0x14002b49c`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002af48`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002af48`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002afd5`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002afd5`
- `FLTMGR!FltClose` at `0x14002b605`
- `FLTMGR!FltClose` at `0x14002b605`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002b594`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002b5c4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002b594`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002b5c4`
- `FLTMGR!FltObjectDereference` at `0x14002b398`
- `FLTMGR!FltObjectDereference` at `0x14002b3bb`
- `FLTMGR!FltObjectDereference` at `0x14002b56a`
- `FLTMGR!FltObjectDereference` at `0x14002b57f`
- `FLTMGR!FltObjectDereference` at `0x14002b5eb`
- `FLTMGR!FltObjectDereference` at `0x14002b398`
- `FLTMGR!FltObjectDereference` at `0x14002b3bb`
- `FLTMGR!FltObjectDereference` at `0x14002b56a`
- `FLTMGR!FltObjectDereference` at `0x14002b57f`
- `FLTMGR!FltObjectDereference` at `0x14002b5eb`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b0c9`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b0ff`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b2a6`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b0c9`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b0ff`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002b2a6`
- `FLTMGR!FltQueryInformationFile` at `0x14002b22c`
- `FLTMGR!FltQueryInformationFile` at `0x14002b22c`

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
  NTSTATUS v26; // eax
  PVOID *v27; // rax
  void *v28; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v29; // rbx
  int v30; // r9d
  void *v31; // rcx
  void *v32; // rcx
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char IoStatusBlocka; // [rsp+30h] [rbp-D0h]
  char AllocationSize; // [rsp+38h] [rbp-C8h]
  struct _UNICODE_STRING *AllocationSizea; // [rsp+38h] [rbp-C8h]
  char FileAttributes; // [rsp+40h] [rbp-C0h]
  PVOID EcpContext; // [rsp+80h] [rbp-80h] BYREF
  struct _FLT_FILE_NAME_INFORMATION *v39; // [rsp+88h] [rbp-78h]
  PECP_LIST EcpList; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  ULONG ShareAccess; // [rsp+A8h] [rbp-58h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]
  PFLT_INSTANCE RetInstance; // [rsp+110h] [rbp+10h] BYREF
  __int64 v48; // [rsp+118h] [rbp+18h]
  _QWORD *v49; // [rsp+120h] [rbp+20h]
  struct _IO_STATUS_BLOCK v50; // [rsp+128h] [rbp+28h] BYREF
  _OWORD FileInformation[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v52; // [rsp+158h] [rbp+58h]

  v49 = a7;
  v48 = a2;
  v46 = a1;
  LOWORD(v45) = 0;
  v52 = 0;
  EcpList = 0;
  DestinationString = 0;
  EcpContext = 0;
  v10 = 0;
  memset(&ObjectAttributes, 0, 44);
  RetInstance = 0;
  v39 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v50 = 0;
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
    a3 = *(struct _FLT_INSTANCE **)(v48 + 40);
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
    v45 = v46;
    appended = FltCreateFileEx2(
                 Globals,
                 a3,
                 (PHANDLE)(Pool2 + 8),
                 (PFILE_OBJECT *)(Pool2 + 16),
                 0x80000000,
                 &ObjectAttributes,
                 &v50,
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
      v45 = v46;
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
              &v50,
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
            || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            goto LABEL_69;
          }
          FileAttributes = appended;
          AllocationSizea = &DestinationString;
          v30 = 97;
          IoStatusBlocka = 124;
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            goto LABEL_69;
          }
          FileAttributes = appended;
          v30 = 98;
          AllocationSizea = Source;
          IoStatusBlocka = -125;
        }
        LOBYTE(v17) = 5;
        WPP_RECORDER_SF_sDZd(
          WcVerboseRecorder,
          v17,
          5,
          v30,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          IoStatusBlocka,
          (__int64)AllocationSizea,
          FileAttributes);
LABEL_69:
        v10 = v39;
        goto LABEL_4;
      }
      if ( !FltIsEcpAcknowledged(Globals, EcpContext) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          AllocationSize = appended;
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
      v26 = FltAttachVolume(Globals, *((PFLT_VOLUME *)EcpContext + 1), &stru_14000A5F0, &RetInstance);
      appended = v26;
      if ( v26 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          AllocationSize = v26;
          v25 = 96;
          IoStatusBlock = 65;
          goto LABEL_51;
        }
LABEL_45:
        v10 = 0;
        goto LABEL_4;
      }
      v27 = (PVOID *)EcpContext;
      a3 = RetInstance;
      v28 = (void *)*((_QWORD *)EcpContext + 1);
      if ( v28 )
      {
        FltObjectDereference(v28);
        *((_QWORD *)EcpContext + 1) = 0;
        v27 = (PVOID *)EcpContext;
      }
      if ( *v27 )
      {
        FltObjectDereference(*v27);
        *(_QWORD *)EcpContext = 0;
        v27 = (PVOID *)EcpContext;
      }
      v29 = (struct _FLT_FILE_NAME_INFORMATION *)v27[2];
      v27[2] = 0;
      v39 = v29;
      FltPrepareToReuseEcp(Globals, EcpContext);
      ObjectAttributes.Length = 48;
      *(_DWORD *)(&DriverContext.Size + 1) = 0;
      *(&DriverContext.Size + 3) = 0;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      DriverContext.Size = 40;
      v45 = v46;
      DriverContext.ExtraCreateParameter = EcpList;
      ObjectAttributes.ObjectName = &v29->Name;
      *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      appended = FltCreateFileEx2(
                   Globals,
                   a3,
                   (PHANDLE)v12 + 1,
                   (PFILE_OBJECT *)v12 + 2,
                   0x80000000,
                   &ObjectAttributes,
                   &v50,
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
      v10 = v39;
      appended = InformationFile;
      if ( InformationFile >= 0 )
      {
        *((_QWORD *)v12 + 4) = v48;
        *(_QWORD *)v12 = a3;
        *((_DWORD *)v12 + 6) = v52;
        *v49 = v12;
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
    v31 = (void *)*((_QWORD *)v12 + 1);
    if ( v31 )
      FltClose(v31);
    v32 = (void *)*((_QWORD *)v12 + 2);
    if ( v32 )
      ObfDereferenceObject(v32);
    ExFreePoolWithTag(v12, 0x73734357u);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14002ad04  push    rbp
0x14002ad06  push    rbx
0x14002ad07  push    rsi
0x14002ad08  push    rdi
0x14002ad09  push    r12
0x14002ad0b  push    r13
0x14002ad0d  push    r14
0x14002ad0f  push    r15
0x14002ad11  lea     rbp, [rsp-78h]
0x14002ad16  sub     rsp, 178h
0x14002ad1d  mov     rax, cs:__security_cookie
0x14002ad24  xor     rax, rsp
0x14002ad27  mov     [rbp+0B0h+var_50], rax
0x14002ad2b  mov     rax, [rbp+0B0h+arg_30]
0x14002ad32  xorps   xmm0, xmm0
0x14002ad35  mov     r12, [rbp+0B0h+Source]
0x14002ad3c  xor     r15d, r15d
0x14002ad3f  mov     [rbp+0B0h+var_90], rax
0x14002ad43  mov     rbx, rdx
0x14002ad46  xor     eax, eax
0x14002ad48  mov     [rbp+0B0h+var_98], rdx
0x14002ad4c  mov     [rbp+0B0h+var_A8], rcx
0x14002ad50  xor     edx, edx; SourceString
0x14002ad52  movups  xmmword ptr [rbp+0B0h+var_100.ObjectName], xmm0
0x14002ad56  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14002ad5a  mov     word ptr [rbp+0B0h+var_B0], ax
0x14002ad5e  mov     [rbp+0B0h+var_58], rax
0x14002ad62  mov     r13, r9
0x14002ad65  mov     rsi, r8
0x14002ad68  mov     [rbp+0B0h+EcpList], r15
0x14002ad6c  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x14002ad70  mov     [rbp+0B0h+EcpContext], r15
0x14002ad74  mov     r14d, r15d
0x14002ad77  movups  xmmword ptr [rbp+0B0h+var_100.Length], xmm0
0x14002ad7b  mov     [rbp+0B0h+RetInstance], r15
0x14002ad7f  movups  xmmword ptr [rbp+0B0h+var_100+1Ch], xmm0
0x14002ad83  mov     [rbp+0B0h+var_128], r15
0x14002ad87  movups  xmmword ptr [rbp+0B0h+var_D0.Size], xmm0
0x14002ad8b  movups  xmmword ptr [rbp+0B0h+var_D0.DeviceObjectHint], xmm0
0x14002ad8f  movups  xmmword ptr [rbp+0B0h+var_88], xmm0
0x14002ad93  movups  [rbp+0B0h+FileInformation], xmm0
0x14002ad97  movups  [rbp+0B0h+var_68], xmm0
0x14002ad9b  call    cs:__imp_RtlInitUnicodeString
0x14002ada2  nop     dword ptr [rax+rax+00h]
0x14002ada7  xor     r10d, r10d
0x14002adaa  test    r13, r13
0x14002adad  jnz     loc_14002AE42
0x14002adb3  movzx   eax, word ptr [rbx+18h]
0x14002adb7  mov     edi, r10d
0x14002adba  movzx   ecx, ax
0x14002adbd  add     cx, [r12]
0x14002adc2  cmp     cx, ax
0x14002adc5  jnb     loc_14002B17F
0x14002adcb  mov     eax, 0FFFFh
0x14002add0  mov     ebx, 0C0000095h
0x14002add5  mov     [rbp+0B0h+DestinationString.MaximumLength], ax
0x14002add9  mov     rdx, [rbp+0B0h+EcpContext]; EcpContext
0x14002addd  test    rdx, rdx
0x14002ade0  jnz     loc_14002B0F8
0x14002ade6  mov     rdx, [rbp+0B0h+EcpList]; EcpList
0x14002adea  test    rdx, rdx
0x14002aded  jnz     loc_14002B5A9
0x14002adf3  test    r14, r14
0x14002adf6  jnz     loc_14002B5C1
0x14002adfc  mov     rcx, [rbp+0B0h+DestinationString.Buffer]; P
0x14002ae00  test    rcx, rcx
0x14002ae03  jnz     loc_14002B5D5
0x14002ae09  mov     rcx, [rbp+0B0h+RetInstance]; FltObject
0x14002ae0d  test    rcx, rcx
0x14002ae10  jnz     loc_14002B5EB
0x14002ae16  test    rdi, rdi
0x14002ae19  jnz     loc_14002B5FC
0x14002ae1f  mov     eax, ebx
0x14002ae21  mov     rcx, [rbp+0B0h+var_50]
0x14002ae25  xor     rcx, rsp; StackCookie
0x14002ae28  call    __security_check_cookie
0x14002ae2d  add     rsp, 178h
0x14002ae34  pop     r15
0x14002ae36  pop     r14
0x14002ae38  pop     r13
0x14002ae3a  pop     r12
0x14002ae3c  pop     rdi
0x14002ae3d  pop     rsi
0x14002ae3e  pop     rbx
0x14002ae3f  pop     rbp
0x14002ae40  retn
0x14002ae42  mov     [rbp+0B0h+var_100.RootDirectory], r13
0x14002ae46  mov     [rbp+0B0h+var_100.ObjectName], r12
0x14002ae4a  mov     r14d, 30h ; '0'
0x14002ae50  xorps   xmm0, xmm0
0x14002ae53  mov     r15d, 240h
0x14002ae59  mov     [rbp+0B0h+var_100.Length], r14d
0x14002ae5d  mov     r8d, 73734357h
0x14002ae63  mov     [rbp+0B0h+var_100.Attributes], r15d
0x14002ae67  mov     ecx, 100h
0x14002ae6c  lea     ebx, [r14-8]
0x14002ae70  mov     edx, ebx
0x14002ae72  movdqu  xmmword ptr [rbp+0B0h+var_100.SecurityDescriptor], xmm0
0x14002ae77  call    cs:__imp_ExAllocatePool2
0x14002ae7e  nop     dword ptr [rax+rax+00h]
0x14002ae83  xor     r10d, r10d
0x14002ae86  mov     rdi, rax
0x14002ae89  test    rax, rax
0x14002ae8c  jz      loc_14002B280
0x14002ae92  mov     ecx, [rbp+0B0h+arg_28]
0x14002ae98  lea     r11d, [r14-2Fh]
0x14002ae9c  mov     eax, ecx
0x14002ae9e  lea     r9, [rbp+0B0h+var_D0]
0x14002aea2  mov     [rsp+1B0h+DriverContext], r9; DriverContext
0x14002aea7  lea     r8, [rdi+8]; FileHandle
0x14002aeab  mov     [rsp+1B0h+Flags], r10d; Flags
0x14002aeb0  lea     r9, [rdi+10h]; FileObject
0x14002aeb4  mov     [rsp+1B0h+EaLength], r10d; EaLength
0x14002aeb9  not     eax
0x14002aebb  mov     [rsp+1B0h+EaBuffer], r10; EaBuffer
0x14002aec0  and     eax, r11d
0x14002aec3  mov     [rsp+1B0h+CreateOptions], ecx; CreateOptions
0x14002aec7  xorps   xmm0, xmm0
0x14002aeca  mov     [rsp+1B0h+CreateDisposition], r11d; CreateDisposition
0x14002aecf  lea     rcx, [rbp+0B0h+var_88]
0x14002aed3  movups  xmmword ptr [rbp+0B0h+var_D0.Size], xmm0
0x14002aed7  lea     edx, ds:3[rax*2]
0x14002aede  mov     [rbp+0B0h+var_D0.Size], bx
0x14002aee2  mov     rax, [rbp+0B0h+var_A8]
0x14002aee6  mov     [rsp+1B0h+ShareAccess], edx; ShareAccess
0x14002aeea  mov     dword ptr [rsp+1B0h+FileAttributes], r10d; FileAttributes
0x14002aeef  mov     [rsp+1B0h+AllocationSize], r10; AllocationSize
0x14002aef4  mov     [rsp+1B0h+IoStatusBlock], rcx; IoStatusBlock
0x14002aef9  lea     rcx, [rbp+0B0h+var_100]
0x14002aefd  mov     [rsp+1B0h+ObjectAttributes], rcx; ObjectAttributes
0x14002af02  mov     rcx, cs:Globals; Filter
0x14002af09  mov     [rbp+0B0h+var_108], edx
0x14002af0c  mov     rdx, rsi; Instance
0x14002af0f  movups  xmmword ptr [rbp+0B0h+var_D0.DeviceObjectHint], xmm0
0x14002af13  mov     [rbp+0B0h+var_B0], rax
0x14002af17  mov     [rsp+1B0h+DesiredAccess], 80000000h; DesiredAccess
0x14002af1f  call    cs:__imp_FltCreateFileEx2
0x14002af26  nop     dword ptr [rax+rax+00h]
0x14002af2b  mov     ebx, eax
0x14002af2d  add     eax, 3FFFFC98h
0x14002af32  cmp     eax, 1
0x14002af35  ja      loc_14002B1FF
0x14002af3b  mov     rcx, cs:Globals; Filter
0x14002af42  lea     r8, [rbp+0B0h+EcpList]; EcpList
0x14002af46  xor     edx, edx; Flags
0x14002af48  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14002af4f  nop     dword ptr [rax+rax+00h]
0x14002af54  xor     r10d, r10d
0x14002af57  mov     ebx, eax
0x14002af59  test    eax, eax
0x14002af5b  js      loc_14002B285
0x14002af61  mov     rcx, cs:Globals; Filter
0x14002af68  lea     rax, [rbp+0B0h+EcpContext]
0x14002af6c  mov     [rsp+1B0h+IoStatusBlock], rax; EcpContext
0x14002af71  lea     r8d, [r14-10h]; SizeOfContext
0x14002af75  mov     dword ptr [rsp+1B0h+ObjectAttributes], 63744357h; PoolTag
0x14002af7d  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14002af84  xor     r9d, r9d; Flags
0x14002af87  mov     qword ptr [rsp+1B0h+DesiredAccess], r10; CleanupCallback
0x14002af8c  call    cs:__imp_FltAllocateExtraCreateParameter
0x14002af93  nop     dword ptr [rax+rax+00h]
0x14002af98  xor     r10d, r10d
0x14002af9b  mov     ebx, eax
0x14002af9d  test    eax, eax
0x14002af9f  js      loc_14002B285
0x14002afa5  mov     rax, [rbp+0B0h+EcpContext]
0x14002afa9  mov     word ptr [rax+18h], 1
0x14002afaf  mov     rax, [rbp+0B0h+EcpContext]
0x14002afb3  mov     [rax], r10
0x14002afb6  mov     rax, [rbp+0B0h+EcpContext]
0x14002afba  mov     [rax+8], r10
0x14002afbe  mov     rax, [rbp+0B0h+EcpContext]
0x14002afc2  mov     [rax+10h], r10
0x14002afc6  mov     r8, [rbp+0B0h+EcpContext]; EcpContext
0x14002afca  mov     rdx, [rbp+0B0h+EcpList]; EcpList
0x14002afce  mov     rcx, cs:Globals; Filter
0x14002afd5  call    cs:__imp_FltInsertExtraCreateParameter
0x14002afdc  nop     dword ptr [rax+rax+00h]
0x14002afe1  xor     r10d, r10d
0x14002afe4  mov     ebx, eax
0x14002afe6  test    eax, eax
0x14002afe8  js      loc_14002B285
0x14002afee  lea     eax, [r14-8]
0x14002aff2  xorps   xmm0, xmm0
0x14002aff5  mov     [rbp+0B0h+var_D0.Size], ax
0x14002aff9  mov     rax, [rbp+0B0h+var_A8]
0x14002affd  mov     [rbp+0B0h+var_B0], rax
0x14002b001  mov     rax, [rbp+0B0h+EcpList]
0x14002b005  mov     [rbp+0B0h+var_D0.ExtraCreateParameter], rax
0x14002b009  mov     dword ptr [rbp+0B0h+var_D0+2], r10d
0x14002b00d  mov     word ptr [rbp+0B0h+var_D0+6], r10w
0x14002b012  movdqu  xmmword ptr [rbp+0B0h+var_D0.DeviceObjectHint], xmm0
0x14002b017  mov     [rbp+0B0h+var_100.Length], r14d
0x14002b01b  mov     [rbp+0B0h+var_100.Attributes], r15d
0x14002b01f  movdqu  xmmword ptr [rbp+0B0h+var_100.SecurityDescriptor], xmm0
0x14002b024  cmp     [rbp+0B0h+DestinationString.Length], r10w
0x14002b029  jbe     loc_14002B269
0x14002b02f  lea     rax, [rbp+0B0h+DestinationString]
0x14002b033  mov     [rbp+0B0h+var_100.RootDirectory], r10
0x14002b037  mov     [rbp+0B0h+var_100.ObjectName], rax
0x14002b03b  mov     rcx, cs:Globals; Filter
0x14002b042  lea     rax, [rbp+0B0h+var_D0]
0x14002b046  mov     [rsp+1B0h+DriverContext], rax; DriverContext
0x14002b04b  lea     r13, [rdi+10h]
0x14002b04f  mov     eax, [rbp+0B0h+arg_28]
0x14002b055  lea     r8, [rdi+8]; FileHandle
0x14002b059  mov     [rsp+1B0h+Flags], r10d; Flags
0x14002b05e  mov     r9, r13; FileObject
0x14002b061  mov     [rsp+1B0h+EaLength], r10d; EaLength
0x14002b066  mov     rdx, rsi; Instance
0x14002b069  mov     [rsp+1B0h+EaBuffer], r10; EaBuffer
0x14002b06e  mov     [rsp+1B0h+CreateOptions], eax; CreateOptions
0x14002b072  mov     eax, [rbp+0B0h+var_108]
0x14002b075  mov     [rsp+1B0h+CreateDisposition], 1; CreateDisposition
0x14002b07d  mov     [rsp+1B0h+ShareAccess], eax; ShareAccess
0x14002b081  lea     rax, [rbp+0B0h+var_88]
0x14002b085  mov     dword ptr [rsp+1B0h+FileAttributes], r10d; FileAttributes
0x14002b08a  mov     [rsp+1B0h+AllocationSize], r10; AllocationSize
0x14002b08f  mov     [rsp+1B0h+IoStatusBlock], rax; IoStatusBlock
0x14002b094  lea     rax, [rbp+0B0h+var_100]
0x14002b098  mov     [rsp+1B0h+ObjectAttributes], rax; ObjectAttributes
0x14002b09d  mov     [rsp+1B0h+DesiredAccess], 80000000h; DesiredAccess
0x14002b0a5  call    cs:__imp_FltCreateFileEx2
0x14002b0ac  nop     dword ptr [rax+rax+00h]
0x14002b0b1  xor     r10d, r10d
0x14002b0b4  mov     ebx, eax
0x14002b0b6  test    eax, eax
0x14002b0b8  js      loc_14002B28D
0x14002b0be  mov     rdx, [rbp+0B0h+EcpContext]; EcpContext
0x14002b0c2  mov     rcx, cs:Globals; Filter
0x14002b0c9  call    cs:__imp_FltIsEcpAcknowledged
0x14002b0d0  nop     dword ptr [rax+rax+00h]
0x14002b0d5  xor     r10d, r10d
0x14002b0d8  test    al, al
0x14002b0da  jz      loc_14002B20E
0x14002b0e0  mov     rax, [rbp+0B0h+EcpContext]
0x14002b0e4  mov     rcx, [rax]
0x14002b0e7  test    rcx, rcx
0x14002b0ea  jz      loc_14002B20E
0x14002b0f0  mov     rsi, rcx
0x14002b0f3  jmp     loc_14002B20E
0x14002b0f8  mov     rcx, cs:Globals; Filter
0x14002b0ff  call    cs:__imp_FltIsEcpAcknowledged
0x14002b106  nop     dword ptr [rax+rax+00h]
0x14002b10b  xor     r10d, r10d
0x14002b10e  test    al, al
0x14002b110  jz      loc_14002ADE6
0x14002b116  mov     rdx, [rbp+0B0h+EcpList]; EcpList
0x14002b11a  lea     r9, [rbp+0B0h+EcpContext]; EcpContext
0x14002b11e  mov     rcx, cs:Globals; Filter
0x14002b125  lea     r8, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14002b12c  mov     qword ptr [rsp+1B0h+DesiredAccess], r10; EcpContextSize
0x14002b131  call    cs:__imp_FltRemoveExtraCreateParameter
0x14002b138  nop     dword ptr [rax+rax+00h]
0x14002b13d  mov     rdx, [rbp+0B0h+EcpContext]; EcpContext
0x14002b141  mov     rcx, [rdx]; FltObject
0x14002b144  test    rcx, rcx
0x14002b147  jnz     loc_14002B56A
0x14002b14d  mov     rcx, [rdx+8]; FltObject
0x14002b151  test    rcx, rcx
0x14002b154  jnz     loc_14002B57F
0x14002b15a  mov     rcx, [rdx+10h]; FileNameInformation
0x14002b15e  test    rcx, rcx
0x14002b161  jnz     loc_14002B594
0x14002b167  mov     rcx, cs:Globals; Filter
0x14002b16e  call    cs:__imp_FltFreeExtraCreateParameter
0x14002b175  nop     dword ptr [rax+rax+00h]
0x14002b17a  jmp     loc_14002ADE6
0x14002b17f  mov     [rbp+0B0h+DestinationString.MaximumLength], cx
0x14002b183  mov     r8d, 6E664357h
0x14002b189  movzx   edx, cx
0x14002b18c  mov     ecx, 100h
0x14002b191  call    cs:__imp_ExAllocatePool2
0x14002b198  nop     dword ptr [rax+rax+00h]
0x14002b19d  xor     r10d, r10d
0x14002b1a0  mov     [rbp+0B0h+DestinationString.Buffer], rax
0x14002b1a4  test    rax, rax
0x14002b1a7  jz      loc_14002B276
0x14002b1ad  lea     rdx, [rbx+18h]; SourceString
0x14002b1b1  mov     [rbp+0B0h+DestinationString.Length], r10w
0x14002b1b6  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14002b1ba  call    cs:__imp_RtlCopyUnicodeString
0x14002b1c1  nop     dword ptr [rax+rax+00h]
0x14002b1c6  mov     rdx, r12; Source
0x14002b1c9  lea     rcx, [rbp+0B0h+DestinationString]; Destination
0x14002b1cd  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002b1d4  nop     dword ptr [rax+rax+00h]
0x14002b1d9  xor     r10d, r10d
0x14002b1dc  mov     ebx, eax
0x14002b1de  test    eax, eax
0x14002b1e0  js      loc_14002ADD9
0x14002b1e6  mov     rsi, [rbp+0B0h+var_98]
0x14002b1ea  lea     rax, [rbp+0B0h+DestinationString]
0x14002b1ee  mov     [rbp+0B0h+var_100.RootDirectory], r10
0x14002b1f2  mov     [rbp+0B0h+var_100.ObjectName], rax
0x14002b1f6  mov     rsi, [rsi+28h]
0x14002b1fa  jmp     loc_14002AE4A
0x14002b1ff  lea     r13, [rdi+10h]
0x14002b203  xor     r10d, r10d
0x14002b206  test    ebx, ebx
  ... truncated ...
```
