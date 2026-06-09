# GetPackageFromPackageFamilyName(ushort const *,Windows::Internal::StateRepository::IPackage * *,Windows::Internal::StateRepository::IPackageUser * *)

- ea: `0x18001c3ec`
- end: `0x18001c835`
- name: `?GetPackageFromPackageFamilyName@@YAJPEBGPEAPEAUIPackage@StateRepository@Internal@Windows@@PEAPEAUIPackageUser@234@@Z`
- size: `1097`
- prototype: `__int64 __fastcall(PCWSTR sourceString, struct Windows::Internal::StateRepository::IPackage **, struct Windows::Internal::StateRepository::IPackageUser **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c308`

## callees

- `0x18001c3ec`
- `0x18001c83c`
- `0x18001c940`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c4b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c808`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c81b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c82e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c4b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c808`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c81b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c82e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c46a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c540`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c46a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c540`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c4c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c523`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c4c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c523`

## pseudocode

```c
__int64 __fastcall GetPackageFromPackageFamilyName(
        PCWSTR sourceString,
        struct Windows::Internal::StateRepository::IPackage **a2,
        struct Windows::Internal::StateRepository::IPackageUser **a3)
{
  int CurrentUser; // ebx
  HRESULT v6; // eax
  _QWORD *v7; // rbx
  unsigned __int64 v8; // rdx
  __int64 v9; // r14
  HRESULT v10; // eax
  HRESULT v11; // eax
  int v12; // eax
  struct Windows::Internal::StateRepository::IPackageUser *v13; // rcx
  struct Windows::Internal::StateRepository::IPackageUser *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  struct Windows::Internal::StateRepository::IUser *v19; // rcx
  __int64 v21; // rcx
  void (*v22)(void); // rax
  _QWORD *v23; // rcx
  void (*v24)(void); // rax
  struct Windows::Internal::StateRepository::IUser *v25; // rcx
  void (*v26)(void); // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  void (*v29)(void); // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  _QWORD *v34; // rcx
  struct Windows::Internal::StateRepository::IUser *v35; // rcx
  struct Windows::Internal::StateRepository::IUser *v36; // rdx
  _QWORD *v37; // rdx
  __int64 v38; // rcx
  struct Windows::Internal::StateRepository::IUser *v39; // [rsp+30h] [rbp-29h] BYREF
  _QWORD *v40; // [rsp+38h] [rbp-21h] BYREF
  __int64 v41; // [rsp+40h] [rbp-19h] BYREF
  __int64 v42; // [rsp+48h] [rbp-11h] BYREF
  __int64 v43; // [rsp+50h] [rbp-9h] BYREF
  struct Windows::Internal::StateRepository::IPackageUser *v44; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  HSTRING string; // [rsp+78h] [rbp+1Fh] BYREF

  v39 = 0;
  CurrentUser = GetCurrentUser(&v39);
  if ( CurrentUser < 0 )
  {
    v36 = v39;
    if ( !v39 )
      return (unsigned int)CurrentUser;
    v39 = 0;
    v26 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
    goto LABEL_38;
  }
  v40 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  CurrentUser = RoGetActivationFactory(string, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v40);
  if ( CurrentUser < 0 )
  {
    v37 = v40;
    if ( !v40 )
      goto LABEL_36;
    v40 = 0;
    v24 = *(void (**)(void))(*v37 + 16LL);
    goto LABEL_35;
  }
  v7 = v40;
  v8 = -1;
  v41 = 0;
  v9 = *v40;
  string = 0;
  do
    ++v8;
  while ( sourceString[v8] );
  if ( v8 > 0xFFFFFFFF || (int)v8 + 1 < (unsigned int)v8 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v10 = WindowsCreateStringReference(sourceString, v8, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    RaiseException(v10, 1u, 0, 0);
    __debugbreak();
  }
  CurrentUser = (*(__int64 (__fastcall **)(_QWORD *, struct Windows::Internal::StateRepository::IUser *, HSTRING, __int64, __int64 *))(v9 + 424))(
                  v7,
                  v39,
                  string,
                  1,
                  &v41);
  if ( CurrentUser < 0 )
  {
    v21 = v41;
    if ( !v41 )
    {
LABEL_33:
      v23 = v40;
      if ( !v40 )
      {
LABEL_36:
        v25 = v39;
        if ( !v39 )
          return (unsigned int)CurrentUser;
        v39 = 0;
        v26 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
LABEL_38:
        v26();
        return (unsigned int)CurrentUser;
      }
      v40 = 0;
      v24 = *(void (**)(void))(*v23 + 16LL);
LABEL_35:
      v24();
      goto LABEL_36;
    }
    v41 = 0;
    v22 = *(void (**)(void))(*(_QWORD *)v21 + 16LL);
LABEL_32:
    v22();
    goto LABEL_33;
  }
  v42 = 0;
  string = 0;
  v11 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageUser", 0x2Cu, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    JUMPOUT(0x18001C834LL);
  }
  CurrentUser = RoGetActivationFactory(string, &GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6, &v42);
  if ( CurrentUser < 0 )
  {
    v38 = v42;
    if ( !v42 )
      goto LABEL_47;
    v42 = 0;
    v29 = *(void (**)(void))(*(_QWORD *)v38 + 16LL);
LABEL_46:
    v29();
LABEL_47:
    v30 = v41;
    if ( !v41 )
      goto LABEL_33;
    v41 = 0;
    v22 = *(void (**)(void))(*(_QWORD *)v30 + 16LL);
    goto LABEL_32;
  }
  hstringHeader.Reserved.Reserved1 = &v42;
  v43 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v39;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v44;
  string = (HSTRING)&v43;
  v44 = 0;
  v12 = ForEach_Windows::Internal::StateRepository::Package____lambda_8ac71d931e4442495cadb6e2921601b1___(
          v41,
          &hstringHeader);
  v13 = v44;
  CurrentUser = v12;
  if ( v12 < 0 )
  {
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackageUser *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v27 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v42;
    if ( !v42 )
      goto LABEL_47;
    v42 = 0;
    v29 = *(void (**)(void))(*(_QWORD *)v28 + 16LL);
    goto LABEL_46;
  }
  if ( v44 )
  {
    if ( a3 )
    {
      v14 = v44;
      v13 = 0;
      v44 = 0;
      *a3 = v14;
    }
    if ( v13 )
    {
      v44 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackageUser *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v15 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    }
    v19 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IUser *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return 0;
  }
  else
  {
    v31 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
    }
    v35 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IUser *))(*(_QWORD *)v35 + 16LL))(v35);
    }
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x18001c3ec  mov     [rsp-8+arg_8], rbx
0x18001c3f1  push    rbp
0x18001c3f2  push    rsi
0x18001c3f3  push    rdi
0x18001c3f4  push    r14
0x18001c3f6  push    r15
0x18001c3f8  lea     rbp, [rsp-37h]
0x18001c3fd  sub     rsp, 90h
0x18001c404  mov     rax, cs:__security_cookie
0x18001c40b  xor     rax, rsp
0x18001c40e  mov     [rbp+57h+var_30], rax
0x18001c412  mov     rsi, rcx
0x18001c415  xor     r15d, r15d
0x18001c418  lea     rcx, [rbp+57h+var_80]; struct Windows::Internal::StateRepository::IUser **
0x18001c41c  mov     [rbp+57h+var_80], r15
0x18001c420  mov     rdi, r8
0x18001c423  call    ?GetCurrentUser@@YAJPEAPEAUIUser@StateRepository@Internal@Windows@@@Z; GetCurrentUser(Windows::Internal::StateRepository::IUser * *)
0x18001c428  mov     ebx, eax
0x18001c42a  test    eax, eax
0x18001c42c  js      loc_18001C79F
0x18001c432  lea     r9, [rbp+57h+string]; string
0x18001c436  mov     [rbp+57h+var_78], r15
0x18001c43a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001c43e  mov     [rbp+57h+string], r15
0x18001c442  lea     edx, [r15+28h]; length
0x18001c446  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18001c44d  call    cs:__imp_WindowsCreateStringReference
0x18001c453  test    eax, eax
0x18001c455  js      loc_18001C7FC
0x18001c45b  mov     rcx, [rbp+57h+string]
0x18001c45f  lea     r8, [rbp+57h+var_78]
0x18001c463  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18001c46a  call    cs:__imp_RoGetActivationFactory
0x18001c470  mov     ebx, eax
0x18001c472  test    eax, eax
0x18001c474  js      loc_18001C7BF
0x18001c47a  mov     rbx, [rbp+57h+var_78]
0x18001c47e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001c482  mov     [rbp+57h+var_70], r15
0x18001c486  mov     r14, [rbx]
0x18001c489  mov     [rbp+57h+string], r15
0x18001c48d  inc     rdx; length
0x18001c490  cmp     [rsi+rdx*2], r15w
0x18001c495  jnz     short loc_18001C48D
0x18001c497  mov     eax, 0FFFFFFFFh
0x18001c49c  cmp     rdx, rax
0x18001c49f  ja      short loc_18001C4A8
0x18001c4a1  lea     eax, [rdx+1]
0x18001c4a4  cmp     eax, edx
0x18001c4a6  jnb     short loc_18001C4BE
0x18001c4a8  xor     r9d, r9d; lpArguments
0x18001c4ab  xor     r8d, r8d; nNumberOfArguments
0x18001c4ae  mov     ecx, 80070216h; dwExceptionCode
0x18001c4b3  lea     edx, [r9+1]; dwExceptionFlags
0x18001c4b7  call    cs:__imp_RaiseException
0x18001c4bd  int     3; Trap to Debugger
0x18001c4be  lea     r9, [rbp+57h+string]; string
0x18001c4c2  mov     rcx, rsi; sourceString
0x18001c4c5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001c4c9  call    cs:__imp_WindowsCreateStringReference
0x18001c4cf  test    eax, eax
0x18001c4d1  js      loc_18001C80F
0x18001c4d7  mov     r8, [rbp+57h+string]
0x18001c4db  lea     rax, [rbp+57h+var_70]
0x18001c4df  mov     rdx, [rbp+57h+var_80]
0x18001c4e3  mov     r9d, 1
0x18001c4e9  mov     [rsp+0B0h+var_90], rax
0x18001c4ee  mov     rcx, rbx
0x18001c4f1  mov     rax, [r14+1A8h]
0x18001c4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4fd  mov     ebx, eax
0x18001c4ff  test    eax, eax
0x18001c501  js      loc_18001C644
0x18001c507  lea     r9, [rbp+57h+string]; string
0x18001c50b  mov     [rbp+57h+var_68], r15
0x18001c50f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001c513  mov     [rbp+57h+string], r15
0x18001c517  mov     edx, 2Ch ; ','; length
0x18001c51c  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageUser@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18001c523  call    cs:__imp_WindowsCreateStringReference
0x18001c529  test    eax, eax
0x18001c52b  js      loc_18001C822
0x18001c531  mov     rcx, [rbp+57h+string]
0x18001c535  lea     r8, [rbp+57h+var_68]
0x18001c539  lea     rdx, _GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6
0x18001c540  call    cs:__imp_RoGetActivationFactory
0x18001c546  mov     ebx, eax
0x18001c548  test    eax, eax
0x18001c54a  js      loc_18001C7DF
0x18001c550  mov     rcx, [rbp+57h+var_70]
0x18001c554  lea     rax, [rbp+57h+var_68]
0x18001c558  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18001c55c  lea     rdx, [rbp+57h+hstringHeader]
0x18001c560  lea     rax, [rbp+57h+var_80]
0x18001c564  mov     [rbp+57h+var_60], r15
0x18001c568  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x18001c56c  lea     rax, [rbp+57h+var_58]
0x18001c570  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x18001c574  lea     rax, [rbp+57h+var_60]
0x18001c578  mov     [rbp+57h+string], rax
0x18001c57c  mov     [rbp+57h+var_58], r15
0x18001c580  call    ForEach_Windows__Internal__StateRepository__Package____lambda_8ac71d931e4442495cadb6e2921601b1___
0x18001c585  mov     rcx, [rbp+57h+var_58]
0x18001c589  mov     ebx, eax
0x18001c58b  test    eax, eax
0x18001c58d  js      loc_18001C6B4
0x18001c593  test    rcx, rcx
0x18001c596  jz      loc_18001C718
0x18001c59c  test    rdi, rdi
0x18001c59f  jz      short loc_18001C5AE
0x18001c5a1  mov     rax, rcx
0x18001c5a4  mov     rcx, r15
0x18001c5a7  mov     [rbp+57h+var_58], rcx
0x18001c5ab  mov     [rdi], rax
0x18001c5ae  test    rcx, rcx
0x18001c5b1  jz      short loc_18001C5C3
0x18001c5b3  mov     [rbp+57h+var_58], r15
0x18001c5b7  mov     rax, [rcx]
0x18001c5ba  mov     rax, [rax+10h]
0x18001c5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5c3  mov     rcx, [rbp+57h+var_60]
0x18001c5c7  test    rcx, rcx
0x18001c5ca  jz      short loc_18001C5DC
0x18001c5cc  mov     [rbp+57h+var_60], r15
0x18001c5d0  mov     rax, [rcx]
0x18001c5d3  mov     rax, [rax+10h]
0x18001c5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5dc  mov     rcx, [rbp+57h+var_68]
0x18001c5e0  test    rcx, rcx
0x18001c5e3  jz      short loc_18001C5F5
0x18001c5e5  mov     [rbp+57h+var_68], r15
0x18001c5e9  mov     rax, [rcx]
0x18001c5ec  mov     rax, [rax+10h]
0x18001c5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5f5  mov     rcx, [rbp+57h+var_70]
0x18001c5f9  test    rcx, rcx
0x18001c5fc  jz      short loc_18001C60E
0x18001c5fe  mov     [rbp+57h+var_70], r15
0x18001c602  mov     rax, [rcx]
0x18001c605  mov     rax, [rax+10h]
0x18001c609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c60e  mov     rcx, [rbp+57h+var_78]
0x18001c612  test    rcx, rcx
0x18001c615  jz      short loc_18001C627
0x18001c617  mov     [rbp+57h+var_78], r15
0x18001c61b  mov     rax, [rcx]
0x18001c61e  mov     rax, [rax+10h]
0x18001c622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c627  mov     rcx, [rbp+57h+var_80]
0x18001c62b  test    rcx, rcx
0x18001c62e  jz      short loc_18001C640
0x18001c630  mov     [rbp+57h+var_80], r15
0x18001c634  mov     rax, [rcx]
0x18001c637  mov     rax, [rax+10h]
0x18001c63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c640  xor     eax, eax
0x18001c642  jmp     short loc_18001C691
0x18001c644  mov     rcx, [rbp+57h+var_70]
0x18001c648  test    rcx, rcx
0x18001c64b  jz      short loc_18001C65D
0x18001c64d  mov     [rbp+57h+var_70], r15
0x18001c651  mov     rdx, [rcx]
0x18001c654  mov     rax, [rdx+10h]
0x18001c658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c65d  mov     rcx, [rbp+57h+var_78]
0x18001c661  test    rcx, rcx
0x18001c664  jz      short loc_18001C676
0x18001c666  mov     [rbp+57h+var_78], r15
0x18001c66a  mov     rax, [rcx]
0x18001c66d  mov     rax, [rax+10h]
0x18001c671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c676  mov     rcx, [rbp+57h+var_80]
0x18001c67a  test    rcx, rcx
0x18001c67d  jz      short loc_18001C68F
0x18001c67f  mov     [rbp+57h+var_80], r15
0x18001c683  mov     rax, [rcx]
0x18001c686  mov     rax, [rax+10h]
0x18001c68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c68f  mov     eax, ebx
0x18001c691  mov     rcx, [rbp+57h+var_30]
0x18001c695  xor     rcx, rsp; StackCookie
0x18001c698  call    __security_check_cookie
0x18001c69d  mov     rbx, [rsp+0B0h+arg_8]
0x18001c6a5  add     rsp, 90h
0x18001c6ac  pop     r15
0x18001c6ae  pop     r14
0x18001c6b0  pop     rdi
0x18001c6b1  pop     rsi
0x18001c6b2  pop     rbp
0x18001c6b3  retn
0x18001c6b4  test    rcx, rcx
0x18001c6b7  jz      short loc_18001C6C9
0x18001c6b9  mov     [rbp+57h+var_58], r15
0x18001c6bd  mov     rdx, [rcx]
0x18001c6c0  mov     rax, [rdx+10h]
0x18001c6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6c9  mov     rcx, [rbp+57h+var_60]
0x18001c6cd  test    rcx, rcx
0x18001c6d0  jz      short loc_18001C6E2
0x18001c6d2  mov     [rbp+57h+var_60], r15
0x18001c6d6  mov     rax, [rcx]
0x18001c6d9  mov     rax, [rax+10h]
0x18001c6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6e2  mov     rcx, [rbp+57h+var_68]
0x18001c6e6  test    rcx, rcx
0x18001c6e9  jz      short loc_18001C6FB
0x18001c6eb  mov     [rbp+57h+var_68], r15
0x18001c6ef  mov     rax, [rcx]
0x18001c6f2  mov     rax, [rax+10h]
0x18001c6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6fb  mov     rcx, [rbp+57h+var_70]
0x18001c6ff  test    rcx, rcx
0x18001c702  jz      loc_18001C65D
0x18001c708  mov     [rbp+57h+var_70], r15
0x18001c70c  mov     rax, [rcx]
0x18001c70f  mov     rax, [rax+10h]
0x18001c713  jmp     loc_18001C658
0x18001c718  mov     rcx, [rbp+57h+var_60]
0x18001c71c  test    rcx, rcx
0x18001c71f  jz      short loc_18001C731
0x18001c721  mov     [rbp+57h+var_60], r15
0x18001c725  mov     rax, [rcx]
0x18001c728  mov     rax, [rax+10h]
0x18001c72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c731  mov     rcx, [rbp+57h+var_68]
0x18001c735  test    rcx, rcx
0x18001c738  jz      short loc_18001C74A
0x18001c73a  mov     [rbp+57h+var_68], r15
0x18001c73e  mov     rax, [rcx]
0x18001c741  mov     rax, [rax+10h]
0x18001c745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c74a  mov     rcx, [rbp+57h+var_70]
0x18001c74e  test    rcx, rcx
0x18001c751  jz      short loc_18001C763
0x18001c753  mov     [rbp+57h+var_70], r15
0x18001c757  mov     rax, [rcx]
0x18001c75a  mov     rax, [rax+10h]
0x18001c75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c763  mov     rcx, [rbp+57h+var_78]
0x18001c767  test    rcx, rcx
0x18001c76a  jz      short loc_18001C77C
0x18001c76c  mov     [rbp+57h+var_78], r15
0x18001c770  mov     rax, [rcx]
0x18001c773  mov     rax, [rax+10h]
0x18001c777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c77c  mov     rcx, [rbp+57h+var_80]
0x18001c780  test    rcx, rcx
0x18001c783  jz      short loc_18001C795
0x18001c785  mov     [rbp+57h+var_80], r15
0x18001c789  mov     rax, [rcx]
0x18001c78c  mov     rax, [rax+10h]
0x18001c790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c795  mov     eax, 80070490h
0x18001c79a  jmp     loc_18001C691
0x18001c79f  mov     rdx, [rbp+57h+var_80]
0x18001c7a3  test    rdx, rdx
0x18001c7a6  jz      loc_18001C68F
0x18001c7ac  mov     [rbp+57h+var_80], r15
0x18001c7b0  mov     rcx, [rdx]
0x18001c7b3  mov     rax, [rcx+10h]
0x18001c7b7  mov     rcx, rdx
0x18001c7ba  jmp     loc_18001C68A
0x18001c7bf  mov     rdx, [rbp+57h+var_78]
0x18001c7c3  test    rdx, rdx
0x18001c7c6  jz      loc_18001C676
0x18001c7cc  mov     [rbp+57h+var_78], r15
0x18001c7d0  mov     rcx, [rdx]
0x18001c7d3  mov     rax, [rcx+10h]
0x18001c7d7  mov     rcx, rdx
0x18001c7da  jmp     loc_18001C671
0x18001c7df  mov     rcx, [rbp+57h+var_68]
0x18001c7e3  test    rcx, rcx
0x18001c7e6  jz      loc_18001C6FB
0x18001c7ec  mov     [rbp+57h+var_68], r15
0x18001c7f0  mov     rdx, [rcx]
0x18001c7f3  mov     rax, [rdx+10h]
0x18001c7f7  jmp     loc_18001C6F6
0x18001c7fc  xor     r9d, r9d; lpArguments
0x18001c7ff  xor     r8d, r8d; nNumberOfArguments
0x18001c802  mov     ecx, eax; dwExceptionCode
0x18001c804  lea     edx, [r9+1]; dwExceptionFlags
0x18001c808  call    cs:__imp_RaiseException
0x18001c80e  int     3; Trap to Debugger
0x18001c80f  xor     r9d, r9d; lpArguments
0x18001c812  xor     r8d, r8d; nNumberOfArguments
0x18001c815  mov     ecx, eax; dwExceptionCode
0x18001c817  lea     edx, [r9+1]; dwExceptionFlags
0x18001c81b  call    cs:__imp_RaiseException
0x18001c821  int     3; Trap to Debugger
0x18001c822  xor     r9d, r9d; lpArguments
0x18001c825  xor     r8d, r8d; nNumberOfArguments
0x18001c828  mov     ecx, eax; dwExceptionCode
0x18001c82a  lea     edx, [r9+1]; dwExceptionFlags
0x18001c82e  call    cs:__imp_RaiseException
```
