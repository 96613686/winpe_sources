# CEventNotifier::RegisterEventCallback(long,ushort *,_GUID const *,_GUID const *,ushort const *,ushort *,ushort *,ushort *)

- ea: `0x1800315a0`
- end: `0x18003244d`
- name: `?RegisterEventCallback@CEventNotifier@@QEAAJJPEAGPEBU_GUID@@1PEBG000@Z`
- size: `3757`
- prototype: `__int64 __fastcall(CEventNotifier *this, int, unsigned __int64, const struct _GUID *, struct _GUID *Buf1, LPCWSTR lpString, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800315a0`
- `0x180056dd8`
- `0x1800571f8`

## callees

- `0x180002610`
- `0x180004380`
- `0x1800045e0`
- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x1800245f0`
- `0x180025aec`
- `0x180025e4c`
- `0x180026380`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x18002f290`
- `0x180030294`
- `0x1800315a0`
- `0x180033cc0`
- `0x180034658`
- `0x18003c2a4`
- `0x18003cc00`
- `0x1800775fc`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180031931`
- `KERNEL32!GetSystemTime` at `0x180031a76`
- `KERNEL32!GetSystemTime` at `0x180031931`
- `KERNEL32!GetSystemTime` at `0x180031a76`
- `KERNEL32!SystemTimeToFileTime` at `0x180031943`
- `KERNEL32!SystemTimeToFileTime` at `0x180031a8a`
- `KERNEL32!SystemTimeToFileTime` at `0x180031943`
- `KERNEL32!SystemTimeToFileTime` at `0x180031a8a`
- `KERNEL32!lstrlenW` at `0x180031732`
- `KERNEL32!lstrlenW` at `0x180031732`
- `OLEAUT32!__imp_SysAllocString` at `0x180031c7a`
- `OLEAUT32!__imp_SysAllocString` at `0x180031e0c`
- `OLEAUT32!__imp_SysAllocString` at `0x180031ea1`
- `OLEAUT32!__imp_SysAllocString` at `0x18003228c`
- `OLEAUT32!__imp_SysAllocString` at `0x180032316`
- `OLEAUT32!__imp_SysAllocString` at `0x180031c7a`
- `OLEAUT32!__imp_SysAllocString` at `0x180031e0c`
- `OLEAUT32!__imp_SysAllocString` at `0x180031ea1`
- `OLEAUT32!__imp_SysAllocString` at `0x18003228c`
- `OLEAUT32!__imp_SysAllocString` at `0x180032316`
- `OLEAUT32!__imp_SysFreeString` at `0x180031cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180031ee3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003235a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800323a6`
- `OLEAUT32!__imp_SysFreeString` at `0x180031cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180031ee3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003235a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800323a6`
- `RPCRT4!UuidCreate` at `0x1800317b5`
- `RPCRT4!UuidCreate` at `0x1800317b5`

## string_xrefs

- `0x180031748`: `ptszCommandline is greater than MAX_PATH characters!`
- `0x18003176e`: `ptszCommandline is greater than MAX_PATH characters!`
- `0x180031957`: `Found event node  EvName=%S CommandLine=%S`
- `0x180031986`: `Found event node  EvName=%S CommandLine=%S`
- `0x180031b67`: `SavePersistentEventCB CommandLine=%S failed!`
- `0x180031b91`: `SavePersistentEventCB CommandLine=%S failed!`

## pseudocode

```c
__int64 __fastcall CEventNotifier::RegisterEventCallback(
        CEventNotifier *this,
        int a2,
        unsigned __int64 a3,
        const struct _GUID *a4,
        struct _GUID *Buf1,
        LPCWSTR lpString,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9)
{
  struct tagWiaTraceData_Type *v13; // rax
  char *v14; // rdx
  unsigned int v15; // r8d
  char *v16; // rbx
  void *v17; // rdx
  void *v18; // rax
  int v19; // edx
  int v20; // ecx
  CEventNotifier *v21; // rcx
  __int64 v22; // rax
  char *v23; // rbx
  void *v24; // rdx
  void *v25; // rax
  int v26; // edx
  int v27; // ecx
  int CLSIDForCommandline; // r14d
  CEventNotifier *v29; // rcx
  char *v30; // rbx
  void *v31; // rdx
  void *v32; // rax
  int v33; // edx
  int v34; // ecx
  RPC_STATUS v35; // ebx
  int v37; // r13d
  int v38; // r13d
  const WCHAR *v39; // r8
  char *v40; // rbx
  void *v41; // rdx
  const WCHAR *v42; // r8
  void *v43; // rax
  int v44; // edx
  int v45; // ecx
  CEventNotifier *v46; // rcx
  unsigned int v47; // edx
  CEventNotifier *v48; // rcx
  unsigned int v49; // edx
  CEventNotifier *v50; // rcx
  struct __EventDestNode__ *EventCBNode; // r13
  char *v52; // rbx
  void *v53; // rdx
  void *v54; // rax
  int v55; // edx
  int v56; // ecx
  CEventNotifier *v57; // rcx
  CEventNotifier *v58; // rcx
  const WCHAR *v59; // r12
  const WCHAR *v60; // r8
  char *v61; // rbx
  void *v62; // rdx
  void *v63; // rax
  int v64; // edx
  int v65; // ecx
  int v66; // r9d
  const WCHAR *v67; // r8
  char *v68; // rbx
  void *v69; // rdx
  const WCHAR *v70; // r8
  void *v71; // rax
  int v72; // edx
  int v73; // ecx
  int v74; // ebx
  char *v75; // rbx
  void *v76; // rdx
  void *v77; // rax
  int v78; // edx
  int v79; // ecx
  CEventNotifier *v80; // rcx
  const WCHAR *v81; // r12
  const WCHAR *v82; // r8
  char *v83; // rbx
  void *v84; // rdx
  const WCHAR *v85; // r8
  void *v86; // rax
  int v87; // edx
  int v88; // ecx
  unsigned __int16 *v89; // rax
  OLECHAR *v90; // rbx
  const WCHAR *v91; // r8
  char *v92; // rbx
  void *v93; // rdx
  CEventNotifier *v94; // rcx
  char *v95; // rbx
  void *v96; // rdx
  char *v97; // rbx
  void *v98; // rdx
  void *v99; // rax
  int v100; // edx
  int v101; // ecx
  const OLECHAR *v102; // rcx
  CEventNotifier *v103; // rcx
  unsigned __int16 *v104; // r12
  char *v105; // rbx
  void *v106; // rdx
  void *v107; // rax
  int v108; // edx
  int v109; // ecx
  unsigned __int16 *v110; // rax
  OLECHAR *v111; // rbx
  char *v112; // rbx
  void *v113; // rdx
  void *v114; // rax
  int v115; // edx
  int v116; // ecx
  OLECHAR *v117; // rcx
  char *v118; // rbx
  void *v119; // rdx
  void *v120; // rax
  int v121; // edx
  int v122; // ecx
  const WCHAR *v123; // rdi
  const WCHAR *v124; // r9
  char *v125; // rbx
  void *v126; // rdx
  void *v127; // rax
  int v128; // edx
  int v129; // ecx
  unsigned __int16 *v130; // rdi
  char *v131; // rbx
  void *v132; // rdx
  void *v133; // rax
  int v134; // edx
  int v135; // ecx
  unsigned int v136; // edx
  CEventNotifier *v137; // rcx
  unsigned __int16 *v138; // rdi
  unsigned __int16 *v139; // r13
  unsigned int v140; // edx
  CEventNotifier *v141; // rcx
  CEventNotifier *v142; // rcx
  unsigned __int16 **v143; // rbx
  unsigned __int16 *v144; // rbx
  CEventNotifier *v145; // rcx
  CEventNotifier *v146; // rcx
  CEventNotifier *v147; // rcx
  CEventNotifier *v148; // rcx
  unsigned __int16 *v149; // rdi
  char *v150; // rbx
  void *v151; // rdx
  void *v152; // rax
  int v153; // edx
  int v154; // ecx
  unsigned __int16 *v155; // rax
  OLECHAR *v156; // rbx
  char *v157; // rbx
  void *v158; // rdx
  void *v159; // rax
  int v160; // edx
  int v161; // ecx
  char *v162; // rbx
  void *v163; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  unsigned int v165; // [rsp+60h] [rbp-A0h] BYREF
  int v166; // [rsp+64h] [rbp-9Ch] BYREF
  struct __EventDestNode__ *v167; // [rsp+68h] [rbp-98h] BYREF
  int v168; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME FileTime; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v170; // [rsp+80h] [rbp-80h]
  unsigned int v171; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR v172; // [rsp+90h] [rbp-70h]
  struct __EventDestNode__ *v173; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v174; // [rsp+A0h] [rbp-60h]
  _BYTE v175[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v176[80]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v177[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v178[260]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 *v179; // [rsp+358h] [rbp+258h]
  unsigned __int16 *v180; // [rsp+360h] [rbp+260h]
  struct __EventDestNode__ *v181; // [rsp+368h] [rbp+268h]
  _SYSTEMTIME SystemTime; // [rsp+380h] [rbp+280h] BYREF
  UUID Uuid; // [rsp+390h] [rbp+290h] BYREF

  v170 = a7;
  v174 = a8;
  v167 = (struct __EventDestNode__ *)a9;
  v172 = lpString;
  v13 = WiaTrace_Trace(&Class);
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v176, v14, v15, "CEventNotifier::RegisterEventCallback", lpMem, v13);
  FileTime = 0;
  v166 = 0;
  v168 = 0;
  SystemTime = 0;
  v165 = 0;
  Uuid = 0;
  memset_0(v177, 0, 0x270u);
  v16 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Flag %d", a2);
  WriteDbgTraceInfoWI("CEventNotifier::RegisterEventCallback", v16);
  WiaTrcLib::Free((WiaTrcLib *)v16, v17);
  v18 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Flag %d", a2);
  WiaTrace_ProcessTrace_Ex(v20, v19, (int)"CEventNotifier::RegisterEventCallback", 4, v18);
  CWiaCritSect::CWiaCritSect((CWiaCritSect *)v175, &stru_1800AF348);
  if ( a3 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(a3 + 2 * v22) );
    a3 &= -(__int64)(v22 != 0);
  }
  if ( a2 != 4 || a3 )
  {
    CLSIDForCommandline = 0;
    if ( lpString )
    {
      v29 = (CEventNotifier *)(lstrlenW(lpString) & 0xFFFFFFFFFFFFFFFEuLL);
      if ( (unsigned __int64)v29 >= 0x208 )
      {
        v30 = (char *)WiaTrace_TraceLog("ptszCommandline is greater than MAX_PATH characters!");
        WriteDbgTraceErrorWI("CEventNotifier::RegisterEventCallback", v30);
        WiaTrcLib::Free((WiaTrcLib *)v30, v31);
        v32 = (void *)WiaTrace_Trace("ptszCommandline is greater than MAX_PATH characters!");
        WiaTrace_ProcessTrace_Ex(v34, v33, (int)"CEventNotifier::RegisterEventCallback", 1, v32);
        v35 = -2147024809;
LABEL_13:
        CWiaCritSect::~CWiaCritSect((CWiaCritSect *)v175);
        CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v176);
        return (unsigned int)v35;
      }
      CLSIDForCommandline = CEventNotifier::FindCLSIDForCommandline(v29, lpString, &Uuid);
      if ( CLSIDForCommandline < 0 )
      {
        v35 = UuidCreate(&Uuid);
        if ( v35 < 0 )
          goto LABEL_13;
      }
      Buf1 = &Uuid;
    }
    v37 = a2 - 1;
    if ( v37 )
    {
      v38 = v37 - 1;
      if ( v38 )
      {
        if ( v38 != 2 )
        {
          CLSIDForCommandline = -2147467259;
          goto LABEL_104;
        }
        v39 = L"*";
        if ( a3 )
          v39 = (const WCHAR *)a3;
        v40 = (char *)WiaTrace_TraceLogWithSubComp(0, "Setting default handler for for %S", v39);
        WriteDbgTraceWarningWI("CEventNotifier::RegisterEventCallback", v40);
        WiaTrcLib::Free((WiaTrcLib *)v40, v41);
        v42 = L"*";
        if ( a3 )
          v42 = (const WCHAR *)a3;
        v43 = (void *)WiaTrace_TraceWithSubComp(0, "Setting default handler for for %S", v42);
        WiaTrace_ProcessTrace_Ex(v45, v44, (int)"CEventNotifier::RegisterEventCallback", 2, v43);
        v171 = 0;
        v173 = 0;
        if ( CEventNotifier::GetNumPersistentHandlerAndDefault(v46, (unsigned __int16 *)a3, a4, &v171, &v173) >= 0
          && v173 )
        {
          *((_DWORD *)v173 + 154) = 0;
        }
        EventCBNode = CEventNotifier::FindEventCBNode(v48, v47, (unsigned __int16 *)a3, a4, Buf1);
        if ( EventCBNode )
        {
          GetSystemTime(&SystemTime);
          SystemTimeToFileTime(&SystemTime, (LPFILETIME)EventCBNode + 76);
          *((_DWORD *)EventCBNode + 154) = 1;
          v67 = L"*";
          if ( a3 )
            v67 = (const WCHAR *)a3;
          v68 = (char *)WiaTrace_TraceLogWithSubComp(0, "Resetting default handler for %S", v67);
          WriteDbgTraceWarningWI("CEventNotifier::RegisterEventCallback", v68);
          WiaTrcLib::Free((WiaTrcLib *)v68, v69);
          v70 = L"*";
          if ( a3 )
            v70 = (const WCHAR *)a3;
          v71 = (void *)WiaTrace_TraceWithSubComp(0, "Resetting default handler for %S", v70);
          WiaTrace_ProcessTrace_Ex(v73, v72, (int)"CEventNotifier::RegisterEventCallback", 2, v71);
        }
        else
        {
          EventCBNode = CEventNotifier::FindEventCBNode(v50, v49, 0, a4, Buf1);
          if ( !EventCBNode )
          {
            memset_0(v177, 0, 0x270u);
            if ( v172 )
              StringCbCopyW(v178, 0x208u, v172);
            EventCBNode = (struct __EventDestNode__ *)v177;
            v179 = v170;
            v180 = v174;
            v181 = v167;
          }
          GetSystemTime(&SystemTime);
          SystemTimeToFileTime(&SystemTime, &FileTime);
          v52 = (char *)WiaTrace_TraceLogWithSubComp(
                          0,
                          "Found event node  EvName=%S CommandLine=%S",
                          *((const wchar_t **)EventCBNode + 73),
                          (const wchar_t *)EventCBNode + 32);
          WriteDbgTraceWarningWI("CEventNotifier::RegisterEventCallback", v52);
          WiaTrcLib::Free((WiaTrcLib *)v52, v53);
          v54 = (void *)WiaTrace_TraceWithSubComp(
                          0,
                          "Found event node  EvName=%S CommandLine=%S",
                          *((const wchar_t **)EventCBNode + 73),
                          (const wchar_t *)EventCBNode + 32);
          WiaTrace_ProcessTrace_Ex(v56, v55, (int)"CEventNotifier::RegisterEventCallback", 2, v54);
          CLSIDForCommandline = CEventNotifier::RegisterEventCB(
                                  v57,
                                  (unsigned __int16 *)a3,
                                  a4,
                                  Buf1,
                                  (const unsigned __int16 *)EventCBNode + 32,
                                  *((unsigned __int16 **)EventCBNode + 73),
                                  *((unsigned __int16 **)EventCBNode + 74),
                                  *((unsigned __int16 **)EventCBNode + 75),
                                  &FileTime,
                                  1);
          if ( CLSIDForCommandline < 0 )
          {
            v59 = L"*";
            v60 = L"*";
            if ( a3 )
              v60 = (const WCHAR *)a3;
            v61 = (char *)WiaTrace_TraceLogWithSubComp(0, "RegisterEventCB for %S failed", v60);
            WriteDbgTraceWarningWI("CEventNotifier::RegisterEventCallback", v61);
            WiaTrcLib::Free((WiaTrcLib *)v61, v62);
            if ( a3 )
              v59 = (const WCHAR *)a3;
            v63 = (void *)WiaTrace_TraceWithSubComp(0, "RegisterEventCB for %S failed", v59);
            v66 = 2;
            goto LABEL_37;
          }
        }
        CLSIDForCommandline = CEventNotifier::SavePersistentEventCB(
                                v58,
                                (unsigned __int16 *)a3,
                                a4,
                                Buf1,
                                (unsigned __int16 *)EventCBNode + 32,
                                *((unsigned __int16 **)EventCBNode + 73),
                                *((unsigned __int16 **)EventCBNode + 74),
                                *((unsigned __int16 **)EventCBNode + 75),
                                &v168,
                                &v165,
                                1);
        if ( CLSIDForCommandline < 0 )
        {
          v75 = (char *)WiaTrace_TraceLog("SavePersistentEventCB CommandLine=%S failed!");
          WriteDbgTraceErrorWI("CEventNotifier::RegisterEventCallback", v75);
          WiaTrcLib::Free((WiaTrcLib *)v75, v76);
          v77 = (void *)WiaTrace_Trace(
                          "SavePersistentEventCB CommandLine=%S failed!",
                          (const wchar_t *)EventCBNode + 32);
          WiaTrace_ProcessTrace_Ex(v79, v78, (int)"CEventNotifier::RegisterEventCallback", 1, v77);
          if ( v177 != (_BYTE *)EventCBNode )
            goto LABEL_104;
          v74 = 0;
          CEventNotifier::UnregisterEventCB(v80, (unsigned __int16 *)a3, a4, Buf1, &v166);
        }
        else
        {
          v74 = v168;
        }
        if ( !v74 || !memcmp_0(Buf1, &WIA_EVENT_HANDLER_PROMPT, 0x10u) || !v165 )
          goto LABEL_104;
        v81 = L"*";
        v82 = L"*";
        if ( a3 )
          v82 = (const WCHAR *)a3;
        v83 = (char *)WiaTrace_TraceLogWithSubComp(0, "About to Register Prompt Dialog for device %S", v82);
        WriteDbgTraceWarningWI("CEventNotifier::RegisterEventCallback", v83);
        WiaTrcLib::Free((WiaTrcLib *)v83, v84);
        v85 = L"*";
        if ( a3 )
          v85 = (const WCHAR *)a3;
        v86 = (void *)WiaTrace_TraceWithSubComp(0, "About to Register Prompt Dialog for device %S", v85);
        WiaTrace_ProcessTrace_Ex(v88, v87, (int)"CEventNotifier::RegisterEventCallback", 2, v86);
        v89 = SysAllocString(L"Internal");
        v90 = v89;
        if ( v89 )
        {
          CEventNotifier::RegisterEventCallback(
            (CEventNotifier *)&g_eventNotifier,
            4,
            (unsigned __int16 *)a3,
            a4,
            &WIA_EVENT_HANDLER_PROMPT,
            0,
            v89,
            v89,
            v89);
          SysFreeString(v90);
        }
        v91 = L"*";
        if ( a3 )
          v91 = (const WCHAR *)a3;
        v92 = (char *)WiaTrace_TraceLogWithSubComp(0, "Registered Prompt Dialog for device %S", v91);
        WriteDbgTraceWarningWI("CEventNotifier::RegisterEventCallback", v92);
        WiaTrcLib::Free((WiaTrcLib *)v92, v93);
        if ( a3 )
          v81 = (const WCHAR *)a3;
        v63 = (void *)WiaTrace_TraceWithSubComp(0, "Registered Prompt Dialog for device %S", v81);
        v66 = 2;
        goto LABEL_37;
      }
      v167 = 0;
      CLSIDForCommandline = CEventNotifier::UnregisterEventCB(v21, (unsigned __int16 *)a3, a4, Buf1, &v166);
      if ( CLSIDForCommandline < 0 )
      {
        v95 = (char *)WiaTrace_TraceLog("UnregisterEventCB failed");
        WriteDbgTraceErrorWI("CEventNotifier::RegisterEventCallback", v95);
        WiaTrcLib::Free((WiaTrcLib *)v95, v96);
        v63 = (void *)WiaTrace_Trace("UnregisterEventCB failed");
        v66 = 1;
LABEL_37:
        WiaTrace_ProcessTrace_Ex(v65, v64, (int)"CEventNotifier::RegisterEventCallback", v66, v63);
        goto LABEL_104;
      }
      CLSIDForCommandline = CEventNotifier::DelPersistentEventCB(v94, (unsigned __int16 *)a3, a4, Buf1, v166);
      if ( CLSIDForCommandline < 0 )
      {
        v97 = (char *)WiaTrace_TraceLog("DelPersistentEventCB failed");
        WriteDbgTraceErrorWI("CEventNotifier::RegisterEventCallback", v97);
        WiaTrcLib::Free((WiaTrcLib *)v97, v98);
        v99 = (void *)WiaTrace_Trace("DelPersistentEventCB failed");
        WiaTrace_ProcessTrace_Ex(v101, v100, (int)"CEventNotifier::RegisterEventCallback", 1, v99);
      }
      if ( !memcmp_0(&WIA_EVENT_HANDLER_PROMPT, Buf1, 0x10u) )
        goto LABEL_104;
      v102 = L"All";
      if ( a3 )
        v102 = (const OLECHAR *)a3;
      v104 = SysAllocString(v102);
      if ( !v104 )
      {
        v118 = (char *)WiaTrace_TraceLog("Out of memory!");
        WriteDbgTraceErrorWI("CEventNotifier::RegisterEventCallback", v118);
        WiaTrcLib::Free((WiaTrcLib *)v118, v119);
        v120 = (void *)WiaTrace_Trace("Out of memory!");
        WiaTrace_ProcessTrace_Ex(v122, v121, (int)"CEventNotifier::RegisterEventCallback", 1, v120);
        CLSIDForCommandline = -2147024882;
        goto LABEL_104;
      }
      CEventNotifier::GetNumPersistentHandlerAndDefault(v103, v104, a4, &v165, &v167);
      if ( CLSIDForCommandline >= 0 && v165 == 2 )
      {
        v105 = (char *)WiaTrace_TraceLogWithSubComp(0, "Unregistering Prompt Dialog");
        WriteDbgTraceWarningWI("CEventNotifier::RegisterEventCallback", v105);
        WiaTrcLib::Free((WiaTrcLib *)v105, v106);
        v107 = (void *)WiaTrace_TraceWithSubComp(0, "Unregistering Prompt Dialog");
        WiaTrace_ProcessTrace_Ex(v109, v108, (int)"CEventNotifier::RegisterEventCallback", 2, v107);
        v110 = SysAllocString(L"Internal");
        v111 = v110;
        if ( v110 )
        {
          CEventNotifier::RegisterEventCallback(
            (CEventNotifier *)&g_eventNotifier,
            2,
            (unsigned __int16 *)a3,
            a4,
            &WIA_EVENT_HANDLER_PROMPT,
            0,
            v110,
            v110,
            v110);
          SysFreeString(v111);
        }
        else
        {
          v112 = (char *)WiaTrace_TraceLog("Out of memory!");
          WriteDbgTraceErrorWI("CEventNotifier::RegisterEventCallback", v112);
          WiaTrcLib::Free((WiaTrcLib *)v112, v113);
          v114 = (void *)WiaTrace_Trace("Out of memory!");
          WiaTrace_ProcessTrace_Ex(v116, v115, (int)"CEventNotifier::RegisterEventCallback", 1, v114);
          CLSIDForCommandline = -2147024882;
        }
      }
      v117 = v104;
LABEL_103:
      SysFreeString(v117);
      goto LABEL_104;
    }
    v123 = L"*";
    v124 = L"*";
    if ( a3 )
      v124 = (const WCHAR *)a3;
    v125 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Setting handler for %S", v124);
    WriteDbgTraceInfoWI("CEventNotifier::RegisterEventCallback", v125);
    WiaTrcLib::Free((WiaTrcLib *)v125, v126);
    if ( a3 )
      v123 = (const WCHAR *)a3;
    v127 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Setting handler for %S", v123);
    WiaTrace_ProcessTrace_Ex(v129, v128, (int)"CEventNotifier::RegisterEventCallback", 4, v127);
    v130 = v170;
    if ( !v170 )
      v130 = L"NULL";
    v131 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Handler is %S", v130);
    WriteDbgTraceInfoWI("CEventNotifier::RegisterEventCallback", v131);
    WiaTrcLib::Free((WiaTrcLib *)v131, v132);
    v133 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Handler is %S", v130);
    WiaTrace_ProcessTrace_Ex(v135, v134, (int)"CEventNotifier::RegisterEventCallback", 4, v133);
    if ( !v170 || (v138 = v174) == 0 || (v139 = (unsigned __int16 *)v167) == 0 )
    {
      v162 = (char *)WiaTrace_TraceLog("Name | Description | Icon are missing");
      WriteDbgTraceErrorWI("CEventNotifier::RegisterEventCallback", v162);
      WiaTrcLib::Free((WiaTrcLib *)v162, v163);
      v25 = (void *)WiaTrace_Trace("Name | Description | Icon are missing");
      goto LABEL_106;
    }
    if ( CEventNotifier::FindEventCBNode(v137, v136, (unsigned __int16 *)a3, a4, Buf1) )
    {
LABEL_104:
      CWiaCritSect::~CWiaCritSect((CWiaCritSect *)v175);
      CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v176);
      return (unsigned int)CLSIDForCommandline;
    }
    v143 = (unsigned __int16 **)CEventNotifier::FindEventCBNode(v141, v140, 0, a4, Buf1);
    FileTime = 0;
    if ( v143 )
    {
      CLSIDForCommandline = CEventNotifier::RegisterEventCB(
                              (CEventNotifier *)(v143 + 8),
                              (unsigned __int16 *)a3,
                              a4,
                              Buf1,
                              (const unsigned __int16 *)v143 + 32,
                              v143[73],
                              v143[74],
                              v143[75],
                              &FileTime,
                              0);
      if ( CLSIDForCommandline < 0 )
        goto LABEL_104;
      CLSIDForCommandline = CEventNotifier::SavePersistentEventCB(
                              v147,
                              (unsigned __int16 *)a3,
                              a4,
                              Buf1,
                              (unsigned __int16 *)v143 + 32,
                              v143[73],
                              v143[74],
                              v143[75],
                              0,
                              &v165,
                              0);
      if ( CLSIDForCommandline < 0 )
        goto LABEL_89;
      v144 = (unsigned __int16 *)v172;
    }
    else
    {
      v144 = (unsigned __int16 *)v172;
      CLSIDForCommandline = CEventNotifier::RegisterEventCB(
                              v142,
                              (unsigned __int16 *)a3,
                              a4,
                              Buf1,
                              v172,
                              v170,
                              v174,
                              (unsigned __int16 *)v167,
                              &FileTime,
                              0);
      if ( CLSIDForCommandline < 0 )
        goto LABEL_104;
      CLSIDForCommandline = CEventNotifier::SavePersistentEventCB(
                              v145,
                              (unsigned __int16 *)a3,
                              a4,
                              Buf1,
                              v144,
                              v170,
                              v138,
                              (unsigned __int16 *)v167,
                              0,
                              &v165,
                              0);
      if ( CLSIDForCommandline < 0 )
      {
LABEL_89:
        CEventNotifier::UnregisterEventCB(v146, (unsigned __int16 *)a3, a4, Buf1, &v166);
        goto LABEL_104;
      }
    }
    if ( !v165 )
      CEventNotifier::RegisterEventCallback(
        (CEventNotifier *)&g_eventNotifier,
        4,
        (unsigned __int16 *)a3,
        a4,
        Buf1,
        v144,
        v170,
        v138,
        v139);
    if ( !memcmp_0(&WIA_EVENT_HANDLER_PROMPT, Buf1, 0x10u) )
      goto LABEL_104;
    if ( a3 )
      goto LABEL_104;
    v167 = 0;
    v149 = SysAllocString(L"All");
    if ( !v149 )
      goto LABEL_104;
    CEventNotifier::GetNumPersistentHandlerAndDefault(v148, v149, a4, &v165, &v167);
    if ( v165 > 1 )
    {
      v150 = (char *)WiaTrace_TraceLogWithSubComp(0, "Registering Prompt Dialog as global handler");
      WriteDbgTraceWarningWI("CEventNotifier::RegisterEventCallback", v150);
      WiaTrcLib::Free((WiaTrcLib *)v150, v151);
      v152 = (void *)WiaTrace_TraceWithSubComp(0, "Registering Prompt Dialog as global handler");
      WiaTrace_ProcessTrace_Ex(v154, v153, (int)"CEventNotifier::RegisterEventCallback", 2, v152);
      v155 = SysAllocString(L"Internal");
      v156 = v155;
      if ( v155 )
      {
        CEventNotifier::RegisterEventCallback(
          (CEventNotifier *)&g_eventNotifier,
          1,
          0,
          a4,
          &WIA_EVENT_HANDLER_PROMPT,
          0,
          v155,
          v155,
          v155);
        SysFreeString(v156);
      }
      else
      {
        v157 = (char *)WiaTrace_TraceLog("Out of memory!");
        WriteDbgTraceErrorWI("CEventNotifier::RegisterEventCallback", v157);
        WiaTrcLib::Free((WiaTrcLib *)v157, v158);
        v159 = (void *)WiaTrace_Trace("Out of memory!");
        WiaTrace_ProcessTrace_Ex(v161, v160, (int)"CEventNotifier::RegisterEventCallback", 1, v159);
      }
    }
    v117 = v149;
    goto LABEL_103;
  }
  v23 = (char *)WiaTrace_TraceLog("DeviceID required to set default handler");
  WriteDbgTraceErrorWI("CEventNotifier::RegisterEventCallback", v23);
  WiaTrcLib::Free((WiaTrcLib *)v23, v24);
  v25 = (void *)WiaTrace_Trace("DeviceID required to set default handler");
LABEL_106:
  WiaTrace_ProcessTrace_Ex(v27, v26, (int)"CEventNotifier::RegisterEventCallback", 1, v25);
  CWiaCritSect::~CWiaCritSect((CWiaCritSect *)v175);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v176);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800315a0  mov     [rsp-8+arg_0], rbx
0x1800315a5  push    rbp
0x1800315a6  push    rsi
0x1800315a7  push    rdi
0x1800315a8  push    r12
0x1800315aa  push    r13
0x1800315ac  push    r14
0x1800315ae  push    r15
0x1800315b0  lea     rbp, [rsp-2B0h]
0x1800315b8  sub     rsp, 3B0h
0x1800315bf  mov     rax, cs:__security_cookie
0x1800315c6  xor     rax, rsp
0x1800315c9  mov     [rbp+2E0h+var_40], rax
0x1800315d0  mov     rax, [rbp+2E0h+arg_30]
0x1800315d7  lea     rcx, Class; unsigned __int16 *
0x1800315de  mov     rdi, [rbp+2E0h+lpString]
0x1800315e5  mov     r15, r9
0x1800315e8  mov     r12, [rbp+2E0h+Buf1]
0x1800315ef  mov     rsi, r8
0x1800315f2  mov     [rbp+2E0h+var_360], rax
0x1800315f6  mov     r13d, edx
0x1800315f9  mov     rax, [rbp+2E0h+arg_38]
0x180031600  mov     [rbp+2E0h+var_340], rax
0x180031604  mov     rax, [rbp+2E0h+arg_40]
0x18003160b  mov     [rsp+3E0h+var_378], rax
0x180031610  mov     [rbp+2E0h+var_350], rdi
0x180031614  call    ?WiaTrace_Trace@@YAPEAUtagWiaTraceData_Type@@PEBGZZ; WiaTrace_Trace(ushort const *,...)
0x180031619  lea     r14, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x180031620  mov     [rsp+3E0h+var_3B8], rax; struct tagWiaTraceData_Type *
0x180031625  mov     r9, r14; char *
0x180031628  lea     rcx, [rbp+2E0h+var_320]; this
0x18003162c  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180031631  xor     eax, eax
0x180031633  lea     rcx, [rbp+2E0h+var_2D0]; void *
0x180031637  xorps   xmm0, xmm0
0x18003163a  mov     qword ptr [rsp+3E0h+FileTime.dwLowDateTime], rax
0x18003163f  xor     edx, edx; Val
0x180031641  mov     [rsp+3E0h+var_37C], eax
0x180031645  mov     r8d, 270h; Size
0x18003164b  mov     [rsp+3E0h+var_370], eax
0x18003164f  movups  xmmword ptr [rbp+2E0h+SystemTime.wYear], xmm0
0x180031656  mov     [rsp+3E0h+var_380], eax
0x18003165a  movups  xmmword ptr [rbp+2E0h+Uuid.Data1], xmm0
0x180031661  call    memset_0
0x180031666  mov     r9d, r13d
0x180031669  lea     r8, aFlagD; "Flag %d"
0x180031670  xor     edx, edx
0x180031672  xor     ecx, ecx
0x180031674  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180031679  mov     rdx, rax; char *
0x18003167c  mov     rcx, r14; char *
0x18003167f  mov     rbx, rax
0x180031682  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180031687  mov     rcx, rbx; this
0x18003168a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003168f  mov     r9d, r13d
0x180031692  lea     r8, aFlagD; "Flag %d"
0x180031699  xor     edx, edx
0x18003169b  xor     ecx, ecx
0x18003169d  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800316a2  mov     r9d, 4; int
0x1800316a8  mov     [rsp+3E0h+lpMem], rax; lpMem
0x1800316ad  mov     r8, r14; int
0x1800316b0  call    WiaTrace_ProcessTrace_Ex
0x1800316b5  lea     rdx, stru_1800AF348; struct _RTL_CRITICAL_SECTION *
0x1800316bc  lea     rcx, [rbp+2E0h+var_338]; this
0x1800316c0  call    ??0CWiaCritSect@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CWiaCritSect::CWiaCritSect(_RTL_CRITICAL_SECTION *)
0x1800316c5  xor     ebx, ebx
0x1800316c7  test    rsi, rsi
0x1800316ca  jz      short loc_1800316E2
0x1800316cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800316d0  inc     rax
0x1800316d3  cmp     [rsi+rax*2], bx
0x1800316d7  jnz     short loc_1800316D0
0x1800316d9  neg     rax
0x1800316dc  sbb     rax, rax
0x1800316df  and     rsi, rax
0x1800316e2  cmp     r13d, 4
0x1800316e6  jnz     short loc_180031723
0x1800316e8  test    rsi, rsi
0x1800316eb  jnz     short loc_180031723
0x1800316ed  lea     rcx, aDeviceidRequir; "DeviceID required to set default handle"...
0x1800316f4  call    WiaTrace_TraceLog
0x1800316f9  mov     rdx, rax; char *
0x1800316fc  mov     rcx, r14; char *
0x1800316ff  mov     rbx, rax
0x180031702  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180031707  mov     rcx, rbx; this
0x18003170a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003170f  lea     rcx, aDeviceidRequir; "DeviceID required to set default handle"...
0x180031716  call    WiaTrace_Trace
0x18003171b  mov     r8, r14
0x18003171e  jmp     loc_1800323FC
0x180031723  mov     r14d, ebx
0x180031726  test    rdi, rdi
0x180031729  jz      loc_1800317E3
0x18003172f  mov     rcx, rdi; lpString
0x180031732  call    cs:__imp_lstrlenW
0x180031738  movsxd  rcx, eax
0x18003173b  and     rcx, 0FFFFFFFFFFFFFFFEh; this
0x18003173f  cmp     rcx, 208h
0x180031746  jb      short loc_180031798
0x180031748  lea     rcx, aPtszcommandlin; "ptszCommandline is greater than MAX_PAT"...
0x18003174f  call    WiaTrace_TraceLog
0x180031754  mov     rdx, rax; char *
0x180031757  lea     rcx, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x18003175e  mov     rbx, rax
0x180031761  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180031766  mov     rcx, rbx; this
0x180031769  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003176e  lea     rcx, aPtszcommandlin; "ptszCommandline is greater than MAX_PAT"...
0x180031775  call    WiaTrace_Trace
0x18003177a  mov     r9d, 1; int
0x180031780  mov     [rsp+3E0h+lpMem], rax; lpMem
0x180031785  lea     r8, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x18003178c  call    WiaTrace_ProcessTrace_Ex
0x180031791  mov     ebx, 80070057h
0x180031796  jmp     short loc_1800317C1
0x180031798  lea     r8, [rbp+2E0h+Uuid]; struct _GUID *
0x18003179f  mov     rdx, rdi; unsigned __int16 *
0x1800317a2  call    ?FindCLSIDForCommandline@CEventNotifier@@AEAAJPEBGPEAU_GUID@@@Z; CEventNotifier::FindCLSIDForCommandline(ushort const *,_GUID *)
0x1800317a7  mov     r14d, eax
0x1800317aa  test    eax, eax
0x1800317ac  jns     short loc_1800317DC
0x1800317ae  lea     rcx, [rbp+2E0h+Uuid]; Uuid
0x1800317b5  call    cs:__imp_UuidCreate
0x1800317bb  mov     ebx, eax
0x1800317bd  test    eax, eax
0x1800317bf  jns     short loc_1800317DA
0x1800317c1  lea     rcx, [rbp+2E0h+var_338]; this
0x1800317c5  call    ??1CWiaCritSect@@QEAA@XZ; CWiaCritSect::~CWiaCritSect(void)
0x1800317ca  lea     rcx, [rbp+2E0h+var_320]; this
0x1800317ce  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800317d3  mov     eax, ebx
0x1800317d5  jmp     loc_180032423
0x1800317da  xor     ebx, ebx
0x1800317dc  lea     r12, [rbp+2E0h+Uuid]
0x1800317e3  sub     r13d, 1
0x1800317e7  jz      loc_180031F96
0x1800317ed  sub     r13d, 1
0x1800317f1  jz      loc_180031D17
0x1800317f7  mov     edi, 2
0x1800317fc  cmp     r13d, edi
0x1800317ff  jz      short loc_18003180C
0x180031801  mov     r14d, 80004005h
0x180031807  jmp     loc_1800323AC
0x18003180c  lea     r14, asc_180086378; "*"
0x180031813  test    rsi, rsi
0x180031816  mov     r8, r14
0x180031819  lea     rdx, aSettingDefault; "Setting default handler for for %S"
0x180031820  cmovnz  r8, rsi
0x180031824  xor     ecx, ecx
0x180031826  call    WiaTrace_TraceLogWithSubComp
0x18003182b  mov     rdx, rax; char *
0x18003182e  lea     rcx, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x180031835  mov     rbx, rax
0x180031838  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003183d  mov     rcx, rbx; this
0x180031840  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180031845  xor     ebx, ebx
0x180031847  lea     rdx, aSettingDefault; "Setting default handler for for %S"
0x18003184e  test    rsi, rsi
0x180031851  mov     r8, r14
0x180031854  cmovnz  r8, rsi
0x180031858  xor     ecx, ecx
0x18003185a  call    WiaTrace_TraceWithSubComp
0x18003185f  mov     r9d, edi; int
0x180031862  mov     [rsp+3E0h+lpMem], rax; lpMem
0x180031867  lea     r8, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x18003186e  call    WiaTrace_ProcessTrace_Ex
0x180031873  lea     rax, [rbp+2E0h+var_348]
0x180031877  mov     [rbp+2E0h+var_358], ebx
0x18003187a  lea     r9, [rbp+2E0h+var_358]; unsigned int *
0x18003187e  mov     [rsp+3E0h+lpMem], rax; struct __EventDestNode__ **
0x180031883  mov     r8, r15; struct _GUID *
0x180031886  mov     [rbp+2E0h+var_348], rbx
0x18003188a  mov     rdx, rsi; unsigned __int16 *
0x18003188d  call    ?GetNumPersistentHandlerAndDefault@CEventNotifier@@QEAAJPEAGPEBU_GUID@@PEAKPEAPEAU__EventDestNode__@@@Z; CEventNotifier::GetNumPersistentHandlerAndDefault(ushort *,_GUID const *,ulong *,__EventDestNode__ * *)
0x180031892  test    eax, eax
0x180031894  js      short loc_1800318A5
0x180031896  mov     rax, [rbp+2E0h+var_348]
0x18003189a  test    rax, rax
0x18003189d  jz      short loc_1800318A5
0x18003189f  mov     [rax+268h], ebx
0x1800318a5  mov     r9, r15; struct _GUID *
0x1800318a8  mov     [rsp+3E0h+lpMem], r12; struct _GUID *
0x1800318ad  mov     r8, rsi; unsigned __int16 *
0x1800318b0  call    ?FindEventCBNode@CEventNotifier@@AEAAPEAU__EventDestNode__@@IPEAGPEBU_GUID@@1@Z; CEventNotifier::FindEventCBNode(uint,ushort *,_GUID const *,_GUID const *)
0x1800318b5  mov     r13, rax
0x1800318b8  test    rax, rax
0x1800318bb  jnz     loc_180031A6F
0x1800318c1  mov     r9, r15; struct _GUID *
0x1800318c4  mov     [rsp+3E0h+lpMem], r12; struct _GUID *
0x1800318c9  xor     r8d, r8d; unsigned __int16 *
0x1800318cc  call    ?FindEventCBNode@CEventNotifier@@AEAAPEAU__EventDestNode__@@IPEAGPEBU_GUID@@1@Z; CEventNotifier::FindEventCBNode(uint,ushort *,_GUID const *,_GUID const *)
0x1800318d1  mov     r13, rax
0x1800318d4  test    rax, rax
0x1800318d7  jnz     short loc_18003192A
0x1800318d9  xor     edx, edx; Val
0x1800318db  lea     rcx, [rbp+2E0h+var_2D0]; void *
0x1800318df  mov     r8d, 270h; Size
0x1800318e5  call    memset_0
0x1800318ea  mov     rbx, [rbp+2E0h+var_350]
0x1800318ee  test    rbx, rbx
0x1800318f1  jz      short loc_180031904
0x1800318f3  mov     r8, rbx; unsigned __int16 *
0x1800318f6  lea     rcx, [rbp+2E0h+var_290]; unsigned __int16 *
0x1800318fa  mov     edx, 208h; unsigned __int64
0x1800318ff  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180031904  mov     rax, [rbp+2E0h+var_360]
0x180031908  lea     r13, [rbp+2E0h+var_2D0]
0x18003190c  mov     [rbp+2E0h+var_88], rax
0x180031913  mov     rax, [rbp+2E0h+var_340]
0x180031917  mov     [rbp+2E0h+var_80], rax
0x18003191e  mov     rax, [rsp+3E0h+var_378]
0x180031923  mov     [rbp+2E0h+var_78], rax
0x18003192a  lea     rcx, [rbp+2E0h+SystemTime]; lpSystemTime
0x180031931  call    cs:__imp_GetSystemTime
0x180031937  lea     rdx, [rsp+3E0h+FileTime]; lpFileTime
0x18003193c  lea     rcx, [rbp+2E0h+SystemTime]; lpSystemTime
0x180031943  call    cs:__imp_SystemTimeToFileTime
0x180031949  mov     r8, [r13+248h]
0x180031950  lea     rdi, [r13+40h]
0x180031954  mov     r9, rdi
0x180031957  lea     rdx, aFoundEventNode; "Found event node  EvName=%S CommandLine"...
0x18003195e  xor     ecx, ecx
0x180031960  call    WiaTrace_TraceLogWithSubComp
0x180031965  mov     rdx, rax; char *
0x180031968  lea     rcx, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x18003196f  mov     rbx, rax
0x180031972  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180031977  mov     rcx, rbx; this
0x18003197a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003197f  mov     r8, [r13+248h]
0x180031986  lea     rdx, aFoundEventNode; "Found event node  EvName=%S CommandLine"...
0x18003198d  mov     r9, rdi
0x180031990  xor     ecx, ecx
0x180031992  call    WiaTrace_TraceWithSubComp
0x180031997  mov     r9d, 2; int
0x18003199d  mov     [rsp+3E0h+lpMem], rax; lpMem
0x1800319a2  lea     r8, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x1800319a9  call    WiaTrace_ProcessTrace_Ex
0x1800319ae  mov     dword ptr [rsp+3E0h+var_398], 1; int
0x1800319b6  lea     rax, [rsp+3E0h+FileTime]
0x1800319bb  mov     [rsp+3E0h+var_3A0], rax; struct _FILETIME *
0x1800319c0  mov     r9, r12; struct _GUID *
0x1800319c3  mov     rax, [r13+258h]
0x1800319ca  mov     r8, r15; struct _GUID *
0x1800319cd  mov     [rsp+3E0h+var_3A8], rax; unsigned __int16 *
0x1800319d2  mov     rdx, rsi; unsigned __int16 *
0x1800319d5  mov     rax, [r13+250h]
0x1800319dc  mov     [rsp+3E0h+var_3B0], rax; unsigned __int16 *
0x1800319e1  mov     rax, [r13+248h]
0x1800319e8  mov     [rsp+3E0h+var_3B8], rax; unsigned __int16 *
0x1800319ed  mov     [rsp+3E0h+lpMem], rdi; unsigned __int16 *
0x1800319f2  call    ?RegisterEventCB@CEventNotifier@@AEAAJPEAGPEBU_GUID@@1PEBG000AEAU_FILETIME@@H@Z; CEventNotifier::RegisterEventCB(ushort *,_GUID const *,_GUID const *,ushort const *,ushort *,ushort *,ushort *,_FILETIME &,int)
0x1800319f7  mov     r14d, eax
0x1800319fa  test    eax, eax
0x1800319fc  jns     loc_180031AFB
0x180031a02  lea     r12, asc_180086378; "*"
0x180031a09  test    rsi, rsi
0x180031a0c  mov     r8, r12
0x180031a0f  lea     rdx, aRegistereventc_3; "RegisterEventCB for %S failed"
0x180031a16  cmovnz  r8, rsi
0x180031a1a  xor     ecx, ecx
0x180031a1c  call    WiaTrace_TraceLogWithSubComp
0x180031a21  mov     rdx, rax; char *
0x180031a24  lea     rcx, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x180031a2b  mov     rbx, rax
0x180031a2e  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180031a33  mov     rcx, rbx; this
0x180031a36  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180031a3b  test    rsi, rsi
0x180031a3e  lea     rdx, aRegistereventc_3; "RegisterEventCB for %S failed"
0x180031a45  cmovnz  r12, rsi
0x180031a49  xor     ecx, ecx
0x180031a4b  mov     r8, r12
0x180031a4e  call    WiaTrace_TraceWithSubComp
0x180031a53  mov     r9d, 2; int
0x180031a59  lea     r8, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x180031a60  mov     [rsp+3E0h+lpMem], rax; lpMem
0x180031a65  call    WiaTrace_ProcessTrace_Ex
0x180031a6a  jmp     loc_1800323AC
0x180031a6f  lea     rcx, [rbp+2E0h+SystemTime]; lpSystemTime
0x180031a76  call    cs:__imp_GetSystemTime
0x180031a7c  lea     rdx, [r13+260h]; lpFileTime
0x180031a83  lea     rcx, [rbp+2E0h+SystemTime]; lpSystemTime
0x180031a8a  call    cs:__imp_SystemTimeToFileTime
0x180031a90  test    rsi, rsi
0x180031a93  mov     dword ptr [r13+268h], 1
0x180031a9e  mov     r8, r14
0x180031aa1  lea     rdx, aResettingDefau; "Resetting default handler for %S"
0x180031aa8  cmovnz  r8, rsi
0x180031aac  xor     ecx, ecx
0x180031aae  call    WiaTrace_TraceLogWithSubComp
0x180031ab3  mov     rdx, rax; char *
0x180031ab6  lea     rcx, aCeventnotifier_21; "CEventNotifier::RegisterEventCallback"
0x180031abd  mov     rbx, rax
0x180031ac0  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180031ac5  mov     rcx, rbx; this
  ... truncated ...
```
