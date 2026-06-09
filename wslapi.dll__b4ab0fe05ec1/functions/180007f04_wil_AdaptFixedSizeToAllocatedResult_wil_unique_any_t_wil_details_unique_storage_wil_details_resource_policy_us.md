# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180007f04`
- end: `0x180008079`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180009270`

## callees

- `0x180001dc0`
- `0x180002ab4`
- `0x180004fd4`
- `0x18000698c`
- `0x180007f04`
- `0x180008678`
- `0x18000885c`
- `0x1800090ac`

## string_xrefs

- `0x180008033`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rax
  int v6; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rbx
  unsigned __int64 v10; // rdi
  int v11; // eax
  int v13[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v15[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[512]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *(_QWORD *)v13 = 0;
  memset_0(v16, 0, sizeof(v16));
  v15[0] = 0;
  v4 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v16, 256, v15);
  if ( v4 < 0 )
    goto LABEL_13;
  v5 = v15[0];
  if ( v15[0] > 0x100u )
  {
    while ( 1 )
    {
      v10 = v5;
      v4 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
             v13,
             0,
             v5 - 1);
      if ( v4 < 0 )
        break;
      v9 = *(_QWORD *)v13;
      v11 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
              a2,
              *(_QWORD *)v13,
              v10,
              v15);
      if ( v11 < 0 )
      {
        v4 = v11;
        goto LABEL_13;
      }
      v5 = v15[0];
      if ( v15[0] <= v10 )
        goto LABEL_9;
    }
    v7 = (unsigned int)v4;
    v8 = 378;
    goto LABEL_12;
  }
  v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
         v13,
         v16,
         v15[0] - 1LL);
  v4 = v6;
  if ( v6 < 0 )
  {
    v7 = (unsigned int)v6;
    v8 = 367;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)v7,
      v13[0]);
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v13);
    return (unsigned int)v4;
  }
  v9 = *(_QWORD *)v13;
LABEL_9:
  v14 = v9;
  *(_QWORD *)v13 = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a1,
    &v14);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v13);
  return 0;
}

```

## disassembly

```asm
0x180007f04  mov     [rsp-8+arg_10], rbx
0x180007f09  mov     [rsp-8+arg_18], rsi
0x180007f0e  push    rbp
0x180007f0f  push    rdi
0x180007f10  push    r14
0x180007f12  lea     rbp, [rsp-150h]
0x180007f1a  sub     rsp, 250h
0x180007f21  mov     rax, cs:__security_cookie
0x180007f28  xor     rax, rsp
0x180007f2b  mov     [rbp+160h+var_20], rax
0x180007f32  mov     rsi, rdx
0x180007f35  mov     r14, rcx
0x180007f38  mov     qword ptr [rsp+260h+var_240], 0; int
0x180007f41  xor     edx, edx; Val
0x180007f43  mov     r8d, 200h; Size
0x180007f49  lea     rcx, [rsp+260h+var_220]; void *
0x180007f4e  call    memset_0
0x180007f53  mov     [rsp+260h+var_230], 0
0x180007f5c  lea     r9, [rsp+260h+var_230]
0x180007f61  mov     edi, 100h
0x180007f66  mov     r8d, edi
0x180007f69  lea     rdx, [rsp+260h+var_220]
0x180007f6e  mov     rcx, rsi
0x180007f71  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180007f76  mov     ebx, eax
0x180007f78  test    eax, eax
0x180007f7a  js      loc_180008046
0x180007f80  mov     rax, [rsp+260h+var_230]
0x180007f85  cmp     rax, rdi
0x180007f88  ja      short loc_180007FB5
0x180007f8a  lea     r8, [rax-1]
0x180007f8e  lea     rdx, [rsp+260h+var_220]
0x180007f93  lea     rcx, [rsp+260h+var_240]
0x180007f98  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180007f9d  mov     ebx, eax
0x180007f9f  test    eax, eax
0x180007fa1  jns     short loc_180007FAE
0x180007fa3  mov     r9d, eax
0x180007fa6  lea     edx, [rdi+6Fh]
0x180007fa9  jmp     loc_180008033
0x180007fae  mov     rbx, qword ptr [rsp+260h+var_240]
0x180007fb3  jmp     short loc_180007FF4
0x180007fb5  mov     rdi, rax
0x180007fb8  lea     r8, [rax-1]
0x180007fbc  xor     edx, edx
0x180007fbe  lea     rcx, [rsp+260h+var_240]
0x180007fc3  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180007fc8  mov     ebx, eax
0x180007fca  test    eax, eax
0x180007fcc  js      short loc_18000802B
0x180007fce  lea     r9, [rsp+260h+var_230]
0x180007fd3  mov     r8, rdi
0x180007fd6  mov     rbx, qword ptr [rsp+260h+var_240]
0x180007fdb  mov     rdx, rbx
0x180007fde  mov     rcx, rsi
0x180007fe1  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180007fe6  test    eax, eax
0x180007fe8  js      short loc_180008027
0x180007fea  mov     rax, [rsp+260h+var_230]
0x180007fef  cmp     rax, rdi
0x180007ff2  ja      short loc_180007FB5
0x180007ff4  mov     [rsp+260h+var_238], rbx
0x180007ff9  mov     qword ptr [rsp+260h+var_240], 0
0x180008002  lea     rdx, [rsp+260h+var_238]
0x180008007  mov     rcx, r14
0x18000800a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000800f  lea     rcx, [rsp+260h+var_238]
0x180008014  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008019  lea     rcx, [rsp+260h+var_240]
0x18000801e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008023  xor     eax, eax
0x180008025  jmp     short loc_180008052
0x180008027  mov     ebx, eax
0x180008029  jmp     short loc_180008046
0x18000802b  mov     r9d, ebx; char *
0x18000802e  mov     edx, 17Ah; void *
0x180008033  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000803a  mov     rcx, [rbp+168h]; this
0x180008041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008046  lea     rcx, [rsp+260h+var_240]
0x18000804b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180008050  mov     eax, ebx
0x180008052  mov     rcx, [rbp+160h+var_20]
0x180008059  xor     rcx, rsp; StackCookie
0x18000805c  call    __security_check_cookie
0x180008061  lea     r11, [rsp+260h+var_10]
0x180008069  mov     rbx, [r11+30h]
0x18000806d  mov     rsi, [r11+38h]
0x180008071  mov     rsp, r11
0x180008074  pop     r14
0x180008076  pop     rdi
0x180008077  pop     rbp
0x180008078  retn
```
