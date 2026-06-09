# CReplicaMetadata::_CleanupBatchOfDeletedItems(CReplicaMetadata::CReplicaStateCache *,ulong,_FILETIME,unsigned __int64,ulong,uchar const *,ulong &,CCoTaskMemPtr<uchar> &)

- ea: `0x1800dd5d0`
- end: `0x1800ddacd`
- name: `?_CleanupBatchOfDeletedItems@CReplicaMetadata@@AEAAJPEAUCReplicaStateCache@1@KU_FILETIME@@_KKPEBEAEAKAEAV?$CCoTaskMemPtr@E@@@Z`
- size: `1277`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800d90f0`

## callees

- `0x180009188`
- `0x1800091ac`
- `0x18000a694`
- `0x18004af44`
- `0x1800ad07c`
- `0x1800d70a0`
- `0x1800d7a70`
- `0x1800d7e94`
- `0x1800dd5d0`
- `0x1800ddad4`
- `0x1800de18c`
- `0x1800e0eac`
- `0x1800e3f28`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd940`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd940`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CReplicaMetadata::_CleanupBatchOfDeletedItems(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        struct _FILETIME a4,
        __int64 a5,
        int a6,
        __int64 a7,
        ...)
{
  unsigned __int64 v10; // rdx
  struct ISyncKnowledge **v11; // r12
  unsigned __int8 *v12; // r10
  unsigned __int64 v13; // r9
  int KnowledgeCopy; // edi
  CReplicaMetadata *v15; // rcx
  unsigned int v16; // r13d
  int DeletedItemsAfterLowerBoundInclusive; // eax
  unsigned __int64 v18; // r14
  _QWORD *v19; // r13
  const unsigned __int8 *v20; // rdi
  const unsigned __int8 **v21; // r13
  unsigned __int16 ItemIdSize; // ax
  char *v23; // rcx
  unsigned __int64 i; // r14
  unsigned int v25; // r14d
  struct ISyncKnowledge *v26; // rcx
  CReplicaMetadata *v27; // rcx
  struct _FILETIME *v28; // r15
  LPVOID v30; // [rsp+A0h] [rbp-41h] BYREF
  unsigned __int64 v31; // [rsp+A8h] [rbp-39h]
  __int64 v32; // [rsp+B0h] [rbp-31h]
  __int64 v33; // [rsp+B8h] [rbp-29h]
  LPVOID pv; // [rsp+C0h] [rbp-21h] BYREF
  unsigned __int8 *v35; // [rsp+C8h] [rbp-19h]
  __int64 v36; // [rsp+D0h] [rbp-11h]
  unsigned __int8 *v37; // [rsp+D8h] [rbp-9h]
  struct IUnknown *v38; // [rsp+130h] [rbp+4Fh] BYREF
  unsigned int v39; // [rsp+138h] [rbp+57h] BYREF
  struct _FILETIME v40; // [rsp+140h] [rbp+5Fh]
  unsigned __int8 *v41; // [rsp+160h] [rbp+7Fh] BYREF
  va_list va; // [rsp+160h] [rbp+7Fh]
  const unsigned __int8 **v43; // [rsp+168h] [rbp+87h]
  va_list va1; // [rsp+170h] [rbp+8Fh] BYREF

  va_start(va1, a7);
  va_start(va, a7);
  v41 = va_arg(va1, unsigned __int8 *);
  v43 = va_arg(va1, const unsigned __int8 **);
  v40 = a4;
  v39 = a3;
  *(_DWORD *)v41 = 0;
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v43);
  v11 = (struct ISyncKnowledge **)(a2 + 56);
  v12 = 0;
  if ( *(_QWORD *)(a2 + 56) && a5 )
  {
    v13 = *(unsigned int *)(a2 + 72) + ((unsigned __int64)*(unsigned int *)(a2 + 76) << 32);
    v10 = a4.dwLowDateTime + ((unsigned __int64)v40.dwHighDateTime << 32);
    if ( v10 < v13 )
    {
      KnowledgeCopy = 1;
    }
    else
    {
      v10 -= v13;
      KnowledgeCopy = v10 <= 10000 * a5;
    }
  }
  else
  {
    KnowledgeCopy = 0;
    if ( a5 )
      goto LABEL_9;
    ATL::CComPtrBase<IFileConcurrencyBlob>::Release(a2 + 56);
    KnowledgeCopy = CReplicaMetadata::_GetKnowledgeCopy(
                      v15,
                      (struct CReplicaMetadata::CReplicaStateCache *)a2,
                      (struct ISyncKnowledge **)(a2 + 56));
    v12 = 0;
  }
  if ( KnowledgeCopy )
    return (unsigned int)KnowledgeCopy;
LABEL_9:
  v16 = 1;
  v39 = 1;
  if ( !*v11 )
  {
LABEL_47:
    v41 = v12;
    v25 = (unsigned int)v12;
    v39 = (unsigned int)v12;
    v26 = *(struct ISyncKnowledge **)(a2 + 48);
    if ( v26 )
    {
      KnowledgeCopy = CMetaStoreUtils::SerializeKnowledge(v26, &v39, (unsigned __int8 **)va);
      v25 = v39;
      v12 = 0;
    }
    if ( KnowledgeCopy >= 0 )
    {
      if ( v16 )
      {
        ATL::CComPtrBase<IFileConcurrencyBlob>::Release(a2 + 56);
        KnowledgeCopy = CReplicaMetadata::_GetKnowledgeCopy(
                          v27,
                          (struct CReplicaMetadata::CReplicaStateCache *)a2,
                          (struct ISyncKnowledge **)(a2 + 56));
        if ( KnowledgeCopy >= 0 )
        {
          v28 = (struct _FILETIME *)(a2 + 72);
          *v28 = a4;
          v38 = 0;
          v39 = 0;
          KnowledgeCopy = CMetaStoreUtils::SerializeKnowledge(*v11, &v39, (unsigned __int8 **)&v38);
          if ( KnowledgeCopy >= 0 )
            KnowledgeCopy = CReplicaTable::UpdateReplicaInfo(
                              *(CReplicaTable **)(a1 + 160),
                              (const struct CSha1Hash *)(a1 + 120),
                              0,
                              0,
                              0,
                              0,
                              (unsigned __int8 **)va,
                              v25,
                              (unsigned __int8 **)&v38,
                              v39,
                              0,
                              v28,
                              0,
                              0,
                              0,
                              0,
                              0);
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v38);
        }
      }
      else
      {
        KnowledgeCopy = CReplicaTable::UpdateReplicaInfo(
                          *(CReplicaTable **)(a1 + 160),
                          (const struct CSha1Hash *)(a1 + 120),
                          0,
                          0,
                          v12,
                          (unsigned int)v12,
                          (unsigned __int8 **)va,
                          v25,
                          (unsigned __int8 **)v12,
                          (unsigned int)v12,
                          (unsigned __int64 *)v12,
                          (struct _FILETIME *)v12,
                          (unsigned int *)v12,
                          v12,
                          (unsigned int)v12,
                          (struct _GUID *)v12,
                          (unsigned __int64 *)v12);
      }
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((unsigned __int8 **)va);
    return (unsigned int)KnowledgeCopy;
  }
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  pv = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  DeletedItemsAfterLowerBoundInclusive = CItemTable::GetDeletedItemsAfterLowerBoundInclusive(
                                           *(_QWORD *)(a1 + 168),
                                           v10,
                                           a6,
                                           a7,
                                           (__int64)&v30,
                                           (__int64)&pv);
  KnowledgeCopy = DeletedItemsAfterLowerBoundInclusive;
  v12 = 0;
  if ( DeletedItemsAfterLowerBoundInclusive >= 0 )
  {
    if ( DeletedItemsAfterLowerBoundInclusive == 1 || (v39 = 0, v31 < 0x3E8) )
      v39 = 1;
    v38 = 0;
    KnowledgeCopy = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)a1 + 40LL))(a1, &v38);
    if ( *(struct IUnknown **)(a2 + 40) != v38 )
      ATL::AtlComPtrAssign((struct IUnknown **)(a2 + 40), v38);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
    v12 = 0;
  }
  v18 = 0;
LABEL_34:
  if ( KnowledgeCopy >= 0 )
  {
    while ( v18 < v31 )
    {
      KnowledgeCopy = ((__int64 (__fastcall *)(struct ISyncKnowledge *, _QWORD, _QWORD, char *))(*v11)->lpVtbl->ContainsChange)(
                        *v11,
                        *(_QWORD *)(a1 + 80),
                        *((_QWORD *)v30 + v18),
                        (char *)pv + 16 * v18);
      v12 = 0;
      if ( KnowledgeCopy )
        goto LABEL_33;
      KnowledgeCopy = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 120LL))(a1, *((_QWORD *)v30 + v18));
      v12 = 0;
      if ( KnowledgeCopy >= 0 )
      {
        v19 = (_QWORD *)(a2 + 48);
        v38 = 0;
        if ( *(_QWORD *)(a2 + 48) )
        {
          KnowledgeCopy = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)a1 + 56LL))(a1, &v38);
          if ( KnowledgeCopy >= 0 && (struct IUnknown *)*v19 != v38 )
            ATL::AtlComPtrAssign((struct IUnknown **)(a2 + 48), v38);
        }
        else
        {
          KnowledgeCopy = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IUnknown **))(**(_QWORD **)(a1 + 152) + 40LL))(
                            *(_QWORD *)(a1 + 152),
                            *(_QWORD *)(a1 + 80),
                            &v38);
          if ( KnowledgeCopy >= 0 )
            KnowledgeCopy = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *, __int64))(**(_QWORD **)(a1 + 152)
                                                                                          + 72LL))(
                              *(_QWORD *)(a1 + 152),
                              v38,
                              a2 + 48);
        }
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
        v12 = 0;
        if ( KnowledgeCopy >= 0 )
        {
          KnowledgeCopy = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)*v19 + 216LL))(
                            *v19,
                            *(_QWORD *)(a2 + 40),
                            (char *)pv + 16 * v18);
          v12 = 0;
          if ( KnowledgeCopy >= 0 )
          {
            KnowledgeCopy = CReplicaMetadata::_CleanupDependentNotContainedMergeTombstones(
                              (CReplicaMetadata *)a1,
                              (struct CReplicaMetadata::CReplicaStateCache *)a2,
                              *((const unsigned __int8 **)v30 + v18));
            v12 = 0;
          }
        }
      }
      if ( KnowledgeCopy != -2147216764 )
      {
LABEL_33:
        ++v18;
        goto LABEL_34;
      }
      KnowledgeCopy = 0;
      ++v18;
    }
    if ( !v39 )
    {
      v20 = (const unsigned __int8 *)*((_QWORD *)v30 + v31 - 1);
      *((_QWORD *)v30 + v31 - 1) = 0;
      v21 = v43;
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v43);
      *v21 = v20;
      KnowledgeCopy = CMetaStoreUtils::Add1ToItemId(v21, a1 + 92);
      v12 = 0;
      if ( KnowledgeCopy >= 0 )
      {
        ItemIdSize = CMetaStoreUtils::GetItemIdSize(*v21, (const struct _ID_PARAMETERS *)(a1 + 92));
        *(_DWORD *)v41 = ItemIdSize;
      }
    }
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    v12 = 0;
    pv = 0;
  }
  v35 = v12;
  v37 = v12;
  v23 = (char *)v30;
  if ( v30 )
  {
    for ( i = (unsigned __int64)v12; i < v31; v23 = (char *)v30 )
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v23[8 * i++]);
    CoTaskMemFree(v23);
    v12 = 0;
  }
  if ( KnowledgeCopy >= 0 )
  {
    v16 = v39;
    goto LABEL_47;
  }
  return (unsigned int)KnowledgeCopy;
}

```

## disassembly

```asm
0x1800dd5d0  mov     rax, rsp
0x1800dd5d3  mov     [rax+8], rbx
0x1800dd5d7  mov     [rax+20h], r9
0x1800dd5db  mov     [rax+18h], r8d
0x1800dd5df  push    rbp
0x1800dd5e0  push    rsi
0x1800dd5e1  push    rdi
0x1800dd5e2  push    r12
0x1800dd5e4  push    r13
0x1800dd5e6  push    r14
0x1800dd5e8  push    r15
0x1800dd5ea  lea     rbp, [rax-3Fh]
0x1800dd5ee  sub     rsp, 0E0h
0x1800dd5f5  mov     rbx, r9
0x1800dd5f8  mov     r15, rdx
0x1800dd5fb  mov     rsi, rcx
0x1800dd5fe  mov     rax, [rbp+37h+arg_38]
0x1800dd602  mov     dword ptr [rax], 0
0x1800dd608  mov     rcx, [rbp+37h+arg_40]
0x1800dd60f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800dd614  lea     r12, [r15+38h]
0x1800dd618  mov     r14d, 1
0x1800dd61e  mov     r8, [rbp+37h+arg_20]
0x1800dd622  xor     r10d, r10d
0x1800dd625  cmp     [r12], r10
0x1800dd629  jz      short loc_1800DD66B
0x1800dd62b  test    r8, r8
0x1800dd62e  jz      short loc_1800DD66B
0x1800dd630  mov     r9d, [r15+4Ch]
0x1800dd634  shl     r9, 20h
0x1800dd638  mov     eax, [r15+48h]
0x1800dd63c  add     r9, rax
0x1800dd63f  mov     edx, [rbp+37h+arg_1C]
0x1800dd642  shl     rdx, 20h
0x1800dd646  mov     eax, ebx
0x1800dd648  add     rdx, rax
0x1800dd64b  cmp     rdx, r9
0x1800dd64e  jb      short loc_1800DD666
0x1800dd650  sub     rdx, r9
0x1800dd653  imul    rax, r8, 2710h
0x1800dd65a  mov     edi, r10d
0x1800dd65d  cmp     rdx, rax
0x1800dd660  setbe   dil
0x1800dd664  jmp     short loc_1800DD68B
0x1800dd666  mov     edi, r14d
0x1800dd669  jmp     short loc_1800DD68B
0x1800dd66b  mov     edi, r10d
0x1800dd66e  test    r8, r8
0x1800dd671  jnz     short loc_1800DD693
0x1800dd673  mov     rcx, r12
0x1800dd676  call    ?Release@?$CComPtrBase@UIFileConcurrencyBlob@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IFileConcurrencyBlob>::Release(void)
0x1800dd67b  mov     r8, r12; struct ISyncKnowledge **
0x1800dd67e  mov     rdx, r15; struct CReplicaMetadata::CReplicaStateCache *
0x1800dd681  call    ?_GetKnowledgeCopy@CReplicaMetadata@@AEAAJPEAUCReplicaStateCache@1@PEAPEAUISyncKnowledge@@@Z; CReplicaMetadata::_GetKnowledgeCopy(CReplicaMetadata::CReplicaStateCache *,ISyncKnowledge * *)
0x1800dd686  mov     edi, eax
0x1800dd688  xor     r10d, r10d
0x1800dd68b  test    edi, edi
0x1800dd68d  jnz     loc_1800DDAB0
0x1800dd693  mov     r13d, r14d
0x1800dd696  mov     [rbp+37h+arg_10], r14d
0x1800dd69a  cmp     [r12], r10
0x1800dd69e  jz      loc_1800DD955
0x1800dd6a4  mov     [rbp+37h+var_78], r10
0x1800dd6a8  mov     [rbp+37h+var_70], r10
0x1800dd6ac  mov     [rbp+37h+var_68], r10
0x1800dd6b0  mov     [rbp+37h+var_60], r10
0x1800dd6b4  mov     [rbp+37h+pv], r10
0x1800dd6b8  mov     [rbp+37h+var_50], r10
0x1800dd6bc  mov     [rbp+37h+var_48], r10
0x1800dd6c0  mov     [rbp+37h+var_40], r10
0x1800dd6c4  lea     rax, [rbp+37h+pv]
0x1800dd6c8  mov     qword ptr [rsp+110h+var_E8], rax
0x1800dd6cd  lea     rax, [rbp+37h+var_78]
0x1800dd6d1  mov     [rsp+110h+var_F0], rax
0x1800dd6d6  mov     r9, [rbp+37h+arg_30]
0x1800dd6da  mov     r8d, [rbp+37h+arg_28]
0x1800dd6de  mov     rcx, [rsi+0A8h]
0x1800dd6e5  call    ?GetDeletedItemsAfterLowerBoundInclusive@CItemTable@@QEAAJKKPEBEPEAV?$CCoSimpleArray@V?$CCoTaskMemPtr@E@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$CCoTaskMemPtr@E@@@@@@PEAV?$CCoSimpleArray@U_SYNC_VERSION@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@U_SYNC_VERSION@@@@@@@Z; CItemTable::GetDeletedItemsAfterLowerBoundInclusive(ulong,ulong,uchar const *,CCoSimpleArray<CCoTaskMemPtr<uchar>,4294967294,CSimpleArrayStandardCompareHelper<CCoTaskMemPtr<uchar>>> *,CCoSimpleArray<_SYNC_VERSION,4294967294,CSimpleArrayStandardCompareHelper<_SYNC_VERSION>> *)
0x1800dd6ea  mov     edi, eax
0x1800dd6ec  xor     r10d, r10d
0x1800dd6ef  test    eax, eax
0x1800dd6f1  js      short loc_1800DD742
0x1800dd6f3  cmp     eax, r14d
0x1800dd6f6  jz      short loc_1800DD706
0x1800dd6f8  cmp     [rbp+37h+var_70], 3E8h
0x1800dd700  mov     [rbp+37h+arg_10], r10d
0x1800dd704  jnb     short loc_1800DD70A
0x1800dd706  mov     [rbp+37h+arg_10], r14d
0x1800dd70a  mov     [rbp+37h+arg_8], r10
0x1800dd70e  mov     rax, [rsi]
0x1800dd711  lea     rdx, [rbp+37h+arg_8]
0x1800dd715  mov     rcx, rsi
0x1800dd718  mov     rax, [rax+28h]
0x1800dd71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd721  mov     edi, eax
0x1800dd723  lea     rcx, [r15+28h]; struct IUnknown **
0x1800dd727  mov     rdx, [rbp+37h+arg_8]; struct IUnknown *
0x1800dd72b  cmp     [rcx], rdx
0x1800dd72e  jz      short loc_1800DD736
0x1800dd730  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800dd735  nop
0x1800dd736  lea     rcx, [rbp+37h+arg_8]
0x1800dd73a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800dd73f  xor     r10d, r10d
0x1800dd742  mov     r14, r10
0x1800dd745  jmp     loc_1800DD89A
0x1800dd74a  cmp     r14, [rbp+37h+var_70]
0x1800dd74e  jnb     loc_1800DD8A4
0x1800dd754  mov     rcx, [r12]
0x1800dd758  mov     r8, r14
0x1800dd75b  shl     r8, 4
0x1800dd75f  mov     [rbp+37h+var_80], r8
0x1800dd763  mov     rdx, [rcx]
0x1800dd766  mov     r9, [rbp+37h+pv]
0x1800dd76a  add     r9, r8
0x1800dd76d  mov     rax, [rdx+30h]
0x1800dd771  mov     r8, [rbp+37h+var_78]
0x1800dd775  mov     r8, [r8+r14*8]
0x1800dd779  mov     rdx, [rsi+50h]
0x1800dd77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd782  mov     edi, eax
0x1800dd784  xor     r10d, r10d
0x1800dd787  test    eax, eax
0x1800dd789  jnz     loc_1800DD897
0x1800dd78f  mov     rax, [rsi]
0x1800dd792  mov     rdx, [rbp+37h+var_78]
0x1800dd796  mov     rdx, [rdx+r14*8]
0x1800dd79a  mov     rcx, rsi
0x1800dd79d  mov     rax, [rax+78h]
0x1800dd7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd7a6  mov     edi, eax
0x1800dd7a8  xor     r10d, r10d
0x1800dd7ab  test    eax, eax
0x1800dd7ad  js      loc_1800DD884
0x1800dd7b3  lea     r13, [r15+30h]
0x1800dd7b7  mov     [rbp+37h+arg_8], r10
0x1800dd7bb  cmp     [r13+0], r10
0x1800dd7bf  jnz     short loc_1800DD809
0x1800dd7c1  mov     rcx, [rsi+98h]
0x1800dd7c8  mov     rax, [rcx]
0x1800dd7cb  lea     r8, [rbp+37h+arg_8]
0x1800dd7cf  mov     rdx, [rsi+50h]
0x1800dd7d3  mov     rax, [rax+28h]
0x1800dd7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd7dc  mov     edi, eax
0x1800dd7de  test    eax, eax
0x1800dd7e0  js      short loc_1800DD7FE
0x1800dd7e2  mov     rcx, [rsi+98h]
0x1800dd7e9  mov     rax, [rcx]
0x1800dd7ec  mov     r8, r13
0x1800dd7ef  mov     rdx, [rbp+37h+arg_8]
0x1800dd7f3  mov     rax, [rax+48h]
0x1800dd7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd7fc  mov     edi, eax
0x1800dd7fe  lea     rcx, [rbp+37h+arg_8]
0x1800dd802  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800dd807  jmp     short loc_1800DD83D
0x1800dd809  mov     rax, [rsi]
0x1800dd80c  lea     rdx, [rbp+37h+arg_8]
0x1800dd810  mov     rcx, rsi
0x1800dd813  mov     rax, [rax+38h]
0x1800dd817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd81c  mov     edi, eax
0x1800dd81e  test    eax, eax
0x1800dd820  js      short loc_1800DD834
0x1800dd822  mov     rdx, [rbp+37h+arg_8]; struct IUnknown *
0x1800dd826  cmp     [r13+0], rdx
0x1800dd82a  jz      short loc_1800DD834
0x1800dd82c  mov     rcx, r13; struct IUnknown **
0x1800dd82f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800dd834  lea     rcx, [rbp+37h+arg_8]
0x1800dd838  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800dd83d  xor     r10d, r10d
0x1800dd840  test    edi, edi
0x1800dd842  js      short loc_1800DD884
0x1800dd844  mov     rcx, [r13+0]
0x1800dd848  mov     rdx, [rcx]
0x1800dd84b  mov     r8, [rbp+37h+var_80]
0x1800dd84f  add     r8, [rbp+37h+pv]
0x1800dd853  mov     rax, [rdx+0D8h]
0x1800dd85a  mov     rdx, [r15+28h]
0x1800dd85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd863  mov     edi, eax
0x1800dd865  xor     r10d, r10d
0x1800dd868  test    eax, eax
0x1800dd86a  js      short loc_1800DD884
0x1800dd86c  mov     r8, [rbp+37h+var_78]
0x1800dd870  mov     r8, [r8+r14*8]; unsigned __int8 *
0x1800dd874  mov     rdx, r15; struct CReplicaMetadata::CReplicaStateCache *
0x1800dd877  mov     rcx, rsi; this
0x1800dd87a  call    ?_CleanupDependentNotContainedMergeTombstones@CReplicaMetadata@@AEAAJPEAUCReplicaStateCache@1@PEBE@Z; CReplicaMetadata::_CleanupDependentNotContainedMergeTombstones(CReplicaMetadata::CReplicaStateCache *,uchar const *)
0x1800dd87f  mov     edi, eax
0x1800dd881  xor     r10d, r10d
0x1800dd884  cmp     edi, 80041284h
0x1800dd88a  jnz     short loc_1800DD897
0x1800dd88c  mov     edi, r10d
0x1800dd88f  inc     r14
0x1800dd892  jmp     loc_1800DD74A
0x1800dd897  inc     r14
0x1800dd89a  test    edi, edi
0x1800dd89c  jns     loc_1800DD74A
0x1800dd8a2  jmp     short loc_1800DD8FA
0x1800dd8a4  cmp     [rbp+37h+arg_10], r10d
0x1800dd8a8  jnz     short loc_1800DD8FA
0x1800dd8aa  mov     rdx, [rbp+37h+var_78]
0x1800dd8ae  mov     rax, [rbp+37h+var_70]
0x1800dd8b2  mov     rdi, [rdx+rax*8-8]
0x1800dd8b7  mov     [rdx+rax*8-8], r10
0x1800dd8bc  mov     r13, [rbp+37h+arg_40]
0x1800dd8c3  mov     rcx, r13
0x1800dd8c6  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800dd8cb  mov     [r13+0], rdi
0x1800dd8cf  lea     rdx, [rsi+5Ch]
0x1800dd8d3  mov     rcx, r13
0x1800dd8d6  call    ?Add1ToItemId@CMetaStoreUtils@@SAJAEAV?$CCoTaskMemPtr@E@@PEBU_ID_PARAMETERS@@@Z; CMetaStoreUtils::Add1ToItemId(CCoTaskMemPtr<uchar> &,_ID_PARAMETERS const *)
0x1800dd8db  mov     edi, eax
0x1800dd8dd  xor     r10d, r10d
0x1800dd8e0  test    eax, eax
0x1800dd8e2  js      short loc_1800DD8FA
0x1800dd8e4  lea     rdx, [rsi+5Ch]; struct _ID_PARAMETERS *
0x1800dd8e8  mov     rcx, [r13+0]; unsigned __int8 *
0x1800dd8ec  call    ?GetItemIdSize@CMetaStoreUtils@@SAGPEBEPEBU_ID_PARAMETERS@@@Z; CMetaStoreUtils::GetItemIdSize(uchar const *,_ID_PARAMETERS const *)
0x1800dd8f1  movzx   ecx, ax
0x1800dd8f4  mov     rax, [rbp+37h+arg_38]
0x1800dd8f8  mov     [rax], ecx
0x1800dd8fa  mov     rcx, [rbp+37h+pv]; pv
0x1800dd8fe  test    rcx, rcx
0x1800dd901  jz      short loc_1800DD910
0x1800dd903  call    cs:__imp_CoTaskMemFree
0x1800dd909  xor     r10d, r10d
0x1800dd90c  mov     [rbp+37h+pv], r10
0x1800dd910  mov     [rbp+37h+var_50], r10
0x1800dd914  mov     [rbp+37h+var_40], r10
0x1800dd918  mov     rcx, [rbp+37h+var_78]
0x1800dd91c  test    rcx, rcx
0x1800dd91f  jz      short loc_1800DD949
0x1800dd921  mov     r14, r10
0x1800dd924  cmp     [rbp+37h+var_70], r10
0x1800dd928  jbe     short loc_1800DD940
0x1800dd92a  lea     rcx, [rcx+r14*8]
0x1800dd92e  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800dd933  inc     r14
0x1800dd936  mov     rcx, [rbp+37h+var_78]; pv
0x1800dd93a  cmp     r14, [rbp+37h+var_70]
0x1800dd93e  jb      short loc_1800DD92A
0x1800dd940  call    cs:__imp_CoTaskMemFree
0x1800dd946  xor     r10d, r10d
0x1800dd949  test    edi, edi
0x1800dd94b  js      loc_1800DDAB0
0x1800dd951  mov     r13d, [rbp+37h+arg_10]
0x1800dd955  mov     [rbp+37h+arg_38], r10
0x1800dd959  mov     r14d, r10d
0x1800dd95c  mov     [rbp+37h+arg_10], r10d
0x1800dd960  mov     rcx, [r15+30h]; struct ISyncKnowledge *
0x1800dd964  test    rcx, rcx
0x1800dd967  jz      short loc_1800DD97F
0x1800dd969  lea     r8, [rbp+37h+arg_38]; unsigned __int8 **
0x1800dd96d  lea     rdx, [rbp+37h+arg_10]; unsigned int *
0x1800dd971  call    ?SerializeKnowledge@CMetaStoreUtils@@SAJPEAUISyncKnowledge@@PEAKPEAPEAE@Z; CMetaStoreUtils::SerializeKnowledge(ISyncKnowledge *,ulong *,uchar * *)
0x1800dd976  mov     edi, eax
0x1800dd978  mov     r14d, [rbp+37h+arg_10]
0x1800dd97c  xor     r10d, r10d
0x1800dd97f  test    edi, edi
0x1800dd981  js      loc_1800DDAA7
0x1800dd987  test    r13d, r13d
0x1800dd98a  jz      loc_1800DDA47
0x1800dd990  mov     rcx, r12
0x1800dd993  call    ?Release@?$CComPtrBase@UIFileConcurrencyBlob@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IFileConcurrencyBlob>::Release(void)
0x1800dd998  mov     r8, r12; struct ISyncKnowledge **
0x1800dd99b  mov     rdx, r15; struct CReplicaMetadata::CReplicaStateCache *
0x1800dd99e  call    ?_GetKnowledgeCopy@CReplicaMetadata@@AEAAJPEAUCReplicaStateCache@1@PEAPEAUISyncKnowledge@@@Z; CReplicaMetadata::_GetKnowledgeCopy(CReplicaMetadata::CReplicaStateCache *,ISyncKnowledge * *)
0x1800dd9a3  mov     edi, eax
0x1800dd9a5  xor     r13d, r13d
0x1800dd9a8  test    eax, eax
0x1800dd9aa  js      loc_1800DDAA7
0x1800dd9b0  add     r15, 48h ; 'H'
0x1800dd9b4  mov     [r15], rbx
0x1800dd9b7  mov     [rbp+37h+arg_8], r13
0x1800dd9bb  mov     [rbp+37h+arg_10], r13d
0x1800dd9bf  lea     r8, [rbp+37h+arg_8]; unsigned __int8 **
0x1800dd9c3  lea     rdx, [rbp+37h+arg_10]; unsigned int *
0x1800dd9c7  mov     rcx, [r12]; struct ISyncKnowledge *
0x1800dd9cb  call    ?SerializeKnowledge@CMetaStoreUtils@@SAJPEAUISyncKnowledge@@PEAKPEAPEAE@Z; CMetaStoreUtils::SerializeKnowledge(ISyncKnowledge *,ulong *,uchar * *)
0x1800dd9d0  mov     edi, eax
0x1800dd9d2  test    eax, eax
0x1800dd9d4  js      short loc_1800DDA3C
0x1800dd9d6  lea     rdx, [rsi+78h]; struct CSha1Hash *
0x1800dd9da  mov     [rsp+80h], r13; unsigned __int64 *
0x1800dd9e2  mov     [rsp+110h+var_98], r13; struct _GUID *
0x1800dd9e7  mov     [rsp+110h+var_A0], r13d; unsigned int
0x1800dd9ec  mov     [rsp+110h+var_A8], r13; unsigned __int8 *
0x1800dd9f1  mov     [rsp+110h+var_B0], r13; unsigned int *
0x1800dd9f6  mov     [rsp+110h+var_B8], r15; struct _FILETIME *
0x1800dd9fb  mov     [rsp+110h+var_C0], r13; unsigned __int64 *
0x1800dda00  mov     eax, [rbp+37h+arg_10]
0x1800dda03  mov     [rsp+110h+var_C8], eax; unsigned int
0x1800dda07  lea     rax, [rbp+37h+arg_8]
0x1800dda0b  mov     [rsp+110h+var_D0], rax; unsigned __int8 **
0x1800dda10  mov     [rsp+110h+var_D8], r14d; unsigned int
0x1800dda15  lea     rax, [rbp+37h+arg_38]
  ... truncated ...
```
