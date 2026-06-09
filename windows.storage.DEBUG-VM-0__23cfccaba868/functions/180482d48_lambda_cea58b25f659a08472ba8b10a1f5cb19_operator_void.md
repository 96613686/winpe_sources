# _lambda_cea58b25f659a08472ba8b10a1f5cb19_::operator()(void)

- ea: `0x180482d48`
- end: `0x18048354e`
- name: `??R_lambda_cea58b25f659a08472ba8b10a1f5cb19_@@QEBAJXZ`
- size: `2054`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x18029d5f0`

## callees

- `0x18000d354`
- `0x18000d6cc`
- `0x1800297d8`
- `0x1800432f0`
- `0x180046830`
- `0x180067bb4`
- `0x180077e50`
- `0x1800bdb88`
- `0x1800c6144`
- `0x1800fa9b8`
- `0x180144388`
- `0x18021c7a8`
- `0x1802310dc`
- `0x180233794`
- `0x180241a0c`
- `0x180252a44`
- `0x1802ac044`
- `0x1802fd40c`
- `0x180353cec`
- `0x1803a4cb0`
- `0x18047ec90`
- `0x18047f34c`
- `0x18047f468`
- `0x180482d48`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180483135`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180483135`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x18048348b`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x18048348b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804831c9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18048322a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180483248`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180483269`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18048328a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804832ab`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804832cb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804832fb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18048339e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804831c9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18048322a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180483248`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180483269`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18048328a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804832ab`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804832cb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1804832fb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18048339e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180483151`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180483151`

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
0x180482d48  push    rbp
0x180482d4a  push    rbx
0x180482d4b  push    rsi
0x180482d4c  push    rdi
0x180482d4d  push    r12
0x180482d4f  push    r13
0x180482d51  push    r14
0x180482d53  push    r15
0x180482d55  lea     rbp, [rsp-28h]
0x180482d5a  sub     rsp, 128h
0x180482d61  mov     rax, cs:__security_cookie
0x180482d68  xor     rax, rsp
0x180482d6b  mov     [rbp+60h+var_50], rax
0x180482d6f  mov     rsi, rcx
0x180482d72  mov     rax, [rcx]
0x180482d75  mov     rdx, [rax]
0x180482d78  xor     r13d, r13d
0x180482d7b  mov     [rdx], r13
0x180482d7e  mov     rax, [rcx+8]
0x180482d82  mov     rcx, [rax]
0x180482d85  test    rcx, rcx
0x180482d88  jz      short loc_180482D8D
0x180482d8a  mov     [rcx], r13
0x180482d8d  lea     rdx, aStagetitems; "STAGetItems"
0x180482d94  lea     rcx, [rbp+60h+var_A0]
0x180482d98  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *)
0x180482d9d  nop
0x180482d9e  mov     rax, [rsi+10h]
0x180482da2  mov     rdx, [rax+58h]
0x180482da6  add     rdx, 8
0x180482daa  lea     rcx, [rsp+160h+var_118]
0x180482daf  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180482db4  nop
0x180482db5  mov     [rbp+60h+var_B0], r13
0x180482db9  mov     [rbp+60h+var_B8], r13
0x180482dbd  mov     [rsp+160h+var_120], r13
0x180482dc2  mov     rbx, [rsi+10h]
0x180482dc6  lea     rcx, [rsp+160h+var_120]
0x180482dcb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180482dd0  lea     rdx, [rsp+160h+var_120]; struct IItemCollection **
0x180482dd5  mov     rcx, rbx; this
0x180482dd8  call    ?_LockAndEnsureCollection@CStorageQueryServer@@AEAAJPEAPEAUIItemCollection@@@Z; CStorageQueryServer::_LockAndEnsureCollection(IItemCollection * *)
0x180482ddd  mov     ebx, eax
0x180482ddf  test    eax, eax
0x180482de1  jns     short loc_180482E00
0x180482de3  mov     rcx, [rbp+68h]; this
0x180482de7  mov     r9d, eax; char *
0x180482dea  lea     r8, aOnecoreuapShel_176; "onecoreuap\\shell\\windows.storage\\fil"...
0x180482df1  mov     edx, 2E3h; void *
0x180482df6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180482dfb  jmp     loc_1804834F9
0x180482e00  mov     rcx, [rsi+10h]; this
0x180482e04  cmp     [rcx+0E1h], r13b
0x180482e0b  jz      short loc_180482E1B
0x180482e0d  cmp     [rcx+0E2h], r13b
0x180482e14  jnz     short loc_180482E1B
0x180482e16  call    ?_StartContentsChangedEventInternal@CStorageQueryServer@@AEAAJXZ; CStorageQueryServer::_StartContentsChangedEventInternal(void)
0x180482e1b  mov     [rsp+160h+var_130], r13
0x180482e20  mov     rbx, [rsi+18h]
0x180482e24  lea     rcx, [rsp+160h+var_130]
0x180482e29  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180482e2e  mov     rdx, rbx
0x180482e31  lea     rcx, [rsp+160h+var_130]
0x180482e36  call    ??$MakeAndInitialize@VCStorageQueryItemArray@@V1@AEAK@Details@WRL@Microsoft@@YAJPEAPEAVCStorageQueryItemArray@@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<CStorageQueryItemArray,CStorageQueryItemArray,ulong &>(CStorageQueryItemArray * *,ulong &)
0x180482e3b  mov     ebx, eax
0x180482e3d  test    eax, eax
0x180482e3f  jns     short loc_180482E69
0x180482e41  mov     edx, 2F3h; void *
0x180482e46  lea     r8, aOnecoreuapShel_176; "onecoreuap\\shell\\windows.storage\\fil"...
0x180482e4d  mov     r9d, eax; char *
0x180482e50  mov     rcx, [rbp+68h]; this
0x180482e54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180482e59  nop
0x180482e5a  lea     rcx, [rsp+160h+var_130]
0x180482e5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180482e64  jmp     loc_1804834F9
0x180482e69  mov     rax, [rsp+160h+var_130]
0x180482e6e  mov     r12, [rax+48h]
0x180482e72  add     r12, 8
0x180482e76  mov     qword ptr [rbp+60h+var_C8], r12
0x180482e7a  mov     r8, [rsi+20h]
0x180482e7e  mov     rdx, [rsi+18h]
0x180482e82  lea     rax, [rbp+60h+var_C8]
0x180482e86  mov     qword ptr [rsp+160h+var_140], rax; int
0x180482e8b  mov     r8d, [r8]
0x180482e8e  mov     edx, [rdx]
0x180482e90  mov     rcx, [rsp+160h+var_120]
0x180482e95  call    ??$RealizeItemsOnBackgroundThread@V_lambda_c2a533ae289fe066ebf4ad507e94ce82_@@@CItemCollectionSink@@SAJPEAUIItemCollection@@IIPEAIAEBV_lambda_c2a533ae289fe066ebf4ad507e94ce82_@@@Z; CItemCollectionSink::RealizeItemsOnBackgroundThread<_lambda_c2a533ae289fe066ebf4ad507e94ce82_>(IItemCollection *,uint,uint,uint *,_lambda_c2a533ae289fe066ebf4ad507e94ce82_ const &)
0x180482e9a  mov     ebx, eax
0x180482e9c  test    eax, eax
0x180482e9e  jns     short loc_180482EA7
0x180482ea0  mov     edx, 305h
0x180482ea5  jmp     short loc_180482E46
0x180482ea7  cmp     [r12+8], r13d
0x180482eac  jz      short loc_180482EEC
0x180482eae  mov     rax, [rsi+10h]
0x180482eb2  cmp     [rax+0E1h], r13b
0x180482eb9  jnz     short loc_180482EEC
0x180482ebb  call    ?IsLowMemory@DeviceCapabilitiesW@Internal@Windows@@YA_NXZ; Windows::Internal::DeviceCapabilitiesW::IsLowMemory(void)
0x180482ec0  test    al, al
0x180482ec2  jz      short loc_180482EEC
0x180482ec4  mov     rax, [rsp+160h+var_120]
0x180482ec9  mov     [rsp+160h+var_100], rax
0x180482ece  lea     rcx, [rsp+160h+var_100]
0x180482ed3  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180482ed8  lea     rdx, [rsp+160h+var_100]
0x180482edd  call    ??$QueueTask@V_lambda_013ffc0c5604ddb8f47a9eb988ef629d_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_013ffc0c5604ddb8f47a9eb988ef629d_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_013ffc0c5604ddb8f47a9eb988ef629d_>(Windows::Internal::TaskApartment,_lambda_013ffc0c5604ddb8f47a9eb988ef629d_ &&)
0x180482ee2  lea     rcx, [rsp+160h+var_100]
0x180482ee7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180482eec  mov     rax, [rsi+28h]
0x180482ef0  mov     r15d, [rax]
0x180482ef3  mov     [rsp+160h+pv], r13d
0x180482ef8  mov     [rsp+160h+var_F8], 5
0x180482f01  mov     [rsp+160h+var_F0], 4
0x180482f09  mov     [rsp+160h+var_EC], 64h ; 'd'
0x180482f12  mov     [rbp+60h+var_E0], r13
0x180482f16  mov     [rsp+160h+var_110], r13
0x180482f1b  mov     rcx, [rsi+10h]
0x180482f1f  add     rcx, 78h ; 'x'; this
0x180482f23  lea     rdx, [rsp+160h+var_110]; void **
0x180482f28  call    ??$Unmarshal@UIThreadAffineStorageQueryServer@@@CMarshaledInterface@@QEAAJV?$ComPtrRef@V?$ComPtr@UIThreadAffineStorageQueryServer@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; CMarshaledInterface::Unmarshal<IThreadAffineStorageQueryServer>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IThreadAffineStorageQueryServer>>)
0x180482f2d  mov     ebx, eax
0x180482f2f  test    eax, eax
0x180482f31  jns     short loc_180482F65
0x180482f33  mov     edx, 32Bh; void *
0x180482f38  lea     r8, aOnecoreuapShel_176; "onecoreuap\\shell\\windows.storage\\fil"...
0x180482f3f  mov     r9d, eax; char *
0x180482f42  mov     rcx, [rbp+68h]; this
0x180482f46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180482f4b  nop
0x180482f4c  lea     rcx, [rsp+160h+var_110]
0x180482f51  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180482f56  nop
0x180482f57  lea     rcx, [rbp+60h+var_E0]
0x180482f5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180482f60  jmp     loc_180482E5A
0x180482f65  mov     rdx, [rsi+10h]
0x180482f69  add     rdx, 68h ; 'h'
0x180482f6d  lea     rcx, [rbp+60h+var_C8]
0x180482f71  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180482f76  mov     edx, 0B0h
0x180482f7b  lea     eax, [rdx-20h]
0x180482f7e  cmp     r15d, 1
0x180482f82  cmovnz  edx, eax
0x180482f85  add     rdx, [rsi+10h]
0x180482f89  lea     rcx, [rsp+160h+var_F8]
0x180482f8e  call    ??4SPrefetchData@@QEAAAEAU0@AEBU0@@Z; SPrefetchData::operator=(SPrefetchData const &)
0x180482f93  lea     rcx, [rbp+60h+var_C8]; this
0x180482f97  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180482f9c  cmp     [rbp+60h+var_E0], r13
0x180482fa0  jnz     short loc_180482FA8
0x180482fa2  cmp     r15d, 1
0x180482fa6  jnz     short loc_180482FD4
0x180482fa8  lea     r8, [rsp+160h+pv]; enum Windows::Storage::Search::IndexedState *
0x180482fad  mov     rdx, [rsp+160h+var_110]; struct IThreadAffineStorageQueryServer *
0x180482fb2  mov     rcx, [rsi+10h]; this
0x180482fb6  call    ?_GetIndexedState@CStorageQueryServer@@AEAAJPEAUIThreadAffineStorageQueryServer@@PEAW4IndexedState@Search@Storage@Windows@@@Z; CStorageQueryServer::_GetIndexedState(IThreadAffineStorageQueryServer *,Windows::Storage::Search::IndexedState *)
0x180482fbb  test    eax, eax
0x180482fbd  js      short loc_180482FC6
0x180482fbf  cmp     [rsp+160h+pv], 3
0x180482fc4  jz      short loc_180482FD4
0x180482fc6  lea     rcx, [rbp+60h+var_E0]
0x180482fca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180482fcf  mov     dword ptr [rsp+160h+var_EC+4], r13d
0x180482fd4  mov     rax, [rsi+8]
0x180482fd8  mov     ebx, r13d
0x180482fdb  cmp     [rax], r13
0x180482fde  setnz   bl
0x180482fe1  cmp     dword ptr [rsp+160h+var_F8+4], r13d
0x180482fe6  ja      short loc_180482FEE
0x180482fe8  cmp     [rbp+60h+var_E0], r13
0x180482fec  jz      short loc_180482FF1
0x180482fee  or      ebx, 2
0x180482ff1  mov     [rbp+60h+var_C0], r13d
0x180482ff5  mov     rax, [rsi+10h]
0x180482ff9  mov     rcx, [rax+88h]
0x180483000  mov     rax, [rcx]
0x180483003  lea     rdx, [rbp+60h+var_C0]
0x180483007  mov     rax, [rax+78h]
0x18048300b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180483010  test    eax, eax
0x180483012  js      short loc_18048301D
0x180483014  cmp     [rbp+60h+var_C0], 3
0x180483018  jnz     short loc_18048301D
0x18048301a  or      ebx, 4
0x18048301d  mov     r10, [rsp+160h+var_130]
0x180483022  mov     rax, [rsi+30h]
0x180483026  mov     r14, [rax]
0x180483029  mov     rax, [rsi+28h]
0x18048302d  mov     r9d, [rax]
0x180483030  mov     r8d, dword ptr [rsp+160h+var_EC]
0x180483035  mov     edx, [rsp+160h+var_F0]
0x180483039  mov     ecx, dword ptr [rsp+160h+var_F8+4]
0x18048303d  mov     eax, dword ptr [rsp+160h+var_F8]
0x180483041  mov     [r10+58h], eax
0x180483045  mov     [r10+5Ch], ecx
0x180483049  mov     [r10+60h], edx
0x18048304d  mov     [r10+64h], r8d
0x180483051  mov     [r10+38h], r9d
0x180483055  mov     [r10+3Ch], ebx
0x180483059  test    r14, r14
0x18048305c  jz      short loc_180483085
0x18048305e  mov     rax, [r14]
0x180483061  mov     rdi, [rax]
0x180483064  lea     rbx, [r10+40h]
0x180483068  mov     rcx, rbx
0x18048306b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180483070  mov     r8, rbx
0x180483073  lea     rdx, _GUID_60e1feec_e458_4a19_8022_fb2471e3ec0b
0x18048307a  mov     rcx, r14
0x18048307d  mov     rax, rdi
0x180483080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180483085  mov     rdi, [rsp+160h+var_110]
0x18048308a  mov     rax, [rdi]
0x18048308d  mov     rbx, [rax+18h]
0x180483091  lea     rcx, [rbp+60h+var_B8]
0x180483095  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18048309a  lea     r9, [rbp+60h+var_B8]
0x18048309e  lea     r8, _GUID_ac736759_22c6_4dba_b09e_04fd1889348f
0x1804830a5  mov     rdx, [rsp+160h+var_130]
0x1804830aa  mov     rcx, rdi
0x1804830ad  mov     rax, rbx
0x1804830b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804830b5  mov     ebx, eax
0x1804830b7  test    eax, eax
0x1804830b9  jns     short loc_1804830C5
0x1804830bb  mov     edx, 349h
0x1804830c0  jmp     loc_180482F38
0x1804830c5  cmp     dword ptr [rsp+160h+var_F8+4], r13d
0x1804830ca  jbe     short loc_1804830FA
0x1804830cc  mov     r8, [rsp+160h+var_130]
0x1804830d1  mov     rax, [rsi+10h]
0x1804830d5  mov     ecx, [rax+50h]
0x1804830d8  mov     [rbp+60h+var_D8], ecx
0x1804830db  mov     rbx, [r8+48h]
0x1804830df  lea     rdi, [r8+50h]
0x1804830e3  mov     rcx, rdi
0x1804830e6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1804830eb  lea     r8, [rbp+60h+var_D8]
0x1804830ef  mov     rdx, rbx
0x1804830f2  mov     rcx, rdi
0x1804830f5  call    ??$MakeAndInitialize@VCStorageQueryItemArrayThumbnailPrefetcher@CStorageQueryItemArray@@V12@AEAV?$CRefCountedObject@V?$CCoSimpleArray@USItem@CStorageQueryItemArray@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@USItem@CStorageQueryItemArray@@@@@@@@AEAK@Details@WRL@Microsoft@@YAJPEAPEAVCStorageQueryItemArrayThumbnailPrefetcher@CStorageQueryItemArray@@AEAV?$CRefCountedObject@V?$CCoSimpleArray@USItem@CStorageQueryItemArray@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@USItem@CStorageQueryItemArray@@@@@@@@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<CStorageQueryItemArray::CStorageQueryItemArrayThumbnailPrefetcher,CStorageQueryItemArray::CStorageQueryItemArrayThumbnailPrefetcher,CRefCountedObject<CCoSimpleArray<CStorageQueryItemArray::SItem,4294967294,CSimpleArrayStandardCompareHelper<CStorageQueryItemArray::SItem>>> &,ulong &>(CStorageQueryItemArray::CStorageQueryItemArrayThumbnailPrefetcher * *,CRefCountedObject<CCoSimpleArray<CStorageQueryItemArray::SItem,4294967294,CSimpleArrayStandardCompareHelper<CStorageQueryItemArray::SItem>>> &,ulong &)
0x1804830fa  mov     rdx, [rbp+60h+var_E0]
0x1804830fe  test    rdx, rdx
0x180483101  jz      short loc_18048310D
0x180483103  mov     rcx, [rsp+160h+var_130]
0x180483108  call    ?PrefetchProperties@CStorageQueryItemArray@@QEAAXAEAV?$CRefCountedObject@V?$CCoSimpleArray@U_tagpropertykey@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@U_tagpropertykey@@@@@@@@@Z; CStorageQueryItemArray::PrefetchProperties(CRefCountedObject<CCoSimpleArray<_tagpropertykey,4294967294,CSimpleArrayStandardCompareHelper<_tagpropertykey>>> &)
0x18048310d  cmp     r15d, 1
0x180483111  jnz     short loc_18048313B
0x180483113  mov     rax, [rsi+10h]
0x180483117  cmp     [rax+0D8h], r13b
0x18048311e  jnz     short loc_18048313B
0x180483120  mov     rax, [rsp+160h+var_130]
0x180483125  mov     rcx, [rax+50h]
0x180483129  test    rcx, rcx
0x18048312c  jz      short loc_18048313B
0x18048312e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180483131  mov     rcx, [rcx+38h]; hHandle
0x180483135  call    cs:__imp_WaitForSingleObject
0x18048313b  mov     rax, [rsi+8]
0x18048313f  cmp     [rax], r13
0x180483142  jz      loc_1804834AF
0x180483148  mov     [rsp+160h+pstm], r13
0x18048314d  xor     edx, edx; cbInit
0x18048314f  xor     ecx, ecx; pInit
0x180483151  call    cs:__imp_SHCreateMemStream
0x180483157  mov     rdx, rax
0x18048315a  lea     rcx, [rsp+160h+pstm]
0x18048315f  call    ?Attach@?$ComPtr@VCSemanticTextQuery@@@WRL@Microsoft@@QEAAXPEAVCSemanticTextQuery@@@Z; Microsoft::WRL::ComPtr<CSemanticTextQuery>::Attach(CSemanticTextQuery *)
0x180483164  mov     rbx, [rsp+160h+pstm]
0x180483169  test    rbx, rbx
0x18048316c  jnz     short loc_18048319B
0x18048316e  mov     ebx, 8007000Eh
0x180483173  mov     r9d, ebx; char *
0x180483176  mov     edx, 35Eh; void *
0x18048317b  lea     r8, aOnecoreuapShel_176; "onecoreuap\\shell\\windows.storage\\fil"...
0x180483182  mov     rcx, [rbp+68h]; this
0x180483186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18048318b  nop
0x18048318c  lea     rcx, [rsp+160h+pstm]
0x180483191  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180483196  jmp     loc_180482F4C
0x18048319b  mov     eax, [r12+8]
0x1804831a0  mov     [rsp+160h+pv], eax
0x1804831a4  mov     rax, [rbp+60h+var_E0]
0x1804831a8  test    rax, rax
0x1804831ab  jz      short loc_1804831B2
0x1804831ad  mov     ecx, [rax+10h]
0x1804831b0  jmp     short loc_1804831B5
0x1804831b2  mov     ecx, r13d
0x1804831b5  mov     [rbp+60h+var_D0], ecx
0x1804831b8  mov     r14d, 4
0x1804831be  mov     r8d, r14d; cb
0x1804831c1  lea     rdx, [rsp+160h+pv]; pv
0x1804831c6  mov     rcx, rbx; pstm
0x1804831c9  call    cs:__imp_IStream_Write
0x1804831cf  mov     edi, eax
0x1804831d1  test    eax, eax
0x1804831d3  jns     short loc_18048321F
0x1804831d5  mov     edx, 362h; void *
  ... truncated ...
```
