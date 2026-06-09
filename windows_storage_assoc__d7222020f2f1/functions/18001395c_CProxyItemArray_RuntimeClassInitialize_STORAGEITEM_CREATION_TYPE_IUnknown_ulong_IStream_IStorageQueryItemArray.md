# CProxyItemArray::RuntimeClassInitialize(STORAGEITEM_CREATION_TYPE,IUnknown *,ulong,IStream *,IStorageQueryItemArray *,Windows::Foundation::Collections::IMap<HSTRING__ *,IWeakReference *> *)

- ea: `0x18001395c`
- end: `0x180014062`
- name: `?RuntimeClassInitialize@CProxyItemArray@@QEAAJW4STORAGEITEM_CREATION_TYPE@@PEAUIUnknown@@KPEAUIStream@@PEAUIStorageQueryItemArray@@PEAU?$IMap@PEAUHSTRING__@@PEAUIWeakReference@@@Collections@Foundation@Windows@@@Z`
- size: `1798`
- prototype: `__int64 __fastcall(int, int, int, int, IStream *pstm, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18027ccd4`

## callees

- `0x180009fc0`
- `0x1800109dc`
- `0x1800118c4`
- `0x180013200`
- `0x18001395c`
- `0x180014068`
- `0x180014478`
- `0x180016078`
- `0x1800236bc`
- `0x18002ca8c`
- `0x18007af50`
- `0x18011ca08`
- `0x18011d6c8`
- `0x18027a8c0`
- `0x18027a960`
- `0x18036e88c`
- `0x1803b1f60`
- `0x1803b243c`
- `0x18067d010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800139c4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800139e3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a13`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a2f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a4b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a67`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a91`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013afa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013e35`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800139c4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800139e3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a13`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a2f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a4b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a67`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013a91`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013afa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180013e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180013d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013ba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013ba1`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CProxyItemArray::RuntimeClassInitialize(
        __int64 a1,
        unsigned int a2,
        void (__fastcall ***a3)(_QWORD, GUID *, __int64 *),
        int a4,
        IStream *pstm,
        __int64 a6,
        __int64 a7)
{
  HRESULT HSTRINGWithSpecifiedDefault; // edi
  __int64 v10; // rsi
  _QWORD *v12; // r15
  unsigned int v13; // r12d
  HSTRING v14; // rbx
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  struct IPropertyStore *v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v19; // rcx
  struct IPropertyStore *v20; // rcx
  __int64 v21; // r13
  int v22; // edi
  int v23; // r12d
  int v24; // r13d
  CPrefetchedProperties *v25; // rax
  CPrefetchedProperties *v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v31; // rcx
  void (__fastcall *v32)(_QWORD, GUID *, __int64 *); // rbx
  unsigned __int64 v33; // rdx
  int v34; // r8d
  __int64 v35; // rdx
  int v36; // [rsp+48h] [rbp-C0h]
  bool v37; // [rsp+58h] [rbp-B0h]
  HSTRING string; // [rsp+60h] [rbp-A8h] BYREF
  int v39; // [rsp+68h] [rbp-A0h]
  unsigned int v40; // [rsp+6Ch] [rbp-9Ch]
  __int64 v41; // [rsp+70h] [rbp-98h]
  __int64 v42; // [rsp+78h] [rbp-90h] BYREF
  __int64 v43; // [rsp+80h] [rbp-88h]
  __int64 v44; // [rsp+88h] [rbp-80h]
  struct IPropertyStore *v45; // [rsp+90h] [rbp-78h]
  unsigned int v46; // [rsp+98h] [rbp-70h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp-68h] BYREF
  struct IPropertyStore *v48; // [rsp+A8h] [rbp-60h] BYREF
  int pv; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int pv_4; // [rsp+B4h] [rbp-54h] BYREF
  int v51; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-40h] BYREF
  struct IPropertyStore *v54; // [rsp+D0h] [rbp-38h] BYREF
  int v55; // [rsp+D8h] [rbp-30h] BYREF
  int v56; // [rsp+DCh] [rbp-2Ch] BYREF
  int v57; // [rsp+E0h] [rbp-28h] BYREF
  int v58; // [rsp+E4h] [rbp-24h] BYREF
  int v59; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v60; // [rsp+F0h] [rbp-18h] BYREF

  LODWORD(v41) = a4;
  v40 = a2;
  v43 = a6;
  v44 = a7;
  pv_4 = 0;
  HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &pv_4, 4u);
  v59 = 0;
  if ( HSTRINGWithSpecifiedDefault >= 0 )
    HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v59, 4u);
  v58 = 5;
  v51 = 0;
  v57 = 4;
  v56 = 100;
  if ( HSTRINGWithSpecifiedDefault >= 0 )
  {
    HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v58, 4u);
    if ( HSTRINGWithSpecifiedDefault >= 0 )
    {
      HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v51, 4u);
      if ( HSTRINGWithSpecifiedDefault >= 0 )
      {
        HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v57, 4u);
        if ( HSTRINGWithSpecifiedDefault >= 0 )
          HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v56, 4u);
      }
    }
  }
  v46 = 0;
  v10 = 0;
  v42 = 0;
  if ( HSTRINGWithSpecifiedDefault >= 0 )
  {
    HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v46, 4u);
    if ( HSTRINGWithSpecifiedDefault >= 0 )
    {
      if ( !v46 )
      {
LABEL_14:
        v60 = 0;
        if ( a3 )
        {
          v32 = **a3;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
          v32(a3, &GUID_60e1feec_e458_4a19_8022_fb2471e3ec0b, &v60);
        }
        v55 = 0;
        v37 = !a7 || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)a7 + 56LL))(a7, &v55) >= 0 && !v55;
        v12 = (_QWORD *)(a1 + 48);
        CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(
          a1 + 48,
          pv_4);
        v13 = 0;
        v39 = 0;
        do
        {
          if ( v13 >= pv_4 )
            break;
          v47 = 0;
          v54 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
          HSTRINGWithSpecifiedDefault = PropertyStore_UnmarshalAdditionalData(pstm, &v54);
          if ( HSTRINGWithSpecifiedDefault >= 0 )
          {
            string = 0;
            HSTRINGWithSpecifiedDefault = IPropertyStore_GetHSTRINGWithSpecifiedDefault(
                                            v54,
                                            PKEY_FileAPI_FolderRelativeId,
                                            0,
                                            &string);
            v14 = string;
            if ( HSTRINGWithSpecifiedDefault >= 0 )
            {
              v21 = v44;
              if ( !v44
                || v37
                || WindowsIsStringEmpty(string)
                || (HSTRINGWithSpecifiedDefault = FindInWeakStringMap<Windows::Storage::IStorageItem>(v14, v21, &v47),
                    HSTRINGWithSpecifiedDefault >= 0) )
              {
                if ( !v47 )
                {
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                  HSTRINGWithSpecifiedDefault = StorageItem_CreateProxy_Private(v40, v54, v43, v13);
                  if ( HSTRINGWithSpecifiedDefault >= 0 )
                  {
                    if ( v40 != 1 )
                      goto LABEL_96;
                    v48 = 0;
                    HSTRINGWithSpecifiedDefault = Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>::As<IStorageItemInformationInternal>(
                                                    &v47,
                                                    &v48);
                    if ( HSTRINGWithSpecifiedDefault >= 0 )
                      HSTRINGWithSpecifiedDefault = ((__int64 (__fastcall *)(struct IPropertyStore *, HSTRING, _QWORD, __int64))v48->lpVtbl->GetCount)(
                                                      v48,
                                                      v14,
                                                      v13 + (unsigned int)v41,
                                                      v60);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                    if ( HSTRINGWithSpecifiedDefault >= 0 )
                    {
LABEL_96:
                      if ( v21 && !WindowsIsStringEmpty(v14) )
                        HSTRINGWithSpecifiedDefault = InsertInWeakStringMap(v14, v47, v21);
                    }
                  }
                }
              }
            }
            if ( v14 )
              WindowsDeleteString(v14);
            if ( HSTRINGWithSpecifiedDefault >= 0 )
            {
              HSTRINGWithSpecifiedDefault = 0;
              v15 = v12[1];
              if ( v15 != v12[3]
                || (HSTRINGWithSpecifiedDefault = CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(
                                                    v12,
                                                    v15 + 1),
                    HSTRINGWithSpecifiedDefault >= 0) )
              {
                v16 = (_QWORD *)(*v12 + 8 * v12[1]++);
                if ( v16 )
                {
                  *v16 = v47;
                  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v16);
                }
              }
              if ( HSTRINGWithSpecifiedDefault >= 0 )
              {
                v48 = 0;
                if ( !v46
                  || (pv = 0, HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &pv, 4u),
                              HSTRINGWithSpecifiedDefault >= 0)
                  && (!pv
                   || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48),
                       HSTRINGWithSpecifiedDefault = PropertyStore_UnmarshalAdditionalData(pstm, &v48),
                       HSTRINGWithSpecifiedDefault >= 0)) )
                {
                  if ( v51 || v48 )
                  {
                    v53 = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
                    v22 = v56;
                    v23 = v57;
                    v24 = v51;
                    pv = v58;
                    v45 = v48;
                    LODWORD(v52) = v59;
                    v53 = 0;
                    v25 = (CPrefetchedProperties *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
                    string = (HSTRING)v25;
                    if ( v25 )
                    {
                      v26 = CPrefetchedProperties::CPrefetchedProperties(v25);
                      string = 0;
                      v36 = v23;
                      v13 = v39;
                      HSTRINGWithSpecifiedDefault = CPrefetchedProperties::RuntimeClassInitialize(
                                                      (_DWORD)v26,
                                                      v43,
                                                      v39,
                                                      v10,
                                                      v52,
                                                      (__int64)v45,
                                                      pv,
                                                      v24,
                                                      v36,
                                                      v22);
                      if ( HSTRINGWithSpecifiedDefault >= 0 )
                      {
                        HSTRINGWithSpecifiedDefault = (**(__int64 (__fastcall ***)(CPrefetchedProperties *, GUID *, __int64 *))v26)(
                                                        v26,
                                                        &GUID_2b5b8d70_cd27_46d0_a04b_bf8c7fc9b5c6,
                                                        &v53);
                        (*(void (__fastcall **)(CPrefetchedProperties *))(*(_QWORD *)v26 + 16LL))(v26);
                        Microsoft::WRL::Details::MakeAllocator<CStorageItemThumbnailProxy>::~MakeAllocator<CStorageItemThumbnailProxy>(&string);
                        if ( HSTRINGWithSpecifiedDefault >= 0 )
                        {
                          v52 = 0;
                          v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
                          v30 = **v47;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                          HSTRINGWithSpecifiedDefault = v30(v29, &GUID_c5ab533a_1b75_4bb7_9ae6_3cee5057fac7, &v52);
                          if ( HSTRINGWithSpecifiedDefault >= 0 )
                            HSTRINGWithSpecifiedDefault = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 24LL))(
                                                            v52,
                                                            v53);
                          v31 = v52;
                          if ( v52 )
                          {
                            v52 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                          }
                        }
                      }
                      else if ( v26 )
                      {
                        (*(void (__fastcall **)(CPrefetchedProperties *))(*(_QWORD *)v26 + 16LL))(v26);
                      }
                    }
                    else
                    {
                      Microsoft::WRL::Details::MakeAllocator<CStorageItemThumbnailProxy>::~MakeAllocator<CStorageItemThumbnailProxy>(&string);
                      HSTRINGWithSpecifiedDefault = -2147024882;
                      v13 = v39;
                    }
                    v27 = v53;
                    if ( v53 )
                    {
                      v53 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                    }
                  }
                }
                v20 = v48;
                if ( v48 )
                {
                  v48 = 0;
                  ((void (__fastcall *)(struct IPropertyStore *))v20->lpVtbl->Release)(v20);
                }
              }
            }
          }
          v17 = v54;
          if ( v54 )
          {
            v54 = 0;
            ((void (__fastcall *)(struct IPropertyStore *))v17->lpVtbl->Release)(v17);
          }
          v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
          if ( v47 )
          {
            v47 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v18)[2])(v18);
          }
          v39 = ++v13;
        }
        while ( HSTRINGWithSpecifiedDefault >= 0 );
        v19 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        goto LABEL_10;
      }
      v28 = CreateRefCountedObj<CCoSimpleArray<_tagpropertykey,4294967294,CSimpleArrayStandardCompareHelper<_tagpropertykey>>,>(&string);
      Microsoft::WRL::ComPtr<CRefCountedObject<CCoSimpleArray<_tagpropertykey,4294967294,CSimpleArrayStandardCompareHelper<_tagpropertykey>>>>::operator=(
        &v42,
        v28);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      v10 = v42;
      if ( !v42 )
      {
        HSTRINGWithSpecifiedDefault = -2147024882;
        goto LABEL_10;
      }
      HSTRINGWithSpecifiedDefault = CTSimpleArray<_tagpropertykey,4294967294,CTPolicyCoTaskMem<_tagpropertykey>,CSimpleArrayStandardCompareHelper<_tagpropertykey>,CSimpleArrayStandardMergeHelper<_tagpropertykey>>::_EnsureCapacity(
                                      v42 + 8,
                                      v46);
      if ( HSTRINGWithSpecifiedDefault >= 0 )
      {
        while ( 1 )
        {
          v33 = *(_QWORD *)(v10 + 16);
          if ( v33 >= v46 )
          {
            HSTRINGWithSpecifiedDefault = IStream_Read(pstm, *(void **)(v10 + 8), 20 * v46);
            if ( HSTRINGWithSpecifiedDefault >= 0 )
              goto LABEL_14;
            break;
          }
          v34 = 0;
          string = 0;
          HSTRINGWithSpecifiedDefault = 0;
          if ( v33 != *(_QWORD *)(v10 + 32) )
            goto LABEL_89;
          HSTRINGWithSpecifiedDefault = CTSimpleArray<_tagpropertykey,4294967294,CTPolicyCoTaskMem<_tagpropertykey>,CSimpleArrayStandardCompareHelper<_tagpropertykey>,CSimpleArrayStandardMergeHelper<_tagpropertykey>>::_EnsureCapacity(
                                          v10 + 8,
                                          v33 + 1);
          if ( HSTRINGWithSpecifiedDefault < 0 )
          {
LABEL_91:
            if ( HSTRINGWithSpecifiedDefault < 0 )
              break;
          }
          else
          {
            v34 = (int)string;
LABEL_89:
            ++*(_QWORD *)(v10 + 16);
            v35 = *(_QWORD *)(v10 + 8) + 4 * (5LL * *(_QWORD *)(v10 + 16) - 5);
            if ( v35 )
            {
              *(_OWORD *)v35 = 0;
              *(_DWORD *)(v35 + 16) = v34;
              goto LABEL_91;
            }
          }
        }
      }
    }
  }
LABEL_10:
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)HSTRINGWithSpecifiedDefault;
}

```

## disassembly

```asm
0x18001395c  mov     rax, rsp
0x18001395f  mov     [rax+10h], rbx
0x180013963  push    rbp
0x180013964  push    rsi
0x180013965  push    rdi
0x180013966  push    r12
0x180013968  push    r13
0x18001396a  push    r14
0x18001396c  push    r15
0x18001396e  lea     rbp, [rax-48h]
0x180013972  sub     rsp, 110h
0x180013979  movaps  xmmword ptr [rax-48h], xmm6
0x18001397d  mov     rax, cs:__security_cookie
0x180013984  xor     rax, rsp
0x180013987  mov     [rbp+40h+var_50], rax
0x18001398b  mov     dword ptr [rsp+140h+var_D8], r9d
0x180013990  mov     r15, r8
0x180013993  mov     dword ptr [rsp+140h+var_E0+4], edx
0x180013997  mov     r13, rcx
0x18001399a  mov     r14, [rbp+40h+pstm]
0x18001399e  mov     rax, [rbp+40h+arg_28]
0x1800139a2  mov     [rsp+140h+var_C8], rax
0x1800139a7  mov     r12, [rbp+40h+arg_30]
0x1800139ae  mov     [rbp+40h+var_C0], r12
0x1800139b2  xor     ebx, ebx
0x1800139b4  mov     dword ptr [rbp+40h+pv+4], ebx
0x1800139b7  lea     esi, [rbx+4]
0x1800139ba  mov     r8d, esi; cb
0x1800139bd  lea     rdx, [rbp+40h+pv+4]; pv
0x1800139c1  mov     rcx, r14; pstm
0x1800139c4  call    cs:__imp_IStream_Read
0x1800139cb  nop     dword ptr [rax+rax+00h]
0x1800139d0  mov     edi, eax
0x1800139d2  mov     [rbp+40h+var_60], ebx
0x1800139d5  test    eax, eax
0x1800139d7  js      short loc_1800139F1
0x1800139d9  mov     r8d, esi; cb
0x1800139dc  lea     rdx, [rbp+40h+var_60]; pv
0x1800139e0  mov     rcx, r14; pstm
0x1800139e3  call    cs:__imp_IStream_Read
0x1800139ea  nop     dword ptr [rax+rax+00h]
0x1800139ef  mov     edi, eax
0x1800139f1  mov     [rbp+40h+var_64], 5
0x1800139f8  mov     [rbp+40h+var_90], ebx
0x1800139fb  mov     [rbp+40h+var_68], esi
0x1800139fe  mov     [rbp+40h+var_6C], 64h ; 'd'
0x180013a05  test    edi, edi
0x180013a07  js      short loc_180013A75
0x180013a09  mov     r8d, esi; cb
0x180013a0c  lea     rdx, [rbp+40h+var_64]; pv
0x180013a10  mov     rcx, r14; pstm
0x180013a13  call    cs:__imp_IStream_Read
0x180013a1a  nop     dword ptr [rax+rax+00h]
0x180013a1f  mov     edi, eax
0x180013a21  test    eax, eax
0x180013a23  js      short loc_180013A75
0x180013a25  mov     r8d, esi; cb
0x180013a28  lea     rdx, [rbp+40h+var_90]; pv
0x180013a2c  mov     rcx, r14; pstm
0x180013a2f  call    cs:__imp_IStream_Read
0x180013a36  nop     dword ptr [rax+rax+00h]
0x180013a3b  mov     edi, eax
0x180013a3d  test    eax, eax
0x180013a3f  js      short loc_180013A75
0x180013a41  mov     r8d, esi; cb
0x180013a44  lea     rdx, [rbp+40h+var_68]; pv
0x180013a48  mov     rcx, r14; pstm
0x180013a4b  call    cs:__imp_IStream_Read
0x180013a52  nop     dword ptr [rax+rax+00h]
0x180013a57  mov     edi, eax
0x180013a59  test    eax, eax
0x180013a5b  js      short loc_180013A75
0x180013a5d  mov     r8d, esi; cb
0x180013a60  lea     rdx, [rbp+40h+var_6C]; pv
0x180013a64  mov     rcx, r14; pstm
0x180013a67  call    cs:__imp_IStream_Read
0x180013a6e  nop     dword ptr [rax+rax+00h]
0x180013a73  mov     edi, eax
0x180013a75  mov     [rbp+40h+var_B0], ebx
0x180013a78  mov     rsi, rbx
0x180013a7b  mov     [rsp+140h+var_D0], rbx
0x180013a80  test    edi, edi
0x180013a82  js      short loc_180013AA7
0x180013a84  mov     r8d, 4; cb
0x180013a8a  lea     rdx, [rbp+40h+var_B0]; pv
0x180013a8e  mov     rcx, r14; pstm
0x180013a91  call    cs:__imp_IStream_Read
0x180013a98  nop     dword ptr [rax+rax+00h]
0x180013a9d  mov     edi, eax
0x180013a9f  test    eax, eax
0x180013aa1  jns     loc_180013E8E
0x180013aa7  test    rsi, rsi
0x180013aaa  jz      short loc_180013ABC
0x180013aac  mov     rax, [rsi]
0x180013aaf  mov     rcx, rsi
0x180013ab2  mov     rax, [rax+10h]
0x180013ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013abb  nop
0x180013abc  mov     eax, edi
0x180013abe  mov     rcx, [rbp+40h+var_50]
0x180013ac2  xor     rcx, rsp; StackCookie
0x180013ac5  call    __security_check_cookie
0x180013aca  lea     r11, [rsp+140h+var_30]
0x180013ad2  mov     rbx, [r11+48h]
0x180013ad6  movaps  xmm6, xmmword ptr [r11-10h]
0x180013adb  mov     rsp, r11
0x180013ade  pop     r15
0x180013ae0  pop     r14
0x180013ae2  pop     r13
0x180013ae4  pop     r12
0x180013ae6  pop     rdi
0x180013ae7  pop     rsi
0x180013ae8  pop     rbp
0x180013ae9  retn
0x180013aeb  lea     r8d, [rcx+rcx*4]
0x180013aef  shl     r8d, 2; cb
0x180013af3  mov     rdx, [rsi+8]; pv
0x180013af7  mov     rcx, r14; pstm
0x180013afa  call    cs:__imp_IStream_Read
0x180013b01  nop     dword ptr [rax+rax+00h]
0x180013b06  mov     edi, eax
0x180013b08  test    eax, eax
0x180013b0a  js      short loc_180013AA7
0x180013b0c  mov     [rbp+40h+var_58], rbx
0x180013b10  test    r15, r15
0x180013b13  jnz     loc_180013F94
0x180013b19  mov     [rbp+40h+var_70], ebx
0x180013b1c  test    r12, r12
0x180013b1f  jnz     loc_180013FC0
0x180013b25  mov     byte ptr [rsp+140h+var_F0], 1
0x180013b2a  lea     r15, [r13+30h]
0x180013b2e  mov     edx, dword ptr [rbp+40h+pv+4]
0x180013b31  mov     rcx, r15
0x180013b34  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180013b39  mov     r12d, ebx
0x180013b3c  mov     dword ptr [rsp+140h+var_E0], ebx
0x180013b40  cmp     r12d, dword ptr [rbp+40h+pv+4]
0x180013b44  jnb     loc_180013C2E
0x180013b4a  mov     [rbp+40h+var_A8], rbx
0x180013b4e  mov     [rbp+40h+var_78], rbx
0x180013b52  lea     rcx, [rbp+40h+var_78]
0x180013b56  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013b5b  lea     rdx, [rbp+40h+var_78]; struct IPropertyStore **
0x180013b5f  mov     rcx, r14; pstm
0x180013b62  call    ?PropertyStore_UnmarshalAdditionalData@@YAJPEAUIStream@@PEAPEAUIPropertyStore@@@Z; PropertyStore_UnmarshalAdditionalData(IStream *,IPropertyStore * *)
0x180013b67  mov     edi, eax
0x180013b69  test    eax, eax
0x180013b6b  js      short loc_180013BEA
0x180013b6d  mov     [rsp+140h+string], rbx
0x180013b72  lea     r9, [rsp+140h+string]
0x180013b77  xor     r8d, r8d
0x180013b7a  lea     rdx, PKEY_FileAPI_FolderRelativeId
0x180013b81  mov     rcx, [rbp+40h+var_78]
0x180013b85  call    IPropertyStore_GetHSTRINGWithSpecifiedDefault
0x180013b8a  mov     edi, eax
0x180013b8c  mov     rbx, [rsp+140h+string]
0x180013b91  test    eax, eax
0x180013b93  jns     loc_180013C8C
0x180013b99  test    rbx, rbx
0x180013b9c  jz      short loc_180013BAD
0x180013b9e  mov     rcx, rbx; string
0x180013ba1  call    cs:__imp_WindowsDeleteString
0x180013ba8  nop     dword ptr [rax+rax+00h]
0x180013bad  xor     ebx, ebx
0x180013baf  test    edi, edi
0x180013bb1  js      short loc_180013BEA
0x180013bb3  mov     edi, ebx
0x180013bb5  mov     rdx, [r15+8]
0x180013bb9  cmp     rdx, [r15+18h]
0x180013bbd  jz      loc_18001402F
0x180013bc3  inc     qword ptr [r15+8]
0x180013bc7  mov     rcx, [r15+8]
0x180013bcb  mov     rax, [r15]
0x180013bce  dec     rcx
0x180013bd1  lea     rcx, [rax+rcx*8]
0x180013bd5  test    rcx, rcx
0x180013bd8  jz      short loc_180013BE6
0x180013bda  mov     rax, [rbp+40h+var_A8]
0x180013bde  mov     [rcx], rax
0x180013be1  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180013be6  test    edi, edi
0x180013be8  jns     short loc_180013C4D
0x180013bea  mov     rcx, [rbp+40h+var_78]
0x180013bee  test    rcx, rcx
0x180013bf1  jz      short loc_180013C04
0x180013bf3  mov     [rbp+40h+var_78], rbx
0x180013bf7  mov     rax, [rcx]
0x180013bfa  mov     rax, [rax+10h]
0x180013bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c03  nop
0x180013c04  mov     rcx, [rbp+40h+var_A8]
0x180013c08  test    rcx, rcx
0x180013c0b  jz      short loc_180013C1E
0x180013c0d  mov     [rbp+40h+var_A8], rbx
0x180013c11  mov     rax, [rcx]
0x180013c14  mov     rax, [rax+10h]
0x180013c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c1d  nop
0x180013c1e  inc     r12d
0x180013c21  mov     dword ptr [rsp+140h+var_E0], r12d
0x180013c26  test    edi, edi
0x180013c28  jns     loc_180013B40
0x180013c2e  mov     rcx, [rbp+40h+var_58]
0x180013c32  test    rcx, rcx
0x180013c35  jz      short loc_180013C48
0x180013c37  mov     [rbp+40h+var_58], rbx
0x180013c3b  mov     rax, [rcx]
0x180013c3e  mov     rax, [rax+10h]
0x180013c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c47  nop
0x180013c48  jmp     loc_180013AA7
0x180013c4d  mov     [rbp+40h+var_A0], rbx
0x180013c51  cmp     [rbp+40h+var_B0], ebx
0x180013c54  ja      loc_180013E25
0x180013c5a  cmp     [rbp+40h+var_90], ebx
0x180013c5d  ja      loc_180013D45
0x180013c63  cmp     [rbp+40h+var_A0], rbx
0x180013c67  jnz     loc_180013D45
0x180013c6d  mov     rcx, [rbp+40h+var_A0]
0x180013c71  test    rcx, rcx
0x180013c74  jz      short loc_180013C87
0x180013c76  mov     [rbp+40h+var_A0], rbx
0x180013c7a  mov     rax, [rcx]
0x180013c7d  mov     rax, [rax+10h]
0x180013c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c86  nop
0x180013c87  jmp     loc_180013BEA
0x180013c8c  mov     r13, [rbp+40h+var_C0]
0x180013c90  test    r13, r13
0x180013c93  jz      short loc_180013CC8
0x180013c95  cmp     byte ptr [rsp+140h+var_F0], 0
0x180013c9a  jnz     short loc_180013CC8
0x180013c9c  mov     rcx, rbx; string
0x180013c9f  call    cs:__imp_WindowsIsStringEmpty
0x180013ca6  nop     dword ptr [rax+rax+00h]
0x180013cab  test    eax, eax
0x180013cad  jnz     short loc_180013CC8
0x180013caf  lea     r8, [rbp+40h+var_A8]
0x180013cb3  mov     rdx, r13
0x180013cb6  mov     rcx, rbx
0x180013cb9  call    ??$FindInWeakStringMap@UIStorageItem@Storage@Windows@@@@YAJPEAUHSTRING__@@PEAU?$IMap@PEAUHSTRING__@@PEAUIWeakReference@@@Collections@Foundation@Windows@@PEAPEAUIStorageItem@Storage@4@@Z; FindInWeakStringMap<Windows::Storage::IStorageItem>(HSTRING__ *,Windows::Foundation::Collections::IMap<HSTRING__ *,IWeakReference *> *,Windows::Storage::IStorageItem * *)
0x180013cbe  mov     edi, eax
0x180013cc0  test    eax, eax
0x180013cc2  js      loc_180013B99
0x180013cc8  cmp     [rbp+40h+var_A8], 0
0x180013ccd  jnz     loc_180013B99
0x180013cd3  lea     rcx, [rbp+40h+var_A8]
0x180013cd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013cdc  lea     rax, [rbp+40h+var_A8]
0x180013ce0  mov     [rsp+140h+var_118], rax
0x180013ce5  mov     r9d, r12d
0x180013ce8  mov     r8, [rsp+140h+var_C8]
0x180013ced  mov     rdx, [rbp+40h+var_78]
0x180013cf1  mov     ecx, dword ptr [rsp+140h+var_E0+4]
0x180013cf5  call    ?StorageItem_CreateProxy_Private@@YAJW4STORAGEITEM_CREATION_TYPE@@PEAUIPropertyStore@@PEAUIStorageQueryItemArray@@IAEBU_GUID@@PEAPEAX@Z; StorageItem_CreateProxy_Private(STORAGEITEM_CREATION_TYPE,IPropertyStore *,IStorageQueryItemArray *,uint,_GUID const &,void * *)
0x180013cfa  mov     edi, eax
0x180013cfc  test    eax, eax
0x180013cfe  js      loc_180013B99
0x180013d04  cmp     dword ptr [rsp+140h+var_E0+4], 1
0x180013d09  jz      loc_180013FEA
0x180013d0f  test    r13, r13
0x180013d12  jz      loc_180013B99
0x180013d18  mov     rcx, rbx; string
0x180013d1b  call    cs:__imp_WindowsIsStringEmpty
0x180013d22  nop     dword ptr [rax+rax+00h]
0x180013d27  test    eax, eax
0x180013d29  jnz     loc_180013B99
0x180013d2f  mov     r8, r13
0x180013d32  mov     rdx, [rbp+40h+var_A8]
0x180013d36  mov     rcx, rbx
0x180013d39  call    ?InsertInWeakStringMap@@YAJPEAUHSTRING__@@PEAUIUnknown@@PEAU?$IMap@PEAUHSTRING__@@PEAUIWeakReference@@@Collections@Foundation@Windows@@@Z; InsertInWeakStringMap(HSTRING__ *,IUnknown *,Windows::Foundation::Collections::IMap<HSTRING__ *,IWeakReference *> *)
0x180013d3e  mov     edi, eax
0x180013d40  jmp     loc_180013B99
0x180013d45  mov     [rbp+40h+var_80], rbx
0x180013d49  lea     rcx, [rbp+40h+var_80]
0x180013d4d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013d52  mov     edi, [rbp+40h+var_6C]
0x180013d55  mov     r12d, [rbp+40h+var_68]
0x180013d59  mov     r13d, [rbp+40h+var_90]
0x180013d5d  mov     eax, [rbp+40h+var_64]
0x180013d60  mov     dword ptr [rbp+40h+pv], eax
0x180013d63  mov     rax, [rbp+40h+var_A0]
0x180013d67  mov     [rbp+40h+var_B8], rax
0x180013d6b  mov     eax, [rbp+40h+var_60]
0x180013d6e  mov     dword ptr [rbp+40h+var_88], eax
0x180013d71  mov     [rbp+40h+var_80], rbx
0x180013d75  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013d7c  mov     ecx, 68h ; 'h'; unsigned __int64
0x180013d81  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013d86  mov     [rsp+140h+string], rax
0x180013d8b  test    rax, rax
0x180013d8e  jz      loc_180014049
0x180013d94  mov     rcx, rax; this
0x180013d97  call    ??0CPrefetchedProperties@@QEAA@XZ; CPrefetchedProperties::CPrefetchedProperties(void)
0x180013d9c  mov     rbx, rax
0x180013d9f  mov     [rsp+140h+string], 0
0x180013da8  mov     [rsp+140h+var_F8], edi
0x180013dac  mov     [rsp+140h+var_100], r12d
0x180013db1  mov     [rsp+140h+var_108], r13d
0x180013db6  mov     eax, dword ptr [rbp+40h+pv]
  ... truncated ...
```
