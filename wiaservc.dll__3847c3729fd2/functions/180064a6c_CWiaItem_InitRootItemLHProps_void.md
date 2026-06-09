# CWiaItem::InitRootItemLHProps(void)

- ea: `0x180064a6c`
- end: `0x180064fb9`
- name: `?InitRootItemLHProps@CWiaItem@@QEAAJXZ`
- size: `1357`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800552bc`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x180017740`
- `0x180017e90`
- `0x18001ad9c`
- `0x18001e364`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x18005f520`
- `0x180064a6c`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180064d1c`
- `ole32!CoTaskMemFree` at `0x180064d1c`
- `ole32!PropVariantClear` at `0x180064f0b`
- `ole32!PropVariantClear` at `0x180064f0b`
- `ole32!CoTaskMemAlloc` at `0x180064db2`
- `ole32!CoTaskMemAlloc` at `0x180064db2`

## string_xrefs

- `0x180064cd2`: `C1 property copy failed (0x%X)`
- `0x180064cf4`: `C1 property copy failed (0x%X)`
- `0x180064b26`: `failed to get property enumerator for properties to copy (0x%X)`
- `0x180064b4a`: `failed to get property enumerator for properties to copy (0x%X)`
- `0x180064b72`: `not in compatibility mode or called on non LH A-AIT root item (0x%X)`
- `0x180064b98`: `not in compatibility mode or called on non LH A-AIT root item (0x%X)`
- `0x180064f41`: `Call to wiasSetItemPropNames(WIA_IPA_ITEM_CATEGORY) failed (0x%X)`
- `0x180064f65`: `Call to wiasSetItemPropNames(WIA_IPA_ITEM_CATEGORY) failed (0x%X)`
- `0x180064e69`: `Call to wiasSetItemPropAttribs(WIA_IPA_ITEM_CATEGORY) failed (0x%X)`
- `0x180064e8b`: `Call to wiasSetItemPropAttribs(WIA_IPA_ITEM_CATEGORY) failed (0x%X)`
- `0x180064ec6`: `Call to WriteMultiple(WIA_IPA_ITEM_CATEGORY) failed (0x%X)`
- `0x180064ee8`: `Call to WriteMultiple(WIA_IPA_ITEM_CATEGORY) failed (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::InitRootItemLHProps(CWiaItem *this)
{
  struct tagWiaTraceData_Type *v2; // rax
  char *v3; // rdx
  unsigned int v4; // r8d
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // edi
  char *v9; // rbx
  void *v10; // rdx
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  char *v14; // rbx
  void *v15; // rdx
  void **v16; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  struct CWiaItem *v20; // rdx
  char *v21; // rbx
  void *v22; // rdx
  void **v23; // rax
  void *v24; // rdx
  __int64 v25; // rcx
  char *v26; // rbx
  void *v27; // rdx
  GUID *v28; // rax
  GUID *v29; // r14
  char *v30; // rbx
  void *v31; // rdx
  void **v32; // rax
  void *v33; // rdx
  __int64 v34; // rcx
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  char *v40; // rbx
  void *v41; // rdx
  char *v42; // rbx
  void *v43; // rdx
  void **v44; // rax
  void *v45; // rdx
  __int64 v46; // rcx
  unsigned int lpMem; // [rsp+28h] [rbp-E0h]
  __int64 v49; // [rsp+48h] [rbp-C0h] BYREF
  __int64 pv; // [rsp+50h] [rbp-B8h] BYREF
  struct tagSTATPROPSTG pv_8; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int pvar; // [rsp+68h] [rbp-A0h] BYREF
  PROPVARIANT pvar_8[4]; // [rsp+70h] [rbp-98h] BYREF
  int v54; // [rsp+90h] [rbp-78h] BYREF
  __int64 v55; // [rsp+98h] [rbp-70h]
  unsigned __int16 *v56; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v57[80]; // [rsp+A8h] [rbp-60h] BYREF
  int v58; // [rsp+F8h] [rbp-10h]
  __int128 v59; // [rsp+FCh] [rbp-Ch]
  __int128 v60; // [rsp+10Ch] [rbp+4h]
  int v61; // [rsp+11Ch] [rbp+14h]

  v2 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::InitRootItemLHProps");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v57, v3, v4, "CWiaItem::InitRootItemLHProps", lpMem, v2);
  if ( *((_QWORD *)this + 8) && *((_DWORD *)this + 26) == 1 && *((CWiaItem **)this + 26) == this )
  {
    v5 = *((_QWORD *)this + 8) + 8LL;
    pv = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 88LL))(v5, &pv);
    v7 = pv;
    v8 = v6;
    if ( pv )
    {
      if ( v6 >= 0 )
        goto LABEL_9;
    }
    else
    {
      v8 = -2147024882;
    }
    v9 = (char *)WiaTrace_TraceLog("failed to get property enumerator for properties to copy (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::InitRootItemLHProps", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    v11 = (void **)WiaTrace_Trace("failed to get property enumerator for properties to copy (0x%X)", v8);
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"CWiaItem::InitRootItemLHProps", 1, v11);
    v7 = pv;
  }
  else
  {
    v8 = -2147467261;
    v14 = (char *)WiaTrace_TraceLog("not in compatibility mode or called on non LH A-AIT root item (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::InitRootItemLHProps", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    v16 = (void **)WiaTrace_Trace("not in compatibility mode or called on non LH A-AIT root item (0x%X)", -2147467261);
    WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"CWiaItem::InitRootItemLHProps", 1, v16);
    v7 = 0;
    pv = 0;
  }
LABEL_9:
  LODWORD(v49) = 0;
  pv_8 = 0;
  if ( v8 < 0 )
    goto LABEL_26;
  while ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct tagSTATPROPSTG *, __int64 *))(*(_QWORD *)v7 + 24LL))(
             v7,
             1,
             &pv_8,
             &v49)
       && (_DWORD)v49 == 1 )
  {
    memset(pvar_8, 0, sizeof(pvar_8));
    if ( (unsigned int)CWiaItem::GetPropCompatCategory(v19, pv_8.propid, 1, 8, pvar_8) )
    {
      if ( ((HIDWORD(pvar_8[2]) - 4) & 0xFFFFFFFB) != 0 )
        goto LABEL_21;
      v20 = (struct CWiaItem *)*((_QWORD *)this + 8);
      if ( pv_8.propid != 3086 )
      {
        CWiaItem::CopyPropertyFrom(this, v20, &pv_8);
        goto LABEL_21;
      }
      v8 = CWiaItem::CopyFlagPropertyFrom(this, v20, &pv_8, 63, 2u, 0, 0);
      if ( v8 >= 0 )
        goto LABEL_21;
      v21 = (char *)WiaTrace_TraceLog("WIA_DPS_DOCUMENT_HANDLING_CAPABILITIES translation failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitRootItemLHProps", v21);
      WiaTrcLib::Free((WiaTrcLib *)v21, v22);
      v23 = (void **)WiaTrace_Trace(
                       "WIA_DPS_DOCUMENT_HANDLING_CAPABILITIES translation failed (0x%X)",
                       (unsigned int)v8);
    }
    else
    {
      v8 = CWiaItem::CopyPropertyFrom(this, *((struct CWiaItem **)this + 8), &pv_8);
      if ( v8 >= 0 )
        goto LABEL_21;
      v26 = (char *)WiaTrace_TraceLog("C1 property copy failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitRootItemLHProps", v26);
      WiaTrcLib::Free((WiaTrcLib *)v26, v27);
      v23 = (void **)WiaTrace_Trace("C1 property copy failed (0x%X)", (unsigned int)v8);
    }
    WiaTrace_ProcessTrace_Ex(v25, v24, (void *)"CWiaItem::InitRootItemLHProps", 1, v23);
LABEL_21:
    if ( pv_8.lpwstrName )
    {
      CoTaskMemFree(pv_8.lpwstrName);
      pv_8.lpwstrName = 0;
    }
    if ( v8 < 0 )
      break;
    v7 = pv;
    LODWORD(v49) = 0;
  }
  v7 = pv;
LABEL_26:
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    pv = 0;
  }
  if ( v8 >= 0 )
  {
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 1) + 72LL))((char *)this + 8, 1);
    v54 = 0;
    v55 = 0;
    memset(pvar_8, 0, 24);
    v58 = 0;
    v59 = 0;
    v61 = 0;
    v60 = 0;
    v28 = (GUID *)CoTaskMemAlloc(0x10u);
    v29 = v28;
    if ( v28 )
    {
      *v28 = WIA_CATEGORY_ROOT;
    }
    else
    {
      v8 = -2147024882;
      v30 = (char *)WiaTrace_TraceLog("cannot allocate memory for item category GUID (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitRootItemLHProps", v30);
      WiaTrcLib::Free((WiaTrcLib *)v30, v31);
      v32 = (void **)WiaTrace_Trace("cannot allocate memory for item category GUID (0x%X)", -2147024882);
      WiaTrace_ProcessTrace_Ex(v34, v33, (void *)"CWiaItem::InitRootItemLHProps", 1, v32);
    }
    v54 = 1;
    v58 = 9;
    LOWORD(v59) = 72;
    pvar_8[0] = (PROPVARIANT)72;
    *(_OWORD *)&pvar_8[1] = (unsigned __int64)v29;
    LODWORD(v55) = 4125;
    if ( v8 >= 0 )
    {
      v8 = wiasSetItemPropAttribs(this);
      if ( v8 < 0 )
      {
        v35 = (char *)WiaTrace_TraceLog("Call to wiasSetItemPropAttribs(WIA_IPA_ITEM_CATEGORY) failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitRootItemLHProps", v35);
        WiaTrcLib::Free((WiaTrcLib *)v35, v36);
        v37 = (void **)WiaTrace_Trace(
                         "Call to wiasSetItemPropAttribs(WIA_IPA_ITEM_CATEGORY) failed (0x%X)",
                         (unsigned int)v8);
        goto LABEL_37;
      }
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *, int))(***((_QWORD ***)this + 27) + 32LL))(
             **((_QWORD **)this + 27),
             1,
             &v54,
             pvar_8,
             4098);
      if ( v8 < 0 )
      {
        v40 = (char *)WiaTrace_TraceLog("Call to WriteMultiple(WIA_IPA_ITEM_CATEGORY) failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitRootItemLHProps", v40);
        WiaTrcLib::Free((WiaTrcLib *)v40, v41);
        v37 = (void **)WiaTrace_Trace("Call to WriteMultiple(WIA_IPA_ITEM_CATEGORY) failed (0x%X)", (unsigned int)v8);
LABEL_37:
        WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"CWiaItem::InitRootItemLHProps", 1, v37);
      }
    }
    PropVariantClear(pvar_8);
    if ( v8 >= 0 )
    {
      pvar = 4125;
      v56 = L"Item Category";
      v8 = wiasSetItemPropNames(this, 1, &pvar, &v56);
      if ( v8 < 0 )
      {
        v42 = (char *)WiaTrace_TraceLog("Call to wiasSetItemPropNames(WIA_IPA_ITEM_CATEGORY) failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitRootItemLHProps", v42);
        WiaTrcLib::Free((WiaTrcLib *)v42, v43);
        v44 = (void **)WiaTrace_Trace("Call to wiasSetItemPropNames(WIA_IPA_ITEM_CATEGORY) failed (0x%X)", v8);
        WiaTrace_ProcessTrace_Ex(v46, v45, (void *)"CWiaItem::InitRootItemLHProps", 1, v44);
      }
    }
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v57);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180064a6c  mov     rax, rsp
0x180064a6f  mov     [rax+10h], rbx
0x180064a73  mov     [rax+18h], rsi
0x180064a77  push    rbp
0x180064a78  push    rdi
0x180064a79  push    r12
0x180064a7b  push    r13
0x180064a7d  push    r14
0x180064a7f  lea     rbp, [rax-58h]
0x180064a83  sub     rsp, 130h
0x180064a8a  movaps  xmmword ptr [rax-38h], xmm6
0x180064a8e  mov     rax, cs:__security_cookie
0x180064a95  xor     rax, rsp
0x180064a98  mov     [rbp+50h+var_38], rax
0x180064a9c  mov     rsi, rcx
0x180064a9f  lea     r13, aCwiaitemInitro_1; "CWiaItem::InitRootItemLHProps"
0x180064aa6  mov     rcx, r13
0x180064aa9  call    WiaTrace_Trace
0x180064aae  mov     r9, r13; char *
0x180064ab1  mov     [rsp+150h+var_128], rax; struct tagWiaTraceData_Type *
0x180064ab6  lea     rcx, [rbp+50h+var_B0]; this
0x180064aba  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180064abf  cmp     qword ptr [rsi+40h], 0
0x180064ac4  mov     r12d, 1
0x180064aca  jz      loc_180064B6D
0x180064ad0  cmp     [rsi+68h], r12d
0x180064ad4  jnz     loc_180064B6D
0x180064ada  cmp     [rsi+0D0h], rsi
0x180064ae1  jnz     loc_180064B6D
0x180064ae7  mov     rcx, [rsi+40h]
0x180064aeb  lea     rdx, [rsp+150h+pv]
0x180064af0  add     rcx, 8
0x180064af4  mov     [rsp+150h+pv], 0
0x180064afd  mov     rax, [rcx]
0x180064b00  mov     rax, [rax+58h]
0x180064b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b09  mov     rcx, [rsp+150h+pv]
0x180064b0e  mov     edi, eax
0x180064b10  test    rcx, rcx
0x180064b13  jnz     short loc_180064B1C
0x180064b15  mov     edi, 8007000Eh
0x180064b1a  jmp     short loc_180064B24
0x180064b1c  test    eax, eax
0x180064b1e  jns     loc_180064BBB
0x180064b24  mov     edx, edi
0x180064b26  lea     rcx, aFailedToGetPro; "failed to get property enumerator for p"...
0x180064b2d  call    WiaTrace_TraceLog
0x180064b32  mov     rdx, rax; char *
0x180064b35  mov     rcx, r13; char *
0x180064b38  mov     rbx, rax
0x180064b3b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180064b40  mov     rcx, rbx; this
0x180064b43  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180064b48  mov     edx, edi
0x180064b4a  lea     rcx, aFailedToGetPro; "failed to get property enumerator for p"...
0x180064b51  call    WiaTrace_Trace
0x180064b56  mov     r9d, r12d; int
0x180064b59  mov     [rsp+150h+lpMem], rax; lpMem
0x180064b5e  mov     r8, r13; int
0x180064b61  call    WiaTrace_ProcessTrace_Ex
0x180064b66  mov     rcx, [rsp+150h+pv]
0x180064b6b  jmp     short loc_180064BBB
0x180064b6d  mov     edi, 80004003h
0x180064b72  lea     rcx, aNotInCompatibi_0; "not in compatibility mode or called on "...
0x180064b79  mov     edx, edi
0x180064b7b  call    WiaTrace_TraceLog
0x180064b80  mov     rdx, rax; char *
0x180064b83  mov     rcx, r13; char *
0x180064b86  mov     rbx, rax
0x180064b89  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180064b8e  mov     rcx, rbx; this
0x180064b91  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180064b96  mov     edx, edi
0x180064b98  lea     rcx, aNotInCompatibi_0; "not in compatibility mode or called on "...
0x180064b9f  call    WiaTrace_Trace
0x180064ba4  mov     r9d, r12d; int
0x180064ba7  mov     [rsp+150h+lpMem], rax; lpMem
0x180064bac  mov     r8, r13; int
0x180064baf  call    WiaTrace_ProcessTrace_Ex
0x180064bb4  xor     ecx, ecx
0x180064bb6  mov     [rsp+150h+pv], rcx
0x180064bbb  mov     dword ptr [rsp+150h+var_110], 0
0x180064bc3  xorps   xmm0, xmm0
0x180064bc6  movups  xmmword ptr [rsp+150h+pv+8], xmm0
0x180064bcb  test    edi, edi
0x180064bcd  js      loc_180064D46
0x180064bd3  mov     rax, [rcx]
0x180064bd6  lea     r9, [rsp+150h+var_110]
0x180064bdb  lea     r8, [rsp+150h+pv+8]
0x180064be0  mov     edx, r12d
0x180064be3  mov     rax, [rax+18h]
0x180064be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064bec  test    eax, eax
0x180064bee  jnz     loc_180064D41
0x180064bf4  cmp     dword ptr [rsp+150h+var_110], r12d
0x180064bf9  jnz     loc_180064D41
0x180064bff  mov     edx, [rsp+150h+var_F8]
0x180064c03  lea     rax, [rsp+150h+pvar+8]
0x180064c08  xorps   xmm0, xmm0
0x180064c0b  mov     [rsp+150h+lpMem], rax
0x180064c10  mov     r9d, 8
0x180064c16  mov     r8d, r12d
0x180064c19  movups  xmmword ptr [rsp+150h+pvar+8], xmm0
0x180064c1e  movups  [rsp+150h+var_E0+8], xmm0
0x180064c23  call    ?GetPropCompatCategory@CWiaItem@@QEAAHKHW4_CL_ITEM@@AEAU_PROP_COMPAT_TABLE@@@Z; CWiaItem::GetPropCompatCategory(ulong,int,_CL_ITEM,_PROP_COMPAT_TABLE &)
0x180064c28  test    eax, eax
0x180064c2a  jz      loc_180064CB9
0x180064c30  mov     eax, dword ptr [rsp+150h+var_E0+0Ch]
0x180064c34  add     eax, 0FFFFFFFCh
0x180064c37  test    eax, 0FFFFFFFBh
0x180064c3c  jnz     loc_180064D12
0x180064c42  cmp     [rsp+150h+var_F8], 0C0Eh
0x180064c4a  lea     r8, [rsp+150h+pv+8]; struct tagSTATPROPSTG *
0x180064c4f  mov     rdx, [rsi+40h]; struct CWiaItem *
0x180064c53  mov     rcx, rsi; this
0x180064c56  jnz     short loc_180064CB2
0x180064c58  mov     [rsp+150h+var_120], 0; unsigned int
0x180064c60  mov     r9d, 3Fh ; '?'; unsigned int
0x180064c66  mov     dword ptr [rsp+150h+var_128], 0; unsigned int
0x180064c6e  mov     dword ptr [rsp+150h+lpMem], 2; unsigned int
0x180064c76  call    ?CopyFlagPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@KKKK@Z; CWiaItem::CopyFlagPropertyFrom(CWiaItem *,tagSTATPROPSTG &,ulong,ulong,ulong,ulong)
0x180064c7b  mov     edi, eax
0x180064c7d  test    eax, eax
0x180064c7f  jns     loc_180064D12
0x180064c85  mov     edx, eax
0x180064c87  lea     rcx, aWiaDpsDocument_0; "WIA_DPS_DOCUMENT_HANDLING_CAPABILITIES "...
0x180064c8e  call    WiaTrace_TraceLog
0x180064c93  mov     rdx, rax; char *
0x180064c96  mov     rcx, r13; char *
0x180064c99  mov     rbx, rax
0x180064c9c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180064ca1  mov     rcx, rbx; this
0x180064ca4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180064ca9  lea     rcx, aWiaDpsDocument_0; "WIA_DPS_DOCUMENT_HANDLING_CAPABILITIES "...
0x180064cb0  jmp     short loc_180064CFB
0x180064cb2  call    ?CopyPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@@Z; CWiaItem::CopyPropertyFrom(CWiaItem *,tagSTATPROPSTG &)
0x180064cb7  jmp     short loc_180064D12
0x180064cb9  mov     rdx, [rsi+40h]; struct CWiaItem *
0x180064cbd  lea     r8, [rsp+150h+pv+8]; struct tagSTATPROPSTG *
0x180064cc2  mov     rcx, rsi; this
0x180064cc5  call    ?CopyPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@@Z; CWiaItem::CopyPropertyFrom(CWiaItem *,tagSTATPROPSTG &)
0x180064cca  mov     edi, eax
0x180064ccc  test    eax, eax
0x180064cce  jns     short loc_180064D12
0x180064cd0  mov     edx, eax
0x180064cd2  lea     rcx, aC1PropertyCopy; "C1 property copy failed (0x%X)"
0x180064cd9  call    WiaTrace_TraceLog
0x180064cde  mov     rdx, rax; char *
0x180064ce1  mov     rcx, r13; char *
0x180064ce4  mov     rbx, rax
0x180064ce7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180064cec  mov     rcx, rbx; this
0x180064cef  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180064cf4  lea     rcx, aC1PropertyCopy; "C1 property copy failed (0x%X)"
0x180064cfb  mov     edx, edi
0x180064cfd  call    WiaTrace_Trace
0x180064d02  mov     r9d, r12d; int
0x180064d05  mov     [rsp+150h+lpMem], rax; lpMem
0x180064d0a  mov     r8, r13; int
0x180064d0d  call    WiaTrace_ProcessTrace_Ex
0x180064d12  mov     rcx, [rsp+150h+pv+8]; pv
0x180064d17  test    rcx, rcx
0x180064d1a  jz      short loc_180064D2B
0x180064d1c  call    cs:__imp_CoTaskMemFree
0x180064d22  mov     [rsp+150h+pv+8], 0
0x180064d2b  test    edi, edi
0x180064d2d  js      short loc_180064D41
0x180064d2f  mov     rcx, [rsp+150h+pv]
0x180064d34  mov     dword ptr [rsp+150h+var_110], 0
0x180064d3c  jmp     loc_180064BD3
0x180064d41  mov     rcx, [rsp+150h+pv]
0x180064d46  test    rcx, rcx
0x180064d49  jz      short loc_180064D60
0x180064d4b  mov     rax, [rcx]
0x180064d4e  mov     rax, [rax+10h]
0x180064d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d57  mov     [rsp+150h+pv], 0
0x180064d60  test    edi, edi
0x180064d62  js      loc_180064F81
0x180064d68  lea     rcx, [rsi+8]
0x180064d6c  mov     edx, r12d
0x180064d6f  mov     rax, [rcx]
0x180064d72  mov     rax, [rax+48h]
0x180064d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d7b  movups  xmm6, xmmword ptr cs:WIA_CATEGORY_ROOT.Data1
0x180064d82  xor     eax, eax
0x180064d84  mov     [rbp+50h+var_C8], 0
0x180064d8b  xorps   xmm0, xmm0
0x180064d8e  mov     [rbp+50h+var_C0], rax
0x180064d92  movups  xmmword ptr [rsp+150h+pvar+0Ah], xmm0
0x180064d97  mov     word ptr [rsp+150h+pvar+8], ax
0x180064d9c  lea     ecx, [rax+10h]; cb
0x180064d9f  mov     qword ptr [rsp+150h+var_E0+8], rax
0x180064da4  mov     [rbp+50h+var_60], eax
0x180064da7  movups  [rbp+50h+var_5C], xmm0
0x180064dab  mov     [rbp+50h+var_3C], eax
0x180064dae  movups  [rbp+50h+var_4C], xmm0
0x180064db2  call    cs:__imp_CoTaskMemAlloc
0x180064db8  mov     r14, rax
0x180064dbb  test    rax, rax
0x180064dbe  jz      short loc_180064DC6
0x180064dc0  movdqu  xmmword ptr [rax], xmm6
0x180064dc4  jmp     short loc_180064E0F
0x180064dc6  mov     eax, 8007000Eh
0x180064dcb  lea     rcx, aCannotAllocate_3; "cannot allocate memory for item categor"...
0x180064dd2  mov     edx, eax
0x180064dd4  mov     edi, eax
0x180064dd6  call    WiaTrace_TraceLog
0x180064ddb  mov     rdx, rax; char *
0x180064dde  mov     rcx, r13; char *
0x180064de1  mov     rbx, rax
0x180064de4  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180064de9  mov     rcx, rbx; this
0x180064dec  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180064df1  mov     edx, edi
0x180064df3  lea     rcx, aCannotAllocate_3; "cannot allocate memory for item categor"...
0x180064dfa  call    WiaTrace_Trace
0x180064dff  mov     r9d, r12d; int
0x180064e02  mov     [rsp+150h+lpMem], rax; lpMem
0x180064e07  mov     r8, r13; int
0x180064e0a  call    WiaTrace_ProcessTrace_Ex
0x180064e0f  xor     eax, eax
0x180064e11  mov     [rbp+50h+var_C8], r12d
0x180064e15  mov     qword ptr [rsp+150h+var_E0+8], rax
0x180064e1a  mov     eax, 48h ; 'H'
0x180064e1f  mov     [rbp+50h+var_60], 9
0x180064e26  xorps   xmm0, xmm0
0x180064e29  mov     word ptr [rbp+50h+var_5C], ax
0x180064e2d  movups  xmmword ptr [rsp+150h+pvar+8], xmm0
0x180064e32  mov     qword ptr [rsp+150h+var_E0], r14
0x180064e37  mov     r14d, 101Dh
0x180064e3d  mov     dword ptr [rbp+50h+var_C0], r14d
0x180064e41  mov     word ptr [rsp+150h+pvar+8], ax
0x180064e46  test    edi, edi
0x180064e48  js      loc_180064F06
0x180064e4e  lea     r9, [rbp+50h+var_60]
0x180064e52  mov     edx, r12d
0x180064e55  lea     r8, [rbp+50h+var_C8]
0x180064e59  mov     rcx, rsi; this
0x180064e5c  call    wiasSetItemPropAttribs
0x180064e61  mov     edi, eax
0x180064e63  test    eax, eax
0x180064e65  jns     short loc_180064E94
0x180064e67  mov     edx, eax
0x180064e69  lea     rcx, aCallToWiasseti_4; "Call to wiasSetItemPropAttribs(WIA_IPA_"...
0x180064e70  call    WiaTrace_TraceLog
0x180064e75  mov     rdx, rax; char *
0x180064e78  mov     rcx, r13; char *
0x180064e7b  mov     rbx, rax
0x180064e7e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180064e83  mov     rcx, rbx; this
0x180064e86  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180064e8b  lea     rcx, aCallToWiasseti_4; "Call to wiasSetItemPropAttribs(WIA_IPA_"...
0x180064e92  jmp     short loc_180064EEF
0x180064e94  mov     rax, [rsi+0D8h]
0x180064e9b  lea     r9, [rsp+150h+pvar+8]
0x180064ea0  lea     r8, [rbp+50h+var_C8]
0x180064ea4  mov     dword ptr [rsp+150h+lpMem], 1002h
0x180064eac  mov     edx, r12d
0x180064eaf  mov     rcx, [rax]
0x180064eb2  mov     rax, [rcx]
0x180064eb5  mov     rax, [rax+20h]
0x180064eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ebe  mov     edi, eax
0x180064ec0  test    eax, eax
0x180064ec2  jns     short loc_180064F06
0x180064ec4  mov     edx, eax
0x180064ec6  lea     rcx, aCallToWritemul_2; "Call to WriteMultiple(WIA_IPA_ITEM_CATE"...
0x180064ecd  call    WiaTrace_TraceLog
0x180064ed2  mov     rdx, rax; char *
0x180064ed5  mov     rcx, r13; char *
0x180064ed8  mov     rbx, rax
0x180064edb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180064ee0  mov     rcx, rbx; this
0x180064ee3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180064ee8  lea     rcx, aCallToWritemul_2; "Call to WriteMultiple(WIA_IPA_ITEM_CATE"...
0x180064eef  mov     edx, edi
0x180064ef1  call    WiaTrace_Trace
0x180064ef6  mov     r9d, r12d; int
0x180064ef9  mov     [rsp+150h+lpMem], rax; lpMem
0x180064efe  mov     r8, r13; int
0x180064f01  call    WiaTrace_ProcessTrace_Ex
0x180064f06  lea     rcx, [rsp+150h+pvar+8]; pvar
0x180064f0b  call    cs:__imp_PropVariantClear
0x180064f11  test    edi, edi
0x180064f13  js      short loc_180064F81
0x180064f15  lea     rax, aItemCategory; "Item Category"
0x180064f1c  mov     dword ptr [rsp+150h+pvar], r14d
0x180064f21  lea     r9, [rbp+50h+var_B8]; unsigned __int16 **
0x180064f25  mov     [rbp+50h+var_B8], rax
0x180064f29  lea     r8, [rsp+150h+pvar]; unsigned int *
0x180064f2e  mov     edx, r12d; int
0x180064f31  mov     rcx, rsi; this
0x180064f34  call    wiasSetItemPropNames
0x180064f39  mov     edi, eax
0x180064f3b  test    eax, eax
0x180064f3d  jns     short loc_180064F81
0x180064f3f  mov     edx, eax
0x180064f41  lea     rcx, aCallToWiasseti_3; "Call to wiasSetItemPropNames(WIA_IPA_IT"...
0x180064f48  call    WiaTrace_TraceLog
  ... truncated ...
```
