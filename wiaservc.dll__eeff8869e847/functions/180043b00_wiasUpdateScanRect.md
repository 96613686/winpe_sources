# wiasUpdateScanRect

- ea: `0x180043b00`
- end: `0x180043cda`
- name: `wiasUpdateScanRect`
- size: `474`
- prototype: `__int64 __fastcall(struct IWiaItem *this, struct _WIA_PROPERTY_CONTEXT *, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x180043b00`
- `0x180057734`
- `0x180057d44`

## string_xrefs

- `0x180043b14`: `::wiasUpdateScanRect`
- `0x180043b26`: `wiasUpdateScanRect`
- `0x180043b44`: `wiasUpdateScanRect, pContext is a bad (read) pointer`
- `0x180043b66`: `wiasUpdateScanRect, pContext is a bad (read) pointer`
- `0x180043ba9`: `wiasUpdateScanRect, pContext->pProps is a bad (read) pointer`
- `0x180043bcb`: `wiasUpdateScanRect, pContext->pProps is a bad (read) pointer`
- `0x180043bdb`: `wiasUpdateScanRect, pContext->pChanged is a bad (read) pointer`
- `0x180043bfd`: `wiasUpdateScanRect, pContext->pChanged is a bad (read) pointer`
- `0x180043c50`: `wiasUpdateScanRect, CheckYResAndUpdate failed (0x%X)`
- `0x180043c72`: `wiasUpdateScanRect, CheckYResAndUpdate failed (0x%X)`
- `0x180043c7d`: `wiasUpdateScanRect, CheckXResAndUpdate failed (0x%X)`
- `0x180043c9f`: `wiasUpdateScanRect, CheckXResAndUpdate failed (0x%X)`

## pseudocode

```c
__int64 __fastcall wiasUpdateScanRect(struct IWiaItem *this, struct _WIA_PROPERTY_CONTEXT *a2, int a3, int a4)
{
  char ***v8; // rax
  char *v9; // rdx
  __int64 v10; // r8
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  char *v17; // rbx
  void *v18; // rdx
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  int v24; // edi
  char *v25; // rbx
  void *v26; // rdx
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  char *v30; // rbx
  void *v31; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-88h]
  _BYTE v33[120]; // [rsp+30h] [rbp-78h] BYREF

  v8 = (char ***)WiaTrace_Trace("::wiasUpdateScanRect");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v33, v9, v10, (char **)"wiasUpdateScanRect", lpMem, v8);
  if ( !a2 )
  {
    v11 = (char *)WiaTrace_TraceLog("wiasUpdateScanRect, pContext is a bad (read) pointer");
    WriteDbgTraceErrorWI("wiasUpdateScanRect", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v13 = (void **)WiaTrace_Trace("wiasUpdateScanRect, pContext is a bad (read) pointer");
LABEL_3:
    WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"wiasUpdateScanRect", 1, v13);
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v33);
    return 2147500035LL;
  }
  if ( !*(_DWORD *)a2 )
    goto LABEL_9;
  if ( !*((_QWORD *)a2 + 1) )
  {
    v17 = (char *)WiaTrace_TraceLog("wiasUpdateScanRect, pContext->pProps is a bad (read) pointer");
    WriteDbgTraceErrorWI("wiasUpdateScanRect", v17);
    WiaTrcLib::Free((WiaTrcLib *)v17, v18);
    v13 = (void **)WiaTrace_Trace("wiasUpdateScanRect, pContext->pProps is a bad (read) pointer");
    goto LABEL_3;
  }
  if ( *((_QWORD *)a2 + 2) )
  {
LABEL_9:
    v24 = CheckXResAndUpdate(this, a2, a3);
    if ( v24 < 0 )
    {
      v30 = (char *)WiaTrace_TraceLog("wiasUpdateScanRect, CheckXResAndUpdate failed (0x%X)");
      WriteDbgTraceErrorWI("wiasUpdateScanRect", v30);
      WiaTrcLib::Free((WiaTrcLib *)v30, v31);
      v27 = (void **)WiaTrace_Trace("wiasUpdateScanRect, CheckXResAndUpdate failed (0x%X)", (unsigned int)v24);
    }
    else
    {
      v24 = CheckYResAndUpdate(this, a2, a4);
      if ( v24 >= 0 )
        goto LABEL_14;
      v25 = (char *)WiaTrace_TraceLog("wiasUpdateScanRect, CheckYResAndUpdate failed (0x%X)");
      WriteDbgTraceErrorWI("wiasUpdateScanRect", v25);
      WiaTrcLib::Free((WiaTrcLib *)v25, v26);
      v27 = (void **)WiaTrace_Trace("wiasUpdateScanRect, CheckYResAndUpdate failed (0x%X)", (unsigned int)v24);
    }
    WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"wiasUpdateScanRect", 1, v27);
    goto LABEL_14;
  }
  v19 = (char *)WiaTrace_TraceLog("wiasUpdateScanRect, pContext->pChanged is a bad (read) pointer");
  WriteDbgTraceErrorWI("wiasUpdateScanRect", v19);
  WiaTrcLib::Free((WiaTrcLib *)v19, v20);
  v21 = (void **)WiaTrace_Trace("wiasUpdateScanRect, pContext->pChanged is a bad (read) pointer");
  WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"wiasUpdateScanRect", 1, v21);
  v24 = -2147467261;
LABEL_14:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v33);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180043b00  push    rbx
0x180043b02  push    rbp
0x180043b03  push    rsi
0x180043b04  push    rdi
0x180043b05  push    r15
0x180043b07  sub     rsp, 80h
0x180043b0e  mov     rsi, rcx
0x180043b11  mov     ebp, r9d
0x180043b14  lea     rcx, aWiasupdatescan_6; "::wiasUpdateScanRect"
0x180043b1b  mov     edi, r8d
0x180043b1e  mov     rbx, rdx
0x180043b21  call    WiaTrace_Trace
0x180043b26  lea     r15, aWiasupdatescan_5; "wiasUpdateScanRect"
0x180043b2d  mov     [rsp+0A8h+var_80], rax; struct tagWiaTraceData_Type *
0x180043b32  mov     r9, r15; char *
0x180043b35  lea     rcx, [rsp+0A8h+var_78]; this
0x180043b3a  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180043b3f  test    rbx, rbx
0x180043b42  jnz     short loc_180043B99
0x180043b44  lea     rcx, aWiasupdatescan_1; "wiasUpdateScanRect, pContext is a bad ("...
0x180043b4b  call    WiaTrace_TraceLog
0x180043b50  mov     rdx, rax; char *
0x180043b53  mov     rcx, r15; char *
0x180043b56  mov     rbx, rax
0x180043b59  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180043b5e  mov     rcx, rbx; this
0x180043b61  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180043b66  lea     rcx, aWiasupdatescan_1; "wiasUpdateScanRect, pContext is a bad ("...
0x180043b6d  call    WiaTrace_Trace
0x180043b72  mov     r9d, 1; int
0x180043b78  mov     [rsp+0A8h+lpMem], rax; lpMem
0x180043b7d  mov     r8, r15; int
0x180043b80  call    WiaTrace_ProcessTrace_Ex
0x180043b85  lea     rcx, [rsp+0A8h+var_78]; this
0x180043b8a  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180043b8f  mov     eax, 80004003h
0x180043b94  jmp     loc_180043CCC
0x180043b99  cmp     dword ptr [rbx], 0
0x180043b9c  jz      loc_180043C26
0x180043ba2  cmp     qword ptr [rbx+8], 0
0x180043ba7  jnz     short loc_180043BD4
0x180043ba9  lea     rcx, aWiasupdatescan_0; "wiasUpdateScanRect, pContext->pProps is"...
0x180043bb0  call    WiaTrace_TraceLog
0x180043bb5  mov     rdx, rax; char *
0x180043bb8  mov     rcx, r15; char *
0x180043bbb  mov     rbx, rax
0x180043bbe  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180043bc3  mov     rcx, rbx; this
0x180043bc6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180043bcb  lea     rcx, aWiasupdatescan_0; "wiasUpdateScanRect, pContext->pProps is"...
0x180043bd2  jmp     short loc_180043B6D
0x180043bd4  cmp     qword ptr [rbx+10h], 0
0x180043bd9  jnz     short loc_180043C26
0x180043bdb  lea     rcx, aWiasupdatescan_2; "wiasUpdateScanRect, pContext->pChanged "...
0x180043be2  call    WiaTrace_TraceLog
0x180043be7  mov     rdx, rax; char *
0x180043bea  mov     rcx, r15; char *
0x180043bed  mov     rbx, rax
0x180043bf0  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180043bf5  mov     rcx, rbx; this
0x180043bf8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180043bfd  lea     rcx, aWiasupdatescan_2; "wiasUpdateScanRect, pContext->pChanged "...
0x180043c04  call    WiaTrace_Trace
0x180043c09  mov     r9d, 1; int
0x180043c0f  mov     [rsp+0A8h+lpMem], rax; lpMem
0x180043c14  mov     r8, r15; int
0x180043c17  call    WiaTrace_ProcessTrace_Ex
0x180043c1c  mov     edi, 80004003h
0x180043c21  jmp     loc_180043CC0
0x180043c26  mov     r8d, edi; int
0x180043c29  mov     rdx, rbx; struct _WIA_PROPERTY_CONTEXT *
0x180043c2c  mov     rcx, rsi; this
0x180043c2f  call    ?CheckXResAndUpdate@@YAJPEAEPEAU_WIA_PROPERTY_CONTEXT@@J@Z; CheckXResAndUpdate(uchar *,_WIA_PROPERTY_CONTEXT *,long)
0x180043c34  mov     edi, eax
0x180043c36  test    eax, eax
0x180043c38  js      short loc_180043C7B
0x180043c3a  mov     r8d, ebp; int
0x180043c3d  mov     rdx, rbx; struct _WIA_PROPERTY_CONTEXT *
0x180043c40  mov     rcx, rsi; this
0x180043c43  call    ?CheckYResAndUpdate@@YAJPEAEPEAU_WIA_PROPERTY_CONTEXT@@J@Z; CheckYResAndUpdate(uchar *,_WIA_PROPERTY_CONTEXT *,long)
0x180043c48  mov     edi, eax
0x180043c4a  test    eax, eax
0x180043c4c  jns     short loc_180043CC0
0x180043c4e  mov     edx, eax
0x180043c50  lea     rcx, aWiasupdatescan_3; "wiasUpdateScanRect, CheckYResAndUpdate "...
0x180043c57  call    WiaTrace_TraceLog
0x180043c5c  mov     rdx, rax; char *
0x180043c5f  mov     rcx, r15; char *
0x180043c62  mov     rbx, rax
0x180043c65  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180043c6a  mov     rcx, rbx; this
0x180043c6d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180043c72  lea     rcx, aWiasupdatescan_3; "wiasUpdateScanRect, CheckYResAndUpdate "...
0x180043c79  jmp     short loc_180043CA6
0x180043c7b  mov     edx, edi
0x180043c7d  lea     rcx, aWiasupdatescan_4; "wiasUpdateScanRect, CheckXResAndUpdate "...
0x180043c84  call    WiaTrace_TraceLog
0x180043c89  mov     rdx, rax; char *
0x180043c8c  mov     rcx, r15; char *
0x180043c8f  mov     rbx, rax
0x180043c92  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180043c97  mov     rcx, rbx; this
0x180043c9a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180043c9f  lea     rcx, aWiasupdatescan_4; "wiasUpdateScanRect, CheckXResAndUpdate "...
0x180043ca6  mov     edx, edi
0x180043ca8  call    WiaTrace_Trace
0x180043cad  mov     r9d, 1; int
0x180043cb3  mov     [rsp+0A8h+lpMem], rax; lpMem
0x180043cb8  mov     r8, r15; int
0x180043cbb  call    WiaTrace_ProcessTrace_Ex
0x180043cc0  lea     rcx, [rsp+0A8h+var_78]; this
0x180043cc5  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180043cca  mov     eax, edi
0x180043ccc  add     rsp, 80h
0x180043cd3  pop     r15
0x180043cd5  pop     rdi
0x180043cd6  pop     rsi
0x180043cd7  pop     rbp
0x180043cd8  pop     rbx
0x180043cd9  retn
```
