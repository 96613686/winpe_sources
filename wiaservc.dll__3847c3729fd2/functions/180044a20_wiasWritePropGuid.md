# wiasWritePropGuid

- ea: `0x180044a20`
- end: `0x180044d7a`
- name: `wiasWritePropGuid`
- size: `858`
- prototype: `__int64 __fastcall(CWiaItem *this, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180030980`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800189cc`
- `0x180018ad8`
- `0x18001f614`
- `0x180026f30`
- `0x1800284dc`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180033cc0`
- `0x180044a20`
- `0x180078010`

## string_xrefs

- `0x180044a50`: `::wiasWritePropGuid`
- `0x180044a5f`: `wiasWritePropGuid`
- `0x180044c2a`: `wiasWritePropGuid`
- `0x180044c55`: `wiasWritePropGuid`
- `0x180044c78`: `wiasWritePropGuid`
- `0x180044ca5`: `wiasWritePropGuid`
- `0x180044a85`: `wiasWritePropGuid, invalid pItem`
- `0x180044aa7`: `wiasWritePropGuid, invalid pItem`
- `0x180044af8`: `wiasWritePropGuid failed, GetItemPropStreams item failed (0x%X)`
- `0x180044b1c`: `wiasWritePropGuid failed, GetItemPropStreams item failed (0x%X)`
- `0x180044c16`: `wiasWritePropGuid failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x180044c41`: `wiasWritePropGuid failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)`
- `0x180044c69`: `wiasWritePropGuid failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x180044c91`: `wiasWritePropGuid failed, GetItemPropStreams for A-AIT item failed (0x%X)`
- `0x180044d27`: `wiasWritePropGuid (A-AIT)`

## pseudocode

```c
__int64 __fastcall wiasWritePropGuid(struct IWiaItem *this, PROPID a2, GUID *a3)
{
  struct tagWiaTraceData_Type *v6; // rax
  char *v7; // rdx
  unsigned int v8; // r8d
  int ItemPropStreams; // edi
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  char *v17; // rdx
  struct CWiaItem *v18; // rcx
  int RelatedAAITItem; // eax
  int v20; // eax
  struct IPropertyStorage *v21; // r15
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
  unsigned __int64 v32; // rcx
  GUID *v33; // rax
  unsigned int lpMem; // [rsp+28h] [rbp-A9h]
  struct IPropertyStorage *v36; // [rsp+38h] [rbp-99h] BYREF
  struct tagPROPSPEC v37; // [rsp+40h] [rbp-91h] BYREF
  struct CWiaItem *v38; // [rsp+50h] [rbp-81h] BYREF
  struct IPropertyStorage *v39; // [rsp+58h] [rbp-79h] BYREF
  __int64 v40; // [rsp+60h] [rbp-71h] BYREF
  GUID *v41; // [rsp+68h] [rbp-69h]
  __int64 v42; // [rsp+70h] [rbp-61h]
  _BYTE v43[80]; // [rsp+78h] [rbp-59h] BYREF
  GUID v44; // [rsp+C8h] [rbp-9h] BYREF

  v6 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasWritePropGuid");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v43, v7, v8, "wiasWritePropGuid", lpMem, v6);
  ItemPropStreams = ValidateWiaItem(this);
  if ( ItemPropStreams < 0 )
  {
    v10 = (char *)WiaTrace_TraceLog("wiasWritePropGuid, invalid pItem");
    WriteDbgTraceErrorWI("wiasWritePropGuid", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void **)WiaTrace_Trace("wiasWritePropGuid, invalid pItem");
LABEL_3:
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"wiasWritePropGuid", 1, v12);
    goto LABEL_27;
  }
  v36 = 0;
  ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, &v36, 0, 0, 0);
  if ( ItemPropStreams < 0 )
  {
    v15 = (char *)WiaTrace_TraceLog("wiasWritePropGuid failed, GetItemPropStreams item failed (0x%X)");
    WriteDbgTraceErrorWI("wiasWritePropGuid", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v12 = (void **)WiaTrace_Trace("wiasWritePropGuid failed, GetItemPropStreams item failed (0x%X)", ItemPropStreams);
    goto LABEL_3;
  }
  v42 = 0;
  v37 = 0;
  v37.ulKind = 1;
  v40 = 72;
  v37.propid = a2;
  v41 = a3;
  ItemPropStreams = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, __int64 *, int))v36->lpVtbl->WriteMultiple)(
                      v36,
                      1,
                      &v37,
                      &v40,
                      2);
  if ( ItemPropStreams < 0 )
  {
    v17 = "wiasWritePropGuid";
LABEL_26:
    ReportReadWriteMultipleError(ItemPropStreams, v17, 0, 0, 1u, &v37);
    goto LABEL_27;
  }
  if ( !(unsigned int)CWiaItem::IsCompatMode((CWiaItem *)this) )
    goto LABEL_27;
  v44 = WiaImgFmt_BMP;
  v38 = 0;
  v39 = 0;
  LODWORD(v36) = 0;
  RelatedAAITItem = _FindRelatedAAITItem(v18, a2, &v38, (unsigned int *)&v36);
  ItemPropStreams = RelatedAAITItem;
  if ( RelatedAAITItem == 1 )
  {
    ItemPropStreams = 0;
    goto LABEL_27;
  }
  if ( RelatedAAITItem )
    goto LABEL_27;
  v20 = CWiaItem::GetItemPropStreams(v38, &v39, 0, 0, 0);
  v21 = v39;
  ItemPropStreams = v20;
  if ( v39 )
  {
    if ( v20 >= 0 )
      goto LABEL_17;
  }
  else if ( v20 >= 0 )
  {
    ItemPropStreams = -2147467261;
    v22 = (char *)WiaTrace_TraceLog("wiasWritePropGuid failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
    WriteDbgTraceErrorWI("wiasWritePropGuid", v22);
    WiaTrcLib::Free((WiaTrcLib *)v22, v23);
    v24 = (void **)WiaTrace_Trace("wiasWritePropGuid failed, GetItemPropStreams for A-AIT item returned NULL pointer (E_POINTER)");
    WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"wiasWritePropGuid", 1, v24);
  }
  v27 = (char *)WiaTrace_TraceLog("wiasWritePropGuid failed, GetItemPropStreams for A-AIT item failed (0x%X)");
  WriteDbgTraceErrorWI("wiasWritePropGuid", v27);
  WiaTrcLib::Free((WiaTrcLib *)v27, v28);
  v29 = (void **)WiaTrace_Trace(
                   "wiasWritePropGuid failed, GetItemPropStreams for A-AIT item failed (0x%X)",
                   ItemPropStreams);
  WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"wiasWritePropGuid", 1, v29);
  if ( ItemPropStreams < 0 )
    goto LABEL_27;
LABEL_17:
  if ( a2 == 4106 && (unsigned int)CWiaItem::IsLegacyDriver((CWiaItem *)this) )
  {
    v32 = *(_QWORD *)&v41->Data1 - *(_QWORD *)&WiaImgFmt_MEMORYBMP.Data1;
    if ( *(_QWORD *)&v41->Data1 == *(_QWORD *)&WiaImgFmt_MEMORYBMP.Data1 )
      v32 = *(_QWORD *)v41->Data4 - _mm_srli_si128((__m128i)WiaImgFmt_MEMORYBMP, 8).m128i_u64[0];
    v33 = &v44;
    if ( v32 )
      v33 = v41;
    v41 = v33;
  }
  ItemPropStreams = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, __int64 *, int))v21->lpVtbl->WriteMultiple)(
                      v21,
                      1,
                      &v37,
                      &v40,
                      2);
  if ( ItemPropStreams < 0 )
  {
    v17 = "wiasWritePropGuid (A-AIT)";
    goto LABEL_26;
  }
LABEL_27:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v43);
  return (unsigned int)ItemPropStreams;
}

```

## disassembly

```asm
0x180044a20  mov     rax, rsp
0x180044a23  push    rbp
0x180044a24  push    rbx
0x180044a25  push    rsi
0x180044a26  push    rdi
0x180044a27  push    r12
0x180044a29  push    r14
0x180044a2b  push    r15
0x180044a2d  lea     rbp, [rax-5Fh]
0x180044a31  sub     rsp, 0F0h
0x180044a38  movaps  xmmword ptr [rax-48h], xmm6
0x180044a3c  mov     rax, cs:__security_cookie
0x180044a43  xor     rax, rsp
0x180044a46  mov     [rbp+57h+var_50], rax
0x180044a4a  mov     r14, rcx
0x180044a4d  mov     rbx, r8
0x180044a50  lea     rcx, aWiaswritepropg_1; "::wiasWritePropGuid"
0x180044a57  mov     r12d, edx
0x180044a5a  call    WiaTrace_Trace
0x180044a5f  lea     r15, aWiaswritepropg_7; "wiasWritePropGuid"
0x180044a66  mov     [rsp+120h+var_F8], rax; struct tagWiaTraceData_Type *
0x180044a6b  mov     r9, r15; char *
0x180044a6e  lea     rcx, [rbp+57h+var_B0]; this
0x180044a72  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180044a77  mov     rcx, r14; struct IWiaItem *
0x180044a7a  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180044a7f  mov     edi, eax
0x180044a81  test    eax, eax
0x180044a83  jns     short loc_180044ACB
0x180044a85  lea     rcx, aWiaswritepropg_5; "wiasWritePropGuid, invalid pItem"
0x180044a8c  call    WiaTrace_TraceLog
0x180044a91  mov     rdx, rax; char *
0x180044a94  mov     rcx, r15; char *
0x180044a97  mov     rbx, rax
0x180044a9a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044a9f  mov     rcx, rbx; this
0x180044aa2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044aa7  lea     rcx, aWiaswritepropg_5; "wiasWritePropGuid, invalid pItem"
0x180044aae  call    WiaTrace_Trace
0x180044ab3  mov     r9d, 1; int
0x180044ab9  mov     [rsp+120h+lpMem], rax; lpMem
0x180044abe  mov     r8, r15; int
0x180044ac1  call    WiaTrace_ProcessTrace_Ex
0x180044ac6  jmp     loc_180044D49
0x180044acb  xor     r9d, r9d; struct IPropertyStorage **
0x180044ace  mov     qword ptr [rsp+120h+var_F0.ulKind], 0
0x180044ad7  xor     r8d, r8d; struct IPropertyStorage **
0x180044ada  mov     [rsp+120h+lpMem], 0; struct IPropertyStorage **
0x180044ae3  lea     rdx, [rsp+120h+var_F0]; struct IPropertyStorage **
0x180044ae8  mov     rcx, r14; this
0x180044aeb  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x180044af0  mov     edi, eax
0x180044af2  test    eax, eax
0x180044af4  jns     short loc_180044B2A
0x180044af6  mov     edx, eax
0x180044af8  lea     rcx, aWiaswritepropg_0; "wiasWritePropGuid failed, GetItemPropSt"...
0x180044aff  call    WiaTrace_TraceLog
0x180044b04  mov     rdx, rax; char *
0x180044b07  mov     rcx, r15; char *
0x180044b0a  mov     rbx, rax
0x180044b0d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044b12  mov     rcx, rbx; this
0x180044b15  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044b1a  mov     edx, edi
0x180044b1c  lea     rcx, aWiaswritepropg_0; "wiasWritePropGuid failed, GetItemPropSt"...
0x180044b23  call    WiaTrace_Trace
0x180044b28  jmp     short loc_180044AB3
0x180044b2a  mov     rcx, qword ptr [rsp+120h+var_F0.ulKind]
0x180044b2f  lea     r9, [rbp+57h+var_C8]
0x180044b33  xor     eax, eax
0x180044b35  mov     dword ptr [rsp+120h+lpMem], 2
0x180044b3d  mov     [rbp+57h+var_B8], rax
0x180044b41  lea     r8, [rsp+120h+var_F0.8]
0x180044b46  mov     esi, 1
0x180044b4b  xorps   xmm0, xmm0
0x180044b4e  movups  xmmword ptr [rsp+120h+var_F0.8], xmm0
0x180044b53  mov     dword ptr [rsp+120h+var_F0.8], esi
0x180044b57  mov     edx, esi
0x180044b59  movups  [rbp+57h+var_C8], xmm0
0x180044b5d  lea     eax, [rsi+47h]
0x180044b60  mov     dword ptr [rsp+120h+var_E0], r12d
0x180044b65  mov     word ptr [rbp+57h+var_C8], ax
0x180044b69  mov     qword ptr [rbp+57h+var_C8+8], rbx
0x180044b6d  mov     rax, [rcx]
0x180044b70  mov     rax, [rax+20h]
0x180044b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b79  mov     edi, eax
0x180044b7b  test    eax, eax
0x180044b7d  jns     short loc_180044B87
0x180044b7f  mov     rdx, r15
0x180044b82  jmp     loc_180044D2E
0x180044b87  mov     rcx, r14; this
0x180044b8a  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x180044b8f  test    eax, eax
0x180044b91  jz      loc_180044D49
0x180044b97  movups  xmm0, xmmword ptr cs:WiaImgFmt_BMP.Data1
0x180044b9e  lea     r9, [rsp+120h+var_F0]; unsigned int *
0x180044ba3  mov     edx, r12d; unsigned int
0x180044ba6  movaps  xmm6, xmmword ptr cs:WiaImgFmt_MEMORYBMP.Data1
0x180044bad  lea     r8, [rsp+120h+var_D8]; struct CWiaItem **
0x180044bb2  movdqu  [rbp+57h+var_60], xmm0
0x180044bb7  mov     [rsp+120h+var_D8], 0
0x180044bc0  mov     [rbp+57h+var_D0], 0
0x180044bc8  mov     [rsp+120h+var_F0.ulKind], 0
0x180044bd0  call    ?_FindRelatedAAITItem@@YAJPEAVCWiaItem@@KPEAPEAV1@PEAK@Z; _FindRelatedAAITItem(CWiaItem *,ulong,CWiaItem * *,ulong *)
0x180044bd5  mov     edi, eax
0x180044bd7  cmp     eax, esi
0x180044bd9  jnz     short loc_180044BE2
0x180044bdb  xor     edi, edi
0x180044bdd  jmp     loc_180044D49
0x180044be2  test    eax, eax
0x180044be4  jnz     loc_180044D49
0x180044bea  mov     rcx, [rsp+120h+var_D8]; this
0x180044bef  lea     rdx, [rbp+57h+var_D0]; struct IPropertyStorage **
0x180044bf3  xor     r9d, r9d; struct IPropertyStorage **
0x180044bf6  mov     [rsp+120h+lpMem], 0; struct IPropertyStorage **
0x180044bff  xor     r8d, r8d; struct IPropertyStorage **
0x180044c02  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x180044c07  mov     r15, [rbp+57h+var_D0]
0x180044c0b  mov     edi, eax
0x180044c0d  test    r15, r15
0x180044c10  jnz     short loc_180044C63
0x180044c12  test    eax, eax
0x180044c14  js      short loc_180044C67
0x180044c16  lea     rcx, aWiaswritepropg_6; "wiasWritePropGuid failed, GetItemPropSt"...
0x180044c1d  mov     edi, 80004003h
0x180044c22  call    WiaTrace_TraceLog
0x180044c27  mov     rdx, rax; char *
0x180044c2a  lea     rcx, aWiaswritepropg_7; "wiasWritePropGuid"
0x180044c31  mov     rbx, rax
0x180044c34  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044c39  mov     rcx, rbx; this
0x180044c3c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044c41  lea     rcx, aWiaswritepropg_6; "wiasWritePropGuid failed, GetItemPropSt"...
0x180044c48  call    WiaTrace_Trace
0x180044c4d  mov     r9d, esi; int
0x180044c50  mov     [rsp+120h+lpMem], rax; lpMem
0x180044c55  lea     r8, aWiaswritepropg_7; "wiasWritePropGuid"
0x180044c5c  call    WiaTrace_ProcessTrace_Ex
0x180044c61  jmp     short loc_180044C67
0x180044c63  test    eax, eax
0x180044c65  jns     short loc_180044CB9
0x180044c67  mov     edx, edi
0x180044c69  lea     rcx, aWiaswritepropg_2; "wiasWritePropGuid failed, GetItemPropSt"...
0x180044c70  call    WiaTrace_TraceLog
0x180044c75  mov     rdx, rax; char *
0x180044c78  lea     rcx, aWiaswritepropg_7; "wiasWritePropGuid"
0x180044c7f  mov     rbx, rax
0x180044c82  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180044c87  mov     rcx, rbx; this
0x180044c8a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180044c8f  mov     edx, edi
0x180044c91  lea     rcx, aWiaswritepropg_2; "wiasWritePropGuid failed, GetItemPropSt"...
0x180044c98  call    WiaTrace_Trace
0x180044c9d  mov     r9d, esi; int
0x180044ca0  mov     [rsp+120h+lpMem], rax; lpMem
0x180044ca5  lea     r8, aWiaswritepropg_7; "wiasWritePropGuid"
0x180044cac  call    WiaTrace_ProcessTrace_Ex
0x180044cb1  test    edi, edi
0x180044cb3  js      loc_180044D49
0x180044cb9  cmp     r12d, 100Ah
0x180044cc0  jnz     short loc_180044CFF
0x180044cc2  mov     rcx, r14; this
0x180044cc5  call    ?IsLegacyDriver@CWiaItem@@QEAAHXZ; CWiaItem::IsLegacyDriver(void)
0x180044cca  test    eax, eax
0x180044ccc  jz      short loc_180044CFF
0x180044cce  mov     rdx, qword ptr [rbp+57h+var_C8+8]
0x180044cd2  movq    rax, xmm6
0x180044cd7  mov     rcx, [rdx]
0x180044cda  sub     rcx, rax
0x180044cdd  jnz     short loc_180044CF0
0x180044cdf  mov     rcx, [rdx+8]
0x180044ce3  psrldq  xmm6, 8
0x180044ce8  movq    rax, xmm6
0x180044ced  sub     rcx, rax
0x180044cf0  test    rcx, rcx
0x180044cf3  lea     rax, [rbp+57h+var_60]
0x180044cf7  cmovnz  rax, rdx
0x180044cfb  mov     qword ptr [rbp+57h+var_C8+8], rax
0x180044cff  mov     rax, [r15]
0x180044d02  lea     r9, [rbp+57h+var_C8]
0x180044d06  lea     r8, [rsp+120h+var_F0.8]
0x180044d0b  mov     dword ptr [rsp+120h+lpMem], 2
0x180044d13  mov     edx, esi
0x180044d15  mov     rcx, r15
0x180044d18  mov     rax, [rax+20h]
0x180044d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d21  mov     edi, eax
0x180044d23  test    eax, eax
0x180044d25  jns     short loc_180044D49
0x180044d27  lea     rdx, aWiaswritepropg_3; "wiasWritePropGuid (A-AIT)"
0x180044d2e  lea     rax, [rsp+120h+var_F0.8]
0x180044d33  xor     r9d, r9d; int
0x180044d36  mov     [rsp+120h+var_F8], rax; struct tagPROPSPEC *
0x180044d3b  xor     r8d, r8d; char *
0x180044d3e  mov     ecx, edi; int
0x180044d40  mov     dword ptr [rsp+120h+lpMem], esi; unsigned int
0x180044d44  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x180044d49  lea     rcx, [rbp+57h+var_B0]; this
0x180044d4d  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180044d52  mov     eax, edi
0x180044d54  mov     rcx, [rbp+57h+var_50]
0x180044d58  xor     rcx, rsp; StackCookie
0x180044d5b  call    __security_check_cookie
0x180044d60  movaps  xmm6, [rsp+120h+var_48+8]
0x180044d68  add     rsp, 0F0h
0x180044d6f  pop     r15
0x180044d71  pop     r14
0x180044d73  pop     r12
0x180044d75  pop     rdi
0x180044d76  pop     rsi
0x180044d77  pop     rbx
0x180044d78  pop     rbp
0x180044d79  retn
```
