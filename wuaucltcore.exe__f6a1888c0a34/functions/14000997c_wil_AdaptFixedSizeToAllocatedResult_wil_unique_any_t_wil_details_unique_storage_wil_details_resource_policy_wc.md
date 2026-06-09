# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x14000997c`
- end: `0x140009b6c`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140008fd4`

## callees

- `0x140002ac0`
- `0x14000997c`
- `0x14000acbc`
- `0x14000ae14`
- `0x14001aa60`
- `0x1400206e0`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009aa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009abd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009ae4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009b29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009aa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009abd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009ae4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009a97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009aaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009aaa`

## string_xrefs

- `0x140009b0c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x14000997c  mov     [rsp-8+arg_10], rbx
0x140009981  push    rbp
0x140009982  push    rsi
0x140009983  push    rdi
0x140009984  push    r14
0x140009986  push    r15
0x140009988  lea     rbp, [rsp-150h]
0x140009990  sub     rsp, 250h
0x140009997  mov     rax, cs:__security_cookie
0x14000999e  xor     rax, rsp
0x1400099a1  mov     [rbp+170h+var_30], rax
0x1400099a8  mov     rsi, rdx
0x1400099ab  mov     r15, rcx
0x1400099ae  mov     [rsp+270h+pv], 0; int
0x1400099b7  xor     edx, edx; Val
0x1400099b9  mov     r8d, 200h; Size
0x1400099bf  lea     rcx, [rsp+270h+var_230]; void *
0x1400099c4  call    memset
0x1400099c9  mov     [rsp+270h+var_240], 0
0x1400099d2  lea     r9, [rsp+270h+var_240]
0x1400099d7  mov     edi, 100h
0x1400099dc  mov     r8d, edi
0x1400099df  lea     rdx, [rsp+270h+var_230]
0x1400099e4  mov     rcx, rsi
0x1400099e7  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x1400099ec  mov     ebx, eax
0x1400099ee  test    eax, eax
0x1400099f0  jns     short loc_140009A0B
0x1400099f2  mov     rcx, [rsi+70h]
0x1400099f6  test    rcx, rcx
0x1400099f9  jz      loc_140009B44
0x1400099ff  mov     rdx, [rcx]
0x140009a02  mov     rax, [rdx+18h]
0x140009a06  jmp     loc_140009B3F
0x140009a0b  mov     rax, [rsp+270h+var_240]
0x140009a10  cmp     rax, rdi
0x140009a13  ja      short loc_140009A3F
0x140009a15  lea     r8, [rax-1]
0x140009a19  lea     rdx, [rsp+270h+var_230]
0x140009a1e  lea     rcx, [rsp+270h+pv]
0x140009a23  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x140009a28  mov     ebx, eax
0x140009a2a  test    eax, eax
0x140009a2c  jns     short loc_140009A38
0x140009a2e  mov     edx, 15Fh
0x140009a33  jmp     loc_140009B09
0x140009a38  mov     rbx, [rsp+270h+pv]
0x140009a3d  jmp     short loc_140009A85
0x140009a3f  mov     rdi, rax
0x140009a42  lea     r8, [rax-1]
0x140009a46  xor     edx, edx
0x140009a48  lea     rcx, [rsp+270h+pv]
0x140009a4d  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x140009a52  mov     ebx, eax
0x140009a54  test    eax, eax
0x140009a56  js      loc_140009B04
0x140009a5c  lea     r9, [rsp+270h+var_240]
0x140009a61  mov     r8, rdi
0x140009a64  mov     rbx, [rsp+270h+pv]
0x140009a69  mov     rdx, rbx
0x140009a6c  mov     rcx, rsi
0x140009a6f  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x140009a74  mov     r14d, eax
0x140009a77  test    eax, eax
0x140009a79  js      short loc_140009ADC
0x140009a7b  mov     rax, [rsp+270h+var_240]
0x140009a80  cmp     rax, rdi
0x140009a83  ja      short loc_140009A3F
0x140009a85  lea     rax, [rsp+270h+var_248]
0x140009a8a  cmp     r15, rax
0x140009a8d  jz      short loc_140009AB5
0x140009a8f  mov     r14, [r15]
0x140009a92  test    r14, r14
0x140009a95  jz      short loc_140009AB0
0x140009a97  call    cs:__imp_GetLastError
0x140009a9d  mov     edi, eax
0x140009a9f  mov     rcx, r14; pv
0x140009aa2  call    cs:__imp_CoTaskMemFree
0x140009aa8  mov     ecx, edi; dwErrCode
0x140009aaa  call    cs:__imp_SetLastError
0x140009ab0  mov     [r15], rbx
0x140009ab3  jmp     short loc_140009AC3
0x140009ab5  test    rbx, rbx
0x140009ab8  jz      short loc_140009AC3
0x140009aba  mov     rcx, rbx; pv
0x140009abd  call    cs:__imp_CoTaskMemFree
0x140009ac3  mov     rcx, [rsi+70h]
0x140009ac7  test    rcx, rcx
0x140009aca  jz      short loc_140009AD8
0x140009acc  mov     rax, [rcx]
0x140009acf  mov     rax, [rax+18h]
0x140009ad3  call    _guard_dispatch_icall
0x140009ad8  xor     eax, eax
0x140009ada  jmp     short loc_140009B46
0x140009adc  test    rbx, rbx
0x140009adf  jz      short loc_140009AEA
0x140009ae1  mov     rcx, rbx; pv
0x140009ae4  call    cs:__imp_CoTaskMemFree
0x140009aea  mov     rcx, [rsi+70h]
0x140009aee  test    rcx, rcx
0x140009af1  jz      short loc_140009AFF
0x140009af3  mov     rax, [rcx]
0x140009af6  mov     rax, [rax+18h]
0x140009afa  call    _guard_dispatch_icall
0x140009aff  mov     eax, r14d
0x140009b02  jmp     short loc_140009B46
0x140009b04  mov     edx, 16Ah; void *
0x140009b09  mov     r9d, ebx; char *
0x140009b0c  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140009b13  mov     rcx, [rbp+178h]; this
0x140009b1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009b1f  mov     rcx, [rsp+270h+pv]; pv
0x140009b24  test    rcx, rcx
0x140009b27  jz      short loc_140009B2F
0x140009b29  call    cs:__imp_CoTaskMemFree
0x140009b2f  mov     rcx, [rsi+70h]
0x140009b33  test    rcx, rcx
0x140009b36  jz      short loc_140009B44
0x140009b38  mov     rax, [rcx]
0x140009b3b  mov     rax, [rax+18h]
0x140009b3f  call    _guard_dispatch_icall
0x140009b44  mov     eax, ebx
0x140009b46  mov     rcx, [rbp+170h+var_30]
0x140009b4d  xor     rcx, rsp; StackCookie
0x140009b50  call    __security_check_cookie
0x140009b55  mov     rbx, [rsp+270h+arg_10]
0x140009b5d  add     rsp, 250h
0x140009b64  pop     r15
0x140009b66  pop     r14
0x140009b68  pop     rdi
0x140009b69  pop     rsi
0x140009b6a  pop     rbp
0x140009b6b  retn
```
