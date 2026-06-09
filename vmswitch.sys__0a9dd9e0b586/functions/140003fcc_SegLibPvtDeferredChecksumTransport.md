# SegLibPvtDeferredChecksumTransport

- ea: `0x140003fcc`
- end: `0x140004b6a`
- name: `SegLibPvtDeferredChecksumTransport`
- size: `2974`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140003e34`
- `0x140004ee0`
- `0x140006b00`

## callees

- `0x140003fcc`
- `0x140006620`
- `0x1401bbd20`
- `0x1401bbe80`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000434c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400044e2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400046fe`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000434c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400044e2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400046fe`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004634`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004667`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004634`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004667`

## pseudocode

```c
__int64 __fastcall SegLibPvtDeferredChecksumTransport(__int64 a1, __int64 a2, __int64 a3, char a4, char *a5, char *a6)
{
  struct _MDL *v7; // r15
  char v8; // r14
  unsigned int i; // edi
  unsigned int ByteCount; // eax
  unsigned int v11; // r12d
  __int64 v12; // r9
  char *MappedSystemVa; // rcx
  unsigned int v14; // eax
  char *v15; // r10
  unsigned int v16; // eax
  char *v17; // rbp
  unsigned int v18; // ecx
  unsigned int v19; // r13d
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 *v22; // r14
  __int64 v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // edi
  __int64 v26; // r9
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdi
  bool v34; // zf
  __int64 v35; // rdx
  __int64 v36; // rcx
  unsigned int v37; // eax
  __int64 v38; // rdx
  unsigned int v39; // edi
  __int64 v40; // rcx
  __int64 v41; // r9
  __int64 v42; // rax
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rcx
  int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // edi
  _DWORD *v53; // rax
  int v54; // ecx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r9
  volatile signed __int32 *v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rcx
  unsigned int v64; // eax
  __int64 v65; // rdx
  unsigned int v66; // edi
  __int64 v67; // rcx
  __int64 v68; // r9
  __int64 v69; // rax
  __int64 v70; // r8
  __int64 v71; // r9
  __int64 v72; // rcx
  __int64 v73; // r8
  int v74; // ecx
  unsigned int v75; // ecx
  _DWORD *v76; // rax
  int v77; // ecx
  __int64 v78; // r8
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 v81; // r8
  __int64 v82; // r9
  volatile signed __int32 *v83; // rcx
  __int64 v84; // r8
  __int64 v85; // rcx
  char v86; // di
  char *v87; // rdx
  unsigned __int16 v88; // ax
  __int16 v89; // ax
  char *v90; // rax
  _DWORD *v91; // rax
  int v92; // ecx
  __int64 v93; // r8
  __int64 v94; // rcx
  __int64 v95; // rax
  __int64 v96; // r8
  __int64 v97; // r9
  volatile signed __int32 *v98; // rcx
  __int64 v99; // r8
  __int64 v100; // rcx
  char v101; // di
  char *v102; // rdx
  unsigned __int16 v103; // ax
  __int16 v104; // ax
  unsigned __int16 v105; // ax
  __int16 v106; // ax
  unsigned __int16 v107; // ax
  __int16 v108; // ax
  __int16 *v109; // r8
  __int16 v110; // cx
  __int16 v111; // cx
  __int16 *v112; // rdx
  __int16 v113; // cx
  __int16 v114; // cx
  __int64 v115; // rax
  __int64 v116; // rcx
  __int64 v117; // rax
  char *v118; // [rsp+78h] [rbp+10h]
  unsigned int v119; // [rsp+80h] [rbp+18h]

  v7 = *(struct _MDL **)(a2 + 8);
  v8 = a4;
  for ( i = (unsigned __int16)a3 + *(_DWORD *)(a2 + 16); v7; i -= ByteCount )
  {
    ByteCount = v7->ByteCount;
    if ( ByteCount > i )
      break;
    v7 = v7->Next;
  }
  v11 = *(_DWORD *)(a2 + 24) - (unsigned __int16)a3;
  if ( !v11 )
    return 0;
  v12 = 1;
  if ( !v7 )
  {
    v51 = -1073741811;
    goto LABEL_64;
  }
  if ( (v7->MdlFlags & 5) != 0 )
  {
    MappedSystemVa = (char *)v7->MappedSystemVa;
  }
  else
  {
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000000u);
    v12 = 1;
  }
  if ( !MappedSystemVa || (v14 = v7->ByteCount, v14 <= i) )
  {
LABEL_63:
    v51 = -1073741670;
LABEL_64:
    LOBYTE(a3) = 1;
    BLFlushBatchOpContextEx(a1, 0, a3);
    return v51;
  }
  v15 = a6;
  v16 = v14 - i;
  v17 = &MappedSystemVa[i];
  v118 = a6;
  v18 = v11;
  v119 = v11;
  while ( 1 )
  {
    v19 = v18;
    if ( v16 <= v18 )
      v19 = v16;
    if ( v15 )
    {
      if ( !a1 )
        goto LABEL_60;
      v20 = *(_QWORD *)(a1 + 80);
      if ( *(_BYTE *)(v20 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
      {
        a3 = *(unsigned int *)(a1 + 12);
        v21 = 0;
        *(_BYTE *)(a1 + 4) = 1;
        if ( (_DWORD)a3 != -1 )
        {
          a2 = *(_QWORD *)(v20 + 24);
          if ( a2 )
            v21 = a2 + 20 * a3;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v21 + 16), 1u);
      }
      v22 = (__int64 *)(a1 + 80);
      v23 = *(_QWORD *)(a1 + 80);
      v24 = *(_DWORD *)(v23 + 4);
      if ( v24 )
      {
        a3 = *(_QWORD *)(a1 + 32);
        v25 = *(_DWORD *)(a3 + 8);
        if ( v25 < *(_DWORD *)(a3 + 12) )
        {
LABEL_23:
          ++*(_DWORD *)(a1 + 20);
          ++*(_DWORD *)(a3 + 8);
          if ( *(_BYTE *)(*v22 + 1) == 1 )
          {
            v26 = *(unsigned int *)(a1 + 12);
            v27 = 0;
            if ( (_DWORD)v26 != -1 )
            {
              v28 = *(_QWORD *)(*v22 + 24);
              if ( v28 )
                v27 = v28 + 20 * v26;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v27 + 14), 1u);
            v29 = *(unsigned int *)(a1 + 12);
            v30 = 0;
            if ( (_DWORD)v29 != -1 )
            {
              v31 = *(_QWORD *)(*v22 + 24);
              if ( v31 )
                v30 = v31 + 20 * v29;
            }
            v12 = 1;
            _InterlockedAdd((volatile signed __int32 *)(v30 + 4), 1u);
          }
          v32 = *(_QWORD *)(a3 + 16);
          a2 = 3LL * v25;
          *(_QWORD *)(v32 + 8 * a2) = v15;
          *(_QWORD *)(v32 + 8 * a2 + 8) = v17;
          *(_DWORD *)(v32 + 8 * a2 + 16) = (16 * v19) | 1;
          v33 = v19;
          goto LABEL_32;
        }
        v25 = 0;
        if ( *(_DWORD *)(a1 + 16) >= v24 )
        {
          LOBYTE(a2) = 1;
        }
        else
        {
          v53 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v23 + 64));
          a3 = (__int64)v53;
          if ( v53 )
          {
            *(_QWORD *)v53 = 0;
            v12 = 1;
            v53[2] = 0;
            v54 = *(_DWORD *)(*v22 + 8);
            *((_QWORD *)v53 + 2) = v53 + 6;
            v53[3] = v54;
            **(_QWORD **)(a1 + 32) = v53;
            v55 = *v22;
            ++*(_DWORD *)(a1 + 16);
            *(_QWORD *)(a1 + 32) = v53;
            if ( *(_BYTE *)(v55 + 1) == 1 )
            {
              v56 = *(unsigned int *)(a1 + 12);
              v57 = 0;
              if ( (_DWORD)v56 != -1 )
              {
                v58 = *(_QWORD *)(v55 + 24);
                if ( v58 )
                  v57 = v58 + 20 * v56;
              }
              _InterlockedAdd16((volatile signed __int16 *)(v57 + 12), 1u);
              v59 = *(unsigned int *)(a1 + 12);
              v60 = 0;
              if ( (_DWORD)v59 != -1 )
              {
                v61 = *(_QWORD *)(*v22 + 24);
                if ( v61 )
                  v60 = (volatile signed __int32 *)(v61 + 20 * v59);
              }
              v12 = 1;
              _InterlockedAdd(v60, 1u);
            }
            goto LABEL_75;
          }
          LOBYTE(a2) = 1;
        }
        BLFlushBatchOpContextEx(a1, a2, 0);
        a3 = a1 + 56;
        v12 = 1;
LABEL_75:
        v15 = v118;
        goto LABEL_23;
      }
      if ( *(_DWORD *)(a1 + 20) )
      {
        LOBYTE(a2) = 1;
        BLFlushBatchOpContextEx(a1, a2, 0);
        v15 = v118;
      }
      if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (*(_BYTE *)(a1 + 8) & 6) == 6 )
      {
        v33 = v19;
        (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*v22 + 32))(v23, a2, a3, v12);
        memmove(v118, v17, v19);
        (*(void (**)(void))(*v22 + 40))();
      }
      else
      {
LABEL_60:
        v33 = v19;
        memmove(v15, v17, v19);
      }
      v15 = v118;
LABEL_32:
      v8 = a4;
      v118 = &v15[v33];
      goto LABEL_33;
    }
    v62 = *(_QWORD *)(a1 + 80);
    if ( *(_BYTE *)(v62 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
    {
      a3 = *(unsigned int *)(a1 + 12);
      v115 = 0;
      *(_BYTE *)(a1 + 4) = 1;
      if ( (_DWORD)a3 != -1 )
      {
        a2 = *(_QWORD *)(v62 + 24);
        if ( a2 )
          v115 = a2 + 20 * a3;
      }
      _InterlockedAdd16((volatile signed __int16 *)(v115 + 16), 1u);
    }
    v63 = *(_QWORD *)(a1 + 80);
    v64 = *(_DWORD *)(v63 + 4);
    if ( v64 )
    {
      v65 = *(_QWORD *)(a1 + 32);
      v66 = *(_DWORD *)(v65 + 8);
      if ( v66 >= *(_DWORD *)(v65 + 12) )
      {
        v66 = 0;
        if ( *(_DWORD *)(a1 + 16) >= v64 )
        {
          LOBYTE(v65) = 1;
        }
        else
        {
          v91 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v63 + 64));
          v65 = (__int64)v91;
          if ( v91 )
          {
            *(_QWORD *)v91 = 0;
            v91[2] = 0;
            v92 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
            *((_QWORD *)v91 + 2) = v91 + 6;
            v91[3] = v92;
            **(_QWORD **)(a1 + 32) = v91;
            v93 = *(_QWORD *)(a1 + 80);
            ++*(_DWORD *)(a1 + 16);
            *(_QWORD *)(a1 + 32) = v91;
            if ( *(_BYTE *)(v93 + 1) == 1 )
            {
              v94 = *(unsigned int *)(a1 + 12);
              v95 = 0;
              if ( (_DWORD)v94 != -1 )
              {
                v96 = *(_QWORD *)(v93 + 24);
                if ( v96 )
                  v95 = v96 + 20 * v94;
              }
              _InterlockedAdd16((volatile signed __int16 *)(v95 + 12), 1u);
              v97 = *(unsigned int *)(a1 + 12);
              v98 = 0;
              if ( (_DWORD)v97 != -1 )
              {
                v99 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                if ( v99 )
                  v98 = (volatile signed __int32 *)(v99 + 20 * v97);
              }
              _InterlockedAdd(v98, 1u);
            }
            goto LABEL_80;
          }
          v65 = 1;
        }
        BLFlushBatchOpContextEx(a1, v65, 0);
        v65 = a1 + 56;
      }
LABEL_80:
      ++*(_DWORD *)(a1 + 20);
      ++*(_DWORD *)(v65 + 8);
      v67 = *(_QWORD *)(a1 + 80);
      if ( *(_BYTE *)(v67 + 1) == 1 )
      {
        v68 = *(unsigned int *)(a1 + 12);
        v69 = 0;
        if ( (_DWORD)v68 != -1 )
        {
          v70 = *(_QWORD *)(v67 + 24);
          if ( v70 )
            v69 = v70 + 20 * v68;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v69 + 14), 1u);
        v71 = *(unsigned int *)(a1 + 12);
        v72 = 0;
        if ( (_DWORD)v71 != -1 )
        {
          v73 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
          if ( v73 )
            v72 = v73 + 20 * v71;
        }
        _InterlockedAdd((volatile signed __int32 *)(v72 + 4), 1u);
      }
      v12 = *(_QWORD *)(v65 + 16);
      a3 = 3LL * v66;
      a2 = v12 + 24LL * v66;
      v74 = *(_DWORD *)(a2 + 16);
      if ( v8 )
        v75 = v74 & 0xFFFFFFF0 | 7;
      else
        v75 = v74 & 0xFFFFFFF0 | 6;
      *(_DWORD *)(a2 + 16) = v75;
      *(_QWORD *)(v12 + 24LL * v66 + 8) = v17;
      *(_QWORD *)(v12 + 24LL * v66) = a5;
      *(_DWORD *)(a2 + 16) = (16 * v19) | v75 & 0xF;
      goto LABEL_33;
    }
    if ( *(_DWORD *)(a1 + 20) )
    {
      LOBYTE(a2) = 1;
      BLFlushBatchOpContextEx(a1, a2, 0);
    }
    v100 = *(unsigned int *)(a1 + 8);
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (v100 &= 6u, v101 = 0, (_BYTE)v100 == 6) )
      v101 = 1;
    v102 = *(char **)(a1 + 48);
    if ( v102 && v102 != a5 )
    {
      if ( v101 )
      {
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
        v109 = *(__int16 **)(a1 + 48);
        v110 = *v109;
        if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
          v110 = __ROR2__(v110, 8);
        v111 = ~v110;
        if ( *(_BYTE *)(a1 + 40) && !v111 )
          v111 = -1;
        *v109 = v111;
        *(_QWORD *)(a1 + 48) = 0;
        *(_DWORD *)(a1 + 44) = 0;
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
      }
      else
      {
        LOBYTE(a3) = *(_BYTE *)(a1 + 40);
        v100 = *(unsigned __int16 *)v102;
        if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
          LOWORD(v100) = __ROR2__(v100, 8);
        LOWORD(v100) = ~(_WORD)v100;
        if ( (_BYTE)a3 && !(_WORD)v100 )
          v100 = 0xFFFF;
        *(_WORD *)v102 = v100;
        *(_DWORD *)(a1 + 44) = 0;
      }
    }
    *(_QWORD *)(a1 + 48) = a5;
    *(_BYTE *)(a1 + 40) = v8 != 0;
    if ( v101 )
    {
      (*(void (__fastcall **)(__int64, char *, __int64, __int64))(*(_QWORD *)(a1 + 80) + 32LL))(v100, v102, a3, v12);
      if ( a5 >= v17 && a5 < &v17[v19] )
        v105 = 0;
      else
        v105 = *(_WORD *)a5;
      v106 = tcpxsum(v105, v17, v19);
      *(_WORD *)a5 = v106;
      if ( (v19 & 1) != 0 )
      {
        *(_WORD *)a5 = __ROR2__(v106, 8);
        ++*(_DWORD *)(a1 + 44);
      }
      (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
    }
    else
    {
      if ( a5 < v17 || a5 >= &v17[v19] )
        v103 = *(_WORD *)a5;
      else
        v103 = 0;
      v104 = tcpxsum(v103, v17, v19);
      *(_WORD *)a5 = v104;
      if ( (v19 & 1) != 0 )
      {
        *(_WORD *)a5 = __ROR2__(v104, 8);
        ++*(_DWORD *)(a1 + 44);
      }
    }
LABEL_33:
    v34 = v119 == v19;
    v18 = v119 - v19;
    v119 -= v19;
    if ( v34 )
      break;
    v7 = v7->Next;
    if ( !v7 )
      goto LABEL_63;
    if ( (v7->MdlFlags & 5) != 0 )
    {
      v17 = (char *)v7->MappedSystemVa;
    }
    else
    {
      v90 = (char *)MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000000u);
      v18 = v119;
      v17 = v90;
    }
    if ( !v17 )
      goto LABEL_63;
    v16 = v7->ByteCount;
    v12 = 1;
    v15 = v118;
  }
  if ( !v118 )
    return 0;
  v35 = *(_QWORD *)(a1 + 80);
  if ( *(_BYTE *)(v35 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
  {
    v116 = *(unsigned int *)(a1 + 12);
    v117 = 0;
    *(_BYTE *)(a1 + 4) = 1;
    if ( (_DWORD)v116 != -1 )
    {
      v35 = *(_QWORD *)(v35 + 24);
      if ( v35 )
        v117 = v35 + 20 * v116;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v117 + 16), 1u);
  }
  v36 = *(_QWORD *)(a1 + 80);
  v37 = *(_DWORD *)(v36 + 4);
  if ( !v37 )
  {
    if ( *(_DWORD *)(a1 + 20) )
    {
      LOBYTE(v35) = 1;
      BLFlushBatchOpContextEx(a1, v35, 0);
    }
    v85 = *(unsigned int *)(a1 + 8);
    if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (v85 &= 6u, v86 = 0, (_BYTE)v85 == 6) )
      v86 = 1;
    v87 = *(char **)(a1 + 48);
    if ( v87 && v87 != a5 )
    {
      if ( v86 )
      {
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
        v112 = *(__int16 **)(a1 + 48);
        v113 = *v112;
        if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
          v113 = __ROR2__(v113, 8);
        v114 = ~v113;
        if ( *(_BYTE *)(a1 + 40) && !v114 )
          v114 = -1;
        *v112 = v114;
        *(_QWORD *)(a1 + 48) = 0;
        *(_DWORD *)(a1 + 44) = 0;
        (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
      }
      else
      {
        LOBYTE(a3) = *(_BYTE *)(a1 + 40);
        v85 = *(unsigned __int16 *)v87;
        if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
          LOWORD(v85) = __ROR2__(v85, 8);
        LOWORD(v85) = ~(_WORD)v85;
        if ( (_BYTE)a3 && !(_WORD)v85 )
          v85 = 0xFFFF;
        *(_WORD *)v87 = v85;
        *(_DWORD *)(a1 + 44) = 0;
      }
    }
    *(_QWORD *)(a1 + 48) = a5;
    *(_BYTE *)(a1 + 40) = v8 != 0;
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64, char *, __int64, __int64))(*(_QWORD *)(a1 + 80) + 32LL))(v85, v87, a3, v12);
      if ( a5 >= a6 && a5 < &a6[v11] )
        v107 = 0;
      else
        v107 = *(_WORD *)a5;
      v108 = tcpxsum(v107, a6, v11);
      *(_WORD *)a5 = v108;
      if ( (v11 & 1) != 0 )
      {
        *(_WORD *)a5 = __ROR2__(v108, 8);
        ++*(_DWORD *)(a1 + 44);
      }
      (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
    }
    else
    {
      if ( a5 < a6 || a5 >= &a6[v11] )
        v88 = *(_WORD *)a5;
      else
        v88 = 0;
      v89 = tcpxsum(v88, a6, v11);
      *(_WORD *)a5 = v89;
      if ( (v11 & 1) != 0 )
      {
        *(_WORD *)a5 = __ROR2__(v89, 8);
        ++*(_DWORD *)(a1 + 44);
      }
    }
    return 0;
  }
  v38 = *(_QWORD *)(a1 + 32);
  v39 = *(_DWORD *)(v38 + 8);
  if ( v39 < *(_DWORD *)(v38 + 12) )
    goto LABEL_43;
  v39 = 0;
  if ( *(_DWORD *)(a1 + 16) >= v37 )
  {
    LOBYTE(v38) = 1;
LABEL_120:
    BLFlushBatchOpContextEx(a1, v38, 0);
    v38 = a1 + 56;
    goto LABEL_43;
  }
  v76 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v36 + 64));
  v38 = (__int64)v76;
  if ( !v76 )
  {
    v38 = 1;
    goto LABEL_120;
  }
  *(_QWORD *)v76 = 0;
  v76[2] = 0;
  v77 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
  *((_QWORD *)v76 + 2) = v76 + 6;
  v76[3] = v77;
  **(_QWORD **)(a1 + 32) = v76;
  v78 = *(_QWORD *)(a1 + 80);
  ++*(_DWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 32) = v76;
  if ( *(_BYTE *)(v78 + 1) == 1 )
  {
    v79 = *(unsigned int *)(a1 + 12);
    v80 = 0;
    if ( (_DWORD)v79 != -1 )
    {
      v81 = *(_QWORD *)(v78 + 24);
      if ( v81 )
        v80 = v81 + 20 * v79;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v80 + 12), 1u);
    v82 = *(unsigned int *)(a1 + 12);
    v83 = 0;
    if ( (_DWORD)v82 != -1 )
    {
      v84 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
      if ( v84 )
        v83 = (volatile signed __int32 *)(v84 + 20 * v82);
    }
    _InterlockedAdd(v83, 1u);
  }
LABEL_43:
  ++*(_DWORD *)(a1 + 20);
  ++*(_DWORD *)(v38 + 8);
  v40 = *(_QWORD *)(a1 + 80);
  if ( *(_BYTE *)(v40 + 1) == 1 )
  {
    v41 = *(unsigned int *)(a1 + 12);
    v42 = 0;
    if ( (_DWORD)v41 != -1 )
    {
      v43 = *(_QWORD *)(v40 + 24);
      if ( v43 )
        v42 = v43 + 20 * v41;
    }
    _InterlockedAdd16((volatile signed __int16 *)(v42 + 14), 1u);
    v44 = *(unsigned int *)(a1 + 12);
    v45 = 0;
    if ( (_DWORD)v44 != -1 )
    {
      v46 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
      if ( v46 )
        v45 = v46 + 20 * v44;
    }
    _InterlockedAdd((volatile signed __int32 *)(v45 + 4), 1u);
  }
  v47 = *(_QWORD *)(v38 + 16);
  v48 = v47 + 24LL * v39;
  v49 = *(_DWORD *)(v48 + 16);
  if ( v8 )
    v50 = v49 & 0xFFFFFFF0 | 7;
  else
    v50 = v49 & 0xFFFFFFF0 | 6;
  *(_DWORD *)(v48 + 16) = v50;
  *(_QWORD *)(v47 + 24LL * v39 + 8) = a6;
  *(_DWORD *)(v48 + 16) = (16 * v11) | v50 & 0xF;
  *(_QWORD *)(v47 + 24LL * v39) = a5;
  return 0;
}

```

## disassembly

```asm
0x140003fcc  mov     [rsp+arg_0], rbx
0x140003fd1  mov     [rsp+arg_18], r9b
0x140003fd6  push    rbp
0x140003fd7  push    rsi
0x140003fd8  push    rdi
0x140003fd9  push    r12
0x140003fdb  push    r13
0x140003fdd  push    r14
0x140003fdf  push    r15
0x140003fe1  sub     rsp, 30h
0x140003fe5  mov     edi, [rdx+10h]
0x140003fe8  mov     rbx, rcx
0x140003feb  mov     r15, [rdx+8]
0x140003fef  mov     r14b, r9b
0x140003ff2  movzx   ecx, r8w
0x140003ff6  add     edi, ecx
0x140003ff8  xor     r11d, r11d
0x140003ffb  test    r15, r15
0x140003ffe  jz      short loc_14000400C
0x140004000  mov     eax, [r15+28h]
0x140004004  cmp     eax, edi
0x140004006  jbe     loc_1400043F6
0x14000400c  mov     r12d, [rdx+18h]
0x140004010  sub     r12d, ecx
0x140004013  jz      loc_1400042AF
0x140004019  mov     r9d, 1
0x14000401f  test    r15, r15
0x140004022  jz      loc_140004AAC
0x140004028  test    byte ptr [r15+0Ah], 5
0x14000402d  jz      loc_14000461B
0x140004033  mov     rcx, [r15+18h]
0x140004037  test    rcx, rcx
0x14000403a  jz      loc_140004325
0x140004040  mov     eax, [r15+28h]
0x140004044  cmp     eax, edi
0x140004046  jbe     loc_140004325
0x14000404c  mov     r10, [rsp+68h+arg_28]
0x140004054  sub     eax, edi
0x140004056  mov     rsi, [rsp+68h+arg_20]
0x14000405e  mov     ebp, edi
0x140004060  add     rbp, rcx
0x140004063  mov     [rsp+68h+arg_8], r10
0x140004068  mov     ecx, r12d
0x14000406b  mov     [rsp+68h+arg_10], ecx
0x140004072  cmp     eax, ecx
0x140004074  mov     r13d, ecx
0x140004077  cmovbe  r13d, eax
0x14000407b  test    r10, r10
0x14000407e  jz      loc_140004400
0x140004084  test    rbx, rbx
0x140004087  jz      loc_1400042FF
0x14000408d  mov     rcx, [rbx+50h]
0x140004091  cmp     [rcx+1], r9b
0x140004095  jnz     short loc_1400040C5
0x140004097  cmp     [rbx+4], r11b
0x14000409b  jnz     short loc_1400040C5
0x14000409d  mov     r8d, [rbx+0Ch]
0x1400040a1  mov     rax, r11
0x1400040a4  mov     [rbx+4], r9b
0x1400040a8  cmp     r8d, 0FFFFFFFFh
0x1400040ac  jz      short loc_1400040BF
0x1400040ae  mov     rdx, [rcx+18h]
0x1400040b2  test    rdx, rdx
0x1400040b5  jz      short loc_1400040BF
0x1400040b7  lea     rcx, [r8+r8*4]
0x1400040bb  lea     rax, [rdx+rcx*4]
0x1400040bf  lock add [rax+10h], r9w
0x1400040c5  lea     r14, [rbx+50h]
0x1400040c9  mov     rcx, [r14]
0x1400040cc  mov     eax, [rcx+4]
0x1400040cf  test    eax, eax
0x1400040d1  jz      loc_1400042CA
0x1400040d7  mov     r8, [rbx+20h]
0x1400040db  mov     edi, [r8+8]
0x1400040df  cmp     edi, [r8+0Ch]
0x1400040e3  jnb     loc_14000433C
0x1400040e9  add     [rbx+14h], r9d
0x1400040ed  add     [r8+8], r9d
0x1400040f1  mov     rcx, [r14]
0x1400040f4  cmp     [rcx+1], r9b
0x1400040f8  jnz     short loc_140004150
0x1400040fa  mov     r9d, [rbx+0Ch]
0x1400040fe  mov     rax, r11
0x140004101  cmp     r9d, 0FFFFFFFFh
0x140004105  jz      short loc_140004118
0x140004107  mov     rdx, [rcx+18h]
0x14000410b  test    rdx, rdx
0x14000410e  jz      short loc_140004118
0x140004110  lea     rcx, [r9+r9*4]
0x140004114  lea     rax, [rdx+rcx*4]
0x140004118  mov     r9d, 1
0x14000411e  lock add [rax+0Eh], r9w
0x140004124  mov     r9d, [rbx+0Ch]
0x140004128  mov     rcx, r11
0x14000412b  cmp     r9d, 0FFFFFFFFh
0x14000412f  jz      short loc_140004145
0x140004131  mov     rax, [r14]
0x140004134  mov     rdx, [rax+18h]
0x140004138  test    rdx, rdx
0x14000413b  jz      short loc_140004145
0x14000413d  lea     rcx, [r9+r9*4]
0x140004141  lea     rcx, [rdx+rcx*4]
0x140004145  mov     r9d, 1
0x14000414b  lock add [rcx+4], r9d
0x140004150  mov     rcx, [r8+10h]
0x140004154  mov     eax, edi
0x140004156  lea     rdx, [rax+rax*2]
0x14000415a  mov     eax, r13d
0x14000415d  mov     [rcx+rdx*8], r10
0x140004161  shl     eax, 4
0x140004164  or      eax, r9d
0x140004167  mov     [rcx+rdx*8+8], rbp
0x14000416c  mov     [rcx+rdx*8+10h], eax
0x140004170  mov     edi, r13d
0x140004173  mov     r14b, [rsp+68h+arg_18]
0x14000417b  add     r10, rdi
0x14000417e  xor     r11d, r11d
0x140004181  mov     [rsp+68h+arg_8], r10
0x140004186  lea     r10d, [r11+1]
0x14000418a  mov     ecx, [rsp+68h+arg_10]
0x140004191  sub     ecx, r13d
0x140004194  mov     [rsp+68h+arg_10], ecx
0x14000419b  jz      short loc_1400041D5
0x14000419d  mov     r15, [r15]
0x1400041a0  test    r15, r15
0x1400041a3  jz      loc_140004325
0x1400041a9  test    byte ptr [r15+0Ah], 5
0x1400041ae  jz      loc_14000464F
0x1400041b4  mov     rbp, [r15+18h]
0x1400041b8  test    rbp, rbp
0x1400041bb  jz      loc_140004325
0x1400041c1  mov     eax, [r15+28h]
0x1400041c5  mov     r9d, 1
0x1400041cb  mov     r10, [rsp+68h+arg_8]
0x1400041d0  jmp     loc_140004072
0x1400041d5  cmp     [rsp+68h+arg_8], r11
0x1400041da  jz      loc_1400042AF
0x1400041e0  mov     rdx, [rbx+50h]
0x1400041e4  or      ebp, 0FFFFFFFFh
0x1400041e7  cmp     [rdx+1], r10b
0x1400041eb  jz      loc_140004B28
0x1400041f1  mov     rcx, [rbx+50h]
0x1400041f5  mov     eax, [rcx+4]
0x1400041f8  test    eax, eax
0x1400041fa  jz      loc_140004582
0x140004200  mov     rdx, [rbx+20h]
0x140004204  mov     edi, [rdx+8]
0x140004207  cmp     edi, [rdx+0Ch]
0x14000420a  jnb     loc_1400044D2
0x140004210  add     [rbx+14h], r10d
0x140004214  add     [rdx+8], r10d
0x140004218  mov     rcx, [rbx+50h]
0x14000421c  cmp     [rcx+1], r10b
0x140004220  jnz     short loc_14000426B
0x140004222  mov     r9d, [rbx+0Ch]
0x140004226  mov     rax, r11
0x140004229  cmp     r9d, ebp
0x14000422c  jz      short loc_14000423F
0x14000422e  mov     r8, [rcx+18h]
0x140004232  test    r8, r8
0x140004235  jz      short loc_14000423F
0x140004237  lea     rcx, [r9+r9*4]
0x14000423b  lea     rax, [r8+rcx*4]
0x14000423f  lock add [rax+0Eh], r10w
0x140004245  mov     r9d, [rbx+0Ch]
0x140004249  mov     rcx, r11
0x14000424c  cmp     r9d, ebp
0x14000424f  jz      short loc_140004266
0x140004251  mov     rax, [rbx+50h]
0x140004255  mov     r8, [rax+18h]
0x140004259  test    r8, r8
0x14000425c  jz      short loc_140004266
0x14000425e  lea     rcx, [r9+r9*4]
0x140004262  lea     rcx, [r8+rcx*4]
0x140004266  lock add [rcx+4], r10d
0x14000426b  mov     r9, [rdx+10h]
0x14000426f  mov     eax, edi
0x140004271  lea     r8, [rax+rax*2]
0x140004275  lea     rcx, [r9+r8*8]
0x140004279  mov     eax, [rcx+10h]
0x14000427c  lea     rdx, [rcx+10h]
0x140004280  test    r14b, r14b
0x140004283  jnz     loc_14000431A
0x140004289  and     eax, 0FFFFFFF6h
0x14000428c  or      eax, 6
0x14000428f  mov     [rdx], eax
0x140004291  and     eax, 0Fh
0x140004294  mov     rdx, [rsp+68h+arg_28]
0x14000429c  shl     r12d, 4
0x1400042a0  or      eax, r12d
0x1400042a3  mov     [r9+r8*8+8], rdx
0x1400042a8  mov     [rcx+10h], eax
0x1400042ab  mov     [r9+r8*8], rsi
0x1400042af  mov     edi, r11d
0x1400042b2  mov     rbx, [rsp+68h+arg_0]
0x1400042b7  mov     eax, edi
0x1400042b9  add     rsp, 30h
0x1400042bd  pop     r15
0x1400042bf  pop     r14
0x1400042c1  pop     r13
0x1400042c3  pop     r12
0x1400042c5  pop     rdi
0x1400042c6  pop     rsi
0x1400042c7  pop     rbp
0x1400042c8  retn
0x1400042ca  cmp     [rbx+14h], r11d
0x1400042ce  jz      short loc_1400042E3
0x1400042d0  xor     r8d, r8d
0x1400042d3  mov     dl, r9b
0x1400042d6  mov     rcx, rbx
0x1400042d9  call    BLFlushBatchOpContextEx
0x1400042de  mov     r10, [rsp+68h+arg_8]
0x1400042e3  mov     eax, [rbx+8]
0x1400042e6  and     eax, 5
0x1400042e9  cmp     al, 5
0x1400042eb  jz      loc_140004AB6
0x1400042f1  mov     eax, [rbx+8]
0x1400042f4  and     eax, 6
0x1400042f7  cmp     al, 6
0x1400042f9  jz      loc_140004AB6
0x1400042ff  mov     r8d, r13d; Size
0x140004302  mov     rdx, rbp; Src
0x140004305  mov     rcx, r10; void *
0x140004308  mov     edi, r13d
0x14000430b  call    memmove
0x140004310  mov     r10, [rsp+68h+arg_8]
0x140004315  jmp     loc_140004173
0x14000431a  and     eax, 0FFFFFFF7h
0x14000431d  or      eax, 7
0x140004320  jmp     loc_14000428F
0x140004325  mov     edi, 0C000009Ah
0x14000432a  mov     r8b, 1
0x14000432d  xor     edx, edx
0x14000432f  mov     rcx, rbx
0x140004332  call    BLFlushBatchOpContextEx
0x140004337  jmp     loc_1400042B2
0x14000433c  mov     edi, r11d
0x14000433f  cmp     [rbx+10h], eax
0x140004342  jnb     loc_140004690
0x140004348  add     rcx, 40h ; '@'; Lookaside
0x14000434c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140004353  nop     dword ptr [rax+rax+00h]
0x140004358  xor     r11d, r11d
0x14000435b  mov     r8, rax
0x14000435e  test    rax, rax
0x140004361  jz      loc_1400046AE
0x140004367  mov     [rax], r11
0x14000436a  lea     r9d, [r11+1]
0x14000436e  mov     [rax+8], r11d
0x140004372  mov     rax, [r14]
0x140004375  mov     ecx, [rax+8]
0x140004378  lea     rax, [r8+18h]
0x14000437c  mov     [r8+10h], rax
0x140004380  mov     [r8+0Ch], ecx
0x140004384  mov     rax, [rbx+20h]
0x140004388  mov     [rax], r8
0x14000438b  mov     rdx, [r14]
0x14000438e  add     [rbx+10h], r9d
0x140004392  mov     [rbx+20h], r8
0x140004396  cmp     [rdx+1], r9b
0x14000439a  jnz     short loc_1400043EC
0x14000439c  mov     ecx, [rbx+0Ch]
0x14000439f  or      r10d, 0FFFFFFFFh
0x1400043a3  mov     eax, r11d
0x1400043a6  cmp     ecx, r10d
0x1400043a9  jz      short loc_1400043BC
0x1400043ab  mov     rdx, [rdx+18h]
0x1400043af  test    rdx, rdx
0x1400043b2  jz      short loc_1400043BC
0x1400043b4  lea     rcx, [rcx+rcx*4]
0x1400043b8  lea     rax, [rdx+rcx*4]
0x1400043bc  lock add [rax+0Ch], r9w
0x1400043c2  mov     r9d, [rbx+0Ch]
0x1400043c6  mov     rcx, r11
0x1400043c9  cmp     r9d, r10d
0x1400043cc  jz      short loc_1400043E2
0x1400043ce  mov     rax, [r14]
0x1400043d1  mov     rdx, [rax+18h]
0x1400043d5  test    rdx, rdx
0x1400043d8  jz      short loc_1400043E2
0x1400043da  lea     rcx, [r9+r9*4]
0x1400043de  lea     rcx, [rdx+rcx*4]
0x1400043e2  mov     r9d, 1
0x1400043e8  lock add [rcx], r9d
0x1400043ec  mov     r10, [rsp+68h+arg_8]
0x1400043f1  jmp     loc_1400040E9
0x1400043f6  mov     r15, [r15]
0x1400043f9  sub     edi, eax
0x1400043fb  jmp     loc_140003FFB
0x140004400  mov     rcx, [rbx+50h]
0x140004404  mov     r10d, 1
0x14000440a  cmp     [rcx+1], r10b
0x14000440e  jz      loc_140004AE6
0x140004414  mov     rcx, [rbx+50h]
0x140004418  mov     eax, [rcx+4]
0x14000441b  test    eax, eax
0x14000441d  jz      loc_1400047A0
0x140004423  mov     rdx, [rbx+20h]
0x140004427  mov     edi, [rdx+8]
0x14000442a  cmp     edi, [rdx+0Ch]
  ... truncated ...
```
