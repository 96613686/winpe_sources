# WdcMemoryMonitor::Update(void)

- ea: `0x18000f390`
- end: `0x18000febc`
- name: `?Update@WdcMemoryMonitor@@MEAAJXZ`
- size: `2860`
- prototype: `__int64 __fastcall(WdcMemoryMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callees

- `0x1800071e0`
- `0x18000b7d0`
- `0x18000b854`
- `0x18000dff0`
- `0x18000f390`
- `0x18000fec4`
- `0x18003a3c0`
- `0x18003b064`
- `0x18003b07c`
- `0x18003b0ac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000fa9c`
- `ntdll!RtlNtStatusToDosError` at `0x18000fb18`
- `ntdll!RtlNtStatusToDosError` at `0x18000fa9c`
- `ntdll!RtlNtStatusToDosError` at `0x18000fb18`
- `ntdll!NtQuerySystemInformation` at `0x18000f3f8`
- `ntdll!NtQuerySystemInformation` at `0x18000f3f8`
- `KERNEL32!OutputDebugStringW` at `0x18000fea7`
- `KERNEL32!OutputDebugStringW` at `0x18000fea7`
- `KERNEL32!GetLastError` at `0x18000fb23`
- `KERNEL32!GetLastError` at `0x18000fb23`
- `KERNEL32!LeaveCriticalSection` at `0x18000f84f`
- `KERNEL32!LeaveCriticalSection` at `0x18000f84f`
- `KERNEL32!EnterCriticalSection` at `0x18000f459`
- `KERNEL32!EnterCriticalSection` at `0x18000f459`
- `KERNEL32!GetPhysicallyInstalledSystemMemory` at `0x18000f440`
- `KERNEL32!GetPhysicallyInstalledSystemMemory` at `0x18000f440`

## string_xrefs

- `0x18000fb3c`: `WdcMemoryMonitor::Update`

## pseudocode

```c
__int64 __fastcall WdcMemoryMonitor::Update(WdcMemoryMonitor *this)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // eax
  int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // edi
  __int64 v7; // r13
  double v8; // xmm0_8
  _DWORD *v9; // r9
  __int64 v10; // r10
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // r11
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  double v18; // xmm1_8
  double v19; // xmm1_8
  double v20; // xmm3_8
  double v21; // xmm1_8
  __int64 v22; // rdx
  __int64 v23; // rcx
  double v24; // xmm1_8
  double v25; // xmm0_8
  char *v26; // rcx
  char *v27; // rbx
  unsigned __int64 v28; // xmm11_8
  _DWORD *v29; // rdi
  __int64 v30; // r12
  int v31; // esi
  double v32; // xmm1_8
  double v33; // xmm7_8
  double v34; // xmm0_8
  double v35; // xmm2_8
  double v36; // xmm8_8
  double v37; // xmm9_8
  double v38; // xmm8_8
  double v39; // xmm8_8
  double v40; // xmm1_8
  unsigned int v42; // ecx
  double v43; // xmm2_8
  double v44; // xmm2_8
  double v45; // xmm2_8
  double v46; // xmm2_8
  double v47; // xmm0_8
  __int64 v48; // rax
  double v49; // xmm1_8
  double v50; // xmm0_8
  double v51; // xmm0_8
  double v52; // xmm1_8
  __int64 v53; // rcx
  double v54; // xmm0_8
  double v55; // xmm0_8
  double v56; // xmm1_8
  __int64 v57; // rcx
  double v58; // xmm0_8
  double v59; // xmm0_8
  double v60; // xmm1_8
  __int64 v61; // rcx
  double v62; // xmm0_8
  double v63; // xmm0_8
  double v64; // xmm1_8
  __int64 v65; // rcx
  double v66; // xmm0_8
  double v67; // xmm0_8
  double v68; // xmm1_8
  __int64 v69; // rcx
  double v70; // xmm0_8
  double v71; // xmm0_8
  double v72; // xmm1_8
  __int64 v73; // rcx
  double v74; // xmm0_8
  double v75; // xmm0_8
  double v76; // xmm1_8
  __int64 v77; // rcx
  double v78; // xmm0_8
  double v79; // xmm0_8
  double v80; // xmm1_8
  __int64 v81; // rcx
  double v82; // xmm0_8
  double v83; // xmm0_8
  double v84; // xmm1_8
  __int64 v85; // rcx
  double v86; // xmm0_8
  double v87; // xmm0_8
  double v88; // xmm1_8
  __int64 v89; // rcx
  double v90; // xmm0_8
  double v91; // xmm0_8
  double v92; // xmm1_8
  __int64 v93; // rcx
  double v94; // xmm0_8
  double v95; // xmm0_8
  double v96; // xmm1_8
  __int64 v97; // rcx
  double v98; // xmm0_8
  double v99; // xmm0_8
  double v100; // xmm1_8
  __int64 v101; // rcx
  double v102; // xmm0_8
  double v103; // xmm0_8
  double v104; // xmm1_8
  __int64 v105; // rcx
  double v106; // xmm0_8
  double v107; // xmm0_8
  double v108; // xmm3_8
  double v109; // xmm2_8
  int v110; // eax
  __int64 v111; // [rsp+60h] [rbp-A0h]
  int v112; // [rsp+70h] [rbp-90h]
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+78h] [rbp-88h] BYREF
  __int128 v114; // [rsp+80h] [rbp-80h] BYREF
  void *v115[2]; // [rsp+90h] [rbp-70h]
  __int128 SystemInformation; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v117; // [rsp+B0h] [rbp-50h]
  __int128 v118; // [rsp+C0h] [rbp-40h]
  __int64 v119; // [rsp+D0h] [rbp-30h]
  WCHAR OutputString; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v121[2046]; // [rsp+E2h] [rbp-1Eh] BYREF

  TotalMemoryInKilobytes = 0;
  v112 = 0;
  v119 = 0;
  SystemInformation = 0;
  v117 = 0;
  v118 = 0;
  v114 = 0;
  *(_OWORD *)v115 = 0;
  v2 = NtQuerySystemInformation(SystemLoadGdiDriverInSystemSpaceInformation|0x80, &SystemInformation, 0x38u, 0);
  if ( v2 )
    RtlNtStatusToDosError(v2);
  *(_QWORD *)&v114 = 0x6B7568430000002DLL;
  DWORD2(v114) = 16;
  v115[0] = 0;
  LODWORD(v115[1]) = 0;
  v3 = WdcNtQuerySystemSuperfetchInformation(&v114);
  if ( v3 )
    RtlNtStatusToDosError(v3);
  if ( !GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes) )
    GetLastError();
  if ( *((_DWORD *)this + 12) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v112 = 1;
  }
  v4 = WdcDataMonitor::Update(this);
  v6 = v4;
  if ( v4 < 0 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\memory.cpp",
      "WdcMemoryMonitor::Update",
      0,
      L"FAILURE: 0x%08x",
      v4);
  }
  else
  {
    v7 = *((unsigned int *)this + 2041);
    v8 = 0.0;
    if ( TotalMemoryInKilobytes )
      *((_QWORD *)this + 1174) = TotalMemoryInKilobytes;
    v9 = v115[0];
    *((_QWORD *)this + 1169) = SystemInformation;
    if ( v9 )
    {
      v10 = 0;
      *((_QWORD *)this + 1171) = 0;
      *((_QWORD *)this + 1172) = 0;
      *((_QWORD *)this + 1173) = 0;
      if ( v9[2] )
      {
        v11 = 0;
        v12 = 0;
        v13 = 0;
        do
        {
          v14 = 3 * v11;
          v11 = (unsigned int)(v11 + 1);
          v5 = 16 * v14;
          v10 += *(_QWORD *)((char *)v9 + v5 + 56);
          *((_QWORD *)this + 1171) = v10;
          v15 = *(_QWORD *)((char *)v9 + v5 + 24) + v12;
          *((_QWORD *)this + 1172) = v15;
          v16 = v15 + *(_QWORD *)((char *)v9 + v5 + 32);
          *((_QWORD *)this + 1172) = v16;
          v12 = v16 + *(_QWORD *)((char *)v9 + v5 + 40);
          *((_QWORD *)this + 1172) = v12;
          v13 += *(_QWORD *)((char *)v9 + v5 + 48);
          *((_QWORD *)this + 1173) = v13;
        }
        while ( (unsigned int)v11 < v9[2] );
      }
      else
      {
        v13 = 0;
        v12 = 0;
      }
      v17 = *((_QWORD *)this + 1170);
      *((_QWORD *)this + 1171) = v17 * v10;
      *((_QWORD *)this + 1172) = v17 * v12;
      *((_QWORD *)this + 1173) = v17 * v13;
    }
    if ( *((_QWORD *)&v118 + 1) )
    {
      if ( v117 < 0 )
        v18 = (double)(int)(BYTE8(v117) & 1 | (*((_QWORD *)&v117 + 1) >> 1))
            + (double)(int)(BYTE8(v117) & 1 | (*((_QWORD *)&v117 + 1) >> 1));
      else
        v18 = (double)SDWORD2(v117);
      v19 = v18 * 100.0;
      if ( v118 < 0 )
        v20 = (double)(int)(BYTE8(v118) & 1 | (*((_QWORD *)&v118 + 1) >> 1))
            + (double)(int)(BYTE8(v118) & 1 | (*((_QWORD *)&v118 + 1) >> 1));
      else
        v20 = (double)SDWORD2(v118);
      v21 = v19 / v20;
    }
    else
    {
      v21 = 0.0;
    }
    *((double *)this + v7 + 1175) = v21;
    v22 = *((_QWORD *)this + 1169);
    if ( v22 )
    {
      v23 = *((_QWORD *)this + 1171) + *((_QWORD *)this + 1172) + *((_QWORD *)this + 1173);
      if ( v23 < 0 )
        v24 = (double)(int)(v23 & 1 | ((unsigned __int64)v23 >> 1))
            + (double)(int)(v23 & 1 | ((unsigned __int64)v23 >> 1));
      else
        v24 = (double)(int)v23;
      if ( v22 < 0 )
      {
        v22 = *((_QWORD *)this + 1169) & 1LL;
        v25 = (double)(int)(v22 | (*((_QWORD *)this + 1169) >> 1))
            + (double)(int)(v22 | (*((_QWORD *)this + 1169) >> 1));
      }
      else
      {
        v25 = (double)(int)v22;
      }
      v8 = (1.0 - v24 / v25) * 100.0;
    }
    v26 = (char *)this + 88;
    *((double *)this + v7 + 1083) = (double)(int)v8;
    v27 = (char *)*((_QWORD *)this + 11);
    if ( v27 != (char *)this + 88 )
    {
      v28 = _mm_load_si128((const __m128i *)&_xmm).m128i_u64[0];
      do
      {
        if ( (unsigned int)v7 >= 0x3C )
          goto LABEL_43;
        v29 = v27 + 184;
        v30 = *((_QWORD *)v27 + 4);
        v31 = 0;
        v32 = 0.0;
        v33 = (double)*((int *)this + 2336);
        v34 = (double)(unsigned __int8)v27[v7 + 208] / 255.0 * *((double *)this + v7 + 1023);
        if ( v34 != 0.0 )
        {
          v45 = *((double *)v27 + 34);
          if ( v34 > v45 )
          {
            *((_QWORD *)v27 + 34) = 0;
LABEL_67:
            v31 = 1;
            goto LABEL_33;
          }
          v46 = v45 - v34;
          *((double *)v27 + 34) = v46;
          if ( v46 == 0.0 )
            goto LABEL_67;
        }
LABEL_33:
        if ( v33 != 0.0 )
        {
          v35 = *((double *)v27 + 24);
          if ( v35 != 0.0 )
          {
            v43 = v35 / v33 * 255.0;
            if ( COERCE_DOUBLE(*((_QWORD *)v27 + 25) & v28) >= 0.05 )
            {
              if ( *((double *)v27 + 25) < 0.0 )
                v47 = floor(v43);
              else
                v47 = o_ceil_0();
              v32 = v47;
            }
            else
            {
              if ( v43 <= 0.0 )
                v44 = v43 - 0.5;
              else
                v44 = v43 + 0.5;
              v32 = (double)(int)v44;
            }
          }
        }
        v36 = *((double *)v27 + 24);
        *((_BYTE *)v29 + v7 + 24) = (int)v32;
        v37 = *((double *)v27 + 34);
        if ( v37 != 0.0 )
        {
          if ( (unsigned __int8)(int)v32 )
          {
            *v29 = 0;
          }
          else
          {
            v42 = (*v29)++;
            if ( v42 >= 0x3C )
              goto LABEL_54;
          }
        }
        if ( !v31 )
        {
          if ( v33 != 0.0 )
          {
            v38 = v36 - v32 / 255.0 * v33;
            if ( dword_1800AE114 )
            {
              if ( byte_1800AE118 != 1 && (qword_1800AE100 & 0x800) != 0 && (qword_1800AE108 & 0x800) == qword_1800AE108 )
              {
                OutputString = 0;
                memset_0(v121, 0, sizeof(v121));
                if ( *((_DWORD *)this + 2324) == 1 )
                {
                  v49 = 0.0;
                  v5 = 0;
                  do
                  {
                    v50 = (double)*((unsigned __int8 *)v29 + v5 + 24) / 255.0;
                    if ( (_DWORD)v5 == (_DWORD)v7 )
                      v51 = v50 * v33;
                    else
                      v51 = v50 * *((double *)this + v5 + 1023);
                    v52 = v49 + v51;
                    v53 = (unsigned int)(v5 + 1);
                    v54 = (double)*((unsigned __int8 *)v29 + v53 + 24) / 255.0;
                    if ( (_DWORD)v53 == (_DWORD)v7 )
                      v55 = v54 * v33;
                    else
                      v55 = v54 * *((double *)this + v53 + 1023);
                    v56 = v52 + v55;
                    v57 = (unsigned int)(v5 + 2);
                    v58 = (double)*((unsigned __int8 *)v29 + v57 + 24) / 255.0;
                    if ( (_DWORD)v57 == (_DWORD)v7 )
                      v59 = v58 * v33;
                    else
                      v59 = v58 * *((double *)this + v57 + 1023);
                    v60 = v56 + v59;
                    v61 = (unsigned int)(v5 + 3);
                    v62 = (double)*((unsigned __int8 *)v29 + v61 + 24) / 255.0;
                    if ( (_DWORD)v61 == (_DWORD)v7 )
                      v63 = v62 * v33;
                    else
                      v63 = v62 * *((double *)this + v61 + 1023);
                    v64 = v60 + v63;
                    v65 = (unsigned int)(v5 + 4);
                    v66 = (double)*((unsigned __int8 *)v29 + v65 + 24) / 255.0;
                    if ( (_DWORD)v65 == (_DWORD)v7 )
                      v67 = v66 * v33;
                    else
                      v67 = v66 * *((double *)this + v65 + 1023);
                    v68 = v64 + v67;
                    v69 = (unsigned int)(v5 + 5);
                    v70 = (double)*((unsigned __int8 *)v29 + v69 + 24) / 255.0;
                    if ( (_DWORD)v69 == (_DWORD)v7 )
                      v71 = v70 * v33;
                    else
                      v71 = v70 * *((double *)this + v69 + 1023);
                    v72 = v68 + v71;
                    v73 = (unsigned int)(v5 + 6);
                    v74 = (double)*((unsigned __int8 *)v29 + v73 + 24) / 255.0;
                    if ( (_DWORD)v73 == (_DWORD)v7 )
                      v75 = v74 * v33;
                    else
                      v75 = v74 * *((double *)this + v73 + 1023);
                    v76 = v72 + v75;
                    v77 = (unsigned int)(v5 + 7);
                    v78 = (double)*((unsigned __int8 *)v29 + v77 + 24) / 255.0;
                    if ( (_DWORD)v77 == (_DWORD)v7 )
                      v79 = v78 * v33;
                    else
                      v79 = v78 * *((double *)this + v77 + 1023);
                    v80 = v76 + v79;
                    v81 = (unsigned int)(v5 + 8);
                    v82 = (double)*((unsigned __int8 *)v29 + v81 + 24) / 255.0;
                    if ( (_DWORD)v81 == (_DWORD)v7 )
                      v83 = v82 * v33;
                    else
                      v83 = v82 * *((double *)this + v81 + 1023);
                    v84 = v80 + v83;
                    v85 = (unsigned int)(v5 + 9);
                    v86 = (double)*((unsigned __int8 *)v29 + v85 + 24) / 255.0;
                    if ( (_DWORD)v85 == (_DWORD)v7 )
                      v87 = v86 * v33;
                    else
                      v87 = v86 * *((double *)this + v85 + 1023);
                    v88 = v84 + v87;
                    v89 = (unsigned int)(v5 + 10);
                    v90 = (double)*((unsigned __int8 *)v29 + v89 + 24) / 255.0;
                    if ( (_DWORD)v89 == (_DWORD)v7 )
                      v91 = v90 * v33;
                    else
                      v91 = v90 * *((double *)this + v89 + 1023);
                    v92 = v88 + v91;
                    v93 = (unsigned int)(v5 + 11);
                    v94 = (double)*((unsigned __int8 *)v29 + v93 + 24) / 255.0;
                    if ( (_DWORD)v93 == (_DWORD)v7 )
                      v95 = v94 * v33;
                    else
                      v95 = v94 * *((double *)this + v93 + 1023);
                    v96 = v92 + v95;
                    v97 = (unsigned int)(v5 + 12);
                    v98 = (double)*((unsigned __int8 *)v29 + v97 + 24) / 255.0;
                    if ( (_DWORD)v97 == (_DWORD)v7 )
                      v99 = v98 * v33;
                    else
                      v99 = v98 * *((double *)this + v97 + 1023);
                    v100 = v96 + v99;
                    v101 = (unsigned int)(v5 + 13);
                    v102 = (double)*((unsigned __int8 *)v29 + v101 + 24) / 255.0;
                    if ( (_DWORD)v101 == (_DWORD)v7 )
                      v103 = v102 * v33;
                    else
                      v103 = v102 * *((double *)this + v101 + 1023);
                    v104 = v100 + v103;
                    v105 = (unsigned int)(v5 + 14);
                    v106 = (double)*((unsigned __int8 *)v29 + v105 + 24) / 255.0;
                    if ( (_DWORD)v105 == (_DWORD)v7 )
                      v107 = v106 * v33;
                    else
                      v107 = v106 * *((double *)this + v105 + 1023);
                    v5 = (unsigned int)(v5 + 15);
                    v49 = v104 + v107;
                  }
                  while ( (unsigned int)v5 < 0x3C );
                  v108 = v38 + *((double *)v27 + 25);
                  *(_QWORD *)&v109 = COERCE_UNSIGNED_INT64(v108 - (v37 - v49)) & v28;
                  if ( v109 < 1.0 || (v110 = 0, v109 / v37 < 0.1) )
                    v110 = 1;
                  if ( v30 && *((_QWORD *)this + 8) == v30 || !v110 )
                  {
                    LODWORD(v111) = *((unsigned __int8 *)v29 + v7 + 24);
                    StringCchPrintfW(
                      &OutputString,
                      0x400u,
                      L"WDC: [%2d] Key 0x%08I64x Win %9.03lf His %9.03lf Dlt %9.03lf Tdt %9.03lf Err %9.03lf Cur %9.03lf T"
                       "ot %9.03lf Qtm %3d\n",
                      (unsigned int)v7,
                      v30,
                      v37,
                      v49,
                      v38,
                      v108,
                      v108 - (v37 - v49),
                      *((_QWORD *)v27 + 24),
                      v33,
                      v111);
                    OutputDebugStringW(&OutputString);
                  }
                }
              }
            }
            v39 = v38 + *((double *)v27 + 25);
            *((_QWORD *)v27 + 24) = 0;
            *((double *)v27 + 25) = v39;
          }
          goto LABEL_42;
        }
LABEL_54:
        memset_0(v27 + 184, 0, 0x58u);
        *((_QWORD *)v27 + 34) = 0;
LABEL_42:
        v26 = (char *)this + 88;
LABEL_43:
        v40 = *((double *)v27 + 34) / (double)*((unsigned __int16 *)v27 + 24);
        if ( *((double *)v27 + 14) != v40 )
        {
          *((_DWORD *)v27 + 26) |= 1u;
          *((double *)v27 + 14) = v40;
          if ( *(char **)v27 == v27 )
          {
            v48 = *(_QWORD *)v26;
            if ( *(char **)(*(_QWORD *)v26 + 8LL) != v26 )
              __fastfail(3u);
            *(_QWORD *)v27 = v48;
            *((_QWORD *)v27 + 1) = v26;
            *(_QWORD *)(v48 + 8) = v27;
            *(_QWORD *)v26 = v27;
          }
        }
        v27 = *(char **)v27;
        v6 = 0;
      }
      while ( v27 != v26 );
    }
    *((double *)this + v7 + 1023) = (double)*((int *)this + 2336);
    *((_DWORD *)this + 2336) = 0;
  }
  if ( v112 && *((_DWORD *)this + 12) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( v115[0] )
    WdcFree(v115[0], (const char *)v22, v5);
  return v6;
}

```

## disassembly

```asm
0x18000f390  push    rbp
0x18000f392  push    rdi
0x18000f393  push    r15
0x18000f395  lea     rbp, [rsp-8A0h]
0x18000f39d  sub     rsp, 9A0h
0x18000f3a4  mov     rax, cs:__security_cookie
0x18000f3ab  xor     rax, rsp
0x18000f3ae  mov     [rbp+8B0h+var_D0], rax
0x18000f3b5  xorps   xmm0, xmm0
0x18000f3b8  mov     [rsp+9B0h+TotalMemoryInKilobytes], 0
0x18000f3c1  mov     r15, rcx
0x18000f3c4  mov     [rsp+9B0h+var_940], 0
0x18000f3cc  xor     eax, eax
0x18000f3ce  lea     rdx, [rbp+8B0h+SystemInformation]; SystemInformation
0x18000f3d2  mov     ecx, 0B6h; SystemInformationClass
0x18000f3d7  mov     [rbp+8B0h+var_8E0], rax
0x18000f3db  xor     r9d, r9d; ReturnLength
0x18000f3de  mov     r8d, 38h ; '8'; SystemInformationLength
0x18000f3e4  movups  [rbp+8B0h+SystemInformation], xmm0
0x18000f3e8  movups  [rbp+8B0h+var_900], xmm0
0x18000f3ec  movups  [rbp+8B0h+var_8F0], xmm0
0x18000f3f0  movups  [rbp+8B0h+var_930], xmm0
0x18000f3f4  movups  xmmword ptr [rbp+8B0h+var_920], xmm0
0x18000f3f8  call    cs:__imp_NtQuerySystemInformation
0x18000f3fe  test    eax, eax
0x18000f400  jnz     loc_18000FB16
0x18000f406  lea     rcx, [rbp+8B0h+var_930]; SystemInformation
0x18000f40a  mov     dword ptr [rbp+8B0h+var_930], 2Dh ; '-'
0x18000f411  mov     dword ptr [rbp+8B0h+var_930+4], 6B756843h
0x18000f418  mov     dword ptr [rbp+8B0h+var_930+8], 10h
0x18000f41f  mov     [rbp+8B0h+var_920], 0
0x18000f427  mov     dword ptr [rbp+8B0h+var_920+8], 0
0x18000f42e  call    ?WdcNtQuerySystemSuperfetchInformation@@YAJPEAU_SUPERFETCH_INFORMATION@@@Z; WdcNtQuerySystemSuperfetchInformation(_SUPERFETCH_INFORMATION *)
0x18000f433  test    eax, eax
0x18000f435  jnz     loc_18000FA9A
0x18000f43b  lea     rcx, [rsp+9B0h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x18000f440  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x18000f446  test    eax, eax
0x18000f448  jz      loc_18000FB23
0x18000f44e  cmp     dword ptr [r15+30h], 0
0x18000f453  jz      short loc_18000F467
0x18000f455  lea     rcx, [r15+8]; lpCriticalSection
0x18000f459  call    cs:__imp_EnterCriticalSection
0x18000f45f  mov     [rsp+9B0h+var_940], 1
0x18000f467  mov     [rsp+9B0h+arg_8], rbx
0x18000f46f  mov     rcx, r15; this
0x18000f472  mov     [rsp+9B0h+arg_10], rsi
0x18000f47a  mov     [rsp+9B0h+arg_18], r12
0x18000f482  mov     [rsp+9B0h+var_18], r13
0x18000f48a  mov     [rsp+9B0h+var_20], r14
0x18000f492  movaps  [rsp+9B0h+var_30], xmm6
0x18000f49a  movaps  [rsp+9B0h+var_40], xmm7
0x18000f4a2  movaps  [rsp+9B0h+var_50], xmm8
0x18000f4ab  movaps  [rsp+9B0h+var_60], xmm9
0x18000f4b4  movaps  [rsp+9B0h+var_70], xmm10
0x18000f4bd  movaps  [rsp+9B0h+var_80], xmm11
0x18000f4c6  movaps  [rsp+9B0h+var_90], xmm12
0x18000f4cf  movaps  [rsp+9B0h+var_A0], xmm13
0x18000f4d8  movaps  [rsp+9B0h+var_B0], xmm14
0x18000f4e1  movaps  [rsp+9B0h+var_C0], xmm15
0x18000f4ea  call    ?Update@WdcDataMonitor@@MEAAJXZ; WdcDataMonitor::Update(void)
0x18000f4ef  mov     edi, eax
0x18000f4f1  test    eax, eax
0x18000f4f3  js      loc_18000FB2E
0x18000f4f9  mov     rax, [rsp+9B0h+TotalMemoryInKilobytes]
0x18000f4fe  xorps   xmm6, xmm6
0x18000f501  mov     r13d, [r15+1FE4h]
0x18000f508  xorps   xmm0, xmm0
0x18000f50b  test    rax, rax
0x18000f50e  jz      short loc_18000F517
0x18000f510  mov     [r15+24B0h], rax
0x18000f517  mov     r9, [rbp+8B0h+var_920]
0x18000f51b  mov     rax, qword ptr [rbp+8B0h+SystemInformation]
0x18000f51f  mov     [r15+2488h], rax
0x18000f526  test    r9, r9
0x18000f529  jz      loc_18000F5DE
0x18000f52f  xor     r10d, r10d
0x18000f532  mov     qword ptr [r15+2498h], 0
0x18000f53d  mov     qword ptr [r15+24A0h], 0
0x18000f548  mov     qword ptr [r15+24A8h], 0
0x18000f553  cmp     [r9+8], r10d
0x18000f557  jbe     loc_18000FA17
0x18000f55d  xor     ebx, ebx
0x18000f55f  xor     ecx, ecx
0x18000f561  xor     r11d, r11d
0x18000f564  lea     r8, [rbx+rbx*2]
0x18000f568  inc     ebx
0x18000f56a  shl     r8, 4
0x18000f56e  add     r10, [r8+r9+38h]
0x18000f573  mov     [r15+2498h], r10
0x18000f57a  add     rcx, [r8+r9+18h]
0x18000f57f  mov     [r15+24A0h], rcx
0x18000f586  mov     rdx, [r8+r9+20h]
0x18000f58b  add     rdx, rcx
0x18000f58e  mov     [r15+24A0h], rdx
0x18000f595  mov     rcx, [r8+r9+28h]
0x18000f59a  add     rcx, rdx
0x18000f59d  mov     [r15+24A0h], rcx
0x18000f5a4  add     r11, [r8+r9+30h]
0x18000f5a9  mov     [r15+24A8h], r11
0x18000f5b0  cmp     ebx, [r9+8]
0x18000f5b4  jb      short loc_18000F564
0x18000f5b6  mov     rax, [r15+2490h]
0x18000f5bd  imul    r10, rax
0x18000f5c1  imul    rcx, rax
0x18000f5c5  imul    r11, rax
0x18000f5c9  mov     [r15+2498h], r10
0x18000f5d0  mov     [r15+24A0h], rcx
0x18000f5d7  mov     [r15+24A8h], r11
0x18000f5de  mov     rcx, qword ptr [rbp+8B0h+var_8F0+8]
0x18000f5e2  movsd   xmm2, cs:__real@4059000000000000
0x18000f5ea  test    rcx, rcx
0x18000f5ed  jz      loc_18000FA0F
0x18000f5f3  mov     rdx, qword ptr [rbp+8B0h+var_900+8]
0x18000f5f7  xorps   xmm1, xmm1
0x18000f5fa  test    rdx, rdx
0x18000f5fd  js      loc_18000FAA7
0x18000f603  cvtsi2sd xmm1, rdx
0x18000f608  mulsd   xmm1, xmm2
0x18000f60c  xorps   xmm3, xmm3
0x18000f60f  test    rcx, rcx
0x18000f612  js      loc_18000FAC1
0x18000f618  cvtsi2sd xmm3, rcx
0x18000f61d  divsd   xmm1, xmm3
0x18000f621  movsd   qword ptr [r15+r13*8+24B8h], xmm1
0x18000f62b  mov     rdx, [r15+2488h]
0x18000f632  movsd   xmm14, cs:__real@3ff0000000000000
0x18000f63b  test    rdx, rdx
0x18000f63e  jz      short loc_18000F684
0x18000f640  mov     rcx, [r15+24A8h]
0x18000f647  xorps   xmm1, xmm1
0x18000f64a  add     rcx, [r15+24A0h]
0x18000f651  add     rcx, [r15+2498h]
0x18000f658  js      loc_18000FADB
0x18000f65e  cvtsi2sd xmm1, rcx
0x18000f663  xorps   xmm0, xmm0
0x18000f666  test    rdx, rdx
0x18000f669  js      loc_18000FAF5
0x18000f66f  cvtsi2sd xmm0, rdx
0x18000f674  divsd   xmm1, xmm0
0x18000f678  movaps  xmm0, xmm14
0x18000f67c  subsd   xmm0, xmm1
0x18000f680  mulsd   xmm0, xmm2
0x18000f684  cvttsd2si rcx, xmm0
0x18000f689  xorps   xmm0, xmm0
0x18000f68c  mov     ecx, ecx
0x18000f68e  cvtsi2sd xmm0, rcx
0x18000f693  lea     rcx, [r15+58h]
0x18000f697  movsd   qword ptr [r15+r13*8+21D8h], xmm0
0x18000f6a1  mov     rbx, [rcx]
0x18000f6a4  cmp     rbx, rcx
0x18000f6a7  jz      loc_18000F819
0x18000f6ad  movdqa  xmm11, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x18000f6b6  movsd   xmm10, cs:__real@406fe00000000000
0x18000f6bf  movsd   xmm12, cs:__real@3fa999999999999a
0x18000f6c8  movsd   xmm13, cs:__real@3fe0000000000000
0x18000f6d1  movsd   xmm15, cs:__real@3fb999999999999a
0x18000f6da  nop     word ptr [rax+rax+00h]
0x18000f6e0  cmp     r13d, 3Ch ; '<'
0x18000f6e4  jnb     loc_18000F7DE
0x18000f6ea  mov     eax, [r15+2480h]
0x18000f6f1  lea     rdi, [rbx+0B8h]
0x18000f6f8  mov     r12, [rbx+20h]
0x18000f6fc  xorps   xmm7, xmm7
0x18000f6ff  xor     esi, esi
0x18000f701  movaps  xmm1, xmm6
0x18000f704  cvtsi2sd xmm7, rax
0x18000f709  movzx   eax, byte ptr [rdi+r13+18h]
0x18000f70f  movd    xmm0, eax
0x18000f713  cvtdq2pd xmm0, xmm0
0x18000f717  divsd   xmm0, xmm10
0x18000f71c  mulsd   xmm0, qword ptr [r15+r13*8+1FF8h]
0x18000f726  ucomisd xmm6, xmm0
0x18000f72a  jp      loc_18000F97D
0x18000f730  jnz     loc_18000F97D
0x18000f736  ucomisd xmm7, xmm6
0x18000f73a  jp      short loc_18000F73E
0x18000f73c  jz      short loc_18000F753
0x18000f73e  movsd   xmm2, qword ptr [rdi+8]
0x18000f743  ucomisd xmm2, xmm6
0x18000f747  jp      loc_18000F933
0x18000f74d  jnz     loc_18000F933
0x18000f753  movsd   xmm8, qword ptr [rdi+8]
0x18000f759  movaps  xmm0, xmm1
0x18000f75c  divsd   xmm0, xmm10
0x18000f761  cvttsd2si eax, xmm1
0x18000f765  mulsd   xmm0, xmm7
0x18000f769  mov     [rdi+r13+18h], al
0x18000f76e  movsd   xmm9, qword ptr [rbx+110h]
0x18000f777  ucomisd xmm6, xmm9
0x18000f77c  jp      loc_18000F8FF
0x18000f782  jnz     loc_18000F8FF
0x18000f788  test    esi, esi
0x18000f78a  jnz     loc_18000F913
0x18000f790  ucomisd xmm7, xmm6
0x18000f794  jp      short loc_18000F798
0x18000f796  jz      short loc_18000F7DA
0x18000f798  cmp     cs:dword_1800AE114, 0
0x18000f79f  subsd   xmm8, xmm0
0x18000f7a4  jz      short loc_18000F7C0
0x18000f7a6  cmp     cs:byte_1800AE118, 1
0x18000f7ad  jz      short loc_18000F7C0
0x18000f7af  test    cs:qword_1800AE100, 800h
0x18000f7ba  jnz     loc_18000FA21
0x18000f7c0  addsd   xmm8, qword ptr [rbx+0C8h]
0x18000f7c9  mov     qword ptr [rdi+8], 0
0x18000f7d1  movsd   qword ptr [rbx+0C8h], xmm8
0x18000f7da  lea     rcx, [r15+58h]
0x18000f7de  movzx   eax, word ptr [rbx+30h]
0x18000f7e2  movsd   xmm1, qword ptr [rbx+110h]
0x18000f7ea  movd    xmm0, eax
0x18000f7ee  cvtdq2pd xmm0, xmm0
0x18000f7f2  divsd   xmm1, xmm0
0x18000f7f6  movsd   xmm0, qword ptr [rbx+70h]
0x18000f7fb  ucomisd xmm0, xmm1
0x18000f7ff  jp      loc_18000F9DD
0x18000f805  jnz     loc_18000F9DD
0x18000f80b  mov     rbx, [rbx]
0x18000f80e  xor     edi, edi
0x18000f810  cmp     rbx, rcx
0x18000f813  jnz     loc_18000F6E0
0x18000f819  mov     eax, [r15+2480h]
0x18000f820  xorps   xmm0, xmm0
0x18000f823  cvtsi2sd xmm0, rax
0x18000f828  movsd   qword ptr [r15+r13*8+1FF8h], xmm0
0x18000f832  mov     dword ptr [r15+2480h], 0
0x18000f83d  cmp     [rsp+9B0h+var_940], 0
0x18000f842  jz      short loc_18000F855
0x18000f844  cmp     dword ptr [r15+30h], 0
0x18000f849  jz      short loc_18000F855
0x18000f84b  lea     rcx, [r15+8]; lpCriticalSection
0x18000f84f  call    cs:__imp_LeaveCriticalSection
0x18000f855  mov     rcx, [rbp+8B0h+var_920]; void *
0x18000f859  test    rcx, rcx
0x18000f85c  jnz     loc_18000FEB2
0x18000f862  movaps  xmm15, [rsp+9B0h+var_C0]
0x18000f86b  mov     eax, edi
0x18000f86d  movaps  xmm14, [rsp+9B0h+var_B0]
0x18000f876  movaps  xmm13, [rsp+9B0h+var_A0]
0x18000f87f  movaps  xmm12, [rsp+9B0h+var_90]
0x18000f888  movaps  xmm11, [rsp+9B0h+var_80]
0x18000f891  movaps  xmm10, [rsp+9B0h+var_70]
0x18000f89a  movaps  xmm9, [rsp+9B0h+var_60]
0x18000f8a3  movaps  xmm8, [rsp+9B0h+var_50]
0x18000f8ac  movaps  xmm7, [rsp+9B0h+var_40]
0x18000f8b4  movaps  xmm6, [rsp+9B0h+var_30]
0x18000f8bc  mov     r14, [rsp+9B0h+var_20]
0x18000f8c4  mov     r13, [rsp+9B0h+var_18]
0x18000f8cc  mov     r12, [rsp+9B0h+arg_18]
0x18000f8d4  mov     rsi, [rsp+9B0h+arg_10]
0x18000f8dc  mov     rbx, [rsp+9B0h+arg_8]
0x18000f8e4  mov     rcx, [rbp+8B0h+var_D0]
0x18000f8eb  xor     rcx, rsp; StackCookie
0x18000f8ee  call    __security_check_cookie
0x18000f8f3  add     rsp, 9A0h
0x18000f8fa  pop     r15
0x18000f8fc  pop     rdi
0x18000f8fd  pop     rbp
0x18000f8fe  retn
0x18000f8ff  test    al, al
0x18000f901  jnz     short loc_18000F972
0x18000f903  mov     ecx, [rdi]
0x18000f905  lea     eax, [rcx+1]
0x18000f908  mov     [rdi], eax
0x18000f90a  cmp     ecx, 3Ch ; '<'
0x18000f90d  jb      loc_18000F788
0x18000f913  xor     edx, edx; Val
0x18000f915  mov     r8d, 58h ; 'X'; Size
0x18000f91b  mov     rcx, rdi; void *
0x18000f91e  call    memset_0
0x18000f923  mov     qword ptr [rbx+110h], 0
0x18000f92e  jmp     loc_18000F7DA
0x18000f933  movsd   xmm1, qword ptr [rdi+10h]
0x18000f938  divsd   xmm2, xmm7
0x18000f93c  movaps  xmm0, xmm1
0x18000f93f  andps   xmm0, xmm11
0x18000f943  mulsd   xmm2, xmm10
0x18000f948  comisd  xmm12, xmm0
0x18000f94d  jbe     short loc_18000F9A9
0x18000f94f  comisd  xmm2, xmm6
0x18000f953  jbe     loc_18000FA90
0x18000f959  addsd   xmm2, xmm13
0x18000f95e  cvttsd2si rcx, xmm2
0x18000f963  xorps   xmm1, xmm1
0x18000f966  mov     ecx, ecx
0x18000f968  cvtsi2sd xmm1, rcx
0x18000f96d  jmp     loc_18000F753
0x18000f972  mov     dword ptr [rdi], 0
0x18000f978  jmp     loc_18000F788
0x18000f97d  movsd   xmm2, qword ptr [rbx+110h]
0x18000f985  comisd  xmm0, xmm2
0x18000f989  ja      short loc_18000F9BF
0x18000f98b  subsd   xmm2, xmm0
0x18000f98f  ucomisd xmm6, xmm2
0x18000f993  movsd   qword ptr [rbx+110h], xmm2
0x18000f99b  jp      loc_18000F736
0x18000f9a1  jnz     loc_18000F736
0x18000f9a7  jmp     short loc_18000F9C6
0x18000f9a9  comisd  xmm6, xmm1
0x18000f9ad  movaps  xmm0, xmm2; X
  ... truncated ...
```
