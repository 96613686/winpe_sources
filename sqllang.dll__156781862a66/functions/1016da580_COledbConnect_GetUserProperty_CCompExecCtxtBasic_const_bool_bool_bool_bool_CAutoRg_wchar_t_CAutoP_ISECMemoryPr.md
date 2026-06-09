# COledbConnect::GetUserProperty(CCompExecCtxtBasic const &,bool &,bool &,bool &,bool &,CAutoRg<wchar_t> &,CAutoP<ISECMemoryProtector> &,CAutoRg<wchar_t> &,CAutoRg<uchar> &,ulong &,CAutoRg<wchar_t> &,ExternalAuthMode &)

- ea: `0x1016da580`
- end: `0x1016db86f`
- name: `?GetUserProperty@COledbConnect@@AEBAXAEBVCCompExecCtxtBasic@@AEA_N111AEAV?$CAutoRg@_W@@AEAV?$CAutoP@VISECMemoryProtector@@@@2AEAV?$CAutoRg@E@@AEAK2AEAW4ExternalAuthMode@@@Z`
- size: `4847`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1016d7ed0`
- `0x1016dc000`

## callees

- `0x100401070`
- `0x100401400`
- `0x100401433`
- `0x100403080`
- `0x1004132a0`
- `0x10041a970`
- `0x100536250`
- `0x1007548f0`
- `0x100860500`
- `0x101406e30`
- `0x1014d06b0`
- `0x101670420`
- `0x1016da580`
- `0x1016dbc30`
- `0x1016dbd00`
- `0x1016e9ff0`

## import_xrefs

- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x1016db6df`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x1016db6e6`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x1016db6e6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016da8eb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016da9ba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dab47`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dadc3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dadd5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dae83`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016daeb3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dafa8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016db095`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016da8eb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016da9ba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dab47`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dadc3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dadd5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dae83`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016daeb3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016dafa8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016db095`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016da75d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016da814`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016daf42`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db107`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db1d7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db2fb`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db3d1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db5b9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016da75d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016da814`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016daf42`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db107`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db1d7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db2fb`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db3d1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1016db5b9`
- `sqldk!SystemThread_TlsIndex` at `0x1016da6f3`
- `sqldk!SystemThread_TlsIndex` at `0x1016da7c8`
- `sqldk!SystemThread_TlsIndex` at `0x1016da94b`
- `sqldk!SystemThread_TlsIndex` at `0x1016da9d0`
- `sqldk!SystemThread_TlsIndex` at `0x1016daa6b`
- `sqldk!SystemThread_TlsIndex` at `0x1016daed8`
- `sqldk!SystemThread_TlsIndex` at `0x1016dafc7`
- `sqldk!SystemThread_TlsIndex` at `0x1016db0a4`
- `sqldk!SystemThread_TlsIndex` at `0x1016db16a`
- `sqldk!SystemThread_TlsIndex` at `0x1016db2a7`
- `sqldk!SystemThread_TlsIndex` at `0x1016db384`
- `sqldk!SystemThread_TlsIndex` at `0x1016db415`
- `sqldk!SystemThread_TlsIndex` at `0x1016db558`
- `sqldk!SystemThread_TlsIndex` at `0x1016db612`
- `sqldk!SystemThread_TlsIndex` at `0x1016db754`
- `sqldk!SystemThread_TlsIndex` at `0x1016db7cc`
- `sqldk!SystemThread_TlsOffset` at `0x1016da6fc`
- `sqldk!SystemThread_TlsOffset` at `0x1016da7d1`
- `sqldk!SystemThread_TlsOffset` at `0x1016da954`
- `sqldk!SystemThread_TlsOffset` at `0x1016da9d9`
- `sqldk!SystemThread_TlsOffset` at `0x1016daa74`
- `sqldk!SystemThread_TlsOffset` at `0x1016daee1`
- `sqldk!SystemThread_TlsOffset` at `0x1016dafd0`
- `sqldk!SystemThread_TlsOffset` at `0x1016db0ad`
- `sqldk!SystemThread_TlsOffset` at `0x1016db173`
- `sqldk!SystemThread_TlsOffset` at `0x1016db2b0`
- `sqldk!SystemThread_TlsOffset` at `0x1016db38d`
- `sqldk!SystemThread_TlsOffset` at `0x1016db41e`
- `sqldk!SystemThread_TlsOffset` at `0x1016db561`
- `sqldk!SystemThread_TlsOffset` at `0x1016db61b`
- `sqldk!SystemThread_TlsOffset` at `0x1016db75d`
- `sqldk!SystemThread_TlsOffset` at `0x1016db7d5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da717`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da7ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da9f4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016daa8f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016daefc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016dafeb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db0c8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db18e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db2cb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db3a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db437`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db57a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db636`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db776`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db7ee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da717`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da7ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da9f4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016daa8f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016daefc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016dafeb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db0c8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db18e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db2cb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db3a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db437`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db57a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db636`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db776`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db7ee`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016da772`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016da826`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016dad49`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016dae14`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016daf58`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db11d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db1ed`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db30b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db3e1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db4b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db5ca`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db71a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db7a5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016da772`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016da826`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016dad49`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016dae14`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016daf58`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db11d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db1ed`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db30b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db3e1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db4b3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db5ca`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db71a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016db7a5`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1016dac51`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1016dacad`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1016dac51`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1016dacad`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1016dac68`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1016dacc4`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1016dac68`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1016dacc4`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x1016db794`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x1016db794`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1016db323`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1016db360`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1016db323`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1016db360`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1016db32f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1016db36c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1016db32f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1016db36c`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1016db207`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1016db5e2`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1016db207`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1016db5e2`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1016da8b3`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1016db6a6`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1016da8b3`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x1016db6a6`

## string_xrefs

- `0x1016dace9`: `AccessToken=`
- `0x1016dabd2`: `ActiveDirectoryPassword`
- `0x1016dad8b`: `ActiveDirectoryPassword`
- `0x1016dabf3`: `ActiveDirectoryMSI`
- `0x1016dad82`: `ActiveDirectoryMSI`
- `0x1016dad79`: `AccessToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall COledbConnect::GetUserProperty(
        __int64 a1,
        __int64 a2,
        _BYTE *a3,
        _BYTE *a4,
        __int64 a5,
        _BYTE *a6,
        void **a7,
        _QWORD *a8,
        void **a9,
        void **a10,
        _DWORD *a11,
        void **a12,
        _DWORD *a13)
{
  _BYTE *v14; // r14
  __int64 v15; // r13
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rdi
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  void *v22; // rdi
  void **v23; // rbx
  const void *v24; // r14
  __int64 v25; // rbx
  __int64 v26; // rdx
  void *v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rax
  struct ISecurityContext *v30; // rdi
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 v33; // rdx
  _BYTE *v34; // rdi
  _QWORD *v35; // r12
  void **v36; // r14
  _BYTE *v37; // r13
  __int64 v38; // rdi
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // r12
  __int64 v43; // rax
  wchar_t *v44; // rdi
  __int64 v45; // rbx
  unsigned int v46; // ebx
  __int64 v47; // rsi
  CDefaultCollation *v48; // rax
  int *v49; // rsi
  __int64 v50; // rbx
  unsigned int v51; // ebx
  __int64 v52; // rsi
  CDefaultCollation *v53; // rax
  bool v54; // al
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  const wchar_t *v59; // rax
  int v60; // eax
  int v61; // edx
  __int64 v62; // rax
  __int64 v63; // rdi
  __int64 v64; // r10
  unsigned __int64 v65; // rcx
  unsigned __int64 v66; // rax
  void *v67; // rdi
  void **v68; // rbx
  __int64 v69; // rdx
  __int64 (__fastcall ***v70)(_QWORD, _QWORD); // rbx
  __int64 v71; // rdi
  __int64 v72; // rdx
  __int64 v73; // rbx
  __int64 *v74; // rsi
  __int64 v75; // rcx
  rsize_t v76; // rbx
  const void *v77; // rsi
  __int64 FeatureExtension; // rax
  __int64 v79; // rdi
  __int64 v80; // r10
  unsigned __int64 v81; // rcx
  unsigned __int64 v82; // rax
  void *v83; // r14
  void **v84; // r12
  __int64 v85; // rdi
  unsigned int v86; // r8d
  __int64 v87; // rbx
  __int64 v88; // r10
  unsigned __int64 v89; // rax
  wchar_t *v90; // rbx
  _QWORD *v91; // rsi
  unsigned int v92; // eax
  unsigned __int64 v93; // rsi
  __int64 v94; // rdi
  __int64 v95; // rdx
  void *v96; // rdi
  unsigned int v97; // r14d
  __int64 v98; // rdi
  __int64 v99; // rdx
  void *v100; // rbx
  __int64 v101; // rdi
  __int64 v102; // rcx
  struct ISECMemoryProtector *v103; // r14
  __int64 v104; // rcx
  void *v105; // rbx
  __int64 v106; // rax
  __int64 v107; // rdi
  __int64 v108; // rbx
  __int64 v109; // rcx
  unsigned __int64 v110; // rax
  wchar_t *v111; // rbx
  __int64 (__fastcall ***v112)(_QWORD, _QWORD); // rdi
  __int64 v113; // rbx
  __int64 v114; // rdx
  __int64 v115; // rbx
  __int64 v116; // rcx
  __int64 v117; // rax
  __int64 v118; // rbx
  __int64 v119; // rcx
  wchar_t *v120; // rdi
  __int64 v121; // rdi
  __int64 v122; // rcx
  struct ISECMemoryProtector *v123; // rbx
  __int64 v124; // rcx
  char v125; // [rsp+30h] [rbp-D0h] BYREF
  char v126; // [rsp+31h] [rbp-CFh]
  _DWORD SourceSize[3]; // [rsp+34h] [rbp-CCh] BYREF
  int v128; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v129; // [rsp+48h] [rbp-B8h]
  _BYTE *v130; // [rsp+50h] [rbp-B0h]
  void **v131; // [rsp+58h] [rbp-A8h]
  void *Source; // [rsp+60h] [rbp-A0h]
  unsigned int v133; // [rsp+68h] [rbp-98h] BYREF
  void (__fastcall ****v134)(_QWORD, __int64); // [rsp+70h] [rbp-90h] BYREF
  __int64 v135; // [rsp+78h] [rbp-88h]
  _BYTE *v136; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v137; // [rsp+88h] [rbp-78h] BYREF
  void **v138; // [rsp+90h] [rbp-70h] BYREF
  __int64 v139; // [rsp+98h] [rbp-68h]
  void (__fastcall ***v140)(_QWORD, __int64); // [rsp+A0h] [rbp-60h] BYREF
  _BYTE *v141; // [rsp+A8h] [rbp-58h]
  void **v142; // [rsp+B0h] [rbp-50h]
  void **v143; // [rsp+B8h] [rbp-48h]
  __int64 v144; // [rsp+C0h] [rbp-40h]
  __int64 v145; // [rsp+C8h] [rbp-38h]
  __int64 v146; // [rsp+D0h] [rbp-30h]
  __m128i si128; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v148; // [rsp+E8h] [rbp-18h]
  __int64 v149; // [rsp+F0h] [rbp-10h]
  GUID v150; // [rsp+F8h] [rbp-8h]
  int v151; // [rsp+108h] [rbp+8h]
  __int16 v152; // [rsp+10Ch] [rbp+Ch]
  _OWORD v153[2]; // [rsp+110h] [rbp+10h] BYREF
  int v154; // [rsp+130h] [rbp+30h]
  wchar_t v155; // [rsp+134h] [rbp+34h]
  __int128 v156; // [rsp+138h] [rbp+38h] BYREF
  __int64 v157; // [rsp+148h] [rbp+48h]
  wchar_t v158; // [rsp+150h] [rbp+50h]
  _OWORD v159[3]; // [rsp+158h] [rbp+58h] BYREF
  _OWORD v160[2]; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int8 v161[512]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int8 Src[512]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v146 = -2;
  v141 = a4;
  v130 = a3;
  v135 = a5;
  v14 = a6;
  v136 = a6;
  v131 = a7;
  v129 = a8;
  v142 = a9;
  v143 = a12;
  *(_QWORD *)&SourceSize[1] = a13;
  v15 = *(_QWORD *)(*(_QWORD *)(a2 + 120) + 264LL);
  v144 = *(_QWORD *)(a2 + 72);
  v145 = *(_QWORD *)(v144 + 96);
  v151 = 0;
  v152 = 0;
  v150 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v148 = 0;
  v149 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 224LL))(v15, 1);
  (*(void (__fastcall **)(__int64, __m128i *))(*(_QWORD *)v16 + 200LL))(v16, &si128);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v15 + 392LL))(v15)
    || (v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 400LL))(v15)) != 0 )
  {
    LOBYTE(v17) = 1;
  }
  *v130 = v17;
  *v141 = 0;
  *a11 = 0;
  *a13 = 0;
  SourceSize[0] = 0;
  Source = (void *)(*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v15 + 416LL))(v15, SourceSize, 1);
  if ( SourceSize[0] )
  {
    v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v19 = *(_QWORD *)(v18 + 256);
    if ( !v19 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v19 = *(_QWORD *)(v18 + 256);
    }
    v20 = ((unsigned __int64)SourceSize[0] >> 1) + 1;
    v21 = 2 * v20;
    if ( !is_mul_ok(v20, 2u) )
      v21 = -1;
    v22 = operator new[](v21, *(struct IMemObj **)(v19 + 1000), "sql\\ntdbms\\msql\\utils\\oledbconn.cpp", 2157, 3u);
    v23 = v142;
    if ( *v142 != v22 )
      operator delete[](*v142);
    *v23 = v22;
    memcpy_s(v22, SourceSize[0], Source, SourceSize[0]);
    *((_WORD *)*v23 + ((unsigned __int64)SourceSize[0] >> 1)) = 0;
    if ( *v130 )
    {
      v24 = (const void *)(*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v15 + 408LL))(v15, a11);
      v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v26 = *(_QWORD *)(v25 + 256);
      if ( !v26 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v26 = *(_QWORD *)(v25 + 256);
      }
      v27 = operator new[](
              (unsigned int)*a11,
              *(struct IMemObj **)(v26 + 1000),
              "sql\\ntdbms\\msql\\utils\\oledbconn.cpp",
              2164,
              3u);
      if ( *a10 != v27 )
        operator delete[](*a10);
      *a10 = v27;
      memcpy_s(v27, (unsigned int)*a11, v24, (unsigned int)*a11);
      v14 = v136;
    }
  }
  if ( si128.m128i_i32[0] == 2
    || si128.m128i_i32[0] > 1u
    && si128.m128i_i32[2]
    && (v28 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 224LL))(v15, 1),
        !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v28 + 360LL))(v28))
    && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1)
    && (si128.m128i_i32[0] != 4
     || !*(_BYTE *)(a1 + 141)
     || !CPolybaseFeatureManager::IsPolybaseProvisioned((CPolybaseFeatureManager *)g_PolybaseFeatureManager, 1)
     || (FUseReplicatedServerContext() ? (v29 = qword_102ECFB00 + 28520) : (v29 = qword_102ECFB00 + 14864),
         !*(_BYTE *)(v29 + 13645))) )
  {
    ex_raise(152, 74, 16, 1);
  }
  if ( *((_BYTE *)qword_102EF3550 + 1456)
    && (*((_BYTE *)qword_102ECFB10 + 1300) & 1) == 0
    && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1)
    || *(_DWORD *)(a1 + 80) != -1 )
  {
LABEL_40:
    if ( *(_DWORD *)(a1 + 84) )
      goto LABEL_41;
    if ( *(_DWORD *)(a1 + 80) == -1 )
    {
      v35 = v129;
      v37 = v130;
LABEL_187:
      v36 = v131;
      v34 = (_BYTE *)v135;
      goto LABEL_188;
    }
    v138 = &AutoReadOnlyIMA::`vftable';
    v139 = 0;
    v134 = &v140;
    v140 = 0;
    v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v39 = *(_QWORD *)(v38 + 256);
    if ( !v39 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v39 = *(_QWORD *)(v38 + 256);
    }
    v40 = *(_QWORD *)(v39 + 1000);
    AutoReadOnlyXact::BeginCompatibleXact((AutoReadOnlyXact *)&v140, L"GetSession", 20, 0);
    ((void (__fastcall *)(void ***, __int64))*v138)(&v138, v40);
    v41 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v139 + 144LL))(
            v139,
            *(unsigned int *)(a1 + 80),
            0);
    v42 = 0;
    v126 = 1;
    if ( !v41
      || (v133 = 0,
          v43 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 408LL))(v15, &v133),
          (v42 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v41 + 136LL))(v41, v43, v133)) == 0)
      && (v42 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 144LL))(v41, 0), v126 = 0, !v42) )
    {
      ex_raise(74, 16, 16, 1);
    }
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v42 + 32LL))(v42, &v125);
    *v14 = v125 & 1;
    if ( !byte_102EDCD27 )
    {
      v49 = *(int **)&SourceSize[1];
      goto LABEL_92;
    }
    v160[0] = *(_OWORD *)L"Authentication=";
    v160[1] = *(_OWORD *)L"cation=";
    v44 = 0;
    v137 = 0;
    v128 = 0;
    if ( *(_QWORD *)(a1 + 32) )
    {
      if ( !(unsigned int)COledbConnect::ExtractPropertyValueFromProvstr(a1, v160, &v137, &v128, &v134) )
      {
        v159[0] = *(_OWORD *)L"ActiveDirectoryPassword";
        v159[1] = *(_OWORD *)L"rectoryPassword";
        v159[2] = *(_OWORD *)L"assword";
        v153[0] = *(_OWORD *)L"ActiveDirectoryMSI";
        v153[1] = *(_OWORD *)L"rectoryMSI";
        v154 = *(_DWORD *)L"SI";
        v155 = aActivedirector_0[18];
        v45 = -1;
        do
          ++v45;
        while ( *((_WORD *)v159 + v45) );
        v46 = 2 * v45;
        v44 = v137;
        v47 = -1;
        do
          ++v47;
        while ( v137[v47] );
        v48 = (CDefaultCollation *)CDefaultCollation::PDCServer(-1);
        if ( CDefaultCollation::FEqIgnoreCaseW(v48, v44, 2 * v47, (const wchar_t *)v159, v46) )
        {
          v49 = *(int **)&SourceSize[1];
          **(_DWORD **)&SourceSize[1] = 2;
        }
        else
        {
          v50 = -1;
          do
            ++v50;
          while ( *((_WORD *)v153 + v50) );
          v51 = 2 * v50;
          v52 = -1;
          do
            ++v52;
          while ( v44[v52] );
          v53 = (CDefaultCollation *)CDefaultCollation::PDCServer(-1);
          v54 = CDefaultCollation::FEqIgnoreCaseW(v53, v44, 2 * v52, (const wchar_t *)v153, v51);
          v49 = *(int **)&SourceSize[1];
          **(_DWORD **)&SourceSize[1] = v54 ? 3 : 0;
        }
LABEL_67:
        v55 = *v49;
        if ( *v49 )
          goto LABEL_72;
        v156 = *(_OWORD *)L"AccessToken=";
        v157 = *(_QWORD *)L"ken=";
        v158 = aAccesstoken[12];
        v136 = 0;
        v128 = 0;
        if ( *(_QWORD *)(a1 + 32)
          && !(unsigned int)COledbConnect::ExtractPropertyValueFromProvstr(a1, &v156, &v136, &v128, &v134) )
        {
          *v49 = 4;
        }
        operator delete[](v136);
        v55 = *v49;
        if ( *v49 )
        {
LABEL_72:
          if ( (v125 & 1) != 0 )
          {
            v56 = v55 - 1;
            if ( v56 )
            {
              v57 = v56 - 1;
              if ( v57 )
              {
                v58 = v57 - 1;
                if ( v58 )
                {
                  if ( v58 == 1 )
                    v59 = L"AccessToken";
                  else
                    v59 = 0;
                }
                else
                {
                  v59 = L"ActiveDirectoryMSI";
                }
              }
              else
              {
                v59 = L"ActiveDirectoryPassword";
              }
            }
            else
            {
              v59 = L"Passthrough";
            }
            if ( v126 )
              ex_raise(74, 48, 16, 1, v59);
            else
              ex_raise(74, 50, 16, 1, *(_QWORD *)(a1 + 128), v59);
          }
        }
        if ( ((*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v15 + 384LL))(v15) == 7
           || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v15 + 384LL))(v15) == 8)
          && (v125 & 1) != 0
          && !*v49 )
        {
          *v49 = 1;
        }
        operator delete[](v44);
LABEL_92:
        v60 = *v49;
        if ( !*v49 )
          goto LABEL_110;
        switch ( v60 )
        {
          case 1:
            if ( !byte_102EDCD29 )
            {
              v61 = 42;
LABEL_105:
              ex_raise(74, v61, 16, 1);
            }
            break;
          case 2:
            if ( !byte_102EDCD2E )
            {
              v61 = 47;
              goto LABEL_105;
            }
            break;
          case 4:
            if ( !byte_102EDCD2A )
            {
              v61 = 44;
              goto LABEL_105;
            }
            break;
          default:
            if ( v60 == 3 && !byte_102EDCD28 )
            {
              v61 = 46;
              goto LABEL_105;
            }
            break;
        }
        if ( *v49 == 3 )
        {
          v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          if ( v62 )
          {
            if ( *(_DWORD *)(v62 + 8) )
              ex_raise(74, 49, 16, 1);
          }
        }
LABEL_110:
        if ( (v125 & 1) != 0 )
        {
          if ( SourceSize[0] )
          {
            v63 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v64 = *(_QWORD *)(v63 + 256);
            if ( !v64 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v64 = *(_QWORD *)(v63 + 256);
            }
            v65 = ((unsigned __int64)SourceSize[0] >> 1) + 1;
            v66 = 2 * v65;
            if ( !is_mul_ok(v65, 2u) )
              v66 = -1;
            v67 = operator new[](
                    v66,
                    *(struct IMemObj **)(v64 + 1000),
                    "sql\\ntdbms\\msql\\utils\\oledbconn.cpp",
                    2340,
                    3u);
            v68 = v131;
            if ( *v131 != v67 )
              operator delete[](*v131);
            *v68 = v67;
            memcpy_s(v67, SourceSize[0] + 2LL, Source, SourceSize[0]);
            *((_WORD *)*v68 + ((unsigned __int64)SourceSize[0] >> 1)) = 0;
          }
          if ( COledbConnect::FImpersonated() )
            ex_raise(74, 37, 16, 1);
          v70 = *(__int64 (__fastcall ****)(_QWORD, _QWORD))(v144 + 208);
          if ( v70 )
          {
            v71 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v72 = *(_QWORD *)(v71 + 256);
            if ( !v72 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v72 = *(_QWORD *)(v71 + 256);
            }
            v73 = (**v70)(v70, *(_QWORD *)(v72 + 1000));
            v74 = v129;
            v75 = *v129;
            if ( *v129 != v73 && v75 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v75 + 8LL))(v75, 1);
            *v74 = v73;
            if ( !v73 )
            {
              LOBYTE(v75) = 101;
              ex_raise_oom(v75);
            }
            v49 = *(int **)&SourceSize[1];
          }
          v37 = v130;
          if ( *v130 )
            *v141 = 1;
          if ( *v49 == 1 )
          {
            v76 = 0;
            v77 = 0;
            if ( !v145
              || (LOBYTE(v69) = 2, (FeatureExtension = CPhysicalConnection::GetFeatureExtension(v145, v69)) == 0)
              || (v76 = *(unsigned int *)(FeatureExtension + 64), (v77 = *(const void **)(FeatureExtension + 56)) == 0)
              || !(_DWORD)v76 )
            {
              ex_raise(74, 41, 16, 1);
            }
            v79 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v80 = *(_QWORD *)(v79 + 256);
            if ( !v80 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v80 = *(_QWORD *)(v79 + 256);
            }
            v81 = (v76 >> 1) + 1;
            v82 = 2 * v81;
            if ( !is_mul_ok(v81, 2u) )
              v82 = -1;
            v83 = operator new[](
                    v82,
                    *(struct IMemObj **)(v80 + 1000),
                    "sql\\ntdbms\\msql\\utils\\oledbconn.cpp",
                    2403,
                    3u);
            v84 = v143;
            if ( *v143 != v83 )
              operator delete[](*v143);
            *v84 = v83;
            memcpy_s(v83, v76, v77, v76);
            *((_WORD *)*v84 + (v76 >> 1)) = 0;
          }
        }
        else
        {
          v85 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          v86 = *(_DWORD *)(v85 + 8);
          if ( v86 )
          {
            v87 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v88 = *(_QWORD *)(v87 + 256);
            if ( !v88 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v88 = *(_QWORD *)(v87 + 256);
              v86 = *(_DWORD *)(v85 + 8);
            }
            v89 = 2 * (((unsigned __int64)v86 >> 1) + 1);
            if ( !is_mul_ok(((unsigned __int64)v86 >> 1) + 1, 2u) )
              v89 = -1;
            v90 = (wchar_t *)operator new[](
                               v89,
                               *(struct IMemObj **)(v88 + 1000),
                               "sql\\ntdbms\\msql\\utils\\oledbconn.cpp",
                               2417,
                               3u);
            v91 = v131;
            if ( *v131 != v90 )
              operator delete[](*v131);
            *v91 = v90;
            wcsncpy_s(
              v90,
              ((unsigned __int64)*(unsigned int *)(v85 + 8) >> 1) + 1,
              *(const wchar_t **)v85,
              (unsigned __int64)*(unsigned int *)(v85 + 8) >> 1);
            *(_WORD *)(*v91 + 2 * ((unsigned __int64)*(unsigned int *)(v85 + 8) >> 1)) = 0;
          }
          v92 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v42 + 24LL))(v42, 0, 0);
          v93 = v92;
          if ( v92 )
          {
            Source = 0;
            if ( (*((_BYTE *)qword_102ECFB10 + 575) & 0x40) != 0 || *(_DWORD *)(qword_102ECFB00 + 14544) )
            {
              v97 = v92 + 2;
              v98 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v99 = *(_QWORD *)(v98 + 256);
              if ( !v99 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v99 = *(_QWORD *)(v98 + 256);
              }
              v100 = operator new[](
                       v97,
                       *(struct IMemObj **)(v99 + 1000),
                       "sql\\ntdbms\\msql\\utils\\oledbconn.cpp",
                       2455,
                       3u);
              if ( v100 )
                operator delete[](0);
              Source = v100;
              (*(void (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v42 + 24LL))(v42, v100, v97);
              decryptlinkedpasswd(
                (unsigned __int8 *)v100,
                (unsigned int)v93,
                (unsigned __int8 *)v100,
                (unsigned int)v93);
            }
            else
            {
              (*(void (__fastcall **)(__int64, unsigned __int8 *, __int64))(*(_QWORD *)v42 + 24LL))(v42, v161, 512);
              SourceSize[1] = 512;
              DecryptByServiceMasterKey(v161, v93, Src, &SourceSize[1]);
              v93 = SourceSize[1];
              v94 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset;
              v95 = *(_QWORD *)(v94 + 256);
              if ( !v95 )
              {
                SystemThread::MakeMiniSOSThread(0);
                v95 = *(_QWORD *)(v94 + 256);
              }
              v96 = operator new[](
                      v93 + 2,
                      *(struct IMemObj **)(v95 + 1000),
                      "sql\\ntdbms\\msql\\utils\\oledbconn.cpp",
                      2448,
                      3u);
              if ( v96 )
                operator delete[](0);
              Source = v96;
              if ( (_DWORD)v93 )
              {
                if ( v96 )
                {
                  if ( v93 + 2 < v93 )
                  {
                    memset_0(v96, 0, v93 + 2);
                    *_errno() = 34;
                    _invalid_parameter_noinfo();
                  }
                  else
                  {
                    memmove(v96, Src, v93);
                  }
                }
                else
                {
                  *_errno() = 22;
                  _invalid_parameter_noinfo();
                }
              }
            }
            v101 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            v102 = *(_QWORD *)(v101 + 256);
            if ( !v102 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v102 = *(_QWORD *)(v101 + 256);
            }
            v103 = ISECMemoryProtector::Get(*(struct IMemObj **)(v102 + 1000));
            v35 = v129;
            v104 = *v129;
            if ( (struct ISECMemoryProtector *)*v129 != v103 && v104 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v104 + 8LL))(v104, 1);
            *v35 = v103;
            v105 = Source;
            if ( !v103
              || !(*(unsigned int (__fastcall **)(struct ISECMemoryProtector *, void *, _QWORD, _QWORD))(*(_QWORD *)v103 + 16LL))(
                    v103,
                    Source,
                    (unsigned int)v93,
                    0) )
            {
              memset(v105, 0, v93);
              ex_raise_oom(101);
            }
            memset(v105, 0, v93);
            operator delete[](v105);
            v37 = v130;
            goto LABEL_182;
          }
          v37 = v130;
        }
        v35 = v129;
LABEL_182:
        v138 = &AutoReadOnlyIMA::`vftable';
        if ( v139 )
          (**(void (__fastcall ***)(__int64, __int64))v139)(v139, 1);
        v143 = (void **)&v140;
        if ( v140 )
          (**v140)(v140, 1);
        goto LABEL_187;
      }
      v44 = v137;
    }
    v49 = *(int **)&SourceSize[1];
    goto LABEL_67;
  }
  if ( !*(_DWORD *)(a1 + 84) )
  {
    if ( !*(_BYTE *)(a1 + 141) )
    {
      v30 = *(struct ISecurityContext **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + SystemThread_TlsIndex)
                                                                + SystemThread_TlsOffset)
                                                    + 120LL)
                                        + 264LL);
      ISECManager::IsTrustedToExecuteByCfgId(16391, v30);
      if ( !(**(unsigned int (__fastcall ***)(struct ISecurityContext *))v30)(v30)
        && ((*(_BYTE *)(a1 + 144) & 0x40) == 0 || (*(_BYTE *)(a1 + 148) & 0x40) != 0) )
      {
        v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        ex_raise(74, 15, 16, 1, v31);
      }
    }
    goto LABEL_40;
  }
LABEL_41:
  v32 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v33 = *(_QWORD *)(v32 + 256);
  if ( !v33 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v33 = *(_QWORD *)(v32 + 256);
  }
  v34 = (_BYTE *)v135;
  v35 = v129;
  v36 = v131;
  COledbConnect::GetExtDataSourceProperties(a1, *(_QWORD *)(v33 + 1000), v131, v129, v135);
  v37 = v130;
  *v130 = 0;
LABEL_188:
  *v34 |= *(_BYTE *)(a1 + 149) >> 7;
  if ( !*v36 )
  {
    v106 = *(_QWORD *)(a1 + 64);
    if ( v106 )
    {
      v107 = -1;
      do
        ++v107;
      while ( *(_WORD *)(v106 + 2 * v107) );
      v108 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v109 = *(_QWORD *)(v108 + 256);
      if ( !v109 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v109 = *(_QWORD *)(v108 + 256);
      }
      v110 = 2LL * (unsigned int)(v107 + 1);
      if ( !is_mul_ok((unsigned int)(v107 + 1), 2u) )
        v110 = -1;
      v111 = (wchar_t *)operator new[](
                          v110,
                          *(struct IMemObj **)(v109 + 1000),
                          "sql\\ntdbms\\msql\\utils\\oledbconn.cpp",
                          2481,
                          3u);
      if ( *v36 != v111 )
        operator delete[](*v36);
      *v36 = v111;
      wcsncpy_s(v111, (unsigned int)(v107 + 1), *(const wchar_t **)(a1 + 64), (unsigned int)v107);
      *((_WORD *)*v36 + (unsigned int)v107) = 0;
    }
  }
  if ( !*v35 )
  {
    v112 = *(__int64 (__fastcall ****)(_QWORD, _QWORD))(a1 + 72);
    if ( v112 )
    {
      v113 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v114 = *(_QWORD *)(v113 + 256);
      if ( !v114 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v114 = *(_QWORD *)(v113 + 256);
        v112 = *(__int64 (__fastcall ****)(_QWORD, _QWORD))(a1 + 72);
      }
      v115 = (**v112)(v112, *(_QWORD *)(v114 + 1000));
      v116 = *v35;
      if ( *v35 != v115 && v116 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v116 + 8LL))(v116, 1);
      *v35 = v115;
      if ( !v115 )
      {
        LOBYTE(v116) = 101;
        ex_raise_oom(v116);
      }
    }
  }
  if ( *(_BYTE *)(a1 + 141)
    && CPolybaseFeatureManager::IsPolybaseProvisioned((CPolybaseFeatureManager *)g_PolybaseFeatureManager, 1) )
  {
    v117 = FUseReplicatedServerContext() ? qword_102ECFB00 + 28520 : qword_102ECFB00 + 14864;
    if ( *(_BYTE *)(v117 + 13645) )
    {
      if ( si128.m128i_i32[0] != 4
        && *v37
        && (!OsInfo::IsLinux(SOS_OS_OsInfo)
         || *(_BYTE *)(qword_102ECFB00 + 48768)
         && *(_BYTE *)(qword_102ECFB00 + 48777)
         && *(_BYTE *)(qword_102ECFB00 + 48778)) )
      {
        if ( *v36 )
          operator delete[](*v36);
        *v36 = 0;
        if ( *v35 )
          (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v35 + 8LL))(*v35, 1);
        *v35 = 0;
      }
      else
      {
        *v37 = 0;
        if ( !*v36 )
        {
          v118 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v119 = *(_QWORD *)(v118 + 256);
          if ( !v119 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v119 = *(_QWORD *)(v118 + 256);
          }
          v120 = WszFromWsz(*(struct IMemObj **)(v119 + 1000), (const wchar_t *)*v142, 0);
          if ( *v36 != v120 )
            operator delete[](*v36);
          *v36 = v120;
        }
        if ( !*v35 )
        {
          LODWORD(v134) = *(_DWORD *)L"*";
          v121 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v122 = *(_QWORD *)(v121 + 256);
          if ( !v122 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v122 = *(_QWORD *)(v121 + 256);
          }
          v123 = ISECMemoryProtector::Get(*(struct IMemObj **)(v122 + 1000));
          v124 = *v35;
          if ( (struct ISECMemoryProtector *)*v35 != v123 && v124 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v124 + 8LL))(v124, 1);
          *v35 = v123;
          if ( !v123
            || !(*(unsigned int (__fastcall **)(struct ISECMemoryProtector *, void (__fastcall *****)(_QWORD, __int64), __int64))(*(_QWORD *)v123 + 16LL))(
                  v123,
                  &v134,
                  2) )
          {
            LOBYTE(v124) = 101;
            ex_raise_oom(v124);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1016da580  push    rbp
0x1016da582  push    rbx
0x1016da583  push    rsi
0x1016da584  push    rdi
0x1016da585  push    r12
0x1016da587  push    r13
0x1016da589  push    r14
0x1016da58b  push    r15
0x1016da58d  lea     rbp, [rsp-4C8h]
0x1016da595  sub     rsp, 5C8h
0x1016da59c  mov     [rbp+500h+var_530], 0FFFFFFFFFFFFFFFEh
0x1016da5a4  mov     rax, cs:__security_cookie
0x1016da5ab  xor     rax, rsp
0x1016da5ae  mov     [rbp+500h+var_50], rax
0x1016da5b5  mov     [rbp+500h+var_558], r9
0x1016da5b9  mov     [rsp+600h+var_5B0], r8
0x1016da5be  mov     r15, rcx
0x1016da5c1  mov     rax, [rbp+500h+arg_20]
0x1016da5c8  mov     [rsp+600h+var_588], rax
0x1016da5cd  mov     r14, [rbp+500h+arg_28]
0x1016da5d4  mov     [rbp+500h+var_580], r14
0x1016da5d8  mov     rax, [rbp+500h+arg_30]
0x1016da5df  mov     [rsp+600h+var_5A8], rax
0x1016da5e4  mov     rax, [rbp+500h+arg_38]
0x1016da5eb  mov     [rsp+600h+var_5B8], rax
0x1016da5f0  mov     rax, [rbp+500h+arg_40]
0x1016da5f7  mov     [rbp+500h+var_550], rax
0x1016da5fb  mov     r12, [rbp+500h+arg_48]
0x1016da602  mov     rsi, [rbp+500h+arg_50]
0x1016da609  mov     rax, [rbp+500h+arg_58]
0x1016da610  mov     [rbp+500h+var_548], rax
0x1016da614  mov     rbx, [rbp+500h+arg_60]
0x1016da61b  mov     qword ptr [rsp+600h+SourceSize+4], rbx
0x1016da620  mov     rax, [rdx+78h]
0x1016da624  mov     r13, [rax+108h]
0x1016da62b  mov     rax, [rdx+48h]
0x1016da62f  mov     [rbp+500h+var_540], rax
0x1016da633  mov     rcx, [rax+60h]
0x1016da637  mov     [rbp+500h+var_538], rcx
0x1016da63b  xor     eax, eax
0x1016da63d  mov     [rbp+500h+var_4F8], eax
0x1016da640  mov     [rbp+500h+var_4F4], ax
0x1016da644  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data1; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x1016da64b  movups  [rbp+500h+var_508], xmm0
0x1016da64f  movdqa  xmm1, cs:__xmm@00000001000000000000000000000000
0x1016da657  movdqu  [rbp+500h+var_528], xmm1
0x1016da65c  mov     [rbp+500h+var_518], rax
0x1016da660  mov     [rbp+500h+var_510], rax
0x1016da664  mov     rax, [r13+0]
0x1016da668  mov     edx, 1
0x1016da66d  mov     rcx, r13
0x1016da670  call    qword ptr [rax+0E0h]
0x1016da676  mov     rdi, [rax]
0x1016da679  lea     rdx, [rbp+500h+var_528]
0x1016da67d  mov     rcx, rax
0x1016da680  call    qword ptr [rdi+0C8h]
0x1016da686  mov     rax, [r13+0]
0x1016da68a  mov     rcx, r13
0x1016da68d  call    qword ptr [rax+188h]
0x1016da693  test    eax, eax
0x1016da695  jnz     short loc_1016DA6A8
0x1016da697  mov     rax, [r13+0]
0x1016da69b  mov     rcx, r13
0x1016da69e  call    qword ptr [rax+190h]
0x1016da6a4  test    eax, eax
0x1016da6a6  jz      short loc_1016DA6AA
0x1016da6a8  mov     al, 1
0x1016da6aa  mov     rcx, [rsp+600h+var_5B0]
0x1016da6af  mov     [rcx], al
0x1016da6b1  mov     rax, [rbp+500h+var_558]
0x1016da6b5  mov     byte ptr [rax], 0
0x1016da6b8  xor     eax, eax
0x1016da6ba  mov     [rsi], eax
0x1016da6bc  mov     [rbx], eax
0x1016da6be  mov     dword ptr [rsp+600h+SourceSize], eax
0x1016da6c2  mov     rax, [r13+0]
0x1016da6c6  mov     r8d, 1
0x1016da6cc  lea     rdx, [rsp+600h+SourceSize]
0x1016da6d1  mov     rcx, r13
0x1016da6d4  call    qword ptr [rax+1A0h]
0x1016da6da  mov     [rsp+600h+Source], rax
0x1016da6df  cmp     dword ptr [rsp+600h+SourceSize], 0
0x1016da6e4  jz      loc_1016DA844
0x1016da6ea  mov     rdi, gs:58h
0x1016da6f3  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x1016da6fa  mov     edx, [rcx]
0x1016da6fc  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x1016da703  mov     ebx, [rcx]
0x1016da705  add     rbx, [rdi+rdx*8]
0x1016da709  mov     rdi, [rbx+100h]
0x1016da710  test    rdi, rdi
0x1016da713  jnz     short loc_1016DA724
0x1016da715  xor     ecx, ecx
0x1016da717  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1016da71d  mov     rdi, [rbx+100h]
0x1016da724  mov     ecx, dword ptr [rsp+600h+SourceSize]
0x1016da728  shr     rcx, 1
0x1016da72b  inc     rcx
0x1016da72e  mov     eax, 2
0x1016da733  mul     rcx
0x1016da736  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1016da73d  cmovo   rax, rdx
0x1016da741  mov     byte ptr [rsp+600h+var_5E0], 3
0x1016da746  mov     r9d, 86Dh
0x1016da74c  lea     r8, aSqlNtdbmsMsqlU_4; "sql\\ntdbms\\msql\\utils\\oledbconn.cpp"
0x1016da753  mov     rdx, [rdi+3E8h]
0x1016da75a  mov     rcx, rax
0x1016da75d  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1016da763  mov     rdi, rax
0x1016da766  mov     rbx, [rbp+500h+var_550]
0x1016da76a  mov     rcx, [rbx]
0x1016da76d  cmp     rcx, rax
0x1016da770  jz      short loc_1016DA778
0x1016da772  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1016da778  mov     [rbx], rdi
0x1016da77b  mov     edx, dword ptr [rsp+600h+SourceSize]; DestinationSize
0x1016da77f  mov     r9d, edx; SourceSize
0x1016da782  mov     r8, [rsp+600h+Source]; Source
0x1016da787  mov     rcx, rdi; Destination
0x1016da78a  call    memcpy_s
0x1016da78f  mov     ecx, dword ptr [rsp+600h+SourceSize]
0x1016da793  shr     rcx, 1
0x1016da796  mov     rax, [rbx]
0x1016da799  xor     edx, edx
0x1016da79b  mov     [rax+rcx*2], dx
0x1016da79f  mov     rax, [rsp+600h+var_5B0]
0x1016da7a4  cmp     [rax], dl
0x1016da7a6  jz      loc_1016DA844
0x1016da7ac  mov     rax, [r13+0]
0x1016da7b0  mov     rdx, rsi
0x1016da7b3  mov     rcx, r13
0x1016da7b6  call    qword ptr [rax+198h]
0x1016da7bc  mov     r14, rax
0x1016da7bf  mov     rdi, gs:58h
0x1016da7c8  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x1016da7cf  mov     edx, [rcx]
0x1016da7d1  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x1016da7d8  mov     ebx, [rcx]
0x1016da7da  add     rbx, [rdi+rdx*8]
0x1016da7de  mov     rdx, [rbx+100h]
0x1016da7e5  test    rdx, rdx
0x1016da7e8  jnz     short loc_1016DA7F9
0x1016da7ea  xor     ecx, ecx
0x1016da7ec  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1016da7f2  mov     rdx, [rbx+100h]
0x1016da7f9  mov     ecx, [rsi]
0x1016da7fb  mov     byte ptr [rsp+600h+var_5E0], 3
0x1016da800  mov     r9d, 874h
0x1016da806  lea     r8, aSqlNtdbmsMsqlU_4; "sql\\ntdbms\\msql\\utils\\oledbconn.cpp"
0x1016da80d  mov     rdx, [rdx+3E8h]
0x1016da814  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1016da81a  mov     rdi, rax
0x1016da81d  mov     rcx, [r12]
0x1016da821  cmp     rcx, rax
0x1016da824  jz      short loc_1016DA82C
0x1016da826  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1016da82c  mov     [r12], rdi
0x1016da830  mov     edx, [rsi]; DestinationSize
0x1016da832  mov     r9d, edx; SourceSize
0x1016da835  mov     r8, r14; Source
0x1016da838  mov     rcx, rdi; Destination
0x1016da83b  call    memcpy_s
0x1016da840  mov     r14, [rbp+500h+var_580]
0x1016da844  mov     eax, dword ptr [rbp+500h+var_528]
0x1016da847  cmp     eax, 2
0x1016da84a  jz      loc_1016DA8DB
0x1016da850  cmp     eax, 1
0x1016da853  jbe     loc_1016DA8F1
0x1016da859  cmp     dword ptr [rbp+500h+var_528+8], 0
0x1016da85d  jz      loc_1016DA8F1
0x1016da863  mov     rax, [r13+0]
0x1016da867  mov     edx, 1
0x1016da86c  mov     rcx, r13
0x1016da86f  call    qword ptr [rax+0E0h]
0x1016da875  mov     rdx, [rax]
0x1016da878  mov     rcx, rax
0x1016da87b  call    qword ptr [rdx+168h]
0x1016da881  test    eax, eax
0x1016da883  jnz     short loc_1016DA8F1
0x1016da885  mov     rax, [r15]
0x1016da888  mov     rcx, r15
0x1016da88b  call    qword ptr [rax+58h]
0x1016da88e  test    al, al
0x1016da890  jnz     short loc_1016DA8F1
0x1016da892  cmp     dword ptr [rbp+500h+var_528], 4
0x1016da896  jnz     short loc_1016DA8DB
0x1016da898  cmp     [r15+8Dh], al
0x1016da89f  jz      short loc_1016DA8DB
0x1016da8a1  mov     dl, 1; bool
0x1016da8a3  lea     rcx, ?g_PolybaseFeatureManager@@3VCPolybaseFeatureManager@@A; this
0x1016da8aa  call    ?IsPolybaseProvisioned@CPolybaseFeatureManager@@QEAA_N_N@Z; CPolybaseFeatureManager::IsPolybaseProvisioned(bool)
0x1016da8af  test    al, al
0x1016da8b1  jz      short loc_1016DA8DB
0x1016da8b3  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x1016da8b9  test    al, al
0x1016da8bb  mov     rax, cs:qword_102ECFB00
0x1016da8c2  jnz     short loc_1016DA8CC
0x1016da8c4  add     rax, 3A10h
0x1016da8ca  jmp     short loc_1016DA8D2
0x1016da8cc  add     rax, 6F68h
0x1016da8d2  cmp     byte ptr [rax+354Dh], 0
0x1016da8d9  jnz     short loc_1016DA8F1
0x1016da8db  mov     edx, 4Ah ; 'J'
0x1016da8e0  lea     ecx, [rdx+4Eh]
0x1016da8e3  lea     r9d, [rdx-49h]
0x1016da8e7  lea     r8d, [rdx-3Ah]
0x1016da8eb  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016da8f1  mov     rax, cs:qword_102EF3550
0x1016da8f8  cmp     byte ptr [rax+5B0h], 0
0x1016da8ff  jz      short loc_1016DA922
0x1016da901  mov     rax, cs:qword_102ECFB10
0x1016da908  test    byte ptr [rax+514h], 1
0x1016da90f  jnz     short loc_1016DA922
0x1016da911  mov     rax, [r15]
0x1016da914  mov     rcx, r15
0x1016da917  call    qword ptr [rax+58h]
0x1016da91a  test    al, al
0x1016da91c  jnz     loc_1016DA9C0
0x1016da922  cmp     dword ptr [r15+50h], 0FFFFFFFFh
0x1016da927  jnz     loc_1016DA9C0
0x1016da92d  cmp     dword ptr [r15+54h], 0
0x1016da932  jnz     loc_1016DA9C7
0x1016da938  cmp     byte ptr [r15+8Dh], 0
0x1016da940  jnz     short loc_1016DA9C0
0x1016da942  mov     rdx, gs:58h
0x1016da94b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016da952  mov     ecx, [rax]
0x1016da954  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016da95b  mov     eax, [rax]
0x1016da95d  add     rax, [rdx+rcx*8]
0x1016da961  mov     rax, [rax]
0x1016da964  mov     rcx, [rax+78h]
0x1016da968  mov     rdi, [rcx+108h]
0x1016da96f  mov     rdx, rdi; struct ISecurityContext *
0x1016da972  mov     ecx, 4007h; int
0x1016da977  call    ?IsTrustedToExecuteByCfgId@ISECManager@@SAXHPEAVISecurityContext@@@Z; ISECManager::IsTrustedToExecuteByCfgId(int,ISecurityContext *)
0x1016da97c  mov     rax, [rdi]
0x1016da97f  mov     rcx, rdi
0x1016da982  call    qword ptr [rax]
0x1016da984  test    eax, eax
0x1016da986  jnz     short loc_1016DA9C0
0x1016da988  test    byte ptr [r15+90h], 40h
0x1016da990  jz      short loc_1016DA99C
0x1016da992  test    byte ptr [r15+94h], 40h
0x1016da99a  jz      short loc_1016DA9C0
0x1016da99c  mov     rax, [r15]
0x1016da99f  mov     rcx, r15
0x1016da9a2  call    qword ptr [rax+18h]
0x1016da9a5  mov     [rsp+600h+var_5E0], rax
0x1016da9aa  mov     edx, 0Fh
0x1016da9af  lea     ecx, [rdx+3Bh]
0x1016da9b2  lea     r9d, [rdx-0Eh]
0x1016da9b6  lea     r8d, [rdx+1]
0x1016da9ba  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1016da9c0  cmp     dword ptr [r15+54h], 0
0x1016da9c5  jz      short loc_1016DAA39
0x1016da9c7  mov     rdx, gs:58h
0x1016da9d0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016da9d7  mov     ecx, [rax]
0x1016da9d9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016da9e0  mov     edi, [rax]
0x1016da9e2  add     rdi, [rdx+rcx*8]
0x1016da9e6  mov     rdx, [rdi+100h]
0x1016da9ed  test    rdx, rdx
0x1016da9f0  jnz     short loc_1016DAA01
0x1016da9f2  xor     ecx, ecx
0x1016da9f4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1016da9fa  mov     rdx, [rdi+100h]
0x1016daa01  mov     rdi, [rsp+600h+var_588]
0x1016daa06  mov     [rsp+600h+var_5E0], rdi
0x1016daa0b  mov     r12, [rsp+600h+var_5B8]
0x1016daa10  mov     r9, r12
0x1016daa13  mov     r14, [rsp+600h+var_5A8]
0x1016daa18  mov     r8, r14
0x1016daa1b  mov     rdx, [rdx+3E8h]
0x1016daa22  mov     rcx, r15
0x1016daa25  call    ?GetExtDataSourceProperties@COledbConnect@@AEBAXPEAVIMemObj@@AEAV?$CAutoRg@_W@@AEAV?$CAutoP@VISECMemoryProtector@@@@AEA_N@Z; COledbConnect::GetExtDataSourceProperties(IMemObj *,CAutoRg<wchar_t> &,CAutoP<ISECMemoryProtector> &,bool &)
0x1016daa2a  mov     r13, [rsp+600h+var_5B0]
0x1016daa2f  mov     byte ptr [r13+0], 0
0x1016daa34  jmp     loc_1016DB51A
0x1016daa39  cmp     dword ptr [r15+50h], 0FFFFFFFFh
0x1016daa3e  jz      loc_1016DB506
0x1016daa44  lea     rax, ??_7AutoReadOnlyIMA@@6B@; const AutoReadOnlyIMA::`vftable'
0x1016daa4b  mov     [rbp+500h+var_570], rax
0x1016daa4f  xor     esi, esi
0x1016daa51  mov     [rbp+500h+var_568], rsi
0x1016daa55  lea     rax, [rbp+500h+var_560]
0x1016daa59  mov     [rsp+600h+var_590], rax
0x1016daa5e  mov     [rbp+500h+var_560], rsi
0x1016daa62  mov     rdx, gs:58h
0x1016daa6b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1016daa72  mov     ecx, [rax]
0x1016daa74  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1016daa7b  mov     edi, [rax]
0x1016daa7d  add     rdi, [rdx+rcx*8]
0x1016daa81  mov     rax, [rdi+100h]
0x1016daa88  test    rax, rax
0x1016daa8b  jnz     short loc_1016DAA9C
0x1016daa8d  xor     ecx, ecx
0x1016daa8f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
  ... truncated ...
```
