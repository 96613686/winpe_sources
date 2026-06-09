# CEventNotifier::SavePersistentEventCB(ushort *,_GUID const *,_GUID const *,ushort const *,ushort *,ushort *,ushort *,int *,ulong *,int)

- ea: `0x1800245f0`
- end: `0x180024caa`
- name: `?SavePersistentEventCB@CEventNotifier@@AEAAJPEAGPEBU_GUID@@1PEBG000PEAHPEAKH@Z`
- size: `1722`
- prototype: `__int64 __fastcall(CEventNotifier *this, unsigned __int16 *, const struct _GUID *, struct _GUID *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int *, unsigned int *, int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800315a0`

## callees

- `0x180009474`
- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x1800245f0`
- `0x180024cb0`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e1ac`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180034658`
- `0x18003b854`
- `0x18003ba10`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002472c`
- `ADVAPI32!RegCloseKey` at `0x18002474e`
- `ADVAPI32!RegCloseKey` at `0x18002472c`
- `ADVAPI32!RegCloseKey` at `0x18002474e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800248b6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800248b6`
- `ADVAPI32!RegDeleteKeyW` at `0x180024745`
- `ADVAPI32!RegDeleteKeyW` at `0x180024745`
- `ADVAPI32!RegCreateKeyExW` at `0x180024909`
- `ADVAPI32!RegCreateKeyExW` at `0x180024909`
- `ADVAPI32!RegSetValueExW` at `0x1800249cf`
- `ADVAPI32!RegSetValueExW` at `0x180024a73`
- `ADVAPI32!RegSetValueExW` at `0x180024ae5`
- `ADVAPI32!RegSetValueExW` at `0x180024b63`
- `ADVAPI32!RegSetValueExW` at `0x180024c36`
- `ADVAPI32!RegSetValueExW` at `0x1800249cf`
- `ADVAPI32!RegSetValueExW` at `0x180024a73`
- `ADVAPI32!RegSetValueExW` at `0x180024ae5`
- `ADVAPI32!RegSetValueExW` at `0x180024b63`
- `ADVAPI32!RegSetValueExW` at `0x180024c36`
- `KERNEL32!lstrlenW` at `0x180024c09`
- `KERNEL32!lstrlenW` at `0x180024c09`
- `ole32!StringFromGUID2` at `0x1800248cd`
- `ole32!StringFromGUID2` at `0x1800248cd`

## string_xrefs

- `0x180024b72`: `RegSetValueEx() failed for cmdline`
- `0x180024b98`: `RegSetValueEx() failed for cmdline`
- `0x180024af4`: `RegSetValueEx() failed for icon`
- `0x180024b1a`: `RegSetValueEx() failed for icon`
- `0x18002491a`: `RegCreateKeyEx() failed for CallbackCLSIDs subkey. lRet = %d`
- `0x180024943`: `RegCreateKeyEx() failed for CallbackCLSIDs subkey. lRet = %d`
- `0x180024a82`: `RegSetValueEx() failed for description`
- `0x180024aa8`: `RegSetValueEx() failed for description`
- `0x1800249de`: `RegSetValueEx() failed for name`
- `0x180024a04`: `RegSetValueEx() failed for name`

## pseudocode

```c
__int64 __fastcall CEventNotifier::SavePersistentEventCB(
        CEventNotifier *this,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        struct _GUID *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        int *a9,
        unsigned int *a10,
        int a11)
{
  const unsigned __int16 *v11; // r12
  struct tagWiaTraceData_Type *v14; // rax
  char *v15; // rdx
  unsigned int v16; // r8d
  CEventNotifier *v17; // rcx
  HKEY v18; // r14
  char *v19; // rbx
  void *v20; // rdx
  void *v21; // rax
  int v22; // edx
  int v23; // ecx
  signed int EventByGUID; // esi
  BYTE *v25; // r13
  int v26; // ebx
  __int64 v27; // rax
  __int64 v28; // rax
  CEventNotifier *v30; // rcx
  HKEY v31; // rcx
  LSTATUS v32; // r12d
  char *v33; // rbx
  void *v34; // rdx
  void *v35; // rax
  int v36; // edx
  int v37; // ecx
  __int64 v38; // rbx
  __int64 v39; // rax
  LSTATUS v40; // r12d
  char *v41; // rbx
  void *v42; // rdx
  void *v43; // rax
  int v44; // edx
  int v45; // ecx
  __int64 v46; // rax
  char *v47; // rbx
  void *v48; // rdx
  __int64 v49; // rax
  char *v50; // rbx
  void *v51; // rdx
  char *v52; // rbx
  void *v53; // rdx
  char *v54; // rbx
  void *v55; // rdx
  void *v56; // rax
  int v57; // edx
  int v58; // ecx
  int v59; // eax
  LSTATUS v60; // edi
  char *v61; // rbx
  void *v62; // rdx
  void *v63; // rax
  int v64; // edx
  int v65; // ecx
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  HKEY v69; // [rsp+78h] [rbp-88h] BYREF
  BYTE *lpData; // [rsp+80h] [rbp-80h]
  GUID *rguid; // [rsp+88h] [rbp-78h]
  BYTE *v72; // [rsp+90h] [rbp-70h]
  BYTE *v73; // [rsp+98h] [rbp-68h]
  _BYTE v74[80]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v75[38]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v76[38]; // [rsp+220h] [rbp+120h] BYREF
  WCHAR SubKey[40]; // [rsp+350h] [rbp+250h] BYREF

  v11 = a5;
  lpData = (BYTE *)a6;
  v73 = (BYTE *)a7;
  v72 = (BYTE *)a8;
  rguid = a4;
  v14 = (struct tagWiaTraceData_Type *)WiaTrace_Trace((const char *)&word_18007CF56);
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v74, v15, v16, "CEventNotifier::SavePersistentEventCB", lpcSubKeys, v14);
  dwDisposition = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  v69 = 0;
  v18 = 0;
  hKey = 0;
  if ( a9 )
    *a9 = 0;
  if ( a2 && !(unsigned int)ActionGuidExists(a2, a3) )
  {
    v19 = (char *)WiaTrace_TraceLog("ActionGuidExists() returned FALSE");
    WriteDbgTraceErrorWI("CEventNotifier::SavePersistentEventCB", v19);
    WiaTrcLib::Free((WiaTrcLib *)v19, v20);
    v21 = (void *)WiaTrace_Trace("ActionGuidExists() returned FALSE");
    WiaTrace_ProcessTrace_Ex(v23, v22, (int)"CEventNotifier::SavePersistentEventCB", 1, v21);
    EventByGUID = -2147467259;
LABEL_6:
    v25 = lpData;
    goto LABEL_7;
  }
  EventByGUID = CEventNotifier::FindEventByGUID(v17, a2, a3, &v69);
  if ( EventByGUID < 0 )
    EventByGUID = CEventNotifier::AddEventGUID(v30, a2, a3, &v69);
  v18 = v69;
  if ( EventByGUID )
    goto LABEL_6;
  if ( a10 )
  {
    v31 = v69;
    *a10 = 0;
    RegQueryInfoKeyW(v31, 0, 0, 0, a10, 0, 0, 0, 0, 0, 0, 0);
  }
  StringFromGUID2(rguid, SubKey, 40);
  v32 = RegCreateKeyExW(v18, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  if ( v32 )
  {
    v33 = (char *)WiaTrace_TraceLog("RegCreateKeyEx() failed for CallbackCLSIDs subkey. lRet = %d");
    WriteDbgTraceErrorWI("CEventNotifier::SavePersistentEventCB", v33);
    WiaTrcLib::Free((WiaTrcLib *)v33, v34);
    v35 = (void *)WiaTrace_Trace("RegCreateKeyEx() failed for CallbackCLSIDs subkey. lRet = %d", v32);
    WiaTrace_ProcessTrace_Ex(v37, v36, (int)"CEventNotifier::SavePersistentEventCB", 1, v35);
    if ( v32 > 0 )
      EventByGUID = (unsigned __int16)v32 | 0x80070000;
    else
      EventByGUID = v32;
    v11 = a5;
    goto LABEL_6;
  }
  if ( dwDisposition == 1 && a9 )
    *a9 = 1;
  v25 = lpData;
  v38 = -1;
  v39 = -1;
  do
    ++v39;
  while ( *(_WORD *)&lpData[2 * v39] );
  v40 = RegSetValueExW(hKey, L"Name", 0, 1u, lpData, 2 * v39 + 2);
  if ( v40 )
  {
    v41 = (char *)WiaTrace_TraceLog("RegSetValueEx() failed for name");
    WriteDbgTraceErrorWI("CEventNotifier::SavePersistentEventCB", v41);
    WiaTrcLib::Free((WiaTrcLib *)v41, v42);
    v43 = (void *)WiaTrace_Trace("RegSetValueEx() failed for name");
LABEL_42:
    WiaTrace_ProcessTrace_Ex(v45, v44, (int)"CEventNotifier::SavePersistentEventCB", 1, v43);
    if ( v40 > 0 )
      EventByGUID = (unsigned __int16)v40 | 0x80070000;
    else
      EventByGUID = v40;
    v11 = a5;
    goto LABEL_7;
  }
  v46 = -1;
  do
    ++v46;
  while ( *(_WORD *)&v73[2 * v46] );
  v40 = RegSetValueExW(hKey, L"Desc", 0, 1u, v73, 2 * v46 + 2);
  if ( v40 )
  {
    v47 = (char *)WiaTrace_TraceLog("RegSetValueEx() failed for description");
    WriteDbgTraceErrorWI("CEventNotifier::SavePersistentEventCB", v47);
    WiaTrcLib::Free((WiaTrcLib *)v47, v48);
    v43 = (void *)WiaTrace_Trace("RegSetValueEx() failed for description");
    goto LABEL_42;
  }
  v49 = -1;
  do
    ++v49;
  while ( *(_WORD *)&v72[2 * v49] );
  v40 = RegSetValueExW(hKey, L"Icon", 0, 1u, v72, 2 * v49 + 2);
  if ( v40 )
  {
    v50 = (char *)WiaTrace_TraceLog("RegSetValueEx() failed for icon");
    WriteDbgTraceErrorWI("CEventNotifier::SavePersistentEventCB", v50);
    WiaTrcLib::Free((WiaTrcLib *)v50, v51);
    v43 = (void *)WiaTrace_Trace("RegSetValueEx() failed for icon");
    goto LABEL_42;
  }
  v11 = a5;
  if ( a5 && *a5 )
  {
    do
      ++v38;
    while ( a5[v38] );
    v40 = RegSetValueExW(hKey, L"Cmdline", 0, 1u, (const BYTE *)a5, 2 * v38 + 2);
    if ( v40 )
    {
      v52 = (char *)WiaTrace_TraceLog("RegSetValueEx() failed for cmdline");
      WriteDbgTraceErrorWI("CEventNotifier::SavePersistentEventCB", v52);
      WiaTrcLib::Free((WiaTrcLib *)v52, v53);
      v43 = (void *)WiaTrace_Trace("RegSetValueEx() failed for cmdline");
      goto LABEL_42;
    }
    v11 = a5;
  }
  if ( a11 )
  {
    v54 = (char *)WiaTrace_TraceLogWithSubComp(0, "Writing DEFAULT_HANDLER_VAL");
    WriteDbgTraceWarningWI("CEventNotifier::SavePersistentEventCB", v54);
    WiaTrcLib::Free((WiaTrcLib *)v54, v55);
    v56 = (void *)WiaTrace_TraceWithSubComp(0, "Writing DEFAULT_HANDLER_VAL");
    WiaTrace_ProcessTrace_Ex(v58, v57, (int)"CEventNotifier::SavePersistentEventCB", 2, v56);
    v59 = lstrlenW(SubKey);
    v60 = RegSetValueExW(v18, L"DefaultHandler", 0, 1u, (const BYTE *)SubKey, 2 * v59 + 2);
    v61 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Setting as default: %S, lRet = %d", SubKey, v60);
    WriteDbgTraceInfoWI("CEventNotifier::SavePersistentEventCB", v61);
    WiaTrcLib::Free((WiaTrcLib *)v61, v62);
    v63 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Setting as default: %S, lRet = %d", SubKey, v60);
    WiaTrace_ProcessTrace_Ex(v65, v64, (int)"CEventNotifier::SavePersistentEventCB", 4, v63);
  }
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v18 )
  {
    if ( EventByGUID < 0 )
      RegDeleteKeyW(v18, SubKey);
    RegCloseKey(v18);
  }
  if ( EventByGUID >= 0 )
  {
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v76, v25);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v75, L"Internal");
    v26 = CSimpleStringBase<unsigned short>::CompareNoCase(v76, v75);
    v75[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v75);
    if ( v26 && a3 )
    {
      v27 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&WIA_EVENT_STI_PROXY.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&WIA_EVENT_STI_PROXY.Data1 )
        v27 = *(_QWORD *)a3->Data4 - *(_QWORD *)WIA_EVENT_STI_PROXY.Data4;
      if ( !v27 )
        goto LABEL_22;
      v28 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&WIA_EVENT_DEVICE_CONNECTED.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&WIA_EVENT_DEVICE_CONNECTED.Data1 )
        v28 = *(_QWORD *)a3->Data4 - *(_QWORD *)WIA_EVENT_DEVICE_CONNECTED.Data4;
      if ( !v28 )
LABEL_22:
        AddWiaHandlerToWindowsAutoPlay(
          (const unsigned __int16 *)v25,
          (const unsigned __int16 *)v73,
          (const unsigned __int16 *)v72,
          rguid,
          v11);
    }
    v76[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v76);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v74);
  return (unsigned int)EventByGUID;
}

```

## disassembly

```asm
0x1800245f0  mov     [rsp-8+arg_0], rbx
0x1800245f5  push    rbp
0x1800245f6  push    rsi
0x1800245f7  push    rdi
0x1800245f8  push    r12
0x1800245fa  push    r13
0x1800245fc  push    r14
0x1800245fe  push    r15
0x180024600  lea     rbp, [rsp-2B0h]
0x180024608  sub     rsp, 3B0h
0x18002460f  mov     rax, cs:__security_cookie
0x180024616  xor     rax, rsp
0x180024619  mov     [rbp+2E0h+var_40], rax
0x180024620  mov     rax, [rbp+2E0h+arg_28]
0x180024627  lea     rcx, word_18007CF56
0x18002462e  mov     r12, [rbp+2E0h+arg_20]
0x180024635  mov     r15, r8
0x180024638  mov     r13, [rbp+2E0h+arg_40]
0x18002463f  mov     rbx, rdx
0x180024642  mov     rdi, [rbp+2E0h+arg_48]
0x180024649  mov     [rbp+2E0h+lpData], rax
0x18002464d  mov     rax, [rbp+2E0h+arg_30]
0x180024654  mov     [rbp+2E0h+var_348], rax
0x180024658  mov     rax, [rbp+2E0h+arg_38]
0x18002465f  mov     [rbp+2E0h+var_350], rax
0x180024663  mov     [rbp+2E0h+rguid], r9
0x180024667  mov     [rsp+3E0h+var_380], r12
0x18002466c  call    WiaTrace_Trace
0x180024671  lea     r9, aCeventnotifier_7; "CEventNotifier::SavePersistentEventCB"
0x180024678  mov     [rsp+3E0h+lpcbMaxSubKeyLen], rax; struct tagWiaTraceData_Type *
0x18002467d  lea     rcx, [rbp+2E0h+var_340]; this
0x180024681  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180024686  xor     esi, esi
0x180024688  lea     rcx, [rbp+2E0h+SubKey]; void *
0x18002468f  xor     edx, edx; Val
0x180024691  mov     [rsp+3E0h+dwDisposition], esi
0x180024695  lea     r8d, [rsi+50h]; Size
0x180024699  call    memset_0
0x18002469e  mov     [rsp+3E0h+var_368], rsi
0x1800246a3  mov     r14d, esi
0x1800246a6  mov     [rsp+3E0h+hKey], rsi
0x1800246ab  test    r13, r13
0x1800246ae  jz      short loc_1800246B4
0x1800246b0  mov     [r13+0], esi
0x1800246b4  test    rbx, rbx
0x1800246b7  jz      loc_180024843
0x1800246bd  mov     rdx, r15; struct _GUID *
0x1800246c0  mov     rcx, rbx; unsigned __int16 *
0x1800246c3  call    ?ActionGuidExists@@YAHPEAGPEBU_GUID@@@Z; ActionGuidExists(ushort *,_GUID const *)
0x1800246c8  test    eax, eax
0x1800246ca  jnz     loc_180024843
0x1800246d0  lea     rcx, aActionguidexis_0; "ActionGuidExists() returned FALSE"
0x1800246d7  call    WiaTrace_TraceLog
0x1800246dc  mov     rdx, rax; char *
0x1800246df  lea     rcx, aCeventnotifier_7; "CEventNotifier::SavePersistentEventCB"
0x1800246e6  mov     rbx, rax
0x1800246e9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800246ee  mov     rcx, rbx; this
0x1800246f1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800246f6  lea     rcx, aActionguidexis_0; "ActionGuidExists() returned FALSE"
0x1800246fd  call    WiaTrace_Trace
0x180024702  mov     r9d, 1; int
0x180024708  mov     [rsp+3E0h+lpcSubKeys], rax; lpMem
0x18002470d  lea     r8, aCeventnotifier_7; "CEventNotifier::SavePersistentEventCB"
0x180024714  call    WiaTrace_ProcessTrace_Ex
0x180024719  mov     esi, 80004005h
0x18002471e  mov     r13, [rbp+2E0h+lpData]
0x180024722  mov     rcx, [rsp+3E0h+hKey]; hKey
0x180024727  test    rcx, rcx
0x18002472a  jz      short loc_180024732
0x18002472c  call    cs:__imp_RegCloseKey
0x180024732  test    r14, r14
0x180024735  jz      short loc_180024754
0x180024737  test    esi, esi
0x180024739  jns     short loc_18002474B
0x18002473b  lea     rdx, [rbp+2E0h+SubKey]; lpSubKey
0x180024742  mov     rcx, r14; hKey
0x180024745  call    cs:__imp_RegDeleteKeyW
0x18002474b  mov     rcx, r14; hKey
0x18002474e  call    cs:__imp_RegCloseKey
0x180024754  test    esi, esi
0x180024756  js      loc_18002480E
0x18002475c  mov     rdx, r13
0x18002475f  lea     rcx, [rbp+2E0h+var_1C0]
0x180024766  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18002476b  lea     rdx, aInternal; "Internal"
0x180024772  lea     rcx, [rbp+2E0h+var_2F0]
0x180024776  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18002477b  lea     rdx, [rbp+2E0h+var_2F0]
0x18002477f  lea     rcx, [rbp+2E0h+var_1C0]
0x180024786  call    ?CompareNoCase@?$CSimpleStringBase@G@@QEBAHAEBV1@H@Z; CSimpleStringBase<ushort>::CompareNoCase(CSimpleStringBase<ushort> const &,int)
0x18002478b  lea     rdi, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180024792  mov     ebx, eax
0x180024794  lea     rcx, [rbp+2E0h+var_2F0]
0x180024798  mov     [rbp+2E0h+var_2F0], rdi
0x18002479c  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800247a1  test    ebx, ebx
0x1800247a3  jz      short loc_1800247FB
0x1800247a5  test    r15, r15
0x1800247a8  jz      short loc_1800247FB
0x1800247aa  mov     rax, [r15]
0x1800247ad  sub     rax, qword ptr cs:WIA_EVENT_STI_PROXY.Data1
0x1800247b4  jnz     short loc_1800247C1
0x1800247b6  mov     rax, [r15+8]
0x1800247ba  sub     rax, qword ptr cs:WIA_EVENT_STI_PROXY.Data4
0x1800247c1  test    rax, rax
0x1800247c4  jz      short loc_1800247E2
0x1800247c6  mov     rax, [r15]
0x1800247c9  sub     rax, qword ptr cs:WIA_EVENT_DEVICE_CONNECTED.Data1
0x1800247d0  jnz     short loc_1800247DD
0x1800247d2  mov     rax, [r15+8]
0x1800247d6  sub     rax, qword ptr cs:WIA_EVENT_DEVICE_CONNECTED.Data4
0x1800247dd  test    rax, rax
0x1800247e0  jnz     short loc_1800247FB
0x1800247e2  mov     r9, [rbp+2E0h+rguid]; struct _GUID *
0x1800247e6  mov     rcx, r13; unsigned __int16 *
0x1800247e9  mov     r8, [rbp+2E0h+var_350]; unsigned __int16 *
0x1800247ed  mov     rdx, [rbp+2E0h+var_348]; unsigned __int16 *
0x1800247f1  mov     [rsp+3E0h+lpcSubKeys], r12; unsigned __int16 *
0x1800247f6  call    ?AddWiaHandlerToWindowsAutoPlay@@YAXPEBG00PEBU_GUID@@0@Z; AddWiaHandlerToWindowsAutoPlay(ushort const *,ushort const *,ushort const *,_GUID const *,ushort const *)
0x1800247fb  lea     rcx, [rbp+2E0h+var_1C0]
0x180024802  mov     [rbp+2E0h+var_1C0], rdi
0x180024809  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18002480e  lea     rcx, [rbp+2E0h+var_340]; this
0x180024812  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180024817  mov     eax, esi
0x180024819  mov     rcx, [rbp+2E0h+var_40]
0x180024820  xor     rcx, rsp; StackCookie
0x180024823  call    __security_check_cookie
0x180024828  mov     rbx, [rsp+3E0h+arg_0]
0x180024830  add     rsp, 3B0h
0x180024837  pop     r15
0x180024839  pop     r14
0x18002483b  pop     r13
0x18002483d  pop     r12
0x18002483f  pop     rdi
0x180024840  pop     rsi
0x180024841  pop     rbp
0x180024842  retn
0x180024843  lea     r9, [rsp+3E0h+var_368]; HKEY *
0x180024848  mov     r8, r15; struct _GUID *
0x18002484b  mov     rdx, rbx; unsigned __int16 *
0x18002484e  call    ?FindEventByGUID@CEventNotifier@@AEAAJPEAGPEBU_GUID@@PEAPEAUHKEY__@@@Z; CEventNotifier::FindEventByGUID(ushort *,_GUID const *,HKEY__ * *)
0x180024853  mov     esi, eax
0x180024855  test    eax, eax
0x180024857  jns     short loc_18002486B
0x180024859  lea     r9, [rsp+3E0h+var_368]; HKEY *
0x18002485e  mov     r8, r15; struct _GUID *
0x180024861  mov     rdx, rbx; unsigned __int16 *
0x180024864  call    ?AddEventGUID@CEventNotifier@@AEAAJPEAGPEBU_GUID@@PEAPEAUHKEY__@@@Z; CEventNotifier::AddEventGUID(ushort *,_GUID const *,HKEY__ * *)
0x180024869  mov     esi, eax
0x18002486b  mov     r14, [rsp+3E0h+var_368]
0x180024870  test    esi, esi
0x180024872  jnz     loc_18002471E
0x180024878  xor     r12d, r12d
0x18002487b  test    rdi, rdi
0x18002487e  jz      short loc_1800248BC
0x180024880  mov     [rsp+3E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180024885  xor     r9d, r9d; lpReserved
0x180024888  mov     [rsp+3E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18002488d  xor     r8d, r8d; lpcchClass
0x180024890  mov     [rsp+3E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180024895  xor     edx, edx; lpClass
0x180024897  mov     [rsp+3E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18002489c  mov     rcx, r14; hKey
0x18002489f  mov     [rsp+3E0h+lpcValues], r12; lpcValues
0x1800248a4  mov     [rsp+3E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800248a9  mov     [rsp+3E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800248ae  mov     [rsp+3E0h+lpcSubKeys], rdi; lpcSubKeys
0x1800248b3  mov     [rdi], r12d
0x1800248b6  call    cs:__imp_RegQueryInfoKeyW
0x1800248bc  mov     rcx, [rbp+2E0h+rguid]; rguid
0x1800248c0  lea     rdx, [rbp+2E0h+SubKey]; lpsz
0x1800248c7  mov     r8d, 28h ; '('; cchMax
0x1800248cd  call    cs:__imp_StringFromGUID2
0x1800248d3  lea     rax, [rsp+3E0h+dwDisposition]
0x1800248d8  xor     r9d, r9d; lpClass
0x1800248db  mov     [rsp+3E0h+lpcbMaxValueNameLen], rax; lpdwDisposition
0x1800248e0  lea     rdx, [rbp+2E0h+SubKey]; lpSubKey
0x1800248e7  lea     rax, [rsp+3E0h+hKey]
0x1800248ec  xor     r8d, r8d; Reserved
0x1800248ef  mov     [rsp+3E0h+lpcValues], rax; phkResult
0x1800248f4  mov     rcx, r14; hKey
0x1800248f7  mov     [rsp+3E0h+lpcbMaxClassLen], r12; lpSecurityAttributes
0x1800248fc  mov     dword ptr [rsp+3E0h+lpcbMaxSubKeyLen], 2001Fh; samDesired
0x180024904  mov     dword ptr [rsp+3E0h+lpcSubKeys], r12d; dwOptions
0x180024909  call    cs:__imp_RegCreateKeyExW
0x18002490f  xor     ecx, ecx
0x180024911  mov     r12d, eax
0x180024914  test    eax, eax
0x180024916  jz      short loc_180024984
0x180024918  mov     edx, eax
0x18002491a  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx() failed for CallbackCLS"...
0x180024921  call    WiaTrace_TraceLog
0x180024926  mov     rdx, rax; char *
0x180024929  lea     rcx, aCeventnotifier_7; "CEventNotifier::SavePersistentEventCB"
0x180024930  mov     rbx, rax
0x180024933  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180024938  mov     rcx, rbx; this
0x18002493b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180024940  mov     edx, r12d
0x180024943  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx() failed for CallbackCLS"...
0x18002494a  call    WiaTrace_Trace
0x18002494f  mov     r9d, 1; int
0x180024955  mov     [rsp+3E0h+lpcSubKeys], rax; lpMem
0x18002495a  lea     r8, aCeventnotifier_7; "CEventNotifier::SavePersistentEventCB"
0x180024961  call    WiaTrace_ProcessTrace_Ex
0x180024966  test    r12d, r12d
0x180024969  jg      short loc_180024970
0x18002496b  mov     esi, r12d
0x18002496e  jmp     short loc_18002497A
0x180024970  movzx   esi, r12w
0x180024974  or      esi, 80070000h
0x18002497a  mov     r12, [rsp+3E0h+var_380]
0x18002497f  jmp     loc_18002471E
0x180024984  mov     edi, 1
0x180024989  cmp     [rsp+3E0h+dwDisposition], edi
0x18002498d  jnz     short loc_180024998
0x18002498f  test    r13, r13
0x180024992  jz      short loc_180024998
0x180024994  mov     [r13+0], edi
0x180024998  mov     r13, [rbp+2E0h+lpData]
0x18002499c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800249a0  mov     rax, rbx
0x1800249a3  inc     rax
0x1800249a6  cmp     [r13+rax*2+0], cx
0x1800249ac  jnz     short loc_1800249A3
0x1800249ae  mov     rcx, [rsp+3E0h+hKey]; hKey
0x1800249b3  lea     rdx, aName; "Name"
0x1800249ba  add     rax, rax
0x1800249bd  mov     r9d, edi; dwType
0x1800249c0  add     eax, 2
0x1800249c3  xor     r8d, r8d; Reserved
0x1800249c6  mov     dword ptr [rsp+3E0h+lpcbMaxSubKeyLen], eax; cbData
0x1800249ca  mov     [rsp+3E0h+lpcSubKeys], r13; lpData
0x1800249cf  call    cs:__imp_RegSetValueExW
0x1800249d5  xor     edx, edx
0x1800249d7  mov     r12d, eax
0x1800249da  test    eax, eax
0x1800249dc  jz      short loc_180024A42
0x1800249de  lea     rcx, aRegsetvalueexF_0; "RegSetValueEx() failed for name"
0x1800249e5  call    WiaTrace_TraceLog
0x1800249ea  mov     rdx, rax; char *
0x1800249ed  lea     rcx, aCeventnotifier_7; "CEventNotifier::SavePersistentEventCB"
0x1800249f4  mov     rbx, rax
0x1800249f7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800249fc  mov     rcx, rbx; this
0x1800249ff  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180024a04  lea     rcx, aRegsetvalueexF_0; "RegSetValueEx() failed for name"
0x180024a0b  call    WiaTrace_Trace
0x180024a10  mov     r9d, edi; int
0x180024a13  mov     [rsp+3E0h+lpcSubKeys], rax; lpMem
0x180024a18  lea     r8, aCeventnotifier_7; "CEventNotifier::SavePersistentEventCB"
0x180024a1f  call    WiaTrace_ProcessTrace_Ex
0x180024a24  test    r12d, r12d
0x180024a27  jg      short loc_180024A2E
0x180024a29  mov     esi, r12d
0x180024a2c  jmp     short loc_180024A38
0x180024a2e  movzx   esi, r12w
0x180024a32  or      esi, 80070000h
0x180024a38  mov     r12, [rsp+3E0h+var_380]
0x180024a3d  jmp     loc_180024722
0x180024a42  mov     rcx, [rbp+2E0h+var_348]
0x180024a46  mov     rax, rbx
0x180024a49  inc     rax
0x180024a4c  cmp     [rcx+rax*2], dx
0x180024a50  jnz     short loc_180024A49
0x180024a52  add     rax, rax
0x180024a55  lea     rdx, aDesc; "Desc"
0x180024a5c  add     eax, 2
0x180024a5f  mov     r9d, edi; dwType
0x180024a62  mov     dword ptr [rsp+3E0h+lpcbMaxSubKeyLen], eax; cbData
0x180024a66  xor     r8d, r8d; Reserved
0x180024a69  mov     [rsp+3E0h+lpcSubKeys], rcx; lpData
0x180024a6e  mov     rcx, [rsp+3E0h+hKey]; hKey
0x180024a73  call    cs:__imp_RegSetValueExW
0x180024a79  xor     edx, edx
0x180024a7b  mov     r12d, eax
0x180024a7e  test    eax, eax
0x180024a80  jz      short loc_180024AB4
0x180024a82  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed for description"
0x180024a89  call    WiaTrace_TraceLog
0x180024a8e  mov     rdx, rax; char *
0x180024a91  lea     rcx, aCeventnotifier_7; "CEventNotifier::SavePersistentEventCB"
0x180024a98  mov     rbx, rax
0x180024a9b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180024aa0  mov     rcx, rbx; this
0x180024aa3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180024aa8  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed for description"
0x180024aaf  jmp     loc_180024A0B
0x180024ab4  mov     rcx, [rbp+2E0h+var_350]
0x180024ab8  mov     rax, rbx
0x180024abb  inc     rax
0x180024abe  cmp     [rcx+rax*2], dx
0x180024ac2  jnz     short loc_180024ABB
0x180024ac4  add     rax, rax
0x180024ac7  lea     rdx, aIcon; "Icon"
0x180024ace  add     eax, 2
0x180024ad1  mov     r9d, edi; dwType
0x180024ad4  mov     dword ptr [rsp+3E0h+lpcbMaxSubKeyLen], eax; cbData
  ... truncated ...
```
