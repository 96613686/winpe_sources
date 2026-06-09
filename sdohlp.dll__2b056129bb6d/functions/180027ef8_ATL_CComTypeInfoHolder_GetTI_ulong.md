# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180027ef8`
- end: `0x18002818e`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `662`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180027d74`
- `0x1800282f4`
- `0x1800296a8`

## callees

- `0x180024850`
- `0x1800248a8`
- `0x180024cac`
- `0x1800262bc`
- `0x180027ef8`
- `0x18002974c`
- `0x1800297e0`
- `0x180029a4c`
- `0x18002cc74`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180027fb5`
- `KERNEL32!GetModuleFileNameW` at `0x180027fb5`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180027fde`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180027fde`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18002800c`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18002800c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  DWORD ModuleFileNameW; // eax
  int (__fastcall ***v7)(_QWORD, GUID *, _QWORD); // rcx
  __int64 v8; // rsi
  __int64 v9; // rax
  struct ITypeInfo *v10; // rdx
  int (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // [rsp+30h] [rbp-D0h] BYREF
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD); // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+48h] [rbp-B8h] BYREF
  char *v15; // [rsp+50h] [rbp-B0h] BYREF
  char v16; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v15 = (char *)ATL::_pAtlModule + 24;
  v16 = 0;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v15);
  if ( NameCache >= 0 )
  {
    if ( *((_QWORD *)this + 3) )
    {
      NameCache = 0;
    }
    else
    {
      pptlib = 0;
      if ( !(unsigned int)InlineIsEqualGUID(&ATL::CAtlModule::m_libid, *((_QWORD *)this + 1))
        || *((_WORD *)this + 8) != 0xFFFF
        || *((_WORD *)this + 9) != 0xFFFF )
      {
        NameCache = LoadRegTypeLib(
                      *((const GUID *const *)this + 1),
                      *((_WORD *)this + 8),
                      *((_WORD *)this + 9),
                      lcid,
                      &pptlib);
LABEL_13:
        if ( NameCache >= 0 )
        {
          v12 = 0;
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        *(_QWORD *)this,
                        &v12);
          if ( NameCache >= 0 )
          {
            v7 = v12;
            v11 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v12;
            if ( v12 )
            {
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v12)[1])(v12);
              v7 = v12;
            }
            v13 = 0;
            if ( (**v7)(v7, &GUID_00020412_0000_0000_c000_000000000046, &v13) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v11, v13) )
            {
              v8 = (__int64)v11;
              v11 = 0;
              if ( v13 )
                (**v13)(v13, &GUID_00020401_0000_0000_c000_000000000046, (__int64 *)&v11);
              if ( v8 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            }
            v9 = (__int64)v11;
            v11 = 0;
            *((_QWORD *)this + 3) = v9;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                          & ((unsigned __int64)ATL::_pAtlModule + 8)),
              (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
              (unsigned __int64)this);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
        }
        goto LABEL_26;
      }
      NameCache = -2147467259;
      ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
      if ( ModuleFileNameW && ModuleFileNameW != 260 )
      {
        v12 = 0;
        NameCache = LoadTypeLib(Filename, &pptlib);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v12);
        goto LABEL_13;
      }
    }
LABEL_26:
    v10 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    if ( v10 )
    {
      if ( !*((_QWORD *)this + 5) )
        NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v10);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v15);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x180027ef8  mov     [rsp-8+arg_10], rbx
0x180027efd  push    rbp
0x180027efe  push    rsi
0x180027eff  push    rdi
0x180027f00  lea     rbp, [rsp-180h]
0x180027f08  sub     rsp, 280h
0x180027f0f  mov     rax, cs:__security_cookie
0x180027f16  xor     rax, rsp
0x180027f19  mov     [rbp+190h+var_20], rax
0x180027f20  mov     esi, edx
0x180027f22  mov     rbx, rcx
0x180027f25  cmp     qword ptr [rcx+18h], 0
0x180027f2a  jz      short loc_180027F3A
0x180027f2c  cmp     qword ptr [rcx+28h], 0
0x180027f31  jz      short loc_180027F3A
0x180027f33  xor     eax, eax
0x180027f35  jmp     loc_18002816C
0x180027f3a  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180027f41  add     rax, 18h
0x180027f45  mov     [rsp+290h+var_240], rax
0x180027f4a  mov     [rsp+290h+var_238], 0
0x180027f4f  lea     rcx, [rsp+290h+var_240]
0x180027f54  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180027f59  mov     edi, eax
0x180027f5b  test    eax, eax
0x180027f5d  js      loc_180028160
0x180027f63  cmp     qword ptr [rbx+18h], 0
0x180027f68  jnz     loc_180028144
0x180027f6e  mov     [rsp+290h+pptlib], 0
0x180027f77  mov     rdx, [rbx+8]
0x180027f7b  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; _GUID ATL::CAtlModule::m_libid
0x180027f82  call    InlineIsEqualGUID
0x180027f87  test    eax, eax
0x180027f89  jz      short loc_180027FF2
0x180027f8b  mov     eax, 0FFFFh
0x180027f90  cmp     [rbx+10h], ax
0x180027f94  jnz     short loc_180027FF2
0x180027f96  cmp     [rbx+12h], ax
0x180027f9a  jnz     short loc_180027FF2
0x180027f9c  mov     edi, 80004005h
0x180027fa1  mov     esi, 104h
0x180027fa6  mov     r8d, esi; nSize
0x180027fa9  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180027fae  mov     rcx, cs:hModule; hModule
0x180027fb5  call    cs:__imp_GetModuleFileNameW
0x180027fbb  test    eax, eax
0x180027fbd  jz      loc_180028146
0x180027fc3  cmp     eax, esi
0x180027fc5  jz      loc_180028146
0x180027fcb  mov     [rsp+290h+var_258], 0
0x180027fd4  lea     rdx, [rsp+290h+pptlib]; pptlib
0x180027fd9  lea     rcx, [rsp+290h+Filename]; szFile
0x180027fde  call    cs:__imp_LoadTypeLib
0x180027fe4  mov     edi, eax
0x180027fe6  lea     rcx, [rsp+290h+var_258]
0x180027feb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180027ff0  jmp     short loc_180028014
0x180027ff2  lea     rax, [rsp+290h+pptlib]
0x180027ff7  mov     [rsp+290h+var_270], rax; pptlib
0x180027ffc  mov     r9d, esi; lcid
0x180027fff  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180028004  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x180028008  mov     rcx, [rbx+8]; rguid
0x18002800c  call    cs:__imp_LoadRegTypeLib
0x180028012  mov     edi, eax
0x180028014  test    edi, edi
0x180028016  js      loc_180028146
0x18002801c  mov     [rsp+290h+var_258], 0
0x180028025  mov     rcx, [rsp+290h+pptlib]
0x18002802a  mov     rax, [rcx]
0x18002802d  lea     r8, [rsp+290h+var_258]
0x180028032  mov     rdx, [rbx]
0x180028035  mov     rax, [rax+30h]
0x180028039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002803e  mov     edi, eax
0x180028040  test    eax, eax
0x180028042  js      loc_180028126
0x180028048  mov     rcx, [rsp+290h+var_258]
0x18002804d  mov     [rsp+290h+var_260], rcx
0x180028052  test    rcx, rcx
0x180028055  jz      short loc_180028068
0x180028057  mov     rax, [rcx]
0x18002805a  mov     rax, [rax+8]
0x18002805e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028063  mov     rcx, [rsp+290h+var_258]
0x180028068  mov     [rsp+290h+var_250], 0
0x180028071  mov     rax, [rcx]
0x180028074  lea     r8, [rsp+290h+var_250]
0x180028079  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180028080  mov     rax, [rax]
0x180028083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028088  test    eax, eax
0x18002808a  js      short loc_1800280E2
0x18002808c  mov     rdx, [rsp+290h+var_250]
0x180028091  lea     rcx, [rsp+290h+var_260]
0x180028096  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x18002809b  test    al, al
0x18002809d  jnz     short loc_1800280E2
0x18002809f  mov     rcx, [rsp+290h+var_250]
0x1800280a4  mov     rsi, [rsp+290h+var_260]
0x1800280a9  mov     [rsp+290h+var_260], 0
0x1800280b2  test    rcx, rcx
0x1800280b5  jz      short loc_1800280CE
0x1800280b7  mov     rax, [rcx]
0x1800280ba  lea     r8, [rsp+290h+var_260]
0x1800280bf  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x1800280c6  mov     rax, [rax]
0x1800280c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280ce  test    rsi, rsi
0x1800280d1  jz      short loc_1800280E2
0x1800280d3  mov     rax, [rsi]
0x1800280d6  mov     rcx, rsi
0x1800280d9  mov     rax, [rax+10h]
0x1800280dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280e2  mov     rax, [rsp+290h+var_260]
0x1800280e7  mov     [rsp+290h+var_260], 0
0x1800280f0  mov     [rbx+18h], rax
0x1800280f4  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800280fb  lea     rcx, [rax+8]
0x1800280ff  neg     rax
0x180028102  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180028105  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180028108  mov     r8, rbx; unsigned __int64
0x18002810b  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180028110  nop
0x180028111  lea     rcx, [rsp+290h+var_250]
0x180028116  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002811b  nop
0x18002811c  lea     rcx, [rsp+290h+var_260]
0x180028121  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028126  mov     rcx, [rsp+290h+pptlib]
0x18002812b  mov     rax, [rcx]
0x18002812e  mov     rax, [rax+10h]
0x180028132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028137  nop
0x180028138  lea     rcx, [rsp+290h+var_258]
0x18002813d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028142  jmp     short loc_180028146
0x180028144  xor     edi, edi
0x180028146  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x18002814a  test    rdx, rdx
0x18002814d  jz      short loc_180028160
0x18002814f  cmp     qword ptr [rbx+28h], 0
0x180028154  jnz     short loc_180028160
0x180028156  mov     rcx, rbx; this
0x180028159  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18002815e  mov     edi, eax
0x180028160  lea     rcx, [rsp+290h+var_240]
0x180028165  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002816a  mov     eax, edi
0x18002816c  mov     rcx, [rbp+190h+var_20]
0x180028173  xor     rcx, rsp; StackCookie
0x180028176  call    __security_check_cookie
0x18002817b  mov     rbx, [rsp+290h+arg_10]
0x180028183  add     rsp, 280h
0x18002818a  pop     rdi
0x18002818b  pop     rsi
0x18002818c  pop     rbp
0x18002818d  retn
```
