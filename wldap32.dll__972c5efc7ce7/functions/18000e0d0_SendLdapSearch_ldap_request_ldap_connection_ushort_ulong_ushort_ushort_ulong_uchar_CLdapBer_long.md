# SendLdapSearch(ldap_request *,ldap_connection *,ushort *,ulong,ushort *,ushort * *,ulong,uchar,CLdapBer * *,long)

- ea: `0x18000e0d0`
- end: `0x180010ee7`
- name: `?SendLdapSearch@@YAKPEAUldap_request@@PEAUldap_connection@@PEAGK2PEAPEAGKEPEAPEAVCLdapBer@@J@Z`
- size: `11799`
- prototype: `unsigned int(struct ldap_request *, struct ldap_connection *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 **, unsigned int, unsigned __int8, struct CLdapBer **, int)`
- caller_count: `5`
- callee_count: `18`
- tags: ``

## callers

- `0x180006d80`
- `0x180015640`
- `0x18001af54`
- `0x18002cf6c`
- `0x180045b90`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000b440`
- `0x18000da50`
- `0x18000df44`
- `0x18000e0d0`
- `0x180010ef0`
- `0x180011020`
- `0x180011f50`
- `0x180013610`
- `0x180014060`
- `0x180014460`
- `0x18001ce90`
- `0x18001fb78`
- `0x18002a9f8`
- `0x18002dbac`
- `0x18003d2b8`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f526`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f55c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f526`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f55c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e11b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e1eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ee5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000efa1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f03f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f38c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f934`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f9c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fab8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fb45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e11b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e1eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ee5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000efa1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f03f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f38c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f934`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f9c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fab8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fb45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f264`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ff02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000ff02`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f5e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f5e5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e52a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e5d6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e52a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e5d6`

## string_xrefs

- `0x180010d17`: `LdapAddToPendingList couldn't bump for request 0x%x.\n`
- `0x18000f905`: `LdapAddToPendingList bumping outstanding to 0x%x for 0x%x.\n`
- `0x180010cc4`: `LdapAddToPendingList bumping outstanding to 0x%x for 0x%x.\n`
- `0x18000fc9d`: `ldap_search startWrite connection 0x%x encoding error of 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SendLdapSearch(
        struct ldap_request *a1,
        struct ldap_connection *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int16 *Src,
        unsigned __int16 **a6,
        char a7,
        unsigned __int8 a8,
        struct CLdapBer **a9,
        int a10)
{
  struct ldap_connection *v11; // rbp
  CLdapBer *v13; // rax
  int v14; // ecx
  CLdapBer *v15; // rbx
  unsigned int v16; // eax
  int v18; // ecx
  int v19; // eax
  HANDLE v20; // rcx
  _DWORD *v21; // rax
  _DWORD *v22; // rdi
  unsigned int v23; // eax
  const void *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // ecx
  int v28; // edx
  int v29; // ecx
  int v30; // r10d
  unsigned int v31; // ecx
  int v32; // eax
  char v33; // r12
  unsigned int v34; // eax
  unsigned int v35; // edi
  unsigned int v36; // r9d
  unsigned int v37; // eax
  unsigned int v38; // r8d
  unsigned int v39; // eax
  __int64 v40; // rcx
  unsigned int v41; // r9d
  unsigned int v42; // r8d
  _BYTE *v43; // rdx
  char v44; // r14
  __int64 v45; // r8
  unsigned int v46; // eax
  __int64 v47; // r8
  __int64 v48; // rax
  int v49; // edx
  int v50; // ecx
  int v51; // r9d
  int v52; // eax
  const WCHAR *v53; // r12
  int v54; // edi
  const WCHAR *v55; // rax
  UINT v56; // ecx
  unsigned int v57; // eax
  unsigned int cbMultiByte; // esi
  __int64 v59; // r9
  __int64 v60; // r8
  unsigned int v61; // eax
  __int64 v62; // r8
  unsigned int v63; // eax
  __int64 v64; // rcx
  UINT v65; // ecx
  int v66; // r9d
  int v67; // r11d
  char v68; // r12
  char v69; // r15
  unsigned int v70; // r13d
  unsigned int v71; // eax
  unsigned int v72; // ecx
  unsigned int v73; // edi
  __int64 v74; // r9
  int v75; // r9d
  struct ldap_connection *v76; // rbp
  unsigned int inserted; // edi
  __int64 v78; // r8
  unsigned int v79; // eax
  int v80; // esi
  unsigned int v81; // eax
  unsigned int v82; // ecx
  unsigned int v83; // edi
  unsigned int v84; // r9d
  int v85; // r9d
  __int64 v86; // r8
  unsigned int v87; // eax
  __int64 v88; // rcx
  unsigned int v89; // r8d
  _BYTE *v90; // rdx
  unsigned int v91; // eax
  char v92; // r12
  int v93; // esi
  unsigned int v94; // eax
  unsigned int v95; // ecx
  unsigned int v96; // edi
  __int64 v97; // r9
  int v98; // r9d
  unsigned int v99; // r8d
  unsigned int v100; // eax
  __int64 v101; // rcx
  unsigned int v102; // r8d
  _BYTE *v103; // rdx
  __int64 v104; // r8
  unsigned int v105; // eax
  struct ldap_request *v106; // r12
  int v107; // esi
  unsigned int v108; // edi
  unsigned int v109; // eax
  unsigned int v110; // r12d
  int v111; // eax
  __int64 v112; // r8
  unsigned int v113; // eax
  __int64 v114; // rcx
  unsigned int v115; // r8d
  _BYTE *v116; // rdx
  __int64 v117; // r8
  unsigned int v118; // eax
  unsigned int v119; // eax
  __int64 v120; // rcx
  __int64 v121; // rax
  unsigned int v122; // r8d
  _BYTE *v123; // rdx
  _DWORD *v124; // rsi
  char v125; // di
  unsigned int v126; // eax
  unsigned int v127; // ebp
  unsigned int v128; // ebp
  unsigned int v129; // r15d
  _DWORD *v130; // r14
  const void *v131; // rdx
  unsigned int v132; // ebp
  unsigned int v133; // r15d
  _DWORD *v134; // r14
  const void *v135; // rdx
  unsigned int v136; // ebp
  unsigned int v137; // r15d
  _DWORD *v138; // r14
  const void *v139; // rdx
  unsigned int v140; // ebp
  unsigned int v141; // r15d
  _DWORD *v142; // rax
  _DWORD *v143; // r14
  const void *v144; // rdx
  int v145; // esi
  unsigned int v146; // ebp
  DWORD LastError; // eax
  DWORD v148; // edi
  char v149; // cl
  unsigned __int16 *v150; // rax
  int v151; // ecx
  unsigned int v152; // r15d
  unsigned __int64 v153; // rdi
  unsigned int v154; // r14d
  unsigned int v155; // eax
  __int64 v156; // r8
  __int64 v157; // rax
  int v158; // ecx
  int v159; // edx
  int v160; // esi
  int v161; // ecx
  unsigned int v162; // eax
  ULONG v163; // ecx
  PCHAR v164; // rax
  unsigned int v165; // edx
  _DWORD *Value; // rsi
  int v167; // esi
  char v168; // bp
  __int64 v169; // r8
  unsigned int v170; // eax
  const unsigned __int16 *v171; // rdx
  unsigned int v172; // eax
  __int64 v173; // rax
  unsigned __int16 v174; // cx
  unsigned int v175; // ebp
  _DWORD *v176; // rdi
  const void *v177; // rdx
  unsigned int v178; // r14d
  _DWORD *v179; // rax
  _DWORD *v180; // rsi
  const void *v181; // rdx
  unsigned int v182; // r15d
  _DWORD *v183; // r14
  const void *v184; // rdx
  unsigned int v185; // r14d
  _DWORD *v186; // rdi
  unsigned int v187; // eax
  const void *v188; // rdx
  int v189; // edx
  const char *v190; // rdx
  _DWORD *v191; // rax
  const wchar_t *lpMultiByteStr; // [rsp+20h] [rbp-78h]
  __int16 v193; // [rsp+40h] [rbp-58h] BYREF
  int v194; // [rsp+44h] [rbp-54h]
  int v195; // [rsp+48h] [rbp-50h]
  int v196; // [rsp+4Ch] [rbp-4Ch]
  int v197; // [rsp+50h] [rbp-48h]
  CLdapBer *v198; // [rsp+58h] [rbp-40h]

  v11 = a2;
  if ( *((_DWORD *)a2 + 250) != 2 )
  {
LABEL_2:
    v13 = (CLdapBer *)HeapAlloc(LdapHeap, 8u, 0x370u);
    v14 = g_fTracingOn;
    v15 = v13;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    {
      LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", 880, (_DWORD)v13, 1816347212);
      v14 = g_fTracingOn;
    }
    v16 = LdapAllocatedHeap;
    if ( v15 )
    {
      *(_DWORD *)v15 = 1816347212;
      *((_DWORD *)v15 + 1) = 872;
      v15 = (CLdapBer *)((char *)v15 + 8);
      v16 += 872;
      LdapAllocatedHeap = v16;
    }
    v198 = v15;
    if ( v14 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    {
      LDAPClientPrint(
        8,
        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
        872,
        (_DWORD)v15,
        1816347212,
        v16);
      v14 = g_fTracingOn;
    }
    if ( !v15 )
    {
      if ( v14 && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
        LDAPClientPrint(0x4000, "ldap_search Connection 0x%x couldn't allocate lber.\n", (_DWORD)v11);
      SetConnectionError(v11, 90);
      return 90;
    }
    v18 = *((_DWORD *)v11 + 250);
    *(_QWORD *)v15 = 0;
    v19 = 0;
    *((_DWORD *)v15 + 2) = 0;
    if ( v18 != 2 )
      v19 = 65001;
    *((_QWORD *)v15 + 2) = 0;
    *(_QWORD *)((char *)v15 + 836) = 0;
    *((_QWORD *)v15 + 3) = 0;
    *((_BYTE *)v15 + 856) = 0;
    *((_DWORD *)v15 + 216) = 0;
    *((_DWORD *)v15 + 215) = v19;
    v20 = LdapHeap;
    *((_DWORD *)v15 + 8) = 0;
    v21 = HeapAlloc(v20, 8u, 0x408u);
    v22 = v21;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
        1032,
        (_DWORD)v21,
        1919238732);
    v23 = LdapAllocatedHeap;
    if ( v22 )
    {
      *v22 = 1919238732;
      v22[1] = 1024;
      v22 += 2;
      v23 += 1024;
      LdapAllocatedHeap = v23;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
        1024,
        (_DWORD)v22,
        1919238732,
        v23);
    if ( v22 )
    {
      v24 = (const void *)*((_QWORD *)v15 + 2);
      if ( v24 )
      {
        memcpy_0(v22, v24, *((unsigned int *)v15 + 2));
        ldapFree(*((_QWORD *)v15 + 2), 1919238732);
      }
      v25 = *((unsigned int *)v15 + 1);
      *((_QWORD *)v15 + 2) = v22;
      *((_DWORD *)v15 + 2) = 1024;
      *((_BYTE *)v22 + v25) = 48;
      ++*((_DWORD *)v15 + 1);
      v26 = *((unsigned int *)v15 + 8);
      if ( (unsigned int)v26 >= 0x32 )
      {
        v29 = -2147024882;
      }
      else
      {
        v27 = *((_DWORD *)v15 + 210);
        v28 = *((_DWORD *)v15 + 209);
        *((_DWORD *)v15 + 4 * v26 + 9) = *((_DWORD *)v15 + 1);
        *((_DWORD *)v15 + 4 * *((unsigned int *)v15 + 8) + 10) = 5;
        *((_DWORD *)v15 + 4 * *((unsigned int *)v15 + 8) + 11) = v27;
        v29 = 0;
        *((_DWORD *)v15 + 4 * (unsigned int)(*((_DWORD *)v15 + 8))++ + 12) = v28;
      }
      *((_DWORD *)v15 + 1) += 5;
      *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
      if ( !v29 )
      {
        v30 = 90;
        v194 = 90;
        v196 = -2147024809;
        v31 = 0x80000000;
        if ( !a10 )
        {
          v189 = *((_DWORD *)a1 + 27);
          v195 = 2;
          v41 = CLdapBer::HrAddValue(v15, v189, 2u);
          goto LABEL_40;
        }
        v32 = *((_DWORD *)v15 + 216);
        v195 = 2;
        v33 = 2;
        if ( v32 )
        {
          v33 = v32;
          *((_DWORD *)v15 + 216) = 0;
        }
        v34 = -16777216;
        v35 = 4;
        do
        {
          if ( (v34 & a10) != 0 )
            break;
          v31 >>= 8;
          --v35;
          v34 >>= 8;
        }
        while ( v34 );
        v11 = a2;
        if ( a10 >= 0 && (v31 & a10) != 0 )
          ++v35;
        v36 = v35 + 6;
        if ( v35 + 6 < v35 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
            LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbInt 0x%x\n", v35);
          goto LABEL_39;
        }
        v37 = *(_DWORD *)v15 + v36;
        if ( v37 < *(_DWORD *)v15 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
            LDAPClientPrint(
              0x10000000,
              "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n",
              *(_DWORD *)v15,
              v36);
          goto LABEL_39;
        }
        v38 = *((_DWORD *)v15 + 2);
        if ( v37 <= v38 && v38 )
          goto LABEL_32;
        if ( v36 > 0x400 )
        {
          v140 = v38 + v36;
          if ( v38 + v36 >= v38 )
            goto LABEL_261;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
            LDAPClientPrint(0x10000000, "HrEnsureBuffer: integer overflow. DataMax 0x%x, NeededLength 0x%x\n", v38, v36);
        }
        else
        {
          v140 = v38 + 1024;
          if ( v38 + 1024 >= v38 )
          {
LABEL_261:
            v141 = v140 + 8;
            if ( v140 + 8 < v140 )
            {
              v143 = 0;
              v141 = -1;
            }
            else
            {
              v142 = HeapAlloc(LdapHeap, 8u, v141);
              v30 = v194;
              v143 = v142;
            }
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            {
              LDAPClientPrint(
                8,
                "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                v141,
                (_DWORD)v143,
                1919238732);
              v30 = v194;
            }
            if ( v143 )
            {
              *v143 = 1919238732;
              v143[1] = v140;
              v143 += 2;
              LdapAllocatedHeap += v140;
            }
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            {
              LDAPClientPrint(
                8,
                "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                v140,
                (_DWORD)v143,
                1919238732,
                LdapAllocatedHeap);
              v30 = v194;
            }
            if ( !v143 )
            {
              v11 = a2;
              v41 = v30;
              goto LABEL_40;
            }
            v144 = (const void *)*((_QWORD *)v15 + 2);
            if ( v144 )
            {
              memcpy_0(v143, v144, *((unsigned int *)v15 + 2));
              ldapFree(*((_QWORD *)v15 + 2), 1919238732);
            }
            *((_DWORD *)v15 + 2) = v140;
            v11 = a2;
            *((_QWORD *)v15 + 2) = v143;
LABEL_32:
            *(_BYTE *)(*((unsigned int *)v15 + 1) + *((_QWORD *)v15 + 2)) = v33;
            v39 = *((_DWORD *)v15 + 1) + 1;
            *((_DWORD *)v15 + 1) = v39;
            if ( v35 > 0x7F )
            {
              if ( v35 > 0x7FFF )
              {
                if ( v35 >= 0x7FFFFFFF )
                {
                  v41 = -2147024809;
                  goto LABEL_40;
                }
                *(_BYTE *)(v39 + *((_QWORD *)v15 + 2)) = -124;
                *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = HIBYTE(v35);
                *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE2(v35);
              }
              else
              {
                *(_BYTE *)(v39 + *((_QWORD *)v15 + 2)) = -126;
              }
              *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE1(v35);
              v40 = (unsigned int)++*((_DWORD *)v15 + 1);
            }
            else
            {
              v40 = v39;
            }
            v41 = 0;
            v42 = v35;
            *(_BYTE *)(v40 + *((_QWORD *)v15 + 2)) = v35;
            v43 = (_BYTE *)(*((_QWORD *)v15 + 2) + (unsigned int)++*((_DWORD *)v15 + 1));
            if ( v35 )
            {
              do
                *v43++ = a10 >> (8 * v42-- - 8);
              while ( v42 );
              v11 = a2;
            }
            *((_DWORD *)v15 + 1) += v35;
            *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
LABEL_40:
            if ( v41 )
            {
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                LDAPClientPrint(0x400000, "ldap_search MsgNo connection 0x%x encoding error of 0x%x.\n", v11);
              goto LABEL_486;
            }
            if ( *((_QWORD *)v11 + 120) != -1 && *((_DWORD *)v11 + 250) == 2 )
              CLdapBer::HrAddValue(v15, *((const unsigned __int16 **)v11 + 10), 4u);
            v44 = 99;
            if ( *((_DWORD *)v15 + 216) )
            {
              v44 = *((_DWORD *)v15 + 216);
              *((_DWORD *)v15 + 216) = 0;
            }
            v45 = *(unsigned int *)v15;
            v46 = v45 + 6;
            if ( (int)v45 + 6 < (unsigned int)v45 )
            {
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                LDAPClientPrint(
                  0x10000000,
                  "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n",
                  v45,
                  6);
            }
            else
            {
              v47 = *((unsigned int *)v15 + 2);
              if ( v46 <= (unsigned int)v47 && (_DWORD)v47 )
              {
LABEL_47:
                *(_BYTE *)((unsigned int)(*((_DWORD *)v15 + 1))++ + *((_QWORD *)v15 + 2)) = v44;
                v48 = *((unsigned int *)v15 + 8);
                if ( (unsigned int)v48 >= 0x32 )
                {
                  v51 = -2147024882;
                }
                else
                {
                  v49 = *((_DWORD *)v15 + 209);
                  v50 = *((_DWORD *)v15 + 210);
                  *((_DWORD *)v15 + 4 * v48 + 9) = *((_DWORD *)v15 + 1);
                  *((_DWORD *)v15 + 4 * *((unsigned int *)v15 + 8) + 10) = 5;
                  *((_DWORD *)v15 + 4 * *((unsigned int *)v15 + 8) + 11) = v50;
                  *((_DWORD *)v15 + 4 * (unsigned int)(*((_DWORD *)v15 + 8))++ + 12) = v49;
                  v51 = 0;
                }
                *((_DWORD *)v15 + 1) += 5;
                *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
                goto LABEL_50;
              }
              v145 = v47 + 1024;
              if ( (int)v47 + 1024 >= (unsigned int)v47 )
              {
                v175 = v47 + 1032;
                if ( (int)v47 + 1032 < (unsigned int)(v47 + 1024) )
                {
                  v176 = 0;
                  v175 = -1;
                }
                else
                {
                  v176 = HeapAlloc(LdapHeap, 8u, v175);
                }
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                  LDAPClientPrint(
                    8,
                    "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                    v175,
                    (_DWORD)v176,
                    1919238732);
                if ( v176 )
                {
                  *v176 = 1919238732;
                  v176[1] = v145;
                  v176 += 2;
                  LdapAllocatedHeap += v145;
                }
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                  LDAPClientPrint(
                    8,
                    "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                    v145,
                    (_DWORD)v176,
                    1919238732,
                    LdapAllocatedHeap);
                if ( v176 )
                {
                  v177 = (const void *)*((_QWORD *)v15 + 2);
                  if ( v177 )
                  {
                    memcpy_0(v176, v177, *((unsigned int *)v15 + 2));
                    ldapFree(*((_QWORD *)v15 + 2), 1919238732);
                  }
                  v11 = a2;
                  *((_QWORD *)v15 + 2) = v176;
                  *((_DWORD *)v15 + 2) = v145;
                  goto LABEL_47;
                }
                v51 = v194;
                v11 = a2;
LABEL_50:
                if ( !v51 )
                {
                  v52 = *((_DWORD *)v15 + 216);
                  v197 = 4;
                  v193 = 0;
                  if ( v52 )
                  {
                    v197 = v52;
                    *((_DWORD *)v15 + 216) = 0;
                  }
                  v53 = (const WCHAR *)&v193;
                  v54 = 0;
                  if ( a3 )
                    v53 = a3;
                  v55 = v53;
                  do
                  {
                    if ( !*v55 )
                      break;
                    ++v54;
                    ++v55;
                  }
                  while ( v55 );
                  v56 = *((_DWORD *)v15 + 215);
                  if ( v56 == 65001 )
                    v56 = 65001;
                  v57 = WideCharToMultiByte(v56, 0, v53, v54, 0, 0, 0, 0);
                  cbMultiByte = v57;
                  if ( !v57 && v54 )
                  {
                    LastError = GetLastError();
                    v148 = LastError;
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
                      LDAPClientPrint(
                        0x2000,
                        "HrAddValue received error of 0x%x from WideCharToMultiByte.\n",
                        LastError);
                    if ( v148 == 122 )
                      goto LABEL_300;
LABEL_213:
                    v66 = 82;
                    goto LABEL_72;
                  }
                  v59 = v57 + 6;
                  if ( (unsigned int)v59 < v57 )
                  {
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                      LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbValue 0x%x\n", v57);
                    v66 = 82;
                    goto LABEL_96;
                  }
                  v60 = *(unsigned int *)v15;
                  v61 = v60 + v59;
                  if ( (int)v60 + (int)v59 < (unsigned int)v60 )
                  {
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                      LDAPClientPrint(
                        0x10000000,
                        "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n",
                        v60,
                        v59);
                    goto LABEL_213;
                  }
                  v62 = *((unsigned int *)v15 + 2);
                  if ( v61 > (unsigned int)v62 || !(_DWORD)v62 )
                  {
                    if ( (unsigned int)v59 > 0x400 )
                    {
                      v146 = v62 + v59;
                      if ( (int)v62 + (int)v59 < (unsigned int)v62 )
                      {
                        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                          LDAPClientPrint(
                            0x10000000,
                            "HrEnsureBuffer: integer overflow. DataMax 0x%x, NeededLength 0x%x\n",
                            v62,
                            v59);
                        goto LABEL_213;
                      }
                    }
                    else
                    {
                      v146 = v62 + 1024;
                      if ( (int)v62 + 1024 < (unsigned int)v62 )
                      {
                        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                          LDAPClientPrint(
                            0x10000000,
                            "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n",
                            v62,
                            1024);
                        goto LABEL_213;
                      }
                    }
                    v182 = v146 + 8;
                    if ( v146 + 8 < v146 )
                    {
                      v183 = 0;
                      v182 = -1;
                    }
                    else
                    {
                      v183 = HeapAlloc(LdapHeap, 8u, v182);
                    }
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                      LDAPClientPrint(
                        8,
                        "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                        v182,
                        (_DWORD)v183,
                        1919238732);
                    if ( v183 )
                    {
                      *v183 = 1919238732;
                      v183[1] = v146;
                      v183 += 2;
                      LdapAllocatedHeap += v146;
                    }
                    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                      LDAPClientPrint(
                        8,
                        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                        v146,
                        (_DWORD)v183,
                        1919238732,
                        LdapAllocatedHeap);
                    if ( !v183 )
                    {
                      v66 = v194;
                      goto LABEL_72;
                    }
                    v184 = (const void *)*((_QWORD *)v15 + 2);
                    if ( v184 )
                    {
                      memcpy_0(v183, v184, *((unsigned int *)v15 + 2));
                      ldapFree(*((_QWORD *)v15 + 2), 1919238732);
                    }
                    *((_DWORD *)v15 + 2) = v146;
                    *((_QWORD *)v15 + 2) = v183;
                  }
                  *(_BYTE *)(*((unsigned int *)v15 + 1) + *((_QWORD *)v15 + 2)) = v197;
                  v63 = *((_DWORD *)v15 + 1) + 1;
                  *((_DWORD *)v15 + 1) = v63;
                  if ( cbMultiByte > 0x7F )
                  {
                    if ( cbMultiByte > 0x7FFF )
                    {
                      if ( cbMultiByte >= 0x7FFFFFFF )
                      {
LABEL_300:
                        v66 = -2147024809;
                        goto LABEL_72;
                      }
                      *(_BYTE *)(v63 + *((_QWORD *)v15 + 2)) = -124;
                      *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = HIBYTE(cbMultiByte);
                      *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE2(cbMultiByte);
                    }
                    else
                    {
                      *(_BYTE *)(v63 + *((_QWORD *)v15 + 2)) = -126;
                    }
                    *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE1(cbMultiByte);
                    v64 = (unsigned int)++*((_DWORD *)v15 + 1);
                  }
                  else
                  {
                    v64 = v63;
                  }
                  *(_BYTE *)(v64 + *((_QWORD *)v15 + 2)) = cbMultiByte;
                  ++*((_DWORD *)v15 + 1);
                  if ( v54 )
                  {
                    v65 = *((_DWORD *)v15 + 215);
                    if ( v65 == 65001 )
                      v65 = 65001;
                    cbMultiByte = WideCharToMultiByte(
                                    v65,
                                    0,
                                    v53,
                                    v54,
                                    (LPSTR)(*((_QWORD *)v15 + 2) + *((unsigned int *)v15 + 1)),
                                    cbMultiByte,
                                    0,
                                    0);
                  }
                  *((_DWORD *)v15 + 1) += cbMultiByte;
                  v66 = 0;
                  *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
LABEL_72:
                  if ( !v66 )
                  {
                    v67 = a4;
                    if ( (unsigned int)a4 >= 3 )
                    {
                      if ( g_fTracingOn && g_fProviderEnabled )
                      {
                        v76 = a2;
                        if ( (g_ulTraceFlags & 0x400000) != 0 )
                          LDAPClientPrint(
                            0x400000,
                            "ldap_search connection 0x%x invalid scope of 0x%x.\n",
                            (_DWORD)a2,
                            a4);
                      }
                      else
                      {
                        v76 = a2;
                      }
                      inserted = 89;
                      goto LABEL_337;
                    }
                    v68 = 10;
                    v69 = 10;
                    if ( *((_DWORD *)v15 + 216) )
                    {
                      v69 = *((_DWORD *)v15 + 216);
                      *((_DWORD *)v15 + 216) = 0;
                    }
                    v70 = 7;
                    if ( a4 )
                    {
                      v71 = -16777216;
                      v72 = 0x80000000;
                      v73 = 4;
                      do
                      {
                        if ( (v71 & a4) != 0 )
                          break;
                        v72 >>= 8;
                        --v73;
                        v71 >>= 8;
                      }
                      while ( v71 );
                      if ( a4 >= 0 && (v72 & a4) != 0 )
                        ++v73;
                      v74 = v73 + 6;
                      if ( (unsigned int)v74 < v73 )
                      {
                        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                          LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbInt 0x%x\n", v73);
                        v75 = 82;
                        goto LABEL_87;
                      }
                    }
                    else
                    {
                      v73 = 1;
                      v74 = 7;
                    }
                    v78 = *(unsigned int *)v15;
                    v79 = v78 + v74;
                    if ( (int)v78 + (int)v74 < (unsigned int)v78 )
                    {
                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                        LDAPClientPrint(
                          0x10000000,
                          "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n",
                          v78,
                          v74);
LABEL_103:
                      v75 = 82;
                      goto LABEL_104;
                    }
                    v86 = *((unsigned int *)v15 + 2);
                    if ( v79 > (unsigned int)v86 || !(_DWORD)v86 )
                    {
                      if ( (unsigned int)v74 > 0x400 )
                      {
                        v127 = v86 + v74;
                        if ( (int)v86 + (int)v74 < (unsigned int)v86 )
                        {
                          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                            LDAPClientPrint(
                              0x10000000,
                              "HrEnsureBuffer: integer overflow. DataMax 0x%x, NeededLength 0x%x\n",
                              v86,
                              v74);
                          goto LABEL_103;
                        }
                      }
                      else
                      {
                        v127 = v86 + 1024;
                        if ( (int)v86 + 1024 < (unsigned int)v86 )
                        {
                          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                            LDAPClientPrint(
                              0x10000000,
                              "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n",
                              v86,
                              1024);
                          goto LABEL_103;
                        }
                      }
                      v178 = v127 + 8;
                      if ( v127 + 8 < v127 )
                      {
                        v180 = 0;
                        v178 = -1;
                      }
                      else
                      {
                        v179 = HeapAlloc(LdapHeap, 8u, v178);
                        v67 = a4;
                        v180 = v179;
                      }
                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                      {
                        LDAPClientPrint(
                          8,
                          "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                          v178,
                          (_DWORD)v180,
                          1919238732);
                        v67 = a4;
                      }
                      if ( v180 )
                      {
                        *v180 = 1919238732;
                        v180[1] = v127;
                        v180 += 2;
                        LdapAllocatedHeap += v127;
                      }
                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                      {
                        LDAPClientPrint(
                          8,
                          "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                          v127,
                          (_DWORD)v180,
                          1919238732,
                          LdapAllocatedHeap);
                        v67 = a4;
                      }
                      if ( !v180 )
                      {
                        v75 = v194;
                        goto LABEL_104;
                      }
                      v181 = (const void *)*((_QWORD *)v15 + 2);
                      if ( v181 )
                      {
                        memcpy_0(v180, v181, *((unsigned int *)v15 + 2));
                        ldapFree(*((_QWORD *)v15 + 2), 1919238732);
                        v67 = a4;
                      }
                      *((_QWORD *)v15 + 2) = v180;
                      *((_DWORD *)v15 + 2) = v127;
                    }
                    *(_BYTE *)(*((unsigned int *)v15 + 1) + *((_QWORD *)v15 + 2)) = v69;
                    v87 = *((_DWORD *)v15 + 1) + 1;
                    *((_DWORD *)v15 + 1) = v87;
                    if ( v73 > 0x7F )
                    {
                      if ( v73 > 0x7FFF )
                      {
                        if ( v73 >= 0x7FFFFFFF )
                        {
                          v75 = -2147024809;
                          goto LABEL_104;
                        }
                        *(_BYTE *)(v87 + *((_QWORD *)v15 + 2)) = -124;
                        *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = HIBYTE(v73);
                        *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE2(v73);
                      }
                      else
                      {
                        *(_BYTE *)(v87 + *((_QWORD *)v15 + 2)) = -126;
                      }
                      *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE1(v73);
                      v88 = (unsigned int)++*((_DWORD *)v15 + 1);
                    }
                    else
                    {
                      v88 = v87;
                    }
                    v75 = 0;
                    v89 = v73;
                    *(_BYTE *)(v88 + *((_QWORD *)v15 + 2)) = v73;
                    v90 = (_BYTE *)(*((_QWORD *)v15 + 2) + (unsigned int)++*((_DWORD *)v15 + 1));
                    if ( v73 )
                    {
                      do
                        *v90++ = v67 >> (8 * v73-- - 8);
                      while ( v73 );
                      v75 = 0;
                    }
                    *((_DWORD *)v15 + 1) += v89;
                    *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
LABEL_104:
                    if ( v75 )
                    {
LABEL_87:
                      v76 = a2;
                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                        LDAPClientPrint(
                          0x400000,
                          "ldap_search scope connection 0x%x encoding error of 0x%x.\n",
                          (_DWORD)a2,
                          v75);
                      goto LABEL_88;
                    }
                    v76 = a2;
                    v80 = *((_DWORD *)a2 + 252);
                    if ( (unsigned int)v80 >= 4 )
                    {
                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                        LDAPClientPrint(
                          0x400000,
                          "ldap_search connection 0x%x invalid derefOption of 0x%x.\n",
                          (_DWORD)a2,
                          v80);
                      inserted = 89;
                      goto LABEL_337;
                    }
                    if ( *((_DWORD *)v15 + 216) )
                    {
                      v68 = *((_DWORD *)v15 + 216);
                      *((_DWORD *)v15 + 216) = 0;
                    }
                    if ( v80 )
                    {
                      v81 = -16777216;
                      v82 = 0x80000000;
                      v83 = 4;
                      do
                      {
                        if ( (v81 & v80) != 0 )
                          break;
                        v82 >>= 8;
                        --v83;
                        v81 >>= 8;
                      }
                      while ( v81 );
                      v76 = a2;
                      if ( (v82 & v80) != 0 )
                        ++v83;
                      v84 = v83 + 6;
                      if ( v83 + 6 < v83 )
                      {
                        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                          LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbInt 0x%x\n", v83);
                        v85 = 82;
LABEL_119:
                        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                        {
                          LDAPClientPrint(
                            0x400000,
                            "ldap_search derefOption connection 0x%x encoding error of 0x%x.\n",
                            (_DWORD)v76,
                            v85);
                          inserted = 83;
                          goto LABEL_337;
                        }
LABEL_88:
                        inserted = 83;
                        goto LABEL_337;
                      }
                    }
                    else
                    {
                      v83 = 1;
                      v84 = 7;
                    }
                    v91 = *(_DWORD *)v15 + v84;
                    if ( v91 < *(_DWORD *)v15 )
                    {
                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                        LDAPClientPrint(
                          0x10000000,
                          "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n",
                          *(_DWORD *)v15,
                          v84);
                      goto LABEL_134;
                    }
                    v99 = *((_DWORD *)v15 + 2);
                    if ( v91 <= v99 && v99 )
                      goto LABEL_155;
                    if ( v84 > 0x400 )
                    {
                      v128 = v99 + v84;
                      if ( v99 + v84 >= v99 )
                        goto LABEL_225;
                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                        LDAPClientPrint(
                          0x10000000,
                          "HrEnsureBuffer: integer overflow. DataMax 0x%x, NeededLength 0x%x\n",
                          v99,
                          v84);
                    }
                    else
                    {
                      v128 = v99 + 1024;
                      if ( v99 + 1024 >= v99 )
                      {
LABEL_225:
                        v129 = v128 + 8;
                        if ( v128 + 8 < v128 )
                        {
                          v130 = 0;
                          v129 = -1;
                        }
                        else
                        {
                          v130 = HeapAlloc(LdapHeap, 8u, v129);
                        }
                        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                          LDAPClientPrint(
                            8,
                            "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                            v129,
                            (_DWORD)v130,
                            1919238732);
                        if ( v130 )
                        {
                          *v130 = 1919238732;
                          v130[1] = v128;
                          v130 += 2;
                          LdapAllocatedHeap += v128;
                        }
                        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                          LDAPClientPrint(
                            8,
                            "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                            v128,
                            (_DWORD)v130,
                            1919238732,
                            LdapAllocatedHeap);
                        if ( !v130 )
                        {
                          v85 = v194;
                          v76 = a2;
                          goto LABEL_135;
                        }
                        v131 = (const void *)*((_QWORD *)v15 + 2);
                        if ( v131 )
                        {
                          memcpy_0(v130, v131, *((unsigned int *)v15 + 2));
                          ldapFree(*((_QWORD *)v15 + 2), 1919238732);
                        }
                        *((_DWORD *)v15 + 2) = v128;
                        v76 = a2;
                        *((_QWORD *)v15 + 2) = v130;
LABEL_155:
                        *(_BYTE *)(*((unsigned int *)v15 + 1) + *((_QWORD *)v15 + 2)) = v68;
                        v100 = *((_DWORD *)v15 + 1) + 1;
                        *((_DWORD *)v15 + 1) = v100;
                        if ( v83 > 0x7F )
                        {
                          if ( v83 > 0x7FFF )
                          {
                            if ( v83 >= 0x7FFFFFFF )
                            {
                              v85 = -2147024809;
                              goto LABEL_135;
                            }
                            *(_BYTE *)(v100 + *((_QWORD *)v15 + 2)) = -124;
                            *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = HIBYTE(v83);
                            *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE2(v83);
                          }
                          else
                          {
                            *(_BYTE *)(v100 + *((_QWORD *)v15 + 2)) = -126;
                          }
                          *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE1(v83);
                          v101 = (unsigned int)++*((_DWORD *)v15 + 1);
                        }
                        else
                        {
                          v101 = v100;
                        }
                        v85 = 0;
                        v102 = v83;
                        *(_BYTE *)(v101 + *((_QWORD *)v15 + 2)) = v83;
                        v103 = (_BYTE *)(*((_QWORD *)v15 + 2) + (unsigned int)++*((_DWORD *)v15 + 1));
                        if ( v83 )
                        {
                          do
                            *v103++ = v80 >> (8 * v83-- - 8);
                          while ( v83 );
                          v76 = a2;
                        }
                        *((_DWORD *)v15 + 1) += v102;
                        *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
LABEL_135:
                        if ( v85 )
                          goto LABEL_119;
                        v92 = 2;
                        v93 = *((_DWORD *)a1 + 25);
                        if ( *((_DWORD *)v15 + 216) )
                        {
                          v92 = *((_DWORD *)v15 + 216);
                          *((_DWORD *)v15 + 216) = 0;
                        }
                        if ( v93 )
                        {
                          v94 = -16777216;
                          v95 = 0x80000000;
                          v96 = 4;
                          do
                          {
                            if ( (v93 & v94) != 0 )
                              break;
                            v95 >>= 8;
                            --v96;
                            v94 >>= 8;
                          }
                          while ( v94 );
                          v15 = v198;
                          if ( v93 >= 0 && (v93 & v95) != 0 )
                            ++v96;
                          v97 = v96 + 6;
                          if ( (unsigned int)v97 < v96 )
                          {
                            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                              LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbInt 0x%x\n", v96);
                            v98 = 82;
                            goto LABEL_149;
                          }
                        }
                        else
                        {
                          v96 = 1;
                          v97 = 7;
                        }
                        v104 = *(unsigned int *)v15;
                        v105 = v104 + v97;
                        if ( (int)v104 + (int)v97 < (unsigned int)v104 )
                        {
                          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                            LDAPClientPrint(
                              0x10000000,
                              "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n",
                              v104,
                              v97);
LABEL_164:
                          v98 = 82;
                          goto LABEL_165;
                        }
                        v112 = *((unsigned int *)v15 + 2);
                        if ( v105 > (unsigned int)v112 || !(_DWORD)v112 )
                        {
                          if ( (unsigned int)v97 > 0x400 )
                          {
                            v132 = v112 + v97;
                            if ( (int)v112 + (int)v97 < (unsigned int)v112 )
                            {
                              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                                LDAPClientPrint(
                                  0x10000000,
                                  "HrEnsureBuffer: integer overflow. DataMax 0x%x, NeededLength 0x%x\n",
                                  v112,
                                  v97);
                              goto LABEL_164;
                            }
                          }
                          else
                          {
                            v132 = v112 + 1024;
                            if ( (int)v112 + 1024 < (unsigned int)v112 )
                            {
                              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                                LDAPClientPrint(
                                  0x10000000,
                                  "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n",
                                  v112,
                                  1024);
                              goto LABEL_164;
                            }
                          }
                          v133 = v132 + 8;
                          if ( v132 + 8 < v132 )
                          {
                            v134 = 0;
                            v133 = -1;
                          }
                          else
                          {
                            v134 = HeapAlloc(LdapHeap, 8u, v133);
                          }
                          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                            LDAPClientPrint(
                              8,
                              "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                              v133,
                              (_DWORD)v134,
                              1919238732);
                          if ( v134 )
                          {
                            *v134 = 1919238732;
                            v134[1] = v132;
                            v134 += 2;
                            LdapAllocatedHeap += v132;
                          }
                          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                            LDAPClientPrint(
                              8,
                              "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                              v132,
                              (_DWORD)v134,
                              1919238732,
                              LdapAllocatedHeap);
                          if ( !v134 )
                          {
                            v98 = v194;
                            goto LABEL_165;
                          }
                          v135 = (const void *)*((_QWORD *)v15 + 2);
                          if ( v135 )
                          {
                            memcpy_0(v134, v135, *((unsigned int *)v15 + 2));
                            ldapFree(*((_QWORD *)v15 + 2), 1919238732);
                          }
                          *((_QWORD *)v15 + 2) = v134;
                          *((_DWORD *)v15 + 2) = v132;
                        }
                        *(_BYTE *)(*((unsigned int *)v15 + 1) + *((_QWORD *)v15 + 2)) = v92;
                        v113 = *((_DWORD *)v15 + 1) + 1;
                        *((_DWORD *)v15 + 1) = v113;
                        if ( v96 > 0x7F )
                        {
                          if ( v96 > 0x7FFF )
                          {
                            if ( v96 >= 0x7FFFFFFF )
                            {
                              v98 = -2147024809;
                              goto LABEL_165;
                            }
                            *(_BYTE *)(v113 + *((_QWORD *)v15 + 2)) = -124;
                            *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = HIBYTE(v96);
                            *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE2(v96);
                          }
                          else
                          {
                            *(_BYTE *)(v113 + *((_QWORD *)v15 + 2)) = -126;
                          }
                          *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE1(v96);
                          v114 = (unsigned int)++*((_DWORD *)v15 + 1);
                        }
                        else
                        {
                          v114 = v113;
                        }
                        v98 = 0;
                        v115 = v96;
                        *(_BYTE *)(v114 + *((_QWORD *)v15 + 2)) = v96;
                        v116 = (_BYTE *)(*((_QWORD *)v15 + 2) + (unsigned int)++*((_DWORD *)v15 + 1));
                        if ( v96 )
                        {
                          do
                            *v116++ = v93 >> (8 * v96-- - 8);
                          while ( v96 );
                          v98 = 0;
                        }
                        *((_DWORD *)v15 + 1) += v115;
                        *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
LABEL_165:
                        if ( v98 )
                        {
LABEL_149:
                          v76 = a2;
                          if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
                            goto LABEL_88;
                          LDAPClientPrint(
                            0x400000,
                            "ldap_search size connection 0x%x encoding error of 0x%x.\n",
                            (_DWORD)a2,
                            v98);
                          inserted = 83;
LABEL_337:
                          if ( GlobalTlsLastErrorIndex != -1 )
                          {
                            Value = TlsGetValue(GlobalTlsLastErrorIndex);
                            if ( !Value )
                            {
                              v191 = (_DWORD *)ldapMalloc(16, 1817471076);
                              Value = v191;
                              if ( !v191 )
                                goto LABEL_338;
                              TlsSetValue(GlobalTlsLastErrorIndex, v191);
                            }
                            *Value = inserted;
                          }
LABEL_338:
                          *((_DWORD *)v76 + 255) = inserted;
                          if ( inserted > 0x61 )
                          {
                            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
                              LDAPClientPrint(
                                0x8000000,
                                "ldap SetConnectionError does not have text for message 0x%x.\n",
                                inserted);
                            v163 = 80;
                          }
                          else
                          {
                            v163 = inserted;
                          }
                          v164 = ldap_err2string(v163);
                          *((_QWORD *)v76 + 129) = v164;
                          *((_QWORD *)v76 + 128) = 0;
                          if ( !*v164 )
                          {
                            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
                              LDAPClientPrint(
                                0x8000000,
                                "ldap SetConnectionError does not have text for message 0x%x.\n",
                                inserted);
                            *((_QWORD *)v76 + 129) = ldap_err2string(0x50u);
                          }
                          if ( v15 )
                            CLdapBer::`scalar deleting destructor'(v15, v165);
                          return inserted;
                        }
                        v106 = a1;
                        v107 = *((_DWORD *)a1 + 24);
                        if ( *((_DWORD *)v15 + 216) )
                        {
                          v195 = *((_DWORD *)v15 + 216);
                          *((_DWORD *)v15 + 216) = 0;
                        }
                        if ( v107 )
                        {
                          v108 = 4;
                          v109 = -16777216;
                          v110 = 0x80000000;
                          do
                          {
                            if ( (v109 & v107) != 0 )
                              break;
                            v110 >>= 8;
                            --v108;
                            v109 >>= 8;
                          }
                          while ( v109 );
                          v15 = v198;
                          v197 = v110;
                          v106 = a1;
                          if ( v107 >= 0 && (v107 & v197) != 0 )
                            ++v108;
                          v70 = v108 + 6;
                          if ( v108 + 6 < v108 )
                          {
                            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                              LDAPClientPrint(0x10000000, "HrAddValue: integer overflow. cbInt 0x%x\n", v108);
                            v111 = 82;
LABEL_179:
                            if ( g_fTracingOn && g_fProviderEnabled )
                            {
                              v76 = a2;
                              if ( (g_ulTraceFlags & 0x400000) != 0 )
                                LDAPClientPrint(
                                  0x400000,
                                  "ldap_search time connection 0x%x encoding error of 0x%x.\n",
                                  (_DWORD)a2,
                                  v111);
                              goto LABEL_678;
                            }
LABEL_677:
                            v76 = a2;
LABEL_678:
                            inserted = 83;
                            goto LABEL_337;
                          }
                        }
                        else
                        {
                          v108 = 1;
                        }
                        v117 = *(unsigned int *)v15;
                        v118 = v117 + v70;
                        if ( (unsigned int)v117 + v70 < (unsigned int)v117 )
                        {
                          if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x10000000) == 0 )
                            goto LABEL_211;
                          v190 = "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n";
                        }
                        else
                        {
                          v117 = *((unsigned int *)v15 + 2);
                          if ( v118 <= (unsigned int)v117 && (_DWORD)v117 )
                            goto LABEL_195;
                          if ( v70 <= 0x400 )
                          {
                            v136 = v117 + 1024;
                            if ( (int)v117 + 1024 >= (unsigned int)v117 )
                            {
LABEL_249:
                              v137 = v136 + 8;
                              if ( v136 + 8 < v136 )
                              {
                                v138 = 0;
                                v137 = -1;
                              }
                              else
                              {
                                v138 = HeapAlloc(LdapHeap, 8u, v137);
                              }
                              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                                LDAPClientPrint(
                                  8,
                                  "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                                  v137,
                                  (_DWORD)v138,
                                  1919238732);
                              if ( v138 )
                              {
                                *v138 = 1919238732;
                                v138[1] = v136;
                                v138 += 2;
                                LdapAllocatedHeap += v136;
                              }
                              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                                LDAPClientPrint(
                                  8,
                                  "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                                  v136,
                                  (_DWORD)v138,
                                  1919238732,
                                  LdapAllocatedHeap);
                              if ( !v138 )
                              {
                                v111 = v194;
                                goto LABEL_202;
                              }
                              v139 = (const void *)*((_QWORD *)v15 + 2);
                              if ( v139 )
                              {
                                memcpy_0(v138, v139, *((unsigned int *)v15 + 2));
                                ldapFree(*((_QWORD *)v15 + 2), 1919238732);
                              }
                              *((_QWORD *)v15 + 2) = v138;
                              *((_DWORD *)v15 + 2) = v136;
LABEL_195:
                              *(_BYTE *)(*((unsigned int *)v15 + 1) + *((_QWORD *)v15 + 2)) = v195;
                              v119 = *((_DWORD *)v15 + 1) + 1;
                              *((_DWORD *)v15 + 1) = v119;
                              if ( v108 > 0x7F )
                              {
                                if ( v108 > 0x7FFF )
                                {
                                  if ( v108 >= 0x7FFFFFFF )
                                  {
LABEL_201:
                                    v111 = v196;
LABEL_202:
                                    if ( v111 )
                                      goto LABEL_179;
                                    v124 = 0;
                                    if ( *((_DWORD *)v15 + 216) )
                                    {
                                      v125 = *((_DWORD *)v15 + 216);
                                      *((_DWORD *)v15 + 216) = 0;
                                    }
                                    else
                                    {
                                      v125 = 1;
                                    }
                                    v126 = CLdapBer::HrEnsureBuffer(v15, 3u, 0);
                                    if ( v126 )
                                    {
                                      if ( g_fTracingOn && g_fProviderEnabled )
                                      {
                                        v76 = a2;
                                        if ( (g_ulTraceFlags & 0x400000) != 0 )
                                          LDAPClientPrint(
                                            0x400000,
                                            "ldap_search attributesOnly connection 0x%x encoding error of 0x%x.\n",
                                            (_DWORD)a2,
                                            v126);
                                        goto LABEL_678;
                                      }
                                      goto LABEL_677;
                                    }
                                    *(_BYTE *)((unsigned int)(*((_DWORD *)v15 + 1))++ + *((_QWORD *)v15 + 2)) = v125;
                                    *(_BYTE *)(*((unsigned int *)v15 + 1) + *((_QWORD *)v15 + 2)) = 1;
                                    v149 = -1;
                                    ++*((_DWORD *)v15 + 1);
                                    if ( a7 != 1 )
                                      v149 = 0;
                                    *(_BYTE *)((unsigned int)(*((_DWORD *)v15 + 1))++ + *((_QWORD *)v15 + 2)) = v149;
                                    *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
                                    if ( !Src )
                                      goto LABEL_305;
                                    v150 = Src;
                                    v151 = 0;
                                    do
                                    {
                                      if ( !*v150 )
                                        break;
                                      ++v151;
                                      ++v150;
                                    }
                                    while ( v150 );
                                    v152 = v151 + 1;
                                    if ( v151 )
                                    {
                                      v153 = 2LL * v152;
                                      if ( v153 > 0xFFFFFFFF )
                                      {
                                        inserted = v194;
                                        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
                                          LDAPClientPrint(
                                            0x40000,
                                            "ldap_search : integer overflow for filter with remaining size 0x%x.\n",
                                            v152);
                                        goto LABEL_323;
                                      }
                                      v154 = v153 + 8;
                                      if ( (int)v153 + 8 < (unsigned int)v153 )
                                        v154 = -1;
                                      else
                                        v124 = HeapAlloc(LdapHeap, 8u, v154);
                                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                                        LDAPClientPrint(
                                          8,
                                          "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                                          v154,
                                          (_DWORD)v124,
                                          1920226124);
                                      v155 = LdapAllocatedHeap;
                                      if ( v124 )
                                      {
                                        *v124 = 1920226124;
                                        v124[1] = v153;
                                        v124 += 2;
                                        v155 += v153;
                                        LdapAllocatedHeap = v155;
                                      }
                                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                                        LDAPClientPrint(
                                          8,
                                          "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                                          v153,
                                          (_DWORD)v124,
                                          1920226124,
                                          v155);
                                      if ( !v124 )
                                      {
                                        inserted = v194;
                                        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x40000) != 0 )
                                          LDAPClientPrint(
                                            0x40000,
                                            "ldap_search : could not allocate memory 0x%x.\n",
                                            v152);
                                        goto LABEL_323;
                                      }
                                      memcpy_0(v124, Src, 2LL * v152);
                                      inserted = LdapEncodeFilter(v15, (unsigned __int16 *)v124, 0);
                                      ldapFree(v124, 1920226124);
                                      if ( !inserted )
                                      {
                                        v168 = 48;
                                        if ( *((_DWORD *)v15 + 216) )
                                        {
                                          v168 = *((_DWORD *)v15 + 216);
                                          *((_DWORD *)v15 + 216) = 0;
                                        }
                                        v169 = *(unsigned int *)v15;
                                        v170 = v169 + 6;
                                        if ( (int)v169 + 6 < (unsigned int)v169 )
                                        {
                                          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                                            LDAPClientPrint(
                                              0x10000000,
                                              "HrEnsureBuffer: integer overflow. DataLength 0x%x, NeededLength 0x%x\n",
                                              v169,
                                              6);
LABEL_357:
                                          v160 = 0;
                                          v161 = 82;
                                          goto LABEL_329;
                                        }
                                        v156 = *((unsigned int *)v15 + 2);
                                        if ( v170 > (unsigned int)v156 || !(_DWORD)v156 )
                                        {
                                          v167 = v156 + 1024;
                                          if ( (int)v156 + 1024 < (unsigned int)v156 )
                                          {
                                            if ( g_fTracingOn
                                              && g_fProviderEnabled
                                              && (g_ulTraceFlags & 0x10000000) != 0 )
                                            {
                                              LDAPClientPrint(
                                                0x10000000,
                                                "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n",
                                                v156,
                                                1024);
                                            }
                                            goto LABEL_357;
                                          }
                                          v185 = v156 + 1032;
                                          if ( (int)v156 + 1032 < (unsigned int)(v156 + 1024) )
                                          {
                                            v186 = 0;
                                            v185 = -1;
                                          }
                                          else
                                          {
                                            v186 = HeapAlloc(LdapHeap, 8u, v185);
                                          }
                                          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                                            LDAPClientPrint(
                                              8,
                                              "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                                              v185,
                                              (_DWORD)v186,
                                              1919238732);
                                          v187 = LdapAllocatedHeap;
                                          if ( v186 )
                                          {
                                            *v186 = 1919238732;
                                            v186[1] = v167;
                                            v186 += 2;
                                            v187 += v167;
                                            LdapAllocatedHeap = v187;
                                          }
                                          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                                            LDAPClientPrint(
                                              8,
                                              "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                                              v167,
                                              (_DWORD)v186,
                                              1919238732,
                                              v187);
                                          if ( !v186 )
                                          {
                                            v160 = 0;
                                            v161 = v194;
                                            goto LABEL_329;
                                          }
                                          v188 = (const void *)*((_QWORD *)v15 + 2);
                                          if ( v188 )
                                          {
                                            memcpy_0(v186, v188, *((unsigned int *)v15 + 2));
                                            ldapFree(*((_QWORD *)v15 + 2), 1919238732);
                                          }
                                          *((_QWORD *)v15 + 2) = v186;
                                          *((_DWORD *)v15 + 2) = v167;
                                        }
                                        *(_BYTE *)((unsigned int)(*((_DWORD *)v15 + 1))++ + *((_QWORD *)v15 + 2)) = v168;
                                        v157 = *((unsigned int *)v15 + 8);
                                        if ( (unsigned int)v157 >= 0x32 )
                                        {
                                          v161 = -2147024882;
                                          v160 = 0;
                                        }
                                        else
                                        {
                                          v158 = *((_DWORD *)v15 + 210);
                                          v159 = *((_DWORD *)v15 + 209);
                                          *((_DWORD *)v15 + 4 * v157 + 9) = *((_DWORD *)v15 + 1);
                                          *((_DWORD *)v15 + 4 * *((unsigned int *)v15 + 8) + 10) = 5;
                                          *((_DWORD *)v15 + 4 * *((unsigned int *)v15 + 8) + 11) = v158;
                                          *((_DWORD *)v15 + 4 * (unsigned int)(*((_DWORD *)v15 + 8))++ + 12) = v159;
                                          v160 = 0;
                                          v161 = 0;
                                        }
                                        *((_DWORD *)v15 + 1) += 5;
                                        *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
LABEL_329:
                                        if ( !v161 )
                                        {
                                          if ( a6 )
                                          {
                                            while ( 1 )
                                            {
                                              v171 = a6[v160];
                                              if ( !v171 )
                                                break;
                                              if ( a8 )
                                                v172 = CLdapBer::HrAddValue(v15, v171, 4u);
                                              else
                                                v172 = CLdapBer::HrAddValue(v15, (LPCCH)v171, 4u);
                                              if ( v172 )
                                              {
                                                if ( g_fTracingOn
                                                  && g_fProviderEnabled
                                                  && (g_ulTraceFlags & 0x400000) != 0 )
                                                {
                                                  v76 = a2;
                                                  lpMultiByteStr = a6[v160];
                                                  if ( a8 )
                                                    LDAPClientPrint(
                                                      0x400000,
                                                      "ldap_search connection 0x%x encoding error of 0x%x, attribute = '%S'.\n",
                                                      (_DWORD)a2,
                                                      v172,
                                                      lpMultiByteStr);
                                                  else
                                                    LDAPClientPrint(
                                                      0x400000,
                                                      "ldap_search connection 0x%x encoding error of 0x%x, attribute = '%s'.\n",
                                                      (_DWORD)a2,
                                                      v172,
                                                      (const char *)lpMultiByteStr);
                                                  goto LABEL_678;
                                                }
                                                goto LABEL_677;
                                              }
                                              ++v160;
                                            }
                                          }
                                          CLdapBer::HrEndWriteSequence(v15);
                                          CLdapBer::HrEndWriteSequence(v15);
                                          v76 = a2;
                                          if ( *((_DWORD *)a2 + 250) == 2
                                            || !*((_QWORD *)v106 + 25)
                                            || (inserted = InsertServerControls(v106, a2, v15)) == 0 )
                                          {
                                            CLdapBer::HrEndWriteSequence(v15);
                                            EnterCriticalSection((LPCRITICAL_SECTION)a2 + 14);
                                            EnterCriticalSection((LPCRITICAL_SECTION)((char *)v106 + 48));
                                            if ( a2 == *((struct ldap_connection **)v106 + 4) )
                                            {
                                              _InterlockedIncrement((volatile signed __int32 *)a2 + 118);
                                              ++*((_WORD *)v106 + 91);
                                              ++*((_DWORD *)v106 + 38);
                                              _InterlockedIncrement(&GlobalCountOfOpenRequests);
                                              _InterlockedIncrement64(&qword_180066138);
                                              if ( g_fTracingOn
                                                && g_fProviderEnabled
                                                && (g_ulTraceFlags & 0x1000000) != 0 )
                                              {
LABEL_382:
                                                LDAPClientPrint(
                                                  0x1000000,
                                                  "LdapAddToPendingList bumping outstanding to 0x%x for 0x%x.\n",
                                                  *((unsigned __int16 *)v106 + 91),
                                                  (_DWORD)v106);
                                              }
                                            }
                                            else
                                            {
                                              v173 = *((_QWORD *)v106 + 21);
                                              v174 = 0;
                                              if ( v173 )
                                              {
                                                while ( v174 < *((_WORD *)v106 + 88) )
                                                {
                                                  if ( *(struct ldap_connection **)v173 == a2 )
                                                  {
                                                    _InterlockedIncrement(&GlobalCountOfOpenRequests);
                                                    _InterlockedIncrement64(&qword_180066138);
                                                    _InterlockedIncrement((volatile signed __int32 *)a2 + 118);
                                                    ++*((_WORD *)v106 + 91);
                                                    ++*(_DWORD *)(v173 + 48);
                                                    if ( !g_fTracingOn
                                                      || !g_fProviderEnabled
                                                      || (g_ulTraceFlags & 0x1000000) == 0 )
                                                    {
                                                      goto LABEL_334;
                                                    }
                                                    goto LABEL_382;
                                                  }
                                                  ++v174;
                                                  v173 += 64;
                                                }
                                              }
                                              if ( g_fTracingOn
                                                && g_fProviderEnabled
                                                && (g_ulTraceFlags & 0x1000000) != 0 )
                                              {
                                                LDAPClientPrint(
                                                  0x1000000,
                                                  "LdapAddToPendingList couldn't bump for request 0x%x.\n",
                                                  (_DWORD)v106);
                                              }
                                            }
LABEL_334:
                                            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v106 + 48));
                                            v162 = LdapSend(a2, v15, 0);
                                            inserted = v162;
                                            if ( v162 )
                                            {
                                              if ( g_fTracingOn
                                                && g_fProviderEnabled
                                                && (g_ulTraceFlags & 0x100000) != 0 )
                                              {
                                                LDAPClientPrint(
                                                  0x100000,
                                                  "ldap_search Connection 0x%x send with error of 0x%x.\n",
                                                  (_DWORD)a2,
                                                  v162);
                                              }
                                              DecrementPendingList(v106, a2);
                                            }
                                            else
                                            {
                                              v15 = (CLdapBer *)_InterlockedExchange64(
                                                                  (volatile __int64 *)a9,
                                                                  (__int64)v15);
                                            }
                                            LeaveCriticalSection((LPCRITICAL_SECTION)a2 + 14);
                                          }
                                          goto LABEL_337;
                                        }
                                        if ( g_fTracingOn && g_fProviderEnabled )
                                        {
                                          v76 = a2;
                                          if ( (g_ulTraceFlags & 0x400000) != 0 )
                                            LDAPClientPrint(
                                              0x400000,
                                              "ldap_search attrlist connection 0x%x encoding error of 0x%x.\n",
                                              (_DWORD)a2,
                                              v161);
                                          goto LABEL_678;
                                        }
                                        goto LABEL_677;
                                      }
                                    }
                                    else
                                    {
LABEL_305:
                                      inserted = 87;
                                    }
                                    if ( g_fTracingOn && g_fProviderEnabled )
                                    {
                                      v76 = a2;
                                      if ( (g_ulTraceFlags & 0x400000) != 0 )
                                        LDAPClientPrint(
                                          0x400000,
                                          "ldap_search filter connection 0x%x encoding error of 0x%x.\n",
                                          (_DWORD)a2,
                                          inserted);
                                      goto LABEL_337;
                                    }
LABEL_323:
                                    v76 = a2;
                                    goto LABEL_337;
                                  }
                                  *(_BYTE *)(v119 + *((_QWORD *)v15 + 2)) = -124;
                                  *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = HIBYTE(v108);
                                  *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE2(v108);
                                }
                                else
                                {
                                  *(_BYTE *)(v119 + *((_QWORD *)v15 + 2)) = -126;
                                }
                                *(_BYTE *)((unsigned int)++*((_DWORD *)v15 + 1) + *((_QWORD *)v15 + 2)) = BYTE1(v108);
                                v120 = (unsigned int)++*((_DWORD *)v15 + 1);
                              }
                              else
                              {
                                v120 = v119;
                              }
                              v121 = *((_QWORD *)v15 + 2);
                              v122 = v108;
                              v196 = 0;
                              *(_BYTE *)(v120 + v121) = v108;
                              v123 = (_BYTE *)(*((_QWORD *)v15 + 2) + (unsigned int)++*((_DWORD *)v15 + 1));
                              if ( v108 )
                              {
                                do
                                  *v123++ = v107 >> (8 * v108-- - 8);
                                while ( v108 );
                                v106 = a1;
                              }
                              else
                              {
                                v196 = 0;
                              }
                              *((_DWORD *)v15 + 1) += v122;
                              *(_DWORD *)v15 = *((_DWORD *)v15 + 1);
                              goto LABEL_201;
                            }
                            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                              LDAPClientPrint(
                                0x10000000,
                                "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n",
                                v117,
                                1024);
LABEL_211:
                            v111 = 82;
                            goto LABEL_202;
                          }
                          v136 = v117 + v70;
                          if ( (unsigned int)v117 + v70 >= (unsigned int)v117 )
                            goto LABEL_249;
                          if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x10000000) == 0 )
                            goto LABEL_211;
                          v190 = "HrEnsureBuffer: integer overflow. DataMax 0x%x, NeededLength 0x%x\n";
                        }
                        LDAPClientPrint(0x10000000, v190, v117, v70);
                        goto LABEL_211;
                      }
                      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                      {
                        LDAPClientPrint(
                          0x10000000,
                          "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n",
                          v99,
                          1024);
                        v76 = a2;
                        goto LABEL_134;
                      }
                    }
                    v76 = a2;
LABEL_134:
                    v85 = 82;
                    goto LABEL_135;
                  }
LABEL_96:
                  v76 = a2;
                  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                  {
                    LDAPClientPrint(
                      0x400000,
                      "ldap_search DN connection 0x%x encoding error of 0x%x.\n",
                      (_DWORD)a2,
                      v66);
                    inserted = 83;
                    goto LABEL_337;
                  }
                  goto LABEL_88;
                }
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                  LDAPClientPrint(0x400000, "ldap_search cmd connection 0x%x encoding error of 0x%x.\n", v11);
LABEL_486:
                inserted = 83;
                goto LABEL_323;
              }
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
                LDAPClientPrint(
                  0x10000000,
                  "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n",
                  v47,
                  1024);
            }
            v51 = 82;
            goto LABEL_50;
          }
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
          {
            LDAPClientPrint(0x10000000, "HrEnsureBuffer: integer overflow. DataMax 0x%x, DataGrow 0x%x\n", v38, 1024);
            v11 = a2;
            goto LABEL_39;
          }
        }
        v11 = a2;
LABEL_39:
        v41 = 82;
        goto LABEL_40;
      }
    }
    else
    {
      v29 = 90;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(0x400000, "ldap_search startWrite connection 0x%x encoding error of 0x%x.\n", (_DWORD)v11, v29);
    v76 = a2;
    inserted = 83;
    goto LABEL_337;
  }
  if ( *((_QWORD *)a2 + 120) == -1 && !*((_BYTE *)a2 + 644) )
  {
    *((_DWORD *)a2 + 250) = 3;
    goto LABEL_2;
  }
  if ( (unsigned __int8)LdapCheckForMandatoryControl(*((_QWORD *)a1 + 25)) != 1 )
    goto LABEL_2;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000) != 0 )
    LDAPClientPrint(0x8000, "SendLdapSearch Connection 0x%x has mandatory controls.\n", (_DWORD)v11);
  SetConnectionError(v11, 12);
  return 12;
}

```

## disassembly

```asm
0x18000e0d0  mov     [rsp+arg_18], r9d
0x18000e0d5  mov     [rsp+arg_8], rdx
0x18000e0da  mov     [rsp+arg_0], rcx
0x18000e0df  push    rbp
0x18000e0e0  push    r13
0x18000e0e2  push    r14
0x18000e0e4  sub     rsp, 80h
0x18000e0eb  cmp     dword ptr [rdx+3E8h], 2
0x18000e0f2  mov     r13, r8
0x18000e0f5  mov     rbp, rdx
0x18000e0f8  mov     r14, rcx
0x18000e0fb  jz      loc_180010202
0x18000e101  mov     rcx, cs:LdapHeap; hHeap
0x18000e108  mov     edx, 8; dwFlags
0x18000e10d  mov     r8d, 370h; dwBytes
0x18000e113  mov     [rsp+98h+arg_10], rbx
0x18000e11b  call    cs:__imp_HeapAlloc
0x18000e122  nop     dword ptr [rax+rax+00h]
0x18000e127  mov     ecx, cs:g_fTracingOn
0x18000e12d  mov     rbx, rax
0x18000e130  test    ecx, ecx
0x18000e132  jnz     loc_18000FF13
0x18000e138  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18000e13e  test    rbx, rbx
0x18000e141  jz      short loc_18000E15F
0x18000e143  mov     dword ptr [rbx], 6C43424Ch
0x18000e149  mov     dword ptr [rbx+4], 368h
0x18000e150  add     rbx, 8
0x18000e154  add     eax, 368h
0x18000e159  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18000e15f  mov     [rsp+98h+var_40], rbx
0x18000e164  test    ecx, ecx
0x18000e166  jnz     loc_180010282
0x18000e16c  test    rbx, rbx
0x18000e16f  jnz     short loc_18000E18F
0x18000e171  test    ecx, ecx
0x18000e173  jnz     loc_180010EB0
0x18000e179  mov     ebx, 5Ah ; 'Z'
0x18000e17e  mov     rcx, rbp
0x18000e181  mov     edx, ebx
0x18000e183  call    SetConnectionError
0x18000e188  mov     eax, ebx
0x18000e18a  jmp     loc_18000F5CF
0x18000e18f  mov     ecx, [rbp+3E8h]
0x18000e195  mov     edx, 0FDE9h
0x18000e19a  mov     [rsp+98h+var_20], rsi
0x18000e19f  mov     r8d, 408h; dwBytes
0x18000e1a5  xor     esi, esi
0x18000e1a7  mov     [rsp+98h+var_28], rdi
0x18000e1ac  cmp     ecx, 2
0x18000e1af  mov     [rbx], rsi
0x18000e1b2  mov     eax, esi
0x18000e1b4  mov     [rbx+8], esi
0x18000e1b7  cmovnz  eax, edx
0x18000e1ba  mov     [rbx+10h], rsi
0x18000e1be  mov     [rbx+344h], rsi
0x18000e1c5  mov     edx, 8; dwFlags
0x18000e1ca  mov     [rbx+18h], rsi
0x18000e1ce  mov     [rbx+358h], sil
0x18000e1d5  mov     [rbx+360h], esi
0x18000e1db  mov     [rbx+35Ch], eax
0x18000e1e1  mov     rcx, cs:LdapHeap; hHeap
0x18000e1e8  mov     [rbx+20h], esi
0x18000e1eb  call    cs:__imp_HeapAlloc
0x18000e1f2  nop     dword ptr [rax+rax+00h]
0x18000e1f7  cmp     cs:g_fTracingOn, esi
0x18000e1fd  mov     rdi, rax
0x18000e200  jnz     loc_18000FF98
0x18000e206  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18000e20c  test    rdi, rdi
0x18000e20f  jz      short loc_18000E22D
0x18000e211  mov     dword ptr [rdi], 7265424Ch
0x18000e217  mov     dword ptr [rdi+4], 400h
0x18000e21e  add     rdi, 8
0x18000e222  add     eax, 400h
0x18000e227  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18000e22d  cmp     cs:g_fTracingOn, esi
0x18000e233  jnz     loc_1800102CD
0x18000e239  mov     [rsp+98h+var_38], r15
0x18000e23e  test    rdi, rdi
0x18000e241  jz      loc_18000FC78
0x18000e247  mov     rdx, [rbx+10h]; Src
0x18000e24b  test    rdx, rdx
0x18000e24e  jnz     loc_180010311
0x18000e254  mov     eax, [rbx+4]
0x18000e257  mov     r15d, 8007000Eh
0x18000e25d  mov     [rbx+10h], rdi
0x18000e261  mov     dword ptr [rbx+8], 400h
0x18000e268  mov     byte ptr [rax+rdi], 30h ; '0'
0x18000e26c  inc     dword ptr [rbx+4]
0x18000e26f  mov     eax, [rbx+20h]
0x18000e272  mov     r8d, [rbx+4]
0x18000e276  cmp     eax, 32h ; '2'
0x18000e279  jnb     loc_180010330
0x18000e27f  mov     ecx, [rbx+348h]
0x18000e285  add     rax, rax
0x18000e288  mov     edx, [rbx+344h]
0x18000e28e  mov     [rbx+rax*8+24h], r8d
0x18000e293  mov     eax, [rbx+20h]
0x18000e296  add     rax, rax
0x18000e299  mov     dword ptr [rbx+rax*8+28h], 5
0x18000e2a1  mov     eax, [rbx+20h]
0x18000e2a4  add     rax, rax
0x18000e2a7  mov     [rbx+rax*8+2Ch], ecx
0x18000e2ab  mov     ecx, esi
0x18000e2ad  mov     eax, [rbx+20h]
0x18000e2b0  add     rax, 3
0x18000e2b4  add     rax, rax
0x18000e2b7  mov     [rbx+rax*8], edx
0x18000e2ba  inc     dword ptr [rbx+20h]
0x18000e2bd  add     dword ptr [rbx+4], 5
0x18000e2c1  mov     eax, [rbx+4]
0x18000e2c4  mov     [rbx], eax
0x18000e2c6  test    ecx, ecx
0x18000e2c8  jnz     loc_18000FC7D
0x18000e2ce  mov     esi, [rsp+98h+arg_48]
0x18000e2d5  mov     r10d, 5Ah ; 'Z'
0x18000e2db  mov     [rsp+98h+var_54], r10d
0x18000e2e0  mov     edx, 80070057h
0x18000e2e5  mov     [rsp+98h+var_4C], edx
0x18000e2e9  mov     ecx, 80000000h
0x18000e2ee  mov     [rsp+98h+var_30], r12
0x18000e2f3  test    esi, esi
0x18000e2f5  jz      loc_18000FC58
0x18000e2fb  mov     eax, [rbx+360h]
0x18000e301  mov     r15d, 2
0x18000e307  mov     [rsp+98h+var_50], r15d
0x18000e30c  mov     r12d, r15d
0x18000e30f  test    eax, eax
0x18000e311  jnz     loc_180010338
0x18000e317  mov     eax, 0FF000000h
0x18000e31c  mov     edi, 4
0x18000e321  mov     ebp, 0FFFFFFFFh
0x18000e326  test    esi, eax
0x18000e328  jnz     short loc_18000E336
0x18000e32a  shr     ecx, 8
0x18000e32d  add     edi, ebp
0x18000e32f  shr     eax, 8
0x18000e332  test    eax, eax
0x18000e334  jnz     short loc_18000E326
0x18000e336  mov     rbp, [rsp+98h+arg_8]
0x18000e33e  test    esi, esi
0x18000e340  jns     loc_18000FBF9
0x18000e346  lea     r9d, [rdi+6]
0x18000e34a  cmp     r9d, edi
0x18000e34d  jb      loc_180010439
0x18000e353  mov     r8d, [rbx]
0x18000e356  lea     eax, [r8+r9]
0x18000e35a  cmp     eax, r8d
0x18000e35d  jb      loc_18000E3E5
0x18000e363  mov     r8d, [rbx+8]
0x18000e367  cmp     eax, r8d
0x18000e36a  ja      loc_18000F006
0x18000e370  test    r8d, r8d
0x18000e373  jz      loc_18000F006
0x18000e379  mov     ecx, [rbx+4]
0x18000e37c  mov     rax, [rbx+10h]
0x18000e380  mov     [rcx+rax], r12b
0x18000e384  mov     eax, [rbx+4]
0x18000e387  inc     eax
0x18000e389  mov     [rbx+4], eax
0x18000e38c  cmp     edi, 7Fh
0x18000e38f  ja      loc_18000F229
0x18000e395  mov     ecx, eax
0x18000e397  mov     rax, [rbx+10h]
0x18000e39b  xor     r9d, r9d
0x18000e39e  mov     r8d, edi
0x18000e3a1  mov     [rcx+rax], dil
0x18000e3a5  xor     ecx, ecx
0x18000e3a7  inc     dword ptr [rbx+4]
0x18000e3aa  mov     eax, [rbx+4]
0x18000e3ad  mov     edx, eax
0x18000e3af  add     rdx, [rbx+10h]
0x18000e3b3  test    edi, edi
0x18000e3b5  jz      short loc_18000E3DB
0x18000e3b7  mov     ebp, 0FFFFFFFFh
0x18000e3bc  lea     ecx, ds:0FFFFFFFFFFFFFFF8h[r8*8]
0x18000e3c4  mov     eax, esi
0x18000e3c6  sar     eax, cl
0x18000e3c8  mov     [rdx], al
0x18000e3ca  lea     rdx, [rdx+1]
0x18000e3ce  add     r8d, ebp
0x18000e3d1  jnz     short loc_18000E3BC
0x18000e3d3  mov     rbp, [rsp+98h+arg_8]
0x18000e3db  add     [rbx+4], edi
0x18000e3de  mov     eax, [rbx+4]
0x18000e3e1  mov     [rbx], eax
0x18000e3e3  jmp     short loc_18000E3F8
0x18000e3e5  cmp     cs:g_fTracingOn, 0
0x18000e3ec  jnz     loc_180010405
0x18000e3f2  mov     r9d, 52h ; 'R'
0x18000e3f8  mov     r15d, 8007000Eh
0x18000e3fe  test    r9d, r9d
0x18000e401  jnz     loc_18000FE39
0x18000e407  cmp     qword ptr [rbp+3C0h], 0FFFFFFFFFFFFFFFFh
0x18000e40f  jnz     loc_18000FC08
0x18000e415  mov     eax, [rbx+360h]
0x18000e41b  mov     r14d, 63h ; 'c'
0x18000e421  test    eax, eax
0x18000e423  jnz     loc_1800104B4
0x18000e429  mov     r8d, [rbx]
0x18000e42c  lea     eax, [r8+6]
0x18000e430  cmp     eax, r8d
0x18000e433  jb      loc_18000E6C9
0x18000e439  mov     r8d, [rbx+8]
0x18000e43d  cmp     eax, r8d
0x18000e440  ja      loc_18000F0B6
0x18000e446  test    r8d, r8d
0x18000e449  jz      loc_18000F0B6
0x18000e44f  mov     ecx, [rbx+4]
0x18000e452  mov     rax, [rbx+10h]
0x18000e456  mov     [rcx+rax], r14b
0x18000e45a  inc     dword ptr [rbx+4]
0x18000e45d  mov     eax, [rbx+20h]
0x18000e460  mov     r8d, [rbx+4]
0x18000e464  cmp     eax, 32h ; '2'
0x18000e467  jnb     loc_18001052D
0x18000e46d  mov     edx, [rbx+344h]
0x18000e473  add     rax, rax
0x18000e476  mov     ecx, [rbx+348h]
0x18000e47c  mov     [rbx+rax*8+24h], r8d
0x18000e481  mov     eax, [rbx+20h]
0x18000e484  add     rax, rax
0x18000e487  mov     dword ptr [rbx+rax*8+28h], 5
0x18000e48f  mov     eax, [rbx+20h]
0x18000e492  add     rax, rax
0x18000e495  mov     [rbx+rax*8+2Ch], ecx
0x18000e499  mov     eax, [rbx+20h]
0x18000e49c  add     rax, 3
0x18000e4a0  add     rax, rax
0x18000e4a3  mov     [rbx+rax*8], edx
0x18000e4a6  inc     dword ptr [rbx+20h]
0x18000e4a9  xor     esi, esi
0x18000e4ab  mov     r9d, esi
0x18000e4ae  add     dword ptr [rbx+4], 5
0x18000e4b2  mov     eax, [rbx+4]
0x18000e4b5  mov     [rbx], eax
0x18000e4b7  test    r9d, r9d
0x18000e4ba  jnz     loc_180010571
0x18000e4c0  mov     eax, [rbx+360h]
0x18000e4c6  mov     [rsp+98h+var_48], 4
0x18000e4ce  mov     [rsp+98h+var_58], si
0x18000e4d3  test    eax, eax
0x18000e4d5  jnz     loc_1800105AB
0x18000e4db  test    r13, r13
0x18000e4de  lea     r12, [rsp+98h+var_58]
0x18000e4e3  mov     edi, esi
0x18000e4e5  cmovnz  r12, r13
0x18000e4e9  mov     rax, r12
0x18000e4ec  nop     dword ptr [rax+00h]
0x18000e4f0  cmp     word ptr [rax], 0
0x18000e4f4  jz      short loc_18000E4FE
0x18000e4f6  inc     edi
0x18000e4f8  add     rax, 2
0x18000e4fc  jnz     short loc_18000E4F0
0x18000e4fe  mov     ecx, [rbx+35Ch]
0x18000e504  mov     ebp, 0FDE9h
0x18000e509  mov     [rsp+98h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x18000e50e  xor     edx, edx; dwFlags
0x18000e510  mov     [rsp+98h+lpDefaultChar], rsi; lpDefaultChar
0x18000e515  mov     r9d, edi; cchWideChar
0x18000e518  mov     [rsp+98h+cbMultiByte], esi; cbMultiByte
0x18000e51c  mov     r8, r12; lpWideCharStr
0x18000e51f  mov     [rsp+98h+lpMultiByteStr], rsi; lpMultiByteStr
0x18000e524  cmp     ecx, ebp
0x18000e526  jnz     short loc_18000E52A
0x18000e528  mov     ecx, ebp; CodePage
0x18000e52a  call    cs:__imp_WideCharToMultiByte
0x18000e531  nop     dword ptr [rax+rax+00h]
0x18000e536  mov     esi, eax
0x18000e538  test    eax, eax
0x18000e53a  jz      loc_18000F25C
0x18000e540  lea     r9d, [rsi+6]
0x18000e544  cmp     r9d, esi
0x18000e547  jb      loc_18000E6E3
0x18000e54d  mov     r8d, [rbx]
0x18000e550  lea     eax, [r8+r9]
0x18000e554  cmp     eax, r8d
0x18000e557  jb      loc_18000ED7F
0x18000e55d  mov     r8d, [rbx+8]
0x18000e561  cmp     eax, r8d
0x18000e564  ja      loc_18000F103
0x18000e56a  test    r8d, r8d
0x18000e56d  jz      loc_18000F103
0x18000e573  mov     ecx, [rbx+4]
0x18000e576  mov     rax, [rbx+10h]
0x18000e57a  mov     edx, [rsp+98h+var_48]
0x18000e57e  mov     [rcx+rax], dl
0x18000e581  mov     eax, [rbx+4]
0x18000e584  inc     eax
0x18000e586  mov     [rbx+4], eax
0x18000e589  cmp     esi, 7Fh
0x18000e58c  ja      loc_18000ED97
0x18000e592  mov     ecx, eax
0x18000e594  mov     rax, [rbx+10h]
0x18000e598  mov     [rcx+rax], sil
0x18000e59c  inc     dword ptr [rbx+4]
0x18000e59f  mov     eax, [rbx+4]
0x18000e5a2  test    edi, edi
0x18000e5a4  jz      short loc_18000E5E4
  ... truncated ...
```
