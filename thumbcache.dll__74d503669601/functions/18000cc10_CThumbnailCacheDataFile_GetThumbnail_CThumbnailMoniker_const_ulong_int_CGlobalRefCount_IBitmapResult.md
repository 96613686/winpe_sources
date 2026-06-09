# CThumbnailCacheDataFile::GetThumbnail(CThumbnailMoniker const &,ulong,int,CGlobalRefCount *,IBitmapResult * *)

- ea: `0x18000cc10`
- end: `0x18000d492`
- name: `?GetThumbnail@CThumbnailCacheDataFile@@QEAAJAEBVCThumbnailMoniker@@KHPEAVCGlobalRefCount@@PEAPEAUIBitmapResult@@@Z`
- size: `2178`
- prototype: `__int64 __fastcall(struct IUnknown *this, const struct CThumbnailMoniker *, __int64, int, struct CGlobalRefCount *, struct IBitmapResult **)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013d80`
- `0x18002e588`

## callees

- `0x180003624`
- `0x180008540`
- `0x18000cc10`
- `0x18000e624`
- `0x180010b34`
- `0x180010ba0`
- `0x180012f3c`
- `0x180013008`
- `0x180015798`
- `0x1800182e0`
- `0x180022e44`
- `0x18002321c`
- `0x180023bd4`
- `0x180023e68`
- `0x180025ac4`
- `0x180027f04`
- `0x180029054`
- `0x180029a38`
- `0x18002a1bc`
- `0x18002b024`
- `0x18002b11c`
- `0x180035830`
- `0x180035860`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cd98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d09d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d285`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000cd98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d09d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d285`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cd39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d031`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d24e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cd39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d031`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d24e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d45c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000d45c`
- `GDI32!DeleteObject` at `0x18000d473`
- `GDI32!DeleteObject` at `0x18000d473`
- `GDI32!GetObjectW` at `0x18000cf7c`
- `GDI32!GetObjectW` at `0x18000cf7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CThumbnailCacheDataFile::GetThumbnail(
        struct IUnknown *this,
        const struct CThumbnailMoniker *a2,
        __int64 a3,
        int a4,
        struct CGlobalRefCount *a5,
        struct IBitmapResult **a6)
{
  int v6; // ebx
  unsigned int v7; // r12d
  struct IUnknown *v9; // r13
  int ThumbnailStreamAtOffset; // edi
  char *v11; // r15
  int v12; // r14d
  RTL_SRWLOCK *v13; // rsi
  unsigned int v14; // r12d
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // edi
  unsigned int j; // r8d
  __int64 v19; // rdx
  HANDLE v20; // rsi
  _DWORD *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  struct IUnknown *v25; // rbx
  HBITMAP *v26; // rsi
  CThumbnailCacheDataFile *v27; // rcx
  unsigned int v29; // edi
  HBITMAP *v30; // r12
  struct IUnknownVtbl *v31; // r15
  unsigned int v32; // r12d
  unsigned int i; // r8d
  __int64 v34; // rdx
  unsigned int Ptr; // ecx
  void *v36; // r15
  __int64 v37; // rdx
  RTL_SRWLOCK *v38; // rax
  CThumbnailCacheDataFile *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // r9
  const struct tagSIZE *v42; // r9
  int View; // eax
  unsigned int *v44; // [rsp+20h] [rbp-C9h]
  HBITMAP *v45; // [rsp+28h] [rbp-C1h]
  unsigned int v46; // [rsp+40h] [rbp-A9h]
  unsigned int v47; // [rsp+40h] [rbp-A9h]
  struct IUnknownVtbl *lpBaseAddress; // [rsp+48h] [rbp-A1h]
  char *v49; // [rsp+50h] [rbp-99h]
  CMappingManager *v50; // [rsp+60h] [rbp-89h]
  int v51; // [rsp+68h] [rbp-81h]
  HANDLE h; // [rsp+78h] [rbp-71h] BYREF
  __int128 pv; // [rsp+80h] [rbp-69h] BYREF
  __int128 v54; // [rsp+90h] [rbp-59h]
  CThumbnailCacheDataFile *v55; // [rsp+A0h] [rbp-49h] BYREF
  struct IUnknown *v56; // [rsp+A8h] [rbp-41h] BYREF
  unsigned int v57[2]; // [rsp+B0h] [rbp-39h] BYREF
  struct IStream *v58; // [rsp+B8h] [rbp-31h] BYREF
  HBITMAP *v59; // [rsp+C0h] [rbp-29h] BYREF
  _OWORD v60[2]; // [rsp+C8h] [rbp-21h] BYREF

  v6 = a4;
  LODWORD(v58) = a4;
  v7 = a3;
  v46 = a3;
  h = a2;
  v9 = this;
  v59 = (HBITMAP *)a6;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, &Thumbnails_CacheDataFile_GetThumbnail_Start, a3, 1, v60);
  if ( a6 )
    *a6 = 0;
  if ( v6
    || (ThumbnailStreamAtOffset = CThumbnailCacheDataFile::_CheckForCacheReset((CThumbnailCacheDataFile *)v9),
        ThumbnailStreamAtOffset >= 0) )
  {
    v49 = 0;
    v50 = 0;
    v11 = 0;
    v12 = -2147467259;
    if ( v9[52].lpVtbl == (struct IUnknownVtbl *)-1LL )
    {
      ThumbnailStreamAtOffset = -2147019890;
      if ( !v6
        || (ThumbnailStreamAtOffset = CFileHandleCache::GetFileHandle(
                                        (CFileHandleCache *)this,
                                        (const unsigned __int16 *)&v9[53].lpVtbl + 2,
                                        (void **)&v9[52].lpVtbl),
            ThumbnailStreamAtOffset < 0) )
      {
        v13 = (RTL_SRWLOCK *)&v9[9];
        this = 0;
LABEL_53:
        if ( ThumbnailStreamAtOffset < 0 )
          goto LABEL_42;
        v29 = v7 + 56 + *((_DWORD *)v11 + 4) + *((_DWORD *)v11 + 5);
        LODWORD(v55) = v29;
        v30 = v59;
        if ( v59 )
        {
          if ( !a5 )
          {
            v55 = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
            ThumbnailStreamAtOffset = CThumbnailCacheDataFile::_GetThumbnailStreamAtOffset(
                                        (RTL_SRWLOCK *)v9,
                                        v29,
                                        *((_DWORD *)v11 + 6),
                                        v41,
                                        v6,
                                        (const struct _GUID *)v45,
                                        (void **)&v55);
            if ( ThumbnailStreamAtOffset >= 0 )
            {
              v59 = *(HBITMAP **)(v11 + 28);
              ThumbnailStreamAtOffset = Windows::Internal::Thumbnails::CreateBitmapResult(
                                          v55,
                                          0,
                                          (const unsigned __int16 *)&v59,
                                          v42,
                                          (const int *)v44,
                                          (const struct _GUID *)v30);
            }
            this = (struct IUnknown *)v55;
            if ( v55 )
            {
              v55 = 0;
              ((void (__fastcall *)(struct IUnknown *))this->lpVtbl->Release)(this);
            }
            goto LABEL_42;
          }
          *(_QWORD *)&v60[0] = *((_QWORD *)v11 + 5);
          v47 = *((_DWORD *)v11 + 6);
          h = 0;
          LODWORD(v56) = -2147467259;
          v31 = 0;
          lpBaseAddress = 0;
          v32 = 0;
          v57[0] = 0;
          AcquireSRWLockShared(v13 + 42);
          for ( i = 0; i < 0xA; ++i )
          {
            v34 = 4LL * i;
            if ( v13[v34 + 3].Ptr )
            {
              Ptr = (unsigned int)v13[v34 + 4].Ptr;
              if ( v29 >= Ptr && v47 + v29 < HIDWORD(v13[v34 + 4].Ptr) + Ptr )
              {
                LODWORD(v56) = 0;
                _InterlockedIncrement((volatile signed __int32 *)&v13[v34 + 2]);
                v31 = (struct IUnknownVtbl *)v13[v34 + 3].Ptr;
                lpBaseAddress = v31;
                v32 = v29 - LODWORD(v13[v34 + 4].Ptr);
                v57[0] = v32;
                break;
              }
            }
          }
          if ( v13 != (RTL_SRWLOCK *)-336LL )
            ReleaseSRWLockShared(v13 + 42);
          if ( (int)v56 >= 0 )
          {
            LODWORD(v56) = 1;
            goto LABEL_66;
          }
          pv = 0;
          v54 = 0;
          if ( (int)CMappingManager::_CreateView((CMappingManager *)v13, 0, v29, v47, v57, (struct MAPPED_VIEW *)&pv) >= 0 )
          {
            v31 = (struct IUnknownVtbl *)*((_QWORD *)&pv + 1);
            lpBaseAddress = (struct IUnknownVtbl *)*((_QWORD *)&pv + 1);
            LODWORD(v56) = CMappingManager::_CacheView((CMappingManager *)v13, (struct MAPPED_VIEW *)&pv);
            v32 = v57[0];
LABEL_66:
            ThumbnailStreamAtOffset = -2147024882;
            if ( !(_DWORD)v58 || (unsigned int)IsBufferPagedIn(v31, v47) )
            {
              v58 = 0;
              v12 = -2147024882;
              v36 = operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
              *(_QWORD *)v57 = v36;
              if ( v36 )
              {
                *(_QWORD *)v36 = &CStreamOnPointer::`vftable';
                *((_QWORD *)v36 + 2) = 0;
                *((_QWORD *)v36 + 8) = 0;
                *((_QWORD *)v36 + 9) = 0;
                *((_QWORD *)v36 + 10) = 0;
                *((_DWORD *)v36 + 2) = 1;
                *((_QWORD *)v36 + 4) = (char *)lpBaseAddress + v32;
                if ( *((struct IUnknown **)v36 + 2) != v9 )
                  ATL::AtlComPtrAssign((struct IUnknown **)v36 + 2, v9);
                v37 = *((_QWORD *)v36 + 4);
                *((_QWORD *)v36 + 5) = v37 + v47;
                *((_QWORD *)v36 + 3) = v37;
                v12 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IStream **))v36)(v36, &IID_IStream, &v58);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
                if ( v12 >= 0 )
                {
                  v38 = 0;
                  *(_QWORD *)v57 = 0;
                  if ( v58 )
                  {
                    (**(void (__fastcall ***)(struct IStream *, GUID *, unsigned int *))v58)(
                      v58,
                      &GUID_e237bfd4_55c8_471c_864b_f39e6844c388,
                      v57);
                    v38 = *(RTL_SRWLOCK **)v57;
                  }
                  v38[6].Ptr = v13->Ptr;
                  v39 = (CThumbnailCacheDataFile *)(unsigned int)v55;
                  *(_DWORD *)(*(_QWORD *)v57 + 56LL) = (_DWORD)v55;
                  v55 = 0;
                  v12 = CThumbnailCacheDataFile::_ComputeBitmapStreamChecksum(v39, v58, v47, (unsigned __int64 *)&v55);
                  if ( v12 < 0 || *(CThumbnailCacheDataFile **)&v60[0] == v55 )
                  {
                    if ( v12 >= 0 )
                      v12 = (*(__int64 (__fastcall **)(struct IUnknownVtbl *, struct IStream *, HANDLE *))v9[119].lpVtbl->QueryInterface)(
                              v9[119].lpVtbl,
                              v58,
                              &h);
                  }
                  else
                  {
                    v12 = -2147287038;
                  }
                  if ( *(_QWORD *)v57 )
                    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v57 + 16LL))(*(_QWORD *)v57);
                }
              }
              if ( v58 )
                (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v58 + 16LL))(v58);
              v31 = lpBaseAddress;
            }
            AcquireSRWLockShared(v13 + 42);
            for ( this = 0; ; this = (struct IUnknown *)(unsigned int)((_DWORD)this + 1) )
            {
              if ( (unsigned int)this >= 0xA )
              {
                UnmapViewOfFile(v31);
                goto LABEL_89;
              }
              v40 = 4LL * (unsigned int)this;
              if ( v31 == v9[v40 + 12].lpVtbl )
                break;
            }
            if ( (_DWORD)v56 )
              _InterlockedDecrement((volatile signed __int32 *)&v9[v40 + 11]);
LABEL_89:
            if ( v13 != (RTL_SRWLOCK *)-336LL )
              ReleaseSRWLockShared(v13 + 42);
            if ( v12 >= 0 )
            {
              v56 = 0;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
              v20 = h;
              v21 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
              *(_QWORD *)&v60[0] = v21;
              if ( !v21 )
                goto LABEL_112;
              *(_QWORD *)v21 = &CSharedBitmap::`vftable';
              v21[2] = 1;
              *((_QWORD *)v21 + 4) = 0;
              *((_QWORD *)v21 + 5) = 0;
              *((_QWORD *)v21 + 6) = 0;
              v21[14] = 0;
              DllAddRef();
              CGlobalRefCount::Transfer((CGlobalRefCount *)(v21 + 10), a5);
              *((_QWORD *)v21 + 2) = v20;
              v21[6] = 0;
              if ( !v20 || (pv = 0, v54 = 0, GetObjectW(v20, 32, &pv), *((_QWORD *)&v54 + 1)) )
              {
                v20 = 0;
                ThumbnailStreamAtOffset = (**(__int64 (__fastcall ***)(void *, GUID *, struct IUnknown **))v21)(
                                            v21,
                                            &GUID_091162a4_bc96_411f_aae8_c5122cd03363,
                                            &v56);
              }
              else
              {
                ThumbnailStreamAtOffset = -2147024809;
              }
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v21 + 16LL))(v21);
              if ( ThumbnailStreamAtOffset >= 0 )
              {
                v25 = v56;
                v26 = v59;
                *v59 = 0;
                v55 = 0;
                ThumbnailStreamAtOffset = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Thumbnails::CBitmapResult,IBitmapResult,>(
                                            &v55,
                                            v22,
                                            v23,
                                            v24);
                if ( ThumbnailStreamAtOffset >= 0 )
                {
                  ThumbnailStreamAtOffset = (*(__int64 (__fastcall **)(CThumbnailCacheDataFile *, struct IUnknown *))(*(_QWORD *)v55 + 40LL))(
                                              v55,
                                              v25);
                  if ( ThumbnailStreamAtOffset >= 0 )
                    ThumbnailStreamAtOffset = (**(__int64 (__fastcall ***)(CThumbnailCacheDataFile *, GUID *, HBITMAP *))v55)(
                                                v55,
                                                &GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f,
                                                v26);
                }
                v27 = v55;
                if ( v55 )
                {
                  v55 = 0;
                  (*(void (__fastcall **)(CThumbnailCacheDataFile *))(*(_QWORD *)v27 + 16LL))(v27);
                }
              }
              else
              {
LABEL_112:
                if ( v20 )
                  DeleteObject(v20);
              }
              this = v56;
              if ( v56 )
              {
                v56 = 0;
                ((void (__fastcall *)(struct IUnknown *))this->lpVtbl->Release)(this);
              }
              goto LABEL_42;
            }
            goto LABEL_28;
          }
          goto LABEL_104;
        }
        ThumbnailStreamAtOffset = CThumbnailCacheDataFile::_GetThumbnailAtOffset(
                                    (RTL_SRWLOCK *)v9,
                                    v29,
                                    *((_DWORD *)v11 + 6),
                                    *((CThumbnailCacheDataFile **)v11 + 5),
                                    v6,
                                    0);
LABEL_42:
        if ( v49 )
          CMappingManager::ReleaseView(v50, v49, v51);
        goto LABEL_44;
      }
    }
    ThumbnailStreamAtOffset = CThumbnailCacheDataFile::_RemapOrGrowMapping((CThumbnailCacheDataFile *)v9, 0);
    if ( ThumbnailStreamAtOffset < 0 )
      goto LABEL_42;
    v14 = 56;
    if ( (*((_BYTE *)a2 + 12) & 2) != 0 )
    {
      v15 = *((_QWORD *)a2 + 2);
      if ( v15 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(v15 + 2 * v16) );
      }
      else
      {
        LODWORD(v16) = 0;
      }
      v14 = 2 * v16 + 56;
    }
    v13 = (RTL_SRWLOCK *)&v9[9];
    v51 = 0;
    LODWORD(v56) = -2147467259;
    v49 = 0;
    v17 = 0;
    v57[0] = 0;
    AcquireSRWLockShared((PSRWLOCK)&v9[51]);
    for ( j = 0; j < 0xA; ++j )
    {
      v19 = 4LL * j;
      if ( v13[v19 + 3].Ptr )
      {
        this = (struct IUnknown *)LODWORD(v13[v19 + 4].Ptr);
        if ( v46 >= (unsigned int)this )
        {
          this = (struct IUnknown *)(unsigned int)(HIDWORD(v13[v19 + 4].Ptr) + (_DWORD)this);
          if ( v46 + v14 < (unsigned int)this )
          {
            LODWORD(v56) = 0;
            _InterlockedIncrement((volatile signed __int32 *)&v13[v19 + 2]);
            v49 = (char *)v13[v19 + 3].Ptr;
            v17 = v46 - LODWORD(v13[v19 + 4].Ptr);
            v57[0] = v17;
            break;
          }
        }
      }
    }
    if ( v9 != (struct IUnknown *)-408LL )
      ReleaseSRWLockShared((PSRWLOCK)&v9[51]);
    if ( (int)v56 < 0 )
    {
      memset(v60, 0, sizeof(v60));
      View = CMappingManager::_CreateView((CMappingManager *)&v9[9], 0, v46, v14, v57, (struct MAPPED_VIEW *)v60);
      ThumbnailStreamAtOffset = View;
      this = 0;
      if ( View < 0 )
      {
        if ( View == -2147024891 )
        {
LABEL_104:
          ThumbnailStreamAtOffset = -2147287038;
          goto LABEL_42;
        }
        v6 = (int)v58;
LABEL_52:
        v7 = v46;
        goto LABEL_53;
      }
      v49 = (char *)*((_QWORD *)&v60[0] + 1);
      v51 = CMappingManager::_CacheView((CMappingManager *)&v9[9], (struct MAPPED_VIEW *)v60);
      v17 = v57[0];
    }
    else
    {
      v51 = 1;
    }
    v50 = (CMappingManager *)&v9[9];
    v11 = &v49[v17];
    if ( !v11 || (v6 = (int)v58) != 0 && !(unsigned int)IsBufferPagedIn(&v49[v17], v14) )
    {
LABEL_28:
      ThumbnailStreamAtOffset = v12;
      goto LABEL_42;
    }
    ThumbnailStreamAtOffset = CThumbnailCacheDataFile::_CheckValidHeader(
                                (CThumbnailCacheDataFile *)this,
                                (const struct DataFileEntryHeaderAligned *)v11);
    if ( ThumbnailStreamAtOffset < 0 )
      goto LABEL_42;
    ThumbnailStreamAtOffset = CThumbnailCacheDataFile::_VerifyUrlAndCrcKeyMatch(
                                (CThumbnailCacheDataFile *)this,
                                (const struct DataFileEntryHeaderAligned *)v11,
                                (const struct CThumbnailMoniker *)h);
    this = 0;
    if ( ThumbnailStreamAtOffset < 0 )
      goto LABEL_42;
    goto LABEL_52;
  }
LABEL_44:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(
      this,
      &Thumbnails_CacheDataFile_GetThumbnail_Stop,
      (unsigned int)ThumbnailStreamAtOffset);
  return (unsigned int)ThumbnailStreamAtOffset;
}

```

## disassembly

```asm
0x18000cc10  push    rbp
0x18000cc12  push    rbx
0x18000cc13  push    rsi
0x18000cc14  push    rdi
0x18000cc15  push    r12
0x18000cc17  push    r13
0x18000cc19  push    r14
0x18000cc1b  push    r15
0x18000cc1d  lea     rbp, [rsp-0Fh]
0x18000cc22  sub     rsp, 0F8h
0x18000cc29  mov     rax, cs:__security_cookie
0x18000cc30  xor     rax, rsp
0x18000cc33  mov     [rbp+47h+var_48], rax
0x18000cc37  mov     ebx, r9d
0x18000cc3a  mov     dword ptr [rbp+47h+var_78], ebx
0x18000cc3d  mov     r12d, r8d
0x18000cc40  mov     [rsp+130h+var_F0], r8d
0x18000cc45  mov     rsi, rdx
0x18000cc48  mov     [rbp+47h+h], rdx
0x18000cc4c  mov     r13, rcx
0x18000cc4f  mov     rax, [rbp+47h+arg_20]
0x18000cc53  mov     [rbp+47h+var_C0], rax
0x18000cc57  mov     rdi, [rbp+47h+arg_28]
0x18000cc5b  mov     [rbp+47h+var_70], rdi
0x18000cc5f  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18000cc66  jnz     loc_18000D3E2
0x18000cc6c  xor     r14d, r14d
0x18000cc6f  test    rdi, rdi
0x18000cc72  jz      short loc_18000CC77
0x18000cc74  mov     [rdi], r14
0x18000cc77  test    ebx, ebx
0x18000cc79  jnz     short loc_18000CC8D
0x18000cc7b  mov     rcx, r13; this
0x18000cc7e  call    ?_CheckForCacheReset@CThumbnailCacheDataFile@@AEAAJXZ; CThumbnailCacheDataFile::_CheckForCacheReset(void)
0x18000cc83  mov     edi, eax
0x18000cc85  test    eax, eax
0x18000cc87  js      loc_18000CF36
0x18000cc8d  xorps   xmm0, xmm0
0x18000cc90  movdqu  xmmword ptr [rsp+130h+var_E0], xmm0
0x18000cc96  mov     [rsp+130h+var_D0], r14
0x18000cc9b  mov     r15, r14
0x18000cc9e  lea     r8, [r13+1A0h]; void **
0x18000cca5  mov     r14d, 80004005h
0x18000ccab  cmp     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x18000ccaf  jnz     short loc_18000CCD7
0x18000ccb1  mov     edi, 8007138Eh
0x18000ccb6  test    ebx, ebx
0x18000ccb8  jnz     short loc_18000CCC5
0x18000ccba  lea     rsi, [r13+48h]
0x18000ccbe  xor     ecx, ecx
0x18000ccc0  jmp     loc_18000CFD0
0x18000ccc5  lea     rdx, [r13+1ACh]; unsigned __int16 *
0x18000cccc  call    ?GetFileHandle@CFileHandleCache@@QEAAJPEBGPEAPEAX@Z; CFileHandleCache::GetFileHandle(ushort const *,void * *)
0x18000ccd1  mov     edi, eax
0x18000ccd3  test    eax, eax
0x18000ccd5  js      short loc_18000CCBA
0x18000ccd7  xor     edx, edx; unsigned int
0x18000ccd9  mov     rcx, r13; this
0x18000ccdc  call    ?_RemapOrGrowMapping@CThumbnailCacheDataFile@@AEAAJK@Z; CThumbnailCacheDataFile::_RemapOrGrowMapping(ulong)
0x18000cce1  mov     edi, eax
0x18000cce3  xor     edx, edx
0x18000cce5  test    eax, eax
0x18000cce7  js      loc_18000CF1A
0x18000cced  lea     r12d, [rdx+38h]
0x18000ccf1  test    byte ptr [rsi+0Ch], 2
0x18000ccf5  jz      short loc_18000CD19
0x18000ccf7  mov     rcx, [rsi+10h]
0x18000ccfb  test    rcx, rcx
0x18000ccfe  jz      loc_18000D402
0x18000cd04  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cd08  inc     rax
0x18000cd0b  cmp     [rcx+rax*2], dx
0x18000cd0f  jnz     short loc_18000CD08
0x18000cd11  lea     r12d, ds:38h[rax*2]
0x18000cd19  lea     rsi, [r13+48h]
0x18000cd1d  mov     [rsp+130h+var_C8], edx
0x18000cd21  mov     dword ptr [rbp+47h+var_88], r14d
0x18000cd25  mov     [rsp+130h+var_E0], rdx
0x18000cd2a  mov     edi, edx
0x18000cd2c  mov     [rbp+47h+var_80], edx
0x18000cd2f  lea     rbx, [rsi+150h]
0x18000cd36  mov     rcx, rbx; SRWLock
0x18000cd39  call    cs:__imp_AcquireSRWLockShared
0x18000cd3f  xor     r10d, r10d
0x18000cd42  mov     r8d, r10d
0x18000cd45  cmp     r8d, 0Ah
0x18000cd49  jnb     short loc_18000CD90
0x18000cd4b  mov     edx, r8d
0x18000cd4e  shl     rdx, 5
0x18000cd52  cmp     [rdx+rsi+18h], r10
0x18000cd57  jz      short loc_18000CDD3
0x18000cd59  mov     ecx, [rdx+rsi+20h]
0x18000cd5d  mov     r9d, [rsp+130h+var_F0]
0x18000cd62  cmp     r9d, ecx
0x18000cd65  jb      short loc_18000CDD3
0x18000cd67  add     ecx, [rdx+rsi+24h]
0x18000cd6b  lea     eax, [r9+r12]
0x18000cd6f  cmp     eax, ecx
0x18000cd71  jnb     short loc_18000CDD3
0x18000cd73  mov     dword ptr [rbp+47h+var_88], r10d
0x18000cd77  lock inc dword ptr [rdx+rsi+10h]
0x18000cd7c  mov     rax, [rdx+rsi+18h]
0x18000cd81  mov     [rsp+130h+var_E0], rax
0x18000cd86  mov     edi, r9d
0x18000cd89  sub     edi, [rdx+rsi+20h]
0x18000cd8d  mov     [rbp+47h+var_80], edi
0x18000cd90  test    rbx, rbx
0x18000cd93  jz      short loc_18000CDA1
0x18000cd95  mov     rcx, rbx; SRWLock
0x18000cd98  call    cs:__imp_ReleaseSRWLockShared
0x18000cd9e  xor     r10d, r10d
0x18000cda1  cmp     dword ptr [rbp+47h+var_88], r10d
0x18000cda5  jl      loc_18000D30D
0x18000cdab  mov     [rsp+130h+var_C8], 1
0x18000cdb3  mov     [rsp+130h+var_D0], rsi
0x18000cdb8  mov     r15d, edi
0x18000cdbb  add     r15, [rsp+130h+var_E0]
0x18000cdc0  mov     [rsp+130h+var_E0+8], r15
0x18000cdc5  jnz     loc_18000CF96
0x18000cdcb  mov     edi, r14d
0x18000cdce  jmp     loc_18000CF1A
0x18000cdd3  inc     r8d
0x18000cdd6  jmp     loc_18000CD45
0x18000cddb  test    r14d, r14d
0x18000cdde  js      short loc_18000CDCB
0x18000cde0  mov     [rbp+47h+var_88], r12
0x18000cde4  lea     rcx, [rbp+47h+var_88]
0x18000cde8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cded  mov     rsi, [rbp+47h+h]
0x18000cdf1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cdf8  mov     ecx, 40h ; '@'; unsigned __int64
0x18000cdfd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ce02  mov     rbx, rax
0x18000ce05  mov     qword ptr [rbp+47h+var_68], rax
0x18000ce09  test    rax, rax
0x18000ce0c  jz      loc_18000D467
0x18000ce12  lea     rax, ??_7CSharedBitmap@@6B@; const CSharedBitmap::`vftable'
0x18000ce19  mov     [rbx], rax
0x18000ce1c  mov     dword ptr [rbx+8], 1
0x18000ce23  mov     [rbx+20h], r12
0x18000ce27  mov     [rbx+28h], r12
0x18000ce2b  mov     [rbx+30h], r12
0x18000ce2f  mov     [rbx+38h], r12d
0x18000ce33  call    DllAddRef
0x18000ce38  test    rbx, rbx
0x18000ce3b  jz      loc_18000D467
0x18000ce41  lea     rcx, [rbx+28h]; this
0x18000ce45  mov     rdx, [rbp+47h+var_C0]; struct CGlobalRefCount *
0x18000ce49  call    ?Transfer@CGlobalRefCount@@QEAAXPEAV1@@Z; CGlobalRefCount::Transfer(CGlobalRefCount *)
0x18000ce4e  mov     [rbx+10h], rsi
0x18000ce52  mov     [rbx+18h], r12d
0x18000ce56  test    rsi, rsi
0x18000ce59  jnz     loc_18000CF65
0x18000ce5f  mov     rsi, r12
0x18000ce62  mov     rax, [rbx]
0x18000ce65  lea     r8, [rbp+47h+var_88]
0x18000ce69  lea     rdx, _GUID_091162a4_bc96_411f_aae8_c5122cd03363
0x18000ce70  mov     rcx, rbx
0x18000ce73  mov     rax, [rax]
0x18000ce76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce7b  mov     edi, eax
0x18000ce7d  mov     rax, [rbx]
0x18000ce80  mov     rcx, rbx
0x18000ce83  mov     rax, [rax+10h]
0x18000ce87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce8c  test    edi, edi
0x18000ce8e  js      loc_18000D467
0x18000ce94  mov     rbx, [rbp+47h+var_88]
0x18000ce98  mov     rsi, [rbp+47h+var_70]
0x18000ce9c  mov     [rsi], r12
0x18000ce9f  mov     [rbp+47h+var_90], r12
0x18000cea3  lea     rcx, [rbp+47h+var_90]
0x18000cea7  call    ??$MakeAndInitialize@VCBitmapResult@Thumbnails@Internal@Windows@@UIBitmapResult@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIBitmapResult@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Thumbnails::CBitmapResult,IBitmapResult,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IBitmapResult>>)
0x18000ceac  mov     edi, eax
0x18000ceae  test    eax, eax
0x18000ceb0  js      short loc_18000CEE6
0x18000ceb2  mov     rcx, [rbp+47h+var_90]
0x18000ceb6  mov     rax, [rcx]
0x18000ceb9  mov     rdx, rbx
0x18000cebc  mov     rax, [rax+28h]
0x18000cec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cec5  mov     edi, eax
0x18000cec7  test    eax, eax
0x18000cec9  js      short loc_18000CEE6
0x18000cecb  mov     rcx, [rbp+47h+var_90]
0x18000cecf  mov     rax, [rcx]
0x18000ced2  mov     r8, rsi
0x18000ced5  lea     rdx, _GUID_b11c5842_71c1_4cef_be46_1203d5fdb22f
0x18000cedc  mov     rax, [rax]
0x18000cedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cee4  mov     edi, eax
0x18000cee6  mov     rcx, [rbp+47h+var_90]
0x18000ceea  test    rcx, rcx
0x18000ceed  jz      short loc_18000CF00
0x18000ceef  mov     [rbp+47h+var_90], r12
0x18000cef3  mov     rax, [rcx]
0x18000cef6  mov     rax, [rax+10h]
0x18000cefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceff  nop
0x18000cf00  mov     rcx, [rbp+47h+var_88]
0x18000cf04  test    rcx, rcx
0x18000cf07  jz      short loc_18000CF1A
0x18000cf09  mov     [rbp+47h+var_88], r12
0x18000cf0d  mov     rax, [rcx]
0x18000cf10  mov     rax, [rax+10h]
0x18000cf14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf19  nop
0x18000cf1a  mov     rax, [rsp+130h+var_E0]
0x18000cf1f  test    rax, rax
0x18000cf22  jz      short loc_18000CF36
0x18000cf24  mov     r8d, [rsp+130h+var_C8]; int
0x18000cf29  mov     rdx, rax; void *
0x18000cf2c  mov     rcx, [rsp+130h+var_D0]; this
0x18000cf31  call    ?ReleaseView@CMappingManager@@QEAAJPEAXH@Z; CMappingManager::ReleaseView(void *,int)
0x18000cf36  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18000cf3d  jnz     loc_18000D47E
0x18000cf43  mov     eax, edi
0x18000cf45  mov     rcx, [rbp+47h+var_48]
0x18000cf49  xor     rcx, rsp; StackCookie
0x18000cf4c  call    __security_check_cookie
0x18000cf51  add     rsp, 0F8h
0x18000cf58  pop     r15
0x18000cf5a  pop     r14
0x18000cf5c  pop     r13
0x18000cf5e  pop     r12
0x18000cf60  pop     rdi
0x18000cf61  pop     rsi
0x18000cf62  pop     rbx
0x18000cf63  pop     rbp
0x18000cf64  retn
0x18000cf65  xorps   xmm0, xmm0
0x18000cf68  movups  [rbp+47h+pv], xmm0
0x18000cf6c  movups  [rbp+47h+var_A0], xmm0
0x18000cf70  lea     r8, [rbp+47h+pv]; pv
0x18000cf74  mov     edx, 20h ; ' '; c
0x18000cf79  mov     rcx, rsi; h
0x18000cf7c  call    cs:__imp_GetObjectW
0x18000cf82  cmp     qword ptr [rbp+47h+var_A0+8], r12
0x18000cf86  jnz     loc_18000CE5F
0x18000cf8c  mov     edi, 80070057h
0x18000cf91  jmp     loc_18000CE7D
0x18000cf96  mov     ebx, dword ptr [rbp+47h+var_78]
0x18000cf99  test    ebx, ebx
0x18000cf9b  jnz     loc_18000D3C0
0x18000cfa1  mov     rdx, r15; struct DataFileEntryHeaderAligned *
0x18000cfa4  call    ?_CheckValidHeader@CThumbnailCacheDataFile@@AEAAJPEFBUDataFileEntryHeaderAligned@@@Z; CThumbnailCacheDataFile::_CheckValidHeader(DataFileEntryHeaderAligned const *)
0x18000cfa9  mov     edi, eax
0x18000cfab  test    eax, eax
0x18000cfad  js      loc_18000CF1A
0x18000cfb3  mov     r8, [rbp+47h+h]; struct CThumbnailMoniker *
0x18000cfb7  mov     rdx, r15; struct DataFileEntryHeaderAligned *
0x18000cfba  call    ?_VerifyUrlAndCrcKeyMatch@CThumbnailCacheDataFile@@AEAAJPEFBUDataFileEntryHeaderAligned@@AEBVCThumbnailMoniker@@@Z; CThumbnailCacheDataFile::_VerifyUrlAndCrcKeyMatch(DataFileEntryHeaderAligned const *,CThumbnailMoniker const &)
0x18000cfbf  mov     edi, eax
0x18000cfc1  xor     ecx, ecx
0x18000cfc3  test    eax, eax
0x18000cfc5  js      loc_18000CF1A
0x18000cfcb  mov     r12d, [rsp+130h+var_F0]
0x18000cfd0  test    edi, edi
0x18000cfd2  js      loc_18000CF1A
0x18000cfd8  mov     edi, [r15+14h]
0x18000cfdc  add     edi, [r15+10h]
0x18000cfe0  add     r12d, 38h ; '8'
0x18000cfe4  add     edi, r12d
0x18000cfe7  mov     dword ptr [rbp+47h+var_90], edi
0x18000cfea  mov     r12, [rbp+47h+var_70]
0x18000cfee  test    r12, r12
0x18000cff1  jz      loc_18000D418
0x18000cff7  cmp     [rbp+47h+var_C0], rcx
0x18000cffb  jz      loc_18000D294
0x18000d001  mov     rax, [r15+28h]
0x18000d005  mov     qword ptr [rbp+47h+var_68], rax
0x18000d009  mov     eax, [r15+18h]
0x18000d00d  mov     [rsp+130h+var_F0], eax
0x18000d011  mov     [rbp+47h+h], rcx
0x18000d015  mov     dword ptr [rbp+47h+var_88], r14d
0x18000d019  mov     r15, rcx
0x18000d01c  mov     [rsp+130h+lpBaseAddress], rcx
0x18000d021  mov     r12d, ecx
0x18000d024  mov     [rbp+47h+var_80], ecx
0x18000d027  lea     rbx, [rsi+150h]
0x18000d02e  mov     rcx, rbx; SRWLock
0x18000d031  call    cs:__imp_AcquireSRWLockShared
0x18000d037  xor     r10d, r10d
0x18000d03a  mov     r8d, r10d
0x18000d03d  mov     r9d, [rsp+130h+var_F0]
0x18000d042  cmp     r8d, 0Ah
0x18000d046  jnb     short loc_18000D095
0x18000d048  mov     edx, r8d
0x18000d04b  shl     rdx, 5
0x18000d04f  cmp     [rdx+rsi+18h], r10
0x18000d054  jz      loc_18000D225
0x18000d05a  mov     ecx, [rdx+rsi+20h]
0x18000d05e  cmp     edi, ecx
0x18000d060  jb      loc_18000D225
0x18000d066  add     ecx, [rdx+rsi+24h]
0x18000d06a  lea     eax, [r9+rdi]
0x18000d06e  cmp     eax, ecx
0x18000d070  jnb     loc_18000D225
0x18000d076  mov     dword ptr [rbp+47h+var_88], r10d
0x18000d07a  lock inc dword ptr [rdx+rsi+10h]
  ... truncated ...
```
