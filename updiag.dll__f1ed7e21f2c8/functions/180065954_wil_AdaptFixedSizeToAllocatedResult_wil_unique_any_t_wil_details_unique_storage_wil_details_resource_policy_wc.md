# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x180065954`
- end: `0x180065b44`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180065c40`

## callees

- `0x18000ad5c`
- `0x18006579c`
- `0x1800658f0`
- `0x180065954`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065a7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065abc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065b01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065a7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065abc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065b01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065a82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a6f`

## string_xrefs

- `0x180065ae4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x180065954  mov     [rsp-8+arg_10], rbx
0x180065959  push    rbp
0x18006595a  push    rsi
0x18006595b  push    rdi
0x18006595c  push    r14
0x18006595e  push    r15
0x180065960  lea     rbp, [rsp-150h]
0x180065968  sub     rsp, 250h
0x18006596f  mov     rax, cs:__security_cookie
0x180065976  xor     rax, rsp
0x180065979  mov     [rbp+170h+var_30], rax
0x180065980  mov     rsi, rdx
0x180065983  mov     r15, rcx
0x180065986  mov     [rsp+270h+pv], 0; int
0x18006598f  xor     edx, edx; Val
0x180065991  mov     r8d, 200h; Size
0x180065997  lea     rcx, [rsp+270h+var_230]; void *
0x18006599c  call    memset
0x1800659a1  mov     [rsp+270h+var_240], 0
0x1800659aa  lea     r9, [rsp+270h+var_240]
0x1800659af  mov     edi, 100h
0x1800659b4  mov     r8d, edi
0x1800659b7  lea     rdx, [rsp+270h+var_230]
0x1800659bc  mov     rcx, rsi
0x1800659bf  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x1800659c4  mov     ebx, eax
0x1800659c6  test    eax, eax
0x1800659c8  jns     short loc_1800659E3
0x1800659ca  mov     rcx, [rsi+70h]
0x1800659ce  test    rcx, rcx
0x1800659d1  jz      loc_180065B1C
0x1800659d7  mov     rdx, [rcx]
0x1800659da  mov     rax, [rdx+18h]
0x1800659de  jmp     loc_180065B17
0x1800659e3  mov     rax, [rsp+270h+var_240]
0x1800659e8  cmp     rax, rdi
0x1800659eb  ja      short loc_180065A17
0x1800659ed  lea     r8, [rax-1]
0x1800659f1  lea     rdx, [rsp+270h+var_230]
0x1800659f6  lea     rcx, [rsp+270h+pv]
0x1800659fb  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180065a00  mov     ebx, eax
0x180065a02  test    eax, eax
0x180065a04  jns     short loc_180065A10
0x180065a06  mov     edx, 15Fh
0x180065a0b  jmp     loc_180065AE1
0x180065a10  mov     rbx, [rsp+270h+pv]
0x180065a15  jmp     short loc_180065A5D
0x180065a17  mov     rdi, rax
0x180065a1a  lea     r8, [rax-1]
0x180065a1e  xor     edx, edx
0x180065a20  lea     rcx, [rsp+270h+pv]
0x180065a25  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180065a2a  mov     ebx, eax
0x180065a2c  test    eax, eax
0x180065a2e  js      loc_180065ADC
0x180065a34  lea     r9, [rsp+270h+var_240]
0x180065a39  mov     r8, rdi
0x180065a3c  mov     rbx, [rsp+270h+pv]
0x180065a41  mov     rdx, rbx
0x180065a44  mov     rcx, rsi
0x180065a47  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180065a4c  mov     r14d, eax
0x180065a4f  test    eax, eax
0x180065a51  js      short loc_180065AB4
0x180065a53  mov     rax, [rsp+270h+var_240]
0x180065a58  cmp     rax, rdi
0x180065a5b  ja      short loc_180065A17
0x180065a5d  lea     rax, [rsp+270h+var_248]
0x180065a62  cmp     r15, rax
0x180065a65  jz      short loc_180065A8D
0x180065a67  mov     r14, [r15]
0x180065a6a  test    r14, r14
0x180065a6d  jz      short loc_180065A88
0x180065a6f  call    cs:__imp_GetLastError
0x180065a75  mov     edi, eax
0x180065a77  mov     rcx, r14; pv
0x180065a7a  call    cs:__imp_CoTaskMemFree
0x180065a80  mov     ecx, edi; dwErrCode
0x180065a82  call    cs:__imp_SetLastError
0x180065a88  mov     [r15], rbx
0x180065a8b  jmp     short loc_180065A9B
0x180065a8d  test    rbx, rbx
0x180065a90  jz      short loc_180065A9B
0x180065a92  mov     rcx, rbx; pv
0x180065a95  call    cs:__imp_CoTaskMemFree
0x180065a9b  mov     rcx, [rsi+70h]
0x180065a9f  test    rcx, rcx
0x180065aa2  jz      short loc_180065AB0
0x180065aa4  mov     rax, [rcx]
0x180065aa7  mov     rax, [rax+18h]
0x180065aab  call    _guard_dispatch_icall
0x180065ab0  xor     eax, eax
0x180065ab2  jmp     short loc_180065B1E
0x180065ab4  test    rbx, rbx
0x180065ab7  jz      short loc_180065AC2
0x180065ab9  mov     rcx, rbx; pv
0x180065abc  call    cs:__imp_CoTaskMemFree
0x180065ac2  mov     rcx, [rsi+70h]
0x180065ac6  test    rcx, rcx
0x180065ac9  jz      short loc_180065AD7
0x180065acb  mov     rax, [rcx]
0x180065ace  mov     rax, [rax+18h]
0x180065ad2  call    _guard_dispatch_icall
0x180065ad7  mov     eax, r14d
0x180065ada  jmp     short loc_180065B1E
0x180065adc  mov     edx, 16Ah; void *
0x180065ae1  mov     r9d, ebx; char *
0x180065ae4  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180065aeb  mov     rcx, [rbp+178h]; this
0x180065af2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065af7  mov     rcx, [rsp+270h+pv]; pv
0x180065afc  test    rcx, rcx
0x180065aff  jz      short loc_180065B07
0x180065b01  call    cs:__imp_CoTaskMemFree
0x180065b07  mov     rcx, [rsi+70h]
0x180065b0b  test    rcx, rcx
0x180065b0e  jz      short loc_180065B1C
0x180065b10  mov     rax, [rcx]
0x180065b13  mov     rax, [rax+18h]
0x180065b17  call    _guard_dispatch_icall
0x180065b1c  mov     eax, ebx
0x180065b1e  mov     rcx, [rbp+170h+var_30]
0x180065b25  xor     rcx, rsp; StackCookie
0x180065b28  call    __security_check_cookie
0x180065b2d  mov     rbx, [rsp+270h+arg_10]
0x180065b35  add     rsp, 250h
0x180065b3c  pop     r15
0x180065b3e  pop     r14
0x180065b40  pop     rdi
0x180065b41  pop     rsi
0x180065b42  pop     rbp
0x180065b43  retn
```
