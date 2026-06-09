# WdcProcessMonitor::ResolveImageName(ushort const *,_WDC_PROCESS_INFO *)

- ea: `0x180025694`
- end: `0x180025d37`
- name: `?ResolveImageName@WdcProcessMonitor@@AEAAJPEBGPEAU_WDC_PROCESS_INFO@@@Z`
- size: `1699`
- prototype: `int(WdcProcessMonitor *__hidden this, const unsigned __int16 *, struct _WDC_PROCESS_INFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18000d4a0`

## callees

- `0x180006a80`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x18000e268`
- `0x180025694`
- `0x18007f8c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800257c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800257c3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180025a7e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180025a7e`
- `ADVAPI32!OpenSCManagerW` at `0x180025848`
- `ADVAPI32!OpenSCManagerW` at `0x180025848`
- `ADVAPI32!OpenServiceW` at `0x1800259dc`
- `ADVAPI32!OpenServiceW` at `0x1800259dc`
- `ADVAPI32!CloseServiceHandle` at `0x180025af3`
- `ADVAPI32!CloseServiceHandle` at `0x180025b05`
- `ADVAPI32!CloseServiceHandle` at `0x180025af3`
- `ADVAPI32!CloseServiceHandle` at `0x180025b05`
- `ADVAPI32!QueryServiceConfigW` at `0x180025a46`
- `ADVAPI32!QueryServiceConfigW` at `0x180025a46`
- `KERNEL32!GetLastError` at `0x18002585a`
- `KERNEL32!GetLastError` at `0x1800258d4`
- `KERNEL32!GetLastError` at `0x1800259f2`
- `KERNEL32!GetLastError` at `0x180025a50`
- `KERNEL32!GetLastError` at `0x18002585a`
- `KERNEL32!GetLastError` at `0x1800258d4`
- `KERNEL32!GetLastError` at `0x1800259f2`
- `KERNEL32!GetLastError` at `0x180025a50`
- `OLEAUT32!__imp_SysAllocString` at `0x180025744`
- `OLEAUT32!__imp_SysAllocString` at `0x1800257e3`
- `OLEAUT32!__imp_SysAllocString` at `0x180025bda`
- `OLEAUT32!__imp_SysAllocString` at `0x180025c61`
- `OLEAUT32!__imp_SysAllocString` at `0x180025cc2`
- `OLEAUT32!__imp_SysAllocString` at `0x180025744`
- `OLEAUT32!__imp_SysAllocString` at `0x1800257e3`
- `OLEAUT32!__imp_SysAllocString` at `0x180025bda`
- `OLEAUT32!__imp_SysAllocString` at `0x180025c61`
- `OLEAUT32!__imp_SysAllocString` at `0x180025cc2`
- `OLEAUT32!__imp_SysFreeString` at `0x180025737`
- `OLEAUT32!__imp_SysFreeString` at `0x1800257d6`
- `OLEAUT32!__imp_SysFreeString` at `0x180025bc9`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c54`
- `OLEAUT32!__imp_SysFreeString` at `0x180025cb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180025737`
- `OLEAUT32!__imp_SysFreeString` at `0x1800257d6`
- `OLEAUT32!__imp_SysFreeString` at `0x180025bc9`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c54`
- `OLEAUT32!__imp_SysFreeString` at `0x180025cb5`

## string_xrefs

- `0x18002583c`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall WdcProcessMonitor::ResolveImageName(
        WdcProcessMonitor *this,
        const unsigned __int16 *a2,
        struct _WDC_PROCESS_INFO *a3)
{
  const wchar_t **v3; // rsi
  void *v5; // r15
  WdcStringMap *v8; // rcx
  int v9; // eax
  signed int v10; // ebx
  OLECHAR *v11; // rcx
  OLECHAR *v12; // rbx
  BSTR v13; // rax
  _QWORD *v14; // rdi
  _QWORD *v15; // rax
  __int64 v16; // rcx
  OLECHAR *v17; // rcx
  BSTR v18; // rax
  _QWORD *v19; // rdi
  _QWORD *v20; // rax
  __int64 v21; // rcx
  unsigned __int16 *v22; // r12
  SC_HANDLE v23; // rax
  const char *v24; // rdx
  int v25; // r8d
  SC_HANDLE v26; // rbx
  signed int LastError; // eax
  const char *v28; // rdx
  int v29; // r8d
  signed int v30; // eax
  SC_HANDLE v31; // rax
  int v32; // eax
  unsigned int i; // edx
  OLECHAR *v34; // rax
  const char *v35; // rdx
  int v36; // r8d
  OLECHAR *v37; // rbx
  signed int v38; // eax
  struct _QUERY_SERVICE_CONFIGW *v39; // rax
  signed int v40; // eax
  wchar_t *v41; // rax
  wchar_t *v42; // rsi
  wchar_t *v43; // r8
  WdcStringMap *v44; // rcx
  int v46; // eax
  OLECHAR *v47; // rcx
  BSTR v48; // rax
  _QWORD *v49; // rdi
  _QWORD *v50; // rax
  __int64 v51; // rcx
  OLECHAR *v52; // rcx
  BSTR v53; // rax
  _QWORD *v54; // rdi
  _QWORD *v55; // rax
  __int64 v56; // rcx
  OLECHAR *v57; // rcx
  BSTR v58; // rax
  _QWORD *v59; // rdi
  _QWORD *v60; // rax
  __int64 v61; // rcx
  __int64 v62; // [rsp+20h] [rbp-40h]
  void *v63; // [rsp+30h] [rbp-30h] BYREF
  SC_HANDLE hSCManager; // [rsp+38h] [rbp-28h]
  OLECHAR *psz; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v66; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v67; // [rsp+50h] [rbp-10h] BYREF
  DWORD pcbBytesNeeded; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v69; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  v66 = 0x4000;
  v69 = 0;
  psz = 0;
  v67 = 0;
  v5 = 0;
  pcbBytesNeeded = 0;
  WdcProcessMonitor::ResolveImageDescription(this, a3);
  if ( 1.0 == *((double *)a3 + 14) )
  {
    v9 = WdcStringMap::LoadStringW(v8, 0x7E5Eu, &psz);
    v10 = v9;
    if ( v9 < 0 )
    {
      LODWORD(v62) = v9;
LABEL_4:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
        "WdcProcessMonitor::ResolveImageName",
        0,
        L"FAILURE: 0x%08x",
        v62);
      return (unsigned int)v10;
    }
    v11 = (OLECHAR *)*((_QWORD *)a3 + 12);
    v12 = psz;
    if ( v11 )
    {
      SysFreeString(v11);
      *((_QWORD *)a3 + 12) = 0;
    }
    v13 = SysAllocString(v12);
    if ( v12 && !v13 )
    {
LABEL_9:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      v10 = -2147024882;
      LODWORD(v62) = -2147024882;
      goto LABEL_4;
    }
    *((_QWORD *)a3 + 12) = v13;
    *((_DWORD *)a3 + 22) |= 1u;
    v14 = (_QWORD *)((char *)a3 + 16);
    if ( (_QWORD *)*v14 != v14 )
      return 0;
    v15 = (_QWORD *)((char *)this + 88);
    v16 = *((_QWORD *)this + 11);
    if ( *(WdcProcessMonitor **)(v16 + 8) == (WdcProcessMonitor *)((char *)this + 88) )
    {
      *v14 = v16;
      v14[1] = v15;
      *(_QWORD *)(v16 + 8) = v14;
      *v15 = v14;
      return 0;
    }
LABEL_112:
    __fastfail(3u);
  }
  if ( (unsigned int)_o__wcsicmp(a2, L"svchost.exe") )
  {
    v17 = (OLECHAR *)*((_QWORD *)a3 + 12);
    if ( v17 )
    {
      SysFreeString(v17);
      *((_QWORD *)a3 + 12) = 0;
    }
    v18 = SysAllocString(a2);
    if ( a2 && !v18 )
      goto LABEL_9;
    *((_QWORD *)a3 + 12) = v18;
    *((_DWORD *)a3 + 22) |= 1u;
    v10 = 0;
    v19 = (_QWORD *)((char *)a3 + 16);
    if ( (_QWORD *)*v19 != v19 )
      return (unsigned int)v10;
    v20 = (_QWORD *)((char *)this + 88);
    v21 = *((_QWORD *)this + 11);
    if ( *(WdcProcessMonitor **)(v21 + 8) == (WdcProcessMonitor *)((char *)this + 88) )
    {
      *v19 = v21;
      v19[1] = v20;
      *(_QWORD *)(v21 + 8) = v19;
      *v20 = v19;
      return (unsigned int)v10;
    }
    goto LABEL_112;
  }
  psz = 0;
  v22 = 0;
  v23 = OpenSCManagerW(0, L"ServicesActive", 4u);
  hSCManager = v23;
  v26 = v23;
  if ( !v23 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 >= 0 )
      {
LABEL_27:
        v26 = hSCManager;
        goto LABEL_28;
      }
    }
    else
    {
      v10 = -2147467259;
    }
    LODWORD(v62) = v10;
    goto LABEL_4;
  }
  if ( v23 == (SC_HANDLE)-1LL )
  {
    v30 = GetLastError();
    v10 = v30;
    if ( v30 )
    {
      if ( v30 > 0 )
        v10 = (unsigned __int16)v30 | 0x80070000;
      if ( v10 >= 0 )
        goto LABEL_27;
    }
    else
    {
      v10 = -2147467259;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcProcessMonitor::ResolveImageName",
      0,
      L"FAILURE: 0x%08x",
      v10);
    v31 = hSCManager;
LABEL_69:
    CloseServiceHandle(v31);
    goto LABEL_70;
  }
LABEL_28:
  v63 = WdcAlloc(0x4000u, v24, v25);
  v5 = v63;
  if ( !v63 )
  {
LABEL_29:
    v10 = -2147024882;
    LODWORD(v62) = -2147024882;
LABEL_30:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcProcessMonitor::ResolveImageName",
      0,
      L"FAILURE: 0x%08x",
      v62);
    goto LABEL_68;
  }
  v32 = WdcExpandingCall((int (*)(struct _WDC_EXPANDING_CALL *))WdcEnumServicesStatusEx, &v66, &v63, 2u, v26, &v69);
  v10 = v32;
  if ( v32 < 0 )
  {
    LODWORD(v62) = v32;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcProcessMonitor::ResolveImageName",
      0,
      L"FAILURE: 0x%08x",
      v62);
    v5 = v63;
    goto LABEL_68;
  }
  v5 = v63;
  if ( 56 * (unsigned __int64)v69 > v66 )
  {
    v10 = -2147418113;
    goto LABEL_68;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v69 )
      goto LABEL_103;
    if ( (double)*((int *)v63 + 14 * i + 11) == *((double *)a3 + 14) )
      break;
  }
  if ( i != -1 )
  {
    v34 = (OLECHAR *)OpenServiceW(hSCManager, *((LPCWSTR *)v63 + 7 * (int)i), 1u);
    psz = v34;
    v37 = v34;
    if ( !v34 || v34 == (OLECHAR *)-1LL )
    {
      v38 = GetLastError();
      v10 = v38;
      if ( v38 )
      {
        if ( v38 > 0 )
          v10 = (unsigned __int16)v38 | 0x80070000;
        if ( v10 >= 0 )
        {
          v37 = psz;
          goto LABEL_56;
        }
      }
      else
      {
        v10 = -2147467259;
      }
      LODWORD(v62) = v10;
      goto LABEL_30;
    }
LABEL_56:
    pcbBytesNeeded = 1024;
    v39 = (struct _QUERY_SERVICE_CONFIGW *)WdcAlloc(0x400u, v35, v36);
    v63 = v39;
    v3 = (const wchar_t **)v39;
    if ( !v39 )
      goto LABEL_29;
    if ( !QueryServiceConfigW((SC_HANDLE)v37, v39, pcbBytesNeeded, &pcbBytesNeeded) )
    {
      v40 = GetLastError();
      v10 = v40;
      if ( v40 )
      {
        if ( v40 > 0 )
          v10 = (unsigned __int16)v40 | 0x80070000;
        if ( v10 >= 0 )
          goto LABEL_62;
      }
      else
      {
        v10 = -2147467259;
      }
      LODWORD(v62) = v10;
      goto LABEL_30;
    }
LABEL_62:
    v41 = wcsstr(v3[2], L" -k ");
    v42 = v41;
    if ( v41 && (v43 = (wchar_t *)((char *)v63 + pcbBytesNeeded), v41 + 2 < v43) )
    {
      v22 = (unsigned __int16 *)WdcAlloc(0x400u, (const char *)v41 + 4, (int)v43);
      if ( !v22 )
      {
LABEL_65:
        v10 = -2147024882;
        LODWORD(v62) = -2147024882;
LABEL_66:
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
          "WdcProcessMonitor::ResolveImageName",
          0,
          L"FAILURE: 0x%08x",
          v62);
LABEL_67:
        v3 = (const wchar_t **)v63;
        goto LABEL_68;
      }
      *v22 = 0;
      v46 = WdcStringMap::LoadStringW(v44, 0x81B2u, &v67);
      v10 = v46;
      if ( v46 < 0 || (v46 = StringCchPrintfW(v22, 0x200u, v67, a2, v42 + 4), v10 = v46, v46 < 0) )
      {
        LODWORD(v62) = v46;
        goto LABEL_66;
      }
      v47 = (OLECHAR *)*((_QWORD *)a3 + 12);
      if ( v47 )
      {
        SysFreeString(v47);
        *((_QWORD *)a3 + 12) = 0;
      }
      v48 = SysAllocString(v22);
      if ( v48 )
      {
        *((_QWORD *)a3 + 12) = v48;
        *((_DWORD *)a3 + 22) |= 1u;
        v10 = 0;
        v49 = (_QWORD *)((char *)a3 + 16);
        if ( (_QWORD *)*v49 == v49 )
        {
          v50 = (_QWORD *)((char *)this + 88);
          v51 = *((_QWORD *)this + 11);
          if ( *(WdcProcessMonitor **)(v51 + 8) != (WdcProcessMonitor *)((char *)this + 88) )
            goto LABEL_112;
          *v49 = v51;
          v49[1] = v50;
          *(_QWORD *)(v51 + 8) = v49;
          *v50 = v49;
        }
        goto LABEL_67;
      }
    }
    else
    {
      v52 = (OLECHAR *)*((_QWORD *)a3 + 12);
      if ( v52 )
      {
        SysFreeString(v52);
        *((_QWORD *)a3 + 12) = 0;
      }
      v53 = SysAllocString(a2);
      if ( !a2 || v53 )
      {
        *((_QWORD *)a3 + 12) = v53;
        *((_DWORD *)a3 + 22) |= 1u;
        v54 = (_QWORD *)((char *)a3 + 16);
        if ( (_QWORD *)*v54 == v54 )
        {
          v55 = (_QWORD *)((char *)this + 88);
          v56 = *((_QWORD *)this + 11);
          if ( *(WdcProcessMonitor **)(v56 + 8) != (WdcProcessMonitor *)((char *)this + 88) )
            goto LABEL_112;
          *v54 = v56;
          v54[1] = v55;
          *(_QWORD *)(v56 + 8) = v54;
          *v55 = v54;
        }
        v10 = 0;
        goto LABEL_67;
      }
    }
    LODWORD(v62) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", v62);
    goto LABEL_65;
  }
LABEL_103:
  v57 = (OLECHAR *)*((_QWORD *)a3 + 12);
  if ( v57 )
  {
    SysFreeString(v57);
    *((_QWORD *)a3 + 12) = 0;
  }
  v58 = SysAllocString(a2);
  if ( a2 && !v58 )
  {
    LODWORD(v62) = -2147024882;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", v62);
    goto LABEL_29;
  }
  *((_QWORD *)a3 + 12) = v58;
  *((_DWORD *)a3 + 22) |= 1u;
  v59 = (_QWORD *)((char *)a3 + 16);
  if ( (_QWORD *)*v59 == v59 )
  {
    v60 = (_QWORD *)((char *)this + 88);
    v61 = *((_QWORD *)this + 11);
    if ( *(WdcProcessMonitor **)(v61 + 8) != (WdcProcessMonitor *)((char *)this + 88) )
      goto LABEL_112;
    *v59 = v61;
    v59[1] = v60;
    *(_QWORD *)(v61 + 8) = v59;
    *v60 = v59;
  }
  v10 = 0;
LABEL_68:
  v31 = hSCManager;
  if ( hSCManager )
    goto LABEL_69;
LABEL_70:
  if ( psz )
    CloseServiceHandle((SC_HANDLE)psz);
  if ( v3 )
    WdcFree(v3, v28, v29);
  if ( v5 )
    WdcFree(v5, v28, v29);
  if ( v22 )
    WdcFree(v22, v28, v29);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180025694  mov     [rsp-38h+arg_0], rbx
0x180025699  push    rbp
0x18002569a  push    rsi
0x18002569b  push    rdi
0x18002569c  push    r12
0x18002569e  push    r13
0x1800256a0  push    r14
0x1800256a2  push    r15
0x1800256a4  mov     rbp, rsp
0x1800256a7  sub     rsp, 60h
0x1800256ab  xor     esi, esi
0x1800256ad  mov     [rbp+var_18], 4000h
0x1800256b5  mov     r14, rdx
0x1800256b8  mov     [rbp+arg_18], esi
0x1800256bb  mov     rdx, r8; struct _WDC_PROCESS_INFO *
0x1800256be  mov     [rbp+psz], rsi
0x1800256c2  mov     [rbp+var_10], rsi
0x1800256c6  mov     r15d, esi
0x1800256c9  mov     [rbp+pcbBytesNeeded], esi
0x1800256cc  mov     rdi, r8
0x1800256cf  mov     r13, rcx
0x1800256d2  call    ?ResolveImageDescription@WdcProcessMonitor@@AEAAJPEAU_WDC_PROCESS_INFO@@@Z; WdcProcessMonitor::ResolveImageDescription(_WDC_PROCESS_INFO *)
0x1800256d7  movsd   xmm0, cs:__real@3ff0000000000000
0x1800256df  ucomisd xmm0, qword ptr [rdi+70h]
0x1800256e4  jp      loc_1800257B9
0x1800256ea  jnz     loc_1800257B9
0x1800256f0  lea     r8, [rbp+psz]; unsigned __int16 **
0x1800256f4  mov     edx, 7E5Eh; unsigned int
0x1800256f9  call    ?LoadStringW@WdcStringMap@@QEAAJKPEAPEAG@Z; WdcStringMap::LoadStringW(ulong,ushort * *)
0x1800256fe  mov     ebx, eax
0x180025700  test    eax, eax
0x180025702  jns     short loc_18002572A
0x180025704  mov     dword ptr [rsp+60h+var_40], eax
0x180025708  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002570f  xor     r8d, r8d; int
0x180025712  lea     rdx, aWdcprocessmoni_3; "WdcProcessMonitor::ResolveImageName"
0x180025719  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x180025720  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180025725  jmp     loc_180025B32
0x18002572a  mov     rcx, [rdi+60h]; bstrString
0x18002572e  mov     rbx, [rbp+psz]
0x180025732  test    rcx, rcx
0x180025735  jz      short loc_180025741
0x180025737  call    cs:__imp_SysFreeString
0x18002573d  mov     [rdi+60h], rsi
0x180025741  mov     rcx, rbx; psz
0x180025744  call    cs:__imp_SysAllocString
0x18002574a  test    rbx, rbx
0x18002574d  jz      short loc_180025782
0x18002574f  test    rax, rax
0x180025752  jnz     short loc_180025782
0x180025754  mov     edi, 8007000Eh
0x180025759  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180025760  xor     r8d, r8d; int
0x180025763  mov     dword ptr [rsp+60h+var_40], edi
0x180025767  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18002576e  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180025775  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002577a  mov     ebx, edi
0x18002577c  mov     dword ptr [rsp+60h+var_40], edi
0x180025780  jmp     short loc_180025708
0x180025782  mov     [rdi+60h], rax
0x180025786  or      dword ptr [rdi+58h], 1
0x18002578a  add     rdi, 10h
0x18002578e  cmp     [rdi], rdi
0x180025791  jnz     short loc_1800257B2
0x180025793  lea     rax, [r13+58h]
0x180025797  mov     rcx, [rax]
0x18002579a  cmp     [rcx+8], rax
0x18002579e  jnz     loc_180025D30
0x1800257a4  mov     [rdi], rcx
0x1800257a7  mov     [rdi+8], rax
0x1800257ab  mov     [rcx+8], rdi
0x1800257af  mov     [rax], rdi
0x1800257b2  mov     ebx, esi
0x1800257b4  jmp     loc_180025B32
0x1800257b9  lea     rdx, aSvchostExe; "svchost.exe"
0x1800257c0  mov     rcx, r14
0x1800257c3  call    cs:__imp__o__wcsicmp
0x1800257c9  test    eax, eax
0x1800257cb  jz      short loc_180025832
0x1800257cd  mov     rcx, [rdi+60h]; bstrString
0x1800257d1  test    rcx, rcx
0x1800257d4  jz      short loc_1800257E0
0x1800257d6  call    cs:__imp_SysFreeString
0x1800257dc  mov     [rdi+60h], rsi
0x1800257e0  mov     rcx, r14; psz
0x1800257e3  call    cs:__imp_SysAllocString
0x1800257e9  test    r14, r14
0x1800257ec  jz      short loc_1800257F7
0x1800257ee  test    rax, rax
0x1800257f1  jz      loc_180025754
0x1800257f7  mov     [rdi+60h], rax
0x1800257fb  or      dword ptr [rdi+58h], 1
0x1800257ff  mov     ebx, esi
0x180025801  add     rdi, 10h
0x180025805  cmp     [rdi], rdi
0x180025808  jnz     loc_180025B32
0x18002580e  lea     rax, [r13+58h]
0x180025812  mov     rcx, [rax]
0x180025815  cmp     [rcx+8], rax
0x180025819  jnz     loc_180025D30
0x18002581f  mov     [rdi], rcx
0x180025822  mov     [rdi+8], rax
0x180025826  mov     [rcx+8], rdi
0x18002582a  mov     [rax], rdi
0x18002582d  jmp     loc_180025B32
0x180025832  mov     r8d, 4; dwDesiredAccess
0x180025838  mov     [rbp+psz], rsi
0x18002583c  lea     rdx, DatabaseName; "ServicesActive"
0x180025843  xor     ecx, ecx; lpMachineName
0x180025845  mov     r12, rsi
0x180025848  call    cs:__imp_OpenSCManagerW
0x18002584e  mov     [rbp+hSCManager], rax
0x180025852  mov     rbx, rax
0x180025855  test    rax, rax
0x180025858  jnz     short loc_1800258CE
0x18002585a  call    cs:__imp_GetLastError
0x180025860  mov     ebx, eax
0x180025862  test    eax, eax
0x180025864  jz      short loc_1800258C0
0x180025866  jle     short loc_180025871
0x180025868  movzx   ebx, ax
0x18002586b  or      ebx, 80070000h
0x180025871  test    ebx, ebx
0x180025873  js      short loc_1800258C5
0x180025875  mov     rbx, [rbp+hSCManager]
0x180025879  mov     ecx, 4000h; dwBytes
0x18002587e  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180025883  mov     [rbp+var_30], rax
0x180025887  mov     r15, rax
0x18002588a  test    rax, rax
0x18002588d  jnz     loc_180025920
0x180025893  mov     edi, 8007000Eh
0x180025898  mov     ebx, edi
0x18002589a  mov     dword ptr [rsp+60h+var_40], edi
0x18002589e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800258a5  xor     r8d, r8d; int
0x1800258a8  lea     rdx, aWdcprocessmoni_3; "WdcProcessMonitor::ResolveImageName"
0x1800258af  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x1800258b6  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800258bb  jmp     loc_180025AE7
0x1800258c0  mov     ebx, 80004005h
0x1800258c5  mov     dword ptr [rsp+60h+var_40], ebx
0x1800258c9  jmp     loc_180025708
0x1800258ce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800258d2  jnz     short loc_180025879
0x1800258d4  call    cs:__imp_GetLastError
0x1800258da  mov     ebx, eax
0x1800258dc  test    eax, eax
0x1800258de  jz      short loc_1800258F1
0x1800258e0  jle     short loc_1800258EB
0x1800258e2  movzx   ebx, ax
0x1800258e5  or      ebx, 80070000h
0x1800258eb  test    ebx, ebx
0x1800258ed  jns     short loc_180025875
0x1800258ef  jmp     short loc_1800258F6
0x1800258f1  mov     ebx, 80004005h
0x1800258f6  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800258fd  mov     dword ptr [rsp+60h+var_40], ebx
0x180025901  xor     r8d, r8d; int
0x180025904  lea     rdx, aWdcprocessmoni_3; "WdcProcessMonitor::ResolveImageName"
0x18002590b  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x180025912  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180025917  mov     rax, [rbp+hSCManager]
0x18002591b  jmp     loc_180025AF0
0x180025920  lea     rax, [rbp+arg_18]
0x180025924  mov     r9d, 2; unsigned int
0x18002592a  mov     [rsp+60h+var_38], rax
0x18002592f  lea     r8, [rbp+var_30]; void **
0x180025933  lea     rdx, [rbp+var_18]; unsigned __int64 *
0x180025937  mov     [rsp+60h+var_40], rbx
0x18002593c  lea     rcx, ?WdcEnumServicesStatusEx@@YAJPEAU_WDC_EXPANDING_CALL@@@Z; int (*)(struct _WDC_EXPANDING_CALL *)
0x180025943  call    ?WdcExpandingCall@@YAJP6AJPEAU_WDC_EXPANDING_CALL@@@ZPEA_KPEAPEAXKZZ; WdcExpandingCall(long (*)(_WDC_EXPANDING_CALL *),unsigned __int64 *,void * *,ulong,...)
0x180025948  mov     ebx, eax
0x18002594a  test    eax, eax
0x18002594c  jns     short loc_180025978
0x18002594e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180025955  mov     dword ptr [rsp+60h+var_40], eax
0x180025959  xor     r8d, r8d; int
0x18002595c  lea     rdx, aWdcprocessmoni_3; "WdcProcessMonitor::ResolveImageName"
0x180025963  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18002596a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002596f  mov     r15, [rbp+var_30]
0x180025973  jmp     loc_180025AE7
0x180025978  mov     eax, [rbp+arg_18]
0x18002597b  mov     r15, [rbp+var_30]
0x18002597f  imul    rcx, rax, 38h ; '8'
0x180025983  cmp     rcx, [rbp+var_18]
0x180025987  jbe     short loc_180025993
0x180025989  mov     ebx, 8000FFFFh
0x18002598e  jmp     loc_180025AE7
0x180025993  xor     edx, edx
0x180025995  cmp     edx, [rbp+arg_18]
0x180025998  jnb     loc_180025CAC
0x18002599e  mov     eax, edx
0x1800259a0  xorps   xmm0, xmm0
0x1800259a3  imul    rcx, rax, 38h ; '8'
0x1800259a7  mov     eax, [rcx+r15+2Ch]
0x1800259ac  cvtsi2sd xmm0, rax
0x1800259b1  ucomisd xmm0, qword ptr [rdi+70h]
0x1800259b6  jp      short loc_1800259BA
0x1800259b8  jz      short loc_1800259BE
0x1800259ba  inc     edx
0x1800259bc  jmp     short loc_180025995
0x1800259be  cmp     edx, 0FFFFFFFFh
0x1800259c1  jz      loc_180025CAC
0x1800259c7  mov     rcx, [rbp+hSCManager]; hSCManager
0x1800259cb  mov     r8d, 1; dwDesiredAccess
0x1800259d1  movsxd  rax, edx
0x1800259d4  imul    rdx, rax, 38h ; '8'
0x1800259d8  mov     rdx, [rdx+r15]; lpServiceName
0x1800259dc  call    cs:__imp_OpenServiceW
0x1800259e2  mov     [rbp+psz], rax
0x1800259e6  mov     rbx, rax
0x1800259e9  test    rax, rax
0x1800259ec  jnz     loc_180025B5A
0x1800259f2  call    cs:__imp_GetLastError
0x1800259f8  mov     ebx, eax
0x1800259fa  test    eax, eax
0x1800259fc  jz      loc_180025B4C
0x180025a02  jle     short loc_180025A0D
0x180025a04  movzx   ebx, ax
0x180025a07  or      ebx, 80070000h
0x180025a0d  test    ebx, ebx
0x180025a0f  js      loc_180025B51
0x180025a15  mov     rbx, [rbp+psz]
0x180025a19  mov     eax, 400h
0x180025a1e  mov     ecx, eax; dwBytes
0x180025a20  mov     [rbp+pcbBytesNeeded], eax
0x180025a23  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180025a28  mov     [rbp+var_30], rax
0x180025a2c  mov     rsi, rax
0x180025a2f  test    rax, rax
0x180025a32  jz      loc_180025893
0x180025a38  mov     r8d, [rbp+pcbBytesNeeded]; cbBufSize
0x180025a3c  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x180025a40  mov     rdx, rax; lpServiceConfig
0x180025a43  mov     rcx, rbx; hService
0x180025a46  call    cs:__imp_QueryServiceConfigW
0x180025a4c  test    eax, eax
0x180025a4e  jnz     short loc_180025A73
0x180025a50  call    cs:__imp_GetLastError
0x180025a56  mov     ebx, eax
0x180025a58  test    eax, eax
0x180025a5a  jz      loc_180025B69
0x180025a60  jle     short loc_180025A6B
0x180025a62  movzx   ebx, ax
0x180025a65  or      ebx, 80070000h
0x180025a6b  test    ebx, ebx
0x180025a6d  js      loc_180025B6E
0x180025a73  mov     rcx, [rsi+10h]; Str
0x180025a77  lea     rdx, aK; " -k "
0x180025a7e  call    cs:__imp_wcsstr
0x180025a84  mov     rsi, rax
0x180025a87  test    rax, rax
0x180025a8a  jz      loc_180025C4B
0x180025a90  mov     r8d, [rbp+pcbBytesNeeded]
0x180025a94  lea     rdx, [rax+4]; char *
0x180025a98  add     r8, [rbp+var_30]; int
0x180025a9c  cmp     rdx, r8
0x180025a9f  jnb     loc_180025C4B
0x180025aa5  mov     ecx, 400h; dwBytes
0x180025aaa  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180025aaf  mov     r12, rax
0x180025ab2  test    rax, rax
0x180025ab5  jnz     loc_180025B79
0x180025abb  mov     edi, 8007000Eh
0x180025ac0  mov     ebx, edi
0x180025ac2  mov     dword ptr [rsp+60h+var_40], edi
0x180025ac6  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180025acd  xor     r8d, r8d; int
0x180025ad0  lea     rdx, aWdcprocessmoni_3; "WdcProcessMonitor::ResolveImageName"
0x180025ad7  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x180025ade  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180025ae3  mov     rsi, [rbp+var_30]
0x180025ae7  mov     rax, [rbp+hSCManager]
0x180025aeb  test    rax, rax
0x180025aee  jz      short loc_180025AF9
0x180025af0  mov     rcx, rax; hSCObject
0x180025af3  call    cs:__imp_CloseServiceHandle
0x180025af9  mov     rax, [rbp+psz]
0x180025afd  test    rax, rax
0x180025b00  jz      short loc_180025B0B
0x180025b02  mov     rcx, rax; hSCObject
0x180025b05  call    cs:__imp_CloseServiceHandle
0x180025b0b  test    rsi, rsi
0x180025b0e  jz      short loc_180025B18
0x180025b10  mov     rcx, rsi; void *
0x180025b13  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180025b18  test    r15, r15
0x180025b1b  jz      short loc_180025B25
0x180025b1d  mov     rcx, r15; void *
0x180025b20  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180025b25  test    r12, r12
0x180025b28  jz      short loc_180025B32
0x180025b2a  mov     rcx, r12; void *
0x180025b2d  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180025b32  mov     eax, ebx
0x180025b34  mov     rbx, [rsp+60h+arg_0]
  ... truncated ...
```
