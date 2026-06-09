# DmVirtualNumaNode::ReportStatisticsVm(_VM_MEMORY_PRESSURE_REPORT_VM)

- ea: `0x14003a3c0`
- end: `0x14003b194`
- name: `?ReportStatisticsVm@DmVirtualNumaNode@@QEAAXU_VM_MEMORY_PRESSURE_REPORT_VM@@@Z`
- size: `3540`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003a1e0`

## callees

- `0x14003a3c0`
- `0x14003b19c`
- `0x14004efb0`
- `0x1400559bc`
- `0x1400f9c70`
- `0x1401332f0`
- `0x140133fe8`
- `0x14013e080`
- `0x14022ee90`
- `0x14022ff70`
- `0x140230ba4`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003a692`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003a764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003a91c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003a692`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003a764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003a91c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003a423`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003a5be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003a862`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003a423`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003a5be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003a862`

## string_xrefs

- `0x14003b071`: `DmVirtualNumaNode::ReportStatisticsVm - COM call timeouts and DM operation starts`
- `0x14003ac8d`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`
- `0x14003ace0`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`
- `0x14003ad33`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`
- `0x14003ad86`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`
- `0x14003add9`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`
- `0x14003ae3a`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`
- `0x14003ae8d`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`
- `0x14003af20`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`
- `0x14003af73`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`
- `0x14003afd0`: `onecore\vm\compute\management\resources\dm\lib\dmvirtualnumanode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DmVirtualNumaNode::ReportStatisticsVm(__int64 a1, unsigned __int64 *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  unsigned __int64 v5; // r14
  unsigned int v6; // r13d
  unsigned __int64 v7; // r12
  int v8; // esi
  __int128 v9; // xmm0
  __int64 v10; // rcx
  unsigned __int8 *v11; // r13
  unsigned __int8 *v12; // r14
  __int64 v13; // rsi
  __int64 *v14; // r12
  __int64 v15; // rdi
  struct _RTL_CRITICAL_SECTION *v16; // r14
  __m128d v17; // xmm2
  double v18; // xmm2_8
  double v19; // xmm0_8
  __m128d v20; // xmm1
  __m128d v21; // xmm3
  double v22; // xmm0_8
  __int64 v23; // rcx
  __int64 v24; // rdx
  double v25; // xmm0_8
  double v26; // xmm1_8
  __int64 v27; // rcx
  const char *v28; // rax
  __int64 v29; // r9
  double v30; // xmm6_8
  double v31; // xmm0_8
  unsigned __int64 v32; // rax
  __int64 v33; // rdi
  struct _RTL_CRITICAL_SECTION *v34; // r14
  double v35; // xmm2_8
  double v36; // xmm2_8
  double v37; // xmm1_8
  double v38; // xmm3_8
  double v39; // xmm3_8
  double v40; // xmm2_8
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rax
  unsigned __int8 v44; // al
  unsigned __int8 *v45; // r8
  double v46; // xmm0_8
  unsigned __int64 v47; // rcx
  const unsigned __int16 *v48; // rdi
  const unsigned __int16 *v49; // rax
  __int64 v50; // rcx
  const unsigned __int16 *v51; // rax
  __int64 v52; // rcx
  const unsigned __int16 *v53; // rax
  __int64 v54; // rcx
  const unsigned __int16 *v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  unsigned __int8 v77; // al
  unsigned __int8 v78; // al
  unsigned __int8 *v79; // r10
  unsigned __int8 v80; // al
  unsigned __int8 *v81; // r10
  const unsigned __int16 *v82; // [rsp+38h] [rbp-A9h] BYREF
  __int128 v83; // [rsp+48h] [rbp-99h] BYREF
  __int128 v84; // [rsp+58h] [rbp-89h] BYREF
  __int128 v85; // [rsp+68h] [rbp-79h]
  __int128 v86; // [rsp+78h] [rbp-69h] BYREF
  __int128 v87; // [rsp+88h] [rbp-59h] BYREF
  __int128 v88; // [rsp+98h] [rbp-49h]
  __int128 v89; // [rsp+A8h] [rbp-39h]
  __int128 v90; // [rsp+B8h] [rbp-29h]

  LODWORD(v82) = 0;
  v85 = 0;
  v4 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 304);
  *(_QWORD *)&v85 = &Vml::VmAutoLock::`vftable';
  *((_QWORD *)&v85 + 1) = v4;
  if ( v4 )
    EnterCriticalSection(v4);
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 392) + 104LL))(*(_QWORD *)(a1 + 392), &v87);
  v5 = *a2;
  v6 = 0x4000;
  if ( !*a2 )
  {
    v57 = 0x4000;
    if ( g_BreakOnChildAssert )
      v57 = 0;
    if ( (unsigned int)VmlIsDebugTraceEnabled(v57) )
    {
      v58 = 0x4000;
      if ( g_BreakOnChildAssert )
        v58 = 0;
      VmlDebugTrace(
        v58,
        L"%hs(%u) : assertion failed : %hs\n",
        "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
        761,
        "MemoryPressure.GuestVisiblePhysicalPages != 0");
    }
  }
  v7 = a2[1];
  if ( !v7 )
  {
    v59 = 0x4000;
    if ( g_BreakOnChildAssert )
      v59 = 0;
    if ( (unsigned int)VmlIsDebugTraceEnabled(v59) )
    {
      v60 = 0x4000;
      if ( g_BreakOnChildAssert )
        v60 = 0;
      VmlDebugTrace(
        v60,
        L"%hs(%u) : assertion failed : %hs\n",
        "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
        762,
        "MemoryPressure.ActualTotalPhysicalPages != 0");
    }
  }
  v8 = *((_DWORD *)a2 + 6);
  if ( v8 != 3 && (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 392) + 120LL))(*(_QWORD *)(a1 + 392)) )
  {
    if ( *(_DWORD *)(a1 + 240) == -1 )
    {
      if ( v7 > *(_QWORD *)(a1 + 160) )
      {
        v61 = 0x4000;
        if ( g_BreakOnChildAssert )
          v61 = 0;
        if ( (unsigned int)VmlIsDebugTraceEnabled(v61) )
        {
          v62 = 0x4000;
          if ( g_BreakOnChildAssert )
            v62 = 0;
          VmlDebugTrace(
            v62,
            L"%hs(%u) : assertion failed : %hs\n",
            "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
            789,
            "MemoryPressure.ActualTotalPhysicalPages <= m_MemoryPressure.ActualTotalPhysicalPages");
        }
      }
      if ( a2[2] == *(_QWORD *)(a1 + 168) )
        goto LABEL_7;
      v41 = 0x4000;
      if ( g_BreakOnChildAssert )
        v41 = 0;
      if ( !(unsigned int)VmlIsDebugTraceEnabled(v41) )
        goto LABEL_7;
      if ( g_BreakOnChildAssert )
        v6 = 0;
      v28 = "MemoryPressure.UnbackedPhysicalPages == m_MemoryPressure.UnbackedPhysicalPages";
      v29 = 790;
    }
    else if ( v8 )
    {
      if ( v8 == 1 )
      {
        if ( v7 < *(_QWORD *)(a1 + 160) )
        {
          v67 = 0x4000;
          if ( g_BreakOnChildAssert )
            v67 = 0;
          if ( (unsigned int)VmlIsDebugTraceEnabled(v67) )
          {
            v68 = 0x4000;
            if ( g_BreakOnChildAssert )
              v68 = 0;
            VmlDebugTrace(
              v68,
              L"%hs(%u) : assertion failed : %hs\n",
              "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
              802,
              "MemoryPressure.ActualTotalPhysicalPages >= m_MemoryPressure.ActualTotalPhysicalPages");
          }
        }
        if ( v5 < *(_QWORD *)(a1 + 152) )
        {
          v69 = 0x4000;
          if ( g_BreakOnChildAssert )
            v69 = 0;
          if ( (unsigned int)VmlIsDebugTraceEnabled(v69) )
          {
            v70 = 0x4000;
            if ( g_BreakOnChildAssert )
              v70 = 0;
            VmlDebugTrace(
              v70,
              L"%hs(%u) : assertion failed : %hs\n",
              "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
              803,
              "MemoryPressure.GuestVisiblePhysicalPages >= m_MemoryPressure.GuestVisiblePhysicalPages");
          }
        }
        if ( a2[2] <= *(_QWORD *)(a1 + 168) )
          goto LABEL_7;
        v71 = 0x4000;
        if ( g_BreakOnChildAssert )
          v71 = 0;
        if ( !(unsigned int)VmlIsDebugTraceEnabled(v71) )
          goto LABEL_7;
        v29 = 804;
      }
      else
      {
        if ( v8 != 2 )
          goto LABEL_7;
        if ( v7 > *(_QWORD *)(a1 + 160) )
        {
          v72 = 0x4000;
          if ( g_BreakOnChildAssert )
            v72 = 0;
          if ( (unsigned int)VmlIsDebugTraceEnabled(v72) )
          {
            v73 = 0x4000;
            if ( g_BreakOnChildAssert )
              v73 = 0;
            VmlDebugTrace(
              v73,
              L"%hs(%u) : assertion failed : %hs\n",
              "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
              808,
              "MemoryPressure.ActualTotalPhysicalPages <= m_MemoryPressure.ActualTotalPhysicalPages");
          }
        }
        if ( v5 > *(_QWORD *)(a1 + 152) )
        {
          v74 = 0x4000;
          if ( g_BreakOnChildAssert )
            v74 = 0;
          if ( (unsigned int)VmlIsDebugTraceEnabled(v74) )
          {
            v75 = 0x4000;
            if ( g_BreakOnChildAssert )
              v75 = 0;
            VmlDebugTrace(
              v75,
              L"%hs(%u) : assertion failed : %hs\n",
              "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
              809,
              "MemoryPressure.GuestVisiblePhysicalPages <= m_MemoryPressure.GuestVisiblePhysicalPages");
          }
        }
        if ( a2[2] <= *(_QWORD *)(a1 + 168) )
          goto LABEL_7;
        v76 = 0x4000;
        if ( g_BreakOnChildAssert )
          v76 = 0;
        if ( !(unsigned int)VmlIsDebugTraceEnabled(v76) )
          goto LABEL_7;
        v29 = 810;
      }
      if ( g_BreakOnChildAssert )
        v6 = 0;
      v28 = "MemoryPressure.UnbackedPhysicalPages <= m_MemoryPressure.UnbackedPhysicalPages";
    }
    else
    {
      if ( v7 != *(_QWORD *)(a1 + 160) )
      {
        v63 = 0x4000;
        if ( g_BreakOnChildAssert )
          v63 = 0;
        if ( (unsigned int)VmlIsDebugTraceEnabled(v63) )
        {
          v64 = 0x4000;
          if ( g_BreakOnChildAssert )
            v64 = 0;
          VmlDebugTrace(
            v64,
            L"%hs(%u) : assertion failed : %hs\n",
            "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
            796,
            "MemoryPressure.ActualTotalPhysicalPages == m_MemoryPressure.ActualTotalPhysicalPages");
        }
      }
      if ( v5 != *(_QWORD *)(a1 + 152) )
      {
        v65 = 0x4000;
        if ( g_BreakOnChildAssert )
          v65 = 0;
        if ( (unsigned int)VmlIsDebugTraceEnabled(v65) )
        {
          v66 = 0x4000;
          if ( g_BreakOnChildAssert )
            v66 = 0;
          VmlDebugTrace(
            v66,
            L"%hs(%u) : assertion failed : %hs\n",
            "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
            797,
            "MemoryPressure.GuestVisiblePhysicalPages == m_MemoryPressure.GuestVisiblePhysicalPages");
        }
      }
      if ( a2[2] == *(_QWORD *)(a1 + 168) )
        goto LABEL_7;
      v27 = 0x4000;
      if ( g_BreakOnChildAssert )
        v27 = 0;
      if ( !(unsigned int)VmlIsDebugTraceEnabled(v27) )
        goto LABEL_7;
      if ( g_BreakOnChildAssert )
        v6 = 0;
      v28 = "MemoryPressure.UnbackedPhysicalPages == m_MemoryPressure.UnbackedPhysicalPages";
      v29 = 798;
    }
    VmlDebugTrace(
      v6,
      L"%hs(%u) : assertion failed : %hs\n",
      "onecore\\vm\\compute\\management\\resources\\dm\\lib\\dmvirtualnumanode.cpp",
      v29,
      v28);
  }
LABEL_7:
  v9 = 0;
  v86 = 0;
  v10 = *(_QWORD *)(a1 + 392);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v10 + 96LL))(v10, &v86);
    v9 = v86;
  }
  v11 = (unsigned __int8 *)(a1 + 350);
  v12 = (unsigned __int8 *)(a1 + 349);
  if ( *(_DWORD *)(a1 + 240) == -1 )
  {
    LODWORD(v82) = 1;
    *(_DWORD *)(a1 + 240) = 0;
    v83 = v9;
    v77 = DmVirtualNumaNode::DmOperationStatusToString(0);
    DmBalancerTrace::DmVirtualNumaNodeOperationStatusSet(
      (DmBalancerTrace *)&v83,
      (struct _GUID *)*v12,
      *v11,
      *(_BYTE *)(a1 + 351),
      v77,
      L"DmVirtualNumaNode::ReportStatisticsVm - First report",
      v82);
    v9 = v86;
  }
  if ( !*(_DWORD *)(a1 + 240) && v8 )
  {
    *(_QWORD *)(a1 + 240) = 1;
    *(_QWORD *)(a1 + 296) = 0;
    *(_QWORD *)&v83 = a1 + 349;
    v84 = v9;
    v78 = DmVirtualNumaNode::DmOperationStatusToString(1);
    DmBalancerTrace::DmVirtualNumaNodeOperationStatusSet(
      (DmBalancerTrace *)&v84,
      (struct _GUID *)*v79,
      *(_BYTE *)(a1 + 350),
      *(_BYTE *)(a1 + 351),
      v78,
      L"DmVirtualNumaNode::ReportStatisticsVm - COM call timeouts and DM operation starts",
      v82);
    v9 = v86;
  }
  else
  {
    *(_QWORD *)&v83 = a1 + 349;
  }
  if ( !*(_DWORD *)(a1 + 240) )
  {
    if ( a2[2] || *((_DWORD *)a2 + 7) || a2[5] )
    {
      *(_QWORD *)&v83 = a1 + 349;
    }
    else
    {
      *(_DWORD *)(a1 + 240) = -1;
      *(_QWORD *)&v83 = a1 + 349;
      v84 = v9;
      v80 = DmVirtualNumaNode::DmOperationStatusToString(0xFFFFFFFFLL);
      DmBalancerTrace::DmVirtualNumaNodeOperationStatusSet(
        (DmBalancerTrace *)&v84,
        (struct _GUID *)*v81,
        *(_BYTE *)(a1 + 350),
        *(_BYTE *)(a1 + 351),
        v80,
        L"DmVirtualNumaNode::ReportStatisticsVm - SLP pages backed and no memory report from the guest yet",
        v82);
      v9 = v86;
    }
  }
  if ( v8 )
  {
    if ( v7 != *(_QWORD *)(a1 + 160) || a2[2] != *(_QWORD *)(a1 + 168) )
    {
      *(_DWORD *)(a1 + 260) = 0;
      *(_DWORD *)(a1 + 340) = 1;
    }
    *(_QWORD *)&v83 = a1 + 349;
    if ( v8 == 3 )
    {
      *(_QWORD *)(a1 + 408) = 0;
      *(_QWORD *)(a1 + 416) = 0;
      *(_QWORD *)(a1 + 424) = 0;
      *(_QWORD *)(a1 + 432) = 0;
      *(_DWORD *)(a1 + 240) = 0;
      *(_DWORD *)(a1 + 340) = 1;
      v84 = v9;
      v44 = DmVirtualNumaNode::DmOperationStatusToString(0);
      DmBalancerTrace::DmVirtualNumaNodeOperationStatusSet(
        (DmBalancerTrace *)&v84,
        (struct _GUID *)*v12,
        *v11,
        *v45,
        v44,
        L"DmVirtualNumaNode::ReportStatisticsVm - DmOperationReset",
        v82);
    }
  }
  if ( !*(_DWORD *)(a1 + 240) )
    *(_DWORD *)(a1 + 340) = 1;
  *(_OWORD *)(a1 + 152) = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 168) = *((_OWORD *)a2 + 1);
  *(_OWORD *)(a1 + 184) = *((_OWORD *)a2 + 2);
  *(_OWORD *)(a1 + 200) = *((_OWORD *)a2 + 3);
  *(_QWORD *)(a1 + 216) = a2[8];
  v13 = *(_QWORD *)(a1 + 160);
  if ( *(_QWORD *)(a1 + 168) )
  {
    if ( v13 < 0 )
    {
      v42 = *(_QWORD *)(a1 + 160) & 1LL | ((unsigned __int64)v13 >> 1);
      v30 = (double)(int)v42 + (double)(int)v42;
    }
    else
    {
      v30 = (double)(int)v13;
    }
    v31 = v30 * 4.0;
    v32 = 0;
    if ( v30 * 4.0 >= 9.223372036854776e18 )
    {
      v31 = v31 - 9.223372036854776e18;
      if ( v31 < 9.223372036854776e18 )
        v32 = 0x8000000000000000uLL;
    }
    v33 = v32 + (unsigned int)(int)v31;
    v34 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 136);
    if ( v34 )
      EnterCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 136));
    *(_QWORD *)(a1 + 120) = v13;
    *(_QWORD *)(a1 + 128) = v33;
    if ( v33 < 0 )
      v35 = (double)(int)(v33 & 1 | ((unsigned __int64)v33 >> 1))
          + (double)(int)(v33 & 1 | ((unsigned __int64)v33 >> 1));
    else
      v35 = (double)(int)v33;
    v36 = v35 / v30;
    *(double *)(a1 + 80) = v36;
    if ( (_DWORD)v82 )
    {
      *(double *)(a1 + 88) = v36;
      v39 = v36 * 0.0025 * 20.0;
    }
    else
    {
      v37 = (v36 - *(double *)(a1 + 88)) * 0.09523809523809523 + *(double *)(a1 + 88);
      *(double *)(a1 + 88) = v37;
      v38 = v37 - v36;
      v36 = v37;
      v39 = v38 * v38 + *(double *)(a1 + 96) * 0.9047619047619048;
    }
    *(double *)(a1 + 96) = v39;
    v40 = v36 * 0.0001 * 20.0;
    if ( v40 <= v39 )
      v40 = v39;
    else
      *(double *)(a1 + 96) = v40;
    *(double *)(a1 + 104) = sqrt(v40 / 19.0);
    if ( v34 )
      LeaveCriticalSection(v34);
    v14 = (__int64 *)(a1 + 192);
  }
  else
  {
    v14 = (__int64 *)(a1 + 192);
    v15 = *(_QWORD *)(a1 + 192);
    if ( v15 )
    {
      v16 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 136);
      if ( v16 )
        EnterCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 136));
      *(_QWORD *)(a1 + 120) = v13;
      *(_QWORD *)(a1 + 128) = v15;
      v17 = 0;
      if ( v15 < 0 )
        v18 = (double)(int)(v15 & 1 | ((unsigned __int64)v15 >> 1))
            + (double)(int)(v15 & 1 | ((unsigned __int64)v15 >> 1));
      else
        v18 = (double)(int)v15;
      if ( v13 < 0 )
        v19 = (double)(int)(v13 & 1 | ((unsigned __int64)v13 >> 1))
            + (double)(int)(v13 & 1 | ((unsigned __int64)v13 >> 1));
      else
        v19 = (double)(int)v13;
      v17.m128d_f64[0] = v18 / v19;
      *(double *)(a1 + 80) = v17.m128d_f64[0];
      if ( (_DWORD)v82 )
      {
        *(double *)(a1 + 88) = v17.m128d_f64[0];
        v21.m128d_f64[1] = v17.m128d_f64[1];
        v21.m128d_f64[0] = v17.m128d_f64[0] * 0.0025 * 20.0;
      }
      else
      {
        v20.m128d_f64[1] = v17.m128d_f64[1];
        v20.m128d_f64[0] = (v17.m128d_f64[0] - *(double *)(a1 + 88)) * 0.09523809523809523 + *(double *)(a1 + 88);
        *(double *)(a1 + 88) = v20.m128d_f64[0];
        v21.m128d_f64[1] = v17.m128d_f64[1];
        v21.m128d_f64[0] = v20.m128d_f64[0] - v17.m128d_f64[0];
        v17 = v20;
        v21.m128d_f64[0] = v21.m128d_f64[0] * v21.m128d_f64[0] + *(double *)(a1 + 96) * 0.9047619047619048;
      }
      *(double *)(a1 + 96) = v21.m128d_f64[0];
      v17.m128d_f64[0] = v17.m128d_f64[0] * 0.0001 * 20.0;
      if ( v17.m128d_f64[0] <= v21.m128d_f64[0] )
        v17 = v21;
      else
        *(double *)(a1 + 96) = v17.m128d_f64[0];
      v17.m128d_f64[0] = v17.m128d_f64[0] / 19.0;
      if ( v17.m128d_f64[0] < 0.0 )
        v22 = sqrt(v17.m128d_f64[0]);
      else
        *(_QWORD *)&v22 = *(_OWORD *)&_mm_sqrt_pd(v17);
      *(double *)(a1 + 104) = v22;
      if ( v16 )
        LeaveCriticalSection(v16);
    }
    else
    {
      PressureBasedBalancedObject::SetCommittedMemory((PressureBasedBalancedObject *)a1, *(_QWORD *)(a1 + 160), 0, 1);
    }
  }
  v23 = *v14;
  if ( *v14 )
  {
    v24 = *(_QWORD *)(a1 + 160);
    if ( v24 < 0 )
    {
      v43 = *(_QWORD *)(a1 + 160) & 1LL | ((unsigned __int64)v24 >> 1);
      v25 = (double)(int)v43 + (double)(int)v43;
    }
    else
    {
      v25 = (double)(int)v24;
    }
    if ( v23 < 0 )
      v26 = (double)(int)(*(_DWORD *)v14 & 1 | ((unsigned __int64)v23 >> 1))
          + (double)(int)(*(_DWORD *)v14 & 1 | ((unsigned __int64)v23 >> 1));
    else
      v26 = (double)(int)v23;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 392) + 80LL))(
      *(_QWORD *)(a1 + 392),
      (unsigned int)(int)((v25 - v26) / v25 * 100.0),
      (unsigned int)(int)((v25 - v26)
                        / v25
                        * 100.0
                        * v25
                        / 100.0
                        * 100.0
                        / ((100.0 - (v25 - v26) / v25 * 100.0)
                         * v25
                         / 100.0
                         * (double)SHIDWORD(v88)
                         / 100.0)),
      *(unsigned int *)(a1 + 180));
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**(_QWORD **)(a1 + 392) + 80LL))(
      *(_QWORD *)(a1 + 392),
      0x7FFFFFFF,
      0x7FFFFFFF,
      *(unsigned int *)(a1 + 180));
  }
  Vml::VmPerfTraceComponent::UpdateTracingEnabled((Vml::VmPerfTraceComponent *)&g_DynMemPerfTrace);
  if ( g_DynMemPerfTrace && *(_QWORD *)(a1 + 472) && !*(_BYTE *)v83 )
  {
    v46 = PressureBasedBalancedObject::GetCurrentPressure((PressureBasedBalancedObject *)a1) * 100.0;
    v47 = 0;
    if ( v46 >= 9.223372036854776e18 )
    {
      v46 = v46 - 9.223372036854776e18;
      if ( v46 < 9.223372036854776e18 )
        v47 = 0x8000000000000000uLL;
    }
    *(_QWORD *)&v83 = v47 + (unsigned int)(int)v46;
    v48 = (const unsigned __int16 *)(a1 + 456);
    if ( *(_QWORD *)(a1 + 480) <= 7u )
      v49 = (const unsigned __int16 *)(a1 + 456);
    else
      v49 = *(const unsigned __int16 **)v48;
    v82 = v49;
    Vml::VmPerfTraceComponent::LogEvent<unsigned short const *,unsigned __int64>(
      v47,
      MSVCOMP_VM_MEMORY_PRESSURE,
      &v82,
      &v83);
    *(_QWORD *)&v83 = *v14;
    if ( *(_QWORD *)(a1 + 480) <= 7u )
      v51 = (const unsigned __int16 *)(a1 + 456);
    else
      v51 = *(const unsigned __int16 **)v48;
    v82 = v51;
    Vml::VmPerfTraceComponent::LogEvent<unsigned short const *,unsigned __int64>(
      v50,
      MSVCOMP_VM_MEMORY_PRESSURE_COMMITED,
      &v82,
      &v83);
    *(_QWORD *)&v83 = *(_QWORD *)(a1 + 184);
    if ( *(_QWORD *)(a1 + 480) <= 7u )
      v53 = (const unsigned __int16 *)(a1 + 456);
    else
      v53 = *(const unsigned __int16 **)v48;
    v82 = v53;
    Vml::VmPerfTraceComponent::LogEvent<unsigned short const *,unsigned __int64>(
      v52,
      MSVCOMP_VM_MEMORY_PRESSURE_AVAILABLE,
      &v82,
      &v83);
    *(_QWORD *)&v83 = *(_QWORD *)(a1 + 160);
    if ( *(_QWORD *)(a1 + 480) <= 7u )
      v55 = (const unsigned __int16 *)(a1 + 456);
    else
      v55 = *(const unsigned __int16 **)v48;
    v82 = v55;
    Vml::VmPerfTraceComponent::LogEvent<unsigned short const *,unsigned __int64>(
      v54,
      MSVCOMP_VM_MEMORY_PRESSURE_ACTUAL,
      &v82,
      &v83);
    *(_QWORD *)&v83 = *(_QWORD *)(a1 + 152);
    if ( *(_QWORD *)(a1 + 480) > 7u )
      v48 = *(const unsigned __int16 **)v48;
    v82 = v48;
    Vml::VmPerfTraceComponent::LogEvent<unsigned short const *,unsigned __int64>(
      v56,
      MSVCOMP_VM_MEMORY_PRESSURE_GUEST_VISIBLE,
      &v82,
      &v83);
  }
  if ( v4 )
    LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x14003a3c0  mov     rax, rsp
0x14003a3c3  push    rbp
0x14003a3c4  push    rbx
0x14003a3c5  push    rsi
0x14003a3c6  push    rdi
0x14003a3c7  push    r12
0x14003a3c9  push    r13
0x14003a3cb  push    r14
0x14003a3cd  push    r15
0x14003a3cf  lea     rbp, [rax-5Fh]
0x14003a3d3  sub     rsp, 0F8h
0x14003a3da  movaps  xmmword ptr [rax-58h], xmm6
0x14003a3de  movaps  xmmword ptr [rax-68h], xmm7
0x14003a3e2  mov     rax, cs:__security_cookie
0x14003a3e9  xor     rax, rsp
0x14003a3ec  mov     [rbp+57h+var_70], rax
0x14003a3f0  mov     rdi, rdx
0x14003a3f3  mov     rbx, rcx
0x14003a3f6  mov     dword ptr [rsp+130h+var_100], 0; unsigned __int16 *
0x14003a3fe  xorps   xmm0, xmm0
0x14003a401  movups  [rbp+57h+var_D0], xmm0
0x14003a405  mov     r15, [rcx+130h]
0x14003a40c  lea     rax, ??_7VmAutoLock@Vml@@6B@; const Vml::VmAutoLock::`vftable'
0x14003a413  mov     qword ptr [rbp+57h+var_D0], rax
0x14003a417  mov     qword ptr [rbp+57h+var_D0+8], r15
0x14003a41b  test    r15, r15
0x14003a41e  jz      short loc_14003A430
0x14003a420  mov     rcx, r15; lpCriticalSection
0x14003a423  call    cs:__imp_EnterCriticalSection
0x14003a42a  nop     dword ptr [rax+rax+00h]
0x14003a42f  nop
0x14003a430  xorps   xmm0, xmm0
0x14003a433  movups  [rbp+57h+var_B0], xmm0
0x14003a437  movups  [rbp+57h+var_A0], xmm0
0x14003a43b  movups  [rbp+57h+var_90], xmm0
0x14003a43f  movups  [rbp+57h+var_80], xmm0
0x14003a443  mov     rcx, [rbx+188h]
0x14003a44a  mov     rax, [rcx]
0x14003a44d  lea     rdx, [rbp+57h+var_B0]
0x14003a451  mov     rax, [rax+68h]
0x14003a455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a45a  mov     r14, [rdi]
0x14003a45d  mov     r13d, 4000h
0x14003a463  test    r14, r14
0x14003a466  jz      loc_14003AC52
0x14003a46c  mov     r12, [rdi+8]
0x14003a470  test    r12, r12
0x14003a473  jz      loc_14003ACA5
0x14003a479  mov     esi, [rdi+18h]
0x14003a47c  cmp     esi, 3
0x14003a47f  jz      short loc_14003A49C
0x14003a481  mov     rcx, [rbx+188h]
0x14003a488  mov     rax, [rcx]
0x14003a48b  mov     rax, [rax+78h]
0x14003a48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a494  test    eax, eax
0x14003a496  jnz     loc_14003A7A1
0x14003a49c  xorps   xmm0, xmm0
0x14003a49f  movaps  [rbp+57h+var_C0], xmm0
0x14003a4a3  mov     rcx, [rbx+188h]
0x14003a4aa  test    rcx, rcx
0x14003a4ad  jz      short loc_14003A4C3
0x14003a4af  mov     rax, [rcx]
0x14003a4b2  lea     rdx, [rbp+57h+var_C0]
0x14003a4b6  mov     rax, [rax+60h]
0x14003a4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a4bf  movaps  xmm0, [rbp+57h+var_C0]
0x14003a4c3  lea     r13, [rbx+15Eh]
0x14003a4ca  lea     r14, [rbx+15Dh]
0x14003a4d1  cmp     dword ptr [rbx+0F0h], 0FFFFFFFFh
0x14003a4d8  jz      loc_14003AFEB
0x14003a4de  lea     r8, [rbx+15Fh]
0x14003a4e5  cmp     dword ptr [rbx+0F0h], 0
0x14003a4ec  jnz     short loc_14003A4F6
0x14003a4ee  test    esi, esi
0x14003a4f0  jnz     loc_14003B03F
0x14003a4f6  mov     qword ptr [rsp+130h+var_F8+8], r14
0x14003a4fb  cmp     dword ptr [rbx+0F0h], 0
0x14003a502  jnz     short loc_14003A521
0x14003a504  cmp     qword ptr [rdi+10h], 0
0x14003a509  jnz     short loc_14003A51C
0x14003a50b  cmp     dword ptr [rdi+1Ch], 0
0x14003a50f  jnz     short loc_14003A51C
0x14003a511  cmp     qword ptr [rdi+28h], 0
0x14003a516  jz      loc_14003B0B0
0x14003a51c  mov     qword ptr [rsp+130h+var_F8+8], r14
0x14003a521  test    esi, esi
0x14003a523  jnz     loc_14003B115
0x14003a529  cmp     dword ptr [rbx+0F0h], 0
0x14003a530  jnz     short loc_14003A53C
0x14003a532  mov     dword ptr [rbx+154h], 1
0x14003a53c  movaps  xmm0, xmmword ptr [rdi]
0x14003a53f  movups  xmmword ptr [rbx+98h], xmm0
0x14003a546  movaps  xmm1, xmmword ptr [rdi+10h]
0x14003a54a  movups  xmmword ptr [rbx+0A8h], xmm1
0x14003a551  movaps  xmm0, xmmword ptr [rdi+20h]
0x14003a555  movups  xmmword ptr [rbx+0B8h], xmm0
0x14003a55c  movaps  xmm1, xmmword ptr [rdi+30h]
0x14003a560  movups  xmmword ptr [rbx+0C8h], xmm1
0x14003a567  movsd   xmm0, qword ptr [rdi+40h]
0x14003a56c  movsd   qword ptr [rbx+0D8h], xmm0
0x14003a574  mov     rsi, [rbx+0A0h]
0x14003a57b  mov     r13, 8000000000000000h
0x14003a585  movsd   xmm7, cs:__real@43e0000000000000
0x14003a58d  cmp     qword ptr [rbx+0A8h], 0
0x14003a595  ja      loc_14003A81A
0x14003a59b  lea     r12, [rbx+0C0h]
0x14003a5a2  mov     rdi, [r12]
0x14003a5a6  test    rdi, rdi
0x14003a5a9  jz      loc_14003B17A
0x14003a5af  mov     r14, [rbx+88h]
0x14003a5b6  test    r14, r14
0x14003a5b9  jz      short loc_14003A5CA
0x14003a5bb  mov     rcx, r14; lpCriticalSection
0x14003a5be  call    cs:__imp_EnterCriticalSection
0x14003a5c5  nop     dword ptr [rax+rax+00h]
0x14003a5ca  mov     [rbx+78h], rsi
0x14003a5ce  mov     [rbx+80h], rdi
0x14003a5d5  xorps   xmm2, xmm2
0x14003a5d8  test    rdi, rdi
0x14003a5db  js      loc_14003A9ED
0x14003a5e1  cvtsi2sd xmm2, rdi
0x14003a5e6  xorps   xmm0, xmm0
0x14003a5e9  test    rsi, rsi
0x14003a5ec  js      loc_14003AA07
0x14003a5f2  cvtsi2sd xmm0, rsi
0x14003a5f7  divsd   xmm2, xmm0
0x14003a5fb  movsd   qword ptr [rbx+50h], xmm2
0x14003a600  movsd   xmm4, cs:__real@4034000000000000
0x14003a608  cmp     dword ptr [rsp+130h+var_100], 0
0x14003a60d  jnz     loc_14003B161
0x14003a613  movaps  xmm1, xmm2
0x14003a616  subsd   xmm1, qword ptr [rbx+58h]
0x14003a61b  mulsd   xmm1, cs:__real@3fb8618618618618
0x14003a623  addsd   xmm1, qword ptr [rbx+58h]
0x14003a628  movsd   qword ptr [rbx+58h], xmm1
0x14003a62d  movaps  xmm3, xmm1
0x14003a630  subsd   xmm3, xmm2
0x14003a634  movaps  xmm2, xmm1
0x14003a637  mulsd   xmm3, xmm3
0x14003a63b  movsd   xmm0, qword ptr [rbx+60h]
0x14003a640  mulsd   xmm0, cs:__real@3fecf3cf3cf3cf3d
0x14003a648  addsd   xmm3, xmm0
0x14003a64c  movsd   qword ptr [rbx+60h], xmm3
0x14003a651  mulsd   xmm2, cs:__real@3f1a36e2eb1c432d
0x14003a659  mulsd   xmm2, xmm4
0x14003a65d  comisd  xmm2, xmm3
0x14003a661  jbe     loc_14003A9A6
0x14003a667  movsd   qword ptr [rbx+60h], xmm2
0x14003a66c  divsd   xmm2, cs:__real@4033000000000000
0x14003a674  xorps   xmm0, xmm0
0x14003a677  ucomisd xmm0, xmm2
0x14003a67b  ja      loc_14003AA21
0x14003a681  sqrtpd  xmm0, xmm2
0x14003a685  movsd   qword ptr [rbx+68h], xmm0
0x14003a68a  test    r14, r14
0x14003a68d  jz      short loc_14003A69E
0x14003a68f  mov     rcx, r14; lpCriticalSection
0x14003a692  call    cs:__imp_LeaveCriticalSection
0x14003a699  nop     dword ptr [rax+rax+00h]
0x14003a69e  mov     rcx, [r12]
0x14003a6a2  movsd   xmm6, cs:__real@4059000000000000
0x14003a6aa  test    rcx, rcx
0x14003a6ad  jz      loc_14003A934
0x14003a6b3  mov     rdx, [rbx+0A0h]
0x14003a6ba  xorps   xmm0, xmm0
0x14003a6bd  test    rdx, rdx
0x14003a6c0  js      loc_14003AA2E
0x14003a6c6  cvtsi2sd xmm0, rdx
0x14003a6cb  xorps   xmm1, xmm1
0x14003a6ce  test    rcx, rcx
0x14003a6d1  js      loc_14003AA48
0x14003a6d7  cvtsi2sd xmm1, rcx
0x14003a6dc  movaps  xmm3, xmm0
0x14003a6df  subsd   xmm3, xmm1
0x14003a6e3  divsd   xmm3, xmm0
0x14003a6e7  mulsd   xmm3, xmm6
0x14003a6eb  mov     rcx, [rbx+188h]
0x14003a6f2  mov     r10, [rcx]
0x14003a6f5  movaps  xmm2, xmm3
0x14003a6f8  mulsd   xmm2, xmm0
0x14003a6fc  divsd   xmm2, xmm6
0x14003a700  mulsd   xmm2, xmm6
0x14003a704  movaps  xmm1, xmm6
0x14003a707  subsd   xmm1, xmm3
0x14003a70b  mulsd   xmm1, xmm0
0x14003a70f  divsd   xmm1, xmm6
0x14003a713  mov     eax, dword ptr [rbp+57h+var_A0+0Ch]
0x14003a716  xorps   xmm0, xmm0
0x14003a719  cvtsi2sd xmm0, rax
0x14003a71e  mulsd   xmm1, xmm0
0x14003a722  divsd   xmm1, xmm6
0x14003a726  divsd   xmm2, xmm1
0x14003a72a  cvttsd2si r8d, xmm2
0x14003a72f  cvttsd2si edx, xmm3
0x14003a733  mov     rax, [r10+50h]
0x14003a737  mov     r9d, [rbx+0B4h]
0x14003a73e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a743  lea     rcx, ?g_DynMemPerfTrace@@3VVmPerfTraceComponent@Vml@@A; this
0x14003a74a  call    ?UpdateTracingEnabled@VmPerfTraceComponent@Vml@@AEAAXXZ; Vml::VmPerfTraceComponent::UpdateTracingEnabled(void)
0x14003a74f  cmp     cs:?g_DynMemPerfTrace@@3VVmPerfTraceComponent@Vml@@A, 0; Vml::VmPerfTraceComponent g_DynMemPerfTrace
0x14003a756  jnz     loc_14003AAED
0x14003a75c  test    r15, r15
0x14003a75f  jz      short loc_14003A770
0x14003a761  mov     rcx, r15; lpCriticalSection
0x14003a764  call    cs:__imp_LeaveCriticalSection
0x14003a76b  nop     dword ptr [rax+rax+00h]
0x14003a770  mov     rcx, [rbp+57h+var_70]
0x14003a774  xor     rcx, rsp; StackCookie
0x14003a777  call    __security_check_cookie
0x14003a77c  movaps  xmm6, [rsp+130h+var_58+8]
0x14003a784  movaps  xmm7, [rsp+130h+var_68+8]
0x14003a78c  add     rsp, 0F8h
0x14003a793  pop     r15
0x14003a795  pop     r14
0x14003a797  pop     r13
0x14003a799  pop     r12
0x14003a79b  pop     rdi
0x14003a79c  pop     rsi
0x14003a79d  pop     rbx
0x14003a79e  pop     rbp
0x14003a79f  retn
0x14003a7a1  cmp     dword ptr [rbx+0F0h], 0FFFFFFFFh
0x14003a7a8  jz      loc_14003A94F
0x14003a7ae  test    esi, esi
0x14003a7b0  jnz     loc_14003ADF1
0x14003a7b6  cmp     r12, [rbx+0A0h]
0x14003a7bd  jnz     loc_14003AD4B
0x14003a7c3  cmp     r14, [rbx+98h]
0x14003a7ca  jnz     loc_14003AD9E
0x14003a7d0  mov     rax, [rbx+0A8h]
0x14003a7d7  cmp     [rdi+10h], rax
0x14003a7db  jz      loc_14003A49C
0x14003a7e1  xor     eax, eax
0x14003a7e3  mov     ecx, r13d
0x14003a7e6  cmp     cs:?g_BreakOnChildAssert@@3HA, eax; int g_BreakOnChildAssert
0x14003a7ec  cmovnz  ecx, eax
0x14003a7ef  call    VmlIsDebugTraceEnabled
0x14003a7f4  test    eax, eax
0x14003a7f6  jz      loc_14003A49C
0x14003a7fc  xor     eax, eax
0x14003a7fe  cmp     cs:?g_BreakOnChildAssert@@3HA, eax; int g_BreakOnChildAssert
0x14003a804  cmovnz  r13d, eax
0x14003a808  lea     rax, aMemorypressure_2; "MemoryPressure.UnbackedPhysicalPages =="...
0x14003a80f  mov     r9d, 31Eh
0x14003a815  jmp     loc_14003AFCB
0x14003a81a  xorps   xmm6, xmm6
0x14003a81d  test    rsi, rsi
0x14003a820  js      loc_14003A9B6
0x14003a826  cvtsi2sd xmm6, rsi
0x14003a82b  movaps  xmm0, xmm6
0x14003a82e  mulsd   xmm0, cs:__real@4010000000000000
0x14003a836  xor     eax, eax
0x14003a838  comisd  xmm0, xmm7
0x14003a83c  jb      short loc_14003A84B
0x14003a83e  subsd   xmm0, xmm7
0x14003a842  comisd  xmm0, xmm7
0x14003a846  jnb     short loc_14003A84B
0x14003a848  mov     rax, r13
0x14003a84b  cvttsd2si rdi, xmm0
0x14003a850  add     rdi, rax
0x14003a853  mov     r14, [rbx+88h]
0x14003a85a  test    r14, r14
0x14003a85d  jz      short loc_14003A86E
0x14003a85f  mov     rcx, r14; lpCriticalSection
0x14003a862  call    cs:__imp_EnterCriticalSection
0x14003a869  nop     dword ptr [rax+rax+00h]
0x14003a86e  mov     [rbx+78h], rsi
0x14003a872  mov     [rbx+80h], rdi
0x14003a879  xorps   xmm2, xmm2
0x14003a87c  test    rdi, rdi
0x14003a87f  js      loc_14003A9D3
0x14003a885  cvtsi2sd xmm2, rdi
0x14003a88a  divsd   xmm2, xmm6
0x14003a88e  movsd   qword ptr [rbx+50h], xmm2
0x14003a893  movsd   xmm4, cs:__real@4034000000000000
0x14003a89b  cmp     dword ptr [rsp+130h+var_100], 0
0x14003a8a0  jnz     loc_14003B148
0x14003a8a6  movaps  xmm1, xmm2
0x14003a8a9  subsd   xmm1, qword ptr [rbx+58h]
0x14003a8ae  mulsd   xmm1, cs:__real@3fb8618618618618
0x14003a8b6  addsd   xmm1, qword ptr [rbx+58h]
0x14003a8bb  movsd   qword ptr [rbx+58h], xmm1
0x14003a8c0  movaps  xmm3, xmm1
0x14003a8c3  subsd   xmm3, xmm2
0x14003a8c7  movaps  xmm2, xmm1
0x14003a8ca  mulsd   xmm3, xmm3
0x14003a8ce  movsd   xmm0, qword ptr [rbx+60h]
0x14003a8d3  mulsd   xmm0, cs:__real@3fecf3cf3cf3cf3d
0x14003a8db  addsd   xmm3, xmm0
0x14003a8df  movsd   qword ptr [rbx+60h], xmm3
0x14003a8e4  mulsd   xmm2, cs:__real@3f1a36e2eb1c432d
0x14003a8ec  mulsd   xmm2, xmm4
0x14003a8f0  comisd  xmm2, xmm3
0x14003a8f4  jbe     loc_14003A9AE
0x14003a8fa  movsd   qword ptr [rbx+60h], xmm2
0x14003a8ff  divsd   xmm2, cs:__real@4033000000000000
0x14003a907  movaps  xmm0, xmm2; X
0x14003a90a  call    sqrt
0x14003a90f  movsd   qword ptr [rbx+68h], xmm0
  ... truncated ...
```
