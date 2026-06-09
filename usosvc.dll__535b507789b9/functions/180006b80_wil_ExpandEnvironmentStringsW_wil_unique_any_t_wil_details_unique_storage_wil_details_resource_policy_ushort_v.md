# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180006b80`
- end: `0x180006d4e`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006b28`

## callees

- `0x1800026d0`
- `0x180003198`
- `0x1800059c4`
- `0x180006b80`
- `0x180008e70`
- `0x18000a594`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006cbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006caa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d09`

## string_xrefs

- `0x180006cec`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        char *a2)
{
  int v3; // edi
  unsigned __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rdx
  void *v7; // rbx
  unsigned __int64 v8; // rsi
  void *v9; // rsi
  DWORD LastError; // edi
  void *v11; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  const wchar_t *v15; // [rsp+30h] [rbp-D0h] BYREF
  char v16; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[13]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v19; // [rsp+B0h] [rbp-50h]
  _BYTE v20[512]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v15 = L"%SystemRoot%\\uus";
  v18[0] = &wistd::__function::__func<_lambda_ed01672e02d6682bf5b3b76f9b133eec_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v18[1] = &v15;
  v19 = v18;
  pv = 0;
  memset_0(v20, 0, sizeof(v20));
  v14 = 0;
  v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v17, v20, 256, &v14);
  if ( v3 >= 0 )
  {
    v4 = v14;
    if ( v14 > 0x100 )
    {
      while ( 1 )
      {
        v8 = v4;
        v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v4 - 1);
        v3 = v5;
        if ( v5 < 0 )
        {
          v6 = 378;
          goto LABEL_19;
        }
        v7 = pv;
        v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v17, pv, v8, &v14);
        if ( v3 < 0 )
          break;
        v4 = v14;
        if ( v14 <= v8 )
          goto LABEL_9;
      }
      if ( !v7 )
        goto LABEL_21;
      v11 = v7;
      goto LABEL_20;
    }
    v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
           &pv,
           v20,
           v14 - 1);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v7 = pv;
LABEL_9:
      if ( a2 == &v16 )
      {
        if ( v7 )
          CoTaskMemFree(v7);
      }
      else
      {
        v9 = *(void **)a2;
        if ( *(_QWORD *)a2 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v9);
          SetLastError(LastError);
        }
        *(_QWORD *)a2 = v7;
      }
      v3 = 0;
    }
    else
    {
      v6 = 367;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
        (const char *)(unsigned int)v5,
        (int)pv);
      v11 = pv;
      if ( pv )
LABEL_20:
        CoTaskMemFree(v11);
    }
  }
LABEL_21:
  if ( v19 )
    (*(void (__fastcall **)(_QWORD *))(*v19 + 24LL))(v19);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006b80  mov     [rsp-8+arg_0], rbx
0x180006b85  mov     [rsp-8+arg_10], rsi
0x180006b8a  push    rbp
0x180006b8b  push    rdi
0x180006b8c  push    r14
0x180006b8e  lea     rbp, [rsp-1D0h]
0x180006b96  sub     rsp, 2D0h
0x180006b9d  mov     rax, cs:__security_cookie
0x180006ba4  xor     rax, rsp
0x180006ba7  mov     [rbp+1E0h+var_20], rax
0x180006bae  mov     r14, rdx
0x180006bb1  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x180006bb8  mov     [rsp+2E0h+var_2B0], rax
0x180006bbd  lea     rax, ??_7?$__func@V_lambda_ed01672e02d6682bf5b3b76f9b133eec_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_ed01672e02d6682bf5b3b76f9b133eec_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180006bc4  mov     [rsp+2E0h+var_298], rax
0x180006bc9  lea     rax, [rsp+2E0h+var_2B0]
0x180006bce  mov     [rsp+2E0h+var_290], rax
0x180006bd3  lea     rax, [rsp+2E0h+var_298]
0x180006bd8  mov     [rbp+1E0h+var_230], rax
0x180006bdc  mov     [rsp+2E0h+pv], 0; int
0x180006be5  xor     edx, edx; Val
0x180006be7  mov     r8d, 200h; Size
0x180006bed  lea     rcx, [rbp+1E0h+var_220]; void *
0x180006bf1  call    memset_0
0x180006bf6  mov     [rsp+2E0h+var_2B8], 0
0x180006bff  lea     r9, [rsp+2E0h+var_2B8]
0x180006c04  mov     ebx, 100h
0x180006c09  mov     r8d, ebx
0x180006c0c  lea     rdx, [rbp+1E0h+var_220]
0x180006c10  lea     rcx, [rsp+2E0h+var_2A0]
0x180006c15  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180006c1a  mov     edi, eax
0x180006c1c  test    eax, eax
0x180006c1e  js      loc_180006D10
0x180006c24  mov     rax, [rsp+2E0h+var_2B8]
0x180006c29  cmp     rax, rbx
0x180006c2c  ja      short loc_180006C55
0x180006c2e  lea     r8, [rax-1]
0x180006c32  lea     rdx, [rbp+1E0h+var_220]
0x180006c36  lea     rcx, [rsp+2E0h+pv]
0x180006c3b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180006c40  mov     edi, eax
0x180006c42  test    eax, eax
0x180006c44  jns     short loc_180006C4E
0x180006c46  lea     edx, [rbx+6Fh]
0x180006c49  jmp     loc_180006CE9
0x180006c4e  mov     rbx, [rsp+2E0h+pv]
0x180006c53  jmp     short loc_180006C98
0x180006c55  mov     rsi, rax
0x180006c58  lea     r8, [rax-1]
0x180006c5c  xor     edx, edx
0x180006c5e  lea     rcx, [rsp+2E0h+pv]
0x180006c63  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180006c68  mov     edi, eax
0x180006c6a  test    eax, eax
0x180006c6c  js      short loc_180006CE4
0x180006c6e  lea     r9, [rsp+2E0h+var_2B8]
0x180006c73  mov     r8, rsi
0x180006c76  mov     rbx, [rsp+2E0h+pv]
0x180006c7b  mov     rdx, rbx
0x180006c7e  lea     rcx, [rsp+2E0h+var_2A0]
0x180006c83  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180006c88  mov     edi, eax
0x180006c8a  test    eax, eax
0x180006c8c  js      short loc_180006CDA
0x180006c8e  mov     rax, [rsp+2E0h+var_2B8]
0x180006c93  cmp     rax, rsi
0x180006c96  ja      short loc_180006C55
0x180006c98  lea     rax, [rsp+2E0h+var_2A8]
0x180006c9d  cmp     r14, rax
0x180006ca0  jz      short loc_180006CC8
0x180006ca2  mov     rsi, [r14]
0x180006ca5  test    rsi, rsi
0x180006ca8  jz      short loc_180006CC3
0x180006caa  call    cs:__imp_GetLastError
0x180006cb0  mov     edi, eax
0x180006cb2  mov     rcx, rsi; pv
0x180006cb5  call    cs:__imp_CoTaskMemFree
0x180006cbb  mov     ecx, edi; dwErrCode
0x180006cbd  call    cs:__imp_SetLastError
0x180006cc3  mov     [r14], rbx
0x180006cc6  jmp     short loc_180006CD6
0x180006cc8  test    rbx, rbx
0x180006ccb  jz      short loc_180006CD6
0x180006ccd  mov     rcx, rbx; pv
0x180006cd0  call    cs:__imp_CoTaskMemFree
0x180006cd6  xor     edi, edi
0x180006cd8  jmp     short loc_180006D10
0x180006cda  test    rbx, rbx
0x180006cdd  jz      short loc_180006D10
0x180006cdf  mov     rcx, rbx
0x180006ce2  jmp     short loc_180006D09
0x180006ce4  mov     edx, 17Ah; void *
0x180006ce9  mov     r9d, eax; char *
0x180006cec  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006cf3  mov     rcx, [rbp+1E8h]; this
0x180006cfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cff  mov     rcx, [rsp+2E0h+pv]; pv
0x180006d04  test    rcx, rcx
0x180006d07  jz      short loc_180006D10
0x180006d09  call    cs:__imp_CoTaskMemFree
0x180006d0f  nop
0x180006d10  mov     rcx, [rbp+1E0h+var_230]
0x180006d14  test    rcx, rcx
0x180006d17  jz      short loc_180006D25
0x180006d19  mov     rdx, [rcx]
0x180006d1c  mov     rax, [rdx+18h]
0x180006d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d25  mov     eax, edi
0x180006d27  mov     rcx, [rbp+1E0h+var_20]
0x180006d2e  xor     rcx, rsp; StackCookie
0x180006d31  call    __security_check_cookie
0x180006d36  lea     r11, [rsp+2E0h+var_10]
0x180006d3e  mov     rbx, [r11+20h]
0x180006d42  mov     rsi, [r11+30h]
0x180006d46  mov     rsp, r11
0x180006d49  pop     r14
0x180006d4b  pop     rdi
0x180006d4c  pop     rbp
0x180006d4d  retn
```
