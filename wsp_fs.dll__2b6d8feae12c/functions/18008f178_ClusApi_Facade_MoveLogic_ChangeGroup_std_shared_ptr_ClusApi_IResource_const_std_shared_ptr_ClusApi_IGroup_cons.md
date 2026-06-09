# ClusApi::Facade::MoveLogic::ChangeGroup(std::shared_ptr<ClusApi::IResource> const &,std::shared_ptr<ClusApi::IGroup> const &,std::shared_ptr<ClusApi::IGroup> const &,wchar_t const *)

- ea: `0x18008f178`
- end: `0x18008f421`
- name: `?ChangeGroup@MoveLogic@Facade@ClusApi@@IEAAXAEBV?$shared_ptr@UIResource@ClusApi@@@std@@AEBV?$shared_ptr@UIGroup@ClusApi@@@5@1PEB_W@Z`
- size: `681`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180090e48`
- `0x180090fe0`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005d94`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000c284`
- `0x18000d33c`
- `0x18000dd74`
- `0x180026e64`
- `0x180083580`
- `0x18008d420`
- `0x18008d4a8`
- `0x18008f178`
- `0x1800915dc`
- `0x1800917b0`
- `0x1800928b8`
- `0x18009298c`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008f231`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008f231`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ClusApi::Facade::MoveLogic::ChangeGroup(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r12
  __int64 v6; // r14
  __int64 v8; // rdi
  _QWORD *v9; // rax
  __int64 ownerNodeName; // rax
  const WCHAR *lpString2; // rbx
  __int64 v12; // rax
  const WCHAR *v13; // rax
  int v14; // ebx
  int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rcx
  _QWORD **v18; // rcx
  _QWORD *v19; // rdi
  _QWORD *v20; // rbx
  int v21; // ebx
  __int64 v22; // rax
  struct cxl::TextWriter *v23; // rdi
  __int64 v24; // rax
  struct cxl::TextWriter *v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rcx
  _DWORD v28[2]; // [rsp+30h] [rbp-1E8h] BYREF
  _QWORD *v29; // [rsp+38h] [rbp-1E0h] BYREF
  _QWORD **v30; // [rsp+40h] [rbp-1D8h] BYREF
  std::_Ref_count_base *v31; // [rsp+48h] [rbp-1D0h]
  __int64 v32; // [rsp+50h] [rbp-1C8h]
  __int64 v33; // [rsp+58h] [rbp-1C0h]
  __int64 v34; // [rsp+60h] [rbp-1B8h]
  __int64 v35; // [rsp+68h] [rbp-1B0h]
  __int64 v36; // [rsp+70h] [rbp-1A8h] BYREF
  std::_Ref_count_base *v37; // [rsp+78h] [rbp-1A0h]
  const cxl::Exception *v38; // [rsp+80h] [rbp-198h] BYREF
  const cxl::Exception *v39; // [rsp+88h] [rbp-190h] BYREF
  _BYTE v40[32]; // [rsp+90h] [rbp-188h] BYREF
  _BYTE v41[32]; // [rsp+B0h] [rbp-168h] BYREF
  _BYTE v42[32]; // [rsp+D0h] [rbp-148h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+F0h] [rbp-128h] BYREF
  _BYTE v44[112]; // [rsp+160h] [rbp-B8h] BYREF

  v5 = a4;
  v6 = a3;
  v8 = a1;
  v32 = a1;
  v29 = a2;
  v33 = a3;
  v34 = a4;
  v35 = a5;
  ClusApi::Facade::FacadeFactory::CreateResourceFacade(&v36, a2);
  v9 = (_QWORD *)ClusApi::Facade::FacadeFactory::CreateGroupFacade(&v30, v6);
  ownerNodeName = ClusApi::Facade::GroupFacade::get_ownerNodeName(*v9, v40);
  lpString2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(ownerNodeName);
  v12 = ClusApi::Facade::ResourceFacade::get_ownerNodeName(v36, v41);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v12);
  v14 = CompareStringW(0x400u, 1u, v13, -1, lpString2, -1) - 2;
  std::wstring::_Tidy_deallocate(v41);
  std::wstring::_Tidy_deallocate(v40);
  if ( v31 )
    std::_Ref_count_base::_Decref(v31);
  if ( v14 )
  {
    std::list<std::shared_ptr<ClusApi::IResource>>::list<std::shared_ptr<ClusApi::IResource>>(&v30);
    ClusApi::Facade::MoveLogic::OfflineResources(v8, &v36, &v30, a5);
    try
    {
      v15 = (*(__int64 (**)(void))(*(_QWORD *)*a2 + 232LL))();
      if ( v15 < 0 )
      {
        v16 = std::wstring::wstring(v42, L"ptrResource->ChangeGroup( ptrGroup, reason )");
        v28[0] = v15;
        v28[1] = 2;
        cxl::Exception::Exception(pExceptionObject, v28, v16);
        throw (cxl::Exception *)pExceptionObject;
      }
    }
    catch ( const cxl::Exception *v39 )
    {
      v25 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
      v28[0] = cxl::ErrorCode::GetHr((const cxl::Exception *)((char *)v39 + 88));
      v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 48LL))(*v29);
      std::wstring::wstring(v42, v26);
      std::wstring::wstring(v40, L"ClusApi::Facade::MoveLogic::ChangeGroup");
      std::wstring::wstring(v41);
      cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring,long>(
        v25,
        "{0} An error occurred moving resource '{1}' (0x{2:X}).  The resources which were taken offline in preparation to"
        " move will be brought back online.",
        (__int64)v28);
      std::wstring::_Tidy_deallocate(v41);
      std::wstring::_Tidy_deallocate(v40);
      std::wstring::_Tidy_deallocate(v42);
      ClusApi::Facade::MoveLogic::OnlineResources(v27, &v30, v35);
      throw;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    try
    {
      ClusApi::Facade::MoveLogic::OnlineResources(v17, &v30, a5);
    }
    catch ( const cxl::Exception *v38 )
    {
      v23 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 40);
      v28[0] = cxl::ErrorCode::GetHr((const cxl::Exception *)((char *)v38 + 88));
      v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 48LL))(*v29);
      std::wstring::wstring(v42, v24);
      std::wstring::wstring(v41, L"ClusApi::Facade::MoveLogic::ChangeGroup");
      std::wstring::wstring(v40);
      cxl::TextWriter::WriteLine<char,TraceFunction,std::wstring,long>(
        v23,
        "{0} An error occurred bringing resource '{1}' online (0x{2:X}).",
        (__int64)v28);
      std::wstring::_Tidy_deallocate(v40);
      std::wstring::_Tidy_deallocate(v41);
      std::wstring::_Tidy_deallocate(v42);
      (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v32 + 16LL))(v32, v34, v33, 1);
      v8 = v32;
      v6 = v33;
      v5 = v34;
    }
    (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v8 + 16LL))(v8, v5, v6, 0);
    v18 = v30;
    *v30[1] = 0;
    v19 = *v18;
    if ( *v18 )
    {
      do
      {
        v20 = (_QWORD *)*v19;
        std::shared_ptr<ClusApi::IDiskPartition>::`scalar deleting destructor'(v19 + 2);
        std::_Deallocate<16>(v19, 0x20u);
        v19 = v20;
      }
      while ( v20 );
    }
    std::_Deallocate<16>(v30, 0x20u);
  }
  else
  {
    v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a2 + 232LL))(*a2, v6, a5);
    if ( v21 < 0 )
    {
      v22 = std::wstring::wstring(v42, L"ptrResource->ChangeGroup( ptrGroup, reason )");
      v29 = (_QWORD *)((unsigned int)v21 | 0x200000000LL);
      cxl::Exception::Exception(v44, &v29, v22);
      throw (cxl::Exception *)v44;
    }
  }
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
}

```

## disassembly

```asm
0x18008f178  push    rbx
0x18008f17a  push    rsi
0x18008f17b  push    rdi
0x18008f17c  push    r12
0x18008f17e  push    r14
0x18008f180  push    r15
0x18008f182  sub     rsp, 1E8h
0x18008f189  mov     rax, cs:__security_cookie
0x18008f190  xor     rax, rsp
0x18008f193  mov     [rsp+218h+var_48], rax
0x18008f19b  mov     r12, r9
0x18008f19e  mov     r14, r8
0x18008f1a1  mov     r15, rdx
0x18008f1a4  mov     rdi, rcx
0x18008f1a7  mov     [rsp+218h+var_1C8], rcx
0x18008f1ac  mov     [rsp+218h+var_1E0], rdx
0x18008f1b1  mov     [rsp+218h+var_1C0], r8
0x18008f1b6  mov     [rsp+218h+var_1B8], r9
0x18008f1bb  mov     rsi, [rsp+218h+arg_20]
0x18008f1c3  mov     [rsp+218h+var_1B0], rsi
0x18008f1c8  lea     rcx, [rsp+218h+var_1A8]
0x18008f1cd  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x18008f1d2  nop
0x18008f1d3  mov     rdx, r14
0x18008f1d6  lea     rcx, [rsp+218h+var_1D8]
0x18008f1db  call    ?CreateGroupFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIGroup@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateGroupFacade(std::shared_ptr<ClusApi::IGroup> const &)
0x18008f1e0  nop
0x18008f1e1  lea     rdx, [rsp+218h+var_188]
0x18008f1e9  mov     rcx, [rax]
0x18008f1ec  call    ?get_ownerNodeName@GroupFacade@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::GroupFacade::get_ownerNodeName(void)
0x18008f1f1  nop
0x18008f1f2  mov     rcx, rax
0x18008f1f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008f1fa  mov     rbx, rax
0x18008f1fd  lea     rdx, [rsp+218h+var_168]
0x18008f205  mov     rcx, [rsp+218h+var_1A8]
0x18008f20a  call    ?get_ownerNodeName@ResourceFacade@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::ResourceFacade::get_ownerNodeName(void)
0x18008f20f  mov     rcx, rax
0x18008f212  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008f217  or      r9d, 0FFFFFFFFh; cchCount1
0x18008f21b  mov     [rsp+218h+cchCount2], r9d; cchCount2
0x18008f220  mov     [rsp+218h+lpString2], rbx; lpString2
0x18008f225  mov     r8, rax; lpString1
0x18008f228  lea     edx, [r9+2]; dwCmpFlags
0x18008f22c  mov     ecx, 400h; Locale
0x18008f231  call    cs:__imp_CompareStringW
0x18008f237  lea     ebx, [rax-2]
0x18008f23a  lea     rcx, [rsp+218h+var_168]
0x18008f242  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f247  nop
0x18008f248  lea     rcx, [rsp+218h+var_188]
0x18008f250  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f255  nop
0x18008f256  mov     rcx, [rsp+218h+var_1D0]; this
0x18008f25b  test    rcx, rcx
0x18008f25e  jz      short loc_18008F265
0x18008f260  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f265  test    ebx, ebx
0x18008f267  jz      loc_18008F3B8
0x18008f26d  lea     rcx, [rsp+218h+var_1D8]
0x18008f272  call    ??0?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<ClusApi::IResource>>::list<std::shared_ptr<ClusApi::IResource>>(void)
0x18008f277  nop
0x18008f278  mov     r9, rsi
0x18008f27b  lea     r8, [rsp+218h+var_1D8]
0x18008f280  lea     rdx, [rsp+218h+var_1A8]
0x18008f285  mov     rcx, rdi
0x18008f288  call    ?OfflineResources@MoveLogic@Facade@ClusApi@@AEAAXAEBV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEAV?$list@V?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@V?$allocator@V?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@@2@@5@PEB_W@Z; ClusApi::Facade::MoveLogic::OfflineResources(std::shared_ptr<ClusApi::Facade::ResourceFacade> const &,std::list<std::shared_ptr<ClusApi::Facade::ResourceFacade>> &,wchar_t const *)
0x18008f28d  nop
0x18008f28e  mov     rcx, [r15]
0x18008f291  mov     rax, [rcx]
0x18008f294  mov     r8, rsi
0x18008f297  mov     rdx, r14
0x18008f29a  mov     rax, [rax+0E8h]
0x18008f2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f2a6  mov     ebx, eax
0x18008f2a8  test    eax, eax
0x18008f2aa  jns     short loc_18008F2F7
0x18008f2ac  lea     rdx, aPtrresourceCha; "ptrResource->ChangeGroup( ptrGroup, rea"...
0x18008f2b3  lea     rcx, [rsp+218h+var_148]
0x18008f2bb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008f2c0  nop
0x18008f2c1  mov     [rsp+218h+var_1E8], ebx
0x18008f2c5  mov     [rsp+218h+var_1E4], 2
0x18008f2cd  mov     r8, rax
0x18008f2d0  lea     rdx, [rsp+218h+var_1E8]
0x18008f2d5  lea     rcx, [rsp+218h+pExceptionObject]
0x18008f2dd  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18008f2e2  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18008f2e9  lea     rcx, [rsp+218h+pExceptionObject]; pExceptionObject
0x18008f2f1  call    _CxxThrowException_0
0x18008f2f7  mov     rax, [rdi]
0x18008f2fa  mov     rcx, rdi
0x18008f2fd  mov     rax, [rax+8]
0x18008f301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f306  nop
0x18008f307  mov     r8, rsi
0x18008f30a  lea     rdx, [rsp+218h+var_1D8]
0x18008f30f  call    ?OnlineResources@MoveLogic@Facade@ClusApi@@AEAAXAEBV?$list@V?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@V?$allocator@V?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@@2@@std@@PEB_W@Z; ClusApi::Facade::MoveLogic::OnlineResources(std::list<std::shared_ptr<ClusApi::Facade::ResourceFacade>> const &,wchar_t const *)
0x18008f314  nop
0x18008f315  jmp     short loc_18008F326
0x18008f317  mov     rdi, [rsp+218h+var_1C8]
0x18008f31c  mov     r14, [rsp+218h+var_1C0]
0x18008f321  mov     r12, [rsp+218h+var_1B8]
0x18008f326  mov     rax, [rdi]
0x18008f329  xor     r9d, r9d
0x18008f32c  mov     r8, r14
0x18008f32f  mov     rdx, r12
0x18008f332  mov     rcx, rdi
0x18008f335  mov     rax, [rax+10h]
0x18008f339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f33e  nop
0x18008f33f  mov     rcx, [rsp+218h+var_1D8]
0x18008f344  mov     rax, [rcx+8]
0x18008f348  mov     qword ptr [rax], 0
0x18008f34f  mov     rdi, [rcx]
0x18008f352  test    rdi, rdi
0x18008f355  jz      short loc_18008F378
0x18008f357  mov     rbx, [rdi]
0x18008f35a  lea     rcx, [rdi+10h]
0x18008f35e  call    ??_G?$shared_ptr@UIDiskPartition@ClusApi@@@std@@QEAAPEAXI@Z; std::shared_ptr<ClusApi::IDiskPartition>::`scalar deleting destructor'(uint)
0x18008f363  mov     edx, 20h ; ' '
0x18008f368  mov     rcx, rdi
0x18008f36b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008f370  mov     rdi, rbx
0x18008f373  test    rbx, rbx
0x18008f376  jnz     short loc_18008F357
0x18008f378  mov     edx, 20h ; ' '
0x18008f37d  mov     rcx, [rsp+218h+var_1D8]
0x18008f382  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008f387  nop
0x18008f388  mov     rcx, [rsp+218h+var_1A0]; this
0x18008f38d  test    rcx, rcx
0x18008f390  jz      short loc_18008F397
0x18008f392  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f397  mov     rcx, [rsp+218h+var_48]
0x18008f39f  xor     rcx, rsp; StackCookie
0x18008f3a2  call    __security_check_cookie
0x18008f3a7  add     rsp, 1E8h
0x18008f3ae  pop     r15
0x18008f3b0  pop     r14
0x18008f3b2  pop     r12
0x18008f3b4  pop     rdi
0x18008f3b5  pop     rsi
0x18008f3b6  pop     rbx
0x18008f3b7  retn
0x18008f3b8  mov     rcx, [r15]
0x18008f3bb  mov     rax, [rcx]
0x18008f3be  mov     r8, rsi
0x18008f3c1  mov     rdx, r14
0x18008f3c4  mov     rax, [rax+0E8h]
0x18008f3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f3d0  mov     ebx, eax
0x18008f3d2  test    eax, eax
0x18008f3d4  jns     short loc_18008F388
0x18008f3d6  lea     rdx, aPtrresourceCha; "ptrResource->ChangeGroup( ptrGroup, rea"...
0x18008f3dd  lea     rcx, [rsp+218h+var_148]
0x18008f3e5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008f3ea  nop
0x18008f3eb  mov     dword ptr [rsp+218h+var_1E0], ebx
0x18008f3ef  mov     dword ptr [rsp+218h+var_1E0+4], 2
0x18008f3f7  mov     r8, rax
0x18008f3fa  lea     rdx, [rsp+218h+var_1E0]
0x18008f3ff  lea     rcx, [rsp+218h+var_B8]
0x18008f407  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18008f40c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18008f413  lea     rcx, [rsp+218h+var_B8]; pExceptionObject
0x18008f41b  call    _CxxThrowException_0
```
