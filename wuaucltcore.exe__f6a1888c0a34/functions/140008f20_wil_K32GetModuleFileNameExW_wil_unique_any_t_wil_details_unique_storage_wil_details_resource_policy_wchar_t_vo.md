# wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)

- ea: `0x140008f20`
- end: `0x140008fcb`
- name: `??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000713c`

## callees

- `0x140008f20`
- `0x14000ae78`
- `0x14000bb30`
- `0x14001aa60`

## string_xrefs

- `0x140008fb9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140008f20  mov     [rsp-8+arg_8], rbx
0x140008f25  push    rbp
0x140008f26  lea     rbp, [rsp-57h]
0x140008f2b  sub     rsp, 0C0h
0x140008f32  mov     rax, cs:__security_cookie
0x140008f39  xor     rax, rsp
0x140008f3c  mov     [rbp+57h+var_8], rax
0x140008f40  mov     rbx, rcx
0x140008f43  mov     [rbp+57h+var_98], rcx
0x140008f47  mov     [rbp+57h+var_A0], 0
0x140008f4e  xor     eax, eax
0x140008f50  mov     [rcx], rax
0x140008f53  mov     [rbp+57h+var_A0], 1
0x140008f5a  mov     [rbp+57h+var_10], r8
0x140008f5e  mov     [rbp+57h+var_18], rax
0x140008f62  lea     rax, ??_7?$__func@V_lambda_44354332321693c583119f2a7d89b96e_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_44354332321693c583119f2a7d89b96e_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x140008f69  mov     [rbp+57h+var_88], rax
0x140008f6d  lea     rax, [rbp+57h+var_18]
0x140008f71  mov     [rbp+57h+var_80], rax
0x140008f75  lea     rax, [rbp+57h+var_10]
0x140008f79  mov     [rbp+57h+var_78], rax
0x140008f7d  lea     rax, [rbp+57h+var_88]
0x140008f81  mov     [rbp+57h+var_20], rax
0x140008f85  lea     rdx, [rbp+57h+var_90]
0x140008f89  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x140008f8e  test    eax, eax
0x140008f90  js      short loc_140008FB2
0x140008f92  mov     rax, rbx
0x140008f95  mov     rcx, [rbp+57h+var_8]
0x140008f99  xor     rcx, rsp; StackCookie
0x140008f9c  call    __security_check_cookie
0x140008fa1  mov     rbx, [rsp+0C0h+arg_8]
0x140008fa9  add     rsp, 0C0h
0x140008fb0  pop     rbp
0x140008fb1  retn
0x140008fb2  mov     rcx, [rbp+5Fh]; this
0x140008fb6  mov     r9d, eax; char *
0x140008fb9  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140008fc0  mov     edx, 26Eh; void *
0x140008fc5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
