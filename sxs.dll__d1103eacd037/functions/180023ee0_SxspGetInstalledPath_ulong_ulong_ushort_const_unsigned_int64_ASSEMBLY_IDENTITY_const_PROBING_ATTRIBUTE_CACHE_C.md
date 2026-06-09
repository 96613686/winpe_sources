# SxspGetInstalledPath(ulong,ulong,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)

- ea: `0x180023ee0`
- end: `0x180025ded`
- name: `?SxspGetInstalledPath@@YAHKKPEBG_KPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `7949`
- prototype: `__int64 __fastcall(int, int, int, int, struct _ASSEMBLY_IDENTITY *, __int64, __int64)`
- caller_count: `5`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d4d0`
- `0x180023320`
- `0x18002b7e0`
- `0x18002df40`
- `0x180058284`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180019740`
- `0x18001c2c8`
- `0x18001c320`
- `0x18001d988`
- `0x18001e5c0`
- `0x180022f60`
- `0x180022f90`
- `0x180023260`
- `0x180023ee0`
- `0x1800265b0`
- `0x18002c760`
- `0x18002faa4`
- `0x180030480`
- `0x180032350`
- `0x18003e310`
- `0x18004d550`
- `0x18005b8a0`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180024363`
- `ntdll!RtlPopFrame` at `0x180024552`
- `ntdll!RtlPopFrame` at `0x1800246ec`
- `ntdll!RtlPopFrame` at `0x18002488f`
- `ntdll!RtlPopFrame` at `0x180024a15`
- `ntdll!RtlPopFrame` at `0x180024b2f`
- `ntdll!RtlPopFrame` at `0x180024eb1`
- `ntdll!RtlPopFrame` at `0x180025301`
- `ntdll!RtlPopFrame` at `0x180025a7a`
- `ntdll!RtlPopFrame` at `0x180025aa7`
- `ntdll!RtlPopFrame` at `0x180025b1b`
- `ntdll!RtlPopFrame` at `0x180025b48`
- `ntdll!RtlPopFrame` at `0x180025ba0`
- `ntdll!RtlPopFrame` at `0x180025bcd`
- `ntdll!RtlPopFrame` at `0x180025c4f`
- `ntdll!RtlPopFrame` at `0x180025c7c`
- `ntdll!RtlPopFrame` at `0x180024363`
- `ntdll!RtlPopFrame` at `0x180024552`
- `ntdll!RtlPopFrame` at `0x1800246ec`
- `ntdll!RtlPopFrame` at `0x18002488f`
- `ntdll!RtlPopFrame` at `0x180024a15`
- `ntdll!RtlPopFrame` at `0x180024b2f`
- `ntdll!RtlPopFrame` at `0x180024eb1`
- `ntdll!RtlPopFrame` at `0x180025301`
- `ntdll!RtlPopFrame` at `0x180025a7a`
- `ntdll!RtlPopFrame` at `0x180025aa7`
- `ntdll!RtlPopFrame` at `0x180025b1b`
- `ntdll!RtlPopFrame` at `0x180025b48`
- `ntdll!RtlPopFrame` at `0x180025ba0`
- `ntdll!RtlPopFrame` at `0x180025bcd`
- `ntdll!RtlPopFrame` at `0x180025c4f`
- `ntdll!RtlPopFrame` at `0x180025c7c`
- `ntdll!RtlPushFrame` at `0x180023f97`
- `ntdll!RtlPushFrame` at `0x1800241de`
- `ntdll!RtlPushFrame` at `0x1800243f7`
- `ntdll!RtlPushFrame` at `0x18002493e`
- `ntdll!RtlPushFrame` at `0x180024a87`
- `ntdll!RtlPushFrame` at `0x180024bb5`
- `ntdll!RtlPushFrame` at `0x180023f97`
- `ntdll!RtlPushFrame` at `0x1800241de`
- `ntdll!RtlPushFrame` at `0x1800243f7`
- `ntdll!RtlPushFrame` at `0x18002493e`
- `ntdll!RtlPushFrame` at `0x180024a87`
- `ntdll!RtlPushFrame` at `0x180024bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002477f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002576b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002587d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002477f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002576b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002587d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025bb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025dd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002418a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024320`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800243a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002450a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800245a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800245cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800245f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024625`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800246b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800247b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800247ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024835`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800248d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024966`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800249df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024af9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024b52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024d73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024dab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024e7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024ed0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024f0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024fad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025007`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800250b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002510b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002515d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025249`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800253d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800254a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800254c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800254f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800255c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002560a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800256fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025899`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800258f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800259ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025a13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025aec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025c1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002418a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024320`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800243a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002450a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800245a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800245cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800245f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024625`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800246b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800247b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800247ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024835`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800248d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024966`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800249df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024af9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024b52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024c5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024d73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024dab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024e7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024ed0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024f0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024fad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025007`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800250b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002510b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002515d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025249`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800253d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800254a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800254c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800254f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800255c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002560a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800256fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025899`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800258f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800259ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025a13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025aec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025c1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025d99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002479a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800247d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002481f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002479a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800247d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002481f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024ae3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024bfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024e32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024ae3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024bfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024e32`

## string_xrefs

- `0x180024ad5`: `Software\Microsoft\Windows\CurrentVersion\SideBySide\Winners`
- `0x180025509`: `.manifest`
- `0x18002546e`: `manifests`

## pseudocode

```c
__int64 __fastcall SxspGetInstalledPath(
        int a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        struct _ASSEMBLY_IDENTITY *a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v8; // rbx
  HKEY v9; // rdi
  struct _ASSEMBLY_IDENTITY *v10; // rsi
  unsigned __int16 *v12; // r13
  char v13; // r14
  const char *v14; // rcx
  unsigned int v15; // r11d
  unsigned int v16; // ebx
  __int64 v17; // r15
  __int64 v18; // rax
  unsigned int v19; // ecx
  unsigned int v20; // r8d
  _QWORD *v21; // r14
  unsigned __int64 v22; // r9
  unsigned __int16 *v23; // r10
  __int64 v24; // rax
  const wchar_t *v25; // rdx
  wchar_t *v26; // rsi
  int v27; // ecx
  int v28; // eax
  int v29; // ecx
  __int64 v30; // rbx
  _QWORD *v31; // r11
  unsigned __int64 v32; // r9
  const wchar_t *v33; // rdx
  unsigned __int16 *v34; // r10
  __int64 v35; // rax
  wchar_t *v36; // r8
  int v37; // eax
  int v38; // ecx
  int v39; // ebx
  unsigned __int64 v40; // r14
  unsigned int v41; // r10d
  __int64 v42; // r15
  unsigned int v43; // r11d
  __int64 v44; // rax
  unsigned int v45; // ecx
  unsigned int v46; // r8d
  _QWORD *v47; // r14
  unsigned __int64 v48; // r9
  const unsigned __int16 *v49; // rdx
  unsigned __int16 *v50; // rbx
  __int64 v51; // rax
  const unsigned __int16 *v52; // rsi
  int v53; // ecx
  int v54; // eax
  int v55; // ecx
  __int64 v56; // rbx
  _QWORD *v57; // r11
  unsigned __int64 v58; // r9
  const unsigned __int16 *v59; // rdx
  unsigned __int16 *v60; // r10
  __int64 v61; // rax
  const unsigned __int16 *v62; // r8
  int v63; // eax
  int v64; // ecx
  int v65; // ebx
  unsigned __int16 *v66; // rsi
  unsigned __int64 v67; // r14
  int v68; // eax
  struct _ASSEMBLY_IDENTITY *v69; // r13
  __int64 v70; // r12
  unsigned int v71; // r14d
  HKEY v72; // r13
  int v73; // ebx
  unsigned int v74; // esi
  DWORD v75; // ebx
  LSTATUS v76; // eax
  DWORD v77; // ebx
  LSTATUS v78; // eax
  DWORD v79; // eax
  HKEY v80; // rcx
  DWORD v81; // ebx
  LSTATUS v82; // eax
  void *v84; // r15
  unsigned __int64 v85; // rbx
  unsigned __int64 v86; // r14
  LPCWSTR v87; // r14
  size_t v88; // rsi
  size_t v89; // rsi
  int v90; // ebx
  LSTATUS v91; // eax
  int v92; // ebx
  const WCHAR *v93; // rbx
  LSTATUS v94; // eax
  unsigned int i; // edx
  __int64 v96; // r12
  unsigned int v97; // r10d
  unsigned int v98; // esi
  __int64 v99; // rax
  unsigned int v100; // ecx
  unsigned int v101; // r8d
  _QWORD *v102; // rbx
  unsigned __int64 v103; // r9
  const wchar_t *v104; // rdx
  unsigned __int16 *v105; // r11
  __int64 v106; // rax
  wchar_t *v107; // r14
  int v108; // ecx
  int v109; // eax
  int v110; // ecx
  unsigned int v111; // esi
  unsigned int v112; // r14d
  const WCHAR *v113; // rbx
  LSTATUS v114; // eax
  unsigned int j; // edx
  HKEY v116; // rax
  int v117; // ebx
  __int64 v118; // rsi
  __int16 v119; // ax
  __int64 v120; // rbx
  __int64 v121; // rsi
  __int64 v122; // rsi
  __int64 v123; // r14
  unsigned __int16 *v124; // rax
  HKEY v125; // r12
  unsigned __int64 v126; // rsi
  size_t v127; // rsi
  const WCHAR *v128; // rax
  HKEY v129; // rax
  __int64 v130; // rbx
  bool v131; // zf
  DWORD v132; // ecx
  int v133; // eax
  __int64 v134; // rcx
  DWORD LastError; // eax
  DWORD v136; // eax
  DWORD v137; // eax
  DWORD v138; // eax
  unsigned int v139; // edx
  DWORD v140; // eax
  DWORD v141; // eax
  DWORD v142; // eax
  DWORD v143; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  __int64 v145; // [rsp+28h] [rbp-D8h]
  char v146; // [rsp+50h] [rbp-B0h]
  bool v147; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v148; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v149; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v150; // [rsp+78h] [rbp-88h]
  unsigned __int64 v151; // [rsp+80h] [rbp-80h]
  __int64 v152; // [rsp+88h] [rbp-78h] BYREF
  int v153; // [rsp+90h] [rbp-70h]
  __int64 v154; // [rsp+98h] [rbp-68h]
  __int64 v155; // [rsp+A0h] [rbp-60h]
  HKEY v156; // [rsp+A8h] [rbp-58h] BYREF
  struct _ASSEMBLY_IDENTITY *v157; // [rsp+B0h] [rbp-50h]
  __int64 v158; // [rsp+B8h] [rbp-48h]
  __int64 v159; // [rsp+C0h] [rbp-40h]
  int v160; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v161; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v162; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v163; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v164; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v165; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v166; // [rsp+100h] [rbp+0h]
  unsigned __int64 v167; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v168; // [rsp+110h] [rbp+10h] BYREF
  char v169[8]; // [rsp+118h] [rbp+18h] BYREF
  void *v170; // [rsp+120h] [rbp+20h]
  __int64 v171; // [rsp+128h] [rbp+28h]
  __int64 v172; // [rsp+130h] [rbp+30h]
  HKEY v173; // [rsp+138h] [rbp+38h] BYREF
  HKEY v174; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v175[2]; // [rsp+148h] [rbp+48h] BYREF
  char *v176; // [rsp+158h] [rbp+58h]
  _QWORD v177[2]; // [rsp+160h] [rbp+60h] BYREF
  void *Src; // [rsp+170h] [rbp+70h]
  __int64 v179; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int16 *v180; // [rsp+180h] [rbp+80h] BYREF
  int v181; // [rsp+188h] [rbp+88h] BYREF
  HKEY v182; // [rsp+190h] [rbp+90h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+198h] [rbp+98h] BYREF
  __int64 v184; // [rsp+1B0h] [rbp+B0h]
  int v185; // [rsp+1B8h] [rbp+B8h]
  int *v186; // [rsp+1C0h] [rbp+C0h]
  struct _TEB_ACTIVE_FRAME v187; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v188; // [rsp+1E0h] [rbp+E0h]
  int v189; // [rsp+1E8h] [rbp+E8h]
  unsigned __int16 **v190; // [rsp+1F0h] [rbp+F0h]
  struct _TEB_ACTIVE_FRAME v191; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v192; // [rsp+210h] [rbp+110h]
  __int64 v193; // [rsp+218h] [rbp+118h]
  unsigned __int16 **v194; // [rsp+220h] [rbp+120h]
  __int64 v195; // [rsp+228h] [rbp+128h]
  void **v196; // [rsp+230h] [rbp+130h] BYREF
  int v197; // [rsp+238h] [rbp+138h]
  LPCWSTR InlineBuffer; // [rsp+240h] [rbp+140h]
  __int64 v199; // [rsp+248h] [rbp+148h]
  __int64 v200; // [rsp+250h] [rbp+150h]
  __int16 v201; // [rsp+258h] [rbp+158h] BYREF
  void **v202; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v203; // [rsp+2E8h] [rbp+1E8h]
  LPCWSTR lpSubKey; // [rsp+2F0h] [rbp+1F0h]
  unsigned __int64 v205; // [rsp+2F8h] [rbp+1F8h]
  unsigned __int64 v206; // [rsp+300h] [rbp+200h]
  __int16 v207; // [rsp+308h] [rbp+208h] BYREF
  char v208; // [rsp+510h] [rbp+410h] BYREF
  char v209; // [rsp+630h] [rbp+530h] BYREF

  v8 = a6;
  v9 = 0;
  v10 = a5;
  v179 = a7;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D300;
  v153 = a1;
  v186 = &v181;
  v159 = a4;
  v158 = a3;
  v149 = a2;
  v161 = a6;
  v157 = a5;
  v181 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v184 = 544438355;
  v185 = 1215;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v180 = 0;
  v150 = 0;
  v165 = 0;
  v12 = 0;
  v154 = 0;
  v168 = 0;
  v155 = 0;
  v167 = 0;
  v151 = 0;
  v148 = 0;
  Src = &v208;
  v202 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  v173 = 0;
  v163 = 0;
  v166 = 0;
  v164 = 0;
  v174 = 0;
  v162 = 0;
  v177[0] = 0;
  v177[1] = 280;
  v203 = 0;
  lpSubKey = 0;
  v205 = 0;
  v206 = 0;
  v207 = 0;
  lpSubKey = (LPCWSTR)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v202);
  v205 = ((__int64 (__fastcall *)(void ***))v202[3])(&v202);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0((void *)lpSubKey, 0, 2 * v205);
  v13 = 0;
  v182 = 0;
  v152 = 0;
  v156 = 0;
  v196 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  v197 = 0;
  InlineBuffer = 0;
  v199 = 0;
  v200 = 0;
  v201 = 0;
  InlineBuffer = (LPCWSTR)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v196);
  v199 = ((__int64 (__fastcall *)(void ***))v196[3])(&v196);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0((void *)InlineBuffer, 0, 2 * v199);
  v14 = 0;
  v170 = 0;
  v171 = 0;
  v176 = &v209;
  v172 = 0;
  v147 = 0;
  v146 = 0;
  v160 = 0;
  v175[0] = 0;
  v175[1] = 280;
  if ( v149 - 1 > 1 )
  {
    v185 = 1258;
LABEL_265:
    FusionpTraceParameterCheck(0);
    SetLastError(0x57u);
    v72 = 0;
    goto LABEL_227;
  }
  if ( !a5 )
  {
    v185 = 1260;
    goto LABEL_265;
  }
  if ( (a1 & 0xFFFFFFF7) != 0 )
  {
    v185 = 1262;
    goto LABEL_265;
  }
  if ( !a4 )
  {
    v185 = 1264;
    goto LABEL_265;
  }
  if ( a6 )
  {
    if ( (*(_BYTE *)a6 & 1) != 0 )
    {
      v12 = *(unsigned __int16 **)(a6 + 8);
      v40 = *(_QWORD *)(a6 + 16);
    }
    else
    {
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            0,
                            a5,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                            (const unsigned __int16 **)&v180,
                            &v164) )
      {
        *v186 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006DF48);
        v70 = v179;
        v72 = 0;
        goto LABEL_93;
      }
      v12 = v180;
      v40 = v164;
      *(_DWORD *)a6 |= 1u;
      *(_QWORD *)(a6 + 8) = v12;
      *(_QWORD *)(a6 + 16) = v40;
    }
  }
  else
  {
    SetLastError(0);
    LODWORD(v180) = 0;
    v190 = &v180;
    v187.Flags = 1;
    v187.Previous = 0;
    v187.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CDC0;
    v188 = 544438355;
    v189 = 153;
    RtlPushFrame(&v187);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    v15 = 0;
    v16 = *((_DWORD *)a5 + 4);
    v17 = *((_QWORD *)a5 + 5);
    while ( v15 < v16 )
    {
      v18 = v15;
      v19 = (v16 + v15) >> 1;
      if ( v19 != v16 )
        v18 = v19;
      v20 = v18;
      v21 = *(_QWORD **)(v17 + 8 * v18);
      if ( !v21[1] )
      {
        v22 = v21[2];
        v23 = (unsigned __int16 *)v21[5];
        v24 = v22;
        v25 = L"name";
        if ( v22 >= 4 )
          v24 = 4;
        v26 = &aName[v24];
        while ( v25 < v26 )
        {
          v27 = *v25++;
          v28 = *v23++;
          v29 = v27 - v28;
          if ( v29 )
            goto LABEL_37;
        }
        if ( v22 > 4 )
        {
          v29 = 1;
        }
        else
        {
          if ( v22 == 4 )
          {
            if ( v21 )
            {
              if ( !v20 )
                goto LABEL_216;
              do
              {
                v30 = v20 - 1;
                v31 = *(_QWORD **)(v17 + 8 * v30);
                if ( v31[1] )
                  break;
                v32 = v31[2];
                v33 = L"name";
                v34 = (unsigned __int16 *)v31[5];
                v35 = v32;
                if ( v32 >= 4 )
                  v35 = 4;
                v36 = &aName[v35];
                while ( v33 < v36 )
                {
                  v37 = *v34++;
                  v38 = *v33++;
                  if ( v38 != v37 )
                    goto LABEL_215;
                }
                if ( v32 != 4 )
                  break;
                v20 = v30;
                v21 = *(_QWORD **)(v17 + 8 * v30);
              }
              while ( (_DWORD)v30 );
LABEL_215:
              v9 = 0;
              if ( v21 )
              {
LABEL_216:
                v12 = (unsigned __int16 *)v21[6];
                v39 = 1;
                v40 = v21[3];
                LODWORD(v180) = 1;
                goto LABEL_41;
              }
            }
            break;
          }
          v29 = -1;
        }
LABEL_37:
        if ( v29 >= 0 )
          goto LABEL_38;
        if ( v16 != v20 )
        {
          v16 = v20;
          continue;
        }
        break;
      }
LABEL_38:
      if ( v15 == v20 )
        break;
      v15 = v20;
    }
    SetLastError(0x490u);
    *(_DWORD *)v190 = 0;
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18006D3E0);
    v39 = (int)v180;
    v40 = v166;
LABEL_41:
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *(_DWORD *)v190 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        LastError = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
      }
    }
    RtlPopFrame(&v187);
    if ( !v39 )
    {
      *v186 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075B90);
      v72 = 0;
      v13 = 0;
      goto LABEL_228;
    }
    v8 = v161;
    v10 = v157;
  }
  if ( !v12 || !v40 )
  {
    v132 = 1359;
LABEL_226:
    SetLastError(v132);
    v72 = 0;
    v13 = 0;
LABEL_227:
    *v186 = 0;
    goto LABEL_228;
  }
  if ( v8 )
  {
    if ( (*(_BYTE *)v8 & 2) != 0 )
    {
      v66 = *(unsigned __int16 **)(v8 + 24);
      v67 = *(_QWORD *)(v8 + 32);
      v150 = v66;
      v151 = v67;
    }
    else
    {
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            0,
                            v10,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_version,
                            (const unsigned __int16 **)&v165,
                            &v148) )
      {
        *v186 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006FD30);
        v70 = v179;
        v13 = 0;
        v72 = 0;
        goto LABEL_93;
      }
      v66 = v165;
      v67 = v148;
      *(_DWORD *)v8 |= 2u;
      v150 = v66;
      *(_QWORD *)(v8 + 24) = v66;
      v151 = v67;
      *(_QWORD *)(v8 + 32) = v67;
    }
  }
  else
  {
    SetLastError(0);
    LODWORD(v180) = 0;
    v190 = &v180;
    v187.Flags = 1;
    v187.Previous = 0;
    v187.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CDC0;
    v188 = 544438355;
    v189 = 153;
    RtlPushFrame(&v187);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    v41 = 0;
    v42 = *((_QWORD *)v10 + 5);
    v43 = *((_DWORD *)v10 + 4);
    while ( v41 < v43 )
    {
      v44 = v41;
      v45 = (v43 + v41) >> 1;
      if ( v45 != v43 )
        v44 = v45;
      v46 = v44;
      v47 = *(_QWORD **)(v42 + 8 * v44);
      if ( !v47[1] )
      {
        v48 = v47[2];
        v49 = L"version";
        v50 = (unsigned __int16 *)v47[5];
        v51 = v48;
        if ( v48 >= 7 )
          v51 = 7;
        v52 = &aVersion[v51];
        while ( v49 < v52 )
        {
          v53 = *v49++;
          v54 = *v50++;
          v55 = v53 - v54;
          if ( v55 )
            goto LABEL_72;
        }
        if ( v48 > 7 )
        {
          v55 = 1;
        }
        else
        {
          if ( v48 == 7 )
          {
            if ( v47 )
            {
              if ( !v46 )
                goto LABEL_223;
              do
              {
                v56 = v46 - 1;
                v57 = *(_QWORD **)(v42 + 8 * v56);
                if ( v57[1] )
                  break;
                v58 = v57[2];
                v59 = L"version";
                v60 = (unsigned __int16 *)v57[5];
                v61 = v58;
                if ( v58 >= 7 )
                  v61 = 7;
                v62 = &aVersion[v61];
                while ( v59 < v62 )
                {
                  v63 = *v60++;
                  v64 = *v59++;
                  if ( v64 != v63 )
                    goto LABEL_222;
                }
                if ( v58 != 7 )
                  break;
                v46 = v56;
                v47 = *(_QWORD **)(v42 + 8 * v56);
              }
              while ( (_DWORD)v56 );
LABEL_222:
              if ( v47 )
              {
LABEL_223:
                v66 = (unsigned __int16 *)v47[6];
                v65 = 1;
                v67 = v47[3];
                v151 = v67;
                v150 = v66;
                LODWORD(v180) = 1;
                goto LABEL_76;
              }
            }
            break;
          }
          v55 = -1;
        }
LABEL_72:
        if ( v55 >= 0 )
          goto LABEL_73;
        if ( v43 != v46 )
        {
          v43 = v46;
          continue;
        }
        break;
      }
LABEL_73:
      if ( v41 == v46 )
        break;
      v41 = v46;
    }
    SetLastError(0x490u);
    *(_DWORD *)v190 = 0;
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18006D3E0);
    v65 = (int)v180;
    v66 = v150;
    v67 = v151;
LABEL_76:
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *(_DWORD *)v190 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        v136 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v136, 0);
      }
    }
    RtlPopFrame(&v187);
    if ( !v65 )
    {
      *v186 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075B70);
      v72 = 0;
      v13 = 0;
      goto LABEL_228;
    }
    v8 = v161;
  }
  if ( !v66 || !v67 )
  {
    v185 = 1330;
    FusionpTraceParameterCheck(v14);
    v132 = 87;
    goto LABEL_226;
  }
  if ( !v8 )
  {
    SetLastError(0);
    v69 = v157;
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          v157,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_language,
                          (const unsigned __int16 **)&v163,
                          &v162) )
    {
      *v186 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180070190);
      v70 = v179;
      v13 = 0;
      v72 = 0;
      goto LABEL_93;
    }
    SetLastError(0);
    if ( (unsigned int)SxspGetAssemblyIdentityAttributeValue(
                         1u,
                         v69,
                         (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_processorArchitecture,
                         (const unsigned __int16 **)&v173,
                         (unsigned __int64 *)&v174) )
    {
      SetLastError(0);
      if ( (unsigned int)SxspGetAssemblyIdentityAttributeValue(
                           1u,
                           v69,
                           (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_publicKeyToken,
                           (const unsigned __int16 **)&v168,
                           &v167) )
        goto LABEL_86;
      *v186 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075B10);
      v13 = 0;
      v72 = 0;
    }
    else
    {
      *v186 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075B30);
      v13 = 0;
      v72 = 0;
    }
    goto LABEL_228;
  }
  v68 = *(_DWORD *)v8;
  if ( (*(_DWORD *)v8 & 0x10) == 0 )
  {
    SetLastError(0);
    v69 = v157;
    if ( (unsigned int)SxspGetAssemblyIdentityAttributeValue(
                         1u,
                         v157,
                         (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_language,
                         (const unsigned __int16 **)&v163,
                         &v162) )
    {
      v124 = v163;
      *(_DWORD *)v8 |= 0x10u;
      *(_QWORD *)(v8 + 72) = v124;
      *(_QWORD *)(v8 + 80) = v162;
      v68 = *(_DWORD *)v8;
      goto LABEL_84;
    }
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075B50);
    v13 = 0;
    v72 = 0;
LABEL_228:
    v70 = v179;
    goto LABEL_93;
  }
  v69 = v157;
LABEL_84:
  if ( (v68 & 4) == 0 )
  {
    SetLastError(0);
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          v69,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_processorArchitecture,
                          (const unsigned __int16 **)&v173,
                          (unsigned __int64 *)&v174) )
    {
      *v186 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180070210);
      v70 = v179;
      v13 = 0;
      v72 = 0;
      goto LABEL_93;
    }
    v129 = v173;
    *(_DWORD *)v8 |= 4u;
    *(_QWORD *)(v8 + 40) = v129;
    *(_QWORD *)(v8 + 48) = v174;
    v68 = *(_DWORD *)v8;
  }
  if ( (v68 & 8) == 0 )
  {
    SetLastError(0);
    v187.Flags = 1;
    LODWORD(v180) = 0;
    v187.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CDC0;
    v187.Previous = 0;
    v190 = &v180;
    v188 = 544438355;
    v189 = 153;
    CFrame::BaseEnter((CFrame *)&v187);
    v96 = *((_QWORD *)v69 + 5);
    v97 = *((_DWORD *)v69 + 4);
    v98 = 0;
    v195 = 0;
    v194 = (unsigned __int16 **)L"publicKeyToken";
    *(_QWORD *)&v191.Flags = 0;
    v192 = 0;
    v193 = 0;
    v191.Previous = 0;
    v191.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)14;
    while ( v98 < v97 )
    {
      v99 = v98;
      v100 = (v97 + v98) >> 1;
      if ( v100 != v97 )
        v99 = v100;
      v101 = v99;
      v102 = *(_QWORD **)(v96 + 8 * v99);
      if ( !v102[1] )
      {
        v103 = v102[2];
        v104 = L"publicKeyToken";
        v105 = (unsigned __int16 *)v102[5];
        v106 = v103;
        if ( v103 >= 0xE )
          v106 = 14;
        v107 = &aPublickeytoken[v106];
        while ( v104 < v107 )
        {
          v108 = *v104++;
          v109 = *v105++;
          v110 = v108 - v109;
          if ( v110 )
            goto LABEL_231;
        }
        if ( v103 > 0xE )
        {
          v110 = 1;
        }
        else
        {
          if ( v103 == 14 )
          {
            if ( v102 )
            {
              if ( !v101 )
                goto LABEL_196;
              do
              {
                v121 = v101 - 1;
                if ( SxspCompareAssemblyIdentityAttributes(
                       3u,
                       (const struct _ASSEMBLY_IDENTITY_ATTRIBUTE *)&v191,
                       *(const struct _ASSEMBLY_IDENTITY_ATTRIBUTE **)(v96 + 8 * v121)) != 2 )
                  break;
                v102 = *(_QWORD **)(v96 + 8 * v121);
                v101 = v121;
              }
              while ( (_DWORD)v121 );
              if ( v102 )
              {
LABEL_196:
                v122 = v102[6];
                v123 = v102[3];
                goto LABEL_218;
              }
            }
            break;
          }
          v110 = -1;
        }
LABEL_231:
        if ( v110 >= 0 )
          goto LABEL_232;
        if ( v97 != v101 )
        {
          v97 = v101;
          continue;
        }
        break;
      }
LABEL_232:
      if ( v98 == v101 )
        break;
      v98 = v101;
    }
    v122 = v154;
    v123 = v155;
LABEL_218:
    LODWORD(v180) = 1;
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *(_DWORD *)v190 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        v137 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v137, 0);
      }
    }
    RtlPopFrame(&v187);
    v130 = v161;
    v131 = v122 == 0;
    *(_QWORD *)(v161 + 56) = v122;
    v66 = v150;
    *(_QWORD *)(v130 + 64) = v123;
    v67 = v151;
    if ( !v131 )
      *(_DWORD *)v130 |= 8u;
  }
LABEL_86:
  SetLastError(0);
  if ( !(unsigned int)SxspGenerateKeyform(1u, v69, (struct _LUNICODE_STRING *)v177) )
  {
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075AF0);
    v13 = 0;
    v72 = 0;
    goto LABEL_228;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGenerateKeyform(0, v69, (struct _LUNICODE_STRING *)v175) )
  {
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075AD0);
    v13 = 0;
    v72 = 0;
    goto LABEL_228;
  }
  SetLastError(0);
  if ( !(unsigned int)CFusionParser::ParseVersion((union _ASSEMBLY_VERSION *)&v152, v66, v67, &v147) )
  {
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075AB0);
    v13 = 0;
    v72 = 0;
    goto LABEL_228;
  }
  if ( !v147 )
  {
    SetLastError(0x36C1u);
    *v186 = 0;
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180075A90);
    v13 = 0;
    v72 = 0;
    goto LABEL_228;
  }
  SetLastError(0);
  v70 = v179;
  v71 = v149;
  if ( !(unsigned int)SxspGetFusionRootInstalledPath(0, v149, v158, v159, v69, v177, v175, &v152, v179) )
  {
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075A70);
    v13 = 0;
    v72 = 0;
    goto LABEL_93;
  }
  if ( **(_WORD **)(v70 + 16) )
  {
    v72 = 0;
    v13 = 1;
    v181 = 1;
    goto LABEL_93;
  }
  if ( (v153 & 8) == 0 )
  {
    v72 = 0;
    LODWORD(v84) = 0;
    goto LABEL_182;
  }
  SetLastError(0);
  v84 = Src;
  v191.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign'::`2'::__stc;
  v72 = 0;
  v85 = v177[0] >> 1;
  v194 = &v180;
  LODWORD(v180) = 0;
  v191.Flags = 1;
  v191.Previous = 0;
  v192 = 544438355;
  LODWORD(v193) = 210;
  RtlPushFrame(&v191);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( v203 )
  {
    SetLastError(0x54Fu);
    LODWORD(v84) = 0;
    *(_DWORD *)v194 = 0;
    goto LABEL_132;
  }
  SetLastError(0);
  v86 = v85 + 1;
  if ( v85 + 1 > v205 )
  {
    SetLastError(0);
    if ( v86 > v205 )
    {
      v173 = 0;
      if ( !((unsigned int (__fastcall *)(void ***, unsigned __int64, HKEY *))*v202)(&v202, v85 + 1, &v173) )
      {
        LODWORD(v84) = 0;
        *(_DWORD *)v194 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign'::`41'::__callsite);
        goto LABEL_132;
      }
      v125 = v173;
      if ( lpSubKey )
      {
        v126 = v206;
        if ( v206 >= v86 )
          v126 = v85;
        v127 = 2 * v126;
        memcpy_0(v173, lpSubKey, v127);
        *(_WORD *)((char *)v125 + v127) = 0;
      }
      else
      {
        *(_WORD *)v173 = 0;
      }
      if ( lpSubKey )
      {
        v128 = (const WCHAR *)((__int64 (__fastcall *)(void ***))v202[2])(&v202);
        if ( lpSubKey != v128 )
          ((void (__fastcall *)(void ***))v202[1])(&v202);
      }
      v70 = v179;
      lpSubKey = (LPCWSTR)v173;
      v205 = v85 + 1;
    }
  }
  SetLastError(0);
  if ( v205 )
  {
    v87 = lpSubKey;
    if ( v84 )
    {
      if ( v85 >= v205 )
        v88 = v205 - 1;
      else
        v88 = v85;
      v89 = v88;
      memcpy_0((void *)lpSubKey, v84, v89 * 2);
      LODWORD(v84) = 0;
      v87[v89] = 0;
    }
    else
    {
      *lpSubKey = 0;
    }
  }
  else
  {
    LODWORD(v84) = 0;
  }
  v206 = v85;
  SetLastError(0);
  *(_DWORD *)v194 = 1;
LABEL_132:
  v90 = *(_DWORD *)v194;
  if ( !g_FusionEnterExitTracingEnabled )
  {
    RtlPopFrame(&v191);
    if ( v90 )
      goto LABEL_134;
LABEL_305:
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006D8C0);
    goto LABEL_103;
  }
  if ( !v90 )
  {
    v138 = GetLastError();
    FusionpTraceCallWin32UnsuccessfulExit(v138, 0);
    RtlPopFrame(&v191);
    goto LABEL_305;
  }
  FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&v191);
LABEL_134:
  SetLastError(0);
  LODWORD(v180) = 0;
  v191.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D360;
  v191.Flags = 1;
  v194 = &v180;
  v191.Previous = 0;
  v192 = 544438355;
  LODWORD(v193) = 975;
  RtlPushFrame(&v191);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( v182 )
  {
    v182 = 0;
    COperatorFRegCloseKey::operator()();
  }
  v148 = 0x300000002LL;
  v91 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\SideBySide\\Winners",
          0,
          0x20119u,
          &v182);
  if ( v91 )
  {
    v139 = 0;
    while ( *((_DWORD *)&v148 + v139) != v91 )
    {
      if ( ++v139 >= 2 )
      {
        if ( v139 != 2 )
          break;
        SetLastError(v91);
        FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180075D70);
        goto LABEL_140;
      }
    }
  }
  SetLastError(0);
  *(_DWORD *)v194 = 1;
LABEL_140:
  v92 = *(_DWORD *)v194;
  if ( !g_FusionEnterExitTracingEnabled )
  {
    RtlPopFrame(&v191);
    if ( v92 )
      goto LABEL_142;
LABEL_314:
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075A50);
    goto LABEL_103;
  }
  if ( !v92 )
  {
    v140 = GetLastError();
    FusionpTraceCallWin32UnsuccessfulExit(v140, 0);
    RtlPopFrame(&v191);
    goto LABEL_314;
  }
  FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&v191);
LABEL_142:
  if ( !v182 )
  {
    SetLastError(0x3712u);
    *v186 = 0;
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18006FE90);
    goto LABEL_103;
  }
  SetLastError(0);
  v93 = lpSubKey;
  v194 = &v180;
  LODWORD(v180) = 0;
  v191.Flags = 1;
  v191.Previous = 0;
  v191.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D380;
  v192 = 544438355;
  LODWORD(v193) = 507;
  RtlPushFrame(&v191);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v173 = 0;
  v148 = 0x300000002LL;
  v94 = RegOpenKeyExW(v182, v93, 0, 0x20119u, &v173);
  if ( v94 )
  {
    for ( i = 0; i < 2; ++i )
    {
      if ( *((_DWORD *)&v148 + i) == v94 )
      {
        v9 = 0;
        v173 = 0;
        goto LABEL_98;
      }
    }
    if ( i != 2 )
      goto LABEL_97;
    SetLastError(v94);
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007CA20);
  }
  else
  {
LABEL_97:
    v9 = v173;
LABEL_98:
    SetLastError(0);
    *(_DWORD *)v194 = 1;
  }
  v73 = *(_DWORD *)v194;
  if ( !g_FusionEnterExitTracingEnabled )
  {
    RtlPopFrame(&v191);
    if ( v73 )
      goto LABEL_101;
LABEL_319:
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075A30);
    v72 = 0;
    goto LABEL_103;
  }
  if ( !v73 )
  {
    v141 = GetLastError();
    FusionpTraceCallWin32UnsuccessfulExit(v141, 0);
    RtlPopFrame(&v191);
    goto LABEL_319;
  }
  FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&v191);
LABEL_101:
  if ( !v9 )
  {
    v72 = 0;
    v181 = 1;
LABEL_103:
    CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(v70);
    goto LABEL_104;
  }
  SetLastError(0);
  v111 = WORD2(v152);
  v112 = HIWORD(v152);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Format(
                        &v196,
                        L"%u.%u",
                        HIWORD(v152),
                        WORD2(v152)) )
  {
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075A10);
    v72 = 0;
    goto LABEL_103;
  }
  SetLastError(0);
  v113 = InlineBuffer;
  v190 = (unsigned __int16 **)&v179;
  LODWORD(v179) = 0;
  v187.Flags = 1;
  v187.Previous = 0;
  v187.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D380;
  v188 = 544438355;
  v189 = 507;
  CFrame::BaseEnter((CFrame *)&v187);
  v174 = 0;
  v148 = 0x300000002LL;
  v114 = RegOpenKeyExW(v9, v113, 0, 0x20119u, &v174);
  if ( !v114 )
    goto LABEL_170;
  for ( j = 0; j < 2; ++j )
  {
    if ( *((_DWORD *)&v148 + j) == v114 )
    {
      v116 = 0;
      v174 = 0;
      goto LABEL_171;
    }
  }
  if ( j == 2 )
  {
    SetLastError(v114);
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007CA20);
    v72 = 0;
  }
  else
  {
LABEL_170:
    v116 = v174;
LABEL_171:
    v72 = 0;
    if ( v116 )
      v72 = v116;
    v156 = v72;
    SetLastError(0);
    *(_DWORD *)v190 = 1;
  }
  v117 = *(_DWORD *)v190;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v117 )
    {
      FusionpTraceCallSuccessfulExit(0);
      RtlPopFrame(&v187);
      goto LABEL_176;
    }
    v142 = GetLastError();
    FusionpTraceCallWin32UnsuccessfulExit(v142, 0);
    RtlPopFrame(&v187);
LABEL_325:
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800759F0);
    goto LABEL_103;
  }
  RtlPopFrame(&v187);
  if ( !v117 )
    goto LABEL_325;
LABEL_176:
  if ( !v72 )
  {
    v181 = 1;
    goto LABEL_103;
  }
  SetLastError(0);
  LODWORD(v145) = (unsigned __int16)v152;
  LODWORD(phkResult) = WORD1(v152);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Format(
                        &v196,
                        L"%u.%u.%u.%u",
                        v112,
                        v111,
                        phkResult,
                        v145) )
  {
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800759D0);
    goto LABEL_103;
  }
  SetLastError(0);
  if ( !(unsigned int)CRegKey::GetValue(&v156, 0, InlineBuffer, v169, &v160, 1, 2) )
  {
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800759B0);
    v72 = v156;
    goto LABEL_103;
  }
  if ( v171 != 1 || *(_BYTE *)v170 != 1 )
  {
    v72 = v156;
    v181 = 1;
    goto LABEL_103;
  }
  v72 = v156;
  v71 = v149;
  v146 = 1;
LABEL_182:
  v118 = v175[0] >> 1;
  v119 = *(_WORD *)(v158 + 2 * v159 - 2);
  if ( v119 != 92 && v119 != 47 )
    LODWORD(v84) = 1;
  v120 = v159 + (unsigned int)v84;
  if ( v71 == 1 )
    v120 += 10;
  else
    LOBYTE(v71) = 0;
  SetLastError(0);
  if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(
                       v70,
                       v120 + v118 + 2 + 8LL * (unsigned __int8)v71) )
  {
    SetLastError(0);
    if ( (_BYTE)v71 )
    {
      v133 = 1;
      v134 = 9;
    }
    else
    {
      v134 = 0;
      v133 = 0;
    }
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AssignW(
                         v70,
                         4,
                         v158,
                         (unsigned int)v159,
                         L"\\",
                         (_DWORD)v84,
                         L"manifests",
                         v134,
                         L"\\",
                         v133) )
    {
      SetLastError(0);
      if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v70, v176, v175[0] >> 1) )
      {
        SetLastError(0);
        if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(
                             v70,
                             L"\\",
                             (unsigned __int8)v71 ^ 1LL) )
        {
          if ( (_BYTE)v71
            && (SetLastError(0),
                !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v70, L".manifest", 9)) )
          {
            *v186 = 0;
            FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075950);
            v13 = v146;
          }
          else
          {
            v13 = v146;
            v181 = 1;
          }
        }
        else
        {
          *v186 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075970);
          v13 = v146;
        }
      }
      else
      {
        *v186 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075990);
        v13 = v146;
      }
    }
    else
    {
      *v186 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006DF28);
      v13 = v146;
    }
  }
  else
  {
    *v186 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006D920);
    v13 = v146;
  }
LABEL_93:
  if ( (v153 & 8) != 0 && !v13 )
    goto LABEL_103;
LABEL_104:
  v74 = v181;
  if ( v171 )
    operator delete(v170);
  v196 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( InlineBuffer != (LPCWSTR)&v201 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v196);
  InlineBuffer = 0;
  v196 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v199 = 0;
  v75 = GetLastError();
  if ( (unsigned __int64)v72 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v76 = RegCloseKey(v72);
    if ( v76 )
      SetLastError(v76);
  }
  SetLastError(v75);
  v77 = GetLastError();
  if ( (unsigned __int64)v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v78 = RegCloseKey(v9);
    if ( v78 )
      SetLastError(v78);
  }
  SetLastError(v77);
  v79 = GetLastError();
  v80 = v182;
  v81 = v79;
  v182 = 0;
  if ( (unsigned __int64)v80 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v82 = RegCloseKey(v80);
    if ( v82 )
      SetLastError(v82);
  }
  SetLastError(v81);
  v202 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  if ( lpSubKey != (LPCWSTR)&v207 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v202);
  lpSubKey = 0;
  v205 = 0;
  v202 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v186 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v143 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v143, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v74;
}

```

## disassembly

```asm
0x180023ee0  mov     [rsp-8+arg_0], rbx
0x180023ee5  push    rbp
0x180023ee6  push    rsi
0x180023ee7  push    rdi
0x180023ee8  push    r12
0x180023eea  push    r13
0x180023eec  push    r14
0x180023eee  push    r15
0x180023ef0  lea     rbp, [rsp-660h]
0x180023ef8  sub     rsp, 760h
0x180023eff  mov     rax, cs:__security_cookie
0x180023f06  xor     rax, rsp
0x180023f09  mov     [rbp+690h+var_40], rax
0x180023f10  mov     rax, [rbp+690h+arg_30]
0x180023f17  mov     r12d, ecx
0x180023f1a  mov     rbx, [rbp+690h+arg_28]
0x180023f21  xor     edi, edi
0x180023f23  mov     rsi, [rbp+690h+arg_20]
0x180023f2a  mov     r15, r9
0x180023f2d  mov     [rbp+690h+var_618], rax
0x180023f31  lea     rax, qword_18006D300
0x180023f38  mov     [rbp+690h+Frame.Context], rax
0x180023f3f  lea     rax, [rbp+690h+var_608]
0x180023f46  mov     [rbp+690h+var_700], ecx
0x180023f49  lea     rcx, [rbp+690h+Frame]; Frame
0x180023f50  mov     [rbp+690h+var_5D0], rax
0x180023f57  mov     [rbp+690h+var_6D0], r9
0x180023f5b  mov     [rbp+690h+var_6D8], r8
0x180023f5f  mov     [rsp+790h+var_720], edx
0x180023f63  mov     [rbp+690h+var_6C0], rbx
0x180023f67  mov     [rbp+690h+var_6E0], rsi
0x180023f6b  mov     [rbp+690h+var_608], edi
0x180023f71  mov     [rbp+690h+Frame.Flags], 1
0x180023f7b  mov     [rbp+690h+Frame.Previous], rdi
0x180023f82  mov     [rbp+690h+var_5E0], 20737853h
0x180023f8d  mov     [rbp+690h+var_5D8], 4BFh
0x180023f97  call    cs:__imp_RtlPushFrame
0x180023f9e  nop     dword ptr [rax+rax+00h]
0x180023fa3  cmp     cs:g_FusionEnterExitTracingEnabled, dil
0x180023faa  jnz     loc_18002537C
0x180023fb0  mov     rax, rdi
0x180023fb3  mov     [rbp+690h+var_610], rdi
0x180023fba  mov     [rsp+790h+var_718], rax
0x180023fbf  lea     rcx, [rbp+690h+var_4B0]
0x180023fc6  mov     [rbp+690h+var_6A0], rax
0x180023fca  mov     r13, rdi
0x180023fcd  mov     [rbp+690h+var_6F8], rax
0x180023fd1  mov     [rbp+690h+var_680], rax
0x180023fd5  mov     [rbp+690h+var_6F0], rax
0x180023fd9  mov     [rbp+690h+var_688], rax
0x180023fdd  mov     [rbp+690h+var_710], rax
0x180023fe1  mov     [rsp+790h+var_728], rax
0x180023fe6  lea     rax, [rbp+690h+var_280]
0x180023fed  mov     [rbp+690h+Src], rax
0x180023ff1  lea     rax, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x180023ff8  mov     [rbp+690h+var_4B0], rax
0x180023fff  mov     [rbp+690h+var_658], rdi
0x180024003  mov     [rbp+690h+var_6B0], rdi
0x180024007  mov     [rbp+690h+var_690], rdi
0x18002400b  mov     [rbp+690h+var_6A8], rdi
0x18002400f  mov     [rbp+690h+var_650], rdi
0x180024013  mov     [rbp+690h+var_6B8], rdi
0x180024017  mov     [rbp+690h+var_630], rdi
0x18002401b  mov     [rbp+690h+var_628], 118h
0x180024023  mov     [rbp+690h+var_4A8], edi
0x180024029  mov     [rbp+690h+lpSubKey], rdi
0x180024030  mov     [rbp+690h+var_498], rdi
0x180024037  mov     [rbp+690h+var_490], rdi
0x18002403e  mov     [rbp+690h+var_488], di
0x180024045  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x18002404a  mov     [rbp+690h+lpSubKey], rax
0x180024051  lea     rcx, [rbp+690h+var_4B0]
0x180024058  mov     rax, [rbp+690h+var_4B0]
0x18002405f  mov     rax, [rax+18h]
0x180024063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024068  mov     [rbp+690h+var_498], rax
0x18002406f  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180024074  test    eax, eax
0x180024076  jz      short loc_180024090
0x180024078  mov     r8, [rbp+690h+var_498]
0x18002407f  xor     edx, edx; Val
0x180024081  mov     rcx, [rbp+690h+lpSubKey]; void *
0x180024088  add     r8, r8; Size
0x18002408b  call    memset_0
0x180024090  xor     r14d, r14d
0x180024093  mov     [rbp+690h+var_600], rdi
0x18002409a  mov     eax, r14d
0x18002409d  mov     [rbp+690h+var_708], r14
0x1800240a1  mov     [rsp+790h+hKey], rax
0x1800240a6  lea     rcx, [rbp+690h+var_560]
0x1800240ad  mov     [rbp+690h+var_6E8], rax
0x1800240b1  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x1800240b8  mov     [rbp+690h+var_560], rax
0x1800240bf  mov     [rbp+690h+var_558], r14d
0x1800240c6  mov     [rbp+690h+var_550], r14
0x1800240cd  mov     [rbp+690h+var_548], r14
0x1800240d4  mov     [rbp+690h+var_540], r14
0x1800240db  mov     [rbp+690h+var_538], r14w
0x1800240e3  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x1800240e8  mov     [rbp+690h+var_550], rax
0x1800240ef  lea     rcx, [rbp+690h+var_560]
0x1800240f6  mov     rax, [rbp+690h+var_560]
0x1800240fd  mov     rax, [rax+18h]
0x180024101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024106  mov     [rbp+690h+var_548], rax
0x18002410d  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180024112  test    eax, eax
0x180024114  jnz     loc_1800242DE
0x18002411a  xor     ecx, ecx; char *
0x18002411c  mov     [rbp+690h+var_670], r14
0x180024120  lea     rax, [rbp+690h+var_160]
0x180024127  mov     [rbp+690h+var_668], r14
0x18002412b  mov     [rbp+690h+var_638], rax
0x18002412f  mov     eax, [rsp+790h+var_720]
0x180024133  dec     eax
0x180024135  mov     [rbp+690h+var_660], r14
0x180024139  mov     [rsp+790h+var_730], dil
0x18002413e  mov     [rsp+790h+var_740], r14b
0x180024143  mov     [rbp+690h+var_6C8], ecx
0x180024146  mov     [rbp+690h+var_648], rcx
0x18002414a  mov     [rbp+690h+var_640], 118h
0x180024152  cmp     eax, 1
0x180024155  ja      loc_1800256DD
0x18002415b  test    rsi, rsi
0x18002415e  jz      loc_180025714
0x180024164  test    r12d, 0FFFFFFF7h
0x18002416b  jnz     loc_180025720
0x180024171  test    r15, r15
0x180024174  jz      loc_1800256E9
0x18002417a  lea     r15, qword_18006CDC0
0x180024181  test    rbx, rbx
0x180024184  jnz     loc_180024C47
0x18002418a  call    cs:__imp_SetLastError
0x180024191  nop     dword ptr [rax+rax+00h]
0x180024196  lea     rax, [rbp+690h+var_610]
0x18002419d  mov     dword ptr [rbp+690h+var_610], ebx
0x1800241a3  lea     rcx, [rbp+690h+var_5C8]; Frame
0x1800241aa  mov     [rbp+690h+var_5A0], rax
0x1800241b1  mov     [rbp+690h+var_5C8.Flags], 1
0x1800241bb  mov     [rbp+690h+var_5C8.Previous], rbx
0x1800241c2  mov     [rbp+690h+var_5C8.Context], r15
0x1800241c9  mov     [rbp+690h+var_5B0], 20737853h
0x1800241d4  mov     [rbp+690h+var_5A8], 99h
0x1800241de  call    cs:__imp_RtlPushFrame
0x1800241e5  nop     dword ptr [rax+rax+00h]
0x1800241ea  cmp     cs:g_FusionEnterExitTracingEnabled, bl
0x1800241f0  jnz     loc_1800253BA
0x1800241f6  mov     r12, cs:off_18006D330; "name"
0x1800241fd  mov     r11d, ebx
0x180024200  mov     ebx, [rsi+10h]
0x180024203  mov     r15, [rsi+28h]
0x180024207  cmp     r11d, ebx
0x18002420a  jnb     loc_18002431B
0x180024210  mov     eax, r11d
0x180024213  lea     ecx, [rbx+r11]
0x180024217  shr     ecx, 1
0x180024219  cmp     ecx, ebx
0x18002421b  cmovnz  eax, ecx
0x18002421e  mov     r8d, eax
0x180024221  mov     r14, [r15+rax*8]
0x180024225  cmp     [r14+8], rdi
0x180024229  ja      loc_18002430E
0x18002422f  mov     r9, [r14+10h]
0x180024233  mov     ecx, 4
0x180024238  mov     r10, [r14+28h]
0x18002423c  cmp     r9, 4
0x180024240  mov     rax, r9
0x180024243  mov     rdx, r12
0x180024246  cmovnb  rax, rcx
0x18002424a  lea     rsi, [r12+rax*2]
0x18002424e  cmp     rdx, rsi
0x180024251  jnb     short loc_18002426B
0x180024253  movzx   ecx, word ptr [rdx]
0x180024256  add     rdx, 2
0x18002425a  movzx   eax, word ptr [r10]
0x18002425e  add     r10, 2
0x180024262  sub     ecx, eax
0x180024264  jz      short loc_18002424E
0x180024266  jmp     loc_180024300
0x18002426b  cmp     r9, 4
0x18002426f  ja      loc_18002572C
0x180024275  jnz     loc_1800242FB
0x18002427b  test    r14, r14
0x18002427e  jz      loc_18002431B
0x180024284  test    r8d, r8d
0x180024287  jz      loc_1800252C0
0x18002428d  mov     edi, 4
0x180024292  lea     ebx, [r8-1]
0x180024296  mov     r11, [r15+rbx*8]
0x18002429a  cmp     [r11+8], r13
0x18002429e  ja      loc_1800252B4
0x1800242a4  mov     r9, [r11+10h]
0x1800242a8  mov     rdx, r12
0x1800242ab  mov     r10, [r11+28h]
0x1800242af  cmp     r9, rdi
0x1800242b2  mov     rax, r9
0x1800242b5  cmovnb  rax, rdi
0x1800242b9  lea     r8, [r12+rax*2]
0x1800242bd  cmp     rdx, r8
0x1800242c0  jnb     loc_180025298
0x1800242c6  movzx   eax, word ptr [r10]
0x1800242ca  add     r10, 2
0x1800242ce  movzx   ecx, word ptr [rdx]
0x1800242d1  add     rdx, 2
0x1800242d5  sub     ecx, eax
0x1800242d7  jz      short loc_1800242BD
0x1800242d9  jmp     loc_1800252AC
0x1800242de  mov     r8, [rbp+690h+var_548]
0x1800242e5  xor     edx, edx; Val
0x1800242e7  mov     rcx, [rbp+690h+var_550]; void *
0x1800242ee  add     r8, r8; Size
0x1800242f1  call    memset_0
0x1800242f6  jmp     loc_18002411A
0x1800242fb  mov     ecx, 0FFFFFFFFh
0x180024300  test    ecx, ecx
0x180024302  js      loc_1800256A4
0x180024308  jz      loc_18002427B
0x18002430e  cmp     r11d, r8d
0x180024311  jz      short loc_18002431B
0x180024313  mov     r11d, r8d
0x180024316  jmp     loc_180024207
0x18002431b  mov     ecx, 490h; dwErrCode
0x180024320  call    cs:__imp_SetLastError
0x180024327  nop     dword ptr [rax+rax+00h]
0x18002432c  mov     rax, [rbp+690h+var_5A0]
0x180024333  lea     rcx, off_18006D3E0; struct _CALL_SITE_INFO *
0x18002433a  xor     r15d, r15d
0x18002433d  mov     [rax], r15d
0x180024340  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180024345  mov     ebx, dword ptr [rbp+690h+var_610]
0x18002434b  mov     r14, [rbp+690h+var_690]
0x18002434f  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180024356  jnz     loc_180025753
0x18002435c  lea     rcx, [rbp+690h+var_5C8]; Frame
0x180024363  call    cs:__imp_RtlPopFrame
0x18002436a  nop     dword ptr [rax+rax+00h]
0x18002436f  test    ebx, ebx
0x180024371  jz      loc_180025785
0x180024377  mov     rbx, [rbp+690h+var_6C0]
0x18002437b  lea     r15, qword_18006CDC0
0x180024382  mov     rsi, [rbp+690h+var_6E0]
0x180024386  test    r13, r13
0x180024389  jz      loc_1800253CE
0x18002438f  test    r14, r14
0x180024392  jz      loc_1800253CE
0x180024398  test    rbx, rbx
0x18002439b  jnz     loc_180024FFC
0x1800243a1  xor     ecx, ecx; dwErrCode
0x1800243a3  call    cs:__imp_SetLastError
0x1800243aa  nop     dword ptr [rax+rax+00h]
0x1800243af  lea     rax, [rbp+690h+var_610]
0x1800243b6  mov     dword ptr [rbp+690h+var_610], ebx
0x1800243bc  lea     rcx, [rbp+690h+var_5C8]; Frame
0x1800243c3  mov     [rbp+690h+var_5A0], rax
0x1800243ca  mov     [rbp+690h+var_5C8.Flags], 1
0x1800243d4  mov     [rbp+690h+var_5C8.Previous], rbx
0x1800243db  mov     [rbp+690h+var_5C8.Context], r15
0x1800243e2  mov     [rbp+690h+var_5B0], 20737853h
0x1800243ed  mov     [rbp+690h+var_5A8], 99h
0x1800243f7  call    cs:__imp_RtlPushFrame
0x1800243fe  nop     dword ptr [rax+rax+00h]
0x180024403  cmp     cs:g_FusionEnterExitTracingEnabled, bl
0x180024409  jnz     loc_1800253C4
0x18002440f  mov     r12, cs:off_18006D350; "version"
0x180024416  mov     r10d, ebx
0x180024419  mov     r15, [rsi+28h]
0x18002441d  mov     r13d, 7
0x180024423  mov     r11d, [rsi+10h]
0x180024427  cmp     r10d, r11d
0x18002442a  jnb     loc_180024505
0x180024430  mov     eax, r10d
0x180024433  lea     ecx, [r11+r10]
0x180024437  shr     ecx, 1
0x180024439  cmp     ecx, r11d
0x18002443c  cmovnz  eax, ecx
0x18002443f  mov     r8d, eax
0x180024442  mov     r14, [r15+rax*8]
0x180024446  cmp     qword ptr [r14+8], 0
0x18002444b  ja      loc_1800244F8
0x180024451  mov     r9, [r14+10h]
0x180024455  mov     rdx, r12
0x180024458  mov     rbx, [r14+28h]
0x18002445c  cmp     r9, r13
0x18002445f  mov     rax, r9
0x180024462  cmovnb  rax, r13
0x180024466  lea     rsi, [r12+rax*2]
0x18002446a  cmp     rdx, rsi
0x18002446d  jnb     short loc_180024483
0x18002446f  movzx   ecx, word ptr [rdx]
0x180024472  add     rdx, 2
0x180024476  movzx   eax, word ptr [rbx]
0x180024479  add     rbx, 2
0x18002447d  sub     ecx, eax
0x18002447f  jz      short loc_18002446A
0x180024481  jmp     short loc_1800244EE
0x180024483  cmp     r9, r13
0x180024486  ja      loc_1800257A8
0x18002448c  jnz     short loc_1800244E9
0x18002448e  test    r14, r14
0x180024491  jz      short loc_180024505
  ... truncated ...
```
