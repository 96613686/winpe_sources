# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x18000b88c`
- end: `0x18000ba70`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009224`

## callees

- `0x180005e80`
- `0x18000b6d4`
- `0x18000b828`
- `0x18000b88c`
- `0x180010310`
- `0x1800148e0`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b9b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b9ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ba30`

## string_xrefs

- `0x18000ba16`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
        char *a1,
        __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rcx
  void (*v6)(void); // rax
  unsigned __int64 v7; // rax
  __int64 v8; // rdx
  void *v9; // rbx
  unsigned __int64 v10; // rdi
  int v11; // r14d
  void *v12; // r14
  DWORD LastError; // edi
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  char v19; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[256]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  pv = 0;
  memset(v21, 0, sizeof(v21));
  v20[0] = 0;
  v4 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v21, 128, v20);
  if ( v4 < 0 )
  {
    v5 = *(_QWORD *)(a2 + 112);
    if ( !v5 )
      return (unsigned int)v4;
    v6 = *(void (**)(void))(*(_QWORD *)v5 + 24LL);
LABEL_30:
    v6();
    return (unsigned int)v4;
  }
  v7 = v20[0];
  if ( v20[0] > 0x80u )
  {
    while ( 1 )
    {
      v10 = v7;
      v4 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
             &pv,
             0,
             v7 - 1);
      if ( v4 < 0 )
      {
        v8 = 362;
        goto LABEL_26;
      }
      v9 = pv;
      v11 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, pv, v10, v20);
      if ( v11 < 0 )
        break;
      v7 = v20[0];
      if ( v20[0] <= v10 )
        goto LABEL_11;
    }
    if ( v9 )
      CoTaskMemFree(v9);
    v16 = *(_QWORD *)(a2 + 112);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
    return (unsigned int)v11;
  }
  else
  {
    v4 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
           &pv,
           v21,
           v20[0] - 1LL);
    if ( v4 < 0 )
    {
      v8 = 351;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v4,
        (int)pv);
      if ( pv )
        CoTaskMemFree(pv);
      v17 = *(_QWORD *)(a2 + 112);
      if ( !v17 )
        return (unsigned int)v4;
      v6 = *(void (**)(void))(*(_QWORD *)v17 + 24LL);
      goto LABEL_30;
    }
    v9 = pv;
LABEL_11:
    if ( a1 == &v19 )
    {
      if ( v9 )
        CoTaskMemFree(v9);
    }
    else
    {
      v12 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v12);
        SetLastError(LastError);
      }
      *(_QWORD *)a1 = v9;
    }
    v14 = *(_QWORD *)(a2 + 112);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b88c  mov     [rsp-8+arg_10], rbx
0x18000b891  push    rbp
0x18000b892  push    rsi
0x18000b893  push    rdi
0x18000b894  push    r14
0x18000b896  push    r15
0x18000b898  lea     rbp, [rsp-50h]
0x18000b89d  sub     rsp, 150h
0x18000b8a4  mov     rax, cs:__security_cookie
0x18000b8ab  xor     rax, rsp
0x18000b8ae  mov     [rbp+70h+var_30], rax
0x18000b8b2  mov     rsi, rdx
0x18000b8b5  mov     r15, rcx
0x18000b8b8  mov     [rsp+170h+pv], 0; int
0x18000b8c1  xor     edx, edx; Val
0x18000b8c3  mov     r8d, 100h; Size
0x18000b8c9  lea     rcx, [rsp+170h+var_130]; void *
0x18000b8ce  call    memset
0x18000b8d3  mov     [rsp+170h+var_140], 0
0x18000b8dc  lea     r9, [rsp+170h+var_140]
0x18000b8e1  mov     edi, 80h
0x18000b8e6  mov     r8d, edi
0x18000b8e9  lea     rdx, [rsp+170h+var_130]
0x18000b8ee  mov     rcx, rsi
0x18000b8f1  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18000b8f6  mov     ebx, eax
0x18000b8f8  test    eax, eax
0x18000b8fa  jns     short loc_18000B915
0x18000b8fc  mov     rcx, [rsi+70h]
0x18000b900  test    rcx, rcx
0x18000b903  jz      loc_18000BA4B
0x18000b909  mov     rdx, [rcx]
0x18000b90c  mov     rax, [rdx+18h]
0x18000b910  jmp     loc_18000BA46
0x18000b915  mov     rax, [rsp+170h+var_140]
0x18000b91a  cmp     rax, rdi
0x18000b91d  ja      short loc_18000B949
0x18000b91f  lea     r8, [rax-1]
0x18000b923  lea     rdx, [rsp+170h+var_130]
0x18000b928  lea     rcx, [rsp+170h+pv]
0x18000b92d  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18000b932  mov     ebx, eax
0x18000b934  test    eax, eax
0x18000b936  jns     short loc_18000B942
0x18000b938  mov     edx, 15Fh
0x18000b93d  jmp     loc_18000BA13
0x18000b942  mov     rbx, [rsp+170h+pv]
0x18000b947  jmp     short loc_18000B98F
0x18000b949  mov     rdi, rax
0x18000b94c  lea     r8, [rax-1]
0x18000b950  xor     edx, edx
0x18000b952  lea     rcx, [rsp+170h+pv]
0x18000b957  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18000b95c  mov     ebx, eax
0x18000b95e  test    eax, eax
0x18000b960  js      loc_18000BA0E
0x18000b966  lea     r9, [rsp+170h+var_140]
0x18000b96b  mov     r8, rdi
0x18000b96e  mov     rbx, [rsp+170h+pv]
0x18000b973  mov     rdx, rbx
0x18000b976  mov     rcx, rsi
0x18000b979  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18000b97e  mov     r14d, eax
0x18000b981  test    eax, eax
0x18000b983  js      short loc_18000B9E6
0x18000b985  mov     rax, [rsp+170h+var_140]
0x18000b98a  cmp     rax, rdi
0x18000b98d  ja      short loc_18000B949
0x18000b98f  lea     rax, [rsp+170h+var_148]
0x18000b994  cmp     r15, rax
0x18000b997  jz      short loc_18000B9BF
0x18000b999  mov     r14, [r15]
0x18000b99c  test    r14, r14
0x18000b99f  jz      short loc_18000B9BA
0x18000b9a1  call    cs:__imp_GetLastError
0x18000b9a7  mov     edi, eax
0x18000b9a9  mov     rcx, r14; pv
0x18000b9ac  call    cs:__imp_CoTaskMemFree
0x18000b9b2  mov     ecx, edi; dwErrCode
0x18000b9b4  call    cs:__imp_SetLastError
0x18000b9ba  mov     [r15], rbx
0x18000b9bd  jmp     short loc_18000B9CD
0x18000b9bf  test    rbx, rbx
0x18000b9c2  jz      short loc_18000B9CD
0x18000b9c4  mov     rcx, rbx; pv
0x18000b9c7  call    cs:__imp_CoTaskMemFree
0x18000b9cd  mov     rcx, [rsi+70h]
0x18000b9d1  test    rcx, rcx
0x18000b9d4  jz      short loc_18000B9E2
0x18000b9d6  mov     rax, [rcx]
0x18000b9d9  mov     rax, [rax+18h]
0x18000b9dd  call    _guard_dispatch_icall
0x18000b9e2  xor     eax, eax
0x18000b9e4  jmp     short loc_18000BA4D
0x18000b9e6  test    rbx, rbx
0x18000b9e9  jz      short loc_18000B9F4
0x18000b9eb  mov     rcx, rbx; pv
0x18000b9ee  call    cs:__imp_CoTaskMemFree
0x18000b9f4  mov     rcx, [rsi+70h]
0x18000b9f8  test    rcx, rcx
0x18000b9fb  jz      short loc_18000BA09
0x18000b9fd  mov     rax, [rcx]
0x18000ba00  mov     rax, [rax+18h]
0x18000ba04  call    _guard_dispatch_icall
0x18000ba09  mov     eax, r14d
0x18000ba0c  jmp     short loc_18000BA4D
0x18000ba0e  mov     edx, 16Ah; void *
0x18000ba13  mov     r9d, ebx; char *
0x18000ba16  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000ba1d  mov     rcx, [rbp+78h]; this
0x18000ba21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba26  mov     rcx, [rsp+170h+pv]; pv
0x18000ba2b  test    rcx, rcx
0x18000ba2e  jz      short loc_18000BA36
0x18000ba30  call    cs:__imp_CoTaskMemFree
0x18000ba36  mov     rcx, [rsi+70h]
0x18000ba3a  test    rcx, rcx
0x18000ba3d  jz      short loc_18000BA4B
0x18000ba3f  mov     rax, [rcx]
0x18000ba42  mov     rax, [rax+18h]
0x18000ba46  call    _guard_dispatch_icall
0x18000ba4b  mov     eax, ebx
0x18000ba4d  mov     rcx, [rbp+70h+var_30]
0x18000ba51  xor     rcx, rsp; StackCookie
0x18000ba54  call    __security_check_cookie
0x18000ba59  mov     rbx, [rsp+170h+arg_10]
0x18000ba61  add     rsp, 150h
0x18000ba68  pop     r15
0x18000ba6a  pop     r14
0x18000ba6c  pop     rdi
0x18000ba6d  pop     rsi
0x18000ba6e  pop     rbp
0x18000ba6f  retn
```
