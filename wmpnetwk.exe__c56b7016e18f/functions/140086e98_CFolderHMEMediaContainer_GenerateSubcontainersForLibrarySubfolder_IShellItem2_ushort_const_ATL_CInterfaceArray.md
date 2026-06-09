# CFolderHMEMediaContainer::GenerateSubcontainersForLibrarySubfolder(IShellItem2 *,ushort const *,ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)

- ea: `0x140086e98`
- end: `0x140087131`
- name: `?GenerateSubcontainersForLibrarySubfolder@CFolderHMEMediaContainer@@IEAAJPEAUIShellItem2@@PEBGAEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@@Z`
- size: `665`
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
- `0x140086e98`
- `0x14009e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400870cb`
- `ole32!CoTaskMemFree` at `0x1400870df`
- `ole32!CoTaskMemFree` at `0x1400870e9`
- `ole32!CoTaskMemFree` at `0x1400870cb`
- `ole32!CoTaskMemFree` at `0x1400870df`
- `ole32!CoTaskMemFree` at `0x1400870e9`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x140086f6e`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x140086f6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CFolderHMEMediaContainer::GenerateSubcontainersForLibrarySubfolder(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  HRESULT FolderContainer; // ebx
  unsigned __int16 *v7; // rax
  int v8; // r8d
  int v9; // edx
  __int64 v10; // r15
  void *v11; // r14
  __int64 v12; // rsi
  int v13; // edi
  int v14; // ebx
  char *v15; // rax
  void *ppvItem; // [rsp+50h] [rbp-29h] BYREF
  LPVOID v18; // [rsp+58h] [rbp-21h] BYREF
  IShellFolder *psfParent; // [rsp+60h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-11h] BYREF
  __int64 v21; // [rsp+70h] [rbp-9h] BYREF
  LPCITEMIDLIST pidl; // [rsp+78h] [rbp-1h] BYREF
  __int64 v23; // [rsp+80h] [rbp+7h] BYREF
  void *v24; // [rsp+88h] [rbp+Fh] BYREF
  void *v25; // [rsp+90h] [rbp+17h] BYREF
  void *v26[7]; // [rsp+98h] [rbp+1Fh] BYREF
  int v28; // [rsp+E8h] [rbp+6Fh] BYREF

  psfParent = 0;
  FolderContainer = (*(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *, IShellFolder **))(*(_QWORD *)a2 + 24LL))(
                      a2,
                      0,
                      &BHID_SFObject,
                      &GUID_000214e6_0000_0000_c000_000000000046,
                      &psfParent);
  if ( FolderContainer >= 0 )
  {
    v23 = 0;
    FolderContainer = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, __int64, __int64 *))psfParent->lpVtbl->EnumObjects)(
                        psfParent,
                        0,
                        32,
                        &v23);
    while ( !FolderContainer )
    {
      pidl = 0;
      v28 = 0;
      FolderContainer = (*(__int64 (__fastcall **)(__int64, __int64, LPCITEMIDLIST *, int *))(*(_QWORD *)v23 + 24LL))(
                          v23,
                          1,
                          &pidl,
                          &v28);
      if ( FolderContainer )
        break;
      ppvItem = 0;
      FolderContainer = SHCreateItemWithParent(0, psfParent, pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppvItem);
      if ( FolderContainer >= 0 )
      {
        v18 = 0;
        FolderContainer = (*(__int64 (__fastcall **)(void *, _QWORD, LPVOID *))(*(_QWORD *)ppvItem + 40LL))(
                            ppvItem,
                            0,
                            &v18);
        if ( FolderContainer >= 0 )
        {
          v7 = (unsigned __int16 *)v18;
          do
          {
            v8 = *(unsigned __int16 *)((char *)v7 + a3 - (_QWORD)v18);
            v9 = *v7 - v8;
            if ( v9 )
              break;
            ++v7;
          }
          while ( v8 );
          if ( !v9 )
          {
            pv = 0;
            FolderContainer = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)ppvItem + 40LL))(
                                ppvItem,
                                2147647488LL,
                                &pv);
            if ( FolderContainer >= 0 )
            {
              v21 = 0;
              v10 = a1[4];
              v11 = ppvItem;
              v12 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1);
              v13 = *(_DWORD *)(a1[2] + 32LL);
              v14 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 80LL))(a1);
              v15 = (char *)(*(__int64 (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
                v26,
                v15);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
                &v25,
                (char *)pv);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
                &v24,
                (char *)v18);
              FolderContainer = CGeneratedContainerFactory::CreateFolderContainer(
                                  v10,
                                  (unsigned int)&v24,
                                  (unsigned int)&v25,
                                  (unsigned int)v26,
                                  v14,
                                  v13,
                                  v12,
                                  (__int64)v11,
                                  (__int64)&v21);
              ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v24);
              ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v25);
              ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v26);
              if ( FolderContainer >= 0 )
                ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(
                  a4,
                  v21);
              CoTaskMemFree(pv);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
            }
          }
        }
        CoTaskMemFree(v18);
      }
      CoTaskMemFree((LPVOID)pidl);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppvItem);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&psfParent);
  return (unsigned int)FolderContainer;
}

```

## disassembly

```asm
0x140086e98  mov     [rsp-8+arg_10], rbx
0x140086e9d  mov     [rsp-8+arg_0], rcx
0x140086ea2  push    rbp
0x140086ea3  push    rsi
0x140086ea4  push    rdi
0x140086ea5  push    r12
0x140086ea7  push    r13
0x140086ea9  push    r14
0x140086eab  push    r15
0x140086ead  lea     rbp, [rsp-27h]
0x140086eb2  sub     rsp, 0A0h
0x140086eb9  mov     r12, r9
0x140086ebc  mov     r13, r8
0x140086ebf  mov     r10, rdx
0x140086ec2  xor     edi, edi
0x140086ec4  mov     [rbp+57h+psfParent], rdi
0x140086ec8  mov     rax, [rdx]
0x140086ecb  lea     rcx, [rbp+57h+psfParent]
0x140086ecf  mov     [rsp+0D0h+ppvItem], rcx
0x140086ed4  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x140086edb  lea     r8, BHID_SFObject
0x140086ee2  xor     edx, edx
0x140086ee4  mov     rcx, r10
0x140086ee7  mov     rax, [rax+18h]
0x140086eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086ef0  mov     ebx, eax
0x140086ef2  test    eax, eax
0x140086ef4  js      loc_14008710B
0x140086efa  mov     [rbp+57h+var_50], rdi
0x140086efe  mov     rcx, [rbp+57h+psfParent]
0x140086f02  mov     rax, [rcx]
0x140086f05  lea     r9, [rbp+57h+var_50]
0x140086f09  xor     edx, edx
0x140086f0b  lea     r8d, [rdi+20h]
0x140086f0f  mov     rax, [rax+20h]
0x140086f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086f18  mov     ebx, eax
0x140086f1a  test    eax, eax
0x140086f1c  jnz     loc_140087101
0x140086f22  mov     [rbp+57h+pidl], rdi
0x140086f26  mov     [rbp+57h+arg_8], edi
0x140086f29  mov     rcx, [rbp+57h+var_50]
0x140086f2d  mov     rax, [rcx]
0x140086f30  lea     r9, [rbp+57h+arg_8]
0x140086f34  lea     r8, [rbp+57h+pidl]
0x140086f38  mov     edx, 1
0x140086f3d  mov     rax, [rax+18h]
0x140086f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086f46  mov     ebx, eax
0x140086f48  test    eax, eax
0x140086f4a  jnz     loc_140087101
0x140086f50  mov     [rbp+57h+var_80], rdi
0x140086f54  lea     rax, [rbp+57h+var_80]
0x140086f58  mov     [rsp+0D0h+ppvItem], rax; ppvItem
0x140086f5d  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x140086f64  mov     r8, [rbp+57h+pidl]; pidl
0x140086f68  mov     rdx, [rbp+57h+psfParent]; psfParent
0x140086f6c  xor     ecx, ecx; pidlParent
0x140086f6e  call    cs:__imp_SHCreateItemWithParent
0x140086f74  mov     ebx, eax
0x140086f76  test    eax, eax
0x140086f78  js      loc_1400870E5
0x140086f7e  mov     [rbp+57h+var_78], rdi
0x140086f82  mov     rcx, [rbp+57h+var_80]
0x140086f86  mov     rax, [rcx]
0x140086f89  lea     r8, [rbp+57h+var_78]
0x140086f8d  xor     edx, edx
0x140086f8f  mov     rax, [rax+28h]
0x140086f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086f98  mov     ebx, eax
0x140086f9a  test    eax, eax
0x140086f9c  js      loc_1400870DB
0x140086fa2  mov     rax, [rbp+57h+var_78]
0x140086fa6  mov     rcx, r13
0x140086fa9  sub     rcx, rax
0x140086fac  movzx   edx, word ptr [rax]
0x140086faf  movzx   r8d, word ptr [rax+rcx]
0x140086fb4  sub     edx, r8d
0x140086fb7  jnz     short loc_140086FC2
0x140086fb9  add     rax, 2
0x140086fbd  test    r8d, r8d
0x140086fc0  jnz     short loc_140086FAC
0x140086fc2  test    edx, edx
0x140086fc4  jnz     loc_1400870DB
0x140086fca  mov     [rbp+57h+pv], rdi
0x140086fce  mov     rcx, [rbp+57h+var_80]
0x140086fd2  mov     rax, [rcx]
0x140086fd5  lea     r8, [rbp+57h+pv]
0x140086fd9  mov     edx, 80028000h
0x140086fde  mov     rax, [rax+28h]
0x140086fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086fe7  mov     ebx, eax
0x140086fe9  test    eax, eax
0x140086feb  js      loc_1400870DB
0x140086ff1  mov     [rbp+57h+var_60], rdi
0x140086ff5  mov     rbx, [rbp+57h+arg_0]
0x140086ff9  mov     r15, [rbx+20h]
0x140086ffd  mov     r14, [rbp+57h+var_80]
0x140087001  mov     rax, [rbx]
0x140087004  mov     rcx, rbx
0x140087007  mov     rax, [rax+60h]
0x14008700b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087010  mov     rsi, rax
0x140087013  mov     rcx, [rbx+10h]
0x140087017  mov     edi, [rcx+20h]
0x14008701a  mov     rcx, [rbx]
0x14008701d  mov     rax, [rcx+50h]
0x140087021  mov     rcx, rbx
0x140087024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087029  mov     ebx, eax
0x14008702b  mov     rdx, [rbp+57h+arg_0]
0x14008702f  mov     rcx, [rdx]
0x140087032  mov     rax, [rcx+38h]
0x140087036  mov     rcx, rdx
0x140087039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008703e  mov     rdx, rax
0x140087041  lea     rcx, [rbp+57h+var_38]
0x140087045  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14008704a  nop
0x14008704b  mov     rdx, [rbp+57h+pv]
0x14008704f  lea     rcx, [rbp+57h+var_40]
0x140087053  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140087058  nop
0x140087059  mov     rdx, [rbp+57h+var_78]
0x14008705d  lea     rcx, [rbp+57h+var_48]
0x140087061  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140087066  nop
0x140087067  lea     rax, [rbp+57h+var_60]
0x14008706b  mov     [rsp+0D0h+var_90], rax
0x140087070  mov     [rsp+0D0h+var_98], r14
0x140087075  mov     [rsp+0D0h+var_A0], rsi
0x14008707a  mov     [rsp+0D0h+var_A8], edi
0x14008707e  mov     dword ptr [rsp+0D0h+ppvItem], ebx
0x140087082  lea     r9, [rbp+57h+var_38]
0x140087086  lea     r8, [rbp+57h+var_40]
0x14008708a  lea     rdx, [rbp+57h+var_48]
0x14008708e  mov     rcx, r15
0x140087091  call    ?CreateFolderContainer@CGeneratedContainerFactory@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@00W4MediaCacheSchema@@W4WMPContentProviderObjectClasses@@PEBVCShellCommandFactory@@PEAUIShellItem2@@PEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::CreateFolderContainer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,WMPContentProviderObjectClasses,CShellCommandFactory const *,IShellItem2 *,IHMEMediaContainer * *)
0x140087096  mov     ebx, eax
0x140087098  lea     rcx, [rbp+57h+var_48]
0x14008709c  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400870a1  nop
0x1400870a2  lea     rcx, [rbp+57h+var_40]
0x1400870a6  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400870ab  nop
0x1400870ac  lea     rcx, [rbp+57h+var_38]
0x1400870b0  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400870b5  xor     edi, edi
0x1400870b7  test    ebx, ebx
0x1400870b9  js      short loc_1400870C7
0x1400870bb  mov     rdx, [rbp+57h+var_60]
0x1400870bf  mov     rcx, r12
0x1400870c2  call    ?Add@?$CAtlArray@V?$CComQIPtr@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@2@@ATL@@QEAA_KPEAUIHMEMediaContainer@@@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(IHMEMediaContainer *)
0x1400870c7  mov     rcx, [rbp+57h+pv]; pv
0x1400870cb  call    cs:__imp_CoTaskMemFree
0x1400870d1  nop
0x1400870d2  lea     rcx, [rbp+57h+var_60]
0x1400870d6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400870db  mov     rcx, [rbp+57h+var_78]; pv
0x1400870df  call    cs:__imp_CoTaskMemFree
0x1400870e5  mov     rcx, [rbp+57h+pidl]; pv
0x1400870e9  call    cs:__imp_CoTaskMemFree
0x1400870ef  nop
0x1400870f0  lea     rcx, [rbp+57h+var_80]
0x1400870f4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400870f9  test    ebx, ebx
0x1400870fb  jz      loc_140086F22
0x140087101  lea     rcx, [rbp+57h+var_50]
0x140087105  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008710a  nop
0x14008710b  lea     rcx, [rbp+57h+psfParent]
0x14008710f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140087114  mov     eax, ebx
0x140087116  mov     rbx, [rsp+0D0h+arg_10]
0x14008711e  add     rsp, 0A0h
0x140087125  pop     r15
0x140087127  pop     r14
0x140087129  pop     r13
0x14008712b  pop     r12
0x14008712d  pop     rdi
0x14008712e  pop     rsi
0x14008712f  pop     rbp
0x140087130  retn
```
