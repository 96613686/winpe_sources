# CWiaItem::CopyFlagPropertyFrom(CWiaItem *,tagSTATPROPSTG &,ulong,ulong,ulong,ulong)

- ea: `0x18005f520`
- end: `0x18005fa67`
- name: `?CopyFlagPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@KKKK@Z`
- size: `1351`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, struct CWiaItem *, struct tagSTATPROPSTG *, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180019eac`
- `0x180063688`
- `0x180064a6c`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x18005f520`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18005f7d1`
- `ole32!PropVariantClear` at `0x18005fa3b`
- `ole32!PropVariantClear` at `0x18005f7d1`
- `ole32!PropVariantClear` at `0x18005fa3b`

## string_xrefs

- `0x18005f66e`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)`
- `0x18005f69b`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)`
- `0x18005f809`: `Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f832`: `Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f8ca`: `Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f8f3`: `Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f710`: `Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f739`: `Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f776`: `Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f79f`: `Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f92a`: `Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f953`: `Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f9e0`: `Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005fa09`: `Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f53f`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f5d5`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f605`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f680`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f6b8`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f722`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f788`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f7b9`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f81b`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f8dc`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f93c`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005f9f2`: `CWiaItem::CopyFlagPropertyFrom`
- `0x18005fa23`: `CWiaItem::CopyFlagPropertyFrom`

## pseudocode

```c
__int64 __fastcall CWiaItem::CopyFlagPropertyFrom(
        CWiaItem *this,
        struct CWiaItem *a2,
        struct tagSTATPROPSTG *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7)
{
  int v11; // edi
  struct tagWiaTraceData_Type *v12; // rax
  char *v13; // rdx
  unsigned int v14; // r8d
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // esi
  char *v21; // rbx
  void *v22; // rdx
  void **v23; // rax
  void *v24; // rdx
  __int64 v25; // rcx
  LPOLESTR lpwstrName; // rax
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  char *v32; // rbx
  void *v33; // rdx
  void **v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  char *v37; // rbx
  void *v38; // rdx
  char *v39; // rbx
  void *v40; // rdx
  void **v41; // rax
  void *v42; // rdx
  __int64 v43; // rcx
  bool v44; // zf
  _DWORD *v45; // rax
  unsigned int v46; // ecx
  int v47; // ebx
  char *v48; // rbx
  void *v49; // rdx
  char *v50; // rbx
  void *v51; // rdx
  _DWORD *v52; // rcx
  int v53; // eax
  char *v54; // rbx
  void *v55; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-81h]
  int v58; // [rsp+30h] [rbp-71h] BYREF
  __int64 v59; // [rsp+38h] [rbp-69h]
  PROPVARIANT pvar[4]; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v61[128]; // [rsp+60h] [rbp-41h] BYREF
  LPOLESTR v62; // [rsp+F8h] [rbp+57h] BYREF
  int v63; // [rsp+108h] [rbp+67h] BYREF

  v11 = 0;
  v12 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::CopyFlagPropertyFrom");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v61, v13, v14, "CWiaItem::CopyFlagPropertyFrom", lpMem, v12);
  if ( !a2 )
  {
    v11 = -2147467261;
    v15 = (char *)WiaTrace_TraceLog("NULL source (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyFlagPropertyFrom", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v17 = (void **)WiaTrace_Trace("NULL source (0x%X)", -2147467261);
    WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"CWiaItem::CopyFlagPropertyFrom", 1, v17);
  }
  v20 = a5;
  if ( (a4 & a5) == 0 )
  {
    v11 = -2147024809;
    v21 = (char *)WiaTrace_TraceLog("invalid backup value parameter (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyFlagPropertyFrom", v21);
    WiaTrcLib::Free((WiaTrcLib *)v21, v22);
    v23 = (void **)WiaTrace_Trace("invalid backup value parameter (0x%X)", -2147024809);
    WiaTrace_ProcessTrace_Ex(v25, v24, (void *)"CWiaItem::CopyFlagPropertyFrom", 1, v23);
  }
  v58 = 1;
  v59 = 0;
  LODWORD(v59) = a3->propid;
  v63 = v59;
  lpwstrName = a3->lpwstrName;
  v62 = a3->lpwstrName;
  if ( v11 >= 0 )
  {
    if ( lpwstrName )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, LPOLESTR *))(***((_QWORD ***)this + 27) + 56LL))(
              **((_QWORD **)this + 27),
              1,
              &v63,
              &v62);
      if ( v11 < 0 )
      {
        v27 = (char *)WiaTrace_TraceLog("Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::CopyFlagPropertyFrom", v27);
        WiaTrcLib::Free((WiaTrcLib *)v27, v28);
        v29 = (void **)WiaTrace_Trace(
                         "Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)",
                         a3->propid,
                         v11);
        WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaItem::CopyFlagPropertyFrom", 1, v29);
      }
    }
  }
  memset(pvar, 0, 24);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *))(**(_QWORD **)(*((_QWORD *)a2 + 27) + 16LL)
                                                                           + 24LL))(
            *(_QWORD *)(*((_QWORD *)a2 + 27) + 16LL),
            1,
            &v58,
            pvar);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *, int))(**(_QWORD **)(*((_QWORD *)this + 27)
                                                                                                + 16LL)
                                                                                  + 32LL))(
              *(_QWORD *)(*((_QWORD *)this + 27) + 16LL),
              1,
              &v58,
              pvar,
              2);
      if ( v11 >= 0 )
        goto LABEL_15;
      v37 = (char *)WiaTrace_TraceLog("Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyFlagPropertyFrom", v37);
      WiaTrcLib::Free((WiaTrcLib *)v37, v38);
      v34 = (void **)WiaTrace_Trace(
                       "Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v59,
                       (unsigned int)v11);
    }
    else
    {
      v32 = (char *)WiaTrace_TraceLog("Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyFlagPropertyFrom", v32);
      WiaTrcLib::Free((WiaTrcLib *)v32, v33);
      v34 = (void **)WiaTrace_Trace(
                       "Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v59,
                       (unsigned int)v11);
    }
    WiaTrace_ProcessTrace_Ex(v36, v35, (void *)"CWiaItem::CopyFlagPropertyFrom", 1, v34);
  }
LABEL_15:
  if ( LOWORD(pvar[0]) )
    PropVariantClear(pvar);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *))(***((_QWORD ***)a2 + 27) + 24LL))(
            **((_QWORD **)a2 + 27),
            1,
            &v58,
            pvar);
    if ( v11 < 0 )
    {
      v39 = (char *)WiaTrace_TraceLog("Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyFlagPropertyFrom", v39);
      WiaTrcLib::Free((WiaTrcLib *)v39, v40);
      v41 = (void **)WiaTrace_Trace(
                       "Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v59,
                       (unsigned int)v11);
LABEL_48:
      WiaTrace_ProcessTrace_Ex(v43, v42, (void *)"CWiaItem::CopyFlagPropertyFrom", 1, v41);
      goto LABEL_49;
    }
    if ( ((__int64)pvar[0] & 0x1000) != 0 )
    {
      if ( ((__int64)pvar[0] & 0x13) != 0 || (v47 = v20, ((__int64)pvar[0] & 3) != 0) )
      {
        v44 = (a4 & *(_DWORD *)pvar[2]) == 0;
        *(_DWORD *)pvar[2] &= a4;
        v45 = pvar[2];
        v46 = *(_DWORD *)pvar[2];
        if ( v44 )
        {
          *(_DWORD *)pvar[2] = v20;
          v46 = v20;
          v45 = pvar[2];
        }
        v47 = a7;
        if ( a7 )
          *v45 = a7;
        else
          v47 = v46;
      }
    }
    else
    {
      v44 = (a4 & (__int64)pvar[1]) == 0;
      v47 = a4 & (__int64)pvar[1];
      LODWORD(pvar[1]) &= a4;
      if ( v44 )
      {
        v47 = v20;
        LODWORD(pvar[1]) = v20;
      }
      if ( a7 )
      {
        v47 = a7;
        LODWORD(pvar[1]) = a7;
      }
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *, int))(***((_QWORD ***)this + 27) + 32LL))(
            **((_QWORD **)this + 27),
            1,
            &v58,
            pvar,
            2);
    if ( v11 < 0 )
    {
      v48 = (char *)WiaTrace_TraceLog("Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyFlagPropertyFrom", v48);
      WiaTrcLib::Free((WiaTrcLib *)v48, v49);
      v41 = (void **)WiaTrace_Trace(
                       "Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v59,
                       (unsigned int)v11);
      goto LABEL_48;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *))(**(_QWORD **)(*((_QWORD *)a2 + 27) + 8LL)
                                                                           + 24LL))(
            *(_QWORD *)(*((_QWORD *)a2 + 27) + 8LL),
            1,
            &v58,
            pvar);
    if ( v11 < 0 )
    {
      v50 = (char *)WiaTrace_TraceLog("Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyFlagPropertyFrom", v50);
      WiaTrcLib::Free((WiaTrcLib *)v50, v51);
      v41 = (void **)WiaTrace_Trace(
                       "Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v59,
                       (unsigned int)v11);
      goto LABEL_48;
    }
    if ( ((__int64)pvar[0] & 0x1000) != 0 )
    {
      if ( ((__int64)pvar[0] & 0x13) != 0 || ((__int64)pvar[0] & 3) != 0 )
      {
        *((_DWORD *)pvar[2] + 1) &= a4;
        v52 = pvar[2];
        if ( !*((_DWORD *)pvar[2] + 1) )
        {
          *((_DWORD *)pvar[2] + 1) = v20;
          v52 = pvar[2];
        }
        v52[1] |= a6;
        *((_DWORD *)pvar[2] + 1) |= v47;
      }
    }
    else
    {
      v53 = a4 & (__int64)pvar[1];
      if ( (a4 & (__int64)pvar[1]) == 0 )
        v53 = v20;
      LODWORD(pvar[1]) = a6 | v47 | v53;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *, int))(**(_QWORD **)(*((_QWORD *)this + 27)
                                                                                              + 8LL)
                                                                                + 32LL))(
            *(_QWORD *)(*((_QWORD *)this + 27) + 8LL),
            1,
            &v58,
            pvar,
            2);
    if ( v11 < 0 )
    {
      v54 = (char *)WiaTrace_TraceLog("Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyFlagPropertyFrom", v54);
      WiaTrcLib::Free((WiaTrcLib *)v54, v55);
      v41 = (void **)WiaTrace_Trace(
                       "Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v59,
                       (unsigned int)v11);
      goto LABEL_48;
    }
  }
LABEL_49:
  if ( LOWORD(pvar[0]) )
    PropVariantClear(pvar);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v61);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005f520  mov     [rsp-8+arg_0], rbx
0x18005f525  push    rbp
0x18005f526  push    rsi
0x18005f527  push    rdi
0x18005f528  push    r12
0x18005f52a  push    r13
0x18005f52c  push    r14
0x18005f52e  push    r15
0x18005f530  lea     rbp, [rsp-0Fh]
0x18005f535  sub     rsp, 0B0h
0x18005f53c  mov     r12, rcx
0x18005f53f  lea     rsi, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f546  mov     rcx, rsi
0x18005f549  mov     r14d, r9d
0x18005f54c  mov     r15, r8
0x18005f54f  mov     r13, rdx
0x18005f552  xor     edi, edi
0x18005f554  call    WiaTrace_Trace
0x18005f559  mov     r9, rsi; char *
0x18005f55c  mov     [rsp+0E0h+var_B8], rax; struct tagWiaTraceData_Type *
0x18005f561  lea     rcx, [rbp+3Fh+var_80]; this
0x18005f565  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18005f56a  test    r13, r13
0x18005f56d  jnz     short loc_18005F5B7
0x18005f56f  mov     edi, 80004003h
0x18005f574  lea     rcx, aNullSource0xX; "NULL source (0x%X)"
0x18005f57b  mov     edx, edi
0x18005f57d  call    WiaTrace_TraceLog
0x18005f582  mov     rdx, rax; char *
0x18005f585  mov     rcx, rsi; char *
0x18005f588  mov     rbx, rax
0x18005f58b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f590  mov     rcx, rbx; this
0x18005f593  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f598  mov     edx, edi
0x18005f59a  lea     rcx, aNullSource0xX; "NULL source (0x%X)"
0x18005f5a1  call    WiaTrace_Trace
0x18005f5a6  lea     r9d, [r13+1]; int
0x18005f5aa  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18005f5af  mov     r8, rsi; int
0x18005f5b2  call    WiaTrace_ProcessTrace_Ex
0x18005f5b7  mov     esi, [rbp+3Fh+arg_20]
0x18005f5ba  test    esi, r14d
0x18005f5bd  jnz     short loc_18005F611
0x18005f5bf  mov     edi, 80070057h
0x18005f5c4  lea     rcx, aInvalidBackupV; "invalid backup value parameter (0x%X)"
0x18005f5cb  mov     edx, edi
0x18005f5cd  call    WiaTrace_TraceLog
0x18005f5d2  mov     rdx, rax; char *
0x18005f5d5  lea     rcx, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f5dc  mov     rbx, rax
0x18005f5df  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f5e4  mov     rcx, rbx; this
0x18005f5e7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f5ec  mov     edx, edi
0x18005f5ee  lea     rcx, aInvalidBackupV; "invalid backup value parameter (0x%X)"
0x18005f5f5  call    WiaTrace_Trace
0x18005f5fa  mov     r9d, 1; int
0x18005f600  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18005f605  lea     r8, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f60c  call    WiaTrace_ProcessTrace_Ex
0x18005f611  xor     eax, eax
0x18005f613  mov     [rbp+3Fh+var_B0], 1
0x18005f61a  mov     [rbp+3Fh+var_A8], rax
0x18005f61e  mov     eax, [r15+8]
0x18005f622  mov     dword ptr [rbp+3Fh+var_A8], eax
0x18005f625  mov     [rbp+3Fh+arg_18], eax
0x18005f628  mov     rax, [r15]
0x18005f62b  mov     [rbp+3Fh+arg_8], rax
0x18005f62f  test    edi, edi
0x18005f631  js      loc_18005F6C6
0x18005f637  test    rax, rax
0x18005f63a  jz      loc_18005F6C6
0x18005f640  mov     rax, [r12+0D8h]
0x18005f648  lea     r9, [rbp+3Fh+arg_8]
0x18005f64c  lea     r8, [rbp+3Fh+arg_18]
0x18005f650  mov     edx, 1
0x18005f655  mov     rcx, [rax]
0x18005f658  mov     rax, [rcx]
0x18005f65b  mov     rax, [rax+38h]
0x18005f65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f664  mov     edi, eax
0x18005f666  test    eax, eax
0x18005f668  jns     short loc_18005F6C6
0x18005f66a  mov     edx, [r15+8]
0x18005f66e  lea     rcx, aCallToIwiaprop_0; "Call to IWiaPropertyStorage::WritePrope"...
0x18005f675  mov     r8d, eax
0x18005f678  call    WiaTrace_TraceLog
0x18005f67d  mov     rdx, rax; char *
0x18005f680  lea     rcx, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f687  mov     rbx, rax
0x18005f68a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f68f  mov     rcx, rbx; this
0x18005f692  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f697  mov     edx, [r15+8]
0x18005f69b  lea     rcx, aCallToIwiaprop_0; "Call to IWiaPropertyStorage::WritePrope"...
0x18005f6a2  mov     r8d, edi
0x18005f6a5  call    WiaTrace_Trace
0x18005f6aa  mov     r15d, 1
0x18005f6b0  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18005f6b5  mov     r9d, r15d; int
0x18005f6b8  lea     r8, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f6bf  call    WiaTrace_ProcessTrace_Ex
0x18005f6c4  jmp     short loc_18005F6CC
0x18005f6c6  mov     r15d, 1
0x18005f6cc  xor     eax, eax
0x18005f6ce  xorps   xmm0, xmm0
0x18005f6d1  mov     word ptr [rbp+3Fh+pvar], ax
0x18005f6d5  movups  xmmword ptr [rbp+3Fh+pvar+2], xmm0
0x18005f6d9  mov     [rbp-51h], rax
0x18005f6dd  test    edi, edi
0x18005f6df  js      loc_18005F7C5
0x18005f6e5  mov     rax, [r13+0D8h]
0x18005f6ec  lea     r9, [rbp+3Fh+pvar]
0x18005f6f0  lea     r8, [rbp+3Fh+var_B0]
0x18005f6f4  mov     edx, r15d
0x18005f6f7  mov     rcx, [rax+10h]
0x18005f6fb  mov     rax, [rcx]
0x18005f6fe  mov     rax, [rax+18h]
0x18005f702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f707  mov     edi, eax
0x18005f709  test    eax, eax
0x18005f70b  jns     short loc_18005F742
0x18005f70d  mov     edx, dword ptr [rbp+3Fh+var_A8]
0x18005f710  lea     rcx, aCallToAccessst; "Call to AccessStg#IPropertyStorage::Rea"...
0x18005f717  mov     r8d, eax
0x18005f71a  call    WiaTrace_TraceLog
0x18005f71f  mov     rdx, rax; char *
0x18005f722  lea     rcx, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f729  mov     rbx, rax
0x18005f72c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f731  mov     rcx, rbx; this
0x18005f734  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f739  lea     rcx, aCallToAccessst; "Call to AccessStg#IPropertyStorage::Rea"...
0x18005f740  jmp     short loc_18005F7A6
0x18005f742  mov     rax, [r12+0D8h]
0x18005f74a  lea     r9, [rbp+3Fh+pvar]
0x18005f74e  lea     r8, [rbp+3Fh+var_B0]
0x18005f752  mov     dword ptr [rsp+0E0h+lpMem], 2
0x18005f75a  mov     edx, r15d
0x18005f75d  mov     rcx, [rax+10h]
0x18005f761  mov     rax, [rcx]
0x18005f764  mov     rax, [rax+20h]
0x18005f768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f76d  mov     edi, eax
0x18005f76f  test    eax, eax
0x18005f771  jns     short loc_18005F7C5
0x18005f773  mov     edx, dword ptr [rbp+3Fh+var_A8]
0x18005f776  lea     rcx, aCallToAccessst_0; "Call to AccessStg#IPropertyStorage::Wri"...
0x18005f77d  mov     r8d, eax
0x18005f780  call    WiaTrace_TraceLog
0x18005f785  mov     rdx, rax; char *
0x18005f788  lea     rcx, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f78f  mov     rbx, rax
0x18005f792  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f797  mov     rcx, rbx; this
0x18005f79a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f79f  lea     rcx, aCallToAccessst_0; "Call to AccessStg#IPropertyStorage::Wri"...
0x18005f7a6  mov     edx, dword ptr [rbp+3Fh+var_A8]
0x18005f7a9  mov     r8d, edi
0x18005f7ac  call    WiaTrace_Trace
0x18005f7b1  mov     r9d, r15d; int
0x18005f7b4  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18005f7b9  lea     r8, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f7c0  call    WiaTrace_ProcessTrace_Ex
0x18005f7c5  xor     eax, eax
0x18005f7c7  cmp     ax, word ptr [rbp+3Fh+pvar]
0x18005f7cb  jz      short loc_18005F7D7
0x18005f7cd  lea     rcx, [rbp+3Fh+pvar]; pvar
0x18005f7d1  call    cs:__imp_PropVariantClear
0x18005f7d7  test    edi, edi
0x18005f7d9  js      loc_18005FA2F
0x18005f7df  mov     rax, [r13+0D8h]
0x18005f7e6  lea     r9, [rbp+3Fh+pvar]
0x18005f7ea  lea     r8, [rbp+3Fh+var_B0]
0x18005f7ee  mov     edx, r15d
0x18005f7f1  mov     rcx, [rax]
0x18005f7f4  mov     rax, [rcx]
0x18005f7f7  mov     rax, [rax+18h]
0x18005f7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f800  mov     edi, eax
0x18005f802  test    eax, eax
0x18005f804  jns     short loc_18005F83E
0x18005f806  mov     edx, dword ptr [rbp+3Fh+var_A8]
0x18005f809  lea     rcx, aCallToCurstgIp_0; "Call to CurStg#IPropertyStorage::ReadMu"...
0x18005f810  mov     r8d, eax
0x18005f813  call    WiaTrace_TraceLog
0x18005f818  mov     rdx, rax; char *
0x18005f81b  lea     rcx, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f822  mov     rbx, rax
0x18005f825  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f82a  mov     rcx, rbx; this
0x18005f82d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f832  lea     rcx, aCallToCurstgIp_0; "Call to CurStg#IPropertyStorage::ReadMu"...
0x18005f839  jmp     loc_18005FA10
0x18005f83e  movzx   eax, word ptr [rbp+3Fh+pvar]
0x18005f842  bt      ax, 0Ch
0x18005f847  jnb     short loc_18005F87B
0x18005f849  test    al, 13h
0x18005f84b  jz      short loc_18005F86F
0x18005f84d  mov     rax, [rbp-51h]
0x18005f851  and     [rax], r14d
0x18005f854  mov     rax, [rbp-51h]
0x18005f858  mov     ecx, [rax]
0x18005f85a  jnz     short loc_18005F864
0x18005f85c  mov     [rax], esi
0x18005f85e  mov     ecx, esi
0x18005f860  mov     rax, [rbp-51h]
0x18005f864  mov     ebx, [rbp+3Fh+arg_30]
0x18005f867  test    ebx, ebx
0x18005f869  jz      short loc_18005F877
0x18005f86b  mov     [rax], ebx
0x18005f86d  jmp     short loc_18005F897
0x18005f86f  mov     ebx, esi
0x18005f871  test    al, 3
0x18005f873  jz      short loc_18005F897
0x18005f875  jmp     short loc_18005F84D
0x18005f877  mov     ebx, ecx
0x18005f879  jmp     short loc_18005F897
0x18005f87b  mov     ebx, dword ptr [rbp+3Fh+var_98]
0x18005f87e  and     ebx, r14d
0x18005f881  mov     dword ptr [rbp+3Fh+var_98], ebx
0x18005f884  jnz     short loc_18005F88B
0x18005f886  mov     ebx, esi
0x18005f888  mov     dword ptr [rbp+3Fh+var_98], ebx
0x18005f88b  mov     eax, [rbp+3Fh+arg_30]
0x18005f88e  test    eax, eax
0x18005f890  jz      short loc_18005F897
0x18005f892  mov     ebx, eax
0x18005f894  mov     dword ptr [rbp+3Fh+var_98], eax
0x18005f897  mov     rax, [r12+0D8h]
0x18005f89f  lea     r9, [rbp+3Fh+pvar]
0x18005f8a3  lea     r8, [rbp+3Fh+var_B0]
0x18005f8a7  mov     dword ptr [rsp+0E0h+lpMem], 2
0x18005f8af  mov     edx, r15d
0x18005f8b2  mov     rcx, [rax]
0x18005f8b5  mov     rax, [rcx]
0x18005f8b8  mov     rax, [rax+20h]
0x18005f8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f8c1  mov     edi, eax
0x18005f8c3  test    eax, eax
0x18005f8c5  jns     short loc_18005F8FF
0x18005f8c7  mov     edx, dword ptr [rbp+3Fh+var_A8]
0x18005f8ca  lea     rcx, aCallToCurstgIp; "Call to CurStg#IPropertyStorage::WriteM"...
0x18005f8d1  mov     r8d, eax
0x18005f8d4  call    WiaTrace_TraceLog
0x18005f8d9  mov     rdx, rax; char *
0x18005f8dc  lea     rcx, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f8e3  mov     rbx, rax
0x18005f8e6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f8eb  mov     rcx, rbx; this
0x18005f8ee  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f8f3  lea     rcx, aCallToCurstgIp; "Call to CurStg#IPropertyStorage::WriteM"...
0x18005f8fa  jmp     loc_18005FA10
0x18005f8ff  mov     rax, [r13+0D8h]
0x18005f906  lea     r9, [rbp+3Fh+pvar]
0x18005f90a  lea     r8, [rbp+3Fh+var_B0]
0x18005f90e  mov     edx, r15d
0x18005f911  mov     rcx, [rax+8]
0x18005f915  mov     rax, [rcx]
0x18005f918  mov     rax, [rax+18h]
0x18005f91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f921  mov     edi, eax
0x18005f923  test    eax, eax
0x18005f925  jns     short loc_18005F95F
0x18005f927  mov     edx, dword ptr [rbp+3Fh+var_A8]
0x18005f92a  lea     rcx, aCallToValidstg_0; "Call to ValidStg#IPropertyStorage::Read"...
0x18005f931  mov     r8d, eax
0x18005f934  call    WiaTrace_TraceLog
0x18005f939  mov     rdx, rax; char *
0x18005f93c  lea     rcx, aCwiaitemCopyfl; "CWiaItem::CopyFlagPropertyFrom"
0x18005f943  mov     rbx, rax
0x18005f946  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f94b  mov     rcx, rbx; this
0x18005f94e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f953  lea     rcx, aCallToValidstg_0; "Call to ValidStg#IPropertyStorage::Read"...
0x18005f95a  jmp     loc_18005FA10
0x18005f95f  movzx   eax, word ptr [rbp+3Fh+pvar]
0x18005f963  bt      ax, 0Ch
0x18005f968  jnb     short loc_18005F99A
0x18005f96a  test    al, 13h
0x18005f96c  jnz     short loc_18005F972
0x18005f96e  test    al, 3
0x18005f970  jz      short loc_18005F9AC
0x18005f972  mov     rax, [rbp-51h]
0x18005f976  and     [rax+4], r14d
0x18005f97a  mov     rcx, [rbp-51h]
0x18005f97e  cmp     dword ptr [rcx+4], 0
0x18005f982  jnz     short loc_18005F98B
0x18005f984  mov     [rcx+4], esi
0x18005f987  mov     rcx, [rbp-51h]
0x18005f98b  mov     eax, [rbp+3Fh+arg_28]
0x18005f98e  or      [rcx+4], eax
0x18005f991  mov     rax, [rbp-51h]
0x18005f995  or      [rax+4], ebx
0x18005f998  jmp     short loc_18005F9AC
0x18005f99a  mov     eax, dword ptr [rbp+3Fh+var_98]
0x18005f99d  and     eax, r14d
0x18005f9a0  jnz     short loc_18005F9A4
0x18005f9a2  mov     eax, esi
  ... truncated ...
```
