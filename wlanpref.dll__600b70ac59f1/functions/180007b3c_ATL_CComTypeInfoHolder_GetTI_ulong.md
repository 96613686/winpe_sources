# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180007b3c`
- end: `0x180007ded`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `689`
- prototype: `int(ATL::CComTypeInfoHolder *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007744`
- `0x180007e00`

## callees

- `0x180002cc0`
- `0x180003014`
- `0x180003458`
- `0x180004f00`
- `0x180007b3c`
- `0x1800080c4`
- `0x1800081a4`
- `0x180008238`
- `0x180008560`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLib` at `0x180007c3e`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180007c3e`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180007c62`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180007c62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180007c15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180007c15`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID a2)
{
  ATL::CComTypeInfoHolder *v4; // rcx
  HRESULT NameCache; // ebx
  const GUID *v6; // r10
  DWORD ModuleFileNameW; // eax
  struct ITypeInfo *v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // rdi
  struct ITypeInfo *v11; // rax
  struct ITypeInfo *v12; // [rsp+30h] [rbp-D0h] BYREF
  struct ITypeInfo *v13; // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v14)(_QWORD, GUID *, struct ITypeInfo **); // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+48h] [rbp-B8h] BYREF
  char *v16; // [rsp+50h] [rbp-B0h] BYREF
  char v17; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( qword_18003F538 && qword_18003F548 )
    return 0;
  v16 = (char *)ATL::_pAtlModule + 24;
  v17 = 0;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v16);
  if ( NameCache >= 0 )
  {
    if ( qword_18003F538 )
    {
      NameCache = 0;
    }
    else
    {
      pptlib = 0;
      if ( !(unsigned int)InlineIsEqualGUID(&ATL::CAtlModule::m_libid, off_18003F528) || *(_DWORD *)&wVerMajor != -1 )
      {
        NameCache = LoadRegTypeLib(v6, wVerMajor, *(&wVerMajor + 1), a2, &pptlib);
LABEL_12:
        if ( NameCache >= 0 )
        {
          v13 = 0;
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, GUID *, struct ITypeInfo **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        ATL::IDispatchImpl<IWlanPrefLUA,&_GUID const IID_IWlanPrefLUA,&_GUID const LIBID_WlanPrefLUALib,1,0,ATL::CComTypeInfoHolder>::_tih[0],
                        &v13);
          if ( NameCache >= 0 )
          {
            v8 = v13;
            v12 = v13;
            if ( v13 )
            {
              ((void (__fastcall *)(struct ITypeInfo *))v13->lpVtbl->AddRef)(v13);
              v8 = v13;
            }
            v14 = 0;
            if ( ((__int64 (__fastcall *)(struct ITypeInfo *, GUID *, _QWORD))v8->lpVtbl->QueryInterface)(
                   v8,
                   &GUID_00020412_0000_0000_c000_000000000046,
                   &v14) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v12, v14) )
            {
              v10 = (__int64)v12;
              v12 = 0;
              if ( v14 )
                (**v14)(v14, &GUID_00020401_0000_0000_c000_000000000046, &v12);
              if ( v10 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            }
            v11 = v12;
            v12 = 0;
            qword_18003F538 = v11;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0)),
              (void (*)(unsigned __int64))((char *)ATL::_pAtlModule + 8),
              v9);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
        }
        goto LABEL_25;
      }
      NameCache = -2147467259;
      ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
      if ( ModuleFileNameW && ModuleFileNameW != 260 )
      {
        v13 = 0;
        NameCache = LoadTypeLib(Filename, &pptlib);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v13);
        goto LABEL_12;
      }
    }
LABEL_25:
    if ( qword_18003F538 )
    {
      if ( !qword_18003F548 )
        NameCache = ATL::CComTypeInfoHolder::LoadNameCache(v4, qword_18003F538);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v16);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x180007b3c  mov     [rsp-8+arg_0], rbx
0x180007b41  mov     [rsp-8+arg_10], rdi
0x180007b46  push    rbp
0x180007b47  lea     rbp, [rsp-180h]
0x180007b4f  sub     rsp, 280h
0x180007b56  mov     rax, cs:__security_cookie
0x180007b5d  xor     rax, rsp
0x180007b60  mov     [rbp+180h+var_10], rax
0x180007b67  mov     edi, edx
0x180007b69  cmp     cs:qword_18003F538, 0
0x180007b71  jz      short loc_180007B84
0x180007b73  cmp     cs:qword_18003F548, 0
0x180007b7b  jz      short loc_180007B84
0x180007b7d  xor     eax, eax
0x180007b7f  jmp     loc_180007DC9
0x180007b84  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b8b  add     rax, 18h
0x180007b8f  mov     [rsp+280h+var_230], rax
0x180007b94  mov     [rsp+280h+var_228], 0
0x180007b99  lea     rcx, [rsp+280h+var_230]
0x180007b9e  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180007ba3  mov     ebx, eax
0x180007ba5  test    eax, eax
0x180007ba7  js      loc_180007DBD
0x180007bad  cmp     cs:qword_18003F538, 0
0x180007bb5  jnz     loc_180007D9E
0x180007bbb  mov     [rsp+280h+pptlib], 0
0x180007bc4  mov     r10, cs:off_18003F528
0x180007bcb  mov     rdx, r10; struct _GUID *
0x180007bce  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; struct _GUID *
0x180007bd5  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180007bda  mov     r8, cs:wVerMajor+2; wVerMinor
0x180007be1  mov     rdx, cs:wVerMajor; wVerMajor
0x180007be8  test    eax, eax
0x180007bea  jz      short loc_180007C52
0x180007bec  mov     eax, 0FFFFh
0x180007bf1  cmp     dx, ax
0x180007bf4  jnz     short loc_180007C52
0x180007bf6  cmp     r8w, ax
0x180007bfa  jnz     short loc_180007C52
0x180007bfc  mov     ebx, 80004005h
0x180007c01  mov     edi, 104h
0x180007c06  mov     r8d, edi; nSize
0x180007c09  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180007c0e  mov     rcx, cs:hModule; hModule
0x180007c15  call    cs:__imp_GetModuleFileNameW
0x180007c1b  test    eax, eax
0x180007c1d  jz      loc_180007DA0
0x180007c23  cmp     eax, edi
0x180007c25  jz      loc_180007DA0
0x180007c2b  mov     [rsp+280h+var_248], 0
0x180007c34  lea     rdx, [rsp+280h+pptlib]; pptlib
0x180007c39  lea     rcx, [rsp+280h+Filename]; szFile
0x180007c3e  call    cs:__imp_LoadTypeLib
0x180007c44  mov     ebx, eax
0x180007c46  lea     rcx, [rsp+280h+var_248]
0x180007c4b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007c50  jmp     short loc_180007C6A
0x180007c52  lea     rax, [rsp+280h+pptlib]
0x180007c57  mov     [rsp+280h+var_260], rax; pptlib
0x180007c5c  mov     r9d, edi; lcid
0x180007c5f  mov     rcx, r10; rguid
0x180007c62  call    cs:__imp_LoadRegTypeLib
0x180007c68  mov     ebx, eax
0x180007c6a  test    ebx, ebx
0x180007c6c  js      loc_180007DA0
0x180007c72  mov     [rsp+280h+var_248], 0
0x180007c7b  mov     rcx, [rsp+280h+pptlib]
0x180007c80  mov     rax, [rcx]
0x180007c83  lea     r8, [rsp+280h+var_248]
0x180007c88  mov     rdx, cs:?_tih@?$IDispatchImpl@UIWlanPrefLUA@@$1?IID_IWlanPrefLUA@@3U_GUID@@B$1?LIBID_WlanPrefLUALib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<IWlanPrefLUA,&_GUID const IID_IWlanPrefLUA,&_GUID const LIBID_WlanPrefLUALib,1,0,ATL::CComTypeInfoHolder>::_tih
0x180007c8f  mov     rax, [rax+30h]
0x180007c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c98  mov     ebx, eax
0x180007c9a  test    eax, eax
0x180007c9c  js      loc_180007D80
0x180007ca2  mov     rcx, [rsp+280h+var_248]
0x180007ca7  mov     [rsp+280h+var_250], rcx
0x180007cac  test    rcx, rcx
0x180007caf  jz      short loc_180007CC2
0x180007cb1  mov     rax, [rcx]
0x180007cb4  mov     rax, [rax+8]
0x180007cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cbd  mov     rcx, [rsp+280h+var_248]
0x180007cc2  mov     [rsp+280h+var_240], 0
0x180007ccb  mov     rax, [rcx]
0x180007cce  lea     r8, [rsp+280h+var_240]
0x180007cd3  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180007cda  mov     rax, [rax]
0x180007cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce2  test    eax, eax
0x180007ce4  js      short loc_180007D3C
0x180007ce6  mov     rdx, [rsp+280h+var_240]
0x180007ceb  lea     rcx, [rsp+280h+var_250]
0x180007cf0  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x180007cf5  test    al, al
0x180007cf7  jnz     short loc_180007D3C
0x180007cf9  mov     rcx, [rsp+280h+var_240]
0x180007cfe  mov     rdi, [rsp+280h+var_250]
0x180007d03  mov     [rsp+280h+var_250], 0
0x180007d0c  test    rcx, rcx
0x180007d0f  jz      short loc_180007D28
0x180007d11  mov     rax, [rcx]
0x180007d14  lea     r8, [rsp+280h+var_250]
0x180007d19  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x180007d20  mov     rax, [rax]
0x180007d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d28  test    rdi, rdi
0x180007d2b  jz      short loc_180007D3C
0x180007d2d  mov     rax, [rdi]
0x180007d30  mov     rcx, rdi
0x180007d33  mov     rax, [rax+10h]
0x180007d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d3c  mov     rax, [rsp+280h+var_250]
0x180007d41  mov     [rsp+280h+var_250], 0
0x180007d4a  mov     cs:qword_18003F538, rax
0x180007d51  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007d58  lea     rdx, [rax+8]; void (*)(unsigned __int64)
0x180007d5c  neg     rax
0x180007d5f  sbb     rcx, rcx
0x180007d62  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180007d65  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180007d6a  nop
0x180007d6b  lea     rcx, [rsp+280h+var_240]
0x180007d70  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007d75  nop
0x180007d76  lea     rcx, [rsp+280h+var_250]
0x180007d7b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007d80  mov     rcx, [rsp+280h+pptlib]
0x180007d85  mov     rax, [rcx]
0x180007d88  mov     rax, [rax+10h]
0x180007d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d91  nop
0x180007d92  lea     rcx, [rsp+280h+var_248]
0x180007d97  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007d9c  jmp     short loc_180007DA0
0x180007d9e  xor     ebx, ebx
0x180007da0  mov     rdx, cs:qword_18003F538; struct ITypeInfo *
0x180007da7  test    rdx, rdx
0x180007daa  jz      short loc_180007DBD
0x180007dac  cmp     cs:qword_18003F548, 0
0x180007db4  jnz     short loc_180007DBD
0x180007db6  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180007dbb  mov     ebx, eax
0x180007dbd  lea     rcx, [rsp+280h+var_230]
0x180007dc2  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180007dc7  mov     eax, ebx
0x180007dc9  mov     rcx, [rbp+180h+var_10]
0x180007dd0  xor     rcx, rsp; StackCookie
0x180007dd3  call    __security_check_cookie
0x180007dd8  lea     r11, [rsp+280h+var_s0]
0x180007de0  mov     rbx, [r11+10h]
0x180007de4  mov     rdi, [r11+20h]
0x180007de8  mov     rsp, r11
0x180007deb  pop     rbp
0x180007dec  retn
```
