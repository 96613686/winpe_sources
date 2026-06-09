# CEseLayerObjectStore::InsertObject(__MIDL_RPCIndexedDB_0001 const *,__MIDL_RPCIndexedDB_0004 const *,__MIDL_RPCIndexedDB_0001 *,__int64 *)

- ea: `0x180021cc0`
- end: `0x18002273a`
- name: `?InsertObject@CEseLayerObjectStore@@QEAAJPEBU__MIDL_RPCIndexedDB_0001@@PEBU__MIDL_RPCIndexedDB_0004@@PEAU2@PEA_J@Z`
- size: `2682`
- prototype: `__int64 __fastcall(CEseLayerObjectStore *this, const struct __MIDL_RPCIndexedDB_0001 *, const struct __MIDL_RPCIndexedDB_0004 *, struct __MIDL_RPCIndexedDB_0001 *, __int64 *)`
- caller_count: `3`
- callee_count: `33`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018358`
- `0x18002170c`
- `0x1800b16fc`

## callees

- `0x18000dd40`
- `0x180015a40`
- `0x180015bb0`
- `0x180016b40`
- `0x180017c20`
- `0x180018118`
- `0x180020b40`
- `0x180020ea0`
- `0x180021cc0`
- `0x180022740`
- `0x180022784`
- `0x1800227b0`
- `0x180022854`
- `0x1800228e4`
- `0x180022990`
- `0x1800229fc`
- `0x180023250`
- `0x180024650`
- `0x18004ebcc`
- `0x18004ebe0`
- `0x18004ee84`
- `0x18004ef64`
- `0x1800766b8`
- `0x180080fb0`
- `0x180081a96`
- `0x180081b40`
- `0x180084259`
- `0x1800a713c`
- `0x1800afa1c`
- `0x1800b42bc`
- `0x1800ba434`
- `0x1800ba734`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800220d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800220d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021d26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022521`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180021df4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180021df4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022586`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180022586`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180021e09`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180021e09`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180021e31`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180021e31`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180021e66`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180021e66`

## pseudocode

```c
__int64 __fastcall CEseLayerObjectStore::InsertObject(
        CEseLayerObjectStore *this,
        const struct __MIDL_RPCIndexedDB_0001 *a2,
        const struct __MIDL_RPCIndexedDB_0004 *a3,
        struct __MIDL_RPCIndexedDB_0001 *a4,
        __int64 *a5)
{
  const struct __MIDL_RPCIndexedDB_0001 *v6; // r15
  CEseLayerObjectStore *v7; // r12
  __int64 v8; // rbx
  const char *v9; // r9
  unsigned __int64 v10; // rdi
  unsigned int v11; // r14d
  bool v12; // si
  int HighWaterValue; // ebx
  const void *v14; // r9
  size_t v16; // r14
  const void *v17; // r12
  HGLOBAL v18; // rsi
  void *v19; // r15
  signed int v20; // eax
  signed int v21; // eax
  __int64 v22; // rax
  int v23; // esi
  int v24; // ebx
  unsigned __int64 v25; // r14
  void *v26; // rcx
  unsigned int v27; // r15d
  size_t v28; // r14
  void *v29; // rax
  const char *v30; // r9
  void *v31; // r12
  JET_COLUMNID **v32; // r12
  JET_COLUMNID *v33; // rdx
  int v34; // r8d
  char *v35; // rcx
  char v36; // r14
  __int64 v37; // rdx
  unsigned int v38; // edx
  char v39; // si
  struct IStream *v40; // r13
  JET_TABLEID v41; // r14
  int v42; // edx
  JET_COLUMNID *v43; // r15
  __int64 *v44; // r14
  int v45; // eax
  char v46; // r10
  unsigned int v47; // r11d
  int v48; // ecx
  const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *v49; // r8
  const void *v50; // r9
  signed int LastError; // eax
  __m128d v52; // xmm1
  int v53; // r8d
  int v54; // r8d
  JET_COLUMNID v55; // eax
  int v56; // ecx
  int v57; // ecx
  unsigned int v58; // [rsp+20h] [rbp-E0h]
  void *Src; // [rsp+40h] [rbp-C0h] BYREF
  JET_TABLEID v60; // [rsp+48h] [rbp-B8h] BYREF
  CEseLayerObjectStore *v61; // [rsp+50h] [rbp-B0h]
  LPSTREAM ppstm; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v63[24]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v64; // [rsp+78h] [rbp-88h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h]
  __m128d v66; // [rsp+90h] [rbp-70h] BYREF
  void *v67; // [rsp+A0h] [rbp-60h]
  struct __MIDL_RPCIndexedDB_0001 *v68; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v69; // [rsp+B0h] [rbp-50h] BYREF
  const void *v70; // [rsp+C0h] [rbp-40h]
  __int128 v71; // [rsp+C8h] [rbp-38h] BYREF
  const void *v72; // [rsp+D8h] [rbp-28h]
  __int128 v73; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v74; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v75; // [rsp+100h] [rbp+0h]
  JET_RECSIZE v76; // [rsp+110h] [rbp+10h] BYREF
  JET_RECSIZE v77; // [rsp+150h] [rbp+50h] BYREF
  struct JET_SETCOLUMN v78; // [rsp+190h] [rbp+90h] BYREF
  JET_COLUMNID v79; // [rsp+1B8h] [rbp+B8h]
  _BYTE *v80; // [rsp+1C0h] [rbp+C0h]
  __int64 v81; // [rsp+1C8h] [rbp+C8h]
  int v82; // [rsp+1D0h] [rbp+D0h]
  __int64 v83; // [rsp+1D4h] [rbp+D4h]
  JET_COLUMNID v84; // [rsp+1E0h] [rbp+E0h]
  __int64 v85; // [rsp+1E8h] [rbp+E8h]
  __int64 v86; // [rsp+1F0h] [rbp+F0h]
  int v87; // [rsp+1F8h] [rbp+F8h]
  __int64 v88; // [rsp+1FCh] [rbp+FCh]
  int v89; // [rsp+208h] [rbp+108h]
  __int64 v90; // [rsp+210h] [rbp+110h]
  __int64 v91; // [rsp+218h] [rbp+118h]
  int v92; // [rsp+220h] [rbp+120h]
  __int64 v93; // [rsp+224h] [rbp+124h]
  struct JET_SETCOLUMN v94; // [rsp+230h] [rbp+130h] BYREF
  JET_COLUMNID v95; // [rsp+258h] [rbp+158h]
  __int128 *v96; // [rsp+260h] [rbp+160h]
  int v97; // [rsp+268h] [rbp+168h]
  __int64 v98; // [rsp+26Ch] [rbp+16Ch]
  __int64 v99; // [rsp+274h] [rbp+174h]
  int v100; // [rsp+280h] [rbp+180h]
  __int64 v101; // [rsp+288h] [rbp+188h]
  __int64 v102; // [rsp+290h] [rbp+190h]
  int v103; // [rsp+298h] [rbp+198h]
  __int64 v104; // [rsp+29Ch] [rbp+19Ch]
  int v105; // [rsp+2A8h] [rbp+1A8h]
  __int64 v106; // [rsp+2B0h] [rbp+1B0h]
  __int64 v107; // [rsp+2B8h] [rbp+1B8h]
  int v108; // [rsp+2C0h] [rbp+1C0h]
  __int64 v109; // [rsp+2C4h] [rbp+1C4h]
  wil::details::in1diag3 *retaddr; // [rsp+A58h] [rbp+958h]

  v68 = a4;
  v6 = a2;
  Src = a2;
  v7 = this;
  v61 = this;
  v74 = a5;
  if ( a4 )
  {
    *(_OWORD *)a4 = 0;
    *((_QWORD *)a4 + 2) = 0;
  }
  v60 = -1;
  v8 = *((_QWORD *)this + 6);
  if ( *(_DWORD *)(v8 + 12) != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\ese\\transaction.cxx",
      v9);
  v10 = *(_QWORD *)(v8 + 24);
  v11 = *(_DWORD *)(v8 + 32);
  v12 = 0;
  HighWaterValue = HrJetBeginTransaction(v10);
  if ( HighWaterValue < 0
    || (v12 = 1,
        HighWaterValue = HrJetOpenTable(v10, v11, (const unsigned __int16 *)v7 + 28, v14, v58, 0, &v60),
        HighWaterValue < 0) )
  {
    CloseTableIfNecessary(v10, &v60, HighWaterValue);
    RollbackIfNecessary(v10, v12, HighWaterValue);
    return (unsigned int)HighWaterValue;
  }
  v16 = *(unsigned int *)a3;
  ppstm = 0;
  HighWaterValue = -2147024809;
  if ( v16 )
  {
    v17 = (const void *)*((_QWORD *)a3 + 1);
    if ( !v17 )
      goto LABEL_27;
    v18 = GlobalAlloc(2u, (unsigned int)v16);
    if ( !v18 )
    {
      LastError = GetLastError();
      HighWaterValue = LastError;
      if ( LastError > 0 )
        HighWaterValue = (unsigned __int16)LastError | 0x80070000;
      if ( HighWaterValue < 0 )
        goto LABEL_27;
    }
    v19 = GlobalLock(v18);
    if ( v19 )
      goto LABEL_18;
    v21 = GetLastError();
    HighWaterValue = v21;
    if ( v21 > 0 )
      HighWaterValue = (unsigned __int16)v21 | 0x80070000;
    if ( HighWaterValue >= 0 )
    {
LABEL_18:
      if ( v19 )
      {
        memcpy_0(v19, v17, v16);
      }
      else
      {
        *(_DWORD *)_o__errno() = 22;
        invalid_parameter_noinfo();
      }
      if ( GlobalUnlock(v18) || !GetLastError() )
        goto LABEL_19;
      v20 = GetLastError();
      HighWaterValue = v20;
      if ( v20 > 0 )
        HighWaterValue = (unsigned __int16)v20 | 0x80070000;
      if ( HighWaterValue >= 0 )
      {
LABEL_19:
        HighWaterValue = CreateStreamOnHGlobal(v18, 1, &ppstm);
        if ( HighWaterValue >= 0 )
        {
LABEL_26:
          v6 = (const struct __MIDL_RPCIndexedDB_0001 *)Src;
LABEL_27:
          v7 = v61;
          goto LABEL_28;
        }
        ppstm = 0;
      }
    }
    if ( v18 )
      GlobalFree(v18);
    goto LABEL_26;
  }
LABEL_28:
  if ( HighWaterValue >= 0 )
  {
    memset(v63, 0, sizeof(v63));
    v64 = 0;
    v65 = 0;
    if ( v6 )
    {
      v22 = SmartRpcStruct<__MIDL_RPCIndexedDB_0001,IndexedDbRpcHelpers::IndexedDbKeyTrait>::CloneFrom(&v69, v6);
      v23 = *(_DWORD *)v22;
      LODWORD(v66.m128d_f64[0]) = *(_DWORD *)v22;
      v24 = *(_DWORD *)(v22 + 4);
      HIDWORD(v66.m128d_f64[0]) = v24;
      v25 = *(_QWORD *)(v22 + 8);
      *(_QWORD *)&v66.m128d_f64[1] = v25;
      v26 = *(void **)(v22 + 16);
      Src = v26;
      v67 = v26;
      *(_OWORD *)v22 = 0;
      *(_QWORD *)(v22 + 16) = 0;
      if ( *(_DWORD *)v63 == 4 && *(_QWORD *)&v63[16] )
      {
        *(_QWORD *)&v73 = *(_QWORD *)&v63[16];
        WxFreeHeapEx(&v73);
        *(_OWORD *)&v63[8] = 0;
        v26 = Src;
      }
      v27 = v25;
      memset(v63, 0, sizeof(v63));
      v64 = 0;
      v65 = 0;
      if ( v23 )
      {
        v75 = v25;
        if ( v23 == 4 )
        {
          v73 = 0;
          if ( (_DWORD)v25 )
          {
            v28 = 2LL * (unsigned int)v25;
            v29 = MIDL_user_allocate(v28);
            v31 = v29;
            if ( !v29 )
              wil::details::in1diag3::_FailFast_NullAlloc(
                retaddr,
                (void *)0x15,
                (unsigned int)"onecoreuap\\inetcore\\lib\\webplatstorageutils\\lib\\stringbuffer.cxx",
                v30);
            memcpy_0(v29, Src, v28);
          }
          else
          {
            v31 = 0;
          }
          v75 = __PAIR64__(DWORD1(v73), v27);
          v25 = __PAIR64__(DWORD1(v73), v27);
        }
        else
        {
          v31 = v26;
        }
        *(_DWORD *)v63 = v23;
        *(_DWORD *)&v63[4] = v24;
        *(_QWORD *)&v63[8] = v25;
        *(_QWORD *)&v63[16] = v31;
      }
      if ( *(_DWORD *)v63 == 1 )
      {
        LODWORD(v64) = 1;
        *((double *)&v64 + 1) = (double)*(int *)&v63[8];
      }
      if ( v23 == 4 )
        IndexedDbRpcHelpers::StringBufferTrait::Free((struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *)&v66.m128d_f64[1]);
      if ( (_DWORD)v69 == 4 )
        IndexedDbRpcHelpers::StringBufferTrait::Free((struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *)((char *)&v69 + 8));
      v7 = v61;
    }
    else
    {
      Src = 0;
      HighWaterValue = CEseLayerObjectStore::GetHighWaterValue(v7, (unsigned __int64 *)&Src);
      if ( HighWaterValue < 0 )
        goto LABEL_119;
      *(_QWORD *)&v66.m128d_f64[0] = 2;
      v52 = 0;
      if ( (__int64)Src < 0 )
        v52.m128d_f64[0] = (double)(int)((unsigned __int8)Src & 1 | ((unsigned __int64)Src >> 1))
                         + (double)(int)((unsigned __int8)Src & 1 | ((unsigned __int64)Src >> 1));
      else
        v52.m128d_f64[0] = (double)(int)Src;
      v66 = _mm_unpacklo_pd(v66, v52);
      v67 = 0;
      CEseLayerKeyHelper::SetInsertionKey((CEseLayerKeyHelper *)v63, (const struct IndexedDbKey *)&v66);
      IndexedDbRpcHelpers::IndexedDbKeyTrait::Free((struct __MIDL_RPCIndexedDB_0001 *)&v66);
    }
    v32 = (JET_COLUMNID **)((char *)v7 + 24);
    v33 = *v32;
    v78.columnid = 0;
    memset(&v78.pvData, 0, 20);
    *(_QWORD *)&v78.itagSequence = 1;
    v79 = 0;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    v83 = 1;
    v84 = 0;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v88 = 1;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 1;
    if ( (_DWORD)v64 )
    {
      v34 = v64;
      v35 = (char *)&v64 + 8;
    }
    else
    {
      v34 = *(_DWORD *)v63;
      v35 = &v63[8];
    }
    if ( v34 == 4 )
    {
      v78.columnid = v33[55];
      v78.pvData = (const void *)*((_QWORD *)v35 + 1);
      v78.cbData = StringBufferByteLen((const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *)v35);
      goto LABEL_54;
    }
    if ( v34 )
    {
      v53 = v34 - 1;
      if ( !v53 || (v54 = v53 - 1) == 0 )
      {
        v55 = v33[133];
        goto LABEL_117;
      }
      if ( v54 == 1 )
      {
        v55 = v33[94];
LABEL_117:
        v78.columnid = v55;
        v78.pvData = v35;
        v78.cbData = 8;
        v78.itagSequence = 0;
LABEL_54:
        v79 = v33[172];
        v80 = v63;
        LODWORD(v81) = 4;
        v84 = v33[243];
        v85 = *((_QWORD *)a3 + 1);
        LODWORD(v86) = *(_DWORD *)a3;
        HighWaterValue = HrJetPrepareUpdate(v10, v60, 0);
        if ( HighWaterValue >= 0 )
        {
          HighWaterValue = HrJetSetColumns(v10, v60, &v78, 3u);
          if ( HighWaterValue < 0 )
          {
            v36 = 1;
LABEL_57:
            HrJetPrepareUpdate(v10, v60, 3u);
LABEL_61:
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
            ppstm = 0;
            if ( *(_DWORD *)v63 == 4 && *(_QWORD *)&v63[16] )
            {
              v68 = *(struct __MIDL_RPCIndexedDB_0001 **)&v63[16];
              WxFreeHeapEx(&v68);
            }
            goto LABEL_64;
          }
          v39 = 1;
          v69 = 0;
          v70 = 0;
          v71 = 0;
          v72 = 0;
          v40 = ppstm;
          v41 = v60;
          v42 = 0;
          v43 = *v32;
          if ( *v32 == (JET_COLUMNID *)v32 )
          {
LABEL_70:
            LODWORD(Src) = 0;
            HighWaterValue = HrJetUpdate(v10, v41, &v94, 0x7D0u, (unsigned int *)&Src);
            if ( HighWaterValue < 0 )
              goto LABEL_59;
            v39 = 0;
            HighWaterValue = HrJetGotoBookmark(v10, v60, &v94, (unsigned int)Src);
            if ( HighWaterValue < 0 )
              goto LABEL_59;
            v44 = v74;
            if ( v74 )
            {
              memset_0(&v77, 0, sizeof(v77));
              HighWaterValue = HrJetGetRecordSize(v10, v60, &v77, 0);
              if ( HighWaterValue < 0 )
                goto LABEL_59;
              v76 = v77;
              LOBYTE(v37) = 1;
              HighWaterValue = AdjustQuotaUsage(&v76, v37, v44);
              if ( HighWaterValue < 0 )
                goto LABEL_59;
            }
            HighWaterValue = HrJetCommitTransaction(v10, 1u);
            if ( HighWaterValue < 0 )
            {
LABEL_59:
              v36 = 1;
            }
            else
            {
              v36 = 0;
              if ( v68 )
                IDBKeyCopy((const struct __MIDL_RPCIndexedDB_0001 *const)v63, v68);
              if ( *((_QWORD *)*v32 + 125) )
                CEseLayerObjectStore::UpdateHighWaterValueWithKeyIfEqualOrBigger(
                  v61,
                  (const struct __MIDL_RPCIndexedDB_0001 *)v63);
            }
            IDBKeyFree((struct __MIDL_RPCIndexedDB_0001 *)&v69);
            if ( !v39 )
              goto LABEL_61;
            goto LABEL_57;
          }
          while ( 1 )
          {
            if ( v42 < 0 )
            {
LABEL_87:
              HighWaterValue = v42;
              goto LABEL_59;
            }
            if ( v43 != *v32 )
            {
              v45 = CEseLayerIndexSchema::ReadFromBlobKeyPathToIndexedDbKey(
                      (CEseLayerIndexSchema *)v43,
                      v40,
                      (struct CEseLayerKeyHelper *)&v69);
              v42 = v45;
              if ( v45 >= 0 )
              {
                v46 = 1;
                v47 = 2;
                v42 = 0;
                v94.columnid = 0;
                memset(&v94.pvData, 0, 20);
                *(_QWORD *)&v94.itagSequence = 1;
                v98 = 0;
                v99 = 1;
                v100 = 0;
                v101 = 0;
                v102 = 0;
                v103 = 0;
                v104 = 1;
                v105 = 0;
                v106 = 0;
                v107 = 0;
                v108 = 0;
                v109 = 1;
                v48 = v71;
                if ( (_DWORD)v71 )
                {
                  v49 = (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *)((char *)&v71 + 8);
                  v50 = v72;
                }
                else
                {
                  v48 = v69;
                  v49 = (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *)((char *)&v69 + 8);
                  v50 = v70;
                }
                if ( v48 == 4 )
                {
                  v94.columnid = v43[55];
                  v94.pvData = v50;
                  v94.cbData = StringBufferByteLen(v49);
                }
                else
                {
                  if ( !v48 )
                    goto LABEL_125;
                  v56 = v48 - 1;
                  if ( !v56 || (v57 = v56 - 1) == 0 )
                  {
                    v94.columnid = v43[133];
                    v94.pvData = v49;
                    v94.cbData = 8;
                    v94.itagSequence = 0;
                    goto LABEL_92;
                  }
                  if ( v57 == 1 )
                  {
                    v94.columnid = v43[94];
                    v94.pvData = v49;
                    v94.cbData = 8;
                    v94.itagSequence = 0;
                  }
                  else
                  {
LABEL_125:
                    v42 = -2147467263;
                  }
                }
LABEL_92:
                v95 = v43[172];
                v96 = &v69;
                v97 = 4;
LABEL_93:
                if ( v42 >= 0 && v46 )
                  v42 = HrJetSetColumns(v10, v41, &v94, v47);
                goto LABEL_80;
              }
              if ( v45 != -2147024809 )
              {
                v46 = 0;
                v47 = 0;
                goto LABEL_93;
              }
              v42 = 0;
            }
LABEL_80:
            v43 = *(JET_COLUMNID **)v43;
            if ( v43 == (JET_COLUMNID *)v32 )
            {
              if ( v42 >= 0 )
              {
                v41 = v60;
                goto LABEL_70;
              }
              goto LABEL_87;
            }
          }
        }
LABEL_119:
        v36 = 1;
        goto LABEL_61;
      }
    }
    v79 = v33[172];
    LODWORD(v81) = 4;
    v80 = v63;
    HighWaterValue = -2147467263;
    goto LABEL_119;
  }
  v36 = 1;
LABEL_64:
  v38 = v60;
  if ( v60 != -1 && (int)HrJetCloseTable(v10, v60) >= 0 )
    v60 = -1;
  if ( v36 )
    HrJetRollback(v10, v38);
  return (unsigned int)HighWaterValue;
}

```

## disassembly

```asm
0x180021cc0  push    rbp
0x180021cc2  push    rbx
0x180021cc3  push    rsi
0x180021cc4  push    rdi
0x180021cc5  push    r12
0x180021cc7  push    r13
0x180021cc9  push    r14
0x180021ccb  push    r15
0x180021ccd  lea     rbp, [rsp-918h]
0x180021cd5  sub     rsp, 0A18h
0x180021cdc  mov     rax, cs:__security_cookie
0x180021ce3  xor     rax, rsp
0x180021ce6  mov     [rbp+950h+var_50], rax
0x180021ced  mov     [rbp+950h+var_9A8], r9
0x180021cf1  mov     r13, r8
0x180021cf4  mov     r15, rdx
0x180021cf7  mov     [rsp+0A50h+Src], rdx
0x180021cfc  mov     r12, rcx
0x180021cff  mov     [rsp+0A50h+var_A00], rcx
0x180021d04  mov     rcx, [rbp+950h+arg_20]
0x180021d0b  mov     [rbp+950h+var_960], rcx
0x180021d0f  test    r9, r9
0x180021d12  jnz     loc_180022543
0x180021d18  mov     [rsp+0A50h+var_A08], 0FFFFFFFFFFFFFFFFh
0x180021d21  mov     rbx, [r12+30h]
0x180021d26  call    cs:__imp_GetCurrentThreadId
0x180021d2c  mov     rcx, [rbp+958h]; this
0x180021d33  cmp     [rbx+0Ch], eax
0x180021d36  jnz     loc_180022555
0x180021d3c  mov     rdi, [rbx+18h]
0x180021d40  mov     r14d, [rbx+20h]
0x180021d44  xor     sil, sil
0x180021d47  mov     rcx, rdi; unsigned __int64
0x180021d4a  call    ?HrJetBeginTransaction@@YAJ_K@Z; HrJetBeginTransaction(unsigned __int64)
0x180021d4f  mov     ebx, eax
0x180021d51  test    eax, eax
0x180021d53  jns     short loc_180021D99
0x180021d55  mov     r8d, ebx; int
0x180021d58  lea     rdx, [rsp+0A50h+var_A08]; unsigned __int64 *
0x180021d5d  mov     rcx, rdi; unsigned __int64
0x180021d60  call    ?CloseTableIfNecessary@@YAJ_KPEA_KJ@Z; CloseTableIfNecessary(unsigned __int64,unsigned __int64 *,long)
0x180021d65  mov     r8d, ebx; int
0x180021d68  movzx   edx, sil; bool
0x180021d6c  mov     rcx, rdi; unsigned __int64
0x180021d6f  call    ?RollbackIfNecessary@@YAJ_K_NJ@Z; RollbackIfNecessary(unsigned __int64,bool,long)
0x180021d74  mov     eax, ebx
0x180021d76  mov     rcx, [rbp+950h+var_50]
0x180021d7d  xor     rcx, rsp; StackCookie
0x180021d80  call    __security_check_cookie
0x180021d85  add     rsp, 0A18h
0x180021d8c  pop     r15
0x180021d8e  pop     r14
0x180021d90  pop     r13
0x180021d92  pop     r12
0x180021d94  pop     rdi
0x180021d95  pop     rsi
0x180021d96  pop     rbx
0x180021d97  pop     rbp
0x180021d98  retn
0x180021d99  mov     sil, 1
0x180021d9c  lea     r8, [r12+38h]; unsigned __int16 *
0x180021da1  lea     rax, [rsp+0A50h+var_A08]
0x180021da6  mov     [rsp+0A50h+var_A20], rax; JET_TABLEID *
0x180021dab  mov     [rsp+0A50h+var_A28], 0; JET_GRBIT
0x180021db3  mov     edx, r14d; unsigned int
0x180021db6  mov     rcx, rdi; unsigned __int64
0x180021db9  call    ?HrJetOpenTable@@YAJ_KKPEBGPEBXKKPEA_K@Z; HrJetOpenTable(unsigned __int64,ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x180021dbe  mov     ebx, eax
0x180021dc0  test    eax, eax
0x180021dc2  js      short loc_180021D55
0x180021dc4  mov     r14d, [r13+0]
0x180021dc8  mov     [rsp+0A50h+ppstm], 0
0x180021dd1  mov     ebx, 80070057h
0x180021dd6  test    r14, r14
0x180021dd9  jz      loc_180021EA4
0x180021ddf  mov     r12, [r13+8]
0x180021de3  test    r12, r12
0x180021de6  jz      loc_180021E9F
0x180021dec  mov     edx, r14d; dwBytes
0x180021def  mov     ecx, 2; uFlags
0x180021df4  call    cs:__imp_GlobalAlloc
0x180021dfa  mov     rsi, rax
0x180021dfd  test    rax, rax
0x180021e00  jz      loc_180022521
0x180021e06  mov     rcx, rsi; hMem
0x180021e09  call    cs:__imp_GlobalLock
0x180021e0f  mov     r15, rax
0x180021e12  test    rax, rax
0x180021e15  jz      short loc_180021E7D
0x180021e17  test    r15, r15
0x180021e1a  jz      loc_1800220D9
0x180021e20  mov     r8, r14; Size
0x180021e23  mov     rdx, r12; Src
0x180021e26  mov     rcx, r15; void *
0x180021e29  call    memcpy_0
0x180021e2e  mov     rcx, rsi; hMem
0x180021e31  call    cs:__imp_GlobalUnlock
0x180021e37  test    eax, eax
0x180021e39  jnz     short loc_180021E59
0x180021e3b  call    cs:__imp_GetLastError
0x180021e41  test    eax, eax
0x180021e43  jz      short loc_180021E59
0x180021e45  call    cs:__imp_GetLastError
0x180021e4b  mov     ebx, eax
0x180021e4d  test    eax, eax
0x180021e4f  jg      loc_180022575
0x180021e55  test    ebx, ebx
0x180021e57  js      short loc_180021E91
0x180021e59  lea     r8, [rsp+0A50h+ppstm]; ppstm
0x180021e5e  mov     edx, 1; fDeleteOnRelease
0x180021e63  mov     rcx, rsi; hGlobal
0x180021e66  call    cs:__imp_CreateStreamOnHGlobal
0x180021e6c  mov     ebx, eax
0x180021e6e  test    eax, eax
0x180021e70  jns     short loc_180021E9A
0x180021e72  mov     [rsp+0A50h+ppstm], 0
0x180021e7b  jmp     short loc_180021E91
0x180021e7d  call    cs:__imp_GetLastError
0x180021e83  mov     ebx, eax
0x180021e85  test    eax, eax
0x180021e87  jg      loc_180022567
0x180021e8d  test    ebx, ebx
0x180021e8f  jns     short loc_180021E17
0x180021e91  test    rsi, rsi
0x180021e94  jnz     loc_180022583
0x180021e9a  mov     r15, [rsp+0A50h+Src]
0x180021e9f  mov     r12, [rsp+0A50h+var_A00]
0x180021ea4  test    ebx, ebx
0x180021ea6  js      loc_180022377
0x180021eac  xorps   xmm0, xmm0
0x180021eaf  xor     eax, eax
0x180021eb1  movups  [rsp+0A50h+var_9F0], xmm0
0x180021eb6  mov     [rsp+0A50h+var_9E0], rax
0x180021ebb  xorps   xmm1, xmm1
0x180021ebe  movups  [rsp+0A50h+var_9D8], xmm1
0x180021ec3  mov     [rbp+950h+var_9C8], rax
0x180021ec7  test    r15, r15
0x180021eca  jz      loc_180022591
0x180021ed0  mov     rdx, r15
0x180021ed3  lea     rcx, [rbp+950h+var_9A0]
0x180021ed7  call    ?CloneFrom@?$SmartRpcStruct@U__MIDL_RPCIndexedDB_0001@@UIndexedDbKeyTrait@IndexedDbRpcHelpers@@@@SA?AV1@AEBU__MIDL_RPCIndexedDB_0001@@@Z; SmartRpcStruct<__MIDL_RPCIndexedDB_0001,IndexedDbRpcHelpers::IndexedDbKeyTrait>::CloneFrom(__MIDL_RPCIndexedDB_0001 const &)
0x180021edc  mov     esi, [rax]
0x180021ede  mov     dword ptr [rbp+950h+var_9C0], esi
0x180021ee1  mov     ebx, [rax+4]
0x180021ee4  mov     dword ptr [rbp+950h+var_9C0+4], ebx
0x180021ee7  mov     r14, [rax+8]
0x180021eeb  mov     qword ptr [rbp+950h+var_9C0+8], r14
0x180021eef  mov     rcx, [rax+10h]
0x180021ef3  mov     [rsp+0A50h+Src], rcx
0x180021ef8  mov     [rbp+950h+var_9B0], rcx
0x180021efc  xorps   xmm0, xmm0
0x180021eff  xor     edx, edx
0x180021f01  movups  xmmword ptr [rax], xmm0
0x180021f04  mov     [rax+10h], rdx
0x180021f08  cmp     dword ptr [rsp+0A50h+var_9F0], 4
0x180021f0d  jnz     short loc_180021F1D
0x180021f0f  mov     rax, [rsp+0A50h+var_9E0]
0x180021f14  test    rax, rax
0x180021f17  jnz     loc_1800220BA
0x180021f1d  mov     r15d, r14d
0x180021f20  xorps   xmm0, xmm0
0x180021f23  xor     eax, eax
0x180021f25  movups  [rsp+0A50h+var_9F0], xmm0
0x180021f2a  mov     [rsp+0A50h+var_9E0], rax
0x180021f2f  xorps   xmm1, xmm1
0x180021f32  movups  [rsp+0A50h+var_9D8], xmm1
0x180021f37  mov     [rbp+950h+var_9C8], rax
0x180021f3b  test    esi, esi
0x180021f3d  jz      short loc_180021FAA
0x180021f3f  mov     [rbp+950h+var_950], r14
0x180021f43  cmp     esi, 4
0x180021f46  jnz     loc_1800224D9
0x180021f4c  movups  [rbp+950h+var_970], xmm0
0x180021f50  test    r14d, r14d
0x180021f53  jz      loc_180022096
0x180021f59  mov     r14d, r14d
0x180021f5c  add     r14, r14
0x180021f5f  mov     rcx, r14; size
0x180021f62  call    MIDL_user_allocate
0x180021f67  mov     r12, rax
0x180021f6a  mov     rcx, [rbp+958h]; this
0x180021f71  test    rax, rax
0x180021f74  jz      loc_18002260E
0x180021f7a  mov     r8, r14; Size
0x180021f7d  mov     rdx, [rsp+0A50h+Src]; Src
0x180021f82  mov     rcx, rax; void *
0x180021f85  call    memcpy_0
0x180021f8a  mov     dword ptr [rbp+950h+var_950], r15d
0x180021f8e  mov     eax, dword ptr [rbp+950h+var_970+4]
0x180021f91  mov     dword ptr [rbp+950h+var_950+4], eax
0x180021f94  mov     r14, [rbp+950h+var_950]
0x180021f98  mov     dword ptr [rsp+0A50h+var_9F0], esi
0x180021f9c  mov     dword ptr [rsp+0A50h+var_9F0+4], ebx
0x180021fa0  mov     qword ptr [rsp+0A50h+var_9F0+8], r14
0x180021fa5  mov     [rsp+0A50h+var_9E0], r12
0x180021faa  cmp     dword ptr [rsp+0A50h+var_9F0], 1
0x180021faf  jz      loc_180022620
0x180021fb5  cmp     esi, 4
0x180021fb8  jz      loc_18002209E
0x180021fbe  cmp     dword ptr [rbp+950h+var_9A0], 4
0x180021fc2  jz      loc_1800220AC
0x180021fc8  mov     r12, [rsp+0A50h+var_A00]
0x180021fcd  xor     r15d, r15d
0x180021fd0  add     r12, 18h
0x180021fd4  mov     rdx, [r12]
0x180021fd8  mov     [rbp+950h+var_8C0.columnid], r15d
0x180021fdf  mov     [rbp+950h+var_8C0.pvData], r15
0x180021fe6  mov     qword ptr [rbp+950h+var_8C0.cbData], 0
0x180021ff1  mov     [rbp+950h+var_8C0.ibLongValue], r15d
0x180021ff8  mov     qword ptr [rbp+950h+var_8C0.itagSequence], 1
0x180022003  mov     [rbp+950h+var_898], r15d
0x18002200a  mov     [rbp+950h+var_890], r15
0x180022011  mov     [rbp+950h+var_888], 0
0x18002201c  mov     [rbp+950h+var_880], r15d
0x180022023  mov     [rbp+950h+var_87C], 1
0x18002202e  mov     [rbp+950h+var_870], r15d
0x180022035  mov     [rbp+950h+var_868], r15
0x18002203c  mov     [rbp+950h+var_860], 0
0x180022047  mov     [rbp+950h+var_858], r15d
0x18002204e  mov     [rbp+950h+var_854], 1
0x180022059  mov     [rbp+950h+var_848], r15d
0x180022060  mov     [rbp+950h+var_840], r15
0x180022067  mov     [rbp+950h+var_838], 0
0x180022072  mov     [rbp+950h+var_830], r15d
0x180022079  mov     [rbp+950h+var_82C], 1
0x180022084  cmp     dword ptr [rsp+0A50h+var_9D8], 0
0x180022089  jz      short loc_1800220EF
0x18002208b  mov     r8d, dword ptr [rsp+0A50h+var_9D8]
0x180022090  lea     rcx, [rbp+950h+var_9D8+8]
0x180022094  jmp     short loc_1800220F9
0x180022096  xor     r12d, r12d
0x180022099  jmp     loc_180021F8A
0x18002209e  lea     rcx, [rbp+950h+var_9C0+8]; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *
0x1800220a2  call    ?Free@StringBufferTrait@IndexedDbRpcHelpers@@SAXAEAU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@@Z; IndexedDbRpcHelpers::StringBufferTrait::Free(__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 &)
0x1800220a7  jmp     loc_180021FBE
0x1800220ac  lea     rcx, [rbp+950h+var_9A0+8]; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *
0x1800220b0  call    ?Free@StringBufferTrait@IndexedDbRpcHelpers@@SAXAEAU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@@Z; IndexedDbRpcHelpers::StringBufferTrait::Free(__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 &)
0x1800220b5  jmp     loc_180021FC8
0x1800220ba  mov     qword ptr [rbp+950h+var_970], rax
0x1800220be  lea     rcx, [rbp+950h+var_970]
0x1800220c2  call    WxFreeHeapEx
0x1800220c7  xorps   xmm0, xmm0
0x1800220ca  movups  [rsp+0A50h+var_9F0+8], xmm0
0x1800220cf  mov     rcx, [rsp+0A50h+Src]
0x1800220d4  jmp     loc_180021F1D
0x1800220d9  call    cs:__imp__o__errno
0x1800220df  mov     dword ptr [rax], 16h
0x1800220e5  call    _invalid_parameter_noinfo
0x1800220ea  jmp     loc_180021E2E
0x1800220ef  mov     r8d, dword ptr [rsp+0A50h+var_9F0]
0x1800220f4  lea     rcx, [rsp+0A50h+var_9F0+8]; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *
0x1800220f9  cmp     r8d, 4
0x1800220fd  jnz     loc_18002263C
0x180022103  mov     eax, [rdx+0DCh]
0x180022109  mov     [rbp+950h+var_8C0.columnid], eax
0x18002210f  mov     rax, [rcx+8]
0x180022113  mov     [rbp+950h+var_8C0.pvData], rax
0x18002211a  call    ?StringBufferByteLen@@YA_KPEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@@Z; StringBufferByteLen(__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const *)
0x18002211f  mov     [rbp+950h+var_8C0.cbData], eax
0x180022125  mov     eax, [rdx+2B0h]
0x18002212b  mov     [rbp+950h+var_898], eax
0x180022131  lea     rax, [rsp+0A50h+var_9F0]
0x180022136  mov     [rbp+950h+var_890], rax
0x18002213d  mov     dword ptr [rbp+950h+var_888], 4
0x180022147  mov     eax, [rdx+3CCh]
0x18002214d  mov     [rbp+950h+var_870], eax
0x180022153  mov     rax, [r13+8]
0x180022157  mov     [rbp+950h+var_868], rax
0x18002215e  mov     eax, [r13+0]
0x180022162  mov     dword ptr [rbp+950h+var_860], eax
0x180022168  xor     r8d, r8d; unsigned int
0x18002216b  mov     rdx, [rsp+0A50h+var_A08]; unsigned __int64
0x180022170  mov     rcx, rdi; unsigned __int64
0x180022173  call    ?HrJetPrepareUpdate@@YAJ_K0K@Z; HrJetPrepareUpdate(unsigned __int64,unsigned __int64,ulong)
0x180022178  mov     ebx, eax
0x18002217a  test    eax, eax
0x18002217c  js      loc_1800226AB
0x180022182  mov     r9d, 3; unsigned int
0x180022188  lea     r8, [rbp+950h+var_8C0]; struct JET_SETCOLUMN *
0x18002218f  mov     rdx, [rsp+0A50h+var_A08]; unsigned __int64
0x180022194  mov     rcx, rdi; unsigned __int64
0x180022197  call    ?HrJetSetColumns@@YAJ_K0PEAUJET_SETCOLUMN@@K@Z; HrJetSetColumns(unsigned __int64,unsigned __int64,JET_SETCOLUMN *,ulong)
0x18002219c  mov     ebx, eax
0x18002219e  test    eax, eax
0x1800221a0  jns     loc_18002226A
0x1800221a6  mov     r14b, 1
0x1800221a9  mov     r8d, 3; unsigned int
0x1800221af  mov     rdx, [rsp+0A50h+var_A08]; unsigned __int64
0x1800221b4  mov     rcx, rdi; unsigned __int64
0x1800221b7  call    ?HrJetPrepareUpdate@@YAJ_K0K@Z; HrJetPrepareUpdate(unsigned __int64,unsigned __int64,ulong)
0x1800221bc  jmp     short loc_1800221FE
0x1800221be  xor     edx, edx; Val
0x1800221c0  mov     r8d, 40h ; '@'; Size
0x1800221c6  lea     rcx, [rbp+950h+var_900]; void *
0x1800221ca  call    memset_0
0x1800221cf  xor     r9d, r9d; unsigned int
0x1800221d2  lea     r8, [rbp+950h+var_900]; struct JET_RECSIZE *
0x1800221d6  mov     rdx, [rsp+0A50h+var_A08]; unsigned __int64
0x1800221db  mov     rcx, rdi; unsigned __int64
0x1800221de  call    ?HrJetGetRecordSize@@YAJ_K0PEAUJET_RECSIZE@@K@Z; HrJetGetRecordSize(unsigned __int64,unsigned __int64,JET_RECSIZE *,ulong)
  ... truncated ...
```
