# CQueryOptions::LoadFromString(HSTRING__ *)

- ea: `0x1803135f0`
- end: `0x180313d9e`
- name: `?LoadFromString@CQueryOptions@@UEAAJPEAUHSTRING__@@@Z`
- size: `1966`
- prototype: `__int64 __fastcall(CQueryOptions *__hidden this, HSTRING string)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x1800297d8`
- `0x180034e98`
- `0x1800355e4`
- `0x180068eec`
- `0x180069ed4`
- `0x18006a3bc`
- `0x18006ad98`
- `0x18006d92c`
- `0x180128690`
- `0x180195a1c`
- `0x1801c0b60`
- `0x1801ecd78`
- `0x180234fa8`
- `0x180234fdc`
- `0x18024472c`
- `0x180287de8`
- `0x18028de20`
- `0x1802c03b8`
- `0x1803135f0`
- `0x1803a4cb0`
- `0x180420c5c`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180313b6b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180313b6b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803136e8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313722`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18031375f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313790`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803137c0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313800`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803138f4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803139b6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313a45`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313abf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313ad9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313af3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313b0d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313b27`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313b41`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313c7e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313c9c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803136e8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313722`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18031375f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313790`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803137c0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313800`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803138f4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1803139b6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313a45`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313abf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313ad9`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313af3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313b0d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313b27`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313b41`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313c7e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180313c9c`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180313677`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180313677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803136a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803136a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180313a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180313a74`

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
0x1803135f0  mov     rax, rsp
0x1803135f3  mov     [rax+10h], rbx
0x1803135f7  mov     [rax+18h], rsi
0x1803135fb  push    rbp
0x1803135fc  push    rdi
0x1803135fd  push    r12
0x1803135ff  push    r14
0x180313601  push    r15
0x180313603  lea     rbp, [rax-5Fh]
0x180313607  sub     rsp, 0C0h
0x18031360e  movaps  xmmword ptr [rax-38h], xmm6
0x180313612  mov     rax, cs:__security_cookie
0x180313619  xor     rax, rsp
0x18031361c  mov     [rbp+57h+var_40], rax
0x180313620  mov     rdi, rdx
0x180313623  mov     rsi, rcx
0x180313626  mov     eax, 1
0x18031362b  lock xadd cs:?__wil_apiCallCounter@?3??LoadFromString@CQueryOptions@@UEAAJPEAUHSTRING__@@@Z@4JC, eax; long volatile `CQueryOptions::LoadFromString(HSTRING__ *)'::`4'::__wil_apiCallCounter
0x180313633  inc     eax
0x180313635  xor     r15d, r15d
0x180313638  cmp     eax, 1
0x18031363b  jnz     short loc_18031366F
0x18031363d  lea     rax, ?__wil_apiCallCounter@?3??LoadFromString@CQueryOptions@@UEAAJPEAUHSTRING__@@@Z@4JC; long volatile `CQueryOptions::LoadFromString(HSTRING__ *)'::`4'::__wil_apiCallCounter
0x180313644  mov     [rbp+57h+pstm], rax
0x180313648  mov     [rbp+57h+var_A0], r15
0x18031364c  lea     rax, ?RuntimeClass_Windows_Storage_Search_QueryOptions@@3QBGB; "Windows.Storage.Search.QueryOptions"
0x180313653  mov     qword ptr [rbp+57h+var_80], rax
0x180313657  lea     r9, [rbp+57h+pstm]
0x18031365b  lea     r8, [rbp+57h+var_A0]
0x18031365f  lea     rdx, aLoadfromstring; "LoadFromString"
0x180313666  lea     rcx, [rbp+57h+var_80]
0x18031366a  call    ??$InitApiData@PEBGAEAY06$$CBG$$TPECJ@ApiTelemetryLogger@details@wil@@SAX$$QEAPEBGAEAY06$$CBG$$QEA$$T$$QEAPECJ@Z
0x18031366f  mov     [rbp+57h+pstm], r15
0x180313673  xor     edx, edx; cbInit
0x180313675  xor     ecx, ecx; pInit
0x180313677  call    cs:__imp_SHCreateMemStream
0x18031367d  mov     rdx, rax
0x180313680  lea     rcx, [rbp+57h+pstm]
0x180313684  call    ?Attach@?$ComPtr@VCSemanticTextQuery@@@WRL@Microsoft@@QEAAXPEAVCSemanticTextQuery@@@Z; Microsoft::WRL::ComPtr<CSemanticTextQuery>::Attach(CSemanticTextQuery *)
0x180313689  mov     rbx, [rbp+57h+pstm]
0x18031368d  test    rbx, rbx
0x180313690  jz      loc_180313D56
0x180313696  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18031369d  movdqu  [rbp+57h+var_50], xmm0
0x1803136a2  xor     edx, edx; length
0x1803136a4  mov     rcx, rdi; string
0x1803136a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1803136ad  mov     r8, rbx
0x1803136b0  mov     rdx, rax
0x1803136b3  call    ?TextToBinary@@YAJW4BINARY_TEXT_ENCODE_SCHEME@@PEBGPEAUIStream@@@Z; TextToBinary(BINARY_TEXT_ENCODE_SCHEME,ushort const *,IStream *)
0x1803136b8  mov     edi, eax
0x1803136ba  test    eax, eax
0x1803136bc  js      loc_180313D48
0x1803136c2  mov     rcx, rbx
0x1803136c5  call    Stream_CheckVersion
0x1803136ca  mov     edi, eax
0x1803136cc  test    eax, eax
0x1803136ce  js      loc_180313D48
0x1803136d4  mov     [rbp+57h+pv], r15d
0x1803136d8  mov     r12d, 4
0x1803136de  mov     r8d, r12d; cb
0x1803136e1  lea     rdx, [rbp+57h+pv]; pv
0x1803136e5  mov     rcx, rbx; pstm
0x1803136e8  call    cs:__imp_IStream_Read
0x1803136ee  mov     edi, eax
0x1803136f0  test    eax, eax
0x1803136f2  js      loc_180313D48
0x1803136f8  mov     rax, [rsi]
0x1803136fb  mov     edx, [rbp+57h+pv]
0x1803136fe  mov     rcx, rsi
0x180313701  mov     rax, [rax+40h]
0x180313705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031370a  mov     edi, eax
0x18031370c  test    eax, eax
0x18031370e  js      loc_180313D48
0x180313714  mov     [rbp+57h+var_94], r15d
0x180313718  mov     r8d, r12d; cb
0x18031371b  lea     rdx, [rbp+57h+var_94]; pv
0x18031371f  mov     rcx, rbx; pstm
0x180313722  call    cs:__imp_IStream_Read
0x180313728  mov     edi, eax
0x18031372a  test    eax, eax
0x18031372c  js      loc_180313D48
0x180313732  mov     rax, [rsi]
0x180313735  mov     edx, [rbp+57h+var_94]
0x180313738  mov     rcx, rsi
0x18031373b  mov     rax, [rax+80h]
0x180313742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180313747  mov     edi, eax
0x180313749  test    eax, eax
0x18031374b  js      loc_180313D48
0x180313751  mov     [rbp+57h+var_90], r15d
0x180313755  mov     r8d, r12d; cb
0x180313758  lea     rdx, [rbp+57h+var_90]; pv
0x18031375c  mov     rcx, rbx; pstm
0x18031375f  call    cs:__imp_IStream_Read
0x180313765  mov     edi, eax
0x180313767  test    eax, eax
0x180313769  js      loc_180313D48
0x18031376f  mov     edx, [rbp+57h+var_90]
0x180313772  mov     rcx, rsi
0x180313775  call    ?put_DateStackOption@CQueryOptions@@AEAAJW4DateStackOption@Search@Storage@Windows@@@Z; CQueryOptions::put_DateStackOption(Windows::Storage::Search::DateStackOption)
0x18031377a  mov     edi, eax
0x18031377c  test    eax, eax
0x18031377e  js      loc_180313D48
0x180313784  lea     r8d, [r12+0Ch]; cb
0x180313789  lea     rdx, [rbp+57h+var_50]; pv
0x18031378d  mov     rcx, rbx; pstm
0x180313790  call    cs:__imp_IStream_Read
0x180313796  mov     edi, eax
0x180313798  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59687846@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59687846@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846> `wil::Feature<__WilFeatureTraits_Feature_59687846>::GetImpl(void)'::`2'::impl
0x18031379f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59687846@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687846>::__private_IsEnabled(void)
0x1803137a4  test    al, al
0x1803137a6  jz      short loc_180313824
0x1803137a8  test    edi, edi
0x1803137aa  js      loc_180313D48
0x1803137b0  mov     [rbp+57h+var_98], r15b
0x1803137b4  lea     r8d, [r12-3]; cb
0x1803137b9  lea     rdx, [rbp+57h+var_98]; pv
0x1803137bd  mov     rcx, rbx; pstm
0x1803137c0  call    cs:__imp_IStream_Read
0x1803137c6  mov     edi, eax
0x1803137c8  test    eax, eax
0x1803137ca  js      loc_180313D48
0x1803137d0  lea     r14, [rsi+18h]
0x1803137d4  mov     rax, [r14]
0x1803137d7  mov     dl, [rbp+57h+var_98]
0x1803137da  mov     rcx, r14
0x1803137dd  mov     rax, [rax+38h]
0x1803137e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803137e6  mov     edi, eax
0x1803137e8  test    eax, eax
0x1803137ea  js      loc_180313D48
0x1803137f0  mov     [rbp+57h+var_97], r15b
0x1803137f4  lea     r8d, [r12-3]; cb
0x1803137f9  lea     rdx, [rbp+57h+var_97]; pv
0x1803137fd  mov     rcx, rbx; pstm
0x180313800  call    cs:__imp_IStream_Read
0x180313806  mov     edi, eax
0x180313808  test    eax, eax
0x18031380a  js      loc_180313D48
0x180313810  mov     rax, [r14]
0x180313813  mov     dl, [rbp+57h+var_97]
0x180313816  mov     rcx, r14
0x180313819  mov     rax, [rax+48h]
0x18031381d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180313822  mov     edi, eax
0x180313824  test    edi, edi
0x180313826  js      loc_180313D48
0x18031382c  mov     [rbp+57h+var_A0], r15
0x180313830  lea     r8, [rbp+57h+var_A0]; struct Windows::Internal::String *
0x180313834  mov     rdx, rbx; struct IStream *
0x180313837  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x18031383c  mov     edi, eax
0x18031383e  test    eax, eax
0x180313840  js      loc_1803138D5
0x180313846  mov     rax, [rsi]
0x180313849  mov     rdx, [rbp+57h+var_A0]
0x18031384d  mov     rcx, rsi
0x180313850  mov     rax, [rax+50h]
0x180313854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180313859  mov     edi, eax
0x18031385b  test    eax, eax
0x18031385d  js      short loc_1803138D5
0x18031385f  lea     r8, [rbp+57h+var_A0]; struct Windows::Internal::String *
0x180313863  mov     rdx, rbx; struct IStream *
0x180313866  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x18031386b  mov     edi, eax
0x18031386d  test    eax, eax
0x18031386f  js      short loc_1803138D5
0x180313871  mov     rax, [rsi]
0x180313874  mov     rdx, [rbp+57h+var_A0]
0x180313878  mov     rcx, rsi
0x18031387b  mov     rax, [rax+60h]
0x18031387f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180313884  mov     edi, eax
0x180313886  test    eax, eax
0x180313888  js      short loc_1803138D5
0x18031388a  lea     r8, [rbp+57h+var_A0]; struct Windows::Internal::String *
0x18031388e  mov     rdx, rbx; struct IStream *
0x180313891  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x180313896  mov     edi, eax
0x180313898  test    eax, eax
0x18031389a  js      short loc_1803138D5
0x18031389c  mov     rax, [rsi]
0x18031389f  mov     rdx, [rbp+57h+var_A0]
0x1803138a3  mov     rcx, rsi
0x1803138a6  mov     rax, [rax+70h]
0x1803138aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803138af  mov     edi, eax
0x1803138b1  test    eax, eax
0x1803138b3  js      short loc_1803138D5
0x1803138b5  lea     r8, [rbp+57h+var_A0]; struct Windows::Internal::String *
0x1803138b9  mov     rdx, rbx; struct IStream *
0x1803138bc  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x1803138c1  mov     edi, eax
0x1803138c3  test    eax, eax
0x1803138c5  js      short loc_1803138D5
0x1803138c7  mov     rdx, [rbp+57h+var_A0]; HSTRING
0x1803138cb  mov     rcx, rsi; this
0x1803138ce  call    ?put_GroupPropertyName@CQueryOptions@@AEAAJPEAUHSTRING__@@@Z; CQueryOptions::put_GroupPropertyName(HSTRING__ *)
0x1803138d3  mov     edi, eax
0x1803138d5  lea     rcx, [rbp+57h+var_A0]; this
0x1803138d9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1803138de  test    edi, edi
0x1803138e0  js      loc_180313D48
0x1803138e6  mov     [rbp+57h+pv], r15d
0x1803138ea  mov     r8d, r12d; cb
0x1803138ed  lea     rdx, [rbp+57h+pv]; pv
0x1803138f1  mov     rcx, rbx; pstm
0x1803138f4  call    cs:__imp_IStream_Read
0x1803138fa  mov     edi, eax
0x1803138fc  test    eax, eax
0x1803138fe  js      loc_180313D48
0x180313904  cmp     [rsi+0A0h], r15
0x18031390b  jnz     short loc_180313917
0x18031390d  cmp     [rbp+57h+pv], r15d
0x180313911  jbe     loc_1803139A8
0x180313917  mov     [rbp+57h+var_A0], r15
0x18031391b  lea     rcx, [rbp+57h+var_A0]
0x18031391f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180313924  lea     rdx, [rbp+57h+var_A0]
0x180313928  mov     rcx, rsi
0x18031392b  call    ?_GetFileTypeFilter@CQueryOptions@@AEAAJPEAPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z; CQueryOptions::_GetFileTypeFilter(Windows::Foundation::Collections::IVector<HSTRING__ *> * *)
0x180313930  mov     edi, eax
0x180313932  test    eax, eax
0x180313934  js      short loc_180313997
0x180313936  mov     rcx, [rbp+57h+var_A0]
0x18031393a  mov     rax, [rcx]
0x18031393d  mov     rax, [rax+78h]
0x180313941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180313946  mov     edi, eax
0x180313948  test    eax, eax
0x18031394a  js      short loc_180313997
0x18031394c  mov     r14d, r15d
0x18031394f  cmp     [rbp+57h+pv], r15d
0x180313953  jbe     short loc_180313997
0x180313955  test    edi, edi
0x180313957  js      short loc_180313997
0x180313959  mov     qword ptr [rbp+57h+var_80], r15
0x18031395d  lea     r8, [rbp+57h+var_80]; struct Windows::Internal::String *
0x180313961  mov     rdx, rbx; struct IStream *
0x180313964  call    ?_IStream_ReadString@CQueryOptions@@AEAAJPEAUIStream@@PEAVString@Internal@Windows@@@Z; CQueryOptions::_IStream_ReadString(IStream *,Windows::Internal::String *)
0x180313969  mov     edi, eax
0x18031396b  test    eax, eax
0x18031396d  js      short loc_180313985
0x18031396f  mov     rcx, [rbp+57h+var_A0]
0x180313973  mov     rax, [rcx]
0x180313976  mov     rdx, qword ptr [rbp+57h+var_80]
0x18031397a  mov     rax, [rax+68h]
0x18031397e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180313983  mov     edi, eax
0x180313985  lea     rcx, [rbp+57h+var_80]; this
0x180313989  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18031398e  inc     r14d
0x180313991  cmp     r14d, [rbp+57h+pv]
0x180313995  jb      short loc_180313955
0x180313997  lea     rcx, [rbp+57h+var_A0]
0x18031399b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803139a0  test    edi, edi
0x1803139a2  js      loc_180313D48
0x1803139a8  mov     [rbp+57h+pv], r15d
0x1803139ac  mov     r8d, r12d; cb
0x1803139af  lea     rdx, [rbp+57h+pv]; pv
0x1803139b3  mov     rcx, rbx; pstm
0x1803139b6  call    cs:__imp_IStream_Read
0x1803139bc  mov     edi, eax
0x1803139be  test    eax, eax
0x1803139c0  js      loc_180313D48
0x1803139c6  cmp     [rsi+98h], r15
0x1803139cd  jnz     short loc_1803139D9
0x1803139cf  cmp     [rbp+57h+pv], r15d
0x1803139d3  jbe     loc_180313A94
0x1803139d9  mov     [rbp+57h+var_A0], r15
0x1803139dd  lea     rcx, [rbp+57h+var_A0]
0x1803139e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803139e6  lea     rdx, [rbp+57h+var_A0]
0x1803139ea  mov     rcx, rsi
0x1803139ed  call    ?_GetSortOrderVector@CQueryOptions@@AEAAJPEAPEAU?$IVector@USortEntry@Search@Storage@Windows@@@Collections@Foundation@Windows@@@Z; CQueryOptions::_GetSortOrderVector(Windows::Foundation::Collections::IVector<Windows::Storage::Search::SortEntry> * *)
0x1803139f2  mov     edi, eax
0x1803139f4  test    eax, eax
0x1803139f6  js      loc_180313A83
0x1803139fc  mov     rcx, [rbp+57h+var_A0]
0x180313a00  mov     rax, [rcx]
0x180313a03  mov     rax, [rax+78h]
0x180313a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180313a0c  mov     edi, eax
0x180313a0e  test    eax, eax
0x180313a10  js      short loc_180313A83
0x180313a12  mov     r14d, r15d
0x180313a15  cmp     [rbp+57h+pv], r15d
0x180313a19  jbe     short loc_180313A83
0x180313a1b  test    edi, edi
0x180313a1d  js      short loc_180313A83
0x180313a1f  xorps   xmm0, xmm0
0x180313a22  movups  xmmword ptr [rbp+57h+string], xmm0
0x180313a26  lea     r8, [rbp+57h+string]; HSTRING *
0x180313a2a  mov     rdx, rbx; struct IStream *
0x180313a2d  call    ?_IStream_ReadHSTRING@CQueryOptions@@AEAAJPEAUIStream@@PEAPEAUHSTRING__@@@Z; CQueryOptions::_IStream_ReadHSTRING(IStream *,HSTRING__ * *)
0x180313a32  mov     edi, eax
  ... truncated ...
```
