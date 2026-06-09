# CThumbnailCache::TryGetFileExtension(IShellItem *)

- ea: `0x18000333c`
- end: `0x18000348c`
- name: `?TryGetFileExtension@CThumbnailCache@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011c10`

## callees

- `0x180002c84`
- `0x1800031bc`
- `0x18000333c`
- `0x1800034f8`
- `0x180003510`
- `0x180004464`
- `0x18001d264`
- `0x18001f73c`
- `0x18002d4f8`
- `0x1800345b4`
- `0x180035830`
- `0x18004097c`
- `0x180043558`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000338c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000338c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
_QWORD *__fastcall CThumbnailCache::TryGetFileExtension(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 (__fastcall *v6)(__int64, __int64, LPVOID *); // r14
  void *v7; // rdi
  int v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  const unsigned __int16 *FileExtensionNoPeriod; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 v14; // rax
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-68h]
  _BYTE v18[8]; // [rsp+28h] [rbp-60h] BYREF
  _QWORD *v19; // [rsp+30h] [rbp-58h]
  LPVOID pv; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v21[16]; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int64 v22; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v19 = a1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
    &pv,
    a2,
    a3);
  v6 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v5 + 40LL);
  v7 = pv;
  if ( pv )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v18);
    CoTaskMemFree(v7);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
  }
  pv = 0;
  v8 = v6(a2, 2147647488LL, &pv);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v9, v10, (const char *)(unsigned int)v8, v17);
  FileExtensionNoPeriod = GetFileExtensionNoPeriod((const unsigned __int16 *)pv);
  std::wstring::wstring(v21, FileExtensionNoPeriod);
  v14 = v22;
  if ( v22 > 0x40 )
  {
    std::wstring::resize(v21);
    v14 = v22;
  }
  if ( v14 )
  {
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      a1,
      v16);
  }
  else
  {
    *a1 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
      a1,
      v12,
      v13);
  }
  std::wstring::~wstring(v21);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
  return a1;
}

```

## disassembly

```asm
0x18000333c  mov     [rsp+arg_10], rbx
0x180003341  push    rsi
0x180003342  push    rdi
0x180003343  push    r14
0x180003345  sub     rsp, 70h
0x180003349  mov     rax, cs:__security_cookie
0x180003350  xor     rax, rsp
0x180003353  mov     [rsp+88h+var_28], rax
0x180003358  mov     rsi, rdx
0x18000335b  mov     rbx, rcx
0x18000335e  mov     [rsp+88h+var_58], rcx
0x180003363  lea     rcx, [rsp+88h+pv]
0x180003368  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000336d  nop
0x18000336e  mov     rax, [rdx]
0x180003371  mov     r14, [rax+28h]
0x180003375  mov     rdi, [rsp+88h+pv]
0x18000337a  test    rdi, rdi
0x18000337d  jz      short loc_18000339C
0x18000337f  lea     rcx, [rsp+88h+var_60]; this
0x180003384  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180003389  mov     rcx, rdi; pv
0x18000338c  call    cs:__imp_CoTaskMemFree
0x180003392  lea     rcx, [rsp+88h+var_60]; this
0x180003397  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000339c  mov     [rsp+88h+pv], 0
0x1800033a5  lea     r8, [rsp+88h+pv]
0x1800033aa  mov     edx, 80028000h
0x1800033af  mov     rcx, rsi
0x1800033b2  mov     rax, r14
0x1800033b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ba  mov     rcx, [rsp+88h]; this
0x1800033c2  test    eax, eax
0x1800033c4  jns     short loc_1800033CE
0x1800033c6  mov     r9d, eax; char *
0x1800033c9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800033ce  mov     rcx, [rsp+88h+pv]; unsigned __int16 *
0x1800033d3  call    ?GetFileExtensionNoPeriod@@YAPEBGPEBG@Z; GetFileExtensionNoPeriod(ushort const *)
0x1800033d8  mov     rdx, rax
0x1800033db  lea     rcx, [rsp+88h+var_48]
0x1800033e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800033e5  nop
0x1800033e6  mov     rax, [rsp+88h+var_38]
0x1800033eb  cmp     rax, 40h ; '@'
0x1800033ef  jbe     short loc_180003400
0x1800033f1  lea     rcx, [rsp+88h+var_48]
0x1800033f6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800033fb  mov     rax, [rsp+88h+var_38]
0x180003400  test    rax, rax
0x180003403  jnz     short loc_18000342B
0x180003405  mov     [rbx], rax
0x180003408  mov     rcx, rbx
0x18000340b  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180003410  nop
0x180003411  lea     rcx, [rsp+88h+var_48]
0x180003416  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000341b  nop
0x18000341c  lea     rcx, [rsp+88h+pv]
0x180003421  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180003426  mov     rax, rbx
0x180003429  jmp     short loc_18000346D
0x18000342b  lea     rcx, [rsp+88h+var_48]
0x180003430  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180003435  mov     rdx, rax
0x180003438  mov     rcx, rbx
0x18000343b  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180003440  nop
0x180003441  lea     rcx, [rsp+88h+var_48]
0x180003446  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000344b  nop
0x18000344c  lea     rcx, [rsp+88h+pv]
0x180003451  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180003456  mov     rax, rbx
0x180003459  jmp     short loc_18000346D
0x18000345b  xor     eax, eax
0x18000345d  mov     rcx, [rsp+88h+var_58]
0x180003462  mov     [rcx], rax
0x180003465  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000346a  mov     rax, rcx
0x18000346d  mov     rcx, [rsp+88h+var_28]
0x180003472  xor     rcx, rsp; StackCookie
0x180003475  call    __security_check_cookie
0x18000347a  mov     rbx, [rsp+88h+arg_10]
0x180003482  add     rsp, 70h
0x180003486  pop     r14
0x180003488  pop     rdi
0x180003489  pop     rsi
0x18000348a  retn
```
