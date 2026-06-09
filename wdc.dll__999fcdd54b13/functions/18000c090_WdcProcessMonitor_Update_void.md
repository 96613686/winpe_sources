# WdcProcessMonitor::Update(void)

- ea: `0x18000c090`
- end: `0x18000d493`
- name: `?Update@WdcProcessMonitor@@MEAAJXZ`
- size: `5123`
- prototype: `__int64 __fastcall(WdcProcessMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x180004a90`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x18000b9e0`
- `0x18000c090`
- `0x18000d4a0`
- `0x18000df24`
- `0x18000dff0`
- `0x18000e268`
- `0x18000e374`
- `0x180017c00`
- `0x18001c5d8`
- `0x18001e718`
- `0x18001f16c`
- `0x18003a3c0`
- `0x18003b064`
- `0x18003b07c`
- `0x18003b0ac`
- `0x180075b3c`
- `0x180075c60`

## import_xrefs

- `pdh!PdhCollectQueryData` at `0x18000cbf1`
- `pdh!PdhCollectQueryData` at `0x18000cbf1`
- `KERNEL32!OutputDebugStringW` at `0x18000d0a2`
- `KERNEL32!OutputDebugStringW` at `0x18000d419`
- `KERNEL32!OutputDebugStringW` at `0x18000d0a2`
- `KERNEL32!OutputDebugStringW` at `0x18000d419`
- `KERNEL32!LeaveCriticalSection` at `0x18000c304`
- `KERNEL32!LeaveCriticalSection` at `0x18000c304`
- `KERNEL32!EnterCriticalSection` at `0x18000c263`
- `KERNEL32!EnterCriticalSection` at `0x18000c263`

## string_xrefs

- `0x18000c2e2`: `WdcProcessMonitor::Update`
- `0x18000cd03`: `WdcProcessMonitor::Update`
- `0x18000cd2b`: `WdcProcessMonitor::Update`

## pseudocode

```c
__int64 __fastcall WdcProcessMonitor::Update(WdcProcessMonitor *this)
{
  unsigned __int64 v1; // r14
  int v2; // r13d
  struct _SYSTEM_PROCESS_INFORMATION **v4; // rsi
  _QWORD *v5; // r12
  void *v6; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // edi
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  WdcProcessMonitor *v11; // rdi
  bool v12; // zf
  int v13; // eax
  WdcTraceControl *v14; // rcx
  unsigned int v15; // ebx
  const char *v16; // rdx
  int v17; // r8d
  __int64 v19; // r13
  unsigned __int64 v20; // rcx
  char *v21; // rbx
  char *v22; // rdi
  unsigned __int64 v23; // xmm11_8
  WdcProcessMonitor *v24; // r14
  double v25; // xmm9_8
  _DWORD *v26; // rdi
  int v27; // r14d
  double v28; // xmm7_8
  double v29; // xmm2_8
  __int64 v30; // r12
  double v31; // xmm0_8
  double v32; // xmm1_8
  double v33; // xmm6_8
  double v34; // xmm8_8
  double v35; // xmm6_8
  double v36; // xmm6_8
  double v37; // xmm1_8
  _DWORD *v38; // rdi
  int v39; // r14d
  __int64 v40; // r12
  double v41; // xmm2_8
  double v42; // xmm0_8
  double v43; // xmm1_8
  double v44; // xmm6_8
  double v45; // xmm7_8
  double v46; // xmm6_8
  double v47; // xmm6_8
  double v48; // xmm1_8
  int v49; // eax
  double v50; // xmm1_8
  __int64 v51; // rax
  double v52; // xmm1_8
  double v53; // xmm1_8
  double v54; // xmm1_8
  double v55; // xmm1_8
  double v56; // xmm1_8
  double v57; // xmm1_8
  double v58; // xmm1_8
  double v59; // xmm1_8
  double v60; // xmm0_8
  double v61; // xmm0_8
  __int64 v62; // rax
  double v63; // xmm1_8
  __int64 v64; // r8
  double v65; // xmm0_8
  double v66; // xmm0_8
  double v67; // xmm1_8
  __int64 v68; // r8
  double v69; // xmm0_8
  double v70; // xmm0_8
  __int64 NextEntryOffset; // rax
  struct _SYSTEM_PROCESS_INFORMATION *v72; // rbx
  const char *v73; // rdx
  int v74; // eax
  __int64 v75; // rax
  unsigned int v76; // ecx
  struct _SYSTEM_PROCESS_INFORMATION *v77; // rdx
  unsigned int v78; // r15d
  unsigned int v79; // r8d
  int v80; // esi
  unsigned int *v81; // rax
  unsigned int *v82; // rdi
  const char *v83; // rdx
  unsigned int *v84; // r12
  __int64 v85; // rcx
  double v86; // xmm1_8
  double v87; // xmm2_8
  double v88; // xmm1_8
  __int64 v89; // rcx
  double v90; // xmm0_8
  double v91; // xmm0_8
  __int64 v92; // rcx
  double v93; // xmm1_8
  double v94; // xmm2_8
  double v95; // xmm1_8
  __int64 v96; // rcx
  double v97; // xmm0_8
  double v98; // xmm0_8
  double v99; // xmm1_8
  __int64 v100; // rcx
  double v101; // xmm0_8
  double v102; // xmm0_8
  double v103; // xmm1_8
  __int64 v104; // rcx
  double v105; // xmm0_8
  double v106; // xmm0_8
  double v107; // xmm1_8
  __int64 v108; // rcx
  double v109; // xmm0_8
  double v110; // xmm0_8
  double v111; // xmm1_8
  __int64 v112; // rcx
  double v113; // xmm0_8
  double v114; // xmm0_8
  double v115; // xmm1_8
  __int64 v116; // rcx
  double v117; // xmm0_8
  double v118; // xmm0_8
  double v119; // xmm1_8
  __int64 v120; // rcx
  double v121; // xmm0_8
  double v122; // xmm0_8
  double v123; // xmm1_8
  __int64 v124; // rcx
  double v125; // xmm0_8
  double v126; // xmm0_8
  double v127; // xmm1_8
  __int64 v128; // rcx
  double v129; // xmm0_8
  double v130; // xmm0_8
  double v131; // xmm1_8
  __int64 v132; // rcx
  double v133; // xmm0_8
  double v134; // xmm0_8
  double v135; // xmm1_8
  double v136; // xmm0_8
  double v137; // xmm0_8
  double v138; // xmm3_8
  double v139; // xmm2_8
  int v140; // eax
  double v141; // xmm1_8
  __int64 v142; // rcx
  double v143; // xmm0_8
  double v144; // xmm0_8
  double v145; // xmm1_8
  __int64 v146; // rcx
  double v147; // xmm0_8
  double v148; // xmm0_8
  double v149; // xmm1_8
  __int64 v150; // rcx
  double v151; // xmm0_8
  double v152; // xmm0_8
  double v153; // xmm1_8
  __int64 v154; // rcx
  double v155; // xmm0_8
  double v156; // xmm0_8
  double v157; // xmm1_8
  __int64 v158; // rcx
  double v159; // xmm0_8
  double v160; // xmm0_8
  double v161; // xmm1_8
  __int64 v162; // rcx
  double v163; // xmm0_8
  double v164; // xmm0_8
  double v165; // xmm1_8
  __int64 v166; // rcx
  double v167; // xmm0_8
  double v168; // xmm0_8
  double v169; // xmm1_8
  __int64 v170; // rcx
  double v171; // xmm0_8
  double v172; // xmm0_8
  double v173; // xmm1_8
  __int64 v174; // rcx
  double v175; // xmm0_8
  double v176; // xmm0_8
  double v177; // xmm1_8
  __int64 v178; // rcx
  double v179; // xmm0_8
  double v180; // xmm0_8
  __int64 v181; // rcx
  double v182; // xmm1_8
  double v183; // xmm2_8
  double v184; // xmm1_8
  __int64 v185; // rcx
  double v186; // xmm0_8
  double v187; // xmm0_8
  double v188; // xmm1_8
  __int64 v189; // rcx
  double v190; // xmm0_8
  double v191; // xmm0_8
  double v192; // xmm1_8
  double v193; // xmm2_8
  double v194; // xmm3_8
  double v195; // xmm2_8
  int v196; // eax
  double *v197; // [rsp+20h] [rbp-E0h]
  __int64 v198; // [rsp+60h] [rbp-A0h]
  __int64 i; // [rsp+78h] [rbp-88h]
  char *v201; // [rsp+78h] [rbp-88h]
  unsigned int v202; // [rsp+80h] [rbp-80h]
  int v203; // [rsp+84h] [rbp-7Ch] BYREF
  int v204; // [rsp+88h] [rbp-78h]
  int v205; // [rsp+8Ch] [rbp-74h]
  unsigned int *v206; // [rsp+90h] [rbp-70h]
  union _LARGE_INTEGER v207; // [rsp+98h] [rbp-68h]
  double v208; // [rsp+A0h] [rbp-60h] BYREF
  double v209; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v210; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v211; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v212; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v213; // [rsp+C8h] [rbp-38h] BYREF
  struct _SYSTEM_PROCESS_INFORMATION **v214; // [rsp+D0h] [rbp-30h]
  char *v215; // [rsp+D8h] [rbp-28h]
  WCHAR OutputString; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v217[2046]; // [rsp+E2h] [rbp-1Eh] BYREF

  v208 = 0.0;
  v1 = 0;
  v209 = 0.0;
  v2 = 0;
  v203 = 0;
  v207.QuadPart = 0;
  v211 = 0;
  v204 = 0;
  v210 = 0;
  v213 = 0;
  v212 = 0;
  v205 = 0;
  v206 = 0;
  v202 = 0;
  for ( i = MEMORY[0x7FFE0014]; MEMORY[0x7FFE0018] != MEMORY[0x7FFE001C]; i = MEMORY[0x7FFE0014] )
    ;
  WdcGetTimeStampCounter(&v210);
  v4 = (struct _SYSTEM_PROCESS_INFORMATION **)((char *)this + 9600);
  v5 = (_QWORD *)((char *)this + 9608);
  v214 = (struct _SYSTEM_PROCESS_INFORMATION **)((char *)this + 9600);
  v215 = (char *)this + 9608;
  if ( (int)WdcExpandingCall(
              (int (*)(struct _WDC_EXPANDING_CALL *))WdcQueryProcessInformation,
              (unsigned __int64 *)this + 1201,
              (void **)this + 1200,
              0) < 0 )
    v205 = 1;
  v6 = (void *)*((_QWORD *)this + 1687);
  if ( v6 )
    PdhCollectQueryData(v6);
  WdcGetDpcIsrCycleTime(&stru_1800B5680.CycleTime);
  v7 = MEMORY[0x7FFE0018];
  v8 = MEMORY[0x7FFE0014];
  for ( v207.QuadPart = MEMORY[0x7FFE0014]; MEMORY[0x7FFE0018] != MEMORY[0x7FFE001C]; v207.QuadPart = MEMORY[0x7FFE0014] )
  {
    v7 = MEMORY[0x7FFE0018];
    v8 = MEMORY[0x7FFE0014];
  }
  WdcGetTimeStampCounter(&v213);
  v9 = *((_QWORD *)this + 1204);
  if ( v9 )
  {
    v1 = (v8 | ((unsigned __int64)v7 << 32)) - v9;
    v211 = v1;
  }
  v10 = *((_QWORD *)this + 1334);
  v11 = this;
  *((_QWORD *)this + 1204) = i;
  if ( v10 && v213 && v213 >= v10 )
  {
    v212 = v213 - v10;
    v2 = v204;
  }
  v12 = *((_DWORD *)this + 12) == 0;
  *((_QWORD *)this + 1334) = v210;
  if ( !v12 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v2 = 1;
    v204 = 1;
  }
  v13 = WdcDataMonitor::Update(this);
  v15 = v13;
  if ( v13 < 0 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcProcessMonitor::Update",
      0,
      L"FAILURE: 0x%08x",
      v13);
    goto LABEL_19;
  }
  v19 = *((unsigned int *)this + 2041);
  if ( !v205 )
  {
    WdcTraceControl::FireEventProcessService(
      v14,
      *v4,
      v1 * *((unsigned __int16 *)this + 6793),
      v207,
      *((_DWORD *)this + 2043));
    WdcProcessMonitor::UpdateQuery(this, v19);
    v78 = 0;
    v72 = *v4;
    v210 = *((_QWORD *)v11 + 1697);
    while ( 1 )
    {
      NextEntryOffset = v72->NextEntryOffset;
      if ( !(_DWORD)NextEntryOffset )
        goto LABEL_29;
      v72 = (struct _SYSTEM_PROCESS_INFORMATION *)((char *)v72 + NextEntryOffset);
      if ( (unsigned __int64)(unsigned int)((_DWORD)v72 - *(_DWORD *)v4) > *v5 )
        goto LABEL_69;
      v203 = 0;
      WdcProcessMonitor::UpdateProcess(v11, v72, v1, v212, &v208, &v209, &v203);
      if ( v203 )
      {
        v79 = v202;
        if ( v202 >= v78 )
        {
          v80 = 2;
          if ( v78 )
            v80 = 2 * v78;
          v81 = (unsigned int *)WdcAlloc((unsigned int)(4 * v80), v73, v202);
          v82 = v81;
          if ( !v81 )
          {
            v4 = v214;
            v1 = v211;
            v11 = this;
            goto LABEL_125;
          }
          memset_0(v81, 0, (unsigned int)(4 * v80));
          v79 = v202;
          v83 = 0;
          if ( v202 )
          {
            v84 = v206;
            do
            {
              v82[(_QWORD)v83] = v84[(_QWORD)v83];
              v83 = (const char *)(unsigned int)((_DWORD)v83 + 1);
            }
            while ( (unsigned int)v83 < v202 );
            v5 = v215;
          }
          if ( v206 )
          {
            WdcFree(v206, v83, v202);
            v79 = v202;
          }
          v1 = v211;
          v78 = v80;
          v4 = v214;
          v206 = v82;
          v11 = this;
        }
        v202 = v79 + 1;
        v206[v79] = (unsigned int)v72->UniqueProcessId;
      }
LABEL_125:
      v74 = WdcMemoryMonitor::EventProcessMemory(*(WdcMemoryMonitor **)(*((_QWORD *)v11 + 1019) + 184LL), v72);
      if ( v74 < 0 )
      {
        LODWORD(v197) = v74;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp",
          "WdcTraceControl::FireEventProcessMemory",
          0,
          L"FAILURE: 0x%08x",
          v197);
      }
    }
  }
  WdcProcessMonitor::UpdateQuery(this, v19);
  v210 = *((_QWORD *)this + 1697);
LABEL_29:
  stru_1800B5680.UniqueProcessId = HANDLE_FLAG_INHERIT;
  WdcProcessMonitor::UpdateProcess(v11, &stru_1800B5680, v1, v212, &v208, &v209, &v203);
  if ( v208 > 100.0 )
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcProcessMonitor::Update",
      0,
      L"AllProcessCpuUsage: %f",
      v208);
  if ( v209 > 100.0 )
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcProcessMonitor::Update",
      0,
      L"AllProcessCycleUsage: %f",
      v209);
  v21 = (char *)*((_QWORD *)v11 + 11);
  v22 = (char *)v11 + 88;
  v201 = v22;
  if ( v21 != v22 )
  {
    v23 = _mm_load_si128((const __m128i *)&_xmm).m128i_u64[0];
    v24 = this;
    while ( 1 )
    {
      v25 = v209;
      if ( (unsigned int)v19 < 0x3C )
        break;
LABEL_47:
      v37 = *((double *)v21 + 35) / (double)*((unsigned __int16 *)v21 + 24);
      if ( *((double *)v21 + 22) != v37 )
      {
        *((_DWORD *)v21 + 42) |= 1u;
        *((double *)v21 + 22) = v37;
        if ( *(char **)v21 == v21 )
        {
          v62 = *(_QWORD *)v22;
          if ( *(char **)(*(_QWORD *)v22 + 8LL) != v22 )
            goto LABEL_127;
          *(_QWORD *)v21 = v62;
          *((_QWORD *)v21 + 1) = v22;
          *(_QWORD *)(v62 + 8) = v21;
          *(_QWORD *)v22 = v21;
        }
      }
      if ( *((double *)v21 + 30) >= 0.0 )
      {
        if ( (unsigned int)v19 >= 0x3C )
          goto LABEL_61;
        v38 = v21 + 408;
        v39 = 0;
        v40 = *((_QWORD *)v21 + 4);
        v41 = 0.0;
        v42 = (double)(unsigned __int8)v21[v19 + 432] / 255.0 * *((double *)this + v19 + 1266);
        if ( v42 != 0.0 )
        {
          v58 = *((double *)v21 + 36);
          if ( v42 > v58 )
          {
            *((_QWORD *)v21 + 36) = 0;
          }
          else
          {
            v59 = v58 - v42;
            *((double *)v21 + 36) = v59;
            if ( v59 != 0.0 )
              goto LABEL_51;
          }
          v39 = 1;
        }
LABEL_51:
        if ( v25 != 0.0 )
        {
          v43 = *((double *)v21 + 52);
          if ( v43 != 0.0 )
          {
            v54 = v43 / v25 * 255.0;
            if ( COERCE_DOUBLE(*((_QWORD *)v21 + 53) & v23) >= 0.05 )
            {
              if ( *((double *)v21 + 53) < 0.0 )
                v61 = floor(v54);
              else
                v61 = o_ceil_0();
              v41 = v61;
            }
            else
            {
              if ( v54 <= 0.0 )
                v55 = v54 - 0.5;
              else
                v55 = v54 + 0.5;
              v20 = (unsigned int)(int)v55;
              v41 = (double)(int)v20;
            }
          }
        }
        v44 = *((double *)v21 + 52);
        *((_BYTE *)v38 + v19 + 24) = (int)v41;
        v45 = *((double *)v21 + 36);
        if ( v45 == 0.0 )
        {
LABEL_54:
          if ( !v39 )
          {
            if ( v25 != 0.0 )
            {
              v46 = v44 - v41 / 255.0 * v25;
              if ( dword_1800AE114 )
              {
                if ( byte_1800AE118 != 1
                  && (qword_1800AE100 & 0x800) != 0
                  && (qword_1800AE108 & 0x800) == qword_1800AE108 )
                {
                  OutputString = 0;
                  memset_0(v217, 0, sizeof(v217));
                  if ( *((_DWORD *)this + 2324) == 1 )
                  {
                    v67 = 0.0;
                    v68 = 0;
                    do
                    {
                      v69 = (double)*((unsigned __int8 *)v38 + v68 + 24) / 255.0;
                      if ( (_DWORD)v68 == (_DWORD)v19 )
                        v70 = v69 * v25;
                      else
                        v70 = v69 * *((double *)this + v68 + 1266);
                      v141 = v67 + v70;
                      v142 = (unsigned int)(v68 + 1);
                      v143 = (double)*((unsigned __int8 *)v38 + v142 + 24) / 255.0;
                      if ( (_DWORD)v142 == (_DWORD)v19 )
                        v144 = v143 * v25;
                      else
                        v144 = v143 * *((double *)this + v142 + 1266);
                      v145 = v141 + v144;
                      v146 = (unsigned int)(v68 + 2);
                      v147 = (double)*((unsigned __int8 *)v38 + v146 + 24) / 255.0;
                      if ( (_DWORD)v146 == (_DWORD)v19 )
                        v148 = v147 * v25;
                      else
                        v148 = v147 * *((double *)this + v146 + 1266);
                      v149 = v145 + v148;
                      v150 = (unsigned int)(v68 + 3);
                      v151 = (double)*((unsigned __int8 *)v38 + v150 + 24) / 255.0;
                      if ( (_DWORD)v150 == (_DWORD)v19 )
                        v152 = v151 * v25;
                      else
                        v152 = v151 * *((double *)this + v150 + 1266);
                      v153 = v149 + v152;
                      v154 = (unsigned int)(v68 + 4);
                      v155 = (double)*((unsigned __int8 *)v38 + v154 + 24) / 255.0;
                      if ( (_DWORD)v154 == (_DWORD)v19 )
                        v156 = v155 * v25;
                      else
                        v156 = v155 * *((double *)this + v154 + 1266);
                      v157 = v153 + v156;
                      v158 = (unsigned int)(v68 + 5);
                      v159 = (double)*((unsigned __int8 *)v38 + v158 + 24) / 255.0;
                      if ( (_DWORD)v158 == (_DWORD)v19 )
                        v160 = v159 * v25;
                      else
                        v160 = v159 * *((double *)this + v158 + 1266);
                      v161 = v157 + v160;
                      v162 = (unsigned int)(v68 + 6);
                      v163 = (double)*((unsigned __int8 *)v38 + v162 + 24) / 255.0;
                      if ( (_DWORD)v162 == (_DWORD)v19 )
                        v164 = v163 * v25;
                      else
                        v164 = v163 * *((double *)this + v162 + 1266);
                      v165 = v161 + v164;
                      v166 = (unsigned int)(v68 + 7);
                      v167 = (double)*((unsigned __int8 *)v38 + v166 + 24) / 255.0;
                      if ( (_DWORD)v166 == (_DWORD)v19 )
                        v168 = v167 * v25;
                      else
                        v168 = v167 * *((double *)this + v166 + 1266);
                      v169 = v165 + v168;
                      v170 = (unsigned int)(v68 + 8);
                      v171 = (double)*((unsigned __int8 *)v38 + v170 + 24) / 255.0;
                      if ( (_DWORD)v170 == (_DWORD)v19 )
                        v172 = v171 * v25;
                      else
                        v172 = v171 * *((double *)this + v170 + 1266);
                      v173 = v169 + v172;
                      v174 = (unsigned int)(v68 + 9);
                      v175 = (double)*((unsigned __int8 *)v38 + v174 + 24) / 255.0;
                      if ( (_DWORD)v174 == (_DWORD)v19 )
                        v176 = v175 * v25;
                      else
                        v176 = v175 * *((double *)this + v174 + 1266);
                      v177 = v173 + v176;
                      v178 = (unsigned int)(v68 + 10);
                      v179 = (double)*((unsigned __int8 *)v38 + v178 + 24) / 255.0;
                      if ( (_DWORD)v178 == (_DWORD)v19 )
                        v180 = v179 * v25;
                      else
                        v180 = v179 * *((double *)this + v178 + 1266);
                      v181 = (unsigned int)(v68 + 11);
                      v182 = v177 + v180;
                      v183 = (double)*((unsigned __int8 *)v38 + v181 + 24) / 255.0;
                      if ( (_DWORD)v181 == (_DWORD)v19 )
                        v184 = v182 + v25 * v183;
                      else
                        v184 = v182 + v183 * *((double *)this + v181 + 1266);
                      v185 = (unsigned int)(v68 + 12);
                      v186 = (double)*((unsigned __int8 *)v38 + v185 + 24) / 255.0;
                      if ( (_DWORD)v185 == (_DWORD)v19 )
                        v187 = v186 * v25;
                      else
                        v187 = v186 * *((double *)this + v185 + 1266);
                      v188 = v184 + v187;
                      v189 = (unsigned int)(v68 + 13);
                      v190 = (double)*((unsigned __int8 *)v38 + v189 + 24) / 255.0;
                      if ( (_DWORD)v189 == (_DWORD)v19 )
                        v191 = v190 * v25;
                      else
                        v191 = v190 * *((double *)this + v189 + 1266);
                      v20 = (unsigned int)(v68 + 14);
                      v192 = v188 + v191;
                      v193 = (double)*((unsigned __int8 *)v38 + v20 + 24) / 255.0;
                      if ( (_DWORD)v20 == (_DWORD)v19 )
                        v67 = v192 + v25 * v193;
                      else
                        v67 = v192 + v193 * *((double *)this + v20 + 1266);
                      v68 = (unsigned int)(v68 + 15);
                    }
                    while ( (unsigned int)v68 < 0x3C );
                    v194 = v46 + *((double *)v21 + 53);
                    *(_QWORD *)&v195 = COERCE_UNSIGNED_INT64(v194 - (v45 - v67)) & v23;
                    if ( v195 < 1.0 || (v196 = 0, v195 / v45 < 0.1) )
                      v196 = 1;
                    if ( v40 && *((_QWORD *)this + 8) == v40 || !v196 )
                    {
                      LODWORD(v198) = *((unsigned __int8 *)v38 + v19 + 24);
                      StringCchPrintfW(
                        &OutputString,
                        0x400u,
                        L"WDC: [%2d] Key 0x%08I64x Win %9.03lf His %9.03lf Dlt %9.03lf Tdt %9.03lf Err %9.03lf Cur %9.03lf"
                         " Tot %9.03lf Qtm %3d\n",
                        (unsigned int)v19,
                        v40,
                        v45,
                        v67,
                        v46,
                        v194,
                        v194 - (v45 - v67),
                        *((_QWORD *)v21 + 52),
                        v25,
                        v198);
                      OutputDebugStringW(&OutputString);
                    }
                  }
                }
              }
              v47 = v46 + *((double *)v21 + 53);
              *((_QWORD *)v21 + 52) = 0;
              *((double *)v21 + 53) = v47;
            }
LABEL_60:
            v24 = this;
LABEL_61:
            v48 = *((double *)v21 + 36) / (double)*((unsigned __int16 *)v21 + 24);
            if ( *((double *)v21 + 30) == v48 )
            {
              v22 = v201;
            }
            else
            {
              *((_DWORD *)v21 + 58) |= 1u;
              v22 = v201;
              *((double *)v21 + 30) = v48;
              if ( *(char **)v21 == v21 )
              {
                v51 = *(_QWORD *)v201;
                if ( *(char **)(*(_QWORD *)v201 + 8LL) != v201 )
                  goto LABEL_127;
                *(_QWORD *)v21 = v51;
                *((_QWORD *)v21 + 1) = v201;
                *(_QWORD *)(v51 + 8) = v21;
                *(_QWORD *)v201 = v21;
              }
            }
            goto LABEL_63;
          }
        }
        else
        {
          if ( (unsigned __int8)(int)v41 )
          {
            *v38 = 0;
            goto LABEL_54;
          }
          v20 = (unsigned int)*v38;
          *v38 = v20 + 1;
          if ( (unsigned int)v20 < 0x3C )
            goto LABEL_54;
        }
        memset_0(v21 + 408, 0, 0x58u);
        *((_QWORD *)v21 + 36) = 0;
        goto LABEL_60;
      }
LABEL_63:
      v49 = *((_DWORD *)v21 + 13);
      if ( (v49 & 8) != 0 )
      {
        *((_DWORD *)v21 + 13) = v49 & 0xFFFFFFF7;
      }
      else
      {
        if ( 32213.0 != *((double *)v21 + 16) )
        {
          *((_DWORD *)v21 + 30) |= 1u;
          *((_QWORD *)v21 + 16) = 0x40DF754000000000LL;
          if ( *(char **)v21 == v21 )
          {
            v75 = *(_QWORD *)v22;
            if ( *(char **)(*(_QWORD *)v22 + 8LL) != v22 )
LABEL_127:
              __fastfail(3u);
            *(_QWORD *)v21 = v75;
            *((_QWORD *)v21 + 1) = v22;
            *(_QWORD *)(v75 + 8) = v21;
            *(_QWORD *)v22 = v21;
          }
          WdcDataMonitor::SetRowDirty((WdcDataMonitor *)v20, (struct _WDC_DATA_INFO *)(v21 - 16));
        }
        if ( !v205 )
        {
          v76 = (int)*((double *)v21 + 12);
          v77 = (struct _SYSTEM_PROCESS_INFORMATION *)*((_QWORD *)v24 + 1200);
          v77->WorkingSetSize = 0;
          v77->WorkingSetPrivateSize.QuadPart = 0;
          v77->PrivatePageCount = 0;
          v77->HardFaultCount = 0;
          v77->UniqueProcessId = (HANDLE)v76;
          WdcTraceControl::FireEventProcessMemory(*((WdcTraceControl **)v24 + 1019), v77);
        }
      }
      v21 = *(char **)v21;
      if ( v21 == v22 )
        goto LABEL_66;
    }
    v26 = v21 + 320;
    v27 = 0;
    v28 = v208;
    v29 = 0.0;
    v30 = *((_QWORD *)v21 + 4);
    v31 = (double)(unsigned __int8)v21[v19 + 344] / 255.0 * *((double *)this + v19 + 1206);
    if ( v31 == 0.0 )
    {
LABEL_37:
      if ( v28 != 0.0 )
      {
        v32 = *((double *)v21 + 41);
        if ( v32 != 0.0 )
        {
          v52 = v32 / v28 * 255.0;
          if ( COERCE_DOUBLE(*((_QWORD *)v21 + 42) & v23) >= 0.05 )
          {
            if ( *((double *)v21 + 42) < 0.0 )
              v60 = floor(v52);
            else
              v60 = o_ceil_0();
            v29 = v60;
          }
          else
          {
            if ( v52 <= 0.0 )
              v53 = v52 - 0.5;
            else
              v53 = v52 + 0.5;
            v20 = (unsigned int)(int)v53;
            v29 = (double)(int)v20;
          }
        }
      }
      v33 = *((double *)v21 + 41);
      *((_BYTE *)v26 + v19 + 24) = (int)v29;
      v34 = *((double *)v21 + 35);
      if ( v34 != 0.0 )
      {
        if ( (unsigned __int8)(int)v29 )
        {
          *v26 = 0;
        }
        else
        {
          v20 = (unsigned int)*v26;
          *v26 = v20 + 1;
          if ( (unsigned int)v20 >= 0x3C )
            goto LABEL_75;
        }
      }
      if ( !v27 )
      {
        if ( v28 != 0.0 )
        {
          v35 = v33 - v29 / 255.0 * v28;
          if ( dword_1800AE114 )
          {
            if ( byte_1800AE118 != 1 && (qword_1800AE100 & 0x800) != 0 && (qword_1800AE108 & 0x800) == qword_1800AE108 )
            {
              OutputString = 0;
              memset_0(v217, 0, sizeof(v217));
              if ( *((_DWORD *)this + 2324) == 1 )
              {
                v63 = 0.0;
                v64 = 0;
                do
                {
                  v65 = (double)*((unsigned __int8 *)v26 + v64 + 24) / 255.0;
                  if ( (_DWORD)v64 == (_DWORD)v19 )
                    v66 = v65 * v28;
                  else
                    v66 = v65 * *((double *)this + v64 + 1206);
                  v85 = (unsigned int)(v64 + 1);
                  v86 = v63 + v66;
                  v87 = (double)*((unsigned __int8 *)v26 + v85 + 24) / 255.0;
                  if ( (_DWORD)v85 == (_DWORD)v19 )
                    v88 = v86 + v28 * v87;
                  else
                    v88 = v86 + v87 * *((double *)this + v85 + 1206);
                  v89 = (unsigned int)(v64 + 2);
                  v90 = (double)*((unsigned __int8 *)v26 + v89 + 24) / 255.0;
                  if ( (_DWORD)v89 == (_DWORD)v19 )
                    v91 = v90 * v28;
                  else
                    v91 = v90 * *((double *)this + v89 + 1206);
                  v92 = (unsigned int)(v64 + 3);
                  v93 = v88 + v91;
                  v94 = (double)*((unsigned __int8 *)v26 + v92 + 24) / 255.0;
                  if ( (_DWORD)v92 == (_DWORD)v19 )
                    v95 = v93 + v28 * v94;
                  else
                    v95 = v93 + v94 * *((double *)this + v92 + 1206);
                  v96 = (unsigned int)(v64 + 4);
                  v97 = (double)*((unsigned __int8 *)v26 + v96 + 24) / 255.0;
                  if ( (_DWORD)v96 == (_DWORD)v19 )
                    v98 = v97 * v28;
                  else
                    v98 = v97 * *((double *)this + v96 + 1206);
                  v99 = v95 + v98;
                  v100 = (unsigned int)(v64 + 5);
                  v101 = (double)*((unsigned __int8 *)v26 + v100 + 24) / 255.0;
                  if ( (_DWORD)v100 == (_DWORD)v19 )
                    v102 = v101 * v28;
                  else
                    v102 = v101 * *((double *)this + v100 + 1206);
                  v103 = v99 + v102;
                  v104 = (unsigned int)(v64 + 6);
                  v105 = (double)*((unsigned __int8 *)v26 + v104 + 24) / 255.0;
                  if ( (_DWORD)v104 == (_DWORD)v19 )
                    v106 = v105 * v28;
                  else
                    v106 = v105 * *((double *)this + v104 + 1206);
                  v107 = v103 + v106;
                  v108 = (unsigned int)(v64 + 7);
                  v109 = (double)*((unsigned __int8 *)v26 + v108 + 24) / 255.0;
                  if ( (_DWORD)v108 == (_DWORD)v19 )
                    v110 = v109 * v28;
                  else
                    v110 = v109 * *((double *)this + v108 + 1206);
                  v111 = v107 + v110;
                  v112 = (unsigned int)(v64 + 8);
                  v113 = (double)*((unsigned __int8 *)v26 + v112 + 24) / 255.0;
                  if ( (_DWORD)v112 == (_DWORD)v19 )
                    v114 = v113 * v28;
                  else
                    v114 = v113 * *((double *)this + v112 + 1206);
                  v115 = v111 + v114;
                  v116 = (unsigned int)(v64 + 9);
                  v117 = (double)*((unsigned __int8 *)v26 + v116 + 24) / 255.0;
                  if ( (_DWORD)v116 == (_DWORD)v19 )
                    v118 = v117 * v28;
                  else
                    v118 = v117 * *((double *)this + v116 + 1206);
                  v119 = v115 + v118;
                  v120 = (unsigned int)(v64 + 10);
                  v121 = (double)*((unsigned __int8 *)v26 + v120 + 24) / 255.0;
                  if ( (_DWORD)v120 == (_DWORD)v19 )
                    v122 = v121 * v28;
                  else
                    v122 = v121 * *((double *)this + v120 + 1206);
                  v123 = v119 + v122;
                  v124 = (unsigned int)(v64 + 11);
                  v125 = (double)*((unsigned __int8 *)v26 + v124 + 24) / 255.0;
                  if ( (_DWORD)v124 == (_DWORD)v19 )
                    v126 = v125 * v28;
                  else
                    v126 = v125 * *((double *)this + v124 + 1206);
                  v127 = v123 + v126;
                  v128 = (unsigned int)(v64 + 12);
                  v129 = (double)*((unsigned __int8 *)v26 + v128 + 24) / 255.0;
                  if ( (_DWORD)v128 == (_DWORD)v19 )
                    v130 = v129 * v28;
                  else
                    v130 = v129 * *((double *)this + v128 + 1206);
                  v131 = v127 + v130;
                  v132 = (unsigned int)(v64 + 13);
                  v133 = (double)*((unsigned __int8 *)v26 + v132 + 24) / 255.0;
                  if ( (_DWORD)v132 == (_DWORD)v19 )
                    v134 = v133 * v28;
                  else
                    v134 = v133 * *((double *)this + v132 + 1206);
                  v135 = v131 + v134;
                  v20 = (unsigned int)(v64 + 14);
                  v136 = (double)*((unsigned __int8 *)v26 + v20 + 24) / 255.0;
                  if ( (_DWORD)v20 == (_DWORD)v19 )
                    v137 = v136 * v28;
                  else
                    v137 = v136 * *((double *)this + v20 + 1206);
                  v64 = (unsigned int)(v64 + 15);
                  v63 = v135 + v137;
                }
                while ( (unsigned int)v64 < 0x3C );
                v138 = v35 + *((double *)v21 + 42);
                *(_QWORD *)&v139 = COERCE_UNSIGNED_INT64(v138 - (v34 - v63)) & v23;
                if ( v139 < 1.0 || (v140 = 0, v139 / v34 < 0.1) )
                  v140 = 1;
                if ( v30 && *((_QWORD *)this + 8) == v30 || !v140 )
                {
                  LODWORD(v198) = *((unsigned __int8 *)v26 + v19 + 24);
                  StringCchPrintfW(
                    &OutputString,
                    0x400u,
                    L"WDC: [%2d] Key 0x%08I64x Win %9.03lf His %9.03lf Dlt %9.03lf Tdt %9.03lf Err %9.03lf Cur %9.03lf Tot"
                     " %9.03lf Qtm %3d\n",
                    (unsigned int)v19,
                    v30,
                    v34,
                    v63,
                    v35,
                    v138,
                    v138 - (v34 - v63),
                    *((_QWORD *)v21 + 41),
                    v28,
                    v198);
                  OutputDebugStringW(&OutputString);
                }
              }
            }
          }
          v36 = v35 + *((double *)v21 + 42);
          *((_QWORD *)v21 + 41) = 0;
          *((double *)v21 + 42) = v36;
        }
        goto LABEL_46;
      }
LABEL_75:
      memset_0(v21 + 320, 0, 0x58u);
      *((_QWORD *)v21 + 35) = 0;
LABEL_46:
      v22 = v201;
      v24 = this;
      goto LABEL_47;
    }
    v56 = *((double *)v21 + 35);
    if ( v31 > v56 )
    {
      *((_QWORD *)v21 + 35) = 0;
    }
    else
    {
      v57 = v56 - v31;
      *((double *)v21 + 35) = v57;
      if ( v57 != 0.0 )
        goto LABEL_37;
    }
    v27 = 1;
    goto LABEL_37;
  }
LABEL_66:
  v11 = this;
  v50 = v209;
  *((double *)this + v19 + 1206) = v208;
  *((_QWORD *)this + v19 + 1023) = v210;
  *((double *)this + v19 + 1266) = v50;
  if ( *((_DWORD *)this + 2296) )
    WdcProcessMonitor::UpdateFrequency(this, 0, v19);
  else
    *((_QWORD *)this + v19 + 1083) = 0x4059000000000000LL;
  WdcProcessMonitor::UpdateHangStatus((LPARAM)this);
LABEL_69:
  v2 = v204;
  v15 = 0;
LABEL_19:
  if ( *((_DWORD *)v11 + 12) && v2 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 8));
  v17 = v202;
  if ( v202 )
    WdcTraceControl::NotifyPidReuse(*((WdcTraceControl **)v11 + 1019), v206, v202);
  if ( v206 )
    WdcFree(v206, v16, v17);
  return v15;
}

```

## disassembly

```asm
0x18000c090  push    rbp
0x18000c092  push    rbx
0x18000c093  push    rsi
0x18000c094  push    rdi
0x18000c095  push    r12
0x18000c097  push    r13
0x18000c099  push    r14
0x18000c09b  push    r15
0x18000c09d  lea     rbp, [rsp-898h]
0x18000c0a5  sub     rsp, 998h
0x18000c0ac  movaps  [rsp+9D0h+var_70], xmm8
0x18000c0b5  mov     rax, cs:__security_cookie
0x18000c0bc  xor     rax, rsp
0x18000c0bf  mov     [rbp+8D0h+var_F0], rax
0x18000c0c6  xor     eax, eax
0x18000c0c8  mov     [rsp+9D0h+lParam], rcx
0x18000c0cd  mov     [rsp+9D0h+var_958], rax
0x18000c0d2  xorps   xmm8, xmm8
0x18000c0d6  movsd   [rbp+8D0h+var_930], xmm8
0x18000c0dc  mov     r14d, eax
0x18000c0df  movsd   [rbp+8D0h+var_928], xmm8
0x18000c0e5  mov     r13d, eax
0x18000c0e8  mov     [rbp+8D0h+var_94C], eax
0x18000c0eb  mov     r15, rcx
0x18000c0ee  mov     ecx, ds:7FFE0018h
0x18000c0f5  mov     qword ptr [rbp+8D0h+var_938], rax
0x18000c0f9  mov     [rbp+8D0h+var_918], rax
0x18000c0fd  mov     [rbp+8D0h+var_948], eax
0x18000c100  mov     [rbp+8D0h+var_920], rax
0x18000c104  mov     [rbp+8D0h+var_908], rax
0x18000c108  mov     [rbp+8D0h+var_910], rax
0x18000c10c  mov     [rbp+8D0h+var_944], eax
0x18000c10f  mov     [rbp+8D0h+var_940], rax
0x18000c113  mov     [rbp+8D0h+var_950], eax
0x18000c116  mov     eax, ds:7FFE0014h
0x18000c11d  mov     dword ptr [rsp+9D0h+var_958], eax
0x18000c121  mov     eax, ds:7FFE001Ch
0x18000c128  mov     dword ptr [rsp+9D0h+var_958+4], ecx
0x18000c12c  cmp     ecx, eax
0x18000c12e  jz      short loc_18000C151
0x18000c130  mov     ecx, ds:7FFE0018h
0x18000c137  mov     eax, ds:7FFE0014h
0x18000c13e  mov     dword ptr [rsp+9D0h+var_958], eax
0x18000c142  mov     eax, ds:7FFE001Ch
0x18000c149  mov     dword ptr [rsp+9D0h+var_958+4], ecx
0x18000c14d  cmp     ecx, eax
0x18000c14f  jnz     short loc_18000C130
0x18000c151  lea     rcx, [rbp+8D0h+var_920]; unsigned __int64 *
0x18000c155  call    ?WdcGetTimeStampCounter@@YAJPEA_K@Z; WdcGetTimeStampCounter(unsigned __int64 *)
0x18000c15a  lea     rsi, [r15+2580h]
0x18000c161  xor     r9d, r9d; unsigned int
0x18000c164  lea     r12, [r15+2588h]
0x18000c16b  mov     [rbp+8D0h+var_900], rsi
0x18000c16f  mov     r8, rsi; void **
0x18000c172  mov     [rbp+8D0h+var_8F8], r12
0x18000c176  mov     rdx, r12; unsigned __int64 *
0x18000c179  lea     rcx, ?WdcQueryProcessInformation@@YAJPEAU_WDC_EXPANDING_CALL@@@Z; int (*)(struct _WDC_EXPANDING_CALL *)
0x18000c180  call    ?WdcExpandingCall@@YAJP6AJPEAU_WDC_EXPANDING_CALL@@@ZPEA_KPEAPEAXKZZ; WdcExpandingCall(long (*)(_WDC_EXPANDING_CALL *),unsigned __int64 *,void * *,ulong,...)
0x18000c185  test    eax, eax
0x18000c187  js      loc_18000CBE5
0x18000c18d  mov     rcx, [r15+34B8h]; hQuery
0x18000c194  test    rcx, rcx
0x18000c197  jnz     loc_18000CBF1
0x18000c19d  lea     rcx, stru_1800B5680.CycleTime; unsigned __int64 *
0x18000c1a4  call    ?WdcGetDpcIsrCycleTime@@YAJPEA_K@Z; WdcGetDpcIsrCycleTime(unsigned __int64 *)
0x18000c1a9  mov     ebx, ds:7FFE0018h
0x18000c1b0  mov     edi, ds:7FFE0014h
0x18000c1b7  mov     eax, ds:7FFE001Ch
0x18000c1be  mov     dword ptr [rbp+8D0h+var_938+4], ebx
0x18000c1c1  mov     dword ptr [rbp+8D0h+var_938], edi
0x18000c1c4  cmp     ebx, eax
0x18000c1c6  jz      short loc_18000C1EF
0x18000c1c8  nop     dword ptr [rax+rax+00000000h]
0x18000c1d0  mov     ebx, ds:7FFE0018h
0x18000c1d7  mov     edi, ds:7FFE0014h
0x18000c1de  mov     eax, ds:7FFE001Ch
0x18000c1e5  mov     dword ptr [rbp+8D0h+var_938+4], ebx
0x18000c1e8  mov     dword ptr [rbp+8D0h+var_938], edi
0x18000c1eb  cmp     ebx, eax
0x18000c1ed  jnz     short loc_18000C1D0
0x18000c1ef  lea     rcx, [rbp+8D0h+var_908]; unsigned __int64 *
0x18000c1f3  call    ?WdcGetTimeStampCounter@@YAJPEA_K@Z; WdcGetTimeStampCounter(unsigned __int64 *)
0x18000c1f8  mov     rcx, [r15+25A0h]
0x18000c1ff  test    rcx, rcx
0x18000c202  jz      short loc_18000C217
0x18000c204  mov     r14d, ebx
0x18000c207  shl     r14, 20h
0x18000c20b  mov     eax, edi
0x18000c20d  or      r14, rax
0x18000c210  sub     r14, rcx
0x18000c213  mov     [rbp+8D0h+var_918], r14
0x18000c217  mov     rcx, [r15+29B0h]
0x18000c21e  mov     rdi, r15
0x18000c221  mov     rax, [rsp+9D0h+var_958]
0x18000c226  mov     [r15+25A0h], rax
0x18000c22d  test    rcx, rcx
0x18000c230  jz      short loc_18000C24E
0x18000c232  mov     rax, [rbp+8D0h+var_908]
0x18000c236  test    rax, rax
0x18000c239  jz      short loc_18000C24E
0x18000c23b  cmp     rax, rcx
0x18000c23e  jb      short loc_18000C24E
0x18000c240  mov     r13, rax
0x18000c243  sub     r13, rcx
0x18000c246  mov     [rbp+8D0h+var_910], r13
0x18000c24a  mov     r13d, [rbp+8D0h+var_948]
0x18000c24e  cmp     dword ptr [rdi+30h], 0
0x18000c252  mov     rax, [rbp+8D0h+var_920]
0x18000c256  mov     [rdi+29B0h], rax
0x18000c25d  jz      short loc_18000C273
0x18000c25f  lea     rcx, [rdi+8]; lpCriticalSection
0x18000c263  call    cs:__imp_EnterCriticalSection
0x18000c269  mov     r13d, 1
0x18000c26f  mov     [rbp+8D0h+var_948], r13d
0x18000c273  movaps  [rsp+9D0h+var_50], xmm6
0x18000c27b  mov     rcx, rdi; this
0x18000c27e  movaps  [rsp+9D0h+var_60], xmm7
0x18000c286  movaps  [rsp+9D0h+var_80], xmm9
0x18000c28f  movaps  [rsp+9D0h+var_90], xmm10
0x18000c298  movaps  [rsp+9D0h+var_A0], xmm11
0x18000c2a1  movaps  [rsp+9D0h+var_B0], xmm12
0x18000c2aa  movaps  [rsp+9D0h+var_C0], xmm13
0x18000c2b3  movaps  [rsp+9D0h+var_D0], xmm14
0x18000c2bc  movaps  [rsp+9D0h+var_E0], xmm15
0x18000c2c5  call    ?Update@WdcDataMonitor@@MEAAJXZ; WdcDataMonitor::Update(void)
0x18000c2ca  mov     ebx, eax
0x18000c2cc  test    eax, eax
0x18000c2ce  jns     loc_18000C3A1
0x18000c2d4  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18000c2db  mov     dword ptr [rsp+9D0h+var_9B0], eax
0x18000c2df  xor     r8d, r8d; int
0x18000c2e2  lea     rdx, aWdcprocessmoni_2; "WdcProcessMonitor::Update"
0x18000c2e9  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18000c2f0  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18000c2f5  cmp     dword ptr [rdi+30h], 0
0x18000c2f9  jz      short loc_18000C30A
0x18000c2fb  test    r13d, r13d
0x18000c2fe  jz      short loc_18000C30A
0x18000c300  lea     rcx, [rdi+8]; lpCriticalSection
0x18000c304  call    cs:__imp_LeaveCriticalSection
0x18000c30a  mov     r8d, [rbp+8D0h+var_950]; int
0x18000c30e  test    r8d, r8d
0x18000c311  jnz     loc_18000D471
0x18000c317  mov     rax, [rbp+8D0h+var_940]
0x18000c31b  test    rax, rax
0x18000c31e  jnz     loc_18000D486
0x18000c324  movaps  xmm15, [rsp+9D0h+var_E0]
0x18000c32d  mov     eax, ebx
0x18000c32f  movaps  xmm14, [rsp+9D0h+var_D0]
0x18000c338  movaps  xmm13, [rsp+9D0h+var_C0]
0x18000c341  movaps  xmm12, [rsp+9D0h+var_B0]
0x18000c34a  movaps  xmm11, [rsp+9D0h+var_A0]
0x18000c353  movaps  xmm10, [rsp+9D0h+var_90]
0x18000c35c  movaps  xmm9, [rsp+9D0h+var_80]
0x18000c365  movaps  xmm7, [rsp+9D0h+var_60]
0x18000c36d  movaps  xmm6, [rsp+9D0h+var_50]
0x18000c375  mov     rcx, [rbp+8D0h+var_F0]
0x18000c37c  xor     rcx, rsp; StackCookie
0x18000c37f  call    __security_check_cookie
0x18000c384  movaps  xmm8, [rsp+9D0h+var_70]
0x18000c38d  add     rsp, 998h
0x18000c394  pop     r15
0x18000c396  pop     r14
0x18000c398  pop     r13
0x18000c39a  pop     r12
0x18000c39c  pop     rdi
0x18000c39d  pop     rsi
0x18000c39e  pop     rbx
0x18000c39f  pop     rbp
0x18000c3a0  retn
0x18000c3a1  cmp     [rbp+8D0h+var_944], 0
0x18000c3a5  mov     r13d, [rdi+1FE4h]
0x18000c3ac  jz      loc_18000CBFC
0x18000c3b2  mov     edx, r13d; unsigned int
0x18000c3b5  mov     rcx, rdi; this
0x18000c3b8  call    ?UpdateQuery@WdcProcessMonitor@@AEAAJK@Z; WdcProcessMonitor::UpdateQuery(ulong)
0x18000c3bd  movsd   xmm0, qword ptr [rdi+3508h]
0x18000c3c5  movsd   [rbp+8D0h+var_920], xmm0
0x18000c3ca  mov     r9, [rbp+8D0h+var_910]; unsigned __int64
0x18000c3ce  lea     rax, [rbp+8D0h+var_94C]
0x18000c3d2  mov     [rsp+9D0h+var_9A0], rax; int *
0x18000c3d7  lea     rdx, stru_1800B5680; struct _SYSTEM_PROCESS_INFORMATION *
0x18000c3de  lea     rax, [rbp+8D0h+var_928]
0x18000c3e2  mov     cs:stru_1800B5680.UniqueProcessId, 1
0x18000c3ed  mov     [rsp+9D0h+var_9A8], rax; double *
0x18000c3f2  mov     r8, r14; unsigned __int64
0x18000c3f5  lea     rax, [rbp+8D0h+var_930]
0x18000c3f9  mov     rcx, rdi; this
0x18000c3fc  mov     [rsp+9D0h+var_9B0], rax; double *
0x18000c401  call    ?UpdateProcess@WdcProcessMonitor@@AEAAJPEAU_SYSTEM_PROCESS_INFORMATION@@_K1PEAN2PEAH@Z; WdcProcessMonitor::UpdateProcess(_SYSTEM_PROCESS_INFORMATION *,unsigned __int64,unsigned __int64,double *,double *,int *)
0x18000c406  movsd   xmm0, [rbp+8D0h+var_930]
0x18000c40b  movsd   xmm6, cs:__real@4059000000000000
0x18000c413  comisd  xmm0, xmm6
0x18000c417  ja      loc_18000CCF3
0x18000c41d  movsd   xmm0, [rbp+8D0h+var_928]
0x18000c422  comisd  xmm0, xmm6
0x18000c426  ja      loc_18000CD1B
0x18000c42c  mov     rbx, [rdi+58h]
0x18000c430  add     rdi, 58h ; 'X'
0x18000c434  mov     [rsp+9D0h+var_958], rdi
0x18000c439  cmp     rbx, rdi
0x18000c43c  jz      loc_18000C71B
0x18000c442  movdqa  xmm11, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x18000c44b  movsd   xmm10, cs:__real@406fe00000000000
0x18000c454  movsd   xmm12, cs:__real@3fa999999999999a
0x18000c45d  movsd   xmm13, cs:__real@3fe0000000000000
0x18000c466  movsd   xmm15, cs:__real@3ff0000000000000
0x18000c46f  movsd   xmm14, cs:__real@3fb999999999999a
0x18000c478  mov     r14, [rsp+9D0h+lParam]
0x18000c47d  nop     dword ptr [rax]
0x18000c480  movsd   xmm9, [rbp+8D0h+var_928]
0x18000c486  cmp     r13d, 3Ch ; '<'
0x18000c48a  jnb     loc_18000C58E
0x18000c490  mov     r9, [rsp+9D0h+lParam]
0x18000c495  lea     rdi, [rbx+140h]
0x18000c49c  movzx   eax, byte ptr [r13+rdi+18h]
0x18000c4a2  xor     r14d, r14d
0x18000c4a5  movsd   xmm7, [rbp+8D0h+var_930]
0x18000c4aa  movaps  xmm2, xmm8
0x18000c4ae  mov     r12, [rbx+20h]
0x18000c4b2  movd    xmm0, eax
0x18000c4b6  cvtdq2pd xmm0, xmm0
0x18000c4ba  divsd   xmm0, xmm10
0x18000c4bf  mulsd   xmm0, qword ptr [r9+r13*8+25B0h]
0x18000c4c9  ucomisd xmm8, xmm0
0x18000c4ce  jp      loc_18000C8CB
0x18000c4d4  jnz     loc_18000C8CB
0x18000c4da  ucomisd xmm7, xmm8
0x18000c4df  jp      short loc_18000C4E3
0x18000c4e1  jz      short loc_18000C4F9
0x18000c4e3  movsd   xmm1, qword ptr [rdi+8]
0x18000c4e8  ucomisd xmm1, xmm8
0x18000c4ed  jp      loc_18000C82C
0x18000c4f3  jnz     loc_18000C82C
0x18000c4f9  movsd   xmm6, qword ptr [rdi+8]
0x18000c4fe  movaps  xmm0, xmm2
0x18000c501  divsd   xmm0, xmm10
0x18000c506  cvttsd2si eax, xmm2
0x18000c50a  xorps   xmm1, xmm1
0x18000c50d  mulsd   xmm0, xmm7
0x18000c511  mov     [r13+rdi+18h], al
0x18000c516  movsd   xmm8, qword ptr [rbx+118h]
0x18000c51f  ucomisd xmm1, xmm8
0x18000c524  jp      loc_18000C7BC
0x18000c52a  jnz     loc_18000C7BC
0x18000c530  test    r14d, r14d
0x18000c533  jnz     loc_18000C7D4
0x18000c539  ucomisd xmm7, xmm1
0x18000c53d  jp      short loc_18000C541
0x18000c53f  jz      short loc_18000C580
0x18000c541  cmp     cs:dword_1800AE114, 0
0x18000c548  subsd   xmm6, xmm0
0x18000c54c  jz      short loc_18000C568
0x18000c54e  cmp     cs:byte_1800AE118, 1
0x18000c555  jz      short loc_18000C568
0x18000c557  test    cs:qword_1800AE100, 800h
0x18000c562  jnz     loc_18000C9DB
0x18000c568  addsd   xmm6, qword ptr [rbx+150h]
0x18000c570  mov     qword ptr [rdi+8], 0
0x18000c578  movsd   qword ptr [rbx+150h], xmm6
0x18000c580  mov     rdi, [rsp+9D0h+var_958]
0x18000c585  xorps   xmm8, xmm8
0x18000c589  mov     r14, [rsp+9D0h+lParam]
0x18000c58e  movzx   eax, word ptr [rbx+30h]
0x18000c592  movsd   xmm1, qword ptr [rbx+118h]
0x18000c59a  movd    xmm0, eax
0x18000c59e  cvtdq2pd xmm0, xmm0
0x18000c5a2  divsd   xmm1, xmm0
0x18000c5a6  movsd   xmm0, qword ptr [rbx+0B0h]
0x18000c5ae  ucomisd xmm0, xmm1
0x18000c5b2  jp      loc_18000C965
0x18000c5b8  jnz     loc_18000C965
0x18000c5be  movsd   xmm0, qword ptr [rbx+0F0h]
0x18000c5c6  comisd  xmm0, xmm8
0x18000c5cb  jb      loc_18000C6FE
0x18000c5d1  cmp     r13d, 3Ch ; '<'
0x18000c5d5  jnb     loc_18000C6C9
0x18000c5db  mov     r9, [rsp+9D0h+lParam]
0x18000c5e0  lea     rdi, [rbx+198h]
0x18000c5e7  movzx   eax, byte ptr [r13+rdi+18h]
0x18000c5ed  xor     r14d, r14d
0x18000c5f0  mov     r12, [rbx+20h]
0x18000c5f4  movaps  xmm2, xmm8
0x18000c5f8  movd    xmm0, eax
0x18000c5fc  cvtdq2pd xmm0, xmm0
0x18000c600  divsd   xmm0, xmm10
0x18000c605  mulsd   xmm0, qword ptr [r9+r13*8+2790h]
0x18000c60f  ucomisd xmm8, xmm0
0x18000c614  jp      loc_18000C8FF
0x18000c61a  jnz     loc_18000C8FF
0x18000c620  ucomisd xmm9, xmm8
0x18000c625  jp      short loc_18000C629
0x18000c627  jz      short loc_18000C63F
0x18000c629  movsd   xmm1, qword ptr [rdi+8]
0x18000c62e  ucomisd xmm1, xmm8
0x18000c633  jp      loc_18000C870
0x18000c639  jnz     loc_18000C870
0x18000c63f  movsd   xmm6, qword ptr [rdi+8]
0x18000c644  movaps  xmm0, xmm2
0x18000c647  divsd   xmm0, xmm10
  ... truncated ...
```
