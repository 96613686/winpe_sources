# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180007044`
- end: `0x1800072db`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `663`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180006f44`
- `0x180007304`
- `0x1800074c8`

## callees

- `0x180002ae8`
- `0x180002b4c`
- `0x180002b7c`
- `0x180004550`
- `0x180005e40`
- `0x180006b88`
- `0x180007044`
- `0x18000756c`
- `0x1800075fc`
- `0x18001e9f0`
- `0x180020010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1800070fe`
- `KERNEL32!GetModuleFileNameW` at `0x1800070fe`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000712a`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000712a`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000715e`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000715e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  DWORD ModuleFileNameW; // eax
  int (__fastcall ***v7)(_QWORD, GUID *, _QWORD); // rcx
  int (__fastcall ***v8)(_QWORD, GUID *, _QWORD); // rsi
  int (__fastcall ***v9)(_QWORD, GUID *, _QWORD); // rax
  struct ITypeInfo *v10; // rdx
  int (__fastcall ***v11)(_QWORD, GUID *, _QWORD); // [rsp+30h] [rbp-D0h] BYREF
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD); // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // [rsp+40h] [rbp-C0h] BYREF
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
    NameCache = -2147467259;
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
            v11 = v12;
            if ( v12 )
            {
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v12)[1])(v12);
              v7 = v12;
            }
            v13 = 0;
            if ( (**v7)(v7, &GUID_00020412_0000_0000_c000_000000000046, &v13) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v11, v13) )
            {
              v8 = v11;
              v11 = 0;
              if ( v13 )
                (**v13)(v13, &GUID_00020401_0000_0000_c000_000000000046, &v11);
              if ( v8 )
                ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v8)[2])(v8);
            }
            v9 = v11;
            v11 = 0;
            *((_QWORD *)this + 3) = v9;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                          & ((unsigned __int64)ATL::_pAtlModule + 8)),
              (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
              (unsigned __int64)this);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
        }
        goto LABEL_26;
      }
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
0x180007044  mov     [rsp-8+arg_10], rbx
0x180007049  push    rbp
0x18000704a  push    rsi
0x18000704b  push    rdi
0x18000704c  lea     rbp, [rsp-180h]
0x180007054  sub     rsp, 280h
0x18000705b  mov     rax, cs:__security_cookie
0x180007062  xor     rax, rsp
0x180007065  mov     [rbp+190h+var_20], rax
0x18000706c  mov     esi, edx
0x18000706e  mov     rbx, rcx
0x180007071  cmp     qword ptr [rcx+18h], 0
0x180007076  jz      short loc_180007086
0x180007078  cmp     qword ptr [rcx+28h], 0
0x18000707d  jz      short loc_180007086
0x18000707f  xor     eax, eax
0x180007081  jmp     loc_1800072B8
0x180007086  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000708d  add     rax, 18h
0x180007091  mov     [rsp+290h+var_240], rax
0x180007096  mov     [rsp+290h+var_238], 0
0x18000709b  lea     rcx, [rsp+290h+var_240]
0x1800070a0  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800070a5  mov     edi, eax
0x1800070a7  test    eax, eax
0x1800070a9  js      loc_1800072AC
0x1800070af  mov     edi, 80004005h
0x1800070b4  cmp     qword ptr [rbx+18h], 0
0x1800070b9  jnz     loc_180007290
0x1800070bf  and     [rsp+290h+pptlib], 0
0x1800070c5  mov     rdx, [rbx+8]
0x1800070c9  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; _GUID ATL::CAtlModule::m_libid
0x1800070d0  call    InlineIsEqualGUID
0x1800070d5  test    eax, eax
0x1800070d7  jz      short loc_180007144
0x1800070d9  mov     eax, 0FFFFh
0x1800070de  cmp     [rbx+10h], ax
0x1800070e2  jnz     short loc_180007144
0x1800070e4  cmp     [rbx+12h], ax
0x1800070e8  jnz     short loc_180007144
0x1800070ea  mov     esi, 104h
0x1800070ef  mov     r8d, esi; nSize
0x1800070f2  lea     rdx, [rsp+290h+Filename]; lpFilename
0x1800070f7  mov     rcx, cs:hModule; hModule
0x1800070fe  call    cs:__imp_GetModuleFileNameW
0x180007105  nop     dword ptr [rax+rax+00h]
0x18000710a  test    eax, eax
0x18000710c  jz      loc_180007292
0x180007112  cmp     eax, esi
0x180007114  jz      loc_180007292
0x18000711a  and     [rsp+290h+var_258], 0
0x180007120  lea     rdx, [rsp+290h+pptlib]; pptlib
0x180007125  lea     rcx, [rsp+290h+Filename]; szFile
0x18000712a  call    cs:__imp_LoadTypeLib
0x180007131  nop     dword ptr [rax+rax+00h]
0x180007136  mov     edi, eax
0x180007138  lea     rcx, [rsp+290h+var_258]
0x18000713d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007142  jmp     short loc_18000716C
0x180007144  lea     rax, [rsp+290h+pptlib]
0x180007149  mov     [rsp+290h+var_270], rax; pptlib
0x18000714e  mov     r9d, esi; lcid
0x180007151  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180007156  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x18000715a  mov     rcx, [rbx+8]; rguid
0x18000715e  call    cs:__imp_LoadRegTypeLib
0x180007165  nop     dword ptr [rax+rax+00h]
0x18000716a  mov     edi, eax
0x18000716c  test    edi, edi
0x18000716e  js      loc_180007292
0x180007174  and     [rsp+290h+var_258], 0
0x18000717a  mov     rcx, [rsp+290h+pptlib]
0x18000717f  mov     rax, [rcx]
0x180007182  lea     r8, [rsp+290h+var_258]
0x180007187  mov     rdx, [rbx]
0x18000718a  mov     rax, [rax+30h]
0x18000718e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007193  mov     edi, eax
0x180007195  test    eax, eax
0x180007197  js      loc_180007272
0x18000719d  mov     rcx, [rsp+290h+var_258]
0x1800071a2  mov     [rsp+290h+var_260], rcx
0x1800071a7  test    rcx, rcx
0x1800071aa  jz      short loc_1800071BD
0x1800071ac  mov     rax, [rcx]
0x1800071af  mov     rax, [rax+8]
0x1800071b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071b8  mov     rcx, [rsp+290h+var_258]
0x1800071bd  and     [rsp+290h+var_250], 0
0x1800071c3  mov     rax, [rcx]
0x1800071c6  lea     r8, [rsp+290h+var_250]
0x1800071cb  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x1800071d2  mov     rax, [rax]
0x1800071d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071da  test    eax, eax
0x1800071dc  js      short loc_180007231
0x1800071de  mov     rdx, [rsp+290h+var_250]
0x1800071e3  lea     rcx, [rsp+290h+var_260]
0x1800071e8  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x1800071ed  test    al, al
0x1800071ef  jnz     short loc_180007231
0x1800071f1  mov     rsi, [rsp+290h+var_260]
0x1800071f6  and     [rsp+290h+var_260], 0
0x1800071fc  mov     rcx, [rsp+290h+var_250]
0x180007201  test    rcx, rcx
0x180007204  jz      short loc_18000721D
0x180007206  mov     rax, [rcx]
0x180007209  lea     r8, [rsp+290h+var_260]
0x18000720e  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x180007215  mov     rax, [rax]
0x180007218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000721d  test    rsi, rsi
0x180007220  jz      short loc_180007231
0x180007222  mov     rax, [rsi]
0x180007225  mov     rcx, rsi
0x180007228  mov     rax, [rax+10h]
0x18000722c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007231  mov     rax, [rsp+290h+var_260]
0x180007236  and     [rsp+290h+var_260], 0
0x18000723c  mov     [rbx+18h], rax
0x180007240  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007247  lea     rcx, [rax+8]
0x18000724b  neg     rax
0x18000724e  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180007251  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180007254  mov     r8, rbx; unsigned __int64
0x180007257  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x18000725c  nop
0x18000725d  lea     rcx, [rsp+290h+var_250]
0x180007262  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007267  nop
0x180007268  lea     rcx, [rsp+290h+var_260]
0x18000726d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007272  mov     rcx, [rsp+290h+pptlib]
0x180007277  mov     rax, [rcx]
0x18000727a  mov     rax, [rax+10h]
0x18000727e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007283  nop
0x180007284  lea     rcx, [rsp+290h+var_258]
0x180007289  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000728e  jmp     short loc_180007292
0x180007290  xor     edi, edi
0x180007292  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180007296  test    rdx, rdx
0x180007299  jz      short loc_1800072AC
0x18000729b  cmp     qword ptr [rbx+28h], 0
0x1800072a0  jnz     short loc_1800072AC
0x1800072a2  mov     rcx, rbx; this
0x1800072a5  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x1800072aa  mov     edi, eax
0x1800072ac  lea     rcx, [rsp+290h+var_240]
0x1800072b1  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800072b6  mov     eax, edi
0x1800072b8  mov     rcx, [rbp+190h+var_20]
0x1800072bf  xor     rcx, rsp; StackCookie
0x1800072c2  call    __security_check_cookie
0x1800072c7  mov     rbx, [rsp+290h+arg_10]
0x1800072cf  add     rsp, 280h
0x1800072d6  pop     rdi
0x1800072d7  pop     rsi
0x1800072d8  pop     rbp
0x1800072d9  retn
```
