# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x180018f44`
- end: `0x180019134`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d660`

## callees

- `0x180006400`
- `0x180018f44`
- `0x180024dac`
- `0x180024f00`
- `0x1800427d0`
- `0x180047a30`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001905f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001905f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019072`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019072`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001906a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800190ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800190f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001906a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800190ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800190f1`

## string_xrefs

- `0x1800190d4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x180018f44  mov     [rsp-8+arg_10], rbx
0x180018f49  push    rbp
0x180018f4a  push    rsi
0x180018f4b  push    rdi
0x180018f4c  push    r14
0x180018f4e  push    r15
0x180018f50  lea     rbp, [rsp-150h]
0x180018f58  sub     rsp, 250h
0x180018f5f  mov     rax, cs:__security_cookie
0x180018f66  xor     rax, rsp
0x180018f69  mov     [rbp+170h+var_30], rax
0x180018f70  mov     rsi, rdx
0x180018f73  mov     r15, rcx
0x180018f76  mov     [rsp+270h+pv], 0; int
0x180018f7f  xor     edx, edx; Val
0x180018f81  mov     r8d, 200h; Size
0x180018f87  lea     rcx, [rsp+270h+var_230]; void *
0x180018f8c  call    memset
0x180018f91  mov     [rsp+270h+var_240], 0
0x180018f9a  lea     r9, [rsp+270h+var_240]
0x180018f9f  mov     edi, 100h
0x180018fa4  mov     r8d, edi
0x180018fa7  lea     rdx, [rsp+270h+var_230]
0x180018fac  mov     rcx, rsi
0x180018faf  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180018fb4  mov     ebx, eax
0x180018fb6  test    eax, eax
0x180018fb8  jns     short loc_180018FD3
0x180018fba  mov     rcx, [rsi+70h]
0x180018fbe  test    rcx, rcx
0x180018fc1  jz      loc_18001910C
0x180018fc7  mov     rdx, [rcx]
0x180018fca  mov     rax, [rdx+18h]
0x180018fce  jmp     loc_180019107
0x180018fd3  mov     rax, [rsp+270h+var_240]
0x180018fd8  cmp     rax, rdi
0x180018fdb  ja      short loc_180019007
0x180018fdd  lea     r8, [rax-1]
0x180018fe1  lea     rdx, [rsp+270h+var_230]
0x180018fe6  lea     rcx, [rsp+270h+pv]
0x180018feb  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180018ff0  mov     ebx, eax
0x180018ff2  test    eax, eax
0x180018ff4  jns     short loc_180019000
0x180018ff6  mov     edx, 15Fh
0x180018ffb  jmp     loc_1800190D1
0x180019000  mov     rbx, [rsp+270h+pv]
0x180019005  jmp     short loc_18001904D
0x180019007  mov     rdi, rax
0x18001900a  lea     r8, [rax-1]
0x18001900e  xor     edx, edx
0x180019010  lea     rcx, [rsp+270h+pv]
0x180019015  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18001901a  mov     ebx, eax
0x18001901c  test    eax, eax
0x18001901e  js      loc_1800190CC
0x180019024  lea     r9, [rsp+270h+var_240]
0x180019029  mov     r8, rdi
0x18001902c  mov     rbx, [rsp+270h+pv]
0x180019031  mov     rdx, rbx
0x180019034  mov     rcx, rsi
0x180019037  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18001903c  mov     r14d, eax
0x18001903f  test    eax, eax
0x180019041  js      short loc_1800190A4
0x180019043  mov     rax, [rsp+270h+var_240]
0x180019048  cmp     rax, rdi
0x18001904b  ja      short loc_180019007
0x18001904d  lea     rax, [rsp+270h+var_248]
0x180019052  cmp     r15, rax
0x180019055  jz      short loc_18001907D
0x180019057  mov     r14, [r15]
0x18001905a  test    r14, r14
0x18001905d  jz      short loc_180019078
0x18001905f  call    cs:__imp_GetLastError
0x180019065  mov     edi, eax
0x180019067  mov     rcx, r14; pv
0x18001906a  call    cs:__imp_CoTaskMemFree
0x180019070  mov     ecx, edi; dwErrCode
0x180019072  call    cs:__imp_SetLastError
0x180019078  mov     [r15], rbx
0x18001907b  jmp     short loc_18001908B
0x18001907d  test    rbx, rbx
0x180019080  jz      short loc_18001908B
0x180019082  mov     rcx, rbx; pv
0x180019085  call    cs:__imp_CoTaskMemFree
0x18001908b  mov     rcx, [rsi+70h]
0x18001908f  test    rcx, rcx
0x180019092  jz      short loc_1800190A0
0x180019094  mov     rax, [rcx]
0x180019097  mov     rax, [rax+18h]
0x18001909b  call    _guard_dispatch_icall
0x1800190a0  xor     eax, eax
0x1800190a2  jmp     short loc_18001910E
0x1800190a4  test    rbx, rbx
0x1800190a7  jz      short loc_1800190B2
0x1800190a9  mov     rcx, rbx; pv
0x1800190ac  call    cs:__imp_CoTaskMemFree
0x1800190b2  mov     rcx, [rsi+70h]
0x1800190b6  test    rcx, rcx
0x1800190b9  jz      short loc_1800190C7
0x1800190bb  mov     rax, [rcx]
0x1800190be  mov     rax, [rax+18h]
0x1800190c2  call    _guard_dispatch_icall
0x1800190c7  mov     eax, r14d
0x1800190ca  jmp     short loc_18001910E
0x1800190cc  mov     edx, 16Ah; void *
0x1800190d1  mov     r9d, ebx; char *
0x1800190d4  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800190db  mov     rcx, [rbp+178h]; this
0x1800190e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800190e7  mov     rcx, [rsp+270h+pv]; pv
0x1800190ec  test    rcx, rcx
0x1800190ef  jz      short loc_1800190F7
0x1800190f1  call    cs:__imp_CoTaskMemFree
0x1800190f7  mov     rcx, [rsi+70h]
0x1800190fb  test    rcx, rcx
0x1800190fe  jz      short loc_18001910C
0x180019100  mov     rax, [rcx]
0x180019103  mov     rax, [rax+18h]
0x180019107  call    _guard_dispatch_icall
0x18001910c  mov     eax, ebx
0x18001910e  mov     rcx, [rbp+170h+var_30]
0x180019115  xor     rcx, rsp; StackCookie
0x180019118  call    __security_check_cookie
0x18001911d  mov     rbx, [rsp+270h+arg_10]
0x180019125  add     rsp, 250h
0x18001912c  pop     r15
0x18001912e  pop     r14
0x180019130  pop     rdi
0x180019131  pop     rsi
0x180019132  pop     rbp
0x180019133  retn
```
