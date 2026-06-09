# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180038c08`
- end: `0x180038e4f`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `583`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `7`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180033198`
- `0x180033620`
- `0x180034b10`
- `0x180035590`
- `0x180035640`
- `0x1800356f0`
- `0x180038b98`

## callees

- `0x1800017f0`
- `0x180028a50`
- `0x180037164`
- `0x180038c08`
- `0x1800399e4`
- `0x18003c0d8`
- `0x18003cd34`
- `0x18003cf9c`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038c5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038c5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180038cb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180038cb8`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180038ce4`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180038ce4`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180038d12`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180038d12`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  DWORD ModuleFileNameW; // eax
  int (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v8; // rax
  struct ITypeInfo *v9; // rdx
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  int (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // [rsp+38h] [rbp-C8h] BYREF
  ITypeLib *pptlib; // [rsp+40h] [rbp-C0h] BYREF
  int (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  char *v14; // [rsp+50h] [rbp-B0h] BYREF
  char v15; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v14 = (char *)ATL::_pAtlModule + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v15 = 1;
  if ( *((_QWORD *)this + 3) )
  {
    NameCache = 0;
  }
  else
  {
    pptlib = 0;
    if ( !(unsigned int)InlineIsEqualGUID(&ATL::CAtlModule::m_libid, *((const struct _GUID **)this + 1))
      || *((_WORD *)this + 8) != 0xFFFF
      || *((_WORD *)this + 9) != 0xFFFF )
    {
      NameCache = LoadRegTypeLib(
                    *((const GUID *const *)this + 1),
                    *((_WORD *)this + 8),
                    *((_WORD *)this + 9),
                    lcid,
                    &pptlib);
LABEL_12:
      if ( NameCache >= 0 )
      {
        v13 = 0;
        NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                      pptlib,
                      *(_QWORD *)this,
                      &v13);
        if ( NameCache >= 0 )
        {
          v7 = v13;
          v11 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v13;
          if ( v13 )
          {
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v13)[1])(v13);
            v7 = v13;
          }
          v10 = 0;
          if ( (**v7)(v7, &GUID_00020412_0000_0000_c000_000000000046, &v10) >= 0 )
            ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(&v11, &v10);
          v8 = (__int64)v11;
          v11 = 0;
          *((_QWORD *)this + 3) = v8;
          ATL::AtlModuleAddTermFunc(
            (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                        & ((unsigned __int64)ATL::_pAtlModule + 8)),
            (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
            (unsigned __int64)this);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
        }
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
      }
      goto LABEL_21;
    }
    NameCache = -2147467259;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW && ModuleFileNameW != 260 )
    {
      v10 = 0;
      NameCache = LoadTypeLib(Filename, &pptlib);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v10);
      goto LABEL_12;
    }
  }
LABEL_21:
  v9 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( v9 )
  {
    if ( !*((_QWORD *)this + 5) )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v9);
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v14);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x180038c08  mov     [rsp-8+arg_10], rbx
0x180038c0d  mov     [rsp-8+arg_18], rdi
0x180038c12  push    rbp
0x180038c13  lea     rbp, [rsp-180h]
0x180038c1b  sub     rsp, 280h
0x180038c22  mov     rax, cs:__security_cookie
0x180038c29  xor     rax, rsp
0x180038c2c  mov     [rbp+180h+var_10], rax
0x180038c33  mov     edi, edx
0x180038c35  mov     rbx, rcx
0x180038c38  cmp     qword ptr [rcx+18h], 0
0x180038c3d  jz      short loc_180038C4D
0x180038c3f  cmp     qword ptr [rcx+28h], 0
0x180038c44  jz      short loc_180038C4D
0x180038c46  xor     eax, eax
0x180038c48  jmp     loc_180038E2B
0x180038c4d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180038c54  add     rcx, 18h; lpCriticalSection
0x180038c58  mov     [rsp+280h+var_230], rcx
0x180038c5d  call    cs:__imp_EnterCriticalSection
0x180038c63  mov     [rsp+280h+var_228], 1
0x180038c68  cmp     qword ptr [rbx+18h], 0
0x180038c6d  jnz     loc_180038E03
0x180038c73  mov     [rsp+280h+pptlib], 0
0x180038c7c  mov     rdx, [rbx+8]; struct _GUID *
0x180038c80  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; struct _GUID *
0x180038c87  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180038c8c  test    eax, eax
0x180038c8e  jz      short loc_180038CF8
0x180038c90  mov     eax, 0FFFFh
0x180038c95  cmp     [rbx+10h], ax
0x180038c99  jnz     short loc_180038CF8
0x180038c9b  cmp     [rbx+12h], ax
0x180038c9f  jnz     short loc_180038CF8
0x180038ca1  mov     edi, 80004005h
0x180038ca6  mov     r8d, 104h; nSize
0x180038cac  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180038cb1  mov     rcx, cs:hModule; hModule
0x180038cb8  call    cs:__imp_GetModuleFileNameW
0x180038cbe  test    eax, eax
0x180038cc0  jz      loc_180038E05
0x180038cc6  cmp     eax, 104h
0x180038ccb  jz      loc_180038E05
0x180038cd1  mov     [rsp+280h+var_250], 0
0x180038cda  lea     rdx, [rsp+280h+pptlib]; pptlib
0x180038cdf  lea     rcx, [rsp+280h+Filename]; szFile
0x180038ce4  call    cs:__imp_LoadTypeLib
0x180038cea  mov     edi, eax
0x180038cec  lea     rcx, [rsp+280h+var_250]
0x180038cf1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180038cf6  jmp     short loc_180038D1A
0x180038cf8  lea     rax, [rsp+280h+pptlib]
0x180038cfd  mov     [rsp+280h+var_260], rax; pptlib
0x180038d02  mov     r9d, edi; lcid
0x180038d05  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180038d0a  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x180038d0e  mov     rcx, [rbx+8]; rguid
0x180038d12  call    cs:__imp_LoadRegTypeLib
0x180038d18  mov     edi, eax
0x180038d1a  test    edi, edi
0x180038d1c  js      loc_180038E05
0x180038d22  mov     [rsp+280h+var_238], 0
0x180038d2b  mov     rcx, [rsp+280h+pptlib]
0x180038d30  mov     rax, [rcx]
0x180038d33  lea     r8, [rsp+280h+var_238]
0x180038d38  mov     rdx, [rbx]
0x180038d3b  mov     rax, [rax+30h]
0x180038d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d44  mov     edi, eax
0x180038d46  test    eax, eax
0x180038d48  js      loc_180038DE5
0x180038d4e  mov     rcx, [rsp+280h+var_238]
0x180038d53  mov     [rsp+280h+var_248], rcx
0x180038d58  test    rcx, rcx
0x180038d5b  jz      short loc_180038D6E
0x180038d5d  mov     rax, [rcx]
0x180038d60  mov     rax, [rax+8]
0x180038d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d69  mov     rcx, [rsp+280h+var_238]
0x180038d6e  mov     [rsp+280h+var_250], 0
0x180038d77  mov     rax, [rcx]
0x180038d7a  lea     r8, [rsp+280h+var_250]
0x180038d7f  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180038d86  mov     rax, [rax]
0x180038d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d8e  test    eax, eax
0x180038d90  js      short loc_180038DA1
0x180038d92  lea     rdx, [rsp+280h+var_250]
0x180038d97  lea     rcx, [rsp+280h+var_248]
0x180038d9c  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x180038da1  mov     rax, [rsp+280h+var_248]
0x180038da6  mov     [rsp+280h+var_248], 0
0x180038daf  mov     [rbx+18h], rax
0x180038db3  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180038dba  lea     rcx, [rax+8]
0x180038dbe  neg     rax
0x180038dc1  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180038dc4  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180038dc7  mov     r8, rbx; unsigned __int64
0x180038dca  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180038dcf  nop
0x180038dd0  lea     rcx, [rsp+280h+var_250]
0x180038dd5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038dda  nop
0x180038ddb  lea     rcx, [rsp+280h+var_248]
0x180038de0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038de5  mov     rcx, [rsp+280h+pptlib]
0x180038dea  mov     rax, [rcx]
0x180038ded  mov     rax, [rax+10h]
0x180038df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038df6  nop
0x180038df7  lea     rcx, [rsp+280h+var_238]
0x180038dfc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180038e01  jmp     short loc_180038E05
0x180038e03  xor     edi, edi
0x180038e05  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180038e09  test    rdx, rdx
0x180038e0c  jz      short loc_180038E1F
0x180038e0e  cmp     qword ptr [rbx+28h], 0
0x180038e13  jnz     short loc_180038E1F
0x180038e15  mov     rcx, rbx; this
0x180038e18  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180038e1d  mov     edi, eax
0x180038e1f  lea     rcx, [rsp+280h+var_230]
0x180038e24  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180038e29  mov     eax, edi
0x180038e2b  mov     rcx, [rbp+180h+var_10]
0x180038e32  xor     rcx, rsp; StackCookie
0x180038e35  call    __security_check_cookie
0x180038e3a  lea     r11, [rsp+280h+var_s0]
0x180038e42  mov     rbx, [r11+20h]
0x180038e46  mov     rdi, [r11+28h]
0x180038e4a  mov     rsp, r11
0x180038e4d  pop     rbp
0x180038e4e  retn
```
