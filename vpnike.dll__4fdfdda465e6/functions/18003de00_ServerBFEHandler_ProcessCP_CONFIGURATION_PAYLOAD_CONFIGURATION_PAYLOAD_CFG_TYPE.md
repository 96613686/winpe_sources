# ServerBFEHandler::ProcessCP(_CONFIGURATION_PAYLOAD_ * *,_CONFIGURATION_PAYLOAD_ *,_CFG_TYPE_)

- ea: `0x18003de00`
- end: `0x18003fd0c`
- name: `?ProcessCP@ServerBFEHandler@@UEAAKPEAPEAU_CONFIGURATION_PAYLOAD_@@PEAU2@W4_CFG_TYPE_@@@Z`
- size: `7948`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180039fa8`
- `0x18003a348`
- `0x18003de00`
- `0x180048684`
- `0x18004ac7c`
- `0x18004c824`
- `0x18004cf08`
- `0x18004fc20`
- `0x1800502e0`
- `0x18005dce0`
- `0x18005de2c`
- `0x180065d28`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x180077546`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003faf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003faf2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003e3a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003e3a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e392`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fae4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e392`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fae4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003e272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003e272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e293`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003e23e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003e23e`
- `WS2_32!__imp_ntohl` at `0x18003ecca`
- `WS2_32!__imp_ntohl` at `0x18003ecca`

## string_xrefs

- `0x18003e230`: `System\CurrentControlSet\Services\rasman\IKEv2`
- `0x18003dfe6`: `VPNIKEProtocolEngine::PEHelperFunctions.lpfnRouterTypeLookup failed with error %d`
- `0x18003e266`: `SkipConfigPayload`
- `0x18003e543`: `Received a CFG_REQUEST with zero configuration attributes`
- `0x18003ec49`: `INTERNAL_IP4_ADDRESS already processed`
- `0x18003e9ac`: `INTERNAL_IP4_DNS already processed`
- `0x18003e7d5`: `INTERNAL_IP4_NBNS already processed`
- `0x18003f6e8`: `INTERNAL_IP4_SERVER_FLAG already processed`
- `0x18003f503`: `INTERNAL_IP6_DNS already processed`
- `0x18003f8a3`: `INTERNAL_IP6_SERVER already processed`

## pseudocode

```c
__int64 __fastcall ServerBFEHandler::ProcessCP(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  PVOID *v7; // rbx
  unsigned int v8; // r12d
  unsigned int v9; // ecx
  unsigned __int8 v10; // dl
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int128 *v16; // r9
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  bool v20; // si
  bool v21; // r14
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // rcx
  __int128 *v27; // r9
  _QWORD *v28; // rdi
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  __int128 *v37; // r9
  HANDLE ProcessHeap; // rax
  _DWORD *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  _QWORD *v43; // rax
  __int64 v44; // rcx
  __int128 *v45; // r9
  HKEY v46; // rdi
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rcx
  _QWORD *v50; // rax
  __int64 v51; // rcx
  __int128 *v52; // r9
  unsigned int v53; // ebx
  PVOID v54; // rcx
  _QWORD *v55; // rdx
  unsigned __int64 v56; // r8
  int v57; // ebx
  HKEY i; // rcx
  char v59; // r15
  unsigned __int16 near **v60; // rdx
  int v61; // ecx
  int v62; // ecx
  int v63; // ecx
  int v64; // ecx
  int v65; // ecx
  int v66; // ecx
  _QWORD *v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int128 *v76; // r9
  const wchar_t *v77; // r8
  __int64 v78; // rax
  _DWORD *v79; // rcx
  __int64 v80; // rax
  _DWORD *v81; // rcx
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // rax
  _DWORD *v95; // rcx
  __int64 v96; // rax
  _DWORD *v97; // rcx
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // rax
  __int64 v105; // rax
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // rdx
  __int64 v115; // rcx
  unsigned int v116; // ebx
  __int64 v117; // rcx
  __int64 v118; // rax
  _DWORD *v119; // rax
  u_long v120; // edi
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rdx
  __int64 v124; // rdx
  _QWORD *v125; // rax
  __int64 v126; // rdx
  __int128 *v127; // r9
  __int64 v128; // rdx
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rdx
  __int64 v132; // rcx
  __int64 v133; // rdx
  __int64 v134; // rdx
  __int64 v135; // rcx
  __int128 *v136; // r9
  __int64 v137; // rax
  __int64 v138; // rax
  __int64 v139; // rdx
  __int64 v140; // rcx
  __int64 v141; // rdx
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int128 *v144; // r9
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rdx
  __int64 v148; // rcx
  __int64 v149; // rdx
  __int64 v150; // rcx
  __int64 v151; // rcx
  __int64 v152; // rdx
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // rdx
  __int64 v158; // rcx
  __int64 v159; // rcx
  __int64 v160; // rax
  __int64 v161; // rax
  __int64 v162; // rdx
  __int64 v163; // rcx
  __int64 v164; // rdx
  __int64 v165; // rdx
  __int64 v166; // rcx
  __int128 *v167; // r9
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rdx
  __int64 v171; // rcx
  __int64 v172; // rdx
  __int64 v173; // rcx
  int v174; // ecx
  int v175; // ecx
  int v176; // ecx
  int v177; // ecx
  PVOID v178; // rcx
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rdx
  __int64 v182; // rcx
  __int64 v183; // rdx
  __int64 v184; // rcx
  __int64 v185; // rdx
  void *v186; // rcx
  __int64 v187; // rdx
  void *v188; // rcx
  __int64 v189; // rax
  __int64 v190; // rax
  __int64 v191; // rdx
  __int64 v192; // rcx
  __int64 v193; // rdx
  __int64 v194; // rcx
  __int64 v195; // rax
  __int64 v196; // rax
  __int64 v197; // rdx
  __int64 v198; // rcx
  __int64 v199; // rdx
  __int64 v200; // rcx
  __int64 v201; // rax
  _DWORD *v202; // rcx
  __int64 v203; // rax
  __int64 v204; // rax
  __int64 v205; // rdx
  __int64 v206; // rcx
  __int64 v207; // rdx
  __int64 v208; // rcx
  __int64 v209; // rax
  __int64 v210; // rax
  __int64 v211; // rdx
  __int64 v212; // rcx
  __int64 v213; // rdx
  __int64 v214; // rcx
  __int64 v215; // rdx
  void *v216; // rcx
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // rdx
  __int64 v220; // rcx
  __int64 v221; // rdx
  __int64 v222; // rcx
  __int64 v223; // rax
  __int64 v224; // rax
  __int64 v225; // rdx
  __int64 v226; // rcx
  _QWORD *v227; // rax
  __int64 v228; // rcx
  __int128 *v229; // r9
  IPv4Helper *v230; // rcx
  IPv6Helper *v231; // rcx
  _QWORD *v232; // rsi
  _QWORD *v233; // rbx
  _QWORD *v234; // rdi
  HANDLE v235; // rax
  HANDLE v236; // rax
  __int64 v237; // rax
  __int64 v238; // rax
  __int64 v239; // rcx
  _QWORD *v240; // rax
  __int64 v241; // rcx
  __int128 *v242; // r9
  __int64 v243; // rax
  __int64 v244; // rax
  __int64 v245; // rcx
  _QWORD *v246; // rax
  __int64 v247; // rcx
  __int128 *v248; // r9
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  unsigned int Value; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v252; // [rsp+34h] [rbp-CCh]
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v254; // [rsp+3Ch] [rbp-C4h]
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v256; // [rsp+48h] [rbp-B8h]
  int v257; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v259; // [rsp+60h] [rbp-A0h]
  _QWORD *v260; // [rsp+70h] [rbp-90h]
  _BYTE v261[18]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v262; // [rsp+90h] [rbp-70h] BYREF
  __int128 v263; // [rsp+98h] [rbp-68h]
  __int128 v264; // [rsp+A8h] [rbp-58h]
  __int64 v265; // [rsp+B8h] [rbp-48h]
  int v266; // [rsp+C0h] [rbp-40h]
  int v267; // [rsp+C4h] [rbp-3Ch]
  __int128 v268; // [rsp+C8h] [rbp-38h] BYREF
  GUID Buf1; // [rsp+D8h] [rbp-28h] BYREF
  int v270; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v271; // [rsp+ECh] [rbp-14h]
  __int128 v272; // [rsp+FCh] [rbp-4h]
  int v273; // [rsp+10Ch] [rbp+Ch]
  unsigned __int16 v274[8]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v275; // [rsp+120h] [rbp+20h]
  __int16 v276; // [rsp+130h] [rbp+30h]
  int v277; // [rsp+140h] [rbp+40h] BYREF
  char v278[2044]; // [rsp+144h] [rbp+44h] BYREF
  unsigned __int16 v279[280]; // [rsp+940h] [rbp+840h] BYREF

  v260 = a2;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  Value = 0;
  memset_0(v279, 0, 0x222u);
  *(_OWORD *)v274 = 0;
  v275 = 0;
  v276 = 0;
  Buf1 = GUID_NULL;
  v257 = 0;
  v277 = 0;
  memset_0(v278, 0, sizeof(v278));
  v270 = 0;
  v271 = 0;
  v272 = 0;
  v273 = 0;
  v268 = 0;
  v263 = 0;
  v262 = 0;
  v264 = 0;
  v265 = 0;
  v8 = -1;
  v266 = -1;
  v267 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v262,
      L"ServerBFEHandler::ProcessCP",
      &Value,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      *(void **)(a1 + 48));
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  Buf1 = *(GUID *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 112LL) + 2120LL);
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    LOBYTE(v9) = ServerBFEHandler::V4EnabledGlobal;
    v254 = v9;
    v10 = ServerBFEHandler::V6EnabledGlobal;
    v252 = ServerBFEHandler::V6EnabledGlobal;
    goto LABEL_37;
  }
  Value = VPNIKEProtocolEngine::PEHelperFunctions(&Buf1, &v257);
  if ( Value )
  {
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_25;
    LOWORD(v277) = 0;
    LOWORD(v270) = 0;
    v11 = *(_QWORD *)(a1 + 48);
    if ( v11 )
    {
      v12 = *(_QWORD *)(v11 + 112);
      if ( v12 )
      {
        if ( *(_QWORD *)(v12 + 16) )
          v8 = *(_DWORD *)(v12 + 16);
      }
    }
    ConvertPortNoToString(&v270, v8);
    FormatRRASErrorString(
      &v277,
      L"VPNIKEProtocolEngine::PEHelperFunctions.lpfnRouterTypeLookup failed with error %d",
      Value);
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_25;
    v13 = *(_QWORD *)(a1 + 48);
    v14 = (_QWORD *)(v13 + 112);
    if ( v13 )
    {
      if ( *v14 )
        v15 = *v14 + 2686LL;
      else
        v15 = 0;
      if ( *v14 )
      {
        v16 = (__int128 *)(*v14 + 2120LL);
LABEL_24:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v277,
          (_DWORD)v16,
          v15,
          (__int64)&v270);
LABEL_25:
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
        {
          goto LABEL_662;
        }
        v18 = 15;
        goto LABEL_29;
      }
    }
    else
    {
      v15 = 0;
    }
    v16 = &v268;
    goto LABEL_24;
  }
  LOBYTE(v9) = 0;
  v254 = v9;
  v10 = 0;
  v252 = 0;
  if ( ServerBFEHandler::V4EnabledGlobal )
  {
    LOBYTE(v9) = (v257 & 5) != 0;
    v254 = (unsigned __int8)v9;
  }
  if ( ServerBFEHandler::V6EnabledGlobal && ((v257 & 0x20) != 0 || (v257 & 8) != 0) )
  {
    v10 = 1;
    v252 = 1;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_37:
  v20 = (_BYTE)v9 == 0;
  v21 = v10 == 0;
  if ( a4 != 1 )
  {
    Value = 87;
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_54;
    LOWORD(v277) = 0;
    LOWORD(v270) = 0;
    v22 = *(_QWORD *)(a1 + 48);
    if ( v22 )
    {
      v23 = *(_QWORD *)(v22 + 112);
      if ( v23 )
      {
        if ( *(_QWORD *)(v23 + 16) )
          v8 = *(_DWORD *)(v23 + 16);
      }
    }
    ConvertPortNoToString(&v270, v8);
    FormatRRASErrorString(&v277, L"Invalid type %d ", a4);
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_53:
      v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_54:
      if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 1) == 0 || *((_BYTE *)v7 + 25) < 6u )
        goto LABEL_662;
      v18 = 16;
LABEL_659:
      v54 = v7[2];
LABEL_660:
      v19 = Value;
      goto LABEL_661;
    }
    v24 = *(_QWORD *)(a1 + 48);
    v25 = (_QWORD *)(v24 + 112);
    if ( v24 )
    {
      if ( *v25 )
        v26 = *v25 + 2686LL;
      else
        v26 = 0;
      if ( *v25 )
      {
        v27 = (__int128 *)(*v25 + 2120LL);
LABEL_52:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v277,
          (_DWORD)v27,
          v26,
          (__int64)&v270);
        goto LABEL_53;
      }
    }
    else
    {
      v26 = 0;
    }
    v27 = &v268;
    goto LABEL_52;
  }
  if ( !a3 || (v28 = v260) == 0 )
  {
    Value = 87;
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_655;
    LOWORD(v270) = 0;
    v243 = *(_QWORD *)(a1 + 48);
    if ( v243 )
    {
      v244 = *(_QWORD *)(v243 + 112);
      if ( v244 )
      {
        if ( *(_QWORD *)(v244 + 16) )
          v8 = *(_DWORD *)(v244 + 16);
      }
    }
    ConvertPortNoToString(&v270, v8);
    if ( (byte_1800AA941 & 4) == 0 )
    {
LABEL_654:
      v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_655:
      if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 1) == 0 || *((_BYTE *)v7 + 25) < 6u )
        goto LABEL_662;
      v18 = 17;
      goto LABEL_659;
    }
    v245 = *(_QWORD *)(a1 + 48);
    v246 = (_QWORD *)(v245 + 112);
    if ( v245 )
    {
      if ( *v246 )
        v247 = *v246 + 2686LL;
      else
        v247 = 0;
      if ( *v246 )
      {
        v248 = (__int128 *)(*v246 + 2120LL);
LABEL_653:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid param",
          (_DWORD)v248,
          v247,
          (__int64)&v270);
        goto LABEL_654;
      }
    }
    else
    {
      v247 = 0;
    }
    v248 = &v268;
    goto LABEL_653;
  }
  v256 = 0;
  hKey[0] = 0;
  *(_DWORD *)Data = 0;
  cbData[0] = 4;
  Value = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 1u, hKey);
  if ( !Value )
  {
    Value = RegQueryValueExA(hKey[0], "SkipConfigPayload", 0, 0, Data, cbData);
    if ( !Value )
      v256 = *(_DWORD *)Data != 0;
    RegCloseKey(hKey[0]);
  }
  Value = 0;
  BaseConnection::GetRemoteUserName(*(BaseConnection **)(a1 + 48), v279, v29);
  BaseConnection::GetPortName(*(BaseConnection **)(a1 + 48), v274, v30);
  v31 = *(_QWORD *)(a1 + 48);
  if ( !*(_QWORD *)(v31 + 120) || (byte_1800AA941 & 8) == 0 )
    goto LABEL_81;
  LOWORD(v277) = 0;
  LOWORD(v270) = 0;
  if ( v31 && (v32 = *(_QWORD *)(v31 + 112)) != 0 && *(_QWORD *)(v32 + 16) )
    v33 = *(unsigned int *)(v32 + 16);
  else
    v33 = 0xFFFFFFFFLL;
  ConvertPortNoToString(&v270, v33);
  FormatRRASErrorString(&v277, L" username = %s portname = %s", v279, v274);
  if ( (byte_1800AA941 & 8) == 0 )
    goto LABEL_81;
  v34 = *(_QWORD *)(a1 + 48);
  v35 = (_QWORD *)(v34 + 112);
  if ( !v34 )
  {
    v36 = 0;
LABEL_79:
    v37 = &v268;
    goto LABEL_80;
  }
  if ( *v35 )
    v36 = *v35 + 2686LL;
  else
    v36 = 0;
  if ( !*v35 )
    goto LABEL_79;
  v37 = (__int128 *)(*v35 + 2120LL);
LABEL_80:
  McTemplateU0zjzz_EventWriteTransfer(
    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
    (unsigned int)RasVpnIkeParamTraceInfo,
    (unsigned int)&v277,
    (_DWORD)v37,
    v36,
    (__int64)&v270);
LABEL_81:
  ProcessHeap = GetProcessHeap();
  v39 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  *v28 = v39;
  if ( !v39 )
  {
    Value = 8;
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_97;
    LOWORD(v270) = 0;
    v40 = *(_QWORD *)(a1 + 48);
    if ( v40 )
    {
      v41 = *(_QWORD *)(v40 + 112);
      if ( v41 )
      {
        if ( *(_QWORD *)(v41 + 16) )
          v8 = *(_DWORD *)(v41 + 16);
      }
    }
    ConvertPortNoToString(&v270, v8);
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_97;
    v42 = *(_QWORD *)(a1 + 48);
    v43 = (_QWORD *)(v42 + 112);
    if ( v42 )
    {
      if ( *v43 )
        v44 = *v43 + 2686LL;
      else
        v44 = 0;
      if ( *v43 )
      {
        v45 = (__int128 *)(*v43 + 2120LL);
LABEL_96:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Failed to allocate Payload Response",
          (_DWORD)v45,
          v44,
          (__int64)&v270);
LABEL_97:
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
        {
          goto LABEL_662;
        }
        v18 = 18;
LABEL_29:
        v19 = Value;
LABEL_121:
        v54 = (PVOID)v17[2];
LABEL_661:
        WPP_SF_d(v54, v18, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v19);
        goto LABEL_662;
      }
    }
    else
    {
      v44 = 0;
    }
    v45 = &v268;
    goto LABEL_96;
  }
  *v39 = 2;
  *(_QWORD *)cbData = *v28 + 8LL;
  v46 = *(HKEY *)(a3 + 8);
  if ( !v46 )
  {
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_117;
    LOWORD(v270) = 0;
    v47 = *(_QWORD *)(a1 + 48);
    if ( v47 )
    {
      v48 = *(_QWORD *)(v47 + 112);
      if ( v48 )
      {
        if ( *(_QWORD *)(v48 + 16) )
          v8 = *(_DWORD *)(v48 + 16);
      }
    }
    ConvertPortNoToString(&v270, v8);
    if ( (byte_1800AA941 & 8) == 0 )
      goto LABEL_117;
    v49 = *(_QWORD *)(a1 + 48);
    v50 = (_QWORD *)(v49 + 112);
    if ( v49 )
    {
      if ( *v50 )
        v51 = *v50 + 2686LL;
      else
        v51 = 0;
      if ( *v50 )
      {
        v52 = (__int128 *)(*v50 + 2120LL);
LABEL_116:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Received a CFG_REQUEST with zero configuration attributes",
          (_DWORD)v52,
          v51,
          (__int64)&v270);
LABEL_117:
        *(_QWORD *)(*v260 + 8LL) = 0;
        v53 = 0;
        Value = 0;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
        {
          goto LABEL_663;
        }
        v18 = 19;
        v19 = 0;
        goto LABEL_121;
      }
    }
    else
    {
      v51 = 0;
    }
    v52 = &v268;
    goto LABEL_116;
  }
  v55 = 0;
  v56 = 0;
  v57 = 0;
  *(_DWORD *)Data = 0;
  if ( *((_DWORD *)v46 + 2) == 1 )
  {
    v20 = 1;
  }
  else if ( *((_DWORD *)v46 + 2) == 8 )
  {
    v21 = 1;
  }
  for ( i = v46; (!v20 || !v21) && i && (unsigned int)v56 < 0x64; i = *(HKEY *)i )
  {
    v56 = (unsigned int)(v56 + 1);
    if ( *((_DWORD *)i + 2) == 8 )
    {
      if ( v46 != i && (*((_DWORD *)v46 + 2) != 1 || i != *(HKEY *)v46) )
      {
        *v55 = *(_QWORD *)i;
        *(_QWORD *)i = v46;
        v46 = i;
        i = (HKEY)v55;
      }
      v21 = 1;
    }
    if ( *((_DWORD *)i + 2) == 1 )
    {
      if ( v46 != i && (*((_DWORD *)v46 + 2) != 8 || i != *(HKEY *)v46) )
      {
        *v55 = *(_QWORD *)i;
        *(_QWORD *)i = v46;
        v46 = i;
        i = (HKEY)v55;
      }
      v20 = 1;
    }
    v55 = i;
  }
  *(_QWORD *)(a3 + 8) = v46;
  v59 = v254;
  while ( 1 )
  {
    v60 = &SupportedAttribs;
    hKey[0] = v46;
    if ( !v46 )
      break;
    v61 = *((_DWORD *)v46 + 2);
    if ( v61 > 23456 )
    {
      if ( v61 != 23457 )
        goto LABEL_340;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
      }
      if ( (v57 & 0x80u) == 0 || !v252 || ((_BYTE)v46[3] & 0xF) != 0 )
      {
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v270) = 0;
          v217 = *(_QWORD *)(a1 + 48);
          if ( v217 && (v218 = *(_QWORD *)(v217 + 112)) != 0 && *(_QWORD *)(v218 + 16) )
            v219 = *(unsigned int *)(v218 + 16);
          else
            v219 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v270, v219);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v220 = *(_QWORD *)(a1 + 48);
            if ( v220 )
            {
              v221 = *(_QWORD *)(v220 + 112);
              if ( v221 )
                v74 = v221 + 2686;
              else
                v74 = 0;
              v222 = *(_QWORD *)(v220 + 112);
              if ( v222 )
              {
                LODWORD(v76) = v222 + 2120;
LABEL_586:
                v77 = L"Ignoring INTERNAL_IP6_SERVER";
                goto LABEL_295;
              }
            }
            else
            {
              v74 = 0;
            }
            v76 = &v268;
            goto LABEL_586;
          }
        }
        goto LABEL_340;
      }
      if ( (v57 & 0x8000) != 0 )
        goto LABEL_553;
      if ( !IN6_IS_ADDR_UNSPECIFIED(*(const IN6_ADDR **)(*(_QWORD *)(a1 + 48) + 40LL)) )
      {
        ServerBFEHandler::AddNewAttributeTLV((__int64)v216, v215, (LPVOID **)cbData, 23457, 0x10u, v216);
        v57 |= 0x8000u;
        goto LABEL_456;
      }
    }
    else if ( v61 == 23456 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
      }
      if ( (v57 & 1) != 0 && v59 && ((_BYTE)v46[3] & 3) == 0 )
      {
        if ( (v57 & 0x4000) != 0 )
        {
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v270) = 0;
            v195 = *(_QWORD *)(a1 + 48);
            if ( v195 && (v196 = *(_QWORD *)(v195 + 112)) != 0 && *(_QWORD *)(v196 + 16) )
              v197 = *(unsigned int *)(v196 + 16);
            else
              v197 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v270, v197);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v198 = *(_QWORD *)(a1 + 48);
              if ( v198 )
              {
                v199 = *(_QWORD *)(v198 + 112);
                if ( v199 )
                  v74 = v199 + 2686;
                else
                  v74 = 0;
                v200 = *(_QWORD *)(v198 + 112);
                if ( v200 )
                {
                  LODWORD(v76) = v200 + 2120;
LABEL_525:
                  v77 = L"INTERNAL_IP4_SERVER_FLAG already processed";
                  goto LABEL_295;
                }
              }
              else
              {
                v74 = 0;
              }
              v76 = &v268;
              goto LABEL_525;
            }
          }
        }
        else
        {
          v201 = *(_QWORD *)(a1 + 48);
          v202 = *(_DWORD **)(v201 + 32);
          if ( *v202 )
          {
            ServerBFEHandler::AddNewAttributeTLV(
              (__int64)v202,
              (__int64)v60,
              (LPVOID **)cbData,
              23456,
              4u,
              *(void **)(v201 + 32));
            v57 |= 0x4000u;
            goto LABEL_456;
          }
        }
      }
      else if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v270) = 0;
        v203 = *(_QWORD *)(a1 + 48);
        if ( v203 && (v204 = *(_QWORD *)(v203 + 112)) != 0 && *(_QWORD *)(v204 + 16) )
          v205 = *(unsigned int *)(v204 + 16);
        else
          v205 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v270, v205);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v206 = *(_QWORD *)(a1 + 48);
          if ( v206 )
          {
            v207 = *(_QWORD *)(v206 + 112);
            if ( v207 )
              v74 = v207 + 2686;
            else
              v74 = 0;
            v208 = *(_QWORD *)(v206 + 112);
            if ( v208 )
            {
              LODWORD(v76) = v208 + 2120;
LABEL_543:
              v77 = L"Ignoring INTERNAL_IP4_SERVER";
              goto LABEL_295;
            }
          }
          else
          {
            v74 = 0;
          }
          v76 = &v268;
          goto LABEL_543;
        }
      }
    }
    else if ( v61 > 8 )
    {
      v174 = v61 - 10;
      if ( v174 )
      {
        v175 = v174 - 1;
        if ( v175 )
        {
          v176 = v175 - 1;
          if ( v176 )
          {
            v177 = v176 - 2;
            if ( !v177 )
            {
              v178 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
              }
              if ( v59 )
              {
                if ( v252 )
                  ServerBFEHandler::AddNewAttributeTLV(
                    (__int64)v178,
                    (__int64)&SupportedAttribs,
                    (LPVOID **)cbData,
                    14,
                    0xEu,
                    &SupportedAttribs);
                else
                  ServerBFEHandler::AddNewAttributeTLV(
                    (__int64)v178,
                    (__int64)&SupportedAttribs,
                    (LPVOID **)cbData,
                    14,
                    8u,
                    &SupportedAttribs);
              }
              else if ( v252 )
              {
                ServerBFEHandler::AddNewAttributeTLV(
                  (__int64)v178,
                  (__int64)&SupportedAttribs,
                  (LPVOID **)cbData,
                  14,
                  6u,
                  &qword_1800AA220);
              }
              v57 |= 0x1000u;
              goto LABEL_456;
            }
            if ( v177 != 1 )
              goto LABEL_340;
          }
        }
        v67 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v68 = 29;
          goto LABEL_160;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
        }
        if ( (v57 & 0x80u) == 0 || !v252 || ((_BYTE)v46[3] & 0xF) != 0 )
        {
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v270) = 0;
            v189 = *(_QWORD *)(a1 + 48);
            if ( v189 && (v190 = *(_QWORD *)(v189 + 112)) != 0 && *(_QWORD *)(v190 + 16) )
              v191 = *(unsigned int *)(v190 + 16);
            else
              v191 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v270, v191);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v192 = *(_QWORD *)(a1 + 48);
              if ( v192 )
              {
                v193 = *(_QWORD *)(v192 + 112);
                if ( v193 )
                  v74 = v193 + 2686;
                else
                  v74 = 0;
                v194 = *(_QWORD *)(v192 + 112);
                if ( v194 )
                {
                  LODWORD(v76) = v194 + 2120;
LABEL_501:
                  v77 = L"Ignoring INTERNAL_IP6_DNS";
                  goto LABEL_295;
                }
              }
              else
              {
                v74 = 0;
              }
              v76 = &v268;
              goto LABEL_501;
            }
          }
        }
        else
        {
          if ( (v57 & 0x100) == 0 )
          {
            if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 40LL) + 16LL)) )
              ServerBFEHandler::AddNewAttributeTLV((__int64)v186, v185, (LPVOID **)cbData, 10, 0x10u, v186);
            if ( !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 40LL) + 32LL)) )
              ServerBFEHandler::AddNewAttributeTLV((__int64)v188, v187, (LPVOID **)cbData, 10, 0x10u, v188);
            v57 |= 0x100u;
            goto LABEL_456;
          }
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v270) = 0;
            v179 = *(_QWORD *)(a1 + 48);
            if ( v179 && (v180 = *(_QWORD *)(v179 + 112)) != 0 && *(_QWORD *)(v180 + 16) )
              v181 = *(unsigned int *)(v180 + 16);
            else
              v181 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v270, v181);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v182 = *(_QWORD *)(a1 + 48);
              if ( v182 )
              {
                v183 = *(_QWORD *)(v182 + 112);
                if ( v183 )
                  v74 = v183 + 2686;
                else
                  v74 = 0;
                v184 = *(_QWORD *)(v182 + 112);
                if ( v184 )
                {
                  LODWORD(v76) = v184 + 2120;
LABEL_480:
                  v77 = L"INTERNAL_IP6_DNS already processed";
                  goto LABEL_295;
                }
              }
              else
              {
                v74 = 0;
              }
              v76 = &v268;
              goto LABEL_480;
            }
          }
        }
      }
    }
    else if ( v61 == 8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
      }
      if ( !v252 || (v56 = *((unsigned int *)v46 + 3), v56 != 17 * (v56 / 0x11)) || v256 )
      {
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v270) = 0;
          v168 = *(_QWORD *)(a1 + 48);
          if ( v168 && (v169 = *(_QWORD *)(v168 + 112)) != 0 && *(_QWORD *)(v169 + 16) )
            v170 = *(unsigned int *)(v169 + 16);
          else
            v170 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v270, v170);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v171 = *(_QWORD *)(a1 + 48);
            if ( v171 )
            {
              v172 = *(_QWORD *)(v171 + 112);
              if ( v172 )
                v74 = v172 + 2686;
              else
                v74 = 0;
              v173 = *(_QWORD *)(v171 + 112);
              if ( v173 )
              {
                LODWORD(v76) = v173 + 2120;
LABEL_435:
                v77 = L"Ignoring INTERNAL_IP6_ADDRESS";
                goto LABEL_295;
              }
            }
            else
            {
              v74 = 0;
            }
            v76 = &v268;
            goto LABEL_435;
          }
        }
        goto LABEL_340;
      }
      if ( (v57 & 0x80u) != 0 )
      {
LABEL_553:
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v270) = 0;
          v209 = *(_QWORD *)(a1 + 48);
          if ( v209 && (v210 = *(_QWORD *)(v209 + 112)) != 0 && *(_QWORD *)(v210 + 16) )
            v211 = *(unsigned int *)(v210 + 16);
          else
            v211 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v270, v211);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v212 = *(_QWORD *)(a1 + 48);
            if ( v212 )
            {
              v213 = *(_QWORD *)(v212 + 112);
              if ( v213 )
                v74 = v213 + 2686;
              else
                v74 = 0;
              v214 = *(_QWORD *)(v212 + 112);
              if ( v214 )
              {
                LODWORD(v76) = v214 + 2120;
LABEL_568:
                v77 = L"INTERNAL_IP6_SERVER already processed";
                goto LABEL_295;
              }
            }
            else
            {
              v74 = 0;
            }
            v76 = &v268;
            goto LABEL_568;
          }
        }
        goto LABEL_340;
      }
      v259 = 0u;
      if ( (_DWORD)v56 )
        v259 = *((_OWORD *)v46 + 1);
      v151 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 40LL);
      *(_OWORD *)hKey = v259;
      Value = IPv6Helper::AcquireIPAddressForClient(
                (IPv6Helper *)v151,
                (struct in6_addr *)hKey,
                (struct in6_addr *)(v151 + 52),
                v279,
                v274);
      if ( !Value )
      {
        *(_OWORD *)&v261[1] = 0;
        strcpy(&v261[16], "@");
        v159 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 40LL);
        *(_OWORD *)v261 = *(_OWORD *)(v159 + 52);
        Value = ServerBFEHandler::AddNewAttributeTLV(v159, v152, (LPVOID **)cbData, 8, 0x11u, v261);
        if ( Value )
          goto LABEL_340;
        if ( (byte_1800AA941 & 8) != 0 )
        {
          LOWORD(v270) = 0;
          v160 = *(_QWORD *)(a1 + 48);
          if ( v160 && (v161 = *(_QWORD *)(v160 + 112)) != 0 && *(_QWORD *)(v161 + 16) )
            v162 = *(unsigned int *)(v161 + 16);
          else
            v162 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v270, v162);
          if ( (byte_1800AA941 & 8) != 0 )
          {
            v163 = *(_QWORD *)(a1 + 48);
            if ( v163 )
            {
              v164 = *(_QWORD *)(v163 + 112);
              if ( v164 )
                v165 = v164 + 2686;
              else
                v165 = 0;
              v166 = *(_QWORD *)(v163 + 112);
              if ( v166 )
              {
                LODWORD(v167) = v166 + 2120;
                goto LABEL_418;
              }
            }
            else
            {
              v165 = 0;
            }
            v167 = &v268;
LABEL_418:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceInfo,
              (unsigned int)L"Processed INTERNAL_IP6_ADDRESS successfully",
              (_DWORD)v167,
              v165,
              (__int64)&v270);
          }
        }
        v57 |= 0x80u;
LABEL_456:
        *(_DWORD *)Data = v57;
        goto LABEL_340;
      }
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v277) = 0;
        LOWORD(v270) = 0;
        v153 = *(_QWORD *)(a1 + 48);
        if ( v153 && (v154 = *(_QWORD *)(v153 + 112)) != 0 && *(_QWORD *)(v154 + 16) )
          v155 = *(unsigned int *)(v154 + 16);
        else
          v155 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v270, v155);
        FormatRRASErrorString(&v277, L"Acquire IP address for client failed. Error= %d", Value);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v156 = *(_QWORD *)(a1 + 48);
          if ( v156 )
          {
            v157 = *(_QWORD *)(v156 + 112);
            if ( v157 )
              v74 = v157 + 2686;
            else
              v74 = 0;
            v158 = *(_QWORD *)(v156 + 112);
            if ( v158 )
            {
              LODWORD(v76) = v158 + 2120;
LABEL_401:
              v77 = (const wchar_t *)&v277;
              goto LABEL_295;
            }
          }
          else
          {
            v74 = 0;
          }
          v76 = &v268;
          goto LABEL_401;
        }
      }
    }
    else
    {
      v62 = v61 - 1;
      if ( v62 )
      {
        v63 = v62 - 1;
        if ( v63 )
        {
          v64 = v63 - 1;
          if ( v64 )
          {
            v65 = v64 - 1;
            if ( v65 )
            {
              v66 = v65 - 1;
              if ( !v66 || v66 == 2 )
              {
                v67 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  v68 = 25;
LABEL_160:
                  WPP_SF_(v67[2], v68, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
                }
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
              }
              if ( (v57 & 1) != 0 && v59 && ((_BYTE)v46[3] & 3) == 0 )
              {
                if ( (v57 & 8) != 0 )
                {
                  if ( (byte_1800AA941 & 8) != 0 )
                  {
                    LOWORD(v270) = 0;
                    v69 = *(_QWORD *)(a1 + 48);
                    if ( v69 && (v70 = *(_QWORD *)(v69 + 112)) != 0 && *(_QWORD *)(v70 + 16) )
                      v71 = *(unsigned int *)(v70 + 16);
                    else
                      v71 = 0xFFFFFFFFLL;
                    ConvertPortNoToString(&v270, v71);
                    if ( (byte_1800AA941 & 8) != 0 )
                    {
                      v72 = *(_QWORD *)(a1 + 48);
                      if ( v72 )
                      {
                        v73 = *(_QWORD *)(v72 + 112);
                        if ( v73 )
                          v74 = v73 + 2686;
                        else
                          v74 = 0;
                        v75 = *(_QWORD *)(v72 + 112);
                        if ( v75 )
                        {
                          LODWORD(v76) = v75 + 2120;
LABEL_184:
                          v77 = L"INTERNAL_IP4_NBNS already processed";
                          goto LABEL_295;
                        }
                      }
                      else
                      {
                        v74 = 0;
                      }
                      v76 = &v268;
                      goto LABEL_184;
                    }
                  }
                }
                else
                {
                  v78 = *(_QWORD *)(a1 + 48);
                  v79 = (_DWORD *)(*(_QWORD *)(v78 + 32) + 4LL);
                  if ( *v79 )
                    ServerBFEHandler::AddNewAttributeTLV(
                      (__int64)v79,
                      (__int64)v60,
                      (LPVOID **)cbData,
                      4,
                      4u,
                      (void *)(*(_QWORD *)(v78 + 32) + 4LL));
                  v80 = *(_QWORD *)(a1 + 48);
                  v81 = (_DWORD *)(*(_QWORD *)(v80 + 32) + 8LL);
                  if ( *v81 )
                    ServerBFEHandler::AddNewAttributeTLV(
                      (__int64)v81,
                      (__int64)v60,
                      (LPVOID **)cbData,
                      4,
                      4u,
                      (void *)(*(_QWORD *)(v80 + 32) + 8LL));
                  v57 |= 8u;
                  *(_DWORD *)Data = v57;
                }
              }
              else if ( (byte_1800AA941 & 8) != 0 )
              {
                LOWORD(v270) = 0;
                v82 = *(_QWORD *)(a1 + 48);
                if ( v82 && (v83 = *(_QWORD *)(v82 + 112)) != 0 && *(_QWORD *)(v83 + 16) )
                  v84 = *(unsigned int *)(v83 + 16);
                else
                  v84 = 0xFFFFFFFFLL;
                ConvertPortNoToString(&v270, v84);
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  v85 = *(_QWORD *)(a1 + 48);
                  if ( v85 )
                  {
                    v86 = *(_QWORD *)(v85 + 112);
                    if ( v86 )
                      v74 = v86 + 2686;
                    else
                      v74 = 0;
                    v87 = *(_QWORD *)(v85 + 112);
                    if ( v87 )
                    {
                      LODWORD(v76) = v87 + 2120;
LABEL_205:
                      v77 = L"Ignoring INTERNAL_IP4_NBNS";
                      goto LABEL_295;
                    }
                  }
                  else
                  {
                    v74 = 0;
                  }
                  v76 = &v268;
                  goto LABEL_205;
                }
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
            }
            if ( (v57 & 1) != 0 && v59 && ((_BYTE)v46[3] & 3) == 0 )
            {
              if ( (v57 & 4) == 0 )
              {
                v94 = *(_QWORD *)(a1 + 48);
                v95 = (_DWORD *)(*(_QWORD *)(v94 + 32) + 12LL);
                if ( *v95 )
                  ServerBFEHandler::AddNewAttributeTLV(
                    (__int64)v95,
                    (__int64)v60,
                    (LPVOID **)cbData,
                    3,
                    4u,
                    (void *)(*(_QWORD *)(v94 + 32) + 12LL));
                v96 = *(_QWORD *)(a1 + 48);
                v97 = (_DWORD *)(*(_QWORD *)(v96 + 32) + 16LL);
                if ( *v97 )
                  ServerBFEHandler::AddNewAttributeTLV(
                    (__int64)v97,
                    (__int64)v60,
                    (LPVOID **)cbData,
                    3,
                    4u,
                    (void *)(*(_QWORD *)(v96 + 32) + 16LL));
                v57 |= 4u;
                goto LABEL_456;
              }
              if ( (byte_1800AA941 & 8) != 0 )
              {
                LOWORD(v270) = 0;
                v88 = *(_QWORD *)(a1 + 48);
                if ( v88 && (v89 = *(_QWORD *)(v88 + 112)) != 0 && *(_QWORD *)(v89 + 16) )
                  v90 = *(unsigned int *)(v89 + 16);
                else
                  v90 = 0xFFFFFFFFLL;
                ConvertPortNoToString(&v270, v90);
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  v91 = *(_QWORD *)(a1 + 48);
                  if ( v91 )
                  {
                    v92 = *(_QWORD *)(v91 + 112);
                    if ( v92 )
                      v74 = v92 + 2686;
                    else
                      v74 = 0;
                    v93 = *(_QWORD *)(v91 + 112);
                    if ( v93 )
                    {
                      LODWORD(v76) = v93 + 2120;
LABEL_229:
                      v77 = L"INTERNAL_IP4_DNS already processed";
                      goto LABEL_295;
                    }
                  }
                  else
                  {
                    v74 = 0;
                  }
                  v76 = &v268;
                  goto LABEL_229;
                }
              }
            }
            else if ( (byte_1800AA941 & 8) != 0 )
            {
              LOWORD(v270) = 0;
              v98 = *(_QWORD *)(a1 + 48);
              if ( v98 && (v99 = *(_QWORD *)(v98 + 112)) != 0 && *(_QWORD *)(v99 + 16) )
                v100 = *(unsigned int *)(v99 + 16);
              else
                v100 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v270, v100);
              if ( (byte_1800AA941 & 8) != 0 )
              {
                v101 = *(_QWORD *)(a1 + 48);
                if ( v101 )
                {
                  v102 = *(_QWORD *)(v101 + 112);
                  if ( v102 )
                    v74 = v102 + 2686;
                  else
                    v74 = 0;
                  v103 = *(_QWORD *)(v101 + 112);
                  if ( v103 )
                  {
                    LODWORD(v76) = v103 + 2120;
LABEL_250:
                    v77 = L"Ignoring INTERNAL_IP4_DNS";
                    goto LABEL_295;
                  }
                }
                else
                {
                  v74 = 0;
                }
                v76 = &v268;
                goto LABEL_250;
              }
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
          }
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v270) = 0;
            v104 = *(_QWORD *)(a1 + 48);
            if ( v104 && (v105 = *(_QWORD *)(v104 + 112)) != 0 && *(_QWORD *)(v105 + 16) )
              v106 = *(unsigned int *)(v105 + 16);
            else
              v106 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v270, v106);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v107 = *(_QWORD *)(a1 + 48);
              if ( v107 )
              {
                v108 = *(_QWORD *)(v107 + 112);
                if ( v108 )
                  v74 = v108 + 2686;
                else
                  v74 = 0;
                v109 = *(_QWORD *)(v107 + 112);
                if ( v109 )
                {
                  LODWORD(v76) = v109 + 2120;
                  goto LABEL_270;
                }
              }
              else
              {
                v74 = 0;
              }
              v76 = &v268;
LABEL_270:
              v77 = L"Ignoring INTERNAL_IP4_NETMASK";
LABEL_295:
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasVpnIkeParamTraceInfo,
                (_DWORD)v77,
                (_DWORD)v76,
                v74,
                (__int64)&v270);
            }
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
        }
        if ( !v59 || ((_BYTE)v46[3] & 3) != 0 || v256 )
        {
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v270) = 0;
            v145 = *(_QWORD *)(a1 + 48);
            if ( v145 && (v146 = *(_QWORD *)(v145 + 112)) != 0 && *(_QWORD *)(v146 + 16) )
              v147 = *(unsigned int *)(v146 + 16);
            else
              v147 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v270, v147);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v148 = *(_QWORD *)(a1 + 48);
              if ( v148 )
              {
                v149 = *(_QWORD *)(v148 + 112);
                if ( v149 )
                  v74 = v149 + 2686;
                else
                  v74 = 0;
                v150 = *(_QWORD *)(v148 + 112);
                if ( v150 )
                {
                  LODWORD(v76) = v150 + 2120;
LABEL_374:
                  v77 = L"Ignoring INTERNAL_IP4_ADDRESS";
                  goto LABEL_295;
                }
              }
              else
              {
                v74 = 0;
              }
              v76 = &v268;
              goto LABEL_374;
            }
          }
        }
        else
        {
          if ( (v57 & 1) == 0 )
          {
            v254 = 0;
            if ( *((_DWORD *)v46 + 3) )
            {
              v116 = *((_DWORD *)v46 + 4);
              v254 = v116;
            }
            else
            {
              v116 = v254;
            }
            v117 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 120LL);
            if ( v117 )
            {
              v118 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 near **, unsigned __int64))(*(_QWORD *)v117 + 16LL))(
                       v117,
                       v60,
                       v56);
              v119 = RasAuthAttributeGet(8, v118);
              if ( v119 )
              {
                v120 = ntohl(v119[2]);
                if ( (byte_1800AA941 & 8) != 0 )
                {
                  LOWORD(v277) = 0;
                  LOWORD(v270) = 0;
                  v121 = *(_QWORD *)(a1 + 48);
                  if ( v121 && (v122 = *(_QWORD *)(v121 + 112)) != 0 && *(_QWORD *)(v122 + 16) )
                    v123 = *(unsigned int *)(v122 + 16);
                  else
                    v123 = 0xFFFFFFFFLL;
                  ConvertPortNoToString(&v270, v123);
                  FormatRRASErrorString(&v277, L"ProcessCP IpAddressToHandout: 0x%x", v120);
                  if ( (byte_1800AA941 & 8) != 0 )
                  {
                    v124 = *(_QWORD *)(a1 + 48);
                    v125 = (_QWORD *)(v124 + 112);
                    if ( v124 )
                    {
                      if ( *v125 )
                        v126 = *v125 + 2686LL;
                      else
                        v126 = 0;
                      if ( *v125 )
                      {
                        v127 = (__int128 *)(*v125 + 2120LL);
                        goto LABEL_316;
                      }
                    }
                    else
                    {
                      v126 = 0;
                    }
                    v127 = &v268;
LABEL_316:
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasVpnIkeParamTraceInfo,
                      (unsigned int)&v277,
                      (_DWORD)v127,
                      v126,
                      (__int64)&v270);
                  }
                }
                if ( v120 == -16777217 )
                {
                  v116 = 0;
                }
                else if ( v120 != -1 )
                {
                  v116 = v120;
                }
                v46 = hKey[0];
                v254 = v116;
              }
            }
            Value = IPv4Helper::AcquireIPAddressForClient(
                      *(IPv4Helper **)(*(_QWORD *)(a1 + 48) + 32LL),
                      v116,
                      (unsigned int *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 32LL) + 20LL),
                      v279,
                      v274);
            if ( Value )
            {
              if ( (byte_1800AA941 & 4) != 0 )
              {
                LOWORD(v277) = 0;
                LOWORD(v270) = 0;
                v129 = *(_QWORD *)(a1 + 48);
                if ( v129 && (v130 = *(_QWORD *)(v129 + 112)) != 0 && *(_QWORD *)(v130 + 16) )
                  v131 = *(unsigned int *)(v130 + 16);
                else
                  v131 = 0xFFFFFFFFLL;
                ConvertPortNoToString(&v270, v131);
                FormatRRASErrorString(&v277, L"Acquire IP address for client failed. Error:%d", Value);
                if ( (byte_1800AA941 & 4) != 0 )
                {
                  v132 = *(_QWORD *)(a1 + 48);
                  if ( v132 )
                  {
                    v133 = *(_QWORD *)(v132 + 112);
                    if ( v133 )
                      v134 = v133 + 2686;
                    else
                      v134 = 0;
                    v135 = *(_QWORD *)(v132 + 112);
                    if ( v135 )
                    {
                      LODWORD(v136) = v135 + 2120;
                      goto LABEL_338;
                    }
                  }
                  else
                  {
                    v134 = 0;
                  }
                  v136 = &v268;
LABEL_338:
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceError,
                    (unsigned int)&v277,
                    (_DWORD)v136,
                    v134,
                    (__int64)&v270);
                }
              }
LABEL_339:
              v57 = *(_DWORD *)Data;
              goto LABEL_340;
            }
            lpcbData = (LPDWORD)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 32LL) + 20LL);
            Value = ServerBFEHandler::AddNewAttributeTLV((__int64)lpcbData, v128, (LPVOID **)cbData, 1, 4u, lpcbData);
            if ( Value )
              goto LABEL_339;
            if ( (byte_1800AA941 & 8) != 0 )
            {
              LOWORD(v270) = 0;
              v137 = *(_QWORD *)(a1 + 48);
              if ( v137 && (v138 = *(_QWORD *)(v137 + 112)) != 0 && *(_QWORD *)(v138 + 16) )
                v139 = *(unsigned int *)(v138 + 16);
              else
                v139 = 0xFFFFFFFFLL;
              ConvertPortNoToString(&v270, v139);
              if ( (byte_1800AA941 & 8) != 0 )
              {
                v140 = *(_QWORD *)(a1 + 48);
                if ( v140 )
                {
                  v141 = *(_QWORD *)(v140 + 112);
                  if ( v141 )
                    v142 = v141 + 2686;
                  else
                    v142 = 0;
                  v143 = *(_QWORD *)(v140 + 112);
                  if ( v143 )
                  {
                    LODWORD(v144) = v143 + 2120;
                    goto LABEL_357;
                  }
                }
                else
                {
                  v142 = 0;
                }
                v144 = &v268;
LABEL_357:
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceInfo,
                  (unsigned int)L"Processed INTERNAL_IP4_ADDRESS successfully",
                  (_DWORD)v144,
                  v142,
                  (__int64)&v270);
              }
            }
            v57 = *(_DWORD *)Data | 1;
            goto LABEL_456;
          }
          if ( (byte_1800AA941 & 8) != 0 )
          {
            LOWORD(v270) = 0;
            v110 = *(_QWORD *)(a1 + 48);
            if ( v110 && (v111 = *(_QWORD *)(v110 + 112)) != 0 && *(_QWORD *)(v111 + 16) )
              v112 = *(unsigned int *)(v111 + 16);
            else
              v112 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v270, v112);
            if ( (byte_1800AA941 & 8) != 0 )
            {
              v113 = *(_QWORD *)(a1 + 48);
              if ( v113 )
              {
                v114 = *(_QWORD *)(v113 + 112);
                if ( v114 )
                  v74 = v114 + 2686;
                else
                  v74 = 0;
                v115 = *(_QWORD *)(v113 + 112);
                if ( v115 )
                {
                  LODWORD(v76) = v115 + 2120;
LABEL_294:
                  v77 = L"INTERNAL_IP4_ADDRESS already processed";
                  goto LABEL_295;
                }
              }
              else
              {
                v74 = 0;
              }
              v76 = &v268;
              goto LABEL_294;
            }
          }
        }
      }
    }
LABEL_340:
    v46 = *(HKEY *)v46;
  }
  if ( (v57 & 1) != 0 || (v57 & 0x80u) != 0 || v256 )
  {
    Value = 0;
    v230 = *(IPv4Helper **)(*(_QWORD *)(a1 + 48) + 32LL);
    if ( (v57 & 1) != 0 )
      IPv4Helper::SetNegotiate(v230);
    else
      IPv4Helper::ClearNegotiate(v230);
    v231 = *(IPv6Helper **)(*(_QWORD *)(a1 + 48) + 40LL);
    if ( (v57 & 0x80u) == 0 )
      IPv6Helper::ClearNegotiate(v231);
    else
      IPv6Helper::SetNegotiate(v231);
    goto LABEL_612;
  }
  Value = 13899;
  if ( (byte_1800AA941 & 4) == 0 )
    goto LABEL_613;
  LOWORD(v277) = 0;
  LOWORD(v270) = 0;
  v223 = *(_QWORD *)(a1 + 48);
  if ( v223 && (v224 = *(_QWORD *)(v223 + 112)) != 0 && *(_QWORD *)(v224 + 16) )
    v225 = *(unsigned int *)(v224 + 16);
  else
    v225 = 0xFFFFFFFFLL;
  ConvertPortNoToString(&v270, v225);
  FormatRRASErrorString(&v277, L"Unable to assign v4/v6 address to client. Hence return error:%d", Value);
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v226 = *(_QWORD *)(a1 + 48);
    v227 = (_QWORD *)(v226 + 112);
    if ( v226 )
    {
      if ( *v227 )
        v228 = *v227 + 2686LL;
      else
        v228 = 0;
      if ( *v227 )
      {
        v229 = (__int128 *)(*v227 + 2120LL);
        goto LABEL_605;
      }
    }
    else
    {
      v228 = 0;
    }
    v229 = &v268;
LABEL_605:
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasVpnIkeParamTraceError,
      (unsigned int)&v277,
      (_DWORD)v229,
      v228,
      (__int64)&v270);
  }
LABEL_612:
  if ( Value )
  {
LABEL_613:
    v232 = v260;
    v233 = (_QWORD *)*v260;
    if ( *v260 )
    {
      if ( !v233[1] )
        goto LABEL_619;
      do
      {
        v234 = (_QWORD *)v233[1];
        v233[1] = *v234;
        if ( v234 )
        {
          v235 = GetProcessHeap();
          HeapFree(v235, 0, v234);
        }
        v233 = (_QWORD *)*v232;
      }
      while ( *(_QWORD *)(*v232 + 8LL) );
      if ( v233 )
      {
LABEL_619:
        v236 = GetProcessHeap();
        HeapFree(v236, 0, v233);
        *v232 = 0;
      }
    }
  }
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v277) = 0;
    LOWORD(v270) = 0;
    v237 = *(_QWORD *)(a1 + 48);
    if ( v237 )
    {
      v238 = *(_QWORD *)(v237 + 112);
      if ( v238 )
      {
        if ( *(_QWORD *)(v238 + 16) )
          v8 = *(_DWORD *)(v238 + 16);
      }
    }
    ConvertPortNoToString(&v270, v8);
    FormatRRASErrorString(&v277, L"Returning with %d", Value);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      v239 = *(_QWORD *)(a1 + 48);
      v240 = (_QWORD *)(v239 + 112);
      if ( v239 )
      {
        if ( *v240 )
          v241 = *v240 + 2686LL;
        else
          v241 = 0;
        if ( *v240 )
        {
          v242 = (__int128 *)(*v240 + 2120LL);
          goto LABEL_634;
        }
      }
      else
      {
        v241 = 0;
      }
      v242 = &v268;
LABEL_634:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceInfo,
        (unsigned int)&v277,
        (_DWORD)v242,
        v241,
        (__int64)&v270);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v18 = 31;
    v54 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
    goto LABEL_660;
  }
LABEL_662:
  v53 = Value;
LABEL_663:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v262);
  return v53;
}

```

## disassembly

```asm
0x18003de00  push    rbp
0x18003de02  push    rbx
0x18003de03  push    rsi
0x18003de04  push    rdi
0x18003de05  push    r12
0x18003de07  push    r13
0x18003de09  push    r14
0x18003de0b  push    r15
0x18003de0d  lea     rbp, [rsp-0A88h]
0x18003de15  sub     rsp, 0B88h
0x18003de1c  mov     rax, cs:__security_cookie
0x18003de23  xor     rax, rsp
0x18003de26  mov     [rbp+0AC0h+var_50], rax
0x18003de2d  mov     edi, r9d
0x18003de30  mov     r15, r8
0x18003de33  mov     [rsp+0BC0h+var_B50], rdx
0x18003de38  mov     r13, rcx
0x18003de3b  lea     rax, WPP_GLOBAL_Control
0x18003de42  mov     esi, 1
0x18003de47  mov     rbx, cs:WPP_GLOBAL_Control
0x18003de4e  cmp     rbx, rax
0x18003de51  jz      short loc_18003DE79
0x18003de53  test    [rbx+1Ch], sil
0x18003de57  jz      short loc_18003DE79
0x18003de59  cmp     byte ptr [rbx+19h], 6
0x18003de5d  jb      short loc_18003DE79
0x18003de5f  lea     edx, [rsi+0Dh]
0x18003de62  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003de69  mov     rcx, [rbx+10h]
0x18003de6d  call    WPP_SF_
0x18003de72  mov     rbx, cs:WPP_GLOBAL_Control
0x18003de79  xor     r14d, r14d
0x18003de7c  mov     [rsp+0BC0h+var_B90], r14d
0x18003de81  xor     edx, edx; Val
0x18003de83  mov     r8d, 222h; Size
0x18003de89  lea     rcx, [rbp+0AC0h+var_280]; void *
0x18003de90  call    memset_0
0x18003de95  xorps   xmm0, xmm0
0x18003de98  xor     eax, eax
0x18003de9a  movups  xmmword ptr [rbp+0AC0h+var_AB0], xmm0
0x18003de9e  movups  [rbp+0AC0h+var_AA0], xmm0
0x18003dea2  mov     [rbp+0AC0h+var_A90], ax
0x18003dea6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003dead  movdqu  [rbp+0AC0h+Buf1], xmm0
0x18003deb2  mov     [rsp+0BC0h+var_B74], r14d
0x18003deb7  mov     [rbp+0AC0h+var_A80], r14d
0x18003debb  xor     edx, edx; Val
0x18003debd  mov     r8d, 7FCh; Size
0x18003dec3  lea     rcx, [rbp+0AC0h+var_A7C]; void *
0x18003dec7  call    memset_0
0x18003decc  mov     [rbp+0AC0h+var_AD8], r14d
0x18003ded0  xorps   xmm0, xmm0
0x18003ded3  xor     eax, eax
0x18003ded5  movups  [rbp+0AC0h+var_AD4], xmm0
0x18003ded9  movups  [rbp+0AC0h+var_AC4], xmm0
0x18003dedd  mov     [rbp+0AC0h+var_AB4], eax
0x18003dee0  movups  [rbp+0AC0h+var_AF8], xmm0
0x18003dee4  xorps   xmm1, xmm1
0x18003dee7  movdqu  [rbp+0AC0h+var_B28], xmm1
0x18003deec  mov     [rbp+0AC0h+var_B30], r14
0x18003def0  movdqu  [rbp+0AC0h+var_B18], xmm0
0x18003def5  mov     [rbp+0AC0h+var_B08], r14
0x18003def9  or      r12d, 0FFFFFFFFh
0x18003defd  mov     [rbp+0AC0h+var_B00], r12d
0x18003df01  mov     [rbp+0AC0h+var_AFC], r14d
0x18003df05  test    cs:byte_1800AA941, 8
0x18003df0c  jz      short loc_18003DF3A
0x18003df0e  mov     rax, [r13+30h]
0x18003df12  mov     [rsp+0BC0h+phkResult], rax; void *
0x18003df17  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003df1e  lea     r8, [rsp+0BC0h+var_B90]; unsigned int *
0x18003df23  lea     rdx, aServerbfehandl_4; "ServerBFEHandler::ProcessCP"
0x18003df2a  lea     rcx, [rbp+0AC0h+var_B30]; this
0x18003df2e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18003df33  mov     rbx, cs:WPP_GLOBAL_Control
0x18003df3a  mov     rax, [r13+30h]
0x18003df3e  mov     rcx, [rax+70h]
0x18003df42  movups  xmm0, xmmword ptr [rcx+848h]
0x18003df49  movdqu  [rbp+0AC0h+Buf1], xmm0
0x18003df4e  mov     r8d, 10h; Size
0x18003df54  lea     rdx, GUID_NULL; Buf2
0x18003df5b  lea     rcx, [rbp+0AC0h+Buf1]; Buf1
0x18003df5f  call    memcmp_0
0x18003df64  test    eax, eax
0x18003df66  jnz     short loc_18003DF81
0x18003df68  mov     cl, cs:?V4EnabledGlobal@ServerBFEHandler@@2EA; uchar ServerBFEHandler::V4EnabledGlobal
0x18003df6e  mov     [rsp+0BC0h+var_B84], ecx
0x18003df72  mov     dl, cs:?V6EnabledGlobal@ServerBFEHandler@@2EA; uchar ServerBFEHandler::V6EnabledGlobal
0x18003df78  mov     [rsp+0BC0h+var_B8C], dl
0x18003df7c  jmp     loc_18003E0E2
0x18003df81  lea     rdx, [rsp+0BC0h+var_B74]
0x18003df86  lea     rcx, [rbp+0AC0h+Buf1]
0x18003df8a  mov     rax, qword ptr cs:?PEHelperFunctions@VPNIKEProtocolEngine@@2U_PROTOCOL_ENGINE_HELPER_FUNCTIONS@@A; _PROTOCOL_ENGINE_HELPER_FUNCTIONS VPNIKEProtocolEngine::PEHelperFunctions
0x18003df91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df96  mov     [rsp+0BC0h+var_B90], eax
0x18003df9a  test    eax, eax
0x18003df9c  jz      loc_18003E09C
0x18003dfa2  test    cs:byte_1800AA941, 4
0x18003dfa9  jz      loc_18003E062
0x18003dfaf  mov     word ptr [rbp+0AC0h+var_A80], r14w
0x18003dfb4  mov     word ptr [rbp+0AC0h+var_AD8], r14w
0x18003dfb9  mov     rax, [r13+30h]
0x18003dfbd  test    rax, rax
0x18003dfc0  jz      short loc_18003DFD5
0x18003dfc2  mov     rax, [rax+70h]
0x18003dfc6  test    rax, rax
0x18003dfc9  jz      short loc_18003DFD5
0x18003dfcb  cmp     [rax+10h], r14
0x18003dfcf  jz      short loc_18003DFD5
0x18003dfd1  mov     r12d, [rax+10h]
0x18003dfd5  mov     edx, r12d
0x18003dfd8  lea     rcx, [rbp+0AC0h+var_AD8]
0x18003dfdc  call    ConvertPortNoToString
0x18003dfe1  mov     r8d, [rsp+0BC0h+var_B90]
0x18003dfe6  lea     rdx, aVpnikeprotocol_2; "VPNIKEProtocolEngine::PEHelperFunctions"...
0x18003dfed  lea     rcx, [rbp+0AC0h+var_A80]
0x18003dff1  call    FormatRRASErrorString
0x18003dff6  test    cs:byte_1800AA941, 4
0x18003dffd  jz      short loc_18003E062
0x18003dfff  mov     rcx, [r13+30h]
0x18003e003  lea     rax, [rcx+70h]
0x18003e007  test    rcx, rcx
0x18003e00a  jz      short loc_18003E036
0x18003e00c  mov     rdx, [rax]
0x18003e00f  test    rdx, rdx
0x18003e012  jz      short loc_18003E01D
0x18003e014  lea     rcx, [rdx+0A7Eh]
0x18003e01b  jmp     short loc_18003E025
0x18003e01d  test    rcx, rcx
0x18003e020  jz      short loc_18003E036
0x18003e022  mov     rcx, r14
0x18003e025  mov     rdx, [rax]
0x18003e028  test    rdx, rdx
0x18003e02b  jz      short loc_18003E039
0x18003e02d  lea     r9, [rdx+848h]
0x18003e034  jmp     short loc_18003E03D
0x18003e036  mov     rcx, r14
0x18003e039  lea     r9, [rbp+0AC0h+var_AF8]
0x18003e03d  lea     rax, [rbp+0AC0h+var_AD8]
0x18003e041  mov     [rsp+0BC0h+lpcbData], rax
0x18003e046  mov     [rsp+0BC0h+phkResult], rcx
0x18003e04b  lea     r8, [rbp+0AC0h+var_A80]
0x18003e04f  lea     rdx, RasVpnIkeParamTraceError
0x18003e056  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e05d  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e062  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e069  lea     rax, WPP_GLOBAL_Control
0x18003e070  cmp     rcx, rax
0x18003e073  jz      loc_18003FCDA
0x18003e079  test    [rcx+1Ch], sil
0x18003e07d  jz      loc_18003FCDA
0x18003e083  cmp     byte ptr [rcx+19h], 6
0x18003e087  jb      loc_18003FCDA
0x18003e08d  mov     edx, 0Fh
0x18003e092  mov     r9d, [rsp+0BC0h+var_B90]
0x18003e097  jmp     loc_18003E5A0
0x18003e09c  mov     cl, r14b
0x18003e09f  mov     [rsp+0BC0h+var_B84], ecx
0x18003e0a3  mov     dl, r14b
0x18003e0a6  mov     [rsp+0BC0h+var_B8C], dl
0x18003e0aa  mov     eax, [rsp+0BC0h+var_B74]
0x18003e0ae  cmp     cs:?V4EnabledGlobal@ServerBFEHandler@@2EA, r14b; uchar ServerBFEHandler::V4EnabledGlobal
0x18003e0b5  jz      short loc_18003E0C3
0x18003e0b7  test    al, 5
0x18003e0b9  movzx   ecx, cl
0x18003e0bc  cmovnz  ecx, esi
0x18003e0bf  mov     [rsp+0BC0h+var_B84], ecx
0x18003e0c3  cmp     cs:?V6EnabledGlobal@ServerBFEHandler@@2EA, r14b; uchar ServerBFEHandler::V6EnabledGlobal
0x18003e0ca  jz      short loc_18003E0DB
0x18003e0cc  test    al, 20h
0x18003e0ce  jnz     short loc_18003E0D4
0x18003e0d0  test    al, 8
0x18003e0d2  jz      short loc_18003E0DB
0x18003e0d4  mov     dl, sil
0x18003e0d7  mov     [rsp+0BC0h+var_B8C], dl
0x18003e0db  mov     rbx, cs:WPP_GLOBAL_Control
0x18003e0e2  test    cl, cl
0x18003e0e4  setz    sil
0x18003e0e8  test    dl, dl
0x18003e0ea  setz    r14b
0x18003e0ee  cmp     edi, 1
0x18003e0f1  jz      loc_18003E1F1
0x18003e0f7  mov     [rsp+0BC0h+var_B90], 57h ; 'W'
0x18003e0ff  test    cs:byte_1800AA941, 4
0x18003e106  jz      loc_18003E1C3
0x18003e10c  xor     eax, eax
0x18003e10e  mov     word ptr [rbp+0AC0h+var_A80], ax
0x18003e112  mov     word ptr [rbp+0AC0h+var_AD8], ax
0x18003e116  mov     rax, [r13+30h]
0x18003e11a  test    rax, rax
0x18003e11d  jz      short loc_18003E133
0x18003e11f  mov     rax, [rax+70h]
0x18003e123  test    rax, rax
0x18003e126  jz      short loc_18003E133
0x18003e128  cmp     qword ptr [rax+10h], 0
0x18003e12d  jz      short loc_18003E133
0x18003e12f  mov     r12d, [rax+10h]
0x18003e133  mov     edx, r12d
0x18003e136  lea     rcx, [rbp+0AC0h+var_AD8]
0x18003e13a  call    ConvertPortNoToString
0x18003e13f  mov     r8d, edi
0x18003e142  lea     rdx, aInvalidTypeD; "Invalid type %d "
0x18003e149  lea     rcx, [rbp+0AC0h+var_A80]
0x18003e14d  call    FormatRRASErrorString
0x18003e152  test    cs:byte_1800AA941, 4
0x18003e159  jz      short loc_18003E1BC
0x18003e15b  mov     rcx, [r13+30h]
0x18003e15f  lea     rax, [rcx+70h]
0x18003e163  test    rcx, rcx
0x18003e166  jz      short loc_18003E191
0x18003e168  mov     rdx, [rax]
0x18003e16b  test    rdx, rdx
0x18003e16e  jz      short loc_18003E179
0x18003e170  lea     rcx, [rdx+0A7Eh]
0x18003e177  jmp     short loc_18003E180
0x18003e179  test    rcx, rcx
0x18003e17c  jz      short loc_18003E191
0x18003e17e  xor     ecx, ecx
0x18003e180  mov     rdx, [rax]
0x18003e183  test    rdx, rdx
0x18003e186  jz      short loc_18003E193
0x18003e188  lea     r9, [rdx+848h]
0x18003e18f  jmp     short loc_18003E197
0x18003e191  xor     ecx, ecx
0x18003e193  lea     r9, [rbp+0AC0h+var_AF8]
0x18003e197  lea     rax, [rbp+0AC0h+var_AD8]
0x18003e19b  mov     [rsp+0BC0h+lpcbData], rax
0x18003e1a0  mov     [rsp+0BC0h+phkResult], rcx
0x18003e1a5  lea     r8, [rbp+0AC0h+var_A80]
0x18003e1a9  lea     rdx, RasVpnIkeParamTraceError
0x18003e1b0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e1b7  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e1bc  mov     rbx, cs:WPP_GLOBAL_Control
0x18003e1c3  lea     rax, WPP_GLOBAL_Control
0x18003e1ca  cmp     rbx, rax
0x18003e1cd  jz      loc_18003FCDA
0x18003e1d3  test    byte ptr [rbx+1Ch], 1
0x18003e1d7  jz      loc_18003FCDA
0x18003e1dd  cmp     byte ptr [rbx+19h], 6
0x18003e1e1  jb      loc_18003FCDA
0x18003e1e7  mov     edx, 10h
0x18003e1ec  jmp     loc_18003FCC5
0x18003e1f1  test    r15, r15
0x18003e1f4  jz      loc_18003FBF0
0x18003e1fa  mov     rdi, [rsp+0BC0h+var_B50]
0x18003e1ff  test    rdi, rdi
0x18003e202  jz      loc_18003FBF0
0x18003e208  xor     ebx, ebx
0x18003e20a  mov     [rsp+0BC0h+var_B78], ebx
0x18003e20e  mov     [rsp+0BC0h+hKey], rbx
0x18003e213  mov     dword ptr [rsp+0BC0h+Data], ebx
0x18003e217  mov     [rsp+0BC0h+cbData], 4
0x18003e21f  lea     rax, [rsp+0BC0h+hKey]
0x18003e224  mov     [rsp+0BC0h+phkResult], rax; phkResult
0x18003e229  lea     r9d, [rbx+1]; samDesired
0x18003e22d  xor     r8d, r8d; ulOptions
0x18003e230  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x18003e237  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e23e  call    cs:__imp_RegOpenKeyExA
0x18003e244  mov     [rsp+0BC0h+var_B90], eax
0x18003e248  test    eax, eax
0x18003e24a  jnz     short loc_18003E299
0x18003e24c  lea     rax, [rsp+0BC0h+cbData]
0x18003e251  mov     [rsp+0BC0h+lpcbData], rax; lpcbData
0x18003e256  lea     rax, [rsp+0BC0h+Data]
0x18003e25b  mov     [rsp+0BC0h+phkResult], rax; lpData
0x18003e260  xor     r9d, r9d; lpType
0x18003e263  xor     r8d, r8d; lpReserved
0x18003e266  lea     rdx, aSkipconfigpayl; "SkipConfigPayload"
0x18003e26d  mov     rcx, [rsp+0BC0h+hKey]; hKey
0x18003e272  call    cs:__imp_RegQueryValueExA
0x18003e278  mov     [rsp+0BC0h+var_B90], eax
0x18003e27c  test    eax, eax
0x18003e27e  jnz     short loc_18003E28E
0x18003e280  cmp     dword ptr [rsp+0BC0h+Data], ebx
0x18003e284  lea     eax, [rbx+1]
0x18003e287  cmovnz  ebx, eax
0x18003e28a  mov     [rsp+0BC0h+var_B78], ebx
0x18003e28e  mov     rcx, [rsp+0BC0h+hKey]; hKey
0x18003e293  call    cs:__imp_RegCloseKey
0x18003e299  mov     [rsp+0BC0h+var_B90], 0
0x18003e2a1  lea     rdx, [rbp+0AC0h+var_280]; unsigned __int16 *
0x18003e2a8  mov     rcx, [r13+30h]; this
0x18003e2ac  call    ?GetRemoteUserName@BaseConnection@@QEAAKPEAGK@Z; BaseConnection::GetRemoteUserName(ushort *,ulong)
0x18003e2b1  lea     rdx, [rbp+0AC0h+var_AB0]; unsigned __int16 *
0x18003e2b5  mov     rcx, [r13+30h]; this
0x18003e2b9  call    ?GetPortName@BaseConnection@@QEAAKPEAGK@Z; BaseConnection::GetPortName(ushort *,ulong)
0x18003e2be  mov     rcx, [r13+30h]
0x18003e2c2  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e2c9  cmp     qword ptr [rcx+78h], 0
0x18003e2ce  jz      loc_18003E392
0x18003e2d4  test    cs:byte_1800AA941, 8
0x18003e2db  jz      loc_18003E392
0x18003e2e1  xor     eax, eax
0x18003e2e3  mov     word ptr [rbp+0AC0h+var_A80], ax
0x18003e2e7  mov     word ptr [rbp+0AC0h+var_AD8], ax
0x18003e2eb  test    rcx, rcx
0x18003e2ee  jz      short loc_18003E305
0x18003e2f0  mov     rax, [rcx+70h]
0x18003e2f4  test    rax, rax
  ... truncated ...
```
