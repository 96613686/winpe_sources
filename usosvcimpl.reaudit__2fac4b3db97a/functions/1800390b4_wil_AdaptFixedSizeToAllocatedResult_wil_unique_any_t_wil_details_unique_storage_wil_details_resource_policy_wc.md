# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x1800390b4`
- end: `0x18003927f`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036ee4`

## callees

- `0x180008e64`
- `0x180010768`
- `0x18002feb0`
- `0x18002ff28`
- `0x1800390b4`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003923f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800391fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003923f`

## string_xrefs

- `0x180039225`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
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
  _BYTE v17[256]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  pv = 0;
  memset(v17, 0, sizeof(v17));
  v16 = 0;
  v4 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v17, 128, &v16);
  if ( v4 < 0 )
  {
    v5 = *(_QWORD *)(a2 + 112);
    if ( v5 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 24LL))(*(_QWORD *)(a2 + 112));
    return (unsigned int)v4;
  }
  v6 = v16;
  if ( v16 > 0x80 )
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
0x1800390b4  mov     [rsp-8+arg_10], rbx
0x1800390b9  push    rbp
0x1800390ba  push    rsi
0x1800390bb  push    rdi
0x1800390bc  push    r14
0x1800390be  push    r15
0x1800390c0  lea     rbp, [rsp-40h]
0x1800390c5  sub     rsp, 140h
0x1800390cc  mov     rax, cs:__security_cookie
0x1800390d3  xor     rax, rsp
0x1800390d6  mov     [rbp+60h+var_30], rax
0x1800390da  mov     rdi, rdx
0x1800390dd  mov     r15, rcx
0x1800390e0  mov     [rsp+160h+pv], 0; int
0x1800390e9  xor     edx, edx; Val
0x1800390eb  mov     r8d, 100h; Size
0x1800390f1  lea     rcx, [rsp+160h+var_130]; void *
0x1800390f6  call    memset
0x1800390fb  mov     [rsp+160h+var_138], 0
0x180039104  lea     r9, [rsp+160h+var_138]
0x180039109  mov     esi, 80h
0x18003910e  mov     r8d, esi
0x180039111  lea     rdx, [rsp+160h+var_130]
0x180039116  mov     rcx, rdi
0x180039119  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18003911e  mov     ebx, eax
0x180039120  test    eax, eax
0x180039122  jns     short loc_180039140
0x180039124  mov     rdx, [rdi+70h]
0x180039128  test    rdx, rdx
0x18003912b  jz      loc_18003925A
0x180039131  mov     rcx, [rdx]
0x180039134  mov     rax, [rcx+18h]
0x180039138  mov     rcx, rdx
0x18003913b  jmp     loc_180039255
0x180039140  mov     rax, [rsp+160h+var_138]
0x180039145  cmp     rax, rsi
0x180039148  ja      short loc_180039174
0x18003914a  lea     r8, [rax-1]
0x18003914e  lea     rdx, [rsp+160h+var_130]
0x180039153  lea     rcx, [rsp+160h+pv]
0x180039158  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18003915d  mov     ebx, eax
0x18003915f  test    eax, eax
0x180039161  jns     short loc_18003916D
0x180039163  mov     edx, 15Fh
0x180039168  jmp     loc_180039222
0x18003916d  mov     rbx, [rsp+160h+pv]
0x180039172  jmp     short loc_1800391BA
0x180039174  mov     rsi, rax
0x180039177  lea     r8, [rax-1]
0x18003917b  xor     edx, edx
0x18003917d  lea     rcx, [rsp+160h+pv]
0x180039182  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180039187  mov     ebx, eax
0x180039189  test    eax, eax
0x18003918b  js      loc_18003921D
0x180039191  lea     r9, [rsp+160h+var_138]
0x180039196  mov     r8, rsi
0x180039199  mov     rbx, [rsp+160h+pv]
0x18003919e  mov     rdx, rbx
0x1800391a1  mov     rcx, rdi
0x1800391a4  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x1800391a9  mov     r14d, eax
0x1800391ac  test    eax, eax
0x1800391ae  js      short loc_1800391F5
0x1800391b0  mov     rax, [rsp+160h+var_138]
0x1800391b5  cmp     rax, rsi
0x1800391b8  ja      short loc_180039174
0x1800391ba  mov     [rsp+160h+pv], rbx
0x1800391bf  lea     rdx, [rsp+160h+pv]
0x1800391c4  mov     rcx, r15
0x1800391c7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x1800391cc  mov     rcx, [rsp+160h+pv]; pv
0x1800391d1  test    rcx, rcx
0x1800391d4  jz      short loc_1800391DC
0x1800391d6  call    cs:__imp_CoTaskMemFree
0x1800391dc  mov     rcx, [rdi+70h]
0x1800391e0  test    rcx, rcx
0x1800391e3  jz      short loc_1800391F1
0x1800391e5  mov     rax, [rcx]
0x1800391e8  mov     rax, [rax+18h]
0x1800391ec  call    _guard_dispatch_icall
0x1800391f1  xor     eax, eax
0x1800391f3  jmp     short loc_18003925C
0x1800391f5  test    rbx, rbx
0x1800391f8  jz      short loc_180039203
0x1800391fa  mov     rcx, rbx; pv
0x1800391fd  call    cs:__imp_CoTaskMemFree
0x180039203  mov     rcx, [rdi+70h]
0x180039207  test    rcx, rcx
0x18003920a  jz      short loc_180039218
0x18003920c  mov     rax, [rcx]
0x18003920f  mov     rax, [rax+18h]
0x180039213  call    _guard_dispatch_icall
0x180039218  mov     eax, r14d
0x18003921b  jmp     short loc_18003925C
0x18003921d  mov     edx, 16Ah; void *
0x180039222  mov     r9d, ebx; char *
0x180039225  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18003922c  mov     rcx, [rbp+68h]; this
0x180039230  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039235  mov     rcx, [rsp+160h+pv]; pv
0x18003923a  test    rcx, rcx
0x18003923d  jz      short loc_180039245
0x18003923f  call    cs:__imp_CoTaskMemFree
0x180039245  mov     rcx, [rdi+70h]
0x180039249  test    rcx, rcx
0x18003924c  jz      short loc_18003925A
0x18003924e  mov     rax, [rcx]
0x180039251  mov     rax, [rax+18h]
0x180039255  call    _guard_dispatch_icall
0x18003925a  mov     eax, ebx
0x18003925c  mov     rcx, [rbp+60h+var_30]
0x180039260  xor     rcx, rsp; StackCookie
0x180039263  call    __security_check_cookie
0x180039268  mov     rbx, [rsp+160h+arg_10]
0x180039270  add     rsp, 140h
0x180039277  pop     r15
0x180039279  pop     r14
0x18003927b  pop     rdi
0x18003927c  pop     rsi
0x18003927d  pop     rbp
0x18003927e  retn
```
