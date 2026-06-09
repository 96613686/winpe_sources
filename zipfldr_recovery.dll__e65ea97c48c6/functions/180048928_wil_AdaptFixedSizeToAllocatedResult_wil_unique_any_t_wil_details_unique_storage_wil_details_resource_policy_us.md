# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180048928`
- end: `0x180048aa0`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180059fe8`

## callees

- `0x180030c74`
- `0x180031e94`
- `0x180032480`
- `0x180036f50`
- `0x180037958`
- `0x180046d88`
- `0x180048928`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a72`

## string_xrefs

- `0x180048a59`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

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
          (const char *)(unsigned int)v6);
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
0x180048928  mov     [rsp-8+arg_10], rbx
0x18004892d  push    rbp
0x18004892e  push    rsi
0x18004892f  push    rdi
0x180048930  push    r14
0x180048932  push    r15
0x180048934  lea     rbp, [rsp-140h]
0x18004893c  sub     rsp, 240h
0x180048943  mov     rax, cs:__security_cookie
0x18004894a  xor     rax, rsp
0x18004894d  mov     [rbp+160h+var_30], rax
0x180048954  mov     r14, rdx
0x180048957  mov     [rsp+260h+pv], 0
0x180048960  mov     r15, rcx
0x180048963  xor     edx, edx; Val
0x180048965  lea     rcx, [rsp+260h+var_230]; void *
0x18004896a  mov     r8d, 200h; Size
0x180048970  call    memset_0
0x180048975  mov     ebx, 100h
0x18004897a  mov     [rsp+260h+var_238], 0
0x180048983  mov     r8d, ebx
0x180048986  lea     r9, [rsp+260h+var_238]
0x18004898b  lea     rdx, [rsp+260h+var_230]
0x180048990  mov     rcx, r14
0x180048993  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180048998  test    eax, eax
0x18004899a  js      loc_180048A7A
0x1800489a0  mov     rax, [rsp+260h+var_238]
0x1800489a5  cmp     rax, rbx
0x1800489a8  ja      short loc_1800489D4
0x1800489aa  lea     r8, [rax-1]
0x1800489ae  lea     rdx, [rsp+260h+var_230]
0x1800489b3  lea     rcx, [rsp+260h+pv]
0x1800489b8  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x1800489bd  mov     ebx, eax
0x1800489bf  test    eax, eax
0x1800489c1  jns     short loc_1800489CD
0x1800489c3  mov     edx, 16Fh
0x1800489c8  jmp     loc_180048A52
0x1800489cd  mov     rbx, [rsp+260h+pv]
0x1800489d2  jmp     short loc_180048A15
0x1800489d4  lea     r8, [rax-1]
0x1800489d8  xor     edx, edx
0x1800489da  lea     rcx, [rsp+260h+pv]
0x1800489df  mov     rdi, rax
0x1800489e2  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x1800489e7  mov     ebx, eax
0x1800489e9  test    eax, eax
0x1800489eb  js      short loc_180048A4D
0x1800489ed  mov     rbx, [rsp+260h+pv]
0x1800489f2  lea     r9, [rsp+260h+var_238]
0x1800489f7  mov     rdx, rbx
0x1800489fa  mov     r8, rdi
0x1800489fd  mov     rcx, r14
0x180048a00  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180048a05  mov     esi, eax
0x180048a07  test    eax, eax
0x180048a09  js      short loc_180048A3B
0x180048a0b  mov     rax, [rsp+260h+var_238]
0x180048a10  cmp     rax, rdi
0x180048a13  ja      short loc_1800489D4
0x180048a15  lea     rdx, [rsp+260h+pv]
0x180048a1a  mov     [rsp+260h+pv], rbx
0x180048a1f  mov     rcx, r15
0x180048a22  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180048a27  mov     rcx, [rsp+260h+pv]; pv
0x180048a2c  test    rcx, rcx
0x180048a2f  jz      short loc_180048A37
0x180048a31  call    cs:__imp_CoTaskMemFree
0x180048a37  xor     eax, eax
0x180048a39  jmp     short loc_180048A7A
0x180048a3b  test    rbx, rbx
0x180048a3e  jz      short loc_180048A49
0x180048a40  mov     rcx, rbx; pv
0x180048a43  call    cs:__imp_CoTaskMemFree
0x180048a49  mov     eax, esi
0x180048a4b  jmp     short loc_180048A7A
0x180048a4d  mov     edx, 17Ah
0x180048a52  mov     rcx, [rbp+168h]
0x180048a59  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180048a60  mov     r9d, ebx
0x180048a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048a68  mov     rcx, [rsp+260h+pv]; pv
0x180048a6d  test    rcx, rcx
0x180048a70  jz      short loc_180048A78
0x180048a72  call    cs:__imp_CoTaskMemFree
0x180048a78  mov     eax, ebx
0x180048a7a  mov     rcx, [rbp+160h+var_30]
0x180048a81  xor     rcx, rsp; StackCookie
0x180048a84  call    __security_check_cookie
0x180048a89  mov     rbx, [rsp+260h+arg_10]
0x180048a91  add     rsp, 240h
0x180048a98  pop     r15
0x180048a9a  pop     r14
0x180048a9c  pop     rdi
0x180048a9d  pop     rsi
0x180048a9e  pop     rbp
0x180048a9f  retn
```
