# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x14000ae78`
- end: `0x14000b05c`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140008f20`

## callees

- `0x140002ac0`
- `0x14000acbc`
- `0x14000ae14`
- `0x14000ae78`
- `0x14001aa60`
- `0x1400206e0`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000af98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000afb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000afda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b01c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000af98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000afb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000afda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b01c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000afa0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000afa0`

## string_xrefs

- `0x14000b002`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x14000ae78  mov     [rsp-8+arg_10], rbx
0x14000ae7d  push    rbp
0x14000ae7e  push    rsi
0x14000ae7f  push    rdi
0x14000ae80  push    r14
0x14000ae82  push    r15
0x14000ae84  lea     rbp, [rsp-50h]
0x14000ae89  sub     rsp, 150h
0x14000ae90  mov     rax, cs:__security_cookie
0x14000ae97  xor     rax, rsp
0x14000ae9a  mov     [rbp+70h+var_30], rax
0x14000ae9e  mov     rsi, rdx
0x14000aea1  mov     r15, rcx
0x14000aea4  mov     [rsp+170h+pv], 0; int
0x14000aead  xor     edx, edx; Val
0x14000aeaf  mov     r8d, 100h; Size
0x14000aeb5  lea     rcx, [rsp+170h+var_130]; void *
0x14000aeba  call    memset
0x14000aebf  mov     [rsp+170h+var_140], 0
0x14000aec8  lea     r9, [rsp+170h+var_140]
0x14000aecd  mov     edi, 80h
0x14000aed2  mov     r8d, edi
0x14000aed5  lea     rdx, [rsp+170h+var_130]
0x14000aeda  mov     rcx, rsi
0x14000aedd  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x14000aee2  mov     ebx, eax
0x14000aee4  test    eax, eax
0x14000aee6  jns     short loc_14000AF01
0x14000aee8  mov     rcx, [rsi+70h]
0x14000aeec  test    rcx, rcx
0x14000aeef  jz      loc_14000B037
0x14000aef5  mov     rdx, [rcx]
0x14000aef8  mov     rax, [rdx+18h]
0x14000aefc  jmp     loc_14000B032
0x14000af01  mov     rax, [rsp+170h+var_140]
0x14000af06  cmp     rax, rdi
0x14000af09  ja      short loc_14000AF35
0x14000af0b  lea     r8, [rax-1]
0x14000af0f  lea     rdx, [rsp+170h+var_130]
0x14000af14  lea     rcx, [rsp+170h+pv]
0x14000af19  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x14000af1e  mov     ebx, eax
0x14000af20  test    eax, eax
0x14000af22  jns     short loc_14000AF2E
0x14000af24  mov     edx, 15Fh
0x14000af29  jmp     loc_14000AFFF
0x14000af2e  mov     rbx, [rsp+170h+pv]
0x14000af33  jmp     short loc_14000AF7B
0x14000af35  mov     rdi, rax
0x14000af38  lea     r8, [rax-1]
0x14000af3c  xor     edx, edx
0x14000af3e  lea     rcx, [rsp+170h+pv]
0x14000af43  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x14000af48  mov     ebx, eax
0x14000af4a  test    eax, eax
0x14000af4c  js      loc_14000AFFA
0x14000af52  lea     r9, [rsp+170h+var_140]
0x14000af57  mov     r8, rdi
0x14000af5a  mov     rbx, [rsp+170h+pv]
0x14000af5f  mov     rdx, rbx
0x14000af62  mov     rcx, rsi
0x14000af65  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x14000af6a  mov     r14d, eax
0x14000af6d  test    eax, eax
0x14000af6f  js      short loc_14000AFD2
0x14000af71  mov     rax, [rsp+170h+var_140]
0x14000af76  cmp     rax, rdi
0x14000af79  ja      short loc_14000AF35
0x14000af7b  lea     rax, [rsp+170h+var_148]
0x14000af80  cmp     r15, rax
0x14000af83  jz      short loc_14000AFAB
0x14000af85  mov     r14, [r15]
0x14000af88  test    r14, r14
0x14000af8b  jz      short loc_14000AFA6
0x14000af8d  call    cs:__imp_GetLastError
0x14000af93  mov     edi, eax
0x14000af95  mov     rcx, r14; pv
0x14000af98  call    cs:__imp_CoTaskMemFree
0x14000af9e  mov     ecx, edi; dwErrCode
0x14000afa0  call    cs:__imp_SetLastError
0x14000afa6  mov     [r15], rbx
0x14000afa9  jmp     short loc_14000AFB9
0x14000afab  test    rbx, rbx
0x14000afae  jz      short loc_14000AFB9
0x14000afb0  mov     rcx, rbx; pv
0x14000afb3  call    cs:__imp_CoTaskMemFree
0x14000afb9  mov     rcx, [rsi+70h]
0x14000afbd  test    rcx, rcx
0x14000afc0  jz      short loc_14000AFCE
0x14000afc2  mov     rax, [rcx]
0x14000afc5  mov     rax, [rax+18h]
0x14000afc9  call    _guard_dispatch_icall
0x14000afce  xor     eax, eax
0x14000afd0  jmp     short loc_14000B039
0x14000afd2  test    rbx, rbx
0x14000afd5  jz      short loc_14000AFE0
0x14000afd7  mov     rcx, rbx; pv
0x14000afda  call    cs:__imp_CoTaskMemFree
0x14000afe0  mov     rcx, [rsi+70h]
0x14000afe4  test    rcx, rcx
0x14000afe7  jz      short loc_14000AFF5
0x14000afe9  mov     rax, [rcx]
0x14000afec  mov     rax, [rax+18h]
0x14000aff0  call    _guard_dispatch_icall
0x14000aff5  mov     eax, r14d
0x14000aff8  jmp     short loc_14000B039
0x14000affa  mov     edx, 16Ah; void *
0x14000afff  mov     r9d, ebx; char *
0x14000b002  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14000b009  mov     rcx, [rbp+78h]; this
0x14000b00d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b012  mov     rcx, [rsp+170h+pv]; pv
0x14000b017  test    rcx, rcx
0x14000b01a  jz      short loc_14000B022
0x14000b01c  call    cs:__imp_CoTaskMemFree
0x14000b022  mov     rcx, [rsi+70h]
0x14000b026  test    rcx, rcx
0x14000b029  jz      short loc_14000B037
0x14000b02b  mov     rax, [rcx]
0x14000b02e  mov     rax, [rax+18h]
0x14000b032  call    _guard_dispatch_icall
0x14000b037  mov     eax, ebx
0x14000b039  mov     rcx, [rbp+70h+var_30]
0x14000b03d  xor     rcx, rsp; StackCookie
0x14000b040  call    __security_check_cookie
0x14000b045  mov     rbx, [rsp+170h+arg_10]
0x14000b04d  add     rsp, 150h
0x14000b054  pop     r15
0x14000b056  pop     r14
0x14000b058  pop     rdi
0x14000b059  pop     rsi
0x14000b05a  pop     rbp
0x14000b05b  retn
```
