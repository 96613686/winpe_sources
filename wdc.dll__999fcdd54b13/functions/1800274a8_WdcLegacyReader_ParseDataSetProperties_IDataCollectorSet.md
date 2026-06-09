# WdcLegacyReader::ParseDataSetProperties(IDataCollectorSet *)

- ea: `0x1800274a8`
- end: `0x1800278c3`
- name: `?ParseDataSetProperties@WdcLegacyReader@@AEAAJPEAUIDataCollectorSet@@@Z`
- size: `1051`
- prototype: `__int64 __fastcall(WdcLegacyReader *__hidden this, struct IDataCollectorSet *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006b5bc`

## callees

- `0x1800044ac`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x1800274a8`
- `0x180027d24`
- `0x180068008`
- `0x18006b560`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800274f1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800275ce`
- `OLEAUT32!__imp_SysAllocString` at `0x1800277b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002780f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800274f1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800275ce`
- `OLEAUT32!__imp_SysAllocString` at `0x1800277b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002780f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800275c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800277ab`
- `OLEAUT32!__imp_SysFreeString` at `0x180027804`
- `OLEAUT32!__imp_SysFreeString` at `0x180027895`
- `OLEAUT32!__imp_SysFreeString` at `0x1800275c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800277ab`
- `OLEAUT32!__imp_SysFreeString` at `0x180027804`
- `OLEAUT32!__imp_SysFreeString` at `0x180027895`

## string_xrefs

- `0x1800274c7`: `Comment`
- `0x180027538`: `WdcLegacyReader::ParseDataSetProperties`
- `0x180027578`: `WdcLegacyReader::ParseDataSetProperties`
- `0x18002778b`: `WdcLegacyReader::ParseDataSetProperties`
- `0x18002786d`: `WdcLegacyReader::ParseDataSetProperties`

## pseudocode

```c
__int64 __fastcall WdcLegacyReader::ParseDataSetProperties(WdcLegacyReader *this, struct IDataCollectorSet *a2)
{
  OLECHAR *v2; // rdi
  struct _WDC_LEGACY_PROPERTY ***v5; // r14
  const OLECHAR *v6; // rbx
  BSTR v7; // rax
  unsigned int v8; // ebx
  int v9; // eax
  WdcLegacyReader *v10; // rcx
  int v11; // r8d
  struct _WDC_LEGACY_PROPERTY ***v12; // r14
  const OLECHAR *v13; // rbx
  BSTR v14; // rax
  WdcLegacyReader *v15; // rcx
  int v16; // r8d
  struct _WDC_LEGACY_PROPERTY ***v17; // r14
  WdcLegacyReader *v18; // rcx
  int v19; // r8d
  struct _WDC_LEGACY_PROPERTY ***v20; // r14
  WdcLegacyReader *v21; // rcx
  int v22; // r8d
  const char *v23; // rdx
  int v24; // r8d
  WCHAR *v25; // r14
  int String; // eax
  const char *v27; // rdx
  int v28; // r8d
  BSTR v29; // rax
  struct _WDC_LEGACY_PROPERTY ***v30; // rbx
  const OLECHAR *v31; // r14
  BSTR v32; // rax
  WdcLegacyReader *v33; // rcx
  int v34; // r8d
  int v35; // eax
  __int64 v37; // [rsp+20h] [rbp-20h]
  __int64 v38; // [rsp+20h] [rbp-20h]
  __int64 v39; // [rsp+20h] [rbp-20h]
  __int64 v40; // [rsp+30h] [rbp-10h] BYREF
  int v41; // [rsp+80h] [rbp+40h] BYREF
  struct _WDC_LEGACY_PROPERTY *v42; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v41 = 0;
  v42 = 0;
  v40 = 0;
  if ( (int)WdcLegacyReader::GetProperty(this, L"Comment", &v42) >= 0 )
  {
    v5 = (struct _WDC_LEGACY_PROPERTY ***)v42;
    v6 = (const OLECHAR *)*((_QWORD *)v42 + 3);
    v7 = SysAllocString(v6);
    v2 = v7;
    if ( v6 && !v7 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      LODWORD(v38) = -2147024882;
      v8 = -2147024882;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
        "WdcLegacyReader::ParseDataSetProperties",
        0,
        L"FAILURE: 0x%08x",
        v38);
      goto LABEL_51;
    }
    v9 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR))a2->lpVtbl->put_Description)(a2, v7);
    v8 = v9;
    if ( v9 < 0 )
      goto LABEL_6;
    WdcLegacyReader::FreeProperty(v10, v5, v11);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"LogFileFolder", &v42) >= 0 )
  {
    v12 = (struct _WDC_LEGACY_PROPERTY ***)v42;
    v13 = (const OLECHAR *)*((_QWORD *)v42 + 3);
    if ( v2 )
    {
      SysFreeString(v2);
      v2 = 0;
    }
    v14 = SysAllocString(v13);
    if ( v13 && !v14 )
      goto LABEL_14;
    v2 = v14;
    v9 = ((__int64 (__fastcall *)(struct IDataCollectorSet *))a2->lpVtbl->put_RootPath)(a2);
    v8 = v9;
    if ( v9 < 0 )
      goto LABEL_6;
    WdcLegacyReader::FreeProperty(v15, v12, v16);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"LogFileMaxSize", &v42) >= 0 )
  {
    v17 = (struct _WDC_LEGACY_PROPERTY ***)v42;
    v9 = WdcHexToLong(*((const unsigned __int16 **)v42 + 3), &v41);
    v8 = v9;
    if ( v9 < 0 )
      goto LABEL_6;
    if ( v41 > 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IDataCollectorSet *))a2->lpVtbl->put_SegmentMaxSize)(a2);
      v8 = v9;
      if ( v9 < 0 )
        goto LABEL_6;
    }
    WdcLegacyReader::FreeProperty(v18, v17, v19);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"LogFileSerialNumber", &v42) >= 0 )
  {
    v20 = (struct _WDC_LEGACY_PROPERTY ***)v42;
    v9 = WdcHexToLong(*((const unsigned __int16 **)v42 + 3), &v41);
    v8 = v9;
    if ( v9 >= 0 )
    {
      if ( v41 <= 0
        || (v9 = ((__int64 (__fastcall *)(struct IDataCollectorSet *))a2->lpVtbl->put_SerialNumber)(a2), v8 = v9, v9 >= 0) )
      {
        WdcLegacyReader::FreeProperty(v21, v20, v22);
        goto LABEL_28;
      }
    }
LABEL_6:
    LODWORD(v37) = v9;
LABEL_7:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
      "WdcLegacyReader::ParseDataSetProperties",
      0,
      L"FAILURE: 0x%08x",
      v37);
    goto LABEL_49;
  }
LABEL_28:
  if ( (int)WdcLegacyReader::GetProperty(this, L"LogName", &v42) >= 0
    || (int)WdcLegacyReader::GetProperty(this, L"AlertName", &v42) >= 0
    || (int)WdcLegacyReader::GetProperty(this, L"GraphTitle", &v42) >= 0 )
  {
    v30 = (struct _WDC_LEGACY_PROPERTY ***)v42;
    v31 = (const OLECHAR *)*((_QWORD *)v42 + 3);
    if ( v2 )
    {
      SysFreeString(v2);
      v2 = 0;
    }
    v32 = SysAllocString(v31);
    if ( v31 && !v32 )
    {
LABEL_14:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
LABEL_15:
      v8 = -2147024882;
      LODWORD(v37) = -2147024882;
      goto LABEL_7;
    }
    v25 = 0;
    v2 = v32;
    WdcLegacyReader::FreeProperty(v33, v30, v34);
    goto LABEL_45;
  }
  v25 = (WCHAR *)WdcAlloc(0x800u, v23, v24);
  if ( !v25 )
    goto LABEL_15;
  *v25 = 0;
  String = WdcLoadString(0x29u, v25, 0x400u);
  v8 = String;
  if ( String >= 0 )
  {
    if ( v2 )
    {
      SysFreeString(v2);
      v2 = 0;
    }
    v29 = SysAllocString(v25);
    if ( !v29 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      v8 = -2147024882;
      LODWORD(v37) = -2147024882;
      goto LABEL_34;
    }
    v2 = v29;
LABEL_45:
    v35 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, OLECHAR *, _QWORD, __int64, __int64 *))a2->lpVtbl->Commit)(
            a2,
            v2,
            *((_QWORD *)this + 4),
            4096,
            &v40);
    v8 = v35;
    if ( v35 < 0 )
    {
      LODWORD(v39) = v35;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
        "WdcLegacyReader::ParseDataSetProperties",
        0,
        L"FAILURE: 0x%08x",
        v39);
    }
    if ( !v25 )
      goto LABEL_49;
    goto LABEL_48;
  }
  LODWORD(v37) = String;
LABEL_34:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
    "WdcLegacyReader::ParseDataSetProperties",
    0,
    L"FAILURE: 0x%08x",
    v37);
LABEL_48:
  WdcFree(v25, v27, v28);
LABEL_49:
  if ( v2 )
    SysFreeString(v2);
LABEL_51:
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  return v8;
}

```

## disassembly

```asm
0x1800274a8  mov     [rsp-28h+arg_0], rbx
0x1800274ad  push    rbp
0x1800274ae  push    rsi
0x1800274af  push    rdi
0x1800274b0  push    r14
0x1800274b2  push    r15
0x1800274b4  mov     rbp, rsp
0x1800274b7  sub     rsp, 40h
0x1800274bb  xor     edi, edi
0x1800274bd  lea     r8, [rbp+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x1800274c1  mov     r15, rdx
0x1800274c4  mov     [rbp+arg_10], edi
0x1800274c7  lea     rdx, aComment; "Comment"
0x1800274ce  mov     [rbp+arg_18], rdi
0x1800274d2  mov     [rbp+var_10], rdi
0x1800274d6  mov     rsi, rcx
0x1800274d9  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x1800274de  test    eax, eax
0x1800274e0  js      loc_180027598
0x1800274e6  mov     r14, [rbp+arg_18]
0x1800274ea  mov     rbx, [r14+18h]
0x1800274ee  mov     rcx, rbx; psz
0x1800274f1  call    cs:__imp_SysAllocString
0x1800274f7  mov     rdi, rax
0x1800274fa  test    rbx, rbx
0x1800274fd  jz      short loc_180027552
0x1800274ff  test    rax, rax
0x180027502  jnz     short loc_180027552
0x180027504  mov     esi, 8007000Eh
0x180027509  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027510  xor     r8d, r8d; int
0x180027513  mov     dword ptr [rsp+40h+var_20], esi
0x180027517  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18002751e  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180027525  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002752a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027531  mov     dword ptr [rsp+40h+var_20], esi
0x180027535  xor     r8d, r8d; int
0x180027538  lea     rdx, aWdclegacyreade_3; "WdcLegacyReader::ParseDataSetProperties"
0x18002753f  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x180027546  mov     ebx, esi
0x180027548  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002754d  jmp     loc_18002789B
0x180027552  mov     rax, [r15]
0x180027555  mov     rdx, rdi
0x180027558  mov     rcx, r15
0x18002755b  mov     rax, [rax+58h]
0x18002755f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027564  mov     ebx, eax
0x180027566  test    eax, eax
0x180027568  jns     short loc_180027590
0x18002756a  mov     dword ptr [rsp+40h+var_20], eax
0x18002756e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027575  xor     r8d, r8d; int
0x180027578  lea     rdx, aWdclegacyreade_3; "WdcLegacyReader::ParseDataSetProperties"
0x18002757f  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x180027586  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002758b  jmp     loc_18002788D
0x180027590  mov     rdx, r14; struct _WDC_LEGACY_PROPERTY *
0x180027593  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027598  lea     r8, [rbp+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18002759c  mov     rcx, rsi; this
0x18002759f  lea     rdx, aLogfilefolder; "LogFileFolder"
0x1800275a6  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x1800275ab  test    eax, eax
0x1800275ad  js      loc_180027639
0x1800275b3  mov     r14, [rbp+arg_18]
0x1800275b7  mov     rbx, [r14+18h]
0x1800275bb  test    rdi, rdi
0x1800275be  jz      short loc_1800275CB
0x1800275c0  mov     rcx, rdi; bstrString
0x1800275c3  call    cs:__imp_SysFreeString
0x1800275c9  xor     edi, edi
0x1800275cb  mov     rcx, rbx; psz
0x1800275ce  call    cs:__imp_SysAllocString
0x1800275d4  mov     rdx, rax
0x1800275d7  test    rbx, rbx
0x1800275da  jz      short loc_180027612
0x1800275dc  test    rax, rax
0x1800275df  jnz     short loc_180027612
0x1800275e1  mov     esi, 8007000Eh
0x1800275e6  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800275ed  xor     r8d, r8d; int
0x1800275f0  mov     dword ptr [rsp+40h+var_20], esi
0x1800275f4  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x1800275fb  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180027602  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180027607  mov     ebx, esi
0x180027609  mov     dword ptr [rsp+40h+var_20], esi
0x18002760d  jmp     loc_18002756E
0x180027612  mov     rdi, rdx
0x180027615  mov     rax, [r15]
0x180027618  mov     rcx, r15
0x18002761b  mov     rax, [rax+0B8h]
0x180027622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027627  mov     ebx, eax
0x180027629  test    eax, eax
0x18002762b  js      loc_18002756A
0x180027631  mov     rdx, r14; struct _WDC_LEGACY_PROPERTY *
0x180027634  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027639  lea     r8, [rbp+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18002763d  mov     rcx, rsi; this
0x180027640  lea     rdx, aLogfilemaxsize; "LogFileMaxSize"
0x180027647  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18002764c  test    eax, eax
0x18002764e  js      short loc_180027696
0x180027650  mov     r14, [rbp+arg_18]
0x180027654  lea     rdx, [rbp+arg_10]; int *
0x180027658  mov     rcx, [r14+18h]; unsigned __int16 *
0x18002765c  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x180027661  mov     ebx, eax
0x180027663  test    eax, eax
0x180027665  js      loc_18002756A
0x18002766b  mov     edx, [rbp+arg_10]
0x18002766e  test    edx, edx
0x180027670  jle     short loc_18002768E
0x180027672  mov     rax, [r15]
0x180027675  mov     rcx, r15
0x180027678  mov     rax, [rax+0E8h]
0x18002767f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027684  mov     ebx, eax
0x180027686  test    eax, eax
0x180027688  js      loc_18002756A
0x18002768e  mov     rdx, r14; struct _WDC_LEGACY_PROPERTY *
0x180027691  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027696  lea     r8, [rbp+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18002769a  mov     rcx, rsi; this
0x18002769d  lea     rdx, aLogfileserialn; "LogFileSerialNumber"
0x1800276a4  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x1800276a9  test    eax, eax
0x1800276ab  js      short loc_1800276F3
0x1800276ad  mov     r14, [rbp+arg_18]
0x1800276b1  lea     rdx, [rbp+arg_10]; int *
0x1800276b5  mov     rcx, [r14+18h]; unsigned __int16 *
0x1800276b9  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x1800276be  mov     ebx, eax
0x1800276c0  test    eax, eax
0x1800276c2  js      loc_18002756A
0x1800276c8  mov     edx, [rbp+arg_10]
0x1800276cb  test    edx, edx
0x1800276cd  jle     short loc_1800276EB
0x1800276cf  mov     rax, [r15]
0x1800276d2  mov     rcx, r15
0x1800276d5  mov     rax, [rax+0F8h]
0x1800276dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276e1  mov     ebx, eax
0x1800276e3  test    eax, eax
0x1800276e5  js      loc_18002756A
0x1800276eb  mov     rdx, r14; struct _WDC_LEGACY_PROPERTY *
0x1800276ee  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x1800276f3  lea     r8, [rbp+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x1800276f7  mov     rcx, rsi; this
0x1800276fa  lea     rdx, aLogname; "LogName"
0x180027701  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x180027706  test    eax, eax
0x180027708  jns     loc_1800277F4
0x18002770e  lea     r8, [rbp+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x180027712  mov     rcx, rsi; this
0x180027715  lea     rdx, aAlertname; "AlertName"
0x18002771c  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x180027721  test    eax, eax
0x180027723  jns     loc_1800277F4
0x180027729  lea     r8, [rbp+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18002772d  mov     rcx, rsi; this
0x180027730  lea     rdx, aGraphtitle; "GraphTitle"
0x180027737  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18002773c  test    eax, eax
0x18002773e  jns     loc_1800277F4
0x180027744  mov     ecx, 800h; dwBytes
0x180027749  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002774e  mov     r14, rax
0x180027751  test    rax, rax
0x180027754  jnz     short loc_180027760
0x180027756  mov     esi, 8007000Eh
0x18002775b  jmp     loc_180027607
0x180027760  xor     eax, eax
0x180027762  mov     r8d, 400h; cchBufferMax
0x180027768  mov     rdx, r14; lpBuffer
0x18002776b  mov     [r14], ax
0x18002776f  lea     ecx, [rax+29h]; uID
0x180027772  call    ?WdcLoadString@@YAJKPEAG_K@Z; WdcLoadString(ulong,ushort *,unsigned __int64)
0x180027777  mov     ebx, eax
0x180027779  test    eax, eax
0x18002777b  jns     short loc_1800277A3
0x18002777d  mov     dword ptr [rsp+40h+var_20], eax
0x180027781  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027788  xor     r8d, r8d; int
0x18002778b  lea     rdx, aWdclegacyreade_3; "WdcLegacyReader::ParseDataSetProperties"
0x180027792  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x180027799  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002779e  jmp     loc_180027885
0x1800277a3  test    rdi, rdi
0x1800277a6  jz      short loc_1800277B3
0x1800277a8  mov     rcx, rdi; bstrString
0x1800277ab  call    cs:__imp_SysFreeString
0x1800277b1  xor     edi, edi
0x1800277b3  mov     rcx, r14; psz
0x1800277b6  call    cs:__imp_SysAllocString
0x1800277bc  test    rax, rax
0x1800277bf  jnz     short loc_1800277EF
0x1800277c1  mov     esi, 8007000Eh
0x1800277c6  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800277cd  xor     r8d, r8d; int
0x1800277d0  mov     dword ptr [rsp+40h+var_20], esi
0x1800277d4  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x1800277db  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x1800277e2  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800277e7  mov     ebx, esi
0x1800277e9  mov     dword ptr [rsp+40h+var_20], esi
0x1800277ed  jmp     short loc_180027781
0x1800277ef  mov     rdi, rax
0x1800277f2  jmp     short loc_180027831
0x1800277f4  mov     rbx, [rbp+arg_18]
0x1800277f8  mov     r14, [rbx+18h]
0x1800277fc  test    rdi, rdi
0x1800277ff  jz      short loc_18002780C
0x180027801  mov     rcx, rdi; bstrString
0x180027804  call    cs:__imp_SysFreeString
0x18002780a  xor     edi, edi
0x18002780c  mov     rcx, r14; psz
0x18002780f  call    cs:__imp_SysAllocString
0x180027815  test    r14, r14
0x180027818  jz      short loc_180027823
0x18002781a  test    rax, rax
0x18002781d  jz      loc_1800275E1
0x180027823  xor     r14d, r14d
0x180027826  mov     rdi, rax
0x180027829  mov     rdx, rbx; struct _WDC_LEGACY_PROPERTY *
0x18002782c  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027831  mov     rax, [r15]
0x180027834  lea     rcx, [rbp+var_10]
0x180027838  mov     r8, [rsi+20h]
0x18002783c  mov     r9d, 1000h
0x180027842  mov     [rsp+40h+var_20], rcx
0x180027847  mov     rdx, rdi
0x18002784a  mov     rcx, r15
0x18002784d  mov     rax, [rax+1E0h]
0x180027854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027859  mov     ebx, eax
0x18002785b  test    eax, eax
0x18002785d  jns     short loc_180027880
0x18002785f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027866  mov     dword ptr [rsp+40h+var_20], eax
0x18002786a  xor     r8d, r8d; int
0x18002786d  lea     rdx, aWdclegacyreade_3; "WdcLegacyReader::ParseDataSetProperties"
0x180027874  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x18002787b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180027880  test    r14, r14
0x180027883  jz      short loc_18002788D
0x180027885  mov     rcx, r14; void *
0x180027888  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002788d  test    rdi, rdi
0x180027890  jz      short loc_18002789B
0x180027892  mov     rcx, rdi; bstrString
0x180027895  call    cs:__imp_SysFreeString
0x18002789b  mov     rcx, [rbp+var_10]
0x18002789f  test    rcx, rcx
0x1800278a2  jz      short loc_1800278B0
0x1800278a4  mov     rax, [rcx]
0x1800278a7  mov     rax, [rax+10h]
0x1800278ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278b0  mov     eax, ebx
0x1800278b2  mov     rbx, [rsp+40h+arg_0]
0x1800278b7  add     rsp, 40h
0x1800278bb  pop     r15
0x1800278bd  pop     r14
0x1800278bf  pop     rdi
0x1800278c0  pop     rsi
0x1800278c1  pop     rbp
0x1800278c2  retn
```
