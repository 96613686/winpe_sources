# wiasSetPropertyAttributes

- ea: `0x1800185a0`
- end: `0x1800189c6`
- name: `wiasSetPropertyAttributes`
- size: `1062`
- prototype: `__int64 __usercall@<rax>(CWiaItem *this@<rcx>, __int64)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x18001750c`
- `0x180017e90`
- `0x180023288`
- `0x1800651c4`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800185a0`
- `0x1800189cc`
- `0x180018ad8`
- `0x18002de18`
- `0x18002def8`
- `0x1800649a0`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800186ec`
- `KERNEL32!LocalFree` at `0x1800186ec`
- `KERNEL32!LocalAlloc` at `0x18001868c`
- `KERNEL32!LocalAlloc` at `0x18001868c`

## string_xrefs

- `0x1800186fa`: `wiasSetPropertyAttributes, could not set access flags`
- `0x180018720`: `wiasSetPropertyAttributes, could not set access flags`
- `0x180018616`: `CWiaItem::GetItemPropStreams`
- `0x18001892a`: `CWiaItem::GetItemPropStreams`
- `0x180018958`: `CWiaItem::GetItemPropStreams`
- `0x180018893`: `wiasSetPropertyAttributes, bad pulAccessFlags parameter`
- `0x1800188b5`: `wiasSetPropertyAttributes, bad pulAccessFlags parameter`

## pseudocode

```c
__int64 __fastcall wiasSetPropertyAttributes(
        struct IWiaItem *this,
        int a2,
        const struct tagPROPSPEC *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rsi
  struct tagWiaTraceData_Type *v9; // rax
  char *v10; // rdx
  unsigned int v11; // r8d
  int inited; // edi
  ULONG (__stdcall *Release)(IWiaItem *); // r13
  ULONG (__stdcall *AddRef)(IWiaItem *); // r15
  struct tagWiaTraceData_Type *v15; // rax
  char *v16; // rdx
  unsigned int v17; // r8d
  struct IWiaItemVtbl *lpVtbl; // rax
  _WORD *v19; // rbx
  int v20; // r8d
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  char *v24; // rbx
  void *v25; // rdx
  void **v26; // rax
  void *v27; // rdx
  __int64 v28; // rcx
  char *v30; // rbx
  void *v31; // rdx
  char *v32; // rbx
  void *v33; // rdx
  void **v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  char *v37; // rbx
  void *v38; // rdx
  void **v39; // rax
  void *v40; // rdx
  __int64 v41; // rcx
  char *v42; // rbx
  void *v43; // rdx
  char *v44; // rbx
  void *v45; // rdx
  char *v46; // rbx
  void *v47; // rdx
  void **v48; // rax
  void *v49; // rdx
  __int64 v50; // rcx
  char *v51; // rbx
  void *v52; // rdx
  void **v53; // rax
  void *v54; // rdx
  __int64 v55; // rcx
  char *v56; // rbx
  void *v57; // rdx
  void **v58; // rax
  void *v59; // rdx
  __int64 v60; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-E8h]
  unsigned int lpMema; // [rsp+20h] [rbp-E8h]
  _BYTE v63[80]; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v64[136]; // [rsp+80h] [rbp-88h] BYREF

  v6 = a2;
  v9 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasSetPropertyAttributes");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v63, v10, v11, "wiasSetPropertyAttributes", lpMem, v9);
  inited = ValidateWiaItem(this);
  if ( inited < 0 )
  {
    v32 = (char *)WiaTrace_TraceLog("wiasSetPropertyAttributes, invalid pItem");
    WriteDbgTraceErrorWI("wiasSetPropertyAttributes", v32);
    WiaTrcLib::Free((WiaTrcLib *)v32, v33);
    v34 = (void **)WiaTrace_Trace("wiasSetPropertyAttributes, invalid pItem");
    WiaTrace_ProcessTrace_Ex(v36, v35, (void *)"wiasSetPropertyAttributes", 1, v34);
    goto LABEL_16;
  }
  if ( !a3 )
  {
    v37 = (char *)WiaTrace_TraceLog("wiasSetPropertyAttributes, bad pPropSpec parameter");
    WriteDbgTraceErrorWI("wiasSetPropertyAttributes", v37);
    WiaTrcLib::Free((WiaTrcLib *)v37, v38);
    v39 = (void **)WiaTrace_Trace("wiasSetPropertyAttributes, bad pPropSpec parameter");
LABEL_22:
    WiaTrace_ProcessTrace_Ex(v41, v40, (void *)"wiasSetPropertyAttributes", 1, v39);
    inited = -2147467261;
    goto LABEL_16;
  }
  if ( !a4 )
  {
    v44 = (char *)WiaTrace_TraceLog("wiasSetPropertyAttributes, bad pulAccessFlags parameter");
    WriteDbgTraceErrorWI("wiasSetPropertyAttributes", v44);
    WiaTrcLib::Free((WiaTrcLib *)v44, v45);
    v39 = (void **)WiaTrace_Trace("wiasSetPropertyAttributes, bad pulAccessFlags parameter");
    goto LABEL_22;
  }
  if ( !a5 )
  {
    v42 = (char *)WiaTrace_TraceLog("wiasSetPropertyAttributes, bad pPropVar parameter");
    WriteDbgTraceErrorWI("wiasSetPropertyAttributes", v42);
    WiaTrcLib::Free((WiaTrcLib *)v42, v43);
    v39 = (void **)WiaTrace_Trace("wiasSetPropertyAttributes, bad pPropVar parameter");
    goto LABEL_22;
  }
  Release = 0;
  AddRef = 0;
  v15 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::GetItemPropStreams");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v64, v16, v17, "CWiaItem::GetItemPropStreams", lpMema, v15);
  if ( this[27].lpVtbl )
  {
    inited = 0;
    if ( LODWORD(this[16].lpVtbl) || (inited = CWiaItem::InitLazyProps((CWiaItem *)this), inited >= 0) )
    {
      lpVtbl = this[27].lpVtbl;
      Release = lpVtbl->Release;
      AddRef = lpVtbl->AddRef;
    }
    else
    {
      v51 = (char *)WiaTrace_TraceLog("InitLazyProps failed");
      WriteDbgTraceErrorWI("CWiaItem::GetItemPropStreams", v51);
      WiaTrcLib::Free((WiaTrcLib *)v51, v52);
      v53 = (void **)WiaTrace_Trace("InitLazyProps failed");
      WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"CWiaItem::GetItemPropStreams", 1, v53);
    }
  }
  else
  {
    v46 = (char *)WiaTrace_TraceLog("NULL internal property storage pointer");
    WriteDbgTraceErrorWI("CWiaItem::GetItemPropStreams", v46);
    WiaTrcLib::Free((WiaTrcLib *)v46, v47);
    v48 = (void **)WiaTrace_Trace("NULL internal property storage pointer");
    WiaTrace_ProcessTrace_Ex(v50, v49, (void *)"CWiaItem::GetItemPropStreams", 1, v48);
    inited = -2147467259;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v64);
  if ( inited < 0 )
    goto LABEL_16;
  v19 = LocalAlloc(0x40u, 24 * v6);
  if ( v19 )
  {
    v20 = 0;
    if ( (int)v6 > 0 )
    {
      v21 = 0;
      do
      {
        v22 = 3 * v21;
        ++v20;
        v19[4 * v22] = 19;
        v23 = *(_DWORD *)(a4 + 4 * v21++);
        *(_DWORD *)&v19[4 * v22 + 4] = v23;
      }
      while ( v20 < (int)v6 );
    }
    inited = (*(__int64 (__fastcall **)(ULONG (__stdcall *)(IWiaItem *), _QWORD, const struct tagPROPSPEC *, _WORD *, int))(*(_QWORD *)Release + 32LL))(
               Release,
               (unsigned int)v6,
               a3,
               v19,
               2);
    LocalFree(v19);
    if ( inited >= 0 )
    {
      inited = (*(__int64 (__fastcall **)(ULONG (__stdcall *)(IWiaItem *), _QWORD, const struct tagPROPSPEC *, __int64, int))(*(_QWORD *)AddRef + 32LL))(
                 AddRef,
                 (unsigned int)v6,
                 a3,
                 a5,
                 2);
      if ( inited >= 0 )
        goto LABEL_16;
      v30 = (char *)WiaTrace_TraceLog("wiasSetPropertyAttributes, could not set valid values");
      WriteDbgTraceErrorWI("wiasSetPropertyAttributes", v30);
      WiaTrcLib::Free((WiaTrcLib *)v30, v31);
      v26 = (void **)WiaTrace_Trace("wiasSetPropertyAttributes, could not set valid values");
    }
    else
    {
      v24 = (char *)WiaTrace_TraceLog("wiasSetPropertyAttributes, could not set access flags");
      WriteDbgTraceErrorWI("wiasSetPropertyAttributes", v24);
      WiaTrcLib::Free((WiaTrcLib *)v24, v25);
      v26 = (void **)WiaTrace_Trace("wiasSetPropertyAttributes, could not set access flags");
    }
    WiaTrace_ProcessTrace_Ex(v28, v27, (void *)"wiasSetPropertyAttributes", 1, v26);
    ReportReadWriteMultipleError(inited, "wiasSetPropertyAttributes", 0, 0, v6, a3);
LABEL_16:
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v63);
    return (unsigned int)inited;
  }
  v56 = (char *)WiaTrace_TraceLog("wiasSetPropertyAttributes, out of memory");
  WriteDbgTraceErrorWI("wiasSetPropertyAttributes", v56);
  WiaTrcLib::Free((WiaTrcLib *)v56, v57);
  v58 = (void **)WiaTrace_Trace("wiasSetPropertyAttributes, out of memory");
  WiaTrace_ProcessTrace_Ex(v60, v59, (void *)"wiasSetPropertyAttributes", 1, v58);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v63);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800185a0  push    rbx
0x1800185a2  push    rbp
0x1800185a3  push    rsi
0x1800185a4  push    rdi
0x1800185a5  push    r12
0x1800185a7  push    r13
0x1800185a9  push    r15
0x1800185ab  sub     rsp, 0D0h
0x1800185b2  mov     rbx, rcx
0x1800185b5  movsxd  rsi, edx
0x1800185b8  lea     rcx, aWiassetpropert_6; "::wiasSetPropertyAttributes"
0x1800185bf  mov     r12, r9
0x1800185c2  mov     rbp, r8
0x1800185c5  call    WiaTrace_Trace
0x1800185ca  lea     r15, aWiassetpropert_0; "wiasSetPropertyAttributes"
0x1800185d1  mov     [rsp+108h+var_E0], rax; struct tagWiaTraceData_Type *
0x1800185d6  mov     r9, r15; char *
0x1800185d9  lea     rcx, [rsp+108h+var_D8]; this
0x1800185de  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800185e3  mov     rcx, rbx; struct IWiaItem *
0x1800185e6  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x1800185eb  mov     edi, eax
0x1800185ed  test    eax, eax
0x1800185ef  js      loc_1800187D7
0x1800185f5  test    rbp, rbp
0x1800185f8  jz      loc_18001881D
0x1800185fe  test    r12, r12
0x180018601  jz      loc_180018893
0x180018607  cmp     [rsp+108h+arg_20], 0
0x180018610  jz      loc_180018848
0x180018616  lea     rdi, aCwiaitemGetite; "CWiaItem::GetItemPropStreams"
0x18001861d  xor     r13d, r13d
0x180018620  mov     rcx, rdi
0x180018623  xor     r15d, r15d
0x180018626  call    WiaTrace_Trace
0x18001862b  mov     r9, rdi; char *
0x18001862e  mov     [rsp+108h+var_E0], rax; struct tagWiaTraceData_Type *
0x180018633  lea     rcx, [rsp+108h+var_88]; this
0x18001863b  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180018640  cmp     [rbx+0D8h], r13
0x180018647  jz      loc_1800188BE
0x18001864d  xor     edi, edi
0x18001864f  cmp     [rbx+80h], edi
0x180018655  jz      loc_180018909
0x18001865b  mov     rax, [rbx+0D8h]
0x180018662  mov     r13, [rax+10h]
0x180018666  mov     r15, [rax+8]
0x18001866a  lea     rcx, [rsp+108h+var_88]; this
0x180018672  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180018677  test    edi, edi
0x180018679  js      loc_180018760
0x18001867f  lea     rdx, [rsi+rsi*2]
0x180018683  mov     ecx, 40h ; '@'; uFlags
0x180018688  shl     rdx, 3; uBytes
0x18001868c  call    cs:__imp_LocalAlloc
0x180018692  mov     rbx, rax
0x180018695  test    rax, rax
0x180018698  jz      loc_180018969
0x18001869e  xor     r8d, r8d
0x1800186a1  test    esi, esi
0x1800186a3  jle     short loc_1800186C4
0x1800186a5  xor     edx, edx
0x1800186a7  lea     rcx, [rdx+rdx*2]
0x1800186ab  inc     r8d
0x1800186ae  mov     word ptr [rbx+rcx*8], 13h
0x1800186b4  mov     eax, [r12+rdx*4]
0x1800186b8  inc     rdx
0x1800186bb  mov     [rbx+rcx*8+8], eax
0x1800186bf  cmp     r8d, esi
0x1800186c2  jl      short loc_1800186A7
0x1800186c4  mov     rax, [r13+0]
0x1800186c8  mov     r12d, 2
0x1800186ce  mov     r9, rbx
0x1800186d1  mov     dword ptr [rsp+108h+lpMem], r12d
0x1800186d6  mov     r8, rbp
0x1800186d9  mov     edx, esi
0x1800186db  mov     rcx, r13
0x1800186de  mov     rax, [rax+20h]
0x1800186e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186e7  mov     rcx, rbx; hMem
0x1800186ea  mov     edi, eax
0x1800186ec  call    cs:__imp_LocalFree
0x1800186f2  test    edi, edi
0x1800186f4  jns     loc_18001877E
0x1800186fa  lea     rcx, aWiassetpropert_2; "wiasSetPropertyAttributes, could not se"...
0x180018701  call    WiaTrace_TraceLog
0x180018706  mov     rdx, rax; char *
0x180018709  lea     rcx, aWiassetpropert_0; "wiasSetPropertyAttributes"
0x180018710  mov     rbx, rax
0x180018713  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018718  mov     rcx, rbx; this
0x18001871b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018720  lea     rcx, aWiassetpropert_2; "wiasSetPropertyAttributes, could not se"...
0x180018727  call    WiaTrace_Trace
0x18001872c  mov     r9d, 1; int
0x180018732  mov     [rsp+108h+lpMem], rax; lpMem
0x180018737  lea     r8, aWiassetpropert_0; "wiasSetPropertyAttributes"
0x18001873e  call    WiaTrace_ProcessTrace_Ex
0x180018743  xor     r9d, r9d; int
0x180018746  mov     [rsp+108h+var_E0], rbp; struct tagPROPSPEC *
0x18001874b  xor     r8d, r8d; char *
0x18001874e  mov     dword ptr [rsp+108h+lpMem], esi; unsigned int
0x180018752  lea     rdx, aWiassetpropert_0; "wiasSetPropertyAttributes"
0x180018759  mov     ecx, edi; int
0x18001875b  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x180018760  lea     rcx, [rsp+108h+var_D8]; this
0x180018765  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18001876a  mov     eax, edi
0x18001876c  add     rsp, 0D0h
0x180018773  pop     r15
0x180018775  pop     r13
0x180018777  pop     r12
0x180018779  pop     rdi
0x18001877a  pop     rsi
0x18001877b  pop     rbp
0x18001877c  pop     rbx
0x18001877d  retn
0x18001877e  mov     rax, [r15]
0x180018781  mov     r8, rbp
0x180018784  mov     r9, [rsp+108h+arg_20]
0x18001878c  mov     edx, esi
0x18001878e  mov     rcx, r15
0x180018791  mov     dword ptr [rsp+108h+lpMem], r12d
0x180018796  mov     rax, [rax+20h]
0x18001879a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001879f  mov     edi, eax
0x1800187a1  test    eax, eax
0x1800187a3  jns     short loc_180018760
0x1800187a5  lea     rcx, aWiassetpropert_1; "wiasSetPropertyAttributes, could not se"...
0x1800187ac  call    WiaTrace_TraceLog
0x1800187b1  mov     rdx, rax; char *
0x1800187b4  lea     rcx, aWiassetpropert_0; "wiasSetPropertyAttributes"
0x1800187bb  mov     rbx, rax
0x1800187be  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800187c3  mov     rcx, rbx; this
0x1800187c6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800187cb  lea     rcx, aWiassetpropert_1; "wiasSetPropertyAttributes, could not se"...
0x1800187d2  jmp     loc_180018727
0x1800187d7  lea     rcx, aWiassetpropert_8; "wiasSetPropertyAttributes, invalid pIte"...
0x1800187de  call    WiaTrace_TraceLog
0x1800187e3  mov     rdx, rax; char *
0x1800187e6  mov     rcx, r15; char *
0x1800187e9  mov     rbx, rax
0x1800187ec  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800187f1  mov     rcx, rbx; this
0x1800187f4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800187f9  lea     rcx, aWiassetpropert_8; "wiasSetPropertyAttributes, invalid pIte"...
0x180018800  call    WiaTrace_Trace
0x180018805  mov     r9d, 1; int
0x18001880b  mov     [rsp+108h+lpMem], rax; lpMem
0x180018810  mov     r8, r15; int
0x180018813  call    WiaTrace_ProcessTrace_Ex
0x180018818  jmp     loc_180018760
0x18001881d  lea     rcx, aWiassetpropert_3; "wiasSetPropertyAttributes, bad pPropSpe"...
0x180018824  call    WiaTrace_TraceLog
0x180018829  mov     rdx, rax; char *
0x18001882c  mov     rcx, r15; char *
0x18001882f  mov     rbx, rax
0x180018832  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018837  mov     rcx, rbx; this
0x18001883a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001883f  lea     rcx, aWiassetpropert_3; "wiasSetPropertyAttributes, bad pPropSpe"...
0x180018846  jmp     short loc_180018871
0x180018848  lea     rcx, aWiassetpropert_4; "wiasSetPropertyAttributes, bad pPropVar"...
0x18001884f  call    WiaTrace_TraceLog
0x180018854  mov     rdx, rax; char *
0x180018857  mov     rcx, r15; char *
0x18001885a  mov     rbx, rax
0x18001885d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018862  mov     rcx, rbx; this
0x180018865  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001886a  lea     rcx, aWiassetpropert_4; "wiasSetPropertyAttributes, bad pPropVar"...
0x180018871  call    WiaTrace_Trace
0x180018876  mov     r9d, 1; int
0x18001887c  mov     [rsp+108h+lpMem], rax; lpMem
0x180018881  mov     r8, r15; int
0x180018884  call    WiaTrace_ProcessTrace_Ex
0x180018889  mov     edi, 80004003h
0x18001888e  jmp     loc_180018760
0x180018893  lea     rcx, aWiassetpropert_9; "wiasSetPropertyAttributes, bad pulAcces"...
0x18001889a  call    WiaTrace_TraceLog
0x18001889f  mov     rdx, rax; char *
0x1800188a2  mov     rcx, r15; char *
0x1800188a5  mov     rbx, rax
0x1800188a8  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800188ad  mov     rcx, rbx; this
0x1800188b0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800188b5  lea     rcx, aWiassetpropert_9; "wiasSetPropertyAttributes, bad pulAcces"...
0x1800188bc  jmp     short loc_180018871
0x1800188be  lea     rcx, aNullInternalPr; "NULL internal property storage pointer"
0x1800188c5  call    WiaTrace_TraceLog
0x1800188ca  mov     rdx, rax; char *
0x1800188cd  mov     rcx, rdi; char *
0x1800188d0  mov     rbx, rax
0x1800188d3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800188d8  mov     rcx, rbx; this
0x1800188db  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800188e0  lea     rcx, aNullInternalPr; "NULL internal property storage pointer"
0x1800188e7  call    WiaTrace_Trace
0x1800188ec  mov     r9d, 1; int
0x1800188f2  mov     [rsp+108h+lpMem], rax; lpMem
0x1800188f7  mov     r8, rdi; int
0x1800188fa  call    WiaTrace_ProcessTrace_Ex
0x1800188ff  mov     edi, 80004005h
0x180018904  jmp     loc_18001866A
0x180018909  mov     rcx, rbx; this
0x18001890c  call    ?InitLazyProps@CWiaItem@@QEAAJXZ; CWiaItem::InitLazyProps(void)
0x180018911  mov     edi, eax
0x180018913  test    eax, eax
0x180018915  jns     loc_18001865B
0x18001891b  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x180018922  call    WiaTrace_TraceLog
0x180018927  mov     rdx, rax; char *
0x18001892a  lea     rcx, aCwiaitemGetite; "CWiaItem::GetItemPropStreams"
0x180018931  mov     rbx, rax
0x180018934  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018939  mov     rcx, rbx; this
0x18001893c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018941  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x180018948  call    WiaTrace_Trace
0x18001894d  mov     r9d, 1; int
0x180018953  mov     [rsp+108h+lpMem], rax; lpMem
0x180018958  lea     r8, aCwiaitemGetite; "CWiaItem::GetItemPropStreams"
0x18001895f  call    WiaTrace_ProcessTrace_Ex
0x180018964  jmp     loc_18001866A
0x180018969  lea     rcx, aWiassetpropert_5; "wiasSetPropertyAttributes, out of memor"...
0x180018970  call    WiaTrace_TraceLog
0x180018975  mov     rdx, rax; char *
0x180018978  lea     rcx, aWiassetpropert_0; "wiasSetPropertyAttributes"
0x18001897f  mov     rbx, rax
0x180018982  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018987  mov     rcx, rbx; this
0x18001898a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001898f  lea     rcx, aWiassetpropert_5; "wiasSetPropertyAttributes, out of memor"...
0x180018996  call    WiaTrace_Trace
0x18001899b  mov     r9d, 1; int
0x1800189a1  mov     [rsp+108h+lpMem], rax; lpMem
0x1800189a6  lea     r8, aWiassetpropert_0; "wiasSetPropertyAttributes"
0x1800189ad  call    WiaTrace_ProcessTrace_Ex
0x1800189b2  lea     rcx, [rsp+108h+var_D8]; this
0x1800189b7  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800189bc  mov     eax, 8007000Eh
0x1800189c1  jmp     loc_18001876C
```
