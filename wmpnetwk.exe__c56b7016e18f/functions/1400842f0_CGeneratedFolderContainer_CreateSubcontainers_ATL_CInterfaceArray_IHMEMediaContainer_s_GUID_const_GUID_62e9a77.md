# CGeneratedFolderContainer::CreateSubcontainers(ATL::CInterfaceArray<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196> &)

- ea: `0x1400842f0`
- end: `0x140084562`
- name: `?CreateSubcontainers@CGeneratedFolderContainer@@IEAAJAEAV?$CInterfaceArray@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400855d0`

## callees

- `0x140006d70`
- `0x14000c920`
- `0x140024688`
- `0x14008328c`
- `0x140083358`
- `0x1400842f0`
- `0x14009e010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400844f9`
- `ole32!CoTaskMemFree` at `0x14008450d`
- `ole32!CoTaskMemFree` at `0x140084517`
- `ole32!CoTaskMemFree` at `0x1400844f9`
- `ole32!CoTaskMemFree` at `0x14008450d`
- `ole32!CoTaskMemFree` at `0x140084517`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x1400843bd`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x1400843bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CGeneratedFolderContainer::CreateSubcontainers(_QWORD **a1, _QWORD *a2)
{
  HRESULT FolderContainer; // ebx
  _QWORD *v5; // r15
  void *v6; // r14
  __int64 v7; // rsi
  int v8; // edi
  int v9; // ebx
  char *v10; // rax
  LPVOID pv; // [rsp+50h] [rbp-19h] BYREF
  __int64 v13; // [rsp+58h] [rbp-11h] BYREF
  LPVOID v14; // [rsp+60h] [rbp-9h] BYREF
  LPCITEMIDLIST pidl; // [rsp+68h] [rbp-1h] BYREF
  __int64 v16; // [rsp+70h] [rbp+7h] BYREF
  void *v17; // [rsp+78h] [rbp+Fh] BYREF
  void *v18; // [rsp+80h] [rbp+17h] BYREF
  void *v19[7]; // [rsp+88h] [rbp+1Fh] BYREF
  int v20; // [rsp+D0h] [rbp+67h] BYREF
  void *ppvItem; // [rsp+E0h] [rbp+77h] BYREF
  IShellFolder *psfParent; // [rsp+E8h] [rbp+7Fh] BYREF

  psfParent = 0;
  if ( (*(int (__fastcall **)(_QWORD *, _QWORD, const GUID *, GUID *, IShellFolder **))(*a1[8] + 24LL))(
         a1[8],
         0,
         &BHID_SFObject,
         &GUID_000214e6_0000_0000_c000_000000000046,
         &psfParent) < 0 )
  {
    FolderContainer = 0;
  }
  else
  {
    v16 = 0;
    FolderContainer = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, __int64, __int64 *))psfParent->lpVtbl->EnumObjects)(
                        psfParent,
                        0,
                        32,
                        &v16);
    while ( !FolderContainer )
    {
      pidl = 0;
      v20 = 0;
      FolderContainer = (*(__int64 (__fastcall **)(__int64, __int64, LPCITEMIDLIST *, int *))(*(_QWORD *)v16 + 24LL))(
                          v16,
                          1,
                          &pidl,
                          &v20);
      if ( FolderContainer )
        break;
      ppvItem = 0;
      FolderContainer = SHCreateItemWithParent(0, psfParent, pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppvItem);
      if ( FolderContainer >= 0 )
      {
        v14 = 0;
        FolderContainer = (*(__int64 (__fastcall **)(void *, _QWORD, LPVOID *))(*(_QWORD *)ppvItem + 40LL))(
                            ppvItem,
                            0,
                            &v14);
        if ( FolderContainer >= 0 )
        {
          pv = 0;
          FolderContainer = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)ppvItem + 40LL))(
                              ppvItem,
                              2147647488LL,
                              &pv);
          if ( FolderContainer >= 0 )
          {
            v13 = 0;
            v5 = a1[7];
            v6 = ppvItem;
            v7 = ((__int64 (__fastcall *)(_QWORD **))(*a1)[12])(a1);
            v8 = ((__int64 (__fastcall *)(_QWORD **))(*a1)[6])(a1);
            v9 = ((__int64 (__fastcall *)(_QWORD **))(*a1)[10])(a1);
            v10 = (char *)((__int64 (__fastcall *)(_QWORD **))(*a1)[7])(a1);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              v19,
              v10);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v18,
              (char *)pv);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v17,
              (char *)v14);
            FolderContainer = CGeneratedContainerFactory::CreateFolderContainer(
                                (_DWORD)v5,
                                (unsigned int)&v17,
                                (unsigned int)&v18,
                                (unsigned int)v19,
                                v9,
                                v8,
                                v7,
                                (__int64)v6,
                                (__int64)&v13);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v17);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v18);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v19);
            if ( FolderContainer >= 0 )
              ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(
                a2,
                v13);
            CoTaskMemFree(pv);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
          }
          CoTaskMemFree(v14);
        }
      }
      CoTaskMemFree((LPVOID)pidl);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppvItem);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&psfParent);
  return (unsigned int)FolderContainer;
}

```

## disassembly

```asm
0x1400842f0  mov     [rsp-8+arg_8], rbx
0x1400842f5  push    rbp
0x1400842f6  push    rsi
0x1400842f7  push    rdi
0x1400842f8  push    r12
0x1400842fa  push    r13
0x1400842fc  push    r14
0x1400842fe  push    r15
0x140084300  lea     rbp, [rsp-27h]
0x140084305  sub     rsp, 90h
0x14008430c  mov     r13, rdx
0x14008430f  mov     r12, rcx
0x140084312  xor     edi, edi
0x140084314  mov     [rbp+57h+psfParent], rdi
0x140084318  mov     rcx, [rcx+40h]
0x14008431c  mov     rax, [rcx]
0x14008431f  lea     rdx, [rbp+57h+psfParent]
0x140084323  mov     [rsp+0C0h+ppvItem], rdx
0x140084328  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x14008432f  lea     r8, BHID_SFObject
0x140084336  xor     edx, edx
0x140084338  mov     rax, [rax+18h]
0x14008433c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084341  test    eax, eax
0x140084343  js      loc_14008453A
0x140084349  mov     [rbp+57h+var_50], rdi
0x14008434d  mov     rcx, [rbp+57h+psfParent]
0x140084351  mov     rax, [rcx]
0x140084354  lea     r9, [rbp+57h+var_50]
0x140084358  xor     edx, edx
0x14008435a  lea     r8d, [rdi+20h]
0x14008435e  mov     rax, [rax+20h]
0x140084362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084367  mov     ebx, eax
0x140084369  test    eax, eax
0x14008436b  jnz     loc_14008452F
0x140084371  mov     [rbp+57h+pidl], rdi
0x140084375  mov     [rbp+57h+arg_0], edi
0x140084378  mov     rcx, [rbp+57h+var_50]
0x14008437c  mov     rax, [rcx]
0x14008437f  lea     r9, [rbp+57h+arg_0]
0x140084383  lea     r8, [rbp+57h+pidl]
0x140084387  mov     edx, 1
0x14008438c  mov     rax, [rax+18h]
0x140084390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084395  mov     ebx, eax
0x140084397  test    eax, eax
0x140084399  jnz     loc_14008452F
0x14008439f  mov     [rbp+57h+arg_10], rdi
0x1400843a3  lea     rax, [rbp+57h+arg_10]
0x1400843a7  mov     [rsp+0C0h+ppvItem], rax; ppvItem
0x1400843ac  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1400843b3  mov     r8, [rbp+57h+pidl]; pidl
0x1400843b7  mov     rdx, [rbp+57h+psfParent]; psfParent
0x1400843bb  xor     ecx, ecx; pidlParent
0x1400843bd  call    cs:__imp_SHCreateItemWithParent
0x1400843c3  mov     ebx, eax
0x1400843c5  test    eax, eax
0x1400843c7  js      loc_140084513
0x1400843cd  mov     [rbp+57h+var_60], rdi
0x1400843d1  mov     rcx, [rbp+57h+arg_10]
0x1400843d5  mov     rax, [rcx]
0x1400843d8  lea     r8, [rbp+57h+var_60]
0x1400843dc  xor     edx, edx
0x1400843de  mov     rax, [rax+28h]
0x1400843e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400843e7  mov     ebx, eax
0x1400843e9  test    eax, eax
0x1400843eb  js      loc_140084513
0x1400843f1  mov     [rbp+57h+pv], rdi
0x1400843f5  mov     rcx, [rbp+57h+arg_10]
0x1400843f9  mov     rax, [rcx]
0x1400843fc  lea     r8, [rbp+57h+pv]
0x140084400  mov     edx, 80028000h
0x140084405  mov     rax, [rax+28h]
0x140084409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008440e  mov     ebx, eax
0x140084410  test    eax, eax
0x140084412  js      loc_140084509
0x140084418  mov     [rbp+57h+var_68], rdi
0x14008441c  mov     r15, [r12+38h]
0x140084421  mov     r14, [rbp+57h+arg_10]
0x140084425  mov     rax, [r12]
0x140084429  mov     rcx, r12
0x14008442c  mov     rax, [rax+60h]
0x140084430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084435  mov     rsi, rax
0x140084438  mov     rcx, [r12]
0x14008443c  mov     rax, [rcx+30h]
0x140084440  mov     rcx, r12
0x140084443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084448  mov     edi, eax
0x14008444a  mov     rcx, [r12]
0x14008444e  mov     rax, [rcx+50h]
0x140084452  mov     rcx, r12
0x140084455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008445a  mov     ebx, eax
0x14008445c  mov     rcx, [r12]
0x140084460  mov     rax, [rcx+38h]
0x140084464  mov     rcx, r12
0x140084467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008446c  mov     rdx, rax
0x14008446f  lea     rcx, [rbp+57h+var_38]
0x140084473  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140084478  nop
0x140084479  mov     rdx, [rbp+57h+pv]
0x14008447d  lea     rcx, [rbp+57h+var_40]
0x140084481  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140084486  nop
0x140084487  mov     rdx, [rbp+57h+var_60]
0x14008448b  lea     rcx, [rbp+57h+var_48]
0x14008448f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140084494  nop
0x140084495  lea     rax, [rbp+57h+var_68]
0x140084499  mov     [rsp+0C0h+var_80], rax
0x14008449e  mov     [rsp+0C0h+var_88], r14
0x1400844a3  mov     [rsp+0C0h+var_90], rsi
0x1400844a8  mov     [rsp+0C0h+var_98], edi
0x1400844ac  mov     dword ptr [rsp+0C0h+ppvItem], ebx
0x1400844b0  lea     r9, [rbp+57h+var_38]
0x1400844b4  lea     r8, [rbp+57h+var_40]
0x1400844b8  lea     rdx, [rbp+57h+var_48]
0x1400844bc  mov     rcx, r15
0x1400844bf  call    ?CreateFolderContainer@CGeneratedContainerFactory@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@00W4MediaCacheSchema@@W4WMPContentProviderObjectClasses@@PEBVCShellCommandFactory@@PEAUIShellItem2@@PEAPEAUIHMEMediaContainer@@@Z; CGeneratedContainerFactory::CreateFolderContainer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,WMPContentProviderObjectClasses,CShellCommandFactory const *,IShellItem2 *,IHMEMediaContainer * *)
0x1400844c4  mov     ebx, eax
0x1400844c6  lea     rcx, [rbp+57h+var_48]
0x1400844ca  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400844cf  nop
0x1400844d0  lea     rcx, [rbp+57h+var_40]
0x1400844d4  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400844d9  nop
0x1400844da  lea     rcx, [rbp+57h+var_38]
0x1400844de  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400844e3  xor     edi, edi
0x1400844e5  test    ebx, ebx
0x1400844e7  js      short loc_1400844F5
0x1400844e9  mov     rdx, [rbp+57h+var_68]
0x1400844ed  mov     rcx, r13
0x1400844f0  call    ?Add@?$CAtlArray@V?$CComQIPtr@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMEMediaContainer@@$1?_GUID_62e9a77d_5241_4248_9778_7084017de196@@3U__s_GUID@@B@2@@ATL@@QEAA_KPEAUIHMEMediaContainer@@@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>,ATL::CComQIPtrElementTraits<IHMEMediaContainer,&__s_GUID const _GUID_62e9a77d_5241_4248_9778_7084017de196>>::Add(IHMEMediaContainer *)
0x1400844f5  mov     rcx, [rbp+57h+pv]; pv
0x1400844f9  call    cs:__imp_CoTaskMemFree
0x1400844ff  nop
0x140084500  lea     rcx, [rbp+57h+var_68]
0x140084504  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140084509  mov     rcx, [rbp+57h+var_60]; pv
0x14008450d  call    cs:__imp_CoTaskMemFree
0x140084513  mov     rcx, [rbp+57h+pidl]; pv
0x140084517  call    cs:__imp_CoTaskMemFree
0x14008451d  nop
0x14008451e  lea     rcx, [rbp+57h+arg_10]
0x140084522  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140084527  test    ebx, ebx
0x140084529  jz      loc_140084371
0x14008452f  lea     rcx, [rbp+57h+var_50]
0x140084533  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140084538  jmp     short loc_14008453C
0x14008453a  mov     ebx, edi
0x14008453c  lea     rcx, [rbp+57h+psfParent]
0x140084540  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140084545  mov     eax, ebx
0x140084547  mov     rbx, [rsp+0C0h+arg_8]
0x14008454f  add     rsp, 90h
0x140084556  pop     r15
0x140084558  pop     r14
0x14008455a  pop     r13
0x14008455c  pop     r12
0x14008455e  pop     rdi
0x14008455f  pop     rsi
0x140084560  pop     rbp
0x140084561  retn
```
