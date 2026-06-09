# WcmSelectableConnection::get_Name(ushort * *)

- ea: `0x180016e10`
- end: `0x180016eb7`
- name: `?get_Name@WcmSelectableConnection@@UEAAJPEAPEAG@Z`
- size: `167`
- prototype: `__int64 __fastcall(WcmSelectableConnection *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005280`
- `0x1800152c4`
- `0x180015424`
- `0x180016d00`
- `0x180016e10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016e81`

## pseudocode

```c
__int64 __fastcall WcmSelectableConnection::get_Name(WcmSelectableConnection *this, unsigned __int16 **a2)
{
  __int64 v4; // r8
  const char *v5; // r9
  unsigned __int16 *v6; // rax
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r10
  void *v10[3]; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetImpl'::`2'::impl) )
  {
    v10[0] = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v10,
      (char *)this + 24,
      v4,
      v5);
    v6 = (unsigned __int16 *)v10[0];
    if ( !v10[0] )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v10);
      return 2147942414LL;
    }
    v10[0] = 0;
    *a2 = v6;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v10);
  }
  else
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc(0x200u);
    if ( v8 )
    {
      StringCchCopyW(v8, 0x100u, (const unsigned __int16 *)this + 12);
      *a2 = v9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016e10  mov     [rsp+arg_10], rbx
0x180016e15  push    rdi
0x180016e16  sub     rsp, 30h
0x180016e1a  mov     rbx, rdx
0x180016e1d  mov     qword ptr [rdx], 0
0x180016e24  mov     rdi, rcx
0x180016e27  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety> `wil::Feature<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetImpl(void)'::`2'::impl
0x180016e2e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::__private_IsEnabled(void)
0x180016e33  test    al, al
0x180016e35  jz      short loc_180016E7C
0x180016e37  lea     rdx, [rdi+18h]
0x180016e3b  mov     [rsp+38h+var_18], 0
0x180016e44  lea     rcx, [rsp+38h+var_18]
0x180016e49  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180016e4e  mov     rax, [rsp+38h+var_18]
0x180016e53  lea     rcx, [rsp+38h+var_18]
0x180016e58  test    rax, rax
0x180016e5b  jnz     short loc_180016E69
0x180016e5d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016e62  mov     eax, 8007000Eh
0x180016e67  jmp     short loc_180016EAB
0x180016e69  mov     [rsp+38h+var_18], 0
0x180016e72  mov     [rbx], rax
0x180016e75  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016e7a  jmp     short loc_180016EA9
0x180016e7c  mov     ecx, 200h; cb
0x180016e81  call    cs:__imp_CoTaskMemAlloc
0x180016e88  nop     dword ptr [rax+rax+00h]
0x180016e8d  mov     r10, rax
0x180016e90  test    rax, rax
0x180016e93  jz      short loc_180016EA9
0x180016e95  lea     r8, [rdi+18h]; unsigned __int16 *
0x180016e99  mov     edx, 100h; unsigned __int64
0x180016e9e  mov     rcx, rax; unsigned __int16 *
0x180016ea1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016ea6  mov     [rbx], r10
0x180016ea9  xor     eax, eax
0x180016eab  mov     rbx, [rsp+38h+arg_10]
0x180016eb0  add     rsp, 30h
0x180016eb4  pop     rdi
0x180016eb5  retn
```
