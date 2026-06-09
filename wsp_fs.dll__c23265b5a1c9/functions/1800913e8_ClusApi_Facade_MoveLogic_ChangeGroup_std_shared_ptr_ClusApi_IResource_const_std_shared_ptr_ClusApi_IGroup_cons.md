# ClusApi::Facade::MoveLogic::ChangeGroup(std::shared_ptr<ClusApi::IResource> const &,std::shared_ptr<ClusApi::IGroup> const &,std::shared_ptr<ClusApi::IGroup> const &,wchar_t const *)

- ea: `0x1800913e8`
- end: `0x180091698`
- name: `?ChangeGroup@MoveLogic@Facade@ClusApi@@IEAAXAEBV?$shared_ptr@UIResource@ClusApi@@@std@@AEBV?$shared_ptr@UIGroup@ClusApi@@@5@1PEB_W@Z`
- size: `688`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800930ec`
- `0x180093200`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005e64`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000d6a4`
- `0x18000e14c`
- `0x180027b64`
- `0x180085620`
- `0x18008f6d0`
- `0x18008f75c`
- `0x1800913e8`
- `0x180093790`
- `0x1800938fc`
- `0x180094a28`
- `0x180094afc`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800914a1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800914a1`

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
      std::wstring::wstring(v41, v40);
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
      std::wstring::wstring(v40, v41);
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
        std::_Deallocate<16>(v19, 32);
        v19 = v20;
      }
      while ( v20 );
    }
    std::_Deallocate<16>(v30, 32);
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
0x1800913e8  push    rbx
0x1800913ea  push    rsi
0x1800913eb  push    rdi
0x1800913ec  push    r12
0x1800913ee  push    r14
0x1800913f0  push    r15
0x1800913f2  sub     rsp, 1E8h
0x1800913f9  mov     rax, cs:__security_cookie
0x180091400  xor     rax, rsp
0x180091403  mov     [rsp+218h+var_48], rax
0x18009140b  mov     r12, r9
0x18009140e  mov     r14, r8
0x180091411  mov     r15, rdx
0x180091414  mov     rdi, rcx
0x180091417  mov     [rsp+218h+var_1C8], rcx
0x18009141c  mov     [rsp+218h+var_1E0], rdx
0x180091421  mov     [rsp+218h+var_1C0], r8
0x180091426  mov     [rsp+218h+var_1B8], r9
0x18009142b  mov     rsi, [rsp+218h+arg_20]
0x180091433  mov     [rsp+218h+var_1B0], rsi
0x180091438  lea     rcx, [rsp+218h+var_1A8]
0x18009143d  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x180091442  nop
0x180091443  mov     rdx, r14
0x180091446  lea     rcx, [rsp+218h+var_1D8]
0x18009144b  call    ?CreateGroupFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIGroup@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateGroupFacade(std::shared_ptr<ClusApi::IGroup> const &)
0x180091450  nop
0x180091451  lea     rdx, [rsp+218h+var_188]
0x180091459  mov     rcx, [rax]
0x18009145c  call    ?get_ownerNodeName@GroupFacade@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::GroupFacade::get_ownerNodeName(void)
0x180091461  nop
0x180091462  mov     rcx, rax
0x180091465  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18009146a  mov     rbx, rax
0x18009146d  lea     rdx, [rsp+218h+var_168]
0x180091475  mov     rcx, [rsp+218h+var_1A8]
0x18009147a  call    ?get_ownerNodeName@ResourceFacade@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::ResourceFacade::get_ownerNodeName(void)
0x18009147f  mov     rcx, rax
0x180091482  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180091487  or      r9d, 0FFFFFFFFh; cchCount1
0x18009148b  mov     [rsp+218h+cchCount2], r9d; cchCount2
0x180091490  mov     [rsp+218h+lpString2], rbx; lpString2
0x180091495  mov     r8, rax; lpString1
0x180091498  lea     edx, [r9+2]; dwCmpFlags
0x18009149c  mov     ecx, 400h; Locale
0x1800914a1  call    cs:__imp_CompareStringW
0x1800914a8  nop     dword ptr [rax+rax+00h]
0x1800914ad  lea     ebx, [rax-2]
0x1800914b0  lea     rcx, [rsp+218h+var_168]
0x1800914b8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800914bd  nop
0x1800914be  lea     rcx, [rsp+218h+var_188]
0x1800914c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800914cb  nop
0x1800914cc  mov     rcx, [rsp+218h+var_1D0]; this
0x1800914d1  test    rcx, rcx
0x1800914d4  jz      short loc_1800914DB
0x1800914d6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800914db  test    ebx, ebx
0x1800914dd  jz      loc_18009162F
0x1800914e3  lea     rcx, [rsp+218h+var_1D8]
0x1800914e8  call    ??0?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<ClusApi::IResource>>::list<std::shared_ptr<ClusApi::IResource>>(void)
0x1800914ed  nop
0x1800914ee  mov     r9, rsi
0x1800914f1  lea     r8, [rsp+218h+var_1D8]
0x1800914f6  lea     rdx, [rsp+218h+var_1A8]
0x1800914fb  mov     rcx, rdi
0x1800914fe  call    ?OfflineResources@MoveLogic@Facade@ClusApi@@AEAAXAEBV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEAV?$list@V?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@V?$allocator@V?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@@2@@5@PEB_W@Z; ClusApi::Facade::MoveLogic::OfflineResources(std::shared_ptr<ClusApi::Facade::ResourceFacade> const &,std::list<std::shared_ptr<ClusApi::Facade::ResourceFacade>> &,wchar_t const *)
0x180091503  nop
0x180091504  mov     rcx, [r15]
0x180091507  mov     rax, [rcx]
0x18009150a  mov     r8, rsi
0x18009150d  mov     rdx, r14
0x180091510  mov     rax, [rax+0E8h]
0x180091517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009151c  mov     ebx, eax
0x18009151e  test    eax, eax
0x180091520  jns     short loc_18009156D
0x180091522  lea     rdx, aPtrresourceCha; "ptrResource->ChangeGroup( ptrGroup, rea"...
0x180091529  lea     rcx, [rsp+218h+var_148]
0x180091531  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091536  nop
0x180091537  mov     [rsp+218h+var_1E8], ebx
0x18009153b  mov     [rsp+218h+var_1E4], 2
0x180091543  mov     r8, rax
0x180091546  lea     rdx, [rsp+218h+var_1E8]
0x18009154b  lea     rcx, [rsp+218h+pExceptionObject]
0x180091553  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180091558  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009155f  lea     rcx, [rsp+218h+pExceptionObject]; pExceptionObject
0x180091567  call    _CxxThrowException_0
0x18009156d  mov     rax, [rdi]
0x180091570  mov     rcx, rdi
0x180091573  mov     rax, [rax+8]
0x180091577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009157c  nop
0x18009157d  mov     r8, rsi
0x180091580  lea     rdx, [rsp+218h+var_1D8]
0x180091585  call    ?OnlineResources@MoveLogic@Facade@ClusApi@@AEAAXAEBV?$list@V?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@V?$allocator@V?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@@2@@std@@PEB_W@Z; ClusApi::Facade::MoveLogic::OnlineResources(std::list<std::shared_ptr<ClusApi::Facade::ResourceFacade>> const &,wchar_t const *)
0x18009158a  nop
0x18009158b  jmp     short loc_18009159C
0x18009158d  mov     rdi, [rsp+218h+var_1C8]
0x180091592  mov     r14, [rsp+218h+var_1C0]
0x180091597  mov     r12, [rsp+218h+var_1B8]
0x18009159c  mov     rax, [rdi]
0x18009159f  xor     r9d, r9d
0x1800915a2  mov     r8, r14
0x1800915a5  mov     rdx, r12
0x1800915a8  mov     rcx, rdi
0x1800915ab  mov     rax, [rax+10h]
0x1800915af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800915b4  nop
0x1800915b5  mov     rcx, [rsp+218h+var_1D8]
0x1800915ba  mov     rax, [rcx+8]
0x1800915be  mov     qword ptr [rax], 0
0x1800915c5  mov     rdi, [rcx]
0x1800915c8  test    rdi, rdi
0x1800915cb  jz      short loc_1800915EE
0x1800915cd  mov     rbx, [rdi]
0x1800915d0  lea     rcx, [rdi+10h]
0x1800915d4  call    ??_G?$shared_ptr@UIDiskPartition@ClusApi@@@std@@QEAAPEAXI@Z; std::shared_ptr<ClusApi::IDiskPartition>::`scalar deleting destructor'(uint)
0x1800915d9  mov     edx, 20h ; ' '
0x1800915de  mov     rcx, rdi
0x1800915e1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800915e6  mov     rdi, rbx
0x1800915e9  test    rbx, rbx
0x1800915ec  jnz     short loc_1800915CD
0x1800915ee  mov     edx, 20h ; ' '
0x1800915f3  mov     rcx, [rsp+218h+var_1D8]
0x1800915f8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800915fd  nop
0x1800915fe  mov     rcx, [rsp+218h+var_1A0]; this
0x180091603  test    rcx, rcx
0x180091606  jz      short loc_18009160D
0x180091608  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009160d  mov     rcx, [rsp+218h+var_48]
0x180091615  xor     rcx, rsp; StackCookie
0x180091618  call    __security_check_cookie
0x18009161d  add     rsp, 1E8h
0x180091624  pop     r15
0x180091626  pop     r14
0x180091628  pop     r12
0x18009162a  pop     rdi
0x18009162b  pop     rsi
0x18009162c  pop     rbx
0x18009162d  retn
0x18009162f  mov     rcx, [r15]
0x180091632  mov     rax, [rcx]
0x180091635  mov     r8, rsi
0x180091638  mov     rdx, r14
0x18009163b  mov     rax, [rax+0E8h]
0x180091642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091647  mov     ebx, eax
0x180091649  test    eax, eax
0x18009164b  jns     short loc_1800915FE
0x18009164d  lea     rdx, aPtrresourceCha; "ptrResource->ChangeGroup( ptrGroup, rea"...
0x180091654  lea     rcx, [rsp+218h+var_148]
0x18009165c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091661  nop
0x180091662  mov     dword ptr [rsp+218h+var_1E0], ebx
0x180091666  mov     dword ptr [rsp+218h+var_1E0+4], 2
0x18009166e  mov     r8, rax
0x180091671  lea     rdx, [rsp+218h+var_1E0]
0x180091676  lea     rcx, [rsp+218h+var_B8]
0x18009167e  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180091683  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009168a  lea     rcx, [rsp+218h+var_B8]; pExceptionObject
0x180091692  call    _CxxThrowException_0
```
