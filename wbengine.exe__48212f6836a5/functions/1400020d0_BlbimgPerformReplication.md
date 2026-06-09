# BlbimgPerformReplication

- ea: `0x1400020d0`
- end: `0x140003b22`
- name: `BlbimgPerformReplication`
- size: `6738`
- prototype: `__int64 __usercall@<rax>(void *Source1@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `36`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400170c8`
- `0x14005a62c`

## callees

- `0x140001ac4`
- `0x140001ca0`
- `0x1400020d0`
- `0x140003b30`
- `0x1400042e0`
- `0x140004f20`
- `0x140006428`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14003c434`
- `0x14003c69c`
- `0x14003d228`
- `0x1400b1258`
- `0x1400b7650`
- `0x1400b772c`
- `0x1400b8224`
- `0x1400b93e0`
- `0x1400b9fdc`
- `0x1400bbb38`
- `0x1400bce88`
- `0x1400bd17c`
- `0x1400c3d60`
- `0x1400c3ddc`
- `0x1400c3ed4`
- `0x1400c4114`
- `0x1400c43d8`
- `0x1400c4508`
- `0x1400c455c`
- `0x1400c472c`
- `0x1400d0620`
- `0x1400d06c4`
- `0x140134cd2`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x1400022b2`
- `KERNEL32!RtlCompareMemory` at `0x1400022b2`
- `KERNEL32!GetOverlappedResult` at `0x140002af7`
- `KERNEL32!GetOverlappedResult` at `0x140003381`
- `KERNEL32!GetOverlappedResult` at `0x140003863`
- `KERNEL32!GetOverlappedResult` at `0x140002af7`
- `KERNEL32!GetOverlappedResult` at `0x140003381`
- `KERNEL32!GetOverlappedResult` at `0x140003863`
- `KERNEL32!LocalAlloc` at `0x140002309`
- `KERNEL32!LocalAlloc` at `0x140002372`
- `KERNEL32!LocalAlloc` at `0x140002309`
- `KERNEL32!LocalAlloc` at `0x140002372`
- `KERNEL32!WriteFile` at `0x140003260`
- `KERNEL32!WriteFile` at `0x140003260`
- `KERNEL32!GetSystemTime` at `0x140002a91`
- `KERNEL32!GetSystemTime` at `0x140003478`
- `KERNEL32!GetSystemTime` at `0x1400034ba`
- `KERNEL32!GetSystemTime` at `0x140002a91`
- `KERNEL32!GetSystemTime` at `0x140003478`
- `KERNEL32!GetSystemTime` at `0x1400034ba`
- `KERNEL32!LocalFree` at `0x1400023ea`
- `KERNEL32!LocalFree` at `0x140002412`
- `KERNEL32!LocalFree` at `0x140002462`
- `KERNEL32!LocalFree` at `0x1400039f9`
- `KERNEL32!LocalFree` at `0x1400023ea`
- `KERNEL32!LocalFree` at `0x140002412`
- `KERNEL32!LocalFree` at `0x140002462`
- `KERNEL32!LocalFree` at `0x1400039f9`
- `KERNEL32!SetEvent` at `0x140003349`
- `KERNEL32!SetEvent` at `0x140003349`
- `KERNEL32!CloseHandle` at `0x140002404`
- `KERNEL32!CloseHandle` at `0x140002422`
- `KERNEL32!CloseHandle` at `0x140002454`
- `KERNEL32!CloseHandle` at `0x140002472`
- `KERNEL32!CloseHandle` at `0x1400039e6`
- `KERNEL32!CloseHandle` at `0x140003a3a`
- `KERNEL32!CloseHandle` at `0x140003ab7`
- `KERNEL32!CloseHandle` at `0x140002404`
- `KERNEL32!CloseHandle` at `0x140002422`
- `KERNEL32!CloseHandle` at `0x140002454`
- `KERNEL32!CloseHandle` at `0x140002472`
- `KERNEL32!CloseHandle` at `0x1400039e6`
- `KERNEL32!CloseHandle` at `0x140003a3a`
- `KERNEL32!CloseHandle` at `0x140003ab7`
- `KERNEL32!CreateEventW` at `0x140002353`
- `KERNEL32!CreateEventW` at `0x1400023b1`
- `KERNEL32!CreateEventW` at `0x140002353`
- `KERNEL32!CreateEventW` at `0x1400023b1`
- `KERNEL32!GetLastError` at `0x14000231b`
- `KERNEL32!GetLastError` at `0x1400023d9`
- `KERNEL32!GetLastError` at `0x140002432`
- `KERNEL32!GetLastError` at `0x140002b05`
- `KERNEL32!GetLastError` at `0x14000326e`
- `KERNEL32!GetLastError` at `0x14000338b`
- `KERNEL32!GetLastError` at `0x14000386d`
- `KERNEL32!GetLastError` at `0x14000231b`
- `KERNEL32!GetLastError` at `0x1400023d9`
- `KERNEL32!GetLastError` at `0x140002432`
- `KERNEL32!GetLastError` at `0x140002b05`
- `KERNEL32!GetLastError` at `0x14000326e`
- `KERNEL32!GetLastError` at `0x14000338b`
- `KERNEL32!GetLastError` at `0x14000386d`
- `ntdll!RtlNumberOfSetBits` at `0x1400027e4`
- `ntdll!RtlNumberOfSetBits` at `0x1400027e4`
- `ntdll!RtlInitializeBitMap` at `0x1400027c6`
- `ntdll!RtlInitializeBitMap` at `0x1400027da`
- `ntdll!RtlInitializeBitMap` at `0x140002869`
- `ntdll!RtlInitializeBitMap` at `0x1400027c6`
- `ntdll!RtlInitializeBitMap` at `0x1400027da`
- `ntdll!RtlInitializeBitMap` at `0x140002869`
- `ntdll!RtlAreBitsSet` at `0x14000282a`
- `ntdll!RtlAreBitsSet` at `0x14000282a`

## pseudocode

```c
__int64 __fastcall BlbimgPerformReplication(
        void *Source1,
        unsigned __int8 (__fastcall *a2)(__int64, _QWORD, _QWORD),
        __int64 a3,
        __int64 a4,
        bool *a5,
        _OWORD *a6,
        __int64 a7,
        __int64 a8,
        unsigned __int8 *a9,
        _QWORD *a10,
        _QWORD *a11,
        bool *a12,
        DWORD *a13)
{
  PVOID *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v18; // edi
  HLOCAL v20; // rax
  HLOCAL v21; // rax
  void *v22; // rbx
  HANDLE EventW; // rax
  __int64 i; // rsi
  __int64 v25; // rsi
  _QWORD *v26; // rbx
  DWORD *v27; // rdi
  DWORD Block; // esi
  char *v29; // r12
  void *v30; // rcx
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  bool v33; // zf
  ULONG v34; // eax
  const signed __int64 *Buffer; // rcx
  unsigned __int64 v36; // rdx
  ULONG v37; // ebx
  unsigned __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // r9
  void *v41; // r8
  void *v42; // rdx
  unsigned int v43; // ebx
  char v44; // r13
  __int64 v45; // r8
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  char v48; // r14
  __int64 v49; // r15
  __int64 v50; // rbx
  unsigned int v51; // eax
  unsigned int *v52; // rdi
  void *v53; // rcx
  __int64 v54; // rsi
  __int64 v55; // r8
  DWORD LastError; // r14d
  unsigned int v57; // r8d
  unsigned int *v58; // r15
  unsigned __int8 v59; // al
  __int64 v60; // r8
  PVOID *v61; // rcx
  __int64 v62; // r8
  __int64 v63; // r14
  PVOID *v64; // rcx
  LONGLONG v65; // rbx
  unsigned int v66; // r12d
  _OWORD *v67; // r13
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  unsigned int v71; // edi
  __int64 v72; // r9
  __int64 v73; // r8
  __int64 v74; // rdx
  __int64 v75; // rcx
  unsigned int v76; // ecx
  unsigned int v77; // r9d
  unsigned int v78; // esi
  bool v79; // cf
  unsigned int v80; // ecx
  unsigned int v81; // edi
  unsigned int v82; // ecx
  unsigned int v83; // edi
  __int64 v84; // r9
  __int64 v85; // r8
  __int64 v86; // rdx
  __int64 v87; // rcx
  unsigned __int8 *v88; // r8
  __int64 k; // rcx
  PVOID *v90; // rcx
  ULONG_PTR v91; // rdi
  void *v92; // rbx
  LPOVERLAPPED v93; // rsi
  DWORD v94; // eax
  ULONG_PTR v95; // rbx
  ULONG_PTR v96; // rax
  unsigned __int64 v97; // rsi
  DWORD v98; // r14d
  unsigned int v99; // r9d
  const void *v100; // rdx
  void *v101; // rcx
  unsigned int v102; // r14d
  __int64 v103; // r9
  char *v104; // r8
  PVOID *v105; // rcx
  void *v106; // rbx
  const void *v107; // rdx
  unsigned __int8 *v108; // rdi
  __int64 v109; // r8
  DWORD v110; // eax
  __int64 m; // rbx
  HANDLE hEvent; // rcx
  HLOCAL v113; // rcx
  DWORD v114; // eax
  __int64 v115; // rcx
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-E0h]
  unsigned int lpOverlappeda; // [rsp+20h] [rbp-E0h]
  unsigned int v118; // [rsp+28h] [rbp-D8h]
  char v119; // [rsp+70h] [rbp-90h]
  char j; // [rsp+71h] [rbp-8Fh]
  _WORD v121[7]; // [rsp+72h] [rbp-8Eh] BYREF
  int v122; // [rsp+80h] [rbp-80h]
  _QWORD *v123; // [rsp+88h] [rbp-78h]
  _QWORD *v124; // [rsp+90h] [rbp-70h]
  DWORD v125; // [rsp+98h] [rbp-68h] BYREF
  void *Source1a; // [rsp+A0h] [rbp-60h]
  LPOVERLAPPED v127; // [rsp+A8h] [rbp-58h]
  unsigned __int8 *v128; // [rsp+B0h] [rbp-50h]
  __int64 v129; // [rsp+B8h] [rbp-48h]
  unsigned __int8 (__fastcall *v130)(__int64, _QWORD, _QWORD); // [rsp+C0h] [rbp-40h]
  _RTL_BITMAP BitMapHeader; // [rsp+C8h] [rbp-38h] BYREF
  BLBIMGI_SNAPSHOT_VOLUME *v132; // [rsp+D8h] [rbp-28h]
  union _LARGE_INTEGER v133; // [rsp+E0h] [rbp-20h]
  struct _OVERLAPPED v134; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v135[2]; // [rsp+110h] [rbp+10h] BYREF
  LONGLONG v136; // [rsp+120h] [rbp+20h]
  struct _RTL_BITMAP v137; // [rsp+128h] [rbp+28h] BYREF
  struct _RTL_BITMAP v138; // [rsp+138h] [rbp+38h] BYREF
  _DWORD v139[4]; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v140; // [rsp+160h] [rbp+60h]
  unsigned int v141; // [rsp+164h] [rbp+64h]
  _OWORD v142[4]; // [rsp+168h] [rbp+68h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _SYSTEMTIME v144; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v145[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned int v146[32]; // [rsp+250h] [rbp+150h] BYREF
  union _LARGE_INTEGER v147[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  void *Src[32]; // [rsp+3D0h] [rbp+2D0h] BYREF
  struct _OVERLAPPED Overlapped[32]; // [rsp+4D0h] [rbp+3D0h] BYREF
  HLOCAL hMem[32]; // [rsp+8D0h] [rbp+7D0h] BYREF
  unsigned __int8 v151[16]; // [rsp+9D0h] [rbp+8D0h] BYREF
  _BYTE v152[8]; // [rsp+9E0h] [rbp+8E0h] BYREF

  v123 = a10;
  v129 = a3;
  v130 = a2;
  Source1a = Source1;
  v124 = a11;
  v128 = a9;
  *(_QWORD *)&v121[3] = a13;
  BitMapHeader = 0;
  v138 = 0;
  v137 = 0;
  memset_0(hMem, 0, sizeof(hMem));
  *(_DWORD *)&v121[1] = 0;
  LOBYTE(v121[0]) = 0;
  SystemTime = 0;
  v144 = 0;
  memset(&v134, 0, sizeof(v134));
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 367, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 && *((_BYTE *)v15 + 25) >= 5u )
      WPP_SF_q(v15[2], 368, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids, Source1);
  }
  if ( a12 )
    *a12 = *a5;
  v16 = *((_QWORD *)Source1 + 18);
  SystemTime = 0;
  *v123 = v16;
  v17 = *((_QWORD *)Source1 + 19);
  v144 = 0;
  *v124 = v17;
  *a13 = 0;
  memset_0(Src, 0, sizeof(Src));
  memset_0(Overlapped, 0, sizeof(Overlapped));
  memset_0(v146, 0, sizeof(v146));
  *(_OWORD *)a9 = 0;
  v18 = 0;
  memset(v151, 0, sizeof(v151));
  if ( RtlCompareMemory(Source1, &BLBIMGI_REPLICATION_CONTEXT_GUID, 0x10u) != 16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 369, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
    }
    *a13 = 87;
    return 2;
  }
  v20 = LocalAlloc(0, 0x10000u);
  *((_QWORD *)Source1 + 39) = v20;
  if ( !v20 || (*((_QWORD *)Source1 + 43) = a7, memset(&v134, 0, 24), (v134.hEvent = CreateEventW(0, 1, 0, 0)) == 0) )
  {
    *a13 = GetLastError();
    return 3;
  }
  while ( v18 < 0x20 )
  {
    v21 = LocalAlloc(0, 0x20000u);
    v22 = v21;
    hMem[v18] = v21;
    if ( !v21 )
    {
      v25 = 0;
      for ( **(_DWORD **)&v121[3] = GetLastError(); (unsigned int)v25 < v18; v25 = (unsigned int)(v25 + 1) )
      {
        CloseHandle(Overlapped[(unsigned int)v25].hEvent);
        LocalFree(hMem[v25]);
      }
      CloseHandle(v134.hEvent);
      return 3;
    }
    Src[v18] = (void *)(((unsigned __int64)v21 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL);
    EventW = CreateEventW(0, 1, 0, 0);
    Overlapped[v18].hEvent = EventW;
    if ( !EventW )
    {
      **(_DWORD **)&v121[3] = GetLastError();
      LocalFree(v22);
      for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
      {
        CloseHandle(Overlapped[(unsigned int)i].hEvent);
        LocalFree(hMem[i]);
      }
      CloseHandle(v134.hEvent);
      return 7;
    }
    v146[v18++] = 0;
  }
  v26 = Source1a;
  v27 = *(DWORD **)&v121[3];
  HIBYTE(v121[0]) = 0;
  if ( *((_DWORD *)Source1a + 19) == 1 )
  {
    if ( *((_BYTE *)Source1a + 336) )
    {
LABEL_40:
      v125 = BlbimgPrepareTargetForRestore(a4, Source1a, *(_QWORD *)&v121[3]);
      Block = v125;
      if ( v125 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_37:
          v29 = (char *)Source1a;
          *v123 = *((_QWORD *)Source1a + 18);
          *v124 = v26[19];
          goto LABEL_283;
        }
        LODWORD(lpOverlapped) = **(_DWORD **)&v121[3];
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 371, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
        v29 = (char *)Source1a;
        *v123 = *((_QWORD *)Source1a + 18);
        *v124 = v26[19];
LABEL_283:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LODWORD(lpOverlapped) = *v27;
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 399, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
        }
        BlbimgWaitForOverlappedResults(
          *((HANDLE *)v29 + 4),
          *((HANDLE *)v29 + 41),
          Overlapped,
          v146,
          (unsigned int)lpOverlapped);
        goto LABEL_288;
      }
      v29 = (char *)Source1a;
      goto LABEL_71;
    }
    Block = BlbimgStopDeleteInTheMiddle<BLBIMGI_REPLICATION_CONTEXT>((__int64)Source1a, &v134, *(DWORD **)&v121[3]);
    if ( Block )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LODWORD(lpOverlapped) = **(_DWORD **)&v121[3];
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 370, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
      }
      goto LABEL_37;
    }
    HIBYTE(v121[0]) = 1;
  }
  if ( *((_BYTE *)Source1a + 336) )
    goto LABEL_40;
  if ( !a8 )
    BlbAssert("base\\stor\\blb\\blbimg\\blbimg.cxx", 0x1E0Eu, "ReplicationHandle");
  v29 = (char *)Source1a;
  v30 = Source1a;
  *((_QWORD *)Source1a + 41) = a8;
  Block = BlbimgCopyFirstBlock(v30, v27);
  if ( Block )
    goto LABEL_282;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 372, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
  }
  if ( *((_DWORD *)v29 + 19) == 1 && !*a5 )
  {
    *(_OWORD *)v135 = *a6;
    Block = BlbimgCheckIfDiffBackupPossible<BLBIMGI_REPLICATION_CONTEXT>(
              (unsigned int *)v29,
              0,
              0,
              0,
              (UUID *)v135,
              v121,
              0,
              v27);
    if ( Block )
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_60;
      }
      v32 = 373;
      goto LABEL_59;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 374, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
    }
  }
  v33 = LOBYTE(v121[0]) == 0;
  *a12 = 1;
  *a5 = v33;
  v125 = BlbimgZeroStartOfVolume(*((_QWORD *)v29 + 41), *((_QWORD *)v29 + 43), v27);
  Block = v125;
  if ( v125 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 375, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
    }
    goto LABEL_60;
  }
LABEL_71:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 376, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
  }
  RtlInitializeBitMap(&BitMapHeader, *((PULONG *)v29 + 11), *((_DWORD *)v29 + 18));
  RtlInitializeBitMap(&v138, *((PULONG *)v29 + 12), *((_DWORD *)v29 + 18));
  v34 = RtlNumberOfSetBits(&BitMapHeader);
  Buffer = (const signed __int64 *)BitMapHeader.Buffer;
  v36 = (unsigned __int64)v34 << 16;
  *((_QWORD *)v29 + 19) = v36;
  v37 = v34;
  if ( !_bittest64(Buffer, 0) )
    *((_QWORD *)v29 + 19) = v36 + 0x10000;
  if ( RtlAreBitsSet(&BitMapHeader, *((_DWORD *)v29 + 18) - 1, 1u) )
  {
    v38 = (unsigned __int16)((*((__int64 *)v29 + 8) >> 63) + *((_QWORD *)v29 + 8))
        - (unsigned __int64)(unsigned __int16)(*((__int64 *)v29 + 8) >> 63);
    if ( v38 )
      *((_QWORD *)v29 + 19) += v38 - 0x10000;
  }
  RtlInitializeBitMap(&v137, *((PULONG *)v29 + 13), 4 * *((_DWORD *)v29 + 18));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_iL(*((_QWORD *)WPP_GLOBAL_Control + 2), 377, v39, *((_QWORD *)v29 + 19), v37);
  }
  v40 = *((_QWORD *)v29 + 8);
  v41 = (void *)*((_QWORD *)v29 + 5);
  v42 = (void *)*((_QWORD *)v29 + 4);
  v43 = 0;
  v118 = *((_DWORD *)v29 + 45);
  lpOverlappeda = *((_DWORD *)v29 + 44);
  v132 = (BLBIMGI_SNAPSHOT_VOLUME *)(v29 + 192);
  BLBIMGI_SNAPSHOT_VOLUME::Initialize(
    (BLBIMGI_SNAPSHOT_VOLUME *)(v29 + 192),
    v42,
    v41,
    v40,
    lpOverlappeda,
    v118,
    &BitMapHeader,
    &v137,
    0,
    0,
    1,
    (struct _LIST_ENTRY *)v29 + 7,
    (struct _LIST_ENTRY *)v29 + 10,
    1);
  v44 = 0;
  v119 = 0;
  *v123 = *((_QWORD *)v29 + 18);
  *v124 = *((_QWORD *)v29 + 19);
  while ( v43 < 0x20 )
  {
    if ( !BLBIMGI_SNAPSHOT_VOLUME::ReadBlock(
            (BLBIMGI_SNAPSHOT_VOLUME *)(v29 + 192),
            Src[v43],
            &Overlapped[v43],
            &v147[v43],
            &v145[v43]) )
    {
      v44 = 1;
      v119 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LODWORD(lpOverlapped) = v147[v43].HighPart;
        WPP_SF_dDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 378, v45, v145[v43]);
      }
      break;
    }
    v146[v43] = 1;
    v43 += 2;
  }
  if ( !v130(v129, *((_QWORD *)v29 + 18), *((_QWORD *)v29 + 19)) )
  {
    Block = 1;
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v47 = 379;
LABEL_97:
      WPP_SF_(v46[2], v47, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
    }
LABEL_98:
    v27 = *(DWORD **)&v121[3];
    *v123 = *((_QWORD *)v29 + 18);
    *v124 = *((_QWORD *)v29 + 19);
    goto LABEL_283;
  }
  v48 = 0;
  GetSystemTime(&SystemTime);
LABEL_100:
  if ( !v48 )
  {
    v48 = 1;
    v49 = 0;
    for ( j = 1; ; j = 0 )
    {
      while ( 1 )
      {
        v122 = v49;
        if ( (unsigned int)v49 >= 0x20 )
          goto LABEL_100;
        v50 = (unsigned int)v49;
        v51 = v146[v49];
        v52 = &v146[v49];
        if ( v51 == 1 )
        {
          v53 = (void *)*((_QWORD *)v29 + 4);
          v54 = (unsigned int)v49;
          v127 = &Overlapped[v54];
          if ( !GetOverlappedResult(v53, &Overlapped[v54], (LPDWORD)&v121[1], 1) )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              LODWORD(lpOverlapped) = v145[v49];
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iLd)(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                380,
                v55,
                (union _LARGE_INTEGER)v147[v49].QuadPart);
            }
            v57 = v145[(unsigned int)v49];
            v58 = &v145[(unsigned int)v49];
            v59 = BLBIMGI_SNAPSHOT_VOLUME::IsLastClusterInRead(v132, v147[v50].QuadPart, v57);
            if ( LastError == 23 || v59 )
            {
              v61 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 381, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
                  v61 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v61 != &WPP_GLOBAL_Control && (*((_BYTE *)v61 + 28) & 4) != 0 && *((_BYTE *)v61 + 25) >= 4u )
                  WPP_SF_d(v61[2], 382, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
              }
              LastError = BLBIMGI_SNAPSHOT_VOLUME::ReadAndZeroUnreadable(v132, Src[v50], v147[v50], *v58);
              if ( LastError )
              {
LABEL_112:
                v27 = *(DWORD **)&v121[3];
                **(_DWORD **)&v121[3] = LastError;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  lpOverlapped = (LPOVERLAPPED)v147[v50].QuadPart;
                  WPP_SF_LiD(*((_QWORD *)WPP_GLOBAL_Control + 2), 383, v60, *v58);
                }
                v29 = (char *)Source1a;
                Block = 4;
                goto LABEL_60;
              }
              *(_DWORD *)&v121[1] = *v58;
            }
            else if ( LastError )
            {
              goto LABEL_112;
            }
            v44 = v119;
            v29 = (char *)Source1a;
            LODWORD(v49) = v122;
          }
          v62 = v145[v50];
          v135[0] = (__int64)&v145[v50];
          if ( *(_DWORD *)&v121[1] != (_DWORD)v62 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LODWORD(lpOverlapped) = v62;
              WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 384, v62, *(unsigned int *)&v121[1]);
            }
            v27 = *(DWORD **)&v121[3];
            Block = 4;
            **(_DWORD **)&v121[3] = 1117;
            goto LABEL_60;
          }
          v63 = v50;
          if ( !v147[v50].QuadPart )
          {
            memcpy_0(*((void **)v29 + 39), Src[v50], 0x10000u);
            *v52 = 0;
LABEL_195:
            v48 = j;
            goto LABEL_196;
          }
          v64 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_dDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 385, v62, (unsigned int)v62);
            v64 = (PVOID *)WPP_GLOBAL_Control;
          }
          *v52 = 2;
          if ( v64 != &WPP_GLOBAL_Control && (*((_BYTE *)v64 + 28) & 4) != 0 && *((_BYTE *)v64 + 25) >= 5u )
            WPP_SF_d(v64[2], 386, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
          v65 = *((_QWORD *)v29 + 43) + v147[v50].QuadPart;
          v66 = *(_DWORD *)&v121[1];
          v67 = Src[v63];
          *(_DWORD *)((char *)&Overlapped[0].Pointer + v54 * 32 + 4) = HIDWORD(v65);
          v136 = v65;
          *(DWORD *)((char *)&Overlapped[0].Offset + v54 * 32) = v65;
          j = 0;
          memset_0(v142, 0, sizeof(v142));
          v139[0] = 1732584193;
          v140 = 8 * v66;
          v139[1] = -271733879;
          v139[2] = -1732584194;
          v139[3] = 271733878;
          v141 = v66 >> 29;
          if ( v66 < 0x40 )
          {
            v71 = 0;
          }
          else
          {
            v68 = v67[1];
            v142[0] = *v67;
            v69 = v67[2];
            v142[1] = v68;
            v70 = v67[3];
            v142[2] = v69;
            v142[3] = v70;
            MD4Transform(v139, v142);
            v71 = 4;
            if ( v66 > 0x7F )
            {
              do
              {
                MD4Transform(v139, &v67[v71]);
                v71 += 4;
              }
              while ( v71 * 16 + 63 < v66 );
            }
          }
          memcpy_0(v142, &v67[v71], v66 - v71 * 16);
          v72 = 0;
          v73 = 0;
          do
          {
            v74 = 4 * v72;
            v152[v73] = *((_BYTE *)&v140 + 4 * v72);
            v72 = (unsigned int)(v72 + 1);
            v152[(unsigned int)(v73 + 1)] = *((_BYTE *)&v140 + v74 + 1);
            v152[(unsigned int)(v73 + 2)] = *((_BYTE *)&v140 + v74 + 2);
            v75 = (unsigned int)(v73 + 3);
            v73 = (unsigned int)(v73 + 4);
            v152[v75] = *((_BYTE *)&v140 + v74 + 3);
          }
          while ( (unsigned int)v73 < 8 );
          v76 = v140;
          v77 = (v140 >> 3) & 0x3F;
          v78 = 56 - v77;
          if ( v77 >= 0x38 )
            v78 = 120 - v77;
          v140 += 8 * v78;
          v79 = 8 * v78 + v76 < 8 * v78;
          v80 = v141;
          if ( v79 )
            v80 = v141 + 1;
          v81 = 64 - v77;
          v141 = (v78 >> 29) + v80;
          if ( v78 < 64 - v77 )
          {
            v81 = 0;
          }
          else
          {
            memcpy_0((char *)v142 + v77, qword_14015EA10, v81);
            MD4Transform(v139, v142);
            for ( ; v81 + 63 < v78; v81 += 64 )
              MD4Transform(v139, (char *)qword_14015EA10 + v81);
            v77 = 0;
          }
          memcpy_0((char *)v142 + v77, (char *)qword_14015EA10 + v81, v78 - v81);
          v82 = (v140 >> 3) & 0x3F;
          v140 += 64;
          if ( v140 < 0x40 )
            ++v141;
          v83 = 64 - v82;
          if ( 64 - v82 > 8 )
          {
            v83 = 0;
          }
          else
          {
            memcpy_0((char *)v142 + v82, v152, v83);
            MD4Transform(v139, v142);
            for ( ; v83 + 63 < 8; v83 += 64 )
              MD4Transform(v139, &v152[v83]);
            v82 = 0;
          }
          memcpy_0((char *)v142 + v82, &v152[v83], 8 - v83);
          v84 = 0;
          v85 = 0;
          do
          {
            v86 = v84;
            v151[v85] = v139[v84];
            v84 = (unsigned int)(v84 + 1);
            v151[(unsigned int)(v85 + 1)] = BYTE1(v139[v86]);
            v151[(unsigned int)(v85 + 2)] = BYTE2(v139[v86]);
            v87 = (unsigned int)(v85 + 3);
            v85 = (unsigned int)(v85 + 4);
            v151[v87] = HIBYTE(v139[v86]);
          }
          while ( (unsigned int)v85 < 0x10 );
          memset_0(v139, 0, 0x58u);
          v88 = v128;
          if ( v128 > &v151[15] || v128 + 15 < v151 )
          {
            *(__m128 *)v128 = _mm_xor_ps(
                                (__m128)_mm_loadu_si128((const __m128i *)v151),
                                (__m128)_mm_loadu_si128((const __m128i *)v128));
          }
          else
          {
            for ( k = 0; k != 16; ++k )
              v88[k] ^= v151[k];
          }
          v90 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_DDDDD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                501,
                v88,
                v66,
                *(_DWORD *)v151,
                *(_DWORD *)&v151[4],
                *(_DWORD *)&v151[8],
                *(_DWORD *)&v151[12]);
              v90 = (PVOID *)WPP_GLOBAL_Control;
              v88 = v128;
            }
            if ( v90 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v90 + 28) & 4) != 0 && *((_BYTE *)v90 + 25) >= 5u )
              {
                WPP_SF_DDDDD(
                  v90[2],
                  502,
                  v88,
                  v66,
                  *(_DWORD *)v88,
                  *((_DWORD *)v88 + 1),
                  *((_DWORD *)v88 + 2),
                  *((_DWORD *)v88 + 3));
                v90 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v90 != &WPP_GLOBAL_Control && (*((_BYTE *)v90 + 28) & 4) != 0 && *((_BYTE *)v90 + 25) >= 5u )
              {
                WPP_SF_DDDDDDD(v90[2], 387, v88, HIDWORD(v136));
                v90 = (PVOID *)WPP_GLOBAL_Control;
              }
            }
            LODWORD(v49) = v122;
          }
          v29 = (char *)Source1a;
          v91 = *(unsigned int *)v135[0];
          v92 = (void *)*((_QWORD *)Source1a + 41);
          if ( v90 == &WPP_GLOBAL_Control || (*((_BYTE *)v90 + 28) & 4) == 0 )
          {
            v93 = v127;
          }
          else
          {
            v93 = v127;
            if ( *((_BYTE *)v90 + 25) >= 5u )
              WPP_SF_qqDDD(v90[2], 509, v88, *((_QWORD *)Source1a + 41), v67, v91, v127->Offset, v127->OffsetHigh);
          }
          if ( WriteFile(v92, v67, v91, 0, v93) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 512, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
            }
            v96 = v91;
          }
          else
          {
            v94 = GetLastError();
            v95 = v94;
            if ( v94 == 997 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 510, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
              }
              goto LABEL_194;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 511, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
            }
            v93->Internal = v95;
            v96 = 0;
          }
          v93->InternalHigh = v96;
          SetEvent(v93->hEvent);
LABEL_194:
          v44 = v119;
          goto LABEL_195;
        }
        if ( v51 == 2 )
        {
          v97 = 32LL * (unsigned int)v49;
          if ( GetOverlappedResult(*((HANDLE *)v29 + 41), &Overlapped[v97 / 0x20], (LPDWORD)&v121[1], 1) )
          {
            v103 = *(unsigned int *)&v121[1];
          }
          else
          {
            v98 = GetLastError();
            if ( v98 != 23 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                LODWORD(lpOverlapped) = *(&Overlapped[0].Offset + 8 * (unsigned int)v49);
                WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 389, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
              }
              v27 = *(DWORD **)&v121[3];
              Block = 5;
              **(_DWORD **)&v121[3] = v98;
              goto LABEL_60;
            }
            v99 = v145[v49];
            v100 = Src[v49];
            v101 = (void *)*((_QWORD *)v29 + 41);
            v133.LowPart = *(&Overlapped[0].Offset + 8 * (unsigned int)v49);
            v133.HighPart = *((_DWORD *)&Overlapped[0].Pointer + 8 * (unsigned int)v49 + 1);
            v102 = BlbimgRetryWriteOnCRCError(v101, v100, v133, v99);
            if ( v102 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                LODWORD(lpOverlapped) = *(&Overlapped[0].Offset + 8 * (unsigned int)v49);
                WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 388, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
              }
              v27 = *(DWORD **)&v121[3];
              Block = 20;
              **(_DWORD **)&v121[3] = v102;
              goto LABEL_60;
            }
            v103 = v145[v49];
            v48 = j;
            *(_DWORD *)&v121[1] = v145[v49];
          }
          v104 = (char *)&Overlapped[0].Pointer + 4;
          v105 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            LODWORD(lpOverlapped) = *(DWORD *)((char *)&Overlapped[0].Offset + v97);
            WPP_SF_DDd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              390,
              (char *)&Overlapped[0].Pointer + 4,
              *(unsigned int *)((char *)&Overlapped[0].Pointer + v97 + 4));
            v103 = *(unsigned int *)&v121[1];
            v105 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (_DWORD)v103 != v145[v49] )
          {
            if ( v105 != &WPP_GLOBAL_Control && (*((_BYTE *)v105 + 28) & 4) != 0 && *((_BYTE *)v105 + 25) >= 2u )
            {
              LODWORD(lpOverlapped) = v145[v49];
              WPP_SF_DDd(v105[2], 391, v104, v103);
            }
            v27 = *(DWORD **)&v121[3];
            Block = 5;
            **(_DWORD **)&v121[3] = 1117;
            goto LABEL_60;
          }
          *((_QWORD *)v29 + 18) += (unsigned int)v103;
          GetSystemTime(&v144);
          if ( v144.wSecond != SystemTime.wSecond )
          {
            if ( !v130(v129, *((_QWORD *)v29 + 18), *((_QWORD *)v29 + 19)) )
            {
              Block = 1;
              v46 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v47 = 392;
                goto LABEL_97;
              }
              goto LABEL_98;
            }
            GetSystemTime(&SystemTime);
          }
          *v52 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 393, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
          }
        }
        if ( !v44 )
          break;
LABEL_196:
        v49 = (unsigned int)(v49 + 1);
      }
      if ( !BLBIMGI_SNAPSHOT_VOLUME::ReadBlock(
              (BLBIMGI_SNAPSHOT_VOLUME *)(v29 + 192),
              Src[v49],
              &Overlapped[(unsigned int)v49],
              &v147[v49],
              &v145[v49]) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 395, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
        }
        v44 = 1;
        v119 = 1;
        goto LABEL_196;
      }
      *v52 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 394, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
      }
      v48 = 0;
      v49 = (unsigned int)(v49 + 1);
    }
  }
  v130(v129, *((_QWORD *)v29 + 18), *((_QWORD *)v29 + 19));
  v106 = Src[0];
  v107 = (const void *)*((_QWORD *)v29 + 39);
  Overlapped[0].Pointer = (PVOID)*((_QWORD *)v29 + 43);
  memcpy_0(Src[0], v107, 0x10000u);
  v108 = v128;
  BlbimgAddToChecksum(v128, v106, 0x10000u, v151);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    LODWORD(lpOverlapped) = Overlapped[0].Offset;
    WPP_SF_DDDDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 396, v109, Overlapped[0].OffsetHigh);
  }
  BlbimgWriteFile(*((HANDLE *)v29 + 41), v106, 0x10000u, Overlapped);
  if ( !GetOverlappedResult(*((HANDLE *)v29 + 41), Overlapped, (LPDWORD)&v121[1], 1) )
  {
    v110 = GetLastError();
    v27 = *(DWORD **)&v121[3];
    Block = 5;
    **(_DWORD **)&v121[3] = v110;
    goto LABEL_60;
  }
  *((_QWORD *)v29 + 18) += 0x10000LL;
  if ( v29[336] || !v29[184] )
  {
    Block = v125;
  }
  else
  {
    Block = BlbimgFixUpVolsnapControlItemsAfterBackup(v29, 1, v108, *(_QWORD *)&v121[3]);
    if ( Block )
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v27 = *(DWORD **)&v121[3];
        goto LABEL_60;
      }
      v27 = *(DWORD **)&v121[3];
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_60:
        *v123 = *((_QWORD *)v29 + 18);
        *v124 = *((_QWORD *)v29 + 19);
        goto LABEL_283;
      }
      v32 = 397;
LABEL_59:
      LODWORD(lpOverlapped) = *v27;
      WPP_SF_dd(v31[2], v32, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
      goto LABEL_60;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    LODWORD(lpOverlapped) = *((_DWORD *)v108 + 1);
    WPP_SF_DDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      398,
      WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids,
      *(unsigned int *)v108);
  }
  v27 = *(DWORD **)&v121[3];
LABEL_282:
  *v123 = *((_QWORD *)v29 + 18);
  *v124 = *((_QWORD *)v29 + 19);
  if ( Block )
    goto LABEL_283;
LABEL_288:
  for ( m = 0; m != 32; ++m )
  {
    hEvent = Overlapped[m].hEvent;
    if ( hEvent )
      CloseHandle(hEvent);
    v113 = hMem[m];
    if ( v113 )
      LocalFree(v113);
  }
  if ( HIBYTE(v121[0]) )
  {
    v125 = 0;
    v114 = BlbimgReallowDeleteInTheMiddle<BLBIMGI_BACKUP_CONTEXT>((__int64)v29, &v125);
    if ( v114 )
    {
      if ( !Block )
      {
        Block = v114;
        *v27 = v125;
      }
    }
  }
  if ( v134.hEvent )
    CloseHandle(v134.hEvent);
  v115 = *((_QWORD *)v29 + 41);
  if ( (unsigned __int64)(v115 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !Block && v29[336] )
  {
    Block = BlbimgOfflineAndOnlineVolume(v115, v27);
    if ( Block )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 400, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
      }
      Block = 0;
      *v27 = 0;
    }
    CloseHandle(*((HANDLE *)v29 + 41));
    *((_QWORD *)v29 + 41) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 401, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids);
  }
  return Block;
}

```

## disassembly

```asm
0x1400020d0  push    rbp
0x1400020d2  push    rbx
0x1400020d3  push    rsi
0x1400020d4  push    rdi
0x1400020d5  push    r12
0x1400020d7  push    r13
0x1400020d9  push    r14
0x1400020db  push    r15
0x1400020dd  lea     rbp, [rsp-8F8h]
0x1400020e5  sub     rsp, 9F8h
0x1400020ec  mov     rax, cs:__security_cookie
0x1400020f3  xor     rax, rsp
0x1400020f6  mov     [rbp+930h+var_48], rax
0x1400020fd  mov     rax, [rbp+930h+arg_48]
0x140002104  xorps   xmm0, xmm0
0x140002107  mov     rdi, [rbp+930h+arg_40]
0x14000210e  mov     rbx, rcx
0x140002111  mov     rsi, [rbp+930h+arg_60]
0x140002118  xorps   xmm1, xmm1
0x14000211b  mov     r14, [rbp+930h+arg_20]
0x140002122  mov     r12, r9
0x140002125  mov     r13, [rbp+930h+arg_28]
0x14000212c  mov     r15, [rbp+930h+arg_58]
0x140002133  mov     [rbp+930h+var_9A8], rax
0x140002137  mov     rax, [rbp+930h+arg_50]
0x14000213e  mov     [rbp+930h+var_978], r8
0x140002142  mov     r8d, 100h; Size
0x140002148  mov     [rbp+930h+var_970], rdx
0x14000214c  xor     edx, edx; Val
0x14000214e  mov     [rbp+930h+Source1], rcx
0x140002152  lea     rcx, [rbp+930h+hMem]; void *
0x140002159  mov     [rbp+930h+var_9A0], rax
0x14000215d  mov     [rbp+930h+var_980], rdi
0x140002161  mov     qword ptr [rsp+0A30h+var_9BE+6], rsi
0x140002166  movups  xmmword ptr [rbp+930h+BitMapHeader.SizeOfBitMap], xmm0
0x14000216a  movups  xmmword ptr [rbp+930h+var_8F8.SizeOfBitMap], xmm1
0x14000216e  movups  xmmword ptr [rbp+930h+var_908.SizeOfBitMap], xmm0
0x140002172  call    memset_0
0x140002177  xorps   xmm0, xmm0
0x14000217a  mov     dword ptr [rsp+0A30h+var_9BE+2], 0
0x140002182  xorps   xmm1, xmm1
0x140002185  mov     [rsp+0A30h+var_9BE], 0
0x14000218a  movups  xmmword ptr [rbp+930h+SystemTime.wYear], xmm0
0x140002191  movups  xmmword ptr [rbp+930h+var_870.wYear], xmm1
0x140002198  movups  [rbp+930h+var_948], xmm0
0x14000219c  movups  xmmword ptr [rbp+930h+hObject], xmm0
0x1400021a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021a7  lea     rax, WPP_GLOBAL_Control
0x1400021ae  cmp     rcx, rax
0x1400021b1  jz      short loc_14000220B
0x1400021b3  test    byte ptr [rcx+1Ch], 4
0x1400021b7  jz      short loc_1400021E2
0x1400021b9  cmp     byte ptr [rcx+19h], 4
0x1400021bd  jb      short loc_1400021E2
0x1400021bf  mov     rcx, [rcx+10h]
0x1400021c3  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400021ca  mov     edx, 16Fh
0x1400021cf  call    WPP_SF_
0x1400021d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021db  lea     rax, WPP_GLOBAL_Control
0x1400021e2  cmp     rcx, rax
0x1400021e5  jz      short loc_14000220B
0x1400021e7  test    byte ptr [rcx+1Ch], 4
0x1400021eb  jz      short loc_14000220B
0x1400021ed  cmp     byte ptr [rcx+19h], 5
0x1400021f1  jb      short loc_14000220B
0x1400021f3  mov     rcx, [rcx+10h]
0x1400021f7  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400021fe  mov     edx, 170h
0x140002203  mov     r9, rbx
0x140002206  call    WPP_SF_q
0x14000220b  test    r15, r15
0x14000220e  jz      short loc_14000221A
0x140002210  cmp     byte ptr [r14], 0
0x140002214  setnz   al
0x140002217  mov     [r15], al
0x14000221a  mov     rax, [rbx+90h]
0x140002221  xorps   xmm0, xmm0
0x140002224  mov     rcx, [rbp+930h+var_9A8]
0x140002228  xorps   xmm1, xmm1
0x14000222b  xor     edx, edx; Val
0x14000222d  mov     r8d, 100h; Size
0x140002233  movups  xmmword ptr [rbp+930h+SystemTime.wYear], xmm0
0x14000223a  mov     [rcx], rax
0x14000223d  mov     rax, [rbx+98h]
0x140002244  mov     rcx, [rbp+930h+var_9A0]
0x140002248  movups  xmmword ptr [rbp+930h+var_870.wYear], xmm1
0x14000224f  mov     [rcx], rax
0x140002252  lea     rcx, [rbp+930h+Src]; void *
0x140002259  mov     dword ptr [rsi], 0
0x14000225f  call    memset_0
0x140002264  xor     edx, edx; Val
0x140002266  lea     rcx, [rbp+930h+Overlapped]; void *
0x14000226d  mov     r8d, 400h; Size
0x140002273  call    memset_0
0x140002278  xor     edx, edx; Val
0x14000227a  lea     rcx, [rbp+930h+var_7E0]; void *
0x140002281  mov     r8d, 80h; Size
0x140002287  call    memset_0
0x14000228c  xorps   xmm0, xmm0
0x14000228f  lea     rdx, BLBIMGI_REPLICATION_CONTEXT_GUID; Source2
0x140002296  movups  xmmword ptr [rdi], xmm0
0x140002299  xor     edi, edi
0x14000229b  mov     r8d, 10h; Length
0x1400022a1  mov     rcx, rbx; Source1
0x1400022a4  mov     qword ptr [rbp+930h+var_60], rdi
0x1400022ab  mov     qword ptr [rbp+930h+var_60+8], rdi
0x1400022b2  call    cs:__imp_RtlCompareMemory
0x1400022b8  cmp     rax, 10h
0x1400022bc  jz      short loc_140002302
0x1400022be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022c5  lea     rax, WPP_GLOBAL_Control
0x1400022cc  cmp     rcx, rax
0x1400022cf  jz      short loc_1400022F2
0x1400022d1  test    byte ptr [rcx+1Ch], 4
0x1400022d5  jz      short loc_1400022F2
0x1400022d7  cmp     byte ptr [rcx+19h], 2
0x1400022db  jb      short loc_1400022F2
0x1400022dd  mov     rcx, [rcx+10h]
0x1400022e1  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400022e8  mov     edx, 171h
0x1400022ed  call    WPP_SF_
0x1400022f2  mov     dword ptr [rsi], 57h ; 'W'
0x1400022f8  mov     eax, 2
0x1400022fd  jmp     loc_140003AFF
0x140002302  mov     edx, 10000h; uBytes
0x140002307  xor     ecx, ecx; uFlags
0x140002309  call    cs:__imp_LocalAlloc
0x14000230f  mov     [rbx+138h], rax
0x140002316  test    rax, rax
0x140002319  jnz     short loc_14000232D
0x14000231b  call    cs:__imp_GetLastError
0x140002321  mov     [rsi], eax
0x140002323  mov     eax, 3
0x140002328  jmp     loc_140003AFF
0x14000232d  mov     rax, [rbp+930h+arg_30]
0x140002334  xorps   xmm0, xmm0
0x140002337  xor     r9d, r9d; lpName
0x14000233a  mov     [rbx+158h], rax
0x140002341  xor     r8d, r8d; bInitialState
0x140002344  mov     edx, 1; bManualReset
0x140002349  xor     ecx, ecx; lpEventAttributes
0x14000234b  movups  [rbp+930h+var_948], xmm0
0x14000234f  movups  xmmword ptr [rbp+930h+hObject], xmm0
0x140002353  call    cs:__imp_CreateEventW
0x140002359  mov     [rbp+930h+hObject+8], rax
0x14000235d  test    rax, rax
0x140002360  jz      short loc_14000231B
0x140002362  cmp     edi, 20h ; ' '
0x140002365  jnb     loc_140002482
0x14000236b  mov     edx, 20000h; uBytes
0x140002370  xor     ecx, ecx; uFlags
0x140002372  call    cs:__imp_LocalAlloc
0x140002378  mov     esi, edi
0x14000237a  mov     rbx, rax
0x14000237d  mov     [rbp+rsi*8+930h+hMem], rax
0x140002385  test    rax, rax
0x140002388  jz      loc_140002432
0x14000238e  lea     rcx, [rax+0FFFFh]
0x140002395  xor     r9d, r9d; lpName
0x140002398  and     rcx, 0FFFFFFFFFFFF0000h
0x14000239f  xor     r8d, r8d; bInitialState
0x1400023a2  mov     [rbp+rsi*8+930h+Src], rcx
0x1400023aa  mov     edx, 1; bManualReset
0x1400023af  xor     ecx, ecx; lpEventAttributes
0x1400023b1  call    cs:__imp_CreateEventW
0x1400023b7  mov     ecx, esi
0x1400023b9  shl     rcx, 5
0x1400023bd  mov     [rbp+rcx+930h+Overlapped.hEvent], rax
0x1400023c5  test    rax, rax
0x1400023c8  jz      short loc_1400023D9
0x1400023ca  mov     [rbp+rsi*4+930h+var_7E0], 0
0x1400023d5  inc     edi
0x1400023d7  jmp     short loc_140002362
0x1400023d9  call    cs:__imp_GetLastError
0x1400023df  mov     r9, qword ptr [rsp+0A30h+var_9BE+6]
0x1400023e4  mov     rcx, rbx; hMem
0x1400023e7  mov     [r9], eax
0x1400023ea  call    cs:__imp_LocalFree
0x1400023f0  xor     esi, esi
0x1400023f2  test    edi, edi
0x1400023f4  jz      short loc_14000241E
0x1400023f6  mov     ecx, esi
0x1400023f8  shl     rcx, 5
0x1400023fc  mov     rcx, [rbp+rcx+930h+Overlapped.hEvent]; hObject
0x140002404  call    cs:__imp_CloseHandle
0x14000240a  mov     rcx, [rbp+rsi*8+930h+hMem]; hMem
0x140002412  call    cs:__imp_LocalFree
0x140002418  inc     esi
0x14000241a  cmp     esi, edi
0x14000241c  jb      short loc_1400023F6
0x14000241e  mov     rcx, [rbp+930h+hObject+8]; hObject
0x140002422  call    cs:__imp_CloseHandle
0x140002428  mov     eax, 7
0x14000242d  jmp     loc_140003AFF
0x140002432  call    cs:__imp_GetLastError
0x140002438  mov     r9, qword ptr [rsp+0A30h+var_9BE+6]
0x14000243d  xor     esi, esi
0x14000243f  mov     [r9], eax
0x140002442  test    edi, edi
0x140002444  jz      short loc_14000246E
0x140002446  mov     ecx, esi
0x140002448  shl     rcx, 5
0x14000244c  mov     rcx, [rbp+rcx+930h+Overlapped.hEvent]; hObject
0x140002454  call    cs:__imp_CloseHandle
0x14000245a  mov     rcx, [rbp+rsi*8+930h+hMem]; hMem
0x140002462  call    cs:__imp_LocalFree
0x140002468  inc     esi
0x14000246a  cmp     esi, edi
0x14000246c  jb      short loc_140002446
0x14000246e  mov     rcx, [rbp+930h+hObject+8]; hObject
0x140002472  call    cs:__imp_CloseHandle
0x140002478  mov     eax, 3
0x14000247d  jmp     loc_140003AFF
0x140002482  mov     rbx, [rbp+930h+Source1]
0x140002486  mov     rdi, qword ptr [rsp+0A30h+var_9BE+6]
0x14000248b  mov     [rsp+0A30h+var_9BE+1], 0
0x140002490  cmp     dword ptr [rbx+4Ch], 1
0x140002494  jnz     loc_140002522
0x14000249a  cmp     byte ptr [rbx+150h], 0
0x1400024a1  jnz     loc_14000252B
0x1400024a7  mov     r8, rdi
0x1400024aa  lea     rdx, [rbp+930h+var_948]
0x1400024ae  mov     rcx, rbx
0x1400024b1  call    ??$BlbimgStopDeleteInTheMiddle@UBLBIMGI_REPLICATION_CONTEXT@@@@YA?AW4_BLBIMG_RESULT_CODE@@PEAUBLBIMGI_REPLICATION_CONTEXT@@PEAU_OVERLAPPED@@PEAK@Z; BlbimgStopDeleteInTheMiddle<BLBIMGI_REPLICATION_CONTEXT>(BLBIMGI_REPLICATION_CONTEXT *,_OVERLAPPED *,ulong *)
0x1400024b6  mov     esi, eax
0x1400024b8  test    eax, eax
0x1400024ba  jz      short loc_14000251D
0x1400024bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400024c3  lea     rax, WPP_GLOBAL_Control
0x1400024ca  cmp     rcx, rax
0x1400024cd  jz      short loc_1400024F9
0x1400024cf  test    byte ptr [rcx+1Ch], 4
0x1400024d3  jz      short loc_1400024F9
0x1400024d5  cmp     byte ptr [rcx+19h], 2
0x1400024d9  jb      short loc_1400024F9
0x1400024db  mov     eax, [rdi]
0x1400024dd  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x1400024e4  mov     rcx, [rcx+10h]
0x1400024e8  mov     edx, 172h
0x1400024ed  mov     r9d, esi
0x1400024f0  mov     dword ptr [rsp+0A30h+lpOverlapped], eax
0x1400024f4  call    WPP_SF_dd
0x1400024f9  mov     rax, [rbx+90h]
0x140002500  mov     r12, rbx
0x140002503  mov     rcx, [rbp+930h+var_9A8]
0x140002507  mov     [rcx], rax
0x14000250a  mov     rcx, [rbp+930h+var_9A0]
0x14000250e  mov     rax, [rbx+98h]
0x140002515  mov     [rcx], rax
0x140002518  jmp     loc_140003973
0x14000251d  mov     [rsp+0A30h+var_9BE+1], 1
0x140002522  cmp     byte ptr [rbx+150h], 0
0x140002529  jz      short loc_1400025A7
0x14000252b  mov     r8, rdi
0x14000252e  mov     rdx, rbx
0x140002531  mov     rcx, r12
0x140002534  call    ?BlbimgPrepareTargetForRestore@@YA?AW4_BLBIMG_RESULT_CODE@@PEBGPEAUBLBIMGI_REPLICATION_CONTEXT@@PEAK@Z; BlbimgPrepareTargetForRestore(ushort const *,BLBIMGI_REPLICATION_CONTEXT *,ulong *)
0x140002539  mov     [rbp+930h+var_998], eax
0x14000253c  mov     esi, eax
0x14000253e  test    eax, eax
0x140002540  jz      loc_140002778
0x140002546  mov     rcx, cs:WPP_GLOBAL_Control
0x14000254d  lea     rax, WPP_GLOBAL_Control
0x140002554  cmp     rcx, rax
0x140002557  jz      short loc_1400024F9
0x140002559  test    byte ptr [rcx+1Ch], 4
0x14000255d  jz      short loc_1400024F9
0x14000255f  cmp     byte ptr [rcx+19h], 2
0x140002563  jb      short loc_1400024F9
0x140002565  mov     eax, [rdi]
0x140002567  lea     r8, WPP_5e04bb64dd2330051dcfb7b0075df56b_Traceguids
0x14000256e  mov     rcx, [rcx+10h]
0x140002572  mov     edx, 173h
0x140002577  mov     r9d, esi
0x14000257a  mov     dword ptr [rsp+0A30h+lpOverlapped], eax
0x14000257e  call    WPP_SF_dd
0x140002583  mov     rax, [rbx+90h]
0x14000258a  mov     r12, rbx
0x14000258d  mov     rcx, [rbp+930h+var_9A8]
0x140002591  mov     [rcx], rax
0x140002594  mov     rcx, [rbp+930h+var_9A0]
0x140002598  mov     rax, [rbx+98h]
0x14000259f  mov     [rcx], rax
0x1400025a2  jmp     loc_140003973
0x1400025a7  mov     rbx, [rbp+930h+arg_38]
0x1400025ae  test    rbx, rbx
0x1400025b1  jnz     short loc_1400025CB
0x1400025b3  lea     r8, aReplicationhan; "ReplicationHandle"
0x1400025ba  mov     edx, 1E0Eh; unsigned int
0x1400025bf  lea     rcx, aBaseStorBlbBlb_0; "base\\stor\\blb\\blbimg\\blbimg.cxx"
0x1400025c6  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400025cb  mov     r12, [rbp+930h+Source1]
0x1400025cf  mov     rdx, rdi
0x1400025d2  mov     rcx, r12
0x1400025d5  mov     [r12+148h], rbx
0x1400025dd  call    ?BlbimgCopyFirstBlock@@YA?AW4_BLBIMG_RESULT_CODE@@PEAUBLBIMGI_REPLICATION_CONTEXT@@PEAK@Z; BlbimgCopyFirstBlock(BLBIMGI_REPLICATION_CONTEXT *,ulong *)
0x1400025e2  mov     esi, eax
0x1400025e4  test    eax, eax
0x1400025e6  jnz     loc_140003951
  ... truncated ...
```
