# I_EnrollForAikCertificate

- ea: `0x1800207b4`
- end: `0x180020ce9`
- name: `I_EnrollForAikCertificate`
- size: `1333`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ec10`

## callees

- `0x180001ec0`
- `0x1800035a4`
- `0x180003818`
- `0x18000bc48`
- `0x18000c198`
- `0x180015384`
- `0x180016040`
- `0x18001b1c0`
- `0x18001c9fc`
- `0x18001cafc`
- `0x18001cb24`
- `0x18001cbac`
- `0x18001cca4`
- `0x18001cf74`
- `0x18001d018`
- `0x18001d038`
- `0x18001d564`
- `0x1800207b4`
- `0x180025480`
- `0x180037010`

## import_xrefs

- `certenroll!__imp_EnrollForAIKCertificate` at `0x180020bec`
- `certenroll!__imp_EnrollForAIKCertificate` at `0x180020bec`
- `certenroll!__imp_FreeEnrollAIKResult` at `0x180020bb9`
- `certenroll!__imp_FreeEnrollAIKResult` at `0x180020bb9`
- `OLEAUT32!__imp_SysAllocString` at `0x180020927`
- `OLEAUT32!__imp_SysAllocString` at `0x180020a41`
- `OLEAUT32!__imp_SysAllocString` at `0x180020927`
- `OLEAUT32!__imp_SysAllocString` at `0x180020a41`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800208a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800208a0`

## string_xrefs

- `0x1800208f7`: `Unable to create private key instance`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 I_EnrollForAikCertificate()
{
  __int64 v0; // rax
  __int64 v1; // rcx
  int v2; // r9d
  unsigned int v3; // ebx
  BSTR v4; // rax
  __int64 v5; // rcx
  int v6; // edi
  __int64 v7; // rcx
  int v8; // r9d
  const OLECHAR *v9; // rax
  BSTR v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // r9d
  _QWORD *v14; // rcx
  int v15; // edx
  const char *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rcx
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  HRESULT v22; // [rsp+34h] [rbp-CCh] BYREF
  BSTR v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v31; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v32[3]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v33; // [rsp+98h] [rbp-68h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp-60h] BYREF
  char v35; // [rsp+A8h] [rbp-58h]
  _BYTE v36[40]; // [rsp+B8h] [rbp-48h] BYREF
  char v37[32]; // [rsp+E0h] [rbp-20h] BYREF

  v21 = 0;
  v22 = 0;
  v27 = 0;
  v30 = 0;
  v25 = 0;
  strcpy(v37, "I_EnrollForAikCertificate");
  v32[0] = v37;
  v32[1] = &v25;
  v32[2] = &v21;
  lambda_2351563e18091e8d3efc99849afe8761_::operator()(v32);
  v25 = 1;
  v31 = v32;
  v0 = lambda_de3778786de369a202eed9eff2cb4b76_::_lambda_de3778786de369a202eed9eff2cb4b76_(
         (unsigned int)&v33,
         (unsigned int)&v27,
         (unsigned int)&v21,
         (unsigned int)&v22,
         (__int64)&v30);
  wil::ScopeExitNoExcept__lambda_de3778786de369a202eed9eff2cb4b76___(v36, v0);
  v24 = 0;
  v33 = &v24;
  ppv = 0;
  v35 = 1;
  v22 = CoCreateInstance(
          &GUID_884e200c_217d_11da_b2a4_000e7bbb2b09,
          0,
          1u,
          &GUID_728ab30c_217d_11da_b2a4_000e7bbb2b09,
          &ppv);
  wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IX509PrivateKey2,wil::err_exception_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IX509PrivateKey2,wil::err_exception_policy>>(&v33);
  if ( v22 >= 0 )
  {
    v4 = SysAllocString(L"Microsoft Platform Crypto Provider");
    v23 = v4;
    if ( !v4 )
    {
      WppTraceIndent(v5, 2u);
      v6 = 14;
      v21 = 14;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          14,
          (__int64)"Out of memory");
        v6 = v21;
      }
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
      v3 = v6;
      goto LABEL_44;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v24 + 208LL))(v24, v4);
    if ( v22 < 0 )
    {
      WppTraceIndent(v7, 2u);
      v3 = v22;
      v21 = v22;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          v8,
          v22,
          (__int64)"Unable to set provider name");
        v3 = v21;
      }
      goto LABEL_43;
    }
    v9 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v10 = SysAllocString(v9);
    v26 = v10;
    if ( !v10 )
    {
      WppTraceIndent(v11, 2u);
      v6 = 14;
      v21 = 14;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          14,
          (__int64)"Out of memory");
        v6 = v21;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
      goto LABEL_11;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v24 + 128LL))(v24, v10);
    if ( v22 >= 0 )
    {
      v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 424LL))(v24, 0xFFFFFFFFLL);
      if ( v22 >= 0 )
      {
        std::chrono::steady_clock::now(&v29);
        v18 = v27;
        if ( v27 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v28);
          FreeEnrollAIKResult(v18);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v28);
        }
        v27 = 0;
        v22 = EnrollForAIKCertificate(0, 0, 0, 0, v24, &v27);
        std::chrono::steady_clock::now(&v28);
        v29 = v28 - v29;
        v19 = *(_QWORD *)std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1000>>,__int64,std::ratio<1,1000000000>,0>(
                           &v28,
                           &v29);
        v30 = v19;
        if ( v22 >= 0 )
          goto LABEL_41;
        WppTraceIndent(v19, 2u);
        v3 = v22;
        v21 = v22;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v15 = 20;
        v16 = "Unable to enroll for AIK certificate";
      }
      else
      {
        WppTraceIndent(v17, 2u);
        v3 = v22;
        v21 = v22;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v15 = 19;
        v16 = "Unable to set existing status";
      }
    }
    else
    {
      WppTraceIndent(v12, 2u);
      v3 = v22;
      v21 = v22;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      v15 = 18;
      v16 = "Unable to set container name";
    }
    WPP_SF_sds(v14[2], v15, (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids, v13, v3, (__int64)v16);
LABEL_41:
    v3 = v21;
LABEL_42:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
LABEL_43:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
    goto LABEL_44;
  }
  WppTraceIndent(v1, 2u);
  v3 = v22;
  v21 = v22;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
      v2,
      v22,
      (__int64)"Unable to create private key instance");
    v3 = v21;
  }
LABEL_44:
  wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>(&v24);
  wil::details::ScopeExitFnGuard__lambda_de3778786de369a202eed9eff2cb4b76___::_ScopeExitFnGuard__lambda_de3778786de369a202eed9eff2cb4b76___(v36);
  WppTraceUnwinder__lambda_2351563e18091e8d3efc99849afe8761____::_WppTraceUnwinder__lambda_2351563e18091e8d3efc99849afe8761____(&v31);
  wil::details::unique_storage<wil::details::resource_policy<EnrollAIKResult *,long (*)(EnrollAIKResult *),&long FreeEnrollAIKResult(EnrollAIKResult *),wistd::integral_constant<unsigned __int64,0>,EnrollAIKResult *,EnrollAIKResult *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EnrollAIKResult *,long (*)(EnrollAIKResult *),&long FreeEnrollAIKResult(EnrollAIKResult *),wistd::integral_constant<unsigned __int64,0>,EnrollAIKResult *,EnrollAIKResult *,0,std::nullptr_t>>(&v27);
  return v3;
}

```

## disassembly

```asm
0x1800207b4  mov     [rsp-8+arg_0], rbx
0x1800207b9  mov     [rsp-8+arg_10], rdi
0x1800207be  push    rbp
0x1800207bf  lea     rbp, [rsp-10h]
0x1800207c4  sub     rsp, 110h
0x1800207cb  mov     rax, cs:__security_cookie
0x1800207d2  xor     rax, rsp
0x1800207d5  mov     [rbp+10h+var_10], rax
0x1800207d9  mov     rbx, rdx
0x1800207dc  xor     edi, edi
0x1800207de  mov     [rsp+110h+var_E0], edi
0x1800207e2  mov     [rsp+110h+var_DC], edi
0x1800207e6  mov     [rsp+110h+var_B8], rdi
0x1800207eb  mov     [rsp+110h+var_A0], rdi
0x1800207f0  mov     [rsp+110h+var_C8], edi
0x1800207f4  movups  xmm0, xmmword ptr cs:aIEnrollforaikc; "I_EnrollForAikCertificate"
0x1800207fb  movups  xmmword ptr [rbp+10h+var_30], xmm0
0x1800207ff  movups  xmm1, xmmword ptr cs:aIEnrollforaikc+0Ah; "rAikCertificate"
0x180020806  movups  xmmword ptr [rbp+10h+var_30+0Ah], xmm1
0x18002080a  lea     rax, [rbp+10h+var_30]
0x18002080e  mov     [rbp+10h+var_90], rax
0x180020812  lea     rax, [rsp+110h+var_C8]
0x180020817  mov     [rbp+10h+var_88], rax
0x18002081b  lea     rax, [rsp+110h+var_E0]
0x180020820  mov     [rbp+10h+var_80], rax
0x180020824  lea     rcx, [rbp+10h+var_90]
0x180020828  call    _lambda_2351563e18091e8d3efc99849afe8761___operator__
0x18002082d  mov     [rsp+110h+var_C8], 1
0x180020835  lea     rax, [rbp+10h+var_90]
0x180020839  mov     [rsp+110h+var_98], rax
0x18002083e  lea     rax, [rsp+110h+var_A0]
0x180020843  mov     [rsp+110h+ppv], rax
0x180020848  lea     r9, [rsp+110h+var_DC]
0x18002084d  lea     r8, [rsp+110h+var_E0]
0x180020852  lea     rdx, [rsp+110h+var_B8]
0x180020857  lea     rcx, [rbp+10h+var_78]
0x18002085b  call    _lambda_de3778786de369a202eed9eff2cb4b76____lambda_de3778786de369a202eed9eff2cb4b76_
0x180020860  mov     rdx, rax
0x180020863  lea     rcx, [rbp+10h+var_58]
0x180020867  call    wil__ScopeExitNoExcept__lambda_de3778786de369a202eed9eff2cb4b76___
0x18002086c  nop
0x18002086d  mov     [rsp+110h+var_D0], rdi
0x180020872  lea     rax, [rsp+110h+var_D0]
0x180020877  mov     [rbp+10h+var_78], rax
0x18002087b  mov     [rbp+10h+var_70], rdi
0x18002087f  mov     [rbp+10h+var_68], 1
0x180020883  lea     rax, [rbp+10h+var_70]
0x180020887  mov     [rsp+110h+ppv], rax; ppv
0x18002088c  lea     r9, _GUID_728ab30c_217d_11da_b2a4_000e7bbb2b09; riid
0x180020893  xor     edx, edx; pUnkOuter
0x180020895  lea     r8d, [rdi+1]; dwClsContext
0x180020899  lea     rcx, _GUID_884e200c_217d_11da_b2a4_000e7bbb2b09; rclsid
0x1800208a0  call    cs:__imp_CoCreateInstance
0x1800208a6  mov     [rsp+110h+var_DC], eax
0x1800208aa  lea     rcx, [rbp+10h+var_78]
0x1800208ae  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UIX509PrivateKey2@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IX509PrivateKey2,wil::err_exception_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IX509PrivateKey2,wil::err_exception_policy>>(void)
0x1800208b3  cmp     [rsp+110h+var_DC], edi
0x1800208b7  jge     short loc_180020920
0x1800208b9  lea     edx, [rdi+2]
0x1800208bc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800208c1  mov     ebx, [rsp+110h+var_DC]
0x1800208c5  mov     [rsp+110h+var_E0], ebx
0x1800208c9  lea     rax, WPP_GLOBAL_Control
0x1800208d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208d7  cmp     rcx, rax
0x1800208da  jz      loc_180020C9C
0x1800208e0  test    byte ptr [rcx+1Ch], 1
0x1800208e4  jz      loc_180020C9C
0x1800208ea  cmp     byte ptr [rcx+19h], 2
0x1800208ee  jb      loc_180020C9C
0x1800208f4  lea     edx, [rdi+0Eh]
0x1800208f7  lea     rax, aUnableToCreate_7; "Unable to create private key instance"
0x1800208fe  mov     [rsp+110h+var_E8], rax
0x180020903  mov     dword ptr [rsp+110h+ppv], ebx
0x180020907  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18002090e  mov     rcx, [rcx+10h]
0x180020912  call    WPP_SF_sds
0x180020917  mov     ebx, [rsp+110h+var_E0]
0x18002091b  jmp     loc_180020C9C
0x180020920  lea     rcx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180020927  call    cs:__imp_SysAllocString
0x18002092d  mov     [rsp+110h+var_D8], rax
0x180020932  test    rax, rax
0x180020935  jnz     short loc_1800209A6
0x180020937  lea     edx, [rax+2]
0x18002093a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002093f  mov     edi, 0Eh
0x180020944  mov     [rsp+110h+var_E0], edi
0x180020948  lea     rax, WPP_GLOBAL_Control
0x18002094f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020956  cmp     rcx, rax
0x180020959  jz      short loc_180020995
0x18002095b  test    byte ptr [rcx+1Ch], 1
0x18002095f  jz      short loc_180020995
0x180020961  cmp     byte ptr [rcx+19h], 2
0x180020965  jb      short loc_180020995
0x180020967  lea     edx, [rdi+1]
0x18002096a  lea     rax, aOutOfMemory; "Out of memory"
0x180020971  mov     [rsp+110h+var_E8], rax
0x180020976  mov     dword ptr [rsp+110h+ppv], edi
0x18002097a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180020981  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180020988  mov     rcx, [rcx+10h]
0x18002098c  call    WPP_SF_sDs
0x180020991  mov     edi, [rsp+110h+var_E0]
0x180020995  lea     rcx, [rsp+110h+var_D8]
0x18002099a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002099f  mov     ebx, edi
0x1800209a1  jmp     loc_180020C9C
0x1800209a6  mov     r9, [rsp+110h+var_D0]
0x1800209ab  mov     rcx, [r9]
0x1800209ae  mov     r8, [rcx+0D0h]
0x1800209b5  mov     rdx, rax
0x1800209b8  mov     rcx, r9
0x1800209bb  mov     rax, r8
0x1800209be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209c3  mov     [rsp+110h+var_DC], eax
0x1800209c7  test    eax, eax
0x1800209c9  jns     short loc_180020A36
0x1800209cb  mov     edx, 2
0x1800209d0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800209d5  mov     ebx, [rsp+110h+var_DC]
0x1800209d9  mov     [rsp+110h+var_E0], ebx
0x1800209dd  lea     rax, WPP_GLOBAL_Control
0x1800209e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209eb  cmp     rcx, rax
0x1800209ee  jz      loc_180020C91
0x1800209f4  test    byte ptr [rcx+1Ch], 1
0x1800209f8  jz      loc_180020C91
0x1800209fe  cmp     byte ptr [rcx+19h], 2
0x180020a02  jb      loc_180020C91
0x180020a08  mov     edx, 10h
0x180020a0d  lea     rax, aUnableToSetPro; "Unable to set provider name"
0x180020a14  mov     [rsp+110h+var_E8], rax
0x180020a19  mov     dword ptr [rsp+110h+ppv], ebx
0x180020a1d  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180020a24  mov     rcx, [rcx+10h]
0x180020a28  call    WPP_SF_sds
0x180020a2d  mov     ebx, [rsp+110h+var_E0]
0x180020a31  jmp     loc_180020C91
0x180020a36  mov     rcx, rbx
0x180020a39  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180020a3e  mov     rcx, rax; psz
0x180020a41  call    cs:__imp_SysAllocString
0x180020a47  mov     [rsp+110h+var_C0], rax
0x180020a4c  test    rax, rax
0x180020a4f  jnz     short loc_180020ABE
0x180020a51  lea     edx, [rax+2]
0x180020a54  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020a59  mov     edi, 0Eh
0x180020a5e  mov     [rsp+110h+var_E0], edi
0x180020a62  lea     rax, WPP_GLOBAL_Control
0x180020a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a70  cmp     rcx, rax
0x180020a73  jz      short loc_180020AAF
0x180020a75  test    byte ptr [rcx+1Ch], 1
0x180020a79  jz      short loc_180020AAF
0x180020a7b  cmp     byte ptr [rcx+19h], 2
0x180020a7f  jb      short loc_180020AAF
0x180020a81  lea     edx, [rdi+3]
0x180020a84  lea     rax, aOutOfMemory; "Out of memory"
0x180020a8b  mov     [rsp+110h+var_E8], rax
0x180020a90  mov     dword ptr [rsp+110h+ppv], edi
0x180020a94  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180020a9b  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180020aa2  mov     rcx, [rcx+10h]
0x180020aa6  call    WPP_SF_sDs
0x180020aab  mov     edi, [rsp+110h+var_E0]
0x180020aaf  lea     rcx, [rsp+110h+var_C0]
0x180020ab4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020ab9  jmp     loc_180020995
0x180020abe  mov     rcx, [rsp+110h+var_D0]
0x180020ac3  mov     r8, [rcx]
0x180020ac6  mov     rdx, rax
0x180020ac9  mov     rax, [r8+80h]
0x180020ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ad5  mov     [rsp+110h+var_DC], eax
0x180020ad9  test    eax, eax
0x180020adb  jns     short loc_180020B2B
0x180020add  mov     edx, 2
0x180020ae2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020ae7  mov     ebx, [rsp+110h+var_DC]
0x180020aeb  mov     [rsp+110h+var_E0], ebx
0x180020aef  lea     rax, WPP_GLOBAL_Control
0x180020af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180020afd  cmp     rcx, rax
0x180020b00  jz      loc_180020C86
0x180020b06  test    byte ptr [rcx+1Ch], 1
0x180020b0a  jz      loc_180020C86
0x180020b10  cmp     byte ptr [rcx+19h], 2
0x180020b14  jb      loc_180020C86
0x180020b1a  mov     edx, 12h
0x180020b1f  lea     rax, aUnableToSetCon; "Unable to set container name"
0x180020b26  jmp     loc_180020C69
0x180020b2b  mov     rcx, [rsp+110h+var_D0]
0x180020b30  mov     rax, [rcx]
0x180020b33  or      edx, 0FFFFFFFFh
0x180020b36  mov     rax, [rax+1A8h]
0x180020b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b42  mov     [rsp+110h+var_DC], eax
0x180020b46  test    eax, eax
0x180020b48  jns     short loc_180020B98
0x180020b4a  mov     edx, 2
0x180020b4f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020b54  mov     ebx, [rsp+110h+var_DC]
0x180020b58  mov     [rsp+110h+var_E0], ebx
0x180020b5c  lea     rax, WPP_GLOBAL_Control
0x180020b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b6a  cmp     rcx, rax
0x180020b6d  jz      loc_180020C86
0x180020b73  test    byte ptr [rcx+1Ch], 1
0x180020b77  jz      loc_180020C86
0x180020b7d  cmp     byte ptr [rcx+19h], 2
0x180020b81  jb      loc_180020C86
0x180020b87  mov     edx, 13h
0x180020b8c  lea     rax, aUnableToSetExi; "Unable to set existing status"
0x180020b93  jmp     loc_180020C69
0x180020b98  lea     rcx, [rsp+110h+var_A8]
0x180020b9d  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180020ba2  mov     rbx, [rsp+110h+var_B8]
0x180020ba7  test    rbx, rbx
0x180020baa  jz      short loc_180020BC9
0x180020bac  lea     rcx, [rsp+110h+var_B0]; this
0x180020bb1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180020bb6  mov     rcx, rbx
0x180020bb9  call    cs:__imp_FreeEnrollAIKResult
0x180020bbf  lea     rcx, [rsp+110h+var_B0]; this
0x180020bc4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180020bc9  mov     [rsp+110h+var_B8], rdi
0x180020bce  mov     rax, [rsp+110h+var_D0]
0x180020bd3  lea     rcx, [rsp+110h+var_B8]
0x180020bd8  mov     [rsp+110h+var_E8], rcx
0x180020bdd  mov     [rsp+110h+ppv], rax
0x180020be2  xor     r9d, r9d
0x180020be5  xor     r8d, r8d
0x180020be8  xor     edx, edx
0x180020bea  xor     ecx, ecx
0x180020bec  call    cs:__imp_EnrollForAIKCertificate
0x180020bf2  mov     [rsp+110h+var_DC], eax
0x180020bf6  lea     rcx, [rsp+110h+var_B0]
0x180020bfb  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180020c00  mov     rax, [rsp+110h+var_B0]
0x180020c05  sub     rax, [rsp+110h+var_A8]
0x180020c0a  mov     [rsp+110h+var_A8], rax
0x180020c0f  lea     rdx, [rsp+110h+var_A8]
0x180020c14  lea     rcx, [rsp+110h+var_B0]
0x180020c19  call    ??$duration_cast@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_JU?$ratio@$00$0DLJKMKAA@@3@$0A@@chrono@std@@YA?AV?$duration@_JU?$ratio@$00$0DOI@@std@@@01@AEBV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<__int64,std::ratio<1,1000>>,__int64,std::ratio<1,1000000000>,0>(std::chrono::duration<__int64,std::ratio<1,1000000000>> const &)
0x180020c1e  mov     rcx, [rax]
0x180020c21  mov     [rsp+110h+var_A0], rcx
0x180020c26  cmp     [rsp+110h+var_DC], edi
0x180020c2a  jge     short loc_180020C82
0x180020c2c  mov     edx, 2
0x180020c31  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020c36  mov     ebx, [rsp+110h+var_DC]
0x180020c3a  mov     [rsp+110h+var_E0], ebx
0x180020c3e  lea     rax, WPP_GLOBAL_Control
0x180020c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c4c  cmp     rcx, rax
0x180020c4f  jz      short loc_180020C86
0x180020c51  test    byte ptr [rcx+1Ch], 1
0x180020c55  jz      short loc_180020C86
0x180020c57  cmp     byte ptr [rcx+19h], 2
0x180020c5b  jb      short loc_180020C86
0x180020c5d  mov     edx, 14h
0x180020c62  lea     rax, aUnableToEnroll; "Unable to enroll for AIK certificate"
0x180020c69  mov     [rsp+110h+var_E8], rax
0x180020c6e  mov     dword ptr [rsp+110h+ppv], ebx
0x180020c72  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180020c79  mov     rcx, [rcx+10h]
0x180020c7d  call    WPP_SF_sds
0x180020c82  mov     ebx, [rsp+110h+var_E0]
0x180020c86  lea     rcx, [rsp+110h+var_C0]
0x180020c8b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020c90  nop
0x180020c91  lea     rcx, [rsp+110h+var_D8]
0x180020c96  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020c9b  nop
0x180020c9c  lea     rcx, [rsp+110h+var_D0]
0x180020ca1  call    ??1?$com_ptr_t@UITpmVCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>(void)
0x180020ca6  nop
0x180020ca7  lea     rcx, [rbp+10h+var_58]
0x180020cab  call    wil__details__ScopeExitFnGuard__lambda_de3778786de369a202eed9eff2cb4b76______ScopeExitFnGuard__lambda_de3778786de369a202eed9eff2cb4b76___
0x180020cb0  nop
0x180020cb1  lea     rcx, [rsp+110h+var_98]
0x180020cb6  call    WppTraceUnwinder__lambda_2351563e18091e8d3efc99849afe8761_______WppTraceUnwinder__lambda_2351563e18091e8d3efc99849afe8761____
0x180020cbb  nop
0x180020cbc  lea     rcx, [rsp+110h+var_B8]
0x180020cc1  call    ??1?$unique_storage@U?$resource_policy@PEAUEnrollAIKResult@@P6AJPEAU1@@Z$1?FreeEnrollAIKResult@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EnrollAIKResult *,long (*)(EnrollAIKResult *),&FreeEnrollAIKResult(EnrollAIKResult *),wistd::integral_constant<unsigned __int64,0>,EnrollAIKResult *,EnrollAIKResult *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EnrollAIKResult *,long (*)(EnrollAIKResult *),&FreeEnrollAIKResult(EnrollAIKResult *),wistd::integral_constant<unsigned __int64,0>,EnrollAIKResult *,EnrollAIKResult *,0,std::nullptr_t>>(void)
0x180020cc6  mov     eax, ebx
0x180020cc8  mov     rcx, [rbp+10h+var_10]
0x180020ccc  xor     rcx, rsp; StackCookie
0x180020ccf  call    __security_check_cookie
0x180020cd4  lea     r11, [rsp+110h+var_s0]
0x180020cdc  mov     rbx, [r11+10h]
0x180020ce0  mov     rdi, [r11+20h]
0x180020ce4  mov     rsp, r11
0x180020ce7  pop     rbp
0x180020ce8  retn
```
