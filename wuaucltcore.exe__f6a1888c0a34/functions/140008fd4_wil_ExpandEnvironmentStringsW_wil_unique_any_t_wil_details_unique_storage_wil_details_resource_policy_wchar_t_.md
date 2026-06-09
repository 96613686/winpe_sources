# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)

- ea: `0x140008fd4`
- end: `0x14000907e`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007320`

## callees

- `0x140008fd4`
- `0x14000997c`
- `0x14000bb30`
- `0x14001aa60`

## string_xrefs

- `0x14000906c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
        char *a1)
{
  int v2; // eax
  _BYTE v4[8]; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v5[14]; // [rsp+38h] [rbp-90h] BYREF
  const wchar_t *v6; // [rsp+A8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_QWORD *)a1 = 0;
  v6 = L"%SystemRoot%\\uus";
  v5[0] = &wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v5[1] = &v6;
  v5[13] = v5;
  v2 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
         a1,
         (__int64)v4);
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
0x140008fd4  mov     r11, rsp
0x140008fd7  push    rbx
0x140008fd8  sub     rsp, 0C0h
0x140008fdf  mov     rax, cs:__security_cookie
0x140008fe6  xor     rax, rsp
0x140008fe9  mov     [rsp+0C8h+var_18], rax
0x140008ff1  mov     rbx, rcx
0x140008ff4  mov     [rsp+0C8h+var_A0], rcx
0x140008ff9  mov     [rsp+0C8h+var_A8], 0
0x140009001  xor     eax, eax
0x140009003  mov     [rcx], rax
0x140009006  mov     [rsp+0C8h+var_A8], 1; int
0x14000900e  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x140009015  mov     [r11-20h], rax
0x140009019  lea     rax, ??_7?$__func@V_lambda_e92a0cc36032b557b0292d38c83af5d4_@@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_e92a0cc36032b557b0292d38c83af5d4_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x140009020  mov     [rsp+0C8h+var_90], rax
0x140009025  lea     rax, [r11-20h]
0x140009029  mov     [rsp+0C8h+var_88], rax
0x14000902e  lea     rax, [rsp+0C8h+var_90]
0x140009033  mov     [r11-28h], rax
0x140009037  lea     rdx, [rsp+0C8h+var_98]
0x14000903c  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)
0x140009041  test    eax, eax
0x140009043  js      short loc_140009061
0x140009045  mov     rax, rbx
0x140009048  mov     rcx, [rsp+0C8h+var_18]
0x140009050  xor     rcx, rsp; StackCookie
0x140009053  call    __security_check_cookie
0x140009058  add     rsp, 0C0h
0x14000905f  pop     rbx
0x140009060  retn
0x140009061  mov     rcx, [rsp+0C8h]; this
0x140009069  mov     r9d, eax; char *
0x14000906c  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140009073  mov     edx, 240h; void *
0x140009078  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
