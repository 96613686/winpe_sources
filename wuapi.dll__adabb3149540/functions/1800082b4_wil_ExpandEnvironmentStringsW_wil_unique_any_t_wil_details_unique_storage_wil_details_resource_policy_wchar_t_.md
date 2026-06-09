# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)

- ea: `0x1800082b4`
- end: `0x18000835e`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z`
- size: `170`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006f90`
- `0x180007158`

## callees

- `0x1800082b4`
- `0x180009064`
- `0x18000aa38`
- `0x18000fce0`

## string_xrefs

- `0x18000834c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
_QWORD *__fastcall wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
        _QWORD *a1)
{
  int v2; // eax
  _BYTE v4[8]; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v5[14]; // [rsp+38h] [rbp-90h] BYREF
  const wchar_t *v6; // [rsp+A8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *a1 = 0;
  v6 = L"%SystemRoot%\\uus";
  v5[0] = &wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v5[1] = &v6;
  v5[13] = v5;
  v2 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
         a1,
         v4);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x240,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v2,
      1);
  return a1;
}

```

## disassembly

```asm
0x1800082b4  mov     r11, rsp
0x1800082b7  push    rbx
0x1800082b8  sub     rsp, 0C0h
0x1800082bf  mov     rax, cs:__security_cookie
0x1800082c6  xor     rax, rsp
0x1800082c9  mov     [rsp+0C8h+var_18], rax
0x1800082d1  mov     rbx, rcx
0x1800082d4  mov     [rsp+0C8h+var_A0], rcx
0x1800082d9  mov     [rsp+0C8h+var_A8], 0
0x1800082e1  xor     eax, eax
0x1800082e3  mov     [rcx], rax
0x1800082e6  mov     [rsp+0C8h+var_A8], 1; int
0x1800082ee  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x1800082f5  mov     [r11-20h], rax
0x1800082f9  lea     rax, ??_7?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180008300  mov     [rsp+0C8h+var_90], rax
0x180008305  lea     rax, [r11-20h]
0x180008309  mov     [rsp+0C8h+var_88], rax
0x18000830e  lea     rax, [rsp+0C8h+var_90]
0x180008313  mov     [r11-28h], rax
0x180008317  lea     rdx, [rsp+0C8h+var_98]
0x18000831c  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x180008321  test    eax, eax
0x180008323  js      short loc_180008341
0x180008325  mov     rax, rbx
0x180008328  mov     rcx, [rsp+0C8h+var_18]
0x180008330  xor     rcx, rsp; StackCookie
0x180008333  call    __security_check_cookie
0x180008338  add     rsp, 0C0h
0x18000833f  pop     rbx
0x180008340  retn
0x180008341  mov     rcx, [rsp+0C8h]; this
0x180008349  mov     r9d, eax; char *
0x18000834c  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180008353  mov     edx, 240h; void *
0x180008358  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
