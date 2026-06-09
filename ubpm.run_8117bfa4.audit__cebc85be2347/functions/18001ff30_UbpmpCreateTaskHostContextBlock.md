# UbpmpCreateTaskHostContextBlock

- ea: `0x18001ff30`
- end: `0x180020a78`
- name: `UbpmpCreateTaskHostContextBlock`
- size: `2888`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001da20`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18001ff30`
- `0x1800351ec`
- `0x18003f610`
- `0x180040222`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001ff6e`
- `ntdll!RtlAllocateHeap` at `0x18002004a`
- `ntdll!RtlAllocateHeap` at `0x1800200da`
- `ntdll!RtlAllocateHeap` at `0x18002017d`
- `ntdll!RtlAllocateHeap` at `0x18001ff6e`
- `ntdll!RtlAllocateHeap` at `0x18002004a`
- `ntdll!RtlAllocateHeap` at `0x1800200da`
- `ntdll!RtlAllocateHeap` at `0x18002017d`
- `ntdll!RtlInitializeSRWLock` at `0x1800201fb`
- `ntdll!RtlInitializeSRWLock` at `0x18002020b`
- `ntdll!RtlInitializeSRWLock` at `0x1800201fb`
- `ntdll!RtlInitializeSRWLock` at `0x18002020b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800204e3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800204e3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002054e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180020a67`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002054e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180020a67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800204ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800204ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002098e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002098e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020424`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800208d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800209d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020424`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800208d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800209d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800203d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800203d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002046f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002046f`

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
  _WORD *v17; // rdx
  char *v18; // r8
  __int64 v19; // r9
  _QWORD *v20; // r14
  __int64 v21; // rbx
  _QWORD *v22; // r15
  __int64 v23; // rsi
  __int64 v24; // rbp
  __int64 v25; // r12
  __int64 v26; // rbx
  DWORD v27; // r15d
  __int64 v28; // r14
  DWORD v29; // esi
  __int64 v30; // rax
  bool v31; // zf
  SIZE_T v32; // rbx
  _WORD *v33; // rax
  _WORD *v34; // rdi
  SIZE_T v35; // rbx
  _WORD *v36; // rdx
  __int64 v37; // rcx
  _WORD *v38; // rcx
  __int64 v39; // rax
  SIZE_T v40; // rbx
  _WORD *v41; // rax
  _WORD *v42; // rdi
  SIZE_T v43; // rbx
  _WORD *v44; // rdx
  __int64 v45; // rcx
  _WORD *v46; // rcx
  __int64 v47; // rcx
  _WORD *v48; // rax
  _WORD *v49; // rbx
  unsigned __int64 v50; // rdi
  _WORD *v51; // rcx
  _WORD *v52; // rcx
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // rax
  int v56; // ecx
  HANDLE EventW; // rax
  _QWORD *v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // r9
  DWORD v61; // eax
  void *v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // r9
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // r9
  _QWORD *v81; // rcx
  void *v83; // rax
  unsigned int v84; // eax
  __int64 v85; // rcx
  char *v86; // rcx
  char *v87; // rdi
  unsigned __int8 v88; // r11
  char *v89; // rax
  char *v90; // r14
  __int64 v91; // rax
  unsigned int v92; // eax
  __int64 v93; // rcx
  __int64 v94; // r9
  char *v95; // r8
  _WORD *v96; // rdx
  char *v97; // rcx
  char *v98; // rdi
  unsigned __int8 v99; // r11
  char *v100; // rax
  char *v101; // rsi
  __int64 v102; // rax
  __int64 v103; // rcx
  __int64 v104; // rax
  unsigned int v105; // eax
  SIZE_T v106; // rcx
  __int64 v107; // rcx
  __int64 v108; // rax
  unsigned int v109; // eax
  SIZE_T v110; // rcx
  DWORD LastError; // eax
  _QWORD *v112; // [rsp+30h] [rbp-48h]
  _QWORD *v113; // [rsp+80h] [rbp+8h]

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1B8u);
  v113 = Heap;
  v20 = Heap;
  if ( !Heap )
  {
    SetLastError(8u);
    LastError = GetLastError();
    v29 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
    return v29;
  }
  v21 = *(unsigned __int8 *)(a3 + 120);
  v22 = Heap + 45;
  v23 = *(_QWORD *)(a3 + 128);
  v112 = Heap + 45;
  v24 = 2147483646;
  Heap[45] = 0;
  v25 = -1;
  if ( (_BYTE)v21 )
  {
    v18 = 0;
    LOBYTE(v17) = 0;
    while ( (unsigned __int8)v17 < (unsigned __int8)v21 )
    {
      v103 = *(_QWORD *)(v23 + 8LL * (unsigned __int8)v17);
      if ( v103 )
      {
        v104 = -1;
        do
          v31 = *(_WORD *)(v103 + 2 * v104++ + 2) == 0;
        while ( !v31 );
        v105 = 2 * v104 + 2;
        v18 = (char *)(v105 + (unsigned int)v18);
        if ( (unsigned int)v18 < v105 )
          goto LABEL_109;
      }
      LOBYTE(v17) = (_BYTE)v17 + 1;
    }
    v106 = (unsigned int)(8 * v21 + (_DWORD)v18);
    if ( (unsigned int)v106 < 8 * (int)v21 )
    {
LABEL_109:
      v29 = 534;
    }
    else
    {
      v89 = (char *)UbpmAlloc(v106);
      v90 = v89;
      if ( v89 )
      {
        v88 = 0;
        v87 = &v89[8 * v21];
        do
        {
          if ( *(_QWORD *)(v23 + 8LL * v88) )
          {
            *(_QWORD *)&v90[8 * v88] = v87;
            v17 = *(_WORD **)(v23 + 8LL * v88);
            v91 = -1;
            do
              ++v91;
            while ( v17[v91] );
            v84 = v91 + 1;
            if ( v84 )
            {
              if ( v84 > 0x7FFFFFFFuLL )
              {
                *(_WORD *)v87 = 0;
              }
              else
              {
                v85 = 2147483646;
                v19 = v84;
                v18 = v87;
                do
                {
                  if ( !v85 )
                    break;
                  if ( !*v17 )
                    break;
                  *(_WORD *)v18 = *v17++;
                  v18 += 2;
                  --v85;
                  --v19;
                }
                while ( v19 );
                v86 = v18 - 2;
                if ( v19 )
                  v86 = v18;
                *(_WORD *)v86 = 0;
              }
            }
            v87 += 2 * v84;
          }
          ++v88;
        }
        while ( v88 < (unsigned __int8)v21 );
        *v22 = v90;
        goto LABEL_3;
      }
      v29 = GetLastError();
      if ( !v29 )
        goto LABEL_3;
      v20 = v113;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v29);
    goto LABEL_54;
  }
LABEL_3:
  v26 = *(unsigned __int8 *)(a3 + 152);
  v27 = 0;
  v28 = *(_QWORD *)(a3 + 160);
  v113[47] = 0;
  if ( (_BYTE)v26 )
  {
    v18 = 0;
    LOBYTE(v17) = 0;
    while ( (unsigned __int8)v17 < (unsigned __int8)v26 )
    {
      v107 = *(_QWORD *)(v28 + 8LL * (unsigned __int8)v17);
      if ( v107 )
      {
        v108 = -1;
        do
          v31 = *(_WORD *)(v107 + 2 * v108++ + 2) == 0;
        while ( !v31 );
        v109 = 2 * v108 + 2;
        v18 = (char *)(v109 + (unsigned int)v18);
        if ( (unsigned int)v18 < v109 )
          goto LABEL_121;
      }
      LOBYTE(v17) = (_BYTE)v17 + 1;
    }
    v110 = (unsigned int)((_DWORD)v18 + 8 * v26);
    if ( (unsigned int)v110 < 8 * (int)v26 )
    {
LABEL_121:
      v29 = 534;
      v27 = 534;
      goto LABEL_122;
    }
    v100 = (char *)UbpmAlloc(v110);
    v101 = v100;
    if ( v100 )
    {
      v99 = 0;
      v98 = &v100[8 * v26];
      do
      {
        if ( *(_QWORD *)(v28 + 8LL * v99) )
        {
          *(_QWORD *)&v101[8 * v99] = v98;
          v96 = *(_WORD **)(v28 + 8LL * v99);
          v102 = -1;
          do
            ++v102;
          while ( v96[v102] );
          v92 = v102 + 1;
          if ( v92 )
          {
            if ( v92 > 0x7FFFFFFFuLL )
            {
              *(_WORD *)v98 = 0;
            }
            else
            {
              v93 = 2147483646;
              v94 = v92;
              v95 = v98;
              do
              {
                if ( !v93 )
                  break;
                if ( !*v96 )
                  break;
                *(_WORD *)v95 = *v96++;
                v95 += 2;
                --v93;
                --v94;
              }
              while ( v94 );
              v97 = v95 - 2;
              if ( v94 )
                v97 = v95;
              *(_WORD *)v97 = 0;
            }
          }
          v98 += 2 * v92;
        }
        ++v99;
      }
      while ( v99 < (unsigned __int8)v26 );
      v20 = v113;
      v113[47] = v101;
      v29 = 0;
      goto LABEL_6;
    }
    v27 = GetLastError();
  }
  v29 = v27;
  if ( v27 )
  {
LABEL_122:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v27);
    v22 = v112;
    v20 = v113;
    goto LABEL_54;
  }
  v20 = v113;
LABEL_6:
  *((_DWORD *)v20 + 83) = *(_DWORD *)(a3 + 104);
  if ( *(_QWORD *)(a3 + 112) )
  {
    v83 = UbpmAlloc(*(unsigned int *)(a3 + 108));
    v20[43] = v83;
    if ( !v83 )
    {
      v61 = GetLastError();
      v29 = v61;
      v58 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_53;
      v59 = 68;
LABEL_145:
      v60 = v61;
      goto LABEL_51;
    }
    memcpy_0(v83, *(const void **)(a3 + 112), *(unsigned int *)(a3 + 108));
    *((_DWORD *)v20 + 84) = *(_DWORD *)(a3 + 108);
  }
  v30 = -1;
  do
    v31 = *(_WORD *)(*(_QWORD *)(a3 + 16) + 2 * v30++ + 2) == 0;
  while ( !v31 );
  v32 = (unsigned int)(2 * v30 + 2);
  v33 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v32);
  v34 = v33;
  if ( !v33 )
  {
    SetLastError(8u);
    v20[18] = 0;
    v61 = GetLastError();
    v29 = v61;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    v59 = 69;
    goto LABEL_145;
  }
  v35 = v32 >> 1;
  v20[18] = v33;
  if ( v35 )
  {
    v36 = *(_WORD **)(a3 + 16);
    v37 = 2147483646;
    do
    {
      if ( !v37 )
        break;
      if ( !*v36 )
        break;
      *v34++ = *v36++;
      --v37;
      --v35;
    }
    while ( v35 );
    v38 = v34 - 1;
    if ( v35 )
      v38 = v34;
    *v38 = 0;
  }
  v39 = -1;
  do
    v31 = *(_WORD *)(*(_QWORD *)(a3 + 24) + 2 * v39++ + 2) == 0;
  while ( !v31 );
  v40 = (unsigned int)(2 * v39 + 2);
  v41 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v40);
  v42 = v41;
  if ( !v41 )
  {
    SetLastError(8u);
    v20[19] = 0;
    v61 = GetLastError();
    v29 = v61;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    v59 = 70;
    goto LABEL_145;
  }
  v43 = v40 >> 1;
  v20[19] = v41;
  if ( v43 )
  {
    v44 = *(_WORD **)(a3 + 24);
    v45 = 2147483646;
    do
    {
      if ( !v45 )
        break;
      if ( !*v44 )
        break;
      *v42++ = *v44++;
      --v45;
      --v43;
    }
    while ( v43 );
    v46 = v42 - 1;
    if ( v43 )
      v46 = v42;
    *v46 = 0;
  }
  v47 = *(_QWORD *)(*(_QWORD *)a3 + 8LL);
  if ( !v47 )
    goto LABEL_40;
  do
    v31 = *(_WORD *)(v47 + 2 * v25++ + 2) == 0;
  while ( !v31 );
  v48 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)(2 * v25 + 2));
  v49 = v48;
  if ( !v48 )
  {
    SetLastError(8u);
    v20[20] = 0;
    v61 = GetLastError();
    v29 = v61;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    v59 = 71;
    goto LABEL_145;
  }
  v50 = (unsigned __int64)(unsigned int)(2 * v25 + 2) >> 1;
  v20[20] = v48;
  if ( v50 )
  {
    v51 = *(_WORD **)(*(_QWORD *)a3 + 8LL);
    do
    {
      if ( !v24 )
        break;
      if ( !*v51 )
        break;
      *v49++ = *v51++;
      --v24;
      --v50;
    }
    while ( v50 );
    v52 = v49 - 1;
    if ( v50 )
      v52 = v49;
    *v52 = 0;
  }
LABEL_40:
  *((_DWORD *)v20 + 68) = _InterlockedIncrement((volatile signed __int32 *)&g_dwInstanceId);
  RtlInitializeSRWLock(v20 + 10);
  RtlInitializeSRWLock(v20 + 8);
  v20[3] = a4;
  v20[32] = a7;
  v20[22] = a8;
  v20[23] = a9;
  *(_DWORD *)v20 = 1665679957;
  v20[6] = 0;
  v20[12] = 1;
  v53 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 24LL) + 32LL);
  if ( v53 )
    v54 = *(_DWORD *)(v53 + 36);
  else
    v54 = 0;
  *((_DWORD *)v20 + 66) = v54;
  v55 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 24LL) + 32LL);
  if ( v55 )
    v56 = *(_DWORD *)(v55 + 32);
  else
    v56 = 0;
  *((_DWORD *)v20 + 8) = a5;
  *((_DWORD *)v20 + 48) = a6;
  *((_DWORD *)v20 + 67) = v56;
  *((_WORD *)v20 + 138) = *(_WORD *)(a3 + 44);
  v20[38] = *(_QWORD *)(a3 + 48);
  *((_OWORD *)v20 + 7) = *(_OWORD *)*(_QWORD *)(a3 + 8);
  *(_OWORD *)(v20 + 35) = *(_OWORD *)*(_QWORD *)(a3 + 32);
  *((_DWORD *)v20 + 74) = *(_DWORD *)(a3 + 40);
  v20[39] = *(_QWORD *)(a3 + 88);
  *((_BYTE *)v20 + 352) = *(_BYTE *)(a3 + 120);
  *((_BYTE *)v20 + 372) = *(_BYTE *)(a3 + 152);
  *((_DWORD *)v20 + 92) = *(_DWORD *)(a3 + 136);
  *((_DWORD *)v20 + 98) = a11;
  v20[50] = a12;
  v20[48] = a13;
  v20[53] = a14;
  *((_BYTE *)v20 + 432) = 0;
  if ( a2 )
  {
    v20[30] = a10;
    v20[31] = *a2;
    *a2 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_qLd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0,
      *((unsigned __int8 *)v20 + 104),
      v20,
      *((unsigned __int8 *)v20 + 104),
      *((_DWORD *)v20 + 8));
  v20[26] = v20 + 25;
  v20[25] = v20 + 25;
  v20[28] = v20 + 27;
  v20[27] = v20 + 27;
  EventW = CreateEventW(0, 1, 0, 0);
  v20[29] = EventW;
  if ( !EventW )
  {
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_53;
    v59 = 73;
    v60 = v27;
LABEL_51:
    WPP_SF_d(v58[2], v59, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v60);
LABEL_53:
    v22 = v20 + 45;
LABEL_54:
    v62 = (void *)v20[29];
    if ( v62 )
      CloseHandle(v62);
    UBPM_MIDL_user_free(*v22, v17, v18, v19);
    UBPM_MIDL_user_free(v20[47], v63, v64, v65);
    UBPM_MIDL_user_free(v20[43], v66, v67, v68);
    UBPM_MIDL_user_free(v20[18], v69, v70, v71);
    UBPM_MIDL_user_free(v20[19], v72, v73, v74);
    UBPM_MIDL_user_free(v20[20], v75, v76, v77);
    UBPM_MIDL_user_free(v20, v78, v79, v80);
    return v29;
  }
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  dword_180050018 = GetCurrentThreadId();
  if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_MachineState, 0, 0) )
  {
    v29 = 1115;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, 1115);
    dword_180050018 = 0;
    RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
    goto LABEL_53;
  }
  v81 = off_18004F130;
  if ( *off_18004F130 != (_UNKNOWN *)&g_leTaskHostContextListHead )
    __fastfail(3u);
  v20[2] = off_18004F130;
  v20[1] = &g_leTaskHostContextListHead;
  *v81 = v20 + 1;
  off_18004F130 = (_UNKNOWN **)(v20 + 1);
  dword_180050018 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  *a15 = v20;
  return v29;
}

```

## disassembly

```asm
0x18001ff30  mov     [rsp+arg_10], rbx
0x18001ff35  mov     [rsp+arg_18], r9
0x18001ff3a  mov     [rsp+arg_8], rdx
0x18001ff3f  mov     [rsp+arg_0], rcx
0x18001ff44  push    rbp
0x18001ff45  push    rsi
0x18001ff46  push    rdi
0x18001ff47  push    r12
0x18001ff49  push    r13
0x18001ff4b  push    r14
0x18001ff4d  push    r15
0x18001ff4f  sub     rsp, 40h
0x18001ff53  mov     rcx, gs:60h
0x18001ff5c  mov     r13, r8
0x18001ff5f  mov     edx, 8; Flags
0x18001ff64  mov     r8d, 1B8h; Size
0x18001ff6a  mov     rcx, [rcx+30h]; HeapHandle
0x18001ff6e  call    cs:__imp_RtlAllocateHeap
0x18001ff75  nop     dword ptr [rax+rax+00h]
0x18001ff7a  mov     [rsp+78h+arg_0], rax
0x18001ff82  mov     r14, rax
0x18001ff85  test    rax, rax
0x18001ff88  jz      loc_1800208D2
0x18001ff8e  movzx   ebx, byte ptr [r13+78h]
0x18001ff93  lea     r15, [rax+168h]
0x18001ff9a  mov     rsi, [r13+80h]
0x18001ffa1  xor     edi, edi
0x18001ffa3  mov     [rsp+78h+var_48], r15
0x18001ffa8  mov     ebp, 7FFFFFFEh
0x18001ffad  mov     [r15], rdi
0x18001ffb0  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18001ffb7  test    bl, bl
0x18001ffb9  jnz     loc_18002092F
0x18001ffbf  movzx   ebx, byte ptr [r13+98h]
0x18001ffc7  mov     r15d, edi
0x18001ffca  mov     rax, [rsp+78h+arg_0]
0x18001ffd2  mov     r14, [r13+0A0h]
0x18001ffd9  mov     [rax+178h], rdi
0x18001ffe0  test    bl, bl
0x18001ffe2  jnz     loc_180020966
0x18001ffe8  mov     esi, r15d
0x18001ffeb  test    r15d, r15d
0x18001ffee  jnz     loc_180020823
0x18001fff4  mov     r14, [rsp+78h+arg_0]
0x18001fffc  mov     eax, [r13+68h]
0x180020000  mov     [r14+14Ch], eax
0x180020007  cmp     qword ptr [r13+70h], 0
0x18002000c  jnz     loc_1800205AD
0x180020012  mov     rcx, [r13+10h]
0x180020016  mov     rax, r12
0x180020019  nop     dword ptr [rax+00000000h]
0x180020020  cmp     word ptr [rcx+rax*2+2], 0
0x180020026  lea     rax, [rax+1]
0x18002002a  jnz     short loc_180020020
0x18002002c  mov     rcx, gs:60h
0x180020035  lea     eax, ds:2[rax*2]
0x18002003c  mov     r8d, eax; Size
0x18002003f  mov     edx, 8; Flags
0x180020044  mov     ebx, eax
0x180020046  mov     rcx, [rcx+30h]; HeapHandle
0x18002004a  call    cs:__imp_RtlAllocateHeap
0x180020051  nop     dword ptr [rax+rax+00h]
0x180020056  mov     rdi, rax
0x180020059  test    rax, rax
0x18002005c  jz      loc_180020881
0x180020062  shr     rbx, 1
0x180020065  mov     [r14+90h], rax
0x18002006c  jz      short loc_1800200A6
0x18002006e  mov     rdx, [r13+10h]
0x180020072  mov     rcx, rbp
0x180020075  test    rcx, rcx
0x180020078  jz      short loc_180020096
0x18002007a  movzx   eax, word ptr [rdx]
0x18002007d  test    ax, ax
0x180020080  jz      short loc_180020096
0x180020082  mov     [rdi], ax
0x180020085  add     rdx, 2
0x180020089  add     rdi, 2
0x18002008d  dec     rcx
0x180020090  sub     rbx, 1
0x180020094  jnz     short loc_180020075
0x180020096  test    rbx, rbx
0x180020099  lea     rcx, [rdi-2]
0x18002009d  cmovnz  rcx, rdi
0x1800200a1  xor     eax, eax
0x1800200a3  mov     [rcx], ax
0x1800200a6  mov     rcx, [r13+18h]
0x1800200aa  mov     rax, r12
0x1800200ad  nop     dword ptr [rax]
0x1800200b0  cmp     word ptr [rcx+rax*2+2], 0
0x1800200b6  lea     rax, [rax+1]
0x1800200ba  jnz     short loc_1800200B0
0x1800200bc  mov     rcx, gs:60h
0x1800200c5  lea     eax, ds:2[rax*2]
0x1800200cc  mov     r8d, eax; Size
0x1800200cf  mov     edx, 8; Flags
0x1800200d4  mov     ebx, eax
0x1800200d6  mov     rcx, [rcx+30h]; HeapHandle
0x1800200da  call    cs:__imp_RtlAllocateHeap
0x1800200e1  nop     dword ptr [rax+rax+00h]
0x1800200e6  mov     rdi, rax
0x1800200e9  test    rax, rax
0x1800200ec  jz      loc_1800209D1
0x1800200f2  shr     rbx, 1
0x1800200f5  mov     [r14+98h], rax
0x1800200fc  jz      short loc_180020136
0x1800200fe  mov     rdx, [r13+18h]
0x180020102  mov     rcx, rbp
0x180020105  test    rcx, rcx
0x180020108  jz      short loc_180020126
0x18002010a  movzx   eax, word ptr [rdx]
0x18002010d  test    ax, ax
0x180020110  jz      short loc_180020126
0x180020112  mov     [rdi], ax
0x180020115  add     rdx, 2
0x180020119  add     rdi, 2
0x18002011d  dec     rcx
0x180020120  sub     rbx, 1
0x180020124  jnz     short loc_180020105
0x180020126  test    rbx, rbx
0x180020129  lea     rcx, [rdi-2]
0x18002012d  cmovnz  rcx, rdi
0x180020131  xor     eax, eax
0x180020133  mov     [rcx], ax
0x180020136  mov     rax, [r13+0]
0x18002013a  mov     rcx, [rax+8]
0x18002013e  test    rcx, rcx
0x180020141  jz      loc_1800201E1
0x180020147  nop     word ptr [rax+rax+00000000h]
0x180020150  cmp     word ptr [rcx+r12*2+2], 0
0x180020157  lea     r12, [r12+1]
0x18002015c  jnz     short loc_180020150
0x18002015e  mov     rcx, gs:60h
0x180020167  lea     eax, ds:2[r12*2]
0x18002016f  mov     r8d, eax; Size
0x180020172  mov     edx, 8; Flags
0x180020177  mov     edi, eax
0x180020179  mov     rcx, [rcx+30h]; HeapHandle
0x18002017d  call    cs:__imp_RtlAllocateHeap
0x180020184  nop     dword ptr [rax+rax+00h]
0x180020189  mov     rbx, rax
0x18002018c  test    rax, rax
0x18002018f  jz      loc_18002041F
0x180020195  shr     rdi, 1
0x180020198  mov     [r14+0A0h], rax
0x18002019f  jz      short loc_1800201E1
0x1800201a1  mov     rax, [r13+0]
0x1800201a5  mov     rcx, [rax+8]
0x1800201a9  nop     dword ptr [rax+00000000h]
0x1800201b0  test    rbp, rbp
0x1800201b3  jz      short loc_1800201D1
0x1800201b5  movzx   eax, word ptr [rcx]
0x1800201b8  test    ax, ax
0x1800201bb  jz      short loc_1800201D1
0x1800201bd  mov     [rbx], ax
0x1800201c0  add     rcx, 2
0x1800201c4  add     rbx, 2
0x1800201c8  dec     rbp
0x1800201cb  sub     rdi, 1
0x1800201cf  jnz     short loc_1800201B0
0x1800201d1  test    rdi, rdi
0x1800201d4  lea     rcx, [rbx-2]
0x1800201d8  cmovnz  rcx, rbx
0x1800201dc  xor     eax, eax
0x1800201de  mov     [rcx], ax
0x1800201e1  mov     eax, 1
0x1800201e6  lock xadd cs:?g_dwInstanceId@@3KC, eax; ulong volatile g_dwInstanceId
0x1800201ee  inc     eax
0x1800201f0  lea     rcx, [r14+50h]
0x1800201f4  mov     [r14+110h], eax
0x1800201fb  call    cs:__imp_RtlInitializeSRWLock
0x180020202  nop     dword ptr [rax+rax+00h]
0x180020207  lea     rcx, [r14+40h]
0x18002020b  call    cs:__imp_RtlInitializeSRWLock
0x180020212  nop     dword ptr [rax+rax+00h]
0x180020217  mov     rax, [rsp+78h+arg_18]
0x18002021f  xor     edx, edx
0x180020221  mov     [r14+18h], rax
0x180020225  mov     rax, [rsp+78h+arg_30]
0x18002022d  mov     [r14+100h], rax
0x180020234  mov     rax, [rsp+78h+arg_38]
0x18002023c  mov     [r14+0B0h], rax
0x180020243  mov     rax, [rsp+78h+arg_40]
0x18002024b  mov     [r14+0B8h], rax
0x180020252  mov     dword ptr [r14], 63484255h
0x180020259  mov     [r14+30h], rdx
0x18002025d  mov     qword ptr [r14+60h], 1
0x180020265  mov     rax, [r13+0]
0x180020269  mov     rcx, [rax+18h]
0x18002026d  mov     rax, [rcx+20h]
0x180020271  test    rax, rax
0x180020274  jnz     loc_1800204CC
0x18002027a  mov     eax, edx
0x18002027c  mov     [r14+108h], eax
0x180020283  mov     rax, [r13+0]
0x180020287  mov     rcx, [rax+18h]
0x18002028b  mov     rax, [rcx+20h]
0x18002028f  test    rax, rax
0x180020292  jnz     loc_1800204D4
0x180020298  mov     ecx, edx
0x18002029a  mov     eax, [rsp+78h+arg_20]
0x1800202a1  mov     [r14+20h], eax
0x1800202a5  mov     eax, [rsp+78h+arg_28]
0x1800202ac  mov     [r14+0C0h], eax
0x1800202b3  mov     [r14+10Ch], ecx
0x1800202ba  movzx   eax, word ptr [r13+2Ch]
0x1800202bf  mov     rcx, [rsp+78h+arg_8]
0x1800202c7  mov     [r14+114h], ax
0x1800202cf  mov     rax, [r13+30h]
0x1800202d3  mov     [r14+130h], rax
0x1800202da  mov     rax, [r13+8]
0x1800202de  movups  xmm0, xmmword ptr [rax]
0x1800202e1  movups  xmmword ptr [r14+70h], xmm0
0x1800202e6  mov     rax, [r13+20h]
0x1800202ea  movups  xmm0, xmmword ptr [rax]
0x1800202ed  movups  xmmword ptr [r14+118h], xmm0
0x1800202f5  mov     eax, [r13+28h]
0x1800202f9  mov     [r14+128h], eax
0x180020300  mov     rax, [r13+58h]
0x180020304  mov     [r14+138h], rax
0x18002030b  movzx   eax, byte ptr [r13+78h]
0x180020310  mov     [r14+160h], al
0x180020317  movzx   eax, byte ptr [r13+98h]
0x18002031f  mov     [r14+174h], al
0x180020326  mov     eax, [r13+88h]
0x18002032d  mov     [r14+170h], eax
0x180020334  mov     eax, [rsp+78h+arg_50]
0x18002033b  mov     [r14+188h], eax
0x180020342  mov     rax, [rsp+78h+arg_58]
0x18002034a  mov     [r14+190h], rax
0x180020351  mov     rax, [rsp+78h+arg_60]
0x180020359  mov     [r14+180h], rax
0x180020360  mov     rax, [rsp+78h+arg_68]
0x180020368  mov     [r14+1A8h], rax
0x18002036f  mov     [r14+1B0h], dl
0x180020376  test    rcx, rcx
0x180020379  jz      short loc_180020397
0x18002037b  mov     rax, [rsp+78h+arg_48]
0x180020383  mov     [r14+0F0h], rax
0x18002038a  mov     rax, [rcx]
0x18002038d  mov     [r14+0F8h], rax
0x180020394  mov     [rcx], rdx
0x180020397  mov     rcx, cs:WPP_GLOBAL_Control
0x18002039e  lea     rbx, WPP_GLOBAL_Control
0x1800203a5  cmp     rcx, rbx
0x1800203a8  jnz     loc_180020580
0x1800203ae  lea     rax, [r14+0C8h]
0x1800203b5  xor     r9d, r9d; lpName
0x1800203b8  mov     [rax+8], rax
0x1800203bc  xor     r8d, r8d; bInitialState
0x1800203bf  mov     [rax], rax
0x1800203c2  mov     edx, 1; bManualReset
0x1800203c7  lea     rax, [r14+0D8h]
0x1800203ce  xor     ecx, ecx; lpEventAttributes
0x1800203d0  mov     [rax+8], rax
0x1800203d4  mov     [rax], rax
0x1800203d7  call    cs:__imp_CreateEventW
0x1800203de  nop     dword ptr [rax+rax+00h]
0x1800203e3  mov     [r14+0E8h], rax
0x1800203ea  test    rax, rax
0x1800203ed  jnz     loc_1800204DC
0x1800203f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203fa  cmp     rcx, rbx
0x1800203fd  jz      short loc_18002045C
0x1800203ff  test    byte ptr [rcx+1Ch], 1
0x180020403  jz      short loc_18002045C
0x180020405  mov     edx, 49h ; 'I'
0x18002040a  mov     r9d, r15d
0x18002040d  mov     rcx, [rcx+10h]
0x180020411  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180020418  call    WPP_SF_d
0x18002041d  jmp     short loc_18002045C
0x18002041f  mov     ecx, 8; dwErrCode
0x180020424  call    cs:__imp_SetLastError
0x18002042b  nop     dword ptr [rax+rax+00h]
0x180020430  mov     [r14+0A0h], rbx
0x180020437  call    cs:__imp_GetLastError
0x18002043e  nop     dword ptr [rax+rax+00h]
0x180020443  mov     esi, eax
0x180020445  mov     rcx, cs:WPP_GLOBAL_Control
0x18002044c  lea     rbx, WPP_GLOBAL_Control
0x180020453  cmp     rcx, rbx
0x180020456  jnz     loc_180020A1F
0x18002045c  lea     r15, [r14+168h]
0x180020463  mov     rcx, [r14+0E8h]; hObject
0x18002046a  test    rcx, rcx
0x18002046d  jz      short loc_18002047B
0x18002046f  call    cs:__imp_CloseHandle
0x180020476  nop     dword ptr [rax+rax+00h]
0x18002047b  mov     rcx, [r15]
0x18002047e  call    UBPM_MIDL_user_free
0x180020483  mov     rcx, [r14+178h]
0x18002048a  call    UBPM_MIDL_user_free
0x18002048f  mov     rcx, [r14+158h]
0x180020496  call    UBPM_MIDL_user_free
0x18002049b  mov     rcx, [r14+90h]
0x1800204a2  call    UBPM_MIDL_user_free
0x1800204a7  mov     rcx, [r14+98h]
0x1800204ae  call    UBPM_MIDL_user_free
0x1800204b3  mov     rcx, [r14+0A0h]
  ... truncated ...
```
