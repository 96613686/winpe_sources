# CUtlProps::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x180090eec`
- end: `0x180091691`
- name: `?GetProperties@CUtlProps@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `1957`
- prototype: `__int64 __fastcall(CUtlProps *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180090c90`
- `0x180090e3c`
- `0x180091f70`

## callees

- `0x180038f08`
- `0x180090eec`
- `0x1800916a0`
- `0x1800954d8`
- `0x18015aa68`
- `0x180189cce`
- `0x18018a0e1`
- `0x18018a123`
- `0x1802c0010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180091140`
- `OLEAUT32!__imp_VariantInit` at `0x180091140`
- `OLEAUT32!__imp_VariantClear` at `0x1802bafd6`
- `OLEAUT32!__imp_VariantClear` at `0x1802bafd6`
- `OLEAUT32!__imp_VariantCopy` at `0x18009125e`
- `OLEAUT32!__imp_VariantCopy` at `0x180091450`
- `OLEAUT32!__imp_VariantCopy` at `0x18009125e`
- `OLEAUT32!__imp_VariantCopy` at `0x180091450`

## string_xrefs

- `0x18009148c`: `onecoreuap\base\appmodel\search\tquery\icommand\propbase.cxx`
- `0x1800912dc`: `onecoreuap\base\appmodel\search\tquery\icommand\propbase.cxx`
- `0x18009146e`: `onecoreuap\base\appmodel\search\tquery\icommand\propbase.cxx`
- `0x1800914e9`: `onecoreuap\base\appmodel\search\tquery\icommand\propbase.cxx`
- `0x180091617`: `onecoreuap\base\appmodel\search\tquery\icommand\propbase.cxx`
- `0x180091637`: `onecoreuap\base\appmodel\search\tquery\icommand\propbase.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUtlProps::GetProperties(
        CUtlProps *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  CUtlProps *v5; // r15
  int v6; // edi
  __int64 v7; // rax
  unsigned int v8; // r12d
  struct tagDBPROPSET *v9; // rax
  const wchar_t *v10; // r9
  struct tagDBPROPSET *v11; // r13
  int v12; // r8d
  unsigned int v13; // edx
  unsigned int v14; // r10d
  __int64 v15; // rcx
  unsigned int v16; // r9d
  unsigned int v17; // edx
  _QWORD *v18; // r14
  unsigned __int64 v19; // rcx
  unsigned int j; // ecx
  __int64 v21; // r8
  __int64 v22; // r10
  __int64 v23; // rdx
  _QWORD *v24; // r9
  __int64 v25; // rax
  ULONG v26; // ecx
  unsigned int i; // edx
  __int64 v28; // r8
  _QWORD *v29; // r9
  __int64 v30; // rax
  ULONG k; // eax
  __int64 v32; // r12
  __int64 v33; // r15
  __int64 v34; // r12
  unsigned __int64 v35; // rcx
  __int64 v36; // rax
  VARIANTARG *v37; // r10
  int v38; // r11d
  __int64 v39; // r9
  __int64 v40; // r10
  unsigned int n; // edx
  __int64 v42; // rcx
  char *v43; // rdx
  _WORD *v44; // r15
  HRESULT v45; // eax
  int v46; // eax
  __int64 v47; // rax
  unsigned int v49; // r8d
  __int64 v50; // r11
  __int64 v51; // r10
  __int64 v52; // r11
  unsigned int m; // r8d
  __int64 v54; // rcx
  VARIANTARG *v55; // r12
  HRESULT v56; // eax
  __int64 v57; // rax
  __int64 v58; // rax
  int v59; // eax
  int v60; // [rsp+20h] [rbp-A8h]
  unsigned int v61; // [rsp+30h] [rbp-98h]
  ULONG v62; // [rsp+34h] [rbp-94h]
  unsigned int v63; // [rsp+38h] [rbp-90h]
  ULONG cPropertyIDs; // [rsp+3Ch] [rbp-8Ch]
  ULONG v65; // [rsp+40h] [rbp-88h]
  unsigned int v66; // [rsp+44h] [rbp-84h]
  unsigned int v67; // [rsp+4Ch] [rbp-7Ch] BYREF
  unsigned int v68; // [rsp+50h] [rbp-78h]
  VARIANTARG *v69; // [rsp+58h] [rbp-70h]
  int v70; // [rsp+60h] [rbp-68h]
  _QWORD *v71; // [rsp+68h] [rbp-60h] BYREF
  unsigned __int64 v72; // [rsp+70h] [rbp-58h]
  __int64 v73; // [rsp+78h] [rbp-50h]
  struct tagDBPROPSET *v74; // [rsp+80h] [rbp-48h]
  LPVOID pv; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  unsigned int v78; // [rsp+D8h] [rbp+10h]

  v78 = a2;
  v5 = this;
  v67 = 0;
  LOBYTE(v6) = 0;
  if ( (*((_BYTE *)this + 84) & 1) != 0 && a3 )
  {
    v7 = *(_QWORD *)&a3->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_PROPERTIESINERROR.Data1;
    if ( !v7 )
      v7 = *(_QWORD *)a3->guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_PROPERTIESINERROR.Data4;
    if ( !v7 )
    {
      v78 = 0;
      LOBYTE(v6) = 16;
LABEL_9:
      v8 = *((_DWORD *)this + 12);
      v66 = v8;
      if ( !v8 )
        return 0;
      goto LABEL_10;
    }
  }
  if ( !a2 )
    goto LABEL_9;
  v8 = a2;
  v66 = a2;
LABEL_10:
  v9 = (struct tagDBPROPSET *)WINRT_IMPL_CoTaskMemAlloc(32LL * v8);
  v11 = v9;
  pv = v9;
  if ( !v9 )
  {
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\propbase.cxx",
      (const wchar_t *)0x130,
      (unsigned int)L"[Query] Could not allocate DBPROPSET array for GetProperties\n",
      v10);
    return 2147942414LL;
  }
  v74 = v9;
  v61 = 0;
  memset_0(v9, 0, 32LL * v8);
  v12 = 0;
  v13 = 0;
  v14 = v78;
  do
  {
    v15 = v13;
    if ( v78 )
    {
      v11[v12].guidPropertySet = a3[v15].guidPropertySet;
LABEL_14:
      ++v12;
      goto LABEL_15;
    }
    v57 = *((_QWORD *)v5 + 7);
    if ( (*(_BYTE *)(v57 + v15 * 32 + 24) & 1) == 0 )
    {
      v11[v12].guidPropertySet = *(GUID *)*(_QWORD *)(v57 + 32LL * v13);
      goto LABEL_14;
    }
LABEL_15:
    ++v13;
  }
  while ( v13 < v8 );
  v16 = 0;
  v63 = 0;
  v17 = 0;
  while ( 1 )
  {
    v68 = v17;
    if ( v17 >= v8 )
      break;
    v71 = 0;
    v18 = 0;
    v62 = 0;
    v6 &= 0x1Cu;
    v19 = 32LL * v17;
    v72 = v19;
    if ( v14 )
    {
      cPropertyIDs = a3[v19 / 0x20].cPropertyIDs;
      if ( cPropertyIDs )
      {
        for ( i = 0; i < *((_DWORD *)v5 + 12); ++i )
        {
          v28 = v16;
          v29 = *(_QWORD **)(32LL * i + *((_QWORD *)v5 + 7));
          v30 = *(_QWORD *)&v11[v28].guidPropertySet.Data1 - *v29;
          if ( !v30 )
            v30 = *(_QWORD *)v11[v28].guidPropertySet.Data4 - v29[1];
          if ( !v30 )
          {
            v61 = i;
            goto LABEL_35;
          }
          v16 = v63;
        }
        v6 |= 6u;
LABEL_35:
        v26 = a3[v19 / 0x20].cPropertyIDs;
        goto LABEL_36;
      }
      for ( j = 0; ; ++j )
      {
        if ( j >= *((_DWORD *)v5 + 12) )
        {
          LOBYTE(v6) = v6 | 5;
          goto LABEL_63;
        }
        v21 = 32LL * j;
        v22 = *((_QWORD *)v5 + 7);
        v23 = v16;
        v24 = *(_QWORD **)(v21 + v22);
        v25 = *(_QWORD *)&v11[v23].guidPropertySet.Data1 - *v24;
        if ( !v25 )
          v25 = *(_QWORD *)v11[v23].guidPropertySet.Data4 - v24[1];
        v16 = v63;
        if ( !v25 )
          break;
      }
      v61 = j;
      v26 = *(_DWORD *)(v21 + v22 + 8);
    }
    else
    {
      v58 = *((_QWORD *)v5 + 7);
      if ( (*(_BYTE *)(v58 + v19 + 24) & 1) != 0 )
      {
        XCoMem<unsigned char>::~XCoMem<unsigned char>(&v71);
        v16 = v63;
        goto LABEL_64;
      }
      v26 = *(_DWORD *)(v58 + v19 + 8);
      v61 = v17;
    }
    cPropertyIDs = v26;
    v6 |= 1u;
    if ( !v26 )
      goto LABEL_63;
LABEL_36:
    v18 = WINRT_IMPL_CoTaskMemAlloc(72LL * v26);
    v71 = v18;
    if ( !v18 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\propbase.cxx",
        (const char *)0x8007000ELL,
        v60);
    for ( k = 0; ; k = v65 + 1 )
    {
      v65 = k;
      if ( k >= cPropertyIDs )
        break;
      v32 = k;
      v33 = 9LL * k;
      v18[v33] = 0;
      LODWORD(v18[v33 + 1]) = 0;
      *(_OWORD *)&v18[v33 + 2] = 0;
      *(_OWORD *)&v18[v33 + 4] = 0;
      VariantInit((VARIANTARG *)&v18[v33 + 6]);
      if ( (v6 & 2) != 0 )
      {
        LODWORD(v18[v33]) = (*(DBPROPID **)((char *)&a3->rgPropertyIDs + v72))[v32];
        LODWORD(v18[v33 + 1]) = 1;
        v5 = this;
      }
      else
      {
        v34 = 9LL * v62;
        LODWORD(v18[9 * v62 + 1]) = 0;
        v5 = this;
        if ( (v6 & 1) == 0 )
        {
          v49 = (*(DBPROPID **)((char *)&a3->rgPropertyIDs + v72))[v65];
          LODWORD(v18[9 * v62]) = v49;
          *(DBID *)&v18[9 * v62 + 2] = DB_NULLID;
          if ( (unsigned int)CUtlProps::GetIndexofPropIdinPropSet(this, v61, v49, &v67) )
          {
            LODWORD(v18[9 * v62 + 1]) = 1;
            v6 |= 4u;
          }
          else
          {
            v50 = *(_QWORD *)(32LL * v61 + *((_QWORD *)this + 7) + 16);
            if ( (*(_DWORD *)(v50 + 24LL * v67 + 20) & 0x80000400) != 0 )
            {
              v51 = *((_QWORD *)this + 8);
              v52 = *(_QWORD *)(v51 + 24LL * v61 + 16);
              for ( m = 0; m < *(_DWORD *)(v51 + 24LL * v61); ++m )
              {
                if ( **(_DWORD **)(*(_QWORD *)(v51 + 24LL * v61 + 8) + 8LL * m) == LODWORD(v18[9 * v62]) )
                  goto LABEL_75;
              }
              m = 0;
LABEL_75:
              v54 = 32LL * m;
              HIDWORD(v18[9 * v62]) = *(_DWORD *)(v54 + v52);
              v55 = (VARIANTARG *)&v18[v34 + 6];
              v56 = VariantCopy(v55, (const VARIANTARG *)(v54 + v52 + 8));
            }
            else
            {
              v69 = (VARIANTARG *)&v18[v34 + 6];
              v55 = v69;
              v60 = (int)v69;
              v56 = (*(__int64 (__fastcall **)(CUtlProps *, _QWORD, _QWORD, __int64))(*(_QWORD *)this + 32LL))(
                      this,
                      v61,
                      *(unsigned int *)(v50 + 24LL * v67),
                      (__int64)&v18[9 * v62] + 4);
            }
            if ( v56 < 0 )
            {
              v55->vt = 0;
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x212,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\propbase.cxx",
                (const char *)(unsigned int)v56,
                v60);
            }
LABEL_54:
            v6 |= 8u;
          }
          ++v62;
          continue;
        }
        v35 = ((unsigned __int64)v65 >> 5) + *((_DWORD *)this + 2) * v61;
        if ( ((1 << v65) & *(_DWORD *)(*((_QWORD *)this + 2) + 4 * v35)) != 0 )
        {
          v70 = v6 & 0x10;
          if ( (v6 & 0x10) == 0 || ((1 << v65) & *(_DWORD *)(*((_QWORD *)this + 4) + 4 * v35)) != 0 )
          {
            v36 = *((_QWORD *)this + 7);
            v73 = 3LL * v65;
            v37 = *(VARIANTARG **)(32LL * v61 + v36 + 16);
            v69 = v37;
            v38 = *(_DWORD *)&v37[v65].vt;
            LODWORD(v18[9 * v62]) = v38;
            *(DBID *)&v18[9 * v62 + 2] = DB_NULLID;
            if ( (*((_DWORD *)&v37[v65].decVal + 5) & 0x80000400) != 0 )
            {
              v39 = *((_QWORD *)this + 8);
              v40 = *(_QWORD *)(v39 + 24LL * v61 + 16);
              for ( n = 0; n < *(_DWORD *)(v39 + 24LL * v61); ++n )
              {
                if ( **(_DWORD **)(*(_QWORD *)(v39 + 24LL * v61 + 8) + 8LL * n) == v38 )
                  goto LABEL_49;
              }
              n = 0;
LABEL_49:
              v42 = 32LL * n;
              v43 = (char *)&v18[9 * v62];
              v44 = &v18[v34 + 6];
              if ( (*(_DWORD *)(v42 + v40 + 4) & 4) != 0 )
              {
                v60 = (_DWORD)v18 + 8 * (v34 + 6);
                v59 = (*(__int64 (__fastcall **)(CUtlProps *, _QWORD, _QWORD, char *))(*(_QWORD *)this + 32LL))(
                        this,
                        v61,
                        *(unsigned int *)&v69[(unsigned __int64)v73 / 3].vt,
                        v43 + 4);
                if ( v59 < 0 )
                {
                  *v44 = 0;
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1CD,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\propbase.cxx",
                    (const char *)(unsigned int)v59,
                    v60);
                }
              }
              else
              {
                *((_DWORD *)v43 + 1) = *(_DWORD *)(v42 + v40);
                v45 = VariantCopy((VARIANTARG *)&v18[v34 + 6], (const VARIANTARG *)(v42 + v40 + 8));
                if ( v45 < 0 )
                {
                  *v44 = 0;
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1D8,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\propbase.cxx",
                    (const char *)(unsigned int)v45,
                    v60);
                }
              }
              v5 = this;
            }
            else
            {
              v69 = (VARIANTARG *)&v18[v34 + 6];
              v60 = (_DWORD)v18 + 8 * (v34 + 6);
              v46 = (*(__int64 (__fastcall **)(CUtlProps *, _QWORD, _QWORD, __int64))(*(_QWORD *)this + 32LL))(
                      this,
                      v61,
                      *(unsigned int *)&v37[v65].vt,
                      (__int64)&v18[9 * v62] + 4);
              if ( v46 < 0 )
              {
                v69->vt = 0;
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1E3,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\propbase.cxx",
                  (const char *)(unsigned int)v46,
                  v60);
              }
            }
            if ( v70 )
              LODWORD(v18[9 * v62 + 1]) = 8;
            goto LABEL_54;
          }
        }
      }
    }
    if ( (v6 & 2) != 0 )
    {
      v62 = cPropertyIDs;
    }
    else if ( !v62 )
    {
      CoTaskMemFree_0(v18);
      v18 = 0;
    }
    v8 = v66;
    v16 = v63;
LABEL_63:
    v47 = v16;
    v11[v47].cProperties = v62;
    v11[v47].rgProperties = (DBPROP *)v18;
    v63 = ++v16;
LABEL_64:
    v17 = v68 + 1;
    v14 = v78;
  }
  *a4 = v16;
  *a5 = v11;
  if ( (v6 & 4) == 0 )
    return 0;
  if ( (v6 & 8) != 0 )
    return 265946;
  return 2147749409LL;
}

```

## disassembly

```asm
0x180090eec  mov     rax, rsp
0x180090eef  mov     [rax+20h], r9
0x180090ef3  mov     [rax+18h], r8
0x180090ef7  mov     [rax+10h], edx
0x180090efa  mov     [rax+8], rcx
0x180090efe  push    rbx
0x180090eff  push    rsi
0x180090f00  push    rdi
0x180090f01  push    r12
0x180090f03  push    r13
0x180090f05  push    r14
0x180090f07  push    r15
0x180090f09  sub     rsp, 90h
0x180090f10  mov     r15, rcx
0x180090f13  xor     ebx, ebx
0x180090f15  mov     [rax-7Ch], ebx
0x180090f18  mov     edi, ebx
0x180090f1a  lea     esi, [rbx+1]
0x180090f1d  test    [rcx+54h], sil
0x180090f21  jz      short loc_180090F45
0x180090f23  test    r8, r8
0x180090f26  jz      short loc_180090F45
0x180090f28  mov     rax, [r8+0Ch]
0x180090f2c  sub     rax, qword ptr cs:DBPROPSET_PROPERTIESINERROR.Data1
0x180090f33  jnz     short loc_180090F40
0x180090f35  mov     rax, [r8+14h]
0x180090f39  sub     rax, qword ptr cs:DBPROPSET_PROPERTIESINERROR.Data4
0x180090f40  test    rax, rax
0x180090f43  jz      short loc_180090F52
0x180090f45  test    edx, edx
0x180090f47  jz      short loc_180090F5E
0x180090f49  mov     r12d, edx
0x180090f4c  mov     [rsp+0C8h+var_84], edx
0x180090f50  jmp     short loc_180090F70
0x180090f52  mov     [rsp+0C8h+arg_8], ebx
0x180090f59  mov     edi, 10h
0x180090f5e  mov     r12d, [rcx+30h]
0x180090f62  mov     [rsp+0C8h+var_84], r12d
0x180090f67  test    r12d, r12d
0x180090f6a  jz      loc_180091557
0x180090f70  mov     [rsp+0C8h+var_80], r12d
0x180090f75  mov     r14d, r12d
0x180090f78  shl     r14, 5
0x180090f7c  mov     rcx, r14; cb
0x180090f7f  call    WINRT_IMPL_CoTaskMemAlloc
0x180090f84  mov     r13, rax
0x180090f87  mov     [rsp+0C8h+pv], rax
0x180090f8f  test    rax, rax
0x180090f92  jz      loc_180091480
0x180090f98  mov     [rsp+0C8h+var_48], rax
0x180090fa0  mov     [rsp+0C8h+var_98], ebx
0x180090fa4  mov     r8, r14; Size
0x180090fa7  xor     edx, edx; Val
0x180090fa9  mov     rcx, rax; void *
0x180090fac  call    memset_0
0x180090fb1  mov     r8d, ebx
0x180090fb4  mov     edx, ebx
0x180090fb6  mov     r10d, [rsp+0C8h+arg_8]
0x180090fbe  test    r12d, r12d
0x180090fc1  jz      short loc_180090FF8
0x180090fc3  mov     r9, [rsp+0C8h+arg_10]
0x180090fcb  mov     ecx, edx
0x180090fcd  shl     rcx, 5
0x180090fd1  test    r10d, r10d
0x180090fd4  jz      loc_1800914A2
0x180090fda  mov     eax, r8d
0x180090fdd  shl     rax, 5
0x180090fe1  movups  xmm0, xmmword ptr [r9+rcx+0Ch]
0x180090fe7  movdqu  xmmword ptr [rax+r13+0Ch], xmm0
0x180090fee  add     r8d, esi
0x180090ff1  add     edx, esi
0x180090ff3  cmp     edx, r12d
0x180090ff6  jb      short loc_180090FCB
0x180090ff8  mov     r9d, ebx
0x180090ffb  mov     [rsp+0C8h+var_90], ebx
0x180090fff  mov     edx, ebx
0x180091001  mov     [rsp+0C8h+var_78], edx
0x180091005  cmp     edx, r12d
0x180091008  jnb     loc_18009134F
0x18009100e  mov     [rsp+0C8h+var_60], rbx
0x180091013  mov     r14, rbx
0x180091016  mov     [rsp+0C8h+var_94], ebx
0x18009101a  and     edi, 1Ch
0x18009101d  mov     ecx, edx
0x18009101f  shl     rcx, 5
0x180091023  mov     [rsp+0C8h+var_58], rcx
0x180091028  test    r10d, r10d
0x18009102b  jz      loc_18009155E
0x180091031  mov     rax, [rsp+0C8h+arg_10]
0x180091039  mov     ecx, [rcx+rax+8]
0x18009103d  mov     [rsp+0C8h+var_8C], ecx
0x180091041  test    ecx, ecx
0x180091043  jnz     short loc_1800910A2
0x180091045  mov     ecx, ebx
0x180091047  cmp     ecx, [r15+30h]
0x18009104b  jnb     loc_1800914CB
0x180091051  mov     r8d, ecx
0x180091054  shl     r8, 5
0x180091058  mov     r10, [r15+38h]
0x18009105c  mov     edx, r9d
0x18009105f  shl     rdx, 5
0x180091063  mov     r9, [r8+r10]
0x180091067  mov     rax, [rdx+r13+0Ch]
0x18009106c  sub     rax, [r9]
0x18009106f  jnz     short loc_18009107A
0x180091071  mov     rax, [rdx+r13+14h]
0x180091076  sub     rax, [r9+8]
0x18009107a  mov     r9d, [rsp+0C8h+var_90]
0x18009107f  test    rax, rax
0x180091082  jz      short loc_180091088
0x180091084  add     ecx, esi
0x180091086  jmp     short loc_180091047
0x180091088  mov     [rsp+0C8h+var_98], ecx
0x18009108c  mov     ecx, [r8+r10+8]
0x180091091  mov     eax, esi
0x180091093  mov     [rsp+0C8h+var_8C], ecx
0x180091097  or      edi, eax
0x180091099  test    ecx, ecx
0x18009109b  jnz     short loc_1800910E7
0x18009109d  jmp     loc_180091314
0x1800910a2  mov     edx, ebx
0x1800910a4  cmp     edx, [r15+30h]
0x1800910a8  jnb     loc_1800914D3
0x1800910ae  mov     ecx, edx
0x1800910b0  shl     rcx, 5
0x1800910b4  mov     rax, [r15+38h]
0x1800910b8  mov     r8d, r9d
0x1800910bb  shl     r8, 5
0x1800910bf  mov     r9, [rcx+rax]
0x1800910c3  mov     rax, [r8+r13+0Ch]
0x1800910c8  sub     rax, [r9]
0x1800910cb  jnz     short loc_1800910D6
0x1800910cd  mov     rax, [r8+r13+14h]
0x1800910d2  sub     rax, [r9+8]
0x1800910d6  test    rax, rax
0x1800910d9  jnz     loc_180091343
0x1800910df  mov     [rsp+0C8h+var_98], edx
0x1800910e3  mov     ecx, [rsp+0C8h+var_8C]
0x1800910e7  mov     eax, ecx
0x1800910e9  lea     rcx, [rax+rax*8]
0x1800910ed  shl     rcx, 3; cb
0x1800910f1  call    WINRT_IMPL_CoTaskMemAlloc
0x1800910f6  mov     r14, rax
0x1800910f9  mov     [rsp+0C8h+var_60], rax
0x1800910fe  test    rax, rax
0x180091101  jz      loc_1800914DB
0x180091107  mov     eax, ebx
0x180091109  mov     [rsp+0C8h+var_88], eax
0x18009110d  mov     ecx, [rsp+0C8h+var_8C]
0x180091111  cmp     eax, ecx
0x180091113  jnb     loc_1800912ED
0x180091119  mov     r12d, eax
0x18009111c  lea     r15, [r12+r12*8]
0x180091120  mov     [r14+r15*8], rbx
0x180091124  mov     [r14+r15*8+8], ebx
0x180091129  xorps   xmm0, xmm0
0x18009112c  movups  xmmword ptr [r14+r15*8+10h], xmm0
0x180091132  movups  xmmword ptr [r14+r15*8+20h], xmm0
0x180091138  lea     rcx, [r15+6]
0x18009113c  lea     rcx, [r14+rcx*8]; pvarg
0x180091140  call    cs:__imp_VariantInit
0x180091146  test    dil, 2
0x18009114a  jnz     loc_180091580
0x180091150  mov     eax, [rsp+0C8h+var_94]
0x180091154  lea     r12, [rax+rax*8]
0x180091158  mov     [r14+r12*8+8], ebx
0x18009115d  mov     eax, edi
0x18009115f  and     eax, esi
0x180091161  mov     r9d, [rsp+0C8h+var_88]
0x180091166  mov     r15, [rsp+0C8h+arg_0]
0x18009116e  test    al, al
0x180091170  jz      loc_180091384
0x180091176  mov     ecx, r9d
0x180091179  mov     edx, esi
0x18009117b  shl     edx, cl
0x18009117d  mov     r10d, [rsp+0C8h+var_98]
0x180091182  mov     ecx, r10d
0x180091185  imul    ecx, [r15+8]
0x18009118a  mov     eax, r9d
0x18009118d  shr     rax, 5
0x180091191  add     rcx, rax
0x180091194  mov     rax, [r15+10h]
0x180091198  test    [rax+rcx*4], edx
0x18009119b  jz      loc_180091285
0x1800911a1  mov     eax, edi
0x1800911a3  and     eax, 10h
0x1800911a6  mov     [rsp+0C8h+var_68], eax
0x1800911aa  jnz     loc_1800915AB
0x1800911b0  mov     rdx, r10
0x1800911b3  mov     rcx, r10
0x1800911b6  shl     rcx, 5
0x1800911ba  mov     rax, [r15+38h]
0x1800911be  lea     r8, [r9+r9*2]
0x1800911c2  mov     [rsp+0C8h+var_50], r8
0x1800911c7  mov     r10, [rcx+rax+10h]
0x1800911cc  mov     [rsp+0C8h+var_70], r10
0x1800911d1  mov     r11d, [r10+r8*8]
0x1800911d5  mov     [r14+r12*8], r11d
0x1800911d9  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x1800911e0  movups  xmmword ptr [r14+r12*8+10h], xmm0
0x1800911e6  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x1800911ed  movups  xmmword ptr [r14+r12*8+20h], xmm1
0x1800911f3  test    dword ptr [r10+r8*8+14h], 80000400h
0x1800911fc  jz      loc_180091290
0x180091202  lea     r8, [rdx+rdx*2]
0x180091206  mov     r9, [r15+40h]
0x18009120a  mov     r10, [r9+r8*8+10h]
0x18009120f  mov     edx, ebx
0x180091211  cmp     edx, [r9+r8*8]
0x180091215  jnb     short loc_18009122B
0x180091217  mov     ecx, edx
0x180091219  mov     rax, [r9+r8*8+8]
0x18009121e  mov     rcx, [rax+rcx*8]
0x180091222  cmp     [rcx], r11d
0x180091225  jz      short loc_18009122D
0x180091227  add     edx, esi
0x180091229  jmp     short loc_180091211
0x18009122b  mov     edx, ebx
0x18009122d  mov     ecx, edx
0x18009122f  shl     rcx, 5
0x180091233  lea     rdx, [r14+r12*8]
0x180091237  lea     r15, [r12+6]
0x18009123c  lea     r15, [r14+r15*8]
0x180091240  mov     eax, [rcx+r10+4]
0x180091245  test    al, 4
0x180091247  jnz     loc_1800915D1
0x18009124d  mov     eax, [rcx+r10]
0x180091251  mov     [rdx+4], eax
0x180091254  lea     rdx, [r10+8]
0x180091258  add     rdx, rcx; pvargSrc
0x18009125b  mov     rcx, r15; pvargDest
0x18009125e  call    cs:__imp_VariantCopy
0x180091264  test    eax, eax
0x180091266  js      loc_180091628
0x18009126c  mov     r15, [rsp+0C8h+arg_0]
0x180091274  cmp     [rsp+0C8h+var_68], ebx
0x180091278  jnz     loc_180091648
0x18009127e  or      edi, 8
0x180091281  add     [rsp+0C8h+var_94], esi
0x180091285  mov     eax, [rsp+0C8h+var_88]
0x180091289  add     eax, esi
0x18009128b  jmp     loc_180091109
0x180091290  lea     rcx, [r12+6]
0x180091295  lea     rcx, [r14+rcx*8]
0x180091299  mov     [rsp+0C8h+var_70], rcx
0x18009129e  mov     rax, [r15]
0x1800912a1  lea     r9, ds:4[r12*8]
0x1800912a9  add     r9, r14
0x1800912ac  mov     qword ptr [rsp+0C8h+var_A8], rcx; int
0x1800912b1  mov     r8d, [r10+r8*8]
0x1800912b5  mov     edx, [rsp+0C8h+var_98]
0x1800912b9  mov     rcx, r15
0x1800912bc  mov     rax, [rax+20h]
0x1800912c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800912c5  test    eax, eax
0x1800912c7  jns     short loc_180091274
0x1800912c9  mov     rcx, [rsp+0C8h+var_70]
0x1800912ce  mov     [rcx], bx
0x1800912d1  mov     rcx, [rsp+0C8h]; this
0x1800912d9  mov     r9d, eax; char *
0x1800912dc  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800912e3  mov     edx, 1E3h; void *
0x1800912e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800912ed  test    dil, 2
0x1800912f1  jnz     loc_180091656
0x1800912f7  mov     r12d, [rsp+0C8h+var_94]
0x1800912fc  test    r12d, r12d
0x1800912ff  jz      loc_18009165F
0x180091305  mov     [rsp+0C8h+var_94], r12d
0x18009130a  mov     r12d, [rsp+0C8h+var_84]
0x18009130f  mov     r9d, [rsp+0C8h+var_90]
0x180091314  mov     eax, r9d
0x180091317  shl     rax, 5
0x18009131b  mov     ecx, [rsp+0C8h+var_94]
0x18009131f  mov     [rax+r13+8], ecx
0x180091324  mov     [rax+r13], r14
0x180091328  add     r9d, esi
0x18009132b  mov     [rsp+0C8h+var_90], r9d
0x180091330  mov     edx, [rsp+0C8h+var_78]
0x180091334  add     edx, esi
0x180091336  mov     r10d, [rsp+0C8h+arg_8]
0x18009133e  jmp     loc_180091001
0x180091343  add     edx, esi
0x180091345  mov     r9d, [rsp+0C8h+var_90]
0x18009134a  jmp     loc_1800910A4
0x18009134f  mov     rax, [rsp+0C8h+arg_18]
0x180091357  mov     [rax], r9d
0x18009135a  mov     rax, [rsp+0C8h+arg_20]
0x180091362  mov     [rax], r13
0x180091365  test    dil, 4
0x180091369  jnz     loc_1800914FB
0x18009136f  mov     eax, ebx
0x180091371  add     rsp, 90h
0x180091378  pop     r15
0x18009137a  pop     r14
0x18009137c  pop     r13
0x18009137e  pop     r12
0x180091380  pop     rdi
0x180091381  pop     rsi
0x180091382  pop     rbx
  ... truncated ...
```
