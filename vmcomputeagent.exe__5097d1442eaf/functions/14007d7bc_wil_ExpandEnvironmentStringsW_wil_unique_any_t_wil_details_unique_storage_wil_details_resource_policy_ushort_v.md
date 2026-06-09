# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x14007d7bc`
- end: `0x14007d983`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `455`
- prototype: `__int64 __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140087d00`

## callees

- `0x140005360`
- `0x140006098`
- `0x14000cef4`
- `0x14007d7bc`
- `0x140085600`
- `0x14009455c`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007d8f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007d8f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007d8df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007d8df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007d8ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007d905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007d93e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007d8ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007d905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14007d93e`

## string_xrefs

- `0x14007d921`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  char v14; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[13]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v17; // [rsp+A0h] [rbp-60h]
  const wchar_t *v18; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v19[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v20[512]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v18 = L"%SystemDrive%\\hpc";
  v16[0] = &wistd::__function::__func<_lambda_1f4a220c340983e6f1ea5f164cc797a5_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v16[1] = &v18;
  v17 = v16;
  pv = 0;
  memset_0(v20, 0, sizeof(v20));
  v19[0] = 0;
  v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v15, v20, 256, v19);
  if ( v3 >= 0 )
  {
    v4 = v19[0];
    if ( v19[0] > 0x100u )
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
        v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v15, pv, v8, v19);
        if ( v3 < 0 )
          break;
        v4 = v19[0];
        if ( v19[0] <= v8 )
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
           v19[0] - 1LL);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v7 = pv;
LABEL_9:
      if ( a2 == &v14 )
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v5,
        (int)pv);
      v11 = pv;
      if ( pv )
LABEL_20:
        CoTaskMemFree(v11);
    }
  }
LABEL_21:
  if ( v17 )
    (*(void (__fastcall **)(_QWORD *))(*v17 + 24LL))(v17);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14007d7bc  mov     [rsp-8+arg_0], rbx
0x14007d7c1  mov     [rsp-8+arg_10], rsi
0x14007d7c6  push    rbp
0x14007d7c7  push    rdi
0x14007d7c8  push    r14
0x14007d7ca  lea     rbp, [rsp-1D0h]
0x14007d7d2  sub     rsp, 2D0h
0x14007d7d9  mov     rax, cs:__security_cookie
0x14007d7e0  xor     rax, rsp
0x14007d7e3  mov     [rbp+1E0h+var_20], rax
0x14007d7ea  mov     r14, rdx
0x14007d7ed  lea     rax, aSystemdriveHpc; "%SystemDrive%\\hpc"
0x14007d7f4  mov     [rbp+1E0h+var_238], rax
0x14007d7f8  lea     rax, ??_7?$__func@V_lambda_1f4a220c340983e6f1ea5f164cc797a5_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_1f4a220c340983e6f1ea5f164cc797a5_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x14007d7ff  mov     [rsp+2E0h+var_2A8], rax
0x14007d804  lea     rax, [rbp+1E0h+var_238]
0x14007d808  mov     [rsp+2E0h+var_2A0], rax
0x14007d80d  lea     rax, [rsp+2E0h+var_2A8]
0x14007d812  mov     [rbp+1E0h+var_240], rax
0x14007d816  mov     [rsp+2E0h+pv], 0; int
0x14007d81f  xor     edx, edx; Val
0x14007d821  mov     r8d, 200h; Size
0x14007d827  lea     rcx, [rbp+1E0h+var_220]; void *
0x14007d82b  call    memset_0
0x14007d830  mov     [rbp+1E0h+var_230], 0
0x14007d838  lea     r9, [rbp+1E0h+var_230]
0x14007d83c  mov     ebx, 100h
0x14007d841  mov     r8d, ebx
0x14007d844  lea     rdx, [rbp+1E0h+var_220]
0x14007d848  lea     rcx, [rsp+2E0h+var_2B0]
0x14007d84d  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x14007d852  mov     edi, eax
0x14007d854  test    eax, eax
0x14007d856  js      loc_14007D945
0x14007d85c  mov     rax, [rbp+1E0h+var_230]
0x14007d860  cmp     rax, rbx
0x14007d863  ja      short loc_14007D88C
0x14007d865  lea     r8, [rax-1]
0x14007d869  lea     rdx, [rbp+1E0h+var_220]
0x14007d86d  lea     rcx, [rsp+2E0h+pv]
0x14007d872  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x14007d877  mov     edi, eax
0x14007d879  test    eax, eax
0x14007d87b  jns     short loc_14007D885
0x14007d87d  lea     edx, [rbx+6Fh]
0x14007d880  jmp     loc_14007D91E
0x14007d885  mov     rbx, [rsp+2E0h+pv]
0x14007d88a  jmp     short loc_14007D8CD
0x14007d88c  mov     rsi, rax
0x14007d88f  lea     r8, [rax-1]
0x14007d893  xor     edx, edx
0x14007d895  lea     rcx, [rsp+2E0h+pv]
0x14007d89a  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x14007d89f  mov     edi, eax
0x14007d8a1  test    eax, eax
0x14007d8a3  js      short loc_14007D919
0x14007d8a5  lea     r9, [rbp+1E0h+var_230]
0x14007d8a9  mov     r8, rsi
0x14007d8ac  mov     rbx, [rsp+2E0h+pv]
0x14007d8b1  mov     rdx, rbx
0x14007d8b4  lea     rcx, [rsp+2E0h+var_2B0]
0x14007d8b9  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x14007d8be  mov     edi, eax
0x14007d8c0  test    eax, eax
0x14007d8c2  js      short loc_14007D90F
0x14007d8c4  mov     rax, [rbp+1E0h+var_230]
0x14007d8c8  cmp     rax, rsi
0x14007d8cb  ja      short loc_14007D88C
0x14007d8cd  lea     rax, [rsp+2E0h+var_2B8]
0x14007d8d2  cmp     r14, rax
0x14007d8d5  jz      short loc_14007D8FD
0x14007d8d7  mov     rsi, [r14]
0x14007d8da  test    rsi, rsi
0x14007d8dd  jz      short loc_14007D8F8
0x14007d8df  call    cs:__imp_GetLastError
0x14007d8e5  mov     edi, eax
0x14007d8e7  mov     rcx, rsi; pv
0x14007d8ea  call    cs:__imp_CoTaskMemFree
0x14007d8f0  mov     ecx, edi; dwErrCode
0x14007d8f2  call    cs:__imp_SetLastError
0x14007d8f8  mov     [r14], rbx
0x14007d8fb  jmp     short loc_14007D90B
0x14007d8fd  test    rbx, rbx
0x14007d900  jz      short loc_14007D90B
0x14007d902  mov     rcx, rbx; pv
0x14007d905  call    cs:__imp_CoTaskMemFree
0x14007d90b  xor     edi, edi
0x14007d90d  jmp     short loc_14007D945
0x14007d90f  test    rbx, rbx
0x14007d912  jz      short loc_14007D945
0x14007d914  mov     rcx, rbx
0x14007d917  jmp     short loc_14007D93E
0x14007d919  mov     edx, 17Ah; void *
0x14007d91e  mov     r9d, eax; char *
0x14007d921  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14007d928  mov     rcx, [rbp+1E8h]; this
0x14007d92f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007d934  mov     rcx, [rsp+2E0h+pv]; pv
0x14007d939  test    rcx, rcx
0x14007d93c  jz      short loc_14007D945
0x14007d93e  call    cs:__imp_CoTaskMemFree
0x14007d944  nop
0x14007d945  mov     rcx, [rbp+1E0h+var_240]
0x14007d949  test    rcx, rcx
0x14007d94c  jz      short loc_14007D95A
0x14007d94e  mov     rdx, [rcx]
0x14007d951  mov     rax, [rdx+18h]
0x14007d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007d95a  mov     eax, edi
0x14007d95c  mov     rcx, [rbp+1E0h+var_20]
0x14007d963  xor     rcx, rsp; StackCookie
0x14007d966  call    __security_check_cookie
0x14007d96b  lea     r11, [rsp+2E0h+var_10]
0x14007d973  mov     rbx, [r11+20h]
0x14007d977  mov     rsi, [r11+30h]
0x14007d97b  mov     rsp, r11
0x14007d97e  pop     r14
0x14007d980  pop     rdi
0x14007d981  pop     rbp
0x14007d982  retn
```
