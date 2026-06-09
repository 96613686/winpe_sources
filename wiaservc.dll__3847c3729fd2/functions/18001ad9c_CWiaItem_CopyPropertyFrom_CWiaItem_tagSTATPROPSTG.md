# CWiaItem::CopyPropertyFrom(CWiaItem *,tagSTATPROPSTG &)

- ea: `0x18001ad9c`
- end: `0x18001b2b7`
- name: `?CopyPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@@Z`
- size: `1307`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, struct CWiaItem *, struct tagSTATPROPSTG *)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x18001901c`
- `0x180019eac`
- `0x180063688`
- `0x180064a6c`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18001ad9c`
- `0x18002de18`
- `0x18002def8`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18001af7c`
- `ole32!PropVariantClear` at `0x18001b05e`
- `ole32!PropVariantClear` at `0x18001b244`
- `ole32!PropVariantClear` at `0x18001af7c`
- `ole32!PropVariantClear` at `0x18001b05e`
- `ole32!PropVariantClear` at `0x18001b244`

## string_xrefs

- `0x18001adbb`: `CWiaItem::CopyPropertyFrom`
- `0x18001b18f`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) on the Access Storage failed (0x%X)`
- `0x18001b1b4`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) on the Access Storage failed (0x%X)`
- `0x18001b1c0`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) on the Valid Storage failed (0x%X)`
- `0x18001b1e5`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) on the Valid Storage failed (0x%X)`
- `0x18001b15e`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)`
- `0x18001b183`: `Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)`
- `0x18001b252`: `Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001b277`: `Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001b0c3`: `Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001b0e8`: `Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001b20f`: `Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001b234`: `Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001af15`: `Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001af3a`: `Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001b286`: `Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001b2ab`: `Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001afe5`: `Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`
- `0x18001b00a`: `Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::CopyPropertyFrom(CWiaItem *this, struct CWiaItem *a2, struct tagSTATPROPSTG *a3)
{
  int v6; // edi
  struct tagWiaTraceData_Type *v7; // rax
  char *v8; // rdx
  unsigned int v9; // r8d
  LPOLESTR lpwstrName; // rax
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
  char *v22; // rbx
  void *v23; // rdx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  char *v32; // rbx
  void *v33; // rdx
  void **v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  char *v37; // rbx
  void *v38; // rdx
  char *v39; // rbx
  void *v40; // rdx
  char *v41; // rbx
  void *v42; // rdx
  char *v43; // rbx
  void *v44; // rdx
  char *v45; // rbx
  void *v46; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-69h]
  int v48; // [rsp+30h] [rbp-59h] BYREF
  __int64 v49; // [rsp+38h] [rbp-51h]
  PROPVARIANT pvar[4]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v51[128]; // [rsp+60h] [rbp-29h] BYREF
  int v52; // [rsp+F8h] [rbp+6Fh] BYREF
  LPOLESTR v53; // [rsp+100h] [rbp+77h] BYREF

  v6 = 0;
  v7 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::CopyPropertyFrom");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v51, v8, v9, "CWiaItem::CopyPropertyFrom", lpMem, v7);
  if ( !a2 )
  {
    v6 = -2147467261;
    v27 = (char *)WiaTrace_TraceLog("NULL source (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v29 = (void **)WiaTrace_Trace("NULL source (0x%X)", -2147467261);
    WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaItem::CopyPropertyFrom", 1, v29);
  }
  v48 = 1;
  v49 = 0;
  LODWORD(v49) = a3->propid;
  v52 = v49;
  lpwstrName = a3->lpwstrName;
  v53 = a3->lpwstrName;
  if ( v6 >= 0 && lpwstrName )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, LPOLESTR *))(***((_QWORD ***)this + 27) + 56LL))(
           **((_QWORD **)this + 27),
           1,
           &v52,
           &v53);
    if ( v6 < 0 )
    {
      v32 = (char *)WiaTrace_TraceLog("Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v32);
      WiaTrcLib::Free((WiaTrcLib *)v32, v33);
      v34 = (void **)WiaTrace_Trace(
                       "Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) failed (0x%X)",
                       a3->propid,
                       (unsigned int)v6);
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, LPOLESTR *))(**(_QWORD **)(*((_QWORD *)this + 27) + 16LL)
                                                                         + 56LL))(
             *(_QWORD *)(*((_QWORD *)this + 27) + 16LL),
             1,
             &v52,
             &v53);
      if ( v6 < 0 )
      {
        v37 = (char *)WiaTrace_TraceLog("Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) on the Access S"
                                        "torage failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v37);
        WiaTrcLib::Free((WiaTrcLib *)v37, v38);
        v34 = (void **)WiaTrace_Trace(
                         "Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) on the Access Storage failed (0x%X)",
                         a3->propid,
                         (unsigned int)v6);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, LPOLESTR *))(**(_QWORD **)(*((_QWORD *)this + 27) + 8LL)
                                                                           + 56LL))(
               *(_QWORD *)(*((_QWORD *)this + 27) + 8LL),
               1,
               &v52,
               &v53);
        if ( v6 >= 0 )
          goto LABEL_8;
        v39 = (char *)WiaTrace_TraceLog("Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) on the Valid St"
                                        "orage failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v39);
        WiaTrcLib::Free((WiaTrcLib *)v39, v40);
        v34 = (void **)WiaTrace_Trace(
                         "Call to IWiaPropertyStorage::WritePropertyNames (1 prop, id: %u) on the Valid Storage failed (0x%X)",
                         a3->propid,
                         (unsigned int)v6);
      }
    }
    WiaTrace_ProcessTrace_Ex(v36, v35, (void *)"CWiaItem::CopyPropertyFrom", 1, v34);
  }
LABEL_8:
  memset(pvar, 0, 24);
  if ( v6 < 0 )
    goto LABEL_13;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *))(**(_QWORD **)(*((_QWORD *)a2 + 27) + 16LL)
                                                                        + 24LL))(
         *(_QWORD *)(*((_QWORD *)a2 + 27) + 16LL),
         1,
         &v48,
         pvar);
  if ( v6 < 0 )
  {
    v41 = (char *)WiaTrace_TraceLog("Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v41);
    WiaTrcLib::Free((WiaTrcLib *)v41, v42);
    v13 = (void **)WiaTrace_Trace(
                     "Call to AccessStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)",
                     (unsigned int)v49,
                     (unsigned int)v6);
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *, int))(**(_QWORD **)(*((_QWORD *)this + 27)
                                                                                             + 16LL)
                                                                               + 32LL))(
           *(_QWORD *)(*((_QWORD *)this + 27) + 16LL),
           1,
           &v48,
           pvar,
           2);
    if ( v6 >= 0 )
      goto LABEL_13;
    v11 = (char *)WiaTrace_TraceLog("Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v13 = (void **)WiaTrace_Trace(
                     "Call to AccessStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)",
                     (unsigned int)v49,
                     (unsigned int)v6);
  }
  WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CWiaItem::CopyPropertyFrom", 1, v13);
LABEL_13:
  if ( LOWORD(pvar[0]) )
    PropVariantClear(pvar);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *))(***((_QWORD ***)a2 + 27) + 24LL))(
           **((_QWORD **)a2 + 27),
           1,
           &v48,
           pvar);
    if ( v6 < 0 )
    {
      v43 = (char *)WiaTrace_TraceLog("Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v43);
      WiaTrcLib::Free((WiaTrcLib *)v43, v44);
      v24 = (void **)WiaTrace_Trace(
                       "Call to CurStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v49,
                       (unsigned int)v6);
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *, int))(***((_QWORD ***)this + 27) + 32LL))(
             **((_QWORD **)this + 27),
             1,
             &v48,
             pvar,
             2);
      if ( v6 >= 0 )
        goto LABEL_16;
      v22 = (char *)WiaTrace_TraceLog("Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v22);
      WiaTrcLib::Free((WiaTrcLib *)v22, v23);
      v24 = (void **)WiaTrace_Trace(
                       "Call to CurStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v49,
                       (unsigned int)v6);
    }
    WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"CWiaItem::CopyPropertyFrom", 1, v24);
  }
LABEL_16:
  if ( LOWORD(pvar[0]) )
    PropVariantClear(pvar);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *))(**(_QWORD **)(*((_QWORD *)a2 + 27) + 8LL)
                                                                          + 24LL))(
           *(_QWORD *)(*((_QWORD *)a2 + 27) + 8LL),
           1,
           &v48,
           pvar);
    if ( v6 < 0 )
    {
      v45 = (char *)WiaTrace_TraceLog("Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v45);
      WiaTrcLib::Free((WiaTrcLib *)v45, v46);
      v18 = (void **)WiaTrace_Trace(
                       "Call to ValidStg#IPropertyStorage::ReadMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v49,
                       (unsigned int)v6);
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, PROPVARIANT *, int))(**(_QWORD **)(*((_QWORD *)this + 27)
                                                                                               + 8LL)
                                                                                 + 32LL))(
             *(_QWORD *)(*((_QWORD *)this + 27) + 8LL),
             1,
             &v48,
             pvar,
             2);
      if ( v6 >= 0 )
        goto LABEL_23;
      v16 = (char *)WiaTrace_TraceLog("Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CopyPropertyFrom", v16);
      WiaTrcLib::Free((WiaTrcLib *)v16, v17);
      v18 = (void **)WiaTrace_Trace(
                       "Call to ValidStg#IPropertyStorage::WriteMultiple(1 prop, id: %u) failed (0x%X)",
                       (unsigned int)v49,
                       (unsigned int)v6);
    }
    WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"CWiaItem::CopyPropertyFrom", 1, v18);
  }
LABEL_23:
  if ( LOWORD(pvar[0]) )
    PropVariantClear(pvar);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v51);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ad9c  mov     [rsp-8+arg_0], rbx
0x18001ada1  push    rbp
0x18001ada2  push    rsi
0x18001ada3  push    rdi
0x18001ada4  push    r12
0x18001ada6  push    r13
0x18001ada8  push    r14
0x18001adaa  push    r15
0x18001adac  lea     rbp, [rsp-27h]
0x18001adb1  sub     rsp, 0B0h
0x18001adb8  mov     r14, rcx
0x18001adbb  lea     r13, aCwiaitemCopypr; "CWiaItem::CopyPropertyFrom"
0x18001adc2  mov     rcx, r13
0x18001adc5  mov     rsi, r8
0x18001adc8  mov     r15, rdx
0x18001adcb  xor     edi, edi
0x18001adcd  call    WiaTrace_Trace
0x18001add2  mov     r9, r13; char *
0x18001add5  mov     [rsp+0E0h+var_B8], rax; struct tagWiaTraceData_Type *
0x18001adda  lea     rcx, [rbp+57h+var_80]; this
0x18001adde  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18001ade3  lea     r12d, [rdi+1]
0x18001ade7  test    r15, r15
0x18001adea  jz      loc_18001B10F
0x18001adf0  xor     eax, eax
0x18001adf2  mov     [rbp+57h+var_B0], r12d
0x18001adf6  mov     [rbp+57h+var_A8], rax
0x18001adfa  mov     eax, [rsi+8]
0x18001adfd  mov     dword ptr [rbp+57h+var_A8], eax
0x18001ae00  mov     [rbp+57h+arg_8], eax
0x18001ae03  mov     rax, [rsi]
0x18001ae06  mov     [rbp+57h+arg_10], rax
0x18001ae0a  test    edi, edi
0x18001ae0c  js      loc_18001AE9E
0x18001ae12  test    rax, rax
0x18001ae15  jz      loc_18001AE9E
0x18001ae1b  mov     rax, [r14+0D8h]
0x18001ae22  lea     r9, [rbp+57h+arg_10]
0x18001ae26  lea     r8, [rbp+57h+arg_8]
0x18001ae2a  mov     edx, r12d
0x18001ae2d  mov     rcx, [rax]
0x18001ae30  mov     rax, [rcx]
0x18001ae33  mov     rax, [rax+38h]
0x18001ae37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae3c  mov     edi, eax
0x18001ae3e  test    eax, eax
0x18001ae40  js      loc_18001B15B
0x18001ae46  mov     rax, [r14+0D8h]
0x18001ae4d  lea     r9, [rbp+57h+arg_10]
0x18001ae51  lea     r8, [rbp+57h+arg_8]
0x18001ae55  mov     edx, r12d
0x18001ae58  mov     rcx, [rax+10h]
0x18001ae5c  mov     rax, [rcx]
0x18001ae5f  mov     rax, [rax+38h]
0x18001ae63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae68  mov     edi, eax
0x18001ae6a  test    eax, eax
0x18001ae6c  js      loc_18001B18C
0x18001ae72  mov     rax, [r14+0D8h]
0x18001ae79  lea     r9, [rbp+57h+arg_10]
0x18001ae7d  lea     r8, [rbp+57h+arg_8]
0x18001ae81  mov     edx, r12d
0x18001ae84  mov     rcx, [rax+8]
0x18001ae88  mov     rax, [rcx]
0x18001ae8b  mov     rax, [rax+38h]
0x18001ae8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae94  mov     edi, eax
0x18001ae96  test    eax, eax
0x18001ae98  js      loc_18001B1BD
0x18001ae9e  xor     eax, eax
0x18001aea0  xorps   xmm0, xmm0
0x18001aea3  mov     word ptr [rbp+57h+pvar], ax
0x18001aea7  movups  xmmword ptr [rbp+57h+pvar+2], xmm0
0x18001aeab  mov     [rbp+57h+pvar+10h], rax
0x18001aeaf  lea     esi, [rax+2]
0x18001aeb2  test    edi, edi
0x18001aeb4  js      loc_18001AF5C
0x18001aeba  mov     rax, [r15+0D8h]
0x18001aec1  lea     r9, [rbp+57h+pvar]
0x18001aec5  lea     r8, [rbp+57h+var_B0]
0x18001aec9  mov     edx, r12d
0x18001aecc  mov     rcx, [rax+10h]
0x18001aed0  mov     rax, [rcx]
0x18001aed3  mov     rax, [rax+18h]
0x18001aed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aedc  mov     edi, eax
0x18001aede  test    eax, eax
0x18001aee0  js      loc_18001B20C
0x18001aee6  mov     rax, [r14+0D8h]
0x18001aeed  lea     r9, [rbp+57h+pvar]
0x18001aef1  lea     r8, [rbp+57h+var_B0]
0x18001aef5  mov     dword ptr [rsp+0E0h+lpMem], esi
0x18001aef9  mov     edx, r12d
0x18001aefc  mov     rcx, [rax+10h]
0x18001af00  mov     rax, [rcx]
0x18001af03  mov     rax, [rax+20h]
0x18001af07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af0c  mov     edi, eax
0x18001af0e  test    eax, eax
0x18001af10  jns     short loc_18001AF5C
0x18001af12  mov     edx, dword ptr [rbp+57h+var_A8]
0x18001af15  lea     rcx, aCallToAccessst_0; "Call to AccessStg#IPropertyStorage::Wri"...
0x18001af1c  mov     r8d, eax
0x18001af1f  call    WiaTrace_TraceLog
0x18001af24  mov     rdx, rax; char *
0x18001af27  mov     rcx, r13; char *
0x18001af2a  mov     rbx, rax
0x18001af2d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001af32  mov     rcx, rbx; this
0x18001af35  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001af3a  lea     rcx, aCallToAccessst_0; "Call to AccessStg#IPropertyStorage::Wri"...
0x18001af41  mov     edx, dword ptr [rbp+57h+var_A8]
0x18001af44  mov     r8d, edi
0x18001af47  call    WiaTrace_Trace
0x18001af4c  mov     r9d, r12d; int
0x18001af4f  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18001af54  mov     r8, r13; int
0x18001af57  call    WiaTrace_ProcessTrace_Ex
0x18001af5c  xor     eax, eax
0x18001af5e  cmp     ax, word ptr [rbp+57h+pvar]
0x18001af62  jnz     loc_18001B240
0x18001af68  test    edi, edi
0x18001af6a  jns     loc_18001B066
0x18001af70  xor     eax, eax
0x18001af72  cmp     ax, word ptr [rbp+57h+pvar]
0x18001af76  jz      short loc_18001AF82
0x18001af78  lea     rcx, [rbp+57h+pvar]; pvar
0x18001af7c  call    cs:__imp_PropVariantClear
0x18001af82  test    edi, edi
0x18001af84  js      loc_18001B02C
0x18001af8a  mov     rax, [r15+0D8h]
0x18001af91  lea     r9, [rbp+57h+pvar]
0x18001af95  lea     r8, [rbp+57h+var_B0]
0x18001af99  mov     edx, r12d
0x18001af9c  mov     rcx, [rax+8]
0x18001afa0  mov     rax, [rcx]
0x18001afa3  mov     rax, [rax+18h]
0x18001afa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afac  mov     edi, eax
0x18001afae  test    eax, eax
0x18001afb0  js      loc_18001B283
0x18001afb6  mov     rax, [r14+0D8h]
0x18001afbd  lea     r9, [rbp+57h+pvar]
0x18001afc1  lea     r8, [rbp+57h+var_B0]
0x18001afc5  mov     dword ptr [rsp+0E0h+lpMem], esi
0x18001afc9  mov     edx, r12d
0x18001afcc  mov     rcx, [rax+8]
0x18001afd0  mov     rax, [rcx]
0x18001afd3  mov     rax, [rax+20h]
0x18001afd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afdc  mov     edi, eax
0x18001afde  test    eax, eax
0x18001afe0  jns     short loc_18001B02C
0x18001afe2  mov     edx, dword ptr [rbp+57h+var_A8]
0x18001afe5  lea     rcx, aCallToValidstg; "Call to ValidStg#IPropertyStorage::Writ"...
0x18001afec  mov     r8d, eax
0x18001afef  call    WiaTrace_TraceLog
0x18001aff4  mov     rdx, rax; char *
0x18001aff7  mov     rcx, r13; char *
0x18001affa  mov     rbx, rax
0x18001affd  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001b002  mov     rcx, rbx; this
0x18001b005  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b00a  lea     rcx, aCallToValidstg; "Call to ValidStg#IPropertyStorage::Writ"...
0x18001b011  mov     edx, dword ptr [rbp+57h+var_A8]
0x18001b014  mov     r8d, edi
0x18001b017  call    WiaTrace_Trace
0x18001b01c  mov     r9d, r12d; int
0x18001b01f  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18001b024  mov     r8, r13; int
0x18001b027  call    WiaTrace_ProcessTrace_Ex
0x18001b02c  xor     eax, eax
0x18001b02e  cmp     ax, word ptr [rbp+57h+pvar]
0x18001b032  jnz     short loc_18001B05A
0x18001b034  lea     rcx, [rbp+57h+var_80]; this
0x18001b038  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18001b03d  mov     rbx, [rsp+0E0h+arg_0]
0x18001b045  mov     eax, edi
0x18001b047  add     rsp, 0B0h
0x18001b04e  pop     r15
0x18001b050  pop     r14
0x18001b052  pop     r13
0x18001b054  pop     r12
0x18001b056  pop     rdi
0x18001b057  pop     rsi
0x18001b058  pop     rbp
0x18001b059  retn
0x18001b05a  lea     rcx, [rbp+57h+pvar]; pvar
0x18001b05e  call    cs:__imp_PropVariantClear
0x18001b064  jmp     short loc_18001B034
0x18001b066  mov     rax, [r15+0D8h]
0x18001b06d  lea     r9, [rbp+57h+pvar]
0x18001b071  lea     r8, [rbp+57h+var_B0]
0x18001b075  mov     edx, r12d
0x18001b078  mov     rcx, [rax]
0x18001b07b  mov     rax, [rcx]
0x18001b07e  mov     rax, [rax+18h]
0x18001b082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b087  mov     edi, eax
0x18001b089  test    eax, eax
0x18001b08b  js      loc_18001B24F
0x18001b091  mov     rax, [r14+0D8h]
0x18001b098  lea     r9, [rbp+57h+pvar]
0x18001b09c  lea     r8, [rbp+57h+var_B0]
0x18001b0a0  mov     dword ptr [rsp+0E0h+lpMem], esi
0x18001b0a4  mov     edx, r12d
0x18001b0a7  mov     rcx, [rax]
0x18001b0aa  mov     rax, [rcx]
0x18001b0ad  mov     rax, [rax+20h]
0x18001b0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0b6  mov     edi, eax
0x18001b0b8  test    eax, eax
0x18001b0ba  jns     loc_18001AF70
0x18001b0c0  mov     edx, dword ptr [rbp+57h+var_A8]
0x18001b0c3  lea     rcx, aCallToCurstgIp; "Call to CurStg#IPropertyStorage::WriteM"...
0x18001b0ca  mov     r8d, eax
0x18001b0cd  call    WiaTrace_TraceLog
0x18001b0d2  mov     rdx, rax; char *
0x18001b0d5  mov     rcx, r13; char *
0x18001b0d8  mov     rbx, rax
0x18001b0db  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001b0e0  mov     rcx, rbx; this
0x18001b0e3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b0e8  lea     rcx, aCallToCurstgIp; "Call to CurStg#IPropertyStorage::WriteM"...
0x18001b0ef  mov     edx, dword ptr [rbp+57h+var_A8]
0x18001b0f2  mov     r8d, edi
0x18001b0f5  call    WiaTrace_Trace
0x18001b0fa  mov     r9d, r12d; int
0x18001b0fd  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18001b102  mov     r8, r13; int
0x18001b105  call    WiaTrace_ProcessTrace_Ex
0x18001b10a  jmp     loc_18001AF70
0x18001b10f  mov     edi, 80004003h
0x18001b114  lea     rcx, aNullSource0xX; "NULL source (0x%X)"
0x18001b11b  mov     edx, edi
0x18001b11d  call    WiaTrace_TraceLog
0x18001b122  mov     rdx, rax; char *
0x18001b125  mov     rcx, r13; char *
0x18001b128  mov     rbx, rax
0x18001b12b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001b130  mov     rcx, rbx; this
0x18001b133  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b138  mov     edx, edi
0x18001b13a  lea     rcx, aNullSource0xX; "NULL source (0x%X)"
0x18001b141  call    WiaTrace_Trace
0x18001b146  mov     r9d, r12d; int
0x18001b149  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18001b14e  mov     r8, r13; int
0x18001b151  call    WiaTrace_ProcessTrace_Ex
0x18001b156  jmp     loc_18001ADF0
0x18001b15b  mov     edx, [rsi+8]
0x18001b15e  lea     rcx, aCallToIwiaprop_0; "Call to IWiaPropertyStorage::WritePrope"...
0x18001b165  mov     r8d, edi
0x18001b168  call    WiaTrace_TraceLog
0x18001b16d  mov     rdx, rax; char *
0x18001b170  mov     rcx, r13; char *
0x18001b173  mov     rbx, rax
0x18001b176  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001b17b  mov     rcx, rbx; this
0x18001b17e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b183  lea     rcx, aCallToIwiaprop_0; "Call to IWiaPropertyStorage::WritePrope"...
0x18001b18a  jmp     short loc_18001B1EC
0x18001b18c  mov     edx, [rsi+8]
0x18001b18f  lea     rcx, aCallToIwiaprop; "Call to IWiaPropertyStorage::WritePrope"...
0x18001b196  mov     r8d, edi
0x18001b199  call    WiaTrace_TraceLog
0x18001b19e  mov     rdx, rax; char *
0x18001b1a1  mov     rcx, r13; char *
0x18001b1a4  mov     rbx, rax
0x18001b1a7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001b1ac  mov     rcx, rbx; this
0x18001b1af  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b1b4  lea     rcx, aCallToIwiaprop; "Call to IWiaPropertyStorage::WritePrope"...
0x18001b1bb  jmp     short loc_18001B1EC
0x18001b1bd  mov     edx, [rsi+8]
0x18001b1c0  lea     rcx, aCallToIwiaprop_1; "Call to IWiaPropertyStorage::WritePrope"...
0x18001b1c7  mov     r8d, edi
0x18001b1ca  call    WiaTrace_TraceLog
0x18001b1cf  mov     rdx, rax; char *
0x18001b1d2  mov     rcx, r13; char *
0x18001b1d5  mov     rbx, rax
0x18001b1d8  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001b1dd  mov     rcx, rbx; this
0x18001b1e0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b1e5  lea     rcx, aCallToIwiaprop_1; "Call to IWiaPropertyStorage::WritePrope"...
0x18001b1ec  mov     edx, [rsi+8]
0x18001b1ef  mov     r8d, edi
0x18001b1f2  call    WiaTrace_Trace
0x18001b1f7  mov     r9d, r12d; int
0x18001b1fa  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18001b1ff  mov     r8, r13; int
0x18001b202  call    WiaTrace_ProcessTrace_Ex
0x18001b207  jmp     loc_18001AE9E
0x18001b20c  mov     edx, dword ptr [rbp+57h+var_A8]
0x18001b20f  lea     rcx, aCallToAccessst; "Call to AccessStg#IPropertyStorage::Rea"...
0x18001b216  mov     r8d, edi
0x18001b219  call    WiaTrace_TraceLog
0x18001b21e  mov     rdx, rax; char *
0x18001b221  mov     rcx, r13; char *
0x18001b224  mov     rbx, rax
  ... truncated ...
```
