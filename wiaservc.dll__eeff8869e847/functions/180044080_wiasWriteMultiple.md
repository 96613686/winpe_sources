# wiasWriteMultiple

- ea: `0x180044080`
- end: `0x1800443eb`
- name: `wiasWriteMultiple`
- size: `875`
- prototype: `__int64 __fastcall(CWiaItem *this, int, struct tagPROPSPEC *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800189cc`
- `0x180018ad8`
- `0x18001e3dc`
- `0x18001f614`
- `0x180026f30`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180044080`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180044393`
- `KERNEL32!LocalFree` at `0x180044393`

## string_xrefs

- `0x1800440ab`: `::wiasWriteMultiple`
- `0x1800440bd`: `wiasWriteMultiple`
- `0x180044323`: `wiasWriteMultiple`
- `0x18004435c`: `wiasWriteMultiple`
- `0x18004439d`: `wiasWriteMultiple`
- `0x1800440e6`: `wiasWriteMultiple, invalid pItem`
- `0x180044108`: `wiasWriteMultiple, invalid pItem`
- `0x180044130`: `wiasWriteMultiple, invalid ps pointer`
- `0x180044152`: `wiasWriteMultiple, invalid ps pointer`
- `0x180044180`: `wiasWriteMultiple, invalid pv pointer`
- `0x1800441a2`: `wiasWriteMultiple, invalid pv pointer`

## pseudocode

```c
__int64 __fastcall wiasWriteMultiple(struct IWiaItem *this, unsigned int a2, struct tagPROPSPEC *a3, __int64 a4)
{
  char ***v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r12
  int v12; // edi
  char *v13; // rbx
  void *v14; // rdx
  void **v15; // rax
  void *v16; // rdx
  __int64 v17; // rcx
  char *v18; // rbx
  void *v19; // rdx
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  char *v23; // rbx
  void *v24; // rdx
  int ItemPropStreams; // eax
  CWiaPropStg *lpVtbl; // rcx
  struct tagPROPSPEC *v27; // rsi
  unsigned int v28; // ebx
  __int64 v29; // r14
  int RelatedAAITItem; // eax
  char *v31; // rbx
  void *v32; // rdx
  void **v33; // rax
  void *v34; // rdx
  __int64 v35; // rcx
  unsigned int lpMem; // [rsp+28h] [rbp-69h]
  unsigned int v38; // [rsp+38h] [rbp-59h]
  int v39; // [rsp+3Ch] [rbp-55h]
  struct CWiaItem *v40; // [rsp+40h] [rbp-51h] BYREF
  struct IPropertyStorage *v41; // [rsp+48h] [rbp-49h] BYREF
  __int64 v42; // [rsp+50h] [rbp-41h]
  __int128 v43; // [rsp+58h] [rbp-39h] BYREF
  _BYTE v44[128]; // [rsp+68h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+F8h] [rbp+67h] BYREF
  struct tagPROPSPEC *v46; // [rsp+108h] [rbp+77h]
  __int64 v47; // [rsp+110h] [rbp+7Fh]

  v47 = a4;
  v46 = a3;
  v8 = (char ***)WiaTrace_Trace("::wiasWriteMultiple");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v44, v9, v10, (char **)"wiasWriteMultiple", lpMem, v8);
  v11 = 0;
  v12 = ValidateWiaItem(this);
  if ( v12 < 0 )
  {
    v13 = (char *)WiaTrace_TraceLog("wiasWriteMultiple, invalid pItem");
    WriteDbgTraceErrorWI("wiasWriteMultiple", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v15 = (void **)WiaTrace_Trace("wiasWriteMultiple, invalid pItem");
    WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"wiasWriteMultiple", 1, v15);
    goto LABEL_32;
  }
  if ( !a3 )
  {
    v18 = (char *)WiaTrace_TraceLog("wiasWriteMultiple, invalid ps pointer");
    WriteDbgTraceErrorWI("wiasWriteMultiple", v18);
    WiaTrcLib::Free((WiaTrcLib *)v18, v19);
    v20 = (void **)WiaTrace_Trace("wiasWriteMultiple, invalid ps pointer");
LABEL_5:
    WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"wiasWriteMultiple", 1, v20);
    v12 = -2147467261;
    goto LABEL_32;
  }
  if ( !a4 )
  {
    v23 = (char *)WiaTrace_TraceLog("wiasWriteMultiple, invalid pv pointer");
    WriteDbgTraceErrorWI("wiasWriteMultiple", v23);
    WiaTrcLib::Free((WiaTrcLib *)v23, v24);
    v20 = (void **)WiaTrace_Trace("wiasWriteMultiple, invalid pv pointer");
    goto LABEL_5;
  }
  hMem = 0;
  ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, (struct IPropertyStorage **)&hMem, 0, 0, 0);
  if ( ItemPropStreams < 0 )
  {
    v12 = ItemPropStreams;
    goto LABEL_32;
  }
  if ( !hMem )
  {
    v12 = -2147467259;
    goto LABEL_31;
  }
  v12 = (*(__int64 (__fastcall **)(HLOCAL, _QWORD, struct tagPROPSPEC *, __int64, int))(*(_QWORD *)hMem + 32LL))(
          hMem,
          a2,
          a3,
          a4,
          2);
  if ( v12 < 0 )
    goto LABEL_31;
  if ( !(unsigned int)CWiaItem::IsCompatMode((CWiaItem *)this) )
    goto LABEL_32;
  lpVtbl = (CWiaPropStg *)this[27].lpVtbl;
  v40 = 0;
  hMem = 0;
  v12 = CWiaPropStg::NamesToPropIDs(lpVtbl, a2, a3, (struct tagPROPSPEC **)&hMem);
  if ( v12 < 0 )
  {
LABEL_31:
    ReportReadWriteMultipleError(v12, "wiasWriteMultiple", 0, 0, a2, a3);
    goto LABEL_32;
  }
  v27 = (struct tagPROPSPEC *)hMem;
  v39 = 1;
  if ( !hMem )
  {
    v27 = a3;
    v39 = 0;
  }
  v28 = 0;
  v38 = 0;
  if ( a2 )
  {
    v29 = v47;
    while ( 1 )
    {
      LODWORD(hMem) = 0;
      v42 = 16 * v11;
      RelatedAAITItem = _FindRelatedAAITItem((struct CWiaItem *)this, v27[v11].propid, &v40, (unsigned int *)&hMem);
      v12 = RelatedAAITItem;
      if ( RelatedAAITItem == 1 )
        goto LABEL_24;
      if ( !RelatedAAITItem )
      {
        v41 = 0;
        v12 = CWiaItem::GetItemPropStreams(v40, &v41, 0, 0, 0);
        if ( v12 < 0 )
          break;
        v43 = 0;
        DWORD2(v43) = (_DWORD)hMem;
        LODWORD(v43) = 1;
        v12 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, __int128 *, __int64, int))v41->lpVtbl->WriteMultiple)(
                v41,
                1,
                &v43,
                v29 + 24 * v11,
                2);
      }
      if ( v12 < 0 )
        break;
LABEL_25:
      ++v28;
      ++v11;
      v38 = v28;
      if ( v28 >= a2 )
        goto LABEL_26;
    }
    v31 = (char *)WiaTrace_TraceLog("Property translation failed for property: %d (hr = 0x%X)");
    WriteDbgTraceErrorWI("wiasWriteMultiple", v31);
    WiaTrcLib::Free((WiaTrcLib *)v31, v32);
    v33 = (void **)WiaTrace_Trace(
                     "Property translation failed for property: %d (hr = 0x%X)",
                     v27[(unsigned __int64)v42 / 0x10].propid,
                     v12);
    WiaTrace_ProcessTrace_Ex(v35, v34, (void *)"wiasWriteMultiple", 1, v33);
    v28 = v38;
LABEL_24:
    v12 = 0;
    goto LABEL_25;
  }
LABEL_26:
  if ( v27 && v39 )
    LocalFree(v27);
LABEL_32:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v44);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180044080  mov     rax, rsp
0x180044083  mov     [rax+10h], rbx
0x180044087  mov     [rax+20h], r9
0x18004408b  mov     [rax+18h], r8
0x18004408f  push    rbp
0x180044090  push    rsi
0x180044091  push    rdi
0x180044092  push    r12
0x180044094  push    r13
0x180044096  push    r14
0x180044098  push    r15
0x18004409a  lea     rbp, [rax-5Fh]
0x18004409e  sub     rsp, 0B0h
0x1800440a5  mov     r13, rcx
0x1800440a8  mov     rbx, r9
0x1800440ab  lea     rcx, aWiaswritemulti_1; "::wiasWriteMultiple"
0x1800440b2  mov     r14, r8
0x1800440b5  mov     r15d, edx
0x1800440b8  call    WiaTrace_Trace
0x1800440bd  lea     rsi, aWiaswritemulti_0; "wiasWriteMultiple"
0x1800440c4  mov     qword ptr [rsp+0E0h+lpMem+8], rax; struct tagWiaTraceData_Type *
0x1800440c9  mov     r9, rsi; char *
0x1800440cc  lea     rcx, [rbp+57h+var_80]; this
0x1800440d0  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800440d5  mov     rcx, r13; struct IWiaItem *
0x1800440d8  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x1800440dd  xor     r12d, r12d
0x1800440e0  mov     edi, eax
0x1800440e2  test    eax, eax
0x1800440e4  jns     short loc_18004412B
0x1800440e6  lea     rcx, aWiaswritemulti_5; "wiasWriteMultiple, invalid pItem"
0x1800440ed  call    WiaTrace_TraceLog
0x1800440f2  mov     rdx, rax; char *
0x1800440f5  mov     rcx, rsi; char *
0x1800440f8  mov     rbx, rax
0x1800440fb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044100  mov     rcx, rbx; this
0x180044103  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044108  lea     rcx, aWiaswritemulti_5; "wiasWriteMultiple, invalid pItem"
0x18004410f  call    WiaTrace_Trace
0x180044114  lea     r9d, [r12+1]; int
0x180044119  mov     qword ptr [rsp+0E0h+lpMem], rax; lpMem
0x18004411e  mov     r8, rsi; int
0x180044121  call    WiaTrace_ProcessTrace_Ex
0x180044126  jmp     loc_1800443C5
0x18004412b  test    r14, r14
0x18004412e  jnz     short loc_18004417B
0x180044130  lea     rcx, aWiaswritemulti_3; "wiasWriteMultiple, invalid ps pointer"
0x180044137  call    WiaTrace_TraceLog
0x18004413c  mov     rdx, rax; char *
0x18004413f  mov     rcx, rsi; char *
0x180044142  mov     rbx, rax
0x180044145  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004414a  mov     rcx, rbx; this
0x18004414d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044152  lea     rcx, aWiaswritemulti_3; "wiasWriteMultiple, invalid ps pointer"
0x180044159  call    WiaTrace_Trace
0x18004415e  mov     r9d, 1; int
0x180044164  mov     qword ptr [rsp+0E0h+lpMem], rax; lpMem
0x180044169  mov     r8, rsi; int
0x18004416c  call    WiaTrace_ProcessTrace_Ex
0x180044171  mov     edi, 80004003h
0x180044176  jmp     loc_1800443C5
0x18004417b  test    rbx, rbx
0x18004417e  jnz     short loc_1800441AB
0x180044180  lea     rcx, aWiaswritemulti_4; "wiasWriteMultiple, invalid pv pointer"
0x180044187  call    WiaTrace_TraceLog
0x18004418c  mov     rdx, rax; char *
0x18004418f  mov     rcx, rsi; char *
0x180044192  mov     rbx, rax
0x180044195  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004419a  mov     rcx, rbx; this
0x18004419d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800441a2  lea     rcx, aWiaswritemulti_4; "wiasWriteMultiple, invalid pv pointer"
0x1800441a9  jmp     short loc_180044159
0x1800441ab  xor     r9d, r9d; struct IPropertyStorage **
0x1800441ae  mov     [rbp+57h+hMem], r12
0x1800441b2  xor     r8d, r8d; struct IPropertyStorage **
0x1800441b5  mov     qword ptr [rsp+0E0h+lpMem], r12; struct IPropertyStorage **
0x1800441ba  lea     rdx, [rbp+57h+hMem]; struct IPropertyStorage **
0x1800441be  mov     rcx, r13; this
0x1800441c1  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x1800441c6  test    eax, eax
0x1800441c8  jns     short loc_1800441D1
0x1800441ca  mov     edi, eax
0x1800441cc  jmp     loc_1800443C5
0x1800441d1  mov     rcx, [rbp+57h+hMem]
0x1800441d5  test    rcx, rcx
0x1800441d8  jz      loc_1800443A6
0x1800441de  mov     rax, [rcx]
0x1800441e1  mov     r9, rbx
0x1800441e4  mov     r8, r14
0x1800441e7  mov     [rsp+0E0h+lpMem], 2
0x1800441ef  mov     edx, r15d
0x1800441f2  mov     rax, [rax+20h]
0x1800441f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441fb  mov     edi, eax
0x1800441fd  test    eax, eax
0x1800441ff  js      loc_1800443AB
0x180044205  mov     rcx, r13; this
0x180044208  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x18004420d  test    eax, eax
0x18004420f  jz      loc_1800443C5
0x180044215  mov     rcx, [r13+0D8h]; this
0x18004421c  lea     r9, [rbp+57h+hMem]; struct tagPROPSPEC **
0x180044220  mov     r8, r14; struct tagPROPSPEC *
0x180044223  mov     [rbp+57h+var_A8], r12
0x180044227  mov     edx, r15d; int
0x18004422a  mov     [rbp+57h+hMem], r12
0x18004422e  call    ?NamesToPropIDs@CWiaPropStg@@QEAAJJPEBUtagPROPSPEC@@PEAPEAU2@@Z; CWiaPropStg::NamesToPropIDs(long,tagPROPSPEC const *,tagPROPSPEC * *)
0x180044233  mov     edi, eax
0x180044235  test    eax, eax
0x180044237  js      loc_1800443AB
0x18004423d  mov     rsi, [rbp+57h+hMem]
0x180044241  mov     [rbp+57h+var_AC], 1
0x180044248  test    rsi, rsi
0x18004424b  jnz     short loc_180044254
0x18004424d  mov     rsi, r14
0x180044250  mov     [rbp+57h+var_AC], r12d
0x180044254  mov     ebx, r12d
0x180044257  mov     [rbp+57h+var_B0], ebx
0x18004425a  test    r15d, r15d
0x18004425d  jz      loc_180044385
0x180044263  mov     r14, [rbp+57h+arg_18]
0x180044267  mov     rax, r12
0x18004426a  mov     dword ptr [rbp+57h+hMem], 0
0x180044271  shl     rax, 4
0x180044275  lea     r9, [rbp+57h+hMem]; unsigned int *
0x180044279  lea     r8, [rbp+57h+var_A8]; struct CWiaItem **
0x18004427d  mov     [rbp+57h+var_98], rax
0x180044281  mov     rcx, r13; this
0x180044284  mov     edx, [rax+rsi+8]; unsigned int
0x180044288  call    ?_FindRelatedAAITItem@@YAJPEAVCWiaItem@@KPEAPEAV1@PEAK@Z; _FindRelatedAAITItem(CWiaItem *,ulong,CWiaItem * *,ulong *)
0x18004428d  mov     edi, eax
0x18004428f  cmp     eax, 1
0x180044292  jz      loc_18004436B
0x180044298  test    eax, eax
0x18004429a  jnz     short loc_180044305
0x18004429c  mov     rcx, [rbp+57h+var_A8]; this
0x1800442a0  lea     rdx, [rbp+57h+var_A0]; struct IPropertyStorage **
0x1800442a4  xor     r9d, r9d; struct IPropertyStorage **
0x1800442a7  mov     [rbp+57h+var_A0], 0
0x1800442af  xor     r8d, r8d; struct IPropertyStorage **
0x1800442b2  mov     qword ptr [rsp+0E0h+lpMem], 0; struct IPropertyStorage **
0x1800442bb  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x1800442c0  mov     edi, eax
0x1800442c2  test    eax, eax
0x1800442c4  js      short loc_180044309
0x1800442c6  mov     rcx, [rbp+57h+var_A0]
0x1800442ca  lea     r8, [rbp+57h+var_90]
0x1800442ce  mov     eax, dword ptr [rbp+57h+hMem]
0x1800442d1  xorps   xmm0, xmm0
0x1800442d4  movups  [rbp+57h+var_90], xmm0
0x1800442d8  mov     dword ptr [rbp+57h+var_90+8], eax
0x1800442db  lea     rax, [r12+r12*2]
0x1800442df  mov     dword ptr [rbp+57h+var_90], 1
0x1800442e6  lea     r9, [r14+rax*8]
0x1800442ea  mov     rdx, [rcx]
0x1800442ed  mov     [rsp+0E0h+lpMem], 2
0x1800442f5  mov     rax, [rdx+20h]
0x1800442f9  mov     edx, 1
0x1800442fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044303  mov     edi, eax
0x180044305  test    edi, edi
0x180044307  jns     short loc_18004436D
0x180044309  mov     rdx, [rbp+57h+var_98]
0x18004430d  lea     rcx, aPropertyTransl_0; "Property translation failed for propert"...
0x180044314  mov     r8d, edi
0x180044317  mov     edx, [rdx+rsi+8]
0x18004431b  call    WiaTrace_TraceLog
0x180044320  mov     rdx, rax; char *
0x180044323  lea     rcx, aWiaswritemulti_0; "wiasWriteMultiple"
0x18004432a  mov     rbx, rax
0x18004432d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044332  mov     rcx, rbx; this
0x180044335  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004433a  mov     rax, [rbp+57h+var_98]
0x18004433e  lea     rcx, aPropertyTransl_0; "Property translation failed for propert"...
0x180044345  mov     r8d, edi
0x180044348  mov     edx, [rax+rsi+8]
0x18004434c  call    WiaTrace_Trace
0x180044351  mov     r9d, 1; int
0x180044357  mov     qword ptr [rsp+0E0h+lpMem], rax; lpMem
0x18004435c  lea     r8, aWiaswritemulti_0; "wiasWriteMultiple"
0x180044363  call    WiaTrace_ProcessTrace_Ex
0x180044368  mov     ebx, [rbp+57h+var_B0]
0x18004436b  xor     edi, edi
0x18004436d  inc     ebx
0x18004436f  inc     r12
0x180044372  mov     [rbp+57h+var_B0], ebx
0x180044375  cmp     ebx, r15d
0x180044378  jb      loc_180044267
0x18004437e  mov     r14, [rbp+57h+arg_10]
0x180044382  xor     r12d, r12d
0x180044385  test    rsi, rsi
0x180044388  jz      short loc_180044399
0x18004438a  cmp     [rbp+57h+var_AC], r12d
0x18004438e  jz      short loc_180044399
0x180044390  mov     rcx, rsi; hMem
0x180044393  call    cs:__imp_LocalFree
0x180044399  test    edi, edi
0x18004439b  jns     short loc_1800443C5
0x18004439d  lea     rsi, aWiaswritemulti_0; "wiasWriteMultiple"
0x1800443a4  jmp     short loc_1800443AB
0x1800443a6  mov     edi, 80004005h
0x1800443ab  mov     qword ptr [rsp+0E0h+lpMem+8], r14; struct tagPROPSPEC *
0x1800443b0  xor     r9d, r9d; int
0x1800443b3  xor     r8d, r8d; char *
0x1800443b6  mov     [rsp+0E0h+lpMem], r15d; unsigned int
0x1800443bb  mov     rdx, rsi; char *
0x1800443be  mov     ecx, edi; int
0x1800443c0  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x1800443c5  lea     rcx, [rbp+57h+var_80]; this
0x1800443c9  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800443ce  mov     rbx, [rsp+0E0h+arg_8]
0x1800443d6  mov     eax, edi
0x1800443d8  add     rsp, 0B0h
0x1800443df  pop     r15
0x1800443e1  pop     r14
0x1800443e3  pop     r13
0x1800443e5  pop     r12
0x1800443e7  pop     rdi
0x1800443e8  pop     rsi
0x1800443e9  pop     rbp
0x1800443ea  retn
```
