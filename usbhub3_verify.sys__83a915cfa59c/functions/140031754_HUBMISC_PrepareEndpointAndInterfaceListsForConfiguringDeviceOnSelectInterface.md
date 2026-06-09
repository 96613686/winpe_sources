# HUBMISC_PrepareEndpointAndInterfaceListsForConfiguringDeviceOnSelectInterface

- ea: `0x140031754`
- end: `0x14003258b`
- name: `HUBMISC_PrepareEndpointAndInterfaceListsForConfiguringDeviceOnSelectInterface`
- size: `3639`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140022dc0`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000c578`
- `0x14001892c`
- `0x140031754`
- `0x1400337f8`
- `0x1400339f8`
- `0x14003bd60`
- `0x140045530`
- `0x140045570`
- `0x140045940`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003185e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003185e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031844`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031844`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400321a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400321c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400321eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400322a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400322cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400322f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400321a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400321c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400321eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400322a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400322cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400322f1`
- `ntoskrnl!ExAllocatePool2` at `0x14003222b`
- `ntoskrnl!ExAllocatePool2` at `0x14003224f`
- `ntoskrnl!ExAllocatePool2` at `0x140032276`
- `ntoskrnl!ExAllocatePool2` at `0x14003222b`
- `ntoskrnl!ExAllocatePool2` at `0x14003224f`
- `ntoskrnl!ExAllocatePool2` at `0x140032276`

## pseudocode

```c
__int64 __fastcall HUBMISC_PrepareEndpointAndInterfaceListsForConfiguringDeviceOnSelectInterface(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rdx
  __int64 v3; // rcx
  _DWORD *v4; // rdx
  __int64 v5; // r14
  __int64 v6; // rax
  KIRQL v7; // al
  int v8; // r9d
  int v9; // r8d
  unsigned __int8 *v10; // rax
  int v11; // edx
  unsigned __int8 *v12; // rsi
  void **v13; // r12
  int v14; // ebx
  _DWORD *v15; // rcx
  unsigned int v16; // edx
  __int16 v17; // cx
  size_t v18; // r15
  int v19; // edx
  unsigned int v20; // r10d
  char *v21; // r13
  unsigned __int8 *v22; // rdx
  __int64 v23; // rsi
  unsigned __int64 v24; // r9
  __int64 v25; // rax
  unsigned __int8 *v26; // rcx
  __int64 v27; // rsi
  __int64 v28; // r15
  _BYTE *v29; // rax
  int v30; // r9d
  __int64 v31; // rax
  int v32; // r8d
  int v33; // ecx
  __int16 v34; // r8
  char v35; // cl
  __int64 v36; // rcx
  __int64 v37; // rax
  unsigned __int8 *v38; // rbx
  _BYTE *v39; // r12
  int IsEnabledDeviceUsageNoInline; // eax
  __int16 v41; // ax
  __int64 v42; // rax
  unsigned __int8 *v43; // rcx
  int v44; // eax
  unsigned int v45; // r8d
  int v46; // eax
  unsigned int v47; // edx
  unsigned int v48; // r9d
  unsigned int v49; // r11d
  unsigned int *v50; // rdx
  unsigned int v51; // r8d
  _QWORD *v52; // r15
  __int64 v53; // rax
  _QWORD *v54; // r13
  char v55; // r12
  _QWORD *v56; // rbx
  __int64 v57; // r9
  char v58; // r11
  __int16 v60; // ax
  unsigned int v61; // r8d
  _QWORD *v62; // rsi
  int v63; // eax
  unsigned int v64; // ecx
  unsigned int v65; // edx
  __int64 v66; // r12
  char v67; // r10
  __int64 v68; // rax
  _QWORD *v69; // rax
  unsigned int v70; // esi
  unsigned int v71; // eax
  void *v72; // rcx
  void *v73; // rcx
  void *v74; // rcx
  __int64 Pool2; // rax
  int v76; // edx
  __int64 v77; // rax
  __int64 v78; // rax
  void *v79; // rcx
  void *v80; // rcx
  void *v81; // rcx
  __int64 v82; // rdx
  _QWORD *v83; // rcx
  unsigned int v84; // r8d
  int v85; // ecx
  __int64 v86; // rcx
  _QWORD *i; // rax
  unsigned int j; // r9d
  __int64 v89; // rax
  _QWORD *v90; // r8
  _QWORD *v91; // rdx
  _QWORD *v92; // rax
  int v93; // [rsp+20h] [rbp-E0h]
  char v94[8]; // [rsp+70h] [rbp-90h] BYREF
  void *v95; // [rsp+78h] [rbp-88h]
  unsigned int v96; // [rsp+80h] [rbp-80h]
  unsigned __int64 v97; // [rsp+88h] [rbp-78h]
  void **v98; // [rsp+90h] [rbp-70h]
  __int64 v99; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v100; // [rsp+A0h] [rbp-60h]
  __int64 v101; // [rsp+A8h] [rbp-58h]
  __int64 v102; // [rsp+B0h] [rbp-50h]
  __int128 v103; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v104; // [rsp+C8h] [rbp-38h]
  __int128 v105; // [rsp+D8h] [rbp-28h]
  __int64 v106; // [rsp+E8h] [rbp-18h]
  __int128 v107; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v108; // [rsp+100h] [rbp+0h]
  __int64 v109; // [rsp+110h] [rbp+10h]

  v102 = a1;
  v1 = a1;
  v109 = 0;
  v101 = 0;
  v94[0] = 0;
  v95 = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_DWORD *)(a1 + 112) = 0;
  v107 = 0;
  LODWORD(v106) = 0;
  v108 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  _InterlockedAnd((volatile signed __int32 *)(a1 + 1644), 0xFFFF7FFF);
  v2 = *(_QWORD *)(a1 + 464);
  v109 = 0;
  v107 = 0;
  LOWORD(v107) = 40;
  v108 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    v2,
    &v107);
  v3 = *((_QWORD *)&v107 + 1);
  v4 = (_DWORD *)(*((_QWORD *)&v107 + 1) + 32LL);
  if ( *(_WORD *)(*((_QWORD *)&v107 + 1) + 2LL) == 1 )
  {
    v5 = *((_QWORD *)&v107 + 1) + 32LL;
    *(_DWORD *)(v1 + 148) = 0;
    v6 = 0;
  }
  else
  {
    v5 = *((_QWORD *)&v107 + 1) + 48LL;
    *(_DWORD *)(v1 + 148) = *v4;
    v6 = 0;
    if ( *v4 )
      v6 = *(_QWORD *)(v3 + 40);
  }
  *(_QWORD *)(v1 + 152) = v6;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 40));
  _InterlockedAnd((volatile signed __int32 *)(v1 + 1644), 0xFFFFFFEF);
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 40), v7);
  v8 = *(unsigned __int8 *)(v5 + 3);
  v9 = *(unsigned __int8 *)(v5 + 2);
  v99 = *(_QWORD *)(v1 + 48);
  v10 = (unsigned __int8 *)HUBDESC_ParseConfigurationDescriptor(
                             (int)v99 + 32,
                             (int)v99 + 32,
                             v9,
                             v8,
                             -1,
                             -1,
                             -1,
                             (__int64)v94,
                             *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL));
  v12 = v10;
  if ( !v10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
        v11,
        5,
        34,
        (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
    }
    *(_DWORD *)(v1 + 1572) = -1073725440;
    v13 = (void **)(v5 + 8);
    v14 = -1073741823;
    goto LABEL_117;
  }
  v15 = *(_DWORD **)(v1 + 2456);
  if ( v15 && *v15 )
  {
    v16 = 0;
    while ( *((_BYTE *)v15 + 2 * v16 + 5) != v10[3] || *((_BYTE *)v15 + 2 * v16 + 4) != v10[2] )
    {
      if ( ++v16 >= *v15 )
        goto LABEL_17;
    }
    _InterlockedOr((volatile signed __int32 *)(v1 + 1644), 0x8000u);
  }
LABEL_17:
  v13 = (void **)(v5 + 8);
  v17 = v10[4] + 1;
  *(_DWORD *)(v5 + 4) = 0;
  *(_QWORD *)(v5 + 8) = 0;
  *(_WORD *)v5 = 24 * v17;
  *(_DWORD *)(v5 + 16) = v10[4];
  *(_QWORD *)&v104 = 0;
  *((_QWORD *)&v104 + 1) = 0x100000001LL;
  v103 = 0;
  v106 = 0;
  v105 = 0;
  LODWORD(v103) = 56;
  v18 = 80LL * *(unsigned int *)(v5 + 16) + 40;
  v93 = 80 * *(_DWORD *)(v5 + 16) + 40;
  v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64))(WdfFunctions_01015 + 1536))(
          WdfDriverGlobals,
          &v103,
          512,
          1681082453);
  if ( v14 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
        v19,
        5,
        35,
        (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
        v14);
    }
    goto LABEL_117;
  }
  v98 = (void **)(v5 + 8);
  memset(v95, 0, v18);
  v20 = 0;
  *(_QWORD *)v95 = v101;
  *((_QWORD *)v95 + 4) = v12;
  *((_DWORD *)v95 + 6) = v12[4];
  *(_QWORD *)(v1 + 64) = 0;
  if ( v94[0] == 1 )
  {
    _InterlockedOr((volatile signed __int32 *)v95 + 7, 1u);
    _InterlockedOr((volatile signed __int32 *)v95 + 7, 2u);
    *(_QWORD *)(v1 + 64) = v95;
  }
  *(_BYTE *)(v5 + 4) = v12[5];
  *(_BYTE *)(v5 + 5) = v12[6];
  *(_BYTE *)(v5 + 6) = v12[7];
  v21 = (char *)v95;
  v22 = &v12[*v12];
  v23 = v99;
  v24 = *(unsigned __int16 *)(v99 + 34) + v99 + 32;
  v25 = 0;
  v96 = 0;
  v97 = v24;
  if ( *(_DWORD *)(v5 + 16) )
  {
    while ( 2 )
    {
      v26 = v22;
      if ( (unsigned __int64)v22 >= v24 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v30 = 22;
          break;
        }
        goto LABEL_116;
      }
      v27 = 80 * v25;
      v28 = 3 * v25;
      *(_DWORD *)&v21[v27 + 64] = *(_DWORD *)(v5 + 24 * v25 + 44);
      v29 = v22 + 1;
      *(_DWORD *)&v21[v27 + 48] = 1;
      if ( (unsigned __int64)(v22 + 1) >= v24 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v30 = 23;
          break;
        }
        goto LABEL_116;
      }
      while ( *v29 != 5 )
      {
        v31 = *v26;
        if ( !(_BYTE)v31 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_116;
          v30 = 24;
          goto LABEL_115;
        }
        v22 += v31;
        v26 = v22;
        if ( (unsigned __int64)v22 >= v24 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_116;
          v30 = 25;
          goto LABEL_115;
        }
        v29 = v22 + 1;
        if ( (unsigned __int64)(v22 + 1) >= v24 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_116;
          v30 = 26;
          goto LABEL_115;
        }
      }
      if ( (unsigned __int64)v22 >= v24 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_116;
        v30 = 27;
      }
      else if ( (unsigned __int64)(v22 + 7) > v24 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_116;
        v30 = 28;
      }
      else
      {
        if ( (*(_DWORD *)(v5 + 8 * v28 + 44) & 1) != 0 )
          *((_WORD *)v22 + 2) = *(_WORD *)(v5 + 8 * v28 + 24);
        v32 = *(_DWORD *)(v5 + 8 * v28 + 44) & 0xF0;
        if ( v32 == 16 )
        {
          *(_DWORD *)&v21[v27 + 112] = 1;
        }
        else if ( v32 == 32 )
        {
          *(_DWORD *)&v21[v27 + 112] = 2;
        }
        else
        {
          v33 = 3;
          if ( v32 != 48 )
            v33 = 0;
          *(_DWORD *)&v21[v27 + 112] = v33;
        }
        *(_QWORD *)&v21[v27 + 72] = v22;
        *(_DWORD *)&v21[v27 + 80] = v24 - (_DWORD)v22;
        if ( *(_WORD *)(v1 + 1998) >= 0x250u )
          v34 = *((_WORD *)v22 + 2);
        else
          v34 = (*((_WORD *)v22 + 2) & 0x7FF) * (((*((_WORD *)v22 + 2) >> 11) & 3) + 1);
        *(_WORD *)(v5 + 8 * v28 + 24) = v34;
        v35 = 6;
        if ( v22[6] < 6u )
          v35 = v22[6];
        *(_BYTE *)(v5 + 8 * v28 + 27) = v35;
        *(_BYTE *)(v5 + 8 * v28 + 26) = v22[2];
        v36 = v22[3] & 3;
        if ( (v22[3] & 3) != 0 )
        {
          v36 = (unsigned int)(v36 - 1);
          if ( (_DWORD)v36 )
          {
            v36 = (unsigned int)(v36 - 1);
            if ( (_DWORD)v36 )
            {
              if ( (_DWORD)v36 == 1 )
                *(_DWORD *)(v5 + 8 * v28 + 28) = 3;
            }
            else
            {
              *(_DWORD *)(v5 + 8 * v28 + 28) = 2;
            }
          }
          else
          {
            *(_DWORD *)(v5 + 8 * v28 + 28) = 1;
          }
        }
        else
        {
          *(_DWORD *)(v5 + 8 * v28 + 28) = 0;
        }
        if ( !v34 )
          _InterlockedOr((volatile signed __int32 *)&v21[v27 + 52], 1u);
        v37 = *v22;
        if ( (_BYTE)v37 )
        {
          v38 = &v22[v37];
          v100 = v38;
          v22 += v37;
          if ( (unsigned __int64)v38 < v24 )
          {
            v39 = v38 + 1;
            if ( (unsigned __int64)(v38 + 1) < v24 )
            {
              IsEnabledDeviceUsageNoInline = Feature_EUSB2__private_IsEnabledDeviceUsageNoInline(v36, v22);
              v20 = 0;
              if ( !IsEnabledDeviceUsageNoInline
                || (unsigned __int16)(*(_WORD *)(v1 + 1998) - 544) > 0xDFu
                || *v39 != 18 )
              {
                v24 = v97;
LABEL_68:
                v22 = v38;
                if ( *v39 == 48 )
                {
                  if ( *v38 )
                  {
                    if ( (unsigned __int64)(v38 + 6) <= v24 )
                    {
                      v42 = *(_QWORD *)&v21[v27 + 72];
                      *(_QWORD *)&v21[v27 + 88] = v38;
                      if ( (*(_BYTE *)(v42 + 3) & 3) == 1 )
                      {
                        if ( (*(_DWORD *)&v21[v27 + 52] & 1) == 0 )
                          *(_WORD *)(v5 + 8 * v28 + 24) = *((_WORD *)v38 + 2);
                        if ( (v38[3] & 0x80u) != 0 )
                        {
                          _mm_lfence();
                          v43 = &v38[*v38];
                          v100 = v43;
                          v22 = v43;
                          if ( (unsigned __int64)v43 < v24 && (unsigned __int64)(v43 + 1) < v24 && v43[1] == 49 )
                          {
                            if ( *v43 )
                            {
                              if ( (unsigned __int64)(v43 + 8) <= v24 )
                              {
                                v44 = *(_DWORD *)&v21[v27 + 52];
                                *(_QWORD *)&v21[v27 + 96] = v43;
                                if ( (v44 & 1) == 0 )
                                {
                                  v45 = *((_DWORD *)v43 + 1);
                                  if ( v45 > 0xFFFF )
                                  {
                                    v46 = *(_DWORD *)(v5 + 8 * v28 + 44);
                                    if ( (v46 & 0x100) != 0 )
                                    {
                                      *(_DWORD *)(v5 + 8 * v28 + 40) = v45;
                                      *(_DWORD *)(v5 + 8 * v28 + 44) = v46 | 0x10000;
                                    }
                                  }
                                  else
                                  {
                                    *(_WORD *)(v5 + 8 * v28 + 24) = v45;
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
                goto LABEL_85;
              }
              v22 = v38;
              v24 = v97;
              if ( *v38 && (unsigned __int64)(v38 + 8) <= v97 )
              {
                *(_QWORD *)&v21[v27 + 104] = v38;
                *(_DWORD *)(v5 + 8 * v28 + 40) = *((_DWORD *)v38 + 1);
                v41 = *((_WORD *)v38 + 2);
                *(_WORD *)(v5 + 8 * v28 + 24) = v41;
                if ( v41 )
                  _InterlockedAnd((volatile signed __int32 *)&v21[v27 + 52], 0xFFFFFFFE);
                goto LABEL_68;
              }
            }
          }
LABEL_85:
          v25 = v96 + 1;
          v96 = v25;
          if ( (unsigned int)v25 < *(_DWORD *)(v5 + 16) )
            continue;
          v13 = v98;
          v23 = v99;
          goto LABEL_94;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_116;
        v30 = 29;
      }
      break;
    }
LABEL_115:
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
      (_DWORD)v22,
      5,
      v30,
      (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
LABEL_116:
    v13 = v98;
    v14 = -1073741823;
    *(_DWORD *)(v1 + 1572) = -1073725440;
    goto LABEL_117;
  }
LABEL_94:
  v47 = 0;
  v48 = *((_DWORD *)v95 + 6);
  if ( v48 )
  {
    while ( (*(_BYTE *)(*((_QWORD *)v95 + 10 * v47 + 9) + 2LL) & 0xF) != 0 )
    {
      if ( ++v47 >= v48 )
        goto LABEL_97;
    }
    v14 = -1073741823;
    *(_DWORD *)(v1 + 1572) = -1072693239;
  }
  else
  {
LABEL_97:
    v49 = *(_DWORD *)(v1 + 148);
    if ( v49 )
    {
      v50 = *(unsigned int **)(v1 + 152);
      do
      {
        v51 = 0;
        if ( v48 )
        {
          while ( *(unsigned __int8 *)(*((_QWORD *)v95 + 10 * v51 + 9) + 2LL) != *((_WORD *)v50 + 2) )
          {
            if ( ++v51 >= v48 )
              goto LABEL_102;
          }
        }
        else
        {
LABEL_102:
          if ( v51 == v48 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v60 = *((_WORD *)v50 + 2);
              LOBYTE(v50) = 2;
              WPP_RECORDER_SF_d(
                *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
                (_DWORD)v50,
                5,
                36,
                (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
                v60);
            }
            v14 = -1073741823;
            *(_DWORD *)(v1 + 1572) = -1072693239;
            goto LABEL_117;
          }
        }
        ++v20;
        v50 = (unsigned int *)((char *)v50 + *v50);
      }
      while ( v20 < v49 );
    }
    v52 = (_QWORD *)(v23 + 16);
    *(_QWORD *)(v1 + 72) = 0;
    v53 = *(_QWORD *)(v23 + 16);
    v54 = 0;
    v94[0] = 0;
    v55 = 0;
    v56 = (_QWORD *)(v53 - 8);
    if ( v23 + 16 == v53 )
      goto LABEL_139;
    do
    {
      v57 = v56[4];
      v58 = *(_BYTE *)(v57 + 2);
      if ( v58 == *(_BYTE *)(v5 + 2) )
      {
        v55 = 1;
        v54 = v56;
        v94[0] = 1;
        goto LABEL_137;
      }
      v61 = 0;
      v62 = v95;
      v96 = *((_DWORD *)v56 + 6);
      if ( !v96 )
        goto LABEL_136;
      v63 = *((_DWORD *)v95 + 6);
      v64 = v96;
      LODWORD(v97) = v63;
      do
      {
        if ( !v63 )
          goto LABEL_135;
        v65 = 0;
        v66 = 10LL * v61;
        v100 = (unsigned __int8 *)v56[10 * v61 + 9];
        v67 = v100[2];
        do
        {
          v68 = *((_QWORD *)v95 + 10 * v65 + 9);
          if ( v67 == *(_BYTE *)(v68 + 2) )
          {
            v1 = v102;
            if ( *((_WORD *)v100 + 2) )
            {
              if ( *(_WORD *)(v68 + 4) )
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_Ddddd(
                    *(_QWORD *)(*(_QWORD *)(v102 + 8) + 1432LL),
                    *(unsigned __int8 *)(*((_QWORD *)v95 + 4) + 3LL),
                    *(unsigned __int8 *)(*((_QWORD *)v95 + 4) + 2LL),
                    v57,
                    v93,
                    v67,
                    v58,
                    *(_BYTE *)(v57 + 3),
                    *(_BYTE *)(*((_QWORD *)v95 + 4) + 2LL),
                    *(_BYTE *)(*((_QWORD *)v95 + 4) + 3LL));
                if ( (byte_14006ED43 & 0x10) != 0 )
                {
                  v86 = v62[4];
                  McTemplateK0phhhquuuuu_EtwWriteTransfer(
                    v86,
                    v56[4],
                    v1 + 1524,
                    *(_QWORD *)(v1 + 24),
                    *(_WORD *)(v1 + 2004),
                    *(_WORD *)(v1 + 2006),
                    *(_WORD *)(v1 + 2008),
                    *(_DWORD *)(v1 + 172),
                    *(_BYTE *)(v56[v66 + 9] + 2LL),
                    *(_BYTE *)(v56[4] + 2LL),
                    *(_BYTE *)(v56[4] + 3LL),
                    *(_BYTE *)(v86 + 2),
                    *(_BYTE *)(v86 + 3));
                }
                v13 = v98;
                v14 = -1073741811;
                goto LABEL_117;
              }
            }
          }
          v63 = v97;
          ++v65;
        }
        while ( v65 < (unsigned int)v97 );
        v64 = v96;
LABEL_135:
        ++v61;
      }
      while ( v61 < v64 );
LABEL_136:
      v55 = v94[0];
LABEL_137:
      v69 = (_QWORD *)v56[1];
      v56 = v69 - 1;
    }
    while ( v52 != v69 );
    v23 = v99;
LABEL_139:
    v70 = *((_DWORD *)v95 + 6) + *(_DWORD *)(v23 + 8);
    v71 = *(_DWORD *)(v1 + 96);
    *(_DWORD *)(v1 + 128) = 0;
    *(_DWORD *)(v1 + 144) = 0;
    *(_DWORD *)(v1 + 112) = 0;
    if ( v71 )
    {
      if ( v70 > v71 )
      {
        v72 = *(void **)(v1 + 104);
        *(_DWORD *)(v1 + 96) = 0;
        if ( v72 )
        {
          ExFreePoolWithTag(v72, 0x64334855u);
          *(_QWORD *)(v1 + 104) = 0;
        }
        v73 = *(void **)(v1 + 136);
        if ( v73 )
        {
          ExFreePoolWithTag(v73, 0x64334855u);
          *(_QWORD *)(v1 + 136) = 0;
        }
        v74 = *(void **)(v1 + 120);
        if ( v74 )
        {
          ExFreePoolWithTag(v74, 0x64334855u);
          *(_QWORD *)(v1 + 120) = 0;
        }
        goto LABEL_147;
      }
LABEL_176:
      v14 = 0;
      goto LABEL_161;
    }
LABEL_147:
    v14 = 0;
    if ( !*(_DWORD *)(v1 + 96) && v70 )
    {
      Pool2 = ExAllocatePool2(64, 8LL * v70, 1681082453);
      *(_QWORD *)(v1 + 104) = Pool2;
      if ( Pool2 )
      {
        v77 = ExAllocatePool2(64, 8LL * v70, 1681082453);
        *(_QWORD *)(v1 + 136) = v77;
        if ( v77 )
        {
          v78 = ExAllocatePool2(64, 8LL * v70, 1681082453);
          *(_QWORD *)(v1 + 120) = v78;
          if ( v78 )
          {
            *(_DWORD *)(v1 + 96) = v70;
            goto LABEL_176;
          }
        }
      }
      v79 = *(void **)(v1 + 104);
      v14 = -1073741670;
      *(_DWORD *)(v1 + 96) = 0;
      if ( v79 )
      {
        ExFreePoolWithTag(v79, 0x64334855u);
        *(_QWORD *)(v1 + 104) = 0;
      }
      v80 = *(void **)(v1 + 136);
      if ( v80 )
      {
        ExFreePoolWithTag(v80, 0x64334855u);
        *(_QWORD *)(v1 + 136) = 0;
      }
      v81 = *(void **)(v1 + 120);
      if ( v81 )
      {
        ExFreePoolWithTag(v81, 0x64334855u);
        *(_QWORD *)(v1 + 120) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v76) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
          v76,
          5,
          30,
          (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
          154);
      }
    }
    if ( v14 >= 0 )
    {
LABEL_161:
      if ( v55 )
        v70 -= *((_DWORD *)v54 + 6);
      *(_DWORD *)(v1 + 144) = 0;
      *(_DWORD *)(v1 + 128) = 0;
      if ( v55 )
      {
        v82 = v54[1];
        if ( *(_QWORD **)(v82 + 8) == v54 + 1 )
        {
          v83 = (_QWORD *)v54[2];
          if ( (_QWORD *)*v83 == v54 + 1 )
          {
            *v83 = v82;
            v84 = 0;
            *(_QWORD *)(v82 + 8) = v83;
            for ( *(_QWORD *)(v1 + 72) = v54; v84 < *((_DWORD *)v54 + 6); ++v84 )
            {
              v85 = v54[10 * v84 + 6];
              if ( v85 == 4 )
              {
                LODWORD(v54[10 * v84 + 6]) = 5;
                *(_QWORD *)(*(_QWORD *)(v1 + 120) + 8LL * (unsigned int)(*(_DWORD *)(v1 + 128))++) = v54[10 * v84 + 5];
              }
              else if ( v85 == 6 )
              {
                *(_QWORD *)(*(_QWORD *)(v1 + 136) + 8LL * (unsigned int)(*(_DWORD *)(v1 + 144))++) = v54[10 * v84 + 5];
              }
            }
            goto LABEL_179;
          }
        }
LABEL_185:
        __fastfail(3u);
      }
LABEL_179:
      for ( i = (_QWORD *)*v52; ; i = (_QWORD *)v90[1] )
      {
        v90 = i - 1;
        if ( v52 == i )
          break;
        for ( j = 0; j < *((_DWORD *)v90 + 6); ++*(_DWORD *)(v1 + 144) )
        {
          v89 = j++;
          *(_QWORD *)(*(_QWORD *)(v1 + 136) + 8LL * *(unsigned int *)(v1 + 144)) = v90[10 * v89 + 5];
        }
      }
      v91 = (_QWORD *)v52[1];
      if ( (_QWORD *)*v91 != v52 )
        goto LABEL_185;
      v92 = (char *)v95 + 8;
      *((_QWORD *)v95 + 2) = v91;
      *v92 = v52;
      *v91 = v92;
      v52[1] = v92;
      *(_QWORD *)(v1 + 80) = v95;
      *(_DWORD *)(v99 + 8) = v70;
    }
    v13 = v98;
    if ( v14 >= 0 )
    {
      *v98 = v95;
      return ((v14 >> 31) & 0xFFFFFFF4) + 4077;
    }
  }
LABEL_117:
  *(_DWORD *)(v1 + 148) = 0;
  *(_QWORD *)(v1 + 152) = 0;
  *v13 = (void *)-1LL;
  if ( v95 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, *(_QWORD *)v95);
    *(_QWORD *)(v1 + 64) = 0;
  }
  *(_DWORD *)(v1 + 1568) = v14;
  if ( !*(_DWORD *)(v1 + 1572) )
    *(_DWORD *)(v1 + 1572) = HUBPDO_GetUSBDErrorFromNTStatus((unsigned int)v14);
  return ((v14 >> 31) & 0xFFFFFFF4) + 4077;
}

```

## disassembly

```asm
0x140031754  push    rbp
0x140031756  push    rbx
0x140031757  push    rsi
0x140031758  push    rdi
0x140031759  push    r12
0x14003175b  push    r13
0x14003175d  push    r14
0x14003175f  push    r15
0x140031761  lea     rbp, [rsp-28h]
0x140031766  sub     rsp, 128h
0x14003176d  mov     rax, cs:__security_cookie
0x140031774  xor     rax, rsp
0x140031777  mov     [rbp+60h+var_48], rax
0x14003177b  xorps   xmm0, xmm0
0x14003177e  mov     [rbp+60h+var_B0], rcx
0x140031782  xor     eax, eax
0x140031784  mov     rdi, rcx
0x140031787  xor     r13d, r13d
0x14003178a  mov     [rbp+60h+var_50], rax
0x14003178e  mov     [rbp+60h+var_B8], r13
0x140031792  mov     [rsp+160h+var_F0], r13b
0x140031797  mov     [rsp+160h+var_E8], r13
0x14003179c  mov     [rcx+50h], r13
0x1400317a0  mov     [rcx+70h], r13d
0x1400317a4  movups  [rbp+60h+var_70], xmm0
0x1400317a8  mov     dword ptr [rbp+60h+var_78], eax
0x1400317ab  movups  [rbp+60h+var_60], xmm0
0x1400317af  movups  [rbp+60h+var_A8], xmm0
0x1400317b3  movups  [rbp+60h+var_98], xmm0
0x1400317b7  movups  [rbp+60h+var_88], xmm0
0x1400317bb  lock and dword ptr [rcx+66Ch], 0FFFF7FFFh
0x1400317c6  mov     rdx, [rcx+1D0h]
0x1400317cd  lea     r8, [rbp+60h+var_70]
0x1400317d1  mov     rcx, cs:WdfDriverGlobals
0x1400317d8  mov     [rbp+60h+var_50], rax
0x1400317dc  lea     eax, [r13+28h]
0x1400317e0  movups  [rbp+60h+var_70], xmm0
0x1400317e4  mov     word ptr [rbp+60h+var_70], ax
0x1400317e8  mov     rax, cs:WdfFunctions_01015
0x1400317ef  movups  [rbp+60h+var_60], xmm0
0x1400317f3  mov     rax, [rax+850h]
0x1400317fa  call    _guard_dispatch_icall
0x1400317ff  mov     rcx, qword ptr [rbp+60h+var_70+8]
0x140031803  lea     r15d, [r13+1]
0x140031807  lea     rdx, [rcx+20h]
0x14003180b  cmp     [rcx+2], r15w
0x140031810  jnz     short loc_140031821
0x140031812  mov     r14, rdx
0x140031815  mov     [rdi+94h], r13d
0x14003181c  mov     eax, r13d
0x14003181f  jmp     short loc_140031839
0x140031821  mov     eax, [rdx]
0x140031823  lea     r14, [rcx+30h]
0x140031827  mov     [rdi+94h], eax
0x14003182d  mov     rax, r13
0x140031830  cmp     [rdx], r13d
0x140031833  jbe     short loc_140031839
0x140031835  mov     rax, [rcx+28h]
0x140031839  lea     rcx, [rdi+28h]; SpinLock
0x14003183d  mov     [rdi+98h], rax
0x140031844  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003184b  nop     dword ptr [rax+rax+00h]
0x140031850  lock and dword ptr [rdi+66Ch], 0FFFFFFEFh
0x140031858  mov     dl, al; NewIrql
0x14003185a  lea     rcx, [rdi+28h]; SpinLock
0x14003185e  call    cs:__imp_KeReleaseSpinLock
0x140031865  nop     dword ptr [rax+rax+00h]
0x14003186a  mov     rax, [rdi+30h]
0x14003186e  movzx   r9d, byte ptr [r14+3]
0x140031873  movzx   r8d, byte ptr [r14+2]
0x140031878  mov     [rbp+60h+var_C8], rax
0x14003187c  lea     rcx, [rax+20h]
0x140031880  mov     rax, [rdi+8]
0x140031884  mov     rdx, rcx
0x140031887  mov     rax, [rax+598h]
0x14003188e  mov     [rsp+160h+var_120], rax
0x140031893  lea     rax, [rsp+160h+var_F0]
0x140031898  mov     [rsp+160h+var_128], rax
0x14003189d  mov     dword ptr [rsp+160h+var_130], 0FFFFFFFFh
0x1400318a5  mov     dword ptr [rsp+160h+var_138], 0FFFFFFFFh
0x1400318ad  mov     dword ptr [rsp+160h+var_140], 0FFFFFFFFh
0x1400318b5  call    HUBDESC_ParseConfigurationDescriptor
0x1400318ba  mov     rsi, rax
0x1400318bd  test    rax, rax
0x1400318c0  jnz     short loc_140031910
0x1400318c2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400318c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400318d0  jz      short loc_1400318F8
0x1400318d2  mov     rcx, [rdi+8]
0x1400318d6  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x1400318dd  lea     r9d, [rsi+22h]
0x1400318e1  mov     [rsp+160h+var_140], rax
0x1400318e6  lea     r8d, [rsi+5]
0x1400318ea  mov     dl, 2
0x1400318ec  mov     rcx, [rcx+598h]
0x1400318f3  call    WPP_RECORDER_SF_
0x1400318f8  mov     dword ptr [rdi+624h], 0C0004000h
0x140031902  lea     r12, [r14+8]
0x140031906  mov     ebx, 0C0000001h
0x14003190b  jmp     loc_140031FD8
0x140031910  mov     rcx, [rdi+998h]
0x140031917  test    rcx, rcx
0x14003191a  jz      short loc_140031954
0x14003191c  mov     r9d, [rcx]
0x14003191f  test    r9d, r9d
0x140031922  jz      short loc_140031954
0x140031924  mov     r10b, [rax+3]
0x140031928  mov     edx, r13d
0x14003192b  mov     r8d, edx
0x14003192e  cmp     [rcx+r8*2+5], r10b
0x140031933  jnz     short loc_14003193F
0x140031935  mov     al, [rsi+2]
0x140031938  cmp     [rcx+r8*2+4], al
0x14003193d  jz      short loc_140031949
0x14003193f  add     edx, r15d
0x140031942  cmp     edx, r9d
0x140031945  jb      short loc_14003192B
0x140031947  jmp     short loc_140031954
0x140031949  lock or dword ptr [rdi+66Ch], 8000h
0x140031954  movzx   ecx, byte ptr [rsi+4]
0x140031958  lea     r12, [r14+8]
0x14003195c  add     cx, r15w
0x140031960  mov     [r14+4], r13d
0x140031964  movzx   eax, cx
0x140031967  mov     [r12], r13
0x14003196b  add     ax, ax
0x14003196e  lea     rdx, [rbp+60h+var_A8]
0x140031972  add     cx, ax
0x140031975  xorps   xmm0, xmm0
0x140031978  shl     cx, 3
0x14003197c  mov     r9d, 64334855h
0x140031982  mov     [r14], cx
0x140031986  mov     r8d, 200h
0x14003198c  movzx   eax, byte ptr [rsi+4]
0x140031990  lea     rcx, [rsp+160h+var_E8]
0x140031995  mov     [r14+10h], eax
0x140031999  xor     eax, eax
0x14003199b  movups  [rbp+60h+var_98], xmm0
0x14003199f  mov     dword ptr [rbp+60h+var_98+8], r15d
0x1400319a3  mov     dword ptr [rbp+60h+var_98+0Ch], r15d
0x1400319a7  mov     [rsp+160h+var_130], rcx
0x1400319ac  lea     rcx, [rbp+60h+var_B8]
0x1400319b0  movups  [rbp+60h+var_A8], xmm0
0x1400319b4  mov     [rbp+60h+var_78], rax
0x1400319b8  movups  [rbp+60h+var_88], xmm0
0x1400319bc  mov     dword ptr [rbp+60h+var_A8], 38h ; '8'
0x1400319c3  mov     eax, [r14+10h]
0x1400319c7  mov     [rsp+160h+var_138], rcx
0x1400319cc  mov     rcx, cs:WdfDriverGlobals
0x1400319d3  lea     r15, [rax+rax*4]
0x1400319d7  mov     rax, cs:WdfFunctions_01015
0x1400319de  shl     r15, 4
0x1400319e2  add     r15, 28h ; '('
0x1400319e6  mov     [rsp+160h+var_140], r15
0x1400319eb  mov     rax, [rax+600h]
0x1400319f2  call    _guard_dispatch_icall
0x1400319f7  mov     ebx, eax
0x1400319f9  test    eax, eax
0x1400319fb  jns     short loc_140031A42
0x1400319fd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140031a04  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031a0b  jz      loc_140031FD8
0x140031a11  mov     rcx, [rdi+8]
0x140031a15  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140031a1c  mov     r9d, 23h ; '#'
0x140031a22  mov     dword ptr [rsp+160h+var_138], ebx
0x140031a26  mov     dl, 2
0x140031a28  mov     [rsp+160h+var_140], rax
0x140031a2d  mov     rcx, [rcx+598h]
0x140031a34  lea     r8d, [r9-1Eh]
0x140031a38  call    WPP_RECORDER_SF_d
0x140031a3d  jmp     loc_140031FD8
0x140031a42  mov     rcx, [rsp+160h+var_E8]; void *
0x140031a47  mov     r8, r15; Size
0x140031a4a  xor     edx, edx; Val
0x140031a4c  mov     [rbp+60h+var_D0], r12
0x140031a50  call    memset
0x140031a55  mov     rax, [rsp+160h+var_E8]
0x140031a5a  xor     r10d, r10d
0x140031a5d  mov     rcx, [rbp+60h+var_B8]
0x140031a61  mov     [rax], rcx
0x140031a64  lea     r15d, [r10+1]
0x140031a68  mov     rax, [rsp+160h+var_E8]
0x140031a6d  mov     [rax+20h], rsi
0x140031a71  movzx   ecx, byte ptr [rsi+4]
0x140031a75  mov     rax, [rsp+160h+var_E8]
0x140031a7a  mov     [rax+18h], ecx
0x140031a7d  mov     [rdi+40h], r10
0x140031a81  cmp     [rsp+160h+var_F0], r15b
0x140031a86  jnz     short loc_140031AA5
0x140031a88  mov     rax, [rsp+160h+var_E8]
0x140031a8d  lock or [rax+1Ch], r15d
0x140031a92  mov     rax, [rsp+160h+var_E8]
0x140031a97  lock or dword ptr [rax+1Ch], 2
0x140031a9c  mov     rax, [rsp+160h+var_E8]
0x140031aa1  mov     [rdi+40h], rax
0x140031aa5  mov     al, [rsi+5]
0x140031aa8  mov     ebx, 3
0x140031aad  mov     [r14+4], al
0x140031ab1  mov     al, [rsi+6]
0x140031ab4  mov     [r14+5], al
0x140031ab8  mov     al, [rsi+7]
0x140031abb  mov     [r14+6], al
0x140031abf  movzx   edx, byte ptr [rsi]
0x140031ac2  mov     r13, [rsp+160h+var_E8]
0x140031ac7  add     rdx, rsi
0x140031aca  mov     rsi, [rbp+60h+var_C8]
0x140031ace  movzx   eax, word ptr [rsi+22h]
0x140031ad2  lea     r9, [rsi+20h]
0x140031ad6  add     r9, rax
0x140031ad9  mov     eax, r10d
0x140031adc  mov     [rbp+60h+var_E0], eax
0x140031adf  mov     [rbp+60h+var_D8], r9
0x140031ae3  cmp     [r14+10h], r10d
0x140031ae7  jbe     loc_140031E64
0x140031aed  mov     rcx, rdx
0x140031af0  cmp     rdx, r9
0x140031af3  jnb     loc_140031F88
0x140031af9  lea     rsi, [rax+rax*4]
0x140031afd  mov     r11d, 1
0x140031b03  shl     rsi, 4
0x140031b07  lea     r15, [rax+rax*2]
0x140031b0b  mov     eax, [r14+r15*8+2Ch]
0x140031b10  mov     [rsi+r13+40h], eax
0x140031b15  lea     rax, [rdx+1]
0x140031b19  mov     [rsi+r13+30h], r11d
0x140031b1e  cmp     rax, r9
0x140031b21  jb      short loc_140031B67
0x140031b23  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140031b2a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031b31  jz      loc_140031FC2
0x140031b37  lea     r9d, [r11+16h]
0x140031b3b  jmp     loc_140031F9E
0x140031b40  movzx   eax, byte ptr [rcx]
0x140031b43  test    al, al
0x140031b45  jz      loc_140031E3D
0x140031b4b  add     rdx, rax
0x140031b4e  mov     rcx, rdx
0x140031b51  cmp     rdx, r9
0x140031b54  jnb     loc_140031E1E
0x140031b5a  lea     rax, [rdx+1]
0x140031b5e  cmp     rax, r9
0x140031b61  jnb     loc_140031DFF
0x140031b67  cmp     byte ptr [rax], 5
0x140031b6a  jnz     short loc_140031B40
0x140031b6c  cmp     rdx, r9
0x140031b6f  jnb     loc_140031F70
0x140031b75  lea     rax, [rdx+7]
0x140031b79  cmp     rax, r9
0x140031b7c  ja      loc_140031F58
0x140031b82  mov     eax, [r14+r15*8+2Ch]
0x140031b87  test    r11b, al
0x140031b8a  jz      short loc_140031B96
0x140031b8c  movzx   eax, word ptr [r14+r15*8+18h]
0x140031b92  mov     [rdx+4], ax
0x140031b96  mov     r8d, [r14+r15*8+2Ch]
0x140031b9b  and     r8d, 0F0h
0x140031ba2  cmp     r8d, 10h
0x140031ba6  jz      short loc_140031BCA
0x140031ba8  cmp     r8d, 20h ; ' '
0x140031bac  jz      short loc_140031BBF
0x140031bae  cmp     r8d, 30h ; '0'
0x140031bb2  mov     ecx, ebx
0x140031bb4  cmovnz  ecx, r10d
0x140031bb8  mov     [rsi+r13+70h], ecx
0x140031bbd  jmp     short loc_140031BCF
0x140031bbf  mov     dword ptr [rsi+r13+70h], 2
0x140031bc8  jmp     short loc_140031BCF
0x140031bca  mov     [rsi+r13+70h], r11d
0x140031bcf  mov     eax, r9d
0x140031bd2  mov     [rsi+r13+48h], rdx
0x140031bd7  sub     eax, edx
0x140031bd9  mov     [rsi+r13+50h], eax
0x140031bde  mov     eax, 250h
0x140031be3  cmp     [rdi+7CEh], ax
0x140031bea  jnb     short loc_140031C15
0x140031bec  movzx   eax, word ptr [rdx+4]
0x140031bf0  mov     r8d, 7FFh
0x140031bf6  movzx   ecx, ax
0x140031bf9  and     ax, r8w
0x140031bfd  shr     cx, 0Bh
0x140031c01  and     cx, bx
0x140031c04  movzx   eax, ax
0x140031c07  add     cx, r11w
0x140031c0b  movzx   r8d, cx
0x140031c0f  imul    r8d, eax
0x140031c13  jmp     short loc_140031C1A
0x140031c15  movzx   r8d, word ptr [rdx+4]
0x140031c1a  mov     [r14+r15*8+18h], r8w
0x140031c20  mov     ecx, 6
0x140031c25  movzx   eax, byte ptr [rdx+6]
0x140031c29  cmp     al, cl
0x140031c2b  cmovb   ecx, eax
0x140031c2e  mov     [r14+r15*8+1Bh], cl
0x140031c33  mov     al, [rdx+2]
0x140031c36  mov     [r14+r15*8+1Ah], al
0x140031c3b  movzx   ecx, byte ptr [rdx+3]
0x140031c3f  and     ecx, ebx
0x140031c41  jz      short loc_140031C6B
0x140031c43  sub     ecx, r11d
  ... truncated ...
```
