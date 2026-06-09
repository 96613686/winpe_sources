# SdcCompat::SetDisplayConfigValidateParamsUserMode

- ea: `0x1800597c4`
- end: `0x18005a0c4`
- name: `SdcCompat::SetDisplayConfigValidateParamsUserMode`
- size: `2304`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800595c0`

## callees

- `0x1800597c4`
- `0x180065574`
- `0x1800958ac`
- `0x180095938`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserDisplayConfigGetDeviceInfo` at `0x1800599b5`
- `win32u!NtUserDisplayConfigGetDeviceInfo` at `0x1800599b5`
- `ntdll!RtlFreeHeap` at `0x1800599dd`
- `ntdll!RtlFreeHeap` at `0x1800599dd`
- `ntdll!RtlAllocateHeap` at `0x180059f15`
- `ntdll!RtlAllocateHeap` at `0x180059f15`

## pseudocode

```c
__int64 __fastcall SdcCompat::SetDisplayConfigValidateParamsUserMode(
        unsigned int a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        int a5)
{
  unsigned int v5; // r10d
  __int64 v6; // r15
  unsigned int v7; // r14d
  unsigned int v8; // ebx
  _DWORD *v10; // rbp
  __int64 j; // rax
  __int64 v12; // r14
  _DWORD *v13; // r13
  unsigned int m; // r15d
  unsigned int k; // r14d
  unsigned int v16; // r10d
  unsigned int v17; // r10d
  unsigned int v18; // edx
  unsigned int v19; // r13d
  __int64 v20; // r9
  __int64 v21; // r11
  int v22; // eax
  __int64 v23; // rsi
  unsigned int v24; // r11d
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  char v27; // r11
  bool v28; // bl
  int v29; // r10d
  int v30; // eax
  unsigned int v31; // ecx
  unsigned int v32; // r9d
  __int64 v33; // r11
  unsigned int v34; // ecx
  int v35; // ecx
  unsigned int v36; // eax
  _DWORD *v37; // r10
  int v38; // r9d
  unsigned int v39; // eax
  bool v40; // r11
  char v41; // r14
  int v42; // r9d
  int v43; // r9d
  bool v44; // zf
  unsigned int i; // ecx
  SIZE_T v46; // r14
  _DWORD *Heap; // rax
  bool v48; // r13
  int v49; // r10d
  unsigned int v50; // eax
  bool v51; // zf
  int v52; // edx
  int v53; // eax
  __int64 v54; // r13
  int v55; // eax
  int v56; // ecx
  __int64 v57; // r13
  int v58; // esi
  int v59; // eax
  bool v60; // zf
  char v61; // [rsp+20h] [rbp-A8h]
  char v62; // [rsp+21h] [rbp-A7h]
  bool v63; // [rsp+24h] [rbp-A4h]
  unsigned int v65; // [rsp+38h] [rbp-90h]
  __int64 v66; // [rsp+40h] [rbp-88h] BYREF
  unsigned int v67; // [rsp+48h] [rbp-80h]
  unsigned int v68; // [rsp+4Ch] [rbp-7Ch]
  unsigned int v69; // [rsp+50h] [rbp-78h]
  _DWORD v70[2]; // [rsp+58h] [rbp-70h] BYREF
  __int64 v71; // [rsp+60h] [rbp-68h]
  int v72; // [rsp+68h] [rbp-60h]
  __int128 v73; // [rsp+6Ch] [rbp-5Ch]

  v5 = (unsigned int)a3;
  v6 = a2;
  v65 = (unsigned int)a3;
  v7 = a1;
  v67 = a1;
  if ( (a5 & 0xC0000000) != 0 )
  {
    if ( (a5 & 0x80u) != 0 && ((a5 - 1073741952) & 0xBFFFFFFF) == 0 )
    {
      if ( a1 || a2 || (_DWORD)a3 || a4 )
        return (unsigned int)-1073741811;
      else
        return 0;
    }
    return (unsigned int)-1073741581;
  }
  if ( (a5 & 0xFFFD4000) != 0
    || (a5 & 0xC0) == 0
    || (a5 & 0xC0) == 0xC0
    || (a5 & 0x180) == 0x100
    || (a5 & 0xA0) != 0xA0 && (a5 & 0x1000) != 0
    || (a5 & 0x2010) == 0x2000 )
  {
    return (unsigned int)-1073741581;
  }
  v8 = 0;
  if ( (a5 & 0x1F) != 0 )
  {
    if ( (a5 & 0x400) != 0 || (a5 & 0x20) != 0 || (a5 & 0x200) != 0 )
      return (unsigned int)-1073741581;
    if ( a4 )
      return (unsigned int)-1073741582;
    if ( !(_DWORD)a3 )
    {
      if ( (a5 & 0x10) == 0 )
      {
        if ( !a2 )
        {
          if ( !a1 )
            return v8;
          return (unsigned int)-1073741585;
        }
        return (unsigned int)-1073741584;
      }
      if ( (a5 & 0x800) == 0 )
      {
        if ( a2 )
        {
          if ( a1 )
          {
            for ( i = 0; i < v7; ++i )
            {
              v53 = *(_DWORD *)(v6 + 68) & 1;
              if ( (a5 & 0x8000) != 0 )
              {
                if ( v53
                  && (*(_WORD *)(v6 + 14) != 0xFFFF
                   || *(_WORD *)(v6 + 34) != 0xFFFF
                   || *(unsigned __int16 *)(v6 + 32) != 0xFFFF
                   || *(unsigned __int16 *)(v6 + 12) == 0xFFFF) )
                {
                  return (unsigned int)-1073741584;
                }
              }
              else if ( v53 && (*(_DWORD *)(v6 + 12) != -1 || *(_DWORD *)(v6 + 32) != -1) )
              {
                return (unsigned int)-1073741584;
              }
              v6 += 72;
            }
            return v8;
          }
          return (unsigned int)-1073741585;
        }
        return (unsigned int)-1073741584;
      }
      return (unsigned int)-1073741581;
    }
    return (unsigned int)-1073741583;
  }
  if ( (a5 & 0x20) == 0 || (a5 & 0x800) != 0 )
    return (unsigned int)-1073741581;
  if ( !a2 )
    return (unsigned int)-1073741584;
  if ( !a1 )
    return (unsigned int)-1073741585;
  if ( a4 )
  {
    if ( !(_DWORD)a3 )
      return (unsigned int)-1073741583;
  }
  else if ( (_DWORD)a3 )
  {
    return (unsigned int)-1073741583;
  }
  v10 = 0;
  if ( (a5 & 0x8000) != 0 )
  {
    LODWORD(v66) = 0;
    SdcCompat::EnforceSDCCloneSourceIndexCoherency(a1, a2, &v66);
    a2 = (unsigned int)v66;
    if ( (_DWORD)v66 != -1 )
      LogCodePointPacket(57, (unsigned int)v66, 0);
    v5 = v65;
  }
  if ( v5 )
  {
    v46 = 16LL * v5;
    Heap = RtlAllocateHeap(pUserHeap, 8u, v46);
    v10 = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    memset_0(Heap, 0, v46);
    v7 = v67;
  }
  v62 = 0;
  for ( j = 0; ; j = v68 + 1 )
  {
    v68 = j;
    if ( (unsigned int)j >= v7 )
      break;
    v12 = v6 + 72 * j;
    v13 = (_DWORD *)(v12 + 68);
    if ( (a5 & 0x8000) != 0 && (*v13 & 0xFFFFFFE2) != 0
      || (*(_BYTE *)v13 & 0x10) != 0 && ((a5 & 0x20000) == 0 || !*(_DWORD *)(v12 + 48) || !*(_DWORD *)(v12 + 52)) )
    {
      goto LABEL_34;
    }
    if ( (*(_BYTE *)v13 & 1) == 0 )
      goto LABEL_115;
    v71 = *(_QWORD *)v12;
    v72 = *(_DWORD *)(v12 + 28);
    v73 = 0;
    v70[0] = -13;
    v70[1] = 36;
    if ( (int)NtUserDisplayConfigGetDeviceInfo(v70, a2) < 0 )
      goto LABEL_34;
    v27 = BYTE12(v73) & 1;
    v28 = (BYTE12(v73) & 2) != 0;
    v61 = BYTE12(v73) & 1;
    v63 = v28;
    if ( (BYTE12(v73) & 1) != 0 && (BYTE12(v73) & 2) != 0 )
      *v13 &= ~8u;
    else
      *v13 |= 8u;
    v29 = a5 & 0x8000;
    v30 = *v13;
    if ( (a5 & 0x8000) != 0 )
    {
      if ( v27 && (v30 & 4) != 0 )
        goto LABEL_34;
      a2 = 0xFFFF;
      if ( *(_WORD *)(v12 + 14) == 0xFFFF )
        v31 = -1;
      else
        v31 = *(unsigned __int16 *)(v12 + 14);
    }
    else
    {
      if ( (v30 & 4) != 0 )
        goto LABEL_34;
      v31 = *(_DWORD *)(v12 + 12);
      a2 = 0xFFFF;
    }
    if ( v31 == -1 )
    {
      if ( (a5 & 0x8000) != 0 )
      {
        v49 = *(unsigned __int16 *)(v12 + 12);
        if ( v49 == 0xFFFF )
          goto LABEL_87;
        v50 = v68;
        v63 = v28;
        v8 = 0;
        v61 = v27;
        if ( !v68 )
        {
LABEL_200:
          v48 = v63;
          goto LABEL_201;
        }
        a2 = 0;
        while ( 1 )
        {
          if ( (*v13 & 1) != 0 )
          {
            if ( *(unsigned __int16 *)(v6 + 72LL * (unsigned int)a2 + 12) == v49 )
            {
              if ( ((*(_BYTE *)(v6 + 72LL * (unsigned int)a2 + 68) ^ (unsigned __int8)*v13) & 8) == 0 )
              {
                v48 = v63;
                if ( !v63
                  || *(_DWORD *)(v6 + 72LL * (unsigned int)a2) == *(_DWORD *)v12
                  && *(_DWORD *)(v6 + 72LL * (unsigned int)a2 + 4) == *(_DWORD *)(v12 + 4) )
                {
LABEL_201:
                  v29 = a5 & 0x8000;
                  goto LABEL_89;
                }
              }
              goto LABEL_87;
            }
            v50 = v68;
          }
          a2 = (unsigned int)(a2 + 1);
          if ( (unsigned int)a2 >= v50 )
            goto LABEL_200;
        }
      }
      v63 = v28;
      v8 = 0;
      v48 = v63;
      v61 = v27;
LABEL_89:
      v33 = a4;
      a3 = 0;
      v32 = v65;
      v62 = 1;
    }
    else
    {
      v32 = v65;
      if ( v31 >= v65 )
        goto LABEL_64;
      if ( (a5 & 0x8000) != 0 && *(unsigned __int16 *)(v12 + 12) != 0xFFFF )
        goto LABEL_87;
      v33 = a4;
      a3 = (_DWORD *)(a4 + ((unsigned __int64)v31 << 6));
      if ( *(_DWORD *)v12 != a3[2]
        || *(_DWORD *)(v12 + 4) != a3[3]
        || *(_DWORD *)(v12 + 8) != a3[1]
        || *a3 != 1
        || (unsigned int)(a3[6] - 1) <= 2 )
      {
        goto LABEL_87;
      }
      a2 = 16LL * v31;
      *(_DWORD *)((char *)v10 + a2) |= v28 ? 0x200000 : 0x100000;
      if ( ((*(_DWORD *)(v12 + 40) - 2) & 0xFFFFFFFD) == 0 )
        *(_DWORD *)((char *)v10 + a2) |= 0x2000000u;
      ++*(_WORD *)((char *)v10 + a2);
      *(_QWORD *)((char *)v10 + a2 + 8) = *((_QWORD *)a3 + 1);
      *(_DWORD *)((char *)v10 + a2 + 4) = a3[1];
      v34 = *(_DWORD *)((char *)v10 + a2) & 0xFF7FFFFF | (!v28 << 23);
      *(_DWORD *)((char *)v10 + a2) = v34;
      if ( a3[7] || a3[8] )
        v35 = v34 | 0x20000;
      else
        v35 = v34 | 0x10000;
      *(_DWORD *)((char *)v10 + a2) = v35;
      if ( (*(_BYTE *)v13 & 4) != 0 )
      {
        if ( (v35 & 0x400000) != 0 )
          goto LABEL_34;
        v35 |= 0x400000u;
        *(_DWORD *)((char *)v10 + a2) = v35;
      }
      if ( (v35 & 0x300000) == 0x300000 )
        goto LABEL_87;
      v48 = v28;
      v8 = 0;
    }
    if ( v29 )
    {
      if ( *(_WORD *)(v12 + 34) == 0xFFFF )
        v36 = -1;
      else
        v36 = *(unsigned __int16 *)(v12 + 34);
    }
    else
    {
      v36 = *(_DWORD *)(v12 + 32);
    }
    if ( v36 == -1 )
    {
      v37 = 0;
      v38 = *(_DWORD *)(v12 + 56);
      v69 = *(_DWORD *)(v12 + 48);
      LODWORD(v66) = *(_DWORD *)(v12 + 52);
    }
    else
    {
      if ( v36 >= v32 )
        goto LABEL_64;
      if ( !a3 )
        goto LABEL_34;
      v37 = (_DWORD *)(v33 + ((unsigned __int64)v36 << 6));
      if ( *(_DWORD *)(v12 + 20) != v37[2]
        || *(_DWORD *)(v12 + 24) != v37[3]
        || *(_DWORD *)(v12 + 28) != v37[1]
        || *v37 != 2 )
      {
        goto LABEL_87;
      }
      v38 = v37[15];
      a2 = 16LL * v36;
      v69 = v37[8];
      LODWORD(v66) = v37[9];
      ++*(_WORD *)((char *)v10 + a2);
      *(_QWORD *)((char *)v10 + a2 + 8) = *((_QWORD *)v37 + 1);
      *(_DWORD *)((char *)v10 + a2 + 4) = v37[1];
      *(_DWORD *)((char *)v10 + a2) = *(_DWORD *)((char *)v10 + a2) & 0xFF7FFFFF | (!v48 << 23) | 0x40000;
    }
    if ( (a5 & 0x8000) != 0 )
    {
      a2 = 0;
      v39 = -1;
      if ( *(_WORD *)(v12 + 32) != 0xFFFF )
        v39 = *(unsigned __int16 *)(v12 + 32);
      if ( v39 == -1 )
      {
        v40 = v63;
        v41 = v61;
      }
      else
      {
        if ( v39 >= v65 )
          goto LABEL_64;
        a2 = v33 + ((unsigned __int64)v39 << 6);
        v54 = v39;
        if ( *(_DWORD *)(v12 + 20) != *(_DWORD *)(a2 + 8)
          || *(_DWORD *)(v12 + 24) != *(_DWORD *)(a2 + 12)
          || *(_DWORD *)(v12 + 28) != *(_DWORD *)(a2 + 4)
          || *(_DWORD *)a2 != 3 )
        {
          goto LABEL_87;
        }
        v41 = v61;
        v40 = v63;
        if ( v61 && v63 || !a3 )
          goto LABEL_34;
        if ( *(_DWORD *)(a2 + 44) )
          goto LABEL_87;
        if ( *(_DWORD *)(a2 + 40) )
          goto LABEL_87;
        if ( *(_DWORD *)(a2 + 48) != a3[4] )
          goto LABEL_87;
        if ( *(_DWORD *)(a2 + 52) != a3[5] )
          goto LABEL_87;
        v55 = *(_DWORD *)(a2 + 36);
        if ( *(_DWORD *)(a2 + 28) >= v55 )
          goto LABEL_87;
        v56 = *(_DWORD *)(a2 + 32);
        if ( *(_DWORD *)(a2 + 24) >= v56
          || *(int *)(a2 + 28) < 0
          || *(int *)(a2 + 24) < 0
          || v55 > *(_DWORD *)(a2 + 20)
          || v56 > *(_DWORD *)(a2 + 16) )
        {
          goto LABEL_87;
        }
        v57 = 4 * v54;
        ++LOWORD(v10[v57]);
        *(_QWORD *)&v10[v57 + 2] = *(_QWORD *)(a2 + 8);
        v10[v57 + 1] = *(_DWORD *)(a2 + 4);
        v10[v57] = v10[v57] & 0xFF7FFFFF | (!v63 << 23) | 0x80000;
      }
      if ( v41 && v40 )
      {
        if ( a2 )
          goto LABEL_34;
        if ( !a3 )
          goto LABEL_227;
      }
      else
      {
        if ( !a3 )
        {
          if ( a2 )
            goto LABEL_34;
LABEL_227:
          v51 = v37 == 0;
LABEL_118:
          if ( !v51 )
            goto LABEL_34;
          goto LABEL_109;
        }
        if ( !v37 )
        {
          v51 = a2 == 0;
          goto LABEL_118;
        }
      }
    }
LABEL_109:
    if ( v69 )
    {
      if ( !(_DWORD)v66 )
        goto LABEL_87;
      v42 = v38 - 1;
      if ( !v42 )
        goto LABEL_115;
      v43 = v42 - 1;
      if ( !v43 )
        goto LABEL_115;
      v44 = v43 == 1;
    }
    else
    {
      if ( (_DWORD)v66 )
        goto LABEL_87;
      v44 = v38 == 0;
    }
    if ( !v44 )
      goto LABEL_87;
LABEL_115:
    v7 = v67;
  }
  v17 = v65;
  if ( !v65 )
    goto LABEL_35;
  if ( (a5 & 0x8000) == 0 )
  {
    LOBYTE(a3) = v62;
    v8 = SdcCompat::ValidateSDCv1ModeInfoArray(v10, v65, a3);
    goto LABEL_35;
  }
  v18 = 0;
  v19 = 0;
  v67 = 0;
  for ( k = 0; ; ++k )
  {
LABEL_46:
    if ( k >= v17 )
    {
      if ( !v18 || v19 == 1 || v62 && v19 <= 1 )
        goto LABEL_35;
LABEL_64:
      v8 = -1073741583;
      goto LABEL_35;
    }
    v20 = 2LL * k;
    v21 = k;
    v66 = k;
    v22 = v10[4 * k];
    if ( (_WORD)v22 )
      break;
  }
  if ( (v22 & 0x40000) == 0 && (v22 & 0x80000) == 0 )
  {
    if ( (v22 & 0x30000) == 0 )
    {
      v8 = -1073741811;
      goto LABEL_35;
    }
    if ( (v22 & 0x1000000) == 0 )
    {
      v67 = v18 + 1;
      if ( (v22 & 0x10000) != 0 )
        ++v19;
    }
    if ( (v22 & 0x100000) == 0 )
      goto LABEL_38;
  }
  if ( (unsigned __int16)v22 <= 1u )
  {
LABEL_38:
    for ( m = ++k; ; ++m )
    {
      if ( m >= v17 )
      {
        v18 = v67;
        goto LABEL_46;
      }
      v16 = v10[4 * m];
      v69 = (unsigned __int16)v16;
      if ( (_WORD)v16 )
      {
        if ( v10[2 * v20 + 2] == v10[4 * m + 2] && v10[2 * v20 + 3] == v10[4 * m + 3] )
        {
          v23 = a4;
          if ( v10[2 * v20 + 1] == v10[4 * m + 1] )
          {
            v52 = *(_DWORD *)((v21 << 6) + a4);
            if ( v52 == *(_DWORD *)(((unsigned __int64)m << 6) + a4) && (v52 != 1 || (v10[2 * v20] & 0x800000) != 0) )
              goto LABEL_87;
          }
        }
        else
        {
          v23 = a4;
        }
        v24 = v10[2 * v20];
        if ( (v24 & 0x1000000) == 0 )
        {
          v25 = (unsigned __int64)m << 6;
          if ( *(_DWORD *)(v25 + v23) == 1 )
          {
            v26 = v66 << 6;
            if ( *(_DWORD *)((v66 << 6) + v23) == 1
              && *(_DWORD *)(v25 + v23 + 28) == *(_DWORD *)(v26 + v23 + 28)
              && *(_DWORD *)(v25 + v23 + 32) == *(_DWORD *)(v26 + v23 + 32) )
            {
              v58 = (v24 >> 20) & 1;
              if ( v58 != ((v16 >> 20) & 1) || ((v16 ^ v24) & 0x200000) != 0 )
                goto LABEL_87;
              if ( v69 > 1 )
                break;
              v59 = *(_DWORD *)(v26 + a4 + 20);
              if ( ((v16 ^ v24) & 0x2000000) != 0 )
              {
                if ( *(_DWORD *)(v25 + a4 + 16) != v59 )
                  goto LABEL_87;
                v60 = *(_DWORD *)(v25 + a4 + 20) == *(_DWORD *)(v26 + a4 + 16);
              }
              else
              {
                if ( *(_DWORD *)(v25 + a4 + 20) != v59 )
                  goto LABEL_87;
                v60 = *(_DWORD *)(v25 + a4 + 16) == *(_DWORD *)(v26 + a4 + 16);
              }
              if ( !v60 || *(_DWORD *)(v25 + a4 + 24) != *(_DWORD *)(v26 + a4 + 24) )
              {
LABEL_87:
                v8 = -1073741582;
                goto LABEL_35;
              }
              if ( v58 )
              {
                if ( (v16 & v24 & 0x800000) == 0 )
                  goto LABEL_87;
              }
              else if ( v10[2 * v20 + 2] != v10[4 * m + 2] || v10[2 * v20 + 3] != v10[4 * m + 3] )
              {
                goto LABEL_87;
              }
              v10[4 * m] = v16 | 0x1000000;
            }
          }
        }
        v21 = v66;
      }
      v17 = v65;
    }
  }
LABEL_34:
  v8 = -1073741584;
LABEL_35:
  if ( v10 )
    RtlFreeHeap(pUserHeap, 0, v10);
  return v8;
}

```

## disassembly

```asm
0x1800597c4  mov     [rsp+arg_0], rbx
0x1800597c9  push    rbp
0x1800597ca  push    rsi
0x1800597cb  push    rdi
0x1800597cc  push    r12
0x1800597ce  push    r13
0x1800597d0  push    r14
0x1800597d2  push    r15
0x1800597d4  sub     rsp, 90h
0x1800597db  mov     rax, cs:__security_cookie
0x1800597e2  xor     rax, rsp
0x1800597e5  mov     [rsp+0C8h+var_48], rax
0x1800597ed  mov     esi, [rsp+0C8h+arg_20]
0x1800597f4  mov     r10d, r8d
0x1800597f7  mov     [rsp+0C8h+var_98], r9
0x1800597fc  mov     r15, rdx
0x1800597ff  mov     [rsp+0C8h+var_90], r8d
0x180059804  mov     r14d, ecx
0x180059807  mov     [rsp+0C8h+var_80], ecx
0x18005980b  test    esi, 0C0000000h
0x180059811  jnz     loc_180059E2F
0x180059817  test    esi, 0FFFD4000h
0x18005981d  jnz     short loc_180059853
0x18005981f  mov     eax, esi
0x180059821  mov     ecx, 0C0h
0x180059826  and     eax, ecx
0x180059828  jz      short loc_180059853
0x18005982a  cmp     eax, ecx
0x18005982c  jz      short loc_180059853
0x18005982e  mov     eax, esi
0x180059830  and     eax, 180h
0x180059835  cmp     eax, 100h
0x18005983a  jz      short loc_180059853
0x18005983c  mov     eax, esi
0x18005983e  and     eax, 0A0h
0x180059843  cmp     al, 0A0h
0x180059845  setnz   cl
0x180059848  bt      esi, 0Ch
0x18005984c  setb    al
0x18005984f  test    al, cl
0x180059851  jz      short loc_180059885
0x180059853  mov     ebx, 0C00000F3h
0x180059858  mov     eax, ebx
0x18005985a  mov     rcx, [rsp+0C8h+var_48]
0x180059862  xor     rcx, rsp; StackCookie
0x180059865  call    __security_check_cookie
0x18005986a  mov     rbx, [rsp+0C8h+arg_0]
0x180059872  add     rsp, 90h
0x180059879  pop     r15
0x18005987b  pop     r14
0x18005987d  pop     r13
0x18005987f  pop     r12
0x180059881  pop     rdi
0x180059882  pop     rsi
0x180059883  pop     rbp
0x180059884  retn
0x180059885  mov     eax, esi
0x180059887  and     eax, 2010h
0x18005988c  cmp     eax, 2000h
0x180059891  jz      short loc_180059853
0x180059893  xor     edi, edi
0x180059895  mov     ebx, edi
0x180059897  test    sil, 1Fh
0x18005989b  jz      short loc_1800598E7
0x18005989d  bt      esi, 0Ah
0x1800598a1  jb      short loc_180059853
0x1800598a3  test    sil, 20h
0x1800598a7  jnz     short loc_180059853
0x1800598a9  bt      esi, 9
0x1800598ad  jb      short loc_180059853
0x1800598af  test    r9, r9
0x1800598b2  jnz     loc_180059E76
0x1800598b8  test    r8d, r8d
0x1800598bb  jnz     loc_180059E80
0x1800598c1  test    sil, 10h
0x1800598c5  jnz     loc_180059E8A
0x1800598cb  test    r15, r15
0x1800598ce  jnz     loc_180059EB8
0x1800598d4  test    r14d, r14d
0x1800598d7  jz      loc_180059858
0x1800598dd  mov     ebx, 0C00000EFh
0x1800598e2  jmp     loc_180059858
0x1800598e7  test    sil, 20h
0x1800598eb  jz      loc_180059853
0x1800598f1  bt      esi, 0Bh
0x1800598f5  jb      loc_180059853
0x1800598fb  test    r15, r15
0x1800598fe  jz      loc_180059EB8
0x180059904  test    r14d, r14d
0x180059907  jz      short loc_1800598DD
0x180059909  test    r9, r9
0x18005990c  jnz     loc_180059EC2
0x180059912  test    r8d, r8d
0x180059915  jnz     loc_180059E80
0x18005991b  mov     r13d, esi
0x18005991e  mov     rbp, rdi
0x180059921  and     r13d, 8000h
0x180059928  mov     [rsp+0C8h+var_A0], r13d
0x18005992d  jnz     loc_180059ECC
0x180059933  test    r10d, r10d
0x180059936  jnz     loc_180059EFF
0x18005993c  and     esi, 20000h
0x180059942  mov     [rsp+0C8h+var_A7], dil
0x180059947  mov     eax, edi
0x180059949  mov     r12d, 1
0x18005994f  mov     [rsp+0C8h+var_7C], eax
0x180059953  cmp     eax, r14d
0x180059956  jnb     loc_180059A27
0x18005995c  lea     rcx, [rax+rax*8]
0x180059960  lea     r14, [r15+rcx*8]
0x180059964  lea     r13, [r14+44h]
0x180059968  cmp     [rsp+0C8h+var_A0], edi
0x18005996c  jnz     loc_180059F31
0x180059972  test    byte ptr [r13+0], 10h
0x180059977  jnz     loc_180059F44
0x18005997d  test    [r13+0], r12b
0x180059981  jz      loc_180059DCD
0x180059987  mov     rax, [r14]
0x18005998a  lea     rcx, [rsp+0C8h+var_70]
0x18005998f  mov     [rsp+0C8h+var_68], rax
0x180059994  xorps   xmm0, xmm0
0x180059997  mov     eax, [r14+1Ch]
0x18005999b  mov     [rsp+0C8h+var_60], eax
0x18005999f  movdqu  [rsp+0C8h+var_5C], xmm0
0x1800599a5  mov     [rsp+0C8h+var_70], 0FFFFFFF3h
0x1800599ad  mov     [rsp+0C8h+var_6C], 24h ; '$'
0x1800599b5  call    cs:__imp_NtUserDisplayConfigGetDeviceInfo
0x1800599bb  test    eax, eax
0x1800599bd  jns     loc_180059B32
0x1800599c3  mov     ebx, 0C00000F0h
0x1800599c8  test    rbp, rbp
0x1800599cb  jz      loc_180059858
0x1800599d1  mov     rcx, cs:pUserHeap; HeapHandle
0x1800599d8  mov     r8, rbp; P
0x1800599db  xor     edx, edx; Flags
0x1800599dd  call    cs:__imp_RtlFreeHeap
0x1800599e3  jmp     loc_180059858
0x1800599e8  cmp     ecx, r12d
0x1800599eb  ja      short loc_1800599C3
0x1800599ed  lea     r15d, [r14+1]
0x1800599f1  mov     r14d, r15d
0x1800599f4  cmp     r15d, r10d
0x1800599f7  jnb     short loc_180059A21
0x1800599f9  mov     r8d, r15d
0x1800599fc  add     r8, r8
0x1800599ff  mov     ecx, r15d
0x180059a02  mov     r10d, [rbp+r8*8+0]
0x180059a07  movzx   eax, r10w
0x180059a0b  mov     [rsp+0C8h+var_78], eax
0x180059a0f  test    eax, eax
0x180059a11  jnz     loc_180059A97
0x180059a17  mov     r10d, [rsp+0C8h+var_90]
0x180059a1c  add     r15d, r12d
0x180059a1f  jmp     short loc_1800599F4
0x180059a21  mov     edx, [rsp+0C8h+var_80]
0x180059a25  jmp     short loc_180059A47
0x180059a27  mov     r10d, [rsp+0C8h+var_90]
0x180059a2c  test    r10d, r10d
0x180059a2f  jz      short loc_1800599C8
0x180059a31  cmp     [rsp+0C8h+var_A0], edi
0x180059a35  jz      loc_18005A06C
0x180059a3b  mov     edx, edi
0x180059a3d  mov     r13d, edi
0x180059a40  mov     [rsp+0C8h+var_80], edx
0x180059a44  mov     r14d, edi
0x180059a47  cmp     r14d, r10d
0x180059a4a  jnb     loc_180059B07
0x180059a50  mov     r9d, r14d
0x180059a53  add     r9, r9
0x180059a56  mov     r11d, r14d
0x180059a59  mov     [rsp+0C8h+var_88], r11
0x180059a5e  mov     eax, [rbp+r9*8+0]
0x180059a63  movzx   ecx, ax
0x180059a66  test    ecx, ecx
0x180059a68  jz      loc_180059AFF
0x180059a6e  bt      eax, 12h
0x180059a72  jb      loc_1800599E8
0x180059a78  bt      eax, 13h
0x180059a7c  jb      loc_1800599E8
0x180059a82  test    eax, 30000h
0x180059a87  jnz     loc_180059E0A
0x180059a8d  mov     ebx, 0C000000Dh
0x180059a92  jmp     loc_1800599C8
0x180059a97  mov     eax, [rbp+r9*8+8]
0x180059a9c  cmp     eax, [rbp+r8*8+8]
0x180059aa1  jnz     loc_18005A0BA
0x180059aa7  mov     eax, [rbp+r8*8+0Ch]
0x180059aac  cmp     [rbp+r9*8+0Ch], eax
0x180059ab1  jnz     loc_18005A0BA
0x180059ab7  mov     eax, [rbp+r8*8+4]
0x180059abc  mov     rsi, [rsp+0C8h+var_98]
0x180059ac1  cmp     [rbp+r9*8+4], eax
0x180059ac6  jz      loc_18005A083
0x180059acc  mov     r11d, [rbp+r9*8+0]
0x180059ad1  bt      r11d, 18h
0x180059ad6  jb      short loc_180059AF5
0x180059ad8  shl     rcx, 6
0x180059adc  cmp     [rcx+rsi], r12d
0x180059ae0  jnz     short loc_180059AF5
0x180059ae2  mov     rdx, [rsp+0C8h+var_88]
0x180059ae7  shl     rdx, 6
0x180059aeb  cmp     [rdx+rsi], r12d
0x180059aef  jz      loc_18009FB87
0x180059af5  mov     r11, [rsp+0C8h+var_88]
0x180059afa  jmp     loc_180059A17
0x180059aff  inc     r14d
0x180059b02  jmp     loc_180059A47
0x180059b07  test    edx, edx
0x180059b09  jz      loc_1800599C8
0x180059b0f  cmp     r13d, r12d
0x180059b12  jz      loc_1800599C8
0x180059b18  cmp     [rsp+0C8h+var_A7], dil
0x180059b1d  jz      short loc_180059B28
0x180059b1f  cmp     r13d, r12d
0x180059b22  jbe     loc_1800599C8
0x180059b28  mov     ebx, 0C00000F1h
0x180059b2d  jmp     loc_1800599C8
0x180059b32  mov     ebx, dword ptr [rsp+0C8h+var_5C+0Ch]
0x180059b36  mov     r11b, byte ptr [rsp+0C8h+var_5C+0Ch]
0x180059b3b  shr     ebx, 1
0x180059b3d  and     r11b, r12b
0x180059b40  and     bl, r12b
0x180059b43  mov     [rsp+0C8h+var_A8], r11b
0x180059b48  mov     [rsp+0C8h+var_A4], ebx
0x180059b4c  test    r11b, r11b
0x180059b4f  jnz     loc_180059F65
0x180059b55  or      dword ptr [r13+0], 8
0x180059b5a  mov     r10d, [rsp+0C8h+var_A0]
0x180059b5f  mov     eax, [r13+0]
0x180059b63  test    r10d, r10d
0x180059b66  jz      loc_180059F8E
0x180059b6c  test    r11b, r11b
0x180059b6f  jnz     loc_180059F77
0x180059b75  mov     edx, 0FFFFh
0x180059b7a  cmp     [r14+0Eh], dx
0x180059b7f  jnz     loc_180059F84
0x180059b85  or      ecx, 0FFFFFFFFh
0x180059b88  cmp     ecx, 0FFFFFFFFh
0x180059b8b  jz      loc_180059FD1
0x180059b91  mov     r9d, [rsp+0C8h+var_90]
0x180059b96  cmp     ecx, r9d
0x180059b99  jnb     short loc_180059B28
0x180059b9b  test    r10d, r10d
0x180059b9e  jz      short loc_180059BAD
0x180059ba0  movzx   eax, word ptr [r14+0Ch]
0x180059ba5  cmp     eax, edx
0x180059ba7  jnz     loc_180059C80
0x180059bad  mov     r11, [rsp+0C8h+var_98]
0x180059bb2  mov     r8d, ecx
0x180059bb5  shl     r8, 6
0x180059bb9  add     r8, r11
0x180059bbc  mov     edx, ecx
0x180059bbe  mov     eax, [r8+8]
0x180059bc2  cmp     [r14], eax
0x180059bc5  jnz     loc_180059C80
0x180059bcb  mov     eax, [r8+0Ch]
0x180059bcf  cmp     [r14+4], eax
0x180059bd3  jnz     loc_180059C80
0x180059bd9  mov     eax, [r8+4]
0x180059bdd  cmp     [r14+8], eax
0x180059be1  jnz     loc_180059C80
0x180059be7  cmp     [r8], r12d
0x180059bea  jnz     loc_180059C80
0x180059bf0  mov     eax, [r8+18h]
0x180059bf4  sub     eax, r12d
0x180059bf7  cmp     eax, 2
0x180059bfa  jbe     loc_180059C80
0x180059c00  shl     rdx, 4
0x180059c04  mov     al, bl
0x180059c06  neg     al
0x180059c08  mov     eax, 100000h
0x180059c0d  sbb     ecx, ecx
0x180059c0f  and     ecx, eax
0x180059c11  add     ecx, eax
0x180059c13  or      [rdx+rbp], ecx
0x180059c16  mov     eax, [r14+28h]
0x180059c1a  sub     eax, 2
0x180059c1d  test    eax, 0FFFFFFFDh
0x180059c22  jz      loc_180059FA4
0x180059c28  add     [rdx+rbp], r12w
0x180059c2d  mov     rax, [r8+8]
0x180059c31  mov     [rdx+rbp+8], rax
0x180059c36  mov     eax, [r8+4]
0x180059c3a  mov     [rdx+rbp+4], eax
0x180059c3e  mov     eax, [rdx+rbp]
0x180059c41  btr     eax, 17h
0x180059c45  movzx   ecx, bl
0x180059c48  xor     ecx, r12d
0x180059c4b  shl     ecx, 17h
0x180059c4e  or      ecx, eax
0x180059c50  mov     [rdx+rbp], ecx
0x180059c53  cmp     [r8+1Ch], edi
0x180059c57  jnz     short loc_180059C8A
0x180059c59  cmp     [r8+20h], edi
0x180059c5d  jnz     short loc_180059C8A
0x180059c5f  bts     ecx, 10h
0x180059c63  mov     [rdx+rbp], ecx
0x180059c66  test    byte ptr [r13+0], 4
0x180059c6b  jnz     loc_180059FAE
0x180059c71  mov     eax, 300000h
  ... truncated ...
```
