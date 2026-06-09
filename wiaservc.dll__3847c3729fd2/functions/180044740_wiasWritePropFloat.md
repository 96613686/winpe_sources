# wiasWritePropFloat

- ea: `0x180044740`
- end: `0x180044a13`
- name: `wiasWritePropFloat`
- size: `723`
- prototype: `__int64 __fastcall(CWiaItem *this, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800189cc`
- `0x180018ad8`
- `0x18001f614`
- `0x180026f30`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180044740`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1800449e6`
- `ole32!PropVariantClear` at `0x1800449e6`

## string_xrefs

- `0x180044760`: `::wiasWritePropFloat`
- `0x180044772`: `wiasWritePropFloat`
- `0x180044798`: `wiasWritePropFloat, invalid pItem`
- `0x1800447ba`: `wiasWritePropFloat, invalid pItem`
- `0x180044809`: `wiasWritePropFloat failed, GetItemPropStreams item failed (0x%X)`
- `0x18004482d`: `wiasWritePropFloat failed, GetItemPropStreams item failed (0x%X)`
- `0x18004490b`: `wiasWritePropFloat failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x180044932`: `wiasWritePropFloat failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x180044956`: `wiasWritePropFloat failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x18004497a`: `wiasWritePropFloat failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x1800449c1`: `wiasWritePropFloat (A-AIT)`

## pseudocode

```c
__int64 __fastcall wiasWritePropFloat(struct IWiaItem *this, PROPID a2, float a3)
{
  struct tagWiaTraceData_Type *v5; // rax
  char *v6; // rdx
  unsigned int v7; // r8d
  int ItemPropStreams; // edi
  char *v9; // rbx
  void *v10; // rdx
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  char *v14; // rbx
  void *v15; // rdx
  char *v16; // rdx
  struct CWiaItem *v17; // rcx
  int RelatedAAITItem; // eax
  int v19; // eax
  struct IPropertyStorage *v20; // r14
  char *v21; // rbx
  void *v22; // rdx
  void **v23; // rax
  void *v24; // rdx
  __int64 v25; // rcx
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  unsigned int lpMem; // [rsp+28h] [rbp-69h]
  struct tagPROPSPEC v33; // [rsp+38h] [rbp-59h] BYREF
  struct IPropertyStorage *v34; // [rsp+48h] [rbp-49h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-41h] BYREF
  __int64 v36; // [rsp+60h] [rbp-31h]
  _BYTE v37[96]; // [rsp+68h] [rbp-29h] BYREF
  struct IPropertyStorage *v38; // [rsp+F8h] [rbp+67h] BYREF
  struct CWiaItem *v39; // [rsp+110h] [rbp+7Fh] BYREF

  v5 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasWritePropFloat");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v37, v6, v7, "wiasWritePropFloat", lpMem, v5);
  ItemPropStreams = ValidateWiaItem(this);
  if ( ItemPropStreams >= 0 )
  {
    v38 = 0;
    ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, &v38, 0, 0, 0);
    if ( ItemPropStreams < 0 )
    {
      v14 = (char *)WiaTrace_TraceLog("wiasWritePropFloat failed, GetItemPropStreams item failed (0x%X)");
      WriteDbgTraceErrorWI("wiasWritePropFloat", v14);
      WiaTrcLib::Free((WiaTrcLib *)v14, v15);
      v11 = (void **)WiaTrace_Trace("wiasWritePropFloat failed, GetItemPropStreams item failed (0x%X)", ItemPropStreams);
      goto LABEL_3;
    }
    v36 = 0;
    v33 = 0;
    v33.ulKind = 1;
    *(_OWORD *)pvar = 0;
    v33.propid = a2;
    *(float *)&pvar[1] = a3;
    LOWORD(pvar[0]) = 4;
    ItemPropStreams = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, PROPVARIANT *, int))v38->lpVtbl->WriteMultiple)(
                        v38,
                        1,
                        &v33,
                        pvar,
                        2);
    if ( ItemPropStreams < 0 )
    {
      v16 = "wiasWritePropFloat";
LABEL_19:
      ReportReadWriteMultipleError(ItemPropStreams, v16, 0, 0, 1u, &v33);
      goto LABEL_20;
    }
    if ( !(unsigned int)CWiaItem::IsCompatMode((CWiaItem *)this) )
    {
LABEL_20:
      PropVariantClear(pvar);
      goto LABEL_21;
    }
    v39 = 0;
    v34 = 0;
    LODWORD(v38) = 0;
    RelatedAAITItem = _FindRelatedAAITItem(v17, a2, &v39, (unsigned int *)&v38);
    ItemPropStreams = RelatedAAITItem;
    if ( RelatedAAITItem == 1 )
    {
      ItemPropStreams = 0;
      goto LABEL_20;
    }
    if ( RelatedAAITItem )
      goto LABEL_20;
    v19 = CWiaItem::GetItemPropStreams(v39, &v34, 0, 0, 0);
    v20 = v34;
    ItemPropStreams = v19;
    if ( v34 )
    {
      if ( v19 >= 0 )
      {
LABEL_17:
        ItemPropStreams = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, PROPVARIANT *, int))v20->lpVtbl->WriteMultiple)(
                            v20,
                            1,
                            &v33,
                            pvar,
                            2);
        if ( ItemPropStreams < 0 )
        {
          v16 = "wiasWritePropFloat (A-AIT)";
          goto LABEL_19;
        }
        goto LABEL_20;
      }
    }
    else if ( v19 >= 0 )
    {
      ItemPropStreams = -2147467261;
      v21 = (char *)WiaTrace_TraceLog("wiasWritePropFloat failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
      WriteDbgTraceErrorWI("wiasWritePropFloat", v21);
      WiaTrcLib::Free((WiaTrcLib *)v21, v22);
      v23 = (void **)WiaTrace_Trace("wiasWritePropFloat failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
      WiaTrace_ProcessTrace_Ex(v25, v24, (void *)"wiasWritePropFloat", 1, v23);
    }
    v26 = (char *)WiaTrace_TraceLog("wiasWritePropFloat failed, GetItemPropStreams for A-AIT item failed (0x%X)");
    WriteDbgTraceErrorWI("wiasWritePropFloat", v26);
    WiaTrcLib::Free((WiaTrcLib *)v26, v27);
    v28 = (void **)WiaTrace_Trace(
                     "wiasWritePropFloat failed, GetItemPropStreams for A-AIT item failed (0x%X)",
                     ItemPropStreams);
    WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"wiasWritePropFloat", 1, v28);
    if ( ItemPropStreams < 0 )
      goto LABEL_20;
    goto LABEL_17;
  }
  v9 = (char *)WiaTrace_TraceLog("wiasWritePropFloat, invalid pItem");
  WriteDbgTraceErrorWI("wiasWritePropFloat", v9);
  WiaTrcLib::Free((WiaTrcLib *)v9, v10);
  v11 = (void **)WiaTrace_Trace("wiasWritePropFloat, invalid pItem");
LABEL_3:
  WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"wiasWritePropFloat", 1, v11);
LABEL_21:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v37);
  return (unsigned int)ItemPropStreams;
}

```

## disassembly

```asm
0x180044740  mov     rax, rsp
0x180044743  mov     [rax+10h], rbx
0x180044747  push    rbp
0x180044748  push    rsi
0x180044749  push    rdi
0x18004474a  push    r12
0x18004474c  push    r14
0x18004474e  lea     rbp, [rax-5Fh]
0x180044752  sub     rsp, 0C0h
0x180044759  mov     rbx, rcx
0x18004475c  movaps  xmmword ptr [rax-38h], xmm6
0x180044760  lea     rcx, aWiaswritepropf_6; "::wiasWritePropFloat"
0x180044767  movaps  xmm6, xmm2
0x18004476a  mov     r14d, edx
0x18004476d  call    WiaTrace_Trace
0x180044772  lea     r12, aWiaswritepropf_2; "wiasWritePropFloat"
0x180044779  mov     [rsp+0E0h+var_B8], rax; struct tagWiaTraceData_Type *
0x18004477e  mov     r9, r12; char *
0x180044781  lea     rcx, [rbp+57h+var_80]; this
0x180044785  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18004478a  mov     rcx, rbx; struct IWiaItem *
0x18004478d  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180044792  mov     edi, eax
0x180044794  test    eax, eax
0x180044796  jns     short loc_1800447DE
0x180044798  lea     rcx, aWiaswritepropf_0; "wiasWritePropFloat, invalid pItem"
0x18004479f  call    WiaTrace_TraceLog
0x1800447a4  mov     rdx, rax; char *
0x1800447a7  mov     rcx, r12; char *
0x1800447aa  mov     rbx, rax
0x1800447ad  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800447b2  mov     rcx, rbx; this
0x1800447b5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800447ba  lea     rcx, aWiaswritepropf_0; "wiasWritePropFloat, invalid pItem"
0x1800447c1  call    WiaTrace_Trace
0x1800447c6  mov     r9d, 1; int
0x1800447cc  mov     [rsp+0E0h+lpMem], rax; lpMem
0x1800447d1  mov     r8, r12; int
0x1800447d4  call    WiaTrace_ProcessTrace_Ex
0x1800447d9  jmp     loc_1800449EC
0x1800447de  xor     r9d, r9d; struct IPropertyStorage **
0x1800447e1  mov     [rbp+57h+arg_0], 0
0x1800447e9  xor     r8d, r8d; struct IPropertyStorage **
0x1800447ec  mov     [rsp+0E0h+lpMem], 0; struct IPropertyStorage **
0x1800447f5  lea     rdx, [rbp+57h+arg_0]; struct IPropertyStorage **
0x1800447f9  mov     rcx, rbx; this
0x1800447fc  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x180044801  mov     edi, eax
0x180044803  test    eax, eax
0x180044805  jns     short loc_18004483B
0x180044807  mov     edx, eax
0x180044809  lea     rcx, aWiaswritepropf_1; "wiasWritePropFloat failed, GetItemPropS"...
0x180044810  call    WiaTrace_TraceLog
0x180044815  mov     rdx, rax; char *
0x180044818  mov     rcx, r12; char *
0x18004481b  mov     rbx, rax
0x18004481e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044823  mov     rcx, rbx; this
0x180044826  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004482b  mov     edx, edi
0x18004482d  lea     rcx, aWiaswritepropf_1; "wiasWritePropFloat failed, GetItemPropS"...
0x180044834  call    WiaTrace_Trace
0x180044839  jmp     short loc_1800447C6
0x18004483b  mov     rcx, [rbp+57h+arg_0]
0x18004483f  lea     r9, [rbp+57h+pvar]
0x180044843  xor     eax, eax
0x180044845  mov     dword ptr [rsp+0E0h+lpMem], 2
0x18004484d  mov     [rbp+57h+var_88], rax
0x180044851  lea     r8, [rbp+57h+var_B0]
0x180044855  mov     esi, 1
0x18004485a  xorps   xmm0, xmm0
0x18004485d  movups  xmmword ptr [rbp+57h+var_B0.ulKind], xmm0
0x180044861  mov     [rbp+57h+var_B0.ulKind], esi
0x180044864  mov     edx, esi
0x180044866  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18004486a  lea     eax, [rsi+3]
0x18004486d  mov     dword ptr [rbp+57h+var_B0.8], r14d
0x180044871  movss   dword ptr [rbp+57h+pvar+8], xmm6
0x180044876  mov     word ptr [rbp+57h+pvar], ax
0x18004487a  mov     rax, [rcx]
0x18004487d  mov     rax, [rax+20h]
0x180044881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044886  mov     edi, eax
0x180044888  test    eax, eax
0x18004488a  jns     short loc_180044894
0x18004488c  mov     rdx, r12
0x18004488f  jmp     loc_1800449C8
0x180044894  mov     rcx, rbx; this
0x180044897  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x18004489c  test    eax, eax
0x18004489e  jz      loc_1800449E2
0x1800448a4  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800448a8  mov     [rbp+57h+arg_18], 0
0x1800448b0  lea     r8, [rbp+57h+arg_18]; struct CWiaItem **
0x1800448b4  mov     [rbp+57h+var_A0], 0
0x1800448bc  mov     edx, r14d; unsigned int
0x1800448bf  mov     dword ptr [rbp+57h+arg_0], 0
0x1800448c6  call    ?_FindRelatedAAITItem@@YAJPEAVCWiaItem@@KPEAPEAV1@PEAK@Z; _FindRelatedAAITItem(CWiaItem *,ulong,CWiaItem * *,ulong *)
0x1800448cb  mov     edi, eax
0x1800448cd  cmp     eax, esi
0x1800448cf  jnz     short loc_1800448D8
0x1800448d1  xor     edi, edi
0x1800448d3  jmp     loc_1800449E2
0x1800448d8  test    eax, eax
0x1800448da  jnz     loc_1800449E2
0x1800448e0  mov     rcx, [rbp+57h+arg_18]; this
0x1800448e4  lea     rdx, [rbp+57h+var_A0]; struct IPropertyStorage **
0x1800448e8  xor     r9d, r9d; struct IPropertyStorage **
0x1800448eb  mov     [rsp+0E0h+lpMem], 0; struct IPropertyStorage **
0x1800448f4  xor     r8d, r8d; struct IPropertyStorage **
0x1800448f7  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x1800448fc  mov     r14, [rbp+57h+var_A0]
0x180044900  mov     edi, eax
0x180044902  test    r14, r14
0x180044905  jnz     short loc_180044950
0x180044907  test    eax, eax
0x180044909  js      short loc_180044954
0x18004490b  lea     rcx, aWiaswritepropf_5; "wiasWritePropFloat failed, GetItemPropS"...
0x180044912  mov     edi, 80004003h
0x180044917  call    WiaTrace_TraceLog
0x18004491c  mov     rdx, rax; char *
0x18004491f  mov     rcx, r12; char *
0x180044922  mov     rbx, rax
0x180044925  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004492a  mov     rcx, rbx; this
0x18004492d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044932  lea     rcx, aWiaswritepropf_5; "wiasWritePropFloat failed, GetItemPropS"...
0x180044939  call    WiaTrace_Trace
0x18004493e  mov     r9d, esi; int
0x180044941  mov     [rsp+0E0h+lpMem], rax; lpMem
0x180044946  mov     r8, r12; int
0x180044949  call    WiaTrace_ProcessTrace_Ex
0x18004494e  jmp     short loc_180044954
0x180044950  test    eax, eax
0x180044952  jns     short loc_18004499A
0x180044954  mov     edx, edi
0x180044956  lea     rcx, aWiaswritepropf_3; "wiasWritePropFloat failed, GetItemPropS"...
0x18004495d  call    WiaTrace_TraceLog
0x180044962  mov     rdx, rax; char *
0x180044965  mov     rcx, r12; char *
0x180044968  mov     rbx, rax
0x18004496b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044970  mov     rcx, rbx; this
0x180044973  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044978  mov     edx, edi
0x18004497a  lea     rcx, aWiaswritepropf_3; "wiasWritePropFloat failed, GetItemPropS"...
0x180044981  call    WiaTrace_Trace
0x180044986  mov     r9d, esi; int
0x180044989  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18004498e  mov     r8, r12; int
0x180044991  call    WiaTrace_ProcessTrace_Ex
0x180044996  test    edi, edi
0x180044998  js      short loc_1800449E2
0x18004499a  mov     rax, [r14]
0x18004499d  lea     r9, [rbp+57h+pvar]
0x1800449a1  lea     r8, [rbp+57h+var_B0]
0x1800449a5  mov     dword ptr [rsp+0E0h+lpMem], 2
0x1800449ad  mov     edx, esi
0x1800449af  mov     rcx, r14
0x1800449b2  mov     rax, [rax+20h]
0x1800449b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800449bb  mov     edi, eax
0x1800449bd  test    eax, eax
0x1800449bf  jns     short loc_1800449E2
0x1800449c1  lea     rdx, aWiaswritepropf_4; "wiasWritePropFloat (A-AIT)"
0x1800449c8  lea     rax, [rbp+57h+var_B0]
0x1800449cc  xor     r9d, r9d; int
0x1800449cf  mov     [rsp+0E0h+var_B8], rax; struct tagPROPSPEC *
0x1800449d4  xor     r8d, r8d; char *
0x1800449d7  mov     ecx, edi; int
0x1800449d9  mov     dword ptr [rsp+0E0h+lpMem], esi; unsigned int
0x1800449dd  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x1800449e2  lea     rcx, [rbp+57h+pvar]; pvar
0x1800449e6  call    cs:__imp_PropVariantClear
0x1800449ec  lea     rcx, [rbp+57h+var_80]; this
0x1800449f0  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800449f5  lea     r11, [rsp+0E0h+var_20]
0x1800449fd  mov     eax, edi
0x1800449ff  mov     rbx, [r11+38h]
0x180044a03  movaps  xmm6, xmmword ptr [r11-10h]
0x180044a08  mov     rsp, r11
0x180044a0b  pop     r14
0x180044a0d  pop     r12
0x180044a0f  pop     rdi
0x180044a10  pop     rsi
0x180044a11  pop     rbp
0x180044a12  retn
```
