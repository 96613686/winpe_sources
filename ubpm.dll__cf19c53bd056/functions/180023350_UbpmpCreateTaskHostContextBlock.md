# UbpmpCreateTaskHostContextBlock

- ea: `0x180023350`
- end: `0x180023dfc`
- name: `UbpmpCreateTaskHostContextBlock`
- size: `2732`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64, int, int, __int64, __int64, __int64, __int64, int, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180021060`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x180023350`
- `0x180032e38`
- `0x18003cc14`
- `0x18003d7d2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18002338e`
- `ntdll!RtlAllocateHeap` at `0x18002345d`
- `ntdll!RtlAllocateHeap` at `0x1800234ea`
- `ntdll!RtlAllocateHeap` at `0x18002357f`
- `ntdll!RtlAllocateHeap` at `0x18002338e`
- `ntdll!RtlAllocateHeap` at `0x18002345d`
- `ntdll!RtlAllocateHeap` at `0x1800234ea`
- `ntdll!RtlAllocateHeap` at `0x18002357f`
- `ntdll!RtlInitializeSRWLock` at `0x1800235f0`
- `ntdll!RtlInitializeSRWLock` at `0x1800235fa`
- `ntdll!RtlInitializeSRWLock` at `0x1800235f0`
- `ntdll!RtlInitializeSRWLock` at `0x1800235fa`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800238b4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800238b4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023913`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023df1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023913`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023df1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800238ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800238ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023807`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023807`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d6c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800237c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800237c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023846`

## pseudocode

```c
__int64 __fastcall UbpmpCreateTaskHostContextBlock(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        int a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        _QWORD *a15)
{
  _QWORD *Heap; // rax
  _QWORD *v17; // r14
  __int64 v18; // rbx
  _QWORD *v19; // r15
  __int64 v20; // rsi
  __int64 v21; // rbp
  __int64 v22; // r12
  __int64 v23; // rbx
  DWORD v24; // r15d
  __int64 v25; // r14
  DWORD v26; // esi
  __int64 v27; // rax
  bool v28; // zf
  SIZE_T v29; // rbx
  _WORD *v30; // rax
  _WORD *v31; // rdi
  SIZE_T v32; // rbx
  _WORD *v33; // rdx
  __int64 v34; // rcx
  _WORD *v35; // rcx
  __int64 v36; // rax
  SIZE_T v37; // rbx
  _WORD *v38; // rax
  _WORD *v39; // rdi
  SIZE_T v40; // rbx
  _WORD *v41; // rdx
  __int64 v42; // rcx
  _WORD *v43; // rcx
  __int64 v44; // rcx
  _WORD *v45; // rax
  _WORD *v46; // rbx
  unsigned __int64 v47; // rdi
  _WORD *v48; // rcx
  _WORD *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  __int64 v52; // rax
  int v53; // ecx
  HANDLE EventW; // rax
  _QWORD *v55; // rcx
  __int64 v56; // rdx
  __int64 v57; // r9
  DWORD v58; // eax
  void *v59; // rcx
  _QWORD *v60; // rcx
  void *v62; // rax
  unsigned int v63; // eax
  __int64 v64; // rcx
  __int64 v65; // r9
  char *v66; // r8
  _WORD *v67; // rdx
  char *v68; // rcx
  char *v69; // rdi
  unsigned __int8 v70; // r11
  char *v71; // rax
  char *v72; // r14
  __int64 v73; // rax
  unsigned int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // r9
  char *v77; // r8
  _WORD *v78; // rdx
  char *v79; // rcx
  char *v80; // rdi
  unsigned __int8 v81; // r11
  char *v82; // rax
  char *v83; // rsi
  __int64 v84; // rax
  __int64 v85; // rcx
  __int64 v86; // rax
  unsigned int v87; // eax
  unsigned int v88; // r8d
  unsigned __int8 i; // dl
  SIZE_T v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rax
  unsigned int v93; // eax
  unsigned int v94; // r8d
  unsigned __int8 j; // dl
  SIZE_T v96; // rcx
  DWORD LastError; // eax
  _QWORD *v98; // [rsp+30h] [rbp-48h]
  _QWORD *v99; // [rsp+80h] [rbp+8h]

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1B8u);
  v99 = Heap;
  v17 = Heap;
  if ( !Heap )
  {
    SetLastError(8u);
    LastError = GetLastError();
    v26 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
    return v26;
  }
  v18 = *(unsigned __int8 *)(a3 + 120);
  v19 = Heap + 45;
  v20 = *(_QWORD *)(a3 + 128);
  v98 = Heap + 45;
  v21 = 2147483646;
  Heap[45] = 0;
  v22 = -1;
  if ( (_BYTE)v18 )
  {
    v88 = 0;
    for ( i = 0; i < (unsigned __int8)v18; ++i )
    {
      v85 = *(_QWORD *)(v20 + 8LL * i);
      if ( v85 )
      {
        v86 = -1;
        do
          v28 = *(_WORD *)(v85 + 2 * v86++ + 2) == 0;
        while ( !v28 );
        v87 = 2 * v86 + 2;
        v88 += v87;
        if ( v88 < v87 )
          goto LABEL_109;
      }
    }
    v90 = 8 * (_DWORD)v18 + v88;
    if ( (unsigned int)v90 < 8 * (int)v18 )
    {
LABEL_109:
      v26 = 534;
    }
    else
    {
      v71 = (char *)UbpmAlloc(v90);
      v72 = v71;
      if ( v71 )
      {
        v70 = 0;
        v69 = &v71[8 * v18];
        do
        {
          if ( *(_QWORD *)(v20 + 8LL * v70) )
          {
            *(_QWORD *)&v72[8 * v70] = v69;
            v67 = *(_WORD **)(v20 + 8LL * v70);
            v73 = -1;
            do
              ++v73;
            while ( v67[v73] );
            v63 = v73 + 1;
            if ( v63 )
            {
              if ( v63 > 0x7FFFFFFFuLL )
              {
                *(_WORD *)v69 = 0;
              }
              else
              {
                v64 = 2147483646;
                v65 = v63;
                v66 = v69;
                do
                {
                  if ( !v64 )
                    break;
                  if ( !*v67 )
                    break;
                  *(_WORD *)v66 = *v67++;
                  v66 += 2;
                  --v64;
                  --v65;
                }
                while ( v65 );
                v68 = v66 - 2;
                if ( v65 )
                  v68 = v66;
                *(_WORD *)v68 = 0;
              }
            }
            v69 += 2 * v63;
          }
          ++v70;
        }
        while ( v70 < (unsigned __int8)v18 );
        *v19 = v72;
        goto LABEL_3;
      }
      v26 = GetLastError();
      if ( !v26 )
        goto LABEL_3;
      v17 = v99;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v26);
    goto LABEL_54;
  }
LABEL_3:
  v23 = *(unsigned __int8 *)(a3 + 152);
  v24 = 0;
  v25 = *(_QWORD *)(a3 + 160);
  v99[47] = 0;
  if ( (_BYTE)v23 )
  {
    v94 = 0;
    for ( j = 0; j < (unsigned __int8)v23; ++j )
    {
      v91 = *(_QWORD *)(v25 + 8LL * j);
      if ( v91 )
      {
        v92 = -1;
        do
          v28 = *(_WORD *)(v91 + 2 * v92++ + 2) == 0;
        while ( !v28 );
        v93 = 2 * v92 + 2;
        v94 += v93;
        if ( v94 < v93 )
          goto LABEL_121;
      }
    }
    v96 = v94 + 8 * (_DWORD)v23;
    if ( (unsigned int)v96 < 8 * (int)v23 )
    {
LABEL_121:
      v26 = 534;
      v24 = 534;
      goto LABEL_122;
    }
    v82 = (char *)UbpmAlloc(v96);
    v83 = v82;
    if ( v82 )
    {
      v81 = 0;
      v80 = &v82[8 * v23];
      do
      {
        if ( *(_QWORD *)(v25 + 8LL * v81) )
        {
          *(_QWORD *)&v83[8 * v81] = v80;
          v78 = *(_WORD **)(v25 + 8LL * v81);
          v84 = -1;
          do
            ++v84;
          while ( v78[v84] );
          v74 = v84 + 1;
          if ( v74 )
          {
            if ( v74 > 0x7FFFFFFFuLL )
            {
              *(_WORD *)v80 = 0;
            }
            else
            {
              v75 = 2147483646;
              v76 = v74;
              v77 = v80;
              do
              {
                if ( !v75 )
                  break;
                if ( !*v78 )
                  break;
                *(_WORD *)v77 = *v78++;
                v77 += 2;
                --v75;
                --v76;
              }
              while ( v76 );
              v79 = v77 - 2;
              if ( v76 )
                v79 = v77;
              *(_WORD *)v79 = 0;
            }
          }
          v80 += 2 * v74;
        }
        ++v81;
      }
      while ( v81 < (unsigned __int8)v23 );
      v17 = v99;
      v99[47] = v83;
      v26 = 0;
      goto LABEL_6;
    }
    v24 = GetLastError();
  }
  v26 = v24;
  if ( v24 )
  {
LABEL_122:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v24);
    v19 = v98;
    v17 = v99;
    goto LABEL_54;
  }
  v17 = v99;
LABEL_6:
  *((_DWORD *)v17 + 83) = *(_DWORD *)(a3 + 104);
  if ( *(_QWORD *)(a3 + 112) )
  {
    v62 = UbpmAlloc(*(unsigned int *)(a3 + 108));
    v17[43] = v62;
    if ( !v62 )
    {
      v58 = GetLastError();
      v26 = v58;
      v55 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_53;
      v56 = 68;
LABEL_145:
      v57 = v58;
      goto LABEL_51;
    }
    memcpy_0(v62, *(const void **)(a3 + 112), *(unsigned int *)(a3 + 108));
    *((_DWORD *)v17 + 84) = *(_DWORD *)(a3 + 108);
  }
  v27 = -1;
  do
    v28 = *(_WORD *)(*(_QWORD *)(a3 + 16) + 2 * v27++ + 2) == 0;
  while ( !v28 );
  v29 = (unsigned int)(2 * v27 + 2);
  v30 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v29);
  v31 = v30;
  if ( !v30 )
  {
    SetLastError(8u);
    v17[18] = 0;
    v58 = GetLastError();
    v26 = v58;
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    v56 = 69;
    goto LABEL_145;
  }
  v32 = v29 >> 1;
  v17[18] = v30;
  if ( v32 )
  {
    v33 = *(_WORD **)(a3 + 16);
    v34 = 2147483646;
    do
    {
      if ( !v34 )
        break;
      if ( !*v33 )
        break;
      *v31++ = *v33++;
      --v34;
      --v32;
    }
    while ( v32 );
    v35 = v31 - 1;
    if ( v32 )
      v35 = v31;
    *v35 = 0;
  }
  v36 = -1;
  do
    v28 = *(_WORD *)(*(_QWORD *)(a3 + 24) + 2 * v36++ + 2) == 0;
  while ( !v28 );
  v37 = (unsigned int)(2 * v36 + 2);
  v38 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v37);
  v39 = v38;
  if ( !v38 )
  {
    SetLastError(8u);
    v17[19] = 0;
    v58 = GetLastError();
    v26 = v58;
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    v56 = 70;
    goto LABEL_145;
  }
  v40 = v37 >> 1;
  v17[19] = v38;
  if ( v40 )
  {
    v41 = *(_WORD **)(a3 + 24);
    v42 = 2147483646;
    do
    {
      if ( !v42 )
        break;
      if ( !*v41 )
        break;
      *v39++ = *v41++;
      --v42;
      --v40;
    }
    while ( v40 );
    v43 = v39 - 1;
    if ( v40 )
      v43 = v39;
    *v43 = 0;
  }
  v44 = *(_QWORD *)(*(_QWORD *)a3 + 8LL);
  if ( !v44 )
    goto LABEL_40;
  do
    v28 = *(_WORD *)(v44 + 2 * v22++ + 2) == 0;
  while ( !v28 );
  v45 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)(2 * v22 + 2));
  v46 = v45;
  if ( !v45 )
  {
    SetLastError(8u);
    v17[20] = 0;
    v58 = GetLastError();
    v26 = v58;
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    v56 = 71;
    goto LABEL_145;
  }
  v47 = (unsigned __int64)(unsigned int)(2 * v22 + 2) >> 1;
  v17[20] = v45;
  if ( v47 )
  {
    v48 = *(_WORD **)(*(_QWORD *)a3 + 8LL);
    do
    {
      if ( !v21 )
        break;
      if ( !*v48 )
        break;
      *v46++ = *v48++;
      --v21;
      --v47;
    }
    while ( v47 );
    v49 = v46 - 1;
    if ( v47 )
      v49 = v46;
    *v49 = 0;
  }
LABEL_40:
  *((_DWORD *)v17 + 68) = _InterlockedIncrement((volatile signed __int32 *)&g_dwInstanceId);
  RtlInitializeSRWLock(v17 + 10);
  RtlInitializeSRWLock(v17 + 8);
  v17[3] = a4;
  v17[32] = a7;
  v17[22] = a8;
  v17[23] = a9;
  *(_DWORD *)v17 = 1665679957;
  v17[6] = 0;
  v17[12] = 1;
  v50 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 24LL) + 32LL);
  if ( v50 )
    v51 = *(_DWORD *)(v50 + 36);
  else
    v51 = 0;
  *((_DWORD *)v17 + 66) = v51;
  v52 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 24LL) + 32LL);
  if ( v52 )
    v53 = *(_DWORD *)(v52 + 32);
  else
    v53 = 0;
  *((_DWORD *)v17 + 8) = a5;
  *((_DWORD *)v17 + 48) = a6;
  *((_DWORD *)v17 + 67) = v53;
  *((_WORD *)v17 + 138) = *(_WORD *)(a3 + 44);
  v17[38] = *(_QWORD *)(a3 + 48);
  *((_OWORD *)v17 + 7) = *(_OWORD *)*(_QWORD *)(a3 + 8);
  *(_OWORD *)(v17 + 35) = *(_OWORD *)*(_QWORD *)(a3 + 32);
  *((_DWORD *)v17 + 74) = *(_DWORD *)(a3 + 40);
  v17[39] = *(_QWORD *)(a3 + 88);
  *((_BYTE *)v17 + 352) = *(_BYTE *)(a3 + 120);
  *((_BYTE *)v17 + 372) = *(_BYTE *)(a3 + 152);
  *((_DWORD *)v17 + 92) = *(_DWORD *)(a3 + 136);
  *((_DWORD *)v17 + 98) = a11;
  v17[50] = a12;
  v17[48] = a13;
  v17[53] = a14;
  *((_BYTE *)v17 + 432) = 0;
  if ( a2 )
  {
    v17[30] = a10;
    v17[31] = *a2;
    *a2 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_qLd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0,
      *((unsigned __int8 *)v17 + 104),
      v17,
      *((unsigned __int8 *)v17 + 104),
      *((_DWORD *)v17 + 8));
  v17[26] = v17 + 25;
  v17[25] = v17 + 25;
  v17[28] = v17 + 27;
  v17[27] = v17 + 27;
  EventW = CreateEventW(0, 1, 0, 0);
  v17[29] = EventW;
  if ( !EventW )
  {
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    v56 = 73;
    v57 = v24;
LABEL_51:
    WPP_SF_d(v55[2], v56, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v57);
LABEL_53:
    v19 = v17 + 45;
LABEL_54:
    v59 = (void *)v17[29];
    if ( v59 )
      CloseHandle(v59);
    UBPM_MIDL_user_free(*v19);
    UBPM_MIDL_user_free(v17[47]);
    UBPM_MIDL_user_free(v17[43]);
    UBPM_MIDL_user_free(v17[18]);
    UBPM_MIDL_user_free(v17[19]);
    UBPM_MIDL_user_free(v17[20]);
    UBPM_MIDL_user_free(v17);
    return v26;
  }
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_18004CF18 = GetCurrentThreadId();
  if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_MachineState, 0, 0) )
  {
    v26 = 1115;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, 1115);
    dword_18004CF18 = 0;
    RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
    goto LABEL_53;
  }
  v60 = off_18004C130;
  if ( *off_18004C130 != (_UNKNOWN *)&g_leTaskHostContextListHead )
    __fastfail(3u);
  v17[2] = off_18004C130;
  v17[1] = &g_leTaskHostContextListHead;
  *v60 = v17 + 1;
  off_18004C130 = (_UNKNOWN **)(v17 + 1);
  dword_18004CF18 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  *a15 = v17;
  return v26;
}

```

## disassembly

```asm
0x180023350  mov     [rsp+arg_10], rbx
0x180023355  mov     [rsp+arg_18], r9
0x18002335a  mov     [rsp+arg_8], rdx
0x18002335f  mov     [rsp+arg_0], rcx
0x180023364  push    rbp
0x180023365  push    rsi
0x180023366  push    rdi
0x180023367  push    r12
0x180023369  push    r13
0x18002336b  push    r14
0x18002336d  push    r15
0x18002336f  sub     rsp, 40h
0x180023373  mov     rcx, gs:60h
0x18002337c  mov     r13, r8
0x18002337f  mov     edx, 8; Flags
0x180023384  mov     r8d, 1B8h; Size
0x18002338a  mov     rcx, [rcx+30h]; HeapHandle
0x18002338e  call    cs:__imp_RtlAllocateHeap
0x180023394  mov     [rsp+78h+arg_0], rax
0x18002339c  mov     r14, rax
0x18002339f  test    rax, rax
0x1800233a2  jz      loc_180023C86
0x1800233a8  movzx   ebx, byte ptr [r13+78h]
0x1800233ad  lea     r15, [rax+168h]
0x1800233b4  mov     rsi, [r13+80h]
0x1800233bb  xor     edi, edi
0x1800233bd  mov     [rsp+78h+var_48], r15
0x1800233c2  mov     ebp, 7FFFFFFEh
0x1800233c7  mov     [r15], rdi
0x1800233ca  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800233d1  test    bl, bl
0x1800233d3  jnz     loc_180023CD7
0x1800233d9  movzx   ebx, byte ptr [r13+98h]
0x1800233e1  mov     r15d, edi
0x1800233e4  mov     rax, [rsp+78h+arg_0]
0x1800233ec  mov     r14, [r13+0A0h]
0x1800233f3  mov     [rax+178h], rdi
0x1800233fa  test    bl, bl
0x1800233fc  jnz     loc_180023D08
0x180023402  mov     esi, r15d
0x180023405  test    r15d, r15d
0x180023408  jnz     loc_180023BE3
0x18002340e  mov     r14, [rsp+78h+arg_0]
0x180023416  mov     eax, [r13+68h]
0x18002341a  mov     [r14+14Ch], eax
0x180023421  cmp     qword ptr [r13+70h], 0
0x180023426  jnz     loc_18002396B
0x18002342c  mov     rcx, [r13+10h]
0x180023430  mov     rax, r12
0x180023433  cmp     word ptr [rcx+rax*2+2], 0
0x180023439  lea     rax, [rax+1]
0x18002343d  jnz     short loc_180023433
0x18002343f  mov     rcx, gs:60h
0x180023448  lea     eax, ds:2[rax*2]
0x18002344f  mov     r8d, eax; Size
0x180023452  mov     edx, 8; Flags
0x180023457  mov     ebx, eax
0x180023459  mov     rcx, [rcx+30h]; HeapHandle
0x18002345d  call    cs:__imp_RtlAllocateHeap
0x180023463  mov     rdi, rax
0x180023466  test    rax, rax
0x180023469  jz      loc_180023C41
0x18002346f  shr     rbx, 1
0x180023472  mov     [r14+90h], rax
0x180023479  jz      short loc_1800234B3
0x18002347b  mov     rdx, [r13+10h]
0x18002347f  mov     rcx, rbp
0x180023482  test    rcx, rcx
0x180023485  jz      short loc_1800234A3
0x180023487  movzx   eax, word ptr [rdx]
0x18002348a  test    ax, ax
0x18002348d  jz      short loc_1800234A3
0x18002348f  mov     [rdi], ax
0x180023492  add     rdx, 2
0x180023496  add     rdi, 2
0x18002349a  dec     rcx
0x18002349d  sub     rbx, 1
0x1800234a1  jnz     short loc_180023482
0x1800234a3  test    rbx, rbx
0x1800234a6  lea     rcx, [rdi-2]
0x1800234aa  cmovnz  rcx, rdi
0x1800234ae  xor     eax, eax
0x1800234b0  mov     [rcx], ax
0x1800234b3  mov     rcx, [r13+18h]
0x1800234b7  mov     rax, r12
0x1800234ba  nop     word ptr [rax+rax+00h]
0x1800234c0  cmp     word ptr [rcx+rax*2+2], 0
0x1800234c6  lea     rax, [rax+1]
0x1800234ca  jnz     short loc_1800234C0
0x1800234cc  mov     rcx, gs:60h
0x1800234d5  lea     eax, ds:2[rax*2]
0x1800234dc  mov     r8d, eax; Size
0x1800234df  mov     edx, 8; Flags
0x1800234e4  mov     ebx, eax
0x1800234e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800234ea  call    cs:__imp_RtlAllocateHeap
0x1800234f0  mov     rdi, rax
0x1800234f3  test    rax, rax
0x1800234f6  jz      loc_180023D67
0x1800234fc  shr     rbx, 1
0x1800234ff  mov     [r14+98h], rax
0x180023506  jz      short loc_180023541
0x180023508  mov     rdx, [r13+18h]
0x18002350c  mov     rcx, rbp
0x18002350f  nop
0x180023510  test    rcx, rcx
0x180023513  jz      short loc_180023531
0x180023515  movzx   eax, word ptr [rdx]
0x180023518  test    ax, ax
0x18002351b  jz      short loc_180023531
0x18002351d  mov     [rdi], ax
0x180023520  add     rdx, 2
0x180023524  add     rdi, 2
0x180023528  dec     rcx
0x18002352b  sub     rbx, 1
0x18002352f  jnz     short loc_180023510
0x180023531  test    rbx, rbx
0x180023534  lea     rcx, [rdi-2]
0x180023538  cmovnz  rcx, rdi
0x18002353c  xor     eax, eax
0x18002353e  mov     [rcx], ax
0x180023541  mov     rax, [r13+0]
0x180023545  mov     rcx, [rax+8]
0x180023549  test    rcx, rcx
0x18002354c  jz      loc_1800235D6
0x180023552  cmp     word ptr [rcx+r12*2+2], 0
0x180023559  lea     r12, [r12+1]
0x18002355e  jnz     short loc_180023552
0x180023560  mov     rcx, gs:60h
0x180023569  lea     eax, ds:2[r12*2]
0x180023571  mov     r8d, eax; Size
0x180023574  mov     edx, 8; Flags
0x180023579  mov     edi, eax
0x18002357b  mov     rcx, [rcx+30h]; HeapHandle
0x18002357f  call    cs:__imp_RtlAllocateHeap
0x180023585  mov     rbx, rax
0x180023588  test    rax, rax
0x18002358b  jz      loc_180023802
0x180023591  shr     rdi, 1
0x180023594  mov     [r14+0A0h], rax
0x18002359b  jz      short loc_1800235D6
0x18002359d  mov     rax, [r13+0]
0x1800235a1  mov     rcx, [rax+8]
0x1800235a5  test    rbp, rbp
0x1800235a8  jz      short loc_1800235C6
0x1800235aa  movzx   eax, word ptr [rcx]
0x1800235ad  test    ax, ax
0x1800235b0  jz      short loc_1800235C6
0x1800235b2  mov     [rbx], ax
0x1800235b5  add     rcx, 2
0x1800235b9  add     rbx, 2
0x1800235bd  dec     rbp
0x1800235c0  sub     rdi, 1
0x1800235c4  jnz     short loc_1800235A5
0x1800235c6  test    rdi, rdi
0x1800235c9  lea     rcx, [rbx-2]
0x1800235cd  cmovnz  rcx, rbx
0x1800235d1  xor     eax, eax
0x1800235d3  mov     [rcx], ax
0x1800235d6  mov     eax, 1
0x1800235db  lock xadd cs:?g_dwInstanceId@@3KC, eax; ulong volatile g_dwInstanceId
0x1800235e3  inc     eax
0x1800235e5  lea     rcx, [r14+50h]
0x1800235e9  mov     [r14+110h], eax
0x1800235f0  call    cs:__imp_RtlInitializeSRWLock
0x1800235f6  lea     rcx, [r14+40h]
0x1800235fa  call    cs:__imp_RtlInitializeSRWLock
0x180023600  mov     rax, [rsp+78h+arg_18]
0x180023608  xor     edx, edx
0x18002360a  mov     [r14+18h], rax
0x18002360e  mov     rax, [rsp+78h+arg_30]
0x180023616  mov     [r14+100h], rax
0x18002361d  mov     rax, [rsp+78h+arg_38]
0x180023625  mov     [r14+0B0h], rax
0x18002362c  mov     rax, [rsp+78h+arg_40]
0x180023634  mov     [r14+0B8h], rax
0x18002363b  mov     dword ptr [r14], 63484255h
0x180023642  mov     [r14+30h], rdx
0x180023646  mov     qword ptr [r14+60h], 1
0x18002364e  mov     rax, [r13+0]
0x180023652  mov     rcx, [rax+18h]
0x180023656  mov     rax, [rcx+20h]
0x18002365a  test    rax, rax
0x18002365d  jnz     loc_18002389D
0x180023663  mov     eax, edx
0x180023665  mov     [r14+108h], eax
0x18002366c  mov     rax, [r13+0]
0x180023670  mov     rcx, [rax+18h]
0x180023674  mov     rax, [rcx+20h]
0x180023678  test    rax, rax
0x18002367b  jnz     loc_1800238A5
0x180023681  mov     ecx, edx
0x180023683  mov     eax, [rsp+78h+arg_20]
0x18002368a  mov     [r14+20h], eax
0x18002368e  mov     eax, [rsp+78h+arg_28]
0x180023695  mov     [r14+0C0h], eax
0x18002369c  mov     [r14+10Ch], ecx
0x1800236a3  movzx   eax, word ptr [r13+2Ch]
0x1800236a8  mov     rcx, [rsp+78h+arg_8]
0x1800236b0  mov     [r14+114h], ax
0x1800236b8  mov     rax, [r13+30h]
0x1800236bc  mov     [r14+130h], rax
0x1800236c3  mov     rax, [r13+8]
0x1800236c7  movups  xmm0, xmmword ptr [rax]
0x1800236ca  movups  xmmword ptr [r14+70h], xmm0
0x1800236cf  mov     rax, [r13+20h]
0x1800236d3  movups  xmm0, xmmword ptr [rax]
0x1800236d6  movups  xmmword ptr [r14+118h], xmm0
0x1800236de  mov     eax, [r13+28h]
0x1800236e2  mov     [r14+128h], eax
0x1800236e9  mov     rax, [r13+58h]
0x1800236ed  mov     [r14+138h], rax
0x1800236f4  movzx   eax, byte ptr [r13+78h]
0x1800236f9  mov     [r14+160h], al
0x180023700  movzx   eax, byte ptr [r13+98h]
0x180023708  mov     [r14+174h], al
0x18002370f  mov     eax, [r13+88h]
0x180023716  mov     [r14+170h], eax
0x18002371d  mov     eax, [rsp+78h+arg_50]
0x180023724  mov     [r14+188h], eax
0x18002372b  mov     rax, [rsp+78h+arg_58]
0x180023733  mov     [r14+190h], rax
0x18002373a  mov     rax, [rsp+78h+arg_60]
0x180023742  mov     [r14+180h], rax
0x180023749  mov     rax, [rsp+78h+arg_68]
0x180023751  mov     [r14+1A8h], rax
0x180023758  mov     [r14+1B0h], dl
0x18002375f  test    rcx, rcx
0x180023762  jz      short loc_180023780
0x180023764  mov     rax, [rsp+78h+arg_48]
0x18002376c  mov     [r14+0F0h], rax
0x180023773  mov     rax, [rcx]
0x180023776  mov     [r14+0F8h], rax
0x18002377d  mov     [rcx], rdx
0x180023780  mov     rcx, cs:WPP_GLOBAL_Control
0x180023787  lea     rbx, WPP_GLOBAL_Control
0x18002378e  cmp     rcx, rbx
0x180023791  jnz     loc_18002393E
0x180023797  lea     rax, [r14+0C8h]
0x18002379e  xor     r9d, r9d; lpName
0x1800237a1  mov     [rax+8], rax
0x1800237a5  xor     r8d, r8d; bInitialState
0x1800237a8  mov     [rax], rax
0x1800237ab  mov     edx, 1; bManualReset
0x1800237b0  lea     rax, [r14+0D8h]
0x1800237b7  xor     ecx, ecx; lpEventAttributes
0x1800237b9  mov     [rax+8], rax
0x1800237bd  mov     [rax], rax
0x1800237c0  call    cs:__imp_CreateEventW
0x1800237c6  mov     [r14+0E8h], rax
0x1800237cd  test    rax, rax
0x1800237d0  jnz     loc_1800238AD
0x1800237d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237dd  cmp     rcx, rbx
0x1800237e0  jz      short loc_180023833
0x1800237e2  test    byte ptr [rcx+1Ch], 1
0x1800237e6  jz      short loc_180023833
0x1800237e8  mov     edx, 49h ; 'I'
0x1800237ed  mov     r9d, r15d
0x1800237f0  mov     rcx, [rcx+10h]
0x1800237f4  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800237fb  call    WPP_SF_d
0x180023800  jmp     short loc_180023833
0x180023802  mov     ecx, 8; dwErrCode
0x180023807  call    cs:__imp_SetLastError
0x18002380d  mov     [r14+0A0h], rbx
0x180023814  call    cs:__imp_GetLastError
0x18002381a  mov     esi, eax
0x18002381c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023823  lea     rbx, WPP_GLOBAL_Control
0x18002382a  cmp     rcx, rbx
0x18002382d  jnz     loc_180023DA9
0x180023833  lea     r15, [r14+168h]
0x18002383a  mov     rcx, [r14+0E8h]; hObject
0x180023841  test    rcx, rcx
0x180023844  jz      short loc_18002384C
0x180023846  call    cs:__imp_CloseHandle
0x18002384c  mov     rcx, [r15]
0x18002384f  call    UBPM_MIDL_user_free
0x180023854  mov     rcx, [r14+178h]
0x18002385b  call    UBPM_MIDL_user_free
0x180023860  mov     rcx, [r14+158h]
0x180023867  call    UBPM_MIDL_user_free
0x18002386c  mov     rcx, [r14+90h]
0x180023873  call    UBPM_MIDL_user_free
0x180023878  mov     rcx, [r14+98h]
0x18002387f  call    UBPM_MIDL_user_free
0x180023884  mov     rcx, [r14+0A0h]
0x18002388b  call    UBPM_MIDL_user_free
0x180023890  mov     rcx, r14
0x180023893  call    UBPM_MIDL_user_free
0x180023898  jmp     loc_180023924
0x18002389d  mov     eax, [rax+24h]
0x1800238a0  jmp     loc_180023665
0x1800238a5  mov     ecx, [rax+20h]
0x1800238a8  jmp     loc_180023683
0x1800238ad  lea     rcx, g_TaskHostContextListLock
0x1800238b4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800238ba  call    cs:__imp_GetCurrentThreadId
0x1800238c0  xor     edi, edi
  ... truncated ...
```
