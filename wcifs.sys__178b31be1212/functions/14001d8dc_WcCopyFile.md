# WcCopyFile

- ea: `0x14001d8dc`
- end: `0x14001e020`
- name: `WcCopyFile`
- size: `1860`
- prototype: `__int64 __fastcall(__int64, struct _FILE_OBJECT *, struct _FLT_INSTANCE *, struct _UNICODE_STRING *, struct _FLT_INSTANCE *Instance, void *, __int64, char, char)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001a62c`
- `0x140030da4`

## callees

- `0x1400020c4`
- `0x1400048a4`
- `0x140007c60`
- `0x1400080c0`
- `0x14001d8dc`
- `0x14001e228`
- `0x14001e374`
- `0x14001fa5c`
- `0x140029d84`
- `0x14002f760`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x14001dd72`
- `ntoskrnl!IoGetSilo` at `0x14001dd72`
- `ntoskrnl!ObfDereferenceObject` at `0x14001dfd5`
- `ntoskrnl!ObfDereferenceObject` at `0x14001dfd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001df91`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dfab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dfee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001df91`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dfab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dfee`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001df78`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14001df78`
- `FLTMGR!FltCreateFileEx2` at `0x14001de2c`
- `FLTMGR!FltCreateFileEx2` at `0x14001de2c`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14001db13`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14001db13`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14001dd0d`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14001dd0d`
- `FLTMGR!FltClose` at `0x14001dfc0`
- `FLTMGR!FltClose` at `0x14001dfc0`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001dead`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001dead`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14001db85`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14001db85`
- `FLTMGR!FltQueryInformationFile` at `0x14001d9c4`
- `FLTMGR!FltQueryInformationFile` at `0x14001dc61`
- `FLTMGR!FltQueryInformationFile` at `0x14001d9c4`
- `FLTMGR!FltQueryInformationFile` at `0x14001dc61`

## pseudocode

```c
__int64 __fastcall WcCopyFile(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        struct _FLT_INSTANCE *a3,
        struct _UNICODE_STRING *a4,
        struct _FLT_INSTANCE *Instance,
        void *a6,
        __int64 a7,
        char a8,
        char a9)
{
  void *v10; // rdi
  unsigned __int16 *v11; // r12
  NTSTATUS Ea; // ebx
  ULONG v14; // eax
  int v15; // r8d
  int v16; // r9d
  int v17; // edx
  int ReparseData; // eax
  int v19; // edx
  int v20; // edx
  char EcpContext; // [rsp+30h] [rbp-D0h]
  char AllocationSize; // [rsp+38h] [rbp-C8h]
  PVOID v24; // [rsp+80h] [rbp-80h] BYREF
  __int64 EaLength; // [rsp+88h] [rbp-78h] BYREF
  void *v26; // [rsp+90h] [rbp-70h]
  PECP_LIST EcpList; // [rsp+98h] [rbp-68h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-60h] BYREF
  int v29; // [rsp+A8h] [rbp-58h] BYREF
  ULONG CreateOptions; // [rsp+ACh] [rbp-54h]
  struct _UNICODE_STRING *v31; // [rsp+B0h] [rbp-50h]
  PVOID P; // [rsp+B8h] [rbp-48h]
  void *FileHandle; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v34; // [rsp+C8h] [rbp-38h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+D0h] [rbp-30h] BYREF
  __int64 Silo; // [rsp+F0h] [rbp-10h]
  __int64 v37; // [rsp+F8h] [rbp-8h]
  void *v38; // [rsp+100h] [rbp+0h]
  __int64 v39; // [rsp+108h] [rbp+8h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+110h] [rbp+10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+140h] [rbp+40h] BYREF
  __int128 v42; // [rsp+150h] [rbp+50h] BYREF
  __int128 v43; // [rsp+160h] [rbp+60h]
  __int64 v44; // [rsp+170h] [rbp+70h]
  __int128 v45; // [rsp+178h] [rbp+78h] BYREF
  __int128 v46; // [rsp+188h] [rbp+88h]
  __int128 FileInformation; // [rsp+198h] [rbp+98h] BYREF
  __int64 v48; // [rsp+1A8h] [rbp+A8h]

  v39 = a1;
  v38 = a6;
  v10 = 0;
  v37 = a7;
  v11 = 0;
  v31 = a4;
  P = 0;
  v26 = 0;
  v29 = 0;
  FileHandle = 0;
  FileObject = 0;
  v34 = 0;
  EaLength = 0;
  EcpList = 0;
  v24 = 0;
  LOWORD(Silo) = 0;
  v48 = 0;
  v44 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  FileInformation = 0;
  v45 = 0;
  v46 = 0;
  v42 = 0;
  v43 = 0;
  Ea = FltQueryInformationFile(a3, a2, &FileInformation, 0x18u, FileStandardInformation, 0);
  if ( Ea < 0 )
    goto LABEL_46;
  v14 = 2162728;
  if ( BYTE5(v48) )
    v14 = 2162729;
  CreateOptions = v14;
  Ea = WcQueryEa(a3, a2);
  if ( Ea < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    AllocationSize = Ea;
    v15 = 15;
    EcpContext = -28;
    v16 = 165;
    goto LABEL_7;
  }
  if ( (a9 & 0x40) == 0 )
  {
    Ea = WcQuerySecurity(a3, a2, 0x1Eu, (__int64)&v29);
    if ( Ea < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          2,
          15,
          166,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          241,
          Ea);
      goto LABEL_46;
    }
    v10 = v26;
  }
  Ea = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
  if ( Ea < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    AllocationSize = Ea;
    v16 = 167;
    EcpContext = -1;
    goto LABEL_18;
  }
  Ea = FltAllocateExtraCreateParameterFromLookasideList(
         Globals,
         &GUID_ECP_ATOMIC_CREATE,
         0x58u,
         0,
         0,
         qword_14000E280,
         &v24);
  if ( Ea < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    AllocationSize = Ea;
    v16 = 168;
    EcpContext = 12;
LABEL_18:
    v15 = 5;
LABEL_7:
    v17 = 2;
LABEL_8:
    WPP_RECORDER_SF_sDd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v17,
      v15,
      v16,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      EcpContext,
      AllocationSize);
    goto LABEL_46;
  }
  memset(v24, 0, 0x58u);
  *(_DWORD *)v24 = 88;
  *((_WORD *)v24 + 2) = 0;
  ReparseData = WcGetReparseData(a3, a2, 512, &v34, (ULONG *)&EaLength);
  v11 = v34;
  Ea = ReparseData;
  if ( ReparseData >= 0 )
  {
    *((_WORD *)v24 + 1) |= 2u;
    *((_WORD *)v24 + 3) = EaLength;
    *((_QWORD *)v24 + 1) = v11;
  }
  else if ( ReparseData != -1073741195 )
  {
    goto LABEL_46;
  }
  Ea = FltQueryInformationFile(a3, a2, &v42, 0x28u, FileBasicInformation, 0);
  if ( Ea < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    AllocationSize = Ea;
    v16 = 169;
    EcpContext = 52;
    goto LABEL_29;
  }
  v45 = v42;
  v46 = v43;
  *((_QWORD *)v24 + 4) = &v45;
  *((_WORD *)v24 + 1) |= 0x10u;
  *((_WORD *)v24 + 1) |= 0x400u;
  *((_WORD *)v24 + 1) |= 0x200u;
  Ea = FltInsertExtraCreateParameter(Globals, EcpList, v24);
  if ( Ea < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    AllocationSize = Ea;
    v16 = 170;
    EcpContext = 74;
    goto LABEL_29;
  }
  Silo = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  if ( v37 )
    Silo = IoGetSilo(v37);
  DriverContext.ExtraCreateParameter = EcpList;
  ObjectAttributes.RootDirectory = v38;
  ObjectAttributes.ObjectName = v31;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v10;
  ObjectAttributes.SecurityQualityOfService = 0;
  Ea = FltCreateFileEx2(
         Globals,
         Instance,
         &FileHandle,
         &FileObject,
         0x40040000u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         v44 & 0xFFFFBFFF,
         0,
         2u,
         CreateOptions,
         P,
         HIDWORD(EaLength),
         0,
         &DriverContext);
  if ( Ea >= 0 )
  {
    if ( FltIsEcpAcknowledged(Globals, v24) )
    {
      if ( (v44 & 0x800) == 0 || (Ea = WcCopyFileCompression(a2, a3, FileObject, Instance), Ea >= 0) )
      {
        Ea = WcCopyFileMetaData(v39, a2, a3, FileHandle, FileObject, Instance, a8 != 0 ? 3 : 1);
        goto LABEL_46;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_46;
      AllocationSize = Ea;
      v16 = 173;
      EcpContext = -100;
LABEL_29:
      v15 = 15;
      LOBYTE(v17) = 2;
      goto LABEL_8;
    }
    Ea = -1073741637;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v20) = 2;
      WPP_RECORDER_SF_sDZd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v20,
        10,
        172,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        134,
        (__int64)v31,
        187);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 3;
    WPP_RECORDER_SF_sDZd(
      wil_details_featureDescriptors_a->DeviceExtension,
      v19,
      10,
      171,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      120,
      (__int64)v31,
      Ea);
  }
LABEL_46:
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  if ( P )
    ExFreePoolWithTag(P, 0x65664357u);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v11 )
    ExFreePoolWithTag(v11, 0x69724357u);
  return (unsigned int)Ea;
}

```

## disassembly

```asm
0x14001d8dc  push    rbp
0x14001d8de  push    rbx
0x14001d8df  push    rsi
0x14001d8e0  push    rdi
0x14001d8e1  push    r12
0x14001d8e3  push    r13
0x14001d8e5  push    r14
0x14001d8e7  push    r15
0x14001d8e9  lea     rbp, [rsp-0C8h]
0x14001d8f1  sub     rsp, 1C8h
0x14001d8f8  mov     rax, cs:__security_cookie
0x14001d8ff  xor     rax, rsp
0x14001d902  mov     [rbp+100h+var_50], rax
0x14001d909  mov     rax, [rbp+100h+arg_28]
0x14001d910  xorps   xmm0, xmm0
0x14001d913  mov     r13, [rbp+100h+Instance]
0x14001d91a  mov     r14, r8
0x14001d91d  mov     [rbp+100h+var_F8], rcx
0x14001d921  lea     r8, [rbp+100h+FileInformation]; FileInformation
0x14001d928  xor     ecx, ecx
0x14001d92a  mov     [rbp+100h+var_100], rax
0x14001d92e  mov     rax, [rbp+100h+arg_30]
0x14001d935  xorps   xmm1, xmm1
0x14001d938  mov     [rsp+200h+LengthReturned], rcx; LengthReturned
0x14001d93d  mov     edi, ecx
0x14001d93f  mov     [rbp+100h+var_108], rax
0x14001d943  mov     r12d, ecx
0x14001d946  xor     eax, eax
0x14001d948  mov     [rbp+100h+var_150], r9
0x14001d94c  lea     r9d, [rcx+18h]; Length
0x14001d950  mov     [rbp+100h+P], rcx
0x14001d954  mov     dword ptr [rbp+100h+var_178+4], ecx
0x14001d957  mov     rsi, rdx
0x14001d95a  mov     [rbp+100h+var_170], rcx
0x14001d95e  mov     dword ptr [rbp+100h+var_158], ecx
0x14001d961  mov     [rbp+100h+FileHandle], rcx
0x14001d965  mov     [rbp+100h+FileObject], rcx
0x14001d969  mov     [rbp+100h+var_138], rcx
0x14001d96d  mov     dword ptr [rbp+100h+var_178], ecx
0x14001d970  mov     [rbp+100h+EcpList], rcx
0x14001d974  mov     [rbp+100h+var_180], rcx
0x14001d978  mov     rcx, r14; Instance
0x14001d97b  movups  xmmword ptr [rbp+100h+ObjectAttributes.ObjectName], xmm0
0x14001d97f  mov     word ptr [rbp+100h+var_110], ax
0x14001d983  mov     [rbp+100h+var_58], rax
0x14001d98a  mov     [rbp+100h+var_90], rax
0x14001d98e  movups  xmmword ptr [rbp+100h+ObjectAttributes.Length], xmm0
0x14001d992  mov     [rsp+200h+FileInformationClass], 5; FileInformationClass
0x14001d99a  movups  xmmword ptr [rbp+100h+ObjectAttributes+1Ch], xmm0
0x14001d99e  movups  xmmword ptr [rbp+100h+IoStatusBlock], xmm0
0x14001d9a2  movups  xmmword ptr [rbp+100h+var_130.Size], xmm0
0x14001d9a6  movups  xmmword ptr [rbp+100h+var_130.DeviceObjectHint], xmm0
0x14001d9aa  movups  [rbp+100h+FileInformation], xmm0
0x14001d9b1  movups  [rbp+100h+var_88], xmm0
0x14001d9b5  movups  [rbp+100h+var_78], xmm0
0x14001d9bc  movups  [rbp+100h+var_B0], xmm1
0x14001d9c0  movups  [rbp+100h+var_A0], xmm1
0x14001d9c4  call    cs:__imp_FltQueryInformationFile
0x14001d9cb  nop     dword ptr [rax+rax+00h]
0x14001d9d0  mov     ebx, eax
0x14001d9d2  test    eax, eax
0x14001d9d4  js      loc_14001DF68
0x14001d9da  cmp     byte ptr [rbp+100h+var_58+5], dil
0x14001d9e1  lea     r9, [rbp+100h+var_178+4]
0x14001d9e5  mov     eax, 210028h
0x14001d9ea  lea     r8, [rbp+100h+P]
0x14001d9ee  mov     rdx, rsi; FileObject
0x14001d9f1  lea     ecx, [rax+1]
0x14001d9f4  cmovnz  eax, ecx
0x14001d9f7  neg     [rbp+100h+arg_38]
0x14001d9fd  mov     rcx, r14; Instance
0x14001da00  mov     dword ptr [rbp+100h+var_158+4], eax
0x14001da03  sbb     r15d, r15d
0x14001da06  and     r15d, 2
0x14001da0a  inc     r15d
0x14001da0d  call    WcQueryEa
0x14001da12  mov     ebx, eax
0x14001da14  test    eax, eax
0x14001da16  jns     short loc_14001DA75
0x14001da18  lea     rax, WPP_RECORDER_INITIALIZED
0x14001da1f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001da26  jz      loc_14001DF68
0x14001da2c  mov     dword ptr [rsp+200h+AllocationSize], ebx
0x14001da30  lea     r8d, [r12+0Fh]
0x14001da35  mov     dword ptr [rsp+200h+EcpContext], 1AE4h
0x14001da3d  mov     r9d, 0A5h
0x14001da43  mov     edx, 2
0x14001da48  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001da4f  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001da56  mov     [rsp+200h+LengthReturned], rax
0x14001da5b  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001da62  mov     qword ptr [rsp+200h+FileInformationClass], rax
0x14001da67  mov     rcx, [rcx+40h]
0x14001da6b  call    WPP_RECORDER_SF_sDd
0x14001da70  jmp     loc_14001DF68
0x14001da75  test    [rbp+100h+arg_40], 40h
0x14001da7c  jnz     loc_14001DB06
0x14001da82  lea     rax, [rbp+100h+var_158]
0x14001da86  mov     r8d, 1Eh; SecurityInformation
0x14001da8c  lea     r9, [rbp+100h+var_170]
0x14001da90  mov     qword ptr [rsp+200h+FileInformationClass], rax; __int64
0x14001da95  mov     rdx, rsi; FileObject
0x14001da98  mov     rcx, r14; Instance
0x14001da9b  call    WcQuerySecurity
0x14001daa0  mov     ebx, eax
0x14001daa2  test    eax, eax
0x14001daa4  jns     short loc_14001DB02
0x14001daa6  lea     rax, WPP_RECORDER_INITIALIZED
0x14001daad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dab4  jz      short loc_14001DAF9
0x14001dab6  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001dabd  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001dac4  mov     dword ptr [rsp+200h+AllocationSize], ebx
0x14001dac8  mov     edx, 2
0x14001dacd  mov     dword ptr [rsp+200h+EcpContext], 1AF1h
0x14001dad5  mov     r9d, 0A6h
0x14001dadb  mov     [rsp+200h+LengthReturned], rax
0x14001dae0  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001dae7  mov     rcx, [rcx+40h]
0x14001daeb  lea     r8d, [rdx+0Dh]
0x14001daef  mov     qword ptr [rsp+200h+FileInformationClass], rax
0x14001daf4  call    WPP_RECORDER_SF_sDd
0x14001daf9  mov     rdi, [rbp+100h+var_170]
0x14001dafd  jmp     loc_14001DF68
0x14001db02  mov     rdi, [rbp+100h+var_170]
0x14001db06  mov     rcx, cs:Globals; Filter
0x14001db0d  lea     r8, [rbp+100h+EcpList]; EcpList
0x14001db11  xor     edx, edx; Flags
0x14001db13  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14001db1a  nop     dword ptr [rax+rax+00h]
0x14001db1f  mov     ebx, eax
0x14001db21  test    eax, eax
0x14001db23  jns     short loc_14001DB56
0x14001db25  lea     rax, WPP_RECORDER_INITIALIZED
0x14001db2c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001db33  jz      loc_14001DF68
0x14001db39  mov     dword ptr [rsp+200h+AllocationSize], ebx
0x14001db3d  mov     r9d, 0A7h
0x14001db43  mov     dword ptr [rsp+200h+EcpContext], 1AFFh
0x14001db4b  mov     r8d, 5
0x14001db51  jmp     loc_14001DA43
0x14001db56  mov     rcx, cs:Globals; Filter
0x14001db5d  lea     rax, [rbp+100h+var_180]
0x14001db61  mov     [rsp+200h+EcpContext], rax; EcpContext
0x14001db66  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x14001db6d  xor     r9d, r9d; Flags
0x14001db70  lea     rax, qword_14000E280
0x14001db77  mov     [rsp+200h+LengthReturned], rax; LookasideList
0x14001db7c  mov     qword ptr [rsp+200h+FileInformationClass], r12; CleanupCallback
0x14001db81  lea     r8d, [r9+58h]; SizeOfContext
0x14001db85  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14001db8c  nop     dword ptr [rax+rax+00h]
0x14001db91  mov     ebx, eax
0x14001db93  test    eax, eax
0x14001db95  jns     short loc_14001DBBF
0x14001db97  lea     rax, WPP_RECORDER_INITIALIZED
0x14001db9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dba5  jz      loc_14001DF68
0x14001dbab  mov     dword ptr [rsp+200h+AllocationSize], ebx
0x14001dbaf  mov     r9d, 0A8h
0x14001dbb5  mov     dword ptr [rsp+200h+EcpContext], 1B0Ch
0x14001dbbd  jmp     short loc_14001DB4B
0x14001dbbf  mov     rcx, [rbp+100h+var_180]; void *
0x14001dbc3  mov     ebx, 58h ; 'X'
0x14001dbc8  mov     r8d, ebx; Size
0x14001dbcb  xor     edx, edx; Val
0x14001dbcd  call    memset
0x14001dbd2  mov     rax, [rbp+100h+var_180]
0x14001dbd6  lea     r9, [rbp+100h+var_138]
0x14001dbda  xor     ecx, ecx
0x14001dbdc  mov     r8d, 200h
0x14001dbe2  mov     rdx, rsi; FileObject
0x14001dbe5  mov     [rax], bx
0x14001dbe8  mov     rax, [rbp+100h+var_180]
0x14001dbec  mov     [rax+2], cx
0x14001dbf0  mov     rax, [rbp+100h+var_180]
0x14001dbf4  mov     [rax+4], cx
0x14001dbf8  lea     rax, [rbp+100h+var_178]
0x14001dbfc  mov     rcx, r14; Instance
0x14001dbff  mov     qword ptr [rsp+200h+FileInformationClass], rax; __int64
0x14001dc04  call    WcGetReparseData
0x14001dc09  mov     r12, [rbp+100h+var_138]
0x14001dc0d  mov     ebx, eax
0x14001dc0f  test    eax, eax
0x14001dc11  jns     short loc_14001DC1F
0x14001dc13  cmp     eax, 0C0000275h
0x14001dc18  jz      short loc_14001DC40
0x14001dc1a  jmp     loc_14001DF68
0x14001dc1f  mov     rax, [rbp+100h+var_180]
0x14001dc23  mov     ecx, 2
0x14001dc28  or      [rax+2], cx
0x14001dc2c  mov     rax, [rbp+100h+var_180]
0x14001dc30  movzx   ecx, word ptr [rbp+100h+var_178]
0x14001dc34  mov     [rax+6], cx
0x14001dc38  mov     rax, [rbp+100h+var_180]
0x14001dc3c  mov     [rax+8], r12
0x14001dc40  mov     [rsp+200h+LengthReturned], 0; LengthReturned
0x14001dc49  lea     r8, [rbp+100h+var_B0]; FileInformation
0x14001dc4d  mov     r9d, 28h ; '('; Length
0x14001dc53  mov     [rsp+200h+FileInformationClass], 4; FileInformationClass
0x14001dc5b  mov     rdx, rsi; FileObject
0x14001dc5e  mov     rcx, r14; Instance
0x14001dc61  call    cs:__imp_FltQueryInformationFile
0x14001dc68  nop     dword ptr [rax+rax+00h]
0x14001dc6d  mov     ebx, eax
0x14001dc6f  test    eax, eax
0x14001dc71  jns     short loc_14001DCA6
0x14001dc73  lea     rax, WPP_RECORDER_INITIALIZED
0x14001dc7a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dc81  jz      loc_14001DF68
0x14001dc87  mov     dword ptr [rsp+200h+AllocationSize], ebx
0x14001dc8b  mov     r9d, 0A9h
0x14001dc91  mov     dword ptr [rsp+200h+EcpContext], 1B34h
0x14001dc99  mov     r8d, 0Fh
0x14001dc9f  mov     dl, 2
0x14001dca1  jmp     loc_14001DA48
0x14001dca6  mov     rax, qword ptr [rbp+100h+var_A0+8]
0x14001dcaa  lea     rcx, [rbp+100h+var_88]
0x14001dcae  mov     qword ptr [rbp+100h+var_78+8], rax
0x14001dcb5  mov     rax, qword ptr [rbp+100h+var_B0]
0x14001dcb9  mov     qword ptr [rbp+100h+var_88], rax
0x14001dcbd  mov     rax, qword ptr [rbp+100h+var_B0+8]
0x14001dcc1  mov     qword ptr [rbp+100h+var_88+8], rax
0x14001dcc8  mov     rax, qword ptr [rbp+100h+var_A0]
0x14001dccc  mov     qword ptr [rbp+100h+var_78], rax
0x14001dcd3  mov     rax, [rbp+100h+var_180]
0x14001dcd7  mov     [rax+20h], rcx
0x14001dcdb  mov     ecx, 400h
0x14001dce0  mov     rax, [rbp+100h+var_180]
0x14001dce4  or      word ptr [rax+2], 10h
0x14001dce9  mov     rax, [rbp+100h+var_180]
0x14001dced  or      [rax+2], cx
0x14001dcf1  mov     ecx, 200h
0x14001dcf6  mov     rax, [rbp+100h+var_180]
0x14001dcfa  or      [rax+2], cx
0x14001dcfe  mov     r8, [rbp+100h+var_180]; EcpContext
0x14001dd02  mov     rdx, [rbp+100h+EcpList]; EcpList
0x14001dd06  mov     rcx, cs:Globals; Filter
0x14001dd0d  call    cs:__imp_FltInsertExtraCreateParameter
0x14001dd14  nop     dword ptr [rax+rax+00h]
0x14001dd19  mov     ebx, eax
0x14001dd1b  test    eax, eax
0x14001dd1d  jns     short loc_14001DD4A
0x14001dd1f  lea     rax, WPP_RECORDER_INITIALIZED
0x14001dd26  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dd2d  jz      loc_14001DF68
0x14001dd33  mov     dword ptr [rsp+200h+AllocationSize], ebx
0x14001dd37  mov     r9d, 0AAh
0x14001dd3d  mov     dword ptr [rsp+200h+EcpContext], 1B4Ah
0x14001dd45  jmp     loc_14001DC99
0x14001dd4a  xorps   xmm0, xmm0
0x14001dd4d  mov     [rbp+100h+var_110], 1
0x14001dd55  mov     eax, 28h ; '('
0x14001dd5a  movups  xmmword ptr [rbp+100h+var_130.Size], xmm0
0x14001dd5e  mov     [rbp+100h+var_130.Size], ax
0x14001dd62  mov     rax, [rbp+100h+var_108]
0x14001dd66  movups  xmmword ptr [rbp+100h+var_130.DeviceObjectHint], xmm0
0x14001dd6a  test    rax, rax
0x14001dd6d  jz      short loc_14001DD82
0x14001dd6f  mov     rcx, rax
0x14001dd72  call    cs:__imp_IoGetSilo
0x14001dd79  nop     dword ptr [rax+rax+00h]
0x14001dd7e  mov     [rbp+100h+var_110], rax
0x14001dd82  mov     rax, [rbp+100h+EcpList]
0x14001dd86  lea     r9, [rbp+100h+FileObject]; FileObject
0x14001dd8a  mov     ecx, dword ptr [rbp+100h+var_90]
0x14001dd8d  lea     r8, [rbp+100h+FileHandle]; FileHandle
0x14001dd91  mov     [rbp+100h+var_130.ExtraCreateParameter], rax
0x14001dd95  btr     ecx, 0Eh
0x14001dd99  mov     rax, [rbp+100h+var_100]
0x14001dd9d  mov     rdx, r13; Instance
0x14001dda0  mov     [rbp+100h+ObjectAttributes.RootDirectory], rax
0x14001dda4  mov     rax, [rbp+100h+var_150]
0x14001dda8  mov     [rbp+100h+ObjectAttributes.ObjectName], rax
0x14001ddac  lea     rax, [rbp+100h+var_130]
0x14001ddb0  mov     [rsp+200h+DriverContext], rax; DriverContext
0x14001ddb5  mov     eax, dword ptr [rbp+100h+var_178+4]
0x14001ddb8  mov     [rsp+200h+Flags], 0; Flags
0x14001ddc0  mov     [rsp+200h+EaLength], eax; EaLength
0x14001ddc4  mov     rax, [rbp+100h+P]
0x14001ddc8  mov     [rsp+200h+EaBuffer], rax; EaBuffer
0x14001ddcd  mov     eax, dword ptr [rbp+100h+var_158+4]
0x14001ddd0  mov     [rsp+200h+CreateOptions], eax; CreateOptions
0x14001ddd4  lea     rax, [rbp+100h+IoStatusBlock]
0x14001ddd8  mov     [rsp+200h+CreateDisposition], 2; CreateDisposition
0x14001dde0  mov     [rsp+200h+ShareAccess], 0; ShareAccess
0x14001dde8  mov     [rsp+200h+FileAttributes], ecx; FileAttributes
0x14001ddec  mov     rcx, cs:Globals; Filter
0x14001ddf3  mov     [rsp+200h+AllocationSize], 0; AllocationSize
0x14001ddfc  mov     [rsp+200h+EcpContext], rax; IoStatusBlock
0x14001de01  lea     rax, [rbp+100h+ObjectAttributes]
0x14001de05  mov     [rsp+200h+LengthReturned], rax; ObjectAttributes
0x14001de0a  mov     [rsp+200h+FileInformationClass], 40040000h; DesiredAccess
0x14001de12  mov     [rbp+100h+ObjectAttributes.Length], 30h ; '0'
0x14001de19  mov     [rbp+100h+ObjectAttributes.Attributes], 240h
0x14001de20  mov     [rbp+100h+ObjectAttributes.SecurityDescriptor], rdi
0x14001de24  mov     [rbp+100h+ObjectAttributes.SecurityQualityOfService], 0
0x14001de2c  call    cs:__imp_FltCreateFileEx2
0x14001de33  nop     dword ptr [rax+rax+00h]
0x14001de38  mov     ebx, eax
  ... truncated ...
```
