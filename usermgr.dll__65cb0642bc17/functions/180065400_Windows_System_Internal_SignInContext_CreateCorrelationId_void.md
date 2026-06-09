# Windows::System::Internal::SignInContext::CreateCorrelationId(void)

- ea: `0x180065400`
- end: `0x18006553c`
- name: `?CreateCorrelationId@SignInContext@Internal@System@Windows@@EEAAJXZ`
- size: `316`
- prototype: `__int64 __fastcall(Windows::System::Internal::SignInContext *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000acdc`
- `0x1800181f0`
- `0x1800189b0`
- `0x180019060`
- `0x180065400`
- `0x180065544`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180065463`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180065463`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180065438`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180065438`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800654b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800654b9`

## string_xrefs

- `0x180065446`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x180065471`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`
- `0x1800654fb`: `onecore\ds\security\umstartup\usermgr\lib\signincontext.cpp`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::SignInContext::CreateCorrelationId(
        Windows::System::Internal::SignInContext *this)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  const WCHAR *v4; // rsi
  unsigned __int64 v5; // rcx
  signed int v6; // eax
  __int64 (__fastcall *v7)(char *, __int64); // rbx
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v11; // [rsp+20h] [rbp-50h] BYREF
  LPOLESTR lpsz; // [rsp+28h] [rbp-48h] BYREF
  GUID pguid; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  pguid = 0;
  lpsz = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
      (const char *)(unsigned int)v2,
      v11);
  v3 = StringFromCLSID(&pguid, &lpsz);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
      (const char *)(unsigned int)v3,
      v11);
  v4 = lpsz;
  v5 = -1;
  v15 = 0;
  v11 = 0;
  do
    ++v5;
  while ( lpsz[v5] );
  v6 = ULongLongToUInt(v5, &v11);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  v7 = *(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this + 2) + 56LL);
  v8 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v4, v8, v11);
  v9 = v7((char *)this + 16, v15);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\signincontext.cpp",
      (const char *)(unsigned int)v9,
      v11);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpsz);
  return 0;
}

```

## disassembly

```asm
0x180065400  mov     [rsp-18h+arg_8], rbx
0x180065405  mov     [rsp-18h+arg_10], rsi
0x18006540a  push    rbp
0x18006540b  push    rdi
0x18006540c  push    r14
0x18006540e  mov     rbp, rsp
0x180065411  sub     rsp, 70h
0x180065415  mov     rax, cs:__security_cookie
0x18006541c  xor     rax, rsp
0x18006541f  mov     [rbp+var_10], rax
0x180065423  mov     rdi, rcx
0x180065426  xorps   xmm0, xmm0
0x180065429  xor     r14d, r14d
0x18006542c  lea     rcx, [rbp+pguid]; pguid
0x180065430  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x180065434  mov     [rbp+lpsz], r14
0x180065438  call    cs:__imp_CoCreateGuid
0x18006543e  test    eax, eax
0x180065440  jns     short loc_18006545B
0x180065442  mov     rcx, [rbp+18h]; this
0x180065446  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x18006544d  mov     r9d, eax; char *
0x180065450  mov     edx, 0F8h; void *
0x180065455  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006545b  lea     rdx, [rbp+lpsz]; lplpsz
0x18006545f  lea     rcx, [rbp+pguid]; rclsid
0x180065463  call    cs:__imp_StringFromCLSID
0x180065469  test    eax, eax
0x18006546b  jns     short loc_180065486
0x18006546d  mov     rcx, [rbp+18h]; this
0x180065471  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x180065478  mov     r9d, eax; char *
0x18006547b  mov     edx, 0F9h; void *
0x180065480  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065486  mov     rsi, [rbp+lpsz]
0x18006548a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006548e  mov     [rbp+var_18], r14
0x180065492  mov     [rbp+var_50], r14d
0x180065496  inc     rcx; unsigned __int64
0x180065499  cmp     [rsi+rcx*2], r14w
0x18006549e  jnz     short loc_180065496
0x1800654a0  lea     rdx, [rbp+var_50]; unsigned int *
0x1800654a4  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800654a9  test    eax, eax
0x1800654ab  jns     short loc_1800654C0
0x1800654ad  xor     r9d, r9d; lpArguments
0x1800654b0  xor     r8d, r8d; nNumberOfArguments
0x1800654b3  mov     ecx, eax; dwExceptionCode
0x1800654b5  lea     edx, [r9+1]; dwExceptionFlags
0x1800654b9  call    cs:__imp_RaiseException
0x1800654bf  int     3; Trap to Debugger
0x1800654c0  mov     rax, [rdi+10h]
0x1800654c4  mov     ecx, [rbp+var_50]; unsigned int
0x1800654c7  mov     rbx, [rax+38h]
0x1800654cb  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800654d0  mov     r9d, [rbp+var_50]; unsigned int
0x1800654d4  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800654d8  mov     r8d, eax; unsigned int
0x1800654db  mov     rdx, rsi; sourceString
0x1800654de  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800654e3  mov     rdx, [rbp+var_18]
0x1800654e7  lea     rcx, [rdi+10h]
0x1800654eb  mov     rax, rbx
0x1800654ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654f3  test    eax, eax
0x1800654f5  jns     short loc_180065510
0x1800654f7  mov     rcx, [rbp+18h]; this
0x1800654fb  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\umstartup\\userm"...
0x180065502  mov     r9d, eax; char *
0x180065505  mov     edx, 0FAh; void *
0x18006550a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065510  lea     rcx, [rbp+lpsz]
0x180065514  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180065519  xor     eax, eax
0x18006551b  mov     rcx, [rbp+var_10]
0x18006551f  xor     rcx, rsp; StackCookie
0x180065522  call    __security_check_cookie
0x180065527  lea     r11, [rsp+70h+var_s0]
0x18006552c  mov     rbx, [r11+28h]
0x180065530  mov     rsi, [r11+30h]
0x180065534  mov     rsp, r11
0x180065537  pop     r14
0x180065539  pop     rdi
0x18006553a  pop     rbp
0x18006553b  retn
```
