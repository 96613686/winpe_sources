# CBlbBackupAsync::PublishAllBackupStopEvents(long,uchar)

- ea: `0x140031960`
- end: `0x140032993`
- name: `?PublishAllBackupStopEvents@CBlbBackupAsync@@AEAAJJE@Z`
- size: `4147`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this, int, unsigned __int8)`
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000dd44`
- `0x140014f7c`
- `0x140031960`
- `0x140039730`
- `0x14003c804`
- `0x140079300`
- `0x140079378`
- `0x140086070`
- `0x1400889f0`
- `0x1400d20a8`
- `0x1400d4ba4`
- `0x1400d4c5c`
- `0x1400d4f1c`
- `0x1400d616c`
- `0x1400d7294`
- `0x1400e97b4`
- `0x140101b64`
- `0x140101c50`
- `0x140113368`
- `0x14012e7ec`
- `0x140134d20`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x140031b94`
- `ole32!CoTaskMemAlloc` at `0x140031bc6`
- `ole32!CoTaskMemAlloc` at `0x140031bee`
- `ole32!CoTaskMemAlloc` at `0x140031c16`
- `ole32!CoTaskMemAlloc` at `0x140031c42`
- `ole32!CoTaskMemAlloc` at `0x140031c6e`
- `ole32!CoTaskMemAlloc` at `0x140031c9a`
- `ole32!CoTaskMemAlloc` at `0x140031cc6`
- `ole32!CoTaskMemAlloc` at `0x140031cf2`
- `ole32!CoTaskMemAlloc` at `0x140031d1e`
- `ole32!CoTaskMemAlloc` at `0x140031d4a`
- `ole32!CoTaskMemAlloc` at `0x140031d76`
- `ole32!CoTaskMemAlloc` at `0x140031da2`
- `ole32!CoTaskMemAlloc` at `0x140031dce`
- `ole32!CoTaskMemAlloc` at `0x140031dfd`
- `ole32!CoTaskMemAlloc` at `0x140031e2c`
- `ole32!CoTaskMemAlloc` at `0x140031e5b`
- `ole32!CoTaskMemAlloc` at `0x140031e8a`
- `ole32!CoTaskMemAlloc` at `0x140031eb9`
- `ole32!CoTaskMemAlloc` at `0x140031ee8`
- `ole32!CoTaskMemAlloc` at `0x140031f17`
- `ole32!CoTaskMemAlloc` at `0x140031f42`
- `ole32!CoTaskMemAlloc` at `0x140031f66`
- `ole32!CoTaskMemAlloc` at `0x140031f8a`
- `ole32!CoTaskMemAlloc` at `0x140031fb1`
- `ole32!CoTaskMemAlloc` at `0x140031fdc`
- `ole32!CoTaskMemAlloc` at `0x14003200b`
- `ole32!CoTaskMemAlloc` at `0x1400323d3`
- `ole32!CoTaskMemAlloc` at `0x14003248d`
- `ole32!CoTaskMemAlloc` at `0x140032516`
- `ole32!CoTaskMemAlloc` at `0x140032545`
- `ole32!CoTaskMemAlloc` at `0x140031b94`
- `ole32!CoTaskMemAlloc` at `0x140031bc6`
- `ole32!CoTaskMemAlloc` at `0x140031bee`
- `ole32!CoTaskMemAlloc` at `0x140031c16`
- `ole32!CoTaskMemAlloc` at `0x140031c42`
- `ole32!CoTaskMemAlloc` at `0x140031c6e`
- `ole32!CoTaskMemAlloc` at `0x140031c9a`
- `ole32!CoTaskMemAlloc` at `0x140031cc6`
- `ole32!CoTaskMemAlloc` at `0x140031cf2`
- `ole32!CoTaskMemAlloc` at `0x140031d1e`
- `ole32!CoTaskMemAlloc` at `0x140031d4a`
- `ole32!CoTaskMemAlloc` at `0x140031d76`
- `ole32!CoTaskMemAlloc` at `0x140031da2`
- `ole32!CoTaskMemAlloc` at `0x140031dce`
- `ole32!CoTaskMemAlloc` at `0x140031dfd`
- `ole32!CoTaskMemAlloc` at `0x140031e2c`
- `ole32!CoTaskMemAlloc` at `0x140031e5b`
- `ole32!CoTaskMemAlloc` at `0x140031e8a`
- `ole32!CoTaskMemAlloc` at `0x140031eb9`
- `ole32!CoTaskMemAlloc` at `0x140031ee8`
- `ole32!CoTaskMemAlloc` at `0x140031f17`
- `ole32!CoTaskMemAlloc` at `0x140031f42`
- `ole32!CoTaskMemAlloc` at `0x140031f66`
- `ole32!CoTaskMemAlloc` at `0x140031f8a`
- `ole32!CoTaskMemAlloc` at `0x140031fb1`
- `ole32!CoTaskMemAlloc` at `0x140031fdc`
- `ole32!CoTaskMemAlloc` at `0x14003200b`
- `ole32!CoTaskMemAlloc` at `0x1400323d3`
- `ole32!CoTaskMemAlloc` at `0x14003248d`
- `ole32!CoTaskMemAlloc` at `0x140032516`
- `ole32!CoTaskMemAlloc` at `0x140032545`
- `ole32!CoTaskMemFree` at `0x140031aac`
- `ole32!CoTaskMemFree` at `0x140032416`
- `ole32!CoTaskMemFree` at `0x140031aac`
- `ole32!CoTaskMemFree` at `0x140032416`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::PublishAllBackupStopEvents(CBlbBackupAsync *this, int a2, char a3)
{
  void *v5; // r15
  int VolumeFriendlyNameForPublisher; // ebx
  unsigned int i; // r14d
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // r8
  struct _GUID v12; // xmm0
  __int64 v13; // r8
  __int128 v14; // xmm0
  char v15; // al
  void *v16; // rax
  unsigned __int16 **v17; // rax
  _DWORD *v18; // rax
  _DWORD *v19; // rax
  _DWORD *v20; // rax
  _DWORD *v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // rax
  _DWORD *v27; // rax
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  _QWORD *v33; // rax
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _BYTE *v37; // rax
  _BYTE *v38; // rax
  _BYTE *v39; // rax
  _BYTE *v40; // rax
  _DWORD *v41; // rax
  _DWORD *v42; // rax
  __int64 j; // r12
  __int64 v44; // r14
  __int64 v45; // rbx
  int v46; // eax
  int v47; // ecx
  CBlbFileBackupAsync *v48; // rbx
  _QWORD *v49; // rax
  _QWORD *v51; // rax
  __int64 k; // rsi
  _QWORD *v53; // rax
  __int64 v54; // rcx
  _QWORD *v55; // rax
  _QWORD *v56; // rax
  __int64 m; // rsi
  _QWORD *v58; // rax
  __int64 v59; // rcx
  int v60; // ecx
  const unsigned __int16 *v61; // rsi
  const unsigned __int16 *v62; // rcx
  CBlbComponentBackupHelper *v63; // rcx
  _QWORD *v64; // rcx
  __int64 v65; // rdx
  CBlbSystemStateBackupAsync *v66; // rcx
  unsigned int v67; // r9d
  char v68; // bl
  char v69; // r10
  __int64 v70; // r8
  unsigned int v71; // eax
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 n; // rcx
  const struct _EVENT_DESCRIPTOR *v75; // rdx
  LPVOID pv[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v78; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v79[80]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v80; // [rsp+C0h] [rbp-40h]
  __int128 v81; // [rsp+E0h] [rbp-20h] BYREF
  int v82; // [rsp+F0h] [rbp-10h]
  int v83; // [rsp+F4h] [rbp-Ch]
  char v84[8]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v85; // [rsp+100h] [rbp+0h]
  _DWORD cb[3]; // [rsp+104h] [rbp+4h]
  unsigned __int16 **v87; // [rsp+110h] [rbp+10h]
  _DWORD *v88; // [rsp+118h] [rbp+18h]
  _DWORD *v89; // [rsp+120h] [rbp+20h]
  _QWORD *v90; // [rsp+128h] [rbp+28h]
  _QWORD *v91; // [rsp+130h] [rbp+30h]
  _QWORD *v92; // [rsp+138h] [rbp+38h]
  _QWORD *v93; // [rsp+140h] [rbp+40h]
  _QWORD *v94; // [rsp+148h] [rbp+48h]
  _QWORD *v95; // [rsp+150h] [rbp+50h]
  _DWORD *v96; // [rsp+158h] [rbp+58h]
  _DWORD *v97; // [rsp+160h] [rbp+60h]
  _DWORD *v98; // [rsp+168h] [rbp+68h]
  _BYTE *v99; // [rsp+170h] [rbp+70h]
  _BYTE *v100; // [rsp+178h] [rbp+78h]
  _BYTE *v101; // [rsp+180h] [rbp+80h]
  _BYTE *v102; // [rsp+188h] [rbp+88h]
  _DWORD *v103; // [rsp+190h] [rbp+90h]
  _DWORD *v104; // [rsp+198h] [rbp+98h]
  __int64 v105; // [rsp+1A0h] [rbp+A0h]
  int v106; // [rsp+1A8h] [rbp+A8h]
  int v107; // [rsp+1ACh] [rbp+ACh]
  int v108; // [rsp+1B0h] [rbp+B0h] BYREF
  int v109[6]; // [rsp+1B4h] [rbp+B4h] BYREF
  __int64 v110; // [rsp+1CCh] [rbp+CCh]
  __int64 v111; // [rsp+1D4h] [rbp+D4h]
  _QWORD *v112; // [rsp+1E0h] [rbp+E0h]
  _QWORD *v113; // [rsp+1E8h] [rbp+E8h]
  _QWORD *v114; // [rsp+1F0h] [rbp+F0h]
  _QWORD *v115; // [rsp+1F8h] [rbp+F8h]
  _QWORD *v116; // [rsp+200h] [rbp+100h]
  _QWORD *v117; // [rsp+208h] [rbp+108h]
  _QWORD *v118; // [rsp+210h] [rbp+110h]
  _QWORD *v119; // [rsp+218h] [rbp+118h]
  __int64 v120; // [rsp+220h] [rbp+120h]
  __int64 v121; // [rsp+228h] [rbp+128h]
  _QWORD *v122; // [rsp+230h] [rbp+130h]
  _QWORD *v123; // [rsp+238h] [rbp+138h]
  unsigned int v124; // [rsp+240h] [rbp+140h]
  _QWORD *v125; // [rsp+248h] [rbp+148h]
  _QWORD *v126; // [rsp+250h] [rbp+150h]
  unsigned int v127; // [rsp+258h] [rbp+158h] BYREF
  struct _BLB_COMPONENT_STATUS *v128; // [rsp+260h] [rbp+160h] BYREF
  unsigned int v129; // [rsp+268h] [rbp+168h] BYREF
  struct _BLB_BACKUP_COMPONENT_STATUS *v130[5]; // [rsp+270h] [rbp+170h] BYREF
  struct _GUID v131; // [rsp+298h] [rbp+198h]
  int v132; // [rsp+2A8h] [rbp+1A8h]
  int v133; // [rsp+2ACh] [rbp+1ACh]
  unsigned __int16 *v134; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 *v135; // [rsp+2B8h] [rbp+1B8h] BYREF
  int v136; // [rsp+2C0h] [rbp+1C0h]

  memset_0(&v81, 0, 0x1E8u);
  v5 = 0;
  pv[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 623, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  memset_0(&v81, 0, 0x1E8u);
  memset_0(v79, 0, 0x70u);
  VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                     *((_QWORD *)this + 43),
                                     *((unsigned int *)this + 84),
                                     v84);
  if ( VolumeFriendlyNameForPublisher >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      v8 = *((unsigned int *)this + 92);
      if ( i >= (unsigned int)v8 )
        break;
      v9 = *((_QWORD *)this + 27);
      v10 = 368LL * i;
      if ( *(_QWORD *)(v10 + v9 + 40) )
      {
        VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                           v10 + v9 + 68,
                                           *(unsigned int *)(v10 + v9 + 84),
                                           2,
                                           pv);
        if ( VolumeFriendlyNameForPublisher < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 624, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          }
          v5 = pv[0];
          goto LABEL_72;
        }
        v11 = *((_QWORD *)this + 27);
        v5 = pv[0];
        v12 = *(struct _GUID *)(v10 + v11 + 68);
        v13 = *(_QWORD *)(v10 + v11 + 40);
        v78 = v12;
        VolumeFriendlyNameForPublisher = PublishBadClustersEvent(&v78, (unsigned __int16 *)pv[0], v13);
        if ( VolumeFriendlyNameForPublisher < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 625, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          }
          goto LABEL_72;
        }
        CoTaskMemFree(v5);
        v5 = 0;
        pv[0] = 0;
      }
    }
    v14 = *(_OWORD *)((char *)this + 296);
    v82 = *((_DWORD *)this + 58);
    v83 = *((_DWORD *)this + 59);
    v109[3] = *((unsigned __int8 *)this + 390);
    v15 = ~*((_BYTE *)this + 384);
    cb[0] = v8;
    v109[5] = v15 & 1;
    v81 = v14;
    v16 = CoTaskMemAlloc(8 * v8);
    *(_QWORD *)&cb[1] = v16;
    if ( !v16 )
      goto LABEL_23;
    memset_0(v16, 0, 8LL * cb[0]);
    v17 = (unsigned __int16 **)CoTaskMemAlloc(8LL * cb[0]);
    v87 = v17;
    if ( !v17 )
      goto LABEL_23;
    memset_0(v17, 0, 8LL * cb[0]);
    v18 = CoTaskMemAlloc(4LL * cb[0]);
    v96 = v18;
    if ( !v18 )
      goto LABEL_23;
    memset_0(v18, 0, 4LL * cb[0]);
    v19 = CoTaskMemAlloc(4LL * cb[0]);
    v88 = v19;
    if ( !v19 )
      goto LABEL_23;
    memset_0(v19, 0, 4LL * cb[0]);
    v20 = CoTaskMemAlloc(4LL * cb[0]);
    v89 = v20;
    if ( !v20 )
      goto LABEL_23;
    memset_0(v20, 0, 4LL * cb[0]);
    v21 = CoTaskMemAlloc(4LL * cb[0]);
    v98 = v21;
    if ( !v21 )
      goto LABEL_23;
    memset_0(v21, 0, 4LL * cb[0]);
    v22 = CoTaskMemAlloc(8LL * cb[0]);
    v90 = v22;
    if ( !v22 )
      goto LABEL_23;
    memset_0(v22, 0, 8LL * cb[0]);
    v23 = CoTaskMemAlloc(8LL * cb[0]);
    v94 = v23;
    if ( !v23 )
      goto LABEL_23;
    memset_0(v23, 0, 4LL * cb[0]);
    v24 = CoTaskMemAlloc(8LL * cb[0]);
    v95 = v24;
    if ( !v24 )
      goto LABEL_23;
    memset_0(v24, 0, 8LL * cb[0]);
    v25 = CoTaskMemAlloc(8LL * cb[0]);
    v92 = v25;
    if ( !v25 )
      goto LABEL_23;
    memset_0(v25, 0, 4LL * cb[0]);
    v26 = CoTaskMemAlloc(8LL * cb[0]);
    v91 = v26;
    if ( !v26 )
      goto LABEL_23;
    memset_0(v26, 0, 8LL * cb[0]);
    v27 = CoTaskMemAlloc(4LL * cb[0]);
    v97 = v27;
    if ( !v27 )
      goto LABEL_23;
    memset_0(v27, 0, 4LL * cb[0]);
    v28 = CoTaskMemAlloc(8LL * cb[0]);
    v93 = v28;
    if ( !v28 )
      goto LABEL_23;
    memset_0(v28, 0, 8LL * cb[0]);
    v29 = CoTaskMemAlloc(8LL * cb[0]);
    v112 = v29;
    if ( !v29 )
      goto LABEL_23;
    memset_0(v29, 0, 8LL * cb[0]);
    v30 = CoTaskMemAlloc(8LL * cb[0]);
    v113 = v30;
    if ( !v30 )
      goto LABEL_23;
    memset_0(v30, 0, 8LL * cb[0]);
    v31 = CoTaskMemAlloc(8LL * cb[0]);
    v114 = v31;
    if ( !v31 )
      goto LABEL_23;
    memset_0(v31, 0, 8LL * cb[0]);
    v32 = CoTaskMemAlloc(8LL * cb[0]);
    v115 = v32;
    if ( !v32 )
      goto LABEL_23;
    memset_0(v32, 0, 8LL * cb[0]);
    v33 = CoTaskMemAlloc(8LL * cb[0]);
    v116 = v33;
    if ( !v33 )
      goto LABEL_23;
    memset_0(v33, 0, 8LL * cb[0]);
    v34 = CoTaskMemAlloc(8LL * cb[0]);
    v117 = v34;
    if ( !v34 )
      goto LABEL_23;
    memset_0(v34, 0, 8LL * cb[0]);
    v35 = CoTaskMemAlloc(8LL * cb[0]);
    v118 = v35;
    if ( !v35 )
      goto LABEL_23;
    memset_0(v35, 0, 8LL * cb[0]);
    v36 = CoTaskMemAlloc(8LL * cb[0]);
    v119 = v36;
    if ( !v36 )
      goto LABEL_23;
    memset_0(v36, 0, 8LL * cb[0]);
    v37 = CoTaskMemAlloc(cb[0]);
    v99 = v37;
    if ( !v37 )
      goto LABEL_23;
    memset_0(v37, 0, cb[0]);
    v38 = CoTaskMemAlloc(cb[0]);
    v100 = v38;
    if ( !v38 )
      goto LABEL_23;
    memset_0(v38, 0, cb[0]);
    v39 = CoTaskMemAlloc(cb[0]);
    v101 = v39;
    if ( !v39 )
      goto LABEL_23;
    memset_0(v39, 0, cb[0]);
    v40 = CoTaskMemAlloc(cb[0]);
    v102 = v40;
    if ( !v40 )
      goto LABEL_23;
    memset_0(v40, 0, cb[0]);
    v41 = CoTaskMemAlloc(4LL * cb[0]);
    v103 = v41;
    if ( !v41 )
      goto LABEL_23;
    memset_0(v41, 0, 4LL * cb[0]);
    v42 = CoTaskMemAlloc(4LL * cb[0]);
    v104 = v42;
    if ( !v42 )
      goto LABEL_23;
    memset_0(v42, 0, 4LL * cb[0]);
    for ( j = 0; (unsigned int)j < cb[0]; j = (unsigned int)(j + 1) )
    {
      v44 = 368LL * (unsigned int)j;
      VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                         v44 + *((_QWORD *)this + 27) + 68LL,
                                         *(unsigned int *)(*((_QWORD *)this + 27) + v44 + 84),
                                         2,
                                         *(_QWORD *)&cb[1] + 8 * j);
      if ( VolumeFriendlyNameForPublisher < 0 )
        goto LABEL_72;
      VolumeFriendlyNameForPublisher = BlbutilDuplicateString(
                                         *(const unsigned __int16 **)(*((_QWORD *)this + 27) + v44 + 88),
                                         &v87[j],
                                         0);
      if ( VolumeFriendlyNameForPublisher < 0 )
        goto LABEL_72;
      v96[j] = *(_DWORD *)(*((_QWORD *)this + 27) + v44 + 20);
      v88[j] = *(_DWORD *)(*((_QWORD *)this + 27) + v44 + 32);
      v89[j] = *(_DWORD *)(*((_QWORD *)this + 27) + v44 + 36);
      v98[j] = *(_DWORD *)(*((_QWORD *)this + 27) + v44 + 28);
      v90[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 8);
      v91[j] = *(_QWORD *)(v44 + *((_QWORD *)this + 27));
      v93[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 40);
      v94[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 48);
      v95[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 56);
      v97[j] = *(_DWORD *)(*((_QWORD *)this + 27) + v44 + 84);
      v99[j] = *(_BYTE *)(*((_QWORD *)this + 27) + v44 + 104);
      v100[j] = *(_BYTE *)(*((_QWORD *)this + 27) + v44 + 132);
      v101[j] = *(_BYTE *)(*((_QWORD *)this + 27) + v44 + 345);
      v102[j] = *(_BYTE *)(*((_QWORD *)this + 27) + v44 + 346);
      v103[j] = *(_DWORD *)(*((_QWORD *)this + 27) + v44 + 360);
      v104[j] = *(_DWORD *)(*((_QWORD *)this + 27) + v44 + 364);
      v112[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 140);
      v113[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 148);
      v114[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 156);
      v115[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 164);
      v116[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 172);
      v117[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 180);
      v118[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 188);
      v119[j] = *(_QWORD *)(*((_QWORD *)this + 27) + v44 + 196);
      v45 = *((_QWORD *)this + 27);
      v46 = *(_DWORD *)(v45 + v44 + 32);
      if ( v46 < 0 && *(_BYTE *)(v45 + v44 + 104) && *((int *)this + 82) >= 0 )
      {
        if ( v46 == -2139618939 )
        {
          v47 = -2139618939;
          v46 = -2139618937;
        }
        else
        {
          v47 = *(_DWORD *)(v45 + v44 + 36);
        }
        *((_DWORD *)this + 82) = v46;
        *((_DWORD *)this + 83) = v47;
        *((_DWORD *)this + 81) = 2;
      }
      v48 = *(CBlbFileBackupAsync **)(v45 + v44 + 216);
      if ( v48 )
      {
        FreeVolumeBackupStatus((struct _BLB_VOLUME_BACKUP_STATUS *)v79);
        VolumeFriendlyNameForPublisher = CBlbFileBackupAsync::QueryStatus(v48, (struct _BLB_VOLUME_BACKUP_STATUS *)v79);
        if ( VolumeFriendlyNameForPublisher < 0 )
          goto LABEL_72;
        v92[j] = v80;
      }
      else
      {
        v92[j] = 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_LLLdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)v89[j],
          (unsigned __int8)v99[j],
          (unsigned int)v88[j],
          v89[j],
          v97[j],
          (unsigned __int8)v100[j],
          (unsigned __int8)v99[j]);
      }
    }
    v124 = *((_DWORD *)this + 172);
    v49 = CoTaskMemAlloc(8LL * v124);
    v125 = v49;
    if ( !v49 || (memset_0(v49, 0, 8LL * v124), v51 = CoTaskMemAlloc(8LL * v124), (v126 = v51) == 0) )
    {
      VolumeFriendlyNameForPublisher = -2147024882;
      goto LABEL_72;
    }
    memset_0(v51, 0, 8LL * v124);
    for ( k = 0; (unsigned int)k < v124; k = (unsigned int)(k + 1) )
    {
      v53 = (_QWORD *)ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::operator[](
                        (char *)this + 680,
                        (unsigned int)k);
      v125[k] = *v53;
      v54 = *(_QWORD *)(ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::operator[](
                          (char *)this + 680,
                          (unsigned int)k)
                      + 8);
      v126[k] = v54;
    }
    v85 = *((_DWORD *)this + 164);
    v55 = CoTaskMemAlloc(8LL * v85);
    v122 = v55;
    if ( !v55 || (memset_0(v55, 0, 8LL * v85), v56 = CoTaskMemAlloc(8LL * v85), (v123 = v56) == 0) )
    {
LABEL_23:
      VolumeFriendlyNameForPublisher = -2147024882;
      goto LABEL_72;
    }
    memset_0(v56, 0, 8LL * v85);
    for ( m = 0; (unsigned int)m < v85; m = (unsigned int)(m + 1) )
    {
      v58 = (_QWORD *)ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::operator[](
                        (char *)this + 648,
                        (unsigned int)m);
      v122[m] = *v58;
      v59 = *(_QWORD *)(ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::operator[](
                          (char *)this + 648,
                          (unsigned int)m)
                      + 8);
      v123[m] = v59;
    }
    v60 = *((_DWORD *)this + 80);
    v105 = *((_QWORD *)this + 49);
    v106 = *((_DWORD *)this + 8);
    v107 = *((_DWORD *)this + 9);
    v109[4] = v60 == 1;
    v132 = *((unsigned __int8 *)this + 389);
    if ( (_BYTE)v132 || v60 == 1 )
    {
      v109[1] = *((_DWORD *)this + 82);
      v109[2] = *((_DWORD *)this + 83);
    }
    v133 = *((unsigned __int8 *)this + 390);
    if ( (_BYTE)v133 )
      CBlbSystemStateBackupAsync::GetError(*((CBlbSystemStateBackupAsync **)this + 103), &v108, v109);
    v61 = &String1;
    v136 = *((_DWORD *)this + 96);
    v62 = &String1;
    if ( *((_QWORD *)this + 131) )
      v62 = (const unsigned __int16 *)*((_QWORD *)this + 131);
    VolumeFriendlyNameForPublisher = BlbutilDuplicateString(v62, &v134, 0);
    if ( VolumeFriendlyNameForPublisher >= 0 )
    {
      if ( *((_QWORD *)this + 132) )
        v61 = (const unsigned __int16 *)*((_QWORD *)this + 132);
      VolumeFriendlyNameForPublisher = BlbutilDuplicateString(v61, &v135, 0);
      if ( VolumeFriendlyNameForPublisher >= 0 )
      {
        v63 = (CBlbComponentBackupHelper *)*((_QWORD *)this + 101);
        v110 = *((_QWORD *)this + 77);
        v111 = *((_QWORD *)this + 78);
        v120 = *((_QWORD *)this + 79);
        v121 = *((_QWORD *)this + 80);
        VolumeFriendlyNameForPublisher = CBlbComponentBackupHelper::FillComponentStatus(v63, &v127, &v128);
        if ( VolumeFriendlyNameForPublisher < 0 )
        {
          v64 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_72;
          }
          v65 = 627;
          goto LABEL_102;
        }
        if ( *((_BYTE *)this + 391) )
        {
          VolumeFriendlyNameForPublisher = CBlbApplicationBackupAsync::FillComponentStatus(
                                             *((CBlbApplicationBackupAsync **)this + 104),
                                             &v129,
                                             v130);
          if ( VolumeFriendlyNameForPublisher < 0 )
          {
            v64 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_72;
            }
            v65 = 628;
            goto LABEL_102;
          }
          VolumeFriendlyNameForPublisher = CBlbBackupAsync::WriteAppBackupResultToLogFile(this, v129, v130[0]);
          if ( VolumeFriendlyNameForPublisher < 0 )
          {
            v64 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_72;
            }
            v65 = 629;
LABEL_102:
            WPP_SF_d(v64[2], v65, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            goto LABEL_72;
          }
        }
        v66 = (CBlbSystemStateBackupAsync *)*((_QWORD *)this + 103);
        if ( v66 )
        {
          *(_OWORD *)pv = 0;
          v78 = 0;
          CBlbSystemStateBackupAsync::GetSSBTimes(v66, (struct BLB_TIME_EXTENT *)pv, (struct BLB_TIME_EXTENT *)&v78);
          v130[1] = (struct _BLB_BACKUP_COMPONENT_STATUS *)pv[0];
          v130[2] = (struct _BLB_BACKUP_COMPONENT_STATUS *)pv[1];
          v130[3] = *((struct _BLB_BACKUP_COMPONENT_STATUS **)this + 89);
          v130[4] = *((struct _BLB_BACKUP_COMPONENT_STATUS **)this + 90);
          v131 = v78;
        }
        if ( a2 < 0 )
        {
          if ( a2 == -2139619299 || a2 == -2139618969 )
          {
            v75 = &BACKUP_CANCELED_EVENT;
LABEL_140:
            PublishBackupStopEvent((struct _BLB_BACKUP_STOP_EVENT_INFO *)&v81, v75);
          }
          else if ( !a3 )
          {
            PublishBackupGenericFailEvent((struct _BLB_BACKUP_STOP_EVENT_INFO *)&v81);
          }
        }
        else
        {
          v67 = *((_DWORD *)this + 92);
          v68 = 0;
          v69 = 1;
          if ( v67 )
          {
            v70 = *((_QWORD *)this + 27);
            v71 = 0;
            v72 = 0;
            do
            {
              v73 = 368 * v72;
              if ( *(_DWORD *)(368 * v72 + v70 + 20) == 14 && !*(_DWORD *)(v73 + v70 + 32)
                || (v69 = 0, *(_DWORD *)(v73 + v70 + 20) == 14) )
              {
                if ( *(char *)(v73 + v70 + 84) < 0 )
                  v68 = 1;
              }
              ++v71;
              ++v72;
            }
            while ( v71 < v67 );
          }
          for ( n = 0; (unsigned int)n < v129; n = (unsigned int)(n + 1) )
          {
            if ( *((_DWORD *)v130[0] + 36 * n) != 3 || *((_DWORD *)v130[0] + 36 * n + 1) )
              goto LABEL_133;
          }
          if ( v69 )
          {
            if ( !v68 )
            {
              v75 = (const struct _EVENT_DESCRIPTOR *)BACKUP_SUCCESS_EVENT;
              goto LABEL_140;
            }
            goto LABEL_134;
          }
LABEL_133:
          PublishPartialBackupFailedEvent((struct _BLB_BACKUP_STOP_EVENT_INFO *)&v81);
          if ( !v68 )
            goto LABEL_141;
LABEL_134:
          PublishBackupCompletedWithSkippedFiles((struct _BLB_BACKUP_STOP_EVENT_INFO *)&v81);
        }
LABEL_141:
        VolumeFriendlyNameForPublisher = PublishBackupStopEvent(
                                           (struct _BLB_BACKUP_STOP_EVENT_INFO *)&v81,
                                           &BACKUP_STOPPED_EVENT);
        if ( VolumeFriendlyNameForPublisher >= 0 )
          VolumeFriendlyNameForPublisher = PublishBackupSqmDatapoint(
                                             (CBlbBackupAsync *)((char *)this + 864),
                                             (struct _BLB_BACKUP_STOP_EVENT_INFO *)&v81,
                                             *((struct CBlbEngine **)this + 10),
                                             *((unsigned __int16 **)this + 43));
      }
    }
  }
LABEL_72:
  FreeBackupStopEventInfo((struct _BLB_BACKUP_STOP_EVENT_INFO *const)&v81);
  FreeVolumeBackupStatus((struct _BLB_VOLUME_BACKUP_STATUS *)v79);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 630, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)VolumeFriendlyNameForPublisher;
}

```

## disassembly

```asm
0x140031960  push    rbp
0x140031962  push    rbx
0x140031963  push    rsi
0x140031964  push    rdi
0x140031965  push    r12
0x140031967  push    r13
0x140031969  push    r14
0x14003196b  push    r15
0x14003196d  lea     rbp, [rsp-1E8h]
0x140031975  sub     rsp, 2E8h
0x14003197c  mov     rax, cs:__security_cookie
0x140031983  xor     rax, rsp
0x140031986  mov     [rbp+220h+var_50], rax
0x14003198d  mov     [rsp+320h+var_2E0], r8b
0x140031992  mov     r13d, edx
0x140031995  mov     rdi, rcx
0x140031998  mov     ebx, 1E8h
0x14003199d  mov     r8d, ebx; Size
0x1400319a0  lea     rcx, [rbp+220h+var_240]; void *
0x1400319a4  xor     edx, edx; Val
0x1400319a6  call    memset_0
0x1400319ab  xor     r15d, r15d
0x1400319ae  mov     [rsp+320h+pv], r15
0x1400319b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400319ba  lea     rsi, WPP_GLOBAL_Control
0x1400319c1  lea     r12d, [r15+1]
0x1400319c5  cmp     rcx, rsi
0x1400319c8  jz      short loc_1400319EB
0x1400319ca  test    [rcx+1Ch], r12b
0x1400319ce  jz      short loc_1400319EB
0x1400319d0  cmp     byte ptr [rcx+19h], 4
0x1400319d4  jb      short loc_1400319EB
0x1400319d6  mov     rcx, [rcx+10h]
0x1400319da  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400319e1  mov     edx, 26Fh
0x1400319e6  call    WPP_SF_
0x1400319eb  mov     r8, rbx; Size
0x1400319ee  lea     rcx, [rbp+220h+var_240]; void *
0x1400319f2  xor     edx, edx; Val
0x1400319f4  call    memset_0
0x1400319f9  xor     edx, edx; Val
0x1400319fb  lea     rcx, [rsp+320h+var_2B0]; void *
0x140031a00  lea     r8d, [rdx+70h]; Size
0x140031a04  call    memset_0
0x140031a09  mov     edx, [rdi+150h]
0x140031a0f  lea     r8, [rbp+220h+var_228]
0x140031a13  mov     rcx, [rdi+158h]
0x140031a1a  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAGW4_BLB_MEDIA_TYPE@@AEAPEAG@Z; GetVolumeFriendlyNameForPublisher(ushort *,_BLB_MEDIA_TYPE,ushort * &)
0x140031a1f  mov     ebx, eax
0x140031a21  test    eax, eax
0x140031a23  js      loc_1400323FB
0x140031a29  xor     r14d, r14d
0x140031a2c  mov     edx, [rdi+170h]
0x140031a32  cmp     r14d, edx
0x140031a35  jnb     loc_140031B4B
0x140031a3b  mov     rdx, [rdi+0D8h]
0x140031a42  mov     eax, r14d
0x140031a45  imul    rsi, rax, 170h
0x140031a4c  cmp     qword ptr [rsi+rdx+28h], 0
0x140031a52  jz      short loc_140031ABA
0x140031a54  lea     rcx, [rdx+44h]
0x140031a58  mov     r8d, 2
0x140031a5e  mov     edx, [rsi+rdx+54h]
0x140031a62  lea     r9, [rsp+320h+pv]
0x140031a67  add     rcx, rsi
0x140031a6a  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAU_GUID@@KW4_BLB_MEDIA_TYPE@@PEAPEAG@Z; GetVolumeFriendlyNameForPublisher(_GUID *,ulong,_BLB_MEDIA_TYPE,ushort * *)
0x140031a6f  mov     ebx, eax
0x140031a71  test    eax, eax
0x140031a73  js      loc_140031B0A
0x140031a79  mov     r8, [rdi+0D8h]
0x140031a80  lea     rcx, [rsp+320h+var_2C0]; struct _GUID
0x140031a85  mov     r15, [rsp+320h+pv]
0x140031a8a  mov     rdx, r15; unsigned __int16 *
0x140031a8d  movups  xmm0, xmmword ptr [rsi+r8+44h]
0x140031a93  mov     r8, [rsi+r8+28h]; __int64
0x140031a98  movdqu  xmmword ptr [rsp+320h+var_2C0.Data1], xmm0
0x140031a9e  call    ?PublishBadClustersEvent@@YAJU_GUID@@PEAG_J@Z; PublishBadClustersEvent(_GUID,ushort *,__int64)
0x140031aa3  mov     ebx, eax
0x140031aa5  test    eax, eax
0x140031aa7  js      short loc_140031AC2
0x140031aa9  mov     rcx, r15; pv
0x140031aac  call    cs:__imp_CoTaskMemFree
0x140031ab2  xor     r15d, r15d
0x140031ab5  mov     [rsp+320h+pv], r15
0x140031aba  add     r14d, r12d
0x140031abd  jmp     loc_140031A2C
0x140031ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x140031ac9  lea     rsi, WPP_GLOBAL_Control
0x140031ad0  cmp     rcx, rsi
0x140031ad3  jz      loc_1400323FB
0x140031ad9  test    [rcx+1Ch], r12b
0x140031add  jz      loc_1400323FB
0x140031ae3  cmp     byte ptr [rcx+19h], 2
0x140031ae7  jb      loc_1400323FB
0x140031aed  mov     rcx, [rcx+10h]
0x140031af1  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140031af8  mov     edx, 271h
0x140031afd  mov     r9d, eax
0x140031b00  call    WPP_SF_d
0x140031b05  jmp     loc_1400323FB
0x140031b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b11  lea     rsi, WPP_GLOBAL_Control
0x140031b18  cmp     rcx, rsi
0x140031b1b  jz      short loc_140031B41
0x140031b1d  test    [rcx+1Ch], r12b
0x140031b21  jz      short loc_140031B41
0x140031b23  cmp     byte ptr [rcx+19h], 2
0x140031b27  jb      short loc_140031B41
0x140031b29  mov     rcx, [rcx+10h]
0x140031b2d  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140031b34  mov     edx, 270h
0x140031b39  mov     r9d, eax
0x140031b3c  call    WPP_SF_d
0x140031b41  mov     r15, [rsp+320h+pv]
0x140031b46  jmp     loc_1400323FB
0x140031b4b  mov     eax, [rdi+0E8h]
0x140031b51  movups  xmm0, xmmword ptr [rdi+128h]
0x140031b58  mov     [rbp+220h+var_230], eax
0x140031b5b  mov     eax, [rdi+0ECh]
0x140031b61  mov     [rbp+220h+var_22C], eax
0x140031b64  movzx   eax, byte ptr [rdi+186h]
0x140031b6b  mov     [rbp+220h+var_160], eax
0x140031b71  mov     al, [rdi+180h]
0x140031b77  not     al
0x140031b79  mov     dword ptr [rbp+220h+cb], edx
0x140031b7c  movzx   ecx, al
0x140031b7f  and     ecx, r12d
0x140031b82  mov     [rbp+220h+var_158], ecx
0x140031b88  mov     rcx, rdx
0x140031b8b  shl     rcx, 3; cb
0x140031b8f  movdqu  [rbp+220h+var_240], xmm0
0x140031b94  call    cs:__imp_CoTaskMemAlloc
0x140031b9a  mov     qword ptr [rbp+220h+cb+4], rax
0x140031b9e  test    rax, rax
0x140031ba1  jnz     short loc_140031BAD
0x140031ba3  mov     ebx, 8007000Eh
0x140031ba8  jmp     loc_1400323F4
0x140031bad  mov     r8d, dword ptr [rbp+220h+cb]
0x140031bb1  xor     edx, edx; Val
0x140031bb3  shl     r8, 3; Size
0x140031bb7  mov     rcx, rax; void *
0x140031bba  call    memset_0
0x140031bbf  mov     ecx, dword ptr [rbp+220h+cb]
0x140031bc2  shl     rcx, 3; cb
0x140031bc6  call    cs:__imp_CoTaskMemAlloc
0x140031bcc  mov     [rbp+220h+var_210], rax
0x140031bd0  test    rax, rax
0x140031bd3  jz      short loc_140031BA3
0x140031bd5  mov     r8d, dword ptr [rbp+220h+cb]
0x140031bd9  xor     edx, edx; Val
0x140031bdb  shl     r8, 3; Size
0x140031bdf  mov     rcx, rax; void *
0x140031be2  call    memset_0
0x140031be7  mov     ecx, dword ptr [rbp+220h+cb]
0x140031bea  shl     rcx, 2; cb
0x140031bee  call    cs:__imp_CoTaskMemAlloc
0x140031bf4  mov     [rbp+220h+var_1C8], rax
0x140031bf8  test    rax, rax
0x140031bfb  jz      short loc_140031BA3
0x140031bfd  mov     r8d, dword ptr [rbp+220h+cb]
0x140031c01  xor     edx, edx; Val
0x140031c03  shl     r8, 2; Size
0x140031c07  mov     rcx, rax; void *
0x140031c0a  call    memset_0
0x140031c0f  mov     ecx, dword ptr [rbp+220h+cb]
0x140031c12  shl     rcx, 2; cb
0x140031c16  call    cs:__imp_CoTaskMemAlloc
0x140031c1c  mov     [rbp+220h+var_208], rax
0x140031c20  test    rax, rax
0x140031c23  jz      loc_140031BA3
0x140031c29  mov     r8d, dword ptr [rbp+220h+cb]
0x140031c2d  xor     edx, edx; Val
0x140031c2f  shl     r8, 2; Size
0x140031c33  mov     rcx, rax; void *
0x140031c36  call    memset_0
0x140031c3b  mov     ecx, dword ptr [rbp+220h+cb]
0x140031c3e  shl     rcx, 2; cb
0x140031c42  call    cs:__imp_CoTaskMemAlloc
0x140031c48  mov     [rbp+220h+var_200], rax
0x140031c4c  test    rax, rax
0x140031c4f  jz      loc_140031BA3
0x140031c55  mov     r8d, dword ptr [rbp+220h+cb]
0x140031c59  xor     edx, edx; Val
0x140031c5b  shl     r8, 2; Size
0x140031c5f  mov     rcx, rax; void *
0x140031c62  call    memset_0
0x140031c67  mov     ecx, dword ptr [rbp+220h+cb]
0x140031c6a  shl     rcx, 2; cb
0x140031c6e  call    cs:__imp_CoTaskMemAlloc
0x140031c74  mov     [rbp+220h+var_1B8], rax
0x140031c78  test    rax, rax
0x140031c7b  jz      loc_140031BA3
0x140031c81  mov     r8d, dword ptr [rbp+220h+cb]
0x140031c85  xor     edx, edx; Val
0x140031c87  shl     r8, 2; Size
0x140031c8b  mov     rcx, rax; void *
0x140031c8e  call    memset_0
0x140031c93  mov     ecx, dword ptr [rbp+220h+cb]
0x140031c96  shl     rcx, 3; cb
0x140031c9a  call    cs:__imp_CoTaskMemAlloc
0x140031ca0  mov     [rbp+220h+var_1F8], rax
0x140031ca4  test    rax, rax
0x140031ca7  jz      loc_140031BA3
0x140031cad  mov     r8d, dword ptr [rbp+220h+cb]
0x140031cb1  xor     edx, edx; Val
0x140031cb3  shl     r8, 3; Size
0x140031cb7  mov     rcx, rax; void *
0x140031cba  call    memset_0
0x140031cbf  mov     ecx, dword ptr [rbp+220h+cb]
0x140031cc2  shl     rcx, 3; cb
0x140031cc6  call    cs:__imp_CoTaskMemAlloc
0x140031ccc  mov     [rbp+220h+var_1D8], rax
0x140031cd0  test    rax, rax
0x140031cd3  jz      loc_140031BA3
0x140031cd9  mov     r8d, dword ptr [rbp+220h+cb]
0x140031cdd  xor     edx, edx; Val
0x140031cdf  shl     r8, 2; Size
0x140031ce3  mov     rcx, rax; void *
0x140031ce6  call    memset_0
0x140031ceb  mov     ecx, dword ptr [rbp+220h+cb]
0x140031cee  shl     rcx, 3; cb
0x140031cf2  call    cs:__imp_CoTaskMemAlloc
0x140031cf8  mov     [rbp+220h+var_1D0], rax
0x140031cfc  test    rax, rax
0x140031cff  jz      loc_140031BA3
0x140031d05  mov     r8d, dword ptr [rbp+220h+cb]
0x140031d09  xor     edx, edx; Val
0x140031d0b  shl     r8, 3; Size
0x140031d0f  mov     rcx, rax; void *
0x140031d12  call    memset_0
0x140031d17  mov     ecx, dword ptr [rbp+220h+cb]
0x140031d1a  shl     rcx, 3; cb
0x140031d1e  call    cs:__imp_CoTaskMemAlloc
0x140031d24  mov     [rbp+220h+var_1E8], rax
0x140031d28  test    rax, rax
0x140031d2b  jz      loc_140031BA3
0x140031d31  mov     r8d, dword ptr [rbp+220h+cb]
0x140031d35  xor     edx, edx; Val
0x140031d37  shl     r8, 2; Size
0x140031d3b  mov     rcx, rax; void *
0x140031d3e  call    memset_0
0x140031d43  mov     ecx, dword ptr [rbp+220h+cb]
0x140031d46  shl     rcx, 3; cb
0x140031d4a  call    cs:__imp_CoTaskMemAlloc
0x140031d50  mov     [rbp+220h+var_1F0], rax
0x140031d54  test    rax, rax
0x140031d57  jz      loc_140031BA3
0x140031d5d  mov     r8d, dword ptr [rbp+220h+cb]
0x140031d61  xor     edx, edx; Val
0x140031d63  shl     r8, 3; Size
0x140031d67  mov     rcx, rax; void *
0x140031d6a  call    memset_0
0x140031d6f  mov     ecx, dword ptr [rbp+220h+cb]
0x140031d72  shl     rcx, 2; cb
0x140031d76  call    cs:__imp_CoTaskMemAlloc
0x140031d7c  mov     [rbp+220h+var_1C0], rax
0x140031d80  test    rax, rax
0x140031d83  jz      loc_140031BA3
0x140031d89  mov     r8d, dword ptr [rbp+220h+cb]
0x140031d8d  xor     edx, edx; Val
0x140031d8f  shl     r8, 2; Size
0x140031d93  mov     rcx, rax; void *
0x140031d96  call    memset_0
0x140031d9b  mov     ecx, dword ptr [rbp+220h+cb]
0x140031d9e  shl     rcx, 3; cb
0x140031da2  call    cs:__imp_CoTaskMemAlloc
0x140031da8  mov     [rbp+220h+var_1E0], rax
0x140031dac  test    rax, rax
0x140031daf  jz      loc_140031BA3
0x140031db5  mov     r8d, dword ptr [rbp+220h+cb]
0x140031db9  xor     edx, edx; Val
0x140031dbb  shl     r8, 3; Size
0x140031dbf  mov     rcx, rax; void *
0x140031dc2  call    memset_0
0x140031dc7  mov     ecx, dword ptr [rbp+220h+cb]
0x140031dca  shl     rcx, 3; cb
0x140031dce  call    cs:__imp_CoTaskMemAlloc
0x140031dd4  mov     [rbp+220h+var_140], rax
0x140031ddb  test    rax, rax
0x140031dde  jz      loc_140031BA3
0x140031de4  mov     r8d, dword ptr [rbp+220h+cb]
0x140031de8  xor     edx, edx; Val
0x140031dea  shl     r8, 3; Size
0x140031dee  mov     rcx, rax; void *
0x140031df1  call    memset_0
0x140031df6  mov     ecx, dword ptr [rbp+220h+cb]
0x140031df9  shl     rcx, 3; cb
0x140031dfd  call    cs:__imp_CoTaskMemAlloc
0x140031e03  mov     [rbp+220h+var_138], rax
0x140031e0a  test    rax, rax
0x140031e0d  jz      loc_140031BA3
0x140031e13  mov     r8d, dword ptr [rbp+220h+cb]
0x140031e17  xor     edx, edx; Val
0x140031e19  shl     r8, 3; Size
0x140031e1d  mov     rcx, rax; void *
0x140031e20  call    memset_0
0x140031e25  mov     ecx, dword ptr [rbp+220h+cb]
0x140031e28  shl     rcx, 3; cb
0x140031e2c  call    cs:__imp_CoTaskMemAlloc
0x140031e32  mov     [rbp+220h+var_130], rax
  ... truncated ...
```
