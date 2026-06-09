# CSchema_Table_Statistics::FInit(ulong,tagVARIANT const * const,ulong,tagDBPROPSET * const,_GUID const &,IUnknown *,IUnknown * *)

- ea: `0x3839ffb70`
- end: `0x383a0063b`
- name: `?FInit@CSchema_Table_Statistics@@UEAAJKQEBUtagVARIANT@@KQEAUtagDBPROPSET@@AEBU_GUID@@PEAUIUnknown@@PEAPEAU5@@Z`
- size: `2763`
- prototype: `__int64 __usercall@<rax>(CSchema_Table_Statistics *__hidden this@<rcx>, unsigned int@<edx>, const struct tagVARIANT *const@<r8>, unsigned int@<r9d>, struct tagDBPROPSET *const, const struct _GUID *, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x3838435e0`
- `0x383849aa0`
- `0x383849f80`
- `0x38384a040`
- `0x38384c670`
- `0x38384d2c0`
- `0x38384f2e0`
- `0x38384f470`
- `0x3838588d0`
- `0x383858c30`
- `0x38391aed0`
- `0x38391afe0`
- `0x3839bd900`
- `0x3839fbff0`
- `0x3839ffb70`
- `0x383a02c50`
- `0x383a9a318`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x3839ffcfa`
- `OLEAUT32!__imp_VariantInit` at `0x3839ffcfa`
- `OLEAUT32!__imp_VariantCopy` at `0x3839ffd56`
- `OLEAUT32!__imp_VariantCopy` at `0x3839ffd56`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSchema_Table_Statistics::FInit(
        struct CBaseObj **this,
        unsigned int a2,
        const struct tagVARIANT *const a3,
        unsigned int a4,
        struct tagDBPROPSET *const a5,
        struct _GUID *a6,
        struct IUnknown *a7,
        struct IUnknown **a8)
{
  unsigned __int64 v9; // rbp
  unsigned int v11; // r15d
  unsigned int v12; // r13d
  CRowsetProps *v13; // rdi
  int v14; // eax
  ULONG *p_cProperties; // r9
  HRESULT v16; // ebx
  unsigned __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rbx
  const struct tagVARIANT *v23; // rsi
  unsigned int v24; // r10d
  ULONG v25; // ecx
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // rax
  bool v29; // cf
  unsigned __int64 v30; // rdx
  int v31; // eax
  bool v32; // cf
  unsigned __int64 v33; // rdx
  int v34; // eax
  bool v35; // cf
  unsigned __int64 v36; // rdx
  int v37; // eax
  bool v38; // cf
  unsigned __int64 v39; // rdx
  int v40; // eax
  bool v41; // cf
  unsigned __int64 v42; // rdx
  int v43; // eax
  bool v44; // cf
  unsigned __int64 v45; // rdx
  int v46; // eax
  int v47; // eax
  CRowset *v48; // rax
  CRowset *v49; // r15
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // rdx
  struct tagDISPPARAMS *v53; // [rsp+20h] [rbp-78h]
  __int64 v54; // [rsp+50h] [rbp-48h] BYREF
  CRowset *v55; // [rsp+58h] [rbp-40h]
  __int64 v56; // [rsp+60h] [rbp-38h]
  __int64 v57; // [rsp+68h] [rbp-30h]

  v56 = -2;
  v9 = a2;
  v11 = 0;
  v12 = 0;
  v54 = 0;
  v55 = 0;
  v13 = 0;
  v14 = CCommand::FInit((CCommand *)this, 0, 0);
  v16 = v14;
  if ( v14 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
      {
        LODWORD(v53) = 2230;
        bidTraceW(off_383B43338[0], 2283561, off_383B49128[0], (unsigned int)v14);
      }
      goto LABEL_135;
    }
    goto LABEL_152;
  }
  *((GUID *)this + 79) = IID_IDBSchemaRowset;
  CCommand::ApplyGeneralTimeout((CCommand *)this);
  if ( (_DWORD)v9 )
  {
    *((_DWORD *)this + 388) = v9;
    v17 = v9;
    v18 = 24 * v9;
    if ( !is_mul_ok(v9, 0x18u) )
      v18 = -1;
    v19 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v18);
    this[195] = (struct CBaseObj *)v19;
    if ( v19 )
    {
      v22 = 0;
      do
      {
        VariantInit((VARIANTARG *)((char *)this[195] + v22));
        v22 += 24;
        --v17;
      }
      while ( v17 );
      v23 = a3;
      while ( 1 )
      {
        switch ( v23->vt )
        {
          case 0u:
          case 1u:
          case 2u:
          case 3u:
          case 8u:
          case 0xBu:
          case 0x10u:
          case 0x11u:
          case 0x12u:
          case 0x13u:
          case 0x16u:
          case 0x17u:
            v16 = VariantCopy((VARIANTARG *)this[195] + v11, &a3[v11]);
            if ( v16 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( off_383B49128[0] )
                {
                  LODWORD(v53) = 2271;
                  bidTraceW(off_383B43338[0], 2325545, off_383B49128[0], (unsigned int)v16);
                }
                goto LABEL_135;
              }
              goto LABEL_152;
            }
            ++v11;
            ++v23;
            if ( v11 >= (unsigned int)v9 )
              goto LABEL_27;
            break;
          default:
            v16 = -2147024809;
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_152;
            if ( off_383B49128[0] )
            {
              LODWORD(v53) = 2275;
              bidTraceW(off_383B43338[0], 2329641, off_383B49128[0], 2147942487LL);
            }
            goto LABEL_135;
        }
      }
    }
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    {
      LODWORD(v53) = 2245;
      bidTraceW(off_383B43338[0], 2298921, off_383B49128[0], 2147942414LL);
    }
    v16 = -2147024882;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_152;
    v20 = 2299913;
    v21 = 2147942414LL;
LABEL_134:
    bidTraceHR(off_383B43338[0], v20, v21);
    goto LABEL_135;
  }
LABEL_27:
  if ( a4 )
  {
    v16 = (*(__int64 (__fastcall **)(struct CBaseObj **, GUID *, __int64 *))*this)(this, &IID_ICommandProperties, &v54);
    if ( v16 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_383B49128[0] )
        {
          LODWORD(v53) = 2285;
          bidTraceW(off_383B43338[0], 2339881, off_383B49128[0], (unsigned int)v16);
        }
        goto LABEL_135;
      }
      goto LABEL_152;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagDBPROPSET *const))(*(_QWORD *)v54 + 32LL))(v54, a4, a5);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    if ( v16 == -2147217887 || v16 == 265946 )
    {
      v24 = 0;
      if ( a4 )
      {
        p_cProperties = &a5->cProperties;
        while ( 1 )
        {
          v25 = 0;
          if ( *p_cProperties )
            break;
LABEL_44:
          ++v24;
          p_cProperties += 8;
          if ( v24 >= a4 )
            goto LABEL_50;
        }
        v26 = *((_QWORD *)p_cProperties - 1);
        v27 = 0;
        while ( !*(_DWORD *)(v26 + v27 + 8) || *(_DWORD *)(v26 + v27 + 4) == 1 )
        {
          ++v25;
          v27 += 72;
          if ( v25 >= *p_cProperties )
            goto LABEL_44;
        }
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        {
          LODWORD(v53) = 2303;
          bidTraceW(off_383B43338[0], 2358313, off_383B49128[0], 2147749409LL);
        }
        v16 = -2147217887;
LABEL_135:
        if ( (bidGblFlags & 2) != 0 )
        {
          v50 = 2489353;
          if ( (v16 || (bidGblFlags & 0x40) != 0) && off_383B49128[0] )
          {
            if ( v16 < 0 )
              v50 = 2489385;
            LODWORD(v53) = v50 >> 10;
            bidTraceW(off_383B43338[0], v50, off_383B49128[0], (unsigned int)v16);
          }
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_383B49550[0] )
            {
              LODWORD(v53) = v16;
              bidTraceW(off_383B43260[0], 1388544, off_383B49550[0], &IID_IDBSchemaRowset);
            }
            if ( (bidGblFlags & 2) != 0 )
            {
              v51 = 1390601;
              if ( v16 || (bidGblFlags & 0x40) != 0 )
              {
                if ( off_383B49128[0] )
                {
                  if ( v16 < 0 )
                    v51 = 1390633;
                  LODWORD(v53) = v51 >> 10;
                  bidTraceW(off_383B43260[0], v51, off_383B49128[0], (unsigned int)v16);
                }
              }
            }
          }
        }
LABEL_152:
        CError::PostErrorInternal(
          (CError *)(unsigned int)v16,
          (int)&IID_IDBSchemaRowset,
          (const struct _GUID *)0x10000000,
          (unsigned int)p_cProperties,
          v53);
        goto LABEL_153;
      }
LABEL_50:
      v12 = 265946;
    }
    else if ( v16 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_152;
      v21 = (unsigned int)v16;
      v20 = 2367497;
      goto LABEL_134;
    }
  }
  v28 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 688);
  v13 = (CRowsetProps *)v28;
  v57 = v28;
  if ( v28 )
  {
    *(_QWORD *)(v28 + 12) = 1;
    *(_DWORD *)(v28 + 40) = 0;
    *(_DWORD *)(v28 + 8) = 0;
    *(_QWORD *)(v28 + 32) = 0;
    *(_QWORD *)(v28 + 48) = 0;
    *(_DWORD *)(v28 + 296) = 0;
    *(_QWORD *)(v28 + 560) = 0;
    *(_QWORD *)(v28 + 568) = 0;
    *(_QWORD *)(v28 + 24) = 0;
    *(_QWORD *)v28 = &CRowsetProps::`vftable';
    *(_QWORD *)(v28 + 576) = 0;
    *(_QWORD *)(v28 + 584) = 0;
    *(_DWORD *)(v28 + 676) = -1;
    *(_QWORD *)(v28 + 680) = 0;
    memset((void *)(v28 + 592), 0, 0x54u);
  }
  else
  {
    v13 = 0;
  }
  if ( !v13 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    {
      LODWORD(v53) = 2320;
      bidTraceW(off_383B43338[0], 2375721, off_383B49128[0], 2147942414LL);
    }
LABEL_58:
    v16 = -2147024882;
    goto LABEL_135;
  }
  v16 = CRowsetProps::FInit(v13, (struct CCommand *)this, (const struct CRowsetProps *)(this + 56), 0);
  if ( v16 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
      {
        LODWORD(v53) = 2324;
        bidTraceW(off_383B43338[0], 2379817, off_383B49128[0], (unsigned int)v16);
      }
      goto LABEL_135;
    }
    goto LABEL_152;
  }
  v29 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IRowset.Data1;
  if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IRowset.Data1
    && (v30 = *(_QWORD *)a6->Data4, v29 = v30 < *(_QWORD *)IID_IRowset.Data4, v30 == *(_QWORD *)IID_IRowset.Data4) )
  {
    v31 = 0;
  }
  else
  {
    v31 = -v29 - (v29 - 1);
  }
  if ( v31 )
  {
    v32 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IColumnsInfo.Data1;
    if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IColumnsInfo.Data1
      && (v33 = *(_QWORD *)a6->Data4,
          v32 = v33 < *(_QWORD *)IID_IColumnsInfo.Data4,
          v33 == *(_QWORD *)IID_IColumnsInfo.Data4) )
    {
      v34 = 0;
    }
    else
    {
      v34 = -v32 - (v32 - 1);
    }
    if ( v34 )
    {
      v35 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IAccessor.Data1;
      if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IAccessor.Data1
        && (v36 = *(_QWORD *)a6->Data4, v35 = v36 < *(_QWORD *)IID_IAccessor.Data4,
                                        v36 == *(_QWORD *)IID_IAccessor.Data4) )
      {
        v37 = 0;
      }
      else
      {
        v37 = -v35 - (v35 - 1);
      }
      if ( v37 )
      {
        v38 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IRowsetInfo.Data1;
        if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IRowsetInfo.Data1
          && (v39 = *(_QWORD *)a6->Data4,
              v38 = v39 < *(_QWORD *)IID_IRowsetInfo.Data4,
              v39 == *(_QWORD *)IID_IRowsetInfo.Data4) )
        {
          v40 = 0;
        }
        else
        {
          v40 = -v38 - (v38 - 1);
        }
        if ( v40 )
        {
          v41 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IUnknown.Data1;
          if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IUnknown.Data1
            && (v42 = *(_QWORD *)a6->Data4,
                v41 = v42 < *(_QWORD *)IID_IUnknown.Data4,
                v42 == *(_QWORD *)IID_IUnknown.Data4) )
          {
            v43 = 0;
          }
          else
          {
            v43 = -v41 - (v41 - 1);
          }
          if ( v43 )
          {
            v44 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IMultipleResults.Data1;
            if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IMultipleResults.Data1
              && (v45 = *(_QWORD *)a6->Data4,
                  v44 = v45 < *(_QWORD *)IID_IMultipleResults.Data4,
                  v45 == *(_QWORD *)IID_IMultipleResults.Data4) )
            {
              v46 = 0;
            }
            else
            {
              v46 = -v44 - (v44 - 1);
            }
            if ( v46 )
            {
              v47 = CSchema::SetFirehoseIIDProperty(v13, (struct CRowsetProps *)a6, (const struct _GUID *)0x383800000LL);
              v16 = v47;
              if ( v47 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_152;
                v20 = 2392073;
LABEL_133:
                v21 = (unsigned int)v47;
                goto LABEL_134;
              }
              if ( v47 == 265946 )
                v12 = 265946;
            }
          }
        }
      }
    }
  }
  *((_DWORD *)v13 + 169) = 0;
  *((_DWORD *)v13 + 170) = 1;
  CRowsetProps::CalculateSupport(v13, 0);
  v16 = CRowsetProps::SetPropertiesInError(v13);
  if ( *((_WORD *)v13 + 6 * *((int *)v13 + 169) + 301) )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    {
      LODWORD(v53) = 2133;
      bidTraceW(off_383B433A0[0], 2184233, off_383B49128[0], 2147749409LL);
    }
    v16 = -2147217887;
  }
  if ( a4 && (v16 == 265946 || v16 == -2147217887) && (CUtlProps2::SetPropertyStatus(v13, a4, a5), v16 == 265946) )
  {
    v12 = 265946;
  }
  else if ( v16 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
      {
        LODWORD(v53) = 2355;
        bidTraceW(off_383B43338[0], 2411561, off_383B49128[0], (unsigned int)v16);
      }
      goto LABEL_135;
    }
    goto LABEL_152;
  }
  CRowsetProps::SetStmtOptions(v13, this[151]);
  v16 = CStmt::HandleFirehoseModeAtExecute(this[151], &IID_IDBSchemaRowset, 0, 1);
  if ( v16 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B43338[0], 2418729, off_383B49128[0], (unsigned int)v16);
LABEL_153:
    if ( v13 )
      (*(void (__fastcall **)(CRowsetProps *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 1);
    if ( v55 )
      (*(void (__fastcall **)(CRowset *))(*(_QWORD *)v55 + 16LL))(v55);
    return (unsigned int)v16;
  }
  v16 = (*((__int64 (__fastcall **)(struct CBaseObj **))*this + 6))(this);
  if ( v16 < 0 )
  {
    CStmt::SQLFreeStmt(this[151], 0, 0);
    goto LABEL_135;
  }
  v48 = (CRowset *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 832);
  v49 = v48;
  v55 = v48;
  v57 = (__int64)v48;
  if ( v48 )
  {
    CRowset::CRowset(v48, a7, -1);
    *(_QWORD *)v49 = &CTableStatRowset::`vftable';
  }
  else
  {
    v49 = 0;
    v55 = 0;
  }
  if ( !v49 )
  {
    CStmt::SQLFreeStmt(this[151], 0, 0);
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
    {
      LODWORD(v53) = 2376;
      bidTraceW(off_383B43338[0], 2433065, off_383B49128[0], 2147942414LL);
      v16 = -2147024882;
      goto LABEL_135;
    }
    goto LABEL_58;
  }
  (*(void (__fastcall **)(CRowset *))(*(_QWORD *)v49 + 8LL))(v49);
  (*(void (__fastcall **)(struct CBaseObj *))(*(_QWORD *)this[55] + 8LL))(this[55]);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this[55] + 5) + 8LL))(*((_QWORD *)this[55] + 5));
  (*((void (__fastcall **)(struct CBaseObj **))*this + 1))(this);
  v16 = CRowset::FInit(v49, v13, 0, this[151], this[55], this[55], (struct CCommand *)this, 0, 0);
  if ( v16 < 0 )
  {
    v13 = 0;
    goto LABEL_135;
  }
  if ( v16 == 265946 )
  {
    v12 = 265946;
    if ( a4 )
      CUtlProps2::SetPropertyStatus(v13, a4, a5);
  }
  v13 = 0;
  v47 = (**(__int64 (__fastcall ***)(CRowset *, struct _GUID *, struct IUnknown **))v49)(v49, a6, a8);
  v16 = v47;
  if ( v47 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_152;
    v20 = 2481161;
    goto LABEL_133;
  }
  (*(void (__fastcall **)(CRowset *))(*(_QWORD *)v49 + 16LL))(v49);
  if ( !v16 )
    return v12;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x3839ffb70  mov     rax, rsp
0x3839ffb73  mov     [rax+20h], r9d
0x3839ffb77  push    rdi
0x3839ffb78  push    r12
0x3839ffb7a  push    r13
0x3839ffb7c  push    r14
0x3839ffb7e  push    r15
0x3839ffb80  sub     rsp, 70h
0x3839ffb84  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x3839ffb8c  mov     [rax+8], rbx
0x3839ffb90  mov     [rax+10h], rbp
0x3839ffb94  mov     [rax+18h], rsi
0x3839ffb98  mov     r12, r8
0x3839ffb9b  mov     ebp, edx
0x3839ffb9d  mov     r14, rcx
0x3839ffba0  xor     r15d, r15d
0x3839ffba3  mov     r13d, r15d
0x3839ffba6  mov     [rax-48h], r15
0x3839ffbaa  mov     [rsp+98h+var_40], r15
0x3839ffbaf  mov     edi, r15d
0x3839ffbb2  xor     edx, edx; unsigned __int16
0x3839ffbb4  xor     r8d, r8d; struct CRowsetProps *
0x3839ffbb7  call    ?FInit@CCommand@@QEAAJGPEAVCRowsetProps@@@Z; CCommand::FInit(ushort,CRowsetProps *)
0x3839ffbbc  mov     ebx, eax
0x3839ffbbe  test    eax, eax
0x3839ffbc0  jns     short loc_3839FFC07
0x3839ffbc2  test    byte ptr cs:_bidGblFlags, 2
0x3839ffbc9  jz      loc_383A005D3
0x3839ffbcf  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839ffbd6  mov     rdx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffbdd  test    rdx, rdx
0x3839ffbe0  jz      loc_383A004ED
0x3839ffbe6  mov     dword ptr [rsp+98h+var_78], 8B6h
0x3839ffbee  mov     r9d, eax
0x3839ffbf1  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffbf8  mov     edx, 22D829h
0x3839ffbfd  call    _bidTraceW
0x3839ffc02  jmp     loc_383A004ED
0x3839ffc07  mov     eax, cs:IID_IDBSchemaRowset.Data1
0x3839ffc0d  mov     [r14+4F0h], eax
0x3839ffc14  mov     eax, dword ptr cs:IID_IDBSchemaRowset.Data2
0x3839ffc1a  mov     [r14+4F4h], eax
0x3839ffc21  mov     eax, dword ptr cs:IID_IDBSchemaRowset.Data4
0x3839ffc27  mov     [r14+4F8h], eax
0x3839ffc2e  mov     eax, dword ptr cs:IID_IDBSchemaRowset.Data4+4
0x3839ffc34  mov     [r14+4FCh], eax
0x3839ffc3b  mov     rcx, r14; this
0x3839ffc3e  call    ?ApplyGeneralTimeout@CCommand@@QEAAXXZ; CCommand::ApplyGeneralTimeout(void)
0x3839ffc43  lea     rbx, cs:383800000h
0x3839ffc4a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x3839ffc4e  test    ebp, ebp
0x3839ffc50  jz      loc_3839FFE0C
0x3839ffc56  mov     [r14+610h], ebp
0x3839ffc5d  mov     rsi, rbp
0x3839ffc60  mov     eax, 18h
0x3839ffc65  mul     rbp
0x3839ffc68  mov     rdx, rax
0x3839ffc6b  cmovo   rdx, rcx
0x3839ffc6f  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839ffc76  mov     rax, [rcx]
0x3839ffc79  call    qword ptr [rax+70h]
0x3839ffc7c  mov     [r14+618h], rax
0x3839ffc83  test    rax, rax
0x3839ffc86  jnz     short loc_3839FFCE2
0x3839ffc88  test    byte ptr cs:_bidGblFlags, 2
0x3839ffc8f  jz      short loc_3839FFCC3
0x3839ffc91  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839ffc98  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffc9f  test    rax, rax
0x3839ffca2  jz      short loc_3839FFCC3
0x3839ffca4  mov     dword ptr [rsp+98h+var_78], 8C5h
0x3839ffcac  mov     r9d, 8007000Eh
0x3839ffcb2  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffcb9  mov     edx, 231429h
0x3839ffcbe  call    _bidTraceW
0x3839ffcc3  mov     ebx, 8007000Eh
0x3839ffcc8  test    byte ptr cs:_bidGblFlags, 2
0x3839ffccf  jz      loc_383A005D3
0x3839ffcd5  mov     edx, 231809h
0x3839ffcda  mov     r8d, ebx
0x3839ffcdd  jmp     loc_383A004E1
0x3839ffce2  test    ebp, ebp
0x3839ffce4  jz      loc_3839FFE0C
0x3839ffcea  mov     rbx, r15
0x3839ffced  nop     dword ptr [rax]
0x3839ffcf0  mov     rcx, [r14+618h]
0x3839ffcf7  add     rcx, rbx; pvarg
0x3839ffcfa  call    cs:__imp_VariantInit
0x3839ffd00  add     rbx, 18h
0x3839ffd04  dec     rsi
0x3839ffd07  jnz     short loc_3839FFCF0
0x3839ffd09  lea     rbx, cs:383800000h
0x3839ffd10  test    ebp, ebp
0x3839ffd12  jz      loc_3839FFE0C
0x3839ffd18  mov     rsi, r12
0x3839ffd1b  nop     dword ptr [rax+rax+00h]
0x3839ffd20  movzx   eax, word ptr [rsi]
0x3839ffd23  cmp     eax, 17h; switch 24 cases
0x3839ffd26  ja      def_3839FFD3E; jumptable 00000003839FFD3E default case, cases 4-7,9,10,12-15,20,21
0x3839ffd2c  movzx   eax, ds:(byte_383A00644 - 383800000h)[rbx+rax]
0x3839ffd34  mov     ecx, ds:(jpt_3839FFD3E - 383800000h)[rbx+rax*4]
0x3839ffd3b  add     rcx, rbx
0x3839ffd3e  jmp     rcx; switch jump
0x3839ffd40  mov     eax, r15d; jumptable 00000003839FFD3E cases 0-3,8,11,16-19,22,23
0x3839ffd43  lea     rcx, [rax+rax*2]
0x3839ffd47  lea     rdx, [r12+rcx*8]; pvargSrc
0x3839ffd4b  mov     rax, [r14+618h]
0x3839ffd52  lea     rcx, [rax+rcx*8]; pvargDest
0x3839ffd56  call    cs:__imp_VariantCopy
0x3839ffd5c  mov     ebx, eax
0x3839ffd5e  test    eax, eax
0x3839ffd60  js      short loc_3839FFD7D
0x3839ffd62  inc     r15d
0x3839ffd65  add     rsi, 18h
0x3839ffd69  cmp     r15d, ebp
0x3839ffd6c  lea     rbx, cs:383800000h
0x3839ffd73  jb      short loc_3839FFD20
0x3839ffd75  xor     r15d, r15d
0x3839ffd78  jmp     loc_3839FFE0C
0x3839ffd7d  test    byte ptr cs:_bidGblFlags, 2
0x3839ffd84  jz      loc_383A005D3
0x3839ffd8a  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839ffd91  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffd98  test    rax, rax
0x3839ffd9b  jz      loc_383A004ED
0x3839ffda1  mov     dword ptr [rsp+98h+var_78], 8DFh
0x3839ffda9  mov     r9d, ebx
0x3839ffdac  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffdb3  mov     edx, 237C29h
0x3839ffdb8  call    _bidTraceW
0x3839ffdbd  jmp     loc_383A004ED
0x3839ffdc2  mov     ebx, 80070057h; jumptable 00000003839FFD3E default case, cases 4-7,9,10,12-15,20,21
0x3839ffdc7  test    byte ptr cs:_bidGblFlags, 2
0x3839ffdce  jz      loc_383A005D3
0x3839ffdd4  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839ffddb  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffde2  test    rax, rax
0x3839ffde5  jz      loc_383A004ED
0x3839ffdeb  mov     dword ptr [rsp+98h+var_78], 8E3h
0x3839ffdf3  mov     r9d, ebx
0x3839ffdf6  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffdfd  mov     edx, 238C29h
0x3839ffe02  call    _bidTraceW
0x3839ffe07  jmp     loc_383A004ED
0x3839ffe0c  mov     esi, 40EDAh
0x3839ffe11  mov     r12, [rsp+98h+arg_20]
0x3839ffe19  mov     ebp, [rsp+98h+arg_18]
0x3839ffe20  test    ebp, ebp
0x3839ffe22  jz      loc_3839FFF62
0x3839ffe28  mov     rax, [r14]
0x3839ffe2b  lea     r8, [rsp+98h+var_48]
0x3839ffe30  lea     rdx, IID_ICommandProperties
0x3839ffe37  mov     rcx, r14
0x3839ffe3a  call    qword ptr [rax]
0x3839ffe3c  mov     ebx, eax
0x3839ffe3e  test    eax, eax
0x3839ffe40  jns     short loc_3839FFE87
0x3839ffe42  test    byte ptr cs:_bidGblFlags, 2
0x3839ffe49  jz      loc_383A005D3
0x3839ffe4f  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839ffe56  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffe5d  test    rax, rax
0x3839ffe60  jz      loc_383A004ED
0x3839ffe66  mov     dword ptr [rsp+98h+var_78], 8EDh
0x3839ffe6e  mov     r9d, ebx
0x3839ffe71  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839ffe78  mov     edx, 23B429h
0x3839ffe7d  call    _bidTraceW
0x3839ffe82  jmp     loc_383A004ED
0x3839ffe87  mov     rcx, [rsp+98h+var_48]
0x3839ffe8c  mov     rax, [rcx]
0x3839ffe8f  mov     r8, r12
0x3839ffe92  mov     edx, ebp
0x3839ffe94  call    qword ptr [rax+20h]
0x3839ffe97  mov     ebx, eax
0x3839ffe99  mov     rcx, [rsp+98h+var_48]
0x3839ffe9e  mov     rax, [rcx]
0x3839ffea1  call    qword ptr [rax+10h]
0x3839ffea4  cmp     ebx, 80040E21h
0x3839ffeaa  jz      short loc_3839FFED2
0x3839ffeac  cmp     ebx, esi
0x3839ffeae  jz      short loc_3839FFED2
0x3839ffeb0  test    ebx, ebx
0x3839ffeb2  jns     loc_3839FFF62
0x3839ffeb8  test    byte ptr cs:_bidGblFlags, 2
0x3839ffebf  jz      loc_383A005D3
0x3839ffec5  mov     r8d, ebx
0x3839ffec8  mov     edx, 242009h
0x3839ffecd  jmp     loc_383A004E1
0x3839ffed2  mov     r10d, r15d
0x3839ffed5  test    ebp, ebp
0x3839ffed7  jz      loc_3839FFF5F
0x3839ffedd  lea     r9, [r12+8]
0x3839ffee2  mov     ecx, r15d
0x3839ffee5  mov     edx, [r9]
0x3839ffee8  test    edx, edx
0x3839ffeea  jz      short loc_3839FFF0C
0x3839ffeec  mov     r8, [r9-8]
0x3839ffef0  mov     rax, r15
0x3839ffef3  cmp     [r8+rax+8], edi
0x3839ffef8  jz      short loc_3839FFF02
0x3839ffefa  cmp     dword ptr [r8+rax+4], 1
0x3839fff00  jnz     short loc_3839FFF1A
0x3839fff02  inc     ecx
0x3839fff04  add     rax, 48h ; 'H'
0x3839fff08  cmp     ecx, edx
0x3839fff0a  jb      short loc_3839FFEF3
0x3839fff0c  inc     r10d
0x3839fff0f  add     r9, 20h ; ' '
0x3839fff13  cmp     r10d, ebp
0x3839fff16  jnb     short loc_3839FFF5F
0x3839fff18  jmp     short loc_3839FFEE2
0x3839fff1a  test    byte ptr cs:_bidGblFlags, 2
0x3839fff21  jz      short loc_3839FFF55
0x3839fff23  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fff2a  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fff31  test    rax, rax
0x3839fff34  jz      short loc_3839FFF55
0x3839fff36  mov     dword ptr [rsp+98h+var_78], 8FFh
0x3839fff3e  mov     r9d, 80040E21h
0x3839fff44  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fff4b  mov     edx, 23FC29h
0x3839fff50  call    _bidTraceW
0x3839fff55  mov     ebx, 80040E21h
0x3839fff5a  jmp     loc_383A004ED
0x3839fff5f  mov     r13d, esi
0x3839fff62  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839fff69  mov     rax, [rcx]
0x3839fff6c  mov     edx, 2B0h
0x3839fff71  call    qword ptr [rax+58h]
0x3839fff74  mov     rdi, rax
0x3839fff77  mov     [rsp+98h+var_30], rax
0x3839fff7c  test    rax, rax
0x3839fff7f  jz      short loc_3839FFFF3
0x3839fff81  mov     qword ptr [rax+0Ch], 1
0x3839fff89  mov     [rax+28h], r15d
0x3839fff8d  mov     [rax+8], r15d
0x3839fff91  mov     [rax+20h], r15
0x3839fff95  mov     [rax+30h], r15
0x3839fff99  mov     [rax+128h], r15d
0x3839fffa0  mov     [rax+230h], r15
0x3839fffa7  mov     [rax+238h], r15
0x3839fffae  mov     [rax+18h], r15
0x3839fffb2  lea     rax, ??_7CRowsetProps@@6B@; const CRowsetProps::`vftable'
0x3839fffb9  mov     [rdi], rax
0x3839fffbc  mov     [rdi+240h], r15
0x3839fffc3  mov     [rdi+248h], r15
0x3839fffca  mov     dword ptr [rdi+2A4h], 0FFFFFFFFh
0x3839fffd4  mov     qword ptr [rdi+2A8h], 0
0x3839fffdf  lea     rcx, [rdi+250h]; void *
0x3839fffe6  xor     edx, edx; Val
0x3839fffe8  lea     r8d, [rdx+54h]; Size
0x3839fffec  call    memset
0x3839ffff1  jmp     short loc_3839FFFF6
0x3839ffff3  mov     rdi, r15
0x3839ffff6  test    rdi, rdi
0x3839ffff9  jnz     short loc_383A00040
0x3839ffffb  test    byte ptr cs:_bidGblFlags, 2
0x383a00002  jz      short loc_383A00036
0x383a00004  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a0000b  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a00012  test    rax, rax
0x383a00015  jz      short loc_383A00036
0x383a00017  mov     dword ptr [rsp+98h+var_78], 910h
0x383a0001f  mov     r9d, 8007000Eh
0x383a00025  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a0002c  mov     edx, 244029h
0x383a00031  call    _bidTraceW
0x383a00036  mov     ebx, 8007000Eh
0x383a0003b  jmp     loc_383A004ED
0x383a00040  xor     r9d, r9d; unsigned __int16
0x383a00043  lea     r8, [r14+1C0h]; struct CRowsetProps *
0x383a0004a  mov     rdx, r14; struct CCommand *
0x383a0004d  mov     rcx, rdi; this
0x383a00050  call    ?FInit@CRowsetProps@@QEAAJPEAVCCommand@@PEBV1@G@Z; CRowsetProps::FInit(CCommand *,CRowsetProps const *,ushort)
0x383a00055  mov     ebx, eax
0x383a00057  test    eax, eax
0x383a00059  jns     short loc_383A000A0
0x383a0005b  test    byte ptr cs:_bidGblFlags, 2
0x383a00062  jz      loc_383A005D3
0x383a00068  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a0006f  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a00076  test    rax, rax
0x383a00079  jz      loc_383A004ED
0x383a0007f  mov     dword ptr [rsp+98h+var_78], 914h
0x383a00087  mov     r9d, ebx
0x383a0008a  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a00091  mov     edx, 245029h
0x383a00096  call    _bidTraceW
0x383a0009b  jmp     loc_383A004ED
0x383a000a0  mov     rsi, [rsp+98h+arg_28]
0x383a000a8  lea     r8, cs:383800000h; struct _GUID *
0x383a000af  mov     rdx, [rsi]
0x383a000b2  cmp     rdx, qword ptr ds:rva IID_IRowset.Data1[r8]
0x383a000b9  jnz     short loc_383A000CD
0x383a000bb  mov     rdx, [rsi+8]
0x383a000bf  cmp     rdx, qword ptr ds:rva IID_IRowset.Data4[r8]
0x383a000c6  jnz     short loc_383A000CD
0x383a000c8  mov     eax, r15d
0x383a000cb  jmp     short loc_383A000D2
  ... truncated ...
```
