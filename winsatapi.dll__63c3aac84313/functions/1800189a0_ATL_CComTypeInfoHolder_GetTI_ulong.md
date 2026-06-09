# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x1800189a0`
- end: `0x180018c40`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `672`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800188d4`
- `0x180018c84`
- `0x180018f38`

## callees

- `0x180001a34`
- `0x18000daec`
- `0x180015290`
- `0x180015540`
- `0x180016c40`
- `0x1800189a0`
- `0x180018fdc`
- `0x18001907c`
- `0x1800192f0`
- `0x18002dec0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLib` at `0x180018a90`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180018a90`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180018abe`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180018abe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180018a67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180018a67`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  DWORD ModuleFileNameW; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rsi
  _QWORD *v9; // rax
  struct ITypeInfo *v10; // rdx
  _QWORD *v11; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD *v12; // [rsp+40h] [rbp-C8h] BYREF
  void (__fastcall ***v13)(_QWORD, GUID *, _QWORD **); // [rsp+48h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-B8h] BYREF
  char *v15; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A8h]
  __int64 v17; // [rsp+68h] [rbp-A0h]
  WCHAR Filename[264]; // [rsp+78h] [rbp-90h] BYREF

  v17 = -2;
  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v15 = (char *)ATL::_pAtlModule + 24;
  LOBYTE(v16) = 0;
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
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        *(_QWORD *)this,
                        &v12);
          if ( NameCache >= 0 )
          {
            v7 = v12;
            v11 = v12;
            if ( v12 )
            {
              (*(void (__fastcall **)(_QWORD *))(*v12 + 8LL))(v12);
              v7 = v12;
            }
            v13 = 0;
            if ( (*(int (__fastcall **)(_QWORD *, GUID *, _QWORD))*v7)(
                   v7,
                   &GUID_00020412_0000_0000_c000_000000000046,
                   &v13) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v11, v13) )
            {
              v8 = (__int64)v11;
              v11 = 0;
              if ( v13 )
                (**v13)(v13, &GUID_00020401_0000_0000_c000_000000000046, &v11);
              if ( v8 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            }
            v9 = v11;
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
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v15);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x1800189a0  mov     rax, rsp
0x1800189a3  push    rbp
0x1800189a4  push    rsi
0x1800189a5  push    rdi
0x1800189a6  lea     rbp, [rax-1A8h]
0x1800189ad  sub     rsp, 290h
0x1800189b4  mov     [rsp+2A0h+var_240], 0FFFFFFFFFFFFFFFEh
0x1800189bd  mov     [rax+18h], rbx
0x1800189c1  mov     rax, cs:__security_cookie
0x1800189c8  xor     rax, rsp
0x1800189cb  mov     [rbp+1A0h+var_20], rax
0x1800189d2  mov     esi, edx
0x1800189d4  mov     rbx, rcx
0x1800189d7  cmp     qword ptr [rcx+18h], 0
0x1800189dc  jz      short loc_1800189EC
0x1800189de  cmp     qword ptr [rcx+28h], 0
0x1800189e3  jz      short loc_1800189EC
0x1800189e5  xor     eax, eax
0x1800189e7  jmp     loc_180018C1E
0x1800189ec  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800189f3  add     rax, 18h
0x1800189f7  mov     [rsp+2A0h+var_250], rax
0x1800189fc  mov     byte ptr [rsp+2A0h+var_248], 0
0x180018a01  lea     rcx, [rsp+2A0h+var_250]
0x180018a06  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180018a0b  mov     edi, eax
0x180018a0d  test    eax, eax
0x180018a0f  js      loc_180018C12
0x180018a15  cmp     qword ptr [rbx+18h], 0
0x180018a1a  jnz     loc_180018BF6
0x180018a20  mov     [rsp+2A0h+pptlib], 0
0x180018a29  mov     rdx, [rbx+8]
0x180018a2d  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; _GUID ATL::CAtlModule::m_libid
0x180018a34  call    InlineIsEqualGUID
0x180018a39  test    eax, eax
0x180018a3b  jz      short loc_180018AA4
0x180018a3d  mov     eax, 0FFFFh
0x180018a42  cmp     [rbx+10h], ax
0x180018a46  jnz     short loc_180018AA4
0x180018a48  cmp     [rbx+12h], ax
0x180018a4c  jnz     short loc_180018AA4
0x180018a4e  mov     edi, 80004005h
0x180018a53  mov     esi, 104h
0x180018a58  mov     r8d, esi; nSize
0x180018a5b  lea     rdx, [rsp+2A0h+Filename]; lpFilename
0x180018a60  mov     rcx, cs:hModule; hModule
0x180018a67  call    cs:__imp_GetModuleFileNameW
0x180018a6d  test    eax, eax
0x180018a6f  jz      loc_180018BF8
0x180018a75  cmp     eax, esi
0x180018a77  jz      loc_180018BF8
0x180018a7d  mov     [rsp+2A0h+var_268], 0
0x180018a86  lea     rdx, [rsp+2A0h+pptlib]; pptlib
0x180018a8b  lea     rcx, [rsp+2A0h+Filename]; szFile
0x180018a90  call    cs:__imp_LoadTypeLib
0x180018a96  mov     edi, eax
0x180018a98  lea     rcx, [rsp+2A0h+var_268]
0x180018a9d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180018aa2  jmp     short loc_180018AC6
0x180018aa4  lea     rax, [rsp+2A0h+pptlib]
0x180018aa9  mov     [rsp+20h], rax; pptlib
0x180018aae  mov     r9d, esi; lcid
0x180018ab1  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180018ab6  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x180018aba  mov     rcx, [rbx+8]; rguid
0x180018abe  call    cs:__imp_LoadRegTypeLib
0x180018ac4  mov     edi, eax
0x180018ac6  test    edi, edi
0x180018ac8  js      loc_180018BF8
0x180018ace  mov     [rsp+2A0h+var_268], 0
0x180018ad7  mov     rcx, [rsp+2A0h+pptlib]
0x180018adc  mov     rax, [rcx]
0x180018adf  lea     r8, [rsp+2A0h+var_268]
0x180018ae4  mov     rdx, [rbx]
0x180018ae7  mov     rax, [rax+30h]
0x180018aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018af0  mov     edi, eax
0x180018af2  test    eax, eax
0x180018af4  js      loc_180018BD8
0x180018afa  mov     rcx, [rsp+2A0h+var_268]
0x180018aff  mov     [rsp+2A0h+var_270], rcx
0x180018b04  test    rcx, rcx
0x180018b07  jz      short loc_180018B1A
0x180018b09  mov     rax, [rcx]
0x180018b0c  mov     rax, [rax+8]
0x180018b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b15  mov     rcx, [rsp+2A0h+var_268]
0x180018b1a  mov     [rsp+2A0h+var_260], 0
0x180018b23  mov     rax, [rcx]
0x180018b26  lea     r8, [rsp+2A0h+var_260]
0x180018b2b  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180018b32  mov     rax, [rax]
0x180018b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b3a  test    eax, eax
0x180018b3c  js      short loc_180018B94
0x180018b3e  mov     rdx, [rsp+2A0h+var_260]
0x180018b43  lea     rcx, [rsp+2A0h+var_270]
0x180018b48  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x180018b4d  test    al, al
0x180018b4f  jnz     short loc_180018B94
0x180018b51  mov     rcx, [rsp+2A0h+var_260]
0x180018b56  mov     rsi, [rsp+2A0h+var_270]
0x180018b5b  mov     [rsp+2A0h+var_270], 0
0x180018b64  test    rcx, rcx
0x180018b67  jz      short loc_180018B80
0x180018b69  mov     rax, [rcx]
0x180018b6c  lea     r8, [rsp+2A0h+var_270]
0x180018b71  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x180018b78  mov     rax, [rax]
0x180018b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b80  test    rsi, rsi
0x180018b83  jz      short loc_180018B94
0x180018b85  mov     rax, [rsi]
0x180018b88  mov     rcx, rsi
0x180018b8b  mov     rax, [rax+10h]
0x180018b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b94  mov     rax, [rsp+2A0h+var_270]
0x180018b99  mov     [rsp+2A0h+var_270], 0
0x180018ba2  mov     [rbx+18h], rax
0x180018ba6  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180018bad  lea     rcx, [rax+8]
0x180018bb1  neg     rax
0x180018bb4  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180018bb7  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180018bba  mov     r8, rbx; unsigned __int64
0x180018bbd  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180018bc2  nop
0x180018bc3  lea     rcx, [rsp+2A0h+var_260]
0x180018bc8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018bcd  nop
0x180018bce  lea     rcx, [rsp+2A0h+var_270]
0x180018bd3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018bd8  mov     rcx, [rsp+2A0h+pptlib]
0x180018bdd  mov     rax, [rcx]
0x180018be0  mov     rax, [rax+10h]
0x180018be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018be9  nop
0x180018bea  lea     rcx, [rsp+2A0h+var_268]
0x180018bef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018bf4  jmp     short loc_180018BF8
0x180018bf6  xor     edi, edi
0x180018bf8  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180018bfc  test    rdx, rdx
0x180018bff  jz      short loc_180018C12
0x180018c01  cmp     qword ptr [rbx+28h], 0
0x180018c06  jnz     short loc_180018C12
0x180018c08  mov     rcx, rbx; this
0x180018c0b  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180018c10  mov     edi, eax
0x180018c12  lea     rcx, [rsp+2A0h+var_250]
0x180018c17  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180018c1c  mov     eax, edi
0x180018c1e  mov     rcx, [rbp+1A0h+var_20]
0x180018c25  xor     rcx, rsp; StackCookie
0x180018c28  call    __security_check_cookie
0x180018c2d  mov     rbx, [rsp+2A0h+arg_10]
0x180018c35  add     rsp, 290h
0x180018c3c  pop     rdi
0x180018c3d  pop     rsi
0x180018c3e  pop     rbp
0x180018c3f  retn
```
