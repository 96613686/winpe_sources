# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x18003753c`
- end: `0x18003772c`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800368b0`

## callees

- `0x180003950`
- `0x18003753c`
- `0x180037734`
- `0x180037940`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003766a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003766a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003767d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003767d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800376e9`

## string_xrefs

- `0x1800376cc`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
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
  _BYTE v21[512]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  pv = 0;
  memset(v21, 0, sizeof(v21));
  v20[0] = 0;
  v4 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v21, 256, v20);
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
  if ( v20[0] > 0x100u )
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
0x18003753c  mov     [rsp-8+arg_10], rbx
0x180037541  push    rbp
0x180037542  push    rsi
0x180037543  push    rdi
0x180037544  push    r14
0x180037546  push    r15
0x180037548  lea     rbp, [rsp-150h]
0x180037550  sub     rsp, 250h
0x180037557  mov     rax, cs:__security_cookie
0x18003755e  xor     rax, rsp
0x180037561  mov     [rbp+170h+var_30], rax
0x180037568  mov     rsi, rdx
0x18003756b  mov     r15, rcx
0x18003756e  mov     [rsp+270h+pv], 0; int
0x180037577  xor     edx, edx; Val
0x180037579  mov     r8d, 200h; Size
0x18003757f  lea     rcx, [rsp+270h+var_230]; void *
0x180037584  call    memset
0x180037589  mov     [rsp+270h+var_240], 0
0x180037592  lea     r9, [rsp+270h+var_240]
0x180037597  mov     edi, 100h
0x18003759c  mov     r8d, edi
0x18003759f  lea     rdx, [rsp+270h+var_230]
0x1800375a4  mov     rcx, rsi
0x1800375a7  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x1800375ac  mov     ebx, eax
0x1800375ae  test    eax, eax
0x1800375b0  jns     short loc_1800375CB
0x1800375b2  mov     rcx, [rsi+70h]
0x1800375b6  test    rcx, rcx
0x1800375b9  jz      loc_180037704
0x1800375bf  mov     rdx, [rcx]
0x1800375c2  mov     rax, [rdx+18h]
0x1800375c6  jmp     loc_1800376FF
0x1800375cb  mov     rax, [rsp+270h+var_240]
0x1800375d0  cmp     rax, rdi
0x1800375d3  ja      short loc_1800375FF
0x1800375d5  lea     r8, [rax-1]
0x1800375d9  lea     rdx, [rsp+270h+var_230]
0x1800375de  lea     rcx, [rsp+270h+pv]
0x1800375e3  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x1800375e8  mov     ebx, eax
0x1800375ea  test    eax, eax
0x1800375ec  jns     short loc_1800375F8
0x1800375ee  mov     edx, 15Fh
0x1800375f3  jmp     loc_1800376C9
0x1800375f8  mov     rbx, [rsp+270h+pv]
0x1800375fd  jmp     short loc_180037645
0x1800375ff  mov     rdi, rax
0x180037602  lea     r8, [rax-1]
0x180037606  xor     edx, edx
0x180037608  lea     rcx, [rsp+270h+pv]
0x18003760d  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180037612  mov     ebx, eax
0x180037614  test    eax, eax
0x180037616  js      loc_1800376C4
0x18003761c  lea     r9, [rsp+270h+var_240]
0x180037621  mov     r8, rdi
0x180037624  mov     rbx, [rsp+270h+pv]
0x180037629  mov     rdx, rbx
0x18003762c  mov     rcx, rsi
0x18003762f  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180037634  mov     r14d, eax
0x180037637  test    eax, eax
0x180037639  js      short loc_18003769C
0x18003763b  mov     rax, [rsp+270h+var_240]
0x180037640  cmp     rax, rdi
0x180037643  ja      short loc_1800375FF
0x180037645  lea     rax, [rsp+270h+var_248]
0x18003764a  cmp     r15, rax
0x18003764d  jz      short loc_180037675
0x18003764f  mov     r14, [r15]
0x180037652  test    r14, r14
0x180037655  jz      short loc_180037670
0x180037657  call    cs:__imp_GetLastError
0x18003765d  mov     edi, eax
0x18003765f  mov     rcx, r14; pv
0x180037662  call    cs:__imp_CoTaskMemFree
0x180037668  mov     ecx, edi; dwErrCode
0x18003766a  call    cs:__imp_SetLastError
0x180037670  mov     [r15], rbx
0x180037673  jmp     short loc_180037683
0x180037675  test    rbx, rbx
0x180037678  jz      short loc_180037683
0x18003767a  mov     rcx, rbx; pv
0x18003767d  call    cs:__imp_CoTaskMemFree
0x180037683  mov     rcx, [rsi+70h]
0x180037687  test    rcx, rcx
0x18003768a  jz      short loc_180037698
0x18003768c  mov     rax, [rcx]
0x18003768f  mov     rax, [rax+18h]
0x180037693  call    _guard_dispatch_icall
0x180037698  xor     eax, eax
0x18003769a  jmp     short loc_180037706
0x18003769c  test    rbx, rbx
0x18003769f  jz      short loc_1800376AA
0x1800376a1  mov     rcx, rbx; pv
0x1800376a4  call    cs:__imp_CoTaskMemFree
0x1800376aa  mov     rcx, [rsi+70h]
0x1800376ae  test    rcx, rcx
0x1800376b1  jz      short loc_1800376BF
0x1800376b3  mov     rax, [rcx]
0x1800376b6  mov     rax, [rax+18h]
0x1800376ba  call    _guard_dispatch_icall
0x1800376bf  mov     eax, r14d
0x1800376c2  jmp     short loc_180037706
0x1800376c4  mov     edx, 16Ah; void *
0x1800376c9  mov     r9d, ebx; char *
0x1800376cc  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800376d3  mov     rcx, [rbp+178h]; this
0x1800376da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800376df  mov     rcx, [rsp+270h+pv]; pv
0x1800376e4  test    rcx, rcx
0x1800376e7  jz      short loc_1800376EF
0x1800376e9  call    cs:__imp_CoTaskMemFree
0x1800376ef  mov     rcx, [rsi+70h]
0x1800376f3  test    rcx, rcx
0x1800376f6  jz      short loc_180037704
0x1800376f8  mov     rax, [rcx]
0x1800376fb  mov     rax, [rax+18h]
0x1800376ff  call    _guard_dispatch_icall
0x180037704  mov     eax, ebx
0x180037706  mov     rcx, [rbp+170h+var_30]
0x18003770d  xor     rcx, rsp; StackCookie
0x180037710  call    __security_check_cookie
0x180037715  mov     rbx, [rsp+270h+arg_10]
0x18003771d  add     rsp, 250h
0x180037724  pop     r15
0x180037726  pop     r14
0x180037728  pop     rdi
0x180037729  pop     rsi
0x18003772a  pop     rbp
0x18003772b  retn
```
