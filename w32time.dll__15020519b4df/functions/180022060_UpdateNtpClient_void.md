# UpdateNtpClient(void)

- ea: `0x180022060`
- end: `0x1800234fd`
- name: `?UpdateNtpClient@@YAJXZ`
- size: `5277`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023510`

## callees

- `0x1800144f0`
- `0x180015020`
- `0x180018138`
- `0x18001a714`
- `0x18001bbe0`
- `0x18001d9a0`
- `0x18002125c`
- `0x180022060`
- `0x18002f498`
- `0x180034a88`
- `0x180034c08`
- `0x180038424`
- `0x18003b8fc`
- `0x18003d270`
- `0x18003f49d`
- `0x180041168`
- `0x18004124c`
- `0x180041348`
- `0x180042934`
- `0x180046a88`
- `0x180048b58`
- `0x180053a7c`
- `0x1800548dc`
- `0x1800559bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800220bc`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180023471`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800220bc`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180023471`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002254f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022595`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002254f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022595`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002341a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002341a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023498`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023498`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002225c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002225c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002342a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002342a`
- `ntdll!RtlNtStatusToDosError` at `0x180022bfa`
- `ntdll!RtlNtStatusToDosError` at `0x180022d01`
- `ntdll!RtlNtStatusToDosError` at `0x180022bfa`
- `ntdll!RtlNtStatusToDosError` at `0x180022d01`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x180022bdd`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x180022bdd`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180022ce4`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180022ce4`

## string_xrefs

- `0x180022162`: `  AllowClientNonstandardModeCominations changed.\n`
- `0x180022339`: `  Compatibility flags changed. chng:%u\n`
- `0x180022a62`: `  ManualPeerListUpdate: add:%u del:%u noch:%u\n`
- `0x18002339d`: ` NtsNtpPeerListUpdate: add:%u del:%u noch:%u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 UpdateNtpClient(void)
{
  bool v0; // r14
  char *v1; // r13
  int v2; // r12d
  _NtpProvState *v3; // rdx
  int v4; // r8d
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  __int64 v8; // rcx
  _NtpProvState *v9; // rsi
  unsigned int v10; // esi
  unsigned __int64 v11; // rcx
  volatile signed __int32 *i; // rax
  int v13; // ecx
  unsigned int v14; // r15d
  volatile signed __int32 *j; // rax
  struct NtpClientConfig *v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // edx
  unsigned int v19; // r15d
  unsigned int v20; // r13d
  unsigned __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // edx
  __int64 v24; // r8
  unsigned int v25; // r8d
  char *v26; // r9
  volatile signed __int32 *k; // rax
  char v28; // r11
  unsigned int v29; // r10d
  __int64 v30; // rdx
  __int64 v31; // r10
  void *v32; // rcx
  void *v33; // rcx
  char *v34; // r15
  volatile signed __int32 **v35; // rdx
  __int64 IsPeer; // r13
  volatile signed __int32 **v37; // rdx
  __int64 v38; // rax
  volatile signed __int32 **v39; // rsi
  volatile signed __int32 *v40; // r14
  __int64 v41; // r13
  volatile signed __int32 ***v42; // rax
  char *v43; // r14
  volatile signed __int32 **v44; // r8
  volatile signed __int32 ***v45; // rax
  volatile signed __int32 **v46; // rax
  unsigned int v47; // r13d
  unsigned int v48; // r15d
  char *v49; // rax
  volatile signed __int32 **v50; // rdx
  __int64 v51; // rcx
  unsigned __int16 *m; // r9
  unsigned __int16 *v53; // rax
  int v54; // r8d
  int v55; // r10d
  __int64 v56; // rax
  __int64 v57; // r8
  unsigned __int16 *v58; // rcx
  __int64 v59; // r10
  int v60; // eax
  int v61; // r8d
  __int64 n; // r8
  unsigned __int16 *v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rax
  volatile signed __int32 **v66; // rdx
  volatile signed __int32 **v67; // rax
  _WORD *v68; // rsi
  __int64 v69; // rax
  int v70; // ecx
  volatile signed __int32 **v71; // rdx
  __int64 v72; // r13
  volatile signed __int32 **v73; // rdx
  __int64 v74; // rax
  volatile signed __int32 **v75; // rsi
  volatile signed __int32 **v76; // r14
  __int64 v77; // r12
  volatile signed __int32 ***v78; // rax
  char *v79; // r14
  volatile signed __int32 **v80; // r8
  volatile signed __int32 ***v81; // rax
  NTSTATUS v82; // eax
  signed int v83; // eax
  volatile signed __int32 **v84; // rax
  NTSTATUS v85; // eax
  signed int v86; // eax
  int v87; // ecx
  volatile signed __int32 **v88; // rdx
  __int64 v89; // r13
  volatile signed __int32 **v90; // rdx
  volatile signed __int32 *v91; // rax
  volatile signed __int32 **v92; // rsi
  volatile signed __int32 **v93; // r14
  char *v94; // r12
  volatile signed __int32 ***v95; // rax
  char *v96; // r14
  volatile signed __int32 **v97; // r8
  volatile signed __int32 ***v98; // rax
  int v99; // ecx
  volatile signed __int32 ***v100; // r13
  volatile signed __int32 **v101; // rdx
  volatile signed __int32 **v102; // rdx
  volatile signed __int32 **ii; // rsi
  volatile signed __int32 **v104; // r14
  volatile signed __int32 ***v105; // rax
  char *v106; // r14
  volatile signed __int32 **v107; // r8
  volatile signed __int32 ***v108; // rax
  __int64 v109; // rsi
  volatile signed __int32 **v110; // rax
  volatile signed __int32 **v111; // rax
  _NtpProvState *v112; // rax
  unsigned int v113; // r13d
  char *v114; // rax
  volatile signed __int32 **v115; // rsi
  __int64 v116; // r10
  unsigned __int16 *jj; // rcx
  unsigned __int16 *v118; // rax
  int v119; // edx
  int v120; // r8d
  __int64 v121; // rax
  __int64 kk; // r8
  unsigned __int16 *v123; // rdx
  __int64 v124; // rax
  __int64 v125; // rax
  volatile signed __int32 **v126; // rax
  const unsigned __int16 *v127; // rsi
  __int64 v128; // rax
  signed int LastError; // eax
  int v130; // eax
  struct NtpClientConfig *v132; // [rsp+28h] [rbp-230h] BYREF
  char v133; // [rsp+30h] [rbp-228h]
  char v134; // [rsp+31h] [rbp-227h]
  volatile signed __int32 **v135; // [rsp+38h] [rbp-220h] BYREF
  char v136; // [rsp+40h] [rbp-218h] BYREF
  char v137[3]; // [rsp+41h] [rbp-217h] BYREF
  unsigned int v138; // [rsp+44h] [rbp-214h]
  volatile signed __int32 **v139; // [rsp+48h] [rbp-210h] BYREF
  char *v140; // [rsp+50h] [rbp-208h]
  volatile signed __int32 **v141; // [rsp+58h] [rbp-200h] BYREF
  char *v142; // [rsp+60h] [rbp-1F8h]
  char *v143; // [rsp+68h] [rbp-1F0h]
  volatile signed __int32 **v144; // [rsp+70h] [rbp-1E8h] BYREF
  volatile signed __int32 **v145; // [rsp+78h] [rbp-1E0h]
  unsigned int v146; // [rsp+80h] [rbp-1D8h]
  unsigned int v147; // [rsp+84h] [rbp-1D4h]
  unsigned int v148; // [rsp+88h] [rbp-1D0h]
  unsigned int v149; // [rsp+8Ch] [rbp-1CCh]
  unsigned int v150; // [rsp+90h] [rbp-1C8h]
  volatile signed __int32 **v151; // [rsp+98h] [rbp-1C0h] BYREF
  volatile signed __int32 **v152; // [rsp+A0h] [rbp-1B8h] BYREF
  int v153; // [rsp+A8h] [rbp-1B0h]
  volatile signed __int32 **v154; // [rsp+B0h] [rbp-1A8h] BYREF
  volatile signed __int32 **v155; // [rsp+B8h] [rbp-1A0h] BYREF
  volatile signed __int32 **v156; // [rsp+C0h] [rbp-198h] BYREF
  volatile signed __int32 **v157; // [rsp+C8h] [rbp-190h] BYREF
  volatile signed __int32 **v158; // [rsp+D0h] [rbp-188h] BYREF
  __int64 v159; // [rsp+D8h] [rbp-180h]
  int v160; // [rsp+E0h] [rbp-178h]
  int v161; // [rsp+E4h] [rbp-174h]
  volatile signed __int32 **v162; // [rsp+E8h] [rbp-170h]
  volatile signed __int32 **v163; // [rsp+F0h] [rbp-168h]
  volatile signed __int32 *v164; // [rsp+F8h] [rbp-160h] BYREF
  int v165; // [rsp+100h] [rbp-158h]
  int v166; // [rsp+104h] [rbp-154h]
  __int64 v167; // [rsp+108h] [rbp-150h]
  volatile signed __int32 *v168; // [rsp+110h] [rbp-148h]
  __int64 v169; // [rsp+118h] [rbp-140h]
  volatile signed __int32 *v170; // [rsp+120h] [rbp-138h]
  volatile signed __int32 *v171; // [rsp+128h] [rbp-130h] BYREF
  volatile signed __int32 **v172; // [rsp+130h] [rbp-128h]
  int v173; // [rsp+138h] [rbp-120h]
  volatile signed __int32 *v174; // [rsp+140h] [rbp-118h] BYREF
  int v175; // [rsp+148h] [rbp-110h]
  volatile signed __int32 **v176; // [rsp+150h] [rbp-108h]
  volatile signed __int32 *v177; // [rsp+158h] [rbp-100h] BYREF
  volatile signed __int32 **v178; // [rsp+160h] [rbp-F8h]
  volatile signed __int32 *v179; // [rsp+168h] [rbp-F0h] BYREF
  int v180; // [rsp+170h] [rbp-E8h]
  int v181; // [rsp+174h] [rbp-E4h]
  __int64 v182; // [rsp+178h] [rbp-E0h]
  int v183; // [rsp+180h] [rbp-D8h]
  int v184; // [rsp+184h] [rbp-D4h]
  int v185; // [rsp+188h] [rbp-D0h]
  int v186; // [rsp+18Ch] [rbp-CCh]
  volatile signed __int32 **v187; // [rsp+190h] [rbp-C8h]
  int v188; // [rsp+198h] [rbp-C0h]
  int v189; // [rsp+19Ch] [rbp-BCh]
  int v190; // [rsp+1A0h] [rbp-B8h]
  int v191; // [rsp+1A4h] [rbp-B4h]
  volatile signed __int32 *v192; // [rsp+1A8h] [rbp-B0h]
  volatile signed __int32 **v193; // [rsp+1B0h] [rbp-A8h]
  _QWORD v194[4]; // [rsp+1F0h] [rbp-68h] BYREF

  v0 = 0;
  v1 = (char *)g_pnpstate + 408;
  v140 = (char *)g_pnpstate + 408;
  v142 = (char *)g_pnpstate + 432;
  v132 = 0;
  v133 = 0;
  v134 = 0;
  v182 = _set_se_translator(SeTransFunc);
  if ( (int)ReadNtpClientConfig(&v132) < 0 )
  {
    v2 = 0;
    goto LABEL_218;
  }
  v2 = TrapThreads(1);
  if ( v2 >= 0 )
  {
    v134 = 1;
    v3 = g_pnpstate;
    *((_BYTE *)g_pnpstate + 256) = 0;
    *((_BYTE *)v3 + 257) = 0;
    *((_BYTE *)v3 + 258) = 0;
    v4 = *((_DWORD *)v132 + 14);
    if ( *((_BYTE *)v3 + 168) != (v4 != 0) )
    {
      *((_BYTE *)v3 + 168) = v4 != 0;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  AllowClientNonstandardModeCominations changed.\n");
      v3 = g_pnpstate;
    }
    *((_DWORD *)v3 + 65) = *((_DWORD *)v132 + 29);
    v5 = *((_DWORD *)v132 + 19);
    if ( *((_DWORD *)v3 + 48) != v5 )
    {
      *((_DWORD *)v3 + 48) = v5;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  EventLogFlags changed.\n");
      v3 = g_pnpstate;
    }
    *((_DWORD *)v3 + 60) = *((_DWORD *)v132 + 34);
    v6 = *((_DWORD *)v132 + 20);
    if ( *((_DWORD *)v3 + 49) != v6 )
    {
      *((_DWORD *)v3 + 49) = v6;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  LargeSampleSkew changed.\n");
      v3 = g_pnpstate;
    }
    *((_DWORD *)v3 + 61) = *((_DWORD *)v132 + 35);
    v7 = *((_DWORD *)v132 + 21);
    if ( *((_DWORD *)v3 + 51) != v7 )
    {
      *((_DWORD *)v3 + 51) = v7;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  SignatureAuthAllowed changed.\n");
      v3 = g_pnpstate;
    }
    *((_DWORD *)v3 + 63) = *((_DWORD *)v132 + 36);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 328));
    v133 = 1;
    v8 = *((unsigned int *)v132 + 18);
    v9 = g_pnpstate;
    if ( *((_DWORD *)g_pnpstate + 47) != (_DWORD)v8 )
    {
      *((_DWORD *)g_pnpstate + 47) = v8;
      v10 = 0;
      v165 = 0;
      v11 = 10000000 * v8;
      for ( i = *(volatile signed __int32 **)v1; ; i += 2 )
      {
        v192 = i;
        v135 = (volatile signed __int32 **)*((_QWORD *)v1 + 1);
        if ( i == (volatile signed __int32 *)v135 )
          break;
        v22 = *(_QWORD *)(*(_QWORD *)i + 8LL);
        if ( !*(_DWORD *)(v22 + 48) && (*(_BYTE *)(v22 + 80) & 1) != 0 && *(_QWORD *)(v22 + 280) > v11 )
        {
          *(_QWORD *)(v22 + 280) = v11;
          v165 = ++v10;
          v0 = 1;
        }
        v135 = (volatile signed __int32 **)i;
      }
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  SpecialPollInterval disabled. chng:%u\n", v10);
      v9 = g_pnpstate;
    }
    *((_DWORD *)v9 + 59) = *((_DWORD *)v132 + 33);
    v13 = *((_DWORD *)v132 + 17);
    if ( *((_DWORD *)v9 + 46) != v13 )
    {
      *((_DWORD *)v9 + 46) = v13;
      v14 = 0;
      v161 = 0;
      for ( j = *(volatile signed __int32 **)v1; ; j += 2 )
      {
        v168 = j;
        v135 = (volatile signed __int32 **)*((_QWORD *)v1 + 1);
        if ( j == (volatile signed __int32 *)v135 )
          break;
        v23 = *((_DWORD *)v9 + 46);
        v24 = *(_QWORD *)(*(_QWORD *)j + 8LL);
        if ( *(_DWORD *)(v24 + 60) != v23 )
        {
          *(_DWORD *)(v24 + 60) = v23;
          v0 = 1;
          v161 = ++v14;
        }
        v135 = (volatile signed __int32 **)j;
      }
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  Compatibility flags changed. chng:%u\n", v14);
      v9 = g_pnpstate;
    }
    *((_DWORD *)v9 + 58) = *((_DWORD *)v132 + 32);
    v16 = v132;
    v17 = *((unsigned int *)v132 + 15);
    if ( *((_QWORD *)v9 + 22) != *(_QWORD *)((char *)v132 + 60) )
    {
      *((_DWORD *)v9 + 44) = v17;
      v18 = *((_DWORD *)v132 + 16);
      *((_DWORD *)v9 + 45) = v18;
      v19 = 0;
      v166 = 0;
      v20 = 0;
      v160 = 0;
      v21 = 600000000 * v17;
      v169 = 600000000 * v17;
      while ( 1 )
      {
        v138 = v18;
        if ( v18 <= 1 )
          break;
        v21 *= 2LL;
        v169 = v21;
        --v18;
      }
      v25 = 0;
      v138 = 0;
LABEL_45:
      if ( v25 < 2 )
      {
        v26 = (char *)v9 + 408;
        if ( v25 )
          v26 = (char *)v9 + 432;
        for ( k = *(volatile signed __int32 **)v26; ; k += 2 )
        {
          v170 = k;
          v135 = (volatile signed __int32 **)*((_QWORD *)v26 + 1);
          if ( k == (volatile signed __int32 *)v135 )
          {
            v138 = ++v25;
            goto LABEL_45;
          }
          v28 = 0;
          v29 = *((_DWORD *)v9 + 45);
          v30 = *(_QWORD *)(*(_QWORD *)k + 8LL);
          if ( *(_DWORD *)(v30 + 52) > v29 )
          {
            *(_DWORD *)(v30 + 52) = v29;
            v28 = 1;
          }
          v31 = *(_QWORD *)(*(_QWORD *)k + 8LL);
          if ( *(_QWORD *)(v31 + 280) > v21 )
            break;
          if ( v28 )
            goto LABEL_56;
          v166 = ++v19;
LABEL_58:
          v135 = (volatile signed __int32 **)k;
        }
        *(_QWORD *)(v31 + 280) = v21;
LABEL_56:
        v0 = 1;
        v160 = ++v20;
        goto LABEL_58;
      }
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ResolvePeerBackoff changed. fix:%u noch:%u\n", v20, v19);
      v9 = g_pnpstate;
      v16 = v132;
    }
    *((_DWORD *)v9 + 56) = *((_DWORD *)v16 + 30);
    *((_DWORD *)v9 + 57) = *((_DWORD *)v132 + 31);
    v32 = (void *)*((_QWORD *)v9 + 20);
    if ( v32 )
    {
      LocalFree(v32);
      v9 = g_pnpstate;
    }
    *((_QWORD *)v9 + 20) = *((_QWORD *)v132 + 2);
    *((_QWORD *)v132 + 2) = 0;
    *((_DWORD *)v9 + 53) = *((_DWORD *)v132 + 26);
    v33 = (void *)*((_QWORD *)v9 + 19);
    if ( v33 )
    {
      LocalFree(v33);
      v9 = g_pnpstate;
    }
    *((_QWORD *)v9 + 19) = *((_QWORD *)v132 + 1);
    *((_QWORD *)v132 + 1) = 0;
    *((_DWORD *)v9 + 52) = *((_DWORD *)v132 + 25);
    if ( (*(_BYTE *)v132 & 1) != 0 )
    {
      *((_DWORD *)v9 + 36) |= 1u;
      v147 = 0;
      v146 = 0;
      v47 = 0;
      v153 = 0;
      v48 = 0;
      v138 = 0;
LABEL_77:
      if ( v48 < 2 )
      {
        v49 = (char *)v9 + 408;
        if ( v48 )
          v49 = (char *)v9 + 432;
        v143 = v49;
        v50 = *(volatile signed __int32 ***)v49;
        v145 = *(volatile signed __int32 ***)v49;
        while ( 1 )
        {
          v156 = (volatile signed __int32 **)*((_QWORD *)v49 + 1);
          if ( v50 == v156 )
          {
            v138 = ++v48;
            goto LABEL_77;
          }
          v51 = *((_QWORD *)*v50 + 1);
          if ( !*(_DWORD *)(v51 + 48) )
            break;
LABEL_112:
          v156 = v50++;
          v145 = v50;
          v49 = v143;
        }
        for ( m = (unsigned __int16 *)*((_QWORD *)v132 + 3); *m; m += v56 + 1 )
        {
          v53 = m;
          do
          {
            v54 = *(unsigned __int16 *)((char *)v53 + *(_QWORD *)(v51 + 72) - (_QWORD)m);
            v55 = *v53 - v54;
            if ( v55 )
              break;
            ++v53;
          }
          while ( v54 );
          if ( !v55 )
          {
            while ( 1 )
            {
              v145 = ++v50;
              v193 = (volatile signed __int32 **)*((_QWORD *)v143 + 1);
              if ( v50 == v193 )
                break;
              v57 = *((_QWORD *)*v50 + 1);
              if ( *(_DWORD *)(v57 + 48) )
                break;
              v163 = v50 - 1;
              v58 = *(unsigned __int16 **)(v57 + 72);
              v59 = *(_QWORD *)(*((_QWORD *)*(v50 - 1) + 1) + 72LL) - (_QWORD)v58;
              do
              {
                v60 = *(unsigned __int16 *)((char *)v58 + v59);
                v61 = *v58 - v60;
                if ( v61 )
                  break;
                ++v58;
              }
              while ( v60 );
              if ( v61 )
                break;
              v153 = ++v47;
            }
            for ( n = 0; ; n += v64 + 1 )
            {
              v63 = &m[n];
              if ( !*v63 )
                break;
              v64 = -1;
              do
                ++v64;
              while ( v63[v64] );
            }
            v65 = -1;
            do
              ++v65;
            while ( m[v65] );
            memmove_0(m, &m[v65 + 1], 2 * (n - (v65 + 1)) + 2);
            v153 = ++v47;
            v66 = v145;
            goto LABEL_111;
          }
          v56 = -1;
          do
            ++v56;
          while ( m[v56] );
        }
        if ( v48
          || (v136 = 0,
              v151 = &v174,
              v67 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v174, v50),
              v2 = Reachability_RemovePeer(v67, &v136),
              v2 >= 0) )
        {
          v66 = *(volatile signed __int32 ***)std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(
                                                v143,
                                                &v144);
          v145 = v66;
          ++v146;
          v0 = 1;
          v9 = g_pnpstate;
LABEL_111:
          v156 = v66;
          v50 = v66 - 1;
          v145 = v50;
          goto LABEL_112;
        }
        goto LABEL_212;
      }
      v68 = (_WORD *)*((_QWORD *)v132 + 3);
      while ( *v68 )
      {
        v2 = AddNewPendingManualPeer(v68, gc_toZero, 0);
        if ( v2 < 0 )
          goto LABEL_212;
        v69 = -1;
        do
          ++v69;
        while ( v68[v69] );
        v68 += v69 + 1;
        v0 = 1;
        ++v147;
      }
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ManualPeerListUpdate: add:%u del:%u noch:%u\n", v147, v146, v47);
      v34 = v140;
    }
    else
    {
      if ( (*((_BYTE *)v9 + 144) & 1) == 0 )
      {
        v34 = v140;
        goto LABEL_123;
      }
      *((_DWORD *)v9 + 36) &= ~1u;
      v189 = 0;
      v34 = v140;
      v135 = (volatile signed __int32 **)*((_QWORD *)v140 + 1);
      v35 = v135;
      v135 = *(volatile signed __int32 ***)v140;
      IsPeer = std::count_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
                 v135,
                 v35,
                 0);
      v190 = 0;
      v135 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
      v37 = v135;
      v135 = *(volatile signed __int32 ***)v142;
      v38 = std::count_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
              v135,
              v37,
              0);
      v145 = (volatile signed __int32 **)v38;
      v39 = *(volatile signed __int32 ***)v34;
      v172 = *(volatile signed __int32 ***)v34;
      while ( 1 )
      {
        v40 = (volatile signed __int32 *)*((_QWORD *)v34 + 1);
        v135 = (volatile signed __int32 **)v40;
        if ( v39 == (volatile signed __int32 **)v40 )
          break;
        if ( !*(_DWORD *)(*((_QWORD *)*v39 + 1) + 48LL) )
        {
          v156 = &v171;
          v46 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v171, v39);
          v2 = Reachability_RemovePeer(v46, 0);
          if ( v2 < 0 )
            goto LABEL_212;
        }
        v151 = v39++;
        v172 = v39;
        v38 = (__int64)v145;
      }
      v41 = v38 + IsPeer;
      v191 = 0;
      v135 = (volatile signed __int32 **)v40;
      v135 = *(volatile signed __int32 ***)v34;
      v42 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
              &v151,
              v135,
              (volatile signed __int32 **)v40,
              0);
      std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v34, &v135, *v42);
      v43 = v142;
      v151 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
      v173 = 0;
      v151 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
      v44 = v151;
      v151 = *(volatile signed __int32 ***)v142;
      v45 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
              &v156,
              v151,
              v44,
              0);
      std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v43, &v151, *v45);
      v0 = v41 != 0;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  ManualPeerList disabled. del:%I64u\n", v41);
    }
    v9 = g_pnpstate;
LABEL_123:
    v70 = *((_DWORD *)v9 + 36);
    if ( (*(_DWORD *)v132 & 2) != 0 )
    {
      if ( (v70 & 2) == 0 )
      {
        *((_DWORD *)v9 + 36) = v70 | 2;
        *((_DWORD *)v9 + 43) = *((_DWORD *)v132 + 10);
        *((_DWORD *)v9 + 55) = *((_DWORD *)v132 + 28);
        v2 = AddNewPendingDomHierPeer(0);
        if ( v2 < 0 )
          goto LABEL_212;
        v0 = 1;
        v85 = LsaRegisterPolicyChangeNotification(PolicyNotifyServerRoleInformation, *((HANDLE *)g_pnpstate + 12));
        v2 = v85;
        if ( v85 )
        {
          v86 = RtlNtStatusToDosError(v85);
          v2 = v86;
          if ( v86 > 0 )
            v2 = (unsigned __int16)v86 | 0x80070000;
          goto LABEL_212;
        }
        goto LABEL_147;
      }
      *((_DWORD *)v9 + 55) = *((_DWORD *)v132 + 28);
      v87 = *((_DWORD *)v132 + 10);
      if ( *((_DWORD *)v9 + 43) != v87 )
      {
        *((_DWORD *)v9 + 43) = v87;
        v188 = 1;
        v139 = (volatile signed __int32 **)*((_QWORD *)v34 + 1);
        v88 = v139;
        v139 = *(volatile signed __int32 ***)v34;
        v89 = std::count_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
                v139,
                v88,
                1);
        v184 = 1;
        v139 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
        v90 = v139;
        v139 = *(volatile signed __int32 ***)v142;
        v91 = (volatile signed __int32 *)std::count_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
                                           v139,
                                           v90,
                                           1);
        v164 = v91;
        v92 = *(volatile signed __int32 ***)v34;
        v178 = *(volatile signed __int32 ***)v34;
        while ( 1 )
        {
          v93 = (volatile signed __int32 **)*((_QWORD *)v34 + 1);
          v139 = v93;
          if ( v92 == v93 )
            break;
          if ( *(_DWORD *)(*((_QWORD *)*v92 + 1) + 48LL) == 1 )
          {
            v141 = &v177;
            v110 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v177, v92);
            v2 = Reachability_RemovePeer(v110, 0);
            if ( v2 < 0 )
              goto LABEL_212;
          }
          v155 = v92++;
          v178 = v92;
          v91 = v164;
        }
        v94 = (char *)v91 + v89;
        v185 = 1;
        v139 = v93;
        v139 = *(volatile signed __int32 ***)v34;
        v95 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
                &v155,
                v139,
                v93,
                1);
        std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v34, &v139, *v95);
        v96 = v142;
        v155 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
        v186 = 1;
        v155 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
        v97 = v155;
        v155 = *(volatile signed __int32 ***)v142;
        v98 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
                &v141,
                v155,
                v97,
                1);
        std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v96, &v155, *v98);
        if ( (unsigned __int8)FileLogAllowEntry(58) )
          FileLogAdd(L"  DomainHierarchy: CrossSiteSyncFlags changed. Redetecting. del:%I64u\n", v94);
        v2 = AddNewPendingDomHierPeer(0);
        if ( v2 < 0 )
          goto LABEL_212;
        v0 = 1;
LABEL_147:
        v9 = g_pnpstate;
      }
    }
    else if ( (v70 & 2) != 0 )
    {
      *((_DWORD *)v9 + 36) = v70 & 0xFFFFFFFD;
      v175 = 1;
      v144 = (volatile signed __int32 **)*((_QWORD *)v34 + 1);
      v71 = v144;
      v144 = *(volatile signed __int32 ***)v34;
      v72 = std::count_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
              v144,
              v71,
              1);
      v180 = 1;
      v144 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
      v73 = v144;
      v144 = *(volatile signed __int32 ***)v142;
      v74 = std::count_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
              v144,
              v73,
              1);
      v163 = (volatile signed __int32 **)v74;
      v75 = *(volatile signed __int32 ***)v34;
      v176 = *(volatile signed __int32 ***)v34;
      while ( 1 )
      {
        v76 = (volatile signed __int32 **)*((_QWORD *)v34 + 1);
        v144 = v76;
        if ( v75 == v76 )
          break;
        if ( *(_DWORD *)(*((_QWORD *)*v75 + 1) + 48LL) == 1 )
        {
          v139 = &v164;
          v84 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v164, v75);
          v2 = Reachability_RemovePeer(v84, 0);
          if ( v2 < 0 )
            goto LABEL_212;
        }
        v154 = v75++;
        v176 = v75;
        v74 = (__int64)v163;
      }
      v77 = v74 + v72;
      v181 = 1;
      v144 = v76;
      v144 = *(volatile signed __int32 ***)v34;
      v78 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
              &v154,
              v144,
              v76,
              1);
      std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v34, &v144, *v78);
      v79 = v142;
      v154 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
      v183 = 1;
      v154 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
      v80 = v154;
      v154 = *(volatile signed __int32 ***)v142;
      v81 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
              &v139,
              v154,
              v80,
              1);
      std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v79, &v154, *v81);
      v0 = v77 != 0;
      if ( (unsigned __int8)FileLogAllowEntry(58) )
        FileLogAdd(L"  DomainHierarchy disabled. del:%I64u\n", v77);
      v82 = LsaUnregisterPolicyChangeNotification(PolicyNotifyServerRoleInformation, *((HANDLE *)g_pnpstate + 12));
      v2 = v82;
      if ( v82 )
      {
        v83 = RtlNtStatusToDosError(v82);
        v2 = v83;
        if ( v83 > 0 )
          v2 = (unsigned __int16)v83 | 0x80070000;
        goto LABEL_212;
      }
      goto LABEL_147;
    }
    if ( !*((_BYTE *)v9 + 50) )
      goto LABEL_203;
    if ( (*(_DWORD *)v132 & 0x10) == 0 )
    {
      v99 = *((_DWORD *)v9 + 36);
      if ( (v99 & 0x10) != 0 )
      {
        *((_DWORD *)v9 + 36) = v99 & 0xFFFFFFEF;
        StopNts();
        LODWORD(v167) = 4;
        v100 = (volatile signed __int32 ***)v140;
        v141 = (volatile signed __int32 **)*((_QWORD *)v140 + 1);
        v101 = v141;
        v141 = *(volatile signed __int32 ***)v140;
        v167 = std::count_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
                 v141,
                 v101,
                 4);
        LODWORD(v159) = 4;
        v141 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
        v102 = v141;
        v141 = *(volatile signed __int32 ***)v142;
        v159 = std::count_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
                 v141,
                 v102,
                 4);
        for ( ii = *v100; ; ++ii )
        {
          v187 = ii;
          v104 = v100[1];
          v141 = v104;
          if ( ii == v104 )
            break;
          if ( *(_DWORD *)(*((_QWORD *)*ii + 1) + 48LL) == 4 )
          {
            v158 = &v179;
            v111 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>(&v179, ii);
            v2 = Reachability_RemovePeer(v111, 0);
            if ( v2 < 0 )
              goto LABEL_212;
          }
          v152 = ii;
        }
        LODWORD(v143) = 4;
        v141 = v104;
        v141 = *v100;
        v105 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
                 &v152,
                 v141,
                 v104,
                 4);
        std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v100, &v141, *v105);
        v106 = v142;
        v152 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
        LODWORD(v140) = 4;
        v152 = (volatile signed __int32 **)*((_QWORD *)v142 + 1);
        v107 = v152;
        v152 = *(volatile signed __int32 ***)v142;
        v108 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>,IsPeerType>(
                 &v158,
                 v152,
                 v107,
                 4);
        std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(v106, &v152, *v108);
        v109 = v167 + v159;
        v0 = v167 + v159 != 0;
        if ( (unsigned __int8)FileLogAllowEntry(58) )
          FileLogAdd(L"Nts disabled. del:%I64u\n", v109);
        goto LABEL_155;
      }
      goto LABEL_203;
    }
    v2 = InitializeNts();
    if ( v2 >= 0 )
    {
      v112 = g_pnpstate;
      *((_DWORD *)g_pnpstate + 36) |= 0x10u;
      v150 = 0;
      v149 = 0;
      v148 = 0;
      v113 = 0;
      v138 = 0;
      while ( v113 < 2 )
      {
        if ( v113 )
          v114 = (char *)v112 + 432;
        else
          v114 = (char *)v112 + 408;
        v143 = v114;
        v115 = *(volatile signed __int32 ***)v114;
        v162 = *(volatile signed __int32 ***)v114;
        while ( 1 )
        {
          v158 = (volatile signed __int32 **)*((_QWORD *)v114 + 1);
          if ( v115 == v158 )
            break;
          v116 = *((_QWORD *)*v115 + 1);
          if ( *(_DWORD *)(v116 + 48) == 4 )
          {
            for ( jj = (unsigned __int16 *)*((_QWORD *)v132 + 6); *jj; jj += v121 + 1 )
            {
              v118 = jj;
              do
              {
                v119 = *(unsigned __int16 *)((char *)v118 + *(_QWORD *)(v116 + 72) - (_QWORD)jj);
                v120 = *v118 - v119;
                if ( v120 )
                  break;
                ++v118;
              }
              while ( v119 );
              if ( !v120 )
              {
                for ( kk = 0; ; kk += v124 + 1 )
                {
                  v123 = &jj[kk];
                  if ( !*v123 )
                    break;
                  v124 = -1;
                  do
                    ++v124;
                  while ( v123[v124] );
                }
                v125 = -1;
                do
                  ++v125;
                while ( jj[v125] );
                memmove_0(jj, &jj[v125 + 1], 2 * (kk - (v125 + 1)) + 2);
                ++v148;
                goto LABEL_194;
              }
              v121 = -1;
              do
                ++v121;
              while ( jj[v121] );
            }
            if ( !v113 )
            {
              v137[0] = 0;
              v152 = (volatile signed __int32 **)&v135;
              v126 = AutoPtr<NtpPeer>::AutoPtr<NtpPeer>((volatile signed __int32 **)&v135, v115);
              v2 = Reachability_RemovePeer(v126, v137);
              if ( v2 < 0 )
                goto LABEL_212;
            }
            std::wstring::wstring(v194, *(_QWORD *)(*((_QWORD *)*v115 + 1) + 72LL));
            v2 = ClearNtsServer(v194);
            if ( v2 < 0 )
            {
              std::wstring::~wstring((__int64)v194);
              goto LABEL_212;
            }
            v158 = *(volatile signed __int32 ***)std::vector<AutoPtr<NtpPeer>,MyThrowingAllocator<AutoPtr<NtpPeer>>>::erase(
                                                   v143,
                                                   &v157);
            v115 = v158 - 1;
            v162 = v158 - 1;
            ++v149;
            v0 = 1;
            std::wstring::~wstring((__int64)v194);
          }
LABEL_194:
          v158 = v115++;
          v162 = v115;
          v114 = v143;
        }
        v138 = ++v113;
        v112 = g_pnpstate;
      }
      v127 = (const unsigned __int16 *)*((_QWORD *)v132 + 6);
      while ( *v127 )
      {
        v2 = AddNewPendingNtsNtpPeer(v127, gc_toZero, 0);
        if ( v2 < 0 )
          goto LABEL_212;
        v128 = -1;
        do
          ++v128;
        while ( v127[v128] );
        v127 += v128 + 1;
        v0 = 1;
        ++v150;
      }
      if ( !(unsigned __int8)FileLogAllowEntry(58) )
      {
        v100 = (volatile signed __int32 ***)v140;
LABEL_155:
        v9 = g_pnpstate;
LABEL_204:
        if ( !v0
          || (*((_BYTE *)v9 + 480) = *(_DWORD *)v132 != 0,
              v157 = (volatile signed __int32 **)*((_QWORD *)v142 + 1),
              v157 = *(volatile signed __int32 ***)v142,
              std::sort<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>>(v157),
              v157 = v100[1],
              v157 = *v100,
              std::sort<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<AutoPtr<NtpPeer>>>>>(v157),
              SetEvent(*((HANDLE *)g_pnpstate + 58))) )
        {
          _set_se_translator(v182);
          if ( v2 >= 0 )
            v2 = 0;
        }
        else
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
        }
        goto LABEL_212;
      }
      FileLogAdd(L" NtsNtpPeerListUpdate: add:%u del:%u noch:%u\n", v150, v149, v148);
      v9 = g_pnpstate;
LABEL_203:
      v100 = (volatile signed __int32 ***)v140;
      goto LABEL_204;
    }
LABEL_212:
    if ( v133 )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
    if ( v134 == 1 )
    {
      v130 = TrapThreads(0);
      if ( v130 < 0 && v2 >= 0 )
        v2 = v130;
    }
  }
LABEL_218:
  if ( v132 )
    FreeNtpClientConfig(v132);
  if ( v2 < 0 )
    StopNtpClient();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180022060  push    rbx
0x180022062  push    rsi
0x180022063  push    rdi
0x180022064  push    r12
0x180022066  push    r13
0x180022068  push    r14
0x18002206a  push    r15
0x18002206c  sub     rsp, 220h
0x180022073  mov     rax, cs:__security_cookie
0x18002207a  xor     rax, rsp
0x18002207d  mov     [rsp+258h+var_48], rax
0x180022085  xor     ebx, ebx
0x180022087  mov     r14b, bl
0x18002208a  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180022091  lea     r13, [rax+198h]
0x180022098  mov     [rsp+258h+var_208], r13
0x18002209d  add     rax, 1B0h
0x1800220a3  mov     [rsp+258h+var_1F8], rax
0x1800220a8  mov     [rsp+258h+var_230], rbx
0x1800220ad  mov     [rsp+258h+var_228], bl
0x1800220b1  mov     [rsp+258h+var_227], bl
0x1800220b5  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800220bc  call    cs:__imp__set_se_translator
0x1800220c3  nop     dword ptr [rax+rax+00h]
0x1800220c8  mov     [rsp+258h+var_E0], rax
0x1800220d0  lea     rcx, [rsp+258h+var_230]; struct NtpClientConfig **
0x1800220d5  call    ?ReadNtpClientConfig@@YAJPEAPEAUNtpClientConfig@@@Z; ReadNtpClientConfig(NtpClientConfig * *)
0x1800220da  mov     [rsp+258h+var_234], eax
0x1800220de  test    eax, eax
0x1800220e0  jns     short loc_1800220EE
0x1800220e2  mov     r12d, ebx
0x1800220e5  mov     [rsp+258h+var_234], ebx
0x1800220e9  jmp     loc_1800234BD
0x1800220ee  mov     edi, 1
0x1800220f3  mov     ecx, edi; int
0x1800220f5  call    ?TrapThreads@@YAJH@Z; TrapThreads(int)
0x1800220fa  mov     r12d, eax
0x1800220fd  mov     [rsp+258h+var_234], eax
0x180022101  test    eax, eax
0x180022103  jns     short loc_18002210A
0x180022105  jmp     loc_1800234BD
0x18002210a  mov     [rsp+258h+var_227], dil
0x18002210f  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180022116  mov     [rdx+100h], bl
0x18002211c  mov     [rdx+101h], bl
0x180022122  mov     [rdx+102h], bl
0x180022128  mov     rax, [rsp+258h+var_230]
0x18002212d  mov     r8d, [rax+38h]
0x180022131  mov     ecx, ebx
0x180022133  test    r8d, r8d
0x180022136  setnz   cl
0x180022139  movzx   eax, byte ptr [rdx+0A8h]
0x180022140  mov     r15d, 3Ah ; ':'
0x180022146  cmp     eax, ecx
0x180022148  jz      short loc_180022175
0x18002214a  test    r8d, r8d
0x18002214d  setnz   al
0x180022150  mov     [rdx+0A8h], al
0x180022156  mov     ecx, r15d
0x180022159  call    FileLogAllowEntry
0x18002215e  test    al, al
0x180022160  jz      short loc_18002216E
0x180022162  lea     rcx, aAllowclientnon; "  AllowClientNonstandardModeCominations"...
0x180022169  call    FileLogAdd
0x18002216e  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180022175  mov     rax, [rsp+258h+var_230]
0x18002217a  mov     ecx, [rax+74h]
0x18002217d  mov     [rdx+104h], ecx
0x180022183  mov     rax, [rsp+258h+var_230]
0x180022188  mov     ecx, [rax+4Ch]
0x18002218b  cmp     [rdx+0C0h], ecx
0x180022191  jz      short loc_1800221B8
0x180022193  mov     [rdx+0C0h], ecx
0x180022199  mov     ecx, r15d
0x18002219c  call    FileLogAllowEntry
0x1800221a1  test    al, al
0x1800221a3  jz      short loc_1800221B1
0x1800221a5  lea     rcx, aEventlogflagsC_0; "  EventLogFlags changed.\n"
0x1800221ac  call    FileLogAdd
0x1800221b1  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800221b8  mov     rax, [rsp+258h+var_230]
0x1800221bd  mov     ecx, [rax+88h]
0x1800221c3  mov     [rdx+0F0h], ecx
0x1800221c9  mov     rax, [rsp+258h+var_230]
0x1800221ce  mov     ecx, [rax+50h]
0x1800221d1  cmp     [rdx+0C4h], ecx
0x1800221d7  jz      short loc_1800221FE
0x1800221d9  mov     [rdx+0C4h], ecx
0x1800221df  mov     ecx, r15d
0x1800221e2  call    FileLogAllowEntry
0x1800221e7  test    al, al
0x1800221e9  jz      short loc_1800221F7
0x1800221eb  lea     rcx, aLargesampleske_0; "  LargeSampleSkew changed.\n"
0x1800221f2  call    FileLogAdd
0x1800221f7  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800221fe  mov     rax, [rsp+258h+var_230]
0x180022203  mov     ecx, [rax+8Ch]
0x180022209  mov     [rdx+0F4h], ecx
0x18002220f  mov     rax, [rsp+258h+var_230]
0x180022214  mov     ecx, [rax+54h]
0x180022217  cmp     [rdx+0CCh], ecx
0x18002221d  jz      short loc_180022244
0x18002221f  mov     [rdx+0CCh], ecx
0x180022225  mov     ecx, r15d
0x180022228  call    FileLogAllowEntry
0x18002222d  test    al, al
0x18002222f  jz      short loc_18002223D
0x180022231  lea     rcx, aSignatureautha_0; "  SignatureAuthAllowed changed.\n"
0x180022238  call    FileLogAdd
0x18002223d  mov     rdx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180022244  mov     rax, [rsp+258h+var_230]
0x180022249  mov     ecx, [rax+90h]
0x18002224f  mov     [rdx+0FCh], ecx
0x180022255  lea     rcx, [rdx+148h]; lpCriticalSection
0x18002225c  call    cs:__imp_EnterCriticalSection
0x180022263  nop     dword ptr [rax+rax+00h]
0x180022268  mov     [rsp+258h+var_228], dil
0x18002226d  mov     rax, [rsp+258h+var_230]
0x180022272  mov     ecx, [rax+48h]
0x180022275  mov     rsi, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18002227c  cmp     [rsi+0BCh], ecx
0x180022282  jz      short loc_1800222D9
0x180022284  mov     [rsi+0BCh], ecx
0x18002228a  mov     esi, ebx
0x18002228c  mov     [rsp+258h+var_158], ebx
0x180022293  imul    rcx, 989680h
0x18002229a  mov     rax, [r13+0]
0x18002229e  mov     [rsp+258h+var_B0], rax
0x1800222a6  mov     r8, [r13+8]
0x1800222aa  mov     [rsp+258h+var_220], r8
0x1800222af  cmp     rax, r8
0x1800222b2  jnz     loc_1800223D1
0x1800222b8  mov     ecx, r15d
0x1800222bb  call    FileLogAllowEntry
0x1800222c0  test    al, al
0x1800222c2  jz      short loc_1800222D2
0x1800222c4  mov     edx, esi
0x1800222c6  lea     rcx, aSpecialpollint; "  SpecialPollInterval disabled. chng:%u"...
0x1800222cd  call    FileLogAdd
0x1800222d2  mov     rsi, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800222d9  mov     rax, [rsp+258h+var_230]
0x1800222de  mov     ecx, [rax+84h]
0x1800222e4  mov     [rsi+0ECh], ecx
0x1800222ea  mov     rax, [rsp+258h+var_230]
0x1800222ef  mov     ecx, [rax+44h]
0x1800222f2  cmp     [rsi+0B8h], ecx
0x1800222f8  jz      short loc_18002234C
0x1800222fa  mov     [rsi+0B8h], ecx
0x180022300  mov     r15d, ebx
0x180022303  mov     [rsp+258h+var_174], ebx
0x18002230a  mov     rax, [r13+0]
0x18002230e  mov     [rsp+258h+var_148], rax
0x180022316  mov     rcx, [r13+8]
0x18002231a  mov     [rsp+258h+var_220], rcx
0x18002231f  cmp     rax, rcx
0x180022322  jnz     loc_180022417
0x180022328  mov     ecx, 3Ah ; ':'
0x18002232d  call    FileLogAllowEntry
0x180022332  test    al, al
0x180022334  jz      short loc_180022345
0x180022336  mov     edx, r15d
0x180022339  lea     rcx, aCompatibilityF; "  Compatibility flags changed. chng:%u"...
0x180022340  call    FileLogAdd
0x180022345  mov     rsi, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18002234c  mov     rax, [rsp+258h+var_230]
0x180022351  mov     ecx, [rax+80h]
0x180022357  mov     [rsi+0E8h], ecx
0x18002235d  mov     rcx, [rsp+258h+var_230]
0x180022362  mov     r8d, [rcx+3Ch]
0x180022366  cmp     [rsi+0B0h], r8d
0x18002236d  jnz     short loc_18002237E
0x18002236f  mov     eax, [rcx+40h]
0x180022372  cmp     [rsi+0B4h], eax
0x180022378  jz      loc_18002252C
0x18002237e  mov     [rsi+0B0h], r8d
0x180022385  mov     rax, [rsp+258h+var_230]
0x18002238a  mov     edx, [rax+40h]
0x18002238d  mov     [rsi+0B4h], edx
0x180022393  mov     r15d, ebx
0x180022396  mov     [rsp+258h+var_154], ebx
0x18002239d  mov     r13d, ebx
0x1800223a0  mov     [rsp+258h+var_178], ebx
0x1800223a7  imul    rcx, r8, 23C34600h
0x1800223ae  mov     [rsp+258h+var_140], rcx
0x1800223b6  mov     [rsp+258h+var_214], edx
0x1800223ba  cmp     edx, edi
0x1800223bc  jbe     loc_18002244F
0x1800223c2  add     rcx, rcx
0x1800223c5  mov     [rsp+258h+var_140], rcx
0x1800223cd  dec     edx
0x1800223cf  jmp     short loc_1800223B6
0x1800223d1  mov     rdx, [rax]
0x1800223d4  mov     r8, [rdx+8]
0x1800223d8  cmp     [r8+30h], ebx
0x1800223dc  jnz     short loc_180022409
0x1800223de  mov     edx, [r8+50h]
0x1800223e2  and     edx, edi
0x1800223e4  test    dl, dl
0x1800223e6  jz      short loc_180022409
0x1800223e8  cmp     [r8+118h], rcx
0x1800223ef  jbe     short loc_180022409
0x1800223f1  mov     [r8+118h], rcx
0x1800223f8  add     esi, edi
0x1800223fa  mov     [rsp+258h+var_158], esi
0x180022401  mov     r14b, dil
0x180022404  mov     [rsp+258h+var_238], dil
0x180022409  mov     [rsp+258h+var_220], rax
0x18002240e  add     rax, 8
0x180022412  jmp     loc_18002229E
0x180022417  mov     edx, [rsi+0B8h]
0x18002241d  mov     rcx, [rax]
0x180022420  mov     r8, [rcx+8]
0x180022424  cmp     [r8+3Ch], edx
0x180022428  jz      short loc_180022441
0x18002242a  mov     [r8+3Ch], edx
0x18002242e  mov     r14b, dil
0x180022431  mov     [rsp+258h+var_238], dil
0x180022436  add     r15d, edi
0x180022439  mov     [rsp+258h+var_174], r15d
0x180022441  mov     [rsp+258h+var_220], rax
0x180022446  add     rax, 8
0x18002244a  jmp     loc_18002230E
0x18002244f  mov     r8d, ebx
0x180022452  mov     [rsp+258h+var_214], ebx
0x180022456  cmp     r8d, 2
0x18002245a  jnb     loc_180022500
0x180022460  test    r8d, r8d
0x180022463  lea     r9, [rsi+198h]
0x18002246a  jz      short loc_180022473
0x18002246c  lea     r9, [rsi+1B0h]
0x180022473  mov     rax, [r9]
0x180022476  mov     [rsp+258h+var_138], rax
0x18002247e  mov     rdx, [r9+8]
0x180022482  mov     [rsp+258h+var_220], rdx
0x180022487  cmp     rax, rdx
0x18002248a  jnz     short loc_180022496
0x18002248c  add     r8d, edi
0x18002248f  mov     [rsp+258h+var_214], r8d
0x180022494  jmp     short loc_180022456
0x180022496  mov     r11b, bl
0x180022499  mov     r10d, [rsi+0B4h]
0x1800224a0  mov     rdx, [rax]
0x1800224a3  mov     rdx, [rdx+8]
0x1800224a7  cmp     [rdx+34h], r10d
0x1800224ab  jbe     short loc_1800224B4
0x1800224ad  mov     [rdx+34h], r10d
0x1800224b1  mov     r11b, dil
0x1800224b4  mov     rdx, [rax]
0x1800224b7  mov     r10, [rdx+8]
0x1800224bb  cmp     [r10+118h], rcx
0x1800224c2  jbe     short loc_1800224CD
0x1800224c4  mov     [r10+118h], rcx
0x1800224cb  jmp     short loc_1800224D2
0x1800224cd  test    r11b, r11b
0x1800224d0  jz      short loc_1800224E7
0x1800224d2  mov     r14b, dil
0x1800224d5  mov     [rsp+258h+var_238], dil
0x1800224da  add     r13d, edi
0x1800224dd  mov     [rsp+258h+var_178], r13d
0x1800224e5  jmp     short loc_1800224F2
0x1800224e7  add     r15d, edi
0x1800224ea  mov     [rsp+258h+var_154], r15d
0x1800224f2  mov     [rsp+258h+var_220], rax
0x1800224f7  add     rax, 8
0x1800224fb  jmp     loc_180022476
0x180022500  mov     ecx, 3Ah ; ':'
0x180022505  call    FileLogAllowEntry
0x18002250a  test    al, al
0x18002250c  jz      short loc_180022520
0x18002250e  mov     r8d, r15d
0x180022511  mov     edx, r13d
0x180022514  lea     rcx, aResolvepeerbac_0; "  ResolvePeerBackoff changed. fix:%u no"...
0x18002251b  call    FileLogAdd
0x180022520  mov     rsi, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180022527  mov     rcx, [rsp+258h+var_230]
0x18002252c  mov     eax, [rcx+78h]
0x18002252f  mov     [rsi+0E0h], eax
0x180022535  mov     rax, [rsp+258h+var_230]
0x18002253a  mov     ecx, [rax+7Ch]
0x18002253d  mov     [rsi+0E4h], ecx
0x180022543  mov     rcx, [rsi+0A0h]; hMem
0x18002254a  test    rcx, rcx
0x18002254d  jz      short loc_180022562
0x18002254f  call    cs:__imp_LocalFree
0x180022556  nop     dword ptr [rax+rax+00h]
0x18002255b  mov     rsi, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180022562  mov     rax, [rsp+258h+var_230]
0x180022567  mov     rcx, [rax+10h]
0x18002256b  mov     [rsi+0A0h], rcx
0x180022572  mov     rax, [rsp+258h+var_230]
0x180022577  mov     [rax+10h], rbx
0x18002257b  mov     rax, [rsp+258h+var_230]
0x180022580  mov     ecx, [rax+68h]
0x180022583  mov     [rsi+0D4h], ecx
0x180022589  mov     rcx, [rsi+98h]; hMem
0x180022590  test    rcx, rcx
0x180022593  jz      short loc_1800225A8
0x180022595  call    cs:__imp_LocalFree
0x18002259c  nop     dword ptr [rax+rax+00h]
0x1800225a1  mov     rsi, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
  ... truncated ...
```
