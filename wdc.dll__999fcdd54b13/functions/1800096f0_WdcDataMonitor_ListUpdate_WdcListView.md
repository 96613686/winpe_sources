# WdcDataMonitor::ListUpdate(WdcListView *)

- ea: `0x1800096f0`
- end: `0x18000a4c0`
- name: `?ListUpdate@WdcDataMonitor@@UEAAJPEAVWdcListView@@@Z`
- size: `3536`
- prototype: `__int64 __fastcall(WdcDataMonitor *__hidden this, struct WdcListView *)`
- caller_count: `10`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001f5b0`
- `0x1800210d0`
- `0x18007eb60`
- `0x1800807a0`
- `0x180080af0`
- `0x180080ed0`
- `0x180082570`
- `0x180082870`
- `0x180082c70`
- `0x180083200`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x1800096f0`
- `0x18000b000`
- `0x18000b854`
- `0x180018ec4`
- `0x180020d2c`
- `0x18003b0ac`
- `0x180069b40`
- `0x180078350`
- `0x1800787b8`
- `0x18007990c`
- `0x180086010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a1aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a1c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a1aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a1c9`
- `KERNEL32!GetProcessHeap` at `0x180009755`
- `KERNEL32!GetProcessHeap` at `0x180009755`
- `KERNEL32!HeapAlloc` at `0x180009766`
- `KERNEL32!HeapAlloc` at `0x180009766`
- `KERNEL32!LeaveCriticalSection` at `0x1800097fe`
- `KERNEL32!LeaveCriticalSection` at `0x1800097fe`
- `KERNEL32!EnterCriticalSection` at `0x18000a151`
- `KERNEL32!EnterCriticalSection` at `0x18000a151`
- `KERNEL32!TryEnterCriticalSection` at `0x180009859`
- `KERNEL32!TryEnterCriticalSection` at `0x180009859`
- `USER32!SendMessageW` at `0x1800097c9`
- `USER32!SendMessageW` at `0x180009d32`
- `USER32!SendMessageW` at `0x180009d75`
- `USER32!SendMessageW` at `0x180009da7`
- `USER32!SendMessageW` at `0x180009dcd`
- `USER32!SendMessageW` at `0x180009fbc`
- `USER32!SendMessageW` at `0x18000a364`
- `USER32!SendMessageW` at `0x18000a4a8`
- `USER32!SendMessageW` at `0x1800097c9`
- `USER32!SendMessageW` at `0x180009d32`
- `USER32!SendMessageW` at `0x180009d75`
- `USER32!SendMessageW` at `0x180009da7`
- `USER32!SendMessageW` at `0x180009dcd`
- `USER32!SendMessageW` at `0x180009fbc`
- `USER32!SendMessageW` at `0x18000a364`
- `USER32!SendMessageW` at `0x18000a4a8`

## string_xrefs

- `0x180009fe0`: `WdcDataMonitor::ListUpdate`
- `0x18000a181`: `WdcDataMonitor::ListUpdate`
- `0x18000a06e`: `WdcDataMonitor::TraceListUpdate`
- `0x18000a0d4`: `WdcDataMonitor::TraceListDelete`

## pseudocode

```c
__int64 __fastcall WdcDataMonitor::ListUpdate(WdcDataMonitor *this, struct WdcListView *a2)
{
  int v2; // r12d
  HWND v3; // rdi
  WdcDataMonitor *v4; // r15
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rax
  const char *v7; // rdx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  unsigned __int16 *v11; // r14
  const char *v12; // rdx
  unsigned __int64 v13; // r8
  unsigned __int16 *v14; // rsi
  int v15; // eax
  unsigned int v16; // ebx
  unsigned __int64 *v18; // rsi
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // r12
  unsigned __int64 v22; // rax
  bool v23; // zf
  unsigned __int64 *v24; // r13
  unsigned int v25; // r14d
  __int64 v26; // rcx
  unsigned __int64 *v27; // rdi
  unsigned __int64 v28; // rax
  BOOL v29; // r12d
  int v30; // eax
  unsigned __int64 v31; // rdx
  int v32; // ecx
  int v33; // eax
  int v34; // edx
  _QWORD *v35; // r13
  unsigned __int64 v36; // rax
  unsigned __int64 *v37; // rbx
  unsigned int v38; // eax
  unsigned int v39; // ecx
  __int64 v40; // rdx
  int v41; // edi
  __int64 v42; // rcx
  unsigned int v43; // eax
  double v44; // xmm0_8
  double v45; // xmm1_8
  int v46; // edi
  bool v47; // sf
  unsigned int v48; // eax
  int v49; // edx
  int v50; // edi
  __int64 v51; // rcx
  unsigned int v52; // eax
  double v53; // xmm0_8
  double v54; // xmm1_8
  unsigned __int64 v55; // rax
  __int64 v56; // rax
  unsigned __int64 v57; // rdx
  __int64 v58; // rax
  unsigned __int64 v59; // rax
  unsigned __int64 v60; // rax
  __int64 v61; // rax
  HWND v62; // rsi
  int v63; // r15d
  _DWORD *v64; // rbx
  const char *v65; // rdx
  char *v66; // rsi
  char *v67; // r12
  unsigned int v68; // r14d
  int v69; // ecx
  __int64 *v70; // rdi
  const char *v71; // rdx
  int v72; // r15d
  int updated; // eax
  int v74; // ebx
  int v75; // eax
  unsigned __int16 *v76; // rax
  unsigned __int64 v77; // r9
  unsigned __int16 *v78; // rbx
  int v79; // esi
  unsigned __int16 *v80; // rax
  unsigned __int64 v81; // r9
  unsigned __int16 *v82; // rbx
  unsigned __int16 *v83; // rax
  unsigned __int64 v84; // r9
  unsigned __int16 *v85; // rbx
  __int64 v86; // rdx
  __int64 v87; // rdx
  unsigned __int64 *v88; // rcx
  unsigned __int64 v89; // rdx
  double v90; // xmm0_8
  WdcFilter *v91; // rcx
  const char *v92; // rdx
  int v93; // r8d
  const char *v94; // rdx
  int v95; // r8d
  const char *v96; // rdx
  int v97; // r8d
  struct _WDC_DATA_INFO *v98; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v99; // [rsp+38h] [rbp-C8h]
  HWND hWnd; // [rsp+40h] [rbp-C0h]
  int v101; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v102; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v103; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v104; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v105; // [rsp+68h] [rbp-98h]
  LPARAM v106[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v107[2]; // [rsp+80h] [rbp-80h] BYREF
  int lParam; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int lParam_4; // [rsp+A4h] [rbp-5Ch]
  _DWORD v110[8]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 *v111; // [rsp+C8h] [rbp-38h]
  LPARAM v112; // [rsp+100h] [rbp+0h] BYREF
  int v113; // [rsp+10Ch] [rbp+Ch]
  int v114; // [rsp+110h] [rbp+10h]
  int v117; // [rsp+1E0h] [rbp+E0h]
  unsigned __int64 v118; // [rsp+1E8h] [rbp+E8h] BYREF

  v2 = 0;
  v3 = 0;
  v117 = 0;
  v4 = this;
  v101 = 0;
  hWnd = 0;
  if ( a2 )
  {
    v3 = (HWND)(*(__int64 (__fastcall **)(struct WdcListView *))(*(_QWORD *)a2 + 360LL))(a2);
    hWnd = v3;
  }
  ProcessHeap = GetProcessHeap();
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x100u);
  v105 = v6;
  v11 = v6;
  if ( !v6 )
  {
    v14 = 0;
LABEL_161:
    v16 = -2147024882;
    LODWORD(v98) = -2147024882;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\data.cpp",
      "WdcDataMonitor::ListUpdate",
      0,
      L"FAILURE: 0x%08x",
      v98);
    goto LABEL_12;
  }
  if ( (Microsoft_Windows_Diagnosis_WDCEnableBits & 1) != 0 )
    McTemplateU0sqpp_EventWriteTransfer(v8, (_DWORD)v7, v9, v10, (char)v6, 0);
  *v11 = 0;
  v104 = (unsigned __int16 *)WdcAlloc(0x100u, v7, v9);
  v14 = v104;
  if ( !v104 )
    goto LABEL_161;
  *v104 = 0;
  if ( v3 )
  {
    SendMessageW(v3, 0xBu, 0, 0);
    v101 = 1;
  }
  v15 = *((_DWORD *)v4 + 12);
  if ( *((_DWORD *)v4 + 2330) )
  {
    if ( !v15 )
      goto LABEL_24;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8));
  }
  else if ( !v15 || !TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8)) )
  {
    v16 = -2147467259;
    goto LABEL_12;
  }
  v117 = 1;
LABEL_24:
  v16 = 0;
  v18 = (unsigned __int64 *)((char *)v4 + 88);
  v19 = 9288;
  if ( *((_DWORD *)v4 + 2324) == 1 )
    v19 = 9336;
  v20 = *(_QWORD *)((char *)v4 + v19);
  v103 = v20;
  if ( *((_DWORD *)v4 + 2332) )
  {
    v88 = (unsigned __int64 *)*v18;
    if ( (unsigned __int64 *)*v18 != v18 )
    {
      do
      {
        *((_WORD *)v88 + 26) = 0;
        *((_DWORD *)v88 + 13) &= ~0x40000000u;
        *((_DWORD *)v88 + 13) |= 1u;
        v88 = (unsigned __int64 *)*v88;
      }
      while ( v88 != v18 );
      v20 = v103;
    }
    *((_DWORD *)v4 + 2332) = 0;
  }
  v21 = *v18;
  if ( (unsigned __int64 *)*v18 != v18 )
  {
    do
    {
      v22 = *(_QWORD *)v21;
      v16 = 0;
      v23 = (*(_DWORD *)(v21 + 52) & 0x2000000) == 0;
      v118 = *(_QWORD *)v21;
      if ( v23 )
      {
        v13 = *((_QWORD *)v4 + 1163);
        if ( v13 )
        {
          v89 = 0;
          v90 = *(double *)(*(_QWORD *)(v21 + 64) + 16LL * *((unsigned __int16 *)v4 + 4663) + 8);
          if ( v90 >= 9.223372036854776e18 )
          {
            v90 = v90 - 9.223372036854776e18;
            if ( v90 < 9.223372036854776e18 )
              v89 = 0x8000000000000000uLL;
          }
          v91 = (WdcFilter *)*((_QWORD *)v4 + 1163);
          v102 = v89 + (unsigned int)(int)v90;
          v13 = (unsigned int)WdcFilter::Match(v91, (struct _PROCESS_KEY *)&v102);
          v22 = v118;
        }
        if ( !*((_QWORD *)v4 + 1163) || (_DWORD)v13 )
          *(_DWORD *)(v21 + 52) &= ~0x1000000u;
        else
          *(_DWORD *)(v21 + 52) |= 0x1000000u;
        v32 = *(_DWORD *)(v21 + 52);
        if ( *((_DWORD *)v4 + 2329) )
        {
          v33 = *(_DWORD *)(v21 + 44);
          v34 = v33 & 0xF000;
          if ( !(_DWORD)v13 )
          {
            if ( v34 == 4096 )
              goto LABEL_81;
            v35 = *(_QWORD **)(v21 + 8);
            v102 = (unsigned __int64)v35;
            *(_DWORD *)(v21 + 44) = v33 & 0xFFFF0FFF | 0x1000;
            v36 = *(_QWORD *)v21;
            *(_DWORD *)(v21 + 52) = v32 | 0x4000000;
            v37 = (unsigned __int64 *)*((_QWORD *)v4 + 12);
            if ( v36 != v21 )
            {
              if ( *(_QWORD *)(v36 + 8) != v21 || *v35 != v21 )
                goto LABEL_146;
              *v35 = v36;
              *(_QWORD *)(v36 + 8) = v35;
            }
            if ( v18 == v37 )
              goto LABEL_77;
            while ( 2 )
            {
              if ( *((_DWORD *)v4 + 2329) )
              {
                if ( *((_DWORD *)v4 + 2328) )
                {
                  v38 = (unsigned __int8)HIBYTE(*(_WORD *)(v21 + 44)) >> 4;
                  v39 = (unsigned __int8)HIBYTE(*((_WORD *)v37 + 22)) >> 4;
                  if ( v38 != v39 )
                  {
                    if ( v38 < v39 )
                      goto LABEL_76;
                    goto LABEL_75;
                  }
                }
              }
              LODWORD(v13) = 0;
              v40 = *(_QWORD *)(v21 + 64);
              v41 = *((_DWORD *)v4 + 2320);
              v42 = 16LL * *((unsigned int *)v4 + 2319);
              v43 = *(_DWORD *)(v42 + v40) & 0xF0000000;
              if ( v43 != 0x20000000 )
              {
                if ( v43 == 0x10000000 )
                {
                  v56 = *(_QWORD *)(v42 + v40 + 8);
                  v57 = v37[8];
                  if ( !v56 )
                  {
                    if ( *(_QWORD *)(v42 + v57 + 8) )
                      LODWORD(v13) = -1;
                    goto LABEL_67;
                  }
                  v86 = *(_QWORD *)(v42 + v57 + 8);
                  if ( v86 )
                  {
                    LODWORD(v13) = _o__wcsicmp(v56, v86);
                    goto LABEL_67;
                  }
                }
                else
                {
                  if ( v43 != 805306368 )
                    goto LABEL_67;
                  v59 = v37[8];
                  if ( 1.0 == *(double *)(v42 + v40 + 8) )
                  {
                    if ( 1.0 != *(double *)(v59 + v42 + 8) )
                      LODWORD(v13) = -1;
                    goto LABEL_67;
                  }
                  if ( 1.0 != *(double *)(v59 + v42 + 8) )
                    goto LABEL_64;
                }
LABEL_66:
                LODWORD(v13) = 1;
                goto LABEL_67;
              }
LABEL_64:
              v44 = *(double *)(v42 + v40 + 8);
              v45 = *(double *)(v37[8] + v42 + 8);
              if ( v45 > v44 )
              {
                LODWORD(v13) = -1;
              }
              else if ( v44 > v45 )
              {
                goto LABEL_66;
              }
LABEL_67:
              v46 = v13 * v41;
              v47 = v46 < 0;
              if ( !v46 )
              {
                v48 = *((_DWORD *)v4 + 2318);
                if ( v48 == *((_DWORD *)v4 + 2319) )
                  goto LABEL_75;
                v13 = *(_QWORD *)(v21 + 64);
                v49 = 0;
                v50 = *(char *)(*((_QWORD *)v4 + 1143) + v48);
                v51 = 16LL * v48;
                v52 = *(_DWORD *)(v51 + v13) & 0xF0000000;
                if ( v52 != 0x20000000 )
                {
                  if ( v52 == 0x10000000 )
                  {
                    v58 = *(_QWORD *)(v51 + v13 + 8);
                    v13 = v37[8];
                    if ( !v58 )
                    {
                      if ( *(_QWORD *)(v13 + v51 + 8) )
                        v49 = -1;
                      goto LABEL_73;
                    }
                    v87 = *(_QWORD *)(v13 + v51 + 8);
                    if ( v87 )
                    {
                      v49 = _o__wcsicmp(v58, v87);
                      goto LABEL_73;
                    }
                  }
                  else
                  {
                    if ( v52 != 805306368 )
                      goto LABEL_73;
                    v60 = v37[8];
                    if ( 1.0 == *(double *)(v51 + v13 + 8) )
                    {
                      if ( 1.0 != *(double *)(v60 + v51 + 8) )
                        v49 = -1;
                      goto LABEL_73;
                    }
                    if ( 1.0 != *(double *)(v60 + v51 + 8) )
                      goto LABEL_70;
                  }
LABEL_72:
                  v49 = 1;
                  goto LABEL_73;
                }
LABEL_70:
                v53 = *(double *)(v51 + v13 + 8);
                v54 = *(double *)(v37[8] + v51 + 8);
                if ( v54 > v53 )
                {
                  v49 = -1;
                }
                else if ( v53 > v54 )
                {
                  goto LABEL_72;
                }
LABEL_73:
                v47 = v49 * v50 < 0;
              }
              if ( v47 )
                goto LABEL_76;
LABEL_75:
              v37 = (unsigned __int64 *)v37[1];
              if ( v18 == v37 )
              {
LABEL_76:
                v35 = (_QWORD *)v102;
LABEL_77:
                v55 = *v37;
                if ( *(unsigned __int64 **)(*v37 + 8) == v37 )
                {
                  *(_QWORD *)v21 = v55;
                  *(_QWORD *)(v21 + 8) = v37;
                  *(_QWORD *)(v55 + 8) = v21;
                  *v37 = v21;
                  if ( v35 != *(_QWORD **)(v21 + 8) )
                    *(_DWORD *)(v21 + 52) |= 2u;
                  v16 = 0;
                  goto LABEL_81;
                }
LABEL_146:
                __fastfail(3u);
              }
              continue;
            }
          }
          if ( v34 != 0x2000 )
          {
            *(_DWORD *)(v21 + 52) = v32 | 0x4000000;
            *(_DWORD *)(v21 + 44) = v33 & 0xFFFF0FFF | 0x2000;
            WdcDataMonitor::InfoSort(v4, v21 - 16, v13, 0x8000000000000000uLL);
          }
LABEL_81:
          v22 = v118;
        }
        *(_DWORD *)(v21 + 52) |= 0x2000000u;
      }
      v21 = v22;
    }
    while ( (unsigned __int64 *)v22 != v18 );
    v20 = v103;
  }
  v24 = (unsigned __int64 *)*v18;
  v25 = 0;
  LODWORD(v118) = 0;
  while ( v24 != v18 )
  {
    v26 = v24[7];
    v27 = v24 - 2;
    v24 = (unsigned __int64 *)*v24;
    if ( v26 <= 0 || v20 < v26 )
      v28 = 0;
    else
      v28 = v20 - v26;
    v29 = !*((_DWORD *)v4 + 2330)
       && (v28 > 0x232AAF80
        || (*(unsigned int (__fastcall **)(WdcDataMonitor *, unsigned __int64 *))(*(_QWORD *)v4 + 112LL))(v4, v27));
    LODWORD(v13) = *((_DWORD *)v27 + 17);
    if ( (v13 & 0x20000002) != 0 || (v30 = 0, (v13 & 0x1000000) != 0) && !*((_DWORD *)v4 + 2328) )
      v30 = 1;
    v31 = v27[10];
    if ( (*(_DWORD *)(v31 + 16LL * *((unsigned __int16 *)v4 + 4662)) & 0x10000000) != 0
      && !*(_QWORD *)(v31 + 16LL * *((unsigned __int16 *)v4 + 4662) + 8) )
    {
      v30 = 1;
    }
    if ( !v29 && !v30 )
    {
      if ( (v13 & 0x40000000) != 0 )
        LODWORD(v118) = ++v25;
      goto LABEL_49;
    }
    memset_0(&lParam, 0, 0x58u);
    *(_OWORD *)v106 = 0;
    v61 = *(_QWORD *)a2;
    memset(v107, 0, 24);
    v62 = (HWND)(*(__int64 (__fastcall **)(struct WdcListView *))(v61 + 360))(a2);
    if ( v62 && (*((_DWORD *)v27 + 17) & 0x40000000) != 0 )
    {
      memset_0(v110, 0, 0x50u);
      lParam_4 = v25;
      lParam = 4;
      SendMessageW(v62, 0x104Bu, 0, (LPARAM)&lParam);
      if ( v111 == v27 )
      {
        v63 = v25;
LABEL_110:
        v64 = (_DWORD *)v27 + 15;
        if ( v27 != (unsigned __int64 *)-60LL )
        {
          *v64 &= 0xFFFFFFFC;
          *v64 |= SendMessageW(v62, 0x102Cu, v63, 3);
          if ( (*(_BYTE *)v64 & 1) != 0 )
          {
            memset_0(&v112, 0, 0x58u);
            v114 = 1;
            v113 = 0;
            SendMessageW(v62, 0x102Bu, v63, (LPARAM)&v112);
          }
          v25 = v118;
        }
        SendMessageW(v62, 0x1008u, v63, 0);
        *((_DWORD *)v27 + 17) &= ~0x40000000u;
        v102 = 0;
        if ( dword_1800AE114
          && (unsigned __int8)(byte_1800AE118 - 1) > 2u
          && (qword_1800AE100 & 0x400) != 0
          && (qword_1800AE108 & 0x400) == qword_1800AE108 )
        {
          v79 = *((_DWORD *)a2 + 128);
          v80 = (unsigned __int16 *)WdcAlloc(0x800u, v65, v13);
          v82 = v80;
          if ( v80 )
          {
            *v80 = 0;
            WdcDataMonitor::GetItemContentString(this, (struct _WDC_DATA_INFO *)v27, v80, v81, &v102);
            if ( (Microsoft_Windows_Diagnosis_WDCEnableBits & 2) != 0 )
              McTemplateU0qqqz_EventWriteTransfer(
                (unsigned int)WDC_PROVIDER_GUID_Context,
                (unsigned int)WDC_EVENT_LIST_DELETE,
                v79,
                v63,
                *((_DWORD *)v27 + 15),
                (__int64)v82);
            WdcFree(v82, v92, v93);
          }
          else
          {
            LODWORD(v98) = -2147024882;
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mon\\data.cpp",
              "WdcDataMonitor::TraceListDelete",
              0,
              L"FAILURE: 0x%08x",
              v98);
          }
        }
      }
      else
      {
        LODWORD(v106[0]) = 1;
        *(LPARAM *)((char *)v106 + 4) = 0;
        HIDWORD(v106[1]) = 0;
        *(_QWORD *)&v107[0] = v27;
        *(_OWORD *)((char *)v107 + 8) = 0;
        v63 = SendMessageW(v62, 0x1053u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)v106);
        if ( v63 != -1 )
          goto LABEL_110;
      }
      v4 = this;
    }
    v16 = 0;
    if ( v29 )
      (*(void (__fastcall **)(WdcDataMonitor *, unsigned __int64 *, _QWORD))(*(_QWORD *)v4 + 16LL))(
        v4,
        v27,
        *((unsigned int *)v27 + 14));
    v18 = (unsigned __int64 *)((char *)v4 + 88);
LABEL_49:
    v20 = v103;
  }
  v66 = (char *)*((_QWORD *)v4 + 11);
  v67 = (char *)v4 + 88;
  v3 = hWnd;
  v68 = 0;
  while ( v66 != v67 )
  {
    v69 = *((_DWORD *)v66 + 13);
    v70 = (__int64 *)(v66 - 16);
    if ( (v69 & 0x20000000) != 0
      || (v69 & 0x1000000) != 0 && !*((_DWORD *)v4 + 2328)
      || (v71 = (const char *)v70[10], (*(_DWORD *)&v71[16 * *((unsigned __int16 *)v4 + 4662)] & 0x10000000) != 0)
      && !*(_QWORD *)&v71[16 * *((unsigned __int16 *)v4 + 4662) + 8] )
    {
      v3 = hWnd;
    }
    else
    {
      v118 = 0;
      v72 = *((_DWORD *)a2 + 128);
      if ( (v69 & 0x40000000) != 0 )
      {
        if ( dword_1800AE114
          && (unsigned __int8)(byte_1800AE118 - 1) > 2u
          && (qword_1800AE100 & 0x400) != 0
          && (qword_1800AE108 & 0x400) == qword_1800AE108 )
        {
          v76 = (unsigned __int16 *)WdcAlloc(0x800u, v71, v13);
          v78 = v76;
          if ( v76 )
          {
            *v76 = 0;
            WdcDataMonitor::GetItemContentString(this, (struct _WDC_DATA_INFO *)(v66 - 16), v76, v77, &v118);
            if ( (Microsoft_Windows_Diagnosis_WDCEnableBits & 2) != 0 )
              McTemplateU0qqqz_EventWriteTransfer(
                (unsigned int)WDC_PROVIDER_GUID_Context,
                (unsigned int)WDC_EVENT_LIST_UPDATE,
                v72,
                v68,
                *((_DWORD *)v70 + 15),
                (__int64)v78);
            WdcFree(v78, v96, v97);
          }
          else
          {
            LODWORD(v98) = -2147024882;
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mon\\data.cpp",
              "WdcDataMonitor::TraceListUpdate",
              0,
              L"FAILURE: 0x%08x",
              v98);
          }
        }
      }
      else
      {
        if ( dword_1800AE114
          && (unsigned __int8)(byte_1800AE118 - 1) > 2u
          && (qword_1800AE100 & 0x400) != 0
          && (qword_1800AE108 & 0x400) == qword_1800AE108 )
        {
          v83 = (unsigned __int16 *)WdcAlloc(0x800u, v71, v13);
          v85 = v83;
          if ( v83 )
          {
            *v83 = 0;
            WdcDataMonitor::GetItemContentString(this, (struct _WDC_DATA_INFO *)(v66 - 16), v83, v84, &v118);
            if ( (Microsoft_Windows_Diagnosis_WDCEnableBits & 2) != 0 )
              McTemplateU0qqqz_EventWriteTransfer(
                (unsigned int)WDC_PROVIDER_GUID_Context,
                (unsigned int)WDC_EVENT_LIST_INSERT,
                v72,
                v68,
                *((_DWORD *)v70 + 15),
                (__int64)v85);
            WdcFree(v85, v94, v95);
          }
          else
          {
            LODWORD(v98) = -2147024882;
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mon\\data.cpp",
              "WdcDataMonitor::TraceListInsert",
              0,
              L"FAILURE: 0x%08x",
              v98);
          }
        }
        if ( hWnd )
        {
          v74 = *((_DWORD *)v70 + 15);
          memset_0(&lParam, 0, 0x58u);
          v75 = 12;
          v110[2] = 3;
          v110[1] = v74;
          v110[0] = 0;
          lParam_4 = v68;
          if ( !v74 )
            v75 = 4;
          v111 = (unsigned __int64 *)(v66 - 16);
          lParam = v75;
          SendMessageW(hWnd, 0x104Du, 0, (LPARAM)&lParam);
          *((_DWORD *)v70 + 17) |= 0x40000000u;
        }
        *((_DWORD *)v70 + 17) |= 1u;
      }
      v4 = this;
      v3 = hWnd;
      updated = WdcDataMonitor::ListUpdateRow(
                  this,
                  hWnd,
                  (struct WdcListView *)((char *)a2 + 408),
                  v68,
                  (struct _WDC_DATA_INFO *)(v66 - 16),
                  v105,
                  v104,
                  v99);
      v16 = updated;
      if ( updated < 0 )
      {
        LODWORD(v98) = updated;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\data.cpp",
          "WdcDataMonitor::ListUpdate",
          0,
          L"FAILURE: 0x%08x",
          v98);
        goto LABEL_145;
      }
      ++v68;
    }
    v66 = *(char **)v66;
  }
  WdcDataMonitor::DebugDumpCheck(v4, v3);
LABEL_145:
  v14 = v104;
  v11 = v105;
  v2 = v117;
LABEL_12:
  if ( *((_DWORD *)v4 + 12) && v2 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8));
  if ( v101 )
    SendMessageW(v3, 0xBu, 1u, 0);
  if ( v11 )
    WdcFree(v11, v12, v13);
  if ( v14 )
    WdcFree(v14, v12, v13);
  return v16;
}

```

## disassembly

```asm
0x1800096f0  mov     [rsp-8+arg_8], rdx
0x1800096f5  mov     [rsp-8+arg_0], rcx
0x1800096fa  push    rbp
0x1800096fb  push    rdi
0x1800096fc  push    r12
0x1800096fe  push    r13
0x180009700  push    r14
0x180009702  push    r15
0x180009704  lea     rbp, [rsp-98h]
0x18000970c  sub     rsp, 198h
0x180009713  xor     r12d, r12d
0x180009716  xor     edi, edi
0x180009718  mov     [rbp+0C0h+arg_10], r12d
0x18000971f  mov     r15, rcx
0x180009722  mov     [rsp+1C0h+var_178], r12d
0x180009727  mov     [rsp+1C0h+hWnd], rdi
0x18000972c  test    rdx, rdx
0x18000972f  jnz     loc_18000A1F7
0x180009735  mov     [rsp+1C0h+var_30], rbx
0x18000973d  mov     [rsp+1C0h+var_38], rsi
0x180009745  movaps  [rsp+1C0h+var_50], xmm6
0x18000974d  movaps  [rsp+1C0h+var_60], xmm7
0x180009755  call    cs:__imp_GetProcessHeap
0x18000975b  xor     edx, edx; dwFlags
0x18000975d  mov     r8d, 100h; dwBytes
0x180009763  mov     rcx, rax; hHeap
0x180009766  call    cs:__imp_HeapAlloc
0x18000976c  mov     [rsp+1C0h+var_158], rax
0x180009771  mov     r14, rax
0x180009774  mov     r13d, 1
0x18000977a  test    rax, rax
0x18000977d  jz      loc_18000A16C
0x180009783  test    cs:Microsoft_Windows_Diagnosis_WDCEnableBits, r13b
0x18000978a  jnz     loc_18000A216
0x180009790  xor     eax, eax
0x180009792  mov     ecx, 100h; dwBytes
0x180009797  mov     [r14], ax
0x18000979b  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800097a0  mov     [rsp+1C0h+var_160], rax
0x1800097a5  mov     rsi, rax
0x1800097a8  test    rax, rax
0x1800097ab  jz      loc_18000A16E
0x1800097b1  xor     eax, eax
0x1800097b3  mov     [rsi], ax
0x1800097b6  test    rdi, rdi
0x1800097b9  jz      short loc_1800097D4
0x1800097bb  xor     r9d, r9d; lParam
0x1800097be  xor     r8d, r8d; wParam
0x1800097c1  mov     edx, 0Bh; Msg
0x1800097c6  mov     rcx, rdi; hWnd
0x1800097c9  call    cs:__imp_SendMessageW
0x1800097cf  mov     [rsp+1C0h+var_178], r13d
0x1800097d4  mov     eax, [r15+30h]
0x1800097d8  cmp     [r15+2468h], r12d
0x1800097df  jnz     loc_18000A145
0x1800097e5  test    eax, eax
0x1800097e7  jnz     short loc_180009855
0x1800097e9  mov     ebx, 80004005h
0x1800097ee  cmp     dword ptr [r15+30h], 0
0x1800097f3  jz      short loc_180009804
0x1800097f5  test    r12d, r12d
0x1800097f8  jz      short loc_180009804
0x1800097fa  lea     rcx, [r15+8]; lpCriticalSection
0x1800097fe  call    cs:__imp_LeaveCriticalSection
0x180009804  cmp     [rsp+1C0h+var_178], 0
0x180009809  jnz     loc_18000A49A
0x18000980f  test    r14, r14
0x180009812  jnz     loc_18000A020
0x180009818  test    rsi, rsi
0x18000981b  jnz     loc_18000A4B3
0x180009821  movaps  xmm7, [rsp+1C0h+var_60]
0x180009829  mov     eax, ebx
0x18000982b  mov     rbx, [rsp+1C0h+var_30]
0x180009833  movaps  xmm6, [rsp+1C0h+var_50]
0x18000983b  mov     rsi, [rsp+1C0h+var_38]
0x180009843  add     rsp, 198h
0x18000984a  pop     r15
0x18000984c  pop     r14
0x18000984e  pop     r13
0x180009850  pop     r12
0x180009852  pop     rdi
0x180009853  pop     rbp
0x180009854  retn
0x180009855  lea     rcx, [r15+8]; lpCriticalSection
0x180009859  call    cs:__imp_TryEnterCriticalSection
0x18000985f  test    eax, eax
0x180009861  jz      short loc_1800097E9
0x180009863  mov     [rbp+0C0h+arg_10], r13d
0x18000986a  xor     ebx, ebx
0x18000986c  lea     rsi, [r15+58h]
0x180009870  cmp     [r15+2450h], r13d
0x180009877  mov     ecx, 2478h
0x18000987c  mov     eax, 2448h
0x180009881  cmovz   eax, ecx
0x180009884  mov     rax, [rax+r15]
0x180009888  mov     [rsp+1C0h+var_168], rax
0x18000988d  cmp     [r15+2470h], ebx
0x180009894  jnz     loc_18000A22E
0x18000989a  mov     r12, [rsi]
0x18000989d  cmp     r12, rsi
0x1800098a0  jz      short loc_1800098E9
0x1800098a2  movsd   xmm7, cs:__real@43e0000000000000
0x1800098aa  mov     r9, 8000000000000000h
0x1800098b4  movsd   xmm6, cs:__real@3ff0000000000000
0x1800098bc  nop     dword ptr [rax+00h]
0x1800098c0  mov     rax, [r12]
0x1800098c4  xor     ebx, ebx
0x1800098c6  test    dword ptr [r12+34h], 2000000h
0x1800098cf  mov     [rbp+0C0h+arg_18], rax
0x1800098d6  jz      loc_1800099C3
0x1800098dc  mov     r12, rax
0x1800098df  cmp     rax, rsi
0x1800098e2  jnz     short loc_1800098C0
0x1800098e4  mov     rax, [rsp+1C0h+var_168]
0x1800098e9  mov     r13, [rsi]
0x1800098ec  xor     r14d, r14d
0x1800098ef  mov     dword ptr [rbp+0C0h+arg_18], r14d
0x1800098f6  cmp     r13, rsi
0x1800098f9  jz      loc_180009E4A
0x1800098ff  mov     rcx, [r13+38h]
0x180009903  lea     rdi, [r13-10h]
0x180009907  mov     r13, [r13+0]
0x18000990b  test    rcx, rcx
0x18000990e  jle     loc_180009CAE
0x180009914  cmp     rax, rcx
0x180009917  jl      loc_180009CAE
0x18000991d  sub     rax, rcx
0x180009920  cmp     dword ptr [r15+2468h], 0
0x180009928  jnz     short loc_180009950
0x18000992a  cmp     rax, 232AAF80h
0x180009930  ja      loc_180009E3F
0x180009936  mov     rax, [r15]
0x180009939  mov     rdx, rdi
0x18000993c  mov     rcx, r15
0x18000993f  mov     rax, [rax+70h]
0x180009943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009948  test    eax, eax
0x18000994a  jnz     loc_180009E3F
0x180009950  xor     r12d, r12d
0x180009953  mov     r8d, [rdi+44h]
0x180009957  test    r8d, 20000002h
0x18000995e  jnz     loc_18000A32C
0x180009964  xor     eax, eax
0x180009966  bt      r8d, 18h
0x18000996b  jb      loc_18000A31F
0x180009971  movzx   ecx, word ptr [r15+246Ch]
0x180009979  mov     rdx, [rdi+50h]
0x18000997d  add     rcx, rcx
0x180009980  test    dword ptr [rdx+rcx*8], 10000000h
0x180009987  jz      short loc_180009997
0x180009989  cmp     qword ptr [rdx+rcx*8+8], 0
0x18000998f  mov     ecx, 1
0x180009994  cmovz   eax, ecx
0x180009997  test    r12d, r12d
0x18000999a  jnz     loc_180009CB5
0x1800099a0  test    eax, eax
0x1800099a2  jnz     loc_180009CB5
0x1800099a8  bt      r8d, 1Eh
0x1800099ad  jnb     short loc_1800099B9
0x1800099af  inc     r14d
0x1800099b2  mov     dword ptr [rbp+0C0h+arg_18], r14d
0x1800099b9  mov     rax, [rsp+1C0h+var_168]
0x1800099be  jmp     loc_1800098F6
0x1800099c3  mov     r8, [r15+2458h]
0x1800099ca  test    r8, r8
0x1800099cd  jnz     loc_18000A260
0x1800099d3  cmp     [r15+2458h], rbx
0x1800099da  jnz     loc_18000A2BE
0x1800099e0  and     dword ptr [r12+34h], 0FEFFFFFFh
0x1800099e9  mov     ecx, [r12+34h]
0x1800099ee  cmp     [r15+2464h], ebx
0x1800099f5  jz      loc_180009B9F
0x1800099fb  mov     eax, [r12+2Ch]
0x180009a00  mov     edx, eax
0x180009a02  and     edx, 0F000h
0x180009a08  test    r8d, r8d
0x180009a0b  jnz     loc_18000A2D5
0x180009a11  cmp     edx, 1000h
0x180009a17  jz      loc_180009B98
0x180009a1d  mov     r13, [r12+8]
0x180009a22  and     eax, 0FFFF1FFFh
0x180009a27  bts     eax, 0Ch
0x180009a2b  mov     [rsp+1C0h+var_170], r13
0x180009a30  mov     [r12+2Ch], eax
0x180009a35  bts     ecx, 1Ah
0x180009a39  mov     rax, [r12]
0x180009a3d  mov     [r12+34h], ecx
0x180009a42  mov     rbx, [r15+60h]
0x180009a46  cmp     rax, r12
0x180009a49  jnz     loc_18000A1D6
0x180009a4f  cmp     rsi, rbx
0x180009a52  jz      loc_180009B6E
0x180009a58  mov     r13d, 1
0x180009a5e  xchg    ax, ax
0x180009a60  cmp     dword ptr [r15+2464h], 0
0x180009a68  jz      short loc_180009A97
0x180009a6a  cmp     dword ptr [r15+2460h], 0
0x180009a72  jz      short loc_180009A97
0x180009a74  mov     eax, [r12+2Ch]
0x180009a79  mov     ecx, [rbx+2Ch]
0x180009a7c  shr     eax, 0Ch
0x180009a7f  shr     ecx, 0Ch
0x180009a82  and     eax, 0Fh
0x180009a85  and     ecx, 0Fh
0x180009a88  cmp     eax, ecx
0x180009a8a  jz      short loc_180009A97
0x180009a8c  jb      loc_180009B5F
0x180009a92  jmp     loc_180009B52
0x180009a97  mov     ecx, [r15+243Ch]
0x180009a9e  xor     r8d, r8d
0x180009aa1  mov     rdx, [r12+40h]
0x180009aa6  mov     edi, [r15+2440h]
0x180009aad  shl     rcx, 4
0x180009ab1  mov     eax, [rcx+rdx]
0x180009ab4  and     eax, 0F0000000h
0x180009ab9  cmp     eax, 20000000h
0x180009abe  jnz     loc_180009BBF
0x180009ac4  mov     rax, [rbx+40h]
0x180009ac8  movsd   xmm0, qword ptr [rcx+rdx+8]
0x180009ace  movsd   xmm1, qword ptr [rax+rcx+8]
0x180009ad4  comisd  xmm1, xmm0
0x180009ad8  ja      loc_180009BAD
0x180009ade  comisd  xmm0, xmm1
0x180009ae2  jbe     short loc_180009AE7
0x180009ae4  mov     r8d, r13d
0x180009ae7  imul    edi, r8d
0x180009aeb  test    edi, edi
0x180009aed  jnz     short loc_180009B50
0x180009aef  mov     eax, [r15+2438h]
0x180009af6  cmp     eax, [r15+243Ch]
0x180009afd  jz      short loc_180009B52
0x180009aff  mov     r8, [r12+40h]
0x180009b04  mov     ecx, eax
0x180009b06  mov     rax, [r15+23B8h]
0x180009b0d  xor     edx, edx
0x180009b0f  movsx   edi, byte ptr [rax+rcx]
0x180009b13  shl     rcx, 4
0x180009b17  mov     eax, [rcx+r8]
0x180009b1b  and     eax, 0F0000000h
0x180009b20  cmp     eax, 20000000h
0x180009b25  jnz     loc_180009BEE
0x180009b2b  mov     rax, [rbx+40h]
0x180009b2f  movsd   xmm0, qword ptr [rcx+r8+8]
0x180009b36  movsd   xmm1, qword ptr [rax+rcx+8]
0x180009b3c  comisd  xmm1, xmm0
0x180009b40  ja      short loc_180009BB8
0x180009b42  comisd  xmm0, xmm1
0x180009b46  jbe     short loc_180009B4B
0x180009b48  mov     edx, r13d
0x180009b4b  imul    edi, edx
0x180009b4e  test    edi, edi
0x180009b50  js      short loc_180009B5F
0x180009b52  mov     rbx, [rbx+8]
0x180009b56  cmp     rsi, rbx
0x180009b59  jnz     loc_180009A60
0x180009b5f  mov     r13, [rsp+1C0h+var_170]
0x180009b64  mov     r9, 8000000000000000h
0x180009b6e  mov     rax, [rbx]
0x180009b71  cmp     [rax+8], rbx
0x180009b75  jnz     loc_18000A00F
0x180009b7b  mov     [r12], rax
0x180009b7f  mov     [r12+8], rbx
0x180009b84  mov     [rax+8], r12
0x180009b88  mov     [rbx], r12
0x180009b8b  cmp     r13, [r12+8]
0x180009b90  jnz     loc_18000A314
0x180009b96  xor     ebx, ebx
0x180009b98  mov     rax, [rbp+0C0h+arg_18]
0x180009b9f  or      dword ptr [r12+34h], 2000000h
0x180009ba8  jmp     loc_1800098DC
0x180009bad  mov     r8d, 0FFFFFFFFh
0x180009bb3  jmp     loc_180009AE7
0x180009bb8  mov     edx, 0FFFFFFFFh
0x180009bbd  jmp     short loc_180009B4B
0x180009bbf  cmp     eax, 10000000h
0x180009bc4  jnz     short loc_180009C1C
0x180009bc6  mov     rax, [rcx+rdx+8]
0x180009bcb  mov     rdx, [rbx+40h]
0x180009bcf  test    rax, rax
0x180009bd2  jnz     loc_18000A199
0x180009bd8  cmp     [rcx+rdx+8], r8
0x180009bdd  jz      loc_180009AE7
0x180009be3  mov     r8d, 0FFFFFFFFh
0x180009be9  jmp     loc_180009AE7
0x180009bee  cmp     eax, 10000000h
0x180009bf3  jnz     short loc_180009C4C
0x180009bf5  mov     rax, [rcx+r8+8]
0x180009bfa  mov     r8, [rbx+40h]
0x180009bfe  test    rax, rax
0x180009c01  jnz     loc_18000A1B8
0x180009c07  cmp     [r8+rcx+8], rdx
0x180009c0c  jz      loc_180009B4B
0x180009c12  mov     edx, 0FFFFFFFFh
0x180009c17  jmp     loc_180009B4B
0x180009c1c  cmp     eax, 30000000h
0x180009c21  jnz     loc_180009AE7
0x180009c27  ucomisd xmm6, qword ptr [rcx+rdx+8]
0x180009c2d  mov     rax, [rbx+40h]
0x180009c31  jp      short loc_180009C35
0x180009c33  jz      short loc_180009C7E
  ... truncated ...
```
