# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180004e5c`
- end: `0x180004fd4`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028f40`

## callees

- `0x180004e10`
- `0x180004e5c`
- `0x180004fdc`
- `0x180005000`
- `0x180005cc0`
- `0x18000687c`
- `0x180029e6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fa6`

## string_xrefs

- `0x180004f89`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // rax
  int v6; // ebx
  __int64 v7; // rdx
  void *v8; // rbx
  unsigned __int64 v9; // rdi
  int v10; // esi
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v12; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v13[512]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  pv = 0;
  memset_0(v13, 0, sizeof(v13));
  v12 = 0;
  result = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v13, 256, &v12);
  if ( (int)result >= 0 )
  {
    v5 = v12;
    if ( v12 > 0x100 )
    {
      while ( 1 )
      {
        v9 = v5;
        v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v5 - 1);
        if ( v6 < 0 )
        {
          v7 = 378;
          goto LABEL_16;
        }
        v8 = pv;
        v10 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, pv, v9, &v12);
        if ( v10 < 0 )
          break;
        v5 = v12;
        if ( v12 <= v9 )
          goto LABEL_9;
      }
      if ( v8 )
        CoTaskMemFree(v8);
      return (unsigned int)v10;
    }
    else
    {
      v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
             &pv,
             v13,
             v12 - 1);
      if ( v6 >= 0 )
      {
        v8 = pv;
LABEL_9:
        pv = v8;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          a1,
          &pv);
        if ( pv )
          CoTaskMemFree(pv);
        return 0;
      }
      else
      {
        v7 = 367;
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
          (const char *)(unsigned int)v6,
          (int)pv);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)v6;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004e5c  mov     [rsp-8+arg_10], rbx
0x180004e61  push    rbp
0x180004e62  push    rsi
0x180004e63  push    rdi
0x180004e64  push    r14
0x180004e66  push    r15
0x180004e68  lea     rbp, [rsp-140h]
0x180004e70  sub     rsp, 240h
0x180004e77  mov     rax, cs:__security_cookie
0x180004e7e  xor     rax, rsp
0x180004e81  mov     [rbp+160h+var_30], rax
0x180004e88  mov     r14, rdx
0x180004e8b  mov     r15, rcx
0x180004e8e  mov     [rsp+260h+pv], 0; int
0x180004e97  xor     edx, edx; Val
0x180004e99  mov     r8d, 200h; Size
0x180004e9f  lea     rcx, [rsp+260h+var_230]; void *
0x180004ea4  call    memset_0
0x180004ea9  mov     [rsp+260h+var_238], 0
0x180004eb2  lea     r9, [rsp+260h+var_238]
0x180004eb7  mov     ebx, 100h
0x180004ebc  mov     r8d, ebx
0x180004ebf  lea     rdx, [rsp+260h+var_230]
0x180004ec4  mov     rcx, r14
0x180004ec7  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180004ecc  test    eax, eax
0x180004ece  js      loc_180004FAE
0x180004ed4  mov     rax, [rsp+260h+var_238]
0x180004ed9  cmp     rax, rbx
0x180004edc  ja      short loc_180004F08
0x180004ede  lea     r8, [rax-1]
0x180004ee2  lea     rdx, [rsp+260h+var_230]
0x180004ee7  lea     rcx, [rsp+260h+pv]
0x180004eec  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180004ef1  mov     ebx, eax
0x180004ef3  test    eax, eax
0x180004ef5  jns     short loc_180004F01
0x180004ef7  mov     edx, 16Fh
0x180004efc  jmp     loc_180004F86
0x180004f01  mov     rbx, [rsp+260h+pv]
0x180004f06  jmp     short loc_180004F49
0x180004f08  mov     rdi, rax
0x180004f0b  lea     r8, [rax-1]
0x180004f0f  xor     edx, edx
0x180004f11  lea     rcx, [rsp+260h+pv]
0x180004f16  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180004f1b  mov     ebx, eax
0x180004f1d  test    eax, eax
0x180004f1f  js      short loc_180004F81
0x180004f21  lea     r9, [rsp+260h+var_238]
0x180004f26  mov     r8, rdi
0x180004f29  mov     rbx, [rsp+260h+pv]
0x180004f2e  mov     rdx, rbx
0x180004f31  mov     rcx, r14
0x180004f34  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180004f39  mov     esi, eax
0x180004f3b  test    eax, eax
0x180004f3d  js      short loc_180004F6F
0x180004f3f  mov     rax, [rsp+260h+var_238]
0x180004f44  cmp     rax, rdi
0x180004f47  ja      short loc_180004F08
0x180004f49  mov     [rsp+260h+pv], rbx
0x180004f4e  lea     rdx, [rsp+260h+pv]
0x180004f53  mov     rcx, r15
0x180004f56  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180004f5b  mov     rcx, [rsp+260h+pv]; pv
0x180004f60  test    rcx, rcx
0x180004f63  jz      short loc_180004F6B
0x180004f65  call    cs:__imp_CoTaskMemFree
0x180004f6b  xor     eax, eax
0x180004f6d  jmp     short loc_180004FAE
0x180004f6f  test    rbx, rbx
0x180004f72  jz      short loc_180004F7D
0x180004f74  mov     rcx, rbx; pv
0x180004f77  call    cs:__imp_CoTaskMemFree
0x180004f7d  mov     eax, esi
0x180004f7f  jmp     short loc_180004FAE
0x180004f81  mov     edx, 17Ah; void *
0x180004f86  mov     r9d, ebx; char *
0x180004f89  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004f90  mov     rcx, [rbp+168h]; this
0x180004f97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f9c  mov     rcx, [rsp+260h+pv]; pv
0x180004fa1  test    rcx, rcx
0x180004fa4  jz      short loc_180004FAC
0x180004fa6  call    cs:__imp_CoTaskMemFree
0x180004fac  mov     eax, ebx
0x180004fae  mov     rcx, [rbp+160h+var_30]
0x180004fb5  xor     rcx, rsp; StackCookie
0x180004fb8  call    __security_check_cookie
0x180004fbd  mov     rbx, [rsp+260h+arg_10]
0x180004fc5  add     rsp, 240h
0x180004fcc  pop     r15
0x180004fce  pop     r14
0x180004fd0  pop     rdi
0x180004fd1  pop     rsi
0x180004fd2  pop     rbp
0x180004fd3  retn
```
