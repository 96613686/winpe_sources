# DBTABLE::PostRestoreReplicationFixup(void)

- ea: `0x102034f90`
- end: `0x1020365cd`
- name: `?PostRestoreReplicationFixup@DBTABLE@@QEAAHXZ`
- size: `5693`
- prototype: `__int64 __fastcall(DBTABLE *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x102034730`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x10047bc10`
- `0x1004abbd0`
- `0x10063f720`
- `0x10063f7c0`
- `0x10063f810`
- `0x100646db0`
- `0x10076d7e0`
- `0x101cfe150`
- `0x101f9c160`
- `0x101f9c200`
- `0x101f9c3b0`
- `0x101fd77e0`
- `0x101fd79d0`
- `0x101fd7b40`
- `0x101fd7b70`
- `0x102034f90`
- `0x1023aee60`

## import_xrefs

- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1020362c5`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x1020353aa`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x1020353aa`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x102036363`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x102036363`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x1020352ed`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020354a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020357e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102035c5c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020360c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020354a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020357e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102035c5c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020360c5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020350d0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10203527d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020352c8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020356a3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10203575f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020359e7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035a32`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035b41`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035bd1`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035d4a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035d95`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035f2c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035f77`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035fe9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102036068`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020361b3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020361fe`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102036500`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10203654c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020350d0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10203527d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020352c8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020356a3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10203575f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020359e7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035a32`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035b41`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035bd1`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035d4a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035d95`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035f2c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035f77`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102035fe9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102036068`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020361b3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1020361fe`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x102036500`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10203654c`
- `sqldk!SystemThread_TlsIndex` at `0x102034fe9`
- `sqldk!SystemThread_TlsIndex` at `0x1020350a1`
- `sqldk!SystemThread_TlsIndex` at `0x10203524e`
- `sqldk!SystemThread_TlsIndex` at `0x102035299`
- `sqldk!SystemThread_TlsIndex` at `0x102035316`
- `sqldk!SystemThread_TlsIndex` at `0x102035372`
- `sqldk!SystemThread_TlsIndex` at `0x1020353c6`
- `sqldk!SystemThread_TlsIndex` at `0x1020354b8`
- `sqldk!SystemThread_TlsIndex` at `0x10203551a`
- `sqldk!SystemThread_TlsIndex` at `0x102035674`
- `sqldk!SystemThread_TlsIndex` at `0x102035730`
- `sqldk!SystemThread_TlsIndex` at `0x1020357fa`
- `sqldk!SystemThread_TlsIndex` at `0x102035856`
- `sqldk!SystemThread_TlsIndex` at `0x1020359b8`
- `sqldk!SystemThread_TlsIndex` at `0x102035a03`
- `sqldk!SystemThread_TlsIndex` at `0x102035b0a`
- `sqldk!SystemThread_TlsIndex` at `0x102035ba2`
- `sqldk!SystemThread_TlsIndex` at `0x102035d1b`
- `sqldk!SystemThread_TlsIndex` at `0x102035d66`
- `sqldk!SystemThread_TlsIndex` at `0x102035df7`
- `sqldk!SystemThread_TlsIndex` at `0x102035efd`
- `sqldk!SystemThread_TlsIndex` at `0x102035f48`
- `sqldk!SystemThread_TlsIndex` at `0x102035fba`
- `sqldk!SystemThread_TlsIndex` at `0x102036039`
- `sqldk!SystemThread_TlsIndex` at `0x102036184`
- `sqldk!SystemThread_TlsIndex` at `0x1020361cf`
- `sqldk!SystemThread_TlsIndex` at `0x102036263`
- `sqldk!SystemThread_TlsIndex` at `0x10203632b`
- `sqldk!SystemThread_TlsIndex` at `0x1020364d0`
- `sqldk!SystemThread_TlsIndex` at `0x10203651c`
- `sqldk!SystemThread_TlsOffset` at `0x102034ff2`
- `sqldk!SystemThread_TlsOffset` at `0x1020350aa`
- `sqldk!SystemThread_TlsOffset` at `0x102035257`
- `sqldk!SystemThread_TlsOffset` at `0x1020352a2`
- `sqldk!SystemThread_TlsOffset` at `0x10203531f`
- `sqldk!SystemThread_TlsOffset` at `0x10203537b`
- `sqldk!SystemThread_TlsOffset` at `0x1020353cf`
- `sqldk!SystemThread_TlsOffset` at `0x1020354c9`
- `sqldk!SystemThread_TlsOffset` at `0x10203552b`
- `sqldk!SystemThread_TlsOffset` at `0x10203567d`
- `sqldk!SystemThread_TlsOffset` at `0x102035739`
- `sqldk!SystemThread_TlsOffset` at `0x102035803`
- `sqldk!SystemThread_TlsOffset` at `0x10203585f`
- `sqldk!SystemThread_TlsOffset` at `0x1020359c1`
- `sqldk!SystemThread_TlsOffset` at `0x102035a0c`
- `sqldk!SystemThread_TlsOffset` at `0x102035b13`
- `sqldk!SystemThread_TlsOffset` at `0x102035bab`
- `sqldk!SystemThread_TlsOffset` at `0x102035d24`
- `sqldk!SystemThread_TlsOffset` at `0x102035d6f`
- `sqldk!SystemThread_TlsOffset` at `0x102035e00`
- `sqldk!SystemThread_TlsOffset` at `0x102035f06`
- `sqldk!SystemThread_TlsOffset` at `0x102035f51`
- `sqldk!SystemThread_TlsOffset` at `0x102035fc3`
- `sqldk!SystemThread_TlsOffset` at `0x102036042`
- `sqldk!SystemThread_TlsOffset` at `0x10203618d`
- `sqldk!SystemThread_TlsOffset` at `0x1020361d8`
- `sqldk!SystemThread_TlsOffset` at `0x102036274`
- `sqldk!SystemThread_TlsOffset` at `0x102036334`
- `sqldk!SystemThread_TlsOffset` at `0x1020364d9`
- `sqldk!SystemThread_TlsOffset` at `0x102036525`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203500d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203533a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102035394`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020353ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203581e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203587a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102035e1b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203634d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203500d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203533a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102035394`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020353ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203581e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203587a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102035e1b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10203634d`
- `sqldk!??_V@YAXPEAX@Z` at `0x102035dda`
- `sqldk!??_V@YAXPEAX@Z` at `0x102036240`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020362fd`
- `sqldk!??_V@YAXPEAX@Z` at `0x102036591`
- `sqldk!??_V@YAXPEAX@Z` at `0x102035dda`
- `sqldk!??_V@YAXPEAX@Z` at `0x102036240`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020362fd`
- `sqldk!??_V@YAXPEAX@Z` at `0x102036591`
- `sqllang!?Set@CAutoExecuteAsContext@@QEAAXKKW4EPrincipalType@@W4EImpersonationScope@@HHPEAU_SignerSid@@KH@Z` at `0x1020356f4`
- `sqllang!?Set@CAutoExecuteAsContext@@QEAAXKKW4EPrincipalType@@W4EImpersonationScope@@HHPEAU_SignerSid@@KH@Z` at `0x1020356f4`
- `sqllang!?Restore@CAutoExecuteAsContext@@QEAAXXZ` at `0x10203624c`
- `sqllang!?Restore@CAutoExecuteAsContext@@QEAAXXZ` at `0x10203624c`

## string_xrefs

- `0x10203655d`: `Restore(%ls): PostRestoreReplicationFixup is complete\n`
- `0x10203645f`: `PostRestoreReplicationFixup is complete\n`
- `0x102035ff3`: `SynapseLink rationalization:`
- `0x102035f94`: `exec .dbo.sp_synapse_link_restoredb \n`
- `0x10203622b`: `Restore(%ls): PostRestoreReplicationFixup: SynapseLink cleanup is complete\n`
- `0x102036133`: `PostRestoreReplicationFixup: SynapseLink cleanup is complete\n`
- `0x102035db2`: `Restore(%ls): PostRestoreReplicationFixup: CDC cleanup is complete\n`
- `0x102035cca`: `PostRestoreReplicationFixup: CDC cleanup is complete\n`
- `0x102035f88`: `Restore(%ls): PostRestoreReplicationFixup: SynapseLink cleanup begins\n`
- `0x102035eac`: `PostRestoreReplicationFixup: SynapseLink cleanup begins\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall DBTABLE::PostRestoreReplicationFixup(DBTABLE *this)
{
  DBTABLE *v1; // r15
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 FCB; // rax
  __int64 v6; // rax
  struct CSessionTraceFlags *v7; // rcx
  unsigned int RestoreFlags; // r12d
  __int64 v9; // r14
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int16 **v13; // rax
  __int64 v14; // rax
  struct CSessionTraceFlags *v15; // rcx
  __int64 v16; // rdx
  struct CSessionTraceFlags *v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // r9
  wchar_t *v26; // rdi
  wchar_t *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  struct CSessionTraceFlags *v30; // rcx
  struct IExecSql *v31; // rdi
  __int64 v32; // rdx
  struct CSessionTraceFlags *v33; // rcx
  __int64 v34; // rbx
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rax
  struct CSessionTraceFlags *v40; // rcx
  __int64 v41; // rax
  struct CSessionTraceFlags *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  struct CSessionTraceFlags *v45; // rcx
  __int64 v46; // rdx
  struct CSessionTraceFlags *v47; // rcx
  __int64 v48; // rbx
  __int64 v49; // rax
  struct CSessionTraceFlags *v50; // rcx
  __int64 v51; // rax
  struct CSessionTraceFlags *v52; // rcx
  __int64 v53; // rbx
  __int64 v54; // rax
  __int64 v55; // rax
  struct CSessionTraceFlags *v56; // rcx
  __int64 v57; // rax
  struct CSessionTraceFlags *v58; // rcx
  __int64 v59; // rdx
  struct CSessionTraceFlags *v60; // rcx
  __int64 v61; // rdx
  struct CSessionTraceFlags *v62; // rcx
  void *v63; // rbx
  __int64 v64; // rax
  struct CSessionTraceFlags *v65; // rcx
  __int64 v66; // rax
  struct CSessionTraceFlags *v67; // rcx
  __int64 v68; // r9
  __int64 v69; // rbx
  struct Worker *v70; // rcx
  __int64 v71; // rax
  int v72; // eax
  __int16 **v73; // rax
  __int64 v74; // rax
  struct CSessionTraceFlags *v75; // rcx
  __int64 v76; // rax
  struct CSessionTraceFlags *v77; // rcx
  unsigned int v78; // ebx
  int (*v80)(int, int, int, int, char *); // [rsp+20h] [rbp-7108h]
  wchar_t *v81; // [rsp+28h] [rbp-7100h]
  struct CTypeInfo *v82; // [rsp+30h] [rbp-70F8h]
  struct IExecSql *ExecSql; // [rsp+50h] [rbp-70D8h]
  wchar_t v84[2]; // [rsp+58h] [rbp-70D0h] BYREF
  unsigned __int16 v85; // [rsp+5Ch] [rbp-70CCh]
  int v86; // [rsp+60h] [rbp-70C8h] BYREF
  int v87; // [rsp+64h] [rbp-70C4h] BYREF
  int v88; // [rsp+68h] [rbp-70C0h]
  int v89; // [rsp+70h] [rbp-70B8h]
  int v90; // [rsp+74h] [rbp-70B4h]
  wchar_t *v91; // [rsp+78h] [rbp-70B0h]
  wchar_t *v92; // [rsp+80h] [rbp-70A8h]
  __int64 v93; // [rsp+88h] [rbp-70A0h] BYREF
  int v94; // [rsp+90h] [rbp-7098h]
  wchar_t *v95[2]; // [rsp+98h] [rbp-7090h]
  __int64 v96; // [rsp+A8h] [rbp-7080h]
  __int64 v97; // [rsp+B0h] [rbp-7078h]
  DBTABLE *v98; // [rsp+C0h] [rbp-7068h]
  _QWORD v99[5]; // [rsp+C8h] [rbp-7060h] BYREF
  _QWORD v100[5]; // [rsp+F0h] [rbp-7038h] BYREF
  __int64 v101; // [rsp+118h] [rbp-7010h] BYREF
  int v102; // [rsp+120h] [rbp-7008h]
  __int128 v103; // [rsp+128h] [rbp-7000h]
  __int64 v104; // [rsp+138h] [rbp-6FF0h] BYREF
  int v105; // [rsp+140h] [rbp-6FE8h]
  __int128 v106; // [rsp+148h] [rbp-6FE0h]
  int v107; // [rsp+158h] [rbp-6FD0h]
  int v108; // [rsp+15Ch] [rbp-6FCCh]
  __int64 v109; // [rsp+160h] [rbp-6FC8h] BYREF
  int v110; // [rsp+168h] [rbp-6FC0h]
  __int128 v111; // [rsp+170h] [rbp-6FB8h]
  __int64 v112; // [rsp+180h] [rbp-6FA8h]
  struct IExecSql *v113; // [rsp+188h] [rbp-6FA0h]
  __int64 v114; // [rsp+190h] [rbp-6F98h]
  _BYTE v115[16]; // [rsp+198h] [rbp-6F90h] BYREF
  _BYTE v116[24]; // [rsp+1A8h] [rbp-6F80h] BYREF
  _BYTE v117[48]; // [rsp+1C0h] [rbp-6F68h] BYREF
  _BYTE v118[8]; // [rsp+1F0h] [rbp-6F38h] BYREF
  int v119; // [rsp+1F8h] [rbp-6F30h]
  int v120; // [rsp+200h] [rbp-6F28h]
  __int16 **v121; // [rsp+208h] [rbp-6F20h]
  char *v122; // [rsp+210h] [rbp-6F18h]
  __int64 v123; // [rsp+218h] [rbp-6F10h]
  __int16 *v124; // [rsp+220h] [rbp-6F08h] BYREF
  int v125; // [rsp+228h] [rbp-6F00h]
  int v126; // [rsp+22Ch] [rbp-6EFCh]
  char *v127; // [rsp+230h] [rbp-6EF8h]
  int v128; // [rsp+238h] [rbp-6EF0h]
  int v129; // [rsp+23Ch] [rbp-6EECh]
  __int64 v130; // [rsp+240h] [rbp-6EE8h]
  int v131; // [rsp+248h] [rbp-6EE0h]
  int v132; // [rsp+24Ch] [rbp-6EDCh]
  char v133; // [rsp+250h] [rbp-6ED8h] BYREF
  __int64 v134; // [rsp+440h] [rbp-6CE8h]
  __int64 v135; // [rsp+448h] [rbp-6CE0h]
  __int16 v136; // [rsp+450h] [rbp-6CD8h] BYREF
  _BYTE v137[8]; // [rsp+470h] [rbp-6CB8h] BYREF
  int v138; // [rsp+478h] [rbp-6CB0h]
  int v139; // [rsp+480h] [rbp-6CA8h]
  __int16 **v140; // [rsp+488h] [rbp-6CA0h]
  char *v141; // [rsp+490h] [rbp-6C98h]
  __int64 v142; // [rsp+498h] [rbp-6C90h]
  __int16 *v143; // [rsp+4A0h] [rbp-6C88h] BYREF
  int v144; // [rsp+4A8h] [rbp-6C80h]
  int v145; // [rsp+4ACh] [rbp-6C7Ch]
  char *v146; // [rsp+4B0h] [rbp-6C78h]
  int v147; // [rsp+4B8h] [rbp-6C70h]
  int v148; // [rsp+4BCh] [rbp-6C6Ch]
  __int64 v149; // [rsp+4C0h] [rbp-6C68h]
  int v150; // [rsp+4C8h] [rbp-6C60h]
  int v151; // [rsp+4CCh] [rbp-6C5Ch]
  char v152; // [rsp+4D0h] [rbp-6C58h] BYREF
  __int64 v153; // [rsp+6C0h] [rbp-6A68h]
  __int64 v154; // [rsp+6C8h] [rbp-6A60h]
  __int16 v155; // [rsp+6D0h] [rbp-6A58h] BYREF
  _BYTE v156[640]; // [rsp+6F0h] [rbp-6A38h] BYREF
  _BYTE v157[640]; // [rsp+970h] [rbp-67B8h] BYREF
  _BYTE v158[640]; // [rsp+BF0h] [rbp-6538h] BYREF
  _BYTE v159[640]; // [rsp+E70h] [rbp-62B8h] BYREF
  wchar_t Buffer[2048]; // [rsp+10F0h] [rbp-6038h] BYREF
  wchar_t v161[2048]; // [rsp+20F0h] [rbp-5038h] BYREF
  wchar_t v162[2048]; // [rsp+30F0h] [rbp-4038h] BYREF
  wchar_t v163[2048]; // [rsp+40F0h] [rbp-3038h] BYREF
  wchar_t v164[2048]; // [rsp+50F0h] [rbp-2038h] BYREF
  wchar_t v165[2048]; // [rsp+60F0h] [rbp-1038h] BYREF

  v112 = -2;
  v1 = this;
  v98 = this;
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  v93 = *(_QWORD *)(v3 + 1000);
  v94 = 0;
  *(_OWORD *)v95 = 0;
  v88 = 1;
  v4 = *((_QWORD *)v1 + 578);
  FCB = FileMgr::GetFCB(*(_QWORD *)(v4 + 1696), 2, 1);
  v97 = *(_QWORD *)(FCB + 422);
  v85 = *(_WORD *)(FCB + 430);
  *((_BYTE *)v1 + 684) &= ~0x10u;
  if ( (qword_10317ACFF & 0x2000000000LL) != 0 )
    return 1;
  v6 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset);
  if ( v6 )
  {
    v7 = **(struct CSessionTraceFlags ***)(v6 + 56);
    if ( v7 )
    {
      if ( CSessionTraceFlags::CheckSessionTraceInternal(v7, 0xC1Du) )
        return 1;
    }
  }
  RestoreFlags = RecoveryUnit::GetRestoreFlags((RecoveryUnit *)v4);
  v9 = -1;
  if ( (g_XeSqlMinPkg_enabledBitmap & 0x2000000) != 0 )
  {
    v119 = 196608;
    v120 = 0;
    v121 = &v124;
    v122 = &v133;
    v134 = 0;
    v123 = 0;
    v135 = 0;
    v124 = &v136;
    v125 = 18;
    v126 = 2;
    v130 = 0;
    v131 = 0;
    v132 = 3;
    v136 = 1;
    if ( v1 == (DBTABLE *)-936LL )
    {
      v11 = 0;
    }
    else
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_WORD *)v1 + v10 + 468) );
      v11 = 2 * v10;
    }
    v127 = (char *)v1 + 936;
    v128 = v11;
    v129 = 2;
    memset_0(Buffer, 0, sizeof(Buffer));
    swprintf_s(Buffer, 0x800u, L"PostRestoreReplicationFixup begins\n");
    v12 = -1;
    do
      ++v12;
    while ( Buffer[v12] );
    v13 = v121;
    v121[4] = (__int16 *)Buffer;
    *((_DWORD *)v13 + 10) = 2 * v12;
    *((_DWORD *)v13 + 11) = 3;
    XeSqlPkg::backup_restore_progress_trace::Publish((XeSqlPkg::backup_restore_progress_trace *)v118);
  }
  if ( (byte_10317ACF7 & 0x10) != 0
    || (v14 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset)) != 0
    && (v15 = **(struct CSessionTraceFlags ***)(v14 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v15, 0xBBCu)
    || (byte_10317ACF8 & 0x40) != 0
    || (v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset,
        *(_QWORD *)v16)
    && (v17 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v16 + 56LL)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v17, 0xBC6u) )
  {
    LogSystemMetadata(L"Restore(%ls): PostRestoreReplicationFixup begins\n", (char *)v1 + 936);
  }
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v117, 0, 0, 0, hdl_prntbackout, 0);
    v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v19 = *(_QWORD *)(v18 + 256);
    if ( !v19 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v19 = *(_QWORD *)(v18 + 256);
    }
    v104 = *(_QWORD *)(v19 + 1000);
    v105 = 0;
    v106 = 0;
    v20 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v21 = *(_QWORD *)(v20 + 256);
    if ( !v21 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v21 = *(_QWORD *)(v20 + 256);
    }
    ExecSql = CreateExecSql(*(struct IMemObj **)(v21 + 1000), 0);
    v113 = ExecSql;
    v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v23 = *(_QWORD *)(v22 + 256);
    if ( !v23 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v23 = *(_QWORD *)(v22 + 256);
    }
    v100[4] = *(_QWORD *)(v23 + 1000);
    v100[2] = &v104;
    v100[3] = ExecSql;
    v100[1] = v100;
    v100[0] = v100;
    v86 = 0;
    if ( !CAutoDb::FUse((CAutoDb *)&v86, *((unsigned __int16 *)v1 + 20), 0, 1, 1, 0) )
      ex_raise(31, 65, 25, 5);
    v89 = 0;
    v24 = 8LL * SystemThread_TlsIndex;
    v96 = *(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v24) + SystemThread_TlsOffset);
    v90 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                            + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v24)
                                            + 8LL)
                                + 104LL)
                    + 24LL);
    if ( *(_BYTE *)(v4 + 7378) )
    {
      v89 = 1;
      v25 = 8LL * SystemThread_TlsIndex;
      v96 = *(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v25) + SystemThread_TlsOffset);
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                        + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v25)
                                        + 8LL)
                            + 104LL)
                + 24LL) = 10000;
    }
    v84[0] = 0;
    v26 = v84;
    v91 = v84;
    v27 = v84;
    v92 = v84;
    if ( (RestoreFlags & 1) != 0 )
    {
      v26 = Src;
      v91 = Src;
      v27 = (wchar_t *)((char *)v1 + 936);
      v92 = (wchar_t *)((char *)v1 + 936);
    }
    BackupString::akaswprintf((BackupString *)&v93, L"if object_id('sys.sp_restoredbreplication') is not null\n");
    BackupString::swcatf((BackupString *)&v93, L"    exec .dbo.sp_restoredbreplication N'%s',", v26);
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    v114 = v28;
    ParamBuilder::AddQueryParameter(
      (ParamBuilder *)v100,
      (struct BackupString *)&v93,
      L"nvarchar",
      0xE7u,
      v28,
      v27,
      (const struct CTypeInfo *)&CTypeInfo::tiWString);
    LODWORD(v82) = v85;
    LODWORD(v81) = HIDWORD(v97);
    LODWORD(v80) = v97;
    BackupString::swcatf(
      (BackupString *)&v93,
      L",%d,%d, 0x%08lx%08lx%04lx\n",
      (RestoreFlags >> 5) & 1,
      (RestoreFlags >> 6) & 1,
      v80,
      v81,
      v82);
    if ( (byte_10317AD11 & 0x40) != 0
      || (v29 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset)) != 0
      && (v30 = **(struct CSessionTraceFlags ***)(v29 + 56)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v30, 0xC8Eu) )
    {
      BackupString::Dump((BackupString *)&v93, L"Replication rationalization:");
    }
    v87 = 0;
    CAutoExecuteAsContext::Set(&v87, 0, 1);
    v31 = ExecSql;
    (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 48LL))(ExecSql);
    (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)v31 + 56LL))(v31);
    ParamBuilder::BuildInputParametersForNonRpc((ParamBuilder *)v100);
    if ( (byte_10317ACFC & 0x20) == 0 )
    {
      v32 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( *(_QWORD *)v32
        && (v33 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v32 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v33, 0xBE5u) )
      {
        v31 = ExecSql;
      }
      else
      {
        v31 = ExecSql;
        (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 120LL))(ExecSql);
      }
    }
    v34 = (__int64)(v106 - *((_QWORD *)&v106 + 1)) >> 1;
    BackupString::swcatf((BackupString *)&v104, L"\n");
    BackupString::Append((BackupString *)&v104, (const struct BackupString *)&v93);
    if ( !(*(unsigned int (__fastcall **)(struct IExecSql *, _QWORD, _QWORD))(*(_QWORD *)v31 + 8LL))(
            v31,
            *((_QWORD *)&v106 + 1),
            (unsigned int)v34) )
      ex_raise(31, 65, 25, 3);
    if ( (*((_BYTE *)v1 + 48) & 0x40) == 0 )
    {
LABEL_102:
      if ( (*((_DWORD *)v1 + 12) & 0x800) == 0 )
      {
LABEL_144:
        CAutoExecuteAsContext::Restore((CAutoExecuteAsContext *)&v87);
        if ( v89 )
        {
          v68 = 8LL * SystemThread_TlsIndex;
          v97 = *(_QWORD *)(*(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v68) + SystemThread_TlsOffset);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                            + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v68)
                                            + 8LL)
                                + 104LL)
                    + 24LL) = v90;
          v31 = ExecSql;
        }
        if ( v86 )
        {
          v86 = 0;
          ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
        }
        ParamBuilder::~ParamBuilder((ParamBuilder *)v100);
        (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)v31 + 224LL))(v31, 1);
        if ( *((_QWORD *)&v106 + 1) )
          operator delete[](*((void **)&v106 + 1));
        ExcHandler::~ExcHandler((ExcHandler *)v117);
        goto LABEL_180;
      }
      v53 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v54 = *(_QWORD *)(v53 + 256);
      if ( !v54 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v54 = *(_QWORD *)(v53 + 256);
      }
      v109 = *(_QWORD *)(v54 + 1000);
      v110 = 0;
      v111 = 0;
      v91 = (wchar_t *)0x200000000000000LL;
      if ( (g_XeSqlMinPkg_enabledBitmap & 0x2000000) != 0 )
      {
        XeSqlPkg::backup_restore_progress_trace::backup_restore_progress_trace((XeSqlPkg::backup_restore_progress_trace *)v158);
        v158[608] = 1;
        v158[609] = 0;
        XeSqlPkg::xstore_io_throttling_storage_account_removed::Setstorage_account(
          (XeSqlPkg::xstore_io_throttling_storage_account_removed *)v158,
          (const wchar_t *const)v1 + 468);
        memset_0(v164, 0, sizeof(v164));
        swprintf_s(v164, 0x800u, L"PostRestoreReplicationFixup: SynapseLink cleanup begins\n");
        XeSqlPkg::backup_restore_progress_trace::Settrace_message((XeSqlPkg::backup_restore_progress_trace *)v158, v164);
        XeSqlPkg::backup_restore_progress_trace::Publish((XeSqlPkg::backup_restore_progress_trace *)v158);
      }
      if ( (byte_10317ACF7 & 0x10) != 0
        || (v55 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset)) != 0
        && (v56 = **(struct CSessionTraceFlags ***)(v55 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v56, 0xBBCu)
        || (byte_10317ACF8 & 0x40) != 0
        || (v57 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset)) != 0
        && (v58 = **(struct CSessionTraceFlags ***)(v57 + 56)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v58, 0xBC6u) )
      {
        LogSystemMetadata(L"Restore(%ls): PostRestoreReplicationFixup: SynapseLink cleanup begins\n", (char *)v1 + 936);
      }
      BackupString::akaswprintf((BackupString *)&v93, L"exec .dbo.sp_synapse_link_restoredb \n");
      if ( (byte_10317AD11 & 0x40) != 0
        || (v59 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset,
            *(_QWORD *)v59)
        && (v60 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v59 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v60, 0xC8Eu) )
      {
        BackupString::Dump((BackupString *)&v93, L"SynapseLink rationalization:");
      }
      v31 = ExecSql;
      (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 32LL))(ExecSql);
      (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)v31 + 48LL))(v31);
      (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)v31 + 56LL))(v31);
      if ( (byte_10317ACFC & 0x20) == 0 )
      {
        v61 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( *(_QWORD *)v61
          && (v62 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v61 + 56LL)) != 0
          && CSessionTraceFlags::CheckSessionTraceInternal(v62, 0xBE5u) )
        {
          v31 = ExecSql;
        }
        else
        {
          v31 = ExecSql;
          (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 120LL))(ExecSql);
        }
      }
      BackupString::swcatf((BackupString *)&v109, v95[1]);
      v63 = (void *)*((_QWORD *)&v111 + 1);
      if ( !(*(unsigned int (__fastcall **)(struct IExecSql *, _QWORD, _QWORD))(*(_QWORD *)v31 + 8LL))(
              v31,
              *((_QWORD *)&v111 + 1),
              0) )
        ex_raise(31, 65, 25, 4);
      v96 = 0x200000000000000LL;
      if ( (g_XeSqlMinPkg_enabledBitmap & 0x2000000) != 0 )
      {
        XeSqlPkg::backup_restore_progress_trace::backup_restore_progress_trace((XeSqlPkg::backup_restore_progress_trace *)v159);
        v159[608] = 1;
        v159[609] = 0;
        XeSqlPkg::xstore_io_throttling_storage_account_removed::Setstorage_account(
          (XeSqlPkg::xstore_io_throttling_storage_account_removed *)v159,
          (const wchar_t *const)v1 + 468);
        memset_0(v165, 0, sizeof(v165));
        swprintf_s(v165, 0x800u, L"PostRestoreReplicationFixup: SynapseLink cleanup is complete\n");
        XeSqlPkg::backup_restore_progress_trace::Settrace_message((XeSqlPkg::backup_restore_progress_trace *)v159, v165);
        XeSqlPkg::backup_restore_progress_trace::Publish((XeSqlPkg::backup_restore_progress_trace *)v159);
      }
      if ( (byte_10317ACF7 & 0x10) == 0 )
      {
        v64 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset);
        if ( (!v64
           || (v65 = **(struct CSessionTraceFlags ***)(v64 + 56)) == 0
           || !CSessionTraceFlags::CheckSessionTraceInternal(v65, 0xBBCu))
          && (byte_10317ACF8 & 0x40) == 0 )
        {
          v66 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset);
          if ( !v66
            || (v67 = **(struct CSessionTraceFlags ***)(v66 + 56)) == 0
            || !CSessionTraceFlags::CheckSessionTraceInternal(v67, 0xBC6u) )
          {
            v63 = (void *)*((_QWORD *)&v111 + 1);
            v31 = ExecSql;
            goto LABEL_142;
          }
        }
        v63 = (void *)*((_QWORD *)&v111 + 1);
        v31 = ExecSql;
      }
      LogSystemMetadata(
        L"Restore(%ls): PostRestoreReplicationFixup: SynapseLink cleanup is complete\n",
        (char *)v1 + 936);
LABEL_142:
      if ( v63 )
        operator delete[](v63);
      goto LABEL_144;
    }
    v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v36 = *(_QWORD *)(v35 + 256);
    if ( !v36 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v36 = *(_QWORD *)(v35 + 256);
    }
    v101 = *(_QWORD *)(v36 + 1000);
    v102 = 0;
    v103 = 0;
    v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v38 = *(_QWORD *)(v37 + 256);
    if ( !v38 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v38 = *(_QWORD *)(v37 + 256);
    }
    v99[4] = *(_QWORD *)(v38 + 1000);
    v99[2] = &v101;
    v31 = ExecSql;
    v99[3] = ExecSql;
    v99[1] = v99;
    v99[0] = v99;
    v107 = 0;
    v108 = 0x2000000;
    if ( (g_XeSqlMinPkg_enabledBitmap & 0x2000000) != 0 )
    {
      XeSqlPkg::backup_restore_progress_trace::backup_restore_progress_trace((XeSqlPkg::backup_restore_progress_trace *)v156);
      v156[608] = 1;
      v156[609] = 0;
      XeSqlPkg::xstore_io_throttling_storage_account_removed::Setstorage_account(
        (XeSqlPkg::xstore_io_throttling_storage_account_removed *)v156,
        (const wchar_t *const)v1 + 468);
      memset_0(v162, 0, sizeof(v162));
      swprintf_s(v162, 0x800u, L"PostRestoreReplicationFixup: CDC cleanup begins\n");
      XeSqlPkg::backup_restore_progress_trace::Settrace_message((XeSqlPkg::backup_restore_progress_trace *)v156, v162);
      XeSqlPkg::backup_restore_progress_trace::Publish((XeSqlPkg::backup_restore_progress_trace *)v156);
    }
    if ( (byte_10317ACF7 & 0x10) == 0 )
    {
      v39 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset);
      if ( (!v39
         || (v40 = **(struct CSessionTraceFlags ***)(v39 + 56)) == 0
         || !CSessionTraceFlags::CheckSessionTraceInternal(v40, 0xBBCu))
        && (byte_10317ACF8 & 0x40) == 0 )
      {
        v41 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset);
        if ( !v41
          || (v42 = **(struct CSessionTraceFlags ***)(v41 + 56)) == 0
          || !CSessionTraceFlags::CheckSessionTraceInternal(v42, 0xBC6u) )
        {
          v31 = ExecSql;
LABEL_70:
          BackupString::akaswprintf((BackupString *)&v93, L"if object_id('sys.sp_cdc_restoredb') is not null\n");
          BackupString::swcatf((BackupString *)&v93, L"    exec .dbo.sp_cdc_restoredb N'%s',", v91);
          v43 = -1;
          do
            ++v43;
          while ( v92[v43] );
          v97 = v43;
          ParamBuilder::AddQueryParameter(
            (ParamBuilder *)v99,
            (struct BackupString *)&v93,
            L"nvarchar",
            0xE7u,
            v43,
            v92,
            (const struct CTypeInfo *)&CTypeInfo::tiWString);
          BackupString::swcatf((BackupString *)&v93, L",%d\n", (RestoreFlags >> 10) & 1);
          if ( (byte_10317AD11 & 0x40) == 0 )
          {
            v44 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( !*(_QWORD *)v44
              || (v45 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v44 + 56LL)) == 0
              || !CSessionTraceFlags::CheckSessionTraceInternal(v45, 0xC8Eu) )
            {
              v31 = ExecSql;
LABEL_78:
              (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)v31 + 32LL))(v31);
              (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)v31 + 48LL))(v31);
              (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)v31 + 56LL))(v31);
              ParamBuilder::BuildInputParametersForNonRpc((ParamBuilder *)v99);
              if ( (byte_10317ACFC & 0x20) == 0 )
              {
                v46 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset;
                if ( *(_QWORD *)v46
                  && (v47 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v46 + 56LL)) != 0
                  && CSessionTraceFlags::CheckSessionTraceInternal(v47, 0xBE5u) )
                {
                  v31 = ExecSql;
                }
                else
                {
                  v31 = ExecSql;
                  (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 120LL))(ExecSql);
                }
              }
              v48 = (__int64)(v103 - *((_QWORD *)&v103 + 1)) >> 1;
              BackupString::swcatf((BackupString *)&v101, L"\n");
              BackupString::Append((BackupString *)&v101, (const struct BackupString *)&v93);
              if ( !(*(unsigned int (__fastcall **)(struct IExecSql *, _QWORD, _QWORD))(*(_QWORD *)v31 + 8LL))(
                      v31,
                      *((_QWORD *)&v103 + 1),
                      (unsigned int)v48) )
                ex_raise(31, 65, 25, 3);
              v92 = (wchar_t *)0x200000000000000LL;
              if ( (g_XeSqlMinPkg_enabledBitmap & 0x2000000) != 0 )
              {
                XeSqlPkg::backup_restore_progress_trace::backup_restore_progress_trace((XeSqlPkg::backup_restore_progress_trace *)v157);
                v157[608] = 1;
                v157[609] = 0;
                XeSqlPkg::xstore_io_throttling_storage_account_removed::Setstorage_account(
                  (XeSqlPkg::xstore_io_throttling_storage_account_removed *)v157,
                  (const wchar_t *const)v1 + 468);
                memset_0(v163, 0, sizeof(v163));
                swprintf_s(v163, 0x800u, L"PostRestoreReplicationFixup: CDC cleanup is complete\n");
                XeSqlPkg::backup_restore_progress_trace::Settrace_message(
                  (XeSqlPkg::backup_restore_progress_trace *)v157,
                  v163);
                XeSqlPkg::backup_restore_progress_trace::Publish((XeSqlPkg::backup_restore_progress_trace *)v157);
              }
              if ( (byte_10317ACF7 & 0x10) == 0 )
              {
                v49 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                + SystemThread_TlsOffset);
                if ( (!v49
                   || (v50 = **(struct CSessionTraceFlags ***)(v49 + 56)) == 0
                   || !CSessionTraceFlags::CheckSessionTraceInternal(v50, 0xBBCu))
                  && (byte_10317ACF8 & 0x40) == 0 )
                {
                  v51 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                  + SystemThread_TlsOffset);
                  if ( !v51
                    || (v52 = **(struct CSessionTraceFlags ***)(v51 + 56)) == 0
                    || !CSessionTraceFlags::CheckSessionTraceInternal(v52, 0xBC6u) )
                  {
                    v31 = ExecSql;
                    goto LABEL_100;
                  }
                }
                v31 = ExecSql;
              }
              LogSystemMetadata(
                L"Restore(%ls): PostRestoreReplicationFixup: CDC cleanup is complete\n",
                (char *)v1 + 936);
LABEL_100:
              ParamBuilder::~ParamBuilder((ParamBuilder *)v99);
              if ( *((_QWORD *)&v103 + 1) )
                operator delete[](*((void **)&v103 + 1));
              goto LABEL_102;
            }
            v31 = ExecSql;
          }
          BackupString::Dump((BackupString *)&v93, L"CDC rationalization:");
          goto LABEL_78;
        }
      }
      v31 = ExecSql;
    }
    LogSystemMetadata(L"Restore(%ls): PostRestoreReplicationFixup: CDC cleanup begins\n", (char *)v1 + 936);
    goto LABEL_70;
  }
  catch ( SQLError v116 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v115, (const struct SQLError *)v116);
      v88 = 0;
      BackupReportEvent(3, 3165, 16, 1, (char *)v98 + 936);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v115);
    }
    catch ( ShortStackException )
    {
    }
    v9 = -1;
    v1 = v98;
  }
LABEL_180:
  v69 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v70 = *(struct Worker **)(v69 + 256);
  if ( !v70 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v70 = *(struct Worker **)(v69 + 256);
  }
  if ( *((_DWORD *)v70 + 139) )
    ExceptionPostCatchActions(v70);
  if ( (g_XeSqlMinPkg_enabledBitmap & 0x2000000) != 0 )
  {
    v138 = 196608;
    v139 = 0;
    v140 = &v143;
    v141 = &v152;
    v153 = 0;
    v142 = 0;
    v154 = 0;
    v143 = &v155;
    v144 = 18;
    v145 = 2;
    v149 = 0;
    v150 = 0;
    v151 = 3;
    v155 = 1;
    if ( v1 == (DBTABLE *)-936LL )
    {
      v72 = 0;
    }
    else
    {
      v71 = -1;
      do
        ++v71;
      while ( *((_WORD *)v1 + v71 + 468) );
      v72 = 2 * v71;
    }
    v146 = (char *)v1 + 936;
    v147 = v72;
    v148 = 2;
    memset_0(v161, 0, sizeof(v161));
    swprintf_s(v161, 0x800u, L"PostRestoreReplicationFixup is complete\n");
    do
      ++v9;
    while ( v161[v9] );
    v73 = v140;
    v140[4] = (__int16 *)v161;
    *((_DWORD *)v73 + 10) = 2 * v9;
    *((_DWORD *)v73 + 11) = 3;
    XeSqlPkg::backup_restore_progress_trace::Publish((XeSqlPkg::backup_restore_progress_trace *)v137);
  }
  if ( (byte_10317ACF7 & 0x10) != 0
    || (v74 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset)) != 0
    && (v75 = **(struct CSessionTraceFlags ***)(v74 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v75, 0xBBCu)
    || (byte_10317ACF8 & 0x40) != 0
    || (v76 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset)) != 0
    && (v77 = **(struct CSessionTraceFlags ***)(v76 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v77, 0xBC6u) )
  {
    LogSystemMetadata(L"Restore(%ls): PostRestoreReplicationFixup is complete\n", (char *)v1 + 936);
  }
  *((_BYTE *)v1 + 684) &= ~0x10u;
  v78 = v88;
  *((_BYTE *)v1 + 684) |= 16 * (v88 == 0);
  if ( v95[1] )
    operator delete[](v95[1]);
  return v78;
}

```

## disassembly

```asm
0x102034f90  push    rdi
0x102034f92  push    r12
0x102034f94  push    r13
0x102034f96  push    r14
0x102034f98  push    r15
0x102034f9a  mov     eax, 7100h
0x102034f9f  call    _alloca_probe
0x102034fa4  sub     rsp, rax
0x102034fa7  mov     [rsp+7128h+var_6FA8], 0FFFFFFFFFFFFFFFEh
0x102034fb3  mov     [rsp+7128h+arg_8], rbx
0x102034fbb  mov     [rsp+7128h+arg_10], rsi
0x102034fc3  mov     rax, cs:__security_cookie
0x102034fca  xor     rax, rsp
0x102034fcd  mov     [rsp+7128h+var_38], rax
0x102034fd5  mov     r15, rcx
0x102034fd8  mov     [rsp+7128h+var_7068], rcx
0x102034fe0  mov     r8, gs:58h
0x102034fe9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102034ff0  mov     edx, [rax]
0x102034ff2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102034ff9  mov     ebx, [rax]
0x102034ffb  add     rbx, [r8+rdx*8]
0x102034fff  mov     rax, [rbx+100h]
0x102035006  test    rax, rax
0x102035009  jnz     short loc_10203501A
0x10203500b  xor     ecx, ecx
0x10203500d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x102035013  mov     rax, [rbx+100h]
0x10203501a  mov     rax, [rax+3E8h]
0x102035021  mov     [rsp+7128h+var_70A0], rax
0x102035029  xor     esi, esi
0x10203502b  mov     [rsp+7128h+var_7098], esi
0x102035032  xorps   xmm0, xmm0
0x102035035  movdqu  xmmword ptr [rsp+7128h+var_7090], xmm0
0x10203503e  mov     [rsp+7128h+var_70C0], 1
0x102035046  mov     rdi, [r15+1210h]
0x10203504d  lea     r8d, [rsi+1]
0x102035051  mov     r13d, 2
0x102035057  mov     edx, r13d
0x10203505a  mov     rcx, [rdi+6A0h]
0x102035061  call    ?GetFCB@FileMgr@@QEBAPEAVFCB@@JW4LookupFailureMode@@@Z; FileMgr::GetFCB(long,LookupFailureMode)
0x102035066  movsd   xmm0, qword ptr [rax+1A6h]
0x10203506e  movsd   [rsp+7128h+var_7078], xmm0
0x102035077  movzx   eax, word ptr [rax+1AEh]
0x10203507e  mov     [rsp+7128h+var_70CC], ax
0x102035083  and     byte ptr [r15+2ACh], 0EFh
0x10203508b  test    byte ptr cs:qword_10317ACFF+4, 20h
0x102035092  jnz     loc_10203659B
0x102035098  mov     r8, gs:58h
0x1020350a1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020350a8  mov     ecx, [rax]
0x1020350aa  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020350b1  mov     edx, [rax]
0x1020350b3  add     rdx, [r8+rcx*8]
0x1020350b7  mov     rax, [rdx]
0x1020350ba  test    rax, rax
0x1020350bd  jz      short loc_1020350DE
0x1020350bf  mov     rax, [rax+38h]
0x1020350c3  mov     rcx, [rax]
0x1020350c6  test    rcx, rcx
0x1020350c9  jz      short loc_1020350DE
0x1020350cb  mov     edx, 0C1Dh
0x1020350d0  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1020350d6  test    eax, eax
0x1020350d8  jnz     loc_10203659B
0x1020350de  mov     rcx, rdi; this
0x1020350e1  call    ?GetRestoreFlags@RecoveryUnit@@QEAAGXZ; RecoveryUnit::GetRestoreFlags(void)
0x1020350e6  movzx   r12d, ax
0x1020350ea  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1020350f1  test    cs:?g_XeSqlMinPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FBI@@@@@A, 2000000h; XBitmap<StaticStorage<1304>> g_XeSqlMinPkg_enabledBitmap
0x1020350fb  jz      loc_102035238
0x102035101  mov     [rsp+7128h+var_6F30], 30000h
0x10203510c  mov     [rsp+7128h+var_6F28], esi
0x102035113  lea     rax, [rsp+7128h+var_6F08]
0x10203511b  mov     [rsp+7128h+var_6F20], rax
0x102035123  lea     rax, [rsp+7128h+var_6ED8]
0x10203512b  mov     [rsp+7128h+var_6F18], rax
0x102035133  mov     [rsp+7128h+var_6CE8], rsi
0x10203513b  mov     [rsp+7128h+var_6F10], rsi
0x102035143  mov     [rsp+7128h+var_6CE0], rsi
0x10203514b  lea     rax, [rsp+7128h+var_6CD8]
0x102035153  mov     [rsp+7128h+var_6F08], rax
0x10203515b  mov     [rsp+7128h+var_6F00], 12h
0x102035166  mov     [rsp+7128h+var_6EFC], r13d
0x10203516e  mov     [rsp+7128h+var_6EE8], rsi
0x102035176  mov     [rsp+7128h+var_6EE0], esi
0x10203517d  mov     [rsp+7128h+var_6EDC], 3
0x102035188  mov     [rsp+7128h+var_6CD8], 1
0x102035192  lea     rcx, [r15+3A8h]
0x102035199  test    rcx, rcx
0x10203519c  jz      short loc_1020351AF
0x10203519e  mov     rax, r14
0x1020351a1  inc     rax
0x1020351a4  cmp     word ptr [rcx+rax*2], 0
0x1020351a9  jnz     short loc_1020351A1
0x1020351ab  add     eax, eax
0x1020351ad  jmp     short loc_1020351B1
0x1020351af  mov     eax, esi
0x1020351b1  mov     [rsp+7128h+var_6EF8], rcx
0x1020351b9  mov     [rsp+7128h+var_6EF0], eax
0x1020351c0  mov     [rsp+7128h+var_6EEC], r13d
0x1020351c8  xor     edx, edx; Val
0x1020351ca  mov     r8d, 1000h; Size
0x1020351d0  lea     rcx, [rsp+7128h+Buffer]; void *
0x1020351d8  call    memset_0
0x1020351dd  lea     r8, aPostrestorerep_1; "PostRestoreReplicationFixup begins\n"
0x1020351e4  mov     edx, 800h; BufferCount
0x1020351e9  lea     rcx, [rsp+7128h+Buffer]; Buffer
0x1020351f1  call    swprintf_s
0x1020351f6  lea     rax, [rsp+7128h+Buffer]
0x1020351fe  mov     rcx, r14
0x102035201  inc     rcx
0x102035204  cmp     word ptr [rax+rcx*2], 0
0x102035209  jnz     short loc_102035201
0x10203520b  add     ecx, ecx
0x10203520d  mov     rax, [rsp+7128h+var_6F20]
0x102035215  lea     rdx, [rsp+7128h+Buffer]
0x10203521d  mov     [rax+20h], rdx
0x102035221  mov     [rax+28h], ecx
0x102035224  mov     dword ptr [rax+2Ch], 3
0x10203522b  lea     rcx, [rsp+7128h+var_6F38]; this
0x102035233  call    ?Publish@backup_restore_progress_trace@XeSqlPkg@@QEAAXXZ; XeSqlPkg::backup_restore_progress_trace::Publish(void)
0x102035238  test    cs:byte_10317ACF7, 10h
0x10203523f  jnz     loc_1020352D2
0x102035245  mov     r8, gs:58h
0x10203524e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102035255  mov     ecx, [rax]
0x102035257  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10203525e  mov     edx, [rax]
0x102035260  add     rdx, [r8+rcx*8]
0x102035264  mov     rax, [rdx]
0x102035267  test    rax, rax
0x10203526a  jz      short loc_102035287
0x10203526c  mov     rax, [rax+38h]
0x102035270  mov     rcx, [rax]
0x102035273  test    rcx, rcx
0x102035276  jz      short loc_102035287
0x102035278  mov     edx, 0BBCh
0x10203527d  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x102035283  test    eax, eax
0x102035285  jnz     short loc_1020352D2
0x102035287  test    cs:byte_10317ACF8, 40h
0x10203528e  jnz     short loc_1020352D2
0x102035290  mov     r8, gs:58h
0x102035299  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020352a0  mov     ecx, [rax]
0x1020352a2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020352a9  mov     edx, [rax]
0x1020352ab  add     rdx, [r8+rcx*8]
0x1020352af  mov     rax, [rdx]
0x1020352b2  test    rax, rax
0x1020352b5  jz      short loc_1020352E6
0x1020352b7  mov     rax, [rax+38h]
0x1020352bb  mov     rcx, [rax]
0x1020352be  test    rcx, rcx
0x1020352c1  jz      short loc_1020352E6
0x1020352c3  mov     edx, 0BC6h
0x1020352c8  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1020352ce  test    eax, eax
0x1020352d0  jz      short loc_1020352E6
0x1020352d2  lea     rdx, [r15+3A8h]
0x1020352d9  lea     rcx, aRestoreLsPostr_3; "Restore(%ls): PostRestoreReplicationFix"...
0x1020352e0  call    ?LogSystemMetadata@@YAXPEB_WZZ; LogSystemMetadata(wchar_t const *,...)
0x1020352e5  nop
0x1020352e6  xor     edx, edx; unsigned __int16
0x1020352e8  mov     [rsp+7128h+var_7100], rsi; struct Worker *
0x1020352ed  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x1020352f4  mov     [rsp+7128h+var_7108], rax; int (*)(int, int, int, int, char *)
0x1020352f9  xor     r9d, r9d; unsigned __int8
0x1020352fc  xor     r8d, r8d; unsigned __int8
0x1020352ff  lea     rcx, [rsp+7128h+var_6F68]; this
0x102035307  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10203530c  nop
0x10203530d  mov     rdx, gs:58h
0x102035316  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10203531d  mov     ecx, [rax]
0x10203531f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102035326  mov     ebx, [rax]
0x102035328  add     rbx, [rdx+rcx*8]
0x10203532c  mov     rax, [rbx+100h]
0x102035333  test    rax, rax
0x102035336  jnz     short loc_102035347
0x102035338  xor     ecx, ecx
0x10203533a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x102035340  mov     rax, [rbx+100h]
0x102035347  mov     rax, [rax+3E8h]
0x10203534e  mov     [rsp+7128h+var_6FF0], rax
0x102035356  mov     [rsp+7128h+var_6FE8], esi
0x10203535d  xorps   xmm0, xmm0
0x102035360  movdqu  [rsp+7128h+var_6FE0], xmm0
0x102035369  mov     rdx, gs:58h
0x102035372  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102035379  mov     ecx, [rax]
0x10203537b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102035382  mov     ebx, [rax]
0x102035384  add     rbx, [rdx+rcx*8]
0x102035388  mov     rcx, [rbx+100h]
0x10203538f  test    rcx, rcx
0x102035392  jnz     short loc_1020353A1
0x102035394  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10203539a  mov     rcx, [rbx+100h]
0x1020353a1  xor     edx, edx
0x1020353a3  mov     rcx, [rcx+3E8h]
0x1020353aa  call    cs:__imp_?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z; CreateExecSql(IMemObj *,ICallerParse *)
0x1020353b0  mov     [rsp+7128h+var_70D8], rax
0x1020353b5  mov     [rsp+7128h+var_6FA0], rax
0x1020353bd  mov     rdx, gs:58h
0x1020353c6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020353cd  mov     ecx, [rax]
0x1020353cf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020353d6  mov     ebx, [rax]
0x1020353d8  add     rbx, [rdx+rcx*8]
0x1020353dc  mov     rax, [rbx+100h]
0x1020353e3  test    rax, rax
0x1020353e6  jnz     short loc_1020353F7
0x1020353e8  xor     ecx, ecx
0x1020353ea  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1020353f0  mov     rax, [rbx+100h]
0x1020353f7  mov     rax, [rax+3E8h]
0x1020353fe  xorps   xmm0, xmm0
0x102035401  movdqu  [rsp+7128h+var_7038], xmm0
0x10203540a  lea     rcx, [rsp+7128h+var_7038]
0x102035412  mov     qword ptr [rsp+7128h+var_7038+8], rcx
0x10203541a  lea     rcx, [rsp+7128h+var_7038]
0x102035422  mov     qword ptr [rsp+7128h+var_7038], rcx
0x10203542a  mov     [rsp+7128h+var_7018], rax
0x102035432  lea     rax, [rsp+7128h+var_6FF0]
0x10203543a  mov     [rsp+7128h+var_7028], rax
0x102035442  mov     rax, [rsp+7128h+var_70D8]
0x102035447  mov     [rsp+7128h+var_7020], rax
0x10203544f  lea     rax, [rsp+7128h+var_7038]
0x102035457  mov     qword ptr [rsp+7128h+var_7038+8], rax
0x10203545f  lea     rax, [rsp+7128h+var_7038]
0x102035467  mov     qword ptr [rsp+7128h+var_7038], rax
0x10203546f  mov     [rsp+7128h+var_70C8], esi
0x102035473  movzx   edx, word ptr [r15+28h]; unsigned int
0x102035478  mov     dword ptr [rsp+7128h+var_7100], esi; unsigned int
0x10203547c  mov     byte ptr [rsp+7128h+var_7108], 1; bool
0x102035481  mov     r9b, 1; bool
0x102035484  xor     r8d, r8d; struct BaseXact *
0x102035487  lea     rcx, [rsp+7128h+var_70C8]; this
0x10203548c  call    ?FUse@CAutoDb@@QEAA_NKPEAVBaseXact@@_N1K@Z; CAutoDb::FUse(ulong,BaseXact *,bool,bool,ulong)
0x102035491  test    al, al
0x102035493  jnz     short loc_1020354AB
0x102035495  mov     edx, 41h ; 'A'
0x10203549a  lea     ecx, [rdx-22h]
0x10203549d  lea     r9d, [rdx-3Ch]
0x1020354a1  lea     r8d, [rdx-28h]
0x1020354a5  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1020354ab  mov     [rsp+7128h+var_70B8], esi
0x1020354af  mov     rdx, gs:58h
0x1020354b8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020354bf  mov     ecx, [rax]
0x1020354c1  lea     r9, ds:0[rcx*8]
0x1020354c9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020354d0  mov     r8d, [rax]
0x1020354d3  mov     rax, [r9+rdx]
0x1020354d7  mov     rcx, [rax+r8]
0x1020354db  mov     [rsp+7128h+var_7080], rcx
0x1020354e3  mov     rax, gs:58h
0x1020354ec  mov     rax, [r9+rax]
0x1020354f0  mov     rcx, [r8+rax+8]
0x1020354f5  mov     rax, [rcx+68h]
0x1020354f9  mov     ecx, [rax+18h]
0x1020354fc  mov     [rsp+7128h+var_70B4], ecx
0x102035500  cmp     byte ptr [rdi+1CD2h], 0
0x102035507  jz      short loc_102035562
0x102035509  mov     [rsp+7128h+var_70B8], 1
0x102035511  mov     rdx, gs:58h
0x10203551a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x102035521  mov     ecx, [rax]
0x102035523  lea     r9, ds:0[rcx*8]
0x10203552b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102035532  mov     r8d, [rax]
0x102035535  mov     rax, [r9+rdx]
0x102035539  mov     rcx, [rax+r8]
0x10203553d  mov     [rsp+7128h+var_7080], rcx
0x102035545  mov     rax, gs:58h
0x10203554e  mov     rax, [r9+rax]
0x102035552  mov     rcx, [r8+rax+8]
0x102035557  mov     rax, [rcx+68h]
0x10203555b  mov     dword ptr [rax+18h], 2710h
0x102035562  mov     [rsp+7128h+var_70D0], si
0x102035567  lea     rdi, [rsp+7128h+var_70D0]
0x10203556c  mov     [rsp+7128h+var_70B0], rdi
0x102035571  lea     rbx, [rsp+7128h+var_70D0]
0x102035576  mov     [rsp+7128h+var_70A8], rbx
0x10203557e  test    r12b, 1
0x102035582  jz      short loc_10203559F
0x102035584  mov     rdi, cs:Src
0x10203558b  mov     [rsp+7128h+var_70B0], rdi
0x102035590  lea     rbx, [r15+3A8h]
0x102035597  mov     [rsp+7128h+var_70A8], rbx
0x10203559f  lea     rdx, aIfObjectIdSysS_0; "if object_id('sys.sp_restoredbreplicati"...
0x1020355a6  lea     rcx, [rsp+7128h+var_70A0]; this
0x1020355ae  call    ?akaswprintf@BackupString@@QEAAKPEB_WZZ; BackupString::akaswprintf(wchar_t const *,...)
0x1020355b3  mov     r8, rdi
0x1020355b6  lea     rdx, aExecDboSpResto; "    exec .dbo.sp_restoredbreplication N"...
0x1020355bd  lea     rcx, [rsp+7128h+var_70A0]; this
0x1020355c5  call    ?swcatf@BackupString@@QEAAKPEB_WZZ; BackupString::swcatf(wchar_t const *,...)
  ... truncated ...
```
