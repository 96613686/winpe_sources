# QdcCompat::ConvertPathModalityToDisplayConfig

- ea: `0x1800415c0`
- end: `0x18004214d`
- name: `QdcCompat::ConvertPathModalityToDisplayConfig`
- size: `2957`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041310`

## callees

- `0x1800415c0`
- `0x180042154`
- `0x180042184`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserDisplayConfigGetDeviceInfo` at `0x180041761`
- `win32u!NtUserDisplayConfigGetDeviceInfo` at `0x180041ce3`
- `win32u!NtUserDisplayConfigGetDeviceInfo` at `0x18004205c`
- `win32u!NtUserDisplayConfigGetDeviceInfo` at `0x180041761`
- `win32u!NtUserDisplayConfigGetDeviceInfo` at `0x180041ce3`
- `win32u!NtUserDisplayConfigGetDeviceInfo` at `0x18004205c`
- `ntdll!RtlFreeHeap` at `0x180041bd6`
- `ntdll!RtlFreeHeap` at `0x180041d39`
- `ntdll!RtlFreeHeap` at `0x180041f7a`
- `ntdll!RtlFreeHeap` at `0x18004208f`
- `ntdll!RtlFreeHeap` at `0x180041bd6`
- `ntdll!RtlFreeHeap` at `0x180041d39`
- `ntdll!RtlFreeHeap` at `0x180041f7a`
- `ntdll!RtlFreeHeap` at `0x18004208f`
- `ntdll!RtlAllocateHeap` at `0x180041613`
- `ntdll!RtlAllocateHeap` at `0x180041613`

## pseudocode

```c
__int64 __fastcall QdcCompat::ConvertPathModalityToDisplayConfig(
        unsigned int a1,
        __int64 a2,
        char a3,
        unsigned __int8 a4,
        char a5,
        char a6,
        __int64 a7)
{
  _DWORD *v10; // r12
  __int64 result; // rax
  unsigned int v12; // r11d
  char v13; // si
  char v14; // r13
  __int64 v15; // r10
  __int64 v16; // r9
  int v17; // eax
  unsigned int i; // eax
  __int64 v19; // rdx
  char v20; // al
  char v21; // al
  unsigned int v22; // eax
  __int64 v23; // r14
  __int64 v24; // rcx
  __int64 *v25; // rsi
  _DWORD *v26; // r15
  __int64 *v27; // rdx
  _DWORD *v28; // rcx
  int v29; // eax
  int v30; // r12d
  int v31; // r13d
  __int64 v32; // rax
  int v33; // eax
  int v34; // eax
  int v35; // r11d
  __int64 *v36; // r10
  __int64 v37; // rax
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // r8
  unsigned __int64 j; // rdx
  __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  __int64 v43; // r9
  __int64 v44; // r11
  unsigned __int64 v45; // rax
  __int64 v46; // r8
  int v47; // r11d
  _QWORD *v48; // r15
  _QWORD *v49; // r9
  __int64 v50; // rax
  unsigned __int64 v51; // r8
  unsigned __int64 v52; // rcx
  __int64 v53; // r10
  __int64 v54; // rdx
  int DeviceInfo; // r13d
  PVOID v56; // r8
  __int64 NextModeArrayEntry; // rax
  __int64 v58; // r10
  __int128 v59; // xmm0
  __int64 v60; // rdx
  char v61; // r8
  unsigned int v62; // esi
  __int64 v63; // rdi
  unsigned __int64 v64; // rcx
  unsigned __int64 v65; // rax
  __int64 v66; // rcx
  int v67; // edx
  int v68; // eax
  __int64 v69; // r8
  unsigned int v70; // eax
  int v71; // r14d
  bool v72; // r11
  unsigned int v73; // r9d
  unsigned int v74; // esi
  __int64 v75; // rdx
  _DWORD *v76; // r8
  int v77; // ecx
  int v78; // eax
  char v81; // [rsp+22h] [rbp-AFh]
  char v82; // [rsp+23h] [rbp-AEh]
  char v83; // [rsp+24h] [rbp-ADh]
  unsigned int v84; // [rsp+28h] [rbp-A9h]
  unsigned int v85; // [rsp+2Ch] [rbp-A5h]
  unsigned int v86; // [rsp+2Ch] [rbp-A5h]
  unsigned int v87; // [rsp+30h] [rbp-A1h]
  unsigned int v88; // [rsp+30h] [rbp-A1h]
  char v89; // [rsp+40h] [rbp-91h]
  char v90; // [rsp+40h] [rbp-91h]
  PVOID P; // [rsp+48h] [rbp-89h] BYREF
  __int64 v92; // [rsp+50h] [rbp-81h]
  _DWORD v93[2]; // [rsp+58h] [rbp-79h] BYREF
  __int64 v94; // [rsp+60h] [rbp-71h]
  int v95; // [rsp+68h] [rbp-69h]
  unsigned int v96; // [rsp+6Ch] [rbp-65h]
  __int64 v97; // [rsp+70h] [rbp-61h]
  unsigned int v98; // [rsp+78h] [rbp-59h]
  int v99; // [rsp+7Ch] [rbp-55h]
  _DWORD v100[2]; // [rsp+80h] [rbp-51h] BYREF
  __int64 v101; // [rsp+88h] [rbp-49h]
  int v102; // [rsp+90h] [rbp-41h]
  __int128 v103; // [rsp+94h] [rbp-3Dh]
  int v104; // [rsp+A4h] [rbp-2Dh]
  _DWORD v105[2]; // [rsp+A8h] [rbp-29h] BYREF
  __int128 v106; // [rsp+B0h] [rbp-21h]
  __int64 v107; // [rsp+C0h] [rbp-11h]
  unsigned int v108; // [rsp+C8h] [rbp-9h]
  int v109; // [rsp+CCh] [rbp-5h]

  P = RtlAllocateHeap(pUserHeap, 8u, 8LL * a1);
  v10 = P;
  if ( !P )
    return 3221225495LL;
  if ( a6 )
  {
    if ( !*(_DWORD *)(a7 + 4) )
    {
LABEL_4:
      QdcCompat::ConvertPathModalityToDisplayConfig_::_2_::AUTO::_AUTO(&P);
      return 3221225507LL;
    }
  }
  else if ( *(_DWORD *)(a7 + 4) < a1 )
  {
    goto LABEL_4;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v84 = 0;
  v81 = 0;
  if ( a1 )
  {
    v15 = 0;
    do
    {
      v16 = a2 + 216 * v15;
      v17 = *(_DWORD *)(v16 + 80);
      if ( v17 == 13 || v17 == 0x80000000 || v17 == 11 )
        v14 = 1;
      if ( (*(_QWORD *)v16 & 0x4000000000000LL) != 0 )
      {
        for ( i = 0; i < a1; ++i )
        {
          v19 = 216LL * i;
          if ( (*(_QWORD *)(v19 + a2) & 0x4000000000000LL) != 0 && *(_DWORD *)(v19 + a2 + 156) == *(_DWORD *)(v16 + 156) )
            goto LABEL_16;
        }
      }
      i = -559038737;
LABEL_16:
      v10[2 * v15] = i;
      v20 = *(_BYTE *)(v16 + 101);
      if ( (v20 & 1) != 0 || (v20 & 2) == 0 || a4 )
      {
        v21 = 0;
      }
      else
      {
        v13 = 1;
        v21 = 1;
      }
      ++v12;
      LOBYTE(v10[2 * v15++ + 1]) = v21;
    }
    while ( v12 < a1 );
    v81 = v14;
    if ( v13 )
    {
      v66 = 0;
      do
      {
        if ( LOBYTE(v10[2 * v66 + 1]) )
        {
          if ( (*(_QWORD *)(216LL * (unsigned int)v66 + a2) & 0x4000000000000LL) != 0 )
          {
            v67 = v10[2 * v66];
            if ( v67 != (_DWORD)v66 )
            {
              v69 = 0;
              do
              {
                if ( v10[2 * v69] == v67 )
                {
                  v10[2 * v69] = v66;
                  v67 = v10[2 * v66];
                }
                v69 = (unsigned int)(v69 + 1);
              }
              while ( (unsigned int)v69 < a1 );
            }
          }
        }
        v66 = (unsigned int)(v66 + 1);
      }
      while ( (unsigned int)v66 < a1 );
    }
  }
  v83 = 0;
  v82 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v105[1] = 40;
  v105[0] = -14;
  v109 = 2;
  NtUserDisplayConfigGetDeviceInfo(v105, 0x4000000000000LL);
  v22 = 0;
  v23 = *(_QWORD *)(a7 + 8);
  v89 = BYTE4(v107);
  v85 = v108;
  while ( 1 )
  {
    v87 = v22;
    if ( v22 >= a1 )
      break;
    v24 = v22;
    v25 = (__int64 *)(a2 + 216LL * v22);
    if ( a6 )
    {
      if ( v14 )
      {
        v68 = *((_DWORD *)v25 + 20);
        if ( v68 != 13 && v68 != 0x80000000 && v68 != 11 )
          goto LABEL_89;
      }
    }
    v26 = 0;
    if ( (*v25 & 0x4000000000000LL) != 0 )
    {
      v26 = (_DWORD *)(a2 + 216LL * (unsigned int)v10[2 * v24]);
      if ( *((_DWORD *)v25 + 6) == v26[6] && *((_DWORD *)v25 + 4) == v26[4] && *((_DWORD *)v25 + 5) == v26[5] )
        v26 = 0;
      else
        v82 = 1;
    }
    v27 = v25 + 2;
    *(_QWORD *)v23 = v25[2];
    *(_DWORD *)(v23 + 8) = *((_DWORD *)v25 + 6);
    *(_DWORD *)(v23 + 16) = (*v25 & 0x4000000000000000LL) != 0;
    *(_QWORD *)(v23 + 20) = v25[2];
    *(_DWORD *)(v23 + 28) = *((_DWORD *)v25 + 7);
    *(_DWORD *)(v23 + 36) = *((_DWORD *)v25 + 20);
    *(_DWORD *)(v23 + 68) = 0;
    if ( (*v25 & 0x1000000) != 0 )
    {
      *(_QWORD *)(v23 + 48) = *(__int64 *)((char *)v25 + 196);
      if ( a5 && *((_DWORD *)v25 + 53) > 1u )
        *(_DWORD *)(v23 + 68) = 16;
      v28 = (_DWORD *)(v23 + 56);
    }
    else if ( (*v25 & 2) != 0 )
    {
      v64 = v25[6];
      if ( (*((_WORD *)v25 + 37) & 0x3F) != 0 )
        LODWORD(v65) = (*((_WORD *)v25 + 37) & 0x3F) * HIDWORD(v64);
      else
        v65 = HIDWORD(v64);
      *(_DWORD *)(v23 + 48) = v64;
      v27 = v25 + 2;
      v28 = (_DWORD *)(v23 + 56);
      *(_DWORD *)(v23 + 52) = v65;
      *(_DWORD *)(v23 + 56) = 1;
    }
    else
    {
      v28 = (_DWORD *)(v23 + 56);
      *(_QWORD *)(v23 + 48) = 0;
      *(_DWORD *)(v23 + 56) = 0;
    }
    if ( (*(_BYTE *)v25 & 4) != 0 )
      *v28 = *((_DWORD *)v25 + 19);
    if ( (*(_DWORD *)v25 & 0x200LL) == 0 )
    {
      *(_DWORD *)(v23 + 40) = 1;
LABEL_35:
      v30 = *((_DWORD *)v25 + 31);
      v31 = *((_DWORD *)v25 + 32);
      goto LABEL_36;
    }
    v29 = *((_DWORD *)v25 + 26);
    *(_DWORD *)(v23 + 40) = v29;
    if ( ((v29 - 2) & 0xFFFFFFFD) != 0 )
      goto LABEL_35;
    v30 = *((_DWORD *)v25 + 32);
    v31 = *((_DWORD *)v25 + 31);
LABEL_36:
    v32 = *v25;
    if ( a3 )
    {
      if ( (v32 & 0x10000) != 0 )
      {
        v33 = *((_DWORD *)v25 + 28);
        goto LABEL_39;
      }
    }
    else if ( (v32 & 0x40000000000LL) != 0 )
    {
      v33 = *((_DWORD *)v25 + 27);
      goto LABEL_39;
    }
    v33 = 128;
LABEL_39:
    *(_DWORD *)(v23 + 44) = v33;
    *(_DWORD *)(v23 + 64) = 0;
    v34 = 0;
    if ( (*v25 & 0x2000000000000000LL) != 0 )
    {
      *(_DWORD *)(v23 + 64) = 1;
      v34 = 1;
    }
    if ( (*v25 & 0x200000000000000LL) != 0 )
    {
      v34 |= 2u;
      *(_DWORD *)(v23 + 64) = v34;
    }
    if ( (*v25 & 0x400000000000000LL) != 0 )
    {
      v34 |= 4u;
      *(_DWORD *)(v23 + 64) = v34;
    }
    if ( (*v25 & 0x1000000000000000LL) != 0 )
    {
      v34 |= 0x10u;
      *(_DWORD *)(v23 + 64) = v34;
    }
    if ( (*v25 & 0x800000000000000LL) != 0 )
    {
      v34 |= 8u;
      *(_DWORD *)(v23 + 64) = v34;
    }
    if ( *((_DWORD *)v25 + 47) == 1 )
      *(_DWORD *)(v23 + 64) = v34 | 0x20;
    *(_DWORD *)(v23 + 60) = (*v25 & 0x1D00000000000000LL) != 0;
    if ( *v25 >= 0 )
      v83 = 1;
    else
      *(_DWORD *)(v23 + 68) |= 1u;
    if ( !v26 || a4 )
    {
      v35 = *((_DWORD *)v25 + 7);
      v36 = v27;
    }
    else
    {
      v101 = *v27;
      v102 = *((_DWORD *)v25 + 6);
      v103 = 0;
      v104 = 0;
      v100[1] = 40;
      v100[0] = -14;
      result = NtUserDisplayConfigGetDeviceInfo(v100, v27);
      v84 = result;
      if ( (int)result < 0 )
      {
        if ( P )
        {
          RtlFreeHeap(pUserHeap, 0, P);
          return v84;
        }
        return result;
      }
      v36 = (__int64 *)(v26 + 4);
      v85 = HIDWORD(v103);
      v35 = (*((_DWORD *)v25 + 7) & ~HIDWORD(v103)) + ((_DWORD)v103 << SBYTE8(v103));
      v89 = BYTE8(v103);
      *(_DWORD *)(v23 + 28) = v35;
      *(_QWORD *)(v23 + 20) = *((_QWORD *)v26 + 2);
    }
    v37 = *v36;
    v92 = *v36;
    v38 = *(_QWORD *)(a7 + 24);
    v39 = *(_QWORD *)(a7 + 40);
    for ( j = v38; j < v39; j += 64LL )
    {
      if ( *(_DWORD *)j == 2 && *(_DWORD *)(j + 4) == v35 && *(_QWORD *)(j + 8) == __PAIR64__(HIDWORD(v92), v37) )
      {
        v42 = (__int64)(j - v38) >> 6;
        goto LABEL_70;
      }
    }
    if ( (*(_BYTE *)v25 & 0x87) == 0 )
    {
      v42 = 0xFFFFFFFFLL;
LABEL_70:
      v41 = a7;
      goto LABEL_71;
    }
    if ( (__int64)(v39 - v38) >> 6 >= *(int *)(a7 + 16) || (v41 = a7, *(_QWORD *)(a7 + 40) = v39 + 64, !v39) )
    {
LABEL_112:
      v56 = P;
LABEL_113:
      if ( v56 )
        RtlFreeHeap(pUserHeap, 0, v56);
      return 3221225507LL;
    }
    *(_DWORD *)v39 = 2;
    *(_QWORD *)(v39 + 8) = *v36;
    *(_DWORD *)(v39 + 4) = v35;
    *(_OWORD *)(v39 + 16) = *((_OWORD *)v25 + 2);
    *(_OWORD *)(v39 + 32) = *((_OWORD *)v25 + 3);
    *(_OWORD *)(v39 + 48) = *((_OWORD *)v25 + 4);
    v42 = (__int64)(v39 - *(_QWORD *)(a7 + 24)) >> 6;
    if ( a3 )
      *(_QWORD *)(v39 + 48) = 0;
    if ( !a5 && (*(_DWORD *)v25 & 0x1000000) != 0 )
    {
      v43 = *(__int64 *)((char *)v25 + 196);
      v44 = v25[6];
      if ( (*((_WORD *)v25 + 37) & 0x3F) != 0 )
        v45 = HIDWORD(v44) * (*((unsigned __int16 *)v25 + 37) & 0x3Fu);
      else
        v45 = HIDWORD(v25[6]);
      if ( v45 * (unsigned int)v43 != HIDWORD(*(unsigned __int64 *)((char *)v25 + 196)) * (unsigned int)v44 )
      {
        *(_DWORD *)(v39 + 56) &= 0xFFC1FFFF;
        *(_DWORD *)(v39 + 56) |= 0x10000u;
        *(_QWORD *)(v39 + 32) = v43;
      }
      goto LABEL_70;
    }
LABEL_71:
    v46 = a4;
    if ( a4 )
      *(_WORD *)(v23 + 34) = v42;
    else
      *(_DWORD *)(v23 + 32) = v42;
    if ( v26 && !a4 )
    {
      v47 = v26[6];
      v49 = v26 + 4;
      *(_DWORD *)(v23 + 8) = v47;
      v48 = v25 + 2;
      *(_QWORD *)v23 = *v49;
LABEL_75:
      v50 = *v49;
      v51 = *(_QWORD *)(v41 + 24);
      v92 = *v49;
      v52 = v51;
      v42 = *(_QWORD *)(a7 + 40);
      while ( 1 )
      {
        if ( v52 >= v42 )
        {
          v46 = a4;
          goto LABEL_80;
        }
        if ( *(_DWORD *)v52 == 1 && *(_DWORD *)(v52 + 4) == v47 && *(_QWORD *)(v52 + 8) == __PAIR64__(HIDWORD(v92), v50) )
          break;
        v52 += 64LL;
      }
      *(_DWORD *)(v23 + 12) = (__int64)(v52 - v51) >> 6;
      goto LABEL_87;
    }
    v47 = *((_DWORD *)v25 + 6);
    v48 = v25 + 2;
    v49 = v25 + 2;
    if ( !a4 )
      goto LABEL_75;
LABEL_80:
    if ( (*(_DWORD *)v25 & 0x20000) == 0 )
    {
      if ( (*(_BYTE *)(v23 + 68) & 1) != 0 )
      {
        if ( P )
          RtlFreeHeap(pUserHeap, 0, P);
        return 3221225659LL;
      }
      *(_DWORD *)(v23 + 12) = -1;
      if ( !(_BYTE)v46 )
        goto LABEL_87;
      v53 = a7;
      goto LABEL_122;
    }
    v53 = a7;
    v54 = *(_QWORD *)(a7 + 40);
    if ( (v54 - *(_QWORD *)(a7 + 24)) >> 6 >= *(int *)(a7 + 16) )
      goto LABEL_112;
    *(_QWORD *)(a7 + 40) = v54 + 64;
    if ( !v54 )
      goto LABEL_112;
    *(_DWORD *)v54 = 1;
    *(_DWORD *)(v54 + 4) = v47;
    *(_QWORD *)(v54 + 8) = *v49;
    *(_DWORD *)(v54 + 16) = v30;
    *(_DWORD *)(v54 + 20) = v31;
    *(_DWORD *)(v54 + 24) = 4;
    if ( (*(_DWORD *)v25 & 0x800LL) != 0 )
      *(_QWORD *)(v54 + 28) = *(__int64 *)((char *)v25 + 116);
    else
      *(_QWORD *)(v54 + 28) = 0x7FFFFFFF;
    v42 = (v54 - *(_QWORD *)(a7 + 24)) >> 6;
    if ( (_BYTE)v46 )
    {
      *(_WORD *)(v23 + 14) = v42;
      *(_DWORD *)(v23 + 12) |= 0xFFFFu;
LABEL_122:
      *(_DWORD *)(v23 + 32) |= 0xFFFFu;
      if ( *((_BYTE *)v25 + 101) )
      {
        *(_DWORD *)(v23 + 68) |= 8u;
        if ( *v25 < 0 && (*v25 & 0x800000) != 0 )
        {
          NextModeArrayEntry = QdcCompat::GetNextModeArrayEntry(v53, v42, v46, v49);
          if ( !NextModeArrayEntry )
          {
            v56 = P;
            if ( P )
              goto LABEL_113;
            return 3221225507LL;
          }
          *(_DWORD *)NextModeArrayEntry = 3;
          *(_DWORD *)(NextModeArrayEntry + 4) = *((_DWORD *)v25 + 7);
          *(_QWORD *)(NextModeArrayEntry + 8) = *v48;
          *(_DWORD *)(NextModeArrayEntry + 16) = *((_DWORD *)v25 + 22);
          *(_DWORD *)(NextModeArrayEntry + 20) = *((_DWORD *)v25 + 23);
          v59 = *(_OWORD *)((char *)v25 + 140);
          *(_QWORD *)(NextModeArrayEntry + 40) = 0;
          *(_DWORD *)(NextModeArrayEntry + 48) = v30;
          *(_OWORD *)(NextModeArrayEntry + 24) = v59;
          *(_DWORD *)(NextModeArrayEntry + 52) = v31;
          *(_WORD *)(v23 + 32) = (__int64)(unsigned int)(NextModeArrayEntry - *(_DWORD *)(v58 + 24)) >> 6;
        }
      }
      goto LABEL_87;
    }
    *(_DWORD *)(v23 + 12) = v42;
LABEL_87:
    v10 = P;
    v23 += 72;
    if ( a6 )
      break;
    v14 = v81;
LABEL_89:
    v22 = v87 + 1;
  }
  *(_QWORD *)(a7 + 32) = v23;
  if ( v82 && v83 )
  {
    DeviceInfo = v84;
    if ( !a4 )
    {
      v60 = v85;
      v61 = v89;
      v62 = 0;
      v88 = 0;
      while ( v62 < a1 )
      {
        v63 = *(_QWORD *)(a7 + 8) + 72LL * v62;
        if ( (*(_BYTE *)(v63 + 68) & 1) != 0 )
        {
          v70 = *(_DWORD *)(v63 + 28);
          if ( (v70 & (unsigned int)v60) != 0 )
          {
            v94 = 0;
            v96 = v70 >> v61;
            v95 = 0;
            v97 = 0;
            v98 = 0;
            v93[1] = 40;
            v93[0] = -14;
            v99 = 1;
            DeviceInfo = NtUserDisplayConfigGetDeviceInfo(v93, v60);
            if ( DeviceInfo < 0 )
            {
              QdcCompat::ConvertPathModalityToDisplayConfig_::_2_::AUTO::_AUTO(&P);
              return (unsigned int)DeviceInfo;
            }
            v60 = v98;
            v61 = BYTE4(v97);
            v71 = v95;
            v86 = v98;
            v90 = BYTE4(v97);
            v72 = v94 != *(_QWORD *)(v63 + 20);
            v73 = 0;
            if ( a1 )
            {
              v74 = v98;
              do
              {
                v75 = *(_QWORD *)(a7 + 8) + 72LL * v73;
                if ( (*(_BYTE *)(v75 + 68) & 1) == 0 )
                {
                  if ( v72 )
                  {
                    if ( *(_DWORD *)(v75 + 28) == (*(_DWORD *)(v63 + 28) & ~v74) )
                    {
                      *(_DWORD *)(v75 + 64) &= ~1u;
                      *(_DWORD *)(v75 + 60) = 0;
                    }
                  }
                  else
                  {
                    v76 = (_DWORD *)(v75 + 28);
                    v77 = ~v74;
                    if ( *(_DWORD *)(v75 + 8) == *(_DWORD *)(v63 + 8) && *v76 == (v77 & *(_DWORD *)(v63 + 28)) )
                    {
                      *v76 = *(_DWORD *)(v63 + 28);
                      *(_DWORD *)(v75 + 8) = v71;
                    }
                    else
                    {
                      v78 = *(_DWORD *)(v63 + 28);
                      if ( *v76 == (v78 & v77) )
                        *v76 = v78;
                    }
                  }
                }
                ++v73;
              }
              while ( v73 < a1 );
              v62 = v88;
              v60 = v86;
              v61 = v90;
            }
          }
        }
        v88 = ++v62;
      }
    }
  }
  else
  {
    DeviceInfo = v84;
  }
  if ( v10 )
    RtlFreeHeap(pUserHeap, 0, v10);
  return (unsigned int)DeviceInfo;
}

```

## disassembly

```asm
0x1800415c0  push    rbp
0x1800415c2  push    rbx
0x1800415c3  push    rdi
0x1800415c4  push    r12
0x1800415c6  push    r14
0x1800415c8  push    r15
0x1800415ca  lea     rbp, [rsp-17h]
0x1800415cf  sub     rsp, 0E8h
0x1800415d6  mov     rax, cs:__security_cookie
0x1800415dd  xor     rax, rsp
0x1800415e0  mov     [rbp+3Fh+var_40], rax
0x1800415e4  mov     r15, [rbp+3Fh+arg_30]
0x1800415e8  mov     rdi, rdx
0x1800415eb  mov     [rsp+110h+var_EF], r8b
0x1800415f0  mov     edx, 8; Flags
0x1800415f5  mov     r8d, ecx
0x1800415f8  movzx   r14d, r9b
0x1800415fc  mov     ebx, ecx
0x1800415fe  mov     rcx, cs:pUserHeap; HeapHandle
0x180041605  shl     r8, 3; Size
0x180041609  mov     [rsp+110h+var_F0], r9b
0x18004160e  mov     [rsp+110h+var_D8], r15
0x180041613  call    cs:__imp_RtlAllocateHeap
0x180041619  mov     [rsp+110h+P], rax
0x18004161e  mov     r12, rax
0x180041621  test    rax, rax
0x180041624  jz      loc_180041C61
0x18004162a  cmp     [rbp+3Fh+arg_28], 0
0x18004162e  jz      short loc_18004164B
0x180041630  cmp     dword ptr [r15+4], 1
0x180041635  jnb     short loc_180041651
0x180041637  lea     rcx, [rsp+110h+P]
0x18004163c  call    _QdcCompat__ConvertPathModalityToDisplayConfig____2___AUTO___AUTO
0x180041641  mov     eax, 0C0000023h
0x180041646  jmp     loc_180041BEF
0x18004164b  cmp     [r15+4], ebx
0x18004164f  jb      short loc_180041637
0x180041651  mov     [rsp+110h+arg_10], rsi
0x180041659  xor     r11d, r11d
0x18004165c  mov     [rsp+110h+var_30], r13
0x180041664  xor     sil, sil
0x180041667  xor     r13b, r13b
0x18004166a  mov     [rsp+110h+var_E8], 0
0x180041672  mov     [rsp+110h+var_EE], r13b
0x180041677  mov     rdx, 4000000000000h
0x180041681  test    ebx, ebx
0x180041683  jz      loc_180041727
0x180041689  xor     r10d, r10d
0x18004168c  nop     dword ptr [rax+00h]
0x180041690  imul    r9, r10, 0D8h
0x180041697  add     r9, rdi
0x18004169a  mov     eax, [r9+50h]
0x18004169e  cmp     eax, 0Dh
0x1800416a1  jnz     loc_180041C68
0x1800416a7  mov     r13b, 1
0x1800416aa  test    [r9], rdx
0x1800416ad  jz      loc_180041CA3
0x1800416b3  mov     r8d, [r9+9Ch]
0x1800416ba  xor     eax, eax
0x1800416bc  nop     dword ptr [rax+00h]
0x1800416c0  cmp     eax, ebx
0x1800416c2  jnb     loc_180041C99
0x1800416c8  mov     ecx, eax
0x1800416ca  imul    rdx, rcx, 0D8h
0x1800416d1  mov     rcx, 4000000000000h
0x1800416db  test    [rdx+rdi], rcx
0x1800416df  jz      short loc_1800416EB
0x1800416e1  cmp     [rdx+rdi+9Ch], r8d
0x1800416e9  jz      short loc_1800416EF
0x1800416eb  inc     eax
0x1800416ed  jmp     short loc_1800416C0
0x1800416ef  mov     rdx, rcx
0x1800416f2  mov     [r12+r10*8], eax
0x1800416f6  movzx   eax, byte ptr [r9+65h]
0x1800416fb  test    al, 1
0x1800416fd  jz      loc_180041EDF
0x180041703  xor     al, al
0x180041705  inc     r11d
0x180041708  mov     [r12+r10*8+4], al
0x18004170d  inc     r10
0x180041710  cmp     r11d, ebx
0x180041713  jb      loc_180041690
0x180041719  mov     [rsp+110h+var_EE], r13b
0x18004171e  test    sil, sil
0x180041721  jnz     loc_180041F8A
0x180041727  xorps   xmm0, xmm0
0x18004172a  mov     [rsp+110h+var_EC], 0
0x18004172f  lea     rcx, [rbp+3Fh+var_68]
0x180041733  mov     [rsp+110h+var_ED], 0
0x180041738  movdqu  [rbp+3Fh+var_60], xmm0
0x18004173d  mov     [rbp+3Fh+var_50], 0
0x180041745  mov     [rbp+3Fh+var_48], 0
0x18004174c  mov     [rbp+3Fh+var_64], 28h ; '('
0x180041753  mov     [rbp+3Fh+var_68], 0FFFFFFF2h
0x18004175a  mov     [rbp+3Fh+var_44], 2
0x180041761  call    cs:__imp_NtUserDisplayConfigGetDeviceInfo
0x180041767  mov     r8d, dword ptr [rbp+3Fh+var_50+4]
0x18004176b  xor     eax, eax
0x18004176d  mov     edx, [rbp+3Fh+var_48]
0x180041770  mov     r10, 200000000000000h
0x18004177a  mov     r14, [r15+8]
0x18004177e  mov     r11, 400000000000000h
0x180041788  mov     dword ptr [rsp+110h+var_D0], r8d
0x18004178d  mov     r9, 1D00000000000000h
0x180041797  mov     r8, 40000000000h
0x1800417a1  mov     [rsp+110h+var_E4], edx
0x1800417a5  mov     [rsp+110h+var_E0], eax
0x1800417a9  cmp     eax, ebx
0x1800417ab  jnb     loc_180041BAC
0x1800417b1  mov     ecx, eax
0x1800417b3  imul    rsi, rcx, 0D8h
0x1800417ba  add     rsi, rdi
0x1800417bd  cmp     [rbp+3Fh+arg_28], 0
0x1800417c1  jnz     loc_180041FC1
0x1800417c7  xor     r13d, r13d
0x1800417ca  mov     rax, 4000000000000h
0x1800417d4  mov     r15d, r13d
0x1800417d7  test    [rsi], rax
0x1800417da  jz      short loc_18004180E
0x1800417dc  mov     eax, [r12+rcx*8]
0x1800417e0  imul    r15, rax, 0D8h
0x1800417e7  add     r15, rdi
0x1800417ea  mov     eax, [r15+18h]
0x1800417ee  cmp     [rsi+18h], eax
0x1800417f1  jnz     short loc_180041809
0x1800417f3  mov     eax, [r15+10h]
0x1800417f7  cmp     [rsi+10h], eax
0x1800417fa  jnz     short loc_180041809
0x1800417fc  mov     eax, [r15+14h]
0x180041800  cmp     [rsi+14h], eax
0x180041803  jz      loc_180041EFC
0x180041809  mov     [rsp+110h+var_ED], 1
0x18004180e  mov     rax, [rsi+10h]
0x180041812  lea     rdx, [rsi+10h]
0x180041816  mov     [r14], rax
0x180041819  mov     eax, [rsi+18h]
0x18004181c  mov     [r14+8], eax
0x180041820  mov     rax, [rsi]
0x180041823  shr     rax, 3Eh
0x180041827  and     eax, 1
0x18004182a  mov     [r14+10h], eax
0x18004182e  mov     rax, [rdx]
0x180041831  mov     [r14+14h], rax
0x180041835  mov     eax, [rsi+1Ch]
0x180041838  mov     [r14+1Ch], eax
0x18004183c  mov     eax, [rsi+50h]
0x18004183f  mov     [r14+24h], eax
0x180041843  mov     [r14+44h], r13d
0x180041847  mov     rax, [rsi]
0x18004184a  bt      rax, 18h
0x18004184f  jnb     loc_180041E2F
0x180041855  mov     rax, [rsi+0C4h]
0x18004185c  mov     [r14+30h], rax
0x180041860  cmp     [rbp+3Fh+arg_20], r13b
0x180041864  jnz     loc_180041F17
0x18004186a  lea     rcx, [r14+38h]
0x18004186e  test    byte ptr [rsi], 4
0x180041871  jz      short loc_180041878
0x180041873  mov     eax, [rsi+4Ch]
0x180041876  mov     [rcx], eax
0x180041878  mov     eax, [rsi]
0x18004187a  bt      rax, 9
0x18004187f  jnb     loc_180041D5D
0x180041885  mov     eax, [rsi+68h]
0x180041888  mov     [r14+28h], eax
0x18004188c  add     eax, 0FFFFFFFEh
0x18004188f  test    eax, 0FFFFFFFDh
0x180041894  jz      loc_180041C89
0x18004189a  mov     r12d, [rsi+7Ch]
0x18004189e  mov     r13d, [rsi+80h]
0x1800418a5  cmp     [rsp+110h+var_EF], 0
0x1800418aa  mov     rax, [rsi]
0x1800418ad  jnz     loc_180041E20
0x1800418b3  test    r8, rax
0x1800418b6  jz      loc_180041E47
0x1800418bc  mov     eax, [rsi+6Ch]
0x1800418bf  xor     r8d, r8d
0x1800418c2  mov     [r14+2Ch], eax
0x1800418c6  mov     rcx, 2000000000000000h
0x1800418d0  mov     [r14+40h], r8d
0x1800418d4  mov     eax, r8d
0x1800418d7  test    [rsi], rcx
0x1800418da  jz      short loc_1800418E9
0x1800418dc  mov     dword ptr [r14+40h], 1
0x1800418e4  mov     eax, 1
0x1800418e9  test    [rsi], r10
0x1800418ec  jz      short loc_1800418F5
0x1800418ee  or      eax, 2
0x1800418f1  mov     [r14+40h], eax
0x1800418f5  test    [rsi], r11
0x1800418f8  jz      short loc_180041901
0x1800418fa  or      eax, 4
0x1800418fd  mov     [r14+40h], eax
0x180041901  mov     rcx, 1000000000000000h
0x18004190b  test    [rsi], rcx
0x18004190e  jz      short loc_180041917
0x180041910  or      eax, 10h
0x180041913  mov     [r14+40h], eax
0x180041917  mov     rcx, 800000000000000h
0x180041921  test    [rsi], rcx
0x180041924  jz      short loc_18004192D
0x180041926  or      eax, 8
0x180041929  mov     [r14+40h], eax
0x18004192d  cmp     dword ptr [rsi+0BCh], 1
0x180041934  jnz     short loc_18004193D
0x180041936  or      eax, 20h
0x180041939  mov     [r14+40h], eax
0x18004193d  test    [rsi], r9
0x180041940  mov     eax, r8d
0x180041943  setnz   al
0x180041946  mov     [r14+3Ch], eax
0x18004194a  cmp     [rsi], r8
0x18004194d  jge     loc_180041D53
0x180041953  or      dword ptr [r14+44h], 1
0x180041958  test    r15, r15
0x18004195b  jnz     loc_180041CAD
0x180041961  mov     r11d, [rsi+1Ch]
0x180041965  mov     r10, rdx
0x180041968  mov     rcx, [rsp+110h+var_D8]
0x18004196d  mov     rax, [r10]
0x180041970  mov     [rsp+110h+var_C0], rax
0x180041975  mov     r9, [rcx+18h]
0x180041979  mov     r8, [rcx+28h]
0x18004197d  mov     rdx, r9
0x180041980  mov     ecx, dword ptr [rbp+3Fh+var_C0+4]
0x180041983  cmp     rdx, r8
0x180041986  jnb     short loc_180041997
0x180041988  cmp     dword ptr [rdx], 2
0x18004198b  jz      loc_180041C0C
0x180041991  add     rdx, 40h ; '@'
0x180041995  jmp     short loc_180041983
0x180041997  test    byte ptr [rsi], 87h
0x18004199a  jz      loc_180041E16
0x1800419a0  mov     rdx, [rsp+110h+var_D8]
0x1800419a5  mov     rcx, r8
0x1800419a8  sub     rcx, r9
0x1800419ab  sar     rcx, 6
0x1800419af  movsxd  rax, dword ptr [rdx+10h]
0x1800419b3  cmp     rcx, rax
0x1800419b6  jge     loc_180041D26
0x1800419bc  lea     rax, [r8+40h]
0x1800419c0  mov     rcx, rdx
0x1800419c3  mov     [rdx+28h], rax
0x1800419c7  test    r8, r8
0x1800419ca  jz      loc_180041D26
0x1800419d0  mov     dword ptr [r8], 2
0x1800419d7  mov     rdx, r8
0x1800419da  mov     rax, [r10]
0x1800419dd  mov     [r8+8], rax
0x1800419e1  mov     [r8+4], r11d
0x1800419e5  movups  xmm0, xmmword ptr [rsi+20h]
0x1800419e9  movups  xmmword ptr [r8+10h], xmm0
0x1800419ee  movups  xmm1, xmmword ptr [rsi+30h]
0x1800419f2  movups  xmmword ptr [r8+20h], xmm1
0x1800419f7  movups  xmm0, xmmword ptr [rsi+40h]
0x1800419fb  movups  xmmword ptr [r8+30h], xmm0
0x180041a00  sub     rdx, [rcx+18h]
0x180041a04  sar     rdx, 6
0x180041a08  cmp     [rsp+110h+var_EF], 0
0x180041a0d  jz      short loc_180041A15
0x180041a0f  xor     eax, eax
0x180041a11  mov     [r8+30h], rax
0x180041a15  cmp     [rbp+3Fh+arg_20], 0
0x180041a19  jnz     short loc_180041A79
0x180041a1b  mov     eax, [rsi]
0x180041a1d  bt      rax, 18h
0x180041a22  jnb     short loc_180041A79
0x180041a24  mov     r9, [rsi+0C4h]
0x180041a2b  mov     r11, [rsi+30h]
0x180041a2f  mov     r10, r9
0x180041a32  movzx   eax, word ptr [rsi+4Ah]
0x180041a36  mov     rcx, r11
0x180041a39  shr     r10, 20h
0x180041a3d  shr     rcx, 20h
0x180041a41  and     eax, 3Fh
0x180041a44  jz      loc_180041C81
0x180041a4a  imul    eax, ecx
0x180041a4d  mov     ecx, r9d
0x180041a50  imul    rcx, rax
0x180041a54  mov     eax, r11d
0x180041a57  imul    rax, r10
0x180041a5b  cmp     rcx, rax
0x180041a5e  jz      short loc_180041A74
0x180041a60  and     dword ptr [r8+38h], 0FFC1FFFFh
0x180041a68  or      dword ptr [r8+38h], 10000h
0x180041a70  mov     [r8+20h], r9
0x180041a74  mov     rcx, [rsp+110h+var_D8]
0x180041a79  movzx   r8d, [rsp+110h+var_F0]
0x180041a7f  test    r8b, r8b
0x180041a82  jnz     loc_180041D49
0x180041a88  mov     [r14+20h], edx
0x180041a8c  test    r15, r15
0x180041a8f  jnz     loc_180041E51
0x180041a95  mov     r11d, [rsi+18h]
0x180041a99  lea     r15, [rsi+10h]
0x180041a9d  mov     r9, r15
0x180041aa0  test    r8b, r8b
0x180041aa3  jnz     short loc_180041ADB
0x180041aa5  mov     rdx, [rsp+110h+var_D8]
0x180041aaa  mov     rax, [r9]
  ... truncated ...
```
