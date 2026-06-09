# CFolderHMEMediaContainer::GenerateSubcontainersForLibrary(IShellItem2 *,ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)

- ea: `0x140086d24`
- end: `0x140086e92`
- name: `?GenerateSubcontainersForLibrary@CFolderHMEMediaContainer@@IEAAJPEAUIShellItem2@@AEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@@Z`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140086c1c`

## callees

- `0x140006d70`
- `0x14000c920`
- `0x140024688`
- `0x14008328c`
- `0x140083358`
- `0x140086d24`
- `0x14009e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140086e5e`
- `ole32!CoTaskMemFree` at `0x140086e72`
- `ole32!CoTaskMemFree` at `0x140086e5e`
- `ole32!CoTaskMemFree` at `0x140086e72`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFolderHMEMediaContainer::GenerateSubcontainersForLibrary(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  int FolderContainer; // ebx
  __int64 v7; // r14
  __int64 v8; // rsi
  int v9; // edi
  int v10; // ebx
  char *v11; // rax
  LPVOID v13; // [rsp+50h] [rbp-20h] BYREF
  void *v14; // [rsp+58h] [rbp-18h] BYREF
  void *v15; // [rsp+60h] [rbp-10h] BYREF
  void *v16; // [rsp+68h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v18; // [rsp+C8h] [rbp+58h] BYREF

  v13 = 0;
  FolderContainer = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, 0, &v13);
  if ( FolderContainer >= 0 )
  {
    pv = 0;
    FolderContainer = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)a2 + 40LL))(
                        a2,
                        2147647488LL,
                        &pv);
    if ( FolderContainer >= 0 )
    {
      v18 = 0;
      v7 = a1[4];
      v8 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1);
      v9 = *(_DWORD *)(a1[2] + 32LL);
      v10 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
      v11 = (char *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v16,
        v11);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v15,
        (char *)pv);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v14,
        (char *)v13);
      FolderContainer = CGeneratedContainerFactory::CreateFolderContainer(
                          v7,
                          (unsigned int)&v14,
                          (unsigned int)&v15,
                          (unsigned int)&v16,
                          v10,
                          v9,
                          v8,
                          a2,
                          (__int64)&v18);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v14);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v15);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v16);
      if ( FolderContainer >= 0 )
        ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(
          a3,
          v18);
      CoTaskMemFree(pv);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
    }
    CoTaskMemFree(v13);
  }
  return (unsigned int)FolderContainer;
}

```

## disassembly

```asm
0x140086d24  mov     [rsp-38h+arg_0], rbx
0x140086d29  push    rbp
0x140086d2a  push    rsi
0x140086d2b  push    rdi
0x140086d2c  push    r12
0x140086d2e  push    r13
0x140086d30  push    r14
0x140086d32  push    r15
0x140086d34  mov     rbp, rsp
0x140086d37  sub     rsp, 70h
0x140086d3b  mov     r12, r8
0x140086d3e  mov     r15, rdx
0x140086d41  mov     r13, rcx
0x140086d44  xor     edi, edi
0x140086d46  mov     [rbp+var_20], rdi
0x140086d4a  mov     rax, [rdx]
0x140086d4d  lea     r8, [rbp+var_20]
0x140086d51  xor     edx, edx
0x140086d53  mov     rcx, r15
0x140086d56  mov     rax, [rax+28h]
0x140086d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086d5f  mov     ebx, eax
0x140086d61  test    eax, eax
0x140086d63  js      loc_140086E78
0x140086d69  mov     [rbp+pv], rdi
0x140086d6d  mov     rax, [r15]
0x140086d70  lea     r8, [rbp+pv]
0x140086d74  mov     edx, 80028000h
0x140086d79  mov     rcx, r15
0x140086d7c  mov     rax, [rax+28h]
0x140086d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086d85  mov     ebx, eax
0x140086d87  test    eax, eax
0x140086d89  js      loc_140086E6E
0x140086d8f  mov     [rbp+arg_18], rdi
0x140086d93  mov     r14, [r13+20h]
0x140086d97  mov     rax, [r13+0]
0x140086d9b  mov     rcx, r13
0x140086d9e  mov     rax, [rax+60h]
0x140086da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086da7  mov     rsi, rax
0x140086daa  mov     rcx, [r13+10h]
0x140086dae  mov     edi, [rcx+20h]
0x140086db1  mov     rcx, [r13+0]
0x140086db5  mov     rax, [rcx+50h]
0x140086db9  mov     rcx, r13
0x140086dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086dc1  mov     ebx, eax
0x140086dc3  mov     rcx, [r13+0]
0x140086dc7  mov     rax, [rcx+38h]
0x140086dcb  mov     rcx, r13
0x140086dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086dd3  mov     rdx, rax
0x140086dd6  lea     rcx, [rbp+var_8]
0x140086dda  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140086ddf  nop
0x140086de0  mov     rdx, [rbp+pv]
0x140086de4  lea     rcx, [rbp+var_10]
0x140086de8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140086ded  nop
0x140086dee  mov     rdx, [rbp+var_20]
0x140086df2  lea     rcx, [rbp+var_18]
0x140086df6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140086dfb  nop
0x140086dfc  lea     rax, [rbp+arg_18]
0x140086e00  mov     [rsp+70h+var_30], rax
0x140086e05  mov     [rsp+70h+var_38], r15
0x140086e0a  mov     [rsp+70h+var_40], rsi
0x140086e0f  mov     [rsp+70h+var_48], edi
0x140086e13  mov     [rsp+70h+var_50], ebx
0x140086e17  lea     r9, [rbp+var_8]
0x140086e1b  lea     r8, [rbp+var_10]
0x140086e1f  lea     rdx, [rbp+var_18]
0x140086e23  mov     rcx, r14
0x140086e26  call    ?CreateFolderContainer@CGeneratedContainerFactory@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@00W4MediaCacheSchema@@W4WMPContentProviderObjectClasses@@PEBVCShellCommandFactory@@PEAUIShellItem2@@PEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::CreateFolderContainer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,WMPContentProviderObjectClasses,CShellCommandFactory const *,IShellItem2 *,IHMEMediaContainer * *)
0x140086e2b  mov     ebx, eax
0x140086e2d  lea     rcx, [rbp+var_18]
0x140086e31  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140086e36  nop
0x140086e37  lea     rcx, [rbp+var_10]
0x140086e3b  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140086e40  nop
0x140086e41  lea     rcx, [rbp+var_8]
0x140086e45  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140086e4a  test    ebx, ebx
0x140086e4c  js      short loc_140086E5A
0x140086e4e  mov     rdx, [rbp+arg_18]
0x140086e52  mov     rcx, r12
0x140086e55  call    ?Add@?$CAtlArray@V?$CComQIPtr@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@2@@ATL@@QEAA_KPEAUIHMEMediaContainer@@@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(IHMEMediaContainer *)
0x140086e5a  mov     rcx, [rbp+pv]; pv
0x140086e5e  call    cs:__imp_CoTaskMemFree
0x140086e64  nop
0x140086e65  lea     rcx, [rbp+arg_18]
0x140086e69  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140086e6e  mov     rcx, [rbp+var_20]; pv
0x140086e72  call    cs:__imp_CoTaskMemFree
0x140086e78  mov     eax, ebx
0x140086e7a  mov     rbx, [rsp+70h+arg_0]
0x140086e82  add     rsp, 70h
0x140086e86  pop     r15
0x140086e88  pop     r14
0x140086e8a  pop     r13
0x140086e8c  pop     r12
0x140086e8e  pop     rdi
0x140086e8f  pop     rsi
0x140086e90  pop     rbp
0x140086e91  retn
```
