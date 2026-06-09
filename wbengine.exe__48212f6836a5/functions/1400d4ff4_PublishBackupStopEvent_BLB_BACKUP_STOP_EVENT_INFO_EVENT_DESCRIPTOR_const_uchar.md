# PublishBackupStopEvent(_BLB_BACKUP_STOP_EVENT_INFO *,_EVENT_DESCRIPTOR const *,uchar)

- ea: `0x1400d4ff4`
- end: `0x1400d6019`
- name: `?PublishBackupStopEvent@@YAJPEAU_BLB_BACKUP_STOP_EVENT_INFO@@PEBU_EVENT_DESCRIPTOR@@E@Z`
- size: `4133`
- prototype: `__int64 __fastcall(struct _BLB_BACKUP_STOP_EVENT_INFO *, const struct _EVENT_DESCRIPTOR *, unsigned __int8)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400d4f1c`

## callees

- `0x1400063b4`
- `0x140006a64`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bfd8`
- `0x14000c248`
- `0x14000cbcc`
- `0x14001358c`
- `0x1400154f0`
- `0x140051e98`
- `0x1400d2664`
- `0x1400d2750`
- `0x1400d2cd4`
- `0x1400d3000`
- `0x1400d30b0`
- `0x1400d4ff4`
- `0x1400d6444`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1400d50da`
- `KERNEL32!RaiseException` at `0x1400d50da`
- `ole32!CoTaskMemAlloc` at `0x1400d52ba`
- `ole32!CoTaskMemAlloc` at `0x1400d56af`
- `ole32!CoTaskMemAlloc` at `0x1400d52ba`
- `ole32!CoTaskMemAlloc` at `0x1400d56af`
- `ole32!CoTaskMemFree` at `0x1400d54c7`
- `ole32!CoTaskMemFree` at `0x1400d5507`
- `ole32!CoTaskMemFree` at `0x1400d5531`
- `ole32!CoTaskMemFree` at `0x1400d5543`
- `ole32!CoTaskMemFree` at `0x1400d5551`
- `ole32!CoTaskMemFree` at `0x1400d5563`
- `ole32!CoTaskMemFree` at `0x1400d5575`
- `ole32!CoTaskMemFree` at `0x1400d5587`
- `ole32!CoTaskMemFree` at `0x1400d5599`
- `ole32!CoTaskMemFree` at `0x1400d55ab`
- `ole32!CoTaskMemFree` at `0x1400d55bd`
- `ole32!CoTaskMemFree` at `0x1400d55cf`
- `ole32!CoTaskMemFree` at `0x1400d55de`
- `ole32!CoTaskMemFree` at `0x1400d55ec`
- `ole32!CoTaskMemFree` at `0x1400d55fe`
- `ole32!CoTaskMemFree` at `0x1400d5610`
- `ole32!CoTaskMemFree` at `0x1400d5622`
- `ole32!CoTaskMemFree` at `0x1400d5634`
- `ole32!CoTaskMemFree` at `0x1400d5646`
- `ole32!CoTaskMemFree` at `0x1400d5658`
- `ole32!CoTaskMemFree` at `0x1400d5666`
- `ole32!CoTaskMemFree` at `0x1400d54c7`
- `ole32!CoTaskMemFree` at `0x1400d5507`
- `ole32!CoTaskMemFree` at `0x1400d5531`
- `ole32!CoTaskMemFree` at `0x1400d5543`
- `ole32!CoTaskMemFree` at `0x1400d5551`
- `ole32!CoTaskMemFree` at `0x1400d5563`
- `ole32!CoTaskMemFree` at `0x1400d5575`
- `ole32!CoTaskMemFree` at `0x1400d5587`
- `ole32!CoTaskMemFree` at `0x1400d5599`
- `ole32!CoTaskMemFree` at `0x1400d55ab`
- `ole32!CoTaskMemFree` at `0x1400d55bd`
- `ole32!CoTaskMemFree` at `0x1400d55cf`
- `ole32!CoTaskMemFree` at `0x1400d55de`
- `ole32!CoTaskMemFree` at `0x1400d55ec`
- `ole32!CoTaskMemFree` at `0x1400d55fe`
- `ole32!CoTaskMemFree` at `0x1400d5610`
- `ole32!CoTaskMemFree` at `0x1400d5622`
- `ole32!CoTaskMemFree` at `0x1400d5634`
- `ole32!CoTaskMemFree` at `0x1400d5646`
- `ole32!CoTaskMemFree` at `0x1400d5658`
- `ole32!CoTaskMemFree` at `0x1400d5666`

## string_xrefs

- `0x1400d5444`: `<VolumeInfoItem Name="%ws" OriginalAccessPath="%ws" State="%d" HResult="%d" DetailedHResult="%d" PreviousState="%d" IsCritical="%d" IsIncremental="%d" BlockLevel="%d" HasFiles="%d" HasSystemState="%d" IsCompacted="%d" IsPruned="%d" IsRecreateVhd="%d" FullBackupReason="%d" DataTransferred="%I64u" NumUnreadableBytes="%I64i" TotalSize="%I64u" TotalNoOfFiles="%I64u" Flags="%lu" BackupTypeDetermined="%d" SSBTotalNoOfFiles="%I64u" SSBTotalSizeOnDisk="%I64u" />`

## pseudocode

```c
__int64 __fastcall PublishBackupStopEvent(
        struct _BLB_BACKUP_STOP_EVENT_INFO *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int8 a3)
{
  unsigned int *v3; // r12
  struct _BLB_BACKUP_STOP_EVENT_INFO *v4; // rdi
  unsigned __int16 *v5; // r13
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // r15
  int v8; // eax
  int ErrorCodeStringForEvent; // ebx
  __int64 v10; // rsi
  __int64 v11; // rax
  void *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rbx
  const OLECHAR *v17; // rcx
  __int64 v18; // rax
  const OLECHAR *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // esi
  void *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // rax
  __int64 v28; // r12
  int v29; // r14d
  __int64 v30; // r8
  __int64 v31; // r10
  __int64 v32; // r11
  void *v33; // rdi
  int v34; // eax
  unsigned __int16 *v35; // r12
  unsigned int v36; // edi
  LPVOID *v37; // rax
  unsigned __int64 v39; // r14
  SIZE_T v40; // rbx
  unsigned __int16 *v41; // rax
  unsigned __int16 **v42; // rax
  __int64 v43; // rax
  int v44; // eax
  int TimesListString; // eax
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  unsigned __int16 *v57; // r15
  __int64 v58; // rax
  __int64 v59; // rax
  void *v60; // rcx
  __int64 v61; // rax
  void *v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  int ComponentBackupSummaryString; // eax
  __int64 v69; // [rsp+28h] [rbp-130h]
  __int64 v70; // [rsp+28h] [rbp-130h]
  __int64 v71; // [rsp+30h] [rbp-128h]
  __int64 v72; // [rsp+30h] [rbp-128h]
  __int64 v73; // [rsp+38h] [rbp-120h]
  __int64 v74; // [rsp+40h] [rbp-118h]
  __int64 v75; // [rsp+48h] [rbp-110h]
  __int64 v76; // [rsp+50h] [rbp-108h]
  __int64 v77; // [rsp+58h] [rbp-100h]
  __int64 v78; // [rsp+60h] [rbp-F8h]
  __int64 v79; // [rsp+68h] [rbp-F0h]
  __int64 v80; // [rsp+70h] [rbp-E8h]
  __int64 v81; // [rsp+78h] [rbp-E0h]
  __int64 v82; // [rsp+80h] [rbp-D8h]
  __int64 v83; // [rsp+88h] [rbp-D0h]
  __int64 v84; // [rsp+90h] [rbp-C8h]
  __int64 v85; // [rsp+B8h] [rbp-A0h]
  __int64 v86; // [rsp+C0h] [rbp-98h]
  unsigned __int16 *v87; // [rsp+D8h] [rbp-80h] BYREF
  void *v88; // [rsp+E0h] [rbp-78h] BYREF
  __int64 v89; // [rsp+E8h] [rbp-70h]
  unsigned __int16 *v90; // [rsp+F0h] [rbp-68h] BYREF
  unsigned __int16 *v91; // [rsp+F8h] [rbp-60h] BYREF
  void *v92[3]; // [rsp+100h] [rbp-58h] BYREF
  int v93; // [rsp+118h] [rbp-40h]
  unsigned int v94; // [rsp+120h] [rbp-38h]
  __int64 v95; // [rsp+128h] [rbp-30h]
  int v96; // [rsp+130h] [rbp-28h]
  int v97; // [rsp+134h] [rbp-24h]
  int v98; // [rsp+138h] [rbp-20h]
  unsigned __int16 *v99; // [rsp+140h] [rbp-18h] BYREF
  unsigned __int16 *v100; // [rsp+148h] [rbp-10h] BYREF
  unsigned __int16 *v101; // [rsp+150h] [rbp-8h] BYREF
  unsigned __int16 *v102; // [rsp+158h] [rbp+0h] BYREF
  unsigned __int16 *v103; // [rsp+160h] [rbp+8h] BYREF
  unsigned __int16 *v104; // [rsp+168h] [rbp+10h] BYREF
  unsigned __int16 *v105; // [rsp+170h] [rbp+18h] BYREF
  unsigned __int16 *v106; // [rsp+178h] [rbp+20h] BYREF
  unsigned __int16 *v107; // [rsp+180h] [rbp+28h] BYREF
  unsigned __int16 *v108; // [rsp+188h] [rbp+30h] BYREF
  unsigned __int16 *v109; // [rsp+190h] [rbp+38h] BYREF
  unsigned __int16 *v110; // [rsp+198h] [rbp+40h] BYREF
  unsigned __int16 *v111; // [rsp+1A0h] [rbp+48h] BYREF
  LPVOID v112; // [rsp+1A8h] [rbp+50h] BYREF
  unsigned __int16 *v113; // [rsp+1B0h] [rbp+58h] BYREF
  unsigned int v114; // [rsp+1B8h] [rbp+60h]
  int v115; // [rsp+1BCh] [rbp+64h]
  void *v116; // [rsp+1C0h] [rbp+68h] BYREF
  unsigned __int64 v117; // [rsp+1C8h] [rbp+70h]
  __int64 v118; // [rsp+1D0h] [rbp+78h]
  int v119; // [rsp+1D8h] [rbp+80h]
  LPVOID pv; // [rsp+1E0h] [rbp+88h] BYREF
  unsigned __int16 *v121; // [rsp+1E8h] [rbp+90h]
  const OLECHAR *v122; // [rsp+1F0h] [rbp+98h]
  const OLECHAR *v123; // [rsp+1F8h] [rbp+A0h]
  unsigned __int64 v124; // [rsp+200h] [rbp+A8h]
  unsigned int *v125; // [rsp+208h] [rbp+B0h]
  int v129; // [rsp+280h] [rbp+128h]

  v3 = (unsigned int *)((char *)a1 + 36);
  v4 = a1;
  v5 = 0;
  v6 = 0;
  v121 = 0;
  v7 = 0;
  v91 = 0;
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v99 = 0;
  v113 = 0;
  v107 = 0;
  v90 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v87 = 0;
  memset(v92, 0, sizeof(v92));
  v93 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  v125 = (unsigned int *)((char *)a1 + 36);
  if ( !*((_DWORD *)a1 + 9) && !*((_DWORD *)a1 + 98) )
  {
    BlbAssert("base\\stor\\blb\\blbevents\\publisher\\blbpublisher.cpp", 0x3B0u, "FALSE");
    RaiseException(0x80070057, 1u, 0, 0);
  }
  v88 = v4;
  v89 = 16;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  LODWORD(v89) = 4;
  v88 = (char *)v4 + 200;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  v88 = (char *)v4 + 204;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  ErrorCodeStringForEvent = GetErrorCodeStringForEvent(*((unsigned int *)v4 + 50), &v112);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_32;
  v10 = -1;
  v88 = v112;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)v112 + v11) );
  LODWORD(v89) = 2 * v11 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  LODWORD(v89) = 4;
  v88 = (char *)v4 + 16;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  LODWORD(v89) = 8;
  v88 = (char *)v4 + 192;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  v12 = (void *)*((_QWORD *)v4 + 3);
  v13 = -1;
  v88 = v12;
  do
    ++v13;
  while ( *((_WORD *)v12 + v13) );
  LODWORD(v89) = 2 * v13 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  v88 = v3;
  LODWORD(v89) = 4;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  v14 = 30;
  v15 = 0;
  v129 = 30;
  while ( 1 )
  {
    v94 = v15;
    if ( v15 >= *v3 )
      break;
    v16 = v15;
    v17 = &String1;
    v18 = *((_QWORD *)v4 + 5);
    v19 = &String1;
    v95 = v16;
    if ( *(_QWORD *)(v18 + 8 * v16) )
      v17 = *(const OLECHAR **)(v18 + 8 * v16);
    v20 = *((_QWORD *)v4 + 6);
    v123 = v17;
    if ( *(_QWORD *)(v20 + 8 * v16) )
      v19 = *(const OLECHAR **)(v20 + 8 * v16);
    v21 = -1;
    v122 = v19;
    do
      ++v21;
    while ( v17[v21] );
    do
      ++v10;
    while ( v19[v10] );
    v22 = (unsigned int)(v10 + 580 + v21);
    v23 = v22;
    v98 = v22;
    v124 = (unsigned int)v22;
    v24 = CoTaskMemAlloc(2 * v22);
    pv = v24;
    if ( !v24 )
    {
      v5 = v121;
      ErrorCodeStringForEvent = -2147024882;
      goto LABEL_30;
    }
    memset_0(v24, 0, v23);
    v25 = *((_QWORD *)v4 + 14);
    v26 = *((_QWORD *)v4 + 13);
    v7 = (unsigned __int16 *)*((_QWORD *)v4 + 11);
    v27 = *((_QWORD *)v4 + 19);
    v28 = *((_QWORD *)v4 + 10);
    v114 = *(_DWORD *)(*((_QWORD *)v4 + 16) + 4 * v16);
    v29 = *(unsigned __int8 *)(v27 + v16);
    v115 = *(unsigned __int8 *)(*((_QWORD *)v4 + 20) + v16);
    v96 = *(unsigned __int8 *)(*((_QWORD *)v4 + 21) + v16);
    v30 = *((_QWORD *)a1 + 17);
    v31 = *((_QWORD *)a1 + 8);
    v32 = *((_QWORD *)a1 + 7);
    v97 = (v114 >> 5) & 1;
    LODWORD(v86) = v29;
    LODWORD(v85) = v114;
    LODWORD(v84) = *(_DWORD *)(*((_QWORD *)a1 + 23) + 4 * v95);
    LODWORD(v83) = *(_DWORD *)(*((_QWORD *)a1 + 22) + 4 * v95);
    LODWORD(v82) = v115;
    LODWORD(v81) = v96;
    LODWORD(v80) = v97;
    LODWORD(v79) = (v114 >> 6) & 1;
    LODWORD(v78) = (v114 >> 3) & 1;
    LODWORD(v77) = (v114 >> 4) & 1;
    LODWORD(v76) = *(unsigned __int8 *)(*((_QWORD *)a1 + 18) + v95);
    LODWORD(v75) = *(_DWORD *)(v30 + 4 * v95);
    LODWORD(v74) = *(_DWORD *)(v31 + 4 * v95);
    v33 = pv;
    LODWORD(v73) = *(_DWORD *)(v32 + 4 * v95);
    LODWORD(v71) = *(_DWORD *)(*((_QWORD *)a1 + 15) + 4 * v95);
    v34 = StringCchPrintfW(
            (unsigned __int16 *)pv,
            v124,
            L"<VolumeInfoItem Name=\"%ws\" OriginalAccessPath=\"%ws\" State=\"%d\" HResult=\"%d\" DetailedHResult=\"%d\" P"
             "reviousState=\"%d\" IsCritical=\"%d\" IsIncremental=\"%d\" BlockLevel=\"%d\" HasFiles=\"%d\" HasSystemState"
             "=\"%d\" IsCompacted=\"%d\" IsPruned=\"%d\" IsRecreateVhd=\"%d\" FullBackupReason=\"%d\" DataTransferred=\"%"
             "I64u\" NumUnreadableBytes=\"%I64i\" TotalSize=\"%I64u\" TotalNoOfFiles=\"%I64u\" Flags=\"%lu\" BackupTypeDe"
             "termined=\"%d\" SSBTotalNoOfFiles=\"%I64u\" SSBTotalSizeOnDisk=\"%I64u\" />",
            v123,
            v122,
            v71,
            v73,
            v74,
            v75,
            v76,
            v77,
            v78,
            v79,
            v80,
            v81,
            v82,
            v83,
            v84,
            *(_QWORD *)(*((_QWORD *)a1 + 9) + 8 * v95),
            *(_QWORD *)(*((_QWORD *)a1 + 12) + 8 * v95),
            *(_QWORD *)(v28 + 8 * v95),
            *(_QWORD *)&v7[4 * v95],
            v85,
            v86,
            *(_QWORD *)(v26 + 8 * v95),
            *(_QWORD *)(v25 + 8 * v95));
    LODWORD(v7) = 0;
    ErrorCodeStringForEvent = v34;
    if ( v34 < 0 )
    {
      CoTaskMemFree(v33);
      v5 = 0;
      goto LABEL_30;
    }
    v14 = v98 + v129;
    v129 += v98;
    ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(
      &v116,
      &pv);
    v4 = a1;
    v15 = v94 + 1;
    v3 = v125;
    v10 = -1;
  }
  v39 = v14;
  v40 = 2LL * v14;
  v41 = (unsigned __int16 *)CoTaskMemAlloc(v40);
  v5 = v41;
  if ( !v41 )
  {
    ErrorCodeStringForEvent = -2147024882;
LABEL_30:
    v6 = v91;
LABEL_31:
    v7 = v90;
    goto LABEL_32;
  }
  memset_0(v41, 0, v40);
  ErrorCodeStringForEvent = StringCchCopyW(v5, v39, L"<VolumeInfo>");
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_30;
  while ( (unsigned int)v7 < v117 )
  {
    v42 = (unsigned __int16 **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                 &v116,
                                 (unsigned int)v7);
    ErrorCodeStringForEvent = StringCchCatW(v5, v39, *v42);
    if ( ErrorCodeStringForEvent < 0 )
      goto LABEL_30;
    LODWORD(v7) = (_DWORD)v7 + 1;
  }
  ErrorCodeStringForEvent = StringCchCatW(v5, v39, L"</VolumeInfo>");
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_30;
  v88 = v5;
  v43 = -1;
  do
    ++v43;
  while ( v5[v43] );
  LODWORD(v89) = 2 * v43 + 2;
  v44 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v44 < 0
    || (LODWORD(v89) = 8,
        v88 = (char *)v4 + 236,
        v44 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88),
        v44 < 0)
    || (v88 = (char *)v4 + 244,
        v44 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88),
        v44 < 0) )
  {
    ErrorCodeStringForEvent = v44;
    goto LABEL_30;
  }
  TimesListString = GetTimesListString(*((struct _FILETIME **)v4 + 32), *v3, &v91);
  v6 = v91;
  ErrorCodeStringForEvent = TimesListString;
  if ( TimesListString < 0 )
    goto LABEL_31;
  v88 = v91;
  v46 = -1;
  do
    ++v46;
  while ( v91[v46] );
  LODWORD(v89) = 2 * v46 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 33), *v3, &v100);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v88 = v100;
  v48 = -1;
  do
    ++v48;
  while ( v6[v48] );
  LODWORD(v89) = 2 * v48 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 34), *v3, &v101);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v49 = -1;
  v88 = v101;
  do
    ++v49;
  while ( v101[v49] );
  LODWORD(v89) = 2 * v49 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 35), *v3, &v102);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v50 = -1;
  v88 = v102;
  do
    ++v50;
  while ( v102[v50] );
  LODWORD(v89) = 2 * v50 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  LODWORD(v89) = 8;
  v88 = (char *)v4 + 320;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  v88 = (char *)v4 + 328;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 42), *((_DWORD *)v4 + 8), &v103);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v51 = -1;
  v88 = v103;
  do
    ++v51;
  while ( v103[v51] );
  LODWORD(v89) = 2 * v51 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 43), *((_DWORD *)v4 + 8), &v104);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v52 = -1;
  v88 = v104;
  do
    ++v52;
  while ( v104[v52] );
  LODWORD(v89) = 2 * v52 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 45), *((_DWORD *)v4 + 88), &v105);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v53 = -1;
  v88 = v105;
  do
    ++v53;
  while ( v105[v53] );
  LODWORD(v89) = 2 * v53 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 46), *((_DWORD *)v4 + 88), &v106);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v54 = -1;
  v88 = v106;
  do
    ++v54;
  while ( v106[v54] );
  LODWORD(v89) = 2 * v54 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  LODWORD(v89) = 4;
  v88 = (char *)v4 + 20;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = GetComponentStatusString(
                              *((_DWORD *)v4 + 94),
                              *((struct _BLB_COMPONENT_STATUS **)v4 + 48),
                              &v99);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v55 = -1;
  v88 = v99;
  do
    ++v55;
  while ( v99[v55] );
  LODWORD(v89) = 2 * v55 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = GetComponentInfoString(
                              a3,
                              *((_DWORD *)v4 + 98),
                              *((struct _BLB_BACKUP_COMPONENT_STATUS **)v4 + 50),
                              &v113);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v56 = -1;
  v88 = v113;
  do
    ++v56;
  while ( v113[v56] );
  LODWORD(v89) = 2 * v56 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  LODWORD(v89) = 8;
  v88 = (char *)v4 + 408;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  v88 = (char *)v4 + 416;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  v88 = (char *)v4 + 424;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  v88 = (char *)v4 + 432;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  v88 = (char *)v4 + 440;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  v88 = (char *)v4 + 448;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
    goto LABEL_181;
  ErrorCodeStringForEvent = BlbutilMemalloc((void **)&v107, 0x72u, 2u);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v57 = v107;
  LODWORD(v71) = *((_DWORD *)v4 + 53);
  LODWORD(v69) = *((_DWORD *)v4 + 52);
  ErrorCodeStringForEvent = StringCchPrintfW(
                              v107,
                              0x72u,
                              L"<SystemState IsPresent=\"%d\" HResult=\"%d\" DetailedHResult=\"%d\" />",
                              *((_DWORD *)v4 + 56) != 0,
                              v69,
                              v71);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  v88 = v57;
  v58 = -1;
  do
    ++v58;
  while ( v57[v58] );
  LODWORD(v89) = 2 * v58 + 2;
  v47 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v47 < 0 )
  {
LABEL_181:
    ErrorCodeStringForEvent = v47;
    goto LABEL_31;
  }
  ErrorCodeStringForEvent = BlbutilMemalloc((void **)&v90, 0x6Au, 2u);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_31;
  LODWORD(v72) = *((_DWORD *)v4 + 55);
  v7 = v90;
  LODWORD(v70) = *((_DWORD *)v4 + 54);
  ErrorCodeStringForEvent = StringCchPrintfW(
                              v90,
                              0x6Au,
                              L"<BMR IsPresent=\"%d\" HResult=\"%d\" DetailedHResult=\"%d\" />",
                              *((_DWORD *)v4 + 57) != 0,
                              v70,
                              v72);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_32;
  v88 = v7;
  v59 = -1;
  do
    ++v59;
  while ( v7[v59] );
  LODWORD(v89) = 2 * v59 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  LODWORD(v89) = 4;
  v88 = (char *)v4 + 232;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  v88 = (char *)v4 + 456;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  v88 = (char *)v4 + 460;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  v60 = (void *)*((_QWORD *)v4 + 58);
  v61 = -1;
  v88 = v60;
  do
    ++v61;
  while ( *((_WORD *)v60 + v61) );
  LODWORD(v89) = 2 * v61 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  v62 = (void *)*((_QWORD *)v4 + 59);
  v63 = -1;
  v88 = v62;
  do
    ++v63;
  while ( *((_WORD *)v62 + v63) );
  LODWORD(v89) = 2 * v63 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 36), *v3, &v108);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_32;
  v64 = -1;
  v88 = v108;
  do
    ++v64;
  while ( v108[v64] );
  LODWORD(v89) = 2 * v64 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 37), *v3, &v109);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_32;
  v65 = -1;
  v88 = v109;
  do
    ++v65;
  while ( v109[v65] );
  LODWORD(v89) = 2 * v65 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 38), *v3, &v110);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_32;
  v66 = -1;
  v88 = v110;
  do
    ++v66;
  while ( v110[v66] );
  LODWORD(v89) = 2 * v66 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0 )
    goto LABEL_180;
  ErrorCodeStringForEvent = GetTimesListString(*((struct _FILETIME **)v4 + 39), *v3, &v111);
  if ( ErrorCodeStringForEvent < 0 )
  {
LABEL_32:
    v35 = v87;
    goto LABEL_33;
  }
  v67 = -1;
  v88 = v111;
  do
    ++v67;
  while ( v111[v67] );
  LODWORD(v89) = 2 * v67 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
  if ( v8 < 0
    || (LODWORD(v89) = 4,
        v88 = (char *)v4 + 480,
        v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88),
        v8 < 0) )
  {
LABEL_180:
    ErrorCodeStringForEvent = v8;
    goto LABEL_32;
  }
  ComponentBackupSummaryString = GetComponentBackupSummaryString(
                                   a3,
                                   *((_DWORD *)v4 + 98),
                                   *((struct _BLB_BACKUP_COMPONENT_STATUS **)v4 + 50),
                                   &v87);
  v35 = v87;
  ErrorCodeStringForEvent = ComponentBackupSummaryString;
  if ( ComponentBackupSummaryString >= 0 )
  {
    v88 = v87;
    do
      ++v10;
    while ( v87[v10] );
    LODWORD(v89) = 2 * v10 + 2;
    ErrorCodeStringForEvent = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v92, &v88);
    if ( ErrorCodeStringForEvent >= 0 )
      ErrorCodeStringForEvent = PublishEvent(v92, a2);
  }
LABEL_33:
  v36 = 0;
  if ( v117 )
  {
    do
    {
      if ( *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                        &v116,
                        v36) )
      {
        v37 = (LPVOID *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                          &v116,
                          v36);
        CoTaskMemFree(*v37);
        *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                     &v116,
                     v36) = 0;
      }
      ++v36;
    }
    while ( v36 < v117 );
    v35 = v87;
  }
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v99 )
    CoTaskMemFree(v99);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v100 )
    CoTaskMemFree(v100);
  if ( v101 )
    CoTaskMemFree(v101);
  if ( v102 )
    CoTaskMemFree(v102);
  if ( v103 )
    CoTaskMemFree(v103);
  if ( v104 )
    CoTaskMemFree(v104);
  if ( v105 )
    CoTaskMemFree(v105);
  if ( v106 )
    CoTaskMemFree(v106);
  if ( v107 )
    CoTaskMemFree(v107);
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v108 )
    CoTaskMemFree(v108);
  if ( v109 )
    CoTaskMemFree(v109);
  if ( v110 )
    CoTaskMemFree(v110);
  if ( v111 )
    CoTaskMemFree(v111);
  if ( v112 )
    CoTaskMemFree(v112);
  if ( v113 )
    CoTaskMemFree(v113);
  if ( v35 )
    CoTaskMemFree(v35);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(&v116);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v92);
  return (unsigned int)ErrorCodeStringForEvent;
}

```

## disassembly

```asm
0x1400d4ff4  mov     rax, rsp
0x1400d4ff7  mov     [rax+18h], r8b
0x1400d4ffb  mov     [rax+10h], rdx
0x1400d4fff  mov     [rax+8], rcx
0x1400d5003  push    rbp
0x1400d5004  push    rbx
0x1400d5005  push    rsi
0x1400d5006  push    rdi
0x1400d5007  push    r12
0x1400d5009  push    r13
0x1400d500b  push    r14
0x1400d500d  push    r15
0x1400d500f  lea     rbp, [rax-108h]
0x1400d5016  sub     rsp, 218h
0x1400d501d  xor     ebx, ebx
0x1400d501f  lea     r12, [rcx+24h]
0x1400d5023  mov     rdi, rcx
0x1400d5026  mov     r13d, ebx
0x1400d5029  mov     r14d, ebx
0x1400d502c  mov     [rbp+100h+var_70], rbx
0x1400d5033  mov     r15d, ebx
0x1400d5036  mov     [rbp+100h+var_160], rbx
0x1400d503a  mov     [rbp+100h+var_110], rbx
0x1400d503e  mov     [rbp+100h+var_108], rbx
0x1400d5042  mov     [rbp+100h+var_100], rbx
0x1400d5046  mov     [rbp+100h+var_F8], rbx
0x1400d504a  mov     [rbp+100h+var_F0], rbx
0x1400d504e  mov     [rbp+100h+var_E8], rbx
0x1400d5052  mov     [rbp+100h+var_E0], rbx
0x1400d5056  mov     [rbp+100h+var_118], rbx
0x1400d505a  mov     [rbp+100h+var_A8], rbx
0x1400d505e  mov     [rbp+100h+var_D8], rbx
0x1400d5062  mov     [rbp+100h+var_168], rbx
0x1400d5066  mov     [rbp+100h+var_D0], rbx
0x1400d506a  mov     [rbp+100h+var_C8], rbx
0x1400d506e  mov     [rbp+100h+var_C0], rbx
0x1400d5072  mov     [rbp+100h+var_B8], rbx
0x1400d5076  mov     [rbp+100h+var_B0], rbx
0x1400d507a  mov     [rbp+100h+var_180], rbx
0x1400d507e  mov     [rbp+100h+var_158], rbx
0x1400d5082  mov     [rbp+100h+var_150], rbx
0x1400d5086  mov     [rbp+100h+var_148], rbx
0x1400d508a  mov     [rbp+100h+var_140], ebx
0x1400d508d  mov     [rbp+100h+var_98], rbx
0x1400d5091  mov     [rbp+100h+var_90], rbx
0x1400d5095  mov     [rbp+100h+var_88], rbx
0x1400d5099  mov     [rbp+100h+var_80], ebx
0x1400d509f  mov     [rbp+100h+var_50], r12
0x1400d50a6  cmp     [r12], ebx
0x1400d50aa  ja      short loc_1400D50E0
0x1400d50ac  cmp     [rcx+188h], ebx
0x1400d50b2  ja      short loc_1400D50E0
0x1400d50b4  lea     r8, aFalse_1; "FALSE"
0x1400d50bb  mov     edx, 3B0h; unsigned int
0x1400d50c0  lea     rcx, aBaseStorBlbBlb_1; "base\\stor\\blb\\blbevents\\publisher\\"...
0x1400d50c7  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400d50cc  xor     r9d, r9d; lpArguments
0x1400d50cf  lea     edx, [rbx+1]; dwExceptionFlags
0x1400d50d2  xor     r8d, r8d; nNumberOfArguments
0x1400d50d5  mov     ecx, 80070057h; dwExceptionCode
0x1400d50da  call    cs:__imp_RaiseException
0x1400d50e0  lea     rdx, [rbp+100h+var_178]
0x1400d50e4  mov     [rbp+100h+var_178], rdi
0x1400d50e8  lea     rcx, [rbp+100h+var_158]
0x1400d50ec  mov     [rbp+100h+var_170], 10h
0x1400d50f4  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d50f9  test    eax, eax
0x1400d50fb  js      loc_1400D6004
0x1400d5101  lea     rbx, [rdi+0C8h]
0x1400d5108  mov     dword ptr [rbp+100h+var_170], 4
0x1400d510f  lea     rdx, [rbp+100h+var_178]
0x1400d5113  mov     [rbp+100h+var_178], rbx
0x1400d5117  lea     rcx, [rbp+100h+var_158]
0x1400d511b  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d5120  test    eax, eax
0x1400d5122  js      loc_1400D6004
0x1400d5128  lea     rax, [rdi+0CCh]
0x1400d512f  lea     rdx, [rbp+100h+var_178]
0x1400d5133  mov     [rbp+100h+var_178], rax
0x1400d5137  lea     rcx, [rbp+100h+var_158]
0x1400d513b  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d5140  test    eax, eax
0x1400d5142  js      loc_1400D6004
0x1400d5148  mov     ecx, [rbx]
0x1400d514a  lea     rdx, [rbp+100h+var_B0]
0x1400d514e  call    GetErrorCodeStringForEvent
0x1400d5153  mov     ebx, eax
0x1400d5155  test    eax, eax
0x1400d5157  js      loc_1400D54D8
0x1400d515d  mov     rcx, [rbp+100h+var_B0]
0x1400d5161  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400d5165  mov     [rbp+100h+var_178], rcx
0x1400d5169  mov     rax, rsi
0x1400d516c  xor     ebx, ebx
0x1400d516e  inc     rax
0x1400d5171  cmp     [rcx+rax*2], bx
0x1400d5175  jnz     short loc_1400D516E
0x1400d5177  lea     eax, ds:2[rax*2]
0x1400d517e  lea     rdx, [rbp+100h+var_178]
0x1400d5182  mov     dword ptr [rbp+100h+var_170], eax
0x1400d5185  lea     rcx, [rbp+100h+var_158]
0x1400d5189  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d518e  test    eax, eax
0x1400d5190  js      loc_1400D6004
0x1400d5196  lea     rax, [rdi+10h]
0x1400d519a  mov     dword ptr [rbp+100h+var_170], 4
0x1400d51a1  lea     rdx, [rbp+100h+var_178]
0x1400d51a5  mov     [rbp+100h+var_178], rax
0x1400d51a9  lea     rcx, [rbp+100h+var_158]
0x1400d51ad  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d51b2  test    eax, eax
0x1400d51b4  js      loc_1400D6004
0x1400d51ba  lea     rax, [rdi+0C0h]
0x1400d51c1  mov     dword ptr [rbp+100h+var_170], 8
0x1400d51c8  lea     rdx, [rbp+100h+var_178]
0x1400d51cc  mov     [rbp+100h+var_178], rax
0x1400d51d0  lea     rcx, [rbp+100h+var_158]
0x1400d51d4  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d51d9  test    eax, eax
0x1400d51db  js      loc_1400D6004
0x1400d51e1  mov     rcx, [rdi+18h]
0x1400d51e5  mov     rax, rsi
0x1400d51e8  mov     [rbp+100h+var_178], rcx
0x1400d51ec  inc     rax
0x1400d51ef  cmp     [rcx+rax*2], bx
0x1400d51f3  jnz     short loc_1400D51EC
0x1400d51f5  lea     eax, ds:2[rax*2]
0x1400d51fc  lea     rdx, [rbp+100h+var_178]
0x1400d5200  mov     dword ptr [rbp+100h+var_170], eax
0x1400d5203  lea     rcx, [rbp+100h+var_158]
0x1400d5207  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d520c  test    eax, eax
0x1400d520e  js      loc_1400D6004
0x1400d5214  lea     rdx, [rbp+100h+var_178]
0x1400d5218  mov     [rbp+100h+var_178], r12
0x1400d521c  lea     rcx, [rbp+100h+var_158]
0x1400d5220  mov     dword ptr [rbp+100h+var_170], 4
0x1400d5227  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d522c  test    eax, eax
0x1400d522e  js      loc_1400D6004
0x1400d5234  mov     ebx, 1Eh
0x1400d5239  mov     eax, r15d
0x1400d523c  mov     [rbp+100h+arg_18], ebx
0x1400d5242  mov     [rbp+100h+var_138], eax
0x1400d5245  cmp     eax, [r12]
0x1400d5249  jnb     loc_1400D56A5
0x1400d524f  mov     ebx, eax
0x1400d5251  lea     rcx, String1
0x1400d5258  mov     rax, [rdi+28h]
0x1400d525c  lea     rdx, String1
0x1400d5263  mov     [rbp+100h+var_130], rbx
0x1400d5267  cmp     [rax+rbx*8], r15
0x1400d526b  cmovnz  rcx, [rax+rbx*8]
0x1400d5270  mov     rax, [rdi+30h]
0x1400d5274  mov     [rbp+100h+var_60], rcx
0x1400d527b  cmp     [rax+rbx*8], r15
0x1400d527f  cmovnz  rdx, [rax+rbx*8]
0x1400d5284  mov     rax, rsi
0x1400d5287  mov     [rbp+100h+var_68], rdx
0x1400d528e  inc     rax
0x1400d5291  cmp     [rcx+rax*2], r15w
0x1400d5296  jnz     short loc_1400D528E
0x1400d5298  inc     rsi
0x1400d529b  cmp     [rdx+rsi*2], r15w
0x1400d52a0  jnz     short loc_1400D5298
0x1400d52a2  add     esi, 244h
0x1400d52a8  add     eax, esi
0x1400d52aa  mov     esi, eax
0x1400d52ac  mov     [rbp+100h+var_120], eax
0x1400d52af  mov     [rbp+100h+var_58], rsi
0x1400d52b6  lea     rcx, [rax+rax]; cb
0x1400d52ba  call    cs:__imp_CoTaskMemAlloc
0x1400d52c0  mov     [rbp+100h+pv], rax
0x1400d52c7  test    rax, rax
0x1400d52ca  jz      loc_1400D5694
0x1400d52d0  mov     r8d, esi; Size
0x1400d52d3  xor     edx, edx; Val
0x1400d52d5  mov     rcx, rax; void *
0x1400d52d8  call    memset_0
0x1400d52dd  mov     rax, [rdi+80h]
0x1400d52e4  mov     rdx, [rdi+70h]
0x1400d52e8  mov     r9, [rdi+68h]
0x1400d52ec  mov     r15, [rdi+58h]
0x1400d52f0  mov     ecx, [rax+rbx*4]
0x1400d52f3  mov     r13d, ecx
0x1400d52f6  mov     rax, [rdi+98h]
0x1400d52fd  mov     esi, ecx
0x1400d52ff  mov     r12, [rdi+50h]
0x1400d5303  mov     [rbp+100h+var_A0], ecx
0x1400d5306  shr     r13d, 6
0x1400d530a  movzx   r14d, byte ptr [rax+rbx]
0x1400d530f  and     r13d, 1
0x1400d5313  mov     rax, [rdi+0A0h]
0x1400d531a  shr     esi, 3
0x1400d531d  and     esi, 1
0x1400d5320  movzx   eax, byte ptr [rax+rbx]
0x1400d5324  mov     [rbp+100h+var_9C], eax
0x1400d5327  mov     rax, [rdi+0A8h]
0x1400d532e  mov     edi, ecx
0x1400d5330  shr     edi, 4
0x1400d5333  movzx   eax, byte ptr [rax+rbx]
0x1400d5337  mov     rbx, [rbp+100h+arg_0]
0x1400d533e  mov     [rbp+100h+var_128], eax
0x1400d5341  mov     eax, ecx
0x1400d5343  mov     rcx, [rbp+100h+var_130]
0x1400d5347  shr     eax, 5
0x1400d534a  mov     r8, [rbx+88h]
0x1400d5351  and     eax, 1
0x1400d5354  mov     r10, [rbx+40h]
0x1400d5358  and     edi, 1
0x1400d535b  mov     r11, [rbx+38h]
0x1400d535f  mov     [rbp+100h+var_124], eax
0x1400d5362  mov     rax, [rbx+90h]
0x1400d5369  mov     rbx, [rbx+78h]
0x1400d536d  movzx   ecx, byte ptr [rax+rcx]
0x1400d5371  mov     rax, [rbp+100h+var_130]
0x1400d5375  mov     rax, [rdx+rax*8]
0x1400d5379  mov     [rsp+0C8h], rax
0x1400d5381  mov     rdx, [rbp+100h+arg_0]
0x1400d5388  mov     rax, [rbp+100h+var_130]
0x1400d538c  mov     rax, [r9+rax*8]
0x1400d5390  mov     r9, [rbp+100h+var_130]
0x1400d5394  mov     [rsp+250h+var_190], rax
0x1400d539c  mov     eax, [rbp+100h+var_A0]
0x1400d539f  mov     dword ptr [rsp+250h+var_198], r14d
0x1400d53a7  mov     dword ptr [rsp+250h+var_1A0], eax
0x1400d53ae  mov     rax, [r15+r9*8]
0x1400d53b2  mov     qword ptr [rsp+250h+var_1A8], rax
0x1400d53ba  mov     rax, [r12+r9*8]
0x1400d53be  mov     [rsp+250h+var_1B0], rax
0x1400d53c6  mov     rax, [rdx+60h]
0x1400d53ca  mov     rax, [rax+r9*8]
0x1400d53ce  mov     [rsp+250h+var_1B8], rax
0x1400d53d6  mov     rax, [rdx+48h]
0x1400d53da  mov     rax, [rax+r9*8]
0x1400d53de  mov     [rsp+250h+var_1C0], rax
0x1400d53e6  mov     rax, [rdx+0B8h]
0x1400d53ed  mov     eax, [rax+r9*4]
0x1400d53f1  mov     dword ptr [rsp+250h+var_1C8], eax
0x1400d53f8  mov     rax, [rdx+0B0h]
0x1400d53ff  mov     eax, [rax+r9*4]
0x1400d5403  mov     dword ptr [rsp+250h+var_1D0], eax
0x1400d540a  mov     eax, [rbp+100h+var_9C]
0x1400d540d  mov     dword ptr [rsp+250h+var_1D8], eax
0x1400d5411  mov     eax, [rbp+100h+var_128]
0x1400d5414  mov     dword ptr [rsp+250h+var_1E0], eax
0x1400d5418  mov     eax, [rbp+100h+var_124]
0x1400d541b  mov     dword ptr [rsp+250h+var_1E8], eax
0x1400d541f  mov     eax, [r8+r9*4]
0x1400d5423  mov     dword ptr [rsp+250h+var_1F0], r13d
0x1400d5428  mov     dword ptr [rsp+250h+var_1F8], esi
0x1400d542c  mov     dword ptr [rsp+250h+var_200], edi
0x1400d5430  mov     dword ptr [rsp+250h+var_208], ecx
0x1400d5434  mov     dword ptr [rsp+250h+var_210], eax
0x1400d5438  mov     eax, [r10+r9*4]
0x1400d543c  mov     dword ptr [rsp+250h+var_218], eax
0x1400d5440  mov     eax, [r11+r9*4]
0x1400d5444  lea     r8, aVolumeinfoitem_0; "<VolumeInfoItem Name=\"%ws\" OriginalAc"...
0x1400d544b  mov     rdi, [rbp+100h+pv]
0x1400d5452  mov     rdx, [rbp+100h+var_58]; unsigned __int64
0x1400d5459  mov     rcx, rdi; unsigned __int16 *
0x1400d545c  mov     dword ptr [rsp+250h+var_220], eax
0x1400d5460  mov     eax, [rbx+r9*4]
0x1400d5464  mov     r9, [rbp+100h+var_60]
0x1400d546b  mov     dword ptr [rsp+250h+var_228], eax
0x1400d546f  mov     rax, [rbp+100h+var_68]
0x1400d5476  mov     [rsp+250h+var_230], rax
0x1400d547b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400d5480  xor     r15d, r15d
0x1400d5483  mov     ebx, eax
0x1400d5485  test    eax, eax
0x1400d5487  js      short loc_1400D54C4
0x1400d5489  mov     ebx, [rbp+100h+arg_18]
0x1400d548f  lea     rdx, [rbp+100h+pv]
0x1400d5496  add     ebx, [rbp+100h+var_120]
0x1400d5499  lea     rcx, [rbp+100h+var_98]
0x1400d549d  mov     [rbp+100h+arg_18], ebx
0x1400d54a3  call    ?Add@?$CAtlArray@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@@2@@ATL@@QEAA_KAEBQEAV?$CComObject@VCBlbComponentRestoreContext@@@2@@Z; ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(ATL::CComObject<CBlbComponentRestoreContext> * const &)
0x1400d54a8  mov     eax, [rbp+100h+var_138]
0x1400d54ab  mov     rdi, [rbp+100h+arg_0]
0x1400d54b2  inc     eax
0x1400d54b4  mov     r12, [rbp+100h+var_50]
0x1400d54bb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400d54bf  jmp     loc_1400D5242
0x1400d54c4  mov     rcx, rdi; pv
0x1400d54c7  call    cs:__imp_CoTaskMemFree
0x1400d54cd  mov     r13, r15
0x1400d54d0  mov     r14, [rbp+100h+var_160]
0x1400d54d4  mov     r15, [rbp+100h+var_168]
0x1400d54d8  mov     r12, [rbp+100h+var_180]
0x1400d54dc  xor     edi, edi
0x1400d54de  cmp     [rbp+100h+var_90], rdi
0x1400d54e2  jbe     short loc_1400D5529
0x1400d54e4  xor     r12d, r12d
0x1400d54e7  mov     edx, edi
0x1400d54e9  lea     rcx, [rbp+100h+var_98]
0x1400d54ed  mov     esi, edi
0x1400d54ef  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400d54f4  cmp     [rax], r12
0x1400d54f7  jz      short loc_1400D551B
  ... truncated ...
```
