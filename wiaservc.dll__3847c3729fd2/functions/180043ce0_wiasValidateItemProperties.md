# wiasValidateItemProperties

- ea: `0x180043ce0`
- end: `0x18004406b`
- name: `wiasValidateItemProperties`
- size: `907`
- prototype: `__int64 __fastcall(struct IWiaItem *this)`
- caller_count: `4`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180040410`
- `0x1800405b0`
- `0x180040750`
- `0x1800408f0`

## callees

- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800189cc`
- `0x180018ad8`
- `0x18001c1e4`
- `0x18001f614`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x18003de9c`
- `0x18003eea4`
- `0x180041240`
- `0x180043ce0`
- `0x180078010`

## import_xrefs

- `ole32!PropVariantClear` at `0x180043ed3`
- `ole32!PropVariantClear` at `0x180044028`
- `ole32!PropVariantClear` at `0x180044032`
- `ole32!PropVariantClear` at `0x180043ed3`
- `ole32!PropVariantClear` at `0x180044028`
- `ole32!PropVariantClear` at `0x180044032`

## string_xrefs

- `0x180043d01`: `::wiasValidateItemProperties`
- `0x180043d10`: `wiasValidateItemProperties`
- `0x180043f05`: `wiasValidateItemProperties`
- `0x180043f96`: `wiasValidateItemProperties`
- `0x180043fed`: `wiasValidateItemProperties`
- `0x180043d4e`: `wiasValidateItemProperties, invalid pItem`
- `0x180043d70`: `wiasValidateItemProperties, invalid pItem`
- `0x180043d9e`: `wiasValidateItemProperties, bad pPropSpec parameter`
- `0x180043dc0`: `wiasValidateItemProperties, bad pPropSpec parameter`
- `0x180043e12`: `wiasValidateItemProperties, GetItemPropStreams failed`
- `0x180043e36`: `wiasValidateItemProperties, GetItemPropStreams failed`

## pseudocode

```c
__int64 __fastcall wiasValidateItemProperties(struct IWiaItem *this, unsigned int a2, __int64 a3)
{
  __int64 v4; // rsi
  struct tagWiaTraceData_Type *v6; // rax
  char *v7; // rdx
  unsigned int v8; // r8d
  int v9; // edi
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  int ItemPropStreams; // ebx
  char *v21; // rbx
  void *v22; // rdx
  void **v23; // rax
  void *v24; // rdx
  __int64 v25; // rcx
  unsigned int i; // r15d
  struct tagPROPSPEC *v27; // rdi
  int PropertyAttributes; // eax
  int v29; // esi
  int v30; // eax
  unsigned int v31; // esi
  LONG lVal; // r10d
  int v33; // r9d
  const wchar_t *NameFromWiaPropId; // rax
  char *v35; // rbx
  void *v36; // rdx
  int v37; // r9d
  const wchar_t *lpwstr; // rax
  void **v39; // rax
  void *v40; // rdx
  __int64 v41; // rcx
  int v42; // eax
  unsigned int lpMem; // [rsp+20h] [rbp-79h]
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-69h] BYREF
  struct tagPROPVARIANT v46; // [rsp+48h] [rbp-51h] BYREF
  struct IPropertyStorage *v47; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v48[128]; // [rsp+70h] [rbp-29h] BYREF
  struct IPropertyStorage *v49; // [rsp+100h] [rbp+67h] BYREF
  __int64 v50; // [rsp+110h] [rbp+77h]
  struct IPropertyStorage *v51; // [rsp+118h] [rbp+7Fh] BYREF

  v50 = a3;
  v4 = a3;
  v6 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasValidateItemProperties");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v48, v7, v8, "wiasValidateItemProperties", lpMem, v6);
  memset(&v46, 0, sizeof(v46));
  memset(&pvar, 0, sizeof(pvar));
  v9 = ValidateWiaItem(this);
  if ( v9 >= 0 )
  {
    if ( a2 && !v4 )
    {
      v15 = (char *)WiaTrace_TraceLog("wiasValidateItemProperties, bad pPropSpec parameter");
      WriteDbgTraceErrorWI("wiasValidateItemProperties", v15);
      WiaTrcLib::Free((WiaTrcLib *)v15, v16);
      v17 = (void **)WiaTrace_Trace("wiasValidateItemProperties, bad pPropSpec parameter");
      WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"wiasValidateItemProperties", 1, v17);
      v9 = -2147467261;
      goto LABEL_36;
    }
    v51 = 0;
    ItemPropStreams = CWiaItem::GetItemPropStreams((CWiaItem *)this, &v51, &v47, &v49, 0);
    if ( ItemPropStreams < 0 )
    {
      v21 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, GetItemPropStreams failed");
      WriteDbgTraceWarningWI("wiasValidateItemProperties", v21);
      WiaTrcLib::Free((WiaTrcLib *)v21, v22);
      v23 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, GetItemPropStreams failed");
      WiaTrace_ProcessTrace_Ex(v25, v24, (void *)"wiasValidateItemProperties", 2, v23);
      v9 = -2147467259;
      goto LABEL_36;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= a2 )
      {
LABEL_35:
        v9 = ItemPropStreams;
        goto LABEL_36;
      }
      LODWORD(v49) = 0;
      v27 = (struct tagPROPSPEC *)(v4 + 16LL * i);
      memset(&pvar, 0, sizeof(pvar));
      PropertyAttributes = wiasGetPropertyAttributes(this, 1, v27, (unsigned int *)&v49, &pvar);
      ItemPropStreams = PropertyAttributes;
      if ( PropertyAttributes )
      {
        v9 = PropertyAttributes;
        goto LABEL_36;
      }
      v29 = (int)v49;
      if ( ((unsigned __int8)v49 & 3) == 0
        && (((((unsigned int)v49 & 0xFFFFFFFC) - 16) & 0xFFFFFFCF) != 0 || ((unsigned int)v49 & 0xFFFFFFFC) == 0x30) )
      {
        PropVariantClear((PROPVARIANT *)&pvar);
        goto LABEL_33;
      }
      v30 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, struct tagPROPSPEC *, struct tagPROPVARIANT *))v51->lpVtbl->ReadMultiple)(
              v51,
              1,
              v27,
              &v46);
      ItemPropStreams = v30;
      if ( v30 )
      {
        ReportReadWriteMultipleError(v30, "wiasValidateItemProperties", 0, 1, 1u, v27);
        goto LABEL_32;
      }
      v31 = v29 & 0xFFFEFFFC;
      if ( v31 == 16 )
        break;
      if ( v31 == 32 )
      {
        v42 = ValidateListProp(&v46, &pvar, v27);
LABEL_31:
        ItemPropStreams = v42;
        goto LABEL_32;
      }
      if ( v31 == 64 )
      {
        lVal = v46.lVal;
        v33 = *((_DWORD *)pvar.bstrblobVal.pData + 1);
        if ( (~v33 & v46.lVal) != 0 )
        {
          if ( v27->ulKind )
            NameFromWiaPropId = GetNameFromWiaPropId(v27->propid);
          else
            NameFromWiaPropId = v27->lpwstr;
          v35 = (char *)WiaTrace_TraceLogWithSubComp(
                          0,
                          "Invalid flag value for property %S: 0x%08X, valid mask: 0x%08X",
                          NameFromWiaPropId,
                          lVal,
                          v33);
          WriteDbgTraceWarningWI("wiasValidateItemProperties", v35);
          WiaTrcLib::Free((WiaTrcLib *)v35, v36);
          v37 = *((_DWORD *)pvar.bstrblobVal.pData + 1);
          if ( v27->ulKind )
            lpwstr = GetNameFromWiaPropId(v27->propid);
          else
            lpwstr = v27->lpwstr;
          v39 = (void **)WiaTrace_TraceWithSubComp(
                           0,
                           "Invalid flag value for property %S: 0x%08X, valid mask: 0x%08X",
                           lpwstr,
                           v46.lVal,
                           v37);
          WiaTrace_ProcessTrace_Ex(v41, v40, (void *)"wiasValidateItemProperties", 2, v39);
          ItemPropStreams = -2147024809;
        }
      }
      else
      {
        ItemPropStreams = 0;
      }
LABEL_32:
      PropVariantClear((PROPVARIANT *)&pvar);
      PropVariantClear((PROPVARIANT *)&v46);
      if ( ItemPropStreams )
        goto LABEL_35;
LABEL_33:
      v4 = v50;
    }
    v42 = ValidateRangeProp(&v46, &pvar, v27);
    goto LABEL_31;
  }
  v10 = (char *)WiaTrace_TraceLog("wiasValidateItemProperties, invalid pItem");
  WriteDbgTraceErrorWI("wiasValidateItemProperties", v10);
  WiaTrcLib::Free((WiaTrcLib *)v10, v11);
  v12 = (void **)WiaTrace_Trace("wiasValidateItemProperties, invalid pItem");
  WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"wiasValidateItemProperties", 1, v12);
LABEL_36:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v48);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180043ce0  mov     [rsp-8+arg_10], r8
0x180043ce5  push    rbp
0x180043ce6  push    rbx
0x180043ce7  push    rsi
0x180043ce8  push    rdi
0x180043ce9  push    r12
0x180043ceb  push    r13
0x180043ced  push    r15
0x180043cef  lea     rbp, [rsp-27h]
0x180043cf4  sub     rsp, 0C0h
0x180043cfb  mov     r13, rcx
0x180043cfe  mov     rsi, r8
0x180043d01  lea     rcx, aWiasvalidateit_3; "::wiasValidateItemProperties"
0x180043d08  mov     r12d, edx
0x180043d0b  call    WiaTrace_Trace
0x180043d10  lea     r15, aWiasvalidateit_5; "wiasValidateItemProperties"
0x180043d17  mov     [rsp+0F0h+var_C8], rax; struct tagWiaTraceData_Type *
0x180043d1c  mov     r9, r15; char *
0x180043d1f  lea     rcx, [rbp+57h+var_80]; this
0x180043d23  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180043d28  xor     eax, eax
0x180043d2a  xorps   xmm0, xmm0
0x180043d2d  xorps   xmm1, xmm1
0x180043d30  mov     [rbp+57h+var_98], rax
0x180043d34  mov     rcx, r13; struct IWiaItem *
0x180043d37  mov     [rbp+57h+var_B0], rax
0x180043d3b  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180043d3f  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x180043d43  call    ?ValidateWiaItem@@YAJPEAUIWiaItem@@@Z; ValidateWiaItem(IWiaItem *)
0x180043d48  mov     edi, eax
0x180043d4a  test    eax, eax
0x180043d4c  jns     short loc_180043D94
0x180043d4e  lea     rcx, aWiasvalidateit_7; "wiasValidateItemProperties, invalid pIt"...
0x180043d55  call    WiaTrace_TraceLog
0x180043d5a  mov     rdx, rax; char *
0x180043d5d  mov     rcx, r15; char *
0x180043d60  mov     rbx, rax
0x180043d63  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180043d68  mov     rcx, rbx; this
0x180043d6b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180043d70  lea     rcx, aWiasvalidateit_7; "wiasValidateItemProperties, invalid pIt"...
0x180043d77  call    WiaTrace_Trace
0x180043d7c  mov     r9d, 1; int
0x180043d82  mov     [rsp+0F0h+lpMem], rax; lpMem
0x180043d87  mov     r8, r15; int
0x180043d8a  call    WiaTrace_ProcessTrace_Ex
0x180043d8f  jmp     loc_18004404E
0x180043d94  test    r12d, r12d
0x180043d97  jz      short loc_180043DE7
0x180043d99  test    rsi, rsi
0x180043d9c  jnz     short loc_180043DE7
0x180043d9e  lea     rcx, aWiasvalidateit_1; "wiasValidateItemProperties, bad pPropSp"...
0x180043da5  call    WiaTrace_TraceLog
0x180043daa  mov     rdx, rax; char *
0x180043dad  mov     rcx, r15; char *
0x180043db0  mov     rbx, rax
0x180043db3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180043db8  mov     rcx, rbx; this
0x180043dbb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180043dc0  lea     rcx, aWiasvalidateit_1; "wiasValidateItemProperties, bad pPropSp"...
0x180043dc7  call    WiaTrace_Trace
0x180043dcc  lea     r9d, [rsi+1]; int
0x180043dd0  mov     [rsp+0F0h+lpMem], rax; lpMem
0x180043dd5  mov     r8, r15; int
0x180043dd8  call    WiaTrace_ProcessTrace_Ex
0x180043ddd  mov     edi, 80004003h
0x180043de2  jmp     loc_18004404E
0x180043de7  lea     r9, [rbp+57h+arg_0]; struct IPropertyStorage **
0x180043deb  mov     [rbp+57h+arg_18], 0
0x180043df3  lea     r8, [rbp+57h+var_90]; struct IPropertyStorage **
0x180043df7  mov     [rsp+0F0h+lpMem], 0; struct IPropertyStorage **
0x180043e00  lea     rdx, [rbp+57h+arg_18]; struct IPropertyStorage **
0x180043e04  mov     rcx, r13; this
0x180043e07  call    ?GetItemPropStreams@CWiaItem@@QEAAJPEAPEAUIPropertyStorage@@000@Z; CWiaItem::GetItemPropStreams(IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *,IPropertyStorage * *)
0x180043e0c  mov     ebx, eax
0x180043e0e  test    eax, eax
0x180043e10  jns     short loc_180043E61
0x180043e12  lea     rdx, aWiasvalidateit_2; "wiasValidateItemProperties, GetItemProp"...
0x180043e19  xor     ecx, ecx
0x180043e1b  call    WiaTrace_TraceLogWithSubComp
0x180043e20  mov     rdx, rax; char *
0x180043e23  mov     rcx, r15; char *
0x180043e26  mov     rbx, rax
0x180043e29  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180043e2e  mov     rcx, rbx; this
0x180043e31  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180043e36  lea     rdx, aWiasvalidateit_2; "wiasValidateItemProperties, GetItemProp"...
0x180043e3d  xor     ecx, ecx
0x180043e3f  call    WiaTrace_TraceWithSubComp
0x180043e44  mov     r9d, 2; int
0x180043e4a  mov     [rsp+0F0h+lpMem], rax; lpMem
0x180043e4f  mov     r8, r15; int
0x180043e52  call    WiaTrace_ProcessTrace_Ex
0x180043e57  mov     edi, 80004005h
0x180043e5c  jmp     loc_18004404E
0x180043e61  xor     r15d, r15d
0x180043e64  cmp     r15d, r12d
0x180043e67  jnb     loc_18004404C
0x180043e6d  xor     eax, eax
0x180043e6f  mov     edi, r15d
0x180043e72  mov     [rbp+57h+var_B0], rax
0x180043e76  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180043e7a  xorps   xmm0, xmm0
0x180043e7d  shl     rdi, 4
0x180043e81  lea     rax, [rbp+57h+pvar]
0x180043e85  mov     dword ptr [rbp+57h+arg_0], 0
0x180043e8c  add     rdi, rsi
0x180043e8f  mov     [rsp+0F0h+lpMem], rax; struct tagPROPVARIANT *
0x180043e94  mov     r8, rdi; struct tagPROPSPEC *
0x180043e97  mov     edx, 1; int
0x180043e9c  mov     rcx, r13; this
0x180043e9f  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180043ea3  call    wiasGetPropertyAttributes
0x180043ea8  mov     ebx, eax
0x180043eaa  test    eax, eax
0x180043eac  jnz     loc_180044048
0x180043eb2  mov     esi, dword ptr [rbp+57h+arg_0]
0x180043eb5  test    sil, 3
0x180043eb9  jnz     short loc_180043EDE
0x180043ebb  mov     ecx, esi
0x180043ebd  and     ecx, 0FFFFFFFCh
0x180043ec0  lea     eax, [rcx-10h]
0x180043ec3  test    eax, 0FFFFFFCFh
0x180043ec8  jnz     short loc_180043ECF
0x180043eca  cmp     ecx, 30h ; '0'
0x180043ecd  jnz     short loc_180043EDE
0x180043ecf  lea     rcx, [rbp+57h+pvar]; pvar
0x180043ed3  call    cs:__imp_PropVariantClear
0x180043ed9  jmp     loc_18004403C
0x180043ede  mov     rcx, [rbp+57h+arg_18]
0x180043ee2  lea     r9, [rbp+57h+var_A8]
0x180043ee6  mov     r8, rdi
0x180043ee9  mov     edx, 1
0x180043eee  mov     rax, [rcx]
0x180043ef1  mov     rax, [rax+18h]
0x180043ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043efa  mov     ebx, eax
0x180043efc  test    eax, eax
0x180043efe  jz      short loc_180043F29
0x180043f00  mov     [rsp+0F0h+var_C8], rdi; struct tagPROPSPEC *
0x180043f05  lea     rdx, aWiasvalidateit_5; "wiasValidateItemProperties"
0x180043f0c  mov     r9d, 1; int
0x180043f12  mov     dword ptr [rsp+0F0h+lpMem], 1; unsigned int
0x180043f1a  xor     r8d, r8d; char *
0x180043f1d  mov     ecx, eax; int
0x180043f1f  call    ?ReportReadWriteMultipleError@@YAXJPEAD0HKQEBUtagPROPSPEC@@@Z; ReportReadWriteMultipleError(long,char *,char *,int,ulong,tagPROPSPEC const * const)
0x180043f24  jmp     loc_180044024
0x180043f29  and     esi, 0FFFEFFFCh
0x180043f2f  cmp     esi, 10h
0x180043f32  jz      loc_180044012
0x180043f38  cmp     esi, 20h ; ' '
0x180043f3b  jz      loc_180044000
0x180043f41  cmp     esi, 40h ; '@'
0x180043f44  jz      short loc_180043F4D
0x180043f46  xor     ebx, ebx
0x180043f48  jmp     loc_180044024
0x180043f4d  mov     rax, [rbp+57h+var_B0]
0x180043f51  mov     r10d, dword ptr [rbp+57h+var_A8+8]
0x180043f55  mov     r9d, [rax+4]
0x180043f59  mov     eax, r9d
0x180043f5c  not     eax
0x180043f5e  test    r10d, eax
0x180043f61  jz      loc_180044024
0x180043f67  cmp     dword ptr [rdi], 0
0x180043f6a  jnz     short loc_180043F72
0x180043f6c  mov     rax, [rdi+8]
0x180043f70  jmp     short loc_180043F7A
0x180043f72  mov     ecx, [rdi+8]; unsigned int
0x180043f75  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x180043f7a  mov     dword ptr [rsp+0F0h+lpMem], r9d
0x180043f7f  lea     rdx, aInvalidFlagVal; "Invalid flag value for property %S: 0x%"...
0x180043f86  mov     r9d, r10d
0x180043f89  mov     r8, rax
0x180043f8c  xor     ecx, ecx
0x180043f8e  call    WiaTrace_TraceLogWithSubComp
0x180043f93  mov     rdx, rax; char *
0x180043f96  lea     rcx, aWiasvalidateit_5; "wiasValidateItemProperties"
0x180043f9d  mov     rbx, rax
0x180043fa0  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180043fa5  mov     rcx, rbx; this
0x180043fa8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180043fad  cmp     dword ptr [rdi], 0
0x180043fb0  mov     rax, [rbp+57h+var_B0]
0x180043fb4  mov     r9d, [rax+4]
0x180043fb8  jnz     short loc_180043FC0
0x180043fba  mov     rax, [rdi+8]
0x180043fbe  jmp     short loc_180043FC8
0x180043fc0  mov     ecx, [rdi+8]; unsigned int
0x180043fc3  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x180043fc8  mov     dword ptr [rsp+0F0h+lpMem], r9d
0x180043fcd  lea     rdx, aInvalidFlagVal; "Invalid flag value for property %S: 0x%"...
0x180043fd4  mov     r9d, dword ptr [rbp+57h+var_A8+8]
0x180043fd8  mov     r8, rax
0x180043fdb  xor     ecx, ecx
0x180043fdd  call    WiaTrace_TraceWithSubComp
0x180043fe2  mov     r9d, 2; int
0x180043fe8  mov     [rsp+0F0h+lpMem], rax; lpMem
0x180043fed  lea     r8, aWiasvalidateit_5; "wiasValidateItemProperties"
0x180043ff4  call    WiaTrace_ProcessTrace_Ex
0x180043ff9  mov     ebx, 80070057h
0x180043ffe  jmp     short loc_180044024
0x180044000  mov     r8, rdi; struct tagPROPSPEC *
0x180044003  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180044007  lea     rcx, [rbp+57h+var_A8]; struct tagPROPVARIANT *
0x18004400b  call    ?ValidateListProp@@YAJPEAUtagPROPVARIANT@@0PEAUtagPROPSPEC@@@Z; ValidateListProp(tagPROPVARIANT *,tagPROPVARIANT *,tagPROPSPEC *)
0x180044010  jmp     short loc_180044022
0x180044012  mov     r8, rdi; struct tagPROPSPEC *
0x180044015  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180044019  lea     rcx, [rbp+57h+var_A8]; struct tagPROPVARIANT *
0x18004401d  call    ?ValidateRangeProp@@YAJPEAUtagPROPVARIANT@@0PEAUtagPROPSPEC@@@Z; ValidateRangeProp(tagPROPVARIANT *,tagPROPVARIANT *,tagPROPSPEC *)
0x180044022  mov     ebx, eax
0x180044024  lea     rcx, [rbp+57h+pvar]; pvar
0x180044028  call    cs:__imp_PropVariantClear
0x18004402e  lea     rcx, [rbp+57h+var_A8]; pvar
0x180044032  call    cs:__imp_PropVariantClear
0x180044038  test    ebx, ebx
0x18004403a  jnz     short loc_18004404C
0x18004403c  mov     rsi, [rbp+57h+arg_10]
0x180044040  inc     r15d
0x180044043  jmp     loc_180043E64
0x180044048  mov     edi, eax
0x18004404a  jmp     short loc_18004404E
0x18004404c  mov     edi, ebx
0x18004404e  lea     rcx, [rbp+57h+var_80]; this
0x180044052  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180044057  mov     eax, edi
0x180044059  add     rsp, 0C0h
0x180044060  pop     r15
0x180044062  pop     r13
0x180044064  pop     r12
0x180044066  pop     rdi
0x180044067  pop     rsi
0x180044068  pop     rbx
0x180044069  pop     rbp
0x18004406a  retn
```
