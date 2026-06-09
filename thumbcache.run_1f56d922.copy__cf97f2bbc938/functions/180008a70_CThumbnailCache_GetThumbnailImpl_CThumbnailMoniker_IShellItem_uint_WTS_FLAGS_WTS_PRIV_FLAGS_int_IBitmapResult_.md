# CThumbnailCache::_GetThumbnailImpl(CThumbnailMoniker &,IShellItem *,uint,WTS_FLAGS,WTS_PRIV_FLAGS,int,IBitmapResult * *,int *,int *)

- ea: `0x180008a70`
- end: `0x180009958`
- name: `?_GetThumbnailImpl@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@PEAUIShellItem@@IW4WTS_FLAGS@@W4WTS_PRIV_FLAGS@@HPEAPEAUIBitmapResult@@PEAH5@Z`
- size: `3816`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000a300`

## callees

- `0x180003650`
- `0x180006c94`
- `0x180008a70`
- `0x180009960`
- `0x18000f878`
- `0x18000ffcc`
- `0x18001161c`
- `0x18001195c`
- `0x180012e60`
- `0x1800130d0`
- `0x1800132f8`
- `0x180013394`
- `0x180013490`
- `0x1800137b4`
- `0x180013d80`
- `0x180014c4c`
- `0x180014e0c`
- `0x1800152b0`
- `0x180017af0`
- `0x180024618`
- `0x1800246c8`
- `0x180025108`
- `0x1800294b8`
- `0x18002b11c`
- `0x180035830`
- `0x180040e8c`
- `0x180042d38`
- `0x180043818`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009904`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008dfc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008dfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800098e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800098e0`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180008de1`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180008de1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000990e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000990e`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CThumbnailCache::_GetThumbnailImpl(
        __int64 a1,
        struct CThumbnailMoniker *a2,
        struct IShellItem *a3,
        unsigned int a4,
        enum WTS_FLAGS a5,
        int a6,
        int a7,
        _QWORD *a8,
        BOOL *a9,
        _DWORD *a10)
{
  unsigned int v13; // ebx
  _QWORD *v14; // rax
  _DWORD *v15; // rdx
  BOOL v16; // r15d
  char *v17; // rdi
  unsigned __int64 v18; // r8
  int ThumbInfoFromCache; // esi
  __int64 v20; // rcx
  BOOL v21; // r13d
  int NextThumbSizeFromPixelSize; // eax
  int v23; // edx
  int v24; // ecx
  int v25; // edx
  unsigned int v26; // esi
  struct IBitmapResult *v27; // rcx
  int ThumbnailFromCache; // eax
  struct CThumbnailMoniker *v29; // r15
  char *SemaphoreW; // rax
  struct IBitmapResult *v31; // rcx
  struct IBitmapResult *v32; // rbx
  struct IBitmapResult *v33; // rcx
  struct IShellItem *v34; // rsi
  struct IBitmapResult *v35; // rcx
  BOOL CanCache; // eax
  __int64 v37; // r9
  unsigned int v38; // eax
  struct IBitmapResult *v39; // rcx
  unsigned int v40; // r8d
  unsigned int v41; // eax
  __int64 ThumbPixelSize; // r9
  int v43; // r10d
  unsigned int v44; // edx
  struct IBitmapResult *v45; // rcx
  unsigned int v46; // r8d
  int v47; // edx
  int v48; // ecx
  struct IBitmapResult *v49; // rbx
  struct IBitmapResult *v50; // rcx
  unsigned int v51; // ecx
  int v52; // eax
  struct IShellItem *v53; // rsi
  unsigned int v54; // eax
  struct IBitmapResult *v55; // rbx
  struct IBitmapResult *v56; // rcx
  CThumbnailCache *v57; // rcx
  unsigned int v58; // eax
  int v59; // eax
  struct IBitmapResult *v60; // rdx
  struct IBitmapResult *v61; // rbx
  struct IBitmapResult *v62; // rcx
  unsigned int v63; // ebx
  int v64; // eax
  int v65; // ecx
  struct IShellItem *v66; // rbx
  struct IBitmapResult *v67; // rbx
  struct IBitmapResult *v68; // rcx
  __int64 v69; // rbx
  struct IShellItem *v70; // rcx
  struct IBitmapResult *v71; // rax
  struct IBitmapResult *v72; // rcx
  char v74; // [rsp+70h] [rbp-90h]
  char v75; // [rsp+71h] [rbp-8Fh]
  char v76; // [rsp+71h] [rbp-8Fh]
  int v77; // [rsp+74h] [rbp-8Ch]
  int v78; // [rsp+78h] [rbp-88h] BYREF
  BOOL v79; // [rsp+7Ch] [rbp-84h]
  bool v80; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v81; // [rsp+84h] [rbp-7Ch]
  unsigned int v82; // [rsp+88h] [rbp-78h]
  struct CThumbnailMoniker *v83; // [rsp+90h] [rbp-70h]
  struct IBitmapResult **v84; // [rsp+98h] [rbp-68h]
  HANDLE hObject[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v86; // [rsp+B0h] [rbp-50h]
  char *v87; // [rsp+B8h] [rbp-48h]
  BOOL *v88; // [rsp+C0h] [rbp-40h]
  BOOL *v89; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v90; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v91; // [rsp+D8h] [rbp-28h] BYREF
  struct IBitmapResult *v92; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int WideCacheSizeForRequest; // [rsp+E8h] [rbp-18h] BYREF
  struct IShellItem *v94; // [rsp+F0h] [rbp-10h] BYREF
  enum WTS_ALPHATYPE v95; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v96[2]; // [rsp+100h] [rbp+0h] BYREF
  struct IBitmapResult *v97; // [rsp+108h] [rbp+8h] BYREF
  char v98[16]; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v99; // [rsp+120h] [rbp+20h]
  __int64 v100; // [rsp+128h] [rbp+28h]
  WCHAR Name[264]; // [rsp+130h] [rbp+30h] BYREF

  v81 = a4;
  v94 = a3;
  v83 = a2;
  v13 = a4;
  WideCacheSizeForRequest = a4;
  v14 = a8;
  v84 = (struct IBitmapResult **)a8;
  v88 = a9;
  v15 = a10;
  v89 = a10;
  *a9 = 0;
  *v15 = 1;
  if ( v14 )
    *v14 = 0;
  v92 = 0;
  v79 = 0;
  LODWORD(v97) = 0;
  v16 = 1;
  v78 = 1;
  *(_OWORD *)hObject = 0;
  v86 = 0;
  v95 = WTSAT_UNKNOWN;
  v17 = 0;
  v87 = 0;
  if ( (a5 & 0x82) != 2 || (v74 = 1, IShellItem_IsPartialCloudFilePlaceholder(a3)) )
    v74 = 0;
  if ( !CThumbnailCache::_ShouldConsiderItem((CThumbnailCache *)a1, a3) )
  {
    ThumbInfoFromCache = -2147467259;
    goto LABEL_235;
  }
  v75 = 0;
  LODWORD(v91) = a5 & 0x10000200;
  if ( (a5 & 0x10000200) != 0 )
  {
    v90 = 0;
    ThumbInfoFromCache = CThumbnailCache::_TryGetThumbInfoFromCache((CThumbnailCache *)a1, a2, &v90);
    if ( ThumbInfoFromCache >= 0 )
    {
      v18 = v90;
      if ( ((v90 >> 12) & 0x7FF) == 0 || (v18 = v90 & 0x7FF, (v90 & 0x7FF) == 0) )
      {
        ThumbInfoFromCache = -2147467259;
        goto LABEL_18;
      }
      ThumbInfoFromCache = CThumbnailCache::_CalculateIdealLengthForCropping(
                             (CThumbnailCache *)a1,
                             (v90 >> 12) & 0x7FF,
                             v18,
                             a5,
                             &WideCacheSizeForRequest);
      v13 = WideCacheSizeForRequest;
    }
    if ( ThumbInfoFromCache >= 0 )
    {
      if ( !a7 || (unsigned int)CThumbnailCache::_GetNextThumbSizeFromPixelSize(a1, v13) == -1 )
      {
        v21 = 0;
        a7 = 0;
        v75 = 1;
      }
      else
      {
        v21 = 1;
        a7 = 1;
        v75 = 1;
      }
      goto LABEL_28;
    }
LABEL_18:
    v21 = a7;
    goto LABEL_19;
  }
  v21 = a7;
LABEL_28:
  if ( (*(_BYTE *)(a1 + 768) & 1) == 0 && (a5 & 4) != 0 )
  {
    v20 = *(_QWORD *)(a1 + 48);
    if ( v20 )
      CThumbnailCacheIndex::Delete(v20, *(_QWORD *)v83, 14, 0, 0);
    ThumbInfoFromCache = -2147287038;
    goto LABEL_22;
  }
  v23 = !(a5 & 1);
  if ( v21 )
    v23 = !(a5 & 1) | 2;
  v24 = v23 | 4;
  if ( (a5 & 0x4000) == 0 )
    v24 = v23;
  v25 = v24 | 0x20;
  if ( a5 >= WTS_NONE )
    v25 = v24;
  v26 = v25 | 0x10;
  if ( (a5 & 0x8000) == 0 )
    v26 = v25;
  v82 = v26;
  v27 = v92;
  if ( v92 )
  {
    v92 = 0;
    (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v27 + 16LL))(v27);
  }
  ThumbnailFromCache = CThumbnailCache::_TryGetThumbnailFromCache(
                         a1,
                         v83,
                         v13,
                         v26,
                         hObject,
                         &v78,
                         &v95,
                         &GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f,
                         &v92);
  ThumbInfoFromCache = ThumbnailFromCache;
  if ( (a5 & 0x2000) != 0 && !v74 && ThumbnailFromCache < 0 && ThumbnailFromCache != -2147216863 )
  {
    v20 = (unsigned int)(ThumbnailFromCache + 2147175936);
    if ( (unsigned int)v20 > 1 && ThumbnailFromCache != -2147024882 && (*(_BYTE *)(a1 + 768) & 1) == 0 && (a5 & 1) == 0 )
    {
      v29 = v83;
      if ( (int)StringCchPrintfW(Name, 0x104u, L"ThumbnailExtraction-%I64x", *(_QWORD *)v83) >= 0 )
      {
        SemaphoreW = (char *)CreateSemaphoreW(0, 1, 1, Name);
        v17 = SemaphoreW;
        v87 = SemaphoreW;
        if ( SemaphoreW )
        {
          if ( WaitForSingleObject(SemaphoreW, dwMilliseconds) )
          {
            ThumbInfoFromCache = -2147175935;
            v16 = v78;
            goto LABEL_179;
          }
          v31 = v92;
          if ( v92 )
          {
            v92 = 0;
            (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v31 + 16LL))(v31);
          }
          ThumbInfoFromCache = CThumbnailCache::_TryGetThumbnailFromCache(
                                 a1,
                                 v29,
                                 v13,
                                 v82,
                                 hObject,
                                 &v78,
                                 &v95,
                                 &GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f,
                                 &v92);
        }
      }
    }
  }
  v16 = v78;
  if ( ThumbInfoFromCache >= 0 )
  {
    v79 = 1;
    goto LABEL_179;
  }
LABEL_19:
  if ( ThumbInfoFromCache == -2147216863
    || (unsigned int)(ThumbInfoFromCache + 2147175936) <= 1
    || ThumbInfoFromCache == -2147024882 )
  {
    goto LABEL_179;
  }
LABEL_22:
  if ( (*(_BYTE *)(a1 + 768) & 1) != 0 || (a5 & 1) != 0 )
    goto LABEL_179;
  if ( a5 >= WTS_NONE )
    NextThumbSizeFromPixelSize = CThumbnailCache::_GetNextThumbSizeFromPixelSize(a1, v13);
  else
    NextThumbSizeFromPixelSize = GetNextThumbSizeFromPixelSizeWideAlt(v13);
  v77 = NextThumbSizeFromPixelSize;
  if ( (a5 & 0x4000) == 0 || a5 < WTS_NONE && v13 <= 0x500 )
  {
    v80 = 0;
    CanCache = CThumbsDBStore::CanCache((CThumbsDBStore *)(a1 + 792), v94, &v80);
    v20 = CanCache;
    v82 = CanCache;
    v38 = 256;
    if ( (_DWORD)v20 )
    {
      v20 = 0;
      if ( (*(_BYTE *)(a1 + 768) & 2) == 0 )
        v20 = 96;
      if ( v13 <= (unsigned int)v20 )
      {
        v39 = v92;
        if ( v92 )
        {
          v92 = 0;
          (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v39 + 16LL))(v39);
        }
        v40 = 0;
        if ( (*(_BYTE *)(a1 + 768) & 2) == 0 )
          v40 = 96;
        ThumbInfoFromCache = CThumbsDBStore::GetThumbnail((CThumbsDBStore *)(a1 + 792), v94, v40, &v92);
        if ( ThumbInfoFromCache >= 0 )
        {
          v16 = 0;
          v78 = 0;
          v77 = 3;
          goto LABEL_92;
        }
        v38 = 256;
      }
      v44 = qword_180062A8C;
      if ( (*(_BYTE *)(a1 + 768) & 2) != 0 )
        v38 = qword_180062A8C;
      if ( v13 <= v38 )
      {
        v45 = v92;
        if ( v92 )
        {
          v92 = 0;
          (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v45 + 16LL))(v45);
          v44 = qword_180062A8C;
        }
        v46 = 256;
        if ( (*(_BYTE *)(a1 + 768) & 2) != 0 )
          v46 = v44;
        ThumbInfoFromCache = CThumbsDBStore::GetThumbnail((CThumbsDBStore *)(a1 + 792), v94, v46, &v92);
        if ( ThumbInfoFromCache >= 0 )
        {
          v16 = 0;
          v47 = 4;
          v77 = 4;
          goto LABEL_133;
        }
      }
    }
LABEL_92:
    if ( v16 && (a5 & 0x80u) == 0 && !IShellItem_IsPartialCloudFilePlaceholder(v94) )
    {
      v20 = 256;
      if ( (a5 & 2) != 0 )
        goto LABEL_103;
      v41 = 256;
      if ( (*(_BYTE *)(a1 + 768) & 2) != 0 )
        v41 = qword_180062A8C;
      if ( v13 <= v41 )
      {
LABEL_103:
        if ( !v21 )
          goto LABEL_116;
        if ( v77 < 4 )
          goto LABEL_104;
        if ( (*(_BYTE *)(a1 + 768) & 2) != 0 )
          LODWORD(v20) = qword_180062A8C;
        if ( v13 == (_DWORD)v20 )
        {
LABEL_104:
          v96[0] = 1;
          ThumbPixelSize = (unsigned int)CThumbnailCache::_GetThumbPixelSize(a1, 1, (unsigned int)v77, v37);
        }
        else
        {
LABEL_116:
          v96[0] = 0;
          ThumbPixelSize = v13;
          v43 = 1;
        }
        if ( (a5 & 0x42) == 0x42 || (a5 & 0x10000) != 0 )
          v48 = v43;
        else
          v48 = 0;
        v90 = 0;
        ThumbInfoFromCache = CThumbnailCache::_PerformFastExtraction(
                               a1,
                               v83,
                               v94,
                               ThumbPixelSize,
                               a5,
                               a6,
                               v48,
                               v21,
                               hObject,
                               v92,
                               &v90,
                               &v95,
                               &v78);
        if ( ThumbInfoFromCache < 0 )
        {
          v16 = v78;
        }
        else
        {
          v49 = (struct IBitmapResult *)v90;
          if ( v92 != (struct IBitmapResult *)v90 )
          {
            if ( v90 )
              (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v90 + 8LL))(v90);
            v50 = v92;
            v92 = v49;
            if ( v50 )
              (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v50 + 16LL))(v50);
          }
          v16 = v78;
          v13 = WideCacheSizeForRequest;
          if ( !v78 )
            v16 = v96[0] == 0;
        }
        v20 = v90;
        if ( v90 )
        {
          v90 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
    }
    v47 = v77;
LABEL_133:
    if ( (_DWORD)v91 && !v75 )
    {
      if ( ThumbInfoFromCache < 0 )
      {
        if ( !v74 )
        {
          CThumbnailCache::_TryAdjustRequestSizeFromStream((CThumbnailCache *)a1, v94, a5, &WideCacheSizeForRequest);
          v13 = WideCacheSizeForRequest;
        }
      }
      else
      {
        *(_QWORD *)v96 = 0;
        ThumbInfoFromCache = (*(__int64 (__fastcall **)(struct IBitmapResult *, unsigned int *))(*(_QWORD *)v92 + 72LL))(
                               v92,
                               v96);
        if ( ThumbInfoFromCache >= 0 )
        {
          ThumbInfoFromCache = CThumbnailCache::_CalculateIdealLengthForCropping(
                                 (CThumbnailCache *)a1,
                                 v96[0],
                                 v96[1],
                                 a5,
                                 &WideCacheSizeForRequest);
          v13 = WideCacheSizeForRequest;
          if ( ThumbInfoFromCache < 0 )
            goto LABEL_141;
          v51 = v96[1];
          if ( (int)v96[0] > (int)v96[1] )
            v51 = v96[0];
          if ( WideCacheSizeForRequest > v51 )
LABEL_141:
            v16 = 1;
        }
      }
      v52 = CThumbnailCache::_GetNextThumbSizeFromPixelSize(a1, v13);
      v47 = v52;
      v77 = v52;
      v21 = v21 && v52 != -1;
      a7 = v21;
    }
    if ( !v16 || v74 )
      goto LABEL_174;
    if ( v21 )
    {
      if ( v47 < 6 )
      {
        v96[0] = 0;
        v53 = v94;
        if ( (IShellItem_GetFilePlaceholderStatus(v94, v96) < 0 || (v96[0] & 8) == 0)
          && (unsigned int)_GetPerceivedType(v53) == 4 )
        {
          v47 = 6;
          goto LABEL_161;
        }
        v47 = v77;
      }
      if ( v82 && v47 < 4 )
        v47 = 4;
    }
LABEL_161:
    v90 = 0;
    if ( v21 )
      v54 = CThumbnailCache::_GetThumbPixelSize(a1, 1, (unsigned int)v47, v37);
    else
      v54 = v13;
    ThumbInfoFromCache = CThumbnailCache::_PerformFullExtraction(a1, v94, v13, v54, a5, a6, &v90, &a7, &v95);
    if ( ThumbInfoFromCache >= 0 )
    {
      v55 = (struct IBitmapResult *)v90;
      if ( v92 != (struct IBitmapResult *)v90 )
      {
        if ( v90 )
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v90 + 8LL))(v90);
        v56 = v92;
        v92 = v55;
        if ( v56 )
          (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v56 + 16LL))(v56);
      }
      v16 = 0;
      v13 = WideCacheSizeForRequest;
    }
    v20 = v90;
    if ( v90 )
    {
      v90 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = a7;
LABEL_174:
    if ( ThumbInfoFromCache == -2147175936 || ThumbInfoFromCache >= 0 && !v16 && v21 )
    {
      ThumbInfoFromCache = CThumbnailCache::_RecordExtractionTransactionToCache(
                             a1,
                             v94,
                             v83,
                             (unsigned int)ThumbInfoFromCache);
      v79 = (int)v97;
    }
    goto LABEL_179;
  }
  if ( v74 )
  {
    v97 = 0;
    ThumbInfoFromCache = CThumbnailCache::_PerformFastExtraction(
                           a1,
                           v83,
                           v94,
                           v13,
                           a5,
                           a6,
                           0,
                           v21,
                           hObject,
                           v92,
                           &v97,
                           &v95,
                           &v78);
    if ( ThumbInfoFromCache < 0 )
    {
      v16 = v78;
    }
    else
    {
      v32 = v97;
      if ( v92 != v97 )
      {
        if ( v97 )
          (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v97 + 8LL))(v97);
        v33 = v92;
        v92 = v32;
        if ( v33 )
          (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v16 = 1;
      v21 = 0;
      v13 = WideCacheSizeForRequest;
    }
    v20 = (__int64)v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
  }
  else if ( CThumbnailCache::_ShouldTryToExtract((CThumbnailCache *)a1, ThumbInfoFromCache, a5) )
  {
    WideCacheSizeForRequest = CThumbnailCache::s_GetWideCacheSizeForRequest(v13);
    v34 = v94;
    CThumbnailCache::_TryAdjustRequestSizeFromStream((CThumbnailCache *)a1, v94, a5, &WideCacheSizeForRequest);
    v35 = v92;
    if ( v92 )
    {
      v92 = 0;
      (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v13 = WideCacheSizeForRequest;
    ThumbInfoFromCache = CThumbnailCache::_PerformFullExtraction(
                           a1,
                           v34,
                           WideCacheSizeForRequest,
                           WideCacheSizeForRequest,
                           a5,
                           a6,
                           &v92,
                           &a7,
                           &v95);
    v21 = a7;
    if ( ThumbInfoFromCache >= 0 )
    {
      v16 = 0;
      goto LABEL_179;
    }
  }
  if ( ThumbInfoFromCache == -2147175936 )
    CThumbnailCache::_AddNegativeThumbnailToCache((CThumbnailCache *)a1, v94, v83);
LABEL_179:
  if ( (_DWORD)v91 && (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    LODWORD(v91) = v13;
    v99 = &v91;
    v100 = 4;
    McGenEventWrite_EventWriteTransfer(v20, Thumbnails_CropLookupSize_Info, v18, 2, v98);
  }
  if ( ThumbInfoFromCache < 0 )
    goto LABEL_233;
  if ( !v84 )
    goto LABEL_232;
  if ( (a5 & 0x80004000) == 0 || v79 || v16 || !v21 )
    goto LABEL_208;
  v94 = 0;
  LODWORD(v91) = a5 & 0x4000;
  v57 = (CThumbnailCache *)v81;
  if ( (a5 & 0x4000) != 0 && (v58 = CThumbnailCache::s_GetWideCacheSizeForRequest(v81), v58 > (unsigned int)v57) )
  {
    v76 = 0;
    v59 = CThumbnailCache::_PostProcessThumbnail((CThumbnailCache *)&v94, a5, v58, v92, (struct IBitmapResult **)&v94);
  }
  else
  {
    v76 = 1;
    v59 = CThumbnailCache::_PostProcessThumbnail(v57, a5, (unsigned int)v57, v92, (struct IBitmapResult **)&v94);
  }
  ThumbInfoFromCache = v59;
  if ( v59 >= 0 )
  {
    v60 = v92;
    v61 = (struct IBitmapResult *)v94;
    if ( v92 != (struct IBitmapResult *)v94 )
    {
      if ( v94 )
      {
        ((void (__fastcall *)(struct IShellItem *))v94->lpVtbl->AddRef)(v94);
        v60 = v92;
      }
      v62 = v60;
      v60 = v61;
      v92 = v61;
      if ( v62 )
      {
        (*(void (__fastcall **)(struct IBitmapResult *, struct IBitmapResult *))(*(_QWORD *)v62 + 16LL))(v62, v61);
        v60 = v92;
      }
    }
    v63 = 10;
    if ( !(_DWORD)v91 )
      v63 = 12;
    if ( (int)CThumbnailCache::_VerifyValidThumbnail(a1, v60, v63) >= 0 )
    {
      v64 = CThumbnailCache::_AddThumbnailToCache(a1, v83, v63, v92, v95);
      v65 = v79;
      if ( v64 >= 0 )
        v65 = 1;
      v79 = v65;
    }
  }
  v20 = (__int64)v94;
  if ( v94 )
  {
    v94 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( ThumbInfoFromCache < 0 )
    goto LABEL_233;
  if ( !v76 )
  {
LABEL_208:
    v94 = 0;
    ThumbInfoFromCache = CThumbnailCache::_PostProcessThumbnail(
                           (CThumbnailCache *)v20,
                           a5,
                           v81,
                           v92,
                           (struct IBitmapResult **)&v94);
    if ( ThumbInfoFromCache < 0 )
      goto LABEL_228;
    if ( v92 )
    {
      v66 = v94;
      if ( v94 )
      {
        if ( v92 == (struct IBitmapResult *)v94 )
          goto LABEL_228;
        v90 = 0;
        v91 = 0;
        if ( (**(int (__fastcall ***)(struct IBitmapResult *, GUID *, unsigned __int64 *))v92)(
               v92,
               &GUID_00000000_0000_0000_c000_000000000046,
               &v90) >= 0 )
        {
          if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))v66->lpVtbl->QueryInterface)(
                 v66,
                 &GUID_00000000_0000_0000_c000_000000000046,
                 &v91) < 0 )
          {
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v90 + 16LL))(v90);
          }
          else
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v90 + 16LL))(v90);
            if ( v90 == v91 )
              goto LABEL_228;
          }
        }
      }
    }
    v67 = (struct IBitmapResult *)v94;
    if ( v92 != (struct IBitmapResult *)v94 )
    {
      if ( v94 )
        ((void (__fastcall *)(struct IShellItem *))v94->lpVtbl->AddRef)(v94);
      v68 = v92;
      v92 = v67;
      if ( v68 )
        (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v68 + 16LL))(v68);
    }
    if ( (a5 & 0x10000) != 0 && !v79 && !v16 )
    {
      if ( v21 )
      {
        v69 = (unsigned int)CThumbnailCache::_GetNextThumbSizeFromPixelSize(a1, v81);
        if ( (int)CThumbnailCache::_VerifyValidThumbnail(a1, v92, v69) >= 0 )
          v79 = (int)CThumbnailCache::_AddThumbnailToCache(a1, v83, (unsigned int)v69, v92, v95) >= 0;
      }
    }
LABEL_228:
    v70 = v94;
    if ( v94 )
    {
      v94 = 0;
      ((void (__fastcall *)(struct IShellItem *))v70->lpVtbl->Release)(v70);
    }
    if ( ThumbInfoFromCache < 0 )
      goto LABEL_233;
  }
  v71 = v92;
  v92 = 0;
  *v84 = v71;
LABEL_232:
  *v88 = v79;
  *v89 = v16;
LABEL_233:
  CThumbnailCache::_ResetCacheFilesIfFailedCritically((CThumbnailCache *)a1, ThumbInfoFromCache);
  if ( v17 )
    ReleaseSemaphore(v17, 1, 0);
LABEL_235:
  if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v17);
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  SysFreeString((BSTR)hObject[0]);
  v72 = v92;
  if ( v92 )
  {
    v92 = 0;
    (*(void (__fastcall **)(struct IBitmapResult *))(*(_QWORD *)v72 + 16LL))(v72);
  }
  return (unsigned int)ThumbInfoFromCache;
}

```

## disassembly

```asm
0x180008a70  push    rbp
0x180008a72  push    rbx
0x180008a73  push    rsi
0x180008a74  push    rdi
0x180008a75  push    r12
0x180008a77  push    r13
0x180008a79  push    r14
0x180008a7b  push    r15
0x180008a7d  lea     rbp, [rsp-258h]
0x180008a85  sub     rsp, 358h
0x180008a8c  mov     rax, cs:__security_cookie
0x180008a93  xor     rax, rsp
0x180008a96  mov     [rbp+290h+var_50], rax
0x180008a9d  mov     eax, r9d
0x180008aa0  mov     dword ptr [rbp+290h+var_30C], eax
0x180008aa3  mov     rsi, r8
0x180008aa6  mov     [rbp+290h+var_2A0], r8
0x180008aaa  mov     r13, rdx
0x180008aad  mov     [rbp+290h+var_300], rdx
0x180008ab1  mov     r14, rcx
0x180008ab4  mov     ebx, r9d
0x180008ab7  mov     [rbp+290h+var_2A8], eax
0x180008aba  mov     rax, [rbp+290h+arg_38]
0x180008ac1  mov     [rbp+290h+var_2F8], rax
0x180008ac5  mov     rcx, [rbp+290h+arg_40]
0x180008acc  mov     [rbp+290h+var_2D0], rcx
0x180008ad0  mov     rdx, [rbp+290h+arg_48]
0x180008ad7  mov     [rbp+290h+var_2C8], rdx
0x180008adb  xor     r8d, r8d
0x180008ade  mov     [rcx], r8d
0x180008ae1  mov     ecx, 1
0x180008ae6  mov     [rdx], ecx
0x180008ae8  test    rax, rax
0x180008aeb  jz      short loc_180008AF0
0x180008aed  mov     [rax], r8
0x180008af0  mov     [rbp+290h+var_2B0], r8
0x180008af4  mov     eax, r8d
0x180008af7  mov     [rsp+390h+var_314], eax
0x180008afb  mov     dword ptr [rbp+290h+var_288], eax
0x180008afe  mov     r15d, ecx
0x180008b01  mov     [rsp+390h+var_318], ecx
0x180008b05  xorps   xmm0, xmm0
0x180008b08  movdqu  xmmword ptr [rbp+290h+hObject], xmm0
0x180008b0d  mov     [rbp+290h+var_2E0], r8d
0x180008b11  mov     [rbp+290h+var_298], r8d
0x180008b15  mov     rdi, r8
0x180008b18  mov     [rbp+290h+var_2D8], r8
0x180008b1c  mov     r12d, [rbp+290h+arg_20]
0x180008b23  mov     eax, r12d
0x180008b26  and     al, 82h
0x180008b28  cmp     al, 2
0x180008b2a  jnz     short loc_180008B3D
0x180008b2c  mov     rcx, rsi; struct IShellItem *
0x180008b2f  call    ?IShellItem_IsPartialCloudFilePlaceholder@@YA_NPEAUIShellItem@@@Z; IShellItem_IsPartialCloudFilePlaceholder(IShellItem *)
0x180008b34  test    al, al
0x180008b36  mov     [rsp+390h+var_320], 1
0x180008b3b  jz      short loc_180008B42
0x180008b3d  mov     [rsp+390h+var_320], 0
0x180008b42  mov     rdx, rsi; struct IShellItem *
0x180008b45  mov     rcx, r14; this
0x180008b48  call    ?_ShouldConsiderItem@CThumbnailCache@@AEAA_NPEAUIShellItem@@@Z; CThumbnailCache::_ShouldConsiderItem(IShellItem *)
0x180008b4d  test    al, al
0x180008b4f  jnz     short loc_180008B5B
0x180008b51  mov     esi, 80004005h
0x180008b56  jmp     loc_1800098E7
0x180008b5b  mov     [rsp+390h+var_31F], 0
0x180008b60  mov     eax, r12d
0x180008b63  and     eax, 10000200h
0x180008b68  mov     dword ptr [rbp+290h+var_2B8], eax
0x180008b6b  jz      loc_180008C68
0x180008b71  mov     [rbp+290h+var_2C0], 0
0x180008b79  lea     r8, [rbp+290h+var_2C0]; unsigned __int64 *
0x180008b7d  mov     rdx, r13; struct CThumbnailMoniker *
0x180008b80  mov     rcx, r14; this
0x180008b83  call    ?_TryGetThumbInfoFromCache@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@PEA_K@Z; CThumbnailCache::_TryGetThumbInfoFromCache(CThumbnailMoniker &,unsigned __int64 *)
0x180008b88  mov     esi, eax
0x180008b8a  test    eax, eax
0x180008b8c  js      short loc_180008BC3
0x180008b8e  mov     r8, [rbp+290h+var_2C0]
0x180008b92  mov     rdx, r8
0x180008b95  shr     rdx, 0Ch
0x180008b99  and     edx, 7FFh; unsigned int
0x180008b9f  jbe     short loc_180008BF7
0x180008ba1  and     r8d, 7FFh; unsigned int
0x180008ba8  jbe     short loc_180008BF7
0x180008baa  lea     rax, [rbp+290h+var_2A8]
0x180008bae  mov     [rsp+390h+var_370], rax; unsigned int *
0x180008bb3  mov     r9d, r12d; enum WTS_FLAGS
0x180008bb6  mov     rcx, r14; this
0x180008bb9  call    ?_CalculateIdealLengthForCropping@CThumbnailCache@@AEAAJIIW4WTS_FLAGS@@PEAI@Z; CThumbnailCache::_CalculateIdealLengthForCropping(uint,uint,WTS_FLAGS,uint *)
0x180008bbe  mov     esi, eax
0x180008bc0  mov     ebx, [rbp+290h+var_2A8]
0x180008bc3  test    esi, esi
0x180008bc5  js      short loc_180008BFC
0x180008bc7  cmp     [rbp+290h+arg_30], 0
0x180008bce  jz      loc_180008C57
0x180008bd4  mov     edx, ebx
0x180008bd6  mov     rcx, r14
0x180008bd9  call    ?_GetNextThumbSizeFromPixelSize@CThumbnailCache@@AEAA?AW4THUMBSIZE@@I@Z; CThumbnailCache::_GetNextThumbSizeFromPixelSize(uint)
0x180008bde  cmp     eax, 0FFFFFFFFh
0x180008be1  jz      short loc_180008C57
0x180008be3  mov     r13d, 1
0x180008be9  mov     [rbp+290h+arg_30], r13d
0x180008bf0  mov     [rsp+390h+var_31F], r13b
0x180008bf5  jmp     short loc_180008C6F
0x180008bf7  mov     esi, 80004005h
0x180008bfc  mov     r13d, [rbp+290h+arg_30]
0x180008c03  cmp     esi, 80041221h
0x180008c09  jz      loc_18000957D
0x180008c0f  lea     eax, [rsi+7FFB4E00h]
0x180008c15  cmp     eax, 1
0x180008c18  jbe     loc_18000957D
0x180008c1e  cmp     esi, 8007000Eh
0x180008c24  jz      loc_18000957D
0x180008c2a  test    byte ptr [r14+300h], 1
0x180008c32  jnz     loc_18000957D
0x180008c38  test    r12b, 1
0x180008c3c  jnz     loc_18000957D
0x180008c42  test    r12d, r12d
0x180008c45  jns     loc_180008E92
0x180008c4b  mov     ecx, ebx
0x180008c4d  call    ?GetNextThumbSizeFromPixelSizeWideAlt@@YA?AW4THUMBSIZE@@I@Z; GetNextThumbSizeFromPixelSizeWideAlt(uint)
0x180008c52  jmp     loc_180008E9C
0x180008c57  xor     r13d, r13d
0x180008c5a  mov     [rbp+290h+arg_30], r13d
0x180008c61  mov     [rsp+390h+var_31F], 1
0x180008c66  jmp     short loc_180008C6F
0x180008c68  mov     r13d, [rbp+290h+arg_30]
0x180008c6f  test    byte ptr [r14+300h], 1
0x180008c77  jnz     short loc_180008CB0
0x180008c79  test    r12b, 4
0x180008c7d  jz      short loc_180008CB0
0x180008c7f  mov     rcx, [r14+30h]
0x180008c83  test    rcx, rcx
0x180008c86  jz      short loc_180008CA6
0x180008c88  mov     [rsp+390h+var_370], 0
0x180008c91  xor     r9d, r9d
0x180008c94  mov     r8d, 0Eh
0x180008c9a  mov     rdx, [rbp+290h+var_300]
0x180008c9e  mov     rdx, [rdx]
0x180008ca1  call    ?Delete@CThumbnailCacheIndex@@QEAAJ_KW4THUMBSIZE@@KPEAK@Z; CThumbnailCacheIndex::Delete(unsigned __int64,THUMBSIZE,ulong,ulong *)
0x180008ca6  mov     esi, 80030002h
0x180008cab  jmp     loc_180008C2A
0x180008cb0  mov     r15d, r12d
0x180008cb3  and     r15d, 1
0x180008cb7  mov     edx, r15d
0x180008cba  xor     edx, 1
0x180008cbd  mov     eax, edx
0x180008cbf  or      eax, 2
0x180008cc2  test    r13d, r13d
0x180008cc5  cmovnz  edx, eax
0x180008cc8  mov     ecx, edx
0x180008cca  or      ecx, 4
0x180008ccd  bt      r12d, 0Eh
0x180008cd2  cmovnb  ecx, edx
0x180008cd5  mov     edx, ecx
0x180008cd7  or      edx, 20h
0x180008cda  test    r12d, r12d
0x180008cdd  cmovns  edx, ecx
0x180008ce0  mov     esi, edx
0x180008ce2  or      esi, 10h
0x180008ce5  bt      r12d, 0Fh
0x180008cea  cmovnb  esi, edx
0x180008ced  mov     dword ptr [rbp+290h+var_30C+4], esi
0x180008cf0  mov     rcx, [rbp+290h+var_2B0]
0x180008cf4  test    rcx, rcx
0x180008cf7  jz      short loc_180008D0E
0x180008cf9  mov     [rbp+290h+var_2B0], 0
0x180008d01  mov     rax, [rcx]
0x180008d04  mov     rax, [rax+10h]
0x180008d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d0d  nop
0x180008d0e  lea     rax, [rbp+290h+var_2B0]
0x180008d12  mov     [rsp+390h+var_350], rax
0x180008d17  lea     rax, _GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f
0x180008d1e  mov     [rsp+390h+var_358], rax
0x180008d23  lea     rax, [rbp+290h+var_298]
0x180008d27  mov     [rsp+390h+var_360], rax
0x180008d2c  lea     rax, [rsp+390h+var_318]
0x180008d31  mov     [rsp+390h+var_368], rax
0x180008d36  lea     rax, [rbp+290h+hObject]
0x180008d3a  mov     [rsp+390h+var_370], rax
0x180008d3f  mov     r9d, esi
0x180008d42  mov     r8d, ebx
0x180008d45  mov     rdx, [rbp+290h+var_300]
0x180008d49  mov     rcx, r14
0x180008d4c  call    ?_TryGetThumbnailFromCache@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@IW4GFC_FLAGS@@PEAVCGlobalRefCount@@PEAHPEAW4WTS_ALPHATYPE@@AEBU_GUID@@PEAPEAX@Z; CThumbnailCache::_TryGetThumbnailFromCache(CThumbnailMoniker &,uint,GFC_FLAGS,CGlobalRefCount *,int *,WTS_ALPHATYPE *,_GUID const &,void * *)
0x180008d51  mov     esi, eax
0x180008d53  bt      r12d, 0Dh
0x180008d58  jnb     loc_180008E69
0x180008d5e  cmp     [rsp+390h+var_320], 0
0x180008d63  jnz     loc_180008E69
0x180008d69  test    eax, eax
0x180008d6b  jns     loc_180008E69
0x180008d71  cmp     eax, 80041221h
0x180008d76  jz      loc_180008E69
0x180008d7c  lea     ecx, [rax+7FFB4E00h]
0x180008d82  cmp     ecx, 1
0x180008d85  jbe     loc_180008E69
0x180008d8b  cmp     eax, 8007000Eh
0x180008d90  jz      loc_180008E69
0x180008d96  test    byte ptr [r14+300h], 1
0x180008d9e  jnz     loc_180008E69
0x180008da4  test    r15d, r15d
0x180008da7  jnz     loc_180008E69
0x180008dad  mov     r15, [rbp+290h+var_300]
0x180008db1  mov     r9, [r15]
0x180008db4  lea     r8, aThumbnailextra; "ThumbnailExtraction-%I64x"
0x180008dbb  mov     edx, 104h; unsigned __int64
0x180008dc0  lea     rcx, [rbp+290h+Name]; unsigned __int16 *
0x180008dc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008dc9  test    eax, eax
0x180008dcb  js      loc_180008E69
0x180008dd1  lea     r9, [rbp+290h+Name]; lpName
0x180008dd5  mov     eax, 1
0x180008dda  mov     r8d, eax; lMaximumCount
0x180008ddd  mov     edx, eax; lInitialCount
0x180008ddf  xor     ecx, ecx; lpSemaphoreAttributes
0x180008de1  call    cs:__imp_CreateSemaphoreW
0x180008de7  mov     rdi, rax
0x180008dea  mov     [rbp+290h+var_2D8], rax
0x180008dee  test    rax, rax
0x180008df1  jz      short loc_180008E69
0x180008df3  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x180008df9  mov     rcx, rax; hHandle
0x180008dfc  call    cs:__imp_WaitForSingleObject
0x180008e02  test    eax, eax
0x180008e04  jnz     short loc_180008E83
0x180008e06  mov     rcx, [rbp+290h+var_2B0]
0x180008e0a  test    rcx, rcx
0x180008e0d  jz      short loc_180008E24
0x180008e0f  mov     [rbp+290h+var_2B0], 0
0x180008e17  mov     rax, [rcx]
0x180008e1a  mov     rax, [rax+10h]
0x180008e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e23  nop
0x180008e24  lea     rax, [rbp+290h+var_2B0]
0x180008e28  mov     [rsp+390h+var_350], rax
0x180008e2d  lea     rax, _GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f
0x180008e34  mov     [rsp+390h+var_358], rax
0x180008e39  lea     rax, [rbp+290h+var_298]
0x180008e3d  mov     [rsp+390h+var_360], rax
0x180008e42  lea     rax, [rsp+390h+var_318]
0x180008e47  mov     [rsp+390h+var_368], rax
0x180008e4c  lea     rax, [rbp+290h+hObject]
0x180008e50  mov     [rsp+390h+var_370], rax
0x180008e55  mov     r9d, dword ptr [rbp+290h+var_30C+4]
0x180008e59  mov     r8d, ebx
0x180008e5c  mov     rdx, r15
0x180008e5f  mov     rcx, r14
0x180008e62  call    ?_TryGetThumbnailFromCache@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@IW4GFC_FLAGS@@PEAVCGlobalRefCount@@PEAHPEAW4WTS_ALPHATYPE@@AEBU_GUID@@PEAPEAX@Z; CThumbnailCache::_TryGetThumbnailFromCache(CThumbnailMoniker &,uint,GFC_FLAGS,CGlobalRefCount *,int *,WTS_ALPHATYPE *,_GUID const &,void * *)
0x180008e67  mov     esi, eax
0x180008e69  mov     r15d, [rsp+390h+var_318]
0x180008e6e  test    esi, esi
0x180008e70  js      loc_180008C03
0x180008e76  mov     [rsp+390h+var_314], 1
0x180008e7e  jmp     loc_18000957D
0x180008e83  mov     esi, 8004B201h
0x180008e88  mov     r15d, [rsp+390h+var_318]
0x180008e8d  jmp     loc_18000957D
0x180008e92  mov     edx, ebx
0x180008e94  mov     rcx, r14
0x180008e97  call    ?_GetNextThumbSizeFromPixelSize@CThumbnailCache@@AEAA?AW4THUMBSIZE@@I@Z; CThumbnailCache::_GetNextThumbSizeFromPixelSize(uint)
0x180008e9c  mov     [rsp+390h+var_31C], eax
0x180008ea0  bt      r12d, 0Eh
0x180008ea5  jnb     loc_180009061
0x180008eab  test    r12d, r12d
0x180008eae  jns     short loc_180008EBC
0x180008eb0  cmp     ebx, 500h
0x180008eb6  jbe     loc_180009061
0x180008ebc  cmp     [rsp+390h+var_320], 0
0x180008ec1  jz      loc_180008FB7
0x180008ec7  xor     edx, edx
0x180008ec9  mov     [rbp+290h+var_288], rdx
0x180008ecd  mov     rax, [rbp+290h+var_2B0]
0x180008ed1  lea     rcx, [rsp+390h+var_318]
0x180008ed6  mov     [rsp+390h+var_330], rcx
0x180008edb  lea     rcx, [rbp+290h+var_298]
0x180008edf  mov     [rsp+390h+var_338], rcx
0x180008ee4  lea     rcx, [rbp+290h+var_288]
0x180008ee8  mov     [rsp+390h+var_340], rcx
0x180008eed  mov     [rsp+390h+var_348], rax
0x180008ef2  lea     rax, [rbp+290h+hObject]
0x180008ef6  mov     [rsp+390h+var_350], rax
0x180008efb  mov     dword ptr [rsp+390h+var_358], r13d
0x180008f00  mov     dword ptr [rsp+390h+var_360], edx
0x180008f04  mov     eax, [rbp+290h+arg_28]
0x180008f0a  mov     dword ptr [rsp+390h+var_368], eax
0x180008f0e  mov     dword ptr [rsp+390h+var_370], r12d
0x180008f13  mov     r9d, ebx
0x180008f16  mov     r8, [rbp+290h+var_2A0]
0x180008f1a  mov     rdx, [rbp+290h+var_300]
0x180008f1e  mov     rcx, r14
0x180008f21  call    ?_PerformFastExtraction@CThumbnailCache@@AEAAJAEAVCThumbnailMoniker@@PEAUIShellItem@@IW4WTS_FLAGS@@W4WTS_PRIV_FLAGS@@HHPEAVCGlobalRefCount@@PEAUIBitmapResult@@PEAPEAU7@PEAW4WTS_ALPHATYPE@@PEAH@Z; CThumbnailCache::_PerformFastExtraction(CThumbnailMoniker &,IShellItem *,uint,WTS_FLAGS,WTS_PRIV_FLAGS,int,int,CGlobalRefCount *,IBitmapResult *,IBitmapResult * *,WTS_ALPHATYPE *,int *)
0x180008f26  mov     esi, eax
0x180008f28  test    eax, eax
0x180008f2a  js      short loc_180008F73
0x180008f2c  mov     rbx, [rbp+290h+var_288]
0x180008f30  cmp     [rbp+290h+var_2B0], rbx
0x180008f34  jz      short loc_180008F65
  ... truncated ...
```
