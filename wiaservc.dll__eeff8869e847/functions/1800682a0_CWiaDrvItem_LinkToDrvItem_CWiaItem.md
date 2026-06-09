# CWiaDrvItem::LinkToDrvItem(CWiaItem *)

- ea: `0x1800682a0`
- end: `0x1800683dd`
- name: `?LinkToDrvItem@CWiaDrvItem@@UEAAJPEAVCWiaItem@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(CWiaDrvItem *__hidden this, struct CWiaItem *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000ac34`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x1800682a0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800683bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800683bb`
- `KERNEL32!LocalAlloc` at `0x1800682ea`
- `KERNEL32!LocalAlloc` at `0x1800682ea`

## string_xrefs

- `0x1800682b3`: `CWiaDrvItem::LinkToDrvItem`
- `0x18006831d`: `A WIA item is deleted, no longer available and cannot be linked to driver item (%p)`
- `0x180068342`: `A WIA item is deleted, no longer available and cannot be linked to driver item (%p)`
- `0x18006836f`: `CWiaDrvItem::LinkToDrvItem failed with 0x%08X`
- `0x180068393`: `CWiaDrvItem::LinkToDrvItem failed with 0x%08X`

## pseudocode

```c
__int64 __fastcall CWiaDrvItem::LinkToDrvItem(CWiaDrvItem *this, struct CWiaItem *a2)
{
  char ***v4; // rax
  char *v5; // rdx
  __int64 v6; // r8
  int v7; // r14d
  _QWORD *v8; // rax
  unsigned int v9; // edi
  __int64 v10; // rcx
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-98h]
  _BYTE v23[136]; // [rsp+30h] [rbp-88h] BYREF

  v4 = (char ***)WiaTrace_Trace("CWiaDrvItem::LinkToDrvItem");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v23, v5, v6, (char **)"CWiaDrvItem::LinkToDrvItem", lpMem, v4);
  v7 = CRIT_SECT::Lock((CWiaDrvItem *)((char *)this + 72));
  v8 = LocalAlloc(0, 0x18u);
  if ( v8 )
  {
    v8[2] = a2;
    if ( a2 )
    {
      v9 = 0;
      v10 = *((_QWORD *)this + 7);
      *v8 = v10;
      v8[1] = (char *)this + 56;
      *(_QWORD *)(v10 + 8) = v8;
      *((_QWORD *)this + 7) = v8;
      goto LABEL_7;
    }
    v11 = (char *)WiaTrace_TraceLog("A WIA item is deleted, no longer available and cannot be linked to driver item (%p)");
    WriteDbgTraceErrorWI("CWiaDrvItem::LinkToDrvItem", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v13 = (void **)WiaTrace_Trace(
                     "A WIA item is deleted, no longer available and cannot be linked to driver item (%p)",
                     this);
    WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CWiaDrvItem::LinkToDrvItem", 1, v13);
    v9 = -2147024809;
  }
  else
  {
    v9 = -2147024882;
  }
  v16 = (char *)WiaTrace_TraceLog("CWiaDrvItem::LinkToDrvItem failed with 0x%08X");
  WriteDbgTraceErrorWI("CWiaDrvItem::LinkToDrvItem", v16);
  WiaTrcLib::Free((WiaTrcLib *)v16, v17);
  v18 = (void **)WiaTrace_Trace("CWiaDrvItem::LinkToDrvItem failed with 0x%08X", v9);
  WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"CWiaDrvItem::LinkToDrvItem", 1, v18);
LABEL_7:
  if ( v7 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v23);
  return v9;
}

```

## disassembly

```asm
0x1800682a0  push    rbx
0x1800682a2  push    rbp
0x1800682a3  push    rsi
0x1800682a4  push    rdi
0x1800682a5  push    r14
0x1800682a7  push    r15
0x1800682a9  sub     rsp, 88h
0x1800682b0  mov     rsi, rcx
0x1800682b3  lea     r15, aCwiadrvitemLin_0; "CWiaDrvItem::LinkToDrvItem"
0x1800682ba  mov     rcx, r15
0x1800682bd  mov     rbx, rdx
0x1800682c0  call    WiaTrace_Trace
0x1800682c5  mov     r9, r15; char *
0x1800682c8  mov     [rsp+0B8h+var_90], rax; struct tagWiaTraceData_Type *
0x1800682cd  lea     rcx, [rsp+0B8h+var_88]; this
0x1800682d2  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800682d7  lea     rcx, [rsi+48h]; this
0x1800682db  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x1800682e0  mov     edx, 18h; uBytes
0x1800682e5  xor     ecx, ecx; uFlags
0x1800682e7  mov     r14d, eax
0x1800682ea  call    cs:__imp_LocalAlloc
0x1800682f0  test    rax, rax
0x1800682f3  jz      short loc_180068368
0x1800682f5  mov     [rax+10h], rbx
0x1800682f9  test    rbx, rbx
0x1800682fc  jz      short loc_18006831A
0x1800682fe  lea     rdx, [rsi+38h]
0x180068302  xor     edi, edi
0x180068304  mov     rcx, [rdx]
0x180068307  mov     [rax], rcx
0x18006830a  mov     [rax+8], rdx
0x18006830e  mov     [rcx+8], rax
0x180068312  mov     [rdx], rax
0x180068315  jmp     loc_1800683B2
0x18006831a  mov     rdx, rsi
0x18006831d  lea     rcx, aAWiaItemIsDele; "A WIA item is deleted, no longer availa"...
0x180068324  call    WiaTrace_TraceLog
0x180068329  mov     rdx, rax; char *
0x18006832c  mov     rcx, r15; char *
0x18006832f  mov     rbx, rax
0x180068332  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180068337  mov     rcx, rbx; this
0x18006833a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006833f  mov     rdx, rsi
0x180068342  lea     rcx, aAWiaItemIsDele; "A WIA item is deleted, no longer availa"...
0x180068349  call    WiaTrace_Trace
0x18006834e  mov     r9d, 1; int
0x180068354  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180068359  mov     r8, r15; int
0x18006835c  call    WiaTrace_ProcessTrace_Ex
0x180068361  mov     edi, 80070057h
0x180068366  jmp     short loc_18006836D
0x180068368  mov     edi, 8007000Eh
0x18006836d  mov     edx, edi
0x18006836f  lea     rcx, aCwiadrvitemLin; "CWiaDrvItem::LinkToDrvItem failed with "...
0x180068376  call    WiaTrace_TraceLog
0x18006837b  mov     rdx, rax; char *
0x18006837e  mov     rcx, r15; char *
0x180068381  mov     rbx, rax
0x180068384  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180068389  mov     rcx, rbx; this
0x18006838c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180068391  mov     edx, edi
0x180068393  lea     rcx, aCwiadrvitemLin; "CWiaDrvItem::LinkToDrvItem failed with "...
0x18006839a  call    WiaTrace_Trace
0x18006839f  mov     r9d, 1; int
0x1800683a5  mov     [rsp+0B8h+lpMem], rax; lpMem
0x1800683aa  mov     r8, r15; int
0x1800683ad  call    WiaTrace_ProcessTrace_Ex
0x1800683b2  test    r14d, r14d
0x1800683b5  jz      short loc_1800683C1
0x1800683b7  lea     rcx, [rsi+48h]; lpCriticalSection
0x1800683bb  call    cs:__imp_LeaveCriticalSection
0x1800683c1  lea     rcx, [rsp+0B8h+var_88]; this
0x1800683c6  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800683cb  mov     eax, edi
0x1800683cd  add     rsp, 88h
0x1800683d4  pop     r15
0x1800683d6  pop     r14
0x1800683d8  pop     rdi
0x1800683d9  pop     rsi
0x1800683da  pop     rbp
0x1800683db  pop     rbx
0x1800683dc  retn
```
