# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180057e84`
- end: `0x180058018`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `404`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180058020`
- `0x180065a50`

## callees

- `0x180007660`
- `0x18000856c`
- `0x1800183f4`
- `0x180057e84`
- `0x1800584d0`
- `0x18005a1c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057f83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057f96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057f96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057f8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057fa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057fea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057f8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057fa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057fbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057fea`

## string_xrefs

- `0x180057fcd`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        char *a1,
        __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // rax
  int v6; // ebx
  __int64 v7; // rdx
  void *v8; // rbx
  unsigned __int64 v9; // rdi
  int v10; // esi
  void *v11; // rsi
  DWORD LastError; // edi
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  char v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[512]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  pv = 0;
  memset_0(v16, 0, sizeof(v16));
  v14 = 0;
  result = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v16, 256, &v14);
  if ( (int)result >= 0 )
  {
    v5 = v14;
    if ( v14 > 0x100 )
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
          goto LABEL_20;
        }
        v8 = pv;
        v10 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, pv, v9, &v14);
        if ( v10 < 0 )
          break;
        v5 = v14;
        if ( v14 <= v9 )
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
             v16,
             v14 - 1);
      if ( v6 >= 0 )
      {
        v8 = pv;
LABEL_9:
        if ( a1 == &v15 )
        {
          if ( v8 )
            CoTaskMemFree(v8);
        }
        else
        {
          v11 = *(void **)a1;
          if ( *(_QWORD *)a1 )
          {
            LastError = GetLastError();
            CoTaskMemFree(v11);
            SetLastError(LastError);
          }
          *(_QWORD *)a1 = v8;
        }
        return 0;
      }
      else
      {
        v7 = 367;
LABEL_20:
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
0x180057e84  mov     [rsp-8+arg_10], rbx
0x180057e89  push    rbp
0x180057e8a  push    rsi
0x180057e8b  push    rdi
0x180057e8c  push    r14
0x180057e8e  push    r15
0x180057e90  lea     rbp, [rsp-150h]
0x180057e98  sub     rsp, 250h
0x180057e9f  mov     rax, cs:__security_cookie
0x180057ea6  xor     rax, rsp
0x180057ea9  mov     [rbp+170h+var_30], rax
0x180057eb0  mov     r15, rdx
0x180057eb3  mov     r14, rcx
0x180057eb6  mov     [rsp+270h+pv], 0; int
0x180057ebf  xor     edx, edx; Val
0x180057ec1  mov     r8d, 200h; Size
0x180057ec7  lea     rcx, [rsp+270h+var_230]; void *
0x180057ecc  call    memset_0
0x180057ed1  mov     [rsp+270h+var_248], 0
0x180057eda  lea     r9, [rsp+270h+var_248]
0x180057edf  mov     ebx, 100h
0x180057ee4  mov     r8d, ebx
0x180057ee7  lea     rdx, [rsp+270h+var_230]
0x180057eec  mov     rcx, r15
0x180057eef  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180057ef4  test    eax, eax
0x180057ef6  js      loc_180057FF2
0x180057efc  mov     rax, [rsp+270h+var_248]
0x180057f01  cmp     rax, rbx
0x180057f04  ja      short loc_180057F30
0x180057f06  lea     r8, [rax-1]
0x180057f0a  lea     rdx, [rsp+270h+var_230]
0x180057f0f  lea     rcx, [rsp+270h+pv]
0x180057f14  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180057f19  mov     ebx, eax
0x180057f1b  test    eax, eax
0x180057f1d  jns     short loc_180057F29
0x180057f1f  mov     edx, 16Fh
0x180057f24  jmp     loc_180057FCA
0x180057f29  mov     rbx, [rsp+270h+pv]
0x180057f2e  jmp     short loc_180057F71
0x180057f30  mov     rdi, rax
0x180057f33  lea     r8, [rax-1]
0x180057f37  xor     edx, edx
0x180057f39  lea     rcx, [rsp+270h+pv]
0x180057f3e  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180057f43  mov     ebx, eax
0x180057f45  test    eax, eax
0x180057f47  js      short loc_180057FC5
0x180057f49  lea     r9, [rsp+270h+var_248]
0x180057f4e  mov     r8, rdi
0x180057f51  mov     rbx, [rsp+270h+pv]
0x180057f56  mov     rdx, rbx
0x180057f59  mov     rcx, r15
0x180057f5c  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180057f61  mov     esi, eax
0x180057f63  test    eax, eax
0x180057f65  js      short loc_180057FB3
0x180057f67  mov     rax, [rsp+270h+var_248]
0x180057f6c  cmp     rax, rdi
0x180057f6f  ja      short loc_180057F30
0x180057f71  lea     rax, [rsp+270h+var_240]
0x180057f76  cmp     r14, rax
0x180057f79  jz      short loc_180057FA1
0x180057f7b  mov     rsi, [r14]
0x180057f7e  test    rsi, rsi
0x180057f81  jz      short loc_180057F9C
0x180057f83  call    cs:__imp_GetLastError
0x180057f89  mov     edi, eax
0x180057f8b  mov     rcx, rsi; pv
0x180057f8e  call    cs:__imp_CoTaskMemFree
0x180057f94  mov     ecx, edi; dwErrCode
0x180057f96  call    cs:__imp_SetLastError
0x180057f9c  mov     [r14], rbx
0x180057f9f  jmp     short loc_180057FAF
0x180057fa1  test    rbx, rbx
0x180057fa4  jz      short loc_180057FAF
0x180057fa6  mov     rcx, rbx; pv
0x180057fa9  call    cs:__imp_CoTaskMemFree
0x180057faf  xor     eax, eax
0x180057fb1  jmp     short loc_180057FF2
0x180057fb3  test    rbx, rbx
0x180057fb6  jz      short loc_180057FC1
0x180057fb8  mov     rcx, rbx; pv
0x180057fbb  call    cs:__imp_CoTaskMemFree
0x180057fc1  mov     eax, esi
0x180057fc3  jmp     short loc_180057FF2
0x180057fc5  mov     edx, 17Ah; void *
0x180057fca  mov     r9d, ebx; char *
0x180057fcd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180057fd4  mov     rcx, [rbp+178h]; this
0x180057fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057fe0  mov     rcx, [rsp+270h+pv]; pv
0x180057fe5  test    rcx, rcx
0x180057fe8  jz      short loc_180057FF0
0x180057fea  call    cs:__imp_CoTaskMemFree
0x180057ff0  mov     eax, ebx
0x180057ff2  mov     rcx, [rbp+170h+var_30]
0x180057ff9  xor     rcx, rsp; StackCookie
0x180057ffc  call    __security_check_cookie
0x180058001  mov     rbx, [rsp+270h+arg_10]
0x180058009  add     rsp, 250h
0x180058010  pop     r15
0x180058012  pop     r14
0x180058014  pop     rdi
0x180058015  pop     rsi
0x180058016  pop     rbp
0x180058017  retn
```
