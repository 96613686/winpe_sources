# NtsKeyExchangeCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180054b50`
- end: `0x180054ef4`
- name: `?NtsKeyExchangeCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `932`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180016454`
- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18003dd2c`
- `0x180041348`
- `0x180041384`
- `0x1800529e4`
- `0x180052b08`
- `0x180052b4c`
- `0x1800531c0`
- `0x1800532a4`
- `0x180053cb8`
- `0x180054918`
- `0x180054b50`
- `0x180054efc`
- `0x180058a5c`
- `0x18005997c`

## import_xrefs

- `SspiCli!DeleteSecurityContext` at `0x180054ec0`
- `SspiCli!DeleteSecurityContext` at `0x180054ec0`

## string_xrefs

- `0x180054d84`: `NtsKeyExchangeCallback: Attempting to validate cert with selfsigned hashes\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall NtsKeyExchangeCallback(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)
{
  char *v4; // rdx
  int v5; // esi
  __int64 v6; // rbx
  __int64 v7; // rax
  int v8; // esi
  __int64 v9; // rbx
  __int64 v10; // rax
  int v11; // esi
  __int64 v12; // rbx
  __int64 v13; // rax
  int v14; // esi
  __int64 v15; // rbx
  __int64 v16; // rax
  SOCKET v17; // [rsp+30h] [rbp-D0h] BYREF
  PCtxtHandle phContext; // [rsp+38h] [rbp-C8h] BYREF
  char v19; // [rsp+40h] [rbp-C0h]
  _BYTE *v20; // [rsp+48h] [rbp-B8h]
  _BYTE *v21; // [rsp+50h] [rbp-B0h]
  _BYTE v22[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[40]; // [rsp+78h] [rbp-88h] BYREF
  struct _SecHandle v24; // [rsp+A0h] [rbp-60h] BYREF
  char v25; // [rsp+B0h] [rbp-50h] BYREF
  int v26; // [rsp+B1h] [rbp-4Fh]
  __int16 v27; // [rsp+B5h] [rbp-4Bh]
  char v28; // [rsp+B7h] [rbp-49h]
  char v29[32]; // [rsp+B8h] [rbp-48h] BYREF
  char v30[128]; // [rsp+D8h] [rbp-28h] BYREF
  int v31; // [rsp+158h] [rbp+58h]
  int v32; // [rsp+15Ch] [rbp+5Ch]
  __int64 v33; // [rsp+160h] [rbp+60h]
  __int64 v34; // [rsp+168h] [rbp+68h]
  __int64 v35; // [rsp+170h] [rbp+70h]
  char v36; // [rsp+178h] [rbp+78h]
  int v37; // [rsp+179h] [rbp+79h]
  __int16 v38; // [rsp+17Dh] [rbp+7Dh]
  char v39; // [rsp+17Fh] [rbp+7Fh]
  __int64 v40; // [rsp+180h] [rbp+80h]
  __int64 v41[3]; // [rsp+188h] [rbp+88h] BYREF
  char v42[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v43; // [rsp+1B0h] [rbp+B0h]
  __int64 v44; // [rsp+1B8h] [rbp+B8h]
  __int64 v45; // [rsp+1C0h] [rbp+C0h]

  if ( Context )
  {
    v24 = 0;
    v17 = (SOCKET)&v24;
    wil::scope_exit__lambda_85c834fe03eae1d77d2b644c99f96282___(&phContext, &v17, Timer);
    if ( (unsigned __int8)FileLogAllowEntry(200) )
    {
      if ( *((_QWORD *)Context + 3) <= 7u )
        v4 = Context;
      else
        v4 = *(char **)Context;
      FileLogAdd(L"NtsKeyExchangeCallback: Starting callback for server: %s \n", v4);
    }
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    std::wstring::wstring(v29);
    memset_0(v30, 0, sizeof(v30));
    v31 = 123;
    v32 = 0xFFFF;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v41);
    std::set<std::array<unsigned char,32>>::set<std::array<unsigned char,32>>(v42);
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v17 = -1;
    v5 = ConnectSocket(Context, &v17, &v25);
    if ( v5 >= 0 )
    {
      v8 = NegotiateTLS(&v17, (__int64)Context, &v24, 0, Context[32]);
      if ( v8 >= 0 )
      {
        if ( !Context[32] )
          goto LABEL_18;
        if ( (unsigned __int8)FileLogAllowEntry(200) )
          FileLogAdd(L"NtsKeyExchangeCallback: Attempting to validate cert with selfsigned hashes\n");
        v11 = ManualCertValidation(&v24, Context + 33);
        if ( v11 < 0 )
        {
          v21 = v23;
          v12 = std::wstring::wstring(v23, L"ManualCertValidation");
          v20 = v22;
          v13 = std::wstring::wstring(v22, Context);
          NtsKeyExchangeCallbackComplete(v13, (unsigned int)v11, v12, &v25);
        }
        else
        {
LABEL_18:
          v14 = DoNtsKeyExchange((__int64)&v17, &v24, (__int64)&v25, (__int64)(Context + 56));
          v21 = v23;
          if ( v14 >= 0 )
            v15 = std::wstring::wstring(v23, &qword_180071478);
          else
            v15 = std::wstring::wstring(v23, L"DoNtsKeyExchange");
          v20 = v22;
          v16 = std::wstring::wstring(v22, Context);
          NtsKeyExchangeCallbackComplete(v16, (unsigned int)v14, v15, &v25);
        }
      }
      else
      {
        v21 = v23;
        v9 = std::wstring::wstring(v23, L"NegotiateTLS");
        v20 = v22;
        v10 = std::wstring::wstring(v22, Context);
        NtsKeyExchangeCallbackComplete(v10, (unsigned int)v8, v9, &v25);
      }
    }
    else
    {
      v20 = v22;
      v6 = std::wstring::wstring(v22, L"ConnectSocket");
      v21 = v23;
      v7 = std::wstring::wstring(v23, Context);
      NtsKeyExchangeCallbackComplete(v7, (unsigned int)v5, v6, &v25);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>(&v17);
    NtsForNtpInfoInternal::~NtsForNtpInfoInternal((NtsForNtpInfoInternal *)&v25);
    if ( v19 )
    {
      v19 = 0;
      if ( phContext->dwLower || phContext->dwUpper )
        DeleteSecurityContext(phContext);
    }
  }
  else if ( (unsigned __int8)FileLogAllowEntry(200) )
  {
    FileLogAdd(L"NtsKeyExchangeCallback: Context is null\n");
  }
}

```

## disassembly

```asm
0x180054b50  mov     [rsp-8+arg_0], rbx
0x180054b55  mov     [rsp-8+arg_10], rsi
0x180054b5a  push    rbp
0x180054b5b  push    rdi
0x180054b5c  push    r14
0x180054b5e  lea     rbp, [rsp-0E0h]
0x180054b66  sub     rsp, 1E0h
0x180054b6d  mov     rax, cs:__security_cookie
0x180054b74  xor     rax, rsp
0x180054b77  mov     [rbp+0F0h+var_20], rax
0x180054b7e  mov     rdi, rdx
0x180054b81  xor     r14d, r14d
0x180054b84  test    rdx, rdx
0x180054b87  jnz     short loc_180054BAC
0x180054b89  mov     ecx, 0C8h
0x180054b8e  call    FileLogAllowEntry
0x180054b93  test    al, al
0x180054b95  jz      loc_180054ECC
0x180054b9b  lea     rcx, aNtskeyexchange_1; "NtsKeyExchangeCallback: Context is null"...
0x180054ba2  call    FileLogAdd
0x180054ba7  jmp     loc_180054ECC
0x180054bac  xorps   xmm0, xmm0
0x180054baf  movups  [rbp+0F0h+var_150], xmm0
0x180054bb3  lea     rax, [rbp+0F0h+var_150]
0x180054bb7  mov     [rsp+1F0h+var_1C0], rax
0x180054bbc  lea     rdx, [rsp+1F0h+var_1C0]
0x180054bc1  lea     rcx, [rsp+1F0h+phContext]
0x180054bc6  call    wil__scope_exit__lambda_85c834fe03eae1d77d2b644c99f96282___
0x180054bcb  nop
0x180054bcc  mov     ecx, 0C8h
0x180054bd1  call    FileLogAllowEntry
0x180054bd6  test    al, al
0x180054bd8  jz      short loc_180054BF5
0x180054bda  cmp     qword ptr [rdi+18h], 7
0x180054bdf  jbe     short loc_180054BE6
0x180054be1  mov     rdx, [rdi]
0x180054be4  jmp     short loc_180054BE9
0x180054be6  mov     rdx, rdi
0x180054be9  lea     rcx, aNtskeyexchange; "NtsKeyExchangeCallback: Starting callba"...
0x180054bf0  call    FileLogAdd
0x180054bf5  mov     [rbp+0F0h+var_140], r14b
0x180054bf9  xor     eax, eax
0x180054bfb  mov     [rbp+0F0h+var_13F], eax
0x180054bfe  mov     [rbp+0F0h+var_13B], ax
0x180054c02  mov     [rbp+0F0h+var_139], al
0x180054c05  lea     rcx, [rbp+0F0h+var_138]
0x180054c09  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180054c0e  nop
0x180054c0f  xor     edx, edx; Val
0x180054c11  mov     r8d, 80h; Size
0x180054c17  lea     rcx, [rbp+0F0h+var_118]; void *
0x180054c1b  call    memset_0
0x180054c20  mov     [rbp+0F0h+var_98], 7Bh ; '{'
0x180054c27  mov     [rbp+0F0h+var_94], 0FFFFh
0x180054c2e  mov     [rbp+0F0h+var_90], r14
0x180054c32  mov     [rbp+0F0h+var_88], r14
0x180054c36  mov     [rbp+0F0h+var_80], r14
0x180054c3a  mov     [rbp+0F0h+var_78], r14b
0x180054c3e  xor     eax, eax
0x180054c40  mov     [rbp+0F0h+var_77], eax
0x180054c43  mov     [rbp+0F0h+var_73], ax
0x180054c47  mov     [rbp+0F0h+var_71], al
0x180054c4a  mov     [rbp+0F0h+var_70], r14
0x180054c51  lea     rcx, [rbp+0F0h+var_68]
0x180054c58  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180054c5d  nop
0x180054c5e  lea     rcx, [rbp+0F0h+var_50]
0x180054c65  call    ??0?$set@V?$array@E$0CA@@std@@U?$less@V?$array@E$0CA@@std@@@2@V?$allocator@V?$array@E$0CA@@std@@@2@@std@@QEAA@XZ; std::set<std::array<uchar,32>>::set<std::array<uchar,32>>(void)
0x180054c6a  nop
0x180054c6b  mov     [rbp+0F0h+var_40], r14
0x180054c72  xor     eax, eax
0x180054c74  mov     [rbp+0F0h+var_38], rax
0x180054c7b  mov     [rbp+0F0h+var_38], r14
0x180054c82  mov     [rbp+0F0h+var_30], rax
0x180054c89  mov     [rbp+0F0h+var_30], r14
0x180054c90  mov     [rsp+1F0h+var_1C0], r14
0x180054c95  mov     [rsp+1F0h+var_1C0], 0FFFFFFFFFFFFFFFFh
0x180054c9e  lea     r8, [rbp+0F0h+var_140]
0x180054ca2  lea     rdx, [rsp+1F0h+var_1C0]
0x180054ca7  mov     rcx, rdi
0x180054caa  call    ?ConnectSocket@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEAUNtsForNtpInfoInternal@@@Z; ConnectSocket(std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> &,NtsForNtpInfoInternal &)
0x180054caf  mov     esi, eax
0x180054cb1  test    eax, eax
0x180054cb3  jns     short loc_180054D02
0x180054cb5  lea     rax, [rsp+1F0h+var_198]
0x180054cba  mov     [rsp+1F0h+var_1A8], rax
0x180054cbf  lea     rdx, aConnectsocket; "ConnectSocket"
0x180054cc6  lea     rcx, [rsp+1F0h+var_198]
0x180054ccb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180054cd0  mov     rbx, rax
0x180054cd3  lea     rax, [rsp+1F0h+var_178]
0x180054cd8  mov     [rsp+1F0h+var_1A0], rax
0x180054cdd  mov     rdx, rdi
0x180054ce0  lea     rcx, [rsp+1F0h+var_178]
0x180054ce5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180054cea  nop
0x180054ceb  lea     r9, [rbp+0F0h+var_140]
0x180054cef  mov     r8, rbx
0x180054cf2  mov     edx, esi
0x180054cf4  mov     rcx, rax
0x180054cf7  call    ?NtsKeyExchangeCallbackComplete@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J0AEAUNtsForNtpInfoInternal@@@Z; NtsKeyExchangeCallbackComplete(std::wstring,long,std::wstring,NtsForNtpInfoInternal &)
0x180054cfc  nop
0x180054cfd  jmp     loc_180054E8F
0x180054d02  mov     al, [rdi+20h]
0x180054d05  mov     [rsp+1F0h+var_1D0], al
0x180054d09  xor     r9d, r9d
0x180054d0c  lea     r8, [rbp+0F0h+var_150]
0x180054d10  mov     rdx, rdi
0x180054d13  lea     rcx, [rsp+1F0h+var_1C0]
0x180054d18  call    ?NegotiateTLS@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SecHandle@@PEAU_SecBuffer@@_N@Z; NegotiateTLS(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,std::wstring const &,_SecHandle &,_SecBuffer *,bool)
0x180054d1d  mov     esi, eax
0x180054d1f  test    eax, eax
0x180054d21  jns     short loc_180054D70
0x180054d23  lea     rax, [rsp+1F0h+var_178]
0x180054d28  mov     [rsp+1F0h+var_1A0], rax
0x180054d2d  lea     rdx, aNegotiatetls; "NegotiateTLS"
0x180054d34  lea     rcx, [rsp+1F0h+var_178]
0x180054d39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180054d3e  mov     rbx, rax
0x180054d41  lea     rax, [rsp+1F0h+var_198]
0x180054d46  mov     [rsp+1F0h+var_1A8], rax
0x180054d4b  mov     rdx, rdi
0x180054d4e  lea     rcx, [rsp+1F0h+var_198]
0x180054d53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180054d58  nop
0x180054d59  lea     r9, [rbp+0F0h+var_140]
0x180054d5d  mov     r8, rbx
0x180054d60  mov     edx, esi
0x180054d62  mov     rcx, rax
0x180054d65  call    ?NtsKeyExchangeCallbackComplete@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J0AEAUNtsForNtpInfoInternal@@@Z; NtsKeyExchangeCallbackComplete(std::wstring,long,std::wstring,NtsForNtpInfoInternal &)
0x180054d6a  nop
0x180054d6b  jmp     loc_180054E8F
0x180054d70  cmp     [rdi+20h], r14b
0x180054d74  jz      short loc_180054DF0
0x180054d76  mov     ecx, 0C8h
0x180054d7b  call    FileLogAllowEntry
0x180054d80  test    al, al
0x180054d82  jz      short loc_180054D90
0x180054d84  lea     rcx, aNtskeyexchange_2; "NtsKeyExchangeCallback: Attempting to v"...
0x180054d8b  call    FileLogAdd
0x180054d90  lea     rdx, [rdi+21h]
0x180054d94  lea     rcx, [rbp+0F0h+var_150]
0x180054d98  call    ?ManualCertValidation@@YAJAEAU_SecHandle@@AEBV?$array@E$0BE@@std@@@Z; ManualCertValidation(_SecHandle &,std::array<uchar,20> const &)
0x180054d9d  mov     esi, eax
0x180054d9f  test    eax, eax
0x180054da1  jns     short loc_180054DF0
0x180054da3  lea     rax, [rsp+1F0h+var_178]
0x180054da8  mov     [rsp+1F0h+var_1A0], rax
0x180054dad  lea     rdx, aManualcertvali_0; "ManualCertValidation"
0x180054db4  lea     rcx, [rsp+1F0h+var_178]
0x180054db9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180054dbe  mov     rbx, rax
0x180054dc1  lea     rax, [rsp+1F0h+var_198]
0x180054dc6  mov     [rsp+1F0h+var_1A8], rax
0x180054dcb  mov     rdx, rdi
0x180054dce  lea     rcx, [rsp+1F0h+var_198]
0x180054dd3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180054dd8  nop
0x180054dd9  lea     r9, [rbp+0F0h+var_140]
0x180054ddd  mov     r8, rbx
0x180054de0  mov     edx, esi
0x180054de2  mov     rcx, rax
0x180054de5  call    ?NtsKeyExchangeCallbackComplete@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J0AEAUNtsForNtpInfoInternal@@@Z; NtsKeyExchangeCallbackComplete(std::wstring,long,std::wstring,NtsForNtpInfoInternal &)
0x180054dea  nop
0x180054deb  jmp     loc_180054E8F
0x180054df0  lea     r9, [rdi+38h]
0x180054df4  lea     r8, [rbp+0F0h+var_140]
0x180054df8  lea     rdx, [rbp+0F0h+var_150]
0x180054dfc  lea     rcx, [rsp+1F0h+var_1C0]
0x180054e01  call    ?DoNtsKeyExchange@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEAU_SecHandle@@AEAUNtsForNtpInfoInternal@@AEBV?$vector@GV?$allocator@G@std@@@std@@@Z; DoNtsKeyExchange(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,_SecHandle &,NtsForNtpInfoInternal &,std::vector<ushort> const &)
0x180054e06  mov     esi, eax
0x180054e08  lea     rcx, [rsp+1F0h+var_178]
0x180054e0d  test    eax, eax
0x180054e0f  lea     rax, [rsp+1F0h+var_178]
0x180054e14  mov     [rsp+1F0h+var_1A0], rax
0x180054e19  jns     short loc_180054E56
0x180054e1b  lea     rdx, aDontskeyexchan; "DoNtsKeyExchange"
0x180054e22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180054e27  mov     rbx, rax
0x180054e2a  lea     rax, [rsp+1F0h+var_198]
0x180054e2f  mov     [rsp+1F0h+var_1A8], rax
0x180054e34  mov     rdx, rdi
0x180054e37  lea     rcx, [rsp+1F0h+var_198]
0x180054e3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180054e41  nop
0x180054e42  lea     r9, [rbp+0F0h+var_140]
0x180054e46  mov     r8, rbx
0x180054e49  mov     edx, esi
0x180054e4b  mov     rcx, rax
0x180054e4e  call    ?NtsKeyExchangeCallbackComplete@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J0AEAUNtsForNtpInfoInternal@@@Z; NtsKeyExchangeCallbackComplete(std::wstring,long,std::wstring,NtsForNtpInfoInternal &)
0x180054e53  nop
0x180054e54  jmp     short loc_180054E8F
0x180054e56  lea     rdx, qword_180071478
0x180054e5d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180054e62  mov     rbx, rax
0x180054e65  lea     rax, [rsp+1F0h+var_198]
0x180054e6a  mov     [rsp+1F0h+var_1A8], rax
0x180054e6f  mov     rdx, rdi
0x180054e72  lea     rcx, [rsp+1F0h+var_198]
0x180054e77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180054e7c  nop
0x180054e7d  lea     r9, [rbp+0F0h+var_140]
0x180054e81  mov     r8, rbx
0x180054e84  mov     edx, esi
0x180054e86  mov     rcx, rax
0x180054e89  call    ?NtsKeyExchangeCallbackComplete@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J0AEAUNtsForNtpInfoInternal@@@Z; NtsKeyExchangeCallbackComplete(std::wstring,long,std::wstring,NtsForNtpInfoInternal &)
0x180054e8e  nop
0x180054e8f  lea     rcx, [rsp+1F0h+var_1C0]
0x180054e94  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>(void)
0x180054e99  nop
0x180054e9a  lea     rcx, [rbp+0F0h+var_140]; this
0x180054e9e  call    ??1NtsForNtpInfoInternal@@QEAA@XZ; NtsForNtpInfoInternal::~NtsForNtpInfoInternal(void)
0x180054ea3  nop
0x180054ea4  cmp     [rsp+1F0h+var_1B0], r14b
0x180054ea9  jz      short loc_180054ECC
0x180054eab  mov     rcx, [rsp+1F0h+phContext]; phContext
0x180054eb0  mov     [rsp+1F0h+var_1B0], r14b
0x180054eb5  cmp     [rcx], r14
0x180054eb8  jnz     short loc_180054EC0
0x180054eba  cmp     [rcx+8], r14
0x180054ebe  jz      short loc_180054ECC
0x180054ec0  call    cs:__imp_DeleteSecurityContext
0x180054ec7  nop     dword ptr [rax+rax+00h]
0x180054ecc  mov     rcx, [rbp+0F0h+var_20]
0x180054ed3  xor     rcx, rsp; StackCookie
0x180054ed6  call    __security_check_cookie
0x180054edb  lea     r11, [rsp+1F0h+var_10]
0x180054ee3  mov     rbx, [r11+20h]
0x180054ee7  mov     rsi, [r11+30h]
0x180054eeb  mov     rsp, r11
0x180054eee  pop     r14
0x180054ef0  pop     rdi
0x180054ef1  pop     rbp
0x180054ef2  retn
```
