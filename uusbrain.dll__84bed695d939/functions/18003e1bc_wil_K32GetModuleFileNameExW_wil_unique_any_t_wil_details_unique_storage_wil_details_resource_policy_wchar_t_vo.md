# wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)

- ea: `0x18003e1bc`
- end: `0x18003e267`
- name: `??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z`
- size: `171`
- prototype: `char *__fastcall(char *, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034504`
- `0x180037064`
- `0x18003eb80`
- `0x18003ecb0`

## callees

- `0x180026cd8`
- `0x18003deb0`
- `0x18003e1bc`
- `0x1800427d0`

## string_xrefs

- `0x18003e255`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char *__fastcall wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
        char *a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // eax
  _BYTE v6[8]; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v7[14]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v8; // [rsp+A8h] [rbp+3Fh] BYREF
  __int64 v9; // [rsp+B0h] [rbp+47h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *(_QWORD *)a1 = 0;
  v9 = a3;
  v8 = 0;
  v7[0] = &wistd::__function::__func<_lambda_44354332321693c583119f2a7d89b96e_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v7[1] = &v8;
  v7[2] = &v9;
  v7[13] = v7;
  v4 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
         a1,
         (__int64)v6);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x26E,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v4,
      1);
  return a1;
}

```

## disassembly

```asm
0x18003e1bc  mov     [rsp-8+arg_8], rbx
0x18003e1c1  push    rbp
0x18003e1c2  lea     rbp, [rsp-57h]
0x18003e1c7  sub     rsp, 0C0h
0x18003e1ce  mov     rax, cs:__security_cookie
0x18003e1d5  xor     rax, rsp
0x18003e1d8  mov     [rbp+57h+var_8], rax
0x18003e1dc  mov     rbx, rcx
0x18003e1df  mov     [rbp+57h+var_98], rcx
0x18003e1e3  mov     [rbp+57h+var_A0], 0
0x18003e1ea  xor     eax, eax
0x18003e1ec  mov     [rcx], rax
0x18003e1ef  mov     [rbp+57h+var_A0], 1
0x18003e1f6  mov     [rbp+57h+var_10], r8
0x18003e1fa  mov     [rbp+57h+var_18], rax
0x18003e1fe  lea     rax, ??_7?$__func@V_lambda_44354332321693c583119f2a7d89b96e_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_44354332321693c583119f2a7d89b96e_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18003e205  mov     [rbp+57h+var_88], rax
0x18003e209  lea     rax, [rbp+57h+var_18]
0x18003e20d  mov     [rbp+57h+var_80], rax
0x18003e211  lea     rax, [rbp+57h+var_10]
0x18003e215  mov     [rbp+57h+var_78], rax
0x18003e219  lea     rax, [rbp+57h+var_88]
0x18003e21d  mov     [rbp+57h+var_20], rax
0x18003e221  lea     rdx, [rbp+57h+var_90]
0x18003e225  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x18003e22a  test    eax, eax
0x18003e22c  js      short loc_18003E24E
0x18003e22e  mov     rax, rbx
0x18003e231  mov     rcx, [rbp+57h+var_8]
0x18003e235  xor     rcx, rsp; StackCookie
0x18003e238  call    __security_check_cookie
0x18003e23d  mov     rbx, [rsp+0C0h+arg_8]
0x18003e245  add     rsp, 0C0h
0x18003e24c  pop     rbp
0x18003e24d  retn
0x18003e24e  mov     rcx, [rbp+5Fh]; this
0x18003e252  mov     r9d, eax; char *
0x18003e255  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18003e25c  mov     edx, 26Eh; void *
0x18003e261  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
