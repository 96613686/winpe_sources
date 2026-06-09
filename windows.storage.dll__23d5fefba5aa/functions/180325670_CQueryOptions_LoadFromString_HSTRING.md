# CQueryOptions::LoadFromString(HSTRING__ *)

- ea: `0x180325670`
- end: `0x180325ea1`
- name: `?LoadFromString@CQueryOptions@@UEAAJPEAUHSTRING__@@@Z`
- size: `2097`
- prototype: `__int64 __fastcall(CQueryOptions *__hidden this, HSTRING string)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x18001748c`
- `0x180017a24`
- `0x180017e60`
- `0x180017f78`
- `0x180019124`
- `0x18002ca8c`
- `0x1800807d4`
- `0x1800d10a0`
- `0x18011ca08`
- `0x18011d6c8`
- `0x18013cc34`
- `0x180176d14`
- `0x1801be804`
- `0x180248440`
- `0x180248474`
- `0x18029481c`
- `0x180299278`
- `0x1802ceec8`
- `0x180325670`
- `0x1803b1f60`
- `0x18043115c`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180325c5b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180325c5b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325774`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803257b4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803257f7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18032582e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325868`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803258ae`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803259a8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325a70`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325b05`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325b8b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325bab`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325bcb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325beb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325c0b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325c2b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325d74`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325d98`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325774`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803257b4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803257f7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18032582e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325868`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803258ae`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803259a8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325a70`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325b05`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325b8b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325bab`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325bcb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325beb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325c0b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325c2b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325d74`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180325d98`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1803256f7`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1803256f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18032572d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18032572d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325b3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325b3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CQueryOptions::LoadFromString(CQueryOptions *this, HSTRING string)
{
  IStream *v4; // rax
  IStream *v5; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v7; // rcx
  HRESULT FileTypeFilter; // edi
  CQueryOptions *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  CQueryOptions *v12; // rcx
  CQueryOptions *v13; // rcx
  CQueryOptions *v14; // rcx
  CQueryOptions *v15; // rcx
  unsigned int i; // r14d
  CQueryOptions *v17; // rcx
  unsigned int j; // r14d
  __int64 RefCounted; // rax
  char *v20; // r14
  __int64 v21; // rdx
  unsigned int k; // ecx
  _QWORD *v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // rdx
  CQueryOptions *v26; // rcx
  unsigned int m; // r14d
  unsigned int v28; // ebx
  IStream *pstm; // [rsp+38h] [rbp-59h] BYREF
  unsigned int pv; // [rsp+40h] [rbp-51h] BYREF
  HSTRING v32; // [rsp+48h] [rbp-49h] BYREF
  char v33; // [rsp+50h] [rbp-41h] BYREF
  _BYTE v34[3]; // [rsp+51h] [rbp-40h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-3Dh] BYREF
  _DWORD v36[4]; // [rsp+58h] [rbp-39h] BYREF
  __int128 v37; // [rsp+68h] [rbp-29h] BYREF
  _DWORD v38[4]; // [rsp+78h] [rbp-19h] BYREF
  HSTRING stringa[2]; // [rsp+88h] [rbp-9h] BYREF
  GUID v40; // [rsp+98h] [rbp+7h] BYREF

  if ( _InterlockedIncrement(&`CQueryOptions::LoadFromString'::`4'::__wil_apiCallCounter) == 1 )
  {
    pstm = (IStream *)&`CQueryOptions::LoadFromString'::`4'::__wil_apiCallCounter;
    v32 = 0;
    *(_QWORD *)&v37 = L"Windows.Storage.Search.QueryOptions";
    wil::details::ApiTelemetryLogger::InitApiData<unsigned short const *,unsigned short const (&)[7],std::nullptr_t,long volatile *>(
      &v37,
      L"LoadFromString",
      &v32,
      &pstm);
  }
  pstm = 0;
  v4 = SHCreateMemStream(0, 0);
  Microsoft::WRL::ComPtr<CSemanticTextQuery>::Attach(&pstm, v4);
  v5 = pstm;
  if ( !pstm )
  {
    FileTypeFilter = -2147024882;
    goto LABEL_86;
  }
  v40 = GUID_NULL;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  FileTypeFilter = TextToBinary(v7, StringRawBuffer, v5);
  if ( FileTypeFilter >= 0 )
  {
    FileTypeFilter = Stream_CheckVersion(v5);
    if ( FileTypeFilter >= 0 )
    {
      pv = 0;
      FileTypeFilter = IStream_Read(v5, &pv, 4u);
      if ( FileTypeFilter >= 0 )
      {
        FileTypeFilter = (*(__int64 (__fastcall **)(CQueryOptions *, _QWORD))(*(_QWORD *)this + 64LL))(this, pv);
        if ( FileTypeFilter >= 0 )
        {
          v35 = 0;
          FileTypeFilter = IStream_Read(v5, &v35, 4u);
          if ( FileTypeFilter >= 0 )
          {
            FileTypeFilter = (*(__int64 (__fastcall **)(CQueryOptions *, _QWORD))(*(_QWORD *)this + 128LL))(this, v35);
            if ( FileTypeFilter >= 0 )
            {
              v36[0] = 0;
              FileTypeFilter = IStream_Read(v5, v36, 4u);
              if ( FileTypeFilter >= 0 )
              {
                FileTypeFilter = CQueryOptions::put_DateStackOption(this, v36[0]);
                if ( FileTypeFilter >= 0 )
                {
                  FileTypeFilter = IStream_Read(v5, &v40, 0x10u);
                  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59687846>::GetImpl'::`2'::impl) )
                    goto LABEL_18;
                  if ( FileTypeFilter >= 0 )
                  {
                    v33 = 0;
                    FileTypeFilter = IStream_Read(v5, &v33, 1u);
                    if ( FileTypeFilter >= 0 )
                    {
                      LOBYTE(v10) = v33;
                      FileTypeFilter = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this + 3) + 56LL))(
                                         (char *)this + 24,
                                         v10);
                      if ( FileTypeFilter >= 0 )
                      {
                        v34[0] = 0;
                        FileTypeFilter = IStream_Read(v5, v34, 1u);
                        if ( FileTypeFilter >= 0 )
                        {
                          LOBYTE(v11) = v34[0];
                          FileTypeFilter = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this + 3) + 72LL))(
                                             (char *)this + 24,
                                             v11);
LABEL_18:
                          if ( FileTypeFilter >= 0 )
                          {
                            v32 = 0;
                            FileTypeFilter = CQueryOptions::_IStream_ReadString(
                                               v9,
                                               v5,
                                               (struct Windows::Internal::String *)&v32);
                            if ( FileTypeFilter >= 0 )
                            {
                              FileTypeFilter = (*(__int64 (__fastcall **)(CQueryOptions *, HSTRING))(*(_QWORD *)this + 80LL))(
                                                 this,
                                                 v32);
                              if ( FileTypeFilter >= 0 )
                              {
                                FileTypeFilter = CQueryOptions::_IStream_ReadString(
                                                   v12,
                                                   v5,
                                                   (struct Windows::Internal::String *)&v32);
                                if ( FileTypeFilter >= 0 )
                                {
                                  FileTypeFilter = (*(__int64 (__fastcall **)(CQueryOptions *, HSTRING))(*(_QWORD *)this + 96LL))(
                                                     this,
                                                     v32);
                                  if ( FileTypeFilter >= 0 )
                                  {
                                    FileTypeFilter = CQueryOptions::_IStream_ReadString(
                                                       v13,
                                                       v5,
                                                       (struct Windows::Internal::String *)&v32);
                                    if ( FileTypeFilter >= 0 )
                                    {
                                      FileTypeFilter = (*(__int64 (__fastcall **)(CQueryOptions *, HSTRING))(*(_QWORD *)this + 112LL))(
                                                         this,
                                                         v32);
                                      if ( FileTypeFilter >= 0 )
                                      {
                                        FileTypeFilter = CQueryOptions::_IStream_ReadString(
                                                           v14,
                                                           v5,
                                                           (struct Windows::Internal::String *)&v32);
                                        if ( FileTypeFilter >= 0 )
                                          FileTypeFilter = CQueryOptions::put_GroupPropertyName(this, v32);
                                      }
                                    }
                                  }
                                }
                              }
                            }
                            Windows::Internal::String::~String((Windows::Internal::String *)&v32);
                            if ( FileTypeFilter >= 0 )
                            {
                              pv = 0;
                              FileTypeFilter = IStream_Read(v5, &pv, 4u);
                              if ( FileTypeFilter >= 0 )
                              {
                                if ( !*((_QWORD *)this + 20) && !pv )
                                  goto LABEL_39;
                                v32 = 0;
                                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                                FileTypeFilter = CQueryOptions::_GetFileTypeFilter(this, &v32);
                                if ( FileTypeFilter >= 0 )
                                {
                                  FileTypeFilter = (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)v32 + 120LL))(v32);
                                  if ( FileTypeFilter >= 0 )
                                  {
                                    for ( i = 0; i < pv; ++i )
                                    {
                                      if ( FileTypeFilter < 0 )
                                        break;
                                      *(_QWORD *)&v37 = 0;
                                      FileTypeFilter = CQueryOptions::_IStream_ReadString(
                                                         v15,
                                                         v5,
                                                         (struct Windows::Internal::String *)&v37);
                                      if ( FileTypeFilter >= 0 )
                                        FileTypeFilter = (*(__int64 (__fastcall **)(HSTRING, _QWORD))(*(_QWORD *)v32 + 104LL))(
                                                           v32,
                                                           v37);
                                      Windows::Internal::String::~String((Windows::Internal::String *)&v37);
                                    }
                                  }
                                }
                                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                                if ( FileTypeFilter >= 0 )
                                {
LABEL_39:
                                  pv = 0;
                                  FileTypeFilter = IStream_Read(v5, &pv, 4u);
                                  if ( FileTypeFilter >= 0 )
                                  {
                                    if ( !*((_QWORD *)this + 19) && !pv )
                                      goto LABEL_51;
                                    v32 = 0;
                                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                                    FileTypeFilter = CQueryOptions::_GetSortOrderVector(this, &v32);
                                    if ( FileTypeFilter >= 0 )
                                    {
                                      FileTypeFilter = (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)v32 + 120LL))(v32);
                                      if ( FileTypeFilter >= 0 )
                                      {
                                        for ( j = 0; j < pv; ++j )
                                        {
                                          if ( FileTypeFilter < 0 )
                                            break;
                                          *(_OWORD *)stringa = 0;
                                          FileTypeFilter = CQueryOptions::_IStream_ReadHSTRING(v17, v5, stringa);
                                          if ( FileTypeFilter >= 0 )
                                          {
                                            FileTypeFilter = IStream_Read(v5, &stringa[1], 1u);
                                            if ( FileTypeFilter >= 0 )
                                            {
                                              v37 = *(_OWORD *)stringa;
                                              FileTypeFilter = (*(__int64 (__fastcall **)(HSTRING, __int128 *))(*(_QWORD *)v32 + 104LL))(
                                                                 v32,
                                                                 &v37);
                                            }
                                          }
                                          WindowsDeleteString(stringa[0]);
                                        }
                                      }
                                    }
                                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                                    if ( FileTypeFilter >= 0 )
                                    {
LABEL_51:
                                      LODWORD(v37) = 5;
                                      v38[0] = 0;
                                      v35 = 4;
                                      v36[0] = 100;
                                      LODWORD(v32) = 0;
                                      pv = 0;
                                      FileTypeFilter = IStream_Read(v5, &v37, 4u);
                                      if ( FileTypeFilter >= 0 )
                                      {
                                        FileTypeFilter = IStream_Read(v5, v38, 4u);
                                        if ( FileTypeFilter >= 0 )
                                        {
                                          FileTypeFilter = IStream_Read(v5, &v35, 4u);
                                          if ( FileTypeFilter >= 0 )
                                          {
                                            FileTypeFilter = IStream_Read(v5, v36, 4u);
                                            if ( FileTypeFilter >= 0 )
                                            {
                                              FileTypeFilter = IStream_Read(v5, &v32, 4u);
                                              if ( FileTypeFilter >= 0 )
                                              {
                                                FileTypeFilter = IStream_Read(v5, &pv, 4u);
                                                if ( FileTypeFilter >= 0 )
                                                {
                                                  if ( pv <= 0x1F4 )
                                                  {
                                                    FileTypeFilter = CQueryOptions::_SetThumbnailPrefetchOptions(
                                                                       this,
                                                                       (unsigned int)v37,
                                                                       v38[0],
                                                                       v35,
                                                                       v36[0]);
                                                    if ( FileTypeFilter >= 0 )
                                                    {
                                                      FileTypeFilter = CQueryOptions::_SetPropertyPrefetchOptions(
                                                                         this,
                                                                         (unsigned int)v32,
                                                                         0);
                                                      if ( FileTypeFilter >= 0 )
                                                      {
                                                        if ( !pv )
                                                          goto LABEL_73;
                                                        RefCounted = CreateRefCountedObj<CCoSimpleArray<_tagpropertykey,4294967294,CSimpleArrayStandardCompareHelper<_tagpropertykey>>,>(stringa);
                                                        v20 = (char *)this + 256;
                                                        Microsoft::WRL::ComPtr<CRefCountedObject<CCoSimpleArray<_tagpropertykey,4294967294,CSimpleArrayStandardCompareHelper<_tagpropertykey>>>>::operator=(
                                                          (char *)this + 256,
                                                          RefCounted);
                                                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(stringa);
                                                        FileTypeFilter = *((_QWORD *)this + 32)
                                                                       ? CTSimpleArray<_tagpropertykey,4294967294,CTPolicyCoTaskMem<_tagpropertykey>,CSimpleArrayStandardCompareHelper<_tagpropertykey>,CSimpleArrayStandardMergeHelper<_tagpropertykey>>::_EnsureCapacity(
                                                                           *((_QWORD *)this + 32) + 8LL,
                                                                           pv)
                                                                       : -2147024882;
                                                        if ( FileTypeFilter >= 0 )
                                                        {
                                                          stringa[0] = 0;
                                                          v21 = *(_QWORD *)v20;
                                                          for ( k = pv;
                                                                *(_QWORD *)(*(_QWORD *)v20 + 16LL) < (unsigned __int64)pv;
                                                                k = pv )
                                                          {
                                                            v23 = (_QWORD *)(v21 + 8);
                                                            v24 = *(_QWORD *)(v21 + 16);
                                                            if ( v24 != v23[3]
                                                              || (int)CTSimpleArray<_tagpropertykey,4294967294,CTPolicyCoTaskMem<_tagpropertykey>,CSimpleArrayStandardCompareHelper<_tagpropertykey>,CSimpleArrayStandardMergeHelper<_tagpropertykey>>::_EnsureCapacity(
                                                                        v23,
                                                                        v24 + 1) >= 0 )
                                                            {
                                                              ++v23[1];
                                                              v25 = *v23 + 4 * (5LL * v23[1] - 5);
                                                              if ( v25 )
                                                              {
                                                                *(_OWORD *)v25 = 0;
                                                                *(_DWORD *)(v25 + 16) = 0;
                                                              }
                                                            }
                                                            v21 = *(_QWORD *)v20;
                                                          }
                                                          FileTypeFilter = IStream_Read(v5, *(void **)(v21 + 8), 20 * k);
                                                          if ( FileTypeFilter >= 0 )
                                                          {
LABEL_73:
                                                            pv = 0;
                                                            FileTypeFilter = IStream_Read(v5, &pv, 4u);
                                                            if ( FileTypeFilter >= 0 && (*((_QWORD *)this + 21) || pv) )
                                                            {
                                                              v32 = 0;
                                                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                                                              FileTypeFilter = CQueryOptions::_GetStorageProviderIdFilter(
                                                                                 this,
                                                                                 &v32);
                                                              if ( FileTypeFilter >= 0 )
                                                              {
                                                                FileTypeFilter = (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)v32 + 120LL))(v32);
                                                                if ( FileTypeFilter >= 0 )
                                                                {
                                                                  for ( m = 0; m < pv; ++m )
                                                                  {
                                                                    if ( FileTypeFilter < 0 )
                                                                      break;
                                                                    *(_QWORD *)&v37 = 0;
                                                                    FileTypeFilter = CQueryOptions::_IStream_ReadString(
                                                                                       v26,
                                                                                       v5,
                                                                                       (struct Windows::Internal::String *)&v37);
                                                                    if ( FileTypeFilter >= 0 )
                                                                      FileTypeFilter = (*(__int64 (__fastcall **)(HSTRING, _QWORD))(*(_QWORD *)v32 + 104LL))(
                                                                                         v32,
                                                                                         v37);
                                                                    Windows::Internal::String::~String((Windows::Internal::String *)&v37);
                                                                  }
                                                                }
                                                              }
                                                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                  else
                                                  {
                                                    FileTypeFilter = -2147024809;
                                                    RoOriginateErrorW(2147942487LL, 5, L"value");
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  *((GUID *)this + 11) = v40;
LABEL_86:
  v28 = SharedConvertHResultToWinRTFileAPIError(FileTypeFilter, 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstm);
  return v28;
}

```

## disassembly

```asm
0x180325670  mov     rax, rsp
0x180325673  mov     [rax+10h], rbx
0x180325677  mov     [rax+18h], rsi
0x18032567b  push    rbp
0x18032567c  push    rdi
0x18032567d  push    r12
0x18032567f  push    r14
0x180325681  push    r15
0x180325683  lea     rbp, [rax-5Fh]
0x180325687  sub     rsp, 0C0h
0x18032568e  movaps  xmmword ptr [rax-38h], xmm6
0x180325692  mov     rax, cs:__security_cookie
0x180325699  xor     rax, rsp
0x18032569c  mov     [rbp+57h+var_40], rax
0x1803256a0  mov     rdi, rdx
0x1803256a3  mov     rsi, rcx
0x1803256a6  mov     eax, 1
0x1803256ab  lock xadd cs:?__wil_apiCallCounter@?3??LoadFromString@CQueryOptions@@UEAAJPEAUHSTRING__@@@Z@4JC, eax; long volatile `CQueryOptions::LoadFromString(HSTRING__ *)'::`4'::__wil_apiCallCounter
0x1803256b3  inc     eax
0x1803256b5  xor     r15d, r15d
0x1803256b8  cmp     eax, 1
0x1803256bb  jnz     short loc_1803256EF
0x1803256bd  lea     rax, ?__wil_apiCallCounter@?3??LoadFromString@CQueryOptions@@UEAAJPEAUHSTRING__@@@Z@4JC; long volatile `CQueryOptions::LoadFromString(HSTRING__ *)'::`4'::__wil_apiCallCounter
0x1803256c4  mov     [rbp+57h+pstm], rax
0x1803256c8  mov     [rbp+57h+var_A0], r15
0x1803256cc  lea     rax, ?RuntimeClass_Windows_Storage_Search_QueryOptions@@3QBGB; "Windows.Storage.Search.QueryOptions"
0x1803256d3  mov     qword ptr [rbp+57h+var_80], rax
0x1803256d7  lea     r9, [rbp+57h+pstm]
0x1803256db  lea     r8, [rbp+57h+var_A0]
0x1803256df  lea     rdx, aLoadfromstring; "LoadFromString"
0x1803256e6  lea     rcx, [rbp+57h+var_80]
0x1803256ea  call    ??$InitApiData@PEBGAEAY06$$CBG$$TPECJ@ApiTelemetryLogger@details@wil@@SAX$$QEAPEBGAEAY06$$CBG$$QEA$$T$$QEAPECJ@Z
0x1803256ef  mov     [rbp+57h+pstm], r15
0x1803256f3  xor     edx, edx; cbInit
0x1803256f5  xor     ecx, ecx; pInit
0x1803256f7  call    cs:__imp_SHCreateMemStream
0x1803256fe  nop     dword ptr [rax+rax+00h]
0x180325703  mov     rdx, rax
0x180325706  lea     rcx, [rbp+57h+pstm]
0x18032570a  call    ?Attach@?$ComPtr@VCSemanticTextQuery@@@WRL@Microsoft@@QEAAXPEAVCSemanticTextQuery@@@Z; Microsoft::WRL::ComPtr<CSemanticTextQuery>::Attach(CSemanticTextQuery *)
0x18032570f  mov     rbx, [rbp+57h+pstm]
0x180325713  test    rbx, rbx
0x180325716  jz      loc_180325E58
0x18032571c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180325723  movdqu  [rbp+57h+var_50], xmm0
0x180325728  xor     edx, edx; length
0x18032572a  mov     rcx, rdi; string
0x18032572d  call    cs:__imp_WindowsGetStringRawBuffer
0x180325734  nop     dword ptr [rax+rax+00h]
0x180325739  mov     r8, rbx
0x18032573c  mov     rdx, rax
0x18032573f  call    ?TextToBinary@@YAJW4BINARY_TEXT_ENCODE_SCHEME@@PEBGPEAUIStream@@@Z; TextToBinary(BINARY_TEXT_ENCODE_SCHEME,ushort const *,IStream *)
0x180325744  mov     edi, eax
0x180325746  test    eax, eax
0x180325748  js      loc_180325E4A
0x18032574e  mov     rcx, rbx
0x180325751  call    Stream_CheckVersion
0x180325756  mov     edi, eax
0x180325758  test    eax, eax
0x18032575a  js      loc_180325E4A
0x180325760  mov     [rbp+57h+pv], r15d
0x180325764  mov     r12d, 4
0x18032576a  mov     r8d, r12d; cb
0x18032576d  lea     rdx, [rbp+57h+pv]; pv
0x180325771  mov     rcx, rbx; pstm
0x180325774  call    cs:__imp_IStream_Read
0x18032577b  nop     dword ptr [rax+rax+00h]
0x180325780  mov     edi, eax
0x180325782  test    eax, eax
0x180325784  js      loc_180325E4A
0x18032578a  mov     rax, [rsi]
0x18032578d  mov     edx, [rbp+57h+pv]
0x180325790  mov     rcx, rsi
0x180325793  mov     rax, [rax+40h]
0x180325797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032579c  mov     edi, eax
0x18032579e  test    eax, eax
0x1803257a0  js      loc_180325E4A
0x1803257a6  mov     [rbp+57h+var_94], r15d
0x1803257aa  mov     r8d, r12d; cb
0x1803257ad  lea     rdx, [rbp+57h+var_94]; pv
0x1803257b1  mov     rcx, rbx; pstm
0x1803257b4  call    cs:__imp_IStream_Read
0x1803257bb  nop     dword ptr [rax+rax+00h]
0x1803257c0  mov     edi, eax
0x1803257c2  test    eax, eax
0x1803257c4  js      loc_180325E4A
0x1803257ca  mov     rax, [rsi]
0x1803257cd  mov     edx, [rbp+57h+var_94]
0x1803257d0  mov     rcx, rsi
0x1803257d3  mov     rax, [rax+80h]
0x1803257da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803257df  mov     edi, eax
0x1803257e1  test    eax, eax
0x1803257e3  js      loc_180325E4A
0x1803257e9  mov     [rbp+57h+var_90], r15d
0x1803257ed  mov     r8d, r12d; cb
0x1803257f0  lea     rdx, [rbp+57h+var_90]; pv
0x1803257f4  mov     rcx, rbx; pstm
0x1803257f7  call    cs:__imp_IStream_Read
0x1803257fe  nop     dword ptr [rax+rax+00h]
0x180325803  mov     edi, eax
0x180325805  test    eax, eax
0x180325807  js      loc_180325E4A
0x18032580d  mov     edx, [rbp+57h+var_90]
0x180325810  mov     rcx, rsi
0x180325813  call    ?put_DateStackOption@CQueryOptions@@AEAAJW4DateStackOption@Search@Storage@Windows@@@Z; CQueryOptions::put_DateStackOption(Windows::Storage::Search::DateStackOption)
0x180325818  mov     edi, eax
0x18032581a  test    eax, eax
0x18032581c  js      loc_180325E4A
0x180325822  lea     r8d, [r12+0Ch]; cb
0x180325827  lea     rdx, [rbp+57h+var_50]; pv
0x18032582b  mov     rcx, rbx; pstm
0x18032582e  call    cs:__imp_IStream_Read
0x180325835  nop     dword ptr [rax+rax+00h]
0x18032583a  mov     edi, eax
0x18032583c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59687846@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59687846@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846> `wil::Feature<__WilFeatureTraits_Feature_59687846>::GetImpl(void)'::`2'::impl
0x180325843  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59687846@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846>::__private_IsEnabled(void)
0x180325848  test    al, al
0x18032584a  jz      loc_1803258D8
0x180325850  test    edi, edi
0x180325852  js      loc_180325E4A
0x180325858  mov     [rbp+57h+var_98], r15b
0x18032585c  lea     r8d, [r12-3]; cb
0x180325861  lea     rdx, [rbp+57h+var_98]; pv
0x180325865  mov     rcx, rbx; pstm
0x180325868  call    cs:__imp_IStream_Read
0x18032586f  nop     dword ptr [rax+rax+00h]
0x180325874  mov     edi, eax
0x180325876  test    eax, eax
0x180325878  js      loc_180325E4A
0x18032587e  lea     r14, [rsi+18h]
0x180325882  mov     rax, [r14]
0x180325885  mov     dl, [rbp+57h+var_98]
0x180325888  mov     rcx, r14
0x18032588b  mov     rax, [rax+38h]
0x18032588f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325894  mov     edi, eax
0x180325896  test    eax, eax
0x180325898  js      loc_180325E4A
0x18032589e  mov     [rbp+57h+var_97], r15b
0x1803258a2  lea     r8d, [r12-3]; cb
0x1803258a7  lea     rdx, [rbp+57h+var_97]; pv
0x1803258ab  mov     rcx, rbx; pstm
0x1803258ae  call    cs:__imp_IStream_Read
0x1803258b5  nop     dword ptr [rax+rax+00h]
0x1803258ba  mov     edi, eax
0x1803258bc  test    eax, eax
0x1803258be  js      loc_180325E4A
0x1803258c4  mov     rax, [r14]
0x1803258c7  mov     dl, [rbp+57h+var_97]
0x1803258ca  mov     rcx, r14
0x1803258cd  mov     rax, [rax+48h]
0x1803258d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803258d6  mov     edi, eax
0x1803258d8  test    edi, edi
0x1803258da  js      loc_180325E4A
0x1803258e0  mov     [rbp+57h+var_A0], r15
0x1803258e4  lea     r8, [rbp+57h+var_A0]; struct Windows::Internal::String *
0x1803258e8  mov     rdx, rbx; struct IStream *
0x1803258eb  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x1803258f0  mov     edi, eax
0x1803258f2  test    eax, eax
0x1803258f4  js      loc_180325989
0x1803258fa  mov     rax, [rsi]
0x1803258fd  mov     rdx, [rbp+57h+var_A0]
0x180325901  mov     rcx, rsi
0x180325904  mov     rax, [rax+50h]
0x180325908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032590d  mov     edi, eax
0x18032590f  test    eax, eax
0x180325911  js      short loc_180325989
0x180325913  lea     r8, [rbp+57h+var_A0]; struct Windows::Internal::String *
0x180325917  mov     rdx, rbx; struct IStream *
0x18032591a  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x18032591f  mov     edi, eax
0x180325921  test    eax, eax
0x180325923  js      short loc_180325989
0x180325925  mov     rax, [rsi]
0x180325928  mov     rdx, [rbp+57h+var_A0]
0x18032592c  mov     rcx, rsi
0x18032592f  mov     rax, [rax+60h]
0x180325933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325938  mov     edi, eax
0x18032593a  test    eax, eax
0x18032593c  js      short loc_180325989
0x18032593e  lea     r8, [rbp+57h+var_A0]; struct Windows::Internal::String *
0x180325942  mov     rdx, rbx; struct IStream *
0x180325945  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x18032594a  mov     edi, eax
0x18032594c  test    eax, eax
0x18032594e  js      short loc_180325989
0x180325950  mov     rax, [rsi]
0x180325953  mov     rdx, [rbp+57h+var_A0]
0x180325957  mov     rcx, rsi
0x18032595a  mov     rax, [rax+70h]
0x18032595e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325963  mov     edi, eax
0x180325965  test    eax, eax
0x180325967  js      short loc_180325989
0x180325969  lea     r8, [rbp+57h+var_A0]; struct Windows::Internal::String *
0x18032596d  mov     rdx, rbx; struct IStream *
0x180325970  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x180325975  mov     edi, eax
0x180325977  test    eax, eax
0x180325979  js      short loc_180325989
0x18032597b  mov     rdx, [rbp+57h+var_A0]; HSTRING
0x18032597f  mov     rcx, rsi; this
0x180325982  call    ?put_GroupPropertyName@CQueryOptions@@AEAAJPEAUHSTRING__@@@Z; CQueryOptions::put_GroupPropertyName(HSTRING__ *)
0x180325987  mov     edi, eax
0x180325989  lea     rcx, [rbp+57h+var_A0]; this
0x18032598d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180325992  test    edi, edi
0x180325994  js      loc_180325E4A
0x18032599a  mov     [rbp+57h+pv], r15d
0x18032599e  mov     r8d, r12d; cb
0x1803259a1  lea     rdx, [rbp+57h+pv]; pv
0x1803259a5  mov     rcx, rbx; pstm
0x1803259a8  call    cs:__imp_IStream_Read
0x1803259af  nop     dword ptr [rax+rax+00h]
0x1803259b4  mov     edi, eax
0x1803259b6  test    eax, eax
0x1803259b8  js      loc_180325E4A
0x1803259be  cmp     [rsi+0A0h], r15
0x1803259c5  jnz     short loc_1803259D1
0x1803259c7  cmp     [rbp+57h+pv], r15d
0x1803259cb  jbe     loc_180325A62
0x1803259d1  mov     [rbp+57h+var_A0], r15
0x1803259d5  lea     rcx, [rbp+57h+var_A0]
0x1803259d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803259de  lea     rdx, [rbp+57h+var_A0]
0x1803259e2  mov     rcx, rsi
0x1803259e5  call    ?_GetFileTypeFilter@CQueryOptions@@AEAAJPEAPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z; CQueryOptions::_GetFileTypeFilter(Windows::Foundation::Collections::IVector<HSTRING__ *> * *)
0x1803259ea  mov     edi, eax
0x1803259ec  test    eax, eax
0x1803259ee  js      short loc_180325A51
0x1803259f0  mov     rcx, [rbp+57h+var_A0]
0x1803259f4  mov     rax, [rcx]
0x1803259f7  mov     rax, [rax+78h]
0x1803259fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325a00  mov     edi, eax
0x180325a02  test    eax, eax
0x180325a04  js      short loc_180325A51
0x180325a06  mov     r14d, r15d
0x180325a09  cmp     [rbp+57h+pv], r15d
0x180325a0d  jbe     short loc_180325A51
0x180325a0f  test    edi, edi
0x180325a11  js      short loc_180325A51
0x180325a13  mov     qword ptr [rbp+57h+var_80], r15
0x180325a17  lea     r8, [rbp+57h+var_80]; struct Windows::Internal::String *
0x180325a1b  mov     rdx, rbx; struct IStream *
0x180325a1e  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x180325a23  mov     edi, eax
0x180325a25  test    eax, eax
0x180325a27  js      short loc_180325A3F
0x180325a29  mov     rcx, [rbp+57h+var_A0]
0x180325a2d  mov     rax, [rcx]
0x180325a30  mov     rdx, qword ptr [rbp+57h+var_80]
0x180325a34  mov     rax, [rax+68h]
0x180325a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325a3d  mov     edi, eax
0x180325a3f  lea     rcx, [rbp+57h+var_80]; this
0x180325a43  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180325a48  inc     r14d
0x180325a4b  cmp     r14d, [rbp+57h+pv]
0x180325a4f  jb      short loc_180325A0F
0x180325a51  lea     rcx, [rbp+57h+var_A0]
0x180325a55  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180325a5a  test    edi, edi
0x180325a5c  js      loc_180325E4A
0x180325a62  mov     [rbp+57h+pv], r15d
0x180325a66  mov     r8d, r12d; cb
0x180325a69  lea     rdx, [rbp+57h+pv]; pv
0x180325a6d  mov     rcx, rbx; pstm
0x180325a70  call    cs:__imp_IStream_Read
0x180325a77  nop     dword ptr [rax+rax+00h]
0x180325a7c  mov     edi, eax
0x180325a7e  test    eax, eax
0x180325a80  js      loc_180325E4A
0x180325a86  cmp     [rsi+98h], r15
0x180325a8d  jnz     short loc_180325A99
0x180325a8f  cmp     [rbp+57h+pv], r15d
0x180325a93  jbe     loc_180325B60
0x180325a99  mov     [rbp+57h+var_A0], r15
0x180325a9d  lea     rcx, [rbp+57h+var_A0]
0x180325aa1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180325aa6  lea     rdx, [rbp+57h+var_A0]
0x180325aaa  mov     rcx, rsi
0x180325aad  call    ?_GetSortOrderVector@CQueryOptions@@AEAAJPEAPEAU?$IVector@USortEntry@Search@Storage@Windows@@@Collections@Foundation@Windows@@@Z; CQueryOptions::_GetSortOrderVector(Windows::Foundation::Collections::IVector<Windows::Storage::Search::SortEntry> * *)
0x180325ab2  mov     edi, eax
0x180325ab4  test    eax, eax
0x180325ab6  js      loc_180325B4F
0x180325abc  mov     rcx, [rbp+57h+var_A0]
0x180325ac0  mov     rax, [rcx]
0x180325ac3  mov     rax, [rax+78h]
0x180325ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325acc  mov     edi, eax
0x180325ace  test    eax, eax
0x180325ad0  js      short loc_180325B4F
0x180325ad2  mov     r14d, r15d
  ... truncated ...
```
