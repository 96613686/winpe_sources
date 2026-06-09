# WcCopyAsPlaceHolder

- ea: `0x14002da54`
- end: `0x14002e3eb`
- name: `WcCopyAsPlaceHolder`
- size: `2455`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140002d20`
- `0x14001a62c`
- `0x14002befc`
- `0x140030d54`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400020c4`
- `0x1400024d4`
- `0x140004198`
- `0x1400048a4`
- `0x140007c60`
- `0x1400080c0`
- `0x14001e228`
- `0x14001fa5c`
- `0x140020840`
- `0x14002da54`
- `0x14002f710`
- `0x14002fb20`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14002e0b3`
- `ntoskrnl!IoGetSilo` at `0x14002e0b3`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e3b9`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e3b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e359`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e373`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e359`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e373`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002e38f`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14002e38f`
- `FLTMGR!FltCreateFileEx2` at `0x14002e165`
- `FLTMGR!FltCreateFileEx2` at `0x14002e165`
- `FLTMGR!FltFsControlFile` at `0x14002dc7d`
- `FLTMGR!FltFsControlFile` at `0x14002dc7d`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002de2a`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14002de2a`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002e053`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14002e053`
- `FLTMGR!FltClose` at `0x14002e3a4`
- `FLTMGR!FltClose` at `0x14002e3a4`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002e1c1`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14002e1c1`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14002de96`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14002de96`
- `FLTMGR!FltQueryInformationFile` at `0x14002dd54`
- `FLTMGR!FltQueryInformationFile` at `0x14002dfa6`
- `FLTMGR!FltQueryInformationFile` at `0x14002dd54`
- `FLTMGR!FltQueryInformationFile` at `0x14002dfa6`
- `FLTMGR!FltReleaseContext` at `0x14002e33c`
- `FLTMGR!FltReleaseContext` at `0x14002e33c`
- `FLTMGR!FltGetInstanceContext` at `0x14002dbb2`
- `FLTMGR!FltGetInstanceContext` at `0x14002dbb2`

## pseudocode

```c
__int64 __fastcall WcCopyAsPlaceHolder(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        struct _FLT_INSTANCE *a3,
        struct _UNICODE_STRING *a4,
        struct _FLT_INSTANCE *a5,
        void *a6,
        __int64 a7,
        __int64 a8,
        int a9,
        char a10)
{
  NTSTATUS InstanceContext; // eax
  NTSTATUS v12; // ebx
  int v13; // r9d
  int v14; // r8d
  int v15; // edx
  int v16; // ecx
  NTSTATUS v17; // eax
  int v18; // edx
  ULONG v19; // ebx
  __int64 v20; // rcx
  ULONG v21; // eax
  int Ea; // eax
  int Security; // eax
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  __int16 v26; // r9
  struct _FILE_OBJECT *v27; // rdx
  NTSTATUS v28; // eax
  char v29; // r12
  NTSTATUS Parameter; // eax
  NTSTATUS v31; // eax
  int v32; // edx
  int v33; // r9d
  int v34; // eax
  int v35; // eax
  char OutputBufferLength; // [rsp+30h] [rbp-D0h]
  char OutputBufferLengtha; // [rsp+30h] [rbp-D0h]
  char LengthReturned; // [rsp+38h] [rbp-C8h]
  PULONG LengthReturneda; // [rsp+38h] [rbp-C8h]
  char FileAttributes; // [rsp+40h] [rbp-C0h]
  PVOID EcpContext; // [rsp+80h] [rbp-80h] BYREF
  ULONG CreateOptions; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-70h]
  ULONG EaLength; // [rsp+98h] [rbp-68h]
  PFILE_OBJECT v46; // [rsp+A0h] [rbp-60h] BYREF
  PFLT_INSTANCE Instance; // [rsp+A8h] [rbp-58h]
  PECP_LIST EcpList; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING *v50; // [rsp+C0h] [rbp-40h]
  PFLT_CONTEXT Context; // [rsp+C8h] [rbp-38h] BYREF
  PVOID P; // [rsp+D0h] [rbp-30h]
  PVOID EaBuffer; // [rsp+D8h] [rbp-28h]
  void *FileHandle; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v55; // [rsp+E8h] [rbp-18h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+F0h] [rbp-10h] BYREF
  __int64 Silo; // [rsp+110h] [rbp+10h]
  void *v58; // [rsp+118h] [rbp+18h]
  __int64 v59; // [rsp+120h] [rbp+20h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+128h] [rbp+28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+158h] [rbp+58h] BYREF
  __int128 v62; // [rsp+168h] [rbp+68h] BYREF
  __int128 v63; // [rsp+178h] [rbp+78h]
  __int64 v64; // [rsp+188h] [rbp+88h]
  __int128 FileInformation; // [rsp+190h] [rbp+90h] BYREF
  __int64 v66; // [rsp+1A0h] [rbp+A0h]
  __int128 v67; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v68; // [rsp+1B8h] [rbp+B8h]
  _QWORD InputBuffer[3]; // [rsp+1C8h] [rbp+C8h] BYREF
  int v70; // [rsp+1E0h] [rbp+E0h]
  int v71; // [rsp+1E4h] [rbp+E4h]
  _BYTE v72[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  ULONG *p_CreateOptions; // [rsp+208h] [rbp+108h]
  __int64 v74; // [rsp+210h] [rbp+110h]

  Instance = a5;
  v58 = a6;
  v55 = a7;
  v59 = a1;
  v50 = a4;
  FileObject = a2;
  EaBuffer = 0;
  EaLength = 0;
  P = 0;
  LODWORD(v49) = 0;
  EcpList = 0;
  EcpContext = 0;
  LOWORD(Silo) = 0;
  FileHandle = 0;
  v46 = 0;
  v66 = 0;
  v64 = 0;
  Context = 0;
  InputBuffer[0] = 1793;
  InputBuffer[1] = 5633;
  InputBuffer[2] = 3841;
  v70 = 3;
  v71 = 159;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v67 = 0;
  v68 = 0;
  FileInformation = 0;
  v62 = 0;
  v63 = 0;
  if ( !a9 || !a8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        150,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        217);
    goto LABEL_72;
  }
  if ( a9 != *(unsigned __int16 *)(a8 + 4) + 8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        151,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        224);
LABEL_72:
    v12 = -1073741811;
    goto LABEL_73;
  }
  InstanceContext = FltGetInstanceContext(a3, &Context);
  v12 = InstanceContext;
  if ( InstanceContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_73;
    LengthReturned = InstanceContext;
    OutputBufferLength = -5;
    v13 = 152;
LABEL_9:
    v14 = 15;
LABEL_10:
    v15 = 2;
LABEL_11:
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      v14,
      v13,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      OutputBufferLength,
      LengthReturned);
    goto LABEL_73;
  }
  v16 = *((_DWORD *)Context + 2);
  if ( v16 == 13 || v16 == 6 )
  {
    v17 = FltFsControlFile(a3, FileObject, 0x1401C4u, InputBuffer, 0x20u, 0, 0, 0);
    v19 = v17;
    if ( v17 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 3;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          15,
          153,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          17,
          v17);
      }
      if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
      {
        CreateOptions = v19;
        p_CreateOptions = &CreateOptions;
        v74 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v20, &byte_14000BD1F, 0, 0, 3, v72);
      }
    }
  }
  v12 = FltQueryInformationFile(a3, FileObject, &FileInformation, 0x18u, FileStandardInformation, 0);
  if ( v12 >= 0 )
  {
    v21 = 2162728;
    if ( BYTE5(v66) )
      v21 = 2162729;
    CreateOptions = v21;
    Ea = WcQueryEa(a3, FileObject);
    v12 = Ea;
    if ( Ea < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      LengthReturned = Ea;
      v13 = 154;
      OutputBufferLength = 47;
      goto LABEL_9;
    }
    if ( (a10 & 0x40) == 0 )
    {
      Security = WcQuerySecurity(a3, FileObject, (unsigned int)(v55 != 0) + 158, (__int64)&v49);
      v12 = Security;
      if ( Security < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_73;
        LengthReturned = Security;
        v13 = 155;
        OutputBufferLength = 64;
        goto LABEL_9;
      }
    }
    v24 = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
    v12 = v24;
    if ( v24 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      LengthReturned = v24;
      v13 = 156;
      OutputBufferLength = 78;
LABEL_33:
      v14 = 5;
      goto LABEL_10;
    }
    v25 = FltAllocateExtraCreateParameterFromLookasideList(
            Globals,
            &GUID_ECP_ATOMIC_CREATE,
            0x58u,
            0,
            0,
            qword_14000E280,
            &EcpContext);
    v12 = v25;
    if ( v25 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      LengthReturned = v25;
      v13 = 157;
      OutputBufferLength = 91;
      goto LABEL_33;
    }
    memset(EcpContext, 0, 0x58u);
    *(_WORD *)EcpContext = 88;
    *((_WORD *)EcpContext + 1) = 2;
    *((_WORD *)EcpContext + 2) = 0;
    v12 = RtlUShortAdd(*(_WORD *)(a8 + 4), 8u, (USHORT *)EcpContext + 3);
    if ( v12 < 0 )
      goto LABEL_73;
    *((_QWORD *)EcpContext + 1) = a8;
    if ( !BYTE5(v66) )
    {
      *((_WORD *)EcpContext + 1) |= 1u;
      *((_QWORD *)EcpContext + 2) = *((_QWORD *)&FileInformation + 1);
      *((_WORD *)EcpContext + 1) |= 4u;
      *((_QWORD *)EcpContext + 3) = *((_QWORD *)&FileInformation + 1);
      *((_WORD *)EcpContext + 1) |= v26;
    }
    v27 = FileObject;
    *((_WORD *)EcpContext + 1) |= 0x400u;
    *((_WORD *)EcpContext + 1) |= 0x200u;
    v28 = FltQueryInformationFile(a3, v27, &v62, 0x28u, FileBasicInformation, 0);
    v12 = v28;
    if ( v28 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      LengthReturned = v28;
      v13 = 158;
      OutputBufferLength = -107;
LABEL_43:
      v14 = 15;
      LOBYTE(v15) = 2;
      goto LABEL_11;
    }
    v29 = v64 & 1;
    if ( (v64 & 1) != 0 )
      LODWORD(v64) = v64 & 0xFFFFFFFE;
    v67 = v62;
    v68 = v63;
    *((_QWORD *)EcpContext + 4) = &v67;
    *((_WORD *)EcpContext + 1) |= 0x10u;
    Parameter = FltInsertExtraCreateParameter(Globals, EcpList, EcpContext);
    v12 = Parameter;
    if ( Parameter < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      LengthReturned = Parameter;
      v13 = 159;
      OutputBufferLength = -83;
      goto LABEL_43;
    }
    Silo = 1;
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    if ( v55 )
      Silo = IoGetSilo(v55);
    DriverContext.ExtraCreateParameter = EcpList;
    ObjectAttributes.RootDirectory = v58;
    ObjectAttributes.ObjectName = v50;
    ObjectAttributes.SecurityDescriptor = P;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.SecurityQualityOfService = 0;
    v31 = FltCreateFileEx2(
            Globals,
            Instance,
            &FileHandle,
            &v46,
            0x40040000u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            v64 & 0xFFFFAFFF | 0x1000,
            0,
            2u,
            CreateOptions,
            EaBuffer,
            EaLength,
            0,
            &DriverContext);
    v12 = v31;
    if ( v31 < 0 )
    {
      if ( v31 == -1073741771 || v31 == -1073739511 )
      {
        v12 = 0;
        goto LABEL_73;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      FileAttributes = v31;
      v33 = 160;
      LengthReturneda = (PULONG)&v50->Length;
      OutputBufferLengtha = -26;
LABEL_60:
      LOBYTE(v32) = 2;
      WPP_RECORDER_SF_sDZd(
        WPP_GLOBAL_Control->DeviceExtension,
        v32,
        10,
        v33,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        OutputBufferLengtha,
        (__int64)LengthReturneda,
        FileAttributes);
      goto LABEL_73;
    }
    if ( !FltIsEcpAcknowledged(Globals, EcpContext) )
    {
      v12 = -1073741637;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      v33 = 161;
      FileAttributes = -69;
      LengthReturneda = (PULONG)&v50->Length;
      OutputBufferLengtha = -11;
      goto LABEL_60;
    }
    if ( (v64 & 0x800) != 0 )
    {
      v34 = WcCopyFileCompression(FileObject, a3, v46, Instance);
      v12 = v34;
      if ( v34 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_73;
        LengthReturned = v34;
        v13 = 162;
        OutputBufferLength = 10;
        goto LABEL_43;
      }
    }
    v35 = WcCopyFileDataStreams(v59, FileObject, a3, FileHandle, v46, Instance, 1);
    v12 = v35;
    if ( v35 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      LengthReturned = v35;
      v13 = 163;
      OutputBufferLength = 27;
      goto LABEL_43;
    }
    if ( v29 )
      v12 = WcSetFileAttributes(v46, Instance);
  }
LABEL_73:
  if ( Context )
    FltReleaseContext(Context);
  if ( P )
    ExFreePoolWithTag(P, 0x73664357u);
  if ( EaBuffer )
    ExFreePoolWithTag(EaBuffer, 0x65664357u);
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v46 )
    ObfDereferenceObject(v46);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14002da54  push    rbp
0x14002da56  push    rbx
0x14002da57  push    rsi
0x14002da58  push    rdi
0x14002da59  push    r12
0x14002da5b  push    r13
0x14002da5d  push    r14
0x14002da5f  push    r15
0x14002da61  lea     rbp, [rsp-128h]
0x14002da69  sub     rsp, 228h
0x14002da70  mov     rax, cs:__security_cookie
0x14002da77  xor     rax, rsp
0x14002da7a  mov     [rbp+160h+var_48], rax
0x14002da81  mov     rax, [rbp+160h+arg_20]
0x14002da88  xor     edi, edi
0x14002da8a  xorps   xmm0, xmm0
0x14002da8d  mov     [rbp+160h+Instance], rax
0x14002da91  mov     rax, [rbp+160h+arg_28]
0x14002da98  xorps   xmm1, xmm1
0x14002da9b  mov     [rbp+160h+var_148], rax
0x14002da9f  mov     r13, r8
0x14002daa2  mov     rax, [rbp+160h+arg_30]
0x14002daa9  mov     [rbp+160h+var_178], rax
0x14002daad  xor     eax, eax
0x14002daaf  mov     [rbp+160h+var_140], rcx
0x14002dab3  mov     ecx, [rbp+160h+arg_40]
0x14002dab9  mov     [rbp+160h+var_1A0], r9
0x14002dabd  mov     [rbp+160h+FileObject], rdx
0x14002dac1  mov     [rbp+160h+var_188], rdi
0x14002dac5  mov     [rbp+160h+var_1C8], edi
0x14002dac8  mov     [rbp+160h+P], rdi
0x14002dacc  mov     dword ptr [rbp+160h+var_1A8], edi
0x14002dacf  mov     [rbp+160h+EcpList], rdi
0x14002dad3  mov     [rbp+160h+EcpContext], rdi
0x14002dad7  mov     word ptr [rbp+160h+var_150], ax
0x14002dadb  mov     [rbp+160h+FileHandle], rdi
0x14002dadf  mov     [rbp+160h+var_1C0], rdi
0x14002dae3  mov     [rbp+160h+var_C0], rax
0x14002daea  mov     [rbp+160h+var_D8], rax
0x14002daf1  mov     [rbp+160h+Context], rdi
0x14002daf5  mov     [rbp+160h+InputBuffer], 701h
0x14002db00  mov     [rbp+160h+var_90], 1601h
0x14002db0b  mov     [rbp+160h+var_88], 0F01h
0x14002db16  mov     [rbp+160h+var_80], 3
0x14002db20  mov     [rbp+160h+var_7C], 9Fh
0x14002db2a  movups  xmmword ptr [rbp+160h+ObjectAttributes.ObjectName], xmm0
0x14002db2e  movups  xmmword ptr [rbp+160h+var_170.Size], xmm0
0x14002db32  movups  xmmword ptr [rbp+160h+var_170.DeviceObjectHint], xmm0
0x14002db36  movups  xmmword ptr [rbp+160h+ObjectAttributes.Length], xmm0
0x14002db3a  movups  xmmword ptr [rbp+160h+ObjectAttributes+1Ch], xmm0
0x14002db3e  movups  xmmword ptr [rbp+160h+IoStatusBlock], xmm0
0x14002db42  movups  [rbp+160h+var_B8], xmm0
0x14002db49  movups  [rbp+160h+var_A8], xmm0
0x14002db50  movups  [rbp+160h+FileInformation], xmm1
0x14002db57  movups  [rbp+160h+var_F8], xmm0
0x14002db5b  movups  [rbp+160h+var_E8], xmm0
0x14002db5f  test    ecx, ecx
0x14002db61  jz      loc_14002E2DE
0x14002db67  mov     r12, [rbp+160h+arg_38]
0x14002db6e  test    r12, r12
0x14002db71  jz      loc_14002E2DE
0x14002db77  movzx   eax, word ptr [r12+4]
0x14002db7d  add     eax, 8
0x14002db80  cmp     ecx, eax
0x14002db82  jz      short loc_14002DBAB
0x14002db84  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002db8b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002db92  jz      loc_14002E32E
0x14002db98  mov     r9d, 97h
0x14002db9e  mov     [rsp+260h+OutputBufferLength], 18E0h
0x14002dba6  jmp     loc_14002E2FC
0x14002dbab  lea     rdx, [rbp+160h+Context]; Context
0x14002dbaf  mov     rcx, r13; Instance
0x14002dbb2  call    cs:__imp_FltGetInstanceContext
0x14002dbb9  nop     dword ptr [rax+rax+00h]
0x14002dbbe  mov     ebx, eax
0x14002dbc0  test    eax, eax
0x14002dbc2  jns     short loc_14002DC22
0x14002dbc4  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002dbcb  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002dbd2  jz      loc_14002E333
0x14002dbd8  mov     dword ptr [rsp+260h+LengthReturned], eax
0x14002dbdc  lea     r14, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002dbe3  mov     [rsp+260h+OutputBufferLength], 18FBh
0x14002dbeb  lea     r15, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002dbf2  mov     r9d, 98h
0x14002dbf8  mov     r8d, 0Fh
0x14002dbfe  mov     edx, 2
0x14002dc03  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dc0a  mov     [rsp+260h+OutputBuffer], r14
0x14002dc0f  mov     qword ptr [rsp+260h+InputBufferLength], r15
0x14002dc14  mov     rcx, [rcx+40h]
0x14002dc18  call    WPP_RECORDER_SF_sDd
0x14002dc1d  jmp     loc_14002E333
0x14002dc22  mov     rax, [rbp+160h+Context]
0x14002dc26  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002dc2d  lea     r14, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14002dc34  mov     edi, 5
0x14002dc39  lea     r15, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14002dc40  mov     ecx, [rax+8]
0x14002dc43  cmp     ecx, 0Dh
0x14002dc46  jz      short loc_14002DC51
0x14002dc48  cmp     ecx, 6
0x14002dc4b  jnz     loc_14002DD33
0x14002dc51  mov     rdx, [rbp+160h+FileObject]; FileObject
0x14002dc55  lea     r9, [rbp+160h+InputBuffer]; InputBuffer
0x14002dc5c  xor     eax, eax
0x14002dc5e  mov     r8d, 1401C4h; FsControlCode
0x14002dc64  mov     [rsp+260h+LengthReturned], rax; LengthReturned
0x14002dc69  mov     rcx, r13; Instance
0x14002dc6c  mov     [rsp+260h+OutputBufferLength], eax; OutputBufferLength
0x14002dc70  mov     [rsp+260h+OutputBuffer], rax; OutputBuffer
0x14002dc75  mov     [rsp+260h+InputBufferLength], 20h ; ' '; InputBufferLength
0x14002dc7d  call    cs:__imp_FltFsControlFile
0x14002dc84  nop     dword ptr [rax+rax+00h]
0x14002dc89  mov     ebx, eax
0x14002dc8b  test    eax, eax
0x14002dc8d  jns     loc_14002DD33
0x14002dc93  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002dc9a  jz      short loc_14002DCD0
0x14002dc9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dca3  mov     r9d, 99h
0x14002dca9  mov     dword ptr [rsp+260h+LengthReturned], eax
0x14002dcad  mov     r8d, 0Fh
0x14002dcb3  mov     [rsp+260h+OutputBufferLength], 1911h
0x14002dcbb  mov     dl, 3
0x14002dcbd  mov     [rsp+260h+OutputBuffer], r14
0x14002dcc2  mov     rcx, [rcx+40h]
0x14002dcc6  mov     qword ptr [rsp+260h+InputBufferLength], r15
0x14002dccb  call    WPP_RECORDER_SF_sDd
0x14002dcd0  mov     eax, cs:dword_14000E060
0x14002dcd6  cmp     eax, edi
0x14002dcd8  jbe     short loc_14002DD33
0x14002dcda  mov     rdx, 400000000000h
0x14002dce4  lea     rcx, dword_14000E060
0x14002dceb  call    _tlgKeywordOn
0x14002dcf0  test    al, al
0x14002dcf2  jz      short loc_14002DD33
0x14002dcf4  lea     rax, [rbp+160h+var_1D8]
0x14002dcf8  mov     [rbp+160h+var_1D8], ebx
0x14002dcfb  mov     [rbp+160h+var_58], rax
0x14002dd02  lea     rdx, byte_14000BD1F
0x14002dd09  lea     rax, [rbp+160h+var_78]
0x14002dd10  mov     [rbp+160h+var_50], 4
0x14002dd1b  mov     [rsp+260h+OutputBuffer], rax
0x14002dd20  xor     r9d, r9d
0x14002dd23  xor     r8d, r8d
0x14002dd26  mov     [rsp+260h+InputBufferLength], 3
0x14002dd2e  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002dd33  mov     rdx, [rbp+160h+FileObject]; FileObject
0x14002dd37  lea     r8, [rbp+160h+FileInformation]; FileInformation
0x14002dd3e  mov     [rsp+260h+OutputBuffer], 0; LengthReturned
0x14002dd47  mov     r9d, 18h; Length
0x14002dd4d  mov     rcx, r13; Instance
0x14002dd50  mov     [rsp+260h+InputBufferLength], edi; FileInformationClass
0x14002dd54  call    cs:__imp_FltQueryInformationFile
0x14002dd5b  nop     dword ptr [rax+rax+00h]
0x14002dd60  mov     ebx, eax
0x14002dd62  test    eax, eax
0x14002dd64  js      loc_14002E333
0x14002dd6a  cmp     byte ptr [rbp+160h+var_C0+5], 0
0x14002dd71  lea     r9, [rbp+160h+var_1C8]
0x14002dd75  mov     rdx, [rbp+160h+FileObject]; FileObject
0x14002dd79  lea     r8, [rbp+160h+var_188]
0x14002dd7d  mov     eax, 210028h
0x14002dd82  lea     ecx, [rax+1]
0x14002dd85  cmovnz  eax, ecx
0x14002dd88  mov     rcx, r13; Instance
0x14002dd8b  mov     [rbp+160h+var_1D8], eax
0x14002dd8e  call    WcQueryEa
0x14002dd93  mov     ebx, eax
0x14002dd95  test    eax, eax
0x14002dd97  jns     short loc_14002DDBD
0x14002dd99  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002dda0  jz      loc_14002E333
0x14002dda6  mov     dword ptr [rsp+260h+LengthReturned], eax
0x14002ddaa  mov     r9d, 9Ah
0x14002ddb0  mov     [rsp+260h+OutputBufferLength], 192Fh
0x14002ddb8  jmp     loc_14002DBF8
0x14002ddbd  mov     rax, [rbp+160h+var_178]
0x14002ddc1  neg     rax
0x14002ddc4  sbb     r8d, r8d
0x14002ddc7  neg     r8d
0x14002ddca  add     r8d, 9Eh; SecurityInformation
0x14002ddd1  test    [rbp+160h+arg_48], 40h
0x14002ddd8  jnz     short loc_14002DE1D
0x14002ddda  mov     rdx, [rbp+160h+FileObject]; FileObject
0x14002ddde  lea     rax, [rbp+160h+var_1A8]
0x14002dde2  lea     r9, [rbp+160h+P]
0x14002dde6  mov     qword ptr [rsp+260h+InputBufferLength], rax; __int64
0x14002ddeb  mov     rcx, r13; Instance
0x14002ddee  call    WcQuerySecurity
0x14002ddf3  mov     ebx, eax
0x14002ddf5  test    eax, eax
0x14002ddf7  jns     short loc_14002DE1D
0x14002ddf9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002de00  jz      loc_14002E333
0x14002de06  mov     dword ptr [rsp+260h+LengthReturned], eax
0x14002de0a  mov     r9d, 9Bh
0x14002de10  mov     [rsp+260h+OutputBufferLength], 1940h
0x14002de18  jmp     loc_14002DBF8
0x14002de1d  mov     rcx, cs:Globals; Filter
0x14002de24  lea     r8, [rbp+160h+EcpList]; EcpList
0x14002de28  xor     edx, edx; Flags
0x14002de2a  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14002de31  nop     dword ptr [rax+rax+00h]
0x14002de36  mov     ebx, eax
0x14002de38  test    eax, eax
0x14002de3a  jns     short loc_14002DE63
0x14002de3c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002de43  jz      loc_14002E333
0x14002de49  mov     dword ptr [rsp+260h+LengthReturned], eax
0x14002de4d  mov     r9d, 9Ch
0x14002de53  mov     [rsp+260h+OutputBufferLength], 194Eh
0x14002de5b  mov     r8d, edi
0x14002de5e  jmp     loc_14002DBFE
0x14002de63  mov     rcx, cs:Globals; Filter
0x14002de6a  lea     rax, [rbp+160h+EcpContext]
0x14002de6e  mov     qword ptr [rsp+260h+OutputBufferLength], rax; EcpContext
0x14002de73  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x14002de7a  xor     r9d, r9d; Flags
0x14002de7d  lea     rax, qword_14000E280
0x14002de84  mov     [rsp+260h+OutputBuffer], rax; LookasideList
0x14002de89  mov     qword ptr [rsp+260h+InputBufferLength], 0; CleanupCallback
0x14002de92  lea     r8d, [r9+58h]; SizeOfContext
0x14002de96  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14002de9d  nop     dword ptr [rax+rax+00h]
0x14002dea2  mov     ebx, eax
0x14002dea4  test    eax, eax
0x14002dea6  jns     short loc_14002DEC9
0x14002dea8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002deaf  jz      loc_14002E333
0x14002deb5  mov     dword ptr [rsp+260h+LengthReturned], eax
0x14002deb9  mov     r9d, 9Dh
0x14002debf  mov     [rsp+260h+OutputBufferLength], 195Bh
0x14002dec7  jmp     short loc_14002DE5B
0x14002dec9  mov     rcx, [rbp+160h+EcpContext]; void *
0x14002decd  mov     ebx, 58h ; 'X'
0x14002ded2  mov     r8d, ebx; Size
0x14002ded5  xor     edx, edx; Val
0x14002ded7  call    memset
0x14002dedc  mov     rax, [rbp+160h+EcpContext]
0x14002dee0  lea     edi, [rbx-56h]
0x14002dee3  xor     ecx, ecx
0x14002dee5  lea     r9d, [rbx-50h]
0x14002dee9  mov     edx, r9d; usAddend
0x14002deec  mov     [rax], bx
0x14002deef  mov     rax, [rbp+160h+EcpContext]
0x14002def3  mov     [rax+2], di
0x14002def7  mov     rax, [rbp+160h+EcpContext]
0x14002defb  mov     [rax+4], cx
0x14002deff  mov     r8, [rbp+160h+EcpContext]
0x14002df03  movzx   ecx, word ptr [r12+4]; usAugend
0x14002df09  add     r8, 6; pusResult
0x14002df0d  call    RtlUShortAdd
0x14002df12  mov     ebx, eax
0x14002df14  test    eax, eax
0x14002df16  js      loc_14002E333
0x14002df1c  mov     rax, [rbp+160h+EcpContext]
0x14002df20  mov     [rax+8], r12
0x14002df24  cmp     byte ptr [rbp+160h+var_C0+5], 0
0x14002df2b  jnz     short loc_14002DF6A
0x14002df2d  mov     rax, [rbp+160h+EcpContext]
0x14002df31  lea     ecx, [rdi-1]
0x14002df34  or      [rax+2], cx
0x14002df38  mov     rcx, [rbp+160h+EcpContext]
0x14002df3c  mov     rax, qword ptr [rbp+160h+FileInformation+8]
0x14002df43  mov     [rcx+10h], rax
0x14002df47  lea     ecx, [rdi+2]
0x14002df4a  mov     rax, [rbp+160h+EcpContext]
0x14002df4e  or      [rax+2], cx
0x14002df52  mov     rax, qword ptr [rbp+160h+FileInformation+8]
0x14002df59  mov     rcx, [rbp+160h+EcpContext]
0x14002df5d  mov     [rcx+18h], rax
0x14002df61  mov     rax, [rbp+160h+EcpContext]
0x14002df65  or      [rax+2], r9w
0x14002df6a  mov     rax, [rbp+160h+EcpContext]
0x14002df6e  lea     r8, [rbp+160h+var_F8]; FileInformation
0x14002df72  mov     rdx, [rbp+160h+FileObject]; FileObject
0x14002df76  mov     ecx, 400h
0x14002df7b  mov     [rsp+260h+OutputBuffer], 0; LengthReturned
0x14002df84  mov     r9d, 28h ; '('; Length
0x14002df8a  mov     [rsp+260h+InputBufferLength], 4; FileInformationClass
0x14002df92  or      [rax+2], cx
0x14002df96  mov     ecx, 200h
0x14002df9b  mov     rax, [rbp+160h+EcpContext]
0x14002df9f  or      [rax+2], cx
0x14002dfa3  mov     rcx, r13; Instance
0x14002dfa6  call    cs:__imp_FltQueryInformationFile
0x14002dfad  nop     dword ptr [rax+rax+00h]
0x14002dfb2  mov     ebx, eax
0x14002dfb4  test    eax, eax
0x14002dfb6  jns     short loc_14002DFE5
0x14002dfb8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002dfbf  jz      loc_14002E333
0x14002dfc5  mov     dword ptr [rsp+260h+LengthReturned], eax
0x14002dfc9  mov     r9d, 9Eh
0x14002dfcf  mov     [rsp+260h+OutputBufferLength], 1995h
0x14002dfd7  mov     r8d, 0Fh
0x14002dfdd  mov     dl, dil
  ... truncated ...
```
