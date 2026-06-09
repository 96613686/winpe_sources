# CPreflistFolder::GetUIObjectOf(HWND__ *,uint,_ITEMIDLIST const * *,_GUID const &,uint *,void * *)

- ea: `0x18000f770`
- end: `0x18000fa75`
- name: `?GetUIObjectOf@CPreflistFolder@@UEAAJPEAUHWND__@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `773`
- prototype: `__int64 __fastcall(LPCITEMIDLIST *this, HWND, int, const struct _ITEMIDLIST **, const struct _GUID *riid, unsigned int *, void **ppv)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000d0d0`
- `0x18000d578`
- `0x18000f770`
- `0x18000fc60`
- `0x180012730`
- `0x18001369c`
- `0x180013c48`
- `0x180014158`
- `0x180027594`
- `0x180027648`
- `0x18002868c`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `SHELL32!SHCreateDataObject` at `0x18000f89c`
- `SHELL32!SHCreateDataObject` at `0x18000f89c`

## pseudocode

```c
__int64 __fastcall CPreflistFolder::GetUIObjectOf(
        LPCITEMIDLIST *this,
        HWND a2,
        int a3,
        const struct _ITEMIDLIST **a4,
        const struct _GUID *riid,
        unsigned int *a6,
        void **ppv)
{
  struct IUnknown *v10; // rdx
  __int64 v11; // rax
  struct IUnknown *v12; // rbx
  struct IUnknownVtbl *v13; // r14
  int v14; // esi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  struct IUnknown *v18; // rbx
  __int64 v19; // rax
  struct IUnknown *v20; // rbx
  struct IUnknown *v22; // [rsp+30h] [rbp-61h] BYREF
  struct IUnknown *v23; // [rsp+38h] [rbp-59h] BYREF
  _BYTE v24[96]; // [rsp+40h] [rbp-51h] BYREF

  CPreflistFolder::InitializeDataSource((CPreflistFolder *)(this - 1));
  if ( a3 == 1 && a4 && *a4 )
  {
    StructToProfile((CProfile *)v24, (const struct WPLDATA *)(*a4)->mkid.abID);
    v11 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_000214e4_0000_0000_c000_000000000046.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_000214e4_0000_0000_c000_000000000046.Data1 )
      v11 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_000214e4_0000_0000_c000_000000000046.Data4;
    if ( v11 )
    {
      v15 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_0000010e_0000_0000_c000_000000000046.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_0000010e_0000_0000_c000_000000000046.Data1 )
        v15 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_0000010e_0000_0000_c000_000000000046.Data4;
      if ( !v15 )
      {
        v14 = SHCreateDataObject(this[18], 1u, a4, 0, riid, ppv);
LABEL_41:
        CProfile::~CProfile((CProfile *)v24);
        return (unsigned int)v14;
      }
      v16 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_00000122_0000_0000_c000_000000000046.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_00000122_0000_0000_c000_000000000046.Data1 )
        v16 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_00000122_0000_0000_c000_000000000046.Data4;
      if ( v16 )
      {
        v17 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1 )
          v17 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_000214fa_0000_0000_c000_000000000046.Data4;
        if ( v17
          || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                              + 112LL))(
               CSingletonPtr<CWlanProfileStore>::s_pInstance,
               v24) != 1 )
        {
          v19 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1.Data1;
          if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1.Data1 )
            v19 = *(_QWORD *)riid->Data4 - *(_QWORD *)GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1.Data4;
          if ( v19
            || (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                                + 112LL))(
                 CSingletonPtr<CWlanProfileStore>::s_pInstance,
                 v24) )
          {
            *ppv = 0;
            v14 = -2147467262;
            goto LABEL_41;
          }
          v20 = 0;
          v22 = 0;
          v23 = 0;
          v14 = ATL::CComObject<CPreflistExtractImage>::CreateInstance(&v23);
          if ( v14 >= 0 )
          {
            if ( v23 )
            {
              ATL::AtlComPtrAssign(&v22, v23);
              v20 = v22;
            }
            CProfile::Clone((CProfile *)&v20[10], (const struct CProfile *)v24);
            v14 = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, void **))v20->lpVtbl->QueryInterface)(
                    v20,
                    riid,
                    ppv);
          }
        }
        else
        {
          v18 = 0;
          v22 = 0;
          v23 = 0;
          v14 = ATL::CComObject<CPreflistExtractIcon>::CreateInstance(&v23);
          if ( v14 >= 0 )
          {
            if ( v23 )
            {
              ATL::AtlComPtrAssign(&v22, v23);
              v18 = v22;
            }
            CProfile::Clone((CProfile *)&v18[9], (const struct CProfile *)v24);
            v14 = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, void **))v18->lpVtbl->QueryInterface)(
                    v18,
                    riid,
                    ppv);
          }
        }
      }
      else
      {
        v22 = 0;
        v14 = CPreflistDropTarget::CreateTarget(this[18], v10, (const struct CProfile *)v24, &v22);
        if ( v14 >= 0 )
          v14 = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, void **))v22->lpVtbl->QueryInterface)(
                  v22,
                  riid,
                  ppv);
      }
    }
    else
    {
      v12 = 0;
      v22 = 0;
      v13 = (struct IUnknownVtbl *)this[19];
      v23 = 0;
      v14 = ATL::CComObject<CPreflistContextMenu>::CreateInstance(&v23);
      if ( v14 >= 0 )
      {
        if ( v23 )
        {
          ATL::AtlComPtrAssign(&v22, v23);
          v12 = v22;
        }
        CProfile::Clone((CProfile *)&v12[13], (const struct CProfile *)v24);
        v12[24].lpVtbl = v13;
        v14 = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, void **))v12->lpVtbl->QueryInterface)(
                v12,
                riid,
                ppv);
      }
    }
    ATL::CComPtrBase<CUICommand>::~CComPtrBase<CUICommand>(&v22);
    goto LABEL_41;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000f770  mov     [rsp-8+arg_8], rbx
0x18000f775  push    rbp
0x18000f776  push    rsi
0x18000f777  push    rdi
0x18000f778  push    r14
0x18000f77a  push    r15
0x18000f77c  lea     rbp, [rsp-1Fh]
0x18000f781  sub     rsp, 0B0h
0x18000f788  mov     rax, cs:__security_cookie
0x18000f78f  xor     rax, rsp
0x18000f792  mov     [rbp+3Fh+var_30], rax
0x18000f796  mov     rsi, r9
0x18000f799  mov     ebx, r8d
0x18000f79c  mov     r14, rcx
0x18000f79f  mov     rdi, [rbp+3Fh+arg_20]
0x18000f7a3  mov     r15, [rbp+3Fh+arg_30]
0x18000f7a7  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18000f7ab  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x18000f7b0  cmp     ebx, 1
0x18000f7b3  jnz     loc_18000FA4D
0x18000f7b9  test    rsi, rsi
0x18000f7bc  jz      loc_18000FA4D
0x18000f7c2  mov     rdx, [rsi]
0x18000f7c5  test    rdx, rdx
0x18000f7c8  jz      loc_18000FA4D
0x18000f7ce  add     rdx, 2
0x18000f7d2  lea     rcx, [rbp+3Fh+var_90]
0x18000f7d6  call    ?StructToProfile@@YA?AVCProfile@@AEBUWPLDATA@@@Z; StructToProfile(WPLDATA const &)
0x18000f7db  nop
0x18000f7dc  mov     rax, [rdi]
0x18000f7df  sub     rax, qword ptr cs:_GUID_000214e4_0000_0000_c000_000000000046.Data1
0x18000f7e6  jnz     short loc_18000F7F3
0x18000f7e8  mov     rax, [rdi+8]
0x18000f7ec  sub     rax, qword ptr cs:_GUID_000214e4_0000_0000_c000_000000000046.Data4
0x18000f7f3  test    rax, rax
0x18000f7f6  jnz     short loc_18000F866
0x18000f7f8  xor     ebx, ebx
0x18000f7fa  mov     [rbp+3Fh+var_A0], rbx
0x18000f7fe  mov     r14, [r14+98h]
0x18000f805  mov     [rbp+3Fh+var_98], rbx
0x18000f809  lea     rcx, [rbp+3Fh+var_98]
0x18000f80d  call    ?CreateInstance@?$CComObject@VCPreflistContextMenu@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPreflistContextMenu>::CreateInstance(ATL::CComObject<CPreflistContextMenu> * *)
0x18000f812  mov     esi, eax
0x18000f814  test    eax, eax
0x18000f816  js      short loc_18000F858
0x18000f818  mov     rdx, [rbp+3Fh+var_98]; struct IUnknown *
0x18000f81c  test    rdx, rdx
0x18000f81f  jz      short loc_18000F82E
0x18000f821  lea     rcx, [rbp+3Fh+var_A0]; struct IUnknown **
0x18000f825  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000f82a  mov     rbx, [rbp+3Fh+var_A0]
0x18000f82e  lea     rcx, [rbx+68h]; this
0x18000f832  lea     rdx, [rbp+3Fh+var_90]; struct CProfile *
0x18000f836  call    ?Clone@CProfile@@IEAAXAEBV1@@Z; CProfile::Clone(CProfile const &)
0x18000f83b  mov     [rbx+0C0h], r14
0x18000f842  mov     rax, [rbx]
0x18000f845  mov     r8, r15
0x18000f848  mov     rdx, rdi
0x18000f84b  mov     rcx, rbx
0x18000f84e  mov     rax, [rax]
0x18000f851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f856  mov     esi, eax
0x18000f858  lea     rcx, [rbp+3Fh+var_A0]
0x18000f85c  call    ??1?$CComPtrBase@VCUICommand@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CUICommand>::~CComPtrBase<CUICommand>(void)
0x18000f861  jmp     loc_18000FA40
0x18000f866  mov     rax, [rdi]
0x18000f869  sub     rax, qword ptr cs:_GUID_0000010e_0000_0000_c000_000000000046.Data1
0x18000f870  jnz     short loc_18000F87D
0x18000f872  mov     rax, [rdi+8]
0x18000f876  sub     rax, qword ptr cs:_GUID_0000010e_0000_0000_c000_000000000046.Data4
0x18000f87d  test    rax, rax
0x18000f880  jnz     short loc_18000F8A9
0x18000f882  mov     [rsp+0D0h+ppv], r15; ppv
0x18000f887  mov     [rsp+0D0h+riid], rdi; riid
0x18000f88c  xor     r9d, r9d; pdtInner
0x18000f88f  mov     r8, rsi; apidl
0x18000f892  lea     edx, [rax+1]; cidl
0x18000f895  mov     rcx, [r14+90h]; pidlFolder
0x18000f89c  call    cs:__imp_SHCreateDataObject
0x18000f8a2  mov     esi, eax
0x18000f8a4  jmp     loc_18000FA40
0x18000f8a9  mov     rax, [rdi]
0x18000f8ac  sub     rax, qword ptr cs:_GUID_00000122_0000_0000_c000_000000000046.Data1
0x18000f8b3  jnz     short loc_18000F8C0
0x18000f8b5  mov     rax, [rdi+8]
0x18000f8b9  sub     rax, qword ptr cs:_GUID_00000122_0000_0000_c000_000000000046.Data4
0x18000f8c0  test    rax, rax
0x18000f8c3  jnz     short loc_18000F908
0x18000f8c5  mov     [rbp+3Fh+var_A0], rax
0x18000f8c9  lea     r9, [rbp+3Fh+var_A0]
0x18000f8cd  lea     r8, [rbp+3Fh+var_90]
0x18000f8d1  mov     rcx, [r14+90h]; pidl
0x18000f8d8  call    ?CreateTarget@CPreflistDropTarget@@SAJPEFBU_ITEMIDLIST@@AEAV?$CSingletonPtr@VCWlanProfileStore@@@@AEBVCProfile@@AEAV?$CComPtr@VCPreflistDropTarget@@@ATL@@@Z; CPreflistDropTarget::CreateTarget(_ITEMIDLIST const *,CSingletonPtr<CWlanProfileStore> &,CProfile const &,ATL::CComPtr<CPreflistDropTarget> &)
0x18000f8dd  mov     esi, eax
0x18000f8df  test    eax, eax
0x18000f8e1  js      short loc_18000F8FA
0x18000f8e3  mov     rcx, [rbp+3Fh+var_A0]
0x18000f8e7  mov     rax, [rcx]
0x18000f8ea  mov     r8, r15
0x18000f8ed  mov     rdx, rdi
0x18000f8f0  mov     rax, [rax]
0x18000f8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8f8  mov     esi, eax
0x18000f8fa  lea     rcx, [rbp+3Fh+var_A0]
0x18000f8fe  call    ??1?$CComPtrBase@VCUICommand@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CUICommand>::~CComPtrBase<CUICommand>(void)
0x18000f903  jmp     loc_18000FA40
0x18000f908  mov     rax, [rdi]
0x18000f90b  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data1
0x18000f912  jnz     short loc_18000F91F
0x18000f914  mov     rax, [rdi+8]
0x18000f918  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data4
0x18000f91f  test    rax, rax
0x18000f922  jnz     short loc_18000F9A0
0x18000f924  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000f92b  mov     rax, [rcx]
0x18000f92e  lea     rdx, [rbp+3Fh+var_90]
0x18000f932  mov     rax, [rax+70h]
0x18000f936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f93b  cmp     eax, 1
0x18000f93e  jnz     short loc_18000F9A0
0x18000f940  xor     ebx, ebx
0x18000f942  mov     [rbp+3Fh+var_A0], rbx
0x18000f946  mov     [rbp+3Fh+var_98], rbx
0x18000f94a  lea     rcx, [rbp+3Fh+var_98]
0x18000f94e  call    ?CreateInstance@?$CComObject@VCPreflistExtractIcon@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPreflistExtractIcon>::CreateInstance(ATL::CComObject<CPreflistExtractIcon> * *)
0x18000f953  mov     esi, eax
0x18000f955  test    eax, eax
0x18000f957  js      short loc_18000F992
0x18000f959  mov     rdx, [rbp+3Fh+var_98]; struct IUnknown *
0x18000f95d  test    rdx, rdx
0x18000f960  jz      short loc_18000F96F
0x18000f962  lea     rcx, [rbp+3Fh+var_A0]; struct IUnknown **
0x18000f966  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000f96b  mov     rbx, [rbp+3Fh+var_A0]
0x18000f96f  lea     rcx, [rbx+48h]; this
0x18000f973  lea     rdx, [rbp+3Fh+var_90]; struct CProfile *
0x18000f977  call    ?Clone@CProfile@@IEAAXAEBV1@@Z; CProfile::Clone(CProfile const &)
0x18000f97c  mov     rax, [rbx]
0x18000f97f  mov     r8, r15
0x18000f982  mov     rdx, rdi
0x18000f985  mov     rcx, rbx
0x18000f988  mov     rax, [rax]
0x18000f98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f990  mov     esi, eax
0x18000f992  lea     rcx, [rbp+3Fh+var_A0]
0x18000f996  call    ??1?$CComPtrBase@VCUICommand@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CUICommand>::~CComPtrBase<CUICommand>(void)
0x18000f99b  jmp     loc_18000FA40
0x18000f9a0  mov     rax, [rdi]
0x18000f9a3  sub     rax, qword ptr cs:_GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1.Data1
0x18000f9aa  jnz     short loc_18000F9B7
0x18000f9ac  mov     rax, [rdi+8]
0x18000f9b0  sub     rax, qword ptr cs:_GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1.Data4
0x18000f9b7  test    rax, rax
0x18000f9ba  jnz     short loc_18000FA34
0x18000f9bc  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000f9c3  mov     rax, [rcx]
0x18000f9c6  lea     rdx, [rbp+3Fh+var_90]
0x18000f9ca  mov     rax, [rax+70h]
0x18000f9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9d3  test    eax, eax
0x18000f9d5  jnz     short loc_18000FA34
0x18000f9d7  xor     ebx, ebx
0x18000f9d9  mov     [rbp+3Fh+var_A0], rbx
0x18000f9dd  mov     [rbp+3Fh+var_98], rbx
0x18000f9e1  lea     rcx, [rbp+3Fh+var_98]
0x18000f9e5  call    ?CreateInstance@?$CComObject@VCPreflistExtractImage@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPreflistExtractImage>::CreateInstance(ATL::CComObject<CPreflistExtractImage> * *)
0x18000f9ea  mov     esi, eax
0x18000f9ec  test    eax, eax
0x18000f9ee  js      short loc_18000FA29
0x18000f9f0  mov     rdx, [rbp+3Fh+var_98]; struct IUnknown *
0x18000f9f4  test    rdx, rdx
0x18000f9f7  jz      short loc_18000FA06
0x18000f9f9  lea     rcx, [rbp+3Fh+var_A0]; struct IUnknown **
0x18000f9fd  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000fa02  mov     rbx, [rbp+3Fh+var_A0]
0x18000fa06  lea     rcx, [rbx+50h]; this
0x18000fa0a  lea     rdx, [rbp+3Fh+var_90]; struct CProfile *
0x18000fa0e  call    ?Clone@CProfile@@IEAAXAEBV1@@Z; CProfile::Clone(CProfile const &)
0x18000fa13  mov     rax, [rbx]
0x18000fa16  mov     r8, r15
0x18000fa19  mov     rdx, rdi
0x18000fa1c  mov     rcx, rbx
0x18000fa1f  mov     rax, [rax]
0x18000fa22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa27  mov     esi, eax
0x18000fa29  lea     rcx, [rbp+3Fh+var_A0]
0x18000fa2d  call    ??1?$CComPtrBase@VCUICommand@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CUICommand>::~CComPtrBase<CUICommand>(void)
0x18000fa32  jmp     short loc_18000FA40
0x18000fa34  mov     qword ptr [r15], 0
0x18000fa3b  mov     esi, 80004002h
0x18000fa40  lea     rcx, [rbp+3Fh+var_90]; this
0x18000fa44  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x18000fa49  mov     eax, esi
0x18000fa4b  jmp     short loc_18000FA52
0x18000fa4d  mov     eax, 80070057h
0x18000fa52  mov     rcx, [rbp+3Fh+var_30]
0x18000fa56  xor     rcx, rsp; StackCookie
0x18000fa59  call    __security_check_cookie
0x18000fa5e  mov     rbx, [rsp+0D0h+arg_8]
0x18000fa66  add     rsp, 0B0h
0x18000fa6d  pop     r15
0x18000fa6f  pop     r14
0x18000fa71  pop     rdi
0x18000fa72  pop     rsi
0x18000fa73  pop     rbp
0x18000fa74  retn
```
