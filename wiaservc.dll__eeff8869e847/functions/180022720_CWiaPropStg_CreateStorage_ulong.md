# CWiaPropStg::CreateStorage(ulong)

- ea: `0x180022720`
- end: `0x1800227fd`
- name: `?CreateStorage@CWiaPropStg@@AEAAJK@Z`
- size: `221`
- prototype: `__int64 __fastcall(IUnknown **this, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180023288`
- `0x18005c6c4`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x180022720`
- `0x18002de18`
- `0x18002def8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002273d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002273d`
- `api-ms-win-core-com-l2-1-1!StgCreatePropStg` at `0x180022768`
- `api-ms-win-core-com-l2-1-1!StgCreatePropStg` at `0x180022768`

## string_xrefs

- `0x180022776`: `CWiaPropStg::CreateStorage, StgCreatePropStg failed 0x%X`
- `0x18002279c`: `CWiaPropStg::CreateStorage, StgCreatePropStg failed 0x%X`
- `0x180022785`: `CWiaPropStg::CreateStorage`
- `0x1800227b6`: `CWiaPropStg::CreateStorage`
- `0x1800227e6`: `CWiaPropStg::CreateStorage`
- `0x1800227a7`: `CWiaPropStg::CreateStorage, CreateStreamOnHGlobal failed 0x%X`
- `0x1800227cd`: `CWiaPropStg::CreateStorage, CreateStreamOnHGlobal failed 0x%X`

## pseudocode

```c
__int64 __fastcall CWiaPropStg::CreateStorage(IUnknown **this, unsigned int a2)
{
  __int64 v2; // rsi
  LPSTREAM *ppPropStg; // rbp
  HRESULT StreamOnHGlobal; // edi
  char *v6; // rbx
  void *v7; // rdx
  void **v8; // rax
  void *v9; // rdx
  __int64 v10; // rcx
  char *v11; // rbx
  void *v12; // rdx

  v2 = a2;
  ppPropStg = (LPSTREAM *)&this[a2];
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppPropStg + 7);
  if ( StreamOnHGlobal < 0 )
  {
    v11 = (char *)WiaTrace_TraceLog("CWiaPropStg::CreateStorage, CreateStreamOnHGlobal failed 0x%X");
    WriteDbgTraceErrorWI("CWiaPropStg::CreateStorage", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v8 = (void **)WiaTrace_Trace(
                    "CWiaPropStg::CreateStorage, CreateStreamOnHGlobal failed 0x%X",
                    (unsigned int)StreamOnHGlobal);
    goto LABEL_5;
  }
  StreamOnHGlobal = StgCreatePropStg(this[v2 + 7], &GUID_NULL, &GUID_NULL, 0, 0, (IPropertyStorage **)ppPropStg);
  if ( StreamOnHGlobal < 0 )
  {
    v6 = (char *)WiaTrace_TraceLog("CWiaPropStg::CreateStorage, StgCreatePropStg failed 0x%X");
    WriteDbgTraceErrorWI("CWiaPropStg::CreateStorage", v6);
    WiaTrcLib::Free((WiaTrcLib *)v6, v7);
    v8 = (void **)WiaTrace_Trace(
                    "CWiaPropStg::CreateStorage, StgCreatePropStg failed 0x%X",
                    (unsigned int)StreamOnHGlobal);
LABEL_5:
    WiaTrace_ProcessTrace_Ex(v10, v9, (void *)"CWiaPropStg::CreateStorage", 1, v8);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180022720  push    rbx
0x180022722  push    rbp
0x180022723  push    rsi
0x180022724  push    rdi
0x180022725  sub     rsp, 38h
0x180022729  mov     esi, edx
0x18002272b  mov     rbx, rcx
0x18002272e  mov     edx, 1; fDeleteOnRelease
0x180022733  lea     rbp, [rcx+rsi*8]
0x180022737  xor     ecx, ecx; hGlobal
0x180022739  lea     r8, [rbp+38h]; ppstm
0x18002273d  call    cs:__imp_CreateStreamOnHGlobal
0x180022743  mov     edi, eax
0x180022745  test    eax, eax
0x180022747  js      short loc_1800227A5
0x180022749  mov     rcx, [rbx+rsi*8+38h]; pUnk
0x18002274e  lea     rdx, GUID_NULL; fmtid
0x180022755  mov     r8, rdx; pclsid
0x180022758  mov     [rsp+58h+ppPropStg], rbp; ppPropStg
0x18002275d  xor     r9d, r9d; grfFlags
0x180022760  mov     [rsp+58h+dwReserved], 0; dwReserved
0x180022768  call    cs:__imp_StgCreatePropStg
0x18002276e  mov     edi, eax
0x180022770  test    eax, eax
0x180022772  jns     short loc_1800227F2
0x180022774  mov     edx, eax
0x180022776  lea     rcx, aCwiapropstgCre; "CWiaPropStg::CreateStorage, StgCreatePr"...
0x18002277d  call    WiaTrace_TraceLog
0x180022782  mov     rdx, rax; char *
0x180022785  lea     rcx, aCwiapropstgCre_0; "CWiaPropStg::CreateStorage"
0x18002278c  mov     rbx, rax
0x18002278f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180022794  mov     rcx, rbx; this
0x180022797  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002279c  lea     rcx, aCwiapropstgCre; "CWiaPropStg::CreateStorage, StgCreatePr"...
0x1800227a3  jmp     short loc_1800227D4
0x1800227a5  mov     edx, edi
0x1800227a7  lea     rcx, aCwiapropstgCre_1; "CWiaPropStg::CreateStorage, CreateStrea"...
0x1800227ae  call    WiaTrace_TraceLog
0x1800227b3  mov     rdx, rax; char *
0x1800227b6  lea     rcx, aCwiapropstgCre_0; "CWiaPropStg::CreateStorage"
0x1800227bd  mov     rbx, rax
0x1800227c0  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800227c5  mov     rcx, rbx; this
0x1800227c8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800227cd  lea     rcx, aCwiapropstgCre_1; "CWiaPropStg::CreateStorage, CreateStrea"...
0x1800227d4  mov     edx, edi
0x1800227d6  call    WiaTrace_Trace
0x1800227db  mov     r9d, 1; int
0x1800227e1  mov     qword ptr [rsp+58h+dwReserved], rax; lpMem
0x1800227e6  lea     r8, aCwiapropstgCre_0; "CWiaPropStg::CreateStorage"
0x1800227ed  call    WiaTrace_ProcessTrace_Ex
0x1800227f2  mov     eax, edi
0x1800227f4  add     rsp, 38h
0x1800227f8  pop     rdi
0x1800227f9  pop     rsi
0x1800227fa  pop     rbp
0x1800227fb  pop     rbx
0x1800227fc  retn
```
