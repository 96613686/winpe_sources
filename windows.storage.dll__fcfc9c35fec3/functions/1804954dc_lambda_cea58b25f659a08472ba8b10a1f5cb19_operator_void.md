# _lambda_cea58b25f659a08472ba8b10a1f5cb19_::operator()(void)

- ea: `0x1804954dc`
- end: `0x180495d2b`
- name: `??R_lambda_cea58b25f659a08472ba8b10a1f5cb19_@@QEBAJXZ`
- size: `2127`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802aa858`

## callees

- `0x180009fc0`
- `0x1800118c4`
- `0x18001863c`
- `0x180018ac8`
- `0x18001e7a0`
- `0x180038f50`
- `0x18003c410`
- `0x18006f458`
- `0x1800a0f6c`
- `0x1800a24cc`
- `0x180176d14`
- `0x18021610c`
- `0x180243478`
- `0x18024443c`
- `0x1802527a4`
- `0x18026dbdc`
- `0x1802ba1a8`
- `0x18030deb0`
- `0x1803676d0`
- `0x1803b1f60`
- `0x18049138c`
- `0x180491a64`
- `0x180491b94`
- `0x1804954dc`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1804958c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1804958c9`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x180495c61`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x180495c61`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495969`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804959d0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804959f4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495a1b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495a42`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495a69`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495a8f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495ac5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495b6e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495969`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804959d0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804959f4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495a1b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495a42`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495a69`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495a8f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495ac5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180495b6e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1804958eb`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1804958eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall _lambda_cea58b25f659a08472ba8b10a1f5cb19_::operator()(__int64 a1)
{
  _QWORD **v2; // rax
  CStorageQueryServer *v3; // rbx
  int v4; // eax
  unsigned int v5; // ebx
  CStorageQueryServer *v6; // rcx
  __int64 v7; // rbx
  int v8; // eax
  int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // r12
  Windows::Internal::DeviceCapabilitiesW *v12; // rcx
  __int64 v13; // rcx
  int v14; // r15d
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v18; // ebx
  _DWORD *v19; // r10
  void (__fastcall ***v20)(_QWORD, GUID *, _DWORD *); // r14
  int v21; // r9d
  int v22; // r8d
  int v23; // edx
  int v24; // ecx
  void (__fastcall *v25)(_QWORD, GUID *, _DWORD *); // rdi
  _DWORD *v26; // rbx
  struct IThreadAffineStorageQueryServer *v27; // rdi
  __int64 (__fastcall *v28)(struct IThreadAffineStorageQueryServer *, __int64, GUID *, __int64 *); // rbx
  __int64 v29; // rbx
  __int64 v30; // rdi
  __int64 v31; // rcx
  IStream *v32; // rax
  IStream *v33; // rbx
  __int64 v34; // r9
  __int64 v35; // rdx
  int v36; // ecx
  HRESULT v37; // edi
  __int64 v38; // rdx
  unsigned int v39; // r14d
  __int64 v40; // r15
  void (__fastcall *v41)(__int64, struct IPropertyStore **); // rdi
  int v42; // eax
  __int64 v43; // rdx
  int v44; // eax
  _QWORD **v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  int v49; // [rsp+20h] [rbp-E0h]
  __int64 v50; // [rsp+30h] [rbp-D0h] BYREF
  IStream *pstm; // [rsp+38h] [rbp-C8h] BYREF
  struct IItemCollection *v52; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v53[8]; // [rsp+48h] [rbp-B8h] BYREF
  struct IThreadAffineStorageQueryServer *v54; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int pv; // [rsp+58h] [rbp-A8h] BYREF
  struct IPropertyStore *v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h] BYREF
  int v58; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v60; // [rsp+80h] [rbp-80h] BYREF
  int v61; // [rsp+88h] [rbp-78h] BYREF
  int v62; // [rsp+90h] [rbp-70h] BYREF
  int v63[2]; // [rsp+98h] [rbp-68h] BYREF
  int v64; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v67; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v68[80]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  ***(_QWORD ***)a1 = 0;
  v2 = *(_QWORD ***)(a1 + 8);
  if ( *v2 )
    **v2 = 0;
  WinRTStorageTelemetry::WatchCurrentThread(v68, "STAGetItems");
  Microsoft::WRL::Wrappers::SRWLock::LockShared(v53, *(_QWORD *)(*(_QWORD *)(a1 + 16) + 88LL) + 8LL);
  v66 = 0;
  v65 = 0;
  v52 = 0;
  v3 = *(CStorageQueryServer **)(a1 + 16);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  v4 = CStorageQueryServer::_LockAndEnsureCollection(v3, &v52);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E3,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\fileitemcollections.cpp",
      (const char *)(unsigned int)v4,
      v49);
    goto LABEL_98;
  }
  v6 = *(CStorageQueryServer **)(a1 + 16);
  if ( *((_BYTE *)v6 + 225) && !*((_BYTE *)v6 + 226) )
    CStorageQueryServer::_StartContentsChangedEventInternal(v6);
  v50 = 0;
  v7 = *(_QWORD *)(a1 + 24);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v8 = Microsoft::WRL::Details::MakeAndInitialize<CStorageQueryItemArray,CStorageQueryItemArray,unsigned long &>(
         &v50,
         v7);
  v5 = v8;
  if ( v8 < 0 )
  {
    v10 = 755;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\fileitemcollections.cpp",
      (const char *)(unsigned int)v8,
      v49);
LABEL_11:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    goto LABEL_98;
  }
  v11 = *(_QWORD *)(v50 + 72) + 8LL;
  *(_QWORD *)v63 = v11;
  v8 = CItemCollectionSink::RealizeItemsOnBackgroundThread<_lambda_c2a533ae289fe066ebf4ad507e94ce82_>(
         (_DWORD)v52,
         **(_DWORD **)(a1 + 24),
         **(_DWORD **)(a1 + 32),
         v9,
         (__int64)v63);
  v5 = v8;
  if ( v8 < 0 )
  {
    v10 = 773;
    goto LABEL_10;
  }
  if ( *(_DWORD *)(v11 + 8)
    && !*(_BYTE *)(*(_QWORD *)(a1 + 16) + 225LL)
    && Windows::Internal::DeviceCapabilitiesW::IsLowMemory(v12) )
  {
    v56 = (struct IPropertyStore *)v52;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v56);
    Windows::Internal::ComTaskPool::QueueTask<_lambda_013ffc0c5604ddb8f47a9eb988ef629d_>(v13, &v56);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  }
  v14 = **(_DWORD **)(a1 + 40);
  pv = 0;
  v57 = 5;
  v58 = 4;
  v59 = 100;
  v60 = 0;
  v54 = 0;
  v15 = CMarshaledInterface::Unmarshal<IThreadAffineStorageQueryServer>(
          (CMarshaledInterface *)(*(_QWORD *)(a1 + 16) + 120LL),
          (void **)&v54);
  v5 = v15;
  if ( v15 < 0 )
  {
    v16 = 811;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\fileitemcollections.cpp",
      (const char *)(unsigned int)v15,
      v49);
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    goto LABEL_11;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(v63, *(_QWORD *)(a1 + 16) + 104LL);
  v17 = 176;
  if ( v14 != 1 )
    v17 = 144;
  SPrefetchData::operator=(&v57, *(_QWORD *)(a1 + 16) + v17);
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v63);
  if ( (v60 || v14 == 1)
    && ((int)CStorageQueryServer::_GetIndexedState(
               *(CStorageQueryServer **)(a1 + 16),
               v54,
               (enum Windows::Storage::Search::IndexedState *)&pv) < 0
     || pv != 3) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    HIDWORD(v59) = 0;
  }
  v18 = **(_QWORD **)(a1 + 8) != 0;
  if ( HIDWORD(v57) || v60 )
    v18 |= 2u;
  v64 = 0;
  if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 136LL) + 120LL))(
         *(_QWORD *)(*(_QWORD *)(a1 + 16) + 136LL),
         &v64) >= 0
    && v64 == 3 )
  {
    v18 |= 4u;
  }
  v19 = (_DWORD *)v50;
  v20 = **(void (__fastcall *****)(_QWORD, GUID *, _DWORD *))(a1 + 48);
  v21 = **(_DWORD **)(a1 + 40);
  v22 = v59;
  v23 = v58;
  v24 = HIDWORD(v57);
  *(_DWORD *)(v50 + 88) = v57;
  v19[23] = v24;
  v19[24] = v23;
  v19[25] = v22;
  v19[14] = v21;
  v19[15] = v18;
  if ( v20 )
  {
    v25 = **v20;
    v26 = v19 + 16;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v19 + 16);
    v25(v20, &GUID_60e1feec_e458_4a19_8022_fb2471e3ec0b, v26);
  }
  v27 = v54;
  v28 = *(__int64 (__fastcall **)(struct IThreadAffineStorageQueryServer *, __int64, GUID *, __int64 *))(*(_QWORD *)v54 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  v15 = v28(v27, v50, &GUID_ac736759_22c6_4dba_b09e_04fd1889348f, &v65);
  v5 = v15;
  if ( v15 < 0 )
  {
    v16 = 841;
    goto LABEL_20;
  }
  if ( HIDWORD(v57) )
  {
    v61 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 80LL);
    v29 = *(_QWORD *)(v50 + 72);
    v30 = v50 + 80;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v50 + 80);
    Microsoft::WRL::Details::MakeAndInitialize<CStorageQueryItemArray::CStorageQueryItemArrayThumbnailPrefetcher,CStorageQueryItemArray::CStorageQueryItemArrayThumbnailPrefetcher,CRefCountedObject<CCoSimpleArray<CStorageQueryItemArray::SItem,4294967294,CSimpleArrayStandardCompareHelper<CStorageQueryItemArray::SItem>>> &,unsigned long &>(
      v30,
      v29,
      &v61);
  }
  if ( v60 )
    CStorageQueryItemArray::PrefetchProperties(v50);
  if ( v14 == 1 && !*(_BYTE *)(*(_QWORD *)(a1 + 16) + 216LL) )
  {
    v31 = *(_QWORD *)(v50 + 80);
    if ( v31 )
      WaitForSingleObject(*(HANDLE *)(v31 + 56), 0xFFFFFFFF);
  }
  if ( !**(_QWORD **)(a1 + 8) )
  {
LABEL_95:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    v45 = *(_QWORD ***)(a1 + 8);
    if ( *v45 )
    {
      v46 = v66;
      v66 = 0;
      **v45 = v46;
    }
    v47 = v65;
    v65 = 0;
    ***(_QWORD ***)a1 = v47;
    v5 = 0;
    goto LABEL_98;
  }
  pstm = 0;
  v32 = SHCreateMemStream(0, 0);
  Microsoft::WRL::ComPtr<CSemanticTextQuery>::Attach(&pstm, v32);
  v33 = pstm;
  if ( !pstm )
  {
    v5 = -2147024882;
    v34 = 2147942414LL;
    v35 = 862;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\fileitemcollections.cpp",
      (const char *)v34,
      v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstm);
    goto LABEL_21;
  }
  pv = *(_DWORD *)(v11 + 8);
  if ( v60 )
    v36 = *(_DWORD *)(v60 + 16);
  else
    v36 = 0;
  v62 = v36;
  v37 = IStream_Write(pstm, &pv, 4u);
  if ( v37 < 0 )
  {
    v38 = 866;
    goto LABEL_56;
  }
  v37 = IStream_Write(v33, (char *)&v59 + 4, 4u);
  if ( v37 < 0 )
  {
    v38 = 867;
    goto LABEL_56;
  }
  v37 = IStream_Write(v33, &v57, 4u);
  if ( v37 < 0 )
  {
    v38 = 868;
    goto LABEL_56;
  }
  v37 = IStream_Write(v33, (char *)&v57 + 4, 4u);
  if ( v37 < 0 )
  {
    v38 = 869;
    goto LABEL_56;
  }
  v37 = IStream_Write(v33, &v58, 4u);
  if ( v37 < 0 )
  {
    v38 = 870;
    goto LABEL_56;
  }
  v37 = IStream_Write(v33, &v59, 4u);
  if ( v37 < 0 )
  {
    v38 = 871;
    goto LABEL_56;
  }
  v37 = IStream_Write(v33, &v62, 4u);
  if ( v37 < 0 )
  {
    v38 = 872;
    goto LABEL_56;
  }
  if ( v62 )
  {
    v37 = IStream_Write(v33, *(const void **)(v60 + 8), 20 * v62);
    if ( v37 < 0 )
    {
      v38 = 876;
      goto LABEL_56;
    }
  }
  v39 = 0;
  if ( pv )
  {
    while ( 1 )
    {
      v37 = PropertyStore_MarshalAdditionalData(*(struct IPropertyStore **)(*(_QWORD *)v11 + 40LL * v39 + 16), v33);
      if ( v37 < 0 )
        break;
      if ( v62 )
      {
        v56 = 0;
        v40 = *(_QWORD *)(*(_QWORD *)v11 + 40LL * v39 + 24);
        if ( !v40
          || (v41 = *(void (__fastcall **)(__int64, struct IPropertyStore **))(*(_QWORD *)v40 + 72LL),
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56),
              v41(v40, &v56),
              v42 = 1,
              !v56) )
        {
          v42 = 0;
        }
        v61 = v42;
        v37 = IStream_Write(v33, &v61, 4u);
        if ( v37 < 0 )
        {
          v43 = 891;
          goto LABEL_88;
        }
        if ( v61 )
        {
          v37 = PropertyStore_MarshalAdditionalData(v56, v33);
          if ( v37 < 0 )
          {
            v43 = 894;
LABEL_88:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v43,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\fileitemcollections.cpp",
              (const char *)(unsigned int)v37,
              v49);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
            goto LABEL_57;
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
      }
      if ( ++v39 >= pv )
        goto LABEL_84;
    }
    v38 = 881;
    goto LABEL_56;
  }
LABEL_84:
  *(_QWORD *)v63 = 0;
  v37 = (*(__int64 (__fastcall **)(IStream *, _QWORD, __int64, int *))(*(_QWORD *)v33 + 40LL))(v33, 0, 1, v63);
  if ( v37 < 0 )
  {
    v38 = 901;
    goto LABEL_56;
  }
  v67 = 0;
  v37 = (*(__int64 (__fastcall **)(IStream *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v33 + 40LL))(v33, 0, 0, &v67);
  if ( v37 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    v44 = SHCreateReadOnlySharedMemoryStream(
            v33,
            (unsigned int)v63[0],
            &GUID_0000000c_0000_0000_c000_000000000046,
            &v66);
    v5 = v44;
    if ( v44 < 0 )
    {
      v34 = (unsigned int)v44;
      v35 = 905;
      goto LABEL_50;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstm);
    goto LABEL_95;
  }
  v38 = 904;
LABEL_56:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v38,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\fileitemcollections.cpp",
    (const char *)(unsigned int)v37,
    v49);
LABEL_57:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstm);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v5 = v37;
LABEL_98:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v53);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v68);
  return v5;
}

```

## disassembly

```asm
0x1804954dc  push    rbp
0x1804954de  push    rbx
0x1804954df  push    rsi
0x1804954e0  push    rdi
0x1804954e1  push    r12
0x1804954e3  push    r13
0x1804954e5  push    r14
0x1804954e7  push    r15
0x1804954e9  lea     rbp, [rsp-28h]
0x1804954ee  sub     rsp, 128h
0x1804954f5  mov     rax, cs:__security_cookie
0x1804954fc  xor     rax, rsp
0x1804954ff  mov     [rbp+60h+var_50], rax
0x180495503  mov     rsi, rcx
0x180495506  mov     rax, [rcx]
0x180495509  mov     rdx, [rax]
0x18049550c  xor     r13d, r13d
0x18049550f  mov     [rdx], r13
0x180495512  mov     rax, [rcx+8]
0x180495516  mov     rcx, [rax]
0x180495519  test    rcx, rcx
0x18049551c  jz      short loc_180495521
0x18049551e  mov     [rcx], r13
0x180495521  lea     rdx, aStagetitems; "STAGetItems"
0x180495528  lea     rcx, [rbp+60h+var_A0]
0x18049552c  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *)
0x180495531  nop
0x180495532  mov     rax, [rsi+10h]
0x180495536  mov     rdx, [rax+58h]
0x18049553a  add     rdx, 8
0x18049553e  lea     rcx, [rsp+160h+var_118]
0x180495543  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180495548  nop
0x180495549  mov     [rbp+60h+var_B0], r13
0x18049554d  mov     [rbp+60h+var_B8], r13
0x180495551  mov     [rsp+160h+var_120], r13
0x180495556  mov     rbx, [rsi+10h]
0x18049555a  lea     rcx, [rsp+160h+var_120]
0x18049555f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180495564  lea     rdx, [rsp+160h+var_120]; struct IItemCollection **
0x180495569  mov     rcx, rbx; this
0x18049556c  call    ?_LockAndEnsureCollection@CStorageQueryServer@@AEAAJPEAPEAUIItemCollection@@@Z; CStorageQueryServer::_LockAndEnsureCollection(IItemCollection * *)
0x180495571  mov     ebx, eax
0x180495573  test    eax, eax
0x180495575  jns     short loc_180495594
0x180495577  mov     rcx, [rbp+68h]; this
0x18049557b  mov     r9d, eax; char *
0x18049557e  lea     r8, aOnecoreuapShel_176; "onecoreuap\\shell\\windows.storage\\fil"...
0x180495585  mov     edx, 2E3h; void *
0x18049558a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18049558f  jmp     loc_180495CD5
0x180495594  mov     rcx, [rsi+10h]; this
0x180495598  cmp     [rcx+0E1h], r13b
0x18049559f  jz      short loc_1804955AF
0x1804955a1  cmp     [rcx+0E2h], r13b
0x1804955a8  jnz     short loc_1804955AF
0x1804955aa  call    ?_StartContentsChangedEventInternal@CStorageQueryServer@@AEAAJXZ; CStorageQueryServer::_StartContentsChangedEventInternal(void)
0x1804955af  mov     [rsp+160h+var_130], r13
0x1804955b4  mov     rbx, [rsi+18h]
0x1804955b8  lea     rcx, [rsp+160h+var_130]
0x1804955bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804955c2  mov     rdx, rbx
0x1804955c5  lea     rcx, [rsp+160h+var_130]
0x1804955ca  call    ??$MakeAndInitialize@VCStorageQueryItemArray@@V1@AEAK@Details@WRL@Microsoft@@YAJPEAPEAVCStorageQueryItemArray@@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<CStorageQueryItemArray,CStorageQueryItemArray,ulong &>(CStorageQueryItemArray * *,ulong &)
0x1804955cf  mov     ebx, eax
0x1804955d1  test    eax, eax
0x1804955d3  jns     short loc_1804955FD
0x1804955d5  mov     edx, 2F3h; void *
0x1804955da  lea     r8, aOnecoreuapShel_176; "onecoreuap\\shell\\windows.storage\\fil"...
0x1804955e1  mov     r9d, eax; char *
0x1804955e4  mov     rcx, [rbp+68h]; this
0x1804955e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804955ed  nop
0x1804955ee  lea     rcx, [rsp+160h+var_130]
0x1804955f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804955f8  jmp     loc_180495CD5
0x1804955fd  mov     rax, [rsp+160h+var_130]
0x180495602  mov     r12, [rax+48h]
0x180495606  add     r12, 8
0x18049560a  mov     qword ptr [rbp+60h+var_C8], r12
0x18049560e  mov     r8, [rsi+20h]
0x180495612  mov     rdx, [rsi+18h]
0x180495616  lea     rax, [rbp+60h+var_C8]
0x18049561a  mov     qword ptr [rsp+160h+var_140], rax; int
0x18049561f  mov     r8d, [r8]
0x180495622  mov     edx, [rdx]
0x180495624  mov     rcx, [rsp+160h+var_120]
0x180495629  call    ??$RealizeItemsOnBackgroundThread@V_lambda_c2a533ae289fe066ebf4ad507e94ce82_@@@CItemCollectionSink@@SAJPEAUIItemCollection@@IIPEAIAEBV_lambda_c2a533ae289fe066ebf4ad507e94ce82_@@@Z; CItemCollectionSink::RealizeItemsOnBackgroundThread<_lambda_c2a533ae289fe066ebf4ad507e94ce82_>(IItemCollection *,uint,uint,uint *,_lambda_c2a533ae289fe066ebf4ad507e94ce82_ const &)
0x18049562e  mov     ebx, eax
0x180495630  test    eax, eax
0x180495632  jns     short loc_18049563B
0x180495634  mov     edx, 305h
0x180495639  jmp     short loc_1804955DA
0x18049563b  cmp     [r12+8], r13d
0x180495640  jz      short loc_180495680
0x180495642  mov     rax, [rsi+10h]
0x180495646  cmp     [rax+0E1h], r13b
0x18049564d  jnz     short loc_180495680
0x18049564f  call    ?IsLowMemory@DeviceCapabilitiesW@Internal@Windows@@YA_NXZ; Windows::Internal::DeviceCapabilitiesW::IsLowMemory(void)
0x180495654  test    al, al
0x180495656  jz      short loc_180495680
0x180495658  mov     rax, [rsp+160h+var_120]
0x18049565d  mov     [rsp+160h+var_100], rax
0x180495662  lea     rcx, [rsp+160h+var_100]
0x180495667  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18049566c  lea     rdx, [rsp+160h+var_100]
0x180495671  call    ??$QueueTask@V_lambda_013ffc0c5604ddb8f47a9eb988ef629d_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_013ffc0c5604ddb8f47a9eb988ef629d_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_013ffc0c5604ddb8f47a9eb988ef629d_>(Windows::Internal::TaskApartment,_lambda_013ffc0c5604ddb8f47a9eb988ef629d_ &&)
0x180495676  lea     rcx, [rsp+160h+var_100]
0x18049567b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180495680  mov     rax, [rsi+28h]
0x180495684  mov     r15d, [rax]
0x180495687  mov     [rsp+160h+pv], r13d
0x18049568c  mov     [rsp+160h+var_F8], 5
0x180495695  mov     [rsp+160h+var_F0], 4
0x18049569d  mov     [rsp+160h+var_EC], 64h ; 'd'
0x1804956a6  mov     [rbp+60h+var_E0], r13
0x1804956aa  mov     [rsp+160h+var_110], r13
0x1804956af  mov     rcx, [rsi+10h]
0x1804956b3  add     rcx, 78h ; 'x'; this
0x1804956b7  lea     rdx, [rsp+160h+var_110]; void **
0x1804956bc  call    ??$Unmarshal@UIThreadAffineStorageQueryServer@@@CMarshaledInterface@@QEAAJV?$ComPtrRef@V?$ComPtr@UIThreadAffineStorageQueryServer@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; CMarshaledInterface::Unmarshal<IThreadAffineStorageQueryServer>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IThreadAffineStorageQueryServer>>)
0x1804956c1  mov     ebx, eax
0x1804956c3  test    eax, eax
0x1804956c5  jns     short loc_1804956F9
0x1804956c7  mov     edx, 32Bh; void *
0x1804956cc  lea     r8, aOnecoreuapShel_176; "onecoreuap\\shell\\windows.storage\\fil"...
0x1804956d3  mov     r9d, eax; char *
0x1804956d6  mov     rcx, [rbp+68h]; this
0x1804956da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804956df  nop
0x1804956e0  lea     rcx, [rsp+160h+var_110]
0x1804956e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804956ea  nop
0x1804956eb  lea     rcx, [rbp+60h+var_E0]
0x1804956ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804956f4  jmp     loc_1804955EE
0x1804956f9  mov     rdx, [rsi+10h]
0x1804956fd  add     rdx, 68h ; 'h'
0x180495701  lea     rcx, [rbp+60h+var_C8]
0x180495705  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18049570a  mov     edx, 0B0h
0x18049570f  lea     eax, [rdx-20h]
0x180495712  cmp     r15d, 1
0x180495716  cmovnz  edx, eax
0x180495719  add     rdx, [rsi+10h]
0x18049571d  lea     rcx, [rsp+160h+var_F8]
0x180495722  call    ??4SPrefetchData@@QEAAAEAU0@AEBU0@@Z; SPrefetchData::operator=(SPrefetchData const &)
0x180495727  lea     rcx, [rbp+60h+var_C8]; this
0x18049572b  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180495730  cmp     [rbp+60h+var_E0], r13
0x180495734  jnz     short loc_18049573C
0x180495736  cmp     r15d, 1
0x18049573a  jnz     short loc_180495768
0x18049573c  lea     r8, [rsp+160h+pv]; enum Windows::Storage::Search::IndexedState *
0x180495741  mov     rdx, [rsp+160h+var_110]; struct IThreadAffineStorageQueryServer *
0x180495746  mov     rcx, [rsi+10h]; this
0x18049574a  call    ?_GetIndexedState@CStorageQueryServer@@AEAAJPEAUIThreadAffineStorageQueryServer@@PEAW4IndexedState@Search@Storage@Windows@@@Z; CStorageQueryServer::_GetIndexedState(IThreadAffineStorageQueryServer *,Windows::Storage::Search::IndexedState *)
0x18049574f  test    eax, eax
0x180495751  js      short loc_18049575A
0x180495753  cmp     [rsp+160h+pv], 3
0x180495758  jz      short loc_180495768
0x18049575a  lea     rcx, [rbp+60h+var_E0]
0x18049575e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180495763  mov     dword ptr [rsp+160h+var_EC+4], r13d
0x180495768  mov     rax, [rsi+8]
0x18049576c  mov     ebx, r13d
0x18049576f  cmp     [rax], r13
0x180495772  setnz   bl
0x180495775  cmp     dword ptr [rsp+160h+var_F8+4], r13d
0x18049577a  ja      short loc_180495782
0x18049577c  cmp     [rbp+60h+var_E0], r13
0x180495780  jz      short loc_180495785
0x180495782  or      ebx, 2
0x180495785  mov     [rbp+60h+var_C0], r13d
0x180495789  mov     rax, [rsi+10h]
0x18049578d  mov     rcx, [rax+88h]
0x180495794  mov     rax, [rcx]
0x180495797  lea     rdx, [rbp+60h+var_C0]
0x18049579b  mov     rax, [rax+78h]
0x18049579f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804957a4  test    eax, eax
0x1804957a6  js      short loc_1804957B1
0x1804957a8  cmp     [rbp+60h+var_C0], 3
0x1804957ac  jnz     short loc_1804957B1
0x1804957ae  or      ebx, 4
0x1804957b1  mov     r10, [rsp+160h+var_130]
0x1804957b6  mov     rax, [rsi+30h]
0x1804957ba  mov     r14, [rax]
0x1804957bd  mov     rax, [rsi+28h]
0x1804957c1  mov     r9d, [rax]
0x1804957c4  mov     r8d, dword ptr [rsp+160h+var_EC]
0x1804957c9  mov     edx, [rsp+160h+var_F0]
0x1804957cd  mov     ecx, dword ptr [rsp+160h+var_F8+4]
0x1804957d1  mov     eax, dword ptr [rsp+160h+var_F8]
0x1804957d5  mov     [r10+58h], eax
0x1804957d9  mov     [r10+5Ch], ecx
0x1804957dd  mov     [r10+60h], edx
0x1804957e1  mov     [r10+64h], r8d
0x1804957e5  mov     [r10+38h], r9d
0x1804957e9  mov     [r10+3Ch], ebx
0x1804957ed  test    r14, r14
0x1804957f0  jz      short loc_180495819
0x1804957f2  mov     rax, [r14]
0x1804957f5  mov     rdi, [rax]
0x1804957f8  lea     rbx, [r10+40h]
0x1804957fc  mov     rcx, rbx
0x1804957ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180495804  mov     r8, rbx
0x180495807  lea     rdx, _GUID_60e1feec_e458_4a19_8022_fb2471e3ec0b
0x18049580e  mov     rcx, r14
0x180495811  mov     rax, rdi
0x180495814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180495819  mov     rdi, [rsp+160h+var_110]
0x18049581e  mov     rax, [rdi]
0x180495821  mov     rbx, [rax+18h]
0x180495825  lea     rcx, [rbp+60h+var_B8]
0x180495829  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18049582e  lea     r9, [rbp+60h+var_B8]
0x180495832  lea     r8, _GUID_ac736759_22c6_4dba_b09e_04fd1889348f
0x180495839  mov     rdx, [rsp+160h+var_130]
0x18049583e  mov     rcx, rdi
0x180495841  mov     rax, rbx
0x180495844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180495849  mov     ebx, eax
0x18049584b  test    eax, eax
0x18049584d  jns     short loc_180495859
0x18049584f  mov     edx, 349h
0x180495854  jmp     loc_1804956CC
0x180495859  cmp     dword ptr [rsp+160h+var_F8+4], r13d
0x18049585e  jbe     short loc_18049588E
0x180495860  mov     r8, [rsp+160h+var_130]
0x180495865  mov     rax, [rsi+10h]
0x180495869  mov     ecx, [rax+50h]
0x18049586c  mov     [rbp+60h+var_D8], ecx
0x18049586f  mov     rbx, [r8+48h]
0x180495873  lea     rdi, [r8+50h]
0x180495877  mov     rcx, rdi
0x18049587a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18049587f  lea     r8, [rbp+60h+var_D8]
0x180495883  mov     rdx, rbx
0x180495886  mov     rcx, rdi
0x180495889  call    ??$MakeAndInitialize@VCStorageQueryItemArrayThumbnailPrefetcher@CStorageQueryItemArray@@V12@AEAV?$CRefCountedObject@V?$CCoSimpleArray@USItem@CStorageQueryItemArray@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@USItem@CStorageQueryItemArray@@@@@@@@AEAK@Details@WRL@Microsoft@@YAJPEAPEAVCStorageQueryItemArrayThumbnailPrefetcher@CStorageQueryItemArray@@AEAV?$CRefCountedObject@V?$CCoSimpleArray@USItem@CStorageQueryItemArray@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@USItem@CStorageQueryItemArray@@@@@@@@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<CStorageQueryItemArray::CStorageQueryItemArrayThumbnailPrefetcher,CStorageQueryItemArray::CStorageQueryItemArrayThumbnailPrefetcher,CRefCountedObject<CCoSimpleArray<CStorageQueryItemArray::SItem,4294967294,CSimpleArrayStandardCompareHelper<CStorageQueryItemArray::SItem>>> &,ulong &>(CStorageQueryItemArray::CStorageQueryItemArrayThumbnailPrefetcher * *,CRefCountedObject<CCoSimpleArray<CStorageQueryItemArray::SItem,4294967294,CSimpleArrayStandardCompareHelper<CStorageQueryItemArray::SItem>>> &,ulong &)
0x18049588e  mov     rdx, [rbp+60h+var_E0]
0x180495892  test    rdx, rdx
0x180495895  jz      short loc_1804958A1
0x180495897  mov     rcx, [rsp+160h+var_130]
0x18049589c  call    ?PrefetchProperties@CStorageQueryItemArray@@QEAAXAEAV?$CRefCountedObject@V?$CCoSimpleArray@U_tagpropertykey@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@U_tagpropertykey@@@@@@@@@Z; CStorageQueryItemArray::PrefetchProperties(CRefCountedObject<CCoSimpleArray<_tagpropertykey,4294967294,CSimpleArrayStandardCompareHelper<_tagpropertykey>>> &)
0x1804958a1  cmp     r15d, 1
0x1804958a5  jnz     short loc_1804958D5
0x1804958a7  mov     rax, [rsi+10h]
0x1804958ab  cmp     [rax+0D8h], r13b
0x1804958b2  jnz     short loc_1804958D5
0x1804958b4  mov     rax, [rsp+160h+var_130]
0x1804958b9  mov     rcx, [rax+50h]
0x1804958bd  test    rcx, rcx
0x1804958c0  jz      short loc_1804958D5
0x1804958c2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1804958c5  mov     rcx, [rcx+38h]; hHandle
0x1804958c9  call    cs:__imp_WaitForSingleObject
0x1804958d0  nop     dword ptr [rax+rax+00h]
0x1804958d5  mov     rax, [rsi+8]
0x1804958d9  cmp     [rax], r13
0x1804958dc  jz      loc_180495C8B
0x1804958e2  mov     [rsp+160h+pstm], r13
0x1804958e7  xor     edx, edx; cbInit
0x1804958e9  xor     ecx, ecx; pInit
0x1804958eb  call    cs:__imp_SHCreateMemStream
0x1804958f2  nop     dword ptr [rax+rax+00h]
0x1804958f7  mov     rdx, rax
0x1804958fa  lea     rcx, [rsp+160h+pstm]
0x1804958ff  call    ?Attach@?$ComPtr@VCSemanticTextQuery@@@WRL@Microsoft@@QEAAXPEAVCSemanticTextQuery@@@Z; Microsoft::WRL::ComPtr<CSemanticTextQuery>::Attach(CSemanticTextQuery *)
0x180495904  mov     rbx, [rsp+160h+pstm]
0x180495909  test    rbx, rbx
0x18049590c  jnz     short loc_18049593B
0x18049590e  mov     ebx, 8007000Eh
0x180495913  mov     r9d, ebx; char *
0x180495916  mov     edx, 35Eh; void *
0x18049591b  lea     r8, aOnecoreuapShel_176; "onecoreuap\\shell\\windows.storage\\fil"...
0x180495922  mov     rcx, [rbp+68h]; this
0x180495926  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18049592b  nop
0x18049592c  lea     rcx, [rsp+160h+pstm]
0x180495931  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180495936  jmp     loc_1804956E0
0x18049593b  mov     eax, [r12+8]
0x180495940  mov     [rsp+160h+pv], eax
0x180495944  mov     rax, [rbp+60h+var_E0]
0x180495948  test    rax, rax
0x18049594b  jz      short loc_180495952
0x18049594d  mov     ecx, [rax+10h]
0x180495950  jmp     short loc_180495955
0x180495952  mov     ecx, r13d
0x180495955  mov     [rbp+60h+var_D0], ecx
0x180495958  mov     r14d, 4
0x18049595e  mov     r8d, r14d; cb
0x180495961  lea     rdx, [rsp+160h+pv]; pv
0x180495966  mov     rcx, rbx; pstm
0x180495969  call    cs:__imp_IStream_Write
0x180495970  nop     dword ptr [rax+rax+00h]
0x180495975  mov     edi, eax
  ... truncated ...
```
