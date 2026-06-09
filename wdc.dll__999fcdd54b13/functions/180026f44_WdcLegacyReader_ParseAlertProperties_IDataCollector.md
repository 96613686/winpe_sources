# WdcLegacyReader::ParseAlertProperties(IDataCollector *)

- ea: `0x180026f44`
- end: `0x1800274a1`
- name: `?ParseAlertProperties@WdcLegacyReader@@AEAAJPEAUIDataCollector@@@Z`
- size: `1373`
- prototype: `__int64 __fastcall(WdcLegacyReader *__hidden this, struct IDataCollector *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18006b5bc`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x18001cb20`
- `0x180026f44`
- `0x180027d24`
- `0x180040730`
- `0x180068008`
- `0x18006b560`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002706d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800273af`
- `OLEAUT32!__imp_SysAllocString` at `0x18002706d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800273af`
- `OLEAUT32!__imp_SysFreeString` at `0x18002739d`
- `OLEAUT32!__imp_SysFreeString` at `0x180027452`
- `OLEAUT32!__imp_SysFreeString` at `0x18002739d`
- `OLEAUT32!__imp_SysFreeString` at `0x180027452`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180027216`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180027216`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027444`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027444`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002722b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002722b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800273f7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027436`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800273f7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027436`

## string_xrefs

- `0x180026faa`: `WdcLegacyReader::ParseAlertProperties`
- `0x1800270b8`: `WdcLegacyReader::ParseAlertProperties`
- `0x1800270fc`: `WdcLegacyReader::ParseAlertProperties`
- `0x180027158`: `WdcLegacyReader::ParseAlertProperties`
- `0x180026ff8`: `UpdateInterval`
- `0x180027246`: `Counter%05d.Path`

## pseudocode

```c
__int64 __fastcall WdcLegacyReader::ParseAlertProperties(WdcLegacyReader *this, struct IDataCollector *a2, int a3)
{
  unsigned __int16 *v4; // r15
  SAFEARRAY *v6; // r13
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r12
  unsigned int v9; // ebx
  const char *v10; // rdx
  int v11; // r8d
  OLECHAR *v12; // rsi
  int v13; // eax
  struct _WDC_LEGACY_PROPERTY ***v14; // rdi
  WdcLegacyReader *v15; // rcx
  int v16; // r8d
  struct _WDC_LEGACY_PROPERTY ***v17; // rdi
  const OLECHAR *v18; // rbx
  BSTR v19; // rax
  int v20; // eax
  WdcLegacyReader *v21; // rcx
  int v22; // r8d
  struct _WDC_LEGACY_PROPERTY ***v23; // rdi
  HRESULT Property; // eax
  WdcLegacyReader *v25; // rcx
  int v26; // r8d
  struct _WDC_LEGACY_PROPERTY ***v27; // rdi
  WdcLegacyReader *v28; // rcx
  int v29; // r8d
  int v30; // esi
  const char *v31; // rdx
  int v32; // r8d
  int v33; // edi
  SAFEARRAY *v34; // rax
  WdcLegacyReader *v35; // rcx
  int v36; // r8d
  struct _WDC_LEGACY_PROPERTY ***v37; // r11
  struct _WDC_LEGACY_PROPERTY ***v38; // rsi
  WdcLegacyReader *v39; // rcx
  int v40; // r8d
  const unsigned __int16 *v41; // r8
  struct _WDC_LEGACY_PROPERTY ***v42; // rsi
  WdcLegacyReader *v43; // rcx
  int v44; // r8d
  _QWORD *v45; // rsi
  OLECHAR *v46; // rcx
  BSTR v47; // rax
  __int64 v49; // [rsp+20h] [rbp-40h]
  int v50; // [rsp+20h] [rbp-40h]
  __int64 v51; // [rsp+20h] [rbp-40h]
  OLECHAR *v52; // [rsp+30h] [rbp-30h]
  struct _WDC_LEGACY_PROPERTY *v53; // [rsp+38h] [rbp-28h] BYREF
  __int64 v54; // [rsp+40h] [rbp-20h] BYREF
  void *ppvData; // [rsp+48h] [rbp-18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-10h] BYREF
  int v57; // [rsp+B0h] [rbp+50h] BYREF
  int v58; // [rsp+B8h] [rbp+58h] BYREF

  v53 = 0;
  v4 = 0;
  v57 = 0;
  v58 = 0;
  v52 = 0;
  v6 = 0;
  rgsabound = 0;
  ppvData = 0;
  v54 = 0;
  v7 = (unsigned __int16 *)WdcAlloc(0x800u, (const char *)a2, a3);
  v8 = v7;
  if ( !v7 )
  {
    v9 = -2147024882;
    v50 = -2147024882;
LABEL_3:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
      "WdcLegacyReader::ParseAlertProperties",
      0,
      L"FAILURE: 0x%08x",
      v50);
    v12 = 0;
    goto LABEL_53;
  }
  *v7 = 0;
  v13 = ((__int64 (__fastcall *)(struct IDataCollector *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IAlertDataCollector,
          &v54);
  v9 = v13;
  if ( v13 < 0 )
  {
LABEL_5:
    v50 = v13;
    goto LABEL_3;
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"UpdateInterval", &v53) >= 0 )
  {
    v14 = (struct _WDC_LEGACY_PROPERTY ***)v53;
    v13 = WdcHexToLong(*((const unsigned __int16 **)v53 + 3), &v57);
    v9 = v13;
    if ( v13 < 0 )
      goto LABEL_5;
    if ( v57 > 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v54 + 296LL))(v54);
      v9 = v13;
      if ( v13 < 0 )
        goto LABEL_5;
    }
    WdcLegacyReader::FreeProperty(v15, v14, v16);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"PerfLogName", &v53) >= 0 )
  {
    v17 = (struct _WDC_LEGACY_PROPERTY ***)v53;
    v18 = (const OLECHAR *)*((_QWORD *)v53 + 3);
    v19 = SysAllocString(v18);
    v52 = v19;
    v12 = v19;
    if ( v18 && !v19 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      LODWORD(v51) = -2147024882;
      v9 = -2147024882;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
        "WdcLegacyReader::ParseAlertProperties",
        0,
        L"FAILURE: 0x%08x",
        v51);
      goto LABEL_53;
    }
    v20 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v54 + 376LL))(v54, v19);
    v9 = v20;
    if ( v20 < 0 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
        "WdcLegacyReader::ParseAlertProperties",
        0,
        L"FAILURE: 0x%08x",
        v20);
      goto LABEL_53;
    }
    WdcLegacyReader::FreeProperty(v21, v17, v22);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"ActionFlags", &v53) >= 0 )
  {
    v23 = (struct _WDC_LEGACY_PROPERTY ***)v53;
    Property = WdcHexToLong(*((const unsigned __int16 **)v53 + 3), &v57);
    v9 = Property;
    if ( Property < 0 )
      goto LABEL_20;
    if ( (v57 & 1) != 0 )
    {
      Property = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 280LL))(v54, 0xFFFFFFFFLL);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_20;
    }
    WdcLegacyReader::FreeProperty(v25, v23, v26);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"CounterCount", &v53) < 0 )
  {
    v9 = 0;
    goto LABEL_52;
  }
  v27 = (struct _WDC_LEGACY_PROPERTY ***)v53;
  Property = WdcHexToLong(*((const unsigned __int16 **)v53 + 3), &v58);
  v9 = Property;
  if ( Property >= 0 )
  {
    WdcLegacyReader::FreeProperty(v28, v27, v29);
    v30 = v58;
    rgsabound.lLbound = 0;
    rgsabound.cElements = v58;
    v4 = (unsigned __int16 *)WdcAlloc(0x800u, v31, v32);
    if ( !v4 || (*v4 = 0, v33 = 1, v34 = SafeArrayCreate(8u, 1u, &rgsabound), (v6 = v34) == 0) )
    {
LABEL_28:
      v9 = -2147024882;
      LODWORD(v49) = -2147024882;
      goto LABEL_21;
    }
    Property = SafeArrayAccessData(v34, &ppvData);
    v9 = Property;
    if ( Property >= 0 )
    {
      while ( v33 <= v30 )
      {
        Property = StringCchPrintfW(v8, 0x400u, L"Counter%05d.Path", (unsigned int)v33);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        Property = WdcLegacyReader::GetProperty(this, v8, &v53);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        Property = StringCchCopyW(v4, 0x400u, *((const unsigned __int16 **)v53 + 3));
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        WdcLegacyReader::FreeProperty(v35, v37, v36);
        Property = StringCchPrintfW(v8, 0x400u, L"Counter%05d.AlertOverUnder", (unsigned int)v33);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        Property = WdcLegacyReader::GetProperty(this, v8, &v53);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        v38 = (struct _WDC_LEGACY_PROPERTY ***)v53;
        Property = WdcHexToLong(*((const unsigned __int16 **)v53 + 3), &v57);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        WdcLegacyReader::FreeProperty(v39, v38, v40);
        v41 = L"<";
        if ( v57 )
          v41 = L">";
        Property = StringCchCatW(v4, 0x400u, v41);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        Property = StringCchPrintfW(v8, 0x400u, L"Counter%05d.AlertThreshold", (unsigned int)v33);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        Property = WdcLegacyReader::GetProperty(this, v8, &v53);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        v42 = (struct _WDC_LEGACY_PROPERTY ***)v53;
        Property = StringCchCatW(v4, 0x400u, *((const unsigned __int16 **)v53 + 3));
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_20;
        WdcLegacyReader::FreeProperty(v43, v42, v44);
        v45 = ppvData;
        v46 = (OLECHAR *)*((_QWORD *)ppvData + v33 - 1);
        if ( v46 )
        {
          SysFreeString(v46);
          v45[v33 - 1] = 0;
        }
        v47 = SysAllocString(v4);
        if ( !v47 )
        {
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
            "WdcAssignString",
            0,
            L"FAILURE: 0x%08x",
            -2147024882);
          goto LABEL_28;
        }
        v45[v33 - 1] = v47;
        v30 = v58;
        ++v33;
      }
      SafeArrayUnaccessData(v6);
      ppvData = 0;
      Property = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v54 + 264LL))(v54, v6);
      v9 = Property;
      if ( Property >= 0 )
        goto LABEL_52;
    }
  }
LABEL_20:
  LODWORD(v49) = Property;
LABEL_21:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
    "WdcLegacyReader::ParseAlertProperties",
    0,
    L"FAILURE: 0x%08x",
    v49);
LABEL_52:
  v12 = v52;
LABEL_53:
  if ( ppvData )
    SafeArrayUnaccessData(v6);
  if ( v6 )
    SafeArrayDestroy(v6);
  if ( v12 )
    SysFreeString(v12);
  if ( v4 )
    WdcFree(v4, v10, v11);
  if ( v8 )
    WdcFree(v8, v10, v11);
  if ( v54 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  return v9;
}

```

## disassembly

```asm
0x180026f44  mov     [rsp-38h+arg_0], rbx
0x180026f49  push    rbp
0x180026f4a  push    rsi
0x180026f4b  push    rdi
0x180026f4c  push    r12
0x180026f4e  push    r13
0x180026f50  push    r14
0x180026f52  push    r15
0x180026f54  mov     rbp, rsp
0x180026f57  sub     rsp, 60h
0x180026f5b  xor     eax, eax
0x180026f5d  mov     r14, rcx
0x180026f60  mov     ecx, 800h; dwBytes
0x180026f65  mov     [rbp+var_28], rax
0x180026f69  mov     r15d, eax
0x180026f6c  mov     [rbp+arg_10], eax
0x180026f6f  mov     [rbp+arg_18], eax
0x180026f72  mov     rbx, rdx
0x180026f75  mov     [rbp+var_30], rax
0x180026f79  xor     r13d, r13d
0x180026f7c  mov     qword ptr [rbp+rgsabound.cElements], rax
0x180026f80  mov     [rbp+ppvData], rax
0x180026f84  mov     [rbp+var_20], rax
0x180026f88  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180026f8d  mov     r12, rax
0x180026f90  test    rax, rax
0x180026f93  jnz     short loc_180026FC5
0x180026f95  mov     edi, 8007000Eh
0x180026f9a  mov     ebx, edi
0x180026f9c  mov     [rsp+60h+var_40], edi
0x180026fa0  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180026fa7  xor     r8d, r8d; int
0x180026faa  lea     rdx, aWdclegacyreade_2; "WdcLegacyReader::ParseAlertProperties"
0x180026fb1  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x180026fb8  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180026fbd  mov     rsi, r13
0x180026fc0  jmp     loc_18002742C
0x180026fc5  xor     eax, eax
0x180026fc7  lea     r8, [rbp+var_20]
0x180026fcb  mov     [r12], ax
0x180026fd0  lea     rdx, IID_IAlertDataCollector
0x180026fd7  mov     rax, [rbx]
0x180026fda  mov     rcx, rbx
0x180026fdd  mov     rax, [rax]
0x180026fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fe5  mov     ebx, eax
0x180026fe7  test    eax, eax
0x180026fe9  jns     short loc_180026FF1
0x180026feb  mov     [rsp+60h+var_40], eax
0x180026fef  jmp     short loc_180026FA0
0x180026ff1  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x180026ff5  mov     rcx, r14; this
0x180026ff8  lea     rdx, aUpdateinterval; "UpdateInterval"
0x180026fff  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x180027004  test    eax, eax
0x180027006  js      short loc_180027047
0x180027008  mov     rdi, [rbp+var_28]
0x18002700c  lea     rdx, [rbp+arg_10]; int *
0x180027010  mov     rcx, [rdi+18h]; unsigned __int16 *
0x180027014  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x180027019  mov     ebx, eax
0x18002701b  test    eax, eax
0x18002701d  js      short loc_180026FEB
0x18002701f  mov     edx, [rbp+arg_10]
0x180027022  test    edx, edx
0x180027024  jle     short loc_18002703F
0x180027026  mov     rcx, [rbp+var_20]
0x18002702a  mov     rax, [rcx]
0x18002702d  mov     rax, [rax+128h]
0x180027034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027039  mov     ebx, eax
0x18002703b  test    eax, eax
0x18002703d  js      short loc_180026FEB
0x18002703f  mov     rdx, rdi; struct _WDC_LEGACY_PROPERTY *
0x180027042  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027047  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x18002704b  mov     rcx, r14; this
0x18002704e  lea     rdx, aPerflogname; "PerfLogName"
0x180027055  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18002705a  test    eax, eax
0x18002705c  js      loc_18002711C
0x180027062  mov     rdi, [rbp+var_28]
0x180027066  mov     rbx, [rdi+18h]
0x18002706a  mov     rcx, rbx; psz
0x18002706d  call    cs:__imp_SysAllocString
0x180027073  mov     [rbp+var_30], rax
0x180027077  mov     rsi, rax
0x18002707a  test    rbx, rbx
0x18002707d  jz      short loc_1800270D2
0x18002707f  test    rax, rax
0x180027082  jnz     short loc_1800270D2
0x180027084  mov     edi, 8007000Eh
0x180027089  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027090  xor     r8d, r8d; int
0x180027093  mov     [rsp+60h+var_40], edi
0x180027097  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18002709e  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x1800270a5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800270aa  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800270b1  mov     [rsp+60h+var_40], edi
0x1800270b5  xor     r8d, r8d; int
0x1800270b8  lea     rdx, aWdclegacyreade_2; "WdcLegacyReader::ParseAlertProperties"
0x1800270bf  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x1800270c6  mov     ebx, edi
0x1800270c8  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800270cd  jmp     loc_18002742C
0x1800270d2  mov     rcx, [rbp+var_20]
0x1800270d6  mov     rdx, rsi
0x1800270d9  mov     rax, [rcx]
0x1800270dc  mov     rax, [rax+178h]
0x1800270e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270e8  mov     ebx, eax
0x1800270ea  test    eax, eax
0x1800270ec  jns     short loc_180027114
0x1800270ee  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800270f5  mov     [rsp+60h+var_40], eax
0x1800270f9  xor     r8d, r8d; int
0x1800270fc  lea     rdx, aWdclegacyreade_2; "WdcLegacyReader::ParseAlertProperties"
0x180027103  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x18002710a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002710f  jmp     loc_18002742C
0x180027114  mov     rdx, rdi; struct _WDC_LEGACY_PROPERTY *
0x180027117  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x18002711c  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x180027120  mov     rcx, r14; this
0x180027123  lea     rdx, aActionflags; "ActionFlags"
0x18002712a  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18002712f  test    eax, eax
0x180027131  js      short loc_18002719A
0x180027133  mov     rdi, [rbp+var_28]
0x180027137  lea     rdx, [rbp+arg_10]; int *
0x18002713b  mov     rcx, [rdi+18h]; unsigned __int16 *
0x18002713f  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x180027144  mov     ebx, eax
0x180027146  test    eax, eax
0x180027148  jns     short loc_180027170
0x18002714a  mov     [rsp+60h+var_40], eax
0x18002714e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027155  xor     r8d, r8d; int
0x180027158  lea     rdx, aWdclegacyreade_2; "WdcLegacyReader::ParseAlertProperties"
0x18002715f  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x180027166  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002716b  jmp     loc_180027428
0x180027170  test    byte ptr [rbp+arg_10], 1
0x180027174  jz      short loc_180027192
0x180027176  mov     rcx, [rbp+var_20]
0x18002717a  or      edx, 0FFFFFFFFh
0x18002717d  mov     rax, [rcx]
0x180027180  mov     rax, [rax+118h]
0x180027187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002718c  mov     ebx, eax
0x18002718e  test    eax, eax
0x180027190  js      short loc_18002714A
0x180027192  mov     rdx, rdi; struct _WDC_LEGACY_PROPERTY *
0x180027195  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x18002719a  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x18002719e  mov     rcx, r14; this
0x1800271a1  lea     rdx, aCountercount; "CounterCount"
0x1800271a8  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x1800271ad  test    eax, eax
0x1800271af  js      loc_180027426
0x1800271b5  mov     rdi, [rbp+var_28]
0x1800271b9  lea     rdx, [rbp+arg_18]; int *
0x1800271bd  mov     rcx, [rdi+18h]; unsigned __int16 *
0x1800271c1  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x1800271c6  mov     ebx, eax
0x1800271c8  test    eax, eax
0x1800271ca  js      loc_18002714A
0x1800271d0  mov     rdx, rdi; struct _WDC_LEGACY_PROPERTY *
0x1800271d3  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x1800271d8  mov     esi, [rbp+arg_18]
0x1800271db  mov     ecx, 800h; dwBytes
0x1800271e0  mov     [rbp+rgsabound.lLbound], r13d
0x1800271e4  mov     [rbp+rgsabound.cElements], esi
0x1800271e7  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800271ec  mov     r15, rax
0x1800271ef  test    rax, rax
0x1800271f2  jnz     short loc_180027204
0x1800271f4  mov     edi, 8007000Eh
0x1800271f9  mov     ebx, edi
0x1800271fb  mov     [rsp+60h+var_40], edi
0x1800271ff  jmp     loc_18002714E
0x180027204  xor     eax, eax
0x180027206  lea     r8, [rbp+rgsabound]; rgsabound
0x18002720a  mov     [r15], ax
0x18002720e  lea     edi, [rax+1]
0x180027211  mov     edx, edi; cDims
0x180027213  lea     ecx, [rax+8]; vt
0x180027216  call    cs:__imp_SafeArrayCreate
0x18002721c  mov     r13, rax
0x18002721f  test    rax, rax
0x180027222  jz      short loc_1800271F4
0x180027224  lea     rdx, [rbp+ppvData]; ppvData
0x180027228  mov     rcx, rax; psa
0x18002722b  call    cs:__imp_SafeArrayAccessData
0x180027231  mov     ebx, eax
0x180027233  test    eax, eax
0x180027235  js      loc_18002714A
0x18002723b  cmp     edi, esi
0x18002723d  jg      loc_1800273F4
0x180027243  mov     r9d, edi
0x180027246  lea     r8, aCounter05dPath; "Counter%05d.Path"
0x18002724d  mov     edx, 400h; unsigned __int64
0x180027252  mov     rcx, r12; unsigned __int16 *
0x180027255  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002725a  mov     ebx, eax
0x18002725c  test    eax, eax
0x18002725e  js      loc_18002714A
0x180027264  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x180027268  mov     rdx, r12; unsigned __int16 *
0x18002726b  mov     rcx, r14; this
0x18002726e  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x180027273  mov     ebx, eax
0x180027275  test    eax, eax
0x180027277  js      loc_18002714A
0x18002727d  mov     r11, [rbp+var_28]
0x180027281  mov     esi, 400h
0x180027286  mov     edx, esi; unsigned __int64
0x180027288  mov     rcx, r15; unsigned __int16 *
0x18002728b  mov     r8, [r11+18h]; unsigned __int16 *
0x18002728f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027294  mov     ebx, eax
0x180027296  test    eax, eax
0x180027298  js      loc_18002714A
0x18002729e  mov     rdx, r11; struct _WDC_LEGACY_PROPERTY *
0x1800272a1  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x1800272a6  mov     r9d, edi
0x1800272a9  lea     r8, aCounter05dAler; "Counter%05d.AlertOverUnder"
0x1800272b0  mov     edx, esi; unsigned __int64
0x1800272b2  mov     rcx, r12; unsigned __int16 *
0x1800272b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800272ba  mov     ebx, eax
0x1800272bc  test    eax, eax
0x1800272be  js      loc_18002714A
0x1800272c4  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x1800272c8  mov     rdx, r12; unsigned __int16 *
0x1800272cb  mov     rcx, r14; this
0x1800272ce  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x1800272d3  mov     ebx, eax
0x1800272d5  test    eax, eax
0x1800272d7  js      loc_18002714A
0x1800272dd  mov     rsi, [rbp+var_28]
0x1800272e1  lea     rdx, [rbp+arg_10]; int *
0x1800272e5  mov     rcx, [rsi+18h]; unsigned __int16 *
0x1800272e9  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x1800272ee  mov     ebx, eax
0x1800272f0  test    eax, eax
0x1800272f2  js      loc_18002714A
0x1800272f8  mov     rdx, rsi; struct _WDC_LEGACY_PROPERTY *
0x1800272fb  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027300  cmp     [rbp+arg_10], 0
0x180027304  lea     r8, Delimiter; "<"
0x18002730b  mov     esi, 400h
0x180027310  mov     rcx, r15; unsigned __int16 *
0x180027313  mov     edx, esi; unsigned __int64
0x180027315  jz      short loc_18002731E
0x180027317  lea     r8, asc_1800941D0; ">"
0x18002731e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027323  mov     ebx, eax
0x180027325  test    eax, eax
0x180027327  js      loc_18002714A
0x18002732d  mov     r9d, edi
0x180027330  lea     r8, aCounter05dAler_0; "Counter%05d.AlertThreshold"
0x180027337  mov     rdx, rsi; unsigned __int64
0x18002733a  mov     rcx, r12; unsigned __int16 *
0x18002733d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027342  mov     ebx, eax
0x180027344  test    eax, eax
0x180027346  js      loc_18002714A
0x18002734c  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x180027350  mov     rdx, r12; unsigned __int16 *
0x180027353  mov     rcx, r14; this
0x180027356  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18002735b  mov     ebx, eax
0x18002735d  test    eax, eax
0x18002735f  js      loc_18002714A
0x180027365  mov     rsi, [rbp+var_28]
0x180027369  mov     edx, 400h; unsigned __int64
0x18002736e  mov     rcx, r15; unsigned __int16 *
0x180027371  mov     r8, [rsi+18h]; unsigned __int16 *
0x180027375  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002737a  mov     ebx, eax
0x18002737c  test    eax, eax
0x18002737e  js      loc_18002714A
0x180027384  mov     rdx, rsi; struct _WDC_LEGACY_PROPERTY *
0x180027387  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x18002738c  mov     rsi, [rbp+ppvData]
0x180027390  movsxd  rbx, edi
0x180027393  mov     rcx, [rsi+rbx*8-8]; bstrString
0x180027398  test    rcx, rcx
0x18002739b  jz      short loc_1800273AC
0x18002739d  call    cs:__imp_SysFreeString
0x1800273a3  mov     qword ptr [rsi+rbx*8-8], 0
0x1800273ac  mov     rcx, r15; psz
0x1800273af  call    cs:__imp_SysAllocString
0x1800273b5  test    rax, rax
0x1800273b8  jz      short loc_1800273C9
0x1800273ba  mov     [rsi+rbx*8-8], rax
0x1800273bf  mov     esi, [rbp+arg_18]
0x1800273c2  inc     edi
  ... truncated ...
```
