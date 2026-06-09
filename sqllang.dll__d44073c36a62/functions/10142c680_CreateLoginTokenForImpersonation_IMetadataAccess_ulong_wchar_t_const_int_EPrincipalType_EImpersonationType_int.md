# CreateLoginTokenForImpersonation(IMetadataAccess *,ulong,wchar_t const *,int,EPrincipalType,EImpersonationType,int,bool,wchar_t const *,int,wchar_t const *,int,SDSPrincipalType,FederatedContext *,uchar const *,int,int)

- ea: `0x10142c680`
- end: `0x10142dfe0`
- name: `?CreateLoginTokenForImpersonation@@YAPEAVILoginToken@@PEAVIMetadataAccess@@KPEB_WHW4EPrincipalType@@W4EImpersonationType@@H_N1H1HW4SDSPrincipalType@@PEAUFederatedContext@@PEBEHH@Z`
- size: `6496`
- prototype: `struct ILoginToken *__high(struct IMetadataAccess *, unsigned int, const wchar_t *, int, enum EPrincipalType, enum EImpersonationType, int, bool, const wchar_t *, int, const wchar_t *, int, enum SDSPrincipalType, struct FederatedContext *, const unsigned __int8 *, int, int)`
- caller_count: `12`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10042c190`
- `0x100f23ba0`
- `0x100f273d0`
- `0x10134d130`
- `0x101420c00`
- `0x10142dff0`
- `0x10142fc00`
- `0x101431250`
- `0x101431b90`
- `0x101433a50`
- `0x101460000`
- `0x1020871d8`

## callees

- `0x100401070`
- `0x100401400`
- `0x100401433`
- `0x10041a970`
- `0x100430960`
- `0x100440b60`
- `0x100440d70`
- `0x100536250`
- `0x10054bd10`
- `0x10054bd60`
- `0x1005511a0`
- `0x1006ed800`
- `0x1007d40d0`
- `0x100a15030`
- `0x101259d60`
- `0x10138dab0`
- `0x10138e6e0`
- `0x101425e90`
- `0x1014261f0`
- `0x101427250`
- `0x101428200`
- `0x10142c600`
- `0x10142c680`
- `0x10154ee80`
- `0x10155e600`
- `0x1016854b0`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x10142da5a`
- `ADVAPI32!IsValidSid` at `0x10142da5a`
- `ole32!CoCreateGuid` at `0x10142d193`
- `ole32!CoCreateGuid` at `0x10142d193`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10142d23b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10142c80b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10142c80b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142cde1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142cdf3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142ce9d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142cf74`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d129`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d613`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d757`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d91c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d979`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d9f7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142db26`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142cde1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142cdf3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142ce9d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142cf74`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d129`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d613`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d757`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d91c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d979`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142d9f7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10142db26`
- `sqldk!SystemThread_TlsIndex` at `0x10142c731`
- `sqldk!SystemThread_TlsIndex` at `0x10142c79d`
- `sqldk!SystemThread_TlsIndex` at `0x10142cabc`
- `sqldk!SystemThread_TlsIndex` at `0x10142cb88`
- `sqldk!SystemThread_TlsIndex` at `0x10142d0bc`
- `sqldk!SystemThread_TlsIndex` at `0x10142d138`
- `sqldk!SystemThread_TlsIndex` at `0x10142d46b`
- `sqldk!SystemThread_TlsIndex` at `0x10142d5a3`
- `sqldk!SystemThread_TlsIndex` at `0x10142dbd7`
- `sqldk!SystemThread_TlsIndex` at `0x10142ddf5`
- `sqldk!SystemThread_TlsOffset` at `0x10142c73a`
- `sqldk!SystemThread_TlsOffset` at `0x10142c7a6`
- `sqldk!SystemThread_TlsOffset` at `0x10142cac5`
- `sqldk!SystemThread_TlsOffset` at `0x10142cb91`
- `sqldk!SystemThread_TlsOffset` at `0x10142d0cd`
- `sqldk!SystemThread_TlsOffset` at `0x10142d141`
- `sqldk!SystemThread_TlsOffset` at `0x10142d474`
- `sqldk!SystemThread_TlsOffset` at `0x10142d5ac`
- `sqldk!SystemThread_TlsOffset` at `0x10142dbe8`
- `sqldk!SystemThread_TlsOffset` at `0x10142ddfe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142cae0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142cbac`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142d15c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142de17`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142cae0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142cbac`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142d15c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142de17`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142d281`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142d2a0`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142d56d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142d281`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142d2a0`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142d56d`
- `sqlTsEs!?PwchLocateBackSlash@@YAPEA_WPEA_WH@Z` at `0x10142cee9`
- `sqlTsEs!?PwchLocateBackSlash@@YAPEA_WPEA_WH@Z` at `0x10142d58b`
- `sqlTsEs!?PwchLocateBackSlash@@YAPEA_WPEA_WH@Z` at `0x10142cee9`
- `sqlTsEs!?PwchLocateBackSlash@@YAPEA_WPEA_WH@Z` at `0x10142d58b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142cce7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142ccfe`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142d7f2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142d813`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142d8a7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142d8be`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142cce7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142ccfe`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142d7f2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142d813`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142d8a7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10142d8be`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10142cd0a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10142d7fe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10142d81f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10142d8ca`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10142cd0a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10142d7fe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10142d81f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10142d8ca`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10142dc6c`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10142dc83`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10142dc6c`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10142dc83`
- `sqlmin!?GetDBName@DBMgr@@QEAAHVContextHandle@@KPEA_WPEAK_N@Z` at `0x10142c801`
- `sqlmin!?GetDBName@DBMgr@@QEAAHVContextHandle@@KPEA_WPEAK_N@Z` at `0x10142c801`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142c90f`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142c9b8`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142cb02`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142d67c`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142c90f`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142c9b8`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142cb02`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142d67c`
- `sqlmin!GetXdbServerGlobals` at `0x10142d1cb`
- `sqlmin!GetXdbServerGlobals` at `0x10142d518`
- `sqlmin!GetXdbServerGlobals` at `0x10142dba1`
- `sqlmin!GetXdbServerGlobals` at `0x10142d1cb`
- `sqlmin!GetXdbServerGlobals` at `0x10142d518`
- `sqlmin!GetXdbServerGlobals` at `0x10142dba1`

## string_xrefs

- `0x10142d259`: `AADServerAdminSid`
- `0x10142cbc7`: `CreateLoginTokenForImpersonation`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
struct ILoginToken *__fastcall CreateLoginTokenForImpersonation(
        struct IMetadataAccess *a1,
        unsigned int a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        char a8,
        void (__fastcall ****a9)(_QWORD, __int64),
        int a10,
        void *a11,
        int a12,
        unsigned int a13,
        __int64 a14,
        void *a15,
        int a16,
        int a17)
{
  unsigned int v17; // r13d
  unsigned int v19; // r11d
  struct IMetadataAccess *v20; // r10
  unsigned int (__fastcall ***v21)(_QWORD); // rcx
  struct ILoginToken *LoginToken; // r14
  unsigned int v23; // edi
  struct __crt_locale_pointers *DefaultLocale; // rax
  __int64 v25; // rdi
  struct ILoginToken *v26; // rax
  int v27; // esi
  unsigned __int16 v28; // ax
  unsigned __int8 v29; // al
  unsigned int v30; // edi
  unsigned __int16 v31; // ax
  __int64 v32; // rcx
  __int64 v34; // rdi
  __int64 v35; // rsi
  __int64 v36; // rsi
  int v37; // edi
  unsigned __int16 v38; // ax
  __int64 v39; // rdi
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 v42; // r12
  __int16 v43; // r13
  int v44; // edi
  __int64 v45; // rax
  unsigned __int64 v46; // r15
  __int64 v47; // rax
  __int64 v48; // r12
  int v49; // eax
  int v50; // r13d
  unsigned int v51; // edi
  int v52; // edx
  int v53; // ecx
  __int64 v54; // rax
  int v55; // eax
  __int16 v56; // r12
  unsigned int v57; // esi
  struct IMetadataAccess *v58; // r13
  __int64 v59; // rax
  struct IMEDLogin *v60; // rax
  unsigned int (__fastcall ***v61)(_QWORD); // r12
  char *ThreadLocalStoragePointer; // rdx
  __int64 v63; // rsi
  __int64 v64; // rax
  _BYTE *v65; // r12
  const struct CFedAuthFeatureExtension *FeatureExtension; // r15
  __int64 v67; // rsi
  __int64 v68; // rax
  __int64 v69; // r13
  __int64 v70; // rcx
  char v71; // r14
  int v72; // ecx
  unsigned int v73; // eax
  __m128i v74; // xmm6
  __int64 v75; // rax
  wchar_t *v76; // rsi
  __int64 v77; // rax
  __int64 v78; // rcx
  int FederatedContextInternalWithRetry; // esi
  unsigned int v80; // r14d
  __int64 v81; // rax
  __int64 v82; // rcx
  int v83; // edx
  void *v84; // rsi
  char v85; // al
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rdi
  unsigned __int16 MasterDbId; // ax
  __int64 LoginTokenFromFederatedContext; // rdi
  char *v91; // rcx
  int v92; // edi
  const wchar_t *v93; // r15
  unsigned int v94; // r12d
  void *v95; // rsi
  unsigned int v96; // r15d
  unsigned int v97; // edi
  char *v98; // rsi
  __int64 v99; // rcx
  _BYTE *v100; // rdx
  __int64 v101; // r8
  char *v102; // rcx
  char v103; // r13
  unsigned int v104; // esi
  __int64 v105; // rdi
  __int64 v106; // rcx
  struct IMetadataAccessor *DefaultMetadataAccessor; // rdi
  unsigned int v108; // eax
  signed __int32 v109[8]; // [rsp+0h] [rbp-140h] BYREF
  struct IMetadataAccess *v110; // [rsp+20h] [rbp-120h]
  unsigned int v111[2]; // [rsp+28h] [rbp-118h]
  __int64 v112; // [rsp+30h] [rbp-110h]
  __int64 v113; // [rsp+38h] [rbp-108h]
  __int64 v114; // [rsp+40h] [rbp-100h]
  __int64 v115; // [rsp+48h] [rbp-F8h]
  __int64 v116; // [rsp+50h] [rbp-F0h]
  __int64 v117; // [rsp+58h] [rbp-E8h]
  __int64 v118; // [rsp+60h] [rbp-E0h]
  __int64 v119; // [rsp+68h] [rbp-D8h]
  __int64 v120; // [rsp+70h] [rbp-D0h]
  __int64 v121; // [rsp+78h] [rbp-C8h]
  __int64 v122; // [rsp+80h] [rbp-C0h]
  __int64 v123; // [rsp+88h] [rbp-B8h]
  __int64 v124; // [rsp+90h] [rbp-B0h]
  __int64 v125; // [rsp+98h] [rbp-A8h]
  int v126; // [rsp+A0h] [rbp-A0h]
  __int64 v127; // [rsp+A8h] [rbp-98h]
  __int64 v128; // [rsp+B0h] [rbp-90h]
  __int64 v129; // [rsp+B8h] [rbp-88h]
  char v130[4]; // [rsp+C0h] [rbp-80h] BYREF
  unsigned int v131; // [rsp+C4h] [rbp-7Ch]
  int v132; // [rsp+C8h] [rbp-78h]
  unsigned int v133; // [rsp+CCh] [rbp-74h]
  char v134[8]; // [rsp+D0h] [rbp-70h] BYREF
  struct ILoginToken *v135; // [rsp+D8h] [rbp-68h]
  void **v136; // [rsp+E0h] [rbp-60h] BYREF
  struct IMetadataAccess *v137; // [rsp+E8h] [rbp-58h]
  void (__fastcall ***v138)(_QWORD, __int64); // [rsp+F0h] [rbp-50h] BYREF
  unsigned int v139; // [rsp+F8h] [rbp-48h] BYREF
  void *Src; // [rsp+100h] [rbp-40h]
  unsigned int (__fastcall ***v141)(_QWORD); // [rsp+108h] [rbp-38h]
  unsigned int v142; // [rsp+110h] [rbp-30h]
  __int16 v143; // [rsp+114h] [rbp-2Ch] BYREF
  void (__fastcall ****v144)(_QWORD, __int64); // [rsp+118h] [rbp-28h]
  unsigned int v145; // [rsp+120h] [rbp-20h]
  int v146; // [rsp+124h] [rbp-1Ch] BYREF
  unsigned int v147; // [rsp+128h] [rbp-18h] BYREF
  int v148; // [rsp+12Ch] [rbp-14h] BYREF
  int v149; // [rsp+130h] [rbp-10h] BYREF
  struct IMetadataAccess *v150; // [rsp+138h] [rbp-8h]
  int v151; // [rsp+140h] [rbp+0h]
  int v152; // [rsp+144h] [rbp+4h]
  void *v153; // [rsp+148h] [rbp+8h] BYREF
  void (__fastcall ****v154)(_QWORD, __int64); // [rsp+150h] [rbp+10h]
  int v155; // [rsp+158h] [rbp+18h] BYREF
  int v156; // [rsp+15Ch] [rbp+1Ch] BYREF
  struct IMetadataAccessor *v157; // [rsp+160h] [rbp+20h]
  __int64 v158; // [rsp+168h] [rbp+28h]
  void *v159; // [rsp+170h] [rbp+30h]
  void *v160; // [rsp+178h] [rbp+38h]
  wchar_t *v161; // [rsp+180h] [rbp+40h] BYREF
  wchar_t *v162; // [rsp+188h] [rbp+48h]
  wchar_t *v163; // [rsp+190h] [rbp+50h] BYREF
  int v164; // [rsp+198h] [rbp+58h]
  __int64 v165; // [rsp+1A0h] [rbp+60h]
  GUID v166; // [rsp+1B0h] [rbp+70h] BYREF
  __m128i v167; // [rsp+1C0h] [rbp+80h] BYREF
  struct _GUID v168; // [rsp+1D0h] [rbp+90h] BYREF
  char v169[8]; // [rsp+1E0h] [rbp+A0h] BYREF
  int v170; // [rsp+1E8h] [rbp+A8h]
  int v171; // [rsp+1F0h] [rbp+B0h]
  __int16 **v172; // [rsp+1F8h] [rbp+B8h]
  char *v173; // [rsp+200h] [rbp+C0h]
  __int64 v174; // [rsp+208h] [rbp+C8h]
  __int16 *v175; // [rsp+210h] [rbp+D0h] BYREF
  int v176; // [rsp+218h] [rbp+D8h]
  int v177; // [rsp+21Ch] [rbp+DCh]
  GUID *v178; // [rsp+220h] [rbp+E0h]
  int v179; // [rsp+228h] [rbp+E8h]
  int v180; // [rsp+22Ch] [rbp+ECh]
  GUID *p_pguid; // [rsp+230h] [rbp+F0h]
  int v182; // [rsp+238h] [rbp+F8h]
  int v183; // [rsp+23Ch] [rbp+FCh]
  __int64 v184; // [rsp+240h] [rbp+100h]
  int v185; // [rsp+248h] [rbp+108h]
  int v186; // [rsp+24Ch] [rbp+10Ch]
  char v187; // [rsp+250h] [rbp+110h] BYREF
  __int64 v188; // [rsp+430h] [rbp+2F0h]
  __int64 v189; // [rsp+438h] [rbp+2F8h]
  __int16 v190; // [rsp+440h] [rbp+300h] BYREF
  bool v191; // [rsp+442h] [rbp+302h]
  int v192; // [rsp+443h] [rbp+303h]
  int v193; // [rsp+447h] [rbp+307h]
  int v194; // [rsp+44Bh] [rbp+30Bh]
  GUID pguid; // [rsp+470h] [rbp+330h] BYREF
  GUID v196; // [rsp+480h] [rbp+340h] BYREF
  __int128 v197; // [rsp+490h] [rbp+350h] BYREF
  __int128 pSid; // [rsp+4A0h] [rbp+360h] BYREF
  __int128 v199; // [rsp+4B0h] [rbp+370h]
  __int128 v200; // [rsp+4C0h] [rbp+380h]
  __int128 v201; // [rsp+4D0h] [rbp+390h]
  __int128 v202; // [rsp+4E0h] [rbp+3A0h]
  int v203; // [rsp+4F0h] [rbp+3B0h]
  char v204; // [rsp+4F4h] [rbp+3B4h]
  wchar_t v205[2]; // [rsp+500h] [rbp+3C0h] BYREF
  char v206; // [rsp+504h] [rbp+3C4h] BYREF
  wchar_t v207[256]; // [rsp+610h] [rbp+4D0h] BYREF

  v165 = -2;
  v17 = a4;
  v133 = a4;
  Src = a3;
  v19 = a2;
  v142 = a2;
  v20 = a1;
  v150 = a1;
  v159 = a15;
  v160 = a11;
  v131 = a6;
  v144 = a9;
  v152 = a10;
  v145 = a13;
  v158 = a14;
  v151 = a17;
  v21 = *(unsigned int (__fastcall ****)(_QWORD))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                          + SystemThread_TlsIndex)
                                                                        + SystemThread_TlsOffset)
                                                            + 120LL)
                                                + 264LL);
  v141 = v21;
  LoginToken = 0;
  v135 = 0;
  if ( a5 )
  {
    v136 = &AutoReadOnlyIMA::`vftable';
    v137 = 0;
    v154 = &v138;
    v138 = 0;
    if ( !v20 )
    {
      v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v40 = *(_QWORD *)(v39 + 256);
      if ( !v40 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v40 = *(_QWORD *)(v39 + 256);
      }
      v41 = *(_QWORD *)(v40 + 1000);
      AutoReadOnlyXact::BeginCompatibleXact((AutoReadOnlyXact *)&v138, L"CreateLoginTokenForImpersonation", 64, 0);
      ((void (__fastcall *)(void ***, __int64))*v136)(&v136, v41);
      v20 = v137;
      v150 = v137;
      LoginToken = v135;
      v19 = v142;
    }
    v42 = 0;
    v154 = 0;
    v43 = 0;
    v132 = 0;
    v44 = -1;
    if ( a6 != 5 )
    {
      v45 = *(_QWORD *)v20;
      v111[0] = 0;
      v42 = (*(__int64 (__fastcall **)(struct IMetadataAccess *, _QWORD, _QWORD, _QWORD, _DWORD))(v45 + 56))(
              v20,
              v19,
              0,
              0,
              0);
    }
    v46 = (__int16)v133;
    v139 = (__int16)v133;
    if ( (__int16)v133 > 256 )
    {
      if ( a8 )
      {
        v136 = &AutoReadOnlyIMA::`vftable';
        if ( v137 )
          (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
        v144 = &v138;
LABEL_46:
        if ( v138 )
          (**v138)(v138, 1);
        return 0;
      }
      ReportImpersonationError(a5, a6, v133, Src);
    }
    if ( (_WORD)v133 )
    {
      if ( Src && (unsigned __int64)(__int16)v133 <= 0x102 )
      {
        memmove(v205, Src, (__int16)v133);
        goto LABEL_59;
      }
      memset_0(v205, 0, 0x102u);
      if ( Src )
      {
        if ( (unsigned __int64)(__int16)v133 <= 0x102 )
          goto LABEL_59;
        *_errno() = 34;
      }
      else
      {
        *_errno() = 22;
      }
      _invalid_parameter_noinfo();
    }
LABEL_59:
    if ( (v46 & 0xFFFFFFFFFFFFFFFEuLL) >= 0x102 )
      _report_rangecheckfailure();
    *(wchar_t *)((char *)v205 + (v46 & 0xFFFFFFFFFFFFFFFEuLL)) = 0;
    if ( v131 != 5 )
    {
      v163 = v205;
      v164 = v46;
      LOBYTE(a4) = 1;
      v47 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD, __int64))(*(_QWORD *)v42 + 224LL))(
              v42,
              &v163,
              0,
              a4);
      v48 = v47;
      v154 = (void (__fastcall ****)(_QWORD, __int64))v47;
      if ( v47 )
      {
        v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
        v50 = v49;
        if ( v49 && (unsigned int)(v49 - 3) > 1 )
        {
          v51 = v131;
        }
        else
        {
          if ( a8 )
          {
            v136 = &AutoReadOnlyIMA::`vftable';
            if ( v137 )
              (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
            v144 = &v138;
            goto LABEL_46;
          }
          v51 = v131;
          *(_QWORD *)v111 = v205;
          LODWORD(v110) = v46;
          if ( v131 == 2 )
            ex_raise(151, 57, 16, 1, v110, *(_QWORD *)v111);
          else
            ex_raise(155, 17, 16, 1, v110, *(_QWORD *)v111);
        }
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 32LL))(v48, &v147);
        if ( v147 > 1 && (v147 != 7 || !byte_102EDCC6E || (*((_BYTE *)qword_102ECFB10 + 1442) & 0x10) != 0) )
        {
          if ( a8 )
          {
            v136 = &AutoReadOnlyIMA::`vftable';
            if ( v137 )
              (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
            v144 = &v138;
            goto LABEL_46;
          }
          *(_QWORD *)v111 = v205;
          LODWORD(v110) = v46;
          if ( v51 == 2 )
          {
            v52 = 57;
            v53 = 151;
          }
          else
          {
            v52 = 17;
            v53 = 155;
          }
          ex_raise(v53, v52, 16, 1, v110);
        }
        v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 72LL))(v48);
        v44 = v147;
        if ( v54 )
        {
          v55 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v48 + 56LL))(v48, &pSid, 85);
          v56 = v55;
          v132 = v55;
        }
        else
        {
          v56 = v132;
        }
        if ( v44 == 1 )
        {
          if ( !PwchLocateBackSlash(v205, v46 >> 1) )
          {
            v139 = 258;
            getsusername((unsigned __int8 *)&pSid, v56, v205, (int *)&v139, 0);
            LODWORD(v46) = v139;
          }
        }
        else
        {
          if ( !v44 )
          {
            v57 = v131;
            if ( v131 == 2
              && ((unsigned int (__fastcall *)(unsigned int (__fastcall ***)(_QWORD), _QWORD, __int64))(*v141)[44])(
                   v141,
                   v142,
                   1) != 1 )
            {
              LODWORD(v110) = v133;
              ex_raise(151, 57, 16, 1, v110, Src);
            }
            if ( !v56 || v50 == 2 )
            {
              v61 = v141;
              if ( ((unsigned int (__fastcall *)(unsigned int (__fastcall ***)(_QWORD), _QWORD, __int64))(*v141)[44])(
                     v141,
                     v142,
                     1) == 2 )
              {
                if ( a8 )
                {
                  v136 = &AutoReadOnlyIMA::`vftable';
                  if ( v137 )
                    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
                  v144 = &v138;
                  goto LABEL_46;
                }
                ReportImpersonationError(a5, v131, v133, Src);
              }
              LoginToken = CreateLoginToken(L"public", 0xCu, v131 == 2, 1, 0, 0);
              v135 = LoginToken;
              v43 = v132;
LABEL_154:
              if ( PwchLocateBackSlash(v205, (unsigned __int64)(int)v46 >> 1) )
              {
                if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                         + SystemThread_TlsIndex)
                                                       + SystemThread_TlsOffset)
                                           + 72LL)
                               + 270LL)
                    & 4) != 0 )
                  CSqlFilter::RaiseException(405, 14, 32, L"WINDOWS AUTHENTICATION");
                if ( v57 == 2 && !(**v61)(v61) )
                {
                  LODWORD(v110) = v133;
                  ex_raise(151, 57, 16, 1, v110, Src);
                }
                LoginToken = CreateLoginToken(v205, v139, v57 == 2, 1, 0, 0);
                if ( v135 )
                {
                  v87 = (__int64)v135 + *(int *)(*((_QWORD *)v135 + 2) + 4LL) + 16;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 8LL))(v87);
                }
                v135 = LoginToken;
                goto LABEL_267;
              }
              if ( v44 == 7 )
              {
LABEL_267:
                if ( !LoginToken )
                  goto LABEL_273;
                v93 = (const wchar_t *)Src;
                v94 = v133;
LABEL_269:
                if ( !(*(unsigned int (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 8LL))(LoginToken)
                  || (*(unsigned int (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 8LL))(LoginToken) == 1
                  || (*(unsigned int (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 8LL))(LoginToken) == 7
                  || (*(unsigned int (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 192LL))(LoginToken) == 2 )
                {
                  v103 = a8;
                  v104 = v131;
                  goto LABEL_279;
                }
LABEL_273:
                v103 = a8;
                if ( a8 )
                {
                  v136 = &AutoReadOnlyIMA::`vftable';
                  if ( v137 )
                    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
                  v144 = &v138;
LABEL_175:
                  if ( v138 )
                    (**v138)(v138, 1);
                  goto LABEL_177;
                }
                v93 = (const wchar_t *)Src;
                v94 = v133;
                v104 = v131;
                ReportImpersonationError(a5, v131, v133, Src);
LABEL_279:
                if ( !a7 )
                {
LABEL_299:
                  v136 = &AutoReadOnlyIMA::`vftable';
                  if ( v137 )
                    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
                  v157 = (struct IMetadataAccessor *)&v138;
                  if ( v138 )
                    (**v138)(v138, 1);
                  goto LABEL_303;
                }
                v105 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset;
                v106 = *(_QWORD *)(v105 + 256);
                if ( !v106 )
                {
                  SystemThread::MakeMiniSOSThread(0);
                  v106 = *(_QWORD *)(v105 + 256);
                }
                DefaultMetadataAccessor = GetDefaultMetadataAccessor(*(struct IMemObj **)(v106 + 1000), v150);
                v157 = DefaultMetadataAccessor;
                if ( v154 )
                {
                  v108 = ((__int64 (__fastcall *)(void (__fastcall ****)(_QWORD, __int64)))(*v154)[1])(v154);
                  v129 = 0;
                  v128 = 0;
                  v127 = 0;
                  v126 = 0;
                  LODWORD(v125) = 0;
                  LOBYTE(v124) = 0;
                  LODWORD(v123) = 0;
                  LODWORD(v122) = 0;
                  LODWORD(v121) = 0;
                  LODWORD(v120) = -1;
                  LODWORD(v119) = 0;
                  LODWORD(v118) = 0;
                  v117 = 0;
                  LODWORD(v116) = 0;
                  LODWORD(v115) = 30;
                  v114 = 0;
                  v113 = 0;
                  LOBYTE(v112) = 1;
                  if ( (unsigned __int8)ISECManager::AccessCheckWithAuditState(
                                          DefaultMetadataAccessor,
                                          v142,
                                          v108,
                                          7,
                                          0) )
                    goto LABEL_296;
                }
                else if ( (**v141)(v141) )
                {
LABEL_296:
                  if ( DefaultMetadataAccessor )
                    (*(void (__fastcall **)(struct IMetadataAccessor *, __int64))(*(_QWORD *)DefaultMetadataAccessor
                                                                                + 24LL))(
                      DefaultMetadataAccessor,
                      1);
                  LoginToken = v135;
                  goto LABEL_299;
                }
                if ( v103 )
                {
                  if ( DefaultMetadataAccessor )
                    (*(void (__fastcall **)(struct IMetadataAccessor *, __int64))(*(_QWORD *)DefaultMetadataAccessor
                                                                                + 24LL))(
                      DefaultMetadataAccessor,
                      1);
                  v136 = &AutoReadOnlyIMA::`vftable';
                  if ( v137 )
                    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
                  v157 = (struct IMetadataAccessor *)&v138;
                  if ( v138 )
                    (**v138)(v138, 1);
                  if ( !v135 )
                    return 0;
                  v32 = (__int64)v135 + *(int *)(*((_QWORD *)v135 + 2) + 4LL) + 16;
                  goto LABEL_28;
                }
                ReportImpersonationError(a5, v104, v94, v93);
                goto LABEL_296;
              }
              v88 = v158;
              if ( v158 )
              {
                MasterDbId = GetMasterDbId();
                LoginTokenFromFederatedContext = CreateLoginTokenFromFederatedContext(v88, v145, MasterDbId);
                if ( LoginToken )
                {
                  v91 = (char *)LoginToken + *(int *)(*((_QWORD *)LoginToken + 2) + 4LL) + 16;
                  (*(void (__fastcall **)(char *))(*(_QWORD *)v91 + 8LL))(v91);
                }
LABEL_167:
                LoginToken = (struct ILoginToken *)LoginTokenFromFederatedContext;
                v135 = (struct ILoginToken *)LoginTokenFromFederatedContext;
                goto LABEL_267;
              }
              if ( v57 != 5 )
                goto LABEL_242;
              if ( !a12 )
              {
                v92 = a16;
                if ( !a16 )
                {
                  if ( a8 )
                  {
                    v136 = &AutoReadOnlyIMA::`vftable';
                    if ( v137 )
                      (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
                    v144 = &v138;
                    goto LABEL_175;
                  }
                  v93 = (const wchar_t *)Src;
                  v94 = v133;
                  LODWORD(v110) = v133;
                  ex_raise(406, 97, 16, 1, v110, Src);
LABEL_243:
                  if ( (!v43
                     || !(unsigned int)FIsGatewaySID((const unsigned __int8 *)&pSid, v43)
                     && !FIsOrphanedUserSid(&pSid, v43))
                    && (v145 != 1 || v43 != 16 && (!byte_102EDCC3D || v43 != 18 || (_WORD)v199 != 0xDEAA)) )
                  {
                    if ( !*(_DWORD *)(GetXdbServerGlobals(v86) + 11976) || byte_102EDCC04 || !byte_102EDCC22 )
                      goto LABEL_267;
                    v101 = 8LL * SystemThread_TlsIndex;
                    if ( !*(_QWORD *)(SystemThread_TlsOffset
                                    + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v101))
                      || !*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v101))
                                    + 72LL)
                      || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                           + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                       + v101))
                                               + 72LL)
                                   + 270LL)
                        & 2) == 0
                      || !v141
                      || !(**v141)(v141)
                      || wcsncmp(v93, L"dbo", (unsigned __int64)(int)v94 >> 1)
                      && wcsncmp(v93, L"cdc", (unsigned __int64)(int)v94 >> 1)
                      || v43 == 1 && (_BYTE)pSid == 1 )
                    {
                      LoginToken = v135;
                      goto LABEL_267;
                    }
                    LoginToken = v135;
                    if ( v135 )
                      goto LABEL_269;
                  }
                  LOBYTE(v117) = 0;
                  LoginTokenFromFederatedContext = CreateLoginTokenFromSid(
                                                     &pSid,
                                                     (unsigned int)v43,
                                                     0,
                                                     0,
                                                     1,
                                                     v144,
                                                     v152,
                                                     v145,
                                                     0,
                                                     0,
                                                     v151,
                                                     v117,
                                                     0);
                  if ( LoginToken )
                  {
                    v102 = (char *)LoginToken + *(int *)(*((_QWORD *)LoginToken + 2) + 4LL) + 16;
                    (*(void (__fastcall **)(char *))(*(_QWORD *)v102 + 8LL))(v102);
                    LoginToken = (struct ILoginToken *)LoginTokenFromFederatedContext;
                    v135 = (struct ILoginToken *)LoginTokenFromFederatedContext;
                    goto LABEL_267;
                  }
                  goto LABEL_167;
                }
                if ( a16 > 85 )
                {
                  v136 = &AutoReadOnlyIMA::`vftable';
                  if ( v137 )
                    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
                  v144 = &v138;
                  goto LABEL_175;
                }
                if ( v159 && (unsigned __int64)a16 <= 0x55 )
                {
                  memmove(&pSid, v159, a16);
                }
                else
                {
                  pSid = 0;
                  v199 = 0;
                  v200 = 0;
                  v201 = 0;
                  v202 = 0;
                  v203 = 0;
                  v204 = 0;
                  if ( v159 )
                  {
                    if ( (unsigned __int64)a16 > 0x55 )
                    {
                      *_errno() = 34;
                      _invalid_parameter_noinfo();
                    }
                  }
                  else
                  {
                    *_errno() = 22;
                    _invalid_parameter_noinfo();
                  }
                }
                goto LABEL_222;
              }
              if ( (__int16)a12 > 256 )
              {
                v136 = &AutoReadOnlyIMA::`vftable';
                if ( v137 )
                  (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
                v144 = &v138;
                goto LABEL_175;
              }
              if ( (_WORD)a12 )
              {
                v95 = v160;
                if ( !v160 || (unsigned __int64)(__int16)a12 > 0x102 )
                {
                  memset_0(v205, 0, 0x102u);
                  if ( v95 )
                  {
                    if ( (unsigned __int64)(__int16)a12 <= 0x102 )
                      goto LABEL_204;
                    *_errno() = 34;
                  }
                  else
                  {
                    *_errno() = 22;
                  }
                  _invalid_parameter_noinfo();
                  goto LABEL_204;
                }
                memmove(v205, v160, (__int16)a12);
              }
LABEL_204:
              if ( ((__int16)a12 & 0xFFFFFFFC) > 0x164 )
              {
                _mm_lfence();
                v111[0] = (__int16)a12;
                ex_raise(405, 3, 16, 0, L"SID", *(_QWORD *)v111, v205, L"VARBINARY[512]");
                LoginToken = v135;
              }
              if ( (unsigned int)(__int16)a12 < 4 || v205[0] != 48 || v205[1] != 120 || (a12 & 3) != 0 )
              {
                v111[0] = (__int16)a12;
                ex_raise(405, 3, 16, 1, L"SID", *(_QWORD *)v111, v205, L"VARBINARY[512]");
              }
              v96 = 0;
              v97 = 2;
              if ( (unsigned int)(__int16)a12 >> 1 > 2 )
              {
                _mm_lfence();
                v98 = &v206;
                do
                {
                  v99 = *(unsigned __int16 *)v98;
                  if ( (v99 & 0xFF80) != 0 || *((_BYTE *)qword_10259F0C0 + v99) == 0xF8 )
                  {
                    v111[0] = (__int16)a12;
                    ex_raise(405, 3, 16, 2, L"SID", *(_QWORD *)v111, v205, L"VARBINARY[28]");
                    LOWORD(v99) = *(_WORD *)v98;
                  }
                  v100 = (char *)&pSid + v96;
                  if ( (v97 & 1) != 0 )
                  {
                    *v100 |= *((_BYTE *)qword_10259F0C0 + (unsigned __int16)v99);
                    ++v96;
                  }
                  else
                  {
                    *v100 = 16 * *((_BYTE *)qword_10259F0C0 + (unsigned __int16)v99);
                  }
                  ++v97;
                  v98 += 2;
                }
                while ( v97 < (unsigned int)(__int16)a12 >> 1 );
                LoginToken = v135;
              }
              v92 = (unsigned __int16)v96;
LABEL_222:
              v132 = v92;
              if ( (!IsValidSid(&pSid)
                 || (_BYTE)pSid != 1
                 || ((BYTE1(pSid) - 2) & 0xFB) != 0
                 || (_WORD)v92 != 32
                 || BYTE7(pSid) != 100
                 || BYTE6(pSid) > 1u
                 || BYTE5(pSid) > 1u
                 || *(_WORD *)((char *)&pSid + 3)
                 || BYTE2(pSid))
                && (v145 != 1 || (_WORD)v92 != 16 && (!byte_102EDCC3D || (_WORD)v92 != 18 || (_WORD)v199 != 0xDEAA)) )
              {
                if ( a8 )
                {
                  v136 = &AutoReadOnlyIMA::`vftable';
                  if ( v137 )
                    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v137)(v137, 1);
                  v144 = &v138;
                  goto LABEL_175;
                }
                ex_raise(405, 6, 16, 0);
              }
              v43 = v132;
LABEL_242:
              v93 = (const wchar_t *)Src;
              v94 = v133;
              goto LABEL_243;
            }
            v58 = v150;
            v59 = *(_QWORD *)v150;
            v111[0] = 0;
            LOBYTE(v110) = 1;
            v60 = (struct IMEDLogin *)(*(__int64 (__fastcall **)(struct IMetadataAccess *, __int128 *, _QWORD, _QWORD, _DWORD, _QWORD))(v59 + 344))(
                                        v150,
                                        &pSid,
                                        (unsigned int)v56,
                                        0,
                                        (_DWORD)v110,
                                        *(_QWORD *)v111);
            if ( v60 )
            {
              LoginToken = CreateLoginToken(v58, v60, v131 == 2, 1, 0, 0);
              v135 = LoginToken;
            }
            v43 = v132;
LABEL_153:
            v61 = v141;
            goto LABEL_154;
          }
          if ( v44 == 7 && byte_102EDCC6E && (*((_BYTE *)qword_102ECFB10 + 1442) & 0x10) == 0 )
          {
            ThreadLocalStoragePointer = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
            v63 = 8LL * SystemThread_TlsIndex;
            v64 = *(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)&ThreadLocalStoragePointer[v63]) + 72LL);
            v65 = *(_BYTE **)(v64 + 96);
            FeatureExtension = 0;
            if ( v65 )
            {
              LOBYTE(ThreadLocalStoragePointer) = 2;
              FeatureExtension = (const struct CFedAuthFeatureExtension *)CPhysicalConnection::GetFeatureExtension(
                                                                            *(_QWORD *)(v64 + 96),
                                                                            ThreadLocalStoragePointer);
            }
            if ( !(unsigned int)FIsFedAuthScenarioSupported(
                                  *(const struct CCompExecCtxtBasic **)(SystemThread_TlsOffset
                                                                      + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                  + v63)),
                                  FeatureExtension) )
              ex_raise(331, 71, 16, 1);
            v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v68 = *(_QWORD *)(v67 + 256);
            if ( !v68 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v68 = *(_QWORD *)(v67 + 256);
            }
            v69 = *(_QWORD *)(v68 + 1000);
            v197 = pSid;
            pguid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
            CoCreateGuid(&pguid);
            v153 = 0;
            v156 = 0;
            v130[0] = 0;
            v134[0] = 0;
            v155 = 0;
            v148 = 0;
            v149 = 0;
            v143 = 0;
            v71 = byte_102EDCA53
               && v65
               && v65[50]
               && !*(_DWORD *)(GetXdbServerGlobals(v70) + 11976)
               && !IsBoxAADEnabled(0);
            v72 = dword_102EF4298;
            do
            {
              v73 = v72 & 0xFFFFFFFE;
              v74 = (__m128i)xmmword_102EF4288;
              _InterlockedOr(v109, 0);
              v72 = dword_102EF4298;
            }
            while ( v73 != dword_102EF4298 );
            if ( *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1 == v74.m128i_i64[0]
              && *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 == _mm_srli_si128(v74, 8).m128i_u64[0] )
            {
              v162 = 0;
              v75 = *(_QWORD *)s_pServerConf;
              *(_QWORD *)v111 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, wchar_t **))(v75 + 528))(
                     s_pServerConf,
                     L"FederatedAuthentication",
                     L"AADServerAdminSid",
                     v69,
                     &v161) )
              {
                v76 = v161;
                if ( v161 )
                  operator delete[](0);
              }
              else
              {
                v76 = 0;
              }
              v162 = v76;
              v74 = *(__m128i *)AzureActiveDirectoryService::StringToGuid(&v168, v76);
              operator delete[](v76);
            }
            v77 = 0;
            if ( FeatureExtension )
              v77 = *((_QWORD *)FeatureExtension + 7);
            v167 = v74;
            LODWORD(v46) = v139;
            FederatedContextInternalWithRetry = FedAuthTicketService::GetFederatedContextInternalWithRetry(
                                                  v69,
                                                  (unsigned int)v205,
                                                  v139,
                                                  (unsigned int)&v197,
                                                  v77,
                                                  v111[0],
                                                  (__int64)&pguid,
                                                  (__int64)v65,
                                                  0,
                                                  (__int64)&v167,
                                                  0,
                                                  (__int64)&v153,
                                                  (__int64)&v156,
                                                  (__int64)v130,
                                                  (__int64)v134,
                                                  (__int64)&v148,
                                                  (__int64)&v149,
                                                  (__int64)&v143,
                                                  (__int64)&v155,
                                                  0,
                                                  v71);
            v80 = 4;
            if ( (qword_102EDC9EC & 0x200000000000LL) != 0 )
            {
              v196 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
              if ( v65 )
                v196 = *(GUID *)(*(_QWORD *)((*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v65 + 16LL))(v65) + 448)
                               + 28LL);
              v170 = 0x40000;
              v171 = 0;
              v172 = &v175;
              v173 = &v187;
              v188 = 0;
              v174 = 0;
              v189 = 0;
              v175 = &v190;
              v176 = 39;
              v177 = 3;
              v178 = &Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
              v179 = 16;
              v180 = 5;
              p_pguid = &Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
              v182 = 16;
              v183 = 6;
              v184 = 0;
              v185 = 0;
              v186 = 7;
              v81 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                        + SystemThread_TlsIndex)
                                                      + SystemThread_TlsOffset)
                                          + 72LL)
                              + 192LL);
              if ( v81 )
              {
                v82 = v81 + *(unsigned __int16 *)(v81 + 68);
                v83 = *(unsigned __int16 *)(v81 + 70);
              }
              else
              {
                v82 = 0;
                v83 = 0;
              }
              v178 = &v196;
              v190 = v143;
              p_pguid = &pguid;
              v191 = v134[0] != 0;
              v192 = v148;
              v193 = v149;
              v184 = v82;
              v185 = 2 * v83;
              v194 = FederatedContextInternalWithRetry;
              XeSqlPkg::fedauth_execute_as::Publish((XeSqlPkg::fedauth_execute_as *)v169);
              LODWORD(v46) = v139;
            }
            if ( FederatedContextInternalWithRetry )
            {
              LoginToken = v135;
            }
            else
            {
              v84 = v153;
              if ( *(_DWORD *)(GetXdbServerGlobals(v78) + 11976) )
              {
                v85 = v130[0];
                if ( byte_102EDCF29 )
                  v85 = 0;
                v130[0] = v85;
              }
              else
              {
                v85 = v130[0];
              }
              if ( v85 )
                v80 = 2;
              LoginToken = (struct ILoginToken *)CreateLoginTokenFromFederatedContext(v84, v80, v142);
              v135 = LoginToken;
            }
            operator delete[](v153);
          }
        }
        v43 = v132;
      }
    }
    v57 = v131;
    goto LABEL_153;
  }
  if ( a6 == 2 && !(**v21)(v21) )
  {
    v23 = (unsigned __int16)v142;
    if ( !(_WORD)v142 )
      v23 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                          + SystemThread_TlsIndex)
                                                        + SystemThread_TlsOffset)
                                            + 80LL)
                                + 8LL);
    v146 = 256;
    if ( v23 > 0x7FFF
      || v23 == 0x7FFF && !FAllowResourceDBChange()
      || (_mm_lfence(),
          LOBYTE(v111[0]) = 0,
          !(unsigned int)DBMgr::GetDBName(*(_QWORD *)(qword_102ECFB00 + 32), 0, v23, v207, &v146, v111[0])) )
    {
      DefaultLocale = GetDefaultLocale();
      LODWORD(v110) = v23;
      StringCchPrintf_lW(v207, 0x80u, L"%d", DefaultLocale, v110);
      v25 = -1;
      do
        ++v25;
      while ( v207[v25] );
      v146 = 2 * v25;
    }
    if ( a8 )
      return 0;
    ReportImpersonationError(0, 2, v17, a3);
  }
  v26 = CreateLoginToken((const wchar_t *)a3, v17, a6 == 2, 1, 0, 0);
  LoginToken = v26;
  v135 = v26;
  if ( !v26
    || (*(unsigned int (__fastcall **)(struct ILoginToken *))(*(_QWORD *)v26 + 8LL))(v26)
    && (*(unsigned int (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 8LL))(LoginToken) != 1
    && (*(unsigned int (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 8LL))(LoginToken) != 7 )
  {
    if ( !a8 )
    {
      ReportImpersonationError(0, a6, v17, a3);
      goto LABEL_21;
    }
LABEL_177:
    if ( !LoginToken )
      return 0;
    goto LABEL_27;
  }
LABEL_21:
  v27 = 0;
  if ( a7 )
  {
    if ( (*(unsigned int (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 192LL))(LoginToken) != 2 )
      goto LABEL_307;
    if ( !(*(unsigned int (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 88LL))(LoginToken) )
      goto LABEL_307;
    v28 = GetMasterDbId();
    v129 = 0;
    v128 = 0;
    v127 = 0;
    v126 = 0;
    LODWORD(v125) = 0;
    LOBYTE(v124) = 0;
    LODWORD(v123) = 0;
    LODWORD(v122) = 0;
    LODWORD(v121) = 0;
    LODWORD(v120) = -1;
    LODWORD(v119) = 0;
    LODWORD(v118) = 0;
    v117 = 0;
    LODWORD(v116) = 0;
    LODWORD(v115) = 30;
    v114 = 0;
    v113 = 0;
    LOBYTE(v112) = 1;
    v29 = ISECManager::AccessCheckWithAuditState(0, v28, 0, 24, 51);
    v27 = v29;
    if ( !v29 )
    {
LABEL_307:
      v30 = (*(__int64 (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 192LL))(LoginToken);
      v31 = GetMasterDbId();
      v129 = 0;
      v128 = 0;
      v127 = 0;
      v126 = 0;
      LODWORD(v125) = 0;
      LOBYTE(v124) = 0;
      LODWORD(v123) = 0;
      LODWORD(v122) = 0;
      LODWORD(v121) = 0;
      LODWORD(v120) = -1;
      LODWORD(v119) = 0;
      LODWORD(v118) = 0;
      v117 = 0;
      LODWORD(v116) = 0;
      LODWORD(v115) = 30;
      v114 = 0;
      v113 = 0;
      LOBYTE(v112) = 1;
      if ( !(unsigned __int8)ISECManager::AccessCheckWithAuditState(0, v31, v30, 29, 0) )
      {
        if ( a8 )
        {
LABEL_27:
          v32 = (__int64)LoginToken + *(int *)(*((_QWORD *)LoginToken + 2) + 4LL) + 16;
LABEL_28:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
          return 0;
        }
        ReportImpersonationError(0, v131, v17, a3);
      }
    }
    if ( v27 )
    {
      v166 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
      v34 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v35 = *(_QWORD *)(v34 + 256);
      if ( !v35 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v35 = *(_QWORD *)(v34 + 256);
      }
      v36 = *(_QWORD *)(v35 + 1000);
      v37 = (*(__int64 (__fastcall **)(struct ILoginToken *))(*(_QWORD *)LoginToken + 192LL))(LoginToken);
      v38 = GetMasterDbId();
      ISECManager::CheckPermRuleAuditOnly(1313295433, v36, v150, v38, v37, 1, 0, 0, 0, &v166, 0, 0, 0, -1);
      LoginToken = v135;
    }
  }
LABEL_303:
  v135 = 0;
  return LoginToken;
}

```

## disassembly

```asm
0x10142c680  push    rbp
0x10142c682  push    rbx
0x10142c683  push    rsi
0x10142c684  push    rdi
0x10142c685  push    r12
0x10142c687  push    r13
0x10142c689  push    r14
0x10142c68b  push    r15
0x10142c68d  lea     rbp, [rsp-6F8h]
0x10142c695  sub     rsp, 838h
0x10142c69c  mov     [rbp+730h+var_6D0], 0FFFFFFFFFFFFFFFEh
0x10142c6a4  movaps  [rsp+870h+var_50], xmm6
0x10142c6ac  mov     rax, cs:__security_cookie
0x10142c6b3  xor     rax, rsp
0x10142c6b6  mov     [rbp+730h+var_60], rax
0x10142c6bd  mov     r13d, r9d
0x10142c6c0  mov     [rbp+730h+var_7A4], r9d
0x10142c6c4  mov     r12, r8
0x10142c6c7  mov     [rbp+730h+Src], r8
0x10142c6cb  mov     r11d, edx
0x10142c6ce  mov     [rbp+730h+var_760], edx
0x10142c6d1  mov     r10, rcx
0x10142c6d4  mov     [rbp+730h+var_738], rcx
0x10142c6d8  mov     rax, [rbp+730h+arg_70]
0x10142c6df  mov     [rbp+730h+var_700], rax
0x10142c6e3  mov     rax, [rbp+730h+arg_50]
0x10142c6ea  mov     [rbp+730h+var_6F8], rax
0x10142c6ee  mov     esi, [rbp+730h+arg_28]
0x10142c6f4  mov     [rbp+730h+var_7AC], esi
0x10142c6f7  mov     rax, [rbp+730h+arg_40]
0x10142c6fe  mov     [rbp+730h+var_758], rax
0x10142c702  mov     eax, [rbp+730h+arg_48]
0x10142c708  mov     [rbp+730h+var_72C], eax
0x10142c70b  mov     eax, [rbp+730h+arg_60]
0x10142c711  mov     [rbp+730h+var_750], eax
0x10142c714  mov     rax, [rbp+730h+arg_68]
0x10142c71b  mov     [rbp+730h+var_708], rax
0x10142c71f  mov     eax, [rbp+730h+arg_80]
0x10142c725  mov     [rbp+730h+var_730], eax
0x10142c728  mov     rdx, gs:58h
0x10142c731  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10142c738  mov     ecx, [rax]
0x10142c73a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10142c741  mov     eax, [rax]
0x10142c743  add     rax, [rdx+rcx*8]
0x10142c747  mov     rax, [rax]
0x10142c74a  mov     rcx, [rax+78h]
0x10142c74e  mov     rcx, [rcx+108h]
0x10142c755  mov     [rbp+730h+var_768], rcx
0x10142c759  xor     ebx, ebx
0x10142c75b  mov     r14d, ebx
0x10142c75e  mov     [rbp+730h+var_798], rbx
0x10142c762  cmp     [rbp+730h+arg_20], ebx
0x10142c768  jnz     loc_10142CB5F
0x10142c76e  movzx   r15d, [rbp+730h+arg_38]
0x10142c776  cmp     esi, 2
0x10142c779  jnz     loc_10142C86B
0x10142c77f  mov     rax, [rcx]
0x10142c782  call    qword ptr [rax]
0x10142c784  test    eax, eax
0x10142c786  jnz     loc_10142C86B
0x10142c78c  movzx   edi, word ptr [rbp+730h+var_760]
0x10142c790  test    edi, edi
0x10142c792  jnz     short loc_10142C7BE
0x10142c794  mov     rdx, gs:58h
0x10142c79d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10142c7a4  mov     ecx, [rax]
0x10142c7a6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10142c7ad  mov     eax, [rax]
0x10142c7af  add     rax, [rdx+rcx*8]
0x10142c7b3  mov     rax, [rax]
0x10142c7b6  mov     rcx, [rax+50h]
0x10142c7ba  movzx   edi, word ptr [rcx+8]
0x10142c7be  mov     [rbp+730h+var_74C], 100h
0x10142c7c5  cmp     edi, 7FFFh
0x10142c7cb  ja      short loc_10142C80B
0x10142c7cd  jnz     short loc_10142C7D8
0x10142c7cf  call    ?FAllowResourceDBChange@@YA_NXZ; FAllowResourceDBChange(void)
0x10142c7d4  test    al, al
0x10142c7d6  jz      short loc_10142C80B
0x10142c7d8  lfence
0x10142c7db  mov     byte ptr [rsp+870h+var_848], 0
0x10142c7e0  lea     rax, [rbp+730h+var_74C]
0x10142c7e4  mov     [rsp+870h+var_850], rax
0x10142c7e9  lea     r9, [rbp+730h+var_260]
0x10142c7f0  mov     r8d, edi
0x10142c7f3  mov     rdx, rbx
0x10142c7f6  mov     rcx, cs:qword_102ECFB00
0x10142c7fd  mov     rcx, [rcx+20h]
0x10142c801  call    cs:__imp_?GetDBName@DBMgr@@QEAAHVContextHandle@@KPEA_WPEAK_N@Z; DBMgr::GetDBName(ContextHandle,ulong,wchar_t *,ulong *,bool)
0x10142c807  test    eax, eax
0x10142c809  jnz     short loc_10142C850
0x10142c80b  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10142c811  mov     r9, rax; struct __crt_locale_pointers *
0x10142c814  mov     dword ptr [rsp+870h+var_850], edi
0x10142c818  lea     r8, aD_22; "%d"
0x10142c81f  mov     edx, 80h; unsigned __int64
0x10142c824  lea     rcx, [rbp+730h+var_260]; wchar_t *
0x10142c82b  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x10142c830  lea     rax, [rbp+730h+var_260]
0x10142c837  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x10142c83e  xchg    ax, ax
0x10142c840  inc     rdi
0x10142c843  cmp     word ptr [rax+rdi*2], 0
0x10142c848  jnz     short loc_10142C840
0x10142c84a  add     rdi, rdi
0x10142c84d  mov     [rbp+730h+var_74C], edi
0x10142c850  test    r15b, r15b
0x10142c853  jnz     loc_10142CC85
0x10142c859  mov     r9, r12
0x10142c85c  mov     r8d, r13d
0x10142c85f  mov     edx, 2
0x10142c864  xor     ecx, ecx
0x10142c866  call    ?ReportImpersonationError@@YAXW4EPrincipalType@@W4EImpersonationType@@KPEB_W@Z; ReportImpersonationError(EPrincipalType,EImpersonationType,ulong,wchar_t const *)
0x10142c86b  mov     r8d, ebx
0x10142c86e  cmp     esi, 2
0x10142c871  setz    r8b; int
0x10142c875  mov     [rsp+870h+var_848], ebx; unsigned int
0x10142c879  mov     dword ptr [rsp+870h+var_850], ebx; int
0x10142c87d  mov     r9d, 1; int
0x10142c883  mov     edx, r13d; unsigned int
0x10142c886  mov     rcx, r12; wchar_t *
0x10142c889  call    ?CreateLoginToken@@YAPEAVILoginToken@@PEB_WKHHHK@Z; CreateLoginToken(wchar_t const *,ulong,int,int,int,ulong)
0x10142c88e  mov     r14, rax
0x10142c891  mov     [rbp+730h+var_798], rax
0x10142c895  test    rax, rax
0x10142c898  jz      short loc_10142C8C3
0x10142c89a  mov     rax, [rax]
0x10142c89d  mov     rcx, r14
0x10142c8a0  call    qword ptr [rax+8]
0x10142c8a3  test    eax, eax
0x10142c8a5  jz      short loc_10142C8DB
0x10142c8a7  mov     rax, [r14]
0x10142c8aa  mov     rcx, r14
0x10142c8ad  call    qword ptr [rax+8]
0x10142c8b0  cmp     eax, 1
0x10142c8b3  jz      short loc_10142C8DB
0x10142c8b5  mov     rax, [r14]
0x10142c8b8  mov     rcx, r14
0x10142c8bb  call    qword ptr [rax+8]
0x10142c8be  cmp     eax, 7
0x10142c8c1  jz      short loc_10142C8DB
0x10142c8c3  test    r15b, r15b
0x10142c8c6  jnz     loc_10142D725
0x10142c8cc  mov     r9, r12
0x10142c8cf  mov     r8d, r13d
0x10142c8d2  mov     edx, esi
0x10142c8d4  xor     ecx, ecx
0x10142c8d6  call    ?ReportImpersonationError@@YAXW4EPrincipalType@@W4EImpersonationType@@KPEB_W@Z; ReportImpersonationError(EPrincipalType,EImpersonationType,ulong,wchar_t const *)
0x10142c8db  mov     esi, ebx
0x10142c8dd  cmp     [rbp+730h+arg_30], ebx
0x10142c8e3  jz      loc_10142DFCE
0x10142c8e9  mov     rax, [r14]
0x10142c8ec  mov     rcx, r14
0x10142c8ef  call    qword ptr [rax+0C0h]
0x10142c8f5  cmp     eax, 2
0x10142c8f8  jnz     loc_10142C9AA
0x10142c8fe  mov     rax, [r14]
0x10142c901  mov     rcx, r14
0x10142c904  call    qword ptr [rax+58h]
0x10142c907  test    eax, eax
0x10142c909  jz      loc_10142C9AA
0x10142c90f  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x10142c915  movzx   edx, ax
0x10142c918  mov     [rsp+870h+var_7B8], rbx
0x10142c920  mov     [rsp+870h+var_7C0], rbx
0x10142c928  mov     [rsp+870h+var_7C8], rbx
0x10142c930  mov     [rsp+870h+var_7D0], ebx
0x10142c937  mov     dword ptr [rsp+870h+var_7D8], ebx
0x10142c93e  mov     byte ptr [rsp+870h+var_7E0], bl
0x10142c945  mov     dword ptr [rsp+870h+var_7E8], ebx
0x10142c94c  mov     dword ptr [rsp+870h+var_7F0], ebx
0x10142c953  mov     dword ptr [rsp+870h+var_7F8], ebx
0x10142c957  mov     dword ptr [rsp+870h+var_800], 0FFFFFFFFh
0x10142c95f  mov     dword ptr [rsp+870h+var_808], ebx
0x10142c963  mov     dword ptr [rsp+870h+var_810], ebx
0x10142c967  mov     [rsp+870h+var_818], rbx
0x10142c96c  mov     dword ptr [rsp+870h+var_820], ebx
0x10142c970  mov     dword ptr [rsp+870h+var_828], 1Eh
0x10142c978  mov     [rsp+870h+var_830], rbx
0x10142c97d  mov     [rsp+870h+var_838], rbx
0x10142c982  mov     byte ptr [rsp+870h+var_840], 1
0x10142c987  mov     dword ptr [rsp+870h+var_850], 33h ; '3'
0x10142c98f  mov     r9d, 18h
0x10142c995  xor     r8d, r8d
0x10142c998  xor     ecx, ecx
0x10142c99a  call    ?AccessCheckWithAuditState@ISECManager@@SAEPEAUIMetadataAccessor@@KKW4ESECObjectClass@@W4ESECPermissionAction@@AEAEEPEAVIUserToken@@PEAVISecContextToken@@1KPEAKKKKHW4MDObjectType@@JEHH6PEA_NPEAVCExternalPermissionCheckContext@@@Z; ISECManager::AccessCheckWithAuditState(IMetadataAccessor *,ulong,ulong,ESECObjectClass,ESECPermissionAction,uchar &,uchar,IUserToken *,ISecContextToken *,ESECObjectClass,ulong,ulong *,ulong,ulong,ulong,int,MDObjectType,long,uchar,int,int,ulong *,bool *,CExternalPermissionCheckContext *)
0x10142c99f  movzx   esi, al
0x10142c9a2  test    al, al
0x10142c9a4  jnz     loc_10142CAA0
0x10142c9aa  mov     rax, [r14]
0x10142c9ad  mov     rcx, r14
0x10142c9b0  call    qword ptr [rax+0C0h]
0x10142c9b6  mov     edi, eax
0x10142c9b8  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x10142c9be  movzx   edx, ax
0x10142c9c1  mov     [rsp+870h+var_7B8], rbx
0x10142c9c9  mov     [rsp+870h+var_7C0], rbx
0x10142c9d1  mov     [rsp+870h+var_7C8], rbx
0x10142c9d9  mov     [rsp+870h+var_7D0], ebx
0x10142c9e0  mov     dword ptr [rsp+870h+var_7D8], ebx
0x10142c9e7  mov     byte ptr [rsp+870h+var_7E0], 0
0x10142c9ef  mov     dword ptr [rsp+870h+var_7E8], ebx
0x10142c9f6  mov     dword ptr [rsp+870h+var_7F0], ebx
0x10142c9fd  mov     dword ptr [rsp+870h+var_7F8], ebx
0x10142ca01  mov     dword ptr [rsp+870h+var_800], 0FFFFFFFFh
0x10142ca09  mov     dword ptr [rsp+870h+var_808], ebx
0x10142ca0d  mov     dword ptr [rsp+870h+var_810], ebx
0x10142ca11  mov     [rsp+870h+var_818], rbx
0x10142ca16  mov     dword ptr [rsp+870h+var_820], ebx
0x10142ca1a  mov     dword ptr [rsp+870h+var_828], 1Eh
0x10142ca22  mov     [rsp+870h+var_830], rbx
0x10142ca27  mov     [rsp+870h+var_838], rbx
0x10142ca2c  mov     byte ptr [rsp+870h+var_840], 1
0x10142ca31  mov     dword ptr [rsp+870h+var_850], ebx
0x10142ca35  mov     r9d, 1Dh
0x10142ca3b  mov     r8d, edi
0x10142ca3e  xor     ecx, ecx
0x10142ca40  call    ?AccessCheckWithAuditState@ISECManager@@SAEPEAUIMetadataAccessor@@KKW4ESECObjectClass@@W4ESECPermissionAction@@AEAEEPEAVIUserToken@@PEAVISecContextToken@@1KPEAKKKKHW4MDObjectType@@JEHH6PEA_NPEAVCExternalPermissionCheckContext@@@Z; ISECManager::AccessCheckWithAuditState(IMetadataAccessor *,ulong,ulong,ESECObjectClass,ESECPermissionAction,uchar &,uchar,IUserToken *,ISecContextToken *,ESECObjectClass,ulong,ulong *,ulong,ulong,ulong,int,MDObjectType,long,uchar,int,int,ulong *,bool *,CExternalPermissionCheckContext *)
0x10142ca45  test    al, al
0x10142ca47  jnz     short loc_10142CAA0
0x10142ca49  test    r15b, r15b
0x10142ca4c  jz      short loc_10142CA90
0x10142ca4e  mov     rax, [r14+10h]
0x10142ca52  movsxd  rcx, dword ptr [rax+4]
0x10142ca56  add     rcx, 10h
0x10142ca5a  add     rcx, r14
0x10142ca5d  mov     rax, [rcx]
0x10142ca60  call    qword ptr [rax+8]
0x10142ca63  xor     eax, eax
0x10142ca65  mov     rcx, [rbp+730h+var_60]
0x10142ca6c  xor     rcx, rsp; StackCookie
0x10142ca6f  call    __security_check_cookie
0x10142ca74  movaps  xmm6, [rsp+870h+var_50]
0x10142ca7c  add     rsp, 838h
0x10142ca83  pop     r15
0x10142ca85  pop     r14
0x10142ca87  pop     r13
0x10142ca89  pop     r12
0x10142ca8b  pop     rdi
0x10142ca8c  pop     rsi
0x10142ca8d  pop     rbx
0x10142ca8e  pop     rbp
0x10142ca8f  retn
0x10142ca90  mov     r9, r12
0x10142ca93  mov     r8d, r13d
0x10142ca96  mov     edx, [rbp+730h+var_7AC]
0x10142ca99  xor     ecx, ecx
0x10142ca9b  call    ?ReportImpersonationError@@YAXW4EPrincipalType@@W4EImpersonationType@@KPEB_W@Z; ReportImpersonationError(EPrincipalType,EImpersonationType,ulong,wchar_t const *)
0x10142caa0  test    esi, esi
0x10142caa2  jz      loc_10142DFCE
0x10142caa8  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data1; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x10142caaf  movaps  [rbp+730h+var_6C0], xmm0
0x10142cab3  mov     rdx, gs:58h
0x10142cabc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10142cac3  mov     ecx, [rax]
0x10142cac5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10142cacc  mov     edi, [rax]
0x10142cace  add     rdi, [rdx+rcx*8]
0x10142cad2  mov     rsi, [rdi+100h]
0x10142cad9  test    rsi, rsi
0x10142cadc  jnz     short loc_10142CAED
0x10142cade  xor     ecx, ecx
0x10142cae0  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10142cae6  mov     rsi, [rdi+100h]
0x10142caed  mov     rsi, [rsi+3E8h]
0x10142caf4  mov     rax, [r14]
0x10142caf7  mov     rcx, r14
0x10142cafa  call    qword ptr [rax+0C0h]
0x10142cb00  mov     edi, eax
0x10142cb02  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x10142cb08  movzx   r9d, ax
0x10142cb0c  mov     dword ptr [rsp+870h+var_808], 0FFFFFFFFh
0x10142cb14  mov     [rsp+870h+var_810], rbx
0x10142cb19  mov     dword ptr [rsp+870h+var_818], ebx
0x10142cb1d  mov     [rsp+870h+var_820], rbx
0x10142cb22  lea     rax, [rbp+730h+var_6C0]
0x10142cb26  mov     [rsp+870h+var_828], rax
0x10142cb2b  mov     [rsp+870h+var_830], rbx
0x10142cb30  mov     [rsp+870h+var_838], rbx
0x10142cb35  mov     dword ptr [rsp+870h+var_840], ebx
0x10142cb39  mov     [rsp+870h+var_848], 1
0x10142cb41  mov     dword ptr [rsp+870h+var_850], edi
0x10142cb45  mov     r8, [rbp+730h+var_738]
0x10142cb49  mov     rdx, rsi
0x10142cb4c  mov     ecx, 4E474C49h
0x10142cb51  call    ?CheckPermRuleAuditOnly@ISECManager@@SAXW4ESECSecuredOperation@@PEAVIMemObj@@PEAVIMetadataAccess@@KKHW4EObjType@@PEAUAuditEventInfo@@_JU_GUID@@PEAVBatchAuditAdditionalInfo@@HPEAVBaseXact@@K@Z; ISECManager::CheckPermRuleAuditOnly(ESECSecuredOperation,IMemObj *,IMetadataAccess *,ulong,ulong,int,EObjType,AuditEventInfo *,__int64,_GUID,BatchAuditAdditionalInfo *,int,BaseXact *,ulong)
0x10142cb56  mov     r14, [rbp+730h+var_798]
0x10142cb5a  jmp     loc_10142DFCE
0x10142cb5f  lea     rax, ??_7AutoReadOnlyIMA@@6B@; const AutoReadOnlyIMA::`vftable'
0x10142cb66  mov     [rbp+730h+var_790], rax
0x10142cb6a  mov     [rbp+730h+var_788], rbx
0x10142cb6e  lea     rax, [rbp+730h+var_780]
0x10142cb72  mov     [rbp+730h+var_720], rax
0x10142cb76  mov     [rbp+730h+var_780], rbx
0x10142cb7a  test    r10, r10
0x10142cb7d  jnz     short loc_10142CBF4
0x10142cb7f  mov     rdx, gs:58h
0x10142cb88  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10142cb8f  mov     ecx, [rax]
  ... truncated ...
```
