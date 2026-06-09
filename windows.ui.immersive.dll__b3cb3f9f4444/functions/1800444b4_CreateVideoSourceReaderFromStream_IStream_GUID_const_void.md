# CreateVideoSourceReaderFromStream(IStream *,_GUID const &,void * *)

- ea: `0x1800444b4`
- end: `0x180044798`
- name: `?CreateVideoSourceReaderFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `740`
- prototype: `__int64 __fastcall(struct IStream *pStream, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800441b4`
- `0x1800dd72c`

## callees

- `0x180013f14`
- `0x180014350`
- `0x1800343ec`
- `0x1800444b4`
- `0x1800ed010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180044626`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180044626`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044708`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180044708`
- `MFPlat!MFCreateAttributes` at `0x18004454b`
- `MFPlat!MFCreateAttributes` at `0x18004454b`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x1800444f0`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x1800444f0`
- `MFPlat!MFCreateSourceResolver` at `0x18004451b`
- `MFPlat!MFCreateSourceResolver` at `0x18004451b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateVideoSourceReaderFromStream(struct IStream *pStream, const struct _GUID *a2, void **a3)
{
  HRESULT v5; // ebx
  IMFSourceResolver *v6; // rdi
  HRESULT (__stdcall *CreateObjectFromByteStream)(IMFSourceResolver *, IMFByteStream *, LPCWSTR, DWORD, IPropertyStore *, MF_OBJECT_TYPE *, IUnknown **); // rbx
  LPVOID v9; // [rsp+40h] [rbp-40h] BYREF
  __int64 v10; // [rsp+48h] [rbp-38h] BYREF
  IMFSourceResolver *ppISourceResolver; // [rsp+50h] [rbp-30h] BYREF
  IMFByteStream *ppByteStream; // [rsp+58h] [rbp-28h] BYREF
  __int128 v13; // [rsp+60h] [rbp-20h] BYREF
  __int64 v14; // [rsp+70h] [rbp-10h]
  const struct _GUID *v15; // [rsp+A8h] [rbp+28h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+B0h] [rbp+30h] BYREF
  void *ppv; // [rsp+B8h] [rbp+38h] BYREF

  v15 = a2;
  *a3 = 0;
  ppByteStream = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppByteStream);
  v5 = MFCreateMFByteStreamOnStream(pStream, &ppByteStream);
  if ( v5 >= 0 )
  {
    ppISourceResolver = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppISourceResolver);
    v5 = MFCreateSourceResolver(&ppISourceResolver);
    if ( v5 >= 0 )
    {
      ppMFAttributes = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
      v5 = MFCreateAttributes(&ppMFAttributes, 8u);
      if ( v5 >= 0 )
      {
        v5 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               &MF_SOURCE_READER_ENABLE_VIDEO_PROCESSING,
               1);
        if ( v5 >= 0 )
        {
          ((void (__fastcall *)(IMFAttributes *, GUID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &GUID_9561c3e8_ea9e_4435_9b1e_a93e691894d8,
            1);
          ((void (__fastcall *)(IMFAttributes *, GUID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &GUID_5ae557b8_77af_41f5_9fa6_4db2fe1d4bca,
            256);
          ((void (__fastcall *)(IMFAttributes *, GUID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &GUID_7262a16a_d2dc_4e75_9ba8_65c0c6d32b13,
            256);
          ((void (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            MF_LOW_LATENCY,
            1);
          ppv = 0;
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
          v5 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
          if ( v5 >= 0 )
          {
            v14 = 0;
            v13 = 0;
            LOWORD(v13) = 11;
            WORD4(v13) = -1;
            v5 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                   ppv,
                   &MFPKEY_MediaSource_DisableReadAhead,
                   &v13);
            if ( v5 >= 0 )
            {
              v6 = ppISourceResolver;
              LODWORD(v15) = 0;
              v10 = 0;
              CreateObjectFromByteStream = ppISourceResolver->lpVtbl->CreateObjectFromByteStream;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
              v5 = ((__int64 (__fastcall *)(IMFSourceResolver *, IMFByteStream *, _QWORD, __int64, void *, const struct _GUID **, __int64 *))CreateObjectFromByteStream)(
                     v6,
                     ppByteStream,
                     0,
                     65553,
                     ppv,
                     &v15,
                     &v10);
              if ( v5 >= 0 )
              {
                v9 = 0;
                Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v9);
                v5 = CoCreateInstance(
                       &CLSID_MFReadWriteClassFactory,
                       0,
                       1u,
                       &GUID_e7fe2e12_661c_40da_92f9_4f002ab67627,
                       &v9);
                if ( v5 >= 0 )
                  v5 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, IMFAttributes *, GUID *, void **))(*(_QWORD *)v9 + 32LL))(
                         v9,
                         &CLSID_MFSourceReader,
                         v10,
                         ppMFAttributes,
                         &GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993,
                         a3);
                Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v9);
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
            }
          }
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppISourceResolver);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppByteStream);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800444b4  mov     [rsp-18h+arg_0], rbx
0x1800444b9  mov     [rsp-18h+arg_8], rdx
0x1800444be  push    rbp
0x1800444bf  push    rsi
0x1800444c0  push    rdi
0x1800444c1  mov     rbp, rsp
0x1800444c4  sub     rsp, 80h
0x1800444cb  mov     rbx, rcx
0x1800444ce  mov     qword ptr [r8], 0
0x1800444d5  lea     rcx, [rbp+ppByteStream]
0x1800444d9  mov     [rbp+ppByteStream], 0
0x1800444e1  mov     rsi, r8
0x1800444e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800444e9  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x1800444ed  mov     rcx, rbx; pStream
0x1800444f0  call    cs:__imp_MFCreateMFByteStreamOnStream
0x1800444f7  nop     dword ptr [rax+rax+00h]
0x1800444fc  mov     ebx, eax
0x1800444fe  test    eax, eax
0x180044500  js      loc_180044779
0x180044506  lea     rcx, [rbp+ppISourceResolver]
0x18004450a  mov     [rbp+ppISourceResolver], 0
0x180044512  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044517  lea     rcx, [rbp+ppISourceResolver]; ppISourceResolver
0x18004451b  call    cs:__imp_MFCreateSourceResolver
0x180044522  nop     dword ptr [rax+rax+00h]
0x180044527  mov     ebx, eax
0x180044529  test    eax, eax
0x18004452b  js      loc_180044770
0x180044531  lea     rcx, [rbp+ppMFAttributes]
0x180044535  mov     [rbp+ppMFAttributes], 0
0x18004453d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044542  mov     edx, 8; cInitialSize
0x180044547  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18004454b  call    cs:__imp_MFCreateAttributes
0x180044552  nop     dword ptr [rax+rax+00h]
0x180044557  mov     ebx, eax
0x180044559  test    eax, eax
0x18004455b  js      loc_180044767
0x180044561  mov     rcx, [rbp+ppMFAttributes]
0x180044565  lea     rdx, MF_SOURCE_READER_ENABLE_VIDEO_PROCESSING
0x18004456c  mov     r8d, 1
0x180044572  mov     rax, [rcx]
0x180044575  mov     rax, [rax+0A8h]
0x18004457c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044581  mov     ebx, eax
0x180044583  test    eax, eax
0x180044585  js      loc_180044767
0x18004458b  mov     rcx, [rbp+ppMFAttributes]
0x18004458f  lea     rdx, _GUID_9561c3e8_ea9e_4435_9b1e_a93e691894d8
0x180044596  mov     r8d, 1
0x18004459c  mov     rax, [rcx]
0x18004459f  mov     rax, [rax+0A8h]
0x1800445a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445ab  mov     rcx, [rbp+ppMFAttributes]
0x1800445af  lea     rdx, _GUID_5ae557b8_77af_41f5_9fa6_4db2fe1d4bca
0x1800445b6  mov     ebx, 100h
0x1800445bb  mov     r8d, ebx
0x1800445be  mov     rax, [rcx]
0x1800445c1  mov     rax, [rax+0A8h]
0x1800445c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445cd  mov     rcx, [rbp+ppMFAttributes]
0x1800445d1  lea     rdx, _GUID_7262a16a_d2dc_4e75_9ba8_65c0c6d32b13
0x1800445d8  mov     r8d, ebx
0x1800445db  mov     rax, [rcx]
0x1800445de  mov     rax, [rax+0A8h]
0x1800445e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445ea  mov     rcx, [rbp+ppMFAttributes]
0x1800445ee  lea     rdx, MF_LOW_LATENCY
0x1800445f5  mov     r8d, 1
0x1800445fb  mov     rax, [rcx]
0x1800445fe  mov     rax, [rax+0A8h]
0x180044605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004460a  lea     rcx, [rbp+ppv]
0x18004460e  mov     [rbp+ppv], 0
0x180044616  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18004461b  lea     rdx, [rbp+ppv]; ppv
0x18004461f  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180044626  call    cs:__imp_PSCreateMemoryPropertyStore
0x18004462d  nop     dword ptr [rax+rax+00h]
0x180044632  mov     ebx, eax
0x180044634  test    eax, eax
0x180044636  js      loc_18004475E
0x18004463c  mov     rcx, [rbp+ppv]
0x180044640  lea     r8, [rbp+var_20]
0x180044644  xor     eax, eax
0x180044646  lea     rdx, MFPKEY_MediaSource_DisableReadAhead
0x18004464d  mov     [rbp+var_10], rax
0x180044651  xorps   xmm0, xmm0
0x180044654  mov     eax, 0Bh
0x180044659  movups  [rbp+var_20], xmm0
0x18004465d  mov     word ptr [rbp+var_20], ax
0x180044661  or      eax, 0FFFFFFFFh
0x180044664  mov     word ptr [rbp+var_20+8], ax
0x180044668  mov     rax, [rcx]
0x18004466b  mov     rax, [rax+30h]
0x18004466f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044674  mov     ebx, eax
0x180044676  test    eax, eax
0x180044678  js      loc_18004475E
0x18004467e  mov     rdi, [rbp+ppISourceResolver]
0x180044682  lea     rcx, [rbp+var_38]
0x180044686  mov     dword ptr [rbp+arg_8], 0
0x18004468d  mov     [rbp+var_38], 0
0x180044695  mov     rax, [rdi]
0x180044698  mov     rbx, [rax+20h]
0x18004469c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800446a1  mov     r8, [rbp+ppv]
0x1800446a5  lea     rax, [rbp+var_38]
0x1800446a9  mov     rdx, [rbp+ppByteStream]
0x1800446ad  mov     r9d, 10011h
0x1800446b3  mov     [rsp+80h+var_50], rax
0x1800446b8  mov     rcx, rdi
0x1800446bb  lea     rax, [rbp+arg_8]
0x1800446bf  mov     [rsp+80h+var_58], rax
0x1800446c4  mov     rax, rbx
0x1800446c7  mov     [rsp+80h+var_60], r8
0x1800446cc  xor     r8d, r8d
0x1800446cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446d4  mov     ebx, eax
0x1800446d6  test    eax, eax
0x1800446d8  js      short loc_180044755
0x1800446da  lea     rcx, [rbp+var_40]
0x1800446de  mov     [rbp+var_40], 0
0x1800446e6  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800446eb  xor     edx, edx; pUnkOuter
0x1800446ed  lea     rax, [rbp+var_40]
0x1800446f1  lea     r9, _GUID_e7fe2e12_661c_40da_92f9_4f002ab67627; riid
0x1800446f8  mov     [rsp+80h+var_60], rax; ppv
0x1800446fd  lea     rcx, CLSID_MFReadWriteClassFactory; rclsid
0x180044704  lea     r8d, [rdx+1]; dwClsContext
0x180044708  call    cs:__imp_CoCreateInstance
0x18004470f  nop     dword ptr [rax+rax+00h]
0x180044714  mov     ebx, eax
0x180044716  test    eax, eax
0x180044718  js      short loc_18004474C
0x18004471a  mov     rcx, [rbp+var_40]
0x18004471e  lea     rdx, _GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993
0x180044725  mov     r9, [rbp+ppMFAttributes]
0x180044729  mov     r8, [rbp+var_38]
0x18004472d  mov     [rsp+80h+var_58], rsi
0x180044732  mov     rax, [rcx]
0x180044735  mov     [rsp+80h+var_60], rdx
0x18004473a  lea     rdx, CLSID_MFSourceReader
0x180044741  mov     rax, [rax+20h]
0x180044745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004474a  mov     ebx, eax
0x18004474c  lea     rcx, [rbp+var_40]
0x180044750  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180044755  lea     rcx, [rbp+var_38]
0x180044759  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004475e  lea     rcx, [rbp+ppv]
0x180044762  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180044767  lea     rcx, [rbp+ppMFAttributes]
0x18004476b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044770  lea     rcx, [rbp+ppISourceResolver]
0x180044774  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044779  lea     rcx, [rbp+ppByteStream]
0x18004477d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044782  mov     eax, ebx
0x180044784  mov     rbx, [rsp+80h+arg_0]
0x18004478c  add     rsp, 80h
0x180044793  pop     rdi
0x180044794  pop     rsi
0x180044795  pop     rbp
0x180044796  retn
```
