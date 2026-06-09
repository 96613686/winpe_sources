# CSchema::FInit(ulong,tagVARIANT const * const,ulong,tagDBPROPSET * const,_GUID const &,IUnknown *,IUnknown * *)

- ea: `0x3839fc100`
- end: `0x3839fcb34`
- name: `?FInit@CSchema@@UEAAJKQEBUtagVARIANT@@KQEAUtagDBPROPSET@@AEBU_GUID@@PEAUIUnknown@@PEAPEAU5@@Z`
- size: `2612`
- prototype: `__int64 __usercall@<rax>(CSchema *__hidden this@<rcx>, unsigned int@<edx>, const struct tagVARIANT *const@<r8>, unsigned int@<r9d>, struct tagDBPROPSET *const, const struct _GUID *, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x3838435e0`
- `0x383849aa0`
- `0x383849f80`
- `0x38384c670`
- `0x38384d2c0`
- `0x38384d9c0`
- `0x383850fd0`
- `0x3838588d0`
- `0x383858c30`
- `0x38391aed0`
- `0x38391afe0`
- `0x3839bd770`
- `0x3839fbf00`
- `0x3839fc100`
- `0x383a02c50`
- `0x383a42930`
- `0x383a9a318`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x3839fc28a`
- `OLEAUT32!__imp_VariantInit` at `0x3839fc28a`
- `OLEAUT32!__imp_VariantCopy` at `0x3839fc2ee`
- `OLEAUT32!__imp_VariantCopy` at `0x3839fc2ee`
- `OLEAUT32!__imp_SetErrorInfo` at `0x3839fc475`
- `OLEAUT32!__imp_SetErrorInfo` at `0x3839fc475`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSchema::FInit(
        struct CBaseObj **this,
        unsigned int a2,
        const struct tagVARIANT *const a3,
        unsigned int a4,
        struct tagDBPROPSET *const a5,
        struct _GUID *a6,
        struct IUnknown *a7,
        struct IUnknown **a8)
{
  unsigned __int64 v10; // r14
  unsigned int v12; // r15d
  CRowsetProps *v13; // rdi
  int v14; // eax
  const struct _GUID *v15; // r8
  HRESULT v16; // ebx
  ULONG *p_cProperties; // r9
  unsigned __int64 v18; // rbp
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rbx
  const struct tagVARIANT *v22; // rbp
  CRowset *v23; // r14
  unsigned int v24; // r11d
  ULONG v25; // ecx
  __int64 v26; // rax
  __int64 v27; // rax
  bool v28; // cf
  unsigned __int64 v29; // rdx
  int v30; // eax
  bool v31; // cf
  unsigned __int64 v32; // rdx
  int v33; // eax
  bool v34; // cf
  unsigned __int64 v35; // rdx
  int v36; // eax
  bool v37; // cf
  unsigned __int64 v38; // rdx
  int v39; // eax
  bool v40; // cf
  unsigned __int64 v41; // rdx
  int v42; // eax
  bool v43; // cf
  unsigned __int64 v44; // rdx
  int v45; // eax
  int OnlyIIDProperty; // eax
  int CapableCC; // eax
  HRESULT v48; // eax
  CRowset *v49; // rax
  int v50; // eax
  __int64 v51; // rdx
  struct _GUID *v53; // [rsp+20h] [rbp-88h]
  int v54; // [rsp+28h] [rbp-80h]
  unsigned int v55; // [rsp+50h] [rbp-58h] BYREF
  __int64 v56; // [rsp+58h] [rbp-50h]
  __int64 v57; // [rsp+60h] [rbp-48h] BYREF
  CRowset *v58; // [rsp+68h] [rbp-40h]
  __int64 v59[2]; // [rsp+70h] [rbp-38h] BYREF

  v59[1] = -2;
  v10 = a2;
  v12 = 0;
  v55 = 0;
  v57 = 0;
  v58 = 0;
  v13 = 0;
  v59[0] = -1;
  v14 = CCommand::FInit((CCommand *)this, 1u, 0);
  v16 = v14;
  if ( v14 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
        bidTraceW(off_383B43338[0], 178217, off_383B49128[0], (unsigned int)v14);
      goto LABEL_129;
    }
    goto LABEL_136;
  }
  *((GUID *)this + 79) = IID_IDBSchemaRowset;
  CCommand::ApplyGeneralTimeout((CCommand *)this);
  if ( !(_DWORD)v10 )
    goto LABEL_25;
  *((_DWORD *)this + 388) = v10;
  v18 = v10;
  v19 = 24 * v10;
  if ( !is_mul_ok(v10, 0x18u) )
    v19 = -1;
  v20 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v19);
  this[195] = (struct CBaseObj *)v20;
  if ( !v20 )
  {
    v16 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
        bidTraceW(off_383B43338[0], 193577, off_383B49128[0], 2147942414LL);
      goto LABEL_129;
    }
    goto LABEL_136;
  }
  v21 = 0;
  do
  {
    VariantInit((VARIANTARG *)((char *)this[195] + v21));
    v21 += 24;
    --v18;
  }
  while ( v18 );
  v22 = a3;
  while ( 2 )
  {
    switch ( v22->vt )
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
        v16 = VariantCopy((VARIANTARG *)this[195] + v12, &a3[v12]);
        if ( v16 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_136;
          if ( off_383B49128[0] )
            bidTraceW(off_383B43338[0], 220201, off_383B49128[0], (unsigned int)v16);
          goto LABEL_129;
        }
        ++v12;
        ++v22;
        if ( v12 < (unsigned int)v10 )
          continue;
        v12 = 0;
LABEL_25:
        if ( !a4 )
          goto LABEL_48;
        v16 = (*(__int64 (__fastcall **)(struct CBaseObj **, GUID *, __int64 *))*this)(
                this,
                &IID_ICommandProperties,
                &v57);
        if ( v16 >= 0 )
        {
          v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct tagDBPROPSET *const))(*(_QWORD *)v57 + 32LL))(
                  v57,
                  a4,
                  a5);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
          if ( v16 == -2147217887 || v16 == 265946 )
          {
            SetErrorInfo(0, 0);
            v23 = 0;
            v24 = 0;
            p_cProperties = &a5->cProperties;
            while ( 1 )
            {
              v25 = 0;
              if ( *p_cProperties )
                break;
LABEL_41:
              ++v24;
              p_cProperties += 8;
              if ( v24 >= a4 )
              {
                v12 = 265946;
                goto LABEL_49;
              }
            }
            v15 = (const struct _GUID *)*((_QWORD *)p_cProperties - 1);
            v26 = 0;
            while ( !*(_DWORD *)&v15->Data4[v26] || *(_DWORD *)((char *)&v15->Data2 + v26) == 1 )
            {
              ++v25;
              v26 += 72;
              if ( v25 >= *p_cProperties )
                goto LABEL_41;
            }
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              bidTraceW(off_383B43338[0], 253993, off_383B49128[0], 2147749409LL);
            v16 = -2147217887;
          }
          else
          {
            if ( v16 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                bidTraceHR(off_383B43338[0], 263177, (unsigned int)v16);
                goto LABEL_129;
              }
              goto LABEL_136;
            }
LABEL_48:
            v23 = 0;
LABEL_49:
            v27 = ((__int64 (__fastcall *)(struct IMalloc *, __int64, const struct _GUID *, ULONG *))g_pMO->lpVtbl[1].Release)(
                    g_pMO,
                    688,
                    v15,
                    p_cProperties);
            v13 = (CRowsetProps *)v27;
            v56 = v27;
            if ( v27 )
            {
              *(_QWORD *)(v27 + 12) = 1;
              *(_DWORD *)(v27 + 40) = 0;
              *(_DWORD *)(v27 + 8) = 0;
              *(_QWORD *)(v27 + 32) = 0;
              *(_QWORD *)(v27 + 48) = 0;
              *(_DWORD *)(v27 + 296) = 0;
              *(_QWORD *)(v27 + 560) = 0;
              *(_QWORD *)(v27 + 568) = 0;
              *(_QWORD *)(v27 + 24) = 0;
              *(_QWORD *)v27 = &CRowsetProps::`vftable';
              *(_QWORD *)(v27 + 576) = 0;
              *(_QWORD *)(v27 + 584) = 0;
              *(_DWORD *)(v27 + 676) = -1;
              *(_QWORD *)(v27 + 680) = 0;
              memset((void *)(v27 + 592), 0, 0x54u);
            }
            else
            {
              v13 = 0;
            }
            if ( v13 )
            {
              v16 = CRowsetProps::FInit(v13, (struct CCommand *)this, (const struct CRowsetProps *)(this + 56), 1u);
              if ( v16 >= 0 )
              {
                v28 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IRowset.Data1;
                if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IRowset.Data1
                  && (v29 = *(_QWORD *)a6->Data4,
                      v28 = v29 < *(_QWORD *)IID_IRowset.Data4,
                      v29 == *(_QWORD *)IID_IRowset.Data4) )
                {
                  v30 = 0;
                }
                else
                {
                  v30 = -v28 - (v28 - 1);
                }
                if ( v30 )
                {
                  v31 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IColumnsInfo.Data1;
                  if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IColumnsInfo.Data1
                    && (v32 = *(_QWORD *)a6->Data4,
                        v31 = v32 < *(_QWORD *)IID_IColumnsInfo.Data4,
                        v32 == *(_QWORD *)IID_IColumnsInfo.Data4) )
                  {
                    v33 = 0;
                  }
                  else
                  {
                    v33 = -v31 - (v31 - 1);
                  }
                  if ( v33 )
                  {
                    v34 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IAccessor.Data1;
                    if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IAccessor.Data1
                      && (v35 = *(_QWORD *)a6->Data4,
                          v34 = v35 < *(_QWORD *)IID_IAccessor.Data4,
                          v35 == *(_QWORD *)IID_IAccessor.Data4) )
                    {
                      v36 = 0;
                    }
                    else
                    {
                      v36 = -v34 - (v34 - 1);
                    }
                    if ( v36 )
                    {
                      v37 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IRowsetInfo.Data1;
                      if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IRowsetInfo.Data1
                        && (v38 = *(_QWORD *)a6->Data4,
                            v37 = v38 < *(_QWORD *)IID_IRowsetInfo.Data4,
                            v38 == *(_QWORD *)IID_IRowsetInfo.Data4) )
                      {
                        v39 = 0;
                      }
                      else
                      {
                        v39 = -v37 - (v37 - 1);
                      }
                      if ( v39 )
                      {
                        v40 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IUnknown.Data1;
                        if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IUnknown.Data1
                          && (v41 = *(_QWORD *)a6->Data4,
                              v40 = v41 < *(_QWORD *)IID_IUnknown.Data4,
                              v41 == *(_QWORD *)IID_IUnknown.Data4) )
                        {
                          v42 = 0;
                        }
                        else
                        {
                          v42 = -v40 - (v40 - 1);
                        }
                        if ( v42 )
                        {
                          v43 = *(_QWORD *)&a6->Data1 < *(_QWORD *)&IID_IMultipleResults.Data1;
                          if ( *(_QWORD *)&a6->Data1 == *(_QWORD *)&IID_IMultipleResults.Data1
                            && (v44 = *(_QWORD *)a6->Data4,
                                v43 = v44 < *(_QWORD *)IID_IMultipleResults.Data4,
                                v44 == *(_QWORD *)IID_IMultipleResults.Data4) )
                          {
                            v45 = 0;
                          }
                          else
                          {
                            v45 = -v43 - (v43 - 1);
                          }
                          if ( v45 )
                          {
                            OnlyIIDProperty = CSchema::SetReadOnlyIIDProperty(
                                                v13,
                                                (struct CRowsetProps *)a6,
                                                (const struct _GUID *)0x383800000LL);
                            v16 = OnlyIIDProperty;
                            if ( OnlyIIDProperty < 0 )
                            {
                              if ( (bidGblFlags & 2) != 0 )
                              {
                                bidTraceHR(off_383B43338[0], 287753, (unsigned int)OnlyIIDProperty);
                                goto LABEL_129;
                              }
                              goto LABEL_136;
                            }
                          }
                        }
                      }
                    }
                  }
                }
                CapableCC = CRowsetProps::FindCapableCC(v13, this[151], &v55, a6, 0, v54);
                v16 = CapableCC;
                if ( CapableCC >= 0 )
                {
                  v16 = CStmt::HandleFirehoseModeAtExecute(this[151], &IID_IDBSchemaRowset, 0, 1);
                  if ( v16 < 0 )
                  {
                    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                      bidTraceW(off_383B43338[0], 308265, off_383B49128[0], (unsigned int)v16);
                    goto LABEL_137;
                  }
                  v16 = (*((__int64 (__fastcall **)(struct CBaseObj **))*this + 6))(this);
                  if ( v16 < 0 )
                    goto LABEL_128;
                  v48 = CRowsetProps::ReValidate(v13, this[151], &v55, 0, v53);
                  v16 = v48;
                  if ( (v48 == -2147217887 || v48 == 265946) && a4 )
                    CUtlProps2::SetPropertyStatus(v13, a4, a5);
                  if ( v16 < 0 )
                  {
LABEL_128:
                    CStmt::SQLFreeStmt(this[151], 0, 0);
                    goto LABEL_129;
                  }
                  if ( v16 == 265946 )
                    v12 = 265946;
                  CStmt::SQLCursorRowCount(this[151], v59);
                  v49 = (CRowset *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(
                                     g_pMO,
                                     832);
                  v56 = (__int64)v49;
                  if ( v49 )
                    v23 = CRowset::CRowset(v49, a7, v59[0]);
                  v58 = v23;
                  if ( v23 )
                  {
                    (*(void (__fastcall **)(CRowset *))(*(_QWORD *)v23 + 8LL))(v23);
                    (*(void (__fastcall **)(struct CBaseObj *))(*(_QWORD *)this[55] + 8LL))(this[55]);
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this[55] + 5) + 8LL))(*((_QWORD *)this[55] + 5));
                    (*((void (__fastcall **)(struct CBaseObj **))*this + 1))(this);
                    v16 = CRowset::FInit(v23, v13, v55, this[151], this[55], this[55], (struct CCommand *)this, 0, 0);
                    if ( v16 >= 0 )
                    {
                      if ( v16 == 265946 )
                      {
                        v12 = 265946;
                        if ( a4 )
                          CUtlProps2::SetPropertyStatus(v13, a4, a5);
                      }
                      v13 = 0;
                      v50 = (**(__int64 (__fastcall ***)(CRowset *, struct _GUID *, struct IUnknown **))v23)(
                              v23,
                              a6,
                              a8);
                      v16 = v50;
                      if ( v50 < 0 )
                      {
                        if ( (bidGblFlags & 2) != 0 )
                        {
                          bidTraceHR(off_383B43338[0], 392201, (unsigned int)v50);
                          goto LABEL_129;
                        }
                        goto LABEL_136;
                      }
                      (*(void (__fastcall **)(CRowset *))(*(_QWORD *)v23 + 16LL))(v23);
                      if ( !v16 )
                        return v12;
                      return (unsigned int)v16;
                    }
                    if ( a4 )
                      CUtlProps2::SetPropertyStatus(v13, a4, a5);
                    v13 = 0;
                  }
                  else
                  {
                    CStmt::SQLFreeStmt(this[151], 0, 0);
                    v16 = -2147024882;
                    if ( (bidGblFlags & 2) == 0 )
                      goto LABEL_136;
                    if ( off_383B49128[0] )
                      bidTraceW(off_383B43338[0], 338985, off_383B49128[0], 2147942414LL);
                  }
                }
                else if ( CapableCC == -2147217887 && a4 )
                {
                  CUtlProps2::SetPropertyStatus(v13, a4, a5);
                }
              }
              else
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_136;
                if ( off_383B49128[0] )
                  bidTraceW(off_383B43338[0], 275497, off_383B49128[0], (unsigned int)v16);
              }
            }
            else
            {
              v16 = -2147024882;
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_136;
              if ( off_383B49128[0] )
                bidTraceW(off_383B43338[0], 271401, off_383B49128[0], 2147942414LL);
            }
          }
LABEL_129:
          if ( (bidGblFlags & 2) != 0 )
          {
            v51 = 399369;
            if ( v16 || (bidGblFlags & 0x40) != 0 )
            {
              if ( off_383B49128[0] )
              {
                if ( v16 < 0 )
                  v51 = 399401;
                bidTraceW(off_383B43338[0], v51, off_383B49128[0], (unsigned int)v16);
              }
            }
          }
          goto LABEL_136;
        }
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_383B49128[0] )
            bidTraceW(off_383B43338[0], 234537, off_383B49128[0], (unsigned int)v16);
          goto LABEL_129;
        }
LABEL_136:
        CError::PostHResult((CError *)(unsigned int)v16, (int)&IID_IDBSchemaRowset, v15);
LABEL_137:
        if ( v13 )
          (*(void (__fastcall **)(CRowsetProps *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 1);
        if ( v58 )
          (*(void (__fastcall **)(CRowset *))(*(_QWORD *)v58 + 16LL))(v58);
        return (unsigned int)v16;
      default:
        v16 = -2147024809;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_136;
        if ( off_383B49128[0] )
          bidTraceW(off_383B43338[0], 224297, off_383B49128[0], 2147942487LL);
        goto LABEL_129;
    }
  }
}

```

## disassembly

```asm
0x3839fc100  mov     r11, rsp
0x3839fc103  push    rdi
0x3839fc104  push    r12
0x3839fc106  push    r13
0x3839fc108  push    r14
0x3839fc10a  push    r15
0x3839fc10c  sub     rsp, 80h
0x3839fc113  mov     qword ptr [r11-30h], 0FFFFFFFFFFFFFFFEh
0x3839fc11b  mov     [r11+8], rbx
0x3839fc11f  mov     [r11+10h], rbp
0x3839fc123  mov     [r11+18h], rsi
0x3839fc127  mov     r12d, r9d
0x3839fc12a  mov     r13, r8
0x3839fc12d  mov     r14d, edx
0x3839fc130  mov     rsi, rcx
0x3839fc133  xor     eax, eax
0x3839fc135  mov     r15d, eax
0x3839fc138  mov     [rsp+0A8h+var_58], eax
0x3839fc13c  mov     [r11-48h], rax
0x3839fc140  mov     [rsp+0A8h+var_40], rax
0x3839fc145  mov     edi, eax
0x3839fc147  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFFh
0x3839fc14f  lea     edx, [rax+1]; unsigned __int16
0x3839fc152  xor     r8d, r8d; struct CRowsetProps *
0x3839fc155  call    ?FInit@CCommand@@QEAAJGPEAVCRowsetProps@@@Z; CCommand::FInit(ushort,CRowsetProps *)
0x3839fc15a  mov     ebx, eax
0x3839fc15c  test    eax, eax
0x3839fc15e  jns     short loc_3839FC1A5
0x3839fc160  test    byte ptr cs:_bidGblFlags, 2
0x3839fc167  jz      loc_3839FCAC0
0x3839fc16d  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fc174  mov     rdx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc17b  test    rdx, rdx
0x3839fc17e  jz      loc_3839FCA6D
0x3839fc184  mov     dword ptr [rsp+0A8h+var_88], 0AEh
0x3839fc18c  mov     r9d, eax
0x3839fc18f  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc196  mov     edx, 2B829h
0x3839fc19b  call    _bidTraceW
0x3839fc1a0  jmp     loc_3839FCA6D
0x3839fc1a5  mov     eax, cs:IID_IDBSchemaRowset.Data1
0x3839fc1ab  mov     [rsi+4F0h], eax
0x3839fc1b1  mov     eax, dword ptr cs:IID_IDBSchemaRowset.Data2
0x3839fc1b7  mov     [rsi+4F4h], eax
0x3839fc1bd  mov     eax, dword ptr cs:IID_IDBSchemaRowset.Data4
0x3839fc1c3  mov     [rsi+4F8h], eax
0x3839fc1c9  mov     eax, dword ptr cs:IID_IDBSchemaRowset.Data4+4
0x3839fc1cf  mov     [rsi+4FCh], eax
0x3839fc1d5  mov     rcx, rsi; this
0x3839fc1d8  call    ?ApplyGeneralTimeout@CCommand@@QEAAXXZ; CCommand::ApplyGeneralTimeout(void)
0x3839fc1dd  lea     rbx, cs:383800000h
0x3839fc1e4  test    r14d, r14d
0x3839fc1e7  jz      loc_3839FC3A4
0x3839fc1ed  mov     [rsi+610h], r14d
0x3839fc1f4  mov     rbp, r14
0x3839fc1f7  mov     eax, 18h
0x3839fc1fc  mul     r14
0x3839fc1ff  mov     rdx, rax
0x3839fc202  mov     rax, 0FFFFFFFFFFFFFFFFh
0x3839fc209  cmovo   rdx, rax
0x3839fc20d  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839fc214  mov     rax, [rcx]
0x3839fc217  call    qword ptr [rax+70h]
0x3839fc21a  mov     [rsi+618h], rax
0x3839fc221  test    rax, rax
0x3839fc224  jnz     short loc_3839FC270
0x3839fc226  mov     ebx, 8007000Eh
0x3839fc22b  test    byte ptr cs:_bidGblFlags, 2
0x3839fc232  jz      loc_3839FCAC0
0x3839fc238  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fc23f  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc246  test    rax, rax
0x3839fc249  jz      loc_3839FCA6D
0x3839fc24f  mov     dword ptr [rsp+0A8h+var_88], 0BDh
0x3839fc257  mov     r9d, ebx
0x3839fc25a  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc261  mov     edx, 2F429h
0x3839fc266  call    _bidTraceW
0x3839fc26b  jmp     loc_3839FCA6D
0x3839fc270  test    r14d, r14d
0x3839fc273  jz      loc_3839FC3A1
0x3839fc279  mov     rbx, r15
0x3839fc27c  nop     dword ptr [rax+00h]
0x3839fc280  mov     rcx, [rsi+618h]
0x3839fc287  add     rcx, rbx; pvarg
0x3839fc28a  call    cs:__imp_VariantInit
0x3839fc290  add     rbx, 18h
0x3839fc294  dec     rbp
0x3839fc297  jnz     short loc_3839FC280
0x3839fc299  lea     rbx, cs:383800000h
0x3839fc2a0  test    r14d, r14d
0x3839fc2a3  jz      loc_3839FC3A1
0x3839fc2a9  mov     rbp, r13
0x3839fc2ac  nop     dword ptr [rax+00h]
0x3839fc2b0  movzx   eax, word ptr [rbp+0]
0x3839fc2b4  cmp     eax, 17h; switch 24 cases
0x3839fc2b7  ja      def_3839FC2CF; jumptable 00000003839FC2CF default case, cases 4-7,9,10,12-15,20,21
0x3839fc2bd  movzx   eax, ds:(byte_3839FCB1C - 383800000h)[rbx+rax]
0x3839fc2c5  mov     ecx, ds:(jpt_3839FC2CF - 383800000h)[rbx+rax*4]
0x3839fc2cc  add     rcx, rbx
0x3839fc2cf  jmp     rcx; switch jump
0x3839fc2d1  mov     eax, r15d; jumptable 00000003839FC2CF cases 0-3,8,11,16-19,22,23
0x3839fc2d4  lea     rcx, [rax+rax*2]
0x3839fc2d8  lea     rdx, ds:0[rcx*8]
0x3839fc2e0  add     rdx, r13; pvargSrc
0x3839fc2e3  mov     rax, [rsi+618h]
0x3839fc2ea  lea     rcx, [rax+rcx*8]; pvargDest
0x3839fc2ee  call    cs:__imp_VariantCopy
0x3839fc2f4  mov     ebx, eax
0x3839fc2f6  test    eax, eax
0x3839fc2f8  js      short loc_3839FC312
0x3839fc2fa  inc     r15d
0x3839fc2fd  add     rbp, 18h
0x3839fc301  cmp     r15d, r14d
0x3839fc304  lea     rbx, cs:383800000h
0x3839fc30b  jb      short loc_3839FC2B0
0x3839fc30d  jmp     loc_3839FC3A1
0x3839fc312  test    byte ptr cs:_bidGblFlags, 2
0x3839fc319  jz      loc_3839FCAC0
0x3839fc31f  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fc326  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc32d  test    rax, rax
0x3839fc330  jz      loc_3839FCA6D
0x3839fc336  mov     dword ptr [rsp+0A8h+var_88], 0D7h
0x3839fc33e  mov     r9d, ebx
0x3839fc341  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc348  mov     edx, 35C29h
0x3839fc34d  call    _bidTraceW
0x3839fc352  jmp     loc_3839FCA6D
0x3839fc357  mov     ebx, 80070057h; jumptable 00000003839FC2CF default case, cases 4-7,9,10,12-15,20,21
0x3839fc35c  test    byte ptr cs:_bidGblFlags, 2
0x3839fc363  jz      loc_3839FCAC0
0x3839fc369  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fc370  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc377  test    rax, rax
0x3839fc37a  jz      loc_3839FCA6D
0x3839fc380  mov     dword ptr [rsp+0A8h+var_88], 0DBh
0x3839fc388  mov     r9d, ebx
0x3839fc38b  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc392  mov     edx, 36C29h
0x3839fc397  call    _bidTraceW
0x3839fc39c  jmp     loc_3839FCA6D
0x3839fc3a1  mov     r15d, edi
0x3839fc3a4  mov     ebp, 40EDAh
0x3839fc3a9  mov     r13, [rsp+0A8h+arg_20]
0x3839fc3b1  test    r12d, r12d
0x3839fc3b4  jz      loc_3839FC512
0x3839fc3ba  mov     rax, [rsi]
0x3839fc3bd  lea     r8, [rsp+0A8h+var_48]
0x3839fc3c2  lea     rdx, IID_ICommandProperties
0x3839fc3c9  mov     rcx, rsi
0x3839fc3cc  call    qword ptr [rax]
0x3839fc3ce  mov     ebx, eax
0x3839fc3d0  test    eax, eax
0x3839fc3d2  jns     short loc_3839FC419
0x3839fc3d4  test    byte ptr cs:_bidGblFlags, 2
0x3839fc3db  jz      loc_3839FCAC0
0x3839fc3e1  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fc3e8  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc3ef  test    rax, rax
0x3839fc3f2  jz      loc_3839FCA6D
0x3839fc3f8  mov     dword ptr [rsp+0A8h+var_88], 0E5h
0x3839fc400  mov     r9d, ebx
0x3839fc403  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc40a  mov     edx, 39429h
0x3839fc40f  call    _bidTraceW
0x3839fc414  jmp     loc_3839FCA6D
0x3839fc419  mov     rcx, [rsp+0A8h+var_48]
0x3839fc41e  mov     rax, [rcx]
0x3839fc421  mov     r8, r13
0x3839fc424  mov     edx, r12d
0x3839fc427  call    qword ptr [rax+20h]
0x3839fc42a  mov     ebx, eax
0x3839fc42c  mov     rcx, [rsp+0A8h+var_48]
0x3839fc431  mov     rax, [rcx]
0x3839fc434  call    qword ptr [rax+10h]
0x3839fc437  cmp     ebx, 80040E21h
0x3839fc43d  jz      short loc_3839FC471
0x3839fc43f  cmp     ebx, ebp
0x3839fc441  jz      short loc_3839FC471
0x3839fc443  test    ebx, ebx
0x3839fc445  jns     loc_3839FC512
0x3839fc44b  test    byte ptr cs:_bidGblFlags, 2
0x3839fc452  jz      loc_3839FCAC0
0x3839fc458  mov     r8d, ebx
0x3839fc45b  mov     edx, 40409h
0x3839fc460  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fc467  call    _bidTraceHR
0x3839fc46c  jmp     loc_3839FCA6D
0x3839fc471  xor     edx, edx; perrinfo
0x3839fc473  xor     ecx, ecx; dwReserved
0x3839fc475  call    cs:__imp_SetErrorInfo
0x3839fc47b  xor     r14d, r14d
0x3839fc47e  mov     r11d, r14d
0x3839fc481  test    r12d, r12d
0x3839fc484  jz      loc_3839FC50D
0x3839fc48a  lea     r9, [r13+8]
0x3839fc48e  xchg    ax, ax
0x3839fc490  mov     ecx, r14d
0x3839fc493  mov     edx, [r9]
0x3839fc496  test    edx, edx
0x3839fc498  jz      short loc_3839FC4BA
0x3839fc49a  mov     r8, [r9-8]
0x3839fc49e  mov     rax, r14
0x3839fc4a1  cmp     [r8+rax+8], edi
0x3839fc4a6  jz      short loc_3839FC4B0
0x3839fc4a8  cmp     dword ptr [r8+rax+4], 1
0x3839fc4ae  jnz     short loc_3839FC4C8
0x3839fc4b0  inc     ecx
0x3839fc4b2  add     rax, 48h ; 'H'
0x3839fc4b6  cmp     ecx, edx
0x3839fc4b8  jb      short loc_3839FC4A1
0x3839fc4ba  inc     r11d
0x3839fc4bd  add     r9, 20h ; ' '
0x3839fc4c1  cmp     r11d, r12d
0x3839fc4c4  jnb     short loc_3839FC50D
0x3839fc4c6  jmp     short loc_3839FC490
0x3839fc4c8  test    byte ptr cs:_bidGblFlags, 2
0x3839fc4cf  jz      short loc_3839FC503
0x3839fc4d1  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fc4d8  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc4df  test    rax, rax
0x3839fc4e2  jz      short loc_3839FC503
0x3839fc4e4  mov     dword ptr [rsp+0A8h+var_88], 0F8h
0x3839fc4ec  mov     r9d, 80040E21h
0x3839fc4f2  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc4f9  mov     edx, 3E029h
0x3839fc4fe  call    _bidTraceW
0x3839fc503  mov     ebx, 80040E21h
0x3839fc508  jmp     loc_3839FCA6D
0x3839fc50d  mov     r15d, ebp
0x3839fc510  jmp     short loc_3839FC515
0x3839fc512  xor     r14d, r14d
0x3839fc515  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839fc51c  mov     rax, [rcx]
0x3839fc51f  mov     edx, 2B0h
0x3839fc524  call    qword ptr [rax+58h]
0x3839fc527  mov     rdi, rax
0x3839fc52a  mov     [rsp+0A8h+var_50], rax
0x3839fc52f  test    rax, rax
0x3839fc532  jz      short loc_3839FC5A6
0x3839fc534  mov     qword ptr [rax+0Ch], 1
0x3839fc53c  mov     [rax+28h], r14d
0x3839fc540  mov     [rax+8], r14d
0x3839fc544  mov     [rax+20h], r14
0x3839fc548  mov     [rax+30h], r14
0x3839fc54c  mov     [rax+128h], r14d
0x3839fc553  mov     [rax+230h], r14
0x3839fc55a  mov     [rax+238h], r14
0x3839fc561  mov     [rax+18h], r14
0x3839fc565  lea     rax, ??_7CRowsetProps@@6B@; const CRowsetProps::`vftable'
0x3839fc56c  mov     [rdi], rax
0x3839fc56f  mov     [rdi+240h], r14
0x3839fc576  mov     [rdi+248h], r14
0x3839fc57d  or      rax, 0FFFFFFFFFFFFFFFFh
0x3839fc581  mov     [rdi+2A4h], eax
0x3839fc587  mov     qword ptr [rdi+2A8h], 0
0x3839fc592  lea     rcx, [rdi+250h]; void *
0x3839fc599  xor     edx, edx; Val
0x3839fc59b  lea     r8d, [rax+55h]; Size
0x3839fc59f  call    memset
0x3839fc5a4  jmp     short loc_3839FC5A9
0x3839fc5a6  mov     rdi, r14
0x3839fc5a9  test    rdi, rdi
0x3839fc5ac  jnz     short loc_3839FC5F8
0x3839fc5ae  mov     ebx, 8007000Eh
0x3839fc5b3  test    byte ptr cs:_bidGblFlags, 2
0x3839fc5ba  jz      loc_3839FCAC0
0x3839fc5c0  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fc5c7  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc5ce  test    rax, rax
0x3839fc5d1  jz      loc_3839FCA6D
0x3839fc5d7  mov     dword ptr [rsp+0A8h+var_88], 109h
0x3839fc5df  mov     r9d, ebx
0x3839fc5e2  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc5e9  mov     edx, 42429h
0x3839fc5ee  call    _bidTraceW
0x3839fc5f3  jmp     loc_3839FCA6D
0x3839fc5f8  mov     r9d, 1; unsigned __int16
0x3839fc5fe  lea     r8, [rsi+1C0h]; struct CRowsetProps *
0x3839fc605  mov     rdx, rsi; struct CCommand *
0x3839fc608  mov     rcx, rdi; this
0x3839fc60b  call    ?FInit@CRowsetProps@@QEAAJPEAVCCommand@@PEBV1@G@Z; CRowsetProps::FInit(CCommand *,CRowsetProps const *,ushort)
0x3839fc610  mov     ebx, eax
0x3839fc612  test    eax, eax
0x3839fc614  jns     short loc_3839FC65B
0x3839fc616  test    byte ptr cs:_bidGblFlags, 2
0x3839fc61d  jz      loc_3839FCAC0
0x3839fc623  mov     rcx, cs:off_383B43338; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fc62a  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc631  test    rax, rax
0x3839fc634  jz      loc_3839FCA6D
0x3839fc63a  mov     dword ptr [rsp+0A8h+var_88], 10Dh
0x3839fc642  mov     r9d, ebx
0x3839fc645  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fc64c  mov     edx, 43429h
0x3839fc651  call    _bidTraceW
0x3839fc656  jmp     loc_3839FCA6D
0x3839fc65b  mov     rbp, [rsp+0A8h+arg_28]
0x3839fc663  lea     r8, cs:383800000h; struct _GUID *
  ... truncated ...
```
