# WcNormalizeNameComponent

- ea: `0x140033860`
- end: `0x140033f82`
- name: `WcNormalizeNameComponent`
- size: `1826`
- prototype: `__int64 __usercall@<rax>(PVOID FltObject@<rcx>, PFILE_OBJECT FileObject@<rdx>, __int64, __int64, ULONG Length, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001710`
- `0x1400020c4`
- `0x140004b0c`
- `0x140007c60`
- `0x140029608`
- `0x14002ef40`
- `0x140033860`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140033941`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140033941`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140033ed7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140033ed7`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140033ebe`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140033ee9`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140033ebe`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140033ee9`
- `ntoskrnl!ObfDereferenceObject` at `0x140033e4a`
- `ntoskrnl!ObfDereferenceObject` at `0x140033e4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f39`
- `ntoskrnl!ExAcquireFastMutex` at `0x140033f08`
- `ntoskrnl!ExAcquireFastMutex` at `0x140033f08`
- `ntoskrnl!ExReleaseFastMutex` at `0x140033f25`
- `ntoskrnl!ExReleaseFastMutex` at `0x140033f25`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140033e90`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140033e90`
- `FLTMGR!FltCreateFileEx2` at `0x140033b8d`
- `FLTMGR!FltCreateFileEx2` at `0x140033d86`
- `FLTMGR!FltCreateFileEx2` at `0x140033b8d`
- `FLTMGR!FltCreateFileEx2` at `0x140033d86`
- `FLTMGR!FltQueryDirectoryFile` at `0x140033dd2`
- `FLTMGR!FltQueryDirectoryFile` at `0x140033dd2`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400339dd`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400339dd`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140033ae1`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140033ae1`
- `FLTMGR!FltClose` at `0x140033e35`
- `FLTMGR!FltClose` at `0x140033e35`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140033a5f`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140033a5f`
- `FLTMGR!FltReleaseContext` at `0x140033e5f`
- `FLTMGR!FltReleaseContext` at `0x140033e74`
- `FLTMGR!FltReleaseContext` at `0x140033e5f`
- `FLTMGR!FltReleaseContext` at `0x140033e74`

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
  char AllocationSize; // [rsp+38h] [rbp-C8h]
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
      AllocationSize = v16;
      v19 = 39;
      EcpContext = -24;
LABEL_9:
      LOBYTE(v17) = 2;
LABEL_37:
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
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
          WPP_GLOBAL_Control->DeviceExtension,
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
      SetContextFileObject = WcGetSetContextFileObject(
                               FltObject,
                               FileObjecta,
                               CleanupCallback,
                               (__int64)&Context,
                               (__int64)&v40);
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
              WPP_GLOBAL_Control->DeviceExtension,
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
    AllocationSize = DirectoryFile;
    v19 = 43;
    EcpContext = -91;
    LOBYTE(v17) = 3;
    goto LABEL_37;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    AllocationSize = v20;
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
0x140033860  push    rbp
0x140033862  push    rbx
0x140033863  push    r12
0x140033865  push    r13
0x140033867  lea     rbp, [rsp-88h]
0x14003386f  sub     rsp, 188h
0x140033876  mov     rax, cs:__security_cookie
0x14003387d  xor     rax, rsp
0x140033880  mov     [rbp+0A0h+var_38], rax
0x140033884  mov     rax, [rbp+0A0h+arg_20]
0x14003388b  xorps   xmm0, xmm0
0x14003388e  mov     r12, rcx
0x140033891  mov     [rbp+0A0h+FileName], rax
0x140033895  mov     rax, [rbp+0A0h+arg_28]
0x14003389c  xor     ecx, ecx
0x14003389e  cmp     [rbp+0A0h+Length], 10h
0x1400338a5  mov     r13, r8
0x1400338a8  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x1400338ac  mov     [rbp+0A0h+FileInformation], rax
0x1400338b0  mov     rbx, rdx
0x1400338b3  movups  [rbp+0A0h+var_68], xmm0
0x1400338b7  mov     [rbp+0A0h+var_110], rcx
0x1400338bb  movups  [rbp+0A0h+var_58], xmm0
0x1400338bf  mov     [rbp+0A0h+EcpList], rcx
0x1400338c3  movups  [rbp+0A0h+var_48], xmm0
0x1400338c7  mov     [rbp+0A0h+FileHandle], rcx
0x1400338cb  movups  [rbp+0A0h+var_B8], xmm0
0x1400338cf  mov     [rbp+0A0h+FileObject], rcx
0x1400338d3  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x1400338d7  mov     [rbp+0A0h+Context], rcx
0x1400338db  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x1400338df  mov     [rbp+0A0h+var_F0], rcx
0x1400338e3  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x1400338e7  jnb     short loc_1400338F3
0x1400338e9  mov     eax, 0C000000Dh
0x1400338ee  jmp     loc_140033F67
0x1400338f3  mov     [rsp+1A0h+arg_18], rsi
0x1400338fb  mov     eax, 28h ; '('
0x140033900  mov     [rsp+1A0h+var_20], rdi
0x140033908  mov     rcx, rbx; FileObject
0x14003390b  movzx   edi, [rbp+0A0h+arg_38]
0x140033912  movups  xmmword ptr [rbp+0A0h+var_A0.Size], xmm0
0x140033916  and     dil, 1
0x14003391a  mov     [rsp+1A0h+var_28], r14
0x140033922  mov     [rbp+0A0h+arg_38], dil
0x140033929  mov     [rsp+1A0h+var_30], r15
0x140033931  movups  xmmword ptr [rbp+0A0h+var_A0.DeviceObjectHint], xmm0
0x140033935  mov     [rbp+0A0h+var_A0.Size], ax
0x140033939  mov     [rbp+0A0h+var_80], 1
0x140033941  call    cs:__imp_IoGetTransactionParameterBlock
0x140033948  nop     dword ptr [rax+rax+00h]
0x14003394d  mov     ecx, 10h
0x140033952  test    rax, rax
0x140033955  jz      short loc_140033974
0x140033957  mov     word ptr [rbp+0A0h+var_B8], cx
0x14003395b  mov     rax, [rax+8]
0x14003395f  mov     qword ptr [rbp+0A0h+var_B8+8], rax
0x140033963  mov     eax, 0FFFEh
0x140033968  mov     word ptr [rbp+0A0h+var_B8+2], ax
0x14003396c  lea     rax, [rbp+0A0h+var_B8]
0x140033970  mov     [rbp+0A0h+var_A0.TxnParameters], rax
0x140033974  mov     r9, r13
0x140033977  mov     r8, rbx; FileObject
0x14003397a  mov     rdx, r12; Instance
0x14003397d  xor     ecx, ecx; CallbackData
0x14003397f  call    WcpGetUnionContext
0x140033984  lea     rsi, WPP_RECORDER_INITIALIZED
0x14003398b  mov     rbx, rax
0x14003398e  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140033995  xorps   xmm0, xmm0
0x140033998  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x14003399f  test    rax, rax
0x1400339a2  jz      loc_140033CF3
0x1400339a8  mov     ecx, [rax+24h]
0x1400339ab  lea     r8, [rbp+0A0h+EcpList]; EcpList
0x1400339af  lea     rax, [rbp+0A0h+var_68]
0x1400339b3  mov     dword ptr [rbp+0A0h+var_58], ecx
0x1400339b6  mov     rcx, cs:Globals; Filter
0x1400339bd  xor     edx, edx; Flags
0x1400339bf  mov     qword ptr [rbp+0A0h+var_68+8], rax
0x1400339c3  lea     rax, [rbp+0A0h+var_68]
0x1400339c7  mov     qword ptr [rbp+0A0h+var_68], rax
0x1400339cb  movups  [rbp+0A0h+var_58+8], xmm0
0x1400339cf  mov     dword ptr [rbp+0A0h+var_58+4], 80000004h
0x1400339d6  mov     dword ptr [rbp+0A0h+var_48+8], 30h ; '0'
0x1400339dd  call    cs:__imp_FltAllocateExtraCreateParameterList
0x1400339e4  nop     dword ptr [rax+rax+00h]
0x1400339e9  mov     edi, eax
0x1400339eb  test    eax, eax
0x1400339ed  jns     short loc_140033A2A
0x1400339ef  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400339f6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400339fd  jz      loc_140033E2C
0x140033a03  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x140033a07  mov     r9d, 27h ; '''
0x140033a0d  mov     dword ptr [rsp+1A0h+EcpContext], 5E8h
0x140033a15  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140033a1c  mov     dl, 2
0x140033a1e  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140033a25  jmp     loc_140033E0C
0x140033a2a  mov     rcx, cs:Globals; Filter
0x140033a31  lea     rax, [rbp+0A0h+var_110]
0x140033a35  mov     [rsp+1A0h+EcpContext], rax; EcpContext
0x140033a3a  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x140033a41  lea     rax, qword_14000E300
0x140033a48  xor     r9d, r9d; Flags
0x140033a4b  mov     [rsp+1A0h+LookasideList], rax; LookasideList
0x140033a50  mov     r8d, 10h; SizeOfContext
0x140033a56  mov     [rsp+1A0h+CleanupCallback], 0; CleanupCallback
0x140033a5f  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140033a66  nop     dword ptr [rax+rax+00h]
0x140033a6b  mov     edi, eax
0x140033a6d  test    eax, eax
0x140033a6f  jns     short loc_140033A9C
0x140033a71  lea     rsi, WPP_RECORDER_INITIALIZED
0x140033a78  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140033a7f  jz      loc_140033E2C
0x140033a85  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x140033a89  mov     r9d, 28h ; '('
0x140033a8f  mov     dword ptr [rsp+1A0h+EcpContext], 5F5h
0x140033a97  jmp     loc_140033A15
0x140033a9c  mov     rax, [rbp+0A0h+var_110]
0x140033aa0  mov     [rax+8], rax
0x140033aa4  mov     [rax], rax
0x140033aa7  mov     rax, [rbp+0A0h+var_110]
0x140033aab  mov     rcx, [rax+8]
0x140033aaf  cmp     [rcx], rax
0x140033ab2  jz      short loc_140033ABB
0x140033ab4  mov     ecx, 3
0x140033ab9  int     29h; Win8: RtlFailFast(ecx)
0x140033abb  mov     qword ptr [rbp+0A0h+var_68+8], rcx
0x140033abf  lea     rdx, [rbp+0A0h+var_68]
0x140033ac3  mov     qword ptr [rbp+0A0h+var_68], rax
0x140033ac7  mov     [rcx], rdx
0x140033aca  lea     rcx, [rbp+0A0h+var_68]
0x140033ace  mov     [rax+8], rcx
0x140033ad2  mov     r8, [rbp+0A0h+var_110]; EcpContext
0x140033ad6  mov     rdx, [rbp+0A0h+EcpList]; EcpList
0x140033ada  mov     rcx, cs:Globals; Filter
0x140033ae1  call    cs:__imp_FltInsertExtraCreateParameter
0x140033ae8  nop     dword ptr [rax+rax+00h]
0x140033aed  mov     rax, [rbp+0A0h+EcpList]
0x140033af1  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x140033af5  mov     [rbp+0A0h+var_A0.ExtraCreateParameter], rax
0x140033af9  lea     r8, [rbp+0A0h+FileHandle]; FileHandle
0x140033afd  movzx   eax, [rbp+0A0h+arg_38]
0x140033b04  xor     ecx, ecx
0x140033b06  xor     eax, 1
0x140033b09  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rcx
0x140033b0d  shl     eax, 6
0x140033b10  xorps   xmm0, xmm0
0x140033b13  bts     eax, 9
0x140033b17  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x140033b1e  mov     [rbp+0A0h+ObjectAttributes.Attributes], eax
0x140033b21  mov     rdx, r12; Instance
0x140033b24  lea     rax, [rbp+0A0h+var_A0]
0x140033b28  mov     [rbp+0A0h+ObjectAttributes.ObjectName], r13
0x140033b2c  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x140033b31  lea     rax, [rbp+0A0h+IoStatusBlock]
0x140033b35  mov     [rsp+1A0h+Flags], 800h; Flags
0x140033b3d  mov     [rsp+1A0h+EaLength], ecx; EaLength
0x140033b41  mov     [rsp+1A0h+EaBuffer], rcx; EaBuffer
0x140033b46  mov     [rsp+1A0h+CreateOptions], 4021h; CreateOptions
0x140033b4e  mov     [rsp+1A0h+CreateDisposition], 1; CreateDisposition
0x140033b56  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x140033b5e  mov     [rsp+1A0h+FileAttributes], 90h; FileAttributes
0x140033b66  mov     [rsp+1A0h+AllocationSize], rcx; AllocationSize
0x140033b6b  mov     rcx, cs:Globals; Filter
0x140033b72  mov     [rsp+1A0h+EcpContext], rax; IoStatusBlock
0x140033b77  lea     rax, [rbp+0A0h+ObjectAttributes]
0x140033b7b  mov     [rsp+1A0h+LookasideList], rax; ObjectAttributes
0x140033b80  mov     dword ptr [rsp+1A0h+CleanupCallback], 100001h; int
0x140033b88  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140033b8d  call    cs:__imp_FltCreateFileEx2
0x140033b94  nop     dword ptr [rax+rax+00h]
0x140033b99  mov     edi, eax
0x140033b9b  test    eax, eax
0x140033b9d  jns     short loc_140033C0A
0x140033b9f  cmp     eax, 0C0000279h
0x140033ba4  jnz     loc_140033E2C
0x140033baa  lea     rsi, WPP_RECORDER_INITIALIZED
0x140033bb1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140033bb8  jz      loc_140033E2C
0x140033bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140033bc5  lea     r14, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140033bcc  mov     qword ptr [rsp+1A0h+FileAttributes], r13
0x140033bd1  lea     r15, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140033bd8  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x140033bdc  mov     r9d, 29h ; ')'
0x140033be2  mov     dword ptr [rsp+1A0h+EcpContext], 629h
0x140033bea  mov     r8d, 11h
0x140033bf0  mov     rcx, [rcx+40h]
0x140033bf4  mov     dl, 3
0x140033bf6  mov     [rsp+1A0h+LookasideList], r14
0x140033bfb  mov     [rsp+1A0h+CleanupCallback], r15
0x140033c00  call    WPP_RECORDER_SF_sDdZ
0x140033c05  jmp     loc_140033E2C
0x140033c0a  cmp     dword ptr [rbx+18h], 2
0x140033c0e  jz      loc_140033D9C
0x140033c14  test    byte ptr [rbp+0A0h+var_58+4], 1
0x140033c18  jz      loc_140033D9C
0x140033c1e  mov     rdx, [rbp+0A0h+FileObject]; FileObject
0x140033c22  lea     rax, [rbp+0A0h+var_F0]
0x140033c26  mov     [rsp+1A0h+EcpContext], rax; __int64
0x140033c2b  mov     r9d, 1
0x140033c31  lea     rax, [rbp+0A0h+Context]
0x140033c35  mov     r8, rbx
0x140033c38  mov     rcx, r12; Instance
0x140033c3b  mov     [rsp+1A0h+LookasideList], rax; __int64
0x140033c40  call    WcGetSetContextFileObject
0x140033c45  mov     edi, eax
0x140033c47  test    eax, eax
0x140033c49  jns     short loc_140033C5B
0x140033c4b  cmp     eax, 0C0000275h
0x140033c50  jz      loc_140033D9C
0x140033c56  jmp     loc_140033E2C
0x140033c5b  mov     rdi, [rbp+0A0h+FileName]
0x140033c5f  cmp     eax, 104h
0x140033c64  jz      loc_140033DA0
0x140033c6a  mov     r9, [rbp+0A0h+FileHandle]
0x140033c6e  mov     rdx, r12; FltObject
0x140033c71  mov     r8, [rbp+0A0h+FileObject]; Object
0x140033c75  xor     ecx, ecx; CallbackData
0x140033c77  mov     [rsp+1A0h+LookasideList], rdi; PUNICODE_STRING
0x140033c7c  mov     byte ptr [rsp+1A0h+CleanupCallback], 0; char
0x140033c81  call    WcPartiallyExpandDirectory
0x140033c86  test    eax, eax
0x140033c88  jns     loc_140033DA0
0x140033c8e  lea     ecx, [rax+3FFFFFCDh]
0x140033c94  cmp     ecx, 1
0x140033c97  jbe     loc_140033DA0
0x140033c9d  cmp     eax, 0C000003Ah
0x140033ca2  jz      loc_140033DA0
0x140033ca8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140033caf  jz      loc_140033DA0
0x140033cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140033cbc  mov     r9d, 2Ah ; '*'
0x140033cc2  mov     qword ptr [rsp+1A0h+FileAttributes], r13
0x140033cc7  mov     r8d, 11h
0x140033ccd  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x140033cd1  mov     dl, 3
0x140033cd3  mov     dword ptr [rsp+1A0h+EcpContext], 663h
0x140033cdb  mov     rcx, [rcx+40h]
0x140033cdf  mov     [rsp+1A0h+LookasideList], r14
0x140033ce4  mov     [rsp+1A0h+CleanupCallback], r15
0x140033ce9  call    WPP_RECORDER_SF_sDdZ
0x140033cee  jmp     loc_140033DA0
0x140033cf3  xor     ecx, ecx
0x140033cf5  mov     [rbp+0A0h+ObjectAttributes.ObjectName], r13
0x140033cf9  mov     eax, 30h ; '0'
0x140033cfe  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rcx
0x140033d02  mov     [rbp+0A0h+ObjectAttributes.Length], eax
0x140033d05  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x140033d09  movzx   eax, dil
0x140033d0d  lea     r8, [rbp+0A0h+FileHandle]; FileHandle
0x140033d11  xor     eax, 1
0x140033d14  mov     rdx, r12; Instance
0x140033d17  shl     eax, 6
0x140033d1a  bts     eax, 9
0x140033d1e  mov     [rbp+0A0h+ObjectAttributes.Attributes], eax
0x140033d21  lea     rax, [rbp+0A0h+var_A0]
0x140033d25  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x140033d2a  lea     rax, [rbp+0A0h+IoStatusBlock]
0x140033d2e  mov     [rsp+1A0h+Flags], 800h; Flags
0x140033d36  mov     [rsp+1A0h+EaLength], ecx; EaLength
0x140033d3a  mov     [rsp+1A0h+EaBuffer], rcx; EaBuffer
0x140033d3f  mov     [rsp+1A0h+CreateOptions], 4021h; CreateOptions
0x140033d47  mov     [rsp+1A0h+CreateDisposition], 1; CreateDisposition
0x140033d4f  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x140033d57  mov     [rsp+1A0h+FileAttributes], 90h; FileAttributes
0x140033d5f  mov     [rsp+1A0h+AllocationSize], rcx; AllocationSize
0x140033d64  mov     rcx, cs:Globals; Filter
0x140033d6b  mov     [rsp+1A0h+EcpContext], rax; IoStatusBlock
0x140033d70  lea     rax, [rbp+0A0h+ObjectAttributes]
0x140033d74  mov     [rsp+1A0h+LookasideList], rax; ObjectAttributes
0x140033d79  mov     dword ptr [rsp+1A0h+CleanupCallback], 100001h; DesiredAccess
0x140033d81  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140033d86  call    cs:__imp_FltCreateFileEx2
0x140033d8d  nop     dword ptr [rax+rax+00h]
0x140033d92  mov     edi, eax
0x140033d94  test    eax, eax
0x140033d96  js      loc_140033E2C
0x140033d9c  mov     rdi, [rbp+0A0h+FileName]
0x140033da0  mov     r9d, [rbp+0A0h+Length]; Length
0x140033da7  mov     rcx, r12; Instance
0x140033daa  mov     r8, [rbp+0A0h+FileInformation]; FileInformation
0x140033dae  mov     rdx, [rbp+0A0h+FileObject]; FileObject
0x140033db2  mov     qword ptr [rsp+1A0h+FileAttributes], 0; LengthReturned
0x140033dbb  mov     byte ptr [rsp+1A0h+AllocationSize], 1; RestartScan
0x140033dc0  mov     [rsp+1A0h+EcpContext], rdi; FileName
0x140033dc5  mov     byte ptr [rsp+1A0h+LookasideList], 1; ReturnSingleEntry
0x140033dca  mov     dword ptr [rsp+1A0h+CleanupCallback], 0Ch; FileInformationClass
0x140033dd2  call    cs:__imp_FltQueryDirectoryFile
0x140033dd9  nop     dword ptr [rax+rax+00h]
0x140033dde  mov     edi, eax
0x140033de0  test    eax, eax
0x140033de2  jns     short loc_140033E2C
0x140033de4  test    rbx, rbx
0x140033de7  jz      short loc_140033E2C
0x140033de9  cmp     dword ptr [rbx+18h], 2
  ... truncated ...
```
