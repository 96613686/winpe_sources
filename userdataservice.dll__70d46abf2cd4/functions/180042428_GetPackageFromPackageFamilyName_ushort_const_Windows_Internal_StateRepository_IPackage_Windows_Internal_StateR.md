# GetPackageFromPackageFamilyName(ushort const *,Windows::Internal::StateRepository::IPackage * *,Windows::Internal::StateRepository::IPackageUser * *)

- ea: `0x180042428`
- end: `0x18004287f`
- name: `?GetPackageFromPackageFamilyName@@YAJPEBGPEAPEAUIPackage@StateRepository@Internal@Windows@@PEAPEAUIPackageUser@234@@Z`
- size: `1111`
- prototype: `__int64 __fastcall(PCWSTR sourceString, struct Windows::Internal::StateRepository::IPackage **, struct Windows::Internal::StateRepository::IPackageUser **)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180040d98`
- `0x180041be4`
- `0x180042360`
- `0x180116c9c`
- `0x180116d00`

## callees

- `0x180004658`
- `0x180042428`
- `0x180042888`
- `0x180042d18`
- `0x180042d64`
- `0x180042d90`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800424f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042843`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042856`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800424f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042843`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042856`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180042491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004257d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180042491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004257d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800424ae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004259a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800424ae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004259a`

## pseudocode

```c
__int64 __fastcall GetPackageFromPackageFamilyName(
        PCWSTR sourceString,
        struct Windows::Internal::StateRepository::IPackage **a2,
        struct Windows::Internal::StateRepository::IPackageUser **a3)
{
  int CurrentUser; // ebx
  HRESULT v7; // eax
  _QWORD *v8; // r14
  unsigned __int64 v9; // rbx
  __int64 v10; // r13
  struct Windows::Internal::StateRepository::IUser *v11; // rcx
  void (*v12)(void); // rax
  unsigned int v13; // eax
  HRESULT v14; // eax
  __int64 v15; // rcx
  void (*v16)(void); // rax
  __int64 v17; // rcx
  void (*v18)(void); // rax
  _QWORD *v19; // rcx
  void (*v20)(void); // rax
  struct Windows::Internal::StateRepository::IUser *v21; // rcx
  struct Windows::Internal::StateRepository::IPackageUser *v23; // rcx
  struct Windows::Internal::StateRepository::IPackage *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  struct Windows::Internal::StateRepository::IUser *v28; // rcx
  struct Windows::Internal::StateRepository::IPackage *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  _QWORD *v32; // rcx
  struct Windows::Internal::StateRepository::IUser *v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // rcx
  struct Windows::Internal::StateRepository::IPackage *v36; // rcx
  __int64 v37; // rcx
  struct Windows::Internal::StateRepository::IPackageUser *v38; // rax
  struct Windows::Internal::StateRepository::IUser *v39; // [rsp+30h] [rbp-39h] BYREF
  _QWORD *v40; // [rsp+38h] [rbp-31h] BYREF
  __int64 v41; // [rsp+40h] [rbp-29h] BYREF
  __int64 v42; // [rsp+48h] [rbp-21h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v43; // [rsp+50h] [rbp-19h] BYREF
  struct Windows::Internal::StateRepository::IPackageUser *v44; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string; // [rsp+78h] [rbp+Fh] BYREF

  v39 = 0;
  CurrentUser = GetCurrentUser(&v39);
  if ( CurrentUser < 0 )
  {
    v11 = v39;
    if ( v39 )
    {
      v39 = 0;
      v12 = *(void (**)(void))(*(_QWORD *)v11 + 16LL);
LABEL_24:
      v12();
    }
    return (unsigned int)CurrentUser;
  }
  v40 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    __debugbreak();
  }
  CurrentUser = RoGetActivationFactory(string, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v40);
  if ( CurrentUser < 0 )
  {
    v34 = v40;
    if ( !v40 )
    {
LABEL_22:
      v21 = v39;
      if ( v39 )
      {
        v39 = 0;
        v12 = *(void (**)(void))(*(_QWORD *)v21 + 16LL);
        goto LABEL_24;
      }
      return (unsigned int)CurrentUser;
    }
    v40 = 0;
    v20 = *(void (**)(void))(*v34 + 16LL);
LABEL_21:
    v20();
    goto LABEL_22;
  }
  v8 = v40;
  v9 = -1;
  v41 = 0;
  v10 = *v40;
  string = 0;
  do
    ++v9;
  while ( sourceString[v9] );
  if ( v9 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v9);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, sourceString, v13, v9);
  CurrentUser = (*(__int64 (__fastcall **)(_QWORD *, struct Windows::Internal::StateRepository::IUser *, HSTRING, __int64, __int64 *))(v10 + 424))(
                  v8,
                  v39,
                  string,
                  1,
                  &v41);
  if ( CurrentUser < 0 )
  {
    v35 = v41;
    if ( !v41 )
      goto LABEL_19;
    v41 = 0;
    v18 = *(void (**)(void))(*(_QWORD *)v35 + 16LL);
    goto LABEL_18;
  }
  v42 = 0;
  string = 0;
  v14 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageUser", 0x2Cu, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
    __debugbreak();
  }
  CurrentUser = RoGetActivationFactory(string, &GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6, &v42);
  if ( CurrentUser < 0 )
  {
    v15 = v42;
    if ( !v42 )
    {
LABEL_16:
      v17 = v41;
      if ( !v41 )
      {
LABEL_19:
        v19 = v40;
        if ( !v40 )
          goto LABEL_22;
        v40 = 0;
        v20 = *(void (**)(void))(*v19 + 16LL);
        goto LABEL_21;
      }
      v41 = 0;
      v18 = *(void (**)(void))(*(_QWORD *)v17 + 16LL);
LABEL_18:
      v18();
      goto LABEL_19;
    }
    v42 = 0;
    v16 = *(void (**)(void))(*(_QWORD *)v15 + 16LL);
LABEL_15:
    v16();
    goto LABEL_16;
  }
  hstringHeader.Reserved.Reserved1 = &v42;
  v43 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v39;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v44;
  string = (HSTRING)&v43;
  v44 = 0;
  CurrentUser = ForEach_Windows::Internal::StateRepository::Package____lambda_8ac71d931e4442495cadb6e2921601b1___(
                  v41,
                  &hstringHeader);
  if ( CurrentUser < 0 )
  {
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v44);
    v36 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = v42;
    if ( !v42 )
      goto LABEL_16;
    v42 = 0;
    v16 = *(void (**)(void))(*(_QWORD *)v37 + 16LL);
    goto LABEL_15;
  }
  v23 = v44;
  if ( v44 )
  {
    if ( a2 )
    {
      *a2 = v43;
      v43 = 0;
    }
    if ( a3 )
    {
      v38 = v23;
      v23 = 0;
      v44 = 0;
      *a3 = v38;
    }
    if ( v23 )
    {
      v44 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackageUser *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
    }
    v28 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IUser *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    return 0;
  }
  else
  {
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v44);
    v29 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
    }
    v33 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IUser *))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return 2147943568LL;
  }
}

```

## disassembly

```asm
0x180042428  mov     [rsp-8+arg_18], rbx
0x18004242d  push    rbp
0x18004242e  push    rsi
0x18004242f  push    rdi
0x180042430  push    r12
0x180042432  push    r13
0x180042434  push    r14
0x180042436  push    r15
0x180042438  lea     rbp, [rsp-27h]
0x18004243d  sub     rsp, 90h
0x180042444  mov     rax, cs:__security_cookie
0x18004244b  xor     rax, rsp
0x18004244e  mov     [rbp+57h+var_40], rax
0x180042452  mov     r15, rcx
0x180042455  xor     r12d, r12d
0x180042458  lea     rcx, [rbp+57h+var_90]; struct Windows::Internal::StateRepository::IUser **
0x18004245c  mov     [rbp+57h+var_90], r12
0x180042460  mov     rsi, r8
0x180042463  mov     rdi, rdx
0x180042466  call    ?GetCurrentUser@@YAJPEAPEAUIUser@StateRepository@Internal@Windows@@@Z; GetCurrentUser(Windows::Internal::StateRepository::IUser * *)
0x18004246b  mov     ebx, eax
0x18004246d  test    eax, eax
0x18004246f  js      loc_1800424FB
0x180042475  lea     r9, [rbp+57h+string]; string
0x180042479  mov     [rbp+57h+var_88], r12
0x18004247d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180042481  mov     [rbp+57h+string], r12
0x180042485  lea     edx, [r12+28h]; length
0x18004248a  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180042491  call    cs:__imp_WindowsCreateStringReference
0x180042497  test    eax, eax
0x180042499  js      loc_180042837
0x18004249f  mov     rcx, [rbp+57h+string]
0x1800424a3  lea     r8, [rbp+57h+var_88]
0x1800424a7  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x1800424ae  call    cs:__imp_RoGetActivationFactory
0x1800424b4  mov     ebx, eax
0x1800424b6  test    eax, eax
0x1800424b8  js      loc_1800427BE
0x1800424be  mov     r14, [rbp+57h+var_88]
0x1800424c2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800424c6  mov     [rbp+57h+var_80], r12
0x1800424ca  mov     r13, [r14]
0x1800424cd  mov     [rbp+57h+string], r12
0x1800424d1  inc     rbx
0x1800424d4  cmp     [r15+rbx*2], r12w
0x1800424d9  jnz     short loc_1800424D1
0x1800424db  mov     eax, 0FFFFFFFFh
0x1800424e0  cmp     rbx, rax
0x1800424e3  jbe     short loc_180042518
0x1800424e5  xor     r9d, r9d; lpArguments
0x1800424e8  xor     r8d, r8d; nNumberOfArguments
0x1800424eb  mov     ecx, 80070216h; dwExceptionCode
0x1800424f0  lea     edx, [r9+1]; dwExceptionFlags
0x1800424f4  call    cs:__imp_RaiseException
0x1800424fa  int     3; Trap to Debugger
0x1800424fb  mov     rcx, [rbp+57h+var_90]
0x1800424ff  test    rcx, rcx
0x180042502  jz      loc_18004260E
0x180042508  mov     [rbp+57h+var_90], r12
0x18004250c  mov     rdx, [rcx]
0x18004250f  mov     rax, [rdx+10h]
0x180042513  jmp     loc_180042609
0x180042518  mov     ecx, ebx; unsigned int
0x18004251a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18004251f  mov     r9d, ebx; unsigned int
0x180042522  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180042526  mov     r8d, eax; unsigned int
0x180042529  mov     rdx, r15; sourceString
0x18004252c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180042531  mov     r8, [rbp+57h+string]
0x180042535  lea     rax, [rbp+57h+var_80]
0x180042539  mov     rdx, [rbp+57h+var_90]
0x18004253d  mov     r9d, 1
0x180042543  mov     [rsp+0C0h+var_A0], rax
0x180042548  mov     rcx, r14
0x18004254b  mov     rax, [r13+1A8h]
0x180042552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042557  mov     ebx, eax
0x180042559  test    eax, eax
0x18004255b  js      loc_1800427DB
0x180042561  lea     r9, [rbp+57h+string]; string
0x180042565  mov     [rbp+57h+var_78], r12
0x180042569  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004256d  mov     [rbp+57h+string], r12
0x180042571  mov     edx, 2Ch ; ','; length
0x180042576  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageUser@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18004257d  call    cs:__imp_WindowsCreateStringReference
0x180042583  test    eax, eax
0x180042585  js      loc_18004284A
0x18004258b  mov     rcx, [rbp+57h+string]
0x18004258f  lea     r8, [rbp+57h+var_78]
0x180042593  lea     rdx, _GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6
0x18004259a  call    cs:__imp_RoGetActivationFactory
0x1800425a0  mov     ebx, eax
0x1800425a2  test    eax, eax
0x1800425a4  jns     loc_180042637
0x1800425aa  mov     rcx, [rbp+57h+var_78]
0x1800425ae  test    rcx, rcx
0x1800425b1  jz      short loc_1800425C3
0x1800425b3  mov     [rbp+57h+var_78], r12
0x1800425b7  mov     rdx, [rcx]
0x1800425ba  mov     rax, [rdx+10h]
0x1800425be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425c3  mov     rcx, [rbp+57h+var_80]
0x1800425c7  test    rcx, rcx
0x1800425ca  jz      short loc_1800425DC
0x1800425cc  mov     [rbp+57h+var_80], r12
0x1800425d0  mov     rax, [rcx]
0x1800425d3  mov     rax, [rax+10h]
0x1800425d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425dc  mov     rcx, [rbp+57h+var_88]
0x1800425e0  test    rcx, rcx
0x1800425e3  jz      short loc_1800425F5
0x1800425e5  mov     [rbp+57h+var_88], r12
0x1800425e9  mov     rax, [rcx]
0x1800425ec  mov     rax, [rax+10h]
0x1800425f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425f5  mov     rcx, [rbp+57h+var_90]
0x1800425f9  test    rcx, rcx
0x1800425fc  jz      short loc_18004260E
0x1800425fe  mov     [rbp+57h+var_90], r12
0x180042602  mov     rax, [rcx]
0x180042605  mov     rax, [rax+10h]
0x180042609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004260e  mov     eax, ebx
0x180042610  mov     rcx, [rbp+57h+var_40]
0x180042614  xor     rcx, rsp; StackCookie
0x180042617  call    __security_check_cookie
0x18004261c  mov     rbx, [rsp+0C0h+arg_18]
0x180042624  add     rsp, 90h
0x18004262b  pop     r15
0x18004262d  pop     r14
0x18004262f  pop     r13
0x180042631  pop     r12
0x180042633  pop     rdi
0x180042634  pop     rsi
0x180042635  pop     rbp
0x180042636  retn
0x180042637  mov     rcx, [rbp+57h+var_80]
0x18004263b  lea     rax, [rbp+57h+var_78]
0x18004263f  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180042643  lea     rdx, [rbp+57h+hstringHeader]
0x180042647  lea     rax, [rbp+57h+var_90]
0x18004264b  mov     [rbp+57h+var_70], r12
0x18004264f  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x180042653  lea     rax, [rbp+57h+var_68]
0x180042657  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x18004265b  lea     rax, [rbp+57h+var_70]
0x18004265f  mov     [rbp+57h+string], rax
0x180042663  mov     [rbp+57h+var_68], r12
0x180042667  call    ForEach_Windows__Internal__StateRepository__Package____lambda_8ac71d931e4442495cadb6e2921601b1___
0x18004266c  mov     ebx, eax
0x18004266e  test    eax, eax
0x180042670  js      loc_1800427F8
0x180042676  mov     rcx, [rbp+57h+var_68]
0x18004267a  test    rcx, rcx
0x18004267d  jz      loc_18004272E
0x180042683  test    rdi, rdi
0x180042686  jnz     loc_18004285D
0x18004268c  test    rsi, rsi
0x18004268f  jnz     loc_18004286D
0x180042695  test    rcx, rcx
0x180042698  jz      short loc_1800426AA
0x18004269a  mov     [rbp+57h+var_68], r12
0x18004269e  mov     rax, [rcx]
0x1800426a1  mov     rax, [rax+10h]
0x1800426a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426aa  mov     rcx, [rbp+57h+var_70]
0x1800426ae  test    rcx, rcx
0x1800426b1  jz      short loc_1800426C3
0x1800426b3  mov     [rbp+57h+var_70], r12
0x1800426b7  mov     rax, [rcx]
0x1800426ba  mov     rax, [rax+10h]
0x1800426be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426c3  mov     rcx, [rbp+57h+var_78]
0x1800426c7  test    rcx, rcx
0x1800426ca  jz      short loc_1800426DC
0x1800426cc  mov     [rbp+57h+var_78], r12
0x1800426d0  mov     rax, [rcx]
0x1800426d3  mov     rax, [rax+10h]
0x1800426d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426dc  mov     rcx, [rbp+57h+var_80]
0x1800426e0  test    rcx, rcx
0x1800426e3  jz      short loc_1800426F5
0x1800426e5  mov     [rbp+57h+var_80], r12
0x1800426e9  mov     rax, [rcx]
0x1800426ec  mov     rax, [rax+10h]
0x1800426f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426f5  mov     rcx, [rbp+57h+var_88]
0x1800426f9  test    rcx, rcx
0x1800426fc  jz      short loc_18004270E
0x1800426fe  mov     [rbp+57h+var_88], r12
0x180042702  mov     rax, [rcx]
0x180042705  mov     rax, [rax+10h]
0x180042709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004270e  mov     rcx, [rbp+57h+var_90]
0x180042712  test    rcx, rcx
0x180042715  jz      short loc_180042727
0x180042717  mov     [rbp+57h+var_90], r12
0x18004271b  mov     rax, [rcx]
0x18004271e  mov     rax, [rax+10h]
0x180042722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042727  xor     eax, eax
0x180042729  jmp     loc_180042610
0x18004272e  lea     rcx, [rbp+57h+var_68]
0x180042732  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180042737  mov     rcx, [rbp+57h+var_70]
0x18004273b  test    rcx, rcx
0x18004273e  jz      short loc_180042750
0x180042740  mov     [rbp+57h+var_70], r12
0x180042744  mov     rax, [rcx]
0x180042747  mov     rax, [rax+10h]
0x18004274b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042750  mov     rcx, [rbp+57h+var_78]
0x180042754  test    rcx, rcx
0x180042757  jz      short loc_180042769
0x180042759  mov     [rbp+57h+var_78], r12
0x18004275d  mov     rax, [rcx]
0x180042760  mov     rax, [rax+10h]
0x180042764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042769  mov     rcx, [rbp+57h+var_80]
0x18004276d  test    rcx, rcx
0x180042770  jz      short loc_180042782
0x180042772  mov     [rbp+57h+var_80], r12
0x180042776  mov     rax, [rcx]
0x180042779  mov     rax, [rax+10h]
0x18004277d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042782  mov     rcx, [rbp+57h+var_88]
0x180042786  test    rcx, rcx
0x180042789  jz      short loc_18004279B
0x18004278b  mov     [rbp+57h+var_88], r12
0x18004278f  mov     rax, [rcx]
0x180042792  mov     rax, [rax+10h]
0x180042796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004279b  mov     rcx, [rbp+57h+var_90]
0x18004279f  test    rcx, rcx
0x1800427a2  jz      short loc_1800427B4
0x1800427a4  mov     [rbp+57h+var_90], r12
0x1800427a8  mov     rax, [rcx]
0x1800427ab  mov     rax, [rax+10h]
0x1800427af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427b4  mov     eax, 80070490h
0x1800427b9  jmp     loc_180042610
0x1800427be  mov     rcx, [rbp+57h+var_88]
0x1800427c2  test    rcx, rcx
0x1800427c5  jz      loc_1800425F5
0x1800427cb  mov     [rbp+57h+var_88], r12
0x1800427cf  mov     rdx, [rcx]
0x1800427d2  mov     rax, [rdx+10h]
0x1800427d6  jmp     loc_1800425F0
0x1800427db  mov     rcx, [rbp+57h+var_80]
0x1800427df  test    rcx, rcx
0x1800427e2  jz      loc_1800425DC
0x1800427e8  mov     [rbp+57h+var_80], r12
0x1800427ec  mov     rdx, [rcx]
0x1800427ef  mov     rax, [rdx+10h]
0x1800427f3  jmp     loc_1800425D7
0x1800427f8  lea     rcx, [rbp+57h+var_68]
0x1800427fc  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180042801  mov     rcx, [rbp+57h+var_70]
0x180042805  test    rcx, rcx
0x180042808  jz      short loc_18004281A
0x18004280a  mov     [rbp+57h+var_70], r12
0x18004280e  mov     rdx, [rcx]
0x180042811  mov     rax, [rdx+10h]
0x180042815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004281a  mov     rcx, [rbp+57h+var_78]
0x18004281e  test    rcx, rcx
0x180042821  jz      loc_1800425C3
0x180042827  mov     [rbp+57h+var_78], r12
0x18004282b  mov     rax, [rcx]
0x18004282e  mov     rax, [rax+10h]
0x180042832  jmp     loc_1800425BE
0x180042837  xor     r9d, r9d; lpArguments
0x18004283a  xor     r8d, r8d; nNumberOfArguments
0x18004283d  mov     ecx, eax; dwExceptionCode
0x18004283f  lea     edx, [r9+1]; dwExceptionFlags
0x180042843  call    cs:__imp_RaiseException
0x180042849  int     3; Trap to Debugger
0x18004284a  xor     r9d, r9d; lpArguments
0x18004284d  xor     r8d, r8d; nNumberOfArguments
0x180042850  mov     ecx, eax; dwExceptionCode
0x180042852  lea     edx, [r9+1]; dwExceptionFlags
0x180042856  call    cs:__imp_RaiseException
0x18004285c  int     3; Trap to Debugger
0x18004285d  mov     rax, [rbp+57h+var_70]
0x180042861  mov     [rdi], rax
0x180042864  mov     [rbp+57h+var_70], r12
0x180042868  jmp     loc_18004268C
0x18004286d  mov     rax, rcx
0x180042870  mov     rcx, r12
0x180042873  mov     [rbp+57h+var_68], rcx
0x180042877  mov     [rsi], rax
0x18004287a  jmp     loc_180042695
```
