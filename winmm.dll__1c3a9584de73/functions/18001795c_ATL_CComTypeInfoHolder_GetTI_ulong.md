# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18001795c`
- end: `0x180017c26`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `714`
- prototype: `int(ATL::CComTypeInfoHolder *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016da4`
- `0x180017de0`

## callees

- `0x18000c990`
- `0x180016600`
- `0x180016630`
- `0x180016668`
- `0x180016ab4`
- `0x18001795c`
- `0x180017f04`
- `0x180017f98`
- `0x1800181e8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017a51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017a51`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180017a7a`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180017a7a`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180017a9b`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180017a9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID a2)
{
  ATL::CComTypeInfoHolder *v4; // rcx
  HRESULT NameCache; // ebx
  DWORD ModuleFileNameW; // eax
  int (__fastcall ***v7)(_QWORD, GUID *, _QWORD); // rcx
  unsigned __int64 v8; // r8
  struct ITypeInfo *v9; // rdi
  struct ITypeInfo *v10; // rax
  struct ITypeInfo *v11; // [rsp+30h] [rbp-D0h] BYREF
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD); // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v13)(_QWORD, GUID *, struct ITypeInfo **); // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+48h] [rbp-B8h] BYREF
  char *v15; // [rsp+50h] [rbp-B0h] BYREF
  char v16; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( qword_180025078 && qword_180025088 )
    return 0;
  v15 = (char *)ATL::_pAtlModule + 24;
  v16 = 0;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v15);
  if ( NameCache >= 0 )
  {
    if ( qword_180025078 )
    {
      NameCache = 0;
    }
    else
    {
      pptlib = 0;
      if ( ATL::CAtlModule::m_libid.Data1 != rguid->Data1
        || *(_DWORD *)&ATL::CAtlModule::m_libid.Data2 != *(_DWORD *)&rguid->Data2
        || *(_DWORD *)ATL::CAtlModule::m_libid.Data4 != *(_DWORD *)rguid->Data4
        || *(_DWORD *)&ATL::CAtlModule::m_libid.Data4[4] != *(_DWORD *)&rguid->Data4[4]
        || *(_DWORD *)&wVerMajor != -1 )
      {
        NameCache = LoadRegTypeLib(rguid, wVerMajor, *(&wVerMajor + 1), a2, &pptlib);
LABEL_15:
        if ( NameCache >= 0 )
        {
          v12 = 0;
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        ATL::IDispatchImpl<IAccessible,&_GUID const IID_IAccessible,&_GUID const LIBID_Accessibility,1,1,ATL::CComTypeInfoHolder>::_tih[0],
                        &v12);
          if ( NameCache >= 0 )
          {
            v7 = v12;
            v11 = (struct ITypeInfo *)v12;
            if ( v12 )
            {
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v12)[1])(v12);
              v7 = v12;
            }
            v13 = 0;
            if ( (**v7)(v7, &GUID_00020412_0000_0000_c000_000000000046, &v13) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v11, v13) )
            {
              v9 = v11;
              v11 = 0;
              if ( v13 )
                (**v13)(v13, &GUID_00020401_0000_0000_c000_000000000046, &v11);
              if ( v9 )
                ((void (__fastcall *)(struct ITypeInfo *))v9->lpVtbl->Release)(v9);
            }
            v10 = v11;
            v11 = 0;
            qword_180025078 = v10;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0)),
              (void (*)(unsigned __int64))((char *)ATL::_pAtlModule + 8),
              v8);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
        }
        goto LABEL_28;
      }
      NameCache = -2147467259;
      ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
      if ( ModuleFileNameW && ModuleFileNameW != 260 )
      {
        v12 = 0;
        NameCache = LoadTypeLib(Filename, &pptlib);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v12);
        goto LABEL_15;
      }
    }
LABEL_28:
    if ( qword_180025078 )
    {
      if ( !qword_180025088 )
        NameCache = ATL::CComTypeInfoHolder::LoadNameCache(v4, qword_180025078);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v15);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x18001795c  mov     [rsp-8+arg_0], rbx
0x180017961  mov     [rsp-8+arg_10], rdi
0x180017966  push    rbp
0x180017967  lea     rbp, [rsp-180h]
0x18001796f  sub     rsp, 280h
0x180017976  mov     rax, cs:__security_cookie
0x18001797d  xor     rax, rsp
0x180017980  mov     [rbp+180h+var_10], rax
0x180017987  mov     edi, edx
0x180017989  cmp     cs:qword_180025078, 0
0x180017991  jz      short loc_1800179A4
0x180017993  cmp     cs:qword_180025088, 0
0x18001799b  jz      short loc_1800179A4
0x18001799d  xor     eax, eax
0x18001799f  jmp     loc_180017C02
0x1800179a4  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800179ab  add     rax, 18h
0x1800179af  mov     [rsp+280h+var_230], rax
0x1800179b4  mov     [rsp+280h+var_228], 0
0x1800179b9  lea     rcx, [rsp+280h+var_230]
0x1800179be  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800179c3  mov     ebx, eax
0x1800179c5  test    eax, eax
0x1800179c7  js      loc_180017BF6
0x1800179cd  cmp     cs:qword_180025078, 0
0x1800179d5  jnz     loc_180017BD7
0x1800179db  mov     [rsp+280h+pptlib], 0
0x1800179e4  mov     r8, cs:wVerMajor+2; wVerMinor
0x1800179eb  mov     rdx, cs:wVerMajor; wVerMajor
0x1800179f2  mov     rcx, cs:rguid; rguid
0x1800179f9  mov     eax, [rcx]
0x1800179fb  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x180017a01  jnz     loc_180017A8E
0x180017a07  mov     eax, [rcx+4]
0x180017a0a  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x180017a10  jnz     short loc_180017A8E
0x180017a12  mov     eax, [rcx+8]
0x180017a15  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180017a1b  jnz     short loc_180017A8E
0x180017a1d  mov     eax, [rcx+0Ch]
0x180017a20  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180017a26  jnz     short loc_180017A8E
0x180017a28  mov     eax, 0FFFFh
0x180017a2d  cmp     dx, ax
0x180017a30  jnz     short loc_180017A8E
0x180017a32  cmp     r8w, ax
0x180017a36  jnz     short loc_180017A8E
0x180017a38  mov     ebx, 80004005h
0x180017a3d  mov     edi, 104h
0x180017a42  mov     r8d, edi; nSize
0x180017a45  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180017a4a  mov     rcx, cs:hModule; hModule
0x180017a51  call    cs:__imp_GetModuleFileNameW
0x180017a57  test    eax, eax
0x180017a59  jz      loc_180017BD9
0x180017a5f  cmp     eax, edi
0x180017a61  jz      loc_180017BD9
0x180017a67  mov     [rsp+280h+var_248], 0
0x180017a70  lea     rdx, [rsp+280h+pptlib]; pptlib
0x180017a75  lea     rcx, [rsp+280h+Filename]; szFile
0x180017a7a  call    cs:__imp_LoadTypeLib
0x180017a80  mov     ebx, eax
0x180017a82  lea     rcx, [rsp+280h+var_248]
0x180017a87  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017a8c  jmp     short loc_180017AA3
0x180017a8e  lea     rax, [rsp+280h+pptlib]
0x180017a93  mov     [rsp+280h+var_260], rax; pptlib
0x180017a98  mov     r9d, edi; lcid
0x180017a9b  call    cs:__imp_LoadRegTypeLib
0x180017aa1  mov     ebx, eax
0x180017aa3  test    ebx, ebx
0x180017aa5  js      loc_180017BD9
0x180017aab  mov     [rsp+280h+var_248], 0
0x180017ab4  mov     rcx, [rsp+280h+pptlib]
0x180017ab9  mov     rax, [rcx]
0x180017abc  lea     r8, [rsp+280h+var_248]
0x180017ac1  mov     rdx, cs:?_tih@?$IDispatchImpl@UIAccessible@@$1?IID_IAccessible@@3U_GUID@@B$1?LIBID_Accessibility@@3U3@B$00$00VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<IAccessible,&_GUID const IID_IAccessible,&_GUID const LIBID_Accessibility,1,1,ATL::CComTypeInfoHolder>::_tih
0x180017ac8  mov     rax, [rax+30h]
0x180017acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ad1  mov     ebx, eax
0x180017ad3  test    eax, eax
0x180017ad5  js      loc_180017BB9
0x180017adb  mov     rcx, [rsp+280h+var_248]
0x180017ae0  mov     [rsp+280h+var_250], rcx
0x180017ae5  test    rcx, rcx
0x180017ae8  jz      short loc_180017AFB
0x180017aea  mov     rax, [rcx]
0x180017aed  mov     rax, [rax+8]
0x180017af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017af6  mov     rcx, [rsp+280h+var_248]
0x180017afb  mov     [rsp+280h+var_240], 0
0x180017b04  mov     rax, [rcx]
0x180017b07  lea     r8, [rsp+280h+var_240]
0x180017b0c  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180017b13  mov     rax, [rax]
0x180017b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b1b  test    eax, eax
0x180017b1d  js      short loc_180017B75
0x180017b1f  mov     rdx, [rsp+280h+var_240]
0x180017b24  lea     rcx, [rsp+280h+var_250]
0x180017b29  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x180017b2e  test    al, al
0x180017b30  jnz     short loc_180017B75
0x180017b32  mov     rcx, [rsp+280h+var_240]
0x180017b37  mov     rdi, [rsp+280h+var_250]
0x180017b3c  mov     [rsp+280h+var_250], 0
0x180017b45  test    rcx, rcx
0x180017b48  jz      short loc_180017B61
0x180017b4a  mov     rax, [rcx]
0x180017b4d  lea     r8, [rsp+280h+var_250]
0x180017b52  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x180017b59  mov     rax, [rax]
0x180017b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b61  test    rdi, rdi
0x180017b64  jz      short loc_180017B75
0x180017b66  mov     rax, [rdi]
0x180017b69  mov     rcx, rdi
0x180017b6c  mov     rax, [rax+10h]
0x180017b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b75  mov     rax, [rsp+280h+var_250]
0x180017b7a  mov     [rsp+280h+var_250], 0
0x180017b83  mov     cs:qword_180025078, rax
0x180017b8a  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180017b91  lea     rdx, [rax+8]; void (*)(unsigned __int64)
0x180017b95  neg     rax
0x180017b98  sbb     rcx, rcx
0x180017b9b  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180017b9e  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180017ba3  nop
0x180017ba4  lea     rcx, [rsp+280h+var_240]
0x180017ba9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017bae  nop
0x180017baf  lea     rcx, [rsp+280h+var_250]
0x180017bb4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017bb9  mov     rcx, [rsp+280h+pptlib]
0x180017bbe  mov     rax, [rcx]
0x180017bc1  mov     rax, [rax+10h]
0x180017bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bca  nop
0x180017bcb  lea     rcx, [rsp+280h+var_248]
0x180017bd0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017bd5  jmp     short loc_180017BD9
0x180017bd7  xor     ebx, ebx
0x180017bd9  mov     rdx, cs:qword_180025078; struct ITypeInfo *
0x180017be0  test    rdx, rdx
0x180017be3  jz      short loc_180017BF6
0x180017be5  cmp     cs:qword_180025088, 0
0x180017bed  jnz     short loc_180017BF6
0x180017bef  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180017bf4  mov     ebx, eax
0x180017bf6  lea     rcx, [rsp+280h+var_230]
0x180017bfb  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180017c00  mov     eax, ebx
0x180017c02  mov     rcx, [rbp+180h+var_10]
0x180017c09  xor     rcx, rsp; StackCookie
0x180017c0c  call    __security_check_cookie
0x180017c11  lea     r11, [rsp+280h+var_s0]
0x180017c19  mov     rbx, [r11+10h]
0x180017c1d  mov     rdi, [r11+20h]
0x180017c21  mov     rsp, r11
0x180017c24  pop     rbp
0x180017c25  retn
```
