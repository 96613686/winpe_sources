# CRequestQueue::LookUpDocStore(IDBProperties *,ICiCDocStore * *,TLMString<32,32,1024> &,TLMString<32,32,1024> &,void *)

- ea: `0x18008f4c8`
- end: `0x18008fa84`
- name: `?LookUpDocStore@CRequestQueue@@QEAAJPEAUIDBProperties@@PEAPEAUICiCDocStore@@AEAV?$TLMString@$0CA@$0CA@$0EAA@@@2PEAX@Z`
- size: `1468`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008ddb0`

## callees

- `0x180038f08`
- `0x180078410`
- `0x18008a284`
- `0x18008f4c8`
- `0x18008fa8c`
- `0x18008facc`
- `0x1800983c0`
- `0x1800f4820`
- `0x1800fea64`
- `0x180147190`
- `0x180177de8`
- `0x180188d90`
- `0x18018a123`
- `0x18019b924`
- `0x1801f0b3c`
- `0x180202680`
- `0x18029437c`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18008f5ef`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18008f5ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f733`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f733`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f748`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18008f748`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008f6c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008f6c9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008f85a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008f85a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008f8cf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008f8cf`
- `OLEAUT32!__imp_VariantClear` at `0x18008f7eb`
- `OLEAUT32!__imp_VariantClear` at `0x18008f7eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008f875`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008f875`

## string_xrefs

- `0x18008f99d`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x18008f9bc`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x18008f76e`: `onecoreuap\base\appmodel\Search\common\include\usersidhelper.h`
- `0x1802bae75`: `onecoreuap\base\appmodel\Search\common\include\usersidhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRequestQueue::LookUpDocStore(__int64 a1, __int64 a2, __int64 a3, __int64 a4, void *a5, WCHAR *a6)
{
  void *v7; // rdi
  VARIANTARG *v8; // rbx
  VARIANTARG *v9; // rsi
  LONGLONG llVal; // rdx
  __int64 v11; // r13
  int i; // r14d
  unsigned int v13; // r14d
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rdx
  __int64 v16; // r9
  unsigned __int64 v17; // rcx
  _QWORD *v18; // r13
  void **v19; // r14
  HANDLE CurrentThread; // rax
  int v21; // eax
  int Error; // r14d
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  const char *v25; // r9
  int v26; // eax
  unsigned int v27; // r14d
  __int64 v29; // rdx
  int ReturnLength; // [rsp+20h] [rbp-118h]
  LPVOID *ReturnLengtha; // [rsp+20h] [rbp-118h]
  int v32; // [rsp+30h] [rbp-108h] BYREF
  DWORD v33; // [rsp+34h] [rbp-104h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-100h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-F8h] BYREF
  int v36; // [rsp+48h] [rbp-F0h] BYREF
  int v37; // [rsp+4Ch] [rbp-ECh] BYREF
  LPVOID pv; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v39; // [rsp+58h] [rbp-E0h]
  __int64 v40; // [rsp+60h] [rbp-D8h]
  LPVOID v41; // [rsp+68h] [rbp-D0h]
  VARIANTARG *v42; // [rsp+70h] [rbp-C8h]
  VARIANTARG *v43; // [rsp+78h] [rbp-C0h]
  int *v44; // [rsp+80h] [rbp-B8h] BYREF
  int v45; // [rsp+88h] [rbp-B0h]
  GUID v46; // [rsp+8Ch] [rbp-ACh]
  int v47; // [rsp+9Ch] [rbp-9Ch]
  PSID TokenInformation[10]; // [rsp+A0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v40 = a3;
  v39 = a1;
  TokenHandle = a5;
  StringSid = a6;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19A4,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0x80070057LL,
      ReturnLength);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19A9,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0x80004003LL,
      ReturnLength);
    return 2147500035LL;
  }
  v36 = 2;
  v47 = 0;
  v44 = &v36;
  v45 = 1;
  v46 = guidCiFsExt;
  pv = 0;
  v37 = 0;
  ReturnLengtha = &pv;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64, int **, int *))(*(_QWORD *)a2 + 24LL))(a2, 1, &v44, &v37) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19BD,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0x80070057LL,
      (int)&pv);
  v7 = pv;
  v8 = *(VARIANTARG **)pv;
  v9 = (VARIANTARG *)(*(_QWORD *)pv + 48LL);
  if ( v9->vt == 8 )
  {
    llVal = v8[2].llVal;
  }
  else
  {
    llVal = 0;
    if ( v9->vt == 8200 )
      llVal = **(_QWORD **)(v8[2].llVal + 16);
  }
  v41 = pv;
  v42 = v8;
  v43 = v9;
  CLMString::operator=(a4, llVal);
  v11 = *(_QWORD *)(a4 + 8);
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a4 + 20); ++i )
  {
    if ( wcschr(L"{}", *(_WORD *)(v11 + 2LL * (unsigned int)i)) )
    {
      if ( i >= 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x19E0,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
          (const char *)0x80070057LL,
          (int)&pv);
      break;
    }
  }
  v13 = CLMString::Find((CLMString *)a4, 0x5Cu, 0);
  if ( (int)v13 <= 0 || (v14 = *(unsigned int *)(a4 + 20), v13 >= (int)v14 - 1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A08,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)0x80070057LL,
      (int)&pv);
  v15 = v13 + 1;
  v16 = (unsigned int)(v14 - v15);
  v17 = v15 + v16;
  if ( v15 + v16 < v15 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17, v15, v15, v16, &pv);
  if ( v17 > v14 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      (unsigned int)&pv);
  v18 = TokenHandle;
  (*(void (__fastcall **)(HANDLE, unsigned __int64, _QWORD, __int64))(*(_QWORD *)TokenHandle + 32LL))(
    TokenHandle,
    *(_QWORD *)(a4 + 8) + 2 * v15,
    0,
    v16);
  if ( v13 > *(_DWORD *)(a4 + 20) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      (unsigned int)&pv);
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a4 + 32LL))(a4, *(_QWORD *)(a4 + 8), 0, v13);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && !wcscmp_0(*(const wchar_t **)(a4 + 8), L"Windows") )
  {
    v32 = 0;
    if ( *(_QWORD *)(v39 + 408) && *(_QWORD *)(v39 + 424) )
      XPipeImpersonation::ImpersonateUserToken((XPipeImpersonation *)&v32, *(void **)(v39 + 424));
    else
      XPipeImpersonation::Impersonate((XPipeImpersonation *)&v32, StringSid);
    TokenHandle = 0;
    StringSid = 0;
    v19 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&TokenHandle);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, v19) || (v21 = ResultFromKnownLastError(), Error = v21, v21 >= 0) )
    {
      v33 = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x44u, &v33)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          Error = 0;
          goto LABEL_25;
        }
        v29 = 18;
      }
      else
      {
        v29 = 16;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\usersidhelper.h",
        (const char *)(unsigned int)Error,
        (int)ReturnLengtha);
      v23 = (unsigned int)Error;
      v24 = 38;
    }
    else
    {
      v23 = (unsigned int)v21;
      v24 = 37;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\usersidhelper.h",
      (const char *)v23,
      (int)ReturnLengtha);
LABEL_25:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( Error < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19FA,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        (const char *)(unsigned int)Error,
        (int)ReturnLengtha);
    if ( !StringSid )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x19FB,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        v25);
    *(_DWORD *)(a4 + 20) = 0;
    **(_WORD **)(a4 + 8) = 0;
    CLMString::operator=(a4, StringSid);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&StringSid);
    if ( v32 )
      RevertToSelf();
  }
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(v39 + 192) + 32LL))(
          *(_QWORD *)(v39 + 192),
          v18[1],
          *(_QWORD *)(a4 + 8),
          v40);
  v27 = v26;
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A0E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v26,
      (int)ReturnLengtha);
  if ( v9 )
    VariantClear(v9);
  if ( v8 )
    CoTaskMemFree_0(v8);
  if ( v7 )
    CoTaskMemFree_0(v7);
  return v27;
}

```

## disassembly

```asm
0x18008f4c8  push    rbx
0x18008f4ca  push    rsi
0x18008f4cb  push    rdi
0x18008f4cc  push    r12
0x18008f4ce  push    r13
0x18008f4d0  push    r14
0x18008f4d2  push    r15
0x18008f4d4  sub     rsp, 100h
0x18008f4db  mov     rax, cs:__security_cookie
0x18008f4e2  xor     rax, rsp
0x18008f4e5  mov     [rsp+138h+var_48], rax
0x18008f4ed  mov     r12, r9
0x18008f4f0  mov     [rsp+138h+var_D8], r8
0x18008f4f5  mov     r10, rdx
0x18008f4f8  mov     [rsp+138h+var_E0], rcx
0x18008f4fd  mov     rax, [rsp+138h+arg_20]
0x18008f505  mov     [rsp+138h+TokenHandle], rax
0x18008f50a  mov     rax, [rsp+138h+arg_28]
0x18008f512  mov     [rsp+138h+StringSid], rax
0x18008f517  xor     r15d, r15d
0x18008f51a  test    rdx, rdx
0x18008f51d  jz      loc_18008F8DA
0x18008f523  test    r8, r8
0x18008f526  jz      loc_18008F903
0x18008f52c  mov     [rsp+138h+var_F0], 2
0x18008f534  mov     [rsp+138h+var_9C], r15d
0x18008f53c  lea     rax, [rsp+138h+var_F0]
0x18008f541  mov     [rsp+138h+var_B8], rax
0x18008f549  lea     edx, [r15+1]
0x18008f54d  mov     [rsp+138h+var_B0], edx
0x18008f554  movups  xmm0, xmmword ptr cs:?guidCiFsExt@@3U_GUID@@B.Data1; _GUID const guidCiFsExt ...
0x18008f55b  movdqu  [rsp+138h+var_AC], xmm0
0x18008f564  mov     [rsp+138h+pv], r15
0x18008f569  mov     [rsp+138h+var_EC], r15d
0x18008f56e  mov     rax, [r10]
0x18008f571  lea     rcx, [rsp+138h+pv]
0x18008f576  mov     [rsp+138h+ReturnLength], rcx; int
0x18008f57b  lea     r9, [rsp+138h+var_EC]
0x18008f580  lea     r8, [rsp+138h+var_B8]
0x18008f588  mov     rcx, r10
0x18008f58b  mov     rax, [rax+18h]
0x18008f58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f594  test    eax, eax
0x18008f596  jnz     loc_18008F92B
0x18008f59c  mov     rdi, [rsp+138h+pv]
0x18008f5a1  mov     rbx, [rdi]
0x18008f5a4  lea     rsi, [rbx+30h]
0x18008f5a8  lea     eax, [r15+8]
0x18008f5ac  cmp     ax, [rsi]
0x18008f5af  jnz     loc_18008F94A
0x18008f5b5  mov     rdx, [rbx+38h]
0x18008f5b9  mov     [rsp+138h+var_D0], rdi
0x18008f5be  mov     [rsp+138h+var_C8], rbx
0x18008f5c3  mov     [rsp+138h+var_C0], rsi
0x18008f5c8  mov     rcx, r12
0x18008f5cb  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18008f5d0  mov     r13, [r12+8]
0x18008f5d5  mov     r14d, r15d
0x18008f5d8  cmp     r14d, [r12+14h]
0x18008f5dd  jnb     short loc_18008F608
0x18008f5df  mov     edx, r14d
0x18008f5e2  movzx   edx, word ptr [r13+rdx*2+0]; Ch
0x18008f5e8  lea     rcx, Str; "{}"
0x18008f5ef  call    cs:__imp_wcschr
0x18008f5f5  test    rax, rax
0x18008f5f8  jnz     short loc_18008F5FF
0x18008f5fa  inc     r14d
0x18008f5fd  jmp     short loc_18008F5D8
0x18008f5ff  test    r14d, r14d
0x18008f602  jns     loc_18008F96B
0x18008f608  mov     edx, 5Ch ; '\'; wchar_t
0x18008f60d  xor     r8d, r8d; unsigned int
0x18008f610  mov     rcx, r12; this
0x18008f613  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x18008f618  mov     r14d, eax
0x18008f61b  test    eax, eax
0x18008f61d  jg      short loc_18008F63E
0x18008f61f  mov     rcx, [rsp+138h]; this
0x18008f627  mov     r9d, 80070057h; char *
0x18008f62d  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008f634  mov     edx, 1A08h; void *
0x18008f639  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008f63e  mov     eax, [r12+14h]
0x18008f643  lea     ecx, [rax-1]
0x18008f646  cmp     r14d, ecx
0x18008f649  jnb     short loc_18008F61F
0x18008f64b  lea     edx, [r14+1]
0x18008f64f  mov     ecx, eax
0x18008f651  sub     ecx, edx
0x18008f653  mov     r9d, ecx
0x18008f656  mov     r8d, edx
0x18008f659  add     rcx, rdx
0x18008f65c  cmp     rcx, r8
0x18008f65f  jb      loc_18008F98A
0x18008f665  cmp     rcx, rax
0x18008f668  ja      loc_18008F98F
0x18008f66e  mov     r13, [rsp+138h+TokenHandle]
0x18008f673  mov     rcx, [r13+0]
0x18008f677  mov     rax, [r12+8]
0x18008f67c  lea     rdx, [rax+rdx*2]
0x18008f680  mov     rax, [rcx+20h]
0x18008f684  xor     r8d, r8d
0x18008f687  mov     rcx, r13
0x18008f68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f68f  cmp     r14d, [r12+14h]
0x18008f694  ja      loc_18008F9AE
0x18008f69a  mov     rax, [r12]
0x18008f69e  mov     r9d, r14d
0x18008f6a1  xor     r8d, r8d
0x18008f6a4  mov     rdx, [r12+8]
0x18008f6a9  mov     rcx, r12
0x18008f6ac  mov     rax, [rax+20h]
0x18008f6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f6b5  xor     r9d, r9d; Context
0x18008f6b8  xor     r8d, r8d; Parameter
0x18008f6bb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18008f6c2  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18008f6c9  call    cs:__imp_InitOnceExecuteOnce
0x18008f6cf  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, r15b; bool g_isPerUserCatalogEnabled
0x18008f6d6  jz      loc_18008F7B2
0x18008f6dc  lea     rdx, aWindows; "Windows"
0x18008f6e3  mov     rcx, [r12+8]; String1
0x18008f6e8  call    wcscmp_0
0x18008f6ed  test    eax, eax
0x18008f6ef  jnz     loc_18008F7B2
0x18008f6f5  mov     [rsp+138h+var_108], r15d
0x18008f6fa  mov     rax, [rsp+138h+var_E0]
0x18008f6ff  cmp     [rax+198h], r15
0x18008f706  jnz     loc_18008F9CE
0x18008f70c  mov     rdx, [rsp+138h+StringSid]; void *
0x18008f711  lea     rcx, [rsp+138h+var_108]; this
0x18008f716  call    ?Impersonate@XPipeImpersonation@@QEAAXPEAX@Z; XPipeImpersonation::Impersonate(void *)
0x18008f71b  nop
0x18008f71c  mov     [rsp+138h+TokenHandle], r15
0x18008f721  mov     [rsp+138h+StringSid], r15
0x18008f726  lea     rcx, [rsp+138h+TokenHandle]
0x18008f72b  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18008f730  mov     r14, rax
0x18008f733  call    cs:__imp_GetCurrentThread
0x18008f739  mov     r9, r14; TokenHandle
0x18008f73c  mov     edx, 8; DesiredAccess
0x18008f741  lea     r8d, [rdx-7]; OpenAsSelf
0x18008f745  mov     rcx, rax; ThreadHandle
0x18008f748  call    cs:__imp_OpenThreadToken
0x18008f74e  test    eax, eax
0x18008f750  jnz     loc_18008F834
0x18008f756  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008f75b  mov     r14d, eax
0x18008f75e  test    eax, eax
0x18008f760  jns     loc_18008F834
0x18008f766  mov     r9d, eax; char *
0x18008f769  mov     edx, 25h ; '%'; void *
0x18008f76e  lea     r8, aOnecoreuapBase_294; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18008f775  mov     rcx, [rsp+138h]; this
0x18008f77d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f782  lea     rcx, [rsp+138h+TokenHandle]
0x18008f787  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008f78c  mov     rcx, [rsp+138h]; this
0x18008f794  test    r14d, r14d
0x18008f797  jns     loc_18008FA13
0x18008f79d  mov     r9d, r14d; char *
0x18008f7a0  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008f7a7  mov     edx, 19FAh; void *
0x18008f7ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008f7b2  mov     rcx, [rsp+138h+var_E0]
0x18008f7b7  mov     rcx, [rcx+0C0h]
0x18008f7be  mov     rax, [rcx]
0x18008f7c1  mov     r9, [rsp+138h+var_D8]
0x18008f7c6  mov     r8, [r12+8]
0x18008f7cb  mov     rdx, [r13+8]
0x18008f7cf  mov     rax, [rax+20h]
0x18008f7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f7d8  mov     r14d, eax
0x18008f7db  test    eax, eax
0x18008f7dd  js      loc_18008FA38
0x18008f7e3  test    rsi, rsi
0x18008f7e6  jz      short loc_18008F7F2
0x18008f7e8  mov     rcx, rsi; pvarg
0x18008f7eb  call    cs:__imp_VariantClear
0x18008f7f1  nop
0x18008f7f2  test    rbx, rbx
0x18008f7f5  jz      short loc_18008F800
0x18008f7f7  mov     rcx, rbx; pv
0x18008f7fa  call    CoTaskMemFree_0
0x18008f7ff  nop
0x18008f800  test    rdi, rdi
0x18008f803  jz      short loc_18008F80E
0x18008f805  mov     rcx, rdi; pv
0x18008f808  call    CoTaskMemFree_0
0x18008f80d  nop
0x18008f80e  mov     eax, r14d
0x18008f811  mov     rcx, [rsp+138h+var_48]
0x18008f819  xor     rcx, rsp; StackCookie
0x18008f81c  call    __security_check_cookie
0x18008f821  add     rsp, 100h
0x18008f828  pop     r15
0x18008f82a  pop     r14
0x18008f82c  pop     r13
0x18008f82e  pop     r12
0x18008f830  pop     rdi
0x18008f831  pop     rsi
0x18008f832  pop     rbx
0x18008f833  retn
0x18008f834  mov     [rsp+138h+var_104], r15d
0x18008f839  lea     rax, [rsp+138h+var_104]
0x18008f83e  mov     [rsp+138h+ReturnLength], rax; int
0x18008f843  mov     r9d, 44h ; 'D'; TokenInformationLength
0x18008f849  lea     r8, [rsp+138h+TokenInformation]; TokenInformation
0x18008f851  lea     edx, [r9-43h]; TokenInformationClass
0x18008f855  mov     rcx, [rsp+138h+TokenHandle]; TokenHandle
0x18008f85a  call    cs:__imp_GetTokenInformation
0x18008f860  test    eax, eax
0x18008f862  jz      loc_18008F9F1
0x18008f868  lea     rdx, [rsp+138h+StringSid]; StringSid
0x18008f86d  mov     rcx, [rsp+138h+TokenInformation]; Sid
0x18008f875  call    cs:__imp_ConvertSidToStringSidW
0x18008f87b  test    eax, eax
0x18008f87d  jnz     loc_18008FA0B
0x18008f883  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008f888  mov     r14d, eax
0x18008f88b  test    eax, eax
0x18008f88d  jns     loc_18008FA0B
0x18008f893  mov     edx, 12h; void *
0x18008f898  jmp     loc_1802BAE6A
0x18008f89d  mov     [r12+14h], r15d
0x18008f8a2  mov     rax, [r12+8]
0x18008f8a7  mov     [rax], r15w
0x18008f8ab  mov     rdx, [rsp+138h+StringSid]
0x18008f8b0  mov     rcx, r12
0x18008f8b3  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18008f8b8  nop
0x18008f8b9  lea     rcx, [rsp+138h+StringSid]
0x18008f8be  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18008f8c3  nop
0x18008f8c4  cmp     [rsp+138h+var_108], r15d
0x18008f8c9  jz      loc_18008F7B2
0x18008f8cf  call    cs:__imp_RevertToSelf
0x18008f8d5  jmp     loc_18008F7B2
0x18008f8da  mov     rcx, [rsp+138h]; this
0x18008f8e2  mov     r9d, 80070057h; char *
0x18008f8e8  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008f8ef  mov     edx, 19A4h; void *
0x18008f8f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f8f9  mov     eax, 80070057h
0x18008f8fe  jmp     loc_18008F811
0x18008f903  mov     rcx, [rsp+138h]; this
0x18008f90b  mov     ebx, 80004003h
0x18008f910  mov     r9d, ebx; char *
0x18008f913  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008f91a  mov     edx, 19A9h; void *
0x18008f91f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f924  mov     eax, ebx
0x18008f926  jmp     loc_18008F811
0x18008f92b  mov     rcx, [rsp+138h]; this
0x18008f933  mov     r9d, 80070057h; char *
0x18008f939  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008f940  mov     edx, 19BDh; void *
0x18008f945  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008f94a  mov     rdx, r15
0x18008f94d  mov     eax, 2008h
0x18008f952  cmp     ax, [rsi]
0x18008f955  jnz     loc_18008F5B9
0x18008f95b  mov     rax, [rbx+38h]
0x18008f95f  mov     rcx, [rax+10h]
0x18008f963  mov     rdx, [rcx]
0x18008f966  jmp     loc_18008F5B9
0x18008f96b  mov     rcx, [rsp+138h]; this
0x18008f973  mov     r9d, 80070057h; char *
0x18008f979  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18008f980  mov     edx, 19E0h; void *
0x18008f985  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008f98a  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18008f98f  mov     rcx, [rsp+138h]; this
0x18008f997  mov     r9d, 0CEh; char *
0x18008f99d  lea     r8, aOnecoreuapBase_291; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18008f9a4  mov     edx, 40Ch; void *
0x18008f9a9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18008f9ae  mov     rcx, [rsp+138h]; this
0x18008f9b6  mov     r9d, 0CEh; char *
0x18008f9bc  lea     r8, aOnecoreuapBase_291; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18008f9c3  mov     edx, 40Ch; void *
0x18008f9c8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18008f9ce  cmp     [rax+1A8h], r15
0x18008f9d5  jz      loc_18008F70C
0x18008f9db  mov     rdx, [rax+1A8h]; void *
0x18008f9e2  lea     rcx, [rsp+138h+var_108]; this
0x18008f9e7  call    ?ImpersonateUserToken@XPipeImpersonation@@QEAAXPEAX@Z; XPipeImpersonation::ImpersonateUserToken(void *)
0x18008f9ec  jmp     loc_18008F71C
0x18008f9f1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008f9f6  mov     r14d, eax
0x18008f9f9  test    eax, eax
0x18008f9fb  jns     loc_18008F868
0x18008fa01  mov     edx, 10h
0x18008fa06  jmp     loc_1802BAE6A
0x18008fa0b  mov     r14d, r15d
0x18008fa0e  jmp     loc_18008F782
0x18008fa13  mov     rcx, [rsp+138h]; this
0x18008fa1b  cmp     [rsp+138h+StringSid], r15
0x18008fa20  jnz     loc_18008F89D
0x18008fa26  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
  ... truncated ...
```
