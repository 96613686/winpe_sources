# CAssocHandler::GetUIName(ushort * *)

- ea: `0x1802bb190`
- end: `0x1802bb34e`
- name: `?GetUIName@CAssocHandler@@UEAAJPEAPEAG@Z`
- size: `446`
- prototype: `int(CAssocHandler *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800432f0`
- `0x1800d13a0`
- `0x1802bb190`
- `0x1803a4cb0`
- `0x1805ded38`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802bb33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802bb33d`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1802bb290`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1802bb290`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802bb26d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802bb26d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1802bb32f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1802bb32f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb2c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb2d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb2e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb2fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb30c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb2c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb2d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb2e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb2fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb30c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802bb320`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1802bb21d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1802bb21d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathRemoveArgsW` at `0x1802bb263`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathRemoveArgsW` at `0x1802bb263`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall CAssocHandler::GetUIName(CAssocHandler *this, unsigned __int16 **a2)
{
  unsigned __int16 **v4; // rsi
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, __int64, _QWORD, __int64); // rbx
  __int64 v8; // rax
  PWSTR *v9; // rax
  HRESULT v10; // eax
  HRESULT v11; // ebx
  unsigned __int16 *v12; // rax
  void *v13; // rcx
  int v14; // [rsp+20h] [rbp-30h]
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR pszPath; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  *a2 = 0;
  v4 = (unsigned __int16 **)((char *)this + 160);
  if ( !*((_QWORD *)this + 20)
    && (*(int (__fastcall **)(_QWORD, __int64, _QWORD, unsigned __int16 **))(**((_QWORD **)this + 8) + 24LL))(
         *((_QWORD *)this + 8),
         35061768,
         0,
         v4) < 0 )
  {
    pszPath = 0;
    v6 = *((_QWORD *)this + 8);
    v7 = *(int (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v6 + 24LL);
    v8 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszPath);
    if ( v7(v6, 34013184, 0, v8) >= 0 )
    {
      PathRemoveArgsW(pszPath);
      PathUnquoteSpacesW(pszPath);
      pv = 0;
      v9 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
      v10 = PathAllocCanonicalize(pszPath, 0x40u, v9);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6D1,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\cassochandler.cpp",
          (const char *)(unsigned int)v10,
          v14);
        if ( pv )
          CoTaskMemFree(pv);
        if ( pszPath )
          CoTaskMemFree(pszPath);
        return v11;
      }
      if ( !PathFileExistsW((LPCWSTR)pv) && GetLastError() == 2 )
      {
        if ( pv )
          CoTaskMemFree(pv);
        if ( pszPath )
          CoTaskMemFree(pszPath);
        return -2147467259;
      }
      GetAppNameFromAppAssociationElement((const unsigned __int16 *)pv, v4);
      if ( *v4 )
      {
        v13 = pv;
      }
      else
      {
        v12 = (unsigned __int16 *)pv;
        v13 = 0;
        pv = 0;
        *v4 = v12;
      }
      if ( v13 )
        CoTaskMemFree(v13);
    }
    if ( pszPath )
      CoTaskMemFree(pszPath);
  }
  if ( !*v4 )
    return -2147467259;
  return SHStrDupW(*v4, a2);
}

```

## disassembly

```asm
0x1802bb190  mov     [rsp-18h+arg_10], rbx
0x1802bb195  mov     [rsp-18h+arg_18], rsi
0x1802bb19a  push    rbp
0x1802bb19b  push    rdi
0x1802bb19c  push    r14
0x1802bb19e  mov     rbp, rsp
0x1802bb1a1  sub     rsp, 50h
0x1802bb1a5  mov     rax, cs:__security_cookie
0x1802bb1ac  xor     rax, rsp
0x1802bb1af  mov     [rbp+var_10], rax
0x1802bb1b3  mov     r14, rdx
0x1802bb1b6  mov     rdi, rcx
0x1802bb1b9  mov     qword ptr [rdx], 0
0x1802bb1c0  lea     rsi, [rcx+0A0h]
0x1802bb1c7  cmp     qword ptr [rsi], 0
0x1802bb1cb  jnz     short loc_1802BB1EC
0x1802bb1cd  mov     rcx, [rcx+40h]
0x1802bb1d1  mov     rax, [rcx]
0x1802bb1d4  mov     r9, rsi
0x1802bb1d7  xor     r8d, r8d
0x1802bb1da  mov     edx, 2170008h
0x1802bb1df  mov     rax, [rax+18h]
0x1802bb1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bb1e8  test    eax, eax
0x1802bb1ea  js      short loc_1802BB225
0x1802bb1ec  mov     rcx, [rsi]; psz
0x1802bb1ef  test    rcx, rcx
0x1802bb1f2  jnz     short loc_1802BB21A
0x1802bb1f4  mov     eax, 80004005h
0x1802bb1f9  mov     rcx, [rbp+var_10]
0x1802bb1fd  xor     rcx, rsp; StackCookie
0x1802bb200  call    __security_check_cookie
0x1802bb205  lea     r11, [rsp+50h+var_s0]
0x1802bb20a  mov     rbx, [r11+30h]
0x1802bb20e  mov     rsi, [r11+38h]
0x1802bb212  mov     rsp, r11
0x1802bb215  pop     r14
0x1802bb217  pop     rdi
0x1802bb218  pop     rbp
0x1802bb219  retn
0x1802bb21a  mov     rdx, r14; ppwsz
0x1802bb21d  call    cs:__imp_SHStrDupW
0x1802bb223  jmp     short loc_1802BB1F9
0x1802bb225  mov     [rbp+pszPath], 0
0x1802bb22d  mov     rdi, [rdi+40h]
0x1802bb231  mov     rax, [rdi]
0x1802bb234  mov     rbx, [rax+18h]
0x1802bb238  lea     rcx, [rbp+pszPath]
0x1802bb23c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1802bb241  mov     r9, rax
0x1802bb244  xor     r8d, r8d
0x1802bb247  mov     edx, 2070000h
0x1802bb24c  mov     rcx, rdi
0x1802bb24f  mov     rax, rbx
0x1802bb252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bb257  test    eax, eax
0x1802bb259  js      loc_1802BB313
0x1802bb25f  mov     rcx, [rbp+pszPath]; pszPath
0x1802bb263  call    cs:__imp_PathRemoveArgsW
0x1802bb269  mov     rcx, [rbp+pszPath]; lpsz
0x1802bb26d  call    cs:__imp_PathUnquoteSpacesW
0x1802bb273  mov     [rbp+pv], 0
0x1802bb27b  lea     rcx, [rbp+pv]
0x1802bb27f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1802bb284  mov     r8, rax; ppszPathOut
0x1802bb287  mov     edx, 40h ; '@'; dwFlags
0x1802bb28c  mov     rcx, [rbp+pszPath]; pszPathIn
0x1802bb290  call    cs:__imp_PathAllocCanonicalize
0x1802bb296  mov     ebx, eax
0x1802bb298  test    eax, eax
0x1802bb29a  jns     loc_1802BB32B
0x1802bb2a0  mov     rcx, [rbp+18h]; this
0x1802bb2a4  mov     r9d, eax; char *
0x1802bb2a7  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\windows.storage\\sha"...
0x1802bb2ae  mov     edx, 6D1h; void *
0x1802bb2b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802bb2b8  nop
0x1802bb2b9  mov     rcx, [rbp+pv]; pv
0x1802bb2bd  test    rcx, rcx
0x1802bb2c0  jz      short loc_1802BB2C9
0x1802bb2c2  call    cs:__imp_CoTaskMemFree
0x1802bb2c8  nop
0x1802bb2c9  mov     rcx, [rbp+pszPath]; pv
0x1802bb2cd  test    rcx, rcx
0x1802bb2d0  jz      short loc_1802BB2D8
0x1802bb2d2  call    cs:__imp_CoTaskMemFree
0x1802bb2d8  mov     eax, ebx
0x1802bb2da  jmp     loc_1802BB1F9
0x1802bb2df  mov     rcx, [rbp+pv]; pv
0x1802bb2e3  test    rcx, rcx
0x1802bb2e6  jz      short loc_1802BB2EF
0x1802bb2e8  call    cs:__imp_CoTaskMemFree
0x1802bb2ee  nop
0x1802bb2ef  mov     rcx, [rbp+pszPath]; pv
0x1802bb2f3  test    rcx, rcx
0x1802bb2f6  jz      loc_1802BB1F4
0x1802bb2fc  call    cs:__imp_CoTaskMemFree
0x1802bb302  jmp     loc_1802BB1F4
0x1802bb307  test    rcx, rcx
0x1802bb30a  jz      short loc_1802BB313
0x1802bb30c  call    cs:__imp_CoTaskMemFree
0x1802bb312  nop
0x1802bb313  mov     rcx, [rbp+pszPath]; pv
0x1802bb317  test    rcx, rcx
0x1802bb31a  jz      loc_1802BB1EC
0x1802bb320  call    cs:__imp_CoTaskMemFree
0x1802bb326  jmp     loc_1802BB1EC
0x1802bb32b  mov     rcx, [rbp+pv]; pszPath
0x1802bb32f  call    cs:__imp_PathFileExistsW
0x1802bb335  test    eax, eax
0x1802bb337  jnz     loc_180658248
0x1802bb33d  call    cs:__imp_GetLastError
0x1802bb343  cmp     eax, 2
0x1802bb346  jnz     loc_180658248
0x1802bb34c  jmp     short loc_1802BB2DF
0x180658248  mov     rdx, rsi; unsigned __int16 **
0x18065824b  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18065824f  call    ?GetAppNameFromAppAssociationElement@@YAJPEBGPEAPEAG@Z; GetAppNameFromAppAssociationElement(ushort const *,ushort * *)
0x180658254  cmp     qword ptr [rsi], 0
0x180658258  jnz     short loc_18065826C
0x18065825a  mov     rax, [rbp+pv]
0x18065825e  xor     ecx, ecx; pv
0x180658260  mov     [rbp+pv], rcx
0x180658264  mov     [rsi], rax
0x180658267  jmp     loc_1802BB307
0x18065826c  mov     rcx, [rbp+pv]
0x180658270  jmp     loc_1802BB307
```
