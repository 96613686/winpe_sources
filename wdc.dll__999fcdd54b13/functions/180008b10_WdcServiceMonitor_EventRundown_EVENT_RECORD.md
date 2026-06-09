# WdcServiceMonitor::EventRundown(_EVENT_RECORD *)

- ea: `0x180008b10`
- end: `0x1800096e6`
- name: `?EventRundown@WdcServiceMonitor@@QEAAJPEAU_EVENT_RECORD@@@Z`
- size: `3030`
- prototype: `__int64 __fastcall(WdcServiceMonitor *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x18000a4d0`

## callees

- `0x180008b10`
- `0x18000b7d0`
- `0x18000b854`
- `0x18000dff0`
- `0x18003a3c0`
- `0x18003b064`
- `0x18003b07c`
- `0x18003b0ac`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000966e`
- `KERNEL32!OutputDebugStringW` at `0x18000966e`
- `KERNEL32!LeaveCriticalSection` at `0x180008d48`
- `KERNEL32!LeaveCriticalSection` at `0x180008d80`
- `KERNEL32!LeaveCriticalSection` at `0x180008d48`
- `KERNEL32!LeaveCriticalSection` at `0x180008d80`
- `KERNEL32!EnterCriticalSection` at `0x180008ba0`
- `KERNEL32!EnterCriticalSection` at `0x180008c94`
- `KERNEL32!EnterCriticalSection` at `0x180008e13`
- `KERNEL32!EnterCriticalSection` at `0x180008ba0`
- `KERNEL32!EnterCriticalSection` at `0x180008c94`
- `KERNEL32!EnterCriticalSection` at `0x180008e13`

## string_xrefs

- `0x180009304`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180009693`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x1800096c8`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x18000968c`: `WdcServiceMonitor::ChargeService`
- `0x1800092ed`: `AllServiceCpuUsage: %f`
- `0x1800092fd`: `WdcServiceMonitor::EventRundown`
- `0x1800096b3`: `WdcServiceMonitor::EventRundown`
- `0x1800096a9`: `ServiceTag %d not found: PID: %d TID: %d`

## pseudocode

```c
__int64 __fastcall WdcServiceMonitor::EventRundown(WdcServiceMonitor *this, struct _EVENT_RECORD *a2)
{
  USHORT Id; // ax
  int v3; // esi
  unsigned int *UserData; // r12
  __int64 v6; // rcx
  __int64 v7; // r15
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 *i; // rbx
  __int64 *v11; // rax
  __int64 **v12; // rcx
  __int64 *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rbp
  int v16; // r14d
  char *v17; // rdx
  char *j; // rax
  char *v19; // rcx
  char **v20; // r8
  char *v21; // rcx
  __int64 v22; // rcx
  struct _RTL_CRITICAL_SECTION *v23; // rcx
  bool v25; // zf
  __int64 v26; // rbx
  double v27; // xmm6_8
  __int64 v28; // rdi
  double *v29; // rdx
  char *v30; // r9
  __int64 v31; // rcx
  __int64 v32; // r8
  double v33; // xmm0_8
  double v34; // xmm1_8
  double v35; // xmm0_8
  double v36; // xmm0_8
  __int64 v37; // rcx
  __int64 v38; // rax
  unsigned int v39; // eax
  char *v40; // rbx
  char *v41; // r15
  __int64 v42; // r14
  unsigned __int64 v43; // xmm10_8
  __int64 v44; // r12
  _DWORD *v45; // rdi
  int v46; // esi
  double v47; // xmm2_8
  double v48; // xmm0_8
  double v49; // xmm1_8
  double v50; // xmm7_8
  double v51; // xmm8_8
  double v52; // xmm7_8
  double v53; // xmm7_8
  double v54; // xmm1_8
  unsigned int v55; // ecx
  __int64 v56; // rax
  double v57; // xmm1_8
  double v58; // xmm1_8
  double v59; // xmm1_8
  double v60; // xmm1_8
  double v61; // xmm0_8
  double v62; // xmm1_8
  __int64 v63; // r8
  double v64; // xmm0_8
  double v65; // xmm0_8
  double v66; // xmm1_8
  __int64 v67; // rcx
  double v68; // xmm0_8
  double v69; // xmm0_8
  double v70; // xmm1_8
  __int64 v71; // rcx
  double v72; // xmm0_8
  double v73; // xmm0_8
  double v74; // xmm1_8
  __int64 v75; // rcx
  double v76; // xmm0_8
  double v77; // xmm0_8
  double v78; // xmm1_8
  __int64 v79; // rcx
  double v80; // xmm0_8
  double v81; // xmm0_8
  double v82; // xmm1_8
  __int64 v83; // rcx
  double v84; // xmm0_8
  double v85; // xmm0_8
  double v86; // xmm1_8
  __int64 v87; // rcx
  double v88; // xmm0_8
  double v89; // xmm0_8
  double v90; // xmm1_8
  __int64 v91; // rcx
  double v92; // xmm0_8
  double v93; // xmm0_8
  double v94; // xmm1_8
  __int64 v95; // rcx
  double v96; // xmm0_8
  double v97; // xmm0_8
  double v98; // xmm1_8
  __int64 v99; // rcx
  double v100; // xmm0_8
  double v101; // xmm0_8
  double v102; // xmm1_8
  __int64 v103; // rcx
  double v104; // xmm0_8
  double v105; // xmm0_8
  double v106; // xmm1_8
  __int64 v107; // rcx
  double v108; // xmm0_8
  double v109; // xmm0_8
  double v110; // xmm1_8
  __int64 v111; // rcx
  double v112; // xmm0_8
  double v113; // xmm0_8
  double v114; // xmm1_8
  __int64 v115; // rcx
  double v116; // xmm0_8
  double v117; // xmm0_8
  double v118; // xmm1_8
  __int64 v119; // rcx
  double v120; // xmm0_8
  double v121; // xmm0_8
  double v122; // xmm3_8
  double v123; // xmm2_8
  int v124; // eax
  __int64 v125; // [rsp+20h] [rbp-938h]
  __int64 v126; // [rsp+28h] [rbp-930h]
  __int64 v127; // [rsp+30h] [rbp-928h]
  __int64 v128; // [rsp+60h] [rbp-8F8h]
  int v129; // [rsp+70h] [rbp-8E8h]
  WCHAR OutputString; // [rsp+80h] [rbp-8D8h] BYREF
  char v131[2046]; // [rsp+82h] [rbp-8D6h] BYREF

  Id = a2->EventHeader.EventDescriptor.Id;
  v3 = 0;
  UserData = (unsigned int *)a2->UserData;
  v129 = 0;
  if ( Id == 100 )
  {
    v6 = *((_QWORD *)this + 1168);
    if ( *(_DWORD *)(v6 + 48) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
      v129 = 1;
    }
    v7 = 0;
    if ( UserData[1] )
    {
      while ( 1 )
      {
        v8 = UserData[6 * v7 + 9];
        v9 = 16LL * ((((unsigned int)(1103515245 * v8 + 12345) >> 16) | (69069 * (_DWORD)v8 + 1) & 0xFFFF0000) % 0x1F7)
           + *((_QWORD *)this + 1168)
           + 104LL;
        for ( i = *(__int64 **)v9; ; i = (__int64 *)*i )
        {
          if ( i == (__int64 *)v9 )
            goto LABEL_162;
          v11 = (__int64 *)*i;
          if ( i[6] == v8 )
            break;
        }
        if ( (__int64 *)v11[1] != i )
          break;
        v12 = (__int64 **)i[1];
        if ( *v12 != i )
          break;
        *v12 = v11;
        v11[1] = (__int64)v12;
        v13 = *(__int64 **)v9;
        if ( *(_QWORD *)(*(_QWORD *)v9 + 8LL) != v9 )
          break;
        *i = (__int64)v13;
        v3 = 0;
        i[1] = v9;
        v13[1] = (__int64)i;
        *(_QWORD *)v9 = i;
        v14 = *((unsigned int *)i + 23);
        if ( (_DWORD)v14 )
        {
          v15 = 0;
          if ( *(_QWORD *)&UserData[6 * v7 + 5] - i[13] >= 0 )
            v15 = *(_QWORD *)&UserData[6 * v7 + 5] - i[13];
          v16 = 0;
          if ( *((_DWORD *)this + 12) )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
            v16 = 1;
          }
          v17 = (char *)this
              + 16
              * ((((unsigned int)(1103515245 * v14 + 12345) >> 16) | (69069 * (_DWORD)v14 + 1) & 0xFFFF0000) % 0x1F7)
              + 104;
          for ( j = *(char **)v17; ; j = *(char **)j )
          {
            if ( j == v17 )
            {
              v3 = -2147024894;
              LODWORD(v125) = -2147024894;
              WdcDebugMessage(
                "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
                "WdcServiceMonitor::ChargeService",
                0,
                L"FAILURE: 0x%08x",
                v125);
              goto LABEL_26;
            }
            v19 = *(char **)j;
            if ( *((_QWORD *)j + 6) == v14 )
              break;
          }
          if ( *((char **)v19 + 1) != j )
            break;
          v20 = (char **)*((_QWORD *)j + 1);
          if ( *v20 != j )
            break;
          *v20 = v19;
          *((_QWORD *)v19 + 1) = v20;
          v21 = *(char **)v17;
          if ( *(char **)(*(_QWORD *)v17 + 8LL) != v17 )
            break;
          *(_QWORD *)j = v21;
          *((_QWORD *)j + 1) = v17;
          *((_QWORD *)v21 + 1) = j;
          *(_QWORD *)v17 = j;
          *((_QWORD *)j + 26) += v15;
LABEL_26:
          if ( *((_DWORD *)this + 12) && v16 )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
          if ( v3 < 0 )
          {
            LODWORD(v127) = UserData[6 * v7 + 9];
            LODWORD(v126) = UserData[6 * v7 + 7];
            LODWORD(v125) = *((_DWORD *)i + 23);
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
              "WdcServiceMonitor::EventRundown",
              0,
              L"ServiceTag %d not found: PID: %d TID: %d",
              v125,
              v126,
              v127);
LABEL_162:
            v3 = 0;
          }
          else
          {
            i[13] += v15;
          }
        }
        v7 = (unsigned int)(v7 + 1);
        if ( (unsigned int)v7 >= UserData[1] )
          goto LABEL_32;
      }
LABEL_12:
      __fastfail(3u);
    }
LABEL_32:
    v22 = *((_QWORD *)this + 1168);
    if ( v129 && *(_DWORD *)(v22 + 48) )
    {
      v23 = (struct _RTL_CRITICAL_SECTION *)(v22 + 8);
LABEL_35:
      LeaveCriticalSection(v23);
      return (unsigned int)v3;
    }
    return (unsigned int)v3;
  }
  if ( Id != 102 )
    return (unsigned int)v3;
  v25 = *((_DWORD *)this + 12) == 0;
  v26 = *(_QWORD *)UserData;
  v27 = 0.0;
  v28 = *((_QWORD *)UserData + 1);
  *((_DWORD *)this + 2044) = UserData[4];
  if ( !v25 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v129 = 1;
  }
  if ( v28 )
  {
    v29 = (double *)*((_QWORD *)this + 11);
    v30 = (char *)this + 88;
    if ( v29 != (double *)((char *)this + 88) )
    {
      do
      {
        v31 = *((_QWORD *)v29 + 25);
        v32 = *((_QWORD *)v29 + 24);
        if ( v32 < v31 )
        {
          v34 = 0.0;
        }
        else
        {
          if ( v28 < 0 )
            v33 = (double)(int)(v28 & 1 | ((unsigned __int64)v28 >> 1))
                + (double)(int)(v28 & 1 | ((unsigned __int64)v28 >> 1));
          else
            v33 = (double)(int)v28;
          v34 = (double)((int)v32 - (int)v31) / v33 * 100.0;
        }
        v35 = v29[20];
        *((_QWORD *)v29 + 25) = v32;
        if ( v35 != v34 )
        {
          *((_DWORD *)v29 + 38) |= 1u;
          v29[20] = v34;
          if ( *(double **)v29 == v29 )
          {
            v38 = *(_QWORD *)v30;
            if ( *(char **)(*(_QWORD *)v30 + 8LL) != v30 )
              goto LABEL_12;
            *(_QWORD *)v29 = v38;
            *((_QWORD *)v29 + 1) = v30;
            *(_QWORD *)(v38 + 8) = v29;
            *(_QWORD *)v30 = v29;
          }
        }
        v25 = (*((_DWORD *)v29 + 13) & 0x10000000) == 0;
        v27 = v27 + v34;
        v36 = v34 - v29[28];
        v29[28] = v34;
        v29[23] = v36 + v29[23];
        if ( v25 )
        {
          v37 = *((_QWORD *)v29 + 7);
          if ( v37 )
          {
            while ( v26 - v37 > 5000000 )
            {
              v39 = *((unsigned __int16 *)v29 + 24);
              v37 += 10000000;
              *((_QWORD *)v29 + 7) = v37;
              if ( v39 < *((_DWORD *)this + 2288) )
                *((_WORD *)v29 + 24) = v39 + 1;
            }
          }
          else
          {
            *((_QWORD *)v29 + 7) = v26;
            *((_WORD *)v29 + 24) = 1;
          }
        }
        v29 = *(double **)v29;
      }
      while ( v29 != (double *)v30 );
      if ( v27 > 100.0 )
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
          "WdcServiceMonitor::EventRundown",
          0,
          L"AllServiceCpuUsage: %f",
          v27);
    }
  }
  v3 = WdcDataMonitor::Update(this);
  if ( v3 >= 0 )
  {
    v40 = (char *)*((_QWORD *)this + 11);
    v41 = (char *)this + 88;
    v42 = *((unsigned int *)this + 2041);
    if ( v40 == (char *)this + 88 )
    {
LABEL_80:
      *((double *)this + v42 + 1023) = v27;
      goto LABEL_54;
    }
    v43 = _mm_load_si128((const __m128i *)&_xmm).m128i_u64[0];
    while ( 1 )
    {
      if ( (unsigned int)v42 >= 0x3C )
        goto LABEL_78;
      v44 = *((_QWORD *)v40 + 4);
      v45 = v40 + 216;
      v46 = 0;
      v47 = 0.0;
      v48 = (double)(unsigned __int8)v40[v42 + 240] / 255.0 * *((double *)this + v42 + 1023);
      if ( v48 != 0.0 )
      {
        v59 = *((double *)v40 + 23);
        if ( v48 > v59 )
        {
          *((_QWORD *)v40 + 23) = 0;
        }
        else
        {
          v60 = v59 - v48;
          *((double *)v40 + 23) = v60;
          if ( v60 != 0.0 )
            goto LABEL_69;
        }
        v46 = 1;
      }
LABEL_69:
      if ( v27 != 0.0 )
      {
        v49 = *((double *)v40 + 28);
        if ( v49 != 0.0 )
        {
          v57 = v49 / v27 * 255.0;
          if ( COERCE_DOUBLE(*((_QWORD *)v40 + 29) & v43) >= 0.05 )
          {
            if ( *((double *)v40 + 29) < 0.0 )
              v61 = floor(v57);
            else
              v61 = o_ceil_0();
            v47 = v61;
          }
          else
          {
            if ( v57 <= 0.0 )
              v58 = v57 - 0.5;
            else
              v58 = v57 + 0.5;
            v47 = (double)(int)v58;
          }
        }
      }
      v50 = *((double *)v40 + 28);
      *((_BYTE *)v45 + v42 + 24) = (int)v47;
      v51 = *((double *)v40 + 23);
      if ( v51 != 0.0 )
      {
        if ( (unsigned __int8)(int)v47 )
        {
          *v45 = 0;
        }
        else
        {
          v55 = (*v45)++;
          if ( v55 >= 0x3C )
          {
LABEL_83:
            memset_0(v40 + 216, 0, 0x58u);
            *((_QWORD *)v40 + 23) = 0;
            goto LABEL_78;
          }
        }
      }
      if ( v46 )
        goto LABEL_83;
      if ( v27 != 0.0 )
      {
        v52 = v50 - v47 / 255.0 * v27;
        if ( dword_1800AE114 )
        {
          if ( byte_1800AE118 != 1 && (qword_1800AE100 & 0x800) != 0 && (qword_1800AE108 & 0x800) == qword_1800AE108 )
          {
            OutputString = 0;
            memset_0(v131, 0, sizeof(v131));
            if ( *((_DWORD *)this + 2324) == 1 )
            {
              v62 = 0.0;
              v63 = 0;
              do
              {
                v64 = (double)*((unsigned __int8 *)v45 + v63 + 24) / 255.0;
                if ( (_DWORD)v63 == (_DWORD)v42 )
                  v65 = v64 * v27;
                else
                  v65 = v64 * *((double *)this + v63 + 1023);
                v66 = v62 + v65;
                v67 = (unsigned int)(v63 + 1);
                v68 = (double)*((unsigned __int8 *)v45 + v67 + 24) / 255.0;
                if ( (_DWORD)v67 == (_DWORD)v42 )
                  v69 = v68 * v27;
                else
                  v69 = v68 * *((double *)this + v67 + 1023);
                v70 = v66 + v69;
                v71 = (unsigned int)(v63 + 2);
                v72 = (double)*((unsigned __int8 *)v45 + v71 + 24) / 255.0;
                if ( (_DWORD)v71 == (_DWORD)v42 )
                  v73 = v72 * v27;
                else
                  v73 = v72 * *((double *)this + v71 + 1023);
                v74 = v70 + v73;
                v75 = (unsigned int)(v63 + 3);
                v76 = (double)*((unsigned __int8 *)v45 + v75 + 24) / 255.0;
                if ( (_DWORD)v75 == (_DWORD)v42 )
                  v77 = v76 * v27;
                else
                  v77 = v76 * *((double *)this + v75 + 1023);
                v78 = v74 + v77;
                v79 = (unsigned int)(v63 + 4);
                v80 = (double)*((unsigned __int8 *)v45 + v79 + 24) / 255.0;
                if ( (_DWORD)v79 == (_DWORD)v42 )
                  v81 = v80 * v27;
                else
                  v81 = v80 * *((double *)this + v79 + 1023);
                v82 = v78 + v81;
                v83 = (unsigned int)(v63 + 5);
                v84 = (double)*((unsigned __int8 *)v45 + v83 + 24) / 255.0;
                if ( (_DWORD)v83 == (_DWORD)v42 )
                  v85 = v84 * v27;
                else
                  v85 = v84 * *((double *)this + v83 + 1023);
                v86 = v82 + v85;
                v87 = (unsigned int)(v63 + 6);
                v88 = (double)*((unsigned __int8 *)v45 + v87 + 24) / 255.0;
                if ( (_DWORD)v87 == (_DWORD)v42 )
                  v89 = v88 * v27;
                else
                  v89 = v88 * *((double *)this + v87 + 1023);
                v90 = v86 + v89;
                v91 = (unsigned int)(v63 + 7);
                v92 = (double)*((unsigned __int8 *)v45 + v91 + 24) / 255.0;
                if ( (_DWORD)v91 == (_DWORD)v42 )
                  v93 = v92 * v27;
                else
                  v93 = v92 * *((double *)this + v91 + 1023);
                v94 = v90 + v93;
                v95 = (unsigned int)(v63 + 8);
                v96 = (double)*((unsigned __int8 *)v45 + v95 + 24) / 255.0;
                if ( (_DWORD)v95 == (_DWORD)v42 )
                  v97 = v96 * v27;
                else
                  v97 = v96 * *((double *)this + v95 + 1023);
                v98 = v94 + v97;
                v99 = (unsigned int)(v63 + 9);
                v100 = (double)*((unsigned __int8 *)v45 + v99 + 24) / 255.0;
                if ( (_DWORD)v99 == (_DWORD)v42 )
                  v101 = v100 * v27;
                else
                  v101 = v100 * *((double *)this + v99 + 1023);
                v102 = v98 + v101;
                v103 = (unsigned int)(v63 + 10);
                v104 = (double)*((unsigned __int8 *)v45 + v103 + 24) / 255.0;
                if ( (_DWORD)v103 == (_DWORD)v42 )
                  v105 = v104 * v27;
                else
                  v105 = v104 * *((double *)this + v103 + 1023);
                v106 = v102 + v105;
                v107 = (unsigned int)(v63 + 11);
                v108 = (double)*((unsigned __int8 *)v45 + v107 + 24) / 255.0;
                if ( (_DWORD)v107 == (_DWORD)v42 )
                  v109 = v108 * v27;
                else
                  v109 = v108 * *((double *)this + v107 + 1023);
                v110 = v106 + v109;
                v111 = (unsigned int)(v63 + 12);
                v112 = (double)*((unsigned __int8 *)v45 + v111 + 24) / 255.0;
                if ( (_DWORD)v111 == (_DWORD)v42 )
                  v113 = v112 * v27;
                else
                  v113 = v112 * *((double *)this + v111 + 1023);
                v114 = v110 + v113;
                v115 = (unsigned int)(v63 + 13);
                v116 = (double)*((unsigned __int8 *)v45 + v115 + 24) / 255.0;
                if ( (_DWORD)v115 == (_DWORD)v42 )
                  v117 = v116 * v27;
                else
                  v117 = v116 * *((double *)this + v115 + 1023);
                v118 = v114 + v117;
                v119 = (unsigned int)(v63 + 14);
                v120 = (double)*((unsigned __int8 *)v45 + v119 + 24) / 255.0;
                if ( (_DWORD)v119 == (_DWORD)v42 )
                  v121 = v120 * v27;
                else
                  v121 = v120 * *((double *)this + v119 + 1023);
                v63 = (unsigned int)(v63 + 15);
                v62 = v118 + v121;
              }
              while ( (unsigned int)v63 < 0x3C );
              v122 = v52 + *((double *)v40 + 29);
              *(_QWORD *)&v123 = COERCE_UNSIGNED_INT64(v122 - (v51 - v62)) & v43;
              if ( v123 < 1.0 || (v124 = 0, v123 / v51 < 0.1) )
                v124 = 1;
              if ( v44 && *((_QWORD *)this + 8) == v44 || !v124 )
              {
                LODWORD(v128) = *((unsigned __int8 *)v45 + v42 + 24);
                StringCchPrintfW(
                  &OutputString,
                  0x400u,
                  L"WDC: [%2d] Key 0x%08I64x Win %9.03lf His %9.03lf Dlt %9.03lf Tdt %9.03lf Err %9.03lf Cur %9.03lf Tot %"
                   "9.03lf Qtm %3d\n",
                  (unsigned int)v42,
                  v44,
                  v51,
                  v62,
                  v52,
                  v122,
                  v122 - (v51 - v62),
                  *((_QWORD *)v40 + 28),
                  v27,
                  v128);
                OutputDebugStringW(&OutputString);
              }
            }
          }
        }
        v53 = v52 + *((double *)v40 + 29);
        *((_QWORD *)v40 + 28) = 0;
        *((double *)v40 + 29) = v53;
      }
LABEL_78:
      v54 = *((double *)v40 + 23) / (double)*((unsigned __int16 *)v40 + 24);
      if ( *((double *)v40 + 22) != v54 )
      {
        *((_DWORD *)v40 + 42) |= 1u;
        *((double *)v40 + 22) = v54;
        if ( *(char **)v40 == v40 )
        {
          v56 = *(_QWORD *)v41;
          if ( *(char **)(*(_QWORD *)v41 + 8LL) != v41 )
            goto LABEL_12;
          *(_QWORD *)v40 = v56;
          *((_QWORD *)v40 + 1) = v41;
          *(_QWORD *)(v56 + 8) = v40;
          *(_QWORD *)v41 = v40;
        }
      }
      v40 = *(char **)v40;
      v3 = 0;
      if ( v40 == v41 )
        goto LABEL_80;
    }
  }
LABEL_54:
  if ( v129 && *((_DWORD *)this + 12) )
  {
    v23 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
    goto LABEL_35;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008b10  mov     rax, rsp
0x180008b13  mov     [rax+18h], rbx
0x180008b17  push    rbp
0x180008b18  push    rsi
0x180008b19  push    rdi
0x180008b1a  push    r12
0x180008b1c  push    r13
0x180008b1e  push    r14
0x180008b20  push    r15
0x180008b22  sub     rsp, 920h
0x180008b29  movaps  xmmword ptr [rax-48h], xmm6
0x180008b2d  movaps  xmmword ptr [rax-58h], xmm7
0x180008b31  movaps  xmmword ptr [rax-68h], xmm8
0x180008b36  movaps  xmmword ptr [rax-78h], xmm9
0x180008b3b  movaps  xmmword ptr [rax-88h], xmm10
0x180008b43  movaps  xmmword ptr [rax-98h], xmm11
0x180008b4b  movaps  xmmword ptr [rax-0A8h], xmm13
0x180008b53  movaps  xmmword ptr [rax-0B8h], xmm14
0x180008b5b  movaps  xmmword ptr [rax-0C8h], xmm15
0x180008b63  mov     rax, cs:__security_cookie
0x180008b6a  xor     rax, rsp
0x180008b6d  mov     [rsp+958h+var_D8], rax
0x180008b75  movzx   eax, word ptr [rdx+28h]
0x180008b79  xor     esi, esi
0x180008b7b  mov     r12, [rdx+60h]
0x180008b7f  mov     r13, rcx
0x180008b82  mov     [rsp+958h+var_8E8], esi
0x180008b86  cmp     ax, 64h ; 'd'
0x180008b8a  jnz     loc_180008DE3
0x180008b90  mov     rcx, [rcx+2480h]
0x180008b97  cmp     [rcx+30h], esi
0x180008b9a  jz      short loc_180008BAE
0x180008b9c  add     rcx, 8; lpCriticalSection
0x180008ba0  call    cs:__imp_EnterCriticalSection
0x180008ba6  mov     [rsp+958h+var_8E8], 1
0x180008bae  xor     r15d, r15d
0x180008bb1  cmp     [r12+4], esi
0x180008bb6  jbe     loc_180008D68
0x180008bbc  nop     dword ptr [rax+00h]
0x180008bc0  lea     r9, [r15+r15*2]
0x180008bc4  mov     r8d, [r12+r9*8+24h]
0x180008bc9  imul    ecx, r8d, 10DCDh
0x180008bd0  imul    eax, r8d, 41C64E6Dh
0x180008bd7  mov     [rsp+958h+var_8E0], r9
0x180008bdc  inc     ecx
0x180008bde  add     eax, 3039h
0x180008be3  and     ecx, 0FFFF0000h
0x180008be9  shr     eax, 10h
0x180008bec  or      ecx, eax
0x180008bee  mov     eax, 824A4E61h
0x180008bf3  mul     ecx
0x180008bf5  shr     edx, 8
0x180008bf8  imul    eax, edx, 1F7h
0x180008bfe  mov     rdx, [r13+2480h]
0x180008c05  add     rdx, 68h ; 'h'
0x180008c09  sub     ecx, eax
0x180008c0b  movsxd  rcx, ecx
0x180008c0e  shl     rcx, 4
0x180008c12  add     rdx, rcx
0x180008c15  mov     rbx, [rdx]
0x180008c18  nop     dword ptr [rax+rax+00000000h]
0x180008c20  cmp     rbx, rdx
0x180008c23  jz      loc_1800096DF
0x180008c29  mov     rax, [rbx]
0x180008c2c  cmp     [rbx+30h], r8
0x180008c30  jz      short loc_180008C37
0x180008c32  mov     rbx, rax
0x180008c35  jmp     short loc_180008C20
0x180008c37  cmp     [rax+8], rbx
0x180008c3b  jnz     short loc_180008C56
0x180008c3d  mov     rcx, [rbx+8]
0x180008c41  cmp     [rcx], rbx
0x180008c44  jnz     short loc_180008C56
0x180008c46  mov     [rcx], rax
0x180008c49  mov     [rax+8], rcx
0x180008c4d  mov     rax, [rdx]
0x180008c50  cmp     [rax+8], rdx
0x180008c54  jz      short loc_180008C5D
0x180008c56  mov     ecx, 3
0x180008c5b  int     29h; Win8: RtlFailFast(ecx)
0x180008c5d  mov     [rbx], rax
0x180008c60  xor     esi, esi
0x180008c62  mov     [rbx+8], rdx
0x180008c66  mov     [rax+8], rbx
0x180008c6a  mov     [rdx], rbx
0x180008c6d  mov     edi, [rbx+5Ch]
0x180008c70  test    edi, edi
0x180008c72  jz      loc_180008D5A
0x180008c78  mov     rax, [r12+r9*8+14h]
0x180008c7d  mov     ebp, esi
0x180008c7f  sub     rax, [rbx+68h]
0x180008c83  cmovns  rbp, rax
0x180008c87  xor     r14d, r14d
0x180008c8a  cmp     [r13+30h], esi
0x180008c8e  jz      short loc_180008CA0
0x180008c90  lea     rcx, [r13+8]; lpCriticalSection
0x180008c94  call    cs:__imp_EnterCriticalSection
0x180008c9a  mov     r14d, 1
0x180008ca0  imul    eax, edi, 41C64E6Dh
0x180008ca6  imul    ecx, edi, 10DCDh
0x180008cac  add     eax, 3039h
0x180008cb1  shr     eax, 10h
0x180008cb4  inc     ecx
0x180008cb6  and     ecx, 0FFFF0000h
0x180008cbc  or      ecx, eax
0x180008cbe  mov     eax, 824A4E61h
0x180008cc3  mul     ecx
0x180008cc5  shr     edx, 8
0x180008cc8  imul    eax, edx, 1F7h
0x180008cce  sub     ecx, eax
0x180008cd0  movsxd  rdx, ecx
0x180008cd3  shl     rdx, 4
0x180008cd7  add     rdx, 68h ; 'h'
0x180008cdb  add     rdx, r13
0x180008cde  mov     rax, [rdx]
0x180008ce1  cmp     rax, rdx
0x180008ce4  jz      loc_180009679
0x180008cea  mov     rcx, [rax]
0x180008ced  cmp     [rax+30h], rdi
0x180008cf1  jz      short loc_180008CF8
0x180008cf3  mov     rax, rcx
0x180008cf6  jmp     short loc_180008CE1
0x180008cf8  cmp     [rcx+8], rax
0x180008cfc  jnz     loc_180008C56
0x180008d02  mov     r8, [rax+8]
0x180008d06  cmp     [r8], rax
0x180008d09  jnz     loc_180008C56
0x180008d0f  mov     [r8], rcx
0x180008d12  mov     [rcx+8], r8
0x180008d16  mov     rcx, [rdx]
0x180008d19  cmp     [rcx+8], rdx
0x180008d1d  jnz     loc_180008C56
0x180008d23  mov     [rax], rcx
0x180008d26  mov     [rax+8], rdx
0x180008d2a  mov     [rcx+8], rax
0x180008d2e  mov     [rdx], rax
0x180008d31  add     [rax+0D0h], rbp
0x180008d38  cmp     dword ptr [r13+30h], 0
0x180008d3d  jz      short loc_180008D4E
0x180008d3f  test    r14d, r14d
0x180008d42  jz      short loc_180008D4E
0x180008d44  lea     rcx, [r13+8]; lpCriticalSection
0x180008d48  call    cs:__imp_LeaveCriticalSection
0x180008d4e  test    esi, esi
0x180008d50  js      loc_1800096A4
0x180008d56  add     [rbx+68h], rbp
0x180008d5a  inc     r15d
0x180008d5d  cmp     r15d, [r12+4]
0x180008d62  jb      loc_180008BC0
0x180008d68  cmp     [rsp+958h+var_8E8], 0
0x180008d6d  mov     rcx, [r13+2480h]
0x180008d74  jz      short loc_180008D86
0x180008d76  cmp     dword ptr [rcx+30h], 0
0x180008d7a  jz      short loc_180008D86
0x180008d7c  add     rcx, 8; lpCriticalSection
0x180008d80  call    cs:__imp_LeaveCriticalSection
0x180008d86  mov     eax, esi
0x180008d88  mov     rcx, [rsp+958h+var_D8]
0x180008d90  xor     rcx, rsp; StackCookie
0x180008d93  call    __security_check_cookie
0x180008d98  lea     r11, [rsp+958h+var_38]
0x180008da0  mov     rbx, [r11+50h]
0x180008da4  movaps  xmm6, xmmword ptr [r11-10h]
0x180008da9  movaps  xmm7, xmmword ptr [r11-20h]
0x180008dae  movaps  xmm8, xmmword ptr [r11-30h]
0x180008db3  movaps  xmm9, xmmword ptr [r11-40h]
0x180008db8  movaps  xmm10, xmmword ptr [r11-50h]
0x180008dbd  movaps  xmm11, xmmword ptr [r11-60h]
0x180008dc2  movaps  xmm13, xmmword ptr [r11-70h]
0x180008dc7  movaps  xmm14, xmmword ptr [r11-80h]
0x180008dcc  movaps  xmm15, xmmword ptr [r11-90h]
0x180008dd4  mov     rsp, r11
0x180008dd7  pop     r15
0x180008dd9  pop     r14
0x180008ddb  pop     r13
0x180008ddd  pop     r12
0x180008ddf  pop     rdi
0x180008de0  pop     rsi
0x180008de1  pop     rbp
0x180008de2  retn
0x180008de3  cmp     ax, 66h ; 'f'
0x180008de7  jnz     short loc_180008D86
0x180008de9  cmp     dword ptr [rcx+30h], 0
0x180008ded  xorps   xmm15, xmm15
0x180008df1  mov     rbx, [r12]
0x180008df5  xorps   xmm6, xmm6
0x180008df8  mov     rdi, [r12+8]
0x180008dfd  mov     esi, 1
0x180008e02  mov     eax, [r12+10h]
0x180008e07  mov     [rcx+1FF0h], eax
0x180008e0d  jz      short loc_180008E1D
0x180008e0f  add     rcx, 8; lpCriticalSection
0x180008e13  call    cs:__imp_EnterCriticalSection
0x180008e19  mov     [rsp+958h+var_8E8], esi
0x180008e1d  test    rdi, rdi
0x180008e20  jz      loc_180008EF8
0x180008e26  mov     rdx, [r13+58h]
0x180008e2a  lea     r9, [r13+58h]
0x180008e2e  cmp     rdx, r9
0x180008e31  jz      loc_180008EF8
0x180008e37  movsd   xmm2, cs:__real@4059000000000000
0x180008e3f  nop
0x180008e40  mov     rcx, [rdx+0C8h]
0x180008e47  mov     r8, [rdx+0C0h]
0x180008e4e  cmp     r8, rcx
0x180008e51  jl      loc_1800092E4
0x180008e57  mov     rax, r8
0x180008e5a  xorps   xmm1, xmm1
0x180008e5d  sub     rax, rcx
0x180008e60  xorps   xmm0, xmm0
0x180008e63  cvtsi2sd xmm1, rax
0x180008e68  test    rdi, rdi
0x180008e6b  js      loc_1800092BB
0x180008e71  cvtsi2sd xmm0, rdi
0x180008e76  divsd   xmm1, xmm0
0x180008e7a  mulsd   xmm1, xmm2
0x180008e7e  movsd   xmm0, qword ptr [rdx+0A0h]
0x180008e86  ucomisd xmm0, xmm1
0x180008e8a  mov     [rdx+0C8h], r8
0x180008e91  jp      loc_180008F29
0x180008e97  jnz     loc_180008F29
0x180008e9d  test    dword ptr [rdx+34h], 10000000h
0x180008ea4  addsd   xmm6, xmm1
0x180008ea8  movaps  xmm0, xmm1
0x180008eab  subsd   xmm0, qword ptr [rdx+0E0h]
0x180008eb3  movsd   qword ptr [rdx+0E0h], xmm1
0x180008ebb  addsd   xmm0, qword ptr [rdx+0B8h]
0x180008ec3  movsd   qword ptr [rdx+0B8h], xmm0
0x180008ecb  jnz     short loc_180008EE2
0x180008ecd  mov     rcx, [rdx+38h]
0x180008ed1  test    rcx, rcx
0x180008ed4  jnz     loc_180008F60
0x180008eda  mov     [rdx+38h], rbx
0x180008ede  mov     [rdx+30h], si
0x180008ee2  mov     rdx, [rdx]
0x180008ee5  cmp     rdx, r9
0x180008ee8  jnz     loc_180008E40
0x180008eee  comisd  xmm6, xmm2
0x180008ef2  ja      loc_1800092ED
0x180008ef8  mov     rcx, r13; this
0x180008efb  call    ?Update@WdcDataMonitor@@MEAAJXZ; WdcDataMonitor::Update(void)
0x180008f00  mov     esi, eax
0x180008f02  test    eax, eax
0x180008f04  jns     loc_180008FB2
0x180008f0a  cmp     [rsp+958h+var_8E8], 0
0x180008f0f  jz      loc_180008D86
0x180008f15  cmp     dword ptr [r13+30h], 0
0x180008f1a  jz      loc_180008D86
0x180008f20  lea     rcx, [r13+8]
0x180008f24  jmp     loc_180008D80
0x180008f29  or      [rdx+98h], esi
0x180008f2f  movsd   qword ptr [rdx+0A0h], xmm1
0x180008f37  cmp     [rdx], rdx
0x180008f3a  jnz     loc_180008E9D
0x180008f40  mov     rax, [r9]
0x180008f43  cmp     [rax+8], r9
0x180008f47  jnz     loc_180008C56
0x180008f4d  mov     [rdx], rax
0x180008f50  mov     [rdx+8], r9
0x180008f54  mov     [rax+8], rdx
0x180008f58  mov     [r9], rdx
0x180008f5b  jmp     loc_180008E9D
0x180008f60  mov     rax, rbx
0x180008f63  sub     rax, rcx
0x180008f66  cmp     rax, 4C4B40h
0x180008f6c  jle     loc_180008EE2
0x180008f72  nop     dword ptr [rax+00h]
0x180008f76  nop     word ptr [rax+rax+00000000h]
0x180008f80  movzx   eax, word ptr [rdx+30h]
0x180008f84  add     rcx, 989680h
0x180008f8b  mov     [rdx+38h], rcx
0x180008f8f  cmp     eax, [r13+23C0h]
0x180008f96  jnb     short loc_180008F9F
0x180008f98  inc     ax
0x180008f9b  mov     [rdx+30h], ax
0x180008f9f  mov     rax, rbx
0x180008fa2  sub     rax, rcx
0x180008fa5  cmp     rax, 4C4B40h
0x180008fab  jg      short loc_180008F80
0x180008fad  jmp     loc_180008EE2
0x180008fb2  mov     rbx, [r13+58h]
0x180008fb6  lea     r15, [r13+58h]
0x180008fba  mov     r14d, [r13+1FE4h]
0x180008fc1  cmp     rbx, r15
0x180008fc4  jz      loc_180009122
0x180008fca  movdqa  xmm10, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x180008fd3  movsd   xmm9, cs:__real@406fe00000000000
0x180008fdc  movsd   xmm11, cs:__real@3fa999999999999a
0x180008fe5  movsd   xmm14, cs:__real@3ff0000000000000
0x180008fee  movsd   xmm13, cs:__real@3fb999999999999a
0x180008ff7  nop     word ptr [rax+rax+00000000h]
0x180009000  cmp     r14d, 3Ch ; '<'
0x180009004  jnb     loc_1800090EC
0x18000900a  mov     r12, [rbx+20h]
0x18000900e  lea     rdi, [rbx+0D8h]
0x180009015  movzx   eax, byte ptr [rdi+r14+18h]
0x18000901b  xor     esi, esi
0x18000901d  movaps  xmm2, xmm15
0x180009021  movd    xmm0, eax
0x180009025  cvtdq2pd xmm0, xmm0
  ... truncated ...
```
