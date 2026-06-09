# SamIUpdateLogonStatistics

- ea: `0x18002b810`
- end: `0x18002c447`
- name: `SamIUpdateLogonStatistics`
- size: `3127`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, struct _SAM_LOGON_STATISTICS *)`
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800028e0`
- `0x180008590`
- `0x18000e7f0`
- `0x180012a28`
- `0x180022b30`
- `0x180027e24`
- `0x180027ef8`
- `0x18002b810`
- `0x18002c450`
- `0x18002cd80`
- `0x18002d720`
- `0x180037284`
- `0x1800372ac`
- `0x18006194c`
- `0x180065630`
- `0x180065a2c`
- `0x180065b60`
- `0x1800696f0`
- `0x180076e8c`
- `0x180077738`
- `0x18007780c`
- `0x18007877c`
- `0x18008f300`
- `0x18009b0a0`
- `0x1800a0150`
- `0x1800a0258`
- `0x1800a1ab8`
- `0x1800a5620`
- `0x1800a8094`
- `0x1800a83bc`
- `0x1800acb78`
- `0x1800bb77c`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18002be5f`
- `ntdll!RtlCompareUnicodeString` at `0x18002be5f`
- `ntdll!RtlInitUnicodeString` at `0x18002be4a`
- `ntdll!RtlInitUnicodeString` at `0x18002be4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bea7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bea7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bb24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bc33`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bc86`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bcce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bdb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bb24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bc33`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bc86`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bcce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bdb7`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtPurgeSecrets` at `0x18002c1b1`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtPurgeSecrets` at `0x18002c1b1`

## pseudocode

```c
__int64 __fastcall SamIUpdateLogonStatistics(struct _SAMP_OBJECT *a1, struct _SAM_LOGON_STATISTICS *a2)
{
  unsigned __int8 v2; // r13
  __int64 v5; // rbx
  _BYTE *v6; // rax
  unsigned int v7; // r15d
  int v8; // r12d
  int v9; // ebx
  PUNICODE_STRING v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int UserAccountSettings; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  PUNICODE_STRING v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  struct _UNICODE_STRING *v19; // rbx
  int v20; // r12d
  char v21; // r15
  bool v22; // zf
  PUNICODE_STRING v23; // rcx
  unsigned __int8 v24; // dl
  char *v25; // rax
  __int64 v26; // rcx
  int updated; // eax
  PUNICODE_STRING v28; // rcx
  __int64 v29; // rdx
  PUNICODE_STRING v30; // rcx
  __int64 v31; // rdx
  char *v32; // rax
  __int64 v33; // rcx
  struct _DSNAME *v34; // r13
  int StrIpAddressFromSocketAddress; // eax
  HLOCAL *v36; // rcx
  unsigned __int8 v37; // bl
  int v38; // edx
  int v39; // eax
  int v40; // eax
  __int64 v41; // r15
  int v42; // eax
  int v43; // eax
  PUNICODE_STRING v44; // rcx
  __int64 v45; // rdx
  int v46; // eax
  __int64 v47; // rcx
  struct _PSAMP_DEFINED_DOMAINS *v48; // rax
  unsigned __int8 v49; // al
  int v50; // eax
  unsigned int v51; // r12d
  __int64 v52; // rcx
  char v54; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v55[7]; // [rsp+61h] [rbp-9Fh] BYREF
  __int64 v56; // [rsp+68h] [rbp-98h] BYREF
  char v57; // [rsp+70h] [rbp-90h]
  unsigned int v58; // [rsp+74h] [rbp-8Ch]
  int v59; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  __int128 Buf2; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v63[8]; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B8h] [rbp-48h] BYREF
  struct _FILETIME v65; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v66; // [rsp+E0h] [rbp-20h]
  unsigned int v67; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v68; // [rsp+F0h] [rbp-10h]
  __int16 v69; // [rsp+F2h] [rbp-Eh]
  __int128 Buf1; // [rsp+100h] [rbp+0h] BYREF
  struct _DOMAIN_PASSWORD_INFORMATION v71[2]; // [rsp+110h] [rbp+10h] BYREF

  v2 = 0;
  v59 = 0;
  v5 = 80;
  memset_0(v63, 0, 0x50u);
  v55[0] = 0;
  v6 = v63;
  Buf1 = 0;
  Buf2 = 0;
  memset(v71, 0, sizeof(v71));
  do
  {
    *v6++ = 0;
    --v5;
  }
  while ( v5 );
  if ( !a1 || !a2 )
  {
    v10 = WPP_GLOBAL_Control;
    v9 = -1073741811;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v11 = 280;
      v12 = 3221225485LL;
      goto LABEL_220;
    }
    return (unsigned int)v9;
  }
  v58 = 0;
  v7 = 1;
  v57 = 0;
  LODWORD(v56) = 1;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_qDDDiiZZ(
      WPP_GLOBAL_Control[3].Buffer,
      (_DWORD)a2 + 24,
      *((unsigned __int16 *)a2 + 3),
      (_DWORD)a1,
      *(_DWORD *)a2,
      *((_WORD *)a2 + 2),
      *((_WORD *)a2 + 3),
      *((_QWORD *)a2 + 1),
      *((_QWORD *)a2 + 2),
      (__int64)a2 + 24,
      (__int64)a2 + 40);
  v8 = *(_DWORD *)a2;
  if ( (*((_BYTE *)a1 + 28) & 1) != 0 && (*((_BYTE *)a1 + 192) & 2) != 0 )
  {
    v55[0] = 0;
    _InterlockedAdd((volatile signed __int32 *)a1 + 36, 1u);
    goto LABEL_16;
  }
  v9 = SampMaybeAcquireWriteLock(a1, v55);
  if ( v9 >= 0 )
  {
    v55[0] = 1;
    v9 = SampLookupContext(a1, 0, 4, &v59);
    if ( v9 < 0 )
    {
      v51 = 0;
      goto LABEL_211;
    }
LABEL_16:
    v54 = 0;
    UserAccountSettings = SampGetUserAccountSettings(a1, v71);
    v9 = UserAccountSettings;
    if ( UserAccountSettings < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
        goto LABEL_193;
      }
      v17 = 283;
      goto LABEL_20;
    }
    UserAccountSettings = SampRetrieveUserV1aFixed(a1, v63, v14, v15);
    v9 = UserAccountSettings;
    if ( UserAccountSettings < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
        goto LABEL_193;
      }
      v17 = 284;
LABEL_20:
      WPP_SF_d(v16[3].Buffer, v17, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, (unsigned int)UserAccountSettings);
      goto LABEL_193;
    }
    v19 = 0;
    v20 = v8 & 0x400000;
    v21 = 0;
    *(_OWORD *)((char *)a1 + 392) = *(_OWORD *)((char *)a2 + 56);
    *(_OWORD *)((char *)a1 + 408) = *(_OWORD *)((char *)a2 + 72);
    *(_OWORD *)((char *)a1 + 424) = *(_OWORD *)((char *)a2 + 88);
    *(_OWORD *)((char *)a1 + 440) = *(_OWORD *)((char *)a2 + 104);
    *(_OWORD *)((char *)a1 + 456) = *(_OWORD *)((char *)a2 + 120);
    *(_OWORD *)((char *)a1 + 472) = *(_OWORD *)((char *)a2 + 136);
    *(_OWORD *)((char *)a1 + 488) = *(_OWORD *)((char *)a2 + 152);
    *(_OWORD *)((char *)a1 + 504) = *(_OWORD *)((char *)a2 + 168);
    *((_QWORD *)a1 + 65) = *((_QWORD *)a2 + 23);
    v22 = (*(_DWORD *)a2 & 0x1000000) == 0;
    v58 = *((_DWORD *)a1 + 62);
    if ( v22 )
    {
      v30 = WPP_GLOBAL_Control;
      goto LABEL_53;
    }
    if ( v20 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 3u )
      {
LABEL_31:
        if ( v68 && (*(_BYTE *)(&v23[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v23[4].Length) >= 4u )
          WPP_SF_Dd(v23[3].Buffer, 286, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v66, v68);
        v68 = 0;
        v21 = 1;
        if ( v69 != -1 )
          ++v69;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( (*((_BYTE *)a1 + 192) & 2) != 0 && (v25 = (char *)a1 + 272, *((_QWORD *)a1 + 34)) )
        {
          v26 = 8;
          do
          {
            *v25++ = 0;
            --v26;
          }
          while ( v26 );
          updated = SampExtUpdateLockoutTimeExDs(a1, v24);
          v9 = updated;
          if ( updated < 0 )
          {
            v28 = WPP_GLOBAL_Control;
            if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
              || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
            {
              goto LABEL_192;
            }
            v29 = 287;
            goto LABEL_45;
          }
          v30 = WPP_GLOBAL_Control;
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 288, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v66);
            v30 = WPP_GLOBAL_Control;
          }
          v19 = 0;
        }
        else
        {
          v30 = WPP_GLOBAL_Control;
        }
LABEL_53:
        if ( (*(_DWORD *)a2 & 0x20000000) != 0 )
        {
          if ( (*(_DWORD *)a2 & 0xDFFFFFFF) != 0 )
          {
            v9 = -1073741811;
            if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) == 0 || HIBYTE(v30[4].Length) < 2u )
              goto LABEL_192;
            v31 = 289;
            goto LABEL_58;
          }
          if ( v69 )
            --v69;
          GetSystemTimeAsFileTime(&v65);
          v30 = WPP_GLOBAL_Control;
          v21 = 1;
        }
        if ( (*(_DWORD *)a2 & 0x40000000) == 0 )
        {
LABEL_88:
          if ( *(int *)a2 < 0 )
          {
            if ( (*(_DWORD *)a2 & 0x7FFFFFFF) != 0 )
            {
              v9 = -1073741811;
              if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) == 0 || HIBYTE(v30[4].Length) < 2u )
                goto LABEL_192;
              v31 = 294;
LABEL_58:
              WPP_SF_(v30[3].Buffer, v31, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
              goto LABEL_192;
            }
            if ( v20 && (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 3u )
              WPP_SF_(v30[3].Buffer, 295, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
            GetSystemTimeAsFileTime(&v65);
            v30 = WPP_GLOBAL_Control;
            v21 = 1;
          }
          v34 = 0;
          if ( (*(_DWORD *)a2 & 0x8000000) != 0 )
          {
            if ( v20 && (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 3u )
            {
              WPP_SF_(v30[3].Buffer, 296, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
              v30 = WPP_GLOBAL_Control;
            }
            if ( (*(_DWORD *)a2 & 0x10000000) != 0 )
            {
              v19 = (struct _UNICODE_STRING *)((char *)a2 + 24);
              if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 4u )
                WPP_SF_DZ(
                  v30[3].Buffer,
                  297,
                  (unsigned int)WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
                  v66,
                  (__int64)a2 + 24);
            }
            DestinationString = 0;
            *(_OWORD *)hMem = 0;
            RtlInitUnicodeString(&DestinationString, &Annotation);
            if ( !v19 || !RtlCompareUnicodeString(v19, &DestinationString, 0) )
            {
              StrIpAddressFromSocketAddress = SampGetStrIpAddressFromSocketAddress(
                                                (LPSOCKADDR)a2 + 4,
                                                *((_WORD *)a2 + 32) != 23,
                                                (struct _UNICODE_STRING *)hMem);
              v36 = hMem;
              if ( StrIpAddressFromSocketAddress < 0 )
                v36 = (HLOCAL *)v19;
              v19 = (struct _UNICODE_STRING *)v36;
            }
            v37 = SampIncrementBadPasswordCount(
                    a1,
                    (struct _SAMP_V1_0A_FIXED_LENGTH_USER *)v63,
                    v19,
                    (struct _SAMP_USER_ACCOUNT_SETTINGS *)v71);
            LocalFree(hMem[1]);
            if ( v37 )
            {
              v30 = WPP_GLOBAL_Control;
              if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
                && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 298, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v66);
                v30 = WPP_GLOBAL_Control;
              }
              v54 = 1;
            }
            else
            {
              v30 = WPP_GLOBAL_Control;
            }
          }
          if ( (*(_BYTE *)a2 & 2) == 0 )
          {
LABEL_127:
            if ( (*(_BYTE *)a2 & 1) == 0 )
              goto LABEL_136;
            if ( v20 )
            {
              if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) == 0 )
              {
LABEL_135:
                v65 = (struct _FILETIME)*((_QWORD *)a2 + 2);
LABEL_136:
                v38 = *(_DWORD *)a2;
                if ( (*(_DWORD *)a2 & 4) != 0 )
                {
                  if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 4u )
                  {
                    WPP_SF_Dd(
                      v30[3].Buffer,
                      303,
                      WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
                      v66,
                      *((unsigned __int16 *)a2 + 2));
                    v38 = *(_DWORD *)a2;
                    v30 = WPP_GLOBAL_Control;
                  }
                  v68 = *((_WORD *)a2 + 2);
                }
                if ( (v38 & 8) == 0 )
                {
LABEL_150:
                  if ( (*((_BYTE *)a1 + 192) & 2) == 0 )
                    goto LABEL_164;
                  if ( (*(_DWORD *)a2 & 0x20000) != 0 )
                  {
                    v21 = 1;
                    v34 = *(struct _DSNAME **)(*((_QWORD *)a2 + 8) + 176LL);
                  }
                  v39 = *(_DWORD *)a2 & 0x80000;
                  if ( (*(_DWORD *)a2 & 0x100000) != 0 )
                  {
                    if ( !v39 )
                    {
LABEL_160:
                      v40 = 2 - ((*(_DWORD *)a2 & 0x100000) != 0);
                      Buf1 = *(_OWORD *)(*((_QWORD *)a1 + 22) + 8LL);
                      LODWORD(v56) = v40;
                      if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 4u )
                        WPP_SF__guid_(v30[3].Buffer, 306, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
                      else
                        LODWORD(v56) = v40;
LABEL_164:
                      if ( v21 )
                      {
                        if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
                        {
                          v9 = SampExtSuccessfulLogonSetDs(
                                 a1,
                                 *(_DWORD *)a2,
                                 *((_DWORD *)SampDefinedDomains + 340 * *((unsigned int *)a1 + 50) + 326),
                                 (struct _SAMP_V1_0A_FIXED_LENGTH_USER *)v63,
                                 v34);
                          if ( (SamIQueryCapabilities() & 5) == 1 && (*(_DWORD *)a2 & 0x100000) != 0 )
                          {
                            v41 = *((_QWORD *)a1 + 22);
                            v42 = SampShouldCallNtdsaApiSet();
                            v9 = v42;
                            if ( v42 == -1073741637 )
                            {
                              v9 = 0;
                            }
                            else
                            {
                              if ( v42 >= 0 )
                                v9 = NtdsaExtPurgeSecrets(v41);
                              if ( v9 < 0 )
                              {
                                if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
                                  && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
                                {
                                  WPP_SF_Dd(
                                    WPP_GLOBAL_Control[3].Buffer,
                                    307,
                                    WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
                                    v66,
                                    v9);
                                }
                                goto LABEL_191;
                              }
                            }
                            if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
                              && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
                            {
                              WPP_SF_d(
                                WPP_GLOBAL_Control[3].Buffer,
                                308,
                                WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
                                v66);
                            }
                          }
LABEL_191:
                          v2 = v54;
                          goto LABEL_192;
                        }
                      }
                      else if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
                      {
                        v9 = SampExtFailedLogonSetDs(a1, *(_DWORD *)a2, (struct _SAMP_V1_0A_FIXED_LENGTH_USER *)v63);
                        goto LABEL_191;
                      }
                      v43 = SampReplaceUserV1aFixed(a1, v63);
                      v9 = v43;
                      if ( v43 < 0 )
                      {
                        v44 = WPP_GLOBAL_Control;
                        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
                          || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
                        {
                          goto LABEL_190;
                        }
                        v45 = 310;
                      }
                      else
                      {
                        v43 = SampRegistryUpdateInteractiveLogonStatistics(a1, a2);
                        v9 = v43;
                        if ( v43 >= 0 )
                          goto LABEL_190;
                        v44 = WPP_GLOBAL_Control;
                        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
                          || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
                        {
                          goto LABEL_190;
                        }
                        v45 = 309;
                      }
                      WPP_SF_Dd(v44[3].Buffer, v45, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v66, v43);
LABEL_190:
                      v57 = 1;
                      goto LABEL_191;
                    }
                  }
                  else if ( !v39 )
                  {
                    goto LABEL_164;
                  }
                  if ( (SamIQueryCapabilities() & 5) != 1 )
                  {
                    v9 = -1073741811;
                    goto LABEL_191;
                  }
                  v30 = WPP_GLOBAL_Control;
                  goto LABEL_160;
                }
                if ( v20 )
                {
                  if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) == 0 )
                  {
LABEL_149:
                    v69 = *((_WORD *)a2 + 3);
                    goto LABEL_150;
                  }
                  if ( HIBYTE(v30[4].Length) >= 3u )
                  {
                    WPP_SF_(v30[3].Buffer, 304, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
                    v30 = WPP_GLOBAL_Control;
                  }
                }
                if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 4u )
                {
                  WPP_SF_Dd(
                    v30[3].Buffer,
                    305,
                    WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
                    v66,
                    *((unsigned __int16 *)a2 + 3));
                  v30 = WPP_GLOBAL_Control;
                }
                goto LABEL_149;
              }
              if ( HIBYTE(v30[4].Length) >= 3u )
              {
                WPP_SF_(v30[3].Buffer, 301, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
                v30 = WPP_GLOBAL_Control;
              }
            }
            if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 4u )
            {
              WPP_SF_Di(v30[3].Buffer, 302, v18, v66, *((_QWORD *)a2 + 2));
              v30 = WPP_GLOBAL_Control;
            }
            goto LABEL_135;
          }
          if ( v20 )
          {
            if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) == 0 )
            {
LABEL_126:
              SystemTimeAsFileTime = (struct _FILETIME)*((_QWORD *)a2 + 1);
              goto LABEL_127;
            }
            if ( HIBYTE(v30[4].Length) >= 3u )
            {
              WPP_SF_(v30[3].Buffer, 299, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
              v30 = WPP_GLOBAL_Control;
            }
          }
          if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 4u )
          {
            WPP_SF_Di(v30[3].Buffer, 300, v18, v66, *((_QWORD *)a2 + 1));
            v30 = WPP_GLOBAL_Control;
          }
          goto LABEL_126;
        }
        if ( v20 )
        {
          if ( (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 4u )
            WPP_SF_d(v30[3].Buffer, 290, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v66);
          if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
            v68 = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        }
        else
        {
          if ( v68 && (*(_BYTE *)(&v30[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v30[4].Length) >= 4u )
            WPP_SF_Dd(v30[3].Buffer, 291, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v66, v68);
          v68 = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
          {
            v32 = (char *)a1 + 272;
            if ( *((_QWORD *)a1 + 34) )
            {
              v33 = 8;
              do
              {
                *v32++ = 0;
                --v33;
              }
              while ( v33 );
              updated = SampExtUpdateLockoutTimeExDs(a1, 1u);
              v9 = updated;
              if ( updated < 0 )
              {
                v28 = WPP_GLOBAL_Control;
                if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
                  || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
                {
                  goto LABEL_192;
                }
                v29 = 292;
LABEL_45:
                WPP_SF_d(v28[3].Buffer, v29, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, (unsigned int)updated);
LABEL_192:
                v7 = v56;
LABEL_193:
                v46 = SampDeReferenceContext(a1, v9 >= 0);
                if ( v46 < 0 && v9 >= 0 )
                  v9 = v46;
                if ( !v55[0] )
                {
                  if ( v9 < 0 )
                    v52 = 2;
                  else
                    v52 = 3;
                  SampExtMaybeEndDsTransactionDs(v52);
                  v51 = v58;
LABEL_212:
                  if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
                    SampExtQueueReplicationRequestDs(&Buf1, *((_QWORD *)a1 + 22) + 56LL, v7);
                  if ( v57 )
                    SampLAPSNotifyLocalAccountAuthentication(v51, a2);
                  v10 = WPP_GLOBAL_Control;
                  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                  {
                    v11 = 311;
                    goto LABEL_14;
                  }
                  return (unsigned int)v9;
                }
                if ( v9 < 0 )
                {
                  v51 = v58;
                }
                else
                {
                  if ( !v2 && (*((_BYTE *)a1 + 192) & 2) == 0 )
                  {
                    v47 = 1360LL * SampTransactionDomainIndexGlobal;
                    v48 = SampDefinedDomains;
                    if ( *(_DWORD *)((char *)SampDefinedDomains + v47 + 220) != 2 )
                    {
                      --*(_QWORD *)((char *)SampDefinedDomains + v47 + 144);
                      --*(_QWORD *)((char *)v48 + v47 + 872);
                    }
                  }
                  v49 = SampAsyncCommitAllowed(a1, a2);
                  v50 = SampCommitAndRetainWriteLockEx(v49);
                  v51 = v58;
                  v9 = v50;
                  if ( v50 >= 0 && v2 )
                  {
                    v56 = v67;
                    SampNotifyNetlogonOfDelta(7, 2, v58, 0, v2, &v56);
                  }
                }
LABEL_211:
                SampReleaseWriteLock(0);
                goto LABEL_212;
              }
              v30 = WPP_GLOBAL_Control;
              if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
                && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 293, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v66);
                v30 = WPP_GLOBAL_Control;
              }
              v19 = 0;
              goto LABEL_87;
            }
          }
        }
        v30 = WPP_GLOBAL_Control;
LABEL_87:
        v21 = 1;
        goto LABEL_88;
      }
      WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 285, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids);
    }
    v23 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v10 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v11 = 282;
LABEL_14:
    v12 = (unsigned int)v9;
LABEL_220:
    WPP_SF_Dd(v10[3].Buffer, v11, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v12, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002b810  mov     [rsp-8+arg_10], rbx
0x18002b815  push    rbp
0x18002b816  push    rsi
0x18002b817  push    rdi
0x18002b818  push    r12
0x18002b81a  push    r13
0x18002b81c  push    r14
0x18002b81e  push    r15
0x18002b820  lea     rbp, [rsp-50h]
0x18002b825  sub     rsp, 150h
0x18002b82c  mov     rax, cs:__security_cookie
0x18002b833  xor     rax, rsp
0x18002b836  mov     [rbp+80h+var_40], rax
0x18002b83a  xor     r13d, r13d
0x18002b83d  mov     rdi, rdx
0x18002b840  mov     rsi, rcx
0x18002b843  mov     [rsp+180h+var_108], r13d
0x18002b848  xor     edx, edx; Val
0x18002b84a  lea     rcx, [rbp+80h+var_D0]; void *
0x18002b84e  lea     ebx, [r13+50h]
0x18002b852  mov     r8d, ebx; Size
0x18002b855  call    memset_0
0x18002b85a  xorps   xmm0, xmm0
0x18002b85d  mov     [rsp+180h+var_11F], r13b
0x18002b862  xorps   xmm1, xmm1
0x18002b865  lea     rax, [rbp+80h+var_D0]
0x18002b869  movups  [rbp+80h+Buf1], xmm0
0x18002b86d  lea     edx, [rbx-4Fh]
0x18002b870  movups  [rbp+80h+Buf2], xmm1
0x18002b874  movups  [rbp+80h+var_70], xmm0
0x18002b878  movups  [rbp+80h+var_60], xmm0
0x18002b87c  movups  [rbp+80h+var_50], xmm0
0x18002b880  mov     [rax], r13b
0x18002b883  add     rax, rdx
0x18002b886  sub     rbx, rdx
0x18002b889  jnz     short loc_18002B880
0x18002b88b  test    rsi, rsi
0x18002b88e  jz      loc_18002C3EA
0x18002b894  test    rdi, rdi
0x18002b897  jz      loc_18002C3EA
0x18002b89d  mov     [rsp+180h+var_10C], r13d
0x18002b8a2  mov     r15d, edx
0x18002b8a5  mov     [rsp+180h+var_110], r13b
0x18002b8aa  mov     dword ptr [rsp+180h+var_118], edx
0x18002b8ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8b5  test    byte ptr [rcx+44h], 20h
0x18002b8b9  jz      short loc_18002B90E
0x18002b8bb  cmp     byte ptr [rcx+41h], 4
0x18002b8bf  jb      short loc_18002B90E
0x18002b8c1  movzx   r9d, word ptr [rdi+4]
0x18002b8c6  lea     rax, [rdi+28h]
0x18002b8ca  movzx   r8d, word ptr [rdi+6]
0x18002b8cf  lea     rdx, [rdi+18h]
0x18002b8d3  mov     rcx, [rcx+38h]
0x18002b8d7  mov     [rsp+180h+var_130], rax
0x18002b8dc  mov     rax, [rdi+10h]
0x18002b8e0  mov     [rsp+180h+var_138], rdx
0x18002b8e5  mov     [rsp+180h+var_140], rax
0x18002b8ea  mov     rax, [rdi+8]
0x18002b8ee  mov     [rsp+180h+var_148], rax
0x18002b8f3  mov     eax, [rdi]
0x18002b8f5  mov     [rsp+180h+var_150], r8d
0x18002b8fa  mov     dword ptr [rsp+180h+var_158], r9d
0x18002b8ff  mov     r9, rsi
0x18002b902  mov     dword ptr [rsp+180h+var_160], eax
0x18002b906  call    WPP_SF_qDDDiiZZ
0x18002b90b  lea     edx, [rbx+1]
0x18002b90e  lea     r14, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x18002b915  mov     r12d, [rdi]
0x18002b918  test    [rsi+1Ch], dl
0x18002b91b  jz      short loc_18002B934
0x18002b91d  test    byte ptr [rsi+0C0h], 2
0x18002b924  jz      short loc_18002B934
0x18002b926  mov     [rsp+180h+var_11F], r13b
0x18002b92b  lock add [rsi+90h], edx
0x18002b932  jmp     short loc_18002B98D
0x18002b934  lea     rdx, [rsp+180h+var_11F]; unsigned __int8 *
0x18002b939  mov     rcx, rsi; struct _SAMP_OBJECT *
0x18002b93c  call    ?SampMaybeAcquireWriteLock@@YAJPEAU_SAMP_OBJECT@@PEAE@Z; SampMaybeAcquireWriteLock(_SAMP_OBJECT *,uchar *)
0x18002b941  mov     ebx, eax
0x18002b943  test    eax, eax
0x18002b945  jns     short loc_18002B96B
0x18002b947  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b94e  test    dword ptr [rcx+44h], 20000h
0x18002b955  jz      loc_18002C41E
0x18002b95b  mov     edx, 11Ah
0x18002b960  mov     r9d, ebx
0x18002b963  mov     r8, r14
0x18002b966  jmp     loc_18002C411
0x18002b96b  xor     edx, edx
0x18002b96d  mov     [rsp+180h+var_11F], r15b
0x18002b972  lea     r9, [rsp+180h+var_108]
0x18002b977  mov     rcx, rsi
0x18002b97a  lea     r8d, [rdx+4]
0x18002b97e  call    SampLookupContext
0x18002b983  mov     ebx, eax
0x18002b985  test    eax, eax
0x18002b987  js      loc_18002C366
0x18002b98d  lea     rdx, [rbp+80h+var_70]
0x18002b991  mov     [rsp+180h+var_120], r13b
0x18002b996  mov     rcx, rsi
0x18002b999  call    SampGetUserAccountSettings
0x18002b99e  mov     ebx, eax
0x18002b9a0  test    eax, eax
0x18002b9a2  jns     short loc_18002B9D8
0x18002b9a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9ab  test    byte ptr [rcx+44h], 20h
0x18002b9af  jz      loc_18002C289
0x18002b9b5  cmp     byte ptr [rcx+41h], 2
0x18002b9b9  jb      loc_18002C289
0x18002b9bf  mov     edx, 11Bh
0x18002b9c4  mov     rcx, [rcx+38h]
0x18002b9c8  mov     r9d, eax
0x18002b9cb  mov     r8, r14
0x18002b9ce  call    WPP_SF_d
0x18002b9d3  jmp     loc_18002C289
0x18002b9d8  lea     rdx, [rbp+80h+var_D0]
0x18002b9dc  mov     rcx, rsi
0x18002b9df  call    SampRetrieveUserV1aFixed
0x18002b9e4  mov     ebx, eax
0x18002b9e6  test    eax, eax
0x18002b9e8  jns     short loc_18002BA0C
0x18002b9ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9f1  test    byte ptr [rcx+44h], 20h
0x18002b9f5  jz      loc_18002C289
0x18002b9fb  cmp     byte ptr [rcx+41h], 2
0x18002b9ff  jb      loc_18002C289
0x18002ba05  mov     edx, 11Ch
0x18002ba0a  jmp     short loc_18002B9C4
0x18002ba0c  movups  xmm0, xmmword ptr [rdi+38h]
0x18002ba10  xor     ebx, ebx
0x18002ba12  and     r12d, 400000h
0x18002ba19  mov     r15b, bl
0x18002ba1c  mov     edx, 0FFFFh
0x18002ba21  movups  xmmword ptr [rsi+188h], xmm0
0x18002ba28  movups  xmm1, xmmword ptr [rdi+48h]
0x18002ba2c  movups  xmmword ptr [rsi+198h], xmm1
0x18002ba33  movups  xmm0, xmmword ptr [rdi+58h]
0x18002ba37  movups  xmmword ptr [rsi+1A8h], xmm0
0x18002ba3e  movups  xmm1, xmmword ptr [rdi+68h]
0x18002ba42  movups  xmmword ptr [rsi+1B8h], xmm1
0x18002ba49  movups  xmm0, xmmword ptr [rdi+78h]
0x18002ba4d  movups  xmmword ptr [rsi+1C8h], xmm0
0x18002ba54  movups  xmm1, xmmword ptr [rdi+88h]
0x18002ba5b  movups  xmmword ptr [rsi+1D8h], xmm1
0x18002ba62  movups  xmm0, xmmword ptr [rdi+98h]
0x18002ba69  movups  xmmword ptr [rsi+1E8h], xmm0
0x18002ba70  movups  xmm1, xmmword ptr [rdi+0A8h]
0x18002ba77  movups  xmmword ptr [rsi+1F8h], xmm1
0x18002ba7e  mov     rax, [rdi+0B8h]
0x18002ba85  mov     [rsi+208h], rax
0x18002ba8c  test    dword ptr [rdi], 1000000h
0x18002ba92  mov     eax, [rsi+0F8h]
0x18002ba98  mov     [rsp+180h+var_10C], eax
0x18002ba9c  jz      loc_18002BBD9
0x18002baa2  test    r12d, r12d
0x18002baa5  jz      short loc_18002BACB
0x18002baa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002baae  test    byte ptr [rcx+44h], 20h
0x18002bab2  jz      short loc_18002BAD2
0x18002bab4  cmp     byte ptr [rcx+41h], 3
0x18002bab8  jb      short loc_18002BAD2
0x18002baba  mov     rcx, [rcx+38h]
0x18002babe  mov     edx, 11Dh
0x18002bac3  mov     r8, r14
0x18002bac6  call    WPP_SF_
0x18002bacb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bad2  movzx   eax, [rbp+80h+var_90]
0x18002bad6  test    ax, ax
0x18002bad9  jz      short loc_18002BB00
0x18002badb  test    byte ptr [rcx+44h], 20h
0x18002badf  jz      short loc_18002BB00
0x18002bae1  cmp     byte ptr [rcx+41h], 4
0x18002bae5  jb      short loc_18002BB00
0x18002bae7  mov     r9d, [rbp+80h+var_A0]
0x18002baeb  mov     edx, 11Eh
0x18002baf0  mov     rcx, [rcx+38h]
0x18002baf4  mov     r8, r14
0x18002baf7  mov     dword ptr [rsp+180h+var_160], eax
0x18002bafb  call    WPP_SF_Dd
0x18002bb00  movzx   eax, [rbp+80h+var_8E]
0x18002bb04  mov     ecx, 0FFFFh
0x18002bb09  mov     [rbp+80h+var_90], bx
0x18002bb0d  mov     r15d, 1
0x18002bb13  cmp     ax, cx
0x18002bb16  jz      short loc_18002BB20
0x18002bb18  add     ax, r15w
0x18002bb1c  mov     [rbp+80h+var_8E], ax
0x18002bb20  lea     rcx, [rbp+80h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002bb24  call    cs:__imp_GetSystemTimeAsFileTime
0x18002bb2a  test    byte ptr [rsi+0C0h], 2
0x18002bb31  jz      loc_18002BBD0
0x18002bb37  lea     rax, [rsi+110h]
0x18002bb3e  cmp     [rax], rbx
0x18002bb41  jz      loc_18002BBD0
0x18002bb47  mov     ecx, 8
0x18002bb4c  mov     [rax], bl
0x18002bb4e  add     rax, r15
0x18002bb51  sub     rcx, r15
0x18002bb54  jnz     short loc_18002BB4C
0x18002bb56  mov     rcx, rsi; struct _SAMP_OBJECT *
0x18002bb59  call    ?SampExtUpdateLockoutTimeExDs@@YAJPEAU_SAMP_OBJECT@@E@Z; SampExtUpdateLockoutTimeExDs(_SAMP_OBJECT *,uchar)
0x18002bb5e  mov     ebx, eax
0x18002bb60  test    eax, eax
0x18002bb62  jns     short loc_18002BB98
0x18002bb64  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb6b  test    byte ptr [rcx+44h], 20h
0x18002bb6f  jz      loc_18002C284
0x18002bb75  cmp     byte ptr [rcx+41h], 2
0x18002bb79  jb      loc_18002C284
0x18002bb7f  mov     edx, 11Fh
0x18002bb84  mov     rcx, [rcx+38h]
0x18002bb88  mov     r9d, eax
0x18002bb8b  mov     r8, r14
0x18002bb8e  call    WPP_SF_d
0x18002bb93  jmp     loc_18002C284
0x18002bb98  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb9f  test    byte ptr [rcx+44h], 20h
0x18002bba3  jz      short loc_18002BBC7
0x18002bba5  cmp     byte ptr [rcx+41h], 4
0x18002bba9  jb      short loc_18002BBC7
0x18002bbab  mov     r9d, [rbp+80h+var_A0]
0x18002bbaf  mov     edx, 120h
0x18002bbb4  mov     rcx, [rcx+38h]
0x18002bbb8  mov     r8, r14
0x18002bbbb  call    WPP_SF_d
0x18002bbc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbc7  xor     ebx, ebx
0x18002bbc9  mov     edx, 0FFFFh
0x18002bbce  jmp     short loc_18002BBE0
0x18002bbd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbd7  jmp     short loc_18002BBC9
0x18002bbd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbe0  test    dword ptr [rdi], 20000000h
0x18002bbe6  jz      short loc_18002BC43
0x18002bbe8  test    dword ptr [rdi], 0DFFFFFFFh
0x18002bbee  jz      short loc_18002BC1F
0x18002bbf0  mov     ebx, 0C000000Dh
0x18002bbf5  test    byte ptr [rcx+44h], 20h
0x18002bbf9  jz      loc_18002C284
0x18002bbff  cmp     byte ptr [rcx+41h], 2
0x18002bc03  jb      loc_18002C284
0x18002bc09  mov     edx, 121h
0x18002bc0e  mov     rcx, [rcx+38h]
0x18002bc12  mov     r8, r14
0x18002bc15  call    WPP_SF_
0x18002bc1a  jmp     loc_18002C284
0x18002bc1f  movzx   eax, [rbp+80h+var_8E]
0x18002bc23  test    ax, ax
0x18002bc26  jz      short loc_18002BC2F
0x18002bc28  add     ax, dx
0x18002bc2b  mov     [rbp+80h+var_8E], ax
0x18002bc2f  lea     rcx, [rbp+80h+var_C0]; lpSystemTimeAsFileTime
0x18002bc33  call    cs:__imp_GetSystemTimeAsFileTime
0x18002bc39  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc40  mov     r15b, 1
0x18002bc43  test    dword ptr [rdi], 40000000h
0x18002bc49  jz      loc_18002BD62
0x18002bc4f  test    r12d, r12d
0x18002bc52  jz      short loc_18002BC98
0x18002bc54  test    byte ptr [rcx+44h], 20h
0x18002bc58  jz      short loc_18002BC75
0x18002bc5a  cmp     byte ptr [rcx+41h], 4
0x18002bc5e  jb      short loc_18002BC75
0x18002bc60  mov     r9d, [rbp+80h+var_A0]
0x18002bc64  mov     edx, 122h
0x18002bc69  mov     rcx, [rcx+38h]
0x18002bc6d  mov     r8, r14
0x18002bc70  call    WPP_SF_d
0x18002bc75  test    byte ptr [rsi+0C0h], 2
0x18002bc7c  jz      short loc_18002BC82
0x18002bc7e  mov     [rbp+80h+var_90], bx
0x18002bc82  lea     rcx, [rbp+80h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002bc86  call    cs:__imp_GetSystemTimeAsFileTime
0x18002bc8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc93  jmp     loc_18002BD5F
0x18002bc98  movzx   eax, [rbp+80h+var_90]
0x18002bc9c  test    ax, ax
0x18002bc9f  jz      short loc_18002BCC6
0x18002bca1  test    byte ptr [rcx+44h], 20h
0x18002bca5  jz      short loc_18002BCC6
0x18002bca7  cmp     byte ptr [rcx+41h], 4
0x18002bcab  jb      short loc_18002BCC6
0x18002bcad  mov     r9d, [rbp+80h+var_A0]
0x18002bcb1  mov     edx, 123h
0x18002bcb6  mov     rcx, [rcx+38h]
0x18002bcba  mov     r8, r14
0x18002bcbd  mov     dword ptr [rsp+180h+var_160], eax
0x18002bcc1  call    WPP_SF_Dd
0x18002bcc6  lea     rcx, [rbp+80h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002bcca  mov     [rbp+80h+var_90], bx
0x18002bcce  call    cs:__imp_GetSystemTimeAsFileTime
0x18002bcd4  test    byte ptr [rsi+0C0h], 2
0x18002bcdb  jz      short loc_18002BC8C
0x18002bcdd  lea     rax, [rsi+110h]
0x18002bce4  cmp     [rax], rbx
0x18002bce7  jz      short loc_18002BC8C
0x18002bce9  mov     ecx, 8
0x18002bcee  lea     edx, [rcx-7]; unsigned __int8
0x18002bcf1  mov     [rax], bl
  ... truncated ...
```
