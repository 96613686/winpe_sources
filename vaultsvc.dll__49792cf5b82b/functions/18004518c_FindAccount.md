# _FindAccount

- ea: `0x18004518c`
- end: `0x180045437`
- name: `_FindAccount`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020030`

## callees

- `0x18001cea8`
- `0x18003178c`
- `0x180038c6c`
- `0x18003a580`
- `0x180041b3c`
- `0x18004249c`
- `0x180042638`
- `0x18004518c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180045203`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180045203`

## string_xrefs

- `0x180045216`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x180045375`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x1800453e4`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x1800451e4`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall FindAccount(int a1, __int64 a2, __int64 a3)
{
  int ActivationFactory; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64, __int64 *); // r14
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, _QWORD, __int64 *); // rbx
  __int64 v19; // rax
  int v20; // eax
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rdi
  int v25; // [rsp+20h] [rbp-79h]
  __int64 v26; // [rsp+30h] [rbp-69h] BYREF
  __int64 v27; // [rsp+38h] [rbp-61h] BYREF
  __int64 v28; // [rsp+40h] [rbp-59h] BYREF
  int v29; // [rsp+48h] [rbp-51h]
  __int64 v30; // [rsp+50h] [rbp-49h] BYREF
  __int64 v31; // [rsp+58h] [rbp-41h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-39h] BYREF
  __int64 v33; // [rsp+78h] [rbp-21h]
  _BYTE v34[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v35[32]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v31 = a2;
  v29 = 0;
  v28 = 0;
  v30 = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  ActivationFactory = RoGetActivationFactory(v33, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v30);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v26 = 0;
    v7 = v30;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v30 + 96LL);
    v26 = 0;
    if ( a1 == 5 )
    {
      v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_18005F100);
      v29 = 1;
    }
    else
    {
      v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v35, off_18005F0F8);
      v29 = 2;
    }
    v10 = *(_QWORD *)(v9 + 24);
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v34, off_18005F108);
    v12 = v8(v7, *(_QWORD *)(v11 + 24), v10, &v26);
    v6 = v12;
    if ( v12 >= 0 )
    {
      v15 = v28;
      v28 = 0;
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v16 = v26;
      v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(v26);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, &v28);
        if ( v6 >= 0 )
        {
          if ( !v28 )
          {
            wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v26);
            v6 = -2146893805;
            goto LABEL_24;
          }
          v27 = 0;
          v17 = v30;
          v18 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 80LL);
          v27 = 0;
          v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v34, &v31);
          v20 = v18(v17, v28, *(_QWORD *)(v19 + 24), &v27);
          v6 = v20;
          if ( v20 >= 0 )
          {
            v23 = v27;
            v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(v27);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 64LL))(v23, a3);
              if ( v6 >= 0 )
              {
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v27);
                wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v26);
                v6 = 0;
                goto LABEL_24;
              }
            }
            v21 = (unsigned int)v6;
            v22 = 116;
          }
          else
          {
            v21 = (unsigned int)v20;
            v22 = 115;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
            (const char *)v21,
            v25);
          wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v27);
LABEL_23:
          wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v26);
          goto LABEL_24;
        }
      }
      v13 = (unsigned int)v6;
      v14 = 108;
    }
    else
    {
      v13 = (unsigned int)v12;
      v14 = 107;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
      (const char *)v13,
      v25);
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x65,
    (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v25);
LABEL_24:
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v30);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v28);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004518c  mov     [rsp-8+arg_0], rbx
0x180045191  push    rbp
0x180045192  push    rsi
0x180045193  push    rdi
0x180045194  push    r14
0x180045196  push    r15
0x180045198  lea     rbp, [rsp-37h]
0x18004519d  sub     rsp, 0D0h
0x1800451a4  mov     rax, cs:__security_cookie
0x1800451ab  xor     rax, rsp
0x1800451ae  mov     [rbp+57h+var_30], rax
0x1800451b2  mov     r15, r8
0x1800451b5  mov     esi, ecx
0x1800451b7  mov     [rbp+57h+var_98], rdx
0x1800451bb  mov     [rbp+57h+var_A8], 0
0x1800451c2  mov     [rbp+57h+var_B0], 0
0x1800451ca  mov     [rbp+57h+var_A0], 0
0x1800451d2  mov     [rbp+57h+var_78], 0
0x1800451da  mov     r9d, 45h ; 'E'; unsigned int
0x1800451e0  lea     r8d, [r9+1]; unsigned int
0x1800451e4  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800451eb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800451ef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800451f4  lea     r8, [rbp+57h+var_A0]
0x1800451f8  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x1800451ff  mov     rcx, [rbp+57h+var_78]
0x180045203  call    cs:__imp_RoGetActivationFactory
0x180045209  mov     ebx, eax
0x18004520b  test    eax, eax
0x18004520d  jns     short loc_18004522C
0x18004520f  mov     rcx, [rbp+5Fh]; this
0x180045213  mov     r9d, eax; char *
0x180045216  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18004521d  mov     edx, 65h ; 'e'; void *
0x180045222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045227  jmp     loc_1800453FF
0x18004522c  mov     [rbp+57h+var_C0], 0
0x180045234  mov     rdi, [rbp+57h+var_A0]
0x180045238  mov     rax, [rdi]
0x18004523b  mov     r14, [rax+60h]
0x18004523f  mov     [rbp+57h+var_C0], 0
0x180045247  cmp     esi, 5
0x18004524a  jnz     short loc_180045266
0x18004524c  lea     rdx, off_18005F100; "consumers"
0x180045253  lea     rcx, [rbp+57h+hstringHeader]
0x180045257  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004525c  nop
0x18004525d  mov     [rbp+57h+var_A8], 1
0x180045264  jmp     short loc_18004527E
0x180045266  lea     rdx, off_18005F0F8; "organizations"
0x18004526d  lea     rcx, [rbp+57h+var_50]
0x180045271  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180045276  nop
0x180045277  mov     [rbp+57h+var_A8], 2
0x18004527e  mov     rbx, [rax+18h]
0x180045282  lea     rdx, off_18005F108; "https://login.microsoft.com"
0x180045289  lea     rcx, [rbp+57h+var_70]
0x18004528d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180045292  nop
0x180045293  lea     r9, [rbp+57h+var_C0]
0x180045297  mov     r8, rbx
0x18004529a  mov     rdx, [rax+18h]
0x18004529e  mov     rcx, rdi
0x1800452a1  mov     rax, r14
0x1800452a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452a9  mov     ebx, eax
0x1800452ab  test    eax, eax
0x1800452ad  jns     short loc_1800452BC
0x1800452af  mov     r9d, eax
0x1800452b2  mov     edx, 6Bh ; 'k'
0x1800452b7  jmp     loc_1800453E4
0x1800452bc  mov     rcx, [rbp+57h+var_B0]
0x1800452c0  mov     [rbp+57h+var_B0], 0
0x1800452c8  test    rcx, rcx
0x1800452cb  jz      short loc_1800452DA
0x1800452cd  mov     rax, [rcx]
0x1800452d0  mov     rax, [rax+10h]
0x1800452d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452d9  nop
0x1800452da  mov     rdi, [rbp+57h+var_C0]
0x1800452de  mov     rcx, rdi
0x1800452e1  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x1800452e6  mov     ebx, eax
0x1800452e8  test    eax, eax
0x1800452ea  js      loc_1800453DC
0x1800452f0  mov     rax, [rdi]
0x1800452f3  lea     rdx, [rbp+57h+var_B0]
0x1800452f7  mov     rcx, rdi
0x1800452fa  mov     rax, [rax+40h]
0x1800452fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045303  mov     ebx, eax
0x180045305  test    eax, eax
0x180045307  js      loc_1800453DC
0x18004530d  cmp     [rbp+57h+var_B0], 0
0x180045312  jnz     short loc_180045327
0x180045314  lea     rcx, [rbp+57h+var_C0]
0x180045318  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x18004531d  mov     ebx, 80090013h
0x180045322  jmp     loc_1800453FF
0x180045327  mov     [rbp+57h+var_B8], 0
0x18004532f  mov     rdi, [rbp+57h+var_A0]
0x180045333  mov     rax, [rdi]
0x180045336  mov     rbx, [rax+50h]
0x18004533a  mov     [rbp+57h+var_B8], 0
0x180045342  lea     rdx, [rbp+57h+var_98]
0x180045346  lea     rcx, [rbp+57h+var_70]
0x18004534a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004534f  nop
0x180045350  lea     r9, [rbp+57h+var_B8]
0x180045354  mov     r8, [rax+18h]
0x180045358  mov     rdx, [rbp+57h+var_B0]
0x18004535c  mov     rcx, rdi
0x18004535f  mov     rax, rbx
0x180045362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045367  mov     ebx, eax
0x180045369  test    eax, eax
0x18004536b  jns     short loc_180045391
0x18004536d  mov     r9d, eax; char *
0x180045370  mov     edx, 73h ; 's'; void *
0x180045375  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18004537c  mov     rcx, [rbp+5Fh]; this
0x180045380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045385  nop
0x180045386  lea     rcx, [rbp+57h+var_B8]
0x18004538a  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x18004538f  jmp     short loc_1800453F5
0x180045391  mov     rdi, [rbp+57h+var_B8]
0x180045395  mov     rcx, rdi
0x180045398  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)
0x18004539d  mov     ebx, eax
0x18004539f  test    eax, eax
0x1800453a1  js      short loc_1800453D2
0x1800453a3  mov     rax, [rdi]
0x1800453a6  mov     rdx, r15
0x1800453a9  mov     rcx, rdi
0x1800453ac  mov     rax, [rax+40h]
0x1800453b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453b5  mov     ebx, eax
0x1800453b7  test    eax, eax
0x1800453b9  js      short loc_1800453D2
0x1800453bb  lea     rcx, [rbp+57h+var_B8]
0x1800453bf  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x1800453c4  nop
0x1800453c5  lea     rcx, [rbp+57h+var_C0]
0x1800453c9  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x1800453ce  xor     ebx, ebx
0x1800453d0  jmp     short loc_1800453FF
0x1800453d2  mov     r9d, ebx
0x1800453d5  mov     edx, 74h ; 't'
0x1800453da  jmp     short loc_180045375
0x1800453dc  mov     r9d, ebx; char *
0x1800453df  mov     edx, 6Ch ; 'l'; void *
0x1800453e4  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x1800453eb  mov     rcx, [rbp+5Fh]; this
0x1800453ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800453f4  nop
0x1800453f5  lea     rcx, [rbp+57h+var_C0]
0x1800453f9  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x1800453fe  nop
0x1800453ff  lea     rcx, [rbp+57h+var_A0]
0x180045403  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x180045408  nop
0x180045409  lea     rcx, [rbp+57h+var_B0]
0x18004540d  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x180045412  mov     eax, ebx
0x180045414  mov     rcx, [rbp+57h+var_30]
0x180045418  xor     rcx, rsp; StackCookie
0x18004541b  call    __security_check_cookie
0x180045420  mov     rbx, [rsp+0F0h+arg_0]
0x180045428  add     rsp, 0D0h
0x18004542f  pop     r15
0x180045431  pop     r14
0x180045433  pop     rdi
0x180045434  pop     rsi
0x180045435  pop     rbp
0x180045436  retn
```
