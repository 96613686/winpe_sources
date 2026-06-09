# CControlPanelTasks::_LoadAppletTasksFromXml(IXmlReader *,ushort const *)

- ea: `0x18019be80`
- end: `0x18019c706`
- name: `?_LoadAppletTasksFromXml@CControlPanelTasks@@AEAAJPEAUIXmlReader@@PEBG@Z`
- size: `2182`
- prototype: `int(CControlPanelTasks *__hidden this, struct IXmlReader *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180144f5c`

## callees

- `0x18000f5a4`
- `0x18001bf10`
- `0x18001f630`
- `0x1800208d8`
- `0x1800426e8`
- `0x180083dec`
- `0x1800843fc`
- `0x1800e90ac`
- `0x180125884`
- `0x180139e5c`
- `0x18019be80`
- `0x1801ca654`
- `0x1801d606c`
- `0x1801d796c`
- `0x180233280`
- `0x180233a7c`
- `0x1802342fc`
- `0x18040cd14`
- `0x18040d29c`
- `0x18040dacc`
- `0x18040db48`
- `0x18040dc84`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c07b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c0fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c137`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c1bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c316`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c36c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c3c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c536`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c07b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c0fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c137`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c1bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c316`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c36c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c3c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18019c536`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18019c186`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18019c212`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18019c258`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18019c186`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18019c212`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18019c258`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18019c34d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18019c34d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c601`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c6c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c601`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019c6c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019bf3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019bf3f`
- `SHCORE!__imp_GUIDFromStringW` at `0x18019bec9`
- `SHCORE!__imp_GUIDFromStringW` at `0x18019c016`
- `SHCORE!__imp_GUIDFromStringW` at `0x18019bec9`
- `SHCORE!__imp_GUIDFromStringW` at `0x18019c016`

## string_xrefs

- `0x18019c307`: `command`
- `0x18019c346`: `%windir%\system32\msdt.exe`
- `0x18019c35e`: `%windir%\system32\msdt.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CControlPanelTasks::_LoadAppletTasksFromXml(
        HDSA *this,
        struct IXmlReader *a2,
        const unsigned __int16 *a3)
{
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  HDSA *v8; // rdi
  unsigned __int16 *v9; // rsi
  CControlPanelTasks *v10; // rcx
  int Element; // eax
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r12
  int v15; // edi
  __int64 v16; // rdx
  int v17; // eax
  char v18; // cl
  char v19; // r13
  CControlPanelTasks *v20; // rcx
  bool v21; // r15
  CControlPanelTasks *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  LPVOID *p_pv; // r9
  WCHAR *v26; // r8
  CControlPanelTasks *v27; // rcx
  __int64 v28; // r15
  HRESULT v29; // edi
  CControlPanelTasks *v30; // rcx
  int v31; // r15d
  int v32; // r12d
  CControlPanelTasks *v33; // rcx
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  CControlPanelTasks *v40; // rcx
  int v41; // eax
  CControlPanelTasks *v42; // rcx
  int CategoryTasks; // r14d
  int v45; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v46; // [rsp+38h] [rbp-C8h] BYREF
  HDSA *v47; // [rsp+40h] [rbp-C0h]
  HDSA *v48; // [rsp+48h] [rbp-B8h]
  LPCWCH lpString1[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD pitem[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v51; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v52; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  struct ITaskCondition *v54; // [rsp+98h] [rbp-68h] BYREF
  char v55; // [rsp+A0h] [rbp-60h]
  char v56; // [rsp+A1h] [rbp-5Fh]
  __int128 v57; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v58[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-10h]
  __int128 v60; // [rsp+100h] [rbp+0h] BYREF
  __int64 v61; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v62[104]; // [rsp+118h] [rbp+18h] BYREF
  WCHAR pszOutBuf[520]; // [rsp+180h] [rbp+80h] BYREF

  v47 = this;
  v57 = 0;
  if ( !(unsigned int)GUIDFromStringW(a3, &v57, a3) )
    return (unsigned int)-2147467259;
  v8 = this + 13;
  v48 = this + 13;
  if ( (unsigned int)CDSA_Base<APPLETTASKS>::Search((int)this + 104, v5, v6, v7, (__int64)&v57) != -1 )
    return (unsigned int)-2147467259;
  v61 = 0;
  `eh vector constructor iterator'(
    v62,
    8u,
    0xCu,
    (void (*)(void *))CDSA<MENUIDMAP>::`default constructor closure',
    (void (*)(void *))tip2::details::merged_data<_tip_BackupWallpaperCreationTest,_tip_BackupWallpaperCreationTest>::on_result);
  v60 = v57;
  v45 = 2560;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(0x1400u);
  v46 = v9;
  while ( 1 )
  {
    Element = CPL_MoveToNextElement(a2, L"task");
    if ( Element >= 0 )
      break;
    if ( CControlPanelTasks::_ReachedCategoryOrEndElement(v10, a2, L"application") >= 0 )
      goto LABEL_94;
  }
  if ( !Element )
  {
    while ( 1 )
    {
      if ( v9 )
        *v9 = 0;
      if ( !((unsigned int (__fastcall *)(struct IXmlReader *, const WCHAR *, _QWORD))a2->lpVtbl->MoveToAttributeByName)(
              a2,
              L"id",
              0) )
      {
        lpString1[0] = 0;
        v12 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWCH *, _QWORD))a2->lpVtbl->GetValue)(a2, lpString1, 0);
        if ( v12 >= 0 )
          break;
      }
LABEL_91:
      while ( 1 )
      {
        v41 = CPL_MoveToNextElement(a2, L"task");
        if ( v41 >= 0 )
          break;
        if ( CControlPanelTasks::_ReachedCategoryOrEndElement(v10, a2, L"application") >= 0 )
          goto LABEL_93;
      }
      if ( v41 )
      {
LABEL_93:
        v8 = v48;
        goto LABEL_94;
      }
    }
    if ( !v61 )
    {
      if ( (unsigned int)CDSA_Base<tagTASKWITHOVERRIDE>::Create(&v61) )
        goto LABEL_15;
      v12 = -2147024882;
    }
    if ( v12 < 0 )
      goto LABEL_91;
LABEL_15:
    memset_0(pitem, 0, 0x60u);
    if ( !(unsigned int)GUIDFromStringW(lpString1[0], pitem, v13) )
      goto LABEL_89;
    LODWORD(v14) = 0;
    v15 = 0;
    if ( !((unsigned int (__fastcall *)(struct IXmlReader *, const wchar_t *, _QWORD))a2->lpVtbl->MoveToAttributeByName)(
            a2,
            L"needsElevation",
            0) )
    {
      v15 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWCH *, _QWORD))a2->lpVtbl->GetValue)(a2, lpString1, 0);
      v17 = CompareStringOrdinal(lpString1[0], -1, L"true", -1, 1);
      v18 = v56;
      if ( v17 == 2 )
        v18 = 1;
      v56 = v18;
    }
    v19 = 0;
    if ( v15 < 0 )
      goto LABEL_89;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v19 )
          goto LABEL_79;
        if ( CPL_MoveToNextElement(a2, 0) )
          goto LABEL_78;
        v21 = CControlPanelTasks::_ReachedEndElement(v20, a2);
        v15 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWCH *, _QWORD))a2->lpVtbl->GetLocalName)(
                a2,
                lpString1,
                0);
        if ( v15 < 0 )
          goto LABEL_89;
        if ( CompareStringOrdinal(lpString1[0], -1, L"task", -1, 1) != 2 )
          break;
        if ( v21 )
        {
          v19 = 1;
        }
        else
        {
          v15 = -2147467259;
LABEL_77:
          if ( v15 < 0 )
          {
LABEL_78:
            if ( v15 >= 0 )
            {
LABEL_79:
              if ( v51
                && pv
                && *(_WORD *)v51
                && *(_WORD *)pv
                && (!v9 || !*v9 || (int)_AllocString<CTCoAllocPolicy>(v51, v16, v9, &v52) >= 0) )
              {
                pitem[1] = v57;
                if ( DSA_InsertItem(*v47, 0x7FFFFFFF, pitem) != -1 )
                {
                  v58[1] = 0;
                  v59 = 0;
                  v58[0] = pitem[0];
                  if ( (int)CDSA_Base<GROUP_ITEM_ENTRY>::AppendItem(&v61, v58) >= 0 )
                    goto LABEL_91;
                }
                CoTaskMemFree(v52);
              }
            }
LABEL_89:
            SafeRelease<IUpdatableItemSet>(&v54);
            CoTaskMemFree(v51);
            CoTaskMemFree(pv);
            goto LABEL_91;
          }
        }
      }
      if ( CompareStringOrdinal(lpString1[0], -1, L"name", -1, 1) == 2 && !v21 )
        break;
      if ( CompareStringOrdinal(lpString1[0], -1, L"keywords", -1, 1) == 2 && !v21 && v9 )
      {
        if ( (int)CControlPanelTasks::_GetElementText(v27, a2, lpString1) < 0 )
          goto LABEL_89;
        v28 = (int)v14;
        v29 = SHLoadIndirectString(lpString1[0], &v9[v28], v45 - v14, 0);
        if ( v29 < 0 )
        {
          while ( (unsigned int)ResultFromKnownLastError() == -2147024774 )
          {
            v29 = CControlPanelTasks::_IncreaseTaskKeywordsBuffer(v30, &v46, &v45);
            v9 = v46;
            if ( v29 >= 0 )
            {
              v29 = SHLoadIndirectString(lpString1[0], &v46[v28], v45 - v14, 0);
              if ( v29 >= 0 )
                break;
            }
          }
          if ( v29 < 0 )
            goto LABEL_89;
        }
        v14 = -1;
        do
          ++v14;
        while ( v9[v14] );
        if ( (int)v14 > 0 && v9[(int)v14 - 1] != 59 )
        {
          v31 = v14 + 1;
          v32 = v45;
          if ( v45 < v31 )
          {
            v29 = CControlPanelTasks::_IncreaseTaskKeywordsBuffer((CControlPanelTasks *)0x3B, &v46, &v45);
            v9 = v46;
            v32 = v45;
          }
          if ( v29 < 0 || (int)StringCchCatW(v9, v32, L";") < 0 )
            goto LABEL_89;
          LODWORD(v14) = v31;
        }
LABEL_60:
        v35 = CPL_MoveToNextElement(a2, 0);
LABEL_73:
        v15 = v35;
        goto LABEL_77;
      }
      if ( CompareStringOrdinal(lpString1[0], -1, L"command", -1, 1) == 2 && !v21 )
      {
        if ( (int)CControlPanelTasks::_GetElementText(v33, a2, lpString1) < 0 )
          goto LABEL_89;
        v34 = lstrlenW(L"%windir%\\system32\\msdt.exe");
        if ( CompareStringOrdinal(lpString1[0], v34, L"%windir%\\system32\\msdt.exe", v34, 1) == 2 )
        {
          v26 = L"%SystemRoot%\\explorer.exe ms-settings:troubleshoot";
          lpString1[0] = L"%SystemRoot%\\explorer.exe ms-settings:troubleshoot";
          v56 = 0;
        }
        else
        {
          v26 = (WCHAR *)lpString1[0];
        }
        p_pv = &pv;
LABEL_59:
        if ( (int)_AllocString<CTCoAllocPolicy>(v24, v23, v26, p_pv) < 0 )
          goto LABEL_89;
        goto LABEL_60;
      }
      if ( CompareStringOrdinal(lpString1[0], -1, L"controlpanel", -1, 1) == 2 )
      {
        if ( !pv || !*(_WORD *)pv )
        {
          v15 = ((__int64 (__fastcall *)(struct IXmlReader *, const WCHAR *, _QWORD))a2->lpVtbl->MoveToAttributeByName)(
                  a2,
                  L"name",
                  0);
          if ( v15 )
            goto LABEL_77;
          if ( ((int (__fastcall *)(struct IXmlReader *, LPCWCH *, _QWORD))a2->lpVtbl->GetValue)(a2, lpString1, 0) < 0
            || (int)_AllocString<CTCoAllocPolicy>(v37, v36, lpString1[0], &pv) < 0 )
          {
            goto LABEL_89;
          }
          v55 = 1;
          v15 = ((__int64 (__fastcall *)(struct IXmlReader *, const wchar_t *, _QWORD))a2->lpVtbl->MoveToAttributeByName)(
                  a2,
                  L"page",
                  0);
          if ( v15 )
            goto LABEL_77;
          if ( ((int (__fastcall *)(struct IXmlReader *, LPCWCH *, _QWORD))a2->lpVtbl->GetValue)(a2, lpString1, 0) < 0 )
            goto LABEL_89;
          memset_0(pszOutBuf, 0, sizeof(pszOutBuf));
          if ( (int)StringCchCopyW(pszOutBuf, 0x208u, (const unsigned __int16 *)pv) < 0
            || (int)StringCchCatW(pszOutBuf, 0x208u, L"\\") < 0
            || (int)StringCchCatW(pszOutBuf, 0x208u, lpString1[0]) < 0 )
          {
            goto LABEL_89;
          }
          CoTaskMemFree(pv);
          v35 = _AllocString<CTCoAllocPolicy>(v39, v38, pszOutBuf, &pv);
          goto LABEL_73;
        }
      }
      else if ( CompareStringOrdinal(lpString1[0], -1, L"conditions", -1, 1) == 2 && !v21 )
      {
        v15 = CControlPanelTasks::_LoadTaskCondition(v40, a2, &v54);
        goto LABEL_77;
      }
    }
    if ( (int)CControlPanelTasks::_GetElementText(v22, a2, lpString1) < 0 )
      goto LABEL_89;
    memset_0(pszOutBuf, 0, 0xF0u);
    if ( SHLoadIndirectString(lpString1[0], pszOutBuf, 0x78u, 0) < 0 )
      goto LABEL_89;
    p_pv = &v51;
    v26 = pszOutBuf;
    goto LABEL_59;
  }
LABEL_94:
  CategoryTasks = CControlPanelTasks::_LoadCategoryTasks(v10, a2, L"application", v62);
  if ( CategoryTasks < 0 )
    goto LABEL_98;
  if ( DSA_InsertItem(*v8, 0x7FFFFFFF, &v60) == -1 )
  {
    CategoryTasks = -2147024882;
LABEL_98:
    CControlPanelTasks::_APPLETTASKS_Destroy(v42, (struct APPLETTASKS *)&v60);
    goto LABEL_99;
  }
  CategoryTasks = 0;
  v61 = 0;
  memset_0(v62, 0, 0x60u);
LABEL_99:
  if ( v9 )
    CoTaskMemFree(v9);
  APPLETTASKS::~APPLETTASKS((APPLETTASKS *)&v60);
  return (unsigned int)CategoryTasks;
}

```

## disassembly

```asm
0x18019be80  mov     [rsp-8+arg_18], rbx
0x18019be85  push    rbp
0x18019be86  push    rsi
0x18019be87  push    rdi
0x18019be88  push    r12
0x18019be8a  push    r13
0x18019be8c  push    r14
0x18019be8e  push    r15
0x18019be90  lea     rbp, [rsp-4A0h]
0x18019be98  sub     rsp, 5A0h
0x18019be9f  mov     rax, cs:__security_cookie
0x18019bea6  xor     rax, rsp
0x18019bea9  mov     [rbp+4D0h+var_40], rax
0x18019beb0  mov     rbx, rdx
0x18019beb3  mov     r15, rcx
0x18019beb6  mov     [rsp+5D0h+var_590], rcx
0x18019bebb  xorps   xmm0, xmm0
0x18019bebe  movups  [rbp+4D0h+var_510], xmm0
0x18019bec2  lea     rdx, [rbp+4D0h+var_510]
0x18019bec6  mov     rcx, r8
0x18019bec9  call    cs:__imp_GUIDFromStringW
0x18019becf  test    eax, eax
0x18019bed1  jz      loc_18019C6D3
0x18019bed7  lea     rdi, [r15+68h]
0x18019bedb  mov     [rsp+5D0h+var_588], rdi
0x18019bee0  lea     rax, [rbp+4D0h+var_510]
0x18019bee4  mov     qword ptr [rsp+5D0h+bIgnoreCase], rax
0x18019bee9  mov     rcx, rdi
0x18019beec  call    ?Search@?$CDSA_Base@UAPPLETTASKS@@@@QEBAHPEBUAPPLETTASKS@@HP6AH00_J@Z1I@Z; CDSA_Base<APPLETTASKS>::Search(APPLETTASKS const *,int,int (*)(APPLETTASKS const *,APPLETTASKS const *,__int64),__int64,uint)
0x18019bef1  cmp     eax, 0FFFFFFFFh
0x18019bef4  jnz     loc_18019C6D3
0x18019befa  xor     r15d, r15d
0x18019befd  mov     [rbp+4D0h+var_4C0], r15
0x18019bf01  lea     rax, ?on_result@?$merged_data@U_tip_BackupWallpaperCreationTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_BackupWallpaperCreationTest,_tip_BackupWallpaperCreationTest>::on_result(TipReportingInfo const &)
0x18019bf08  mov     qword ptr [rsp+5D0h+bIgnoreCase], rax; void (*)(void *)
0x18019bf0d  lea     r9, ??_F?$CDSA@UMENUIDMAP@@@@QEAAXXZ; void (*)(void *)
0x18019bf14  lea     edx, [r15+8]; unsigned __int64
0x18019bf18  lea     r8d, [r15+0Ch]; unsigned __int64
0x18019bf1c  lea     rcx, [rbp+4D0h+var_4B8]; void *
0x18019bf20  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18019bf25  nop
0x18019bf26  movups  xmm0, [rbp+4D0h+var_510]
0x18019bf2a  movdqu  [rbp+4D0h+var_4D0], xmm0
0x18019bf2f  mov     r12d, 0A00h
0x18019bf35  mov     [rsp+5D0h+var_5A0], r12d
0x18019bf3a  mov     ecx, 1400h; cb
0x18019bf3f  call    cs:__imp_CoTaskMemAlloc
0x18019bf45  mov     rsi, rax
0x18019bf48  mov     [rsp+5D0h+var_598], rax
0x18019bf4d  jmp     short loc_18019BF66
0x18019bf4f  lea     r8, aApplication; "application"
0x18019bf56  mov     rdx, rbx; struct IXmlReader *
0x18019bf59  call    ?_ReachedCategoryOrEndElement@CControlPanelTasks@@AEAAJPEAUIXmlReader@@PEBG@Z; CControlPanelTasks::_ReachedCategoryOrEndElement(IXmlReader *,ushort const *)
0x18019bf5e  test    eax, eax
0x18019bf60  jns     loc_18019C662
0x18019bf66  lea     rdx, aTask; "task"
0x18019bf6d  mov     rcx, rbx; struct IXmlReader *
0x18019bf70  call    ?CPL_MoveToNextElement@@YAJPEAUIXmlReader@@PEBG@Z; CPL_MoveToNextElement(IXmlReader *,ushort const *)
0x18019bf75  test    eax, eax
0x18019bf77  js      short loc_18019BF4F
0x18019bf79  jnz     loc_18019C662
0x18019bf7f  mov     r14d, 80004005h
0x18019bf85  mov     r13d, 1
0x18019bf8b  test    rsi, rsi
0x18019bf8e  jz      short loc_18019BF94
0x18019bf90  mov     [rsi], r15w
0x18019bf94  mov     rax, [rbx]
0x18019bf97  xor     r8d, r8d
0x18019bf9a  lea     rdx, aId_0; "id"
0x18019bfa1  mov     rcx, rbx
0x18019bfa4  mov     rax, [rax+50h]
0x18019bfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019bfad  test    eax, eax
0x18019bfaf  jnz     loc_18019C63E
0x18019bfb5  mov     [rsp+5D0h+lpString1], r15
0x18019bfba  mov     rax, [rbx]
0x18019bfbd  xor     r8d, r8d
0x18019bfc0  lea     rdx, [rsp+5D0h+lpString1]
0x18019bfc5  mov     rcx, rbx
0x18019bfc8  mov     rax, [rax+80h]
0x18019bfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019bfd4  test    eax, eax
0x18019bfd6  js      loc_18019C63E
0x18019bfdc  cmp     [rbp+4D0h+var_4C0], r15
0x18019bfe0  jnz     short loc_18019BFF4
0x18019bfe2  lea     rcx, [rbp+4D0h+var_4C0]
0x18019bfe6  call    ?Create@?$CDSA_Base@UtagTASKWITHOVERRIDE@@@@QEAAHH@Z; CDSA_Base<tagTASKWITHOVERRIDE>::Create(int)
0x18019bfeb  test    eax, eax
0x18019bfed  jnz     short loc_18019BFFC
0x18019bfef  mov     eax, 8007000Eh
0x18019bff4  test    eax, eax
0x18019bff6  js      loc_18019C63E
0x18019bffc  xor     edx, edx; Val
0x18019bffe  lea     r8d, [rdx+60h]; Size
0x18019c002  lea     rcx, [rsp+5D0h+pitem]; void *
0x18019c007  call    memset_0
0x18019c00c  lea     rdx, [rsp+5D0h+pitem]
0x18019c011  mov     rcx, [rsp+5D0h+lpString1]
0x18019c016  call    cs:__imp_GUIDFromStringW
0x18019c01c  test    eax, eax
0x18019c01e  jz      loc_18019C60C
0x18019c024  mov     r12d, r15d
0x18019c027  mov     edi, r15d
0x18019c02a  mov     rax, [rbx]
0x18019c02d  xor     r8d, r8d
0x18019c030  lea     rdx, aNeedselevation; "needsElevation"
0x18019c037  mov     rcx, rbx
0x18019c03a  mov     rax, [rax+50h]
0x18019c03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c043  test    eax, eax
0x18019c045  jnz     short loc_18019C08F
0x18019c047  mov     rax, [rbx]
0x18019c04a  xor     r8d, r8d
0x18019c04d  lea     rdx, [rsp+5D0h+lpString1]
0x18019c052  mov     rcx, rbx
0x18019c055  mov     rax, [rax+80h]
0x18019c05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c061  mov     edi, eax
0x18019c063  mov     [rsp+5D0h+bIgnoreCase], r13d; bIgnoreCase
0x18019c068  or      r9d, 0FFFFFFFFh; cchCount2
0x18019c06c  lea     r8, aTrue; "true"
0x18019c073  or      edx, r9d; cchCount1
0x18019c076  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x18019c07b  call    cs:__imp_CompareStringOrdinal
0x18019c081  movzx   ecx, [rbp+4D0h+var_52F]
0x18019c085  cmp     eax, 2
0x18019c088  cmovz   ecx, r13d
0x18019c08c  mov     [rbp+4D0h+var_52F], cl
0x18019c08f  mov     r13b, r15b
0x18019c092  test    edi, edi
0x18019c094  js      loc_18019C60C
0x18019c09a  test    r13b, r13b
0x18019c09d  jnz     loc_18019C56F
0x18019c0a3  xor     edx, edx; unsigned __int16 *
0x18019c0a5  mov     rcx, rbx; struct IXmlReader *
0x18019c0a8  call    ?CPL_MoveToNextElement@@YAJPEAUIXmlReader@@PEBG@Z; CPL_MoveToNextElement(IXmlReader *,ushort const *)
0x18019c0ad  test    eax, eax
0x18019c0af  jnz     loc_18019C567
0x18019c0b5  mov     rdx, rbx; struct IXmlReader *
0x18019c0b8  call    ?_ReachedEndElement@CControlPanelTasks@@AEAA_NPEAUIXmlReader@@@Z; CControlPanelTasks::_ReachedEndElement(IXmlReader *)
0x18019c0bd  mov     r15b, al
0x18019c0c0  mov     rcx, [rbx]
0x18019c0c3  mov     rax, [rcx+70h]
0x18019c0c7  xor     r8d, r8d
0x18019c0ca  lea     rdx, [rsp+5D0h+lpString1]
0x18019c0cf  mov     rcx, rbx
0x18019c0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c0d7  mov     edi, eax
0x18019c0d9  test    eax, eax
0x18019c0db  js      loc_18019C609
0x18019c0e1  mov     [rsp+5D0h+bIgnoreCase], 1; bIgnoreCase
0x18019c0e9  or      r9d, 0FFFFFFFFh; cchCount2
0x18019c0ed  lea     r8, aTask; "task"
0x18019c0f4  or      edx, r9d; cchCount1
0x18019c0f7  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x18019c0fc  call    cs:__imp_CompareStringOrdinal
0x18019c102  cmp     eax, 2
0x18019c105  jnz     short loc_18019C11C
0x18019c107  test    r15b, r15b
0x18019c10a  jz      short loc_18019C114
0x18019c10c  mov     r13b, 1
0x18019c10f  xor     r15d, r15d
0x18019c112  jmp     short loc_18019C09A
0x18019c114  mov     edi, r14d
0x18019c117  jmp     loc_18019C55C
0x18019c11c  mov     [rsp+5D0h+bIgnoreCase], 1; bIgnoreCase
0x18019c124  or      r9d, 0FFFFFFFFh; cchCount2
0x18019c128  lea     r8, aName_1; "name"
0x18019c12f  or      edx, r9d; cchCount1
0x18019c132  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x18019c137  call    cs:__imp_CompareStringOrdinal
0x18019c13d  cmp     eax, 2
0x18019c140  jnz     short loc_18019C1A4
0x18019c142  test    r15b, r15b
0x18019c145  jnz     short loc_18019C1A4
0x18019c147  lea     r8, [rsp+5D0h+lpString1]; unsigned __int16 **
0x18019c14c  mov     rdx, rbx; struct IXmlReader *
0x18019c14f  call    ?_GetElementText@CControlPanelTasks@@AEAAJPEAUIXmlReader@@PEAPEBG@Z; CControlPanelTasks::_GetElementText(IXmlReader *,ushort const * *)
0x18019c154  xor     r15d, r15d
0x18019c157  test    eax, eax
0x18019c159  js      loc_18019C60C
0x18019c15f  xor     edx, edx; Val
0x18019c161  mov     r8d, 0F0h; Size
0x18019c167  lea     rcx, [rbp+4D0h+pszOutBuf]; void *
0x18019c16e  call    memset_0
0x18019c173  xor     r9d, r9d; ppvReserved
0x18019c176  lea     r8d, [r15+78h]; cchOutBuf
0x18019c17a  lea     rdx, [rbp+4D0h+pszOutBuf]; pszOutBuf
0x18019c181  mov     rcx, [rsp+5D0h+lpString1]; pszSource
0x18019c186  call    cs:__imp_SHLoadIndirectString
0x18019c18c  test    eax, eax
0x18019c18e  js      loc_18019C60C
0x18019c194  lea     r9, [rbp+4D0h+var_550]
0x18019c198  lea     r8, [rbp+4D0h+pszOutBuf]
0x18019c19f  jmp     loc_18019C392
0x18019c1a4  mov     [rsp+5D0h+bIgnoreCase], 1; bIgnoreCase
0x18019c1ac  or      r9d, 0FFFFFFFFh; cchCount2
0x18019c1b0  lea     r8, aKeywords; "keywords"
0x18019c1b7  or      edx, r9d; cchCount1
0x18019c1ba  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x18019c1bf  call    cs:__imp_CompareStringOrdinal
0x18019c1c5  cmp     eax, 2
0x18019c1c8  jnz     loc_18019C2FB
0x18019c1ce  test    r15b, r15b
0x18019c1d1  jnz     loc_18019C2FB
0x18019c1d7  test    rsi, rsi
0x18019c1da  jz      loc_18019C2FB
0x18019c1e0  lea     r8, [rsp+5D0h+lpString1]; unsigned __int16 **
0x18019c1e5  mov     rdx, rbx; struct IXmlReader *
0x18019c1e8  call    ?_GetElementText@CControlPanelTasks@@AEAAJPEAUIXmlReader@@PEAPEBG@Z; CControlPanelTasks::_GetElementText(IXmlReader *,ushort const * *)
0x18019c1ed  xor     r15d, r15d
0x18019c1f0  test    eax, eax
0x18019c1f2  js      loc_18019C60C
0x18019c1f8  movsxd  r15, r12d
0x18019c1fb  add     r15, r15
0x18019c1fe  mov     r8d, [rsp+5D0h+var_5A0]
0x18019c203  sub     r8d, r12d; cchOutBuf
0x18019c206  lea     rdx, [r15+rsi]; pszOutBuf
0x18019c20a  xor     r9d, r9d; ppvReserved
0x18019c20d  mov     rcx, [rsp+5D0h+lpString1]; pszSource
0x18019c212  call    cs:__imp_SHLoadIndirectString
0x18019c218  mov     edi, eax
0x18019c21a  test    eax, eax
0x18019c21c  jns     short loc_18019C277
0x18019c21e  call    ResultFromKnownLastError
0x18019c223  cmp     eax, 8007007Ah
0x18019c228  jnz     short loc_18019C264
0x18019c22a  lea     r8, [rsp+5D0h+var_5A0]; int *
0x18019c22f  lea     rdx, [rsp+5D0h+var_598]; unsigned __int16 **
0x18019c234  call    ?_IncreaseTaskKeywordsBuffer@CControlPanelTasks@@AEAAJPEAPEAGPEAH@Z; CControlPanelTasks::_IncreaseTaskKeywordsBuffer(ushort * *,int *)
0x18019c239  mov     edi, eax
0x18019c23b  mov     rsi, [rsp+5D0h+var_598]
0x18019c240  test    eax, eax
0x18019c242  js      short loc_18019C21E
0x18019c244  mov     r8d, [rsp+5D0h+var_5A0]
0x18019c249  sub     r8d, r12d; cchOutBuf
0x18019c24c  lea     rdx, [r15+rsi]; pszOutBuf
0x18019c250  xor     r9d, r9d; ppvReserved
0x18019c253  mov     rcx, [rsp+5D0h+lpString1]; pszSource
0x18019c258  call    cs:__imp_SHLoadIndirectString
0x18019c25e  mov     edi, eax
0x18019c260  test    eax, eax
0x18019c262  js      short loc_18019C21E
0x18019c264  xor     r15d, r15d
0x18019c267  test    edi, edi
0x18019c269  mov     r14d, 80004005h
0x18019c26f  js      loc_18019C60C
0x18019c275  jmp     short loc_18019C27A
0x18019c277  xor     r15d, r15d
0x18019c27a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18019c27e  inc     r12
0x18019c281  cmp     [rsi+r12*2], r15w
0x18019c286  jnz     short loc_18019C27E
0x18019c288  test    r12d, r12d
0x18019c28b  jle     loc_18019C39F
0x18019c291  movsxd  rax, r12d
0x18019c294  mov     ecx, 3Bh ; ';'; this
0x18019c299  cmp     cx, [rsi+rax*2-2]
0x18019c29e  jz      loc_18019C39F
0x18019c2a4  lea     r15d, [r12+1]
0x18019c2a9  mov     r12d, [rsp+5D0h+var_5A0]
0x18019c2ae  cmp     r12d, r15d
0x18019c2b1  jge     short loc_18019C2CE
0x18019c2b3  lea     r8, [rsp+5D0h+var_5A0]; int *
0x18019c2b8  lea     rdx, [rsp+5D0h+var_598]; unsigned __int16 **
0x18019c2bd  call    ?_IncreaseTaskKeywordsBuffer@CControlPanelTasks@@AEAAJPEAPEAGPEAH@Z; CControlPanelTasks::_IncreaseTaskKeywordsBuffer(ushort * *,int *)
0x18019c2c2  mov     edi, eax
0x18019c2c4  mov     rsi, [rsp+5D0h+var_598]
0x18019c2c9  mov     r12d, [rsp+5D0h+var_5A0]
0x18019c2ce  test    edi, edi
0x18019c2d0  js      loc_18019C609
0x18019c2d6  movsxd  rdx, r12d; unsigned __int64
0x18019c2d9  lea     r8, asc_1805EE0B0; ";"
0x18019c2e0  mov     rcx, rsi; unsigned __int16 *
0x18019c2e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18019c2e8  test    eax, eax
0x18019c2ea  js      loc_18019C609
0x18019c2f0  mov     r12d, r15d
0x18019c2f3  xor     r15d, r15d
0x18019c2f6  jmp     loc_18019C39F
0x18019c2fb  mov     [rsp+5D0h+bIgnoreCase], 1; bIgnoreCase
0x18019c303  or      r9d, 0FFFFFFFFh; cchCount2
0x18019c307  lea     r8, pszSubKey; "command"
0x18019c30e  or      edx, r9d; cchCount1
0x18019c311  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x18019c316  call    cs:__imp_CompareStringOrdinal
0x18019c31c  cmp     eax, 2
0x18019c31f  jnz     loc_18019C3AE
0x18019c325  test    r15b, r15b
0x18019c328  jnz     loc_18019C3AE
0x18019c32e  lea     r8, [rsp+5D0h+lpString1]; unsigned __int16 **
0x18019c333  mov     rdx, rbx; struct IXmlReader *
0x18019c336  call    ?_GetElementText@CControlPanelTasks@@AEAAJPEAUIXmlReader@@PEAPEBG@Z; CControlPanelTasks::_GetElementText(IXmlReader *,ushort const * *)
0x18019c33b  xor     r15d, r15d
0x18019c33e  test    eax, eax
0x18019c340  js      loc_18019C60C
0x18019c346  lea     rcx, ?c_legacyTroubleshoot@@3QBGB; "%windir%\\system32\\msdt.exe"
0x18019c34d  call    cs:__imp_lstrlenW
0x18019c353  mov     [rsp+5D0h+bIgnoreCase], 1; bIgnoreCase
0x18019c35b  mov     r9d, eax; cchCount2
  ... truncated ...
```
