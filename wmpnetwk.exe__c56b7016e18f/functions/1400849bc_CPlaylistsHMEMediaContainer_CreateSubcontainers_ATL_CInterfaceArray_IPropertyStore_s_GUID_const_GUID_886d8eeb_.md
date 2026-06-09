# CPlaylistsHMEMediaContainer::CreateSubcontainers(ATL::CInterfaceArray<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99> const &,ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)

- ea: `0x1400849bc`
- end: `0x140084c25`
- name: `?CreateSubcontainers@CPlaylistsHMEMediaContainer@@IEAAJAEBV?$CInterfaceArray@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@AEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@3@@Z`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140085fc0`

## callees

- `0x140006d70`
- `0x14000c920`
- `0x140024688`
- `0x14002c410`
- `0x140041b14`
- `0x140045f20`
- `0x14008328c`
- `0x1400849bc`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x140084bda`
- `ole32!PropVariantClear` at `0x140084be5`
- `ole32!PropVariantClear` at `0x140084bda`
- `ole32!PropVariantClear` at `0x140084be5`
- `SHLWAPI!PathCreateFromUrlW` at `0x140084ad5`
- `SHLWAPI!PathCreateFromUrlW` at `0x140084ad5`
- `SHLWAPI!PathRemoveExtensionW` at `0x140084aea`
- `SHLWAPI!PathRemoveExtensionW` at `0x140084aea`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPlaylistsHMEMediaContainer::CreateSubcontainers(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  HRESULT PlaylistContainer; // ebx
  unsigned __int64 i; // r15
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  unsigned __int64 v9; // rax
  _QWORD *v10; // rbx
  __int64 v11; // r14
  __int64 v12; // rsi
  int v13; // edi
  char *v14; // rax
  DWORD pcchPath; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v18; // [rsp+50h] [rbp-B0h]
  void *v19; // [rsp+58h] [rbp-A8h] BYREF
  void *v20; // [rsp+60h] [rbp-A0h] BYREF
  void *v21; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR v22[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h]
  PCWSTR pszUrl[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+98h] [rbp-68h]
  WCHAR pszPath[264]; // [rsp+A0h] [rbp-60h] BYREF

  v18 = a1;
  PlaylistContainer = 0;
  for ( i = 0; i < a2[1]; ++i )
  {
    if ( PlaylistContainer < 0 )
      break;
    *(_OWORD *)v22 = 0;
    v23 = 0;
    v7 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](
                     a2,
                     i);
    PlaylistContainer = (*(__int64 (__fastcall **)(_QWORD, const PROPERTYKEY *, LPWSTR *))(*(_QWORD *)*v7 + 40LL))(
                          *v7,
                          &PKEY_ItemNameDisplay,
                          v22);
    if ( PlaylistContainer >= 0 && LOWORD(v22[0]) == 31 )
    {
      *(_OWORD *)pszUrl = 0;
      v25 = 0;
      v8 = (_QWORD *)ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](
                       a2,
                       i);
      PlaylistContainer = (*(__int64 (__fastcall **)(_QWORD, const PROPERTYKEY *, PCWSTR *))(*(_QWORD *)*v8 + 40LL))(
                            *v8,
                            &PKEY_ItemUrl,
                            pszUrl);
      if ( PlaylistContainer >= 0 && LOWORD(pszUrl[0]) == 31 )
      {
        v9 = -1;
        do
          ++v9;
        while ( pszUrl[1][v9] );
        if ( v9 > 5 )
        {
          v17 = 0;
          pcchPath = 260;
          PlaylistContainer = PathCreateFromUrlW(pszUrl[1], pszPath, &pcchPath, 0);
          if ( PlaylistContainer >= 0 )
          {
            PathRemoveExtensionW(v22[1]);
            v10 = v18;
            v11 = v18[4];
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v21,
              (char *)pszPath);
            v12 = (*(__int64 (__fastcall **)(_QWORD *))(*v10 + 96LL))(v10);
            v13 = *(_DWORD *)(v10[2] + 32LL);
            LODWORD(v10) = (*(__int64 (__fastcall **)(_QWORD *))(*v10 + 80LL))(v10);
            v14 = (char *)(*(__int64 (__fastcall **)(_QWORD *))(*v18 + 56LL))(v18);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v20,
              v14);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v19,
              (char *)v22[1]);
            PlaylistContainer = CGeneratedContainerFactory::CreatePlaylistContainer(
                                  v11,
                                  (unsigned int)&v19,
                                  (unsigned int)&v20,
                                  (_DWORD)v10,
                                  v13,
                                  v12,
                                  (__int64)&v21,
                                  (__int64)&v17);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v19);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v20);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v21);
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
    PropVariantClear((PROPVARIANT *)v22);
  }
  return (unsigned int)PlaylistContainer;
}

```

## disassembly

```asm
0x1400849bc  mov     [rsp-8+arg_18], rbx
0x1400849c1  push    rbp
0x1400849c2  push    rsi
0x1400849c3  push    rdi
0x1400849c4  push    r12
0x1400849c6  push    r13
0x1400849c8  push    r14
0x1400849ca  push    r15
0x1400849cc  lea     rbp, [rsp-1C0h]
0x1400849d4  sub     rsp, 2C0h
0x1400849db  mov     rax, cs:__security_cookie
0x1400849e2  xor     rax, rsp
0x1400849e5  mov     [rbp+1F0h+var_40], rax
0x1400849ec  mov     r13, r8
0x1400849ef  mov     r12, rdx
0x1400849f2  mov     [rsp+2F0h+var_2A0], rcx
0x1400849f7  xor     edi, edi
0x1400849f9  mov     ebx, edi
0x1400849fb  mov     r15d, edi
0x1400849fe  cmp     [rdx+8], rdi
0x140084a02  jbe     loc_140084BF9
0x140084a08  test    ebx, ebx
0x140084a0a  js      loc_140084BF9
0x140084a10  xorps   xmm0, xmm0
0x140084a13  xor     eax, eax
0x140084a15  movups  xmmword ptr [rsp+2F0h+var_280], xmm0
0x140084a1a  mov     [rbp+1F0h+var_270], rax
0x140084a1e  mov     rdx, r15
0x140084a21  mov     rcx, r12
0x140084a24  call    ??A?$CAtlArray@V?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@2@@ATL@@QEBAAEBV?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](unsigned __int64)
0x140084a29  mov     rcx, [rax]
0x140084a2c  mov     rax, [rcx]
0x140084a2f  lea     r8, [rsp+2F0h+var_280]
0x140084a34  lea     rdx, PKEY_ItemNameDisplay
0x140084a3b  mov     rax, [rax+28h]
0x140084a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084a44  mov     ebx, eax
0x140084a46  test    eax, eax
0x140084a48  js      loc_140084BE0
0x140084a4e  cmp     word ptr [rsp+2F0h+var_280], 1Fh
0x140084a54  jnz     loc_140084BE0
0x140084a5a  xorps   xmm0, xmm0
0x140084a5d  xor     eax, eax
0x140084a5f  movups  xmmword ptr [rbp+1F0h+pszUrl], xmm0
0x140084a63  mov     [rbp+1F0h+var_258], rax
0x140084a67  mov     rdx, r15
0x140084a6a  mov     rcx, r12
0x140084a6d  call    ??A?$CAtlArray@V?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@2@@ATL@@QEBAAEBV?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::operator[](unsigned __int64)
0x140084a72  mov     rcx, [rax]
0x140084a75  mov     rax, [rcx]
0x140084a78  lea     r8, [rbp+1F0h+pszUrl]
0x140084a7c  lea     rdx, PKEY_ItemUrl
0x140084a83  mov     rax, [rax+28h]
0x140084a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084a8c  mov     ebx, eax
0x140084a8e  test    eax, eax
0x140084a90  js      loc_140084BD6
0x140084a96  cmp     word ptr [rbp+1F0h+pszUrl], 1Fh
0x140084a9b  jnz     loc_140084BD6
0x140084aa1  mov     rcx, [rbp+1F0h+pszUrl+8]; pszUrl
0x140084aa5  or      rax, 0FFFFFFFFFFFFFFFFh
0x140084aa9  inc     rax
0x140084aac  cmp     [rcx+rax*2], di
0x140084ab0  jnz     short loc_140084AA9
0x140084ab2  cmp     rax, 5
0x140084ab6  jbe     loc_140084BD6
0x140084abc  mov     [rsp+2F0h+var_2A8], rdi
0x140084ac1  mov     [rsp+2F0h+pcchPath], 104h
0x140084ac9  xor     r9d, r9d; dwFlags
0x140084acc  lea     r8, [rsp+2F0h+pcchPath]; pcchPath
0x140084ad1  lea     rdx, [rbp+1F0h+pszPath]; pszPath
0x140084ad5  call    cs:__imp_PathCreateFromUrlW
0x140084adb  mov     ebx, eax
0x140084add  test    eax, eax
0x140084adf  js      loc_140084BCC
0x140084ae5  mov     rcx, [rsp+2F0h+var_280+8]; pszPath
0x140084aea  call    cs:__imp_PathRemoveExtensionW
0x140084af0  mov     rbx, [rsp+2F0h+var_2A0]
0x140084af5  mov     r14, [rbx+20h]
0x140084af9  lea     rdx, [rbp+1F0h+pszPath]
0x140084afd  lea     rcx, [rsp+2F0h+var_288]
0x140084b02  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140084b07  nop
0x140084b08  mov     rax, [rbx]
0x140084b0b  mov     rcx, rbx
0x140084b0e  mov     rax, [rax+60h]
0x140084b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084b17  mov     rsi, rax
0x140084b1a  mov     rcx, [rbx+10h]
0x140084b1e  mov     edi, [rcx+20h]
0x140084b21  mov     rcx, [rbx]
0x140084b24  mov     rax, [rcx+50h]
0x140084b28  mov     rcx, rbx
0x140084b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084b30  mov     ebx, eax
0x140084b32  mov     rdx, [rsp+2F0h+var_2A0]
0x140084b37  mov     rcx, [rdx]
0x140084b3a  mov     rax, [rcx+38h]
0x140084b3e  mov     rcx, rdx
0x140084b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084b46  mov     rdx, rax
0x140084b49  lea     rcx, [rsp+2F0h+var_290]
0x140084b4e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140084b53  nop
0x140084b54  mov     rdx, [rsp+2F0h+var_280+8]
0x140084b59  lea     rcx, [rsp+2F0h+var_298]
0x140084b5e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140084b63  nop
0x140084b64  lea     rax, [rsp+2F0h+var_2A8]
0x140084b69  mov     [rsp+2F0h+var_2B8], rax
0x140084b6e  lea     rax, [rsp+2F0h+var_288]
0x140084b73  mov     [rsp+2F0h+var_2C0], rax
0x140084b78  mov     [rsp+2F0h+var_2C8], rsi
0x140084b7d  mov     [rsp+2F0h+var_2D0], edi
0x140084b81  mov     r9d, ebx
0x140084b84  lea     r8, [rsp+2F0h+var_290]
0x140084b89  lea     rdx, [rsp+2F0h+var_298]
0x140084b8e  mov     rcx, r14
0x140084b91  call    ?CreatePlaylistContainer@CGeneratedContainerFactory@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0W4MediaCacheSchema@@W4WMPContentProviderObjectClasses@@PEBVCShellCommandFactory@@0PEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::CreatePlaylistContainer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,WMPContentProviderObjectClasses,CShellCommandFactory const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,IHMEMediaContainer * *)
0x140084b96  mov     ebx, eax
0x140084b98  lea     rcx, [rsp+2F0h+var_298]
0x140084b9d  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084ba2  nop
0x140084ba3  lea     rcx, [rsp+2F0h+var_290]
0x140084ba8  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084bad  nop
0x140084bae  lea     rcx, [rsp+2F0h+var_288]
0x140084bb3  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140084bb8  xor     edi, edi
0x140084bba  test    ebx, ebx
0x140084bbc  js      short loc_140084BCC
0x140084bbe  mov     rdx, [rsp+2F0h+var_2A8]
0x140084bc3  mov     rcx, r13
0x140084bc6  call    ?Add@?$CAtlArray@V?$CComQIPtr@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@2@@ATL@@QEAA_KPEAUIHMEMediaContainer@@@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(IHMEMediaContainer *)
0x140084bcb  nop
0x140084bcc  lea     rcx, [rsp+2F0h+var_2A8]
0x140084bd1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140084bd6  lea     rcx, [rbp+1F0h+pszUrl]; pvar
0x140084bda  call    cs:__imp_PropVariantClear
0x140084be0  lea     rcx, [rsp+2F0h+var_280]; pvar
0x140084be5  call    cs:__imp_PropVariantClear
0x140084beb  inc     r15
0x140084bee  cmp     r15, [r12+8]
0x140084bf3  jb      loc_140084A08
0x140084bf9  mov     eax, ebx
0x140084bfb  mov     rcx, [rbp+1F0h+var_40]
0x140084c02  xor     rcx, rsp; StackCookie
0x140084c05  call    __security_check_cookie
0x140084c0a  mov     rbx, [rsp+2F0h+arg_18]
0x140084c12  add     rsp, 2C0h
0x140084c19  pop     r15
0x140084c1b  pop     r14
0x140084c1d  pop     r13
0x140084c1f  pop     r12
0x140084c21  pop     rdi
0x140084c22  pop     rsi
0x140084c23  pop     rbp
0x140084c24  retn
```
