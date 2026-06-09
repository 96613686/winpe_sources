# UnionFs::Utils::OpenAsReparsePoint(_FLT_INSTANCE const &,_UNICODE_STRING const &,ulong,UnionFs::Utils::OpenAsReparsePointFlags,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *,void *)

- ea: `0x140072c08`
- end: `0x14007302d`
- name: `?OpenAsReparsePoint@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KW4OpenAsReparsePointFlags@12@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@PEAX@Z`
- size: `1061`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1400628e4`
- `0x14006c1fc`

## callees

- `0x140056a50`
- `0x140056afc`
- `0x140070c88`
- `0x140072c08`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!PsGetHostSilo` at `0x140072e6a`
- `ntoskrnl!PsGetHostSilo` at `0x140072e6a`
- `ntoskrnl!ObfDereferenceObject` at `0x140072c5f`
- `ntoskrnl!ObfDereferenceObject` at `0x140072f63`
- `ntoskrnl!ObfDereferenceObject` at `0x140072c5f`
- `ntoskrnl!ObfDereferenceObject` at `0x140072f63`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140072d26`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140072d26`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140072c7f`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140072c7f`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140073003`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140073003`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140072db3`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140072db3`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140072d57`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140072e05`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140072d57`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140072e05`
- `FLTMGR!FltCreateFileEx2` at `0x140072f3c`
- `FLTMGR!FltCreateFileEx2` at `0x140072f3c`
- `FLTMGR!FltClose` at `0x140072c41`
- `FLTMGR!FltClose` at `0x140072ec6`
- `FLTMGR!FltClose` at `0x140072c41`
- `FLTMGR!FltClose` at `0x140072ec6`

## string_xrefs

- `0x140072c97`: `API: FltAllocateExtraCreateParameterList`
- `0x140072e11`: `PUSH: Preparing QUERY_ON_CREATE ECP`
- `0x140072c9e`: `UnionFs::Utils::OpenAsReparsePoint`
- `0x140072f8e`: `UnionFs::Utils::OpenAsReparsePoint`
- `0x140072fdf`: `UnionFs::Utils::OpenAsReparsePoint`
- `0x140072fce`: `PUSH: Getting QUERY_ON_CREATE info`
- `0x140072f87`: `API: Opening file`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::OpenAsReparsePoint(
        struct _FLT_INSTANCE *a1,
        struct _UNICODE_STRING *a2,
        ACCESS_MASK a3,
        unsigned int a4,
        PVOID a5,
        __int64 a6,
        __int64 *a7,
        void *a8)
{
  char *v8; // rdi
  void *v11; // rcx
  NTSTATUS Parameter; // ebx
  struct _ECP_LIST *v13; // rcx
  char v14; // r14
  struct _ECP_LIST *v15; // r12
  struct _FLT_FILTER *v16; // rcx
  PVOID v17; // rdx
  const char *v18; // rax
  __int64 v19; // r8
  int v20; // edi
  const char *v21; // rax
  __int64 v22; // r8
  int v23; // edx
  __int64 HostSilo; // rax
  void *v25; // rcx
  PFLT_FILTER *v26; // rcx
  PVOID v27; // rcx
  const char *LookasideList; // [rsp+30h] [rbp-D8h]
  const char *LookasideLista; // [rsp+30h] [rbp-D8h]
  const char *LookasideListb; // [rsp+30h] [rbp-D8h]
  PECP_LIST EcpList; // [rsp+88h] [rbp-80h] BYREF
  PVOID *v33; // [rsp+90h] [rbp-78h]
  PVOID EcpContext; // [rsp+98h] [rbp-70h] BYREF
  char v35; // [rsp+A0h] [rbp-68h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v37; // [rsp+C8h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp-8h] BYREF

  v8 = (char *)a5;
  if ( *(_QWORD *)a5 )
    FltClose(*(HANDLE *)a5);
  *(_QWORD *)v8 = 0;
  v11 = (void *)*((_QWORD *)v8 + 1);
  *((_QWORD *)v8 + 1) = 0;
  if ( v11 )
    ObfDereferenceObject(v11);
  EcpList = 0;
  Parameter = FltAllocateExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, 0, &EcpList);
  if ( Parameter >= 0 )
  {
    v13 = EcpList;
    v14 = 0;
    v15 = EcpList;
    if ( (a4 & 6) != 0 )
    {
      a5 = 0;
      EcpContext = 0;
      v33 = &a5;
      v16 = *(struct _FLT_FILTER **)UnionFs::g_FilterState;
      v35 = 1;
      Parameter = FltAllocateExtraCreateParameterFromLookasideList(
                    v16,
                    &GUID_ECP_QUERY_ON_CREATE,
                    0xC8u,
                    0,
                    UnionFs::Utils::QoCEcpCleanupCallback,
                    (char *)UnionFs::g_FilterState + 2240,
                    &EcpContext);
      if ( v35 )
      {
        v17 = *v33;
        *v33 = EcpContext;
        if ( v17 )
          FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, v17);
      }
      if ( Parameter < 0 )
      {
        v18 = "API: Allocating QoC ECP";
        v19 = 0x305002120AALL;
LABEL_19:
        v20 = a6;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)Parameter,
          a6,
          (struct UnionFs::StackEventTracer *)v19,
          (unsigned __int64)"UnionFs::Utils::PrepareQoCEcp",
          v18,
          LookasideLista);
        if ( a5 )
          FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, a5);
        v21 = "PUSH: Preparing QUERY_ON_CREATE ECP";
        v22 = 0x1090021211FLL;
        v23 = v20;
        goto LABEL_38;
      }
      memset(a5, 0, 0xC8u);
      if ( (a4 & 2) != 0 )
        *(_DWORD *)a5 |= 1u;
      if ( (a4 & 4) != 0 )
        *(_DWORD *)a5 |= 4u;
      Parameter = FltInsertExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, v15, a5);
      if ( Parameter < 0 )
      {
        v18 = "API: Inserting QoC ECP";
        v19 = 0x30F002120BELL;
        goto LABEL_19;
      }
      v13 = EcpList;
      v14 = 1;
      a5 = 0;
    }
    *(_DWORD *)(&DriverContext.Size + 1) = 0;
    DriverContext.Size = 40;
    *(&DriverContext.Size + 3) = 0;
    v37 = 1;
    DriverContext.ExtraCreateParameter = v13;
    *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
    if ( a7 )
      HostSilo = *a7;
    else
      HostSilo = PsGetHostSilo(v13, 0);
    v25 = *(void **)v8;
    v37 = HostSilo;
    ObjectAttributes.RootDirectory = a8;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.Attributes + 1, 0, 20);
    ObjectAttributes.ObjectName = a2;
    ObjectAttributes.Attributes = (((a4 & 1) == 0) + 8) << 6;
    v33 = (PVOID *)(v8 + 8);
    EcpContext = 0;
    v35 = 1;
    IoStatusBlock = 0;
    if ( v25 )
      FltClose(v25);
    v26 = (PFLT_FILTER *)UnionFs::g_FilterState;
    *(_QWORD *)v8 = 0;
    Parameter = FltCreateFileEx2(
                  *v26,
                  a1,
                  (PHANDLE)v8,
                  (PFILE_OBJECT *)&EcpContext,
                  a3,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0,
                  7u,
                  1u,
                  0x200028u,
                  0,
                  0,
                  0,
                  &DriverContext);
    if ( v35 )
    {
      v27 = *v33;
      *v33 = EcpContext;
      if ( v27 )
        ObfDereferenceObject(v27);
    }
    if ( Parameter < 0 )
    {
      if ( Parameter != -1073741772 && Parameter != -1073741766 )
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)Parameter,
          a6,
          (struct UnionFs::StackEventTracer *)0x25F00212158LL,
          (unsigned __int64)"UnionFs::Utils::OpenAsReparsePoint",
          "API: Opening file",
          LookasideListb);
      goto LABEL_40;
    }
    if ( !v14 || (Parameter = UnionFs::Utils::MoveQueryOnCreateEcpToResults(a4, EcpList, v8, a6), Parameter >= 0) )
    {
      Parameter = 0;
      goto LABEL_40;
    }
    v23 = a6;
    v21 = "PUSH: Getting QUERY_ON_CREATE info";
    v22 = 0x33F00212167LL;
LABEL_38:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)Parameter,
      v23,
      (struct UnionFs::StackEventTracer *)v22,
      (unsigned __int64)"UnionFs::Utils::OpenAsReparsePoint",
      v21,
      LookasideListb);
LABEL_40:
    FltFreeExtraCreateParameterList(*(PFLT_FILTER *)UnionFs::g_FilterState, v15);
    return (unsigned int)Parameter;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)Parameter,
    a6,
    (struct UnionFs::StackEventTracer *)0x2560021210DLL,
    (unsigned __int64)"UnionFs::Utils::OpenAsReparsePoint",
    "API: FltAllocateExtraCreateParameterList",
    LookasideList);
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x140072c08  mov     rax, rsp
0x140072c0b  mov     [rax+10h], rbx
0x140072c0f  mov     [rax+18h], r8d
0x140072c13  mov     [rax+8], rcx
0x140072c17  push    rbp
0x140072c18  push    rsi
0x140072c19  push    rdi
0x140072c1a  push    r12
0x140072c1c  push    r13
0x140072c1e  push    r14
0x140072c20  push    r15
0x140072c22  lea     rbp, [rax-48h]
0x140072c26  sub     rsp, 110h
0x140072c2d  mov     rdi, [rbp+40h+arg_20]
0x140072c31  xor     ebx, ebx
0x140072c33  mov     esi, r9d
0x140072c36  mov     r13, rdx
0x140072c39  mov     rcx, [rdi]; FileHandle
0x140072c3c  test    rcx, rcx
0x140072c3f  jz      short loc_140072C4D
0x140072c41  call    cs:__imp_FltClose
0x140072c48  nop     dword ptr [rax+rax+00h]
0x140072c4d  lea     r15, [rdi+8]
0x140072c51  mov     [rdi], rbx
0x140072c54  mov     rcx, [r15]; Object
0x140072c57  mov     [r15], rbx
0x140072c5a  test    rcx, rcx
0x140072c5d  jz      short loc_140072C6B
0x140072c5f  call    cs:__imp_ObfDereferenceObject
0x140072c66  nop     dword ptr [rax+rax+00h]
0x140072c6b  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072c72  lea     r8, [rbp+40h+EcpList]; EcpList
0x140072c76  mov     [rbp+40h+EcpList], rbx
0x140072c7a  xor     edx, edx; Flags
0x140072c7c  mov     rcx, [rcx]; Filter
0x140072c7f  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140072c86  nop     dword ptr [rax+rax+00h]
0x140072c8b  xor     edx, edx
0x140072c8d  mov     ebx, eax
0x140072c8f  test    eax, eax
0x140072c91  jns     short loc_140072CC0
0x140072c93  mov     rdx, [rbp+40h+arg_28]; int
0x140072c97  lea     rax, aApiFltallocate; "API: FltAllocateExtraCreateParameterLis"...
0x140072c9e  lea     r9, aUnionfsUtilsOp_1; "UnionFs::Utils::OpenAsReparsePoint"
0x140072ca5  mov     [rsp+140h+CleanupCallback], rax; char *
0x140072caa  mov     r8, 2560021210Dh; struct UnionFs::StackEventTracer *
0x140072cb4  mov     ecx, ebx; this
0x140072cb6  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140072cbb  jmp     loc_14007300F
0x140072cc0  mov     rcx, [rbp+40h+EcpList]
0x140072cc4  mov     r14b, dl
0x140072cc7  mov     r12, rcx
0x140072cca  test    sil, 6
0x140072cce  jz      loc_140072E35
0x140072cd4  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072cdb  lea     rax, [rbp+40h+arg_20]
0x140072cdf  mov     [rbp+40h+arg_20], rdx
0x140072ce3  mov     r14d, 0C8h
0x140072ce9  mov     [rbp+40h+var_B0], rdx
0x140072ced  xor     r9d, r9d; Flags
0x140072cf0  mov     [rbp+40h+var_B8], rax
0x140072cf4  lea     rdx, [rbp+40h+var_B0]
0x140072cf8  lea     rax, [rcx+8C0h]
0x140072cff  mov     [rsp+140h+EcpContext], rdx; EcpContext
0x140072d04  mov     rcx, [rcx]; Filter
0x140072d07  lea     rdx, GUID_ECP_QUERY_ON_CREATE; EcpType
0x140072d0e  mov     [rsp+140h+LookasideList], rax; char *
0x140072d13  mov     r8d, r14d; SizeOfContext
0x140072d16  lea     rax, ?QoCEcpCleanupCallback@Utils@UnionFs@@YAXPEAXPEBU_GUID@@@Z; UnionFs::Utils::QoCEcpCleanupCallback(void *,_GUID const *)
0x140072d1d  mov     [rbp+40h+var_A8], 1
0x140072d21  mov     [rsp+140h+CleanupCallback], rax; CleanupCallback
0x140072d26  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140072d2d  nop     dword ptr [rax+rax+00h]
0x140072d32  cmp     [rbp+40h+var_A8], 0
0x140072d36  mov     ebx, eax
0x140072d38  jz      short loc_140072D63
0x140072d3a  mov     r8, [rbp+40h+var_B8]
0x140072d3e  mov     rcx, [rbp+40h+var_B0]
0x140072d42  mov     rdx, [r8]; EcpContext
0x140072d45  mov     [r8], rcx
0x140072d48  test    rdx, rdx
0x140072d4b  jz      short loc_140072D63
0x140072d4d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072d54  mov     rcx, [rcx]; Filter
0x140072d57  call    cs:__imp_FltFreeExtraCreateParameter
0x140072d5e  nop     dword ptr [rax+rax+00h]
0x140072d63  test    ebx, ebx
0x140072d65  jns     short loc_140072D7A
0x140072d67  lea     rax, aApiAllocatingQ; "API: Allocating QoC ECP"
0x140072d6e  mov     r8, 305002120AAh
0x140072d78  jmp     short loc_140072DD8
0x140072d7a  mov     rcx, [rbp+40h+arg_20]; void *
0x140072d7e  mov     r8, r14; Size
0x140072d81  xor     edx, edx; Val
0x140072d83  call    memset
0x140072d88  test    sil, 2
0x140072d8c  jz      short loc_140072D95
0x140072d8e  mov     rax, [rbp+40h+arg_20]
0x140072d92  or      dword ptr [rax], 1
0x140072d95  test    sil, 4
0x140072d99  jz      short loc_140072DA2
0x140072d9b  mov     rax, [rbp+40h+arg_20]
0x140072d9f  or      dword ptr [rax], 4
0x140072da2  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072da9  mov     rdx, r12; EcpList
0x140072dac  mov     r8, [rbp+40h+arg_20]; EcpContext
0x140072db0  mov     rcx, [rcx]; Filter
0x140072db3  call    cs:__imp_FltInsertExtraCreateParameter
0x140072dba  nop     dword ptr [rax+rax+00h]
0x140072dbf  xor     edx, edx
0x140072dc1  mov     ebx, eax
0x140072dc3  test    eax, eax
0x140072dc5  jns     short loc_140072E2A
0x140072dc7  lea     rax, aApiInsertingQo; "API: Inserting QoC ECP"
0x140072dce  mov     r8, 30F002120BEh; struct UnionFs::StackEventTracer *
0x140072dd8  mov     rdi, [rbp+40h+arg_28]
0x140072ddc  lea     r9, aUnionfsUtilsPr; "UnionFs::Utils::PrepareQoCEcp"
0x140072de3  mov     rdx, rdi; int
0x140072de6  mov     [rsp+140h+CleanupCallback], rax; char *
0x140072deb  mov     ecx, ebx; this
0x140072ded  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140072df2  mov     rdx, [rbp+40h+arg_20]; EcpContext
0x140072df6  test    rdx, rdx
0x140072df9  jz      short loc_140072E11
0x140072dfb  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072e02  mov     rcx, [rcx]; Filter
0x140072e05  call    cs:__imp_FltFreeExtraCreateParameter
0x140072e0c  nop     dword ptr [rax+rax+00h]
0x140072e11  lea     rax, aPushPreparingQ; "PUSH: Preparing QUERY_ON_CREATE ECP"
0x140072e18  mov     r8, 1090021211Fh
0x140072e22  mov     rdx, rdi
0x140072e25  jmp     loc_140072FDF
0x140072e2a  mov     rcx, [rbp+40h+EcpList]
0x140072e2e  mov     r14b, 1
0x140072e31  mov     [rbp+40h+arg_20], rdx
0x140072e35  mov     eax, 28h ; '('
0x140072e3a  mov     dword ptr [rbp+40h+DriverContext+2], edx
0x140072e3d  mov     [rbp+40h+DriverContext.Size], ax
0x140072e41  xorps   xmm0, xmm0
0x140072e44  mov     rax, [rbp+40h+arg_30]
0x140072e4b  mov     word ptr [rbp+40h+DriverContext+6], dx
0x140072e4f  mov     [rbp+40h+var_80], 1
0x140072e57  mov     [rbp+40h+DriverContext.ExtraCreateParameter], rcx
0x140072e5b  movdqu  xmmword ptr [rbp+40h+DriverContext.DeviceObjectHint], xmm0
0x140072e60  test    rax, rax
0x140072e63  jz      short loc_140072E6A
0x140072e65  mov     rax, [rax]
0x140072e68  jmp     short loc_140072E78
0x140072e6a  call    cs:__imp_PsGetHostSilo
0x140072e71  nop     dword ptr [rax+rax+00h]
0x140072e76  xor     edx, edx
0x140072e78  mov     rcx, [rdi]; FileHandle
0x140072e7b  xorps   xmm0, xmm0
0x140072e7e  mov     [rbp+40h+var_80], rax
0x140072e82  mov     rax, [rbp+40h+arg_38]
0x140072e89  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x140072e8d  mov     eax, esi
0x140072e8f  not     eax
0x140072e91  mov     qword ptr [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x140072e99  and     eax, 1
0x140072e9c  mov     dword ptr [rbp+40h+ObjectAttributes+1Ch], edx
0x140072e9f  add     eax, 8
0x140072ea2  mov     [rbp+40h+ObjectAttributes.ObjectName], r13
0x140072ea6  shl     eax, 6
0x140072ea9  mov     [rbp+40h+ObjectAttributes.Attributes], eax
0x140072eac  mov     [rbp+40h+var_B8], r15
0x140072eb0  mov     [rbp+40h+var_B0], rdx
0x140072eb4  mov     [rbp+40h+var_A8], 1
0x140072eb8  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x140072ebd  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x140072ec1  test    rcx, rcx
0x140072ec4  jz      short loc_140072ED4
0x140072ec6  call    cs:__imp_FltClose
0x140072ecd  nop     dword ptr [rax+rax+00h]
0x140072ed2  xor     edx, edx
0x140072ed4  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072edb  lea     rax, [rbp+40h+DriverContext]
0x140072edf  mov     [rsp+78h], rax; DriverContext
0x140072ee4  lea     r9, [rbp+40h+var_B0]; FileObject
0x140072ee8  mov     [rsp+140h+Flags], edx; Flags
0x140072eec  lea     rax, [rbp+40h+IoStatusBlock]
0x140072ef0  mov     [rsp+140h+EaLength], edx; EaLength
0x140072ef4  mov     r8, rdi; FileHandle
0x140072ef7  mov     [rsp+140h+EaBuffer], rdx; EaBuffer
0x140072efc  mov     [rsp+140h+CreateOptions], 200028h; CreateOptions
0x140072f04  mov     [rsp+140h+CreateDisposition], 1; CreateDisposition
0x140072f0c  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x140072f14  mov     [rsp+140h+FileAttributes], edx; FileAttributes
0x140072f18  mov     [rsp+140h+AllocationSize], rdx; AllocationSize
0x140072f1d  mov     [rsp+140h+EcpContext], rax; IoStatusBlock
0x140072f22  lea     rax, [rbp+40h+ObjectAttributes]
0x140072f26  mov     [rsp+140h+LookasideList], rax; char *
0x140072f2b  mov     eax, [rbp+40h+DesiredAccess]
0x140072f2e  mov     [rdi], rdx
0x140072f31  mov     rdx, [rbp+40h+Instance]; Instance
0x140072f35  mov     rcx, [rcx]; Filter
0x140072f38  mov     dword ptr [rsp+140h+CleanupCallback], eax; DesiredAccess
0x140072f3c  call    cs:__imp_FltCreateFileEx2
0x140072f43  nop     dword ptr [rax+rax+00h]
0x140072f48  cmp     [rbp+40h+var_A8], 0
0x140072f4c  mov     ebx, eax
0x140072f4e  jz      short loc_140072F6F
0x140072f50  mov     r8, [rbp+40h+var_B8]
0x140072f54  mov     rdx, [rbp+40h+var_B0]
0x140072f58  mov     rcx, [r8]; Object
0x140072f5b  mov     [r8], rdx
0x140072f5e  test    rcx, rcx
0x140072f61  jz      short loc_140072F6F
0x140072f63  call    cs:__imp_ObfDereferenceObject
0x140072f6a  nop     dword ptr [rax+rax+00h]
0x140072f6f  test    ebx, ebx
0x140072f71  jns     short loc_140072FAD
0x140072f73  cmp     ebx, 0C0000034h
0x140072f79  jz      short loc_140072FF6
0x140072f7b  cmp     ebx, 0C000003Ah
0x140072f81  jz      short loc_140072FF6
0x140072f83  mov     rdx, [rbp+40h+arg_28]; int
0x140072f87  lea     rax, aApiOpeningFile; "API: Opening file"
0x140072f8e  lea     r9, aUnionfsUtilsOp_1; "UnionFs::Utils::OpenAsReparsePoint"
0x140072f95  mov     [rsp+140h+CleanupCallback], rax; char *
0x140072f9a  mov     r8, 25F00212158h; struct UnionFs::StackEventTracer *
0x140072fa4  mov     ecx, ebx; this
0x140072fa6  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140072fab  jmp     short loc_140072FF6
0x140072fad  test    r14b, r14b
0x140072fb0  jz      short loc_140072FF4
0x140072fb2  mov     r9, [rbp+40h+arg_28]
0x140072fb6  mov     r8, rdi
0x140072fb9  mov     rdx, [rbp+40h+EcpList]
0x140072fbd  mov     ecx, esi
0x140072fbf  call    ?MoveQueryOnCreateEcpToResults@Utils@UnionFs@@YAJW4OpenAsReparsePointFlags@12@AEAU_ECP_LIST@@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@@Z; UnionFs::Utils::MoveQueryOnCreateEcpToResults(UnionFs::Utils::OpenAsReparsePointFlags,_ECP_LIST &,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &)
0x140072fc4  mov     ebx, eax
0x140072fc6  test    eax, eax
0x140072fc8  jns     short loc_140072FF4
0x140072fca  mov     rdx, [rbp+40h+arg_28]; int
0x140072fce  lea     rax, aPushGettingQue; "PUSH: Getting QUERY_ON_CREATE info"
0x140072fd5  mov     r8, 33F00212167h; struct UnionFs::StackEventTracer *
0x140072fdf  lea     r9, aUnionfsUtilsOp_1; "UnionFs::Utils::OpenAsReparsePoint"
0x140072fe6  mov     [rsp+140h+CleanupCallback], rax; char *
0x140072feb  mov     ecx, ebx; this
0x140072fed  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140072ff2  jmp     short loc_140072FF6
0x140072ff4  xor     ebx, ebx
0x140072ff6  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140072ffd  mov     rdx, r12; EcpList
0x140073000  mov     rcx, [rcx]; Filter
0x140073003  call    cs:__imp_FltFreeExtraCreateParameterList
0x14007300a  nop     dword ptr [rax+rax+00h]
0x14007300f  mov     eax, ebx
0x140073011  mov     rbx, [rsp+140h+arg_8]
0x140073019  add     rsp, 110h
0x140073020  pop     r15
0x140073022  pop     r14
0x140073024  pop     r13
0x140073026  pop     r12
0x140073028  pop     rdi
0x140073029  pop     rsi
0x14007302a  pop     rbp
0x14007302b  retn
```
