# CreateLoginToken(wchar_t const *,ulong,int,int,int,ulong)

- ea: `0x101428200`
- end: `0x101429545`
- name: `?CreateLoginToken@@YAPEAVILoginToken@@PEB_WKHHHK@Z`
- size: `4933`
- prototype: `struct ILoginToken *__fastcall(const wchar_t *, unsigned int, int, int, int, unsigned int)`
- caller_count: `11`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1004031c0`
- `0x100910d80`
- `0x100962250`
- `0x10138fab0`
- `0x10142a0d0`
- `0x10142af70`
- `0x10142c680`
- `0x101436740`
- `0x10146a920`
- `0x101470860`
- `0x1018ba040`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401433`
- `0x100403080`
- `0x100407d80`
- `0x10040be50`
- `0x10041a970`
- `0x100435510`
- `0x10045c260`
- `0x10054b920`
- `0x10054bd10`
- `0x10054bd60`
- `0x10054ccb0`
- `0x10058ae90`
- `0x100701770`
- `0x10070e860`
- `0x10070eb30`
- `0x10070f030`
- `0x10070f570`
- `0x100713a50`
- `0x100c34c20`
- `0x1011e3ed0`
- `0x10138d430`
- `0x101399090`
- `0x101425e90`
- `0x101427250`
- `0x101428200`
- `0x1014e72b0`
- `0x10154ee80`
- `0x10155e600`

## import_xrefs

- `ole32!CoCreateGuid` at `0x101428cf0`
- `ole32!CoCreateGuid` at `0x101428cf0`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101428868`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101428887`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1014292a9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014282ce`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101428371`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10142850b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014289d6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101428ef0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014282ce`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101428371`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10142850b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014289d6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101428ef0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101428695`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101428cba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014290d3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101429155`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014291a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101428695`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101428cba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014290d3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101429155`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014291a5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10142859e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014288b5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014288f3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10142892d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10142896d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10142859e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014288b5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014288f3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10142892d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10142896d`
- `sqldk!SystemThread_TlsIndex` at `0x101428294`
- `sqldk!SystemThread_TlsIndex` at `0x101428335`
- `sqldk!SystemThread_TlsIndex` at `0x10142846f`
- `sqldk!SystemThread_TlsIndex` at `0x1014284b8`
- `sqldk!SystemThread_TlsIndex` at `0x10142854c`
- `sqldk!SystemThread_TlsIndex` at `0x1014286a4`
- `sqldk!SystemThread_TlsIndex` at `0x101428c47`
- `sqldk!SystemThread_TlsIndex` at `0x101428d17`
- `sqldk!SystemThread_TlsIndex` at `0x101428d77`
- `sqldk!SystemThread_TlsIndex` at `0x101428e39`
- `sqldk!SystemThread_TlsIndex` at `0x101428e83`
- `sqldk!SystemThread_TlsIndex` at `0x10142920a`
- `sqldk!SystemThread_TlsIndex` at `0x1014293d3`
- `sqldk!SystemThread_TlsOffset` at `0x10142829d`
- `sqldk!SystemThread_TlsOffset` at `0x10142833e`
- `sqldk!SystemThread_TlsOffset` at `0x101428478`
- `sqldk!SystemThread_TlsOffset` at `0x1014284c1`
- `sqldk!SystemThread_TlsOffset` at `0x101428555`
- `sqldk!SystemThread_TlsOffset` at `0x1014286ad`
- `sqldk!SystemThread_TlsOffset` at `0x101428c58`
- `sqldk!SystemThread_TlsOffset` at `0x101428d20`
- `sqldk!SystemThread_TlsOffset` at `0x101428d80`
- `sqldk!SystemThread_TlsOffset` at `0x101428e42`
- `sqldk!SystemThread_TlsOffset` at `0x101428e8c`
- `sqldk!SystemThread_TlsOffset` at `0x101429213`
- `sqldk!SystemThread_TlsOffset` at `0x1014293dc`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101429043`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101429043`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014284dc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101428570`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014286c8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101428d50`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142922e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014284dc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101428570`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014286c8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101428d50`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10142922e`
- `sqldk!??_V@YAXPEAX@Z` at `0x101428b7d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101428fa9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014290fd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014292ef`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142930b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142940c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101429418`
- `sqldk!??_V@YAXPEAX@Z` at `0x101429423`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142942e`
- `sqldk!??_V@YAXPEAX@Z` at `0x101429441`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142944c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101428b7d`
- `sqldk!??_V@YAXPEAX@Z` at `0x101428fa9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014290fd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014292ef`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142930b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142940c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101429418`
- `sqldk!??_V@YAXPEAX@Z` at `0x101429423`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142942e`
- `sqldk!??_V@YAXPEAX@Z` at `0x101429441`
- `sqldk!??_V@YAXPEAX@Z` at `0x10142944c`
- `sqldk!?DestroyDescriptor@SOS_UserStore@@QEAAXPEAVSOS_UserDescriptor@@@Z` at `0x101428b53`
- `sqldk!?DestroyDescriptor@SOS_UserStore@@QEAAXPEAVSOS_UserDescriptor@@@Z` at `0x101428b53`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1014291ef`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1014291ef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1014291fb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1014291fb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014290ea`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014290ea`
- `sqlmin!?FIsSynapseWorkspaceServer@@YA_NXZ` at `0x101428276`
- `sqlmin!?FIsSynapseWorkspaceServer@@YA_NXZ` at `0x10142841f`
- `sqlmin!?FIsSynapseWorkspaceServer@@YA_NXZ` at `0x101428276`
- `sqlmin!?FIsSynapseWorkspaceServer@@YA_NXZ` at `0x10142841f`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142885f`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142887e`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142885f`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x10142887e`
- `sqlmin!GetXdbServerGlobals` at `0x101428c17`
- `sqlmin!GetXdbServerGlobals` at `0x101428d94`
- `sqlmin!GetXdbServerGlobals` at `0x101428f53`
- `sqlmin!GetXdbServerGlobals` at `0x101428c17`
- `sqlmin!GetXdbServerGlobals` at `0x101428d94`
- `sqlmin!GetXdbServerGlobals` at `0x101428f53`
- `sqlfabric!GetServerManagedIdentityTypeWinFabProperty` at `0x101428f92`
- `sqlfabric!GetServerManagedIdentityTypeWinFabProperty` at `0x101428f92`

## string_xrefs

- `0x101428edd`: `sql\ntdbms\msql\security\src\seccommon.cpp`
- `0x1014282c4`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x101428365`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x1014284ff`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x10142858c`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x1014288ab`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x1014288e2`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x10142891f`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x101428963`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x1014289c7`: `sql\ntdbms\msql\security\src\seccontext.cpp`
- `0x1014292c7`: `AADServerAdminSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=64
struct ILoginToken *__fastcall CreateLoginToken(
        const wchar_t *a1,
        unsigned int a2,
        int a3,
        int a4,
        int a5,
        unsigned int a6)
{
  rsize_t v7; // rsi
  char *v9; // rbx
  int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rdx
  char *v18; // rax
  void *v19; // r13
  __int64 v20; // rbx
  __int64 v21; // rdx
  struct IMemObj *v22; // rdi
  struct IWindowsSecurityPrimaryInfo *WindowsSecurityPrimaryInfo; // rax
  struct IWindowsSecurityPrimaryInfo *v24; // r12
  __int64 v25; // rax
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rbx
  __int64 v29; // rdi
  struct IMemObj *v30; // rdi
  unsigned int v31; // ebx
  struct IWSPSingleInfo **v32; // rax
  int v33; // eax
  int v34; // eax
  CLoginToken *LoginToken; // rsi
  CLoginToken *v36; // rdi
  struct IMemObj *v37; // rdi
  struct LoginInfo *v38; // rsi
  unsigned __int16 MasterDbId; // ax
  unsigned __int16 v40; // ax
  void *v41; // rax
  struct IMemObj *v42; // rdx
  rsize_t v43; // rdi
  void *v44; // rax
  struct IMemObj *v45; // rdi
  void *v46; // rax
  void *v47; // rax
  int v48; // eax
  int v49; // edi
  int v50; // r14d
  rsize_t v51; // r9
  char *v52; // rcx
  __int64 v53; // rcx
  struct IMEDLogin *v54; // rdi
  __int64 v55; // rcx
  char *ThreadLocalStoragePointer; // rdx
  __int64 v57; // rbx
  struct IMemObj *v58; // rax
  const struct CFedAuthFeatureExtension *FeatureExtension; // r12
  __int64 v60; // rdi
  __int64 v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rbx
  CSession *v64; // r13
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rcx
  _QWORD *v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rbx
  __int64 v71; // rax
  struct IMemObj *v72; // r13
  struct IMemObj *v73; // rdi
  bool v74; // bl
  struct IMemObj *SecPmo; // rax
  __int64 (__fastcall **v76)(struct IMemObj *, struct IMemObj *, const wchar_t **, __int64, GUID *); // rax
  int v77; // ebx
  __int64 v78; // r8
  _WORD *v79; // rdx
  signed __int64 v80; // rax
  __int16 v81; // cx
  _WORD *v82; // rax
  int v83; // edx
  int v84; // ecx
  int v85; // edx
  __int64 v86; // rbx
  __int64 v87; // rax
  __int64 v88; // rdi
  int v89; // ecx
  unsigned int v90; // eax
  __m128i v91; // xmm6
  __int64 v92; // rax
  wchar_t *v93; // rbx
  __int64 v94; // rax
  struct IMetadataAccess *v95; // rcx
  unsigned int v96; // eax
  unsigned int v97; // eax
  signed __int32 v99[8]; // [rsp+0h] [rbp-130h] BYREF
  unsigned int *v100; // [rsp+28h] [rbp-108h]
  __int64 v101; // [rsp+30h] [rbp-100h]
  _DWORD *v102; // [rsp+38h] [rbp-F8h]
  int *v103; // [rsp+40h] [rbp-F0h]
  int *v104; // [rsp+48h] [rbp-E8h]
  int *v105; // [rsp+50h] [rbp-E0h]
  _BYTE *v106; // [rsp+58h] [rbp-D8h]
  struct IMemObj **v107; // [rsp+60h] [rbp-D0h]
  GUID *v108; // [rsp+68h] [rbp-C8h]
  bool v109; // [rsp+B0h] [rbp-80h]
  _BYTE v110[3]; // [rsp+B1h] [rbp-7Fh] BYREF
  int v111; // [rsp+B4h] [rbp-7Ch] BYREF
  char v112[4]; // [rsp+B8h] [rbp-78h] BYREF
  unsigned int v113; // [rsp+BCh] [rbp-74h] BYREF
  int v114; // [rsp+C0h] [rbp-70h] BYREF
  _DWORD SourceSize[3]; // [rsp+C4h] [rbp-6Ch] BYREF
  rsize_t v116; // [rsp+D0h] [rbp-60h] BYREF
  rsize_t DestinationSize; // [rsp+D8h] [rbp-58h] BYREF
  struct IMemObj *v118; // [rsp+E0h] [rbp-50h] BYREF
  struct IMemObj *v119; // [rsp+E8h] [rbp-48h] BYREF
  void *Source; // [rsp+F0h] [rbp-40h] BYREF
  struct LoginInfo *v121; // [rsp+F8h] [rbp-38h] BYREF
  CLoginToken *v122; // [rsp+100h] [rbp-30h]
  char *v123; // [rsp+108h] [rbp-28h]
  void *v124; // [rsp+110h] [rbp-20h] BYREF
  int v125; // [rsp+120h] [rbp-10h] BYREF
  void *v126; // [rsp+128h] [rbp-8h]
  wchar_t *v127; // [rsp+130h] [rbp+0h] BYREF
  struct IMemObj *v128; // [rsp+138h] [rbp+8h]
  struct IMemObj *v129; // [rsp+140h] [rbp+10h]
  struct _GUID v130; // [rsp+148h] [rbp+18h] BYREF
  char *v131; // [rsp+158h] [rbp+28h]
  __int64 v132; // [rsp+160h] [rbp+30h] BYREF
  int v133; // [rsp+168h] [rbp+38h]
  __int64 v134; // [rsp+170h] [rbp+40h] BYREF
  int v135; // [rsp+178h] [rbp+48h]
  __m128i v136; // [rsp+180h] [rbp+50h] BYREF
  const wchar_t *v137; // [rsp+190h] [rbp+60h] BYREF
  int v138; // [rsp+198h] [rbp+68h]
  const wchar_t *v139; // [rsp+1A0h] [rbp+70h] BYREF
  int v140; // [rsp+1A8h] [rbp+78h]
  const wchar_t *v141; // [rsp+1B0h] [rbp+80h] BYREF
  int v142; // [rsp+1B8h] [rbp+88h]
  __int64 v143; // [rsp+1C0h] [rbp+90h]
  void *v144; // [rsp+1C8h] [rbp+98h]
  struct IMemObj *v145; // [rsp+1D0h] [rbp+A0h]
  struct IMemObj *v146; // [rsp+1D8h] [rbp+A8h]
  GUID v147; // [rsp+1E0h] [rbp+B0h] BYREF
  void **v148; // [rsp+1F0h] [rbp+C0h] BYREF
  int v149; // [rsp+1F8h] [rbp+C8h]
  int v150; // [rsp+1FCh] [rbp+CCh]
  int v151; // [rsp+200h] [rbp+D0h]
  char Destination[88]; // [rsp+204h] [rbp+D4h] BYREF
  int v153; // [rsp+25Ch] [rbp+12Ch]
  unsigned int v154; // [rsp+260h] [rbp+130h]
  __int64 v155; // [rsp+268h] [rbp+138h]
  int v156; // [rsp+270h] [rbp+140h]
  int v157; // [rsp+274h] [rbp+144h]
  GUID pguid; // [rsp+278h] [rbp+148h] BYREF
  GUID v159; // [rsp+288h] [rbp+158h] BYREF
  _WORD v160[2048]; // [rsp+2A0h] [rbp+170h] BYREF

  v143 = -2;
  v114 = a4;
  v111 = a3;
  v7 = a2;
  v113 = a2;
  v123 = 0;
  if ( a6 && FIsSynapseWorkspaceServer() )
  {
    LODWORD(v121) = 8427;
    v128 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                        + SystemThread_TlsIndex)
                                                      + SystemThread_TlsOffset)
                                          + 72LL)
                              + 88LL);
    v9 = (char *)operator new(0x38u, v128, "sql\\ntdbms\\msql\\security\\src\\seccontext.cpp", 8427, 3u);
    v119 = (struct IMemObj *)v9;
    if ( v9 )
    {
      *(_QWORD *)v9 = &CSECAuthMedAccess::`vftable';
      *((_WORD *)v9 + 4) = 256;
      *((_DWORD *)v9 + 3) = 0;
      *((_QWORD *)v9 + 2) = 0;
      v131 = v9 + 24;
      *((_QWORD *)v9 + 3) = 0;
      v129 = (struct IMemObj *)(v9 + 32);
      *((_QWORD *)v9 + 4) = 0;
      *(_QWORD *)v9 = &CSECAuthMedServerAccess::`vftable';
      *((_DWORD *)v9 + 10) = a6;
    }
    else
    {
      v9 = 0;
    }
  }
  else
  {
    LODWORD(v121) = 8431;
    v129 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                        + SystemThread_TlsIndex)
                                                      + SystemThread_TlsOffset)
                                          + 72LL)
                              + 88LL);
    v9 = (char *)operator new(0x38u, v129, "sql\\ntdbms\\msql\\security\\src\\seccontext.cpp", 8431, 3u);
    v131 = v9;
    if ( v9 )
    {
      *(_QWORD *)v9 = &CSECAuthMedAccess::`vftable';
      *((_WORD *)v9 + 4) = 256;
      *((_DWORD *)v9 + 3) = 0;
      *((_QWORD *)v9 + 2) = 0;
      v128 = (struct IMemObj *)(v9 + 24);
      *((_QWORD *)v9 + 3) = 0;
      v119 = (struct IMemObj *)(v9 + 32);
      *((_QWORD *)v9 + 4) = 0;
      *(_QWORD *)v9 = &CSECAuthMedServerAccess::`vftable';
      *((_DWORD *)v9 + 10) = 0;
      *((_QWORD *)v9 + 6) = 0;
    }
    else
    {
      v9 = 0;
    }
  }
  v123 = v9;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 216LL))(v9);
  v134 = 0;
  v135 = 0;
  v132 = 0;
  v133 = 0;
  if ( !a1 )
    goto LABEL_15;
  if ( !(_DWORD)v7 )
    goto LABEL_15;
  v10 = 0;
  if ( !(v7 >> 1) )
    goto LABEL_15;
  v11 = 0;
  while ( a1[v11] != 92 )
  {
    ++v10;
    if ( ++v11 >= (__int64)(v7 >> 1) )
      goto LABEL_15;
  }
  if ( !&a1[v10] )
  {
LABEL_15:
    v109 = 0;
    if ( a6 && FIsSynapseWorkspaceServer() )
    {
      v12 = *((_QWORD *)v9 + 2);
      v137 = a1;
      v138 = v7;
      v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD, __int64, unsigned int))(*(_QWORD *)v12 + 328LL))(
              v12,
              &v137,
              0,
              1,
              a6);
      v109 = 1;
    }
    else
    {
      v53 = *((_QWORD *)v9 + 2);
      v139 = a1;
      v140 = v7;
      v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD, __int64, _DWORD))(*(_QWORD *)v53 + 328LL))(
              v53,
              &v139,
              0,
              1,
              0);
    }
    v54 = (struct IMEDLogin *)v13;
    if ( !v13 )
      goto LABEL_175;
    if ( !a4 )
      goto LABEL_170;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13) == 8 )
      goto LABEL_175;
    if ( (*(unsigned int (__fastcall **)(struct IMEDLogin *))(*(_QWORD *)v54 + 24LL))(v54) != 7 )
    {
LABEL_170:
      v95 = (struct IMetadataAccess *)*((_QWORD *)v9 + 2);
      if ( v109 )
        LODWORD(v100) = a6;
      else
        LODWORD(v100) = 0;
      LoginToken = CreateLoginToken(v95, v54, v111, a4, a5, (unsigned int)v100);
      goto LABEL_176;
    }
    if ( (!*(_DWORD *)(GetXdbServerGlobals(v55) + 11976) || !byte_102EDCC23) && !IsBoxAADEnabled(0) )
      goto LABEL_175;
    ThreadLocalStoragePointer = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
    v57 = 8LL * SystemThread_TlsIndex;
    v58 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                     + *(_QWORD *)&ThreadLocalStoragePointer[v57])
                                         + 72LL)
                             + 96LL);
    v128 = v58;
    FeatureExtension = 0;
    if ( v58 )
    {
      LOBYTE(ThreadLocalStoragePointer) = 2;
      FeatureExtension = (const struct CFedAuthFeatureExtension *)CPhysicalConnection::GetFeatureExtension(
                                                                    v58,
                                                                    ThreadLocalStoragePointer);
    }
    if ( !(unsigned int)FIsFedAuthScenarioSupported(
                          *(const struct CCompExecCtxtBasic **)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                          + v57)
                                                              + SystemThread_TlsOffset),
                          FeatureExtension) )
      ex_raise(331, 99, 16, 14);
    v113 = 0;
    *(_QWORD *)&SourceSize[1] = 0;
    v159 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    v110[0] = 0;
    v111 = 0;
    v125 = 0;
    pguid = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
    CoCreateGuid(&pguid);
    v118 = 0;
    v141 = a1;
    v142 = v7;
    v60 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset);
    v61 = SystemThread_TlsOffset + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex);
    v62 = *(_QWORD *)(v61 + 256);
    if ( !v62 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v62 = *(_QWORD *)(v61 + 256);
    }
    v119 = *(struct IMemObj **)(v62 + 1000);
    v63 = 0;
    v109 = 0;
    v64 = *(CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset)
                       + 72LL);
    if ( *(_DWORD *)(GetXdbServerGlobals(SystemThread_TlsIndex) + 11976) || IsBoxAADEnabled(0) )
    {
      if ( v60 )
      {
        v65 = *(_QWORD *)(v60 + 72);
        if ( (*(_BYTE *)(v65 + 270) & 2) != 0 )
          goto LABEL_103;
        if ( (***(unsigned int (__fastcall ****)(_QWORD))(*(_QWORD *)(v65 + 104) + 264LL))(*(_QWORD *)(*(_QWORD *)(v65 + 104) + 264LL)) )
          goto LABEL_103;
        v66 = *(_QWORD *)(v60 + 128);
        if ( v66 )
        {
          if ( (*(_DWORD *)(v66 + 76) & 0x2000) != 0 )
            goto LABEL_103;
        }
      }
    }
    if ( CSession::FIsDwFidoGlmServerCtx(v64)
      || (unsigned int)IsVDWBackendSession()
      && *(_DWORD *)(qword_102ECFB00 + 14504)
      && *((_BYTE *)qword_102EF3550 + 1651) )
    {
      v63 = *((_QWORD *)v64 + 625);
      if ( v63 )
      {
LABEL_103:
        v71 = *((_QWORD *)v64 + 12);
        if ( v71 )
          v109 = *(_BYTE *)(v71 + 50) != 0;
        LODWORD(v121) = 3202;
        v72 = v119;
        v73 = (struct IMemObj *)operator new(8u, v119, "sql\\ntdbms\\msql\\security\\src\\seccommon.cpp", 3202, 3u);
        v129 = v73;
        if ( v73 )
          *(_QWORD *)v73 = &AzureADGraphAPIService::`vftable';
        else
          v73 = 0;
        v146 = v73;
        v147 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
        v76 = *(__int64 (__fastcall ***)(struct IMemObj *, struct IMemObj *, const wchar_t **, __int64, GUID *))v73;
        v108 = &v147;
        v107 = &v118;
        v106 = v110;
        v105 = &v125;
        v104 = &v111;
        v103 = (int *)&v113;
        v102 = &SourceSize[1];
        LOBYTE(v101) = 0;
        LOBYTE(v100) = v109;
        v77 = (*v76)(v73, v72, &v141, v63, &pguid);
        operator delete(v73, 8u);
        if ( v77 )
        {
          v160[0] = 0;
          if ( v118 )
          {
            v78 = 2048;
            v79 = v160;
            v80 = v118 - (struct IMemObj *)v160;
            do
            {
              if ( v78 == -2147481598 )
                break;
              v81 = *(_WORD *)((char *)v79 + v80);
              if ( !v81 )
                break;
              *v79++ = v81;
              --v78;
            }
            while ( v78 );
            v82 = v79 - 1;
            if ( v78 )
              v82 = v79;
            *v82 = 0;
          }
          v100 = (unsigned int *)v160;
          ex_raise(331, 34, 16, 1, a1);
        }
        goto LABEL_110;
      }
    }
    else
    {
      v68 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v69 = *(_QWORD *)(v68[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      LOBYTE(v68) = 2;
      v70 = CPhysicalConnection::GetFeatureExtension(*(_QWORD *)(*(_QWORD *)(v69 + 72) + 96LL), v68);
      if ( v70 )
      {
        if ( IsTridentSqlFrontendSession() )
          v63 = *(_QWORD *)CTMap<wchar_t *,wchar_t *,CFnH_WChar,CFnC_WChar,CFnI_Default<wchar_t *>,CFnD_Ptr<wchar_t>,CFnD_Ptr<wchar_t>,CMemObjAlloc<0>>::ValLookup(
                             *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + SystemThread_TlsIndex)
                                                                           + SystemThread_TlsOffset)
                                                               + 72LL)
                                                   + 248LL)
                                       + 8LL),
                             off_10303C640);
        else
          v63 = *(_QWORD *)(v70 + 56);
        goto LABEL_103;
      }
    }
    v111 = 52;
LABEL_110:
    v74 = 0;
    if ( byte_102EDCC84
      && *(_DWORD *)(qword_102ECFB00 + 14504)
      && !*(_DWORD *)(GetXdbServerGlobals(v67) + 11976)
      && !(unsigned int)IsVDWFrontendInstance()
      && !IsBoxAADEnabled(0) )
    {
      Source = 0;
      SecPmo = SecThreadSafePmo::GetSecPmo();
      if ( (int)GetServerManagedIdentityTypeWinFabProperty(&Source, SecPmo) >= 0 )
      {
        if ( Source )
          v74 = _wcsicmp((const wchar_t *)Source, L"UserAssigned") == 0;
      }
      else
      {
        if ( Source )
          operator delete[](Source);
        Source = 0;
      }
      operator delete[](Source);
    }
    switch ( v111 )
    {
      case 12:
      case 47:
        v85 = 30;
        goto LABEL_136;
      case 13:
        v85 = 31;
        goto LABEL_136;
      case 14:
        v83 = 32;
        v84 = 331;
        goto LABEL_144;
      case 52:
        v85 = 59;
LABEL_136:
        ex_raise(331, v85, 16, 1, a1);
        break;
      case 105:
      case 115:
        if ( IsBoxAADEnabled(0) )
        {
          v83 = 55;
          v84 = 374;
        }
        else if ( v74 )
        {
          v83 = 65;
          v84 = 374;
        }
        else
        {
          v83 = 53;
          v84 = 373;
        }
LABEL_144:
        ex_raise(v84, v83, 16, 1);
        break;
      default:
        break;
    }
    if ( !*(_QWORD *)&SourceSize[1]
      || v113 != 18
      || **(_BYTE **)&SourceSize[1] != 69 && **(_BYTE **)&SourceSize[1] != 88 )
    {
      LoginToken = 0;
      goto LABEL_169;
    }
    if ( *(_QWORD *)&SourceSize[1] == -2 )
    {
      v159 = 0;
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    else
    {
      v159 = *(GUID *)(*(_QWORD *)&SourceSize[1] + 2LL);
    }
    v86 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v87 = *(_QWORD *)(v86 + 256);
    if ( !v87 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v87 = *(_QWORD *)(v86 + 256);
    }
    v88 = *(_QWORD *)(v87 + 1000);
    DestinationSize = 0;
    LODWORD(v124) = 0;
    v112[0] = 0;
    LODWORD(v121) = 0;
    LODWORD(v119) = 0;
    LOWORD(v114) = 0;
    v89 = dword_102EF4298;
    do
    {
      v90 = v89 & 0xFFFFFFFE;
      v91 = (__m128i)xmmword_102EF4288;
      _InterlockedOr(v99, 0);
      v89 = dword_102EF4298;
    }
    while ( v90 != dword_102EF4298 );
    if ( *(_QWORD *)&Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data1 == v91.m128i_i64[0]
      && *(_QWORD *)Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val.Data4 == _mm_srli_si128(v91, 8).m128i_u64[0] )
    {
      v126 = 0;
      v92 = *(_QWORD *)s_pServerConf;
      v100 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, __int64, wchar_t **))(v92 + 528))(
             s_pServerConf,
             L"FederatedAuthentication",
             L"AADServerAdminSid",
             v88,
             &v127) )
      {
        v93 = v127;
        if ( v127 )
          operator delete[](0);
      }
      else
      {
        v93 = 0;
      }
      v126 = v93;
      v91 = *(__m128i *)AzureActiveDirectoryService::StringToGuid(&v130, v93);
      operator delete[](v93);
    }
    v94 = 0;
    if ( FeatureExtension )
      v94 = *((_QWORD *)FeatureExtension + 7);
    v136 = v91;
    if ( !(unsigned int)FedAuthTicketService::GetFederatedContextInternalWithRetry(
                          v88,
                          (_DWORD)a1,
                          v7,
                          (unsigned int)&v159,
                          v94,
                          (_DWORD)v100,
                          (__int64)&pguid,
                          (__int64)v128,
                          0,
                          (__int64)&v136,
                          0,
                          (__int64)&DestinationSize,
                          (__int64)&v124,
                          (__int64)v112,
                          (__int64)v110,
                          (__int64)&v121,
                          (__int64)&v119,
                          (__int64)&v114,
                          (__int64)&v111,
                          0,
                          0) )
    {
      LoginToken = (CLoginToken *)CreateLoginTokenFromFederatedContext(
                                    DestinationSize,
                                    4,
                                    *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                  + SystemThread_TlsIndex)
                                                                                + SystemThread_TlsOffset)
                                                                    + 80LL)
                                                        + 8LL));
      operator delete[]((void *)DestinationSize);
LABEL_169:
      operator delete[](v118);
      operator delete[](*(void **)&SourceSize[1]);
      v9 = v123;
      goto LABEL_176;
    }
    operator delete[]((void *)DestinationSize);
    operator delete[](v118);
    operator delete[](*(void **)&SourceSize[1]);
    v9 = v123;
LABEL_175:
    LoginToken = 0;
    goto LABEL_176;
  }
  v15 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                        + SystemThread_TlsIndex)
                                                      + SystemThread_TlsOffset)
                                          + 72LL)
                              + 104LL)
                  + 264LL);
  v118 = (struct IMemObj *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 328LL))(v15);
  v122 = 0;
  LODWORD(v124) = 8449;
  v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v17 = *(_QWORD *)(v16 + 256);
  if ( !v17 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v17 = *(_QWORD *)(v16 + 256);
  }
  v129 = *(struct IMemObj **)(v17 + 1000);
  v18 = (char *)operator new(0xE8u, v129, "sql\\ntdbms\\msql\\security\\src\\seccontext.cpp", 8449, 3u);
  v19 = v18;
  v131 = v18;
  if ( v18 )
  {
    memset_0(v18, 0, 0xE8u);
    *((_DWORD *)v19 + 57) = 0;
  }
  else
  {
    v19 = 0;
  }
  v144 = v19;
  SourceSize[0] = 0;
  v20 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v21 = *(_QWORD *)(v20 + 256);
  if ( !v21 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v21 = *(_QWORD *)(v20 + 256);
  }
  DestinationSize = v7;
  v22 = (struct IMemObj *)operator new[](
                            v7 + 2,
                            *(struct IMemObj **)(v21 + 1000),
                            "sql\\ntdbms\\msql\\security\\src\\seccontext.cpp",
                            8453,
                            3u);
  v119 = v22;
  v145 = v22;
  memcpy_s(v22, v7 + 2, a1, v7);
  *((_WORD *)v22 + (v7 >> 1)) = 0;
  WindowsSecurityPrimaryInfo = GetWindowsSecurityPrimaryInfo((const wchar_t *)v22);
  v24 = WindowsSecurityPrimaryInfo;
  v126 = WindowsSecurityPrimaryInfo;
  if ( !WindowsSecurityPrimaryInfo
    || (v25 = (**(__int64 (__fastcall ***)(struct IWindowsSecurityPrimaryInfo *))WindowsSecurityPrimaryInfo)(WindowsSecurityPrimaryInfo),
        (v26 = v25) == 0)
    || (v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 24LL))(v25), ((v27 - 1) & 0xFFFFFFF3) != 0)
    || v27 == 13 )
  {
    v9 = v123;
    v36 = v122;
LABEL_68:
    LoginToken = 0;
    goto LABEL_69;
  }
  v116 = 0;
  v124 = (void *)(**(__int64 (__fastcall ***)(__int64, char *))v26)(v26, (char *)&v116 + 4);
  Source = (void *)(*(__int64 (__fastcall **)(__int64, rsize_t *))(*(_QWORD *)v26 + 8LL))(v26, &v116);
  *(_QWORD *)&SourceSize[1] = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v26 + 16LL))(v26, SourceSize);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v26 + 24LL))(v26) != 1
    && !(unsigned int)FIsLocalWellknownSID(*(PSID *)&SourceSize[1]) )
  {
    LODWORD(v100) = -65535;
    ex_raise(154, 4, 16, 50, v22, v100);
  }
  v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v29 = *(_QWORD *)(v28 + 256);
  if ( !v29 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v29 = *(_QWORD *)(v28 + 256);
  }
  v30 = *(struct IMemObj **)(v29 + 1000);
  v31 = (*(__int64 (__fastcall **)(struct IWindowsSecurityPrimaryInfo *))(*(_QWORD *)v24 + 8LL))(v24);
  v32 = (struct IWSPSingleInfo **)(*(__int64 (__fastcall **)(struct IWindowsSecurityPrimaryInfo *))(*(_QWORD *)v24 + 24LL))(v24);
  PopulateUserGroupInfo(v30, 0, v32, v31, (struct NTGroupInfo **)v19 + 20, (unsigned int *)v19 + 39);
  v9 = v123;
  v33 = a5;
  if ( a5 )
  {
    v36 = 0;
    v122 = 0;
LABEL_42:
    *(_QWORD *)&v130.Data1 = &CAutoUserDescriptor::`vftable';
    *(_QWORD *)v130.Data4 = 0;
    if ( !v33 )
      *(_QWORD *)v130.Data4 = (*(__int64 (__fastcall **)(void *))(g_LoginTokenCache + 64LL))(&g_LoginTokenCache);
    v136.m128i_i64[0] = (__int64)a1;
    v136.m128i_i32[2] = v7;
    (*(void (__fastcall **)(char *, __m128i *))(*(_QWORD *)v9 + 8LL))(v9, &v136);
    if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v9 + 56LL))(v9)
      && (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v9 + 48LL))(v9)
      && !v114 )
    {
      LoginToken = 0;
    }
    else
    {
      v37 = v118;
      v38 = DuplicateLoginInfo(v118, (struct LoginInfo *)v19, 0xFu);
      v121 = v38;
      v127 = (wchar_t *)v38;
      *((_QWORD *)v38 + 1) = 0;
      *((_DWORD *)v38 + 6) = 1;
      MasterDbId = GetMasterDbId();
      *((_DWORD *)v38 + 49) = *(_DWORD *)(g_dbtableFactory[4](MasterDbId) + 544);
      v40 = GetMasterDbId();
      *((_DWORD *)v38 + 50) = *(_DWORD *)(g_dbtableFactory[4](v40) + 576);
      v41 = operator new[](SourceSize[0], v37, "sql\\ntdbms\\msql\\security\\src\\seccontext.cpp", 8555, 3u);
      *((_QWORD *)v38 + 4) = v41;
      *((_DWORD *)v38 + 10) = SourceSize[0];
      memcpy_s(v41, SourceSize[0], *(const void *const *)&SourceSize[1], SourceSize[0]);
      v42 = v37;
      v43 = DestinationSize;
      v44 = operator new[](DestinationSize, v42, "sql\\ntdbms\\msql\\security\\src\\seccontext.cpp", 8559, 3u);
      *((_QWORD *)v38 + 6) = v44;
      *((_DWORD *)v38 + 14) = v43;
      memcpy_s(v44, v43, a1, v43);
      v45 = v118;
      v46 = operator new[]((unsigned int)v116, v118, "sql\\ntdbms\\msql\\security\\src\\seccontext.cpp", 8563, 3u);
      *((_QWORD *)v38 + 16) = v46;
      memcpy_s(v46, (unsigned int)v116, Source, (unsigned int)v116);
      *((_DWORD *)v38 + 34) = v116;
      v47 = operator new[](HIDWORD(v116), v45, "sql\\ntdbms\\msql\\security\\src\\seccontext.cpp", 8567, 3u);
      *((_QWORD *)v38 + 18) = v47;
      memcpy_s(v47, HIDWORD(v116), v124, HIDWORD(v116));
      *((_DWORD *)v38 + 38) = HIDWORD(v116);
      CSECAuthenticate::FillLoginInfo((_DWORD)v45, (_DWORD)v9, (_DWORD)v38, (unsigned int)&v134, (__int64)&v132, 1);
      LODWORD(v124) = 8580;
      DestinationSize = (rsize_t)operator new(0x150u, v45, "sql\\ntdbms\\msql\\security\\src\\seccontext.cpp", 8580, 3u);
      if ( DestinationSize )
      {
        if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v9 + 56LL))(v9) )
          v48 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 112LL))(v9);
        else
          v48 = 0;
        v49 = *((unsigned __int16 *)v38 + 104);
        *(_QWORD *)&SourceSize[1] = *((_QWORD *)v38 + 20);
        v113 = *((_DWORD *)v38 + 39);
        v50 = *((_DWORD *)v38 + 6);
        v148 = &CLoginTokenKey::`vftable';
        v149 = v50;
        v150 = v48;
        v151 = 0;
        v156 = 15;
        v51 = 85;
        if ( *((_DWORD *)v38 + 10) < 0x55u )
          v51 = *((unsigned int *)v38 + 10);
        v153 = v51;
        memcpy_s(Destination, 0x55u, *((const void *const *)v38 + 4), v51);
        v157 = v49;
        if ( (unsigned int)(v50 - 1) <= 1 || (unsigned int)(v50 - 7) <= 1 )
        {
          v154 = v113;
          v155 = *(_QWORD *)&SourceSize[1];
        }
        LoginToken = (CLoginToken *)CLoginToken::CLoginToken(DestinationSize, &v148, 1);
      }
      else
      {
        LoginToken = 0;
      }
      v36 = LoginToken;
      v122 = LoginToken;
      v127 = 0;
      CLoginToken::InitToken(LoginToken, v118, v121, 0xFu, 0);
      if ( !a5 )
        CSecurityContext::CacheLoginToken(LoginToken, (struct SOS_UserDescriptor **)v130.Data4);
      if ( !v111 || (unsigned int)FCheckSrvAccess(*((struct IMetadataAccess **)v9 + 2), v114) )
      {
        v36 = 0;
        v122 = 0;
      }
      else
      {
        LoginToken = 0;
      }
    }
    *(_QWORD *)&v130.Data1 = &CAutoUserDescriptor::`vftable';
    if ( *(_QWORD *)v130.Data4 )
    {
      SOS_UserStore::DestroyDescriptor(
        *(SOS_UserStore **)(*(_QWORD *)v130.Data4 + 128LL),
        *(struct SOS_UserDescriptor **)v130.Data4);
      *(_QWORD *)v130.Data4 = 0;
    }
    goto LABEL_69;
  }
  v34 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v123 + 160LL))(v123);
  LoginToken = (CLoginToken *)CSecurityContext::LookupLoginToken(
                                1,
                                *(_QWORD *)&SourceSize[1],
                                SourceSize[0],
                                0,
                                0,
                                *((_DWORD *)v19 + 39),
                                *((_QWORD *)v19 + 20),
                                v34,
                                15);
  v36 = LoginToken;
  v122 = LoginToken;
  if ( !LoginToken )
  {
    LODWORD(v7) = v113;
    v33 = 0;
    goto LABEL_42;
  }
  if ( v111 && !(unsigned int)FCheckSrvAccess(0, v114) )
    goto LABEL_68;
  v36 = 0;
  v122 = 0;
LABEL_69:
  if ( v24 )
    (*(void (__fastcall **)(struct IWindowsSecurityPrimaryInfo *))(*(_QWORD *)v24 + 32LL))(v24);
  operator delete[](v119);
  if ( v19 )
    LoginInfo::`scalar deleting destructor'((LoginInfo *)v19, 1u);
  if ( v36 )
  {
    v52 = (char *)v36 + *(int *)(*((_QWORD *)v36 + 2) + 4LL) + 16;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v52 + 8LL))(v52);
  }
LABEL_176:
  if ( v133 )
  {
    LOBYTE(v14) = 0;
    v96 = v133 - 1;
    if ( v133 != 1 )
    {
      do
      {
        LOBYTE(v14) = v14 + 3;
        v96 >>= 3;
      }
      while ( v96 );
    }
    v133 = 0;
    DeleteSubtree(&v132, v14, 0);
  }
  if ( v135 )
  {
    LOBYTE(v14) = 0;
    v97 = v135 - 1;
    if ( v135 != 1 )
    {
      do
      {
        LOBYTE(v14) = v14 + 3;
        v97 >>= 3;
      }
      while ( v97 );
    }
    v135 = 0;
    DeleteSubtree(&v134, v14, 0);
  }
  (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v9 + 224LL))(v9, 1);
  return LoginToken;
}

```

## disassembly

```asm
0x101428200  push    rbp
0x101428202  push    rsi
0x101428203  push    rdi
0x101428204  push    r12
0x101428206  push    r13
0x101428208  push    r14
0x10142820a  push    r15
0x10142820c  lea     rbp, [rsp-1190h]
0x101428214  mov     eax, 12C0h
0x101428219  call    _alloca_probe
0x10142821e  sub     rsp, rax
0x101428221  mov     [rbp+11C0h+var_1130], 0FFFFFFFFFFFFFFFEh
0x10142822c  mov     [rsp+12F0h+arg_10], rbx
0x101428234  movaps  [rsp+12F0h+var_40], xmm6
0x10142823c  mov     rax, cs:__security_cookie
0x101428243  xor     rax, rsp
0x101428246  mov     [rbp+11C0h+var_50], rax
0x10142824d  mov     r13d, r9d
0x101428250  mov     [rbp+11C0h+var_1230], r9d
0x101428254  mov     [rbp+11C0h+var_123C], r8d
0x101428258  mov     esi, edx
0x10142825a  mov     [rbp+11C0h+var_1234], esi
0x10142825d  mov     r14, rcx
0x101428260  mov     r12d, [rbp+11C0h+arg_28]
0x101428267  xor     edi, edi
0x101428269  mov     [rbp+11C0h+var_11E8], rdi
0x10142826d  test    r12d, r12d
0x101428270  jz      loc_101428325
0x101428276  call    cs:__imp_?FIsSynapseWorkspaceServer@@YA_NXZ; FIsSynapseWorkspaceServer(void)
0x10142827c  test    al, al
0x10142827e  jz      loc_101428325
0x101428284  mov     dword ptr [rbp+11C0h+var_11F8], 20EBh
0x10142828b  mov     rdx, gs:58h
0x101428294  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10142829b  mov     ecx, [rax]
0x10142829d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1014282a4  mov     eax, [rax]
0x1014282a6  add     rax, [rdx+rcx*8]
0x1014282aa  mov     rax, [rax]
0x1014282ad  mov     rcx, [rax+48h]
0x1014282b1  mov     rdx, [rcx+58h]
0x1014282b5  mov     [rbp+11C0h+var_11B8], rdx
0x1014282b9  mov     byte ptr [rsp+12F0h+var_12D0], 3
0x1014282be  mov     r9d, 20EBh
0x1014282c4  lea     r8, aSqlNtdbmsMsqlS_35; "sql\\ntdbms\\msql\\security\\src\\secco"...
0x1014282cb  lea     ecx, [rdi+38h]
0x1014282ce  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x1014282d4  mov     rbx, rax
0x1014282d7  mov     [rbp+11C0h+var_1208], rax
0x1014282db  test    rax, rax
0x1014282de  jz      short loc_10142831D
0x1014282e0  lea     rax, ??_7CSECAuthMedAccess@@6B@; const CSECAuthMedAccess::`vftable'
0x1014282e7  mov     [rbx], rax
0x1014282ea  mov     word ptr [rbx+8], 100h
0x1014282f0  mov     [rbx+0Ch], edi
0x1014282f3  mov     [rbx+10h], rdi
0x1014282f7  lea     rax, [rbx+18h]
0x1014282fb  mov     [rbp+11C0h+var_1198], rax
0x1014282ff  mov     [rax], rdi
0x101428302  lea     rax, [rbx+20h]
0x101428306  mov     [rbp+11C0h+var_11B0], rax
0x10142830a  mov     [rax], rdi
0x10142830d  lea     rax, ??_7CSECAuthMedServerAccess@@6B@; const CSECAuthMedServerAccess::`vftable'
0x101428314  mov     [rbx], rax
0x101428317  mov     [rbx+28h], r12d
0x10142831b  jmp     short loc_101428320
0x10142831d  mov     rbx, rdi
0x101428320  jmp     loc_1014283C6
0x101428325  mov     dword ptr [rbp+11C0h+var_11F8], 20EFh
0x10142832c  mov     rdx, gs:58h
0x101428335  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10142833c  mov     ecx, [rax]
0x10142833e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101428345  mov     eax, [rax]
0x101428347  add     rax, [rdx+rcx*8]
0x10142834b  mov     rax, [rax]
0x10142834e  mov     rcx, [rax+48h]
0x101428352  mov     rdx, [rcx+58h]
0x101428356  mov     [rbp+11C0h+var_11B0], rdx
0x10142835a  mov     byte ptr [rsp+12F0h+var_12D0], 3
0x10142835f  mov     r9d, 20EFh
0x101428365  lea     r8, aSqlNtdbmsMsqlS_35; "sql\\ntdbms\\msql\\security\\src\\secco"...
0x10142836c  mov     ecx, 38h ; '8'
0x101428371  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x101428377  mov     rbx, rax
0x10142837a  mov     [rbp+11C0h+var_1198], rax
0x10142837e  test    rax, rax
0x101428381  jz      short loc_1014283C3
0x101428383  lea     rax, ??_7CSECAuthMedAccess@@6B@; const CSECAuthMedAccess::`vftable'
0x10142838a  mov     [rbx], rax
0x10142838d  mov     word ptr [rbx+8], 100h
0x101428393  mov     [rbx+0Ch], edi
0x101428396  mov     [rbx+10h], rdi
0x10142839a  lea     rax, [rbx+18h]
0x10142839e  mov     [rbp+11C0h+var_11B8], rax
0x1014283a2  mov     [rax], rdi
0x1014283a5  lea     rax, [rbx+20h]
0x1014283a9  mov     [rbp+11C0h+var_1208], rax
0x1014283ad  mov     [rax], rdi
0x1014283b0  lea     rax, ??_7CSECAuthMedServerAccess@@6B@; const CSECAuthMedServerAccess::`vftable'
0x1014283b7  mov     [rbx], rax
0x1014283ba  mov     [rbx+28h], edi
0x1014283bd  mov     [rbx+30h], rdi
0x1014283c1  jmp     short loc_1014283C6
0x1014283c3  mov     rbx, rdi
0x1014283c6  mov     [rbp+11C0h+var_11E8], rbx
0x1014283ca  mov     rax, [rbx]
0x1014283cd  mov     rcx, rbx
0x1014283d0  call    qword ptr [rax+0D8h]
0x1014283d6  mov     [rbp+11C0h+var_1180], rdi
0x1014283da  mov     [rbp+11C0h+var_1178], edi
0x1014283dd  mov     [rbp+11C0h+var_1190], rdi
0x1014283e1  mov     [rbp+11C0h+var_1188], edi
0x1014283e4  mov     r15d, 1
0x1014283ea  test    r14, r14
0x1014283ed  jz      short loc_101428412
0x1014283ef  test    esi, esi
0x1014283f1  jz      short loc_101428412
0x1014283f3  mov     ecx, edi
0x1014283f5  mov     rdx, rsi
0x1014283f8  shr     rdx, 1
0x1014283fb  jz      short loc_101428412
0x1014283fd  mov     rax, rdi
0x101428400  cmp     word ptr [r14+rax*2], 5Ch ; '\'
0x101428406  jz      short loc_10142845A
0x101428408  inc     ecx
0x10142840a  inc     rax
0x10142840d  cmp     rax, rdx
0x101428410  jl      short loc_101428400
0x101428412  mov     [rbp+11C0h+var_1240], 0
0x101428416  test    r12d, r12d
0x101428419  jz      loc_101428BBB
0x10142841f  call    cs:__imp_?FIsSynapseWorkspaceServer@@YA_NXZ; FIsSynapseWorkspaceServer(void)
0x101428425  test    al, al
0x101428427  jz      loc_101428BBB
0x10142842d  mov     rcx, [rbx+10h]
0x101428431  mov     [rbp+11C0h+var_1160], r14
0x101428435  mov     [rbp+11C0h+var_1158], esi
0x101428438  mov     rax, [rcx]
0x10142843b  mov     dword ptr [rsp+12F0h+var_12D0], r12d
0x101428440  movzx   r9d, r15b
0x101428444  xor     r8d, r8d
0x101428447  lea     rdx, [rbp+11C0h+var_1160]
0x10142844b  call    qword ptr [rax+148h]
0x101428451  mov     [rbp+11C0h+var_1240], r15b
0x101428455  jmp     loc_101428BDE
0x10142845a  movsxd  rax, ecx
0x10142845d  lea     rcx, [r14+rax*2]
0x101428461  test    rcx, rcx
0x101428464  jz      short loc_101428412
0x101428466  mov     rdx, gs:58h
0x10142846f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101428476  mov     ecx, [rax]
0x101428478  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10142847f  mov     eax, [rax]
0x101428481  add     rax, [rdx+rcx*8]
0x101428485  mov     rax, [rax]
0x101428488  mov     rcx, [rax+48h]
0x10142848c  mov     rax, [rcx+68h]
0x101428490  mov     rcx, [rax+108h]
0x101428497  mov     rax, [rcx]
0x10142849a  call    qword ptr [rax+148h]
0x1014284a0  mov     [rbp+11C0h+var_1210], rax
0x1014284a4  mov     [rbp+11C0h+var_11F0], rdi
0x1014284a8  mov     dword ptr [rbp+11C0h+var_11E0], 2101h
0x1014284af  mov     r8, gs:58h
0x1014284b8  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x1014284bf  mov     edx, [rcx]
0x1014284c1  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x1014284c8  mov     ebx, [rcx]
0x1014284ca  add     rbx, [r8+rdx*8]
0x1014284ce  mov     rdx, [rbx+100h]
0x1014284d5  test    rdx, rdx
0x1014284d8  jnz     short loc_1014284E9
0x1014284da  xor     ecx, ecx
0x1014284dc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1014284e2  mov     rdx, [rbx+100h]
0x1014284e9  mov     rdx, [rdx+3E8h]
0x1014284f0  mov     [rbp+11C0h+var_11B0], rdx
0x1014284f4  mov     byte ptr [rsp+12F0h+var_12D0], 3
0x1014284f9  mov     r9d, 2101h
0x1014284ff  lea     r8, aSqlNtdbmsMsqlS_35; "sql\\ntdbms\\msql\\security\\src\\secco"...
0x101428506  mov     ecx, 0E8h
0x10142850b  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x101428511  mov     r13, rax
0x101428514  mov     [rbp+11C0h+var_1198], rax
0x101428518  test    rax, rax
0x10142851b  jz      short loc_101428536
0x10142851d  xor     edx, edx; Val
0x10142851f  mov     r8d, 0E8h; Size
0x101428525  mov     rcx, rax; void *
0x101428528  call    memset_0
0x10142852d  mov     [r13+0E4h], edi
0x101428534  jmp     short loc_101428539
0x101428536  mov     r13, rdi
0x101428539  mov     [rbp+11C0h+var_1128], r13
0x101428540  mov     dword ptr [rbp+11C0h+SourceSize], edi
0x101428543  mov     rdx, gs:58h
0x10142854c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101428553  mov     ecx, [rax]
0x101428555  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10142855c  mov     ebx, [rax]
0x10142855e  add     rbx, [rdx+rcx*8]
0x101428562  mov     rdx, [rbx+100h]
0x101428569  test    rdx, rdx
0x10142856c  jnz     short loc_10142857D
0x10142856e  xor     ecx, ecx
0x101428570  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101428576  mov     rdx, [rbx+100h]
0x10142857d  mov     [rbp+11C0h+DestinationSize], rsi
0x101428581  mov     byte ptr [rsp+12F0h+var_12D0], 3
0x101428586  mov     r9d, 2105h
0x10142858c  lea     r8, aSqlNtdbmsMsqlS_35; "sql\\ntdbms\\msql\\security\\src\\secco"...
0x101428593  mov     rdx, [rdx+3E8h]
0x10142859a  lea     rcx, [rsi+2]
0x10142859e  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1014285a4  mov     rdi, rax
0x1014285a7  mov     [rbp+11C0h+var_1208], rax
0x1014285ab  mov     [rbp+11C0h+var_1120], rax
0x1014285b2  mov     r9, rsi; SourceSize
0x1014285b5  mov     r8, r14; Source
0x1014285b8  lea     rdx, [rsi+2]; DestinationSize
0x1014285bc  mov     rcx, rax; Destination
0x1014285bf  call    memcpy_s
0x1014285c4  mov     rcx, rsi
0x1014285c7  shr     rcx, 1
0x1014285ca  xor     eax, eax
0x1014285cc  mov     [rdi+rcx*2], ax
0x1014285d0  mov     [rbp+11C0h+var_11C8], rax
0x1014285d4  mov     rcx, rdi; wchar_t *
0x1014285d7  call    ?GetWindowsSecurityPrimaryInfo@@YAPEAUIWindowsSecurityPrimaryInfo@@PEB_W@Z; GetWindowsSecurityPrimaryInfo(wchar_t const *)
0x1014285dc  mov     r12, rax
0x1014285df  mov     [rbp+11C0h+var_11C8], rax
0x1014285e3  test    rax, rax
0x1014285e6  jz      loc_101428B5F
0x1014285ec  mov     rdx, [rax]
0x1014285ef  mov     rcx, rax
0x1014285f2  call    qword ptr [rdx]
0x1014285f4  mov     rbx, rax
0x1014285f7  test    rax, rax
0x1014285fa  jz      loc_101428B5F
0x101428600  mov     rdx, [rax]
0x101428603  mov     rcx, rax
0x101428606  call    qword ptr [rdx+18h]
0x101428609  lea     ecx, [rax-1]
0x10142860c  test    ecx, 0FFFFFFF3h
0x101428612  jnz     loc_101428B5F
0x101428618  cmp     eax, 0Dh
0x10142861b  jz      loc_101428B5F
0x101428621  xor     eax, eax
0x101428623  mov     dword ptr [rbp+11C0h+var_1220+4], eax
0x101428626  mov     dword ptr [rbp+11C0h+var_1220], eax
0x101428629  mov     rax, [rbx]
0x10142862c  lea     rdx, [rbp+11C0h+var_1220+4]
0x101428630  mov     rcx, rbx
0x101428633  call    qword ptr [rax]
0x101428635  mov     [rbp+11C0h+var_11E0], rax
0x101428639  mov     r8, [rbx]
0x10142863c  lea     rdx, [rbp+11C0h+var_1220]
0x101428640  mov     rcx, rbx
0x101428643  call    qword ptr [r8+8]
0x101428647  mov     [rbp+11C0h+Source], rax
0x10142864b  mov     r8, [rbx]
0x10142864e  lea     rdx, [rbp+11C0h+SourceSize]
0x101428652  mov     rcx, rbx
0x101428655  call    qword ptr [r8+10h]
0x101428659  mov     qword ptr [rbp+11C0h+SourceSize+4], rax
0x10142865d  mov     rdx, [rbx]
0x101428660  mov     rcx, rbx
0x101428663  call    qword ptr [rdx+18h]
0x101428666  cmp     eax, 1
0x101428669  jz      short loc_10142869B
0x10142866b  mov     rcx, qword ptr [rbp+11C0h+SourceSize+4]; pSid
0x10142866f  call    ?FIsLocalWellknownSID@@YAHPEAX@Z; FIsLocalWellknownSID(void *)
0x101428674  test    eax, eax
0x101428676  jnz     short loc_10142869B
0x101428678  mov     dword ptr [rsp+12F0h+var_12C8], 0FFFF0001h
0x101428680  mov     [rsp+12F0h+var_12D0], rdi
0x101428685  lea     edx, [rax+4]
0x101428688  mov     ecx, 9Ah
0x10142868d  lea     r9d, [rax+32h]
0x101428691  lea     r8d, [rax+10h]
0x101428695  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10142869b  mov     rdx, gs:58h
0x1014286a4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1014286ab  mov     ecx, [rax]
0x1014286ad  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1014286b4  mov     ebx, [rax]
0x1014286b6  add     rbx, [rdx+rcx*8]
0x1014286ba  mov     rdi, [rbx+100h]
0x1014286c1  test    rdi, rdi
0x1014286c4  jnz     short loc_1014286D5
0x1014286c6  xor     ecx, ecx
0x1014286c8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1014286ce  mov     rdi, [rbx+100h]
0x1014286d5  mov     rdi, [rdi+3E8h]
0x1014286dc  mov     rax, [r12]
0x1014286e0  mov     rcx, r12
0x1014286e3  call    qword ptr [rax+8]
0x1014286e6  mov     ebx, eax
  ... truncated ...
```
