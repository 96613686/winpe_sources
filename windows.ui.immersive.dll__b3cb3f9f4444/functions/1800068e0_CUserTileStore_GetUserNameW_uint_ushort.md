# CUserTileStore::GetUserNameW(uint,ushort * *)

- ea: `0x1800068e0`
- end: `0x180006b38`
- name: `?GetUserNameW@CUserTileStore@@UEAAJIPEAPEAG@Z`
- size: `600`
- prototype: `int(CUserTileStore *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006794`
- `0x1800068e0`
- `0x180006b40`
- `0x180006ba8`
- `0x180006c64`
- `0x180006c94`
- `0x18000af00`
- `0x18003d244`
- `0x180054ad4`
- `0x1800ce1ec`
- `0x1800ce61c`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ad9`
- `SspiCli!GetUserNameExW` at `0x1800069c5`
- `SspiCli!GetUserNameExW` at `0x180006a5e`
- `SspiCli!GetUserNameExW` at `0x1800069c5`
- `SspiCli!GetUserNameExW` at `0x180006a5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUserTileStore::GetUserNameW(CUserTileStore *this, EXTENDED_NAME_FORMAT a2, unsigned __int16 **a3)
{
  __int64 (__fastcall *v6)(CUserTileStore *, unsigned __int16 **, unsigned __int16 **); // rdi
  unsigned __int16 **v7; // r8
  unsigned __int16 **v8; // rdx
  int Error; // edi
  unsigned __int16 *v10; // rax
  CUserTileStore *v11; // rcx
  unsigned __int16 *v12; // rsi
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r15
  size_t v16; // rax
  unsigned __int16 *v17; // rax
  bool IsDomainUser; // bl
  __int64 v19; // rcx
  wil::TraceLoggingProvider *v20; // rax
  unsigned __int8 v21; // dl
  unsigned __int64 v22; // r8
  __int64 v23; // rcx
  UserInfoTelemetry *v24; // rcx
  unsigned __int16 *v26; // [rsp+30h] [rbp-20h] BYREF
  __int64 v27; // [rsp+38h] [rbp-18h]
  __int64 v28; // [rsp+40h] [rbp-10h]
  ULONG nSize; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 *v30; // [rsp+A0h] [rbp+50h]

  *a3 = 0;
  if ( CUserTileStore::_IsDomainUser(this) && (unsigned int)(a2 - 13) <= 1 )
  {
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v6 = *(__int64 (__fastcall **)(CUserTileStore *, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)this + 136LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
    v27 = -1;
    v28 = -1;
    if ( a2 == NameGivenName )
    {
      v7 = 0;
      v8 = &v26;
    }
    else
    {
      v7 = &v26;
      v8 = 0;
    }
    Error = v6(this, v8, v7);
    if ( Error >= 0 )
    {
      v10 = v26;
      v26 = 0;
      v28 = 0;
      v27 = 0;
      *a3 = v10;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v26);
    goto LABEL_31;
  }
  v27 = -1;
  v28 = -1;
  v12 = 0;
  v26 = 0;
  nSize = 0;
  if ( !GetUserNameExW(a2, 0, &nSize) )
  {
    Error = ResultFromKnownLastError();
    if ( Error != -2147024662 )
      goto LABEL_23;
    v30 = 0;
    CoTaskMemFree(0);
    v13 = 0;
    v30 = 0;
    if ( !is_mul_ok(nSize, 2u) )
    {
      Error = -2147024362;
      goto LABEL_22;
    }
    v14 = (unsigned __int16 *)CoTaskMemAlloc(2LL * nSize);
    v15 = v14;
    v13 = v14;
    v30 = v14;
    if ( v14 )
    {
      v16 = CTCoAllocPolicy::_CoTaskMemSize(v14);
      memset_0(v13, 0, v16);
      Error = 0;
    }
    else
    {
      Error = -2147024882;
    }
    if ( Error < 0 )
      goto LABEL_22;
    if ( GetUserNameExW(a2, v13, &nSize) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_22:
        CoTaskMemFree(v13);
        goto LABEL_23;
      }
    }
    v13 = 0;
    v12 = v15;
    v26 = v15;
    goto LABEL_22;
  }
  Error = 0;
LABEL_23:
  if ( Error < 0 )
  {
    if ( a2 == NameDisplay )
    {
      if ( Error != -2147023564 || (Error = CUserTileStore::_GetInternetPrincipalName(v11, a3), Error < 0) )
        Error = CUserTileStore::_GetLocalAccountDisplayName(v11, a3);
    }
  }
  else
  {
    v17 = v12;
    v12 = 0;
    *a3 = v17;
  }
  if ( v12 )
    CoTaskMemFree(v12);
LABEL_31:
  IsDomainUser = CUserTileStore::_IsDomainUser(v11);
  v20 = (wil::TraceLoggingProvider *)wil::details::static_lazy<UserInfoTelemetry>::get(
                                       v19,
                                       _lambda_ce69ed42d60ac1ca0172729e13171e74_::_lambda_invoker_cdecl_);
  if ( wil::TraceLoggingProvider::IsEnabled_(v20, v21, v22) )
  {
    wil::details::static_lazy<UserInfoTelemetry>::get(
      v23,
      _lambda_ce69ed42d60ac1ca0172729e13171e74_::_lambda_invoker_cdecl_);
    UserInfoTelemetry::GetUserNameEvent_(v24, 0x23C2u, Error, IsDomainUser, a2);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800068e0  push    rbp
0x1800068e2  push    rbx
0x1800068e3  push    rsi
0x1800068e4  push    rdi
0x1800068e5  push    r12
0x1800068e7  push    r14
0x1800068e9  push    r15
0x1800068eb  mov     rbp, rsp
0x1800068ee  sub     rsp, 50h
0x1800068f2  mov     r12, r8
0x1800068f5  mov     r14d, edx
0x1800068f8  mov     rbx, rcx
0x1800068fb  mov     qword ptr [r8], 0
0x180006902  call    ?_IsDomainUser@CUserTileStore@@AEAA_NXZ; CUserTileStore::_IsDomainUser(void)
0x180006907  test    al, al
0x180006909  jz      loc_1800069A7
0x18000690f  lea     eax, [r14-0Dh]
0x180006913  cmp     eax, 1
0x180006916  ja      loc_1800069A7
0x18000691c  mov     [rbp+var_20], 0
0x180006924  mov     [rbp+var_18], 0
0x18000692c  mov     [rbp+var_10], 0
0x180006934  mov     rax, [rbx]
0x180006937  mov     rdi, [rax+88h]
0x18000693e  lea     rcx, [rbp+var_20]
0x180006942  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180006947  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000694b  mov     rcx, rbx
0x18000694e  mov     [rbp+var_18], rax
0x180006952  mov     [rbp+var_10], rax
0x180006956  mov     rax, rdi
0x180006959  cmp     r14d, 0Dh
0x18000695d  jnz     short loc_180006968
0x18000695f  xor     r8d, r8d
0x180006962  lea     rdx, [rbp+var_20]
0x180006966  jmp     short loc_18000696E
0x180006968  lea     r8, [rbp+var_20]
0x18000696c  xor     edx, edx
0x18000696e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006973  mov     edi, eax
0x180006975  test    eax, eax
0x180006977  js      short loc_180006999
0x180006979  mov     rax, [rbp+var_20]
0x18000697d  mov     [rbp+var_20], 0
0x180006985  mov     [rbp+var_10], 0
0x18000698d  mov     [rbp+var_18], 0
0x180006995  mov     [r12], rax
0x180006999  lea     rcx, [rbp+var_20]
0x18000699d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800069a2  jmp     loc_180006AE5
0x1800069a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800069ab  mov     [rbp+var_18], rax
0x1800069af  mov     [rbp+var_10], rax
0x1800069b3  xor     esi, esi
0x1800069b5  mov     [rbp+var_20], rsi
0x1800069b9  mov     [rbp+nSize], esi
0x1800069bc  lea     r8, [rbp+nSize]; nSize
0x1800069c0  xor     edx, edx; lpNameBuffer
0x1800069c2  mov     ecx, r14d; NameFormat
0x1800069c5  call    cs:__imp_GetUserNameExW
0x1800069cc  nop     dword ptr [rax+rax+00h]
0x1800069d1  test    al, al
0x1800069d3  jz      short loc_1800069DC
0x1800069d5  xor     edi, edi
0x1800069d7  jmp     loc_180006A9C
0x1800069dc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800069e1  mov     edi, eax
0x1800069e3  cmp     eax, 800700EAh
0x1800069e8  jnz     loc_180006A9C
0x1800069ee  mov     [rbp+arg_10], rsi
0x1800069f2  xor     ecx, ecx; pv
0x1800069f4  call    cs:__imp_CoTaskMemFree
0x1800069fb  nop     dword ptr [rax+rax+00h]
0x180006a00  xor     ebx, ebx
0x180006a02  mov     [rbp+arg_10], rbx
0x180006a06  mov     ecx, [rbp+nSize]
0x180006a09  lea     eax, [rbx+2]
0x180006a0c  mul     rcx
0x180006a0f  test    rdx, rdx
0x180006a12  jnz     short loc_180006A88
0x180006a14  mov     rcx, rax; cb
0x180006a17  call    cs:__imp_CoTaskMemAlloc
0x180006a1e  nop     dword ptr [rax+rax+00h]
0x180006a23  mov     r15, rax
0x180006a26  mov     rbx, rax
0x180006a29  mov     [rbp+arg_10], rax
0x180006a2d  test    rax, rax
0x180006a30  jz      short loc_180006A4B
0x180006a32  mov     rcx, rax; void *
0x180006a35  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180006a3a  mov     r8, rax; Size
0x180006a3d  xor     edx, edx; Val
0x180006a3f  mov     rcx, rbx; void *
0x180006a42  call    memset_0
0x180006a47  xor     edi, edi
0x180006a49  jmp     short loc_180006A50
0x180006a4b  mov     edi, 8007000Eh
0x180006a50  test    edi, edi
0x180006a52  js      short loc_180006A8D
0x180006a54  lea     r8, [rbp+nSize]; nSize
0x180006a58  mov     rdx, rbx; lpNameBuffer
0x180006a5b  mov     ecx, r14d; NameFormat
0x180006a5e  call    cs:__imp_GetUserNameExW
0x180006a65  nop     dword ptr [rax+rax+00h]
0x180006a6a  test    al, al
0x180006a6c  jz      short loc_180006A72
0x180006a6e  xor     edi, edi
0x180006a70  jmp     short loc_180006A7D
0x180006a72  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006a77  mov     edi, eax
0x180006a79  test    eax, eax
0x180006a7b  js      short loc_180006A8D
0x180006a7d  xor     ebx, ebx
0x180006a7f  mov     rsi, r15
0x180006a82  mov     [rbp+var_20], r15
0x180006a86  jmp     short loc_180006A8D
0x180006a88  mov     edi, 80070216h
0x180006a8d  mov     rcx, rbx; pv
0x180006a90  call    cs:__imp_CoTaskMemFree
0x180006a97  nop     dword ptr [rax+rax+00h]
0x180006a9c  test    edi, edi
0x180006a9e  js      short loc_180006AAB
0x180006aa0  mov     rax, rsi
0x180006aa3  xor     esi, esi
0x180006aa5  mov     [r12], rax
0x180006aa9  jmp     short loc_180006AD1
0x180006aab  cmp     r14d, 3
0x180006aaf  jnz     short loc_180006AD1
0x180006ab1  cmp     edi, 80070534h
0x180006ab7  jnz     short loc_180006AC7
0x180006ab9  mov     rdx, r12; unsigned __int16 **
0x180006abc  call    ?_GetInternetPrincipalName@CUserTileStore@@AEAAJPEAPEAG@Z; CUserTileStore::_GetInternetPrincipalName(ushort * *)
0x180006ac1  mov     edi, eax
0x180006ac3  test    eax, eax
0x180006ac5  jns     short loc_180006AD1
0x180006ac7  mov     rdx, r12; unsigned __int16 **
0x180006aca  call    ?_GetLocalAccountDisplayName@CUserTileStore@@AEAAJPEAPEAG@Z; CUserTileStore::_GetLocalAccountDisplayName(ushort * *)
0x180006acf  mov     edi, eax
0x180006ad1  test    rsi, rsi
0x180006ad4  jz      short loc_180006AE5
0x180006ad6  mov     rcx, rsi; pv
0x180006ad9  call    cs:__imp_CoTaskMemFree
0x180006ae0  nop     dword ptr [rax+rax+00h]
0x180006ae5  call    ?_IsDomainUser@CUserTileStore@@AEAA_NXZ; CUserTileStore::_IsDomainUser(void)
0x180006aea  mov     bl, al
0x180006aec  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ce69ed42d60ac1ca0172729e13171e74_@@CA@XZ; _lambda_ce69ed42d60ac1ca0172729e13171e74_::_lambda_invoker_cdecl_(void)
0x180006af3  call    ?get@?$static_lazy@VUserInfoTelemetry@@@details@wil@@QEAAPEAVUserInfoTelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserInfoTelemetry>::get(void (*)(void))
0x180006af8  mov     rcx, rax; this
0x180006afb  call    ?IsEnabled_@TraceLoggingProvider@wil@@IEBA_NE_K@Z; wil::TraceLoggingProvider::IsEnabled_(uchar,unsigned __int64)
0x180006b00  test    al, al
0x180006b02  jz      short loc_180006B26
0x180006b04  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ce69ed42d60ac1ca0172729e13171e74_@@CA@XZ; _lambda_ce69ed42d60ac1ca0172729e13171e74_::_lambda_invoker_cdecl_(void)
0x180006b0b  call    ?get@?$static_lazy@VUserInfoTelemetry@@@details@wil@@QEAAPEAVUserInfoTelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserInfoTelemetry>::get(void (*)(void))
0x180006b10  mov     [rsp+50h+var_30], r14d; enum EXTENDED_NAME_FORMAT
0x180006b15  mov     r9b, bl; bool
0x180006b18  mov     r8d, edi; int
0x180006b1b  mov     edx, 23C2h; unsigned int
0x180006b20  call    ?GetUserNameEvent_@UserInfoTelemetry@@QEAAXKJ_NW4EXTENDED_NAME_FORMAT@@@Z; UserInfoTelemetry::GetUserNameEvent_(ulong,long,bool,EXTENDED_NAME_FORMAT)
0x180006b25  nop
0x180006b26  mov     eax, edi
0x180006b28  add     rsp, 50h
0x180006b2c  pop     r15
0x180006b2e  pop     r14
0x180006b30  pop     r12
0x180006b32  pop     rdi
0x180006b33  pop     rsi
0x180006b34  pop     rbx
0x180006b35  pop     rbp
0x180006b36  retn
```
