# UbpmpSendCommandGetResponse

- ea: `0x18000e660`
- end: `0x18000f98e`
- name: `UbpmpSendCommandGetResponse`
- size: `4910`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, unsigned __int16)`
- caller_count: `6`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002fcc`
- `0x180008f30`
- `0x18000b6d0`
- `0x18000e660`
- `0x180021060`
- `0x180029590`

## callees

- `0x18000c248`
- `0x18000e660`
- `0x18000f9a0`
- `0x180019d90`
- `0x18001e9f4`
- `0x180020328`
- `0x1800260fc`
- `0x180029fbc`
- `0x180030cec`
- `0x180032e38`
- `0x180034f3c`
- `0x18003c494`
- `0x18003c830`
- `0x18003ca54`
- `0x18003cc78`
- `0x18003ce90`
- `0x18003d7d2`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000ed7e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000ed7e`
- `ntdll!RtlAllocateHeap` at `0x18000e6ff`
- `ntdll!RtlAllocateHeap` at `0x18000e736`
- `ntdll!RtlAllocateHeap` at `0x18000e7fb`
- `ntdll!RtlAllocateHeap` at `0x18000e89a`
- `ntdll!RtlAllocateHeap` at `0x18000ea0c`
- `ntdll!RtlAllocateHeap` at `0x18000eab3`
- `ntdll!RtlAllocateHeap` at `0x18000e6ff`
- `ntdll!RtlAllocateHeap` at `0x18000e736`
- `ntdll!RtlAllocateHeap` at `0x18000e7fb`
- `ntdll!RtlAllocateHeap` at `0x18000e89a`
- `ntdll!RtlAllocateHeap` at `0x18000ea0c`
- `ntdll!RtlAllocateHeap` at `0x18000eab3`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e6d8`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000ef5d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f3ff`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f452`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f466`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f47d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f4cb`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e6d8`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000ef5d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f3ff`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f452`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f466`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f47d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f4cb`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e6ab`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e6ab`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000eade`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000eade`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ebf9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ef1c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f79b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f83d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f876`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f950`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ebf9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ef1c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f79b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f83d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f876`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f950`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eae4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f862`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ec09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f3b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f540`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f59d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f675`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f728`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ec09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f3b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f540`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f59d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f675`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f728`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000eb7b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000eb7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000edaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f95b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000edaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f95b`

## pseudocode

```c
__int64 __fastcall UbpmpSendCommandGetResponse(__int64 a1, __int64 a2, _QWORD *a3, unsigned __int16 a4)
{
  __int64 v4; // rbx
  unsigned int v5; // edi
  __int64 v6; // rsi
  _QWORD *v7; // r13
  _QWORD *v8; // r14
  __int64 v9; // r15
  DWORD LastError; // r12d
  unsigned __int64 v11; // r8
  _QWORD *v12; // rax
  __int64 v13; // rsi
  __int64 v14; // r15
  __int64 v15; // r13
  __int64 v16; // rbx
  DWORD v17; // eax
  __int64 v18; // r15
  __int64 v19; // rbx
  __int64 v20; // rax
  bool v21; // zf
  SIZE_T v22; // rbx
  _WORD *v23; // rax
  HINSTANCE v24; // rdx
  _WORD *v25; // rdi
  SIZE_T v26; // rbx
  __int64 v27; // rcx
  _WORD *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rax
  SIZE_T v31; // rdi
  _WORD *v32; // rax
  _WORD *v33; // rbx
  SIZE_T v34; // rdi
  __int64 v35; // rcx
  _WORD *v36; // rcx
  signed __int32 v37; // r14d
  _OWORD *v38; // rax
  _WORD *v39; // rbx
  __int64 v40; // rax
  _WORD *v41; // rax
  _WORD *v42; // rbx
  unsigned __int64 v43; // rdi
  _WORD *v44; // rcx
  _WORD *v45; // rcx
  signed __int64 v46; // rax
  _OWORD *v47; // rax
  __int64 v48; // r8
  char v49; // al
  unsigned int v50; // r14d
  _QWORD *v51; // rsi
  _QWORD *v52; // rdi
  _QWORD *v53; // rax
  _QWORD *v54; // rcx
  __int64 v55; // r8
  _QWORD *v56; // rdx
  DWORD v57; // eax
  _QWORD *v58; // rcx
  _QWORD *v59; // rdi
  __int64 v61; // rax
  unsigned int v62; // edi
  _WORD *v63; // rdx
  __int64 v64; // rcx
  _WORD *v65; // rcx
  void *v66; // rcx
  _QWORD *v67; // r8
  __int64 v68; // rcx
  _QWORD *v69; // r15
  _QWORD *v70; // rdx
  _QWORD *v71; // r8
  __int64 v72; // rcx
  __int64 v73; // rax
  char v74; // r14
  __int16 v75; // ax
  const wchar_t *v76; // r9
  _QWORD *v77; // r8
  __int64 v78; // r8
  void *v79; // rax
  __int64 v80; // r8
  __int64 v81; // rax
  unsigned int v82; // eax
  __int64 v83; // rcx
  __int64 v84; // r9
  char *v85; // r8
  _WORD *v86; // rdx
  char *v87; // rcx
  char *v88; // rdi
  unsigned __int8 v89; // r11
  _QWORD *v90; // r8
  char *v91; // rax
  char *v92; // r14
  __int64 v93; // rax
  unsigned int v94; // eax
  __int64 v95; // rcx
  __int64 v96; // r9
  char *v97; // r8
  _WORD *v98; // rdx
  char *v99; // rcx
  char *v100; // rdi
  unsigned __int8 v101; // r11
  _QWORD *v102; // r8
  char *v103; // rax
  char *v104; // r14
  __int64 v105; // rax
  __int64 v106; // rcx
  __int64 v107; // rax
  unsigned int v108; // eax
  unsigned int v109; // r8d
  _QWORD *v110; // rcx
  __int64 v111; // rdx
  __int64 v112; // r9
  unsigned __int8 i; // dl
  SIZE_T v114; // rcx
  __int64 v115; // rcx
  __int64 v116; // rax
  unsigned int v117; // eax
  unsigned int v118; // r8d
  unsigned __int8 j; // dl
  SIZE_T v120; // rcx
  __int64 v121; // r8
  _QWORD *v122; // rcx
  __int64 v123; // rdx
  const wchar_t **v124; // rax
  const wchar_t *v125; // rcx
  __int64 v126; // rdx
  DWORD v127; // eax
  DWORD v128; // eax
  __int64 v129; // rcx
  _QWORD *v130; // rcx
  __int64 v131; // rdx
  __int64 v132; // rcx
  DWORD v133; // eax
  __int64 v134; // rcx
  int v135; // [rsp+40h] [rbp-38h]
  unsigned int v136; // [rsp+44h] [rbp-34h]
  _QWORD *v137; // [rsp+48h] [rbp-30h] BYREF
  _QWORD *Heap; // [rsp+50h] [rbp-28h]
  HANDLE hObject; // [rsp+58h] [rbp-20h] BYREF
  _OWORD *v140; // [rsp+60h] [rbp-18h]
  __int64 v141; // [rsp+68h] [rbp-10h]

  v4 = a1 + 64;
  v5 = a4;
  v6 = a1;
  v141 = a1 + 64;
  v7 = 0;
  v8 = 0;
  v137 = 0;
  v9 = a2;
  hObject = 0;
  RtlAcquireSRWLockShared(a1 + 64);
  if ( (*(_BYTE *)(v6 + 104) & 0x10) == 0 )
  {
    RtlReleaseSRWLockShared(v4);
    LastError = 50;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, v121, *(unsigned __int8 *)(v6 + 104), 50);
    goto LABEL_73;
  }
  LastError = 0;
  v140 = 0;
  v135 = 0;
  v136 = v5;
  if ( v5 != 1 )
  {
    switch ( v5 )
    {
      case 2u:
        v66 = *(void **)(v6 + 248);
        if ( v66 )
        {
          if ( *(_QWORD *)(v6 + 256) )
            v66 = *(void **)(v6 + 256);
          if ( !DuplicateTokenEx(v66, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
          {
            LastError = GetLastError();
            RtlReleaseSRWLockShared(v4);
            v122 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_72;
            v123 = 132;
            goto LABEL_226;
          }
          LastError = UbpmFileAccessCheck(hObject);
          if ( LastError )
          {
            RtlReleaseSRWLockShared(v4);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_72;
            v124 = *(const wchar_t ***)(*(_QWORD *)(*(_QWORD *)v9 + 24LL) + 40LL);
            if ( v124 )
              v125 = *v124;
            else
              v125 = L"NULL";
            WPP_SF_SSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              133,
              (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
              *(_QWORD *)(v9 + 16),
              (__int64)v125,
              LastError);
            v8 = v137;
            goto LABEL_73;
          }
          CloseHandle(hObject);
          hObject = 0;
        }
        v67 = (_QWORD *)*a3;
        v137 = (_QWORD *)*a3;
        if ( v9 )
        {
          v68 = *(_QWORD *)(*(_QWORD *)v9 + 24LL);
          if ( v68 )
          {
            if ( !v67 && *(_QWORD *)(v9 + 8) )
            {
              v140 = *(_OWORD **)(v68 + 8);
              v135 = *(_DWORD *)(v9 + 84);
              goto LABEL_3;
            }
          }
        }
        LastError = 87;
        RtlReleaseSRWLockShared(v4);
        break;
      case 3u:
        v77 = (_QWORD *)*a3;
        v137 = (_QWORD *)*a3;
        if ( v9 || !v77 )
        {
          LastError = 87;
          goto LABEL_3;
        }
        LODWORD(v8) = *((_DWORD *)v77 + 14);
        if ( (unsigned int)UbpmpIsTaskStarted(v6, (unsigned int)v8) )
        {
          v140 = (_OWORD *)(v78 + 32);
          goto LABEL_3;
        }
        LastError = 2;
        RtlReleaseSRWLockShared(v4);
        break;
      case 4u:
        LastError = 87;
        if ( v9 )
          LastError = 0;
        goto LABEL_3;
      default:
        LastError = 50;
        RtlReleaseSRWLockShared(v4);
        break;
    }
LABEL_125:
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v76 = L"start";
    if ( v5 != 2 )
      v76 = L"stop";
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      134,
      (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
      (_DWORD)v76,
      LastError);
    v8 = v137;
    goto LABEL_73;
  }
LABEL_3:
  RtlReleaseSRWLockShared(v4);
  if ( LastError )
    goto LABEL_125;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
  v7 = Heap;
  if ( !Heap )
  {
    SetLastError(8u);
    v57 = GetLastError();
    LastError = v57;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v126 = 135;
    goto LABEL_236;
  }
  if ( v5 != 2 )
    goto LABEL_51;
  v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xC8u);
  v137 = v12;
  v8 = v12;
  if ( !v12 )
  {
    SetLastError(8u);
    v127 = GetLastError();
    LastError = v127;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v127);
    goto LABEL_73;
  }
  LastError = 0;
  v12[1] = 1;
  v13 = 2147483646;
  v14 = *(_QWORD *)(v9 + 128);
  v15 = -1;
  v16 = *(unsigned __int8 *)(a2 + 120);
  v12[21] = 0;
  if ( (_BYTE)v16 )
  {
    v109 = 0;
    for ( i = 0; i < (unsigned __int8)v16; ++i )
    {
      v106 = *(_QWORD *)(v14 + 8LL * i);
      if ( v106 )
      {
        v107 = -1;
        do
          v21 = *(_WORD *)(v106 + 2 * v107++ + 2) == 0;
        while ( !v21 );
        v108 = 2 * v107 + 2;
        v109 += v108;
        if ( v109 < v108 )
          goto LABEL_193;
      }
    }
    v114 = 8 * (_DWORD)v16 + v109;
    if ( (unsigned int)v114 < 8 * (int)v16 )
    {
LABEL_193:
      LastError = 534;
    }
    else
    {
      v91 = (char *)UbpmAlloc(v114);
      v92 = v91;
      if ( v91 )
      {
        v89 = 0;
        v88 = &v91[8 * v16];
        do
        {
          if ( *(_QWORD *)(v14 + 8LL * v89) )
          {
            *(_QWORD *)&v92[8 * v89] = v88;
            v86 = *(_WORD **)(v14 + 8LL * v89);
            v93 = -1;
            do
              ++v93;
            while ( v86[v93] );
            v82 = v93 + 1;
            if ( v82 )
            {
              if ( v82 > 0x7FFFFFFFuLL )
              {
                *(_WORD *)v88 = 0;
              }
              else
              {
                v83 = 2147483646;
                v84 = v82;
                v85 = v88;
                do
                {
                  if ( !v83 )
                    break;
                  if ( !*v86 )
                    break;
                  *(_WORD *)v85 = *v86++;
                  v85 += 2;
                  --v83;
                  --v84;
                }
                while ( v84 );
                v87 = v85 - 2;
                if ( v84 )
                  v87 = v85;
                *(_WORD *)v87 = 0;
              }
            }
            v88 += 2 * v82;
          }
          ++v89;
        }
        while ( v89 < (unsigned __int8)v16 );
        v90 = v137;
        v137[21] = v92;
        v8 = v90;
        goto LABEL_8;
      }
      v8 = v137;
      LastError = GetLastError();
      if ( !LastError )
      {
        LastError = 0;
        goto LABEL_8;
      }
    }
    v110 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_215;
    v111 = 137;
    v112 = LastError;
    goto LABEL_210;
  }
LABEL_8:
  v17 = 0;
  v18 = *(_QWORD *)(a2 + 160);
  v19 = *(unsigned __int8 *)(a2 + 152);
  v8[23] = 0;
  if ( !(_BYTE)v19 )
    goto LABEL_9;
  v118 = 0;
  for ( j = 0; j < (unsigned __int8)v19; ++j )
  {
    v115 = *(_QWORD *)(v18 + 8LL * j);
    if ( v115 )
    {
      v116 = -1;
      do
        v21 = *(_WORD *)(v115 + 2 * v116++ + 2) == 0;
      while ( !v21 );
      v117 = 2 * v116 + 2;
      v118 += v117;
      if ( v118 < v117 )
        goto LABEL_205;
    }
  }
  v120 = v118 + 8 * (_DWORD)v19;
  if ( (unsigned int)v120 < 8 * (int)v19 )
  {
LABEL_205:
    LastError = 534;
    v17 = 534;
    goto LABEL_206;
  }
  v103 = (char *)UbpmAlloc(v120);
  v104 = v103;
  if ( !v103 )
  {
    v17 = GetLastError();
    v8 = v137;
LABEL_9:
    LastError = v17;
    if ( !v17 )
      goto LABEL_10;
LABEL_206:
    v110 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_215;
    v111 = 138;
    goto LABEL_209;
  }
  v101 = 0;
  v100 = &v103[8 * v19];
  do
  {
    if ( *(_QWORD *)(v18 + 8LL * v101) )
    {
      *(_QWORD *)&v104[8 * v101] = v100;
      v98 = *(_WORD **)(v18 + 8LL * v101);
      v105 = -1;
      do
        ++v105;
      while ( v98[v105] );
      v94 = v105 + 1;
      if ( v94 )
      {
        if ( v94 > 0x7FFFFFFFuLL )
        {
          *(_WORD *)v100 = 0;
        }
        else
        {
          v95 = 2147483646;
          v96 = v94;
          v97 = v100;
          do
          {
            if ( !v95 )
              break;
            if ( !*v98 )
              break;
            *(_WORD *)v97 = *v98++;
            v97 += 2;
            --v95;
            --v96;
          }
          while ( v96 );
          v99 = v97 - 2;
          if ( v96 )
            v99 = v97;
          *(_WORD *)v99 = 0;
        }
      }
      v100 += 2 * v94;
    }
    ++v101;
  }
  while ( v101 < (unsigned __int8)v19 );
  v102 = v137;
  v137[23] = v104;
  v8 = v102;
LABEL_10:
  v9 = a2;
  *((_DWORD *)v8 + 36) = *(_DWORD *)(a2 + 104);
  if ( *(_QWORD *)(a2 + 112) )
  {
    v79 = UbpmAlloc(*(unsigned int *)(a2 + 108));
    v8[19] = v79;
    if ( v79 )
    {
      memcpy_0(v79, *(const void **)(a2 + 112), *(unsigned int *)(a2 + 108));
      *((_DWORD *)v8 + 37) = *(_DWORD *)(a2 + 108);
      goto LABEL_11;
    }
    v17 = GetLastError();
    LastError = v17;
    v110 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_215;
    v111 = 139;
LABEL_209:
    v112 = v17;
LABEL_210:
    WPP_SF_d(v110[2], v111, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v112);
    goto LABEL_215;
  }
LABEL_11:
  v20 = -1;
  do
    v21 = *(_WORD *)(*(_QWORD *)(a2 + 16) + 2 * v20++ + 2) == 0;
  while ( !v21 );
  v22 = (unsigned int)(2 * v20 + 2);
  v23 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v22);
  v25 = v23;
  if ( !v23 )
  {
    SetLastError(8u);
    v8[10] = 0;
    v17 = GetLastError();
    LastError = v17;
    v110 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_215;
    v111 = 140;
    goto LABEL_209;
  }
  v26 = v22 >> 1;
  v11 = (unsigned __int64)v137;
  v137[10] = v23;
  if ( v26 )
  {
    v24 = *(HINSTANCE *)(a2 + 16);
    v27 = 2147483646;
    do
    {
      if ( !v27 )
        break;
      if ( !*(_WORD *)v24 )
        break;
      *v25 = *(_WORD *)v24;
      v24 = (HINSTANCE)((char *)v24 + 2);
      ++v25;
      --v27;
      --v26;
    }
    while ( v26 );
    v28 = v25 - 1;
    if ( v26 )
      v28 = v25;
    *v28 = 0;
  }
  v29 = *(_QWORD *)(*(_QWORD *)a2 + 8LL);
  if ( v29 )
  {
    v30 = -1;
    do
      v21 = *(_WORD *)(v29 + 2 * v30++ + 2) == 0;
    while ( !v21 );
    v31 = (unsigned int)(2 * v30 + 2);
    v32 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v31);
    v33 = v32;
    if ( v32 )
    {
      v34 = v31 >> 1;
      v11 = (unsigned __int64)v137;
      v137[11] = v32;
      if ( v34 )
      {
        v35 = 2147483646;
        v24 = *(HINSTANCE *)(*(_QWORD *)a2 + 8LL);
        do
        {
          if ( !v35 )
            break;
          if ( !*(_WORD *)v24 )
            break;
          *v33 = *(_WORD *)v24;
          v24 = (HINSTANCE)((char *)v24 + 2);
          ++v33;
          --v35;
          --v34;
        }
        while ( v34 );
        v36 = v33 - 1;
        if ( v34 )
          v36 = v33;
        *v36 = 0;
      }
      goto LABEL_34;
    }
    SetLastError(8u);
    v8 = v137;
    v137[11] = 0;
    v17 = GetLastError();
    LastError = v17;
    v110 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_215:
      v7 = Heap;
      goto LABEL_73;
    }
    v111 = 141;
    goto LABEL_209;
  }
LABEL_34:
  if ( (*(_DWORD *)(a2 + 136) & 0x200000) != 0 )
  {
    UbpmUtilsSystemPowerOn(*(const unsigned __int16 **)(a2 + 16), v24, (void **)(v11 + 192));
    v11 = (unsigned __int64)v137;
  }
  v37 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwInstanceId, 1u);
  *(_QWORD *)(v11 + 24) = v11 + 16;
  LODWORD(v8) = v37 + 1;
  *(_QWORD *)(v11 + 16) = v11 + 16;
  v38 = v140;
  *(_DWORD *)v11 = 1950892629;
  *(_QWORD *)(v11 + 48) = a1;
  *(_OWORD *)(v11 + 32) = *v38;
  *(_DWORD *)(v11 + 56) = (_DWORD)v8;
  *(_OWORD *)(v11 + 60) = *(_OWORD *)*(_QWORD *)(a2 + 8);
  *(_WORD *)(v11 + 106) = *(_WORD *)(a2 + 44);
  *(_QWORD *)(v11 + 128) = *(_QWORD *)(a2 + 48);
  *(_OWORD *)(v11 + 108) = *(_OWORD *)*(_QWORD *)(a2 + 32);
  *(_DWORD *)(v11 + 124) = *(_DWORD *)(a2 + 40);
  *(_QWORD *)(v11 + 136) = *(_QWORD *)(a2 + 88);
  v39 = *(_WORD **)(a2 + 96);
  if ( !v39 )
    v39 = *(_WORD **)(*(_QWORD *)(*(_QWORD *)a2 + 24LL) + 16LL);
  *(_BYTE *)(v11 + 160) = *(_BYTE *)(a2 + 120);
  *(_BYTE *)(v11 + 180) = *(_BYTE *)(a2 + 152);
  *(_DWORD *)(v11 + 176) = *(_DWORD *)(a2 + 136);
  if ( !v39 )
    goto LABEL_39;
  v61 = -1;
  do
    v21 = v39[++v61] == 0;
  while ( !v21 );
  v62 = 2 * v61 + 2;
  v63 = UbpmAlloc(v62);
  Heap[3] = v63;
  if ( !v63 )
  {
    v128 = GetLastError();
    LastError = v128;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v128);
    v8 = v137;
    goto LABEL_215;
  }
  v11 = (unsigned __int64)v62 >> 1;
  if ( v11 )
  {
    v64 = 2147483646;
    do
    {
      if ( !v64 )
        break;
      if ( !*v39 )
        break;
      *v63++ = *v39++;
      --v64;
      --v11;
    }
    while ( v11 );
    v65 = v63 - 1;
    if ( v11 )
      v65 = v63;
    *v65 = 0;
  }
LABEL_39:
  v40 = *(_QWORD *)(a2 + 16);
  if ( v40 )
  {
    do
      v21 = *(_WORD *)(v40 + 2 * v15++ + 2) == 0;
    while ( !v21 );
    v41 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)(2 * v15 + 2));
    v42 = v41;
    if ( !v41 )
    {
      SetLastError(8u);
      v7 = Heap;
      Heap[2] = 0;
      v57 = GetLastError();
      LastError = v57;
      v58 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_72;
      v126 = 143;
      goto LABEL_236;
    }
    v43 = (unsigned __int64)(unsigned int)(2 * v15 + 2) >> 1;
    v7 = Heap;
    Heap[2] = v41;
    if ( v43 )
    {
      v44 = *(_WORD **)(a2 + 16);
      do
      {
        if ( !v13 )
          break;
        if ( !*v44 )
          break;
        *v42++ = *v44++;
        --v13;
        --v43;
      }
      while ( v43 );
      v45 = v42 - 1;
      if ( v43 )
        v45 = v42;
      *v45 = 0;
    }
  }
  else
  {
    v7 = Heap;
  }
  LOWORD(v5) = a4;
  v6 = a1;
LABEL_51:
  v46 = _InterlockedExchangeAdd64(&g_ullCommandSequence, 1u);
  *(_WORD *)v7 = v5;
  v7[4] = v46 + 1;
  *((_DWORD *)v7 + 12) = v135;
  *((_DWORD *)v7 + 14) = (_DWORD)v8;
  if ( (unsigned __int16)(v5 - 2) > 1u )
  {
    if ( (_WORD)v5 == 4 )
    {
      *((_DWORD *)v7 + 13) = *(_DWORD *)(v9 + 80);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_dqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, v11, *(unsigned int *)(v9 + 80), v6, *(_DWORD *)(v6 + 32));
    }
    goto LABEL_54;
  }
  v47 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
  if ( !v47 )
  {
    SetLastError(8u);
    v7[1] = 0;
    v57 = GetLastError();
    LastError = v57;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v126 = 144;
LABEL_236:
    WPP_SF_d(v58[2], v126, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v57);
    v8 = v137;
    goto LABEL_73;
  }
  v7[1] = v47;
  *v47 = *v140;
LABEL_54:
  RtlAcquireSRWLockExclusive(v6 + 64);
  *(_DWORD *)(v6 + 72) = GetCurrentThreadId();
  v49 = *(_BYTE *)(v6 + 104);
  if ( v49 < 0 || (v49 & 4) != 0 )
  {
    LastError = 1237;
    if ( (_WORD)v5 != 2 )
      LastError = 1067;
    if ( (_WORD)v5 == 3 )
    {
      UbpmpDecrementTaskRefAndDelete(&v137);
      v59 = a3;
      v8 = 0;
      v137 = 0;
      *a3 = 0;
    }
    else
    {
      v8 = v137;
      v59 = a3;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        146,
        v48,
        v136,
        *(_DWORD *)(v6 + 32),
        *(unsigned __int8 *)(v6 + 104),
        LastError);
    *(_DWORD *)(v6 + 72) = 0;
    RtlReleaseSRWLockExclusive(v6 + 64);
    goto LABEL_74;
  }
  v50 = 0;
  v51 = *(_QWORD **)(v6 + 224);
  v52 = (_QWORD *)(a1 + 216);
  do
  {
    while ( 1 )
    {
      if ( v51 == v52 )
      {
        if ( v50 < 0x2710 )
        {
          v53 = UbpmAlloc(0x20u);
          if ( v53 )
          {
            v8 = v137;
            v53[3] = v137;
            v53[2] = v7;
            v54 = *(_QWORD **)(a1 + 224);
            if ( (_QWORD *)*v54 == v52 )
            {
              *v53 = v52;
              v53[1] = v54;
              *v54 = v53;
              *(_QWORD *)(a1 + 224) = v53;
              if ( v8 )
                _InterlockedIncrement64(v8 + 1);
              SetEvent(*(HANDLE *)(a1 + 232));
              if ( a4 != 2 )
              {
                if ( a4 == 3 )
                {
                  UbpmpDecrementTaskRefAndDelete(&v137);
                  v8 = 0;
                  v137 = 0;
                  *a3 = 0;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                    WPP_SF_qdd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      152,
                      v80,
                      a1,
                      *(_DWORD *)(a1 + 32),
                      *(unsigned __int16 *)(a1 + 196));
                }
                goto LABEL_70;
              }
              ++*(_WORD *)(a1 + 196);
              v56 = *(_QWORD **)(a1 + 208);
              if ( *v56 == a1 + 200 )
              {
                v8[2] = a1 + 200;
                v8[3] = v56;
                *v56 = v8 + 2;
                *(_QWORD *)(a1 + 208) = v8 + 2;
                _InterlockedIncrement64(v8 + 1);
                *a3 = v8;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                  WPP_SF_qqidd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    151,
                    v55,
                    a1,
                    v8,
                    v8[12],
                    *(_DWORD *)(a1 + 32),
                    *(unsigned __int16 *)(a1 + 196));
                v8 = 0;
                v137 = 0;
LABEL_70:
                *(_DWORD *)(a1 + 72) = 0;
                RtlReleaseSRWLockExclusive(a1 + 64);
                v7 = 0;
                goto LABEL_73;
              }
            }
LABEL_135:
            __fastfail(3u);
          }
          v133 = GetLastError();
          v134 = v141;
          LastError = v133;
          *(_DWORD *)(v141 + 8) = 0;
          RtlReleaseSRWLockExclusive(v134);
          v122 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_72;
          v123 = 150;
LABEL_226:
          WPP_SF_d(v122[2], v123, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
          goto LABEL_72;
        }
        v132 = v141;
        LastError = 4320;
        *(_DWORD *)(v141 + 8) = 0;
        RtlReleaseSRWLockExclusive(v132);
        v130 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_72;
        v131 = 149;
LABEL_268:
        WPP_SF_dd(
          v130[2],
          v131,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *(unsigned int *)(a1 + 32),
          *(unsigned __int8 *)(a1 + 104));
        goto LABEL_72;
      }
      v69 = v51;
      v70 = v51 + 1;
      ++v50;
      v71 = v51;
      v51 = (_QWORD *)v51[1];
      v72 = v69[2];
      if ( *(_WORD *)v72 != 1 )
        break;
      if ( a4 == 1 )
      {
        v129 = v141;
        *(_DWORD *)(v141 + 8) = 0;
        RtlReleaseSRWLockExclusive(v129);
        v130 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_72;
        v131 = 147;
        goto LABEL_268;
      }
      v81 = *v71;
      if ( *(_QWORD **)(*v71 + 8LL) != v69 || (_QWORD *)*v51 != v69 )
        goto LABEL_135;
      *v51 = v81;
      *(_QWORD *)(v81 + 8) = v51;
      *v70 = v69;
      *v71 = v69;
      UBPM_MIDL_user_free(*(_QWORD *)(v69[2] + 16LL));
      UBPM_MIDL_user_free(*(_QWORD *)(v69[2] + 24LL));
      UBPM_MIDL_user_free(*(_QWORD *)(v69[2] + 8LL));
      UBPM_MIDL_user_free(v69[2]);
      if ( v69[3] )
        UbpmpDecrementTaskRefAndDelete(&v137);
      UBPM_MIDL_user_free(v69);
    }
  }
  while ( *(_WORD *)v72 != 2 || *(_DWORD *)(v72 + 56) != *((_DWORD *)v7 + 14) || a4 != 3 );
  v73 = *v69;
  if ( *(_QWORD **)(*v69 + 8LL) != v69 || (_QWORD *)*v51 != v69 )
    goto LABEL_135;
  *v51 = v73;
  v74 = 0;
  *(_QWORD *)(v73 + 8) = v51;
  *v70 = v69;
  *v69 = v69;
  UBPM_MIDL_user_free(*(_QWORD *)(v69[2] + 16LL));
  UBPM_MIDL_user_free(*(_QWORD *)(v69[2] + 24LL));
  UBPM_MIDL_user_free(*(_QWORD *)(v69[2] + 8LL));
  UBPM_MIDL_user_free(v69[2]);
  if ( v69[3] )
    UbpmpDecrementTaskRefAndDelete(&v137);
  UBPM_MIDL_user_free(v69);
  v75 = *(_WORD *)(a1 + 196);
  if ( v75 )
    *(_WORD *)(a1 + 196) = v75 - 1;
  UbpmpDecrementTaskRefAndDelete(&v137);
  UbpmpDecrementTaskRefAndDelete(&v137);
  v137 = 0;
  *a3 = 0;
  if ( !*(_WORD *)(a1 + 196) && (_QWORD *)*v52 == v52 )
    v74 = 1;
  *(_DWORD *)(a1 + 72) = 0;
  RtlReleaseSRWLockExclusive(a1 + 64);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      148,
      WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
      *(unsigned int *)(a1 + 32),
      *(unsigned __int8 *)(a1 + 104));
  if ( v74 == 1 )
    UbpmpSendCommandGetResponse(a1, 0, 0, 1);
LABEL_72:
  v8 = v137;
LABEL_73:
  v59 = a3;
LABEL_74:
  if ( hObject )
    CloseHandle(hObject);
  if ( v7 )
  {
    UBPM_MIDL_user_free(v7[2]);
    UBPM_MIDL_user_free(v7[3]);
    UBPM_MIDL_user_free(v7[1]);
    UBPM_MIDL_user_free(v7);
  }
  if ( v59 && v8 != (_QWORD *)*v59 && v8 )
    UbpmpDecrementTaskRefAndDelete(&v137);
  return LastError;
}

```

## disassembly

```asm
0x18000e660  mov     [rsp-40h+arg_18], r9w
0x18000e666  mov     [rsp-40h+arg_10], r8
0x18000e66b  mov     [rsp-40h+arg_8], rdx
0x18000e670  mov     [rsp-40h+arg_0], rcx
0x18000e675  push    rbp
0x18000e676  push    rbx
0x18000e677  push    rsi
0x18000e678  push    rdi
0x18000e679  push    r12
0x18000e67b  push    r13
0x18000e67d  push    r14
0x18000e67f  push    r15
0x18000e681  mov     rbp, rsp
0x18000e684  sub     rsp, 78h
0x18000e688  lea     rbx, [rcx+40h]
0x18000e68c  movzx   edi, r9w
0x18000e690  mov     rsi, rcx
0x18000e693  mov     [rbp+var_10], rbx
0x18000e697  xor     r13d, r13d
0x18000e69a  xor     r14d, r14d
0x18000e69d  mov     rcx, rbx
0x18000e6a0  mov     [rbp+var_30], r14
0x18000e6a4  mov     r15, rdx
0x18000e6a7  mov     [rbp+hObject], r13
0x18000e6ab  call    cs:__imp_RtlAcquireSRWLockShared
0x18000e6b1  test    byte ptr [rsi+68h], 10h
0x18000e6b5  jz      loc_18000F3FC
0x18000e6bb  xor     edx, edx
0x18000e6bd  xor     r12d, r12d
0x18000e6c0  mov     [rbp+var_18], rdx
0x18000e6c4  mov     ecx, edi
0x18000e6c6  mov     [rbp+var_38], edx
0x18000e6c9  mov     [rbp+var_34], ecx
0x18000e6cc  cmp     edi, 1
0x18000e6cf  jnz     loc_18000ED3C
0x18000e6d5  mov     rcx, rbx
0x18000e6d8  call    cs:__imp_RtlReleaseSRWLockShared
0x18000e6de  test    r12d, r12d
0x18000e6e1  jnz     loc_18000EF63
0x18000e6e7  mov     rcx, gs:60h
0x18000e6f0  mov     edx, 8; Flags
0x18000e6f5  mov     r8d, 40h ; '@'; Size
0x18000e6fb  mov     rcx, [rcx+30h]; HeapHandle
0x18000e6ff  call    cs:__imp_RtlAllocateHeap
0x18000e705  mov     [rbp+var_28], rax
0x18000e709  mov     r13, rax
0x18000e70c  test    rax, rax
0x18000e70f  jz      loc_18000F53B
0x18000e715  cmp     edi, 2
0x18000e718  jnz     loc_18000EA69
0x18000e71e  mov     rcx, gs:60h
0x18000e727  mov     edx, 8; Flags
0x18000e72c  mov     r8d, 0C8h; Size
0x18000e732  mov     rcx, [rcx+30h]; HeapHandle
0x18000e736  call    cs:__imp_RtlAllocateHeap
0x18000e73c  mov     [rbp+var_30], rax
0x18000e740  mov     r14, rax
0x18000e743  test    rax, rax
0x18000e746  jz      loc_18000F598
0x18000e74c  mov     rbx, [rbp+arg_8]
0x18000e750  xor     r12d, r12d
0x18000e753  mov     qword ptr [rax+8], 1
0x18000e75b  mov     esi, 7FFFFFFEh
0x18000e760  mov     r15, [r15+80h]
0x18000e767  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000e76e  movzx   ebx, byte ptr [rbx+78h]
0x18000e772  mov     [rax+0A8h], r12
0x18000e779  test    bl, bl
0x18000e77b  jnz     loc_18000F5EA
0x18000e781  mov     rbx, [rbp+arg_8]
0x18000e785  mov     eax, r12d
0x18000e788  mov     r15, [rbx+0A0h]
0x18000e78f  movzx   ebx, byte ptr [rbx+98h]
0x18000e796  mov     [r14+0B8h], r12
0x18000e79d  test    bl, bl
0x18000e79f  jnz     loc_18000F61A
0x18000e7a5  mov     r12d, eax
0x18000e7a8  test    eax, eax
0x18000e7aa  jnz     loc_18000F364
0x18000e7b0  mov     r15, [rbp+arg_8]
0x18000e7b4  mov     eax, [r15+68h]
0x18000e7b8  mov     [r14+90h], eax
0x18000e7bf  cmp     qword ptr [r15+70h], 0
0x18000e7c4  jnz     loc_18000F024
0x18000e7ca  mov     rcx, [r15+10h]
0x18000e7ce  mov     rax, r13
0x18000e7d1  cmp     word ptr [rcx+rax*2+2], 0
0x18000e7d7  lea     rax, [rax+1]
0x18000e7db  jnz     short loc_18000E7D1
0x18000e7dd  mov     rcx, gs:60h
0x18000e7e6  lea     eax, ds:2[rax*2]
0x18000e7ed  mov     r8d, eax; Size
0x18000e7f0  mov     edx, 8; Flags
0x18000e7f5  mov     ebx, eax
0x18000e7f7  mov     rcx, [rcx+30h]; HeapHandle
0x18000e7fb  call    cs:__imp_RtlAllocateHeap
0x18000e801  mov     rdi, rax
0x18000e804  test    rax, rax
0x18000e807  jz      loc_18000F670
0x18000e80d  shr     rbx, 1
0x18000e810  mov     r8, [rbp+var_30]
0x18000e814  mov     [r8+50h], rax
0x18000e818  jz      short loc_18000E852
0x18000e81a  mov     rdx, [r15+10h]
0x18000e81e  mov     rcx, rsi
0x18000e821  test    rcx, rcx
0x18000e824  jz      short loc_18000E842
0x18000e826  movzx   eax, word ptr [rdx]
0x18000e829  test    ax, ax
0x18000e82c  jz      short loc_18000E842
0x18000e82e  mov     [rdi], ax
0x18000e831  add     rdx, 2
0x18000e835  add     rdi, 2
0x18000e839  dec     rcx
0x18000e83c  sub     rbx, 1
0x18000e840  jnz     short loc_18000E821
0x18000e842  test    rbx, rbx
0x18000e845  lea     rcx, [rdi-2]
0x18000e849  cmovnz  rcx, rdi
0x18000e84d  xor     eax, eax
0x18000e84f  mov     [rcx], ax
0x18000e852  mov     rax, [r15]
0x18000e855  mov     rcx, [rax+8]
0x18000e859  test    rcx, rcx
0x18000e85c  jz      loc_18000E8F4
0x18000e862  mov     rax, r13
0x18000e865  nop     word ptr [rax+rax+00000000h]
0x18000e870  cmp     word ptr [rcx+rax*2+2], 0
0x18000e876  lea     rax, [rax+1]
0x18000e87a  jnz     short loc_18000E870
0x18000e87c  mov     rcx, gs:60h
0x18000e885  lea     eax, ds:2[rax*2]
0x18000e88c  mov     r8d, eax; Size
0x18000e88f  mov     edx, 8; Flags
0x18000e894  mov     edi, eax
0x18000e896  mov     rcx, [rcx+30h]; HeapHandle
0x18000e89a  call    cs:__imp_RtlAllocateHeap
0x18000e8a0  mov     rbx, rax
0x18000e8a3  test    rax, rax
0x18000e8a6  jz      loc_18000F3AF
0x18000e8ac  shr     rdi, 1
0x18000e8af  mov     r8, [rbp+var_30]
0x18000e8b3  mov     [r8+58h], rax
0x18000e8b7  jz      short loc_18000E8F4
0x18000e8b9  mov     rax, [r15]
0x18000e8bc  mov     rcx, rsi
0x18000e8bf  mov     rdx, [rax+8]
0x18000e8c3  test    rcx, rcx
0x18000e8c6  jz      short loc_18000E8E4
0x18000e8c8  movzx   eax, word ptr [rdx]
0x18000e8cb  test    ax, ax
0x18000e8ce  jz      short loc_18000E8E4
0x18000e8d0  mov     [rbx], ax
0x18000e8d3  add     rdx, 2; HINSTANCE
0x18000e8d7  add     rbx, 2
0x18000e8db  dec     rcx
0x18000e8de  sub     rdi, 1
0x18000e8e2  jnz     short loc_18000E8C3
0x18000e8e4  test    rdi, rdi
0x18000e8e7  lea     rcx, [rbx-2]
0x18000e8eb  cmovnz  rcx, rbx
0x18000e8ef  xor     eax, eax
0x18000e8f1  mov     [rcx], ax
0x18000e8f4  test    dword ptr [r15+88h], 200000h
0x18000e8ff  jnz     loc_18000F6C7
0x18000e905  mov     r14d, 1
0x18000e90b  lock xadd cs:?g_dwInstanceId@@3KC, r14d; ulong volatile g_dwInstanceId
0x18000e914  mov     r9, [rbp+arg_0]
0x18000e918  lea     rax, [r8+10h]
0x18000e91c  mov     [rax+8], rax
0x18000e920  inc     r14d
0x18000e923  mov     [rax], rax
0x18000e926  mov     rax, [rbp+var_18]
0x18000e92a  mov     dword ptr [r8], 74484255h
0x18000e931  mov     [r8+30h], r9
0x18000e935  movups  xmm0, xmmword ptr [rax]
0x18000e938  movups  xmmword ptr [r8+20h], xmm0
0x18000e93d  mov     [r8+38h], r14d
0x18000e941  mov     rax, [r15+8]
0x18000e945  movups  xmm0, xmmword ptr [rax]
0x18000e948  movups  xmmword ptr [r8+3Ch], xmm0
0x18000e94d  movzx   eax, word ptr [r15+2Ch]
0x18000e952  mov     [r8+6Ah], ax
0x18000e957  mov     rax, [r15+30h]
0x18000e95b  mov     [r8+80h], rax
0x18000e962  mov     rax, [r15+20h]
0x18000e966  movups  xmm0, xmmword ptr [rax]
0x18000e969  movups  xmmword ptr [r8+6Ch], xmm0
0x18000e96e  mov     eax, [r15+28h]
0x18000e972  mov     [r8+7Ch], eax
0x18000e976  mov     rax, [r15+58h]
0x18000e97a  mov     [r8+88h], rax
0x18000e981  mov     rbx, [r15+60h]
0x18000e985  test    rbx, rbx
0x18000e988  jnz     short loc_18000E995
0x18000e98a  mov     rax, [r15]
0x18000e98d  mov     rcx, [rax+18h]
0x18000e991  mov     rbx, [rcx+10h]
0x18000e995  movzx   eax, byte ptr [r15+78h]
0x18000e99a  mov     [r8+0A0h], al
0x18000e9a1  movzx   eax, byte ptr [r15+98h]
0x18000e9a9  mov     [r8+0B4h], al
0x18000e9b0  mov     eax, [r15+88h]
0x18000e9b7  mov     [r8+0B0h], eax
0x18000e9be  test    rbx, rbx
0x18000e9c1  jnz     loc_18000EC6E
0x18000e9c7  mov     rax, [r15+10h]
0x18000e9cb  test    rax, rax
0x18000e9ce  jz      loc_18000F76A
0x18000e9d4  nop     dword ptr [rax+00h]
0x18000e9d8  nop     dword ptr [rax+rax+00000000h]
0x18000e9e0  cmp     word ptr [rax+r13*2+2], 0
0x18000e9e7  lea     r13, [r13+1]
0x18000e9eb  jnz     short loc_18000E9E0
0x18000e9ed  mov     rcx, gs:60h
0x18000e9f6  lea     eax, ds:2[r13*2]
0x18000e9fe  mov     r8d, eax; Size
0x18000ea01  mov     edx, 8; Flags
0x18000ea06  mov     edi, eax
0x18000ea08  mov     rcx, [rcx+30h]; HeapHandle
0x18000ea0c  call    cs:__imp_RtlAllocateHeap
0x18000ea12  mov     rbx, rax
0x18000ea15  test    rax, rax
0x18000ea18  jz      loc_18000F723
0x18000ea1e  shr     rdi, 1
0x18000ea21  mov     r13, [rbp+var_28]
0x18000ea25  mov     [r13+10h], rax
0x18000ea29  jz      short loc_18000EA61
0x18000ea2b  mov     rcx, [r15+10h]
0x18000ea2f  nop
0x18000ea30  test    rsi, rsi
0x18000ea33  jz      short loc_18000EA51
0x18000ea35  movzx   eax, word ptr [rcx]
0x18000ea38  test    ax, ax
0x18000ea3b  jz      short loc_18000EA51
0x18000ea3d  mov     [rbx], ax
0x18000ea40  add     rcx, 2
0x18000ea44  add     rbx, 2
0x18000ea48  dec     rsi
0x18000ea4b  sub     rdi, 1
0x18000ea4f  jnz     short loc_18000EA30
0x18000ea51  test    rdi, rdi
0x18000ea54  lea     rcx, [rbx-2]
0x18000ea58  cmovnz  rcx, rbx
0x18000ea5c  xor     eax, eax
0x18000ea5e  mov     [rcx], ax
0x18000ea61  movzx   edi, [rbp+arg_18]
0x18000ea65  mov     rsi, [rbp+arg_0]
0x18000ea69  mov     eax, 1
0x18000ea6e  lock xadd cs:?g_ullCommandSequence@@3_JC, rax; __int64 volatile g_ullCommandSequence
0x18000ea77  inc     rax
0x18000ea7a  mov     [r13+0], di
0x18000ea7f  mov     [r13+20h], rax
0x18000ea83  mov     eax, [rbp+var_38]
0x18000ea86  mov     [r13+30h], eax
0x18000ea8a  lea     eax, [rdi-2]
0x18000ea8d  mov     [r13+38h], r14d
0x18000ea91  cmp     ax, 1
0x18000ea95  ja      loc_18000ECE6
0x18000ea9b  mov     rcx, gs:60h
0x18000eaa4  mov     edx, 8; Flags
0x18000eaa9  mov     r8d, 10h; Size
0x18000eaaf  mov     rcx, [rcx+30h]; HeapHandle
0x18000eab3  call    cs:__imp_RtlAllocateHeap
0x18000eab9  mov     rbx, rax
0x18000eabc  test    rax, rax
0x18000eabf  jz      loc_18000EC04
0x18000eac5  mov     [r13+8], rax
0x18000eac9  mov     rax, [rbp+var_18]
0x18000eacd  movups  xmm0, xmmword ptr [rax]
0x18000ead0  movups  xmmword ptr [rbx], xmm0
0x18000ead3  lea     rbx, WPP_GLOBAL_Control
0x18000eada  lea     rcx, [rsi+40h]
0x18000eade  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000eae4  call    cs:__imp_GetCurrentThreadId
0x18000eaea  mov     [rsi+48h], eax
0x18000eaed  movzx   eax, byte ptr [rsi+68h]
0x18000eaf1  test    al, al
0x18000eaf3  js      loc_18000F8D3
0x18000eaf9  test    al, 4
0x18000eafb  jnz     loc_18000F8D3
0x18000eb01  mov     rdi, [rbp+arg_0]
0x18000eb05  xor     r14d, r14d
0x18000eb08  mov     rsi, [rsi+0E0h]
0x18000eb0f  add     rdi, 0D8h
0x18000eb16  cmp     rsi, rdi
0x18000eb19  jnz     loc_18000EE24
0x18000eb1f  cmp     r14d, 2710h
0x18000eb26  jnb     loc_18000F82C
0x18000eb2c  mov     ecx, 20h ; ' '; Size
0x18000eb31  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000eb36  test    rax, rax
0x18000eb39  jz      loc_18000F862
0x18000eb3f  mov     r14, [rbp+var_30]
0x18000eb43  mov     [rax+18h], r14
0x18000eb47  mov     [rax+10h], r13
0x18000eb4b  mov     rcx, [rdi+8]
0x18000eb4f  cmp     [rcx], rdi
0x18000eb52  jnz     loc_18000EFDC
0x18000eb58  mov     [rax], rdi
  ... truncated ...
```
