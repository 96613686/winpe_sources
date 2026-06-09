# ClusApi::Facade::StorageMoveLogic::PerformOnlineCompleteAction(std::shared_ptr<ClusApi::IGroup> const &,std::shared_ptr<ClusApi::IGroup> const &,ClusApi::Facade::OnlineActionResult::Enum)

- ea: `0x180091a70`
- end: `0x180091dd1`
- name: `?PerformOnlineCompleteAction@StorageMoveLogic@Facade@ClusApi@@MEAAXAEBV?$shared_ptr@UIGroup@ClusApi@@@std@@0W4Enum@OnlineActionResult@23@@Z`
- size: `865`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000d298`
- `0x18000d33c`
- `0x18000dd74`
- `0x180071c54`
- `0x180073ba4`
- `0x1800740c4`
- `0x180075cc8`
- `0x180091a70`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091bc1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091cd3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091bc1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091cd3`

## string_xrefs

- `0x180091d5d`: `Resource->SaveProperties( CommonReadWrite, &pl )`

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
0x180091a70  push    rbp
0x180091a72  push    rbx
0x180091a73  push    rsi
0x180091a74  push    rdi
0x180091a75  push    r14
0x180091a77  lea     rbp, [rsp-60h]
0x180091a7c  sub     rsp, 160h
0x180091a83  mov     rax, cs:__security_cookie
0x180091a8a  xor     rax, rsp
0x180091a8d  mov     [rbp+80h+var_30], rax
0x180091a91  mov     ebx, r9d
0x180091a94  mov     r14, r8
0x180091a97  mov     rdi, rdx
0x180091a9a  mov     rsi, rcx
0x180091a9d  lea     rcx, [rbp+80h+var_C8]
0x180091aa1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180091aa6  nop
0x180091aa7  lea     rcx, [rbp+80h+var_E8]
0x180091aab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180091ab0  nop
0x180091ab1  lea     rcx, [rsp+180h+var_130]; this
0x180091ab6  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x180091abb  nop
0x180091abc  test    ebx, ebx
0x180091abe  jnz     loc_180091D99
0x180091ac4  mov     rax, [rsi+8]
0x180091ac8  mov     rcx, [rax+38h]
0x180091acc  mov     rax, [rcx]
0x180091acf  mov     rax, [rax+50h]
0x180091ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091ad8  mov     rcx, [rax]
0x180091adb  mov     rax, [rcx]
0x180091ade  lea     rdx, [rbp+80h+var_C8]
0x180091ae2  mov     rax, [rax+150h]
0x180091ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091aee  mov     ebx, eax
0x180091af0  test    eax, eax
0x180091af2  jns     short loc_180091B35
0x180091af4  lea     rdx, aResourceCluste; "Resource->Cluster->GetAvailableStorageI"...
0x180091afb  lea     rcx, [rsp+180h+var_108]
0x180091b00  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091b05  nop
0x180091b06  mov     [rsp+180h+var_150], ebx
0x180091b0a  mov     ebx, 2
0x180091b0f  mov     [rsp+180h+var_14C], ebx
0x180091b13  mov     r8, rax
0x180091b16  lea     rdx, [rsp+180h+var_150]
0x180091b1b  lea     rcx, [rbp+80h+pExceptionObject]
0x180091b1f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180091b24  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180091b2b  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180091b2f  call    _CxxThrowException_0
0x180091b35  mov     rcx, [rdi]
0x180091b38  mov     rax, [rcx]
0x180091b3b  lea     rdx, [rbp+80h+var_E8]
0x180091b3f  mov     rax, [rax+60h]
0x180091b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091b48  mov     ebx, eax
0x180091b4a  test    eax, eax
0x180091b4c  jns     short loc_180091B8F
0x180091b4e  lea     rdx, aPtrownergroupG; "ptrOwnerGroup->GetId( &id )"
0x180091b55  lea     rcx, [rsp+180h+var_108]
0x180091b5a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091b5f  nop
0x180091b60  mov     [rsp+180h+var_150], ebx
0x180091b64  mov     ebx, 2
0x180091b69  mov     [rsp+180h+var_14C], ebx
0x180091b6d  mov     r8, rax
0x180091b70  lea     rdx, [rsp+180h+var_150]
0x180091b75  lea     rcx, [rbp+80h+pExceptionObject]
0x180091b79  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180091b7e  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180091b85  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180091b89  call    _CxxThrowException_0
0x180091b8f  lea     rcx, [rbp+80h+var_C8]
0x180091b93  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180091b98  mov     rdx, rax
0x180091b9b  lea     rcx, [rbp+80h+var_E8]
0x180091b9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180091ba4  mov     r8, rax; lpString1
0x180091ba7  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x180091baf  mov     [rsp+180h+lpString2], rdx; lpString2
0x180091bb4  or      r9d, 0FFFFFFFFh; cchCount1
0x180091bb8  lea     edx, [r9+2]; dwCmpFlags
0x180091bbc  mov     ecx, 400h; Locale
0x180091bc1  call    cs:__imp_CompareStringW
0x180091bc7  mov     ebx, 2
0x180091bcc  cmp     eax, ebx
0x180091bce  jnz     short loc_180091C4C
0x180091bd0  lea     rdx, aRestartaction; "RestartAction"
0x180091bd7  lea     rcx, [rsp+180h+var_108]
0x180091bdc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091be1  nop
0x180091be2  mov     [rsp+180h+var_148], 0
0x180091bea  mov     [rsp+180h+var_150], 10002h
0x180091bf2  lea     rax, [rsp+180h+var_148]
0x180091bf7  mov     [rsp+180h+var_140], rax
0x180091bfc  lea     rax, [rsp+180h+var_150]
0x180091c01  mov     [rsp+180h+var_138], rax
0x180091c06  lea     r8, [rsp+180h+var_140]
0x180091c0b  lea     rdx, [rsp+180h+var_108]
0x180091c10  lea     rcx, [rsp+180h+var_130]
0x180091c15  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180091c1a  nop
0x180091c1b  lea     rcx, [rsp+180h+var_108]
0x180091c20  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180091c25  lea     rdx, aRestartaction; "RestartAction"
0x180091c2c  lea     rcx, [rsp+180h+var_108]
0x180091c31  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091c36  nop
0x180091c37  lea     rdx, [rsp+180h+var_108]
0x180091c3c  lea     rcx, [rsp+180h+var_130]; this
0x180091c41  call    ?SetToDefaultValue@PropertyList@cxl@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::PropertyList::SetToDefaultValue(std::wstring const &)
0x180091c46  nop
0x180091c47  jmp     loc_180091D28
0x180091c4c  mov     rcx, [r14]
0x180091c4f  mov     rax, [rcx]
0x180091c52  lea     rdx, [rbp+80h+var_E8]
0x180091c56  mov     rax, [rax+60h]
0x180091c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091c5f  mov     edi, eax
0x180091c61  test    eax, eax
0x180091c63  jns     short loc_180091CA1
0x180091c65  lea     rdx, aPtrdestgroupGe; "ptrDestGroup->GetId( &id )"
0x180091c6c  lea     rcx, [rsp+180h+var_108]
0x180091c71  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091c76  nop
0x180091c77  mov     [rsp+180h+var_150], edi
0x180091c7b  mov     [rsp+180h+var_14C], ebx
0x180091c7f  mov     r8, rax
0x180091c82  lea     rdx, [rsp+180h+var_150]
0x180091c87  lea     rcx, [rbp+80h+pExceptionObject]
0x180091c8b  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180091c90  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180091c97  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180091c9b  call    _CxxThrowException_0
0x180091ca1  lea     rcx, [rbp+80h+var_C8]
0x180091ca5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180091caa  mov     r10, rax
0x180091cad  lea     rcx, [rbp+80h+var_E8]
0x180091cb1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180091cb6  mov     r8, rax; lpString1
0x180091cb9  mov     [rsp+180h+cchCount2], 0FFFFFFFFh; cchCount2
0x180091cc1  mov     [rsp+180h+lpString2], r10; lpString2
0x180091cc6  or      r9d, 0FFFFFFFFh; cchCount1
0x180091cca  lea     edx, [r9+2]; dwCmpFlags
0x180091cce  mov     ecx, 400h; Locale
0x180091cd3  call    cs:__imp_CompareStringW
0x180091cd9  cmp     eax, ebx
0x180091cdb  jnz     short loc_180091D32
0x180091cdd  lea     rdx, aRestartaction; "RestartAction"
0x180091ce4  lea     rcx, [rsp+180h+var_108]
0x180091ce9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091cee  nop
0x180091cef  mov     [rsp+180h+var_150], 0
0x180091cf7  mov     [rsp+180h+var_148], 10002h
0x180091cff  lea     rax, [rsp+180h+var_150]
0x180091d04  mov     [rsp+180h+var_140], rax
0x180091d09  lea     rax, [rsp+180h+var_148]
0x180091d0e  mov     [rsp+180h+var_138], rax
0x180091d13  lea     r8, [rsp+180h+var_140]
0x180091d18  lea     rdx, [rsp+180h+var_108]
0x180091d1d  lea     rcx, [rsp+180h+var_130]
0x180091d22  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180091d27  nop
0x180091d28  lea     rcx, [rsp+180h+var_108]
0x180091d2d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180091d32  mov     rax, [rsp+180h+var_120]
0x180091d37  cmp     dword ptr [rax], 0
0x180091d3a  jbe     short loc_180091D99
0x180091d3c  mov     rax, [rsi+8]
0x180091d40  mov     rcx, [rax+38h]
0x180091d44  mov     rax, [rcx]
0x180091d47  lea     r8, [rsp+180h+var_130]
0x180091d4c  mov     edx, ebx
0x180091d4e  mov     rax, [rax+10h]
0x180091d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091d57  mov     edi, eax
0x180091d59  test    eax, eax
0x180091d5b  jns     short loc_180091D99
0x180091d5d  lea     rdx, aResourceSavepr_0; "Resource->SaveProperties( CommonReadWri"...
0x180091d64  lea     rcx, [rsp+180h+var_108]
0x180091d69  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180091d6e  nop
0x180091d6f  mov     [rsp+180h+var_150], edi
0x180091d73  mov     [rsp+180h+var_14C], ebx
0x180091d77  mov     r8, rax
0x180091d7a  lea     rdx, [rsp+180h+var_150]
0x180091d7f  lea     rcx, [rbp+80h+pExceptionObject]
0x180091d83  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180091d88  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180091d8f  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180091d93  call    _CxxThrowException_0
0x180091d99  lea     rcx, [rsp+180h+var_130]; this
0x180091d9e  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x180091da3  nop
0x180091da4  lea     rcx, [rbp+80h+var_E8]
0x180091da8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180091dad  nop
0x180091dae  lea     rcx, [rbp+80h+var_C8]
0x180091db2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180091db7  mov     rcx, [rbp+80h+var_30]
0x180091dbb  xor     rcx, rsp; StackCookie
0x180091dbe  call    __security_check_cookie
0x180091dc3  add     rsp, 160h
0x180091dca  pop     r14
0x180091dcc  pop     rdi
0x180091dcd  pop     rsi
0x180091dce  pop     rbx
0x180091dcf  pop     rbp
0x180091dd0  retn
```
