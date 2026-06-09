# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1400065f4`
- end: `0x1400067c2`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000659c`

## callees

- `0x140002130`
- `0x140002c38`
- `0x140005434`
- `0x1400065f4`
- `0x140008c30`
- `0x14000a418`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006731`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000671e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000671e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000677d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000677d`

## string_xrefs

- `0x140006760`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        char *a2)
{
  int v3; // edi
  unsigned __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rdx
  void *v7; // rbx
  unsigned __int64 v8; // rsi
  void *v9; // rsi
  DWORD LastError; // edi
  void *v11; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  const wchar_t *v15; // [rsp+30h] [rbp-D0h] BYREF
  char v16; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[13]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v19; // [rsp+B0h] [rbp-50h]
  _BYTE v20[512]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v15 = L"%SystemRoot%\\uus";
  v18[0] = &wistd::__function::__func<_lambda_ed01672e02d6682bf5b3b76f9b133eec_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v18[1] = &v15;
  v19 = v18;
  pv = 0;
  memset_0(v20, 0, sizeof(v20));
  v14 = 0;
  v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v17, v20, 256, &v14);
  if ( v3 >= 0 )
  {
    v4 = v14;
    if ( v14 > 0x100 )
    {
      while ( 1 )
      {
        v8 = v4;
        v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v4 - 1);
        v3 = v5;
        if ( v5 < 0 )
        {
          v6 = 378;
          goto LABEL_19;
        }
        v7 = pv;
        v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v17, pv, v8, &v14);
        if ( v3 < 0 )
          break;
        v4 = v14;
        if ( v14 <= v8 )
          goto LABEL_9;
      }
      if ( !v7 )
        goto LABEL_21;
      v11 = v7;
      goto LABEL_20;
    }
    v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
           &pv,
           v20,
           v14 - 1);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v7 = pv;
LABEL_9:
      if ( a2 == &v16 )
      {
        if ( v7 )
          CoTaskMemFree(v7);
      }
      else
      {
        v9 = *(void **)a2;
        if ( *(_QWORD *)a2 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v9);
          SetLastError(LastError);
        }
        *(_QWORD *)a2 = v7;
      }
      v3 = 0;
    }
    else
    {
      v6 = 367;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
        (const char *)(unsigned int)v5,
        (int)pv);
      v11 = pv;
      if ( pv )
LABEL_20:
        CoTaskMemFree(v11);
    }
  }
LABEL_21:
  if ( v19 )
    (*(void (__fastcall **)(_QWORD *))(*v19 + 24LL))(v19);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400065f4  mov     [rsp-8+arg_0], rbx
0x1400065f9  mov     [rsp-8+arg_10], rsi
0x1400065fe  push    rbp
0x1400065ff  push    rdi
0x140006600  push    r14
0x140006602  lea     rbp, [rsp-1D0h]
0x14000660a  sub     rsp, 2D0h
0x140006611  mov     rax, cs:__security_cookie
0x140006618  xor     rax, rsp
0x14000661b  mov     [rbp+1E0h+var_20], rax
0x140006622  mov     r14, rdx
0x140006625  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x14000662c  mov     [rsp+2E0h+var_2B0], rax
0x140006631  lea     rax, ??_7?$__func@V_lambda_ed01672e02d6682bf5b3b76f9b133eec_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_ed01672e02d6682bf5b3b76f9b133eec_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x140006638  mov     [rsp+2E0h+var_298], rax
0x14000663d  lea     rax, [rsp+2E0h+var_2B0]
0x140006642  mov     [rsp+2E0h+var_290], rax
0x140006647  lea     rax, [rsp+2E0h+var_298]
0x14000664c  mov     [rbp+1E0h+var_230], rax
0x140006650  mov     [rsp+2E0h+pv], 0; int
0x140006659  xor     edx, edx; Val
0x14000665b  mov     r8d, 200h; Size
0x140006661  lea     rcx, [rbp+1E0h+var_220]; void *
0x140006665  call    memset_0
0x14000666a  mov     [rsp+2E0h+var_2B8], 0
0x140006673  lea     r9, [rsp+2E0h+var_2B8]
0x140006678  mov     ebx, 100h
0x14000667d  mov     r8d, ebx
0x140006680  lea     rdx, [rbp+1E0h+var_220]
0x140006684  lea     rcx, [rsp+2E0h+var_2A0]
0x140006689  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x14000668e  mov     edi, eax
0x140006690  test    eax, eax
0x140006692  js      loc_140006784
0x140006698  mov     rax, [rsp+2E0h+var_2B8]
0x14000669d  cmp     rax, rbx
0x1400066a0  ja      short loc_1400066C9
0x1400066a2  lea     r8, [rax-1]
0x1400066a6  lea     rdx, [rbp+1E0h+var_220]
0x1400066aa  lea     rcx, [rsp+2E0h+pv]
0x1400066af  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x1400066b4  mov     edi, eax
0x1400066b6  test    eax, eax
0x1400066b8  jns     short loc_1400066C2
0x1400066ba  lea     edx, [rbx+6Fh]
0x1400066bd  jmp     loc_14000675D
0x1400066c2  mov     rbx, [rsp+2E0h+pv]
0x1400066c7  jmp     short loc_14000670C
0x1400066c9  mov     rsi, rax
0x1400066cc  lea     r8, [rax-1]
0x1400066d0  xor     edx, edx
0x1400066d2  lea     rcx, [rsp+2E0h+pv]
0x1400066d7  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x1400066dc  mov     edi, eax
0x1400066de  test    eax, eax
0x1400066e0  js      short loc_140006758
0x1400066e2  lea     r9, [rsp+2E0h+var_2B8]
0x1400066e7  mov     r8, rsi
0x1400066ea  mov     rbx, [rsp+2E0h+pv]
0x1400066ef  mov     rdx, rbx
0x1400066f2  lea     rcx, [rsp+2E0h+var_2A0]
0x1400066f7  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x1400066fc  mov     edi, eax
0x1400066fe  test    eax, eax
0x140006700  js      short loc_14000674E
0x140006702  mov     rax, [rsp+2E0h+var_2B8]
0x140006707  cmp     rax, rsi
0x14000670a  ja      short loc_1400066C9
0x14000670c  lea     rax, [rsp+2E0h+var_2A8]
0x140006711  cmp     r14, rax
0x140006714  jz      short loc_14000673C
0x140006716  mov     rsi, [r14]
0x140006719  test    rsi, rsi
0x14000671c  jz      short loc_140006737
0x14000671e  call    cs:__imp_GetLastError
0x140006724  mov     edi, eax
0x140006726  mov     rcx, rsi; pv
0x140006729  call    cs:__imp_CoTaskMemFree
0x14000672f  mov     ecx, edi; dwErrCode
0x140006731  call    cs:__imp_SetLastError
0x140006737  mov     [r14], rbx
0x14000673a  jmp     short loc_14000674A
0x14000673c  test    rbx, rbx
0x14000673f  jz      short loc_14000674A
0x140006741  mov     rcx, rbx; pv
0x140006744  call    cs:__imp_CoTaskMemFree
0x14000674a  xor     edi, edi
0x14000674c  jmp     short loc_140006784
0x14000674e  test    rbx, rbx
0x140006751  jz      short loc_140006784
0x140006753  mov     rcx, rbx
0x140006756  jmp     short loc_14000677D
0x140006758  mov     edx, 17Ah; void *
0x14000675d  mov     r9d, eax; char *
0x140006760  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006767  mov     rcx, [rbp+1E8h]; this
0x14000676e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006773  mov     rcx, [rsp+2E0h+pv]; pv
0x140006778  test    rcx, rcx
0x14000677b  jz      short loc_140006784
0x14000677d  call    cs:__imp_CoTaskMemFree
0x140006783  nop
0x140006784  mov     rcx, [rbp+1E0h+var_230]
0x140006788  test    rcx, rcx
0x14000678b  jz      short loc_140006799
0x14000678d  mov     rdx, [rcx]
0x140006790  mov     rax, [rdx+18h]
0x140006794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006799  mov     eax, edi
0x14000679b  mov     rcx, [rbp+1E0h+var_20]
0x1400067a2  xor     rcx, rsp; StackCookie
0x1400067a5  call    __security_check_cookie
0x1400067aa  lea     r11, [rsp+2E0h+var_10]
0x1400067b2  mov     rbx, [r11+20h]
0x1400067b6  mov     rsi, [r11+30h]
0x1400067ba  mov     rsp, r11
0x1400067bd  pop     r14
0x1400067bf  pop     rdi
0x1400067c0  pop     rbp
0x1400067c1  retn
```
