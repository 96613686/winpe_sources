# WslSession::s_GetCommandLineForDistro(ushort const *,ushort const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180009270`
- end: `0x1800093e4`
- name: `?s_GetCommandLineForDistro@WslSession@@CAJPEBG0HAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(va_list, __int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007b58`

## callees

- `0x180001dc0`
- `0x180004fb4`
- `0x180004fd4`
- `0x18000698c`
- `0x180007f04`
- `0x18000854c`
- `0x180008570`
- `0x180009270`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009386`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009386`

## pseudocode

```c
__int64 __fastcall WslSession::s_GetCommandLineForDistro(va_list a1, __int64 *a2, int a3, __int64 a4)
{
  int LastError; // ebx
  __int64 *v9; // rcx
  __int64 *v10; // rax
  DWORD v11; // ebx
  const char *v12; // r9
  va_list v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v17; // [rsp+58h] [rbp-A8h]
  _BYTE v18[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v19[14]; // [rsp+68h] [rbp-98h] BYREF
  va_list Arguments[6]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v14 = 0;
  v19[0] = &wistd::__function::__func<_lambda_b184ef8228511dea446194ec32405fe9_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v19[13] = v19;
  LastError = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                (__int64)&v14,
                (__int64)v18);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v18);
  if ( LastError >= 0 )
  {
    v9 = &qword_18000F0B8;
    Arguments[0] = v14;
    Arguments[4] = a1;
    Arguments[1] = (va_list)L"wsl.exe";
    v10 = &qword_18000F0B8;
    v15 = a4;
    if ( !a3 )
      v10 = (__int64 *)L"~";
    *(_QWORD *)Buffer = 0;
    Arguments[2] = (va_list)v10;
    v17 = 1;
    Arguments[3] = (va_list)L"distribution";
    if ( a2 )
      v9 = a2;
    Arguments[5] = (va_list)v9;
    v11 = FormatMessageW(0x2500u, L"%1\\%2 %3 --%4 %5 %6", 0, 0, Buffer, 0, Arguments);
    wil::details::out_param_ptr_t<unsigned short *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_ptr_t<unsigned short *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v15);
    if ( v11 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x7F,
                    (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
                    v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A,
      (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)(unsigned int)LastError);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v14);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180009270  mov     [rsp-8+arg_10], rbx
0x180009275  push    rbp
0x180009276  push    rsi
0x180009277  push    rdi
0x180009278  push    r14
0x18000927a  push    r15
0x18000927c  lea     rbp, [rsp-10h]
0x180009281  sub     rsp, 110h
0x180009288  mov     rax, cs:__security_cookie
0x18000928f  xor     rax, rsp
0x180009292  mov     [rbp+30h+var_28], rax
0x180009296  lea     rax, ??_7?$__func@V_lambda_b184ef8228511dea446194ec32405fe9_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_b184ef8228511dea446194ec32405fe9_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000929d  mov     [rsp+130h+var_F0], 0
0x1800092a6  mov     [rsp+130h+var_C8], rax
0x1800092ab  mov     rdi, rdx
0x1800092ae  lea     rax, [rsp+130h+var_C8]
0x1800092b3  mov     r15, rcx
0x1800092b6  lea     rdx, [rsp+130h+var_D0]
0x1800092bb  mov     [rbp+30h+var_60], rax
0x1800092bf  lea     rcx, [rsp+130h+var_F0]
0x1800092c4  mov     rsi, r9
0x1800092c7  mov     r14d, r8d
0x1800092ca  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x1800092cf  lea     rcx, [rsp+130h+var_D0]
0x1800092d4  mov     ebx, eax
0x1800092d6  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x1800092db  test    ebx, ebx
0x1800092dd  jns     short loc_1800092FC
0x1800092df  mov     rcx, [rbp+38h]; this
0x1800092e3  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x1800092ea  mov     r9d, ebx; char *
0x1800092ed  mov     edx, 6Ah ; 'j'; void *
0x1800092f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800092f7  jmp     loc_1800093B5
0x1800092fc  mov     rax, [rsp+130h+var_F0]
0x180009301  lea     rcx, qword_18000F0B8
0x180009308  mov     [rbp+30h+var_58], rax
0x18000930c  lea     rdx, asc_18000EFBC; "~"
0x180009313  lea     rax, aWslExe; "wsl.exe"
0x18000931a  mov     [rbp+30h+var_38], r15
0x18000931e  mov     [rbp+30h+var_50], rax
0x180009322  test    r14d, r14d
0x180009325  mov     rax, rcx
0x180009328  mov     [rsp+130h+var_E8], rsi
0x18000932d  cmovz   rax, rdx
0x180009331  mov     qword ptr [rsp+130h+Buffer], 0
0x18000933a  mov     [rbp+30h+var_48], rax
0x18000933e  lea     rdx, a123456; "%1\\%2 %3 --%4 %5 %6"
0x180009345  lea     rax, aDistribution; "distribution"
0x18000934c  mov     [rsp+130h+var_D8], 1
0x180009351  mov     [rbp+30h+var_40], rax
0x180009355  test    rdi, rdi
0x180009358  lea     rax, [rbp+30h+var_58]
0x18000935c  cmovnz  rcx, rdi
0x180009360  mov     [rsp+130h+Arguments], rax; Arguments
0x180009365  lea     rax, [rsp+130h+Buffer]
0x18000936a  mov     [rbp+30h+var_30], rcx
0x18000936e  mov     [rsp+130h+nSize], 0; nSize
0x180009376  xor     r9d, r9d; dwLanguageId
0x180009379  xor     r8d, r8d; dwMessageId
0x18000937c  mov     [rsp+130h+lpBuffer], rax; lpBuffer
0x180009381  mov     ecx, 2500h; dwFlags
0x180009386  call    cs:__imp_FormatMessageW
0x18000938c  lea     rcx, [rsp+130h+var_E8]
0x180009391  mov     ebx, eax
0x180009393  call    ??1?$out_param_ptr_t@PEAGV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<ushort *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_ptr_t<ushort *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180009398  test    ebx, ebx
0x18000939a  jnz     short loc_1800093B3
0x18000939c  mov     rcx, [rbp+38h]; this
0x1800093a0  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x1800093a7  lea     edx, [rbx+7Fh]; void *
0x1800093aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800093af  mov     ebx, eax
0x1800093b1  jmp     short loc_1800093B5
0x1800093b3  xor     ebx, ebx
0x1800093b5  lea     rcx, [rsp+130h+var_F0]
0x1800093ba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800093bf  mov     eax, ebx
0x1800093c1  mov     rcx, [rbp+30h+var_28]
0x1800093c5  xor     rcx, rsp; StackCookie
0x1800093c8  call    __security_check_cookie
0x1800093cd  mov     rbx, [rsp+130h+arg_10]
0x1800093d5  add     rsp, 110h
0x1800093dc  pop     r15
0x1800093de  pop     r14
0x1800093e0  pop     rdi
0x1800093e1  pop     rsi
0x1800093e2  pop     rbp
0x1800093e3  retn
```
