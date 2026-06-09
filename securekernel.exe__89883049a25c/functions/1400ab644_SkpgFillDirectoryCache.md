# SkpgFillDirectoryCache

- ea: `0x1400ab644`
- end: `0x1400abfa0`
- name: `SkpgFillDirectoryCache`
- size: `2396`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1400ac44c`

## callees

- `0x140032038`
- `0x140032c68`
- `0x1400a589c`
- `0x1400a5dac`
- `0x1400aafe8`
- `0x1400ab040`
- `0x1400ab438`
- `0x1400ab4bc`
- `0x1400ab644`
- `0x1400abfa8`
- `0x1400ac1f0`
- `0x1400acf78`
- `0x1400f3620`

## pseudocode

```c
__int64 __fastcall SkpgFillDirectoryCache(
        __int64 a1,
        unsigned int *a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int v5; // esi
  unsigned int v6; // r10d
  unsigned __int64 v8; // rcx
  unsigned int v11; // edx
  __int64 v12; // r15
  int i; // r13d
  __int64 v14; // rax
  int v15; // r11d
  int v16; // eax
  __int64 v17; // rsi
  __int64 v18; // rax
  int v19; // edx
  __int64 v20; // rax
  int v21; // edx
  int v22; // ecx
  int v23; // r10d
  int v24; // r9d
  int v25; // r8d
  __int64 result; // rax
  unsigned int v27; // edx
  unsigned __int64 *v28; // r9
  unsigned int v29; // edx
  unsigned int v30; // ecx
  __int64 v31; // r8
  int v32; // r10d
  unsigned int j; // edx
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r15
  int v38; // r13d
  __int64 v39; // r8
  int v40; // eax
  int v41; // r15d
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // edx
  unsigned int v46; // r11d
  int v47; // r8d
  int v48; // eax
  unsigned __int64 v49; // rcx
  __int64 v50; // r11
  int v51; // eax
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // rax
  __int64 v54; // r13
  __int64 v55; // r15
  __int64 v56; // r8
  int v57; // eax
  unsigned __int64 v58; // rcx
  unsigned __int64 v59; // rax
  unsigned __int64 v60; // rax
  unsigned __int64 v61; // rcx
  unsigned int v62; // eax
  __int64 v63; // rax
  int v64; // edx
  unsigned int v65; // [rsp+30h] [rbp-51h]
  unsigned __int64 v66; // [rsp+38h] [rbp-49h]
  unsigned int v67; // [rsp+40h] [rbp-41h]
  int v68; // [rsp+44h] [rbp-3Dh]
  int v69; // [rsp+48h] [rbp-39h]
  __int64 v71; // [rsp+50h] [rbp-31h] BYREF
  __int64 v72; // [rsp+58h] [rbp-29h]
  unsigned __int64 v73; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int64 v74; // [rsp+68h] [rbp-19h]
  unsigned __int64 v75; // [rsp+70h] [rbp-11h]
  __int64 v76; // [rsp+78h] [rbp-9h]
  _QWORD v77[3]; // [rsp+80h] [rbp-1h] BYREF

  v5 = 0;
  v6 = a4;
  v8 = (unsigned __int64)a5;
  v73 = 0;
  v67 = -1073741799;
  if ( !a5 || !*a5 )
  {
    if ( (unsigned __int64)(((__int64)a3 >> 47) + 1) > 1 )
    {
      SkpgUpdateDirectoryCachePteTracking(a5, a2, a4);
      v21 = 7;
      v22 = a1;
      v24 = v23;
      v25 = a3;
      goto LABEL_15;
    }
    if ( (*a2 & 8) != 0 )
    {
      SkpgLogEvent(a1, 8, a3, a4, 0, 0);
      return 3221225659LL;
    }
    if ( (*(_DWORD *)(a1 + 244) & 2) == 0 )
    {
      SkpgAcquireTbFlushLock(a1);
      v6 = a4;
    }
    v27 = *a2;
    v69 = 1;
    if ( (*a2 & 1) != 0 )
    {
      v31 = *((_QWORD *)a2 + 1);
      if ( v31 != -1 || (v8 = a2[1], a3 >> v8 != *((_QWORD *)a2 + 2)) )
      {
        if ( a3 >> 21 == v31 )
        {
          if ( (v27 & 2) != 0 )
          {
            SkpgUpdateDirectoryCachePteTracking(v8, a2, v6);
            v25 = a3;
            v22 = a1;
            v24 = v32;
            if ( (*a2 & 4) != 0 )
            {
              ++*(_DWORD *)(a1 + 824);
              SkpgLogEvent(a1, 9, a3, v32, 0, 0);
              return 3221225497LL;
            }
            ++*(_DWORD *)(a1 + 820);
            v21 = 10;
LABEL_15:
            SkpgLogEvent(v22, v21, v25, v24, 0, 0);
            return 3221225477LL;
          }
        }
        else
        {
          v69 = 0;
          *a2 = v27 & 0xFFFFFFFE;
        }
      }
    }
    else
    {
      SkpgxReadDirectoryTableBase(a1, a2);
      *((_QWORD *)a2 + 3) = -1;
      *a2 &= ~0x10u;
    }
    SkpgUpdateDirectoryCachePteTracking(v8, a2, a4);
    v29 = *a2;
    if ( (*a2 & 1) != 0 )
      return 0;
    v68 = 1;
    *v28 = a3 >> 21;
    *a2 = v29 & 0xFFFFFFF9;
    v74 = __rdtsc();
    goto LABEL_24;
  }
  ++*(_DWORD *)(a1 + 848);
  v74 = __rdtsc();
  if ( *((_QWORD *)a2 + 1) != a3 >> 21 )
  {
    *a2 &= ~1u;
    *((_QWORD *)a2 + 1) = a3 >> 21;
  }
  *a2 &= 0xFFFFFFF9;
  v11 = *a5;
  v12 = *((_QWORD *)a2 + 6);
  i = a5[1];
  LODWORD(v72) = i;
  v71 = v12;
  if ( v11 )
  {
    do
    {
      v14 = v5++;
      v12 = *(_QWORD *)&a2[2 * v14 + 8];
      v71 = v12;
      v77[v14] = v12;
    }
    while ( v5 < v11 );
  }
  SkpgLogEvent(a1, 6, a3, a4, v5, a2[6]);
  v68 = v15;
  v69 = v15;
  if ( v5 < 3 )
    goto LABEL_26;
LABEL_8:
  v66 = (((a3 & 0xFFFFFFFFFFE00000uLL) >> 9) & 0x7FFFFFFFF8LL) + *(_QWORD *)(a1 + 368);
  v16 = SkpgTranslatePageTableVa(a1, v66, &v71);
  v17 = v16;
  if ( v16 >= 0 )
  {
    v18 = v71;
    if ( v71 == v12 )
    {
      *a2 |= 1u;
      v54 = SkpgMapPage(a1, v18, 128);
      v55 = 0;
      do
      {
        v56 = v54 + 8 * v55;
        do
          v57 = SkpgxReadPte(a1, 0, v56, &v73);
        while ( v57 == -1073740748 && (*(_DWORD *)(a1 + 244) & 0x3000) == 0x1000 );
        if ( v57 >= 0 )
        {
          *(_QWORD *)&a2[2 * v55 + 14] = *(_QWORD *)&a2[2 * v55 + 14] & 0xFFCLL | v73 & 0xFFFFFFFFFF000LL | 1;
        }
        else
        {
          v58 = *(_QWORD *)&a2[2 * v55 + 14] & 0xFFFFFFFFFFFFFFFCuLL;
          *(_QWORD *)&a2[2 * v55 + 14] = v58;
          if ( v57 == -1073741799 )
            *(_QWORD *)&a2[2 * v55 + 14] = v58 | 2;
        }
        v55 = (unsigned int)(v55 + 1);
      }
      while ( (unsigned int)v55 < 0x200 );
      *(_DWORD *)(a1 + 68) += 15360;
      SkpgLogEvent(a1, 21, a3, a4, *((_QWORD *)a2 + 1), 0);
      SkpgFlushMappings(a1);
      v59 = __rdtsc();
      v60 = (((unsigned __int64)HIDWORD(v59) << 32) | (unsigned int)v59) - v74;
      if ( v60 > *(_QWORD *)(a1 + 856) )
        *(_QWORD *)(a1 + 856) = v60;
      return 0;
    }
  }
  SkpgFlushMappings(a1);
  if ( (int)v17 >= 0 )
  {
    v19 = 18;
    goto LABEL_12;
  }
  if ( (_DWORD)v17 == -1073741799 )
  {
    v19 = 19;
LABEL_12:
    v20 = v71;
    ++*(_DWORD *)(a1 + 836);
    SkpgLogEvent(a1, v19, a3 & 0xFFE00000, v66, v20, v12);
LABEL_75:
    v5 = 0;
    *((_QWORD *)a2 + 3) = -1;
    *((_QWORD *)a2 + 543) = 0;
    a2[1088] = 0;
LABEL_24:
    v12 = *((_QWORD *)a2 + 6);
    SkpgFlushMappings(a1);
    for ( i = 39; ; i -= 9 )
    {
      LODWORD(v72) = i;
LABEL_26:
      v75 = a3 >> i;
      v65 = (a3 >> i) & 0x1FF;
      if ( v5 < 2 )
      {
        v30 = a2[v5 + 6];
        if ( v30 == ((a3 >> i) & 0x1FF) )
        {
          v12 = *(_QWORD *)&a2[2 * v5 + 8];
          ++*(_DWORD *)(a1 + 832);
          v71 = v12;
          v77[v5] = v12;
          goto LABEL_64;
        }
        if ( v30 != -1 )
        {
          for ( j = v5; j < 3; ++j )
          {
            if ( j < 2 )
              a2[j + 6] = -1;
            if ( (*a2 & 0x10) != 0 )
            {
              v34 = ~(1 << (j + 1));
              a2[1086] &= v34;
              a2[1087] &= v34;
              a2[1088] &= v34;
            }
          }
        }
      }
      if ( (*a2 & 0x10) != 0 )
      {
        v35 = a2[1086];
        if ( _bittest64(&v35, v5) )
        {
          if ( ((*((_BYTE *)&a2[16 * (unsigned __int64)v5 + 1038] + (((a3 >> i) & 0x1FF) >> 3)) >> ((a3 >> i) & 7)) & 1) != 0 )
          {
            v49 = v75;
            *a2 |= 7u;
            *((_QWORD *)a2 + 2) = v49;
            a2[1] = i;
            ++*(_DWORD *)(a1 + 868);
            SkpgLogEvent(a1, 11, a3, i, (a3 >> i) & 0x1FF, v5);
            goto LABEL_118;
          }
        }
      }
      if ( v68 )
      {
        ++*(_DWORD *)(a1 + 844);
        v68 = 0;
      }
      v36 = SkpgMapPage(a1, v12, 128);
      *(_DWORD *)(a1 + 68) += 3072;
      v37 = v36;
      v76 = v36;
      if ( !v5 )
      {
        if ( v69 )
        {
          v38 = SkpgVerifySelfMap(a1, a2, v36);
          if ( v38 < 0 )
          {
            if ( v38 != -1073740767 )
              ++*(_DWORD *)(a1 + 812);
            SkpgFlushMappings(a1);
            if ( v38 == -1073741799 )
              v38 = -1073741819;
            SkpgLogEvent(a1, 12, a3, 0, 0, 0);
            result = (unsigned int)v38;
            *((_QWORD *)a2 + 543) = v50;
            a2[1088] = v50;
            return result;
          }
        }
      }
      v39 = v37 + 8LL * v65;
      do
      {
        v40 = SkpgxReadPte(a1, 3 - v5, v39, &v73);
        v41 = v40;
      }
      while ( v40 == -1073740748 && (*(_DWORD *)(a1 + 244) & 0x3000) == 0x1000 );
      i = v72;
      if ( v40 < 0 )
      {
        *a2 |= 3u;
        v47 = a3;
        if ( v40 == -1073741799 )
        {
          v48 = SkpgConfirmNonOverlayPtes(a1, (_DWORD)a2, a3, v5, (__int64)v77);
          v41 = v48;
          if ( v48 == -1073740748 )
            goto LABEL_74;
          if ( v48 >= 0 )
          {
            *a2 |= 4u;
            v41 = -1073741799;
            v61 = v75;
            v62 = *a2;
            a2[1] = i;
            *((_QWORD *)a2 + 2) = v61;
            if ( (v62 & 0x10) != 0 )
              SkpgFillInvalidPtesBitmap(a1, (_DWORD)a2, v76, v5, v65);
LABEL_117:
            v67 = v41;
LABEL_118:
            SkpgFlushMappings(a1);
            return v67;
          }
          if ( v48 != -1073741799 )
            goto LABEL_117;
          v41 = -1073741819;
          v47 = a3;
          v63 = v5;
          v64 = 13;
        }
        else
        {
          v63 = v73;
          v64 = 14;
          *((_QWORD *)a2 + 543) = 0;
          a2[1088] = 0;
        }
        SkpgLogEvent(a1, v64, v47, i, v65, v63);
        goto LABEL_117;
      }
      v12 = (v73 >> 12) & 0xFFFFFFFFFFLL;
      v71 = v12;
      v72 = v5;
      v77[v5] = v12;
      if ( v5 < 2 )
      {
        a2[v5 + 6] = v65;
        *(_QWORD *)&a2[2 * v5 + 8] = v12;
      }
      v42 = *(_DWORD *)(a1 + 444);
      if ( _bittest(&v42, 3 - v5) && (v73 & 0x80u) != 0LL )
      {
        ++*(_DWORD *)(a1 + 804);
        v44 = SkpgConfirmNonOverlayPtes(a1, (_DWORD)a2, a3, v5, (__int64)v77);
        if ( v44 == -1073740748 )
        {
LABEL_74:
          ++*(_DWORD *)(a1 + 836);
          goto LABEL_75;
        }
        if ( v44 < 0 )
        {
          v45 = 15;
          goto LABEL_69;
        }
        *((_QWORD *)a2 + 2) = v75;
        a2[1] = i;
        if ( v5 < 2 )
          a2[v5 + 6] = -1;
        *((_QWORD *)a2 + 1) = -1;
        *((_QWORD *)a2 + 545) = v12;
        while ( v5 < 3 )
        {
          if ( v5 < 2 )
            a2[v5 + 6] = -1;
          if ( (*a2 & 0x10) != 0 )
          {
            v51 = ~(1 << (v5 + 1));
            a2[1086] &= v51;
            a2[1087] &= v51;
            a2[1088] &= v51;
          }
          ++v5;
        }
        *a2 |= 1u;
        SkpgFlushMappings(a1);
        v52 = __rdtsc();
        v53 = (((unsigned __int64)HIDWORD(v52) << 32) | (unsigned int)v52) - v74;
        if ( v53 > *(_QWORD *)(a1 + 856) )
          *(_QWORD *)(a1 + 856) = v53;
        SkpgLogEvent(a1, 16, a3, a2[1], *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 545));
        return 0;
      }
      if ( (*a2 & 0x10) != 0 )
      {
        SkpgFillInvalidPtesBitmap(a1, (_DWORD)a2, v76, v5, -1);
        if ( v5 == 2 )
        {
          v43 = SkpgConfirmNonOverlayPtes(a1, (_DWORD)a2, a3, 2, (__int64)v77);
          if ( v43 == -1073740748 )
            goto LABEL_74;
          if ( v43 < 0 )
          {
            v45 = 17;
LABEL_69:
            SkpgLogEvent(a1, v45, a3, i, v65, v72);
            v67 = v46;
            goto LABEL_118;
          }
        }
      }
LABEL_64:
      if ( ++v5 >= 3 )
        goto LABEL_8;
    }
  }
  if ( (_DWORD)v17 != -1073740767 )
  {
    SkpgLogEvent(a1, 20, a3 & 0xFFE00000, v66, v17, 0);
    *a2 |= 3u;
    ++*(_DWORD *)(a1 + 816);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400ab644  mov     [rsp-8+arg_18], rbx
0x1400ab649  push    rbp
0x1400ab64a  push    rsi
0x1400ab64b  push    rdi
0x1400ab64c  push    r12
0x1400ab64e  push    r13
0x1400ab650  push    r14
0x1400ab652  push    r15
0x1400ab654  lea     rbp, [rsp-1Fh]
0x1400ab659  sub     rsp, 0A0h
0x1400ab660  mov     rax, cs:__security_cookie
0x1400ab667  xor     rax, rsp
0x1400ab66a  mov     [rbp+4Fh+var_38], rax
0x1400ab66e  xor     esi, esi
0x1400ab670  mov     r10d, r9d
0x1400ab673  mov     rdi, rcx
0x1400ab676  mov     [rbp+4Fh+var_84], r10d
0x1400ab67a  mov     rcx, [rbp+4Fh+arg_20]
0x1400ab67e  mov     r12, r8
0x1400ab681  mov     [rbp+4Fh+var_70], rsi
0x1400ab685  mov     rbx, rdx
0x1400ab688  mov     [rbp+4Fh+var_90], 0C0000019h
0x1400ab68f  test    rcx, rcx
0x1400ab692  jz      loc_1400AB7BC
0x1400ab698  cmp     [rcx], esi
0x1400ab69a  jz      loc_1400AB7BC
0x1400ab6a0  rdtsc
0x1400ab6a2  shl     rdx, 20h
0x1400ab6a6  lea     r14d, [rsi+1]
0x1400ab6aa  add     [rdi+350h], r14d
0x1400ab6b1  or      rax, rdx
0x1400ab6b4  mov     [rbp+4Fh+var_68], rax
0x1400ab6b8  mov     rax, r8
0x1400ab6bb  shr     rax, 15h
0x1400ab6bf  cmp     [rbx+8], rax
0x1400ab6c3  jz      short loc_1400AB6CC
0x1400ab6c5  and     dword ptr [rbx], 0FFFFFFFEh
0x1400ab6c8  mov     [rbx+8], rax
0x1400ab6cc  and     dword ptr [rbx], 0FFFFFFF9h
0x1400ab6cf  xor     r11d, r11d
0x1400ab6d2  mov     edx, [rcx]
0x1400ab6d4  mov     r15, [rbx+30h]
0x1400ab6d8  mov     r13d, [rcx+4]
0x1400ab6dc  mov     dword ptr [rbp+4Fh+var_78], r13d
0x1400ab6e0  mov     [rbp+4Fh+var_80], r15
0x1400ab6e4  test    edx, edx
0x1400ab6e6  jz      short loc_1400AB6FF
0x1400ab6e8  mov     eax, esi
0x1400ab6ea  add     esi, r14d
0x1400ab6ed  mov     r15, [rbx+rax*8+20h]
0x1400ab6f2  mov     [rbp+4Fh+var_80], r15
0x1400ab6f6  mov     [rbp+rax*8+4Fh+var_50], r15
0x1400ab6fb  cmp     esi, edx
0x1400ab6fd  jb      short loc_1400AB6E8
0x1400ab6ff  mov     eax, [rbx+18h]
0x1400ab702  mov     r9, r10
0x1400ab705  mov     ecx, esi
0x1400ab707  mov     edx, 6
0x1400ab70c  mov     [rsp+0D0h+var_A8], rax
0x1400ab711  mov     [rsp+0D0h+var_B0], rcx
0x1400ab716  mov     rcx, rdi
0x1400ab719  call    SkpgLogEvent
0x1400ab71e  mov     [rbp+4Fh+var_8C], r11d
0x1400ab722  mov     [rbp+4Fh+var_88], r11d
0x1400ab726  cmp     esi, 3
0x1400ab729  jb      loc_1400AB8B5
0x1400ab72f  mov     rax, 7FFFFFFFF8h
0x1400ab739  lea     r8, [rbp+4Fh+var_80]
0x1400ab73d  mov     r13, r12
0x1400ab740  and     r13, 0FFFFFFFFFFE00000h
0x1400ab747  mov     rcx, r13
0x1400ab74a  shr     rcx, 9
0x1400ab74e  and     rcx, rax
0x1400ab751  mov     rax, [rdi+170h]
0x1400ab758  add     rax, rcx
0x1400ab75b  mov     rcx, rdi
0x1400ab75e  mov     rdx, rax
0x1400ab761  mov     [rbp+4Fh+var_98], rax
0x1400ab765  call    SkpgTranslatePageTableVa
0x1400ab76a  movsxd  rsi, eax
0x1400ab76d  test    eax, eax
0x1400ab76f  js      short loc_1400AB77E
0x1400ab771  mov     rax, [rbp+4Fh+var_80]
0x1400ab775  cmp     rax, r15
0x1400ab778  jz      loc_1400ABDCD
0x1400ab77e  mov     rcx, rdi
0x1400ab781  call    SkpgFlushMappings
0x1400ab786  test    esi, esi
0x1400ab788  js      loc_1400ABBDC
0x1400ab78e  mov     edx, 12h
0x1400ab793  mov     rax, [rbp+4Fh+var_80]
0x1400ab797  mov     r8, r13
0x1400ab79a  mov     r9, [rbp+4Fh+var_98]
0x1400ab79e  mov     rcx, rdi
0x1400ab7a1  add     [rdi+344h], r14d
0x1400ab7a8  mov     [rsp+0D0h+var_A8], r15
0x1400ab7ad  mov     [rsp+0D0h+var_B0], rax
0x1400ab7b2  call    SkpgLogEvent
0x1400ab7b7  jmp     loc_1400ABC2F
0x1400ab7bc  mov     r14d, 1
0x1400ab7c2  mov     rax, r12
0x1400ab7c5  sar     rax, 2Fh
0x1400ab7c9  add     rax, r14
0x1400ab7cc  cmp     rax, r14
0x1400ab7cf  jbe     short loc_1400AB7FF
0x1400ab7d1  mov     r8d, r10d
0x1400ab7d4  call    SkpgUpdateDirectoryCachePteTracking
0x1400ab7d9  mov     [rsp+0D0h+var_A8], rsi
0x1400ab7de  lea     edx, [r14+6]
0x1400ab7e2  mov     [rsp+0D0h+var_B0], rsi
0x1400ab7e7  mov     rcx, rdi
0x1400ab7ea  mov     r9, r10
0x1400ab7ed  mov     r8, r12
0x1400ab7f0  call    SkpgLogEvent
0x1400ab7f5  mov     eax, 0C0000005h
0x1400ab7fa  jmp     loc_1400ABD9B
0x1400ab7ff  mov     eax, [rdx]
0x1400ab801  mov     edx, 8
0x1400ab806  test    dl, al
0x1400ab808  jz      short loc_1400AB829
0x1400ab80a  mov     r9, r10
0x1400ab80d  mov     [rsp+0D0h+var_A8], rsi
0x1400ab812  mov     rcx, rdi
0x1400ab815  mov     [rsp+0D0h+var_B0], rsi
0x1400ab81a  call    SkpgLogEvent
0x1400ab81f  mov     eax, 0C00000BBh
0x1400ab824  jmp     loc_1400ABD9B
0x1400ab829  mov     eax, [rdi+0F4h]
0x1400ab82f  test    al, 2
0x1400ab831  jnz     short loc_1400AB83F
0x1400ab833  mov     rcx, rdi
0x1400ab836  call    SkpgAcquireTbFlushLock
0x1400ab83b  mov     r10d, [rbp+4Fh+var_84]
0x1400ab83f  mov     edx, [rbx]
0x1400ab841  mov     [rbp+4Fh+var_88], r14d
0x1400ab845  test    r14b, dl
0x1400ab848  jnz     loc_1400AB902
0x1400ab84e  mov     rdx, rbx
0x1400ab851  mov     rcx, rdi
0x1400ab854  call    SkpgxReadDirectoryTableBase
0x1400ab859  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x1400ab861  lea     r9, [rbx+8]
0x1400ab865  and     dword ptr [rbx], 0FFFFFFEFh
0x1400ab868  mov     r8d, [rbp+4Fh+var_84]
0x1400ab86c  mov     rdx, rbx
0x1400ab86f  call    SkpgUpdateDirectoryCachePteTracking
0x1400ab874  mov     edx, [rbx]
0x1400ab876  test    r14b, dl
0x1400ab879  jnz     loc_1400ABD99
0x1400ab87f  mov     rax, r12
0x1400ab882  mov     [rbp+4Fh+var_8C], r14d
0x1400ab886  shr     rax, 15h
0x1400ab88a  and     edx, 0FFFFFFF9h
0x1400ab88d  mov     [r9], rax
0x1400ab890  mov     [rbx], edx
0x1400ab892  rdtsc
0x1400ab894  shl     rdx, 20h
0x1400ab898  or      rax, rdx
0x1400ab89b  mov     [rbp+4Fh+var_68], rax
0x1400ab89f  mov     r15, [rbx+30h]
0x1400ab8a3  mov     rcx, rdi
0x1400ab8a6  call    SkpgFlushMappings
0x1400ab8ab  mov     r13d, 27h ; '''
0x1400ab8b1  mov     dword ptr [rbp+4Fh+var_78], r13d
0x1400ab8b5  mov     ecx, r13d
0x1400ab8b8  mov     rax, r12
0x1400ab8bb  shr     rax, cl
0x1400ab8be  mov     r9d, eax
0x1400ab8c1  mov     [rbp+4Fh+var_60], rax
0x1400ab8c5  and     r9d, 1FFh
0x1400ab8cc  mov     [rbp+4Fh+var_A0], r9d
0x1400ab8d0  cmp     esi, 2
0x1400ab8d3  jnb     loc_1400AB9D5
0x1400ab8d9  mov     eax, esi
0x1400ab8db  mov     ecx, [rbx+rax*4+18h]
0x1400ab8df  cmp     ecx, r9d
0x1400ab8e2  jnz     loc_1400AB994
0x1400ab8e8  mov     r15, [rbx+rax*8+20h]
0x1400ab8ed  add     [rdi+340h], r14d
0x1400ab8f4  mov     [rbp+4Fh+var_80], r15
0x1400ab8f8  mov     [rbp+rax*8+4Fh+var_50], r15
0x1400ab8fd  jmp     loc_1400ABB63
0x1400ab902  lea     r9, [rbx+8]
0x1400ab906  mov     r8, [r9]
0x1400ab909  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400ab90d  jnz     short loc_1400AB922
0x1400ab90f  mov     ecx, [rbx+4]
0x1400ab912  mov     rax, r12
0x1400ab915  shr     rax, cl
0x1400ab918  cmp     rax, [rbx+10h]
0x1400ab91c  jz      loc_1400AB868
0x1400ab922  mov     rax, r12
0x1400ab925  shr     rax, 15h
0x1400ab929  cmp     rax, r8
0x1400ab92c  jz      short loc_1400AB93B
0x1400ab92e  and     edx, 0FFFFFFFEh
0x1400ab931  mov     [rbp+4Fh+var_88], esi
0x1400ab934  mov     [rbx], edx
0x1400ab936  jmp     loc_1400AB868
0x1400ab93b  test    dl, 2
0x1400ab93e  jz      loc_1400AB868
0x1400ab944  mov     r8d, r10d
0x1400ab947  mov     rdx, rbx
0x1400ab94a  call    SkpgUpdateDirectoryCachePteTracking
0x1400ab94f  mov     eax, [rbx]
0x1400ab951  mov     r8, r12
0x1400ab954  mov     [rsp+0D0h+var_A8], rsi
0x1400ab959  mov     rcx, rdi
0x1400ab95c  mov     r9d, r10d
0x1400ab95f  mov     [rsp+0D0h+var_B0], rsi
0x1400ab964  test    al, 4
0x1400ab966  jz      short loc_1400AB983
0x1400ab968  add     [rdi+338h], r14d
0x1400ab96f  mov     edx, 9
0x1400ab974  call    SkpgLogEvent
0x1400ab979  mov     eax, 0C0000019h
0x1400ab97e  jmp     loc_1400ABD9B
0x1400ab983  add     [rdi+334h], r14d
0x1400ab98a  mov     edx, 0Ah
0x1400ab98f  jmp     loc_1400AB7F0
0x1400ab994  or      r8d, 0FFFFFFFFh
0x1400ab998  cmp     ecx, r8d
0x1400ab99b  jz      short loc_1400AB9D5
0x1400ab99d  mov     edx, esi
0x1400ab99f  cmp     edx, 2
0x1400ab9a2  jnb     short loc_1400AB9AB
0x1400ab9a4  mov     eax, edx
0x1400ab9a6  mov     [rbx+rax*4+18h], r8d
0x1400ab9ab  mov     eax, [rbx]
0x1400ab9ad  test    al, 10h
0x1400ab9af  jz      short loc_1400AB9CD
0x1400ab9b1  lea     ecx, [rdx+1]
0x1400ab9b4  mov     eax, r14d
0x1400ab9b7  shl     eax, cl
0x1400ab9b9  not     eax
0x1400ab9bb  and     [rbx+10F8h], eax
0x1400ab9c1  and     [rbx+10FCh], eax
0x1400ab9c7  and     [rbx+1100h], eax
0x1400ab9cd  add     edx, r14d
0x1400ab9d0  cmp     edx, 3
0x1400ab9d3  jb      short loc_1400AB99F
0x1400ab9d5  mov     edx, [rbx]
0x1400ab9d7  test    dl, 10h
0x1400ab9da  jz      short loc_1400ABA1B
0x1400ab9dc  mov     ecx, [rbx+10F8h]
0x1400ab9e2  mov     eax, esi
0x1400ab9e4  bt      rcx, rax
0x1400ab9e8  jnb     short loc_1400ABA1B
0x1400ab9ea  mov     eax, r9d
0x1400ab9ed  mov     cl, r9b
0x1400ab9f0  shr     rax, 3
0x1400ab9f4  and     cl, 7
0x1400ab9f7  add     rax, rbx
0x1400ab9fa  mov     r8d, esi
0x1400ab9fd  shl     r8, 6
0x1400aba01  mov     r10d, r9d
0x1400aba04  mov     r11d, esi
0x1400aba07  mov     r8b, [r8+rax+1038h]
0x1400aba0f  shr     r8b, cl
0x1400aba12  test    r14b, r8b
0x1400aba15  jnz     loc_1400ABC4B
0x1400aba1b  cmp     [rbp+4Fh+var_8C], 0
0x1400aba1f  jz      short loc_1400ABA2F
0x1400aba21  add     [rdi+34Ch], r14d
0x1400aba28  mov     [rbp+4Fh+var_8C], 0
0x1400aba2f  mov     r8d, 80h
0x1400aba35  mov     rdx, r15
0x1400aba38  mov     rcx, rdi
0x1400aba3b  call    SkpgMapPage
0x1400aba40  add     dword ptr [rdi+44h], 0C00h
0x1400aba47  mov     r15, rax
0x1400aba4a  mov     [rbp+4Fh+var_58], rax
0x1400aba4e  test    esi, esi
0x1400aba50  jnz     short loc_1400ABA70
0x1400aba52  cmp     [rbp+4Fh+var_88], esi
0x1400aba55  jz      short loc_1400ABA70
0x1400aba57  mov     r8, rax
0x1400aba5a  mov     rdx, rbx
0x1400aba5d  mov     rcx, rdi
0x1400aba60  call    SkpgVerifySelfMap
0x1400aba65  mov     r13d, eax
0x1400aba68  test    eax, eax
0x1400aba6a  js      loc_1400ABC85
0x1400aba70  mov     eax, [rbp+4Fh+var_A0]
0x1400aba73  mov     r13d, 3
0x1400aba79  sub     r13d, esi
0x1400aba7c  mov     dword ptr [rbp+4Fh+var_98], r13d
0x1400aba80  lea     r8, [r15+rax*8]
0x1400aba84  lea     r9, [rbp+4Fh+var_70]
0x1400aba88  mov     edx, r13d
0x1400aba8b  mov     rcx, rdi
0x1400aba8e  call    SkpgxReadPte
0x1400aba93  mov     r15d, eax
0x1400aba96  cmp     eax, 0C0000434h
0x1400aba9b  jnz     short loc_1400ABAB1
0x1400aba9d  mov     ecx, [rdi+0F4h]
0x1400abaa3  and     ecx, 3000h
0x1400abaa9  cmp     ecx, 1000h
0x1400abaaf  jz      short loc_1400ABA84
0x1400abab1  mov     r13d, dword ptr [rbp+4Fh+var_78]
  ... truncated ...
```
