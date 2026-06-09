# wiasCreateDrvItem

- ea: `0x18003f970`
- end: `0x18003fc59`
- name: `wiasCreateDrvItem`
- size: `745`
- prototype: `__int64 __fastcall(int, unsigned __int16 *, unsigned __int16 *, struct IWiaMiniDrv *, int, unsigned __int8 **, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x18002ec74`
- `0x180033884`
- `0x18003d324`
- `0x18003f970`
- `0x180068088`
- `0x180078010`

## string_xrefs

- `0x18003f987`: `::wiasCreateDrvItem`
- `0x18003f999`: `wiasCreateDrvItem`
- `0x18003f9b8`: `wiasCreateDrvItem, bad object flags`
- `0x18003f9da`: `wiasCreateDrvItem, bad object flags`
- `0x18003fa08`: `wiasCreateDrvItem, invalid bstrItemName pointer`
- `0x18003fa2a`: `wiasCreateDrvItem, invalid bstrItemName pointer`
- `0x18003fa58`: `wiasCreateDrvItem, invalid bstrFullItemName pointer`
- `0x18003fa7a`: `wiasCreateDrvItem, invalid bstrFullItemName pointer`
- `0x18003fa88`: `wiasCreateDrvItem, invalid pIMiniDrv pointer`
- `0x18003faaa`: `wiasCreateDrvItem, invalid pIMiniDrv pointer`
- `0x18003fac1`: `wiasCreateDrvItem, invalid ppIWiaItemControl parameter`
- `0x18003fae3`: `wiasCreateDrvItem, invalid ppIWiaItemControl parameter`
- `0x18003fbac`: `wiasCreateDrvItem, QI for IID_IWiaDrvItem failed`
- `0x18003fbce`: `wiasCreateDrvItem, QI for IID_IWiaDrvItem failed`
- `0x18003fbf6`: `wiasCreateDrvItem, out of memory!`
- `0x18003fc18`: `wiasCreateDrvItem, out of memory!`

## pseudocode

```c
__int64 __fastcall wiasCreateDrvItem(
        int a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IWiaMiniDrv *a4,
        int a5,
        unsigned __int8 **a6,
        __int64 a7)
{
  char ***v11; // rax
  char *v12; // rdx
  __int64 v13; // r8
  char *v14; // rbx
  void *v15; // rdx
  void **v16; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  int v19; // edi
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  char *v25; // rbx
  void *v26; // rdx
  char *v27; // rbx
  void *v28; // rdx
  char *v29; // rbx
  void *v30; // rdx
  _QWORD *v31; // rbx
  unsigned int v32; // edx
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  char *v38; // rbx
  void *v39; // rdx
  void **v40; // rax
  void *v41; // rdx
  __int64 v42; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-A8h]
  _BYTE v45[136]; // [rsp+40h] [rbp-88h] BYREF

  v11 = (char ***)WiaTrace_Trace("::wiasCreateDrvItem");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v45, v12, v13, (char **)"wiasCreateDrvItem", lpMem, v11);
  if ( (a1 & 6) == 0 )
  {
    v14 = (char *)WiaTrace_TraceLog("wiasCreateDrvItem, bad object flags");
    WriteDbgTraceErrorWI("wiasCreateDrvItem", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    v16 = (void **)WiaTrace_Trace("wiasCreateDrvItem, bad object flags");
    WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"wiasCreateDrvItem", 1, v16);
    v19 = -2147024809;
    goto LABEL_18;
  }
  if ( !a2 )
  {
    v20 = (char *)WiaTrace_TraceLog("wiasCreateDrvItem, invalid bstrItemName pointer");
    WriteDbgTraceErrorWI("wiasCreateDrvItem", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v22 = (void **)WiaTrace_Trace("wiasCreateDrvItem, invalid bstrItemName pointer");
LABEL_5:
    WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"wiasCreateDrvItem", 1, v22);
    v19 = -2147467261;
    goto LABEL_18;
  }
  if ( !a3 )
  {
    v25 = (char *)WiaTrace_TraceLog("wiasCreateDrvItem, invalid bstrFullItemName pointer");
    WriteDbgTraceErrorWI("wiasCreateDrvItem", v25);
    WiaTrcLib::Free((WiaTrcLib *)v25, v26);
    v22 = (void **)WiaTrace_Trace("wiasCreateDrvItem, invalid bstrFullItemName pointer");
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v27 = (char *)WiaTrace_TraceLog("wiasCreateDrvItem, invalid pIMiniDrv pointer");
    WriteDbgTraceErrorWI("wiasCreateDrvItem", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v22 = (void **)WiaTrace_Trace("wiasCreateDrvItem, invalid pIMiniDrv pointer");
    goto LABEL_5;
  }
  if ( !a7 )
  {
    v29 = (char *)WiaTrace_TraceLog("wiasCreateDrvItem, invalid ppIWiaItemControl parameter");
    WriteDbgTraceErrorWI("wiasCreateDrvItem", v29);
    WiaTrcLib::Free((WiaTrcLib *)v29, v30);
    v22 = (void **)WiaTrace_Trace("wiasCreateDrvItem, invalid ppIWiaItemControl parameter");
    goto LABEL_5;
  }
  v31 = operator new(0x78u);
  if ( v31 )
  {
    *v31 = &CWiaDrvItem::`vftable';
    CRIT_SECT::CRIT_SECT((CRIT_SECT *)(v31 + 9));
    v31[8] = v31 + 7;
    v31[7] = v31 + 7;
    *((_DWORD *)v31 + 2) = 1147234647;
    *((_DWORD *)v31 + 10) = 0;
    v31[2] = 0;
    v31[3] = 0;
    v31[6] = 0;
    v31[4] = 0;
    v19 = CWiaDrvItem::Initialize((CWiaDrvItem *)v31, a1, a2, a3, a4, a5, a6);
    if ( v19 )
    {
      CWiaDrvItem::`scalar deleting destructor'((CWiaDrvItem *)v31, v32);
    }
    else
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64))*v31)(v31, &IID_IWiaDrvItem, a7);
      if ( v19 < 0 )
      {
        v33 = (char *)WiaTrace_TraceLog("wiasCreateDrvItem, QI for IID_IWiaDrvItem failed");
        WriteDbgTraceErrorWI("wiasCreateDrvItem", v33);
        WiaTrcLib::Free((WiaTrcLib *)v33, v34);
        v35 = (void **)WiaTrace_Trace("wiasCreateDrvItem, QI for IID_IWiaDrvItem failed");
        WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"wiasCreateDrvItem", 1, v35);
      }
    }
  }
  else
  {
    v38 = (char *)WiaTrace_TraceLog("wiasCreateDrvItem, out of memory!");
    WriteDbgTraceErrorWI("wiasCreateDrvItem", v38);
    WiaTrcLib::Free((WiaTrcLib *)v38, v39);
    v40 = (void **)WiaTrace_Trace("wiasCreateDrvItem, out of memory!");
    WiaTrace_ProcessTrace_Ex(v42, v41, (void *)"wiasCreateDrvItem", 1, v40);
    v19 = -2147024882;
  }
LABEL_18:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v45);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18003f970  push    rbx
0x18003f972  push    rbp
0x18003f973  push    rdi
0x18003f974  push    r13
0x18003f976  push    r14
0x18003f978  push    r15
0x18003f97a  sub     rsp, 98h
0x18003f981  mov     r15d, ecx
0x18003f984  mov     rdi, r9
0x18003f987  lea     rcx, aWiascreatedrvi_3; "::wiasCreateDrvItem"
0x18003f98e  mov     rbp, r8
0x18003f991  mov     r14, rdx
0x18003f994  call    WiaTrace_Trace
0x18003f999  lea     r13, aWiascreatedrvi_6; "wiasCreateDrvItem"
0x18003f9a0  mov     [rsp+0C8h+var_A0], rax; struct tagWiaTraceData_Type *
0x18003f9a5  mov     r9, r13; char *
0x18003f9a8  lea     rcx, [rsp+0C8h+var_88]; this
0x18003f9ad  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18003f9b2  test    r15b, 6
0x18003f9b6  jnz     short loc_18003FA03
0x18003f9b8  lea     rcx, aWiascreatedrvi_2; "wiasCreateDrvItem, bad object flags"
0x18003f9bf  call    WiaTrace_TraceLog
0x18003f9c4  mov     rdx, rax; char *
0x18003f9c7  mov     rcx, r13; char *
0x18003f9ca  mov     rbx, rax
0x18003f9cd  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003f9d2  mov     rcx, rbx; this
0x18003f9d5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f9da  lea     rcx, aWiascreatedrvi_2; "wiasCreateDrvItem, bad object flags"
0x18003f9e1  call    WiaTrace_Trace
0x18003f9e6  mov     r9d, 1; int
0x18003f9ec  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18003f9f1  mov     r8, r13; int
0x18003f9f4  call    WiaTrace_ProcessTrace_Ex
0x18003f9f9  mov     edi, 80070057h
0x18003f9fe  jmp     loc_18003FC3C
0x18003fa03  test    r14, r14
0x18003fa06  jnz     short loc_18003FA53
0x18003fa08  lea     rcx, aWiascreatedrvi_8; "wiasCreateDrvItem, invalid bstrItemName"...
0x18003fa0f  call    WiaTrace_TraceLog
0x18003fa14  mov     rdx, rax; char *
0x18003fa17  mov     rcx, r13; char *
0x18003fa1a  mov     rbx, rax
0x18003fa1d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fa22  mov     rcx, rbx; this
0x18003fa25  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fa2a  lea     rcx, aWiascreatedrvi_8; "wiasCreateDrvItem, invalid bstrItemName"...
0x18003fa31  call    WiaTrace_Trace
0x18003fa36  mov     r9d, 1; int
0x18003fa3c  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18003fa41  mov     r8, r13; int
0x18003fa44  call    WiaTrace_ProcessTrace_Ex
0x18003fa49  mov     edi, 80004003h
0x18003fa4e  jmp     loc_18003FC3C
0x18003fa53  test    rbp, rbp
0x18003fa56  jnz     short loc_18003FA83
0x18003fa58  lea     rcx, aWiascreatedrvi_5; "wiasCreateDrvItem, invalid bstrFullItem"...
0x18003fa5f  call    WiaTrace_TraceLog
0x18003fa64  mov     rdx, rax; char *
0x18003fa67  mov     rcx, r13; char *
0x18003fa6a  mov     rbx, rax
0x18003fa6d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fa72  mov     rcx, rbx; this
0x18003fa75  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fa7a  lea     rcx, aWiascreatedrvi_5; "wiasCreateDrvItem, invalid bstrFullItem"...
0x18003fa81  jmp     short loc_18003FA31
0x18003fa83  test    rdi, rdi
0x18003fa86  jnz     short loc_18003FAB6
0x18003fa88  lea     rcx, aWiascreatedrvi_4; "wiasCreateDrvItem, invalid pIMiniDrv po"...
0x18003fa8f  call    WiaTrace_TraceLog
0x18003fa94  mov     rdx, rax; char *
0x18003fa97  mov     rcx, r13; char *
0x18003fa9a  mov     rbx, rax
0x18003fa9d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003faa2  mov     rcx, rbx; this
0x18003faa5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003faaa  lea     rcx, aWiascreatedrvi_4; "wiasCreateDrvItem, invalid pIMiniDrv po"...
0x18003fab1  jmp     loc_18003FA31
0x18003fab6  cmp     [rsp+0C8h+arg_30], 0
0x18003fabf  jnz     short loc_18003FAEF
0x18003fac1  lea     rcx, aWiascreatedrvi_0; "wiasCreateDrvItem, invalid ppIWiaItemCo"...
0x18003fac8  call    WiaTrace_TraceLog
0x18003facd  mov     rdx, rax; char *
0x18003fad0  mov     rcx, r13; char *
0x18003fad3  mov     rbx, rax
0x18003fad6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fadb  mov     rcx, rbx; this
0x18003fade  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fae3  lea     rcx, aWiascreatedrvi_0; "wiasCreateDrvItem, invalid ppIWiaItemCo"...
0x18003faea  jmp     loc_18003FA31
0x18003faef  mov     ecx, 78h ; 'x'; Size
0x18003faf4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003faf9  mov     rbx, rax
0x18003fafc  test    rax, rax
0x18003faff  jz      loc_18003FBF6
0x18003fb05  lea     rax, ??_7CWiaDrvItem@@6B@; const CWiaDrvItem::`vftable'
0x18003fb0c  lea     rcx, [rbx+48h]; this
0x18003fb10  mov     [rbx], rax
0x18003fb13  call    ??0CRIT_SECT@@QEAA@XZ; CRIT_SECT::CRIT_SECT(void)
0x18003fb18  mov     rax, [rsp+0C8h+arg_28]
0x18003fb20  lea     rcx, [rbx+38h]
0x18003fb24  mov     [rsp+0C8h+var_98], rax; unsigned __int8 **
0x18003fb29  mov     r9, rbp; unsigned __int16 *
0x18003fb2c  mov     eax, [rsp+0C8h+arg_20]
0x18003fb33  mov     r8, r14; unsigned __int16 *
0x18003fb36  mov     [rbx+40h], rcx
0x18003fb3a  mov     edx, r15d; int
0x18003fb3d  mov     [rcx], rcx
0x18003fb40  mov     rcx, rbx; this
0x18003fb43  mov     dword ptr [rsp+0C8h+var_A0], eax; int
0x18003fb47  mov     [rsp+0C8h+lpMem], rdi; struct IWiaMiniDrv *
0x18003fb4c  mov     dword ptr [rbx+8], 44616957h
0x18003fb53  mov     dword ptr [rbx+28h], 0
0x18003fb5a  mov     qword ptr [rbx+10h], 0
0x18003fb62  mov     qword ptr [rbx+18h], 0
0x18003fb6a  mov     qword ptr [rbx+30h], 0
0x18003fb72  mov     qword ptr [rbx+20h], 0
0x18003fb7a  call    ?Initialize@CWiaDrvItem@@QEAAJJPEAG0PEAUIWiaMiniDrv@@JPEAPEAE@Z; CWiaDrvItem::Initialize(long,ushort *,ushort *,IWiaMiniDrv *,long,uchar * *)
0x18003fb7f  mov     edi, eax
0x18003fb81  mov     rcx, rbx; this
0x18003fb84  test    eax, eax
0x18003fb86  jnz     short loc_18003FBEF
0x18003fb88  mov     rax, [rbx]
0x18003fb8b  lea     rdx, IID_IWiaDrvItem
0x18003fb92  mov     r8, [rsp+0C8h+arg_30]
0x18003fb9a  mov     rax, [rax]
0x18003fb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fba2  mov     edi, eax
0x18003fba4  test    eax, eax
0x18003fba6  jns     loc_18003FC3C
0x18003fbac  lea     rcx, aWiascreatedrvi_1; "wiasCreateDrvItem, QI for IID_IWiaDrvIt"...
0x18003fbb3  call    WiaTrace_TraceLog
0x18003fbb8  mov     rdx, rax; char *
0x18003fbbb  mov     rcx, r13; char *
0x18003fbbe  mov     rbx, rax
0x18003fbc1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fbc6  mov     rcx, rbx; this
0x18003fbc9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fbce  lea     rcx, aWiascreatedrvi_1; "wiasCreateDrvItem, QI for IID_IWiaDrvIt"...
0x18003fbd5  call    WiaTrace_Trace
0x18003fbda  mov     r9d, 1; int
0x18003fbe0  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18003fbe5  mov     r8, r13; int
0x18003fbe8  call    WiaTrace_ProcessTrace_Ex
0x18003fbed  jmp     short loc_18003FC3C
0x18003fbef  call    ??_GCWiaDrvItem@@QEAAPEAXI@Z; CWiaDrvItem::`scalar deleting destructor'(uint)
0x18003fbf4  jmp     short loc_18003FC3C
0x18003fbf6  lea     rcx, aWiascreatedrvi_7; "wiasCreateDrvItem, out of memory!"
0x18003fbfd  call    WiaTrace_TraceLog
0x18003fc02  mov     rdx, rax; char *
0x18003fc05  mov     rcx, r13; char *
0x18003fc08  mov     rbx, rax
0x18003fc0b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fc10  mov     rcx, rbx; this
0x18003fc13  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fc18  lea     rcx, aWiascreatedrvi_7; "wiasCreateDrvItem, out of memory!"
0x18003fc1f  call    WiaTrace_Trace
0x18003fc24  mov     r9d, 1; int
0x18003fc2a  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18003fc2f  mov     r8, r13; int
0x18003fc32  call    WiaTrace_ProcessTrace_Ex
0x18003fc37  mov     edi, 8007000Eh
0x18003fc3c  lea     rcx, [rsp+0C8h+var_88]; this
0x18003fc41  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18003fc46  mov     eax, edi
0x18003fc48  add     rsp, 98h
0x18003fc4f  pop     r15
0x18003fc51  pop     r14
0x18003fc53  pop     r13
0x18003fc55  pop     rdi
0x18003fc56  pop     rbp
0x18003fc57  pop     rbx
0x18003fc58  retn
```
