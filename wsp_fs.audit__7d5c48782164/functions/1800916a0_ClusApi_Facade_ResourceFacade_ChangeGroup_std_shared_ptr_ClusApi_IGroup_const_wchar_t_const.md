# ClusApi::Facade::ResourceFacade::ChangeGroup(std::shared_ptr<ClusApi::IGroup> const &,wchar_t const *)

- ea: `0x1800916a0`
- end: `0x18009196a`
- name: `?ChangeGroup@ResourceFacade@Facade@ClusApi@@QEAA?AV?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@AEBV?$shared_ptr@UIGroup@ClusApi@@@5@PEB_W@Z`
- size: `714`
- prototype: `__int64 __fastcall(ClusApi::Facade::ResourceFacade *this)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180095a40`

## callees

- `0x180002ad0`
- `0x180002af4`
- `0x180003534`
- `0x180005e64`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000c4ac`
- `0x18000c5c4`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000e14c`
- `0x180057488`
- `0x180085620`
- `0x18009019c`
- `0x1800901e0`
- `0x180090f30`
- `0x1800916a0`
- `0x180094c80`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091808`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091808`

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
  std::_Ref_count_base *v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
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
    v22 = (unsigned int)v10 | 0x200000000LL;
    cxl::Exception::Exception(pExceptionObject, &v22, v11);
    throw (cxl::Exception *)pExceptionObject;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a3 + 88LL))(*a3, v27);
  if ( v12 < 0 )
  {
    v13 = std::wstring::wstring(v28, L"ptrGroup->GetName( &groupName )");
    v22 = (unsigned int)v12 | 0x200000000LL;
    cxl::Exception::Exception(pExceptionObject, &v22, v13);
    throw (cxl::Exception *)pExceptionObject;
  }
  std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27);
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26);
  if ( CompareStringW(0x400u, 1u, v14, -1, lpString2, -1) != 2 )
  {
    if ( ClusApi::Facade::ResourceFacade::get_storage(this) )
    {
      v16 = (std::_Ref_count_base *)operator new(0x38u);
      *(_OWORD *)v16 = 0;
      *((_DWORD *)v16 + 2) = 1;
      *((_DWORD *)v16 + 3) = 1;
      *(_QWORD *)v16 = &std::_Ref_count_obj2<ClusApi::Facade::StorageMoveLogic>::`vftable';
      std::_Construct_in_place<ClusApi::Facade::StorageMoveLogic,ClusApi::Facade::StorageMoveLogic::private_make_shared_tag,std::shared_ptr<ClusApi::IResource> &>(
        (char *)v16 + 16,
        v18,
        v9);
    }
    else
    {
      v16 = (std::_Ref_count_base *)operator new(0x40u);
      *(_OWORD *)v16 = 0;
      *((_DWORD *)v16 + 2) = 1;
      *((_DWORD *)v16 + 3) = 1;
      *(_QWORD *)v16 = &std::_Ref_count_obj2<ClusApi::Facade::NoStorageMoveLogic>::`vftable';
      std::_Construct_in_place<ClusApi::Facade::NoStorageMoveLogic,ClusApi::Facade::NoStorageMoveLogic::private_make_shared_tag,std::shared_ptr<ClusApi::IResource> &>(
        (char *)v16 + 16,
        v17,
        v9);
    }
    v22 = (__int64)v16 + 16;
    v23 = v16;
    std::shared_ptr<ClusWmi::DataStore>::operator=(v24, &v22);
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    v19 = (**(__int64 (__fastcall ***)(std::_Ref_count_base *, __int64 *, _QWORD *, _BYTE *, __int64))v24[0])(
            v24[0],
            &v22,
            a3,
            v26,
            a4);
    std::list<std::shared_ptr<ClusApi::IResource>>::operator=(a2, v19);
    std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(
      v20,
      v22);
    std::_Deallocate<16>(v22, 32);
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
0x1800916a0  push    rbp
0x1800916a2  push    rbx
0x1800916a3  push    rsi
0x1800916a4  push    rdi
0x1800916a5  push    r12
0x1800916a7  push    r13
0x1800916a9  push    r14
0x1800916ab  push    r15
0x1800916ad  lea     rbp, [rsp-48h]
0x1800916b2  sub     rsp, 148h
0x1800916b9  mov     rax, cs:__security_cookie
0x1800916c0  xor     rax, rsp
0x1800916c3  mov     [rbp+80h+var_50], rax
0x1800916c7  mov     r12, r9
0x1800916ca  mov     r15, r8
0x1800916cd  mov     rsi, rdx
0x1800916d0  mov     rdi, rcx
0x1800916d3  mov     [rsp+180h+var_128], rdx
0x1800916d8  mov     r13d, 1
0x1800916de  mov     [rsp+180h+var_150], r13d
0x1800916e3  lea     rcx, [rsp+180h+var_120]
0x1800916e8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800916ed  nop
0x1800916ee  lea     rcx, [rbp+80h+var_100]
0x1800916f2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800916f7  nop
0x1800916f8  xorps   xmm1, xmm1
0x1800916fb  movdqu  xmmword ptr [rsp+180h+var_138], xmm1
0x180091701  mov     rcx, rdx
0x180091704  call    ??0?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<ClusApi::IResource>>::list<std::shared_ptr<ClusApi::IResource>>(void)
0x180091709  nop
0x18009170a  mov     [rsp+180h+var_150], r13d
0x18009170f  lea     r14, [rdi+38h]
0x180091713  mov     rcx, [r14]
0x180091716  mov     rax, [rcx]
0x180091719  lea     r9, [rsp+180h+var_120]
0x18009171e  xor     r8d, r8d
0x180091721  xor     edx, edx
0x180091723  mov     rax, [rax+78h]
0x180091727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009172c  mov     ebx, eax
0x18009172e  test    eax, eax
0x180091730  jns     short loc_180091779
0x180091732  lea     rdx, aPtrresourceGet_3; "_ptrResource->GetState( nullptr, nullpt"...
0x180091739  lea     rcx, [rbp+80h+var_E0]
0x18009173d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091742  nop
0x180091743  mov     dword ptr [rsp+180h+var_148], ebx
0x180091747  mov     dword ptr [rsp+180h+var_148+4], 2
0x18009174f  mov     r8, rax
0x180091752  lea     rdx, [rsp+180h+var_148]
0x180091757  lea     rcx, [rbp+80h+pExceptionObject]
0x18009175b  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180091760  mov     [rsp+180h+var_150], 3
0x180091768  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009176f  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180091773  call    _CxxThrowException_0
0x180091779  mov     rcx, [r15]
0x18009177c  mov     rax, [rcx]
0x18009177f  lea     rdx, [rbp+80h+var_100]
0x180091783  mov     rax, [rax+58h]
0x180091787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009178c  mov     ebx, eax
0x18009178e  test    eax, eax
0x180091790  jns     short loc_1800917D9
0x180091792  lea     rdx, aPtrgroupGetnam; "ptrGroup->GetName( &groupName )"
0x180091799  lea     rcx, [rbp+80h+var_E0]
0x18009179d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800917a2  nop
0x1800917a3  mov     dword ptr [rsp+180h+var_148], ebx
0x1800917a7  mov     dword ptr [rsp+180h+var_148+4], 2
0x1800917af  mov     r8, rax
0x1800917b2  lea     rdx, [rsp+180h+var_148]
0x1800917b7  lea     rcx, [rbp+80h+pExceptionObject]
0x1800917bb  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800917c0  mov     [rsp+180h+var_150], 5
0x1800917c8  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800917cf  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x1800917d3  call    _CxxThrowException_0
0x1800917d9  lea     rcx, [rbp+80h+var_100]
0x1800917dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800917e2  mov     rdx, rax
0x1800917e5  lea     rcx, [rsp+180h+var_120]
0x1800917ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800917ef  mov     r8, rax; lpString1
0x1800917f2  or      r9d, 0FFFFFFFFh; cchCount1
0x1800917f6  mov     [rsp+180h+cchCount2], r9d; cchCount2
0x1800917fb  mov     [rsp+180h+lpString2], rdx; lpString2
0x180091800  mov     edx, r13d; dwCmpFlags
0x180091803  mov     ecx, 400h; Locale
0x180091808  call    cs:__imp_CompareStringW
0x18009180f  nop     dword ptr [rax+rax+00h]
0x180091814  cmp     eax, 2
0x180091817  jnz     short loc_18009181E
0x180091819  jmp     loc_180091932
0x18009181e  mov     rcx, rdi; this
0x180091821  call    ?get_storage@ResourceFacade@Facade@ClusApi@@QEBA_NXZ; ClusApi::Facade::ResourceFacade::get_storage(void)
0x180091826  test    al, al
0x180091828  jnz     short loc_180091870
0x18009182a  mov     ecx, 40h ; '@'; Size
0x18009182f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180091834  mov     rdi, rax
0x180091837  mov     [rsp+180h+var_148], rax
0x18009183c  xorps   xmm0, xmm0
0x18009183f  movups  xmmword ptr [rax], xmm0
0x180091842  mov     [rax+8], r13d
0x180091846  mov     [rax+0Ch], r13d
0x18009184a  lea     rax, ??_7?$_Ref_count_obj2@VNoStorageMoveLogic@Facade@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::Facade::NoStorageMoveLogic>::`vftable'
0x180091851  mov     [rdi], rax
0x180091854  lea     rbx, [rdi+10h]
0x180091858  mov     r8, r14
0x18009185b  mov     rcx, rbx
0x18009185e  call    ??$_Construct_in_place@VNoStorageMoveLogic@Facade@ClusApi@@Uprivate_make_shared_tag@123@AEAV?$shared_ptr@UIResource@ClusApi@@@std@@@std@@YAXAEAVNoStorageMoveLogic@Facade@ClusApi@@$$QEAUprivate_make_shared_tag@123@AEAV?$shared_ptr@UIResource@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::Facade::NoStorageMoveLogic,ClusApi::Facade::NoStorageMoveLogic::private_make_shared_tag,std::shared_ptr<ClusApi::IResource> &>(ClusApi::Facade::NoStorageMoveLogic &,ClusApi::Facade::NoStorageMoveLogic::private_make_shared_tag &&,std::shared_ptr<ClusApi::IResource> &)
0x180091863  nop
0x180091864  mov     [rsp+180h+var_148], rbx
0x180091869  mov     ebx, 39h ; '9'
0x18009186e  jmp     short loc_1800918B4
0x180091870  mov     ecx, 38h ; '8'; Size
0x180091875  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009187a  mov     rdi, rax
0x18009187d  mov     [rsp+180h+var_148], rax
0x180091882  xorps   xmm0, xmm0
0x180091885  movups  xmmword ptr [rax], xmm0
0x180091888  mov     [rax+8], r13d
0x18009188c  mov     [rax+0Ch], r13d
0x180091890  lea     rax, ??_7?$_Ref_count_obj2@VStorageMoveLogic@Facade@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::Facade::StorageMoveLogic>::`vftable'
0x180091897  mov     [rdi], rax
0x18009189a  lea     rbx, [rdi+10h]
0x18009189e  mov     r8, r14
0x1800918a1  mov     rcx, rbx
0x1800918a4  call    ??$_Construct_in_place@VStorageMoveLogic@Facade@ClusApi@@Uprivate_make_shared_tag@123@AEAV?$shared_ptr@UIResource@ClusApi@@@std@@@std@@YAXAEAVStorageMoveLogic@Facade@ClusApi@@$$QEAUprivate_make_shared_tag@123@AEAV?$shared_ptr@UIResource@ClusApi@@@0@@Z; std::_Construct_in_place<ClusApi::Facade::StorageMoveLogic,ClusApi::Facade::StorageMoveLogic::private_make_shared_tag,std::shared_ptr<ClusApi::IResource> &>(ClusApi::Facade::StorageMoveLogic &,ClusApi::Facade::StorageMoveLogic::private_make_shared_tag &&,std::shared_ptr<ClusApi::IResource> &)
0x1800918a9  nop
0x1800918aa  mov     [rsp+180h+var_148], rbx
0x1800918af  mov     ebx, 1C1h
0x1800918b4  mov     [rsp+180h+var_150], ebx
0x1800918b8  mov     [rsp+180h+var_140], rdi
0x1800918bd  lea     rdx, [rsp+180h+var_148]
0x1800918c2  lea     rcx, [rsp+180h+var_138]
0x1800918c7  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x1800918cc  mov     rcx, [rsp+180h+var_140]; this
0x1800918d1  test    rcx, rcx
0x1800918d4  jz      short loc_1800918DB
0x1800918d6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800918db  mov     rcx, [rsp+180h+var_138]
0x1800918e0  mov     rax, [rcx]
0x1800918e3  mov     [rsp+180h+lpString2], r12
0x1800918e8  lea     r9, [rsp+180h+var_120]
0x1800918ed  mov     r8, r15
0x1800918f0  lea     rdx, [rsp+180h+var_148]
0x1800918f5  mov     rax, [rax]
0x1800918f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800918fd  mov     rdx, rax
0x180091900  mov     rcx, rsi
0x180091903  call    ??4?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::list<std::shared_ptr<ClusApi::IResource>>::operator=(std::list<std::shared_ptr<ClusApi::IResource>> &&)
0x180091908  mov     rdx, [rsp+180h+var_148]
0x18009190d  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>> &,std::_List_node<std::shared_ptr<ClusApi::IResource>,void *> *)
0x180091912  mov     edx, 20h ; ' '
0x180091917  mov     rcx, [rsp+180h+var_148]
0x18009191c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180091921  nop
0x180091922  mov     rcx, [rsp+180h+var_138+8]; this
0x180091927  test    rcx, rcx
0x18009192a  jz      short loc_180091932
0x18009192c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180091931  nop
0x180091932  lea     rcx, [rbp+80h+var_100]
0x180091936  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009193b  nop
0x18009193c  lea     rcx, [rsp+180h+var_120]
0x180091941  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180091946  mov     rax, rsi
0x180091949  mov     rcx, [rbp+80h+var_50]
0x18009194d  xor     rcx, rsp; StackCookie
0x180091950  call    __security_check_cookie
0x180091955  add     rsp, 148h
0x18009195c  pop     r15
0x18009195e  pop     r14
0x180091960  pop     r13
0x180091962  pop     r12
0x180091964  pop     rdi
0x180091965  pop     rsi
0x180091966  pop     rbx
0x180091967  pop     rbp
0x180091968  retn
```
