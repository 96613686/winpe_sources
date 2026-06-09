# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x18003825c`
- end: `0x180038433`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036f98`
- `0x180065fd0`

## callees

- `0x180008e64`
- `0x180010768`
- `0x18002feb0`
- `0x18002ff28`
- `0x18003825c`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800383ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800383f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800383ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800383f0`

## string_xrefs

- `0x1800383d3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  void *v8; // rbx
  unsigned __int64 v9; // rsi
  int v10; // r14d
  __int64 v11; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v17[512]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  pv = 0;
  memset(v17, 0, sizeof(v17));
  v16 = 0;
  v4 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v17, 256, &v16);
  if ( v4 < 0 )
  {
    v5 = *(_QWORD *)(a2 + 112);
    if ( v5 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 24LL))(*(_QWORD *)(a2 + 112));
    return (unsigned int)v4;
  }
  v6 = v16;
  if ( v16 > 0x100 )
  {
    while ( 1 )
    {
      v9 = v6;
      v4 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
             &pv,
             0,
             v6 - 1);
      if ( v4 < 0 )
      {
        v7 = 362;
        goto LABEL_22;
      }
      v8 = pv;
      v10 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, pv, v9, &v16);
      if ( v10 < 0 )
        break;
      v6 = v16;
      if ( v16 <= v9 )
        goto LABEL_11;
    }
    if ( v8 )
      CoTaskMemFree(v8);
    v13 = *(_QWORD *)(a2 + 112);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
    return (unsigned int)v10;
  }
  else
  {
    v4 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
           &pv,
           v17,
           v16 - 1);
    if ( v4 < 0 )
    {
      v7 = 351;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v4,
        (int)pv);
      if ( pv )
        CoTaskMemFree(pv);
      v14 = *(_QWORD *)(a2 + 112);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
      return (unsigned int)v4;
    }
    v8 = pv;
LABEL_11:
    pv = v8;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      a1,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    v11 = *(_QWORD *)(a2 + 112);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
    return 0;
  }
}

```

## disassembly

```asm
0x18003825c  mov     [rsp-8+arg_10], rbx
0x180038261  push    rbp
0x180038262  push    rsi
0x180038263  push    rdi
0x180038264  push    r14
0x180038266  push    r15
0x180038268  lea     rbp, [rsp-140h]
0x180038270  sub     rsp, 240h
0x180038277  mov     rax, cs:__security_cookie
0x18003827e  xor     rax, rsp
0x180038281  mov     [rbp+160h+var_30], rax
0x180038288  mov     rdi, rdx
0x18003828b  mov     r15, rcx
0x18003828e  mov     [rsp+260h+pv], 0; int
0x180038297  xor     edx, edx; Val
0x180038299  mov     r8d, 200h; Size
0x18003829f  lea     rcx, [rsp+260h+var_230]; void *
0x1800382a4  call    memset
0x1800382a9  mov     [rsp+260h+var_238], 0
0x1800382b2  lea     r9, [rsp+260h+var_238]
0x1800382b7  mov     esi, 100h
0x1800382bc  mov     r8d, esi
0x1800382bf  lea     rdx, [rsp+260h+var_230]
0x1800382c4  mov     rcx, rdi
0x1800382c7  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x1800382cc  mov     ebx, eax
0x1800382ce  test    eax, eax
0x1800382d0  jns     short loc_1800382EE
0x1800382d2  mov     rdx, [rdi+70h]
0x1800382d6  test    rdx, rdx
0x1800382d9  jz      loc_18003840B
0x1800382df  mov     rcx, [rdx]
0x1800382e2  mov     rax, [rcx+18h]
0x1800382e6  mov     rcx, rdx
0x1800382e9  jmp     loc_180038406
0x1800382ee  mov     rax, [rsp+260h+var_238]
0x1800382f3  cmp     rax, rsi
0x1800382f6  ja      short loc_180038322
0x1800382f8  lea     r8, [rax-1]
0x1800382fc  lea     rdx, [rsp+260h+var_230]
0x180038301  lea     rcx, [rsp+260h+pv]
0x180038306  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18003830b  mov     ebx, eax
0x18003830d  test    eax, eax
0x18003830f  jns     short loc_18003831B
0x180038311  mov     edx, 15Fh
0x180038316  jmp     loc_1800383D0
0x18003831b  mov     rbx, [rsp+260h+pv]
0x180038320  jmp     short loc_180038368
0x180038322  mov     rsi, rax
0x180038325  lea     r8, [rax-1]
0x180038329  xor     edx, edx
0x18003832b  lea     rcx, [rsp+260h+pv]
0x180038330  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180038335  mov     ebx, eax
0x180038337  test    eax, eax
0x180038339  js      loc_1800383CB
0x18003833f  lea     r9, [rsp+260h+var_238]
0x180038344  mov     r8, rsi
0x180038347  mov     rbx, [rsp+260h+pv]
0x18003834c  mov     rdx, rbx
0x18003834f  mov     rcx, rdi
0x180038352  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180038357  mov     r14d, eax
0x18003835a  test    eax, eax
0x18003835c  js      short loc_1800383A3
0x18003835e  mov     rax, [rsp+260h+var_238]
0x180038363  cmp     rax, rsi
0x180038366  ja      short loc_180038322
0x180038368  mov     [rsp+260h+pv], rbx
0x18003836d  lea     rdx, [rsp+260h+pv]
0x180038372  mov     rcx, r15
0x180038375  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18003837a  mov     rcx, [rsp+260h+pv]; pv
0x18003837f  test    rcx, rcx
0x180038382  jz      short loc_18003838A
0x180038384  call    cs:__imp_CoTaskMemFree
0x18003838a  mov     rcx, [rdi+70h]
0x18003838e  test    rcx, rcx
0x180038391  jz      short loc_18003839F
0x180038393  mov     rax, [rcx]
0x180038396  mov     rax, [rax+18h]
0x18003839a  call    _guard_dispatch_icall
0x18003839f  xor     eax, eax
0x1800383a1  jmp     short loc_18003840D
0x1800383a3  test    rbx, rbx
0x1800383a6  jz      short loc_1800383B1
0x1800383a8  mov     rcx, rbx; pv
0x1800383ab  call    cs:__imp_CoTaskMemFree
0x1800383b1  mov     rcx, [rdi+70h]
0x1800383b5  test    rcx, rcx
0x1800383b8  jz      short loc_1800383C6
0x1800383ba  mov     rax, [rcx]
0x1800383bd  mov     rax, [rax+18h]
0x1800383c1  call    _guard_dispatch_icall
0x1800383c6  mov     eax, r14d
0x1800383c9  jmp     short loc_18003840D
0x1800383cb  mov     edx, 16Ah; void *
0x1800383d0  mov     r9d, ebx; char *
0x1800383d3  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800383da  mov     rcx, [rbp+168h]; this
0x1800383e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800383e6  mov     rcx, [rsp+260h+pv]; pv
0x1800383eb  test    rcx, rcx
0x1800383ee  jz      short loc_1800383F6
0x1800383f0  call    cs:__imp_CoTaskMemFree
0x1800383f6  mov     rcx, [rdi+70h]
0x1800383fa  test    rcx, rcx
0x1800383fd  jz      short loc_18003840B
0x1800383ff  mov     rax, [rcx]
0x180038402  mov     rax, [rax+18h]
0x180038406  call    _guard_dispatch_icall
0x18003840b  mov     eax, ebx
0x18003840d  mov     rcx, [rbp+160h+var_30]
0x180038414  xor     rcx, rsp; StackCookie
0x180038417  call    __security_check_cookie
0x18003841c  mov     rbx, [rsp+260h+arg_10]
0x180038424  add     rsp, 240h
0x18003842b  pop     r15
0x18003842d  pop     r14
0x18003842f  pop     rdi
0x180038430  pop     rsi
0x180038431  pop     rbp
0x180038432  retn
```
