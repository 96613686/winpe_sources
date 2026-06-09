# ClusApi::Facade::StorageMoveLogic::PerformOnlineCompleteAction(std::shared_ptr<ClusApi::IGroup> const &,std::shared_ptr<ClusApi::IGroup> const &,ClusApi::Facade::OnlineActionResult::Enum)

- ea: `0x180093bc0`
- end: `0x180093f2e`
- name: `?PerformOnlineCompleteAction@StorageMoveLogic@Facade@ClusApi@@MEAAXAEBV?$shared_ptr@UIGroup@ClusApi@@@std@@0W4Enum@OnlineActionResult@23@@Z`
- size: `878`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000e14c`
- `0x1800737d4`
- `0x180075734`
- `0x180075c60`
- `0x180077928`
- `0x180093bc0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180093d11`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180093e29`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180093d11`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180093e29`

## string_xrefs

- `0x180093eb9`: `Resource->SaveProperties( CommonReadWrite, &pl )`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ClusApi::Facade::StorageMoveLogic::PerformOnlineCompleteAction(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        int a4)
{
  _QWORD *v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  int v11; // ebx
  __int64 v12; // rax
  const WCHAR *v13; // rax
  PCNZWCH lpString2; // rdx
  int v15; // edi
  __int64 v16; // rax
  const WCHAR *v17; // rax
  PCNZWCH v18; // r10
  int v19; // edi
  __int64 v20; // rax
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh]
  int v24; // [rsp+38h] [rbp-C8h] BYREF
  int *v25; // [rsp+40h] [rbp-C0h] BYREF
  int *v26; // [rsp+48h] [rbp-B8h]
  _BYTE v27[16]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v28; // [rsp+60h] [rbp-A0h]
  _BYTE v29[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+E0h] [rbp-20h] BYREF

  std::wstring::wstring(v31);
  std::wstring::wstring(v30);
  cxl::PropertyList::PropertyList((cxl::PropertyList *)v27);
  if ( a4 )
    goto LABEL_16;
  v8 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 8) + 56LL) + 80LL))(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL));
  v9 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v8 + 336LL))(*v8, v31);
  if ( v9 < 0 )
  {
    v10 = std::wstring::wstring(v29, L"Resource->Cluster->GetAvailableStorageId( &availableStorageId )");
    v22 = v9;
    v23 = 2;
    cxl::Exception::Exception(pExceptionObject, &v22, v10);
    throw (cxl::Exception *)pExceptionObject;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a2 + 96LL))(*a2, v30);
  if ( v11 < 0 )
  {
    v12 = std::wstring::wstring(v29, L"ptrOwnerGroup->GetId( &id )");
    v22 = v11;
    v23 = 2;
    cxl::Exception::Exception(pExceptionObject, &v22, v12);
    throw (cxl::Exception *)pExceptionObject;
  }
  std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30);
  if ( CompareStringW(0x400u, 1u, v13, -1, lpString2, -1) == 2 )
  {
    std::wstring::wstring(v29, L"RestartAction");
    v24 = 0;
    v22 = 65538;
    v25 = &v24;
    v26 = &v22;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v27, v29, &v25);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::wstring(v29, L"RestartAction");
    cxl::PropertyList::SetToDefaultValue((cxl::PropertyList *)v27);
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a3 + 96LL))(*a3, v30);
    if ( v15 < 0 )
    {
      v16 = std::wstring::wstring(v29, L"ptrDestGroup->GetId( &id )");
      v22 = v15;
      v23 = 2;
      cxl::Exception::Exception(pExceptionObject, &v22, v16);
      throw (cxl::Exception *)pExceptionObject;
    }
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31);
    v17 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30);
    if ( CompareStringW(0x400u, 1u, v17, -1, v18, -1) != 2 )
      goto LABEL_13;
    std::wstring::wstring(v29, L"RestartAction");
    v22 = 0;
    v24 = 65538;
    v25 = &v22;
    v26 = &v24;
    cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v27, v29, &v25);
  }
  std::wstring::_Tidy_deallocate(v29);
LABEL_13:
  if ( *v28 )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *))(**(_QWORD **)(*(_QWORD *)(a1 + 8) + 56LL) + 16LL))(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL),
            2,
            v27);
    if ( v19 < 0 )
    {
      v20 = std::wstring::wstring(v29, L"Resource->SaveProperties( CommonReadWrite, &pl )");
      v22 = v19;
      v23 = 2;
      cxl::Exception::Exception(pExceptionObject, &v22, v20);
      throw (cxl::Exception *)pExceptionObject;
    }
  }
LABEL_16:
  cxl::PropertyList::~PropertyList((cxl::PropertyList *)v27);
  std::wstring::_Tidy_deallocate(v30);
  return std::wstring::_Tidy_deallocate(v31);
}

```

## disassembly

```asm
0x180093bc0  push    rbp
0x180093bc2  push    rbx
0x180093bc3  push    rsi
0x180093bc4  push    rdi
0x180093bc5  push    r14
0x180093bc7  lea     rbp, [rsp-60h]
0x180093bcc  sub     rsp, 160h
0x180093bd3  mov     rax, cs:__security_cookie
0x180093bda  xor     rax, rsp
0x180093bdd  mov     [rbp+80h+var_30], rax
0x180093be1  mov     ebx, r9d
0x180093be4  mov     r14, r8
0x180093be7  mov     rdi, rdx
0x180093bea  mov     rsi, rcx
0x180093bed  lea     rcx, [rbp+80h+var_C8]
0x180093bf1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180093bf6  nop
0x180093bf7  lea     rcx, [rbp+80h+var_E8]
0x180093bfb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180093c00  nop
0x180093c01  lea     rcx, [rsp+180h+var_130]; this
0x180093c06  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x180093c0b  nop
0x180093c0c  test    ebx, ebx
0x180093c0e  jnz     loc_180093EF5
0x180093c14  mov     rax, [rsi+8]
0x180093c18  mov     rcx, [rax+38h]
0x180093c1c  mov     rax, [rcx]
0x180093c1f  mov     rax, [rax+50h]
0x180093c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c28  mov     rcx, [rax]
0x180093c2b  mov     rax, [rcx]
0x180093c2e  lea     rdx, [rbp+80h+var_C8]
0x180093c32  mov     rax, [rax+150h]
0x180093c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c3e  mov     ebx, eax
0x180093c40  test    eax, eax
0x180093c42  jns     short loc_180093C85
0x180093c44  lea     rdx, aResourceCluste; "Resource->Cluster->GetAvailableStorageI"...
0x180093c4b  lea     rcx, [rsp+180h+var_108]
0x180093c50  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180093c55  nop
0x180093c56  mov     [rsp+180h+var_150], ebx
0x180093c5a  mov     ebx, 2
0x180093c5f  mov     [rsp+180h+var_14C], ebx
0x180093c63  mov     r8, rax
0x180093c66  lea     rdx, [rsp+180h+var_150]
0x180093c6b  lea     rcx, [rbp+80h+pExceptionObject]
0x180093c6f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180093c74  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180093c7b  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180093c7f  call    _CxxThrowException_0
0x180093c85  mov     rcx, [rdi]
0x180093c88  mov     rax, [rcx]
0x180093c8b  lea     rdx, [rbp+80h+var_E8]
0x180093c8f  mov     rax, [rax+60h]
0x180093c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c98  mov     ebx, eax
0x180093c9a  test    eax, eax
0x180093c9c  jns     short loc_180093CDF
0x180093c9e  lea     rdx, aPtrownergroupG; "ptrOwnerGroup->GetId( &id )"
0x180093ca5  lea     rcx, [rsp+180h+var_108]
0x180093caa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180093caf  nop
0x180093cb0  mov     [rsp+180h+var_150], ebx
0x180093cb4  mov     ebx, 2
0x180093cb9  mov     [rsp+180h+var_14C], ebx
0x180093cbd  mov     r8, rax
0x180093cc0  lea     rdx, [rsp+180h+var_150]
0x180093cc5  lea     rcx, [rbp+80h+pExceptionObject]
0x180093cc9  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180093cce  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180093cd5  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180093cd9  call    _CxxThrowException_0
0x180093cdf  lea     rcx, [rbp+80h+var_C8]
0x180093ce3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180093ce8  mov     rdx, rax
0x180093ceb  lea     rcx, [rbp+80h+var_E8]
0x180093cef  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180093cf4  mov     r8, rax; lpString1
0x180093cf7  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x180093cff  mov     [rsp+180h+lpString2], rdx; lpString2
0x180093d04  or      r9d, 0FFFFFFFFh; cchCount1
0x180093d08  lea     edx, [r9+2]; dwCmpFlags
0x180093d0c  mov     ecx, 400h; Locale
0x180093d11  call    cs:__imp_CompareStringW
0x180093d18  nop     dword ptr [rax+rax+00h]
0x180093d1d  mov     ebx, 2
0x180093d22  cmp     eax, ebx
0x180093d24  jnz     short loc_180093DA2
0x180093d26  lea     rdx, aRestartaction; "RestartAction"
0x180093d2d  lea     rcx, [rsp+180h+var_108]
0x180093d32  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180093d37  nop
0x180093d38  mov     [rsp+180h+var_148], 0
0x180093d40  mov     [rsp+180h+var_150], 10002h
0x180093d48  lea     rax, [rsp+180h+var_148]
0x180093d4d  mov     [rsp+180h+var_140], rax
0x180093d52  lea     rax, [rsp+180h+var_150]
0x180093d57  mov     [rsp+180h+var_138], rax
0x180093d5c  lea     r8, [rsp+180h+var_140]
0x180093d61  lea     rdx, [rsp+180h+var_108]
0x180093d66  lea     rcx, [rsp+180h+var_130]
0x180093d6b  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180093d70  nop
0x180093d71  lea     rcx, [rsp+180h+var_108]
0x180093d76  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180093d7b  lea     rdx, aRestartaction; "RestartAction"
0x180093d82  lea     rcx, [rsp+180h+var_108]
0x180093d87  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180093d8c  nop
0x180093d8d  lea     rdx, [rsp+180h+var_108]
0x180093d92  lea     rcx, [rsp+180h+var_130]; this
0x180093d97  call    ?SetToDefaultValue@PropertyList@cxl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::PropertyList::SetToDefaultValue(std::wstring const &)
0x180093d9c  nop
0x180093d9d  jmp     loc_180093E84
0x180093da2  mov     rcx, [r14]
0x180093da5  mov     rax, [rcx]
0x180093da8  lea     rdx, [rbp+80h+var_E8]
0x180093dac  mov     rax, [rax+60h]
0x180093db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093db5  mov     edi, eax
0x180093db7  test    eax, eax
0x180093db9  jns     short loc_180093DF7
0x180093dbb  lea     rdx, aPtrdestgroupGe; "ptrDestGroup->GetId( &id )"
0x180093dc2  lea     rcx, [rsp+180h+var_108]
0x180093dc7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180093dcc  nop
0x180093dcd  mov     [rsp+180h+var_150], edi
0x180093dd1  mov     [rsp+180h+var_14C], ebx
0x180093dd5  mov     r8, rax
0x180093dd8  lea     rdx, [rsp+180h+var_150]
0x180093ddd  lea     rcx, [rbp+80h+pExceptionObject]
0x180093de1  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180093de6  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180093ded  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180093df1  call    _CxxThrowException_0
0x180093df7  lea     rcx, [rbp+80h+var_C8]
0x180093dfb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180093e00  mov     r10, rax
0x180093e03  lea     rcx, [rbp+80h+var_E8]
0x180093e07  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180093e0c  mov     r8, rax; lpString1
0x180093e0f  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x180093e17  mov     [rsp+180h+lpString2], r10; lpString2
0x180093e1c  or      r9d, 0FFFFFFFFh; cchCount1
0x180093e20  lea     edx, [r9+2]; dwCmpFlags
0x180093e24  mov     ecx, 400h; Locale
0x180093e29  call    cs:__imp_CompareStringW
0x180093e30  nop     dword ptr [rax+rax+00h]
0x180093e35  cmp     eax, ebx
0x180093e37  jnz     short loc_180093E8E
0x180093e39  lea     rdx, aRestartaction; "RestartAction"
0x180093e40  lea     rcx, [rsp+180h+var_108]
0x180093e45  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180093e4a  nop
0x180093e4b  mov     [rsp+180h+var_150], 0
0x180093e53  mov     [rsp+180h+var_148], 10002h
0x180093e5b  lea     rax, [rsp+180h+var_150]
0x180093e60  mov     [rsp+180h+var_140], rax
0x180093e65  lea     rax, [rsp+180h+var_148]
0x180093e6a  mov     [rsp+180h+var_138], rax
0x180093e6f  lea     r8, [rsp+180h+var_140]
0x180093e74  lea     rdx, [rsp+180h+var_108]
0x180093e79  lea     rcx, [rsp+180h+var_130]
0x180093e7e  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180093e83  nop
0x180093e84  lea     rcx, [rsp+180h+var_108]
0x180093e89  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180093e8e  mov     rax, [rsp+180h+var_120]
0x180093e93  cmp     dword ptr [rax], 0
0x180093e96  jbe     short loc_180093EF5
0x180093e98  mov     rax, [rsi+8]
0x180093e9c  mov     rcx, [rax+38h]
0x180093ea0  mov     rax, [rcx]
0x180093ea3  lea     r8, [rsp+180h+var_130]
0x180093ea8  mov     edx, ebx
0x180093eaa  mov     rax, [rax+10h]
0x180093eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093eb3  mov     edi, eax
0x180093eb5  test    eax, eax
0x180093eb7  jns     short loc_180093EF5
0x180093eb9  lea     rdx, aResourceSavepr_0; "Resource->SaveProperties( CommonReadWri"...
0x180093ec0  lea     rcx, [rsp+180h+var_108]
0x180093ec5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180093eca  nop
0x180093ecb  mov     [rsp+180h+var_150], edi
0x180093ecf  mov     [rsp+180h+var_14C], ebx
0x180093ed3  mov     r8, rax
0x180093ed6  lea     rdx, [rsp+180h+var_150]
0x180093edb  lea     rcx, [rbp+80h+pExceptionObject]
0x180093edf  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180093ee4  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180093eeb  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180093eef  call    _CxxThrowException_0
0x180093ef5  lea     rcx, [rsp+180h+var_130]; this
0x180093efa  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x180093eff  nop
0x180093f00  lea     rcx, [rbp+80h+var_E8]
0x180093f04  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180093f09  nop
0x180093f0a  lea     rcx, [rbp+80h+var_C8]
0x180093f0e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180093f13  mov     rcx, [rbp+80h+var_30]
0x180093f17  xor     rcx, rsp; StackCookie
0x180093f1a  call    __security_check_cookie
0x180093f1f  add     rsp, 160h
0x180093f26  pop     r14
0x180093f28  pop     rdi
0x180093f29  pop     rsi
0x180093f2a  pop     rbx
0x180093f2b  pop     rbp
0x180093f2c  retn
```
