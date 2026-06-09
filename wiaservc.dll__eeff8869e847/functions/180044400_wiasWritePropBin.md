# wiasWritePropBin

- ea: `0x180044400`
- end: `0x18004473a`
- name: `wiasWritePropBin`
- size: `826`
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
- `0x180044400`
- `0x180078010`

## string_xrefs

- `0x180044424`: `::wiasWritePropBin`
- `0x180044436`: `wiasWritePropBin`
- `0x1800444cb`: `wiasWritePropBin`
- `0x180044547`: `wiasWritePropBin`
- `0x1800445ac`: `wiasWritePropBin`
- `0x180044643`: `wiasWritePropBin`
- `0x18004466e`: `wiasWritePropBin`
- `0x180044691`: `wiasWritePropBin`
- `0x1800446be`: `wiasWritePropBin`
- `0x18004445c`: `wiasWritePropBin, invalid pItem`
- `0x18004447e`: `wiasWritePropBin, invalid pItem`
- `0x180044494`: `wiasWritePropBin, invalid pbVal pointer`
- `0x1800444b6`: `wiasWritePropBin, invalid pbVal pointer`
- `0x18004450c`: `wiasWritePropBin failed, GetItemPropStreams item failed (0x%X)`
- `0x180044530`: `wiasWritePropBin failed, GetItemPropStreams item failed (0x%X)`
- `0x18004462f`: `wiasWritePropBin failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x18004465a`: `wiasWritePropBin failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x180044682`: `wiasWritePropBin failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x1800446aa`: `wiasWritePropBin failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x1800446f2`: `wiasWritePropBin (A-AIT)`

## pseudocode

```c
__int64 __fastcall wiasWritePropBin(struct IWiaItem *this, PROPID a2, int a3, __int64 a4)
{
  char ***v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  int ItemPropStreams; // edi
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
  char *v22; // rbx
  void *v23; // rdx
  char *v24; // rdx
  struct CWiaItem *v25; // rcx
  int RelatedAAITItem; // eax
  int v27; // eax
  struct IPropertyStorage *v28; // r14
  char *v29; // rbx
  void *v30; // rdx
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx
  char *v34; // rbx
  void *v35; // rdx
  void **v36; // rax
  void *v37; // rdx
  __int64 v38; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-69h]
  struct tagPROPSPEC v41; // [rsp+30h] [rbp-59h] BYREF
  struct CWiaItem *v42; // [rsp+40h] [rbp-49h] BYREF
  struct IPropertyStorage *v43; // [rsp+48h] [rbp-41h] BYREF
  __int128 v44; // [rsp+50h] [rbp-39h] BYREF
  __int64 v45; // [rsp+60h] [rbp-29h]
  _BYTE v46[80]; // [rsp+70h] [rbp-19h] BYREF
  struct IPropertyStorage *v47; // [rsp+F0h] [rbp+67h] BYREF

  v8 = (char ***)WiaTrace_Trace("::wiasWritePropBin");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v46, v9, v10, (char **)"wiasWritePropBin", lpMem, v8);
  ItemPropStreams = ValidateWiaItem(this);
  if ( ItemPropStreams < 0 )
  {
    v12 = (char *)WiaTrace_TraceLog("wiasWritePropBin, invalid pItem");
    WriteDbgTraceErrorWI("wiasWritePropBin", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("wiasWritePropBin, invalid pItem");
LABEL_7:
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"wiasWritePropBin", 1, v14);
    goto LABEL_22;
  }
  if ( a4 )
  {
    v47 = 0;
    ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, &v47, 0, 0, 0);
    if ( ItemPropStreams < 0 )
    {
      v22 = (char *)WiaTrace_TraceLog("wiasWritePropBin failed, GetItemPropStreams item failed (0x%X)");
      WriteDbgTraceErrorWI("wiasWritePropBin", v22);
      WiaTrcLib::Free((WiaTrcLib *)v22, v23);
      v14 = (void **)WiaTrace_Trace("wiasWritePropBin failed, GetItemPropStreams item failed (0x%X)", ItemPropStreams);
      goto LABEL_7;
    }
    v45 = a4;
    v41 = 0;
    v41.ulKind = 1;
    v41.propid = a2;
    v44 = 0;
    LOWORD(v44) = 4113;
    DWORD2(v44) = a3;
    ItemPropStreams = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, __int128 *, int))v47->lpVtbl->WriteMultiple)(
                        v47,
                        1,
                        &v41,
                        &v44,
                        2);
    if ( ItemPropStreams < 0 )
    {
      v24 = "wiasWritePropBin";
      goto LABEL_21;
    }
    if ( !(unsigned int)CWiaItem::IsCompatMode((CWiaItem *)this) )
      goto LABEL_22;
    v42 = 0;
    v43 = 0;
    LODWORD(v47) = 0;
    RelatedAAITItem = _FindRelatedAAITItem(v25, a2, &v42, (unsigned int *)&v47);
    ItemPropStreams = RelatedAAITItem;
    if ( RelatedAAITItem == 1 )
    {
      ItemPropStreams = 0;
      goto LABEL_22;
    }
    if ( RelatedAAITItem )
      goto LABEL_22;
    v27 = CWiaItem::GetItemPropStreams(v42, &v43, 0, 0, 0);
    v28 = v43;
    ItemPropStreams = v27;
    if ( v43 )
    {
      if ( v27 >= 0 )
      {
LABEL_19:
        ItemPropStreams = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, __int128 *, int))v28->lpVtbl->WriteMultiple)(
                            v28,
                            1,
                            &v41,
                            &v44,
                            2);
        if ( ItemPropStreams >= 0 )
          goto LABEL_22;
        v24 = "wiasWritePropBin (A-AIT)";
LABEL_21:
        ReportReadWriteMultipleError(ItemPropStreams, v24, 0, 0, 1u, &v41);
        goto LABEL_22;
      }
    }
    else if ( v27 >= 0 )
    {
      ItemPropStreams = -2147467261;
      v29 = (char *)WiaTrace_TraceLog("wiasWritePropBin failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
      WriteDbgTraceErrorWI("wiasWritePropBin", v29);
      WiaTrcLib::Free((WiaTrcLib *)v29, v30);
      v31 = (void **)WiaTrace_Trace("wiasWritePropBin failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
      WiaTrace_ProcessTrace_Ex(v33, v32, (void *)"wiasWritePropBin", 1, v31);
    }
    v34 = (char *)WiaTrace_TraceLog("wiasWritePropBin failed, GetItemPropStreams for A-AIT item failed (0x%X)");
    WriteDbgTraceErrorWI("wiasWritePropBin", v34);
    WiaTrcLib::Free((WiaTrcLib *)v34, v35);
    v36 = (void **)WiaTrace_Trace(
                     "wiasWritePropBin failed, GetItemPropStreams for A-AIT item failed (0x%X)",
                     ItemPropStreams);
    WiaTrace_ProcessTrace_Ex(v38, v37, (void *)"wiasWritePropBin", 1, v36);
    if ( ItemPropStreams < 0 )
      goto LABEL_22;
    goto LABEL_19;
  }
  v17 = (char *)WiaTrace_TraceLog("wiasWritePropBin, invalid pbVal pointer");
  WriteDbgTraceErrorWI("wiasWritePropBin", v17);
  WiaTrcLib::Free((WiaTrcLib *)v17, v18);
  v19 = (void **)WiaTrace_Trace("wiasWritePropBin, invalid pbVal pointer");
  WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"wiasWritePropBin", 1, v19);
  ItemPropStreams = -2147467261;
LABEL_22:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v46);
  return (unsigned int)ItemPropStreams;
}

```

## disassembly

```asm
0x180044400  mov     [rsp-8+arg_8], rbx
0x180044405  mov     [rsp-8+arg_10], rsi
0x18004440a  push    rbp
0x18004440b  push    rdi
0x18004440c  push    r12
0x18004440e  push    r14
0x180044410  push    r15
0x180044412  lea     rbp, [rsp-37h]
0x180044417  sub     rsp, 0C0h
0x18004441e  mov     rbx, rcx
0x180044421  mov     r14, r9
0x180044424  lea     rcx, aWiaswritepropb_1; "::wiasWritePropBin"
0x18004442b  mov     r12d, r8d
0x18004442e  mov     r15d, edx
0x180044431  call    WiaTrace_Trace
0x180044436  lea     rsi, aWiaswritepropb_7; "wiasWritePropBin"
0x18004443d  mov     [rsp+0E0h+var_B8], rax; struct tagWiaTraceData_Type *
0x180044442  mov     r9, rsi; char *
0x180044445  lea     rcx, [rbp+57h+var_70]; this
0x180044449  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18004444e  mov     rcx, rbx; struct IWiaItem *
0x180044451  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180044456  mov     edi, eax
0x180044458  test    eax, eax
0x18004445a  jns     short loc_18004448F
0x18004445c  lea     rcx, aWiaswritepropb_0; "wiasWritePropBin, invalid pItem"
0x180044463  call    WiaTrace_TraceLog
0x180044468  mov     rdx, rax; char *
0x18004446b  mov     rcx, rsi; char *
0x18004446e  mov     rbx, rax
0x180044471  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044476  mov     rcx, rbx; this
0x180044479  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004447e  lea     rcx, aWiaswritepropb_0; "wiasWritePropBin, invalid pItem"
0x180044485  call    WiaTrace_Trace
0x18004448a  jmp     loc_18004453C
0x18004448f  test    r14, r14
0x180044492  jnz     short loc_1800444E1
0x180044494  lea     rcx, aWiaswritepropb_5; "wiasWritePropBin, invalid pbVal pointer"
0x18004449b  call    WiaTrace_TraceLog
0x1800444a0  mov     rdx, rax; char *
0x1800444a3  mov     rcx, rsi; char *
0x1800444a6  mov     rbx, rax
0x1800444a9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800444ae  mov     rcx, rbx; this
0x1800444b1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800444b6  lea     rcx, aWiaswritepropb_5; "wiasWritePropBin, invalid pbVal pointer"
0x1800444bd  call    WiaTrace_Trace
0x1800444c2  lea     r9d, [r14+1]; int
0x1800444c6  mov     [rsp+0E0h+lpMem], rax; lpMem
0x1800444cb  lea     r8, aWiaswritepropb_7; "wiasWritePropBin"
0x1800444d2  call    WiaTrace_ProcessTrace_Ex
0x1800444d7  mov     edi, 80004003h
0x1800444dc  jmp     loc_180044713
0x1800444e1  xor     r9d, r9d; struct IPropertyStorage **
0x1800444e4  mov     [rbp+57h+arg_0], 0
0x1800444ec  xor     r8d, r8d; struct IPropertyStorage **
0x1800444ef  mov     [rsp+0E0h+lpMem], 0; struct IPropertyStorage **
0x1800444f8  lea     rdx, [rbp+57h+arg_0]; struct IPropertyStorage **
0x1800444fc  mov     rcx, rbx; this
0x1800444ff  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x180044504  mov     edi, eax
0x180044506  test    eax, eax
0x180044508  jns     short loc_180044558
0x18004450a  mov     edx, eax
0x18004450c  lea     rcx, aWiaswritepropb_2; "wiasWritePropBin failed, GetItemPropStr"...
0x180044513  call    WiaTrace_TraceLog
0x180044518  mov     rdx, rax; char *
0x18004451b  mov     rcx, rsi; char *
0x18004451e  mov     rbx, rax
0x180044521  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044526  mov     rcx, rbx; this
0x180044529  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004452e  mov     edx, edi
0x180044530  lea     rcx, aWiaswritepropb_2; "wiasWritePropBin failed, GetItemPropStr"...
0x180044537  call    WiaTrace_Trace
0x18004453c  mov     r9d, 1; int
0x180044542  mov     [rsp+0E0h+lpMem], rax; lpMem
0x180044547  lea     r8, aWiaswritepropb_7; "wiasWritePropBin"
0x18004454e  call    WiaTrace_ProcessTrace_Ex
0x180044553  jmp     loc_180044713
0x180044558  mov     rcx, [rbp+57h+arg_0]
0x18004455c  lea     r9, [rbp+57h+var_90]
0x180044560  mov     esi, 1
0x180044565  mov     [rbp+57h+var_80], r14
0x180044569  xorps   xmm0, xmm0
0x18004456c  lea     r8, [rbp+57h+var_B0]
0x180044570  movups  xmmword ptr [rbp+57h+var_B0.ulKind], xmm0
0x180044574  mov     [rbp+57h+var_B0.ulKind], esi
0x180044577  mov     eax, 1011h
0x18004457c  xorps   xmm1, xmm1
0x18004457f  mov     dword ptr [rbp+57h+var_B0.8], r15d
0x180044583  movups  [rbp+57h+var_90], xmm1
0x180044587  mov     word ptr [rbp+57h+var_90], ax
0x18004458b  mov     edx, esi
0x18004458d  mov     dword ptr [rbp+57h+var_90+8], r12d
0x180044591  lea     r12d, [rsi+1]
0x180044595  mov     rax, [rcx]
0x180044598  mov     dword ptr [rsp+0E0h+lpMem], r12d
0x18004459d  mov     rax, [rax+20h]
0x1800445a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445a6  mov     edi, eax
0x1800445a8  test    eax, eax
0x1800445aa  jns     short loc_1800445B8
0x1800445ac  lea     rdx, aWiaswritepropb_7; "wiasWritePropBin"
0x1800445b3  jmp     loc_1800446F9
0x1800445b8  mov     rcx, rbx; this
0x1800445bb  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x1800445c0  test    eax, eax
0x1800445c2  jz      loc_180044713
0x1800445c8  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800445cc  mov     [rbp+57h+var_A0], 0
0x1800445d4  lea     r8, [rbp+57h+var_A0]; struct CWiaItem **
0x1800445d8  mov     [rbp+57h+var_98], 0
0x1800445e0  mov     edx, r15d; unsigned int
0x1800445e3  mov     dword ptr [rbp+57h+arg_0], 0
0x1800445ea  call    ?_FindRelatedAAITItem@@YAJPEAVCWiaItem@@KPEAPEAV1@PEAK@Z; _FindRelatedAAITItem(CWiaItem *,ulong,CWiaItem * *,ulong *)
0x1800445ef  mov     edi, eax
0x1800445f1  cmp     eax, esi
0x1800445f3  jnz     short loc_1800445FC
0x1800445f5  xor     edi, edi
0x1800445f7  jmp     loc_180044713
0x1800445fc  test    eax, eax
0x1800445fe  jnz     loc_180044713
0x180044604  mov     rcx, [rbp+57h+var_A0]; this
0x180044608  lea     rdx, [rbp+57h+var_98]; struct IPropertyStorage **
0x18004460c  xor     r9d, r9d; struct IPropertyStorage **
0x18004460f  mov     [rsp+0E0h+lpMem], 0; struct IPropertyStorage **
0x180044618  xor     r8d, r8d; struct IPropertyStorage **
0x18004461b  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x180044620  mov     r14, [rbp+57h+var_98]
0x180044624  mov     edi, eax
0x180044626  test    r14, r14
0x180044629  jnz     short loc_18004467C
0x18004462b  test    eax, eax
0x18004462d  js      short loc_180044680
0x18004462f  lea     rcx, aWiaswritepropb_6; "wiasWritePropBin failed, GetItemPropStr"...
0x180044636  mov     edi, 80004003h
0x18004463b  call    WiaTrace_TraceLog
0x180044640  mov     rdx, rax; char *
0x180044643  lea     rcx, aWiaswritepropb_7; "wiasWritePropBin"
0x18004464a  mov     rbx, rax
0x18004464d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044652  mov     rcx, rbx; this
0x180044655  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004465a  lea     rcx, aWiaswritepropb_6; "wiasWritePropBin failed, GetItemPropStr"...
0x180044661  call    WiaTrace_Trace
0x180044666  mov     r9d, esi; int
0x180044669  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18004466e  lea     r8, aWiaswritepropb_7; "wiasWritePropBin"
0x180044675  call    WiaTrace_ProcessTrace_Ex
0x18004467a  jmp     short loc_180044680
0x18004467c  test    eax, eax
0x18004467e  jns     short loc_1800446CE
0x180044680  mov     edx, edi
0x180044682  lea     rcx, aWiaswritepropb_4; "wiasWritePropBin failed, GetItemPropStr"...
0x180044689  call    WiaTrace_TraceLog
0x18004468e  mov     rdx, rax; char *
0x180044691  lea     rcx, aWiaswritepropb_7; "wiasWritePropBin"
0x180044698  mov     rbx, rax
0x18004469b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800446a0  mov     rcx, rbx; this
0x1800446a3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800446a8  mov     edx, edi
0x1800446aa  lea     rcx, aWiaswritepropb_4; "wiasWritePropBin failed, GetItemPropStr"...
0x1800446b1  call    WiaTrace_Trace
0x1800446b6  mov     r9d, esi; int
0x1800446b9  mov     [rsp+0E0h+lpMem], rax; lpMem
0x1800446be  lea     r8, aWiaswritepropb_7; "wiasWritePropBin"
0x1800446c5  call    WiaTrace_ProcessTrace_Ex
0x1800446ca  test    edi, edi
0x1800446cc  js      short loc_180044713
0x1800446ce  mov     rax, [r14]
0x1800446d1  lea     r9, [rbp+57h+var_90]
0x1800446d5  lea     r8, [rbp+57h+var_B0]
0x1800446d9  mov     dword ptr [rsp+0E0h+lpMem], r12d
0x1800446de  mov     edx, esi
0x1800446e0  mov     rcx, r14
0x1800446e3  mov     rax, [rax+20h]
0x1800446e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446ec  mov     edi, eax
0x1800446ee  test    eax, eax
0x1800446f0  jns     short loc_180044713
0x1800446f2  lea     rdx, aWiaswritepropb_3; "wiasWritePropBin (A-AIT)"
0x1800446f9  lea     rax, [rbp+57h+var_B0]
0x1800446fd  xor     r9d, r9d; int
0x180044700  mov     [rsp+0E0h+var_B8], rax; struct tagPROPSPEC *
0x180044705  xor     r8d, r8d; char *
0x180044708  mov     ecx, edi; int
0x18004470a  mov     dword ptr [rsp+0E0h+lpMem], esi; unsigned int
0x18004470e  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x180044713  lea     rcx, [rbp+57h+var_70]; this
0x180044717  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18004471c  lea     r11, [rsp+0E0h+var_20]
0x180044724  mov     eax, edi
0x180044726  mov     rbx, [r11+38h]
0x18004472a  mov     rsi, [r11+40h]
0x18004472e  mov     rsp, r11
0x180044731  pop     r15
0x180044733  pop     r14
0x180044735  pop     r12
0x180044737  pop     rdi
0x180044738  pop     rbp
0x180044739  retn
```
