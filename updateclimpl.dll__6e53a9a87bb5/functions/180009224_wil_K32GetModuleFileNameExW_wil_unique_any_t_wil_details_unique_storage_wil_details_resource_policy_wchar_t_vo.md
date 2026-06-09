# wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)

- ea: `0x180009224`
- end: `0x1800092da`
- name: `??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z`
- size: `182`
- prototype: `char *__fastcall(char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000892c`

## callees

- `0x180009224`
- `0x18000b88c`
- `0x18000bc40`
- `0x180010310`

## string_xrefs

- `0x1800092c8`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
char *__fastcall wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
        char *a1)
{
  int v2; // eax
  _BYTE v4[8]; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v5[14]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v6; // [rsp+A8h] [rbp+3Fh] BYREF
  unsigned __int64 v7; // [rsp+B0h] [rbp+47h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *(_QWORD *)a1 = 0;
  v7 = 0x180000000uLL;
  v6 = 0;
  v5[0] = wistd::__function::Z::$$A6AJPEA_W_KPEA_K::Z::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>'::`2'::_lambda_1_,AJPEAXPEAUHINSTANCE__,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &>::`vftable';
  v5[1] = &v6;
  v5[2] = &v7;
  v5[13] = v5;
  v2 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
         a1,
         (__int64)v4);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x26E,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v2,
      1);
  return a1;
}

```

## disassembly

```asm
0x180009224  mov     [rsp-8+arg_8], rbx
0x180009229  push    rbp
0x18000922a  lea     rbp, [rsp-57h]
0x18000922f  sub     rsp, 0C0h
0x180009236  mov     rax, cs:__security_cookie
0x18000923d  xor     rax, rsp
0x180009240  mov     [rbp+57h+var_8], rax
0x180009244  mov     rbx, rcx
0x180009247  mov     [rbp+57h+var_98], rcx
0x18000924b  mov     [rbp+57h+var_A0], 0
0x180009252  xor     eax, eax
0x180009254  mov     [rcx], rax
0x180009257  mov     [rbp+57h+var_A0], 1
0x18000925e  lea     rax, cs:180000000h
0x180009265  mov     [rbp+57h+var_10], rax
0x180009269  mov     [rbp+57h+var_18], 0
0x180009271  lea     rax, ??_7?$__func@V_lambda_1_@?1???$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180009278  mov     [rbp+57h+var_88], rax
0x18000927c  lea     rax, [rbp+57h+var_18]
0x180009280  mov     [rbp+57h+var_80], rax
0x180009284  lea     rax, [rbp+57h+var_10]
0x180009288  mov     [rbp+57h+var_78], rax
0x18000928c  lea     rax, [rbp+57h+var_88]
0x180009290  mov     [rbp+57h+var_20], rax
0x180009294  lea     rdx, [rbp+57h+var_90]
0x180009298  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x18000929d  test    eax, eax
0x18000929f  js      short loc_1800092C1
0x1800092a1  mov     rax, rbx
0x1800092a4  mov     rcx, [rbp+57h+var_8]
0x1800092a8  xor     rcx, rsp; StackCookie
0x1800092ab  call    __security_check_cookie
0x1800092b0  mov     rbx, [rsp+0C0h+arg_8]
0x1800092b8  add     rsp, 0C0h
0x1800092bf  pop     rbp
0x1800092c0  retn
0x1800092c1  mov     rcx, [rbp+5Fh]; this
0x1800092c5  mov     r9d, eax; char *
0x1800092c8  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800092cf  mov     edx, 26Eh; void *
0x1800092d4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
