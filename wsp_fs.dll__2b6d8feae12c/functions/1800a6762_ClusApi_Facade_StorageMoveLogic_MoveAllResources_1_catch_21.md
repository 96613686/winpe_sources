# _ClusApi::Facade::StorageMoveLogic::MoveAllResources_::_1_::catch$21

- ea: `0x1800a6762`
- end: `0x1800a6978`
- name: `_ClusApi::Facade::StorageMoveLogic::MoveAllResources_::_1_::catch$21`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1800034a4`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000c284`
- `0x18000d250`
- `0x18000dd74`
- `0x18000e6f4`
- `0x18001c2f8`
- `0x18008d4a8`
- `0x18008dd58`
- `0x180092710`
- `0x1800a6762`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a6909`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a6909`

## string_xrefs

- `0x1800a6802`: `ClusApi::Facade::StorageMoveLogic::MoveAllResources`

## pseudocode

```c
__int64 __fastcall ClusApi::Facade::StorageMoveLogic::MoveAllResources_::_1_::catch_21(__int64 a1, __int64 a2)
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
  *(_DWORD *)(a2 + 68) = cxl::ErrorCode::GetHr((cxl::ErrorCode *)(*(_QWORD *)(a2 + 152) + 88LL));
  v4 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a2 + 88) + 48LL))(**(_QWORD **)(a2 + 88));
  v5 = std::wstring::wstring(a2 + 224, v4);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a2 + 96) + 48LL))(**(_QWORD **)(a2 + 96));
  v7 = std::wstring::wstring(a2 + 192, v6);
  v8 = *(_QWORD *)(a2 + 72);
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 64) + 48LL))(*(_QWORD *)(v8 + 64));
  std::wstring::wstring(a2 + 320, v9);
  std::wstring::wstring(a2 + 288, L"ClusApi::Facade::StorageMoveLogic::MoveAllResources");
  std::wstring::wstring(a2 + 256);
  cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring,std::wstring,std::wstring,long>(v3, v7, v5, a2 + 68);
  std::wstring::_Tidy_deallocate(a2 + 256);
  std::wstring::_Tidy_deallocate(a2 + 288);
  std::wstring::_Tidy_deallocate(a2 + 320);
  std::wstring::_Tidy_deallocate(a2 + 192);
  std::wstring::_Tidy_deallocate(a2 + 224);
  ResourceFacade = (_QWORD *)ClusApi::Facade::FacadeFactory::CreateResourceFacade(
                               a2 + 176,
                               *(_QWORD *)(*(_QWORD *)(a2 + 80) + 8LL) + 56LL);
  id = ClusApi::Facade::FacadeItem::get_id(*ResourceFacade, a2 + 192);
  lpString2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(id);
  v13 = (_QWORD *)ClusApi::Facade::FacadeFactory::CreateResourceFacade(a2 + 160, v8 + 64);
  v14 = ClusApi::Facade::FacadeItem::get_id(*v13, a2 + 224);
  v15 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
  v16 = CompareStringW(0x400u, 1u, v15, -1, lpString2, -1) == 2;
  std::wstring::_Tidy_deallocate(a2 + 224);
  v17 = *(std::_Ref_count_base **)(a2 + 168);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  std::wstring::_Tidy_deallocate(a2 + 192);
  v18 = *(std::_Ref_count_base **)(a2 + 184);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( v16 )
    throw;
  return 0;
}

```

## disassembly

```asm
0x1800a6762  mov     [rsp+arg_8], rdx
0x1800a6767  push    rbx
0x1800a6768  push    rbp
0x1800a6769  push    rsi
0x1800a676a  push    rdi
0x1800a676b  push    r14
0x1800a676d  push    r15
0x1800a676f  sub     rsp, 48h
0x1800a6773  mov     rbp, rdx
0x1800a6776  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800a677b  lea     r15, [rax+28h]
0x1800a677f  mov     rcx, [rbp+98h]
0x1800a6786  add     rcx, 58h ; 'X'; this
0x1800a678a  call    ?GetHr@ErrorCode@cxl@@QEBAJXZ; cxl::ErrorCode::GetHr(void)
0x1800a678f  mov     [rbp+44h], eax
0x1800a6792  mov     rax, [rbp+58h]
0x1800a6796  mov     rcx, [rax]
0x1800a6799  mov     rax, [rcx]
0x1800a679c  mov     rax, [rax+30h]
0x1800a67a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a67a5  mov     rdx, rax
0x1800a67a8  lea     rcx, [rbp+0E0h]
0x1800a67af  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a67b4  mov     r14, rax
0x1800a67b7  mov     rcx, [rbp+60h]
0x1800a67bb  mov     rcx, [rcx]
0x1800a67be  mov     rdx, [rcx]
0x1800a67c1  mov     rax, [rdx+30h]
0x1800a67c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a67ca  mov     rdx, rax
0x1800a67cd  lea     rcx, [rbp+0C0h]
0x1800a67d4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a67d9  mov     rsi, rax
0x1800a67dc  mov     rbx, [rbp+48h]
0x1800a67e0  mov     rcx, [rbx+40h]
0x1800a67e4  mov     rdx, [rcx]
0x1800a67e7  mov     rax, [rdx+30h]
0x1800a67eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a67f0  mov     rdx, rax
0x1800a67f3  lea     rcx, [rbp+140h]
0x1800a67fa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a67ff  mov     rdi, rax
0x1800a6802  lea     rdx, aClusapiFacadeS_0; "ClusApi::Facade::StorageMoveLogic::Move"...
0x1800a6809  lea     rcx, [rbp+120h]
0x1800a6810  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a6815  nop
0x1800a6816  lea     rdx, [rbp+120h]
0x1800a681d  lea     rcx, [rbp+100h]
0x1800a6824  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a6829  nop
0x1800a682a  lea     rax, [rbp+44h]
0x1800a682e  mov     [rsp+78h+var_48], rax; __int64
0x1800a6833  mov     qword ptr [rsp+78h+cchCount2], r14; __int64
0x1800a6838  mov     [rsp+78h+lpString2], rsi; __int64
0x1800a683d  mov     r9, rdi
0x1800a6840  lea     r8, [rbp+100h]
0x1800a6847  mov     rcx, r15; struct cxl::TextWriter *
0x1800a684a  call    ??$WriteLine@DUTraceFunction@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V23@V23@J@TextWriter@cxl@@QEAAXPEBDAEBUTraceFunction@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@22AEBJ@Z; cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring,std::wstring,std::wstring,long>(char const *,TraceFunction const &,std::wstring const &,std::wstring const &,std::wstring const &,long const &)
0x1800a684f  nop
0x1800a6850  lea     rcx, [rbp+100h]
0x1800a6857  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a685c  nop
0x1800a685d  lea     rcx, [rbp+120h]
0x1800a6864  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6869  nop
0x1800a686a  lea     rcx, [rbp+140h]
0x1800a6871  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6876  nop
0x1800a6877  lea     rcx, [rbp+0C0h]
0x1800a687e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6883  nop
0x1800a6884  lea     rcx, [rbp+0E0h]
0x1800a688b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6890  mov     rax, [rbp+50h]
0x1800a6894  mov     rdx, [rax+8]
0x1800a6898  add     rdx, 38h ; '8'
0x1800a689c  lea     rcx, [rbp+0B0h]
0x1800a68a3  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x1800a68a8  nop
0x1800a68a9  lea     rdx, [rbp+0C0h]
0x1800a68b0  mov     rcx, [rax]
0x1800a68b3  call    ?get_id@FacadeItem@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::FacadeItem::get_id(void)
0x1800a68b8  nop
0x1800a68b9  mov     rcx, rax
0x1800a68bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800a68c1  mov     rdi, rax
0x1800a68c4  lea     rdx, [rbx+40h]
0x1800a68c8  lea     rcx, [rbp+0A0h]
0x1800a68cf  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x1800a68d4  nop
0x1800a68d5  lea     rdx, [rbp+0E0h]
0x1800a68dc  mov     rcx, [rax]
0x1800a68df  call    ?get_id@FacadeItem@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::FacadeItem::get_id(void)
0x1800a68e4  mov     rcx, rax
0x1800a68e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800a68ec  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800a68f4  mov     [rsp+78h+lpString2], rdi; lpString2
0x1800a68f9  or      r9d, 0FFFFFFFFh; cchCount1
0x1800a68fd  mov     r8, rax; lpString1
0x1800a6900  lea     edx, [r9+2]; dwCmpFlags
0x1800a6904  mov     ecx, 400h; Locale
0x1800a6909  call    cs:__imp_CompareStringW
0x1800a690f  cmp     eax, 2
0x1800a6912  setz    bl
0x1800a6915  lea     rcx, [rbp+0E0h]
0x1800a691c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6921  nop
0x1800a6922  mov     rcx, [rbp+0A8h]; this
0x1800a6929  test    rcx, rcx
0x1800a692c  jz      short loc_1800A6934
0x1800a692e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a6933  nop
0x1800a6934  lea     rcx, [rbp+0C0h]
0x1800a693b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6940  nop
0x1800a6941  mov     rcx, [rbp+0B8h]; this
0x1800a6948  test    rcx, rcx
0x1800a694b  jz      short loc_1800A6952
0x1800a694d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800a6952  test    bl, bl
0x1800a6954  jz      short loc_1800A6960
0x1800a6956  xor     edx, edx; pThrowInfo
0x1800a6958  xor     ecx, ecx; pExceptionObject
0x1800a695a  call    _CxxThrowException_0
0x1800a6960  mov     rax, 0
0x1800a696a  add     rsp, 48h
0x1800a696e  pop     r15
0x1800a6970  pop     r14
0x1800a6972  pop     rdi
0x1800a6973  pop     rsi
0x1800a6974  pop     rbp
0x1800a6975  pop     rbx
0x1800a6976  retn
```
