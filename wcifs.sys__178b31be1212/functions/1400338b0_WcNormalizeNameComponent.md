# WcNormalizeNameComponent

- ea: `0x1400338b0`
- end: `0x140033fd2`
- name: `WcNormalizeNameComponent`
- size: `1826`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *FltObject, PFILE_OBJECT FileObject, struct _UNICODE_STRING *, __int64, struct _UNICODE_STRING *, void *, ULONG Length, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001710`
- `0x1400020c4`
- `0x140004b0c`
- `0x140007c60`
- `0x140029658`
- `0x14002ef90`
- `0x1400338b0`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140033991`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140033991`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140033f27`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140033f27`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140033f0e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140033f39`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140033f0e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140033f39`
- `ntoskrnl!ObfDereferenceObject` at `0x140033e9a`
- `ntoskrnl!ObfDereferenceObject` at `0x140033e9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f89`
- `ntoskrnl!ExAcquireFastMutex` at `0x140033f58`
- `ntoskrnl!ExAcquireFastMutex` at `0x140033f58`
- `ntoskrnl!ExReleaseFastMutex` at `0x140033f75`
- `ntoskrnl!ExReleaseFastMutex` at `0x140033f75`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140033ee0`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140033ee0`
- `FLTMGR!FltCreateFileEx2` at `0x140033bdd`
- `FLTMGR!FltCreateFileEx2` at `0x140033dd6`
- `FLTMGR!FltCreateFileEx2` at `0x140033bdd`
- `FLTMGR!FltCreateFileEx2` at `0x140033dd6`
- `FLTMGR!FltQueryDirectoryFile` at `0x140033e22`
- `FLTMGR!FltQueryDirectoryFile` at `0x140033e22`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140033a2d`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140033a2d`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140033b31`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140033b31`
- `FLTMGR!FltClose` at `0x140033e85`
- `FLTMGR!FltClose` at `0x140033e85`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140033aaf`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140033aaf`
- `FLTMGR!FltReleaseContext` at `0x140033eaf`
- `FLTMGR!FltReleaseContext` at `0x140033ec4`
- `FLTMGR!FltReleaseContext` at `0x140033eaf`
- `FLTMGR!FltReleaseContext` at `0x140033ec4`

## pseudocode

```c
__int64 __fastcall WcNormalizeNameComponent(
        struct _FLT_INSTANCE *FltObject,
        PFILE_OBJECT FileObject,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        struct _UNICODE_STRING *a5,
        void *a6,
        ULONG Length,
        char a8)
{
  unsigned __int8 v12; // di
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rax
  __int64 UnionContext; // rax
  __int64 v15; // rbx
  NTSTATUS v16; // eax
  int v17; // edx
  NTSTATUS v18; // edi
  int v19; // r9d
  NTSTATUS v20; // eax
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  PVOID *v23; // rcx
  NTSTATUS v24; // eax
  int v25; // edx
  int SetContextFileObject; // eax
  struct _UNICODE_STRING *v27; // rdi
  int v28; // eax
  int v29; // edx
  NTSTATUS DirectoryFile; // eax
  PVOID i; // rax
  int CleanupCallback; // [rsp+20h] [rbp-E0h]
  char EcpContext; // [rsp+30h] [rbp-D0h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-C8h]
  PFILE_OBJECT FileObjecta; // [rsp+88h] [rbp-78h] BYREF
  PVOID v36; // [rsp+90h] [rbp-70h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-68h] BYREF
  PECP_LIST EcpList; // [rsp+A0h] [rbp-60h] BYREF
  PFLT_CONTEXT Context; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_CONTEXT v40; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v42; // [rsp+E8h] [rbp-18h] BYREF
  PVOID FileInformation; // [rsp+F8h] [rbp-8h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+100h] [rbp+0h] BYREF
  __int64 v45; // [rsp+120h] [rbp+20h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+128h] [rbp+28h] BYREF
  _OWORD v47[3]; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int8 v48; // [rsp+1E8h] [rbp+E8h]

  FileInformation = a6;
  memset(v47, 0, sizeof(v47));
  v36 = 0;
  EcpList = 0;
  FileHandle = 0;
  v42 = 0;
  FileObjecta = 0;
  memset(&ObjectAttributes, 0, 44);
  Context = 0;
  v40 = 0;
  IoStatusBlock = 0;
  if ( Length < 0x10 )
    return 3221225485LL;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v12 = a8 & 1;
  v48 = a8 & 1;
  DriverContext.Size = 40;
  v45 = 1;
  TransactionParameterBlock = IoGetTransactionParameterBlock(FileObject);
  if ( TransactionParameterBlock )
  {
    LODWORD(v42) = -131056;
    *((_QWORD *)&v42 + 1) = TransactionParameterBlock->TransactionObject;
    DriverContext.TxnParameters = (PTXN_PARAMETER_BLOCK)&v42;
  }
  UnionContext = WcpGetUnionContext(0, FltObject, FileObject);
  v15 = UnionContext;
  if ( !UnionContext )
  {
    ObjectAttributes.ObjectName = a3;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = ((v12 ^ 1) << 6) | 0x200;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v18 = FltCreateFileEx2(
            Globals,
            FltObject,
            &FileHandle,
            &FileObjecta,
            0x100001u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0x90u,
            7u,
            1u,
            0x4021u,
            0,
            0,
            0x800u,
            &DriverContext);
    if ( v18 < 0 )
      goto LABEL_38;
    goto LABEL_31;
  }
  LODWORD(v47[1]) = *(_DWORD *)(UnionContext + 36);
  *((_QWORD *)&v47[0] + 1) = v47;
  *(_QWORD *)&v47[0] = v47;
  *(_OWORD *)((char *)&v47[1] + 8) = 0;
  DWORD1(v47[1]) = -2147483644;
  DWORD2(v47[2]) = 48;
  v16 = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
  v18 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(AllocationSize) = v16;
      v19 = 39;
      EcpContext = -24;
LABEL_9:
      LOBYTE(v17) = 2;
LABEL_37:
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v17,
        17,
        v19,
        (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
        EcpContext,
        AllocationSize);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  v20 = FltAllocateExtraCreateParameterFromLookasideList(
          Globals,
          &ECP_TYPE_OPEN_REPARSE_GUID,
          0x10u,
          0,
          0,
          qword_14000E300,
          &v36);
  v18 = v20;
  if ( v20 >= 0 )
  {
    v21 = v36;
    *((_QWORD *)v36 + 1) = v36;
    *v21 = v21;
    v22 = v36;
    v23 = (PVOID *)*((_QWORD *)v36 + 1);
    if ( *v23 != v36 )
      __fastfail(3u);
    *((_QWORD *)&v47[0] + 1) = *((_QWORD *)v36 + 1);
    *(_QWORD *)&v47[0] = v36;
    *v23 = v47;
    v22[1] = v47;
    FltInsertExtraCreateParameter(Globals, EcpList, v36);
    DriverContext.ExtraCreateParameter = EcpList;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = ((v48 ^ 1) << 6) | 0x200;
    ObjectAttributes.ObjectName = a3;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v24 = FltCreateFileEx2(
            Globals,
            FltObject,
            &FileHandle,
            &FileObjecta,
            0x100001u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0x90u,
            7u,
            1u,
            0x4021u,
            0,
            0,
            0x800u,
            &DriverContext);
    v18 = v24;
    if ( v24 < 0 )
    {
      if ( v24 == -1073741191 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v25) = 3;
        WPP_RECORDER_SF_sDdZ(
          wil_details_featureDescriptors_a->DeviceExtension,
          v25,
          17,
          41,
          (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
          41,
          121,
          (__int64)a3);
      }
      goto LABEL_38;
    }
    if ( *(_DWORD *)(v15 + 24) != 2 && (BYTE4(v47[1]) & 1) != 0 )
    {
      SetContextFileObject = WcGetSetContextFileObject(FltObject, FileObjecta, v15, 1, CleanupCallback, &Context, &v40);
      v18 = SetContextFileObject;
      if ( SetContextFileObject >= 0 )
      {
        v27 = a5;
        if ( SetContextFileObject != 260 )
        {
          v28 = WcPartiallyExpandDirectory(0, FltObject, FileObjecta, 0, a5);
          if ( v28 < 0
            && (unsigned int)(v28 + 1073741773) > 1
            && v28 != -1073741766
            && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v29) = 3;
            WPP_RECORDER_SF_sDdZ(
              wil_details_featureDescriptors_a->DeviceExtension,
              v29,
              17,
              42,
              (__int64)WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
              99,
              v28,
              (__int64)a3);
          }
        }
        goto LABEL_32;
      }
      if ( SetContextFileObject != -1073741195 )
        goto LABEL_38;
    }
LABEL_31:
    v27 = a5;
LABEL_32:
    DirectoryFile = FltQueryDirectoryFile(
                      FltObject,
                      FileObjecta,
                      FileInformation,
                      Length,
                      FileNamesInformation,
                      1u,
                      v27,
                      1u,
                      0);
    v18 = DirectoryFile;
    if ( DirectoryFile >= 0
      || !v15
      || *(_DWORD *)(v15 + 24) != 2
      || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      goto LABEL_38;
    }
    LODWORD(AllocationSize) = DirectoryFile;
    v19 = 43;
    EcpContext = -91;
    LOBYTE(v17) = 3;
    goto LABEL_37;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(AllocationSize) = v20;
    v19 = 40;
    EcpContext = -11;
    goto LABEL_9;
  }
LABEL_38:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObjecta )
    ObfDereferenceObject(FileObjecta);
  if ( Context )
    FltReleaseContext(Context);
  if ( v40 )
    FltReleaseContext(v40);
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  if ( v15 && _InterlockedExchangeAdd((volatile signed __int32 *)v15, 0xFFFFFFFF) == 1 )
  {
    for ( i = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(v15 + 64), 1u);
          i;
          i = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(v15 + 64), 0) )
    {
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v15 + 64), i);
    }
    if ( (*(_DWORD *)(v15 + 32) & 1) != 0 )
    {
      ExAcquireFastMutex(&FastMutex);
      --dword_14000E244;
      *(_DWORD *)(v15 + 32) &= ~1u;
      ExReleaseFastMutex(&FastMutex);
    }
    ExFreePoolWithTag((PVOID)v15, 0x63754357u);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400338b0  push    rbp
0x1400338b2  push    rbx
0x1400338b3  push    r12
0x1400338b5  push    r13
0x1400338b7  lea     rbp, [rsp-88h]
0x1400338bf  sub     rsp, 188h
0x1400338c6  mov     rax, cs:__security_cookie
0x1400338cd  xor     rax, rsp
0x1400338d0  mov     [rbp+0A0h+var_38], rax
0x1400338d4  mov     rax, [rbp+0A0h+arg_20]
0x1400338db  xorps   xmm0, xmm0
0x1400338de  mov     r12, rcx
0x1400338e1  mov     [rbp+0A0h+FileName], rax
0x1400338e5  mov     rax, [rbp+0A0h+arg_28]
0x1400338ec  xor     ecx, ecx
0x1400338ee  cmp     [rbp+0A0h+Length], 10h
0x1400338f5  mov     r13, r8
0x1400338f8  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x1400338fc  mov     [rbp+0A0h+FileInformation], rax
0x140033900  mov     rbx, rdx
0x140033903  movups  [rbp+0A0h+var_68], xmm0
0x140033907  mov     [rbp+0A0h+var_110], rcx
0x14003390b  movups  [rbp+0A0h+var_58], xmm0
0x14003390f  mov     [rbp+0A0h+EcpList], rcx
0x140033913  movups  [rbp+0A0h+var_48], xmm0
0x140033917  mov     [rbp+0A0h+FileHandle], rcx
0x14003391b  movups  [rbp+0A0h+var_B8], xmm0
0x14003391f  mov     [rbp+0A0h+FileObject], rcx
0x140033923  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x140033927  mov     [rbp+0A0h+Context], rcx
0x14003392b  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x14003392f  mov     [rbp+0A0h+var_F0], rcx
0x140033933  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x140033937  jnb     short loc_140033943
0x140033939  mov     eax, 0C000000Dh
0x14003393e  jmp     loc_140033FB7
0x140033943  mov     [rsp+1A0h+arg_18], rsi
0x14003394b  mov     eax, 28h ; '('
0x140033950  mov     [rsp+1A0h+var_20], rdi
0x140033958  mov     rcx, rbx; FileObject
0x14003395b  movzx   edi, [rbp+0A0h+arg_38]
0x140033962  movups  xmmword ptr [rbp+0A0h+var_A0.Size], xmm0
0x140033966  and     dil, 1
0x14003396a  mov     [rsp+1A0h+var_28], r14
0x140033972  mov     [rbp+0A0h+arg_38], dil
0x140033979  mov     [rsp+1A0h+var_30], r15
0x140033981  movups  xmmword ptr [rbp+0A0h+var_A0.DeviceObjectHint], xmm0
0x140033985  mov     [rbp+0A0h+var_A0.Size], ax
0x140033989  mov     [rbp+0A0h+var_80], 1
0x140033991  call    cs:__imp_IoGetTransactionParameterBlock
0x140033998  nop     dword ptr [rax+rax+00h]
0x14003399d  mov     ecx, 10h
0x1400339a2  test    rax, rax
0x1400339a5  jz      short loc_1400339C4
0x1400339a7  mov     word ptr [rbp+0A0h+var_B8], cx
0x1400339ab  mov     rax, [rax+8]
0x1400339af  mov     qword ptr [rbp+0A0h+var_B8+8], rax
0x1400339b3  mov     eax, 0FFFEh
0x1400339b8  mov     word ptr [rbp+0A0h+var_B8+2], ax
0x1400339bc  lea     rax, [rbp+0A0h+var_B8]
0x1400339c0  mov     [rbp+0A0h+var_A0.TxnParameters], rax
0x1400339c4  mov     r9, r13
0x1400339c7  mov     r8, rbx; FileObject
0x1400339ca  mov     rdx, r12; Instance
0x1400339cd  xor     ecx, ecx; CallbackData
0x1400339cf  call    WcpGetUnionContext
0x1400339d4  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400339db  mov     rbx, rax
0x1400339de  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x1400339e5  xorps   xmm0, xmm0
0x1400339e8  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x1400339ef  test    rax, rax
0x1400339f2  jz      loc_140033D43
0x1400339f8  mov     ecx, [rax+24h]
0x1400339fb  lea     r8, [rbp+0A0h+EcpList]; EcpList
0x1400339ff  lea     rax, [rbp+0A0h+var_68]
0x140033a03  mov     dword ptr [rbp+0A0h+var_58], ecx
0x140033a06  mov     rcx, cs:Globals; Filter
0x140033a0d  xor     edx, edx; Flags
0x140033a0f  mov     qword ptr [rbp+0A0h+var_68+8], rax
0x140033a13  lea     rax, [rbp+0A0h+var_68]
0x140033a17  mov     qword ptr [rbp+0A0h+var_68], rax
0x140033a1b  movups  [rbp+0A0h+var_58+8], xmm0
0x140033a1f  mov     dword ptr [rbp+0A0h+var_58+4], 80000004h
0x140033a26  mov     dword ptr [rbp+0A0h+var_48+8], 30h ; '0'
0x140033a2d  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140033a34  nop     dword ptr [rax+rax+00h]
0x140033a39  mov     edi, eax
0x140033a3b  test    eax, eax
0x140033a3d  jns     short loc_140033A7A
0x140033a3f  lea     rsi, WPP_RECORDER_INITIALIZED
0x140033a46  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140033a4d  jz      loc_140033E7C
0x140033a53  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x140033a57  mov     r9d, 27h ; '''
0x140033a5d  mov     dword ptr [rsp+1A0h+EcpContext], 5E8h
0x140033a65  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140033a6c  mov     dl, 2
0x140033a6e  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140033a75  jmp     loc_140033E5C
0x140033a7a  mov     rcx, cs:Globals; Filter
0x140033a81  lea     rax, [rbp+0A0h+var_110]
0x140033a85  mov     [rsp+1A0h+EcpContext], rax; EcpContext
0x140033a8a  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x140033a91  lea     rax, qword_14000E300
0x140033a98  xor     r9d, r9d; Flags
0x140033a9b  mov     [rsp+1A0h+LookasideList], rax; LookasideList
0x140033aa0  mov     r8d, 10h; SizeOfContext
0x140033aa6  mov     [rsp+1A0h+CleanupCallback], 0; CleanupCallback
0x140033aaf  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140033ab6  nop     dword ptr [rax+rax+00h]
0x140033abb  mov     edi, eax
0x140033abd  test    eax, eax
0x140033abf  jns     short loc_140033AEC
0x140033ac1  lea     rsi, WPP_RECORDER_INITIALIZED
0x140033ac8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140033acf  jz      loc_140033E7C
0x140033ad5  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x140033ad9  mov     r9d, 28h ; '('
0x140033adf  mov     dword ptr [rsp+1A0h+EcpContext], 5F5h
0x140033ae7  jmp     loc_140033A65
0x140033aec  mov     rax, [rbp+0A0h+var_110]
0x140033af0  mov     [rax+8], rax
0x140033af4  mov     [rax], rax
0x140033af7  mov     rax, [rbp+0A0h+var_110]
0x140033afb  mov     rcx, [rax+8]
0x140033aff  cmp     [rcx], rax
0x140033b02  jz      short loc_140033B0B
0x140033b04  mov     ecx, 3
0x140033b09  int     29h; Win8: RtlFailFast(ecx)
0x140033b0b  mov     qword ptr [rbp+0A0h+var_68+8], rcx
0x140033b0f  lea     rdx, [rbp+0A0h+var_68]
0x140033b13  mov     qword ptr [rbp+0A0h+var_68], rax
0x140033b17  mov     [rcx], rdx
0x140033b1a  lea     rcx, [rbp+0A0h+var_68]
0x140033b1e  mov     [rax+8], rcx
0x140033b22  mov     r8, [rbp+0A0h+var_110]; EcpContext
0x140033b26  mov     rdx, [rbp+0A0h+EcpList]; EcpList
0x140033b2a  mov     rcx, cs:Globals; Filter
0x140033b31  call    cs:__imp_FltInsertExtraCreateParameter
0x140033b38  nop     dword ptr [rax+rax+00h]
0x140033b3d  mov     rax, [rbp+0A0h+EcpList]
0x140033b41  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x140033b45  mov     [rbp+0A0h+var_A0.ExtraCreateParameter], rax
0x140033b49  lea     r8, [rbp+0A0h+FileHandle]; FileHandle
0x140033b4d  movzx   eax, [rbp+0A0h+arg_38]
0x140033b54  xor     ecx, ecx
0x140033b56  xor     eax, 1
0x140033b59  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rcx
0x140033b5d  shl     eax, 6
0x140033b60  xorps   xmm0, xmm0
0x140033b63  bts     eax, 9
0x140033b67  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x140033b6e  mov     [rbp+0A0h+ObjectAttributes.Attributes], eax
0x140033b71  mov     rdx, r12; Instance
0x140033b74  lea     rax, [rbp+0A0h+var_A0]
0x140033b78  mov     [rbp+0A0h+ObjectAttributes.ObjectName], r13
0x140033b7c  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x140033b81  lea     rax, [rbp+0A0h+IoStatusBlock]
0x140033b85  mov     [rsp+1A0h+Flags], 800h; Flags
0x140033b8d  mov     [rsp+1A0h+EaLength], ecx; EaLength
0x140033b91  mov     [rsp+1A0h+EaBuffer], rcx; EaBuffer
0x140033b96  mov     [rsp+1A0h+CreateOptions], 4021h; CreateOptions
0x140033b9e  mov     [rsp+1A0h+CreateDisposition], 1; CreateDisposition
0x140033ba6  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x140033bae  mov     [rsp+1A0h+FileAttributes], 90h; FileAttributes
0x140033bb6  mov     [rsp+1A0h+AllocationSize], rcx; AllocationSize
0x140033bbb  mov     rcx, cs:Globals; Filter
0x140033bc2  mov     [rsp+1A0h+EcpContext], rax; IoStatusBlock
0x140033bc7  lea     rax, [rbp+0A0h+ObjectAttributes]
0x140033bcb  mov     [rsp+1A0h+LookasideList], rax; ObjectAttributes
0x140033bd0  mov     dword ptr [rsp+1A0h+CleanupCallback], 100001h; int
0x140033bd8  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140033bdd  call    cs:__imp_FltCreateFileEx2
0x140033be4  nop     dword ptr [rax+rax+00h]
0x140033be9  mov     edi, eax
0x140033beb  test    eax, eax
0x140033bed  jns     short loc_140033C5A
0x140033bef  cmp     eax, 0C0000279h
0x140033bf4  jnz     loc_140033E7C
0x140033bfa  lea     rsi, WPP_RECORDER_INITIALIZED
0x140033c01  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140033c08  jz      loc_140033E7C
0x140033c0e  mov     rcx, cs:wil_details_featureDescriptors_a
0x140033c15  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140033c1c  mov     qword ptr [rsp+1A0h+FileAttributes], r13
0x140033c21  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140033c28  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x140033c2c  mov     r9d, 29h ; ')'
0x140033c32  mov     dword ptr [rsp+1A0h+EcpContext], 629h
0x140033c3a  mov     r8d, 11h
0x140033c40  mov     rcx, [rcx+40h]
0x140033c44  mov     dl, 3
0x140033c46  mov     [rsp+1A0h+LookasideList], r14
0x140033c4b  mov     [rsp+1A0h+CleanupCallback], r15
0x140033c50  call    WPP_RECORDER_SF_sDdZ
0x140033c55  jmp     loc_140033E7C
0x140033c5a  cmp     dword ptr [rbx+18h], 2
0x140033c5e  jz      loc_140033DEC
0x140033c64  test    byte ptr [rbp+0A0h+var_58+4], 1
0x140033c68  jz      loc_140033DEC
0x140033c6e  mov     rdx, [rbp+0A0h+FileObject]; FileObject
0x140033c72  lea     rax, [rbp+0A0h+var_F0]
0x140033c76  mov     [rsp+1A0h+EcpContext], rax; __int64
0x140033c7b  mov     r9d, 1
0x140033c81  lea     rax, [rbp+0A0h+Context]
0x140033c85  mov     r8, rbx
0x140033c88  mov     rcx, r12; Instance
0x140033c8b  mov     [rsp+1A0h+LookasideList], rax; __int64
0x140033c90  call    WcGetSetContextFileObject
0x140033c95  mov     edi, eax
0x140033c97  test    eax, eax
0x140033c99  jns     short loc_140033CAB
0x140033c9b  cmp     eax, 0C0000275h
0x140033ca0  jz      loc_140033DEC
0x140033ca6  jmp     loc_140033E7C
0x140033cab  mov     rdi, [rbp+0A0h+FileName]
0x140033caf  cmp     eax, 104h
0x140033cb4  jz      loc_140033DF0
0x140033cba  mov     r9, [rbp+0A0h+FileHandle]
0x140033cbe  mov     rdx, r12; FltObject
0x140033cc1  mov     r8, [rbp+0A0h+FileObject]; Object
0x140033cc5  xor     ecx, ecx; CallbackData
0x140033cc7  mov     [rsp+1A0h+LookasideList], rdi; PUNICODE_STRING
0x140033ccc  mov     byte ptr [rsp+1A0h+CleanupCallback], 0; char
0x140033cd1  call    WcPartiallyExpandDirectory
0x140033cd6  test    eax, eax
0x140033cd8  jns     loc_140033DF0
0x140033cde  lea     ecx, [rax+3FFFFFCDh]
0x140033ce4  cmp     ecx, 1
0x140033ce7  jbe     loc_140033DF0
0x140033ced  cmp     eax, 0C000003Ah
0x140033cf2  jz      loc_140033DF0
0x140033cf8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140033cff  jz      loc_140033DF0
0x140033d05  mov     rcx, cs:wil_details_featureDescriptors_a
0x140033d0c  mov     r9d, 2Ah ; '*'
0x140033d12  mov     qword ptr [rsp+1A0h+FileAttributes], r13
0x140033d17  mov     r8d, 11h
0x140033d1d  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x140033d21  mov     dl, 3
0x140033d23  mov     dword ptr [rsp+1A0h+EcpContext], 663h
0x140033d2b  mov     rcx, [rcx+40h]
0x140033d2f  mov     [rsp+1A0h+LookasideList], r14
0x140033d34  mov     [rsp+1A0h+CleanupCallback], r15
0x140033d39  call    WPP_RECORDER_SF_sDdZ
0x140033d3e  jmp     loc_140033DF0
0x140033d43  xor     ecx, ecx
0x140033d45  mov     [rbp+0A0h+ObjectAttributes.ObjectName], r13
0x140033d49  mov     eax, 30h ; '0'
0x140033d4e  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rcx
0x140033d52  mov     [rbp+0A0h+ObjectAttributes.Length], eax
0x140033d55  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x140033d59  movzx   eax, dil
0x140033d5d  lea     r8, [rbp+0A0h+FileHandle]; FileHandle
0x140033d61  xor     eax, 1
0x140033d64  mov     rdx, r12; Instance
0x140033d67  shl     eax, 6
0x140033d6a  bts     eax, 9
0x140033d6e  mov     [rbp+0A0h+ObjectAttributes.Attributes], eax
0x140033d71  lea     rax, [rbp+0A0h+var_A0]
0x140033d75  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x140033d7a  lea     rax, [rbp+0A0h+IoStatusBlock]
0x140033d7e  mov     [rsp+1A0h+Flags], 800h; Flags
0x140033d86  mov     [rsp+1A0h+EaLength], ecx; EaLength
0x140033d8a  mov     [rsp+1A0h+EaBuffer], rcx; EaBuffer
0x140033d8f  mov     [rsp+1A0h+CreateOptions], 4021h; CreateOptions
0x140033d97  mov     [rsp+1A0h+CreateDisposition], 1; CreateDisposition
0x140033d9f  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x140033da7  mov     [rsp+1A0h+FileAttributes], 90h; FileAttributes
0x140033daf  mov     [rsp+1A0h+AllocationSize], rcx; AllocationSize
0x140033db4  mov     rcx, cs:Globals; Filter
0x140033dbb  mov     [rsp+1A0h+EcpContext], rax; IoStatusBlock
0x140033dc0  lea     rax, [rbp+0A0h+ObjectAttributes]
0x140033dc4  mov     [rsp+1A0h+LookasideList], rax; ObjectAttributes
0x140033dc9  mov     dword ptr [rsp+1A0h+CleanupCallback], 100001h; DesiredAccess
0x140033dd1  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140033dd6  call    cs:__imp_FltCreateFileEx2
0x140033ddd  nop     dword ptr [rax+rax+00h]
0x140033de2  mov     edi, eax
0x140033de4  test    eax, eax
0x140033de6  js      loc_140033E7C
0x140033dec  mov     rdi, [rbp+0A0h+FileName]
0x140033df0  mov     r9d, [rbp+0A0h+Length]; Length
0x140033df7  mov     rcx, r12; Instance
0x140033dfa  mov     r8, [rbp+0A0h+FileInformation]; FileInformation
0x140033dfe  mov     rdx, [rbp+0A0h+FileObject]; FileObject
0x140033e02  mov     qword ptr [rsp+1A0h+FileAttributes], 0; LengthReturned
0x140033e0b  mov     byte ptr [rsp+1A0h+AllocationSize], 1; RestartScan
0x140033e10  mov     [rsp+1A0h+EcpContext], rdi; FileName
0x140033e15  mov     byte ptr [rsp+1A0h+LookasideList], 1; ReturnSingleEntry
0x140033e1a  mov     dword ptr [rsp+1A0h+CleanupCallback], 0Ch; FileInformationClass
0x140033e22  call    cs:__imp_FltQueryDirectoryFile
0x140033e29  nop     dword ptr [rax+rax+00h]
0x140033e2e  mov     edi, eax
0x140033e30  test    eax, eax
0x140033e32  jns     short loc_140033E7C
0x140033e34  test    rbx, rbx
0x140033e37  jz      short loc_140033E7C
0x140033e39  cmp     dword ptr [rbx+18h], 2
  ... truncated ...
```
