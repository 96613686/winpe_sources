# CGeneratedFolderContainer::CreatePlaylistSubcontainers(ATL::CInterfaceArray<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99> const &,ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)

- ea: `0x140083b9c`
- end: `0x140083df9`
- name: `?CreatePlaylistSubcontainers@CGeneratedFolderContainer@@IEAAJAEBV?$CInterfaceArray@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@AEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@3@@Z`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400855d0`

## callees

- `0x140006d70`
- `0x14000c920`
- `0x140024688`
- `0x14002c410`
- `0x140041b14`
- `0x140045f20`
- `0x14008328c`
- `0x140083b9c`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x140083daf`
- `ole32!PropVariantClear` at `0x140083dba`
- `ole32!PropVariantClear` at `0x140083daf`
- `ole32!PropVariantClear` at `0x140083dba`
- `SHLWAPI!PathCreateFromUrlW` at `0x140083cb4`
- `SHLWAPI!PathCreateFromUrlW` at `0x140083cb4`
- `SHLWAPI!PathRemoveExtensionW` at `0x140083cc9`
- `SHLWAPI!PathRemoveExtensionW` at `0x140083cc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CGeneratedFolderContainer::CreatePlaylistSubcontainers(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  HRESULT PlaylistContainer; // ebx
  unsigned __int64 i; // r14
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  unsigned __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rdi
  int v13; // ebx
  char *v14; // rax
  DWORD pcchPath; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  void *v18; // [rsp+50h] [rbp-B0h] BYREF
  void *v19; // [rsp+58h] [rbp-A8h] BYREF
  void *v20; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR v21[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h]
  PCWSTR pszUrl[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h]
  WCHAR pszPath[264]; // [rsp+A0h] [rbp-60h] BYREF

  PlaylistContainer = 0;
  for ( i = 0; i < a2[1]; ++i )
  {
    if ( PlaylistContainer < 0 )
      break;
    *(_OWORD *)v21 = 0;
    v22 = 0;
    v8 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](
                     a2,
                     i);
    PlaylistContainer = (*(__int64 (__fastcall **)(_QWORD, const PROPERTYKEY *, LPWSTR *))(*(_QWORD *)*v8 + 40LL))(
                          *v8,
                          &PKEY_ItemNameDisplay,
                          v21);
    if ( PlaylistContainer >= 0 && LOWORD(v21[0]) == 31 )
    {
      *(_OWORD *)pszUrl = 0;
      v24 = 0;
      v9 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](
                       a2,
                       i);
      PlaylistContainer = (*(__int64 (__fastcall **)(_QWORD, const PROPERTYKEY *, PCWSTR *))(*(_QWORD *)*v9 + 40LL))(
                            *v9,
                            &PKEY_ItemUrl,
                            pszUrl);
      if ( PlaylistContainer >= 0 && LOWORD(pszUrl[0]) == 31 )
      {
        v10 = -1;
        do
          ++v10;
        while ( pszUrl[1][v10] );
        if ( v10 > 5 )
        {
          v17 = 0;
          pcchPath = 260;
          PlaylistContainer = PathCreateFromUrlW(pszUrl[1], pszPath, &pcchPath, 0);
          if ( PlaylistContainer >= 0 )
          {
            PathRemoveExtensionW(v21[1]);
            v11 = a1[7];
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v20,
              (char *)pszPath);
            v12 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1);
            v13 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
            v14 = (char *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v19,
              v14);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v18,
              (char *)v21[1]);
            PlaylistContainer = CGeneratedContainerFactory::CreatePlaylistContainer(
                                  v11,
                                  (unsigned int)&v18,
                                  (unsigned int)&v19,
                                  v13,
                                  19,
                                  v12,
                                  (__int64)&v20,
                                  (__int64)&v17);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v18);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v19);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v20);
            if ( PlaylistContainer >= 0 )
              ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(
                a3,
                v17);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
        }
      }
      PropVariantClear((PROPVARIANT *)pszUrl);
    }
    PropVariantClear((PROPVARIANT *)v21);
  }
  return (unsigned int)PlaylistContainer;
}

```

## disassembly

```asm
0x140083b9c  mov     [rsp-8+arg_18], rbx
0x140083ba1  push    rbp
0x140083ba2  push    rsi
0x140083ba3  push    rdi
0x140083ba4  push    r12
0x140083ba6  push    r13
0x140083ba8  push    r14
0x140083baa  push    r15
0x140083bac  lea     rbp, [rsp-1C0h]
0x140083bb4  sub     rsp, 2C0h
0x140083bbb  mov     rax, cs:__security_cookie
0x140083bc2  xor     rax, rsp
0x140083bc5  mov     [rbp+1F0h+var_40], rax
0x140083bcc  mov     r12, r8
0x140083bcf  mov     r15, rdx
0x140083bd2  mov     r13, rcx
0x140083bd5  xor     edi, edi
0x140083bd7  mov     ebx, edi
0x140083bd9  mov     r14d, edi
0x140083bdc  cmp     [rdx+8], rdi
0x140083be0  jbe     loc_140083DCD
0x140083be6  test    ebx, ebx
0x140083be8  js      loc_140083DCD
0x140083bee  xorps   xmm0, xmm0
0x140083bf1  xor     eax, eax
0x140083bf3  movups  xmmword ptr [rsp+2F0h+var_288], xmm0
0x140083bf8  mov     [rsp+2F0h+var_278], rax
0x140083bfd  mov     rdx, r14
0x140083c00  mov     rcx, r15
0x140083c03  call    ??A?$CAtlArray@V?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@2@@ATL@@QEBAAEBV?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](unsigned __int64)
0x140083c08  mov     rcx, [rax]
0x140083c0b  mov     rax, [rcx]
0x140083c0e  lea     r8, [rsp+2F0h+var_288]
0x140083c13  lea     rdx, PKEY_ItemNameDisplay
0x140083c1a  mov     rax, [rax+28h]
0x140083c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083c23  mov     ebx, eax
0x140083c25  test    eax, eax
0x140083c27  js      loc_140083DB5
0x140083c2d  cmp     word ptr [rsp+2F0h+var_288], 1Fh
0x140083c33  jnz     loc_140083DB5
0x140083c39  xorps   xmm0, xmm0
0x140083c3c  xor     eax, eax
0x140083c3e  movups  xmmword ptr [rbp+1F0h+pszUrl], xmm0
0x140083c42  mov     [rbp+1F0h+var_260], rax
0x140083c46  mov     rdx, r14
0x140083c49  mov     rcx, r15
0x140083c4c  call    ??A?$CAtlArray@V?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@2@@ATL@@QEBAAEBV?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](unsigned __int64)
0x140083c51  mov     rcx, [rax]
0x140083c54  mov     rax, [rcx]
0x140083c57  lea     r8, [rbp+1F0h+pszUrl]
0x140083c5b  lea     rdx, PKEY_ItemUrl
0x140083c62  mov     rax, [rax+28h]
0x140083c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083c6b  mov     ebx, eax
0x140083c6d  test    eax, eax
0x140083c6f  js      loc_140083DAB
0x140083c75  cmp     word ptr [rbp+1F0h+pszUrl], 1Fh
0x140083c7a  jnz     loc_140083DAB
0x140083c80  mov     rcx, [rbp+1F0h+pszUrl+8]; pszUrl
0x140083c84  or      rax, 0FFFFFFFFFFFFFFFFh
0x140083c88  inc     rax
0x140083c8b  cmp     [rcx+rax*2], di
0x140083c8f  jnz     short loc_140083C88
0x140083c91  cmp     rax, 5
0x140083c95  jbe     loc_140083DAB
0x140083c9b  mov     [rsp+2F0h+var_2A8], rdi
0x140083ca0  mov     [rsp+2F0h+pcchPath], 104h
0x140083ca8  xor     r9d, r9d; dwFlags
0x140083cab  lea     r8, [rsp+2F0h+pcchPath]; pcchPath
0x140083cb0  lea     rdx, [rbp+1F0h+pszPath]; pszPath
0x140083cb4  call    cs:__imp_PathCreateFromUrlW
0x140083cba  mov     ebx, eax
0x140083cbc  test    eax, eax
0x140083cbe  js      loc_140083DA1
0x140083cc4  mov     rcx, [rsp+2F0h+var_288+8]; pszPath
0x140083cc9  call    cs:__imp_PathRemoveExtensionW
0x140083ccf  mov     rsi, [r13+38h]
0x140083cd3  lea     rdx, [rbp+1F0h+pszPath]
0x140083cd7  lea     rcx, [rsp+2F0h+var_290]
0x140083cdc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140083ce1  nop
0x140083ce2  mov     rax, [r13+0]
0x140083ce6  mov     rcx, r13
0x140083ce9  mov     rax, [rax+60h]
0x140083ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083cf2  mov     rdi, rax
0x140083cf5  mov     rcx, [r13+0]
0x140083cf9  mov     rax, [rcx+50h]
0x140083cfd  mov     rcx, r13
0x140083d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083d05  mov     ebx, eax
0x140083d07  mov     rcx, [r13+0]
0x140083d0b  mov     rax, [rcx+38h]
0x140083d0f  mov     rcx, r13
0x140083d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083d17  mov     rdx, rax
0x140083d1a  lea     rcx, [rsp+2F0h+var_298]
0x140083d1f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140083d24  nop
0x140083d25  mov     rdx, [rsp+2F0h+var_288+8]
0x140083d2a  lea     rcx, [rsp+2F0h+var_2A0]
0x140083d2f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140083d34  nop
0x140083d35  lea     rax, [rsp+2F0h+var_2A8]
0x140083d3a  mov     [rsp+2F0h+var_2B8], rax
0x140083d3f  lea     rax, [rsp+2F0h+var_290]
0x140083d44  mov     [rsp+2F0h+var_2C0], rax
0x140083d49  mov     [rsp+2F0h+var_2C8], rdi
0x140083d4e  mov     [rsp+2F0h+var_2D0], 13h
0x140083d56  mov     r9d, ebx
0x140083d59  lea     r8, [rsp+2F0h+var_298]
0x140083d5e  lea     rdx, [rsp+2F0h+var_2A0]
0x140083d63  mov     rcx, rsi
0x140083d66  call    ?CreatePlaylistContainer@CGeneratedContainerFactory@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0W4MediaCacheSchema@@W4WMPContentProviderObjectClasses@@PEBVCShellCommandFactory@@0PEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::CreatePlaylistContainer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,WMPContentProviderObjectClasses,CShellCommandFactory const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,IHMEMediaContainer * *)
0x140083d6b  mov     ebx, eax
0x140083d6d  lea     rcx, [rsp+2F0h+var_2A0]
0x140083d72  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140083d77  nop
0x140083d78  lea     rcx, [rsp+2F0h+var_298]
0x140083d7d  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140083d82  nop
0x140083d83  lea     rcx, [rsp+2F0h+var_290]
0x140083d88  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140083d8d  xor     edi, edi
0x140083d8f  test    ebx, ebx
0x140083d91  js      short loc_140083DA1
0x140083d93  mov     rdx, [rsp+2F0h+var_2A8]
0x140083d98  mov     rcx, r12
0x140083d9b  call    ?Add@?$CAtlArray@V?$CComQIPtr@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@2@@ATL@@QEAA_KPEAUIHMEMediaContainer@@@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(IHMEMediaContainer *)
0x140083da0  nop
0x140083da1  lea     rcx, [rsp+2F0h+var_2A8]
0x140083da6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140083dab  lea     rcx, [rbp+1F0h+pszUrl]; pvar
0x140083daf  call    cs:__imp_PropVariantClear
0x140083db5  lea     rcx, [rsp+2F0h+var_288]; pvar
0x140083dba  call    cs:__imp_PropVariantClear
0x140083dc0  inc     r14
0x140083dc3  cmp     r14, [r15+8]
0x140083dc7  jb      loc_140083BE6
0x140083dcd  mov     eax, ebx
0x140083dcf  mov     rcx, [rbp+1F0h+var_40]
0x140083dd6  xor     rcx, rsp; StackCookie
0x140083dd9  call    __security_check_cookie
0x140083dde  mov     rbx, [rsp+2F0h+arg_18]
0x140083de6  add     rsp, 2C0h
0x140083ded  pop     r15
0x140083def  pop     r14
0x140083df1  pop     r13
0x140083df3  pop     r12
0x140083df5  pop     rdi
0x140083df6  pop     rsi
0x140083df7  pop     rbp
0x140083df8  retn
```
