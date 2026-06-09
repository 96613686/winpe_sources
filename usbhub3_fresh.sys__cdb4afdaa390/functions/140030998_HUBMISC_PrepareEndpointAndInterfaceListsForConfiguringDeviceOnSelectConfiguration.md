# HUBMISC_PrepareEndpointAndInterfaceListsForConfiguringDeviceOnSelectConfiguration

- ea: `0x140030998`
- end: `0x14003174c`
- name: `HUBMISC_PrepareEndpointAndInterfaceListsForConfiguringDeviceOnSelectConfiguration`
- size: `3508`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140022da0`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000c578`
- `0x14001892c`
- `0x140030998`
- `0x140033b30`
- `0x14003bd60`
- `0x140045530`
- `0x140045570`
- `0x140045640`
- `0x140045940`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140030a59`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030a59`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030a26`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030a26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003149b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400314bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400314dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003158d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400315ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400315cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003149b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400314bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400314dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003158d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400315ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400315cf`
- `ntoskrnl!ExAllocatePool2` at `0x14003151a`
- `ntoskrnl!ExAllocatePool2` at `0x14003153a`
- `ntoskrnl!ExAllocatePool2` at `0x14003155d`
- `ntoskrnl!ExAllocatePool2` at `0x14003151a`
- `ntoskrnl!ExAllocatePool2` at `0x14003153a`
- `ntoskrnl!ExAllocatePool2` at `0x14003155d`

## pseudocode

```c
__int64 __fastcall HUBMISC_PrepareEndpointAndInterfaceListsForConfiguringDeviceOnSelectConfiguration(__int64 a1)
{
  __int64 v1; // rdx
  unsigned __int16 *v3; // r13
  KIRQL v4; // al
  __int64 *v5; // r14
  size_t v6; // rsi
  int v7; // edx
  int v8; // ebx
  _QWORD *v9; // r15
  unsigned __int8 *v10; // r10
  unsigned __int16 *v11; // r14
  unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rax
  unsigned int v14; // r13d
  __int64 v15; // rax
  int v16; // r9d
  int v17; // r8d
  unsigned __int8 *v18; // rax
  int v19; // edx
  unsigned __int8 *v20; // rsi
  _DWORD *v21; // rcx
  unsigned int v22; // edx
  size_t v23; // r15
  int v24; // edx
  _QWORD *v25; // rbx
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  char *v28; // r10
  unsigned __int8 *v29; // rdx
  unsigned __int64 v30; // r9
  __int64 v31; // rax
  unsigned __int8 *v32; // rcx
  __int64 v33; // r15
  __int64 v34; // r13
  _BYTE *v35; // rax
  __int64 v36; // rax
  int v37; // r9d
  int v38; // ecx
  int v39; // r8d
  unsigned __int16 v40; // r8
  char v41; // cl
  __int64 v42; // rcx
  __int64 v43; // rax
  unsigned __int8 *v44; // rbx
  _BYTE *v45; // rsi
  unsigned __int16 v46; // ax
  __int64 v47; // rax
  unsigned __int8 *v48; // rcx
  int v49; // eax
  unsigned int v50; // r8d
  int v51; // eax
  _QWORD *v52; // rsi
  _QWORD **v53; // rdi
  _QWORD *v54; // rdx
  _QWORD *v55; // rax
  __int64 v56; // r9
  __int64 v57; // rax
  __int64 v58; // rdx
  unsigned int v59; // r11d
  unsigned int i; // r8d
  __int64 v61; // rdx
  int v62; // edx
  unsigned __int16 v63; // bx
  int v64; // r8d
  __int64 k; // rax
  __int64 v66; // r10
  unsigned int v67; // r11d
  unsigned int v68; // r15d
  __int64 v69; // rax
  char *v70; // rcx
  unsigned __int16 *v71; // rsi
  char v72; // bl
  char v73; // cl
  unsigned int v74; // eax
  void *v75; // rcx
  void *v76; // rcx
  void *v77; // rcx
  __int64 Pool2; // rax
  int v79; // edx
  __int64 v80; // rax
  __int64 v81; // rax
  void *v82; // rcx
  void *v83; // rcx
  void *v84; // rcx
  __int64 v85; // rcx
  _QWORD *v86; // rcx
  __int64 v87; // r8
  unsigned int j; // r9d
  int v89; // ecx
  __int64 v90; // rcx
  __int64 v91; // rax
  int v93; // [rsp+20h] [rbp-E0h]
  __int64 *v94; // [rsp+28h] [rbp-D8h]
  __int64 v95; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v96; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v97; // [rsp+54h] [rbp-ACh] BYREF
  int v98; // [rsp+58h] [rbp-A8h] BYREF
  void *v99; // [rsp+60h] [rbp-A0h]
  char *v100; // [rsp+68h] [rbp-98h]
  unsigned int v101; // [rsp+70h] [rbp-90h]
  unsigned __int64 v102; // [rsp+78h] [rbp-88h]
  __int64 v103; // [rsp+80h] [rbp-80h] BYREF
  __int64 v104; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v105; // [rsp+90h] [rbp-70h]
  _QWORD *v106; // [rsp+98h] [rbp-68h]
  __int64 v107; // [rsp+A0h] [rbp-60h]
  __int128 v108; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v109; // [rsp+B8h] [rbp-48h]
  __int128 v110; // [rsp+C8h] [rbp-38h]
  __int64 v111; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v112; // [rsp+E8h] [rbp-18h]
  _OWORD v113[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v114; // [rsp+110h] [rbp+10h]

  v1 = *(_QWORD *)(a1 + 464);
  LODWORD(v111) = 0;
  v114 = 0;
  *(_DWORD *)(a1 + 112) = 0;
  memset(v113, 0, sizeof(v113));
  v103 = 0;
  LOWORD(v113[0]) = 40;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    v1,
    v113);
  v3 = (unsigned __int16 *)*((_QWORD *)&v113[0] + 1);
  v107 = *((_QWORD *)&v113[0] + 1);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 40));
  _InterlockedAnd((volatile signed __int32 *)(a1 + 1644), 0xFFFFFFEF);
  v5 = (__int64 *)(a1 + 48);
  *(_QWORD *)(a1 + 56) = *(_QWORD *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = 0;
  _InterlockedAnd((volatile signed __int32 *)(a1 + 1644), 0xFFFF7FFF);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 40), v4);
  v111 = 0;
  v94 = &v103;
  *(_QWORD *)&v109 = 0;
  v108 = 0;
  *((_QWORD *)&v109 + 1) = 0x100000001LL;
  v110 = 0;
  LODWORD(v108) = 56;
  v6 = *(unsigned __int16 *)(*((_QWORD *)v3 + 3) + 2LL);
  v93 = v6 + 39;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64))(WdfFunctions_01015 + 1536))(
         WdfDriverGlobals,
         &v108,
         512,
         1681082453);
  if ( v8 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v94) = v8;
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v7,
        5,
        31,
        (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
        v94);
    }
    goto LABEL_101;
  }
  v9 = (_QWORD *)*v5;
  v106 = v9;
  *v9 = v103;
  memmove((void *)(*v5 + 32), *((const void **)v3 + 3), v6);
  v10 = (unsigned __int8 *)(v9 + 4);
  v9[3] = v9 + 2;
  v9[2] = v9 + 2;
  v11 = v3 + 20;
  v12 = (unsigned __int16 *)((char *)v3 + *v3);
  v105 = (unsigned __int8 *)(v9 + 4);
  v13 = v3 + 21;
  v112 = (unsigned __int64)v12;
  v101 = 0;
  v14 = 0;
  if ( v13 < v12 )
  {
    while ( 1 )
    {
      v15 = *(_QWORD *)(a1 + 8);
      v104 = 0;
      v99 = 0;
      v16 = *((unsigned __int8 *)v11 + 3);
      v17 = *((unsigned __int8 *)v11 + 2);
      v95 = *(_QWORD *)(v15 + 1432);
      LOBYTE(v98) = 0;
      v18 = HUBDESC_ParseConfigurationDescriptor((__int64)v10, v10, v17, v16, -1, -1, -1, &v98, v95);
      v20 = v18;
      if ( !v18 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v19) = 2;
          WPP_RECORDER_SF_(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
            v19,
            5,
            32,
            (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
        }
        v8 = -1073741823;
        *(_DWORD *)(a1 + 1572) = -1073737984;
        goto LABEL_100;
      }
      v21 = *(_DWORD **)(a1 + 2456);
      if ( v21 && *v21 )
      {
        v22 = 0;
        while ( *((_BYTE *)v21 + 2 * v22 + 5) != v18[3] || *((_BYTE *)v21 + 2 * v22 + 4) != v18[2] )
        {
          if ( ++v22 >= *v21 )
            goto LABEL_14;
        }
        _InterlockedOr((volatile signed __int32 *)(a1 + 1644), 0x8000u);
      }
LABEL_14:
      *((_DWORD *)v11 + 4) = v18[4];
      LOBYTE(v96) = v18[4];
      v97 = *v11;
      v111 = 0;
      *(_QWORD *)&v109 = 0;
      v108 = 0;
      *((_QWORD *)&v109 + 1) = 0x100000001LL;
      v110 = 0;
      LODWORD(v108) = 56;
      v94 = &v104;
      v23 = 80LL * *((unsigned int *)v11 + 4) + 40;
      v93 = 80 * *((_DWORD *)v11 + 4) + 40;
      v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64))(WdfFunctions_01015 + 1536))(
             WdfDriverGlobals,
             &v108,
             512,
             1681082453);
      if ( v8 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v94) = v8;
          LOBYTE(v24) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
            v24,
            2,
            33,
            (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
            v94);
        }
        goto LABEL_100;
      }
      *((_QWORD *)v11 + 1) = v99;
      memset(v99, 0, v23);
      *(_QWORD *)v99 = v104;
      *((_QWORD *)v99 + 4) = v20;
      *((_DWORD *)v99 + 6) = v20[4];
      if ( (_BYTE)v98 == 1 )
      {
        _InterlockedOr((volatile signed __int32 *)v99 + 7, 1u);
        _InterlockedOr((volatile signed __int32 *)v99 + 7, 2u);
      }
      v25 = v106 + 2;
      v26 = (_QWORD *)v106[3];
      if ( (_QWORD *)*v26 != v106 + 2 )
LABEL_175:
        __fastfail(3u);
      v27 = v99;
      *((_QWORD *)v99 + 2) = v26;
      *++v27 = v25;
      *v26 = v27;
      v25[1] = v27;
      *((_BYTE *)v11 + 4) = v20[5];
      *((_BYTE *)v11 + 5) = v20[6];
      *((_BYTE *)v11 + 6) = v20[7];
      v28 = (char *)v99;
      v29 = &v20[*v20];
      v100 = (char *)v99;
      v30 = (unsigned __int64)&v105[*(unsigned __int16 *)(*(_QWORD *)(v107 + 24) + 2LL)];
      v31 = 0;
      v102 = v30;
      v98 = 0;
      if ( *((_DWORD *)v11 + 4) )
        break;
LABEL_82:
      v14 += (unsigned __int8)v96;
      v11 = (unsigned __int16 *)((char *)v11 + v97);
      v101 = v14;
      if ( (unsigned __int64)(v11 + 1) >= v112 )
        goto LABEL_114;
      v10 = v105;
    }
    while ( 1 )
    {
      v32 = v29;
      if ( (unsigned __int64)v29 >= v30 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_99;
        v37 = 22;
        goto LABEL_98;
      }
      v33 = 80 * v31;
      v34 = 3 * v31;
      *(_DWORD *)&v28[v33 + 64] = *(_DWORD *)&v11[12 * v31 + 22];
      v35 = v29 + 1;
      *(_DWORD *)&v28[v33 + 48] = 1;
      if ( (unsigned __int64)(v29 + 1) >= v30 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_99;
        v37 = 23;
        goto LABEL_98;
      }
      while ( *v35 != 5 )
      {
        v36 = *v32;
        if ( !(_BYTE)v36 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_99;
          v37 = 24;
          goto LABEL_98;
        }
        v29 += v36;
        v32 = v29;
        if ( (unsigned __int64)v29 >= v30 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_99;
          v37 = 25;
          goto LABEL_98;
        }
        v35 = v29 + 1;
        if ( (unsigned __int64)(v29 + 1) >= v30 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_99;
          v37 = 26;
LABEL_98:
          LOBYTE(v29) = 2;
          WPP_RECORDER_SF_(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
            (_DWORD)v29,
            5,
            v37,
            (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
          goto LABEL_99;
        }
      }
      if ( (unsigned __int64)v29 >= v30 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_99;
        v37 = 27;
        goto LABEL_98;
      }
      if ( (unsigned __int64)(v29 + 7) > v30 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_99;
        v37 = 28;
        goto LABEL_98;
      }
      v38 = 1;
      if ( (*(_DWORD *)&v11[4 * v34 + 22] & 1) != 0 )
        *((_WORD *)v29 + 2) = v11[4 * v34 + 12];
      v39 = *(_DWORD *)&v11[4 * v34 + 22] & 0xF0;
      if ( v39 == 16 )
        goto LABEL_35;
      if ( v39 != 32 )
        break;
      *(_DWORD *)&v28[v33 + 112] = 2;
LABEL_36:
      *(_QWORD *)&v28[v33 + 72] = v29;
      *(_DWORD *)&v28[v33 + 80] = v30 - (_DWORD)v29;
      if ( *(_WORD *)(a1 + 1998) >= 0x250u )
        v40 = *((_WORD *)v29 + 2);
      else
        v40 = (*((_WORD *)v29 + 2) & 0x7FF) * (((*((_WORD *)v29 + 2) >> 11) & 3) + 1);
      v11[4 * v34 + 12] = v40;
      v41 = 6;
      if ( v29[6] < 6u )
        v41 = v29[6];
      HIBYTE(v11[4 * v34 + 13]) = v41;
      LOBYTE(v11[4 * v34 + 13]) = v29[2];
      v42 = v29[3] & 3;
      if ( (v29[3] & 3) != 0 )
      {
        v42 = (unsigned int)(v42 - 1);
        if ( (_DWORD)v42 )
        {
          v42 = (unsigned int)(v42 - 1);
          if ( (_DWORD)v42 )
          {
            if ( (_DWORD)v42 == 1 )
              *(_DWORD *)&v11[4 * v34 + 14] = 3;
          }
          else
          {
            *(_DWORD *)&v11[4 * v34 + 14] = 2;
          }
        }
        else
        {
          *(_DWORD *)&v11[4 * v34 + 14] = 1;
        }
      }
      else
      {
        *(_DWORD *)&v11[4 * v34 + 14] = 0;
      }
      if ( !v40 )
        _InterlockedOr((volatile signed __int32 *)&v28[v33 + 52], 1u);
      v43 = *v29;
      if ( !(_BYTE)v43 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_99;
        v37 = 29;
        goto LABEL_98;
      }
      v44 = &v29[v43];
      v29 = v44;
      if ( (unsigned __int64)v44 >= v30 )
        goto LABEL_80;
      v45 = v44 + 1;
      if ( (unsigned __int64)(v44 + 1) >= v30 )
        goto LABEL_80;
      if ( !(unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline(v42, v44)
        || (unsigned __int16)(*(_WORD *)(a1 + 1998) - 544) > 0xDFu
        || *v45 != 18 )
      {
        v30 = v102;
        v28 = v100;
LABEL_63:
        v29 = v44;
        if ( *v45 == 48 )
        {
          if ( *v44 )
          {
            if ( (unsigned __int64)(v44 + 6) <= v30 )
            {
              v47 = *(_QWORD *)&v28[v33 + 72];
              *(_QWORD *)&v28[v33 + 88] = v44;
              if ( (*(_BYTE *)(v47 + 3) & 3) == 1 )
              {
                if ( (*(_DWORD *)&v28[v33 + 52] & 1) == 0 )
                  v11[4 * v34 + 12] = *((_WORD *)v44 + 2);
                if ( (v44[3] & 0x80u) != 0 )
                {
                  _mm_lfence();
                  v48 = &v44[*v44];
                  v29 = v48;
                  if ( (unsigned __int64)v48 < v30 && (unsigned __int64)(v48 + 1) < v30 && v48[1] == 49 )
                  {
                    if ( *v48 )
                    {
                      if ( (unsigned __int64)(v48 + 8) <= v30 )
                      {
                        v49 = *(_DWORD *)&v28[v33 + 52];
                        *(_QWORD *)&v28[v33 + 96] = v48;
                        if ( (v49 & 1) == 0 )
                        {
                          v50 = *((_DWORD *)v48 + 1);
                          if ( v50 > 0xFFFF )
                          {
                            v51 = *(_DWORD *)&v11[4 * v34 + 22];
                            if ( (v51 & 0x100) != 0 )
                            {
                              *(_DWORD *)&v11[4 * v34 + 20] = v50;
                              *(_DWORD *)&v11[4 * v34 + 22] = v51 | 0x10000;
                            }
                          }
                          else
                          {
                            v11[4 * v34 + 12] = v50;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        goto LABEL_80;
      }
      v29 = v44;
      v30 = v102;
      v28 = v100;
      if ( *v44 && (unsigned __int64)(v44 + 8) <= v102 )
      {
        *(_QWORD *)&v100[v33 + 104] = v44;
        *(_DWORD *)&v11[4 * v34 + 20] = *((_DWORD *)v44 + 1);
        v46 = *((_WORD *)v44 + 2);
        v11[4 * v34 + 12] = v46;
        if ( v46 )
          _InterlockedAnd((volatile signed __int32 *)&v28[v33 + 52], 0xFFFFFFFE);
        goto LABEL_63;
      }
LABEL_80:
      v31 = (unsigned int)(v98 + 1);
      v98 = v31;
      if ( (unsigned int)v31 >= *((_DWORD *)v11 + 4) )
      {
        v14 = v101;
        goto LABEL_82;
      }
    }
    v38 = 3;
    if ( v39 != 48 )
      v38 = 0;
LABEL_35:
    *(_DWORD *)&v28[v33 + 112] = v38;
    goto LABEL_36;
  }
LABEL_114:
  v5 = (__int64 *)(a1 + 48);
  v56 = *(_QWORD *)(a1 + 48);
  if ( v56 )
  {
    v57 = *(_QWORD *)(v56 + 16);
    v58 = v57 - 8;
    if ( v56 + 16 != v57 )
    {
      while ( 1 )
      {
        v59 = *(_DWORD *)(v58 + 24);
        for ( i = 0; i < v59; ++i )
        {
          if ( (*(_BYTE *)(*(_QWORD *)(v58 + 80LL * i + 72) + 2LL) & 0xF) == 0 )
          {
            v8 = -1073741823;
            *(_DWORD *)(a1 + 1572) = -1072693239;
            goto LABEL_101;
          }
        }
        v61 = *(_QWORD *)(v58 + 8);
        if ( v56 + 16 == v61 )
          break;
        v58 = v61 - 8;
      }
    }
  }
  v97 = 0;
  v62 = 0;
  v96 = 0;
  v63 = 0;
  LOWORD(v98) = 0;
  v64 = 0;
  if ( !v56 )
  {
LABEL_140:
    *((_DWORD *)v106 + 2) = v14;
    v74 = *(_DWORD *)(a1 + 96);
    *(_DWORD *)(a1 + 128) = 0;
    *(_DWORD *)(a1 + 144) = 0;
    *(_DWORD *)(a1 + 112) = 0;
    if ( v74 )
    {
      if ( v14 <= v74 )
        goto LABEL_169;
      v75 = *(void **)(a1 + 104);
      *(_DWORD *)(a1 + 96) = 0;
      if ( v75 )
      {
        ExFreePoolWithTag(v75, 0x64334855u);
        *(_QWORD *)(a1 + 104) = 0;
      }
      v76 = *(void **)(a1 + 136);
      if ( v76 )
      {
        ExFreePoolWithTag(v76, 0x64334855u);
        *(_QWORD *)(a1 + 136) = 0;
      }
      v77 = *(void **)(a1 + 120);
      if ( v77 )
      {
        ExFreePoolWithTag(v77, 0x64334855u);
        *(_QWORD *)(a1 + 120) = 0;
      }
    }
    v8 = 0;
    if ( *(_DWORD *)(a1 + 96) || !v14 )
      goto LABEL_161;
    Pool2 = ExAllocatePool2(64, 8LL * v14, 1681082453);
    *(_QWORD *)(a1 + 104) = Pool2;
    if ( !Pool2
      || (v80 = ExAllocatePool2(64, 8LL * v14, 1681082453), (*(_QWORD *)(a1 + 136) = v80) == 0)
      || (v81 = ExAllocatePool2(64, 8LL * v14, 1681082453), (*(_QWORD *)(a1 + 120) = v81) == 0) )
    {
      v82 = *(void **)(a1 + 104);
      v8 = -1073741670;
      *(_DWORD *)(a1 + 96) = 0;
      if ( v82 )
      {
        ExFreePoolWithTag(v82, 0x64334855u);
        *(_QWORD *)(a1 + 104) = 0;
      }
      v83 = *(void **)(a1 + 136);
      if ( v83 )
      {
        ExFreePoolWithTag(v83, 0x64334855u);
        *(_QWORD *)(a1 + 136) = 0;
      }
      v84 = *(void **)(a1 + 120);
      if ( v84 )
      {
        ExFreePoolWithTag(v84, 0x64334855u);
        *(_QWORD *)(a1 + 120) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v94) = -1073741670;
        LOBYTE(v79) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
          v79,
          5,
          30,
          (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
          v94);
      }
LABEL_161:
      if ( v8 < 0 )
        goto LABEL_101;
      goto LABEL_162;
    }
    *(_DWORD *)(a1 + 96) = v14;
LABEL_169:
    v8 = 0;
LABEL_162:
    v85 = *(_QWORD *)(a1 + 56);
    if ( v85 )
    {
      v86 = (_QWORD *)(v85 + 16);
      *(_DWORD *)(a1 + 144) = 0;
      *(_DWORD *)(a1 + 128) = 0;
      v87 = *v86 - 8LL;
      if ( v86 != (_QWORD *)*v86 )
      {
        do
        {
          for ( j = 0; j < *(_DWORD *)(v87 + 24); ++j )
          {
            v89 = *(_DWORD *)(v87 + 80LL * j + 48);
            if ( v89 == 4 )
            {
              *(_DWORD *)(v87 + 80LL * j + 48) = 5;
              *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL * (unsigned int)(*(_DWORD *)(a1 + 128))++) = *(_QWORD *)(v87 + 80LL * j + 40);
            }
            else if ( v89 == 6 )
            {
              *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL * (unsigned int)(*(_DWORD *)(a1 + 144))++) = *(_QWORD *)(v87 + 80LL * j + 40);
            }
          }
          v90 = *(_QWORD *)(v87 + 8);
          v87 = v90 - 8;
        }
        while ( *(_QWORD *)(a1 + 56) + 16LL != v90 );
      }
    }
    v91 = *v5;
    goto LABEL_174;
  }
  for ( k = *(_QWORD *)(v56 + 16); ; k = *(_QWORD *)(v66 + 8) )
  {
    v66 = k - 8;
    if ( v56 + 16 == k )
    {
      v5 = (__int64 *)(a1 + 48);
      goto LABEL_140;
    }
    v67 = 0;
    v68 = *(_DWORD *)(v66 + 24);
    if ( v68 )
      break;
LABEL_136:
    ;
  }
  while ( (*(_DWORD *)(v66 + 80LL * v67 + 52) & 1) != 0 )
  {
LABEL_135:
    if ( ++v67 >= v68 )
      goto LABEL_136;
  }
  v69 = *(_QWORD *)(v66 + 80LL * v67 + 72);
  v70 = (char *)(v69 + 2);
  if ( (*(_BYTE *)(v69 + 3) & 3) != 0 )
  {
    if ( *v70 >= 0 )
    {
      v71 = (unsigned __int16 *)&v98;
      v62 = v63;
    }
    else
    {
      v71 = &v96;
    }
  }
  else
  {
    v71 = &v97;
    v62 = (unsigned __int16)v64;
  }
  v72 = *v70;
  v73 = *v70 & 0xF;
  LOWORD(v64) = (unsigned __int16)v64 >> v73;
  if ( (v64 & 1) == 0 && (((unsigned __int16)v62 >> v73) & 1) == 0 )
  {
    *v71 = v62 | (1 << (v72 & 0xF));
    v62 = v96;
    v63 = v98;
    v64 = v97;
    goto LABEL_135;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Dq(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL), v62, v64, v56, v93, v72, v56);
LABEL_99:
  v8 = -1073741823;
  *(_DWORD *)(a1 + 1572) = -1073737984;
LABEL_100:
  v5 = (__int64 *)(a1 + 48);
LABEL_101:
  *(_DWORD *)(a1 + 1568) = v8;
  if ( !*(_DWORD *)(a1 + 1572) )
    *(_DWORD *)(a1 + 1572) = HUBPDO_GetUSBDErrorFromNTStatus((unsigned int)v8);
  v52 = (_QWORD *)*v5;
  *v5 = *(_QWORD *)(a1 + 56);
  *(_QWORD *)(a1 + 56) = 0;
  _InterlockedOr((volatile signed __int32 *)(a1 + 1644), 0x10u);
  if ( v52 )
  {
    v53 = (_QWORD **)(v52 + 2);
    while ( 1 )
    {
      v54 = *v53;
      if ( *v53 == v53 )
        break;
      if ( (_QWORD **)v54[1] != v53 )
        goto LABEL_175;
      v55 = (_QWORD *)*v54;
      if ( *(_QWORD **)(*v54 + 8LL) != v54 )
        goto LABEL_175;
      *v53 = v55;
      v55[1] = v53;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, *(v54 - 1));
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, *v52);
  }
  v91 = 0;
LABEL_174:
  *(_QWORD *)(v107 + 32) = v91;
  return ((v8 >> 31) & 0xFFFFFFF4) + 4077;
}

```

## disassembly

```asm
0x140030998  push    rbp
0x14003099a  push    rbx
0x14003099b  push    rsi
0x14003099c  push    rdi
0x14003099d  push    r12
0x14003099f  push    r13
0x1400309a1  push    r14
0x1400309a3  push    r15
0x1400309a5  lea     rbp, [rsp-28h]
0x1400309aa  sub     rsp, 128h
0x1400309b1  mov     rax, cs:__security_cookie
0x1400309b8  xor     rax, rsp
0x1400309bb  mov     [rbp+60h+var_48], rax
0x1400309bf  mov     rdx, [rcx+1D0h]
0x1400309c6  lea     r8, [rbp+60h+var_70]
0x1400309ca  xor     eax, eax
0x1400309cc  xorps   xmm0, xmm0
0x1400309cf  mov     dword ptr [rbp+60h+var_88], eax
0x1400309d2  xor     r15d, r15d
0x1400309d5  mov     [rbp+60h+var_50], rax
0x1400309d9  mov     rdi, rcx
0x1400309dc  mov     [rcx+70h], r15d
0x1400309e0  mov     rcx, cs:WdfDriverGlobals
0x1400309e7  movups  [rbp+60h+var_70], xmm0
0x1400309eb  lea     eax, [r15+28h]
0x1400309ef  mov     [rbp+60h+var_E0], r15
0x1400309f3  mov     word ptr [rbp+60h+var_70], ax
0x1400309f7  mov     rax, cs:WdfFunctions_01015
0x1400309fe  movups  [rbp+60h+var_B8], xmm0
0x140030a02  movups  [rbp+60h+var_A8], xmm0
0x140030a06  movups  [rbp+60h+var_98], xmm0
0x140030a0a  movups  [rbp+60h+var_60], xmm0
0x140030a0e  mov     rax, [rax+850h]
0x140030a15  call    _guard_dispatch_icall
0x140030a1a  mov     r13, qword ptr [rbp+60h+var_70+8]
0x140030a1e  lea     rcx, [rdi+28h]; SpinLock
0x140030a22  mov     [rbp+60h+var_C0], r13
0x140030a26  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030a2d  nop     dword ptr [rax+rax+00h]
0x140030a32  lock and dword ptr [rdi+66Ch], 0FFFFFFEFh
0x140030a3a  lea     r14, [rdi+30h]
0x140030a3e  mov     rdx, [r14]
0x140030a41  mov     [rdi+38h], rdx
0x140030a45  mov     [r14], r15
0x140030a48  lock and dword ptr [rdi+66Ch], 0FFFF7FFFh
0x140030a53  mov     dl, al; NewIrql
0x140030a55  lea     rcx, [rdi+28h]; SpinLock
0x140030a59  call    cs:__imp_KeReleaseSpinLock
0x140030a60  nop     dword ptr [rax+rax+00h]
0x140030a65  xor     eax, eax
0x140030a67  mov     [rsp+160h+var_130], r14
0x140030a6c  mov     [rbp+60h+var_88], rax
0x140030a70  lea     rdx, [rbp+60h+var_E0]
0x140030a74  xorps   xmm0, xmm0
0x140030a77  mov     [rsp+160h+var_138], rdx
0x140030a7c  movups  [rbp+60h+var_A8], xmm0
0x140030a80  lea     eax, [r15+1]
0x140030a84  mov     r9d, 64334855h
0x140030a8a  movups  [rbp+60h+var_B8], xmm0
0x140030a8e  mov     dword ptr [rbp+60h+var_A8+8], eax
0x140030a91  lea     rdx, [rbp+60h+var_B8]
0x140030a95  mov     dword ptr [rbp+60h+var_A8+0Ch], eax
0x140030a98  mov     r8d, 200h
0x140030a9e  movups  [rbp+60h+var_98], xmm0
0x140030aa2  mov     dword ptr [rbp+60h+var_B8], 38h ; '8'
0x140030aa9  mov     rax, [r13+18h]
0x140030aad  movzx   esi, word ptr [rax+2]
0x140030ab1  mov     rax, cs:WdfFunctions_01015
0x140030ab8  lea     rcx, [rsi+27h]
0x140030abc  mov     rax, [rax+600h]
0x140030ac3  mov     [rsp+160h+var_140], rcx
0x140030ac8  mov     rcx, cs:WdfDriverGlobals
0x140030acf  call    _guard_dispatch_icall
0x140030ad4  mov     ebx, eax
0x140030ad6  test    eax, eax
0x140030ad8  jns     short loc_140030B1D
0x140030ada  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140030ae1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140030ae8  jz      loc_1400311C5
0x140030aee  mov     rcx, [rdi+8]
0x140030af2  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140030af9  lea     r9d, [r15+1Fh]
0x140030afd  mov     dword ptr [rsp+160h+var_138], ebx
0x140030b01  lea     r8d, [r15+5]
0x140030b05  mov     [rsp+160h+var_140], rax
0x140030b0a  mov     dl, 2
0x140030b0c  mov     rcx, [rcx+598h]
0x140030b13  call    WPP_RECORDER_SF_d
0x140030b18  jmp     loc_1400311C5
0x140030b1d  mov     r15, [r14]
0x140030b20  mov     r8, rsi; Size
0x140030b23  mov     rax, [rbp+60h+var_E0]
0x140030b27  mov     [rbp+60h+var_C8], r15
0x140030b2b  mov     [r15], rax
0x140030b2e  mov     rcx, [r14]
0x140030b31  mov     rdx, [r13+18h]; Src
0x140030b35  add     rcx, 20h ; ' '; void *
0x140030b39  call    memmove
0x140030b3e  lea     rbx, [r15+10h]
0x140030b42  lea     r10, [r15+20h]
0x140030b46  mov     [rbx+8], rbx
0x140030b4a  xor     r15d, r15d
0x140030b4d  mov     [rbx], rbx
0x140030b50  movzx   ecx, word ptr [r13+0]
0x140030b55  lea     r14, [r13+28h]
0x140030b59  add     rcx, r13
0x140030b5c  mov     [rbp+60h+var_D0], r10
0x140030b60  lea     rax, [r14+2]
0x140030b64  mov     [rbp+60h+var_78], rcx
0x140030b68  mov     [rsp+160h+var_F0], r15d
0x140030b6d  mov     r13d, r15d
0x140030b70  lea     r12d, [r15+5]
0x140030b74  cmp     rax, rcx
0x140030b77  jnb     loc_1400312DF
0x140030b7d  mov     rax, [rdi+8]
0x140030b81  mov     rdx, r10
0x140030b84  mov     [rbp+60h+var_D8], r15
0x140030b88  mov     rcx, r10
0x140030b8b  mov     [rsp+160h+var_100], r15
0x140030b90  movzx   r9d, byte ptr [r14+3]
0x140030b95  mov     rax, [rax+598h]
0x140030b9c  movzx   r8d, byte ptr [r14+2]
0x140030ba1  mov     [rsp+160h+var_120], rax
0x140030ba6  lea     rax, [rsp+160h+var_108]
0x140030bab  mov     [rsp+160h+var_128], rax
0x140030bb0  mov     dword ptr [rsp+160h+var_130], 0FFFFFFFFh
0x140030bb8  mov     dword ptr [rsp+160h+var_138], 0FFFFFFFFh
0x140030bc0  mov     dword ptr [rsp+160h+var_140], 0FFFFFFFFh
0x140030bc8  mov     byte ptr [rsp+160h+var_108], r15b
0x140030bcd  call    HUBDESC_ParseConfigurationDescriptor
0x140030bd2  mov     rsi, rax
0x140030bd5  test    rax, rax
0x140030bd8  jz      loc_140031294
0x140030bde  mov     rcx, [rdi+998h]
0x140030be5  test    rcx, rcx
0x140030be8  jz      short loc_140030C21
0x140030bea  mov     r9d, [rcx]
0x140030bed  test    r9d, r9d
0x140030bf0  jz      short loc_140030C21
0x140030bf2  mov     r10b, [rax+3]
0x140030bf6  mov     edx, r15d
0x140030bf9  mov     r8d, edx
0x140030bfc  cmp     [rcx+r8*2+5], r10b
0x140030c01  jnz     short loc_140030C0D
0x140030c03  mov     al, [rsi+2]
0x140030c06  cmp     [rcx+r8*2+4], al
0x140030c0b  jz      short loc_140030C16
0x140030c0d  inc     edx
0x140030c0f  cmp     edx, r9d
0x140030c12  jb      short loc_140030BF9
0x140030c14  jmp     short loc_140030C21
0x140030c16  lock or dword ptr [rdi+66Ch], 8000h
0x140030c21  movzx   eax, byte ptr [rsi+4]
0x140030c25  lea     rcx, [rsp+160h+var_100]
0x140030c2a  mov     [r14+10h], eax
0x140030c2e  lea     rdx, [rbp+60h+var_B8]
0x140030c32  mov     al, [rsi+4]
0x140030c35  xorps   xmm0, xmm0
0x140030c38  mov     byte ptr [rsp+160h+var_110], al
0x140030c3c  mov     r9d, 64334855h
0x140030c42  movzx   eax, word ptr [r14]
0x140030c46  mov     r8d, 200h
0x140030c4c  mov     [rsp+160h+var_10C], ax
0x140030c51  xor     eax, eax
0x140030c53  mov     [rbp+60h+var_88], rax
0x140030c57  mov     eax, 1
0x140030c5c  movups  [rbp+60h+var_A8], xmm0
0x140030c60  mov     [rsp+160h+var_130], rcx
0x140030c65  lea     rcx, [rbp+60h+var_D8]
0x140030c69  movups  [rbp+60h+var_B8], xmm0
0x140030c6d  mov     dword ptr [rbp+60h+var_A8+8], eax
0x140030c70  mov     dword ptr [rbp+60h+var_A8+0Ch], eax
0x140030c73  movups  [rbp+60h+var_98], xmm0
0x140030c77  mov     dword ptr [rbp+60h+var_B8], 38h ; '8'
0x140030c7e  mov     eax, [r14+10h]
0x140030c82  mov     [rsp+160h+var_138], rcx
0x140030c87  mov     rcx, cs:WdfDriverGlobals
0x140030c8e  lea     r15, [rax+rax*4]
0x140030c92  mov     rax, cs:WdfFunctions_01015
0x140030c99  shl     r15, 4
0x140030c9d  add     r15, 28h ; '('
0x140030ca1  mov     [rsp+160h+var_140], r15
0x140030ca6  mov     rax, [rax+600h]
0x140030cad  call    _guard_dispatch_icall
0x140030cb2  mov     ebx, eax
0x140030cb4  test    eax, eax
0x140030cb6  js      loc_14003124E
0x140030cbc  mov     rax, [rsp+160h+var_100]
0x140030cc1  mov     r8, r15; Size
0x140030cc4  mov     [r14+8], rax
0x140030cc8  xor     edx, edx; Val
0x140030cca  mov     rcx, [rsp+160h+var_100]; void *
0x140030ccf  call    memset
0x140030cd4  mov     rax, [rsp+160h+var_100]
0x140030cd9  mov     rcx, [rbp+60h+var_D8]
0x140030cdd  mov     [rax], rcx
0x140030ce0  mov     rax, [rsp+160h+var_100]
0x140030ce5  mov     [rax+20h], rsi
0x140030ce9  movzx   ecx, byte ptr [rsi+4]
0x140030ced  mov     rax, [rsp+160h+var_100]
0x140030cf2  mov     [rax+18h], ecx
0x140030cf5  mov     ecx, 1
0x140030cfa  cmp     byte ptr [rsp+160h+var_108], cl
0x140030cfe  jnz     short loc_140030D13
0x140030d00  mov     rax, [rsp+160h+var_100]
0x140030d05  lock or [rax+1Ch], ecx
0x140030d09  mov     rax, [rsp+160h+var_100]
0x140030d0e  lock or dword ptr [rax+1Ch], 2
0x140030d13  mov     rbx, [rbp+60h+var_C8]
0x140030d17  add     rbx, 10h
0x140030d1b  mov     rcx, [rbx+8]
0x140030d1f  cmp     [rcx], rbx
0x140030d22  jnz     loc_140031723
0x140030d28  mov     rax, [rsp+160h+var_100]
0x140030d2d  xor     r15d, r15d
0x140030d30  mov     [rax+10h], rcx
0x140030d34  add     rax, 8
0x140030d38  mov     [rax], rbx
0x140030d3b  mov     [rcx], rax
0x140030d3e  mov     [rbx+8], rax
0x140030d42  mov     al, [rsi+5]
0x140030d45  mov     [r14+4], al
0x140030d49  mov     al, [rsi+6]
0x140030d4c  mov     [r14+5], al
0x140030d50  mov     al, [rsi+7]
0x140030d53  mov     [r14+6], al
0x140030d57  mov     rax, [rbp+60h+var_C0]
0x140030d5b  movzx   edx, byte ptr [rsi]
0x140030d5e  mov     r10, [rsp+160h+var_100]
0x140030d63  add     rdx, rsi
0x140030d66  mov     [rsp+160h+var_F8], r10
0x140030d6b  mov     rax, [rax+18h]
0x140030d6f  movzx   r9d, word ptr [rax+2]
0x140030d74  add     r9, [rbp+60h+var_D0]
0x140030d78  mov     eax, r15d
0x140030d7b  mov     [rsp+160h+var_E8], r9
0x140030d80  mov     [rsp+160h+var_108], eax
0x140030d84  cmp     [r14+10h], r15d
0x140030d88  jbe     loc_1400310AD
0x140030d8e  mov     rcx, rdx
0x140030d91  cmp     rdx, r9
0x140030d94  jnb     loc_140031178
0x140030d9a  lea     r15, [rax+rax*4]
0x140030d9e  shl     r15, 4
0x140030da2  lea     r13, [rax+rax*2]
0x140030da6  mov     eax, [r14+r13*8+2Ch]
0x140030dab  mov     [r15+r10+40h], eax
0x140030db0  lea     rax, [rdx+1]
0x140030db4  mov     dword ptr [r15+r10+30h], 1
0x140030dbd  cmp     rax, r9
0x140030dc0  jnb     loc_140031160
0x140030dc6  xor     r11d, r11d
0x140030dc9  cmp     [rax], r12b
0x140030dcc  jz      short loc_140030E10
0x140030dce  movzx   eax, byte ptr [rcx]
0x140030dd1  test    al, al
0x140030dd3  jz      loc_1400310F8
0x140030dd9  add     rdx, rax
0x140030ddc  mov     rcx, rdx
0x140030ddf  cmp     rdx, r9
0x140030de2  jnb     loc_1400310D9
0x140030de8  lea     rax, [rdx+1]
0x140030dec  cmp     rax, r9
0x140030def  jb      short loc_140030DC9
0x140030df1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140030df8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140030dff  jz      loc_1400311AF
0x140030e05  mov     r9d, 1Ah
0x140030e0b  jmp     loc_14003118E
0x140030e10  cmp     rdx, r9
0x140030e13  jnb     loc_140031148
0x140030e19  lea     rax, [rdx+7]
0x140030e1d  cmp     rax, r9
0x140030e20  ja      loc_140031130
0x140030e26  mov     eax, [r14+r13*8+2Ch]
0x140030e2b  mov     ecx, 1
0x140030e30  test    cl, al
0x140030e32  jz      short loc_140030E3E
0x140030e34  movzx   eax, word ptr [r14+r13*8+18h]
0x140030e3a  mov     [rdx+4], ax
0x140030e3e  mov     r8d, [r14+r13*8+2Ch]
0x140030e43  mov     ebx, 3
0x140030e48  and     r8d, 0F0h
0x140030e4f  cmp     r8d, 10h
0x140030e53  jz      short loc_140030E65
0x140030e55  cmp     r8d, 20h ; ' '
0x140030e59  jz      short loc_140030EAF
0x140030e5b  cmp     r8d, 30h ; '0'
0x140030e5f  mov     ecx, ebx
0x140030e61  cmovnz  ecx, r11d
0x140030e65  mov     [r15+r10+70h], ecx
0x140030e6a  mov     eax, r9d
0x140030e6d  mov     [r15+r10+48h], rdx
0x140030e72  sub     eax, edx
0x140030e74  mov     [r15+r10+50h], eax
0x140030e79  mov     eax, 250h
0x140030e7e  cmp     [rdi+7CEh], ax
0x140030e85  jnb     short loc_140030EBA
0x140030e87  movzx   eax, word ptr [rdx+4]
0x140030e8b  mov     r8d, 7FFh
  ... truncated ...
```
