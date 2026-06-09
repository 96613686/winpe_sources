# PeriodicallyLogConfigAndStatus(StateInfo *)

- ea: `0x18000d464`
- end: `0x18000dfcc`
- name: `?PeriodicallyLogConfigAndStatus@@YAXPEAUStateInfo@@@Z`
- size: `2920`
- prototype: `void __fastcall(struct StateInfo *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task`

## callers

- `0x18000f150`

## callees

- `0x180003ac0`
- `0x180005480`
- `0x18000a7e0`
- `0x18000d464`
- `0x180018138`
- `0x180019688`
- `0x18001d9a0`
- `0x18002108c`
- `0x180021170`
- `0x180026bf0`
- `0x18002b720`
- `0x18002caf0`
- `0x18002d538`
- `0x18002da5c`
- `0x18002e570`
- `0x18002ea14`
- `0x18003d270`
- `0x18004b794`
- `0x180063ef0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000deaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064754`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000deaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064754`

## string_xrefs

- `0x18000de91`: `Failed to gather service status info for logging purposes`

## pseudocode

```c
void __fastcall PeriodicallyLogConfigAndStatus(struct StateInfo *a1)
{
  unsigned __int16 *v1; // r14
  unsigned __int16 *v2; // r15
  unsigned __int16 *v3; // rsi
  _WORD *v4; // r12
  _WORD *v5; // r13
  unsigned __int16 *v6; // rdi
  _WORD *v7; // rbx
  unsigned __int64 *v8; // r9
  __int64 v9; // rdx
  void *v10; // rsp
  unsigned __int16 *v11; // rax
  void *v12; // rsp
  unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  void *v15; // rsp
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  void *v18; // rsp
  _DWORD *v19; // rax
  __int64 v20; // rdx
  void *v21; // rsp
  _DWORD *v22; // rax
  __int64 v23; // rdx
  void *v24; // rsp
  unsigned __int16 *v25; // rax
  _DWORD *v26; // rcx
  __int64 v27; // rdx
  void *v28; // rsp
  _DWORD *v29; // rcx
  _DWORD *v30; // rax
  unsigned __int16 *v31; // rcx
  __int64 v32; // rdx
  void *v33; // rsp
  unsigned __int16 *v34; // rcx
  unsigned __int16 *v35; // rax
  unsigned __int16 *v36; // rdx
  void *v37; // rsp
  unsigned __int16 *v38; // rax
  _WORD *v39; // rbx
  __int64 v40; // rcx
  __int64 v41; // r9
  const unsigned __int16 *v42; // r8
  unsigned __int64 v43; // r8
  _QWORD *v44; // rdi
  unsigned __int64 v45; // r9
  unsigned __int16 *v46; // r10
  HLOCAL v47; // rdi
  UCHAR *v48; // rcx
  __int64 v49; // rax
  BCRYPT_HASH_HANDLE v50; // rax
  _BYTE v51[96]; // [rsp+90h] [rbp-4790h] BYREF
  _BYTE v52[96]; // [rsp+1A0h] [rbp-4680h] BYREF
  _BYTE v53[96]; // [rsp+2B0h] [rbp-4570h] BYREF
  _BYTE v54[96]; // [rsp+3C0h] [rbp-4460h] BYREF
  _BYTE v55[96]; // [rsp+4D0h] [rbp-4350h] BYREF
  _BYTE v56[96]; // [rsp+5E0h] [rbp-4240h] BYREF
  _BYTE v57[96]; // [rsp+6F0h] [rbp-4130h] BYREF
  _BYTE v58[8208]; // [rsp+800h] [rbp-4020h] BYREF
  _BYTE v59[8208]; // [rsp+2810h] [rbp-2010h] BYREF
  _WORD *v60; // [rsp+4820h] [rbp+0h]
  HLOCAL hMem; // [rsp+4828h] [rbp+8h] BYREF
  unsigned __int16 *v62; // [rsp+4830h] [rbp+10h]
  unsigned __int16 *v63; // [rsp+4838h] [rbp+18h]
  unsigned __int16 *v64; // [rsp+4840h] [rbp+20h]
  int v65; // [rsp+4848h] [rbp+28h] BYREF
  unsigned __int16 *v66; // [rsp+4850h] [rbp+30h]
  unsigned __int16 *v67; // [rsp+4858h] [rbp+38h]
  unsigned __int16 *v68; // [rsp+4860h] [rbp+40h]
  _BYTE *v69; // [rsp+4868h] [rbp+48h]
  _BYTE *v70; // [rsp+4870h] [rbp+50h]
  unsigned __int16 *v71; // [rsp+4878h] [rbp+58h]
  _BYTE *v72; // [rsp+4880h] [rbp+60h]
  unsigned __int16 *v73; // [rsp+4888h] [rbp+68h]
  unsigned __int16 *v74; // [rsp+4890h] [rbp+70h]
  unsigned __int64 v75; // [rsp+4898h] [rbp+78h] BYREF
  struct StateInfo *v76; // [rsp+48A0h] [rbp+80h]
  unsigned __int64 v77; // [rsp+48A8h] [rbp+88h]
  unsigned __int64 v78; // [rsp+48B0h] [rbp+90h] BYREF
  unsigned __int16 *v79; // [rsp+48B8h] [rbp+98h]
  unsigned __int16 *v80; // [rsp+48C0h] [rbp+A0h]
  unsigned __int16 *v81; // [rsp+48C8h] [rbp+A8h]
  _WORD *v82; // [rsp+48D0h] [rbp+B0h]
  _WORD *v83; // [rsp+48D8h] [rbp+B8h]
  unsigned __int16 *v84; // [rsp+48E0h] [rbp+C0h]
  _DWORD *v85; // [rsp+48E8h] [rbp+C8h]
  unsigned __int16 *v86; // [rsp+48F0h] [rbp+D0h]
  char *v87; // [rsp+48F8h] [rbp+D8h]

  v76 = a1;
  hMem = 0;
  v75 = 0;
  v1 = 0;
  v79 = 0;
  v2 = 0;
  v80 = 0;
  v3 = 0;
  v81 = 0;
  v4 = 0;
  v82 = 0;
  v5 = 0;
  v83 = 0;
  v6 = 0;
  v84 = 0;
  v7 = 0;
  v60 = 0;
  v85 = 0;
  v62 = 0;
  v86 = 0;
  v65 = 0;
  v78 = 0;
  v77 = 0;
  AccurateGetTickCountSafe(&v75, 0);
  v87 = (char *)v76 + 3184;
  if ( (unsigned int)ShouldLogPeriodicEvent(*((_QWORD *)v76 + 397), *((_QWORD *)v76 + 398), v75) )
  {
    AccurateGetTickCountSafe(v8, 0);
    if ( (int)s_W32TimeQueryStatus(-1, &hMem) >= 0 && hMem )
    {
      v1 = 0;
      v66 = 0;
      v9 = 0x2000;
      if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x2000
        && (unsigned __int64)(g_ulAdditionalProbeSize + 8200) >= 0x2000 )
      {
        if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 8200, 0x2000) )
        {
          v10 = alloca(8208);
          v1 = (unsigned __int16 *)v59;
          v66 = (unsigned __int16 *)v59;
        }
        if ( !v1 )
        {
LABEL_11:
          v11 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pfnAllocate)(8200, v9, 0);
          v1 = v11;
          v66 = v11;
          if ( v11 )
          {
            *(_DWORD *)v11 = 1885431112;
            v1 = v11 + 4;
            v66 = v11 + 4;
          }
LABEL_13:
          v79 = v1;
          if ( !v1 )
            goto LABEL_108;
          v2 = 0;
          v67 = 0;
          if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x2000
            && (unsigned __int64)(g_ulAdditionalProbeSize + 8200) >= 0x2000 )
          {
            if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 8200, v9) )
            {
              v12 = alloca(8208);
              v2 = (unsigned __int16 *)v58;
              v67 = (unsigned __int16 *)v58;
            }
            if ( !v2 )
            {
LABEL_21:
              v13 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pfnAllocate)(8200, v9, 0);
              v2 = v13;
              v67 = v13;
              if ( v13 )
              {
                *(_DWORD *)v13 = 1885431112;
                v2 = v13 + 4;
                v67 = v13 + 4;
              }
LABEL_23:
              v80 = v2;
              if ( !v2 )
                goto LABEL_108;
              v3 = 0;
              v68 = 0;
              v14 = 256;
              if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x100
                && (unsigned __int64)(g_ulAdditionalProbeSize + 264) >= 0x100 )
              {
                if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 264, 256) )
                {
                  v15 = alloca(272);
                  v3 = (unsigned __int16 *)v57;
                  v68 = (unsigned __int16 *)v57;
                }
                if ( !v3 )
                {
LABEL_31:
                  v16 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pfnAllocate)(
                                              264,
                                              v14,
                                              0);
                  v3 = v16;
                  v68 = v16;
                  if ( v16 )
                  {
                    *(_DWORD *)v16 = 1885431112;
                    v3 = v16 + 4;
                    v68 = v16 + 4;
                  }
LABEL_33:
                  v81 = v3;
                  if ( !v3 )
                    goto LABEL_108;
                  v4 = 0;
                  v69 = 0;
                  v17 = 256;
                  if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x100
                    && (unsigned __int64)(g_ulAdditionalProbeSize + 264) >= 0x100 )
                  {
                    if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 264, 256) )
                    {
                      v18 = alloca(272);
                      v4 = v56;
                      v69 = v56;
                    }
                    if ( !v4 )
                    {
LABEL_41:
                      v19 = (_DWORD *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pfnAllocate)(264, v17, 0);
                      v4 = v19;
                      v69 = v19;
                      if ( v19 )
                      {
                        *v19 = 1885431112;
                        v4 = v19 + 2;
                        v69 = v19 + 2;
                      }
LABEL_43:
                      v82 = v4;
                      if ( !v4 )
                        goto LABEL_108;
                      v5 = 0;
                      v70 = 0;
                      v20 = 256;
                      if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x100
                        && (unsigned __int64)(g_ulAdditionalProbeSize + 264) >= 0x100 )
                      {
                        if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 264, 256) )
                        {
                          v21 = alloca(272);
                          v5 = v55;
                          v70 = v55;
                        }
                        if ( !v5 )
                        {
LABEL_51:
                          v22 = (_DWORD *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pfnAllocate)(264, v20, 0);
                          v5 = v22;
                          v70 = v22;
                          if ( v22 )
                          {
                            *v22 = 1885431112;
                            v5 = v22 + 2;
                            v70 = v22 + 2;
                          }
LABEL_53:
                          v83 = v5;
                          if ( !v5 )
                            goto LABEL_108;
                          v6 = 0;
                          v64 = 0;
                          v71 = 0;
                          v23 = 256;
                          if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x100
                            && (unsigned __int64)(g_ulAdditionalProbeSize + 264) >= 0x100 )
                          {
                            if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 264, 256) )
                            {
                              v24 = alloca(272);
                              v6 = (unsigned __int16 *)v54;
                              v64 = (unsigned __int16 *)v54;
                              v71 = (unsigned __int16 *)v54;
                            }
                            if ( !v6 )
                            {
LABEL_61:
                              v25 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pfnAllocate)(
                                                          264,
                                                          v23,
                                                          0);
                              v6 = v25;
                              v64 = v25;
                              v71 = v25;
                              if ( v25 )
                              {
                                *(_DWORD *)v25 = 1885431112;
                                v6 = v25 + 4;
                                v64 = v25 + 4;
                                v71 = v25 + 4;
                              }
LABEL_63:
                              v84 = v6;
                              if ( !v6 )
                                goto LABEL_108;
                              v26 = 0;
                              v60 = 0;
                              v72 = 0;
                              v27 = 256;
                              if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x100
                                && (unsigned __int64)(g_ulAdditionalProbeSize + 264) >= 0x100 )
                              {
                                if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 264, 256) )
                                {
                                  v28 = alloca(272);
                                  v29 = v53;
                                  v60 = v53;
                                  v72 = v53;
                                }
                                else
                                {
                                  v29 = v60;
                                }
                                if ( !v29 )
                                {
LABEL_72:
                                  v30 = (_DWORD *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pfnAllocate)(
                                                    264,
                                                    v27,
                                                    0);
                                  v26 = v30;
                                  v60 = v30;
                                  v72 = v30;
                                  if ( v30 )
                                  {
                                    *v30 = 1885431112;
                                    v26 = v30 + 2;
                                    v60 = v30 + 2;
                                    v72 = v30 + 2;
                                  }
LABEL_74:
                                  v85 = v26;
                                  if ( !v26 )
                                    goto LABEL_108;
                                  v31 = 0;
                                  v62 = 0;
                                  v73 = 0;
                                  v32 = 256;
                                  if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x100
                                    && (unsigned __int64)(g_ulAdditionalProbeSize + 264) >= 0x100 )
                                  {
                                    if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 264, 256) )
                                    {
                                      v33 = alloca(272);
                                      v34 = (unsigned __int16 *)v52;
                                      v62 = (unsigned __int16 *)v52;
                                      v73 = (unsigned __int16 *)v52;
                                    }
                                    else
                                    {
                                      v34 = v62;
                                    }
                                    if ( !v34 )
                                    {
LABEL_83:
                                      v35 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64, __int64, _QWORD))g_pfnAllocate)(
                                                                  264,
                                                                  v32,
                                                                  0);
                                      v31 = v35;
                                      v62 = v35;
                                      v73 = v35;
                                      if ( v35 )
                                      {
                                        *(_DWORD *)v35 = 1885431112;
                                        v31 = v35 + 4;
                                        v62 = v35 + 4;
                                        v73 = v35 + 4;
                                      }
LABEL_85:
                                      v86 = v31;
                                      if ( v31 )
                                      {
                                        v36 = 0;
                                        v63 = 0;
                                        v74 = 0;
                                        if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x100
                                          && (unsigned __int64)(g_ulAdditionalProbeSize + 264) >= 0x100 )
                                        {
                                          if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 264, 0) )
                                          {
                                            v37 = alloca(272);
                                            v36 = (unsigned __int16 *)v51;
                                            v63 = (unsigned __int16 *)v51;
                                            v74 = (unsigned __int16 *)v51;
                                          }
                                          else
                                          {
                                            v36 = v63;
                                          }
                                          if ( !v36 )
                                            goto LABEL_94;
                                          *(_DWORD *)v36 = 1801679955;
                                          v36 += 4;
                                          v63 = v36;
                                          v74 = v36;
                                        }
                                        if ( v36 )
                                        {
LABEL_97:
                                          *v1 = 0;
                                          *v2 = 0;
                                          *v3 = 0;
                                          *v4 = 0;
                                          *v5 = 0;
                                          *v6 = 0;
                                          v39 = v60;
                                          *v60 = 0;
                                          *v62 = 0;
                                          *v36 = 0;
                                          GetServiceConfigStrings(v1, (__int64)v36, v2);
                                          v40 = *((int *)hMem + 12);
                                          *v3 = 0;
                                          v41 = v40;
                                          if ( v40 < 0 )
                                            v41 = -v40;
                                          v42 = L"-%I64u";
                                          if ( v40 >= 0 )
                                            v42 = L"%I64u";
                                          StringCchPrintfW(v3, 0x80u, v42, v41);
                                          GetFormattedRefId(*((unsigned int *)hMem + 4), v4);
                                          GetTimeSigned(*((_QWORD *)hMem + 4), v5);
                                          v43 = *((_QWORD *)hMem + 5);
                                          *v6 = 0;
                                          StringCchPrintfW(v6, 0x80u, L"%I64u.%07I64us", v43 / 0x989680, v43 % 0x989680);
                                          v44 = hMem;
                                          GetTimeSigned(*((_QWORD *)hMem + 8), v39);
                                          v45 = v44[12];
                                          v46 = v62;
                                          *v62 = 0;
                                          StringCchPrintfW(
                                            v46,
                                            0x80u,
                                            L"%I64u.%07I64us",
                                            v45 / 0x989680,
                                            v45 % 0x989680);
                                          MyGetLastProviderInUse(v63, (enum NtpLeapIndicator *)&v65);
                                          LogEvent(
                                            &_W32TimeRegistrationHandle,
                                            W32TIME_OPS_PERIODIC_CONFIG_STATUS,
                                            L"SSiiSSSSTSiSiiiiiSi",
                                            v1);
                                          LogClockFreqEvents(v76, v75);
                                          MyGetLastSyncTime(&v78);
                                          v47 = hMem;
                                          v48 = (UCHAR *)*((_QWORD *)hMem + 7);
                                          if ( v48 )
                                          {
                                            v49 = -1;
                                            do
                                              ++v49;
                                            while ( *(_WORD *)&v48[2 * v49] );
                                            v77 = (unsigned __int64)MyBuiltInHashing(v48, 2 * (int)v49);
                                          }
                                          v50 = MyBuiltInHashing((PUCHAR)v47 + 16, 4u);
                                          LogSyncInfo(
                                            v78,
                                            qword_1800A4350,
                                            qword_1800A4348,
                                            v63,
                                            v77,
                                            (unsigned __int64)v50,
                                            byte_1800A46F8,
                                            byte_1800A45A2,
                                            dword_1800A4708,
                                            v65,
                                            dword_1800A4720,
                                            dword_1800A4710 != 0,
                                            qword_1800A4738,
                                            dword_1800A4760,
                                            0,
                                            *((_DWORD *)v47 + 19));
                                          byte_1800A45A2 = 0;
                                          byte_1800A46F8 = 0;
                                          qword_1800A4350 = 0;
                                          v6 = v64;
                                          goto LABEL_108;
                                        }
LABEL_94:
                                        v38 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64, unsigned __int16 *, _QWORD))g_pfnAllocate)(
                                                                    264,
                                                                    v36,
                                                                    0);
                                        v36 = v38;
                                        v63 = v38;
                                        v74 = v38;
                                        if ( v38 )
                                        {
                                          *(_DWORD *)v38 = 1885431112;
                                          v36 = v38 + 4;
                                          v63 = v38 + 4;
                                          v74 = v38 + 4;
                                        }
                                        if ( !v36 )
                                          goto LABEL_108;
                                        goto LABEL_97;
                                      }
LABEL_108:
                                      v7 = v60;
                                      goto LABEL_109;
                                    }
                                    *(_DWORD *)v34 = 1801679955;
                                    v31 = v34 + 4;
                                    v62 = v31;
                                    v73 = v31;
                                  }
                                  if ( v31 )
                                    goto LABEL_85;
                                  goto LABEL_83;
                                }
                                *v29 = 1801679955;
                                v26 = v29 + 2;
                                v60 = v26;
                                v72 = v26;
                              }
                              if ( v26 )
                                goto LABEL_74;
                              goto LABEL_72;
                            }
                            *(_DWORD *)v6 = 1801679955;
                            v6 += 4;
                            v64 = v6;
                            v71 = v6;
                          }
                          if ( v6 )
                            goto LABEL_63;
                          goto LABEL_61;
                        }
                        *(_DWORD *)v5 = 1801679955;
                        v5 += 4;
                        v70 = v5;
                      }
                      if ( v5 )
                        goto LABEL_53;
                      goto LABEL_51;
                    }
                    *(_DWORD *)v4 = 1801679955;
                    v4 += 4;
                    v69 = v4;
                  }
                  if ( v4 )
                    goto LABEL_43;
                  goto LABEL_41;
                }
                *(_DWORD *)v3 = 1801679955;
                v3 += 4;
                v68 = v3;
              }
              if ( v3 )
                goto LABEL_33;
              goto LABEL_31;
            }
            *(_DWORD *)v2 = 1801679955;
            v2 += 4;
            v67 = v2;
          }
          if ( v2 )
            goto LABEL_23;
          goto LABEL_21;
        }
        *(_DWORD *)v1 = 1801679955;
        v1 += 4;
        v66 = v1;
      }
      if ( v1 )
        goto LABEL_13;
      goto LABEL_11;
    }
    if ( (unsigned __int8)FileLogAllowEntry(64) )
      FileLogAdd(L"Failed to gather service status info for logging purposes");
  }
LABEL_109:
  if ( hMem )
    LocalFree(hMem);
  if ( v1 && *((_DWORD *)v1 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v2 && *((_DWORD *)v2 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v3 && *((_DWORD *)v3 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v4 && *((_DWORD *)v4 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v5 && *((_DWORD *)v5 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v6 && *((_DWORD *)v6 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v7 && *((_DWORD *)v7 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v62 )
  {
    if ( *((_DWORD *)v62 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
}

```

## disassembly

```asm
0x18000d464  push    rbp
0x18000d466  push    rbx
0x18000d467  push    rsi
0x18000d468  push    rdi
0x18000d469  push    r12
0x18000d46b  push    r13
0x18000d46d  push    r14
0x18000d46f  push    r15
0x18000d471  sub     rsp, 1A8h
0x18000d478  lea     rbp, [rsp+0B0h]
0x18000d480  mov     rax, cs:__security_cookie
0x18000d487  xor     rax, rbp
0x18000d48a  mov     [rbp+130h+var_50], rax
0x18000d491  mov     [rbp+130h+var_B0], rcx
0x18000d498  xor     ecx, ecx
0x18000d49a  mov     [rbp+130h+hMem], rcx
0x18000d49e  mov     [rbp+130h+var_B8], rcx
0x18000d4a2  mov     r14d, ecx
0x18000d4a5  mov     [rbp+130h+var_98], rcx
0x18000d4ac  mov     r15d, ecx
0x18000d4af  mov     [rbp+130h+var_90], rcx
0x18000d4b6  mov     esi, ecx
0x18000d4b8  mov     [rbp+130h+var_88], rcx
0x18000d4bf  mov     r12d, ecx
0x18000d4c2  mov     [rbp+130h+var_80], rcx
0x18000d4c9  mov     r13d, ecx
0x18000d4cc  mov     [rbp+130h+var_78], rcx
0x18000d4d3  mov     edi, ecx
0x18000d4d5  mov     [rbp+130h+var_70], rcx
0x18000d4dc  mov     ebx, ecx
0x18000d4de  mov     [rbp+130h+var_130], rcx
0x18000d4e2  mov     [rbp+130h+var_68], rcx
0x18000d4e9  mov     [rbp+130h+var_120], rcx
0x18000d4ed  mov     [rbp+130h+var_60], rcx
0x18000d4f4  mov     [rbp+130h+var_108], ecx
0x18000d4f7  mov     [rbp+130h+var_A0], rcx
0x18000d4fe  mov     [rbp+130h+var_A8], rcx
0x18000d505  xor     edx, edx; bool
0x18000d507  lea     rcx, [rbp+130h+var_B8]; unsigned __int64 *
0x18000d50b  call    ?AccurateGetTickCountSafe@@YAJPEA_K_N@Z; AccurateGetTickCountSafe(unsigned __int64 *,bool)
0x18000d510  mov     rax, [rbp+130h+var_B0]
0x18000d517  lea     r9, [rax+0C70h]
0x18000d51e  mov     [rbp+130h+var_58], r9
0x18000d525  mov     r8, [rbp+130h+var_B8]
0x18000d529  mov     rdx, [r9]
0x18000d52c  mov     rcx, [rax+0C68h]
0x18000d533  call    ShouldLogPeriodicEvent
0x18000d538  test    eax, eax
0x18000d53a  jz      loc_18000DEA3
0x18000d540  xor     edx, edx; bool
0x18000d542  mov     rcx, r9; unsigned __int64 *
0x18000d545  call    ?AccurateGetTickCountSafe@@YAJPEA_K_N@Z; AccurateGetTickCountSafe(unsigned __int64 *,bool)
0x18000d54a  lea     rdx, [rbp+130h+hMem]
0x18000d54e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d552  call    s_W32TimeQueryStatus
0x18000d557  xor     r8d, r8d
0x18000d55a  test    eax, eax
0x18000d55c  js      loc_18000DE83
0x18000d562  cmp     [rbp+130h+hMem], r8
0x18000d566  jz      loc_18000DE83
0x18000d56c  mov     r14d, r8d
0x18000d56f  mov     [rbp+130h+var_100], r8
0x18000d573  mov     edx, 2000h
0x18000d578  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18000d57f  jb      short loc_18000D5CD
0x18000d581  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000d588  add     rcx, 2008h
0x18000d58f  cmp     rcx, rdx
0x18000d592  jb      short loc_18000D5CD
0x18000d594  call    VerifyStackAvailable
0x18000d599  xor     r8d, r8d
0x18000d59c  test    eax, eax
0x18000d59e  jz      short loc_18000D5B9
0x18000d5a0  mov     eax, 2010h
0x18000d5a5  call    _alloca_probe
0x18000d5aa  sub     rsp, rax
0x18000d5ad  lea     r14, [rsp+21F0h+var_2140]
0x18000d5b5  mov     [rbp+130h+var_100], r14
0x18000d5b9  test    r14, r14
0x18000d5bc  jz      short loc_18000D5D2
0x18000d5be  mov     dword ptr [r14], 6B637453h
0x18000d5c5  add     r14, 8
0x18000d5c9  mov     [rbp+130h+var_100], r14
0x18000d5cd  test    r14, r14
0x18000d5d0  jnz     short loc_18000D603
0x18000d5d2  mov     ecx, 2008h
0x18000d5d7  mov     rax, cs:g_pfnAllocate
0x18000d5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5e3  mov     r14, rax
0x18000d5e6  mov     [rbp+130h+var_100], rax
0x18000d5ea  xor     r8d, r8d
0x18000d5ed  mov     ebx, 70616548h
0x18000d5f2  test    rax, rax
0x18000d5f5  jz      short loc_18000D608
0x18000d5f7  mov     [rax], ebx
0x18000d5f9  add     r14, 8
0x18000d5fd  mov     [rbp+130h+var_100], r14
0x18000d601  jmp     short loc_18000D608
0x18000d603  mov     ebx, 70616548h
0x18000d608  mov     [rbp+130h+var_98], r14
0x18000d60f  test    r14, r14
0x18000d612  jz      loc_18000DE9F
0x18000d618  mov     r15, r8
0x18000d61b  mov     [rbp+130h+var_F8], r8
0x18000d61f  mov     eax, 2000h
0x18000d624  cmp     cs:g_ulMaxStackAllocSize, rax
0x18000d62b  jb      short loc_18000D679
0x18000d62d  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000d634  add     rcx, 2008h
0x18000d63b  cmp     rcx, rax
0x18000d63e  jb      short loc_18000D679
0x18000d640  call    VerifyStackAvailable
0x18000d645  xor     r8d, r8d
0x18000d648  test    eax, eax
0x18000d64a  jz      short loc_18000D665
0x18000d64c  mov     eax, 2010h
0x18000d651  call    _alloca_probe
0x18000d656  sub     rsp, rax
0x18000d659  lea     r15, [rsp+4200h+var_4150]
0x18000d661  mov     [rbp+130h+var_F8], r15
0x18000d665  test    r15, r15
0x18000d668  jz      short loc_18000D67E
0x18000d66a  mov     dword ptr [r15], 6B637453h
0x18000d671  add     r15, 8
0x18000d675  mov     [rbp+130h+var_F8], r15
0x18000d679  test    r15, r15
0x18000d67c  jnz     short loc_18000D6A8
0x18000d67e  mov     ecx, 2008h
0x18000d683  mov     rax, cs:g_pfnAllocate
0x18000d68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d68f  mov     r15, rax
0x18000d692  mov     [rbp+130h+var_F8], rax
0x18000d696  xor     r8d, r8d
0x18000d699  test    rax, rax
0x18000d69c  jz      short loc_18000D6A8
0x18000d69e  mov     [rax], ebx
0x18000d6a0  add     r15, 8
0x18000d6a4  mov     [rbp+130h+var_F8], r15
0x18000d6a8  mov     [rbp+130h+var_90], r15
0x18000d6af  test    r15, r15
0x18000d6b2  jz      loc_18000DE9F
0x18000d6b8  mov     rsi, r8
0x18000d6bb  mov     [rbp+130h+var_F0], r8
0x18000d6bf  mov     edx, 100h
0x18000d6c4  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18000d6cb  jb      short loc_18000D718
0x18000d6cd  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000d6d4  add     rcx, 108h
0x18000d6db  cmp     rcx, rdx
0x18000d6de  jb      short loc_18000D718
0x18000d6e0  call    VerifyStackAvailable
0x18000d6e5  xor     r8d, r8d
0x18000d6e8  test    eax, eax
0x18000d6ea  jz      short loc_18000D705
0x18000d6ec  mov     eax, [rsp+4200h+var_4200]
0x18000d6ef  mov     eax, 110h
0x18000d6f4  sub     rsp, rax
0x18000d6f7  lea     rsi, [rsp+4310h+var_4260]
0x18000d6ff  mov     eax, [rsi]
0x18000d701  mov     [rbp+130h+var_F0], rsi
0x18000d705  test    rsi, rsi
0x18000d708  jz      short loc_18000D71D
0x18000d70a  mov     dword ptr [rsi], 6B637453h
0x18000d710  add     rsi, 8
0x18000d714  mov     [rbp+130h+var_F0], rsi
0x18000d718  test    rsi, rsi
0x18000d71b  jnz     short loc_18000D747
0x18000d71d  mov     ecx, 108h
0x18000d722  mov     rax, cs:g_pfnAllocate
0x18000d729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d72e  mov     rsi, rax
0x18000d731  mov     [rbp+130h+var_F0], rax
0x18000d735  xor     r8d, r8d
0x18000d738  test    rax, rax
0x18000d73b  jz      short loc_18000D747
0x18000d73d  mov     [rax], ebx
0x18000d73f  add     rsi, 8
0x18000d743  mov     [rbp+130h+var_F0], rsi
0x18000d747  mov     [rbp+130h+var_88], rsi
0x18000d74e  test    rsi, rsi
0x18000d751  jz      loc_18000DE9F
0x18000d757  mov     r12, r8
0x18000d75a  mov     [rbp+130h+var_E8], r8
0x18000d75e  mov     edx, 100h
0x18000d763  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18000d76a  jb      short loc_18000D7BB
0x18000d76c  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000d773  add     rcx, 108h
0x18000d77a  cmp     rcx, rdx
0x18000d77d  jb      short loc_18000D7BB
0x18000d77f  call    VerifyStackAvailable
0x18000d784  xor     r8d, r8d
0x18000d787  test    eax, eax
0x18000d789  jz      short loc_18000D7A6
0x18000d78b  mov     eax, [rsp+4310h+var_4310]
0x18000d78e  mov     eax, 110h
0x18000d793  sub     rsp, rax
0x18000d796  lea     r12, [rsp+4420h+var_4370]
0x18000d79e  mov     eax, [r12]
0x18000d7a2  mov     [rbp+130h+var_E8], r12
0x18000d7a6  test    r12, r12
0x18000d7a9  jz      short loc_18000D7C0
0x18000d7ab  mov     dword ptr [r12], 6B637453h
0x18000d7b3  add     r12, 8
0x18000d7b7  mov     [rbp+130h+var_E8], r12
0x18000d7bb  test    r12, r12
0x18000d7be  jnz     short loc_18000D7EA
0x18000d7c0  mov     ecx, 108h
0x18000d7c5  mov     rax, cs:g_pfnAllocate
0x18000d7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7d1  mov     r12, rax
0x18000d7d4  mov     [rbp+130h+var_E8], rax
0x18000d7d8  xor     r8d, r8d
0x18000d7db  test    rax, rax
0x18000d7de  jz      short loc_18000D7EA
0x18000d7e0  mov     [rax], ebx
0x18000d7e2  add     r12, 8
0x18000d7e6  mov     [rbp+130h+var_E8], r12
0x18000d7ea  mov     [rbp+130h+var_80], r12
0x18000d7f1  test    r12, r12
0x18000d7f4  jz      loc_18000DE9F
0x18000d7fa  mov     r13, r8
0x18000d7fd  mov     [rbp+130h+var_E0], r8
0x18000d801  mov     edx, 100h
0x18000d806  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18000d80d  jb      short loc_18000D85E
0x18000d80f  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000d816  add     rcx, 108h
0x18000d81d  cmp     rcx, rdx
0x18000d820  jb      short loc_18000D85E
0x18000d822  call    VerifyStackAvailable
0x18000d827  xor     r8d, r8d
0x18000d82a  test    eax, eax
0x18000d82c  jz      short loc_18000D849
0x18000d82e  mov     eax, [rsp+4420h+var_4420]
0x18000d831  mov     eax, 110h
0x18000d836  sub     rsp, rax
0x18000d839  lea     r13, [rsp+4530h+var_4480]
0x18000d841  mov     eax, [r13+0]
0x18000d845  mov     [rbp+130h+var_E0], r13
0x18000d849  test    r13, r13
0x18000d84c  jz      short loc_18000D863
0x18000d84e  mov     dword ptr [r13+0], 6B637453h
0x18000d856  add     r13, 8
0x18000d85a  mov     [rbp+130h+var_E0], r13
0x18000d85e  test    r13, r13
0x18000d861  jnz     short loc_18000D88D
0x18000d863  mov     ecx, 108h
0x18000d868  mov     rax, cs:g_pfnAllocate
0x18000d86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d874  mov     r13, rax
0x18000d877  mov     [rbp+130h+var_E0], rax
0x18000d87b  xor     r8d, r8d
0x18000d87e  test    rax, rax
0x18000d881  jz      short loc_18000D88D
0x18000d883  mov     [rax], ebx
0x18000d885  add     r13, 8
0x18000d889  mov     [rbp+130h+var_E0], r13
0x18000d88d  mov     [rbp+130h+var_78], r13
0x18000d894  test    r13, r13
0x18000d897  jz      loc_18000DE9F
0x18000d89d  mov     rdi, r8
0x18000d8a0  mov     [rbp+130h+var_110], r8
0x18000d8a4  mov     [rbp+130h+var_D8], r8
0x18000d8a8  mov     edx, 100h
0x18000d8ad  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18000d8b4  jb      short loc_18000D909
0x18000d8b6  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000d8bd  add     rcx, 108h
0x18000d8c4  cmp     rcx, rdx
0x18000d8c7  jb      short loc_18000D909
0x18000d8c9  call    VerifyStackAvailable
0x18000d8ce  xor     r8d, r8d
0x18000d8d1  test    eax, eax
0x18000d8d3  jz      short loc_18000D8F2
0x18000d8d5  mov     eax, [rsp+4530h+var_4530]
0x18000d8d8  mov     eax, 110h
0x18000d8dd  sub     rsp, rax
0x18000d8e0  lea     rdi, [rsp+4640h+var_4590]
0x18000d8e8  mov     [rbp+130h+var_110], rdi
0x18000d8ec  mov     eax, [rdi]
0x18000d8ee  mov     [rbp+130h+var_D8], rdi
0x18000d8f2  test    rdi, rdi
0x18000d8f5  jz      short loc_18000D90E
0x18000d8f7  mov     dword ptr [rdi], 6B637453h
0x18000d8fd  add     rdi, 8
0x18000d901  mov     [rbp+130h+var_110], rdi
0x18000d905  mov     [rbp+130h+var_D8], rdi
0x18000d909  test    rdi, rdi
0x18000d90c  jnz     short loc_18000D940
0x18000d90e  mov     ecx, 108h
0x18000d913  mov     rax, cs:g_pfnAllocate
0x18000d91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d91f  mov     rdi, rax
0x18000d922  mov     [rbp+130h+var_110], rax
0x18000d926  mov     [rbp+130h+var_D8], rax
0x18000d92a  xor     r8d, r8d
0x18000d92d  test    rax, rax
0x18000d930  jz      short loc_18000D940
0x18000d932  mov     [rax], ebx
  ... truncated ...
```
