# ClientBFEHandler::PlumbPolicy(uchar,in_addr *,in6_addr *,uchar *,ulong)

- ea: `0x180032690`
- end: `0x180036247`
- name: `?PlumbPolicy@ClientBFEHandler@@QEAAKEPEAUin_addr@@PEAUin6_addr@@PEAEK@Z`
- size: `15287`
- prototype: `__int64 __fastcall(ClientBFEHandler *this, char, struct in_addr *, struct in6_addr *, unsigned __int8 *, DWORD)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001bd20`
- `0x18001f240`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180007894`
- `0x180014bec`
- `0x18002c7d8`
- `0x18002ccc4`
- `0x18002e6f4`
- `0x180031b44`
- `0x1800322b4`
- `0x180032690`
- `0x180036250`
- `0x180039fe4`
- `0x18005ad28`
- `0x18005ad64`
- `0x18005af3c`
- `0x18005af64`
- `0x180067490`
- `0x180067570`
- `0x1800677d8`
- `0x180067890`
- `0x180067b78`
- `0x18006886c`
- `0x180068a14`
- `0x180068b6c`
- `0x180068c60`
- `0x180069220`
- `0x180075a3c`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!FwpmIPsecTunnelAdd2` at `0x180035df9`
- `fwpuclnt!FwpmIPsecTunnelAdd2` at `0x180035df9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032f49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800345df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034617`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034645`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003466e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034696`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032f49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800345df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034617`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034645`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003466e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034696`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032db9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034b84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032db9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033659`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034b84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032da8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032f3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033647`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800345d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034609`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034637`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034660`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034688`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034b73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032da8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032f3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033647`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800345d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034609`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034637`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034660`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034688`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034b73`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032abf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032d11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032d49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032df6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032e31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032f7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032feb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180033058`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800330c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180033132`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003319f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003320d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003328d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003330e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180033466`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800334e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003390b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800356b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032abf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032d11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032d49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032df6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032e31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032f7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180032feb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180033058`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800330c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180033132`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003319f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003320d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003328d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003330e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180033466`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800334e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003390b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800356b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180032a78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180032a78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800333f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800333f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800346c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800346c6`
- `RPCRT4!UuidCreate` at `0x18003379e`
- `RPCRT4!UuidCreate` at `0x18003570b`
- `RPCRT4!UuidCreate` at `0x18003379e`
- `RPCRT4!UuidCreate` at `0x18003570b`
- `rtutils!RouterLogEventA` at `0x180035f52`
- `rtutils!RouterLogEventA` at `0x1800361a9`
- `rtutils!RouterLogEventA` at `0x180035f52`
- `rtutils!RouterLogEventA` at `0x1800361a9`
- `WS2_32!WSAStringToAddressA` at `0x180032ed4`
- `WS2_32!WSAStringToAddressA` at `0x180032ed4`
- `WS2_32!__imp_ntohl` at `0x180035c75`
- `WS2_32!__imp_ntohl` at `0x180035c8f`
- `WS2_32!__imp_ntohl` at `0x180035c75`
- `WS2_32!__imp_ntohl` at `0x180035c8f`

## string_xrefs

- `0x180032a6a`: `System\CurrentControlSet\Services\rasman\IKEv2`
- `0x18003382f`: `UuidCreate failed: %d`
- `0x180033a47`: `PopulateIKEPolicyFromRouterConfiguration failed: %d.`
- `0x18003605f`: `PreShareKey is not available while %s auth is configured as PSK`
- `0x180034c19`: `VPNIKE_MALLOC[configuredTrustedListOutbound] failed: %d`
- `0x180034cbb`: `Initiator cannot combine cert local auth type with non-cert remote auth types.Changing remote auth type from %d to AUTH_MACHINE_CERTIFICATES`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::PlumbPolicy(
        ClientBFEHandler *this,
        char a2,
        struct in_addr *a3,
        struct in6_addr *a4,
        unsigned __int8 *a5,
        DWORD a6)
{
  int AuthenticationType; // edi
  int RemoteAuthenticationType; // r13d
  int IsRouter; // esi
  _QWORD *v10; // rbx
  int v11; // r12d
  __int64 v12; // r9
  unsigned int v13; // r15d
  PVOID *v14; // rcx
  int v15; // ebx
  unsigned int v16; // eax
  int v17; // ecx
  unsigned int v18; // eax
  __int64 v19; // r9
  PVOID *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int128 *v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rdx
  DWORD v29; // eax
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  DWORD v32; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v34; // rbx
  DWORD v35; // eax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rdx
  unsigned int v39; // eax
  __int64 v40; // rcx
  HANDLE v41; // rax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  DWORD v48; // eax
  DWORD v49; // eax
  DWORD v50; // eax
  PVOID *v51; // rcx
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  _QWORD *v59; // rax
  __int64 v60; // rcx
  __int128 *v61; // r9
  DWORD v62; // r13d
  BYTE *v63; // rdi
  HANDLE v64; // rax
  char *v65; // rax
  char v66; // cl
  _QWORD *v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  _QWORD *v73; // rax
  __int64 v74; // rcx
  __int128 *v75; // r9
  unsigned int v76; // eax
  _QWORD *v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rcx
  _QWORD *v82; // rax
  __int64 v83; // rcx
  __int128 *v84; // r9
  __int64 *v85; // rdx
  int v86; // ebx
  PVOID *v87; // rdx
  __int64 v88; // r9
  PVOID *v89; // rcx
  __int64 v90; // r8
  unsigned int v91; // eax
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rcx
  _QWORD *v95; // rax
  __int64 v96; // rcx
  __int128 *v97; // r9
  _QWORD *v98; // rcx
  __int64 v99; // rdx
  DWORD v100; // eax
  _QWORD *v101; // rcx
  __int64 v102; // rdx
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rax
  unsigned int DH2048_AES256RegValue; // ebx
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rdx
  __int64 v110; // rcx
  _QWORD *v111; // rax
  __int64 v112; // rcx
  __int128 *v113; // r9
  DWORD v114; // eax
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rcx
  __int64 v118; // rax
  __int64 v119; // rdx
  __int64 v120; // rcx
  _QWORD *v121; // rax
  __int64 v122; // rcx
  __int128 *v123; // r9
  DWORD v124; // eax
  __int64 v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rdx
  __int64 v130; // rbx
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rdx
  __int64 v134; // rcx
  _QWORD *v135; // rax
  __int64 v136; // rcx
  __int128 *v137; // r9
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 v140; // rcx
  _QWORD *v141; // rax
  __int64 v142; // rcx
  __int128 *v143; // r9
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rdx
  __int64 v147; // rcx
  _QWORD *v148; // rax
  __int64 v149; // rcx
  __int128 *v150; // r9
  unsigned int v151; // ebx
  __int64 v152; // rax
  __int64 v153; // rax
  DWORD v154; // eax
  __int64 v155; // rdx
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rcx
  _QWORD *v159; // rax
  __int64 v160; // rcx
  __int128 *v161; // r9
  char *v162; // rsi
  void *v163; // rbx
  HANDLE v164; // rax
  struct IKEEXT_CERTIFICATE_CRITERIA0_ *v165; // rbx
  HANDLE v166; // rax
  struct IKEEXT_CERTIFICATE_CRITERIA0_ *v167; // rbx
  void *v168; // rdi
  HANDLE v169; // rax
  HANDLE v170; // rax
  HANDLE v171; // rax
  DWORD v172; // ebx
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rdx
  __int64 v177; // rcx
  _QWORD *v178; // rax
  __int64 v179; // rcx
  __int128 *v180; // r9
  __int64 v181; // rax
  __int64 v182; // rax
  __int64 v183; // rdx
  __int64 v184; // rcx
  _QWORD *v185; // rax
  __int64 v186; // rcx
  __int128 *v187; // r9
  __int64 v188; // rax
  __int64 v189; // rax
  __int64 v190; // rdx
  __int64 v191; // rcx
  _QWORD *v192; // rax
  __int64 v193; // rcx
  __int128 *v194; // r9
  void *v195; // rax
  __int64 v196; // rdi
  HANDLE v197; // rax
  _QWORD *v198; // rax
  __int64 v199; // rax
  __int64 v200; // rax
  unsigned int v201; // eax
  __int64 v202; // rax
  __int64 v203; // rax
  __int64 v204; // rdx
  __int64 v205; // rcx
  _QWORD *v206; // rax
  __int64 v207; // rcx
  __int128 *v208; // r9
  __int64 v209; // rax
  __int64 v210; // rax
  __int64 v211; // rdx
  __int64 v212; // rcx
  _QWORD *v213; // rax
  __int64 v214; // rcx
  __int128 *v215; // r9
  __int64 v216; // rdi
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // rcx
  _QWORD *v220; // rax
  __int64 v221; // rax
  __int64 v222; // rax
  __int64 v223; // rdx
  __int64 v224; // rcx
  _QWORD *v225; // rax
  __int64 v226; // rcx
  __int128 *v227; // r9
  __int64 v228; // rax
  __int64 v229; // rax
  __int64 v230; // rdx
  __int64 v231; // rcx
  _QWORD *v232; // rax
  __int64 v233; // rcx
  __int128 *v234; // r9
  int IsCertRequestPayloadDisabled; // ebx
  unsigned int v236; // edi
  __int64 v237; // r13
  __int64 v238; // rdx
  IKEEXT_AUTHENTICATION_METHOD_TYPE_ v239; // r8d
  int v240; // eax
  __int64 v241; // rcx
  __int64 v242; // rcx
  int v243; // eax
  char v244; // dl
  __int64 v245; // rax
  __int64 v246; // rax
  __int64 v247; // rdx
  __int64 v248; // rcx
  _QWORD *v249; // rax
  __int64 v250; // rcx
  __int128 *v251; // r9
  __int64 v252; // rax
  __int64 v253; // rbx
  __int64 v254; // rax
  __int64 v255; // rax
  __int64 v256; // rdx
  __int64 v257; // rcx
  _QWORD *v258; // rax
  __int64 v259; // rcx
  __int128 *v260; // r9
  int v261; // ebx
  __int64 v262; // rdx
  int v263; // ecx
  __int64 v264; // rcx
  __int64 v265; // rax
  __int64 v266; // rdx
  __int64 v267; // rcx
  _QWORD *v268; // rax
  __int64 v269; // rcx
  __int128 *v270; // r9
  DWORD v271; // eax
  __int64 v272; // rax
  __int64 v273; // rax
  __int64 v274; // rax
  __int64 v275; // rax
  __int64 v276; // rdx
  __int64 v277; // rcx
  _QWORD *v278; // rax
  __int64 v279; // rcx
  __int128 *v280; // r9
  __int64 v281; // r12
  int v282; // r13d
  int v283; // ebx
  int v284; // edi
  int v285; // esi
  int v286; // eax
  DWORD v287; // eax
  __int64 v288; // rax
  __int64 v289; // rax
  __int64 v290; // rcx
  _QWORD *v291; // rax
  __int64 v292; // rax
  __int64 v293; // rax
  __int64 v294; // rdx
  unsigned int EncryptionType; // eax
  __int64 v296; // rcx
  _QWORD *v297; // rax
  __int64 v298; // rcx
  __int128 *v299; // r9
  __int64 v300; // rcx
  DWORD BfeHandle; // eax
  __int64 v302; // rax
  __int64 v303; // rax
  DWORD v304; // eax
  __int64 v305; // rax
  __int64 v306; // rax
  __int64 v307; // rdx
  __int64 v308; // rcx
  _QWORD *v309; // rax
  __int64 v310; // rcx
  __int128 *v311; // r9
  __int64 v312; // rax
  __int64 v313; // rax
  char v314; // al
  const wchar_t *v315; // rbx
  __int64 v316; // rax
  __int64 v317; // rax
  unsigned int v318; // edi
  unsigned int v319; // esi
  const wchar_t *v320; // r8
  __int64 v321; // rcx
  _QWORD *v322; // rax
  __int64 v323; // rcx
  __int128 *v324; // r9
  __int64 v325; // rax
  __int64 v326; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  unsigned int *v331; // [rsp+30h] [rbp-D0h]
  struct IKEEXT_CERTIFICATE_CRITERIA0_ **v332; // [rsp+38h] [rbp-C8h]
  DWORD dwErrorCode; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  BYTE v335[8]; // [rsp+58h] [rbp-A8h] BYREF
  char v336; // [rsp+60h] [rbp-A0h]
  unsigned int v337; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v338; // [rsp+68h] [rbp-98h]
  BYTE v339[4]; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  BYTE v341[4]; // [rsp+78h] [rbp-88h] BYREF
  BYTE v342[4]; // [rsp+7Ch] [rbp-84h] BYREF
  IKEEXT_AUTHENTICATION_METHOD_TYPE_ v343; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v344; // [rsp+84h] [rbp-7Ch]
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v346; // [rsp+90h] [rbp-70h] BYREF
  int v347; // [rsp+94h] [rbp-6Ch]
  int v348; // [rsp+98h] [rbp-68h]
  BYTE v349[4]; // [rsp+9Ch] [rbp-64h] BYREF
  BYTE v350[4]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v351; // [rsp+A4h] [rbp-5Ch] BYREF
  BYTE v352[4]; // [rsp+A8h] [rbp-58h] BYREF
  BYTE v353[4]; // [rsp+ACh] [rbp-54h] BYREF
  BYTE v354[8]; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID lpMem; // [rsp+B8h] [rbp-48h] BYREF
  struct IKEEXT_CERTIFICATE_CRITERIA0_ *v356; // [rsp+C0h] [rbp-40h] BYREF
  BYTE v357[8]; // [rsp+C8h] [rbp-38h] BYREF
  BYTE Data[4]; // [rsp+D0h] [rbp-30h] BYREF
  DWORD v359; // [rsp+D4h] [rbp-2Ch] BYREF
  int v360; // [rsp+D8h] [rbp-28h]
  DWORD v361; // [rsp+DCh] [rbp-24h] BYREF
  BYTE v362[4]; // [rsp+E0h] [rbp-20h] BYREF
  BYTE v363[4]; // [rsp+E4h] [rbp-1Ch] BYREF
  struct IKEEXT_CERTIFICATE_CRITERIA0_ *v364; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v365; // [rsp+F0h] [rbp-10h]
  HLOCAL v366; // [rsp+F8h] [rbp-8h] BYREF
  struct in_addr *v367; // [rsp+100h] [rbp+0h]
  struct in6_addr *v368; // [rsp+108h] [rbp+8h]
  __int128 v369; // [rsp+110h] [rbp+10h] BYREF
  __int128 v370; // [rsp+120h] [rbp+20h]
  __int128 v371; // [rsp+130h] [rbp+30h]
  void *v372; // [rsp+140h] [rbp+40h] BYREF
  LPSTR plpszSubStringArray; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v374[2]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v375; // [rsp+160h] [rbp+60h] BYREF
  __int128 v376; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v377[4]; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v378; // [rsp+184h] [rbp+84h]
  HLOCAL v379; // [rsp+188h] [rbp+88h]
  int v380; // [rsp+190h] [rbp+90h]
  u_long v381; // [rsp+194h] [rbp+94h]
  __int64 v382; // [rsp+198h] [rbp+98h]
  int v383; // [rsp+1A0h] [rbp+A0h]
  u_long v384; // [rsp+1A4h] [rbp+A4h]
  __int64 v385; // [rsp+1A8h] [rbp+A8h]
  int v386; // [rsp+1B0h] [rbp+B0h]
  int v387; // [rsp+1D8h] [rbp+D8h]
  int v388; // [rsp+1DCh] [rbp+DCh]
  __int64 v389; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v390; // [rsp+1F8h] [rbp+F8h]
  __int128 v391; // [rsp+208h] [rbp+108h]
  __int64 v392; // [rsp+218h] [rbp+118h]
  int v393; // [rsp+220h] [rbp+120h]
  int v394; // [rsp+224h] [rbp+124h]
  UUID v395; // [rsp+230h] [rbp+130h] BYREF
  const wchar_t *v396; // [rsp+240h] [rbp+140h]
  int v397; // [rsp+270h] [rbp+170h]
  _BYTE *v398; // [rsp+278h] [rbp+178h]
  UUID Uuid; // [rsp+290h] [rbp+190h] BYREF
  const wchar_t *v400; // [rsp+2A0h] [rbp+1A0h]
  int v401; // [rsp+2D0h] [rbp+1D0h]
  __int128 *v402; // [rsp+2D8h] [rbp+1D8h]
  __int128 v403; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v404; // [rsp+300h] [rbp+200h] BYREF
  struct sockaddr Address[8]; // [rsp+310h] [rbp+210h] BYREF
  _DWORD v406[2]; // [rsp+390h] [rbp+290h] BYREF
  _DWORD v407[2]; // [rsp+398h] [rbp+298h]
  BYTE *v408; // [rsp+3A0h] [rbp+2A0h]
  _DWORD v409[2]; // [rsp+3A8h] [rbp+2A8h]
  _DWORD v410[2]; // [rsp+3B0h] [rbp+2B0h]
  int v411; // [rsp+3B8h] [rbp+2B8h]
  _QWORD v412[4]; // [rsp+3C0h] [rbp+2C0h]
  int v413; // [rsp+3E0h] [rbp+2E0h]
  DWORD v414; // [rsp+3E8h] [rbp+2E8h]
  __int64 v415; // [rsp+3F0h] [rbp+2F0h]
  int v416; // [rsp+3F8h] [rbp+2F8h]
  int v417; // [rsp+400h] [rbp+300h]
  int v418; // [rsp+570h] [rbp+470h] BYREF
  __int128 v419; // [rsp+574h] [rbp+474h]
  __int128 v420; // [rsp+584h] [rbp+484h]
  int v421; // [rsp+594h] [rbp+494h]
  _OWORD v422[3]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v423[30]; // [rsp+5D0h] [rbp+4D0h]
  __int16 v424; // [rsp+5EEh] [rbp+4EEh]
  int v425; // [rsp+5F0h] [rbp+4F0h] BYREF
  char v426[2044]; // [rsp+5F4h] [rbp+4F4h] BYREF
  BYTE v427; // [rsp+DF0h] [rbp+CF0h] BYREF
  char v428[255]; // [rsp+DF1h] [rbp+CF1h] BYREF

  v368 = a4;
  v367 = a3;
  v336 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a2 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, a4);
  }
  dwErrorCode = 0;
  memset_0(v406, 0, 0x1E0u);
  memset_0(&v395, 0, 0x58u);
  memset_0(&Uuid, 0, 0x58u);
  v369 = 0;
  v370 = 0;
  v371 = 0;
  hMem = 0;
  memset_0(v377, 0, 0x70u);
  v366 = 0;
  v346 = 0;
  v337 = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  *(_DWORD *)v342 = 28800;
  *(_DWORD *)v362 = 300;
  *(_DWORD *)v363 = 60;
  *(_DWORD *)v349 = 3600;
  *(_DWORD *)v350 = 250000;
  *(_DWORD *)v354 = 0x7FFFFFFF;
  AuthenticationType = ConnectionParams::GetAuthenticationType(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL));
  v344 = AuthenticationType;
  RemoteAuthenticationType = ConnectionParams::GetRemoteAuthenticationType(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL));
  v338 = RemoteAuthenticationType;
  v427 = 0;
  memset_0(v428, 0, sizeof(v428));
  v356 = 0;
  lpMem = 0;
  v343 = IKEEXT_CERTIFICATE;
  v351 = 0;
  v364 = 0;
  IsRouter = ConnectionParams::IsRouter(*(ConnectionParams **)(*((_QWORD *)this + 6) + 112LL));
  v347 = IsRouter;
  v10 = (_QWORD *)*((_QWORD *)this + 6);
  v11 = *(_DWORD *)(v10[14] + 40LL);
  v348 = v11;
  plpszSubStringArray = 0;
  v422[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v422[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v422[2] = *(_OWORD *)L"000-0000-000000000000}";
  *(_OWORD *)v423 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v423[14] = *(_OWORD *)L"000000}";
  v424 = 0;
  v404 = 0;
  v374[0] = "1.3.6.1.5.5.7.3.2";
  v374[1] = "1.3.6.1.5.5.8.2.2";
  v375 = 0;
  v376 = 0;
  *(_DWORD *)v353 = 0;
  v361 = 0;
  *(_DWORD *)v352 = 0;
  v359 = 0;
  v425 = 0;
  memset_0(v426, 0, sizeof(v426));
  v418 = 0;
  v419 = 0;
  v420 = 0;
  v421 = 0;
  v403 = 0;
  v390 = 0;
  v389 = 0;
  v391 = 0;
  v392 = 0;
  v13 = -1;
  v393 = -1;
  v394 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v389,
      L"ClientBFEHandler::PlumbPolicy",
      &dwErrorCode,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      v10);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    LOBYTE(v12) = IsRouter != 0;
    LOBYTE(phkResult) = v11 == 2;
    WPP_SF_cc(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v12, phkResult);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v336 )
  {
    if ( v367 )
      goto LABEL_13;
  }
  else if ( v368 )
  {
LABEL_13:
    v15 = 0;
    v360 = 1800;
    memset_0(&Uuid, 0, 0x58u);
    memset_0(&v395, 0, 0x58u);
    v369 = 0;
    v370 = 0;
    v371 = 0;
    memset_0(v377, 0, 0x70u);
    memset_0(v406, 0, 0x1E0u);
    v365 = *(_QWORD *)(*((_QWORD *)this + 6) + 112LL);
    v16 = *(_DWORD *)(v365 + 352);
    if ( v16 )
    {
      v17 = *(_DWORD *)(v365 + 352);
      if ( v16 < 0x78 )
        v17 = 120;
      v360 = v17;
    }
    v18 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 1u, &hKey);
    dwErrorCode = v18;
    if ( v18 )
    {
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_198;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = 85;
        goto LABEL_54;
      }
    }
    else
    {
      cbData = 4;
      v18 = RegQueryValueExA(hKey, "CustomParams", 0, 0, Data, &cbData);
      dwErrorCode = v18;
      if ( !v18 )
      {
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( *(_DWORD *)Data == 1 )
          v15 = 1;
        goto LABEL_55;
      }
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_198;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = 84;
LABEL_54:
        WPP_SF_d(v20[2], v28, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v18);
        v20 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
LABEL_55:
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 5u )
    {
      LOBYTE(v19) = v15;
      WPP_SF_c(v20[2], 86, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v19);
    }
    if ( !v15 )
      goto LABEL_198;
    memset_0(Address, 0, sizeof(Address));
    *(_DWORD *)v339 = 2;
    *(_DWORD *)v357 = 1;
    *(_DWORD *)v335 = 1;
    cbData = 0;
    if ( *(_BYTE *)(*((_QWORD *)this + 6) + 16LL) )
    {
      v29 = RegQueryValueExA(hKey, "LocalAddrV4", 0, 0, 0, &cbData);
      dwErrorCode = v29;
      if ( v29 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v31 = 87;
LABEL_71:
          WPP_SF_d(v30[2], v31, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v29);
          v29 = dwErrorCode;
          goto LABEL_72;
        }
        goto LABEL_72;
      }
    }
    else
    {
      v29 = RegQueryValueExA(hKey, "LocalAddrV6", 0, 0, 0, &cbData);
      dwErrorCode = v29;
      if ( v29 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v31 = 88;
          goto LABEL_71;
        }
LABEL_72:
        if ( v29 )
          goto LABEL_100;
      }
    }
    if ( cbData )
    {
      v32 = cbData + 1;
      ProcessHeap = GetProcessHeap();
      v34 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v32);
      if ( v34 )
      {
        if ( *(_BYTE *)(*((_QWORD *)this + 6) + 16LL) )
        {
          v35 = RegQueryValueExA(hKey, "LocalAddrV4", 0, 0, v34, &cbData);
          dwErrorCode = v35;
          if ( !v35 )
            goto LABEL_88;
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_87;
          }
          v37 = 89;
        }
        else
        {
          v35 = RegQueryValueExA(hKey, "LocalAddrV6", 0, 0, v34, &cbData);
          dwErrorCode = v35;
          if ( !v35 )
            goto LABEL_88;
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_87:
            if ( v35 )
            {
LABEL_99:
              v41 = GetProcessHeap();
              HeapFree(v41, 0, v34);
              goto LABEL_100;
            }
LABEL_88:
            if ( cbData )
            {
              if ( v34[cbData - 1] )
                v34[cbData] = 0;
              v38 = *((_QWORD *)this + 6);
              cbData = *(_BYTE *)(v38 + 16) != 0 ? 16 : 28;
              v39 = WSAStringToAddressA((LPSTR)v34, *(_BYTE *)(v38 + 16) != 0 ? 2 : 23, 0, Address, (LPINT)&cbData);
              dwErrorCode = v39;
              if ( v39 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    91,
                    &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                    v39);
                }
              }
              else
              {
                v40 = *((_QWORD *)this + 6);
                if ( *(_BYTE *)(v40 + 16) )
                  *(_DWORD *)(v40 + 48) = *(_DWORD *)&Address[0].sa_data[2];
                else
                  *(struct sockaddr *)(v40 + 52) = *(struct sockaddr *)&Address[0].sa_data[6];
              }
            }
            goto LABEL_99;
          }
          v37 = 90;
        }
        WPP_SF_d(v36[2], v37, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v35);
        v35 = dwErrorCode;
        goto LABEL_87;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
      }
    }
LABEL_100:
    cbData = 4;
    v42 = RegQueryValueExA(hKey, "IKEMaxLifeTimeSec", 0, 0, v342, &cbData);
    dwErrorCode = v42;
    if ( v42
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v42);
    }
    cbData = 4;
    v43 = RegQueryValueExA(hKey, "IdleTimeoutInSec", 0, 0, v362, &cbData);
    dwErrorCode = v43;
    if ( v43
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v43);
    }
    cbData = 4;
    v44 = RegQueryValueExA(hKey, "IdleTimeoutSecFailOver", 0, 0, v363, &cbData);
    dwErrorCode = v44;
    if ( v44
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v44);
    }
    cbData = 4;
    v45 = RegQueryValueExA(hKey, "IPSecMaxLifeTimeSec", 0, 0, v349, &cbData);
    dwErrorCode = v45;
    if ( v45
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v45);
    }
    cbData = 4;
    v46 = RegQueryValueExA(hKey, "IPSesMaxLifeTimeKB", 0, 0, v350, &cbData);
    dwErrorCode = v46;
    if ( v46
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v46);
    }
    cbData = 4;
    v47 = RegQueryValueExA(hKey, "IPSecMaxLifeTimePkts", 0, 0, v354, &cbData);
    dwErrorCode = v47;
    if ( v47
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v47);
    }
    cbData = 4;
    v48 = RegQueryValueExA(hKey, "IkeDHGroup", 0, 0, v339, &cbData);
    dwErrorCode = v48;
    if ( !v48 )
      goto LABEL_136;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v48);
      v48 = dwErrorCode;
    }
    if ( !v48 )
    {
LABEL_136:
      if ( cbData )
        v337 = 1;
    }
    cbData = 4;
    v49 = RegQueryValueExA(hKey, "IkeCipherAlgo", 0, 0, v357, &cbData);
    dwErrorCode = v49;
    if ( !v49 )
      goto LABEL_144;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v49);
      v49 = dwErrorCode;
    }
    if ( !v49 )
    {
LABEL_144:
      if ( cbData )
        v337 = 1;
    }
    cbData = 4;
    v50 = RegQueryValueExA(hKey, "IkeIntegrityAlgo", 0, 0, v335, &cbData);
    dwErrorCode = v50;
    if ( v50 )
    {
      v51 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_152:
        if ( v50 || !cbData )
        {
          v52 = v337;
        }
        else
        {
          v52 = 1;
          v337 = 1;
        }
        if ( v51 != &WPP_GLOBAL_Control && (*((_BYTE *)v51 + 28) & 1) != 0 && *((_BYTE *)v51 + 25) >= 5u )
        {
          WPP_SF_d(v51[2], 102, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v52);
          v52 = v337;
        }
        if ( v52 == 1 )
        {
          hMem = LocalAlloc(0x40u, 0x1Cu);
          *(_DWORD *)hMem = *(_DWORD *)v357;
          *((_DWORD *)hMem + 3) = *(_DWORD *)v335;
          *((_DWORD *)hMem + 4) = *(_DWORD *)v342;
          *((_DWORD *)hMem + 5) = *(_DWORD *)v339;
          *((_DWORD *)hMem + 6) = 0;
        }
        *(_DWORD *)v341 = 0;
        cbData = 4;
        v53 = RegQueryValueExA(hKey, "IkeAuthTypePsk", 0, 0, v341, &cbData);
        dwErrorCode = v53;
        if ( v53
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v53);
        }
        if ( *(_DWORD *)v341 )
        {
          cbData = 256;
          v54 = RegQueryValueExA(hKey, "IkeAuthPsk", 0, 0, &v427, &cbData);
          dwErrorCode = v54;
          if ( !v54 )
          {
            if ( (byte_1800AA941 & 8) == 0 )
              goto LABEL_189;
            LOWORD(v425) = 0;
            LOWORD(v418) = 0;
            v55 = *((_QWORD *)this + 6);
            if ( v55 && (v56 = *(_QWORD *)(v55 + 112)) != 0 && *(_QWORD *)(v56 + 16) )
              v57 = *(unsigned int *)(v56 + 16);
            else
              v57 = 0xFFFFFFFFLL;
            ConvertPortNoToString(&v418, v57);
            FormatRRASErrorString(&v425, L"PSKAuthType: %04x, PSK: %S", *(unsigned int *)v341, &v427);
            if ( (byte_1800AA941 & 8) == 0 )
              goto LABEL_189;
            v58 = *((_QWORD *)this + 6);
            v59 = (_QWORD *)(v58 + 112);
            if ( v58 )
            {
              if ( *v59 )
                v60 = *v59 + 2686LL;
              else
                v60 = 0;
              if ( *v59 )
              {
                v61 = (__int128 *)(*v59 + 2120LL);
LABEL_188:
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasVpnIkeParamTraceInfo,
                  (unsigned int)&v425,
                  (_DWORD)v61,
                  v60,
                  (__int64)&v418);
LABEL_189:
                if ( (v341[0] & 1) != 0 )
                  AuthenticationType = 3;
                v344 = AuthenticationType;
                if ( (v341[0] & 2) != 0 )
                  RemoteAuthenticationType = 3;
                v338 = RemoteAuthenticationType;
                v62 = cbData;
                v63 = &v427;
LABEL_199:
                *(_QWORD *)v357 = v63;
                v64 = GetProcessHeap();
                v65 = (char *)HeapAlloc(v64, 8u, 0x40u);
                *(_QWORD *)v335 = v65;
                if ( !v65 )
                {
                  dwErrorCode = 8;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      107,
                      &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                      8);
                  }
                  if ( (byte_1800AA941 & 4) == 0 )
                    goto LABEL_493;
                  LOWORD(v425) = 0;
                  LOWORD(v418) = 0;
                  v325 = *((_QWORD *)this + 6);
                  if ( v325 )
                  {
                    v326 = *(_QWORD *)(v325 + 112);
                    if ( v326 )
                    {
                      if ( *(_QWORD *)(v326 + 16) )
                        v13 = *(_DWORD *)(v326 + 16);
                    }
                  }
                  ConvertPortNoToString(&v418, v13);
                  FormatRRASErrorString(&v425, L"Failed to allocate memory: %d", dwErrorCode);
                  goto LABEL_238;
                }
                v66 = v336;
                v65[8] = v336;
                if ( v66 )
                {
                  *((struct in_addr *)v65 + 3) = *v367;
                  v67 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
                  {
                    goto LABEL_210;
                  }
                  v68 = 105;
                }
                else
                {
                  *(struct in6_addr *)(v65 + 12) = *v368;
                  v67 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
                  {
                    goto LABEL_210;
                  }
                  v68 = 106;
                }
                WPP_SF_(v67[2], v68, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
LABEL_210:
                if ( (byte_1800AA941 & 8) == 0
                  || ((LOWORD(v418) = 0, (v69 = *((_QWORD *)this + 6)) == 0)
                   || (v70 = *(_QWORD *)(v69 + 112)) == 0
                   || !*(_QWORD *)(v70 + 16)
                    ? (v71 = 0xFFFFFFFFLL)
                    : (v71 = *(unsigned int *)(v70 + 16)),
                      ConvertPortNoToString(&v418, v71),
                      (byte_1800AA941 & 8) == 0) )
                {
LABEL_226:
                  v76 = UuidCreate(&Uuid);
                  dwErrorCode = v76;
                  if ( v76 )
                  {
                    v77 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_232;
                    }
                    v78 = 108;
LABEL_231:
                    WPP_SF_d(v77[2], v78, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v76);
LABEL_232:
                    if ( (byte_1800AA941 & 4) == 0 )
                      goto LABEL_493;
                    LOWORD(v425) = 0;
                    LOWORD(v418) = 0;
                    v79 = *((_QWORD *)this + 6);
                    if ( v79 )
                    {
                      v80 = *(_QWORD *)(v79 + 112);
                      if ( v80 )
                      {
                        if ( *(_QWORD *)(v80 + 16) )
                          v13 = *(_DWORD *)(v80 + 16);
                      }
                    }
                    ConvertPortNoToString(&v418, v13);
                    FormatRRASErrorString(&v425, L"UuidCreate failed: %d", dwErrorCode);
LABEL_238:
                    if ( (byte_1800AA941 & 4) != 0 )
                    {
                      v81 = *((_QWORD *)this + 6);
                      v82 = (_QWORD *)(v81 + 112);
                      if ( v81 )
                      {
                        if ( *v82 )
                          v83 = *v82 + 2686LL;
                        else
                          v83 = 0;
                        if ( *v82 )
                        {
                          v84 = (__int128 *)(*v82 + 2120LL);
LABEL_247:
                          v85 = RasVpnIkeParamTraceError;
LABEL_248:
                          McTemplateU0zjzz_EventWriteTransfer(
                            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                            (_DWORD)v85,
                            (unsigned int)&v425,
                            (_DWORD)v84,
                            v83,
                            (__int64)&v418);
                          goto LABEL_493;
                        }
                      }
                      else
                      {
                        v83 = 0;
                      }
                      v84 = &v403;
                      goto LABEL_247;
                    }
LABEL_493:
                    v162 = *(char **)v335;
                    goto LABEL_494;
                  }
                  v86 = 0;
                  v400 = L"IKEv2 Client Main mode IPsec tunnel policy";
                  v401 = 10;
                  v402 = &v369;
                  v359 = 4;
                  dwErrorCode = RegQueryValueExA(hKey, "UseRSACertForEcpDHGroups", 0, 0, v352, &v359);
                  if ( dwErrorCode )
                  {
                    v89 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  else
                  {
                    v89 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        109,
                        &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                        *(unsigned int *)v352);
                      v89 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( *(_DWORD *)v352 == 1 )
                      v86 = 1;
                  }
                  v90 = 7;
                  if ( v347 )
                  {
                    if ( v89 != &WPP_GLOBAL_Control && (*((_BYTE *)v89 + 28) & 1) != 0 && *((_BYTE *)v89 + 25) >= 5u )
                      WPP_SF_(v89[2], 110, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                    v91 = ClientBFEHandler::PopulateIKEPolicyFromRouterConfiguration(
                            this,
                            (struct _ROUTER_IKEv2_IF_CUSTOM_CONFIG2 *)(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL)
                                                                     + 2040LL),
                            v86,
                            &v343,
                            (unsigned int *)v342,
                            (unsigned int *)v349,
                            (unsigned int *)v350,
                            &v356);
                    dwErrorCode = v91;
                    if ( v91 )
                    {
                      if ( (byte_1800AA941 & 4) == 0 )
                        goto LABEL_280;
                      LOWORD(v425) = 0;
                      LOWORD(v418) = 0;
                      v92 = *((_QWORD *)this + 6);
                      if ( v92 )
                      {
                        v93 = *(_QWORD *)(v92 + 112);
                        if ( v93 )
                        {
                          if ( *(_QWORD *)(v93 + 16) )
                            v13 = *(_DWORD *)(v93 + 16);
                        }
                      }
                      ConvertPortNoToString(&v418, v13);
                      FormatRRASErrorString(&v425, L"PopulateIKEPolicyFromRouterConfiguration failed: %d.", dwErrorCode);
                      if ( (byte_1800AA941 & 4) == 0 )
                      {
LABEL_279:
                        v91 = dwErrorCode;
LABEL_280:
                        if ( !v91 )
                          goto LABEL_493;
                        v98 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                        {
                          goto LABEL_493;
                        }
                        v99 = 111;
                        goto LABEL_285;
                      }
                      v94 = *((_QWORD *)this + 6);
                      v95 = (_QWORD *)(v94 + 112);
                      if ( v94 )
                      {
                        if ( *v95 )
                          v96 = *v95 + 2686LL;
                        else
                          v96 = 0;
                        if ( *v95 )
                        {
                          v97 = (__int128 *)(*v95 + 2120LL);
LABEL_278:
                          McTemplateU0zjzz_EventWriteTransfer(
                            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                            (unsigned int)RasVpnIkeParamTraceError,
                            (unsigned int)&v425,
                            (_DWORD)v97,
                            v96,
                            (__int64)&v418);
                          goto LABEL_279;
                        }
                      }
                      else
                      {
                        v96 = 0;
                      }
                      v97 = &v403;
                      goto LABEL_278;
                    }
                    if ( v338 == 2 )
                    {
                      *(_DWORD *)v339 = 0;
                      v100 = BFEHandler::BuildTrustedRootCertificateList(1, &v351, (unsigned int *)v339, &v364, 0);
                      dwErrorCode = v100;
                      if ( v100 )
                      {
                        v101 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                        {
                          goto LABEL_293;
                        }
                        v102 = 112;
LABEL_292:
                        WPP_SF_d(v101[2], v102, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v100);
LABEL_293:
                        if ( (byte_1800AA941 & 4) == 0 )
                          goto LABEL_493;
                        LOWORD(v425) = 0;
                        LOWORD(v418) = 0;
                        v103 = *((_QWORD *)this + 6);
                        if ( v103 )
                        {
                          v104 = *(_QWORD *)(v103 + 112);
                          if ( v104 )
                          {
                            if ( *(_QWORD *)(v104 + 16) )
                              v13 = *(_DWORD *)(v104 + 16);
                          }
                        }
                        ConvertPortNoToString(&v418, v13);
                        FormatRRASErrorString(&v425, L"BuildTrustedRootCertificateList failed: %d", dwErrorCode);
                        goto LABEL_238;
                      }
                    }
                  }
                  else
                  {
                    if ( v348 == 2 )
                      goto LABEL_315;
                    v87 = &WPP_GLOBAL_Control;
                    if ( v89 != &WPP_GLOBAL_Control && (*((_BYTE *)v89 + 28) & 1) != 0 && *((_BYTE *)v89 + 25) >= 5u )
                    {
                      WPP_SF_(v89[2], 113, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                      v89 = (PVOID *)WPP_GLOBAL_Control;
                      v87 = &WPP_GLOBAL_Control;
                      v90 = 7;
                    }
                    if ( !v86 )
                    {
                      v105 = *(_QWORD *)(v365 + 4544);
                      if ( v105 )
                      {
                        if ( *(_DWORD *)(v105 + 8) == 4 )
                        {
                          v343 = IKEEXT_CERTIFICATE_ECDSA_P256;
                        }
                        else if ( *(_DWORD *)(v105 + 8) == 5 )
                        {
                          v343 = IKEEXT_CERTIFICATE_ECDSA_P384;
                        }
                      }
                    }
                    if ( v89 == &WPP_GLOBAL_Control || (*((_BYTE *)v89 + 28) & 1) == 0 || *((_BYTE *)v89 + 25) < 5u )
                    {
LABEL_315:
                      if ( v337 )
                        goto LABEL_439;
                      DH2048_AES256RegValue = ReadDH2048_AES256RegValue(
                                                v89,
                                                v87,
                                                v90,
                                                v88,
                                                phkResulta,
                                                lpcbData,
                                                v331,
                                                v332);
                      if ( DH2048_AES256RegValue )
                      {
                        if ( (byte_1800AA941 & 8) == 0
                          || ((LOWORD(v425) = 0, LOWORD(v418) = 0, (v107 = *((_QWORD *)this + 6)) == 0)
                           || (v108 = *(_QWORD *)(v107 + 112)) == 0
                           || !*(_QWORD *)(v108 + 16)
                            ? (v109 = 0xFFFFFFFFLL)
                            : (v109 = *(unsigned int *)(v108 + 16)),
                              ConvertPortNoToString(&v418, v109),
                              FormatRRASErrorString(&v425, L"NegotiateDH2048_AES256= %d", DH2048_AES256RegValue),
                              (byte_1800AA941 & 8) == 0) )
                        {
LABEL_333:
                          v114 = BuildDH2048_AES256IKEEncryption(&hMem, &v337, *(unsigned int *)v342);
                          dwErrorCode = v114;
                          if ( v114 )
                          {
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                115,
                                &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                v114);
                            }
                            if ( (byte_1800AA941 & 4) == 0 )
                              goto LABEL_493;
                            LOWORD(v425) = 0;
                            LOWORD(v418) = 0;
                            v115 = *((_QWORD *)this + 6);
                            if ( v115 )
                            {
                              v116 = *(_QWORD *)(v115 + 112);
                              if ( v116 )
                              {
                                if ( *(_QWORD *)(v116 + 16) )
                                  v13 = *(_DWORD *)(v116 + 16);
                              }
                            }
                            ConvertPortNoToString(&v418, v13);
                            FormatRRASErrorString(&v425, L"BuildDH2048_AES256IKEEncryption %d", dwErrorCode);
                            goto LABEL_238;
                          }
                          goto LABEL_438;
                        }
                        v110 = *((_QWORD *)this + 6);
                        v111 = (_QWORD *)(v110 + 112);
                        if ( v110 )
                        {
                          if ( *v111 )
                            v112 = *v111 + 2686LL;
                          else
                            v112 = 0;
                          if ( *v111 )
                          {
                            v113 = (__int128 *)(*v111 + 2120LL);
LABEL_332:
                            McTemplateU0zjzz_EventWriteTransfer(
                              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                              (unsigned int)RasVpnIkeParamTraceInfo,
                              (unsigned int)&v425,
                              (_DWORD)v113,
                              v112,
                              (__int64)&v418);
                            goto LABEL_333;
                          }
                        }
                        else
                        {
                          v112 = 0;
                        }
                        v113 = &v403;
                        goto LABEL_332;
                      }
                      if ( v347 )
                      {
                        v117 = *((_QWORD *)this + 6);
                        if ( *(_QWORD *)(*(_QWORD *)(v117 + 112) + 2064LL) )
                        {
                          if ( (byte_1800AA941 & 8) == 0 )
                            goto LABEL_362;
                          LOWORD(v418) = 0;
                          if ( v117 && (v118 = *(_QWORD *)(v117 + 112)) != 0 && *(_QWORD *)(v118 + 16) )
                            v119 = *(unsigned int *)(v118 + 16);
                          else
                            v119 = 0xFFFFFFFFLL;
                          ConvertPortNoToString(&v418, v119);
                          if ( (byte_1800AA941 & 8) == 0 )
                            goto LABEL_362;
                          v120 = *((_QWORD *)this + 6);
                          v121 = (_QWORD *)(v120 + 112);
                          if ( v120 )
                          {
                            if ( *v121 )
                              v122 = *v121 + 2686LL;
                            else
                              v122 = 0;
                            if ( *v121 )
                            {
                              v123 = (__int128 *)(*v121 + 2120LL);
LABEL_361:
                              McTemplateU0zjzz_EventWriteTransfer(
                                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                (unsigned int)RasVpnIkeParamTraceInfo,
                                (unsigned int)L"Building custom IKEv2 proposals",
                                (_DWORD)v123,
                                v122,
                                (__int64)&v418);
LABEL_362:
                              v124 = BuildIkev2CustomProposals(
                                       *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL) + 2064LL),
                                       *(unsigned int *)v342,
                                       &v337,
                                       &hMem);
                              dwErrorCode = v124;
                              if ( v124 )
                              {
                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                {
                                  WPP_SF_d(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    116,
                                    &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                    v124);
                                }
                                if ( (byte_1800AA941 & 4) == 0 )
                                  goto LABEL_493;
                                LOWORD(v425) = 0;
                                LOWORD(v418) = 0;
                                v125 = *((_QWORD *)this + 6);
                                if ( v125 )
                                {
                                  v126 = *(_QWORD *)(v125 + 112);
                                  if ( v126 )
                                  {
                                    if ( *(_QWORD *)(v126 + 16) )
                                      v13 = *(_DWORD *)(v126 + 16);
                                  }
                                }
                                ConvertPortNoToString(&v418, v13);
                                FormatRRASErrorString(&v425, L"BuildIkev2CustomProposals failed: %d", dwErrorCode);
                                goto LABEL_238;
                              }
                              if ( (byte_1800AA941 & 8) == 0 )
                                goto LABEL_438;
                              LOWORD(v425) = 0;
                              LOWORD(v418) = 0;
                              v127 = *((_QWORD *)this + 6);
                              if ( v127 && (v128 = *(_QWORD *)(v127 + 112)) != 0 && *(_QWORD *)(v128 + 16) )
                                v129 = *(unsigned int *)(v128 + 16);
                              else
                                v129 = 0xFFFFFFFFLL;
                              ConvertPortNoToString(&v418, v129);
                              FormatRRASErrorString(&v425, L"Custom IKEv2 proposal count: %d", v337);
                              goto LABEL_428;
                            }
                          }
                          else
                          {
                            v122 = 0;
                          }
                          v123 = &v403;
                          goto LABEL_361;
                        }
LABEL_464:
                        if ( (unsigned int)ConnectionParams::GetEncryptionType(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL)) == 3 )
                        {
                          v154 = BuildStrongIKEEncryption(&hMem, &v337, *(unsigned int *)v342);
                          dwErrorCode = v154;
                          if ( v154 )
                          {
                            v89 = (PVOID *)WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              v155 = 118;
LABEL_475:
                              WPP_SF_d(v89[2], v155, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v154);
                              v154 = dwErrorCode;
                              goto LABEL_476;
                            }
                            goto LABEL_477;
                          }
                        }
                        else
                        {
                          v154 = BuildRequireIKEEncryption(&hMem, &v337, *(unsigned int *)v342);
                          dwErrorCode = v154;
                          if ( v154 )
                          {
                            v89 = (PVOID *)WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              v155 = 119;
                              goto LABEL_475;
                            }
LABEL_477:
                            if ( !v154 )
                            {
LABEL_439:
                              v151 = v344;
                              if ( v344 != 3 && v338 != 3 || v63 && v62 )
                              {
                                *(_DWORD *)v341 = 0;
                                if ( v89 != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)v89 + 28) & 1) != 0
                                  && *((_BYTE *)v89 + 25) >= 5u )
                                {
                                  WPP_SF_d(v89[2], 121, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v344);
                                  v89 = (PVOID *)WPP_GLOBAL_Control;
                                }
                                if ( v151 != 1 )
                                {
                                  if ( v151 != 2 )
                                  {
                                    if ( v151 != 3 )
                                    {
                                      if ( v89 != &WPP_GLOBAL_Control
                                        && (*((_BYTE *)v89 + 28) & 1) != 0
                                        && *((_BYTE *)v89 + 25) >= 5u )
                                      {
                                        WPP_SF_(v89[2], 129, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                        v89 = (PVOID *)WPP_GLOBAL_Control;
                                      }
                                      dwErrorCode = 87;
                                      if ( v89 != &WPP_GLOBAL_Control
                                        && (*((_BYTE *)v89 + 28) & 1) != 0
                                        && *((_BYTE *)v89 + 25) >= 2u )
                                      {
                                        WPP_SF_d(v89[2], 130, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 87);
                                      }
                                      if ( (byte_1800AA941 & 4) == 0 )
                                        goto LABEL_493;
                                      LOWORD(v425) = 0;
                                      LOWORD(v418) = 0;
                                      v152 = *((_QWORD *)this + 6);
                                      if ( v152 )
                                      {
                                        v153 = *(_QWORD *)(v152 + 112);
                                        if ( v153 )
                                        {
                                          if ( *(_QWORD *)(v153 + 16) )
                                            v13 = *(_DWORD *)(v153 + 16);
                                        }
                                      }
                                      ConvertPortNoToString(&v418, v13);
                                      FormatRRASErrorString(&v425, L"Invalid local Auth Type %d", v151);
                                      goto LABEL_238;
                                    }
                                    if ( v89 != &WPP_GLOBAL_Control
                                      && (*((_BYTE *)v89 + 28) & 1) != 0
                                      && *((_BYTE *)v89 + 25) >= 5u )
                                    {
                                      WPP_SF_(v89[2], 128, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                      v89 = (PVOID *)WPP_GLOBAL_Control;
                                    }
                                    if ( (byte_1800AA941 & 8) == 0 )
                                      goto LABEL_539;
                                    LOWORD(v418) = 0;
                                    v174 = *((_QWORD *)this + 6);
                                    if ( v174 && (v175 = *(_QWORD *)(v174 + 112)) != 0 && *(_QWORD *)(v175 + 16) )
                                      v176 = *(unsigned int *)(v175 + 16);
                                    else
                                      v176 = 0xFFFFFFFFLL;
                                    ConvertPortNoToString(&v418, v176);
                                    if ( (byte_1800AA941 & 8) == 0 )
                                    {
LABEL_538:
                                      v89 = (PVOID *)WPP_GLOBAL_Control;
LABEL_539:
                                      v406[0] = 0;
                                      v407[0] = v62;
                                      v408 = v63;
                                      v409[0] = 1;
                                      *(_DWORD *)v341 = *((_DWORD *)VpnIkeProtocolEngine + 24) >> 31;
                                      v151 = v344;
LABEL_652:
                                      v201 = v338;
                                      goto LABEL_653;
                                    }
                                    v177 = *((_QWORD *)this + 6);
                                    v178 = (_QWORD *)(v177 + 112);
                                    if ( v177 )
                                    {
                                      if ( *v178 )
                                        v179 = *v178 + 2686LL;
                                      else
                                        v179 = 0;
                                      if ( *v178 )
                                      {
                                        v180 = (__int128 *)(*v178 + 2120LL);
LABEL_537:
                                        McTemplateU0zjzz_EventWriteTransfer(
                                          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                          (unsigned int)RasVpnIkeParamTraceInfo,
                                          (unsigned int)L"Adding PSK as LocalAuth method",
                                          (_DWORD)v180,
                                          v179,
                                          (__int64)&v418);
                                        goto LABEL_538;
                                      }
                                    }
                                    else
                                    {
                                      v179 = 0;
                                    }
                                    v180 = &v403;
                                    goto LABEL_537;
                                  }
                                  if ( v89 != &WPP_GLOBAL_Control
                                    && (*((_BYTE *)v89 + 28) & 1) != 0
                                    && *((_BYTE *)v89 + 25) >= 5u )
                                  {
                                    WPP_SF_(v89[2], 123, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                    v89 = (PVOID *)WPP_GLOBAL_Control;
                                  }
                                  if ( (byte_1800AA941 & 8) == 0 )
                                  {
LABEL_561:
                                    v406[0] = v343;
                                    v407[0] = 3;
                                    if ( v347 )
                                    {
                                      if ( v356 )
                                      {
                                        if ( v89 != &WPP_GLOBAL_Control
                                          && (*((_BYTE *)v89 + 28) & 1) != 0
                                          && *((_BYTE *)v89 + 25) >= 5u )
                                        {
                                          WPP_SF_(v89[2], 124, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                          v89 = (PVOID *)WPP_GLOBAL_Control;
                                        }
                                        if ( (byte_1800AA941 & 8) == 0 )
                                          goto LABEL_584;
                                        LOWORD(v418) = 0;
                                        v188 = *((_QWORD *)this + 6);
                                        if ( v188 && (v189 = *(_QWORD *)(v188 + 112)) != 0 && *(_QWORD *)(v189 + 16) )
                                          v190 = *(unsigned int *)(v189 + 16);
                                        else
                                          v190 = 0xFFFFFFFFLL;
                                        ConvertPortNoToString(&v418, v190);
                                        if ( (byte_1800AA941 & 8) == 0 )
                                        {
LABEL_583:
                                          v89 = (PVOID *)WPP_GLOBAL_Control;
LABEL_584:
                                          v411 = 1;
                                          v195 = v356;
LABEL_610:
                                          v410[0] = 2;
                                          goto LABEL_611;
                                        }
                                        v191 = *((_QWORD *)this + 6);
                                        v192 = (_QWORD *)(v191 + 112);
                                        if ( v191 )
                                        {
                                          if ( *v192 )
                                            v193 = *v192 + 2686LL;
                                          else
                                            v193 = 0;
                                          if ( *v192 )
                                          {
                                            v194 = (__int128 *)(*v192 + 2120LL);
LABEL_582:
                                            McTemplateU0zjzz_EventWriteTransfer(
                                              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                              (unsigned int)RasVpnIkeParamTraceInfo,
                                              (unsigned int)L"Adding ClientCert for local Auth",
                                              (_DWORD)v194,
                                              v193,
                                              (__int64)&v418);
                                            goto LABEL_583;
                                          }
                                        }
                                        else
                                        {
                                          v193 = 0;
                                        }
                                        v194 = &v403;
                                        goto LABEL_582;
                                      }
                                    }
                                    else if ( v348 != 2 )
                                    {
                                      v196 = v365;
                                      if ( *(_DWORD *)(v365 + 4528) || *(_DWORD *)(v365 + 4476) )
                                      {
                                        if ( v89 != &WPP_GLOBAL_Control
                                          && (*((_BYTE *)v89 + 28) & 1) != 0
                                          && *((_BYTE *)v89 + 25) >= 5u )
                                        {
                                          WPP_SF_(v89[2], 125, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                        }
                                        *(_DWORD *)v339 = 0;
                                        v100 = BFEHandler::BuildVPNTrustedRootCertificateList(
                                                 this,
                                                 &v351,
                                                 (unsigned int *)v339,
                                                 0,
                                                 (struct IKEEXT_CERTIFICATE_CRITERIA0_ **)&lpMem);
                                        dwErrorCode = v100;
                                        if ( v100 )
                                        {
                                          v101 = WPP_GLOBAL_Control;
                                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                          {
                                            goto LABEL_293;
                                          }
                                          v102 = 126;
                                          goto LABEL_292;
                                        }
                                        v410[0] = *(_DWORD *)(v196 + 4528) == 0 ? 2 : 0;
                                        v411 = *(_DWORD *)v339;
                                        v195 = lpMem;
                                        v89 = (PVOID *)WPP_GLOBAL_Control;
LABEL_611:
                                        v412[0] = v195;
                                        v201 = v338;
                                        if ( v338 == 2 )
                                        {
LABEL_653:
                                          LODWORD(v216) = 0;
                                          if ( v89 != &WPP_GLOBAL_Control
                                            && (*((_BYTE *)v89 + 28) & 1) != 0
                                            && *((_BYTE *)v89 + 25) >= 5u )
                                          {
                                            WPP_SF_d(
                                              v89[2],
                                              131,
                                              &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                              v201);
                                            v89 = (PVOID *)WPP_GLOBAL_Control;
                                          }
                                          if ( v338 != 2 )
                                          {
                                            if ( v338 != 3 )
                                            {
                                              if ( v89 != &WPP_GLOBAL_Control
                                                && (*((_BYTE *)v89 + 28) & 1) != 0
                                                && *((_BYTE *)v89 + 25) >= 5u )
                                              {
                                                WPP_SF_(v89[2], 136, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                                v89 = (PVOID *)WPP_GLOBAL_Control;
                                              }
                                              dwErrorCode = 87;
                                              if ( v89 != &WPP_GLOBAL_Control
                                                && (*((_BYTE *)v89 + 28) & 1) != 0
                                                && *((_BYTE *)v89 + 25) >= 2u )
                                              {
                                                WPP_SF_d(
                                                  v89[2],
                                                  137,
                                                  &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                                  87);
                                              }
                                              if ( (byte_1800AA941 & 8) == 0 )
                                                goto LABEL_493;
                                              LOWORD(v425) = 0;
                                              LOWORD(v418) = 0;
                                              v217 = *((_QWORD *)this + 6);
                                              if ( v217 )
                                              {
                                                v218 = *(_QWORD *)(v217 + 112);
                                                if ( v218 )
                                                {
                                                  if ( *(_QWORD *)(v218 + 16) )
                                                    v13 = *(_DWORD *)(v218 + 16);
                                                }
                                              }
                                              ConvertPortNoToString(&v418, v13);
                                              FormatRRASErrorString(&v425, L"Invalid remote Auth Type %d", v151);
                                              if ( (byte_1800AA941 & 8) == 0 )
                                                goto LABEL_493;
                                              v219 = *((_QWORD *)this + 6);
                                              v220 = (_QWORD *)(v219 + 112);
                                              if ( v219 )
                                              {
                                                if ( *v220 )
                                                  v83 = *v220 + 2686LL;
                                                else
                                                  v83 = 0;
                                                if ( *v220 )
                                                {
                                                  v84 = (__int128 *)(*v220 + 2120LL);
LABEL_681:
                                                  v85 = RasVpnIkeParamTraceInfo;
                                                  goto LABEL_248;
                                                }
                                              }
                                              else
                                              {
                                                v83 = 0;
                                              }
                                              v84 = &v403;
                                              goto LABEL_681;
                                            }
                                            if ( v89 != &WPP_GLOBAL_Control
                                              && (*((_BYTE *)v89 + 28) & 1) != 0
                                              && *((_BYTE *)v89 + 25) >= 5u )
                                            {
                                              WPP_SF_(v89[2], 132, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                              v89 = (PVOID *)WPP_GLOBAL_Control;
                                            }
                                            if ( (byte_1800AA941 & 8) == 0 )
                                              goto LABEL_703;
                                            LOWORD(v418) = 0;
                                            v221 = *((_QWORD *)this + 6);
                                            if ( v221 && (v222 = *(_QWORD *)(v221 + 112)) != 0 && *(_QWORD *)(v222 + 16) )
                                              v223 = *(unsigned int *)(v222 + 16);
                                            else
                                              v223 = 0xFFFFFFFFLL;
                                            ConvertPortNoToString(&v418, v223);
                                            if ( (byte_1800AA941 & 8) == 0 )
                                            {
LABEL_702:
                                              v89 = (PVOID *)WPP_GLOBAL_Control;
LABEL_703:
                                              if ( v151 == 3 )
                                              {
                                                v409[0] = 0;
                                                if ( v89 != &WPP_GLOBAL_Control
                                                  && (*((_BYTE *)v89 + 28) & 1) != 0
                                                  && *((_BYTE *)v89 + 25) >= 5u )
                                                {
                                                  WPP_SF_(v89[2], 133, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                                }
                                              }
                                              else
                                              {
                                                LODWORD(v216) = 1;
                                                v413 = 0;
                                                v414 = v62;
                                                v415 = *(_QWORD *)v357;
                                                v416 = 2;
                                              }
                                              *((_DWORD *)this + 16) = 0;
LABEL_788:
                                              v261 = 0;
                                              DWORD1(v369) = v216 + 1;
                                              *((_QWORD *)&v369 + 1) = v406;
                                              DWORD1(v370) = v337;
                                              *((_QWORD *)&v370 + 1) = hMem;
                                              DWORD1(v371) = 100;
                                              DWORD2(v371) = v360;
                                              v262 = *((_QWORD *)this + 6);
                                              v263 = v371;
                                              if ( (*(_DWORD *)(*(_QWORD *)(v262 + 112) + 4432LL) & 0x100000) != 0 )
                                              {
                                                v263 = v371 | 0x10;
                                                LODWORD(v371) = v371 | 0x10;
                                              }
                                              if ( *(_DWORD *)(*(_QWORD *)(v262 + 112) + 4252LL) == 1 )
                                                LODWORD(v371) = v263 | 0x140;
                                              if ( (*(_BYTE *)(*(_QWORD *)(v262 + 112) + 3200LL) & 2) != 0 )
                                              {
                                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                                                {
                                                  WPP_SF_(
                                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                    138,
                                                    &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                                }
                                                v261 = 1;
                                              }
                                              v361 = 4;
                                              dwErrorCode = RegQueryValueExA(
                                                              hKey,
                                                              "DisableClientFragmentation",
                                                              0,
                                                              0,
                                                              v353,
                                                              &v361);
                                              if ( dwErrorCode )
                                                goto LABEL_804;
                                              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                                              {
                                                WPP_SF_d(
                                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                  139,
                                                  &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                                  *(unsigned int *)v353);
                                              }
                                              if ( *(_DWORD *)v353 != 1 )
                                              {
LABEL_804:
                                                if ( !v261 )
                                                  LODWORD(v371) = v371 | 0x80;
                                              }
                                              v76 = UuidCreate(&v395);
                                              dwErrorCode = v76;
                                              if ( v76 )
                                              {
                                                v77 = WPP_GLOBAL_Control;
                                                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                                                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                                                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                                                {
                                                  goto LABEL_232;
                                                }
                                                v78 = 140;
                                                goto LABEL_231;
                                              }
                                              v396 = L"IKEv2 Client Quick mode IPsec tunnel policy";
                                              v397 = 9;
                                              v398 = v377;
                                              if ( v347 )
                                              {
                                                v264 = *((_QWORD *)this + 6);
                                                if ( *(_QWORD *)(*(_QWORD *)(v264 + 112) + 2064LL) )
                                                {
                                                  if ( (byte_1800AA941 & 8) == 0
                                                    || ((LOWORD(v418) = 0, !v264)
                                                     || (v265 = *(_QWORD *)(v264 + 112)) == 0
                                                     || !*(_QWORD *)(v265 + 16)
                                                      ? (v266 = 0xFFFFFFFFLL)
                                                      : (v266 = *(unsigned int *)(v265 + 16)),
                                                        ConvertPortNoToString(&v418, v266),
                                                        (byte_1800AA941 & 8) == 0) )
                                                  {
LABEL_829:
                                                    v271 = BuildCustomIpsecOffers(
                                                             *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL)
                                                                       + 2064LL),
                                                             *(_DWORD *)v350,
                                                             *(_DWORD *)v349,
                                                             *(_DWORD *)v354,
                                                             (__int64)&v346,
                                                             (__int64)&v366);
                                                    dwErrorCode = v271;
                                                    if ( v271 )
                                                    {
                                                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                      {
                                                        WPP_SF_d(
                                                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                          141,
                                                          &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                                          v271);
                                                      }
                                                      if ( (byte_1800AA941 & 4) == 0 )
                                                        goto LABEL_493;
                                                      LOWORD(v425) = 0;
                                                      LOWORD(v418) = 0;
                                                      v272 = *((_QWORD *)this + 6);
                                                      if ( v272 )
                                                      {
                                                        v273 = *(_QWORD *)(v272 + 112);
                                                        if ( v273 )
                                                        {
                                                          if ( *(_QWORD *)(v273 + 16) )
                                                            v13 = *(_DWORD *)(v273 + 16);
                                                        }
                                                      }
                                                      ConvertPortNoToString(&v418, v13);
                                                      FormatRRASErrorString(
                                                        &v425,
                                                        L"BuildCustomIpsecOffers failed: %d",
                                                        dwErrorCode);
                                                      goto LABEL_238;
                                                    }
                                                    if ( (byte_1800AA941 & 8) == 0
                                                      || ((LOWORD(v425) = 0,
                                                           LOWORD(v418) = 0,
                                                           (v274 = *((_QWORD *)this + 6)) == 0)
                                                       || (v275 = *(_QWORD *)(v274 + 112)) == 0
                                                       || !*(_QWORD *)(v275 + 16)
                                                        ? (v276 = 0xFFFFFFFFLL)
                                                        : (v276 = *(unsigned int *)(v275 + 16)),
                                                          ConvertPortNoToString(&v418, v276),
                                                          FormatRRASErrorString(
                                                            &v425,
                                                            L"Custom IPSec proposal count: %d",
                                                            v346),
                                                          (byte_1800AA941 & 8) == 0) )
                                                    {
LABEL_878:
                                                      v379 = v366;
                                                      v378 = v346;
                                                      if ( (byte_1800AA941 & 8) == 0 )
                                                        goto LABEL_894;
                                                      LOWORD(v425) = 0;
                                                      LOWORD(v418) = 0;
                                                      v292 = *((_QWORD *)this + 6);
                                                      if ( v292
                                                        && (v293 = *(_QWORD *)(v292 + 112)) != 0
                                                        && *(_QWORD *)(v293 + 16) )
                                                      {
                                                        v294 = *(unsigned int *)(v293 + 16);
                                                      }
                                                      else
                                                      {
                                                        v294 = 0xFFFFFFFFLL;
                                                      }
                                                      ConvertPortNoToString(&v418, v294);
                                                      EncryptionType = ConnectionParams::GetEncryptionType(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL));
                                                      LODWORD(phkResultb) = v338;
                                                      FormatRRASErrorString(
                                                        &v425,
                                                        L"Chosen encryption: %u,localauth: %u,remoteauth: %u",
                                                        EncryptionType,
                                                        v344,
                                                        phkResultb);
                                                      if ( (byte_1800AA941 & 8) == 0 )
                                                      {
LABEL_894:
                                                        if ( v336 )
                                                        {
                                                          v380 = 0;
                                                          v384 = ntohl(v367->S_un.S_addr);
                                                          if ( *(_DWORD *)v341 )
                                                            v381 = ntohl(*(_DWORD *)(*((_QWORD *)this + 6) + 48LL));
                                                        }
                                                        else
                                                        {
                                                          v380 = 1;
                                                          v384 = *(_DWORD *)v368->u.Byte;
                                                          v385 = *(_QWORD *)&v368->u.Word[2];
                                                          v386 = *(_DWORD *)&v368->u.Word[6];
                                                          if ( *(_DWORD *)v341 )
                                                          {
                                                            v300 = *((_QWORD *)this + 6);
                                                            v381 = *(_DWORD *)(v300 + 52);
                                                            v382 = *(_QWORD *)(v300 + 56);
                                                            v383 = *(_DWORD *)(v300 + 64);
                                                          }
                                                        }
                                                        v387 = *(_DWORD *)v362;
                                                        v388 = *(_DWORD *)v363;
                                                        v372 = 0;
                                                        BfeHandle = BFEHandler::GetBfeHandle(&v372);
                                                        dwErrorCode = BfeHandle;
                                                        if ( !v372 )
                                                        {
                                                          if ( BfeHandle
                                                            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                          {
                                                            WPP_SF_d(
                                                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                              143,
                                                              &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                                              BfeHandle);
                                                          }
                                                          if ( (byte_1800AA941 & 4) == 0 )
                                                            goto LABEL_493;
                                                          LOWORD(v425) = 0;
                                                          LOWORD(v418) = 0;
                                                          v302 = *((_QWORD *)this + 6);
                                                          if ( v302 )
                                                          {
                                                            v303 = *(_QWORD *)(v302 + 112);
                                                            if ( v303 )
                                                            {
                                                              if ( *(_QWORD *)(v303 + 16) )
                                                                v13 = *(_DWORD *)(v303 + 16);
                                                            }
                                                          }
                                                          ConvertPortNoToString(&v418, v13);
                                                          FormatRRASErrorString(
                                                            &v425,
                                                            L"GetBfeHandle failed: %d",
                                                            dwErrorCode);
                                                          goto LABEL_238;
                                                        }
                                                        v304 = FwpmIPsecTunnelAdd2(
                                                                 v372,
                                                                 2,
                                                                 &Uuid,
                                                                 &v395,
                                                                 0,
                                                                 0,
                                                                 &FWPM_KEYING_MODULE_IKEV2,
                                                                 0);
                                                        dwErrorCode = v304;
                                                        if ( !v304 )
                                                        {
                                                          v162 = *(char **)v335;
                                                          *(UUID *)(*(_QWORD *)v335 + 28LL) = Uuid;
                                                          *(UUID *)(v162 + 44) = v395;
                                                          *(_QWORD *)v162 = *((_QWORD *)this + 7);
                                                          *((_QWORD *)this + 7) = v162;
LABEL_494:
                                                          v163 = lpMem;
                                                          if ( lpMem )
                                                          {
                                                            v164 = GetProcessHeap();
                                                            HeapFree(v164, 0, v163);
                                                            lpMem = 0;
                                                          }
                                                          FreeIkeextCertificateCriteria(VpnikeFree, v351, v364);
                                                          v165 = v364;
                                                          if ( v364 )
                                                          {
                                                            v166 = GetProcessHeap();
                                                            HeapFree(v166, 0, v165);
                                                            v364 = 0;
                                                          }
                                                          v167 = v356;
                                                          if ( v356 )
                                                          {
                                                            v168 = (void *)*((_QWORD *)v356 + 3);
                                                            if ( v168 )
                                                            {
                                                              v169 = GetProcessHeap();
                                                              HeapFree(v169, 0, v168);
                                                              *((_QWORD *)v356 + 3) = 0;
                                                              v167 = v356;
                                                            }
                                                            if ( v167 )
                                                            {
                                                              v170 = GetProcessHeap();
                                                              HeapFree(v170, 0, v167);
                                                              v356 = 0;
                                                            }
                                                          }
                                                          if ( dwErrorCode && v162 )
                                                          {
                                                            v171 = GetProcessHeap();
                                                            HeapFree(v171, 0, v162);
                                                          }
                                                          if ( hKey )
                                                            RegCloseKey(hKey);
                                                          if ( v366 )
                                                            FreeIpsecOffers(v366);
                                                          if ( hMem )
                                                            LocalFree(hMem);
                                                          v14 = (PVOID *)WPP_GLOBAL_Control;
                                                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
                                                          {
                                                            v27 = 145;
                                                            goto LABEL_516;
                                                          }
                                                          goto LABEL_517;
                                                        }
                                                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                                        {
                                                          WPP_SF_d(
                                                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                            144,
                                                            &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                                            v304);
                                                        }
                                                        if ( (byte_1800AA941 & 4) == 0 )
                                                          goto LABEL_932;
                                                        LOWORD(v425) = 0;
                                                        LOWORD(v418) = 0;
                                                        v305 = *((_QWORD *)this + 6);
                                                        if ( v305
                                                          && (v306 = *(_QWORD *)(v305 + 112)) != 0
                                                          && *(_QWORD *)(v306 + 16) )
                                                        {
                                                          v307 = *(unsigned int *)(v306 + 16);
                                                        }
                                                        else
                                                        {
                                                          v307 = 0xFFFFFFFFLL;
                                                        }
                                                        ConvertPortNoToString(&v418, v307);
                                                        FormatRRASErrorString(
                                                          &v425,
                                                          L"FwpmIPsecTunnelAdd1 failed: %d",
                                                          dwErrorCode);
                                                        if ( (byte_1800AA941 & 4) == 0 )
                                                          goto LABEL_932;
                                                        v308 = *((_QWORD *)this + 6);
                                                        v309 = (_QWORD *)(v308 + 112);
                                                        if ( v308 )
                                                        {
                                                          if ( *v309 )
                                                            v310 = *v309 + 2686LL;
                                                          else
                                                            v310 = 0;
                                                          if ( *v309 )
                                                          {
                                                            v311 = (__int128 *)(*v309 + 2120LL);
LABEL_931:
                                                            McTemplateU0zjzz_EventWriteTransfer(
                                                              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                              (unsigned int)RasVpnIkeParamTraceError,
                                                              (unsigned int)&v425,
                                                              (_DWORD)v311,
                                                              v310,
                                                              (__int64)&v418);
LABEL_932:
                                                            if ( !*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL)
                                                                            + 2064LL) )
                                                              goto LABEL_493;
                                                            RouterLogEventA(
                                                              *((HANDLE *)VpnIkeProtocolEngine + 2),
                                                              1u,
                                                              0x4F3Eu,
                                                              0,
                                                              0,
                                                              dwErrorCode);
                                                            if ( (byte_1800AA941 & 4) == 0 )
                                                              goto LABEL_493;
                                                            LOWORD(v425) = 0;
                                                            LOWORD(v418) = 0;
                                                            v312 = *((_QWORD *)this + 6);
                                                            if ( v312 )
                                                            {
                                                              v313 = *(_QWORD *)(v312 + 112);
                                                              if ( v313 )
                                                              {
                                                                if ( *(_QWORD *)(v313 + 16) )
                                                                  v13 = *(_DWORD *)(v313 + 16);
                                                              }
                                                            }
                                                            ConvertPortNoToString(&v418, v13);
                                                            FormatRRASErrorString(
                                                              &v425,
                                                              L"Failed to plumb the custom IKEv2 policy - %d",
                                                              dwErrorCode);
                                                            goto LABEL_238;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v310 = 0;
                                                        }
                                                        v311 = &v403;
                                                        goto LABEL_931;
                                                      }
                                                      v296 = *((_QWORD *)this + 6);
                                                      v297 = (_QWORD *)(v296 + 112);
                                                      if ( v296 )
                                                      {
                                                        if ( *v297 )
                                                          v298 = *v297 + 2686LL;
                                                        else
                                                          v298 = 0;
                                                        if ( *v297 )
                                                        {
                                                          v299 = (__int128 *)(*v297 + 2120LL);
LABEL_893:
                                                          McTemplateU0zjzz_EventWriteTransfer(
                                                            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                            (unsigned int)RasVpnIkeParamTraceInfo,
                                                            (unsigned int)&v425,
                                                            (_DWORD)v299,
                                                            v298,
                                                            (__int64)&v418);
                                                          goto LABEL_894;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v298 = 0;
                                                      }
                                                      v299 = &v403;
                                                      goto LABEL_893;
                                                    }
                                                    v277 = *((_QWORD *)this + 6);
                                                    v278 = (_QWORD *)(v277 + 112);
                                                    if ( v277 )
                                                    {
                                                      if ( *v278 )
                                                        v279 = *v278 + 2686LL;
                                                      else
                                                        v279 = 0;
                                                      if ( *v278 )
                                                      {
                                                        v280 = (__int128 *)(*v278 + 2120LL);
LABEL_855:
                                                        McTemplateU0zjzz_EventWriteTransfer(
                                                          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                          (unsigned int)RasVpnIkeParamTraceInfo,
                                                          (unsigned int)&v425,
                                                          (_DWORD)v280,
                                                          v279,
                                                          (__int64)&v418);
                                                        goto LABEL_878;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v279 = 0;
                                                    }
                                                    v280 = &v403;
                                                    goto LABEL_855;
                                                  }
                                                  v267 = *((_QWORD *)this + 6);
                                                  v268 = (_QWORD *)(v267 + 112);
                                                  if ( v267 )
                                                  {
                                                    if ( *v268 )
                                                      v269 = *v268 + 2686LL;
                                                    else
                                                      v269 = 0;
                                                    if ( *v268 )
                                                    {
                                                      v270 = (__int128 *)(*v268 + 2120LL);
LABEL_828:
                                                      McTemplateU0zjzz_EventWriteTransfer(
                                                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                        (unsigned int)RasVpnIkeParamTraceInfo,
                                                        (unsigned int)L"Building custom IPSec proposals",
                                                        (_DWORD)v270,
                                                        v269,
                                                        (__int64)&v418);
                                                      goto LABEL_829;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    v269 = 0;
                                                  }
                                                  v270 = &v403;
                                                  goto LABEL_828;
                                                }
                                                v281 = 0;
                                                v282 = 0;
                                              }
                                              else
                                              {
                                                v281 = 0;
                                                v282 = 0;
                                                if ( v348 != 2 )
                                                {
                                                  v281 = *(_QWORD *)(v365 + 4544);
                                                  v282 = *(_DWORD *)(v365 + 4468);
                                                }
                                              }
                                              v283 = *(_DWORD *)v354;
                                              v284 = *(_DWORD *)v349;
                                              v285 = *(_DWORD *)v350;
                                              v286 = ConnectionParams::GetEncryptionType(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL));
                                              v287 = BuildIpsecOffers(
                                                       v286,
                                                       (unsigned int)&v366,
                                                       (unsigned int)&v346,
                                                       0,
                                                       v285,
                                                       v284,
                                                       v283,
                                                       0,
                                                       v281,
                                                       v282);
                                              dwErrorCode = v287;
                                              if ( !v287 )
                                                goto LABEL_878;
                                              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                              {
                                                WPP_SF_d(
                                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                                  142,
                                                  &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                                  v287);
                                              }
                                              if ( (byte_1800AA941 & 4) == 0 )
                                                goto LABEL_493;
                                              LOWORD(v425) = 0;
                                              LOWORD(v418) = 0;
                                              v288 = *((_QWORD *)this + 6);
                                              if ( v288 )
                                              {
                                                v289 = *(_QWORD *)(v288 + 112);
                                                if ( v289 )
                                                {
                                                  if ( *(_QWORD *)(v289 + 16) )
                                                    v13 = *(_DWORD *)(v289 + 16);
                                                }
                                              }
                                              ConvertPortNoToString(&v418, v13);
                                              FormatRRASErrorString(&v425, L"BuildIpsecOffers failed: %d", dwErrorCode);
                                              if ( (byte_1800AA941 & 4) == 0 )
                                                goto LABEL_493;
                                              v290 = *((_QWORD *)this + 6);
                                              v291 = (_QWORD *)(v290 + 112);
                                              if ( v290 )
                                              {
                                                if ( *v291 )
                                                  v160 = *v291 + 2686LL;
                                                else
                                                  v160 = 0;
                                                if ( *v291 )
                                                {
                                                  v161 = (__int128 *)(*v291 + 2120LL);
                                                  goto LABEL_492;
                                                }
                                              }
                                              else
                                              {
                                                v160 = 0;
                                              }
                                              v161 = &v403;
                                              goto LABEL_492;
                                            }
                                            v224 = *((_QWORD *)this + 6);
                                            v225 = (_QWORD *)(v224 + 112);
                                            if ( v224 )
                                            {
                                              if ( *v225 )
                                                v226 = *v225 + 2686LL;
                                              else
                                                v226 = 0;
                                              if ( *v225 )
                                              {
                                                v227 = (__int128 *)(*v225 + 2120LL);
LABEL_701:
                                                McTemplateU0zjzz_EventWriteTransfer(
                                                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                  (unsigned int)RasVpnIkeParamTraceInfo,
                                                  (unsigned int)L"Adding PSK as RemoteAuth method",
                                                  (_DWORD)v227,
                                                  v226,
                                                  (__int64)&v418);
                                                goto LABEL_702;
                                              }
                                            }
                                            else
                                            {
                                              v226 = 0;
                                            }
                                            v227 = &v403;
                                            goto LABEL_701;
                                          }
                                          if ( v89 != &WPP_GLOBAL_Control
                                            && (*((_BYTE *)v89 + 28) & 1) != 0
                                            && *((_BYTE *)v89 + 25) >= 5u )
                                          {
                                            WPP_SF_(v89[2], 134, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                            v89 = (PVOID *)WPP_GLOBAL_Control;
                                          }
                                          *(_DWORD *)v339 = 0;
                                          if ( v151 == 1 )
                                          {
                                            if ( !(unsigned int)ClientBFEHandler::IsPeerCertValidationForEapDisabled(
                                                                  this,
                                                                  (int *)v339)
                                              && *(_DWORD *)v339 )
                                            {
                                              goto LABEL_788;
                                            }
                                            v89 = (PVOID *)WPP_GLOBAL_Control;
                                          }
                                          if ( (byte_1800AA941 & 8) == 0 )
                                          {
LABEL_735:
                                            if ( v89 != &WPP_GLOBAL_Control
                                              && (*((_BYTE *)v89 + 28) & 1) != 0
                                              && *((_BYTE *)v89 + 25) >= 5u )
                                            {
                                              WPP_SF_(v89[2], 135, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                            }
                                            IsCertRequestPayloadDisabled = ClientBFEHandler::IsCertRequestPayloadDisabled(this);
                                            v236 = v344;
                                            if ( v344 != 2 )
                                              v417 = 3;
                                            v237 = 20;
                                            v238 = -(__int64)(v344 != 2) & 0x50;
                                            v239 = v343;
                                            *(_DWORD *)((char *)v406 + v238) = v343;
                                            if ( IsCertRequestPayloadDisabled )
                                              *(_DWORD *)((char *)&v412[1] + v238) = 64;
                                            if ( v351 )
                                            {
                                              *(_DWORD *)((char *)&v409[-2] + v238) = v351;
                                              *(_QWORD *)((char *)v409 + v238) = v364;
                                              v240 = 0;
                                            }
                                            else
                                            {
                                              v240 = 2;
                                            }
                                            *(_DWORD *)((char *)v407 + v238) = v240;
                                            v241 = (v236 != 2) + 1LL;
                                            if ( IsCertRequestPayloadDisabled )
                                              LODWORD(v412[10 * v241 + 1]) = 64;
                                            v242 = 10 * v241;
                                            *(_OWORD *)&v406[2 * v242] = *(_OWORD *)((char *)v406 + v238);
                                            *(_OWORD *)&v409[2 * v242 - 2] = *(_OWORD *)((char *)&v409[-2] + v238);
                                            *(_OWORD *)&v410[2 * v242] = *(_OWORD *)((char *)v410 + v238);
                                            *(_OWORD *)&v412[v242] = *(_OWORD *)((char *)v412 + v238);
                                            *(_OWORD *)&v412[v242 + 2] = *(_OWORD *)((char *)&v412[2] + v238);
                                            v243 = 1;
                                            if ( v239 == IKEEXT_CERTIFICATE )
                                              v243 = 7;
                                            v406[2 * v242] = v243;
                                            v410[2 * v242] = 3;
                                            v244 = byte_1800AA941;
                                            if ( (byte_1800AA941 & 8) == 0 )
                                            {
LABEL_769:
                                              v252 = (unsigned int)(v236 != 2) + 2;
                                              v216 = v252;
                                              if ( IsCertRequestPayloadDisabled )
                                                LODWORD(v412[10 * v252 + 1]) = 64;
                                              v253 = 10 * v252;
                                              *(_OWORD *)&v406[2 * v253] = *(_OWORD *)&v406[20
                                                                                          * (unsigned int)(v252 - 1)];
                                              *(_OWORD *)&v409[2 * v253 - 2] = *(_OWORD *)&v409[20
                                                                                              * (unsigned int)(v252 - 1)
                                                                                              - 2];
                                              *(_OWORD *)&v410[2 * v253] = *(_OWORD *)&v410[20
                                                                                          * (unsigned int)(v252 - 1)];
                                              *(_OWORD *)&v412[v253] = *(_OWORD *)&v412[10 * (unsigned int)(v252 - 1)];
                                              *(_OWORD *)&v412[v253 + 2] = *(_OWORD *)&v412[10
                                                                                          * (unsigned int)(v252 - 1)
                                                                                          + 2];
                                              v406[2 * v253] = (v239 != IKEEXT_CERTIFICATE_ECDSA_P384) + 7;
                                              v410[2 * v253] = 3;
                                              if ( (v244 & 8) == 0 )
                                                goto LABEL_787;
                                              LOWORD(v425) = 0;
                                              LOWORD(v418) = 0;
                                              v254 = *((_QWORD *)this + 6);
                                              if ( v254
                                                && (v255 = *(_QWORD *)(v254 + 112)) != 0
                                                && *(_QWORD *)(v255 + 16) )
                                              {
                                                v256 = *(unsigned int *)(v255 + 16);
                                              }
                                              else
                                              {
                                                v256 = 0xFFFFFFFFLL;
                                              }
                                              ConvertPortNoToString(&v418, v256);
                                              FormatRRASErrorString(
                                                &v425,
                                                L"Adding Cert(method type: %d) as RemoteAuth method",
                                                (unsigned int)v406[20 * v216]);
                                              if ( (byte_1800AA941 & 8) == 0 )
                                                goto LABEL_787;
                                              v257 = *((_QWORD *)this + 6);
                                              v258 = (_QWORD *)(v257 + 112);
                                              if ( v257 )
                                              {
                                                if ( *v258 )
                                                  v259 = *v258 + 2686LL;
                                                else
                                                  v259 = 0;
                                                if ( *v258 )
                                                {
                                                  v260 = (__int128 *)(*v258 + 2120LL);
LABEL_786:
                                                  McTemplateU0zjzz_EventWriteTransfer(
                                                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                    (unsigned int)RasVpnIkeParamTraceInfo,
                                                    (unsigned int)&v425,
                                                    (_DWORD)v260,
                                                    v259,
                                                    (__int64)&v418);
LABEL_787:
                                                  *((_DWORD *)this + 16) = 1;
                                                  goto LABEL_788;
                                                }
                                              }
                                              else
                                              {
                                                v259 = 0;
                                              }
                                              v260 = &v403;
                                              goto LABEL_786;
                                            }
                                            LOWORD(v425) = 0;
                                            LOWORD(v418) = 0;
                                            v245 = *((_QWORD *)this + 6);
                                            if ( v245 && (v246 = *(_QWORD *)(v245 + 112)) != 0 && *(_QWORD *)(v246 + 16) )
                                              v247 = *(unsigned int *)(v246 + 16);
                                            else
                                              v247 = 0xFFFFFFFFLL;
                                            ConvertPortNoToString(&v418, v247);
                                            if ( v236 != 2 )
                                              v237 = 40;
                                            FormatRRASErrorString(
                                              &v425,
                                              L"Adding Cert(method type: %d) as RemoteAuth method",
                                              (unsigned int)v406[v237]);
                                            v244 = byte_1800AA941;
                                            if ( (byte_1800AA941 & 8) == 0 )
                                            {
LABEL_768:
                                              v239 = v343;
                                              goto LABEL_769;
                                            }
                                            v248 = *((_QWORD *)this + 6);
                                            v249 = (_QWORD *)(v248 + 112);
                                            if ( v248 )
                                            {
                                              if ( *v249 )
                                                v250 = *v249 + 2686LL;
                                              else
                                                v250 = 0;
                                              if ( *v249 )
                                              {
                                                v251 = (__int128 *)(*v249 + 2120LL);
LABEL_767:
                                                McTemplateU0zjzz_EventWriteTransfer(
                                                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                  (unsigned int)RasVpnIkeParamTraceInfo,
                                                  (unsigned int)&v425,
                                                  (_DWORD)v251,
                                                  v250,
                                                  (__int64)&v418);
                                                v244 = byte_1800AA941;
                                                goto LABEL_768;
                                              }
                                            }
                                            else
                                            {
                                              v250 = 0;
                                            }
                                            v251 = &v403;
                                            goto LABEL_767;
                                          }
                                          LOWORD(v418) = 0;
                                          v228 = *((_QWORD *)this + 6);
                                          if ( v228 && (v229 = *(_QWORD *)(v228 + 112)) != 0 && *(_QWORD *)(v229 + 16) )
                                            v230 = *(unsigned int *)(v229 + 16);
                                          else
                                            v230 = 0xFFFFFFFFLL;
                                          ConvertPortNoToString(&v418, v230);
                                          if ( (byte_1800AA941 & 8) == 0 )
                                          {
LABEL_734:
                                            v89 = (PVOID *)WPP_GLOBAL_Control;
                                            goto LABEL_735;
                                          }
                                          v231 = *((_QWORD *)this + 6);
                                          v232 = (_QWORD *)(v231 + 112);
                                          if ( v231 )
                                          {
                                            if ( *v232 )
                                              v233 = *v232 + 2686LL;
                                            else
                                              v233 = 0;
                                            if ( *v232 )
                                            {
                                              v234 = (__int128 *)(*v232 + 2120LL);
LABEL_733:
                                              McTemplateU0zjzz_EventWriteTransfer(
                                                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                (unsigned int)RasVpnIkeParamTraceInfo,
                                                (unsigned int)L"Adding Cert as RemoteAuth method",
                                                (_DWORD)v234,
                                                v233,
                                                (__int64)&v418);
                                              goto LABEL_734;
                                            }
                                          }
                                          else
                                          {
                                            v233 = 0;
                                          }
                                          v234 = &v403;
                                          goto LABEL_733;
                                        }
                                        if ( (byte_1800AA941 & 4) == 0 )
                                        {
LABEL_629:
                                          v201 = 2;
                                          v338 = 2;
                                          goto LABEL_653;
                                        }
                                        LOWORD(v425) = 0;
                                        LOWORD(v418) = 0;
                                        v202 = *((_QWORD *)this + 6);
                                        if ( v202 && (v203 = *(_QWORD *)(v202 + 112)) != 0 && *(_QWORD *)(v203 + 16) )
                                          v204 = *(unsigned int *)(v203 + 16);
                                        else
                                          v204 = 0xFFFFFFFFLL;
                                        ConvertPortNoToString(&v418, v204);
                                        FormatRRASErrorString(
                                          &v425,
                                          L"Initiator cannot combine cert local auth type with non-cert remote auth types."
                                           "Changing remote auth type from %d to AUTH_MACHINE_CERTIFICATES",
                                          v338);
                                        if ( (byte_1800AA941 & 4) == 0 )
                                        {
LABEL_628:
                                          v89 = (PVOID *)WPP_GLOBAL_Control;
                                          goto LABEL_629;
                                        }
                                        v205 = *((_QWORD *)this + 6);
                                        v206 = (_QWORD *)(v205 + 112);
                                        if ( v205 )
                                        {
                                          if ( *v206 )
                                            v207 = *v206 + 2686LL;
                                          else
                                            v207 = 0;
                                          if ( *v206 )
                                          {
                                            v208 = (__int128 *)(*v206 + 2120LL);
LABEL_627:
                                            McTemplateU0zjzz_EventWriteTransfer(
                                              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                              (unsigned int)RasVpnIkeParamTraceError,
                                              (unsigned int)&v425,
                                              (_DWORD)v208,
                                              v207,
                                              (__int64)&v418);
                                            goto LABEL_628;
                                          }
                                        }
                                        else
                                        {
                                          v207 = 0;
                                        }
                                        v208 = &v403;
                                        goto LABEL_627;
                                      }
                                    }
                                    LODWORD(v375) = 2;
                                    *((_QWORD *)&v375 + 1) = v374;
                                    LODWORD(v376) = 1;
                                    *((_QWORD *)&v376 + 1) = v374;
                                    v197 = GetProcessHeap();
                                    v198 = HeapAlloc(v197, 8u, 0x70u);
                                    lpMem = v198;
                                    if ( !v198 )
                                    {
                                      dwErrorCode = 8;
                                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                      {
                                        WPP_SF_d(
                                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                                          127,
                                          &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                          8);
                                      }
                                      if ( (byte_1800AA941 & 4) == 0 )
                                        goto LABEL_493;
                                      LOWORD(v425) = 0;
                                      LOWORD(v418) = 0;
                                      v199 = *((_QWORD *)this + 6);
                                      if ( v199 )
                                      {
                                        v200 = *(_QWORD *)(v199 + 112);
                                        if ( v200 )
                                        {
                                          if ( *(_QWORD *)(v200 + 16) )
                                            v13 = *(_DWORD *)(v200 + 16);
                                        }
                                      }
                                      ConvertPortNoToString(&v418, v13);
                                      FormatRRASErrorString(
                                        &v425,
                                        L"VPNIKE_MALLOC[configuredTrustedListOutbound] failed: %d",
                                        dwErrorCode);
                                      goto LABEL_238;
                                    }
                                    v198[4] = &v375;
                                    *((_QWORD *)lpMem + 11) = &v376;
                                    v411 = 2;
                                    v195 = lpMem;
                                    v89 = (PVOID *)WPP_GLOBAL_Control;
                                    goto LABEL_610;
                                  }
                                  LOWORD(v418) = 0;
                                  v181 = *((_QWORD *)this + 6);
                                  if ( v181 && (v182 = *(_QWORD *)(v181 + 112)) != 0 && *(_QWORD *)(v182 + 16) )
                                    v183 = *(unsigned int *)(v182 + 16);
                                  else
                                    v183 = 0xFFFFFFFFLL;
                                  ConvertPortNoToString(&v418, v183);
                                  if ( (byte_1800AA941 & 8) == 0 )
                                  {
LABEL_560:
                                    v89 = (PVOID *)WPP_GLOBAL_Control;
                                    goto LABEL_561;
                                  }
                                  v184 = *((_QWORD *)this + 6);
                                  v185 = (_QWORD *)(v184 + 112);
                                  if ( v184 )
                                  {
                                    if ( *v185 )
                                      v186 = *v185 + 2686LL;
                                    else
                                      v186 = 0;
                                    if ( *v185 )
                                    {
                                      v187 = (__int128 *)(*v185 + 2120LL);
LABEL_559:
                                      McTemplateU0zjzz_EventWriteTransfer(
                                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                        (unsigned int)RasVpnIkeParamTraceInfo,
                                        (unsigned int)L"Adding Cert as LocalAuth method",
                                        (_DWORD)v187,
                                        v186,
                                        (__int64)&v418);
                                      goto LABEL_560;
                                    }
                                  }
                                  else
                                  {
                                    v186 = 0;
                                  }
                                  v187 = &v403;
                                  goto LABEL_559;
                                }
                                if ( v89 != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)v89 + 28) & 1) != 0
                                  && *((_BYTE *)v89 + 25) >= 5u )
                                {
                                  WPP_SF_(v89[2], 122, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
                                  v89 = (PVOID *)WPP_GLOBAL_Control;
                                }
                                if ( (byte_1800AA941 & 8) == 0 )
                                {
LABEL_651:
                                  v406[0] = 11;
                                  v407[0] = 1;
                                  goto LABEL_652;
                                }
                                LOWORD(v418) = 0;
                                v209 = *((_QWORD *)this + 6);
                                if ( v209 && (v210 = *(_QWORD *)(v209 + 112)) != 0 && *(_QWORD *)(v210 + 16) )
                                  v211 = *(unsigned int *)(v210 + 16);
                                else
                                  v211 = 0xFFFFFFFFLL;
                                ConvertPortNoToString(&v418, v211);
                                if ( (byte_1800AA941 & 8) == 0 )
                                {
LABEL_650:
                                  v89 = (PVOID *)WPP_GLOBAL_Control;
                                  goto LABEL_651;
                                }
                                v212 = *((_QWORD *)this + 6);
                                v213 = (_QWORD *)(v212 + 112);
                                if ( v212 )
                                {
                                  if ( *v213 )
                                    v214 = *v213 + 2686LL;
                                  else
                                    v214 = 0;
                                  if ( *v213 )
                                  {
                                    v215 = (__int128 *)(*v213 + 2120LL);
LABEL_649:
                                    McTemplateU0zjzz_EventWriteTransfer(
                                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                      (unsigned int)RasVpnIkeParamTraceInfo,
                                      (unsigned int)L"Adding EAP as LocalAuth method",
                                      (_DWORD)v215,
                                      v214,
                                      (__int64)&v418);
                                    goto LABEL_650;
                                  }
                                }
                                else
                                {
                                  v214 = 0;
                                }
                                v215 = &v403;
                                goto LABEL_649;
                              }
                              v314 = 74;
                              dwErrorCode = 1610;
                              v315 = L"both remote/local";
                              if ( (byte_1800AA941 & 1) == 0 )
                              {
                                v318 = v344;
                                v319 = v338;
                                goto LABEL_962;
                              }
                              LOWORD(v425) = 0;
                              LOWORD(v418) = 0;
                              v316 = *((_QWORD *)this + 6);
                              if ( v316 )
                              {
                                v317 = *(_QWORD *)(v316 + 112);
                                if ( v317 )
                                {
                                  if ( *(_QWORD *)(v317 + 16) )
                                    v13 = *(_DWORD *)(v317 + 16);
                                }
                              }
                              ConvertPortNoToString(&v418, v13);
                              v318 = v344;
                              v319 = v338;
                              if ( v338 == v344 )
                              {
                                v320 = L"both remote/local";
                              }
                              else
                              {
                                v320 = L"remote";
                                if ( v338 != 3 )
                                  v320 = L"local";
                              }
                              FormatRRASErrorString(
                                &v425,
                                L"PreShareKey is not available while %s auth is configured as PSK",
                                v320);
                              if ( (byte_1800AA941 & 1) == 0 )
                              {
LABEL_959:
                                v314 = dwErrorCode;
                                if ( !dwErrorCode )
                                {
LABEL_969:
                                  v404 = *(_OWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 112LL) + 2120LL);
                                  MprConvertGuidToString(&v404, 40, v422);
                                  plpszSubStringArray = (LPSTR)v422;
                                  RouterLogEventA(
                                    *((HANDLE *)VpnIkeProtocolEngine + 2),
                                    1u,
                                    0x4F3Fu,
                                    1u,
                                    &plpszSubStringArray,
                                    dwErrorCode);
                                  goto LABEL_493;
                                }
                                v89 = (PVOID *)WPP_GLOBAL_Control;
LABEL_962:
                                if ( v89 != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)v89 + 28) & 1) != 0
                                  && *((_BYTE *)v89 + 25) >= 2u )
                                {
                                  if ( v319 != v318 )
                                  {
                                    v315 = L"remote";
                                    if ( v319 != 3 )
                                      v315 = L"local";
                                  }
                                  WPP_SF_SD(
                                    (unsigned int)v89[2],
                                    120,
                                    (unsigned int)&WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
                                    (_DWORD)v315,
                                    v314);
                                }
                                goto LABEL_969;
                              }
                              v321 = *((_QWORD *)this + 6);
                              v322 = (_QWORD *)(v321 + 112);
                              if ( v321 )
                              {
                                if ( *v322 )
                                  v323 = *v322 + 2686LL;
                                else
                                  v323 = 0;
                                if ( *v322 )
                                {
                                  v324 = (__int128 *)(*v322 + 2120LL);
LABEL_958:
                                  McTemplateU0zjzz_EventWriteTransfer(
                                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                    (unsigned int)RasVpnIkeParamTraceAdminError,
                                    (unsigned int)&v425,
                                    (_DWORD)v324,
                                    v323,
                                    (__int64)&v418);
                                  goto LABEL_959;
                                }
                              }
                              else
                              {
                                v323 = 0;
                              }
                              v324 = &v403;
                              goto LABEL_958;
                            }
                            if ( (byte_1800AA941 & 4) == 0 )
                              goto LABEL_493;
                            LOWORD(v425) = 0;
                            LOWORD(v418) = 0;
                            v156 = *((_QWORD *)this + 6);
                            if ( v156 )
                            {
                              v157 = *(_QWORD *)(v156 + 112);
                              if ( v157 )
                              {
                                if ( *(_QWORD *)(v157 + 16) )
                                  v13 = *(_DWORD *)(v157 + 16);
                              }
                            }
                            ConvertPortNoToString(&v418, v13);
                            FormatRRASErrorString(&v425, L"BuildIKEEncryption %d", dwErrorCode);
                            if ( (byte_1800AA941 & 4) == 0 )
                              goto LABEL_493;
                            v158 = *((_QWORD *)this + 6);
                            v159 = (_QWORD *)(v158 + 112);
                            if ( v158 )
                            {
                              if ( *v159 )
                                v160 = *v159 + 2686LL;
                              else
                                v160 = 0;
                              if ( *v159 )
                              {
                                v161 = (__int128 *)(*v159 + 2120LL);
LABEL_492:
                                McTemplateU0zjzz_EventWriteTransfer(
                                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                  (unsigned int)RasVpnIkeParamTraceError,
                                  (unsigned int)&v425,
                                  (_DWORD)v161,
                                  v160,
                                  (__int64)&v418);
                                goto LABEL_493;
                              }
                            }
                            else
                            {
                              v160 = 0;
                            }
                            v161 = &v403;
                            goto LABEL_492;
                          }
                        }
LABEL_476:
                        v89 = (PVOID *)WPP_GLOBAL_Control;
                        goto LABEL_477;
                      }
                      if ( v348 == 2 )
                        goto LABEL_464;
                      v130 = v365;
                      if ( !*(_DWORD *)(v365 + 4468) || !*(_QWORD *)(v365 + 4544) )
                        goto LABEL_464;
                      if ( (byte_1800AA941 & 8) == 0
                        || ((LOWORD(v418) = 0, (v131 = *((_QWORD *)this + 6)) == 0)
                         || (v132 = *(_QWORD *)(v131 + 112)) == 0
                         || !*(_QWORD *)(v132 + 16)
                          ? (v133 = 0xFFFFFFFFLL)
                          : (v133 = *(unsigned int *)(v132 + 16)),
                            ConvertPortNoToString(&v418, v133),
                            (byte_1800AA941 & 8) == 0) )
                      {
LABEL_399:
                        v91 = BuildIkev2ClientCustomProposals(
                                *(_QWORD *)(v130 + 4544),
                                *(_DWORD *)(v130 + 4468),
                                *(_DWORD *)v342,
                                (unsigned int)&v337,
                                (__int64)&hMem);
                        dwErrorCode = v91;
                        if ( !v91 )
                        {
                          if ( (byte_1800AA941 & 8) == 0 )
                            goto LABEL_438;
                          LOWORD(v425) = 0;
                          LOWORD(v418) = 0;
                          v144 = *((_QWORD *)this + 6);
                          if ( v144 && (v145 = *(_QWORD *)(v144 + 112)) != 0 && *(_QWORD *)(v145 + 16) )
                            v146 = *(unsigned int *)(v145 + 16);
                          else
                            v146 = 0xFFFFFFFFLL;
                          ConvertPortNoToString(&v418, v146);
                          FormatRRASErrorString(&v425, L"Custom Client IKEv2 proposal count: %d", v337);
LABEL_428:
                          if ( (byte_1800AA941 & 8) != 0 )
                          {
                            v147 = *((_QWORD *)this + 6);
                            v148 = (_QWORD *)(v147 + 112);
                            if ( v147 )
                            {
                              if ( *v148 )
                                v149 = *v148 + 2686LL;
                              else
                                v149 = 0;
                              if ( *v148 )
                              {
                                v150 = (__int128 *)(*v148 + 2120LL);
LABEL_437:
                                McTemplateU0zjzz_EventWriteTransfer(
                                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                  (unsigned int)RasVpnIkeParamTraceInfo,
                                  (unsigned int)&v425,
                                  (_DWORD)v150,
                                  v149,
                                  (__int64)&v418);
                                goto LABEL_438;
                              }
                            }
                            else
                            {
                              v149 = 0;
                            }
                            v150 = &v403;
                            goto LABEL_437;
                          }
LABEL_438:
                          v89 = (PVOID *)WPP_GLOBAL_Control;
                          goto LABEL_439;
                        }
                        if ( (byte_1800AA941 & 4) == 0 )
                        {
LABEL_416:
                          if ( !v91 )
                            goto LABEL_493;
                          v98 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                          {
                            goto LABEL_493;
                          }
                          v99 = 117;
LABEL_285:
                          WPP_SF_d(v98[2], v99, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v91);
                          goto LABEL_493;
                        }
                        LOWORD(v425) = 0;
                        LOWORD(v418) = 0;
                        v138 = *((_QWORD *)this + 6);
                        if ( v138 )
                        {
                          v139 = *(_QWORD *)(v138 + 112);
                          if ( v139 )
                          {
                            if ( *(_QWORD *)(v139 + 16) )
                              v13 = *(_DWORD *)(v139 + 16);
                          }
                        }
                        ConvertPortNoToString(&v418, v13);
                        FormatRRASErrorString(&v425, L"BuildIkev2ClientCustomProposals failed: %d", dwErrorCode);
                        if ( (byte_1800AA941 & 4) == 0 )
                        {
LABEL_415:
                          v91 = dwErrorCode;
                          goto LABEL_416;
                        }
                        v140 = *((_QWORD *)this + 6);
                        v141 = (_QWORD *)(v140 + 112);
                        if ( v140 )
                        {
                          if ( *v141 )
                            v142 = *v141 + 2686LL;
                          else
                            v142 = 0;
                          if ( *v141 )
                          {
                            v143 = (__int128 *)(*v141 + 2120LL);
LABEL_414:
                            McTemplateU0zjzz_EventWriteTransfer(
                              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                              (unsigned int)RasVpnIkeParamTraceError,
                              (unsigned int)&v425,
                              (_DWORD)v143,
                              v142,
                              (__int64)&v418);
                            goto LABEL_415;
                          }
                        }
                        else
                        {
                          v142 = 0;
                        }
                        v143 = &v403;
                        goto LABEL_414;
                      }
                      v134 = *((_QWORD *)this + 6);
                      v135 = (_QWORD *)(v134 + 112);
                      if ( v134 )
                      {
                        if ( *v135 )
                          v136 = *v135 + 2686LL;
                        else
                          v136 = 0;
                        if ( *v135 )
                        {
                          v137 = (__int128 *)(*v135 + 2120LL);
LABEL_398:
                          McTemplateU0zjzz_EventWriteTransfer(
                            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                            (unsigned int)RasVpnIkeParamTraceInfo,
                            (unsigned int)L"Building custom Client IKEv2 proposals",
                            (_DWORD)v137,
                            v136,
                            (__int64)&v418);
                          goto LABEL_399;
                        }
                      }
                      else
                      {
                        v136 = 0;
                      }
                      v137 = &v403;
                      goto LABEL_398;
                    }
                    WPP_SF_d(v89[2], 114, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, (unsigned int)v343);
                  }
                  v89 = (PVOID *)WPP_GLOBAL_Control;
                  goto LABEL_315;
                }
                v72 = *((_QWORD *)this + 6);
                v73 = (_QWORD *)(v72 + 112);
                if ( v72 )
                {
                  if ( *v73 )
                    v74 = *v73 + 2686LL;
                  else
                    v74 = 0;
                  if ( *v73 )
                  {
                    v75 = (__int128 *)(*v73 + 2120LL);
LABEL_225:
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasVpnIkeParamTraceInfo,
                      (unsigned int)L"Adding Policy for Server address",
                      (_DWORD)v75,
                      v74,
                      (__int64)&v418);
                    goto LABEL_226;
                  }
                }
                else
                {
                  v74 = 0;
                }
                v75 = &v403;
                goto LABEL_225;
              }
            }
            else
            {
              v60 = 0;
            }
            v61 = &v403;
            goto LABEL_188;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v54);
          }
        }
LABEL_198:
        v63 = a5;
        v62 = a6;
        goto LABEL_199;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v50);
      v50 = dwErrorCode;
    }
    v51 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_152;
  }
  dwErrorCode = 87;
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 2u )
  {
    WPP_SF_d(v14[2], 82, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 87);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v418) = 0;
    v21 = *((_QWORD *)this + 6);
    if ( v21 )
    {
      v22 = *(_QWORD *)(v21 + 112);
      if ( v22 )
      {
        if ( *(_QWORD *)(v22 + 16) )
          v13 = *(_DWORD *)(v22 + 16);
      }
    }
    ConvertPortNoToString(&v418, v13);
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_41;
    v23 = *((_QWORD *)this + 6);
    v24 = (_QWORD *)(v23 + 112);
    if ( v23 )
    {
      if ( *v24 )
        v25 = *v24 + 2686LL;
      else
        v25 = 0;
      if ( *v24 )
      {
        v26 = (__int128 *)(*v24 + 2120LL);
LABEL_40:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"Invalid param",
          (_DWORD)v26,
          v25,
          (__int64)&v418);
LABEL_41:
        v14 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_42;
      }
    }
    else
    {
      v25 = 0;
    }
    v26 = &v403;
    goto LABEL_40;
  }
LABEL_42:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 6u )
  {
    v27 = 83;
LABEL_516:
    WPP_SF_d(v14[2], v27, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, dwErrorCode);
  }
LABEL_517:
  v172 = dwErrorCode;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v389);
  return v172;
}

```

## disassembly

```asm
0x180032690  mov     [rsp-8+arg_8], rbx
0x180032695  push    rbp
0x180032696  push    rsi
0x180032697  push    rdi
0x180032698  push    r12
0x18003269a  push    r13
0x18003269c  push    r14
0x18003269e  push    r15
0x1800326a0  lea     rbp, [rsp-0E00h]
0x1800326a8  sub     rsp, 0F00h
0x1800326af  mov     rax, cs:__security_cookie
0x1800326b6  xor     rax, rsp
0x1800326b9  mov     [rbp+0E30h+var_40], rax
0x1800326c0  mov     [rbp+0E30h+var_E28], r9
0x1800326c4  mov     [rbp+0E30h+var_E30], r8
0x1800326c8  mov     al, dl
0x1800326ca  mov     [rsp+0F30h+var_ED0], dl
0x1800326ce  mov     r14, rcx
0x1800326d1  lea     rdx, WPP_GLOBAL_Control
0x1800326d8  xor     r15d, r15d
0x1800326db  lea     ebx, [r15+1]
0x1800326df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326e6  cmp     rcx, rdx
0x1800326e9  jz      short loc_18003270F
0x1800326eb  test    [rcx+1Ch], bl
0x1800326ee  jz      short loc_18003270F
0x1800326f0  cmp     byte ptr [rcx+19h], 6
0x1800326f4  jb      short loc_18003270F
0x1800326f6  test    al, al
0x1800326f8  setnz   r9b
0x1800326fc  lea     edx, [rbx+4Fh]
0x1800326ff  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180032706  mov     rcx, [rcx+10h]
0x18003270a  call    WPP_SF_c
0x18003270f  mov     [rsp+0F30h+dwErrorCode], r15d
0x180032714  xor     edx, edx; Val
0x180032716  mov     r8d, 1E0h; Size
0x18003271c  lea     rcx, [rbp+0E30h+var_BA0]; void *
0x180032723  call    memset_0
0x180032728  mov     edi, 58h ; 'X'
0x18003272d  mov     r8d, edi; Size
0x180032730  xor     edx, edx; Val
0x180032732  lea     rcx, [rbp+0E30h+var_D00]; void *
0x180032739  call    memset_0
0x18003273e  mov     r8d, edi; Size
0x180032741  xor     edx, edx; Val
0x180032743  lea     rcx, [rbp+0E30h+Uuid]; void *
0x18003274a  call    memset_0
0x18003274f  xorps   xmm0, xmm0
0x180032752  movups  [rbp+0E30h+var_E20], xmm0
0x180032756  movups  [rbp+0E30h+var_E10], xmm0
0x18003275a  movups  [rbp+0E30h+var_E00], xmm0
0x18003275e  mov     [rbp+0E30h+hMem], r15
0x180032762  xor     edx, edx; Val
0x180032764  lea     r8d, [rdi+18h]; Size
0x180032768  lea     rcx, [rbp+0E30h+var_DB0]; void *
0x18003276f  call    memset_0
0x180032774  mov     [rbp+0E30h+var_E38], r15
0x180032778  mov     [rbp+0E30h+var_EA0], r15d
0x18003277c  mov     [rsp+0F30h+var_ECC], r15d
0x180032781  mov     [rsp+0F30h+hKey], r15
0x180032786  mov     dword ptr [rbp+0E30h+Data], r15d
0x18003278a  mov     [rsp+0F30h+cbData], r15d
0x18003278f  mov     dword ptr [rsp+0F30h+var_EB4], 7080h
0x180032797  mov     dword ptr [rbp+0E30h+var_E50], 12Ch
0x18003279e  mov     dword ptr [rbp+0E30h+var_E4C], 3Ch ; '<'
0x1800327a5  mov     dword ptr [rbp+0E30h+var_E94], 0E10h
0x1800327ac  mov     dword ptr [rbp+0E30h+var_E90], 3D090h
0x1800327b3  mov     dword ptr [rbp+0E30h+var_E80], 7FFFFFFFh
0x1800327ba  mov     rcx, [r14+30h]
0x1800327be  mov     rcx, [rcx+70h]
0x1800327c2  call    ?GetAuthenticationType@ConnectionParams@@QEAA?AW4_IKEv2_AUTH_TYPE_@@XZ; ConnectionParams::GetAuthenticationType(void)
0x1800327c7  mov     edi, eax
0x1800327c9  mov     [rbp+0E30h+var_EAC], eax
0x1800327cc  mov     rcx, [r14+30h]
0x1800327d0  mov     rcx, [rcx+70h]
0x1800327d4  call    ?GetRemoteAuthenticationType@ConnectionParams@@QEAA?AW4_IKEv2_AUTH_TYPE_@@XZ; ConnectionParams::GetRemoteAuthenticationType(void)
0x1800327d9  mov     r13d, eax
0x1800327dc  mov     [rsp+0F30h+var_EC8], eax
0x1800327e0  mov     [rbp+0E30h+var_140], r15b
0x1800327e7  xor     edx, edx; Val
0x1800327e9  mov     r8d, 0FFh; Size
0x1800327ef  lea     rcx, [rbp+0E30h+var_13F]; void *
0x1800327f6  call    memset_0
0x1800327fb  mov     [rbp+0E30h+var_E70], r15
0x1800327ff  mov     [rbp+0E30h+lpMem], r15
0x180032803  mov     [rbp+0E30h+var_EB0], ebx
0x180032806  mov     [rbp+0E30h+var_E8C], r15d
0x18003280a  mov     [rbp+0E30h+var_E48], r15
0x18003280e  mov     rcx, [r14+30h]
0x180032812  mov     rcx, [rcx+70h]; this
0x180032816  call    ?IsRouter@ConnectionParams@@QEAAHXZ; ConnectionParams::IsRouter(void)
0x18003281b  mov     esi, eax
0x18003281d  mov     [rbp+0E30h+var_E9C], eax
0x180032820  mov     rbx, [r14+30h]
0x180032824  mov     rcx, [rbx+70h]
0x180032828  mov     r12d, [rcx+28h]
0x18003282c  mov     [rbp+0E30h+var_E98], r12d
0x180032830  mov     [rbp+0E30h+plpszSubStringArray], r15
0x180032834  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18003283b  movaps  [rbp+0E30h+var_990], xmm0
0x180032842  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180032849  movaps  [rbp+0E30h+var_980], xmm1
0x180032850  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180032857  movaps  [rbp+0E30h+var_970], xmm0
0x18003285e  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180032865  movaps  xmmword ptr [rbp+0E30h+var_960], xmm1
0x18003286c  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x180032873  movups  xmmword ptr [rbp+0E30h+var_960+0Eh], xmm0
0x18003287a  xor     eax, eax
0x18003287c  mov     [rbp+0E30h+var_942], ax
0x180032883  xorps   xmm0, xmm0
0x180032886  movups  [rbp+0E30h+var_C30], xmm0
0x18003288d  lea     rax, a136155732; "1.3.6.1.5.5.7.3.2"
0x180032894  mov     [rbp+0E30h+var_DE0], rax
0x180032898  lea     rax, a136155822; "1.3.6.1.5.5.8.2.2"
0x18003289f  mov     [rbp+0E30h+var_DD8], rax
0x1800328a3  movups  [rbp+0E30h+var_DD0], xmm0
0x1800328a7  xorps   xmm1, xmm1
0x1800328aa  movups  [rbp+0E30h+var_DC0], xmm1
0x1800328ae  mov     dword ptr [rbp+0E30h+var_E84], r15d
0x1800328b2  mov     [rbp+0E30h+var_E54], r15d
0x1800328b6  mov     dword ptr [rbp+0E30h+var_E88], r15d
0x1800328ba  mov     [rbp+0E30h+var_E5C], r15d
0x1800328be  mov     [rbp+0E30h+var_940], r15d
0x1800328c5  xor     edx, edx; Val
0x1800328c7  mov     r8d, 7FCh; Size
0x1800328cd  lea     rcx, [rbp+0E30h+var_93C]; void *
0x1800328d4  call    memset_0
0x1800328d9  mov     [rbp+0E30h+var_9C0], r15d
0x1800328e0  xorps   xmm0, xmm0
0x1800328e3  xor     eax, eax
0x1800328e5  movups  [rbp+0E30h+var_9BC], xmm0
0x1800328ec  movups  [rbp+0E30h+var_9AC], xmm0
0x1800328f3  mov     [rbp+0E30h+var_99C], eax
0x1800328f9  movups  [rbp+0E30h+var_C40], xmm0
0x180032900  xorps   xmm1, xmm1
0x180032903  movdqu  [rbp+0E30h+var_D38], xmm1
0x18003290b  mov     [rbp+0E30h+var_D40], r15
0x180032912  movdqu  [rbp+0E30h+var_D28], xmm0
0x18003291a  mov     [rbp+0E30h+var_D18], r15
0x180032921  or      r15d, 0FFFFFFFFh
0x180032925  mov     [rbp+0E30h+var_D10], r15d
0x18003292c  mov     [rbp+0E30h+var_D0C], eax
0x180032932  test    cs:byte_1800AA941, 8
0x180032939  jz      short loc_18003295F
0x18003293b  mov     [rsp+0F30h+phkResult], rbx; void *
0x180032940  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180032947  lea     r8, [rsp+0F30h+dwErrorCode]; unsigned int *
0x18003294c  lea     rdx, aClientbfehandl_0; "ClientBFEHandler::PlumbPolicy"
0x180032953  lea     rcx, [rbp+0E30h+var_D40]; this
0x18003295a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18003295f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032966  lea     rdx, WPP_GLOBAL_Control
0x18003296d  mov     ebx, 1
0x180032972  cmp     rcx, rdx
0x180032975  jz      short loc_1800329B4
0x180032977  test    [rcx+1Ch], bl
0x18003297a  jz      short loc_1800329B4
0x18003297c  cmp     byte ptr [rcx+19h], 5
0x180032980  jb      short loc_1800329B4
0x180032982  cmp     r12d, 2
0x180032986  setz    al
0x180032989  test    esi, esi
0x18003298b  setnz   r9b
0x18003298f  lea     edx, [rbx+50h]
0x180032992  mov     byte ptr [rsp+0F30h+phkResult], al
0x180032996  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x18003299d  mov     rcx, [rcx+10h]
0x1800329a1  call    WPP_SF_cc
0x1800329a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329ad  lea     rdx, WPP_GLOBAL_Control
0x1800329b4  xor     esi, esi
0x1800329b6  cmp     [rsp+0F30h+var_ED0], sil
0x1800329bb  jz      loc_180032AEA
0x1800329c1  cmp     [rbp+0E30h+var_E30], rsi
0x1800329c5  jz      loc_180032AF4
0x1800329cb  mov     ebx, esi
0x1800329cd  mov     [rbp+0E30h+var_E58], 708h
0x1800329d4  mov     r12d, 58h ; 'X'
0x1800329da  mov     r8d, r12d; Size
0x1800329dd  xor     edx, edx; Val
0x1800329df  lea     rcx, [rbp+0E30h+Uuid]; void *
0x1800329e6  call    memset_0
0x1800329eb  mov     r8d, r12d; Size
0x1800329ee  xor     edx, edx; Val
0x1800329f0  lea     rcx, [rbp+0E30h+var_D00]; void *
0x1800329f7  call    memset_0
0x1800329fc  xorps   xmm0, xmm0
0x1800329ff  movups  [rbp+0E30h+var_E20], xmm0
0x180032a03  movups  [rbp+0E30h+var_E10], xmm0
0x180032a07  movups  [rbp+0E30h+var_E00], xmm0
0x180032a0b  xor     edx, edx; Val
0x180032a0d  lea     r8d, [r12+18h]; Size
0x180032a12  lea     rcx, [rbp+0E30h+var_DB0]; void *
0x180032a19  call    memset_0
0x180032a1e  xor     edx, edx; Val
0x180032a20  mov     r8d, 1E0h; Size
0x180032a26  lea     rcx, [rbp+0E30h+var_BA0]; void *
0x180032a2d  call    memset_0
0x180032a32  mov     rax, [r14+30h]
0x180032a36  mov     rax, [rax+70h]
0x180032a3a  mov     [rbp+0E30h+var_E40], rax
0x180032a3e  mov     eax, [rax+160h]
0x180032a44  lea     edx, [r12+20h]
0x180032a49  test    eax, eax
0x180032a4b  jz      short loc_180032A57
0x180032a4d  mov     ecx, eax
0x180032a4f  cmp     eax, edx
0x180032a51  cmovb   ecx, edx
0x180032a54  mov     [rbp+0E30h+var_E58], ecx
0x180032a57  lea     rax, [rsp+0F30h+hKey]
0x180032a5c  mov     [rsp+0F30h+phkResult], rax; phkResult
0x180032a61  mov     r9d, 1; samDesired
0x180032a67  xor     r8d, r8d; ulOptions
0x180032a6a  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x180032a71  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032a78  call    cs:__imp_RegOpenKeyExA
0x180032a7e  mov     [rsp+0F30h+dwErrorCode], eax
0x180032a82  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180032a89  mov     esi, 4
0x180032a8e  test    eax, eax
0x180032a90  jnz     loc_180032C3C
0x180032a96  mov     [rsp+0F30h+cbData], esi
0x180032a9a  lea     rax, [rsp+0F30h+cbData]
0x180032a9f  mov     [rsp+0F30h+lpcbData], rax; lpcbData
0x180032aa4  lea     rax, [rbp+0E30h+Data]
0x180032aa8  mov     [rsp+0F30h+phkResult], rax; lpData
0x180032aad  xor     r9d, r9d; lpType
0x180032ab0  xor     r8d, r8d; lpReserved
0x180032ab3  lea     rdx, aCustomparams; "CustomParams"
0x180032aba  mov     rcx, [rsp+0F30h+hKey]; hKey
0x180032abf  call    cs:__imp_RegQueryValueExA
0x180032ac5  mov     [rsp+0F30h+dwErrorCode], eax
0x180032ac9  test    eax, eax
0x180032acb  jnz     loc_180032C12
0x180032ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ad8  cmp     dword ptr [rbp+0E30h+Data], 1
0x180032adc  jnz     loc_180032C7E
0x180032ae2  lea     ebx, [rsi-3]
0x180032ae5  jmp     loc_180032C7E
0x180032aea  cmp     [rbp+0E30h+var_E28], rsi
0x180032aee  jnz     loc_1800329CB
0x180032af4  mov     eax, 57h ; 'W'
0x180032af9  mov     [rsp+0F30h+dwErrorCode], eax
0x180032afd  cmp     rcx, rdx
0x180032b00  jz      short loc_180032B2A
0x180032b02  test    [rcx+1Ch], bl
0x180032b05  jz      short loc_180032B2A
0x180032b07  cmp     byte ptr [rcx+19h], 2
0x180032b0b  jb      short loc_180032B2A
0x180032b0d  lea     edx, [rax-5]
0x180032b10  mov     r9d, eax
0x180032b13  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180032b1a  mov     rcx, [rcx+10h]
0x180032b1e  call    WPP_SF_d
0x180032b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b2a  test    cs:byte_1800AA941, 4
0x180032b31  jz      loc_180032BE5
0x180032b37  mov     word ptr [rbp+0E30h+var_9C0], si
0x180032b3e  mov     rax, [r14+30h]
0x180032b42  test    rax, rax
0x180032b45  jz      short loc_180032B5A
0x180032b47  mov     rax, [rax+70h]
0x180032b4b  test    rax, rax
0x180032b4e  jz      short loc_180032B5A
0x180032b50  cmp     [rax+10h], rsi
0x180032b54  jz      short loc_180032B5A
0x180032b56  mov     r15d, [rax+10h]
0x180032b5a  mov     edx, r15d
0x180032b5d  lea     rcx, [rbp+0E30h+var_9C0]
0x180032b64  call    ConvertPortNoToString
0x180032b69  test    cs:byte_1800AA941, 4
0x180032b70  jz      short loc_180032BDE
0x180032b72  mov     rcx, [r14+30h]
0x180032b76  lea     rax, [rcx+70h]
0x180032b7a  test    rcx, rcx
0x180032b7d  jz      short loc_180032BA9
0x180032b7f  mov     rdx, [rax]
0x180032b82  test    rdx, rdx
0x180032b85  jz      short loc_180032B90
0x180032b87  lea     rcx, [rdx+0A7Eh]
0x180032b8e  jmp     short loc_180032B98
0x180032b90  test    rcx, rcx
0x180032b93  jz      short loc_180032BA9
0x180032b95  mov     rcx, rsi
0x180032b98  mov     rdx, [rax]
0x180032b9b  test    rdx, rdx
0x180032b9e  jz      short loc_180032BAC
0x180032ba0  lea     r9, [rdx+848h]
0x180032ba7  jmp     short loc_180032BB3
0x180032ba9  mov     rcx, rsi
0x180032bac  lea     r9, [rbp+0E30h+var_C40]
0x180032bb3  lea     rax, [rbp+0E30h+var_9C0]
0x180032bba  mov     [rsp+0F30h+lpcbData], rax
0x180032bbf  mov     [rsp+0F30h+phkResult], rcx
0x180032bc4  lea     r8, aInvalidParam; "Invalid param"
0x180032bcb  lea     rdx, RasVpnIkeParamTraceError
0x180032bd2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180032bd9  call    McTemplateU0zjzz_EventWriteTransfer
  ... truncated ...
```
