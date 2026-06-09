# GetAppDisplayName

- ea: `0x180041be4`
- end: `0x180041ff0`
- name: `GetAppDisplayName`
- size: `1036`
- prototype: `__int64 __fastcall(PCWSTR sourceString)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180040d98`
- `0x1800631f4`
- `0x1800a0274`
- `0x1800d8c34`
- `0x1800dbe0c`

## callees

- `0x180018c20`
- `0x18001b340`
- `0x180035c40`
- `0x180041be4`
- `0x180042428`
- `0x1800977ac`
- `0x1801168dc`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041cc9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041cc9`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180041f2f`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180041f2f`
- `UserDataTypeHelperUtil!SafeStrDup` at `0x180041f45`
- `UserDataTypeHelperUtil!SafeStrDup` at `0x180041f45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041cb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041cb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041dae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041de9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041e66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041f87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041dae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041de9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041e66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041f87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041e4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041e4a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041ce1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041ce1`

## pseudocode

```c
__int64 __fastcall GetAppDisplayName(PCWSTR sourceString, __int64 a2)
{
  const WCHAR *v4; // rbx
  int PackageFromPackageFamilyName; // ebx
  HRESULT v7; // eax
  int ActivationFactory; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  struct Windows::Internal::StateRepository::IPackage *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rdi
  __int64 v16; // rcx
  __int64 v17; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  HRESULT v23; // eax
  WCHAR *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v28; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING v29; // [rsp+30h] [rbp-D0h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v30; // [rsp+38h] [rbp-C8h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v32; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+80h] [rbp-80h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(Block);
  GetAppCaptionFromExtras(sourceString, Block);
  v4 = (const WCHAR *)Block[0];
  if ( Block[0] == Block[1] )
  {
    v30 = 0;
    PackageFromPackageFamilyName = GetPackageFromPackageFamilyName(sourceString, &v30, 0);
    if ( PackageFromPackageFamilyName < 0 )
    {
      if ( v30 )
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v30 + 16LL))(v30);
LABEL_5:
      if ( Block[0] != &v32 )
        operator delete(Block[0]);
      return (unsigned int)PackageFromPackageFamilyName;
    }
    v27 = 0;
    string = 0;
    v7 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.MrtPackage", 0x2Bu, &hstringHeader, &string);
    if ( v7 < 0 )
    {
      RaiseException(v7, 1u, 0, 0);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_ede4711a_0c90_4d5b_acf3_58af696d9425, &v27);
    v9 = v27;
    PackageFromPackageFamilyName = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      if ( !v30 )
        goto LABEL_60;
      v10 = *(_QWORD *)v30;
LABEL_22:
      (*(void (**)(void))(v10 + 16))();
LABEL_60:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Block);
      return (unsigned int)PackageFromPackageFamilyName;
    }
    v11 = v30;
    v28 = 0;
    PackageFromPackageFamilyName = (*(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IPackage *, __int64 *))(*(_QWORD *)v27 + 88LL))(
                                     v27,
                                     v30,
                                     &v28);
    if ( PackageFromPackageFamilyName < 0 )
    {
LABEL_16:
      v12 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      v13 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      if ( !v11 )
        goto LABEL_60;
      v10 = *(_QWORD *)v11;
      goto LABEL_22;
    }
    v14 = v28;
    v29 = 0;
    if ( !v28 )
    {
      WindowsDeleteString(0);
      v25 = v28;
      v29 = 0;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v26 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      if ( v11 )
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v11 + 16LL))(v11);
      PackageFromPackageFamilyName = -2147023728;
      goto LABEL_60;
    }
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 80LL);
    WindowsDeleteString(0);
    v29 = 0;
    PackageFromPackageFamilyName = v15(v14, &v29);
    if ( PackageFromPackageFamilyName < 0 )
    {
      WindowsDeleteString(v29);
      v29 = 0;
      goto LABEL_16;
    }
    if ( !v29 )
    {
      WindowsDeleteString(0);
      v16 = v28;
      v29 = 0;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v17 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      if ( v11 )
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v11 + 16LL))(v11);
      PackageFromPackageFamilyName = -2147418113;
      goto LABEL_60;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v29, 0);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             Block,
                             StringRawBuffer) )
    {
      WindowsDeleteString(v29);
      v19 = v28;
      v29 = 0;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v20 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      if ( v11 )
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v11 + 16LL))(v11);
      PackageFromPackageFamilyName = -2147024882;
      goto LABEL_60;
    }
    WindowsDeleteString(v29);
    v21 = v28;
    v29 = 0;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( v11 )
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v11 + 16LL))(v11);
    v4 = (const WCHAR *)Block[0];
  }
  v23 = SHLoadIndirectString(v4, pszOutBuf, 0x104u, 0);
  v24 = pszOutBuf;
  if ( v23 < 0 )
    v24 = (WCHAR *)v4;
  PackageFromPackageFamilyName = SafeStrDup(v24, 0xFFFFFFFFLL, a2);
  if ( PackageFromPackageFamilyName < 0 )
    goto LABEL_5;
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(Block);
  return 0;
}

```

## disassembly

```asm
0x180041be4  mov     [rsp-8+arg_10], rbx
0x180041be9  push    rbp
0x180041bea  push    rsi
0x180041beb  push    rdi
0x180041bec  push    r14
0x180041bee  push    r15
0x180041bf0  lea     rbp, [rsp-1A0h]
0x180041bf8  sub     rsp, 2A0h
0x180041bff  mov     rax, cs:__security_cookie
0x180041c06  xor     rax, rsp
0x180041c09  mov     [rbp+1C0h+var_30], rax
0x180041c10  mov     rdi, rcx
0x180041c13  mov     r14, rdx
0x180041c16  lea     rcx, [rsp+2C0h+Block]; void *
0x180041c1b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180041c20  lea     rdx, [rsp+2C0h+Block]
0x180041c25  mov     rcx, rdi
0x180041c28  call    ?GetAppCaptionFromExtras@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetAppCaptionFromExtras(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180041c2d  mov     rbx, [rsp+2C0h+Block]
0x180041c32  xor     r15d, r15d
0x180041c35  cmp     rbx, [rsp+2C0h+var_278]
0x180041c3a  jnz     loc_180041F1F
0x180041c40  xor     r8d, r8d; struct Windows::Internal::StateRepository::IPackageUser **
0x180041c43  mov     [rsp+2C0h+var_288], r15
0x180041c48  lea     rdx, [rsp+2C0h+var_288]; struct Windows::Internal::StateRepository::IPackage **
0x180041c4d  mov     rcx, rdi; sourceString
0x180041c50  call    ?GetPackageFromPackageFamilyName@@YAJPEBGPEAPEAUIPackage@StateRepository@Internal@Windows@@PEAPEAUIPackageUser@234@@Z; GetPackageFromPackageFamilyName(ushort const *,Windows::Internal::StateRepository::IPackage * *,Windows::Internal::StateRepository::IPackageUser * *)
0x180041c55  mov     ebx, eax
0x180041c57  test    eax, eax
0x180041c59  jns     short loc_180041C93
0x180041c5b  mov     rcx, [rsp+2C0h+var_288]
0x180041c60  test    rcx, rcx
0x180041c63  jz      short loc_180041C71
0x180041c65  mov     rdx, [rcx]
0x180041c68  mov     rax, [rdx+10h]
0x180041c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c71  mov     rcx, [rsp+2C0h+Block]; Block
0x180041c76  lea     rax, [rsp+2C0h+var_270]
0x180041c7b  cmp     rcx, rax
0x180041c7e  jz      short loc_180041C8C
0x180041c80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180041c87  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180041c8c  mov     eax, ebx
0x180041c8e  jmp     loc_180041F61
0x180041c93  lea     r9, [rsp+2C0h+string]; string
0x180041c98  mov     [rsp+2C0h+var_2A0], r15
0x180041c9d  lea     r8, [rsp+2C0h+hstringHeader]; hstringHeader
0x180041ca2  mov     [rsp+2C0h+string], r15
0x180041ca7  mov     edx, 2Bh ; '+'; length
0x180041cac  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_MrtPackage@@3QBGB; "Windows.Internal.StateRepository.MrtPac"...
0x180041cb3  call    cs:__imp_WindowsCreateStringReference
0x180041cb9  test    eax, eax
0x180041cbb  jns     short loc_180041CD0
0x180041cbd  xor     r9d, r9d; lpArguments
0x180041cc0  xor     r8d, r8d; nNumberOfArguments
0x180041cc3  mov     ecx, eax; dwExceptionCode
0x180041cc5  lea     edx, [r9+1]; dwExceptionFlags
0x180041cc9  call    cs:__imp_RaiseException
0x180041ccf  int     3; Trap to Debugger
0x180041cd0  mov     rcx, [rsp+2C0h+string]
0x180041cd5  lea     r8, [rsp+2C0h+var_2A0]
0x180041cda  lea     rdx, _GUID_ede4711a_0c90_4d5b_acf3_58af696d9425
0x180041ce1  call    cs:__imp_RoGetActivationFactory
0x180041ce7  mov     rcx, [rsp+2C0h+var_2A0]
0x180041cec  mov     ebx, eax
0x180041cee  test    eax, eax
0x180041cf0  jns     short loc_180041D1B
0x180041cf2  test    rcx, rcx
0x180041cf5  jz      short loc_180041D08
0x180041cf7  mov     [rsp+2C0h+var_2A0], r15
0x180041cfc  mov     rdx, [rcx]
0x180041cff  mov     rax, [rdx+10h]
0x180041d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d08  mov     rcx, [rsp+2C0h+var_288]
0x180041d0d  test    rcx, rcx
0x180041d10  jz      loc_180041FE1
0x180041d16  mov     rax, [rcx]
0x180041d19  jmp     short loc_180041D84
0x180041d1b  mov     rsi, [rsp+2C0h+var_288]
0x180041d20  lea     r8, [rsp+2C0h+var_298]
0x180041d25  mov     [rsp+2C0h+var_298], r15
0x180041d2a  mov     rdx, rsi
0x180041d2d  mov     rax, [rcx]
0x180041d30  mov     rax, [rax+58h]
0x180041d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d39  mov     ebx, eax
0x180041d3b  test    eax, eax
0x180041d3d  jns     short loc_180041D92
0x180041d3f  mov     rcx, [rsp+2C0h+var_298]
0x180041d44  test    rcx, rcx
0x180041d47  jz      short loc_180041D5A
0x180041d49  mov     [rsp+2C0h+var_298], r15
0x180041d4e  mov     rdx, [rcx]
0x180041d51  mov     rax, [rdx+10h]
0x180041d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d5a  mov     rcx, [rsp+2C0h+var_2A0]
0x180041d5f  test    rcx, rcx
0x180041d62  jz      short loc_180041D75
0x180041d64  mov     [rsp+2C0h+var_2A0], r15
0x180041d69  mov     rax, [rcx]
0x180041d6c  mov     rax, [rax+10h]
0x180041d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d75  test    rsi, rsi
0x180041d78  jz      loc_180041FE1
0x180041d7e  mov     rax, [rsi]
0x180041d81  mov     rcx, rsi
0x180041d84  mov     rax, [rax+10h]
0x180041d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d8d  jmp     loc_180041FE1
0x180041d92  mov     rbx, [rsp+2C0h+var_298]
0x180041d97  xor     ecx, ecx; string
0x180041d99  mov     [rsp+2C0h+var_290], r15
0x180041d9e  test    rbx, rbx
0x180041da1  jz      loc_180041F87
0x180041da7  mov     rax, [rbx]
0x180041daa  mov     rdi, [rax+50h]
0x180041dae  call    cs:__imp_WindowsDeleteString
0x180041db4  lea     rdx, [rsp+2C0h+var_290]
0x180041db9  mov     [rsp+2C0h+var_290], r15
0x180041dbe  mov     rcx, rbx
0x180041dc1  mov     rax, rdi
0x180041dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041dc9  mov     rcx, [rsp+2C0h+var_290]; string
0x180041dce  mov     ebx, eax
0x180041dd0  test    eax, eax
0x180041dd2  jns     short loc_180041DE4
0x180041dd4  call    cs:__imp_WindowsDeleteString
0x180041dda  mov     [rsp+2C0h+var_290], r15
0x180041ddf  jmp     loc_180041D3F
0x180041de4  test    rcx, rcx
0x180041de7  jnz     short loc_180041E48
0x180041de9  call    cs:__imp_WindowsDeleteString
0x180041def  mov     rcx, [rsp+2C0h+var_298]
0x180041df4  mov     [rsp+2C0h+var_290], r15
0x180041df9  test    rcx, rcx
0x180041dfc  jz      short loc_180041E0F
0x180041dfe  mov     [rsp+2C0h+var_298], r15
0x180041e03  mov     rax, [rcx]
0x180041e06  mov     rax, [rax+10h]
0x180041e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e0f  mov     rcx, [rsp+2C0h+var_2A0]
0x180041e14  test    rcx, rcx
0x180041e17  jz      short loc_180041E2A
0x180041e19  mov     [rsp+2C0h+var_2A0], r15
0x180041e1e  mov     rax, [rcx]
0x180041e21  mov     rax, [rax+10h]
0x180041e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e2a  test    rsi, rsi
0x180041e2d  jz      short loc_180041E3E
0x180041e2f  mov     rax, [rsi]
0x180041e32  mov     rcx, rsi
0x180041e35  mov     rax, [rax+10h]
0x180041e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e3e  mov     ebx, 8000FFFFh
0x180041e43  jmp     loc_180041FE1
0x180041e48  xor     edx, edx; length
0x180041e4a  call    cs:__imp_WindowsGetStringRawBuffer
0x180041e50  mov     rdx, rax
0x180041e53  lea     rcx, [rsp+2C0h+Block]
0x180041e58  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180041e5d  mov     rcx, [rsp+2C0h+var_290]; string
0x180041e62  test    al, al
0x180041e64  jnz     short loc_180041EC5
0x180041e66  call    cs:__imp_WindowsDeleteString
0x180041e6c  mov     rcx, [rsp+2C0h+var_298]
0x180041e71  mov     [rsp+2C0h+var_290], r15
0x180041e76  test    rcx, rcx
0x180041e79  jz      short loc_180041E8C
0x180041e7b  mov     [rsp+2C0h+var_298], r15
0x180041e80  mov     rax, [rcx]
0x180041e83  mov     rax, [rax+10h]
0x180041e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e8c  mov     rcx, [rsp+2C0h+var_2A0]
0x180041e91  test    rcx, rcx
0x180041e94  jz      short loc_180041EA7
0x180041e96  mov     [rsp+2C0h+var_2A0], r15
0x180041e9b  mov     rax, [rcx]
0x180041e9e  mov     rax, [rax+10h]
0x180041ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ea7  test    rsi, rsi
0x180041eaa  jz      short loc_180041EBB
0x180041eac  mov     rax, [rsi]
0x180041eaf  mov     rcx, rsi
0x180041eb2  mov     rax, [rax+10h]
0x180041eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ebb  mov     ebx, 8007000Eh
0x180041ec0  jmp     loc_180041FE1
0x180041ec5  call    cs:__imp_WindowsDeleteString
0x180041ecb  mov     rcx, [rsp+2C0h+var_298]
0x180041ed0  mov     [rsp+2C0h+var_290], r15
0x180041ed5  test    rcx, rcx
0x180041ed8  jz      short loc_180041EEB
0x180041eda  mov     [rsp+2C0h+var_298], r15
0x180041edf  mov     rax, [rcx]
0x180041ee2  mov     rax, [rax+10h]
0x180041ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041eeb  mov     rcx, [rsp+2C0h+var_2A0]
0x180041ef0  test    rcx, rcx
0x180041ef3  jz      short loc_180041F06
0x180041ef5  mov     [rsp+2C0h+var_2A0], r15
0x180041efa  mov     rax, [rcx]
0x180041efd  mov     rax, [rax+10h]
0x180041f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f06  test    rsi, rsi
0x180041f09  jz      short loc_180041F1A
0x180041f0b  mov     rax, [rsi]
0x180041f0e  mov     rcx, rsi
0x180041f11  mov     rax, [rax+10h]
0x180041f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f1a  mov     rbx, [rsp+2C0h+Block]
0x180041f1f  xor     r9d, r9d; ppvReserved
0x180041f22  lea     rdx, [rbp+1C0h+pszOutBuf]; pszOutBuf
0x180041f26  mov     r8d, 104h; cchOutBuf
0x180041f2c  mov     rcx, rbx; pszSource
0x180041f2f  call    cs:__imp_SHLoadIndirectString
0x180041f35  lea     rcx, [rbp+1C0h+pszOutBuf]
0x180041f39  mov     r8, r14
0x180041f3c  test    eax, eax
0x180041f3e  cmovs   rcx, rbx
0x180041f42  or      edx, 0FFFFFFFFh
0x180041f45  call    cs:__imp_SafeStrDup
0x180041f4b  mov     ebx, eax
0x180041f4d  test    eax, eax
0x180041f4f  js      loc_180041C71
0x180041f55  lea     rcx, [rsp+2C0h+Block]; void *
0x180041f5a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180041f5f  xor     eax, eax
0x180041f61  mov     rcx, [rbp+1C0h+var_30]
0x180041f68  xor     rcx, rsp; StackCookie
0x180041f6b  call    __security_check_cookie
0x180041f70  mov     rbx, [rsp+2C0h+arg_10]
0x180041f78  add     rsp, 2A0h
0x180041f7f  pop     r15
0x180041f81  pop     r14
0x180041f83  pop     rdi
0x180041f84  pop     rsi
0x180041f85  pop     rbp
0x180041f86  retn
0x180041f87  call    cs:__imp_WindowsDeleteString
0x180041f8d  mov     rcx, [rsp+2C0h+var_298]
0x180041f92  mov     [rsp+2C0h+var_290], r15
0x180041f97  test    rcx, rcx
0x180041f9a  jz      short loc_180041FAD
0x180041f9c  mov     [rsp+2C0h+var_298], r15
0x180041fa1  mov     rax, [rcx]
0x180041fa4  mov     rax, [rax+10h]
0x180041fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fad  mov     rcx, [rsp+2C0h+var_2A0]
0x180041fb2  test    rcx, rcx
0x180041fb5  jz      short loc_180041FC8
0x180041fb7  mov     [rsp+2C0h+var_2A0], r15
0x180041fbc  mov     rax, [rcx]
0x180041fbf  mov     rax, [rax+10h]
0x180041fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fc8  test    rsi, rsi
0x180041fcb  jz      short loc_180041FDC
0x180041fcd  mov     rax, [rsi]
0x180041fd0  mov     rcx, rsi
0x180041fd3  mov     rax, [rax+10h]
0x180041fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fdc  mov     ebx, 80070490h
0x180041fe1  lea     rcx, [rsp+2C0h+Block]; void *
0x180041fe6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180041feb  jmp     loc_180041C8C
```
