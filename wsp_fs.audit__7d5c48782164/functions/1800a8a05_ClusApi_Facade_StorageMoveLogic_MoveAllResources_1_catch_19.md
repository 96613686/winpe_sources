# _ClusApi::Facade::StorageMoveLogic::MoveAllResources_::_1_::catch$19

- ea: `0x1800a8a05`
- end: `0x1800a8c21`
- name: `_ClusApi::Facade::StorageMoveLogic::MoveAllResources_::_1_::catch$19`
- size: `540`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180003534`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000d5b8`
- `0x18000e14c`
- `0x18000eb18`
- `0x18001cdd4`
- `0x18008f75c`
- `0x18008ff28`
- `0x180094880`
- `0x1800a8a05`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a8bac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a8bac`

## string_xrefs

- `0x1800a8aa5`: `ClusApi::Facade::StorageMoveLogic::MoveAllResources`

## pseudocode

```c
__int64 __fastcall ClusApi::Facade::StorageMoveLogic::MoveAllResources_::_1_::catch_19(__int64 a1, __int64 a2)
{
  struct cxl::TextWriter *v3; // r15
  __int64 v4; // rax
  __int64 v5; // r14
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rbx
  __int64 v9; // rax
  _QWORD *ResourceFacade; // rax
  __int64 id; // rax
  const WCHAR *lpString2; // rdi
  _QWORD *v13; // rax
  __int64 v14; // rax
  const WCHAR *v15; // rax
  bool v16; // bl
  std::_Ref_count_base *v17; // rcx
  std::_Ref_count_base *v18; // rcx

  v3 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
  *(_DWORD *)(a2 + 68) = cxl::ErrorCode::GetHr((cxl::ErrorCode *)(*(_QWORD *)(a2 + 128) + 88LL));
  v4 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a2 + 88) + 48LL))(**(_QWORD **)(a2 + 88));
  v5 = std::wstring::wstring(a2 + 200, v4);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a2 + 96) + 48LL))(**(_QWORD **)(a2 + 96));
  v7 = std::wstring::wstring(a2 + 168, v6);
  v8 = *(_QWORD *)(a2 + 72);
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 64) + 48LL))(*(_QWORD *)(v8 + 64));
  std::wstring::wstring(a2 + 296, v9);
  std::wstring::wstring(a2 + 264, L"ClusApi::Facade::StorageMoveLogic::MoveAllResources");
  std::wstring::wstring(a2 + 232, a2 + 264);
  cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring,std::wstring,std::wstring,long>(v3, v7, v5, a2 + 68);
  std::wstring::_Tidy_deallocate(a2 + 232);
  std::wstring::_Tidy_deallocate(a2 + 264);
  std::wstring::_Tidy_deallocate(a2 + 296);
  std::wstring::_Tidy_deallocate(a2 + 168);
  std::wstring::_Tidy_deallocate(a2 + 200);
  ResourceFacade = (_QWORD *)ClusApi::Facade::FacadeFactory::CreateResourceFacade(
                               a2 + 152,
                               *(_QWORD *)(*(_QWORD *)(a2 + 80) + 8LL) + 56LL);
  id = ClusApi::Facade::FacadeItem::get_id(*ResourceFacade, a2 + 168);
  lpString2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(id);
  v13 = (_QWORD *)ClusApi::Facade::FacadeFactory::CreateResourceFacade(a2 + 136, v8 + 64);
  v14 = ClusApi::Facade::FacadeItem::get_id(*v13, a2 + 200);
  v15 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
  v16 = CompareStringW(0x400u, 1u, v15, -1, lpString2, -1) == 2;
  std::wstring::_Tidy_deallocate(a2 + 200);
  v17 = *(std::_Ref_count_base **)(a2 + 144);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  std::wstring::_Tidy_deallocate(a2 + 168);
  v18 = *(std::_Ref_count_base **)(a2 + 160);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( v16 )
    throw;
  return 0;
}

```

## disassembly

```asm
0x1800a8a05  mov     [rsp+arg_8], rdx
0x1800a8a0a  push    rbx
0x1800a8a0b  push    rbp
0x1800a8a0c  push    rsi
0x1800a8a0d  push    rdi
0x1800a8a0e  push    r14
0x1800a8a10  push    r15
0x1800a8a12  sub     rsp, 48h
0x1800a8a16  mov     rbp, rdx
0x1800a8a19  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800a8a1e  lea     r15, [rax+28h]
0x1800a8a22  mov     rcx, [rbp+80h]
0x1800a8a29  add     rcx, 58h ; 'X'; this
0x1800a8a2d  call    ?GetHr@ErrorCode@cxl@@QEBAJXZ; cxl::ErrorCode::GetHr(void)
0x1800a8a32  mov     [rbp+44h], eax
0x1800a8a35  mov     rax, [rbp+58h]
0x1800a8a39  mov     rcx, [rax]
0x1800a8a3c  mov     rax, [rcx]
0x1800a8a3f  mov     rax, [rax+30h]
0x1800a8a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a48  mov     rdx, rax
0x1800a8a4b  lea     rcx, [rbp+0C8h]
0x1800a8a52  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a8a57  mov     r14, rax
0x1800a8a5a  mov     rcx, [rbp+60h]
0x1800a8a5e  mov     rcx, [rcx]
0x1800a8a61  mov     rdx, [rcx]
0x1800a8a64  mov     rax, [rdx+30h]
0x1800a8a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a6d  mov     rdx, rax
0x1800a8a70  lea     rcx, [rbp+0A8h]
0x1800a8a77  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a8a7c  mov     rsi, rax
0x1800a8a7f  mov     rbx, [rbp+48h]
0x1800a8a83  mov     rcx, [rbx+40h]
0x1800a8a87  mov     rdx, [rcx]
0x1800a8a8a  mov     rax, [rdx+30h]
0x1800a8a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a93  mov     rdx, rax
0x1800a8a96  lea     rcx, [rbp+128h]
0x1800a8a9d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a8aa2  mov     rdi, rax
0x1800a8aa5  lea     rdx, aClusapiFacadeS_0; "ClusApi::Facade::StorageMoveLogic::Move"...
0x1800a8aac  lea     rcx, [rbp+108h]
0x1800a8ab3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a8ab8  nop
0x1800a8ab9  lea     rdx, [rbp+108h]
0x1800a8ac0  lea     rcx, [rbp+0E8h]
0x1800a8ac7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a8acc  nop
0x1800a8acd  lea     rax, [rbp+44h]
0x1800a8ad1  mov     [rsp+78h+var_48], rax; __int64
0x1800a8ad6  mov     qword ptr [rsp+78h+cchCount2], r14; __int64
0x1800a8adb  mov     [rsp+78h+lpString2], rsi; __int64
0x1800a8ae0  mov     r9, rdi
0x1800a8ae3  lea     r8, [rbp+0E8h]
0x1800a8aea  mov     rcx, r15; struct cxl::TextWriter *
0x1800a8aed  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V23@V23@J@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@22AEBJ@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring,std::wstring,std::wstring,long>(char const *,TraceFunction const &,std::wstring const &,std::wstring const &,std::wstring const &,long const &)
0x1800a8af2  nop
0x1800a8af3  lea     rcx, [rbp+0E8h]
0x1800a8afa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8aff  nop
0x1800a8b00  lea     rcx, [rbp+108h]
0x1800a8b07  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8b0c  nop
0x1800a8b0d  lea     rcx, [rbp+128h]
0x1800a8b14  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8b19  nop
0x1800a8b1a  lea     rcx, [rbp+0A8h]
0x1800a8b21  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8b26  nop
0x1800a8b27  lea     rcx, [rbp+0C8h]
0x1800a8b2e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8b33  mov     rax, [rbp+50h]
0x1800a8b37  mov     rdx, [rax+8]
0x1800a8b3b  add     rdx, 38h ; '8'
0x1800a8b3f  lea     rcx, [rbp+98h]
0x1800a8b46  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x1800a8b4b  nop
0x1800a8b4c  lea     rdx, [rbp+0A8h]
0x1800a8b53  mov     rcx, [rax]
0x1800a8b56  call    ?get_id@FacadeItem@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::FacadeItem::get_id(void)
0x1800a8b5b  nop
0x1800a8b5c  mov     rcx, rax
0x1800a8b5f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800a8b64  mov     rdi, rax
0x1800a8b67  lea     rdx, [rbx+40h]
0x1800a8b6b  lea     rcx, [rbp+88h]
0x1800a8b72  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x1800a8b77  nop
0x1800a8b78  lea     rdx, [rbp+0C8h]
0x1800a8b7f  mov     rcx, [rax]
0x1800a8b82  call    ?get_id@FacadeItem@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::FacadeItem::get_id(void)
0x1800a8b87  mov     rcx, rax
0x1800a8b8a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800a8b8f  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800a8b97  mov     [rsp+78h+lpString2], rdi; lpString2
0x1800a8b9c  or      r9d, 0FFFFFFFFh; cchCount1
0x1800a8ba0  mov     r8, rax; lpString1
0x1800a8ba3  lea     edx, [r9+2]; dwCmpFlags
0x1800a8ba7  mov     ecx, 400h; Locale
0x1800a8bac  call    cs:__imp_CompareStringW
0x1800a8bb3  nop     dword ptr [rax+rax+00h]
0x1800a8bb8  cmp     eax, 2
0x1800a8bbb  setz    bl
0x1800a8bbe  lea     rcx, [rbp+0C8h]
0x1800a8bc5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8bca  nop
0x1800a8bcb  mov     rcx, [rbp+90h]; this
0x1800a8bd2  test    rcx, rcx
0x1800a8bd5  jz      short loc_1800A8BDD
0x1800a8bd7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a8bdc  nop
0x1800a8bdd  lea     rcx, [rbp+0A8h]
0x1800a8be4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a8be9  nop
0x1800a8bea  mov     rcx, [rbp+0A0h]; this
0x1800a8bf1  test    rcx, rcx
0x1800a8bf4  jz      short loc_1800A8BFB
0x1800a8bf6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a8bfb  test    bl, bl
0x1800a8bfd  jz      short loc_1800A8C09
0x1800a8bff  xor     edx, edx; pThrowInfo
0x1800a8c01  xor     ecx, ecx; pExceptionObject
0x1800a8c03  call    _CxxThrowException_0
0x1800a8c09  mov     rax, 0
0x1800a8c13  add     rsp, 48h
0x1800a8c17  pop     r15
0x1800a8c19  pop     r14
0x1800a8c1b  pop     rdi
0x1800a8c1c  pop     rsi
0x1800a8c1d  pop     rbp
0x1800a8c1e  pop     rbx
0x1800a8c1f  retn
```
