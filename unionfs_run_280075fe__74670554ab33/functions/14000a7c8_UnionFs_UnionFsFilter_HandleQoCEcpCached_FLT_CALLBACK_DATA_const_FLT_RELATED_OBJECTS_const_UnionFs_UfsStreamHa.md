# UnionFs::UnionFsFilter::HandleQoCEcpCached(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsUnionCtx &,UnionFs::UfsPathCachePayload &,UnionFs::StackEventTracer &)

- ea: `0x14000a7c8`
- end: `0x14000acc0`
- name: `?HandleQoCEcpCached@UnionFsFilter@UnionFs@@AEAAXAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVUfsUnionCtx@2@AEAVUfsPathCachePayload@2@AEAVStackEventTracer@2@@Z`
- size: `1272`
- prototype: `void(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, const struct UnionFs::UfsStreamHandleCtx *, struct UnionFs::UfsUnionCtx *, struct UnionFs::UfsPathCachePayload *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140013bb0`
- `0x1400156a8`

## callees

- `0x14000a7c8`
- `0x14000acc8`
- `0x14000ed54`
- `0x14000f7fc`
- `0x1400567f4`
- `0x140056afc`
- `0x14006f7fc`
- `0x1400787d4`
- `0x140078930`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac6c`
- `ntoskrnl!ExAllocatePool2` at `0x14000ac10`
- `ntoskrnl!ExAllocatePool2` at `0x14000ac10`
- `ntoskrnl!ObfReferenceObject` at `0x14000a85c`
- `ntoskrnl!ObfReferenceObject` at `0x14000aa48`
- `ntoskrnl!ObfReferenceObject` at `0x14000a85c`
- `ntoskrnl!ObfReferenceObject` at `0x14000aa48`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000abdd`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000ac40`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000abdd`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000ac40`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a99f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000aadb`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a99f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000aadb`
- `FLTMGR!FltQueryInformationFile` at `0x14000a8b1`
- `FLTMGR!FltQueryInformationFile` at `0x14000a8b1`
- `FLTMGR!FltAcknowledgeEcp` at `0x14000ac95`
- `FLTMGR!FltAcknowledgeEcp` at `0x14000ac95`

## string_xrefs

- `0x14000a8d1`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000a95c`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000aa02`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000aa94`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000ab37`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000a950`: `PUSH: VirtualizeQoCEcpStatInfo cached`
- `0x14000a9f6`: `PUSH: HandleQoCEcpEaInfo cached`
- `0x14000ab2b`: `PUSH: VirtualizeQoCEcpUsnInfo cached`

## pseudocode

```c
void __fastcall UnionFs::UnionFsFilter::HandleQoCEcpCached(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        const struct UnionFs::UfsStreamHandleCtx *a4,
        struct _FLT_RELATED_OBJECTS *a5,
        PVOID *a6,
        struct UnionFs::StackEventTracer *a7)
{
  struct _FLT_RELATED_OBJECTS *v7; // r15
  const struct _FLT_CALLBACK_DATA *v8; // rsi
  struct _FLT_RELATED_OBJECTS *v9; // r13
  UnionFs::UnionFsFilter *v10; // rcx
  _DWORD *v11; // rbx
  volatile signed __int32 *v12; // rsi
  struct _FILE_OBJECT *v13; // r15
  PFLT_INSTANCE **v14; // r13
  NTSTATUS InformationFile; // eax
  struct UnionFs::UfsUnionCtx *v16; // r8
  UnionFs::Utils *v17; // rcx
  struct _FLT_RELATED_OBJECTS *v18; // rdx
  int v19; // eax
  int v20; // eax
  UnionFs::UnionFsFilter *v21; // rcx
  volatile signed __int32 *v22; // rsi
  struct _FILE_OBJECT *v23; // r15
  const struct _FLT_INSTANCE ***v24; // rdx
  int BackingEAsForQoC; // eax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // r14d
  void *Pool2; // rax
  void *v30; // rdi
  char *LengthReturned; // [rsp+28h] [rbp-89h]
  struct UnionFs::StackEventTracer *LengthReturneda; // [rsp+28h] [rbp-89h]
  const char *LengthReturnedb; // [rsp+28h] [rbp-89h]
  struct _QUERY_ON_CREATE_ECP_CONTEXT *Length; // [rsp+30h] [rbp-81h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+38h] [rbp-79h] BYREF
  struct _FLT_RELATED_OBJECTS *v36; // [rsp+40h] [rbp-71h]
  PVOID EcpContext; // [rsp+48h] [rbp-69h] BYREF
  UnionFs::Utils *v38; // [rsp+50h] [rbp-61h]
  struct _FLT_CALLBACK_DATA *v39; // [rsp+58h] [rbp-59h]
  _OWORD FileInformation[5]; // [rsp+60h] [rbp-51h] BYREF

  v7 = a5;
  v8 = a2;
  v9 = a3;
  v38 = (UnionFs::Utils *)a3;
  v39 = a2;
  ObjectsSecurityDescriptor = a4;
  v36 = a5;
  EcpContext = 0;
  LODWORD(Length) = 0;
  if ( UnionFs::Utils::GetQueryOnCreateEcp(
         a2,
         (const struct _FLT_CALLBACK_DATA *)&EcpContext,
         &Length,
         (unsigned int *)a4) )
  {
    v11 = EcpContext;
    LOBYTE(v10) = 0;
    if ( (*(_DWORD *)EcpContext & 1) == 0 )
      goto LABEL_18;
    if ( (unsigned int)Length < 0x58 )
    {
      *((_DWORD *)EcpContext + 2) |= 1u;
LABEL_17:
      v11[1] |= 1u;
      LOBYTE(v10) = 1;
LABEL_18:
      if ( (*v11 & 4) != 0 )
      {
        if ( (unsigned int)Length >= 0x88 )
        {
          v20 = UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(
                  v10,
                  v8,
                  v9,
                  (struct UnionFs::UfsUnionCtx *)v7,
                  (struct _QUERY_ON_CREATE_ECP_CONTEXT *)v11,
                  a7);
          if ( v20 >= 0 )
          {
            if ( (v11[1] & 4) == 0 )
            {
              ObfReferenceObject(a6[8]);
              v22 = (volatile signed __int32 *)a6[5];
              v23 = (struct _FILE_OBJECT *)a6[8];
              v24 = (const struct _FLT_INSTANCE ***)a6[4];
              if ( v22 )
                _InterlockedIncrement(v22 + 2);
              BackingEAsForQoC = UnionFs::UnionFsFilter::QueryBackingEAsForQoC(
                                   v21,
                                   *v24[1],
                                   v23,
                                   (struct _QUERY_ON_CREATE_ECP_CONTEXT *)v11,
                                   a7);
              if ( BackingEAsForQoC < 0 )
              {
                v11[2] |= 4u;
                UnionFs::ProcessTraceStatusPushLocation(
                  (UnionFs *)(unsigned int)BackingEAsForQoC,
                  (int)a7,
                  (struct UnionFs::StackEventTracer *)0x7BA0001135DLL,
                  (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
                  "PUSH: QueryBackingEAsForQoC",
                  LengthReturned);
                UnionFs::StackEventTracer::LogError(a7);
                *(_DWORD *)a7 = 0;
                *((_WORD *)a7 + 274) = 0;
              }
              if ( v22 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v22);
              if ( v23 )
                ObfDereferenceObject(v23);
            }
          }
          else
          {
            v11[2] |= 4u;
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v20,
              (int)a7,
              (struct UnionFs::StackEventTracer *)0x7BB0001134CLL,
              (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
              "PUSH: HandleQoCEcpEaInfo cached",
              LengthReturned);
            UnionFs::StackEventTracer::LogError(a7);
            *(_DWORD *)a7 = 0;
            *((_WORD *)a7 + 274) = 0;
          }
        }
        else
        {
          v11[2] |= 4u;
        }
        v11[1] |= 4u;
        LOBYTE(v10) = 1;
      }
      if ( (*v11 & 8) != 0 )
      {
        if ( (unsigned int)Length >= 0xB0 )
        {
          v26 = UnionFs::Utils::VirtualizeQoCEcpUsnInfo(
                  (UnionFs::Utils *)v9,
                  v36,
                  (struct UnionFs::UfsUnionCtx *)ObjectsSecurityDescriptor,
                  (const struct UnionFs::UfsStreamHandleCtx *)(v11 + 38),
                  a7,
                  (struct UnionFs::StackEventTracer *)LengthReturned);
          if ( v26 < 0 )
          {
            v11[2] |= 8u;
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v26,
              (int)a7,
              (struct UnionFs::StackEventTracer *)0x7B90001137ALL,
              (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
              "PUSH: VirtualizeQoCEcpUsnInfo cached",
              LengthReturnedb);
            UnionFs::StackEventTracer::LogError(a7);
            *(_DWORD *)a7 = 0;
            *((_WORD *)a7 + 274) = 0;
          }
        }
        else
        {
          v11[2] |= 8u;
        }
        v11[1] |= 8u;
        LOBYTE(v10) = 1;
      }
      v27 = *v11;
      if ( (*v11 & 2) != 0 )
      {
        v11[1] |= 2u;
        LOBYTE(v10) = 1;
        v11[2] |= 2u;
      }
      if ( (v27 & 0x10) == 0 )
      {
        if ( !(_BYTE)v10 )
          return;
        goto LABEL_54;
      }
      if ( (unsigned int)Length >= 0xC8 )
      {
        ObjectsSecurityDescriptor = a6[10];
        if ( !v11[44] )
        {
          v11[3] |= 0x10u;
LABEL_52:
          v11[1] |= 0x10u;
LABEL_54:
          FltAcknowledgeEcp(*(PFLT_FILTER *)UnionFs::g_FilterState, v11);
          return;
        }
        LODWORD(Length) = 0;
        if ( SeQuerySecurityDescriptorInfo(v11 + 44, 0, (PULONG)&Length, &ObjectsSecurityDescriptor) == -1073741789 )
        {
          if ( (_DWORD)Length )
          {
            v28 = (unsigned int)Length;
            Pool2 = (void *)ExAllocatePool2(256, (unsigned int)Length, 1936803413);
            v30 = Pool2;
            if ( Pool2 )
            {
              memset(Pool2, 0, v28);
              if ( SeQuerySecurityDescriptorInfo(v11 + 44, v30, (PULONG)&Length, &ObjectsSecurityDescriptor) < 0 )
              {
                v11[2] |= 0x10u;
                ExFreePoolWithTag(v30, 0);
              }
              else
              {
                *((_QWORD *)v11 + 24) = v30;
                v11[47] = (_DWORD)Length;
              }
              goto LABEL_52;
            }
          }
        }
      }
      v11[2] |= 0x10u;
      goto LABEL_52;
    }
    ObfReferenceObject(a6[8]);
    v12 = (volatile signed __int32 *)a6[5];
    v13 = (struct _FILE_OBJECT *)a6[8];
    v14 = (PFLT_INSTANCE **)a6[4];
    if ( v12 )
      _InterlockedIncrement(v12 + 2);
    memset(FileInformation, 0, 0x48u);
    InformationFile = FltQueryInformationFile(*v14[1], v13, FileInformation, 0x48u, (FILE_INFORMATION_CLASS)68, 0);
    if ( InformationFile >= 0 )
    {
      v9 = (struct _FLT_RELATED_OBJECTS *)v38;
      v16 = (struct UnionFs::UfsUnionCtx *)ObjectsSecurityDescriptor;
      v17 = v38;
      v18 = v36;
      *((_OWORD *)v11 + 1) = FileInformation[0];
      *((_OWORD *)v11 + 2) = FileInformation[1];
      *((_OWORD *)v11 + 3) = FileInformation[2];
      *((_OWORD *)v11 + 4) = FileInformation[3];
      *((_QWORD *)v11 + 10) = *(_QWORD *)&FileInformation[4];
      v19 = UnionFs::Utils::VirtualizeQoCEcpStatInfo(
              v17,
              v18,
              v16,
              (const struct UnionFs::UfsStreamHandleCtx *)(v11 + 4),
              a7,
              LengthReturneda);
      if ( v19 >= 0 )
      {
LABEL_12:
        if ( v12 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v12);
        if ( v13 )
          ObfDereferenceObject(v13);
        v7 = v36;
        v8 = v39;
        goto LABEL_17;
      }
      v11[2] |= 1u;
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v19,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x7BC00011334LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
        "PUSH: VirtualizeQoCEcpStatInfo cached",
        LengthReturned);
      UnionFs::StackEventTracer::LogError(a7);
    }
    else
    {
      v11[2] |= 1u;
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)InformationFile,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x7BD0001131ELL,
        (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
        "PUSH: FltQueryInformationFile for stat QoC",
        (const char *)LengthReturneda);
      UnionFs::StackEventTracer::LogError(a7);
      v9 = (struct _FLT_RELATED_OBJECTS *)v38;
    }
    *((_WORD *)a7 + 274) = 0;
    *(_DWORD *)a7 = 0;
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x14000a7c8  push    rbp
0x14000a7ca  push    rbx
0x14000a7cb  push    rsi
0x14000a7cc  push    rdi
0x14000a7cd  push    r13
0x14000a7cf  push    r14
0x14000a7d1  push    r15
0x14000a7d3  lea     rbp, [rsp-0Fh]
0x14000a7d8  sub     rsp, 0C0h
0x14000a7df  mov     rax, cs:__security_cookie
0x14000a7e6  xor     rax, rsp
0x14000a7e9  mov     [rbp+3Fh+var_40], rax
0x14000a7ed  mov     r15, [rbp+3Fh+arg_20]
0x14000a7f1  mov     rsi, rdx
0x14000a7f4  mov     rdi, [rbp+3Fh+arg_30]
0x14000a7f8  mov     r13, r8
0x14000a7fb  mov     r14, [rbp+3Fh+arg_28]
0x14000a7ff  mov     rcx, rsi; CallbackData
0x14000a802  mov     [rbp+3Fh+var_A0], r8
0x14000a806  lea     r8, [rsp+0F0h+Length]; struct _QUERY_ON_CREATE_ECP_CONTEXT **
0x14000a80b  mov     [rbp+3Fh+var_98], rdx
0x14000a80f  lea     rdx, [rbp+3Fh+EcpContext]; struct _FLT_CALLBACK_DATA *
0x14000a813  mov     [rbp+3Fh+ObjectsSecurityDescriptor], r9
0x14000a817  mov     [rbp+3Fh+var_B0], r15
0x14000a81b  mov     [rbp+3Fh+EcpContext], 0
0x14000a823  mov     dword ptr [rsp+0F0h+Length], 0
0x14000a82b  call    ?GetQueryOnCreateEcp@Utils@UnionFs@@YA_NAEBU_FLT_CALLBACK_DATA@@PEAPEAU_QUERY_ON_CREATE_ECP_CONTEXT@@PEAK@Z; UnionFs::Utils::GetQueryOnCreateEcp(_FLT_CALLBACK_DATA const &,_QUERY_ON_CREATE_ECP_CONTEXT * *,ulong *)
0x14000a830  test    al, al
0x14000a832  jz      loc_14000ACA1
0x14000a838  mov     rbx, [rbp+3Fh+EcpContext]
0x14000a83c  xor     cl, cl
0x14000a83e  mov     eax, [rbx]
0x14000a840  test    al, 1
0x14000a842  jz      loc_14000A9B9
0x14000a848  cmp     dword ptr [rsp+0F0h+Length], 58h ; 'X'
0x14000a84d  jnb     short loc_14000A858
0x14000a84f  or      dword ptr [rbx+8], 1
0x14000a853  jmp     loc_14000A9B3
0x14000a858  mov     rcx, [r14+40h]; Object
0x14000a85c  call    cs:__imp_ObfReferenceObject
0x14000a863  nop     dword ptr [rax+rax+00h]
0x14000a868  mov     rsi, [r14+28h]
0x14000a86c  mov     r15, [r14+40h]
0x14000a870  mov     r13, [r14+20h]
0x14000a874  test    rsi, rsi
0x14000a877  jz      short loc_14000A87D
0x14000a879  lock inc dword ptr [rsi+8]
0x14000a87d  xor     edx, edx; Val
0x14000a87f  lea     rcx, [rbp+3Fh+FileInformation]; void *
0x14000a883  lea     r8d, [rdx+48h]; Size
0x14000a887  call    memset
0x14000a88c  mov     rcx, [r13+8]
0x14000a890  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x14000a894  mov     [rsp+0F0h+LengthReturned], 0; char *
0x14000a89d  mov     r9d, 48h ; 'H'; Length
0x14000a8a3  mov     rdx, r15; FileObject
0x14000a8a6  mov     [rsp+0F0h+FileInformationClass], 44h ; 'D'; FileInformationClass
0x14000a8ae  mov     rcx, [rcx]; Instance
0x14000a8b1  call    cs:__imp_FltQueryInformationFile
0x14000a8b8  nop     dword ptr [rax+rax+00h]
0x14000a8bd  test    eax, eax
0x14000a8bf  jns     short loc_14000A8FD
0x14000a8c1  or      dword ptr [rbx+8], 1
0x14000a8c5  lea     rcx, aPushFltqueryin; "PUSH: FltQueryInformationFile for stat "...
0x14000a8cc  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000a8d1  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000a8d8  mov     ecx, eax; this
0x14000a8da  mov     r8, 7BD0001131Eh; struct UnionFs::StackEventTracer *
0x14000a8e4  mov     rdx, rdi; int
0x14000a8e7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000a8ec  mov     rcx, rdi; this
0x14000a8ef  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000a8f4  mov     r13, [rbp+3Fh+var_A0]
0x14000a8f8  jmp     loc_14000A97F
0x14000a8fd  movaps  xmm0, [rbp+3Fh+FileInformation]
0x14000a901  lea     r9, [rbx+10h]; struct UnionFs::UfsStreamHandleCtx *
0x14000a905  mov     r13, [rbp+3Fh+var_A0]
0x14000a909  mov     r8, [rbp+3Fh+ObjectsSecurityDescriptor]; struct UnionFs::UfsUnionCtx *
0x14000a90d  mov     rcx, r13; this
0x14000a910  mov     rdx, [rbp+3Fh+var_B0]; struct _FLT_RELATED_OBJECTS *
0x14000a914  movups  xmmword ptr [r9], xmm0
0x14000a918  mov     qword ptr [rsp+0F0h+FileInformationClass], rdi; struct _QUERY_ON_CREATE_FILE_STAT_INFORMATION *
0x14000a91d  movaps  xmm1, [rbp+3Fh+var_80]
0x14000a921  movups  xmmword ptr [r9+10h], xmm1
0x14000a926  movaps  xmm0, [rbp+3Fh+var_70]
0x14000a92a  movups  xmmword ptr [r9+20h], xmm0
0x14000a92f  movaps  xmm1, [rbp+3Fh+var_60]
0x14000a933  movups  xmmword ptr [r9+30h], xmm1
0x14000a938  movsd   xmm0, [rbp+3Fh+var_50]
0x14000a93d  movsd   qword ptr [r9+40h], xmm0
0x14000a943  call    ?VirtualizeQoCEcpStatInfo@Utils@UnionFs@@YAJAEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@AEBVUfsStreamHandleCtx@2@AEAU_QUERY_ON_CREATE_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::VirtualizeQoCEcpStatInfo(_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,_QUERY_ON_CREATE_FILE_STAT_INFORMATION &,UnionFs::StackEventTracer &)
0x14000a948  test    eax, eax
0x14000a94a  jns     short loc_14000A98A
0x14000a94c  or      dword ptr [rbx+8], 1
0x14000a950  lea     rcx, aPushVirtualize_0; "PUSH: VirtualizeQoCEcpStatInfo cached"
0x14000a957  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000a95c  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000a963  mov     ecx, eax; this
0x14000a965  mov     r8, 7BC00011334h; struct UnionFs::StackEventTracer *
0x14000a96f  mov     rdx, rdi; int
0x14000a972  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000a977  mov     rcx, rdi; this
0x14000a97a  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000a97f  xor     eax, eax
0x14000a981  mov     [rdi+224h], ax
0x14000a988  mov     [rdi], eax
0x14000a98a  test    rsi, rsi
0x14000a98d  jz      short loc_14000A997
0x14000a98f  mov     rcx, rsi; this
0x14000a992  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14000a997  test    r15, r15
0x14000a99a  jz      short loc_14000A9AB
0x14000a99c  mov     rcx, r15; Object
0x14000a99f  call    cs:__imp_ObfDereferenceObject
0x14000a9a6  nop     dword ptr [rax+rax+00h]
0x14000a9ab  mov     r15, [rbp+3Fh+var_B0]
0x14000a9af  mov     rsi, [rbp+3Fh+var_98]
0x14000a9b3  or      dword ptr [rbx+4], 1
0x14000a9b7  mov     cl, 1; this
0x14000a9b9  mov     eax, [rbx]
0x14000a9bb  test    al, 4
0x14000a9bd  jz      loc_14000AAED
0x14000a9c3  cmp     dword ptr [rsp+0F0h+Length], 88h
0x14000a9cb  jnb     short loc_14000A9D6
0x14000a9cd  or      dword ptr [rbx+8], 4
0x14000a9d1  jmp     loc_14000AAE7
0x14000a9d6  mov     [rsp+0F0h+LengthReturned], rdi; char *
0x14000a9db  mov     r9, r15; struct UnionFs::UfsUnionCtx *
0x14000a9de  mov     r8, r13; struct _FLT_RELATED_OBJECTS *
0x14000a9e1  mov     qword ptr [rsp+0F0h+FileInformationClass], rbx; struct _QUERY_ON_CREATE_ECP_CONTEXT *
0x14000a9e6  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x14000a9e9  call    ?HandleQoCEcpEaInfo@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,_QUERY_ON_CREATE_ECP_CONTEXT *,UnionFs::StackEventTracer &)
0x14000a9ee  test    eax, eax
0x14000a9f0  jns     short loc_14000AA39
0x14000a9f2  or      dword ptr [rbx+8], 4
0x14000a9f6  lea     rcx, aPushHandleqoce; "PUSH: HandleQoCEcpEaInfo cached"
0x14000a9fd  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000aa02  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000aa09  mov     ecx, eax; this
0x14000aa0b  mov     r8, 7BB0001134Ch; struct UnionFs::StackEventTracer *
0x14000aa15  mov     rdx, rdi; int
0x14000aa18  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000aa1d  mov     rcx, rdi; this
0x14000aa20  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000aa25  xor     eax, eax
0x14000aa27  mov     dword ptr [rdi], 0
0x14000aa2d  mov     [rdi+224h], ax
0x14000aa34  jmp     loc_14000AAE7
0x14000aa39  mov     eax, [rbx+4]
0x14000aa3c  test    al, 4
0x14000aa3e  jnz     loc_14000AAE7
0x14000aa44  mov     rcx, [r14+40h]; Object
0x14000aa48  call    cs:__imp_ObfReferenceObject
0x14000aa4f  nop     dword ptr [rax+rax+00h]
0x14000aa54  mov     rsi, [r14+28h]
0x14000aa58  mov     r15, [r14+40h]
0x14000aa5c  mov     rdx, [r14+20h]
0x14000aa60  test    rsi, rsi
0x14000aa63  jz      short loc_14000AA69
0x14000aa65  lock inc dword ptr [rsi+8]
0x14000aa69  mov     rdx, [rdx+8]
0x14000aa6d  mov     r9, rbx; struct _QUERY_ON_CREATE_ECP_CONTEXT *
0x14000aa70  mov     r8, r15; struct _FILE_OBJECT *
0x14000aa73  mov     qword ptr [rsp+0F0h+FileInformationClass], rdi; struct UnionFs::StackEventTracer *
0x14000aa78  mov     rdx, [rdx]; struct _FLT_INSTANCE *
0x14000aa7b  call    ?QueryBackingEAsForQoC@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::QueryBackingEAsForQoC(_FLT_INSTANCE const &,_FILE_OBJECT const &,_QUERY_ON_CREATE_ECP_CONTEXT *,UnionFs::StackEventTracer &)
0x14000aa80  test    eax, eax
0x14000aa82  jns     short loc_14000AAC6
0x14000aa84  or      dword ptr [rbx+8], 4
0x14000aa88  lea     rcx, aPushQuerybacki; "PUSH: QueryBackingEAsForQoC"
0x14000aa8f  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000aa94  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000aa9b  mov     ecx, eax; this
0x14000aa9d  mov     r8, 7BA0001135Dh; struct UnionFs::StackEventTracer *
0x14000aaa7  mov     rdx, rdi; int
0x14000aaaa  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000aaaf  mov     rcx, rdi; this
0x14000aab2  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000aab7  xor     eax, eax
0x14000aab9  mov     dword ptr [rdi], 0
0x14000aabf  mov     [rdi+224h], ax
0x14000aac6  test    rsi, rsi
0x14000aac9  jz      short loc_14000AAD3
0x14000aacb  mov     rcx, rsi; this
0x14000aace  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14000aad3  test    r15, r15
0x14000aad6  jz      short loc_14000AAE7
0x14000aad8  mov     rcx, r15; Object
0x14000aadb  call    cs:__imp_ObfDereferenceObject
0x14000aae2  nop     dword ptr [rax+rax+00h]
0x14000aae7  or      dword ptr [rbx+4], 4
0x14000aaeb  mov     cl, 1
0x14000aaed  mov     eax, [rbx]
0x14000aaef  test    al, 8
0x14000aaf1  jz      loc_14000AB77
0x14000aaf7  cmp     dword ptr [rsp+0F0h+Length], 0B0h
0x14000aaff  jnb     short loc_14000AB07
0x14000ab01  or      dword ptr [rbx+8], 8
0x14000ab05  jmp     short loc_14000AB69
0x14000ab07  mov     r8, [rbp+3Fh+ObjectsSecurityDescriptor]; struct UnionFs::UfsUnionCtx *
0x14000ab0b  lea     r9, [rbx+98h]; struct UnionFs::UfsStreamHandleCtx *
0x14000ab12  mov     rdx, [rbp+3Fh+var_B0]; struct _FLT_RELATED_OBJECTS *
0x14000ab16  mov     rcx, r13; this
0x14000ab19  mov     qword ptr [rsp+0F0h+FileInformationClass], rdi; struct _QUERY_ON_CREATE_USN_INFORMATION *
0x14000ab1e  call    ?VirtualizeQoCEcpUsnInfo@Utils@UnionFs@@YAJAEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@AEBVUfsStreamHandleCtx@2@AEAU_QUERY_ON_CREATE_USN_INFORMATION@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::VirtualizeQoCEcpUsnInfo(_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,_QUERY_ON_CREATE_USN_INFORMATION &,UnionFs::StackEventTracer &)
0x14000ab23  test    eax, eax
0x14000ab25  jns     short loc_14000AB69
0x14000ab27  or      dword ptr [rbx+8], 8
0x14000ab2b  lea     rcx, aPushVirtualize_1; "PUSH: VirtualizeQoCEcpUsnInfo cached"
0x14000ab32  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000ab37  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000ab3e  mov     ecx, eax; this
0x14000ab40  mov     r8, 7B90001137Ah; struct UnionFs::StackEventTracer *
0x14000ab4a  mov     rdx, rdi; int
0x14000ab4d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000ab52  mov     rcx, rdi; this
0x14000ab55  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000ab5a  xor     eax, eax
0x14000ab5c  mov     dword ptr [rdi], 0
0x14000ab62  mov     [rdi+224h], ax
0x14000ab69  or      dword ptr [rbx+4], 8
0x14000ab6d  mov     edi, 1
0x14000ab72  mov     cl, dil
0x14000ab75  jmp     short loc_14000AB7C
0x14000ab77  mov     edi, 1
0x14000ab7c  mov     eax, [rbx]
0x14000ab7e  test    al, 2
0x14000ab80  jz      short loc_14000AB8D
0x14000ab82  or      dword ptr [rbx+4], 2
0x14000ab86  mov     cl, dil
0x14000ab89  or      dword ptr [rbx+8], 2
0x14000ab8d  mov     r15d, 10h
0x14000ab93  test    r15b, al
0x14000ab96  jz      loc_14000AC84
0x14000ab9c  cmp     dword ptr [rsp+0F0h+Length], 0C8h
0x14000aba4  jb      loc_14000AC7A
0x14000abaa  mov     rax, [r14+50h]
0x14000abae  lea     rsi, [rbx+0B0h]
0x14000abb5  mov     [rbp+3Fh+ObjectsSecurityDescriptor], rax
0x14000abb9  cmp     dword ptr [rsi], 0
0x14000abbc  jnz     short loc_14000ABC7
0x14000abbe  or      [rbx+0Ch], r15d
0x14000abc2  jmp     loc_14000AC7E
0x14000abc7  lea     r9, [rbp+3Fh+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x14000abcb  mov     dword ptr [rsp+0F0h+Length], 0
0x14000abd3  lea     r8, [rsp+0F0h+Length]; Length
0x14000abd8  xor     edx, edx; SecurityDescriptor
0x14000abda  mov     rcx, rsi; SecurityInformation
0x14000abdd  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x14000abe4  nop     dword ptr [rax+rax+00h]
0x14000abe9  cmp     eax, 0C0000023h
0x14000abee  jnz     loc_14000AC7A
0x14000abf4  mov     eax, dword ptr [rsp+0F0h+Length]
0x14000abf8  test    eax, eax
0x14000abfa  jz      short loc_14000AC7A
0x14000abfc  mov     edx, eax
0x14000abfe  mov     ecx, 100h
0x14000ac03  cmovz   rdx, rdi
0x14000ac07  mov     r8d, 73714655h
0x14000ac0d  mov     r14d, eax
0x14000ac10  call    cs:__imp_ExAllocatePool2
0x14000ac17  nop     dword ptr [rax+rax+00h]
0x14000ac1c  mov     rdi, rax
0x14000ac1f  test    rax, rax
0x14000ac22  jz      short loc_14000AC7A
0x14000ac24  mov     r8d, r14d; Size
0x14000ac27  xor     edx, edx; Val
0x14000ac29  mov     rcx, rax; void *
0x14000ac2c  call    memset
0x14000ac31  lea     r9, [rbp+3Fh+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x14000ac35  mov     rdx, rdi; SecurityDescriptor
0x14000ac38  lea     r8, [rsp+0F0h+Length]; Length
0x14000ac3d  mov     rcx, rsi; SecurityInformation
0x14000ac40  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x14000ac47  nop     dword ptr [rax+rax+00h]
0x14000ac4c  test    eax, eax
0x14000ac4e  js      short loc_14000AC63
0x14000ac50  mov     [rbx+0C0h], rdi
0x14000ac57  mov     eax, dword ptr [rsp+0F0h+Length]
0x14000ac5b  mov     [rbx+0BCh], eax
0x14000ac61  jmp     short loc_14000AC7E
0x14000ac63  or      [rbx+8], r15d
0x14000ac67  xor     edx, edx; Tag
0x14000ac69  mov     rcx, rdi; P
0x14000ac6c  call    cs:__imp_ExFreePoolWithTag
0x14000ac73  nop     dword ptr [rax+rax+00h]
0x14000ac78  jmp     short loc_14000AC7E
0x14000ac7a  or      [rbx+8], r15d
0x14000ac7e  or      [rbx+4], r15d
0x14000ac82  jmp     short loc_14000AC88
0x14000ac84  test    cl, cl
0x14000ac86  jz      short loc_14000ACA1
0x14000ac88  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000ac8f  mov     rdx, rbx; EcpContext
0x14000ac92  mov     rcx, [rcx]; Filter
0x14000ac95  call    cs:__imp_FltAcknowledgeEcp
0x14000ac9c  nop     dword ptr [rax+rax+00h]
0x14000aca1  mov     rcx, [rbp+3Fh+var_40]
0x14000aca5  xor     rcx, rsp; StackCookie
0x14000aca8  call    __security_check_cookie
  ... truncated ...
```
