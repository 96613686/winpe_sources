# wiasReadPropBin

- ea: `0x180041eb0`
- end: `0x180042136`
- name: `wiasReadPropBin`
- size: `646`
- prototype: `__int64 __usercall@<rax>(CWiaItem *this@<rcx>, int)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800189cc`
- `0x180018ad8`
- `0x18001f614`
- `0x18002de18`
- `0x18002def8`
- `0x180041eb0`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1800420c6`
- `ole32!PropVariantClear` at `0x1800420c6`

## string_xrefs

- `0x180041ed4`: `::wiasReadPropBin`
- `0x180041ee6`: `wiasReadPropBin`
- `0x180041f45`: `wiasReadPropBin`
- `0x180041f92`: `wiasReadPropBin`
- `0x180042087`: `wiasReadPropBin`
- `0x1800420b6`: `wiasReadPropBin`
- `0x1800420ee`: `wiasReadPropBin`
- `0x180041f0c`: `wiasReadPropBin, invalid pItem`
- `0x180041f2e`: `wiasReadPropBin, invalid pItem`
- `0x180041f5b`: `wiasReadPropBin, invalid ppbVal pointer`
- `0x180041f7d`: `wiasReadPropBin, invalid ppbVal pointer`
- `0x180042078`: `wiasReadPropBin, invalid property type: %X`
- `0x1800420a2`: `wiasReadPropBin, invalid property type: %X`

## pseudocode

```c
__int64 __fastcall wiasReadPropBin(struct IWiaItem *this, PROPID a2, _QWORD *a3, _QWORD *a4, int a5)
{
  char ***v9; // rax
  char *v10; // rdx
  __int64 v11; // r8
  int v12; // esi
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
  int ItemPropStreams; // eax
  int v24; // ebx
  char *v25; // rbx
  void *v26; // rdx
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  int v30; // esi
  unsigned int lpMem; // [rsp+20h] [rbp-61h]
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-51h] BYREF
  __int64 v34; // [rsp+40h] [rbp-41h]
  struct IPropertyStorage *v35; // [rsp+48h] [rbp-39h] BYREF
  struct tagPROPSPEC v36; // [rsp+50h] [rbp-31h] BYREF
  _BYTE v37[80]; // [rsp+60h] [rbp-21h] BYREF
  struct IPropertyStorage *v38; // [rsp+E0h] [rbp+5Fh] BYREF

  v9 = (char ***)WiaTrace_Trace("::wiasReadPropBin");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v37, v10, v11, (char **)"wiasReadPropBin", lpMem, v9);
  v12 = ValidateWiaItem(this);
  if ( v12 >= 0 )
  {
    if ( !a3 )
    {
      v18 = (char *)WiaTrace_TraceLog("wiasReadPropBin, invalid ppbVal pointer");
      WriteDbgTraceErrorWI("wiasReadPropBin", v18);
      WiaTrcLib::Free((WiaTrcLib *)v18, v19);
      v20 = (void **)WiaTrace_Trace("wiasReadPropBin, invalid ppbVal pointer");
      WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"wiasReadPropBin", 1, v20);
      v12 = -2147467261;
      goto LABEL_20;
    }
    *a3 = 0;
    v38 = 0;
    v35 = 0;
    ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, &v38, 0, 0, &v35);
    if ( ItemPropStreams < 0 )
    {
      v12 = ItemPropStreams;
      goto LABEL_20;
    }
    v34 = 0;
    v36 = 0;
    v36.propid = a2;
    v36.ulKind = 1;
    *(_OWORD *)pvar = 0;
    v24 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, PROPVARIANT *))v38->lpVtbl->ReadMultiple)(
            v38,
            1,
            &v36,
            pvar);
    if ( !v24 )
    {
      if ( LOWORD(pvar[0]) != 4113 )
        goto LABEL_13;
      *a3 = v34;
      if ( !a4 )
      {
LABEL_19:
        v12 = v24;
        goto LABEL_20;
      }
      v24 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, PROPVARIANT *))v35->lpVtbl->ReadMultiple)(
              v35,
              1,
              &v36,
              pvar);
      if ( !v24 )
      {
        if ( LOWORD(pvar[0]) == 4113 )
        {
          *a4 = v34;
          goto LABEL_19;
        }
LABEL_13:
        v25 = (char *)WiaTrace_TraceLog("wiasReadPropBin, invalid property type: %X");
        WriteDbgTraceErrorWI("wiasReadPropBin", v25);
        WiaTrcLib::Free((WiaTrcLib *)v25, v26);
        v27 = (void **)WiaTrace_Trace("wiasReadPropBin, invalid property type: %X", LOWORD(pvar[0]));
        WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"wiasReadPropBin", 1, v27);
        PropVariantClear(pvar);
        v12 = -2147024809;
        goto LABEL_20;
      }
    }
    v30 = a5;
    if ( v24 == 1 && a5 || v24 < 0 )
    {
      ReportReadWriteMultipleError(v24, "wiasReadPropBin", 0, 1, 1u, &v36);
      if ( v30 )
        v24 = -2147024809;
    }
    goto LABEL_19;
  }
  v13 = (char *)WiaTrace_TraceLog("wiasReadPropBin, invalid pItem");
  WriteDbgTraceErrorWI("wiasReadPropBin", v13);
  WiaTrcLib::Free((WiaTrcLib *)v13, v14);
  v15 = (void **)WiaTrace_Trace("wiasReadPropBin, invalid pItem");
  WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"wiasReadPropBin", 1, v15);
LABEL_20:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v37);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180041eb0  mov     [rsp-8+arg_8], rbx
0x180041eb5  mov     [rsp-8+arg_10], rsi
0x180041eba  push    rbp
0x180041ebb  push    rdi
0x180041ebc  push    r12
0x180041ebe  push    r14
0x180041ec0  push    r15
0x180041ec2  lea     rbp, [rsp-2Fh]
0x180041ec7  sub     rsp, 0B0h
0x180041ece  mov     rbx, rcx
0x180041ed1  mov     r15, r9
0x180041ed4  lea     rcx, aWiasreadpropbi_4; "::wiasReadPropBin"
0x180041edb  mov     r14, r8
0x180041ede  mov     r12d, edx
0x180041ee1  call    WiaTrace_Trace
0x180041ee6  lea     rdi, aWiasreadpropbi_2; "wiasReadPropBin"
0x180041eed  mov     [rsp+0D0h+var_A8], rax; struct tagWiaTraceData_Type *
0x180041ef2  mov     r9, rdi; char *
0x180041ef5  lea     rcx, [rbp+4Fh+var_70]; this
0x180041ef9  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180041efe  mov     rcx, rbx; struct IWiaItem *
0x180041f01  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180041f06  mov     esi, eax
0x180041f08  test    eax, eax
0x180041f0a  jns     short loc_180041F56
0x180041f0c  lea     rcx, aWiasreadpropbi_0; "wiasReadPropBin, invalid pItem"
0x180041f13  call    WiaTrace_TraceLog
0x180041f18  mov     rdx, rax; char *
0x180041f1b  mov     rcx, rdi; char *
0x180041f1e  mov     rbx, rax
0x180041f21  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180041f26  mov     rcx, rbx; this
0x180041f29  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180041f2e  lea     rcx, aWiasreadpropbi_0; "wiasReadPropBin, invalid pItem"
0x180041f35  call    WiaTrace_Trace
0x180041f3a  mov     r9d, 1; int
0x180041f40  mov     [rsp+0D0h+lpMem], rax; lpMem
0x180041f45  lea     r8, aWiasreadpropbi_2; "wiasReadPropBin"
0x180041f4c  call    WiaTrace_ProcessTrace_Ex
0x180041f51  jmp     loc_18004210F
0x180041f56  test    r14, r14
0x180041f59  jnz     short loc_180041FA8
0x180041f5b  lea     rcx, aWiasreadpropbi_1; "wiasReadPropBin, invalid ppbVal pointer"
0x180041f62  call    WiaTrace_TraceLog
0x180041f67  mov     rdx, rax; char *
0x180041f6a  mov     rcx, rdi; char *
0x180041f6d  mov     rbx, rax
0x180041f70  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180041f75  mov     rcx, rbx; this
0x180041f78  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180041f7d  lea     rcx, aWiasreadpropbi_1; "wiasReadPropBin, invalid ppbVal pointer"
0x180041f84  call    WiaTrace_Trace
0x180041f89  lea     r9d, [r14+1]; int
0x180041f8d  mov     [rsp+0D0h+lpMem], rax; lpMem
0x180041f92  lea     r8, aWiasreadpropbi_2; "wiasReadPropBin"
0x180041f99  call    WiaTrace_ProcessTrace_Ex
0x180041f9e  mov     esi, 80004003h
0x180041fa3  jmp     loc_18004210F
0x180041fa8  lea     rax, [rbp+4Fh+var_88]
0x180041fac  mov     qword ptr [r14], 0
0x180041fb3  xor     r9d, r9d; struct IPropertyStorage **
0x180041fb6  mov     [rsp+0D0h+lpMem], rax; struct IPropertyStorage **
0x180041fbb  xor     r8d, r8d; struct IPropertyStorage **
0x180041fbe  mov     [rbp+4Fh+arg_0], 0
0x180041fc6  lea     rdx, [rbp+4Fh+arg_0]; struct IPropertyStorage **
0x180041fca  mov     [rbp+4Fh+var_88], 0
0x180041fd2  mov     rcx, rbx; this
0x180041fd5  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x180041fda  test    eax, eax
0x180041fdc  jns     short loc_180041FE5
0x180041fde  mov     esi, eax
0x180041fe0  jmp     loc_18004210F
0x180041fe5  mov     rcx, [rbp+4Fh+arg_0]
0x180041fe9  lea     r9, [rbp+4Fh+pvar]
0x180041fed  xor     eax, eax
0x180041fef  lea     r8, [rbp+4Fh+var_80]
0x180041ff3  mov     [rbp+4Fh+var_90], rax
0x180041ff7  xorps   xmm0, xmm0
0x180041ffa  movups  xmmword ptr [rbp+4Fh+var_80.ulKind], xmm0
0x180041ffe  mov     dword ptr [rbp+4Fh+var_80.8], r12d
0x180042002  lea     edi, [rax+1]
0x180042005  xorps   xmm1, xmm1
0x180042008  mov     [rbp+4Fh+var_80.ulKind], edi
0x18004200b  mov     edx, edi
0x18004200d  movups  xmmword ptr [rbp+4Fh+pvar], xmm1
0x180042011  mov     rax, [rcx]
0x180042014  mov     rax, [rax+18h]
0x180042018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004201d  mov     ebx, eax
0x18004201f  test    eax, eax
0x180042021  jnz     loc_1800420D3
0x180042027  mov     esi, 1011h
0x18004202c  cmp     word ptr [rbp+4Fh+pvar], si
0x180042030  jnz     short loc_180042074
0x180042032  mov     rcx, [rbp+4Fh+var_90]
0x180042036  mov     [r14], rcx
0x180042039  test    r15, r15
0x18004203c  jz      loc_18004210D
0x180042042  mov     rcx, [rbp+4Fh+var_88]
0x180042046  lea     r9, [rbp+4Fh+pvar]
0x18004204a  lea     r8, [rbp+4Fh+var_80]
0x18004204e  mov     edx, edi
0x180042050  mov     rax, [rcx]
0x180042053  mov     rax, [rax+18h]
0x180042057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004205c  mov     ebx, eax
0x18004205e  test    eax, eax
0x180042060  jnz     short loc_1800420D3
0x180042062  cmp     word ptr [rbp+4Fh+pvar], si
0x180042066  jnz     short loc_180042074
0x180042068  mov     rax, [rbp+4Fh+var_90]
0x18004206c  mov     [r15], rax
0x18004206f  jmp     loc_18004210D
0x180042074  movzx   edx, word ptr [rbp+4Fh+pvar]
0x180042078  lea     rcx, aWiasreadpropbi_3; "wiasReadPropBin, invalid property type:"...
0x18004207f  call    WiaTrace_TraceLog
0x180042084  mov     rdx, rax; char *
0x180042087  lea     rcx, aWiasreadpropbi_2; "wiasReadPropBin"
0x18004208e  mov     rbx, rax
0x180042091  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180042096  mov     rcx, rbx; this
0x180042099  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004209e  movzx   edx, word ptr [rbp+4Fh+pvar]
0x1800420a2  lea     rcx, aWiasreadpropbi_3; "wiasReadPropBin, invalid property type:"...
0x1800420a9  call    WiaTrace_Trace
0x1800420ae  mov     r9d, edi; int
0x1800420b1  mov     [rsp+0D0h+lpMem], rax; lpMem
0x1800420b6  lea     r8, aWiasreadpropbi_2; "wiasReadPropBin"
0x1800420bd  call    WiaTrace_ProcessTrace_Ex
0x1800420c2  lea     rcx, [rbp+4Fh+pvar]; pvar
0x1800420c6  call    cs:__imp_PropVariantClear
0x1800420cc  mov     esi, 80070057h
0x1800420d1  jmp     short loc_18004210F
0x1800420d3  mov     esi, [rbp+4Fh+arg_20]
0x1800420d6  cmp     ebx, edi
0x1800420d8  jnz     short loc_1800420DE
0x1800420da  test    esi, esi
0x1800420dc  jnz     short loc_1800420E2
0x1800420de  test    ebx, ebx
0x1800420e0  jns     short loc_18004210D
0x1800420e2  lea     rax, [rbp+4Fh+var_80]
0x1800420e6  mov     r9d, edi; int
0x1800420e9  mov     [rsp+0D0h+var_A8], rax; struct tagPROPSPEC *
0x1800420ee  lea     rdx, aWiasreadpropbi_2; "wiasReadPropBin"
0x1800420f5  xor     r8d, r8d; char *
0x1800420f8  mov     dword ptr [rsp+0D0h+lpMem], edi; unsigned int
0x1800420fc  mov     ecx, ebx; int
0x1800420fe  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x180042103  test    esi, esi
0x180042105  mov     eax, 80070057h
0x18004210a  cmovnz  ebx, eax
0x18004210d  mov     esi, ebx
0x18004210f  lea     rcx, [rbp+4Fh+var_70]; this
0x180042113  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180042118  lea     r11, [rsp+0D0h+var_20]
0x180042120  mov     eax, esi
0x180042122  mov     rbx, [r11+38h]
0x180042126  mov     rsi, [r11+40h]
0x18004212a  mov     rsp, r11
0x18004212d  pop     r15
0x18004212f  pop     r14
0x180042131  pop     r12
0x180042133  pop     rdi
0x180042134  pop     rbp
0x180042135  retn
```
