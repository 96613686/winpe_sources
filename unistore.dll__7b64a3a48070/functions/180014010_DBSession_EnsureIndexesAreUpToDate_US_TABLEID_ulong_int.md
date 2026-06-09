# DBSession::_EnsureIndexesAreUpToDate(US_TABLEID,ulong,int)

- ea: `0x180014010`
- end: `0x1800146c1`
- name: `?_EnsureIndexesAreUpToDate@DBSession@@AEAAJW4US_TABLEID@@KH@Z`
- size: `1713`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014de8`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x1800115a0`
- `0x180011ed0`
- `0x18001203c`
- `0x180012098`
- `0x1800131c8`
- `0x18001323c`
- `0x180014010`
- `0x1800146d0`
- `0x180014700`
- `0x18001491c`
- `0x180043bcc`
- `0x180056fd4`
- `0x180070790`
- `0x1800737b4`
- `0x1800ad518`
- `0x1800c50f0`
- `0x1800c5180`

## import_xrefs

- `ESENT!JetOpenTableW` at `0x1800140b6`
- `ESENT!JetOpenTableW` at `0x1800140b6`
- `ESENT!JetCreateIndex3A` at `0x180014683`
- `ESENT!JetCreateIndex3A` at `0x180014683`

## string_xrefs

- `0x1800145f7`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180014619`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x1800146a8`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DBSession::_EnsureIndexesAreUpToDate(__int64 a1, unsigned int a2, unsigned int a3, int a4)
{
  int v5; // r15d
  unsigned __int16 **v6; // r12
  unsigned int TableClassGrBit; // eax
  JET_ERR v8; // ebx
  int ExistingIndex; // eax
  __int64 v10; // r8
  unsigned int HresultFromJetError; // ebx
  DBSession::UnistoreJETIndexInfo *v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // rdi
  unsigned __int64 v15; // rdx
  __int64 k; // rcx
  unsigned int v17; // r13d
  unsigned int v18; // r8d
  __int64 v19; // r14
  struct DBSession::IndexListEntry *v20; // rax
  __int64 i; // rbx
  bool v22; // zf
  __int64 v23; // rcx
  int v24; // r10d
  unsigned int v25; // ebx
  __int64 v26; // r9
  char *j; // r15
  unsigned int v28; // edx
  int v29; // ecx
  int v30; // edx
  int v31; // r8d
  unsigned int v32; // edx
  __int64 v33; // r11
  int v34; // r9d
  int v35; // r8d
  int v36; // r10d
  int v37; // edx
  int v38; // ecx
  int v39; // eax
  __int64 v40; // r8
  unsigned int v41; // r14d
  JET_SESID *v42; // r14
  __int64 m; // rbx
  DBSession::UnistoreJETIndexInfo *v44; // rbx
  int v45; // eax
  DBSession::UnistoreJETIndexInfo *v47; // rbx
  int v48; // eax
  __int64 v49; // r8
  int v50; // eax
  int v51; // eax
  bool v52; // zf
  unsigned int v53; // ebx
  __int64 v54; // r8
  unsigned int v55; // eax
  unsigned int v56; // eax
  int v57; // eax
  __int64 v58; // r8
  unsigned int v59; // edi
  JET_ERR Index3A; // ebx
  unsigned int v61; // eax
  struct DBSession::IndexListEntry *v62; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v63; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v64; // [rsp+4Ch] [rbp-B4h]
  unsigned int v65; // [rsp+50h] [rbp-B0h]
  __int64 v66; // [rsp+58h] [rbp-A8h] BYREF
  JET_TABLEID tableid; // [rsp+60h] [rbp-A0h] BYREF
  int v68; // [rsp+68h] [rbp-98h]
  DBSession *v69; // [rsp+70h] [rbp-90h]
  JET_INDEXCREATE2_A pindexcreate[32]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v71[704]; // [rsp+B80h] [rbp+A80h] BYREF
  _QWORD v72[2]; // [rsp+3780h] [rbp+3680h] BYREF

  v69 = (DBSession *)a1;
  v5 = a4;
  v68 = a4;
  v64 = a3;
  v65 = a2;
  v6 = &(&g_rgTableInfo)[12 * (int)a2];
  tableid = -1;
  v66 = *(_QWORD *)(a1 + 216);
  TableClassGrBit = GetTableClassGrBit(a2);
  v8 = JetOpenTableW(*(_QWORD *)(a1 + 216), *(_DWORD *)(a1 + 224), *v6, 0, 0, TableClassGrBit | 0xA, &tableid);
  CheckCorruption(v8);
  if ( v8 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v8);
    Log_HREventPersist(HresultFromJetError, 0, v49, 647);
LABEL_84:
    v50 = auto_JET_TABLEID::close((auto_JET_TABLEID *)&v66);
    if ( v50 < 0 )
    {
      v55 = MakeHresultFromJetError(v50);
      Log_UnistoreHREvent_0(
        v55,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        261);
    }
    return HresultFromJetError;
  }
  v62 = 0;
  v63 = 0;
  ExistingIndex = DBSession::_GetExistingIndex((DBSession *)a1, tableid, &v63, &v62);
  HresultFromJetError = ExistingIndex;
  if ( ExistingIndex < 0 )
  {
    Log_HREventPersist((unsigned int)ExistingIndex, 1, v10, 652);
    if ( v62 )
      tlx::_delete_array<DBSession::IndexListEntry>((__int64)v62);
    goto LABEL_84;
  }
  v12 = (DBSession::UnistoreJETIndexInfo *)v71;
  v13 = 32;
  v14 = 32;
  do
  {
    DBSession::UnistoreJETIndexInfo::UnistoreJETIndexInfo(v12);
    v12 = (DBSession::UnistoreJETIndexInfo *)((char *)v12 + 352);
    --v14;
  }
  while ( v14 );
  v17 = 0;
  while ( (unsigned int)v14 < *((unsigned __int16 *)v6 + 12) )
  {
    v18 = v63;
    v19 = (__int64)&v6[4][68 * (unsigned int)v14];
    if ( v5 && (LODWORD(i) = v63, (*(_WORD *)(v19 + 4) & 0x1200) == 0) )
    {
LABEL_14:
      v20 = v62;
LABEL_15:
      v22 = (_DWORD)i == v18;
    }
    else
    {
      v20 = v62;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v22 = (_DWORD)i == v63;
        if ( (unsigned int)i >= v63 )
          break;
        if ( *((_DWORD *)v62 + 12 * i + 1) == (_DWORD)v14 )
        {
          if ( !*((_DWORD *)v62 + 12 * i) )
            goto LABEL_15;
          Log_AssertionEvent_3(6 * i, v15, 670);
          v18 = v63;
          goto LABEL_14;
        }
      }
    }
    if ( !v22 )
    {
      v23 = (unsigned int)i;
      v24 = 0;
      v25 = *(unsigned __int16 *)(v19 + 2);
      v26 = 0;
      for ( j = (char *)v20 + 48 * v23; (unsigned int)v26 < v25; v26 = (unsigned int)(v26 + 1) )
      {
        if ( *(_WORD *)(v19 + 4 * v26 + 8) == 31 )
        {
          v35 = *(_DWORD *)(v19 + 4 * v26 + 72);
          v36 = v24 | 0x400;
          v37 = v36 | 1;
          if ( (v35 & 2) == 0 )
            v37 = v36;
          if ( (v35 & 0x40) != 0 )
            v37 |= 0x10000u;
          v38 = v37 | 0x20000;
          if ( (v35 & 0x80u) == 0 )
            v38 = v37;
          v24 = v38 | 4;
          if ( (v35 & 0x20) == 0 )
            v24 = v38;
          if ( (v35 & 0x10) != 0 )
            v24 |= 2u;
        }
      }
      v28 = (((*(__int16 *)(v19 + 4) >> 31) & 0xFFFF0000) + 0x10000) | 2;
      if ( (*(_WORD *)(v19 + 4) & 0x1200) != 0x1200 )
        v28 = ((*(__int16 *)(v19 + 4) >> 31) & 0xFFFF0000) + 0x10000;
      v29 = v28 | 1;
      if ( (*(_WORD *)(v19 + 4) & 0x200) == 0 )
        v29 = v28;
      v30 = v29 | 0x800;
      if ( !v24 )
        v30 = v29;
      v31 = *((_DWORD *)j + 3);
      if ( (*(_WORD *)(v19 + 4) & 0x4000) != 0 )
        v30 |= 0x400u;
      v32 = v30 & 0xFFFFF7FF;
      k = v32;
      LODWORD(k) = v32 | 0x8000;
      if ( (v31 & 0x8000) == 0 )
        k = v32;
      v15 = (unsigned int)k;
      LODWORD(v15) = k & 0xFFFEFFFF;
      if ( (v31 & 0x10000) != 0 )
        v15 = (unsigned int)k;
      if ( (!v24 || v64 == *((_DWORD *)j + 2)) && v31 == (_DWORD)v15 && (!v24 || *((_DWORD *)j + 4) == v24) )
      {
        v33 = *((_QWORD *)j + 3);
        v15 = *(unsigned __int16 *)(v19 + 2);
        if ( (*((_QWORD *)j + 4) - v33) >> 4 == v15 )
        {
          for ( k = 0; (unsigned int)k < *(unsigned __int16 *)(v19 + 2); k = (unsigned int)(k + 1) )
          {
            v15 = v33 + 16LL * (unsigned int)k;
            if ( *(_DWORD *)(v19 + 4 * k + 8) != *(_DWORD *)(v15 + 4) )
              break;
            v34 = *(_DWORD *)(v19 + 4 * k + 72);
            if ( (v34 & 1) != *(_DWORD *)v15 )
              break;
            if ( *(_DWORD *)(v15 + 8) )
            {
              v51 = *(_DWORD *)(v15 + 12);
              if ( v51 == 1 )
              {
                v52 = (v34 & 0x800) == 0;
              }
              else
              {
                if ( v51 != 2 )
                  continue;
                v52 = (v34 & 0x400) == 0;
              }
              if ( v52 )
                break;
            }
          }
          if ( (_DWORD)k == v25 )
          {
            *(_DWORD *)j = 1;
            goto LABEL_43;
          }
        }
      }
      if ( *(_DWORD *)j )
        Log_AssertionEvent_3(k, v15, 733);
    }
    v39 = DBSession::_FillIndexInfo(&pindexcreate[v17], v65, (unsigned int)v14, v64, &pindexcreate[v17], &v71[22 * v17]);
    v41 = v39;
    if ( v39 < 0 )
    {
      Log_HREventPersist((unsigned int)v39, 1, v40, 739);
      v47 = (DBSession::UnistoreJETIndexInfo *)v72;
      do
      {
        v47 = (DBSession::UnistoreJETIndexInfo *)((char *)v47 - 352);
        DBSession::UnistoreJETIndexInfo::~UnistoreJETIndexInfo(v47);
        --v13;
      }
      while ( v13 );
      if ( v62 )
        tlx::_delete_array<DBSession::IndexListEntry>((__int64)v62);
      v48 = auto_JET_TABLEID::close((auto_JET_TABLEID *)&v66);
      if ( v48 < 0 )
      {
        v56 = MakeHresultFromJetError(v48);
        Log_UnistoreHREvent_0(
          v56,
          0,
          "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
          261);
      }
      return v41;
    }
    ++v17;
LABEL_43:
    v5 = v68;
    LODWORD(v14) = v14 + 1;
  }
  v42 = (JET_SESID *)v69;
  for ( m = 0; (unsigned int)m < v63; m = (unsigned int)(m + 1) )
  {
    k = 6 * m;
    if ( !*((_DWORD *)v62 + 12 * m) )
    {
      v57 = DBSession::_DeleteIndex((DBSession *)v42, tableid, *((_DWORD *)v62 + 12 * m + 1));
      v59 = v57;
      if ( v57 < 0 )
      {
        Log_HREventPersist((unsigned int)v57, 1, v58, 748);
        `vector destructor iterator'(
          v71,
          0x160u,
          0x20u,
          (void (*)(void *))DBSession::UnistoreJETIndexInfo::~UnistoreJETIndexInfo);
        if ( v62 )
          tlx::_delete_array<DBSession::IndexListEntry>((__int64)v62);
        auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v66);
        return v59;
      }
    }
  }
  if ( !v17 )
    goto LABEL_69;
  if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x4000) != 0 )
    McTemplateU0qq_EventWriteTransfer(k, UnifiedStore_CreateMissingIndexes, v65, v17);
  Index3A = JetCreateIndex3A(v42[27], tableid, pindexcreate, v17);
  CheckCorruption(Index3A);
  if ( Index3A < 0 )
  {
    v53 = MakeHresultFromJetError(Index3A);
    Log_HREventPersist(v53, 0, v54, 757);
    `vector destructor iterator'(
      v71,
      0x160u,
      0x20u,
      (void (*)(void *))DBSession::UnistoreJETIndexInfo::~UnistoreJETIndexInfo);
    if ( v62 )
      tlx::_delete_array<DBSession::IndexListEntry>((__int64)v62);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v66);
    return v53;
  }
  else
  {
LABEL_69:
    v44 = (DBSession::UnistoreJETIndexInfo *)v72;
    do
    {
      v44 = (DBSession::UnistoreJETIndexInfo *)((char *)v44 - 352);
      DBSession::UnistoreJETIndexInfo::~UnistoreJETIndexInfo(v44);
      --v13;
    }
    while ( v13 );
    if ( v62 )
      tlx::_delete_array<DBSession::IndexListEntry>((__int64)v62);
    v45 = auto_JET_TABLEID::close((auto_JET_TABLEID *)&v66);
    if ( v45 < 0 )
    {
      v61 = MakeHresultFromJetError(v45);
      Log_UnistoreHREvent_0(
        v61,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        261);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180014010  push    rbp
0x180014012  push    rbx
0x180014013  push    rdi
0x180014014  push    r12
0x180014016  push    r14
0x180014018  push    r15
0x18001401a  lea     rbp, [rsp-3698h]
0x180014022  mov     eax, 3798h
0x180014027  call    _alloca_probe
0x18001402c  sub     rsp, rax
0x18001402f  mov     rax, cs:__security_cookie
0x180014036  xor     rax, rsp
0x180014039  mov     [rbp+36C0h+var_40], rax
0x180014040  movsxd  rax, edx
0x180014043  mov     r14, rcx
0x180014046  mov     [rsp+37C0h+var_3750], rcx
0x18001404b  mov     r15d, r9d
0x18001404e  mov     [rsp+37C0h+var_3758], r9d
0x180014053  mov     [rsp+37C0h+var_3774], r8d
0x180014058  lea     r12, [rax+rax*2]
0x18001405c  mov     [rsp+37C0h+var_3770], edx
0x180014060  lea     rax, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180014067  shl     r12, 5
0x18001406b  add     r12, rax
0x18001406e  mov     [rsp+37C0h+tableid], 0FFFFFFFFFFFFFFFFh
0x180014077  mov     rax, [rcx+0D8h]
0x18001407e  mov     ecx, edx; unsigned int
0x180014080  mov     [rsp+37C0h+var_3768], rax
0x180014085  call    ?GetTableClassGrBit@@YAKK@Z; GetTableClassGrBit(ulong)
0x18001408a  mov     r8, [r12]; szTableName
0x18001408e  lea     rcx, [rsp+37C0h+tableid]
0x180014093  mov     edx, [r14+0E0h]; dbid
0x18001409a  or      eax, 0Ah
0x18001409d  mov     [rsp+37C0h+ptableid], rcx; ptableid
0x1800140a2  xor     edi, edi
0x1800140a4  mov     rcx, [r14+0D8h]; sesid
0x1800140ab  xor     r9d, r9d; pvParameters
0x1800140ae  mov     [rsp+37C0h+grbit], eax; grbit
0x1800140b2  mov     [rsp+37C0h+cbParameters], edi; cbParameters
0x1800140b6  call    cs:__imp_JetOpenTableW
0x1800140bc  mov     ecx, eax; int
0x1800140be  mov     ebx, eax
0x1800140c0  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x1800140c5  test    ebx, ebx
0x1800140c7  js      loc_1800144CE
0x1800140cd  mov     rdx, [rsp+37C0h+tableid]; unsigned __int64
0x1800140d2  lea     r9, [rsp+37C0h+var_3780]; struct DBSession::IndexListEntry **
0x1800140d7  lea     r8, [rsp+37C0h+var_3778]; unsigned int *
0x1800140dc  mov     [rsp+37C0h+var_3780], rdi
0x1800140e1  mov     rcx, r14; this
0x1800140e4  mov     [rsp+37C0h+var_3778], edi
0x1800140e8  call    ?_GetExistingIndex@DBSession@@AEAAJ_KPEAKPEAPEAUIndexListEntry@1@@Z; DBSession::_GetExistingIndex(unsigned __int64,ulong *,DBSession::IndexListEntry * *)
0x1800140ed  mov     ebx, eax
0x1800140ef  test    eax, eax
0x1800140f1  js      loc_18001452B
0x1800140f7  mov     [rsp+37C0h+arg_18], rsi
0x1800140ff  lea     rbx, [rbp+36C0h+var_2C40]
0x180014106  mov     esi, 20h ; ' '
0x18001410b  mov     [rsp+37C0h+var_30], r13
0x180014113  mov     edi, esi
0x180014115  mov     rcx, rbx; this
0x180014118  call    ??0UnistoreJETIndexInfo@DBSession@@QEAA@XZ; DBSession::UnistoreJETIndexInfo::UnistoreJETIndexInfo(void)
0x18001411d  add     rbx, 160h
0x180014124  sub     rdi, 1
0x180014128  jnz     short loc_180014115
0x18001412a  xor     r13d, r13d
0x18001412d  movzx   eax, word ptr [r12+18h]
0x180014133  mov     r11d, 1200h
0x180014139  cmp     edi, eax
0x18001413b  jnb     loc_1800143BF
0x180014141  mov     r8d, [rsp+37C0h+var_3778]
0x180014146  mov     eax, edi
0x180014148  imul    r14, rax, 88h
0x18001414f  add     r14, [r12+20h]
0x180014154  test    r15d, r15d
0x180014157  jnz     loc_1800143AC
0x18001415d  mov     rax, [rsp+37C0h+var_3780]
0x180014162  xor     ebx, ebx
0x180014164  cmp     ebx, r8d
0x180014167  jnb     short loc_18001419E
0x180014169  lea     rcx, [rbx+rbx*2]
0x18001416d  add     rcx, rcx
0x180014170  cmp     [rax+rcx*8+4], edi
0x180014174  jz      short loc_18001417A
0x180014176  inc     ebx
0x180014178  jmp     short loc_180014164
0x18001417a  cmp     dword ptr [rax+rcx*8], 0
0x18001417e  jz      short loc_18001419B
0x180014180  mov     r8d, 29Eh
0x180014186  call    Log_AssertionEvent_3
0x18001418b  mov     r8d, [rsp+37C0h+var_3778]
0x180014190  mov     r11d, 1200h
0x180014196  mov     rax, [rsp+37C0h+var_3780]
0x18001419b  cmp     ebx, r8d
0x18001419e  jz      loc_180014353
0x1800141a4  mov     ecx, ebx
0x1800141a6  xor     r10d, r10d
0x1800141a9  movzx   ebx, word ptr [r14+2]
0x1800141ae  xor     r9d, r9d
0x1800141b1  lea     r15, [rcx+rcx*2]
0x1800141b5  shl     r15, 4
0x1800141b9  add     r15, rax
0x1800141bc  test    ebx, ebx
0x1800141be  jz      short loc_1800141D5
0x1800141c0  cmp     word ptr [r14+r9*4+8], 1Fh
0x1800141c7  jz      loc_1800142E1
0x1800141cd  inc     r9d
0x1800141d0  cmp     r9d, ebx
0x1800141d3  jb      short loc_1800141C0
0x1800141d5  movsx   r8d, word ptr [r14+4]
0x1800141da  movzx   eax, r8w
0x1800141de  mov     ecx, r8d
0x1800141e1  sar     ecx, 1Fh
0x1800141e4  and     ax, r11w
0x1800141e8  and     ecx, 0FFFF0000h
0x1800141ee  add     ecx, 10000h
0x1800141f4  mov     edx, ecx
0x1800141f6  or      edx, 2
0x1800141f9  cmp     ax, r11w
0x1800141fd  movzx   eax, r8w
0x180014201  cmovnz  edx, ecx
0x180014204  mov     ecx, 200h
0x180014209  and     ax, cx
0x18001420c  mov     ecx, edx
0x18001420e  or      ecx, 1
0x180014211  test    ax, ax
0x180014214  cmovz   ecx, edx
0x180014217  mov     edx, ecx
0x180014219  bts     edx, 0Bh
0x18001421d  test    r10d, r10d
0x180014220  cmovz   edx, ecx
0x180014223  mov     eax, edx
0x180014225  bts     eax, 0Ah
0x180014229  bt      r8w, 0Eh
0x18001422f  mov     r8d, [r15+0Ch]
0x180014233  cmovb   edx, eax
0x180014236  btr     edx, 0Bh
0x18001423a  mov     ecx, edx
0x18001423c  bts     ecx, 0Fh
0x180014240  bt      r8d, 0Fh
0x180014245  cmovnb  ecx, edx
0x180014248  mov     edx, ecx
0x18001424a  btr     edx, 10h
0x18001424e  bt      r8d, 10h
0x180014253  cmovb   edx, ecx
0x180014256  test    r10d, r10d
0x180014259  jnz     loc_180014334
0x18001425f  cmp     r8d, edx
0x180014262  jnz     loc_180014342
0x180014268  test    r10d, r10d
0x18001426b  jnz     loc_1800143A0
0x180014271  mov     r11, [r15+18h]
0x180014275  mov     rax, [r15+20h]
0x180014279  movzx   edx, word ptr [r14+2]
0x18001427e  sub     rax, r11
0x180014281  sar     rax, 4
0x180014285  cmp     rax, rdx
0x180014288  jnz     loc_180014342
0x18001428e  xor     ecx, ecx
0x180014290  mov     r10d, edx
0x180014293  test    edx, edx
0x180014295  jz      short loc_1800142CA
0x180014297  mov     edx, ecx
0x180014299  shl     rdx, 4
0x18001429d  add     rdx, r11
0x1800142a0  mov     eax, [rdx+4]
0x1800142a3  cmp     [r14+rcx*4+8], eax
0x1800142a8  jnz     short loc_1800142CA
0x1800142aa  mov     r9d, [r14+rcx*4+48h]
0x1800142af  mov     eax, r9d
0x1800142b2  and     eax, 1
0x1800142b5  cmp     eax, [rdx]
0x1800142b7  jnz     short loc_1800142CA
0x1800142b9  cmp     dword ptr [rdx+8], 0
0x1800142bd  jnz     loc_1800144FF
0x1800142c3  inc     ecx
0x1800142c5  cmp     ecx, r10d
0x1800142c8  jb      short loc_180014297
0x1800142ca  cmp     ecx, ebx
0x1800142cc  jnz     short loc_180014342
0x1800142ce  mov     dword ptr [r15], 1
0x1800142d5  mov     r15d, [rsp+37C0h+var_3758]
0x1800142da  inc     edi
0x1800142dc  jmp     loc_18001412D
0x1800142e1  mov     r8d, [r14+r9*4+48h]
0x1800142e6  bts     r10d, 0Ah
0x1800142eb  mov     edx, r10d
0x1800142ee  or      edx, 1
0x1800142f1  test    r8b, 2
0x1800142f5  cmovz   edx, r10d
0x1800142f9  mov     eax, edx
0x1800142fb  bts     eax, 10h
0x1800142ff  test    r8b, 40h
0x180014303  cmovnz  edx, eax
0x180014306  mov     ecx, edx
0x180014308  bts     ecx, 11h
0x18001430c  test    r8b, 80h
0x180014310  cmovz   ecx, edx
0x180014313  mov     r10d, ecx
0x180014316  or      r10d, 4
0x18001431a  test    sil, r8b
0x18001431d  cmovz   r10d, ecx
0x180014321  mov     eax, r10d
0x180014324  or      eax, 2
0x180014327  test    r8b, 10h
0x18001432b  cmovnz  r10d, eax
0x18001432f  jmp     loc_1800141CD
0x180014334  mov     eax, [rsp+37C0h+var_3774]
0x180014338  cmp     eax, [r15+8]
0x18001433c  jz      loc_18001425F
0x180014342  cmp     dword ptr [r15], 0
0x180014346  jz      short loc_180014353
0x180014348  mov     r8d, 2DDh
0x18001434e  call    Log_AssertionEvent_3
0x180014353  mov     r9d, [rsp+37C0h+var_3774]
0x180014358  lea     rdx, [rbp+36C0h+var_2C40]
0x18001435f  mov     ecx, r13d
0x180014362  mov     r8d, edi
0x180014365  imul    rax, rcx, 160h
0x18001436c  add     rdx, rax
0x18001436f  imul    rax, rcx, 58h ; 'X'
0x180014373  mov     qword ptr [rsp+37C0h+grbit], rdx
0x180014378  lea     rcx, [rbp+36C0h+pindexcreate]
0x18001437c  mov     edx, [rsp+37C0h+var_3770]
0x180014380  add     rcx, rax
0x180014383  mov     qword ptr [rsp+37C0h+cbParameters], rcx
0x180014388  call    ?_FillIndexInfo@DBSession@@AEAAJW4US_TABLEID@@KKPEAUtagJET_INDEXCREATE2_A@@PEAUUnistoreJETIndexInfo@1@@Z; DBSession::_FillIndexInfo(US_TABLEID,ulong,ulong,tagJET_INDEXCREATE2_A *,DBSession::UnistoreJETIndexInfo *)
0x18001438d  mov     r14d, eax
0x180014390  test    eax, eax
0x180014392  js      loc_180014468
0x180014398  inc     r13d
0x18001439b  jmp     loc_1800142D5
0x1800143a0  cmp     [r15+10h], r10d
0x1800143a4  jz      loc_180014271
0x1800143aa  jmp     short loc_180014342
0x1800143ac  mov     ebx, r8d
0x1800143af  test    [r14+4], r11w
0x1800143b4  jz      loc_180014196
0x1800143ba  jmp     loc_18001415D
0x1800143bf  mov     r14, [rsp+37C0h+var_3750]
0x1800143c4  xor     ebx, ebx
0x1800143c6  cmp     ebx, [rsp+37C0h+var_3778]
0x1800143ca  jnb     short loc_1800143E6
0x1800143cc  mov     rax, [rsp+37C0h+var_3780]
0x1800143d1  lea     rcx, [rbx+rbx*2]
0x1800143d5  add     rcx, rcx
0x1800143d8  cmp     dword ptr [rax+rcx*8], 0
0x1800143dc  jz      loc_180014632
0x1800143e2  inc     ebx
0x1800143e4  jmp     short loc_1800143C6
0x1800143e6  test    r13d, r13d
0x1800143e9  jnz     loc_180014653
0x1800143ef  lea     rbx, [rbp+36C0h+var_40]
0x1800143f6  nop     word ptr [rax+rax+00000000h]
0x180014400  sub     rbx, 160h
0x180014407  mov     rcx, rbx; this
0x18001440a  call    ??1UnistoreJETIndexInfo@DBSession@@QEAA@XZ; DBSession::UnistoreJETIndexInfo::~UnistoreJETIndexInfo(void)
0x18001440f  sub     rsi, 1
0x180014413  jnz     short loc_180014400
0x180014415  mov     rcx, [rsp+37C0h+var_3780]
0x18001441a  test    rcx, rcx
0x18001441d  jz      short loc_180014424
0x18001441f  call    ??$_delete_array@UIndexListEntry@DBSession@@@tlx@@YAXPEAUIndexListEntry@DBSession@@@Z; tlx::_delete_array<DBSession::IndexListEntry>(DBSession::IndexListEntry *)
0x180014424  lea     rcx, [rsp+37C0h+var_3768]; this
0x180014429  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x18001442e  test    eax, eax
0x180014430  js      loc_18001469F
0x180014436  xor     eax, eax
0x180014438  mov     rsi, [rsp+37C0h+arg_18]
0x180014440  mov     r13, [rsp+37C0h+var_30]
0x180014448  mov     rcx, [rbp+36C0h+var_40]
0x18001444f  xor     rcx, rsp; StackCookie
0x180014452  call    __security_check_cookie
0x180014457  add     rsp, 3798h
0x18001445e  pop     r15
0x180014460  pop     r14
0x180014462  pop     r12
0x180014464  pop     rdi
0x180014465  pop     rbx
0x180014466  pop     rbp
0x180014467  retn
0x180014468  mov     edx, 1
0x18001446d  mov     r9d, 2E3h
0x180014473  mov     ecx, r14d
0x180014476  call    Log_HREventPersist
0x18001447b  lea     rbx, [rbp+36C0h+var_40]
0x180014482  nop     dword ptr [rax+00h]
0x180014486  nop     word ptr [rax+rax+00000000h]
0x180014490  sub     rbx, 160h
0x180014497  mov     rcx, rbx; this
0x18001449a  call    ??1UnistoreJETIndexInfo@DBSession@@QEAA@XZ; DBSession::UnistoreJETIndexInfo::~UnistoreJETIndexInfo(void)
0x18001449f  sub     rsi, 1
0x1800144a3  jnz     short loc_180014490
0x1800144a5  mov     rcx, [rsp+37C0h+var_3780]
0x1800144aa  test    rcx, rcx
0x1800144ad  jz      short loc_1800144B4
0x1800144af  call    ??$_delete_array@UIndexListEntry@DBSession@@@tlx@@YAXPEAUIndexListEntry@DBSession@@@Z; tlx::_delete_array<DBSession::IndexListEntry>(DBSession::IndexListEntry *)
0x1800144b4  lea     rcx, [rsp+37C0h+var_3768]; this
0x1800144b9  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x1800144be  test    eax, eax
  ... truncated ...
```
