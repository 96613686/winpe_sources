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
  __int64 v27; // rcx
  int ThumbnailFromCache; // eax
  struct CThumbnailMoniker *v29; // r15
  char *SemaphoreW; // rax
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rcx
  struct IShellItem *v34; // rsi
  __int64 v35; // rcx
  BOOL CanCache; // eax
  unsigned int v37; // eax
  __int64 v38; // rcx
  unsigned int v39; // r8d
  unsigned int v40; // eax
  __int64 ThumbPixelSize; // r9
  int v42; // r10d
  unsigned int v43; // edx
  __int64 v44; // rcx
  unsigned int v45; // r8d
  int v46; // edx
  int v47; // ecx
  unsigned __int64 v48; // rbx
  __int64 v49; // rcx
  unsigned int v50; // ecx
  int v51; // eax
  struct IShellItem *v52; // rsi
  unsigned int v53; // eax
  unsigned __int64 v54; // rbx
  __int64 v55; // rcx
  CThumbnailCache *v56; // rcx
  unsigned int WideCacheSizeForRequest; // eax
  int v58; // eax
  __int64 v59; // rdx
  struct IShellItem *v60; // rbx
  __int64 v61; // rcx
  unsigned int v62; // ebx
  int v63; // eax
  int v64; // ecx
  struct IShellItem *v65; // rbx
  struct IShellItem *v66; // rbx
  __int64 v67; // rcx
  unsigned int v68; // ebx
  struct IShellItem *v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rcx
  char v73; // [rsp+70h] [rbp-90h]
  char v74; // [rsp+71h] [rbp-8Fh]
  char v75; // [rsp+71h] [rbp-8Fh]
  int v76; // [rsp+74h] [rbp-8Ch]
  int v77; // [rsp+78h] [rbp-88h] BYREF
  BOOL v78; // [rsp+7Ch] [rbp-84h]
  bool v79; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v80; // [rsp+84h] [rbp-7Ch]
  unsigned int v81; // [rsp+88h] [rbp-78h]
  struct CThumbnailMoniker *v82; // [rsp+90h] [rbp-70h]
  _QWORD *v83; // [rsp+98h] [rbp-68h]
  HANDLE hObject[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v85; // [rsp+B0h] [rbp-50h]
  char *v86; // [rsp+B8h] [rbp-48h]
  BOOL *v87; // [rsp+C0h] [rbp-40h]
  BOOL *v88; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v89; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v90; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID v91; // [rsp+E0h] [rbp-20h] BYREF
  struct IShellItem *v92; // [rsp+F0h] [rbp-10h] BYREF
  enum WTS_ALPHATYPE v93; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v94[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v95; // [rsp+108h] [rbp+8h] BYREF
  char v96[16]; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v97; // [rsp+120h] [rbp+20h]
  __int64 v98; // [rsp+128h] [rbp+28h]
  WCHAR Name[264]; // [rsp+130h] [rbp+30h] BYREF

  v80 = a4;
  v92 = a3;
  v82 = a2;
  v13 = a4;
  *(_DWORD *)v91.Data4 = a4;
  v14 = a8;
  v83 = a8;
  v87 = a9;
  v15 = a10;
  v88 = a10;
  *a9 = 0;
  *v15 = 1;
  if ( v14 )
    *v14 = 0;
  *(_QWORD *)&v91.Data1 = 0;
  v78 = 0;
  LODWORD(v95) = 0;
  v16 = 1;
  v77 = 1;
  *(_OWORD *)hObject = 0;
  v85 = 0;
  v93 = WTSAT_UNKNOWN;
  v17 = 0;
  v86 = 0;
  if ( (a5 & 0x82) != 2 || (v73 = 1, IShellItem_IsPartialCloudFilePlaceholder(a3)) )
    v73 = 0;
  if ( !CThumbnailCache::_ShouldConsiderItem((CThumbnailCache *)a1, a3) )
  {
    ThumbInfoFromCache = -2147467259;
    goto LABEL_236;
  }
  v74 = 0;
  LODWORD(v90) = a5 & 0x10000200;
  if ( (a5 & 0x10000200) != 0 )
  {
    v89 = 0;
    ThumbInfoFromCache = CThumbnailCache::_TryGetThumbInfoFromCache((CThumbnailCache *)a1, a2, &v89);
    if ( ThumbInfoFromCache >= 0 )
    {
      v18 = v89;
      if ( ((v89 >> 12) & 0x7FF) == 0 || (v18 = v89 & 0x7FF, (v89 & 0x7FF) == 0) )
      {
        ThumbInfoFromCache = -2147467259;
        goto LABEL_18;
      }
      ThumbInfoFromCache = CThumbnailCache::_CalculateIdealLengthForCropping(
                             (CThumbnailCache *)a1,
                             (v89 >> 12) & 0x7FF,
                             v18,
                             a5,
                             (unsigned int *)v91.Data4);
      v13 = *(_DWORD *)v91.Data4;
    }
    if ( ThumbInfoFromCache >= 0 )
    {
      if ( !a7 || (unsigned int)CThumbnailCache::_GetNextThumbSizeFromPixelSize(a1, v13) == -1 )
      {
        v21 = 0;
        a7 = 0;
        v74 = 1;
      }
      else
      {
        v21 = 1;
        a7 = 1;
        v74 = 1;
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
      CThumbnailCacheIndex::Delete(v20, *(_QWORD *)v82, 14, 0, 0);
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
  v81 = v26;
  v27 = *(_QWORD *)&v91.Data1;
  if ( *(_QWORD *)&v91.Data1 )
  {
    *(_QWORD *)&v91.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  ThumbnailFromCache = CThumbnailCache::_TryGetThumbnailFromCache(
                         a1,
                         v82,
                         v13,
                         v26,
                         hObject,
                         &v77,
                         &v93,
                         &GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f,
                         &v91);
  ThumbInfoFromCache = ThumbnailFromCache;
  if ( (a5 & 0x2000) != 0 && !v73 && ThumbnailFromCache < 0 && ThumbnailFromCache != -2147216863 )
  {
    v20 = (unsigned int)(ThumbnailFromCache + 2147175936);
    if ( (unsigned int)v20 > 1 && ThumbnailFromCache != -2147024882 && (*(_BYTE *)(a1 + 768) & 1) == 0 && (a5 & 1) == 0 )
    {
      v29 = v82;
      if ( (int)StringCchPrintfW(Name, 0x104u, L"ThumbnailExtraction-%I64x", *(_QWORD *)v82) >= 0 )
      {
        SemaphoreW = (char *)CreateSemaphoreW(0, 1, 1, Name);
        v17 = SemaphoreW;
        v86 = SemaphoreW;
        if ( SemaphoreW )
        {
          if ( WaitForSingleObject(SemaphoreW, dwMilliseconds) )
          {
            ThumbInfoFromCache = -2147175935;
            v16 = v77;
            goto LABEL_180;
          }
          v31 = *(_QWORD *)&v91.Data1;
          if ( *(_QWORD *)&v91.Data1 )
          {
            *(_QWORD *)&v91.Data1 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          }
          ThumbInfoFromCache = CThumbnailCache::_TryGetThumbnailFromCache(
                                 a1,
                                 v29,
                                 v13,
                                 v81,
                                 hObject,
                                 &v77,
                                 &v93,
                                 &GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f,
                                 &v91);
        }
      }
    }
  }
  v16 = v77;
  if ( ThumbInfoFromCache >= 0 )
  {
    v78 = 1;
    goto LABEL_180;
  }
LABEL_19:
  if ( ThumbInfoFromCache == -2147216863
    || (unsigned int)(ThumbInfoFromCache + 2147175936) <= 1
    || ThumbInfoFromCache == -2147024882 )
  {
    goto LABEL_180;
  }
LABEL_22:
  if ( (*(_BYTE *)(a1 + 768) & 1) != 0 || (a5 & 1) != 0 )
    goto LABEL_180;
  if ( a5 >= WTS_NONE )
    NextThumbSizeFromPixelSize = CThumbnailCache::_GetNextThumbSizeFromPixelSize(a1, v13);
  else
    NextThumbSizeFromPixelSize = GetNextThumbSizeFromPixelSizeWideAlt(v13);
  v76 = NextThumbSizeFromPixelSize;
  if ( (a5 & 0x4000) == 0 || a5 < WTS_NONE && v13 <= 0x500 )
  {
    v79 = 0;
    CanCache = CThumbsDBStore::CanCache((CThumbsDBStore *)(a1 + 792), v92, &v79);
    v20 = CanCache;
    v81 = CanCache;
    v37 = 256;
    if ( (_DWORD)v20 )
    {
      v20 = 0;
      if ( (*(_BYTE *)(a1 + 768) & 2) == 0 )
        v20 = 96;
      if ( v13 <= (unsigned int)v20 )
      {
        v38 = *(_QWORD *)&v91.Data1;
        if ( *(_QWORD *)&v91.Data1 )
        {
          *(_QWORD *)&v91.Data1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        }
        v39 = 0;
        if ( (*(_BYTE *)(a1 + 768) & 2) == 0 )
          v39 = 96;
        ThumbInfoFromCache = CThumbsDBStore::GetThumbnail((CThumbsDBStore *)(a1 + 792), v92, v39, &v91);
        if ( ThumbInfoFromCache >= 0 )
        {
          v16 = 0;
          v77 = 0;
          v76 = 3;
          goto LABEL_92;
        }
        v37 = 256;
      }
      v43 = qword_180062A8C;
      if ( (*(_BYTE *)(a1 + 768) & 2) != 0 )
        v37 = qword_180062A8C;
      if ( v13 <= v37 )
      {
        v44 = *(_QWORD *)&v91.Data1;
        if ( *(_QWORD *)&v91.Data1 )
        {
          *(_QWORD *)&v91.Data1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          v43 = qword_180062A8C;
        }
        v45 = 256;
        if ( (*(_BYTE *)(a1 + 768) & 2) != 0 )
          v45 = v43;
        ThumbInfoFromCache = CThumbsDBStore::GetThumbnail((CThumbsDBStore *)(a1 + 792), v92, v45, &v91);
        if ( ThumbInfoFromCache >= 0 )
        {
          v16 = 0;
          v46 = 4;
          v76 = 4;
          goto LABEL_133;
        }
      }
    }
LABEL_92:
    if ( v16 && (a5 & 0x80u) == 0 && !IShellItem_IsPartialCloudFilePlaceholder(v92) )
    {
      v20 = 256;
      if ( (a5 & 2) != 0 )
        goto LABEL_103;
      v40 = 256;
      if ( (*(_BYTE *)(a1 + 768) & 2) != 0 )
        v40 = qword_180062A8C;
      if ( v13 <= v40 )
      {
LABEL_103:
        if ( !v21 )
          goto LABEL_116;
        if ( v76 < 4 )
          goto LABEL_104;
        if ( (*(_BYTE *)(a1 + 768) & 2) != 0 )
          LODWORD(v20) = qword_180062A8C;
        if ( v13 == (_DWORD)v20 )
        {
LABEL_104:
          v94[0] = 1;
          ThumbPixelSize = (unsigned int)CThumbnailCache::_GetThumbPixelSize(a1, 1, v76);
        }
        else
        {
LABEL_116:
          v94[0] = 0;
          ThumbPixelSize = v13;
          v42 = 1;
        }
        if ( (a5 & 0x42) == 0x42 || (a5 & 0x10000) != 0 )
          v47 = v42;
        else
          v47 = 0;
        v89 = 0;
        ThumbInfoFromCache = CThumbnailCache::_PerformFastExtraction(
                               a1,
                               v82,
                               v92,
                               ThumbPixelSize,
                               a5,
                               a6,
                               v47,
                               v21,
                               hObject,
                               *(_QWORD *)&v91.Data1,
                               &v89,
                               &v93,
                               &v77);
        if ( ThumbInfoFromCache < 0 )
        {
          v16 = v77;
        }
        else
        {
          v48 = v89;
          if ( *(_QWORD *)&v91.Data1 != v89 )
          {
            if ( v89 )
              (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v89 + 8LL))(v89);
            v49 = *(_QWORD *)&v91.Data1;
            *(_QWORD *)&v91.Data1 = v48;
            if ( v49 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          }
          v16 = v77;
          v13 = *(_DWORD *)v91.Data4;
          if ( !v77 )
            v16 = v94[0] == 0;
        }
        v20 = v89;
        if ( v89 )
        {
          v89 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
    }
    v46 = v76;
LABEL_133:
    if ( (_DWORD)v90 && !v74 )
    {
      if ( ThumbInfoFromCache < 0 )
      {
        if ( !v73 )
        {
          CThumbnailCache::_TryAdjustRequestSizeFromStream((CThumbnailCache *)a1, v92, a5, (unsigned int *)v91.Data4);
          v13 = *(_DWORD *)v91.Data4;
        }
      }
      else
      {
        *(_QWORD *)v94 = 0;
        ThumbInfoFromCache = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)&v91.Data1 + 72LL))(
                               *(_QWORD *)&v91.Data1,
                               v94);
        if ( ThumbInfoFromCache >= 0 )
        {
          ThumbInfoFromCache = CThumbnailCache::_CalculateIdealLengthForCropping(
                                 (CThumbnailCache *)a1,
                                 v94[0],
                                 v94[1],
                                 a5,
                                 (unsigned int *)v91.Data4);
          v13 = *(_DWORD *)v91.Data4;
          if ( ThumbInfoFromCache < 0 )
            goto LABEL_141;
          v50 = v94[1];
          if ( (int)v94[0] > (int)v94[1] )
            v50 = v94[0];
          if ( *(_DWORD *)v91.Data4 > v50 )
LABEL_141:
            v16 = 1;
        }
      }
      v51 = CThumbnailCache::_GetNextThumbSizeFromPixelSize(a1, v13);
      v46 = v51;
      v76 = v51;
      v21 = v21 && v51 != -1;
      a7 = v21;
    }
    if ( !v16 || v73 )
      goto LABEL_175;
    if ( v21 )
    {
      if ( v46 < 6 )
      {
        v94[0] = 0;
        v52 = v92;
        if ( (IShellItem_GetFilePlaceholderStatus(v92, v94) < 0 || (v94[0] & 8) == 0)
          && (unsigned int)_GetPerceivedType(v52) == 4 )
        {
          v46 = 6;
LABEL_161:
          v76 = v46;
          goto LABEL_162;
        }
        v46 = v76;
      }
      if ( v81 )
      {
        if ( v46 < 4 )
          v46 = 4;
        goto LABEL_161;
      }
    }
LABEL_162:
    v89 = 0;
    if ( v21 )
      v53 = CThumbnailCache::_GetThumbPixelSize(a1, 1, v46);
    else
      v53 = v13;
    ThumbInfoFromCache = CThumbnailCache::_PerformFullExtraction(a1, v92, v13, v53, a5, a6, &v89, &a7, &v93);
    if ( ThumbInfoFromCache >= 0 )
    {
      v54 = v89;
      if ( *(_QWORD *)&v91.Data1 != v89 )
      {
        if ( v89 )
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v89 + 8LL))(v89);
        v55 = *(_QWORD *)&v91.Data1;
        *(_QWORD *)&v91.Data1 = v54;
        if ( v55 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      v16 = 0;
      v13 = *(_DWORD *)v91.Data4;
    }
    v20 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = a7;
    v46 = v76;
LABEL_175:
    if ( ThumbInfoFromCache == -2147175936 || ThumbInfoFromCache >= 0 && !v16 && v21 )
    {
      ThumbInfoFromCache = CThumbnailCache::_RecordExtractionTransactionToCache(
                             a1,
                             v92,
                             v82,
                             (const char *)(unsigned int)ThumbInfoFromCache,
                             v46,
                             *(struct IBitmapResult **)&v91.Data1,
                             v93,
                             v81,
                             &v95);
      v78 = v95;
    }
    goto LABEL_180;
  }
  if ( v73 )
  {
    v95 = 0;
    ThumbInfoFromCache = CThumbnailCache::_PerformFastExtraction(
                           a1,
                           v82,
                           v92,
                           v13,
                           a5,
                           a6,
                           0,
                           v21,
                           hObject,
                           *(_QWORD *)&v91.Data1,
                           &v95,
                           &v93,
                           &v77);
    if ( ThumbInfoFromCache < 0 )
    {
      v16 = v77;
    }
    else
    {
      v32 = v95;
      if ( *(_QWORD *)&v91.Data1 != v95 )
      {
        if ( v95 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 8LL))(v95);
        v33 = *(_QWORD *)&v91.Data1;
        *(_QWORD *)&v91.Data1 = v32;
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v16 = 1;
      v21 = 0;
      v13 = *(_DWORD *)v91.Data4;
    }
    v20 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
  }
  else if ( CThumbnailCache::_ShouldTryToExtract((CThumbnailCache *)a1, ThumbInfoFromCache, a5) )
  {
    *(_DWORD *)v91.Data4 = CThumbnailCache::s_GetWideCacheSizeForRequest(v13);
    v34 = v92;
    CThumbnailCache::_TryAdjustRequestSizeFromStream((CThumbnailCache *)a1, v92, a5, (unsigned int *)v91.Data4);
    v35 = *(_QWORD *)&v91.Data1;
    if ( *(_QWORD *)&v91.Data1 )
    {
      *(_QWORD *)&v91.Data1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v13 = *(_DWORD *)v91.Data4;
    ThumbInfoFromCache = CThumbnailCache::_PerformFullExtraction(
                           a1,
                           v34,
                           *(unsigned int *)v91.Data4,
                           *(unsigned int *)v91.Data4,
                           a5,
                           a6,
                           &v91,
                           &a7,
                           &v93);
    v21 = a7;
    if ( ThumbInfoFromCache >= 0 )
    {
      v16 = 0;
      goto LABEL_180;
    }
  }
  if ( ThumbInfoFromCache == -2147175936 )
    CThumbnailCache::_AddNegativeThumbnailToCache((CThumbnailCache *)a1, v92, v82);
LABEL_180:
  if ( (_DWORD)v90 && (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    LODWORD(v90) = v13;
    v97 = &v90;
    v98 = 4;
    McGenEventWrite_EventWriteTransfer(v20, &Thumbnails_CropLookupSize_Info, v18, 2, v96);
  }
  if ( ThumbInfoFromCache < 0 )
    goto LABEL_234;
  if ( !v83 )
    goto LABEL_233;
  if ( (a5 & 0x80004000) == 0 || v78 || v16 || !v21 )
    goto LABEL_209;
  v92 = 0;
  LODWORD(v90) = a5 & 0x4000;
  v56 = (CThumbnailCache *)v80;
  if ( (a5 & 0x4000) != 0
    && (WideCacheSizeForRequest = CThumbnailCache::s_GetWideCacheSizeForRequest(v80),
        WideCacheSizeForRequest > (unsigned int)v56) )
  {
    v75 = 0;
    v58 = CThumbnailCache::_PostProcessThumbnail(
            (CThumbnailCache *)&v92,
            a5,
            WideCacheSizeForRequest,
            *(struct IBitmapResult **)&v91.Data1,
            (struct IBitmapResult **)&v92);
  }
  else
  {
    v75 = 1;
    v58 = CThumbnailCache::_PostProcessThumbnail(
            v56,
            a5,
            (unsigned int)v56,
            *(struct IBitmapResult **)&v91.Data1,
            (struct IBitmapResult **)&v92);
  }
  ThumbInfoFromCache = v58;
  if ( v58 >= 0 )
  {
    v59 = *(_QWORD *)&v91.Data1;
    v60 = v92;
    if ( *(struct IShellItem **)&v91.Data1 != v92 )
    {
      if ( v92 )
      {
        ((void (__fastcall *)(struct IShellItem *))v92->lpVtbl->AddRef)(v92);
        v59 = *(_QWORD *)&v91.Data1;
      }
      v61 = v59;
      v59 = (__int64)v60;
      *(_QWORD *)&v91.Data1 = v60;
      if ( v61 )
      {
        (*(void (__fastcall **)(__int64, struct IShellItem *))(*(_QWORD *)v61 + 16LL))(v61, v60);
        v59 = *(_QWORD *)&v91.Data1;
      }
    }
    v62 = 10;
    if ( !(_DWORD)v90 )
      v62 = 12;
    if ( (int)CThumbnailCache::_VerifyValidThumbnail(a1, v59, v62) >= 0 )
    {
      v63 = CThumbnailCache::_AddThumbnailToCache(a1, v82, v62, *(struct IBitmapResult **)&v91.Data1, v93);
      v64 = v78;
      if ( v63 >= 0 )
        v64 = 1;
      v78 = v64;
    }
  }
  v20 = (__int64)v92;
  if ( v92 )
  {
    v92 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( ThumbInfoFromCache < 0 )
    goto LABEL_234;
  if ( !v75 )
  {
LABEL_209:
    v92 = 0;
    ThumbInfoFromCache = CThumbnailCache::_PostProcessThumbnail(
                           (CThumbnailCache *)v20,
                           a5,
                           v80,
                           *(struct IBitmapResult **)&v91.Data1,
                           (struct IBitmapResult **)&v92);
    if ( ThumbInfoFromCache < 0 )
      goto LABEL_229;
    if ( *(_QWORD *)&v91.Data1 )
    {
      v65 = v92;
      if ( v92 )
      {
        if ( *(struct IShellItem **)&v91.Data1 == v92 )
          goto LABEL_229;
        v89 = 0;
        v90 = 0;
        if ( (***(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned __int64 *))&v91.Data1)(
               *(_QWORD *)&v91.Data1,
               &GUID_00000000_0000_0000_c000_000000000046,
               &v89) >= 0 )
        {
          if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))v65->lpVtbl->QueryInterface)(
                 v65,
                 &GUID_00000000_0000_0000_c000_000000000046,
                 &v90) < 0 )
          {
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v89 + 16LL))(v89);
          }
          else
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v89 + 16LL))(v89);
            if ( v89 == v90 )
              goto LABEL_229;
          }
        }
      }
    }
    v66 = v92;
    if ( *(struct IShellItem **)&v91.Data1 != v92 )
    {
      if ( v92 )
        ((void (__fastcall *)(struct IShellItem *))v92->lpVtbl->AddRef)(v92);
      v67 = *(_QWORD *)&v91.Data1;
      *(_QWORD *)&v91.Data1 = v66;
      if ( v67 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    if ( (a5 & 0x10000) != 0 && !v78 && !v16 )
    {
      if ( v21 )
      {
        v68 = CThumbnailCache::_GetNextThumbSizeFromPixelSize(a1, v80);
        if ( (int)CThumbnailCache::_VerifyValidThumbnail(a1, *(__int64 *)&v91.Data1, v68) >= 0 )
          v78 = (int)CThumbnailCache::_AddThumbnailToCache(a1, v82, v68, *(struct IBitmapResult **)&v91.Data1, v93) >= 0;
      }
    }
LABEL_229:
    v69 = v92;
    if ( v92 )
    {
      v92 = 0;
      ((void (__fastcall *)(struct IShellItem *))v69->lpVtbl->Release)(v69);
    }
    if ( ThumbInfoFromCache < 0 )
      goto LABEL_234;
  }
  v70 = *(_QWORD *)&v91.Data1;
  *(_QWORD *)&v91.Data1 = 0;
  *v83 = v70;
LABEL_233:
  *v87 = v78;
  *v88 = v16;
LABEL_234:
  CThumbnailCache::_ResetCacheFilesIfFailedCritically((CThumbnailCache *)a1, ThumbInfoFromCache);
  if ( v17 )
    ReleaseSemaphore(v17, 1, 0);
LABEL_236:
  if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v17);
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  SysFreeString((BSTR)hObject[0]);
  v71 = *(_QWORD *)&v91.Data1;
  if ( *(_QWORD *)&v91.Data1 )
  {
    *(_QWORD *)&v91.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
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
