# CFolderHMEMediaContainer::GenerateSubcontainers(ushort const *,ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)

- ea: `0x140086c1c`
- end: `0x140086d1c`
- name: `?GenerateSubcontainers@CFolderHMEMediaContainer@@IEAAJPEBGAEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140085380`

## callees

- `0x140003690`
- `0x14000c920`
- `0x140024688`
- `0x1400346fc`
- `0x140039480`
- `0x140086c1c`
- `0x140086d24`
- `0x140086e98`
- `0x14009e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140086d03`
- `KERNEL32!LeaveCriticalSection` at `0x140086d03`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x140086cac`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x140086cac`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFolderHMEMediaContainer::GenerateSubcontainers(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rbx
  unsigned int v7; // eax
  HRESULT v8; // ebx
  unsigned __int64 v9; // rdi
  _QWORD *i; // r14
  const void **v11; // rax
  HRESULT SubcontainersForLibrarySubfolder; // eax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v15; // [rsp+28h] [rbp-30h]
  void *ppv; // [rsp+60h] [rbp+8h] BYREF
  PCWSTR pszPath; // [rsp+78h] [rbp+20h] BYREF

  v6 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 88LL))(a1);
  v7 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
  CShellLibraryCache::GetFolderListForSchema(v6, &lpCriticalSection, v7);
  v8 = 0;
  v9 = 0;
  for ( i = v15; v9 < i[1]; ++v9 )
  {
    v11 = (const void **)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](
                           i,
                           v9);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &pszPath,
      v11);
    ppv = 0;
    v8 = SHCreateItemFromParsingName(pszPath, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
    if ( v8 >= 0 )
    {
      if ( a2 )
        SubcontainersForLibrarySubfolder = CFolderHMEMediaContainer::GenerateSubcontainersForLibrarySubfolder(
                                             a1,
                                             (__int64)ppv,
                                             a2,
                                             a3);
      else
        SubcontainersForLibrarySubfolder = CFolderHMEMediaContainer::GenerateSubcontainersForLibrary(
                                             a1,
                                             (__int64)ppv,
                                             a3);
      v8 = SubcontainersForLibrarySubfolder;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&pszPath);
  }
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140086c1c  mov     [rsp+arg_8], rbx
0x140086c21  push    rbp
0x140086c22  push    rsi
0x140086c23  push    rdi
0x140086c24  push    r14
0x140086c26  push    r15
0x140086c28  sub     rsp, 30h
0x140086c2c  mov     r15, r8
0x140086c2f  mov     rbp, rdx
0x140086c32  mov     rsi, rcx
0x140086c35  mov     rax, [rcx]
0x140086c38  mov     rax, [rax+58h]
0x140086c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086c41  mov     rbx, rax
0x140086c44  mov     r9, [rsi]
0x140086c47  mov     rcx, rsi
0x140086c4a  mov     rax, [r9+50h]
0x140086c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086c53  mov     r8d, eax
0x140086c56  lea     rdx, [rsp+58h+lpCriticalSection]
0x140086c5b  mov     rcx, rbx
0x140086c5e  call    ?GetFolderListForSchema@CShellLibraryCache@@QEBA?AVCFolderListContext@1@W4MediaCacheSchema@@@Z; CShellLibraryCache::GetFolderListForSchema(MediaCacheSchema)
0x140086c63  nop
0x140086c64  xor     ebx, ebx
0x140086c66  xor     edi, edi
0x140086c68  mov     r14, [rsp+58h+var_30]
0x140086c6d  cmp     [r14+8], rbx
0x140086c71  jbe     loc_140086CFE
0x140086c77  mov     rdx, rdi
0x140086c7a  mov     rcx, r14
0x140086c7d  call    ??A?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAAAEAV?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@1@_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::operator[](unsigned __int64)
0x140086c82  mov     rdx, rax
0x140086c85  lea     rcx, [rsp+58h+pszPath]
0x140086c8a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x140086c8f  nop
0x140086c90  mov     [rsp+58h+ppv], 0
0x140086c99  lea     r9, [rsp+58h+ppv]; ppv
0x140086c9e  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x140086ca5  xor     edx, edx; pbc
0x140086ca7  mov     rcx, [rsp+58h+pszPath]; pszPath
0x140086cac  call    cs:__imp_SHCreateItemFromParsingName
0x140086cb2  mov     ebx, eax
0x140086cb4  test    eax, eax
0x140086cb6  js      short loc_140086CDC
0x140086cb8  mov     rdx, [rsp+58h+ppv]
0x140086cbd  mov     rcx, rsi
0x140086cc0  test    rbp, rbp
0x140086cc3  jz      short loc_140086CD2
0x140086cc5  mov     r9, r15
0x140086cc8  mov     r8, rbp
0x140086ccb  call    ?GenerateSubcontainersForLibrarySubfolder@CFolderHMEMediaContainer@@IEAAJPEAUIShellItem2@@PEBGAEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@@Z; CFolderHMEMediaContainer::GenerateSubcontainersForLibrarySubfolder(IShellItem2 *,ushort const *,ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)
0x140086cd0  jmp     short loc_140086CDA
0x140086cd2  mov     r8, r15
0x140086cd5  call    ?GenerateSubcontainersForLibrary@CFolderHMEMediaContainer@@IEAAJPEAUIShellItem2@@AEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@@Z; CFolderHMEMediaContainer::GenerateSubcontainersForLibrary(IShellItem2 *,ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)
0x140086cda  mov     ebx, eax
0x140086cdc  lea     rcx, [rsp+58h+ppv]
0x140086ce1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140086ce6  nop
0x140086ce7  lea     rcx, [rsp+58h+pszPath]
0x140086cec  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140086cf1  inc     rdi
0x140086cf4  cmp     rdi, [r14+8]
0x140086cf8  jb      loc_140086C77
0x140086cfe  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x140086d03  call    cs:__imp_LeaveCriticalSection
0x140086d09  mov     eax, ebx
0x140086d0b  mov     rbx, [rsp+58h+arg_8]
0x140086d10  add     rsp, 30h
0x140086d14  pop     r15
0x140086d16  pop     r14
0x140086d18  pop     rdi
0x140086d19  pop     rsi
0x140086d1a  pop     rbp
0x140086d1b  retn
```
