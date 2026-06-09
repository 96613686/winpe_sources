# WdcPortMonitor::UpdatePort(ulong,ulong,void *)

- ea: `0x1800076e0`
- end: `0x1800081d8`
- name: `?UpdatePort@WdcPortMonitor@@AEAAJKKPEAX@Z`
- size: `2808`
- prototype: `int(WdcPortMonitor *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x180007230`

## callees

- `0x180004550`
- `0x180004a90`
- `0x180005388`
- `0x1800065f0`
- `0x180006a80`
- `0x1800076e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18000ff88`
- `0x18001e40c`
- `0x18003a3c0`
- `0x18003b0ac`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringW` at `0x18000774e`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000774e`
- `ntdll!RtlIpv6AddressToStringW` at `0x180007bd9`
- `ntdll!RtlIpv6AddressToStringW` at `0x180007f1d`
- `ntdll!RtlIpv6AddressToStringW` at `0x180007bd9`
- `ntdll!RtlIpv6AddressToStringW` at `0x180007f1d`
- `OLEAUT32!__imp_SysAllocString` at `0x180007dc4`
- `OLEAUT32!__imp_SysAllocString` at `0x180007e6a`
- `OLEAUT32!__imp_SysAllocString` at `0x180007ee4`
- `OLEAUT32!__imp_SysAllocString` at `0x180007dc4`
- `OLEAUT32!__imp_SysAllocString` at `0x180007e6a`
- `OLEAUT32!__imp_SysAllocString` at `0x180007ee4`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b18`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008112`
- `OLEAUT32!__imp_SysFreeString` at `0x180008186`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b18`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008112`
- `OLEAUT32!__imp_SysFreeString` at `0x180008186`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081c6`
- `WS2_32!__imp_ntohs` at `0x180007ff5`
- `WS2_32!__imp_ntohs` at `0x18000803f`
- `WS2_32!__imp_ntohs` at `0x18000809c`
- `WS2_32!__imp_ntohs` at `0x1800080d5`
- `WS2_32!__imp_ntohs` at `0x180007ff5`
- `WS2_32!__imp_ntohs` at `0x18000803f`
- `WS2_32!__imp_ntohs` at `0x18000809c`
- `WS2_32!__imp_ntohs` at `0x1800080d5`

## string_xrefs

- `0x180007cf4`: `WdcPortMonitor::UpdatePort`
- `0x180007fc4`: `WdcPortMonitor::UpdatePort`
- `0x18000815c`: `WdcPortMonitor::UpdatePort`
- `0x180007f9e`: `WdcPortMonitor::CreateEntry`

## pseudocode

```c
__int64 __fastcall WdcPortMonitor::UpdatePort(WdcPortMonitor *this, int a2, int a3, struct in_addr *a4)
{
  int S_addr; // r14d
  const struct in_addr *v9; // rcx
  const char *v10; // rdx
  WdcDataMonitor *v11; // rcx
  int v12; // r8d
  char *v13; // rbx
  char *v14; // rsi
  char *v15; // r13
  bool v16; // zf
  char *v17; // rax
  _QWORD *v18; // rbx
  WdcDataMonitor *v19; // rcx
  char *v20; // rax
  __int64 v21; // r9
  int v22; // r10d
  __int64 v23; // rcx
  __int64 v24; // r9
  int v25; // ebp
  __int64 v26; // rax
  unsigned int v27; // ebx
  int v28; // eax
  WdcStringMap *v29; // rcx
  WdcPortMonitor *v30; // r14
  unsigned int v31; // ecx
  unsigned int i; // edx
  __int64 v33; // r8
  __int64 v34; // rcx
  unsigned __int64 v35; // r8
  ULONG v37; // eax
  _QWORD *v38; // rax
  OLECHAR *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  unsigned int v42; // eax
  unsigned __int64 v43; // rdx
  _QWORD *v44; // rax
  __int64 v45; // rcx
  int updated; // eax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rcx
  OLECHAR *v52; // rcx
  OLECHAR *v53; // r14
  BSTR v54; // rax
  _QWORD *v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rax
  OLECHAR *v59; // rcx
  BSTR v60; // rax
  _QWORD *v61; // rbx
  OLECHAR *v62; // rcx
  BSTR v63; // rax
  OLECHAR *v64; // rcx
  int v65; // r15d
  struct in_addr *v66; // rcx
  __int64 v67; // [rsp+20h] [rbp-F8h]
  __int64 v68; // [rsp+20h] [rbp-F8h]
  unsigned int ImageName; // [rsp+30h] [rbp-E8h]
  OLECHAR *psz; // [rsp+40h] [rbp-D8h] BYREF
  WCHAR S[64]; // [rsp+50h] [rbp-C8h] BYREF

  psz = 0;
  if ( a2 != 2 )
  {
    if ( a2 == 23 )
    {
      if ( a3 == 32220 )
      {
        S_addr = a4[13].S_un.S_addr;
        RtlIpv6AddressToStringW((const struct in6_addr *)a4, S);
        goto LABEL_6;
      }
      if ( a3 == 32221 )
      {
        S_addr = a4[6].S_un.S_addr;
        RtlIpv6AddressToStringW((const struct in6_addr *)a4, S);
        goto LABEL_6;
      }
    }
    return (unsigned int)-2147467259;
  }
  if ( a3 == 32220 )
  {
    S_addr = a4[5].S_un.S_addr;
    v9 = a4 + 1;
    goto LABEL_5;
  }
  if ( a3 != 32221 )
    return (unsigned int)-2147467259;
  S_addr = a4[2].S_un.S_addr;
  v9 = a4;
LABEL_5:
  RtlIpv4AddressToStringW(v9, S);
LABEL_6:
  v13 = (char *)*((_QWORD *)this + 11);
  v14 = (char *)this + 88;
  if ( v13 == (char *)this + 88 )
    goto LABEL_15;
  while ( 1 )
  {
    v15 = v13 - 16;
    if ( *((_DWORD *)v13 + 42) != a2 || *((double *)v15 + 20) != (double)a3 )
      goto LABEL_14;
    if ( a2 == 2 )
      break;
    if ( a3 == 32220 )
    {
      v40 = *((_QWORD *)v15 + 24) - *(_QWORD *)&a4->S_un.S_un_b.s_b1;
      if ( !v40 )
        v40 = *((_QWORD *)v15 + 25) - *(_QWORD *)&a4[2].S_un.S_un_b.s_b1;
      if ( !v40 && *((_DWORD *)v15 + 52) == a4[4].S_un.S_addr && *((_DWORD *)v15 + 53) == a4[5].S_un.S_addr )
      {
        v41 = *((_QWORD *)v15 + 27) - *(_QWORD *)&a4[6].S_un.S_un_b.s_b1;
        if ( !v41 )
          v41 = *((_QWORD *)v15 + 28) - *(_QWORD *)&a4[8].S_un.S_un_b.s_b1;
        if ( !v41 && *((_DWORD *)v15 + 58) == a4[10].S_un.S_addr )
        {
          v16 = *((_DWORD *)v15 + 59) == a4[11].S_un.S_addr;
LABEL_13:
          if ( v16 )
            goto LABEL_34;
        }
      }
    }
    else
    {
      v26 = *(_QWORD *)(v15 + 188) - *(_QWORD *)&a4->S_un.S_un_b.s_b1;
      if ( !v26 )
        v26 = *(_QWORD *)(v15 + 196) - *(_QWORD *)&a4[2].S_un.S_un_b.s_b1;
      if ( !v26 && *((_DWORD *)v15 + 51) == a4[4].S_un.S_addr )
      {
        v16 = *((_DWORD *)v15 + 52) == a4[5].S_un.S_addr;
        goto LABEL_13;
      }
    }
LABEL_14:
    v13 = *(char **)v13;
    if ( v13 == v14 )
      goto LABEL_15;
  }
  if ( a3 != 32220 )
  {
    if ( *((_DWORD *)v15 + 47) == a4->S_un.S_addr )
    {
      v16 = *((_DWORD *)v15 + 48) == a4[1].S_un.S_addr;
      goto LABEL_13;
    }
    goto LABEL_14;
  }
  if ( *((_DWORD *)v15 + 48) != a4[1].S_un.S_addr
    || *((_DWORD *)v15 + 49) != a4[2].S_un.S_addr
    || *((_DWORD *)v15 + 50) != a4[3].S_un.S_addr
    || *((_DWORD *)v15 + 51) != a4[4].S_un.S_addr )
  {
    goto LABEL_14;
  }
LABEL_34:
  if ( v13 == v14 )
  {
LABEL_15:
    v17 = (char *)WdcAlloc(0xF0u, v10, v12);
    v15 = v17;
    if ( !v17 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\port.cpp",
        "WdcPortMonitor::CreateEntry",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      v27 = -2147024882;
      LODWORD(v67) = -2147024882;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\port.cpp",
        "WdcPortMonitor::UpdatePort",
        0,
        L"FAILURE: 0x%08x",
        v67);
      return v27;
    }
    memset_0(v17, 0, 0xF0u);
    *((_DWORD *)v15 + 14) = 240;
    *((_QWORD *)v15 + 1) = v15;
    v18 = v15 + 16;
    *(_QWORD *)v15 = v15;
    *((_QWORD *)v15 + 3) = v15 + 16;
    *((_QWORD *)v15 + 2) = v15 + 16;
    *((_QWORD *)v15 + 5) = v15 + 32;
    *((_QWORD *)v15 + 4) = v15 + 32;
    *((_QWORD *)v15 + 10) = v15 + 88;
    *((_DWORD *)v15 + 22) = 0x10000000;
    *((_DWORD *)v15 + 16) = 393217;
    *((_DWORD *)v15 + 17) = 1;
    *((_DWORD *)v15 + 26) = 553713664;
    *((_DWORD *)v15 + 30) = 0x10000000;
    *((_DWORD *)v15 + 34) = 553648128;
    *((_DWORD *)v15 + 38) = 587202560;
    *((_DWORD *)v15 + 42) = 587202560;
    WdcDataMonitor::SetRowDirty(v19, (struct _WDC_DATA_INFO *)v15);
    v20 = (char *)this + 16 * (int)WdcHashKey((unsigned int)S_addr) + 104;
    v23 = *(_QWORD *)v20;
    if ( *(char **)(*(_QWORD *)v20 + 8LL) != v20 )
      goto LABEL_71;
    *(_QWORD *)v15 = v23;
    *((_QWORD *)v15 + 1) = v20;
    *(_QWORD *)(v23 + 8) = v15;
    *(_QWORD *)v20 = v15;
    *((_DWORD *)v15 + 38) |= v22;
    *((_QWORD *)v15 + 6) = v21;
    *((_DWORD *)v15 + 46) = a2;
    *((double *)v15 + 20) = (double)a3;
    if ( (_QWORD *)*v18 == v18 )
    {
      v49 = *(_QWORD *)v14;
      if ( *(char **)(*(_QWORD *)v14 + 8LL) != v14 )
        goto LABEL_71;
      *v18 = v49;
      *((_QWORD *)v15 + 3) = v14;
      *(_QWORD *)(v49 + 8) = v18;
      *(_QWORD *)v14 = v18;
    }
    if ( a2 == 2 )
    {
      if ( a3 == 32220 )
      {
        *((double *)v15 + 18) = (double)ntohs(a4[2].S_un.S_un_w.s_w1);
        *((struct in_addr *)v15 + 48) = a4[1];
        *((struct in_addr *)v15 + 49) = a4[2];
        goto LABEL_136;
      }
      if ( a3 - 32220 == v22 )
      {
        *((double *)v15 + 18) = (double)ntohs(a4[1].S_un.S_un_w.s_w1);
        *((struct in_addr *)v15 + 47) = *a4;
        *((struct in_addr *)v15 + 48) = a4[1];
        goto LABEL_136;
      }
    }
    else
    {
      if ( a3 == 32220 )
      {
        *((double *)v15 + 18) = (double)ntohs(a4[5].S_un.S_un_w.s_w1);
        *((_OWORD *)v15 + 12) = *(_OWORD *)&a4->S_un.S_un_b.s_b1;
        *((struct in_addr *)v15 + 52) = a4[4];
        *((struct in_addr *)v15 + 53) = a4[5];
        goto LABEL_136;
      }
      if ( a3 - 32220 == v22 )
      {
        *((double *)v15 + 18) = (double)ntohs(a4[5].S_un.S_un_w.s_w1);
        *(_OWORD *)(v15 + 188) = *(_OWORD *)&a4->S_un.S_un_b.s_b1;
        *((struct in_addr *)v15 + 51) = a4[4];
        *((struct in_addr *)v15 + 52) = a4[5];
LABEL_136:
        v22 = 1;
      }
    }
    *((_DWORD *)v15 + 34) |= 1u;
    if ( (_QWORD *)*v18 == v18 )
    {
      v50 = *(_QWORD *)v14;
      if ( *(char **)(*(_QWORD *)v14 + 8LL) != v14 )
        goto LABEL_71;
      *v18 = v50;
      *((_QWORD *)v15 + 3) = v14;
      *(_QWORD *)(v50 + 8) = v18;
      *(_QWORD *)v14 = v18;
    }
    LOWORD(v24) = 0;
    ImageName = 0;
    goto LABEL_22;
  }
  v28 = *((_DWORD *)v15 + 17);
  LOWORD(v24) = 0;
  ImageName = 0;
  if ( (v28 & 0x18000000) == 0 )
  {
    v25 = 0;
    goto LABEL_37;
  }
  *((_DWORD *)v15 + 17) = v28 & 0xE7FFFFFF;
  WdcDataMonitor::SetRowDirty(v11, (struct _WDC_DATA_INFO *)(v13 - 16));
  v64 = (OLECHAR *)*((_QWORD *)v15 + 12);
  *((_DWORD *)v15 + 17) &= 0xFCFFFFFF;
  *((_QWORD *)v15 + 9) = v24;
  if ( v64 )
  {
    SysFreeString(v64);
    v24 = 0;
    v22 = 1;
    *((_QWORD *)v15 + 12) = 0;
  }
  *((_DWORD *)v15 + 22) |= 1u;
  if ( *(char **)v13 == v13 )
  {
    v47 = *(_QWORD *)v14;
    if ( *(char **)(*(_QWORD *)v14 + 8LL) == v14 )
    {
      *(_QWORD *)v13 = v47;
      *((_QWORD *)v13 + 1) = v14;
      *(_QWORD *)(v47 + 8) = v13;
      *(_QWORD *)v14 = v13;
      goto LABEL_125;
    }
    goto LABEL_71;
  }
LABEL_125:
  *((_DWORD *)v15 + 42) |= 1u;
  *((_QWORD *)v15 + 22) = v24;
  if ( *(char **)v13 != v13 )
  {
LABEL_22:
    v25 = v22;
    goto LABEL_37;
  }
  v48 = *(_QWORD *)v14;
  if ( *(char **)(*(_QWORD *)v14 + 8LL) != v14 )
    goto LABEL_71;
  *(_QWORD *)v13 = v48;
  v25 = v22;
  *((_QWORD *)v13 + 1) = v14;
  *(_QWORD *)(v48 + 8) = v13;
  *(_QWORD *)v14 = v13;
LABEL_37:
  if ( a2 == 2 )
  {
    if ( a3 != 32220 )
      goto LABEL_39;
    v37 = a4->S_un.S_addr;
LABEL_70:
    *((_DWORD *)v15 + 47) = v37;
  }
  else if ( a3 == 32220 )
  {
    v37 = a4[12].S_un.S_addr;
    goto LABEL_70;
  }
LABEL_39:
  if ( *((double *)v15 + 14) != (double)S_addr )
  {
    *((_DWORD *)v15 + 26) |= 1u;
    v38 = v15 + 16;
    *((double *)v15 + 14) = (double)S_addr;
    if ( (_QWORD *)*v38 == v38 )
    {
      v51 = *(_QWORD *)v14;
      if ( *(char **)(*(_QWORD *)v14 + 8LL) != v14 )
        goto LABEL_71;
      *v38 = v51;
      *((_QWORD *)v15 + 3) = v14;
      *(_QWORD *)(v51 + 8) = v38;
      *(_QWORD *)v14 = v38;
    }
    v39 = (OLECHAR *)*((_QWORD *)v15 + 12);
    if ( v39 )
    {
      SysFreeString(v39);
      LOWORD(v24) = 0;
      *((_QWORD *)v15 + 12) = 0;
    }
  }
  v29 = (WdcStringMap *)*((_QWORD *)v15 + 12);
  if ( v29 && (_WORD)v24 != *(_WORD *)v29 )
  {
LABEL_42:
    v30 = this;
    goto LABEL_43;
  }
  if ( !S_addr )
  {
    updated = WdcStringMap::LoadStringW(v29, 0x81B0u, &psz);
    ImageName = updated;
    if ( updated < 0 )
      goto LABEL_86;
    v52 = (OLECHAR *)*((_QWORD *)v15 + 12);
    v53 = psz;
    if ( v52 )
    {
      SysFreeString(v52);
      *((_QWORD *)v15 + 12) = 0;
    }
    v54 = SysAllocString(v53);
    if ( !v53 || v54 )
    {
      *((_QWORD *)v15 + 12) = v54;
      *((_DWORD *)v15 + 22) |= 1u;
      v55 = v15 + 16;
      ImageName = 0;
      if ( (_QWORD *)*v55 != v55 )
        goto LABEL_42;
      v56 = *(_QWORD *)v14;
      if ( *(char **)(*(_QWORD *)v14 + 8LL) == v14 )
      {
        *v55 = v56;
        *((_QWORD *)v15 + 3) = v14;
        *(_QWORD *)(v56 + 8) = v55;
        *(_QWORD *)v14 = v55;
        goto LABEL_42;
      }
      goto LABEL_71;
    }
    goto LABEL_137;
  }
  v43 = (unsigned int)S_addr;
  v30 = this;
  ImageName = WdcTraceControl::GetImageName(*((WdcTraceControl **)this + 1019), v43, (unsigned __int16 **)v15 + 12, 0);
  if ( !ImageName )
  {
    *((_DWORD *)v15 + 22) |= 1u;
    v44 = v15 + 16;
    if ( (_QWORD *)*v44 != v44 )
      goto LABEL_43;
    v45 = *(_QWORD *)v14;
    if ( *(char **)(*(_QWORD *)v14 + 8LL) == v14 )
    {
      *v44 = v45;
      *((_QWORD *)v15 + 3) = v14;
      *(_QWORD *)(v45 + 8) = v44;
      *(_QWORD *)v14 = v44;
      goto LABEL_43;
    }
LABEL_71:
    __fastfail(3u);
  }
  ImageName = 0;
LABEL_43:
  if ( v25 )
  {
    v59 = (OLECHAR *)*((_QWORD *)v15 + 16);
    if ( v59 )
    {
      SysFreeString(v59);
      *((_QWORD *)v15 + 16) = 0;
    }
    v60 = SysAllocString(S);
    if ( v60 )
    {
      *((_QWORD *)v15 + 16) = v60;
      v61 = v15 + 16;
      *((_DWORD *)v15 + 30) |= 1u;
      if ( (_QWORD *)*v61 == v61 )
      {
        v57 = *(_QWORD *)v14;
        if ( *(char **)(*(_QWORD *)v14 + 8LL) != v14 )
          goto LABEL_71;
        *v61 = v57;
        *((_QWORD *)v15 + 3) = v14;
        *(_QWORD *)(v57 + 8) = v61;
        *(_QWORD *)v14 = v61;
      }
      updated = WdcPortMonitor::UpdatePortStatus(v30, (struct _WDC_PORT_INFO *)v15);
      ImageName = updated;
      if ( updated >= 0 )
      {
        if ( a2 == 2 )
        {
          v65 = a3 - 32220;
          if ( v65 )
          {
            if ( v65 != 1 )
              goto LABEL_116;
            v66 = a4;
          }
          else
          {
            v66 = a4 + 1;
          }
          WdcIpv4AddressToString(v66, S);
        }
        else if ( (unsigned int)(a3 - 32220) <= 1 )
        {
          WdcIpv6AddressToString((struct in6_addr *)a4, S);
        }
LABEL_116:
        v62 = (OLECHAR *)*((_QWORD *)v15 + 16);
        if ( v62 )
        {
          SysFreeString(v62);
          *((_QWORD *)v15 + 16) = 0;
        }
        v63 = SysAllocString(S);
        if ( v63 )
        {
          *((_QWORD *)v15 + 16) = v63;
          *((_DWORD *)v15 + 30) |= 1u;
          ImageName = 0;
          if ( (_QWORD *)*v61 == v61 )
          {
            v58 = *(_QWORD *)v14;
            if ( *(char **)(*(_QWORD *)v14 + 8LL) != v14 )
              goto LABEL_71;
            *v61 = v58;
            *((_QWORD *)v15 + 3) = v14;
            *(_QWORD *)(v58 + 8) = v61;
            *(_QWORD *)v14 = v61;
          }
          goto LABEL_44;
        }
        goto LABEL_137;
      }
LABEL_86:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\port.cpp",
        "WdcPortMonitor::UpdatePort",
        0,
        L"FAILURE: 0x%08x",
        updated);
      return ImageName;
    }
LABEL_137:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
      "WdcAssignString",
      0,
      L"FAILURE: 0x%08x",
      -2147024882);
    LODWORD(v68) = -2147024882;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\port.cpp",
      "WdcPortMonitor::UpdatePort",
      0,
      L"FAILURE: 0x%08x",
      v68);
    return (unsigned int)-2147024882;
  }
LABEL_44:
  v31 = MEMORY[0x7FFE0018];
  for ( i = MEMORY[0x7FFE0014]; MEMORY[0x7FFE0018] != MEMORY[0x7FFE001C]; i = MEMORY[0x7FFE0014] )
    v31 = MEMORY[0x7FFE0018];
  v33 = v31;
  v34 = *((_QWORD *)v15 + 9);
  v35 = i | (unsigned __int64)(v33 << 32);
  if ( v34 )
  {
    while ( (__int64)(v35 - v34) > 5000000 )
    {
      v42 = *((unsigned __int16 *)v15 + 32);
      v34 += 10000000;
      *((_QWORD *)v15 + 9) = v34;
      if ( v42 < *((_DWORD *)v30 + 2288) )
        *((_WORD *)v15 + 32) = v42 + 1;
    }
  }
  else
  {
    *((_QWORD *)v15 + 9) = v35;
    *((_WORD *)v15 + 32) = 1;
  }
  *((_DWORD *)v15 + 17) |= 8u;
  return ImageName;
}

```

## disassembly

```asm
0x1800076e0  mov     [rsp+arg_8], rbx
0x1800076e5  push    rbp
0x1800076e6  push    rsi
0x1800076e7  push    rdi
0x1800076e8  push    r12
0x1800076ea  push    r13
0x1800076ec  push    r14
0x1800076ee  push    r15
0x1800076f0  sub     rsp, 0E0h
0x1800076f7  mov     rax, cs:__security_cookie
0x1800076fe  xor     rax, rsp
0x180007701  mov     [rsp+118h+var_48], rax
0x180007709  mov     r15d, r8d
0x18000770c  mov     r12, r9
0x18000770f  mov     [rsp+118h+var_E0], rcx
0x180007714  mov     edi, edx
0x180007716  mov     [rsp+118h+psz], 0
0x18000771f  mov     rbp, rcx
0x180007722  cmp     edx, 2
0x180007725  jnz     loc_180007989
0x18000772b  mov     eax, r15d
0x18000772e  sub     eax, 7DDCh
0x180007733  jz      loc_18000797C
0x180007739  cmp     eax, 1
0x18000773c  jnz     loc_180007992
0x180007742  mov     r14d, [r9+8]
0x180007746  mov     rcx, r9; Addr
0x180007749  lea     rdx, [rsp+118h+S]; S
0x18000774e  call    cs:__imp_RtlIpv4AddressToStringW
0x180007754  mov     rbx, [rbp+58h]
0x180007758  lea     rsi, [rbp+58h]
0x18000775c  mov     r10d, 1
0x180007762  cmp     rbx, rsi
0x180007765  jz      short loc_1800077DC
0x180007767  nop     word ptr [rax+rax+00000000h]
0x180007770  lea     r13, [rbx-10h]
0x180007774  cmp     [r13+0B8h], edi
0x18000777b  jnz     short loc_1800077D4
0x18000777d  movsd   xmm0, qword ptr [r13+0A0h]
0x180007786  xorps   xmm1, xmm1
0x180007789  cvtsi2sd xmm1, r15
0x18000778e  ucomisd xmm0, xmm1
0x180007792  jp      short loc_1800077D4
0x180007794  jnz     short loc_1800077D4
0x180007796  cmp     edi, 2
0x180007799  jnz     loc_180007914
0x18000779f  cmp     r15d, 7DDCh
0x1800077a6  jz      loc_180007C44
0x1800077ac  cmp     r15d, 7DDDh
0x1800077b3  jnz     short loc_1800077D4
0x1800077b5  mov     eax, [r12]
0x1800077b9  cmp     [r13+0BCh], eax
0x1800077c0  jnz     short loc_1800077D4
0x1800077c2  mov     eax, [r12+4]
0x1800077c7  cmp     [r13+0C0h], eax
0x1800077ce  jz      loc_1800079C0
0x1800077d4  mov     rbx, [rbx]
0x1800077d7  cmp     rbx, rsi
0x1800077da  jnz     short loc_180007770
0x1800077dc  mov     ecx, 0F0h; dwBytes
0x1800077e1  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800077e6  mov     r13, rax
0x1800077e9  test    rax, rax
0x1800077ec  jz      loc_180007F8C
0x1800077f2  xor     edx, edx; Val
0x1800077f4  mov     r8d, 0F0h; Size
0x1800077fa  mov     rcx, rax; void *
0x1800077fd  call    memset_0
0x180007802  mov     dword ptr [r13+38h], 0F0h
0x18000780a  lea     rax, [r13+20h]
0x18000780e  mov     [r13+8], r13
0x180007812  lea     rbx, [r13+10h]
0x180007816  mov     [r13+0], r13
0x18000781a  mov     r10d, 1
0x180007820  mov     [rbx+8], rbx
0x180007824  mov     rdx, r13; struct _WDC_DATA_INFO *
0x180007827  mov     [rbx], rbx
0x18000782a  mov     [rax+8], rax
0x18000782e  mov     [rax], rax
0x180007831  lea     rax, [r13+58h]
0x180007835  mov     [r13+50h], rax
0x180007839  mov     dword ptr [rax], 10000000h
0x18000783f  mov     dword ptr [r13+40h], 60001h
0x180007847  mov     [r13+44h], r10d
0x18000784b  mov     dword ptr [r13+68h], 21010000h
0x180007853  mov     dword ptr [r13+78h], 10000000h
0x18000785b  mov     dword ptr [r13+88h], 21000000h
0x180007866  mov     dword ptr [r13+98h], 23000000h
0x180007871  mov     dword ptr [r13+0A8h], 23000000h
0x18000787c  call    ?SetRowDirty@WdcDataMonitor@@QEAAJPEAU_WDC_DATA_INFO@@@Z; WdcDataMonitor::SetRowDirty(_WDC_DATA_INFO *)
0x180007881  mov     ecx, r14d; unsigned __int64
0x180007884  mov     r9d, r14d
0x180007887  call    ?WdcHashKey@@YAH_K@Z; WdcHashKey(unsigned __int64)
0x18000788c  cdqe
0x18000788e  shl     rax, 4
0x180007892  add     rax, 68h ; 'h'
0x180007896  add     rax, rbp
0x180007899  mov     rcx, [rax]
0x18000789c  cmp     [rcx+8], rax
0x1800078a0  jnz     loc_180007BF4
0x1800078a6  mov     [r13+0], rcx
0x1800078aa  xorps   xmm0, xmm0
0x1800078ad  mov     [r13+8], rax
0x1800078b1  mov     [rcx+8], r13
0x1800078b5  mov     [rax], r13
0x1800078b8  or      [r13+98h], r10d
0x1800078bf  cvtsi2sd xmm0, r15
0x1800078c4  mov     [r13+30h], r9
0x1800078c8  mov     [r13+0B8h], edi
0x1800078cf  movsd   qword ptr [r13+0A0h], xmm0
0x1800078d8  cmp     [rbx], rbx
0x1800078db  jz      loc_180007D4F
0x1800078e1  cmp     edi, 2
0x1800078e4  jz      loc_180008083
0x1800078ea  cmp     edi, 17h
0x1800078ed  jz      loc_180007FDC
0x1800078f3  or      dword ptr [r13+88h], 1
0x1800078fb  cmp     [rbx], rbx
0x1800078fe  jz      loc_180007D6F
0x180007904  xor     r9d, r9d
0x180007907  mov     [rsp+118h+var_E8], r9d
0x18000790c  mov     ebp, r10d
0x18000790f  jmp     loc_1800079E3
0x180007914  cmp     edi, 17h
0x180007917  jnz     loc_1800077D4
0x18000791d  cmp     r15d, 7DDCh
0x180007924  jz      loc_180007B2A
0x18000792a  cmp     r15d, 7DDDh
0x180007931  jnz     loc_1800077D4
0x180007937  mov     rax, [r13+0BCh]
0x18000793e  sub     rax, [r12]
0x180007942  jnz     short loc_180007950
0x180007944  mov     rax, [r13+0C4h]
0x18000794b  sub     rax, [r12+8]
0x180007950  test    rax, rax
0x180007953  jnz     loc_1800077D4
0x180007959  mov     eax, [r12+10h]
0x18000795e  cmp     [r13+0CCh], eax
0x180007965  jnz     loc_1800077D4
0x18000796b  mov     eax, [r12+14h]
0x180007970  cmp     [r13+0D0h], eax
0x180007977  jmp     loc_1800077CE
0x18000797c  mov     r14d, [r9+14h]
0x180007980  lea     rcx, [r9+4]
0x180007984  jmp     loc_180007749
0x180007989  cmp     edi, 17h
0x18000798c  jz      loc_180007BB6
0x180007992  mov     ebx, 80004005h
0x180007997  jmp     loc_180007AA6
0x18000799c  mov     eax, [r12+0Ch]
0x1800079a1  cmp     [r13+0C8h], eax
0x1800079a8  jnz     loc_1800077D4
0x1800079ae  mov     eax, [r12+10h]
0x1800079b3  cmp     [r13+0CCh], eax
0x1800079ba  jnz     loc_1800077D4
0x1800079c0  cmp     rbx, rsi
0x1800079c3  jz      loc_1800077DC
0x1800079c9  mov     eax, [r13+44h]
0x1800079cd  xor     r9d, r9d
0x1800079d0  mov     [rsp+118h+var_E8], r9d
0x1800079d5  test    eax, 18000000h
0x1800079da  jnz     loc_180007F28
0x1800079e0  mov     ebp, r9d
0x1800079e3  cmp     edi, 2
0x1800079e6  jnz     loc_180007AD3
0x1800079ec  cmp     r15d, 7DDCh
0x1800079f3  jz      loc_180007BE4
0x1800079f9  movsd   xmm0, qword ptr [r13+70h]
0x1800079ff  xorps   xmm1, xmm1
0x180007a02  mov     eax, r14d
0x180007a05  cvtsi2sd xmm1, rax
0x180007a0a  ucomisd xmm0, xmm1
0x180007a0e  jp      loc_180007AF3
0x180007a14  jnz     loc_180007AF3
0x180007a1a  mov     rcx, [r13+60h]; this
0x180007a1e  test    rcx, rcx
0x180007a21  jz      loc_180007C6D
0x180007a27  cmp     r9w, [rcx]
0x180007a2b  jz      loc_180007C6D
0x180007a31  mov     r14, [rsp+118h+var_E0]
0x180007a36  test    ebp, ebp
0x180007a38  jnz     loc_180007E53
0x180007a3e  mov     ecx, ds:7FFE0018h
0x180007a45  mov     edx, ds:7FFE0014h
0x180007a4c  mov     eax, ds:7FFE001Ch
0x180007a53  cmp     ecx, eax
0x180007a55  jz      short loc_180007A79
0x180007a57  nop     word ptr [rax+rax+00000000h]
0x180007a60  mov     ecx, ds:7FFE0018h
0x180007a67  mov     edx, ds:7FFE0014h
0x180007a6e  mov     eax, ds:7FFE001Ch
0x180007a75  cmp     ecx, eax
0x180007a77  jnz     short loc_180007A60
0x180007a79  mov     r8d, ecx
0x180007a7c  mov     rcx, [r13+48h]
0x180007a80  shl     r8, 20h
0x180007a84  mov     eax, edx
0x180007a86  or      r8, rax
0x180007a89  test    rcx, rcx
0x180007a8c  jnz     loc_180007BFB
0x180007a92  mov     [r13+48h], r8
0x180007a96  mov     word ptr [r13+40h], 1
0x180007a9d  or      dword ptr [r13+44h], 8
0x180007aa2  mov     ebx, [rsp+118h+var_E8]
0x180007aa6  mov     eax, ebx
0x180007aa8  mov     rcx, [rsp+118h+var_48]
0x180007ab0  xor     rcx, rsp; StackCookie
0x180007ab3  call    __security_check_cookie
0x180007ab8  mov     rbx, [rsp+118h+arg_8]
0x180007ac0  add     rsp, 0E0h
0x180007ac7  pop     r15
0x180007ac9  pop     r14
0x180007acb  pop     r13
0x180007acd  pop     r12
0x180007acf  pop     rdi
0x180007ad0  pop     rsi
0x180007ad1  pop     rbp
0x180007ad2  retn
0x180007ad3  cmp     r15d, 7DDCh
0x180007ada  jnz     loc_1800079F9
0x180007ae0  cmp     edi, 17h
0x180007ae3  jnz     loc_1800079F9
0x180007ae9  mov     eax, [r12+30h]
0x180007aee  jmp     loc_180007BE8
0x180007af3  or      dword ptr [r13+68h], 1
0x180007af8  lea     rax, [r13+10h]
0x180007afc  movsd   qword ptr [r13+70h], xmm1
0x180007b02  cmp     [rax], rax
0x180007b05  jz      loc_180007D8F
0x180007b0b  mov     rcx, [r13+60h]; bstrString
0x180007b0f  test    rcx, rcx
0x180007b12  jz      loc_180007A1A
0x180007b18  call    cs:__imp_SysFreeString
0x180007b1e  xor     r9d, r9d
0x180007b21  mov     [r13+60h], r9
0x180007b25  jmp     loc_180007A1A
0x180007b2a  mov     rax, [r13+0C0h]
0x180007b31  sub     rax, [r12]
0x180007b35  jnz     short loc_180007B43
0x180007b37  mov     rax, [r13+0C8h]
0x180007b3e  sub     rax, [r12+8]
0x180007b43  test    rax, rax
0x180007b46  jnz     loc_1800077D4
0x180007b4c  mov     eax, [r12+10h]
0x180007b51  cmp     [r13+0D0h], eax
0x180007b58  jnz     loc_1800077D4
0x180007b5e  mov     eax, [r12+14h]
0x180007b63  cmp     [r13+0D4h], eax
0x180007b6a  jnz     loc_1800077D4
0x180007b70  mov     rax, [r13+0D8h]
0x180007b77  sub     rax, [r12+18h]
0x180007b7c  jnz     short loc_180007B8A
0x180007b7e  mov     rax, [r13+0E0h]
0x180007b85  sub     rax, [r12+20h]
0x180007b8a  test    rax, rax
0x180007b8d  jnz     loc_1800077D4
0x180007b93  mov     eax, [r12+28h]
0x180007b98  cmp     [r13+0E8h], eax
0x180007b9f  jnz     loc_1800077D4
0x180007ba5  mov     eax, [r12+2Ch]
0x180007baa  cmp     [r13+0ECh], eax
0x180007bb1  jmp     loc_1800077CE
0x180007bb6  mov     eax, r15d
0x180007bb9  sub     eax, 7DDCh
0x180007bbe  jz      loc_180007F11
0x180007bc4  cmp     eax, 1
0x180007bc7  jnz     loc_180007992
0x180007bcd  mov     r14d, [r9+18h]
0x180007bd1  lea     rdx, [rsp+118h+S]; S
0x180007bd6  mov     rcx, r12; Addr
0x180007bd9  call    cs:__imp_RtlIpv6AddressToStringW
0x180007bdf  jmp     loc_180007754
0x180007be4  mov     eax, [r12]
0x180007be8  mov     [r13+0BCh], eax
0x180007bef  jmp     loc_1800079F9
0x180007bf4  mov     ecx, 3
0x180007bf9  int     29h; Win8: RtlFailFast(ecx)
0x180007bfb  mov     rax, r8
0x180007bfe  sub     rax, rcx
0x180007c01  cmp     rax, 4C4B40h
0x180007c07  jle     loc_180007A9D
0x180007c0d  nop     dword ptr [rax]
0x180007c10  movzx   eax, word ptr [r13+40h]
0x180007c15  add     rcx, 989680h
0x180007c1c  mov     [r13+48h], rcx
0x180007c20  cmp     eax, [r14+23C0h]
0x180007c27  jnb     short loc_180007C31
0x180007c29  inc     ax
0x180007c2c  mov     [r13+40h], ax
0x180007c31  mov     rax, r8
0x180007c34  sub     rax, rcx
0x180007c37  cmp     rax, 4C4B40h
0x180007c3d  jg      short loc_180007C10
0x180007c3f  jmp     loc_180007A9D
0x180007c44  mov     eax, [r12+4]
0x180007c49  cmp     [r13+0C0h], eax
0x180007c50  jnz     loc_1800077D4
0x180007c56  mov     eax, [r12+8]
0x180007c5b  cmp     [r13+0C4h], eax
0x180007c62  jnz     loc_1800077D4
  ... truncated ...
```
