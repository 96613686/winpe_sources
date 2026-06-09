# HeapDataSetSession::ReclaimSpaceInOneRow(uint,unsigned __int64,__int64 &,PageRange const *,BlobTimeStampTable const *)

- ea: `0x101487bd0`
- end: `0x101489641`
- name: `?ReclaimSpaceInOneRow@HeapDataSetSession@@QEAAXI_KAEA_JPEBVPageRange@@PEBVBlobTimeStampTable@@@Z`
- size: `6769`
- prototype: `void __fastcall(HeapDataSetSession *__hidden this, unsigned int, unsigned __int64, __int64 *, const struct PageRange *, const struct BlobTimeStampTable *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x101489650`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x100415e90`
- `0x10043e110`
- `0x100441e00`
- `0x100442050`
- `0x10045d930`
- `0x10046bf90`
- `0x1004add30`
- `0x10133bcb0`
- `0x101379de0`
- `0x10137e0d0`
- `0x101487bd0`
- `0x10212bba0`
- `0x10212cee0`
- `0x10212e8c0`
- `0x1021d5c70`
- `0x1021d8a90`
- `0x1021db830`
- `0x1021e7bb0`
- `0x1021eab40`
- `0x1021ed230`

## import_xrefs

- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101489618`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101489618`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014894e1`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014894e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101487cf9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101487e4c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101487f1d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101487fe9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014882af`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10148837c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488687`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488760`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488835`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488ad3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488b94`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488daa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488e83`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488f58`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014891d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101489298`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10148938f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101487cf9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101487e4c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101487f1d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101487fe9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014882af`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10148837c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488687`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488760`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488835`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488ad3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488b94`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488daa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488e83`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101488f58`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014891d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101489298`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10148938f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101487e26`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101487ef7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101487fc3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488289`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488348`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488661`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148873a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148880f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488aad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488b6e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488d84`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488e5d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488f32`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014891b1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101489272`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101487e26`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101487ef7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101487fc3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488289`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488348`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488661`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148873a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10148880f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488aad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488b6e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488d84`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488e5d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101488f32`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014891b1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101489272`
- `sqldk!SystemThread_TlsIndex` at `0x101487dd1`
- `sqldk!SystemThread_TlsIndex` at `0x101487ea2`
- `sqldk!SystemThread_TlsIndex` at `0x101487f6e`
- `sqldk!SystemThread_TlsIndex` at `0x101488234`
- `sqldk!SystemThread_TlsIndex` at `0x1014882f3`
- `sqldk!SystemThread_TlsIndex` at `0x10148860c`
- `sqldk!SystemThread_TlsIndex` at `0x1014886e5`
- `sqldk!SystemThread_TlsIndex` at `0x1014887ba`
- `sqldk!SystemThread_TlsIndex` at `0x101488a58`
- `sqldk!SystemThread_TlsIndex` at `0x101488b19`
- `sqldk!SystemThread_TlsIndex` at `0x101488d2f`
- `sqldk!SystemThread_TlsIndex` at `0x101488e08`
- `sqldk!SystemThread_TlsIndex` at `0x101488edd`
- `sqldk!SystemThread_TlsIndex` at `0x10148915c`
- `sqldk!SystemThread_TlsIndex` at `0x10148921d`
- `sqldk!SystemThread_TlsIndex` at `0x10148948a`
- `sqldk!SystemThread_TlsIndex` at `0x101489504`
- `sqldk!SystemThread_TlsIndex` at `0x1014895e0`
- `sqldk!SystemThread_TlsOffset` at `0x101487dda`
- `sqldk!SystemThread_TlsOffset` at `0x101487eab`
- `sqldk!SystemThread_TlsOffset` at `0x101487f77`
- `sqldk!SystemThread_TlsOffset` at `0x10148823d`
- `sqldk!SystemThread_TlsOffset` at `0x1014882fc`
- `sqldk!SystemThread_TlsOffset` at `0x101488615`
- `sqldk!SystemThread_TlsOffset` at `0x1014886ee`
- `sqldk!SystemThread_TlsOffset` at `0x1014887c3`
- `sqldk!SystemThread_TlsOffset` at `0x101488a61`
- `sqldk!SystemThread_TlsOffset` at `0x101488b22`
- `sqldk!SystemThread_TlsOffset` at `0x101488d38`
- `sqldk!SystemThread_TlsOffset` at `0x101488e11`
- `sqldk!SystemThread_TlsOffset` at `0x101488ee6`
- `sqldk!SystemThread_TlsOffset` at `0x101489165`
- `sqldk!SystemThread_TlsOffset` at `0x101489226`
- `sqldk!SystemThread_TlsOffset` at `0x101489493`
- `sqldk!SystemThread_TlsOffset` at `0x10148950d`
- `sqldk!SystemThread_TlsOffset` at `0x1014895e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014894ae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101489528`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101489602`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014894ae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101489528`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101489602`

## string_xrefs

- `0x1014894d5`: `Sql\Ntdbms\storeng\dfs\access\HeapDataSet.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HeapDataSetSession::ReclaimSpaceInOneRow(
        HeapDataSetSession *this,
        unsigned int a2,
        HeapRowObject *a3,
        __int64 *a4,
        const struct PageRange *a5,
        const struct BlobTimeStampTable *a6)
{
  HeapRowObject *v6; // r14
  unsigned int v7; // ebx
  HeapDataSetSession *v8; // r13
  char v9; // r15
  int v10; // edi
  int v11; // r12d
  __int64 Record; // rsi
  __int16 *v13; // rbx
  __int64 v14; // r8
  _BYTE *v15; // rdx
  char v16; // al
  _BYTE *v17; // rcx
  unsigned __int16 *v18; // r14
  unsigned __int16 v19; // ax
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int16 v22; // dx
  unsigned int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int v26; // ecx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // r9
  __int64 v30; // rax
  unsigned int v31; // edi
  unsigned int v32; // r8d
  unsigned int v33; // eax
  unsigned __int16 v34; // cx
  __int64 v35; // rdx
  __int16 v36; // cx
  __int16 v37; // cx
  int v38; // eax
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v40; // rdx
  int v41; // r8d
  unsigned __int64 v42; // r9
  int v43; // edx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  unsigned int v48; // edx
  char v49; // cl
  int v50; // r14d
  unsigned __int8 *v51; // r9
  unsigned __int8 *v52; // r8
  int v53; // ecx
  unsigned int v54; // ebx
  unsigned int v55; // ecx
  __int16 v56; // ax
  __int16 v57; // cx
  _QWORD *v58; // rax
  __int64 v59; // rax
  unsigned int v60; // edx
  unsigned __int8 *v61; // rdi
  unsigned __int16 v62; // r8
  __int64 v63; // rax
  __int64 v64; // rax
  unsigned int v65; // r10d
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  unsigned __int8 *v70; // rax
  unsigned int v71; // ebx
  unsigned __int16 v72; // r9
  unsigned __int8 *v73; // r8
  __int16 v74; // ax
  __int16 v75; // cx
  struct RecVersioningInfo *v76; // rax
  __int64 v77; // rdx
  int v78; // r8d
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  char v83; // cl
  int v84; // r8d
  bool v85; // zf
  unsigned int v86; // ecx
  unsigned int v87; // eax
  unsigned __int8 *v88; // rdi
  unsigned __int16 v89; // r8
  __int64 v90; // rax
  __int64 v91; // rax
  unsigned int v92; // r10d
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  unsigned __int8 *v97; // rax
  unsigned int v98; // ebx
  unsigned __int16 v99; // r9
  unsigned __int8 *v100; // r8
  __int16 v101; // r9
  __int16 v102; // cx
  struct RecVersioningInfo *v103; // rax
  __int64 v104; // rdx
  int v105; // r8d
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  char v110; // cl
  bool v111; // zf
  unsigned int v112; // ecx
  unsigned int v113; // eax
  __int64 *v114; // rdi
  __int64 v115; // rbx
  __int64 v116; // rdx
  struct BlobTimeStampTable *v117; // rdi
  __int64 v118; // rbx
  __int64 v119; // rdx
  AccBindings *v120; // rbx
  __int64 v121; // rbx
  struct Worker *v122; // rcx
  const struct SQLError *CurrentException; // rax
  __int16 v124; // [rsp+30h] [rbp-2098h] BYREF
  __int16 v125; // [rsp+32h] [rbp-2096h] BYREF
  unsigned int v126; // [rsp+34h] [rbp-2094h]
  unsigned __int8 *v127; // [rsp+38h] [rbp-2090h]
  __int64 v128; // [rsp+40h] [rbp-2088h]
  unsigned int v129; // [rsp+48h] [rbp-2080h]
  unsigned __int16 v130; // [rsp+4Ch] [rbp-207Ch]
  unsigned __int64 v131; // [rsp+4Eh] [rbp-207Ah]
  _TBYTE v132; // [rsp+56h] [rbp-2072h]
  unsigned int v133; // [rsp+60h] [rbp-2068h]
  int v134; // [rsp+68h] [rbp-2060h]
  int v135; // [rsp+6Ch] [rbp-205Ch] BYREF
  int v136; // [rsp+70h] [rbp-2058h] BYREF
  int v137; // [rsp+74h] [rbp-2054h] BYREF
  int v138; // [rsp+78h] [rbp-2050h]
  __int64 *v139; // [rsp+80h] [rbp-2048h]
  unsigned int v140; // [rsp+88h] [rbp-2040h]
  unsigned __int64 v141; // [rsp+90h] [rbp-2038h] BYREF
  struct BlobTimeStampTable *v142; // [rsp+98h] [rbp-2030h]
  struct PageRange *v143; // [rsp+A0h] [rbp-2028h]
  HeapRowObject *v144[3]; // [rsp+A8h] [rbp-2020h] BYREF
  _BYTE v145[32]; // [rsp+C0h] [rbp-2008h] BYREF
  unsigned __int8 Destination[8096]; // [rsp+E0h] [rbp-1FE8h] BYREF

  v144[2] = (HeapRowObject *)-2LL;
  v139 = a4;
  v6 = a3;
  v144[0] = a3;
  v7 = a2;
  v140 = a2;
  v8 = this;
  v141 = (unsigned __int64)this;
  v143 = a5;
  v142 = a6;
  v124 = -1;
  v127 = 0;
  v126 = 0;
  v131 = 0;
  *(_QWORD *)((char *)&v132 + 2) = 0;
  v128 = 0;
  v135 = 0;
  v136 = 0;
  v137 = 0;
  v9 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 3) + 48LL) + 7390LL);
  v10 = a2 & 0xC2;
  v138 = v10;
  if ( !a5 || (v11 = 1, (a2 & 8) == 0) )
    v11 = 0;
  v134 = v11;
  Record = HeapRowObject::GetRecord(a3, 1, 0);
  if ( v9 )
  {
    if ( (unsigned int)HeapRowObject::PrepareForUpdate(v6, 0, 0) )
      utassert_fail(1u, "hr == S_OK", "HeapDataSet.cpp", 7515, 0);
    Record = HeapRowObject::GetRecord(v6, 1, 0);
    if ( !Record )
    {
      (*(void (__fastcall **)(HeapRowObject *))(*(_QWORD *)v6 + 8LL))(v6);
      return;
    }
  }
  if ( (v7 & 0x10) == 0 && !v10 && !v11 && (v7 & 0x100) == 0 )
    goto LABEL_353;
  v124 = *(_WORD *)Record;
  if ( v124 )
  {
    if ( *(_WORD *)Record && (v58 = *(_QWORD **)(Record + 16)) != 0 && *v58 )
    {
      Record::DecompressRec((Record *)&v124, Destination, 0x1F9Eu, (const struct Record *)Record);
    }
    else
    {
      CDRecord::CopyNewRec((CDRecord *)&v125, Destination, 0x1F9Eu, (const struct CDRecord *)(Record + 2));
      if ( *(_WORD *)Record )
        v59 = *(_QWORD *)(Record + 16);
      else
        v59 = 0;
      v128 = v59;
    }
    v50 = 9;
    goto LABEL_128;
  }
  v13 = (__int16 *)(Record + 2);
  if ( *(_DWORD *)(Record + 4) )
    goto LABEL_101;
  *v13 = 0;
  v14 = *(unsigned int *)(Record + 16);
  *(_DWORD *)(Record + 20) = v14;
  v15 = *(_BYTE **)(Record + 8);
  v16 = *v15;
  v17 = v15;
  if ( (*v15 & 0x10) != 0 )
  {
    LODWORD(v14) = (((unsigned int)*(unsigned __int16 *)&v15[v14] + 7) >> 3) + 2 + v14;
    *(_DWORD *)(Record + 20) = v14;
    v16 = *v15;
    v17 = v15;
  }
  if ( (v16 & 0x20) == 0 )
  {
    *(_DWORD *)(Record + 4) = v14;
    *(_WORD *)(Record + 28) = 0;
    *(_DWORD *)(Record + 24) = v14;
    goto LABEL_69;
  }
  v18 = (unsigned __int16 *)&v15[(unsigned int)v14];
  v19 = *v18;
  *(_WORD *)(Record + 28) = *v18;
  if ( !v19 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v20 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v20 )
      {
        v21 = *(_QWORD *)(v20 + 96);
        if ( v21 )
        {
          if ( *(_BYTE *)(v21 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
            else
              ex_raise(34, 68, 21, 1003);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(Record + 8), 3);
    LODWORD(v14) = *(_DWORD *)(Record + 20);
    v19 = *(_WORD *)(Record + 28);
  }
  v22 = v19;
  v23 = v14 + 2 * (v19 + 1);
  *(_DWORD *)(Record + 24) = v23;
  if ( v23 > 0x1F9E )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v24 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v24 )
      {
        v25 = *(_QWORD *)(v24 + 96);
        if ( v25 )
        {
          if ( *(_BYTE *)(v25 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(Record + 8), 4);
    v22 = *(_WORD *)(Record + 28);
  }
  v26 = v18[v22] & 0x7FFF;
  *(_DWORD *)(Record + 4) = v26;
  if ( *(_DWORD *)(Record + 24) > v26 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v27 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v27 )
      {
        v28 = *(_QWORD *)(v27 + 96);
        if ( v28 )
        {
          if ( *(_BYTE *)(v28 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(Record + 8), 4);
    v22 = *(_WORD *)(Record + 28);
  }
  if ( (v18[v22] & 0x8000u) == 0 )
  {
LABEL_63:
    LODWORD(v14) = *(_DWORD *)(Record + 4);
    v17 = *(_BYTE **)(Record + 8);
    goto LABEL_69;
  }
  while ( 1 )
  {
    v29 = *(_QWORD *)(Record + 8);
    v30 = v29 + *(unsigned int *)(Record + 20);
    if ( v22 == 1 )
    {
      v31 = *(_DWORD *)(Record + 24);
      v32 = v31;
      v33 = *(_WORD *)(v30 + 2LL * v22) & 0x7FFF;
    }
    else
    {
      v31 = *(_WORD *)(v30 + 2LL * v22 - 2) & 0x7FFF;
      v32 = *(_DWORD *)(Record + 24);
      v33 = *(_WORD *)(v30 + 2LL * v22) & 0x7FFF;
      if ( v31 < v32 )
        goto LABEL_56;
    }
    if ( v33 < v31 )
    {
LABEL_56:
      RaiseInconsistencyError(*(_QWORD *)(Record + 8), 7);
      v32 = *(_DWORD *)(Record + 24);
      v29 = *(_QWORD *)(Record + 8);
      v22 = *(_WORD *)(Record + 28);
    }
    if ( v31 < v32 || v31 > *(_DWORD *)(Record + 4) )
      goto LABEL_101;
    v34 = *(_WORD *)(v29 + v31);
    if ( v34 == 5 )
      break;
    if ( v34 >= 0x400u )
    {
      *v13 |= 1u;
      *(_WORD *)(Record + 28) = --v22;
      if ( v22 )
      {
        if ( (v18[v22] & 0x8000u) != 0 )
          continue;
      }
    }
    goto LABEL_63;
  }
  *v13 |= 2u;
  *(_WORD *)(Record + 28) = v22 - 1;
  *(_WORD *)(Record + 42) = v31;
  v35 = *(_QWORD *)(Record + 8) + (unsigned __int16)v31;
  v36 = *(_WORD *)(v35 + 2);
  if ( (v36 & 0x4000) != 0 )
    v37 = *(_WORD *)(Record + 44) & 0xC7FF | v36 & 0x3800;
  else
    v37 = *(_WORD *)(Record + 44) & 0xC7FF;
  *(_WORD *)(Record + 44) = v37;
  *(_WORD *)(Record + 44) = v37 ^ (*(_WORD *)(v35 + 2) ^ v37) & 0x7FF;
  LODWORD(v14) = *(_DWORD *)(Record + 4);
  v17 = *(_BYTE **)(Record + 8);
LABEL_69:
  if ( (*v17 & 0x40) != 0 )
  {
    v38 = *(_DWORD *)(Record + 4);
    *(_DWORD *)(Record + 38) = v38;
    *(_DWORD *)(Record + 4) = v38 + 14;
    VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)(Record + 2));
    v40 = HIWORD(*(_QWORD *)VersioningInfo);
    v41 = 0;
    if ( (((__int16)v40 ^ ((unsigned int)(__int16)v40 >> 1)) & 0x2000) != 0 )
    {
      if ( (v40 & 0x4000) != 0 )
        LOWORD(v40) = v40 | 0x2000;
      else
        LOWORD(v40) = v40 & 0xDFFF;
    }
    if ( (_WORD)v40 == 0xFFFC )
      v41 = (unsigned __int16)WORD2(*(_QWORD *)VersioningInfo) >> 5;
    *(_DWORD *)(Record + 4) += v41;
    LODWORD(v14) = *(_DWORD *)(Record + 4);
    v17 = *(_BYTE **)(Record + 8);
  }
  else
  {
    *(_DWORD *)(Record + 38) = 0;
  }
  v42 = *(_QWORD *)(Record + 30);
  v43 = v14;
  if ( v42 && v42 < (unsigned __int64)&v17[(unsigned int)v14] )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v44 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v44 )
      {
        v45 = *(_QWORD *)(v44 + 96);
        if ( v45 )
        {
          if ( *(_BYTE *)(v45 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
            else
              ex_raise(34, 68, 21, 1018);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(Record + 8), 18);
    v43 = *(_DWORD *)(Record + 4);
  }
  if ( (unsigned int)(v43 - 1) > 0x3F3B )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v46 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset
                      + 8LL);
      if ( v46 )
      {
        v47 = *(_QWORD *)(v46 + 96);
        if ( v47 )
        {
          if ( *(_BYTE *)(v47 + 1177) )
          {
            if ( !byte_10316E7C7 && (qword_10317B120 & 2) == 0 )
            {
              ex_raise(34, 68, 21, 1005);
              RaiseInconsistencyError(*(_QWORD *)(Record + 8), 5);
              goto LABEL_101;
            }
            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(Record + 8), 5);
  }
LABEL_101:
  v48 = *(_DWORD *)(Record + 4);
  if ( v48 >= 9 || (v49 = **(_BYTE **)(Record + 8) & 0xE) != 0 && v49 != 12 )
  {
    v50 = 9;
  }
  else
  {
    v50 = 9;
    v48 = 9;
  }
  LODWORD(v128) = *(_DWORD *)(Record + 16);
  v125 = *v13;
  v126 = *(_DWORD *)(Record + 4);
  v130 = *(_WORD *)(Record + 28);
  HIDWORD(v128) = *(_DWORD *)(Record + 20);
  v129 = *(_DWORD *)(Record + 24);
  LODWORD(v132) = *(_DWORD *)(Record + 38);
  memcpy_s(Destination, 0x1F9Eu, *(const void *const *)(Record + 8), v48);
  v127 = Destination;
  if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v125) )
  {
    v51 = v127;
    v52 = &v127[HIDWORD(v128)];
    v53 = *(unsigned __int16 *)v52 - 1;
    if ( (v125 & 1) == 0 )
      v53 = *(unsigned __int16 *)v52;
    if ( v53 == 1 )
      v54 = v129;
    else
      v54 = *(_WORD *)&v52[2 * v53 - 2] & 0x7FFF;
    v55 = *(_WORD *)&v52[2 * v53] & 0x7FFF;
    if ( v54 < v129 || v55 < v54 )
    {
      RaiseInconsistencyError(v127, 7);
      v51 = v127;
    }
    WORD2(v132) = v54;
    v56 = *(_WORD *)&v51[(unsigned __int16)v54 + 2];
    if ( (v56 & 0x4000) != 0 )
      v57 = (WORD3(v132) ^ v56) & 0x3800 ^ WORD3(v132);
    else
      v57 = WORD3(v132) & 0xC7FF;
    WORD3(v132) = v57;
    WORD3(v132) = v57 ^ (*(_WORD *)&v51[(unsigned __int16)v54 + 2] ^ v57) & 0x7FF;
  }
LABEL_128:
  if ( v124 )
    CDRecord::MakePrimaryRec((CDRecord *)&v125);
  else
    FixedVarRecord::MakePrimaryRec((FixedVarRecord *)&v125);
  v60 = v126;
  if ( !v9 )
    goto LABEL_348;
  if ( v124 )
  {
    if ( (((*v127 & 0x1C) - 16) & 0xFFFFFFFB) != 0 )
    {
      if ( !v126 )
      {
        CDRecord::Resize((CDRecord *)&v125);
        v60 = v126;
        if ( !v126 )
        {
          CDRecord::Resize((CDRecord *)&v125);
          v60 = v126;
        }
      }
      if ( v60 >= 9 || (*v127 & 0x1C) != 0 && (*v127 & 0x1C) != 0xC )
        v84 = v60;
      else
        v84 = 9;
      v85 = (*v127 & 2) == 0;
      v86 = v133;
      goto LABEL_236;
    }
LABEL_241:
    if ( v124 )
    {
      if ( !v60 )
      {
        CDRecord::Resize((CDRecord *)&v125);
        v60 = v126;
        if ( !v126 )
        {
          CDRecord::Resize((CDRecord *)&v125);
          v60 = v126;
        }
      }
      if ( v60 >= 9 || (*v127 & 0x1C) != 0 && (*v127 & 0x1C) != 0xC )
        v50 = v60;
      v111 = (*v127 & 2) == 0;
      v112 = v133;
      goto LABEL_343;
    }
LABEL_242:
    if ( !v60 )
    {
      v125 = 0;
      v60 = v128;
      HIDWORD(v128) = v128;
      if ( (*v127 & 0x10) != 0 )
      {
        v60 = (((unsigned int)*(unsigned __int16 *)&v127[(unsigned int)v128] + 7) >> 3) + v128 + 2;
        HIDWORD(v128) = v60;
      }
      if ( (*v127 & 0x20) != 0 )
      {
        v88 = &v127[v60];
        v89 = *(_WORD *)v88;
        v130 = v89;
        if ( !v89 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v90 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v90 )
            {
              v91 = *(_QWORD *)(v90 + 96);
              if ( v91 )
              {
                if ( *(_BYTE *)(v91 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v127, 3);
          v89 = v130;
        }
        v92 = HIDWORD(v128) + 2 + 2 * v89;
        v129 = v92;
        if ( v92 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v93 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v93 )
            {
              v94 = *(_QWORD *)(v93 + 96);
              if ( v94 )
              {
                if ( *(_BYTE *)(v94 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v127, 4);
          v89 = v130;
          v92 = v129;
        }
        v60 = *(_WORD *)&v88[2 * v89] & 0x7FFF;
        v126 = v60;
        if ( v92 > v60 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v95 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL);
            if ( v95 )
            {
              v96 = *(_QWORD *)(v95 + 96);
              if ( v96 )
              {
                if ( *(_BYTE *)(v96 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v127, 4);
          v89 = v130;
          v92 = v129;
          v60 = v126;
        }
        while ( *(__int16 *)&v88[2 * v89] < 0 )
        {
          v97 = &v127[HIDWORD(v128)];
          if ( v89 == 1 )
            v98 = v92;
          else
            v98 = *(_WORD *)&v97[2 * v89 - 2] & 0x7FFF;
          if ( v98 < v92 || (*(_WORD *)&v97[2 * v89] & 0x7FFFu) < v98 )
          {
            RaiseInconsistencyError(v127, 7);
            v89 = v130;
            v92 = v129;
            v60 = v126;
          }
          if ( v98 < v92 || v98 > v60 )
            goto LABEL_330;
          v99 = *(_WORD *)&v127[v98];
          if ( v99 == 5 )
          {
            v125 |= 2u;
            v130 = v89 - 1;
            WORD2(v132) = v98;
            v100 = &v127[(unsigned __int16)v98];
            v101 = *((_WORD *)v100 + 1);
            if ( (v101 & 0x4000) != 0 )
              v102 = (v101 ^ WORD3(v132)) & 0x3800 ^ WORD3(v132);
            else
              v102 = WORD3(v132) & 0xC7FF;
            WORD3(v132) = v102;
            WORD3(v132) = v102 ^ (*((_WORD *)v100 + 1) ^ v102) & 0x7FF;
            break;
          }
          if ( v99 >= 0x400u )
          {
            v125 |= 1u;
            v85 = v89-- == 1;
            v130 = v89;
            if ( !v85 )
              continue;
          }
          break;
        }
      }
      else
      {
        v126 = v60;
        v130 = 0;
        v129 = v60;
      }
      if ( (*v127 & 0x40) != 0 )
      {
        LODWORD(v132) = v60;
        v126 = v60 + 14;
        v103 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v125);
        v104 = HIWORD(*(_QWORD *)v103);
        v105 = 0;
        if ( (((__int16)v104 ^ ((unsigned int)(__int16)v104 >> 1)) & 0x2000) != 0 )
        {
          if ( (v104 & 0x4000) != 0 )
            LOWORD(v104) = v104 | 0x2000;
          else
            LOWORD(v104) = v104 & 0xDFFF;
        }
        if ( (_WORD)v104 == 0xFFFC )
          v105 = (unsigned __int16)WORD2(*(_QWORD *)v103) >> 5;
        v60 = v105 + v126;
        v126 += v105;
      }
      else
      {
        LODWORD(v132) = 0;
      }
      if ( v131 && v131 < (unsigned __int64)&v127[v60] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v106 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v106 )
          {
            v107 = *(_QWORD *)(v106 + 96);
            if ( v107 )
            {
              if ( *(_BYTE *)(v107 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v127, 18);
        v60 = v126;
      }
      if ( v60 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v108 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v108 )
          {
            v109 = *(_QWORD *)(v108 + 96);
            if ( v109 )
            {
              if ( *(_BYTE *)(v109 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v127, 5);
        v60 = v126;
      }
    }
LABEL_330:
    if ( v60 >= 9 || (v110 = *v127 & 0xE) != 0 && v110 != 12 )
      v50 = v60;
    v111 = (*v127 & 0x40) == 0;
    v112 = LODWORD(v132);
LABEL_343:
    if ( v111 )
      v112 = v50;
    v113 = 24;
    if ( !v124 )
      v113 = 32;
    if ( v112 >= v113 )
      goto LABEL_348;
    goto LABEL_350;
  }
  if ( (*v127 & 0xE) == 2 )
    goto LABEL_242;
  if ( !v126 )
  {
    v125 = 0;
    v60 = v128;
    HIDWORD(v128) = v128;
    if ( (*v127 & 0x10) != 0 )
    {
      v60 = (((unsigned int)*(unsigned __int16 *)&v127[(unsigned int)v128] + 7) >> 3) + v128 + 2;
      HIDWORD(v128) = v60;
    }
    if ( (*v127 & 0x20) != 0 )
    {
      v61 = &v127[v60];
      v62 = *(_WORD *)v61;
      v130 = v62;
      if ( !v62 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v63 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v63 )
          {
            v64 = *(_QWORD *)(v63 + 96);
            if ( v64 )
            {
              if ( *(_BYTE *)(v64 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                else
                  ex_raise(34, 68, 21, 1003);
              }
            }
          }
        }
        RaiseInconsistencyError(v127, 3);
        v62 = v130;
      }
      v65 = HIDWORD(v128) + 2 + 2 * v62;
      v129 = v65;
      if ( v65 > 0x1F9E )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v66 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v66 )
          {
            v67 = *(_QWORD *)(v66 + 96);
            if ( v67 )
            {
              if ( *(_BYTE *)(v67 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(v127, 4);
        v62 = v130;
        v65 = v129;
      }
      v60 = *(_WORD *)&v61[2 * v62] & 0x7FFF;
      v126 = v60;
      if ( v65 > v60 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v68 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset
                          + 8LL);
          if ( v68 )
          {
            v69 = *(_QWORD *)(v68 + 96);
            if ( v69 )
            {
              if ( *(_BYTE *)(v69 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(v127, 4);
        v62 = v130;
        v65 = v129;
        v60 = v126;
      }
      while ( *(__int16 *)&v61[2 * v62] < 0 )
      {
        v70 = &v127[HIDWORD(v128)];
        if ( v62 == 1 )
          v71 = v65;
        else
          v71 = *(_WORD *)&v70[2 * v62 - 2] & 0x7FFF;
        if ( v71 < v65 || (*(_WORD *)&v70[2 * v62] & 0x7FFFu) < v71 )
        {
          RaiseInconsistencyError(v127, 7);
          v62 = v130;
          v65 = v129;
          v60 = v126;
        }
        if ( v71 < v65 || v71 > v60 )
          goto LABEL_221;
        v72 = *(_WORD *)&v127[v71];
        if ( v72 == 5 )
        {
          v125 |= 2u;
          v130 = v62 - 1;
          WORD2(v132) = v71;
          v73 = &v127[(unsigned __int16)v71];
          v74 = *((_WORD *)v73 + 1);
          if ( (v74 & 0x4000) != 0 )
            v75 = (WORD3(v132) ^ v74) & 0x3800 ^ WORD3(v132);
          else
            v75 = WORD3(v132) & 0xC7FF;
          WORD3(v132) = v75;
          WORD3(v132) = v75 ^ (*((_WORD *)v73 + 1) ^ v75) & 0x7FF;
          break;
        }
        if ( v72 >= 0x400u )
        {
          v125 |= 1u;
          v85 = v62-- == 1;
          v130 = v62;
          if ( !v85 )
            continue;
        }
        break;
      }
    }
    else
    {
      v126 = v60;
      v130 = 0;
      v129 = v60;
    }
    if ( (*v127 & 0x40) != 0 )
    {
      LODWORD(v132) = v60;
      v126 = v60 + 14;
      v76 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v125);
      v77 = HIWORD(*(_QWORD *)v76);
      v78 = 0;
      if ( (((__int16)v77 ^ ((unsigned int)(__int16)v77 >> 1)) & 0x2000) != 0 )
      {
        if ( (v77 & 0x4000) != 0 )
          LOWORD(v77) = v77 | 0x2000;
        else
          LOWORD(v77) = v77 & 0xDFFF;
      }
      if ( (_WORD)v77 == 0xFFFC )
        v78 = (unsigned __int16)WORD2(*(_QWORD *)v76) >> 5;
      v60 = v78 + v126;
      v126 += v78;
    }
    else
    {
      LODWORD(v132) = 0;
    }
    if ( v131 && v131 < (unsigned __int64)&v127[v60] )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v79 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL);
        if ( v79 )
        {
          v80 = *(_QWORD *)(v79 + 96);
          if ( v80 )
          {
            if ( *(_BYTE *)(v80 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
              else
                ex_raise(34, 68, 21, 1018);
            }
          }
        }
      }
      RaiseInconsistencyError(v127, 18);
      v60 = v126;
    }
    if ( v60 - 1 > 0x3F3B )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v81 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset
                        + 8LL);
        if ( v81 )
        {
          v82 = *(_QWORD *)(v81 + 96);
          if ( v82 )
          {
            if ( *(_BYTE *)(v82 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
              else
                ex_raise(34, 68, 21, 1005);
            }
          }
        }
      }
      RaiseInconsistencyError(v127, 5);
      v60 = v126;
    }
  }
LABEL_221:
  if ( v60 >= 9 || (v83 = *v127 & 0xE) != 0 && v83 != 12 )
  {
    v84 = v60;
    v85 = (*v127 & 0x40) == 0;
    v86 = LODWORD(v132);
  }
  else
  {
    v84 = 9;
    v85 = (*v127 & 0x40) == 0;
    v86 = LODWORD(v132);
  }
LABEL_236:
  if ( v85 )
    v86 = v84;
  v87 = 16;
  if ( !v124 )
    v87 = 22;
  if ( v86 < v87 )
    goto LABEL_241;
LABEL_348:
  if ( v124 )
  {
    if ( (*v127 & 2) != 0 )
    {
      if ( !v60 )
        CDRecord::Resize((CDRecord *)&v125);
      *v127 &= ~2u;
      v126 = v133;
      v133 = 0;
    }
  }
  else
  {
    FixedVarRecord::ClearVersioningInfo((FixedVarRecord *)&v125);
  }
LABEL_350:
  v6 = v144[0];
  if ( (unsigned int)HeapRowObject::PrepareForUpdate(v144[0], 0, 0) )
    utassert_fail(1u, "hr == S_OK", "HeapDataSet.cpp", 7568, 0);
  v7 = v140;
  v8 = (HeapDataSetSession *)v141;
  v10 = v138;
  v11 = v134;
LABEL_353:
  (*(void (__fastcall **)(HeapRowObject *))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v10 || (v7 & 0x10) != 0 )
    LongRecord_ReclaimSpace(
      **((const struct HoBtAccess ***)v8 + 92),
      *((struct LobContext **)v8 + 61),
      (struct Record *)&v124,
      v7,
      &v136);
  v114 = v139;
  if ( v11 )
    LongRecord_MoveOffRowStorage(*((struct LobContext **)v8 + 61), (struct Record *)&v124, v143, v142, v139, &v135);
  if ( (v7 & 0x100) != 0 )
    LongRecord_MoveFilestreamStorage(*((struct LobContext **)v8 + 61), (struct Record *)&v124, v114, &v137);
  if ( (v135 || v136 || v137) && (v7 & 0x20) == 0 )
    HeapRowObject::Update(v6, (struct Record *)&v124, 0, 0);
  if ( (v7 & 4) != 0 )
  {
    v138 = 7628;
    v115 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v116 = *(_QWORD *)(v115 + 256);
    if ( !v116 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v116 = *(_QWORD *)(v115 + 256);
    }
    v143 = *(struct PageRange **)(v116 + 1000);
    v117 = (struct BlobTimeStampTable *)operator new(
                                          0x110u,
                                          v143,
                                          "Sql\\Ntdbms\\storeng\\dfs\\access\\HeapDataSet.cpp",
                                          7628,
                                          5u);
    v142 = v117;
    if ( v117 )
    {
      v118 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v119 = *(_QWORD *)(v118 + 256);
      if ( !v119 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v119 = *(_QWORD *)(v118 + 256);
      }
      v120 = AccBindings::AccBindings(v117, *(struct IMemObj **)(v119 + 1000));
    }
    else
    {
      v120 = 0;
    }
    v139 = (__int64 *)v120;
    memset_0(v120, 0, 0x110u);
    *((_WORD *)v120 + 7) = 2;
    *((_WORD *)v120 + 28) |= 2u;
    try
    {
      DatasetSession::SetData(v8, (unsigned __int64)v6, (unsigned __int64)v120, 0, &v141, 0);
      AccBindings::Release(v120);
    }
    catch ( SQLError v145 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v144, (const struct SQLError *)v145);
        AccBindings::Release((AccBindings *)v139);
        CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v144);
        ExceptionRethrow(CurrentException);
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v144);
      }
      catch ( ShortStackException )
      {
      }
    }
    v121 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v122 = *(struct Worker **)(v121 + 256);
    if ( !v122 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v122 = *(struct Worker **)(v121 + 256);
    }
    if ( *((_DWORD *)v122 + 139) )
      ExceptionPostCatchActions(v122);
  }
}

```

## disassembly

```asm
0x101487bd0  push    rbx
0x101487bd2  push    rsi
0x101487bd3  push    rdi
0x101487bd4  push    r12
0x101487bd6  push    r13
0x101487bd8  push    r14
0x101487bda  push    r15
0x101487bdc  mov     eax, 2090h
0x101487be1  call    _alloca_probe
0x101487be6  sub     rsp, rax
0x101487be9  mov     [rsp+20C8h+var_2010], 0FFFFFFFFFFFFFFFEh
0x101487bf5  mov     rax, cs:__security_cookie
0x101487bfc  xor     rax, rsp
0x101487bff  mov     [rsp+20C8h+var_48], rax
0x101487c07  mov     [rsp+20C8h+var_2048], r9
0x101487c0f  mov     r14, r8
0x101487c12  mov     [rsp+20C8h+var_2020], r8
0x101487c1a  mov     ebx, edx
0x101487c1c  mov     [rsp+20C8h+var_2040], edx
0x101487c23  mov     r13, rcx
0x101487c26  mov     [rsp+20C8h+var_2038], rcx
0x101487c2e  mov     rdx, [rsp+20C8h+arg_20]
0x101487c36  mov     [rsp+20C8h+var_2028], rdx
0x101487c3e  mov     rax, [rsp+20C8h+arg_28]
0x101487c46  mov     [rsp+20C8h+var_2030], rax
0x101487c4e  mov     eax, 0FFFFFFFFh
0x101487c53  mov     [rsp+20C8h+var_2098], ax
0x101487c58  xor     r8d, r8d
0x101487c5b  mov     [rsp+20C8h+var_2090], r8
0x101487c60  mov     [rsp+20C8h+var_2094], r8d
0x101487c65  mov     [rsp+20C8h+var_207A], r8
0x101487c6a  mov     [rsp+20C8h+var_2070], r8
0x101487c6f  mov     [rsp+20C8h+var_2088], r8
0x101487c74  mov     [rsp+20C8h+var_205C], r8d
0x101487c79  mov     [rsp+20C8h+var_2058], r8d
0x101487c7e  mov     [rsp+20C8h+var_2054], r8d
0x101487c83  mov     rax, [rcx+18h]
0x101487c87  mov     rcx, [rax+30h]
0x101487c8b  movzx   r15d, byte ptr [rcx+1CDEh]
0x101487c93  mov     edi, ebx
0x101487c95  and     edi, 0C2h
0x101487c9b  mov     [rsp+20C8h+var_2050], edi
0x101487c9f  test    rdx, rdx
0x101487ca2  jz      short loc_101487CAD
0x101487ca4  test    bl, 8
0x101487ca7  lea     r12d, [r8+1]
0x101487cab  jnz     short loc_101487CB0
0x101487cad  mov     r12d, r8d
0x101487cb0  mov     [rsp+20C8h+var_2060], r12d
0x101487cb5  mov     edx, 1
0x101487cba  mov     rcx, r14
0x101487cbd  call    ?GetRecord@HeapRowObject@@QEAAPEAVRecord@@W4CheckVisibilityOption@@_N@Z; HeapRowObject::GetRecord(CheckVisibilityOption,bool)
0x101487cc2  mov     rsi, rax
0x101487cc5  test    r15b, r15b
0x101487cc8  jz      short loc_101487D24
0x101487cca  xor     r8d, r8d; bool
0x101487ccd  xor     edx, edx; unsigned int
0x101487ccf  mov     rcx, r14; this
0x101487cd2  call    ?PrepareForUpdate@HeapRowObject@@QEAAJI_N@Z; HeapRowObject::PrepareForUpdate(uint,bool)
0x101487cd7  test    eax, eax
0x101487cd9  jz      short loc_101487CFF
0x101487cdb  xor     eax, eax
0x101487cdd  mov     [rsp+20C8h+var_20A8], rax
0x101487ce2  mov     r9d, 1D5Bh
0x101487ce8  lea     r8, aHeapdatasetCpp; "HeapDataSet.cpp"
0x101487cef  lea     rdx, ?szExpression@?6??DeleteRowInternal@HeapDataSetSession@@AEAAXPEAVHeapRowObject@@H_N@Z@4QBDB; "hr == S_OK"
0x101487cf6  lea     ecx, [rax+1]
0x101487cf9  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101487cff  xor     r8d, r8d
0x101487d02  lea     edx, [r8+1]
0x101487d06  mov     rcx, r14
0x101487d09  call    ?GetRecord@HeapRowObject@@QEAAPEAVRecord@@W4CheckVisibilityOption@@_N@Z; HeapRowObject::GetRecord(CheckVisibilityOption,bool)
0x101487d0e  mov     rsi, rax
0x101487d11  test    rax, rax
0x101487d14  jnz     short loc_101487D24
0x101487d16  mov     rax, [r14]
0x101487d19  mov     rcx, r14
0x101487d1c  call    qword ptr [rax+8]
0x101487d1f  jmp     loc_10148961E
0x101487d24  test    bl, 10h
0x101487d27  jnz     short loc_101487D3C
0x101487d29  test    edi, edi
0x101487d2b  jnz     short loc_101487D3C
0x101487d2d  test    r12d, r12d
0x101487d30  jnz     short loc_101487D3C
0x101487d32  bt      ebx, 8
0x101487d36  jnb     loc_1014893AD
0x101487d3c  movzx   eax, word ptr [rsi]
0x101487d3f  mov     [rsp+20C8h+var_2098], ax
0x101487d44  test    ax, ax
0x101487d47  jnz     loc_1014884DE
0x101487d4d  lea     rbx, [rsi+2]
0x101487d51  cmp     dword ptr [rbx+2], 0
0x101487d55  jnz     loc_101488392
0x101487d5b  xor     r10d, r10d
0x101487d5e  mov     [rbx], r10w
0x101487d62  mov     r8d, [rbx+0Eh]
0x101487d66  mov     [rbx+12h], r8d
0x101487d6a  mov     rdx, [rbx+6]
0x101487d6e  movzx   eax, byte ptr [rdx]
0x101487d71  mov     rcx, rdx
0x101487d74  test    al, 10h
0x101487d76  jz      short loc_101487D93
0x101487d78  movzx   ecx, word ptr [rdx+r8]
0x101487d7d  add     ecx, 7
0x101487d80  shr     ecx, 3
0x101487d83  add     ecx, 2
0x101487d86  add     r8d, ecx
0x101487d89  mov     [rbx+12h], r8d
0x101487d8d  movzx   eax, byte ptr [rdx]
0x101487d90  mov     rcx, rdx
0x101487d93  test    al, 20h
0x101487d95  jz      loc_101488159
0x101487d9b  mov     r14d, r8d
0x101487d9e  add     r14, rdx
0x101487da1  movzx   eax, word ptr [r14]
0x101487da5  mov     [rbx+1Ah], ax
0x101487da9  test    ax, ax
0x101487dac  jnz     loc_101487E6B
0x101487db2  cmp     cs:byte_10316E8D7, r10b
0x101487db9  jnz     short loc_101487DC8
0x101487dbb  test    byte ptr cs:qword_10317B120, 1
0x101487dc2  jz      loc_101487E52
0x101487dc8  mov     r8, gs:58h
0x101487dd1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101487dd8  mov     ecx, [rax]
0x101487dda  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101487de1  mov     edx, [rax]
0x101487de3  add     rdx, [r8+rcx*8]
0x101487de7  mov     rax, [rdx+8]
0x101487deb  test    rax, rax
0x101487dee  jz      short loc_101487E52
0x101487df0  mov     rax, [rax+60h]
0x101487df4  test    rax, rax
0x101487df7  jz      short loc_101487E52
0x101487df9  cmp     [rax+499h], r10b
0x101487e00  jz      short loc_101487E52
0x101487e02  cmp     cs:byte_10316E7C7, r10b
0x101487e09  jnz     short loc_101487E2E
0x101487e0b  test    byte ptr cs:qword_10317B120, 2
0x101487e12  jnz     short loc_101487E2E
0x101487e14  mov     edx, 44h ; 'D'
0x101487e19  lea     ecx, [rdx-22h]
0x101487e1c  mov     r9d, 3EBh
0x101487e22  lea     r8d, [rdx-2Fh]
0x101487e26  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101487e2c  jmp     short loc_101487E52
0x101487e2e  mov     [rsp+20C8h+var_20A8], r10
0x101487e33  mov     r9d, 7DAh
0x101487e39  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x101487e40  lea     rdx, aFalse; "false"
0x101487e47  mov     ecx, 1
0x101487e4c  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101487e52  mov     edx, 3
0x101487e57  mov     rcx, [rbx+6]
0x101487e5b  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x101487e60  mov     r8d, [rbx+12h]
0x101487e64  movzx   eax, word ptr [rbx+1Ah]
0x101487e68  xor     r10d, r10d
0x101487e6b  movzx   edx, ax
0x101487e6e  lea     eax, [rdx+1]
0x101487e71  lea     eax, [r8+rax*2]
0x101487e75  mov     [rbx+16h], eax
0x101487e78  cmp     eax, 1F9Eh
0x101487e7d  jbe     loc_101487F35
0x101487e83  cmp     cs:byte_10316E8D7, 0
0x101487e8a  jnz     short loc_101487E99
0x101487e8c  test    byte ptr cs:qword_10317B120, 1
0x101487e93  jz      loc_101487F23
0x101487e99  mov     r8, gs:58h
0x101487ea2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101487ea9  mov     ecx, [rax]
0x101487eab  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101487eb2  mov     edx, [rax]
0x101487eb4  add     rdx, [r8+rcx*8]
0x101487eb8  mov     rax, [rdx+8]
0x101487ebc  test    rax, rax
0x101487ebf  jz      short loc_101487F23
0x101487ec1  mov     rax, [rax+60h]
0x101487ec5  test    rax, rax
0x101487ec8  jz      short loc_101487F23
0x101487eca  cmp     byte ptr [rax+499h], 0
0x101487ed1  jz      short loc_101487F23
0x101487ed3  cmp     cs:byte_10316E7C7, 0
0x101487eda  jnz     short loc_101487EFF
0x101487edc  test    byte ptr cs:qword_10317B120, 2
0x101487ee3  jnz     short loc_101487EFF
0x101487ee5  mov     edx, 44h ; 'D'
0x101487eea  lea     ecx, [rdx-22h]
0x101487eed  mov     r9d, 3ECh
0x101487ef3  lea     r8d, [rdx-2Fh]
0x101487ef7  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101487efd  jmp     short loc_101487F23
0x101487eff  mov     [rsp+20C8h+var_20A8], r10
0x101487f04  mov     r9d, 7E1h
0x101487f0a  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x101487f11  lea     rdx, aFalse; "false"
0x101487f18  mov     ecx, 1
0x101487f1d  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101487f23  mov     edx, 4
0x101487f28  mov     rcx, [rbx+6]
0x101487f2c  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x101487f31  movzx   edx, word ptr [rsi+1Ch]
0x101487f35  movzx   eax, dx
0x101487f38  movzx   ecx, word ptr [r14+rax*2]
0x101487f3d  and     ecx, 7FFFh
0x101487f43  mov     [rbx+2], ecx
0x101487f46  cmp     [rbx+16h], ecx
0x101487f49  jbe     loc_101488001
0x101487f4f  cmp     cs:byte_10316E8D7, 0
0x101487f56  jnz     short loc_101487F65
0x101487f58  test    byte ptr cs:qword_10317B120, 1
0x101487f5f  jz      loc_101487FEF
0x101487f65  mov     r8, gs:58h
0x101487f6e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101487f75  mov     ecx, [rax]
0x101487f77  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101487f7e  mov     edx, [rax]
0x101487f80  add     rdx, [r8+rcx*8]
0x101487f84  mov     rax, [rdx+8]
0x101487f88  test    rax, rax
0x101487f8b  jz      short loc_101487FEF
0x101487f8d  mov     rax, [rax+60h]
0x101487f91  test    rax, rax
0x101487f94  jz      short loc_101487FEF
0x101487f96  cmp     byte ptr [rax+499h], 0
0x101487f9d  jz      short loc_101487FEF
0x101487f9f  cmp     cs:byte_10316E7C7, 0
0x101487fa6  jnz     short loc_101487FCB
0x101487fa8  test    byte ptr cs:qword_10317B120, 2
0x101487faf  jnz     short loc_101487FCB
0x101487fb1  mov     edx, 44h ; 'D'
0x101487fb6  lea     ecx, [rdx-22h]
0x101487fb9  mov     r9d, 3ECh
0x101487fbf  lea     r8d, [rdx-2Fh]
0x101487fc3  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101487fc9  jmp     short loc_101487FEF
0x101487fcb  xor     eax, eax
0x101487fcd  mov     [rsp+20C8h+var_20A8], rax
0x101487fd2  mov     r9d, 7E8h
0x101487fd8  lea     r8, aSqlNtdbmsStore_517; "Sql\\Ntdbms\\storeng\\drs\\fixedvarreco"...
0x101487fdf  lea     rdx, aFalse; "false"
0x101487fe6  lea     ecx, [rax+1]
0x101487fe9  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101487fef  mov     edx, 4
0x101487ff4  mov     rcx, [rbx+6]
0x101487ff8  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x101487ffd  movzx   edx, word ptr [rsi+1Ch]
0x101488001  movzx   eax, dx
0x101488004  dec     eax
0x101488006  cmp     word ptr [r14+rax*2+2], 0
0x10148800d  jge     loc_1014880CB
0x101488013  mov     r10d, 400h
0x101488019  nop     dword ptr [rax+00000000h]
0x101488020  movzx   ecx, dx
0x101488023  mov     r9, [rbx+6]
0x101488027  mov     eax, [rbx+12h]
0x10148802a  add     rax, r9
0x10148802d  cmp     ecx, 1
0x101488030  jnz     short loc_101488043
0x101488032  mov     edi, [rbx+16h]
0x101488035  mov     r8d, edi
0x101488038  movzx   eax, word ptr [rax+rcx*2]
0x10148803c  and     eax, 7FFFh
0x101488041  jmp     short loc_101488060
0x101488043  movzx   edi, word ptr [rax+rcx*2-2]
0x101488048  and     edi, 7FFFh
0x10148804e  mov     r8d, [rsi+18h]
0x101488052  movzx   eax, word ptr [rax+rcx*2]
0x101488056  and     eax, 7FFFh
0x10148805b  cmp     edi, r8d
0x10148805e  jb      short loc_101488064
0x101488060  cmp     eax, edi
0x101488062  jnb     short loc_101488083
0x101488064  mov     edx, 7
0x101488069  mov     rcx, r9
0x10148806c  call    ?RaiseInconsistencyError@@YAXPEBXW4IRN_REF_NUM@@@Z; RaiseInconsistencyError(void const *,IRN_REF_NUM)
0x101488071  mov     r8d, [rsi+18h]
0x101488075  mov     r9, [rsi+8]
0x101488079  movzx   edx, word ptr [rsi+1Ch]
0x10148807d  mov     r10d, 400h
0x101488083  cmp     edi, r8d
0x101488086  jb      loc_101488392
0x10148808c  cmp     edi, [rbx+2]
0x10148808f  ja      loc_101488392
0x101488095  mov     eax, edi
0x101488097  movzx   ecx, word ptr [r9+rax]
0x10148809c  cmp     cx, 5
0x1014880a0  jz      short loc_1014880EC
0x1014880a2  cmp     cx, r10w
0x1014880a6  jb      short loc_1014880CB
0x1014880a8  or      word ptr [rbx], 1
0x1014880ac  sub     dx, 1
0x1014880b0  movzx   eax, dx
0x1014880b3  mov     [rbx+1Ah], ax
0x1014880b7  jz      short loc_1014880CB
0x1014880b9  movzx   edx, ax
0x1014880bc  dec     eax
0x1014880be  cmp     word ptr [r14+rax*2+2], 0
0x1014880c5  jl      loc_101488020
  ... truncated ...
```
