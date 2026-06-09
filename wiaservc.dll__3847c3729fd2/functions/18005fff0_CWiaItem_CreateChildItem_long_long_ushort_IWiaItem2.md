# CWiaItem::CreateChildItem(long,long,ushort *,IWiaItem2 * *)

- ea: `0x18005fff0`
- end: `0x18006033e`
- name: `?CreateChildItem@CWiaItem@@UEAAJJJPEAGPEAPEAUIWiaItem2@@@Z`
- size: `846`
- prototype: `int(CWiaItem *__hidden this, int, int, unsigned __int16 *, struct IWiaItem2 **)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x180013bfc`
- `0x180018390`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180033cc0`
- `0x18005fa70`
- `0x18005fd7c`
- `0x18005fff0`
- `0x180068b08`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006016b`
- `OLEAUT32!__imp_SysAllocString` at `0x18006016b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006030a`
- `OLEAUT32!__imp_SysFreeString` at `0x18006030a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800600d0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800600d0`

## string_xrefs

- `0x180060073`: `failed (E_NOTIMPL), operation not allowed in compatibility mode`
- `0x180060099`: `failed (E_NOTIMPL), operation not allowed in compatibility mode`
- `0x180060026`: `CWiaItem::IWiaItem2::CreateChildItem`
- `0x18006003c`: `CWiaItem::CreateChildItem`
- `0x180060082`: `CWiaItem::CreateChildItem`
- `0x1800600ae`: `CWiaItem::CreateChildItem`
- `0x180060273`: `CWiaItem::CreateChildItem`
- `0x1800602a1`: `CWiaItem::CreateChildItem`
- `0x1800602c3`: `CWiaItem::CreateChildItem`

## pseudocode

```c
__int64 __fastcall CWiaItem::CreateChildItem(
        CWiaTree **this,
        int a2,
        int a3,
        unsigned __int16 *a4,
        struct IWiaItem2 **a5)
{
  struct tagWiaTraceData_Type *v8; // rax
  char *v9; // rdx
  unsigned int v10; // r8d
  CWiaItem *v11; // rbx
  unsigned __int16 *v12; // r15
  char *v13; // rbx
  void *v14; // rdx
  void **v15; // rax
  void *v16; // rdx
  __int64 v17; // rcx
  int FullItemName; // edi
  BSTR v19; // rax
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  char *v25; // rbx
  void *v26; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v29; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v30; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+40h] [rbp-C0h]
  _BYTE v32[80]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v33[38]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v34[38]; // [rsp+1D0h] [rbp+D0h] BYREF

  v31 = a2;
  v8 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::IWiaItem2::CreateChildItem");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v32, v9, v10, "CWiaItem::CreateChildItem", lpMem, v8);
  v11 = (CWiaItem *)(this - 7);
  v29 = 0;
  v12 = 0;
  v30 = 0;
  if ( (unsigned int)CWiaItem::IsCompatMode((CWiaItem *)(this - 7)) )
  {
    v13 = (char *)WiaTrace_TraceLog("failed (E_NOTIMPL), operation not allowed in compatibility mode");
    WriteDbgTraceErrorWI("CWiaItem::CreateChildItem", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v15 = (void **)WiaTrace_Trace("failed (E_NOTIMPL), operation not allowed in compatibility mode");
    WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"CWiaItem::CreateChildItem", 1, v15);
    FullItemName = -2147467263;
    goto LABEL_18;
  }
  if ( !a5 || !SysStringLen(a4) )
  {
    FullItemName = -2147467261;
    goto LABEL_18;
  }
  FullItemName = CWiaTree::GetFullItemName(this[8], &v29);
  if ( FullItemName < 0 )
    goto LABEL_18;
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v34, v29);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v33, L"\\");
  CSimpleStringBase<unsigned short>::Concat(v34, v33);
  v33[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v33);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v33, a4);
  CSimpleStringBase<unsigned short>::Concat(v34, v33);
  v33[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v33);
  v19 = SysAllocString((const OLECHAR *)v34[33]);
  v34[0] = &CSimpleStringBase<unsigned short>::`vftable';
  v12 = v19;
  CSimpleStringBase<unsigned short>::DeleteStorage(v34);
  v34[34] = 0;
  LODWORD(v29) = 0;
  if ( (int)wiasReadPropLong(v11, 1) < 0 || !(_DWORD)v29 )
  {
    FullItemName = -2147467263;
    v25 = (char *)WiaTrace_TraceLog("failed (E_NOTIMPL), WIA_IPS_SUPPORTS_CHILD_ITEM_CREATION not supported or FALSE");
    WriteDbgTraceErrorWI("CWiaItem::CreateChildItem", v25);
    WiaTrcLib::Free((WiaTrcLib *)v25, v26);
    v22 = (void **)WiaTrace_Trace("failed (E_NOTIMPL), WIA_IPS_SUPPORTS_CHILD_ITEM_CREATION not supported or FALSE");
    goto LABEL_15;
  }
  LODWORD(v29) = 0;
  if ( (int)wiasReadPropLong(v11, 1) < 0 || ((unsigned __int8)v29 & 4) == 0 )
  {
    FullItemName = -2147467263;
    v20 = (char *)WiaTrace_TraceLog("failed (E_NOTIMPL), not a folder (WiaItemTypeFolder) item");
    WriteDbgTraceErrorWI("CWiaItem::CreateChildItem", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v22 = (void **)WiaTrace_Trace("failed (E_NOTIMPL), not a folder (WiaItemTypeFolder) item");
LABEL_15:
    WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"CWiaItem::CreateChildItem", 1, v22);
    goto LABEL_18;
  }
  FullItemName = CWiaItem::CreateChild(v11, v31, a4, v12, (void **)&v30);
  if ( FullItemName >= 0 )
  {
    if ( (a3 & 0x40000000) == 0 || (FullItemName = CWiaItem::CopyParentReadWriteProperties(v11, v30), FullItemName >= 0) )
      FullItemName = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IWiaItem2 **))v30->lpVtbl->QueryInterface)(
                       v30,
                       &IID_IWiaItem2,
                       a5);
  }
LABEL_18:
  if ( v30 )
  {
    ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->Release)(v30);
    v30 = 0;
  }
  SysFreeString(v12);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v32);
  return (unsigned int)FullItemName;
}

```

## disassembly

```asm
0x18005fff0  push    rbp
0x18005fff2  push    rbx
0x18005fff3  push    rdi
0x18005fff4  push    r12
0x18005fff6  push    r13
0x18005fff8  push    r14
0x18005fffa  push    r15
0x18005fffc  lea     rbp, [rsp-210h]
0x180060004  sub     rsp, 310h
0x18006000b  mov     rax, cs:__security_cookie
0x180060012  xor     rax, rsp
0x180060015  mov     [rbp+240h+var_40], rax
0x18006001c  mov     r12, [rbp+240h+arg_20]
0x180060023  mov     rdi, rcx
0x180060026  lea     rcx, aCwiaitemIwiait_8; "CWiaItem::IWiaItem2::CreateChildItem"
0x18006002d  mov     [rsp+340h+var_300], edx
0x180060031  mov     r14, r9
0x180060034  mov     r13d, r8d
0x180060037  call    WiaTrace_Trace
0x18006003c  lea     r9, aCwiaitemCreate; "CWiaItem::CreateChildItem"
0x180060043  mov     [rsp+340h+var_318], rax; struct tagWiaTraceData_Type *
0x180060048  lea     rcx, [rsp+340h+var_2F0]; this
0x18006004d  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180060052  lea     rbx, [rdi-38h]
0x180060056  mov     [rsp+340h+var_310], 0
0x18006005f  xor     r15d, r15d
0x180060062  mov     rcx, rbx; this
0x180060065  mov     [rsp+340h+var_308], r15
0x18006006a  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x18006006f  test    eax, eax
0x180060071  jz      short loc_1800600C4
0x180060073  lea     rcx, aFailedENotimpl; "failed (E_NOTIMPL), operation not allow"...
0x18006007a  call    WiaTrace_TraceLog
0x18006007f  mov     rdx, rax; char *
0x180060082  lea     rcx, aCwiaitemCreate; "CWiaItem::CreateChildItem"
0x180060089  mov     rbx, rax
0x18006008c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180060091  mov     rcx, rbx; this
0x180060094  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180060099  lea     rcx, aFailedENotimpl; "failed (E_NOTIMPL), operation not allow"...
0x1800600a0  call    WiaTrace_Trace
0x1800600a5  lea     r9d, [r15+1]; int
0x1800600a9  mov     [rsp+340h+lpMem], rax; lpMem
0x1800600ae  lea     r8, aCwiaitemCreate; "CWiaItem::CreateChildItem"
0x1800600b5  call    WiaTrace_ProcessTrace_Ex
0x1800600ba  mov     edi, 80004001h
0x1800600bf  jmp     loc_1800602E8
0x1800600c4  test    r12, r12
0x1800600c7  jz      loc_1800602E3
0x1800600cd  mov     rcx, r14; pbstr
0x1800600d0  call    cs:__imp_SysStringLen
0x1800600d6  test    eax, eax
0x1800600d8  jz      loc_1800602E3
0x1800600de  mov     rcx, [rdi+40h]; this
0x1800600e2  lea     rdx, [rsp+340h+var_310]; unsigned __int16 **
0x1800600e7  call    ?GetFullItemName@CWiaTree@@QEAAJPEAPEAG@Z; CWiaTree::GetFullItemName(ushort * *)
0x1800600ec  mov     edi, eax
0x1800600ee  test    eax, eax
0x1800600f0  js      loc_1800602E8
0x1800600f6  mov     rdx, [rsp+340h+var_310]
0x1800600fb  lea     rcx, [rbp+240h+var_170]
0x180060102  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180060107  lea     rdx, SubBlock; "\\"
0x18006010e  lea     rcx, [rbp+240h+var_2A0]
0x180060112  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180060117  lea     rdx, [rbp+240h+var_2A0]
0x18006011b  lea     rcx, [rbp+240h+var_170]
0x180060122  call    ?Concat@?$CSimpleStringBase@G@@QEAAXAEBV1@@Z; CSimpleStringBase<ushort>::Concat(CSimpleStringBase<ushort> const &)
0x180060127  lea     rdi, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18006012e  lea     rcx, [rbp+240h+var_2A0]
0x180060132  mov     [rbp+240h+var_2A0], rdi
0x180060136  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18006013b  mov     rdx, r14
0x18006013e  lea     rcx, [rbp+240h+var_2A0]
0x180060142  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180060147  lea     rdx, [rbp+240h+var_2A0]
0x18006014b  lea     rcx, [rbp+240h+var_170]
0x180060152  call    ?Concat@?$CSimpleStringBase@G@@QEAAXAEBV1@@Z; CSimpleStringBase<ushort>::Concat(CSimpleStringBase<ushort> const &)
0x180060157  lea     rcx, [rbp+240h+var_2A0]
0x18006015b  mov     [rbp+240h+var_2A0], rdi
0x18006015f  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180060164  mov     rcx, [rbp+240h+psz]; psz
0x18006016b  call    cs:__imp_SysAllocString
0x180060171  lea     rcx, [rbp+240h+var_170]
0x180060178  mov     [rbp+240h+var_170], rdi
0x18006017f  mov     r15, rax
0x180060182  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180060187  xor     r9d, r9d
0x18006018a  mov     [rbp+240h+var_60], 0
0x180060195  lea     r8, [rsp+340h+var_310]
0x18006019a  mov     dword ptr [rsp+340h+var_310], 0
0x1800601a2  mov     edx, 0C24h
0x1800601a7  mov     dword ptr [rsp+340h+lpMem], 1; int
0x1800601af  mov     rcx, rbx; this
0x1800601b2  call    wiasReadPropLong
0x1800601b7  test    eax, eax
0x1800601b9  js      loc_1800602AF
0x1800601bf  cmp     dword ptr [rsp+340h+var_310], 0
0x1800601c4  jz      loc_1800602AF
0x1800601ca  xor     r9d, r9d
0x1800601cd  mov     dword ptr [rsp+340h+var_310], 0
0x1800601d5  lea     r8, [rsp+340h+var_310]
0x1800601da  mov     dword ptr [rsp+340h+lpMem], 1; int
0x1800601e2  mov     edx, 1005h
0x1800601e7  mov     rcx, rbx; this
0x1800601ea  call    wiasReadPropLong
0x1800601ef  test    eax, eax
0x1800601f1  js      short loc_18006025F
0x1800601f3  test    byte ptr [rsp+340h+var_310], 4
0x1800601f8  jz      short loc_18006025F
0x1800601fa  mov     edx, [rsp+340h+var_300]; int
0x1800601fe  lea     rax, [rsp+340h+var_308]
0x180060203  mov     r9, r15; unsigned __int16 *
0x180060206  mov     [rsp+340h+lpMem], rax; void **
0x18006020b  mov     r8, r14; unsigned __int16 *
0x18006020e  mov     rcx, rbx; this
0x180060211  call    ?CreateChild@CWiaItem@@AEAAJJPEAG0PEAPEAX@Z; CWiaItem::CreateChild(long,ushort *,ushort *,void * *)
0x180060216  mov     edi, eax
0x180060218  test    eax, eax
0x18006021a  js      loc_1800602E8
0x180060220  bt      r13d, 1Eh
0x180060225  jnb     short loc_18006023E
0x180060227  mov     rdx, [rsp+340h+var_308]; struct IUnknown *
0x18006022c  mov     rcx, rbx; this
0x18006022f  call    ?CopyParentReadWriteProperties@CWiaItem@@AEAAJPEAUIUnknown@@@Z; CWiaItem::CopyParentReadWriteProperties(IUnknown *)
0x180060234  mov     edi, eax
0x180060236  test    eax, eax
0x180060238  js      loc_1800602E8
0x18006023e  mov     rcx, [rsp+340h+var_308]
0x180060243  lea     rdx, IID_IWiaItem2
0x18006024a  mov     r8, r12
0x18006024d  mov     rax, [rcx]
0x180060250  mov     rax, [rax]
0x180060253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060258  mov     edi, eax
0x18006025a  jmp     loc_1800602E8
0x18006025f  lea     rcx, aFailedENotimpl_0; "failed (E_NOTIMPL), not a folder (WiaIt"...
0x180060266  mov     edi, 80004001h
0x18006026b  call    WiaTrace_TraceLog
0x180060270  mov     rdx, rax; char *
0x180060273  lea     rcx, aCwiaitemCreate; "CWiaItem::CreateChildItem"
0x18006027a  mov     rbx, rax
0x18006027d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180060282  mov     rcx, rbx; this
0x180060285  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006028a  lea     rcx, aFailedENotimpl_0; "failed (E_NOTIMPL), not a folder (WiaIt"...
0x180060291  call    WiaTrace_Trace
0x180060296  mov     r9d, 1; int
0x18006029c  mov     [rsp+340h+lpMem], rax; lpMem
0x1800602a1  lea     r8, aCwiaitemCreate; "CWiaItem::CreateChildItem"
0x1800602a8  call    WiaTrace_ProcessTrace_Ex
0x1800602ad  jmp     short loc_1800602E8
0x1800602af  lea     rcx, aFailedENotimpl_1; "failed (E_NOTIMPL), WIA_IPS_SUPPORTS_CH"...
0x1800602b6  mov     edi, 80004001h
0x1800602bb  call    WiaTrace_TraceLog
0x1800602c0  mov     rdx, rax; char *
0x1800602c3  lea     rcx, aCwiaitemCreate; "CWiaItem::CreateChildItem"
0x1800602ca  mov     rbx, rax
0x1800602cd  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800602d2  mov     rcx, rbx; this
0x1800602d5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800602da  lea     rcx, aFailedENotimpl_1; "failed (E_NOTIMPL), WIA_IPS_SUPPORTS_CH"...
0x1800602e1  jmp     short loc_180060291
0x1800602e3  mov     edi, 80004003h
0x1800602e8  mov     rcx, [rsp+340h+var_308]
0x1800602ed  test    rcx, rcx
0x1800602f0  jz      short loc_180060307
0x1800602f2  mov     rax, [rcx]
0x1800602f5  mov     rax, [rax+10h]
0x1800602f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602fe  mov     [rsp+340h+var_308], 0
0x180060307  mov     rcx, r15; bstrString
0x18006030a  call    cs:__imp_SysFreeString
0x180060310  lea     rcx, [rsp+340h+var_2F0]; this
0x180060315  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18006031a  mov     eax, edi
0x18006031c  mov     rcx, [rbp+240h+var_40]
0x180060323  xor     rcx, rsp; StackCookie
0x180060326  call    __security_check_cookie
0x18006032b  add     rsp, 310h
0x180060332  pop     r15
0x180060334  pop     r14
0x180060336  pop     r13
0x180060338  pop     r12
0x18006033a  pop     rdi
0x18006033b  pop     rbx
0x18006033c  pop     rbp
0x18006033d  retn
```
