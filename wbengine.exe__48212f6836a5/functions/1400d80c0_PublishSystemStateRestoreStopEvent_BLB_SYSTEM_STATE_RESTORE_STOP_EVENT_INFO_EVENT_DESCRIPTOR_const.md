# PublishSystemStateRestoreStopEvent(_BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *,_EVENT_DESCRIPTOR const *)

- ea: `0x1400d80c0`
- end: `0x1400d88cc`
- name: `?PublishSystemStateRestoreStopEvent@@YAJPEAU_BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO@@PEBU_EVENT_DESCRIPTOR@@@Z`
- size: `2060`
- prototype: `__int64 __fastcall(struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `5`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400d7c08`
- `0x1400d7cc8`
- `0x1400d7d88`
- `0x1400d8000`
- `0x1400d88d4`

## callees

- `0x1400063b4`
- `0x140006a64`
- `0x140007ad3`
- `0x14000bfd8`
- `0x14000c248`
- `0x14001358c`
- `0x1400154f0`
- `0x140051e98`
- `0x1400d3000`
- `0x1400d6444`
- `0x1400d80c0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400d826d`
- `ole32!CoTaskMemAlloc` at `0x1400d82e6`
- `ole32!CoTaskMemAlloc` at `0x1400d83fb`
- `ole32!CoTaskMemAlloc` at `0x1400d84b7`
- `ole32!CoTaskMemAlloc` at `0x1400d826d`
- `ole32!CoTaskMemAlloc` at `0x1400d82e6`
- `ole32!CoTaskMemAlloc` at `0x1400d83fb`
- `ole32!CoTaskMemAlloc` at `0x1400d84b7`
- `ole32!CoTaskMemFree` at `0x1400d881d`
- `ole32!CoTaskMemFree` at `0x1400d8846`
- `ole32!CoTaskMemFree` at `0x1400d8866`
- `ole32!CoTaskMemFree` at `0x1400d8887`
- `ole32!CoTaskMemFree` at `0x1400d8895`
- `ole32!CoTaskMemFree` at `0x1400d881d`
- `ole32!CoTaskMemFree` at `0x1400d8846`
- `ole32!CoTaskMemFree` at `0x1400d8866`
- `ole32!CoTaskMemFree` at `0x1400d8887`
- `ole32!CoTaskMemFree` at `0x1400d8895`

## string_xrefs

- `0x1400d844f`: `<WriterInfoItem Name="%ws" HResult="%d" NumOfComponents="%d" NoOfFilesProcessed="%lld" NoOfFilesFailed="%lld" NoOfBytesProcessed="%lld" TotalNumOfBytes="%lld" />`
- `0x1400d84d9`: `<WriterInfo>`
- `0x1400d8524`: `</WriterInfo>`

## pseudocode

```c
__int64 __fastcall PublishSystemStateRestoreStopEvent(
        struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *a1,
        const struct _EVENT_DESCRIPTOR *a2)
{
  struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *v2; // rbx
  __int64 v4; // rcx
  unsigned __int16 *v5; // r13
  unsigned __int16 *v6; // r12
  int ErrorCodeStringForEvent; // edi
  int v8; // eax
  unsigned int *v9; // rdi
  unsigned int v10; // r15d
  unsigned int v11; // ebx
  __int64 v12; // r14
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rdi
  __int64 v17; // rbx
  SIZE_T v18; // rdi
  unsigned __int16 *v19; // rax
  unsigned int v20; // r15d
  unsigned __int16 **v21; // rax
  unsigned int v22; // r15d
  __int64 v23; // rax
  unsigned int *v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned int v28; // ebx
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // rax
  unsigned int v31; // r15d
  unsigned __int16 **v32; // rax
  __int64 v33; // rax
  struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *v34; // rcx
  __int64 v35; // rax
  struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *v36; // rcx
  __int64 v37; // rax
  struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *v38; // rcx
  __int64 v39; // rax
  struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *v40; // rcx
  __int64 v41; // rax
  struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  void *v45; // r15
  unsigned int v46; // esi
  LPVOID *v47; // rax
  _QWORD *v48; // rax
  unsigned int i; // esi
  LPVOID *v50; // rax
  _QWORD *v51; // rax
  __int64 v53; // [rsp+20h] [rbp-99h]
  __int64 v54; // [rsp+28h] [rbp-91h]
  struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *v55; // [rsp+50h] [rbp-69h] BYREF
  __int64 v56; // [rsp+58h] [rbp-61h]
  void *v57[3]; // [rsp+60h] [rbp-59h] BYREF
  int v58; // [rsp+78h] [rbp-41h]
  unsigned __int16 *v59; // [rsp+80h] [rbp-39h] BYREF
  void *v60; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int64 v61; // [rsp+90h] [rbp-29h]
  __int64 v62; // [rsp+98h] [rbp-21h]
  int v63; // [rsp+A0h] [rbp-19h]
  void *v64; // [rsp+A8h] [rbp-11h] BYREF
  unsigned __int64 v65; // [rsp+B0h] [rbp-9h]
  __int64 v66; // [rsp+B8h] [rbp-1h]
  int v67; // [rsp+C0h] [rbp+7h]
  unsigned __int64 v68; // [rsp+C8h] [rbp+Fh]
  unsigned int Size; // [rsp+120h] [rbp+67h]
  int Sizea; // [rsp+120h] [rbp+67h]
  int v72; // [rsp+130h] [rbp+77h]
  LPVOID pv; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 8);
  memset(v57, 0, sizeof(v57));
  v4 = *((unsigned int *)a1 + 2);
  v5 = 0;
  v6 = 0;
  v58 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  pv = 0;
  ErrorCodeStringForEvent = GetErrorCodeStringForEvent(v4, &pv);
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_75;
  v55 = a1;
  v56 = 8;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = v2;
  LODWORD(v56) = 4;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 12);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 16);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 20);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  LODWORD(v56) = 16;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 24);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  LODWORD(v56) = 8;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 40);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v9 = (unsigned int *)((char *)a1 + 48);
  LODWORD(v56) = 4;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 48);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v72 = 30;
  v10 = 30;
  v11 = 0;
  v12 = -1;
  while ( v11 < *v9 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)a1 + 7) + 8LL * v11) + 2 * v13) );
    v14 = (unsigned int)(v13 + 38);
    Size = v14;
    v15 = (unsigned __int16 *)CoTaskMemAlloc(2 * v14);
    v59 = v15;
    v16 = v15;
    if ( !v15 )
      goto LABEL_17;
    memset_0(v15, 0, Size);
    ErrorCodeStringForEvent = StringCchPrintfW(
                                v16,
                                Size,
                                L"<VolumeInfoItem Name=\"%ws\"/>",
                                *(_QWORD *)(*((_QWORD *)a1 + 7) + 8LL * v11));
    if ( ErrorCodeStringForEvent < 0 )
      goto LABEL_75;
    v10 += Size;
    ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(
      &v64,
      &v59);
    ++v11;
    v9 = (unsigned int *)((char *)a1 + 48);
  }
  v17 = v10;
  v18 = 2LL * v10;
  v19 = (unsigned __int16 *)CoTaskMemAlloc(v18);
  v20 = 0;
  v5 = v19;
  if ( !v19 )
  {
LABEL_17:
    ErrorCodeStringForEvent = -2147024882;
    goto LABEL_75;
  }
  memset_0(v19, 0, v18);
  ErrorCodeStringForEvent = StringCchCopyW(v5, (unsigned int)v17, L"<VolumeInfo>");
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_75;
  while ( v20 < v65 )
  {
    v21 = (unsigned __int16 **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                 &v64,
                                 v20);
    ErrorCodeStringForEvent = StringCchCatW(v5, v17, *v21);
    if ( ErrorCodeStringForEvent < 0 )
      goto LABEL_75;
    ++v20;
  }
  v22 = 0;
  ErrorCodeStringForEvent = StringCchCatW(v5, v17, L"</VolumeInfo>");
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_75;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)v5;
  v23 = -1;
  do
    ++v23;
  while ( v5[v23] );
  LODWORD(v56) = 2 * v23 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0
    || (v24 = (unsigned int *)((char *)a1 + 64),
        LODWORD(v56) = 4,
        v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 64),
        v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55),
        v8 < 0) )
  {
LABEL_74:
    ErrorCodeStringForEvent = v8;
LABEL_75:
    v45 = pv;
    goto LABEL_76;
  }
  v25 = 30;
  while ( v22 < *v24 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)a1 + 9) + 8LL * v22) + 2 * v26) );
    v27 = (unsigned int)(v26 + 1161);
    v28 = v27;
    Sizea = v27;
    v68 = (unsigned int)v27;
    v29 = (unsigned __int16 *)CoTaskMemAlloc(2 * v27);
    v59 = v29;
    if ( !v29 )
      goto LABEL_17;
    memset_0(v29, 0, v28);
    LODWORD(v54) = *(_DWORD *)(*((_QWORD *)a1 + 11) + 4LL * v22);
    LODWORD(v53) = *(_DWORD *)(*((_QWORD *)a1 + 10) + 4LL * v22);
    ErrorCodeStringForEvent = StringCchPrintfW(
                                v59,
                                v68,
                                L"<WriterInfoItem Name=\"%ws\" HResult=\"%d\" NumOfComponents=\"%d\" NoOfFilesProcessed=\""
                                 "%lld\" NoOfFilesFailed=\"%lld\" NoOfBytesProcessed=\"%lld\" TotalNumOfBytes=\"%lld\" />",
                                *(_QWORD *)(*((_QWORD *)a1 + 9) + 8LL * v22),
                                v53,
                                v54,
                                *(_QWORD *)(*((_QWORD *)a1 + 12) + 8LL * v22),
                                *(_QWORD *)(*((_QWORD *)a1 + 13) + 8LL * v22),
                                *(_QWORD *)(*((_QWORD *)a1 + 14) + 8LL * v22),
                                *(_QWORD *)(*((_QWORD *)a1 + 15) + 8LL * v22));
    if ( ErrorCodeStringForEvent < 0 )
      goto LABEL_75;
    v25 = (unsigned int)(Sizea + v72);
    v72 += Sizea;
    ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(
      &v60,
      &v59);
    ++v22;
    v24 = (unsigned int *)((char *)a1 + 64);
  }
  v30 = (unsigned __int16 *)CoTaskMemAlloc(2 * v25);
  v31 = 0;
  v6 = v30;
  if ( !v30 )
    goto LABEL_17;
  memset_0(v30, 0, 2 * v25);
  ErrorCodeStringForEvent = StringCchCopyW(v6, v25, L"<WriterInfo>");
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_75;
  while ( v31 < v61 )
  {
    v32 = (unsigned __int16 **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                 &v60,
                                 v31);
    ErrorCodeStringForEvent = StringCchCatW(v6, v25, *v32);
    if ( ErrorCodeStringForEvent < 0 )
      goto LABEL_75;
    ++v31;
  }
  ErrorCodeStringForEvent = StringCchCatW(v6, v25, L"</WriterInfo>");
  if ( ErrorCodeStringForEvent < 0 )
    goto LABEL_75;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)v6;
  v33 = -1;
  do
    ++v33;
  while ( v6[v33] );
  LODWORD(v56) = 2 * v33 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  LODWORD(v56) = 8;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 128);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 136);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 144);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 152);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 160);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 168);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 176);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 184);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 192);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 200);
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v34 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)*((_QWORD *)a1 + 26);
  v35 = -1;
  v55 = v34;
  do
    ++v35;
  while ( *((_WORD *)v34 + v35) );
  LODWORD(v56) = 2 * v35 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v36 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)*((_QWORD *)a1 + 27);
  v37 = -1;
  v55 = v36;
  do
    ++v37;
  while ( *((_WORD *)v36 + v37) );
  LODWORD(v56) = 2 * v37 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v38 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)*((_QWORD *)a1 + 28);
  v39 = -1;
  v55 = v38;
  do
    ++v39;
  while ( *((_WORD *)v38 + v39) );
  LODWORD(v56) = 2 * v39 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v40 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)*((_QWORD *)a1 + 29);
  v41 = -1;
  v55 = v40;
  do
    ++v41;
  while ( *((_WORD *)v40 + v41) );
  LODWORD(v56) = 2 * v41 + 2;
  v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( v8 < 0 )
    goto LABEL_74;
  v42 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)*((_QWORD *)a1 + 30);
  v43 = -1;
  v55 = v42;
  do
    ++v43;
  while ( *((_WORD *)v42 + v43) );
  LODWORD(v56) = 2 * v43 + 2;
  v44 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  v45 = pv;
  if ( v44 < 0 )
    goto LABEL_73;
  v55 = (struct _BLB_SYSTEM_STATE_RESTORE_STOP_EVENT_INFO *)pv;
  do
    ++v12;
  while ( *((_WORD *)pv + v12) );
  LODWORD(v56) = 2 * v12 + 2;
  ErrorCodeStringForEvent = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v57, &v55);
  if ( ErrorCodeStringForEvent >= 0 )
  {
    v44 = PublishEvent(v57, a2);
LABEL_73:
    ErrorCodeStringForEvent = v44;
  }
LABEL_76:
  v46 = 0;
  if ( v65 )
  {
    do
    {
      v47 = (LPVOID *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                        &v64,
                        v46);
      CoTaskMemFree(*v47);
      v48 = (_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                        &v64,
                        v46++);
      *v48 = 0;
    }
    while ( v46 < v65 );
    v45 = pv;
  }
  CoTaskMemFree(v5);
  for ( i = 0; i < v61; *v51 = 0 )
  {
    v50 = (LPVOID *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                      &v60,
                      i);
    CoTaskMemFree(*v50);
    v51 = (_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                      &v60,
                      i++);
  }
  CoTaskMemFree(v6);
  if ( v45 )
    CoTaskMemFree(v45);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(&v60);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(&v64);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v57);
  return (unsigned int)ErrorCodeStringForEvent;
}

```

## disassembly

```asm
0x1400d80c0  mov     [rsp-8+arg_8], rdx
0x1400d80c5  push    rbp
0x1400d80c6  push    rbx
0x1400d80c7  push    rsi
0x1400d80c8  push    rdi
0x1400d80c9  push    r12
0x1400d80cb  push    r13
0x1400d80cd  push    r14
0x1400d80cf  push    r15
0x1400d80d1  lea     rbp, [rsp-1Fh]
0x1400d80d6  sub     rsp, 0D8h
0x1400d80dd  xor     r15d, r15d
0x1400d80e0  lea     rbx, [rcx+8]
0x1400d80e4  mov     rsi, rcx
0x1400d80e7  mov     [rbp+57h+var_B0], r15
0x1400d80eb  mov     ecx, [rbx]
0x1400d80ed  lea     rdx, [rbp+57h+pv]
0x1400d80f1  mov     [rbp+57h+var_A8], r15
0x1400d80f5  mov     r13d, r15d
0x1400d80f8  mov     [rbp+57h+var_A0], r15
0x1400d80fc  mov     r12d, r15d
0x1400d80ff  mov     [rbp+57h+var_98], r15d
0x1400d8103  mov     [rbp+57h+var_68], r15
0x1400d8107  mov     [rbp+57h+var_60], r15
0x1400d810b  mov     [rbp+57h+var_58], r15
0x1400d810f  mov     [rbp+57h+var_50], r15d
0x1400d8113  mov     [rbp+57h+var_88], r15
0x1400d8117  mov     [rbp+57h+var_80], r15
0x1400d811b  mov     [rbp+57h+var_78], r15
0x1400d811f  mov     [rbp+57h+var_70], r15d
0x1400d8123  mov     [rbp+57h+pv], r15
0x1400d8127  call    GetErrorCodeStringForEvent
0x1400d812c  mov     edi, eax
0x1400d812e  test    eax, eax
0x1400d8130  js      loc_1400D8803
0x1400d8136  lea     edi, [r15+8]
0x1400d813a  mov     [rbp+57h+var_C0], rsi
0x1400d813e  lea     rdx, [rbp+57h+var_C0]
0x1400d8142  mov     [rbp+57h+var_B8], rdi
0x1400d8146  lea     rcx, [rbp+57h+var_B0]
0x1400d814a  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d814f  test    eax, eax
0x1400d8151  js      loc_1400D8801
0x1400d8157  mov     [rbp+57h+var_C0], rbx
0x1400d815b  lea     rdx, [rbp+57h+var_C0]
0x1400d815f  lea     ebx, [rdi-4]
0x1400d8162  lea     rcx, [rbp+57h+var_B0]
0x1400d8166  mov     dword ptr [rbp+57h+var_B8], ebx
0x1400d8169  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d816e  test    eax, eax
0x1400d8170  js      loc_1400D8801
0x1400d8176  lea     rax, [rsi+0Ch]
0x1400d817a  lea     rdx, [rbp+57h+var_C0]
0x1400d817e  mov     [rbp+57h+var_C0], rax
0x1400d8182  lea     rcx, [rbp+57h+var_B0]
0x1400d8186  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d818b  test    eax, eax
0x1400d818d  js      loc_1400D8801
0x1400d8193  lea     rax, [rsi+10h]
0x1400d8197  lea     rdx, [rbp+57h+var_C0]
0x1400d819b  mov     [rbp+57h+var_C0], rax
0x1400d819f  lea     rcx, [rbp+57h+var_B0]
0x1400d81a3  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d81a8  test    eax, eax
0x1400d81aa  js      loc_1400D8801
0x1400d81b0  lea     rax, [rsi+14h]
0x1400d81b4  lea     rdx, [rbp+57h+var_C0]
0x1400d81b8  mov     [rbp+57h+var_C0], rax
0x1400d81bc  lea     rcx, [rbp+57h+var_B0]
0x1400d81c0  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d81c5  test    eax, eax
0x1400d81c7  js      loc_1400D8801
0x1400d81cd  lea     rax, [rsi+18h]
0x1400d81d1  mov     dword ptr [rbp+57h+var_B8], 10h
0x1400d81d8  lea     rdx, [rbp+57h+var_C0]
0x1400d81dc  mov     [rbp+57h+var_C0], rax
0x1400d81e0  lea     rcx, [rbp+57h+var_B0]
0x1400d81e4  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d81e9  test    eax, eax
0x1400d81eb  js      loc_1400D8801
0x1400d81f1  lea     rax, [rsi+28h]
0x1400d81f5  mov     dword ptr [rbp+57h+var_B8], edi
0x1400d81f8  lea     rdx, [rbp+57h+var_C0]
0x1400d81fc  mov     [rbp+57h+var_C0], rax
0x1400d8200  lea     rcx, [rbp+57h+var_B0]
0x1400d8204  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8209  test    eax, eax
0x1400d820b  js      loc_1400D8801
0x1400d8211  lea     rdi, [rsi+30h]
0x1400d8215  mov     dword ptr [rbp+57h+var_B8], ebx
0x1400d8218  lea     rdx, [rbp+57h+var_C0]
0x1400d821c  mov     [rbp+57h+var_C0], rdi
0x1400d8220  lea     rcx, [rbp+57h+var_B0]
0x1400d8224  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8229  test    eax, eax
0x1400d822b  js      loc_1400D8801
0x1400d8231  lea     eax, [rbx+1Ah]
0x1400d8234  xor     r8d, r8d
0x1400d8237  mov     [rbp+57h+arg_10], eax
0x1400d823a  mov     r15d, eax
0x1400d823d  mov     ebx, r8d
0x1400d8240  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400d8244  cmp     ebx, [rdi]
0x1400d8246  jnb     loc_1400D82DC
0x1400d824c  mov     rax, [rsi+38h]
0x1400d8250  mov     ecx, ebx
0x1400d8252  mov     rdx, [rax+rcx*8]
0x1400d8256  mov     rax, r14
0x1400d8259  inc     rax
0x1400d825c  cmp     [rdx+rax*2], r8w
0x1400d8261  jnz     short loc_1400D8259
0x1400d8263  add     eax, 26h ; '&'
0x1400d8266  mov     dword ptr [rbp+57h+Size], eax
0x1400d8269  lea     rcx, [rax+rax]; cb
0x1400d826d  call    cs:__imp_CoTaskMemAlloc
0x1400d8273  mov     [rbp+57h+var_90], rax
0x1400d8277  mov     rdi, rax
0x1400d827a  test    rax, rax
0x1400d827d  jz      short loc_1400D82D2
0x1400d827f  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x1400d8283  xor     edx, edx; Val
0x1400d8285  mov     rcx, rax; void *
0x1400d8288  call    memset_0
0x1400d828d  mov     r9, [rsi+38h]
0x1400d8291  lea     r8, aVolumeinfoitem_1; "<VolumeInfoItem Name=\"%ws\"/>"
0x1400d8298  mov     edx, dword ptr [rbp+57h+Size]; unsigned __int64
0x1400d829b  mov     rcx, rdi; unsigned __int16 *
0x1400d829e  mov     eax, ebx
0x1400d82a0  mov     r9, [r9+rax*8]
0x1400d82a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400d82a9  mov     edi, eax
0x1400d82ab  test    eax, eax
0x1400d82ad  js      loc_1400D8803
0x1400d82b3  add     r15d, dword ptr [rbp+57h+Size]
0x1400d82b7  lea     rdx, [rbp+57h+var_90]
0x1400d82bb  lea     rcx, [rbp+57h+var_68]
0x1400d82bf  call    ?Add@?$CAtlArray@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@@2@@ATL@@QEAA_KAEBQEAV?$CComObject@VCBlbComponentRestoreContext@@@2@@Z; ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(ATL::CComObject<CBlbComponentRestoreContext> * const &)
0x1400d82c4  inc     ebx
0x1400d82c6  lea     rdi, [rsi+30h]
0x1400d82ca  xor     r8d, r8d
0x1400d82cd  jmp     loc_1400D8244
0x1400d82d2  mov     edi, 8007000Eh
0x1400d82d7  jmp     loc_1400D8803
0x1400d82dc  mov     ebx, r15d
0x1400d82df  lea     rdi, [rbx+rbx]
0x1400d82e3  mov     rcx, rdi; cb
0x1400d82e6  call    cs:__imp_CoTaskMemAlloc
0x1400d82ec  xor     r15d, r15d
0x1400d82ef  mov     r13, rax
0x1400d82f2  test    rax, rax
0x1400d82f5  jz      short loc_1400D82D2
0x1400d82f7  mov     r8, rdi; Size
0x1400d82fa  xor     edx, edx; Val
0x1400d82fc  mov     rcx, rax; void *
0x1400d82ff  call    memset_0
0x1400d8304  lea     r8, aVolumeinfo; "<VolumeInfo>"
0x1400d830b  mov     edx, ebx; unsigned __int64
0x1400d830d  mov     rcx, r13; unsigned __int16 *
0x1400d8310  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400d8315  mov     edi, eax
0x1400d8317  test    eax, eax
0x1400d8319  js      loc_1400D8803
0x1400d831f  mov     edx, r15d
0x1400d8322  cmp     rdx, [rbp+57h+var_60]
0x1400d8326  jnb     short loc_1400D834E
0x1400d8328  lea     rcx, [rbp+57h+var_68]
0x1400d832c  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400d8331  mov     rdx, rbx; unsigned __int64
0x1400d8334  mov     rcx, r13; unsigned __int16 *
0x1400d8337  mov     r8, [rax]; unsigned __int16 *
0x1400d833a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400d833f  mov     edi, eax
0x1400d8341  test    eax, eax
0x1400d8343  js      loc_1400D8803
0x1400d8349  inc     r15d
0x1400d834c  jmp     short loc_1400D831F
0x1400d834e  lea     r8, aVolumeinfo_0; "</VolumeInfo>"
0x1400d8355  mov     rdx, rbx; unsigned __int64
0x1400d8358  mov     rcx, r13; unsigned __int16 *
0x1400d835b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400d8360  xor     r15d, r15d
0x1400d8363  mov     edi, eax
0x1400d8365  test    eax, eax
0x1400d8367  js      loc_1400D8803
0x1400d836d  mov     [rbp+57h+var_C0], r13
0x1400d8371  mov     rax, r14
0x1400d8374  inc     rax
0x1400d8377  cmp     [r13+rax*2+0], r15w
0x1400d837d  jnz     short loc_1400D8374
0x1400d837f  lea     eax, ds:2[rax*2]
0x1400d8386  lea     rdx, [rbp+57h+var_C0]
0x1400d838a  mov     dword ptr [rbp+57h+var_B8], eax
0x1400d838d  lea     rcx, [rbp+57h+var_B0]
0x1400d8391  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8396  test    eax, eax
0x1400d8398  js      loc_1400D8801
0x1400d839e  lea     rdi, [rsi+40h]
0x1400d83a2  mov     dword ptr [rbp+57h+var_B8], 4
0x1400d83a9  lea     rdx, [rbp+57h+var_C0]
0x1400d83ad  mov     [rbp+57h+var_C0], rdi
0x1400d83b1  lea     rcx, [rbp+57h+var_B0]
0x1400d83b5  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d83ba  test    eax, eax
0x1400d83bc  js      loc_1400D8801
0x1400d83c2  mov     ebx, 1Eh
0x1400d83c7  cmp     r15d, [rdi]
0x1400d83ca  jnb     loc_1400D84B0
0x1400d83d0  mov     rax, [rsi+48h]
0x1400d83d4  xor     edi, edi
0x1400d83d6  mov     ecx, r15d
0x1400d83d9  mov     rdx, [rax+rcx*8]
0x1400d83dd  mov     rax, r14
0x1400d83e0  inc     rax
0x1400d83e3  cmp     [rdx+rax*2], di
0x1400d83e7  jnz     short loc_1400D83E0
0x1400d83e9  add     eax, 489h
0x1400d83ee  mov     ebx, eax
0x1400d83f0  mov     dword ptr [rbp+57h+Size], eax
0x1400d83f3  mov     [rbp+57h+var_48], rbx
0x1400d83f7  lea     rcx, [rax+rax]; cb
0x1400d83fb  call    cs:__imp_CoTaskMemAlloc
0x1400d8401  mov     [rbp+57h+var_90], rax
0x1400d8405  test    rax, rax
0x1400d8408  jz      loc_1400D82D2
0x1400d840e  mov     r8d, ebx; Size
0x1400d8411  xor     edx, edx; Val
0x1400d8413  mov     rcx, rax; void *
0x1400d8416  call    memset_0
0x1400d841b  mov     r8, [rsi+70h]
0x1400d841f  mov     rax, [rsi+78h]
0x1400d8423  mov     r10, [rsi+68h]
0x1400d8427  mov     r11, [rsi+60h]
0x1400d842b  mov     rbx, [rsi+58h]
0x1400d842f  mov     rdi, [rsi+50h]
0x1400d8433  mov     r9, [rsi+48h]
0x1400d8437  mov     rdx, [rbp+57h+var_48]; unsigned __int64
0x1400d843b  mov     ecx, r15d
0x1400d843e  mov     rax, [rax+rcx*8]
0x1400d8442  mov     r9, [r9+rcx*8]
0x1400d8446  mov     [rsp+110h+var_C8], rax
0x1400d844b  mov     rax, [r8+rcx*8]
0x1400d844f  lea     r8, aWriterinfoitem; "<WriterInfoItem Name=\"%ws\" HResult=\""...
0x1400d8456  mov     [rsp+110h+var_D0], rax
0x1400d845b  mov     rax, [r10+rcx*8]
0x1400d845f  mov     [rsp+110h+var_D8], rax
0x1400d8464  mov     rax, [r11+rcx*8]
0x1400d8468  mov     [rsp+110h+var_E0], rax
0x1400d846d  mov     eax, [rbx+rcx*4]
0x1400d8470  mov     dword ptr [rsp+110h+var_E8], eax
0x1400d8474  mov     eax, [rdi+rcx*4]
0x1400d8477  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x1400d847b  mov     dword ptr [rsp+110h+var_F0], eax
0x1400d847f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400d8484  mov     edi, eax
0x1400d8486  test    eax, eax
0x1400d8488  js      loc_1400D8803
0x1400d848e  mov     ebx, [rbp+57h+arg_10]
0x1400d8491  lea     rdx, [rbp+57h+var_90]
0x1400d8495  add     ebx, dword ptr [rbp+57h+Size]
0x1400d8498  lea     rcx, [rbp+57h+var_88]
0x1400d849c  mov     [rbp+57h+arg_10], ebx
0x1400d849f  call    ?Add@?$CAtlArray@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@@2@@ATL@@QEAA_KAEBQEAV?$CComObject@VCBlbComponentRestoreContext@@@2@@Z; ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(ATL::CComObject<CBlbComponentRestoreContext> * const &)
0x1400d84a4  inc     r15d
0x1400d84a7  lea     rdi, [rsi+40h]
0x1400d84ab  jmp     loc_1400D83C7
0x1400d84b0  lea     rdi, [rbx+rbx]
0x1400d84b4  mov     rcx, rdi; cb
0x1400d84b7  call    cs:__imp_CoTaskMemAlloc
0x1400d84bd  xor     r15d, r15d
0x1400d84c0  mov     r12, rax
0x1400d84c3  test    rax, rax
0x1400d84c6  jz      loc_1400D82D2
0x1400d84cc  mov     r8, rdi; Size
0x1400d84cf  xor     edx, edx; Val
0x1400d84d1  mov     rcx, rax; void *
0x1400d84d4  call    memset_0
0x1400d84d9  lea     r8, aWriterinfo; "<WriterInfo>"
0x1400d84e0  mov     rdx, rbx; unsigned __int64
0x1400d84e3  mov     rcx, r12; unsigned __int16 *
0x1400d84e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400d84eb  mov     edi, eax
0x1400d84ed  test    eax, eax
0x1400d84ef  js      loc_1400D8803
0x1400d84f5  mov     edx, r15d
0x1400d84f8  cmp     rdx, [rbp+57h+var_80]
0x1400d84fc  jnb     short loc_1400D8524
0x1400d84fe  lea     rcx, [rbp+57h+var_88]
0x1400d8502  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400d8507  mov     rdx, rbx; unsigned __int64
0x1400d850a  mov     rcx, r12; unsigned __int16 *
0x1400d850d  mov     r8, [rax]; unsigned __int16 *
0x1400d8510  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400d8515  mov     edi, eax
0x1400d8517  test    eax, eax
0x1400d8519  js      loc_1400D8803
0x1400d851f  inc     r15d
0x1400d8522  jmp     short loc_1400D84F5
0x1400d8524  lea     r8, aWriterinfo_0; "</WriterInfo>"
0x1400d852b  mov     rdx, rbx; unsigned __int64
0x1400d852e  mov     rcx, r12; unsigned __int16 *
  ... truncated ...
```
