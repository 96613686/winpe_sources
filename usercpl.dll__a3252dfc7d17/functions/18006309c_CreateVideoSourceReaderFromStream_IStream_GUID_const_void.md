# CreateVideoSourceReaderFromStream(IStream *,_GUID const &,void * *)

- ea: `0x18006309c`
- end: `0x180063357`
- name: `?CreateVideoSourceReaderFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `699`
- prototype: `__int64 __fastcall(struct IStream *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062cd0`

## callees

- `0x18006309c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006326e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006326e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800631b8`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800631b8`
- `MFPlat!MFCreateSourceResolver` at `0x1800630db`
- `MFPlat!MFCreateSourceResolver` at `0x1800630db`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x1800630c3`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x1800630c3`
- `MFPlat!MFCreateAttributes` at `0x1800630f6`
- `MFPlat!MFCreateAttributes` at `0x1800630f6`

## pseudocode

```c
__int64 __fastcall CreateVideoSourceReaderFromStream(struct IStream *a1, const struct _GUID *a2, void **a3)
{
  HRESULT v4; // ebx
  LPVOID v5; // rcx
  __int64 v6; // rcx
  void *v7; // rcx
  IMFAttributes *v8; // rcx
  IMFSourceResolver *v9; // rcx
  IMFByteStream *v10; // rcx
  LPVOID v12; // [rsp+40h] [rbp-40h] BYREF
  __int64 v13; // [rsp+48h] [rbp-38h] BYREF
  IMFSourceResolver *ppISourceResolver; // [rsp+50h] [rbp-30h] BYREF
  IMFByteStream *ppByteStream; // [rsp+58h] [rbp-28h] BYREF
  __int128 v16; // [rsp+60h] [rbp-20h] BYREF
  __int64 v17; // [rsp+70h] [rbp-10h]
  const struct _GUID *v18; // [rsp+A8h] [rbp+28h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+B0h] [rbp+30h] BYREF
  void *ppv; // [rsp+B8h] [rbp+38h] BYREF

  v18 = a2;
  *a3 = 0;
  ppByteStream = 0;
  v4 = MFCreateMFByteStreamOnStream(a1, &ppByteStream);
  if ( v4 >= 0 )
  {
    ppISourceResolver = 0;
    v4 = MFCreateSourceResolver(&ppISourceResolver);
    if ( v4 >= 0 )
    {
      ppMFAttributes = 0;
      v4 = MFCreateAttributes(&ppMFAttributes, 8u);
      if ( v4 >= 0 )
      {
        v4 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               &MF_SOURCE_READER_ENABLE_VIDEO_PROCESSING,
               1);
        if ( v4 >= 0 )
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
          v4 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
          if ( v4 >= 0 )
          {
            v17 = 0;
            v16 = 0;
            LOWORD(v16) = 11;
            WORD4(v16) = -1;
            v4 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
                   ppv,
                   &MFPKEY_MediaSource_DisableReadAhead,
                   &v16);
            if ( v4 >= 0 )
            {
              LODWORD(v18) = 0;
              v13 = 0;
              v4 = ((__int64 (__fastcall *)(IMFSourceResolver *, IMFByteStream *, _QWORD, __int64, void *, const struct _GUID **, __int64 *))ppISourceResolver->lpVtbl->CreateObjectFromByteStream)(
                     ppISourceResolver,
                     ppByteStream,
                     0,
                     65553,
                     ppv,
                     &v18,
                     &v13);
              if ( v4 >= 0 )
              {
                v12 = 0;
                v4 = CoCreateInstance(
                       &CLSID_MFReadWriteClassFactory,
                       0,
                       1u,
                       &GUID_e7fe2e12_661c_40da_92f9_4f002ab67627,
                       &v12);
                if ( v4 >= 0 )
                  v4 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, IMFAttributes *, GUID *, void **))(*(_QWORD *)v12 + 32LL))(
                         v12,
                         &CLSID_MFSourceReader,
                         v13,
                         ppMFAttributes,
                         &GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993,
                         a3);
                v5 = v12;
                if ( v12 )
                {
                  v12 = 0;
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
                }
              }
              v6 = v13;
              if ( v13 )
              {
                v13 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
              }
            }
          }
          v7 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
          }
        }
      }
      v8 = ppMFAttributes;
      if ( ppMFAttributes )
      {
        ppMFAttributes = 0;
        ((void (__fastcall *)(IMFAttributes *))v8->lpVtbl->Release)(v8);
      }
    }
    v9 = ppISourceResolver;
    if ( ppISourceResolver )
    {
      ppISourceResolver = 0;
      ((void (__fastcall *)(IMFSourceResolver *))v9->lpVtbl->Release)(v9);
    }
  }
  v10 = ppByteStream;
  if ( ppByteStream )
  {
    ppByteStream = 0;
    ((void (__fastcall *)(IMFByteStream *))v10->lpVtbl->Release)(v10);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006309c  mov     [rsp-18h+arg_0], rbx
0x1800630a1  mov     [rsp-18h+arg_8], rdx
0x1800630a6  push    rbp
0x1800630a7  push    rsi
0x1800630a8  push    rdi
0x1800630a9  mov     rbp, rsp
0x1800630ac  sub     rsp, 80h
0x1800630b3  xor     esi, esi
0x1800630b5  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x1800630b9  mov     [r8], rsi
0x1800630bc  mov     rdi, r8
0x1800630bf  mov     [rbp+ppByteStream], rsi
0x1800630c3  call    cs:__imp_MFCreateMFByteStreamOnStream
0x1800630c9  mov     ebx, eax
0x1800630cb  test    eax, eax
0x1800630cd  js      loc_180063329
0x1800630d3  lea     rcx, [rbp+ppISourceResolver]; ppISourceResolver
0x1800630d7  mov     [rbp+ppISourceResolver], rsi
0x1800630db  call    cs:__imp_MFCreateSourceResolver
0x1800630e1  mov     ebx, eax
0x1800630e3  test    eax, eax
0x1800630e5  js      loc_180063310
0x1800630eb  lea     edx, [rsi+8]; cInitialSize
0x1800630ee  mov     [rbp+ppMFAttributes], rsi
0x1800630f2  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800630f6  call    cs:__imp_MFCreateAttributes
0x1800630fc  mov     ebx, eax
0x1800630fe  test    eax, eax
0x180063100  js      loc_1800632F7
0x180063106  mov     rcx, [rbp+ppMFAttributes]
0x18006310a  lea     r8d, [rsi+1]
0x18006310e  lea     rdx, MF_SOURCE_READER_ENABLE_VIDEO_PROCESSING
0x180063115  mov     rax, [rcx]
0x180063118  mov     rax, [rax+0A8h]
0x18006311f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063124  mov     ebx, eax
0x180063126  test    eax, eax
0x180063128  js      loc_1800632F7
0x18006312e  mov     rcx, [rbp+ppMFAttributes]
0x180063132  lea     r8d, [rsi+1]
0x180063136  lea     rdx, _GUID_9561c3e8_ea9e_4435_9b1e_a93e691894d8
0x18006313d  mov     rax, [rcx]
0x180063140  mov     rax, [rax+0A8h]
0x180063147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006314c  mov     rcx, [rbp+ppMFAttributes]
0x180063150  lea     rdx, _GUID_5ae557b8_77af_41f5_9fa6_4db2fe1d4bca
0x180063157  mov     ebx, 100h
0x18006315c  mov     r8d, ebx
0x18006315f  mov     rax, [rcx]
0x180063162  mov     rax, [rax+0A8h]
0x180063169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006316e  mov     rcx, [rbp+ppMFAttributes]
0x180063172  lea     rdx, _GUID_7262a16a_d2dc_4e75_9ba8_65c0c6d32b13
0x180063179  mov     r8d, ebx
0x18006317c  mov     rax, [rcx]
0x18006317f  mov     rax, [rax+0A8h]
0x180063186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006318b  mov     rcx, [rbp+ppMFAttributes]
0x18006318f  lea     r8d, [rsi+1]
0x180063193  lea     rdx, MF_LOW_LATENCY
0x18006319a  mov     rax, [rcx]
0x18006319d  mov     rax, [rax+0A8h]
0x1800631a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631a9  lea     rdx, [rbp+ppv]; ppv
0x1800631ad  mov     [rbp+ppv], rsi
0x1800631b1  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800631b8  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800631be  mov     ebx, eax
0x1800631c0  test    eax, eax
0x1800631c2  js      loc_1800632DE
0x1800631c8  mov     rcx, [rbp+ppv]
0x1800631cc  lea     r8, [rbp+var_20]
0x1800631d0  xor     eax, eax
0x1800631d2  lea     rdx, MFPKEY_MediaSource_DisableReadAhead
0x1800631d9  mov     [rbp+var_10], rax
0x1800631dd  xorps   xmm0, xmm0
0x1800631e0  lea     eax, [rsi+0Bh]
0x1800631e3  movups  [rbp+var_20], xmm0
0x1800631e7  mov     word ptr [rbp+var_20], ax
0x1800631eb  or      eax, 0FFFFFFFFh
0x1800631ee  mov     word ptr [rbp+var_20+8], ax
0x1800631f2  mov     rax, [rcx]
0x1800631f5  mov     rax, [rax+30h]
0x1800631f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631fe  mov     ebx, eax
0x180063200  test    eax, eax
0x180063202  js      loc_1800632DE
0x180063208  mov     r8, [rbp+ppv]
0x18006320c  lea     rdx, [rbp+var_38]
0x180063210  mov     rcx, [rbp+ppISourceResolver]
0x180063214  mov     r9d, 10011h
0x18006321a  mov     [rsp+80h+var_50], rdx
0x18006321f  lea     rdx, [rbp+arg_8]
0x180063223  mov     [rsp+80h+var_58], rdx
0x180063228  mov     rdx, [rbp+ppByteStream]
0x18006322c  mov     dword ptr [rbp+arg_8], esi
0x18006322f  mov     [rbp+var_38], rsi
0x180063233  mov     rax, [rcx]
0x180063236  mov     [rsp+80h+var_60], r8
0x18006323b  xor     r8d, r8d
0x18006323e  mov     rax, [rax+20h]
0x180063242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063247  mov     ebx, eax
0x180063249  test    eax, eax
0x18006324b  js      short loc_1800632C5
0x18006324d  lea     rax, [rbp+var_40]
0x180063251  mov     [rbp+var_40], rsi
0x180063255  lea     r9, _GUID_e7fe2e12_661c_40da_92f9_4f002ab67627; riid
0x18006325c  mov     [rsp+80h+var_60], rax; ppv
0x180063261  xor     edx, edx; pUnkOuter
0x180063263  lea     r8d, [rsi+1]; dwClsContext
0x180063267  lea     rcx, CLSID_MFReadWriteClassFactory; rclsid
0x18006326e  call    cs:__imp_CoCreateInstance
0x180063274  mov     ebx, eax
0x180063276  test    eax, eax
0x180063278  js      short loc_1800632AC
0x18006327a  mov     rcx, [rbp+var_40]
0x18006327e  lea     rdx, _GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993
0x180063285  mov     r9, [rbp+ppMFAttributes]
0x180063289  mov     r8, [rbp+var_38]
0x18006328d  mov     [rsp+80h+var_58], rdi
0x180063292  mov     rax, [rcx]
0x180063295  mov     [rsp+80h+var_60], rdx
0x18006329a  lea     rdx, CLSID_MFSourceReader
0x1800632a1  mov     rax, [rax+20h]
0x1800632a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632aa  mov     ebx, eax
0x1800632ac  mov     rcx, [rbp+var_40]
0x1800632b0  test    rcx, rcx
0x1800632b3  jz      short loc_1800632C5
0x1800632b5  mov     [rbp+var_40], rsi
0x1800632b9  mov     rax, [rcx]
0x1800632bc  mov     rax, [rax+10h]
0x1800632c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632c5  mov     rcx, [rbp+var_38]
0x1800632c9  test    rcx, rcx
0x1800632cc  jz      short loc_1800632DE
0x1800632ce  mov     [rbp+var_38], rsi
0x1800632d2  mov     rax, [rcx]
0x1800632d5  mov     rax, [rax+10h]
0x1800632d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632de  mov     rcx, [rbp+ppv]
0x1800632e2  test    rcx, rcx
0x1800632e5  jz      short loc_1800632F7
0x1800632e7  mov     [rbp+ppv], rsi
0x1800632eb  mov     rax, [rcx]
0x1800632ee  mov     rax, [rax+10h]
0x1800632f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632f7  mov     rcx, [rbp+ppMFAttributes]
0x1800632fb  test    rcx, rcx
0x1800632fe  jz      short loc_180063310
0x180063300  mov     [rbp+ppMFAttributes], rsi
0x180063304  mov     rax, [rcx]
0x180063307  mov     rax, [rax+10h]
0x18006330b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063310  mov     rcx, [rbp+ppISourceResolver]
0x180063314  test    rcx, rcx
0x180063317  jz      short loc_180063329
0x180063319  mov     [rbp+ppISourceResolver], rsi
0x18006331d  mov     rax, [rcx]
0x180063320  mov     rax, [rax+10h]
0x180063324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063329  mov     rcx, [rbp+ppByteStream]
0x18006332d  test    rcx, rcx
0x180063330  jz      short loc_180063342
0x180063332  mov     [rbp+ppByteStream], rsi
0x180063336  mov     rax, [rcx]
0x180063339  mov     rax, [rax+10h]
0x18006333d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063342  mov     eax, ebx
0x180063344  mov     rbx, [rsp+80h+arg_0]
0x18006334c  add     rsp, 80h
0x180063353  pop     rdi
0x180063354  pop     rsi
0x180063355  pop     rbp
0x180063356  retn
```
