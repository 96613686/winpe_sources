# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)

- ea: `0x18000a360`
- end: `0x18000a40a`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z`
- size: `170`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008848`
- `0x18000a430`

## callees

- `0x180009e68`
- `0x18000a070`
- `0x18000a360`
- `0x18000fc90`

## string_xrefs

- `0x18000a3f8`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x18000a360  mov     r11, rsp
0x18000a363  push    rbx
0x18000a364  sub     rsp, 0C0h
0x18000a36b  mov     rax, cs:__security_cookie
0x18000a372  xor     rax, rsp
0x18000a375  mov     [rsp+0C8h+var_18], rax
0x18000a37d  mov     rbx, rcx
0x18000a380  mov     [rsp+0C8h+var_A0], rcx
0x18000a385  mov     [rsp+0C8h+var_A8], 0
0x18000a38d  xor     eax, eax
0x18000a38f  mov     [rcx], rax
0x18000a392  mov     [rsp+0C8h+var_A8], 1; int
0x18000a39a  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x18000a3a1  mov     [r11-20h], rax
0x18000a3a5  lea     rax, ??_7?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000a3ac  mov     [rsp+0C8h+var_90], rax
0x18000a3b1  lea     rax, [r11-20h]
0x18000a3b5  mov     [rsp+0C8h+var_88], rax
0x18000a3ba  lea     rax, [rsp+0C8h+var_90]
0x18000a3bf  mov     [r11-28h], rax
0x18000a3c3  lea     rdx, [rsp+0C8h+var_98]
0x18000a3c8  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x18000a3cd  test    eax, eax
0x18000a3cf  js      short loc_18000A3ED
0x18000a3d1  mov     rax, rbx
0x18000a3d4  mov     rcx, [rsp+0C8h+var_18]
0x18000a3dc  xor     rcx, rsp; StackCookie
0x18000a3df  call    __security_check_cookie
0x18000a3e4  add     rsp, 0C0h
0x18000a3eb  pop     rbx
0x18000a3ec  retn
0x18000a3ed  mov     rcx, [rsp+0C8h]; this
0x18000a3f5  mov     r9d, eax; char *
0x18000a3f8  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000a3ff  mov     edx, 240h; void *
0x18000a404  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
