# CControlPanelTasks::_LoadAppletTasksFromXml(IXmlReader *,ushort const *)

- ea: `0x1801b0010`
- end: `0x1801b0923`
- name: `?_LoadAppletTasksFromXml@CControlPanelTasks@@AEAAJPEAUIXmlReader@@PEBG@Z`
- size: `2323`
- prototype: `int(CControlPanelTasks *__hidden this, struct IXmlReader *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180080f00`

## callees

- `0x18000fc30`
- `0x180018e4c`
- `0x18001aae0`
- `0x18001b9a0`
- `0x18003e1e8`
- `0x1800808f0`
- `0x180081060`
- `0x1800e9518`
- `0x180135948`
- `0x18013ede4`
- `0x1801b0010`
- `0x1801e0c5c`
- `0x1801ed88c`
- `0x1801eeb38`
- `0x180249490`
- `0x180249c8c`
- `0x18024a53c`
- `0x18043b8cc`
- `0x18043c15c`
- `0x18043ca14`
- `0x18043caa0`
- `0x18043cbe0`
- `0x18043d428`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b021d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b02a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b02e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b0379`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b04e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b0554`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b05b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b0730`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b021d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b02a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b02e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b0379`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b04e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b0554`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b05b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801b0730`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1801b033a`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1801b03d2`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1801b041e`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1801b033a`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1801b03d2`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1801b041e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1801b052f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1801b052f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b06f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0805`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b08d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b06f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0805`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b08d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b00d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b00d5`
- `SHCORE!__imp_GUIDFromStringW` at `0x1801b0059`
- `SHCORE!__imp_GUIDFromStringW` at `0x1801b01b2`
- `SHCORE!__imp_GUIDFromStringW` at `0x1801b0059`
- `SHCORE!__imp_GUIDFromStringW` at `0x1801b01b2`

## string_xrefs

- `0x1801b04d3`: `command`
- `0x1801b0528`: `%windir%\system32\msdt.exe`
- `0x1801b0546`: `%windir%\system32\msdt.exe`

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
  __int64 v13; // r12
  int v14; // edi
  __int64 v15; // rdx
  int v16; // eax
  char v17; // cl
  char v18; // r13
  CControlPanelTasks *v19; // rcx
  bool v20; // r15
  CControlPanelTasks *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  LPVOID *p_pv; // r9
  WCHAR *v25; // r8
  CControlPanelTasks *v26; // rcx
  __int64 v27; // r15
  HRESULT v28; // edi
  CControlPanelTasks *v29; // rcx
  int v30; // r15d
  int v31; // r12d
  CControlPanelTasks *v32; // rcx
  int v33; // eax
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  CControlPanelTasks *v39; // rcx
  int v40; // eax
  CControlPanelTasks *v41; // rcx
  int CategoryTasks; // r14d
  int v44; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v45; // [rsp+38h] [rbp-C8h] BYREF
  HDSA *v46; // [rsp+40h] [rbp-C0h]
  HDSA *v47; // [rsp+48h] [rbp-B8h]
  LPCWCH lpString1[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD pitem[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v50; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v51; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  struct ITaskCondition *v53; // [rsp+98h] [rbp-68h] BYREF
  char v54; // [rsp+A0h] [rbp-60h]
  char v55; // [rsp+A1h] [rbp-5Fh]
  __int128 v56; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v57[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v58; // [rsp+F0h] [rbp-10h]
  __int128 v59; // [rsp+100h] [rbp+0h] BYREF
  __int64 v60; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v61[104]; // [rsp+118h] [rbp+18h] BYREF
  WCHAR pszOutBuf[520]; // [rsp+180h] [rbp+80h] BYREF

  v46 = this;
  v56 = 0;
  if ( !(unsigned int)GUIDFromStringW(a3, &v56) )
    return (unsigned int)-2147467259;
  v8 = this + 13;
  v47 = this + 13;
  if ( (unsigned int)CDSA_Base<APPLETTASKS>::Search((int)this + 104, v5, v6, v7, (__int64)&v56) != -1 )
    return (unsigned int)-2147467259;
  v60 = 0;
  `eh vector constructor iterator'(
    v61,
    8u,
    0xCu,
    (void (*)(void *))CDSA<MENUIDMAP>::`default constructor closure',
    (void (*)(void *))tip2::details::merged_data<_tip_BackupWallpaperCreationTest,_tip_BackupWallpaperCreationTest>::on_result);
  v59 = v56;
  v44 = 2560;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(0x1400u);
  v45 = v9;
  while ( 1 )
  {
    Element = CPL_MoveToNextElement(a2, L"task");
    if ( Element >= 0 )
      break;
    if ( CControlPanelTasks::_ReachedCategoryOrEndElement(v10, a2, L"application") >= 0 )
      goto LABEL_95;
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
LABEL_92:
      while ( 1 )
      {
        v40 = CPL_MoveToNextElement(a2, L"task");
        if ( v40 >= 0 )
          break;
        if ( CControlPanelTasks::_ReachedCategoryOrEndElement(v10, a2, L"application") >= 0 )
          goto LABEL_94;
      }
      if ( v40 )
      {
LABEL_94:
        v8 = v47;
        goto LABEL_95;
      }
    }
    if ( !v60 )
    {
      if ( (unsigned int)CDSA_Base<tagTASKWITHOVERRIDE>::Create(&v60) )
        goto LABEL_15;
      v12 = -2147024882;
    }
    if ( v12 < 0 )
      goto LABEL_92;
LABEL_15:
    memset_0(pitem, 0, 0x60u);
    if ( !(unsigned int)GUIDFromStringW(lpString1[0], pitem) )
      goto LABEL_90;
    LODWORD(v13) = 0;
    v14 = 0;
    if ( !((unsigned int (__fastcall *)(struct IXmlReader *, const wchar_t *, _QWORD))a2->lpVtbl->MoveToAttributeByName)(
            a2,
            L"needsElevation",
            0) )
    {
      v14 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWCH *, _QWORD))a2->lpVtbl->GetValue)(a2, lpString1, 0);
      v16 = CompareStringOrdinal(lpString1[0], -1, L"true", -1, 1);
      v17 = v55;
      if ( v16 == 2 )
        v17 = 1;
      v55 = v17;
    }
    v18 = 0;
    if ( v14 < 0 )
      goto LABEL_90;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v18 )
          goto LABEL_80;
        if ( CPL_MoveToNextElement(a2, 0) )
          goto LABEL_79;
        v20 = CControlPanelTasks::_ReachedEndElement(v19, a2);
        v14 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWCH *, _QWORD))a2->lpVtbl->GetLocalName)(
                a2,
                lpString1,
                0);
        if ( v14 < 0 )
          goto LABEL_90;
        if ( CompareStringOrdinal(lpString1[0], -1, L"task", -1, 1) != 2 )
          break;
        if ( v20 )
        {
          v18 = 1;
        }
        else
        {
          v14 = -2147467259;
LABEL_78:
          if ( v14 < 0 )
          {
LABEL_79:
            if ( v14 >= 0 )
            {
LABEL_80:
              if ( v50
                && pv
                && *(_WORD *)v50
                && *(_WORD *)pv
                && (!v9 || !*v9 || (int)_AllocString<CTCoAllocPolicy>(v50, v15, v9, &v51) >= 0) )
              {
                pitem[1] = v56;
                if ( DSA_InsertItem(*v46, 0x7FFFFFFF, pitem) != -1 )
                {
                  v57[1] = 0;
                  v58 = 0;
                  v57[0] = pitem[0];
                  if ( (int)CDSA_Base<GROUP_ITEM_ENTRY>::AppendItem(&v60, v57) >= 0 )
                    goto LABEL_92;
                }
                CoTaskMemFree(v51);
              }
            }
LABEL_90:
            SafeRelease<IUpdatableItemSet>(&v53);
            CoTaskMemFree(v50);
            CoTaskMemFree(pv);
            goto LABEL_92;
          }
        }
      }
      if ( CompareStringOrdinal(lpString1[0], -1, L"name", -1, 1) == 2 && !v20 )
        break;
      if ( CompareStringOrdinal(lpString1[0], -1, L"keywords", -1, 1) == 2 && !v20 && v9 )
      {
        if ( (int)CControlPanelTasks::_GetElementText(v26, a2, lpString1) < 0 )
          goto LABEL_90;
        v27 = (int)v13;
        v28 = SHLoadIndirectString(lpString1[0], &v9[v27], v44 - v13, 0);
        if ( v28 < 0 )
        {
          while ( (unsigned int)ResultFromKnownLastError() == -2147024774 )
          {
            v28 = CControlPanelTasks::_IncreaseTaskKeywordsBuffer(v29, &v45, &v44);
            v9 = v45;
            if ( v28 >= 0 )
            {
              v28 = SHLoadIndirectString(lpString1[0], &v45[v27], v44 - v13, 0);
              if ( v28 >= 0 )
                break;
            }
          }
          if ( v28 < 0 )
            goto LABEL_90;
        }
        v13 = -1;
        do
          ++v13;
        while ( v9[v13] );
        if ( (int)v13 > 0 && v9[(int)v13 - 1] != 59 )
        {
          v30 = v13 + 1;
          v31 = v44;
          if ( v44 < v30 )
          {
            v28 = CControlPanelTasks::_IncreaseTaskKeywordsBuffer((CControlPanelTasks *)0x3B, &v45, &v44);
            v9 = v45;
            v31 = v44;
          }
          if ( v28 < 0 || (int)StringCchCatW(v9, v31, L";") < 0 )
            goto LABEL_90;
          LODWORD(v13) = v30;
        }
LABEL_61:
        v34 = CPL_MoveToNextElement(a2, 0);
LABEL_74:
        v14 = v34;
        goto LABEL_78;
      }
      if ( CompareStringOrdinal(lpString1[0], -1, L"command", -1, 1) == 2 && !v20 )
      {
        if ( (int)CControlPanelTasks::_GetElementText(v32, a2, lpString1) < 0 )
          goto LABEL_90;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_44969195>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_44969195>::GetImpl'::`2'::impl)
          && (v33 = lstrlenW(L"%windir%\\system32\\msdt.exe"),
              CompareStringOrdinal(lpString1[0], v33, L"%windir%\\system32\\msdt.exe", v33, 1) == 2) )
        {
          v25 = L"%SystemRoot%\\explorer.exe ms-settings:troubleshoot";
          lpString1[0] = L"%SystemRoot%\\explorer.exe ms-settings:troubleshoot";
          v55 = 0;
        }
        else
        {
          v25 = (WCHAR *)lpString1[0];
        }
        p_pv = &pv;
LABEL_60:
        if ( (int)_AllocString<CTCoAllocPolicy>(v23, v22, v25, p_pv) < 0 )
          goto LABEL_90;
        goto LABEL_61;
      }
      if ( CompareStringOrdinal(lpString1[0], -1, L"controlpanel", -1, 1) == 2 )
      {
        if ( !pv || !*(_WORD *)pv )
        {
          v14 = ((__int64 (__fastcall *)(struct IXmlReader *, const WCHAR *, _QWORD))a2->lpVtbl->MoveToAttributeByName)(
                  a2,
                  L"name",
                  0);
          if ( v14 )
            goto LABEL_78;
          if ( ((int (__fastcall *)(struct IXmlReader *, LPCWCH *, _QWORD))a2->lpVtbl->GetValue)(a2, lpString1, 0) < 0
            || (int)_AllocString<CTCoAllocPolicy>(v36, v35, lpString1[0], &pv) < 0 )
          {
            goto LABEL_90;
          }
          v54 = 1;
          v14 = ((__int64 (__fastcall *)(struct IXmlReader *, const wchar_t *, _QWORD))a2->lpVtbl->MoveToAttributeByName)(
                  a2,
                  L"page",
                  0);
          if ( v14 )
            goto LABEL_78;
          if ( ((int (__fastcall *)(struct IXmlReader *, LPCWCH *, _QWORD))a2->lpVtbl->GetValue)(a2, lpString1, 0) < 0 )
            goto LABEL_90;
          memset_0(pszOutBuf, 0, sizeof(pszOutBuf));
          if ( (int)StringCchCopyW(pszOutBuf, 0x208u, (const unsigned __int16 *)pv) < 0
            || (int)StringCchCatW(pszOutBuf, 0x208u, L"\\") < 0
            || (int)StringCchCatW(pszOutBuf, 0x208u, lpString1[0]) < 0 )
          {
            goto LABEL_90;
          }
          CoTaskMemFree(pv);
          v34 = _AllocString<CTCoAllocPolicy>(v38, v37, pszOutBuf, &pv);
          goto LABEL_74;
        }
      }
      else if ( CompareStringOrdinal(lpString1[0], -1, L"conditions", -1, 1) == 2 && !v20 )
      {
        v14 = CControlPanelTasks::_LoadTaskCondition(v39, a2, &v53);
        goto LABEL_78;
      }
    }
    if ( (int)CControlPanelTasks::_GetElementText(v21, a2, lpString1) < 0 )
      goto LABEL_90;
    memset_0(pszOutBuf, 0, 0xF0u);
    if ( SHLoadIndirectString(lpString1[0], pszOutBuf, 0x78u, 0) < 0 )
      goto LABEL_90;
    p_pv = &v50;
    v25 = pszOutBuf;
    goto LABEL_60;
  }
LABEL_95:
  CategoryTasks = CControlPanelTasks::_LoadCategoryTasks(v10, a2, L"application", v61);
  if ( CategoryTasks < 0 )
    goto LABEL_99;
  if ( DSA_InsertItem(*v8, 0x7FFFFFFF, &v59) == -1 )
  {
    CategoryTasks = -2147024882;
LABEL_99:
    CControlPanelTasks::_APPLETTASKS_Destroy(v41, (struct APPLETTASKS *)&v59);
    goto LABEL_100;
  }
  CategoryTasks = 0;
  v60 = 0;
  memset_0(v61, 0, 0x60u);
LABEL_100:
  if ( v9 )
    CoTaskMemFree(v9);
  APPLETTASKS::~APPLETTASKS((APPLETTASKS *)&v59);
  return (unsigned int)CategoryTasks;
}

```

## disassembly

```asm
0x1801b0010  mov     [rsp-8+arg_18], rbx
0x1801b0015  push    rbp
0x1801b0016  push    rsi
0x1801b0017  push    rdi
0x1801b0018  push    r12
0x1801b001a  push    r13
0x1801b001c  push    r14
0x1801b001e  push    r15
0x1801b0020  lea     rbp, [rsp-4A0h]
0x1801b0028  sub     rsp, 5A0h
0x1801b002f  mov     rax, cs:__security_cookie
0x1801b0036  xor     rax, rsp
0x1801b0039  mov     [rbp+4D0h+var_40], rax
0x1801b0040  mov     rbx, rdx
0x1801b0043  mov     r15, rcx
0x1801b0046  mov     [rsp+5D0h+var_590], rcx
0x1801b004b  xorps   xmm0, xmm0
0x1801b004e  movups  [rbp+4D0h+var_510], xmm0
0x1801b0052  lea     rdx, [rbp+4D0h+var_510]
0x1801b0056  mov     rcx, r8
0x1801b0059  call    cs:__imp_GUIDFromStringW
0x1801b0060  nop     dword ptr [rax+rax+00h]
0x1801b0065  test    eax, eax
0x1801b0067  jz      loc_1801B08EF
0x1801b006d  lea     rdi, [r15+68h]
0x1801b0071  mov     [rsp+5D0h+var_588], rdi
0x1801b0076  lea     rax, [rbp+4D0h+var_510]
0x1801b007a  mov     qword ptr [rsp+5D0h+bIgnoreCase], rax
0x1801b007f  mov     rcx, rdi
0x1801b0082  call    ?Search@?$CDSA_Base@UAPPLETTASKS@@@@QEBAHPEBUAPPLETTASKS@@HP6AH00_J@Z1I@Z; CDSA_Base<APPLETTASKS>::Search(APPLETTASKS const *,int,int (*)(APPLETTASKS const *,APPLETTASKS const *,__int64),__int64,uint)
0x1801b0087  cmp     eax, 0FFFFFFFFh
0x1801b008a  jnz     loc_1801B08EF
0x1801b0090  xor     r15d, r15d
0x1801b0093  mov     [rbp+4D0h+var_4C0], r15
0x1801b0097  lea     rax, ?on_result@?$merged_data@U_tip_BackupWallpaperCreationTest@@U1@@details@tip2@@EEAAXAEBUTipReportingInfo@@@Z; tip2::details::merged_data<_tip_BackupWallpaperCreationTest,_tip_BackupWallpaperCreationTest>::on_result(TipReportingInfo const &)
0x1801b009e  mov     qword ptr [rsp+5D0h+bIgnoreCase], rax; void (*)(void *)
0x1801b00a3  lea     r9, ??_F?$CDSA@UMENUIDMAP@@@@QEAAXXZ; void (*)(void *)
0x1801b00aa  lea     edx, [r15+8]; unsigned __int64
0x1801b00ae  lea     r8d, [r15+0Ch]; unsigned __int64
0x1801b00b2  lea     rcx, [rbp+4D0h+var_4B8]; void *
0x1801b00b6  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1801b00bb  nop
0x1801b00bc  movups  xmm0, [rbp+4D0h+var_510]
0x1801b00c0  movdqu  [rbp+4D0h+var_4D0], xmm0
0x1801b00c5  mov     r12d, 0A00h
0x1801b00cb  mov     [rsp+5D0h+var_5A0], r12d
0x1801b00d0  mov     ecx, 1400h; cb
0x1801b00d5  call    cs:__imp_CoTaskMemAlloc
0x1801b00dc  nop     dword ptr [rax+rax+00h]
0x1801b00e1  mov     rsi, rax
0x1801b00e4  mov     [rsp+5D0h+var_598], rax
0x1801b00e9  jmp     short loc_1801B0102
0x1801b00eb  lea     r8, aApplication; "application"
0x1801b00f2  mov     rdx, rbx; struct IXmlReader *
0x1801b00f5  call    ?_ReachedCategoryOrEndElement@CControlPanelTasks@@AEAAJPEAUIXmlReader@@PEBG@Z; CControlPanelTasks::_ReachedCategoryOrEndElement(IXmlReader *,ushort const *)
0x1801b00fa  test    eax, eax
0x1801b00fc  jns     loc_1801B0878
0x1801b0102  lea     rdx, aTask; "task"
0x1801b0109  mov     rcx, rbx; struct IXmlReader *
0x1801b010c  call    ?CPL_MoveToNextElement@@YAJPEAUIXmlReader@@PEBG@Z; CPL_MoveToNextElement(IXmlReader *,ushort const *)
0x1801b0111  test    eax, eax
0x1801b0113  js      short loc_1801B00EB
0x1801b0115  jnz     loc_1801B0878
0x1801b011b  mov     r14d, 80004005h
0x1801b0121  mov     r13d, 1
0x1801b0127  test    rsi, rsi
0x1801b012a  jz      short loc_1801B0130
0x1801b012c  mov     [rsi], r15w
0x1801b0130  mov     rax, [rbx]
0x1801b0133  xor     r8d, r8d
0x1801b0136  lea     rdx, aId_0; "id"
0x1801b013d  mov     rcx, rbx
0x1801b0140  mov     rax, [rax+50h]
0x1801b0144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0149  test    eax, eax
0x1801b014b  jnz     loc_1801B0854
0x1801b0151  mov     [rsp+5D0h+lpString1], r15
0x1801b0156  mov     rax, [rbx]
0x1801b0159  xor     r8d, r8d
0x1801b015c  lea     rdx, [rsp+5D0h+lpString1]
0x1801b0161  mov     rcx, rbx
0x1801b0164  mov     rax, [rax+80h]
0x1801b016b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0170  test    eax, eax
0x1801b0172  js      loc_1801B0854
0x1801b0178  cmp     [rbp+4D0h+var_4C0], r15
0x1801b017c  jnz     short loc_1801B0190
0x1801b017e  lea     rcx, [rbp+4D0h+var_4C0]
0x1801b0182  call    ?Create@?$CDSA_Base@UtagTASKWITHOVERRIDE@@@@QEAAHH@Z; CDSA_Base<tagTASKWITHOVERRIDE>::Create(int)
0x1801b0187  test    eax, eax
0x1801b0189  jnz     short loc_1801B0198
0x1801b018b  mov     eax, 8007000Eh
0x1801b0190  test    eax, eax
0x1801b0192  js      loc_1801B0854
0x1801b0198  xor     edx, edx; Val
0x1801b019a  lea     r8d, [rdx+60h]; Size
0x1801b019e  lea     rcx, [rsp+5D0h+pitem]; void *
0x1801b01a3  call    memset_0
0x1801b01a8  lea     rdx, [rsp+5D0h+pitem]
0x1801b01ad  mov     rcx, [rsp+5D0h+lpString1]
0x1801b01b2  call    cs:__imp_GUIDFromStringW
0x1801b01b9  nop     dword ptr [rax+rax+00h]
0x1801b01be  test    eax, eax
0x1801b01c0  jz      loc_1801B0816
0x1801b01c6  mov     r12d, r15d
0x1801b01c9  mov     edi, r15d
0x1801b01cc  mov     rax, [rbx]
0x1801b01cf  xor     r8d, r8d
0x1801b01d2  lea     rdx, aNeedselevation; "needsElevation"
0x1801b01d9  mov     rcx, rbx
0x1801b01dc  mov     rax, [rax+50h]
0x1801b01e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b01e5  test    eax, eax
0x1801b01e7  jnz     short loc_1801B0237
0x1801b01e9  mov     rax, [rbx]
0x1801b01ec  xor     r8d, r8d
0x1801b01ef  lea     rdx, [rsp+5D0h+lpString1]
0x1801b01f4  mov     rcx, rbx
0x1801b01f7  mov     rax, [rax+80h]
0x1801b01fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0203  mov     edi, eax
0x1801b0205  mov     [rsp+5D0h+bIgnoreCase], r13d; bIgnoreCase
0x1801b020a  or      r9d, 0FFFFFFFFh; cchCount2
0x1801b020e  lea     r8, aTrue; "true"
0x1801b0215  or      edx, r9d; cchCount1
0x1801b0218  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x1801b021d  call    cs:__imp_CompareStringOrdinal
0x1801b0224  nop     dword ptr [rax+rax+00h]
0x1801b0229  movzx   ecx, [rbp+4D0h+var_52F]
0x1801b022d  cmp     eax, 2
0x1801b0230  cmovz   ecx, r13d
0x1801b0234  mov     [rbp+4D0h+var_52F], cl
0x1801b0237  mov     r13b, r15b
0x1801b023a  test    edi, edi
0x1801b023c  js      loc_1801B0816
0x1801b0242  test    r13b, r13b
0x1801b0245  jnz     loc_1801B076F
0x1801b024b  xor     edx, edx; unsigned __int16 *
0x1801b024d  mov     rcx, rbx; struct IXmlReader *
0x1801b0250  call    ?CPL_MoveToNextElement@@YAJPEAUIXmlReader@@PEBG@Z; CPL_MoveToNextElement(IXmlReader *,ushort const *)
0x1801b0255  test    eax, eax
0x1801b0257  jnz     loc_1801B0767
0x1801b025d  mov     rdx, rbx; struct IXmlReader *
0x1801b0260  call    ?_ReachedEndElement@CControlPanelTasks@@AEAA_NPEAUIXmlReader@@@Z; CControlPanelTasks::_ReachedEndElement(IXmlReader *)
0x1801b0265  mov     r15b, al
0x1801b0268  mov     rcx, [rbx]
0x1801b026b  mov     rax, [rcx+70h]
0x1801b026f  xor     r8d, r8d
0x1801b0272  lea     rdx, [rsp+5D0h+lpString1]
0x1801b0277  mov     rcx, rbx
0x1801b027a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b027f  mov     edi, eax
0x1801b0281  test    eax, eax
0x1801b0283  js      loc_1801B0813
0x1801b0289  mov     [rsp+5D0h+bIgnoreCase], 1; bIgnoreCase
0x1801b0291  or      r9d, 0FFFFFFFFh; cchCount2
0x1801b0295  lea     r8, aTask; "task"
0x1801b029c  or      edx, r9d; cchCount1
0x1801b029f  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x1801b02a4  call    cs:__imp_CompareStringOrdinal
0x1801b02ab  nop     dword ptr [rax+rax+00h]
0x1801b02b0  cmp     eax, 2
0x1801b02b3  jnz     short loc_1801B02CA
0x1801b02b5  test    r15b, r15b
0x1801b02b8  jz      short loc_1801B02C2
0x1801b02ba  mov     r13b, 1
0x1801b02bd  xor     r15d, r15d
0x1801b02c0  jmp     short loc_1801B0242
0x1801b02c2  mov     edi, r14d
0x1801b02c5  jmp     loc_1801B075C
0x1801b02ca  mov     [rsp+5D0h+bIgnoreCase], 1; bIgnoreCase
0x1801b02d2  or      r9d, 0FFFFFFFFh; cchCount2
0x1801b02d6  lea     r8, aName_1; "name"
0x1801b02dd  or      edx, r9d; cchCount1
0x1801b02e0  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x1801b02e5  call    cs:__imp_CompareStringOrdinal
0x1801b02ec  nop     dword ptr [rax+rax+00h]
0x1801b02f1  cmp     eax, 2
0x1801b02f4  jnz     short loc_1801B035E
0x1801b02f6  test    r15b, r15b
0x1801b02f9  jnz     short loc_1801B035E
0x1801b02fb  lea     r8, [rsp+5D0h+lpString1]; unsigned __int16 **
0x1801b0300  mov     rdx, rbx; struct IXmlReader *
0x1801b0303  call    ?_GetElementText@CControlPanelTasks@@AEAAJPEAUIXmlReader@@PEAPEBG@Z; CControlPanelTasks::_GetElementText(IXmlReader *,ushort const * *)
0x1801b0308  xor     r15d, r15d
0x1801b030b  test    eax, eax
0x1801b030d  js      loc_1801B0816
0x1801b0313  xor     edx, edx; Val
0x1801b0315  mov     r8d, 0F0h; Size
0x1801b031b  lea     rcx, [rbp+4D0h+pszOutBuf]; void *
0x1801b0322  call    memset_0
0x1801b0327  xor     r9d, r9d; ppvReserved
0x1801b032a  lea     r8d, [r15+78h]; cchOutBuf
0x1801b032e  lea     rdx, [rbp+4D0h+pszOutBuf]; pszOutBuf
0x1801b0335  mov     rcx, [rsp+5D0h+lpString1]; pszSource
0x1801b033a  call    cs:__imp_SHLoadIndirectString
0x1801b0341  nop     dword ptr [rax+rax+00h]
0x1801b0346  test    eax, eax
0x1801b0348  js      loc_1801B0816
0x1801b034e  lea     r9, [rbp+4D0h+var_550]
0x1801b0352  lea     r8, [rbp+4D0h+pszOutBuf]
0x1801b0359  jmp     loc_1801B0580
0x1801b035e  mov     [rsp+5D0h+bIgnoreCase], 1; bIgnoreCase
0x1801b0366  or      r9d, 0FFFFFFFFh; cchCount2
0x1801b036a  lea     r8, aKeywords; "keywords"
0x1801b0371  or      edx, r9d; cchCount1
0x1801b0374  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x1801b0379  call    cs:__imp_CompareStringOrdinal
0x1801b0380  nop     dword ptr [rax+rax+00h]
0x1801b0385  cmp     eax, 2
0x1801b0388  jnz     loc_1801B04C7
0x1801b038e  test    r15b, r15b
0x1801b0391  jnz     loc_1801B04C7
0x1801b0397  test    rsi, rsi
0x1801b039a  jz      loc_1801B04C7
0x1801b03a0  lea     r8, [rsp+5D0h+lpString1]; unsigned __int16 **
0x1801b03a5  mov     rdx, rbx; struct IXmlReader *
0x1801b03a8  call    ?_GetElementText@CControlPanelTasks@@AEAAJPEAUIXmlReader@@PEAPEBG@Z; CControlPanelTasks::_GetElementText(IXmlReader *,ushort const * *)
0x1801b03ad  xor     r15d, r15d
0x1801b03b0  test    eax, eax
0x1801b03b2  js      loc_1801B0816
0x1801b03b8  movsxd  r15, r12d
0x1801b03bb  add     r15, r15
0x1801b03be  mov     r8d, [rsp+5D0h+var_5A0]
0x1801b03c3  sub     r8d, r12d; cchOutBuf
0x1801b03c6  lea     rdx, [r15+rsi]; pszOutBuf
0x1801b03ca  xor     r9d, r9d; ppvReserved
0x1801b03cd  mov     rcx, [rsp+5D0h+lpString1]; pszSource
0x1801b03d2  call    cs:__imp_SHLoadIndirectString
0x1801b03d9  nop     dword ptr [rax+rax+00h]
0x1801b03de  mov     edi, eax
0x1801b03e0  test    eax, eax
0x1801b03e2  jns     short loc_1801B0443
0x1801b03e4  call    ResultFromKnownLastError
0x1801b03e9  cmp     eax, 8007007Ah
0x1801b03ee  jnz     short loc_1801B0430
0x1801b03f0  lea     r8, [rsp+5D0h+var_5A0]; int *
0x1801b03f5  lea     rdx, [rsp+5D0h+var_598]; unsigned __int16 **
0x1801b03fa  call    ?_IncreaseTaskKeywordsBuffer@CControlPanelTasks@@AEAAJPEAPEAGPEAH@Z; CControlPanelTasks::_IncreaseTaskKeywordsBuffer(ushort * *,int *)
0x1801b03ff  mov     edi, eax
0x1801b0401  mov     rsi, [rsp+5D0h+var_598]
0x1801b0406  test    eax, eax
0x1801b0408  js      short loc_1801B03E4
0x1801b040a  mov     r8d, [rsp+5D0h+var_5A0]
0x1801b040f  sub     r8d, r12d; cchOutBuf
0x1801b0412  lea     rdx, [r15+rsi]; pszOutBuf
0x1801b0416  xor     r9d, r9d; ppvReserved
0x1801b0419  mov     rcx, [rsp+5D0h+lpString1]; pszSource
0x1801b041e  call    cs:__imp_SHLoadIndirectString
0x1801b0425  nop     dword ptr [rax+rax+00h]
0x1801b042a  mov     edi, eax
0x1801b042c  test    eax, eax
0x1801b042e  js      short loc_1801B03E4
0x1801b0430  xor     r15d, r15d
0x1801b0433  test    edi, edi
0x1801b0435  mov     r14d, 80004005h
0x1801b043b  js      loc_1801B0816
0x1801b0441  jmp     short loc_1801B0446
0x1801b0443  xor     r15d, r15d
0x1801b0446  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801b044a  inc     r12
0x1801b044d  cmp     [rsi+r12*2], r15w
0x1801b0452  jnz     short loc_1801B044A
0x1801b0454  test    r12d, r12d
0x1801b0457  jle     loc_1801B058D
0x1801b045d  movsxd  rax, r12d
0x1801b0460  mov     ecx, 3Bh ; ';'; this
0x1801b0465  cmp     cx, [rsi+rax*2-2]
0x1801b046a  jz      loc_1801B058D
0x1801b0470  lea     r15d, [r12+1]
0x1801b0475  mov     r12d, [rsp+5D0h+var_5A0]
0x1801b047a  cmp     r12d, r15d
0x1801b047d  jge     short loc_1801B049A
0x1801b047f  lea     r8, [rsp+5D0h+var_5A0]; int *
0x1801b0484  lea     rdx, [rsp+5D0h+var_598]; unsigned __int16 **
0x1801b0489  call    ?_IncreaseTaskKeywordsBuffer@CControlPanelTasks@@AEAAJPEAPEAGPEAH@Z; CControlPanelTasks::_IncreaseTaskKeywordsBuffer(ushort * *,int *)
0x1801b048e  mov     edi, eax
0x1801b0490  mov     rsi, [rsp+5D0h+var_598]
0x1801b0495  mov     r12d, [rsp+5D0h+var_5A0]
0x1801b049a  test    edi, edi
0x1801b049c  js      loc_1801B0813
0x1801b04a2  movsxd  rdx, r12d; unsigned __int64
0x1801b04a5  lea     r8, asc_18062EBF0; ";"
0x1801b04ac  mov     rcx, rsi; unsigned __int16 *
0x1801b04af  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801b04b4  test    eax, eax
0x1801b04b6  js      loc_1801B0813
0x1801b04bc  mov     r12d, r15d
0x1801b04bf  xor     r15d, r15d
0x1801b04c2  jmp     loc_1801B058D
0x1801b04c7  mov     [rsp+5D0h+bIgnoreCase], 1; bIgnoreCase
0x1801b04cf  or      r9d, 0FFFFFFFFh; cchCount2
0x1801b04d3  lea     r8, aCommand_0; "command"
0x1801b04da  or      edx, r9d; cchCount1
0x1801b04dd  mov     rcx, [rsp+5D0h+lpString1]; lpString1
0x1801b04e2  call    cs:__imp_CompareStringOrdinal
0x1801b04e9  nop     dword ptr [rax+rax+00h]
0x1801b04ee  cmp     eax, 2
0x1801b04f1  jnz     loc_1801B059C
0x1801b04f7  test    r15b, r15b
  ... truncated ...
```
