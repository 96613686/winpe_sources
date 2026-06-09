# TmpLogTransaction

- ea: `0x14001f3e8`
- end: `0x14002023f`
- name: `TmpLogTransaction`
- size: `3671`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c010`
- `0x14000c480`
- `0x140011ab4`
- `0x140015fc8`
- `0x140020dd4`

## callees

- `0x1400012b8`
- `0x140001374`
- `0x140001d84`
- `0x1400024e0`
- `0x140002940`
- `0x14000fa08`
- `0x14001f3e8`

## import_xrefs

- `CLFS!CLFS_LSN_NULL` at `0x14001f43b`
- `CLFS!ClfsReserveAndAppendLog` at `0x14001f76b`
- `CLFS!ClfsReserveAndAppendLog` at `0x14001fffb`
- `CLFS!ClfsReserveAndAppendLog` at `0x14001f76b`
- `CLFS!ClfsReserveAndAppendLog` at `0x14001fffb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fbdd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fbdd`
- `ntoskrnl!KeReleaseMutex` at `0x14001fd27`
- `ntoskrnl!KeReleaseMutex` at `0x14001fe96`
- `ntoskrnl!KeReleaseMutex` at `0x14001fd27`
- `ntoskrnl!KeReleaseMutex` at `0x14001fe96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400201ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400201ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219e2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001f5e1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001f5e1`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001f92a`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001fafa`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001fb99`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001f92a`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001fafa`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001fb99`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001f607`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14001f607`
- `ntoskrnl!ObGetObjectSecurity` at `0x14001f903`
- `ntoskrnl!ObGetObjectSecurity` at `0x14001fab2`
- `ntoskrnl!ObGetObjectSecurity` at `0x14001fb51`
- `ntoskrnl!ObGetObjectSecurity` at `0x14001f903`
- `ntoskrnl!ObGetObjectSecurity` at `0x14001fab2`
- `ntoskrnl!ObGetObjectSecurity` at `0x14001fb51`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400201a4`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400219a0`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400201a4`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400219a0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400201d7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400219d2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400201d7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400219d2`

## pseudocode

```c
__int64 __fastcall TmpLogTransaction(__int64 a1, int a2, int a3)
{
  __int64 v5; // r14
  int v6; // eax
  char *v8; // r8
  _DWORD *v9; // rsi
  unsigned int v10; // r11d
  unsigned int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // r13
  unsigned __int64 v14; // rax
  int v15; // edx
  unsigned __int64 v16; // rbx
  int v17; // r9d
  unsigned int v18; // r15d
  unsigned int v19; // eax
  int v20; // edx
  unsigned __int64 v21; // rax
  unsigned int v22; // ecx
  unsigned int v23; // edx
  char *PoolWithTag; // rax
  NTSTATUS appended; // ebx
  char *v26; // rbx
  int v27; // r15d
  __int64 v28; // r8
  unsigned int v29; // r13d
  int v30; // eax
  BOOL v31; // r14d
  ULONG v32; // ebx
  int v33; // r15d
  __int64 *v34; // rcx
  unsigned int v35; // r14d
  ULONG v36; // eax
  int v37; // r9d
  unsigned int v38; // edx
  __int64 v39; // rcx
  unsigned int v40; // edx
  int v41; // r9d
  unsigned int v42; // edx
  __int64 v43; // rcx
  int v44; // eax
  __int64 *v45; // r9
  __int64 *v46; // rcx
  __int64 *v47; // rcx
  __int64 v48; // rcx
  PSECURITY_DESCRIPTOR *v49; // rdx
  __int64 v50; // rax
  ULONG *v51; // rbx
  PSECURITY_DESCRIPTOR *v52; // rdx
  char *v53; // r8
  __int64 v54; // rax
  __int64 v55; // rax
  int v56; // r10d
  unsigned int v57; // r9d
  __int64 v58; // rcx
  ULONG v59; // r10d
  unsigned int v60; // r9d
  __int64 v61; // rcx
  ULONG v62; // r9d
  unsigned int v63; // r8d
  __int64 v64; // rcx
  __int64 v65; // rax
  int v66; // r8d
  unsigned int v67; // edx
  __int64 v68; // rcx
  __int64 v69; // rcx
  int v70; // eax
  unsigned int v71; // r15d
  __int64 v72; // r8
  __int64 v73; // r12
  unsigned int i; // edi
  void *v75; // rcx
  char rgcbReservation; // [rsp+30h] [rbp-178h]
  int v77; // [rsp+50h] [rbp-158h]
  char v78; // [rsp+54h] [rbp-154h]
  char *v79; // [rsp+60h] [rbp-148h]
  unsigned int v80; // [rsp+68h] [rbp-140h]
  unsigned int v81; // [rsp+68h] [rbp-140h]
  __int64 *v82; // [rsp+70h] [rbp-138h]
  unsigned int v83; // [rsp+84h] [rbp-124h]
  unsigned int v84; // [rsp+88h] [rbp-120h]
  __int64 v86; // [rsp+98h] [rbp-110h]
  ULONG *v87; // [rsp+A0h] [rbp-108h]
  char v88[8]; // [rsp+A8h] [rbp-100h] BYREF
  __int64 v89; // [rsp+B0h] [rbp-F8h]
  int v90; // [rsp+B8h] [rbp-F0h]
  int v91; // [rsp+BCh] [rbp-ECh]
  char *v92; // [rsp+C0h] [rbp-E8h]
  char *v93; // [rsp+C8h] [rbp-E0h]
  char *v94; // [rsp+D0h] [rbp-D8h]
  PSECURITY_DESCRIPTOR *v95; // [rsp+D8h] [rbp-D0h]
  ULONG *v96; // [rsp+E0h] [rbp-C8h]
  PSECURITY_DESCRIPTOR *v97; // [rsp+E8h] [rbp-C0h]
  __int64 v98; // [rsp+F8h] [rbp-B0h]
  __int64 v99; // [rsp+100h] [rbp-A8h]
  __int64 v100; // [rsp+108h] [rbp-A0h]
  CLFS_LSN plsn1; // [rsp+110h] [rbp-98h] BYREF
  _QWORD v102[9]; // [rsp+120h] [rbp-88h] BYREF

  v91 = a3;
  memset(v102, 0, sizeof(v102));
  plsn1 = CLFS_LSN_NULL;
  v5 = *(_QWORD *)(a1 + 512);
  v86 = v5;
  if ( !v5 || (*(_DWORD *)(v5 + 128) & 1) != 0 )
    return 0;
  v6 = *(_DWORD *)(v5 + 64);
  if ( v6 == 4 )
    return 3222863876LL;
  if ( !*(_QWORD *)(v5 + 152) || !*(_QWORD *)(v5 + 160) || v6 != 3 )
    return 3222863954LL;
  v8 = 0;
  v79 = 0;
  v9 = 0;
  v94 = 0;
  v78 = 0;
  v10 = 0;
  v77 = 0;
  v99 = 0;
  v11 = *(_DWORD *)(a1 + 220);
  if ( !v11 && a2 != 4 )
    return 0;
  v12 = 0;
  if ( a2 != 4 )
    v12 = v11;
  v13 = (unsigned int)v12;
  v14 = (unsigned int)v12 + 4 * v12;
  if ( v14 <= 0xFFFFFFFF && (int)v14 + 4 >= (unsigned int)v14 )
  {
    v15 = 0;
    v16 = 16LL * (unsigned int)(v14 + 4);
    if ( v16 > 0xFFFFFFFF )
    {
      LODWORD(v16) = -1;
      v15 = -1073741675;
    }
    if ( v15 >= 0 )
    {
      v17 = 112 * v13;
      v98 = 112 * v13;
      if ( (unsigned __int64)(112 * v13) <= 0xFFFFFFFF )
      {
        v18 = 8 * v13;
        if ( (unsigned __int64)(8 * v13) <= 0xFFFFFFFF )
        {
          v19 = 2 * v13;
          if ( (unsigned __int64)(2 * v13) > 0xFFFFFFFF
            || (v20 = 0, v19 + 1 < v19)
            || (v21 = 16LL * (v19 + 1), v21 > 0xFFFFFFFF) )
          {
            LODWORD(v21) = -1;
            v20 = -1073741675;
          }
          if ( v20 >= 0 )
          {
            if ( (unsigned int)v13 <= 3 )
            {
              v78 = 1;
              PoolWithTag = (char *)ExAllocateFromPagedLookasideList(&TmpLogWriteLookasideList);
LABEL_31:
              v94 = PoolWithTag;
              v9 = PoolWithTag;
              if ( !PoolWithTag )
              {
                appended = -1073741670;
LABEL_133:
                v8 = v79;
                goto LABEL_134;
              }
              v92 = &PoolWithTag[(unsigned int)v16];
              v93 = &PoolWithTag[(unsigned int)v16 + (unsigned __int64)(unsigned int)v98];
              v26 = &PoolWithTag[(unsigned int)v98 + (unsigned int)v16 + (unsigned __int64)v18];
              v79 = v26;
              v27 = 72;
              memset(v102, 0, sizeof(v102));
              HIDWORD(v102[0]) = a2;
              *(_OWORD *)&v102[1] = *(_OWORD *)(a1 + 176);
              v102[4] = (unsigned int)v13 | 0x4800000000LL;
              LODWORD(v102[0]) = 260;
              LODWORD(v102[6]) = *(_DWORD *)(a1 + 196);
              LODWORD(v102[7]) = *(unsigned __int16 *)(a1 + 304);
              HIDWORD(v102[6]) = 268435457;
              LODWORD(v102[8]) = 0;
              *(_QWORD *)v9 = v102;
              v9[2] = 72;
              v84 = 1;
              if ( a2 == 4 )
              {
                if ( (*(_DWORD *)(a1 + 196) & 0x1000000) != 0 )
                {
                  *(_QWORD *)v88 = -*(_QWORD *)(a1 + 520);
                  appended = ClfsReserveAndAppendLog(*(PVOID *)(v5 + 160), 0, 0, 0, 0, 1u, (PLONGLONG)v88, 0, 0);
                  if ( appended < 0 )
                    goto LABEL_133;
                  _InterlockedAnd((volatile signed __int32 *)(a1 + 196), 0xFEFFFFFF);
                  *(_QWORD *)(a1 + 520) = 0;
                }
                *(_QWORD *)((char *)&v102[4] + 4) = 0;
                HIDWORD(v102[5]) = 0;
                v102[7] = 0;
                v29 = 1;
                v90 = 1;
                v30 = *(_DWORD *)(a1 + 196);
                v31 = (v30 & 0x2000000) != 0;
                v32 = 0;
                if ( (v30 & 0x2000000) != 0
                  && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                {
                  WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 3), 10, v28, v86, a1);
                }
                v33 = 0;
              }
              else
              {
                v35 = 120 * v13 + 72;
                v29 = v13 + 2;
                appended = ObGetObjectSecurity((PVOID)a1, (PSECURITY_DESCRIPTOR *)v26, (PBOOLEAN)v26 + 12);
                v8 = v79;
                if ( appended < 0 )
                {
LABEL_134:
                  v10 = v77;
                  goto LABEL_135;
                }
                if ( *(_QWORD *)v79 )
                {
                  v36 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)v79);
                  v8 = v79;
                  *((_DWORD *)v79 + 2) = v36;
                }
                else
                {
                  *((_DWORD *)v79 + 2) = 0;
                }
                v10 = 1;
                v77 = 1;
                HIDWORD(v102[5]) = v35;
                LODWORD(v102[5]) = *((_DWORD *)v8 + 2);
                v37 = *((_DWORD *)v8 + 2);
                v38 = (v37 + 7) & 0xFFFFFFF8;
                if ( v38 + v35 >= v35 )
                {
                  v39 = 2LL * v29;
                  *(_QWORD *)&v9[2 * v39] = *(_QWORD *)v8;
                  v9[2 * v39 + 2] = v37;
                  v27 = v38 + 72;
                  v35 += v38;
                  ++v29;
                  appended = 0;
                }
                else
                {
                  appended = -1073741675;
                }
                if ( appended < 0 )
                  goto LABEL_135;
                v40 = 1;
                v80 = 1;
                if ( LODWORD(v102[7]) )
                {
                  HIDWORD(v102[7]) = v35;
                  v41 = *(unsigned __int16 *)(a1 + 304);
                  v42 = (v41 + 7) & 0xFFFFFFF8;
                  if ( v42 + v35 >= v35 )
                  {
                    v43 = 2LL * v29;
                    *(_QWORD *)&v9[2 * v43] = *(_QWORD *)(a1 + 312);
                    v9[2 * v43 + 2] = v41;
                    v27 += v42;
                    v35 += v42;
                    ++v29;
                    appended = 0;
                  }
                  else
                  {
                    appended = -1073741675;
                  }
                  if ( appended < 0 )
                    goto LABEL_135;
                  v40 = 1;
                }
                else
                {
                  v102[7] = 0;
                }
                v44 = 0;
                v83 = 0;
                v45 = (__int64 *)(a1 + 200);
                v46 = *(__int64 **)(a1 + 200);
                v32 = 2;
                while ( 1 )
                {
                  v82 = v46;
                  if ( v46 == v45 )
                    break;
                  v47 = v46 - 15;
                  if ( (*((_DWORD *)v47 + 43) & 4) != 0 || (*((_DWORD *)v47 + 43) & 2) == 0 )
                  {
                    v44 = v83;
                  }
                  else
                  {
                    if ( (*((_DWORD *)v47 + 43) & 0x100) == 0 )
                    {
                      appended = -1072103326;
                      goto LABEL_135;
                    }
                    v95 = (PSECURITY_DESCRIPTOR *)&v8[16 * v40];
                    appended = ObGetObjectSecurity(v47, v95, (PBOOLEAN)v95 + 12);
                    if ( appended < 0 )
                      goto LABEL_133;
                    v48 = 16LL * v80;
                    v87 = (ULONG *)&v79[v48 + 8];
                    v49 = v95;
                    if ( *v95 )
                    {
                      *v87 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)&v79[v48]);
                    }
                    else
                    {
                      *(_DWORD *)&v79[v48 + 8] = 0;
                      v87 = (ULONG *)(v49 + 1);
                    }
                    v81 = v80 + 1;
                    ++v77;
                    v97 = (PSECURITY_DESCRIPTOR *)&v79[16 * v81];
                    appended = ObGetObjectSecurity((PVOID)v82[4], v97, (PBOOLEAN)v97 + 12);
                    if ( appended < 0 )
                      goto LABEL_133;
                    v50 = 16LL * v81;
                    v51 = (ULONG *)&v79[v50 + 8];
                    v96 = v51;
                    v52 = v97;
                    if ( *v97 )
                    {
                      *v51 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)&v79[v50]);
                    }
                    else
                    {
                      *v51 = 0;
                      v51 = (ULONG *)(v52 + 1);
                      v96 = (ULONG *)(v52 + 1);
                    }
                    v80 = v81 + 1;
                    ++v77;
                    KeWaitForSingleObject(v82 - 7, Executive, 0, 0, 0);
                    v100 = v83;
                    v53 = &v92[112 * v83];
                    *(_OWORD *)v53 = *(_OWORD *)(v82 - 9);
                    *((_OWORD *)v53 + 1) = *(_OWORD *)(v82[4] + 136);
                    if ( (*((_DWORD *)v82 + 13) & 0x20) != 0 )
                    {
                      *((_OWORD *)v53 + 2) = *((_OWORD *)v82 + 9);
                      *((_OWORD *)v53 + 4) = *((_OWORD *)v82 + 10);
                      *((_OWORD *)v53 + 3) = *((_OWORD *)v82 + 11);
                    }
                    *((_DWORD *)v53 + 20) = *((_DWORD *)v82 + 13);
                    *((_DWORD *)v53 + 22) = *((_DWORD *)v82 + 22);
                    *((_DWORD *)v53 + 24) = *v87;
                    *((_DWORD *)v53 + 26) = *v51;
                    *(_DWORD *)&v93[8 * v83] = *(unsigned __int16 *)(v82[4] + 368);
                    v54 = 2LL * v84;
                    *(_QWORD *)&v9[2 * v54] = v53;
                    v9[2 * v54 + 2] = 112;
                    v27 += 112;
                    ++v84;
                    v55 = 112LL * v83;
                    if ( *((_DWORD *)v53 + 22) )
                    {
                      *(_DWORD *)&v92[v55 + 92] = v35;
                      v56 = *((_DWORD *)v82 + 22);
                      v57 = (v56 + 7) & 0xFFFFFFF8;
                      if ( v57 + v35 >= v35 )
                      {
                        v58 = 2LL * v29;
                        *(_QWORD *)&v9[2 * v58] = v82[10];
                        v9[2 * v58 + 2] = v56;
                        v27 += v57;
                        v35 += v57;
                        ++v29;
                        appended = 0;
                      }
                      else
                      {
                        appended = -1073741675;
                      }
                      if ( appended < 0 )
                      {
LABEL_89:
                        KeReleaseMutex((PRKMUTEX)v82 - 1, 0);
                        goto LABEL_133;
                      }
                    }
                    else
                    {
                      *(_DWORD *)&v92[v55 + 92] = 0;
                    }
                    *((_DWORD *)v53 + 25) = v35;
                    v59 = *v87;
                    v60 = (*v87 + 7) & 0xFFFFFFF8;
                    if ( v60 + v35 >= v35 )
                    {
                      v61 = 2LL * v29;
                      *(_QWORD *)&v9[2 * v61] = *v95;
                      v9[2 * v61 + 2] = v59;
                      v27 += v60;
                      v35 += v60;
                      ++v29;
                      appended = 0;
                    }
                    else
                    {
                      appended = -1073741675;
                    }
                    if ( appended < 0 )
                      goto LABEL_89;
                    *((_DWORD *)v53 + 27) = v35;
                    v62 = *v96;
                    v63 = (*v96 + 7) & 0xFFFFFFF8;
                    if ( v63 + v35 >= v35 )
                    {
                      v64 = 2LL * v29;
                      *(_QWORD *)&v9[2 * v64] = *v97;
                      v9[2 * v64 + 2] = v62;
                      v27 += v63;
                      v35 += v63;
                      ++v29;
                      appended = 0;
                    }
                    else
                    {
                      appended = -1073741675;
                    }
                    if ( appended < 0 )
                      goto LABEL_89;
                    if ( *(_DWORD *)&v93[8 * v100] )
                    {
                      *(_DWORD *)&v93[8 * v100 + 4] = v35;
                      v65 = v82[4];
                      v66 = *(unsigned __int16 *)(v65 + 368);
                      v67 = (v66 + 7) & 0xFFFFFFF8;
                      if ( v67 + v35 >= v35 )
                      {
                        v68 = 2LL * v29;
                        *(_QWORD *)&v9[2 * v68] = *(_QWORD *)(v65 + 376);
                        v9[2 * v68 + 2] = v66;
                        v27 += v67;
                        v35 += v67;
                        ++v29;
                        appended = 0;
                      }
                      else
                      {
                        appended = -1073741675;
                      }
                      if ( appended < 0 )
                        goto LABEL_89;
                    }
                    else
                    {
                      *(_DWORD *)&v93[8 * v100 + 4] = 0;
                    }
                    KeReleaseMutex((PRKMUTEX)v82 - 1, 0);
                    v44 = ++v83;
                    v8 = v79;
                    v32 = 2;
                    v45 = (__int64 *)(a1 + 200);
                    v10 = v77;
                  }
                  v46 = (__int64 *)*v82;
                  v40 = v80;
                }
                v69 = 2LL * v84;
                *(_QWORD *)&v9[2 * v69] = v93;
                v70 = 8 * v44;
                v9[2 * v69 + 2] = v70;
                v71 = v70 + v27;
                LODWORD(v102[8]) = v98 + 72;
                v90 = v29;
                if ( a2 == 3 )
                {
                  if ( (*(_DWORD *)(a1 + 196) & 0x1000000) != 0 )
                  {
                    v72 = *(_QWORD *)(a1 + 520);
                    if ( v72 == v71 )
                    {
                      v73 = v86;
                    }
                    else
                    {
                      *(_QWORD *)v88 = -v72;
                      v89 = v71;
                      v73 = v86;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                      {
                        WPP_SF_qq_guid_ii(*((_QWORD *)WPP_GLOBAL_Control + 3), 11, v72, v86, a1, a1 + 176);
                      }
                      appended = ClfsReserveAndAppendLog(*(PVOID *)(v86 + 160), 0, 0, 0, 0, 2u, (PLONGLONG)v88, 0, 0);
                      if ( appended < 0 )
                        goto LABEL_133;
                      *(_QWORD *)(a1 + 520) = v71;
                    }
                    v31 = 1;
                    v32 = 0;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                    {
                      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 3), 12, v72, v73, a1);
                    }
                  }
                  else
                  {
                    v31 = 0;
                    if ( (*(_DWORD *)(a1 + 196) & 0x2000000) != 0 )
                    {
                      v32 = 0;
                    }
                    else
                    {
                      v32 = 1;
                      *(_QWORD *)v88 = 72;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                      {
                        rgcbReservation = 72;
                        WPP_SF_qq_guid_i(*((_QWORD *)WPP_GLOBAL_Control + 3), v84 + 1, (_DWORD)v8, v86, a1, a1 + 176);
                      }
                    }
                  }
                  v33 = v32;
                }
                else
                {
                  v31 = 0;
                  *(_QWORD *)v88 = 72;
                  v99 = v71;
                  v89 = v71;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                  {
                    rgcbReservation = v71;
                    WPP_SF_qq_guid_ii(*((_QWORD *)WPP_GLOBAL_Control + 3), 14, v71, v86, a1, a1 + 176);
                  }
                  v33 = 1;
                }
              }
              v34 = (__int64 *)v88;
              if ( !v32 )
                v34 = 0;
              appended = TmpWriteLog(a1, (int)v9, v29, (int)&v102[3], v91, v31, rgcbReservation, v32, v34, &plsn1);
              if ( appended >= 0 )
              {
                if ( v99 )
                {
                  *(_QWORD *)(a1 + 520) = v99;
                  _InterlockedOr((volatile signed __int32 *)(a1 + 196), 0x1000000u);
                }
                if ( v33 )
                  _InterlockedOr((volatile signed __int32 *)(a1 + 196), 0x2000000u);
                if ( v31 )
                {
                  if ( a2 == 3 )
                  {
                    *(_QWORD *)(a1 + 520) = 0;
                    _InterlockedAnd((volatile signed __int32 *)(a1 + 196), 0xFEFFFFFF);
                  }
                  else if ( a2 == 4 )
                  {
                    _InterlockedAnd((volatile signed __int32 *)(a1 + 196), 0xFDFFFFFF);
                  }
                }
              }
              goto LABEL_133;
            }
            v78 = 0;
            v22 = v17 + v16;
            if ( v17 + (int)v16 >= (unsigned int)v16 )
            {
              v23 = v18 + v22;
              if ( v18 + v22 >= v22 && v23 + (unsigned int)v21 >= v23 )
              {
                PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v23 + (unsigned int)v21, 0x6F4C6D54u);
                goto LABEL_31;
              }
            }
          }
        }
      }
    }
  }
  appended = -1073741675;
LABEL_135:
  for ( i = 0; i < v10; ++i )
  {
    v75 = *(void **)&v8[16 * i];
    if ( v75 )
    {
      ObReleaseObjectSecurity(v75, v8[16 * i + 12]);
      v8 = v79;
      v10 = v77;
    }
  }
  if ( v9 )
  {
    if ( v78 )
      ExFreeToPagedLookasideList(&TmpLogWriteLookasideList, v9);
    else
      ExFreePoolWithTag(v9, 0);
  }
  if ( appended == -1073741789 )
    return (unsigned int)-1072103336;
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14001f3e8  mov     [rsp+arg_10], rbx
0x14001f3ed  mov     [rsp+arg_18], rsi
0x14001f3f2  push    rdi
0x14001f3f3  push    r12
0x14001f3f5  push    r13
0x14001f3f7  push    r14
0x14001f3f9  push    r15
0x14001f3fb  sub     rsp, 180h
0x14001f402  mov     rax, cs:__security_cookie
0x14001f409  xor     rax, rsp
0x14001f40c  mov     [rsp+1A8h+var_38], rax
0x14001f414  mov     [rsp+1A8h+var_EC], r8d
0x14001f41c  mov     ebx, edx
0x14001f41e  mov     [rsp+1A8h+var_114], edx
0x14001f425  mov     rdi, rcx
0x14001f428  xor     edx, edx; Val
0x14001f42a  lea     r8d, [rdx+48h]; Size
0x14001f42e  lea     rcx, [rsp+1A8h+var_88]; void *
0x14001f436  call    memset
0x14001f43b  mov     rax, cs:__imp_CLFS_LSN_NULL
0x14001f442  mov     r8, [rax]
0x14001f445  mov     qword ptr [rsp+1A8h+var_98], r8
0x14001f44d  mov     r14, [rdi+200h]
0x14001f454  mov     [rsp+1A8h+var_110], r14
0x14001f45c  test    r14, r14
0x14001f45f  jz      loc_14002020F
0x14001f465  mov     eax, [r14+80h]
0x14001f46c  test    al, 1
0x14001f46e  jnz     loc_14002020F
0x14001f474  mov     eax, [r14+40h]
0x14001f478  cmp     eax, 4
0x14001f47b  jnz     short loc_14001F487
0x14001f47d  mov     eax, 0C0190004h
0x14001f482  jmp     loc_140020211
0x14001f487  cmp     qword ptr [r14+98h], 0
0x14001f48f  jz      loc_140020208
0x14001f495  cmp     qword ptr [r14+0A0h], 0
0x14001f49d  jz      loc_140020208
0x14001f4a3  cmp     eax, 3
0x14001f4a6  jnz     loc_140020208
0x14001f4ac  xor     r8d, r8d
0x14001f4af  mov     [rsp+1A8h+var_148], r8
0x14001f4b4  xor     esi, esi
0x14001f4b6  mov     [rsp+1A8h+var_D8], rsi
0x14001f4be  mov     [rsp+1A8h+var_154], sil
0x14001f4c3  xor     r11d, r11d
0x14001f4c6  mov     [rsp+1A8h+var_158], r11d
0x14001f4cb  mov     [rsp+1A8h+var_A8], rsi
0x14001f4d3  mov     dword ptr [rsp+1A8h+var_138], esi
0x14001f4d7  mov     ecx, [rdi+0DCh]
0x14001f4dd  test    ecx, ecx
0x14001f4df  jnz     short loc_14001F4EA
0x14001f4e1  cmp     ebx, 4
0x14001f4e4  jnz     loc_14002020F
0x14001f4ea  xor     eax, eax
0x14001f4ec  cmp     ebx, 4
0x14001f4ef  cmovnz  eax, ecx
0x14001f4f2  mov     r13d, eax
0x14001f4f5  lea     rax, ds:0[rax*4]
0x14001f4fd  add     rax, r13
0x14001f500  mov     r10d, 0FFFFFFFFh
0x14001f506  cmp     rax, r10
0x14001f509  ja      loc_140020175
0x14001f50f  lea     ecx, [rax+4]
0x14001f512  cmp     ecx, eax
0x14001f514  jb      loc_140020175
0x14001f51a  xor     edx, edx
0x14001f51c  mov     [rsp+1A8h+var_11C], eax
0x14001f523  mov     [rsp+1A8h+var_11C], ecx
0x14001f52a  mov     ebx, ecx
0x14001f52c  shl     rbx, 4
0x14001f530  mov     r12d, 0C0000095h
0x14001f536  cmp     rbx, r10
0x14001f539  jbe     short loc_14001F541
0x14001f53b  mov     ebx, r10d
0x14001f53e  mov     edx, r12d
0x14001f541  mov     [rsp+1A8h+var_11C], ebx
0x14001f548  test    edx, edx
0x14001f54a  js      loc_14001F5EF
0x14001f550  imul    r9, r13, 70h ; 'p'
0x14001f554  mov     [rsp+1A8h+var_B0], r9
0x14001f55c  cmp     r9, r10
0x14001f55f  ja      loc_14001F5EF
0x14001f565  lea     r15, ds:0[r13*8]
0x14001f56d  cmp     r15, r10
0x14001f570  ja      short loc_14001F5EF
0x14001f572  lea     rax, ds:0[r13*2]
0x14001f57a  cmp     rax, r10
0x14001f57d  ja      short loc_14001F5A1
0x14001f57f  xor     edx, edx
0x14001f581  mov     [rsp+1A8h+var_128], eax
0x14001f588  lea     ecx, [rax+1]
0x14001f58b  cmp     ecx, eax
0x14001f58d  jb      short loc_14001F5A1
0x14001f58f  mov     [rsp+1A8h+var_128], ecx
0x14001f596  mov     eax, ecx
0x14001f598  shl     rax, 4
0x14001f59c  cmp     rax, r10
0x14001f59f  jbe     short loc_14001F5A7
0x14001f5a1  mov     eax, r10d
0x14001f5a4  mov     edx, r12d
0x14001f5a7  mov     [rsp+1A8h+var_128], eax
0x14001f5ae  test    edx, edx
0x14001f5b0  js      short loc_14001F5EF
0x14001f5b2  cmp     r13d, 3
0x14001f5b6  jbe     short loc_14001F5FB
0x14001f5b8  mov     [rsp+1A8h+var_154], 0
0x14001f5bd  lea     ecx, [r9+rbx]
0x14001f5c1  cmp     ecx, ebx
0x14001f5c3  jb      short loc_14001F5EF
0x14001f5c5  lea     edx, [r15+rcx]
0x14001f5c9  cmp     edx, ecx
0x14001f5cb  jb      short loc_14001F5EF
0x14001f5cd  lea     ecx, [rdx+rax]
0x14001f5d0  cmp     ecx, edx
0x14001f5d2  jb      short loc_14001F5EF
0x14001f5d4  mov     edx, ecx; NumberOfBytes
0x14001f5d6  mov     ecx, 1; PoolType
0x14001f5db  mov     r8d, 6F4C6D54h; Tag
0x14001f5e1  call    cs:__imp_ExAllocatePoolWithTag
0x14001f5e8  nop     dword ptr [rax+rax+00h]
0x14001f5ed  jmp     short loc_14001F613
0x14001f5ef  mov     ebx, r12d
0x14001f5f2  mov     [rsp+1A8h+var_150], ebx
0x14001f5f6  jmp     loc_14002018A
0x14001f5fb  mov     [rsp+1A8h+var_154], 1
0x14001f600  lea     rcx, TmpLogWriteLookasideList; Lookaside
0x14001f607  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14001f60e  nop     dword ptr [rax+rax+00h]
0x14001f613  mov     [rsp+1A8h+var_D8], rax
0x14001f61b  mov     rsi, rax
0x14001f61e  test    rax, rax
0x14001f621  jnz     short loc_14001F631
0x14001f623  mov     ebx, 0C000009Ah
0x14001f628  mov     [rsp+1A8h+var_150], ebx
0x14001f62c  jmp     loc_140020180
0x14001f631  mov     edx, ebx
0x14001f633  lea     rax, [rdx+rsi]
0x14001f637  mov     [rsp+1A8h+var_E8], rax
0x14001f63f  mov     rcx, [rsp+1A8h+var_B0]
0x14001f647  mov     ecx, ecx
0x14001f649  lea     rax, [rdx+rcx]
0x14001f64d  add     rax, rsi
0x14001f650  mov     [rsp+1A8h+var_E0], rax
0x14001f658  mov     ebx, r15d
0x14001f65b  add     rbx, rdx
0x14001f65e  add     rbx, rcx
0x14001f661  add     rbx, rsi
0x14001f664  mov     [rsp+1A8h+var_148], rbx
0x14001f669  mov     r15d, 48h ; 'H'
0x14001f66f  mov     r8d, r15d; Size
0x14001f672  xor     edx, edx; Val
0x14001f674  lea     rcx, [rsp+1A8h+var_88]; void *
0x14001f67c  call    memset
0x14001f681  mov     ecx, [rsp+1A8h+var_114]
0x14001f688  mov     [rsp+1A8h+var_84], ecx
0x14001f68f  movups  xmm0, xmmword ptr [rdi+0B0h]
0x14001f696  movdqu  [rsp+1A8h+var_80], xmm0
0x14001f69f  mov     dword ptr [rsp+1A8h+var_64], r15d
0x14001f6a7  mov     [rsp+1A8h+var_68], r13d
0x14001f6af  mov     [rsp+1A8h+var_88], 104h
0x14001f6ba  mov     eax, [rdi+0C4h]
0x14001f6c0  mov     [rsp+1A8h+var_58], eax
0x14001f6c7  movzx   eax, word ptr [rdi+130h]
0x14001f6ce  mov     dword ptr [rsp+1A8h+var_50], eax
0x14001f6d5  mov     [rsp+1A8h+var_54], 10000001h
0x14001f6e0  mov     [rsp+1A8h+var_48], 0
0x14001f6eb  lea     rax, [rsp+1A8h+var_88]
0x14001f6f3  mov     [rsi], rax
0x14001f6f6  mov     [rsi+8], r15d
0x14001f6fa  mov     [rsp+1A8h+var_13C], r15d
0x14001f6ff  lea     edx, [r15-47h]
0x14001f703  mov     [rsp+1A8h+var_120], edx
0x14001f70a  cmp     ecx, 4
0x14001f70d  jnz     loc_14001F8E4
0x14001f713  mov     eax, [rdi+0C4h]
0x14001f719  bt      eax, 18h
0x14001f71d  jnb     short loc_14001F79B
0x14001f71f  mov     rax, [rdi+208h]
0x14001f726  neg     rax
0x14001f729  mov     qword ptr [rsp+1A8h+var_100], rax
0x14001f731  mov     [rsp+1A8h+plsn], 0; plsn
0x14001f73a  mov     [rsp+1A8h+fFlags], 0; fFlags
0x14001f742  lea     rax, [rsp+1A8h+var_100]
0x14001f74a  mov     [rsp+1A8h+rgcbReservation], rax; char
0x14001f74f  mov     [rsp+1A8h+cReserveRecords], edx; cReserveRecords
0x14001f753  mov     [rsp+1A8h+plsnPrevious], 0; plsnPrevious
0x14001f75c  xor     r9d, r9d; plsnUndoNext
0x14001f75f  xor     r8d, r8d; cWriteEntries
0x14001f762  xor     edx, edx; rgWriteEntries
0x14001f764  mov     rcx, [r14+0A0h]; pvMarshalContext
0x14001f76b  call    cs:__imp_ClfsReserveAndAppendLog
0x14001f772  nop     dword ptr [rax+rax+00h]
0x14001f777  mov     ebx, eax
0x14001f779  mov     [rsp+1A8h+var_150], eax
0x14001f77d  test    eax, eax
0x14001f77f  js      loc_140020180
0x14001f785  lock and dword ptr [rdi+0C4h], 0FEFFFFFFh
0x14001f790  mov     qword ptr [rdi+208h], 0
0x14001f79b  mov     [rsp+1A8h+var_64], 0
0x14001f7a7  mov     [rsp+1A8h+var_5C], 0
0x14001f7b2  mov     [rsp+1A8h+var_50], 0
0x14001f7be  mov     r13d, 1
0x14001f7c4  mov     [rsp+1A8h+var_F0], r13d
0x14001f7cc  mov     eax, [rdi+0C4h]
0x14001f7d2  bt      eax, 19h
0x14001f7d6  lea     r14d, [r13-1]
0x14001f7da  setb    r14b
0x14001f7de  mov     [rsp+1A8h+var_118], r14d
0x14001f7e6  xor     ebx, ebx
0x14001f7e8  bt      eax, 19h
0x14001f7ec  jnb     short loc_14001F822
0x14001f7ee  lea     r15, WPP_GLOBAL_Control
0x14001f7f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f7fc  cmp     rcx, r15
0x14001f7ff  jz      short loc_14001F822
0x14001f801  mov     eax, [rcx+2Ch]
0x14001f804  test    r13b, al
0x14001f807  jz      short loc_14001F822
0x14001f809  lea     edx, [rbx+0Ah]
0x14001f80c  mov     [rsp+1A8h+plsnPrevious], rdi
0x14001f811  mov     r9, [rsp+1A8h+var_110]
0x14001f819  mov     rcx, [rcx+18h]
0x14001f81d  call    WPP_SF_qq
0x14001f822  mov     r15d, dword ptr [rsp+1A8h+var_138]
0x14001f827  lea     rcx, [rsp+1A8h+var_100]
0x14001f82f  xor     eax, eax
0x14001f831  test    ebx, ebx
0x14001f833  cmovz   rcx, rax
0x14001f837  lea     rax, [rsp+1A8h+var_98]
0x14001f83f  mov     [rsp+1A8h+plsn1], rax; plsn1
0x14001f844  mov     [rsp+1A8h+plsn], rcx; PLONGLONG
0x14001f849  mov     [rsp+1A8h+fFlags], ebx; cReserveRecords
0x14001f84d  mov     [rsp+1A8h+cReserveRecords], r14d; int
0x14001f852  mov     eax, [rsp+1A8h+var_EC]
0x14001f859  mov     dword ptr [rsp+1A8h+plsnPrevious], eax; int
0x14001f85d  lea     r9, [rsp+1A8h+var_70]; int
0x14001f865  mov     r8d, r13d; int
0x14001f868  mov     rdx, rsi; int
0x14001f86b  mov     rcx, rdi; int
0x14001f86e  call    TmpWriteLog
0x14001f873  mov     ebx, eax
0x14001f875  mov     [rsp+1A8h+var_150], eax
0x14001f879  test    eax, eax
0x14001f87b  js      loc_140020180
0x14001f881  mov     rax, [rsp+1A8h+var_A8]
0x14001f889  test    rax, rax
0x14001f88c  jz      short loc_14001F8A0
0x14001f88e  mov     [rdi+208h], rax
0x14001f895  lock or dword ptr [rdi+0C4h], 1000000h
0x14001f8a0  test    r15d, r15d
0x14001f8a3  jz      short loc_14001F8B0
0x14001f8a5  lock or dword ptr [rdi+0C4h], 2000000h
0x14001f8b0  test    r14d, r14d
0x14001f8b3  jz      loc_140020180
0x14001f8b9  mov     eax, [rsp+1A8h+var_114]
0x14001f8c0  cmp     eax, 3
0x14001f8c3  jnz     loc_140020163
0x14001f8c9  mov     qword ptr [rdi+208h], 0
0x14001f8d4  lock and dword ptr [rdi+0C4h], 0FEFFFFFFh
0x14001f8df  jmp     loc_140020180
0x14001f8e4  imul    r14d, r13d, 78h ; 'x'
0x14001f8e8  add     r14d, r15d
0x14001f8eb  mov     [rsp+1A8h+var_130], r14d
0x14001f8f0  add     r13d, 2
0x14001f8f4  mov     [rsp+1A8h+var_12C], r13d
0x14001f8f9  lea     r8, [rbx+0Ch]; MemoryAllocated
0x14001f8fd  mov     rdx, rbx; SecurityDescriptor
0x14001f900  mov     rcx, rdi; Object
0x14001f903  call    cs:__imp_ObGetObjectSecurity
0x14001f90a  nop     dword ptr [rax+rax+00h]
0x14001f90f  mov     ebx, eax
0x14001f911  mov     [rsp+1A8h+var_150], eax
0x14001f915  mov     r8, [rsp+1A8h+var_148]
0x14001f91a  test    eax, eax
0x14001f91c  js      loc_140020185
0x14001f922  mov     rcx, [r8]; SecurityDescriptor
0x14001f925  test    rcx, rcx
0x14001f928  jz      short loc_14001F941
0x14001f92a  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001f931  nop     dword ptr [rax+rax+00h]
0x14001f936  mov     r8, [rsp+1A8h+var_148]
0x14001f93b  mov     [r8+8], eax
0x14001f93f  jmp     short loc_14001F949
0x14001f941  mov     dword ptr [r8+8], 0
0x14001f949  mov     r11d, 1
0x14001f94f  mov     [rsp+1A8h+var_158], r11d
0x14001f954  mov     [rsp+1A8h+var_5C], r14d
0x14001f95c  mov     eax, [r8+8]
0x14001f960  mov     dword ptr [rsp+1A8h+var_64+4], eax
0x14001f967  mov     r9d, [r8+8]
0x14001f96b  lea     edx, [r9+7]
0x14001f96f  and     edx, 0FFFFFFF8h
0x14001f972  lea     r10d, [rdx+r14]
0x14001f976  cmp     r10d, r14d
0x14001f979  jnb     short loc_14001F980
0x14001f97b  mov     ebx, r12d
0x14001f97e  jmp     short loc_14001F9AD
0x14001f980  mov     ecx, r13d
0x14001f983  add     rcx, rcx
  ... truncated ...
```
