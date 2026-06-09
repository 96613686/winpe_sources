# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x180009064`
- end: `0x180009254`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800082b4`

## callees

- `0x180003760`
- `0x180009064`
- `0x180009564`
- `0x1800097e0`
- `0x18000fce0`
- `0x180015a00`
- `0x180015a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009192`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000917f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000917f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000918a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000918a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009211`

## string_xrefs

- `0x1800091f4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x180009064  mov     [rsp-8+arg_10], rbx
0x180009069  push    rbp
0x18000906a  push    rsi
0x18000906b  push    rdi
0x18000906c  push    r14
0x18000906e  push    r15
0x180009070  lea     rbp, [rsp-150h]
0x180009078  sub     rsp, 250h
0x18000907f  mov     rax, cs:__security_cookie
0x180009086  xor     rax, rsp
0x180009089  mov     [rbp+170h+var_30], rax
0x180009090  mov     rsi, rdx
0x180009093  mov     r15, rcx
0x180009096  mov     [rsp+270h+pv], 0; int
0x18000909f  xor     edx, edx; Val
0x1800090a1  mov     r8d, 200h; Size
0x1800090a7  lea     rcx, [rsp+270h+var_230]; void *
0x1800090ac  call    memset
0x1800090b1  mov     [rsp+270h+var_240], 0
0x1800090ba  lea     r9, [rsp+270h+var_240]
0x1800090bf  mov     edi, 100h
0x1800090c4  mov     r8d, edi
0x1800090c7  lea     rdx, [rsp+270h+var_230]
0x1800090cc  mov     rcx, rsi
0x1800090cf  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x1800090d4  mov     ebx, eax
0x1800090d6  test    eax, eax
0x1800090d8  jns     short loc_1800090F3
0x1800090da  mov     rcx, [rsi+70h]
0x1800090de  test    rcx, rcx
0x1800090e1  jz      loc_18000922C
0x1800090e7  mov     rdx, [rcx]
0x1800090ea  mov     rax, [rdx+18h]
0x1800090ee  jmp     loc_180009227
0x1800090f3  mov     rax, [rsp+270h+var_240]
0x1800090f8  cmp     rax, rdi
0x1800090fb  ja      short loc_180009127
0x1800090fd  lea     r8, [rax-1]
0x180009101  lea     rdx, [rsp+270h+var_230]
0x180009106  lea     rcx, [rsp+270h+pv]
0x18000910b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180009110  mov     ebx, eax
0x180009112  test    eax, eax
0x180009114  jns     short loc_180009120
0x180009116  mov     edx, 15Fh
0x18000911b  jmp     loc_1800091F1
0x180009120  mov     rbx, [rsp+270h+pv]
0x180009125  jmp     short loc_18000916D
0x180009127  mov     rdi, rax
0x18000912a  lea     r8, [rax-1]
0x18000912e  xor     edx, edx
0x180009130  lea     rcx, [rsp+270h+pv]
0x180009135  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18000913a  mov     ebx, eax
0x18000913c  test    eax, eax
0x18000913e  js      loc_1800091EC
0x180009144  lea     r9, [rsp+270h+var_240]
0x180009149  mov     r8, rdi
0x18000914c  mov     rbx, [rsp+270h+pv]
0x180009151  mov     rdx, rbx
0x180009154  mov     rcx, rsi
0x180009157  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18000915c  mov     r14d, eax
0x18000915f  test    eax, eax
0x180009161  js      short loc_1800091C4
0x180009163  mov     rax, [rsp+270h+var_240]
0x180009168  cmp     rax, rdi
0x18000916b  ja      short loc_180009127
0x18000916d  lea     rax, [rsp+270h+var_248]
0x180009172  cmp     r15, rax
0x180009175  jz      short loc_18000919D
0x180009177  mov     r14, [r15]
0x18000917a  test    r14, r14
0x18000917d  jz      short loc_180009198
0x18000917f  call    cs:__imp_GetLastError
0x180009185  mov     edi, eax
0x180009187  mov     rcx, r14; pv
0x18000918a  call    cs:__imp_CoTaskMemFree
0x180009190  mov     ecx, edi; dwErrCode
0x180009192  call    cs:__imp_SetLastError
0x180009198  mov     [r15], rbx
0x18000919b  jmp     short loc_1800091AB
0x18000919d  test    rbx, rbx
0x1800091a0  jz      short loc_1800091AB
0x1800091a2  mov     rcx, rbx; pv
0x1800091a5  call    cs:__imp_CoTaskMemFree
0x1800091ab  mov     rcx, [rsi+70h]
0x1800091af  test    rcx, rcx
0x1800091b2  jz      short loc_1800091C0
0x1800091b4  mov     rax, [rcx]
0x1800091b7  mov     rax, [rax+18h]
0x1800091bb  call    _guard_dispatch_icall
0x1800091c0  xor     eax, eax
0x1800091c2  jmp     short loc_18000922E
0x1800091c4  test    rbx, rbx
0x1800091c7  jz      short loc_1800091D2
0x1800091c9  mov     rcx, rbx; pv
0x1800091cc  call    cs:__imp_CoTaskMemFree
0x1800091d2  mov     rcx, [rsi+70h]
0x1800091d6  test    rcx, rcx
0x1800091d9  jz      short loc_1800091E7
0x1800091db  mov     rax, [rcx]
0x1800091de  mov     rax, [rax+18h]
0x1800091e2  call    _guard_dispatch_icall
0x1800091e7  mov     eax, r14d
0x1800091ea  jmp     short loc_18000922E
0x1800091ec  mov     edx, 16Ah; void *
0x1800091f1  mov     r9d, ebx; char *
0x1800091f4  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800091fb  mov     rcx, [rbp+178h]; this
0x180009202  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009207  mov     rcx, [rsp+270h+pv]; pv
0x18000920c  test    rcx, rcx
0x18000920f  jz      short loc_180009217
0x180009211  call    cs:__imp_CoTaskMemFree
0x180009217  mov     rcx, [rsi+70h]
0x18000921b  test    rcx, rcx
0x18000921e  jz      short loc_18000922C
0x180009220  mov     rax, [rcx]
0x180009223  mov     rax, [rax+18h]
0x180009227  call    _guard_dispatch_icall
0x18000922c  mov     eax, ebx
0x18000922e  mov     rcx, [rbp+170h+var_30]
0x180009235  xor     rcx, rsp; StackCookie
0x180009238  call    __security_check_cookie
0x18000923d  mov     rbx, [rsp+270h+arg_10]
0x180009245  add     rsp, 250h
0x18000924c  pop     r15
0x18000924e  pop     r14
0x180009250  pop     rdi
0x180009251  pop     rsi
0x180009252  pop     rbp
0x180009253  retn
```
