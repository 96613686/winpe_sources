# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x180037350`
- end: `0x180037534`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800367fc`

## callees

- `0x180003950`
- `0x180037350`
- `0x180037734`
- `0x180037940`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037465`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003748b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800374b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800374f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003748b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800374b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800374f4`

## string_xrefs

- `0x1800374da`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x180037350  mov     [rsp-8+arg_10], rbx
0x180037355  push    rbp
0x180037356  push    rsi
0x180037357  push    rdi
0x180037358  push    r14
0x18003735a  push    r15
0x18003735c  lea     rbp, [rsp-50h]
0x180037361  sub     rsp, 150h
0x180037368  mov     rax, cs:__security_cookie
0x18003736f  xor     rax, rsp
0x180037372  mov     [rbp+70h+var_30], rax
0x180037376  mov     rsi, rdx
0x180037379  mov     r15, rcx
0x18003737c  mov     [rsp+170h+pv], 0; int
0x180037385  xor     edx, edx; Val
0x180037387  mov     r8d, 100h; Size
0x18003738d  lea     rcx, [rsp+170h+var_130]; void *
0x180037392  call    memset
0x180037397  mov     [rsp+170h+var_140], 0
0x1800373a0  lea     r9, [rsp+170h+var_140]
0x1800373a5  mov     edi, 80h
0x1800373aa  mov     r8d, edi
0x1800373ad  lea     rdx, [rsp+170h+var_130]
0x1800373b2  mov     rcx, rsi
0x1800373b5  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x1800373ba  mov     ebx, eax
0x1800373bc  test    eax, eax
0x1800373be  jns     short loc_1800373D9
0x1800373c0  mov     rcx, [rsi+70h]
0x1800373c4  test    rcx, rcx
0x1800373c7  jz      loc_18003750F
0x1800373cd  mov     rdx, [rcx]
0x1800373d0  mov     rax, [rdx+18h]
0x1800373d4  jmp     loc_18003750A
0x1800373d9  mov     rax, [rsp+170h+var_140]
0x1800373de  cmp     rax, rdi
0x1800373e1  ja      short loc_18003740D
0x1800373e3  lea     r8, [rax-1]
0x1800373e7  lea     rdx, [rsp+170h+var_130]
0x1800373ec  lea     rcx, [rsp+170h+pv]
0x1800373f1  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x1800373f6  mov     ebx, eax
0x1800373f8  test    eax, eax
0x1800373fa  jns     short loc_180037406
0x1800373fc  mov     edx, 15Fh
0x180037401  jmp     loc_1800374D7
0x180037406  mov     rbx, [rsp+170h+pv]
0x18003740b  jmp     short loc_180037453
0x18003740d  mov     rdi, rax
0x180037410  lea     r8, [rax-1]
0x180037414  xor     edx, edx
0x180037416  lea     rcx, [rsp+170h+pv]
0x18003741b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180037420  mov     ebx, eax
0x180037422  test    eax, eax
0x180037424  js      loc_1800374D2
0x18003742a  lea     r9, [rsp+170h+var_140]
0x18003742f  mov     r8, rdi
0x180037432  mov     rbx, [rsp+170h+pv]
0x180037437  mov     rdx, rbx
0x18003743a  mov     rcx, rsi
0x18003743d  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180037442  mov     r14d, eax
0x180037445  test    eax, eax
0x180037447  js      short loc_1800374AA
0x180037449  mov     rax, [rsp+170h+var_140]
0x18003744e  cmp     rax, rdi
0x180037451  ja      short loc_18003740D
0x180037453  lea     rax, [rsp+170h+var_148]
0x180037458  cmp     r15, rax
0x18003745b  jz      short loc_180037483
0x18003745d  mov     r14, [r15]
0x180037460  test    r14, r14
0x180037463  jz      short loc_18003747E
0x180037465  call    cs:__imp_GetLastError
0x18003746b  mov     edi, eax
0x18003746d  mov     rcx, r14; pv
0x180037470  call    cs:__imp_CoTaskMemFree
0x180037476  mov     ecx, edi; dwErrCode
0x180037478  call    cs:__imp_SetLastError
0x18003747e  mov     [r15], rbx
0x180037481  jmp     short loc_180037491
0x180037483  test    rbx, rbx
0x180037486  jz      short loc_180037491
0x180037488  mov     rcx, rbx; pv
0x18003748b  call    cs:__imp_CoTaskMemFree
0x180037491  mov     rcx, [rsi+70h]
0x180037495  test    rcx, rcx
0x180037498  jz      short loc_1800374A6
0x18003749a  mov     rax, [rcx]
0x18003749d  mov     rax, [rax+18h]
0x1800374a1  call    _guard_dispatch_icall
0x1800374a6  xor     eax, eax
0x1800374a8  jmp     short loc_180037511
0x1800374aa  test    rbx, rbx
0x1800374ad  jz      short loc_1800374B8
0x1800374af  mov     rcx, rbx; pv
0x1800374b2  call    cs:__imp_CoTaskMemFree
0x1800374b8  mov     rcx, [rsi+70h]
0x1800374bc  test    rcx, rcx
0x1800374bf  jz      short loc_1800374CD
0x1800374c1  mov     rax, [rcx]
0x1800374c4  mov     rax, [rax+18h]
0x1800374c8  call    _guard_dispatch_icall
0x1800374cd  mov     eax, r14d
0x1800374d0  jmp     short loc_180037511
0x1800374d2  mov     edx, 16Ah; void *
0x1800374d7  mov     r9d, ebx; char *
0x1800374da  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800374e1  mov     rcx, [rbp+78h]; this
0x1800374e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800374ea  mov     rcx, [rsp+170h+pv]; pv
0x1800374ef  test    rcx, rcx
0x1800374f2  jz      short loc_1800374FA
0x1800374f4  call    cs:__imp_CoTaskMemFree
0x1800374fa  mov     rcx, [rsi+70h]
0x1800374fe  test    rcx, rcx
0x180037501  jz      short loc_18003750F
0x180037503  mov     rax, [rcx]
0x180037506  mov     rax, [rax+18h]
0x18003750a  call    _guard_dispatch_icall
0x18003750f  mov     eax, ebx
0x180037511  mov     rcx, [rbp+70h+var_30]
0x180037515  xor     rcx, rsp; StackCookie
0x180037518  call    __security_check_cookie
0x18003751d  mov     rbx, [rsp+170h+arg_10]
0x180037525  add     rsp, 150h
0x18003752c  pop     r15
0x18003752e  pop     r14
0x180037530  pop     rdi
0x180037531  pop     rsi
0x180037532  pop     rbp
0x180037533  retn
```
