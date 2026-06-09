# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x180004ea4`
- end: `0x180005094`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004348`

## callees

- `0x180004ea4`
- `0x180005320`
- `0x1800055a0`
- `0x180006858`
- `0x18000ed40`
- `0x180015430`
- `0x1800154b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000500c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005051`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000500c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fd2`

## string_xrefs

- `0x180005034`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x180004ea4  mov     [rsp-8+arg_10], rbx
0x180004ea9  push    rbp
0x180004eaa  push    rsi
0x180004eab  push    rdi
0x180004eac  push    r14
0x180004eae  push    r15
0x180004eb0  lea     rbp, [rsp-150h]
0x180004eb8  sub     rsp, 250h
0x180004ebf  mov     rax, cs:__security_cookie
0x180004ec6  xor     rax, rsp
0x180004ec9  mov     [rbp+170h+var_30], rax
0x180004ed0  mov     rsi, rdx
0x180004ed3  mov     r15, rcx
0x180004ed6  mov     [rsp+270h+pv], 0; int
0x180004edf  xor     edx, edx; Val
0x180004ee1  mov     r8d, 200h; Size
0x180004ee7  lea     rcx, [rsp+270h+var_230]; void *
0x180004eec  call    memset
0x180004ef1  mov     [rsp+270h+var_240], 0
0x180004efa  lea     r9, [rsp+270h+var_240]
0x180004eff  mov     edi, 100h
0x180004f04  mov     r8d, edi
0x180004f07  lea     rdx, [rsp+270h+var_230]
0x180004f0c  mov     rcx, rsi
0x180004f0f  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180004f14  mov     ebx, eax
0x180004f16  test    eax, eax
0x180004f18  jns     short loc_180004F33
0x180004f1a  mov     rcx, [rsi+70h]
0x180004f1e  test    rcx, rcx
0x180004f21  jz      loc_18000506C
0x180004f27  mov     rdx, [rcx]
0x180004f2a  mov     rax, [rdx+18h]
0x180004f2e  jmp     loc_180005067
0x180004f33  mov     rax, [rsp+270h+var_240]
0x180004f38  cmp     rax, rdi
0x180004f3b  ja      short loc_180004F67
0x180004f3d  lea     r8, [rax-1]
0x180004f41  lea     rdx, [rsp+270h+var_230]
0x180004f46  lea     rcx, [rsp+270h+pv]
0x180004f4b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180004f50  mov     ebx, eax
0x180004f52  test    eax, eax
0x180004f54  jns     short loc_180004F60
0x180004f56  mov     edx, 15Fh
0x180004f5b  jmp     loc_180005031
0x180004f60  mov     rbx, [rsp+270h+pv]
0x180004f65  jmp     short loc_180004FAD
0x180004f67  mov     rdi, rax
0x180004f6a  lea     r8, [rax-1]
0x180004f6e  xor     edx, edx
0x180004f70  lea     rcx, [rsp+270h+pv]
0x180004f75  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180004f7a  mov     ebx, eax
0x180004f7c  test    eax, eax
0x180004f7e  js      loc_18000502C
0x180004f84  lea     r9, [rsp+270h+var_240]
0x180004f89  mov     r8, rdi
0x180004f8c  mov     rbx, [rsp+270h+pv]
0x180004f91  mov     rdx, rbx
0x180004f94  mov     rcx, rsi
0x180004f97  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180004f9c  mov     r14d, eax
0x180004f9f  test    eax, eax
0x180004fa1  js      short loc_180005004
0x180004fa3  mov     rax, [rsp+270h+var_240]
0x180004fa8  cmp     rax, rdi
0x180004fab  ja      short loc_180004F67
0x180004fad  lea     rax, [rsp+270h+var_248]
0x180004fb2  cmp     r15, rax
0x180004fb5  jz      short loc_180004FDD
0x180004fb7  mov     r14, [r15]
0x180004fba  test    r14, r14
0x180004fbd  jz      short loc_180004FD8
0x180004fbf  call    cs:__imp_GetLastError
0x180004fc5  mov     edi, eax
0x180004fc7  mov     rcx, r14; pv
0x180004fca  call    cs:__imp_CoTaskMemFree
0x180004fd0  mov     ecx, edi; dwErrCode
0x180004fd2  call    cs:__imp_SetLastError
0x180004fd8  mov     [r15], rbx
0x180004fdb  jmp     short loc_180004FEB
0x180004fdd  test    rbx, rbx
0x180004fe0  jz      short loc_180004FEB
0x180004fe2  mov     rcx, rbx; pv
0x180004fe5  call    cs:__imp_CoTaskMemFree
0x180004feb  mov     rcx, [rsi+70h]
0x180004fef  test    rcx, rcx
0x180004ff2  jz      short loc_180005000
0x180004ff4  mov     rax, [rcx]
0x180004ff7  mov     rax, [rax+18h]
0x180004ffb  call    _guard_dispatch_icall
0x180005000  xor     eax, eax
0x180005002  jmp     short loc_18000506E
0x180005004  test    rbx, rbx
0x180005007  jz      short loc_180005012
0x180005009  mov     rcx, rbx; pv
0x18000500c  call    cs:__imp_CoTaskMemFree
0x180005012  mov     rcx, [rsi+70h]
0x180005016  test    rcx, rcx
0x180005019  jz      short loc_180005027
0x18000501b  mov     rax, [rcx]
0x18000501e  mov     rax, [rax+18h]
0x180005022  call    _guard_dispatch_icall
0x180005027  mov     eax, r14d
0x18000502a  jmp     short loc_18000506E
0x18000502c  mov     edx, 16Ah; void *
0x180005031  mov     r9d, ebx; char *
0x180005034  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000503b  mov     rcx, [rbp+178h]; this
0x180005042  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005047  mov     rcx, [rsp+270h+pv]; pv
0x18000504c  test    rcx, rcx
0x18000504f  jz      short loc_180005057
0x180005051  call    cs:__imp_CoTaskMemFree
0x180005057  mov     rcx, [rsi+70h]
0x18000505b  test    rcx, rcx
0x18000505e  jz      short loc_18000506C
0x180005060  mov     rax, [rcx]
0x180005063  mov     rax, [rax+18h]
0x180005067  call    _guard_dispatch_icall
0x18000506c  mov     eax, ebx
0x18000506e  mov     rcx, [rbp+170h+var_30]
0x180005075  xor     rcx, rsp; StackCookie
0x180005078  call    __security_check_cookie
0x18000507d  mov     rbx, [rsp+270h+arg_10]
0x180005085  add     rsp, 250h
0x18000508c  pop     r15
0x18000508e  pop     r14
0x180005090  pop     rdi
0x180005091  pop     rsi
0x180005092  pop     rbp
0x180005093  retn
```
