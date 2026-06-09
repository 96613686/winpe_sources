# CWiaItem::CreateChildItem(long,ushort *,ushort *,IWiaItem * *)

- ea: `0x180060350`
- end: `0x180060519`
- name: `?CreateChildItem@CWiaItem@@UEAAJJPEAG0PEAPEAUIWiaItem@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, int, unsigned __int16 *, unsigned __int16 *, struct IWiaItem **)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x18005fd7c`
- `0x180060350`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180060432`
- `OLEAUT32!__imp_SysStringLen` at `0x18006043f`
- `OLEAUT32!__imp_SysStringLen` at `0x180060432`
- `OLEAUT32!__imp_SysStringLen` at `0x18006043f`

## string_xrefs

- `0x1800603ae`: `failed (E_NOTIMPL), operation not allowed in compatibility mode`
- `0x1800603d0`: `failed (E_NOTIMPL), operation not allowed in compatibility mode`
- `0x1800604b1`: `Item (%p) is app owned and will not be released by the service`
- `0x1800604da`: `Item (%p) is app owned and will not be released by the service`
- `0x180060366`: `CWiaItem::IWiaItem::CreateChildItem`
- `0x180060378`: `CWiaItem::CreateChildItem`

## pseudocode

```c
__int64 __fastcall CWiaItem::CreateChildItem(
        CWiaItem *this,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IWiaItem **a5)
{
  struct tagWiaTraceData_Type *v9; // rax
  char *v10; // rdx
  unsigned int v11; // r8d
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  int v19; // edi
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-A8h]
  void *v27; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v28[136]; // [rsp+40h] [rbp-88h] BYREF

  v9 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::IWiaItem::CreateChildItem");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v28, v10, v11, "CWiaItem::CreateChildItem", lpMem, v9);
  v27 = 0;
  if ( (unsigned int)CWiaItem::IsCompatMode(this) )
  {
    v12 = (char *)WiaTrace_TraceLog("failed (E_NOTIMPL), operation not allowed in compatibility mode");
    WriteDbgTraceErrorWI("CWiaItem::CreateChildItem", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("failed (E_NOTIMPL), operation not allowed in compatibility mode");
LABEL_5:
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"CWiaItem::CreateChildItem", 1, v14);
    v19 = -2147467263;
    goto LABEL_12;
  }
  if ( *((_DWORD *)this + 56) != 1 )
  {
    v17 = (char *)WiaTrace_TraceLog("E_NOTIMPL");
    WriteDbgTraceErrorWI("CWiaItem::CreateChildItem", v17);
    WiaTrcLib::Free((WiaTrcLib *)v17, v18);
    v14 = (void **)WiaTrace_Trace("E_NOTIMPL");
    goto LABEL_5;
  }
  if ( a5 && SysStringLen(a3) && SysStringLen(a4) )
  {
    v19 = CWiaItem::CreateChild(this, a2, a3, a4, &v27);
    if ( v19 >= 0 )
      (**(void (__fastcall ***)(void *, GUID *, struct IWiaItem **))v27)(v27, &IID_IWiaItem, a5);
  }
  else
  {
    v19 = -2147024809;
  }
LABEL_12:
  if ( v27 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v19 >= 0 )
  {
    v20 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "Item (%p) is app owned and will not be released by the service",
                    *a5);
    WriteDbgTraceInfoWI("CWiaItem::CreateChildItem", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v22 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "Item (%p) is app owned and will not be released by the service",
                     *a5);
    WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"CWiaItem::CreateChildItem", 4, v22);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v28);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180060350  push    rbx
0x180060352  push    rbp
0x180060353  push    rsi
0x180060354  push    rdi
0x180060355  push    r14
0x180060357  push    r15
0x180060359  sub     rsp, 98h
0x180060360  mov     rbx, rcx
0x180060363  mov     rdi, r9
0x180060366  lea     rcx, aCwiaitemIwiait_10; "CWiaItem::IWiaItem::CreateChildItem"
0x18006036d  mov     rbp, r8
0x180060370  mov     r14d, edx
0x180060373  call    WiaTrace_Trace
0x180060378  lea     r15, aCwiaitemCreate; "CWiaItem::CreateChildItem"
0x18006037f  mov     [rsp+0C8h+var_A0], rax; struct tagWiaTraceData_Type *
0x180060384  mov     r9, r15; char *
0x180060387  lea     rcx, [rsp+0C8h+var_88]; this
0x18006038c  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180060391  mov     rcx, rbx; this
0x180060394  mov     [rsp+0C8h+var_98], 0
0x18006039d  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x1800603a2  mov     rsi, [rsp+0C8h+arg_20]
0x1800603aa  test    eax, eax
0x1800603ac  jz      short loc_1800603D9
0x1800603ae  lea     rcx, aFailedENotimpl; "failed (E_NOTIMPL), operation not allow"...
0x1800603b5  call    WiaTrace_TraceLog
0x1800603ba  mov     rdx, rax; char *
0x1800603bd  mov     rcx, r15; char *
0x1800603c0  mov     rbx, rax
0x1800603c3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800603c8  mov     rcx, rbx; this
0x1800603cb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800603d0  lea     rcx, aFailedENotimpl; "failed (E_NOTIMPL), operation not allow"...
0x1800603d7  jmp     short loc_18006040B
0x1800603d9  cmp     dword ptr [rbx+0E0h], 1
0x1800603e0  jz      short loc_18006042A
0x1800603e2  lea     rcx, aENotimpl; "E_NOTIMPL"
0x1800603e9  call    WiaTrace_TraceLog
0x1800603ee  mov     rdx, rax; char *
0x1800603f1  mov     rcx, r15; char *
0x1800603f4  mov     rbx, rax
0x1800603f7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800603fc  mov     rcx, rbx; this
0x1800603ff  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180060404  lea     rcx, aENotimpl; "E_NOTIMPL"
0x18006040b  call    WiaTrace_Trace
0x180060410  mov     r9d, 1; int
0x180060416  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18006041b  mov     r8, r15; int
0x18006041e  call    WiaTrace_ProcessTrace_Ex
0x180060423  mov     edi, 80004001h
0x180060428  jmp     short loc_18006048B
0x18006042a  test    rsi, rsi
0x18006042d  jz      short loc_180060486
0x18006042f  mov     rcx, rbp; pbstr
0x180060432  call    cs:__imp_SysStringLen
0x180060438  test    eax, eax
0x18006043a  jz      short loc_180060486
0x18006043c  mov     rcx, rdi; pbstr
0x18006043f  call    cs:__imp_SysStringLen
0x180060445  test    eax, eax
0x180060447  jz      short loc_180060486
0x180060449  lea     rax, [rsp+0C8h+var_98]
0x18006044e  mov     r9, rdi; unsigned __int16 *
0x180060451  mov     r8, rbp; unsigned __int16 *
0x180060454  mov     [rsp+0C8h+lpMem], rax; void **
0x180060459  mov     edx, r14d; int
0x18006045c  mov     rcx, rbx; this
0x18006045f  call    ?CreateChild@CWiaItem@@AEAAJJPEAG0PEAPEAX@Z; CWiaItem::CreateChild(long,ushort *,ushort *,void * *)
0x180060464  mov     edi, eax
0x180060466  test    eax, eax
0x180060468  js      short loc_18006048B
0x18006046a  mov     rcx, [rsp+0C8h+var_98]
0x18006046f  mov     r8, rsi
0x180060472  mov     rdx, [rcx]
0x180060475  mov     rax, [rdx]
0x180060478  lea     rdx, IID_IWiaItem
0x18006047f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060484  jmp     short loc_18006048B
0x180060486  mov     edi, 80070057h
0x18006048b  mov     rcx, [rsp+0C8h+var_98]
0x180060490  test    rcx, rcx
0x180060493  jz      short loc_1800604AA
0x180060495  mov     rax, [rcx]
0x180060498  mov     rax, [rax+10h]
0x18006049c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604a1  mov     [rsp+0C8h+var_98], 0
0x1800604aa  test    edi, edi
0x1800604ac  js      short loc_1800604FD
0x1800604ae  mov     r9, [rsi]
0x1800604b1  lea     r8, aItemPIsAppOwne; "Item (%p) is app owned and will not be "...
0x1800604b8  xor     edx, edx
0x1800604ba  xor     ecx, ecx
0x1800604bc  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800604c1  mov     rdx, rax; char *
0x1800604c4  mov     rcx, r15; char *
0x1800604c7  mov     rbx, rax
0x1800604ca  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800604cf  mov     rcx, rbx; this
0x1800604d2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800604d7  mov     r9, [rsi]
0x1800604da  lea     r8, aItemPIsAppOwne; "Item (%p) is app owned and will not be "...
0x1800604e1  xor     edx, edx
0x1800604e3  xor     ecx, ecx
0x1800604e5  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800604ea  mov     r9d, 4; int
0x1800604f0  mov     [rsp+0C8h+lpMem], rax; lpMem
0x1800604f5  mov     r8, r15; int
0x1800604f8  call    WiaTrace_ProcessTrace_Ex
0x1800604fd  lea     rcx, [rsp+0C8h+var_88]; this
0x180060502  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180060507  mov     eax, edi
0x180060509  add     rsp, 98h
0x180060510  pop     r15
0x180060512  pop     r14
0x180060514  pop     rdi
0x180060515  pop     rsi
0x180060516  pop     rbp
0x180060517  pop     rbx
0x180060518  retn
```
