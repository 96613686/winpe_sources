# CWiaItem::CopyC2PropertyFrom(CWiaItem *,tagSTATPROPSTG &,ulong)

- ea: `0x18005ee10`
- end: `0x18005f361`
- name: `?CopyC2PropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@K@Z`
- size: `1361`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, struct CWiaItem *, struct tagSTATPROPSTG *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180019eac`
- `0x180063688`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18001c1e4`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x18005ee10`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18005f171`
- `ole32!PropVariantClear` at `0x18005f252`
- `ole32!PropVariantClear` at `0x18005f335`
- `ole32!PropVariantClear` at `0x18005f171`
- `ole32!PropVariantClear` at `0x18005f252`
- `ole32!PropVariantClear` at `0x18005f335`

## string_xrefs

- `0x18005eff2`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)`
- `0x18005f022`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)`
- `0x18005f1a4`: `Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f1c9`: `Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f1fe`: `Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f223`: `Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f07e`: `Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f0a3`: `Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f11d`: `Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f142`: `Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005ee32`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005ee46`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005ee7c`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005eea9`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005eede`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005ef0b`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005ef80`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005f001`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005f03c`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005f0c7`: `CWiaItem::CopyC2PropertyFrom`
- `0x18005eecd`: `not in compatibility mode or called on non A-AIT item (0x%X)`
- `0x18005eef7`: `not in compatibility mode or called on non A-AIT item (0x%X)`
- `0x18005f286`: `Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f2ab`: `Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f2e1`: `Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18005f306`: `Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::CopyC2PropertyFrom(
        CWiaItem *this,
        struct CWiaItem *a2,
        struct tagSTATPROPSTG *a3,
        unsigned int a4)
{
  int v8; // edi
  struct tagWiaTraceData_Type *v9; // rax
  char *v10; // rdx
  unsigned int v11; // r8d
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  PROPID propid; // eax
  _QWORD *v23; // rsi
  _QWORD *v24; // r12
  char *v25; // rbx
  void *v26; // rdx
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rcx
  char *v31; // rbx
  void *v32; // rdx
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  char *v38; // rbx
  void *v39; // rdx
  char *v40; // rbx
  void *v41; // rdx
  char *v42; // rbx
  void *v43; // rdx
  void **v44; // rax
  void *v45; // rdx
  __int64 v46; // rcx
  char *v47; // rbx
  void *v48; // rdx
  char *v49; // rbx
  void *v50; // rdx
  void **v51; // rax
  void *v52; // rdx
  __int64 v53; // rcx
  char *v54; // rbx
  void *v55; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-79h]
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v59; // [rsp+40h] [rbp-59h]
  __int128 v60; // [rsp+48h] [rbp-51h] BYREF
  __int128 v61; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v62[128]; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *NameFromWiaPropId; // [rsp+100h] [rbp+67h] BYREF
  unsigned int v64; // [rsp+118h] [rbp+7Fh] BYREF

  v8 = 0;
  v9 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::CopyC2PropertyFrom");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v62, v10, v11, "CWiaItem::CopyC2PropertyFrom", lpMem, v9);
  if ( !a2 )
  {
    v8 = -2147467261;
    v12 = (char *)WiaTrace_TraceLog("NULL source (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("NULL source (0x%X)", -2147467261);
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"CWiaItem::CopyC2PropertyFrom", 1, v14);
  }
  if ( !*((_QWORD *)this + 8) || !(unsigned int)CWiaItem::IsCompatMode(this) )
  {
    v8 = -2147467263;
    v17 = (char *)WiaTrace_TraceLog("not in compatibility mode or called on non A-AIT item (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v17);
    WiaTrcLib::Free((WiaTrcLib *)v17, v18);
    v19 = (void **)WiaTrace_Trace("not in compatibility mode or called on non A-AIT item (0x%X)", -2147467263);
    WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"CWiaItem::CopyC2PropertyFrom", 1, v19);
  }
  propid = a3->propid;
  v23 = (_QWORD *)*((_QWORD *)this + 27);
  v60 = 0;
  LODWORD(v60) = 1;
  v61 = 0;
  LODWORD(v61) = 1;
  v24 = (_QWORD *)*((_QWORD *)a2 + 27);
  DWORD2(v60) = propid;
  DWORD2(v61) = a4;
  if ( !v24 || !v23 )
  {
    v8 = -2147467261;
    v38 = (char *)WiaTrace_TraceLog("NULL storage object(s) (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v38);
    WiaTrcLib::Free((WiaTrcLib *)v38, v39);
    v27 = (void **)WiaTrace_Trace("NULL storage object(s) (0x%X)", 2147500035LL);
    goto LABEL_11;
  }
  if ( v8 < 0 )
    goto LABEL_14;
  NameFromWiaPropId = GetNameFromWiaPropId(a4);
  if ( !NameFromWiaPropId )
  {
    v25 = (char *)WiaTrace_TraceLog("warning: unable to get target property (%u) name");
    WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v25);
    WiaTrcLib::Free((WiaTrcLib *)v25, v26);
    v27 = (void **)WiaTrace_Trace("warning: unable to get target property (%u) name", a4);
LABEL_11:
    WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"CWiaItem::CopyC2PropertyFrom", 1, v27);
    goto LABEL_14;
  }
  v30 = *v23;
  v64 = a4;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, unsigned __int16 **))(*(_QWORD *)v30 + 56LL))(
         v30,
         1,
         &v64,
         &NameFromWiaPropId);
  if ( v8 < 0 )
  {
    v31 = (char *)WiaTrace_TraceLog("Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v31);
    WiaTrcLib::Free((WiaTrcLib *)v31, v32);
    v27 = (void **)WiaTrace_Trace(
                     "Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)",
                     a3->propid,
                     v8);
    goto LABEL_11;
  }
LABEL_14:
  v59 = 0;
  *(_OWORD *)pvar = 0;
  if ( v8 < 0 )
    goto LABEL_21;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v24[2] + 24LL))(
         v24[2],
         1,
         &v60,
         pvar);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *, int))(*(_QWORD *)v23[2] + 32LL))(
           v23[2],
           1,
           &v61,
           pvar,
           2);
    if ( v8 >= 0 )
      goto LABEL_21;
    v40 = (char *)WiaTrace_TraceLog("Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v40);
    WiaTrcLib::Free((WiaTrcLib *)v40, v41);
    v35 = (void **)WiaTrace_Trace(
                     "Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)",
                     a3->propid,
                     (unsigned int)v8);
  }
  else
  {
    v33 = (char *)WiaTrace_TraceLog("Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v33);
    WiaTrcLib::Free((WiaTrcLib *)v33, v34);
    v35 = (void **)WiaTrace_Trace(
                     "Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)",
                     a3->propid,
                     (unsigned int)v8);
  }
  WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"CWiaItem::CopyC2PropertyFrom", 1, v35);
LABEL_21:
  if ( LOWORD(pvar[0]) )
    PropVariantClear(pvar);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *))(*(_QWORD *)*v24 + 24LL))(
           *v24,
           1,
           &v60,
           pvar);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *, int))(*(_QWORD *)*v23 + 32LL))(
             *v23,
             1,
             &v61,
             pvar,
             2);
      if ( v8 >= 0 )
        goto LABEL_29;
      v47 = (char *)WiaTrace_TraceLog("Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v47);
      WiaTrcLib::Free((WiaTrcLib *)v47, v48);
      v44 = (void **)WiaTrace_Trace(
                       "Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)",
                       a3->propid,
                       (unsigned int)v8);
    }
    else
    {
      v42 = (char *)WiaTrace_TraceLog("Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v42);
      WiaTrcLib::Free((WiaTrcLib *)v42, v43);
      v44 = (void **)WiaTrace_Trace(
                       "Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)",
                       a3->propid,
                       (unsigned int)v8);
    }
    WiaTrace_ProcessTrace_Ex(v46, v45, (void *)"CWiaItem::CopyC2PropertyFrom", 1, v44);
  }
LABEL_29:
  if ( LOWORD(pvar[0]) )
    PropVariantClear(pvar);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v24[1] + 24LL))(
           v24[1],
           1,
           &v60,
           pvar);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *, int))(*(_QWORD *)v23[1] + 32LL))(
             v23[1],
             1,
             &v61,
             pvar,
             2);
      if ( v8 >= 0 )
        goto LABEL_37;
      v54 = (char *)WiaTrace_TraceLog("Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v54);
      WiaTrcLib::Free((WiaTrcLib *)v54, v55);
      v51 = (void **)WiaTrace_Trace(
                       "Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)",
                       a3->propid,
                       (unsigned int)v8);
    }
    else
    {
      v49 = (char *)WiaTrace_TraceLog("Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyC2PropertyFrom", v49);
      WiaTrcLib::Free((WiaTrcLib *)v49, v50);
      v51 = (void **)WiaTrace_Trace(
                       "Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)",
                       a3->propid,
                       (unsigned int)v8);
    }
    WiaTrace_ProcessTrace_Ex(v53, v52, (void *)"CWiaItem::CopyC2PropertyFrom", 1, v51);
  }
LABEL_37:
  if ( LOWORD(pvar[0]) )
    PropVariantClear(pvar);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v62);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005ee10  mov     [rsp-8+arg_8], rbx
0x18005ee15  push    rbp
0x18005ee16  push    rsi
0x18005ee17  push    rdi
0x18005ee18  push    r12
0x18005ee1a  push    r13
0x18005ee1c  push    r14
0x18005ee1e  push    r15
0x18005ee20  lea     rbp, [rsp-27h]
0x18005ee25  sub     rsp, 0C0h
0x18005ee2c  mov     rsi, rcx
0x18005ee2f  mov     r15d, r9d
0x18005ee32  lea     rcx, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005ee39  mov     r14, r8
0x18005ee3c  mov     r13, rdx
0x18005ee3f  xor     edi, edi
0x18005ee41  call    WiaTrace_Trace
0x18005ee46  lea     r9, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005ee4d  mov     [rsp+0F0h+var_C8], rax; struct tagWiaTraceData_Type *
0x18005ee52  lea     rcx, [rbp+57h+var_80]; this
0x18005ee56  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18005ee5b  lea     r12d, [rdi+1]
0x18005ee5f  mov     eax, 80004003h
0x18005ee64  test    r13, r13
0x18005ee67  jnz     short loc_18005EEB5
0x18005ee69  mov     edx, eax
0x18005ee6b  lea     rcx, aNullSource0xX; "NULL source (0x%X)"
0x18005ee72  mov     edi, eax
0x18005ee74  call    WiaTrace_TraceLog
0x18005ee79  mov     rdx, rax; char *
0x18005ee7c  lea     rcx, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005ee83  mov     rbx, rax
0x18005ee86  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ee8b  mov     rcx, rbx; this
0x18005ee8e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ee93  mov     edx, edi
0x18005ee95  lea     rcx, aNullSource0xX; "NULL source (0x%X)"
0x18005ee9c  call    WiaTrace_Trace
0x18005eea1  mov     r9d, r12d; int
0x18005eea4  mov     [rsp+0F0h+lpMem], rax; lpMem
0x18005eea9  lea     r8, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005eeb0  call    WiaTrace_ProcessTrace_Ex
0x18005eeb5  cmp     qword ptr [rsi+40h], 0
0x18005eeba  jz      short loc_18005EEC8
0x18005eebc  mov     rcx, rsi; this
0x18005eebf  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x18005eec4  test    eax, eax
0x18005eec6  jnz     short loc_18005EF17
0x18005eec8  mov     edi, 80004001h
0x18005eecd  lea     rcx, aNotInCompatibi_2; "not in compatibility mode or called on "...
0x18005eed4  mov     edx, edi
0x18005eed6  call    WiaTrace_TraceLog
0x18005eedb  mov     rdx, rax; char *
0x18005eede  lea     rcx, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005eee5  mov     rbx, rax
0x18005eee8  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005eeed  mov     rcx, rbx; this
0x18005eef0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005eef5  mov     edx, edi
0x18005eef7  lea     rcx, aNotInCompatibi_2; "not in compatibility mode or called on "...
0x18005eefe  call    WiaTrace_Trace
0x18005ef03  mov     r9d, r12d; int
0x18005ef06  mov     [rsp+0F0h+lpMem], rax; lpMem
0x18005ef0b  lea     r8, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005ef12  call    WiaTrace_ProcessTrace_Ex
0x18005ef17  mov     eax, [r14+8]
0x18005ef1b  xorps   xmm0, xmm0
0x18005ef1e  mov     rsi, [rsi+0D8h]
0x18005ef25  xorps   xmm1, xmm1
0x18005ef28  movups  [rbp+57h+var_A8], xmm0
0x18005ef2c  mov     dword ptr [rbp+57h+var_A8], r12d
0x18005ef30  movups  [rbp+57h+var_98], xmm1
0x18005ef34  mov     dword ptr [rbp+57h+var_98], r12d
0x18005ef38  mov     r12, [r13+0D8h]
0x18005ef3f  mov     dword ptr [rbp+57h+var_A8+8], eax
0x18005ef42  mov     dword ptr [rbp+57h+var_98+8], r15d
0x18005ef46  test    r12, r12
0x18005ef49  jz      loc_18005F0AF
0x18005ef4f  test    rsi, rsi
0x18005ef52  jz      loc_18005F0AF
0x18005ef58  test    edi, edi
0x18005ef5a  js      loc_18005F036
0x18005ef60  mov     ecx, r15d; unsigned int
0x18005ef63  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18005ef68  mov     [rbp+57h+arg_0], rax
0x18005ef6c  test    rax, rax
0x18005ef6f  jnz     short loc_18005EFC4
0x18005ef71  mov     edx, r15d
0x18005ef74  lea     rcx, aWarningUnableT; "warning: unable to get target property "...
0x18005ef7b  call    WiaTrace_TraceLog
0x18005ef80  lea     r13, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005ef87  mov     rdx, rax; char *
0x18005ef8a  mov     rcx, r13; char *
0x18005ef8d  mov     rbx, rax
0x18005ef90  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ef95  mov     rcx, rbx; this
0x18005ef98  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ef9d  lea     rcx, aWarningUnableT; "warning: unable to get target property "...
0x18005efa4  mov     edx, r15d
0x18005efa7  call    WiaTrace_Trace
0x18005efac  mov     r15d, 1
0x18005efb2  mov     r9d, r15d; int
0x18005efb5  mov     [rsp+0F0h+lpMem], rax; lpMem
0x18005efba  mov     r8, r13; int
0x18005efbd  call    WiaTrace_ProcessTrace_Ex
0x18005efc2  jmp     short loc_18005F043
0x18005efc4  mov     rcx, [rsi]
0x18005efc7  lea     r9, [rbp+57h+arg_0]
0x18005efcb  mov     [rbp+57h+arg_18], r15d
0x18005efcf  lea     r8, [rbp+57h+arg_18]
0x18005efd3  mov     r15d, 1
0x18005efd9  mov     edx, r15d
0x18005efdc  mov     rax, [rcx]
0x18005efdf  mov     rax, [rax+38h]
0x18005efe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efe8  mov     edi, eax
0x18005efea  test    eax, eax
0x18005efec  jns     short loc_18005F03C
0x18005efee  mov     edx, [r14+8]
0x18005eff2  lea     rcx, aCallToIwiaprop_0; "Call to IWiaPropertyStorage::WritePrope"...
0x18005eff9  mov     r8d, eax
0x18005effc  call    WiaTrace_TraceLog
0x18005f001  lea     r13, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005f008  mov     rdx, rax; char *
0x18005f00b  mov     rcx, r13; char *
0x18005f00e  mov     rbx, rax
0x18005f011  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f016  mov     rcx, rbx; this
0x18005f019  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f01e  mov     edx, [r14+8]
0x18005f022  lea     rcx, aCallToIwiaprop_0; "Call to IWiaPropertyStorage::WritePrope"...
0x18005f029  mov     r8d, edi
0x18005f02c  call    WiaTrace_Trace
0x18005f031  jmp     loc_18005EFB2
0x18005f036  mov     r15d, 1
0x18005f03c  lea     r13, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005f043  xor     eax, eax
0x18005f045  xorps   xmm0, xmm0
0x18005f048  mov     [rbp+57h+var_B0], rax
0x18005f04c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18005f050  test    edi, edi
0x18005f052  js      loc_18005F165
0x18005f058  mov     rcx, [r12+10h]
0x18005f05d  lea     r9, [rbp+57h+pvar]
0x18005f061  lea     r8, [rbp+57h+var_A8]
0x18005f065  mov     edx, r15d
0x18005f068  mov     rax, [rcx]
0x18005f06b  mov     rax, [rax+18h]
0x18005f06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f074  mov     edi, eax
0x18005f076  test    eax, eax
0x18005f078  jns     short loc_18005F0F0
0x18005f07a  mov     edx, [r14+8]
0x18005f07e  lea     rcx, aCallToAccessst; "Call to AccessStg#IPropertyStorage::Rea"...
0x18005f085  mov     r8d, eax
0x18005f088  call    WiaTrace_TraceLog
0x18005f08d  mov     rdx, rax; char *
0x18005f090  mov     rcx, r13; char *
0x18005f093  mov     rbx, rax
0x18005f096  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f09b  mov     rcx, rbx; this
0x18005f09e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f0a3  lea     rcx, aCallToAccessst; "Call to AccessStg#IPropertyStorage::Rea"...
0x18005f0aa  jmp     loc_18005F149
0x18005f0af  mov     r15d, 80004003h
0x18005f0b5  lea     rcx, aNullStorageObj; "NULL storage object(s) (0x%X)"
0x18005f0bc  mov     edx, r15d
0x18005f0bf  mov     edi, r15d
0x18005f0c2  call    WiaTrace_TraceLog
0x18005f0c7  lea     r13, aCwiaitemCopyc2; "CWiaItem::CopyC2PropertyFrom"
0x18005f0ce  mov     rdx, rax; char *
0x18005f0d1  mov     rcx, r13; char *
0x18005f0d4  mov     rbx, rax
0x18005f0d7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f0dc  mov     rcx, rbx; this
0x18005f0df  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f0e4  lea     rcx, aNullStorageObj; "NULL storage object(s) (0x%X)"
0x18005f0eb  jmp     loc_18005EFA4
0x18005f0f0  mov     rcx, [rsi+10h]
0x18005f0f4  lea     r9, [rbp+57h+pvar]
0x18005f0f8  lea     r8, [rbp+57h+var_98]
0x18005f0fc  mov     dword ptr [rsp+0F0h+lpMem], 2
0x18005f104  mov     edx, r15d
0x18005f107  mov     rax, [rcx]
0x18005f10a  mov     rax, [rax+20h]
0x18005f10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f113  mov     edi, eax
0x18005f115  test    eax, eax
0x18005f117  jns     short loc_18005F165
0x18005f119  mov     edx, [r14+8]
0x18005f11d  lea     rcx, aCallToAccessst_0; "Call to AccessStg#IPropertyStorage::Wri"...
0x18005f124  mov     r8d, eax
0x18005f127  call    WiaTrace_TraceLog
0x18005f12c  mov     rdx, rax; char *
0x18005f12f  mov     rcx, r13; char *
0x18005f132  mov     rbx, rax
0x18005f135  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f13a  mov     rcx, rbx; this
0x18005f13d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f142  lea     rcx, aCallToAccessst_0; "Call to AccessStg#IPropertyStorage::Wri"...
0x18005f149  mov     edx, [r14+8]
0x18005f14d  mov     r8d, edi
0x18005f150  call    WiaTrace_Trace
0x18005f155  mov     r9d, r15d; int
0x18005f158  mov     [rsp+0F0h+lpMem], rax; lpMem
0x18005f15d  mov     r8, r13; int
0x18005f160  call    WiaTrace_ProcessTrace_Ex
0x18005f165  xor     eax, eax
0x18005f167  cmp     ax, word ptr [rbp+57h+pvar]
0x18005f16b  jz      short loc_18005F177
0x18005f16d  lea     rcx, [rbp+57h+pvar]; pvar
0x18005f171  call    cs:__imp_PropVariantClear
0x18005f177  test    edi, edi
0x18005f179  js      loc_18005F246
0x18005f17f  mov     rcx, [r12]
0x18005f183  lea     r9, [rbp+57h+pvar]
0x18005f187  lea     r8, [rbp+57h+var_A8]
0x18005f18b  mov     edx, r15d
0x18005f18e  mov     rax, [rcx]
0x18005f191  mov     rax, [rax+18h]
0x18005f195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f19a  mov     edi, eax
0x18005f19c  test    eax, eax
0x18005f19e  jns     short loc_18005F1D2
0x18005f1a0  mov     edx, [r14+8]
0x18005f1a4  lea     rcx, aCallToCurstgIp_0; "Call to CurStg#IPropertyStorage::ReadMu"...
0x18005f1ab  mov     r8d, eax
0x18005f1ae  call    WiaTrace_TraceLog
0x18005f1b3  mov     rdx, rax; char *
0x18005f1b6  mov     rcx, r13; char *
0x18005f1b9  mov     rbx, rax
0x18005f1bc  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f1c1  mov     rcx, rbx; this
0x18005f1c4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f1c9  lea     rcx, aCallToCurstgIp_0; "Call to CurStg#IPropertyStorage::ReadMu"...
0x18005f1d0  jmp     short loc_18005F22A
0x18005f1d2  mov     rcx, [rsi]
0x18005f1d5  lea     r9, [rbp+57h+pvar]
0x18005f1d9  lea     r8, [rbp+57h+var_98]
0x18005f1dd  mov     dword ptr [rsp+0F0h+lpMem], 2
0x18005f1e5  mov     edx, r15d
0x18005f1e8  mov     rax, [rcx]
0x18005f1eb  mov     rax, [rax+20h]
0x18005f1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f1f4  mov     edi, eax
0x18005f1f6  test    eax, eax
0x18005f1f8  jns     short loc_18005F246
0x18005f1fa  mov     edx, [r14+8]
0x18005f1fe  lea     rcx, aCallToCurstgIp; "Call to CurStg#IPropertyStorage::WriteM"...
0x18005f205  mov     r8d, eax
0x18005f208  call    WiaTrace_TraceLog
0x18005f20d  mov     rdx, rax; char *
0x18005f210  mov     rcx, r13; char *
0x18005f213  mov     rbx, rax
0x18005f216  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f21b  mov     rcx, rbx; this
0x18005f21e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f223  lea     rcx, aCallToCurstgIp; "Call to CurStg#IPropertyStorage::WriteM"...
0x18005f22a  mov     edx, [r14+8]
0x18005f22e  mov     r8d, edi
0x18005f231  call    WiaTrace_Trace
0x18005f236  mov     r9d, r15d; int
0x18005f239  mov     [rsp+0F0h+lpMem], rax; lpMem
0x18005f23e  mov     r8, r13; int
0x18005f241  call    WiaTrace_ProcessTrace_Ex
0x18005f246  xor     eax, eax
0x18005f248  cmp     ax, word ptr [rbp+57h+pvar]
0x18005f24c  jz      short loc_18005F258
0x18005f24e  lea     rcx, [rbp+57h+pvar]; pvar
0x18005f252  call    cs:__imp_PropVariantClear
0x18005f258  test    edi, edi
0x18005f25a  js      loc_18005F329
0x18005f260  mov     rcx, [r12+8]
0x18005f265  lea     r9, [rbp+57h+pvar]
0x18005f269  lea     r8, [rbp+57h+var_A8]
0x18005f26d  mov     edx, r15d
0x18005f270  mov     rax, [rcx]
0x18005f273  mov     rax, [rax+18h]
0x18005f277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f27c  mov     edi, eax
0x18005f27e  test    eax, eax
0x18005f280  jns     short loc_18005F2B4
0x18005f282  mov     edx, [r14+8]
0x18005f286  lea     rcx, aCallToValidstg_0; "Call to ValidStg#IPropertyStorage::Read"...
0x18005f28d  mov     r8d, eax
0x18005f290  call    WiaTrace_TraceLog
0x18005f295  mov     rdx, rax; char *
0x18005f298  mov     rcx, r13; char *
0x18005f29b  mov     rbx, rax
0x18005f29e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005f2a3  mov     rcx, rbx; this
0x18005f2a6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005f2ab  lea     rcx, aCallToValidstg_0; "Call to ValidStg#IPropertyStorage::Read"...
0x18005f2b2  jmp     short loc_18005F30D
0x18005f2b4  mov     rcx, [rsi+8]
0x18005f2b8  lea     r9, [rbp+57h+pvar]
0x18005f2bc  lea     r8, [rbp+57h+var_98]
0x18005f2c0  mov     dword ptr [rsp+0F0h+lpMem], 2
0x18005f2c8  mov     edx, r15d
0x18005f2cb  mov     rax, [rcx]
  ... truncated ...
```
