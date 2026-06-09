# TdhApplyPayloadFilter

- ea: `0x1800286b0`
- end: `0x180028ebe`
- name: `TdhApplyPayloadFilter`
- size: `2062`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, void *, char, char, __int64, _BYTE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800207c0`
- `0x180023b05`
- `0x180028114`
- `0x180028604`
- `0x1800286b0`
- `0x180049f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x1800287f6`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x180028871`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x1800287f6`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x180028871`
- `ntdll!RtlLengthRequiredSid` at `0x180028b2e`
- `ntdll!RtlLengthRequiredSid` at `0x180028b2e`
- `ntdll!RtlSubAuthorityCountSid` at `0x180028aef`
- `ntdll!RtlSubAuthorityCountSid` at `0x180028b0c`
- `ntdll!RtlSubAuthorityCountSid` at `0x180028aef`
- `ntdll!RtlSubAuthorityCountSid` at `0x180028b0c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028812`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028889`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028812`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028889`

## pseudocode

```c
__int64 __fastcall TdhApplyPayloadFilter(
        unsigned __int16 *a1,
        unsigned int a2,
        void *a3,
        char a4,
        char a5,
        __int64 a6,
        _BYTE *a7)
{
  char v9; // r11
  __int64 v10; // rax
  __int64 v11; // rsi
  unsigned int v12; // r8d
  unsigned int v13; // edx
  bool v14; // zf
  unsigned int v15; // edx
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  char *v25; // r12
  unsigned int v26; // eax
  __int64 v27; // r9
  __int64 v28; // rdx
  unsigned int v29; // r8d
  unsigned int v30; // r14d
  char *v31; // r15
  _BYTE *v32; // rcx
  char *v33; // r10
  unsigned int v34; // eax
  unsigned int v35; // r11d
  char v36; // al
  __int64 v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rcx
  ULONG v40; // ecx
  int v42; // edx
  void *v43; // rdi
  PUCHAR v44; // rax
  __int64 v45; // r9
  unsigned int v46; // ecx
  _WORD *v47; // rdx
  unsigned int v48; // ecx
  unsigned int v49; // edi
  unsigned int v50; // r9d
  unsigned int v51; // ecx
  _BYTE *v52; // rax
  unsigned int v53; // ecx
  unsigned int v54; // edi
  unsigned int v55; // ecx
  char *v56; // r10
  __int64 v57; // r11
  unsigned __int16 *v58; // r14
  char v59; // si
  char v60; // di
  unsigned int v61; // r8d
  unsigned __int16 *v62; // r12
  char v63; // r13
  char v64; // cl
  unsigned int v65; // r15d
  __int16 v66; // dx
  __int64 v67; // rcx
  char v68; // [rsp+30h] [rbp+0h] BYREF
  char v69; // [rsp+31h] [rbp+1h]
  char v70; // [rsp+32h] [rbp+2h]
  int v71; // [rsp+34h] [rbp+4h]
  unsigned int v72; // [rsp+38h] [rbp+8h]
  unsigned int v73; // [rsp+3Ch] [rbp+Ch]
  unsigned int v74; // [rsp+40h] [rbp+10h]
  _BYTE *v75; // [rsp+48h] [rbp+18h]
  char v76; // [rsp+50h] [rbp+20h]
  ULONG SubAuthorityCount[2]; // [rsp+58h] [rbp+28h] BYREF
  __int64 v78; // [rsp+60h] [rbp+30h]
  char *v79; // [rsp+68h] [rbp+38h]
  char *v80; // [rsp+70h] [rbp+40h]
  char *v81; // [rsp+78h] [rbp+48h]
  unsigned __int16 v82; // [rsp+80h] [rbp+50h]
  unsigned int v83; // [rsp+84h] [rbp+54h]
  unsigned int v84; // [rsp+88h] [rbp+58h]
  __int64 v85; // [rsp+90h] [rbp+60h]
  __int64 v86; // [rsp+98h] [rbp+68h]
  _WORD *v87; // [rsp+A0h] [rbp+70h]
  _BYTE *v88; // [rsp+A8h] [rbp+78h]

  v79 = 0;
  *(_QWORD *)SubAuthorityCount = 0;
  v68 = 0;
  if ( a2 > 0x80 )
    return 3221225485LL;
  v82 = *a1;
  v9 = *((_BYTE *)a1 + 2);
  v76 = v9;
  v10 = *(_QWORD *)(a6 + 8);
  if ( !_bittest64(&v10, v82 % 0x3Fu) )
    goto LABEL_119;
  v11 = a6 + *(unsigned __int16 *)(a6 + 32);
  v12 = 0;
  v13 = *(unsigned __int16 *)(a6 + 34) / 0xCu;
  while ( 1 )
  {
    v75 = (_BYTE *)v11;
    v86 = v11;
    v14 = v12 == v13;
    if ( v12 >= v13 )
      break;
    if ( *(_WORD *)v11 == v82 && *(_BYTE *)(v11 + 2) == v9 )
    {
      v14 = v12 == v13;
      break;
    }
    if ( *(unsigned __int8 *)(v11 + 3) >= (unsigned int)*(_WORD *)(v11 + 6) )
      return 3221225485LL;
    v11 += 12;
    ++v12;
  }
  if ( v14 )
  {
LABEL_119:
    *a7 = 1;
    return 0;
  }
  v79 = 0;
  v15 = 16 * a2;
  LODWORD(v80) = 16 * a2;
  v73 = *(unsigned __int16 *)(v11 + 6);
  v16 = 4 * v73;
  v81 = 0;
  v17 = v16 + 15;
  if ( v16 + 15 < v16 )
    v17 = 0xFFFFFFFFFFFFFF0LL;
  v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
  v19 = alloca(v18);
  v20 = alloca(v18);
  v81 = &v68;
  v71 = 16 * a2;
  if ( a4 )
  {
    v21 = v15 + 15LL;
    if ( v21 <= v15 )
      v21 = 0xFFFFFFFFFFFFFF0LL;
    v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
    v23 = alloca(v22);
    v24 = alloca(v22);
    v25 = &v68;
    v79 = &v68;
  }
  else
  {
    v25 = v79;
  }
  v71 = -1073741811;
  if ( a4 )
  {
    memcpy_0(v25, a3, v15);
    v26 = 0;
    v83 = 0;
    while ( v26 < a2 )
      v83 = ++v26;
  }
  else
  {
    v25 = (char *)a3;
    v79 = (char *)a3;
  }
  v27 = 0;
  v72 = 0;
  v28 = a6 + *(unsigned __int16 *)(a6 + 36);
  v78 = v28;
  v29 = 0;
  v71 = 0;
  v30 = 0;
  v31 = v25;
  v32 = (_BYTE *)(v28 + 4LL * *(unsigned __int16 *)(v11 + 4));
  v33 = v81;
  v34 = 0;
  v35 = v73;
  while ( 1 )
  {
    v74 = v34;
    v80 = v33;
    v75 = v32;
    if ( v34 >= v35 )
      break;
    if ( v29 == a2 )
      return 3221225990LL;
    v36 = *v32 & 0xF;
    if ( v36 == 7 )
    {
      if ( *((_WORD *)v32 + 1) )
        return 3221225520LL;
      v33[3] = v29;
      *(_DWORD *)v33 = (*(_DWORD *)v33 & 0xFF000FFF ^ ((v30 & 0xFFF) << 12)) & 0xFFFFF000;
      goto LABEL_98;
    }
    if ( v36 == 8 )
      v37 = a5 != 0 ? 8 : 4;
    else
      v37 = *((unsigned __int16 *)v32 + 1);
    if ( (*v32 & 0x10) != 0 )
    {
      if ( (unsigned int)v37 >= v74 )
        return 3221225520LL;
      if ( (unsigned __int8)((*(_BYTE *)(v28 + 4 * v37) & 0xF) - 1) > 1u )
        return 3221225520LL;
      if ( (*(_BYTE *)(v28 + 4 * v37) & 0x30) != 0 )
        return 3221225520LL;
      if ( *(unsigned __int16 *)(v28 + 4 * v37 + 2) > 8u )
        return 3221225520LL;
      if ( *(_BYTE *)(v28 + 4 * v37 + 1) != 1 )
        return 3221225520LL;
      _mm_lfence();
      if ( !(unsigned __int8)EtwpGetFieldValue(
                               *(_QWORD *)&v25[16 * (unsigned __int8)v81[4 * v37 + 3]]
                             + ((*(_DWORD *)&v81[4 * v37] >> 12) & 0xFFF),
                               *(unsigned __int16 *)(v28 + 4 * v37 + 2),
                               SubAuthorityCount,
                               v27) )
        return 3221225520LL;
      LODWORD(v37) = SubAuthorityCount[0];
      if ( SubAuthorityCount[0] != *(_QWORD *)SubAuthorityCount )
        return 3221225520LL;
      v28 = v78;
      v32 = v75;
    }
    v38 = (unsigned __int8)v32[1];
    if ( (*v32 & 0x20) != 0 )
    {
      if ( (unsigned int)v38 >= v74 )
        return 3221225520LL;
      v39 = (unsigned __int8)v32[1];
      if ( (unsigned __int8)((*(_BYTE *)(v28 + 4 * v38) & 0xF) - 1) > 1u )
        return 3221225520LL;
      if ( (*(_BYTE *)(v28 + 4 * v39) & 0x30) != 0 )
        return 3221225520LL;
      if ( *(unsigned __int16 *)(v28 + 4 * v39 + 2) > 8u )
        return 3221225520LL;
      if ( *(_BYTE *)(v28 + 4 * v39 + 1) != 1 )
        return 3221225520LL;
      _mm_lfence();
      if ( !(unsigned __int8)EtwpGetFieldValue(
                               *(_QWORD *)&v25[16 * (unsigned __int8)v81[4 * v39 + 3]]
                             + ((*(_DWORD *)&v81[4 * v39] >> 12) & 0xFFF),
                               *(unsigned __int16 *)(v28 + 4 * v39 + 2),
                               SubAuthorityCount,
                               v27) )
        return 3221225520LL;
      v40 = SubAuthorityCount[0];
      v85 = *(_QWORD *)SubAuthorityCount;
      if ( SubAuthorityCount[0] != *(_QWORD *)SubAuthorityCount )
        return 3221225520LL;
    }
    else
    {
      v40 = (unsigned __int8)v32[1];
      v85 = (unsigned int)v38;
    }
    v42 = 0;
    if ( !(_DWORD)v37 )
    {
      if ( (*v75 & 0x10) != 0 || v40 != 1 )
        return 3221225520LL;
      switch ( *v75 & 0xF )
      {
        case 3:
          v51 = *((_DWORD *)v31 + 2);
          if ( v30 >= v51 )
            return 3221225485LL;
          v52 = (_BYTE *)(*(_QWORD *)v31 + v30);
          v53 = v51 - v30;
          LODWORD(v37) = 0;
          while ( (unsigned int)v37 < v53 && *v52 )
          {
            LODWORD(v37) = v37 + 1;
            v84 = v37;
            v88 = ++v52;
          }
          if ( (_DWORD)v37 == v53 )
          {
            v50 = 1;
            v72 = 1;
            v42 = 0;
            goto LABEL_82;
          }
          v42 = 1;
          break;
        case 4:
          v46 = *((_DWORD *)v31 + 2) - v30;
          if ( v46 < 2 )
            return 3221225485LL;
          v47 = (_WORD *)(v30 + *(_QWORD *)v31);
          v48 = v46 >> 1;
          v49 = 0;
          while ( v49 < v48 && *v47 )
          {
            v84 = ++v49;
            v87 = ++v47;
          }
          if ( v49 == v48 )
          {
            v50 = 2;
            v72 = 2;
            v42 = 0;
          }
          else
          {
            v42 = 2;
            v50 = v72;
          }
          if ( v49 == v48 && v30 + 2LL * v48 != *((_DWORD *)v31 + 2) )
            return 3221225485LL;
          LODWORD(v37) = 2 * v49;
          goto LABEL_82;
        case 6:
          v43 = (void *)(*(_QWORD *)v31 + v30);
          if ( *((_DWORD *)v31 + 2) - v30 < (unsigned int)RtlSubAuthorityCountSid(v43) - (unsigned int)v43 + 1 )
            return 3221225485LL;
          v44 = RtlSubAuthorityCountSid(v43);
          if ( !(unsigned __int8)EtwpGetFieldValue(v44, 1, SubAuthorityCount, v45) )
            return 3221225485LL;
          LODWORD(v37) = RtlLengthRequiredSid(SubAuthorityCount[0]);
          if ( (_DWORD)v37 == -1 )
            return 3221225485LL;
          v42 = 0;
          break;
        default:
          return 3221225520LL;
      }
    }
    v50 = v72;
LABEL_82:
    v54 = v85 * v37;
    if ( *((_DWORD *)v31 + 2) - v30 < v54 )
      return 3221225990LL;
    v29 = v71;
    v33 = v80;
    v80[3] = v71;
    v55 = *(_DWORD *)v33
        ^ (*(_DWORD *)v33
         ^ (v30 << 12))
        & 0xFFF000
        ^ (v54
         ^ *(_DWORD *)v33
         ^ (*(_DWORD *)v33
          ^ (v30 << 12))
         & 0xFFF000)
        & 0xFFF;
    *(_DWORD *)v33 = v55;
    if ( (unsigned __int8)v33[3] != v29 || ((v55 >> 12) & 0xFFF) != v30 || (v55 & 0xFFF) != v54 )
      return 3221225990LL;
    v30 += v54 + v42;
    if ( v30 > *((_DWORD *)v31 + 2) )
      return 3221225473LL;
    if ( v30 != *((_DWORD *)v31 + 2) || (++v29, v71 = v29, v29 >= a2) )
    {
      v27 = v72;
LABEL_97:
      v28 = v78;
      v35 = v73;
      goto LABEL_98;
    }
    v31 += 16;
    if ( v31 >= &v25[16 * a2] )
      return 3221225473LL;
    v30 = 0;
    if ( v50 )
    {
      if ( *((_DWORD *)v31 + 2) < v50 )
        return 3221225990LL;
      v30 = v50;
    }
    v27 = 0;
    v72 = 0;
    if ( v30 != *((_DWORD *)v31 + 2) )
      goto LABEL_97;
    v71 = ++v29;
    v28 = v78;
    v35 = v73;
    if ( v29 < a2 )
    {
      v30 = 0;
      v31 += 16;
    }
LABEL_98:
    v34 = v74 + 1;
    v32 = v75 + 4;
    v33 += 4;
  }
  if ( (_DWORD)v27 || v29 != a2 || v30 != *((_DWORD *)v31 + 2) )
    return 3221225990LL;
  v56 = (char *)(v28 + 4LL * *(unsigned __int16 *)(v11 + 4));
  v80 = v56;
  v57 = a6;
  v58 = (unsigned __int16 *)(a6 + *(unsigned __int16 *)(a6 + 40) + 4LL * *(unsigned __int16 *)(v11 + 8));
  v59 = 0;
  v60 = 0;
  v70 = 1;
  v61 = 0;
  while ( 1 )
  {
    v71 = v61;
    if ( v61 >= *(unsigned __int16 *)(v86 + 10) )
      break;
    v62 = (unsigned __int16 *)(v57 + 8 * (v58[1] + 2LL * v58[1] + 7));
    v63 = 1;
    v64 = 0;
    v69 = 0;
    v65 = 0;
    while ( 1 )
    {
      v66 = *v58;
      if ( v65 >= ((*v58 >> 2) & 0x3Fu) )
        break;
      v67 = *v62;
      if ( !(unsigned __int8)EtwpApplyPredicate(
                               v57,
                               v56[4 * v67] & 0xF,
                               v62,
                               *(_QWORD *)&v79[16 * (unsigned __int8)v81[4 * v67 + 3]]
                             + (((unsigned __int64)*(unsigned int *)&v81[4 * v67] >> 12) & 0xFFF),
                               *(_DWORD *)&v81[4 * v67] & 0xFFF,
                               &v68) )
        return 3221225520LL;
      v63 &= v68;
      v64 = v68 | v69;
      v69 |= v68;
      ++v65;
      v62 += 12;
      v56 = v80;
      v57 = a6;
    }
    if ( (v66 & 2) == 0 )
      v64 = v63;
    if ( (v66 & 1) != 0 )
    {
      if ( v70 )
      {
        v59 = v64;
        v70 = 0;
      }
      else
      {
        v59 &= v64;
      }
    }
    else
    {
      v60 |= v64;
      if ( v60 == 1 )
        break;
    }
    v61 = v71 + 1;
    v58 += 2;
  }
  *a7 = v59 | v60;
  return 0;
}

```

## disassembly

```asm
0x1800286b0  mov     [rsp-8+arg_18], r9b
0x1800286b5  mov     [rsp-8+arg_10], r8
0x1800286ba  mov     [rsp-8+arg_8], edx
0x1800286be  push    rbp
0x1800286bf  push    rsi
0x1800286c0  push    rdi
0x1800286c1  push    r12
0x1800286c3  push    r13
0x1800286c5  push    r14
0x1800286c7  push    r15
0x1800286c9  sub     rsp, 0C0h
0x1800286d0  lea     rbp, [rsp+30h]
0x1800286d5  mov     [rbp+0C0h+arg_0], rbx
0x1800286dc  mov     rax, cs:__security_cookie
0x1800286e3  xor     rax, rbp
0x1800286e6  mov     [rbp+0C0h+var_40], rax
0x1800286ed  mov     rdi, r8
0x1800286f0  mov     r13d, edx
0x1800286f3  xor     ebx, ebx
0x1800286f5  mov     [rbp+0C0h+var_88], rbx
0x1800286f9  mov     qword ptr [rbp+0C0h+SubAuthorityCount], rbx
0x1800286fd  mov     [rbp+0C0h+var_C0], bl
0x180028700  cmp     edx, 80h
0x180028706  ja      loc_180028E90
0x18002870c  movzx   r10d, word ptr [rcx]
0x180028710  mov     [rbp+0C0h+var_70], r10w
0x180028715  mov     r11b, [rcx+2]
0x180028719  mov     [rbp+0C0h+var_A0], r11b
0x18002871d  mov     ecx, r10d
0x180028720  mov     eax, 4104105h
0x180028725  mul     r10d
0x180028728  mov     eax, r10d
0x18002872b  sub     eax, edx
0x18002872d  shr     eax, 1
0x18002872f  add     eax, edx
0x180028731  shr     eax, 5
0x180028734  imul    eax, 3Fh ; '?'
0x180028737  sub     ecx, eax
0x180028739  movzx   ecx, cl
0x18002873c  mov     rdx, [rbp+0C0h+arg_28]
0x180028743  mov     rax, [rdx+8]
0x180028747  bt      rax, rcx
0x18002874b  jnb     loc_180028E7B
0x180028751  movzx   esi, word ptr [rdx+20h]
0x180028755  add     rsi, rdx
0x180028758  mov     r8d, ebx
0x18002875b  movzx   ecx, word ptr [rdx+22h]
0x18002875f  mov     rax, 0AAAAAAAAAAAAAAABh
0x180028769  mul     rcx
0x18002876c  shr     rdx, 3
0x180028770  mov     [rbp+0C0h+var_A8], rsi
0x180028774  mov     [rbp+0C0h+var_58], rsi
0x180028778  cmp     r8d, edx
0x18002877b  jnb     short loc_1800287A3
0x18002877d  cmp     [rsi], r10w
0x180028781  jnz     short loc_180028789
0x180028783  cmp     [rsi+2], r11b
0x180028787  jz      short loc_1800287A0
0x180028789  movzx   eax, byte ptr [rsi+3]
0x18002878d  cmp     ax, [rsi+6]
0x180028791  jnb     loc_180028E90
0x180028797  add     rsi, 0Ch
0x18002879b  inc     r8d
0x18002879e  jmp     short loc_180028770
0x1800287a0  cmp     r8d, edx
0x1800287a3  jz      loc_180028E7B
0x1800287a9  mov     [rbp+0C0h+var_88], rbx
0x1800287ad  mov     eax, r13d
0x1800287b0  shl     eax, 4
0x1800287b3  mov     edx, eax
0x1800287b5  mov     dword ptr [rbp+0C0h+var_80], eax
0x1800287b8  movzx   eax, word ptr [rsi+6]
0x1800287bc  mov     [rbp+0C0h+var_B4], eax
0x1800287bf  shl     eax, 2
0x1800287c2  mov     [rbp+0C0h+var_78], rbx
0x1800287c6  lea     rcx, [rax+0Fh]
0x1800287ca  mov     r8, 0FFFFFFFFFFFFFF0h
0x1800287d4  cmp     rcx, rax
0x1800287d7  ja      short loc_1800287DC
0x1800287d9  mov     rcx, r8
0x1800287dc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800287e0  mov     rax, rcx
0x1800287e3  call    _alloca_probe
0x1800287e8  sub     rsp, rcx
0x1800287eb  lea     rax, [rsp+0F0h+var_C0]
0x1800287f0  mov     [rbp+0C0h+var_78], rax
0x1800287f4  jmp     short loc_180028841
0x1800287f6  call    cs:__imp__o__resetstkoflw
0x1800287fc  test    eax, eax
0x1800287fe  jnz     loc_180028E74
0x180028804  xor     r9d, r9d; lpArguments
0x180028807  xor     r8d, r8d; nNumberOfArguments
0x18002880a  lea     edx, [rax+1]; dwExceptionFlags
0x18002880d  mov     ecx, 0C00000FDh; dwExceptionCode
0x180028812  call    cs:__imp_RaiseException
0x180028818  xor     ebx, ebx
0x18002881a  mov     r8, 0FFFFFFFFFFFFFF0h
0x180028824  mov     r9b, [rbp+0C0h+arg_18]
0x18002882b  mov     rdi, [rbp+0C0h+arg_10]
0x180028832  mov     r13d, [rbp+0C0h+arg_8]
0x180028839  mov     rsi, [rbp+0C0h+var_A8]
0x18002883d  mov     rdx, [rbp+0C0h+var_80]
0x180028841  mov     [rbp+0C0h+var_BC], edx
0x180028844  test    r9b, r9b
0x180028847  jz      short loc_1800288BD
0x180028849  mov     eax, edx
0x18002884b  lea     rcx, [rax+0Fh]
0x18002884f  cmp     rcx, rax
0x180028852  ja      short loc_180028857
0x180028854  mov     rcx, r8
0x180028857  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002885b  mov     rax, rcx
0x18002885e  call    _alloca_probe
0x180028863  sub     rsp, rcx
0x180028866  lea     r12, [rsp+0F0h+var_C0]
0x18002886b  mov     [rbp+0C0h+var_88], r12
0x18002886f  jmp     short loc_1800288C1
0x180028871  call    cs:__imp__o__resetstkoflw
0x180028877  test    eax, eax
0x180028879  jnz     short loc_1800288B3
0x18002887b  xor     r9d, r9d; lpArguments
0x18002887e  xor     r8d, r8d; nNumberOfArguments
0x180028881  lea     edx, [rax+1]; dwExceptionFlags
0x180028884  mov     ecx, 0C00000FDh; dwExceptionCode
0x180028889  call    cs:__imp_RaiseException
0x18002888f  xor     ebx, ebx
0x180028891  mov     r9b, [rbp+0C0h+arg_18]
0x180028898  mov     rdi, [rbp+0C0h+arg_10]
0x18002889f  mov     r13d, [rbp+0C0h+arg_8]
0x1800288a6  mov     rsi, [rbp+0C0h+var_A8]
0x1800288aa  mov     edx, [rbp+0C0h+var_BC]
0x1800288ad  mov     r12, [rbp+0C0h+var_88]
0x1800288b1  jmp     short loc_1800288C1
0x1800288b3  mov     eax, 0C00000FDh
0x1800288b8  jmp     loc_180028E95
0x1800288bd  mov     r12, [rbp+0C0h+var_88]
0x1800288c1  mov     [rbp+0C0h+var_BC], 0C000000Dh
0x1800288c8  test    r9b, r9b
0x1800288cb  jz      short loc_1800288F6
0x1800288cd  mov     r8d, edx; Size
0x1800288d0  mov     rdx, rdi; Src
0x1800288d3  mov     rcx, r12; void *
0x1800288d6  call    memcpy_0
0x1800288db  mov     eax, ebx
0x1800288dd  mov     [rbp+0C0h+var_6C], ebx
0x1800288e0  cmp     eax, r13d
0x1800288e3  jnb     short loc_1800288EC
0x1800288e5  inc     eax
0x1800288e7  mov     [rbp+0C0h+var_6C], eax
0x1800288ea  jmp     short loc_1800288E0
0x1800288ec  jmp     short loc_1800288FD
0x1800288ee  mov     eax, [rbp+0C0h+var_BC]
0x1800288f1  jmp     loc_180028E95
0x1800288f6  mov     r12, rdi
0x1800288f9  mov     [rbp+0C0h+var_88], rdi
0x1800288fd  mov     r9d, ebx
0x180028900  mov     [rbp+0C0h+var_B8], ebx
0x180028903  mov     r11, [rbp+0C0h+arg_28]
0x18002890a  movzx   edx, word ptr [r11+24h]
0x18002890f  add     rdx, r11
0x180028912  mov     [rbp+0C0h+var_90], rdx
0x180028916  mov     r8d, ebx
0x180028919  mov     [rbp+0C0h+var_BC], ebx
0x18002891c  mov     r14d, ebx
0x18002891f  mov     r15, r12
0x180028922  movzx   eax, word ptr [rsi+4]
0x180028926  lea     rcx, [rdx+rax*4]
0x18002892a  mov     r10, [rbp+0C0h+var_78]
0x18002892e  mov     eax, ebx
0x180028930  mov     r11d, [rbp+0C0h+var_B4]
0x180028934  mov     [rbp+0C0h+var_B0], eax
0x180028937  mov     [rbp+0C0h+var_80], r10
0x18002893b  mov     [rbp+0C0h+var_A8], rcx
0x18002893f  cmp     eax, r11d
0x180028942  jnb     loc_180028D13
0x180028948  cmp     r8d, r13d
0x18002894b  jz      loc_180028E6D
0x180028951  mov     al, [rcx]
0x180028953  and     al, 0Fh
0x180028955  cmp     al, 7
0x180028957  jnz     short loc_18002898B
0x180028959  cmp     [rcx+2], bx
0x18002895d  jnz     loc_180028AA5
0x180028963  mov     [r10+3], r8b
0x180028967  mov     eax, [r10]
0x18002896a  mov     ecx, r14d
0x18002896d  and     ecx, 0FFFh
0x180028973  shl     ecx, 0Ch
0x180028976  and     eax, 0FF000FFFh
0x18002897b  xor     ecx, eax
0x18002897d  and     ecx, 0FFFFF000h
0x180028983  mov     [r10], ecx
0x180028986  jmp     loc_180028CF3
0x18002898b  cmp     al, 8
0x18002898d  jnz     short loc_1800289A1
0x18002898f  mov     al, [rbp+0C0h+arg_20]
0x180028995  neg     al
0x180028997  sbb     edi, edi
0x180028999  and     edi, 4
0x18002899c  add     edi, 4
0x18002899f  jmp     short loc_1800289A5
0x1800289a1  movzx   edi, word ptr [rcx+2]
0x1800289a5  test    byte ptr [rcx], 10h
0x1800289a8  jz      loc_180028A32
0x1800289ae  cmp     edi, [rbp+0C0h+var_B0]
0x1800289b1  jnb     loc_180028AA5
0x1800289b7  mov     al, [rdx+rdi*4]
0x1800289ba  and     al, 0Fh
0x1800289bc  dec     al
0x1800289be  cmp     al, 1
0x1800289c0  ja      loc_180028AA5
0x1800289c6  test    byte ptr [rdx+rdi*4], 30h
0x1800289ca  jnz     loc_180028AA5
0x1800289d0  movzx   eax, word ptr [rdx+rdi*4+2]
0x1800289d5  cmp     eax, 8
0x1800289d8  ja      loc_180028AA5
0x1800289de  cmp     byte ptr [rdx+rdi*4+1], 1
0x1800289e3  jnz     loc_180028AA5
0x1800289e9  lfence
0x1800289ec  mov     edx, eax
0x1800289ee  mov     r8, [rbp+0C0h+var_78]
0x1800289f2  movzx   eax, byte ptr [r8+rdi*4+3]
0x1800289f8  shl     rax, 4
0x1800289fc  mov     ecx, [r8+rdi*4]
0x180028a00  shr     rcx, 0Ch
0x180028a04  and     ecx, 0FFFh
0x180028a0a  add     rcx, [rax+r12]
0x180028a0e  lea     r8, [rbp+0C0h+SubAuthorityCount]
0x180028a12  call    EtwpGetFieldValue
0x180028a17  test    al, al
0x180028a19  jz      loc_180028AA5
0x180028a1f  mov     rdi, qword ptr [rbp+0C0h+SubAuthorityCount]
0x180028a23  mov     eax, edi
0x180028a25  cmp     rax, rdi
0x180028a28  jnz     short loc_180028AA5
0x180028a2a  mov     rdx, [rbp+0C0h+var_90]
0x180028a2e  mov     rcx, [rbp+0C0h+var_A8]
0x180028a32  movzx   eax, byte ptr [rcx+1]
0x180028a36  test    byte ptr [rcx], 20h
0x180028a39  jz      short loc_180028AAF
0x180028a3b  cmp     eax, [rbp+0C0h+var_B0]
0x180028a3e  jnb     short loc_180028AA5
0x180028a40  mov     ecx, eax
0x180028a42  mov     al, [rdx+rax*4]
0x180028a45  and     al, 0Fh
0x180028a47  dec     al
0x180028a49  cmp     al, 1
0x180028a4b  ja      short loc_180028AA5
0x180028a4d  test    byte ptr [rdx+rcx*4], 30h
0x180028a51  jnz     short loc_180028AA5
0x180028a53  movzx   eax, word ptr [rdx+rcx*4+2]
0x180028a58  cmp     eax, 8
0x180028a5b  ja      short loc_180028AA5
0x180028a5d  cmp     byte ptr [rdx+rcx*4+1], 1
0x180028a62  jnz     short loc_180028AA5
0x180028a64  lfence
0x180028a67  mov     edx, eax
0x180028a69  mov     r8, [rbp+0C0h+var_78]
0x180028a6d  movzx   eax, byte ptr [r8+rcx*4+3]
0x180028a73  shl     rax, 4
0x180028a77  mov     ecx, [r8+rcx*4]
0x180028a7b  shr     rcx, 0Ch
0x180028a7f  and     ecx, 0FFFh
0x180028a85  add     rcx, [rax+r12]
0x180028a89  lea     r8, [rbp+0C0h+SubAuthorityCount]
0x180028a8d  call    EtwpGetFieldValue
0x180028a92  test    al, al
0x180028a94  jz      short loc_180028AA5
0x180028a96  mov     rcx, qword ptr [rbp+0C0h+SubAuthorityCount]
0x180028a9a  mov     [rbp+0C0h+var_60], rcx
0x180028a9e  mov     eax, ecx
0x180028aa0  cmp     rax, rcx
0x180028aa3  jz      short loc_180028AB5
0x180028aa5  mov     eax, 0C0000030h
0x180028aaa  jmp     loc_180028E95
0x180028aaf  mov     ecx, eax
0x180028ab1  mov     [rbp+0C0h+var_60], rcx
0x180028ab5  mov     edx, ebx
0x180028ab7  test    edi, edi
0x180028ab9  jnz     loc_180028C08
0x180028abf  mov     rax, [rbp+0C0h+var_A8]
0x180028ac3  test    byte ptr [rax], 10h
0x180028ac6  jnz     short loc_180028AA5
0x180028ac8  cmp     ecx, 1
0x180028acb  jnz     short loc_180028AA5
0x180028acd  movzx   ecx, byte ptr [rax]
0x180028ad0  and     ecx, 0Fh
0x180028ad3  sub     ecx, 3
0x180028ad6  jz      loc_180028BB7
0x180028adc  sub     ecx, 1
0x180028adf  jz      short loc_180028B46
0x180028ae1  cmp     ecx, 2
0x180028ae4  jnz     short loc_180028AA5
0x180028ae6  mov     edi, r14d
0x180028ae9  add     rdi, [r15]
0x180028aec  mov     rcx, rdi; Sid
0x180028aef  call    cs:__imp_RtlSubAuthorityCountSid
0x180028af5  sub     eax, edi
0x180028af7  lea     edx, [rax+1]
0x180028afa  mov     eax, [r15+8]
  ... truncated ...
```
