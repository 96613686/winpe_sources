# ClusApi::Facade::NonShadowCopyTaskNonStorageResourceFilter::Filter(std::shared_ptr<ClusApi::IResource> const &)

- ea: `0x180093b40`
- end: `0x180093c02`
- name: `?Filter@NonShadowCopyTaskNonStorageResourceFilter@Facade@ClusApi@@UEAA_NAEBV?$shared_ptr@UIResource@ClusApi@@@std@@@Z`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000c284`
- `0x18000dd74`
- `0x18008d4a8`
- `0x180092b10`
- `0x180092c6c`
- `0x180093b40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180093bb3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180093bb3`

## string_xrefs

- `0x180093b9d`: `Volume Shadow Copy Service Task`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall ClusApi::Facade::NonShadowCopyTaskNonStorageResourceFilter::Filter(__int64 a1, __int64 a2)
{
  char v2; // di
  __int64 type; // rax
  const WCHAR *v4; // rax
  bool v5; // bl
  ClusApi::Facade::ResourceFacade *v7; // [rsp+38h] [rbp-40h] BYREF
  std::_Ref_count_base *v8; // [rsp+40h] [rbp-38h]
  _BYTE v9[32]; // [rsp+48h] [rbp-30h] BYREF

  v2 = 0;
  ClusApi::Facade::FacadeFactory::CreateResourceFacade(&v7, a2);
  v5 = 0;
  if ( !ClusApi::Facade::ResourceFacade::get_storage(v7) )
  {
    type = ClusApi::Facade::ResourceFacade::get_type(v7, v9);
    v2 = 1;
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(type);
    if ( CompareStringW(0x400u, 1u, v4, -1, L"Volume Shadow Copy Service Task", -1) != 2 )
      v5 = 1;
  }
  if ( (v2 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v9);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  return v5;
}

```

## disassembly

```asm
0x180093b40  mov     [rsp+arg_0], rbx
0x180093b45  push    rdi
0x180093b46  sub     rsp, 70h
0x180093b4a  mov     rax, cs:__security_cookie
0x180093b51  xor     rax, rsp
0x180093b54  mov     [rsp+78h+var_10], rax
0x180093b59  xor     edi, edi
0x180093b5b  mov     [rsp+78h+var_48], edi
0x180093b5f  lea     rcx, [rsp+78h+var_40]
0x180093b64  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x180093b69  nop
0x180093b6a  mov     rcx, [rsp+78h+var_40]; this
0x180093b6f  call    ?get_storage@ResourceFacade@Facade@ClusApi@@QEBA_NXZ; ClusApi::Facade::ResourceFacade::get_storage(void)
0x180093b74  test    al, al
0x180093b76  jnz     short loc_180093BC3
0x180093b78  lea     rdx, [rsp+78h+var_30]
0x180093b7d  mov     rcx, [rsp+78h+var_40]
0x180093b82  call    ?get_type@ResourceFacade@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::ResourceFacade::get_type(void)
0x180093b87  mov     edi, 1
0x180093b8c  mov     rcx, rax
0x180093b8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180093b94  or      r9d, 0FFFFFFFFh; cchCount1
0x180093b98  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180093b9d  lea     rcx, aVolumeShadowCo; "Volume Shadow Copy Service Task"
0x180093ba4  mov     [rsp+78h+lpString2], rcx; lpString2
0x180093ba9  mov     r8, rax; lpString1
0x180093bac  mov     edx, edi; dwCmpFlags
0x180093bae  mov     ecx, 400h; Locale
0x180093bb3  call    cs:__imp_CompareStringW
0x180093bb9  cmp     eax, 2
0x180093bbc  jz      short loc_180093BC3
0x180093bbe  mov     bl, dil
0x180093bc1  jmp     short loc_180093BC5
0x180093bc3  xor     bl, bl
0x180093bc5  test    dil, 1
0x180093bc9  jz      short loc_180093BD6
0x180093bcb  lea     rcx, [rsp+78h+var_30]
0x180093bd0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180093bd5  nop
0x180093bd6  mov     rcx, [rsp+78h+var_38]; this
0x180093bdb  test    rcx, rcx
0x180093bde  jz      short loc_180093BE5
0x180093be0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180093be5  mov     al, bl
0x180093be7  mov     rcx, [rsp+78h+var_10]
0x180093bec  xor     rcx, rsp; StackCookie
0x180093bef  call    __security_check_cookie
0x180093bf4  mov     rbx, [rsp+78h+arg_0]
0x180093bfc  add     rsp, 70h
0x180093c00  pop     rdi
0x180093c01  retn
```
