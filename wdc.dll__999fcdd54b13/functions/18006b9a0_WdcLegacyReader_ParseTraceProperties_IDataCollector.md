# WdcLegacyReader::ParseTraceProperties(IDataCollector *)

- ea: `0x18006b9a0`
- end: `0x18006bfb0`
- name: `?ParseTraceProperties@WdcLegacyReader@@AEAAJPEAUIDataCollector@@@Z`
- size: `1552`
- prototype: `__int64 __fastcall(WdcLegacyReader *__hidden this, struct IDataCollector *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18006b5bc`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x180027d24`
- `0x180068008`
- `0x18006b560`
- `0x18006b9a0`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006bcda`
- `OLEAUT32!__imp_SysAllocString` at `0x18006bcda`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bcd1`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bcd1`

## string_xrefs

- `0x18006ba24`: `WdcLegacyReader::ParseTraceProperties`
- `0x18006bd78`: `WdcLegacyReader::ParseTraceProperties`

## pseudocode

```c
__int64 __fastcall WdcLegacyReader::ParseTraceProperties(WdcLegacyReader *this, struct IDataCollector *a2, int a3)
{
  __int64 v3; // r15
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r13
  unsigned int v9; // ebx
  const char *v10; // rdx
  int v11; // r8d
  int Property; // eax
  struct _WDC_LEGACY_PROPERTY ***v13; // r14
  WdcLegacyReader *v14; // rcx
  int v15; // r8d
  struct _WDC_LEGACY_PROPERTY ***v16; // r14
  WdcLegacyReader *v17; // rcx
  int v18; // r8d
  struct _WDC_LEGACY_PROPERTY ***v19; // r14
  WdcLegacyReader *v20; // rcx
  int v21; // r8d
  struct _WDC_LEGACY_PROPERTY ***v22; // r14
  WdcLegacyReader *v23; // rcx
  int v24; // r8d
  int v25; // r12d
  struct _WDC_LEGACY_PROPERTY ***v26; // r15
  WdcLegacyReader *v27; // rcx
  int v28; // r8d
  OLECHAR *v29; // r14
  int i; // r15d
  struct _WDC_LEGACY_PROPERTY ***v31; // r13
  const OLECHAR *v32; // rbx
  BSTR v33; // rax
  int v34; // eax
  WdcLegacyReader *v35; // rcx
  int v36; // r8d
  char v37; // si
  __int64 v38; // rax
  __int64 v40; // [rsp+20h] [rbp-49h]
  int v41; // [rsp+20h] [rbp-49h]
  __int64 *v42; // [rsp+30h] [rbp-39h] BYREF
  __int64 v43; // [rsp+38h] [rbp-31h] BYREF
  __int64 v44; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 *v45; // [rsp+48h] [rbp-21h]
  __int64 v46; // [rsp+50h] [rbp-19h] BYREF
  __int128 v47; // [rsp+60h] [rbp-9h] BYREF
  __int64 v48; // [rsp+70h] [rbp+7h]
  GUID v49; // [rsp+80h] [rbp+17h] BYREF
  int v50; // [rsp+E0h] [rbp+77h] BYREF
  struct _WDC_LEGACY_PROPERTY *v51; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = 0;
  v51 = 0;
  v50 = 0;
  *(_QWORD *)&v49.Data1 = 0;
  v47 = 0;
  v46 = 0;
  LOWORD(v47) = 20;
  v42 = 0;
  v44 = 0;
  v6 = 0;
  v43 = 0;
  v7 = (unsigned __int16 *)WdcAlloc(0x800u, (const char *)a2, a3);
  v45 = v7;
  v8 = v7;
  if ( !v7 )
  {
    v9 = -2147024882;
    v41 = -2147024882;
LABEL_3:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
      "WdcLegacyReader::ParseTraceProperties",
      0,
      L"FAILURE: 0x%08x",
      v41);
    goto LABEL_72;
  }
  *v7 = 0;
  Property = ((__int64 (__fastcall *)(struct IDataCollector *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
               a2,
               &IID_ITraceDataCollector,
               &v43);
  v9 = Property;
  if ( Property < 0 )
    goto LABEL_5;
  if ( (int)WdcLegacyReader::GetProperty(this, L"TraceBufferFlushInterval", &v51) >= 0 )
  {
    v13 = (struct _WDC_LEGACY_PROPERTY ***)v51;
    Property = WdcHexToLong(*((const unsigned __int16 **)v51 + 3), &v50);
    v9 = Property;
    if ( Property < 0 )
      goto LABEL_5;
    if ( v50 > 0 )
    {
      Property = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 360LL))(v43);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_5;
    }
    WdcLegacyReader::FreeProperty(v14, v13, v15);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"TraceBufferMaxCount", &v51) >= 0 )
  {
    v16 = (struct _WDC_LEGACY_PROPERTY ***)v51;
    Property = WdcHexToLong(*((const unsigned __int16 **)v51 + 3), &v50);
    v9 = Property;
    if ( Property < 0 )
      goto LABEL_5;
    if ( v50 > 0 )
    {
      Property = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 416LL))(v43);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_5;
    }
    WdcLegacyReader::FreeProperty(v17, v16, v18);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"TraceBufferMinCount", &v51) >= 0 )
  {
    v19 = (struct _WDC_LEGACY_PROPERTY ***)v51;
    Property = WdcHexToLong(*((const unsigned __int16 **)v51 + 3), &v50);
    v9 = Property;
    if ( Property < 0 )
      goto LABEL_5;
    if ( v50 > 0 )
    {
      Property = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 432LL))(v43);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_5;
    }
    WdcLegacyReader::FreeProperty(v20, v19, v21);
  }
  if ( (int)WdcLegacyReader::GetProperty(this, L"TraceBufferSize", &v51) >= 0 )
  {
    v22 = (struct _WDC_LEGACY_PROPERTY ***)v51;
    Property = WdcHexToLong(*((const unsigned __int16 **)v51 + 3), &v50);
    v9 = Property;
    if ( Property < 0 )
      goto LABEL_5;
    if ( v50 > 0 )
    {
      Property = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 264LL))(v43);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_5;
    }
    WdcLegacyReader::FreeProperty(v23, v22, v24);
  }
  Property = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 568LL))(v43, &v44);
  v9 = Property;
  if ( Property < 0 )
    goto LABEL_5;
  v25 = 1;
  if ( (int)WdcLegacyReader::GetProperty(this, L"TraceProviderCount", &v51) < 0 )
    goto LABEL_47;
  v26 = (struct _WDC_LEGACY_PROPERTY ***)v51;
  Property = WdcHexToLong(*((const unsigned __int16 **)v51 + 3), &v50);
  v9 = Property;
  if ( Property < 0 )
  {
LABEL_5:
    v41 = Property;
    goto LABEL_3;
  }
  v29 = 0;
  WdcLegacyReader::FreeProperty(v27, v26, v28);
  for ( i = 1; i <= v50; ++i )
  {
    Property = StringCchPrintfW(v8, 0x400u, L"TraceProvider%05d.Guid", (unsigned int)i);
    v9 = Property;
    if ( Property < 0 )
      goto LABEL_5;
    Property = WdcLegacyReader::GetProperty(this, v8, &v51);
    v9 = Property;
    if ( Property < 0 )
      goto LABEL_5;
    if ( v42 )
    {
      (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
      v42 = 0;
    }
    Property = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v44 + 112LL))(v44, &v42);
    v9 = Property;
    if ( Property < 0 )
      goto LABEL_5;
    v31 = (struct _WDC_LEGACY_PROPERTY ***)v51;
    v32 = (const OLECHAR *)*((_QWORD *)v51 + 3);
    if ( v29 )
      SysFreeString(v29);
    v33 = SysAllocString(v32);
    v29 = v33;
    if ( v32 && !v33 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      v9 = -2147024882;
      LODWORD(v40) = -2147024882;
LABEL_44:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
        "WdcLegacyReader::ParseTraceProperties",
        0,
        L"FAILURE: 0x%08x",
        v40);
      v8 = v45;
      goto LABEL_72;
    }
    v34 = (*(__int64 (__fastcall **)(__int64 *, BSTR, _QWORD))(*v42 + 168))(v42, v33, *((_QWORD *)this + 4));
    v9 = v34;
    if ( v34 < 0
      || (v34 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 80LL))(v44, v42), v9 = v34, v34 < 0) )
    {
      LODWORD(v40) = v34;
      goto LABEL_44;
    }
    v25 = 0;
    WdcLegacyReader::FreeProperty(v35, v31, v36);
    v8 = v45;
  }
  v3 = *(_QWORD *)&v49.Data1;
LABEL_47:
  if ( (int)WdcLegacyReader::GetProperty(this, L"TraceFlags", &v51) >= 0 && v25 )
  {
    Property = WdcHexToLong(*((const unsigned __int16 **)v51 + 3), &v50);
    v9 = Property;
    if ( Property < 0 )
      goto LABEL_5;
    v37 = v50;
    if ( v50 )
    {
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
        v42 = 0;
      }
      Property = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v44 + 112LL))(v44, &v42);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_5;
      v38 = *v42;
      v49 = SystemTraceControlGuid;
      Property = (*(__int64 (__fastcall **)(__int64 *, GUID *))(v38 + 80))(v42, &v49);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_5;
      Property = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v42 + 96))(v42, &v46);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_5;
      if ( (v37 & 0x10) != 0 )
        v6 = 1;
      *((_QWORD *)&v47 + 1) = v6;
      if ( (v37 & 0x20) != 0 )
      {
        v6 |= 2uLL;
        *((_QWORD *)&v47 + 1) = v6;
      }
      if ( (v37 & 4) != 0 )
      {
        v6 |= 0x3000uLL;
        *((_QWORD *)&v47 + 1) = v6;
      }
      if ( (v37 & 0x40) != 0 )
      {
        v6 |= 0x100uLL;
        *((_QWORD *)&v47 + 1) = v6;
      }
      if ( v37 < 0 )
      {
        v6 |= 0x10000uLL;
        *((_QWORD *)&v47 + 1) = v6;
      }
      if ( (v37 & 8) != 0 )
        *((_QWORD *)&v47 + 1) = v6 | 0x200;
      v48 = v3;
      Property = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v46 + 104LL))(v46, &v47);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_5;
      Property = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 80LL))(v44, v42);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_5;
    }
  }
  else
  {
    v9 = 0;
  }
LABEL_72:
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
    v42 = 0;
  }
  if ( v8 )
    WdcFree(v8, v10, v11);
  return v9;
}

```

## disassembly

```asm
0x18006b9a0  mov     [rsp-8+arg_0], rbx
0x18006b9a5  push    rbp
0x18006b9a6  push    rsi
0x18006b9a7  push    rdi
0x18006b9a8  push    r12
0x18006b9aa  push    r13
0x18006b9ac  push    r14
0x18006b9ae  push    r15
0x18006b9b0  lea     rbp, [rsp-27h]
0x18006b9b5  sub     rsp, 90h
0x18006b9bc  xor     r15d, r15d
0x18006b9bf  mov     [rbp+57h+arg_18], 0
0x18006b9c7  xorps   xmm0, xmm0
0x18006b9ca  mov     [rbp+57h+arg_10], 0
0x18006b9d1  mov     rsi, rcx
0x18006b9d4  mov     qword ptr [rbp+57h+var_40], r15
0x18006b9d8  movups  [rbp+57h+var_60], xmm0
0x18006b9dc  lea     eax, [r15+14h]
0x18006b9e0  mov     [rbp+57h+var_70], r15
0x18006b9e4  mov     ecx, 800h; dwBytes
0x18006b9e9  mov     word ptr [rbp+57h+var_60], ax
0x18006b9ed  mov     rbx, rdx
0x18006b9f0  mov     [rbp+57h+var_90], r15
0x18006b9f4  mov     [rbp+57h+var_80], r15
0x18006b9f8  xor     edi, edi
0x18006b9fa  mov     [rbp+57h+var_88], r15
0x18006b9fe  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18006ba03  mov     [rbp+57h+var_78], rax
0x18006ba07  mov     r13, rax
0x18006ba0a  test    rax, rax
0x18006ba0d  jnz     short loc_18006BA3C
0x18006ba0f  mov     edi, 8007000Eh
0x18006ba14  mov     ebx, edi
0x18006ba16  mov     [rsp+0C0h+var_A0], edi
0x18006ba1a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18006ba21  xor     r8d, r8d; int
0x18006ba24  lea     rdx, aWdclegacyreade_6; "WdcLegacyReader::ParseTraceProperties"
0x18006ba2b  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x18006ba32  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18006ba37  jmp     loc_18006BF12
0x18006ba3c  xor     eax, eax
0x18006ba3e  lea     r8, [rbp+57h+var_88]
0x18006ba42  mov     [r13+0], ax
0x18006ba47  lea     rdx, IID_ITraceDataCollector
0x18006ba4e  mov     rax, [rbx]
0x18006ba51  mov     rcx, rbx
0x18006ba54  mov     rax, [rax]
0x18006ba57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba5c  mov     ebx, eax
0x18006ba5e  test    eax, eax
0x18006ba60  jns     short loc_18006BA68
0x18006ba62  mov     [rsp+0C0h+var_A0], eax
0x18006ba66  jmp     short loc_18006BA1A
0x18006ba68  lea     r8, [rbp+57h+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18006ba6c  mov     rcx, rsi; this
0x18006ba6f  lea     rdx, aTracebufferflu; "TraceBufferFlushInterval"
0x18006ba76  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18006ba7b  test    eax, eax
0x18006ba7d  js      short loc_18006BABE
0x18006ba7f  mov     r14, [rbp+57h+arg_18]
0x18006ba83  lea     rdx, [rbp+57h+arg_10]; int *
0x18006ba87  mov     rcx, [r14+18h]; unsigned __int16 *
0x18006ba8b  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x18006ba90  mov     ebx, eax
0x18006ba92  test    eax, eax
0x18006ba94  js      short loc_18006BA62
0x18006ba96  mov     edx, [rbp+57h+arg_10]
0x18006ba99  test    edx, edx
0x18006ba9b  jle     short loc_18006BAB6
0x18006ba9d  mov     rcx, [rbp+57h+var_88]
0x18006baa1  mov     rax, [rcx]
0x18006baa4  mov     rax, [rax+168h]
0x18006baab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bab0  mov     ebx, eax
0x18006bab2  test    eax, eax
0x18006bab4  js      short loc_18006BA62
0x18006bab6  mov     rdx, r14; struct _WDC_LEGACY_PROPERTY *
0x18006bab9  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x18006babe  lea     r8, [rbp+57h+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18006bac2  mov     rcx, rsi; this
0x18006bac5  lea     rdx, aTracebuffermax; "TraceBufferMaxCount"
0x18006bacc  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18006bad1  test    eax, eax
0x18006bad3  js      short loc_18006BB1C
0x18006bad5  mov     r14, [rbp+57h+arg_18]
0x18006bad9  lea     rdx, [rbp+57h+arg_10]; int *
0x18006badd  mov     rcx, [r14+18h]; unsigned __int16 *
0x18006bae1  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x18006bae6  mov     ebx, eax
0x18006bae8  test    eax, eax
0x18006baea  js      loc_18006BA62
0x18006baf0  mov     edx, [rbp+57h+arg_10]
0x18006baf3  test    edx, edx
0x18006baf5  jle     short loc_18006BB14
0x18006baf7  mov     rcx, [rbp+57h+var_88]
0x18006bafb  mov     rax, [rcx]
0x18006bafe  mov     rax, [rax+1A0h]
0x18006bb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb0a  mov     ebx, eax
0x18006bb0c  test    eax, eax
0x18006bb0e  js      loc_18006BA62
0x18006bb14  mov     rdx, r14; struct _WDC_LEGACY_PROPERTY *
0x18006bb17  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x18006bb1c  lea     r8, [rbp+57h+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18006bb20  mov     rcx, rsi; this
0x18006bb23  lea     rdx, aTracebuffermin; "TraceBufferMinCount"
0x18006bb2a  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18006bb2f  test    eax, eax
0x18006bb31  js      short loc_18006BB7A
0x18006bb33  mov     r14, [rbp+57h+arg_18]
0x18006bb37  lea     rdx, [rbp+57h+arg_10]; int *
0x18006bb3b  mov     rcx, [r14+18h]; unsigned __int16 *
0x18006bb3f  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x18006bb44  mov     ebx, eax
0x18006bb46  test    eax, eax
0x18006bb48  js      loc_18006BA62
0x18006bb4e  mov     edx, [rbp+57h+arg_10]
0x18006bb51  test    edx, edx
0x18006bb53  jle     short loc_18006BB72
0x18006bb55  mov     rcx, [rbp+57h+var_88]
0x18006bb59  mov     rax, [rcx]
0x18006bb5c  mov     rax, [rax+1B0h]
0x18006bb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb68  mov     ebx, eax
0x18006bb6a  test    eax, eax
0x18006bb6c  js      loc_18006BA62
0x18006bb72  mov     rdx, r14; struct _WDC_LEGACY_PROPERTY *
0x18006bb75  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x18006bb7a  lea     r8, [rbp+57h+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18006bb7e  mov     rcx, rsi; this
0x18006bb81  lea     rdx, aTracebuffersiz; "TraceBufferSize"
0x18006bb88  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18006bb8d  test    eax, eax
0x18006bb8f  js      short loc_18006BBD8
0x18006bb91  mov     r14, [rbp+57h+arg_18]
0x18006bb95  lea     rdx, [rbp+57h+arg_10]; int *
0x18006bb99  mov     rcx, [r14+18h]; unsigned __int16 *
0x18006bb9d  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x18006bba2  mov     ebx, eax
0x18006bba4  test    eax, eax
0x18006bba6  js      loc_18006BA62
0x18006bbac  mov     edx, [rbp+57h+arg_10]
0x18006bbaf  test    edx, edx
0x18006bbb1  jle     short loc_18006BBD0
0x18006bbb3  mov     rcx, [rbp+57h+var_88]
0x18006bbb7  mov     rax, [rcx]
0x18006bbba  mov     rax, [rax+108h]
0x18006bbc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbc6  mov     ebx, eax
0x18006bbc8  test    eax, eax
0x18006bbca  js      loc_18006BA62
0x18006bbd0  mov     rdx, r14; struct _WDC_LEGACY_PROPERTY *
0x18006bbd3  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x18006bbd8  mov     rcx, [rbp+57h+var_88]
0x18006bbdc  lea     rdx, [rbp+57h+var_80]
0x18006bbe0  mov     rax, [rcx]
0x18006bbe3  mov     rax, [rax+238h]
0x18006bbea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbef  mov     ebx, eax
0x18006bbf1  test    eax, eax
0x18006bbf3  js      loc_18006BA62
0x18006bbf9  mov     r14d, 1
0x18006bbff  lea     r8, [rbp+57h+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18006bc03  lea     rdx, aTraceproviderc; "TraceProviderCount"
0x18006bc0a  mov     rcx, rsi; this
0x18006bc0d  mov     r12d, r14d
0x18006bc10  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18006bc15  test    eax, eax
0x18006bc17  js      loc_18006BDA4
0x18006bc1d  mov     r15, [rbp+57h+arg_18]
0x18006bc21  lea     rdx, [rbp+57h+arg_10]; int *
0x18006bc25  mov     rcx, [r15+18h]; unsigned __int16 *
0x18006bc29  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x18006bc2e  mov     ebx, eax
0x18006bc30  test    eax, eax
0x18006bc32  js      loc_18006BA62
0x18006bc38  xor     r14d, r14d
0x18006bc3b  mov     rdx, r15; struct _WDC_LEGACY_PROPERTY *
0x18006bc3e  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x18006bc43  mov     r15d, r12d
0x18006bc46  cmp     r15d, [rbp+57h+arg_10]
0x18006bc4a  jg      loc_18006BD9A
0x18006bc50  mov     r9d, r15d
0x18006bc53  lea     r8, aTraceprovider0; "TraceProvider%05d.Guid"
0x18006bc5a  mov     edx, 400h; unsigned __int64
0x18006bc5f  mov     rcx, r13; unsigned __int16 *
0x18006bc62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006bc67  mov     ebx, eax
0x18006bc69  test    eax, eax
0x18006bc6b  js      loc_18006BA62
0x18006bc71  lea     r8, [rbp+57h+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18006bc75  mov     rdx, r13; unsigned __int16 *
0x18006bc78  mov     rcx, rsi; this
0x18006bc7b  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18006bc80  mov     ebx, eax
0x18006bc82  test    eax, eax
0x18006bc84  js      loc_18006BA62
0x18006bc8a  mov     rcx, [rbp+57h+var_90]
0x18006bc8e  test    rcx, rcx
0x18006bc91  jz      short loc_18006BCA3
0x18006bc93  mov     rax, [rcx]
0x18006bc96  mov     rax, [rax+10h]
0x18006bc9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc9f  mov     [rbp+57h+var_90], rdi
0x18006bca3  mov     rcx, [rbp+57h+var_80]
0x18006bca7  lea     rdx, [rbp+57h+var_90]
0x18006bcab  mov     rax, [rcx]
0x18006bcae  mov     rax, [rax+70h]
0x18006bcb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bcb7  mov     ebx, eax
0x18006bcb9  test    eax, eax
0x18006bcbb  js      loc_18006BA62
0x18006bcc1  mov     r13, [rbp+57h+arg_18]
0x18006bcc5  mov     rbx, [r13+18h]
0x18006bcc9  test    r14, r14
0x18006bccc  jz      short loc_18006BCD7
0x18006bcce  mov     rcx, r14; bstrString
0x18006bcd1  call    cs:__imp_SysFreeString
0x18006bcd7  mov     rcx, rbx; psz
0x18006bcda  call    cs:__imp_SysAllocString
0x18006bce0  mov     r14, rax
0x18006bce3  test    rbx, rbx
0x18006bce6  jz      short loc_18006BCED
0x18006bce8  test    rax, rax
0x18006bceb  jz      short loc_18006BD42
0x18006bced  mov     rcx, [rbp+57h+var_90]
0x18006bcf1  mov     rdx, r14
0x18006bcf4  mov     r8, [rsi+20h]
0x18006bcf8  mov     rax, [rcx]
0x18006bcfb  mov     rax, [rax+0A8h]
0x18006bd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd07  mov     ebx, eax
0x18006bd09  test    eax, eax
0x18006bd0b  js      loc_18006BD94
0x18006bd11  mov     rcx, [rbp+57h+var_80]
0x18006bd15  mov     rdx, [rbp+57h+var_90]
0x18006bd19  mov     rax, [rcx]
0x18006bd1c  mov     rax, [rax+50h]
0x18006bd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd25  mov     ebx, eax
0x18006bd27  test    eax, eax
0x18006bd29  js      short loc_18006BD94
0x18006bd2b  mov     rdx, r13; struct _WDC_LEGACY_PROPERTY *
0x18006bd2e  xor     r12d, r12d
0x18006bd31  call    ?FreeProperty@WdcLegacyReader@@AEAAJPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::FreeProperty(_WDC_LEGACY_PROPERTY *)
0x18006bd36  mov     r13, [rbp+57h+var_78]
0x18006bd3a  inc     r15d
0x18006bd3d  jmp     loc_18006BC46
0x18006bd42  mov     edi, 8007000Eh
0x18006bd47  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18006bd4e  xor     r8d, r8d; int
0x18006bd51  mov     [rsp+0C0h+var_A0], edi
0x18006bd55  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18006bd5c  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18006bd63  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18006bd68  mov     ebx, edi
0x18006bd6a  mov     [rsp+0C0h+var_A0], edi
0x18006bd6e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18006bd75  xor     r8d, r8d; int
0x18006bd78  lea     rdx, aWdclegacyreade_6; "WdcLegacyReader::ParseTraceProperties"
0x18006bd7f  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x18006bd86  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18006bd8b  mov     r13, [rbp+57h+var_78]
0x18006bd8f  jmp     loc_18006BF12
0x18006bd94  mov     [rsp+0C0h+var_A0], eax
0x18006bd98  jmp     short loc_18006BD6E
0x18006bd9a  mov     r15, qword ptr [rbp+57h+var_40]
0x18006bd9e  mov     r14d, 1
0x18006bda4  lea     r8, [rbp+57h+arg_18]; struct _WDC_LEGACY_PROPERTY **
0x18006bda8  mov     rcx, rsi; this
0x18006bdab  lea     rdx, aTraceflags; "TraceFlags"
0x18006bdb2  call    ?GetProperty@WdcLegacyReader@@AEAAJPEAGPEAPEAU_WDC_LEGACY_PROPERTY@@@Z; WdcLegacyReader::GetProperty(ushort *,_WDC_LEGACY_PROPERTY * *)
0x18006bdb7  test    eax, eax
0x18006bdb9  js      loc_18006BF10
0x18006bdbf  test    r12d, r12d
0x18006bdc2  jz      loc_18006BF10
0x18006bdc8  mov     rcx, [rbp+57h+arg_18]
0x18006bdcc  lea     rdx, [rbp+57h+arg_10]; int *
0x18006bdd0  mov     rcx, [rcx+18h]; unsigned __int16 *
0x18006bdd4  call    ?WdcHexToLong@@YAJPEBGPEAJ@Z; WdcHexToLong(ushort const *,long *)
0x18006bdd9  mov     ebx, eax
0x18006bddb  test    eax, eax
0x18006bddd  js      loc_18006BA62
0x18006bde3  mov     esi, [rbp+57h+arg_10]
0x18006bde6  test    esi, esi
0x18006bde8  jz      loc_18006BF12
0x18006bdee  mov     rcx, [rbp+57h+var_90]
0x18006bdf2  test    rcx, rcx
0x18006bdf5  jz      short loc_18006BE07
0x18006bdf7  mov     rax, [rcx]
0x18006bdfa  mov     rax, [rax+10h]
0x18006bdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be03  mov     [rbp+57h+var_90], rdi
0x18006be07  mov     rcx, [rbp+57h+var_80]
0x18006be0b  lea     rdx, [rbp+57h+var_90]
0x18006be0f  mov     rax, [rcx]
0x18006be12  mov     rax, [rax+70h]
0x18006be16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be1b  mov     ebx, eax
0x18006be1d  test    eax, eax
  ... truncated ...
```
