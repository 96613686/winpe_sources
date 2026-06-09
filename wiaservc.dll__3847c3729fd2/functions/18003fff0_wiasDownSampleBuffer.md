# wiasDownSampleBuffer

- ea: `0x18003fff0`
- end: `0x18004033f`
- name: `wiasDownSampleBuffer`
- size: `847`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x18003fff0`
- `0x180057518`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800402bc`
- `ole32!CoTaskMemFree` at `0x1800402bc`
- `ole32!CoTaskMemAlloc` at `0x180040135`
- `ole32!CoTaskMemAlloc` at `0x180040135`

## string_xrefs

- `0x180040035`: `wiasDownSampleBuffer, cannot write to WIAS_DOWN_SAMPLE_INFO!`
- `0x180040057`: `wiasDownSampleBuffer, cannot write to WIAS_DOWN_SAMPLE_INFO!`
- `0x1800401b8`: `wiasDownSampleBuffer, cannot read ulSrcBufSize bytes from pSrcBuffer!`
- `0x1800401de`: `wiasDownSampleBuffer, cannot read ulSrcBufSize bytes from pSrcBuffer!`

## pseudocode

```c
__int64 __fastcall wiasDownSampleBuffer(int a1, __int64 a2)
{
  struct tagWiaTraceData_Type *v4; // rax
  char *v5; // rdx
  unsigned int v6; // r8d
  unsigned int v7; // edi
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // ecx
  int *v14; // r10
  int *v15; // r12
  unsigned int v16; // r8d
  unsigned int v17; // ecx
  unsigned int v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // edx
  int v21; // r8d
  int v22; // ebx
  int v23; // r13d
  LPVOID *v24; // r14
  LPVOID v25; // rax
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  unsigned __int8 *v31; // rcx
  char *v32; // rbx
  void *v33; // rdx
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-A8h]
  _BYTE v41[120]; // [rsp+50h] [rbp-78h] BYREF
  int *v42; // [rsp+E0h] [rbp+18h]

  v4 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasDownSampleBuffer");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v41, v5, v6, "wiasDownSampleBuffer", lpMem, v4);
  v7 = 0;
  if ( !a2 )
  {
    v8 = (char *)WiaTrace_TraceLog("wiasDownSampleBuffer, cannot write to WIAS_DOWN_SAMPLE_INFO!");
    WriteDbgTraceErrorWI("wiasDownSampleBuffer", v8);
    WiaTrcLib::Free((WiaTrcLib *)v8, v9);
    v10 = (void **)WiaTrace_Trace("wiasDownSampleBuffer, cannot write to WIAS_DOWN_SAMPLE_INFO!");
LABEL_20:
    WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"wiasDownSampleBuffer", 1, v10);
    v7 = -2147024809;
LABEL_21:
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v41);
    return v7;
  }
  v13 = *(_DWORD *)(a2 + 20);
  v14 = (int *)(a2 + 4);
  v15 = (int *)(a2 + 24);
  v42 = (int *)(a2 + 4);
  if ( !v13 )
  {
    v16 = *v14;
    *v15 = (unsigned int)(50 * *v14) / *(_DWORD *)(a2 + 12);
    v17 = *(_DWORD *)a2;
    v18 = (unsigned int)(50 * *(_DWORD *)a2) / *(_DWORD *)(a2 + 12);
    *(_DWORD *)(a2 + 20) = v18;
    if ( *(_DWORD *)(a2 + 12) <= 0x12Cu )
    {
      v13 = v18;
      v42 = (int *)(a2 + 4);
    }
    else
    {
      *v15 = v16 >> 2;
      v13 = v17 >> 2;
      *(_DWORD *)(a2 + 20) = v13;
    }
  }
  if ( *v15 && *v14 )
  {
    v19 = *(_DWORD *)(a2 + 8);
    if ( v19 == 1 )
      v20 = (v13 + 7) >> 3;
    else
      v20 = v13 * (v19 >> 3);
    v21 = *v15 * (v20 + ((v20 & 3) != 0 ? 4 - (v20 & 3) : 0));
    *(_DWORD *)(a2 + 28) = v21;
    if ( a1 == 1 )
      goto LABEL_21;
    v22 = 0;
    v23 = 0;
    v24 = (LPVOID *)(a2 + 48);
    if ( !*(_QWORD *)(a2 + 48) )
    {
      v25 = CoTaskMemAlloc((unsigned int)(2 * v21));
      *v24 = v25;
      if ( v25 )
      {
        *(_DWORD *)(a2 + 32) = *(_DWORD *)(a2 + 28);
        v23 = 1;
      }
      else
      {
        v26 = (char *)WiaTrace_TraceLog("wiasDownSampleBuffer, Out of memory");
        WriteDbgTraceErrorWI("wiasDownSampleBuffer", v26);
        WiaTrcLib::Free((WiaTrcLib *)v26, v27);
        v28 = (void **)WiaTrace_Trace("wiasDownSampleBuffer, Out of memory");
        WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"wiasDownSampleBuffer", 1, v28);
        v22 = -2147024882;
      }
      v14 = v42;
    }
    v31 = *(unsigned __int8 **)(a2 + 40);
    if ( !v31 )
    {
      v32 = (char *)WiaTrace_TraceLog("wiasDownSampleBuffer, cannot read ulSrcBufSize bytes from pSrcBuffer!");
      WriteDbgTraceErrorWI("wiasDownSampleBuffer", v32);
      WiaTrcLib::Free((WiaTrcLib *)v32, v33);
      v10 = (void **)WiaTrace_Trace("wiasDownSampleBuffer, cannot read ulSrcBufSize bytes from pSrcBuffer!");
      goto LABEL_20;
    }
    if ( v22 < 0
      || (v22 = BQADScale(
                  v31,
                  *(_DWORD *)a2,
                  *v14,
                  *(_DWORD *)(a2 + 8),
                  (unsigned __int8 *)*v24,
                  *(_DWORD *)(a2 + 20),
                  *v15),
          v22 < 0) )
    {
      if ( v23 )
      {
        CoTaskMemFree(*v24);
        *v24 = 0;
      }
    }
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v41);
    return (unsigned int)v22;
  }
  else
  {
    v35 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasDownSampleBuffer, height is zero, nothing to do...");
    WriteDbgTraceWarningWI("wiasDownSampleBuffer", v35);
    WiaTrcLib::Free((WiaTrcLib *)v35, v36);
    v37 = (void **)WiaTrace_TraceWithSubComp(0, "wiasDownSampleBuffer, height is zero, nothing to do...");
    WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"wiasDownSampleBuffer", 2, v37);
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v41);
    return 1;
  }
}

```

## disassembly

```asm
0x18003fff0  mov     [rsp+arg_0], rbx
0x18003fff5  push    rsi
0x18003fff6  push    rdi
0x18003fff7  push    r12
0x18003fff9  push    r13
0x18003fffb  push    r14
0x18003fffd  sub     rsp, 0A0h
0x180040004  mov     rsi, rdx
0x180040007  mov     ebx, ecx
0x180040009  lea     rcx, aWiasdownsample_3; "::wiasDownSampleBuffer"
0x180040010  call    WiaTrace_Trace
0x180040015  mov     [rsp+0C8h+var_A0], rax; struct tagWiaTraceData_Type *
0x18004001a  lea     r14, aWiasdownsample_0; "wiasDownSampleBuffer"
0x180040021  mov     r9, r14; char *
0x180040024  lea     rcx, [rsp+0C8h+var_78]; this
0x180040029  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18004002e  xor     edi, edi
0x180040030  test    rsi, rsi
0x180040033  jnz     short loc_18004006B
0x180040035  lea     rcx, aWiasdownsample_2; "wiasDownSampleBuffer, cannot write to W"...
0x18004003c  call    WiaTrace_TraceLog
0x180040041  mov     rbx, rax
0x180040044  mov     rdx, rax; char *
0x180040047  mov     rcx, r14; char *
0x18004004a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004004f  mov     rcx, rbx; this
0x180040052  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180040057  lea     rcx, aWiasdownsample_2; "wiasDownSampleBuffer, cannot write to W"...
0x18004005e  call    WiaTrace_Trace
0x180040063  mov     r8, r14
0x180040066  jmp     loc_1800401F1
0x18004006b  mov     ecx, [rsi+14h]
0x18004006e  lea     r10, [rsi+4]
0x180040072  lea     r12, [rsi+18h]
0x180040076  mov     [rsp+0C8h+arg_10], r10
0x18004007e  test    ecx, ecx
0x180040080  jnz     short loc_1800400C2
0x180040082  mov     r8d, [r10]
0x180040085  imul    eax, r8d, 32h ; '2'
0x180040089  xor     edx, edx
0x18004008b  div     dword ptr [rsi+0Ch]
0x18004008e  mov     [r12], eax
0x180040092  mov     ecx, [rsi]
0x180040094  imul    eax, ecx, 32h ; '2'
0x180040097  xor     edx, edx
0x180040099  div     dword ptr [rsi+0Ch]
0x18004009c  mov     [rsi+14h], eax
0x18004009f  cmp     dword ptr [rsi+0Ch], 12Ch
0x1800400a6  jbe     short loc_1800400B8
0x1800400a8  shr     r8d, 2
0x1800400ac  mov     [r12], r8d
0x1800400b0  shr     ecx, 2
0x1800400b3  mov     [rsi+14h], ecx
0x1800400b6  jmp     short loc_1800400C2
0x1800400b8  mov     ecx, eax
0x1800400ba  mov     [rsp+0C8h+arg_10], r10
0x1800400c2  cmp     [r12], edi
0x1800400c6  jz      loc_1800402D3
0x1800400cc  cmp     [r10], edi
0x1800400cf  jz      loc_1800402D3
0x1800400d5  mov     edx, [rsi+8]
0x1800400d8  cmp     edx, 1
0x1800400db  jnz     short loc_1800400E5
0x1800400dd  lea     edx, [rcx+7]
0x1800400e0  shr     edx, 3
0x1800400e3  jmp     short loc_1800400EB
0x1800400e5  shr     edx, 3
0x1800400e8  imul    edx, ecx
0x1800400eb  mov     ecx, edx
0x1800400ed  and     ecx, 3
0x1800400f0  mov     eax, 4
0x1800400f5  sub     eax, ecx
0x1800400f7  neg     ecx
0x1800400f9  sbb     r8d, r8d
0x1800400fc  and     r8d, eax
0x1800400ff  add     r8d, edx
0x180040102  imul    r8d, [r12]
0x180040107  mov     [rsi+1Ch], r8d
0x18004010b  cmp     ebx, 1
0x18004010e  jz      loc_180040206
0x180040114  mov     ebx, edi
0x180040116  mov     r13d, edi
0x180040119  mov     [rsp+0C8h+arg_8], edi
0x180040120  lea     r14, [rsi+30h]
0x180040124  mov     [rsp+0C8h+arg_18], r14
0x18004012c  cmp     [r14], rdi
0x18004012f  jnz     short loc_1800401AF
0x180040131  lea     ecx, [r8+r8]; cb
0x180040135  call    cs:__imp_CoTaskMemAlloc
0x18004013b  mov     [r14], rax
0x18004013e  test    rax, rax
0x180040141  jz      short loc_180040159
0x180040143  mov     eax, [rsi+1Ch]
0x180040146  mov     [rsi+20h], eax
0x180040149  mov     r13d, 1
0x18004014f  mov     [rsp+0C8h+arg_8], r13d
0x180040157  jmp     short loc_1800401A7
0x180040159  lea     rcx, aWiasdownsample_5; "wiasDownSampleBuffer, Out of memory"
0x180040160  call    WiaTrace_TraceLog
0x180040165  mov     rbx, rax
0x180040168  mov     rdx, rax; char *
0x18004016b  lea     rcx, aWiasdownsample_0; "wiasDownSampleBuffer"
0x180040172  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180040177  mov     rcx, rbx; this
0x18004017a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004017f  lea     rcx, aWiasdownsample_5; "wiasDownSampleBuffer, Out of memory"
0x180040186  call    WiaTrace_Trace
0x18004018b  mov     [rsp+0C8h+lpMem], rax; lpMem
0x180040190  mov     r9d, 1; int
0x180040196  lea     r8, aWiasdownsample_0; "wiasDownSampleBuffer"
0x18004019d  call    WiaTrace_ProcessTrace_Ex
0x1800401a2  mov     ebx, 8007000Eh
0x1800401a7  mov     r10, [rsp+0C8h+arg_10]
0x1800401af  mov     rcx, [rsi+28h]; unsigned __int8 *
0x1800401b3  test    rcx, rcx
0x1800401b6  jnz     short loc_180040217
0x1800401b8  lea     rcx, aWiasdownsample_6; "wiasDownSampleBuffer, cannot read ulSrc"...
0x1800401bf  call    WiaTrace_TraceLog
0x1800401c4  mov     rbx, rax
0x1800401c7  mov     rdx, rax; char *
0x1800401ca  lea     rcx, aWiasdownsample_0; "wiasDownSampleBuffer"
0x1800401d1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800401d6  mov     rcx, rbx; this
0x1800401d9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800401de  lea     rcx, aWiasdownsample_6; "wiasDownSampleBuffer, cannot read ulSrc"...
0x1800401e5  call    WiaTrace_Trace
0x1800401ea  lea     r8, aWiasdownsample_0; "wiasDownSampleBuffer"
0x1800401f1  mov     [rsp+0C8h+lpMem], rax; lpMem
0x1800401f6  mov     r9d, 1; int
0x1800401fc  call    WiaTrace_ProcessTrace_Ex
0x180040201  mov     edi, 80070057h
0x180040206  lea     rcx, [rsp+0C8h+var_78]; this
0x18004020b  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180040210  mov     eax, edi
0x180040212  jmp     loc_180040327
0x180040217  test    ebx, ebx
0x180040219  js      loc_1800402B4
0x18004021f  mov     eax, [r12]
0x180040223  mov     [rsp+0C8h+var_98], eax; int
0x180040227  mov     eax, [rsi+14h]
0x18004022a  mov     dword ptr [rsp+0C8h+var_A0], eax; int
0x18004022e  mov     rax, [r14]
0x180040231  mov     [rsp+0C8h+lpMem], rax; unsigned __int8 *
0x180040236  mov     r9d, [rsi+8]; int
0x18004023a  mov     r8d, [r10]; int
0x18004023d  mov     edx, [rsi]; int
0x18004023f  call    ?BQADScale@@YAJPEAEJJJ0JJ@Z; BQADScale(uchar *,long,long,long,uchar *,long,long)
0x180040244  mov     ebx, eax
0x180040246  mov     [rsp+0C8h+var_88], eax
0x18004024a  jmp     short loc_1800402B0
0x18004024c  lea     rcx, aWiasdownsample_4; "wiasDownSampleBuffer, Exception occurre"...
0x180040253  call    WiaTrace_TraceLog
0x180040258  mov     rbx, rax
0x18004025b  mov     rdx, rax; char *
0x18004025e  lea     rcx, aWiasdownsample_0; "wiasDownSampleBuffer"
0x180040265  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004026a  mov     rcx, rbx; this
0x18004026d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180040272  lea     rcx, aWiasdownsample_4; "wiasDownSampleBuffer, Exception occurre"...
0x180040279  call    WiaTrace_Trace
0x18004027e  mov     [rsp+0C8h+lpMem], rax; lpMem
0x180040283  mov     r9d, 1; int
0x180040289  lea     r8, aWiasdownsample_0; "wiasDownSampleBuffer"
0x180040290  call    WiaTrace_ProcessTrace_Ex
0x180040295  mov     ebx, 8000FFFFh
0x18004029a  mov     [rsp+0C8h+var_88], ebx
0x18004029e  xor     edi, edi
0x1800402a0  mov     r13d, [rsp+0C8h+arg_8]
0x1800402a8  mov     r14, [rsp+0C8h+arg_18]
0x1800402b0  test    ebx, ebx
0x1800402b2  jns     short loc_1800402C5
0x1800402b4  test    r13d, r13d
0x1800402b7  jz      short loc_1800402C5
0x1800402b9  mov     rcx, [r14]; pv
0x1800402bc  call    cs:__imp_CoTaskMemFree
0x1800402c2  mov     [r14], rdi
0x1800402c5  lea     rcx, [rsp+0C8h+var_78]; this
0x1800402ca  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800402cf  mov     eax, ebx
0x1800402d1  jmp     short loc_180040327
0x1800402d3  lea     rdx, aWiasdownsample_1; "wiasDownSampleBuffer, height is zero, n"...
0x1800402da  xor     ecx, ecx
0x1800402dc  call    WiaTrace_TraceLogWithSubComp
0x1800402e1  mov     rbx, rax
0x1800402e4  mov     rdx, rax; char *
0x1800402e7  mov     rcx, r14; char *
0x1800402ea  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800402ef  mov     rcx, rbx; this
0x1800402f2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800402f7  lea     rdx, aWiasdownsample_1; "wiasDownSampleBuffer, height is zero, n"...
0x1800402fe  xor     ecx, ecx
0x180040300  call    WiaTrace_TraceWithSubComp
0x180040305  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18004030a  mov     r9d, 2; int
0x180040310  mov     r8, r14; int
0x180040313  call    WiaTrace_ProcessTrace_Ex
0x180040318  lea     rcx, [rsp+0C8h+var_78]; this
0x18004031d  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180040322  mov     eax, 1
0x180040327  mov     rbx, [rsp+0C8h+arg_0]
0x18004032f  add     rsp, 0A0h
0x180040336  pop     r14
0x180040338  pop     r13
0x18004033a  pop     r12
0x18004033c  pop     rdi
0x18004033d  pop     rsi
0x18004033e  retn
```
