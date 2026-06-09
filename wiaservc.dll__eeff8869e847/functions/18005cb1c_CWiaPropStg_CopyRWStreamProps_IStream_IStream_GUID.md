# CWiaPropStg::CopyRWStreamProps(IStream *,IStream *,_GUID *)

- ea: `0x18005cb1c`
- end: `0x18005cecb`
- name: `?CopyRWStreamProps@CWiaPropStg@@AEAAJPEAUIStream@@0PEAU_GUID@@@Z`
- size: `943`
- prototype: `__int64 __fastcall(CWiaPropStg *__hidden this, IUnknown *pUnk, IUnknown *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005d390`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x180017c7c`
- `0x18002de18`
- `0x18002def8`
- `0x18005c7b0`
- `0x18005cb1c`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18005cc97`
- `ole32!CoTaskMemFree` at `0x18005cccb`
- `ole32!CoTaskMemFree` at `0x18005cc97`
- `ole32!CoTaskMemFree` at `0x18005cccb`
- `ole32!PropVariantClear` at `0x18005cbe0`
- `ole32!PropVariantClear` at `0x18005cbe0`
- `api-ms-win-core-com-l2-1-1!StgCreatePropStg` at `0x18005cc03`
- `api-ms-win-core-com-l2-1-1!StgCreatePropStg` at `0x18005cc03`
- `api-ms-win-core-com-l2-1-1!StgOpenPropStg` at `0x18005cb8c`
- `api-ms-win-core-com-l2-1-1!StgOpenPropStg` at `0x18005cb8c`

## string_xrefs

- `0x18005ccf5`: `CWiaPropStg::CopyRWStreamProps WritePropertyNames failed`
- `0x18005cd17`: `CWiaPropStg::CopyRWStreamProps WritePropertyNames failed`
- `0x18005cc3c`: `CWiaPropStg::CopyRWStreamProps`
- `0x18005cdc6`: `CWiaPropStg::CopyRWStreamProps`
- `0x18005ce21`: `CWiaPropStg::CopyRWStreamProps`
- `0x18005ce7c`: `CWiaPropStg::CopyRWStreamProps`
- `0x18005ce15`: `CWiaPropStg::CopyRWStreamProps, creating Dst storage failed 0x%X`
- `0x18005ce40`: `CWiaPropStg::CopyRWStreamProps, creating Dst storage failed 0x%X`
- `0x18005ce70`: `CWiaPropStg::CopyRWStreamProps, StgCreatePropStg for pSrc failed 0x%X`
- `0x18005ce9b`: `CWiaPropStg::CopyRWStreamProps, StgCreatePropStg for pSrc failed 0x%X`
- `0x18005cdba`: `CWiaPropStg::CopyRWStreamProps, Enum failed 0x%X`
- `0x18005cde5`: `CWiaPropStg::CopyRWStreamProps, Enum failed 0x%X`
- `0x18005cd88`: `CWiaPropStg::CopyRWStreamProps, Error writing number of properties`
- `0x18005cdaa`: `CWiaPropStg::CopyRWStreamProps, Error writing number of properties`

## pseudocode

```c
__int64 __fastcall CWiaPropStg::CopyRWStreamProps(CWiaPropStg *this, IUnknown *pUnk, IUnknown *a3, struct _GUID *a4)
{
  int v7; // edi
  GUID v8; // xmm0
  int v9; // r14d
  CWiaPropStg *v10; // rcx
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
  char *v21; // rbx
  void *v22; // rdx
  char *v23; // rbx
  void *v24; // rdx
  void **v25; // rax
  void *v26; // rdx
  __int64 v27; // rcx
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  IPropertyStorage *v34; // [rsp+30h] [rbp-39h] BYREF
  IPropertyStorage *ppPropStg; // [rsp+38h] [rbp-31h] BYREF
  struct tagPROPSPEC v36; // [rsp+40h] [rbp-29h] BYREF
  int v37; // [rsp+50h] [rbp-19h] BYREF
  int v38; // [rsp+54h] [rbp-15h] BYREF
  __int64 v39; // [rsp+58h] [rbp-11h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-9h] BYREF
  PROPVARIANT pvar[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v42; // [rsp+80h] [rbp+17h]
  LPVOID v43[7]; // [rsp+88h] [rbp+1Fh] BYREF

  ppPropStg = 0;
  v34 = 0;
  v39 = 0;
  v36.lpwstr = (LPOLESTR)4122;
  v36.ulKind = 1;
  *(_OWORD *)pv = 0;
  v7 = StgOpenPropStg(pUnk, &GUID_NULL, 0, 0, &ppPropStg);
  if ( v7 < 0 )
  {
    v28 = (char *)WiaTrace_TraceLog("CWiaPropStg::CopyRWStreamProps, StgCreatePropStg for pSrc failed 0x%X");
    WriteDbgTraceErrorWI("CWiaPropStg::CopyRWStreamProps", v28);
    WiaTrcLib::Free((WiaTrcLib *)v28, v29);
    v30 = (void **)WiaTrace_Trace("CWiaPropStg::CopyRWStreamProps, StgCreatePropStg for pSrc failed 0x%X", v7);
    WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"CWiaPropStg::CopyRWStreamProps", 1, v30);
    return (unsigned int)v7;
  }
  v42 = 0;
  *(_OWORD *)pvar = 0;
  if ( ((unsigned int (__fastcall *)(IPropertyStorage *, __int64, struct tagPROPSPEC *, PROPVARIANT *))ppPropStg->lpVtbl->ReadMultiple)(
         ppPropStg,
         1,
         &v36,
         pvar) )
  {
    v8 = GUID_NULL;
  }
  else
  {
    v8 = *(GUID *)pvar[1];
  }
  *a4 = v8;
  PropVariantClear(pvar);
  v7 = StgCreatePropStg(a3, &GUID_NULL, &GUID_NULL, 0, 0, &v34);
  if ( v7 < 0 )
  {
    v23 = (char *)WiaTrace_TraceLog("CWiaPropStg::CopyRWStreamProps, creating Dst storage failed 0x%X");
    WriteDbgTraceErrorWI("CWiaPropStg::CopyRWStreamProps", v23);
    WiaTrcLib::Free((WiaTrcLib *)v23, v24);
    v25 = (void **)WiaTrace_Trace("CWiaPropStg::CopyRWStreamProps, creating Dst storage failed 0x%X", v7);
    WiaTrace_ProcessTrace_Ex(v27, v26, (void *)"CWiaPropStg::CopyRWStreamProps", 1, v25);
    goto LABEL_25;
  }
  v7 = ((__int64 (__fastcall *)(IPropertyStorage *, __int64 *))ppPropStg->lpVtbl->Enum)(ppPropStg, &v39);
  if ( v7 < 0 )
  {
    v21 = (char *)WiaTrace_TraceLog("CWiaPropStg::CopyRWStreamProps, Enum failed 0x%X");
    WriteDbgTraceErrorWI("CWiaPropStg::CopyRWStreamProps", v21);
    WiaTrcLib::Free((WiaTrcLib *)v21, v22);
    v18 = (void **)WiaTrace_Trace("CWiaPropStg::CopyRWStreamProps, Enum failed 0x%X", v7);
  }
  else
  {
    v9 = 0;
    v36.ulKind = 1;
    v37 = 0;
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v39 + 24LL))(
               v39,
               1,
               pv,
               &v37) )
    {
      v38 = (int)pv[1];
      v36.propid = (PROPID)pv[1];
      v43[0] = pv[0];
      if ( (unsigned int)CWiaPropStg::CheckPropertyAccess(this, 0, 1, &v36) )
      {
        v7 = 0;
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
      }
      else
      {
        if ( pv[0] )
        {
          v7 = ((__int64 (__fastcall *)(IPropertyStorage *, __int64, int *, LPVOID *))v34->lpVtbl->WritePropertyNames)(
                 v34,
                 1,
                 &v38,
                 v43);
          if ( v7 < 0 )
          {
            v11 = (char *)WiaTrace_TraceLog("CWiaPropStg::CopyRWStreamProps WritePropertyNames failed");
            WriteDbgTraceErrorWI("CWiaPropStg::CopyRWStreamProps", v11);
            WiaTrcLib::Free((WiaTrcLib *)v11, v12);
            v13 = (void **)WiaTrace_Trace("CWiaPropStg::CopyRWStreamProps WritePropertyNames failed");
            WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CWiaPropStg::CopyRWStreamProps", 1, v13);
            break;
          }
          CoTaskMemFree(pv[0]);
        }
        v7 = CWiaPropStg::CopyItemProp(v10, ppPropStg, v34, &v36, "CWiaPropStg::CopyRWStreamProps");
        if ( v7 < 0 )
          break;
        ++v9;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    if ( v7 < 0 )
      goto LABEL_23;
    v36.propid = 111111;
    LOWORD(pvar[0]) = 3;
    LODWORD(pvar[1]) = v9;
    v7 = ((__int64 (__fastcall *)(IPropertyStorage *, __int64, struct tagPROPSPEC *, PROPVARIANT *, int))v34->lpVtbl->WriteMultiple)(
           v34,
           1,
           &v36,
           pvar,
           4098);
    if ( v7 >= 0 )
      goto LABEL_23;
    v16 = (char *)WiaTrace_TraceLog("CWiaPropStg::CopyRWStreamProps, Error writing number of properties");
    WriteDbgTraceErrorWI("CWiaPropStg::CopyRWStreamProps", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void **)WiaTrace_Trace("CWiaPropStg::CopyRWStreamProps, Error writing number of properties");
  }
  WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"CWiaPropStg::CopyRWStreamProps", 1, v18);
LABEL_23:
  ((void (__fastcall *)(IPropertyStorage *))v34->lpVtbl->Release)(v34);
LABEL_25:
  ((void (__fastcall *)(IPropertyStorage *))ppPropStg->lpVtbl->Release)(ppPropStg);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005cb1c  push    rbp
0x18005cb1e  push    rbx
0x18005cb1f  push    rsi
0x18005cb20  push    rdi
0x18005cb21  push    r13
0x18005cb23  push    r14
0x18005cb25  push    r15
0x18005cb27  lea     rbp, [rsp-27h]
0x18005cb2c  sub     rsp, 90h
0x18005cb33  mov     r15, rcx
0x18005cb36  mov     [rbp+57h+var_88], 0
0x18005cb3e  mov     rax, rdx
0x18005cb41  mov     [rbp+57h+var_90], 0
0x18005cb49  lea     rcx, [rbp+57h+var_88]
0x18005cb4d  mov     [rbp+57h+var_68], 0
0x18005cb55  mov     [rsp+0C0h+ppPropStg], rcx; ppPropStg
0x18005cb5a  lea     r14, GUID_NULL
0x18005cb61  mov     rbx, r9
0x18005cb64  mov     qword ptr [rbp+57h+var_80.8], 101Ah
0x18005cb6c  mov     rsi, r8
0x18005cb6f  xorps   xmm0, xmm0
0x18005cb72  mov     r13d, 1
0x18005cb78  mov     rcx, rax; pUnk
0x18005cb7b  xor     r9d, r9d; dwReserved
0x18005cb7e  mov     [rbp+57h+var_80.ulKind], r13d
0x18005cb82  xor     r8d, r8d; grfFlags
0x18005cb85  mov     rdx, r14; fmtid
0x18005cb88  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18005cb8c  call    cs:__imp_StgOpenPropStg
0x18005cb92  mov     edi, eax
0x18005cb94  test    eax, eax
0x18005cb96  js      loc_18005CE6E
0x18005cb9c  mov     rcx, [rbp+57h+var_88]
0x18005cba0  lea     r9, [rbp+57h+pvar]
0x18005cba4  xor     eax, eax
0x18005cba6  lea     r8, [rbp+57h+var_80]
0x18005cbaa  mov     [rbp+57h+var_40], rax
0x18005cbae  xorps   xmm0, xmm0
0x18005cbb1  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18005cbb5  mov     rax, [rcx]
0x18005cbb8  mov     edx, r13d
0x18005cbbb  mov     rax, [rax+18h]
0x18005cbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cbc4  test    eax, eax
0x18005cbc6  jnz     short loc_18005CBD1
0x18005cbc8  mov     rax, [rbp+57h+pvar+8]
0x18005cbcc  movups  xmm0, xmmword ptr [rax]
0x18005cbcf  jmp     short loc_18005CBD8
0x18005cbd1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18005cbd8  lea     rcx, [rbp+57h+pvar]; pvar
0x18005cbdc  movdqu  xmmword ptr [rbx], xmm0
0x18005cbe0  call    cs:__imp_PropVariantClear
0x18005cbe6  lea     rax, [rbp+57h+var_90]
0x18005cbea  xor     r9d, r9d; grfFlags
0x18005cbed  mov     [rsp+0C0h+var_98], rax; ppPropStg
0x18005cbf2  mov     r8, r14; pclsid
0x18005cbf5  mov     rdx, r14; fmtid
0x18005cbf8  mov     dword ptr [rsp+0C0h+ppPropStg], 0; dwReserved
0x18005cc00  mov     rcx, rsi; pUnk
0x18005cc03  call    cs:__imp_StgCreatePropStg
0x18005cc09  mov     edi, eax
0x18005cc0b  test    eax, eax
0x18005cc0d  js      loc_18005CE13
0x18005cc13  mov     rcx, [rbp+57h+var_88]
0x18005cc17  lea     rdx, [rbp+57h+var_68]
0x18005cc1b  mov     rax, [rcx]
0x18005cc1e  mov     rax, [rax+58h]
0x18005cc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc27  mov     edi, eax
0x18005cc29  test    eax, eax
0x18005cc2b  js      loc_18005CDB8
0x18005cc31  xor     r14d, r14d
0x18005cc34  mov     [rbp+57h+var_80.ulKind], r13d
0x18005cc38  mov     [rbp+57h+var_70], r14d
0x18005cc3c  lea     rsi, aCwiapropstgCop_4; "CWiaPropStg::CopyRWStreamProps"
0x18005cc43  mov     rcx, [rbp+57h+var_68]
0x18005cc47  lea     r9, [rbp+57h+var_70]
0x18005cc4b  lea     r8, [rbp+57h+pv]
0x18005cc4f  mov     edx, r13d
0x18005cc52  mov     rax, [rcx]
0x18005cc55  mov     rax, [rax+18h]
0x18005cc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc5e  test    eax, eax
0x18005cc60  jnz     loc_18005CD33
0x18005cc66  mov     ecx, dword ptr [rbp+57h+pv+8]
0x18005cc69  lea     r9, [rbp+57h+var_80]; struct tagPROPSPEC *
0x18005cc6d  mov     rax, [rbp+57h+pv]
0x18005cc71  mov     r8d, r13d; int
0x18005cc74  mov     [rbp+57h+var_6C], ecx
0x18005cc77  xor     edx, edx; int
0x18005cc79  mov     dword ptr [rbp+57h+var_80.8], ecx
0x18005cc7c  mov     rcx, r15; this
0x18005cc7f  mov     [rbp+57h+var_38], rax
0x18005cc83  call    ?CheckPropertyAccess@CWiaPropStg@@QEAAJHJPEAUtagPROPSPEC@@@Z; CWiaPropStg::CheckPropertyAccess(int,long,tagPROPSPEC *)
0x18005cc88  test    eax, eax
0x18005cc8a  jz      short loc_18005CC9F
0x18005cc8c  mov     rcx, [rbp+57h+pv]; pv
0x18005cc90  xor     edi, edi
0x18005cc92  test    rcx, rcx
0x18005cc95  jz      short loc_18005CC43
0x18005cc97  call    cs:__imp_CoTaskMemFree
0x18005cc9d  jmp     short loc_18005CC43
0x18005cc9f  cmp     [rbp+57h+pv], 0
0x18005cca4  jz      short loc_18005CCD1
0x18005cca6  mov     rcx, [rbp+57h+var_90]
0x18005ccaa  lea     r9, [rbp+57h+var_38]
0x18005ccae  lea     r8, [rbp+57h+var_6C]
0x18005ccb2  mov     edx, r13d
0x18005ccb5  mov     rax, [rcx]
0x18005ccb8  mov     rax, [rax+38h]
0x18005ccbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ccc1  mov     edi, eax
0x18005ccc3  test    eax, eax
0x18005ccc5  js      short loc_18005CCF5
0x18005ccc7  mov     rcx, [rbp+57h+pv]; pv
0x18005cccb  call    cs:__imp_CoTaskMemFree
0x18005ccd1  mov     r8, [rbp+57h+var_90]; struct IPropertyStorage *
0x18005ccd5  lea     r9, [rbp+57h+var_80]; struct tagPROPSPEC *
0x18005ccd9  mov     rdx, [rbp+57h+var_88]; struct IPropertyStorage *
0x18005ccdd  mov     [rsp+0C0h+ppPropStg], rsi; char *
0x18005cce2  call    ?CopyItemProp@CWiaPropStg@@AEAAJPEAUIPropertyStorage@@0PEAUtagPROPSPEC@@PEAD@Z; CWiaPropStg::CopyItemProp(IPropertyStorage *,IPropertyStorage *,tagPROPSPEC *,char *)
0x18005cce7  mov     edi, eax
0x18005cce9  test    eax, eax
0x18005cceb  js      short loc_18005CD33
0x18005cced  add     r14d, r13d
0x18005ccf0  jmp     loc_18005CC43
0x18005ccf5  lea     rcx, aCwiapropstgCop_2; "CWiaPropStg::CopyRWStreamProps WritePro"...
0x18005ccfc  call    WiaTrace_TraceLog
0x18005cd01  mov     rdx, rax; char *
0x18005cd04  mov     rcx, rsi; char *
0x18005cd07  mov     rbx, rax
0x18005cd0a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005cd0f  mov     rcx, rbx; this
0x18005cd12  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005cd17  lea     rcx, aCwiapropstgCop_2; "CWiaPropStg::CopyRWStreamProps WritePro"...
0x18005cd1e  call    WiaTrace_Trace
0x18005cd23  mov     r9d, r13d; int
0x18005cd26  mov     [rsp+0C0h+ppPropStg], rax; lpMem
0x18005cd2b  mov     r8, rsi; int
0x18005cd2e  call    WiaTrace_ProcessTrace_Ex
0x18005cd33  mov     rcx, [rbp+57h+var_68]
0x18005cd37  mov     rax, [rcx]
0x18005cd3a  mov     rax, [rax+10h]
0x18005cd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd43  test    edi, edi
0x18005cd45  js      loc_18005CE01
0x18005cd4b  mov     rcx, [rbp+57h+var_90]
0x18005cd4f  lea     r9, [rbp+57h+pvar]
0x18005cd53  mov     eax, 3
0x18005cd58  mov     dword ptr [rbp+57h+var_80.8], 1B207h
0x18005cd5f  mov     word ptr [rbp+57h+pvar], ax
0x18005cd63  lea     r8, [rbp+57h+var_80]
0x18005cd67  mov     dword ptr [rbp+57h+pvar+8], r14d
0x18005cd6b  mov     edx, r13d
0x18005cd6e  mov     rax, [rcx]
0x18005cd71  mov     dword ptr [rsp+0C0h+ppPropStg], 1002h
0x18005cd79  mov     rax, [rax+20h]
0x18005cd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd82  mov     edi, eax
0x18005cd84  test    eax, eax
0x18005cd86  jns     short loc_18005CE01
0x18005cd88  lea     rcx, aCwiapropstgCop_1; "CWiaPropStg::CopyRWStreamProps, Error w"...
0x18005cd8f  call    WiaTrace_TraceLog
0x18005cd94  mov     rdx, rax; char *
0x18005cd97  mov     rcx, rsi; char *
0x18005cd9a  mov     rbx, rax
0x18005cd9d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005cda2  mov     rcx, rbx; this
0x18005cda5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005cdaa  lea     rcx, aCwiapropstgCop_1; "CWiaPropStg::CopyRWStreamProps, Error w"...
0x18005cdb1  call    WiaTrace_Trace
0x18005cdb6  jmp     short loc_18005CDF1
0x18005cdb8  mov     edx, edi
0x18005cdba  lea     rcx, aCwiapropstgCop; "CWiaPropStg::CopyRWStreamProps, Enum fa"...
0x18005cdc1  call    WiaTrace_TraceLog
0x18005cdc6  lea     rsi, aCwiapropstgCop_4; "CWiaPropStg::CopyRWStreamProps"
0x18005cdcd  mov     rdx, rax; char *
0x18005cdd0  mov     rcx, rsi; char *
0x18005cdd3  mov     rbx, rax
0x18005cdd6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005cddb  mov     rcx, rbx; this
0x18005cdde  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005cde3  mov     edx, edi
0x18005cde5  lea     rcx, aCwiapropstgCop; "CWiaPropStg::CopyRWStreamProps, Enum fa"...
0x18005cdec  call    WiaTrace_Trace
0x18005cdf1  mov     r9d, r13d; int
0x18005cdf4  mov     [rsp+0C0h+ppPropStg], rax; lpMem
0x18005cdf9  mov     r8, rsi; int
0x18005cdfc  call    WiaTrace_ProcessTrace_Ex
0x18005ce01  mov     rcx, [rbp+57h+var_90]
0x18005ce05  mov     rax, [rcx]
0x18005ce08  mov     rax, [rax+10h]
0x18005ce0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce11  jmp     short loc_18005CE5C
0x18005ce13  mov     edx, edi
0x18005ce15  lea     rcx, aCwiapropstgCop_3; "CWiaPropStg::CopyRWStreamProps, creatin"...
0x18005ce1c  call    WiaTrace_TraceLog
0x18005ce21  lea     rsi, aCwiapropstgCop_4; "CWiaPropStg::CopyRWStreamProps"
0x18005ce28  mov     rdx, rax; char *
0x18005ce2b  mov     rcx, rsi; char *
0x18005ce2e  mov     rbx, rax
0x18005ce31  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ce36  mov     rcx, rbx; this
0x18005ce39  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ce3e  mov     edx, edi
0x18005ce40  lea     rcx, aCwiapropstgCop_3; "CWiaPropStg::CopyRWStreamProps, creatin"...
0x18005ce47  call    WiaTrace_Trace
0x18005ce4c  mov     r9d, r13d; int
0x18005ce4f  mov     [rsp+0C0h+ppPropStg], rax; lpMem
0x18005ce54  mov     r8, rsi; int
0x18005ce57  call    WiaTrace_ProcessTrace_Ex
0x18005ce5c  mov     rcx, [rbp+57h+var_88]
0x18005ce60  mov     rax, [rcx]
0x18005ce63  mov     rax, [rax+10h]
0x18005ce67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce6c  jmp     short loc_18005CEB7
0x18005ce6e  mov     edx, edi
0x18005ce70  lea     rcx, aCwiapropstgCop_0; "CWiaPropStg::CopyRWStreamProps, StgCrea"...
0x18005ce77  call    WiaTrace_TraceLog
0x18005ce7c  lea     rsi, aCwiapropstgCop_4; "CWiaPropStg::CopyRWStreamProps"
0x18005ce83  mov     rdx, rax; char *
0x18005ce86  mov     rcx, rsi; char *
0x18005ce89  mov     rbx, rax
0x18005ce8c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005ce91  mov     rcx, rbx; this
0x18005ce94  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005ce99  mov     edx, edi
0x18005ce9b  lea     rcx, aCwiapropstgCop_0; "CWiaPropStg::CopyRWStreamProps, StgCrea"...
0x18005cea2  call    WiaTrace_Trace
0x18005cea7  mov     r9d, r13d; int
0x18005ceaa  mov     [rsp+0C0h+ppPropStg], rax; lpMem
0x18005ceaf  mov     r8, rsi; int
0x18005ceb2  call    WiaTrace_ProcessTrace_Ex
0x18005ceb7  mov     eax, edi
0x18005ceb9  add     rsp, 90h
0x18005cec0  pop     r15
0x18005cec2  pop     r14
0x18005cec4  pop     r13
0x18005cec6  pop     rdi
0x18005cec7  pop     rsi
0x18005cec8  pop     rbx
0x18005cec9  pop     rbp
0x18005ceca  retn
```
