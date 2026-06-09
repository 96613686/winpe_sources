# CWiaItem::CreateChild(long,ushort *,ushort *,void * *)

- ea: `0x18005fd7c`
- end: `0x18005ffdd`
- name: `?CreateChild@CWiaItem@@AEAAJJPEAG0PEAPEAX@Z`
- size: `609`
- prototype: `__int64 __fastcall(CWiaItem *this, __int64, unsigned __int16 *, unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005fff0`
- `0x180060350`

## callees

- `0x18000426c`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x1800453c0`
- `0x18005fd7c`
- `0x1800649a0`
- `0x180068ca0`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18005fdd6`
- `OLEAUT32!__imp_SysStringLen` at `0x18005fde5`
- `OLEAUT32!__imp_SysStringLen` at `0x18005fdd6`
- `OLEAUT32!__imp_SysStringLen` at `0x18005fde5`

## string_xrefs

- `0x18005fe0a`: `failed (E_NOTIMPL), operation not allowed in compatibility mode`
- `0x18005fe2c`: `failed (E_NOTIMPL), operation not allowed in compatibility mode`
- `0x18005fd93`: `CWiaItem::CreateChild`
- `0x18005ff92`: `unable to remove new item from tree, possible memory leak!`
- `0x18005ffb4`: `unable to remove new item from tree, possible memory leak!`

## pseudocode

```c
__int64 __fastcall CWiaItem::CreateChild(
        CWiaItem *this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        void **a5)
{
  char ***v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  int ChildAppItem; // edi
  struct CWiaItem *v12; // rcx
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
  CWiaItem *v24; // rsi
  char *v25; // rbx
  void *v26; // rdx
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  char *v30; // rbx
  void *v31; // rdx
  CWiaTree *v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-B8h]
  CWiaItem *v39; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v40[152]; // [rsp+40h] [rbp-98h] BYREF

  v8 = (char ***)WiaTrace_Trace("CWiaItem::CreateChild");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v40, v9, v10, (char **)"CWiaItem::CreateChild", lpMem, v8);
  v39 = 0;
  if ( !a5 || !SysStringLen(a3) || (ChildAppItem = 0, !SysStringLen(a4)) )
    ChildAppItem = -2147467261;
  if ( (unsigned int)CWiaItem::IsCompatMode(this) )
  {
    v13 = (char *)WiaTrace_TraceLog("failed (E_NOTIMPL), operation not allowed in compatibility mode");
    WriteDbgTraceErrorWI("CWiaItem::CreateChild", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v15 = (void **)WiaTrace_Trace("failed (E_NOTIMPL), operation not allowed in compatibility mode");
    WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"CWiaItem::CreateChild", 1, v15);
    ChildAppItem = -2147467263;
LABEL_7:
    v18 = (char *)WiaTrace_TraceLog("error creating generated item");
    WriteDbgTraceErrorWI("CWiaItem::CreateChild", v18);
    WiaTrcLib::Free((WiaTrcLib *)v18, v19);
    v20 = (void **)WiaTrace_Trace("error creating generated item");
    WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"CWiaItem::CreateChild", 1, v20);
    goto LABEL_8;
  }
  if ( ChildAppItem < 0 )
    goto LABEL_7;
  *a5 = 0;
  ChildAppItem = wiasCreateChildAppItem(v12, (__int64)&v39);
  if ( ChildAppItem < 0 )
    goto LABEL_7;
  v24 = v39;
  ChildAppItem = CWiaItem::InitLazyProps(v39);
  if ( ChildAppItem < 0 )
  {
    v30 = (char *)WiaTrace_TraceLog("Error initializing the item properties");
    WriteDbgTraceErrorWI("CWiaItem::CreateChild", v30);
    WiaTrcLib::Free((WiaTrcLib *)v30, v31);
    v27 = (void **)WiaTrace_Trace("Error initializing the item properties");
  }
  else
  {
    ChildAppItem = (**(__int64 (__fastcall ***)(CWiaItem *, GUID *, void **))v24)(v24, &IID_IUnknown, a5);
    if ( ChildAppItem >= 0 )
      goto LABEL_8;
    v25 = (char *)WiaTrace_TraceLog("bad mini driver interface");
    WriteDbgTraceErrorWI("CWiaItem::CreateChild", v25);
    WiaTrcLib::Free((WiaTrcLib *)v25, v26);
    v27 = (void **)WiaTrace_Trace("bad mini driver interface");
  }
  WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"CWiaItem::CreateChild", 1, v27);
  if ( v24 )
  {
    v32 = (CWiaTree *)*((_QWORD *)v24 + 15);
    if ( v32 && (int)CWiaTree::RemoveItemFromFolder(v32, 128) < 0 )
    {
      v33 = (char *)WiaTrace_TraceLog("unable to remove new item from tree, possible memory leak!");
      WriteDbgTraceErrorWI("CWiaItem::CreateChild", v33);
      WiaTrcLib::Free((WiaTrcLib *)v33, v34);
      v35 = (void **)WiaTrace_Trace("unable to remove new item from tree, possible memory leak!");
      WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"CWiaItem::CreateChild", 1, v35);
    }
    CWiaItem::DisconnectAndDelete(v24);
  }
LABEL_8:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v40);
  return (unsigned int)ChildAppItem;
}

```

## disassembly

```asm
0x18005fd7c  push    rbx
0x18005fd7e  push    rbp
0x18005fd7f  push    rsi
0x18005fd80  push    rdi
0x18005fd81  push    r12
0x18005fd83  push    r13
0x18005fd85  push    r14
0x18005fd87  push    r15
0x18005fd89  sub     rsp, 98h
0x18005fd90  mov     rbp, rcx
0x18005fd93  lea     r12, aCwiaitemCreate_1; "CWiaItem::CreateChild"
0x18005fd9a  mov     rcx, r12
0x18005fd9d  mov     rsi, r9
0x18005fda0  mov     rbx, r8
0x18005fda3  mov     r15d, edx
0x18005fda6  call    WiaTrace_Trace
0x18005fdab  mov     r9, r12; char *
0x18005fdae  mov     [rsp+0D8h+var_B0], rax; struct tagWiaTraceData_Type *
0x18005fdb3  lea     rcx, [rsp+0D8h+var_98]; this
0x18005fdb8  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18005fdbd  mov     r14, [rsp+0D8h+arg_20]
0x18005fdc5  mov     [rsp+0D8h+var_A8], 0
0x18005fdce  test    r14, r14
0x18005fdd1  jz      short loc_18005FDEF
0x18005fdd3  mov     rcx, rbx; pbstr
0x18005fdd6  call    cs:__imp_SysStringLen
0x18005fddc  test    eax, eax
0x18005fdde  jz      short loc_18005FDEF
0x18005fde0  mov     rcx, rsi; pbstr
0x18005fde3  xor     edi, edi
0x18005fde5  call    cs:__imp_SysStringLen
0x18005fdeb  test    eax, eax
0x18005fded  jnz     short loc_18005FDF4
0x18005fdef  mov     edi, 80004003h
0x18005fdf4  mov     rcx, rbp; this
0x18005fdf7  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x18005fdfc  mov     r13d, 1
0x18005fe02  test    eax, eax
0x18005fe04  jz      loc_18005FEAB
0x18005fe0a  lea     rcx, aFailedENotimpl; "failed (E_NOTIMPL), operation not allow"...
0x18005fe11  call    WiaTrace_TraceLog
0x18005fe16  mov     rdx, rax; char *
0x18005fe19  mov     rcx, r12; char *
0x18005fe1c  mov     rbx, rax
0x18005fe1f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005fe24  mov     rcx, rbx; this
0x18005fe27  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005fe2c  lea     rcx, aFailedENotimpl; "failed (E_NOTIMPL), operation not allow"...
0x18005fe33  call    WiaTrace_Trace
0x18005fe38  mov     r9d, r13d; int
0x18005fe3b  mov     [rsp+0D8h+lpMem], rax; lpMem
0x18005fe40  mov     r8, r12; int
0x18005fe43  call    WiaTrace_ProcessTrace_Ex
0x18005fe48  mov     edi, 80004001h
0x18005fe4d  lea     rcx, aErrorCreatingG; "error creating generated item"
0x18005fe54  call    WiaTrace_TraceLog
0x18005fe59  mov     rdx, rax; char *
0x18005fe5c  mov     rcx, r12; char *
0x18005fe5f  mov     rbx, rax
0x18005fe62  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005fe67  mov     rcx, rbx; this
0x18005fe6a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005fe6f  lea     rcx, aErrorCreatingG; "error creating generated item"
0x18005fe76  call    WiaTrace_Trace
0x18005fe7b  mov     r9d, r13d; int
0x18005fe7e  mov     [rsp+0D8h+lpMem], rax; lpMem
0x18005fe83  mov     r8, r12; int
0x18005fe86  call    WiaTrace_ProcessTrace_Ex
0x18005fe8b  lea     rcx, [rsp+0D8h+var_98]; this
0x18005fe90  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18005fe95  mov     eax, edi
0x18005fe97  add     rsp, 98h
0x18005fe9e  pop     r15
0x18005fea0  pop     r14
0x18005fea2  pop     r13
0x18005fea4  pop     r12
0x18005fea6  pop     rdi
0x18005fea7  pop     rsi
0x18005fea8  pop     rbp
0x18005fea9  pop     rbx
0x18005feaa  retn
0x18005feab  test    edi, edi
0x18005fead  js      short loc_18005FE4D
0x18005feaf  lea     rax, [rsp+0D8h+var_A8]
0x18005feb4  mov     qword ptr [r14], 0
0x18005febb  mov     r9, rsi
0x18005febe  mov     [rsp+0D8h+lpMem], rax; __int64
0x18005fec3  mov     r8, rbx
0x18005fec6  mov     edx, r15d
0x18005fec9  call    wiasCreateChildAppItem
0x18005fece  mov     edi, eax
0x18005fed0  test    eax, eax
0x18005fed2  js      loc_18005FE4D
0x18005fed8  mov     rsi, [rsp+0D8h+var_A8]
0x18005fedd  mov     rcx, rsi; this
0x18005fee0  call    ?InitLazyProps@CWiaItem@@QEAAJXZ; CWiaItem::InitLazyProps(void)
0x18005fee5  mov     edi, eax
0x18005fee7  test    eax, eax
0x18005fee9  js      short loc_18005FF34
0x18005feeb  mov     rax, [rsi]
0x18005feee  lea     rdx, IID_IUnknown
0x18005fef5  mov     r8, r14
0x18005fef8  mov     rcx, rsi
0x18005fefb  mov     rax, [rax]
0x18005fefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ff03  mov     edi, eax
0x18005ff05  test    eax, eax
0x18005ff07  jns     short loc_18005FE8B
0x18005ff09  lea     rcx, aBadMiniDriverI; "bad mini driver interface"
0x18005ff10  call    WiaTrace_TraceLog
0x18005ff15  mov     rdx, rax; char *
0x18005ff18  mov     rcx, r12; char *
0x18005ff1b  mov     rbx, rax
0x18005ff1e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ff23  mov     rcx, rbx; this
0x18005ff26  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ff2b  lea     rcx, aBadMiniDriverI; "bad mini driver interface"
0x18005ff32  jmp     short loc_18005FF5D
0x18005ff34  lea     rcx, aErrorInitializ; "Error initializing the item properties"
0x18005ff3b  call    WiaTrace_TraceLog
0x18005ff40  mov     rdx, rax; char *
0x18005ff43  mov     rcx, r12; char *
0x18005ff46  mov     rbx, rax
0x18005ff49  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ff4e  mov     rcx, rbx; this
0x18005ff51  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ff56  lea     rcx, aErrorInitializ; "Error initializing the item properties"
0x18005ff5d  call    WiaTrace_Trace
0x18005ff62  mov     r9d, r13d; int
0x18005ff65  mov     [rsp+0D8h+lpMem], rax; lpMem
0x18005ff6a  mov     r8, r12; int
0x18005ff6d  call    WiaTrace_ProcessTrace_Ex
0x18005ff72  test    rsi, rsi
0x18005ff75  jz      loc_18005FE8B
0x18005ff7b  mov     rcx, [rsi+78h]; this
0x18005ff7f  test    rcx, rcx
0x18005ff82  jz      short loc_18005FFD0
0x18005ff84  mov     edx, 80h; int
0x18005ff89  call    ?RemoveItemFromFolder@CWiaTree@@QEAAJJ@Z; CWiaTree::RemoveItemFromFolder(long)
0x18005ff8e  test    eax, eax
0x18005ff90  jns     short loc_18005FFD0
0x18005ff92  lea     rcx, aUnableToRemove; "unable to remove new item from tree, po"...
0x18005ff99  call    WiaTrace_TraceLog
0x18005ff9e  mov     rdx, rax; char *
0x18005ffa1  mov     rcx, r12; char *
0x18005ffa4  mov     rbx, rax
0x18005ffa7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ffac  mov     rcx, rbx; this
0x18005ffaf  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ffb4  lea     rcx, aUnableToRemove; "unable to remove new item from tree, po"...
0x18005ffbb  call    WiaTrace_Trace
0x18005ffc0  mov     r9d, r13d; int
0x18005ffc3  mov     [rsp+0D8h+lpMem], rax; lpMem
0x18005ffc8  mov     r8, r12; int
0x18005ffcb  call    WiaTrace_ProcessTrace_Ex
0x18005ffd0  mov     rcx, rsi; this
0x18005ffd3  call    ?DisconnectAndDelete@CWiaItem@@QEAAXXZ; CWiaItem::DisconnectAndDelete(void)
0x18005ffd8  jmp     loc_18005FE8B
```
