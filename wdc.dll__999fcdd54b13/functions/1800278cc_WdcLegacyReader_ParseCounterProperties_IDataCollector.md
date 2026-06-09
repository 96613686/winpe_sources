# WdcLegacyReader::ParseCounterProperties(IDataCollector *)

- ea: `0x1800278cc`
- end: `0x180027d1c`
- name: `?ParseCounterProperties@WdcLegacyReader@@AEAAJPEAUIDataCollector@@@Z`
- size: `1104`
- prototype: `__int64 __fastcall(WdcLegacyReader *__hidden this, struct IDataCollector *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18006b5bc`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x1800278cc`
- `0x180027d24`
- `0x180068008`
- `0x18006b560`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800279f3`
- `OLEAUT32!__imp_SysAllocString` at `0x180027b77`
- `OLEAUT32!__imp_SysAllocString` at `0x1800279f3`
- `OLEAUT32!__imp_SysAllocString` at `0x180027b77`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b65`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ce7`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b65`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ce7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180027ad9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180027ad9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027ccc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027ccc`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180027afb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180027afb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027bf9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027cbe`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027bf9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180027cbe`

## string_xrefs

- `0x180027982`: `UpdateInterval`
- `0x180027b15`: `Counter%05d.Path`
- `0x180027937`: `WdcLegacyReader::ParseCounterProperties`
- `0x180027aa2`: `WdcLegacyReader::ParseCounterProperties`
- `0x180027bd8`: `WdcLegacyReader::ParseCounterProperties`

## pseudocode

```c
__int64 __fastcall WdcLegacyReader::ParseCounterProperties(WdcLegacyReader *this, struct IDataCollector *a2, int a3)
{
  OLECHAR *v3; // rsi
  SAFEARRAY *v6; // r15
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r13
  unsigned int v9; // ebx
  const char *v10; // rdx
  int v11; // r8d
  int v12; // eax
  struct _WDC_LEGACY_PROPERTY ***v13; // rdi
  WdcLegacyReader *v14; // rcx
  int v15; // r8d
  struct _WDC_LEGACY_PROPERTY ***v16; // rdi
  const OLECHAR *v17; // rbx
  BSTR v18; // rax
  WdcLegacyReader *v19; // rcx
  int v20; // r8d
  unsigned int v21; // edi
  struct _WDC_LEGACY_PROPERTY ***v22; // rsi
  HRESULT Property; // eax
  WdcLegacyReader *v24; // rcx
  int v25; // r8d
  int v26; // r12d
  SAFEARRAY *v27; // rax
  int i; // esi
  _QWORD *v29; // r12
  const OLECHAR *v30; // r13
  OLECHAR *v31; // rcx
  BSTR v32; // rax
  WdcLegacyReader *v33; // rcx
  int v34; // r8d
  struct _WDC_LEGACY_PROPERTY ***v35; // rsi
  WdcLegacyReader *v36; // rcx
  int v37; // r8d
  __int64 v39; // [rsp+20h] [rbp-40h]
  int v40; // [rsp+20h] [rbp-40h]
  __int64 v41; // [rsp+20h] [rbp-40h]
  OLECHAR *v42; // [rsp+30h] [rbp-30h]
  struct _WDC_LEGACY_PROPERTY *v43; // [rsp+38h] [rbp-28h] BYREF
  __int64 v44; // [rsp+40h] [rbp-20h] BYREF
  void *ppvData; // [rsp+48h] [rbp-18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v47; // [rsp+58h] [rbp-8h]
  int v48; // [rsp+B0h] [rbp+50h] BYREF
  int v49; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  v43 = 0;
  v42 = 0;
  v48 = 0;
  v49 = 0;
  rgsabound = 0;
  v6 = 0;
  ppvData = 0;
  v44 = 0;
  v7 = (unsigned __int16 *)WdcAlloc(0x800u, (const char *)a2, a3);
  v47 = v7;
  v8 = v7;
  if ( !v7 )
    goto LABEL_2;
  *v7 = 0;
  v12 = ((__int64 (__fastcall *)(struct IDataCollector *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IPerformanceCounterDataCollector,
          &v44);
  v9 = v12;
  if ( v12 < 0 )
    goto LABEL_5;
  if ( (int)WdcLegacyReader::GetProperty(this, L"UpdateInterval", &v43) >= 0 )
  {
    v13 = (struct _WDC_LEGACY_PROPERTY ***)v43;
    v12 = WdcHexToLong(*((const unsigned __int16 **)v43 + 3), &v48);
    v9 = v12;
    if ( v12 < 0 )
      goto LABEL_5;
    if ( v48 > 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 312LL))(v44);
      v9 = v12;
      if ( v12 < 0 )
        goto LABEL_5;
    }
    WdcLegacyReader::FreeProperty(v14, v13, v15);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"SqlDsnName", &v43) >= 0 )
  {
    v16 = (struct _WDC_LEGACY_PROPERTY ***)v43;
    v17 = (const OLECHAR *)*((_QWORD *)v43 + 3);
    v18 = SysAllocString(v17);
    v42 = v18;
    v3 = v18;
    if ( v17 && !v18 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
LABEL_2:
      v9 = -2147024882;
      LODWORD(v39) = -2147024882;
LABEL_3:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
        "WdcLegacyReader::ParseCounterProperties",
        0,
        L"FAILURE: 0x%08x",
        v39);
      goto LABEL_49;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v44 + 264LL))(v44, v18);
    v9 = v12;
    if ( v12 < 0 )
    {
LABEL_5:
      LODWORD(v39) = v12;
      goto LABEL_3;
    }
    WdcLegacyReader::FreeProperty(v19, v16, v20);
  }
  v21 = 1;
  if ( (int)WdcLegacyReader::GetProperty(this, L"CounterCount", &v43) < 0 )
    goto LABEL_35;
  v22 = (struct _WDC_LEGACY_PROPERTY ***)v43;
  Property = WdcHexToLong(*((const unsigned __int16 **)v43 + 3), &v49);
  v9 = Property;
  if ( Property >= 0 )
  {
    WdcLegacyReader::FreeProperty(v24, v22, v25);
    v26 = v49;
    rgsabound.lLbound = 0;
    rgsabound.cElements = v49;
    v27 = SafeArrayCreate(8u, 1u, &rgsabound);
    v6 = v27;
    if ( !v27 )
    {
      v9 = -2147024882;
      v40 = -2147024882;
      goto LABEL_20;
    }
    Property = SafeArrayAccessData(v27, &ppvData);
    v9 = Property;
    if ( Property >= 0 )
    {
      for ( i = 1; i <= v26; ++i )
      {
        Property = StringCchPrintfW(v8, 0x400u, L"Counter%05d.Path", (unsigned int)i);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_19;
        Property = WdcLegacyReader::GetProperty(this, v8, &v43);
        v9 = Property;
        if ( Property < 0 )
          goto LABEL_19;
        v29 = ppvData;
        v30 = (const OLECHAR *)*((_QWORD *)v43 + 3);
        v31 = (OLECHAR *)*((_QWORD *)ppvData + i - 1);
        if ( v31 )
        {
          SysFreeString(v31);
          v29[i - 1] = 0;
        }
        v32 = SysAllocString(v30);
        if ( v30 && !v32 )
        {
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
            "WdcAssignString",
            0,
            L"FAILURE: 0x%08x",
            -2147024882);
          LODWORD(v41) = -2147024882;
          v9 = -2147024882;
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
            "WdcLegacyReader::ParseCounterProperties",
            0,
            L"FAILURE: 0x%08x",
            v41);
          v8 = v47;
          goto LABEL_48;
        }
        v29[i - 1] = v32;
        WdcLegacyReader::FreeProperty(v33, (struct _WDC_LEGACY_PROPERTY ***)v43, v34);
        v26 = v49;
        v8 = v47;
      }
      SafeArrayUnaccessData(v6);
      ppvData = 0;
      Property = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v44 + 280LL))(v44, v6);
      v9 = Property;
      if ( Property >= 0 )
      {
LABEL_35:
        if ( (int)WdcLegacyReader::GetProperty(this, L"LogFileType", &v43) < 0 )
        {
          v9 = 0;
          goto LABEL_48;
        }
        v35 = (struct _WDC_LEGACY_PROPERTY ***)v43;
        Property = WdcHexToLong(*((const unsigned __int16 **)v43 + 3), &v48);
        v9 = Property;
        if ( Property >= 0 )
        {
          if ( v48 )
          {
            if ( v48 != 1 )
            {
              if ( v48 == 2 || v48 == 3 )
              {
                v21 = 3;
              }
              else
              {
                v21 = 3;
                if ( v48 == 6 )
                  v21 = 2;
              }
            }
          }
          else
          {
            v21 = 0;
          }
          Property = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v44 + 296LL))(v44, v21);
          v9 = Property;
          if ( Property >= 0 )
          {
            WdcLegacyReader::FreeProperty(v36, v35, v37);
            goto LABEL_48;
          }
        }
      }
    }
  }
LABEL_19:
  v40 = Property;
LABEL_20:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
    "WdcLegacyReader::ParseCounterProperties",
    0,
    L"FAILURE: 0x%08x",
    v40);
LABEL_48:
  v3 = v42;
LABEL_49:
  if ( ppvData )
    SafeArrayUnaccessData(v6);
  if ( v6 )
    SafeArrayDestroy(v6);
  if ( v8 )
    WdcFree(v8, v10, v11);
  if ( v3 )
    SysFreeString(v3);
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  return v9;
}

```

## disassembly

```asm
0x1800278cc  mov     [rsp-38h+arg_0], rbx
0x1800278d1  push    rbp
0x1800278d2  push    rsi
0x1800278d3  push    rdi
0x1800278d4  push    r12
0x1800278d6  push    r13
0x1800278d8  push    r14
0x1800278da  push    r15
0x1800278dc  mov     rbp, rsp
0x1800278df  sub     rsp, 60h
0x1800278e3  xor     esi, esi
0x1800278e5  mov     [rbp+var_28], 0
0x1800278ed  mov     r14, rcx
0x1800278f0  mov     [rbp+var_30], rsi
0x1800278f4  mov     ecx, 800h; dwBytes
0x1800278f9  mov     [rbp+arg_10], esi
0x1800278fc  mov     [rbp+arg_18], esi
0x1800278ff  mov     rbx, rdx
0x180027902  mov     qword ptr [rbp+rgsabound.cElements], rsi
0x180027906  xor     r15d, r15d
0x180027909  mov     [rbp+ppvData], rsi
0x18002790d  mov     [rbp+var_20], rsi
0x180027911  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180027916  mov     [rbp+var_8], rax
0x18002791a  mov     r13, rax
0x18002791d  test    rax, rax
0x180027920  jnz     short loc_18002794F
0x180027922  mov     edi, 8007000Eh
0x180027927  mov     ebx, edi
0x180027929  mov     [rsp+60h+var_40], edi
0x18002792d  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027934  xor     r8d, r8d; int
0x180027937  lea     rdx, aWdclegacyreade_4; "WdcLegacyReader::ParseCounterProperties"
0x18002793e  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x180027945  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002794a  jmp     loc_180027CB4
0x18002794f  xor     eax, eax
0x180027951  lea     r8, [rbp+var_20]
0x180027955  mov     [r13+0], ax
0x18002795a  lea     rdx, IID_IPerformanceCounterDataCollector
0x180027961  mov     rax, [rbx]
0x180027964  mov     rcx, rbx
0x180027967  mov     rax, [rax]
0x18002796a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002796f  mov     ebx, eax
0x180027971  test    eax, eax
0x180027973  jns     short loc_18002797B
0x180027975  mov     [rsp+60h+var_40], eax
0x180027979  jmp     short loc_18002792D
0x18002797b  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x18002797f  mov     rcx, r14; this
0x180027982  lea     rdx, aUpdateinterval; "UpdateInterval"
0x180027989  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18002798e  test    eax, eax
0x180027990  js      short loc_1800279D1
0x180027992  mov     rdi, [rbp+var_28]
0x180027996  lea     rdx, [rbp+arg_10]; int *
0x18002799a  mov     rcx, [rdi+18h]; unsigned __int16 *
0x18002799e  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x1800279a3  mov     ebx, eax
0x1800279a5  test    eax, eax
0x1800279a7  js      short loc_180027975
0x1800279a9  mov     edx, [rbp+arg_10]
0x1800279ac  test    edx, edx
0x1800279ae  jle     short loc_1800279C9
0x1800279b0  mov     rcx, [rbp+var_20]
0x1800279b4  mov     rax, [rcx]
0x1800279b7  mov     rax, [rax+138h]
0x1800279be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279c3  mov     ebx, eax
0x1800279c5  test    eax, eax
0x1800279c7  js      short loc_180027975
0x1800279c9  mov     rdx, rdi; struct _WDC_LEGACY_PROPERTY *
0x1800279cc  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x1800279d1  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x1800279d5  mov     rcx, r14; this
0x1800279d8  lea     rdx, aSqldsnname; "SqlDsnName"
0x1800279df  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x1800279e4  test    eax, eax
0x1800279e6  js      short loc_180027A5D
0x1800279e8  mov     rdi, [rbp+var_28]
0x1800279ec  mov     rbx, [rdi+18h]
0x1800279f0  mov     rcx, rbx; psz
0x1800279f3  call    cs:__imp_SysAllocString
0x1800279f9  mov     [rbp+var_30], rax
0x1800279fd  mov     rsi, rax
0x180027a00  test    rbx, rbx
0x180027a03  jz      short loc_180027A35
0x180027a05  test    rax, rax
0x180027a08  jnz     short loc_180027A35
0x180027a0a  mov     edi, 8007000Eh
0x180027a0f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027a16  xor     r8d, r8d; int
0x180027a19  mov     [rsp+60h+var_40], edi
0x180027a1d  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180027a24  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180027a2b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180027a30  jmp     loc_180027927
0x180027a35  mov     rcx, [rbp+var_20]
0x180027a39  mov     rdx, rsi
0x180027a3c  mov     rax, [rcx]
0x180027a3f  mov     rax, [rax+108h]
0x180027a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a4b  mov     ebx, eax
0x180027a4d  test    eax, eax
0x180027a4f  js      loc_180027975
0x180027a55  mov     rdx, rdi; struct _WDC_LEGACY_PROPERTY *
0x180027a58  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027a5d  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x180027a61  mov     rcx, r14; this
0x180027a64  lea     rdx, aCountercount; "CounterCount"
0x180027a6b  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x180027a70  mov     edi, 1
0x180027a75  test    eax, eax
0x180027a77  js      loc_180027C27
0x180027a7d  mov     rsi, [rbp+var_28]
0x180027a81  lea     rdx, [rbp+arg_18]; int *
0x180027a85  mov     rcx, [rsi+18h]; unsigned __int16 *
0x180027a89  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x180027a8e  mov     ebx, eax
0x180027a90  test    eax, eax
0x180027a92  jns     short loc_180027ABA
0x180027a94  mov     [rsp+60h+var_40], eax
0x180027a98  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027a9f  xor     r8d, r8d; int
0x180027aa2  lea     rdx, aWdclegacyreade_4; "WdcLegacyReader::ParseCounterProperties"
0x180027aa9  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x180027ab0  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180027ab5  jmp     loc_180027CB0
0x180027aba  mov     rdx, rsi; struct _WDC_LEGACY_PROPERTY *
0x180027abd  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027ac2  mov     r12d, [rbp+arg_18]
0x180027ac6  lea     r8, [rbp+rgsabound]; rgsabound
0x180027aca  mov     ecx, 8; vt
0x180027acf  mov     [rbp+rgsabound.lLbound], r15d
0x180027ad3  mov     edx, edi; cDims
0x180027ad5  mov     [rbp+rgsabound.cElements], r12d
0x180027ad9  call    cs:__imp_SafeArrayCreate
0x180027adf  mov     r15, rax
0x180027ae2  test    rax, rax
0x180027ae5  jnz     short loc_180027AF4
0x180027ae7  mov     edi, 8007000Eh
0x180027aec  mov     ebx, edi
0x180027aee  mov     [rsp+60h+var_40], edi
0x180027af2  jmp     short loc_180027A98
0x180027af4  lea     rdx, [rbp+ppvData]; ppvData
0x180027af8  mov     rcx, r15; psa
0x180027afb  call    cs:__imp_SafeArrayAccessData
0x180027b01  mov     ebx, eax
0x180027b03  test    eax, eax
0x180027b05  js      short loc_180027A94
0x180027b07  mov     esi, edi
0x180027b09  cmp     esi, r12d
0x180027b0c  jg      loc_180027BF6
0x180027b12  mov     r9d, esi
0x180027b15  lea     r8, aCounter05dPath; "Counter%05d.Path"
0x180027b1c  mov     edx, 400h; unsigned __int64
0x180027b21  mov     rcx, r13; unsigned __int16 *
0x180027b24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027b29  mov     ebx, eax
0x180027b2b  test    eax, eax
0x180027b2d  js      loc_180027A94
0x180027b33  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x180027b37  mov     rdx, r13; unsigned __int16 *
0x180027b3a  mov     rcx, r14; this
0x180027b3d  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x180027b42  mov     ebx, eax
0x180027b44  test    eax, eax
0x180027b46  js      loc_180027A94
0x180027b4c  mov     r12, [rbp+ppvData]
0x180027b50  mov     r13, [rbp+var_28]
0x180027b54  movsxd  rbx, esi
0x180027b57  mov     r13, [r13+18h]
0x180027b5b  mov     rcx, [r12+rbx*8-8]; bstrString
0x180027b60  test    rcx, rcx
0x180027b63  jz      short loc_180027B74
0x180027b65  call    cs:__imp_SysFreeString
0x180027b6b  mov     qword ptr [r12+rbx*8-8], 0
0x180027b74  mov     rcx, r13; psz
0x180027b77  call    cs:__imp_SysAllocString
0x180027b7d  test    r13, r13
0x180027b80  jz      short loc_180027B87
0x180027b82  test    rax, rax
0x180027b85  jz      short loc_180027BA4
0x180027b87  mov     [r12+rbx*8-8], rax
0x180027b8c  mov     rdx, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY *
0x180027b90  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027b95  mov     r12d, [rbp+arg_18]
0x180027b99  add     esi, edi
0x180027b9b  mov     r13, [rbp+var_8]
0x180027b9f  jmp     loc_180027B09
0x180027ba4  mov     edi, 8007000Eh
0x180027ba9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027bb0  xor     r8d, r8d; int
0x180027bb3  mov     [rsp+60h+var_40], edi
0x180027bb7  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180027bbe  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180027bc5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180027bca  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027bd1  mov     [rsp+60h+var_40], edi
0x180027bd5  xor     r8d, r8d; int
0x180027bd8  lea     rdx, aWdclegacyreade_4; "WdcLegacyReader::ParseCounterProperties"
0x180027bdf  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x180027be6  mov     ebx, edi
0x180027be8  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180027bed  mov     r13, [rbp+var_8]
0x180027bf1  jmp     loc_180027CB0
0x180027bf6  mov     rcx, r15; psa
0x180027bf9  call    cs:__imp_SafeArrayUnaccessData
0x180027bff  mov     rcx, [rbp+var_20]
0x180027c03  mov     rdx, r15
0x180027c06  mov     [rbp+ppvData], 0
0x180027c0e  mov     rax, [rcx]
0x180027c11  mov     rax, [rax+118h]
0x180027c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c1d  mov     ebx, eax
0x180027c1f  test    eax, eax
0x180027c21  js      loc_180027A94
0x180027c27  lea     r8, [rbp+var_28]; struct _WDC_LEGACY_PROPERTY **
0x180027c2b  mov     rcx, r14; this
0x180027c2e  lea     rdx, aLogfiletype; "LogFileType"
0x180027c35  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x180027c3a  test    eax, eax
0x180027c3c  js      short loc_180027CAE
0x180027c3e  mov     rsi, [rbp+var_28]
0x180027c42  lea     rdx, [rbp+arg_10]; int *
0x180027c46  mov     rcx, [rsi+18h]; unsigned __int16 *
0x180027c4a  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x180027c4f  mov     ebx, eax
0x180027c51  test    eax, eax
0x180027c53  js      loc_180027A94
0x180027c59  mov     ecx, [rbp+arg_10]
0x180027c5c  test    ecx, ecx
0x180027c5e  jz      short loc_180027C83
0x180027c60  sub     ecx, edi
0x180027c62  jz      short loc_180027C85
0x180027c64  sub     ecx, edi
0x180027c66  jz      short loc_180027C7C
0x180027c68  sub     ecx, edi
0x180027c6a  jz      short loc_180027C7C
0x180027c6c  mov     edi, 3
0x180027c71  cmp     ecx, edi
0x180027c73  jnz     short loc_180027C85
0x180027c75  mov     edi, 2
0x180027c7a  jmp     short loc_180027C85
0x180027c7c  mov     edi, 3
0x180027c81  jmp     short loc_180027C85
0x180027c83  xor     edi, edi
0x180027c85  mov     rcx, [rbp+var_20]
0x180027c89  mov     edx, edi
0x180027c8b  mov     rax, [rcx]
0x180027c8e  mov     rax, [rax+128h]
0x180027c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c9a  mov     ebx, eax
0x180027c9c  test    eax, eax
0x180027c9e  js      loc_180027A94
0x180027ca4  mov     rdx, rsi; struct _WDC_LEGACY_PROPERTY *
0x180027ca7  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x180027cac  jmp     short loc_180027CB0
0x180027cae  xor     ebx, ebx
0x180027cb0  mov     rsi, [rbp+var_30]
0x180027cb4  cmp     [rbp+ppvData], 0
0x180027cb9  jz      short loc_180027CC4
0x180027cbb  mov     rcx, r15; psa
0x180027cbe  call    cs:__imp_SafeArrayUnaccessData
0x180027cc4  test    r15, r15
0x180027cc7  jz      short loc_180027CD2
0x180027cc9  mov     rcx, r15; psa
0x180027ccc  call    cs:__imp_SafeArrayDestroy
0x180027cd2  test    r13, r13
0x180027cd5  jz      short loc_180027CDF
0x180027cd7  mov     rcx, r13; void *
0x180027cda  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180027cdf  test    rsi, rsi
0x180027ce2  jz      short loc_180027CED
0x180027ce4  mov     rcx, rsi; bstrString
0x180027ce7  call    cs:__imp_SysFreeString
0x180027ced  mov     rcx, [rbp+var_20]
0x180027cf1  test    rcx, rcx
0x180027cf4  jz      short loc_180027D02
0x180027cf6  mov     rax, [rcx]
0x180027cf9  mov     rax, [rax+10h]
0x180027cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d02  mov     eax, ebx
0x180027d04  mov     rbx, [rsp+60h+arg_0]
0x180027d0c  add     rsp, 60h
0x180027d10  pop     r15
0x180027d12  pop     r14
0x180027d14  pop     r13
0x180027d16  pop     r12
0x180027d18  pop     rdi
0x180027d19  pop     rsi
0x180027d1a  pop     rbp
0x180027d1b  retn
```
