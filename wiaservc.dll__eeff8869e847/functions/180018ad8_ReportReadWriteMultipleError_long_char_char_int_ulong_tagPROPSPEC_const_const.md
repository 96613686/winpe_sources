# ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)

- ea: `0x180018ad8`
- end: `0x180018f1f`
- name: `?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z`
- size: `1095`
- prototype: `void __fastcall(int, char *, char *, int, unsigned int, const struct tagPROPSPEC *const)`
- caller_count: `25`
- callee_count: `9`
- tags: ``

## callers

- `0x180015f90`
- `0x18001750c`
- `0x180017c7c`
- `0x180018390`
- `0x1800185a0`
- `0x18001b2c0`
- `0x180024500`
- `0x1800279b0`
- `0x180041cc0`
- `0x180041eb0`
- `0x180042140`
- `0x180042360`
- `0x180042590`
- `0x180043ce0`
- `0x180044080`
- `0x180044400`
- `0x180044740`
- `0x180044a20`
- `0x180059348`
- `0x180059640`
- `0x18005a220`
- `0x18005a354`
- `0x18005c7b0`
- `0x180064fc0`
- `0x1800651c4`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x180018ad8`
- `0x18001c1e4`
- `0x18002de18`
- `0x18002def8`

## string_xrefs

- `0x180018af2`: `::ReportReadWriteMultipleError`
- `0x180018b04`: `ReportReadWriteMultipleError`
- `0x180018b7c`: `%s, ReadMultiple property not found`
- `0x180018b9e`: `%s, ReadMultiple property not found`
- `0x180018bba`: `%s, WriteMultiple returned S_FALSE, %s`
- `0x180018bdc`: `%s, WriteMultiple returned S_FALSE, %s`
- `0x180018b43`: `%s, ReadMultiple property not found, %s`
- `0x180018b65`: `%s, ReadMultiple property not found, %s`
- `0x180018c24`: `%s, ReadMultiple failed, %s Error 0x%X`
- `0x180018c4d`: `%s, ReadMultiple failed, %s Error 0x%X`
- `0x180018c59`: `%s, WriteMultiple failed, %s Error 0x%X`
- `0x180018c82`: `%s, WriteMultiple failed, %s Error 0x%X`
- `0x180018be5`: `%s, WriteMultiple returned S_FALSE`
- `0x180018c07`: `%s, WriteMultiple returned S_FALSE`

## pseudocode

```c
void __fastcall ReportReadWriteMultipleError(
        int a1,
        char *a2,
        char *a3,
        int a4,
        unsigned int a5,
        const struct tagPROPSPEC *const a6)
{
  char ***v10; // rax
  char *v11; // rdx
  __int64 v12; // r8
  char *v13; // rbx
  void *v14; // rdx
  void **v15; // rax
  void *v16; // rdx
  __int64 v17; // rcx
  char *v18; // rbx
  void *v19; // rdx
  char *v20; // rbx
  void *v21; // rdx
  char *v22; // rbx
  void *v23; // rdx
  char *v24; // rbx
  void *v25; // rdx
  char *v26; // rbx
  void *v27; // rdx
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  const wchar_t *NameFromWiaPropId; // rax
  int v36; // ecx
  char *v37; // rbx
  void *v38; // rdx
  char *v39; // rbx
  void *v40; // rdx
  char *v41; // rbx
  void *v42; // rdx
  void **v43; // rax
  void *v44; // rdx
  __int64 v45; // rcx
  unsigned int v46; // ebp
  __int64 v47; // r15
  char *v48; // rbx
  void *v49; // rdx
  unsigned __int16 *v50; // rax
  unsigned int v51; // ecx
  void **v52; // rax
  void *v53; // rdx
  __int64 v54; // rcx
  char *v55; // rbx
  void *v56; // rdx
  char *v57; // rbx
  void *v58; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-A8h]
  _BYTE v60[152]; // [rsp+30h] [rbp-98h] BYREF

  v10 = (char ***)WiaTrace_Trace("::ReportReadWriteMultipleError");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v60, v11, v12, (char **)"ReportReadWriteMultipleError", lpMem, v10);
  if ( a1 < 0 )
  {
    if ( a4 )
    {
      if ( !a3 )
        a3 = "(null)";
      v24 = (char *)WiaTrace_TraceLog("%s, ReadMultiple failed, %s Error 0x%X");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v24);
      WiaTrcLib::Free((WiaTrcLib *)v24, v25);
      v15 = (void **)WiaTrace_Trace("%s, ReadMultiple failed, %s Error 0x%X", a2, a3, (unsigned int)a1);
    }
    else
    {
      if ( !a3 )
        a3 = "(null)";
      v26 = (char *)WiaTrace_TraceLog("%s, WriteMultiple failed, %s Error 0x%X");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v26);
      WiaTrcLib::Free((WiaTrcLib *)v26, v27);
      v15 = (void **)WiaTrace_Trace("%s, WriteMultiple failed, %s Error 0x%X", a2, a3, (unsigned int)a1);
    }
  }
  else
  {
    if ( a1 != 1 )
      goto LABEL_34;
    if ( a4 )
    {
      if ( a3 )
      {
        v13 = (char *)WiaTrace_TraceLog("%s, ReadMultiple property not found, %s");
        WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v13);
        WiaTrcLib::Free((WiaTrcLib *)v13, v14);
        v15 = (void **)WiaTrace_Trace("%s, ReadMultiple property not found, %s", a2, a3);
      }
      else
      {
        v18 = (char *)WiaTrace_TraceLog("%s, ReadMultiple property not found");
        WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v18);
        WiaTrcLib::Free((WiaTrcLib *)v18, v19);
        v15 = (void **)WiaTrace_Trace("%s, ReadMultiple property not found", a2);
      }
    }
    else if ( a3 )
    {
      v20 = (char *)WiaTrace_TraceLog("%s, WriteMultiple returned S_FALSE, %s");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v20);
      WiaTrcLib::Free((WiaTrcLib *)v20, v21);
      v15 = (void **)WiaTrace_Trace("%s, WriteMultiple returned S_FALSE, %s", a2, a3);
    }
    else
    {
      v22 = (char *)WiaTrace_TraceLog("%s, WriteMultiple returned S_FALSE");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v22);
      WiaTrcLib::Free((WiaTrcLib *)v22, v23);
      v15 = (void **)WiaTrace_Trace("%s, WriteMultiple returned S_FALSE", a2);
    }
  }
  WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"ReportReadWriteMultipleError", 1, v15);
  if ( !a5 )
  {
    v28 = (char *)WiaTrace_TraceLog("  count of PROPSPEC's is zero");
    WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v28);
    WiaTrcLib::Free((WiaTrcLib *)v28, v29);
    v30 = (void **)WiaTrace_Trace("  count of PROPSPEC's is zero");
LABEL_25:
    WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"ReportReadWriteMultipleError", 1, v30);
    goto LABEL_34;
  }
  if ( a5 == 1 )
  {
    if ( a6->ulKind == 1 )
    {
      GetNameFromWiaPropId(a6->propid);
      v33 = (char *)WiaTrace_TraceLog("  property ID: %d, property name: %S");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v33);
      WiaTrcLib::Free((WiaTrcLib *)v33, v34);
      NameFromWiaPropId = GetNameFromWiaPropId(a6->propid);
      v30 = (void **)WiaTrace_Trace("  property ID: %d, property name: %S", v36, NameFromWiaPropId);
    }
    else if ( a6->ulKind )
    {
      v39 = (char *)WiaTrace_TraceLog("  bad property specification");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v39);
      WiaTrcLib::Free((WiaTrcLib *)v39, v40);
      v30 = (void **)WiaTrace_Trace("  bad property specification");
    }
    else
    {
      v37 = (char *)WiaTrace_TraceLog("  property name: %S");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v37);
      WiaTrcLib::Free((WiaTrcLib *)v37, v38);
      v30 = (void **)WiaTrace_Trace("  property name: %S", a6->lpwstr);
    }
    goto LABEL_25;
  }
  v41 = (char *)WiaTrace_TraceLog("  count of PROPSPEC's is: %d");
  WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v41);
  WiaTrcLib::Free((WiaTrcLib *)v41, v42);
  v43 = (void **)WiaTrace_Trace("  count of PROPSPEC's is: %d", a5);
  WiaTrace_ProcessTrace_Ex(v45, v44, (void *)"ReportReadWriteMultipleError", 1, v43);
  v46 = 0;
  v47 = 0;
  do
  {
    if ( a6[v47].ulKind == 1 )
    {
      GetNameFromWiaPropId(a6[v47].propid);
      v48 = (char *)WiaTrace_TraceLog("  property ID: %d, property name: %S");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v48);
      WiaTrcLib::Free((WiaTrcLib *)v48, v49);
      v50 = GetNameFromWiaPropId(a6[v47].propid);
      v52 = (void **)WiaTrace_Trace("  property ID: %d, property name: %S", v51, v50);
    }
    else if ( a6[v47].ulKind )
    {
      v57 = (char *)WiaTrace_TraceLog("  index: %d,  bad property specification");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v57);
      WiaTrcLib::Free((WiaTrcLib *)v57, v58);
      v52 = (void **)WiaTrace_Trace("  index: %d,  bad property specification", v46);
    }
    else
    {
      v55 = (char *)WiaTrace_TraceLog("  index: %d,  property name: %S");
      WriteDbgTraceErrorWI("ReportReadWriteMultipleError", v55);
      WiaTrcLib::Free((WiaTrcLib *)v55, v56);
      v52 = (void **)WiaTrace_Trace("  index: %d,  property name: %S", v46, a6[v47].lpwstr);
    }
    WiaTrace_ProcessTrace_Ex(v54, v53, (void *)"ReportReadWriteMultipleError", 1, v52);
    ++v46;
    ++v47;
  }
  while ( v46 < a5 );
LABEL_34:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v60);
}

```

## disassembly

```asm
0x180018ad8  push    rbx
0x180018ada  push    rbp
0x180018adb  push    rsi
0x180018adc  push    rdi
0x180018add  push    r12
0x180018adf  push    r13
0x180018ae1  push    r14
0x180018ae3  push    r15
0x180018ae5  sub     rsp, 88h
0x180018aec  mov     r14d, ecx
0x180018aef  mov     ebx, r9d
0x180018af2  lea     rcx, aReportreadwrit_0; "::ReportReadWriteMultipleError"
0x180018af9  mov     rsi, r8
0x180018afc  mov     rbp, rdx
0x180018aff  call    WiaTrace_Trace
0x180018b04  lea     r13, aReportreadwrit; "ReportReadWriteMultipleError"
0x180018b0b  mov     [rsp+0C8h+var_A0], rax; struct tagWiaTraceData_Type *
0x180018b10  mov     r9, r13; char *
0x180018b13  lea     rcx, [rsp+0C8h+var_98]; this
0x180018b18  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180018b1d  test    r14d, r14d
0x180018b20  js      loc_180018C10
0x180018b26  mov     edi, 1
0x180018b2b  cmp     r14d, edi
0x180018b2e  jnz     loc_180018F01
0x180018b34  mov     rdx, rbp
0x180018b37  test    ebx, ebx
0x180018b39  jz      short loc_180018BB2
0x180018b3b  test    rsi, rsi
0x180018b3e  jz      short loc_180018B7C
0x180018b40  mov     r8, rsi
0x180018b43  lea     rcx, aSReadmultipleP; "%s, ReadMultiple property not found, %s"
0x180018b4a  call    WiaTrace_TraceLog
0x180018b4f  mov     rdx, rax; char *
0x180018b52  mov     rcx, r13; char *
0x180018b55  mov     rbx, rax
0x180018b58  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018b5d  mov     rcx, rbx; this
0x180018b60  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018b65  lea     rcx, aSReadmultipleP; "%s, ReadMultiple property not found, %s"
0x180018b6c  mov     rdx, rbp
0x180018b6f  mov     r8, rsi
0x180018b72  call    WiaTrace_Trace
0x180018b77  jmp     loc_180018C9C
0x180018b7c  lea     rcx, aSReadmultipleP_0; "%s, ReadMultiple property not found"
0x180018b83  call    WiaTrace_TraceLog
0x180018b88  mov     rdx, rax; char *
0x180018b8b  mov     rcx, r13; char *
0x180018b8e  mov     rbx, rax
0x180018b91  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018b96  mov     rcx, rbx; this
0x180018b99  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018b9e  lea     rcx, aSReadmultipleP_0; "%s, ReadMultiple property not found"
0x180018ba5  mov     rdx, rbp
0x180018ba8  call    WiaTrace_Trace
0x180018bad  jmp     loc_180018C9C
0x180018bb2  test    rsi, rsi
0x180018bb5  jz      short loc_180018BE5
0x180018bb7  mov     r8, rsi
0x180018bba  lea     rcx, aSWritemultiple; "%s, WriteMultiple returned S_FALSE, %s"
0x180018bc1  call    WiaTrace_TraceLog
0x180018bc6  mov     rdx, rax; char *
0x180018bc9  mov     rcx, r13; char *
0x180018bcc  mov     rbx, rax
0x180018bcf  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018bd4  mov     rcx, rbx; this
0x180018bd7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018bdc  lea     rcx, aSWritemultiple; "%s, WriteMultiple returned S_FALSE, %s"
0x180018be3  jmp     short loc_180018B6C
0x180018be5  lea     rcx, aSWritemultiple_1; "%s, WriteMultiple returned S_FALSE"
0x180018bec  call    WiaTrace_TraceLog
0x180018bf1  mov     rdx, rax; char *
0x180018bf4  mov     rcx, r13; char *
0x180018bf7  mov     rbx, rax
0x180018bfa  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018bff  mov     rcx, rbx; this
0x180018c02  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018c07  lea     rcx, aSWritemultiple_1; "%s, WriteMultiple returned S_FALSE"
0x180018c0e  jmp     short loc_180018BA5
0x180018c10  lea     rax, aNull_1; "(null)"
0x180018c17  mov     r9d, r14d
0x180018c1a  mov     rdx, rbp
0x180018c1d  test    ebx, ebx
0x180018c1f  jz      short loc_180018C56
0x180018c21  test    rsi, rsi
0x180018c24  lea     rcx, aSReadmultipleF; "%s, ReadMultiple failed, %s Error 0x%X"
0x180018c2b  cmovz   rsi, rax
0x180018c2f  mov     r8, rsi
0x180018c32  call    WiaTrace_TraceLog
0x180018c37  mov     rdx, rax; char *
0x180018c3a  mov     rcx, r13; char *
0x180018c3d  mov     rbx, rax
0x180018c40  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018c45  mov     rcx, rbx; this
0x180018c48  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018c4d  lea     rcx, aSReadmultipleF; "%s, ReadMultiple failed, %s Error 0x%X"
0x180018c54  jmp     short loc_180018C89
0x180018c56  test    rsi, rsi
0x180018c59  lea     rcx, aSWritemultiple_0; "%s, WriteMultiple failed, %s Error 0x%X"
0x180018c60  cmovz   rsi, rax
0x180018c64  mov     r8, rsi
0x180018c67  call    WiaTrace_TraceLog
0x180018c6c  mov     rdx, rax; char *
0x180018c6f  mov     rcx, r13; char *
0x180018c72  mov     rbx, rax
0x180018c75  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018c7a  mov     rcx, rbx; this
0x180018c7d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018c82  lea     rcx, aSWritemultiple_0; "%s, WriteMultiple failed, %s Error 0x%X"
0x180018c89  mov     r9d, r14d
0x180018c8c  mov     r8, rsi
0x180018c8f  mov     rdx, rbp
0x180018c92  call    WiaTrace_Trace
0x180018c97  mov     edi, 1
0x180018c9c  mov     r9d, edi; int
0x180018c9f  mov     [rsp+0C8h+lpMem], rax; lpMem
0x180018ca4  mov     r8, r13; int
0x180018ca7  call    WiaTrace_ProcessTrace_Ex
0x180018cac  mov     esi, [rsp+0C8h+arg_20]
0x180018cb3  test    esi, esi
0x180018cb5  jnz     short loc_180018CE5
0x180018cb7  lea     rcx, aCountOfPropspe; "  count of PROPSPEC's is zero"
0x180018cbe  call    WiaTrace_TraceLog
0x180018cc3  mov     rdx, rax; char *
0x180018cc6  mov     rcx, r13; char *
0x180018cc9  mov     rbx, rax
0x180018ccc  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018cd1  mov     rcx, rbx; this
0x180018cd4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018cd9  lea     rcx, aCountOfPropspe; "  count of PROPSPEC's is zero"
0x180018ce0  jmp     loc_180018DA9
0x180018ce5  cmp     esi, edi
0x180018ce7  jnz     loc_180018DC3
0x180018ced  mov     rsi, [rsp+0C8h+arg_28]
0x180018cf5  cmp     [rsi], edi
0x180018cf7  jnz     short loc_180018D43
0x180018cf9  mov     ecx, [rsi+8]; unsigned int
0x180018cfc  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x180018d01  mov     edx, ecx
0x180018d03  mov     r8, rax
0x180018d06  lea     rcx, aPropertyIdDPro; "  property ID: %d, property name: %S"
0x180018d0d  call    WiaTrace_TraceLog
0x180018d12  mov     rdx, rax; char *
0x180018d15  mov     rcx, r13; char *
0x180018d18  mov     rbx, rax
0x180018d1b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018d20  mov     rcx, rbx; this
0x180018d23  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018d28  mov     ecx, [rsi+8]; unsigned int
0x180018d2b  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x180018d30  mov     edx, ecx
0x180018d32  mov     r8, rax
0x180018d35  lea     rcx, aPropertyIdDPro; "  property ID: %d, property name: %S"
0x180018d3c  call    WiaTrace_Trace
0x180018d41  jmp     short loc_180018DAE
0x180018d43  cmp     dword ptr [rsi], 0
0x180018d46  jnz     short loc_180018D80
0x180018d48  mov     rdx, [rsi+8]
0x180018d4c  lea     rcx, aPropertyNameS; "  property name: %S"
0x180018d53  call    WiaTrace_TraceLog
0x180018d58  mov     rdx, rax; char *
0x180018d5b  mov     rcx, r13; char *
0x180018d5e  mov     rbx, rax
0x180018d61  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018d66  mov     rcx, rbx; this
0x180018d69  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018d6e  mov     rdx, [rsi+8]
0x180018d72  lea     rcx, aPropertyNameS; "  property name: %S"
0x180018d79  call    WiaTrace_Trace
0x180018d7e  jmp     short loc_180018DAE
0x180018d80  lea     rcx, aBadPropertySpe; "  bad property specification"
0x180018d87  call    WiaTrace_TraceLog
0x180018d8c  mov     rdx, rax; char *
0x180018d8f  mov     rcx, r13; char *
0x180018d92  mov     rbx, rax
0x180018d95  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018d9a  mov     rcx, rbx; this
0x180018d9d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018da2  lea     rcx, aBadPropertySpe; "  bad property specification"
0x180018da9  call    WiaTrace_Trace
0x180018dae  mov     r9d, edi; int
0x180018db1  mov     [rsp+0C8h+lpMem], rax; lpMem
0x180018db6  mov     r8, r13; int
0x180018db9  call    WiaTrace_ProcessTrace_Ex
0x180018dbe  jmp     loc_180018F01
0x180018dc3  mov     r12, [rsp+0C8h+arg_28]
0x180018dcb  lea     rcx, aCountOfPropspe_0; "  count of PROPSPEC's is: %d"
0x180018dd2  mov     edx, esi
0x180018dd4  call    WiaTrace_TraceLog
0x180018dd9  mov     rdx, rax; char *
0x180018ddc  mov     rcx, r13; char *
0x180018ddf  mov     rbx, rax
0x180018de2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018de7  mov     rcx, rbx; this
0x180018dea  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018def  mov     edx, esi
0x180018df1  lea     rcx, aCountOfPropspe_0; "  count of PROPSPEC's is: %d"
0x180018df8  call    WiaTrace_Trace
0x180018dfd  mov     r9d, edi; int
0x180018e00  mov     [rsp+0C8h+lpMem], rax; lpMem
0x180018e05  mov     r8, r13; int
0x180018e08  call    WiaTrace_ProcessTrace_Ex
0x180018e0d  xor     ebp, ebp
0x180018e0f  test    esi, esi
0x180018e11  jz      loc_180018F01
0x180018e17  xor     r15d, r15d
0x180018e1a  mov     r14, r15
0x180018e1d  add     r14, r14
0x180018e20  cmp     [r12+r14*8], edi
0x180018e24  jnz     short loc_180018E74
0x180018e26  mov     ecx, [r12+r14*8+8]; unsigned int
0x180018e2b  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x180018e30  mov     edx, ecx
0x180018e32  mov     r8, rax
0x180018e35  lea     rcx, aPropertyIdDPro; "  property ID: %d, property name: %S"
0x180018e3c  call    WiaTrace_TraceLog
0x180018e41  mov     rdx, rax; char *
0x180018e44  mov     rcx, r13; char *
0x180018e47  mov     rbx, rax
0x180018e4a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018e4f  mov     rcx, rbx; this
0x180018e52  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018e57  mov     ecx, [r12+r14*8+8]; unsigned int
0x180018e5c  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x180018e61  mov     edx, ecx
0x180018e63  mov     r8, rax
0x180018e66  lea     rcx, aPropertyIdDPro; "  property ID: %d, property name: %S"
0x180018e6d  call    WiaTrace_Trace
0x180018e72  jmp     short loc_180018EE4
0x180018e74  cmp     dword ptr [r12+r14*8], 0
0x180018e79  mov     edx, ebp
0x180018e7b  jnz     short loc_180018EB4
0x180018e7d  mov     r8, [r12+r14*8+8]
0x180018e82  lea     rcx, aIndexDProperty; "  index: %d,  property name: %S"
0x180018e89  call    WiaTrace_TraceLog
0x180018e8e  mov     rdx, rax; char *
0x180018e91  mov     rcx, r13; char *
0x180018e94  mov     rbx, rax
0x180018e97  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018e9c  mov     rcx, rbx; this
0x180018e9f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018ea4  mov     r8, [r12+r14*8+8]
0x180018ea9  lea     rcx, aIndexDProperty; "  index: %d,  property name: %S"
0x180018eb0  mov     edx, ebp
0x180018eb2  jmp     short loc_180018E6D
0x180018eb4  lea     rcx, aIndexDBadPrope; "  index: %d,  bad property specificatio"...
0x180018ebb  call    WiaTrace_TraceLog
0x180018ec0  mov     rdx, rax; char *
0x180018ec3  mov     rcx, r13; char *
0x180018ec6  mov     rbx, rax
0x180018ec9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180018ece  mov     rcx, rbx; this
0x180018ed1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180018ed6  mov     edx, ebp
0x180018ed8  lea     rcx, aIndexDBadPrope; "  index: %d,  bad property specificatio"...
0x180018edf  call    WiaTrace_Trace
0x180018ee4  mov     r9d, edi; int
0x180018ee7  mov     [rsp+0C8h+lpMem], rax; lpMem
0x180018eec  mov     r8, r13; int
0x180018eef  call    WiaTrace_ProcessTrace_Ex
0x180018ef4  add     ebp, edi
0x180018ef6  add     r15, rdi
0x180018ef9  cmp     ebp, esi
0x180018efb  jb      loc_180018E1A
0x180018f01  lea     rcx, [rsp+0C8h+var_98]; this
0x180018f06  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180018f0b  add     rsp, 88h
0x180018f12  pop     r15
0x180018f14  pop     r14
0x180018f16  pop     r13
0x180018f18  pop     r12
0x180018f1a  pop     rdi
0x180018f1b  pop     rsi
0x180018f1c  pop     rbp
0x180018f1d  pop     rbx
0x180018f1e  retn
```
