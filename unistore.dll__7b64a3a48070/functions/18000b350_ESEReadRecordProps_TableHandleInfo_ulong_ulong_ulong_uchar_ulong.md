# ESEReadRecordProps(TableHandleInfo *,ulong,ulong *,ulong *,uchar * *,ulong *)

- ea: `0x18000b350`
- end: `0x18000b9a3`
- name: `?ESEReadRecordProps@@YAJPEAUTableHandleInfo@@KPEAK1PEAPEAE1@Z`
- size: `1619`
- prototype: `__int64 __fastcall(struct TableHandleInfo *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `8`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180003598`
- `0x180008af0`
- `0x180009b40`
- `0x180019c3c`
- `0x1800448a0`
- `0x180054754`
- `0x180058d40`
- `0x1800ab6c4`

## callees

- `0x180004464`
- `0x1800068f0`
- `0x18000b350`
- `0x18000b9d0`
- `0x18000c610`
- `0x18000f530`
- `0x18001363c`
- `0x18001abf4`
- `0x180045990`
- `0x180051140`
- `0x18005430c`
- `0x180066290`
- `0x180067c1c`
- `0x18006f180`
- `0x180078a40`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b83f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b870`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b83f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b870`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b46f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b46f`
- `ESENT!JetEnumerateColumns` at `0x18000b563`
- `ESENT!JetEnumerateColumns` at `0x18000b563`
- `ESENT!JetGetErrorInfoW` at `0x18000b5e8`
- `ESENT!JetGetErrorInfoW` at `0x18000b5e8`
- `UserDataPlatformHelperUtil!JetReallocMethod` at `0x18000b517`
- `UserDataPlatformHelperUtil!FreeEnumColumn` at `0x18000b6e7`
- `UserDataPlatformHelperUtil!FreeEnumColumn` at `0x18000b6e7`

## string_xrefs

- `0x18000b91d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000b955`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000b3ed`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000b631`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000b732`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000b7c5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000b802`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000b978`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall ESEReadRecordProps(
        struct TableHandleInfo *a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  JET_SESID v7; // r10
  JET_TABLEID v9; // rdx
  __int64 v12; // rdx
  unsigned int *v13; // r8
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rbx
  JET_ENUMCOLUMNID *v17; // rdi
  __int64 i; // rbx
  unsigned int v19; // eax
  RTL_SRWLOCK *v20; // r9
  unsigned int v21; // esi
  __int64 v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // r9
  RTL_SRWLOCK *v25; // rdx
  unsigned __int64 v26; // r8
  RTL_SRWLOCK v27; // rcx
  PVOID v28; // r9
  unsigned int v29; // edi
  JET_ENUMCOLUMNID *v30; // rsi
  JET_ERR v31; // eax
  int v32; // ebx
  int HresultFromJetError; // ebx
  unsigned int v34; // edx
  unsigned int v35; // r10d
  __int64 v36; // r9
  __int64 v37; // r9
  int v38; // eax
  __int64 v39; // r10
  __int64 j; // rcx
  __int64 v41; // xmm6_8
  __int64 v42; // rax
  JET_ENUMCOLUMNID *v43; // rax
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  unsigned int cEnumColumnId; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v48; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int pcEnumColumn; // [rsp+5Ch] [rbp-A4h] BYREF
  JET_ENUMCOLUMN *prgEnumColumn; // [rsp+60h] [rbp-A0h] BYREF
  JET_ENUMCOLUMNID *rgEnumColumnId; // [rsp+68h] [rbp-98h] BYREF
  JET_ENUMCOLUMNID *v52; // [rsp+70h] [rbp-90h]
  JET_ENUMCOLUMN **p_prgEnumColumn; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *p_pcEnumColumn; // [rsp+88h] [rbp-78h]
  char v55; // [rsp+90h] [rbp-70h]
  unsigned int *v56; // [rsp+98h] [rbp-68h]
  unsigned __int8 **v57; // [rsp+A0h] [rbp-60h]
  JET_TABLEID tableid; // [rsp+A8h] [rbp-58h]
  JET_SESID sesid; // [rsp+B0h] [rbp-50h]
  int v60; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v61; // [rsp+C4h] [rbp-3Ch]
  __int128 v62; // [rsp+D4h] [rbp-2Ch]
  __int128 v63; // [rsp+E4h] [rbp-1Ch]
  __int128 v64; // [rsp+F4h] [rbp-Ch]
  __int128 v65; // [rsp+104h] [rbp+4h]
  __int128 v66; // [rsp+114h] [rbp+14h]
  __int128 v67; // [rsp+124h] [rbp+24h]
  __int128 v68; // [rsp+134h] [rbp+34h]
  __int128 v69; // [rsp+144h] [rbp+44h]
  int v70; // [rsp+154h] [rbp+54h]

  v7 = *((_QWORD *)a1 + 1);
  v9 = *((_QWORD *)a1 + 2);
  v57 = a5;
  v56 = a6;
  sesid = v7;
  tableid = v9;
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &rgEnumColumnId,
    v9,
    a3);
  v14 = *v13;
  v15 = v52 - rgEnumColumnId;
  if ( v14 <= v15 )
  {
    v17 = &rgEnumColumnId[v14];
  }
  else
  {
    if ( !(unsigned __int8)utl::vector<JET_ENUMCOLUMNID,utl::allocator<JET_ENUMCOLUMNID>>::reserve(
                             &rgEnumColumnId,
                             (unsigned int)v14) )
    {
      Log_UnistoreHREvent_0(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        2501);
      utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&rgEnumColumnId);
      return 2147942414LL;
    }
    v44 = 0;
    v12 = v14 - v15;
    while ( v44 != v12 )
    {
      v43 = &v52[v44++];
      *v43 = 0;
    }
    v17 = &rgEnumColumnId[v14];
  }
  v52 = v17;
  v48 = 0;
  cEnumColumnId = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v19 = *a3;
    v20 = &g_columnIdMapping;
    if ( (unsigned int)i >= *a3 )
      break;
    v21 = a4[i];
    p_prgEnumColumn = 0;
    LODWORD(p_pcEnumColumn) = 0;
    if ( (a2 & 2) != 0 && (unsigned int)DPHelper::DoesPropertyRequireProtection((DPHelper *)v21, v12) )
    {
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= 0x26 )
        {
          Log_UnistoreHREvent_0(
            2147942402LL,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            2513);
          utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&rgEnumColumnId);
          return 2147942402LL;
        }
        if ( *(_DWORD *)(8 * j + v39) == v21 )
          break;
      }
      v21 = *(_DWORD *)(8 * j + v39 + 4);
    }
    v22 = *(int *)a1;
    AcquireSRWLockShared(v20);
    if ( dword_18010D248 )
    {
      v23 = v22 + 4 * v22 + 1;
      v24 = *((_QWORD *)&g_columnIdMapping + v23 + 2);
      v25 = &g_columnIdMapping + v23;
      if ( v24 )
      {
        v26 = (unsigned __int64)v21 >> 16;
        v27.Ptr = *(PVOID *)(v24 + 16 * (v26 & ((8LL << LOBYTE(v25[4].Ptr)) - 1)));
        if ( v27.Ptr )
        {
          v28 = **(PVOID **)(v24 + 16 * (v26 & ((8LL << LOBYTE(v25[4].Ptr)) - 1)) + 8);
          while ( v27.Ptr != v28 )
          {
            if ( *((_QWORD *)v27.Ptr + 2) >= v26 )
            {
              if ( *((_QWORD *)v27.Ptr + 2) > v26 )
                break;
              if ( v21 == *((_DWORD *)v27.Ptr + 6) )
              {
                if ( v27.Ptr == v25 )
                  break;
                v41 = *(_QWORD *)((char *)v27.Ptr + 28);
                LODWORD(p_pcEnumColumn) = *((_DWORD *)v27.Ptr + 9);
                ReleaseSRWLockShared(&g_columnIdMapping);
                v42 = cEnumColumnId;
                LODWORD(v12) = ++cEnumColumnId;
                *(_QWORD *)&rgEnumColumnId[v42].columnid = (unsigned int)v41;
                goto LABEL_55;
              }
            }
            v27.Ptr = *(PVOID *)v27.Ptr;
          }
        }
      }
    }
    ReleaseSRWLockShared(&g_columnIdMapping);
    ++v48;
LABEL_55:
    ;
  }
  v29 = cEnumColumnId;
  prgEnumColumn = 0;
  pcEnumColumn = 0;
  if ( cEnumColumnId || !v19 )
  {
    v30 = rgEnumColumnId;
    v31 = JetEnumerateColumns(
            sesid,
            tableid,
            cEnumColumnId,
            rgEnumColumnId,
            &pcEnumColumn,
            &prgEnumColumn,
            JetReallocMethod,
            0,
            0xA00000u,
            0x80000u);
    v32 = v31;
    if ( g_fInProc && !dword_18010D924 )
    {
      if ( v31 != -1414 )
      {
        cEnumColumnId = v31;
        if ( v31 >= 0 )
          goto LABEL_32;
        v60 = 152;
        v70 = 0;
        v61 = 0;
        v62 = 0;
        v63 = 0;
        v64 = 0;
        v65 = 0;
        v66 = 0;
        v67 = 0;
        v68 = 0;
        v69 = 0;
        if ( (int)JetGetErrorInfoW(&cEnumColumnId, &v60, 152, 1, 0) < 0 )
          goto LABEL_28;
        if ( DWORD1(v61) != 10 )
        {
          if ( DWORD1(v61) == 11 )
          {
            v48 = cEnumColumnId;
            UnistoreTelemetry::JetInconsistentError<unsigned long>(&v48);
          }
          else if ( DWORD1(v61) == 12 )
          {
            v48 = cEnumColumnId;
            UnistoreTelemetry::JetFragmentationError<unsigned long>(&v48);
          }
          goto LABEL_28;
        }
        if ( cEnumColumnId == -1414 )
        {
LABEL_28:
          HresultFromJetError = MakeHresultFromJetError(v32);
          Log_UnistoreHREvent_0(
            (unsigned int)HresultFromJetError,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            2543);
          goto LABEL_29;
        }
      }
      v45 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v32);
      if ( v45 >= 0 )
      {
        cEnumColumnId = v32;
        UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&cEnumColumnId);
        if ( (unsigned int)IsJetCorruptionError(v32) )
        {
          Log_AssertionEvent(
            v46,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            109);
          __int2c();
        }
      }
      else
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v45,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          102);
      }
    }
    if ( v32 >= 0 )
      goto LABEL_32;
    goto LABEL_28;
  }
  v38 = UnistoreReseek(a1);
  HresultFromJetError = v38;
  if ( v38 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v38,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      2549);
    v30 = rgEnumColumnId;
LABEL_29:
    if ( v30 != (JET_ENUMCOLUMNID *)-1LL )
      operator delete(v30);
    return (unsigned int)HresultFromJetError;
  }
  v30 = rgEnumColumnId;
LABEL_32:
  v34 = *a3;
  p_prgEnumColumn = &prgEnumColumn;
  p_pcEnumColumn = &pcEnumColumn;
  v55 = 1;
  if ( !v34 )
    goto LABEL_35;
  if ( pcEnumColumn != v29 )
  {
    v36 = 2556;
    goto LABEL_42;
  }
  if ( v29 + v48 != v34 )
  {
    v36 = 2557;
LABEL_42:
    Log_UnistoreHREvent_0(
      2147549183LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      v36);
    tlx::_UndoSolo__lambda_9c9b0fa7062f2af27f78bbb345476e79___::__UndoSolo__lambda_9c9b0fa7062f2af27f78bbb345476e79___(&p_prgEnumColumn);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&rgEnumColumnId);
    return 2147549183LL;
  }
LABEL_35:
  v35 = *(_DWORD *)a1;
  if ( (a2 & 1) != 0 )
  {
    HresultFromJetError = MapAndConvertPropsEx(v35, a3, a4, pcEnumColumn, prgEnumColumn, v57, v56);
    if ( HresultFromJetError >= 0 )
      goto LABEL_37;
    v37 = 2569;
LABEL_72:
    Log_UnistoreHREvent_0(
      (unsigned int)HresultFromJetError,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      v37);
    tlx::_UndoSolo__lambda_9c9b0fa7062f2af27f78bbb345476e79___::__UndoSolo__lambda_9c9b0fa7062f2af27f78bbb345476e79___(&p_prgEnumColumn);
    utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&rgEnumColumnId);
    return (unsigned int)HresultFromJetError;
  }
  HresultFromJetError = MapAndConvertProps(v35, a2, a3, a4, pcEnumColumn, prgEnumColumn, v57, v56);
  if ( HresultFromJetError < 0 )
  {
    v37 = 2581;
    goto LABEL_72;
  }
LABEL_37:
  FreeEnumColumn(prgEnumColumn, pcEnumColumn);
  if ( v30 != (JET_ENUMCOLUMNID *)-1LL )
    operator delete(v30);
  return 0;
}

```

## disassembly

```asm
0x18000b350  push    rbp
0x18000b352  push    rbx
0x18000b353  push    rsi
0x18000b354  push    rdi
0x18000b355  push    r12
0x18000b357  push    r13
0x18000b359  push    r14
0x18000b35b  push    r15
0x18000b35d  lea     rbp, [rsp-88h]
0x18000b365  sub     rsp, 188h
0x18000b36c  mov     rax, cs:__security_cookie
0x18000b373  xor     rax, rsp
0x18000b376  mov     [rbp+0C0h+var_60], rax
0x18000b37a  mov     rax, [rbp+0C0h+arg_20]
0x18000b381  mov     r12d, edx
0x18000b384  mov     r10, [rcx+8]
0x18000b388  mov     r15, rcx
0x18000b38b  mov     rdx, [rcx+10h]
0x18000b38f  mov     r13, r9
0x18000b392  mov     [rbp+0C0h+var_120], rax
0x18000b396  lea     rcx, [rsp+1C0h+rgEnumColumnId]
0x18000b39b  mov     rax, [rbp+0C0h+arg_28]
0x18000b3a2  mov     r14, r8
0x18000b3a5  mov     [rbp+0C0h+var_128], rax
0x18000b3a9  mov     [rbp+0C0h+sesid], r10
0x18000b3ad  mov     [rbp+0C0h+tableid], rdx
0x18000b3b1  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x18000b3b6  mov     rbx, [rsp+1C0h+var_150]
0x18000b3bb  mov     rsi, [rsp+1C0h+rgEnumColumnId]
0x18000b3c0  mov     edi, [r8]
0x18000b3c3  sub     rbx, rsi
0x18000b3c6  sar     rbx, 4
0x18000b3ca  cmp     rdi, rbx
0x18000b3cd  jbe     loc_18000B89C
0x18000b3d3  mov     edx, edi
0x18000b3d5  lea     rcx, [rsp+1C0h+rgEnumColumnId]
0x18000b3da  call    ?reserve@?$vector@UJET_ENUMCOLUMNID@@V?$allocator@UJET_ENUMCOLUMNID@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<JET_ENUMCOLUMNID,utl::allocator<JET_ENUMCOLUMNID>>::reserve(unsigned __int64)
0x18000b3df  test    al, al
0x18000b3e1  jnz     loc_18000B8A8
0x18000b3e7  mov     r9d, 9C5h
0x18000b3ed  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b3f4  xor     edx, edx
0x18000b3f6  mov     ecx, 8007000Eh
0x18000b3fb  call    Log_UnistoreHREvent_0
0x18000b400  lea     rcx, [rsp+1C0h+rgEnumColumnId]
0x18000b405  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x18000b40a  mov     eax, 8007000Eh
0x18000b40f  jmp     loc_18000B70C
0x18000b414  shl     rdi, 4
0x18000b418  add     rdi, [rsp+1C0h+rgEnumColumnId]
0x18000b41d  xor     eax, eax
0x18000b41f  mov     [rsp+1C0h+var_150], rdi
0x18000b424  xor     edi, edi
0x18000b426  mov     [rsp+1C0h+var_168], eax
0x18000b42a  mov     [rsp+1C0h+cEnumColumnId], edi
0x18000b42e  xor     ebx, ebx
0x18000b430  movaps  [rsp+1C0h+var_50], xmm6
0x18000b438  mov     eax, [r14]
0x18000b43b  lea     r9, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x18000b442  lea     r10, ?c_rgUSOriginalToProtectedPropMap@@3QBUUSOriginalToProtectedPropMap@@B; USOriginalToProtectedPropMap const near * const c_rgUSOriginalToProtectedPropMap
0x18000b449  cmp     ebx, eax
0x18000b44b  jnb     loc_18000B4FA
0x18000b451  mov     esi, [r13+rbx*4+0]
0x18000b456  xor     eax, eax
0x18000b458  mov     [rbp+0C0h+var_140], rax
0x18000b45c  mov     dword ptr [rbp+0C0h+var_138], eax
0x18000b45f  test    r12b, 2
0x18000b463  jnz     loc_18000B7E2
0x18000b469  movsxd  rdi, dword ptr [r15]
0x18000b46c  mov     rcx, r9; SRWLock
0x18000b46f  call    cs:__imp_AcquireSRWLockShared
0x18000b475  cmp     cs:dword_18010D248, 0
0x18000b47c  lea     r10, ?g_columnIdMapping@@3VColumnIdMappings@@A; ColumnIdMappings g_columnIdMapping
0x18000b483  jz      loc_18000B86D
0x18000b489  lea     rdx, ds:1[rdi*4]
0x18000b491  add     rdx, rdi
0x18000b494  mov     r9, [r10+rdx*8+10h]
0x18000b499  lea     rdx, [r10+rdx*8]
0x18000b49d  test    r9, r9
0x18000b4a0  jz      loc_18000B86D
0x18000b4a6  movzx   ecx, byte ptr [rdx+20h]
0x18000b4aa  mov     eax, 8
0x18000b4af  shl     rax, cl
0x18000b4b2  dec     rax
0x18000b4b5  mov     r8d, esi
0x18000b4b8  shr     r8, 10h
0x18000b4bc  and     rax, r8
0x18000b4bf  add     rax, rax
0x18000b4c2  mov     rcx, [r9+rax*8]
0x18000b4c6  test    rcx, rcx
0x18000b4c9  jz      loc_18000B86D
0x18000b4cf  mov     rax, [r9+rax*8+8]
0x18000b4d4  mov     r9, [rax]
0x18000b4d7  cmp     rcx, r9
0x18000b4da  jz      loc_18000B86D
0x18000b4e0  cmp     [rcx+10h], r8
0x18000b4e4  jb      short loc_18000B4F5
0x18000b4e6  ja      loc_18000B86D
0x18000b4ec  cmp     esi, [rcx+18h]
0x18000b4ef  jz      loc_18000B82C
0x18000b4f5  mov     rcx, [rcx]
0x18000b4f8  jmp     short loc_18000B4D7
0x18000b4fa  mov     edi, [rsp+1C0h+cEnumColumnId]
0x18000b4fe  mov     [rsp+1C0h+var_160], 0
0x18000b507  mov     [rsp+1C0h+var_164], 0
0x18000b50f  test    edi, edi
0x18000b511  jz      loc_18000B7A5
0x18000b517  mov     rax, cs:__imp_JetReallocMethod
0x18000b51e  mov     r8d, edi; cEnumColumnId
0x18000b521  mov     rsi, [rsp+1C0h+rgEnumColumnId]
0x18000b526  mov     rdx, [rbp+0C0h+tableid]; tableid
0x18000b52a  mov     r9, rsi; rgEnumColumnId
0x18000b52d  mov     rcx, [rbp+0C0h+sesid]; sesid
0x18000b531  mov     [rsp+1C0h+grbit], 80000h; grbit
0x18000b539  mov     [rsp+1C0h+cbDataMost], 0A00000h; cbDataMost
0x18000b541  mov     [rsp+1C0h+pvReallocContext], 0; pvReallocContext
0x18000b54a  mov     [rsp+1C0h+pfnRealloc], rax; pfnRealloc
0x18000b54f  lea     rax, [rsp+1C0h+var_160]
0x18000b554  mov     [rsp+1C0h+prgEnumColumn], rax; prgEnumColumn
0x18000b559  lea     rax, [rsp+1C0h+var_164]
0x18000b55e  mov     [rsp+1C0h+pcEnumColumn], rax; pcEnumColumn
0x18000b563  call    cs:__imp_JetEnumerateColumns
0x18000b569  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x18000b570  mov     ebx, eax
0x18000b572  jz      loc_18000B620
0x18000b578  cmp     cs:dword_18010D924, 0
0x18000b57f  jnz     loc_18000B620
0x18000b585  cmp     eax, 0FFFFFA7Ah
0x18000b58a  jz      loc_18000B8F6
0x18000b590  mov     [rsp+1C0h+cEnumColumnId], eax
0x18000b594  test    eax, eax
0x18000b596  jns     loc_18000B65F
0x18000b59c  xorps   xmm0, xmm0
0x18000b59f  mov     [rbp+0C0h+var_100], 98h
0x18000b5a6  xor     eax, eax
0x18000b5a8  lea     rdx, [rbp+0C0h+var_100]
0x18000b5ac  mov     r9d, 1
0x18000b5b2  mov     [rbp+0C0h+var_6C], eax
0x18000b5b5  mov     r8d, 98h
0x18000b5bb  mov     dword ptr [rsp+1C0h+pcEnumColumn], eax
0x18000b5bf  lea     rcx, [rsp+1C0h+cEnumColumnId]
0x18000b5c4  movups  [rbp+0C0h+var_FC], xmm0
0x18000b5c8  movups  [rbp+0C0h+var_EC], xmm0
0x18000b5cc  movups  [rbp+0C0h+var_DC], xmm0
0x18000b5d0  movups  [rbp+0C0h+var_CC], xmm0
0x18000b5d4  movups  [rbp+0C0h+var_BC], xmm0
0x18000b5d8  movups  [rbp+0C0h+var_AC], xmm0
0x18000b5dc  movups  [rbp+0C0h+var_9C], xmm0
0x18000b5e0  movups  [rbp+0C0h+var_8C], xmm0
0x18000b5e4  movups  [rbp+0C0h+var_7C], xmm0
0x18000b5e8  call    cs:__imp_JetGetErrorInfoW
0x18000b5ee  test    eax, eax
0x18000b5f0  js      short loc_18000B624
0x18000b5f2  mov     ecx, dword ptr [rbp+0C0h+var_FC+4]
0x18000b5f5  sub     ecx, 0Ah
0x18000b5f8  jz      loc_18000B8E8
0x18000b5fe  sub     ecx, 1
0x18000b601  jz      loc_18000B8D1
0x18000b607  cmp     ecx, 1
0x18000b60a  jnz     short loc_18000B624
0x18000b60c  mov     eax, [rsp+1C0h+cEnumColumnId]
0x18000b610  lea     rcx, [rsp+1C0h+var_168]
0x18000b615  mov     [rsp+1C0h+var_168], eax
0x18000b619  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x18000b61e  jmp     short loc_18000B624
0x18000b620  test    ebx, ebx
0x18000b622  jns     short loc_18000B65F
0x18000b624  mov     ecx, ebx; int
0x18000b626  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000b62b  mov     r9d, 9EFh
0x18000b631  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b638  xor     edx, edx
0x18000b63a  mov     ecx, eax
0x18000b63c  mov     ebx, eax
0x18000b63e  call    Log_UnistoreHREvent_0
0x18000b643  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000b647  jz      short loc_18000B658
0x18000b649  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000b650  mov     rcx, rsi; Block
0x18000b653  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b658  mov     eax, ebx
0x18000b65a  jmp     loc_18000B704
0x18000b65f  mov     edx, [r14]
0x18000b662  lea     rax, [rsp+1C0h+var_160]
0x18000b667  mov     ecx, [rsp+1C0h+var_164]
0x18000b66b  mov     [rbp+0C0h+var_140], rax
0x18000b66f  lea     rax, [rsp+1C0h+var_164]
0x18000b674  mov     [rbp+0C0h+var_138], rax
0x18000b678  mov     [rbp+0C0h+var_130], 1
0x18000b67c  test    edx, edx
0x18000b67e  jz      short loc_18000B696
0x18000b680  cmp     ecx, edi
0x18000b682  jnz     loc_18000B75F
0x18000b688  mov     eax, [rsp+1C0h+var_168]
0x18000b68c  add     eax, edi
0x18000b68e  cmp     eax, edx
0x18000b690  jnz     loc_18000B72C
0x18000b696  mov     r10d, [r15]
0x18000b699  mov     rax, [rbp+0C0h+var_128]
0x18000b69d  test    r12b, 1
0x18000b6a1  jnz     loc_18000B767
0x18000b6a7  mov     [rsp+1C0h+pvReallocContext], rax; unsigned int *
0x18000b6ac  mov     r9, r13; unsigned int *
0x18000b6af  mov     rax, [rbp+0C0h+var_120]
0x18000b6b3  mov     r8, r14; unsigned int *
0x18000b6b6  mov     [rsp+1C0h+pfnRealloc], rax; unsigned __int8 **
0x18000b6bb  mov     edx, r12d; unsigned int
0x18000b6be  mov     rax, [rsp+1C0h+var_160]
0x18000b6c3  mov     [rsp+1C0h+prgEnumColumn], rax; struct JET_ENUMCOLUMN *
0x18000b6c8  mov     dword ptr [rsp+1C0h+pcEnumColumn], ecx; unsigned int
0x18000b6cc  mov     ecx, r10d; unsigned int
0x18000b6cf  call    ?MapAndConvertProps@@YAJKKPEAK0KPEBUJET_ENUMCOLUMN@@PEAPEAE0@Z; MapAndConvertProps(ulong,ulong,ulong *,ulong *,ulong,JET_ENUMCOLUMN const *,uchar * *,ulong *)
0x18000b6d4  mov     ebx, eax
0x18000b6d6  test    eax, eax
0x18000b6d8  js      loc_18000B972
0x18000b6de  mov     edx, [rsp+1C0h+var_164]
0x18000b6e2  mov     rcx, [rsp+1C0h+var_160]
0x18000b6e7  call    cs:__imp_FreeEnumColumn
0x18000b6ed  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000b6f1  jz      short loc_18000B702
0x18000b6f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000b6fa  mov     rcx, rsi; Block
0x18000b6fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b702  xor     eax, eax
0x18000b704  movaps  xmm6, [rsp+1C0h+var_50]
0x18000b70c  mov     rcx, [rbp+0C0h+var_60]
0x18000b710  xor     rcx, rsp; StackCookie
0x18000b713  call    __security_check_cookie
0x18000b718  add     rsp, 188h
0x18000b71f  pop     r15
0x18000b721  pop     r14
0x18000b723  pop     r13
0x18000b725  pop     r12
0x18000b727  pop     rdi
0x18000b728  pop     rsi
0x18000b729  pop     rbx
0x18000b72a  pop     rbp
0x18000b72b  retn
0x18000b72c  mov     r9d, 9FDh
0x18000b732  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b739  xor     edx, edx
0x18000b73b  mov     ecx, 8000FFFFh
0x18000b740  call    Log_UnistoreHREvent_0
0x18000b745  lea     rcx, [rbp+0C0h+var_140]
0x18000b749  call    tlx___UndoSolo__lambda_9c9b0fa7062f2af27f78bbb345476e79_______UndoSolo__lambda_9c9b0fa7062f2af27f78bbb345476e79___
0x18000b74e  lea     rcx, [rsp+1C0h+rgEnumColumnId]
0x18000b753  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x18000b758  mov     eax, 8000FFFFh
0x18000b75d  jmp     short loc_18000B704
0x18000b75f  mov     r9d, 9FCh
0x18000b765  jmp     short loc_18000B732
0x18000b767  mov     [rsp+1C0h+pfnRealloc], rax; unsigned int *
0x18000b76c  mov     r9d, ecx; unsigned int
0x18000b76f  mov     rax, [rbp+0C0h+var_120]
0x18000b773  mov     r8, r13; unsigned int *
0x18000b776  mov     [rsp+1C0h+prgEnumColumn], rax; unsigned __int8 **
0x18000b77b  mov     rdx, r14; unsigned int *
0x18000b77e  mov     rax, [rsp+1C0h+var_160]
0x18000b783  mov     ecx, r10d; unsigned int
0x18000b786  mov     [rsp+1C0h+pcEnumColumn], rax; struct JET_ENUMCOLUMN *
0x18000b78b  call    ?MapAndConvertPropsEx@@YAJKPEAK0KPEBUJET_ENUMCOLUMN@@PEAPEAE0@Z; MapAndConvertPropsEx(ulong,ulong *,ulong *,ulong,JET_ENUMCOLUMN const *,uchar * *,ulong *)
0x18000b790  mov     ebx, eax
0x18000b792  test    eax, eax
0x18000b794  jns     loc_18000B6DE
0x18000b79a  mov     r9d, 0A09h
0x18000b7a0  jmp     loc_18000B978
0x18000b7a5  test    eax, eax
0x18000b7a7  jz      loc_18000B517
0x18000b7ad  mov     rcx, r15; struct TableHandleInfo *
0x18000b7b0  call    ?UnistoreReseek@@YAJPEAUTableHandleInfo@@@Z; UnistoreReseek(TableHandleInfo *)
0x18000b7b5  mov     ebx, eax
0x18000b7b7  test    eax, eax
0x18000b7b9  jns     loc_18000B968
0x18000b7bf  mov     r9d, 9F5h
0x18000b7c5  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b7cc  mov     edx, 1
0x18000b7d1  mov     ecx, eax
0x18000b7d3  call    Log_UnistoreHREvent_0
0x18000b7d8  mov     rsi, [rsp+1C0h+rgEnumColumnId]
0x18000b7dd  jmp     loc_18000B643
0x18000b7e2  mov     ecx, esi; this
0x18000b7e4  call    ?DoesPropertyRequireProtection@DPHelper@@YAHK@Z; DPHelper::DoesPropertyRequireProtection(ulong)
0x18000b7e9  test    eax, eax
0x18000b7eb  jz      loc_18000B469
0x18000b7f1  xor     ecx, ecx
0x18000b7f3  cmp     ecx, 26h ; '&'
0x18000b7f6  jb      loc_18000B8B2
0x18000b7fc  mov     r9d, 9D1h
0x18000b802  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b809  mov     edx, 1
0x18000b80e  mov     ecx, 80070002h
0x18000b813  call    Log_UnistoreHREvent_0
0x18000b818  lea     rcx, [rsp+1C0h+rgEnumColumnId]
0x18000b81d  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x18000b822  mov     eax, 80070002h
0x18000b827  jmp     loc_18000B704
0x18000b82c  cmp     rcx, rdx
0x18000b82f  jz      short loc_18000B86D
0x18000b831  mov     eax, [rcx+24h]
0x18000b834  movsd   xmm6, qword ptr [rcx+1Ch]
  ... truncated ...
```
