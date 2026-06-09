# CWiaDrvItem::UnlinkFromDrvItem(CWiaItem *)

- ea: `0x180025560`
- end: `0x180025659`
- name: `?UnlinkFromDrvItem@CWiaDrvItem@@UEAAJPEAVCWiaItem@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(CWiaDrvItem *__hidden this, struct CWiaItem *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x18000ac34`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x180025560`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800255d9`
- `KERNEL32!LeaveCriticalSection` at `0x18002563b`
- `KERNEL32!LeaveCriticalSection` at `0x1800255d9`
- `KERNEL32!LeaveCriticalSection` at `0x18002563b`
- `KERNEL32!LocalFree` at `0x1800255cc`
- `KERNEL32!LocalFree` at `0x1800255cc`

## string_xrefs

- `0x180025572`: `CWiaDrvItem::UnlinkFromDrvItem`
- `0x18002557e`: `CWiaDrvItem::UnlinkFromDrvItem`
- `0x1800255f5`: `CWiaDrvItem::UnlinkFromDrvItem`
- `0x180025628`: `CWiaDrvItem::UnlinkFromDrvItem`
- `0x1800255e6`: `CWiaDrvItem::UnlinkFromDrvItem, app item (%p) not found`
- `0x18002560f`: `CWiaDrvItem::UnlinkFromDrvItem, app item (%p) not found`

## pseudocode

```c
__int64 __fastcall CWiaDrvItem::UnlinkFromDrvItem(CWiaDrvItem *this, struct CWiaItem *a2)
{
  char ***v4; // rax
  char *v5; // rdx
  __int64 v6; // r8
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  int v8; // eax
  struct CWiaItem ***v9; // rbx
  int v10; // ebp
  struct CWiaItem **i; // rcx
  struct CWiaItem *v12; // rdx
  struct CWiaItem *v13; // rax
  unsigned int v14; // ebx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-88h]
  _BYTE v22[120]; // [rsp+30h] [rbp-78h] BYREF

  v4 = (char ***)WiaTrace_Trace("CWiaDrvItem::UnlinkFromDrvItem");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v22, v5, v6, (char **)"CWiaDrvItem::UnlinkFromDrvItem", lpMem, v4);
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  v8 = CRIT_SECT::Lock((CWiaDrvItem *)((char *)this + 72));
  v9 = (struct CWiaItem ***)((char *)this + 56);
  v10 = v8;
  for ( i = *v9; i != (struct CWiaItem **)v9 && i; i = (struct CWiaItem **)*i )
  {
    v12 = *i;
    if ( i[2] == a2 )
    {
      v13 = i[1];
      *(_QWORD *)v13 = v12;
      *((_QWORD *)v12 + 1) = v13;
      LocalFree(i);
      if ( v10 )
        LeaveCriticalSection(v7);
      v14 = 0;
      goto LABEL_11;
    }
  }
  v15 = (char *)WiaTrace_TraceLog("CWiaDrvItem::UnlinkFromDrvItem, app item (%p) not found");
  WriteDbgTraceErrorWI("CWiaDrvItem::UnlinkFromDrvItem", v15);
  WiaTrcLib::Free((WiaTrcLib *)v15, v16);
  v17 = (void **)WiaTrace_Trace("CWiaDrvItem::UnlinkFromDrvItem, app item (%p) not found", a2);
  v14 = 1;
  WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"CWiaDrvItem::UnlinkFromDrvItem", 1, v17);
  if ( v10 )
    LeaveCriticalSection(v7);
LABEL_11:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v22);
  return v14;
}

```

## disassembly

```asm
0x180025560  push    rbx
0x180025562  push    rbp
0x180025563  push    rsi
0x180025564  push    rdi
0x180025565  sub     rsp, 88h
0x18002556c  mov     rbx, rcx
0x18002556f  mov     rsi, rdx
0x180025572  lea     rcx, aCwiadrvitemUnl_1; "CWiaDrvItem::UnlinkFromDrvItem"
0x180025579  call    WiaTrace_Trace
0x18002557e  lea     r9, aCwiadrvitemUnl_1; "CWiaDrvItem::UnlinkFromDrvItem"
0x180025585  mov     [rsp+0A8h+var_80], rax; struct tagWiaTraceData_Type *
0x18002558a  lea     rcx, [rsp+0A8h+var_78]; this
0x18002558f  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180025594  lea     rdi, [rbx+48h]
0x180025598  mov     rcx, rdi; this
0x18002559b  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x1800255a0  add     rbx, 38h ; '8'
0x1800255a4  mov     ebp, eax
0x1800255a6  mov     rcx, [rbx]; hMem
0x1800255a9  cmp     rcx, rbx
0x1800255ac  jz      short loc_1800255E3
0x1800255ae  test    rcx, rcx
0x1800255b1  jz      short loc_1800255E3
0x1800255b3  mov     rdx, [rcx]
0x1800255b6  cmp     [rcx+10h], rsi
0x1800255ba  jz      short loc_1800255C1
0x1800255bc  mov     rcx, rdx
0x1800255bf  jmp     short loc_1800255A9
0x1800255c1  mov     rax, [rcx+8]
0x1800255c5  mov     [rax], rdx
0x1800255c8  mov     [rdx+8], rax
0x1800255cc  call    cs:__imp_LocalFree
0x1800255d2  test    ebp, ebp
0x1800255d4  jz      short loc_1800255DF
0x1800255d6  mov     rcx, rdi; lpCriticalSection
0x1800255d9  call    cs:__imp_LeaveCriticalSection
0x1800255df  xor     ebx, ebx
0x1800255e1  jmp     short loc_180025641
0x1800255e3  mov     rdx, rsi
0x1800255e6  lea     rcx, aCwiadrvitemUnl; "CWiaDrvItem::UnlinkFromDrvItem, app ite"...
0x1800255ed  call    WiaTrace_TraceLog
0x1800255f2  mov     rdx, rax; char *
0x1800255f5  lea     rcx, aCwiadrvitemUnl_1; "CWiaDrvItem::UnlinkFromDrvItem"
0x1800255fc  mov     rbx, rax
0x1800255ff  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180025604  mov     rcx, rbx; this
0x180025607  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002560c  mov     rdx, rsi
0x18002560f  lea     rcx, aCwiadrvitemUnl; "CWiaDrvItem::UnlinkFromDrvItem, app ite"...
0x180025616  call    WiaTrace_Trace
0x18002561b  mov     ebx, 1
0x180025620  mov     [rsp+0A8h+lpMem], rax; lpMem
0x180025625  mov     r9d, ebx; int
0x180025628  lea     r8, aCwiadrvitemUnl_1; "CWiaDrvItem::UnlinkFromDrvItem"
0x18002562f  call    WiaTrace_ProcessTrace_Ex
0x180025634  test    ebp, ebp
0x180025636  jz      short loc_180025641
0x180025638  mov     rcx, rdi; lpCriticalSection
0x18002563b  call    cs:__imp_LeaveCriticalSection
0x180025641  lea     rcx, [rsp+0A8h+var_78]; this
0x180025646  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18002564b  mov     eax, ebx
0x18002564d  add     rsp, 88h
0x180025654  pop     rdi
0x180025655  pop     rsi
0x180025656  pop     rbp
0x180025657  pop     rbx
0x180025658  retn
```
