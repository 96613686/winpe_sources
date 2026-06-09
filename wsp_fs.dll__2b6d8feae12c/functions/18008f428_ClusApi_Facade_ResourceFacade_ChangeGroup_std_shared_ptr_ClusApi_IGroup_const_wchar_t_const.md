# ClusApi::Facade::ResourceFacade::ChangeGroup(std::shared_ptr<ClusApi::IGroup> const &,wchar_t const *)

- ea: `0x18008f428`
- end: `0x18008f6eb`
- name: `?ChangeGroup@ResourceFacade@Facade@ClusApi@@QEAA?AV?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@AEBV?$shared_ptr@UIGroup@ClusApi@@@5@PEB_W@Z`
- size: `707`
- prototype: `__int64 __fastcall(ClusApi::Facade::ResourceFacade *this)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180093930`

## callees

- `0x180002a70`
- `0x180002a94`
- `0x1800034a4`
- `0x180005d94`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000c168`
- `0x18000c284`
- `0x18000d298`
- `0x18000d33c`
- `0x18000dd74`
- `0x180056400`
- `0x180083580`
- `0x18008dfcc`
- `0x18008e010`
- `0x18008ecd0`
- `0x18008f428`
- `0x180092b10`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008f590`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008f590`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ClusApi::Facade::ResourceFacade::ChangeGroup(
        ClusApi::Facade::ResourceFacade *this,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v8; // rdx
  char *v9; // r14
  int v10; // ebx
  __int64 v11; // rax
  int v12; // ebx
  __int64 v13; // rax
  const WCHAR *v14; // rax
  PCNZWCH lpString2; // rdx
  _DWORD *v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  void *v22; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v23; // [rsp+40h] [rbp-C0h]
  std::_Ref_count_base *v24[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  _BYTE v26[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+C0h] [rbp-40h] BYREF

  v25 = a2;
  std::wstring::wstring(v26);
  std::wstring::wstring(v27);
  *(_OWORD *)v24 = 0;
  std::list<std::shared_ptr<ClusApi::IResource>>::list<std::shared_ptr<ClusApi::IResource>>(v8);
  v9 = (char *)this + 56;
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE *))(**((_QWORD **)this + 7) + 120LL))(
          *((_QWORD *)this + 7),
          0,
          0,
          v26);
  if ( v10 < 0 )
  {
    v11 = std::wstring::wstring(v28, L"_ptrResource->GetState( nullptr, nullptr, &ownerGroup )");
    v22 = (void *)((unsigned int)v10 | 0x200000000LL);
    cxl::Exception::Exception(pExceptionObject, &v22, v11);
    throw (cxl::Exception *)pExceptionObject;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a3 + 88LL))(*a3, v27);
  if ( v12 < 0 )
  {
    v13 = std::wstring::wstring(v28, L"ptrGroup->GetName( &groupName )");
    v22 = (void *)((unsigned int)v12 | 0x200000000LL);
    cxl::Exception::Exception(pExceptionObject, &v22, v13);
    throw (cxl::Exception *)pExceptionObject;
  }
  std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27);
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26);
  if ( CompareStringW(0x400u, 1u, v14, -1, lpString2, -1) != 2 )
  {
    if ( ClusApi::Facade::ResourceFacade::get_storage(this) )
    {
      v16 = operator new(0x38u);
      *(_OWORD *)v16 = 0;
      v16[2] = 1;
      v16[3] = 1;
      *(_QWORD *)v16 = &std::_Ref_count_obj2<ClusApi::Facade::StorageMoveLogic>::`vftable';
      std::_Construct_in_place<ClusApi::Facade::StorageMoveLogic,ClusApi::Facade::StorageMoveLogic::private_make_shared_tag,std::shared_ptr<ClusApi::IResource> &>(
        (_QWORD *)v16 + 2,
        v18,
        (__int64)v9);
    }
    else
    {
      v16 = operator new(0x40u);
      *(_OWORD *)v16 = 0;
      v16[2] = 1;
      v16[3] = 1;
      *(_QWORD *)v16 = &std::_Ref_count_obj2<ClusApi::Facade::NoStorageMoveLogic>::`vftable';
      std::_Construct_in_place<ClusApi::Facade::NoStorageMoveLogic,ClusApi::Facade::NoStorageMoveLogic::private_make_shared_tag,std::shared_ptr<ClusApi::IResource> &>(
        (__int64)(v16 + 4),
        v17,
        (__int64)v9);
    }
    v22 = v16 + 4;
    v23 = (std::_Ref_count_base *)v16;
    std::shared_ptr<ClusWmi::DataStore>::operator=(v24, &v22);
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    v19 = (**(__int64 (__fastcall ***)(std::_Ref_count_base *, void **, _QWORD *, _BYTE *, __int64))v24[0])(
            v24[0],
            &v22,
            a3,
            v26,
            a4);
    std::list<std::shared_ptr<ClusApi::IResource>>::operator=(a2, v19);
    std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(
      v20,
      v22);
    std::_Deallocate<16>(v22, 0x20u);
    if ( v24[1] )
      std::_Ref_count_base::_Decref(v24[1]);
  }
  std::wstring::_Tidy_deallocate(v27);
  std::wstring::_Tidy_deallocate(v26);
  return a2;
}

```

## disassembly

```asm
0x18008f428  push    rbp
0x18008f42a  push    rbx
0x18008f42b  push    rsi
0x18008f42c  push    rdi
0x18008f42d  push    r12
0x18008f42f  push    r13
0x18008f431  push    r14
0x18008f433  push    r15
0x18008f435  lea     rbp, [rsp-48h]
0x18008f43a  sub     rsp, 148h
0x18008f441  mov     rax, cs:__security_cookie
0x18008f448  xor     rax, rsp
0x18008f44b  mov     [rbp+80h+var_50], rax
0x18008f44f  mov     r12, r9
0x18008f452  mov     r15, r8
0x18008f455  mov     rsi, rdx
0x18008f458  mov     rdi, rcx
0x18008f45b  mov     [rsp+180h+var_128], rdx
0x18008f460  mov     r13d, 1
0x18008f466  mov     [rsp+180h+var_150], r13d
0x18008f46b  lea     rcx, [rsp+180h+var_120]
0x18008f470  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008f475  nop
0x18008f476  lea     rcx, [rbp+80h+var_100]
0x18008f47a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008f47f  nop
0x18008f480  xorps   xmm1, xmm1
0x18008f483  movdqu  xmmword ptr [rsp+180h+var_138], xmm1
0x18008f489  mov     rcx, rdx
0x18008f48c  call    ??0?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<ClusApi::IResource>>::list<std::shared_ptr<ClusApi::IResource>>(void)
0x18008f491  nop
0x18008f492  mov     [rsp+180h+var_150], r13d
0x18008f497  lea     r14, [rdi+38h]
0x18008f49b  mov     rcx, [r14]
0x18008f49e  mov     rax, [rcx]
0x18008f4a1  lea     r9, [rsp+180h+var_120]
0x18008f4a6  xor     r8d, r8d
0x18008f4a9  xor     edx, edx
0x18008f4ab  mov     rax, [rax+78h]
0x18008f4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f4b4  mov     ebx, eax
0x18008f4b6  test    eax, eax
0x18008f4b8  jns     short loc_18008F501
0x18008f4ba  lea     rdx, aPtrresourceGet_3; "_ptrResource->GetState( nullptr, nullpt"...
0x18008f4c1  lea     rcx, [rbp+80h+var_E0]
0x18008f4c5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008f4ca  nop
0x18008f4cb  mov     dword ptr [rsp+180h+var_148], ebx
0x18008f4cf  mov     dword ptr [rsp+180h+var_148+4], 2
0x18008f4d7  mov     r8, rax
0x18008f4da  lea     rdx, [rsp+180h+var_148]
0x18008f4df  lea     rcx, [rbp+80h+pExceptionObject]
0x18008f4e3  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18008f4e8  mov     [rsp+180h+var_150], 3
0x18008f4f0  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18008f4f7  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18008f4fb  call    _CxxThrowException_0
0x18008f501  mov     rcx, [r15]
0x18008f504  mov     rax, [rcx]
0x18008f507  lea     rdx, [rbp+80h+var_100]
0x18008f50b  mov     rax, [rax+58h]
0x18008f50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f514  mov     ebx, eax
0x18008f516  test    eax, eax
0x18008f518  jns     short loc_18008F561
0x18008f51a  lea     rdx, aPtrgroupGetnam; "ptrGroup->GetName( &groupName )"
0x18008f521  lea     rcx, [rbp+80h+var_E0]
0x18008f525  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008f52a  nop
0x18008f52b  mov     dword ptr [rsp+180h+var_148], ebx
0x18008f52f  mov     dword ptr [rsp+180h+var_148+4], 2
0x18008f537  mov     r8, rax
0x18008f53a  lea     rdx, [rsp+180h+var_148]
0x18008f53f  lea     rcx, [rbp+80h+pExceptionObject]
0x18008f543  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18008f548  mov     [rsp+180h+var_150], 5
0x18008f550  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18008f557  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18008f55b  call    _CxxThrowException_0
0x18008f561  lea     rcx, [rbp+80h+var_100]
0x18008f565  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008f56a  mov     rdx, rax
0x18008f56d  lea     rcx, [rsp+180h+var_120]
0x18008f572  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008f577  mov     r8, rax; lpString1
0x18008f57a  or      r9d, 0FFFFFFFFh; cchCount1
0x18008f57e  mov     [rsp+180h+cchCount2], r9d; cchCount2
0x18008f583  mov     [rsp+180h+lpString2], rdx; lpString2
0x18008f588  mov     edx, r13d; dwCmpFlags
0x18008f58b  mov     ecx, 400h; Locale
0x18008f590  call    cs:__imp_CompareStringW
0x18008f596  cmp     eax, 2
0x18008f599  jnz     short loc_18008F5A0
0x18008f59b  jmp     loc_18008F6B4
0x18008f5a0  mov     rcx, rdi; this
0x18008f5a3  call    ?get_storage@ResourceFacade@Facade@ClusApi@@QEBA_NXZ; ClusApi::Facade::ResourceFacade::get_storage(void)
0x18008f5a8  test    al, al
0x18008f5aa  jnz     short loc_18008F5F2
0x18008f5ac  mov     ecx, 40h ; '@'; Size
0x18008f5b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008f5b6  mov     rdi, rax
0x18008f5b9  mov     [rsp+180h+var_148], rax
0x18008f5be  xorps   xmm0, xmm0
0x18008f5c1  movups  xmmword ptr [rax], xmm0
0x18008f5c4  mov     [rax+8], r13d
0x18008f5c8  mov     [rax+0Ch], r13d
0x18008f5cc  lea     rax, ??_7?$_Ref_count_obj2@VNoStorageMoveLogic@Facade@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::Facade::NoStorageMoveLogic>::`vftable'
0x18008f5d3  mov     [rdi], rax
0x18008f5d6  lea     rbx, [rdi+10h]
0x18008f5da  mov     r8, r14
0x18008f5dd  mov     rcx, rbx
0x18008f5e0  call    ??$_Construct_in_place@VNoStorageMoveLogic@Facade@ClusApi@@Uprivate_make_shared_tag@123@AEAV?$shared_ptr@UIResource@ClusApi@@@std@@@std@@YAXAEAVNoStorageMoveLogic@Facade@ClusApi@@$$QEAUprivate_make_shared_tag@123@AEAV?$shared_ptr@UIResource@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::Facade::NoStorageMoveLogic,ClusApi::Facade::NoStorageMoveLogic::private_make_shared_tag,std::shared_ptr<ClusApi::IResource> &>(ClusApi::Facade::NoStorageMoveLogic &,ClusApi::Facade::NoStorageMoveLogic::private_make_shared_tag &&,std::shared_ptr<ClusApi::IResource> &)
0x18008f5e5  nop
0x18008f5e6  mov     [rsp+180h+var_148], rbx
0x18008f5eb  mov     ebx, 39h ; '9'
0x18008f5f0  jmp     short loc_18008F636
0x18008f5f2  mov     ecx, 38h ; '8'; Size
0x18008f5f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008f5fc  mov     rdi, rax
0x18008f5ff  mov     [rsp+180h+var_148], rax
0x18008f604  xorps   xmm0, xmm0
0x18008f607  movups  xmmword ptr [rax], xmm0
0x18008f60a  mov     [rax+8], r13d
0x18008f60e  mov     [rax+0Ch], r13d
0x18008f612  lea     rax, ??_7?$_Ref_count_obj2@VStorageMoveLogic@Facade@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::Facade::StorageMoveLogic>::`vftable'
0x18008f619  mov     [rdi], rax
0x18008f61c  lea     rbx, [rdi+10h]
0x18008f620  mov     r8, r14
0x18008f623  mov     rcx, rbx
0x18008f626  call    ??$_Construct_in_place@VStorageMoveLogic@Facade@ClusApi@@Uprivate_make_shared_tag@123@AEAV?$shared_ptr@UIResource@ClusApi@@@std@@@std@@YAXAEAVStorageMoveLogic@Facade@ClusApi@@$$QEAUprivate_make_shared_tag@123@AEAV?$shared_ptr@UIResource@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::Facade::StorageMoveLogic,ClusApi::Facade::StorageMoveLogic::private_make_shared_tag,std::shared_ptr<ClusApi::IResource> &>(ClusApi::Facade::StorageMoveLogic &,ClusApi::Facade::StorageMoveLogic::private_make_shared_tag &&,std::shared_ptr<ClusApi::IResource> &)
0x18008f62b  nop
0x18008f62c  mov     [rsp+180h+var_148], rbx
0x18008f631  mov     ebx, 1C1h
0x18008f636  mov     [rsp+180h+var_150], ebx
0x18008f63a  mov     [rsp+180h+var_140], rdi
0x18008f63f  lea     rdx, [rsp+180h+var_148]
0x18008f644  lea     rcx, [rsp+180h+var_138]
0x18008f649  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18008f64e  mov     rcx, [rsp+180h+var_140]; this
0x18008f653  test    rcx, rcx
0x18008f656  jz      short loc_18008F65D
0x18008f658  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f65d  mov     rcx, [rsp+180h+var_138]
0x18008f662  mov     rax, [rcx]
0x18008f665  mov     [rsp+180h+lpString2], r12
0x18008f66a  lea     r9, [rsp+180h+var_120]
0x18008f66f  mov     r8, r15
0x18008f672  lea     rdx, [rsp+180h+var_148]
0x18008f677  mov     rax, [rax]
0x18008f67a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f67f  mov     rdx, rax
0x18008f682  mov     rcx, rsi
0x18008f685  call    ??4?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::list<std::shared_ptr<ClusApi::IResource>>::operator=(std::list<std::shared_ptr<ClusApi::IResource>> &&)
0x18008f68a  mov     rdx, [rsp+180h+var_148]
0x18008f68f  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>> &,std::_List_node<std::shared_ptr<ClusApi::IResource>,void *> *)
0x18008f694  mov     edx, 20h ; ' '
0x18008f699  mov     rcx, [rsp+180h+var_148]
0x18008f69e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008f6a3  nop
0x18008f6a4  mov     rcx, [rsp+180h+var_138+8]; this
0x18008f6a9  test    rcx, rcx
0x18008f6ac  jz      short loc_18008F6B4
0x18008f6ae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008f6b3  nop
0x18008f6b4  lea     rcx, [rbp+80h+var_100]
0x18008f6b8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f6bd  nop
0x18008f6be  lea     rcx, [rsp+180h+var_120]
0x18008f6c3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008f6c8  mov     rax, rsi
0x18008f6cb  mov     rcx, [rbp+80h+var_50]
0x18008f6cf  xor     rcx, rsp; StackCookie
0x18008f6d2  call    __security_check_cookie
0x18008f6d7  add     rsp, 148h
0x18008f6de  pop     r15
0x18008f6e0  pop     r14
0x18008f6e2  pop     r13
0x18008f6e4  pop     r12
0x18008f6e6  pop     rdi
0x18008f6e7  pop     rsi
0x18008f6e8  pop     rbx
0x18008f6e9  pop     rbp
0x18008f6ea  retn
```
