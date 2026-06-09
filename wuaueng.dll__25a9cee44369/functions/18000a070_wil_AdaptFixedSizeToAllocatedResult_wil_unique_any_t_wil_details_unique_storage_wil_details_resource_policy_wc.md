# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x18000a070`
- end: `0x18000a260`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a360`

## callees

- `0x180003760`
- `0x180009eb8`
- `0x18000a00c`
- `0x18000a070`
- `0x18000fc90`
- `0x1800159b0`
- `0x180015a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a19e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a19e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a18b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a21d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a21d`

## string_xrefs

- `0x18000a200`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x18000a070  mov     [rsp-8+arg_10], rbx
0x18000a075  push    rbp
0x18000a076  push    rsi
0x18000a077  push    rdi
0x18000a078  push    r14
0x18000a07a  push    r15
0x18000a07c  lea     rbp, [rsp-150h]
0x18000a084  sub     rsp, 250h
0x18000a08b  mov     rax, cs:__security_cookie
0x18000a092  xor     rax, rsp
0x18000a095  mov     [rbp+170h+var_30], rax
0x18000a09c  mov     rsi, rdx
0x18000a09f  mov     r15, rcx
0x18000a0a2  mov     [rsp+270h+pv], 0; int
0x18000a0ab  xor     edx, edx; Val
0x18000a0ad  mov     r8d, 200h; Size
0x18000a0b3  lea     rcx, [rsp+270h+var_230]; void *
0x18000a0b8  call    memset
0x18000a0bd  mov     [rsp+270h+var_240], 0
0x18000a0c6  lea     r9, [rsp+270h+var_240]
0x18000a0cb  mov     edi, 100h
0x18000a0d0  mov     r8d, edi
0x18000a0d3  lea     rdx, [rsp+270h+var_230]
0x18000a0d8  mov     rcx, rsi
0x18000a0db  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18000a0e0  mov     ebx, eax
0x18000a0e2  test    eax, eax
0x18000a0e4  jns     short loc_18000A0FF
0x18000a0e6  mov     rcx, [rsi+70h]
0x18000a0ea  test    rcx, rcx
0x18000a0ed  jz      loc_18000A238
0x18000a0f3  mov     rdx, [rcx]
0x18000a0f6  mov     rax, [rdx+18h]
0x18000a0fa  jmp     loc_18000A233
0x18000a0ff  mov     rax, [rsp+270h+var_240]
0x18000a104  cmp     rax, rdi
0x18000a107  ja      short loc_18000A133
0x18000a109  lea     r8, [rax-1]
0x18000a10d  lea     rdx, [rsp+270h+var_230]
0x18000a112  lea     rcx, [rsp+270h+pv]
0x18000a117  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18000a11c  mov     ebx, eax
0x18000a11e  test    eax, eax
0x18000a120  jns     short loc_18000A12C
0x18000a122  mov     edx, 15Fh
0x18000a127  jmp     loc_18000A1FD
0x18000a12c  mov     rbx, [rsp+270h+pv]
0x18000a131  jmp     short loc_18000A179
0x18000a133  mov     rdi, rax
0x18000a136  lea     r8, [rax-1]
0x18000a13a  xor     edx, edx
0x18000a13c  lea     rcx, [rsp+270h+pv]
0x18000a141  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18000a146  mov     ebx, eax
0x18000a148  test    eax, eax
0x18000a14a  js      loc_18000A1F8
0x18000a150  lea     r9, [rsp+270h+var_240]
0x18000a155  mov     r8, rdi
0x18000a158  mov     rbx, [rsp+270h+pv]
0x18000a15d  mov     rdx, rbx
0x18000a160  mov     rcx, rsi
0x18000a163  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18000a168  mov     r14d, eax
0x18000a16b  test    eax, eax
0x18000a16d  js      short loc_18000A1D0
0x18000a16f  mov     rax, [rsp+270h+var_240]
0x18000a174  cmp     rax, rdi
0x18000a177  ja      short loc_18000A133
0x18000a179  lea     rax, [rsp+270h+var_248]
0x18000a17e  cmp     r15, rax
0x18000a181  jz      short loc_18000A1A9
0x18000a183  mov     r14, [r15]
0x18000a186  test    r14, r14
0x18000a189  jz      short loc_18000A1A4
0x18000a18b  call    cs:__imp_GetLastError
0x18000a191  mov     edi, eax
0x18000a193  mov     rcx, r14; pv
0x18000a196  call    cs:__imp_CoTaskMemFree
0x18000a19c  mov     ecx, edi; dwErrCode
0x18000a19e  call    cs:__imp_SetLastError
0x18000a1a4  mov     [r15], rbx
0x18000a1a7  jmp     short loc_18000A1B7
0x18000a1a9  test    rbx, rbx
0x18000a1ac  jz      short loc_18000A1B7
0x18000a1ae  mov     rcx, rbx; pv
0x18000a1b1  call    cs:__imp_CoTaskMemFree
0x18000a1b7  mov     rcx, [rsi+70h]
0x18000a1bb  test    rcx, rcx
0x18000a1be  jz      short loc_18000A1CC
0x18000a1c0  mov     rax, [rcx]
0x18000a1c3  mov     rax, [rax+18h]
0x18000a1c7  call    _guard_dispatch_icall
0x18000a1cc  xor     eax, eax
0x18000a1ce  jmp     short loc_18000A23A
0x18000a1d0  test    rbx, rbx
0x18000a1d3  jz      short loc_18000A1DE
0x18000a1d5  mov     rcx, rbx; pv
0x18000a1d8  call    cs:__imp_CoTaskMemFree
0x18000a1de  mov     rcx, [rsi+70h]
0x18000a1e2  test    rcx, rcx
0x18000a1e5  jz      short loc_18000A1F3
0x18000a1e7  mov     rax, [rcx]
0x18000a1ea  mov     rax, [rax+18h]
0x18000a1ee  call    _guard_dispatch_icall
0x18000a1f3  mov     eax, r14d
0x18000a1f6  jmp     short loc_18000A23A
0x18000a1f8  mov     edx, 16Ah; void *
0x18000a1fd  mov     r9d, ebx; char *
0x18000a200  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000a207  mov     rcx, [rbp+178h]; this
0x18000a20e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a213  mov     rcx, [rsp+270h+pv]; pv
0x18000a218  test    rcx, rcx
0x18000a21b  jz      short loc_18000A223
0x18000a21d  call    cs:__imp_CoTaskMemFree
0x18000a223  mov     rcx, [rsi+70h]
0x18000a227  test    rcx, rcx
0x18000a22a  jz      short loc_18000A238
0x18000a22c  mov     rax, [rcx]
0x18000a22f  mov     rax, [rax+18h]
0x18000a233  call    _guard_dispatch_icall
0x18000a238  mov     eax, ebx
0x18000a23a  mov     rcx, [rbp+170h+var_30]
0x18000a241  xor     rcx, rsp; StackCookie
0x18000a244  call    __security_check_cookie
0x18000a249  mov     rbx, [rsp+270h+arg_10]
0x18000a251  add     rsp, 250h
0x18000a258  pop     r15
0x18000a25a  pop     r14
0x18000a25c  pop     rdi
0x18000a25d  pop     rsi
0x18000a25e  pop     rbp
0x18000a25f  retn
```
