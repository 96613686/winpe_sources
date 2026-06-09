# ClusApi::Facade::NonShadowCopyTaskNonStorageResourceFilter::Filter(std::shared_ptr<ClusApi::IResource> const &)

- ea: `0x180095c50`
- end: `0x180095d19`
- name: `?Filter@NonShadowCopyTaskNonStorageResourceFilter@Facade@ClusApi@@UEAA_NAEBV?$shared_ptr@UIResource@ClusApi@@@std@@@Z`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000e14c`
- `0x18008f75c`
- `0x180094c80`
- `0x180094de0`
- `0x180095c50`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180095cc3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180095cc3`

## string_xrefs

- `0x180095cad`: `Volume Shadow Copy Service Task`

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
0x180095c50  mov     [rsp+arg_0], rbx
0x180095c55  push    rdi
0x180095c56  sub     rsp, 70h
0x180095c5a  mov     rax, cs:__security_cookie
0x180095c61  xor     rax, rsp
0x180095c64  mov     [rsp+78h+var_10], rax
0x180095c69  xor     edi, edi
0x180095c6b  mov     [rsp+78h+var_48], edi
0x180095c6f  lea     rcx, [rsp+78h+var_40]
0x180095c74  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x180095c79  nop
0x180095c7a  mov     rcx, [rsp+78h+var_40]; this
0x180095c7f  call    ?get_storage@ResourceFacade@Facade@ClusApi@@QEBA_NXZ; ClusApi::Facade::ResourceFacade::get_storage(void)
0x180095c84  test    al, al
0x180095c86  jnz     short loc_180095CD9
0x180095c88  lea     rdx, [rsp+78h+var_30]
0x180095c8d  mov     rcx, [rsp+78h+var_40]
0x180095c92  call    ?get_type@ResourceFacade@Facade@ClusApi@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusApi::Facade::ResourceFacade::get_type(void)
0x180095c97  mov     edi, 1
0x180095c9c  mov     rcx, rax
0x180095c9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180095ca4  or      r9d, 0FFFFFFFFh; cchCount1
0x180095ca8  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180095cad  lea     rcx, aVolumeShadowCo; "Volume Shadow Copy Service Task"
0x180095cb4  mov     [rsp+78h+lpString2], rcx; lpString2
0x180095cb9  mov     r8, rax; lpString1
0x180095cbc  mov     edx, edi; dwCmpFlags
0x180095cbe  mov     ecx, 400h; Locale
0x180095cc3  call    cs:__imp_CompareStringW
0x180095cca  nop     dword ptr [rax+rax+00h]
0x180095ccf  cmp     eax, 2
0x180095cd2  jz      short loc_180095CD9
0x180095cd4  mov     bl, dil
0x180095cd7  jmp     short loc_180095CDB
0x180095cd9  xor     bl, bl
0x180095cdb  test    dil, 1
0x180095cdf  jz      short loc_180095CEC
0x180095ce1  lea     rcx, [rsp+78h+var_30]
0x180095ce6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180095ceb  nop
0x180095cec  mov     rcx, [rsp+78h+var_38]; this
0x180095cf1  test    rcx, rcx
0x180095cf4  jz      short loc_180095CFB
0x180095cf6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180095cfb  mov     al, bl
0x180095cfd  mov     rcx, [rsp+78h+var_10]
0x180095d02  xor     rcx, rsp; StackCookie
0x180095d05  call    __security_check_cookie
0x180095d0a  mov     rbx, [rsp+78h+arg_0]
0x180095d12  add     rsp, 70h
0x180095d16  pop     rdi
0x180095d17  retn
```
