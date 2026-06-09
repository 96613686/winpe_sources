# SegLibPvtDeferredChecksumMdlChain

- ea: `0x140008ac0`
- end: `0x1400095b5`
- name: `SegLibPvtDeferredChecksumMdlChain`
- size: `2805`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140003d9c`
- `0x1400082b8`
- `0x1401b9e8c`

## callees

- `0x140006620`
- `0x140008ac0`
- `0x1401bbcb0`
- `0x1401bbe10`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140008dda`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140008f53`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140009155`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140008dda`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140008f53`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140009155`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400090ce`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400090fa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400090ce`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400090fa`

## pseudocode

```c
__int64 __fastcall SegLibPvtDeferredChecksumMdlChain(
        __int64 a1,
        char a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int16 *a6,
        __int16 *a7)
{
  struct _MDL *v7; // rdi
  __int64 v8; // rsi
  char *v10; // rax
  unsigned int ByteCount; // ecx
  __int64 v12; // rdx
  char *MappedSystemVa; // r14
  unsigned int v14; // ecx
  char *v15; // rsi
  unsigned int v16; // r12d
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned int v20; // eax
  _DWORD *v21; // rdx
  unsigned int v22; // ebp
  __int64 v23; // rcx
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rbp
  __int64 v30; // rcx
  __int64 v31; // rax
  bool v32; // zf
  __int64 v33; // rax
  __int64 v34; // rcx
  unsigned int v35; // eax
  _DWORD *v36; // rdx
  unsigned int v37; // edi
  __int64 v38; // rcx
  __int64 v39; // r9
  __int64 v40; // rax
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // rax
  __int64 v46; // rdx
  char v47; // cl
  char v48; // al
  char v49; // cl
  unsigned int v51; // edi
  _DWORD *v52; // rax
  int v53; // ecx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // r9
  volatile signed __int32 *v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rcx
  unsigned int v60; // eax
  _DWORD *v61; // rdx
  unsigned int v62; // ebp
  __int64 v63; // rcx
  __int64 v64; // r9
  __int64 v65; // rax
  __int64 v66; // r9
  __int64 v67; // rcx
  __int64 v68; // rdx
  int v69; // ecx
  unsigned int v70; // ecx
  _DWORD *v71; // rax
  int v72; // ecx
  __int64 v73; // r8
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // r8
  __int64 v77; // r9
  volatile signed __int32 *v78; // rcx
  __int64 v79; // r8
  bool v80; // si
  __int16 *v81; // rcx
  unsigned __int16 v82; // ax
  __int16 v83; // ax
  char *v84; // rax
  _DWORD *v85; // rax
  int v86; // ecx
  __int64 v87; // rcx
  __int64 v88; // rax
  __int64 v89; // r9
  volatile signed __int32 *v90; // rcx
  bool v91; // bp
  __int16 *v92; // rdx
  unsigned __int16 v93; // ax
  __int16 v94; // ax
  unsigned __int16 v95; // ax
  __int16 v96; // ax
  unsigned __int16 v97; // ax
  __int16 v98; // ax
  __int16 *v99; // r8
  __int16 v100; // cx
  __int16 v101; // cx
  __int16 v102; // cx
  __int16 v103; // cx
  __int16 *v104; // rdx
  __int16 v105; // cx
  __int16 v106; // cx
  __int16 v107; // dx
  __int16 v108; // dx
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // rcx
  unsigned int v112; // [rsp+30h] [rbp-38h]

  v7 = (struct _MDL *)a3;
  v8 = a4;
  if ( !a5 )
    return 0;
  if ( !a3 )
  {
    v51 = -1073741811;
    goto LABEL_58;
  }
  if ( (*(_BYTE *)(a3 + 10) & 5) != 0 )
    v10 = *(char **)(a3 + 24);
  else
    v10 = (char *)MmMapLockedPagesSpecifyCache((PMDL)a3, 0, MmCached, 0, 0, 0x40000000u);
  if ( !v10 || (ByteCount = v7->ByteCount, ByteCount <= (unsigned int)v8) )
  {
LABEL_57:
    v51 = -1073741670;
LABEL_58:
    LOBYTE(a3) = 1;
    BLFlushBatchOpContextEx(a1, 0, a3);
    return v51;
  }
  v12 = a5;
  MappedSystemVa = &v10[v8];
  v14 = ByteCount - v8;
  v112 = a5;
  v15 = (char *)a6;
  while ( 1 )
  {
    v16 = v12;
    if ( v14 <= (unsigned int)v12 )
      v16 = v14;
    if ( v15 )
    {
      if ( !a1 )
        goto LABEL_56;
      v17 = *(_QWORD *)(a1 + 80);
      if ( *(_BYTE *)(v17 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
      {
        a3 = *(unsigned int *)(a1 + 12);
        v18 = 0;
        *(_BYTE *)(a1 + 4) = 1;
        if ( (_DWORD)a3 != -1 )
        {
          v12 = *(_QWORD *)(v17 + 24);
          if ( v12 )
            v18 = v12 + 20 * a3;
        }
        _InterlockedIncrement16((volatile signed __int16 *)(v18 + 16));
      }
      v19 = *(_QWORD *)(a1 + 80);
      v20 = *(_DWORD *)(v19 + 4);
      if ( v20 )
      {
        v21 = *(_DWORD **)(a1 + 32);
        v22 = v21[2];
        if ( v22 >= v21[3] )
        {
          v22 = 0;
          if ( *(_DWORD *)(a1 + 16) < v20
            && (v52 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v19 + 64)), (v21 = v52) != 0) )
          {
            *(_QWORD *)v52 = 0;
            v52[2] = 0;
            v53 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
            *((_QWORD *)v52 + 2) = v52 + 6;
            v52[3] = v53;
            **(_QWORD **)(a1 + 32) = v52;
            a3 = *(_QWORD *)(a1 + 80);
            ++*(_DWORD *)(a1 + 16);
            *(_QWORD *)(a1 + 32) = v52;
            if ( *(_BYTE *)(a3 + 1) == 1 )
            {
              v54 = *(unsigned int *)(a1 + 12);
              v55 = 0;
              if ( (_DWORD)v54 != -1 )
              {
                a3 = *(_QWORD *)(a3 + 24);
                if ( a3 )
                  v55 = a3 + 20 * v54;
              }
              _InterlockedIncrement16((volatile signed __int16 *)(v55 + 12));
              v56 = *(unsigned int *)(a1 + 12);
              v57 = 0;
              if ( (_DWORD)v56 != -1 )
              {
                a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                if ( a3 )
                  v57 = (volatile signed __int32 *)(a3 + 20 * v56);
              }
              _InterlockedIncrement(v57);
            }
          }
          else
          {
            LOBYTE(v21) = 1;
            BLFlushBatchOpContextEx(a1, v21, 0);
            v21 = (_DWORD *)(a1 + 56);
          }
        }
        ++*(_DWORD *)(a1 + 20);
        ++v21[2];
        v23 = *(_QWORD *)(a1 + 80);
        if ( *(_BYTE *)(v23 + 1) == 1 )
        {
          v24 = *(unsigned int *)(a1 + 12);
          v25 = 0;
          if ( (_DWORD)v24 != -1 )
          {
            a3 = *(_QWORD *)(v23 + 24);
            if ( a3 )
              v25 = a3 + 20 * v24;
          }
          _InterlockedIncrement16((volatile signed __int16 *)(v25 + 14));
          v26 = *(unsigned int *)(a1 + 12);
          v27 = 0;
          if ( (_DWORD)v26 != -1 )
          {
            a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
            if ( a3 )
              v27 = a3 + 20 * v26;
          }
          _InterlockedIncrement((volatile signed __int32 *)(v27 + 4));
        }
        v28 = v22;
        v29 = v16;
        v30 = 3 * v28;
        v31 = *((_QWORD *)v21 + 2);
        *(_QWORD *)(v31 + 8 * v30) = v15;
        *(_QWORD *)(v31 + 8 * v30 + 8) = MappedSystemVa;
        *(_DWORD *)(v31 + 8 * v30 + 16) = (16 * v16) | 1;
        goto LABEL_29;
      }
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(v12) = 1;
        BLFlushBatchOpContextEx(a1, v12, 0);
      }
      if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
      {
        v29 = v16;
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
        memmove(v15, MappedSystemVa, v16);
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
      }
      else
      {
LABEL_56:
        v29 = v16;
        memmove(v15, MappedSystemVa, v16);
      }
LABEL_29:
      v15 += v29;
      goto LABEL_30;
    }
    v58 = *(_QWORD *)(a1 + 80);
    if ( *(_BYTE *)(v58 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      a3 = *(unsigned int *)(a1 + 12);
      v109 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)a3 != -1 )
      {
        v12 = *(_QWORD *)(v58 + 24);
        if ( v12 )
          v109 = v12 + 20 * a3;
      }
      _InterlockedIncrement16((volatile signed __int16 *)(v109 + 16));
    }
    v59 = *(_QWORD *)(a1 + 80);
    v60 = *(_DWORD *)(v59 + 4);
    if ( v60 )
    {
      v61 = *(_DWORD **)(a1 + 32);
      v62 = v61[2];
      if ( v62 >= v61[3] )
      {
        v62 = 0;
        if ( *(_DWORD *)(a1 + 16) < v60
          && (v85 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v59 + 64)), (v61 = v85) != 0) )
        {
          *(_QWORD *)v85 = 0;
          v85[2] = 0;
          v86 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
          *((_QWORD *)v85 + 2) = v85 + 6;
          v85[3] = v86;
          **(_QWORD **)(a1 + 32) = v85;
          a3 = *(_QWORD *)(a1 + 80);
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v85;
          if ( *(_BYTE *)(a3 + 1) == 1 )
          {
            v87 = *(unsigned int *)(a1 + 12);
            v88 = 0;
            if ( (_DWORD)v87 != -1 )
            {
              a3 = *(_QWORD *)(a3 + 24);
              if ( a3 )
                v88 = a3 + 20 * v87;
            }
            _InterlockedIncrement16((volatile signed __int16 *)(v88 + 12));
            v89 = *(unsigned int *)(a1 + 12);
            v90 = 0;
            if ( (_DWORD)v89 != -1 )
            {
              a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
              if ( a3 )
                v90 = (volatile signed __int32 *)(a3 + 20 * v89);
            }
            _InterlockedIncrement(v90);
          }
        }
        else
        {
          LOBYTE(v61) = 1;
          BLFlushBatchOpContextEx(a1, v61, 0);
          v61 = (_DWORD *)(a1 + 56);
        }
      }
      ++*(_DWORD *)(a1 + 20);
      ++v61[2];
      v63 = *(_QWORD *)(a1 + 80);
      if ( *(_BYTE *)(v63 + 1) == 1 )
      {
        v64 = *(unsigned int *)(a1 + 12);
        v65 = 0;
        if ( (_DWORD)v64 != -1 )
        {
          a3 = *(_QWORD *)(v63 + 24);
          if ( a3 )
            v65 = a3 + 20 * v64;
        }
        _InterlockedIncrement16((volatile signed __int16 *)(v65 + 14));
        v66 = *(unsigned int *)(a1 + 12);
        v67 = 0;
        if ( (_DWORD)v66 != -1 )
        {
          a3 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
          if ( a3 )
            v67 = a3 + 20 * v66;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v67 + 4));
      }
      v68 = *((_QWORD *)v61 + 2) + 24LL * v62;
      v69 = *(_DWORD *)(v68 + 16);
      v70 = a2 ? v69 & 0xFFFFFFF0 | 7 : v69 & 0xFFFFFFF0 | 6;
      *(_DWORD *)(v68 + 16) = v70;
      *(_QWORD *)v68 = a7;
      *(_QWORD *)(v68 + 8) = MappedSystemVa;
      *(_DWORD *)(v68 + 16) = (16 * v16) | v70 & 0xF;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(v12) = 1;
        BLFlushBatchOpContextEx(a1, v12, 0);
      }
      v91 = (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_DWORD *)(a1 + 8) & 6) == 6;
      v92 = *(__int16 **)(a1 + 48);
      if ( v92 && v92 != a7 )
      {
        if ( v91 )
        {
          (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
          v99 = *(__int16 **)(a1 + 48);
          v100 = *v99;
          if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
            v100 = __ROR2__(v100, 8);
          v101 = ~v100;
          if ( *(_BYTE *)(a1 + 40) && !v101 )
            v101 = -1;
          *v99 = v101;
          *(_QWORD *)(a1 + 48) = 0;
          *(_DWORD *)(a1 + 44) = 0;
          (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
        }
        else
        {
          v102 = *v92;
          if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
            v102 = __ROR2__(v102, 8);
          v103 = ~v102;
          if ( *(_BYTE *)(a1 + 40) && !v103 )
            v103 = -1;
          *v92 = v103;
          *(_DWORD *)(a1 + 44) = 0;
        }
      }
      *(_BYTE *)(a1 + 40) = a2 != 0;
      *(_QWORD *)(a1 + 48) = a7;
      if ( v91 )
      {
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
        if ( a7 < (__int16 *)MappedSystemVa || (v95 = 0, a7 >= (__int16 *)&MappedSystemVa[v16]) )
          v95 = *a7;
        v96 = tcpxsum(v95, MappedSystemVa, v16);
        *a7 = v96;
        if ( (v16 & 1) != 0 )
        {
          *a7 = __ROR2__(v96, 8);
          ++*(_DWORD *)(a1 + 44);
        }
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
      }
      else
      {
        if ( a7 < (__int16 *)MappedSystemVa || a7 >= (__int16 *)&MappedSystemVa[v16] )
          v93 = *a7;
        else
          v93 = 0;
        v94 = tcpxsum(v93, MappedSystemVa, v16);
        *a7 = v94;
        if ( (v16 & 1) != 0 )
        {
          *a7 = __ROR2__(v94, 8);
          ++*(_DWORD *)(a1 + 44);
        }
      }
    }
LABEL_30:
    v32 = v112 == v16;
    v12 = v112 - v16;
    v112 -= v16;
    if ( v32 )
      break;
    v7 = v7->Next;
    if ( !v7 )
      goto LABEL_57;
    if ( (v7->MdlFlags & 5) != 0 )
    {
      MappedSystemVa = (char *)v7->MappedSystemVa;
    }
    else
    {
      v84 = (char *)MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000000u);
      v12 = v112;
      MappedSystemVa = v84;
    }
    if ( !MappedSystemVa )
      goto LABEL_57;
    v14 = v7->ByteCount;
  }
  if ( v15 )
  {
    v33 = *(_QWORD *)(a1 + 80);
    if ( *(_BYTE *)(v33 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      v110 = *(unsigned int *)(a1 + 12);
      v111 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)v110 != -1 )
      {
        v12 = *(_QWORD *)(v33 + 24);
        if ( v12 )
          v111 = v12 + 20 * v110;
      }
      _InterlockedIncrement16((volatile signed __int16 *)(v111 + 16));
    }
    v34 = *(_QWORD *)(a1 + 80);
    v35 = *(_DWORD *)(v34 + 4);
    if ( v35 )
    {
      v36 = *(_DWORD **)(a1 + 32);
      v37 = v36[2];
      if ( v37 >= v36[3] )
      {
        v37 = 0;
        if ( *(_DWORD *)(a1 + 16) < v35
          && (v71 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v34 + 64)), (v36 = v71) != 0) )
        {
          *(_QWORD *)v71 = 0;
          v71[2] = 0;
          v72 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
          *((_QWORD *)v71 + 2) = v71 + 6;
          v71[3] = v72;
          **(_QWORD **)(a1 + 32) = v71;
          v73 = *(_QWORD *)(a1 + 80);
          ++*(_DWORD *)(a1 + 16);
          *(_QWORD *)(a1 + 32) = v71;
          if ( *(_BYTE *)(v73 + 1) == 1 )
          {
            v74 = *(unsigned int *)(a1 + 12);
            v75 = 0;
            if ( (_DWORD)v74 != -1 )
            {
              v76 = *(_QWORD *)(v73 + 24);
              if ( v76 )
                v75 = v76 + 20 * v74;
            }
            _InterlockedIncrement16((volatile signed __int16 *)(v75 + 12));
            v77 = *(unsigned int *)(a1 + 12);
            v78 = 0;
            if ( (_DWORD)v77 != -1 )
            {
              v79 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
              if ( v79 )
                v78 = (volatile signed __int32 *)(v79 + 20 * v77);
            }
            _InterlockedIncrement(v78);
          }
        }
        else
        {
          LOBYTE(v36) = 1;
          BLFlushBatchOpContextEx(a1, v36, 0);
          v36 = (_DWORD *)(a1 + 56);
        }
      }
      ++*(_DWORD *)(a1 + 20);
      ++v36[2];
      v38 = *(_QWORD *)(a1 + 80);
      if ( *(_BYTE *)(v38 + 1) == 1 )
      {
        v39 = *(unsigned int *)(a1 + 12);
        v40 = 0;
        if ( (_DWORD)v39 != -1 )
        {
          v41 = *(_QWORD *)(v38 + 24);
          if ( v41 )
            v40 = v41 + 20 * v39;
        }
        _InterlockedIncrement16((volatile signed __int16 *)(v40 + 14));
        v42 = *(unsigned int *)(a1 + 12);
        v43 = 0;
        if ( (_DWORD)v42 != -1 )
        {
          v44 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
          if ( v44 )
            v43 = v44 + 20 * v42;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v43 + 4));
      }
      v45 = *((_QWORD *)v36 + 2);
      *(_QWORD *)(v45 + 24LL * v37 + 8) = a6;
      v46 = v45 + 24LL * v37;
      LODWORD(v45) = *(_DWORD *)(v46 + 16);
      v47 = v45 & 0xF6;
      v48 = v45 & 0xF0 | 7;
      v49 = v47 | 6;
      if ( a2 )
        v49 = v48;
      *(_QWORD *)v46 = a7;
      *(_DWORD *)(v46 + 16) = (16 * a5) | v49 & 0xF;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(v12) = 1;
        BLFlushBatchOpContextEx(a1, v12, 0);
      }
      v80 = (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_DWORD *)(a1 + 8) & 6) == 6;
      v81 = *(__int16 **)(a1 + 48);
      if ( v81 && v81 != a7 )
      {
        if ( v80 )
        {
          (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
          v104 = *(__int16 **)(a1 + 48);
          v105 = *v104;
          if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
            v105 = __ROR2__(v105, 8);
          v106 = ~v105;
          if ( *(_BYTE *)(a1 + 40) && !v106 )
            v106 = -1;
          *v104 = v106;
          *(_QWORD *)(a1 + 48) = 0;
          *(_DWORD *)(a1 + 44) = 0;
          (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
        }
        else
        {
          v107 = *v81;
          if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
            v107 = __ROR2__(v107, 8);
          v108 = ~v107;
          if ( *(_BYTE *)(a1 + 40) && !v108 )
            v108 = -1;
          *v81 = v108;
          *(_DWORD *)(a1 + 44) = 0;
        }
      }
      *(_BYTE *)(a1 + 40) = a2 != 0;
      *(_QWORD *)(a1 + 48) = a7;
      if ( v80 )
      {
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
        if ( a7 < a6 || (v97 = 0, a7 >= (__int16 *)((char *)a6 + a5)) )
          v97 = *a7;
        v98 = tcpxsum(v97, a6, a5);
        *a7 = v98;
        if ( (a5 & 1) != 0 )
        {
          *a7 = __ROR2__(v98, 8);
          ++*(_DWORD *)(a1 + 44);
        }
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
      }
      else
      {
        if ( a7 < a6 || a7 >= (__int16 *)((char *)a6 + a5) )
          v82 = *a7;
        else
          v82 = 0;
        v83 = tcpxsum(v82, a6, a5);
        *a7 = v83;
        if ( (a5 & 1) != 0 )
        {
          *a7 = __ROR2__(v83, 8);
          ++*(_DWORD *)(a1 + 44);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140008ac0  mov     rax, rsp
0x140008ac3  mov     [rax+10h], dl
0x140008ac6  push    rbx
0x140008ac7  push    rsi
0x140008ac8  push    rdi
0x140008ac9  push    r13
0x140008acb  push    r15
0x140008acd  sub     rsp, 40h
0x140008ad1  mov     r15d, [rsp+68h+arg_20]
0x140008ad9  mov     rdi, r8
0x140008adc  mov     esi, r9d
0x140008adf  mov     rbx, rcx
0x140008ae2  test    r15d, r15d
0x140008ae5  jz      loc_140009289
0x140008aeb  mov     [rax+8], rbp
0x140008aef  mov     [rax+18h], r12
0x140008af3  mov     [rax+20h], r14
0x140008af7  test    r8, r8
0x140008afa  jz      loc_1400094E9
0x140008b00  xor     r13d, r13d
0x140008b03  test    byte ptr [r8+0Ah], 5
0x140008b08  jz      loc_1400090B3
0x140008b0e  mov     rax, [r8+18h]
0x140008b12  test    rax, rax
0x140008b15  jz      loc_140008DB4
0x140008b1b  mov     ecx, [rdi+28h]
0x140008b1e  cmp     ecx, esi
0x140008b20  jbe     loc_140008DB4
0x140008b26  mov     edx, r15d
0x140008b29  lea     r14, [rax+rsi]
0x140008b2d  sub     ecx, esi
0x140008b2f  mov     [rsp+68h+var_38], edx
0x140008b33  mov     rsi, [rsp+68h+arg_28]
0x140008b3b  cmp     ecx, edx
0x140008b3d  mov     r12d, edx
0x140008b40  cmovbe  r12d, ecx
0x140008b44  test    rsi, rsi
0x140008b47  jz      loc_140008E73
0x140008b4d  test    rbx, rbx
0x140008b50  jz      loc_140008D9E
0x140008b56  mov     rax, [rbx+50h]
0x140008b5a  cmp     byte ptr [rax+1], 1
0x140008b5e  jnz     short loc_140008B8D
0x140008b60  cmp     [rbx+4], r13b
0x140008b64  jnz     short loc_140008B8D
0x140008b66  mov     r8d, [rbx+0Ch]
0x140008b6a  mov     rcx, r13
0x140008b6d  mov     byte ptr [rbx+4], 1
0x140008b71  cmp     r8d, 0FFFFFFFFh
0x140008b75  jz      short loc_140008B88
0x140008b77  mov     rdx, [rax+18h]
0x140008b7b  test    rdx, rdx
0x140008b7e  jz      short loc_140008B88
0x140008b80  lea     rcx, [r8+r8*4]
0x140008b84  lea     rcx, [rdx+rcx*4]
0x140008b88  lock inc word ptr [rcx+10h]
0x140008b8d  mov     rcx, [rbx+50h]
0x140008b91  mov     eax, [rcx+4]
0x140008b94  test    eax, eax
0x140008b96  jz      loc_140008D6F
0x140008b9c  mov     rdx, [rbx+20h]
0x140008ba0  mov     ebp, [rdx+8]
0x140008ba3  cmp     ebp, [rdx+0Ch]
0x140008ba6  jnb     loc_140008DCA
0x140008bac  inc     dword ptr [rbx+14h]
0x140008baf  inc     dword ptr [rdx+8]
0x140008bb2  mov     rcx, [rbx+50h]
0x140008bb6  cmp     byte ptr [rcx+1], 1
0x140008bba  jnz     short loc_140008C05
0x140008bbc  mov     r9d, [rbx+0Ch]
0x140008bc0  mov     rax, r13
0x140008bc3  cmp     r9d, 0FFFFFFFFh
0x140008bc7  jz      short loc_140008BDA
0x140008bc9  mov     r8, [rcx+18h]
0x140008bcd  test    r8, r8
0x140008bd0  jz      short loc_140008BDA
0x140008bd2  lea     rcx, [r9+r9*4]
0x140008bd6  lea     rax, [r8+rcx*4]
0x140008bda  lock inc word ptr [rax+0Eh]
0x140008bdf  mov     r9d, [rbx+0Ch]
0x140008be3  mov     rcx, r13
0x140008be6  cmp     r9d, 0FFFFFFFFh
0x140008bea  jz      short loc_140008C01
0x140008bec  mov     rax, [rbx+50h]
0x140008bf0  mov     r8, [rax+18h]
0x140008bf4  test    r8, r8
0x140008bf7  jz      short loc_140008C01
0x140008bf9  lea     rcx, [r9+r9*4]
0x140008bfd  lea     rcx, [r8+rcx*4]
0x140008c01  lock inc dword ptr [rcx+4]
0x140008c05  mov     eax, ebp
0x140008c07  mov     ebp, r12d
0x140008c0a  lea     rcx, [rax+rax*2]
0x140008c0e  mov     rax, [rdx+10h]
0x140008c12  mov     [rax+rcx*8], rsi
0x140008c16  mov     [rax+rcx*8+8], r14
0x140008c1b  lea     rdx, [rax+rcx*8]
0x140008c1f  mov     eax, r12d
0x140008c22  shl     eax, 4
0x140008c25  or      eax, 1
0x140008c28  mov     [rdx+10h], eax
0x140008c2b  add     rsi, rbp
0x140008c2e  mov     edx, [rsp+68h+var_38]
0x140008c32  sub     edx, r12d
0x140008c35  mov     [rsp+68h+var_38], edx
0x140008c39  jz      short loc_140008C66
0x140008c3b  mov     rdi, [rdi]
0x140008c3e  test    rdi, rdi
0x140008c41  jz      loc_140008DB4
0x140008c47  test    byte ptr [rdi+0Ah], 5
0x140008c4b  jz      loc_1400090DF
0x140008c51  mov     r14, [rdi+18h]
0x140008c55  test    r14, r14
0x140008c58  jz      loc_140008DB4
0x140008c5e  mov     ecx, [rdi+28h]
0x140008c61  jmp     loc_140008B3B
0x140008c66  test    rsi, rsi
0x140008c69  jz      loc_140008D4A
0x140008c6f  mov     rax, [rbx+50h]
0x140008c73  cmp     byte ptr [rax+1], 1
0x140008c77  jz      loc_14000956C
0x140008c7d  mov     rcx, [rbx+50h]
0x140008c81  mov     eax, [rcx+4]
0x140008c84  test    eax, eax
0x140008c86  jz      loc_140008FEC
0x140008c8c  mov     rdx, [rbx+20h]
0x140008c90  mov     edi, [rdx+8]
0x140008c93  cmp     edi, [rdx+0Ch]
0x140008c96  jnb     loc_140008F43
0x140008c9c  inc     dword ptr [rbx+14h]
0x140008c9f  inc     dword ptr [rdx+8]
0x140008ca2  mov     rcx, [rbx+50h]
0x140008ca6  cmp     byte ptr [rcx+1], 1
0x140008caa  jnz     short loc_140008CF5
0x140008cac  mov     r9d, [rbx+0Ch]
0x140008cb0  mov     rax, r13
0x140008cb3  cmp     r9d, 0FFFFFFFFh
0x140008cb7  jz      short loc_140008CCA
0x140008cb9  mov     r8, [rcx+18h]
0x140008cbd  test    r8, r8
0x140008cc0  jz      short loc_140008CCA
0x140008cc2  lea     rcx, [r9+r9*4]
0x140008cc6  lea     rax, [r8+rcx*4]
0x140008cca  lock inc word ptr [rax+0Eh]
0x140008ccf  mov     r9d, [rbx+0Ch]
0x140008cd3  mov     rcx, r13
0x140008cd6  cmp     r9d, 0FFFFFFFFh
0x140008cda  jz      short loc_140008CF1
0x140008cdc  mov     rax, [rbx+50h]
0x140008ce0  mov     r8, [rax+18h]
0x140008ce4  test    r8, r8
0x140008ce7  jz      short loc_140008CF1
0x140008ce9  lea     rcx, [r9+r9*4]
0x140008ced  lea     rcx, [r8+rcx*4]
0x140008cf1  lock inc dword ptr [rcx+4]
0x140008cf5  mov     r15d, [rsp+68h+arg_20]
0x140008cfd  mov     r9, [rsp+68h+arg_28]
0x140008d05  mov     eax, edi
0x140008d07  lea     rcx, [rax+rax*2]
0x140008d0b  mov     rax, [rdx+10h]
0x140008d0f  mov     [rax+rcx*8+8], r9
0x140008d14  lea     rdx, [rax+rcx*8]
0x140008d18  mov     ecx, [rax+rcx*8+10h]
0x140008d1c  mov     eax, ecx
0x140008d1e  and     ecx, 0FFFFFFF6h
0x140008d21  and     eax, 0FFFFFFF7h
0x140008d24  or      eax, 7
0x140008d27  or      ecx, 6
0x140008d2a  cmp     [rsp+68h+arg_8], r13b
0x140008d2f  cmovnz  ecx, eax
0x140008d32  mov     rax, [rsp+68h+arg_30]
0x140008d3a  and     ecx, 0Fh
0x140008d3d  shl     r15d, 4
0x140008d41  or      ecx, r15d
0x140008d44  mov     [rdx], rax
0x140008d47  mov     [rdx+10h], ecx
0x140008d4a  mov     eax, r13d
0x140008d4d  mov     r12, [rsp+68h+arg_10]
0x140008d55  mov     rbp, [rsp+68h+arg_0]
0x140008d5a  mov     r14, [rsp+68h+arg_18]
0x140008d62  add     rsp, 40h
0x140008d66  pop     r15
0x140008d68  pop     r13
0x140008d6a  pop     rdi
0x140008d6b  pop     rsi
0x140008d6c  pop     rbx
0x140008d6d  retn
0x140008d6f  cmp     [rbx+14h], r13d
0x140008d73  jz      short loc_140008D82
0x140008d75  xor     r8d, r8d
0x140008d78  mov     dl, 1
0x140008d7a  mov     rcx, rbx
0x140008d7d  call    BLFlushBatchOpContextEx
0x140008d82  mov     eax, [rbx+8]
0x140008d85  and     eax, 5
0x140008d88  cmp     al, 5
0x140008d8a  jz      loc_1400094F3
0x140008d90  mov     eax, [rbx+8]
0x140008d93  and     eax, 6
0x140008d96  cmp     al, 6
0x140008d98  jz      loc_1400094F3
0x140008d9e  mov     r8d, r12d; Size
0x140008da1  mov     rdx, r14; Src
0x140008da4  mov     rcx, rsi; void *
0x140008da7  mov     ebp, r12d
0x140008daa  call    memmove
0x140008daf  jmp     loc_140008C2B
0x140008db4  mov     edi, 0C000009Ah
0x140008db9  mov     r8b, 1
0x140008dbc  xor     edx, edx
0x140008dbe  mov     rcx, rbx
0x140008dc1  call    BLFlushBatchOpContextEx
0x140008dc6  mov     eax, edi
0x140008dc8  jmp     short loc_140008D4D
0x140008dca  mov     ebp, r13d
0x140008dcd  cmp     [rbx+10h], eax
0x140008dd0  jnb     loc_14000909D
0x140008dd6  add     rcx, 40h ; '@'; Lookaside
0x140008dda  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140008de1  nop     dword ptr [rax+rax+00h]
0x140008de6  mov     rdx, rax
0x140008de9  test    rax, rax
0x140008dec  jz      loc_14000909D
0x140008df2  mov     [rax], r13
0x140008df5  mov     [rax+8], r13d
0x140008df9  mov     rax, [rbx+50h]
0x140008dfd  mov     ecx, [rax+8]
0x140008e00  lea     rax, [rdx+18h]
0x140008e04  mov     [rdx+10h], rax
0x140008e08  mov     [rdx+0Ch], ecx
0x140008e0b  mov     rax, [rbx+20h]
0x140008e0f  mov     [rax], rdx
0x140008e12  mov     r8, [rbx+50h]
0x140008e16  inc     dword ptr [rbx+10h]
0x140008e19  mov     [rbx+20h], rdx
0x140008e1d  cmp     byte ptr [r8+1], 1
0x140008e22  jnz     loc_140008BAC
0x140008e28  mov     ecx, [rbx+0Ch]
0x140008e2b  mov     rax, r13
0x140008e2e  cmp     ecx, 0FFFFFFFFh
0x140008e31  jz      short loc_140008E44
0x140008e33  mov     r8, [r8+18h]
0x140008e37  test    r8, r8
0x140008e3a  jz      short loc_140008E44
0x140008e3c  lea     rcx, [rcx+rcx*4]
0x140008e40  lea     rax, [r8+rcx*4]
0x140008e44  lock inc word ptr [rax+0Ch]
0x140008e49  mov     r9d, [rbx+0Ch]
0x140008e4d  mov     rcx, r13
0x140008e50  cmp     r9d, 0FFFFFFFFh
0x140008e54  jz      short loc_140008E6B
0x140008e56  mov     rax, [rbx+50h]
0x140008e5a  mov     r8, [rax+18h]
0x140008e5e  test    r8, r8
0x140008e61  jz      short loc_140008E6B
0x140008e63  lea     rcx, [r9+r9*4]
0x140008e67  lea     rcx, [r8+rcx*4]
0x140008e6b  lock inc dword ptr [rcx]
0x140008e6e  jmp     loc_140008BAC
0x140008e73  mov     rax, [rbx+50h]
0x140008e77  cmp     byte ptr [rax+1], 1
0x140008e7b  jz      loc_140009523
0x140008e81  mov     rcx, [rbx+50h]
0x140008e85  mov     eax, [rcx+4]
0x140008e88  test    eax, eax
0x140008e8a  jz      loc_1400091EE
0x140008e90  mov     rdx, [rbx+20h]
0x140008e94  mov     ebp, [rdx+8]
0x140008e97  cmp     ebp, [rdx+0Ch]
0x140008e9a  jnb     loc_140009145
0x140008ea0  inc     dword ptr [rbx+14h]
0x140008ea3  inc     dword ptr [rdx+8]
0x140008ea6  mov     rcx, [rbx+50h]
0x140008eaa  cmp     byte ptr [rcx+1], 1
0x140008eae  jnz     short loc_140008EF9
0x140008eb0  mov     r9d, [rbx+0Ch]
0x140008eb4  mov     rax, r13
0x140008eb7  cmp     r9d, 0FFFFFFFFh
0x140008ebb  jz      short loc_140008ECE
0x140008ebd  mov     r8, [rcx+18h]
0x140008ec1  test    r8, r8
0x140008ec4  jz      short loc_140008ECE
0x140008ec6  lea     rcx, [r9+r9*4]
0x140008eca  lea     rax, [r8+rcx*4]
0x140008ece  lock inc word ptr [rax+0Eh]
0x140008ed3  mov     r9d, [rbx+0Ch]
0x140008ed7  mov     rcx, r13
0x140008eda  cmp     r9d, 0FFFFFFFFh
0x140008ede  jz      short loc_140008EF5
0x140008ee0  mov     rax, [rbx+50h]
0x140008ee4  mov     r8, [rax+18h]
0x140008ee8  test    r8, r8
0x140008eeb  jz      short loc_140008EF5
0x140008eed  lea     rcx, [r9+r9*4]
0x140008ef1  lea     rcx, [r8+rcx*4]
0x140008ef5  lock inc dword ptr [rcx+4]
0x140008ef9  mov     eax, ebp
0x140008efb  lea     rcx, [rax+rax*2]
0x140008eff  mov     rax, [rdx+10h]
0x140008f03  lea     rdx, [rax+rcx*8]
  ... truncated ...
```
