# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18003bcdc`
- end: `0x18003bf3c`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `608`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `7`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180035f68`
- `0x18003645c`
- `0x180037ab0`
- `0x180038710`
- `0x180038890`
- `0x180038940`
- `0x18003bc68`

## callees

- `0x180001880`
- `0x18002a6c0`
- `0x18003a164`
- `0x18003bcdc`
- `0x18003cb58`
- `0x18003f468`
- `0x1800401e8`
- `0x180040450`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bd31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bd31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003bd92`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003bd92`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18003bdc4`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18003bdc4`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18003bdf8`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18003bdf8`

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
0x18003bcdc  mov     [rsp-8+arg_10], rbx
0x18003bce1  mov     [rsp-8+arg_18], rdi
0x18003bce6  push    rbp
0x18003bce7  lea     rbp, [rsp-180h]
0x18003bcef  sub     rsp, 280h
0x18003bcf6  mov     rax, cs:__security_cookie
0x18003bcfd  xor     rax, rsp
0x18003bd00  mov     [rbp+180h+var_10], rax
0x18003bd07  mov     edi, edx
0x18003bd09  mov     rbx, rcx
0x18003bd0c  cmp     qword ptr [rcx+18h], 0
0x18003bd11  jz      short loc_18003BD21
0x18003bd13  cmp     qword ptr [rcx+28h], 0
0x18003bd18  jz      short loc_18003BD21
0x18003bd1a  xor     eax, eax
0x18003bd1c  jmp     loc_18003BF17
0x18003bd21  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18003bd28  add     rcx, 18h; lpCriticalSection
0x18003bd2c  mov     [rsp+280h+var_230], rcx
0x18003bd31  call    cs:__imp_EnterCriticalSection
0x18003bd38  nop     dword ptr [rax+rax+00h]
0x18003bd3d  mov     [rsp+280h+var_228], 1
0x18003bd42  cmp     qword ptr [rbx+18h], 0
0x18003bd47  jnz     loc_18003BEEF
0x18003bd4d  mov     [rsp+280h+pptlib], 0
0x18003bd56  mov     rdx, [rbx+8]; struct _GUID *
0x18003bd5a  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; struct _GUID *
0x18003bd61  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18003bd66  test    eax, eax
0x18003bd68  jz      short loc_18003BDDE
0x18003bd6a  mov     eax, 0FFFFh
0x18003bd6f  cmp     [rbx+10h], ax
0x18003bd73  jnz     short loc_18003BDDE
0x18003bd75  cmp     [rbx+12h], ax
0x18003bd79  jnz     short loc_18003BDDE
0x18003bd7b  mov     edi, 80004005h
0x18003bd80  mov     r8d, 104h; nSize
0x18003bd86  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18003bd8b  mov     rcx, cs:hModule; hModule
0x18003bd92  call    cs:__imp_GetModuleFileNameW
0x18003bd99  nop     dword ptr [rax+rax+00h]
0x18003bd9e  test    eax, eax
0x18003bda0  jz      loc_18003BEF1
0x18003bda6  cmp     eax, 104h
0x18003bdab  jz      loc_18003BEF1
0x18003bdb1  mov     [rsp+280h+var_250], 0
0x18003bdba  lea     rdx, [rsp+280h+pptlib]; pptlib
0x18003bdbf  lea     rcx, [rsp+280h+Filename]; szFile
0x18003bdc4  call    cs:__imp_LoadTypeLib
0x18003bdcb  nop     dword ptr [rax+rax+00h]
0x18003bdd0  mov     edi, eax
0x18003bdd2  lea     rcx, [rsp+280h+var_250]
0x18003bdd7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003bddc  jmp     short loc_18003BE06
0x18003bdde  lea     rax, [rsp+280h+pptlib]
0x18003bde3  mov     [rsp+280h+var_260], rax; pptlib
0x18003bde8  mov     r9d, edi; lcid
0x18003bdeb  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x18003bdf0  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x18003bdf4  mov     rcx, [rbx+8]; rguid
0x18003bdf8  call    cs:__imp_LoadRegTypeLib
0x18003bdff  nop     dword ptr [rax+rax+00h]
0x18003be04  mov     edi, eax
0x18003be06  test    edi, edi
0x18003be08  js      loc_18003BEF1
0x18003be0e  mov     [rsp+280h+var_238], 0
0x18003be17  mov     rcx, [rsp+280h+pptlib]
0x18003be1c  mov     rax, [rcx]
0x18003be1f  lea     r8, [rsp+280h+var_238]
0x18003be24  mov     rdx, [rbx]
0x18003be27  mov     rax, [rax+30h]
0x18003be2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be30  mov     edi, eax
0x18003be32  test    eax, eax
0x18003be34  js      loc_18003BED1
0x18003be3a  mov     rcx, [rsp+280h+var_238]
0x18003be3f  mov     [rsp+280h+var_248], rcx
0x18003be44  test    rcx, rcx
0x18003be47  jz      short loc_18003BE5A
0x18003be49  mov     rax, [rcx]
0x18003be4c  mov     rax, [rax+8]
0x18003be50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be55  mov     rcx, [rsp+280h+var_238]
0x18003be5a  mov     [rsp+280h+var_250], 0
0x18003be63  mov     rax, [rcx]
0x18003be66  lea     r8, [rsp+280h+var_250]
0x18003be6b  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18003be72  mov     rax, [rax]
0x18003be75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be7a  test    eax, eax
0x18003be7c  js      short loc_18003BE8D
0x18003be7e  lea     rdx, [rsp+280h+var_250]
0x18003be83  lea     rcx, [rsp+280h+var_248]
0x18003be88  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x18003be8d  mov     rax, [rsp+280h+var_248]
0x18003be92  mov     [rsp+280h+var_248], 0
0x18003be9b  mov     [rbx+18h], rax
0x18003be9f  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18003bea6  lea     rcx, [rax+8]
0x18003beaa  neg     rax
0x18003bead  sbb     rdx, rdx; void (*)(unsigned __int64)
0x18003beb0  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x18003beb3  mov     r8, rbx; unsigned __int64
0x18003beb6  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x18003bebb  nop
0x18003bebc  lea     rcx, [rsp+280h+var_250]
0x18003bec1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003bec6  nop
0x18003bec7  lea     rcx, [rsp+280h+var_248]
0x18003becc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003bed1  mov     rcx, [rsp+280h+pptlib]
0x18003bed6  mov     rax, [rcx]
0x18003bed9  mov     rax, [rax+10h]
0x18003bedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bee2  nop
0x18003bee3  lea     rcx, [rsp+280h+var_238]
0x18003bee8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003beed  jmp     short loc_18003BEF1
0x18003beef  xor     edi, edi
0x18003bef1  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x18003bef5  test    rdx, rdx
0x18003bef8  jz      short loc_18003BF0B
0x18003befa  cmp     qword ptr [rbx+28h], 0
0x18003beff  jnz     short loc_18003BF0B
0x18003bf01  mov     rcx, rbx; this
0x18003bf04  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18003bf09  mov     edi, eax
0x18003bf0b  lea     rcx, [rsp+280h+var_230]
0x18003bf10  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18003bf15  mov     eax, edi
0x18003bf17  mov     rcx, [rbp+180h+var_10]
0x18003bf1e  xor     rcx, rsp; StackCookie
0x18003bf21  call    __security_check_cookie
0x18003bf26  lea     r11, [rsp+280h+var_s0]
0x18003bf2e  mov     rbx, [r11+20h]
0x18003bf32  mov     rdi, [r11+28h]
0x18003bf36  mov     rsp, r11
0x18003bf39  pop     rbp
0x18003bf3a  retn
```
