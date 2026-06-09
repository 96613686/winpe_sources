# CWIADevInfo::Initialize(USDWrapper *)

- ea: `0x18001699c`
- end: `0x180016ab1`
- name: `?Initialize@CWIADevInfo@@QEAAJPEAVUSDWrapper@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(CWIADevInfo *__hidden this, struct USDWrapper *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180015f90`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18001699c`
- `0x18002de18`
- `0x18002def8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800169ed`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800169ed`
- `api-ms-win-core-com-l2-1-1!StgCreatePropStg` at `0x180016a1b`
- `api-ms-win-core-com-l2-1-1!StgCreatePropStg` at `0x180016a1b`

## string_xrefs

- `0x180016a56`: `CWIADevInfo::Initialize, CreateStreamOnHGlobal failed (0x%X)`
- `0x180016a78`: `CWIADevInfo::Initialize, CreateStreamOnHGlobal failed (0x%X)`
- `0x180016a29`: `CWIADevInfo::Initialize, StgOpenPropStg failed (0x%X)`
- `0x180016a4b`: `CWIADevInfo::Initialize, StgOpenPropStg failed (0x%X)`

## pseudocode

```c
__int64 __fastcall CWIADevInfo::Initialize(CWIADevInfo *this, struct USDWrapper *a2)
{
  struct tagWiaTraceData_Type *v4; // rax
  char *v5; // rdx
  unsigned int v6; // r8d
  HRESULT StreamOnHGlobal; // edi
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  char *v13; // rbx
  void *v14; // rdx
  unsigned int dwReserved; // [rsp+20h] [rbp-88h]
  _BYTE v17[120]; // [rsp+30h] [rbp-78h] BYREF

  v4 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWIADevInfo::Initialize");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v17, v5, v6, "CWIADevInfo::Initialize", dwReserved, v4);
  *((_QWORD *)this + 5) = a2;
  (*(void (__fastcall **)(struct USDWrapper *))(*(_QWORD *)a2 + 8LL))(a2);
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)this + 4);
  if ( StreamOnHGlobal < 0 )
  {
    v13 = (char *)WiaTrace_TraceLog("CWIADevInfo::Initialize, CreateStreamOnHGlobal failed (0x%X)");
    WriteDbgTraceErrorWI("CWIADevInfo::Initialize", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v10 = (void **)WiaTrace_Trace(
                     "CWIADevInfo::Initialize, CreateStreamOnHGlobal failed (0x%X)",
                     (unsigned int)StreamOnHGlobal);
    goto LABEL_5;
  }
  StreamOnHGlobal = StgCreatePropStg(
                      *((IUnknown **)this + 4),
                      &GUID_NULL,
                      &GUID_NULL,
                      0,
                      0,
                      (IPropertyStorage **)this + 1);
  if ( StreamOnHGlobal < 0 )
  {
    v8 = (char *)WiaTrace_TraceLog("CWIADevInfo::Initialize, StgOpenPropStg failed (0x%X)");
    WriteDbgTraceErrorWI("CWIADevInfo::Initialize", v8);
    WiaTrcLib::Free((WiaTrcLib *)v8, v9);
    v10 = (void **)WiaTrace_Trace(
                     "CWIADevInfo::Initialize, StgOpenPropStg failed (0x%X)",
                     (unsigned int)StreamOnHGlobal);
LABEL_5:
    WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"CWIADevInfo::Initialize", 1, v10);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v17);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18001699c  push    rbx
0x18001699e  push    rbp
0x18001699f  push    rsi
0x1800169a0  push    rdi
0x1800169a1  sub     rsp, 88h
0x1800169a8  mov     rsi, rcx
0x1800169ab  lea     rbp, aCwiadevinfoIni; "CWIADevInfo::Initialize"
0x1800169b2  mov     rcx, rbp
0x1800169b5  mov     rbx, rdx
0x1800169b8  call    WiaTrace_Trace
0x1800169bd  mov     r9, rbp; char *
0x1800169c0  mov     [rsp+0A8h+ppPropStg], rax; struct tagWiaTraceData_Type *
0x1800169c5  lea     rcx, [rsp+0A8h+var_78]; this
0x1800169ca  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800169cf  mov     [rsi+28h], rbx
0x1800169d3  mov     rcx, rbx
0x1800169d6  mov     rax, [rbx]
0x1800169d9  mov     rax, [rax+8]
0x1800169dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169e2  lea     r8, [rsi+20h]; ppstm
0x1800169e6  mov     edx, 1; fDeleteOnRelease
0x1800169eb  xor     ecx, ecx; hGlobal
0x1800169ed  call    cs:__imp_CreateStreamOnHGlobal
0x1800169f3  mov     edi, eax
0x1800169f5  test    eax, eax
0x1800169f7  js      short loc_180016A54
0x1800169f9  mov     rcx, [rsi+20h]; pUnk
0x1800169fd  lea     rax, [rsi+8]
0x180016a01  lea     rdx, GUID_NULL; fmtid
0x180016a08  mov     [rsp+0A8h+ppPropStg], rax; ppPropStg
0x180016a0d  mov     r8, rdx; pclsid
0x180016a10  mov     [rsp+0A8h+dwReserved], 0; dwReserved
0x180016a18  xor     r9d, r9d; grfFlags
0x180016a1b  call    cs:__imp_StgCreatePropStg
0x180016a21  mov     edi, eax
0x180016a23  test    eax, eax
0x180016a25  jns     short loc_180016A99
0x180016a27  mov     edx, eax
0x180016a29  lea     rcx, aCwiadevinfoIni_1; "CWIADevInfo::Initialize, StgOpenPropStg"...
0x180016a30  call    WiaTrace_TraceLog
0x180016a35  mov     rdx, rax; char *
0x180016a38  mov     rcx, rbp; char *
0x180016a3b  mov     rbx, rax
0x180016a3e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180016a43  mov     rcx, rbx; this
0x180016a46  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016a4b  lea     rcx, aCwiadevinfoIni_1; "CWIADevInfo::Initialize, StgOpenPropStg"...
0x180016a52  jmp     short loc_180016A7F
0x180016a54  mov     edx, edi
0x180016a56  lea     rcx, aCwiadevinfoIni_0; "CWIADevInfo::Initialize, CreateStreamOn"...
0x180016a5d  call    WiaTrace_TraceLog
0x180016a62  mov     rdx, rax; char *
0x180016a65  mov     rcx, rbp; char *
0x180016a68  mov     rbx, rax
0x180016a6b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180016a70  mov     rcx, rbx; this
0x180016a73  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016a78  lea     rcx, aCwiadevinfoIni_0; "CWIADevInfo::Initialize, CreateStreamOn"...
0x180016a7f  mov     edx, edi
0x180016a81  call    WiaTrace_Trace
0x180016a86  mov     r9d, 1; int
0x180016a8c  mov     qword ptr [rsp+0A8h+dwReserved], rax; lpMem
0x180016a91  mov     r8, rbp; int
0x180016a94  call    WiaTrace_ProcessTrace_Ex
0x180016a99  lea     rcx, [rsp+0A8h+var_78]; this
0x180016a9e  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180016aa3  mov     eax, edi
0x180016aa5  add     rsp, 88h
0x180016aac  pop     rdi
0x180016aad  pop     rsi
0x180016aae  pop     rbp
0x180016aaf  pop     rbx
0x180016ab0  retn
```
