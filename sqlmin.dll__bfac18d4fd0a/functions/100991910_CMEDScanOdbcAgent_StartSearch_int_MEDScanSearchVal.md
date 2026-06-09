# CMEDScanOdbcAgent::StartSearch(int,MEDScanSearchVal *)

- ea: `0x100991910`
- end: `0x100992e4f`
- name: `?StartSearch@CMEDScanOdbcAgent@@UEAAXHPEAUMEDScanSearchVal@@@Z`
- size: `5439`
- prototype: `void __fastcall(CMEDScanOdbcAgent *__hidden this, int, struct MEDScanSearchVal *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1004025c0`
- `0x10042d300`
- `0x10045e0a0`
- `0x100990f70`
- `0x100991090`
- `0x100991910`

## import_xrefs

- `ODBC32!__imp_SQLAllocHandle` at `0x100991aac`
- `ODBC32!__imp_SQLAllocHandle` at `0x100991aac`
- `ODBC32!__imp_SQLExecDirectW` at `0x100992da9`
- `ODBC32!__imp_SQLExecDirectW` at `0x100992da9`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100991a1a`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100992d17`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100991a1a`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100992d17`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991980`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991b91`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991caf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991d94`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991e96`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991f91`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992058`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992161`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992252`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992323`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1009923f4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1009924b6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10099258b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1009926a8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992936`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992a5f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992b40`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992c2e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991980`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991b91`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991caf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991d94`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991e96`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100991f91`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992058`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992161`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992252`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992323`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1009923f4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1009924b6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10099258b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1009926a8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992936`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992a5f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992b40`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100992c2e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10099284b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10099284b`
- `sqldk!SystemThread_TlsIndex` at `0x1009919d9`
- `sqldk!SystemThread_TlsIndex` at `0x100991a2f`
- `sqldk!SystemThread_TlsIndex` at `0x100991b42`
- `sqldk!SystemThread_TlsIndex` at `0x100991c54`
- `sqldk!SystemThread_TlsIndex` at `0x100991d32`
- `sqldk!SystemThread_TlsIndex` at `0x100991e3b`
- `sqldk!SystemThread_TlsIndex` at `0x100991f2f`
- `sqldk!SystemThread_TlsIndex` at `0x100991ff6`
- `sqldk!SystemThread_TlsIndex` at `0x1009920ff`
- `sqldk!SystemThread_TlsIndex` at `0x1009921f0`
- `sqldk!SystemThread_TlsIndex` at `0x1009922c1`
- `sqldk!SystemThread_TlsIndex` at `0x100992392`
- `sqldk!SystemThread_TlsIndex` at `0x100992454`
- `sqldk!SystemThread_TlsIndex` at `0x100992530`
- `sqldk!SystemThread_TlsIndex` at `0x100992645`
- `sqldk!SystemThread_TlsIndex` at `0x1009928d4`
- `sqldk!SystemThread_TlsIndex` at `0x1009929fd`
- `sqldk!SystemThread_TlsIndex` at `0x100992ade`
- `sqldk!SystemThread_TlsIndex` at `0x100992bcc`
- `sqldk!SystemThread_TlsIndex` at `0x100992cd6`
- `sqldk!SystemThread_TlsIndex` at `0x100992d2c`
- `sqldk!SystemThread_TlsOffset` at `0x1009919e2`
- `sqldk!SystemThread_TlsOffset` at `0x100991a38`
- `sqldk!SystemThread_TlsOffset` at `0x100991b4b`
- `sqldk!SystemThread_TlsOffset` at `0x100991c5d`
- `sqldk!SystemThread_TlsOffset` at `0x100991d3b`
- `sqldk!SystemThread_TlsOffset` at `0x100991e44`
- `sqldk!SystemThread_TlsOffset` at `0x100991f38`
- `sqldk!SystemThread_TlsOffset` at `0x100991fff`
- `sqldk!SystemThread_TlsOffset` at `0x100992108`
- `sqldk!SystemThread_TlsOffset` at `0x1009921f9`
- `sqldk!SystemThread_TlsOffset` at `0x1009922ca`
- `sqldk!SystemThread_TlsOffset` at `0x10099239b`
- `sqldk!SystemThread_TlsOffset` at `0x10099245d`
- `sqldk!SystemThread_TlsOffset` at `0x100992539`
- `sqldk!SystemThread_TlsOffset` at `0x10099264e`
- `sqldk!SystemThread_TlsOffset` at `0x1009928dd`
- `sqldk!SystemThread_TlsOffset` at `0x100992a06`
- `sqldk!SystemThread_TlsOffset` at `0x100992ae7`
- `sqldk!SystemThread_TlsOffset` at `0x100992bd5`
- `sqldk!SystemThread_TlsOffset` at `0x100992cdf`
- `sqldk!SystemThread_TlsOffset` at `0x100992d35`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009919fd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991a53`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991b66`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991c78`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991d56`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991e5f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991f53`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10099201a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992123`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992214`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009922e5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009923b6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992478`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992554`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992669`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009928f8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992a21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992b02`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992bf0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992cfa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992d50`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009919fd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991a53`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991b66`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991c78`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991d56`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991e5f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100991f53`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10099201a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992123`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992214`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009922e5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009923b6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992478`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992554`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992669`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009928f8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992a21`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992b02`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992bf0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992cfa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100992d50`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991b9c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991cce`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991dba`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991eb5`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991fb4`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992077`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992184`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992271`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992342`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992413`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009924d5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009925aa`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009926cd`
- `sqldk!??_V@YAXPEAX@Z` at `0x10099295c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992a7e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992b66`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992c4d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991b9c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991cce`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991dba`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991eb5`
- `sqldk!??_V@YAXPEAX@Z` at `0x100991fb4`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992077`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992184`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992271`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992342`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992413`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009924d5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009925aa`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009926cd`
- `sqldk!??_V@YAXPEAX@Z` at `0x10099295c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992a7e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992b66`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992c4d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100992e48`

## string_xrefs

- `0x100992355`: `,READPAST`
- `0x100992280`: `,READUNCOMMITTED`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CMEDScanOdbcAgent::StartSearch(CMEDScanOdbcAgent *this, int a2, struct MEDScanSearchVal *a3)
{
  CMEDScanOdbcAgent *v4; // r15
  _QWORD *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rdx
  unsigned __int16 v11; // ax
  __int64 v12; // rbx
  __int64 v13; // rdx
  _QWORD *v14; // rdi
  unsigned int v15; // esi
  unsigned int v16; // r14d
  unsigned int v17; // r13d
  __int64 v18; // r8
  unsigned int v19; // r15d
  void **v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // r10
  unsigned __int64 v23; // rax
  int v24; // r12d
  __int64 v25; // rbx
  __int64 v26; // r10
  unsigned __int64 v27; // rax
  __int64 v28; // r13
  __int64 v29; // rbx
  __int64 v30; // r10
  unsigned __int64 v31; // rax
  char *v32; // rcx
  _WORD *v33; // r12
  __int64 v34; // r14
  __int64 v35; // r15
  __int64 v36; // rbx
  __int64 v37; // r10
  unsigned __int64 v38; // rax
  __int64 v39; // r13
  __int64 v40; // rbx
  __int64 v41; // r10
  unsigned __int64 v42; // rax
  char *v43; // rcx
  _WORD *v44; // r12
  __int64 v45; // r15
  __int64 v46; // r14
  __int64 v47; // rbx
  __int64 v48; // r10
  unsigned __int64 v49; // rax
  CMEDScanOdbcAgent *v50; // r12
  int v51; // r15d
  __int64 v52; // rbx
  __int64 v53; // r10
  unsigned __int64 v54; // rax
  __int64 v55; // rbx
  __int64 v56; // r10
  unsigned __int64 v57; // rax
  char *v58; // rcx
  __int64 v59; // rbx
  __int64 v60; // r10
  unsigned __int64 v61; // rax
  __int64 v62; // r15
  __int64 v63; // rbx
  __int64 v64; // r10
  unsigned __int64 v65; // rax
  unsigned int v66; // esi
  __int64 v67; // rbx
  __int64 v68; // r10
  unsigned __int64 v69; // rax
  char *v70; // rcx
  _DWORD *v71; // r14
  int v72; // r13d
  int v73; // esi
  int v74; // r15d
  unsigned int v75; // r12d
  __int64 v76; // rbx
  __int64 v77; // r10
  unsigned __int64 v78; // rax
  char *v79; // rdi
  char *v80; // rcx
  __int64 v81; // r8
  CMEDScanOdbcAgent *v82; // rcx
  __int64 v83; // rbx
  CMEDScanOdbcAgent *v84; // rcx
  SQLLEN *v85; // rdi
  unsigned int v86; // r14d
  __int64 v87; // rbx
  __int64 v88; // r10
  unsigned __int64 v89; // rax
  char *v90; // rcx
  unsigned int v91; // r13d
  __int64 v92; // r9
  __int64 v93; // r15
  void **v94; // rcx
  __int64 v95; // rbx
  __int64 v96; // r10
  unsigned __int64 v97; // rax
  int v98; // r12d
  __int64 v99; // rbx
  __int64 v100; // r10
  unsigned __int64 v101; // rax
  __int64 v102; // rbx
  __int64 v103; // r10
  unsigned __int64 v104; // rax
  char *v105; // rcx
  __int64 v106; // rbx
  __int64 v107; // rax
  __int64 v108; // rcx
  __int64 v109; // rbx
  __int64 v110; // rdx
  void *v111; // rbx
  unsigned __int16 v112; // ax
  void (__fastcall ***v113)(_QWORD, _QWORD, _QWORD, __int64, int, _QWORD); // rcx
  SQLLEN v114; // [rsp+20h] [rbp-E0h]
  unsigned int v115; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  void *v117; // [rsp+50h] [rbp-B0h]
  int v118; // [rsp+58h] [rbp-A8h] BYREF
  SQLLEN *v119; // [rsp+60h] [rbp-A0h]
  int v120; // [rsp+70h] [rbp-90h] BYREF
  __int64 v121; // [rsp+78h] [rbp-88h]
  int v122; // [rsp+80h] [rbp-80h] BYREF
  int v123; // [rsp+84h] [rbp-7Ch]
  __int64 v124; // [rsp+88h] [rbp-78h]
  int v125; // [rsp+90h] [rbp-70h] BYREF
  __int64 v126; // [rsp+98h] [rbp-68h]
  __int64 v127; // [rsp+A0h] [rbp-60h]
  __int64 v128; // [rsp+A8h] [rbp-58h]
  __int64 v129; // [rsp+B0h] [rbp-50h]
  bool v130; // [rsp+C0h] [rbp-40h]
  int v131; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v132; // [rsp+D8h] [rbp-28h]
  int v133; // [rsp+E0h] [rbp-20h]
  int v134; // [rsp+E4h] [rbp-1Ch]
  __int64 v135; // [rsp+E8h] [rbp-18h]
  int v136; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v137; // [rsp+F8h] [rbp-8h]
  __int64 v138; // [rsp+100h] [rbp+0h]
  __int64 v139; // [rsp+108h] [rbp+8h]
  __int64 v140; // [rsp+110h] [rbp+10h]
  bool v141; // [rsp+120h] [rbp+20h]
  __int64 v142; // [rsp+130h] [rbp+30h]
  int *TextLength; // [rsp+1A8h] [rbp+A8h] BYREF

  v142 = -2;
  v4 = this;
  (*(void (__fastcall **)(CMEDScanOdbcAgent *))(*(_QWORD *)this + 80LL))(this);
  v118 = 1;
  v119 = 0;
  if ( a2 > 0 )
  {
    _mm_lfence();
    v5 = operator new[](
           (unsigned int)(8 * a2) + 8LL,
           *((struct IMemObj **)v4 + 4),
           "sql\\ntdbms\\metadata\\src\\cmed.h",
           172,
           6u);
    *v5 = *((_QWORD *)v4 + 5);
    *((_QWORD *)v4 + 5) = v5;
    v119 = v5 + 1;
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v120, 1);
  TextLength = &v122;
  v125 = 536871503;
  v126 = 0;
  v128 = 0;
  v127 = 0;
  v129 = 0;
  v130 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 600);
  if ( v8 )
    v130 = (unsigned int)SOS_Task::PushWait(v8, &v125) == 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v124 = v10;
  v123 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
  if ( v123 || (*(_BYTE *)(v10 + 800) & 4) == 0 )
  {
    v122 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 608) + 8LL))(*(_QWORD *)(v10 + 608));
  }
  else
  {
    v122 = 0;
  }
  v11 = SQLAllocHandle(3, **(SQLHANDLE **)(*((_QWORD *)v4 + 1) + 8LL), (SQLHANDLE *)v4 + 6);
  (***(void (__fastcall ****)(_QWORD, _QWORD, _QWORD, __int64, int, _QWORD))(*(_QWORD *)(*((_QWORD *)v4 + 1) + 8LL)
                                                                           + 16LL))(
    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v4 + 1) + 8LL) + 16LL),
    v11,
    **(_QWORD **)(*((_QWORD *)v4 + 1) + 8LL),
    2,
    121,
    0);
  TextLength = &v122;
  if ( v122 )
  {
    if ( v123 )
      *(_DWORD *)(v124 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v124 + 608) + 16LL))(
        *(_QWORD *)(v124 + 608),
        v124,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v125);
  *(_DWORD *)(v121 + 616) &= ~v120;
  Src = 0;
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  v14 = operator new[](
          0x200u,
          *(struct IMemObj **)(v13 + 1000),
          "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
          200,
          6u);
  operator delete[](0);
  Src = v14;
  v15 = 256;
  v115 = 256;
  *v14 = *(_QWORD *)L"SELECT ";
  *((_DWORD *)v14 + 2) = *(_DWORD *)L"CT ";
  *((_WORD *)v14 + 6) = aSelect_0[6];
  v16 = 7;
  LODWORD(TextLength) = 7;
  v17 = 1;
  v18 = *((_QWORD *)v4 + 1);
  if ( *(_BYTE *)(*(_QWORD *)(v18 + 88) + 2LL) )
  {
    v19 = 7;
    do
    {
      v20 = (void **)(*(_QWORD *)(*(_QWORD *)(v18 + 16) + 8LL)
                    + 24LL
                    * ((unsigned int)*(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(v18 + 88) + 8LL) + 4LL * (v17 - 1)) - 1));
      v117 = v20;
      if ( v17 > 1 )
      {
        v16 = v19 + 1;
        if ( v15 < v19 + 1 )
        {
          v15 = (v19 + 256) & 0xFFFFFF00;
          v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v22 = *(_QWORD *)(v21 + 256);
          if ( !v22 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v22 = *(_QWORD *)(v21 + 256);
          }
          v23 = 2LL * v15;
          if ( !is_mul_ok(v15, 2u) )
            v23 = -1;
          v14 = operator new[](
                  v23,
                  *(struct IMemObj **)(v22 + 1000),
                  "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
                  200,
                  6u);
          memmove(v14, Src, 2 * v19);
          operator delete[](Src);
          Src = v14;
          v115 = (v19 + 256) & 0xFFFFFF00;
          v20 = (void **)v117;
        }
        *((_WORD *)v14 + v19) = 44;
        LODWORD(TextLength) = ++v19;
      }
      v24 = *((_DWORD *)v20 + 4);
      v117 = v20[1];
      if ( v15 < v19 + v24 )
      {
        _mm_lfence();
        v15 = (v24 + (_DWORD)TextLength + 255) & 0xFFFFFF00;
        v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v26 = *(_QWORD *)(v25 + 256);
        if ( !v26 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v26 = *(_QWORD *)(v25 + 256);
        }
        v27 = 2LL * v15;
        if ( !is_mul_ok(v15, 2u) )
          v27 = -1;
        v14 = operator new[](
                v27,
                *(struct IMemObj **)(v26 + 1000),
                "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
                200,
                6u);
        v16 = (unsigned int)TextLength;
        memmove(v14, Src, (unsigned int)(2 * (_DWORD)TextLength));
        operator delete[](Src);
        Src = v14;
        v115 = v15;
      }
      memmove((char *)v14 + 2 * v16, v117, (unsigned int)(2 * v24));
      v16 += v24;
      v19 = v16;
      LODWORD(TextLength) = v16;
      ++v17;
      v18 = *((_QWORD *)this + 1);
    }
    while ( v17 <= *(unsigned __int8 *)(*(_QWORD *)(v18 + 88) + 2LL) );
    v4 = this;
  }
  v28 = v16 + 13;
  if ( v15 < (unsigned int)v28 )
  {
    v15 = (v16 + 268) & 0xFFFFFF00;
    v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v30 = *(_QWORD *)(v29 + 256);
    if ( !v30 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v30 = *(_QWORD *)(v29 + 256);
    }
    v31 = 2LL * v15;
    if ( !is_mul_ok(v15, 2u) )
      v31 = -1;
    v14 = operator new[](v31, *(struct IMemObj **)(v30 + 1000), "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp", 200, 6u);
    memmove(v14, Src, 2 * v16);
    operator delete[](Src);
    Src = v14;
    v115 = (v16 + 268) & 0xFFFFFF00;
  }
  v32 = (char *)v14 + 2 * v16;
  *(_OWORD *)v32 = *(_OWORD *)L" FROM sys.sys";
  *((_QWORD *)v32 + 2) = *(_QWORD *)L"s.sys";
  *((_WORD *)v32 + 12) = aFromSysSys[12];
  v33 = *(_WORD **)(*(_QWORD *)(*((_QWORD *)v4 + 1) + 16LL) + 24LL);
  v34 = -1;
  do
    ++v34;
  while ( v33[v34] );
  v35 = (unsigned int)(v34 + v28);
  if ( v15 < (unsigned int)v35 )
  {
    v15 = (v35 + 255) & 0xFFFFFF00;
    v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v37 = *(_QWORD *)(v36 + 256);
    if ( !v37 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v37 = *(_QWORD *)(v36 + 256);
    }
    v38 = 2LL * v15;
    if ( !is_mul_ok(v15, 2u) )
      v38 = -1;
    v14 = operator new[](v38, *(struct IMemObj **)(v37 + 1000), "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp", 200, 6u);
    memmove(v14, Src, (unsigned int)(2 * v28));
    operator delete[](Src);
    Src = v14;
    v115 = (v35 + 255) & 0xFFFFFF00;
  }
  memmove((char *)v14 + 2 * v28, v33, (unsigned int)(2 * v34));
  v39 = (unsigned int)(v35 + 22);
  if ( v15 < (unsigned int)v39 )
  {
    v15 = (v35 + 277) & 0xFFFFFF00;
    v40 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v41 = *(_QWORD *)(v40 + 256);
    if ( !v41 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v41 = *(_QWORD *)(v40 + 256);
    }
    v42 = 2LL * v15;
    if ( !is_mul_ok(v15, 2u) )
      v42 = -1;
    v14 = operator new[](v42, *(struct IMemObj **)(v41 + 1000), "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp", 200, 6u);
    memmove(v14, Src, (unsigned int)(2 * v35));
    operator delete[](Src);
    Src = v14;
    v115 = (v35 + 277) & 0xFFFFFF00;
  }
  v43 = (char *)v14 + 2 * v35;
  *(_OWORD *)v43 = *(_OWORD *)L" WITH (ROWLOCK, INDEX=";
  *((_OWORD *)v43 + 1) = *(_OWORD *)L"OWLOCK, INDEX=";
  *((_QWORD *)v43 + 4) = *(_QWORD *)L"INDEX=";
  *((_DWORD *)v43 + 10) = *(_DWORD *)L"X=";
  v44 = *(_WORD **)(*(_QWORD *)(*((_QWORD *)this + 1) + 88LL) + 32LL);
  v45 = -1;
  do
    ++v45;
  while ( v44[v45] );
  v46 = (unsigned int)(v45 + v39);
  if ( v15 < (unsigned int)v46 )
  {
    v15 = (v46 + 255) & 0xFFFFFF00;
    v47 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v48 = *(_QWORD *)(v47 + 256);
    if ( !v48 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v48 = *(_QWORD *)(v47 + 256);
    }
    v49 = 2LL * v15;
    if ( !is_mul_ok(v15, 2u) )
      v49 = -1;
    v14 = operator new[](v49, *(struct IMemObj **)(v48 + 1000), "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp", 200, 6u);
    memmove(v14, Src, (unsigned int)(2 * v39));
    operator delete[](Src);
    Src = v14;
    v115 = (v46 + 255) & 0xFFFFFF00;
  }
  memmove((char *)v14 + 2 * v39, v44, (unsigned int)(2 * v45));
  v50 = this;
  switch ( *(_DWORD *)(*((_QWORD *)this + 1) + 32LL) )
  {
    case 1:
      v51 = v46 + 8;
      if ( v15 < (int)v46 + 8 )
      {
        v15 = (v46 + 263) & 0xFFFFFF00;
        v59 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v60 = *(_QWORD *)(v59 + 256);
        if ( !v60 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v60 = *(_QWORD *)(v59 + 256);
        }
        v61 = 2LL * v15;
        if ( !is_mul_ok(v15, 2u) )
          v61 = -1;
        v14 = operator new[](
                v61,
                *(struct IMemObj **)(v60 + 1000),
                "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
                200,
                6u);
        memmove(v14, Src, (unsigned int)(2 * v46));
        operator delete[](Src);
        Src = v14;
        v115 = (v46 + 263) & 0xFFFFFF00;
      }
      *(_OWORD *)((char *)v14 + 2 * v46) = *(_OWORD *)L",UPDLOCK";
      break;
    case 2:
      v51 = v46 + 9;
      if ( v15 < (int)v46 + 9 )
      {
        v15 = (v46 + 264) & 0xFFFFFF00;
        v55 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v56 = *(_QWORD *)(v55 + 256);
        if ( !v56 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v56 = *(_QWORD *)(v55 + 256);
        }
        v57 = 2LL * v15;
        if ( !is_mul_ok(v15, 2u) )
          v57 = -1;
        v14 = operator new[](
                v57,
                *(struct IMemObj **)(v56 + 1000),
                "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
                200,
                6u);
        memmove(v14, Src, (unsigned int)(2 * v46));
        operator delete[](Src);
        Src = v14;
        v115 = (v46 + 264) & 0xFFFFFF00;
      }
      v58 = (char *)v14 + 2 * v46;
      *(_OWORD *)v58 = *(_OWORD *)L",READPAST";
      *((_WORD *)v58 + 8) = aReadpast[8];
      break;
    case 3:
      v51 = v46 + 16;
      if ( v15 < (int)v46 + 16 )
      {
        v15 = (v46 + 271) & 0xFFFFFF00;
        v52 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v53 = *(_QWORD *)(v52 + 256);
        if ( !v53 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v53 = *(_QWORD *)(v52 + 256);
        }
        v54 = 2LL * v15;
        if ( !is_mul_ok(v15, 2u) )
          v54 = -1;
        v14 = operator new[](
                v54,
                *(struct IMemObj **)(v53 + 1000),
                "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
                200,
                6u);
        memmove(v14, Src, (unsigned int)(2 * v46));
        operator delete[](Src);
        Src = v14;
        v115 = (v46 + 271) & 0xFFFFFF00;
      }
      *(_OWORD *)((char *)v14 + 2 * v46) = *(_OWORD *)L",READUNCOMMITTED";
      *(_OWORD *)((char *)v14 + 2 * v46 + 16) = *(_OWORD *)L"OMMITTED";
      break;
    default:
      goto LABEL_90;
  }
  LODWORD(v46) = v51;
LABEL_90:
  v62 = (unsigned int)(v46 + 1);
  if ( v15 < (unsigned int)v62 )
  {
    v15 = (v46 + 256) & 0xFFFFFF00;
    v63 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v64 = *(_QWORD *)(v63 + 256);
    if ( !v64 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v64 = *(_QWORD *)(v63 + 256);
    }
    v65 = 2LL * v15;
    if ( !is_mul_ok(v15, 2u) )
      v65 = -1;
    v14 = operator new[](v65, *(struct IMemObj **)(v64 + 1000), "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp", 200, 6u);
    memmove(v14, Src, (unsigned int)(2 * v46));
    operator delete[](Src);
    Src = v14;
    v115 = (v46 + 256) & 0xFFFFFF00;
  }
  *((_WORD *)v14 + (unsigned int)v46) = 41;
  LODWORD(TextLength) = v46 + 1;
  if ( a2 > 0 )
  {
    if ( v15 < (int)v46 + 8 )
    {
      v66 = (v46 + 263) & 0xFFFFFF00;
      v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v68 = *(_QWORD *)(v67 + 256);
      if ( !v68 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v68 = *(_QWORD *)(v67 + 256);
      }
      v69 = 2LL * v66;
      if ( !is_mul_ok(v66, 2u) )
        v69 = -1;
      v14 = operator new[](
              v69,
              *(struct IMemObj **)(v68 + 1000),
              "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
              200,
              6u);
      memmove(v14, Src, (unsigned int)(2 * v62));
      operator delete[](Src);
      Src = v14;
      v115 = (v46 + 263) & 0xFFFFFF00;
    }
    v70 = (char *)v14 + 2 * v62;
    *(_QWORD *)v70 = *(_QWORD *)L" WHERE ";
    *((_DWORD *)v70 + 2) = *(_DWORD *)L"RE ";
    *((_WORD *)v70 + 6) = aWhere_0[6];
    LODWORD(TextLength) = v46 + 8;
    _mm_lfence();
    v71 = (_DWORD *)((char *)a3 + 16);
    v72 = 0;
    do
    {
      if ( v72 > 0 )
      {
        v73 = (int)TextLength;
        v74 = (_DWORD)TextLength + 5;
        if ( v115 >= (int)TextLength + 5 )
        {
          v79 = (char *)Src;
        }
        else
        {
          v75 = ((_DWORD)TextLength + 260) & 0xFFFFFF00;
          v76 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v77 = *(_QWORD *)(v76 + 256);
          if ( !v77 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v77 = *(_QWORD *)(v76 + 256);
          }
          v78 = 2LL * v75;
          if ( !is_mul_ok(v75, 2u) )
            v78 = -1;
          v79 = (char *)operator new[](
                          v78,
                          *(struct IMemObj **)(v77 + 1000),
                          "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
                          200,
                          6u);
          v73 = (int)TextLength;
          memmove(v79, Src, (unsigned int)(2 * (_DWORD)TextLength));
          operator delete[](Src);
          Src = v79;
          v115 = v75;
          v50 = this;
        }
        v80 = &v79[2 * v73];
        *(_QWORD *)v80 = *(_QWORD *)L" AND ";
        *((_WORD *)v80 + 4) = aAnd_0[4];
        LODWORD(TextLength) = v74;
      }
      v81 = *((_QWORD *)v50 + 1);
      v82 = *(CMEDScanOdbcAgent **)(*(_QWORD *)(v81 + 16) + 8LL);
      v83 = (__int64)v82
          + 24
          * (unsigned int)*(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(v81 + 88) + 8LL)
                                             + 4LL * (unsigned int)(*(v71 - 4) - 1))
          - 24;
      CMEDScanOdbcAgent::AppendFragment(
        v82,
        (wchar_t **)&Src,
        &v115,
        (unsigned int *)&TextLength,
        *(const wchar_t **)(v83 + 8),
        *(_DWORD *)(v83 + 16));
      switch ( *((_BYTE *)v71 - 12) )
      {
        case 0x81:
          CMEDScanOdbcAgent::AppendFragment(v84, (wchar_t **)&Src, &v115, (unsigned int *)&TextLength, L" = ?", 4u);
          break;
        case 0x82:
          CMEDScanOdbcAgent::AppendFragment(v84, (wchar_t **)&Src, &v115, (unsigned int *)&TextLength, L" < ?", 4u);
          break;
        case 0x83:
          CMEDScanOdbcAgent::AppendFragment(v84, (wchar_t **)&Src, &v115, (unsigned int *)&TextLength, L" <= ?", 5u);
          break;
        case 0x84:
          CMEDScanOdbcAgent::AppendFragment(v84, (wchar_t **)&Src, &v115, (unsigned int *)&TextLength, L" > ?", 4u);
          break;
        case 0x85:
          CMEDScanOdbcAgent::AppendFragment(v84, (wchar_t **)&Src, &v115, (unsigned int *)&TextLength, L" >= ?", 5u);
          break;
        case 0x86:
          CMEDScanOdbcAgent::AppendFragment(v84, (wchar_t **)&Src, &v115, (unsigned int *)&TextLength, L" <> ?", 5u);
          break;
        default:
          utassert_fail(1u, "FALSE", "cmedscanodbc.cpp", 349, "Invalid switch value");
          break;
      }
      v85 = v119;
      LODWORD(v114) = *v71;
      CMEDScanOdbcAgent::BindParameter((int)v50, (_DWORD)v50 + 48, (int)&v118, *((_QWORD *)v71 - 1), v114, v83, v119);
      ++v72;
      v119 = v85 + 1;
      v71 += 6;
    }
    while ( v72 < a2 );
    v14 = Src;
    v15 = v115;
    LODWORD(v62) = (_DWORD)TextLength;
  }
  v86 = v62 + 10;
  if ( v15 < (int)v62 + 10 )
  {
    v15 = (v62 + 265) & 0xFFFFFF00;
    v87 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v88 = *(_QWORD *)(v87 + 256);
    if ( !v88 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v88 = *(_QWORD *)(v87 + 256);
    }
    v89 = 2LL * v15;
    if ( !is_mul_ok(v15, 2u) )
      v89 = -1;
    v14 = operator new[](v89, *(struct IMemObj **)(v88 + 1000), "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp", 200, 6u);
    LODWORD(v62) = (_DWORD)TextLength;
    memmove(v14, Src, (unsigned int)(2 * (_DWORD)TextLength));
    operator delete[](Src);
    Src = v14;
  }
  v90 = (char *)v14 + 2 * (unsigned int)v62;
  *(_OWORD *)v90 = *(_OWORD *)L" ORDER BY ";
  *((_DWORD *)v90 + 4) = *(_DWORD *)L"Y ";
  LODWORD(TextLength) = v86;
  v91 = 0;
  v92 = *((_QWORD *)v50 + 1);
  if ( *(_BYTE *)(*(_QWORD *)(v92 + 88) + 3LL) )
  {
    LODWORD(v93) = v86;
    do
    {
      v94 = (void **)(*(_QWORD *)(*(_QWORD *)(v92 + 16) + 8LL)
                    + 24LL
                    * ((unsigned int)*(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(v92 + 88) + 8LL)
                                                        + 4LL
                                                        * ((unsigned int)*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v92 + 88) + 16LL)
                                                                                             + 2LL * (int)v91)
                                                         - 1))
                     - 1));
      v117 = v94;
      if ( v91 )
      {
        v86 = v93 + 1;
        if ( v15 < (int)v93 + 1 )
        {
          v15 = (v93 + 256) & 0xFFFFFF00;
          v95 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v96 = *(_QWORD *)(v95 + 256);
          if ( !v96 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v96 = *(_QWORD *)(v95 + 256);
          }
          v97 = 2LL * v15;
          if ( !is_mul_ok(v15, 2u) )
            v97 = -1;
          v14 = operator new[](
                  v97,
                  *(struct IMemObj **)(v96 + 1000),
                  "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
                  200,
                  6u);
          memmove(v14, Src, (unsigned int)(2 * v93));
          operator delete[](Src);
          Src = v14;
          v94 = (void **)v117;
        }
        *((_WORD *)v14 + (unsigned int)v93) = 44;
        LODWORD(TextLength) = v93 + 1;
        LODWORD(v93) = v93 + 1;
      }
      v98 = *((_DWORD *)v94 + 4);
      v117 = v94[1];
      if ( v15 < (int)v93 + v98 )
      {
        _mm_lfence();
        v15 = (v98 + (_DWORD)TextLength + 255) & 0xFFFFFF00;
        v99 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v100 = *(_QWORD *)(v99 + 256);
        if ( !v100 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v100 = *(_QWORD *)(v99 + 256);
        }
        v101 = 2LL * v15;
        if ( !is_mul_ok(v15, 2u) )
          v101 = -1;
        v14 = operator new[](
                v101,
                *(struct IMemObj **)(v100 + 1000),
                "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
                200,
                6u);
        v86 = (unsigned int)TextLength;
        memmove(v14, Src, (unsigned int)(2 * (_DWORD)TextLength));
        operator delete[](Src);
        Src = v14;
      }
      memmove((char *)v14 + 2 * v86, v117, (unsigned int)(2 * v98));
      v86 += v98;
      v93 = v86;
      LODWORD(TextLength) = v86;
      v50 = this;
      if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 104LL) & 0x20) != 0 )
      {
        v86 += 5;
        if ( v15 < v86 )
        {
          v15 = (v93 + 260) & 0xFFFFFF00;
          v102 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v103 = *(_QWORD *)(v102 + 256);
          if ( !v103 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v103 = *(_QWORD *)(v102 + 256);
          }
          v104 = 2LL * v15;
          if ( !is_mul_ok(v15, 2u) )
            v104 = -1;
          v14 = operator new[](
                  v104,
                  *(struct IMemObj **)(v103 + 1000),
                  "sql\\ntdbms\\metadata\\src\\cmedscanodbc.cpp",
                  200,
                  6u);
          memmove(v14, Src, (unsigned int)(2 * v93));
          operator delete[](Src);
          Src = v14;
        }
        v105 = (char *)v14 + 2 * v93;
        *(_QWORD *)v105 = *(_QWORD *)L" DESC";
        *((_WORD *)v105 + 4) = aDesc[4];
        LODWORD(TextLength) = v86;
        LODWORD(v93) = v86;
      }
      ++v91;
      v92 = *((_QWORD *)this + 1);
    }
    while ( v91 < *(unsigned __int8 *)(*(_QWORD *)(v92 + 88) + 3LL) );
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v131, 1);
  v136 = 536871503;
  v137 = 0;
  v139 = 0;
  v138 = 0;
  v140 = 0;
  v141 = 0;
  v106 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v107 = *(_QWORD *)(v106 + 256);
  if ( !v107 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v107 = *(_QWORD *)(v106 + 256);
  }
  v108 = *(_QWORD *)(v107 + 600);
  if ( v108 )
    v141 = (unsigned int)SOS_Task::PushWait(v108, &v136) == 0;
  v109 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v110 = *(_QWORD *)(v109 + 256);
  if ( !v110 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v110 = *(_QWORD *)(v109 + 256);
  }
  v135 = v110;
  v134 = (*(_DWORD *)(v110 + 800) >> 11) & 1;
  if ( v134 || (*(_BYTE *)(v110 + 800) & 4) == 0 )
  {
    v133 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v110 + 608) + 8LL))(*(_QWORD *)(v110 + 608));
  }
  else
  {
    v133 = 0;
  }
  v111 = Src;
  v112 = SQLExecDirectW(*((SQLHSTMT *)v50 + 6), (SQLWCHAR *)Src, (SQLINTEGER)TextLength);
  v113 = *(void (__fastcall ****)(_QWORD, _QWORD, _QWORD, __int64, int, _QWORD))(*(_QWORD *)(*((_QWORD *)v50 + 1) + 8LL)
                                                                               + 16LL);
  (**v113)(v113, v112, *((_QWORD *)v50 + 6), 3, 123, 0);
  if ( v133 )
  {
    if ( v134 )
      *(_DWORD *)(v135 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v135 + 608) + 16LL))(
        *(_QWORD *)(v135 + 608),
        v135,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v136);
  *(_DWORD *)(v132 + 616) &= ~v131;
  operator delete[](v111);
}

```

## disassembly

```asm
0x100991910  mov     [rsp-8+arg_10], r8
0x100991915  mov     [rsp-8+arg_8], edx
0x100991919  mov     qword ptr [rsp-8+arg_0], rcx
0x10099191e  push    rbp
0x10099191f  push    rbx
0x100991920  push    rsi
0x100991921  push    rdi
0x100991922  push    r12
0x100991924  push    r13
0x100991926  push    r14
0x100991928  push    r15
0x10099192a  lea     rbp, [rsp-48h]
0x10099192f  sub     rsp, 148h
0x100991936  mov     [rbp+80h+var_50], 0FFFFFFFFFFFFFFFEh
0x10099193e  mov     ebx, edx
0x100991940  mov     r15, rcx
0x100991943  mov     rax, [rcx]
0x100991946  call    qword ptr [rax+50h]
0x100991949  mov     [rsp+180h+var_128], 1
0x100991951  xor     edi, edi
0x100991953  mov     [rsp+180h+var_120], rdi
0x100991958  test    ebx, ebx
0x10099195a  jle     short loc_10099199A
0x10099195c  lfence
0x10099195f  lea     ecx, ds:0[rbx*8]
0x100991966  add     rcx, 8
0x10099196a  mov     byte ptr [rsp+180h+var_160], 6
0x10099196f  mov     r9d, 0ACh
0x100991975  lea     r8, aSqlNtdbmsMetad_34; "sql\\ntdbms\\metadata\\src\\cmed.h"
0x10099197c  mov     rdx, [r15+20h]
0x100991980  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100991986  mov     rcx, [r15+28h]
0x10099198a  mov     [rax], rcx
0x10099198d  mov     [r15+28h], rax
0x100991991  add     rax, 8
0x100991995  mov     [rsp+180h+var_120], rax
0x10099199a  mov     edx, 1
0x10099199f  lea     rcx, [rsp+180h+var_110]
0x1009919a4  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x1009919a9  nop
0x1009919aa  lea     rax, [rbp+80h+var_100]
0x1009919ae  mov     [rbp+80h+TextLength], rax
0x1009919b5  mov     [rbp+80h+var_F0], 2000024Fh
0x1009919bc  mov     [rbp+80h+var_E8], rdi
0x1009919c0  mov     [rbp+80h+var_D8], rdi
0x1009919c4  mov     [rbp+80h+var_E0], rdi
0x1009919c8  mov     [rbp+80h+var_D0], rdi
0x1009919cc  mov     [rbp+80h+var_C0], 0
0x1009919d0  mov     rdx, gs:58h
0x1009919d9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1009919e0  mov     ecx, [rax]
0x1009919e2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1009919e9  mov     ebx, [rax]
0x1009919eb  add     rbx, [rdx+rcx*8]
0x1009919ef  mov     rax, [rbx+100h]
0x1009919f6  test    rax, rax
0x1009919f9  jnz     short loc_100991A0A
0x1009919fb  xor     ecx, ecx
0x1009919fd  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100991a03  mov     rax, [rbx+100h]
0x100991a0a  mov     rcx, [rax+258h]
0x100991a11  test    rcx, rcx
0x100991a14  jz      short loc_100991A26
0x100991a16  lea     rdx, [rbp+80h+var_F0]
0x100991a1a  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100991a20  test    eax, eax
0x100991a22  setz    [rbp+80h+var_C0]
0x100991a26  mov     rdx, gs:58h
0x100991a2f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100991a36  mov     ecx, [rax]
0x100991a38  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100991a3f  mov     ebx, [rax]
0x100991a41  add     rbx, [rdx+rcx*8]
0x100991a45  mov     rdx, [rbx+100h]
0x100991a4c  test    rdx, rdx
0x100991a4f  jnz     short loc_100991A60
0x100991a51  xor     ecx, ecx
0x100991a53  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100991a59  mov     rdx, [rbx+100h]
0x100991a60  mov     [rbp+80h+var_F8], rdx
0x100991a64  mov     eax, [rdx+320h]
0x100991a6a  shr     eax, 0Bh
0x100991a6d  and     eax, 1
0x100991a70  mov     [rbp+80h+var_FC], eax
0x100991a73  jnz     short loc_100991A83
0x100991a75  test    byte ptr [rdx+320h], 4
0x100991a7c  jz      short loc_100991A83
0x100991a7e  mov     [rbp+80h+var_100], edi
0x100991a81  jmp     short loc_100991A98
0x100991a83  mov     [rbp+80h+var_100], 1
0x100991a8a  mov     rcx, [rdx+260h]
0x100991a91  mov     rax, [rcx]
0x100991a94  call    qword ptr [rax+8]
0x100991a97  nop
0x100991a98  mov     rax, [r15+8]
0x100991a9c  mov     rcx, [rax+8]
0x100991aa0  mov     rdx, [rcx]; InputHandle
0x100991aa3  lea     r8, [r15+30h]; OutputHandle
0x100991aa7  mov     ecx, 3; HandleType
0x100991aac  call    cs:__imp_SQLAllocHandle
0x100991ab2  mov     rcx, [r15+8]
0x100991ab6  mov     rdx, [rcx+8]
0x100991aba  mov     rcx, [rdx+10h]
0x100991abe  mov     r10, [rcx]
0x100991ac1  mov     r9d, 2
0x100991ac7  mov     qword ptr [rsp+180h+var_158], rdi
0x100991acc  mov     dword ptr [rsp+180h+var_160], 79h ; 'y'
0x100991ad4  mov     r8, [rdx]
0x100991ad7  movzx   edx, ax
0x100991ada  call    qword ptr [r10]
0x100991add  nop
0x100991ade  lea     rax, [rbp+80h+var_100]
0x100991ae2  mov     [rbp+80h+TextLength], rax
0x100991ae9  cmp     [rbp+80h+var_100], 0
0x100991aed  jz      short loc_100991B19
0x100991aef  mov     rdx, [rbp+80h+var_F8]
0x100991af3  mov     rcx, [rdx+260h]
0x100991afa  cmp     [rbp+80h+var_FC], 0
0x100991afe  jz      short loc_100991B0C
0x100991b00  or      dword ptr [rdx+320h], 800h
0x100991b0a  jmp     short loc_100991B19
0x100991b0c  mov     rax, [rcx]
0x100991b0f  mov     r8d, 1
0x100991b15  call    qword ptr [rax+10h]
0x100991b18  nop
0x100991b19  lea     rcx, [rbp+80h+var_F0]; this
0x100991b1d  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x100991b22  nop
0x100991b23  mov     ecx, [rsp+180h+var_110]
0x100991b27  not     ecx
0x100991b29  mov     rax, [rsp+180h+var_108]
0x100991b2e  and     [rax+268h], ecx
0x100991b34  mov     [rsp+180h+Src], rdi
0x100991b39  mov     rdx, gs:58h
0x100991b42  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100991b49  mov     ecx, [rax]
0x100991b4b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100991b52  mov     ebx, [rax]
0x100991b54  add     rbx, [rdx+rcx*8]
0x100991b58  mov     rdx, [rbx+100h]
0x100991b5f  test    rdx, rdx
0x100991b62  jnz     short loc_100991B73
0x100991b64  xor     ecx, ecx
0x100991b66  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100991b6c  mov     rdx, [rbx+100h]
0x100991b73  mov     byte ptr [rsp+180h+var_160], 6
0x100991b78  mov     r9d, 0C8h
0x100991b7e  lea     r8, aSqlNtdbmsMetad_49; "sql\\ntdbms\\metadata\\src\\cmedscanodb"...
0x100991b85  mov     rdx, [rdx+3E8h]
0x100991b8c  mov     ecx, 200h
0x100991b91  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100991b97  mov     rdi, rax
0x100991b9a  xor     ecx, ecx
0x100991b9c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100991ba2  mov     [rsp+180h+Src], rdi
0x100991ba7  mov     esi, 100h
0x100991bac  mov     [rsp+180h+var_140], esi
0x100991bb0  movsd   xmm0, qword ptr cs:aSelect_0; "SELECT "
0x100991bb8  movsd   qword ptr [rdi], xmm0
0x100991bbc  mov     eax, dword ptr cs:aSelect_0+8; "CT "
0x100991bc2  mov     [rdi+8], eax
0x100991bc5  movzx   eax, word ptr cs:aSelect_0+0Ch; " "
0x100991bcc  mov     [rdi+0Ch], ax
0x100991bd0  mov     r14d, 7
0x100991bd6  mov     dword ptr [rbp+80h+TextLength], r14d
0x100991bdd  mov     r13d, 1
0x100991be3  mov     r8, [r15+8]
0x100991be7  mov     rax, [r8+58h]
0x100991beb  lea     r12, [r14-8]
0x100991bef  cmp     [rax+2], r13b
0x100991bf3  jb      loc_100991E18
0x100991bf9  mov     r15d, r14d
0x100991bfc  nop     dword ptr [rax+00h]
0x100991c00  lea     edx, [r13-1]
0x100991c04  mov     rax, [r8+58h]
0x100991c08  mov     rcx, [rax+8]
0x100991c0c  movzx   eax, byte ptr [rcx+rdx*4]
0x100991c10  dec     eax
0x100991c12  lea     rdx, [rax+rax*2]
0x100991c16  mov     rax, [r8+10h]
0x100991c1a  mov     rcx, [rax+8]
0x100991c1e  lea     rcx, [rcx+rdx*8]
0x100991c22  mov     [rsp+180h+var_130], rcx
0x100991c27  cmp     r13d, 1
0x100991c2b  jbe     loc_100991CF8
0x100991c31  lea     r14d, [r15+1]
0x100991c35  cmp     esi, r14d
0x100991c38  jnb     loc_100991CE2
0x100991c3e  lea     esi, [r15+100h]
0x100991c45  and     esi, 0FFFFFF00h
0x100991c4b  mov     rdx, gs:58h
0x100991c54  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100991c5b  mov     ecx, [rax]
0x100991c5d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100991c64  mov     ebx, [rax]
0x100991c66  add     rbx, [rdx+rcx*8]
0x100991c6a  mov     r10, [rbx+100h]
0x100991c71  test    r10, r10
0x100991c74  jnz     short loc_100991C85
0x100991c76  xor     ecx, ecx
0x100991c78  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100991c7e  mov     r10, [rbx+100h]
0x100991c85  mov     ecx, esi
0x100991c87  mov     eax, 2
0x100991c8c  mul     rcx
0x100991c8f  cmovo   rax, r12
0x100991c93  mov     byte ptr [rsp+180h+var_160], 6
0x100991c98  mov     r9d, 0C8h
0x100991c9e  lea     r8, aSqlNtdbmsMetad_49; "sql\\ntdbms\\metadata\\src\\cmedscanodb"...
0x100991ca5  mov     rdx, [r10+3E8h]
0x100991cac  mov     rcx, rax
0x100991caf  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100991cb5  mov     rdi, rax
0x100991cb8  lea     r8d, [r15+r15]; Size
0x100991cbc  mov     rdx, [rsp+180h+Src]; Src
0x100991cc1  mov     rcx, rax; void *
0x100991cc4  call    memmove
0x100991cc9  mov     rcx, [rsp+180h+Src]
0x100991cce  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100991cd4  mov     [rsp+180h+Src], rdi
0x100991cd9  mov     [rsp+180h+var_140], esi
0x100991cdd  mov     rcx, [rsp+180h+var_130]
0x100991ce2  mov     eax, r15d
0x100991ce5  mov     edx, 2Ch ; ','
0x100991cea  mov     [rdi+rax*2], dx
0x100991cee  mov     dword ptr [rbp+80h+TextLength], r14d
0x100991cf5  mov     r15d, r14d
0x100991cf8  mov     r12d, [rcx+10h]
0x100991cfc  mov     rax, [rcx+8]
0x100991d00  mov     [rsp+180h+var_130], rax
0x100991d05  lea     eax, [r15+r12]
0x100991d09  cmp     esi, eax
0x100991d0b  jnb     loc_100991DC9
0x100991d11  lfence
0x100991d14  mov     esi, dword ptr [rbp+80h+TextLength]
0x100991d1a  add     esi, 0FFh
0x100991d20  add     esi, r12d
0x100991d23  and     esi, 0FFFFFF00h
0x100991d29  mov     rdx, gs:58h
0x100991d32  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100991d39  mov     ecx, [rax]
0x100991d3b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100991d42  mov     ebx, [rax]
0x100991d44  add     rbx, [rdx+rcx*8]
0x100991d48  mov     r10, [rbx+100h]
0x100991d4f  test    r10, r10
0x100991d52  jnz     short loc_100991D63
0x100991d54  xor     ecx, ecx
0x100991d56  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100991d5c  mov     r10, [rbx+100h]
0x100991d63  mov     ecx, esi
0x100991d65  mov     eax, 2
0x100991d6a  mul     rcx
0x100991d6d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100991d74  cmovo   rax, rcx
0x100991d78  mov     byte ptr [rsp+180h+var_160], 6
0x100991d7d  mov     r9d, 0C8h
0x100991d83  lea     r8, aSqlNtdbmsMetad_49; "sql\\ntdbms\\metadata\\src\\cmedscanodb"...
0x100991d8a  mov     rdx, [r10+3E8h]
0x100991d91  mov     rcx, rax
0x100991d94  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100991d9a  mov     rdi, rax
0x100991d9d  mov     r14d, dword ptr [rbp+80h+TextLength]
0x100991da4  lea     r8d, [r14+r14]; Size
0x100991da8  mov     rdx, [rsp+180h+Src]; Src
0x100991dad  mov     rcx, rax; void *
0x100991db0  call    memmove
0x100991db5  mov     rcx, [rsp+180h+Src]
0x100991dba  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100991dc0  mov     [rsp+180h+Src], rdi
0x100991dc5  mov     [rsp+180h+var_140], esi
0x100991dc9  lea     r8d, [r12+r12]; Size
0x100991dcd  mov     eax, r14d
0x100991dd0  lea     rcx, [rdi+rax*2]; void *
0x100991dd4  mov     rdx, [rsp+180h+var_130]; Src
0x100991dd9  call    memmove
0x100991dde  add     r14d, r12d
0x100991de1  mov     r15d, r14d
0x100991de4  mov     dword ptr [rbp+80h+TextLength], r14d
0x100991deb  inc     r13d
0x100991dee  mov     rax, qword ptr [rbp+80h+arg_0]
0x100991df5  mov     r8, [rax+8]
0x100991df9  mov     rax, [r8+58h]
0x100991dfd  movzx   ecx, byte ptr [rax+2]
0x100991e01  cmp     r13d, ecx
0x100991e04  mov     r12, 0FFFFFFFFFFFFFFFFh
0x100991e0b  jbe     loc_100991C00
0x100991e11  mov     r15, qword ptr [rbp+80h+arg_0]
0x100991e18  lea     r13d, [r14+0Dh]
0x100991e1c  cmp     esi, r13d
0x100991e1f  jnb     loc_100991EC4
0x100991e25  lea     esi, [r14+10Ch]
0x100991e2c  and     esi, 0FFFFFF00h
0x100991e32  mov     rdx, gs:58h
0x100991e3b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100991e42  mov     ecx, [rax]
0x100991e44  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100991e4b  mov     ebx, [rax]
0x100991e4d  add     rbx, [rdx+rcx*8]
0x100991e51  mov     r10, [rbx+100h]
  ... truncated ...
```
