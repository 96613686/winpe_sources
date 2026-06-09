# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x18003deb0`
- end: `0x18003e094`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003e1bc`

## callees

- `0x180006400`
- `0x180024dac`
- `0x180024f00`
- `0x18003deb0`
- `0x1800427d0`
- `0x180047a30`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dfc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dfc5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dfd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dfd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dfd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dfeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e012`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dfd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dfeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e012`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e054`

## string_xrefs

- `0x18003e03a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x18003deb0  mov     [rsp-8+arg_10], rbx
0x18003deb5  push    rbp
0x18003deb6  push    rsi
0x18003deb7  push    rdi
0x18003deb8  push    r14
0x18003deba  push    r15
0x18003debc  lea     rbp, [rsp-50h]
0x18003dec1  sub     rsp, 150h
0x18003dec8  mov     rax, cs:__security_cookie
0x18003decf  xor     rax, rsp
0x18003ded2  mov     [rbp+70h+var_30], rax
0x18003ded6  mov     rsi, rdx
0x18003ded9  mov     r15, rcx
0x18003dedc  mov     [rsp+170h+pv], 0; int
0x18003dee5  xor     edx, edx; Val
0x18003dee7  mov     r8d, 100h; Size
0x18003deed  lea     rcx, [rsp+170h+var_130]; void *
0x18003def2  call    memset
0x18003def7  mov     [rsp+170h+var_140], 0
0x18003df00  lea     r9, [rsp+170h+var_140]
0x18003df05  mov     edi, 80h
0x18003df0a  mov     r8d, edi
0x18003df0d  lea     rdx, [rsp+170h+var_130]
0x18003df12  mov     rcx, rsi
0x18003df15  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18003df1a  mov     ebx, eax
0x18003df1c  test    eax, eax
0x18003df1e  jns     short loc_18003DF39
0x18003df20  mov     rcx, [rsi+70h]
0x18003df24  test    rcx, rcx
0x18003df27  jz      loc_18003E06F
0x18003df2d  mov     rdx, [rcx]
0x18003df30  mov     rax, [rdx+18h]
0x18003df34  jmp     loc_18003E06A
0x18003df39  mov     rax, [rsp+170h+var_140]
0x18003df3e  cmp     rax, rdi
0x18003df41  ja      short loc_18003DF6D
0x18003df43  lea     r8, [rax-1]
0x18003df47  lea     rdx, [rsp+170h+var_130]
0x18003df4c  lea     rcx, [rsp+170h+pv]
0x18003df51  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18003df56  mov     ebx, eax
0x18003df58  test    eax, eax
0x18003df5a  jns     short loc_18003DF66
0x18003df5c  mov     edx, 15Fh
0x18003df61  jmp     loc_18003E037
0x18003df66  mov     rbx, [rsp+170h+pv]
0x18003df6b  jmp     short loc_18003DFB3
0x18003df6d  mov     rdi, rax
0x18003df70  lea     r8, [rax-1]
0x18003df74  xor     edx, edx
0x18003df76  lea     rcx, [rsp+170h+pv]
0x18003df7b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18003df80  mov     ebx, eax
0x18003df82  test    eax, eax
0x18003df84  js      loc_18003E032
0x18003df8a  lea     r9, [rsp+170h+var_140]
0x18003df8f  mov     r8, rdi
0x18003df92  mov     rbx, [rsp+170h+pv]
0x18003df97  mov     rdx, rbx
0x18003df9a  mov     rcx, rsi
0x18003df9d  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18003dfa2  mov     r14d, eax
0x18003dfa5  test    eax, eax
0x18003dfa7  js      short loc_18003E00A
0x18003dfa9  mov     rax, [rsp+170h+var_140]
0x18003dfae  cmp     rax, rdi
0x18003dfb1  ja      short loc_18003DF6D
0x18003dfb3  lea     rax, [rsp+170h+var_148]
0x18003dfb8  cmp     r15, rax
0x18003dfbb  jz      short loc_18003DFE3
0x18003dfbd  mov     r14, [r15]
0x18003dfc0  test    r14, r14
0x18003dfc3  jz      short loc_18003DFDE
0x18003dfc5  call    cs:__imp_GetLastError
0x18003dfcb  mov     edi, eax
0x18003dfcd  mov     rcx, r14; pv
0x18003dfd0  call    cs:__imp_CoTaskMemFree
0x18003dfd6  mov     ecx, edi; dwErrCode
0x18003dfd8  call    cs:__imp_SetLastError
0x18003dfde  mov     [r15], rbx
0x18003dfe1  jmp     short loc_18003DFF1
0x18003dfe3  test    rbx, rbx
0x18003dfe6  jz      short loc_18003DFF1
0x18003dfe8  mov     rcx, rbx; pv
0x18003dfeb  call    cs:__imp_CoTaskMemFree
0x18003dff1  mov     rcx, [rsi+70h]
0x18003dff5  test    rcx, rcx
0x18003dff8  jz      short loc_18003E006
0x18003dffa  mov     rax, [rcx]
0x18003dffd  mov     rax, [rax+18h]
0x18003e001  call    _guard_dispatch_icall
0x18003e006  xor     eax, eax
0x18003e008  jmp     short loc_18003E071
0x18003e00a  test    rbx, rbx
0x18003e00d  jz      short loc_18003E018
0x18003e00f  mov     rcx, rbx; pv
0x18003e012  call    cs:__imp_CoTaskMemFree
0x18003e018  mov     rcx, [rsi+70h]
0x18003e01c  test    rcx, rcx
0x18003e01f  jz      short loc_18003E02D
0x18003e021  mov     rax, [rcx]
0x18003e024  mov     rax, [rax+18h]
0x18003e028  call    _guard_dispatch_icall
0x18003e02d  mov     eax, r14d
0x18003e030  jmp     short loc_18003E071
0x18003e032  mov     edx, 16Ah; void *
0x18003e037  mov     r9d, ebx; char *
0x18003e03a  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18003e041  mov     rcx, [rbp+78h]; this
0x18003e045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e04a  mov     rcx, [rsp+170h+pv]; pv
0x18003e04f  test    rcx, rcx
0x18003e052  jz      short loc_18003E05A
0x18003e054  call    cs:__imp_CoTaskMemFree
0x18003e05a  mov     rcx, [rsi+70h]
0x18003e05e  test    rcx, rcx
0x18003e061  jz      short loc_18003E06F
0x18003e063  mov     rax, [rcx]
0x18003e066  mov     rax, [rax+18h]
0x18003e06a  call    _guard_dispatch_icall
0x18003e06f  mov     eax, ebx
0x18003e071  mov     rcx, [rbp+70h+var_30]
0x18003e075  xor     rcx, rsp; StackCookie
0x18003e078  call    __security_check_cookie
0x18003e07d  mov     rbx, [rsp+170h+arg_10]
0x18003e085  add     rsp, 150h
0x18003e08c  pop     r15
0x18003e08e  pop     r14
0x18003e090  pop     rdi
0x18003e091  pop     rsi
0x18003e092  pop     rbp
0x18003e093  retn
```
